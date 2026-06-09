# __DllMainCRTStartup

- ea: `0x180001ed4`
- end: `0x180001fd5`
- name: `__DllMainCRTStartup`
- size: `257`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001e90`

## callees

- `0x180001dac`
- `0x180001ed4`
- `0x180002104`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  if ( (_DWORD)fdwReason || dword_18000A0A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 || (v5 = CRT_INIT(hinstDLL, fdwReason, a3)) != 0 )
    {
      v5 = DllMain(hinstDLL, v3, a3);
      if ( v3 == 1 && !v5 )
      {
        DllMain(hinstDLL, 0, 0);
        CRT_INIT(hinstDLL, 0, 0);
      }
      if ( !v3 || v3 == 3 )
        return (unsigned int)CRT_INIT(hinstDLL, v3, a3);
    }
  }
  else
  {
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180001ed4  mov     rax, rsp
0x180001ed7  mov     [rax+18h], r8
0x180001edb  mov     [rax+10h], edx
0x180001ede  mov     [rax+8], rcx
0x180001ee2  push    rbx
0x180001ee3  push    rsi
0x180001ee4  push    rdi
0x180001ee5  sub     rsp, 50h
0x180001ee9  mov     edi, edx
0x180001eeb  mov     rsi, rcx
0x180001eee  test    edx, edx
0x180001ef0  jnz     short loc_180001F04
0x180001ef2  cmp     cs:dword_18000A0A0, edx
0x180001ef8  jnz     short loc_180001F04
0x180001efa  xor     ebx, ebx
0x180001efc  mov     [rax-48h], ebx
0x180001eff  jmp     loc_180001FCB
0x180001f04  lea     eax, [rdx-1]
0x180001f07  cmp     eax, 1
0x180001f0a  ja      short loc_180001F38
0x180001f0c  mov     r8, [rsp+68h+lpvReserved]
0x180001f14  call    _CRT_INIT
0x180001f19  mov     ebx, eax
0x180001f1b  mov     [rsp+68h+var_48], eax
0x180001f1f  jmp     short loc_180001F30
0x180001f21  xor     ebx, ebx
0x180001f23  mov     [rsp+68h+var_48], ebx
0x180001f27  mov     edi, [rsp+68h+arg_8]
0x180001f2b  mov     rsi, [rsp+68h+arg_0]
0x180001f30  test    ebx, ebx
0x180001f32  jz      loc_180001FCB
0x180001f38  mov     r8, [rsp+68h+lpvReserved]; lpvReserved
0x180001f40  mov     edx, edi; fdwReason
0x180001f42  mov     rcx, rsi; hinstDLL
0x180001f45  call    DllMain
0x180001f4a  mov     ebx, eax
0x180001f4c  mov     [rsp+68h+var_48], eax
0x180001f50  jmp     short loc_180001F61
0x180001f52  xor     ebx, ebx
0x180001f54  mov     [rsp+68h+var_48], ebx
0x180001f58  mov     edi, [rsp+68h+arg_8]
0x180001f5c  mov     rsi, [rsp+68h+arg_0]
0x180001f61  cmp     edi, 1
0x180001f64  jnz     short loc_180001FA2
0x180001f66  test    ebx, ebx
0x180001f68  jnz     short loc_180001FA2
0x180001f6a  xor     r8d, r8d; lpvReserved
0x180001f6d  xor     edx, edx; fdwReason
0x180001f6f  mov     rcx, rsi; hinstDLL
0x180001f72  call    DllMain
0x180001f77  jmp     short loc_180001F86
0x180001f79  mov     edi, [rsp+68h+arg_8]
0x180001f7d  mov     rsi, [rsp+68h+arg_0]
0x180001f82  mov     ebx, [rsp+68h+var_48]
0x180001f86  xor     r8d, r8d
0x180001f89  xor     edx, edx
0x180001f8b  mov     rcx, rsi
0x180001f8e  call    _CRT_INIT
0x180001f93  jmp     short loc_180001FA2
0x180001f95  mov     edi, [rsp+68h+arg_8]
0x180001f99  mov     rsi, [rsp+68h+arg_0]
0x180001f9e  mov     ebx, [rsp+68h+var_48]
0x180001fa2  test    edi, edi
0x180001fa4  jz      short loc_180001FAB
0x180001fa6  cmp     edi, 3
0x180001fa9  jnz     short loc_180001FCB
0x180001fab  mov     r8, [rsp+68h+lpvReserved]
0x180001fb3  mov     edx, edi
0x180001fb5  mov     rcx, rsi
0x180001fb8  call    _CRT_INIT
0x180001fbd  mov     ebx, eax
0x180001fbf  mov     [rsp+68h+var_48], eax
0x180001fc3  jmp     short loc_180001FCB
0x180001fc5  xor     ebx, ebx
0x180001fc7  mov     [rsp+68h+var_48], ebx
0x180001fcb  mov     eax, ebx
0x180001fcd  add     rsp, 50h
0x180001fd1  pop     rdi
0x180001fd2  pop     rsi
0x180001fd3  pop     rbx
0x180001fd4  retn
0x18000349c  push    rbp
0x18000349e  sub     rsp, 20h
0x1800034a2  mov     rbp, rdx
0x1800034a5  xor     eax, eax
0x1800034a7  add     rsp, 20h
0x1800034ab  pop     rbp
0x1800034ac  retn
0x1800034ae  push    rbp
0x1800034b0  sub     rsp, 20h
0x1800034b4  mov     rbp, rdx
0x1800034b7  xor     eax, eax
0x1800034b9  add     rsp, 20h
0x1800034bd  pop     rbp
0x1800034be  retn
0x1800034c0  push    rbp
0x1800034c2  sub     rsp, 20h
0x1800034c6  mov     rbp, rdx
0x1800034c9  xor     eax, eax
0x1800034cb  add     rsp, 20h
0x1800034cf  pop     rbp
0x1800034d0  retn
0x1800034d2  push    rbp
0x1800034d4  sub     rsp, 20h
0x1800034d8  mov     rbp, rdx
0x1800034db  xor     eax, eax
0x1800034dd  add     rsp, 20h
0x1800034e1  pop     rbp
0x1800034e2  retn
0x1800034e4  push    rbp
0x1800034e6  sub     rsp, 20h
0x1800034ea  mov     rbp, rdx
0x1800034ed  xor     eax, eax
0x1800034ef  add     rsp, 20h
0x1800034f3  pop     rbp
0x1800034f4  retn
0x1800034f6  push    rbp
0x1800034f8  sub     rsp, 20h
0x1800034fc  mov     rbp, rdx
0x1800034ff  add     rsp, 20h
0x180003503  pop     rbp
0x180003504  retn
```
