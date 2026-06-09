# __DllMainCRTStartup

- ea: `0x18000ddf4`
- end: `0x18000e000`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ddb0`

## callees

- `0x18000db80`
- `0x18000ddf4`
- `0x18000e368`
- `0x18000e538`
- `0x180011040`

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
  if ( (_DWORD)fdwReason || dword_18001B420 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001B424 = 1;
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
            if ( dword_18001B424 )
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
0x18000ddf4  mov     [rsp+lpvReserved], r8
0x18000ddf9  mov     [rsp+arg_8], edx
0x18000ddfd  mov     [rsp+arg_0], rcx
0x18000de02  push    rbx
0x18000de03  push    rsi
0x18000de04  push    rdi
0x18000de05  sub     rsp, 0F0h
0x18000de0c  mov     edi, edx
0x18000de0e  mov     rsi, rcx
0x18000de11  mov     ebx, 1
0x18000de16  cmp     edx, ebx
0x18000de18  ja      short loc_18000DE20
0x18000de1a  mov     cs:__native_dllmain_reason, edx
0x18000de20  test    edx, edx
0x18000de22  jnz     short loc_18000DE37
0x18000de24  cmp     cs:dword_18001B420, edx
0x18000de2a  jnz     short loc_18000DE37
0x18000de2c  xor     ebx, ebx
0x18000de2e  mov     [rsp+108h+var_E8], ebx
0x18000de32  jmp     loc_18000DFE4
0x18000de37  lea     eax, [rdx-1]
0x18000de3a  cmp     eax, 1
0x18000de3d  ja      loc_18000DEC4
0x18000de43  mov     rax, cs:_pRawDllMain
0x18000de4a  test    rax, rax
0x18000de4d  jz      short loc_18000DE85
0x18000de4f  cmp     edx, 1
0x18000de52  jnz     short loc_18000DE5A
0x18000de54  mov     cs:dword_18001B424, edx
0x18000de5a  mov     r8, [rsp+108h+lpvReserved]
0x18000de62  call    cs:__guard_dispatch_icall_fptr
0x18000de68  mov     ebx, eax
0x18000de6a  mov     [rsp+108h+var_E8], eax
0x18000de6e  jmp     short loc_18000DE85
0x18000de70  xor     ebx, ebx
0x18000de72  mov     [rsp+108h+var_E8], ebx
0x18000de76  mov     edi, [rsp+108h+arg_8]
0x18000de7d  mov     rsi, [rsp+108h+arg_0]
0x18000de85  test    ebx, ebx
0x18000de87  jz      loc_18000DFE4
0x18000de8d  mov     r8, [rsp+108h+lpvReserved]
0x18000de95  mov     edx, edi
0x18000de97  mov     rcx, rsi
0x18000de9a  call    _CRT_INIT
0x18000de9f  mov     ebx, eax
0x18000dea1  mov     [rsp+108h+var_E8], eax
0x18000dea5  jmp     short loc_18000DEBC
0x18000dea7  xor     ebx, ebx
0x18000dea9  mov     [rsp+108h+var_E8], ebx
0x18000dead  mov     edi, [rsp+108h+arg_8]
0x18000deb4  mov     rsi, [rsp+108h+arg_0]
0x18000debc  test    ebx, ebx
0x18000debe  jz      loc_18000DFE4
0x18000dec4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000decc  mov     edx, edi; fdwReason
0x18000dece  mov     rcx, rsi; hinstDLL
0x18000ded1  call    DllMain
0x18000ded6  mov     ebx, eax
0x18000ded8  mov     [rsp+108h+var_E8], eax
0x18000dedc  jmp     short loc_18000DEF3
0x18000dede  xor     ebx, ebx
0x18000dee0  mov     [rsp+108h+var_E8], ebx
0x18000dee4  mov     edi, [rsp+108h+arg_8]
0x18000deeb  mov     rsi, [rsp+108h+arg_0]
0x18000def3  cmp     edi, 1
0x18000def6  jnz     short loc_18000DF6F
0x18000def8  test    ebx, ebx
0x18000defa  jnz     short loc_18000DF6F
0x18000defc  xor     r8d, r8d; lpvReserved
0x18000deff  xor     edx, edx; fdwReason
0x18000df01  mov     rcx, rsi; hinstDLL
0x18000df04  call    DllMain
0x18000df09  jmp     short loc_18000DF1E
0x18000df0b  mov     edi, [rsp+108h+arg_8]
0x18000df12  mov     rsi, [rsp+108h+arg_0]
0x18000df1a  mov     ebx, [rsp+108h+var_E8]
0x18000df1e  xor     r8d, r8d
0x18000df21  xor     edx, edx
0x18000df23  mov     rcx, rsi
0x18000df26  call    _CRT_INIT
0x18000df2b  jmp     short loc_18000DF40
0x18000df2d  mov     edi, [rsp+108h+arg_8]
0x18000df34  mov     rsi, [rsp+108h+arg_0]
0x18000df3c  mov     ebx, [rsp+108h+var_E8]
0x18000df40  mov     rax, cs:_pRawDllMain
0x18000df47  test    rax, rax
0x18000df4a  jz      short loc_18000DF6F
0x18000df4c  xor     r8d, r8d
0x18000df4f  xor     edx, edx
0x18000df51  mov     rcx, rsi
0x18000df54  call    cs:__guard_dispatch_icall_fptr
0x18000df5a  jmp     short loc_18000DF6F
0x18000df5c  mov     edi, [rsp+108h+arg_8]
0x18000df63  mov     rsi, [rsp+108h+arg_0]
0x18000df6b  mov     ebx, [rsp+108h+var_E8]
0x18000df6f  test    edi, edi
0x18000df71  jz      short loc_18000DF78
0x18000df73  cmp     edi, 3
0x18000df76  jnz     short loc_18000DFE4
0x18000df78  mov     r8, [rsp+108h+lpvReserved]
0x18000df80  mov     edx, edi
0x18000df82  mov     rcx, rsi
0x18000df85  call    _CRT_INIT
0x18000df8a  mov     ebx, eax
0x18000df8c  mov     [rsp+108h+var_E8], eax
0x18000df90  jmp     short loc_18000DFA7
0x18000df92  xor     ebx, ebx
0x18000df94  mov     [rsp+108h+var_E8], ebx
0x18000df98  mov     edi, [rsp+108h+arg_8]
0x18000df9f  mov     rsi, [rsp+108h+arg_0]
0x18000dfa7  mov     rax, cs:_pRawDllMain
0x18000dfae  test    rax, rax
0x18000dfb1  jz      short loc_18000DFE4
0x18000dfb3  cmp     cs:dword_18001B424, 0
0x18000dfba  jz      short loc_18000DFE4
0x18000dfbc  mov     r8, [rsp+108h+lpvReserved]
0x18000dfc4  mov     edx, edi
0x18000dfc6  mov     rcx, rsi
0x18000dfc9  call    cs:__guard_dispatch_icall_fptr
0x18000dfcf  mov     ebx, eax
0x18000dfd1  mov     [rsp+108h+var_E8], eax
0x18000dfd5  jmp     short loc_18000DFE4
0x18000dfd7  xor     ebx, ebx
0x18000dfd9  mov     [rsp+108h+var_E8], ebx
0x18000dfdd  mov     edi, [rsp+108h+arg_8]
0x18000dfe4  cmp     edi, 1
0x18000dfe7  ja      short loc_18000DFF3
0x18000dfe9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18000dff3  mov     eax, ebx
0x18000dff5  add     rsp, 0F0h
0x18000dffc  pop     rdi
0x18000dffd  pop     rsi
0x18000dffe  pop     rbx
0x18000dfff  retn
0x18001195d  push    rbp
0x18001195f  sub     rsp, 20h
0x180011963  mov     rbp, rdx
0x180011966  mov     rax, [rcx]
0x180011969  mov     edx, [rax]
0x18001196b  mov     [rbp+0A8h], rcx
0x180011972  mov     [rbp+28h], edx
0x180011975  mov     eax, [rbp+28h]
0x180011978  cmp     eax, 0E06D7363h
0x18001197d  jnz     short loc_180011993
0x18001197f  mov     rdx, [rbp+0A8h]
0x180011986  mov     ecx, [rbp+28h]
0x180011989  call    _XcptFilter_0
0x18001198e  mov     [rbp+30h], eax
0x180011991  jmp     short loc_18001199A
0x180011993  mov     dword ptr [rbp+30h], 0
0x18001199a  mov     eax, [rbp+30h]
0x18001199d  add     rsp, 20h
0x1800119a1  pop     rbp
0x1800119a2  retn
0x1800119a4  push    rbp
0x1800119a6  sub     rsp, 20h
0x1800119aa  mov     rbp, rdx
0x1800119ad  mov     rax, [rcx]
0x1800119b0  mov     edx, [rax]
0x1800119b2  mov     [rbp+0B0h], rcx
0x1800119b9  mov     [rbp+38h], edx
0x1800119bc  mov     eax, [rbp+38h]
0x1800119bf  cmp     eax, 0E06D7363h
0x1800119c4  jnz     short loc_1800119DA
0x1800119c6  mov     rdx, [rbp+0B0h]
0x1800119cd  mov     ecx, [rbp+38h]
0x1800119d0  call    _XcptFilter_0
0x1800119d5  mov     [rbp+40h], eax
0x1800119d8  jmp     short loc_1800119E1
0x1800119da  mov     dword ptr [rbp+40h], 0
0x1800119e1  mov     eax, [rbp+40h]
0x1800119e4  add     rsp, 20h
0x1800119e8  pop     rbp
0x1800119e9  retn
0x1800119eb  push    rbp
0x1800119ed  sub     rsp, 20h
0x1800119f1  mov     rbp, rdx
0x1800119f4  mov     rax, [rcx]
0x1800119f7  mov     edx, [rax]
0x1800119f9  mov     [rbp+0B8h], rcx
0x180011a00  mov     [rbp+48h], edx
0x180011a03  mov     eax, [rbp+48h]
0x180011a06  cmp     eax, 0E06D7363h
0x180011a0b  jnz     short loc_180011A21
0x180011a0d  mov     rdx, [rbp+0B8h]
0x180011a14  mov     ecx, [rbp+48h]
0x180011a17  call    _XcptFilter_0
0x180011a1c  mov     [rbp+50h], eax
0x180011a1f  jmp     short loc_180011A28
0x180011a21  mov     dword ptr [rbp+50h], 0
0x180011a28  mov     eax, [rbp+50h]
0x180011a2b  add     rsp, 20h
0x180011a2f  pop     rbp
0x180011a30  retn
0x180011a32  push    rbp
0x180011a34  sub     rsp, 20h
0x180011a38  mov     rbp, rdx
0x180011a3b  mov     rax, [rcx]
0x180011a3e  mov     edx, [rax]
0x180011a40  mov     [rbp+0C0h], rcx
0x180011a47  mov     [rbp+58h], edx
0x180011a4a  mov     eax, [rbp+58h]
0x180011a4d  cmp     eax, 0E06D7363h
0x180011a52  jnz     short loc_180011A68
0x180011a54  mov     rdx, [rbp+0C0h]
0x180011a5b  mov     ecx, [rbp+58h]
0x180011a5e  call    _XcptFilter_0
0x180011a63  mov     [rbp+60h], eax
0x180011a66  jmp     short loc_180011A6F
0x180011a68  mov     dword ptr [rbp+60h], 0
0x180011a6f  mov     eax, [rbp+60h]
0x180011a72  add     rsp, 20h
0x180011a76  pop     rbp
0x180011a77  retn
0x180011a79  push    rbp
0x180011a7b  sub     rsp, 20h
0x180011a7f  mov     rbp, rdx
0x180011a82  mov     rax, [rcx]
0x180011a85  mov     edx, [rax]
0x180011a87  mov     [rbp+0C8h], rcx
0x180011a8e  mov     [rbp+68h], edx
0x180011a91  mov     eax, [rbp+68h]
0x180011a94  cmp     eax, 0E06D7363h
0x180011a99  jnz     short loc_180011AAF
0x180011a9b  mov     rdx, [rbp+0C8h]
0x180011aa2  mov     ecx, [rbp+68h]
0x180011aa5  call    _XcptFilter_0
0x180011aaa  mov     [rbp+70h], eax
0x180011aad  jmp     short loc_180011AB6
0x180011aaf  mov     dword ptr [rbp+70h], 0
0x180011ab6  mov     eax, [rbp+70h]
0x180011ab9  add     rsp, 20h
0x180011abd  pop     rbp
0x180011abe  retn
0x180011ac0  push    rbp
0x180011ac2  sub     rsp, 20h
0x180011ac6  mov     rbp, rdx
0x180011ac9  mov     rax, [rcx]
0x180011acc  mov     edx, [rax]
0x180011ace  mov     [rbp+0D0h], rcx
0x180011ad5  mov     [rbp+78h], edx
0x180011ad8  mov     eax, [rbp+78h]
0x180011adb  cmp     eax, 0E06D7363h
0x180011ae0  jnz     short loc_180011AF9
0x180011ae2  mov     rdx, [rbp+0D0h]
0x180011ae9  mov     ecx, [rbp+78h]
0x180011aec  call    _XcptFilter_0
0x180011af1  mov     [rbp+80h], eax
0x180011af7  jmp     short loc_180011B03
0x180011af9  mov     dword ptr [rbp+80h], 0
0x180011b03  mov     eax, [rbp+80h]
0x180011b09  add     rsp, 20h
0x180011b0d  pop     rbp
0x180011b0e  retn
0x180011b10  push    rbp
0x180011b12  sub     rsp, 20h
0x180011b16  mov     rbp, rdx
0x180011b19  mov     rax, [rcx]
0x180011b1c  mov     edx, [rax]
0x180011b1e  mov     [rbp+0D8h], rcx
0x180011b25  mov     [rbp+88h], edx
0x180011b2b  mov     eax, [rbp+88h]
0x180011b31  cmp     eax, 0E06D7363h
0x180011b36  jnz     short loc_180011B52
0x180011b38  mov     rdx, [rbp+0D8h]
0x180011b3f  mov     ecx, [rbp+88h]
0x180011b45  call    _XcptFilter_0
0x180011b4a  mov     [rbp+90h], eax
0x180011b50  jmp     short loc_180011B5C
0x180011b52  mov     dword ptr [rbp+90h], 0
0x180011b5c  mov     eax, [rbp+90h]
0x180011b62  add     rsp, 20h
0x180011b66  pop     rbp
0x180011b67  retn
0x180011b69  push    rbp
0x180011b6b  sub     rsp, 20h
0x180011b6f  mov     rbp, rdx
0x180011b72  mov     rax, [rcx]
0x180011b75  mov     edx, [rax]
0x180011b77  mov     [rbp+0E0h], rcx
0x180011b7e  mov     [rbp+98h], edx
0x180011b84  mov     eax, [rbp+98h]
0x180011b8a  cmp     eax, 0E06D7363h
0x180011b8f  jnz     short loc_180011BAB
0x180011b91  mov     rdx, [rbp+0E0h]
0x180011b98  mov     ecx, [rbp+98h]
0x180011b9e  call    _XcptFilter_0
0x180011ba3  mov     [rbp+0A0h], eax
0x180011ba9  jmp     short loc_180011BB5
0x180011bab  mov     dword ptr [rbp+0A0h], 0
0x180011bb5  mov     eax, [rbp+0A0h]
0x180011bbb  add     rsp, 20h
0x180011bbf  pop     rbp
0x180011bc0  retn
0x180011bc2  push    rbp
0x180011bc4  sub     rsp, 20h
0x180011bc8  mov     rbp, rdx
0x180011bcb  cmp     dword ptr [rbp+118h], 1
0x180011bd2  ja      short loc_180011BDE
0x180011bd4  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
