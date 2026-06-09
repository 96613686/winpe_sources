# WdcDataPortal::ShowFilterHint(ushort const *)

- ea: `0x180077ac0`
- end: `0x180077bba`
- name: `?ShowFilterHint@WdcDataPortal@@QEAAJPEBG@Z`
- size: `250`
- prototype: `__int64 __fastcall(WdcDataPortal *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800235d8`

## callees

- `0x18000b854`
- `0x180077ac0`

## import_xrefs

- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180077af6`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180077af6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180077b56`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180077b69`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180077b56`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180077b69`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180077b80`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180077b9b`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180077b80`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180077b9b`
- `DUI70!?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z` at `0x180077b2f`
- `DUI70!?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z` at `0x180077b2f`
- `DUI70!?AccDescProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180077b90`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180077b75`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180077b41`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180077b41`

## pseudocode

```c
__int64 __fastcall WdcDataPortal::ShowFilterHint(WdcDataPortal *this, const unsigned __int16 *a2)
{
  DirectUI::Element *v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-18h]

  v4 = (DirectUI::Element *)*((_QWORD *)this + 6);
  if ( !v4 || !*((_QWORD *)this + 7) )
    return (unsigned int)-2147418113;
  if ( a2 )
  {
    v5 = DirectUI::Element::SetContentString(*((DirectUI::Element **)this + 7), a2);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v5 = DirectUI::Element::SetAccDesc(*((DirectUI::Element **)this + 7), a2);
      v6 = v5;
      if ( v5 >= 0 )
      {
        v5 = DirectUI::Element::SetSelected(*((DirectUI::Element **)this + 6), 0);
        v6 = v5;
        if ( v5 >= 0 )
        {
          v5 = DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 6), 1);
          goto LABEL_9;
        }
      }
    }
  }
  else
  {
    v5 = DirectUI::Element::SetLayoutPos(v4, -3);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v5 = DirectUI::Element::RemoveLocalValue(
             *((DirectUI::Element **)this + 7),
             (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp);
      v6 = v5;
      if ( v5 >= 0 )
      {
        v5 = DirectUI::Element::RemoveLocalValue(
               *((DirectUI::Element **)this + 7),
               (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::AccDescProp);
LABEL_9:
        v6 = v5;
        if ( v5 >= 0 )
          return v6;
      }
    }
  }
  v8 = v5;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\portal.cpp",
    "WdcDataPortal::ShowFilterHint",
    0,
    L"FAILURE: 0x%08x",
    v8);
  return v6;
}

```

## disassembly

```asm
0x180077ac0  mov     [rsp+arg_0], rbx
0x180077ac5  mov     [rsp+arg_8], rsi
0x180077aca  push    rdi
0x180077acb  sub     rsp, 30h
0x180077acf  mov     rdi, rcx
0x180077ad2  mov     rsi, rdx
0x180077ad5  mov     rcx, [rcx+30h]
0x180077ad9  test    rcx, rcx
0x180077adc  jz      loc_180077BA3
0x180077ae2  cmp     qword ptr [rdi+38h], 0
0x180077ae7  jz      loc_180077BA3
0x180077aed  test    rdx, rdx
0x180077af0  jz      short loc_180077B64
0x180077af2  mov     rcx, [rdi+38h]
0x180077af6  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180077afc  mov     ebx, eax
0x180077afe  test    eax, eax
0x180077b00  jns     short loc_180077B28
0x180077b02  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180077b09  mov     [rsp+38h+var_18], eax
0x180077b0d  xor     r8d, r8d; int
0x180077b10  lea     rdx, aWdcdataportalS_0; "WdcDataPortal::ShowFilterHint"
0x180077b17  lea     rcx, aBaseDiagnosisP_14; "base\\diagnosis\\pdui\\perfmon\\mon\\po"...
0x180077b1e  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180077b23  jmp     loc_180077BA8
0x180077b28  mov     rcx, [rdi+38h]
0x180077b2c  mov     rdx, rsi
0x180077b2f  call    cs:__imp_?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccDesc(ushort const *)
0x180077b35  mov     ebx, eax
0x180077b37  test    eax, eax
0x180077b39  js      short loc_180077B02
0x180077b3b  mov     rcx, [rdi+30h]
0x180077b3f  xor     edx, edx
0x180077b41  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180077b47  mov     ebx, eax
0x180077b49  test    eax, eax
0x180077b4b  js      short loc_180077B02
0x180077b4d  mov     rcx, [rdi+30h]
0x180077b51  mov     edx, 1
0x180077b56  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180077b5c  mov     ebx, eax
0x180077b5e  test    eax, eax
0x180077b60  jns     short loc_180077BA8
0x180077b62  jmp     short loc_180077B02
0x180077b64  mov     edx, 0FFFFFFFDh
0x180077b69  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180077b6f  mov     ebx, eax
0x180077b71  test    eax, eax
0x180077b73  js      short loc_180077B02
0x180077b75  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180077b7c  mov     rcx, [rdi+38h]
0x180077b80  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x180077b86  mov     ebx, eax
0x180077b88  test    eax, eax
0x180077b8a  js      loc_180077B02
0x180077b90  mov     rdx, cs:__imp_?AccDescProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::AccDescProp(void)
0x180077b97  mov     rcx, [rdi+38h]
0x180077b9b  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x180077ba1  jmp     short loc_180077B5C
0x180077ba3  mov     ebx, 8000FFFFh
0x180077ba8  mov     rsi, [rsp+38h+arg_8]
0x180077bad  mov     eax, ebx
0x180077baf  mov     rbx, [rsp+38h+arg_0]
0x180077bb4  add     rsp, 30h
0x180077bb8  pop     rdi
0x180077bb9  retn
```
