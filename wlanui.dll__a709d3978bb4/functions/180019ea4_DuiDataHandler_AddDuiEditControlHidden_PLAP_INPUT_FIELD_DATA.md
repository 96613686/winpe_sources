# DuiDataHandler::AddDuiEditControlHidden(_PLAP_INPUT_FIELD_DATA *)

- ea: `0x180019ea4`
- end: `0x180019f9a`
- name: `?AddDuiEditControlHidden@DuiDataHandler@@AEAAXPEAU_PLAP_INPUT_FIELD_DATA@@@Z`
- size: `246`
- prototype: `void __fastcall(DuiDataHandler *__hidden this, struct _PLAP_INPUT_FIELD_DATA *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001ab44`

## callees

- `0x180019c58`
- `0x180019ea4`
- `0x18001a84c`
- `0x18001ad64`
- `0x18001ae4c`
- `0x18001b408`

## string_xrefs

- `0x180019f08`: `            <element layoutpos="top" layout="rowlayout(2)" width="300rp" padding="rect(10rp,0rp,10rp,0rp)" >                <element content="%1:" margin="rect(10rp,10rp,10rp,10rp)" />                <element layout="borderlayout()" content="%0:" accessible="true" accrole="statictext">                    <edit id="atom(%2)" passwordcharacter="0x25cf" layoutpos="top" margin="rect(10rp,10rp,10rp,10rp)" accessible="true" accrole="statictext"/>                </element>            </element>`
- `0x180019f01`: `            <element layoutpos="top" layout="flowlayout(1,0,2,2)" background="argb(0,0,0,0)" margin="rect(0rp, 10rp, 0rp, 5rp)" >                <element id="atom(%3)" layout="borderlayout()" sheet="UsersStyle" >                    <edit id="atom(%2)" passwordcharacter="0x25cf" accessible="true" layoutpos="client" sheet="UsersStyle" />                </element>            </element>`

## pseudocode

```c
void __fastcall DuiDataHandler::AddDuiEditControlHidden(DuiDataHandler *this, struct _PLAP_INPUT_FIELD_DATA *a2)
{
  unsigned __int16 *UniqueCOntrolContainerString; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rax
  BOOL v8; // eax
  wchar_t *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax
  _WORD *v12; // rdi
  WCHAR *v13; // r8
  unsigned __int16 *UniqueCOntrolString; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v15; // [rsp+28h] [rbp-20h]
  struct _PLAP_INPUT_FIELD_DATA *v16; // [rsp+30h] [rbp-18h]

  UniqueCOntrolString = DuiDataHandler::GetUniqueCOntrolString(this);
  UniqueCOntrolContainerString = DuiDataHandler::GetUniqueCOntrolContainerString(this);
  v5 = *((_QWORD *)this + 1);
  v15 = UniqueCOntrolContainerString;
  v16 = a2;
  std::vector<_DUI_EAPDATA_MAPPING>::push_back(v5, &UniqueCOntrolString);
  v6 = *((_QWORD *)this + 3);
  v8 = 0;
  if ( v6 )
  {
    v7 = *(_QWORD *)(v6 + 8);
    if ( v7 )
    {
      if ( *(_DWORD *)(v7 + 20) == 1 )
        v8 = 1;
    }
  }
  v9 = L"            <element layoutpos=\"top\" layout=\"rowlayout(2)\" width=\"300rp\" padding=\"rect(10rp,0rp,10rp,0rp)\""
        " >                <element content=\"%1:\" margin=\"rect(10rp,10rp,10rp,10rp)\" />                <element layou"
        "t=\"borderlayout()\" content=\"%0:\" accessible=\"true\" accrole=\"statictext\">                    <edit id=\"a"
        "tom(%2)\" passwordcharacter=\"0x25cf\" layoutpos=\"top\" margin=\"rect(10rp,10rp,10rp,10rp)\" accessible=\"true\""
        " accrole=\"statictext\"/>                </element>            </element>";
  if ( v8 )
    v9 = L"            <element layoutpos=\"top\" layout=\"flowlayout(1,0,2,2)\" background=\"argb(0,0,0,0)\" margin=\"rec"
          "t(0rp, 10rp, 0rp, 5rp)\" >                <element id=\"atom(%3)\" layout=\"borderlayout()\" sheet=\"UsersStyl"
          "e\" >                    <edit id=\"atom(%2)\" passwordcharacter=\"0x25cf\" accessible=\"true\" layoutpos=\"cl"
          "ient\" sheet=\"UsersStyle\" />                </element>            </element>";
  std::wstring::operator+=(*(void **)this, v9);
  v10 = *((_QWORD *)this + 3);
  if ( v10 && (v11 = *(_QWORD *)(v10 + 8)) != 0 && *(_DWORD *)(v11 + 20) == 1 )
  {
    v12 = (_WORD *)((char *)a2 + 12);
    v13 = (WCHAR *)&String;
  }
  else
  {
    v13 = (WCHAR *)((char *)a2 + 12);
    v12 = (_WORD *)((char *)a2 + 12);
  }
  DuiStringFindAndReplace(*(void **)this, (__int64)L"%1", v13);
  DuiStringFindAndReplace(*(void **)this, (__int64)L"%0", v12);
  DuiStringFindAndReplace(*(void **)this, (__int64)L"%2", UniqueCOntrolString);
  DuiStringFindAndReplace(*(void **)this, (__int64)L"%3", v15);
}

```

## disassembly

```asm
0x180019ea4  mov     [rsp+arg_0], rbx
0x180019ea9  push    rdi
0x180019eaa  sub     rsp, 40h
0x180019eae  mov     rdi, rdx
0x180019eb1  mov     rbx, rcx
0x180019eb4  call    ?GetUniqueCOntrolString@DuiDataHandler@@AEAAPEAGXZ; DuiDataHandler::GetUniqueCOntrolString(void)
0x180019eb9  mov     rcx, rbx; this
0x180019ebc  mov     [rsp+48h+var_28], rax
0x180019ec1  call    ?GetUniqueCOntrolContainerString@DuiDataHandler@@AEAAPEAGXZ; DuiDataHandler::GetUniqueCOntrolContainerString(void)
0x180019ec6  mov     rcx, [rbx+8]
0x180019eca  lea     rdx, [rsp+48h+var_28]
0x180019ecf  mov     [rsp+48h+var_20], rax
0x180019ed4  mov     [rsp+48h+var_18], rdi
0x180019ed9  call    ?push_back@?$vector@U_DUI_EAPDATA_MAPPING@@V?$allocator@U_DUI_EAPDATA_MAPPING@@@std@@@std@@QEAAXAEBU_DUI_EAPDATA_MAPPING@@@Z; std::vector<_DUI_EAPDATA_MAPPING>::push_back(_DUI_EAPDATA_MAPPING const &)
0x180019ede  mov     rax, [rbx+18h]
0x180019ee2  test    rax, rax
0x180019ee5  jz      short loc_180019EFD
0x180019ee7  mov     rax, [rax+8]
0x180019eeb  test    rax, rax
0x180019eee  jz      short loc_180019EFD
0x180019ef0  cmp     dword ptr [rax+14h], 1
0x180019ef4  jnz     short loc_180019EFD
0x180019ef6  mov     eax, 1
0x180019efb  jmp     short loc_180019EFF
0x180019efd  xor     eax, eax
0x180019eff  test    eax, eax
0x180019f01  lea     rcx, aElementLayoutp_4; "            <element layoutpos=\"top\" "...
0x180019f08  lea     rdx, aElementLayoutp_2; "            <element layoutpos=\"top\" "...
0x180019f0f  cmovnz  rdx, rcx; void *
0x180019f13  mov     rcx, [rbx]; Src
0x180019f16  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180019f1b  mov     rax, [rbx+18h]
0x180019f1f  test    rax, rax
0x180019f22  jz      short loc_180019F40
0x180019f24  mov     rax, [rax+8]
0x180019f28  test    rax, rax
0x180019f2b  jz      short loc_180019F40
0x180019f2d  cmp     dword ptr [rax+14h], 1
0x180019f31  jnz     short loc_180019F40
0x180019f33  add     rdi, 0Ch
0x180019f37  lea     r8, String
0x180019f3e  jmp     short loc_180019F47
0x180019f40  lea     r8, [rdi+0Ch]
0x180019f44  mov     rdi, r8
0x180019f47  mov     rcx, [rbx]; Src
0x180019f4a  lea     rdx, a1; "%1"
0x180019f51  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x180019f56  mov     rcx, [rbx]; Src
0x180019f59  lea     rdx, a0_0; "%0"
0x180019f60  mov     r8, rdi
0x180019f63  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x180019f68  mov     r8, [rsp+48h+var_28]
0x180019f6d  lea     rdx, a2; "%2"
0x180019f74  mov     rcx, [rbx]; Src
0x180019f77  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x180019f7c  mov     r8, [rsp+48h+var_20]
0x180019f81  lea     rdx, a3; "%3"
0x180019f88  mov     rcx, [rbx]; Src
0x180019f8b  mov     rbx, [rsp+48h+arg_0]
0x180019f90  add     rsp, 40h
0x180019f94  pop     rdi
0x180019f95  jmp     ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
```
