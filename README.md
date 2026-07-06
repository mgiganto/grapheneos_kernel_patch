### KernelSU Integration

If you require `KernelSU` integration, you must compile a custom kernel independently and replace the GrapheneOS prebuilt kernel with your own.

#### Step 1.1: Verify Custom Kernel Build
Before applying any patches, ensure you can successfully build and boot a clean custom kernel:
1. Clone the GrapheneOS kernel source to `<kernel_src>`.
2. Compile the kernel according to [official GrapheneOS documentation](https://grapheneos.org/build#kernel-compilation).
3. Replace the prebuilt kernel in `<grapheneos_src>` with your newly compiled kernel.
4. Perform a full GrapheneOS build and verify that the device boots correctly.

#### Step 1.2: Patch the Kernel
Once you have verified your custom kernel build, apply the `KernelSU` patches.

Get the kernel patch:
```bash
git clone https://github.com/mgiganto/grapheneos_kernel_patch
cd grapheneos_kernel_patch
git checkout rooted
```
Apply the relevant patch to your <kernel_src>:
```Bash

# Standard patch
git -C <kernel_src> am grapheneos_kernel.patch

# OR Muzel version
git -C <kernel_src> am grapheneos_kernel_muzel.patch
```

#### Step 2.3: Final Build
1. Recompile your patched kernel in <kernel_src>.
2. Replace the kernel prebuilts in <grapheneos_src> with the patched version.
3. Perform the final GrapheneOS system build.

