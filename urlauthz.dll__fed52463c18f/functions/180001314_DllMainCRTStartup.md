# __DllMainCRTStartup

- ea: `0x180001314`
- end: `0x180001520`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x1800010a0`
- `0x180001314`
- `0x18000154a`
- `0x180001728`
- `0x180003c20`

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
0x180001314  mov     [rsp+lpvReserved], r8
0x180001319  mov     [rsp+arg_8], edx
0x18000131d  mov     [rsp+arg_0], rcx
0x180001322  push    rbx
0x180001323  push    rsi
0x180001324  push    rdi
0x180001325  sub     rsp, 0F0h
0x18000132c  mov     edi, edx
0x18000132e  mov     rsi, rcx
0x180001331  mov     ebx, 1
0x180001336  cmp     edx, ebx
0x180001338  ja      short loc_180001340
0x18000133a  mov     cs:__native_dllmain_reason, edx
0x180001340  test    edx, edx
0x180001342  jnz     short loc_180001357
0x180001344  cmp     cs:dword_1800070A0, edx
0x18000134a  jnz     short loc_180001357
0x18000134c  xor     ebx, ebx
0x18000134e  mov     [rsp+108h+var_E8], ebx
0x180001352  jmp     loc_180001504
0x180001357  lea     eax, [rdx-1]
0x18000135a  cmp     eax, 1
0x18000135d  ja      loc_1800013E4
0x180001363  mov     rax, cs:_pRawDllMain
0x18000136a  test    rax, rax
0x18000136d  jz      short loc_1800013A5
0x18000136f  cmp     edx, 1
0x180001372  jnz     short loc_18000137A
0x180001374  mov     cs:dword_1800070A4, edx
0x18000137a  mov     r8, [rsp+108h+lpvReserved]
0x180001382  call    cs:__guard_dispatch_icall_fptr
0x180001388  mov     ebx, eax
0x18000138a  mov     [rsp+108h+var_E8], eax
0x18000138e  jmp     short loc_1800013A5
0x180001390  xor     ebx, ebx
0x180001392  mov     [rsp+108h+var_E8], ebx
0x180001396  mov     edi, [rsp+108h+arg_8]
0x18000139d  mov     rsi, [rsp+108h+arg_0]
0x1800013a5  test    ebx, ebx
0x1800013a7  jz      loc_180001504
0x1800013ad  mov     r8, [rsp+108h+lpvReserved]
0x1800013b5  mov     edx, edi
0x1800013b7  mov     rcx, rsi
0x1800013ba  call    _CRT_INIT
0x1800013bf  mov     ebx, eax
0x1800013c1  mov     [rsp+108h+var_E8], eax
0x1800013c5  jmp     short loc_1800013DC
0x1800013c7  xor     ebx, ebx
0x1800013c9  mov     [rsp+108h+var_E8], ebx
0x1800013cd  mov     edi, [rsp+108h+arg_8]
0x1800013d4  mov     rsi, [rsp+108h+arg_0]
0x1800013dc  test    ebx, ebx
0x1800013de  jz      loc_180001504
0x1800013e4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013ec  mov     edx, edi; fdwReason
0x1800013ee  mov     rcx, rsi; hinstDLL
0x1800013f1  call    DllMain
0x1800013f6  mov     ebx, eax
0x1800013f8  mov     [rsp+108h+var_E8], eax
0x1800013fc  jmp     short loc_180001413
0x1800013fe  xor     ebx, ebx
0x180001400  mov     [rsp+108h+var_E8], ebx
0x180001404  mov     edi, [rsp+108h+arg_8]
0x18000140b  mov     rsi, [rsp+108h+arg_0]
0x180001413  cmp     edi, 1
0x180001416  jnz     short loc_18000148F
0x180001418  test    ebx, ebx
0x18000141a  jnz     short loc_18000148F
0x18000141c  xor     r8d, r8d; lpvReserved
0x18000141f  xor     edx, edx; fdwReason
0x180001421  mov     rcx, rsi; hinstDLL
0x180001424  call    DllMain
0x180001429  jmp     short loc_18000143E
0x18000142b  mov     edi, [rsp+108h+arg_8]
0x180001432  mov     rsi, [rsp+108h+arg_0]
0x18000143a  mov     ebx, [rsp+108h+var_E8]
0x18000143e  xor     r8d, r8d
0x180001441  xor     edx, edx
0x180001443  mov     rcx, rsi
0x180001446  call    _CRT_INIT
0x18000144b  jmp     short loc_180001460
0x18000144d  mov     edi, [rsp+108h+arg_8]
0x180001454  mov     rsi, [rsp+108h+arg_0]
0x18000145c  mov     ebx, [rsp+108h+var_E8]
0x180001460  mov     rax, cs:_pRawDllMain
0x180001467  test    rax, rax
0x18000146a  jz      short loc_18000148F
0x18000146c  xor     r8d, r8d
0x18000146f  xor     edx, edx
0x180001471  mov     rcx, rsi
0x180001474  call    cs:__guard_dispatch_icall_fptr
0x18000147a  jmp     short loc_18000148F
0x18000147c  mov     edi, [rsp+108h+arg_8]
0x180001483  mov     rsi, [rsp+108h+arg_0]
0x18000148b  mov     ebx, [rsp+108h+var_E8]
0x18000148f  test    edi, edi
0x180001491  jz      short loc_180001498
0x180001493  cmp     edi, 3
0x180001496  jnz     short loc_180001504
0x180001498  mov     r8, [rsp+108h+lpvReserved]
0x1800014a0  mov     edx, edi
0x1800014a2  mov     rcx, rsi
0x1800014a5  call    _CRT_INIT
0x1800014aa  mov     ebx, eax
0x1800014ac  mov     [rsp+108h+var_E8], eax
0x1800014b0  jmp     short loc_1800014C7
0x1800014b2  xor     ebx, ebx
0x1800014b4  mov     [rsp+108h+var_E8], ebx
0x1800014b8  mov     edi, [rsp+108h+arg_8]
0x1800014bf  mov     rsi, [rsp+108h+arg_0]
0x1800014c7  mov     rax, cs:_pRawDllMain
0x1800014ce  test    rax, rax
0x1800014d1  jz      short loc_180001504
0x1800014d3  cmp     cs:dword_1800070A4, 0
0x1800014da  jz      short loc_180001504
0x1800014dc  mov     r8, [rsp+108h+lpvReserved]
0x1800014e4  mov     edx, edi
0x1800014e6  mov     rcx, rsi
0x1800014e9  call    cs:__guard_dispatch_icall_fptr
0x1800014ef  mov     ebx, eax
0x1800014f1  mov     [rsp+108h+var_E8], eax
0x1800014f5  jmp     short loc_180001504
0x1800014f7  xor     ebx, ebx
0x1800014f9  mov     [rsp+108h+var_E8], ebx
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  cmp     edi, 1
0x180001507  ja      short loc_180001513
0x180001509  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001513  mov     eax, ebx
0x180001515  add     rsp, 0F0h
0x18000151c  pop     rdi
0x18000151d  pop     rsi
0x18000151e  pop     rbx
0x18000151f  retn
0x180003c90  push    rbp
0x180003c92  sub     rsp, 20h
0x180003c96  mov     rbp, rdx
0x180003c99  mov     rax, [rcx]
0x180003c9c  mov     edx, [rax]
0x180003c9e  mov     [rbp+0A8h], rcx
0x180003ca5  mov     [rbp+28h], edx
0x180003ca8  mov     eax, [rbp+28h]
0x180003cab  cmp     eax, 0E06D7363h
0x180003cb0  jnz     short loc_180003CC6
0x180003cb2  mov     rdx, [rbp+0A8h]
0x180003cb9  mov     ecx, [rbp+28h]
0x180003cbc  call    _XcptFilter_0
0x180003cc1  mov     [rbp+30h], eax
0x180003cc4  jmp     short loc_180003CCD
0x180003cc6  mov     dword ptr [rbp+30h], 0
0x180003ccd  mov     eax, [rbp+30h]
0x180003cd0  add     rsp, 20h
0x180003cd4  pop     rbp
0x180003cd5  retn
0x180003cd7  push    rbp
0x180003cd9  sub     rsp, 20h
0x180003cdd  mov     rbp, rdx
0x180003ce0  mov     rax, [rcx]
0x180003ce3  mov     edx, [rax]
0x180003ce5  mov     [rbp+0B0h], rcx
0x180003cec  mov     [rbp+38h], edx
0x180003cef  mov     eax, [rbp+38h]
0x180003cf2  cmp     eax, 0E06D7363h
0x180003cf7  jnz     short loc_180003D0D
0x180003cf9  mov     rdx, [rbp+0B0h]
0x180003d00  mov     ecx, [rbp+38h]
0x180003d03  call    _XcptFilter_0
0x180003d08  mov     [rbp+40h], eax
0x180003d0b  jmp     short loc_180003D14
0x180003d0d  mov     dword ptr [rbp+40h], 0
0x180003d14  mov     eax, [rbp+40h]
0x180003d17  add     rsp, 20h
0x180003d1b  pop     rbp
0x180003d1c  retn
0x180003d1e  push    rbp
0x180003d20  sub     rsp, 20h
0x180003d24  mov     rbp, rdx
0x180003d27  mov     rax, [rcx]
0x180003d2a  mov     edx, [rax]
0x180003d2c  mov     [rbp+0B8h], rcx
0x180003d33  mov     [rbp+48h], edx
0x180003d36  mov     eax, [rbp+48h]
0x180003d39  cmp     eax, 0E06D7363h
0x180003d3e  jnz     short loc_180003D54
0x180003d40  mov     rdx, [rbp+0B8h]
0x180003d47  mov     ecx, [rbp+48h]
0x180003d4a  call    _XcptFilter_0
0x180003d4f  mov     [rbp+50h], eax
0x180003d52  jmp     short loc_180003D5B
0x180003d54  mov     dword ptr [rbp+50h], 0
0x180003d5b  mov     eax, [rbp+50h]
0x180003d5e  add     rsp, 20h
0x180003d62  pop     rbp
0x180003d63  retn
0x180003d65  push    rbp
0x180003d67  sub     rsp, 20h
0x180003d6b  mov     rbp, rdx
0x180003d6e  mov     rax, [rcx]
0x180003d71  mov     edx, [rax]
0x180003d73  mov     [rbp+0C0h], rcx
0x180003d7a  mov     [rbp+58h], edx
0x180003d7d  mov     eax, [rbp+58h]
0x180003d80  cmp     eax, 0E06D7363h
0x180003d85  jnz     short loc_180003D9B
0x180003d87  mov     rdx, [rbp+0C0h]
0x180003d8e  mov     ecx, [rbp+58h]
0x180003d91  call    _XcptFilter_0
0x180003d96  mov     [rbp+60h], eax
0x180003d99  jmp     short loc_180003DA2
0x180003d9b  mov     dword ptr [rbp+60h], 0
0x180003da2  mov     eax, [rbp+60h]
0x180003da5  add     rsp, 20h
0x180003da9  pop     rbp
0x180003daa  retn
0x180003dac  push    rbp
0x180003dae  sub     rsp, 20h
0x180003db2  mov     rbp, rdx
0x180003db5  mov     rax, [rcx]
0x180003db8  mov     edx, [rax]
0x180003dba  mov     [rbp+0C8h], rcx
0x180003dc1  mov     [rbp+68h], edx
0x180003dc4  mov     eax, [rbp+68h]
0x180003dc7  cmp     eax, 0E06D7363h
0x180003dcc  jnz     short loc_180003DE2
0x180003dce  mov     rdx, [rbp+0C8h]
0x180003dd5  mov     ecx, [rbp+68h]
0x180003dd8  call    _XcptFilter_0
0x180003ddd  mov     [rbp+70h], eax
0x180003de0  jmp     short loc_180003DE9
0x180003de2  mov     dword ptr [rbp+70h], 0
0x180003de9  mov     eax, [rbp+70h]
0x180003dec  add     rsp, 20h
0x180003df0  pop     rbp
0x180003df1  retn
0x180003df3  push    rbp
0x180003df5  sub     rsp, 20h
0x180003df9  mov     rbp, rdx
0x180003dfc  mov     rax, [rcx]
0x180003dff  mov     edx, [rax]
0x180003e01  mov     [rbp+0D0h], rcx
0x180003e08  mov     [rbp+78h], edx
0x180003e0b  mov     eax, [rbp+78h]
0x180003e0e  cmp     eax, 0E06D7363h
0x180003e13  jnz     short loc_180003E2C
0x180003e15  mov     rdx, [rbp+0D0h]
0x180003e1c  mov     ecx, [rbp+78h]
0x180003e1f  call    _XcptFilter_0
0x180003e24  mov     [rbp+80h], eax
0x180003e2a  jmp     short loc_180003E36
0x180003e2c  mov     dword ptr [rbp+80h], 0
0x180003e36  mov     eax, [rbp+80h]
0x180003e3c  add     rsp, 20h
0x180003e40  pop     rbp
0x180003e41  retn
0x180003e43  push    rbp
0x180003e45  sub     rsp, 20h
0x180003e49  mov     rbp, rdx
0x180003e4c  mov     rax, [rcx]
0x180003e4f  mov     edx, [rax]
0x180003e51  mov     [rbp+0D8h], rcx
0x180003e58  mov     [rbp+88h], edx
0x180003e5e  mov     eax, [rbp+88h]
0x180003e64  cmp     eax, 0E06D7363h
0x180003e69  jnz     short loc_180003E85
0x180003e6b  mov     rdx, [rbp+0D8h]
0x180003e72  mov     ecx, [rbp+88h]
0x180003e78  call    _XcptFilter_0
0x180003e7d  mov     [rbp+90h], eax
0x180003e83  jmp     short loc_180003E8F
0x180003e85  mov     dword ptr [rbp+90h], 0
0x180003e8f  mov     eax, [rbp+90h]
0x180003e95  add     rsp, 20h
0x180003e99  pop     rbp
0x180003e9a  retn
0x180003e9c  push    rbp
0x180003e9e  sub     rsp, 20h
0x180003ea2  mov     rbp, rdx
0x180003ea5  mov     rax, [rcx]
0x180003ea8  mov     edx, [rax]
0x180003eaa  mov     [rbp+0E0h], rcx
0x180003eb1  mov     [rbp+98h], edx
0x180003eb7  mov     eax, [rbp+98h]
0x180003ebd  cmp     eax, 0E06D7363h
0x180003ec2  jnz     short loc_180003EDE
0x180003ec4  mov     rdx, [rbp+0E0h]
0x180003ecb  mov     ecx, [rbp+98h]
0x180003ed1  call    _XcptFilter_0
0x180003ed6  mov     [rbp+0A0h], eax
0x180003edc  jmp     short loc_180003EE8
0x180003ede  mov     dword ptr [rbp+0A0h], 0
0x180003ee8  mov     eax, [rbp+0A0h]
0x180003eee  add     rsp, 20h
0x180003ef2  pop     rbp
0x180003ef3  retn
0x180003ef5  push    rbp
0x180003ef7  sub     rsp, 20h
0x180003efb  mov     rbp, rdx
0x180003efe  cmp     dword ptr [rbp+118h], 1
0x180003f05  ja      short loc_180003F11
0x180003f07  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
