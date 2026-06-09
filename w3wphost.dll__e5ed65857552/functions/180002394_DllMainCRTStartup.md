# __DllMainCRTStartup

- ea: `0x180002394`
- end: `0x1800025a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002350`

## callees

- `0x180002120`
- `0x180002394`
- `0x1800025e0`
- `0x1800027b8`
- `0x18000d330`

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
  if ( (_DWORD)fdwReason || dword_180015100 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180015104 = 1;
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
            if ( dword_180015104 )
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
0x180002394  mov     [rsp+lpvReserved], r8
0x180002399  mov     [rsp+arg_8], edx
0x18000239d  mov     [rsp+arg_0], rcx
0x1800023a2  push    rbx
0x1800023a3  push    rsi
0x1800023a4  push    rdi
0x1800023a5  sub     rsp, 0F0h
0x1800023ac  mov     edi, edx
0x1800023ae  mov     rsi, rcx
0x1800023b1  mov     ebx, 1
0x1800023b6  cmp     edx, ebx
0x1800023b8  ja      short loc_1800023C0
0x1800023ba  mov     cs:__native_dllmain_reason, edx
0x1800023c0  test    edx, edx
0x1800023c2  jnz     short loc_1800023D7
0x1800023c4  cmp     cs:dword_180015100, edx
0x1800023ca  jnz     short loc_1800023D7
0x1800023cc  xor     ebx, ebx
0x1800023ce  mov     [rsp+108h+var_E8], ebx
0x1800023d2  jmp     loc_180002584
0x1800023d7  lea     eax, [rdx-1]
0x1800023da  cmp     eax, 1
0x1800023dd  ja      loc_180002464
0x1800023e3  mov     rax, cs:_pRawDllMain
0x1800023ea  test    rax, rax
0x1800023ed  jz      short loc_180002425
0x1800023ef  cmp     edx, 1
0x1800023f2  jnz     short loc_1800023FA
0x1800023f4  mov     cs:dword_180015104, edx
0x1800023fa  mov     r8, [rsp+108h+lpvReserved]
0x180002402  call    cs:__guard_dispatch_icall_fptr
0x180002408  mov     ebx, eax
0x18000240a  mov     [rsp+108h+var_E8], eax
0x18000240e  jmp     short loc_180002425
0x180002410  xor     ebx, ebx
0x180002412  mov     [rsp+108h+var_E8], ebx
0x180002416  mov     edi, [rsp+108h+arg_8]
0x18000241d  mov     rsi, [rsp+108h+arg_0]
0x180002425  test    ebx, ebx
0x180002427  jz      loc_180002584
0x18000242d  mov     r8, [rsp+108h+lpvReserved]
0x180002435  mov     edx, edi
0x180002437  mov     rcx, rsi
0x18000243a  call    _CRT_INIT
0x18000243f  mov     ebx, eax
0x180002441  mov     [rsp+108h+var_E8], eax
0x180002445  jmp     short loc_18000245C
0x180002447  xor     ebx, ebx
0x180002449  mov     [rsp+108h+var_E8], ebx
0x18000244d  mov     edi, [rsp+108h+arg_8]
0x180002454  mov     rsi, [rsp+108h+arg_0]
0x18000245c  test    ebx, ebx
0x18000245e  jz      loc_180002584
0x180002464  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000246c  mov     edx, edi; fdwReason
0x18000246e  mov     rcx, rsi; hinstDLL
0x180002471  call    DllMain
0x180002476  mov     ebx, eax
0x180002478  mov     [rsp+108h+var_E8], eax
0x18000247c  jmp     short loc_180002493
0x18000247e  xor     ebx, ebx
0x180002480  mov     [rsp+108h+var_E8], ebx
0x180002484  mov     edi, [rsp+108h+arg_8]
0x18000248b  mov     rsi, [rsp+108h+arg_0]
0x180002493  cmp     edi, 1
0x180002496  jnz     short loc_18000250F
0x180002498  test    ebx, ebx
0x18000249a  jnz     short loc_18000250F
0x18000249c  xor     r8d, r8d; lpvReserved
0x18000249f  xor     edx, edx; fdwReason
0x1800024a1  mov     rcx, rsi; hinstDLL
0x1800024a4  call    DllMain
0x1800024a9  jmp     short loc_1800024BE
0x1800024ab  mov     edi, [rsp+108h+arg_8]
0x1800024b2  mov     rsi, [rsp+108h+arg_0]
0x1800024ba  mov     ebx, [rsp+108h+var_E8]
0x1800024be  xor     r8d, r8d
0x1800024c1  xor     edx, edx
0x1800024c3  mov     rcx, rsi
0x1800024c6  call    _CRT_INIT
0x1800024cb  jmp     short loc_1800024E0
0x1800024cd  mov     edi, [rsp+108h+arg_8]
0x1800024d4  mov     rsi, [rsp+108h+arg_0]
0x1800024dc  mov     ebx, [rsp+108h+var_E8]
0x1800024e0  mov     rax, cs:_pRawDllMain
0x1800024e7  test    rax, rax
0x1800024ea  jz      short loc_18000250F
0x1800024ec  xor     r8d, r8d
0x1800024ef  xor     edx, edx
0x1800024f1  mov     rcx, rsi
0x1800024f4  call    cs:__guard_dispatch_icall_fptr
0x1800024fa  jmp     short loc_18000250F
0x1800024fc  mov     edi, [rsp+108h+arg_8]
0x180002503  mov     rsi, [rsp+108h+arg_0]
0x18000250b  mov     ebx, [rsp+108h+var_E8]
0x18000250f  test    edi, edi
0x180002511  jz      short loc_180002518
0x180002513  cmp     edi, 3
0x180002516  jnz     short loc_180002584
0x180002518  mov     r8, [rsp+108h+lpvReserved]
0x180002520  mov     edx, edi
0x180002522  mov     rcx, rsi
0x180002525  call    _CRT_INIT
0x18000252a  mov     ebx, eax
0x18000252c  mov     [rsp+108h+var_E8], eax
0x180002530  jmp     short loc_180002547
0x180002532  xor     ebx, ebx
0x180002534  mov     [rsp+108h+var_E8], ebx
0x180002538  mov     edi, [rsp+108h+arg_8]
0x18000253f  mov     rsi, [rsp+108h+arg_0]
0x180002547  mov     rax, cs:_pRawDllMain
0x18000254e  test    rax, rax
0x180002551  jz      short loc_180002584
0x180002553  cmp     cs:dword_180015104, 0
0x18000255a  jz      short loc_180002584
0x18000255c  mov     r8, [rsp+108h+lpvReserved]
0x180002564  mov     edx, edi
0x180002566  mov     rcx, rsi
0x180002569  call    cs:__guard_dispatch_icall_fptr
0x18000256f  mov     ebx, eax
0x180002571  mov     [rsp+108h+var_E8], eax
0x180002575  jmp     short loc_180002584
0x180002577  xor     ebx, ebx
0x180002579  mov     [rsp+108h+var_E8], ebx
0x18000257d  mov     edi, [rsp+108h+arg_8]
0x180002584  cmp     edi, 1
0x180002587  ja      short loc_180002593
0x180002589  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002593  mov     eax, ebx
0x180002595  add     rsp, 0F0h
0x18000259c  pop     rdi
0x18000259d  pop     rsi
0x18000259e  pop     rbx
0x18000259f  retn
0x18000d3a0  push    rbp
0x18000d3a2  sub     rsp, 20h
0x18000d3a6  mov     rbp, rdx
0x18000d3a9  mov     rax, [rcx]
0x18000d3ac  mov     edx, [rax]
0x18000d3ae  mov     [rbp+0A8h], rcx
0x18000d3b5  mov     [rbp+28h], edx
0x18000d3b8  mov     eax, [rbp+28h]
0x18000d3bb  cmp     eax, 0E06D7363h
0x18000d3c0  jnz     short loc_18000D3D6
0x18000d3c2  mov     rdx, [rbp+0A8h]
0x18000d3c9  mov     ecx, [rbp+28h]
0x18000d3cc  call    _XcptFilter_0
0x18000d3d1  mov     [rbp+30h], eax
0x18000d3d4  jmp     short loc_18000D3DD
0x18000d3d6  mov     dword ptr [rbp+30h], 0
0x18000d3dd  mov     eax, [rbp+30h]
0x18000d3e0  add     rsp, 20h
0x18000d3e4  pop     rbp
0x18000d3e5  retn
0x18000d3e7  push    rbp
0x18000d3e9  sub     rsp, 20h
0x18000d3ed  mov     rbp, rdx
0x18000d3f0  mov     rax, [rcx]
0x18000d3f3  mov     edx, [rax]
0x18000d3f5  mov     [rbp+0B0h], rcx
0x18000d3fc  mov     [rbp+38h], edx
0x18000d3ff  mov     eax, [rbp+38h]
0x18000d402  cmp     eax, 0E06D7363h
0x18000d407  jnz     short loc_18000D41D
0x18000d409  mov     rdx, [rbp+0B0h]
0x18000d410  mov     ecx, [rbp+38h]
0x18000d413  call    _XcptFilter_0
0x18000d418  mov     [rbp+40h], eax
0x18000d41b  jmp     short loc_18000D424
0x18000d41d  mov     dword ptr [rbp+40h], 0
0x18000d424  mov     eax, [rbp+40h]
0x18000d427  add     rsp, 20h
0x18000d42b  pop     rbp
0x18000d42c  retn
0x18000d42e  push    rbp
0x18000d430  sub     rsp, 20h
0x18000d434  mov     rbp, rdx
0x18000d437  mov     rax, [rcx]
0x18000d43a  mov     edx, [rax]
0x18000d43c  mov     [rbp+0B8h], rcx
0x18000d443  mov     [rbp+48h], edx
0x18000d446  mov     eax, [rbp+48h]
0x18000d449  cmp     eax, 0E06D7363h
0x18000d44e  jnz     short loc_18000D464
0x18000d450  mov     rdx, [rbp+0B8h]
0x18000d457  mov     ecx, [rbp+48h]
0x18000d45a  call    _XcptFilter_0
0x18000d45f  mov     [rbp+50h], eax
0x18000d462  jmp     short loc_18000D46B
0x18000d464  mov     dword ptr [rbp+50h], 0
0x18000d46b  mov     eax, [rbp+50h]
0x18000d46e  add     rsp, 20h
0x18000d472  pop     rbp
0x18000d473  retn
0x18000d475  push    rbp
0x18000d477  sub     rsp, 20h
0x18000d47b  mov     rbp, rdx
0x18000d47e  mov     rax, [rcx]
0x18000d481  mov     edx, [rax]
0x18000d483  mov     [rbp+0C0h], rcx
0x18000d48a  mov     [rbp+58h], edx
0x18000d48d  mov     eax, [rbp+58h]
0x18000d490  cmp     eax, 0E06D7363h
0x18000d495  jnz     short loc_18000D4AB
0x18000d497  mov     rdx, [rbp+0C0h]
0x18000d49e  mov     ecx, [rbp+58h]
0x18000d4a1  call    _XcptFilter_0
0x18000d4a6  mov     [rbp+60h], eax
0x18000d4a9  jmp     short loc_18000D4B2
0x18000d4ab  mov     dword ptr [rbp+60h], 0
0x18000d4b2  mov     eax, [rbp+60h]
0x18000d4b5  add     rsp, 20h
0x18000d4b9  pop     rbp
0x18000d4ba  retn
0x18000d4bc  push    rbp
0x18000d4be  sub     rsp, 20h
0x18000d4c2  mov     rbp, rdx
0x18000d4c5  mov     rax, [rcx]
0x18000d4c8  mov     edx, [rax]
0x18000d4ca  mov     [rbp+0C8h], rcx
0x18000d4d1  mov     [rbp+68h], edx
0x18000d4d4  mov     eax, [rbp+68h]
0x18000d4d7  cmp     eax, 0E06D7363h
0x18000d4dc  jnz     short loc_18000D4F2
0x18000d4de  mov     rdx, [rbp+0C8h]
0x18000d4e5  mov     ecx, [rbp+68h]
0x18000d4e8  call    _XcptFilter_0
0x18000d4ed  mov     [rbp+70h], eax
0x18000d4f0  jmp     short loc_18000D4F9
0x18000d4f2  mov     dword ptr [rbp+70h], 0
0x18000d4f9  mov     eax, [rbp+70h]
0x18000d4fc  add     rsp, 20h
0x18000d500  pop     rbp
0x18000d501  retn
0x18000d503  push    rbp
0x18000d505  sub     rsp, 20h
0x18000d509  mov     rbp, rdx
0x18000d50c  mov     rax, [rcx]
0x18000d50f  mov     edx, [rax]
0x18000d511  mov     [rbp+0D0h], rcx
0x18000d518  mov     [rbp+78h], edx
0x18000d51b  mov     eax, [rbp+78h]
0x18000d51e  cmp     eax, 0E06D7363h
0x18000d523  jnz     short loc_18000D53C
0x18000d525  mov     rdx, [rbp+0D0h]
0x18000d52c  mov     ecx, [rbp+78h]
0x18000d52f  call    _XcptFilter_0
0x18000d534  mov     [rbp+80h], eax
0x18000d53a  jmp     short loc_18000D546
0x18000d53c  mov     dword ptr [rbp+80h], 0
0x18000d546  mov     eax, [rbp+80h]
0x18000d54c  add     rsp, 20h
0x18000d550  pop     rbp
0x18000d551  retn
0x18000d553  push    rbp
0x18000d555  sub     rsp, 20h
0x18000d559  mov     rbp, rdx
0x18000d55c  mov     rax, [rcx]
0x18000d55f  mov     edx, [rax]
0x18000d561  mov     [rbp+0D8h], rcx
0x18000d568  mov     [rbp+88h], edx
0x18000d56e  mov     eax, [rbp+88h]
0x18000d574  cmp     eax, 0E06D7363h
0x18000d579  jnz     short loc_18000D595
0x18000d57b  mov     rdx, [rbp+0D8h]
0x18000d582  mov     ecx, [rbp+88h]
0x18000d588  call    _XcptFilter_0
0x18000d58d  mov     [rbp+90h], eax
0x18000d593  jmp     short loc_18000D59F
0x18000d595  mov     dword ptr [rbp+90h], 0
0x18000d59f  mov     eax, [rbp+90h]
0x18000d5a5  add     rsp, 20h
0x18000d5a9  pop     rbp
0x18000d5aa  retn
0x18000d5ac  push    rbp
0x18000d5ae  sub     rsp, 20h
0x18000d5b2  mov     rbp, rdx
0x18000d5b5  mov     rax, [rcx]
0x18000d5b8  mov     edx, [rax]
0x18000d5ba  mov     [rbp+0E0h], rcx
0x18000d5c1  mov     [rbp+98h], edx
0x18000d5c7  mov     eax, [rbp+98h]
0x18000d5cd  cmp     eax, 0E06D7363h
0x18000d5d2  jnz     short loc_18000D5EE
0x18000d5d4  mov     rdx, [rbp+0E0h]
0x18000d5db  mov     ecx, [rbp+98h]
0x18000d5e1  call    _XcptFilter_0
0x18000d5e6  mov     [rbp+0A0h], eax
0x18000d5ec  jmp     short loc_18000D5F8
0x18000d5ee  mov     dword ptr [rbp+0A0h], 0
0x18000d5f8  mov     eax, [rbp+0A0h]
0x18000d5fe  add     rsp, 20h
0x18000d602  pop     rbp
0x18000d603  retn
0x18000d605  push    rbp
0x18000d607  sub     rsp, 20h
0x18000d60b  mov     rbp, rdx
0x18000d60e  cmp     dword ptr [rbp+118h], 1
0x18000d615  ja      short loc_18000D621
0x18000d617  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
