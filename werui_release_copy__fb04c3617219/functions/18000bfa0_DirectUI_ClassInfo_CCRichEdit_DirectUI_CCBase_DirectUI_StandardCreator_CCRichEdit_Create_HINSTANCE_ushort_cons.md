# DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>> * *)

- ea: `0x18000bfa0`
- end: `0x18000c037`
- name: `?Create@?$ClassInfo@VCCRichEdit@@VCCBase@DirectUI@@V?$StandardCreator@VCCRichEdit@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c70c`

## callees

- `0x18000be54`
- `0x18000bfa0`
- `0x18000c110`

## import_xrefs

- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x18000c005`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x18000c005`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x18000bfd0`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x18000bfd0`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>::Create(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        DirectUI::ClassInfoBase **a6)
{
  DirectUI::ClassInfoBase *v6; // rax
  DirectUI::ClassInfoBase *v7; // rbx
  int v8; // edi

  *a6 = 0;
  v6 = (DirectUI::ClassInfoBase *)DirectUI::HAllocAndZero((DirectUI *)0x10, a2);
  v7 = v6;
  if ( v6 )
  {
    DirectUI::ClassInfoBase::ClassInfoBase(v6);
    *(_QWORD *)v7 = &DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(v7, &_ImageBase, L"CCRichEdit", 0, 0, 0);
    if ( v8 < 0 )
      DirectUI::HDelete<DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>>(v7);
    else
      *a6 = v7;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000bfa0  mov     [rsp+arg_0], rbx
0x18000bfa5  mov     [rsp+arg_8], rsi
0x18000bfaa  push    rdi
0x18000bfab  sub     rsp, 30h
0x18000bfaf  mov     rsi, [rsp+38h+arg_28]
0x18000bfb4  mov     ecx, 10h; this
0x18000bfb9  mov     qword ptr [rsi], 0
0x18000bfc0  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000bfc5  mov     rbx, rax
0x18000bfc8  test    rax, rax
0x18000bfcb  jz      short loc_18000C020
0x18000bfcd  mov     rcx, rax
0x18000bfd0  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x18000bfd6  lea     rax, ??_7?$ClassInfo@VCCRichEdit@@VCCBase@DirectUI@@V?$StandardCreator@VCCRichEdit@@@3@@DirectUI@@6B@; const DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>::`vftable'
0x18000bfdd  mov     [rsp+38h+var_10], 0
0x18000bfe5  xor     r9d, r9d
0x18000bfe8  mov     [rbx], rax
0x18000bfeb  lea     r8, aCcrichedit; "CCRichEdit"
0x18000bff2  mov     [rsp+38h+var_18], 0
0x18000bffb  lea     rdx, __ImageBase
0x18000c002  mov     rcx, rbx
0x18000c005  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x18000c00b  mov     edi, eax
0x18000c00d  test    eax, eax
0x18000c00f  js      short loc_18000C016
0x18000c011  mov     [rsi], rbx
0x18000c014  jmp     short loc_18000C025
0x18000c016  mov     rcx, rbx
0x18000c019  call    ??$HDelete@V?$ClassInfo@VCCRichEdit@@VCCBase@DirectUI@@V?$StandardCreator@VCCRichEdit@@@3@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCCRichEdit@@VCCBase@DirectUI@@V?$StandardCreator@VCCRichEdit@@@3@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>>(DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>> *)
0x18000c01e  jmp     short loc_18000C025
0x18000c020  mov     edi, 8007000Eh
0x18000c025  mov     rbx, [rsp+38h+arg_0]
0x18000c02a  mov     eax, edi
0x18000c02c  mov     rsi, [rsp+38h+arg_8]
0x18000c031  add     rsp, 30h
0x18000c035  pop     rdi
0x18000c036  retn
```
