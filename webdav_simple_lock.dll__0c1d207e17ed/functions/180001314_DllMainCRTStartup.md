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
- `0x180001560`
- `0x180001a8c`
- `0x180003c70`

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
0x180003d40  push    rbp
0x180003d42  sub     rsp, 20h
0x180003d46  mov     rbp, rdx
0x180003d49  mov     rax, [rcx]
0x180003d4c  mov     edx, [rax]
0x180003d4e  mov     [rbp+0A8h], rcx
0x180003d55  mov     [rbp+28h], edx
0x180003d58  mov     eax, [rbp+28h]
0x180003d5b  cmp     eax, 0E06D7363h
0x180003d60  jnz     short loc_180003D76
0x180003d62  mov     rdx, [rbp+0A8h]
0x180003d69  mov     ecx, [rbp+28h]
0x180003d6c  call    _XcptFilter_0
0x180003d71  mov     [rbp+30h], eax
0x180003d74  jmp     short loc_180003D7D
0x180003d76  mov     dword ptr [rbp+30h], 0
0x180003d7d  mov     eax, [rbp+30h]
0x180003d80  add     rsp, 20h
0x180003d84  pop     rbp
0x180003d85  retn
0x180003d87  push    rbp
0x180003d89  sub     rsp, 20h
0x180003d8d  mov     rbp, rdx
0x180003d90  mov     rax, [rcx]
0x180003d93  mov     edx, [rax]
0x180003d95  mov     [rbp+0B0h], rcx
0x180003d9c  mov     [rbp+38h], edx
0x180003d9f  mov     eax, [rbp+38h]
0x180003da2  cmp     eax, 0E06D7363h
0x180003da7  jnz     short loc_180003DBD
0x180003da9  mov     rdx, [rbp+0B0h]
0x180003db0  mov     ecx, [rbp+38h]
0x180003db3  call    _XcptFilter_0
0x180003db8  mov     [rbp+40h], eax
0x180003dbb  jmp     short loc_180003DC4
0x180003dbd  mov     dword ptr [rbp+40h], 0
0x180003dc4  mov     eax, [rbp+40h]
0x180003dc7  add     rsp, 20h
0x180003dcb  pop     rbp
0x180003dcc  retn
0x180003dce  push    rbp
0x180003dd0  sub     rsp, 20h
0x180003dd4  mov     rbp, rdx
0x180003dd7  mov     rax, [rcx]
0x180003dda  mov     edx, [rax]
0x180003ddc  mov     [rbp+0B8h], rcx
0x180003de3  mov     [rbp+48h], edx
0x180003de6  mov     eax, [rbp+48h]
0x180003de9  cmp     eax, 0E06D7363h
0x180003dee  jnz     short loc_180003E04
0x180003df0  mov     rdx, [rbp+0B8h]
0x180003df7  mov     ecx, [rbp+48h]
0x180003dfa  call    _XcptFilter_0
0x180003dff  mov     [rbp+50h], eax
0x180003e02  jmp     short loc_180003E0B
0x180003e04  mov     dword ptr [rbp+50h], 0
0x180003e0b  mov     eax, [rbp+50h]
0x180003e0e  add     rsp, 20h
0x180003e12  pop     rbp
0x180003e13  retn
0x180003e15  push    rbp
0x180003e17  sub     rsp, 20h
0x180003e1b  mov     rbp, rdx
0x180003e1e  mov     rax, [rcx]
0x180003e21  mov     edx, [rax]
0x180003e23  mov     [rbp+0C0h], rcx
0x180003e2a  mov     [rbp+58h], edx
0x180003e2d  mov     eax, [rbp+58h]
0x180003e30  cmp     eax, 0E06D7363h
0x180003e35  jnz     short loc_180003E4B
0x180003e37  mov     rdx, [rbp+0C0h]
0x180003e3e  mov     ecx, [rbp+58h]
0x180003e41  call    _XcptFilter_0
0x180003e46  mov     [rbp+60h], eax
0x180003e49  jmp     short loc_180003E52
0x180003e4b  mov     dword ptr [rbp+60h], 0
0x180003e52  mov     eax, [rbp+60h]
0x180003e55  add     rsp, 20h
0x180003e59  pop     rbp
0x180003e5a  retn
0x180003e5c  push    rbp
0x180003e5e  sub     rsp, 20h
0x180003e62  mov     rbp, rdx
0x180003e65  mov     rax, [rcx]
0x180003e68  mov     edx, [rax]
0x180003e6a  mov     [rbp+0C8h], rcx
0x180003e71  mov     [rbp+68h], edx
0x180003e74  mov     eax, [rbp+68h]
0x180003e77  cmp     eax, 0E06D7363h
0x180003e7c  jnz     short loc_180003E92
0x180003e7e  mov     rdx, [rbp+0C8h]
0x180003e85  mov     ecx, [rbp+68h]
0x180003e88  call    _XcptFilter_0
0x180003e8d  mov     [rbp+70h], eax
0x180003e90  jmp     short loc_180003E99
0x180003e92  mov     dword ptr [rbp+70h], 0
0x180003e99  mov     eax, [rbp+70h]
0x180003e9c  add     rsp, 20h
0x180003ea0  pop     rbp
0x180003ea1  retn
0x180003ea3  push    rbp
0x180003ea5  sub     rsp, 20h
0x180003ea9  mov     rbp, rdx
0x180003eac  mov     rax, [rcx]
0x180003eaf  mov     edx, [rax]
0x180003eb1  mov     [rbp+0D0h], rcx
0x180003eb8  mov     [rbp+78h], edx
0x180003ebb  mov     eax, [rbp+78h]
0x180003ebe  cmp     eax, 0E06D7363h
0x180003ec3  jnz     short loc_180003EDC
0x180003ec5  mov     rdx, [rbp+0D0h]
0x180003ecc  mov     ecx, [rbp+78h]
0x180003ecf  call    _XcptFilter_0
0x180003ed4  mov     [rbp+80h], eax
0x180003eda  jmp     short loc_180003EE6
0x180003edc  mov     dword ptr [rbp+80h], 0
0x180003ee6  mov     eax, [rbp+80h]
0x180003eec  add     rsp, 20h
0x180003ef0  pop     rbp
0x180003ef1  retn
0x180003ef3  push    rbp
0x180003ef5  sub     rsp, 20h
0x180003ef9  mov     rbp, rdx
0x180003efc  mov     rax, [rcx]
0x180003eff  mov     edx, [rax]
0x180003f01  mov     [rbp+0D8h], rcx
0x180003f08  mov     [rbp+88h], edx
0x180003f0e  mov     eax, [rbp+88h]
0x180003f14  cmp     eax, 0E06D7363h
0x180003f19  jnz     short loc_180003F35
0x180003f1b  mov     rdx, [rbp+0D8h]
0x180003f22  mov     ecx, [rbp+88h]
0x180003f28  call    _XcptFilter_0
0x180003f2d  mov     [rbp+90h], eax
0x180003f33  jmp     short loc_180003F3F
0x180003f35  mov     dword ptr [rbp+90h], 0
0x180003f3f  mov     eax, [rbp+90h]
0x180003f45  add     rsp, 20h
0x180003f49  pop     rbp
0x180003f4a  retn
0x180003f4c  push    rbp
0x180003f4e  sub     rsp, 20h
0x180003f52  mov     rbp, rdx
0x180003f55  mov     rax, [rcx]
0x180003f58  mov     edx, [rax]
0x180003f5a  mov     [rbp+0E0h], rcx
0x180003f61  mov     [rbp+98h], edx
0x180003f67  mov     eax, [rbp+98h]
0x180003f6d  cmp     eax, 0E06D7363h
0x180003f72  jnz     short loc_180003F8E
0x180003f74  mov     rdx, [rbp+0E0h]
0x180003f7b  mov     ecx, [rbp+98h]
0x180003f81  call    _XcptFilter_0
0x180003f86  mov     [rbp+0A0h], eax
0x180003f8c  jmp     short loc_180003F98
0x180003f8e  mov     dword ptr [rbp+0A0h], 0
0x180003f98  mov     eax, [rbp+0A0h]
0x180003f9e  add     rsp, 20h
0x180003fa2  pop     rbp
0x180003fa3  retn
0x180003fa5  push    rbp
0x180003fa7  sub     rsp, 20h
0x180003fab  mov     rbp, rdx
0x180003fae  cmp     dword ptr [rbp+118h], 1
0x180003fb5  ja      short loc_180003FC1
0x180003fb7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
