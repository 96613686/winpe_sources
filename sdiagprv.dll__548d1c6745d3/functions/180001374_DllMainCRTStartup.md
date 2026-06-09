# __DllMainCRTStartup

- ea: `0x180001374`
- end: `0x180001580`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001330`

## callees

- `0x180001100`
- `0x180001374`
- `0x180001610`
- `0x180002024`
- `0x180018130`

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
  if ( (_DWORD)fdwReason || dword_180023B00 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180023B04 = 1;
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
            if ( dword_180023B04 )
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
0x180001374  mov     [rsp+lpvReserved], r8
0x180001379  mov     [rsp+arg_8], edx
0x18000137d  mov     [rsp+arg_0], rcx
0x180001382  push    rbx
0x180001383  push    rsi
0x180001384  push    rdi
0x180001385  sub     rsp, 0F0h
0x18000138c  mov     edi, edx
0x18000138e  mov     rsi, rcx
0x180001391  mov     ebx, 1
0x180001396  cmp     edx, ebx
0x180001398  ja      short loc_1800013A0
0x18000139a  mov     cs:__native_dllmain_reason, edx
0x1800013a0  test    edx, edx
0x1800013a2  jnz     short loc_1800013B7
0x1800013a4  cmp     cs:dword_180023B00, edx
0x1800013aa  jnz     short loc_1800013B7
0x1800013ac  xor     ebx, ebx
0x1800013ae  mov     [rsp+108h+var_E8], ebx
0x1800013b2  jmp     loc_180001564
0x1800013b7  lea     eax, [rdx-1]
0x1800013ba  cmp     eax, 1
0x1800013bd  ja      loc_180001444
0x1800013c3  mov     rax, cs:_pRawDllMain
0x1800013ca  test    rax, rax
0x1800013cd  jz      short loc_180001405
0x1800013cf  cmp     edx, 1
0x1800013d2  jnz     short loc_1800013DA
0x1800013d4  mov     cs:dword_180023B04, edx
0x1800013da  mov     r8, [rsp+108h+lpvReserved]
0x1800013e2  call    cs:__guard_dispatch_icall_fptr
0x1800013e8  mov     ebx, eax
0x1800013ea  mov     [rsp+108h+var_E8], eax
0x1800013ee  jmp     short loc_180001405
0x1800013f0  xor     ebx, ebx
0x1800013f2  mov     [rsp+108h+var_E8], ebx
0x1800013f6  mov     edi, [rsp+108h+arg_8]
0x1800013fd  mov     rsi, [rsp+108h+arg_0]
0x180001405  test    ebx, ebx
0x180001407  jz      loc_180001564
0x18000140d  mov     r8, [rsp+108h+lpvReserved]
0x180001415  mov     edx, edi
0x180001417  mov     rcx, rsi
0x18000141a  call    _CRT_INIT
0x18000141f  mov     ebx, eax
0x180001421  mov     [rsp+108h+var_E8], eax
0x180001425  jmp     short loc_18000143C
0x180001427  xor     ebx, ebx
0x180001429  mov     [rsp+108h+var_E8], ebx
0x18000142d  mov     edi, [rsp+108h+arg_8]
0x180001434  mov     rsi, [rsp+108h+arg_0]
0x18000143c  test    ebx, ebx
0x18000143e  jz      loc_180001564
0x180001444  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000144c  mov     edx, edi; fdwReason
0x18000144e  mov     rcx, rsi; hinstDLL
0x180001451  call    DllMain
0x180001456  mov     ebx, eax
0x180001458  mov     [rsp+108h+var_E8], eax
0x18000145c  jmp     short loc_180001473
0x18000145e  xor     ebx, ebx
0x180001460  mov     [rsp+108h+var_E8], ebx
0x180001464  mov     edi, [rsp+108h+arg_8]
0x18000146b  mov     rsi, [rsp+108h+arg_0]
0x180001473  cmp     edi, 1
0x180001476  jnz     short loc_1800014EF
0x180001478  test    ebx, ebx
0x18000147a  jnz     short loc_1800014EF
0x18000147c  xor     r8d, r8d; lpvReserved
0x18000147f  xor     edx, edx; fdwReason
0x180001481  mov     rcx, rsi; hinstDLL
0x180001484  call    DllMain
0x180001489  jmp     short loc_18000149E
0x18000148b  mov     edi, [rsp+108h+arg_8]
0x180001492  mov     rsi, [rsp+108h+arg_0]
0x18000149a  mov     ebx, [rsp+108h+var_E8]
0x18000149e  xor     r8d, r8d
0x1800014a1  xor     edx, edx
0x1800014a3  mov     rcx, rsi
0x1800014a6  call    _CRT_INIT
0x1800014ab  jmp     short loc_1800014C0
0x1800014ad  mov     edi, [rsp+108h+arg_8]
0x1800014b4  mov     rsi, [rsp+108h+arg_0]
0x1800014bc  mov     ebx, [rsp+108h+var_E8]
0x1800014c0  mov     rax, cs:_pRawDllMain
0x1800014c7  test    rax, rax
0x1800014ca  jz      short loc_1800014EF
0x1800014cc  xor     r8d, r8d
0x1800014cf  xor     edx, edx
0x1800014d1  mov     rcx, rsi
0x1800014d4  call    cs:__guard_dispatch_icall_fptr
0x1800014da  jmp     short loc_1800014EF
0x1800014dc  mov     edi, [rsp+108h+arg_8]
0x1800014e3  mov     rsi, [rsp+108h+arg_0]
0x1800014eb  mov     ebx, [rsp+108h+var_E8]
0x1800014ef  test    edi, edi
0x1800014f1  jz      short loc_1800014F8
0x1800014f3  cmp     edi, 3
0x1800014f6  jnz     short loc_180001564
0x1800014f8  mov     r8, [rsp+108h+lpvReserved]
0x180001500  mov     edx, edi
0x180001502  mov     rcx, rsi
0x180001505  call    _CRT_INIT
0x18000150a  mov     ebx, eax
0x18000150c  mov     [rsp+108h+var_E8], eax
0x180001510  jmp     short loc_180001527
0x180001512  xor     ebx, ebx
0x180001514  mov     [rsp+108h+var_E8], ebx
0x180001518  mov     edi, [rsp+108h+arg_8]
0x18000151f  mov     rsi, [rsp+108h+arg_0]
0x180001527  mov     rax, cs:_pRawDllMain
0x18000152e  test    rax, rax
0x180001531  jz      short loc_180001564
0x180001533  cmp     cs:dword_180023B04, 0
0x18000153a  jz      short loc_180001564
0x18000153c  mov     r8, [rsp+108h+lpvReserved]
0x180001544  mov     edx, edi
0x180001546  mov     rcx, rsi
0x180001549  call    cs:__guard_dispatch_icall_fptr
0x18000154f  mov     ebx, eax
0x180001551  mov     [rsp+108h+var_E8], eax
0x180001555  jmp     short loc_180001564
0x180001557  xor     ebx, ebx
0x180001559  mov     [rsp+108h+var_E8], ebx
0x18000155d  mov     edi, [rsp+108h+arg_8]
0x180001564  cmp     edi, 1
0x180001567  ja      short loc_180001573
0x180001569  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001573  mov     eax, ebx
0x180001575  add     rsp, 0F0h
0x18000157c  pop     rdi
0x18000157d  pop     rsi
0x18000157e  pop     rbx
0x18000157f  retn
0x1800181a0  push    rbp
0x1800181a2  sub     rsp, 20h
0x1800181a6  mov     rbp, rdx
0x1800181a9  mov     rax, [rcx]
0x1800181ac  mov     edx, [rax]
0x1800181ae  mov     [rbp+0A8h], rcx
0x1800181b5  mov     [rbp+28h], edx
0x1800181b8  mov     eax, [rbp+28h]
0x1800181bb  cmp     eax, 0E06D7363h
0x1800181c0  jnz     short loc_1800181D6
0x1800181c2  mov     rdx, [rbp+0A8h]
0x1800181c9  mov     ecx, [rbp+28h]
0x1800181cc  call    _XcptFilter_0
0x1800181d1  mov     [rbp+30h], eax
0x1800181d4  jmp     short loc_1800181DD
0x1800181d6  mov     dword ptr [rbp+30h], 0
0x1800181dd  mov     eax, [rbp+30h]
0x1800181e0  add     rsp, 20h
0x1800181e4  pop     rbp
0x1800181e5  retn
0x1800181e7  push    rbp
0x1800181e9  sub     rsp, 20h
0x1800181ed  mov     rbp, rdx
0x1800181f0  mov     rax, [rcx]
0x1800181f3  mov     edx, [rax]
0x1800181f5  mov     [rbp+0B0h], rcx
0x1800181fc  mov     [rbp+38h], edx
0x1800181ff  mov     eax, [rbp+38h]
0x180018202  cmp     eax, 0E06D7363h
0x180018207  jnz     short loc_18001821D
0x180018209  mov     rdx, [rbp+0B0h]
0x180018210  mov     ecx, [rbp+38h]
0x180018213  call    _XcptFilter_0
0x180018218  mov     [rbp+40h], eax
0x18001821b  jmp     short loc_180018224
0x18001821d  mov     dword ptr [rbp+40h], 0
0x180018224  mov     eax, [rbp+40h]
0x180018227  add     rsp, 20h
0x18001822b  pop     rbp
0x18001822c  retn
0x18001822e  push    rbp
0x180018230  sub     rsp, 20h
0x180018234  mov     rbp, rdx
0x180018237  mov     rax, [rcx]
0x18001823a  mov     edx, [rax]
0x18001823c  mov     [rbp+0B8h], rcx
0x180018243  mov     [rbp+48h], edx
0x180018246  mov     eax, [rbp+48h]
0x180018249  cmp     eax, 0E06D7363h
0x18001824e  jnz     short loc_180018264
0x180018250  mov     rdx, [rbp+0B8h]
0x180018257  mov     ecx, [rbp+48h]
0x18001825a  call    _XcptFilter_0
0x18001825f  mov     [rbp+50h], eax
0x180018262  jmp     short loc_18001826B
0x180018264  mov     dword ptr [rbp+50h], 0
0x18001826b  mov     eax, [rbp+50h]
0x18001826e  add     rsp, 20h
0x180018272  pop     rbp
0x180018273  retn
0x180018275  push    rbp
0x180018277  sub     rsp, 20h
0x18001827b  mov     rbp, rdx
0x18001827e  mov     rax, [rcx]
0x180018281  mov     edx, [rax]
0x180018283  mov     [rbp+0C0h], rcx
0x18001828a  mov     [rbp+58h], edx
0x18001828d  mov     eax, [rbp+58h]
0x180018290  cmp     eax, 0E06D7363h
0x180018295  jnz     short loc_1800182AB
0x180018297  mov     rdx, [rbp+0C0h]
0x18001829e  mov     ecx, [rbp+58h]
0x1800182a1  call    _XcptFilter_0
0x1800182a6  mov     [rbp+60h], eax
0x1800182a9  jmp     short loc_1800182B2
0x1800182ab  mov     dword ptr [rbp+60h], 0
0x1800182b2  mov     eax, [rbp+60h]
0x1800182b5  add     rsp, 20h
0x1800182b9  pop     rbp
0x1800182ba  retn
0x1800182bc  push    rbp
0x1800182be  sub     rsp, 20h
0x1800182c2  mov     rbp, rdx
0x1800182c5  mov     rax, [rcx]
0x1800182c8  mov     edx, [rax]
0x1800182ca  mov     [rbp+0C8h], rcx
0x1800182d1  mov     [rbp+68h], edx
0x1800182d4  mov     eax, [rbp+68h]
0x1800182d7  cmp     eax, 0E06D7363h
0x1800182dc  jnz     short loc_1800182F2
0x1800182de  mov     rdx, [rbp+0C8h]
0x1800182e5  mov     ecx, [rbp+68h]
0x1800182e8  call    _XcptFilter_0
0x1800182ed  mov     [rbp+70h], eax
0x1800182f0  jmp     short loc_1800182F9
0x1800182f2  mov     dword ptr [rbp+70h], 0
0x1800182f9  mov     eax, [rbp+70h]
0x1800182fc  add     rsp, 20h
0x180018300  pop     rbp
0x180018301  retn
0x180018303  push    rbp
0x180018305  sub     rsp, 20h
0x180018309  mov     rbp, rdx
0x18001830c  mov     rax, [rcx]
0x18001830f  mov     edx, [rax]
0x180018311  mov     [rbp+0D0h], rcx
0x180018318  mov     [rbp+78h], edx
0x18001831b  mov     eax, [rbp+78h]
0x18001831e  cmp     eax, 0E06D7363h
0x180018323  jnz     short loc_18001833C
0x180018325  mov     rdx, [rbp+0D0h]
0x18001832c  mov     ecx, [rbp+78h]
0x18001832f  call    _XcptFilter_0
0x180018334  mov     [rbp+80h], eax
0x18001833a  jmp     short loc_180018346
0x18001833c  mov     dword ptr [rbp+80h], 0
0x180018346  mov     eax, [rbp+80h]
0x18001834c  add     rsp, 20h
0x180018350  pop     rbp
0x180018351  retn
0x180018353  push    rbp
0x180018355  sub     rsp, 20h
0x180018359  mov     rbp, rdx
0x18001835c  mov     rax, [rcx]
0x18001835f  mov     edx, [rax]
0x180018361  mov     [rbp+0D8h], rcx
0x180018368  mov     [rbp+88h], edx
0x18001836e  mov     eax, [rbp+88h]
0x180018374  cmp     eax, 0E06D7363h
0x180018379  jnz     short loc_180018395
0x18001837b  mov     rdx, [rbp+0D8h]
0x180018382  mov     ecx, [rbp+88h]
0x180018388  call    _XcptFilter_0
0x18001838d  mov     [rbp+90h], eax
0x180018393  jmp     short loc_18001839F
0x180018395  mov     dword ptr [rbp+90h], 0
0x18001839f  mov     eax, [rbp+90h]
0x1800183a5  add     rsp, 20h
0x1800183a9  pop     rbp
0x1800183aa  retn
0x1800183ac  push    rbp
0x1800183ae  sub     rsp, 20h
0x1800183b2  mov     rbp, rdx
0x1800183b5  mov     rax, [rcx]
0x1800183b8  mov     edx, [rax]
0x1800183ba  mov     [rbp+0E0h], rcx
0x1800183c1  mov     [rbp+98h], edx
0x1800183c7  mov     eax, [rbp+98h]
0x1800183cd  cmp     eax, 0E06D7363h
0x1800183d2  jnz     short loc_1800183EE
0x1800183d4  mov     rdx, [rbp+0E0h]
0x1800183db  mov     ecx, [rbp+98h]
0x1800183e1  call    _XcptFilter_0
0x1800183e6  mov     [rbp+0A0h], eax
0x1800183ec  jmp     short loc_1800183F8
0x1800183ee  mov     dword ptr [rbp+0A0h], 0
0x1800183f8  mov     eax, [rbp+0A0h]
0x1800183fe  add     rsp, 20h
0x180018402  pop     rbp
0x180018403  retn
0x180018405  push    rbp
0x180018407  sub     rsp, 20h
0x18001840b  mov     rbp, rdx
0x18001840e  cmp     dword ptr [rbp+118h], 1
0x180018415  ja      short loc_180018421
0x180018417  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
