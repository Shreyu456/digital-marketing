import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { motion } from "framer-motion";
import { FaFacebook, FaTwitter, FaLinkedin } from "react-icons/fa";

const services = [{ title: "SEO Optimization", desc: "Improve your search engine rankings." },
{ title: "Social Media Marketing", desc: "Grow your brand presence online." },
{ title: "Content Creation", desc: "Engage your audience with quality content." },
];
const testimonials = [
  { name: "John Doe", review: "Amazing agency! Helped us scale our business." },
  { name: "Jane Smith", review: "Great results and excellent support!" },
];

export default function DigitalAgency() {
  return (
    <div className="min-h-screen bg-gray-50 text-gray-900 p-6">
      <header className="text-center py-6">
        <h1 className="text-4xl font-bold">Digital Marketing Agency</h1>
        <p className="text-lg text-gray-600">Helping brands grow online</p>
      </header>

      <section className="grid md:grid-cols-3 gap-6 my-10">
        {services.map((service, index) => (
          <Card key={index} className="p-6 shadow-lg rounded-xl bg-white">
            <CardContent>
              <h2 className="text-xl font-semibold">{service.title}</h2>
              <p className="text-gray-600">{service.desc}</p>
            </CardContent>
          </Card>
        ))}
      </section>

      <section className="text-center my-10">
        <h2 className="text-2xl font-bold">What Our Clients Say</h2>
        <div className="mt-6 space-y-4">
          {testimonials.map((t, index) => (
            <motion.div key={index} className="p-4 bg-white shadow-md rounded-lg" whileHover={{ scale: 1.05 }}>
              <p className="italic">"{t.review}"</p>
              <h3 className="font-semibold mt-2">- {t.name}</h3>
            </motion.div>
          ))}
        </div>
      </section>

      <footer className="text-center py-6 mt-10 border-t">
        <p className="text-gray-600">Follow us:</p>
        <div className="flex justify-center gap-4 mt-2">
          <FaFacebook className="text-blue-600 text-xl cursor-pointer" />
          <FaTwitter className="text-blue-400 text-xl cursor-pointer" />
          <FaLinkedin className="text-blue-700 text-xl cursor-pointer" />
        </div>
      </footer>
    </div>
  );
}
