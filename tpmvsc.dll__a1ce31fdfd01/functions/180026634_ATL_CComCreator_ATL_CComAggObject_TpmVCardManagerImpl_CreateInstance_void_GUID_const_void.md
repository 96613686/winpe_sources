# ATL::CComCreator<ATL::CComAggObject<TpmVCardManagerImpl>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180026634`
- end: `0x180026715`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VTpmVCardManagerImpl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `225`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180026620`

## callees

- `0x1800023c0`
- `0x180026634`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<TpmVCardManagerImpl>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  _DWORD *v7; // rbx
  unsigned int v8; // edi
  _DWORD *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = operator new(0x20u);
    v7[2] = 0;
    *(_QWORD *)v7 = &ATL::CComAggObject<TpmVCardManagerImpl>::`vftable';
    *((_QWORD *)v7 + 2) = &ATL::CComContainedObject<TpmVCardManagerImpl>::`vftable';
    *((_QWORD *)v7 + 3) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, v4, v3);
    if ( v8 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
  }
  return v8;
}

```

## disassembly

```asm
0x180026634  mov     [rsp+arg_10], r8
0x180026639  mov     [rsp+arg_8], rdx
0x18002663e  push    rbx
0x18002663f  push    rsi
0x180026640  push    rdi
0x180026641  push    r14
0x180026643  push    r15
0x180026645  sub     rsp, 30h
0x180026649  mov     rsi, r8
0x18002664c  mov     r14, rdx
0x18002664f  mov     r15, rcx
0x180026652  test    r8, r8
0x180026655  jnz     short loc_180026661
0x180026657  mov     eax, 80004003h
0x18002665c  jmp     loc_180026709
0x180026661  mov     qword ptr [r8], 0
0x180026668  mov     edi, 8007000Eh
0x18002666d  mov     [rsp+58h+arg_18], edi
0x180026671  mov     [rsp+58h+var_38], 0
0x18002667a  mov     ecx, 20h ; ' '; Size
0x18002667f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026684  mov     rbx, rax
0x180026687  mov     dword ptr [rax+8], 0
0x18002668e  lea     rax, ??_7?$CComAggObject@VTpmVCardManagerImpl@@@ATL@@6B@; const ATL::CComAggObject<TpmVCardManagerImpl>::`vftable'
0x180026695  mov     [rbx], rax
0x180026698  lea     rax, ??_7?$CComContainedObject@VTpmVCardManagerImpl@@@ATL@@6B@; const ATL::CComContainedObject<TpmVCardManagerImpl>::`vftable'
0x18002669f  mov     [rbx+10h], rax
0x1800266a3  mov     [rbx+18h], r15
0x1800266a7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800266ae  mov     rax, [rcx]
0x1800266b1  mov     rax, [rax+8]
0x1800266b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266ba  mov     [rsp+58h+var_38], rbx
0x1800266bf  jmp     short loc_1800266D4
0x1800266c1  mov     rsi, [rsp+58h+arg_10]
0x1800266c6  mov     r14, [rsp+58h+arg_8]
0x1800266cb  mov     edi, [rsp+58h+arg_18]
0x1800266cf  mov     rbx, [rsp+58h+var_38]
0x1800266d4  test    rbx, rbx
0x1800266d7  jz      short loc_180026707
0x1800266d9  mov     rax, [rbx]
0x1800266dc  mov     r8, rsi
0x1800266df  mov     rdx, r14
0x1800266e2  mov     rcx, rbx
0x1800266e5  mov     rax, [rax]
0x1800266e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266ed  mov     edi, eax
0x1800266ef  test    eax, eax
0x1800266f1  jz      short loc_180026707
0x1800266f3  mov     rdx, [rbx]
0x1800266f6  mov     rax, [rdx+18h]
0x1800266fa  mov     edx, 1
0x1800266ff  mov     rcx, rbx
0x180026702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026707  mov     eax, edi
0x180026709  add     rsp, 30h
0x18002670d  pop     r15
0x18002670f  pop     r14
0x180026711  pop     rdi
0x180026712  pop     rsi
0x180026713  pop     rbx
0x180026714  retn
```
