# StartList::Add(Accommodation *)

- ea: `0x140013ec4`
- end: `0x140013fa1`
- name: `?Add@StartList@@QEAAJPEAVAccommodation@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(StartList *__hidden this, struct Accommodation *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400172b0`
- `0x14001cfa0`

## callees

- `0x140013ad0`
- `0x140013ea0`
- `0x140013ec4`
- `0x140013fa8`
- `0x140014d0c`
- `0x140015fb8`
- `0x1400169b8`
- `0x1400170a8`

## pseudocode

```c
__int64 __fastcall StartList::Add(StartList *this, struct Accommodation *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  __int64 v6; // rbx
  _QWORD *v7; // rax
  StartList *v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rbx
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF

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
      if ( !v6 )
      {
        v7 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                         &v11,
                         a2);
        v8 = this;
LABEL_9:
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          v8,
          *v7);
        ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
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
      if ( !v10 )
      {
        v7 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                         &v11,
                         a2);
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
0x140013ec4  push    rbx
0x140013ec6  push    rbp
0x140013ec7  push    rsi
0x140013ec8  push    rdi
0x140013ec9  sub     rsp, 28h
0x140013ecd  mov     rdi, rdx
0x140013ed0  mov     rsi, rcx
0x140013ed3  test    rdx, rdx
0x140013ed6  jnz     short loc_140013EE2
0x140013ed8  mov     eax, 80070057h
0x140013edd  jmp     loc_140013F97
0x140013ee2  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x140013ee7  test    eax, eax
0x140013ee9  js      loc_140013F97
0x140013eef  lea     rcx, [rdi+28h]
0x140013ef3  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x140013ef8  lea     rcx, [rsp+48h+arg_8]
0x140013efd  mov     rdx, rdi
0x140013f00  test    al, al
0x140013f02  jz      short loc_140013F3C
0x140013f04  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140013f09  mov     rcx, rsi
0x140013f0c  mov     rdx, [rax]
0x140013f0f  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x140013f14  mov     rcx, [rsp+48h+arg_8]
0x140013f19  mov     rbx, rax
0x140013f1c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140013f20  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140013f25  test    rbx, rbx
0x140013f28  jnz     short loc_140013F8F
0x140013f2a  mov     rdx, rdi
0x140013f2d  lea     rcx, [rsp+48h+arg_8]
0x140013f32  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140013f37  mov     rcx, rsi
0x140013f3a  jmp     short loc_140013F79
0x140013f3c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140013f41  lea     rbp, [rsi+90h]
0x140013f48  mov     rcx, rbp
0x140013f4b  mov     rdx, [rax]
0x140013f4e  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x140013f53  mov     rcx, [rsp+48h+arg_8]
0x140013f58  mov     rbx, rax
0x140013f5b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140013f5f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140013f64  test    rbx, rbx
0x140013f67  jnz     short loc_140013F8F
0x140013f69  mov     rdx, rdi
0x140013f6c  lea     rcx, [rsp+48h+arg_8]
0x140013f71  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140013f76  mov     rcx, rbp
0x140013f79  mov     rdx, [rax]
0x140013f7c  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x140013f81  mov     rcx, [rsp+48h+arg_8]
0x140013f86  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140013f8a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140013f8f  mov     rcx, rsi; this
0x140013f92  call    ?SaveSettings@StartList@@AEAAJXZ; StartList::SaveSettings(void)
0x140013f97  add     rsp, 28h
0x140013f9b  pop     rdi
0x140013f9c  pop     rsi
0x140013f9d  pop     rbp
0x140013f9e  pop     rbx
0x140013f9f  retn
```
