# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180013c80`
- end: `0x180013e0b`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `395`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001264`
- `0x18000968c`
- `0x180013c80`
- `0x180020010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180013df4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013df4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013deb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013deb`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r13
  unsigned int v6; // esi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  int v9; // ecx
  int v10; // eax
  _QWORD *v11; // [rsp+20h] [rbp-58h]

  v3 = a3;
  v4 = a1;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  try
  {
    v7 = operator new(0x48u);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 2) = 0;
      *((_OWORD *)v7 + 1) = 0;
      *((_OWORD *)v7 + 2) = 0;
      v7[6] = 0;
      *((_BYTE *)v7 + 56) = 0;
      *v7 = &ATL::CComClassFactory::`vftable';
      *v7 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    }
    else
    {
      v8 = 0;
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a1;
    v6 = -2147024882;
    v8 = v11;
  }
  if ( v8 )
  {
    v8[8] = v4;
    v9 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 2));
    if ( v9 >= 0 )
      *((_BYTE *)v8 + 56) = 1;
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v8)(v8, a2, v3)) != 0 )
    {
      *v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
      *((_DWORD *)v8 + 2) = -1073741823;
      *v8 = &ATL::CComClassFactory::`vftable';
      if ( *((_BYTE *)v8 + 56) )
      {
        *((_BYTE *)v8 + 56) = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v8 + 2));
      }
      operator delete(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180013c80  mov     [rsp+arg_10], r8
0x180013c85  mov     [rsp+arg_8], rdx
0x180013c8a  mov     [rsp+arg_0], rcx
0x180013c8f  push    rbx
0x180013c90  push    rsi
0x180013c91  push    r12
0x180013c93  push    r13
0x180013c95  push    r14
0x180013c97  push    r15
0x180013c99  sub     rsp, 48h
0x180013c9d  mov     r14, r8
0x180013ca0  mov     r13, rcx
0x180013ca3  test    r8, r8
0x180013ca6  jnz     short loc_180013CB2
0x180013ca8  mov     eax, 80004003h
0x180013cad  jmp     loc_180013DFC
0x180013cb2  mov     qword ptr [r8], 0
0x180013cb9  mov     esi, 8007000Eh
0x180013cbe  mov     dword ptr [rsp+78h+arg_18], esi
0x180013cc5  mov     [rsp+78h+var_58], 0
0x180013cce  mov     ecx, 48h ; 'H'; Size
0x180013cd3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013cd8  mov     rbx, rax
0x180013cdb  mov     [rsp+78h+var_50], rax
0x180013ce0  test    rax, rax
0x180013ce3  jz      short loc_180013D26
0x180013ce5  add     rax, 8
0x180013ce9  mov     [rsp+78h+var_48], rax
0x180013cee  mov     dword ptr [rax], 0
0x180013cf4  add     rax, 8
0x180013cf8  mov     [rsp+78h+var_40], rax
0x180013cfd  xorps   xmm0, xmm0
0x180013d00  xor     ecx, ecx
0x180013d02  movups  xmmword ptr [rax], xmm0
0x180013d05  movups  xmmword ptr [rax+10h], xmm0
0x180013d09  mov     [rax+20h], rcx
0x180013d0d  mov     [rax+28h], cl
0x180013d10  lea     r15, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180013d17  mov     [rbx], r15
0x180013d1a  lea     r12, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180013d21  mov     [rbx], r12
0x180013d24  jmp     short loc_180013D36
0x180013d26  xor     ebx, ebx
0x180013d28  lea     r15, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180013d2f  lea     r12, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180013d36  mov     [rsp+78h+var_58], rbx
0x180013d3b  jmp     short loc_180013D67
0x180013d3d  lea     r15, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180013d44  lea     r12, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180013d4b  mov     r14, [rsp+78h+arg_10]
0x180013d53  mov     r13, [rsp+78h+arg_0]
0x180013d5b  mov     esi, dword ptr [rsp+78h+arg_18]
0x180013d62  mov     rbx, [rsp+78h+var_58]
0x180013d67  test    rbx, rbx
0x180013d6a  jz      loc_180013DFA
0x180013d70  mov     [rbx+40h], r13
0x180013d74  lea     rcx, [rbx+10h]; this
0x180013d78  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180013d7d  mov     ecx, eax
0x180013d7f  test    eax, eax
0x180013d81  js      short loc_180013D87
0x180013d83  mov     byte ptr [rbx+38h], 1
0x180013d87  xor     eax, eax
0x180013d89  test    ecx, ecx
0x180013d8b  cmovs   eax, ecx
0x180013d8e  xor     esi, esi
0x180013d90  test    eax, eax
0x180013d92  cmovs   esi, eax
0x180013d95  test    esi, esi
0x180013d97  jnz     short loc_180013DB8
0x180013d99  mov     rax, [rbx]
0x180013d9c  mov     r8, r14
0x180013d9f  mov     rdx, [rsp+78h+arg_8]
0x180013da7  mov     rcx, rbx
0x180013daa  mov     rax, [rax]
0x180013dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013db2  mov     esi, eax
0x180013db4  test    eax, eax
0x180013db6  jz      short loc_180013DFA
0x180013db8  mov     [rsp+78h+arg_10], rbx
0x180013dc0  mov     [rbx], r12
0x180013dc3  lea     rax, [rbx+8]
0x180013dc7  mov     dword ptr [rax], 0C0000001h
0x180013dcd  mov     [rbx], r15
0x180013dd0  mov     [rsp+78h+arg_18], rax
0x180013dd8  lea     rcx, [rax+8]; lpCriticalSection
0x180013ddc  mov     [rsp+78h+var_40], rcx
0x180013de1  cmp     byte ptr [rcx+28h], 0
0x180013de5  jz      short loc_180013DF1
0x180013de7  mov     byte ptr [rcx+28h], 0
0x180013deb  call    cs:__imp_DeleteCriticalSection
0x180013df1  mov     rcx, rbx
0x180013df4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013dfa  mov     eax, esi
0x180013dfc  add     rsp, 48h
0x180013e00  pop     r15
0x180013e02  pop     r14
0x180013e04  pop     r13
0x180013e06  pop     r12
0x180013e08  pop     rsi
0x180013e09  pop     rbx
0x180013e0a  retn
```
