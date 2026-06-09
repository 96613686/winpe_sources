# CIlKernel32::OpenProcess(ulong,int,ulong)

- ea: `0x18000ee30`
- end: `0x18000ee41`
- name: `?OpenProcess@CIlKernel32@@UEAAPEAXKHK@Z`
- size: `17`
- prototype: `void *__fastcall(CIlKernel32 *__hidden this, unsigned int, int, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000ee3a`

## pseudocode

```c
HANDLE __fastcall CIlKernel32::OpenProcess(CIlKernel32 *this, DWORD a2, BOOL a3, DWORD a4)
{
  return OpenProcess(a2, a3, a4);
}

```

## disassembly

```asm
0x18000ee30  mov     eax, r8d
0x18000ee33  mov     ecx, edx
0x18000ee35  mov     edx, eax
0x18000ee37  mov     r8d, r9d
0x18000ee3a  jmp     cs:__imp_OpenProcess
```
