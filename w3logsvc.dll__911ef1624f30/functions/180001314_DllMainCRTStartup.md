# __DllMainCRTStartup

- ea: `0x180001314`
- end: `0x180001520`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x1800010a0`
- `0x180001314`
- `0x18000156d`
- `0x180001db0`
- `0x18000e9e0`

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
  if ( (_DWORD)fdwReason || dword_180018140 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180018144 = 1;
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
            if ( dword_180018144 )
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
0x180001344  cmp     cs:dword_180018140, edx
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
0x180001374  mov     cs:dword_180018144, edx
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
0x1800014d3  cmp     cs:dword_180018144, 0
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
0x18000ea50  push    rbp
0x18000ea52  sub     rsp, 20h
0x18000ea56  mov     rbp, rdx
0x18000ea59  mov     rax, [rcx]
0x18000ea5c  mov     edx, [rax]
0x18000ea5e  mov     [rbp+0A8h], rcx
0x18000ea65  mov     [rbp+28h], edx
0x18000ea68  mov     eax, [rbp+28h]
0x18000ea6b  cmp     eax, 0E06D7363h
0x18000ea70  jnz     short loc_18000EA86
0x18000ea72  mov     rdx, [rbp+0A8h]
0x18000ea79  mov     ecx, [rbp+28h]
0x18000ea7c  call    _XcptFilter_0
0x18000ea81  mov     [rbp+30h], eax
0x18000ea84  jmp     short loc_18000EA8D
0x18000ea86  mov     dword ptr [rbp+30h], 0
0x18000ea8d  mov     eax, [rbp+30h]
0x18000ea90  add     rsp, 20h
0x18000ea94  pop     rbp
0x18000ea95  retn
0x18000ea97  push    rbp
0x18000ea99  sub     rsp, 20h
0x18000ea9d  mov     rbp, rdx
0x18000eaa0  mov     rax, [rcx]
0x18000eaa3  mov     edx, [rax]
0x18000eaa5  mov     [rbp+0B0h], rcx
0x18000eaac  mov     [rbp+38h], edx
0x18000eaaf  mov     eax, [rbp+38h]
0x18000eab2  cmp     eax, 0E06D7363h
0x18000eab7  jnz     short loc_18000EACD
0x18000eab9  mov     rdx, [rbp+0B0h]
0x18000eac0  mov     ecx, [rbp+38h]
0x18000eac3  call    _XcptFilter_0
0x18000eac8  mov     [rbp+40h], eax
0x18000eacb  jmp     short loc_18000EAD4
0x18000eacd  mov     dword ptr [rbp+40h], 0
0x18000ead4  mov     eax, [rbp+40h]
0x18000ead7  add     rsp, 20h
0x18000eadb  pop     rbp
0x18000eadc  retn
0x18000eade  push    rbp
0x18000eae0  sub     rsp, 20h
0x18000eae4  mov     rbp, rdx
0x18000eae7  mov     rax, [rcx]
0x18000eaea  mov     edx, [rax]
0x18000eaec  mov     [rbp+0B8h], rcx
0x18000eaf3  mov     [rbp+48h], edx
0x18000eaf6  mov     eax, [rbp+48h]
0x18000eaf9  cmp     eax, 0E06D7363h
0x18000eafe  jnz     short loc_18000EB14
0x18000eb00  mov     rdx, [rbp+0B8h]
0x18000eb07  mov     ecx, [rbp+48h]
0x18000eb0a  call    _XcptFilter_0
0x18000eb0f  mov     [rbp+50h], eax
0x18000eb12  jmp     short loc_18000EB1B
0x18000eb14  mov     dword ptr [rbp+50h], 0
0x18000eb1b  mov     eax, [rbp+50h]
0x18000eb1e  add     rsp, 20h
0x18000eb22  pop     rbp
0x18000eb23  retn
0x18000eb25  push    rbp
0x18000eb27  sub     rsp, 20h
0x18000eb2b  mov     rbp, rdx
0x18000eb2e  mov     rax, [rcx]
0x18000eb31  mov     edx, [rax]
0x18000eb33  mov     [rbp+0C0h], rcx
0x18000eb3a  mov     [rbp+58h], edx
0x18000eb3d  mov     eax, [rbp+58h]
0x18000eb40  cmp     eax, 0E06D7363h
0x18000eb45  jnz     short loc_18000EB5B
0x18000eb47  mov     rdx, [rbp+0C0h]
0x18000eb4e  mov     ecx, [rbp+58h]
0x18000eb51  call    _XcptFilter_0
0x18000eb56  mov     [rbp+60h], eax
0x18000eb59  jmp     short loc_18000EB62
0x18000eb5b  mov     dword ptr [rbp+60h], 0
0x18000eb62  mov     eax, [rbp+60h]
0x18000eb65  add     rsp, 20h
0x18000eb69  pop     rbp
0x18000eb6a  retn
0x18000eb6c  push    rbp
0x18000eb6e  sub     rsp, 20h
0x18000eb72  mov     rbp, rdx
0x18000eb75  mov     rax, [rcx]
0x18000eb78  mov     edx, [rax]
0x18000eb7a  mov     [rbp+0C8h], rcx
0x18000eb81  mov     [rbp+68h], edx
0x18000eb84  mov     eax, [rbp+68h]
0x18000eb87  cmp     eax, 0E06D7363h
0x18000eb8c  jnz     short loc_18000EBA2
0x18000eb8e  mov     rdx, [rbp+0C8h]
0x18000eb95  mov     ecx, [rbp+68h]
0x18000eb98  call    _XcptFilter_0
0x18000eb9d  mov     [rbp+70h], eax
0x18000eba0  jmp     short loc_18000EBA9
0x18000eba2  mov     dword ptr [rbp+70h], 0
0x18000eba9  mov     eax, [rbp+70h]
0x18000ebac  add     rsp, 20h
0x18000ebb0  pop     rbp
0x18000ebb1  retn
0x18000ebb3  push    rbp
0x18000ebb5  sub     rsp, 20h
0x18000ebb9  mov     rbp, rdx
0x18000ebbc  mov     rax, [rcx]
0x18000ebbf  mov     edx, [rax]
0x18000ebc1  mov     [rbp+0D0h], rcx
0x18000ebc8  mov     [rbp+78h], edx
0x18000ebcb  mov     eax, [rbp+78h]
0x18000ebce  cmp     eax, 0E06D7363h
0x18000ebd3  jnz     short loc_18000EBEC
0x18000ebd5  mov     rdx, [rbp+0D0h]
0x18000ebdc  mov     ecx, [rbp+78h]
0x18000ebdf  call    _XcptFilter_0
0x18000ebe4  mov     [rbp+80h], eax
0x18000ebea  jmp     short loc_18000EBF6
0x18000ebec  mov     dword ptr [rbp+80h], 0
0x18000ebf6  mov     eax, [rbp+80h]
0x18000ebfc  add     rsp, 20h
0x18000ec00  pop     rbp
0x18000ec01  retn
0x18000ec03  push    rbp
0x18000ec05  sub     rsp, 20h
0x18000ec09  mov     rbp, rdx
0x18000ec0c  mov     rax, [rcx]
0x18000ec0f  mov     edx, [rax]
0x18000ec11  mov     [rbp+0D8h], rcx
0x18000ec18  mov     [rbp+88h], edx
0x18000ec1e  mov     eax, [rbp+88h]
0x18000ec24  cmp     eax, 0E06D7363h
0x18000ec29  jnz     short loc_18000EC45
0x18000ec2b  mov     rdx, [rbp+0D8h]
0x18000ec32  mov     ecx, [rbp+88h]
0x18000ec38  call    _XcptFilter_0
0x18000ec3d  mov     [rbp+90h], eax
0x18000ec43  jmp     short loc_18000EC4F
0x18000ec45  mov     dword ptr [rbp+90h], 0
0x18000ec4f  mov     eax, [rbp+90h]
0x18000ec55  add     rsp, 20h
0x18000ec59  pop     rbp
0x18000ec5a  retn
0x18000ec5c  push    rbp
0x18000ec5e  sub     rsp, 20h
0x18000ec62  mov     rbp, rdx
0x18000ec65  mov     rax, [rcx]
0x18000ec68  mov     edx, [rax]
0x18000ec6a  mov     [rbp+0E0h], rcx
0x18000ec71  mov     [rbp+98h], edx
0x18000ec77  mov     eax, [rbp+98h]
0x18000ec7d  cmp     eax, 0E06D7363h
0x18000ec82  jnz     short loc_18000EC9E
0x18000ec84  mov     rdx, [rbp+0E0h]
0x18000ec8b  mov     ecx, [rbp+98h]
0x18000ec91  call    _XcptFilter_0
0x18000ec96  mov     [rbp+0A0h], eax
0x18000ec9c  jmp     short loc_18000ECA8
0x18000ec9e  mov     dword ptr [rbp+0A0h], 0
0x18000eca8  mov     eax, [rbp+0A0h]
0x18000ecae  add     rsp, 20h
0x18000ecb2  pop     rbp
0x18000ecb3  retn
0x18000ecb5  push    rbp
0x18000ecb7  sub     rsp, 20h
0x18000ecbb  mov     rbp, rdx
0x18000ecbe  cmp     dword ptr [rbp+118h], 1
0x18000ecc5  ja      short loc_18000ECD1
0x18000ecc7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
