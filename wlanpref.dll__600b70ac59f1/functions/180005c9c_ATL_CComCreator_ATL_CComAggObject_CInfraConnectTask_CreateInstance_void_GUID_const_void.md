# ATL::CComCreator<ATL::CComAggObject<CInfraConnectTask>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005c9c`
- end: `0x180005dce`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCInfraConnectTask@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800058f0`

## callees

- `0x18000130c`
- `0x180005c9c`
- `0x1800080a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CInfraConnectTask>>::CreateInstance(
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
      *(_QWORD *)v8 = &ATL::CComAggObject<CInfraConnectTask>::`vftable';
      *(_OWORD *)(v8 + 40) = 0;
      *(_OWORD *)(v8 + 56) = 0;
      *((_QWORD *)v8 + 9) = 0;
      v8[80] = 0;
      *((_QWORD *)v8 + 11) = 0;
      *((_QWORD *)v8 + 12) = 0;
      *(GUID *)(v8 + 104) = GUID_NULL;
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CInfraConnectTask>::`vftable';
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
0x180005c9c  mov     [rsp+arg_10], r8
0x180005ca1  mov     [rsp+arg_8], rdx
0x180005ca6  push    rsi
0x180005ca7  push    rdi
0x180005ca8  push    r12
0x180005caa  push    r14
0x180005cac  push    r15
0x180005cae  sub     rsp, 30h
0x180005cb2  mov     r14, r8
0x180005cb5  mov     r15, rdx
0x180005cb8  mov     r12, rcx
0x180005cbb  test    r8, r8
0x180005cbe  jnz     short loc_180005CCA
0x180005cc0  mov     eax, 80004003h
0x180005cc5  jmp     loc_180005DC1
0x180005cca  mov     qword ptr [r8], 0
0x180005cd1  mov     esi, 8007000Eh
0x180005cd6  mov     [rsp+58h+arg_18], esi
0x180005cda  mov     [rsp+58h+var_38], 0
0x180005ce3  mov     ecx, 78h ; 'x'; Size
0x180005ce8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005ced  mov     rdi, rax
0x180005cf0  test    rdi, rdi
0x180005cf3  jz      short loc_180005D50
0x180005cf5  mov     dword ptr [rax+8], 0
0x180005cfc  lea     rax, ??_7?$CComAggObject@VCInfraConnectTask@@@ATL@@6B@; const ATL::CComAggObject<CInfraConnectTask>::`vftable'
0x180005d03  mov     [rdi], rax
0x180005d06  xorps   xmm0, xmm0
0x180005d09  xor     eax, eax
0x180005d0b  movups  xmmword ptr [rdi+28h], xmm0
0x180005d0f  movups  xmmword ptr [rdi+38h], xmm0
0x180005d13  mov     [rdi+48h], rax
0x180005d17  mov     [rdi+50h], al
0x180005d1a  mov     [rdi+58h], rax
0x180005d1e  mov     [rdi+60h], rax
0x180005d22  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180005d29  movdqu  xmmword ptr [rdi+68h], xmm0
0x180005d2e  lea     rax, ??_7?$CComContainedObject@VCInfraConnectTask@@@ATL@@6B@; const ATL::CComContainedObject<CInfraConnectTask>::`vftable'
0x180005d35  mov     [rdi+18h], rax
0x180005d39  mov     [rdi+20h], r12
0x180005d3d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005d44  mov     rax, [rcx]
0x180005d47  mov     rax, [rax+8]
0x180005d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d50  mov     [rsp+58h+var_38], rdi
0x180005d55  jmp     short loc_180005D6A
0x180005d57  mov     r14, [rsp+58h+arg_10]
0x180005d5c  mov     r15, [rsp+58h+arg_8]
0x180005d61  mov     esi, [rsp+58h+arg_18]
0x180005d65  mov     rdi, [rsp+58h+var_38]
0x180005d6a  test    rdi, rdi
0x180005d6d  jz      short loc_180005DBF
0x180005d6f  lea     rcx, [rdi+28h]; this
0x180005d73  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180005d78  xor     ecx, ecx
0x180005d7a  test    eax, eax
0x180005d7c  cmovs   ecx, eax
0x180005d7f  xor     eax, eax
0x180005d81  test    ecx, ecx
0x180005d83  cmovs   eax, ecx
0x180005d86  xor     esi, esi
0x180005d88  test    eax, eax
0x180005d8a  cmovs   esi, eax
0x180005d8d  test    esi, esi
0x180005d8f  jnz     short loc_180005DAB
0x180005d91  mov     rax, [rdi]
0x180005d94  mov     r8, r14
0x180005d97  mov     rdx, r15
0x180005d9a  mov     rcx, rdi
0x180005d9d  mov     rax, [rax]
0x180005da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da5  mov     esi, eax
0x180005da7  test    eax, eax
0x180005da9  jz      short loc_180005DBF
0x180005dab  mov     rdx, [rdi]
0x180005dae  mov     rax, [rdx+18h]
0x180005db2  mov     edx, 1
0x180005db7  mov     rcx, rdi
0x180005dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dbf  mov     eax, esi
0x180005dc1  add     rsp, 30h
0x180005dc5  pop     r15
0x180005dc7  pop     r14
0x180005dc9  pop     r12
0x180005dcb  pop     rdi
0x180005dcc  pop     rsi
0x180005dcd  retn
```
