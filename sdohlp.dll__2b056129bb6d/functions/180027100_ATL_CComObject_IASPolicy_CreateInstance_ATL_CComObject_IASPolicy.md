# ATL::CComObject<IASPolicy>::CreateInstance(ATL::CComObject<IASPolicy> * *)

- ea: `0x180027100`
- end: `0x18002722a`
- name: `?CreateInstance@?$CComObject@VIASPolicy@@@ATL@@SAJPEAPEAV12@@Z`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002844c`

## callees

- `0x180024e34`
- `0x180027100`
- `0x180029110`
- `0x180058010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<IASPolicy>::CreateInstance(char **a1)
{
  char **v1; // r14
  unsigned int v3; // esi
  char *v4; // rax
  char *v5; // rdi
  int v6; // ecx
  int v7; // eax
  char *v9; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (char *)operator new(0x98u);
    v5 = v4;
    if ( v4 )
    {
      *((_DWORD *)v4 + 16) = 0;
      *(_OWORD *)(v4 + 72) = 0;
      *(_OWORD *)(v4 + 88) = 0;
      *((_QWORD *)v4 + 13) = 0;
      v4[112] = 0;
      *((_QWORD *)v4 + 3) = 0;
      *((_QWORD *)v4 + 4) = 0;
      *((_QWORD *)v4 + 5) = 0;
      *((_QWORD *)v4 + 6) = 0;
      *((_QWORD *)v4 + 7) = 0;
      *((_DWORD *)v4 + 30) = 0;
      *((_QWORD *)v4 + 16) = 0;
      *((_QWORD *)v4 + 17) = 0;
      *((_QWORD *)v4 + 18) = 0;
      *(_QWORD *)v4 = &ATL::CComObject<IASPolicy>::`vftable'{for `ATL::IDispatchImpl<IIASPolicy,&_GUID const IID_IIASPolicy,&_GUID const LIBID_SDOHlpLib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v4 + 1) = &ATL::CComObject<IASPolicy>::`vftable'{for `IIASItemInternal'};
      *((_QWORD *)v4 + 2) = &ATL::CComObject<IASPolicy>::`vftable'{for `IASItem'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v9 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v9;
  }
  if ( v5 )
  {
    v6 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v5 + 72));
    if ( v6 >= 0 )
      v5[112] = 1;
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    if ( v3 )
    {
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 208LL))(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180027100  mov     [rsp+arg_0], rcx
0x180027105  push    rsi
0x180027106  push    rdi
0x180027107  push    r14
0x180027109  sub     rsp, 20h
0x18002710d  mov     r14, rcx
0x180027110  test    rcx, rcx
0x180027113  jnz     short loc_18002711F
0x180027115  mov     eax, 80004003h
0x18002711a  jmp     loc_180027221
0x18002711f  mov     qword ptr [rcx], 0
0x180027126  mov     esi, 8007000Eh
0x18002712b  mov     [rsp+38h+arg_8], esi
0x18002712f  mov     [rsp+38h+arg_10], 0
0x180027138  mov     ecx, 98h; Size
0x18002713d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027142  mov     rdi, rax
0x180027145  test    rdi, rdi
0x180027148  jz      short loc_1800271C4
0x18002714a  mov     dword ptr [rax+40h], 0
0x180027151  xorps   xmm0, xmm0
0x180027154  xor     eax, eax
0x180027156  movups  xmmword ptr [rdi+48h], xmm0
0x18002715a  movups  xmmword ptr [rdi+58h], xmm0
0x18002715e  mov     [rdi+68h], rax
0x180027162  mov     [rdi+70h], al
0x180027165  mov     [rdi+18h], rax
0x180027169  mov     [rdi+20h], rax
0x18002716d  mov     [rdi+28h], rax
0x180027171  mov     [rdi+30h], rax
0x180027175  mov     [rdi+38h], rax
0x180027179  mov     [rdi+78h], eax
0x18002717c  mov     [rdi+80h], rax
0x180027183  mov     [rdi+88h], rax
0x18002718a  mov     [rdi+90h], rax
0x180027191  lea     rax, ??_7?$CComObject@VIASPolicy@@@ATL@@6B?$IDispatchImpl@UIIASPolicy@@$1?IID_IIASPolicy@@3U_GUID@@B$1?LIBID_SDOHlpLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<IASPolicy>::`vftable'{for `ATL::IDispatchImpl<IIASPolicy,&_GUID const IID_IIASPolicy,&_GUID const LIBID_SDOHlpLib,1,0,ATL::CComTypeInfoHolder>'}
0x180027198  mov     [rdi], rax
0x18002719b  lea     rax, ??_7?$CComObject@VIASPolicy@@@ATL@@6BIIASItemInternal@@@; const ATL::CComObject<IASPolicy>::`vftable'{for `IIASItemInternal'}
0x1800271a2  mov     [rdi+8], rax
0x1800271a6  lea     rax, ??_7?$CComObject@VIASPolicy@@@ATL@@6BIASItem@@@; const ATL::CComObject<IASPolicy>::`vftable'{for `IASItem'}
0x1800271ad  mov     [rdi+10h], rax
0x1800271b1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800271b8  mov     rax, [rcx]
0x1800271bb  mov     rax, [rax+8]
0x1800271bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271c4  mov     [rsp+38h+arg_10], rdi
0x1800271c9  jmp     short loc_1800271D9
0x1800271cb  mov     r14, [rsp+38h+arg_0]
0x1800271d0  mov     esi, [rsp+38h+arg_8]
0x1800271d4  mov     rdi, [rsp+38h+arg_10]
0x1800271d9  test    rdi, rdi
0x1800271dc  jz      short loc_18002721C
0x1800271de  lea     rcx, [rdi+48h]; this
0x1800271e2  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800271e7  mov     ecx, eax
0x1800271e9  test    eax, eax
0x1800271eb  js      short loc_1800271F1
0x1800271ed  mov     byte ptr [rdi+70h], 1
0x1800271f1  xor     eax, eax
0x1800271f3  test    ecx, ecx
0x1800271f5  cmovs   eax, ecx
0x1800271f8  xor     esi, esi
0x1800271fa  test    eax, eax
0x1800271fc  cmovs   esi, eax
0x1800271ff  test    esi, esi
0x180027201  jz      short loc_18002721C
0x180027203  mov     rax, [rdi]
0x180027206  mov     edx, 1
0x18002720b  mov     rcx, rdi
0x18002720e  mov     rax, [rax+0D0h]
0x180027215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002721a  xor     edi, edi
0x18002721c  mov     [r14], rdi
0x18002721f  mov     eax, esi
0x180027221  add     rsp, 20h
0x180027225  pop     r14
0x180027227  pop     rdi
0x180027228  pop     rsi
0x180027229  retn
```
