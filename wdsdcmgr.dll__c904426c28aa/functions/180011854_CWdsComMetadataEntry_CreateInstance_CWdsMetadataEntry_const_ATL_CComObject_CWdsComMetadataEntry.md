# CWdsComMetadataEntry::CreateInstance(CWdsMetadataEntry const *,ATL::CComObject<CWdsComMetadataEntry> * *)

- ea: `0x180011854`
- end: `0x1800119a9`
- name: `?CreateInstance@CWdsComMetadataEntry@@SAJPEBVCWdsMetadataEntry@@PEAPEAV?$CComObject@VCWdsComMetadataEntry@@@ATL@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(struct CWdsMetadataEntry *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e750`
- `0x18000e8f0`

## callees

- `0x180001cd0`
- `0x18001170c`
- `0x180011854`
- `0x180014ee0`
- `0x180015068`
- `0x180015c9d`
- `0x180015cc0`

## string_xrefs

- `0x180011926`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x18001195c`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::CreateInstance(struct CWdsMetadataEntry *a1, CWdsComMetadataEntry **a2)
{
  unsigned int v4; // esi
  char *v5; // rax
  const char *v6; // rdx
  CWdsComMetadataEntry *v7; // rdi
  int v8; // eax
  CWdsComMetadataEntry *v9; // rbx
  const char *v10; // rdx

  v4 = -2147024882;
  v5 = (char *)operator new(0x80u);
  v7 = (CWdsComMetadataEntry *)v5;
  if ( v5 )
  {
    *((_DWORD *)v5 + 2) = 0;
    memset_0(v5 + 16, 0, 0x28u);
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)((char *)v7 + 100) = 0;
    *((_QWORD *)v7 + 14) = 0;
    *((_QWORD *)v7 + 15) = 0;
    *((_QWORD *)v7 + 8) = 0;
    *((_QWORD *)v7 + 9) = 0;
    *((_QWORD *)v7 + 10) = 0;
    *((_QWORD *)v7 + 11) = 0;
    *((_DWORD *)v7 + 24) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CWdsComMetadataEntry>::`vftable';
    _InterlockedIncrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  }
  else
  {
    v7 = 0;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((CWdsComMetadataEntry *)((char *)v7 + 16));
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
      (*(void (__fastcall **)(CWdsComMetadataEntry *, __int64))(*(_QWORD *)v7 + 128LL))(v7, 1);
      v7 = 0;
    }
  }
  v9 = v7;
  if ( (int)ElValidateHr(v4, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x9Eu) >= 0 )
  {
    (*(void (__fastcall **)(CWdsComMetadataEntry *))(*(_QWORD *)v7 + 8LL))(v7);
    v4 = CWdsComMetadataEntry::Initialize(v7, a1);
    if ( (int)ElValidateHr(v4, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0xA3u) >= 0 )
    {
      *a2 = v7;
      v9 = 0;
      v7 = 0;
    }
  }
  if ( v9 )
    (*(void (__fastcall **)(CWdsComMetadataEntry *))(*(_QWORD *)v7 + 16LL))(v7);
  return v4;
}

```

## disassembly

```asm
0x180011854  mov     [rsp+arg_0], rbx
0x180011859  mov     [rsp+arg_8], rbp
0x18001185e  mov     [rsp+arg_10], rsi
0x180011863  push    rdi
0x180011864  push    r14
0x180011866  push    r15
0x180011868  sub     rsp, 20h
0x18001186c  mov     rbp, rcx
0x18001186f  mov     r14, rdx
0x180011872  mov     ecx, 80h; Size
0x180011877  mov     esi, 8007000Eh
0x18001187c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011881  xor     r15d, r15d
0x180011884  mov     rdi, rax
0x180011887  test    rax, rax
0x18001188a  jz      short loc_1800118DC
0x18001188c  xor     edx, edx; Val
0x18001188e  mov     [rax+8], r15d
0x180011892  lea     r8d, [r15+28h]; Size
0x180011896  lea     rcx, [rax+10h]; void *
0x18001189a  call    memset_0
0x18001189f  mov     [rdi+38h], r15b
0x1800118a3  xor     eax, eax
0x1800118a5  mov     [rdi+64h], r15
0x1800118a9  mov     [rdi+70h], rax
0x1800118ad  mov     [rdi+78h], rax
0x1800118b1  lea     rax, ??_7?$CComObject@VCWdsComMetadataEntry@@@ATL@@6B@; const ATL::CComObject<CWdsComMetadataEntry>::`vftable'
0x1800118b8  mov     [rdi+40h], r15
0x1800118bc  mov     [rdi+48h], r15
0x1800118c0  mov     [rdi+50h], r15
0x1800118c4  mov     [rdi+58h], r15
0x1800118c8  mov     [rdi+60h], r15d
0x1800118cc  mov     [rdi], rax
0x1800118cf  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800118d6  lock inc dword ptr [rax+0Ch]
0x1800118da  jmp     short loc_1800118DF
0x1800118dc  mov     rdi, r15
0x1800118df  test    rdi, rdi
0x1800118e2  jz      short loc_180011920
0x1800118e4  lea     rcx, [rdi+10h]; this
0x1800118e8  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800118ed  test    eax, eax
0x1800118ef  js      short loc_1800118F5
0x1800118f1  mov     byte ptr [rdi+38h], 1
0x1800118f5  cmovns  eax, r15d
0x1800118f9  mov     esi, r15d
0x1800118fc  test    eax, eax
0x1800118fe  cmovs   esi, eax
0x180011901  test    esi, esi
0x180011903  jz      short loc_180011920
0x180011905  mov     rax, [rdi]
0x180011908  mov     edx, 1
0x18001190d  mov     rcx, rdi
0x180011910  mov     rax, [rax+80h]
0x180011917  call    cs:__guard_dispatch_icall_fptr
0x18001191d  mov     rdi, r15
0x180011920  mov     r9d, 9Eh; unsigned int
0x180011926  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001192d  mov     ecx, esi; int
0x18001192f  mov     rbx, rdi
0x180011932  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011937  test    eax, eax
0x180011939  js      short loc_180011979
0x18001193b  mov     rax, [rdi]
0x18001193e  mov     rcx, rdi
0x180011941  mov     rax, [rax+8]
0x180011945  call    cs:__guard_dispatch_icall_fptr
0x18001194b  mov     rdx, rbp; struct CWdsMetadataEntry *
0x18001194e  mov     rcx, rdi; this
0x180011951  call    ?Initialize@CWdsComMetadataEntry@@AEAAJPEBVCWdsMetadataEntry@@@Z; CWdsComMetadataEntry::Initialize(CWdsMetadataEntry const *)
0x180011956  mov     r9d, 0A3h; unsigned int
0x18001195c  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011963  mov     ecx, eax; int
0x180011965  mov     esi, eax
0x180011967  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18001196c  test    eax, eax
0x18001196e  js      short loc_180011979
0x180011970  mov     [r14], rdi
0x180011973  mov     rbx, r15
0x180011976  mov     rdi, r15
0x180011979  test    rbx, rbx
0x18001197c  jz      short loc_18001198E
0x18001197e  mov     rax, [rdi]
0x180011981  mov     rcx, rdi
0x180011984  mov     rax, [rax+10h]
0x180011988  call    cs:__guard_dispatch_icall_fptr
0x18001198e  mov     rbx, [rsp+38h+arg_0]
0x180011993  mov     eax, esi
0x180011995  mov     rsi, [rsp+38h+arg_10]
0x18001199a  mov     rbp, [rsp+38h+arg_8]
0x18001199f  add     rsp, 20h
0x1800119a3  pop     r15
0x1800119a5  pop     r14
0x1800119a7  pop     rdi
0x1800119a8  retn
```
