# __DllMainCRTStartup

- ea: `0x1800018b4`
- end: `0x180001ac0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001870`

## callees

- `0x180001640`
- `0x1800018b4`
- `0x180001db6`
- `0x180001f88`
- `0x180031a60`

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
  if ( (_DWORD)fdwReason || dword_18004CD9C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18004CDA0 = 1;
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
            if ( dword_18004CDA0 )
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
0x1800018b4  mov     [rsp+lpvReserved], r8
0x1800018b9  mov     [rsp+arg_8], edx
0x1800018bd  mov     [rsp+arg_0], rcx
0x1800018c2  push    rbx
0x1800018c3  push    rsi
0x1800018c4  push    rdi
0x1800018c5  sub     rsp, 0F0h
0x1800018cc  mov     edi, edx
0x1800018ce  mov     rsi, rcx
0x1800018d1  mov     ebx, 1
0x1800018d6  cmp     edx, ebx
0x1800018d8  ja      short loc_1800018E0
0x1800018da  mov     cs:__native_dllmain_reason, edx
0x1800018e0  test    edx, edx
0x1800018e2  jnz     short loc_1800018F7
0x1800018e4  cmp     cs:dword_18004CD9C, edx
0x1800018ea  jnz     short loc_1800018F7
0x1800018ec  xor     ebx, ebx
0x1800018ee  mov     [rsp+108h+var_E8], ebx
0x1800018f2  jmp     loc_180001AA4
0x1800018f7  lea     eax, [rdx-1]
0x1800018fa  cmp     eax, 1
0x1800018fd  ja      loc_180001984
0x180001903  mov     rax, cs:_pRawDllMain
0x18000190a  test    rax, rax
0x18000190d  jz      short loc_180001945
0x18000190f  cmp     edx, 1
0x180001912  jnz     short loc_18000191A
0x180001914  mov     cs:dword_18004CDA0, edx
0x18000191a  mov     r8, [rsp+108h+lpvReserved]
0x180001922  call    cs:__guard_dispatch_icall_fptr
0x180001928  mov     ebx, eax
0x18000192a  mov     [rsp+108h+var_E8], eax
0x18000192e  jmp     short loc_180001945
0x180001930  xor     ebx, ebx
0x180001932  mov     [rsp+108h+var_E8], ebx
0x180001936  mov     edi, [rsp+108h+arg_8]
0x18000193d  mov     rsi, [rsp+108h+arg_0]
0x180001945  test    ebx, ebx
0x180001947  jz      loc_180001AA4
0x18000194d  mov     r8, [rsp+108h+lpvReserved]
0x180001955  mov     edx, edi
0x180001957  mov     rcx, rsi
0x18000195a  call    _CRT_INIT
0x18000195f  mov     ebx, eax
0x180001961  mov     [rsp+108h+var_E8], eax
0x180001965  jmp     short loc_18000197C
0x180001967  xor     ebx, ebx
0x180001969  mov     [rsp+108h+var_E8], ebx
0x18000196d  mov     edi, [rsp+108h+arg_8]
0x180001974  mov     rsi, [rsp+108h+arg_0]
0x18000197c  test    ebx, ebx
0x18000197e  jz      loc_180001AA4
0x180001984  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000198c  mov     edx, edi; fdwReason
0x18000198e  mov     rcx, rsi; hinstDLL
0x180001991  call    DllMain
0x180001996  mov     ebx, eax
0x180001998  mov     [rsp+108h+var_E8], eax
0x18000199c  jmp     short loc_1800019B3
0x18000199e  xor     ebx, ebx
0x1800019a0  mov     [rsp+108h+var_E8], ebx
0x1800019a4  mov     edi, [rsp+108h+arg_8]
0x1800019ab  mov     rsi, [rsp+108h+arg_0]
0x1800019b3  cmp     edi, 1
0x1800019b6  jnz     short loc_180001A2F
0x1800019b8  test    ebx, ebx
0x1800019ba  jnz     short loc_180001A2F
0x1800019bc  xor     r8d, r8d; lpvReserved
0x1800019bf  xor     edx, edx; fdwReason
0x1800019c1  mov     rcx, rsi; hinstDLL
0x1800019c4  call    DllMain
0x1800019c9  jmp     short loc_1800019DE
0x1800019cb  mov     edi, [rsp+108h+arg_8]
0x1800019d2  mov     rsi, [rsp+108h+arg_0]
0x1800019da  mov     ebx, [rsp+108h+var_E8]
0x1800019de  xor     r8d, r8d
0x1800019e1  xor     edx, edx
0x1800019e3  mov     rcx, rsi
0x1800019e6  call    _CRT_INIT
0x1800019eb  jmp     short loc_180001A00
0x1800019ed  mov     edi, [rsp+108h+arg_8]
0x1800019f4  mov     rsi, [rsp+108h+arg_0]
0x1800019fc  mov     ebx, [rsp+108h+var_E8]
0x180001a00  mov     rax, cs:_pRawDllMain
0x180001a07  test    rax, rax
0x180001a0a  jz      short loc_180001A2F
0x180001a0c  xor     r8d, r8d
0x180001a0f  xor     edx, edx
0x180001a11  mov     rcx, rsi
0x180001a14  call    cs:__guard_dispatch_icall_fptr
0x180001a1a  jmp     short loc_180001A2F
0x180001a1c  mov     edi, [rsp+108h+arg_8]
0x180001a23  mov     rsi, [rsp+108h+arg_0]
0x180001a2b  mov     ebx, [rsp+108h+var_E8]
0x180001a2f  test    edi, edi
0x180001a31  jz      short loc_180001A38
0x180001a33  cmp     edi, 3
0x180001a36  jnz     short loc_180001AA4
0x180001a38  mov     r8, [rsp+108h+lpvReserved]
0x180001a40  mov     edx, edi
0x180001a42  mov     rcx, rsi
0x180001a45  call    _CRT_INIT
0x180001a4a  mov     ebx, eax
0x180001a4c  mov     [rsp+108h+var_E8], eax
0x180001a50  jmp     short loc_180001A67
0x180001a52  xor     ebx, ebx
0x180001a54  mov     [rsp+108h+var_E8], ebx
0x180001a58  mov     edi, [rsp+108h+arg_8]
0x180001a5f  mov     rsi, [rsp+108h+arg_0]
0x180001a67  mov     rax, cs:_pRawDllMain
0x180001a6e  test    rax, rax
0x180001a71  jz      short loc_180001AA4
0x180001a73  cmp     cs:dword_18004CDA0, 0
0x180001a7a  jz      short loc_180001AA4
0x180001a7c  mov     r8, [rsp+108h+lpvReserved]
0x180001a84  mov     edx, edi
0x180001a86  mov     rcx, rsi
0x180001a89  call    cs:__guard_dispatch_icall_fptr
0x180001a8f  mov     ebx, eax
0x180001a91  mov     [rsp+108h+var_E8], eax
0x180001a95  jmp     short loc_180001AA4
0x180001a97  xor     ebx, ebx
0x180001a99  mov     [rsp+108h+var_E8], ebx
0x180001a9d  mov     edi, [rsp+108h+arg_8]
0x180001aa4  cmp     edi, 1
0x180001aa7  ja      short loc_180001AB3
0x180001aa9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001ab3  mov     eax, ebx
0x180001ab5  add     rsp, 0F0h
0x180001abc  pop     rdi
0x180001abd  pop     rsi
0x180001abe  pop     rbx
0x180001abf  retn
0x180031b03  push    rbp
0x180031b05  sub     rsp, 20h
0x180031b09  mov     rbp, rdx
0x180031b0c  mov     rax, [rcx]
0x180031b0f  mov     edx, [rax]
0x180031b11  mov     [rbp+0A8h], rcx
0x180031b18  mov     [rbp+28h], edx
0x180031b1b  mov     eax, [rbp+28h]
0x180031b1e  cmp     eax, 0E06D7363h
0x180031b23  jnz     short loc_180031B39
0x180031b25  mov     rdx, [rbp+0A8h]
0x180031b2c  mov     ecx, [rbp+28h]
0x180031b2f  call    _XcptFilter_0
0x180031b34  mov     [rbp+30h], eax
0x180031b37  jmp     short loc_180031B40
0x180031b39  mov     dword ptr [rbp+30h], 0
0x180031b40  mov     eax, [rbp+30h]
0x180031b43  add     rsp, 20h
0x180031b47  pop     rbp
0x180031b48  retn
0x180031b4a  push    rbp
0x180031b4c  sub     rsp, 20h
0x180031b50  mov     rbp, rdx
0x180031b53  mov     rax, [rcx]
0x180031b56  mov     edx, [rax]
0x180031b58  mov     [rbp+0B0h], rcx
0x180031b5f  mov     [rbp+38h], edx
0x180031b62  mov     eax, [rbp+38h]
0x180031b65  cmp     eax, 0E06D7363h
0x180031b6a  jnz     short loc_180031B80
0x180031b6c  mov     rdx, [rbp+0B0h]
0x180031b73  mov     ecx, [rbp+38h]
0x180031b76  call    _XcptFilter_0
0x180031b7b  mov     [rbp+40h], eax
0x180031b7e  jmp     short loc_180031B87
0x180031b80  mov     dword ptr [rbp+40h], 0
0x180031b87  mov     eax, [rbp+40h]
0x180031b8a  add     rsp, 20h
0x180031b8e  pop     rbp
0x180031b8f  retn
0x180031b91  push    rbp
0x180031b93  sub     rsp, 20h
0x180031b97  mov     rbp, rdx
0x180031b9a  mov     rax, [rcx]
0x180031b9d  mov     edx, [rax]
0x180031b9f  mov     [rbp+0B8h], rcx
0x180031ba6  mov     [rbp+48h], edx
0x180031ba9  mov     eax, [rbp+48h]
0x180031bac  cmp     eax, 0E06D7363h
0x180031bb1  jnz     short loc_180031BC7
0x180031bb3  mov     rdx, [rbp+0B8h]
0x180031bba  mov     ecx, [rbp+48h]
0x180031bbd  call    _XcptFilter_0
0x180031bc2  mov     [rbp+50h], eax
0x180031bc5  jmp     short loc_180031BCE
0x180031bc7  mov     dword ptr [rbp+50h], 0
0x180031bce  mov     eax, [rbp+50h]
0x180031bd1  add     rsp, 20h
0x180031bd5  pop     rbp
0x180031bd6  retn
0x180031bd8  push    rbp
0x180031bda  sub     rsp, 20h
0x180031bde  mov     rbp, rdx
0x180031be1  mov     rax, [rcx]
0x180031be4  mov     edx, [rax]
0x180031be6  mov     [rbp+0C0h], rcx
0x180031bed  mov     [rbp+58h], edx
0x180031bf0  mov     eax, [rbp+58h]
0x180031bf3  cmp     eax, 0E06D7363h
0x180031bf8  jnz     short loc_180031C0E
0x180031bfa  mov     rdx, [rbp+0C0h]
0x180031c01  mov     ecx, [rbp+58h]
0x180031c04  call    _XcptFilter_0
0x180031c09  mov     [rbp+60h], eax
0x180031c0c  jmp     short loc_180031C15
0x180031c0e  mov     dword ptr [rbp+60h], 0
0x180031c15  mov     eax, [rbp+60h]
0x180031c18  add     rsp, 20h
0x180031c1c  pop     rbp
0x180031c1d  retn
0x180031c1f  push    rbp
0x180031c21  sub     rsp, 20h
0x180031c25  mov     rbp, rdx
0x180031c28  mov     rax, [rcx]
0x180031c2b  mov     edx, [rax]
0x180031c2d  mov     [rbp+0C8h], rcx
0x180031c34  mov     [rbp+68h], edx
0x180031c37  mov     eax, [rbp+68h]
0x180031c3a  cmp     eax, 0E06D7363h
0x180031c3f  jnz     short loc_180031C55
0x180031c41  mov     rdx, [rbp+0C8h]
0x180031c48  mov     ecx, [rbp+68h]
0x180031c4b  call    _XcptFilter_0
0x180031c50  mov     [rbp+70h], eax
0x180031c53  jmp     short loc_180031C5C
0x180031c55  mov     dword ptr [rbp+70h], 0
0x180031c5c  mov     eax, [rbp+70h]
0x180031c5f  add     rsp, 20h
0x180031c63  pop     rbp
0x180031c64  retn
0x180031c66  push    rbp
0x180031c68  sub     rsp, 20h
0x180031c6c  mov     rbp, rdx
0x180031c6f  mov     rax, [rcx]
0x180031c72  mov     edx, [rax]
0x180031c74  mov     [rbp+0D0h], rcx
0x180031c7b  mov     [rbp+78h], edx
0x180031c7e  mov     eax, [rbp+78h]
0x180031c81  cmp     eax, 0E06D7363h
0x180031c86  jnz     short loc_180031C9F
0x180031c88  mov     rdx, [rbp+0D0h]
0x180031c8f  mov     ecx, [rbp+78h]
0x180031c92  call    _XcptFilter_0
0x180031c97  mov     [rbp+80h], eax
0x180031c9d  jmp     short loc_180031CA9
0x180031c9f  mov     dword ptr [rbp+80h], 0
0x180031ca9  mov     eax, [rbp+80h]
0x180031caf  add     rsp, 20h
0x180031cb3  pop     rbp
0x180031cb4  retn
0x180031cb6  push    rbp
0x180031cb8  sub     rsp, 20h
0x180031cbc  mov     rbp, rdx
0x180031cbf  mov     rax, [rcx]
0x180031cc2  mov     edx, [rax]
0x180031cc4  mov     [rbp+0D8h], rcx
0x180031ccb  mov     [rbp+88h], edx
0x180031cd1  mov     eax, [rbp+88h]
0x180031cd7  cmp     eax, 0E06D7363h
0x180031cdc  jnz     short loc_180031CF8
0x180031cde  mov     rdx, [rbp+0D8h]
0x180031ce5  mov     ecx, [rbp+88h]
0x180031ceb  call    _XcptFilter_0
0x180031cf0  mov     [rbp+90h], eax
0x180031cf6  jmp     short loc_180031D02
0x180031cf8  mov     dword ptr [rbp+90h], 0
0x180031d02  mov     eax, [rbp+90h]
0x180031d08  add     rsp, 20h
0x180031d0c  pop     rbp
0x180031d0d  retn
0x180031d0f  push    rbp
0x180031d11  sub     rsp, 20h
0x180031d15  mov     rbp, rdx
0x180031d18  mov     rax, [rcx]
0x180031d1b  mov     edx, [rax]
0x180031d1d  mov     [rbp+0E0h], rcx
0x180031d24  mov     [rbp+98h], edx
0x180031d2a  mov     eax, [rbp+98h]
0x180031d30  cmp     eax, 0E06D7363h
0x180031d35  jnz     short loc_180031D51
0x180031d37  mov     rdx, [rbp+0E0h]
0x180031d3e  mov     ecx, [rbp+98h]
0x180031d44  call    _XcptFilter_0
0x180031d49  mov     [rbp+0A0h], eax
0x180031d4f  jmp     short loc_180031D5B
0x180031d51  mov     dword ptr [rbp+0A0h], 0
0x180031d5b  mov     eax, [rbp+0A0h]
0x180031d61  add     rsp, 20h
0x180031d65  pop     rbp
0x180031d66  retn
0x180031d68  push    rbp
0x180031d6a  sub     rsp, 20h
0x180031d6e  mov     rbp, rdx
0x180031d71  cmp     dword ptr [rbp+118h], 1
0x180031d78  ja      short loc_180031D84
0x180031d7a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
