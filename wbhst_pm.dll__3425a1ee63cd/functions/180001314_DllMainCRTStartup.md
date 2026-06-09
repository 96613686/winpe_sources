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
- `0x1800048c0`

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
  if ( (_DWORD)fdwReason || dword_1800090C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800090C4 = 1;
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
            if ( dword_1800090C4 )
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
0x180001344  cmp     cs:dword_1800090C0, edx
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
0x180001374  mov     cs:dword_1800090C4, edx
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
0x1800014d3  cmp     cs:dword_1800090C4, 0
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
0x180004930  push    rbp
0x180004932  sub     rsp, 20h
0x180004936  mov     rbp, rdx
0x180004939  mov     rax, [rcx]
0x18000493c  mov     edx, [rax]
0x18000493e  mov     [rbp+0A8h], rcx
0x180004945  mov     [rbp+28h], edx
0x180004948  mov     eax, [rbp+28h]
0x18000494b  cmp     eax, 0E06D7363h
0x180004950  jnz     short loc_180004966
0x180004952  mov     rdx, [rbp+0A8h]
0x180004959  mov     ecx, [rbp+28h]
0x18000495c  call    _XcptFilter_0
0x180004961  mov     [rbp+30h], eax
0x180004964  jmp     short loc_18000496D
0x180004966  mov     dword ptr [rbp+30h], 0
0x18000496d  mov     eax, [rbp+30h]
0x180004970  add     rsp, 20h
0x180004974  pop     rbp
0x180004975  retn
0x180004977  push    rbp
0x180004979  sub     rsp, 20h
0x18000497d  mov     rbp, rdx
0x180004980  mov     rax, [rcx]
0x180004983  mov     edx, [rax]
0x180004985  mov     [rbp+0B0h], rcx
0x18000498c  mov     [rbp+38h], edx
0x18000498f  mov     eax, [rbp+38h]
0x180004992  cmp     eax, 0E06D7363h
0x180004997  jnz     short loc_1800049AD
0x180004999  mov     rdx, [rbp+0B0h]
0x1800049a0  mov     ecx, [rbp+38h]
0x1800049a3  call    _XcptFilter_0
0x1800049a8  mov     [rbp+40h], eax
0x1800049ab  jmp     short loc_1800049B4
0x1800049ad  mov     dword ptr [rbp+40h], 0
0x1800049b4  mov     eax, [rbp+40h]
0x1800049b7  add     rsp, 20h
0x1800049bb  pop     rbp
0x1800049bc  retn
0x1800049be  push    rbp
0x1800049c0  sub     rsp, 20h
0x1800049c4  mov     rbp, rdx
0x1800049c7  mov     rax, [rcx]
0x1800049ca  mov     edx, [rax]
0x1800049cc  mov     [rbp+0B8h], rcx
0x1800049d3  mov     [rbp+48h], edx
0x1800049d6  mov     eax, [rbp+48h]
0x1800049d9  cmp     eax, 0E06D7363h
0x1800049de  jnz     short loc_1800049F4
0x1800049e0  mov     rdx, [rbp+0B8h]
0x1800049e7  mov     ecx, [rbp+48h]
0x1800049ea  call    _XcptFilter_0
0x1800049ef  mov     [rbp+50h], eax
0x1800049f2  jmp     short loc_1800049FB
0x1800049f4  mov     dword ptr [rbp+50h], 0
0x1800049fb  mov     eax, [rbp+50h]
0x1800049fe  add     rsp, 20h
0x180004a02  pop     rbp
0x180004a03  retn
0x180004a05  push    rbp
0x180004a07  sub     rsp, 20h
0x180004a0b  mov     rbp, rdx
0x180004a0e  mov     rax, [rcx]
0x180004a11  mov     edx, [rax]
0x180004a13  mov     [rbp+0C0h], rcx
0x180004a1a  mov     [rbp+58h], edx
0x180004a1d  mov     eax, [rbp+58h]
0x180004a20  cmp     eax, 0E06D7363h
0x180004a25  jnz     short loc_180004A3B
0x180004a27  mov     rdx, [rbp+0C0h]
0x180004a2e  mov     ecx, [rbp+58h]
0x180004a31  call    _XcptFilter_0
0x180004a36  mov     [rbp+60h], eax
0x180004a39  jmp     short loc_180004A42
0x180004a3b  mov     dword ptr [rbp+60h], 0
0x180004a42  mov     eax, [rbp+60h]
0x180004a45  add     rsp, 20h
0x180004a49  pop     rbp
0x180004a4a  retn
0x180004a4c  push    rbp
0x180004a4e  sub     rsp, 20h
0x180004a52  mov     rbp, rdx
0x180004a55  mov     rax, [rcx]
0x180004a58  mov     edx, [rax]
0x180004a5a  mov     [rbp+0C8h], rcx
0x180004a61  mov     [rbp+68h], edx
0x180004a64  mov     eax, [rbp+68h]
0x180004a67  cmp     eax, 0E06D7363h
0x180004a6c  jnz     short loc_180004A82
0x180004a6e  mov     rdx, [rbp+0C8h]
0x180004a75  mov     ecx, [rbp+68h]
0x180004a78  call    _XcptFilter_0
0x180004a7d  mov     [rbp+70h], eax
0x180004a80  jmp     short loc_180004A89
0x180004a82  mov     dword ptr [rbp+70h], 0
0x180004a89  mov     eax, [rbp+70h]
0x180004a8c  add     rsp, 20h
0x180004a90  pop     rbp
0x180004a91  retn
0x180004a93  push    rbp
0x180004a95  sub     rsp, 20h
0x180004a99  mov     rbp, rdx
0x180004a9c  mov     rax, [rcx]
0x180004a9f  mov     edx, [rax]
0x180004aa1  mov     [rbp+0D0h], rcx
0x180004aa8  mov     [rbp+78h], edx
0x180004aab  mov     eax, [rbp+78h]
0x180004aae  cmp     eax, 0E06D7363h
0x180004ab3  jnz     short loc_180004ACC
0x180004ab5  mov     rdx, [rbp+0D0h]
0x180004abc  mov     ecx, [rbp+78h]
0x180004abf  call    _XcptFilter_0
0x180004ac4  mov     [rbp+80h], eax
0x180004aca  jmp     short loc_180004AD6
0x180004acc  mov     dword ptr [rbp+80h], 0
0x180004ad6  mov     eax, [rbp+80h]
0x180004adc  add     rsp, 20h
0x180004ae0  pop     rbp
0x180004ae1  retn
0x180004ae3  push    rbp
0x180004ae5  sub     rsp, 20h
0x180004ae9  mov     rbp, rdx
0x180004aec  mov     rax, [rcx]
0x180004aef  mov     edx, [rax]
0x180004af1  mov     [rbp+0D8h], rcx
0x180004af8  mov     [rbp+88h], edx
0x180004afe  mov     eax, [rbp+88h]
0x180004b04  cmp     eax, 0E06D7363h
0x180004b09  jnz     short loc_180004B25
0x180004b0b  mov     rdx, [rbp+0D8h]
0x180004b12  mov     ecx, [rbp+88h]
0x180004b18  call    _XcptFilter_0
0x180004b1d  mov     [rbp+90h], eax
0x180004b23  jmp     short loc_180004B2F
0x180004b25  mov     dword ptr [rbp+90h], 0
0x180004b2f  mov     eax, [rbp+90h]
0x180004b35  add     rsp, 20h
0x180004b39  pop     rbp
0x180004b3a  retn
0x180004b3c  push    rbp
0x180004b3e  sub     rsp, 20h
0x180004b42  mov     rbp, rdx
0x180004b45  mov     rax, [rcx]
0x180004b48  mov     edx, [rax]
0x180004b4a  mov     [rbp+0E0h], rcx
0x180004b51  mov     [rbp+98h], edx
0x180004b57  mov     eax, [rbp+98h]
0x180004b5d  cmp     eax, 0E06D7363h
0x180004b62  jnz     short loc_180004B7E
0x180004b64  mov     rdx, [rbp+0E0h]
0x180004b6b  mov     ecx, [rbp+98h]
0x180004b71  call    _XcptFilter_0
0x180004b76  mov     [rbp+0A0h], eax
0x180004b7c  jmp     short loc_180004B88
0x180004b7e  mov     dword ptr [rbp+0A0h], 0
0x180004b88  mov     eax, [rbp+0A0h]
0x180004b8e  add     rsp, 20h
0x180004b92  pop     rbp
0x180004b93  retn
0x180004b95  push    rbp
0x180004b97  sub     rsp, 20h
0x180004b9b  mov     rbp, rdx
0x180004b9e  cmp     dword ptr [rbp+118h], 1
0x180004ba5  ja      short loc_180004BB1
0x180004ba7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
