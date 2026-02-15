import React, { useState } from 'react';
import { Github, Mail, ExternalLink, Code, User, FileText } from 'lucide-react';

const Portfolio = () => {
  const [formData, setFormData] = useState({ name: '', email: '', message: '' });

  const projects = [
    { title: "E-Commerce Site", tech: "React, Node.js", desc: "A full-stack shop with payment integration." },
    { title: "Weather App", tech: "JavaScript, API", desc: "Real-time weather tracking using OpenWeather API." }
  ];

  const handleSubmit = (e) => {
    e.preventDefault();
    alert(`Message sent! (In a real app, this would hit your Node.js/MongoDB backend)`);
  };

  return (
    <div className="min-h-screen bg-gray-50 font-sans text-gray-900">
      {/* Navbar */}
      <nav className="p-6 flex justify-between items-center bg-white shadow-sm sticky top-0 z-10">
        <h1 className="text-xl font-bold text-blue-600">DevPortfolio</h1>
        <div className="space-x-6">
          <a href="#projects" className="hover:text-blue-500">Projects</a>
          <a href="#resume" className="hover:text-blue-500">Resume</a>
          <a href="#contact" className="bg-blue-600 text-white px-4 py-2 rounded-lg">Hire Me</a>
        </div>
      </nav>

      {/* Hero Section */}
      <header className="py-20 text-center px-4">
        <h2 className="text-5xl font-extrabold mb-4">Hi, I'm a Full-Stack Developer</h2>
        <p className="text-xl text-gray-600 max-w-2xl mx-auto">I build SEO-friendly, high-performance web applications using the MERN stack.</p>
      </header>

      {/* Projects Section */}
      <section id="projects" className="max-w-6xl mx-auto py-16 px-4">
        <div className="flex items-center mb-8 gap-2">
          <Code className="text-blue-600" />
          <h3 className="text-3xl font-bold">Featured Projects</h3>
        </div>
        <div className="grid md:grid-cols-2 gap-8">
          {projects.map((p, i) => (
            <div key={i} className="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition">
              <h4 className="text-xl font-bold mb-2">{p.title}</h4>
              <p className="text-blue-500 text-sm mb-3">{p.tech}</p>
              <p className="text-gray-600 mb-4">{p.desc}</p>
              <a href="#" className="flex items-center gap-1 text-blue-600 font-medium">View Code <ExternalLink size={16}/></a>
            </div>
          ))}
        </div>
      </section>

      {/* Resume Section */}
      <section id="resume" className="bg-white py-16 px-4">
        <div className="max-w-6xl mx-auto">
          <div className="flex items-center mb-8 gap-2">
            <FileText className="text-blue-600" />
            <h3 className="text-3xl font-bold">Interactive Resume</h3>
          </div>
          <div className="border-l-4 border-blue-600 pl-6 space-y-8">
            <div>
              <span className="text-sm font-bold text-blue-600">2023 - Present</span>
              <h4 className="text-xl font-bold">Junior Web Developer</h4>
              <p className="text-gray-600 italic">Tech Solutions Inc.</p>
            </div>
            <div>
              <span className="text-sm font-bold text-blue-600">2021 - 2023</span>
              <h4 className="text-xl font-bold">Computer Science Degree</h4>
              <p className="text-gray-600 italic">State University</p>
            </div>
          </div>
        </div>
      </section>

      {/* Contact Section */}
      <section id="contact" className="max-w-3xl mx-auto py-16 px-4 text-center">
        <h3 className="text-3xl font-bold mb-8">Get In Touch</h3>
        <form onSubmit={handleSubmit} className="space-y-4">
          <input 
            type="text" placeholder="Your Name" required
            className="w-full p-3 border rounded-lg outline-none focus:ring-2 focus:ring-blue-500"
            onChange={(e) => setFormData({...formData, name: e.target.value})}
          />
          <input 
            type="email" placeholder="Your Email" required
            className="w-full p-3 border rounded-lg outline-none focus:ring-2 focus:ring-blue-500"
            onChange={(e) => setFormData({...formData, email: e.target.value})}
          />
          <textarea 
            placeholder="Your Message" rows="4" required
            className="w-full p-3 border rounded-lg outline-none focus:ring-2 focus:ring-blue-500"
            onChange={(e) => setFormData({...formData, message: e.target.value})}
          ></textarea>
          <button className="w-full bg-blue-600 text-white font-bold py-3 rounded-lg hover:bg-blue-700 transition">
            Send Message
          </button>
        </form>
      </section>

      {/* Footer */}
      <footer className="py-10 text-center border-t border-gray-200">
        <div className="flex justify-center gap-6 mb-4">
          <Github className="cursor-pointer hover:text-blue-600" />
          <Mail className="cursor-pointer hover:text-blue-600" />
        </div>
        <p className="text-gray-500">Built with React & Tailwind</p>
      </footer>
    </div>
  );
};

export default Portfolio;
