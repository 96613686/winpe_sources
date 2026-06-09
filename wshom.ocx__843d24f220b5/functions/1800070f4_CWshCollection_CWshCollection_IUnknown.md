# CWshCollection::CWshCollection(IUnknown *)

- ea: `0x1800070f4`
- end: `0x180007177`
- name: `??0CWshCollection@@QEAA@PEAUIUnknown@@@Z`
- size: `131`
- prototype: `CWshCollection *__fastcall(CWshCollection *__hidden this, struct IUnknown *)`
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180007f90`
- `0x180008080`
- `0x18000ca00`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180007168`
- `OLEAUT32!__imp_VariantInit` at `0x180007168`

## pseudocode

```c
CWshCollection *__fastcall CWshCollection::CWshCollection(CWshCollection *this, struct IUnknown *a2)
{
  *((_QWORD *)this + 1) = &CUnknown::`vftable';
  *((_DWORD *)this + 10) = 1;
  *((_QWORD *)this + 4) = &CUnknown::InnerUnknown::`vftable';
  *((_QWORD *)this + 2) = (char *)this + 32;
  *((_QWORD *)this + 3) = this;
  _InterlockedIncrement(&Global::g_cObjects);
  *((_QWORD *)this + 6) = &TaUser_DescCWshCollection;
  *((_BYTE *)this + 56) = 0;
  *(_QWORD *)this = &CWshCollection::`vftable'{for `IWshCollection'};
  *((_QWORD *)this + 1) = &CWshCollection::`vftable'{for `CDispatch'};
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 8) = &CWshCollection::`vftable'{for `IProvideClassInfo'};
  VariantInit((VARIANTARG *)this + 4);
  return this;
}

```

## disassembly

```asm
0x1800070f4  push    rbx
0x1800070f6  sub     rsp, 20h
0x1800070fa  mov     rbx, rcx
0x1800070fd  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x180007104  mov     [rcx+8], rax
0x180007108  lea     rax, [rcx+20h]
0x18000710c  mov     dword ptr [rax+8], 1
0x180007113  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x18000711a  mov     [rax], rcx
0x18000711d  mov     [rbx+10h], rax
0x180007121  mov     [rbx+18h], rbx
0x180007125  lock inc cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x18000712c  xor     ecx, ecx
0x18000712e  lea     rax, ?TaUser_DescCWshCollection@@3UTaDescDispatch@@A; TaDescDispatch TaUser_DescCWshCollection
0x180007135  mov     [rbx+30h], rax
0x180007139  lea     rax, ??_7CWshCollection@@6BIWshCollection@@@; const CWshCollection::`vftable'{for `IWshCollection'}
0x180007140  mov     [rbx+38h], cl
0x180007143  mov     [rbx], rax
0x180007146  lea     rax, ??_7CWshCollection@@6BCDispatch@@@; const CWshCollection::`vftable'{for `CDispatch'}
0x18000714d  mov     [rbx+8], rax
0x180007151  lea     rax, ??_7CWshCollection@@6BIProvideClassInfo@@@; const CWshCollection::`vftable'{for `IProvideClassInfo'}
0x180007158  mov     [rbx+48h], rcx
0x18000715c  mov     [rbx+50h], rcx
0x180007160  lea     rcx, [rbx+60h]; pvarg
0x180007164  mov     [rbx+40h], rax
0x180007168  call    cs:__imp_VariantInit
0x18000716e  mov     rax, rbx
0x180007171  add     rsp, 20h
0x180007175  pop     rbx
0x180007176  retn
```
