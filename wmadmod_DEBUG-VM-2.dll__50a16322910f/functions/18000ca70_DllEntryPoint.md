# DllEntryPoint

- ea: `0x18000ca70`
- end: `0x18000cacf`
- name: `DllEntryPoint`
- size: `95`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000ca70`
- `0x18002ec40`
- `0x18002ec80`
- `0x180093330`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  __int64 v3; // rbp
  int v7; // ebx

  v3 = (unsigned int)dword_1800E0E3C;
  if ( fdwReason == 1 && (int)sub_18002EC80() < 0 )
  {
    sub_18002EC40();
    return 0;
  }
  else
  {
    v7 = ((__int64 (__fastcall *)(HINSTANCE, _QWORD, LPVOID))((char *)&_ImageBase + v3))(
           hinstDLL,
           fdwReason,
           lpReserved);
    if ( !fdwReason )
      sub_18002EC40();
  }
  return v7;
}

```

## disassembly

```asm
0x18000ca70  push    rbx
0x18000ca72  push    rbp
0x18000ca73  push    rsi
0x18000ca74  push    rdi
0x18000ca75  sub     rsp, 28h
0x18000ca79  mov     ebp, cs:dword_1800E0E3C
0x18000ca7f  mov     rbx, r8
0x18000ca82  mov     edi, edx
0x18000ca84  mov     rsi, rcx
0x18000ca87  cmp     edx, 1
0x18000ca8a  jz      short loc_18000CAB6
0x18000ca8c  lea     rax, __ImageBase
0x18000ca93  mov     r8, rbx
0x18000ca96  add     rax, rbp
0x18000ca99  mov     edx, edi
0x18000ca9b  mov     rcx, rsi
0x18000ca9e  call    cs:__guard_dispatch_icall_fptr
0x18000caa4  mov     ebx, eax
0x18000caa6  test    edi, edi
0x18000caa8  jz      short loc_18000CAC8
0x18000caaa  mov     eax, ebx
0x18000caac  add     rsp, 28h
0x18000cab0  pop     rdi
0x18000cab1  pop     rsi
0x18000cab2  pop     rbp
0x18000cab3  pop     rbx
0x18000cab4  retn
0x18000cab6  call    sub_18002EC80
0x18000cabb  test    eax, eax
0x18000cabd  jns     short loc_18000CA8C
0x18000cabf  call    sub_18002EC40
0x18000cac4  xor     ebx, ebx
0x18000cac6  jmp     short loc_18000CAAA
0x18000cac8  call    sub_18002EC40
0x18000cacd  jmp     short loc_18000CAAA
```
