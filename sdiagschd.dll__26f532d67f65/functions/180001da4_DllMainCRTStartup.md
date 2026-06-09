# __DllMainCRTStartup

- ea: `0x180001da4`
- end: `0x180001fb1`
- name: `__DllMainCRTStartup`
- size: `525`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001d60`

## callees

- `0x180001b1c`
- `0x180001da4`
- `0x18000218e`
- `0x180007680`
- `0x18000d010`

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
  if ( (_DWORD)fdwReason || dword_1800142EC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800142F0 = 1;
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
            if ( dword_1800142F0 )
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
0x180001da4  mov     [rsp+lpvReserved], r8
0x180001da9  mov     [rsp+arg_8], edx
0x180001dad  mov     [rsp+arg_0], rcx
0x180001db2  push    rbx
0x180001db3  push    rsi
0x180001db4  push    rdi
0x180001db5  sub     rsp, 150h
0x180001dbc  mov     edi, edx
0x180001dbe  mov     rsi, rcx
0x180001dc1  mov     ebx, 1
0x180001dc6  mov     [rsp+168h+var_148], ebx
0x180001dca  cmp     edx, ebx
0x180001dcc  ja      short loc_180001DD4
0x180001dce  mov     cs:__native_dllmain_reason, edx
0x180001dd4  test    edx, edx
0x180001dd6  jnz     short loc_180001DEB
0x180001dd8  cmp     cs:dword_1800142EC, edx
0x180001dde  jnz     short loc_180001DEB
0x180001de0  xor     ebx, ebx
0x180001de2  mov     [rsp+168h+var_148], ebx
0x180001de6  jmp     loc_180001F95
0x180001deb  lea     eax, [rdx-1]
0x180001dee  cmp     eax, 1
0x180001df1  ja      loc_180001E77
0x180001df7  mov     rax, cs:_pRawDllMain
0x180001dfe  test    rax, rax
0x180001e01  jz      short loc_180001E38
0x180001e03  cmp     edx, 1
0x180001e06  jnz     short loc_180001E0E
0x180001e08  mov     cs:dword_1800142F0, edx
0x180001e0e  mov     r8, [rsp+168h+lpvReserved]
0x180001e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e1b  mov     ebx, eax
0x180001e1d  mov     [rsp+168h+var_148], eax
0x180001e21  jmp     short loc_180001E38
0x180001e23  xor     ebx, ebx
0x180001e25  mov     [rsp+168h+var_148], ebx
0x180001e29  mov     edi, [rsp+168h+arg_8]
0x180001e30  mov     rsi, [rsp+168h+arg_0]
0x180001e38  test    ebx, ebx
0x180001e3a  jz      loc_180001F95
0x180001e40  mov     r8, [rsp+168h+lpvReserved]
0x180001e48  mov     edx, edi
0x180001e4a  mov     rcx, rsi
0x180001e4d  call    _CRT_INIT
0x180001e52  mov     ebx, eax
0x180001e54  mov     [rsp+168h+var_148], eax
0x180001e58  jmp     short loc_180001E6F
0x180001e5a  xor     ebx, ebx
0x180001e5c  mov     [rsp+168h+var_148], ebx
0x180001e60  mov     edi, [rsp+168h+arg_8]
0x180001e67  mov     rsi, [rsp+168h+arg_0]
0x180001e6f  test    ebx, ebx
0x180001e71  jz      loc_180001F95
0x180001e77  mov     r8, [rsp+168h+lpvReserved]; lpvReserved
0x180001e7f  mov     edx, edi; fdwReason
0x180001e81  mov     rcx, rsi; hinstDLL
0x180001e84  call    DllMain
0x180001e89  mov     ebx, eax
0x180001e8b  mov     [rsp+168h+var_148], eax
0x180001e8f  jmp     short loc_180001EA6
0x180001e91  xor     ebx, ebx
0x180001e93  mov     [rsp+168h+var_148], ebx
0x180001e97  mov     edi, [rsp+168h+arg_8]
0x180001e9e  mov     rsi, [rsp+168h+arg_0]
0x180001ea6  cmp     edi, 1
0x180001ea9  jnz     short loc_180001F21
0x180001eab  test    ebx, ebx
0x180001ead  jnz     short loc_180001F21
0x180001eaf  xor     r8d, r8d; lpvReserved
0x180001eb2  xor     edx, edx; fdwReason
0x180001eb4  mov     rcx, rsi; hinstDLL
0x180001eb7  call    DllMain
0x180001ebc  jmp     short loc_180001ED1
0x180001ebe  mov     edi, [rsp+168h+arg_8]
0x180001ec5  mov     rsi, [rsp+168h+arg_0]
0x180001ecd  mov     ebx, [rsp+168h+var_148]
0x180001ed1  xor     r8d, r8d
0x180001ed4  xor     edx, edx
0x180001ed6  mov     rcx, rsi
0x180001ed9  call    _CRT_INIT
0x180001ede  jmp     short loc_180001EF3
0x180001ee0  mov     edi, [rsp+168h+arg_8]
0x180001ee7  mov     rsi, [rsp+168h+arg_0]
0x180001eef  mov     ebx, [rsp+168h+var_148]
0x180001ef3  mov     rax, cs:_pRawDllMain
0x180001efa  test    rax, rax
0x180001efd  jz      short loc_180001F21
0x180001eff  xor     r8d, r8d
0x180001f02  xor     edx, edx
0x180001f04  mov     rcx, rsi
0x180001f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f0c  jmp     short loc_180001F21
0x180001f0e  mov     edi, [rsp+168h+arg_8]
0x180001f15  mov     rsi, [rsp+168h+arg_0]
0x180001f1d  mov     ebx, [rsp+168h+var_148]
0x180001f21  test    edi, edi
0x180001f23  jz      short loc_180001F2A
0x180001f25  cmp     edi, 3
0x180001f28  jnz     short loc_180001F95
0x180001f2a  mov     r8, [rsp+168h+lpvReserved]
0x180001f32  mov     edx, edi
0x180001f34  mov     rcx, rsi
0x180001f37  call    _CRT_INIT
0x180001f3c  mov     ebx, eax
0x180001f3e  mov     [rsp+168h+var_148], eax
0x180001f42  jmp     short loc_180001F59
0x180001f44  xor     ebx, ebx
0x180001f46  mov     [rsp+168h+var_148], ebx
0x180001f4a  mov     edi, [rsp+168h+arg_8]
0x180001f51  mov     rsi, [rsp+168h+arg_0]
0x180001f59  mov     rax, cs:_pRawDllMain
0x180001f60  test    rax, rax
0x180001f63  jz      short loc_180001F95
0x180001f65  cmp     cs:dword_1800142F0, 0
0x180001f6c  jz      short loc_180001F95
0x180001f6e  mov     r8, [rsp+168h+lpvReserved]
0x180001f76  mov     edx, edi
0x180001f78  mov     rcx, rsi
0x180001f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f80  mov     ebx, eax
0x180001f82  mov     [rsp+168h+var_148], eax
0x180001f86  jmp     short loc_180001F95
0x180001f88  xor     ebx, ebx
0x180001f8a  mov     [rsp+168h+var_148], ebx
0x180001f8e  mov     edi, [rsp+168h+arg_8]
0x180001f95  cmp     edi, 1
0x180001f98  ja      short loc_180001FA4
0x180001f9a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001fa4  mov     eax, ebx
0x180001fa6  add     rsp, 150h
0x180001fad  pop     rdi
0x180001fae  pop     rsi
0x180001faf  pop     rbx
0x180001fb0  retn
0x18000c9e2  push    rbp
0x18000c9e4  sub     rsp, 20h
0x18000c9e8  mov     rbp, rdx
0x18000c9eb  mov     [rbp+108h], rcx
0x18000c9f2  mov     rax, [rcx]
0x18000c9f5  mov     edx, [rax]
0x18000c9f7  mov     [rbp+0A4h], edx
0x18000c9fd  mov     [rbp+0C8h], rcx
0x18000ca04  mov     [rbp+28h], edx
0x18000ca07  mov     eax, [rbp+28h]
0x18000ca0a  cmp     eax, 0E06D7363h
0x18000ca0f  jnz     short loc_18000CA25
0x18000ca11  mov     rdx, [rbp+0C8h]
0x18000ca18  mov     ecx, [rbp+28h]
0x18000ca1b  call    _XcptFilter_0
0x18000ca20  mov     [rbp+30h], eax
0x18000ca23  jmp     short loc_18000CA2C
0x18000ca25  mov     dword ptr [rbp+30h], 0
0x18000ca2c  mov     eax, [rbp+30h]
0x18000ca2f  add     rsp, 20h
0x18000ca33  pop     rbp
0x18000ca34  retn
0x18000ca36  push    rbp
0x18000ca38  sub     rsp, 20h
0x18000ca3c  mov     rbp, rdx
0x18000ca3f  mov     [rbp+110h], rcx
0x18000ca46  mov     rax, [rcx]
0x18000ca49  mov     edx, [rax]
0x18000ca4b  mov     [rbp+0A8h], edx
0x18000ca51  mov     [rbp+0D0h], rcx
0x18000ca58  mov     [rbp+38h], edx
0x18000ca5b  mov     eax, [rbp+38h]
0x18000ca5e  cmp     eax, 0E06D7363h
0x18000ca63  jnz     short loc_18000CA79
0x18000ca65  mov     rdx, [rbp+0D0h]
0x18000ca6c  mov     ecx, [rbp+38h]
0x18000ca6f  call    _XcptFilter_0
0x18000ca74  mov     [rbp+40h], eax
0x18000ca77  jmp     short loc_18000CA80
0x18000ca79  mov     dword ptr [rbp+40h], 0
0x18000ca80  mov     eax, [rbp+40h]
0x18000ca83  add     rsp, 20h
0x18000ca87  pop     rbp
0x18000ca88  retn
0x18000ca8a  push    rbp
0x18000ca8c  sub     rsp, 20h
0x18000ca90  mov     rbp, rdx
0x18000ca93  mov     [rbp+118h], rcx
0x18000ca9a  mov     rax, [rcx]
0x18000ca9d  mov     edx, [rax]
0x18000ca9f  mov     [rbp+0ACh], edx
0x18000caa5  mov     [rbp+0D8h], rcx
0x18000caac  mov     [rbp+48h], edx
0x18000caaf  mov     eax, [rbp+48h]
0x18000cab2  cmp     eax, 0E06D7363h
0x18000cab7  jnz     short loc_18000CACD
0x18000cab9  mov     rdx, [rbp+0D8h]
0x18000cac0  mov     ecx, [rbp+48h]
0x18000cac3  call    _XcptFilter_0
0x18000cac8  mov     [rbp+50h], eax
0x18000cacb  jmp     short loc_18000CAD4
0x18000cacd  mov     dword ptr [rbp+50h], 0
0x18000cad4  mov     eax, [rbp+50h]
0x18000cad7  add     rsp, 20h
0x18000cadb  pop     rbp
0x18000cadc  retn
0x18000cade  push    rbp
0x18000cae0  sub     rsp, 20h
0x18000cae4  mov     rbp, rdx
0x18000cae7  mov     [rbp+120h], rcx
0x18000caee  mov     rax, [rcx]
0x18000caf1  mov     edx, [rax]
0x18000caf3  mov     [rbp+0B0h], edx
0x18000caf9  mov     [rbp+0E0h], rcx
0x18000cb00  mov     [rbp+58h], edx
0x18000cb03  mov     eax, [rbp+58h]
0x18000cb06  cmp     eax, 0E06D7363h
0x18000cb0b  jnz     short loc_18000CB21
0x18000cb0d  mov     rdx, [rbp+0E0h]
0x18000cb14  mov     ecx, [rbp+58h]
0x18000cb17  call    _XcptFilter_0
0x18000cb1c  mov     [rbp+60h], eax
0x18000cb1f  jmp     short loc_18000CB28
0x18000cb21  mov     dword ptr [rbp+60h], 0
0x18000cb28  mov     eax, [rbp+60h]
0x18000cb2b  add     rsp, 20h
0x18000cb2f  pop     rbp
0x18000cb30  retn
0x18000cb32  push    rbp
0x18000cb34  sub     rsp, 20h
0x18000cb38  mov     rbp, rdx
0x18000cb3b  mov     [rbp+128h], rcx
0x18000cb42  mov     rax, [rcx]
0x18000cb45  mov     edx, [rax]
0x18000cb47  mov     [rbp+0B4h], edx
0x18000cb4d  mov     [rbp+0E8h], rcx
0x18000cb54  mov     [rbp+68h], edx
0x18000cb57  mov     eax, [rbp+68h]
0x18000cb5a  cmp     eax, 0E06D7363h
0x18000cb5f  jnz     short loc_18000CB75
0x18000cb61  mov     rdx, [rbp+0E8h]
0x18000cb68  mov     ecx, [rbp+68h]
0x18000cb6b  call    _XcptFilter_0
0x18000cb70  mov     [rbp+70h], eax
0x18000cb73  jmp     short loc_18000CB7C
0x18000cb75  mov     dword ptr [rbp+70h], 0
0x18000cb7c  mov     eax, [rbp+70h]
0x18000cb7f  add     rsp, 20h
0x18000cb83  pop     rbp
0x18000cb84  retn
0x18000cb86  push    rbp
0x18000cb88  sub     rsp, 20h
0x18000cb8c  mov     rbp, rdx
0x18000cb8f  mov     [rbp+130h], rcx
0x18000cb96  mov     rax, [rcx]
0x18000cb99  mov     edx, [rax]
0x18000cb9b  mov     [rbp+0B8h], edx
0x18000cba1  mov     [rbp+0F0h], rcx
0x18000cba8  mov     [rbp+78h], edx
0x18000cbab  mov     eax, [rbp+78h]
0x18000cbae  cmp     eax, 0E06D7363h
0x18000cbb3  jnz     short loc_18000CBCC
0x18000cbb5  mov     rdx, [rbp+0F0h]
0x18000cbbc  mov     ecx, [rbp+78h]
0x18000cbbf  call    _XcptFilter_0
0x18000cbc4  mov     [rbp+80h], eax
0x18000cbca  jmp     short loc_18000CBD6
0x18000cbcc  mov     dword ptr [rbp+80h], 0
0x18000cbd6  mov     eax, [rbp+80h]
0x18000cbdc  add     rsp, 20h
0x18000cbe0  pop     rbp
0x18000cbe1  retn
0x18000cbe3  push    rbp
0x18000cbe5  sub     rsp, 20h
0x18000cbe9  mov     rbp, rdx
0x18000cbec  mov     [rbp+138h], rcx
0x18000cbf3  mov     rax, [rcx]
0x18000cbf6  mov     edx, [rax]
0x18000cbf8  mov     [rbp+0BCh], edx
0x18000cbfe  mov     [rbp+0F8h], rcx
0x18000cc05  mov     [rbp+88h], edx
0x18000cc0b  mov     eax, [rbp+88h]
0x18000cc11  cmp     eax, 0E06D7363h
0x18000cc16  jnz     short loc_18000CC32
0x18000cc18  mov     rdx, [rbp+0F8h]
0x18000cc1f  mov     ecx, [rbp+88h]
0x18000cc25  call    _XcptFilter_0
0x18000cc2a  mov     [rbp+90h], eax
0x18000cc30  jmp     short loc_18000CC3C
0x18000cc32  mov     dword ptr [rbp+90h], 0
0x18000cc3c  mov     eax, [rbp+90h]
0x18000cc42  add     rsp, 20h
0x18000cc46  pop     rbp
0x18000cc47  retn
0x18000cc49  push    rbp
0x18000cc4b  sub     rsp, 20h
0x18000cc4f  mov     rbp, rdx
0x18000cc52  mov     [rbp+140h], rcx
0x18000cc59  mov     rax, [rcx]
0x18000cc5c  mov     edx, [rax]
0x18000cc5e  mov     [rbp+0C0h], edx
0x18000cc64  mov     [rbp+100h], rcx
0x18000cc6b  mov     [rbp+98h], edx
0x18000cc71  mov     eax, [rbp+98h]
0x18000cc77  cmp     eax, 0E06D7363h
  ... truncated ...
```
