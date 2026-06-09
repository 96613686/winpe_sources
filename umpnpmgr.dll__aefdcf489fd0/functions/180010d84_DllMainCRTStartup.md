# __DllMainCRTStartup

- ea: `0x180010d84`
- end: `0x180010f90`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180010d40`

## callees

- `0x180010b10`
- `0x180010d84`
- `0x1800112c4`
- `0x180011614`
- `0x1800189b0`

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
  if ( (_DWORD)fdwReason || dword_180023180 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180023184 = 1;
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
            if ( dword_180023184 )
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
0x180010d84  mov     [rsp+lpvReserved], r8
0x180010d89  mov     [rsp+arg_8], edx
0x180010d8d  mov     [rsp+arg_0], rcx
0x180010d92  push    rbx
0x180010d93  push    rsi
0x180010d94  push    rdi
0x180010d95  sub     rsp, 0F0h
0x180010d9c  mov     edi, edx
0x180010d9e  mov     rsi, rcx
0x180010da1  mov     ebx, 1
0x180010da6  cmp     edx, ebx
0x180010da8  ja      short loc_180010DB0
0x180010daa  mov     cs:__native_dllmain_reason, edx
0x180010db0  test    edx, edx
0x180010db2  jnz     short loc_180010DC7
0x180010db4  cmp     cs:dword_180023180, edx
0x180010dba  jnz     short loc_180010DC7
0x180010dbc  xor     ebx, ebx
0x180010dbe  mov     [rsp+108h+var_E8], ebx
0x180010dc2  jmp     loc_180010F74
0x180010dc7  lea     eax, [rdx-1]
0x180010dca  cmp     eax, 1
0x180010dcd  ja      loc_180010E54
0x180010dd3  mov     rax, cs:_pRawDllMain
0x180010dda  test    rax, rax
0x180010ddd  jz      short loc_180010E15
0x180010ddf  cmp     edx, 1
0x180010de2  jnz     short loc_180010DEA
0x180010de4  mov     cs:dword_180023184, edx
0x180010dea  mov     r8, [rsp+108h+lpvReserved]
0x180010df2  call    cs:__guard_dispatch_icall_fptr
0x180010df8  mov     ebx, eax
0x180010dfa  mov     [rsp+108h+var_E8], eax
0x180010dfe  jmp     short loc_180010E15
0x180010e00  xor     ebx, ebx
0x180010e02  mov     [rsp+108h+var_E8], ebx
0x180010e06  mov     edi, [rsp+108h+arg_8]
0x180010e0d  mov     rsi, [rsp+108h+arg_0]
0x180010e15  test    ebx, ebx
0x180010e17  jz      loc_180010F74
0x180010e1d  mov     r8, [rsp+108h+lpvReserved]
0x180010e25  mov     edx, edi
0x180010e27  mov     rcx, rsi
0x180010e2a  call    _CRT_INIT
0x180010e2f  mov     ebx, eax
0x180010e31  mov     [rsp+108h+var_E8], eax
0x180010e35  jmp     short loc_180010E4C
0x180010e37  xor     ebx, ebx
0x180010e39  mov     [rsp+108h+var_E8], ebx
0x180010e3d  mov     edi, [rsp+108h+arg_8]
0x180010e44  mov     rsi, [rsp+108h+arg_0]
0x180010e4c  test    ebx, ebx
0x180010e4e  jz      loc_180010F74
0x180010e54  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180010e5c  mov     edx, edi; fdwReason
0x180010e5e  mov     rcx, rsi; hinstDLL
0x180010e61  call    DllMain
0x180010e66  mov     ebx, eax
0x180010e68  mov     [rsp+108h+var_E8], eax
0x180010e6c  jmp     short loc_180010E83
0x180010e6e  xor     ebx, ebx
0x180010e70  mov     [rsp+108h+var_E8], ebx
0x180010e74  mov     edi, [rsp+108h+arg_8]
0x180010e7b  mov     rsi, [rsp+108h+arg_0]
0x180010e83  cmp     edi, 1
0x180010e86  jnz     short loc_180010EFF
0x180010e88  test    ebx, ebx
0x180010e8a  jnz     short loc_180010EFF
0x180010e8c  xor     r8d, r8d; lpvReserved
0x180010e8f  xor     edx, edx; fdwReason
0x180010e91  mov     rcx, rsi; hinstDLL
0x180010e94  call    DllMain
0x180010e99  jmp     short loc_180010EAE
0x180010e9b  mov     edi, [rsp+108h+arg_8]
0x180010ea2  mov     rsi, [rsp+108h+arg_0]
0x180010eaa  mov     ebx, [rsp+108h+var_E8]
0x180010eae  xor     r8d, r8d
0x180010eb1  xor     edx, edx
0x180010eb3  mov     rcx, rsi
0x180010eb6  call    _CRT_INIT
0x180010ebb  jmp     short loc_180010ED0
0x180010ebd  mov     edi, [rsp+108h+arg_8]
0x180010ec4  mov     rsi, [rsp+108h+arg_0]
0x180010ecc  mov     ebx, [rsp+108h+var_E8]
0x180010ed0  mov     rax, cs:_pRawDllMain
0x180010ed7  test    rax, rax
0x180010eda  jz      short loc_180010EFF
0x180010edc  xor     r8d, r8d
0x180010edf  xor     edx, edx
0x180010ee1  mov     rcx, rsi
0x180010ee4  call    cs:__guard_dispatch_icall_fptr
0x180010eea  jmp     short loc_180010EFF
0x180010eec  mov     edi, [rsp+108h+arg_8]
0x180010ef3  mov     rsi, [rsp+108h+arg_0]
0x180010efb  mov     ebx, [rsp+108h+var_E8]
0x180010eff  test    edi, edi
0x180010f01  jz      short loc_180010F08
0x180010f03  cmp     edi, 3
0x180010f06  jnz     short loc_180010F74
0x180010f08  mov     r8, [rsp+108h+lpvReserved]
0x180010f10  mov     edx, edi
0x180010f12  mov     rcx, rsi
0x180010f15  call    _CRT_INIT
0x180010f1a  mov     ebx, eax
0x180010f1c  mov     [rsp+108h+var_E8], eax
0x180010f20  jmp     short loc_180010F37
0x180010f22  xor     ebx, ebx
0x180010f24  mov     [rsp+108h+var_E8], ebx
0x180010f28  mov     edi, [rsp+108h+arg_8]
0x180010f2f  mov     rsi, [rsp+108h+arg_0]
0x180010f37  mov     rax, cs:_pRawDllMain
0x180010f3e  test    rax, rax
0x180010f41  jz      short loc_180010F74
0x180010f43  cmp     cs:dword_180023184, 0
0x180010f4a  jz      short loc_180010F74
0x180010f4c  mov     r8, [rsp+108h+lpvReserved]
0x180010f54  mov     edx, edi
0x180010f56  mov     rcx, rsi
0x180010f59  call    cs:__guard_dispatch_icall_fptr
0x180010f5f  mov     ebx, eax
0x180010f61  mov     [rsp+108h+var_E8], eax
0x180010f65  jmp     short loc_180010F74
0x180010f67  xor     ebx, ebx
0x180010f69  mov     [rsp+108h+var_E8], ebx
0x180010f6d  mov     edi, [rsp+108h+arg_8]
0x180010f74  cmp     edi, 1
0x180010f77  ja      short loc_180010F83
0x180010f79  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180010f83  mov     eax, ebx
0x180010f85  add     rsp, 0F0h
0x180010f8c  pop     rdi
0x180010f8d  pop     rsi
0x180010f8e  pop     rbx
0x180010f8f  retn
0x180018ec6  push    rbp
0x180018ec8  sub     rsp, 20h
0x180018ecc  mov     rbp, rdx
0x180018ecf  mov     rax, [rcx]
0x180018ed2  mov     edx, [rax]
0x180018ed4  mov     [rbp+0A8h], rcx
0x180018edb  mov     [rbp+28h], edx
0x180018ede  mov     eax, [rbp+28h]
0x180018ee1  cmp     eax, 0E06D7363h
0x180018ee6  jnz     short loc_180018EFC
0x180018ee8  mov     rdx, [rbp+0A8h]
0x180018eef  mov     ecx, [rbp+28h]
0x180018ef2  call    _XcptFilter_0
0x180018ef7  mov     [rbp+30h], eax
0x180018efa  jmp     short loc_180018F03
0x180018efc  mov     dword ptr [rbp+30h], 0
0x180018f03  mov     eax, [rbp+30h]
0x180018f06  add     rsp, 20h
0x180018f0a  pop     rbp
0x180018f0b  retn
0x180018f0d  push    rbp
0x180018f0f  sub     rsp, 20h
0x180018f13  mov     rbp, rdx
0x180018f16  mov     rax, [rcx]
0x180018f19  mov     edx, [rax]
0x180018f1b  mov     [rbp+0B0h], rcx
0x180018f22  mov     [rbp+38h], edx
0x180018f25  mov     eax, [rbp+38h]
0x180018f28  cmp     eax, 0E06D7363h
0x180018f2d  jnz     short loc_180018F43
0x180018f2f  mov     rdx, [rbp+0B0h]
0x180018f36  mov     ecx, [rbp+38h]
0x180018f39  call    _XcptFilter_0
0x180018f3e  mov     [rbp+40h], eax
0x180018f41  jmp     short loc_180018F4A
0x180018f43  mov     dword ptr [rbp+40h], 0
0x180018f4a  mov     eax, [rbp+40h]
0x180018f4d  add     rsp, 20h
0x180018f51  pop     rbp
0x180018f52  retn
0x180018f54  push    rbp
0x180018f56  sub     rsp, 20h
0x180018f5a  mov     rbp, rdx
0x180018f5d  mov     rax, [rcx]
0x180018f60  mov     edx, [rax]
0x180018f62  mov     [rbp+0B8h], rcx
0x180018f69  mov     [rbp+48h], edx
0x180018f6c  mov     eax, [rbp+48h]
0x180018f6f  cmp     eax, 0E06D7363h
0x180018f74  jnz     short loc_180018F8A
0x180018f76  mov     rdx, [rbp+0B8h]
0x180018f7d  mov     ecx, [rbp+48h]
0x180018f80  call    _XcptFilter_0
0x180018f85  mov     [rbp+50h], eax
0x180018f88  jmp     short loc_180018F91
0x180018f8a  mov     dword ptr [rbp+50h], 0
0x180018f91  mov     eax, [rbp+50h]
0x180018f94  add     rsp, 20h
0x180018f98  pop     rbp
0x180018f99  retn
0x180018f9b  push    rbp
0x180018f9d  sub     rsp, 20h
0x180018fa1  mov     rbp, rdx
0x180018fa4  mov     rax, [rcx]
0x180018fa7  mov     edx, [rax]
0x180018fa9  mov     [rbp+0C0h], rcx
0x180018fb0  mov     [rbp+58h], edx
0x180018fb3  mov     eax, [rbp+58h]
0x180018fb6  cmp     eax, 0E06D7363h
0x180018fbb  jnz     short loc_180018FD1
0x180018fbd  mov     rdx, [rbp+0C0h]
0x180018fc4  mov     ecx, [rbp+58h]
0x180018fc7  call    _XcptFilter_0
0x180018fcc  mov     [rbp+60h], eax
0x180018fcf  jmp     short loc_180018FD8
0x180018fd1  mov     dword ptr [rbp+60h], 0
0x180018fd8  mov     eax, [rbp+60h]
0x180018fdb  add     rsp, 20h
0x180018fdf  pop     rbp
0x180018fe0  retn
0x180018fe2  push    rbp
0x180018fe4  sub     rsp, 20h
0x180018fe8  mov     rbp, rdx
0x180018feb  mov     rax, [rcx]
0x180018fee  mov     edx, [rax]
0x180018ff0  mov     [rbp+0C8h], rcx
0x180018ff7  mov     [rbp+68h], edx
0x180018ffa  mov     eax, [rbp+68h]
0x180018ffd  cmp     eax, 0E06D7363h
0x180019002  jnz     short loc_180019018
0x180019004  mov     rdx, [rbp+0C8h]
0x18001900b  mov     ecx, [rbp+68h]
0x18001900e  call    _XcptFilter_0
0x180019013  mov     [rbp+70h], eax
0x180019016  jmp     short loc_18001901F
0x180019018  mov     dword ptr [rbp+70h], 0
0x18001901f  mov     eax, [rbp+70h]
0x180019022  add     rsp, 20h
0x180019026  pop     rbp
0x180019027  retn
0x180019029  push    rbp
0x18001902b  sub     rsp, 20h
0x18001902f  mov     rbp, rdx
0x180019032  mov     rax, [rcx]
0x180019035  mov     edx, [rax]
0x180019037  mov     [rbp+0D0h], rcx
0x18001903e  mov     [rbp+78h], edx
0x180019041  mov     eax, [rbp+78h]
0x180019044  cmp     eax, 0E06D7363h
0x180019049  jnz     short loc_180019062
0x18001904b  mov     rdx, [rbp+0D0h]
0x180019052  mov     ecx, [rbp+78h]
0x180019055  call    _XcptFilter_0
0x18001905a  mov     [rbp+80h], eax
0x180019060  jmp     short loc_18001906C
0x180019062  mov     dword ptr [rbp+80h], 0
0x18001906c  mov     eax, [rbp+80h]
0x180019072  add     rsp, 20h
0x180019076  pop     rbp
0x180019077  retn
0x180019079  push    rbp
0x18001907b  sub     rsp, 20h
0x18001907f  mov     rbp, rdx
0x180019082  mov     rax, [rcx]
0x180019085  mov     edx, [rax]
0x180019087  mov     [rbp+0D8h], rcx
0x18001908e  mov     [rbp+88h], edx
0x180019094  mov     eax, [rbp+88h]
0x18001909a  cmp     eax, 0E06D7363h
0x18001909f  jnz     short loc_1800190BB
0x1800190a1  mov     rdx, [rbp+0D8h]
0x1800190a8  mov     ecx, [rbp+88h]
0x1800190ae  call    _XcptFilter_0
0x1800190b3  mov     [rbp+90h], eax
0x1800190b9  jmp     short loc_1800190C5
0x1800190bb  mov     dword ptr [rbp+90h], 0
0x1800190c5  mov     eax, [rbp+90h]
0x1800190cb  add     rsp, 20h
0x1800190cf  pop     rbp
0x1800190d0  retn
0x1800190d2  push    rbp
0x1800190d4  sub     rsp, 20h
0x1800190d8  mov     rbp, rdx
0x1800190db  mov     rax, [rcx]
0x1800190de  mov     edx, [rax]
0x1800190e0  mov     [rbp+0E0h], rcx
0x1800190e7  mov     [rbp+98h], edx
0x1800190ed  mov     eax, [rbp+98h]
0x1800190f3  cmp     eax, 0E06D7363h
0x1800190f8  jnz     short loc_180019114
0x1800190fa  mov     rdx, [rbp+0E0h]
0x180019101  mov     ecx, [rbp+98h]
0x180019107  call    _XcptFilter_0
0x18001910c  mov     [rbp+0A0h], eax
0x180019112  jmp     short loc_18001911E
0x180019114  mov     dword ptr [rbp+0A0h], 0
0x18001911e  mov     eax, [rbp+0A0h]
0x180019124  add     rsp, 20h
0x180019128  pop     rbp
0x180019129  retn
0x18001912b  push    rbp
0x18001912d  sub     rsp, 20h
0x180019131  mov     rbp, rdx
0x180019134  cmp     dword ptr [rbp+118h], 1
0x18001913b  ja      short loc_180019147
0x18001913d  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
