# ATL::CComCreator<ATL::CComObject<CPXWizardFactoryRegistration>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800041d0`
- end: `0x1800042d4`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPXWizardFactoryRegistration@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003e10`

## callees

- `0x1800011dc`
- `0x1800041d0`
- `0x180004a90`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CPXWizardFactoryRegistration>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
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
    v7 = operator new(0x40u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *((_OWORD *)v7 + 1) = 0;
      *((_OWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *((_BYTE *)v7 + 56) = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CPXWizardFactoryRegistration>::`vftable';
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
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 88LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800041d0  mov     [rsp+arg_10], r8
0x1800041d5  mov     [rsp+arg_8], rdx
0x1800041da  mov     [rsp+arg_0], rcx
0x1800041df  push    rbx
0x1800041e0  push    rsi
0x1800041e1  push    rdi
0x1800041e2  push    r14
0x1800041e4  sub     rsp, 28h
0x1800041e8  mov     rsi, r8
0x1800041eb  mov     r14, rdx
0x1800041ee  test    r8, r8
0x1800041f1  jnz     short loc_1800041FD
0x1800041f3  mov     eax, 80004003h
0x1800041f8  jmp     loc_1800042CA
0x1800041fd  mov     qword ptr [r8], 0
0x180004204  mov     edi, 8007000Eh
0x180004209  mov     dword ptr [rsp+48h+arg_0], edi
0x18000420d  mov     [rsp+48h+arg_18], 0
0x180004216  mov     ecx, 40h ; '@'; Size
0x18000421b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004220  mov     rbx, rax
0x180004223  test    rbx, rbx
0x180004226  jz      short loc_180004260
0x180004228  mov     dword ptr [rax+8], 0
0x18000422f  xorps   xmm0, xmm0
0x180004232  xor     eax, eax
0x180004234  movups  xmmword ptr [rbx+10h], xmm0
0x180004238  movups  xmmword ptr [rbx+20h], xmm0
0x18000423c  mov     [rbx+30h], rax
0x180004240  mov     [rbx+38h], al
0x180004243  lea     rax, ??_7?$CComObject@VCPXWizardFactoryRegistration@@@ATL@@6B@; const ATL::CComObject<CPXWizardFactoryRegistration>::`vftable'
0x18000424a  mov     [rbx], rax
0x18000424d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004254  mov     rax, [rcx]
0x180004257  mov     rax, [rax+8]
0x18000425b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004260  mov     [rsp+48h+arg_18], rbx
0x180004265  jmp     short loc_18000427A
0x180004267  mov     rsi, [rsp+48h+arg_10]
0x18000426c  mov     r14, [rsp+48h+arg_8]
0x180004271  mov     edi, dword ptr [rsp+48h+arg_0]
0x180004275  mov     rbx, [rsp+48h+arg_18]
0x18000427a  test    rbx, rbx
0x18000427d  jz      short loc_1800042C8
0x18000427f  lea     rcx, [rbx+10h]; this
0x180004283  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180004288  xor     ecx, ecx
0x18000428a  test    eax, eax
0x18000428c  cmovs   ecx, eax
0x18000428f  xor     edi, edi
0x180004291  test    ecx, ecx
0x180004293  cmovs   edi, ecx
0x180004296  test    edi, edi
0x180004298  jnz     short loc_1800042B4
0x18000429a  mov     rax, [rbx]
0x18000429d  mov     r8, rsi
0x1800042a0  mov     rdx, r14
0x1800042a3  mov     rcx, rbx
0x1800042a6  mov     rax, [rax]
0x1800042a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ae  mov     edi, eax
0x1800042b0  test    eax, eax
0x1800042b2  jz      short loc_1800042C8
0x1800042b4  mov     rdx, [rbx]
0x1800042b7  mov     rax, [rdx+58h]
0x1800042bb  mov     edx, 1
0x1800042c0  mov     rcx, rbx
0x1800042c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042c8  mov     eax, edi
0x1800042ca  add     rsp, 28h
0x1800042ce  pop     r14
0x1800042d0  pop     rdi
0x1800042d1  pop     rsi
0x1800042d2  pop     rbx
0x1800042d3  retn
```
