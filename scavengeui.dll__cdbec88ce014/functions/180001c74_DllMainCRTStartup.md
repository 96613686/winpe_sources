# __DllMainCRTStartup

- ea: `0x180001c74`
- end: `0x180001e80`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001c30`

## callees

- `0x180001a00`
- `0x180001c74`
- `0x18000203e`
- `0x180002218`
- `0x180003be0`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_18000A34C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000A350 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_18000A350 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x180001c74  mov     [rsp+lpvReserved], r8
0x180001c79  mov     [rsp+arg_8], edx
0x180001c7d  mov     [rsp+arg_0], rcx
0x180001c82  push    rbx
0x180001c83  push    rsi
0x180001c84  push    rdi
0x180001c85  sub     rsp, 0F0h
0x180001c8c  mov     edi, edx
0x180001c8e  mov     rsi, rcx
0x180001c91  mov     ebx, 1
0x180001c96  cmp     edx, ebx
0x180001c98  ja      short loc_180001CA0
0x180001c9a  mov     cs:__native_dllmain_reason, edx
0x180001ca0  test    edx, edx
0x180001ca2  jnz     short loc_180001CB7
0x180001ca4  cmp     cs:dword_18000A34C, edx
0x180001caa  jnz     short loc_180001CB7
0x180001cac  xor     ebx, ebx
0x180001cae  mov     [rsp+108h+var_E8], ebx
0x180001cb2  jmp     loc_180001E64
0x180001cb7  lea     eax, [rdx-1]
0x180001cba  cmp     eax, 1
0x180001cbd  ja      loc_180001D44
0x180001cc3  mov     rax, cs:_pRawDllMain
0x180001cca  test    rax, rax
0x180001ccd  jz      short loc_180001D05
0x180001ccf  cmp     edx, 1
0x180001cd2  jnz     short loc_180001CDA
0x180001cd4  mov     cs:dword_18000A350, edx
0x180001cda  mov     r8, [rsp+108h+lpvReserved]
0x180001ce2  call    cs:__guard_dispatch_icall_fptr
0x180001ce8  mov     ebx, eax
0x180001cea  mov     [rsp+108h+var_E8], eax
0x180001cee  jmp     short loc_180001D05
0x180001cf0  xor     ebx, ebx
0x180001cf2  mov     [rsp+108h+var_E8], ebx
0x180001cf6  mov     edi, [rsp+108h+arg_8]
0x180001cfd  mov     rsi, [rsp+108h+arg_0]
0x180001d05  test    ebx, ebx
0x180001d07  jz      loc_180001E64
0x180001d0d  mov     r8, [rsp+108h+lpvReserved]
0x180001d15  mov     edx, edi
0x180001d17  mov     rcx, rsi
0x180001d1a  call    _CRT_INIT
0x180001d1f  mov     ebx, eax
0x180001d21  mov     [rsp+108h+var_E8], eax
0x180001d25  jmp     short loc_180001D3C
0x180001d27  xor     ebx, ebx
0x180001d29  mov     [rsp+108h+var_E8], ebx
0x180001d2d  mov     edi, [rsp+108h+arg_8]
0x180001d34  mov     rsi, [rsp+108h+arg_0]
0x180001d3c  test    ebx, ebx
0x180001d3e  jz      loc_180001E64
0x180001d44  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001d4c  mov     edx, edi; fdwReason
0x180001d4e  mov     rcx, rsi; hinstDLL
0x180001d51  call    DllMain
0x180001d56  mov     ebx, eax
0x180001d58  mov     [rsp+108h+var_E8], eax
0x180001d5c  jmp     short loc_180001D73
0x180001d5e  xor     ebx, ebx
0x180001d60  mov     [rsp+108h+var_E8], ebx
0x180001d64  mov     edi, [rsp+108h+arg_8]
0x180001d6b  mov     rsi, [rsp+108h+arg_0]
0x180001d73  cmp     edi, 1
0x180001d76  jnz     short loc_180001DEF
0x180001d78  test    ebx, ebx
0x180001d7a  jnz     short loc_180001DEF
0x180001d7c  xor     r8d, r8d; lpvReserved
0x180001d7f  xor     edx, edx; fdwReason
0x180001d81  mov     rcx, rsi; hinstDLL
0x180001d84  call    DllMain
0x180001d89  jmp     short loc_180001D9E
0x180001d8b  mov     edi, [rsp+108h+arg_8]
0x180001d92  mov     rsi, [rsp+108h+arg_0]
0x180001d9a  mov     ebx, [rsp+108h+var_E8]
0x180001d9e  xor     r8d, r8d
0x180001da1  xor     edx, edx
0x180001da3  mov     rcx, rsi
0x180001da6  call    _CRT_INIT
0x180001dab  jmp     short loc_180001DC0
0x180001dad  mov     edi, [rsp+108h+arg_8]
0x180001db4  mov     rsi, [rsp+108h+arg_0]
0x180001dbc  mov     ebx, [rsp+108h+var_E8]
0x180001dc0  mov     rax, cs:_pRawDllMain
0x180001dc7  test    rax, rax
0x180001dca  jz      short loc_180001DEF
0x180001dcc  xor     r8d, r8d
0x180001dcf  xor     edx, edx
0x180001dd1  mov     rcx, rsi
0x180001dd4  call    cs:__guard_dispatch_icall_fptr
0x180001dda  jmp     short loc_180001DEF
0x180001ddc  mov     edi, [rsp+108h+arg_8]
0x180001de3  mov     rsi, [rsp+108h+arg_0]
0x180001deb  mov     ebx, [rsp+108h+var_E8]
0x180001def  test    edi, edi
0x180001df1  jz      short loc_180001DF8
0x180001df3  cmp     edi, 3
0x180001df6  jnz     short loc_180001E64
0x180001df8  mov     r8, [rsp+108h+lpvReserved]
0x180001e00  mov     edx, edi
0x180001e02  mov     rcx, rsi
0x180001e05  call    _CRT_INIT
0x180001e0a  mov     ebx, eax
0x180001e0c  mov     [rsp+108h+var_E8], eax
0x180001e10  jmp     short loc_180001E27
0x180001e12  xor     ebx, ebx
0x180001e14  mov     [rsp+108h+var_E8], ebx
0x180001e18  mov     edi, [rsp+108h+arg_8]
0x180001e1f  mov     rsi, [rsp+108h+arg_0]
0x180001e27  mov     rax, cs:_pRawDllMain
0x180001e2e  test    rax, rax
0x180001e31  jz      short loc_180001E64
0x180001e33  cmp     cs:dword_18000A350, 0
0x180001e3a  jz      short loc_180001E64
0x180001e3c  mov     r8, [rsp+108h+lpvReserved]
0x180001e44  mov     edx, edi
0x180001e46  mov     rcx, rsi
0x180001e49  call    cs:__guard_dispatch_icall_fptr
0x180001e4f  mov     ebx, eax
0x180001e51  mov     [rsp+108h+var_E8], eax
0x180001e55  jmp     short loc_180001E64
0x180001e57  xor     ebx, ebx
0x180001e59  mov     [rsp+108h+var_E8], ebx
0x180001e5d  mov     edi, [rsp+108h+arg_8]
0x180001e64  cmp     edi, 1
0x180001e67  ja      short loc_180001E73
0x180001e69  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001e73  mov     eax, ebx
0x180001e75  add     rsp, 0F0h
0x180001e7c  pop     rdi
0x180001e7d  pop     rsi
0x180001e7e  pop     rbx
0x180001e7f  retn
0x180003c8f  push    rbp
0x180003c91  sub     rsp, 20h
0x180003c95  mov     rbp, rdx
0x180003c98  mov     rax, [rcx]
0x180003c9b  mov     edx, [rax]
0x180003c9d  mov     [rbp+0A8h], rcx
0x180003ca4  mov     [rbp+28h], edx
0x180003ca7  mov     eax, [rbp+28h]
0x180003caa  cmp     eax, 0E06D7363h
0x180003caf  jnz     short loc_180003CC5
0x180003cb1  mov     rdx, [rbp+0A8h]
0x180003cb8  mov     ecx, [rbp+28h]
0x180003cbb  call    _XcptFilter_0
0x180003cc0  mov     [rbp+30h], eax
0x180003cc3  jmp     short loc_180003CCC
0x180003cc5  mov     dword ptr [rbp+30h], 0
0x180003ccc  mov     eax, [rbp+30h]
0x180003ccf  add     rsp, 20h
0x180003cd3  pop     rbp
0x180003cd4  retn
0x180003cd6  push    rbp
0x180003cd8  sub     rsp, 20h
0x180003cdc  mov     rbp, rdx
0x180003cdf  mov     rax, [rcx]
0x180003ce2  mov     edx, [rax]
0x180003ce4  mov     [rbp+0B0h], rcx
0x180003ceb  mov     [rbp+38h], edx
0x180003cee  mov     eax, [rbp+38h]
0x180003cf1  cmp     eax, 0E06D7363h
0x180003cf6  jnz     short loc_180003D0C
0x180003cf8  mov     rdx, [rbp+0B0h]
0x180003cff  mov     ecx, [rbp+38h]
0x180003d02  call    _XcptFilter_0
0x180003d07  mov     [rbp+40h], eax
0x180003d0a  jmp     short loc_180003D13
0x180003d0c  mov     dword ptr [rbp+40h], 0
0x180003d13  mov     eax, [rbp+40h]
0x180003d16  add     rsp, 20h
0x180003d1a  pop     rbp
0x180003d1b  retn
0x180003d1d  push    rbp
0x180003d1f  sub     rsp, 20h
0x180003d23  mov     rbp, rdx
0x180003d26  mov     rax, [rcx]
0x180003d29  mov     edx, [rax]
0x180003d2b  mov     [rbp+0B8h], rcx
0x180003d32  mov     [rbp+48h], edx
0x180003d35  mov     eax, [rbp+48h]
0x180003d38  cmp     eax, 0E06D7363h
0x180003d3d  jnz     short loc_180003D53
0x180003d3f  mov     rdx, [rbp+0B8h]
0x180003d46  mov     ecx, [rbp+48h]
0x180003d49  call    _XcptFilter_0
0x180003d4e  mov     [rbp+50h], eax
0x180003d51  jmp     short loc_180003D5A
0x180003d53  mov     dword ptr [rbp+50h], 0
0x180003d5a  mov     eax, [rbp+50h]
0x180003d5d  add     rsp, 20h
0x180003d61  pop     rbp
0x180003d62  retn
0x180003d64  push    rbp
0x180003d66  sub     rsp, 20h
0x180003d6a  mov     rbp, rdx
0x180003d6d  mov     rax, [rcx]
0x180003d70  mov     edx, [rax]
0x180003d72  mov     [rbp+0C0h], rcx
0x180003d79  mov     [rbp+58h], edx
0x180003d7c  mov     eax, [rbp+58h]
0x180003d7f  cmp     eax, 0E06D7363h
0x180003d84  jnz     short loc_180003D9A
0x180003d86  mov     rdx, [rbp+0C0h]
0x180003d8d  mov     ecx, [rbp+58h]
0x180003d90  call    _XcptFilter_0
0x180003d95  mov     [rbp+60h], eax
0x180003d98  jmp     short loc_180003DA1
0x180003d9a  mov     dword ptr [rbp+60h], 0
0x180003da1  mov     eax, [rbp+60h]
0x180003da4  add     rsp, 20h
0x180003da8  pop     rbp
0x180003da9  retn
0x180003dab  push    rbp
0x180003dad  sub     rsp, 20h
0x180003db1  mov     rbp, rdx
0x180003db4  mov     rax, [rcx]
0x180003db7  mov     edx, [rax]
0x180003db9  mov     [rbp+0C8h], rcx
0x180003dc0  mov     [rbp+68h], edx
0x180003dc3  mov     eax, [rbp+68h]
0x180003dc6  cmp     eax, 0E06D7363h
0x180003dcb  jnz     short loc_180003DE1
0x180003dcd  mov     rdx, [rbp+0C8h]
0x180003dd4  mov     ecx, [rbp+68h]
0x180003dd7  call    _XcptFilter_0
0x180003ddc  mov     [rbp+70h], eax
0x180003ddf  jmp     short loc_180003DE8
0x180003de1  mov     dword ptr [rbp+70h], 0
0x180003de8  mov     eax, [rbp+70h]
0x180003deb  add     rsp, 20h
0x180003def  pop     rbp
0x180003df0  retn
0x180003df2  push    rbp
0x180003df4  sub     rsp, 20h
0x180003df8  mov     rbp, rdx
0x180003dfb  mov     rax, [rcx]
0x180003dfe  mov     edx, [rax]
0x180003e00  mov     [rbp+0D0h], rcx
0x180003e07  mov     [rbp+78h], edx
0x180003e0a  mov     eax, [rbp+78h]
0x180003e0d  cmp     eax, 0E06D7363h
0x180003e12  jnz     short loc_180003E2B
0x180003e14  mov     rdx, [rbp+0D0h]
0x180003e1b  mov     ecx, [rbp+78h]
0x180003e1e  call    _XcptFilter_0
0x180003e23  mov     [rbp+80h], eax
0x180003e29  jmp     short loc_180003E35
0x180003e2b  mov     dword ptr [rbp+80h], 0
0x180003e35  mov     eax, [rbp+80h]
0x180003e3b  add     rsp, 20h
0x180003e3f  pop     rbp
0x180003e40  retn
0x180003e42  push    rbp
0x180003e44  sub     rsp, 20h
0x180003e48  mov     rbp, rdx
0x180003e4b  mov     rax, [rcx]
0x180003e4e  mov     edx, [rax]
0x180003e50  mov     [rbp+0D8h], rcx
0x180003e57  mov     [rbp+88h], edx
0x180003e5d  mov     eax, [rbp+88h]
0x180003e63  cmp     eax, 0E06D7363h
0x180003e68  jnz     short loc_180003E84
0x180003e6a  mov     rdx, [rbp+0D8h]
0x180003e71  mov     ecx, [rbp+88h]
0x180003e77  call    _XcptFilter_0
0x180003e7c  mov     [rbp+90h], eax
0x180003e82  jmp     short loc_180003E8E
0x180003e84  mov     dword ptr [rbp+90h], 0
0x180003e8e  mov     eax, [rbp+90h]
0x180003e94  add     rsp, 20h
0x180003e98  pop     rbp
0x180003e99  retn
0x180003e9b  push    rbp
0x180003e9d  sub     rsp, 20h
0x180003ea1  mov     rbp, rdx
0x180003ea4  mov     rax, [rcx]
0x180003ea7  mov     edx, [rax]
0x180003ea9  mov     [rbp+0E0h], rcx
0x180003eb0  mov     [rbp+98h], edx
0x180003eb6  mov     eax, [rbp+98h]
0x180003ebc  cmp     eax, 0E06D7363h
0x180003ec1  jnz     short loc_180003EDD
0x180003ec3  mov     rdx, [rbp+0E0h]
0x180003eca  mov     ecx, [rbp+98h]
0x180003ed0  call    _XcptFilter_0
0x180003ed5  mov     [rbp+0A0h], eax
0x180003edb  jmp     short loc_180003EE7
0x180003edd  mov     dword ptr [rbp+0A0h], 0
0x180003ee7  mov     eax, [rbp+0A0h]
0x180003eed  add     rsp, 20h
0x180003ef1  pop     rbp
0x180003ef2  retn
0x180003ef4  push    rbp
0x180003ef6  sub     rsp, 20h
0x180003efa  mov     rbp, rdx
0x180003efd  cmp     dword ptr [rbp+118h], 1
0x180003f04  ja      short loc_180003F10
0x180003f06  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
