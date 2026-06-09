# ATL::CComCreator<ATL::CComAggObject<CFsrmPropertiesPropSheet>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001394c`
- end: `0x180013a52`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCFsrmPropertiesPropSheet@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013820`

## callees

- `0x180001264`
- `0x180008288`
- `0x18001394c`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CFsrmPropertiesPropSheet>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v7; // edi
  _DWORD *v8; // rax
  CFsrmPropertiesPropSheet *v9; // rcx
  _DWORD *v10; // rbx
  int v11; // eax
  _DWORD *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  try
  {
    v8 = operator new(0x20u);
    v10 = v8;
    if ( v8 )
    {
      v8[2] = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CFsrmPropertiesPropSheet>::`vftable';
      v8[6] = 0;
      *((_QWORD *)v8 + 2) = &ATL::CComContainedObject<CFsrmPropertiesPropSheet>::`vftable';
      *((_QWORD *)v8 + 3) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v10 = 0;
    }
    v12 = v10;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v10 = v12;
  }
  if ( v10 )
  {
    v11 = CFsrmPropertiesPropSheet::FinalConstruct(v9);
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v10)(v10, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v10 + 24LL))(v10, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x18001394c  mov     [rsp+arg_10], r8
0x180013951  mov     [rsp+arg_8], rdx
0x180013956  push    rbx
0x180013957  push    rsi
0x180013958  push    rdi
0x180013959  push    r14
0x18001395b  push    r15
0x18001395d  sub     rsp, 30h
0x180013961  mov     rsi, r8
0x180013964  mov     r14, rdx
0x180013967  mov     r15, rcx
0x18001396a  test    r8, r8
0x18001396d  jnz     short loc_180013979
0x18001396f  mov     eax, 80004003h
0x180013974  jmp     loc_180013A46
0x180013979  mov     qword ptr [r8], 0
0x180013980  mov     edi, 8007000Eh
0x180013985  mov     [rsp+58h+arg_18], edi
0x180013989  mov     [rsp+58h+var_38], 0
0x180013992  mov     ecx, 20h ; ' '; Size
0x180013997  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001399c  mov     rbx, rax
0x18001399f  mov     [rsp+58h+var_30], rax
0x1800139a4  test    rax, rax
0x1800139a7  jz      short loc_1800139E5
0x1800139a9  mov     dword ptr [rax+8], 0
0x1800139b0  lea     rax, ??_7?$CComAggObject@VCFsrmPropertiesPropSheet@@@ATL@@6B@; const ATL::CComAggObject<CFsrmPropertiesPropSheet>::`vftable'
0x1800139b7  mov     [rbx], rax
0x1800139ba  mov     dword ptr [rbx+18h], 0
0x1800139c1  lea     rax, ??_7?$CComContainedObject@VCFsrmPropertiesPropSheet@@@ATL@@6B@; const ATL::CComContainedObject<CFsrmPropertiesPropSheet>::`vftable'
0x1800139c8  mov     [rbx+10h], rax
0x1800139cc  mov     [rbx+18h], r15
0x1800139d0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800139d7  mov     rax, [rcx]
0x1800139da  mov     rax, [rax+8]
0x1800139de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139e3  jmp     short loc_1800139E7
0x1800139e5  xor     ebx, ebx
0x1800139e7  mov     [rsp+58h+var_38], rbx
0x1800139ec  jmp     short loc_180013A01
0x1800139ee  mov     rsi, [rsp+58h+arg_10]
0x1800139f3  mov     r14, [rsp+58h+arg_8]
0x1800139f8  mov     edi, [rsp+58h+arg_18]
0x1800139fc  mov     rbx, [rsp+58h+var_38]
0x180013a01  test    rbx, rbx
0x180013a04  jz      short loc_180013A44
0x180013a06  call    ?FinalConstruct@CFsrmPropertiesPropSheet@@QEAAJXZ; CFsrmPropertiesPropSheet::FinalConstruct(void)
0x180013a0b  xor     edi, edi
0x180013a0d  test    eax, eax
0x180013a0f  cmovs   edi, eax
0x180013a12  test    edi, edi
0x180013a14  jnz     short loc_180013A30
0x180013a16  mov     rax, [rbx]
0x180013a19  mov     r8, rsi
0x180013a1c  mov     rdx, r14
0x180013a1f  mov     rcx, rbx
0x180013a22  mov     rax, [rax]
0x180013a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a2a  mov     edi, eax
0x180013a2c  test    eax, eax
0x180013a2e  jz      short loc_180013A44
0x180013a30  mov     rdx, [rbx]
0x180013a33  mov     rax, [rdx+18h]
0x180013a37  mov     edx, 1
0x180013a3c  mov     rcx, rbx
0x180013a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a44  mov     eax, edi
0x180013a46  add     rsp, 30h
0x180013a4a  pop     r15
0x180013a4c  pop     r14
0x180013a4e  pop     rdi
0x180013a4f  pop     rsi
0x180013a50  pop     rbx
0x180013a51  retn
```
