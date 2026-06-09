# ATL::CComCreator<ATL::CComAggObject<CInfraCreateTask>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005f04`
- end: `0x18000602a`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCInfraCreateTask@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005930`

## callees

- `0x18000130c`
- `0x180005f04`
- `0x1800080a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CInfraCreateTask>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  char *v8; // rax
  char *v9; // rdi
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  char *v13; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x78u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CInfraCreateTask>::`vftable';
      *(_OWORD *)(v8 + 40) = 0;
      *(_OWORD *)(v8 + 56) = 0;
      *((_QWORD *)v8 + 9) = 0;
      v8[80] = 0;
      *((_QWORD *)v8 + 11) = 0;
      *((_QWORD *)v8 + 12) = 0;
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CInfraCreateTask>::`vftable';
      *((_QWORD *)v8 + 4) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v13;
  }
  if ( v9 )
  {
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 40));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v7 = 0;
    if ( v12 < 0 )
      v7 = v12;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180005f04  mov     [rsp+arg_10], r8
0x180005f09  mov     [rsp+arg_8], rdx
0x180005f0e  push    rsi
0x180005f0f  push    rdi
0x180005f10  push    r12
0x180005f12  push    r14
0x180005f14  push    r15
0x180005f16  sub     rsp, 30h
0x180005f1a  mov     r14, r8
0x180005f1d  mov     r15, rdx
0x180005f20  mov     r12, rcx
0x180005f23  test    r8, r8
0x180005f26  jnz     short loc_180005F32
0x180005f28  mov     eax, 80004003h
0x180005f2d  jmp     loc_18000601D
0x180005f32  mov     qword ptr [r8], 0
0x180005f39  mov     esi, 8007000Eh
0x180005f3e  mov     [rsp+58h+arg_18], esi
0x180005f42  mov     [rsp+58h+var_38], 0
0x180005f4b  mov     ecx, 78h ; 'x'; Size
0x180005f50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005f55  mov     rdi, rax
0x180005f58  test    rdi, rdi
0x180005f5b  jz      short loc_180005FAC
0x180005f5d  mov     dword ptr [rax+8], 0
0x180005f64  lea     rax, ??_7?$CComAggObject@VCInfraCreateTask@@@ATL@@6B@; const ATL::CComAggObject<CInfraCreateTask>::`vftable'
0x180005f6b  mov     [rdi], rax
0x180005f6e  xorps   xmm0, xmm0
0x180005f71  xor     eax, eax
0x180005f73  movups  xmmword ptr [rdi+28h], xmm0
0x180005f77  movups  xmmword ptr [rdi+38h], xmm0
0x180005f7b  mov     [rdi+48h], rax
0x180005f7f  mov     [rdi+50h], al
0x180005f82  mov     [rdi+58h], rax
0x180005f86  mov     [rdi+60h], rax
0x180005f8a  lea     rax, ??_7?$CComContainedObject@VCInfraCreateTask@@@ATL@@6B@; const ATL::CComContainedObject<CInfraCreateTask>::`vftable'
0x180005f91  mov     [rdi+18h], rax
0x180005f95  mov     [rdi+20h], r12
0x180005f99  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005fa0  mov     rax, [rcx]
0x180005fa3  mov     rax, [rax+8]
0x180005fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fac  mov     [rsp+58h+var_38], rdi
0x180005fb1  jmp     short loc_180005FC6
0x180005fb3  mov     r14, [rsp+58h+arg_10]
0x180005fb8  mov     r15, [rsp+58h+arg_8]
0x180005fbd  mov     esi, [rsp+58h+arg_18]
0x180005fc1  mov     rdi, [rsp+58h+var_38]
0x180005fc6  test    rdi, rdi
0x180005fc9  jz      short loc_18000601B
0x180005fcb  lea     rcx, [rdi+28h]; this
0x180005fcf  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180005fd4  xor     ecx, ecx
0x180005fd6  test    eax, eax
0x180005fd8  cmovs   ecx, eax
0x180005fdb  xor     eax, eax
0x180005fdd  test    ecx, ecx
0x180005fdf  cmovs   eax, ecx
0x180005fe2  xor     esi, esi
0x180005fe4  test    eax, eax
0x180005fe6  cmovs   esi, eax
0x180005fe9  test    esi, esi
0x180005feb  jnz     short loc_180006007
0x180005fed  mov     rax, [rdi]
0x180005ff0  mov     r8, r14
0x180005ff3  mov     rdx, r15
0x180005ff6  mov     rcx, rdi
0x180005ff9  mov     rax, [rax]
0x180005ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006001  mov     esi, eax
0x180006003  test    eax, eax
0x180006005  jz      short loc_18000601B
0x180006007  mov     rdx, [rdi]
0x18000600a  mov     rax, [rdx+18h]
0x18000600e  mov     edx, 1
0x180006013  mov     rcx, rdi
0x180006016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000601b  mov     eax, esi
0x18000601d  add     rsp, 30h
0x180006021  pop     r15
0x180006023  pop     r14
0x180006025  pop     r12
0x180006027  pop     rdi
0x180006028  pop     rsi
0x180006029  retn
```
