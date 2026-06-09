# __DllMainCRTStartup

- ea: `0x180003874`
- end: `0x180003a80`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180003830`

## callees

- `0x180003600`
- `0x180003874`
- `0x180003fb6`
- `0x1800190e4`
- `0x18001a280`

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
  if ( (_DWORD)fdwReason || dword_180027E6C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180027E70 = 1;
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
            if ( dword_180027E70 )
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
0x180003874  mov     [rsp+lpvReserved], r8
0x180003879  mov     [rsp+arg_8], edx
0x18000387d  mov     [rsp+arg_0], rcx
0x180003882  push    rbx
0x180003883  push    rsi
0x180003884  push    rdi
0x180003885  sub     rsp, 0F0h
0x18000388c  mov     edi, edx
0x18000388e  mov     rsi, rcx
0x180003891  mov     ebx, 1
0x180003896  cmp     edx, ebx
0x180003898  ja      short loc_1800038A0
0x18000389a  mov     cs:__native_dllmain_reason, edx
0x1800038a0  test    edx, edx
0x1800038a2  jnz     short loc_1800038B7
0x1800038a4  cmp     cs:dword_180027E6C, edx
0x1800038aa  jnz     short loc_1800038B7
0x1800038ac  xor     ebx, ebx
0x1800038ae  mov     [rsp+108h+var_E8], ebx
0x1800038b2  jmp     loc_180003A64
0x1800038b7  lea     eax, [rdx-1]
0x1800038ba  cmp     eax, 1
0x1800038bd  ja      loc_180003944
0x1800038c3  mov     rax, cs:_pRawDllMain
0x1800038ca  test    rax, rax
0x1800038cd  jz      short loc_180003905
0x1800038cf  cmp     edx, 1
0x1800038d2  jnz     short loc_1800038DA
0x1800038d4  mov     cs:dword_180027E70, edx
0x1800038da  mov     r8, [rsp+108h+lpvReserved]
0x1800038e2  call    cs:__guard_dispatch_icall_fptr
0x1800038e8  mov     ebx, eax
0x1800038ea  mov     [rsp+108h+var_E8], eax
0x1800038ee  jmp     short loc_180003905
0x1800038f0  xor     ebx, ebx
0x1800038f2  mov     [rsp+108h+var_E8], ebx
0x1800038f6  mov     edi, [rsp+108h+arg_8]
0x1800038fd  mov     rsi, [rsp+108h+arg_0]
0x180003905  test    ebx, ebx
0x180003907  jz      loc_180003A64
0x18000390d  mov     r8, [rsp+108h+lpvReserved]
0x180003915  mov     edx, edi
0x180003917  mov     rcx, rsi
0x18000391a  call    _CRT_INIT
0x18000391f  mov     ebx, eax
0x180003921  mov     [rsp+108h+var_E8], eax
0x180003925  jmp     short loc_18000393C
0x180003927  xor     ebx, ebx
0x180003929  mov     [rsp+108h+var_E8], ebx
0x18000392d  mov     edi, [rsp+108h+arg_8]
0x180003934  mov     rsi, [rsp+108h+arg_0]
0x18000393c  test    ebx, ebx
0x18000393e  jz      loc_180003A64
0x180003944  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000394c  mov     edx, edi; fdwReason
0x18000394e  mov     rcx, rsi; hinstDLL
0x180003951  call    DllMain
0x180003956  mov     ebx, eax
0x180003958  mov     [rsp+108h+var_E8], eax
0x18000395c  jmp     short loc_180003973
0x18000395e  xor     ebx, ebx
0x180003960  mov     [rsp+108h+var_E8], ebx
0x180003964  mov     edi, [rsp+108h+arg_8]
0x18000396b  mov     rsi, [rsp+108h+arg_0]
0x180003973  cmp     edi, 1
0x180003976  jnz     short loc_1800039EF
0x180003978  test    ebx, ebx
0x18000397a  jnz     short loc_1800039EF
0x18000397c  xor     r8d, r8d; lpvReserved
0x18000397f  xor     edx, edx; fdwReason
0x180003981  mov     rcx, rsi; hinstDLL
0x180003984  call    DllMain
0x180003989  jmp     short loc_18000399E
0x18000398b  mov     edi, [rsp+108h+arg_8]
0x180003992  mov     rsi, [rsp+108h+arg_0]
0x18000399a  mov     ebx, [rsp+108h+var_E8]
0x18000399e  xor     r8d, r8d
0x1800039a1  xor     edx, edx
0x1800039a3  mov     rcx, rsi
0x1800039a6  call    _CRT_INIT
0x1800039ab  jmp     short loc_1800039C0
0x1800039ad  mov     edi, [rsp+108h+arg_8]
0x1800039b4  mov     rsi, [rsp+108h+arg_0]
0x1800039bc  mov     ebx, [rsp+108h+var_E8]
0x1800039c0  mov     rax, cs:_pRawDllMain
0x1800039c7  test    rax, rax
0x1800039ca  jz      short loc_1800039EF
0x1800039cc  xor     r8d, r8d
0x1800039cf  xor     edx, edx
0x1800039d1  mov     rcx, rsi
0x1800039d4  call    cs:__guard_dispatch_icall_fptr
0x1800039da  jmp     short loc_1800039EF
0x1800039dc  mov     edi, [rsp+108h+arg_8]
0x1800039e3  mov     rsi, [rsp+108h+arg_0]
0x1800039eb  mov     ebx, [rsp+108h+var_E8]
0x1800039ef  test    edi, edi
0x1800039f1  jz      short loc_1800039F8
0x1800039f3  cmp     edi, 3
0x1800039f6  jnz     short loc_180003A64
0x1800039f8  mov     r8, [rsp+108h+lpvReserved]
0x180003a00  mov     edx, edi
0x180003a02  mov     rcx, rsi
0x180003a05  call    _CRT_INIT
0x180003a0a  mov     ebx, eax
0x180003a0c  mov     [rsp+108h+var_E8], eax
0x180003a10  jmp     short loc_180003A27
0x180003a12  xor     ebx, ebx
0x180003a14  mov     [rsp+108h+var_E8], ebx
0x180003a18  mov     edi, [rsp+108h+arg_8]
0x180003a1f  mov     rsi, [rsp+108h+arg_0]
0x180003a27  mov     rax, cs:_pRawDllMain
0x180003a2e  test    rax, rax
0x180003a31  jz      short loc_180003A64
0x180003a33  cmp     cs:dword_180027E70, 0
0x180003a3a  jz      short loc_180003A64
0x180003a3c  mov     r8, [rsp+108h+lpvReserved]
0x180003a44  mov     edx, edi
0x180003a46  mov     rcx, rsi
0x180003a49  call    cs:__guard_dispatch_icall_fptr
0x180003a4f  mov     ebx, eax
0x180003a51  mov     [rsp+108h+var_E8], eax
0x180003a55  jmp     short loc_180003A64
0x180003a57  xor     ebx, ebx
0x180003a59  mov     [rsp+108h+var_E8], ebx
0x180003a5d  mov     edi, [rsp+108h+arg_8]
0x180003a64  cmp     edi, 1
0x180003a67  ja      short loc_180003A73
0x180003a69  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180003a73  mov     eax, ebx
0x180003a75  add     rsp, 0F0h
0x180003a7c  pop     rdi
0x180003a7d  pop     rsi
0x180003a7e  pop     rbx
0x180003a7f  retn
0x18001a392  push    rbp
0x18001a394  sub     rsp, 20h
0x18001a398  mov     rbp, rdx
0x18001a39b  mov     rax, [rcx]
0x18001a39e  mov     edx, [rax]
0x18001a3a0  mov     [rbp+0A8h], rcx
0x18001a3a7  mov     [rbp+28h], edx
0x18001a3aa  mov     eax, [rbp+28h]
0x18001a3ad  cmp     eax, 0E06D7363h
0x18001a3b2  jnz     short loc_18001A3C8
0x18001a3b4  mov     rdx, [rbp+0A8h]
0x18001a3bb  mov     ecx, [rbp+28h]
0x18001a3be  call    _XcptFilter_0
0x18001a3c3  mov     [rbp+30h], eax
0x18001a3c6  jmp     short loc_18001A3CF
0x18001a3c8  mov     dword ptr [rbp+30h], 0
0x18001a3cf  mov     eax, [rbp+30h]
0x18001a3d2  add     rsp, 20h
0x18001a3d6  pop     rbp
0x18001a3d7  retn
0x18001a3d9  push    rbp
0x18001a3db  sub     rsp, 20h
0x18001a3df  mov     rbp, rdx
0x18001a3e2  mov     rax, [rcx]
0x18001a3e5  mov     edx, [rax]
0x18001a3e7  mov     [rbp+0B0h], rcx
0x18001a3ee  mov     [rbp+38h], edx
0x18001a3f1  mov     eax, [rbp+38h]
0x18001a3f4  cmp     eax, 0E06D7363h
0x18001a3f9  jnz     short loc_18001A40F
0x18001a3fb  mov     rdx, [rbp+0B0h]
0x18001a402  mov     ecx, [rbp+38h]
0x18001a405  call    _XcptFilter_0
0x18001a40a  mov     [rbp+40h], eax
0x18001a40d  jmp     short loc_18001A416
0x18001a40f  mov     dword ptr [rbp+40h], 0
0x18001a416  mov     eax, [rbp+40h]
0x18001a419  add     rsp, 20h
0x18001a41d  pop     rbp
0x18001a41e  retn
0x18001a420  push    rbp
0x18001a422  sub     rsp, 20h
0x18001a426  mov     rbp, rdx
0x18001a429  mov     rax, [rcx]
0x18001a42c  mov     edx, [rax]
0x18001a42e  mov     [rbp+0B8h], rcx
0x18001a435  mov     [rbp+48h], edx
0x18001a438  mov     eax, [rbp+48h]
0x18001a43b  cmp     eax, 0E06D7363h
0x18001a440  jnz     short loc_18001A456
0x18001a442  mov     rdx, [rbp+0B8h]
0x18001a449  mov     ecx, [rbp+48h]
0x18001a44c  call    _XcptFilter_0
0x18001a451  mov     [rbp+50h], eax
0x18001a454  jmp     short loc_18001A45D
0x18001a456  mov     dword ptr [rbp+50h], 0
0x18001a45d  mov     eax, [rbp+50h]
0x18001a460  add     rsp, 20h
0x18001a464  pop     rbp
0x18001a465  retn
0x18001a467  push    rbp
0x18001a469  sub     rsp, 20h
0x18001a46d  mov     rbp, rdx
0x18001a470  mov     rax, [rcx]
0x18001a473  mov     edx, [rax]
0x18001a475  mov     [rbp+0C0h], rcx
0x18001a47c  mov     [rbp+58h], edx
0x18001a47f  mov     eax, [rbp+58h]
0x18001a482  cmp     eax, 0E06D7363h
0x18001a487  jnz     short loc_18001A49D
0x18001a489  mov     rdx, [rbp+0C0h]
0x18001a490  mov     ecx, [rbp+58h]
0x18001a493  call    _XcptFilter_0
0x18001a498  mov     [rbp+60h], eax
0x18001a49b  jmp     short loc_18001A4A4
0x18001a49d  mov     dword ptr [rbp+60h], 0
0x18001a4a4  mov     eax, [rbp+60h]
0x18001a4a7  add     rsp, 20h
0x18001a4ab  pop     rbp
0x18001a4ac  retn
0x18001a4ae  push    rbp
0x18001a4b0  sub     rsp, 20h
0x18001a4b4  mov     rbp, rdx
0x18001a4b7  mov     rax, [rcx]
0x18001a4ba  mov     edx, [rax]
0x18001a4bc  mov     [rbp+0C8h], rcx
0x18001a4c3  mov     [rbp+68h], edx
0x18001a4c6  mov     eax, [rbp+68h]
0x18001a4c9  cmp     eax, 0E06D7363h
0x18001a4ce  jnz     short loc_18001A4E4
0x18001a4d0  mov     rdx, [rbp+0C8h]
0x18001a4d7  mov     ecx, [rbp+68h]
0x18001a4da  call    _XcptFilter_0
0x18001a4df  mov     [rbp+70h], eax
0x18001a4e2  jmp     short loc_18001A4EB
0x18001a4e4  mov     dword ptr [rbp+70h], 0
0x18001a4eb  mov     eax, [rbp+70h]
0x18001a4ee  add     rsp, 20h
0x18001a4f2  pop     rbp
0x18001a4f3  retn
0x18001a4f5  push    rbp
0x18001a4f7  sub     rsp, 20h
0x18001a4fb  mov     rbp, rdx
0x18001a4fe  mov     rax, [rcx]
0x18001a501  mov     edx, [rax]
0x18001a503  mov     [rbp+0D0h], rcx
0x18001a50a  mov     [rbp+78h], edx
0x18001a50d  mov     eax, [rbp+78h]
0x18001a510  cmp     eax, 0E06D7363h
0x18001a515  jnz     short loc_18001A52E
0x18001a517  mov     rdx, [rbp+0D0h]
0x18001a51e  mov     ecx, [rbp+78h]
0x18001a521  call    _XcptFilter_0
0x18001a526  mov     [rbp+80h], eax
0x18001a52c  jmp     short loc_18001A538
0x18001a52e  mov     dword ptr [rbp+80h], 0
0x18001a538  mov     eax, [rbp+80h]
0x18001a53e  add     rsp, 20h
0x18001a542  pop     rbp
0x18001a543  retn
0x18001a545  push    rbp
0x18001a547  sub     rsp, 20h
0x18001a54b  mov     rbp, rdx
0x18001a54e  mov     rax, [rcx]
0x18001a551  mov     edx, [rax]
0x18001a553  mov     [rbp+0D8h], rcx
0x18001a55a  mov     [rbp+88h], edx
0x18001a560  mov     eax, [rbp+88h]
0x18001a566  cmp     eax, 0E06D7363h
0x18001a56b  jnz     short loc_18001A587
0x18001a56d  mov     rdx, [rbp+0D8h]
0x18001a574  mov     ecx, [rbp+88h]
0x18001a57a  call    _XcptFilter_0
0x18001a57f  mov     [rbp+90h], eax
0x18001a585  jmp     short loc_18001A591
0x18001a587  mov     dword ptr [rbp+90h], 0
0x18001a591  mov     eax, [rbp+90h]
0x18001a597  add     rsp, 20h
0x18001a59b  pop     rbp
0x18001a59c  retn
0x18001a59e  push    rbp
0x18001a5a0  sub     rsp, 20h
0x18001a5a4  mov     rbp, rdx
0x18001a5a7  mov     rax, [rcx]
0x18001a5aa  mov     edx, [rax]
0x18001a5ac  mov     [rbp+0E0h], rcx
0x18001a5b3  mov     [rbp+98h], edx
0x18001a5b9  mov     eax, [rbp+98h]
0x18001a5bf  cmp     eax, 0E06D7363h
0x18001a5c4  jnz     short loc_18001A5E0
0x18001a5c6  mov     rdx, [rbp+0E0h]
0x18001a5cd  mov     ecx, [rbp+98h]
0x18001a5d3  call    _XcptFilter_0
0x18001a5d8  mov     [rbp+0A0h], eax
0x18001a5de  jmp     short loc_18001A5EA
0x18001a5e0  mov     dword ptr [rbp+0A0h], 0
0x18001a5ea  mov     eax, [rbp+0A0h]
0x18001a5f0  add     rsp, 20h
0x18001a5f4  pop     rbp
0x18001a5f5  retn
0x18001a5f7  push    rbp
0x18001a5f9  sub     rsp, 20h
0x18001a5fd  mov     rbp, rdx
0x18001a600  cmp     dword ptr [rbp+118h], 1
0x18001a607  ja      short loc_18001A613
0x18001a609  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
