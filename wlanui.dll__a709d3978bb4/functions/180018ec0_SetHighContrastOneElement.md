# SetHighContrastOneElement

- ea: `0x180018ec0`
- end: `0x1800190b7`
- name: `SetHighContrastOneElement`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800199f8`

## callees

- `0x180018ec0`
- `0x18001bf16`

## import_xrefs

- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180018fc3`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18001903e`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180019099`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180018fc3`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18001903e`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180019099`
- `DUI70!StrToID` at `0x180018f68`
- `DUI70!StrToID` at `0x180018f81`
- `DUI70!StrToID` at `0x180018f9a`
- `DUI70!StrToID` at `0x180019052`
- `DUI70!StrToID` at `0x18001906b`
- `DUI70!StrToID` at `0x180019084`
- `DUI70!StrToID` at `0x180018f68`
- `DUI70!StrToID` at `0x180018f81`
- `DUI70!StrToID` at `0x180018f9a`
- `DUI70!StrToID` at `0x180019052`
- `DUI70!StrToID` at `0x18001906b`
- `DUI70!StrToID` at `0x180019084`
- `DUI70!?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x180018f54`
- `DUI70!?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x180018fb1`
- `DUI70!?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x180018f54`
- `DUI70!?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x180018fb1`
- `DUI70!?SetForegroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x180018edb`
- `DUI70!?SetForegroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x180018edb`
- `DUI70!?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180018ef2`
- `DUI70!?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180018fda`
- `DUI70!?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180018ef2`
- `DUI70!?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180018fda`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800190a4`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800190a4`
- `DUI70!?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180019034`
- `DUI70!?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18001908f`
- `DUI70!?ForegroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180018fbc`

## string_xrefs

- `0x180018f13`: `SecurityCommandLink`
- `0x180018ffb`: `SecurityCommandLink`
- `0x180018f26`: `CommandButton`
- `0x18001900e`: `CommandButton`

## pseudocode

```c
__int64 __fastcall SetHighContrastOneElement(DirectUI::Element *a1, __int64 a2)
{
  const wchar_t *Class; // rax
  const wchar_t *v4; // rbx
  __int16 v5; // bx
  __int16 v6; // bx
  __int16 v7; // bx
  const wchar_t *v8; // rax
  const wchar_t *v9; // rbx
  __int16 v10; // bx
  __int16 v11; // bx
  __int16 v12; // bx
  struct DirectUI::Value *v14; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    DirectUI::Element::SetForegroundStdColor(a1, 10008);
    v14 = 0;
    Class = DirectUI::Element::GetClass(a1, &v14);
    v4 = Class;
    if ( Class
      && (!wcscmp_0(Class, L"GenericButton")
       || !wcscmp_0(v4, L"SecurityCommandLink")
       || !wcscmp_0(v4, L"CommandButton")
       || !wcscmp_0(v4, L"SubmitButton")) )
    {
      DirectUI::Element::SetBackgroundStdColor(a1, 10005);
    }
    v5 = *((_WORD *)a1 + 72);
    if ( v5 == (unsigned __int16)StrToID(L"Thumb")
      || (v6 = *((_WORD *)a1 + 72), v6 == (unsigned __int16)StrToID(L"LineUp"))
      || (v7 = *((_WORD *)a1 + 72), v7 == (unsigned __int16)StrToID(L"LineDown")) )
    {
      DirectUI::Element::SetBackgroundStdColor(a1, 10008);
    }
  }
  else
  {
    DirectUI::Element::RemoveLocalValue(
      a1,
      (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ForegroundProp);
    v14 = 0;
    v8 = DirectUI::Element::GetClass(a1, &v14);
    v9 = v8;
    if ( v8
      && (!wcscmp_0(v8, L"GenericButton")
       || !wcscmp_0(v9, L"SecurityCommandLink")
       || !wcscmp_0(v9, L"CommandButton")
       || !wcscmp_0(v9, L"SubmitButton")) )
    {
      DirectUI::Element::RemoveLocalValue(
        a1,
        (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::BackgroundProp);
    }
    v10 = *((_WORD *)a1 + 72);
    if ( v10 == (unsigned __int16)StrToID(L"Thumb")
      || (v11 = *((_WORD *)a1 + 72), v11 == (unsigned __int16)StrToID(L"LineUp"))
      || (v12 = *((_WORD *)a1 + 72), v12 == (unsigned __int16)StrToID(L"LineDown")) )
    {
      DirectUI::Element::RemoveLocalValue(
        a1,
        (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::BackgroundProp);
    }
  }
  DirectUI::Value::Release(v14);
  return 0;
}

```

## disassembly

```asm
0x180018ec0  mov     [rsp+arg_0], rbx
0x180018ec5  push    rdi
0x180018ec6  sub     rsp, 20h
0x180018eca  mov     rdi, rcx
0x180018ecd  test    rdx, rdx
0x180018ed0  jz      loc_180018FBC
0x180018ed6  mov     edx, 2718h
0x180018edb  call    cs:__imp_?SetForegroundStdColor@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetForegroundStdColor(int)
0x180018ee1  lea     rdx, [rsp+28h+arg_8]
0x180018ee6  mov     [rsp+28h+arg_8], 0
0x180018eef  mov     rcx, rdi
0x180018ef2  call    cs:__imp_?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetClass(DirectUI::Value * *)
0x180018ef8  mov     rbx, rax
0x180018efb  test    rax, rax
0x180018efe  jz      short loc_180018F5A
0x180018f00  lea     rdx, aGenericbutton; "GenericButton"
0x180018f07  mov     rcx, rax; String1
0x180018f0a  call    wcscmp_0
0x180018f0f  test    eax, eax
0x180018f11  jz      short loc_180018F4C
0x180018f13  lea     rdx, aSecuritycomman; "SecurityCommandLink"
0x180018f1a  mov     rcx, rbx; String1
0x180018f1d  call    wcscmp_0
0x180018f22  test    eax, eax
0x180018f24  jz      short loc_180018F4C
0x180018f26  lea     rdx, aCommandbutton; "CommandButton"
0x180018f2d  mov     rcx, rbx; String1
0x180018f30  call    wcscmp_0
0x180018f35  test    eax, eax
0x180018f37  jz      short loc_180018F4C
0x180018f39  lea     rdx, aSubmitbutton; "SubmitButton"
0x180018f40  mov     rcx, rbx; String1
0x180018f43  call    wcscmp_0
0x180018f48  test    eax, eax
0x180018f4a  jnz     short loc_180018F5A
0x180018f4c  mov     edx, 2715h
0x180018f51  mov     rcx, rdi
0x180018f54  call    cs:__imp_?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetBackgroundStdColor(int)
0x180018f5a  movzx   ebx, word ptr [rdi+90h]
0x180018f61  lea     rcx, aThumb; "Thumb"
0x180018f68  call    cs:__imp_StrToID
0x180018f6e  cmp     bx, ax
0x180018f71  jz      short loc_180018FA9
0x180018f73  movzx   ebx, word ptr [rdi+90h]
0x180018f7a  lea     rcx, aLineup; "LineUp"
0x180018f81  call    cs:__imp_StrToID
0x180018f87  cmp     bx, ax
0x180018f8a  jz      short loc_180018FA9
0x180018f8c  movzx   ebx, word ptr [rdi+90h]
0x180018f93  lea     rcx, aLinedown; "LineDown"
0x180018f9a  call    cs:__imp_StrToID
0x180018fa0  cmp     bx, ax
0x180018fa3  jnz     loc_18001909F
0x180018fa9  mov     edx, 2718h
0x180018fae  mov     rcx, rdi
0x180018fb1  call    cs:__imp_?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetBackgroundStdColor(int)
0x180018fb7  jmp     loc_18001909F
0x180018fbc  mov     rdx, cs:__imp_?ForegroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ForegroundProp(void)
0x180018fc3  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x180018fc9  lea     rdx, [rsp+28h+arg_8]
0x180018fce  mov     [rsp+28h+arg_8], 0
0x180018fd7  mov     rcx, rdi
0x180018fda  call    cs:__imp_?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetClass(DirectUI::Value * *)
0x180018fe0  mov     rbx, rax
0x180018fe3  test    rax, rax
0x180018fe6  jz      short loc_180019044
0x180018fe8  lea     rdx, aGenericbutton; "GenericButton"
0x180018fef  mov     rcx, rax; String1
0x180018ff2  call    wcscmp_0
0x180018ff7  test    eax, eax
0x180018ff9  jz      short loc_180019034
0x180018ffb  lea     rdx, aSecuritycomman; "SecurityCommandLink"
0x180019002  mov     rcx, rbx; String1
0x180019005  call    wcscmp_0
0x18001900a  test    eax, eax
0x18001900c  jz      short loc_180019034
0x18001900e  lea     rdx, aCommandbutton; "CommandButton"
0x180019015  mov     rcx, rbx; String1
0x180019018  call    wcscmp_0
0x18001901d  test    eax, eax
0x18001901f  jz      short loc_180019034
0x180019021  lea     rdx, aSubmitbutton; "SubmitButton"
0x180019028  mov     rcx, rbx; String1
0x18001902b  call    wcscmp_0
0x180019030  test    eax, eax
0x180019032  jnz     short loc_180019044
0x180019034  mov     rdx, cs:__imp_?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::BackgroundProp(void)
0x18001903b  mov     rcx, rdi
0x18001903e  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x180019044  movzx   ebx, word ptr [rdi+90h]
0x18001904b  lea     rcx, aThumb; "Thumb"
0x180019052  call    cs:__imp_StrToID
0x180019058  cmp     bx, ax
0x18001905b  jz      short loc_18001908F
0x18001905d  movzx   ebx, word ptr [rdi+90h]
0x180019064  lea     rcx, aLineup; "LineUp"
0x18001906b  call    cs:__imp_StrToID
0x180019071  cmp     bx, ax
0x180019074  jz      short loc_18001908F
0x180019076  movzx   ebx, word ptr [rdi+90h]
0x18001907d  lea     rcx, aLinedown; "LineDown"
0x180019084  call    cs:__imp_StrToID
0x18001908a  cmp     bx, ax
0x18001908d  jnz     short loc_18001909F
0x18001908f  mov     rdx, cs:__imp_?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::BackgroundProp(void)
0x180019096  mov     rcx, rdi
0x180019099  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x18001909f  mov     rcx, [rsp+28h+arg_8]
0x1800190a4  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800190aa  mov     rbx, [rsp+28h+arg_0]
0x1800190af  xor     eax, eax
0x1800190b1  add     rsp, 20h
0x1800190b5  pop     rdi
0x1800190b6  retn
```
