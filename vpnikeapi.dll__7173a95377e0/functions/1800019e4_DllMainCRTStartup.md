# __DllMainCRTStartup

- ea: `0x1800019e4`
- end: `0x180001bf0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800019a0`

## callees

- `0x180001770`
- `0x1800019e4`
- `0x180001ecc`
- `0x180002de8`
- `0x18000d030`

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
  if ( (_DWORD)fdwReason || dword_180016200 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180016204 = 1;
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
            if ( dword_180016204 )
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
0x1800019e4  mov     [rsp+lpvReserved], r8
0x1800019e9  mov     [rsp+arg_8], edx
0x1800019ed  mov     [rsp+arg_0], rcx
0x1800019f2  push    rbx
0x1800019f3  push    rsi
0x1800019f4  push    rdi
0x1800019f5  sub     rsp, 0F0h
0x1800019fc  mov     edi, edx
0x1800019fe  mov     rsi, rcx
0x180001a01  mov     ebx, 1
0x180001a06  cmp     edx, ebx
0x180001a08  ja      short loc_180001A10
0x180001a0a  mov     cs:__native_dllmain_reason, edx
0x180001a10  test    edx, edx
0x180001a12  jnz     short loc_180001A27
0x180001a14  cmp     cs:dword_180016200, edx
0x180001a1a  jnz     short loc_180001A27
0x180001a1c  xor     ebx, ebx
0x180001a1e  mov     [rsp+108h+var_E8], ebx
0x180001a22  jmp     loc_180001BD4
0x180001a27  lea     eax, [rdx-1]
0x180001a2a  cmp     eax, 1
0x180001a2d  ja      loc_180001AB4
0x180001a33  mov     rax, cs:_pRawDllMain
0x180001a3a  test    rax, rax
0x180001a3d  jz      short loc_180001A75
0x180001a3f  cmp     edx, 1
0x180001a42  jnz     short loc_180001A4A
0x180001a44  mov     cs:dword_180016204, edx
0x180001a4a  mov     r8, [rsp+108h+lpvReserved]
0x180001a52  call    cs:__guard_dispatch_icall_fptr
0x180001a58  mov     ebx, eax
0x180001a5a  mov     [rsp+108h+var_E8], eax
0x180001a5e  jmp     short loc_180001A75
0x180001a60  xor     ebx, ebx
0x180001a62  mov     [rsp+108h+var_E8], ebx
0x180001a66  mov     edi, [rsp+108h+arg_8]
0x180001a6d  mov     rsi, [rsp+108h+arg_0]
0x180001a75  test    ebx, ebx
0x180001a77  jz      loc_180001BD4
0x180001a7d  mov     r8, [rsp+108h+lpvReserved]
0x180001a85  mov     edx, edi
0x180001a87  mov     rcx, rsi
0x180001a8a  call    _CRT_INIT
0x180001a8f  mov     ebx, eax
0x180001a91  mov     [rsp+108h+var_E8], eax
0x180001a95  jmp     short loc_180001AAC
0x180001a97  xor     ebx, ebx
0x180001a99  mov     [rsp+108h+var_E8], ebx
0x180001a9d  mov     edi, [rsp+108h+arg_8]
0x180001aa4  mov     rsi, [rsp+108h+arg_0]
0x180001aac  test    ebx, ebx
0x180001aae  jz      loc_180001BD4
0x180001ab4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001abc  mov     edx, edi; fdwReason
0x180001abe  mov     rcx, rsi; hinstDLL
0x180001ac1  call    DllMain
0x180001ac6  mov     ebx, eax
0x180001ac8  mov     [rsp+108h+var_E8], eax
0x180001acc  jmp     short loc_180001AE3
0x180001ace  xor     ebx, ebx
0x180001ad0  mov     [rsp+108h+var_E8], ebx
0x180001ad4  mov     edi, [rsp+108h+arg_8]
0x180001adb  mov     rsi, [rsp+108h+arg_0]
0x180001ae3  cmp     edi, 1
0x180001ae6  jnz     short loc_180001B5F
0x180001ae8  test    ebx, ebx
0x180001aea  jnz     short loc_180001B5F
0x180001aec  xor     r8d, r8d; lpvReserved
0x180001aef  xor     edx, edx; fdwReason
0x180001af1  mov     rcx, rsi; hinstDLL
0x180001af4  call    DllMain
0x180001af9  jmp     short loc_180001B0E
0x180001afb  mov     edi, [rsp+108h+arg_8]
0x180001b02  mov     rsi, [rsp+108h+arg_0]
0x180001b0a  mov     ebx, [rsp+108h+var_E8]
0x180001b0e  xor     r8d, r8d
0x180001b11  xor     edx, edx
0x180001b13  mov     rcx, rsi
0x180001b16  call    _CRT_INIT
0x180001b1b  jmp     short loc_180001B30
0x180001b1d  mov     edi, [rsp+108h+arg_8]
0x180001b24  mov     rsi, [rsp+108h+arg_0]
0x180001b2c  mov     ebx, [rsp+108h+var_E8]
0x180001b30  mov     rax, cs:_pRawDllMain
0x180001b37  test    rax, rax
0x180001b3a  jz      short loc_180001B5F
0x180001b3c  xor     r8d, r8d
0x180001b3f  xor     edx, edx
0x180001b41  mov     rcx, rsi
0x180001b44  call    cs:__guard_dispatch_icall_fptr
0x180001b4a  jmp     short loc_180001B5F
0x180001b4c  mov     edi, [rsp+108h+arg_8]
0x180001b53  mov     rsi, [rsp+108h+arg_0]
0x180001b5b  mov     ebx, [rsp+108h+var_E8]
0x180001b5f  test    edi, edi
0x180001b61  jz      short loc_180001B68
0x180001b63  cmp     edi, 3
0x180001b66  jnz     short loc_180001BD4
0x180001b68  mov     r8, [rsp+108h+lpvReserved]
0x180001b70  mov     edx, edi
0x180001b72  mov     rcx, rsi
0x180001b75  call    _CRT_INIT
0x180001b7a  mov     ebx, eax
0x180001b7c  mov     [rsp+108h+var_E8], eax
0x180001b80  jmp     short loc_180001B97
0x180001b82  xor     ebx, ebx
0x180001b84  mov     [rsp+108h+var_E8], ebx
0x180001b88  mov     edi, [rsp+108h+arg_8]
0x180001b8f  mov     rsi, [rsp+108h+arg_0]
0x180001b97  mov     rax, cs:_pRawDllMain
0x180001b9e  test    rax, rax
0x180001ba1  jz      short loc_180001BD4
0x180001ba3  cmp     cs:dword_180016204, 0
0x180001baa  jz      short loc_180001BD4
0x180001bac  mov     r8, [rsp+108h+lpvReserved]
0x180001bb4  mov     edx, edi
0x180001bb6  mov     rcx, rsi
0x180001bb9  call    cs:__guard_dispatch_icall_fptr
0x180001bbf  mov     ebx, eax
0x180001bc1  mov     [rsp+108h+var_E8], eax
0x180001bc5  jmp     short loc_180001BD4
0x180001bc7  xor     ebx, ebx
0x180001bc9  mov     [rsp+108h+var_E8], ebx
0x180001bcd  mov     edi, [rsp+108h+arg_8]
0x180001bd4  cmp     edi, 1
0x180001bd7  ja      short loc_180001BE3
0x180001bd9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001be3  mov     eax, ebx
0x180001be5  add     rsp, 0F0h
0x180001bec  pop     rdi
0x180001bed  pop     rsi
0x180001bee  pop     rbx
0x180001bef  retn
0x18000d128  push    rbp
0x18000d12a  sub     rsp, 20h
0x18000d12e  mov     rbp, rdx
0x18000d131  mov     rax, [rcx]
0x18000d134  mov     edx, [rax]
0x18000d136  mov     [rbp+0A8h], rcx
0x18000d13d  mov     [rbp+28h], edx
0x18000d140  mov     eax, [rbp+28h]
0x18000d143  cmp     eax, 0E06D7363h
0x18000d148  jnz     short loc_18000D15E
0x18000d14a  mov     rdx, [rbp+0A8h]
0x18000d151  mov     ecx, [rbp+28h]
0x18000d154  call    _XcptFilter_0
0x18000d159  mov     [rbp+30h], eax
0x18000d15c  jmp     short loc_18000D165
0x18000d15e  mov     dword ptr [rbp+30h], 0
0x18000d165  mov     eax, [rbp+30h]
0x18000d168  add     rsp, 20h
0x18000d16c  pop     rbp
0x18000d16d  retn
0x18000d16f  push    rbp
0x18000d171  sub     rsp, 20h
0x18000d175  mov     rbp, rdx
0x18000d178  mov     rax, [rcx]
0x18000d17b  mov     edx, [rax]
0x18000d17d  mov     [rbp+0B0h], rcx
0x18000d184  mov     [rbp+38h], edx
0x18000d187  mov     eax, [rbp+38h]
0x18000d18a  cmp     eax, 0E06D7363h
0x18000d18f  jnz     short loc_18000D1A5
0x18000d191  mov     rdx, [rbp+0B0h]
0x18000d198  mov     ecx, [rbp+38h]
0x18000d19b  call    _XcptFilter_0
0x18000d1a0  mov     [rbp+40h], eax
0x18000d1a3  jmp     short loc_18000D1AC
0x18000d1a5  mov     dword ptr [rbp+40h], 0
0x18000d1ac  mov     eax, [rbp+40h]
0x18000d1af  add     rsp, 20h
0x18000d1b3  pop     rbp
0x18000d1b4  retn
0x18000d1b6  push    rbp
0x18000d1b8  sub     rsp, 20h
0x18000d1bc  mov     rbp, rdx
0x18000d1bf  mov     rax, [rcx]
0x18000d1c2  mov     edx, [rax]
0x18000d1c4  mov     [rbp+0B8h], rcx
0x18000d1cb  mov     [rbp+48h], edx
0x18000d1ce  mov     eax, [rbp+48h]
0x18000d1d1  cmp     eax, 0E06D7363h
0x18000d1d6  jnz     short loc_18000D1EC
0x18000d1d8  mov     rdx, [rbp+0B8h]
0x18000d1df  mov     ecx, [rbp+48h]
0x18000d1e2  call    _XcptFilter_0
0x18000d1e7  mov     [rbp+50h], eax
0x18000d1ea  jmp     short loc_18000D1F3
0x18000d1ec  mov     dword ptr [rbp+50h], 0
0x18000d1f3  mov     eax, [rbp+50h]
0x18000d1f6  add     rsp, 20h
0x18000d1fa  pop     rbp
0x18000d1fb  retn
0x18000d1fd  push    rbp
0x18000d1ff  sub     rsp, 20h
0x18000d203  mov     rbp, rdx
0x18000d206  mov     rax, [rcx]
0x18000d209  mov     edx, [rax]
0x18000d20b  mov     [rbp+0C0h], rcx
0x18000d212  mov     [rbp+58h], edx
0x18000d215  mov     eax, [rbp+58h]
0x18000d218  cmp     eax, 0E06D7363h
0x18000d21d  jnz     short loc_18000D233
0x18000d21f  mov     rdx, [rbp+0C0h]
0x18000d226  mov     ecx, [rbp+58h]
0x18000d229  call    _XcptFilter_0
0x18000d22e  mov     [rbp+60h], eax
0x18000d231  jmp     short loc_18000D23A
0x18000d233  mov     dword ptr [rbp+60h], 0
0x18000d23a  mov     eax, [rbp+60h]
0x18000d23d  add     rsp, 20h
0x18000d241  pop     rbp
0x18000d242  retn
0x18000d244  push    rbp
0x18000d246  sub     rsp, 20h
0x18000d24a  mov     rbp, rdx
0x18000d24d  mov     rax, [rcx]
0x18000d250  mov     edx, [rax]
0x18000d252  mov     [rbp+0C8h], rcx
0x18000d259  mov     [rbp+68h], edx
0x18000d25c  mov     eax, [rbp+68h]
0x18000d25f  cmp     eax, 0E06D7363h
0x18000d264  jnz     short loc_18000D27A
0x18000d266  mov     rdx, [rbp+0C8h]
0x18000d26d  mov     ecx, [rbp+68h]
0x18000d270  call    _XcptFilter_0
0x18000d275  mov     [rbp+70h], eax
0x18000d278  jmp     short loc_18000D281
0x18000d27a  mov     dword ptr [rbp+70h], 0
0x18000d281  mov     eax, [rbp+70h]
0x18000d284  add     rsp, 20h
0x18000d288  pop     rbp
0x18000d289  retn
0x18000d28b  push    rbp
0x18000d28d  sub     rsp, 20h
0x18000d291  mov     rbp, rdx
0x18000d294  mov     rax, [rcx]
0x18000d297  mov     edx, [rax]
0x18000d299  mov     [rbp+0D0h], rcx
0x18000d2a0  mov     [rbp+78h], edx
0x18000d2a3  mov     eax, [rbp+78h]
0x18000d2a6  cmp     eax, 0E06D7363h
0x18000d2ab  jnz     short loc_18000D2C4
0x18000d2ad  mov     rdx, [rbp+0D0h]
0x18000d2b4  mov     ecx, [rbp+78h]
0x18000d2b7  call    _XcptFilter_0
0x18000d2bc  mov     [rbp+80h], eax
0x18000d2c2  jmp     short loc_18000D2CE
0x18000d2c4  mov     dword ptr [rbp+80h], 0
0x18000d2ce  mov     eax, [rbp+80h]
0x18000d2d4  add     rsp, 20h
0x18000d2d8  pop     rbp
0x18000d2d9  retn
0x18000d2db  push    rbp
0x18000d2dd  sub     rsp, 20h
0x18000d2e1  mov     rbp, rdx
0x18000d2e4  mov     rax, [rcx]
0x18000d2e7  mov     edx, [rax]
0x18000d2e9  mov     [rbp+0D8h], rcx
0x18000d2f0  mov     [rbp+88h], edx
0x18000d2f6  mov     eax, [rbp+88h]
0x18000d2fc  cmp     eax, 0E06D7363h
0x18000d301  jnz     short loc_18000D31D
0x18000d303  mov     rdx, [rbp+0D8h]
0x18000d30a  mov     ecx, [rbp+88h]
0x18000d310  call    _XcptFilter_0
0x18000d315  mov     [rbp+90h], eax
0x18000d31b  jmp     short loc_18000D327
0x18000d31d  mov     dword ptr [rbp+90h], 0
0x18000d327  mov     eax, [rbp+90h]
0x18000d32d  add     rsp, 20h
0x18000d331  pop     rbp
0x18000d332  retn
0x18000d334  push    rbp
0x18000d336  sub     rsp, 20h
0x18000d33a  mov     rbp, rdx
0x18000d33d  mov     rax, [rcx]
0x18000d340  mov     edx, [rax]
0x18000d342  mov     [rbp+0E0h], rcx
0x18000d349  mov     [rbp+98h], edx
0x18000d34f  mov     eax, [rbp+98h]
0x18000d355  cmp     eax, 0E06D7363h
0x18000d35a  jnz     short loc_18000D376
0x18000d35c  mov     rdx, [rbp+0E0h]
0x18000d363  mov     ecx, [rbp+98h]
0x18000d369  call    _XcptFilter_0
0x18000d36e  mov     [rbp+0A0h], eax
0x18000d374  jmp     short loc_18000D380
0x18000d376  mov     dword ptr [rbp+0A0h], 0
0x18000d380  mov     eax, [rbp+0A0h]
0x18000d386  add     rsp, 20h
0x18000d38a  pop     rbp
0x18000d38b  retn
0x18000d38d  push    rbp
0x18000d38f  sub     rsp, 20h
0x18000d393  mov     rbp, rdx
0x18000d396  cmp     dword ptr [rbp+118h], 1
0x18000d39d  ja      short loc_18000D3A9
0x18000d39f  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
