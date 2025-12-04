# Multi Stage Docker Build

The main purpose of choosing a golang based applciation to demostrate this example is golang is a statically-typed programming language that does not require a runtime in the traditional sense. Unlike dynamically-typed languages like Python, Ruby, and JavaScript, which rely on a runtime environment to execute their code, Go compiles directly to machine code, which can then be executed directly by the operating system.

So the real advantage of multi stage docker build and distro less images can be understand with a drastic decrease in the Image size.
<img width="1358" height="214" alt="Screenshot 2025-12-04 104902" src="https://github.com/user-attachments/assets/9053a29a-2ada-4e96-864e-ed46f565c4bd" />

First, I built a simple Go app image using a single-stage Dockerfile (~380MB). Then I created a multi-stage Dockerfile where Go compiles the binary in the builder stage and the final stage uses a Distroless image. This reduced the image size from ~388MB to ~9MB while improving security.
<img width="1120" height="96" alt="Screenshot 2025-12-04 104747" src="https://github.com/user-attachments/assets/9e40b2fe-74da-4339-bda3-85ad6941a416" />
