# StartList::GetLogonConfigList(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)

- ea: `0x140014ffc`
- end: `0x1400150ad`
- name: `?GetLogonConfigList@StartList@@SAXAEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14001cfa0`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x14000d75c`
- `0x140013b44`
- `0x140014128`
- `0x140014ffc`
- `0x1400150b4`
- `0x1400169b8`
- `0x140016ab4`

## pseudocode

```c
__int64 __fastcall StartList::GetLogonConfigList(__int64 a1)
{
  unsigned int v2; // edx
  __int64 v4; // [rsp+20h] [rbp-838h] BYREF
  _QWORD v5[3]; // [rsp+28h] [rbp-830h] BYREF
  unsigned __int16 v6[1024]; // [rsp+40h] [rbp-818h] BYREF

  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(a1);
  memset(v5, 0, sizeof(v5));
  memset_0(v6, 0, sizeof(v6));
  if ( (int)StartList::GetLogonValue(v6, v2, (struct ATL::CRegKey *)v5) >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v4,
      v6);
    StartList::BuildConfigList((__int64)&v4, a1);
    ATL::CStringData::Release((ATL::CStringData *)(v4 - 24));
  }
  return ATL::CRegKey::Close((ATL::CRegKey *)v5);
}

```

## disassembly

```asm
0x140014ffc  push    rbx
0x140014ffe  sub     rsp, 850h
0x140015005  mov     rax, cs:__security_cookie
0x14001500c  xor     rax, rsp
0x14001500f  mov     [rsp+858h+var_18], rax
0x140015017  mov     rbx, rcx
0x14001501a  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x14001501f  xor     edx, edx; Val
0x140015021  mov     [rsp+858h+var_830], 0
0x14001502a  mov     r8d, 800h; Size
0x140015030  mov     [rsp+858h+var_828], 0
0x140015039  lea     rcx, [rsp+858h+var_818]; void *
0x14001503e  mov     [rsp+858h+var_820], 0
0x140015047  call    memset_0
0x14001504c  lea     r8, [rsp+858h+var_830]; struct ATL::CRegKey *
0x140015051  lea     rcx, [rsp+858h+var_818]; unsigned __int16 *
0x140015056  call    ?GetLogonValue@StartList@@CAJPEAGIAEAVCRegKey@ATL@@@Z; StartList::GetLogonValue(ushort *,uint,ATL::CRegKey &)
0x14001505b  test    eax, eax
0x14001505d  js      short loc_140015089
0x14001505f  lea     rdx, [rsp+858h+var_818]
0x140015064  lea     rcx, [rsp+858h+var_838]
0x140015069  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001506e  mov     rdx, rbx
0x140015071  lea     rcx, [rsp+858h+var_838]
0x140015076  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x14001507b  mov     rcx, [rsp+858h+var_838]
0x140015080  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140015084  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140015089  lea     rcx, [rsp+858h+var_830]; this
0x14001508e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140015093  mov     rcx, [rsp+858h+var_18]
0x14001509b  xor     rcx, rsp; StackCookie
0x14001509e  call    __security_check_cookie
0x1400150a3  add     rsp, 850h
0x1400150aa  pop     rbx
0x1400150ab  retn
```
