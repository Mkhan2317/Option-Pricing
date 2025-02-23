# Option-Pricing
This repository stores Python code for pricing European call options using the Heston Stochastic Volatility Model. The Heston model is a popular choice in financial engineering for modeling the evolution of volatility over time, which addresses some of the limitations of the Black-Scholes model by allowing for a stochastic process for volatility. 
<br>
Author- Amir khan

import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { FaLinkedin, FaGithub, FaEnvelope } from "react-icons/fa";
import { motion } from "framer-motion";
import { Typewriter } from "react-simple-typewriter";

const portfolioData = {
  name: "MD Amir Khan",
  title: "Quantitative Researcher & Trader",
  description:
    "MS in Financial Engineering | Passionate about algorithmic trading, portfolio optimization, and risk management.",
  experience: [
    {
      role: "Quantitative Analyst",
      company: "Lanka Bangla Securities",
      duration: "Aug 2022 - Jun 2023",
    },
    {
      role: "Quantitative Risk Analyst",
      company: "UCB Stock Brokerage",
      duration: "Jun 2023 - Dec 2023",
    },
  ],
  projects: [
    "Factor Analysis on Vanguard ETFs",
    "Implied Volatility Calculation for SPX Options",
    "Pair Trading Strategy using Machine Learning",
  ],
  skills: ["Python", "C++", "Machine Learning", "Algorithmic Trading", "Portfolio Optimization"],
  contacts: {
    linkedin: "https://linkedin.com/in/mdamir-khan",
    github: "https://github.com/mdamirkhan",
    email: "mdamir.khan@example.com",
  },
};

export default function Portfolio() {
  return (
    <div className="min-h-screen p-8 bg-gray-900 text-white flex flex-col items-center">
      <motion.div
        className="max-w-4xl mx-auto"
        initial={{ opacity: 0, y: -20 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 1 }}
      >
        <header className="text-center mb-8">
          <h1 className="text-5xl font-extrabold">
            {portfolioData.name}
          </h1>
          <p className="text-xl text-gray-400 mt-2">
            <Typewriter words={[portfolioData.title]} loop={true} cursor={true} />
          </p>
        </header>
        
        <Card className="mb-6 bg-gray-800 shadow-lg hover:scale-105 transition-transform">
          <CardContent className="p-6">
            <p>{portfolioData.description}</p>
          </CardContent>
        </Card>

        <section className="mb-6">
          <h2 className="text-3xl font-bold mb-3">Experience</h2>
          {portfolioData.experience.map((job, index) => (
            <motion.div
              key={index}
              initial={{ opacity: 0, x: -20 }}
              animate={{ opacity: 1, x: 0 }}
              transition={{ delay: index * 0.2 }}
            >
              <Card className="mb-4 bg-gray-800 shadow-lg">
                <CardContent className="p-4">
                  <h3 className="text-lg font-semibold">{job.role} @ {job.company}</h3>
                  <p className="text-gray-400">{job.duration}</p>
                </CardContent>
              </Card>
            </motion.div>
          ))}
        </section>

        <section className="mb-6">
          <h2 className="text-3xl font-bold mb-3">Projects</h2>
          <ul className="list-disc pl-6">
            {portfolioData.projects.map((project, index) => (
              <motion.li 
                key={index} 
                initial={{ opacity: 0, x: -10 }}
                animate={{ opacity: 1, x: 0 }}
                transition={{ delay: index * 0.2 }}
              >
                {project}
              </motion.li>
            ))}
          </ul>
        </section>

        <section className="mb-6">
          <h2 className="text-3xl font-bold mb-3">Skills</h2>
          <div className="flex flex-wrap gap-2">
            {portfolioData.skills.map((skill, index) => (
              <motion.span
                key={index}
                className="px-3 py-1 bg-gradient-to-r from-purple-500 to-blue-500 rounded-full text-white shadow-md"
                initial={{ scale: 0 }}
                animate={{ scale: 1 }}
                transition={{ delay: index * 0.1 }}
              >
                {skill}
              </motion.span>
            ))}
          </div>
        </section>

        <footer className="text-center mt-8">
          <h2 className="text-3xl font-bold mb-3">Contact</h2>
          <div className="flex justify-center gap-4">
            <Button asChild variant="ghost">
              <a href={portfolioData.contacts.linkedin} target="_blank" rel="noopener noreferrer">
                <FaLinkedin size={30} className="hover:text-blue-500 transition-colors" />
              </a>
            </Button>
            <Button asChild variant="ghost">
              <a href={portfolioData.contacts.github} target="_blank" rel="noopener noreferrer">
                <FaGithub size={30} className="hover:text-gray-400 transition-colors" />
              </a>
            </Button>
            <Button asChild variant="ghost">
              <a href={`mailto:${portfolioData.contacts.email}`}>
                <FaEnvelope size={30} className="hover:text-red-500 transition-colors" />
              </a>
            </Button>
          </div>
        </footer>
      </motion.div>
    </div>
  );
}
