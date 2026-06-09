# DllEntryPoint

- ea: `0x180041e50`
- end: `0x180041eac`
- name: `DllEntryPoint`
- size: `92`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180041e50`
- `0x180041ed0`
- `0x180041f48`
- `0x18006efc0`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  __int64 v3; // rbp
  int v7; // ebx

  v3 = (unsigned int)dword_18008C85C;
  if ( fdwReason == 1 && (int)sub_180041F48() < 0 )
  {
    sub_180041ED0();
    return 0;
  }
  else
  {
    v7 = ((__int64 (__fastcall *)(HINSTANCE, _QWORD, LPVOID))((char *)&_ImageBase + v3))(
           hinstDLL,
           fdwReason,
           lpReserved);
    if ( !fdwReason )
      sub_180041ED0();
  }
  return v7;
}

```

## disassembly

```asm
0x180041e50  push    rbx
0x180041e52  push    rbp
0x180041e53  push    rsi
0x180041e54  push    rdi
0x180041e55  sub     rsp, 28h
0x180041e59  mov     ebp, cs:dword_18008C85C
0x180041e5f  mov     rbx, r8
0x180041e62  mov     edi, edx
0x180041e64  mov     rsi, rcx
0x180041e67  cmp     edx, 1
0x180041e6a  jnz     short loc_180041E7E
0x180041e6c  call    sub_180041F48
0x180041e71  test    eax, eax
0x180041e73  jns     short loc_180041E7E
0x180041e75  call    sub_180041ED0
0x180041e7a  xor     ebx, ebx
0x180041e7c  jmp     short loc_180041EA1
0x180041e7e  lea     rax, __ImageBase
0x180041e85  mov     r8, rbx
0x180041e88  add     rax, rbp
0x180041e8b  mov     edx, edi
0x180041e8d  mov     rcx, rsi
0x180041e90  call    cs:__guard_dispatch_icall_fptr
0x180041e96  mov     ebx, eax
0x180041e98  test    edi, edi
0x180041e9a  jnz     short loc_180041EA1
0x180041e9c  call    sub_180041ED0
0x180041ea1  mov     eax, ebx
0x180041ea3  add     rsp, 28h
0x180041ea7  pop     rdi
0x180041ea8  pop     rsi
0x180041ea9  pop     rbp
0x180041eaa  pop     rbx
0x180041eab  retn
```
