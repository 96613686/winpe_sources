# __DllMainCRTStartup

- ea: `0x180001ae4`
- end: `0x180001cf0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001aa0`

## callees

- `0x180001870`
- `0x180001ae4`
- `0x180001d1a`
- `0x180001ef8`
- `0x1800031a0`

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
  if ( (_DWORD)fdwReason || dword_1800070A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800070A4 = 1;
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
            if ( dword_1800070A4 )
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
0x180001ae4  mov     [rsp+lpvReserved], r8
0x180001ae9  mov     [rsp+arg_8], edx
0x180001aed  mov     [rsp+arg_0], rcx
0x180001af2  push    rbx
0x180001af3  push    rsi
0x180001af4  push    rdi
0x180001af5  sub     rsp, 0F0h
0x180001afc  mov     edi, edx
0x180001afe  mov     rsi, rcx
0x180001b01  mov     ebx, 1
0x180001b06  cmp     edx, ebx
0x180001b08  ja      short loc_180001B10
0x180001b0a  mov     cs:__native_dllmain_reason, edx
0x180001b10  test    edx, edx
0x180001b12  jnz     short loc_180001B27
0x180001b14  cmp     cs:dword_1800070A0, edx
0x180001b1a  jnz     short loc_180001B27
0x180001b1c  xor     ebx, ebx
0x180001b1e  mov     [rsp+108h+var_E8], ebx
0x180001b22  jmp     loc_180001CD4
0x180001b27  lea     eax, [rdx-1]
0x180001b2a  cmp     eax, 1
0x180001b2d  ja      loc_180001BB4
0x180001b33  mov     rax, cs:_pRawDllMain
0x180001b3a  test    rax, rax
0x180001b3d  jz      short loc_180001B75
0x180001b3f  cmp     edx, 1
0x180001b42  jnz     short loc_180001B4A
0x180001b44  mov     cs:dword_1800070A4, edx
0x180001b4a  mov     r8, [rsp+108h+lpvReserved]
0x180001b52  call    cs:__guard_dispatch_icall_fptr
0x180001b58  mov     ebx, eax
0x180001b5a  mov     [rsp+108h+var_E8], eax
0x180001b5e  jmp     short loc_180001B75
0x180001b60  xor     ebx, ebx
0x180001b62  mov     [rsp+108h+var_E8], ebx
0x180001b66  mov     edi, [rsp+108h+arg_8]
0x180001b6d  mov     rsi, [rsp+108h+arg_0]
0x180001b75  test    ebx, ebx
0x180001b77  jz      loc_180001CD4
0x180001b7d  mov     r8, [rsp+108h+lpvReserved]
0x180001b85  mov     edx, edi
0x180001b87  mov     rcx, rsi
0x180001b8a  call    _CRT_INIT
0x180001b8f  mov     ebx, eax
0x180001b91  mov     [rsp+108h+var_E8], eax
0x180001b95  jmp     short loc_180001BAC
0x180001b97  xor     ebx, ebx
0x180001b99  mov     [rsp+108h+var_E8], ebx
0x180001b9d  mov     edi, [rsp+108h+arg_8]
0x180001ba4  mov     rsi, [rsp+108h+arg_0]
0x180001bac  test    ebx, ebx
0x180001bae  jz      loc_180001CD4
0x180001bb4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001bbc  mov     edx, edi; fdwReason
0x180001bbe  mov     rcx, rsi; hinstDLL
0x180001bc1  call    DllMain
0x180001bc6  mov     ebx, eax
0x180001bc8  mov     [rsp+108h+var_E8], eax
0x180001bcc  jmp     short loc_180001BE3
0x180001bce  xor     ebx, ebx
0x180001bd0  mov     [rsp+108h+var_E8], ebx
0x180001bd4  mov     edi, [rsp+108h+arg_8]
0x180001bdb  mov     rsi, [rsp+108h+arg_0]
0x180001be3  cmp     edi, 1
0x180001be6  jnz     short loc_180001C5F
0x180001be8  test    ebx, ebx
0x180001bea  jnz     short loc_180001C5F
0x180001bec  xor     r8d, r8d; lpvReserved
0x180001bef  xor     edx, edx; fdwReason
0x180001bf1  mov     rcx, rsi; hinstDLL
0x180001bf4  call    DllMain
0x180001bf9  jmp     short loc_180001C0E
0x180001bfb  mov     edi, [rsp+108h+arg_8]
0x180001c02  mov     rsi, [rsp+108h+arg_0]
0x180001c0a  mov     ebx, [rsp+108h+var_E8]
0x180001c0e  xor     r8d, r8d
0x180001c11  xor     edx, edx
0x180001c13  mov     rcx, rsi
0x180001c16  call    _CRT_INIT
0x180001c1b  jmp     short loc_180001C30
0x180001c1d  mov     edi, [rsp+108h+arg_8]
0x180001c24  mov     rsi, [rsp+108h+arg_0]
0x180001c2c  mov     ebx, [rsp+108h+var_E8]
0x180001c30  mov     rax, cs:_pRawDllMain
0x180001c37  test    rax, rax
0x180001c3a  jz      short loc_180001C5F
0x180001c3c  xor     r8d, r8d
0x180001c3f  xor     edx, edx
0x180001c41  mov     rcx, rsi
0x180001c44  call    cs:__guard_dispatch_icall_fptr
0x180001c4a  jmp     short loc_180001C5F
0x180001c4c  mov     edi, [rsp+108h+arg_8]
0x180001c53  mov     rsi, [rsp+108h+arg_0]
0x180001c5b  mov     ebx, [rsp+108h+var_E8]
0x180001c5f  test    edi, edi
0x180001c61  jz      short loc_180001C68
0x180001c63  cmp     edi, 3
0x180001c66  jnz     short loc_180001CD4
0x180001c68  mov     r8, [rsp+108h+lpvReserved]
0x180001c70  mov     edx, edi
0x180001c72  mov     rcx, rsi
0x180001c75  call    _CRT_INIT
0x180001c7a  mov     ebx, eax
0x180001c7c  mov     [rsp+108h+var_E8], eax
0x180001c80  jmp     short loc_180001C97
0x180001c82  xor     ebx, ebx
0x180001c84  mov     [rsp+108h+var_E8], ebx
0x180001c88  mov     edi, [rsp+108h+arg_8]
0x180001c8f  mov     rsi, [rsp+108h+arg_0]
0x180001c97  mov     rax, cs:_pRawDllMain
0x180001c9e  test    rax, rax
0x180001ca1  jz      short loc_180001CD4
0x180001ca3  cmp     cs:dword_1800070A4, 0
0x180001caa  jz      short loc_180001CD4
0x180001cac  mov     r8, [rsp+108h+lpvReserved]
0x180001cb4  mov     edx, edi
0x180001cb6  mov     rcx, rsi
0x180001cb9  call    cs:__guard_dispatch_icall_fptr
0x180001cbf  mov     ebx, eax
0x180001cc1  mov     [rsp+108h+var_E8], eax
0x180001cc5  jmp     short loc_180001CD4
0x180001cc7  xor     ebx, ebx
0x180001cc9  mov     [rsp+108h+var_E8], ebx
0x180001ccd  mov     edi, [rsp+108h+arg_8]
0x180001cd4  cmp     edi, 1
0x180001cd7  ja      short loc_180001CE3
0x180001cd9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001ce3  mov     eax, ebx
0x180001ce5  add     rsp, 0F0h
0x180001cec  pop     rdi
0x180001ced  pop     rsi
0x180001cee  pop     rbx
0x180001cef  retn
0x180003210  push    rbp
0x180003212  sub     rsp, 20h
0x180003216  mov     rbp, rdx
0x180003219  mov     rax, [rcx]
0x18000321c  mov     edx, [rax]
0x18000321e  mov     [rbp+0A8h], rcx
0x180003225  mov     [rbp+28h], edx
0x180003228  mov     eax, [rbp+28h]
0x18000322b  cmp     eax, 0E06D7363h
0x180003230  jnz     short loc_180003246
0x180003232  mov     rdx, [rbp+0A8h]
0x180003239  mov     ecx, [rbp+28h]
0x18000323c  call    _XcptFilter_0
0x180003241  mov     [rbp+30h], eax
0x180003244  jmp     short loc_18000324D
0x180003246  mov     dword ptr [rbp+30h], 0
0x18000324d  mov     eax, [rbp+30h]
0x180003250  add     rsp, 20h
0x180003254  pop     rbp
0x180003255  retn
0x180003257  push    rbp
0x180003259  sub     rsp, 20h
0x18000325d  mov     rbp, rdx
0x180003260  mov     rax, [rcx]
0x180003263  mov     edx, [rax]
0x180003265  mov     [rbp+0B0h], rcx
0x18000326c  mov     [rbp+38h], edx
0x18000326f  mov     eax, [rbp+38h]
0x180003272  cmp     eax, 0E06D7363h
0x180003277  jnz     short loc_18000328D
0x180003279  mov     rdx, [rbp+0B0h]
0x180003280  mov     ecx, [rbp+38h]
0x180003283  call    _XcptFilter_0
0x180003288  mov     [rbp+40h], eax
0x18000328b  jmp     short loc_180003294
0x18000328d  mov     dword ptr [rbp+40h], 0
0x180003294  mov     eax, [rbp+40h]
0x180003297  add     rsp, 20h
0x18000329b  pop     rbp
0x18000329c  retn
0x18000329e  push    rbp
0x1800032a0  sub     rsp, 20h
0x1800032a4  mov     rbp, rdx
0x1800032a7  mov     rax, [rcx]
0x1800032aa  mov     edx, [rax]
0x1800032ac  mov     [rbp+0B8h], rcx
0x1800032b3  mov     [rbp+48h], edx
0x1800032b6  mov     eax, [rbp+48h]
0x1800032b9  cmp     eax, 0E06D7363h
0x1800032be  jnz     short loc_1800032D4
0x1800032c0  mov     rdx, [rbp+0B8h]
0x1800032c7  mov     ecx, [rbp+48h]
0x1800032ca  call    _XcptFilter_0
0x1800032cf  mov     [rbp+50h], eax
0x1800032d2  jmp     short loc_1800032DB
0x1800032d4  mov     dword ptr [rbp+50h], 0
0x1800032db  mov     eax, [rbp+50h]
0x1800032de  add     rsp, 20h
0x1800032e2  pop     rbp
0x1800032e3  retn
0x1800032e5  push    rbp
0x1800032e7  sub     rsp, 20h
0x1800032eb  mov     rbp, rdx
0x1800032ee  mov     rax, [rcx]
0x1800032f1  mov     edx, [rax]
0x1800032f3  mov     [rbp+0C0h], rcx
0x1800032fa  mov     [rbp+58h], edx
0x1800032fd  mov     eax, [rbp+58h]
0x180003300  cmp     eax, 0E06D7363h
0x180003305  jnz     short loc_18000331B
0x180003307  mov     rdx, [rbp+0C0h]
0x18000330e  mov     ecx, [rbp+58h]
0x180003311  call    _XcptFilter_0
0x180003316  mov     [rbp+60h], eax
0x180003319  jmp     short loc_180003322
0x18000331b  mov     dword ptr [rbp+60h], 0
0x180003322  mov     eax, [rbp+60h]
0x180003325  add     rsp, 20h
0x180003329  pop     rbp
0x18000332a  retn
0x18000332c  push    rbp
0x18000332e  sub     rsp, 20h
0x180003332  mov     rbp, rdx
0x180003335  mov     rax, [rcx]
0x180003338  mov     edx, [rax]
0x18000333a  mov     [rbp+0C8h], rcx
0x180003341  mov     [rbp+68h], edx
0x180003344  mov     eax, [rbp+68h]
0x180003347  cmp     eax, 0E06D7363h
0x18000334c  jnz     short loc_180003362
0x18000334e  mov     rdx, [rbp+0C8h]
0x180003355  mov     ecx, [rbp+68h]
0x180003358  call    _XcptFilter_0
0x18000335d  mov     [rbp+70h], eax
0x180003360  jmp     short loc_180003369
0x180003362  mov     dword ptr [rbp+70h], 0
0x180003369  mov     eax, [rbp+70h]
0x18000336c  add     rsp, 20h
0x180003370  pop     rbp
0x180003371  retn
0x180003373  push    rbp
0x180003375  sub     rsp, 20h
0x180003379  mov     rbp, rdx
0x18000337c  mov     rax, [rcx]
0x18000337f  mov     edx, [rax]
0x180003381  mov     [rbp+0D0h], rcx
0x180003388  mov     [rbp+78h], edx
0x18000338b  mov     eax, [rbp+78h]
0x18000338e  cmp     eax, 0E06D7363h
0x180003393  jnz     short loc_1800033AC
0x180003395  mov     rdx, [rbp+0D0h]
0x18000339c  mov     ecx, [rbp+78h]
0x18000339f  call    _XcptFilter_0
0x1800033a4  mov     [rbp+80h], eax
0x1800033aa  jmp     short loc_1800033B6
0x1800033ac  mov     dword ptr [rbp+80h], 0
0x1800033b6  mov     eax, [rbp+80h]
0x1800033bc  add     rsp, 20h
0x1800033c0  pop     rbp
0x1800033c1  retn
0x1800033c3  push    rbp
0x1800033c5  sub     rsp, 20h
0x1800033c9  mov     rbp, rdx
0x1800033cc  mov     rax, [rcx]
0x1800033cf  mov     edx, [rax]
0x1800033d1  mov     [rbp+0D8h], rcx
0x1800033d8  mov     [rbp+88h], edx
0x1800033de  mov     eax, [rbp+88h]
0x1800033e4  cmp     eax, 0E06D7363h
0x1800033e9  jnz     short loc_180003405
0x1800033eb  mov     rdx, [rbp+0D8h]
0x1800033f2  mov     ecx, [rbp+88h]
0x1800033f8  call    _XcptFilter_0
0x1800033fd  mov     [rbp+90h], eax
0x180003403  jmp     short loc_18000340F
0x180003405  mov     dword ptr [rbp+90h], 0
0x18000340f  mov     eax, [rbp+90h]
0x180003415  add     rsp, 20h
0x180003419  pop     rbp
0x18000341a  retn
0x18000341c  push    rbp
0x18000341e  sub     rsp, 20h
0x180003422  mov     rbp, rdx
0x180003425  mov     rax, [rcx]
0x180003428  mov     edx, [rax]
0x18000342a  mov     [rbp+0E0h], rcx
0x180003431  mov     [rbp+98h], edx
0x180003437  mov     eax, [rbp+98h]
0x18000343d  cmp     eax, 0E06D7363h
0x180003442  jnz     short loc_18000345E
0x180003444  mov     rdx, [rbp+0E0h]
0x18000344b  mov     ecx, [rbp+98h]
0x180003451  call    _XcptFilter_0
0x180003456  mov     [rbp+0A0h], eax
0x18000345c  jmp     short loc_180003468
0x18000345e  mov     dword ptr [rbp+0A0h], 0
0x180003468  mov     eax, [rbp+0A0h]
0x18000346e  add     rsp, 20h
0x180003472  pop     rbp
0x180003473  retn
0x180003475  push    rbp
0x180003477  sub     rsp, 20h
0x18000347b  mov     rbp, rdx
0x18000347e  cmp     dword ptr [rbp+118h], 1
0x180003485  ja      short loc_180003491
0x180003487  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
