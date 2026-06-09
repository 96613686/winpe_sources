# CWdsComMetadataBuilder::CreateInstance(CWdsMetadata const *,ATL::CComObject<CWdsComMetadataBuilder> * *)

- ea: `0x18000e504`
- end: `0x18000e655`
- name: `?CreateInstance@CWdsComMetadataBuilder@@SAJPEBVCWdsMetadata@@PEAPEAV?$CComObject@VCWdsComMetadataBuilder@@@ATL@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(struct CWdsMetadata *)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800042f4`
- `0x180005818`
- `0x18000600c`
- `0x1800078b0`
- `0x18000ef20`

## callees

- `0x180001cd0`
- `0x18000b834`
- `0x18000e458`
- `0x18000e504`
- `0x180014d58`
- `0x180014ee0`
- `0x180015068`
- `0x180015cc0`

## string_xrefs

- `0x18000e5a5`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000e5df`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000e607`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::CreateInstance(struct CWdsMetadata *a1, CWdsComMetadataBuilder **a2)
{
  unsigned int v4; // edi
  CWdsComMetadataBuilder *v5; // rax
  const char *v6; // rdx
  CWdsComMetadataBuilder *v7; // rbx
  int v8; // eax
  CWdsComMetadataBuilder *v9; // rsi
  signed int appended; // esi
  const char *v11; // rdx
  const char *v12; // rdx

  v4 = -2147024882;
  v5 = (CWdsComMetadataBuilder *)operator new(0xB0u);
  v7 = v5;
  if ( v5 )
  {
    CWdsComMetadataBuilder::CWdsComMetadataBuilder(v5);
    *(_QWORD *)v7 = &ATL::CComObject<CWdsComMetadataBuilder>::`vftable';
    _InterlockedIncrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  }
  else
  {
    v7 = 0;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((CWdsComMetadataBuilder *)((char *)v7 + 16));
    if ( v8 >= 0 )
    {
      *((_BYTE *)v7 + 56) = 1;
      v8 = 0;
    }
    v4 = 0;
    if ( v8 < 0 )
      v4 = v8;
    if ( v4 )
    {
      (*(void (__fastcall **)(CWdsComMetadataBuilder *, __int64))(*(_QWORD *)v7 + 344LL))(v7, 1);
      v7 = 0;
    }
  }
  v9 = v7;
  if ( (int)ElValidateHr(v4, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0xDBu) >= 0 )
  {
    (*(void (__fastcall **)(CWdsComMetadataBuilder *))(*(_QWORD *)v7 + 8LL))(v7);
    v4 = 0;
    appended = CWdsMetadata::AppendAll((CWdsComMetadataBuilder *)((char *)v7 + 64), a1);
    if ( ElValidateWin32(appended, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x9Eu) )
    {
      v4 = (unsigned __int16)appended | 0x80070000;
      if ( appended <= 0 )
        v4 = appended;
    }
    v9 = v7;
    if ( (int)ElValidateHr(v4, v12, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0xE0u) >= 0 )
    {
      *a2 = v7;
      v9 = 0;
      v7 = 0;
    }
  }
  if ( v9 )
    (*(void (__fastcall **)(CWdsComMetadataBuilder *))(*(_QWORD *)v7 + 16LL))(v7);
  return v4;
}

```

## disassembly

```asm
0x18000e504  mov     [rsp+arg_0], rbx
0x18000e509  mov     [rsp+arg_8], rbp
0x18000e50e  mov     [rsp+arg_10], rsi
0x18000e513  push    rdi
0x18000e514  push    r14
0x18000e516  push    r15
0x18000e518  sub     rsp, 20h
0x18000e51c  mov     rbp, rcx
0x18000e51f  mov     r14, rdx
0x18000e522  mov     ecx, 0B0h; Size
0x18000e527  mov     edi, 8007000Eh
0x18000e52c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e531  xor     r15d, r15d
0x18000e534  mov     rbx, rax
0x18000e537  test    rax, rax
0x18000e53a  jz      short loc_18000E55B
0x18000e53c  mov     rcx, rax; this
0x18000e53f  call    ??0CWdsComMetadataBuilder@@QEAA@XZ; CWdsComMetadataBuilder::CWdsComMetadataBuilder(void)
0x18000e544  lea     rax, ??_7?$CComObject@VCWdsComMetadataBuilder@@@ATL@@6B@; const ATL::CComObject<CWdsComMetadataBuilder>::`vftable'
0x18000e54b  mov     [rbx], rax
0x18000e54e  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e555  lock inc dword ptr [rax+0Ch]
0x18000e559  jmp     short loc_18000E55E
0x18000e55b  mov     rbx, r15
0x18000e55e  test    rbx, rbx
0x18000e561  jz      short loc_18000E59F
0x18000e563  lea     rcx, [rbx+10h]; this
0x18000e567  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000e56c  test    eax, eax
0x18000e56e  js      short loc_18000E574
0x18000e570  mov     byte ptr [rbx+38h], 1
0x18000e574  cmovns  eax, r15d
0x18000e578  mov     edi, r15d
0x18000e57b  test    eax, eax
0x18000e57d  cmovs   edi, eax
0x18000e580  test    edi, edi
0x18000e582  jz      short loc_18000E59F
0x18000e584  mov     rax, [rbx]
0x18000e587  mov     edx, 1
0x18000e58c  mov     rcx, rbx
0x18000e58f  mov     rax, [rax+158h]
0x18000e596  call    cs:__guard_dispatch_icall_fptr
0x18000e59c  mov     rbx, r15
0x18000e59f  mov     r9d, 0DBh; unsigned int
0x18000e5a5  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e5ac  mov     ecx, edi; int
0x18000e5ae  mov     rsi, rbx
0x18000e5b1  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000e5b6  test    eax, eax
0x18000e5b8  js      short loc_18000E625
0x18000e5ba  mov     rax, [rbx]
0x18000e5bd  mov     rcx, rbx
0x18000e5c0  mov     rax, [rax+8]
0x18000e5c4  call    cs:__guard_dispatch_icall_fptr
0x18000e5ca  lea     rcx, [rbx+40h]; this
0x18000e5ce  mov     rdx, rbp; struct CWdsMetadata *
0x18000e5d1  mov     edi, r15d
0x18000e5d4  call    ?AppendAll@CWdsMetadata@@QEAAKPEBV1@@Z; CWdsMetadata::AppendAll(CWdsMetadata const *)
0x18000e5d9  mov     r9d, 9Eh; unsigned int
0x18000e5df  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e5e6  mov     ecx, eax; unsigned int
0x18000e5e8  mov     esi, eax
0x18000e5ea  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e5ef  test    eax, eax
0x18000e5f1  jz      short loc_18000E601
0x18000e5f3  movzx   edi, si
0x18000e5f6  or      edi, 80070000h
0x18000e5fc  test    esi, esi
0x18000e5fe  cmovle  edi, esi
0x18000e601  mov     r9d, 0E0h; unsigned int
0x18000e607  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e60e  mov     ecx, edi; int
0x18000e610  mov     rsi, rbx
0x18000e613  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000e618  test    eax, eax
0x18000e61a  js      short loc_18000E625
0x18000e61c  mov     [r14], rbx
0x18000e61f  mov     rsi, r15
0x18000e622  mov     rbx, r15
0x18000e625  test    rsi, rsi
0x18000e628  jz      short loc_18000E63A
0x18000e62a  mov     rdx, [rbx]
0x18000e62d  mov     rcx, rbx
0x18000e630  mov     rax, [rdx+10h]
0x18000e634  call    cs:__guard_dispatch_icall_fptr
0x18000e63a  mov     rbx, [rsp+38h+arg_0]
0x18000e63f  mov     eax, edi
0x18000e641  mov     rbp, [rsp+38h+arg_8]
0x18000e646  mov     rsi, [rsp+38h+arg_10]
0x18000e64b  add     rsp, 20h
0x18000e64f  pop     r15
0x18000e651  pop     r14
0x18000e653  pop     rdi
0x18000e654  retn
```
