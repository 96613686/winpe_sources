# __DllMainCRTStartup

- ea: `0x180001944`
- end: `0x180001b50`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001900`

## callees

- `0x1800016d0`
- `0x180001944`
- `0x180001c80`
- `0x1800071c4`
- `0x1800121f0`

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
  if ( (_DWORD)fdwReason || dword_18001C280 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001C284 = 1;
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
            if ( dword_18001C284 )
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
0x180001944  mov     [rsp+lpvReserved], r8
0x180001949  mov     [rsp+arg_8], edx
0x18000194d  mov     [rsp+arg_0], rcx
0x180001952  push    rbx
0x180001953  push    rsi
0x180001954  push    rdi
0x180001955  sub     rsp, 0F0h
0x18000195c  mov     edi, edx
0x18000195e  mov     rsi, rcx
0x180001961  mov     ebx, 1
0x180001966  cmp     edx, ebx
0x180001968  ja      short loc_180001970
0x18000196a  mov     cs:__native_dllmain_reason, edx
0x180001970  test    edx, edx
0x180001972  jnz     short loc_180001987
0x180001974  cmp     cs:dword_18001C280, edx
0x18000197a  jnz     short loc_180001987
0x18000197c  xor     ebx, ebx
0x18000197e  mov     [rsp+108h+var_E8], ebx
0x180001982  jmp     loc_180001B34
0x180001987  lea     eax, [rdx-1]
0x18000198a  cmp     eax, 1
0x18000198d  ja      loc_180001A14
0x180001993  mov     rax, cs:_pRawDllMain
0x18000199a  test    rax, rax
0x18000199d  jz      short loc_1800019D5
0x18000199f  cmp     edx, 1
0x1800019a2  jnz     short loc_1800019AA
0x1800019a4  mov     cs:dword_18001C284, edx
0x1800019aa  mov     r8, [rsp+108h+lpvReserved]
0x1800019b2  call    cs:__guard_dispatch_icall_fptr
0x1800019b8  mov     ebx, eax
0x1800019ba  mov     [rsp+108h+var_E8], eax
0x1800019be  jmp     short loc_1800019D5
0x1800019c0  xor     ebx, ebx
0x1800019c2  mov     [rsp+108h+var_E8], ebx
0x1800019c6  mov     edi, [rsp+108h+arg_8]
0x1800019cd  mov     rsi, [rsp+108h+arg_0]
0x1800019d5  test    ebx, ebx
0x1800019d7  jz      loc_180001B34
0x1800019dd  mov     r8, [rsp+108h+lpvReserved]
0x1800019e5  mov     edx, edi
0x1800019e7  mov     rcx, rsi
0x1800019ea  call    _CRT_INIT
0x1800019ef  mov     ebx, eax
0x1800019f1  mov     [rsp+108h+var_E8], eax
0x1800019f5  jmp     short loc_180001A0C
0x1800019f7  xor     ebx, ebx
0x1800019f9  mov     [rsp+108h+var_E8], ebx
0x1800019fd  mov     edi, [rsp+108h+arg_8]
0x180001a04  mov     rsi, [rsp+108h+arg_0]
0x180001a0c  test    ebx, ebx
0x180001a0e  jz      loc_180001B34
0x180001a14  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001a1c  mov     edx, edi; fdwReason
0x180001a1e  mov     rcx, rsi; hinstDLL
0x180001a21  call    DllMain
0x180001a26  mov     ebx, eax
0x180001a28  mov     [rsp+108h+var_E8], eax
0x180001a2c  jmp     short loc_180001A43
0x180001a2e  xor     ebx, ebx
0x180001a30  mov     [rsp+108h+var_E8], ebx
0x180001a34  mov     edi, [rsp+108h+arg_8]
0x180001a3b  mov     rsi, [rsp+108h+arg_0]
0x180001a43  cmp     edi, 1
0x180001a46  jnz     short loc_180001ABF
0x180001a48  test    ebx, ebx
0x180001a4a  jnz     short loc_180001ABF
0x180001a4c  xor     r8d, r8d; lpvReserved
0x180001a4f  xor     edx, edx; fdwReason
0x180001a51  mov     rcx, rsi; hinstDLL
0x180001a54  call    DllMain
0x180001a59  jmp     short loc_180001A6E
0x180001a5b  mov     edi, [rsp+108h+arg_8]
0x180001a62  mov     rsi, [rsp+108h+arg_0]
0x180001a6a  mov     ebx, [rsp+108h+var_E8]
0x180001a6e  xor     r8d, r8d
0x180001a71  xor     edx, edx
0x180001a73  mov     rcx, rsi
0x180001a76  call    _CRT_INIT
0x180001a7b  jmp     short loc_180001A90
0x180001a7d  mov     edi, [rsp+108h+arg_8]
0x180001a84  mov     rsi, [rsp+108h+arg_0]
0x180001a8c  mov     ebx, [rsp+108h+var_E8]
0x180001a90  mov     rax, cs:_pRawDllMain
0x180001a97  test    rax, rax
0x180001a9a  jz      short loc_180001ABF
0x180001a9c  xor     r8d, r8d
0x180001a9f  xor     edx, edx
0x180001aa1  mov     rcx, rsi
0x180001aa4  call    cs:__guard_dispatch_icall_fptr
0x180001aaa  jmp     short loc_180001ABF
0x180001aac  mov     edi, [rsp+108h+arg_8]
0x180001ab3  mov     rsi, [rsp+108h+arg_0]
0x180001abb  mov     ebx, [rsp+108h+var_E8]
0x180001abf  test    edi, edi
0x180001ac1  jz      short loc_180001AC8
0x180001ac3  cmp     edi, 3
0x180001ac6  jnz     short loc_180001B34
0x180001ac8  mov     r8, [rsp+108h+lpvReserved]
0x180001ad0  mov     edx, edi
0x180001ad2  mov     rcx, rsi
0x180001ad5  call    _CRT_INIT
0x180001ada  mov     ebx, eax
0x180001adc  mov     [rsp+108h+var_E8], eax
0x180001ae0  jmp     short loc_180001AF7
0x180001ae2  xor     ebx, ebx
0x180001ae4  mov     [rsp+108h+var_E8], ebx
0x180001ae8  mov     edi, [rsp+108h+arg_8]
0x180001aef  mov     rsi, [rsp+108h+arg_0]
0x180001af7  mov     rax, cs:_pRawDllMain
0x180001afe  test    rax, rax
0x180001b01  jz      short loc_180001B34
0x180001b03  cmp     cs:dword_18001C284, 0
0x180001b0a  jz      short loc_180001B34
0x180001b0c  mov     r8, [rsp+108h+lpvReserved]
0x180001b14  mov     edx, edi
0x180001b16  mov     rcx, rsi
0x180001b19  call    cs:__guard_dispatch_icall_fptr
0x180001b1f  mov     ebx, eax
0x180001b21  mov     [rsp+108h+var_E8], eax
0x180001b25  jmp     short loc_180001B34
0x180001b27  xor     ebx, ebx
0x180001b29  mov     [rsp+108h+var_E8], ebx
0x180001b2d  mov     edi, [rsp+108h+arg_8]
0x180001b34  cmp     edi, 1
0x180001b37  ja      short loc_180001B43
0x180001b39  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001b43  mov     eax, ebx
0x180001b45  add     rsp, 0F0h
0x180001b4c  pop     rdi
0x180001b4d  pop     rsi
0x180001b4e  pop     rbx
0x180001b4f  retn
0x1800122c0  push    rbp
0x1800122c2  sub     rsp, 20h
0x1800122c6  mov     rbp, rdx
0x1800122c9  mov     rax, [rcx]
0x1800122cc  mov     edx, [rax]
0x1800122ce  mov     [rbp+0A8h], rcx
0x1800122d5  mov     [rbp+28h], edx
0x1800122d8  mov     eax, [rbp+28h]
0x1800122db  cmp     eax, 0E06D7363h
0x1800122e0  jnz     short loc_1800122F6
0x1800122e2  mov     rdx, [rbp+0A8h]
0x1800122e9  mov     ecx, [rbp+28h]
0x1800122ec  call    _XcptFilter_0
0x1800122f1  mov     [rbp+30h], eax
0x1800122f4  jmp     short loc_1800122FD
0x1800122f6  mov     dword ptr [rbp+30h], 0
0x1800122fd  mov     eax, [rbp+30h]
0x180012300  add     rsp, 20h
0x180012304  pop     rbp
0x180012305  retn
0x180012307  push    rbp
0x180012309  sub     rsp, 20h
0x18001230d  mov     rbp, rdx
0x180012310  mov     rax, [rcx]
0x180012313  mov     edx, [rax]
0x180012315  mov     [rbp+0B0h], rcx
0x18001231c  mov     [rbp+38h], edx
0x18001231f  mov     eax, [rbp+38h]
0x180012322  cmp     eax, 0E06D7363h
0x180012327  jnz     short loc_18001233D
0x180012329  mov     rdx, [rbp+0B0h]
0x180012330  mov     ecx, [rbp+38h]
0x180012333  call    _XcptFilter_0
0x180012338  mov     [rbp+40h], eax
0x18001233b  jmp     short loc_180012344
0x18001233d  mov     dword ptr [rbp+40h], 0
0x180012344  mov     eax, [rbp+40h]
0x180012347  add     rsp, 20h
0x18001234b  pop     rbp
0x18001234c  retn
0x18001234e  push    rbp
0x180012350  sub     rsp, 20h
0x180012354  mov     rbp, rdx
0x180012357  mov     rax, [rcx]
0x18001235a  mov     edx, [rax]
0x18001235c  mov     [rbp+0B8h], rcx
0x180012363  mov     [rbp+48h], edx
0x180012366  mov     eax, [rbp+48h]
0x180012369  cmp     eax, 0E06D7363h
0x18001236e  jnz     short loc_180012384
0x180012370  mov     rdx, [rbp+0B8h]
0x180012377  mov     ecx, [rbp+48h]
0x18001237a  call    _XcptFilter_0
0x18001237f  mov     [rbp+50h], eax
0x180012382  jmp     short loc_18001238B
0x180012384  mov     dword ptr [rbp+50h], 0
0x18001238b  mov     eax, [rbp+50h]
0x18001238e  add     rsp, 20h
0x180012392  pop     rbp
0x180012393  retn
0x180012395  push    rbp
0x180012397  sub     rsp, 20h
0x18001239b  mov     rbp, rdx
0x18001239e  mov     rax, [rcx]
0x1800123a1  mov     edx, [rax]
0x1800123a3  mov     [rbp+0C0h], rcx
0x1800123aa  mov     [rbp+58h], edx
0x1800123ad  mov     eax, [rbp+58h]
0x1800123b0  cmp     eax, 0E06D7363h
0x1800123b5  jnz     short loc_1800123CB
0x1800123b7  mov     rdx, [rbp+0C0h]
0x1800123be  mov     ecx, [rbp+58h]
0x1800123c1  call    _XcptFilter_0
0x1800123c6  mov     [rbp+60h], eax
0x1800123c9  jmp     short loc_1800123D2
0x1800123cb  mov     dword ptr [rbp+60h], 0
0x1800123d2  mov     eax, [rbp+60h]
0x1800123d5  add     rsp, 20h
0x1800123d9  pop     rbp
0x1800123da  retn
0x1800123dc  push    rbp
0x1800123de  sub     rsp, 20h
0x1800123e2  mov     rbp, rdx
0x1800123e5  mov     rax, [rcx]
0x1800123e8  mov     edx, [rax]
0x1800123ea  mov     [rbp+0C8h], rcx
0x1800123f1  mov     [rbp+68h], edx
0x1800123f4  mov     eax, [rbp+68h]
0x1800123f7  cmp     eax, 0E06D7363h
0x1800123fc  jnz     short loc_180012412
0x1800123fe  mov     rdx, [rbp+0C8h]
0x180012405  mov     ecx, [rbp+68h]
0x180012408  call    _XcptFilter_0
0x18001240d  mov     [rbp+70h], eax
0x180012410  jmp     short loc_180012419
0x180012412  mov     dword ptr [rbp+70h], 0
0x180012419  mov     eax, [rbp+70h]
0x18001241c  add     rsp, 20h
0x180012420  pop     rbp
0x180012421  retn
0x180012423  push    rbp
0x180012425  sub     rsp, 20h
0x180012429  mov     rbp, rdx
0x18001242c  mov     rax, [rcx]
0x18001242f  mov     edx, [rax]
0x180012431  mov     [rbp+0D0h], rcx
0x180012438  mov     [rbp+78h], edx
0x18001243b  mov     eax, [rbp+78h]
0x18001243e  cmp     eax, 0E06D7363h
0x180012443  jnz     short loc_18001245C
0x180012445  mov     rdx, [rbp+0D0h]
0x18001244c  mov     ecx, [rbp+78h]
0x18001244f  call    _XcptFilter_0
0x180012454  mov     [rbp+80h], eax
0x18001245a  jmp     short loc_180012466
0x18001245c  mov     dword ptr [rbp+80h], 0
0x180012466  mov     eax, [rbp+80h]
0x18001246c  add     rsp, 20h
0x180012470  pop     rbp
0x180012471  retn
0x180012473  push    rbp
0x180012475  sub     rsp, 20h
0x180012479  mov     rbp, rdx
0x18001247c  mov     rax, [rcx]
0x18001247f  mov     edx, [rax]
0x180012481  mov     [rbp+0D8h], rcx
0x180012488  mov     [rbp+88h], edx
0x18001248e  mov     eax, [rbp+88h]
0x180012494  cmp     eax, 0E06D7363h
0x180012499  jnz     short loc_1800124B5
0x18001249b  mov     rdx, [rbp+0D8h]
0x1800124a2  mov     ecx, [rbp+88h]
0x1800124a8  call    _XcptFilter_0
0x1800124ad  mov     [rbp+90h], eax
0x1800124b3  jmp     short loc_1800124BF
0x1800124b5  mov     dword ptr [rbp+90h], 0
0x1800124bf  mov     eax, [rbp+90h]
0x1800124c5  add     rsp, 20h
0x1800124c9  pop     rbp
0x1800124ca  retn
0x1800124cc  push    rbp
0x1800124ce  sub     rsp, 20h
0x1800124d2  mov     rbp, rdx
0x1800124d5  mov     rax, [rcx]
0x1800124d8  mov     edx, [rax]
0x1800124da  mov     [rbp+0E0h], rcx
0x1800124e1  mov     [rbp+98h], edx
0x1800124e7  mov     eax, [rbp+98h]
0x1800124ed  cmp     eax, 0E06D7363h
0x1800124f2  jnz     short loc_18001250E
0x1800124f4  mov     rdx, [rbp+0E0h]
0x1800124fb  mov     ecx, [rbp+98h]
0x180012501  call    _XcptFilter_0
0x180012506  mov     [rbp+0A0h], eax
0x18001250c  jmp     short loc_180012518
0x18001250e  mov     dword ptr [rbp+0A0h], 0
0x180012518  mov     eax, [rbp+0A0h]
0x18001251e  add     rsp, 20h
0x180012522  pop     rbp
0x180012523  retn
0x180012525  push    rbp
0x180012527  sub     rsp, 20h
0x18001252b  mov     rbp, rdx
0x18001252e  cmp     dword ptr [rbp+118h], 1
0x180012535  ja      short loc_180012541
0x180012537  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
