# __DllMainCRTStartup

- ea: `0x180001e04`
- end: `0x180002010`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001dc0`

## callees

- `0x180001160`
- `0x180001b90`
- `0x180001e04`
- `0x18000255e`
- `0x180012870`

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
  if ( (_DWORD)fdwReason || dword_18001DD8C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001DD90 = 1;
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
            if ( dword_18001DD90 )
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
0x180001e04  mov     [rsp+lpvReserved], r8
0x180001e09  mov     [rsp+arg_8], edx
0x180001e0d  mov     [rsp+arg_0], rcx
0x180001e12  push    rbx
0x180001e13  push    rsi
0x180001e14  push    rdi
0x180001e15  sub     rsp, 0F0h
0x180001e1c  mov     edi, edx
0x180001e1e  mov     rsi, rcx
0x180001e21  mov     ebx, 1
0x180001e26  cmp     edx, ebx
0x180001e28  ja      short loc_180001E30
0x180001e2a  mov     cs:__native_dllmain_reason, edx
0x180001e30  test    edx, edx
0x180001e32  jnz     short loc_180001E47
0x180001e34  cmp     cs:dword_18001DD8C, edx
0x180001e3a  jnz     short loc_180001E47
0x180001e3c  xor     ebx, ebx
0x180001e3e  mov     [rsp+108h+var_E8], ebx
0x180001e42  jmp     loc_180001FF4
0x180001e47  lea     eax, [rdx-1]
0x180001e4a  cmp     eax, 1
0x180001e4d  ja      loc_180001ED4
0x180001e53  mov     rax, cs:_pRawDllMain
0x180001e5a  test    rax, rax
0x180001e5d  jz      short loc_180001E95
0x180001e5f  cmp     edx, 1
0x180001e62  jnz     short loc_180001E6A
0x180001e64  mov     cs:dword_18001DD90, edx
0x180001e6a  mov     r8, [rsp+108h+lpvReserved]
0x180001e72  call    cs:__guard_dispatch_icall_fptr
0x180001e78  mov     ebx, eax
0x180001e7a  mov     [rsp+108h+var_E8], eax
0x180001e7e  jmp     short loc_180001E95
0x180001e80  xor     ebx, ebx
0x180001e82  mov     [rsp+108h+var_E8], ebx
0x180001e86  mov     edi, [rsp+108h+arg_8]
0x180001e8d  mov     rsi, [rsp+108h+arg_0]
0x180001e95  test    ebx, ebx
0x180001e97  jz      loc_180001FF4
0x180001e9d  mov     r8, [rsp+108h+lpvReserved]
0x180001ea5  mov     edx, edi
0x180001ea7  mov     rcx, rsi
0x180001eaa  call    _CRT_INIT
0x180001eaf  mov     ebx, eax
0x180001eb1  mov     [rsp+108h+var_E8], eax
0x180001eb5  jmp     short loc_180001ECC
0x180001eb7  xor     ebx, ebx
0x180001eb9  mov     [rsp+108h+var_E8], ebx
0x180001ebd  mov     edi, [rsp+108h+arg_8]
0x180001ec4  mov     rsi, [rsp+108h+arg_0]
0x180001ecc  test    ebx, ebx
0x180001ece  jz      loc_180001FF4
0x180001ed4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001edc  mov     edx, edi; fdwReason
0x180001ede  mov     rcx, rsi; hinstDLL
0x180001ee1  call    DllMain
0x180001ee6  mov     ebx, eax
0x180001ee8  mov     [rsp+108h+var_E8], eax
0x180001eec  jmp     short loc_180001F03
0x180001eee  xor     ebx, ebx
0x180001ef0  mov     [rsp+108h+var_E8], ebx
0x180001ef4  mov     edi, [rsp+108h+arg_8]
0x180001efb  mov     rsi, [rsp+108h+arg_0]
0x180001f03  cmp     edi, 1
0x180001f06  jnz     short loc_180001F7F
0x180001f08  test    ebx, ebx
0x180001f0a  jnz     short loc_180001F7F
0x180001f0c  xor     r8d, r8d; lpvReserved
0x180001f0f  xor     edx, edx; fdwReason
0x180001f11  mov     rcx, rsi; hinstDLL
0x180001f14  call    DllMain
0x180001f19  jmp     short loc_180001F2E
0x180001f1b  mov     edi, [rsp+108h+arg_8]
0x180001f22  mov     rsi, [rsp+108h+arg_0]
0x180001f2a  mov     ebx, [rsp+108h+var_E8]
0x180001f2e  xor     r8d, r8d
0x180001f31  xor     edx, edx
0x180001f33  mov     rcx, rsi
0x180001f36  call    _CRT_INIT
0x180001f3b  jmp     short loc_180001F50
0x180001f3d  mov     edi, [rsp+108h+arg_8]
0x180001f44  mov     rsi, [rsp+108h+arg_0]
0x180001f4c  mov     ebx, [rsp+108h+var_E8]
0x180001f50  mov     rax, cs:_pRawDllMain
0x180001f57  test    rax, rax
0x180001f5a  jz      short loc_180001F7F
0x180001f5c  xor     r8d, r8d
0x180001f5f  xor     edx, edx
0x180001f61  mov     rcx, rsi
0x180001f64  call    cs:__guard_dispatch_icall_fptr
0x180001f6a  jmp     short loc_180001F7F
0x180001f6c  mov     edi, [rsp+108h+arg_8]
0x180001f73  mov     rsi, [rsp+108h+arg_0]
0x180001f7b  mov     ebx, [rsp+108h+var_E8]
0x180001f7f  test    edi, edi
0x180001f81  jz      short loc_180001F88
0x180001f83  cmp     edi, 3
0x180001f86  jnz     short loc_180001FF4
0x180001f88  mov     r8, [rsp+108h+lpvReserved]
0x180001f90  mov     edx, edi
0x180001f92  mov     rcx, rsi
0x180001f95  call    _CRT_INIT
0x180001f9a  mov     ebx, eax
0x180001f9c  mov     [rsp+108h+var_E8], eax
0x180001fa0  jmp     short loc_180001FB7
0x180001fa2  xor     ebx, ebx
0x180001fa4  mov     [rsp+108h+var_E8], ebx
0x180001fa8  mov     edi, [rsp+108h+arg_8]
0x180001faf  mov     rsi, [rsp+108h+arg_0]
0x180001fb7  mov     rax, cs:_pRawDllMain
0x180001fbe  test    rax, rax
0x180001fc1  jz      short loc_180001FF4
0x180001fc3  cmp     cs:dword_18001DD90, 0
0x180001fca  jz      short loc_180001FF4
0x180001fcc  mov     r8, [rsp+108h+lpvReserved]
0x180001fd4  mov     edx, edi
0x180001fd6  mov     rcx, rsi
0x180001fd9  call    cs:__guard_dispatch_icall_fptr
0x180001fdf  mov     ebx, eax
0x180001fe1  mov     [rsp+108h+var_E8], eax
0x180001fe5  jmp     short loc_180001FF4
0x180001fe7  xor     ebx, ebx
0x180001fe9  mov     [rsp+108h+var_E8], ebx
0x180001fed  mov     edi, [rsp+108h+arg_8]
0x180001ff4  cmp     edi, 1
0x180001ff7  ja      short loc_180002003
0x180001ff9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002003  mov     eax, ebx
0x180002005  add     rsp, 0F0h
0x18000200c  pop     rdi
0x18000200d  pop     rsi
0x18000200e  pop     rbx
0x18000200f  retn
0x180012982  push    rbp
0x180012984  sub     rsp, 20h
0x180012988  mov     rbp, rdx
0x18001298b  mov     rax, [rcx]
0x18001298e  mov     edx, [rax]
0x180012990  mov     [rbp+0A8h], rcx
0x180012997  mov     [rbp+28h], edx
0x18001299a  mov     eax, [rbp+28h]
0x18001299d  cmp     eax, 0E06D7363h
0x1800129a2  jnz     short loc_1800129B8
0x1800129a4  mov     rdx, [rbp+0A8h]
0x1800129ab  mov     ecx, [rbp+28h]
0x1800129ae  call    _XcptFilter_0
0x1800129b3  mov     [rbp+30h], eax
0x1800129b6  jmp     short loc_1800129BF
0x1800129b8  mov     dword ptr [rbp+30h], 0
0x1800129bf  mov     eax, [rbp+30h]
0x1800129c2  add     rsp, 20h
0x1800129c6  pop     rbp
0x1800129c7  retn
0x1800129c9  push    rbp
0x1800129cb  sub     rsp, 20h
0x1800129cf  mov     rbp, rdx
0x1800129d2  mov     rax, [rcx]
0x1800129d5  mov     edx, [rax]
0x1800129d7  mov     [rbp+0B0h], rcx
0x1800129de  mov     [rbp+38h], edx
0x1800129e1  mov     eax, [rbp+38h]
0x1800129e4  cmp     eax, 0E06D7363h
0x1800129e9  jnz     short loc_1800129FF
0x1800129eb  mov     rdx, [rbp+0B0h]
0x1800129f2  mov     ecx, [rbp+38h]
0x1800129f5  call    _XcptFilter_0
0x1800129fa  mov     [rbp+40h], eax
0x1800129fd  jmp     short loc_180012A06
0x1800129ff  mov     dword ptr [rbp+40h], 0
0x180012a06  mov     eax, [rbp+40h]
0x180012a09  add     rsp, 20h
0x180012a0d  pop     rbp
0x180012a0e  retn
0x180012a10  push    rbp
0x180012a12  sub     rsp, 20h
0x180012a16  mov     rbp, rdx
0x180012a19  mov     rax, [rcx]
0x180012a1c  mov     edx, [rax]
0x180012a1e  mov     [rbp+0B8h], rcx
0x180012a25  mov     [rbp+48h], edx
0x180012a28  mov     eax, [rbp+48h]
0x180012a2b  cmp     eax, 0E06D7363h
0x180012a30  jnz     short loc_180012A46
0x180012a32  mov     rdx, [rbp+0B8h]
0x180012a39  mov     ecx, [rbp+48h]
0x180012a3c  call    _XcptFilter_0
0x180012a41  mov     [rbp+50h], eax
0x180012a44  jmp     short loc_180012A4D
0x180012a46  mov     dword ptr [rbp+50h], 0
0x180012a4d  mov     eax, [rbp+50h]
0x180012a50  add     rsp, 20h
0x180012a54  pop     rbp
0x180012a55  retn
0x180012a57  push    rbp
0x180012a59  sub     rsp, 20h
0x180012a5d  mov     rbp, rdx
0x180012a60  mov     rax, [rcx]
0x180012a63  mov     edx, [rax]
0x180012a65  mov     [rbp+0C0h], rcx
0x180012a6c  mov     [rbp+58h], edx
0x180012a6f  mov     eax, [rbp+58h]
0x180012a72  cmp     eax, 0E06D7363h
0x180012a77  jnz     short loc_180012A8D
0x180012a79  mov     rdx, [rbp+0C0h]
0x180012a80  mov     ecx, [rbp+58h]
0x180012a83  call    _XcptFilter_0
0x180012a88  mov     [rbp+60h], eax
0x180012a8b  jmp     short loc_180012A94
0x180012a8d  mov     dword ptr [rbp+60h], 0
0x180012a94  mov     eax, [rbp+60h]
0x180012a97  add     rsp, 20h
0x180012a9b  pop     rbp
0x180012a9c  retn
0x180012a9e  push    rbp
0x180012aa0  sub     rsp, 20h
0x180012aa4  mov     rbp, rdx
0x180012aa7  mov     rax, [rcx]
0x180012aaa  mov     edx, [rax]
0x180012aac  mov     [rbp+0C8h], rcx
0x180012ab3  mov     [rbp+68h], edx
0x180012ab6  mov     eax, [rbp+68h]
0x180012ab9  cmp     eax, 0E06D7363h
0x180012abe  jnz     short loc_180012AD4
0x180012ac0  mov     rdx, [rbp+0C8h]
0x180012ac7  mov     ecx, [rbp+68h]
0x180012aca  call    _XcptFilter_0
0x180012acf  mov     [rbp+70h], eax
0x180012ad2  jmp     short loc_180012ADB
0x180012ad4  mov     dword ptr [rbp+70h], 0
0x180012adb  mov     eax, [rbp+70h]
0x180012ade  add     rsp, 20h
0x180012ae2  pop     rbp
0x180012ae3  retn
0x180012ae5  push    rbp
0x180012ae7  sub     rsp, 20h
0x180012aeb  mov     rbp, rdx
0x180012aee  mov     rax, [rcx]
0x180012af1  mov     edx, [rax]
0x180012af3  mov     [rbp+0D0h], rcx
0x180012afa  mov     [rbp+78h], edx
0x180012afd  mov     eax, [rbp+78h]
0x180012b00  cmp     eax, 0E06D7363h
0x180012b05  jnz     short loc_180012B1E
0x180012b07  mov     rdx, [rbp+0D0h]
0x180012b0e  mov     ecx, [rbp+78h]
0x180012b11  call    _XcptFilter_0
0x180012b16  mov     [rbp+80h], eax
0x180012b1c  jmp     short loc_180012B28
0x180012b1e  mov     dword ptr [rbp+80h], 0
0x180012b28  mov     eax, [rbp+80h]
0x180012b2e  add     rsp, 20h
0x180012b32  pop     rbp
0x180012b33  retn
0x180012b35  push    rbp
0x180012b37  sub     rsp, 20h
0x180012b3b  mov     rbp, rdx
0x180012b3e  mov     rax, [rcx]
0x180012b41  mov     edx, [rax]
0x180012b43  mov     [rbp+0D8h], rcx
0x180012b4a  mov     [rbp+88h], edx
0x180012b50  mov     eax, [rbp+88h]
0x180012b56  cmp     eax, 0E06D7363h
0x180012b5b  jnz     short loc_180012B77
0x180012b5d  mov     rdx, [rbp+0D8h]
0x180012b64  mov     ecx, [rbp+88h]
0x180012b6a  call    _XcptFilter_0
0x180012b6f  mov     [rbp+90h], eax
0x180012b75  jmp     short loc_180012B81
0x180012b77  mov     dword ptr [rbp+90h], 0
0x180012b81  mov     eax, [rbp+90h]
0x180012b87  add     rsp, 20h
0x180012b8b  pop     rbp
0x180012b8c  retn
0x180012b8e  push    rbp
0x180012b90  sub     rsp, 20h
0x180012b94  mov     rbp, rdx
0x180012b97  mov     rax, [rcx]
0x180012b9a  mov     edx, [rax]
0x180012b9c  mov     [rbp+0E0h], rcx
0x180012ba3  mov     [rbp+98h], edx
0x180012ba9  mov     eax, [rbp+98h]
0x180012baf  cmp     eax, 0E06D7363h
0x180012bb4  jnz     short loc_180012BD0
0x180012bb6  mov     rdx, [rbp+0E0h]
0x180012bbd  mov     ecx, [rbp+98h]
0x180012bc3  call    _XcptFilter_0
0x180012bc8  mov     [rbp+0A0h], eax
0x180012bce  jmp     short loc_180012BDA
0x180012bd0  mov     dword ptr [rbp+0A0h], 0
0x180012bda  mov     eax, [rbp+0A0h]
0x180012be0  add     rsp, 20h
0x180012be4  pop     rbp
0x180012be5  retn
0x180012be7  push    rbp
0x180012be9  sub     rsp, 20h
0x180012bed  mov     rbp, rdx
0x180012bf0  cmp     dword ptr [rbp+118h], 1
0x180012bf7  ja      short loc_180012C03
0x180012bf9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
