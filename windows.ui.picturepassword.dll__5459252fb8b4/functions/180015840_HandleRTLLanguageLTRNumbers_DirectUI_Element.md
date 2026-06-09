# _HandleRTLLanguageLTRNumbers(DirectUI::Element *)

- ea: `0x180015840`
- end: `0x1800158e5`
- name: `?_HandleRTLLanguageLTRNumbers@@YAXPEAVElement@DirectUI@@@Z`
- size: `165`
- prototype: `void __fastcall(struct DirectUI::Element *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015480`

## callees

- `0x180010d04`
- `0x180015840`
- `0x180018c1c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015886`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015886`
- `DUI70!?GetLayout@Element@DirectUI@@QEAAPEAVLayout@2@PEAPEAVValue@2@@Z` at `0x1800158ad`
- `DUI70!?GetLayout@Element@DirectUI@@QEAAPEAVLayout@2@PEAPEAVValue@2@@Z` at `0x1800158ad`
- `DUI70!?SetDirection@Element@DirectUI@@QEAAJH@Z` at `0x180015896`
- `DUI70!?SetDirection@Element@DirectUI@@QEAAJH@Z` at `0x180015896`
- `DUI70!?Initialize@FlowLayout@DirectUI@@QEAAX_NIII@Z` at `0x1800158cf`
- `DUI70!?Initialize@FlowLayout@DirectUI@@QEAAX_NIII@Z` at `0x1800158cf`

## pseudocode

```c
void __fastcall _HandleRTLLanguageLTRNumbers(struct DirectUI::Element *a1, __int64 a2, __int64 a3)
{
  DirectUI::FlowLayout *Layout; // rax
  WCHAR String1; // [rsp+48h] [rbp+10h] BYREF
  struct DirectUI::Value *v6; // [rsp+50h] [rbp+18h] BYREF

  if ( (int)ResourceStringCopyEx(&_ImageBase, 17535, a3, &String1, 2) >= 0
    && CompareStringOrdinal(&String1, -1, L"1", -1, 0) == 2 )
  {
    DirectUI::Element::SetDirection(a1, 0);
    v6 = 0;
    Layout = DirectUI::Element::GetLayout(a1, &v6);
    if ( Layout )
      DirectUI::FlowLayout::Initialize(Layout, 1, 0, 1u, 2u);
    CValuePtr::Release((CValuePtr *)&v6);
  }
}

```

## disassembly

```asm
0x180015840  push    rbx
0x180015842  sub     rsp, 30h
0x180015846  mov     rbx, rcx
0x180015849  mov     qword ptr [rsp+38h+bIgnoreCase], 2
0x180015852  lea     rcx, __ImageBase
0x180015859  mov     edx, 447Fh
0x18001585e  lea     r9, [rsp+38h+String1]
0x180015863  call    _ResourceStringCopyEx
0x180015868  test    eax, eax
0x18001586a  js      short loc_1800158DF
0x18001586c  or      edx, 0FFFFFFFFh; cchCount1
0x18001586f  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x180015877  mov     r9d, edx; cchCount2
0x18001587a  lea     r8, String2; "1"
0x180015881  lea     rcx, [rsp+38h+String1]; lpString1
0x180015886  call    cs:__imp_CompareStringOrdinal
0x18001588c  cmp     eax, 2
0x18001588f  jnz     short loc_1800158DF
0x180015891  xor     edx, edx
0x180015893  mov     rcx, rbx
0x180015896  call    cs:__imp_?SetDirection@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetDirection(int)
0x18001589c  lea     rdx, [rsp+38h+arg_10]
0x1800158a1  mov     [rsp+38h+arg_10], 0
0x1800158aa  mov     rcx, rbx
0x1800158ad  call    cs:__imp_?GetLayout@Element@DirectUI@@QEAAPEAVLayout@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetLayout(DirectUI::Value * *)
0x1800158b3  test    rax, rax
0x1800158b6  jz      short loc_1800158D5
0x1800158b8  mov     r9d, 1
0x1800158be  mov     [rsp+38h+bIgnoreCase], 2
0x1800158c6  mov     dl, r9b
0x1800158c9  xor     r8d, r8d
0x1800158cc  mov     rcx, rax
0x1800158cf  call    cs:__imp_?Initialize@FlowLayout@DirectUI@@QEAAX_NIII@Z; DirectUI::FlowLayout::Initialize(bool,uint,uint,uint)
0x1800158d5  lea     rcx, [rsp+38h+arg_10]; this
0x1800158da  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800158df  add     rsp, 30h
0x1800158e3  pop     rbx
0x1800158e4  retn
```
