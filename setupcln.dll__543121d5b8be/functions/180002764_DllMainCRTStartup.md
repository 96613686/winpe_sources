# __DllMainCRTStartup

- ea: `0x180002764`
- end: `0x180002970`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002720`

## callees

- `0x1800024f0`
- `0x180002764`
- `0x180002b7e`
- `0x18000304c`
- `0x180013250`

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
  if ( (_DWORD)fdwReason || dword_18001F64C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001F650 = 1;
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
            if ( dword_18001F650 )
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
0x180002764  mov     [rsp+lpvReserved], r8
0x180002769  mov     [rsp+arg_8], edx
0x18000276d  mov     [rsp+arg_0], rcx
0x180002772  push    rbx
0x180002773  push    rsi
0x180002774  push    rdi
0x180002775  sub     rsp, 0F0h
0x18000277c  mov     edi, edx
0x18000277e  mov     rsi, rcx
0x180002781  mov     ebx, 1
0x180002786  cmp     edx, ebx
0x180002788  ja      short loc_180002790
0x18000278a  mov     cs:__native_dllmain_reason, edx
0x180002790  test    edx, edx
0x180002792  jnz     short loc_1800027A7
0x180002794  cmp     cs:dword_18001F64C, edx
0x18000279a  jnz     short loc_1800027A7
0x18000279c  xor     ebx, ebx
0x18000279e  mov     [rsp+108h+var_E8], ebx
0x1800027a2  jmp     loc_180002954
0x1800027a7  lea     eax, [rdx-1]
0x1800027aa  cmp     eax, 1
0x1800027ad  ja      loc_180002834
0x1800027b3  mov     rax, cs:_pRawDllMain
0x1800027ba  test    rax, rax
0x1800027bd  jz      short loc_1800027F5
0x1800027bf  cmp     edx, 1
0x1800027c2  jnz     short loc_1800027CA
0x1800027c4  mov     cs:dword_18001F650, edx
0x1800027ca  mov     r8, [rsp+108h+lpvReserved]
0x1800027d2  call    cs:__guard_dispatch_icall_fptr
0x1800027d8  mov     ebx, eax
0x1800027da  mov     [rsp+108h+var_E8], eax
0x1800027de  jmp     short loc_1800027F5
0x1800027e0  xor     ebx, ebx
0x1800027e2  mov     [rsp+108h+var_E8], ebx
0x1800027e6  mov     edi, [rsp+108h+arg_8]
0x1800027ed  mov     rsi, [rsp+108h+arg_0]
0x1800027f5  test    ebx, ebx
0x1800027f7  jz      loc_180002954
0x1800027fd  mov     r8, [rsp+108h+lpvReserved]
0x180002805  mov     edx, edi
0x180002807  mov     rcx, rsi
0x18000280a  call    _CRT_INIT
0x18000280f  mov     ebx, eax
0x180002811  mov     [rsp+108h+var_E8], eax
0x180002815  jmp     short loc_18000282C
0x180002817  xor     ebx, ebx
0x180002819  mov     [rsp+108h+var_E8], ebx
0x18000281d  mov     edi, [rsp+108h+arg_8]
0x180002824  mov     rsi, [rsp+108h+arg_0]
0x18000282c  test    ebx, ebx
0x18000282e  jz      loc_180002954
0x180002834  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000283c  mov     edx, edi; fdwReason
0x18000283e  mov     rcx, rsi; hinstDLL
0x180002841  call    DllMain
0x180002846  mov     ebx, eax
0x180002848  mov     [rsp+108h+var_E8], eax
0x18000284c  jmp     short loc_180002863
0x18000284e  xor     ebx, ebx
0x180002850  mov     [rsp+108h+var_E8], ebx
0x180002854  mov     edi, [rsp+108h+arg_8]
0x18000285b  mov     rsi, [rsp+108h+arg_0]
0x180002863  cmp     edi, 1
0x180002866  jnz     short loc_1800028DF
0x180002868  test    ebx, ebx
0x18000286a  jnz     short loc_1800028DF
0x18000286c  xor     r8d, r8d; lpvReserved
0x18000286f  xor     edx, edx; fdwReason
0x180002871  mov     rcx, rsi; hinstDLL
0x180002874  call    DllMain
0x180002879  jmp     short loc_18000288E
0x18000287b  mov     edi, [rsp+108h+arg_8]
0x180002882  mov     rsi, [rsp+108h+arg_0]
0x18000288a  mov     ebx, [rsp+108h+var_E8]
0x18000288e  xor     r8d, r8d
0x180002891  xor     edx, edx
0x180002893  mov     rcx, rsi
0x180002896  call    _CRT_INIT
0x18000289b  jmp     short loc_1800028B0
0x18000289d  mov     edi, [rsp+108h+arg_8]
0x1800028a4  mov     rsi, [rsp+108h+arg_0]
0x1800028ac  mov     ebx, [rsp+108h+var_E8]
0x1800028b0  mov     rax, cs:_pRawDllMain
0x1800028b7  test    rax, rax
0x1800028ba  jz      short loc_1800028DF
0x1800028bc  xor     r8d, r8d
0x1800028bf  xor     edx, edx
0x1800028c1  mov     rcx, rsi
0x1800028c4  call    cs:__guard_dispatch_icall_fptr
0x1800028ca  jmp     short loc_1800028DF
0x1800028cc  mov     edi, [rsp+108h+arg_8]
0x1800028d3  mov     rsi, [rsp+108h+arg_0]
0x1800028db  mov     ebx, [rsp+108h+var_E8]
0x1800028df  test    edi, edi
0x1800028e1  jz      short loc_1800028E8
0x1800028e3  cmp     edi, 3
0x1800028e6  jnz     short loc_180002954
0x1800028e8  mov     r8, [rsp+108h+lpvReserved]
0x1800028f0  mov     edx, edi
0x1800028f2  mov     rcx, rsi
0x1800028f5  call    _CRT_INIT
0x1800028fa  mov     ebx, eax
0x1800028fc  mov     [rsp+108h+var_E8], eax
0x180002900  jmp     short loc_180002917
0x180002902  xor     ebx, ebx
0x180002904  mov     [rsp+108h+var_E8], ebx
0x180002908  mov     edi, [rsp+108h+arg_8]
0x18000290f  mov     rsi, [rsp+108h+arg_0]
0x180002917  mov     rax, cs:_pRawDllMain
0x18000291e  test    rax, rax
0x180002921  jz      short loc_180002954
0x180002923  cmp     cs:dword_18001F650, 0
0x18000292a  jz      short loc_180002954
0x18000292c  mov     r8, [rsp+108h+lpvReserved]
0x180002934  mov     edx, edi
0x180002936  mov     rcx, rsi
0x180002939  call    cs:__guard_dispatch_icall_fptr
0x18000293f  mov     ebx, eax
0x180002941  mov     [rsp+108h+var_E8], eax
0x180002945  jmp     short loc_180002954
0x180002947  xor     ebx, ebx
0x180002949  mov     [rsp+108h+var_E8], ebx
0x18000294d  mov     edi, [rsp+108h+arg_8]
0x180002954  cmp     edi, 1
0x180002957  ja      short loc_180002963
0x180002959  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002963  mov     eax, ebx
0x180002965  add     rsp, 0F0h
0x18000296c  pop     rdi
0x18000296d  pop     rsi
0x18000296e  pop     rbx
0x18000296f  retn
0x180013362  push    rbp
0x180013364  sub     rsp, 20h
0x180013368  mov     rbp, rdx
0x18001336b  mov     rax, [rcx]
0x18001336e  mov     edx, [rax]
0x180013370  mov     [rbp+0A8h], rcx
0x180013377  mov     [rbp+28h], edx
0x18001337a  mov     eax, [rbp+28h]
0x18001337d  cmp     eax, 0E06D7363h
0x180013382  jnz     short loc_180013398
0x180013384  mov     rdx, [rbp+0A8h]
0x18001338b  mov     ecx, [rbp+28h]
0x18001338e  call    _XcptFilter_0
0x180013393  mov     [rbp+30h], eax
0x180013396  jmp     short loc_18001339F
0x180013398  mov     dword ptr [rbp+30h], 0
0x18001339f  mov     eax, [rbp+30h]
0x1800133a2  add     rsp, 20h
0x1800133a6  pop     rbp
0x1800133a7  retn
0x1800133a9  push    rbp
0x1800133ab  sub     rsp, 20h
0x1800133af  mov     rbp, rdx
0x1800133b2  mov     rax, [rcx]
0x1800133b5  mov     edx, [rax]
0x1800133b7  mov     [rbp+0B0h], rcx
0x1800133be  mov     [rbp+38h], edx
0x1800133c1  mov     eax, [rbp+38h]
0x1800133c4  cmp     eax, 0E06D7363h
0x1800133c9  jnz     short loc_1800133DF
0x1800133cb  mov     rdx, [rbp+0B0h]
0x1800133d2  mov     ecx, [rbp+38h]
0x1800133d5  call    _XcptFilter_0
0x1800133da  mov     [rbp+40h], eax
0x1800133dd  jmp     short loc_1800133E6
0x1800133df  mov     dword ptr [rbp+40h], 0
0x1800133e6  mov     eax, [rbp+40h]
0x1800133e9  add     rsp, 20h
0x1800133ed  pop     rbp
0x1800133ee  retn
0x1800133f0  push    rbp
0x1800133f2  sub     rsp, 20h
0x1800133f6  mov     rbp, rdx
0x1800133f9  mov     rax, [rcx]
0x1800133fc  mov     edx, [rax]
0x1800133fe  mov     [rbp+0B8h], rcx
0x180013405  mov     [rbp+48h], edx
0x180013408  mov     eax, [rbp+48h]
0x18001340b  cmp     eax, 0E06D7363h
0x180013410  jnz     short loc_180013426
0x180013412  mov     rdx, [rbp+0B8h]
0x180013419  mov     ecx, [rbp+48h]
0x18001341c  call    _XcptFilter_0
0x180013421  mov     [rbp+50h], eax
0x180013424  jmp     short loc_18001342D
0x180013426  mov     dword ptr [rbp+50h], 0
0x18001342d  mov     eax, [rbp+50h]
0x180013430  add     rsp, 20h
0x180013434  pop     rbp
0x180013435  retn
0x180013437  push    rbp
0x180013439  sub     rsp, 20h
0x18001343d  mov     rbp, rdx
0x180013440  mov     rax, [rcx]
0x180013443  mov     edx, [rax]
0x180013445  mov     [rbp+0C0h], rcx
0x18001344c  mov     [rbp+58h], edx
0x18001344f  mov     eax, [rbp+58h]
0x180013452  cmp     eax, 0E06D7363h
0x180013457  jnz     short loc_18001346D
0x180013459  mov     rdx, [rbp+0C0h]
0x180013460  mov     ecx, [rbp+58h]
0x180013463  call    _XcptFilter_0
0x180013468  mov     [rbp+60h], eax
0x18001346b  jmp     short loc_180013474
0x18001346d  mov     dword ptr [rbp+60h], 0
0x180013474  mov     eax, [rbp+60h]
0x180013477  add     rsp, 20h
0x18001347b  pop     rbp
0x18001347c  retn
0x18001347e  push    rbp
0x180013480  sub     rsp, 20h
0x180013484  mov     rbp, rdx
0x180013487  mov     rax, [rcx]
0x18001348a  mov     edx, [rax]
0x18001348c  mov     [rbp+0C8h], rcx
0x180013493  mov     [rbp+68h], edx
0x180013496  mov     eax, [rbp+68h]
0x180013499  cmp     eax, 0E06D7363h
0x18001349e  jnz     short loc_1800134B4
0x1800134a0  mov     rdx, [rbp+0C8h]
0x1800134a7  mov     ecx, [rbp+68h]
0x1800134aa  call    _XcptFilter_0
0x1800134af  mov     [rbp+70h], eax
0x1800134b2  jmp     short loc_1800134BB
0x1800134b4  mov     dword ptr [rbp+70h], 0
0x1800134bb  mov     eax, [rbp+70h]
0x1800134be  add     rsp, 20h
0x1800134c2  pop     rbp
0x1800134c3  retn
0x1800134c5  push    rbp
0x1800134c7  sub     rsp, 20h
0x1800134cb  mov     rbp, rdx
0x1800134ce  mov     rax, [rcx]
0x1800134d1  mov     edx, [rax]
0x1800134d3  mov     [rbp+0D0h], rcx
0x1800134da  mov     [rbp+78h], edx
0x1800134dd  mov     eax, [rbp+78h]
0x1800134e0  cmp     eax, 0E06D7363h
0x1800134e5  jnz     short loc_1800134FE
0x1800134e7  mov     rdx, [rbp+0D0h]
0x1800134ee  mov     ecx, [rbp+78h]
0x1800134f1  call    _XcptFilter_0
0x1800134f6  mov     [rbp+80h], eax
0x1800134fc  jmp     short loc_180013508
0x1800134fe  mov     dword ptr [rbp+80h], 0
0x180013508  mov     eax, [rbp+80h]
0x18001350e  add     rsp, 20h
0x180013512  pop     rbp
0x180013513  retn
0x180013515  push    rbp
0x180013517  sub     rsp, 20h
0x18001351b  mov     rbp, rdx
0x18001351e  mov     rax, [rcx]
0x180013521  mov     edx, [rax]
0x180013523  mov     [rbp+0D8h], rcx
0x18001352a  mov     [rbp+88h], edx
0x180013530  mov     eax, [rbp+88h]
0x180013536  cmp     eax, 0E06D7363h
0x18001353b  jnz     short loc_180013557
0x18001353d  mov     rdx, [rbp+0D8h]
0x180013544  mov     ecx, [rbp+88h]
0x18001354a  call    _XcptFilter_0
0x18001354f  mov     [rbp+90h], eax
0x180013555  jmp     short loc_180013561
0x180013557  mov     dword ptr [rbp+90h], 0
0x180013561  mov     eax, [rbp+90h]
0x180013567  add     rsp, 20h
0x18001356b  pop     rbp
0x18001356c  retn
0x18001356e  push    rbp
0x180013570  sub     rsp, 20h
0x180013574  mov     rbp, rdx
0x180013577  mov     rax, [rcx]
0x18001357a  mov     edx, [rax]
0x18001357c  mov     [rbp+0E0h], rcx
0x180013583  mov     [rbp+98h], edx
0x180013589  mov     eax, [rbp+98h]
0x18001358f  cmp     eax, 0E06D7363h
0x180013594  jnz     short loc_1800135B0
0x180013596  mov     rdx, [rbp+0E0h]
0x18001359d  mov     ecx, [rbp+98h]
0x1800135a3  call    _XcptFilter_0
0x1800135a8  mov     [rbp+0A0h], eax
0x1800135ae  jmp     short loc_1800135BA
0x1800135b0  mov     dword ptr [rbp+0A0h], 0
0x1800135ba  mov     eax, [rbp+0A0h]
0x1800135c0  add     rsp, 20h
0x1800135c4  pop     rbp
0x1800135c5  retn
0x1800135c7  push    rbp
0x1800135c9  sub     rsp, 20h
0x1800135cd  mov     rbp, rdx
0x1800135d0  cmp     dword ptr [rbp+118h], 1
0x1800135d7  ja      short loc_1800135E3
0x1800135d9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
