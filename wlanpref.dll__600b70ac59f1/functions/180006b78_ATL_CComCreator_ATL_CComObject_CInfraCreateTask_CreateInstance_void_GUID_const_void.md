# ATL::CComCreator<ATL::CComObject<CInfraCreateTask>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006b78`
- end: `0x180006c89`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCInfraCreateTask@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005930`

## callees

- `0x18000130c`
- `0x180006b78`
- `0x1800080a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CInfraCreateTask>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  int v9; // eax
  int v10; // ecx
  _DWORD *v13; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x60u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *((_OWORD *)v7 + 1) = 0;
      *((_OWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *((_BYTE *)v7 + 56) = 0;
      *((_QWORD *)v7 + 8) = 0;
      *((_QWORD *)v7 + 9) = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CInfraCreateTask>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v8 + 4));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 136LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180006b78  mov     [rsp+arg_10], r8
0x180006b7d  mov     [rsp+arg_8], rdx
0x180006b82  mov     [rsp+arg_0], rcx
0x180006b87  push    rsi
0x180006b88  push    rdi
0x180006b89  push    r14
0x180006b8b  push    r15
0x180006b8d  sub     rsp, 28h
0x180006b91  mov     r14, r8
0x180006b94  mov     r15, rdx
0x180006b97  test    r8, r8
0x180006b9a  jnz     short loc_180006BA6
0x180006b9c  mov     eax, 80004003h
0x180006ba1  jmp     loc_180006C7E
0x180006ba6  mov     qword ptr [r8], 0
0x180006bad  mov     esi, 8007000Eh
0x180006bb2  mov     dword ptr [rsp+48h+arg_0], esi
0x180006bb6  mov     [rsp+48h+arg_18], 0
0x180006bbf  mov     ecx, 60h ; '`'; Size
0x180006bc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006bc9  mov     rdi, rax
0x180006bcc  test    rdi, rdi
0x180006bcf  jz      short loc_180006C11
0x180006bd1  mov     dword ptr [rax+8], 0
0x180006bd8  xorps   xmm0, xmm0
0x180006bdb  xor     eax, eax
0x180006bdd  movups  xmmword ptr [rdi+10h], xmm0
0x180006be1  movups  xmmword ptr [rdi+20h], xmm0
0x180006be5  mov     [rdi+30h], rax
0x180006be9  mov     [rdi+38h], al
0x180006bec  mov     [rdi+40h], rax
0x180006bf0  mov     [rdi+48h], rax
0x180006bf4  lea     rax, ??_7?$CComObject@VCInfraCreateTask@@@ATL@@6B@; const ATL::CComObject<CInfraCreateTask>::`vftable'
0x180006bfb  mov     [rdi], rax
0x180006bfe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006c05  mov     rax, [rcx]
0x180006c08  mov     rax, [rax+8]
0x180006c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c11  mov     [rsp+48h+arg_18], rdi
0x180006c16  jmp     short loc_180006C2B
0x180006c18  mov     r14, [rsp+48h+arg_10]
0x180006c1d  mov     r15, [rsp+48h+arg_8]
0x180006c22  mov     esi, dword ptr [rsp+48h+arg_0]
0x180006c26  mov     rdi, [rsp+48h+arg_18]
0x180006c2b  test    rdi, rdi
0x180006c2e  jz      short loc_180006C7C
0x180006c30  lea     rcx, [rdi+10h]; this
0x180006c34  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180006c39  xor     ecx, ecx
0x180006c3b  test    eax, eax
0x180006c3d  cmovs   ecx, eax
0x180006c40  xor     esi, esi
0x180006c42  test    ecx, ecx
0x180006c44  cmovs   esi, ecx
0x180006c47  test    esi, esi
0x180006c49  jnz     short loc_180006C65
0x180006c4b  mov     rax, [rdi]
0x180006c4e  mov     r8, r14
0x180006c51  mov     rdx, r15
0x180006c54  mov     rcx, rdi
0x180006c57  mov     rax, [rax]
0x180006c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c5f  mov     esi, eax
0x180006c61  test    eax, eax
0x180006c63  jz      short loc_180006C7C
0x180006c65  mov     rdx, [rdi]
0x180006c68  mov     rax, [rdx+88h]
0x180006c6f  mov     edx, 1
0x180006c74  mov     rcx, rdi
0x180006c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c7c  mov     eax, esi
0x180006c7e  add     rsp, 28h
0x180006c82  pop     r15
0x180006c84  pop     r14
0x180006c86  pop     rdi
0x180006c87  pop     rsi
0x180006c88  retn
```
