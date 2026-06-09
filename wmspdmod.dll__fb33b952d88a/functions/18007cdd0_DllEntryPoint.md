# DllEntryPoint

- ea: `0x18007cdd0`
- end: `0x18007ce2d`
- name: `DllEntryPoint`
- size: `93`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18007cdd0`
- `0x18007cf60`
- `0x18007cfa0`
- `0x1800c60f0`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  __int64 v3; // rbp
  int v7; // ebx

  v3 = (unsigned int)dword_18010F3A0;
  if ( fdwReason == 1 && (int)sub_18007CFA0() < 0 )
  {
    sub_18007CF60();
    return 0;
  }
  else
  {
    v7 = ((__int64 (__fastcall *)(HINSTANCE, _QWORD, LPVOID))(v3 + 0x180000000LL))(hinstDLL, fdwReason, lpReserved);
    if ( !fdwReason )
      sub_18007CF60();
  }
  return v7;
}

```

## disassembly

```asm
0x18007cdd0  push    rbx
0x18007cdd2  push    rbp
0x18007cdd3  push    rsi
0x18007cdd4  push    rdi
0x18007cdd5  sub     rsp, 28h
0x18007cdd9  mov     ebp, cs:dword_18010F3A0
0x18007cddf  mov     rbx, r8
0x18007cde2  mov     edi, edx
0x18007cde4  mov     rsi, rcx
0x18007cde7  cmp     edx, 1
0x18007cdea  jnz     short loc_18007CDFE
0x18007cdec  call    sub_18007CFA0
0x18007cdf1  test    eax, eax
0x18007cdf3  jns     short loc_18007CDFE
0x18007cdf5  call    sub_18007CF60
0x18007cdfa  xor     ebx, ebx
0x18007cdfc  jmp     short loc_18007CE21
0x18007cdfe  lea     rax, cs:180000000h
0x18007ce05  mov     r8, rbx
0x18007ce08  add     rax, rbp
0x18007ce0b  mov     edx, edi
0x18007ce0d  mov     rcx, rsi
0x18007ce10  call    cs:__guard_dispatch_icall_fptr
0x18007ce16  mov     ebx, eax
0x18007ce18  test    edi, edi
0x18007ce1a  jnz     short loc_18007CE21
0x18007ce1c  call    sub_18007CF60
0x18007ce21  mov     eax, ebx
0x18007ce23  add     rsp, 28h
0x18007ce27  pop     rdi
0x18007ce28  pop     rsi
0x18007ce29  pop     rbp
0x18007ce2a  pop     rbx
0x18007ce2b  retn
```
