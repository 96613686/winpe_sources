# StartList::Remove(Accommodation *)

- ea: `0x1400169e8`
- end: `0x140016aad`
- name: `?Remove@StartList@@QEAAJPEAVAccommodation@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(StartList *__hidden this, struct Accommodation *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140017904`

## callees

- `0x140013ad0`
- `0x140013ea0`
- `0x140014d0c`
- `0x140015fb8`
- `0x1400169b8`
- `0x1400169e8`
- `0x140016b24`
- `0x1400170a8`

## pseudocode

```c
__int64 __fastcall StartList::Remove(StartList *this, struct Accommodation *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rdx
  StartList *v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rsi
  __int64 v11; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  result = StartList::LoadSettings(this);
  if ( (int)result >= 0 )
  {
    if ( (unsigned __int8)ATL::operator!=((char *)a2 + 40) )
    {
      v5 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                       &v11,
                       a2);
      v6 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
             this,
             *v5);
      ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
      if ( v6 )
      {
        v7 = v6;
        v8 = this;
LABEL_9:
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAt(
          v8,
          v7);
      }
    }
    else
    {
      v9 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                       &v11,
                       a2);
      v10 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
              (char *)this + 144,
              *v9);
      ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
      if ( v10 )
      {
        v7 = v10;
        v8 = (StartList *)((char *)this + 144);
        goto LABEL_9;
      }
    }
    return StartList::SaveSettings(this);
  }
  return result;
}

```

## disassembly

```asm
0x1400169e8  mov     [rsp+arg_0], rbx
0x1400169ed  mov     [rsp+arg_10], rsi
0x1400169f2  push    rdi
0x1400169f3  sub     rsp, 20h
0x1400169f7  mov     rdi, rdx
0x1400169fa  mov     rbx, rcx
0x1400169fd  test    rdx, rdx
0x140016a00  jnz     short loc_140016A0C
0x140016a02  mov     eax, 80070057h
0x140016a07  jmp     loc_140016A9C
0x140016a0c  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x140016a11  test    eax, eax
0x140016a13  js      loc_140016A9C
0x140016a19  lea     rcx, [rdi+28h]
0x140016a1d  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x140016a22  lea     rcx, [rsp+28h+arg_8]
0x140016a27  mov     rdx, rdi
0x140016a2a  test    al, al
0x140016a2c  jz      short loc_140016A5C
0x140016a2e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016a33  mov     rcx, rbx
0x140016a36  mov     rdx, [rax]
0x140016a39  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x140016a3e  mov     rcx, [rsp+28h+arg_8]
0x140016a43  mov     rdi, rax
0x140016a46  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140016a4a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140016a4f  test    rdi, rdi
0x140016a52  jz      short loc_140016A94
0x140016a54  mov     rdx, rdi
0x140016a57  mov     rcx, rbx
0x140016a5a  jmp     short loc_140016A8F
0x140016a5c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016a61  lea     rdi, [rbx+90h]
0x140016a68  mov     rcx, rdi
0x140016a6b  mov     rdx, [rax]
0x140016a6e  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x140016a73  mov     rcx, [rsp+28h+arg_8]
0x140016a78  mov     rsi, rax
0x140016a7b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140016a7f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140016a84  test    rsi, rsi
0x140016a87  jz      short loc_140016A94
0x140016a89  mov     rdx, rsi
0x140016a8c  mov     rcx, rdi
0x140016a8f  call    ?RemoveAt@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAt(__POSITION *)
0x140016a94  mov     rcx, rbx; this
0x140016a97  call    ?SaveSettings@StartList@@AEAAJXZ; StartList::SaveSettings(void)
0x140016a9c  mov     rbx, [rsp+28h+arg_0]
0x140016aa1  mov     rsi, [rsp+28h+arg_10]
0x140016aa6  add     rsp, 20h
0x140016aaa  pop     rdi
0x140016aab  retn
```
