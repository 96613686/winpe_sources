# __DllMainCRTStartup

- ea: `0x18000bee4`
- end: `0x18000c0f0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000bea0`

## callees

- `0x180008b00`
- `0x18000bc70`
- `0x18000bee4`
- `0x18000c34e`
- `0x1800156c0`

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
  if ( (_DWORD)fdwReason || dword_180021BE4 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180021BE8 = 1;
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
            if ( dword_180021BE8 )
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
0x18000bee4  mov     [rsp+lpvReserved], r8
0x18000bee9  mov     [rsp+arg_8], edx
0x18000beed  mov     [rsp+arg_0], rcx
0x18000bef2  push    rbx
0x18000bef3  push    rsi
0x18000bef4  push    rdi
0x18000bef5  sub     rsp, 0F0h
0x18000befc  mov     edi, edx
0x18000befe  mov     rsi, rcx
0x18000bf01  mov     ebx, 1
0x18000bf06  cmp     edx, ebx
0x18000bf08  ja      short loc_18000BF10
0x18000bf0a  mov     cs:__native_dllmain_reason, edx
0x18000bf10  test    edx, edx
0x18000bf12  jnz     short loc_18000BF27
0x18000bf14  cmp     cs:dword_180021BE4, edx
0x18000bf1a  jnz     short loc_18000BF27
0x18000bf1c  xor     ebx, ebx
0x18000bf1e  mov     [rsp+108h+var_E8], ebx
0x18000bf22  jmp     loc_18000C0D4
0x18000bf27  lea     eax, [rdx-1]
0x18000bf2a  cmp     eax, 1
0x18000bf2d  ja      loc_18000BFB4
0x18000bf33  mov     rax, cs:_pRawDllMain
0x18000bf3a  test    rax, rax
0x18000bf3d  jz      short loc_18000BF75
0x18000bf3f  cmp     edx, 1
0x18000bf42  jnz     short loc_18000BF4A
0x18000bf44  mov     cs:dword_180021BE8, edx
0x18000bf4a  mov     r8, [rsp+108h+lpvReserved]
0x18000bf52  call    cs:__guard_dispatch_icall_fptr
0x18000bf58  mov     ebx, eax
0x18000bf5a  mov     [rsp+108h+var_E8], eax
0x18000bf5e  jmp     short loc_18000BF75
0x18000bf60  xor     ebx, ebx
0x18000bf62  mov     [rsp+108h+var_E8], ebx
0x18000bf66  mov     edi, [rsp+108h+arg_8]
0x18000bf6d  mov     rsi, [rsp+108h+arg_0]
0x18000bf75  test    ebx, ebx
0x18000bf77  jz      loc_18000C0D4
0x18000bf7d  mov     r8, [rsp+108h+lpvReserved]
0x18000bf85  mov     edx, edi
0x18000bf87  mov     rcx, rsi
0x18000bf8a  call    _CRT_INIT
0x18000bf8f  mov     ebx, eax
0x18000bf91  mov     [rsp+108h+var_E8], eax
0x18000bf95  jmp     short loc_18000BFAC
0x18000bf97  xor     ebx, ebx
0x18000bf99  mov     [rsp+108h+var_E8], ebx
0x18000bf9d  mov     edi, [rsp+108h+arg_8]
0x18000bfa4  mov     rsi, [rsp+108h+arg_0]
0x18000bfac  test    ebx, ebx
0x18000bfae  jz      loc_18000C0D4
0x18000bfb4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000bfbc  mov     edx, edi; fdwReason
0x18000bfbe  mov     rcx, rsi; hinstDLL
0x18000bfc1  call    DllMain
0x18000bfc6  mov     ebx, eax
0x18000bfc8  mov     [rsp+108h+var_E8], eax
0x18000bfcc  jmp     short loc_18000BFE3
0x18000bfce  xor     ebx, ebx
0x18000bfd0  mov     [rsp+108h+var_E8], ebx
0x18000bfd4  mov     edi, [rsp+108h+arg_8]
0x18000bfdb  mov     rsi, [rsp+108h+arg_0]
0x18000bfe3  cmp     edi, 1
0x18000bfe6  jnz     short loc_18000C05F
0x18000bfe8  test    ebx, ebx
0x18000bfea  jnz     short loc_18000C05F
0x18000bfec  xor     r8d, r8d; lpvReserved
0x18000bfef  xor     edx, edx; fdwReason
0x18000bff1  mov     rcx, rsi; hinstDLL
0x18000bff4  call    DllMain
0x18000bff9  jmp     short loc_18000C00E
0x18000bffb  mov     edi, [rsp+108h+arg_8]
0x18000c002  mov     rsi, [rsp+108h+arg_0]
0x18000c00a  mov     ebx, [rsp+108h+var_E8]
0x18000c00e  xor     r8d, r8d
0x18000c011  xor     edx, edx
0x18000c013  mov     rcx, rsi
0x18000c016  call    _CRT_INIT
0x18000c01b  jmp     short loc_18000C030
0x18000c01d  mov     edi, [rsp+108h+arg_8]
0x18000c024  mov     rsi, [rsp+108h+arg_0]
0x18000c02c  mov     ebx, [rsp+108h+var_E8]
0x18000c030  mov     rax, cs:_pRawDllMain
0x18000c037  test    rax, rax
0x18000c03a  jz      short loc_18000C05F
0x18000c03c  xor     r8d, r8d
0x18000c03f  xor     edx, edx
0x18000c041  mov     rcx, rsi
0x18000c044  call    cs:__guard_dispatch_icall_fptr
0x18000c04a  jmp     short loc_18000C05F
0x18000c04c  mov     edi, [rsp+108h+arg_8]
0x18000c053  mov     rsi, [rsp+108h+arg_0]
0x18000c05b  mov     ebx, [rsp+108h+var_E8]
0x18000c05f  test    edi, edi
0x18000c061  jz      short loc_18000C068
0x18000c063  cmp     edi, 3
0x18000c066  jnz     short loc_18000C0D4
0x18000c068  mov     r8, [rsp+108h+lpvReserved]
0x18000c070  mov     edx, edi
0x18000c072  mov     rcx, rsi
0x18000c075  call    _CRT_INIT
0x18000c07a  mov     ebx, eax
0x18000c07c  mov     [rsp+108h+var_E8], eax
0x18000c080  jmp     short loc_18000C097
0x18000c082  xor     ebx, ebx
0x18000c084  mov     [rsp+108h+var_E8], ebx
0x18000c088  mov     edi, [rsp+108h+arg_8]
0x18000c08f  mov     rsi, [rsp+108h+arg_0]
0x18000c097  mov     rax, cs:_pRawDllMain
0x18000c09e  test    rax, rax
0x18000c0a1  jz      short loc_18000C0D4
0x18000c0a3  cmp     cs:dword_180021BE8, 0
0x18000c0aa  jz      short loc_18000C0D4
0x18000c0ac  mov     r8, [rsp+108h+lpvReserved]
0x18000c0b4  mov     edx, edi
0x18000c0b6  mov     rcx, rsi
0x18000c0b9  call    cs:__guard_dispatch_icall_fptr
0x18000c0bf  mov     ebx, eax
0x18000c0c1  mov     [rsp+108h+var_E8], eax
0x18000c0c5  jmp     short loc_18000C0D4
0x18000c0c7  xor     ebx, ebx
0x18000c0c9  mov     [rsp+108h+var_E8], ebx
0x18000c0cd  mov     edi, [rsp+108h+arg_8]
0x18000c0d4  cmp     edi, 1
0x18000c0d7  ja      short loc_18000C0E3
0x18000c0d9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18000c0e3  mov     eax, ebx
0x18000c0e5  add     rsp, 0F0h
0x18000c0ec  pop     rdi
0x18000c0ed  pop     rsi
0x18000c0ee  pop     rbx
0x18000c0ef  retn
0x180016699  push    rbp
0x18001669b  sub     rsp, 20h
0x18001669f  mov     rbp, rdx
0x1800166a2  mov     rax, [rcx]
0x1800166a5  mov     edx, [rax]
0x1800166a7  mov     [rbp+0A8h], rcx
0x1800166ae  mov     [rbp+28h], edx
0x1800166b1  mov     eax, [rbp+28h]
0x1800166b4  cmp     eax, 0E06D7363h
0x1800166b9  jnz     short loc_1800166CF
0x1800166bb  mov     rdx, [rbp+0A8h]
0x1800166c2  mov     ecx, [rbp+28h]
0x1800166c5  call    _XcptFilter_0
0x1800166ca  mov     [rbp+30h], eax
0x1800166cd  jmp     short loc_1800166D6
0x1800166cf  mov     dword ptr [rbp+30h], 0
0x1800166d6  mov     eax, [rbp+30h]
0x1800166d9  add     rsp, 20h
0x1800166dd  pop     rbp
0x1800166de  retn
0x1800166e0  push    rbp
0x1800166e2  sub     rsp, 20h
0x1800166e6  mov     rbp, rdx
0x1800166e9  mov     rax, [rcx]
0x1800166ec  mov     edx, [rax]
0x1800166ee  mov     [rbp+0B0h], rcx
0x1800166f5  mov     [rbp+38h], edx
0x1800166f8  mov     eax, [rbp+38h]
0x1800166fb  cmp     eax, 0E06D7363h
0x180016700  jnz     short loc_180016716
0x180016702  mov     rdx, [rbp+0B0h]
0x180016709  mov     ecx, [rbp+38h]
0x18001670c  call    _XcptFilter_0
0x180016711  mov     [rbp+40h], eax
0x180016714  jmp     short loc_18001671D
0x180016716  mov     dword ptr [rbp+40h], 0
0x18001671d  mov     eax, [rbp+40h]
0x180016720  add     rsp, 20h
0x180016724  pop     rbp
0x180016725  retn
0x180016727  push    rbp
0x180016729  sub     rsp, 20h
0x18001672d  mov     rbp, rdx
0x180016730  mov     rax, [rcx]
0x180016733  mov     edx, [rax]
0x180016735  mov     [rbp+0B8h], rcx
0x18001673c  mov     [rbp+48h], edx
0x18001673f  mov     eax, [rbp+48h]
0x180016742  cmp     eax, 0E06D7363h
0x180016747  jnz     short loc_18001675D
0x180016749  mov     rdx, [rbp+0B8h]
0x180016750  mov     ecx, [rbp+48h]
0x180016753  call    _XcptFilter_0
0x180016758  mov     [rbp+50h], eax
0x18001675b  jmp     short loc_180016764
0x18001675d  mov     dword ptr [rbp+50h], 0
0x180016764  mov     eax, [rbp+50h]
0x180016767  add     rsp, 20h
0x18001676b  pop     rbp
0x18001676c  retn
0x18001676e  push    rbp
0x180016770  sub     rsp, 20h
0x180016774  mov     rbp, rdx
0x180016777  mov     rax, [rcx]
0x18001677a  mov     edx, [rax]
0x18001677c  mov     [rbp+0C0h], rcx
0x180016783  mov     [rbp+58h], edx
0x180016786  mov     eax, [rbp+58h]
0x180016789  cmp     eax, 0E06D7363h
0x18001678e  jnz     short loc_1800167A4
0x180016790  mov     rdx, [rbp+0C0h]
0x180016797  mov     ecx, [rbp+58h]
0x18001679a  call    _XcptFilter_0
0x18001679f  mov     [rbp+60h], eax
0x1800167a2  jmp     short loc_1800167AB
0x1800167a4  mov     dword ptr [rbp+60h], 0
0x1800167ab  mov     eax, [rbp+60h]
0x1800167ae  add     rsp, 20h
0x1800167b2  pop     rbp
0x1800167b3  retn
0x1800167b5  push    rbp
0x1800167b7  sub     rsp, 20h
0x1800167bb  mov     rbp, rdx
0x1800167be  mov     rax, [rcx]
0x1800167c1  mov     edx, [rax]
0x1800167c3  mov     [rbp+0C8h], rcx
0x1800167ca  mov     [rbp+68h], edx
0x1800167cd  mov     eax, [rbp+68h]
0x1800167d0  cmp     eax, 0E06D7363h
0x1800167d5  jnz     short loc_1800167EB
0x1800167d7  mov     rdx, [rbp+0C8h]
0x1800167de  mov     ecx, [rbp+68h]
0x1800167e1  call    _XcptFilter_0
0x1800167e6  mov     [rbp+70h], eax
0x1800167e9  jmp     short loc_1800167F2
0x1800167eb  mov     dword ptr [rbp+70h], 0
0x1800167f2  mov     eax, [rbp+70h]
0x1800167f5  add     rsp, 20h
0x1800167f9  pop     rbp
0x1800167fa  retn
0x1800167fc  push    rbp
0x1800167fe  sub     rsp, 20h
0x180016802  mov     rbp, rdx
0x180016805  mov     rax, [rcx]
0x180016808  mov     edx, [rax]
0x18001680a  mov     [rbp+0D0h], rcx
0x180016811  mov     [rbp+78h], edx
0x180016814  mov     eax, [rbp+78h]
0x180016817  cmp     eax, 0E06D7363h
0x18001681c  jnz     short loc_180016835
0x18001681e  mov     rdx, [rbp+0D0h]
0x180016825  mov     ecx, [rbp+78h]
0x180016828  call    _XcptFilter_0
0x18001682d  mov     [rbp+80h], eax
0x180016833  jmp     short loc_18001683F
0x180016835  mov     dword ptr [rbp+80h], 0
0x18001683f  mov     eax, [rbp+80h]
0x180016845  add     rsp, 20h
0x180016849  pop     rbp
0x18001684a  retn
0x18001684c  push    rbp
0x18001684e  sub     rsp, 20h
0x180016852  mov     rbp, rdx
0x180016855  mov     rax, [rcx]
0x180016858  mov     edx, [rax]
0x18001685a  mov     [rbp+0D8h], rcx
0x180016861  mov     [rbp+88h], edx
0x180016867  mov     eax, [rbp+88h]
0x18001686d  cmp     eax, 0E06D7363h
0x180016872  jnz     short loc_18001688E
0x180016874  mov     rdx, [rbp+0D8h]
0x18001687b  mov     ecx, [rbp+88h]
0x180016881  call    _XcptFilter_0
0x180016886  mov     [rbp+90h], eax
0x18001688c  jmp     short loc_180016898
0x18001688e  mov     dword ptr [rbp+90h], 0
0x180016898  mov     eax, [rbp+90h]
0x18001689e  add     rsp, 20h
0x1800168a2  pop     rbp
0x1800168a3  retn
0x1800168a5  push    rbp
0x1800168a7  sub     rsp, 20h
0x1800168ab  mov     rbp, rdx
0x1800168ae  mov     rax, [rcx]
0x1800168b1  mov     edx, [rax]
0x1800168b3  mov     [rbp+0E0h], rcx
0x1800168ba  mov     [rbp+98h], edx
0x1800168c0  mov     eax, [rbp+98h]
0x1800168c6  cmp     eax, 0E06D7363h
0x1800168cb  jnz     short loc_1800168E7
0x1800168cd  mov     rdx, [rbp+0E0h]
0x1800168d4  mov     ecx, [rbp+98h]
0x1800168da  call    _XcptFilter_0
0x1800168df  mov     [rbp+0A0h], eax
0x1800168e5  jmp     short loc_1800168F1
0x1800168e7  mov     dword ptr [rbp+0A0h], 0
0x1800168f1  mov     eax, [rbp+0A0h]
0x1800168f7  add     rsp, 20h
0x1800168fb  pop     rbp
0x1800168fc  retn
0x1800168fe  push    rbp
0x180016900  sub     rsp, 20h
0x180016904  mov     rbp, rdx
0x180016907  cmp     dword ptr [rbp+118h], 1
0x18001690e  ja      short loc_18001691A
0x180016910  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
