# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CElevateWlanUi>>,ATL::CComCreator<ATL::CComAggObject<CElevateWlanUi>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800039a0`
- end: `0x180003a88`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCElevateWlanUi@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCElevateWlanUi@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `232`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800011d0`
- `0x1800039a0`
- `0x180003a90`
- `0x180003e5c`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CElevateWlanUi>>,ATL::CComCreator<ATL::CComAggObject<CElevateWlanUi>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  _DWORD *v6; // rax
  _DWORD *v7; // rdi
  struct ATL::CAtlModule *v8; // rcx
  int v9; // ecx
  int v10; // eax

  if ( a1 )
  {
    return (unsigned int)ATL::CComCreator<ATL::CComAggObject<CElevateWlanUi>>::CreateInstance();
  }
  else if ( a3 )
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = operator new(0x40u);
    v7 = v6;
    if ( v6 )
    {
      v8 = ATL::_pAtlModule;
      v6[2] = 0;
      *((_OWORD *)v6 + 1) = 0;
      *((_OWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 6) = 0;
      *((_BYTE *)v6 + 56) = 0;
      *(_QWORD *)v6 = &ATL::CComObject<CElevateWlanUi>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
      v9 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v7 + 4));
      if ( v9 >= 0 )
        *((_BYTE *)v7 + 56) = 1;
      v10 = 0;
      if ( v9 < 0 )
        v10 = v9;
      v5 = 0;
      if ( v10 < 0 )
        v5 = v10;
      if ( v5 || (v5 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 48LL))(v7, 1);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v5;
}

```

## disassembly

```asm
0x1800039a0  push    rbx
0x1800039a2  push    rbp
0x1800039a3  push    rsi
0x1800039a4  push    rdi
0x1800039a5  sub     rsp, 28h
0x1800039a9  mov     rsi, r8
0x1800039ac  mov     rbp, rdx
0x1800039af  test    rcx, rcx
0x1800039b2  jnz     loc_180003A76
0x1800039b8  test    r8, r8
0x1800039bb  jnz     short loc_1800039C7
0x1800039bd  mov     ebx, 80004003h
0x1800039c2  jmp     loc_180003A7D
0x1800039c7  mov     ecx, 40h ; '@'; Size
0x1800039cc  mov     qword ptr [r8], 0
0x1800039d3  mov     ebx, 8007000Eh
0x1800039d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800039dd  mov     rdi, rax
0x1800039e0  test    rax, rax
0x1800039e3  jz      loc_180003A7D
0x1800039e9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800039f0  xorps   xmm0, xmm0
0x1800039f3  mov     dword ptr [rax+8], 0
0x1800039fa  xor     eax, eax
0x1800039fc  movups  xmmword ptr [rdi+10h], xmm0
0x180003a00  movups  xmmword ptr [rdi+20h], xmm0
0x180003a04  mov     [rdi+30h], rax
0x180003a08  mov     [rdi+38h], al
0x180003a0b  lea     rax, ??_7?$CComObject@VCElevateWlanUi@@@ATL@@6B@; const ATL::CComObject<CElevateWlanUi>::`vftable'
0x180003a12  mov     [rdi], rax
0x180003a15  mov     rax, [rcx]
0x180003a18  mov     rax, [rax+8]
0x180003a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a21  lea     rcx, [rdi+10h]; this
0x180003a25  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003a2a  mov     ecx, eax
0x180003a2c  test    eax, eax
0x180003a2e  js      short loc_180003A34
0x180003a30  mov     byte ptr [rdi+38h], 1
0x180003a34  xor     eax, eax
0x180003a36  test    ecx, ecx
0x180003a38  cmovs   eax, ecx
0x180003a3b  xor     ebx, ebx
0x180003a3d  test    eax, eax
0x180003a3f  cmovs   ebx, eax
0x180003a42  test    ebx, ebx
0x180003a44  jnz     short loc_180003A60
0x180003a46  mov     rax, [rdi]
0x180003a49  mov     r8, rsi
0x180003a4c  mov     rdx, rbp
0x180003a4f  mov     rcx, rdi
0x180003a52  mov     rax, [rax]
0x180003a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a5a  mov     ebx, eax
0x180003a5c  test    eax, eax
0x180003a5e  jz      short loc_180003A7D
0x180003a60  mov     rax, [rdi]
0x180003a63  mov     edx, 1
0x180003a68  mov     rcx, rdi
0x180003a6b  mov     rax, [rax+30h]
0x180003a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a74  jmp     short loc_180003A7D
0x180003a76  call    ?CreateInstance@?$CComCreator@V?$CComAggObject@VCElevateWlanUi@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CElevateWlanUi>>::CreateInstance(void *,_GUID const &,void * *)
0x180003a7b  mov     ebx, eax
0x180003a7d  mov     eax, ebx
0x180003a7f  add     rsp, 28h
0x180003a83  pop     rdi
0x180003a84  pop     rsi
0x180003a85  pop     rbp
0x180003a86  pop     rbx
0x180003a87  retn
```
