# CWdsComMetadata::CreateInstance(CWdsMetadata const *,ATL::CComObject<CWdsComMetadata> * *)

- ea: `0x18000e194`
- end: `0x18000e2e5`
- name: `?CreateInstance@CWdsComMetadata@@SAJPEBVCWdsMetadata@@PEAPEAV?$CComObject@VCWdsComMetadata@@@ATL@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(struct CWdsMetadata *)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800042f4`
- `0x180005430`
- `0x180005818`
- `0x1800063b4`

## callees

- `0x180001cd0`
- `0x18000b834`
- `0x18000e194`
- `0x18000e458`
- `0x180014d58`
- `0x180014ee0`
- `0x180015068`
- `0x180015cc0`

## string_xrefs

- `0x18000e235`: `base\eco\wds\lib\metadata\com\wdscommetadata.cpp`
- `0x18000e297`: `base\eco\wds\lib\metadata\com\wdscommetadata.cpp`
- `0x18000e26f`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadata::CreateInstance(struct CWdsMetadata *a1, CWdsComMetadataBuilder **a2)
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
    *(_QWORD *)v7 = &ATL::CComObject<CWdsComMetadata>::`vftable';
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
  if ( (int)ElValidateHr(v4, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadata.cpp", 0x66u) >= 0 )
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
    if ( (int)ElValidateHr(v4, v12, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadata.cpp", 0x6Bu) >= 0 )
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
0x18000e194  mov     [rsp+arg_0], rbx
0x18000e199  mov     [rsp+arg_8], rbp
0x18000e19e  mov     [rsp+arg_10], rsi
0x18000e1a3  push    rdi
0x18000e1a4  push    r14
0x18000e1a6  push    r15
0x18000e1a8  sub     rsp, 20h
0x18000e1ac  mov     rbp, rcx
0x18000e1af  mov     r14, rdx
0x18000e1b2  mov     ecx, 0B0h; Size
0x18000e1b7  mov     edi, 8007000Eh
0x18000e1bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e1c1  xor     r15d, r15d
0x18000e1c4  mov     rbx, rax
0x18000e1c7  test    rax, rax
0x18000e1ca  jz      short loc_18000E1EB
0x18000e1cc  mov     rcx, rax; this
0x18000e1cf  call    ??0CWdsComMetadataBuilder@@QEAA@XZ; CWdsComMetadataBuilder::CWdsComMetadataBuilder(void)
0x18000e1d4  lea     rax, ??_7?$CComObject@VCWdsComMetadata@@@ATL@@6B@; const ATL::CComObject<CWdsComMetadata>::`vftable'
0x18000e1db  mov     [rbx], rax
0x18000e1de  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e1e5  lock inc dword ptr [rax+0Ch]
0x18000e1e9  jmp     short loc_18000E1EE
0x18000e1eb  mov     rbx, r15
0x18000e1ee  test    rbx, rbx
0x18000e1f1  jz      short loc_18000E22F
0x18000e1f3  lea     rcx, [rbx+10h]; this
0x18000e1f7  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000e1fc  test    eax, eax
0x18000e1fe  js      short loc_18000E204
0x18000e200  mov     byte ptr [rbx+38h], 1
0x18000e204  cmovns  eax, r15d
0x18000e208  mov     edi, r15d
0x18000e20b  test    eax, eax
0x18000e20d  cmovs   edi, eax
0x18000e210  test    edi, edi
0x18000e212  jz      short loc_18000E22F
0x18000e214  mov     rax, [rbx]
0x18000e217  mov     edx, 1
0x18000e21c  mov     rcx, rbx
0x18000e21f  mov     rax, [rax+158h]
0x18000e226  call    cs:__guard_dispatch_icall_fptr
0x18000e22c  mov     rbx, r15
0x18000e22f  mov     r9d, 66h ; 'f'; unsigned int
0x18000e235  lea     r8, aBaseEcoWdsLibM_6; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e23c  mov     ecx, edi; int
0x18000e23e  mov     rsi, rbx
0x18000e241  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000e246  test    eax, eax
0x18000e248  js      short loc_18000E2B5
0x18000e24a  mov     rax, [rbx]
0x18000e24d  mov     rcx, rbx
0x18000e250  mov     rax, [rax+8]
0x18000e254  call    cs:__guard_dispatch_icall_fptr
0x18000e25a  lea     rcx, [rbx+40h]; this
0x18000e25e  mov     rdx, rbp; struct CWdsMetadata *
0x18000e261  mov     edi, r15d
0x18000e264  call    ?AppendAll@CWdsMetadata@@QEAAKPEBV1@@Z; CWdsMetadata::AppendAll(CWdsMetadata const *)
0x18000e269  mov     r9d, 9Eh; unsigned int
0x18000e26f  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e276  mov     ecx, eax; unsigned int
0x18000e278  mov     esi, eax
0x18000e27a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e27f  test    eax, eax
0x18000e281  jz      short loc_18000E291
0x18000e283  movzx   edi, si
0x18000e286  or      edi, 80070000h
0x18000e28c  test    esi, esi
0x18000e28e  cmovle  edi, esi
0x18000e291  mov     r9d, 6Bh ; 'k'; unsigned int
0x18000e297  lea     r8, aBaseEcoWdsLibM_6; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e29e  mov     ecx, edi; int
0x18000e2a0  mov     rsi, rbx
0x18000e2a3  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000e2a8  test    eax, eax
0x18000e2aa  js      short loc_18000E2B5
0x18000e2ac  mov     [r14], rbx
0x18000e2af  mov     rsi, r15
0x18000e2b2  mov     rbx, r15
0x18000e2b5  test    rsi, rsi
0x18000e2b8  jz      short loc_18000E2CA
0x18000e2ba  mov     rdx, [rbx]
0x18000e2bd  mov     rcx, rbx
0x18000e2c0  mov     rax, [rdx+10h]
0x18000e2c4  call    cs:__guard_dispatch_icall_fptr
0x18000e2ca  mov     rbx, [rsp+38h+arg_0]
0x18000e2cf  mov     eax, edi
0x18000e2d1  mov     rbp, [rsp+38h+arg_8]
0x18000e2d6  mov     rsi, [rsp+38h+arg_10]
0x18000e2db  add     rsp, 20h
0x18000e2df  pop     r15
0x18000e2e1  pop     r14
0x18000e2e3  pop     rdi
0x18000e2e4  retn
```
