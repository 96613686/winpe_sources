# CIlKernel32::OpenEventW(ulong,int,ushort const *)

- ea: `0x18000ee10`
- end: `0x18000ee21`
- name: `?OpenEventW@CIlKernel32@@UEAAPEAXKHPEBG@Z`
- size: `17`
- prototype: `void *__fastcall(CIlKernel32 *__hidden this, unsigned int, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000ee1a`

## pseudocode

```c
HANDLE __fastcall CIlKernel32::OpenEventW(CIlKernel32 *this, DWORD a2, BOOL a3, const unsigned __int16 *a4)
{
  return OpenEventW(a2, a3, a4);
}

```

## disassembly

```asm
0x18000ee10  mov     eax, r8d
0x18000ee13  mov     ecx, edx
0x18000ee15  mov     edx, eax
0x18000ee17  mov     r8, r9
0x18000ee1a  jmp     cs:__imp_OpenEventW
```
