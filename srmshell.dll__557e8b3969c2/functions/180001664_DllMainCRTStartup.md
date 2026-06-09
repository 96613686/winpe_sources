# __DllMainCRTStartup

- ea: `0x180001664`
- end: `0x180001870`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001620`

## callees

- `0x1800013f0`
- `0x180001664`
- `0x180001e5c`
- `0x180015c34`
- `0x18001b490`

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
  if ( (_DWORD)fdwReason || dword_18002B500 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002B504 = 1;
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
            if ( dword_18002B504 )
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
0x180001664  mov     [rsp+lpvReserved], r8
0x180001669  mov     [rsp+arg_8], edx
0x18000166d  mov     [rsp+arg_0], rcx
0x180001672  push    rbx
0x180001673  push    rsi
0x180001674  push    rdi
0x180001675  sub     rsp, 0F0h
0x18000167c  mov     edi, edx
0x18000167e  mov     rsi, rcx
0x180001681  mov     ebx, 1
0x180001686  cmp     edx, ebx
0x180001688  ja      short loc_180001690
0x18000168a  mov     cs:__native_dllmain_reason, edx
0x180001690  test    edx, edx
0x180001692  jnz     short loc_1800016A7
0x180001694  cmp     cs:dword_18002B500, edx
0x18000169a  jnz     short loc_1800016A7
0x18000169c  xor     ebx, ebx
0x18000169e  mov     [rsp+108h+var_E8], ebx
0x1800016a2  jmp     loc_180001854
0x1800016a7  lea     eax, [rdx-1]
0x1800016aa  cmp     eax, 1
0x1800016ad  ja      loc_180001734
0x1800016b3  mov     rax, cs:_pRawDllMain
0x1800016ba  test    rax, rax
0x1800016bd  jz      short loc_1800016F5
0x1800016bf  cmp     edx, 1
0x1800016c2  jnz     short loc_1800016CA
0x1800016c4  mov     cs:dword_18002B504, edx
0x1800016ca  mov     r8, [rsp+108h+lpvReserved]
0x1800016d2  call    cs:__guard_dispatch_icall_fptr
0x1800016d8  mov     ebx, eax
0x1800016da  mov     [rsp+108h+var_E8], eax
0x1800016de  jmp     short loc_1800016F5
0x1800016e0  xor     ebx, ebx
0x1800016e2  mov     [rsp+108h+var_E8], ebx
0x1800016e6  mov     edi, [rsp+108h+arg_8]
0x1800016ed  mov     rsi, [rsp+108h+arg_0]
0x1800016f5  test    ebx, ebx
0x1800016f7  jz      loc_180001854
0x1800016fd  mov     r8, [rsp+108h+lpvReserved]
0x180001705  mov     edx, edi
0x180001707  mov     rcx, rsi
0x18000170a  call    _CRT_INIT
0x18000170f  mov     ebx, eax
0x180001711  mov     [rsp+108h+var_E8], eax
0x180001715  jmp     short loc_18000172C
0x180001717  xor     ebx, ebx
0x180001719  mov     [rsp+108h+var_E8], ebx
0x18000171d  mov     edi, [rsp+108h+arg_8]
0x180001724  mov     rsi, [rsp+108h+arg_0]
0x18000172c  test    ebx, ebx
0x18000172e  jz      loc_180001854
0x180001734  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000173c  mov     edx, edi; fdwReason
0x18000173e  mov     rcx, rsi; hinstDLL
0x180001741  call    DllMain
0x180001746  mov     ebx, eax
0x180001748  mov     [rsp+108h+var_E8], eax
0x18000174c  jmp     short loc_180001763
0x18000174e  xor     ebx, ebx
0x180001750  mov     [rsp+108h+var_E8], ebx
0x180001754  mov     edi, [rsp+108h+arg_8]
0x18000175b  mov     rsi, [rsp+108h+arg_0]
0x180001763  cmp     edi, 1
0x180001766  jnz     short loc_1800017DF
0x180001768  test    ebx, ebx
0x18000176a  jnz     short loc_1800017DF
0x18000176c  xor     r8d, r8d; lpvReserved
0x18000176f  xor     edx, edx; fdwReason
0x180001771  mov     rcx, rsi; hinstDLL
0x180001774  call    DllMain
0x180001779  jmp     short loc_18000178E
0x18000177b  mov     edi, [rsp+108h+arg_8]
0x180001782  mov     rsi, [rsp+108h+arg_0]
0x18000178a  mov     ebx, [rsp+108h+var_E8]
0x18000178e  xor     r8d, r8d
0x180001791  xor     edx, edx
0x180001793  mov     rcx, rsi
0x180001796  call    _CRT_INIT
0x18000179b  jmp     short loc_1800017B0
0x18000179d  mov     edi, [rsp+108h+arg_8]
0x1800017a4  mov     rsi, [rsp+108h+arg_0]
0x1800017ac  mov     ebx, [rsp+108h+var_E8]
0x1800017b0  mov     rax, cs:_pRawDllMain
0x1800017b7  test    rax, rax
0x1800017ba  jz      short loc_1800017DF
0x1800017bc  xor     r8d, r8d
0x1800017bf  xor     edx, edx
0x1800017c1  mov     rcx, rsi
0x1800017c4  call    cs:__guard_dispatch_icall_fptr
0x1800017ca  jmp     short loc_1800017DF
0x1800017cc  mov     edi, [rsp+108h+arg_8]
0x1800017d3  mov     rsi, [rsp+108h+arg_0]
0x1800017db  mov     ebx, [rsp+108h+var_E8]
0x1800017df  test    edi, edi
0x1800017e1  jz      short loc_1800017E8
0x1800017e3  cmp     edi, 3
0x1800017e6  jnz     short loc_180001854
0x1800017e8  mov     r8, [rsp+108h+lpvReserved]
0x1800017f0  mov     edx, edi
0x1800017f2  mov     rcx, rsi
0x1800017f5  call    _CRT_INIT
0x1800017fa  mov     ebx, eax
0x1800017fc  mov     [rsp+108h+var_E8], eax
0x180001800  jmp     short loc_180001817
0x180001802  xor     ebx, ebx
0x180001804  mov     [rsp+108h+var_E8], ebx
0x180001808  mov     edi, [rsp+108h+arg_8]
0x18000180f  mov     rsi, [rsp+108h+arg_0]
0x180001817  mov     rax, cs:_pRawDllMain
0x18000181e  test    rax, rax
0x180001821  jz      short loc_180001854
0x180001823  cmp     cs:dword_18002B504, 0
0x18000182a  jz      short loc_180001854
0x18000182c  mov     r8, [rsp+108h+lpvReserved]
0x180001834  mov     edx, edi
0x180001836  mov     rcx, rsi
0x180001839  call    cs:__guard_dispatch_icall_fptr
0x18000183f  mov     ebx, eax
0x180001841  mov     [rsp+108h+var_E8], eax
0x180001845  jmp     short loc_180001854
0x180001847  xor     ebx, ebx
0x180001849  mov     [rsp+108h+var_E8], ebx
0x18000184d  mov     edi, [rsp+108h+arg_8]
0x180001854  cmp     edi, 1
0x180001857  ja      short loc_180001863
0x180001859  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001863  mov     eax, ebx
0x180001865  add     rsp, 0F0h
0x18000186c  pop     rdi
0x18000186d  pop     rsi
0x18000186e  pop     rbx
0x18000186f  retn
0x18001b533  push    rbp
0x18001b535  sub     rsp, 20h
0x18001b539  mov     rbp, rdx
0x18001b53c  mov     rax, [rcx]
0x18001b53f  mov     edx, [rax]
0x18001b541  mov     [rbp+0A8h], rcx
0x18001b548  mov     [rbp+28h], edx
0x18001b54b  mov     eax, [rbp+28h]
0x18001b54e  cmp     eax, 0E06D7363h
0x18001b553  jnz     short loc_18001B569
0x18001b555  mov     rdx, [rbp+0A8h]
0x18001b55c  mov     ecx, [rbp+28h]
0x18001b55f  call    _XcptFilter_0
0x18001b564  mov     [rbp+30h], eax
0x18001b567  jmp     short loc_18001B570
0x18001b569  mov     dword ptr [rbp+30h], 0
0x18001b570  mov     eax, [rbp+30h]
0x18001b573  add     rsp, 20h
0x18001b577  pop     rbp
0x18001b578  retn
0x18001b57a  push    rbp
0x18001b57c  sub     rsp, 20h
0x18001b580  mov     rbp, rdx
0x18001b583  mov     rax, [rcx]
0x18001b586  mov     edx, [rax]
0x18001b588  mov     [rbp+0B0h], rcx
0x18001b58f  mov     [rbp+38h], edx
0x18001b592  mov     eax, [rbp+38h]
0x18001b595  cmp     eax, 0E06D7363h
0x18001b59a  jnz     short loc_18001B5B0
0x18001b59c  mov     rdx, [rbp+0B0h]
0x18001b5a3  mov     ecx, [rbp+38h]
0x18001b5a6  call    _XcptFilter_0
0x18001b5ab  mov     [rbp+40h], eax
0x18001b5ae  jmp     short loc_18001B5B7
0x18001b5b0  mov     dword ptr [rbp+40h], 0
0x18001b5b7  mov     eax, [rbp+40h]
0x18001b5ba  add     rsp, 20h
0x18001b5be  pop     rbp
0x18001b5bf  retn
0x18001b5c1  push    rbp
0x18001b5c3  sub     rsp, 20h
0x18001b5c7  mov     rbp, rdx
0x18001b5ca  mov     rax, [rcx]
0x18001b5cd  mov     edx, [rax]
0x18001b5cf  mov     [rbp+0B8h], rcx
0x18001b5d6  mov     [rbp+48h], edx
0x18001b5d9  mov     eax, [rbp+48h]
0x18001b5dc  cmp     eax, 0E06D7363h
0x18001b5e1  jnz     short loc_18001B5F7
0x18001b5e3  mov     rdx, [rbp+0B8h]
0x18001b5ea  mov     ecx, [rbp+48h]
0x18001b5ed  call    _XcptFilter_0
0x18001b5f2  mov     [rbp+50h], eax
0x18001b5f5  jmp     short loc_18001B5FE
0x18001b5f7  mov     dword ptr [rbp+50h], 0
0x18001b5fe  mov     eax, [rbp+50h]
0x18001b601  add     rsp, 20h
0x18001b605  pop     rbp
0x18001b606  retn
0x18001b608  push    rbp
0x18001b60a  sub     rsp, 20h
0x18001b60e  mov     rbp, rdx
0x18001b611  mov     rax, [rcx]
0x18001b614  mov     edx, [rax]
0x18001b616  mov     [rbp+0C0h], rcx
0x18001b61d  mov     [rbp+58h], edx
0x18001b620  mov     eax, [rbp+58h]
0x18001b623  cmp     eax, 0E06D7363h
0x18001b628  jnz     short loc_18001B63E
0x18001b62a  mov     rdx, [rbp+0C0h]
0x18001b631  mov     ecx, [rbp+58h]
0x18001b634  call    _XcptFilter_0
0x18001b639  mov     [rbp+60h], eax
0x18001b63c  jmp     short loc_18001B645
0x18001b63e  mov     dword ptr [rbp+60h], 0
0x18001b645  mov     eax, [rbp+60h]
0x18001b648  add     rsp, 20h
0x18001b64c  pop     rbp
0x18001b64d  retn
0x18001b64f  push    rbp
0x18001b651  sub     rsp, 20h
0x18001b655  mov     rbp, rdx
0x18001b658  mov     rax, [rcx]
0x18001b65b  mov     edx, [rax]
0x18001b65d  mov     [rbp+0C8h], rcx
0x18001b664  mov     [rbp+68h], edx
0x18001b667  mov     eax, [rbp+68h]
0x18001b66a  cmp     eax, 0E06D7363h
0x18001b66f  jnz     short loc_18001B685
0x18001b671  mov     rdx, [rbp+0C8h]
0x18001b678  mov     ecx, [rbp+68h]
0x18001b67b  call    _XcptFilter_0
0x18001b680  mov     [rbp+70h], eax
0x18001b683  jmp     short loc_18001B68C
0x18001b685  mov     dword ptr [rbp+70h], 0
0x18001b68c  mov     eax, [rbp+70h]
0x18001b68f  add     rsp, 20h
0x18001b693  pop     rbp
0x18001b694  retn
0x18001b696  push    rbp
0x18001b698  sub     rsp, 20h
0x18001b69c  mov     rbp, rdx
0x18001b69f  mov     rax, [rcx]
0x18001b6a2  mov     edx, [rax]
0x18001b6a4  mov     [rbp+0D0h], rcx
0x18001b6ab  mov     [rbp+78h], edx
0x18001b6ae  mov     eax, [rbp+78h]
0x18001b6b1  cmp     eax, 0E06D7363h
0x18001b6b6  jnz     short loc_18001B6CF
0x18001b6b8  mov     rdx, [rbp+0D0h]
0x18001b6bf  mov     ecx, [rbp+78h]
0x18001b6c2  call    _XcptFilter_0
0x18001b6c7  mov     [rbp+80h], eax
0x18001b6cd  jmp     short loc_18001B6D9
0x18001b6cf  mov     dword ptr [rbp+80h], 0
0x18001b6d9  mov     eax, [rbp+80h]
0x18001b6df  add     rsp, 20h
0x18001b6e3  pop     rbp
0x18001b6e4  retn
0x18001b6e6  push    rbp
0x18001b6e8  sub     rsp, 20h
0x18001b6ec  mov     rbp, rdx
0x18001b6ef  mov     rax, [rcx]
0x18001b6f2  mov     edx, [rax]
0x18001b6f4  mov     [rbp+0D8h], rcx
0x18001b6fb  mov     [rbp+88h], edx
0x18001b701  mov     eax, [rbp+88h]
0x18001b707  cmp     eax, 0E06D7363h
0x18001b70c  jnz     short loc_18001B728
0x18001b70e  mov     rdx, [rbp+0D8h]
0x18001b715  mov     ecx, [rbp+88h]
0x18001b71b  call    _XcptFilter_0
0x18001b720  mov     [rbp+90h], eax
0x18001b726  jmp     short loc_18001B732
0x18001b728  mov     dword ptr [rbp+90h], 0
0x18001b732  mov     eax, [rbp+90h]
0x18001b738  add     rsp, 20h
0x18001b73c  pop     rbp
0x18001b73d  retn
0x18001b73f  push    rbp
0x18001b741  sub     rsp, 20h
0x18001b745  mov     rbp, rdx
0x18001b748  mov     rax, [rcx]
0x18001b74b  mov     edx, [rax]
0x18001b74d  mov     [rbp+0E0h], rcx
0x18001b754  mov     [rbp+98h], edx
0x18001b75a  mov     eax, [rbp+98h]
0x18001b760  cmp     eax, 0E06D7363h
0x18001b765  jnz     short loc_18001B781
0x18001b767  mov     rdx, [rbp+0E0h]
0x18001b76e  mov     ecx, [rbp+98h]
0x18001b774  call    _XcptFilter_0
0x18001b779  mov     [rbp+0A0h], eax
0x18001b77f  jmp     short loc_18001B78B
0x18001b781  mov     dword ptr [rbp+0A0h], 0
0x18001b78b  mov     eax, [rbp+0A0h]
0x18001b791  add     rsp, 20h
0x18001b795  pop     rbp
0x18001b796  retn
0x18001b798  push    rbp
0x18001b79a  sub     rsp, 20h
0x18001b79e  mov     rbp, rdx
0x18001b7a1  cmp     dword ptr [rbp+118h], 1
0x18001b7a8  ja      short loc_18001B7B4
0x18001b7aa  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
