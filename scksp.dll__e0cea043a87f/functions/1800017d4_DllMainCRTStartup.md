# __DllMainCRTStartup

- ea: `0x1800017d4`
- end: `0x1800019e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001790`

## callees

- `0x180001560`
- `0x1800017d4`
- `0x180001e52`
- `0x180009f20`
- `0x18003c280`

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
  if ( (_DWORD)fdwReason || dword_18004B600 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18004B604 = 1;
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
            if ( dword_18004B604 )
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
0x1800017d4  mov     [rsp+lpvReserved], r8
0x1800017d9  mov     [rsp+arg_8], edx
0x1800017dd  mov     [rsp+arg_0], rcx
0x1800017e2  push    rbx
0x1800017e3  push    rsi
0x1800017e4  push    rdi
0x1800017e5  sub     rsp, 0F0h
0x1800017ec  mov     edi, edx
0x1800017ee  mov     rsi, rcx
0x1800017f1  mov     ebx, 1
0x1800017f6  cmp     edx, ebx
0x1800017f8  ja      short loc_180001800
0x1800017fa  mov     cs:__native_dllmain_reason, edx
0x180001800  test    edx, edx
0x180001802  jnz     short loc_180001817
0x180001804  cmp     cs:dword_18004B600, edx
0x18000180a  jnz     short loc_180001817
0x18000180c  xor     ebx, ebx
0x18000180e  mov     [rsp+108h+var_E8], ebx
0x180001812  jmp     loc_1800019C4
0x180001817  lea     eax, [rdx-1]
0x18000181a  cmp     eax, 1
0x18000181d  ja      loc_1800018A4
0x180001823  mov     rax, cs:_pRawDllMain
0x18000182a  test    rax, rax
0x18000182d  jz      short loc_180001865
0x18000182f  cmp     edx, 1
0x180001832  jnz     short loc_18000183A
0x180001834  mov     cs:dword_18004B604, edx
0x18000183a  mov     r8, [rsp+108h+lpvReserved]
0x180001842  call    cs:__guard_dispatch_icall_fptr
0x180001848  mov     ebx, eax
0x18000184a  mov     [rsp+108h+var_E8], eax
0x18000184e  jmp     short loc_180001865
0x180001850  xor     ebx, ebx
0x180001852  mov     [rsp+108h+var_E8], ebx
0x180001856  mov     edi, [rsp+108h+arg_8]
0x18000185d  mov     rsi, [rsp+108h+arg_0]
0x180001865  test    ebx, ebx
0x180001867  jz      loc_1800019C4
0x18000186d  mov     r8, [rsp+108h+lpvReserved]
0x180001875  mov     edx, edi
0x180001877  mov     rcx, rsi
0x18000187a  call    _CRT_INIT
0x18000187f  mov     ebx, eax
0x180001881  mov     [rsp+108h+var_E8], eax
0x180001885  jmp     short loc_18000189C
0x180001887  xor     ebx, ebx
0x180001889  mov     [rsp+108h+var_E8], ebx
0x18000188d  mov     edi, [rsp+108h+arg_8]
0x180001894  mov     rsi, [rsp+108h+arg_0]
0x18000189c  test    ebx, ebx
0x18000189e  jz      loc_1800019C4
0x1800018a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800018ac  mov     edx, edi; fdwReason
0x1800018ae  mov     rcx, rsi; hinstDLL
0x1800018b1  call    DllMain
0x1800018b6  mov     ebx, eax
0x1800018b8  mov     [rsp+108h+var_E8], eax
0x1800018bc  jmp     short loc_1800018D3
0x1800018be  xor     ebx, ebx
0x1800018c0  mov     [rsp+108h+var_E8], ebx
0x1800018c4  mov     edi, [rsp+108h+arg_8]
0x1800018cb  mov     rsi, [rsp+108h+arg_0]
0x1800018d3  cmp     edi, 1
0x1800018d6  jnz     short loc_18000194F
0x1800018d8  test    ebx, ebx
0x1800018da  jnz     short loc_18000194F
0x1800018dc  xor     r8d, r8d; lpvReserved
0x1800018df  xor     edx, edx; fdwReason
0x1800018e1  mov     rcx, rsi; hinstDLL
0x1800018e4  call    DllMain
0x1800018e9  jmp     short loc_1800018FE
0x1800018eb  mov     edi, [rsp+108h+arg_8]
0x1800018f2  mov     rsi, [rsp+108h+arg_0]
0x1800018fa  mov     ebx, [rsp+108h+var_E8]
0x1800018fe  xor     r8d, r8d
0x180001901  xor     edx, edx
0x180001903  mov     rcx, rsi
0x180001906  call    _CRT_INIT
0x18000190b  jmp     short loc_180001920
0x18000190d  mov     edi, [rsp+108h+arg_8]
0x180001914  mov     rsi, [rsp+108h+arg_0]
0x18000191c  mov     ebx, [rsp+108h+var_E8]
0x180001920  mov     rax, cs:_pRawDllMain
0x180001927  test    rax, rax
0x18000192a  jz      short loc_18000194F
0x18000192c  xor     r8d, r8d
0x18000192f  xor     edx, edx
0x180001931  mov     rcx, rsi
0x180001934  call    cs:__guard_dispatch_icall_fptr
0x18000193a  jmp     short loc_18000194F
0x18000193c  mov     edi, [rsp+108h+arg_8]
0x180001943  mov     rsi, [rsp+108h+arg_0]
0x18000194b  mov     ebx, [rsp+108h+var_E8]
0x18000194f  test    edi, edi
0x180001951  jz      short loc_180001958
0x180001953  cmp     edi, 3
0x180001956  jnz     short loc_1800019C4
0x180001958  mov     r8, [rsp+108h+lpvReserved]
0x180001960  mov     edx, edi
0x180001962  mov     rcx, rsi
0x180001965  call    _CRT_INIT
0x18000196a  mov     ebx, eax
0x18000196c  mov     [rsp+108h+var_E8], eax
0x180001970  jmp     short loc_180001987
0x180001972  xor     ebx, ebx
0x180001974  mov     [rsp+108h+var_E8], ebx
0x180001978  mov     edi, [rsp+108h+arg_8]
0x18000197f  mov     rsi, [rsp+108h+arg_0]
0x180001987  mov     rax, cs:_pRawDllMain
0x18000198e  test    rax, rax
0x180001991  jz      short loc_1800019C4
0x180001993  cmp     cs:dword_18004B604, 0
0x18000199a  jz      short loc_1800019C4
0x18000199c  mov     r8, [rsp+108h+lpvReserved]
0x1800019a4  mov     edx, edi
0x1800019a6  mov     rcx, rsi
0x1800019a9  call    cs:__guard_dispatch_icall_fptr
0x1800019af  mov     ebx, eax
0x1800019b1  mov     [rsp+108h+var_E8], eax
0x1800019b5  jmp     short loc_1800019C4
0x1800019b7  xor     ebx, ebx
0x1800019b9  mov     [rsp+108h+var_E8], ebx
0x1800019bd  mov     edi, [rsp+108h+arg_8]
0x1800019c4  cmp     edi, 1
0x1800019c7  ja      short loc_1800019D3
0x1800019c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800019d3  mov     eax, ebx
0x1800019d5  add     rsp, 0F0h
0x1800019dc  pop     rdi
0x1800019dd  pop     rsi
0x1800019de  pop     rbx
0x1800019df  retn
0x18003c353  push    rbp
0x18003c355  sub     rsp, 20h
0x18003c359  mov     rbp, rdx
0x18003c35c  mov     rax, [rcx]
0x18003c35f  mov     edx, [rax]
0x18003c361  mov     [rbp+0A8h], rcx
0x18003c368  mov     [rbp+28h], edx
0x18003c36b  mov     eax, [rbp+28h]
0x18003c36e  cmp     eax, 0E06D7363h
0x18003c373  jnz     short loc_18003C389
0x18003c375  mov     rdx, [rbp+0A8h]
0x18003c37c  mov     ecx, [rbp+28h]
0x18003c37f  call    _XcptFilter_0
0x18003c384  mov     [rbp+30h], eax
0x18003c387  jmp     short loc_18003C390
0x18003c389  mov     dword ptr [rbp+30h], 0
0x18003c390  mov     eax, [rbp+30h]
0x18003c393  add     rsp, 20h
0x18003c397  pop     rbp
0x18003c398  retn
0x18003c39a  push    rbp
0x18003c39c  sub     rsp, 20h
0x18003c3a0  mov     rbp, rdx
0x18003c3a3  mov     rax, [rcx]
0x18003c3a6  mov     edx, [rax]
0x18003c3a8  mov     [rbp+0B0h], rcx
0x18003c3af  mov     [rbp+38h], edx
0x18003c3b2  mov     eax, [rbp+38h]
0x18003c3b5  cmp     eax, 0E06D7363h
0x18003c3ba  jnz     short loc_18003C3D0
0x18003c3bc  mov     rdx, [rbp+0B0h]
0x18003c3c3  mov     ecx, [rbp+38h]
0x18003c3c6  call    _XcptFilter_0
0x18003c3cb  mov     [rbp+40h], eax
0x18003c3ce  jmp     short loc_18003C3D7
0x18003c3d0  mov     dword ptr [rbp+40h], 0
0x18003c3d7  mov     eax, [rbp+40h]
0x18003c3da  add     rsp, 20h
0x18003c3de  pop     rbp
0x18003c3df  retn
0x18003c3e1  push    rbp
0x18003c3e3  sub     rsp, 20h
0x18003c3e7  mov     rbp, rdx
0x18003c3ea  mov     rax, [rcx]
0x18003c3ed  mov     edx, [rax]
0x18003c3ef  mov     [rbp+0B8h], rcx
0x18003c3f6  mov     [rbp+48h], edx
0x18003c3f9  mov     eax, [rbp+48h]
0x18003c3fc  cmp     eax, 0E06D7363h
0x18003c401  jnz     short loc_18003C417
0x18003c403  mov     rdx, [rbp+0B8h]
0x18003c40a  mov     ecx, [rbp+48h]
0x18003c40d  call    _XcptFilter_0
0x18003c412  mov     [rbp+50h], eax
0x18003c415  jmp     short loc_18003C41E
0x18003c417  mov     dword ptr [rbp+50h], 0
0x18003c41e  mov     eax, [rbp+50h]
0x18003c421  add     rsp, 20h
0x18003c425  pop     rbp
0x18003c426  retn
0x18003c428  push    rbp
0x18003c42a  sub     rsp, 20h
0x18003c42e  mov     rbp, rdx
0x18003c431  mov     rax, [rcx]
0x18003c434  mov     edx, [rax]
0x18003c436  mov     [rbp+0C0h], rcx
0x18003c43d  mov     [rbp+58h], edx
0x18003c440  mov     eax, [rbp+58h]
0x18003c443  cmp     eax, 0E06D7363h
0x18003c448  jnz     short loc_18003C45E
0x18003c44a  mov     rdx, [rbp+0C0h]
0x18003c451  mov     ecx, [rbp+58h]
0x18003c454  call    _XcptFilter_0
0x18003c459  mov     [rbp+60h], eax
0x18003c45c  jmp     short loc_18003C465
0x18003c45e  mov     dword ptr [rbp+60h], 0
0x18003c465  mov     eax, [rbp+60h]
0x18003c468  add     rsp, 20h
0x18003c46c  pop     rbp
0x18003c46d  retn
0x18003c46f  push    rbp
0x18003c471  sub     rsp, 20h
0x18003c475  mov     rbp, rdx
0x18003c478  mov     rax, [rcx]
0x18003c47b  mov     edx, [rax]
0x18003c47d  mov     [rbp+0C8h], rcx
0x18003c484  mov     [rbp+68h], edx
0x18003c487  mov     eax, [rbp+68h]
0x18003c48a  cmp     eax, 0E06D7363h
0x18003c48f  jnz     short loc_18003C4A5
0x18003c491  mov     rdx, [rbp+0C8h]
0x18003c498  mov     ecx, [rbp+68h]
0x18003c49b  call    _XcptFilter_0
0x18003c4a0  mov     [rbp+70h], eax
0x18003c4a3  jmp     short loc_18003C4AC
0x18003c4a5  mov     dword ptr [rbp+70h], 0
0x18003c4ac  mov     eax, [rbp+70h]
0x18003c4af  add     rsp, 20h
0x18003c4b3  pop     rbp
0x18003c4b4  retn
0x18003c4b6  push    rbp
0x18003c4b8  sub     rsp, 20h
0x18003c4bc  mov     rbp, rdx
0x18003c4bf  mov     rax, [rcx]
0x18003c4c2  mov     edx, [rax]
0x18003c4c4  mov     [rbp+0D0h], rcx
0x18003c4cb  mov     [rbp+78h], edx
0x18003c4ce  mov     eax, [rbp+78h]
0x18003c4d1  cmp     eax, 0E06D7363h
0x18003c4d6  jnz     short loc_18003C4EF
0x18003c4d8  mov     rdx, [rbp+0D0h]
0x18003c4df  mov     ecx, [rbp+78h]
0x18003c4e2  call    _XcptFilter_0
0x18003c4e7  mov     [rbp+80h], eax
0x18003c4ed  jmp     short loc_18003C4F9
0x18003c4ef  mov     dword ptr [rbp+80h], 0
0x18003c4f9  mov     eax, [rbp+80h]
0x18003c4ff  add     rsp, 20h
0x18003c503  pop     rbp
0x18003c504  retn
0x18003c506  push    rbp
0x18003c508  sub     rsp, 20h
0x18003c50c  mov     rbp, rdx
0x18003c50f  mov     rax, [rcx]
0x18003c512  mov     edx, [rax]
0x18003c514  mov     [rbp+0D8h], rcx
0x18003c51b  mov     [rbp+88h], edx
0x18003c521  mov     eax, [rbp+88h]
0x18003c527  cmp     eax, 0E06D7363h
0x18003c52c  jnz     short loc_18003C548
0x18003c52e  mov     rdx, [rbp+0D8h]
0x18003c535  mov     ecx, [rbp+88h]
0x18003c53b  call    _XcptFilter_0
0x18003c540  mov     [rbp+90h], eax
0x18003c546  jmp     short loc_18003C552
0x18003c548  mov     dword ptr [rbp+90h], 0
0x18003c552  mov     eax, [rbp+90h]
0x18003c558  add     rsp, 20h
0x18003c55c  pop     rbp
0x18003c55d  retn
0x18003c55f  push    rbp
0x18003c561  sub     rsp, 20h
0x18003c565  mov     rbp, rdx
0x18003c568  mov     rax, [rcx]
0x18003c56b  mov     edx, [rax]
0x18003c56d  mov     [rbp+0E0h], rcx
0x18003c574  mov     [rbp+98h], edx
0x18003c57a  mov     eax, [rbp+98h]
0x18003c580  cmp     eax, 0E06D7363h
0x18003c585  jnz     short loc_18003C5A1
0x18003c587  mov     rdx, [rbp+0E0h]
0x18003c58e  mov     ecx, [rbp+98h]
0x18003c594  call    _XcptFilter_0
0x18003c599  mov     [rbp+0A0h], eax
0x18003c59f  jmp     short loc_18003C5AB
0x18003c5a1  mov     dword ptr [rbp+0A0h], 0
0x18003c5ab  mov     eax, [rbp+0A0h]
0x18003c5b1  add     rsp, 20h
0x18003c5b5  pop     rbp
0x18003c5b6  retn
0x18003c5b8  push    rbp
0x18003c5ba  sub     rsp, 20h
0x18003c5be  mov     rbp, rdx
0x18003c5c1  cmp     dword ptr [rbp+118h], 1
0x18003c5c8  ja      short loc_18003C5D4
0x18003c5ca  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
