# DllEntryPoint

- ea: `0x1800037a0`
- end: `0x1800037df`
- name: `DllEntryPoint`
- size: `63`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800037a0`
- `0x1800152f0`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  unsigned __int64 v3; // rax

  if ( fdwReason == 1 )
  {
    v3 = __rdtsc();
    LODWORD(v3) = v3 & 0x7FFFFFFF;
    qword_18001F390 = v3;
  }
  return ((__int64 (__fastcall *)(HINSTANCE, _QWORD, LPVOID))((unsigned int)dword_18001E0D8 + 0x180000000LL))(
           hinstDLL,
           fdwReason,
           lpReserved);
}

```

## disassembly

```asm
0x1800037a0  sub     rsp, 28h
0x1800037a4  mov     r10d, cs:dword_18001E0D8
0x1800037ab  mov     r9d, edx
0x1800037ae  cmp     edx, 1
0x1800037b1  jnz     short loc_1800037C7
0x1800037b3  rdtsc
0x1800037b5  shl     rdx, 20h
0x1800037b9  or      rax, rdx
0x1800037bc  btr     eax, 1Fh
0x1800037c0  mov     cs:qword_18001F390, rax
0x1800037c7  lea     rax, cs:180000000h
0x1800037ce  mov     edx, r9d
0x1800037d1  add     rax, r10
0x1800037d4  call    cs:__guard_dispatch_icall_fptr
0x1800037da  add     rsp, 28h
0x1800037de  retn
```
