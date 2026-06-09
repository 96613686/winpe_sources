# __DllMainCRTStartup

- ea: `0x180001f74`
- end: `0x180002180`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001f30`

## callees

- `0x180001d00`
- `0x180001f74`
- `0x180002426`
- `0x18000aac4`
- `0x18001d3b0`

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
  if ( (_DWORD)fdwReason || dword_180028CC0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180028CC4 = 1;
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
            if ( dword_180028CC4 )
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
0x180001f74  mov     [rsp+lpvReserved], r8
0x180001f79  mov     [rsp+arg_8], edx
0x180001f7d  mov     [rsp+arg_0], rcx
0x180001f82  push    rbx
0x180001f83  push    rsi
0x180001f84  push    rdi
0x180001f85  sub     rsp, 0F0h
0x180001f8c  mov     edi, edx
0x180001f8e  mov     rsi, rcx
0x180001f91  mov     ebx, 1
0x180001f96  cmp     edx, ebx
0x180001f98  ja      short loc_180001FA0
0x180001f9a  mov     cs:__native_dllmain_reason, edx
0x180001fa0  test    edx, edx
0x180001fa2  jnz     short loc_180001FB7
0x180001fa4  cmp     cs:dword_180028CC0, edx
0x180001faa  jnz     short loc_180001FB7
0x180001fac  xor     ebx, ebx
0x180001fae  mov     [rsp+108h+var_E8], ebx
0x180001fb2  jmp     loc_180002164
0x180001fb7  lea     eax, [rdx-1]
0x180001fba  cmp     eax, 1
0x180001fbd  ja      loc_180002044
0x180001fc3  mov     rax, cs:_pRawDllMain
0x180001fca  test    rax, rax
0x180001fcd  jz      short loc_180002005
0x180001fcf  cmp     edx, 1
0x180001fd2  jnz     short loc_180001FDA
0x180001fd4  mov     cs:dword_180028CC4, edx
0x180001fda  mov     r8, [rsp+108h+lpvReserved]
0x180001fe2  call    cs:__guard_dispatch_icall_fptr
0x180001fe8  mov     ebx, eax
0x180001fea  mov     [rsp+108h+var_E8], eax
0x180001fee  jmp     short loc_180002005
0x180001ff0  xor     ebx, ebx
0x180001ff2  mov     [rsp+108h+var_E8], ebx
0x180001ff6  mov     edi, [rsp+108h+arg_8]
0x180001ffd  mov     rsi, [rsp+108h+arg_0]
0x180002005  test    ebx, ebx
0x180002007  jz      loc_180002164
0x18000200d  mov     r8, [rsp+108h+lpvReserved]
0x180002015  mov     edx, edi
0x180002017  mov     rcx, rsi
0x18000201a  call    _CRT_INIT
0x18000201f  mov     ebx, eax
0x180002021  mov     [rsp+108h+var_E8], eax
0x180002025  jmp     short loc_18000203C
0x180002027  xor     ebx, ebx
0x180002029  mov     [rsp+108h+var_E8], ebx
0x18000202d  mov     edi, [rsp+108h+arg_8]
0x180002034  mov     rsi, [rsp+108h+arg_0]
0x18000203c  test    ebx, ebx
0x18000203e  jz      loc_180002164
0x180002044  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000204c  mov     edx, edi; fdwReason
0x18000204e  mov     rcx, rsi; hinstDLL
0x180002051  call    DllMain
0x180002056  mov     ebx, eax
0x180002058  mov     [rsp+108h+var_E8], eax
0x18000205c  jmp     short loc_180002073
0x18000205e  xor     ebx, ebx
0x180002060  mov     [rsp+108h+var_E8], ebx
0x180002064  mov     edi, [rsp+108h+arg_8]
0x18000206b  mov     rsi, [rsp+108h+arg_0]
0x180002073  cmp     edi, 1
0x180002076  jnz     short loc_1800020EF
0x180002078  test    ebx, ebx
0x18000207a  jnz     short loc_1800020EF
0x18000207c  xor     r8d, r8d; lpvReserved
0x18000207f  xor     edx, edx; fdwReason
0x180002081  mov     rcx, rsi; hinstDLL
0x180002084  call    DllMain
0x180002089  jmp     short loc_18000209E
0x18000208b  mov     edi, [rsp+108h+arg_8]
0x180002092  mov     rsi, [rsp+108h+arg_0]
0x18000209a  mov     ebx, [rsp+108h+var_E8]
0x18000209e  xor     r8d, r8d
0x1800020a1  xor     edx, edx
0x1800020a3  mov     rcx, rsi
0x1800020a6  call    _CRT_INIT
0x1800020ab  jmp     short loc_1800020C0
0x1800020ad  mov     edi, [rsp+108h+arg_8]
0x1800020b4  mov     rsi, [rsp+108h+arg_0]
0x1800020bc  mov     ebx, [rsp+108h+var_E8]
0x1800020c0  mov     rax, cs:_pRawDllMain
0x1800020c7  test    rax, rax
0x1800020ca  jz      short loc_1800020EF
0x1800020cc  xor     r8d, r8d
0x1800020cf  xor     edx, edx
0x1800020d1  mov     rcx, rsi
0x1800020d4  call    cs:__guard_dispatch_icall_fptr
0x1800020da  jmp     short loc_1800020EF
0x1800020dc  mov     edi, [rsp+108h+arg_8]
0x1800020e3  mov     rsi, [rsp+108h+arg_0]
0x1800020eb  mov     ebx, [rsp+108h+var_E8]
0x1800020ef  test    edi, edi
0x1800020f1  jz      short loc_1800020F8
0x1800020f3  cmp     edi, 3
0x1800020f6  jnz     short loc_180002164
0x1800020f8  mov     r8, [rsp+108h+lpvReserved]
0x180002100  mov     edx, edi
0x180002102  mov     rcx, rsi
0x180002105  call    _CRT_INIT
0x18000210a  mov     ebx, eax
0x18000210c  mov     [rsp+108h+var_E8], eax
0x180002110  jmp     short loc_180002127
0x180002112  xor     ebx, ebx
0x180002114  mov     [rsp+108h+var_E8], ebx
0x180002118  mov     edi, [rsp+108h+arg_8]
0x18000211f  mov     rsi, [rsp+108h+arg_0]
0x180002127  mov     rax, cs:_pRawDllMain
0x18000212e  test    rax, rax
0x180002131  jz      short loc_180002164
0x180002133  cmp     cs:dword_180028CC4, 0
0x18000213a  jz      short loc_180002164
0x18000213c  mov     r8, [rsp+108h+lpvReserved]
0x180002144  mov     edx, edi
0x180002146  mov     rcx, rsi
0x180002149  call    cs:__guard_dispatch_icall_fptr
0x18000214f  mov     ebx, eax
0x180002151  mov     [rsp+108h+var_E8], eax
0x180002155  jmp     short loc_180002164
0x180002157  xor     ebx, ebx
0x180002159  mov     [rsp+108h+var_E8], ebx
0x18000215d  mov     edi, [rsp+108h+arg_8]
0x180002164  cmp     edi, 1
0x180002167  ja      short loc_180002173
0x180002169  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002173  mov     eax, ebx
0x180002175  add     rsp, 0F0h
0x18000217c  pop     rdi
0x18000217d  pop     rsi
0x18000217e  pop     rbx
0x18000217f  retn
0x18001d480  push    rbp
0x18001d482  sub     rsp, 20h
0x18001d486  mov     rbp, rdx
0x18001d489  mov     rax, [rcx]
0x18001d48c  mov     edx, [rax]
0x18001d48e  mov     [rbp+0A8h], rcx
0x18001d495  mov     [rbp+28h], edx
0x18001d498  mov     eax, [rbp+28h]
0x18001d49b  cmp     eax, 0E06D7363h
0x18001d4a0  jnz     short loc_18001D4B6
0x18001d4a2  mov     rdx, [rbp+0A8h]
0x18001d4a9  mov     ecx, [rbp+28h]
0x18001d4ac  call    _XcptFilter_0
0x18001d4b1  mov     [rbp+30h], eax
0x18001d4b4  jmp     short loc_18001D4BD
0x18001d4b6  mov     dword ptr [rbp+30h], 0
0x18001d4bd  mov     eax, [rbp+30h]
0x18001d4c0  add     rsp, 20h
0x18001d4c4  pop     rbp
0x18001d4c5  retn
0x18001d4c7  push    rbp
0x18001d4c9  sub     rsp, 20h
0x18001d4cd  mov     rbp, rdx
0x18001d4d0  mov     rax, [rcx]
0x18001d4d3  mov     edx, [rax]
0x18001d4d5  mov     [rbp+0B0h], rcx
0x18001d4dc  mov     [rbp+38h], edx
0x18001d4df  mov     eax, [rbp+38h]
0x18001d4e2  cmp     eax, 0E06D7363h
0x18001d4e7  jnz     short loc_18001D4FD
0x18001d4e9  mov     rdx, [rbp+0B0h]
0x18001d4f0  mov     ecx, [rbp+38h]
0x18001d4f3  call    _XcptFilter_0
0x18001d4f8  mov     [rbp+40h], eax
0x18001d4fb  jmp     short loc_18001D504
0x18001d4fd  mov     dword ptr [rbp+40h], 0
0x18001d504  mov     eax, [rbp+40h]
0x18001d507  add     rsp, 20h
0x18001d50b  pop     rbp
0x18001d50c  retn
0x18001d50e  push    rbp
0x18001d510  sub     rsp, 20h
0x18001d514  mov     rbp, rdx
0x18001d517  mov     rax, [rcx]
0x18001d51a  mov     edx, [rax]
0x18001d51c  mov     [rbp+0B8h], rcx
0x18001d523  mov     [rbp+48h], edx
0x18001d526  mov     eax, [rbp+48h]
0x18001d529  cmp     eax, 0E06D7363h
0x18001d52e  jnz     short loc_18001D544
0x18001d530  mov     rdx, [rbp+0B8h]
0x18001d537  mov     ecx, [rbp+48h]
0x18001d53a  call    _XcptFilter_0
0x18001d53f  mov     [rbp+50h], eax
0x18001d542  jmp     short loc_18001D54B
0x18001d544  mov     dword ptr [rbp+50h], 0
0x18001d54b  mov     eax, [rbp+50h]
0x18001d54e  add     rsp, 20h
0x18001d552  pop     rbp
0x18001d553  retn
0x18001d555  push    rbp
0x18001d557  sub     rsp, 20h
0x18001d55b  mov     rbp, rdx
0x18001d55e  mov     rax, [rcx]
0x18001d561  mov     edx, [rax]
0x18001d563  mov     [rbp+0C0h], rcx
0x18001d56a  mov     [rbp+58h], edx
0x18001d56d  mov     eax, [rbp+58h]
0x18001d570  cmp     eax, 0E06D7363h
0x18001d575  jnz     short loc_18001D58B
0x18001d577  mov     rdx, [rbp+0C0h]
0x18001d57e  mov     ecx, [rbp+58h]
0x18001d581  call    _XcptFilter_0
0x18001d586  mov     [rbp+60h], eax
0x18001d589  jmp     short loc_18001D592
0x18001d58b  mov     dword ptr [rbp+60h], 0
0x18001d592  mov     eax, [rbp+60h]
0x18001d595  add     rsp, 20h
0x18001d599  pop     rbp
0x18001d59a  retn
0x18001d59c  push    rbp
0x18001d59e  sub     rsp, 20h
0x18001d5a2  mov     rbp, rdx
0x18001d5a5  mov     rax, [rcx]
0x18001d5a8  mov     edx, [rax]
0x18001d5aa  mov     [rbp+0C8h], rcx
0x18001d5b1  mov     [rbp+68h], edx
0x18001d5b4  mov     eax, [rbp+68h]
0x18001d5b7  cmp     eax, 0E06D7363h
0x18001d5bc  jnz     short loc_18001D5D2
0x18001d5be  mov     rdx, [rbp+0C8h]
0x18001d5c5  mov     ecx, [rbp+68h]
0x18001d5c8  call    _XcptFilter_0
0x18001d5cd  mov     [rbp+70h], eax
0x18001d5d0  jmp     short loc_18001D5D9
0x18001d5d2  mov     dword ptr [rbp+70h], 0
0x18001d5d9  mov     eax, [rbp+70h]
0x18001d5dc  add     rsp, 20h
0x18001d5e0  pop     rbp
0x18001d5e1  retn
0x18001d5e3  push    rbp
0x18001d5e5  sub     rsp, 20h
0x18001d5e9  mov     rbp, rdx
0x18001d5ec  mov     rax, [rcx]
0x18001d5ef  mov     edx, [rax]
0x18001d5f1  mov     [rbp+0D0h], rcx
0x18001d5f8  mov     [rbp+78h], edx
0x18001d5fb  mov     eax, [rbp+78h]
0x18001d5fe  cmp     eax, 0E06D7363h
0x18001d603  jnz     short loc_18001D61C
0x18001d605  mov     rdx, [rbp+0D0h]
0x18001d60c  mov     ecx, [rbp+78h]
0x18001d60f  call    _XcptFilter_0
0x18001d614  mov     [rbp+80h], eax
0x18001d61a  jmp     short loc_18001D626
0x18001d61c  mov     dword ptr [rbp+80h], 0
0x18001d626  mov     eax, [rbp+80h]
0x18001d62c  add     rsp, 20h
0x18001d630  pop     rbp
0x18001d631  retn
0x18001d633  push    rbp
0x18001d635  sub     rsp, 20h
0x18001d639  mov     rbp, rdx
0x18001d63c  mov     rax, [rcx]
0x18001d63f  mov     edx, [rax]
0x18001d641  mov     [rbp+0D8h], rcx
0x18001d648  mov     [rbp+88h], edx
0x18001d64e  mov     eax, [rbp+88h]
0x18001d654  cmp     eax, 0E06D7363h
0x18001d659  jnz     short loc_18001D675
0x18001d65b  mov     rdx, [rbp+0D8h]
0x18001d662  mov     ecx, [rbp+88h]
0x18001d668  call    _XcptFilter_0
0x18001d66d  mov     [rbp+90h], eax
0x18001d673  jmp     short loc_18001D67F
0x18001d675  mov     dword ptr [rbp+90h], 0
0x18001d67f  mov     eax, [rbp+90h]
0x18001d685  add     rsp, 20h
0x18001d689  pop     rbp
0x18001d68a  retn
0x18001d68c  push    rbp
0x18001d68e  sub     rsp, 20h
0x18001d692  mov     rbp, rdx
0x18001d695  mov     rax, [rcx]
0x18001d698  mov     edx, [rax]
0x18001d69a  mov     [rbp+0E0h], rcx
0x18001d6a1  mov     [rbp+98h], edx
0x18001d6a7  mov     eax, [rbp+98h]
0x18001d6ad  cmp     eax, 0E06D7363h
0x18001d6b2  jnz     short loc_18001D6CE
0x18001d6b4  mov     rdx, [rbp+0E0h]
0x18001d6bb  mov     ecx, [rbp+98h]
0x18001d6c1  call    _XcptFilter_0
0x18001d6c6  mov     [rbp+0A0h], eax
0x18001d6cc  jmp     short loc_18001D6D8
0x18001d6ce  mov     dword ptr [rbp+0A0h], 0
0x18001d6d8  mov     eax, [rbp+0A0h]
0x18001d6de  add     rsp, 20h
0x18001d6e2  pop     rbp
0x18001d6e3  retn
0x18001d6e5  push    rbp
0x18001d6e7  sub     rsp, 20h
0x18001d6eb  mov     rbp, rdx
0x18001d6ee  cmp     dword ptr [rbp+118h], 1
0x18001d6f5  ja      short loc_18001D701
0x18001d6f7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
