# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800117d0`
- end: `0x1800118e4`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000213c`
- `0x180002148`
- `0x1800117d0`
- `0x180011aec`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800118c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800118c2`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r12
  __int64 v5; // r15
  _BYTE *v7; // rbx
  int v8; // esi
  _BYTE *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = operator new(0x48u);
    *((_DWORD *)v7 + 2) = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    v7[56] = 0;
    *(_QWORD *)v7 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    *((_QWORD *)v7 + 8) = v5;
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 16));
    if ( v8 < 0 || (v7[56] = 1, (v8 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
    {
      *((_DWORD *)v7 + 2) = -1073741823;
      *(_QWORD *)v7 = &ATL::CComClassFactory::`vftable';
      if ( v7[56] )
      {
        v7[56] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
      }
      operator delete(v7);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800117d0  mov     [rsp+arg_10], r8
0x1800117d5  mov     [rsp+arg_8], rdx
0x1800117da  mov     [rsp+arg_0], rcx
0x1800117df  push    rbx
0x1800117e0  push    rsi
0x1800117e1  push    r12
0x1800117e3  push    r14
0x1800117e5  push    r15
0x1800117e7  sub     rsp, 30h
0x1800117eb  mov     r14, r8
0x1800117ee  mov     r12, rdx
0x1800117f1  mov     r15, rcx
0x1800117f4  test    r8, r8
0x1800117f7  jnz     short loc_180011803
0x1800117f9  mov     eax, 80004003h
0x1800117fe  jmp     loc_1800118D7
0x180011803  mov     qword ptr [r8], 0
0x18001180a  mov     esi, 8007000Eh
0x18001180f  mov     [rsp+58h+arg_18], esi
0x180011813  mov     [rsp+58h+var_38], 0
0x18001181c  mov     ecx, 48h ; 'H'; Size
0x180011821  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011826  mov     rbx, rax
0x180011829  mov     dword ptr [rax+8], 0
0x180011830  xorps   xmm0, xmm0
0x180011833  xor     eax, eax
0x180011835  movups  xmmword ptr [rbx+10h], xmm0
0x180011839  movups  xmmword ptr [rbx+20h], xmm0
0x18001183d  mov     [rbx+30h], rax
0x180011841  mov     [rbx+38h], al
0x180011844  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18001184b  mov     [rbx], rax
0x18001184e  mov     [rsp+58h+var_38], rbx
0x180011853  jmp     short loc_18001186D
0x180011855  mov     r14, [rsp+58h+arg_10]
0x18001185a  mov     r12, [rsp+58h+arg_8]
0x18001185f  mov     r15, [rsp+58h+arg_0]
0x180011864  mov     esi, [rsp+58h+arg_18]
0x180011868  mov     rbx, [rsp+58h+var_38]
0x18001186d  test    rbx, rbx
0x180011870  jz      short loc_1800118D5
0x180011872  mov     [rbx+40h], r15
0x180011876  lea     rcx, [rbx+10h]; this
0x18001187a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18001187f  mov     esi, eax
0x180011881  test    eax, eax
0x180011883  js      short loc_1800118A3
0x180011885  mov     byte ptr [rbx+38h], 1
0x180011889  mov     rax, [rbx]
0x18001188c  mov     r8, r14
0x18001188f  mov     rdx, r12
0x180011892  mov     rcx, rbx
0x180011895  mov     rax, [rax]
0x180011898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001189d  mov     esi, eax
0x18001189f  test    eax, eax
0x1800118a1  jz      short loc_1800118D5
0x1800118a3  mov     dword ptr [rbx+8], 0C0000001h
0x1800118aa  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800118b1  mov     [rbx], rax
0x1800118b4  cmp     byte ptr [rbx+38h], 0
0x1800118b8  jz      short loc_1800118C8
0x1800118ba  mov     byte ptr [rbx+38h], 0
0x1800118be  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800118c2  call    cs:__imp_DeleteCriticalSection
0x1800118c8  mov     edx, 48h ; 'H'
0x1800118cd  mov     rcx, rbx; Block
0x1800118d0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800118d5  mov     eax, esi
0x1800118d7  add     rsp, 30h
0x1800118db  pop     r15
0x1800118dd  pop     r14
0x1800118df  pop     r12
0x1800118e1  pop     rsi
0x1800118e2  pop     rbx
0x1800118e3  retn
```
