# SoundWave-Open-
Um aplicativo de streaming de música 

/**
 * Configuração da conexão com MongoDB
 * Utiliza mongoose para modelagem e conexão
 */
const mongoose = require('mongoose');

const connectDB = async () => {
  try {
    // Conecta ao MongoDB usando a URI do .env
    const conn = await mongoose.connect(process.env.MONGODB_URI, {
      useNewUrlParser: true,
      useUnifiedTopology: true,
    });

    console.log(`✅ MongoDB conectado: ${conn.connection.host}`);
  } catch (error) {
    console.error(`❌ Erro na conexão: ${error.message}`);
    process.exit(1); // Encerra o processo em caso de falha
  }
};

module.exports = connectDB;
