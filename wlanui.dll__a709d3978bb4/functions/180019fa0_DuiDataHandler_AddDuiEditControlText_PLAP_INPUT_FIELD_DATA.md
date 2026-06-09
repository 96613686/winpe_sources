# DuiDataHandler::AddDuiEditControlText(_PLAP_INPUT_FIELD_DATA *)

- ea: `0x180019fa0`
- end: `0x18001a096`
- name: `?AddDuiEditControlText@DuiDataHandler@@AEAAXPEAU_PLAP_INPUT_FIELD_DATA@@@Z`
- size: `246`
- prototype: `void __fastcall(DuiDataHandler *__hidden this, struct _PLAP_INPUT_FIELD_DATA *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001ab44`

## callees

- `0x180019c58`
- `0x180019fa0`
- `0x18001a84c`
- `0x18001ad64`
- `0x18001ae4c`
- `0x18001b408`

## string_xrefs

- `0x18001a004`: `            <element layoutpos="top" layout="rowlayout(2)" width="300rp" padding="rect(10rp,0rp,10rp,0rp)">                <element content="%1:" margin="rect(10rp,10rp,10rp,10rp)"  />                <element content="%0:" accessible="true" accrole="statictext" layout="borderlayout()">                    <edit id="atom(%2)" layoutpos="top" margin="rect(10rp,10rp,10rp,10rp)" accessible="true" accrole="statictext"/>                </element>            </element>`

## pseudocode

```c
void __fastcall DuiDataHandler::AddDuiEditControlText(DuiDataHandler *this, struct _PLAP_INPUT_FIELD_DATA *a2)
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
        ">                <element content=\"%1:\" margin=\"rect(10rp,10rp,10rp,10rp)\"  />                <element conte"
        "nt=\"%0:\" accessible=\"true\" accrole=\"statictext\" layout=\"borderlayout()\">                    <edit id=\"a"
        "tom(%2)\" layoutpos=\"top\" margin=\"rect(10rp,10rp,10rp,10rp)\" accessible=\"true\" accrole=\"statictext\"/>   "
        "             </element>            </element>";
  if ( v8 )
    v9 = L"            <element layoutpos=\"top\" layout=\"flowlayout(1,0,2,2)\" background=\"argb(0,0,0,0)\" margin=\"rec"
          "t(0rp, 10rp, 0rp, 5rp)\" >                <element id=\"atom(%3)\" layout=\"borderlayout()\" sheet=\"UsersStyl"
          "e\" >                    <edit id=\"atom(%2)\" layoutpos=\"client\" sheet=\"UsersStyle\" />                </e"
          "lement>            </element>";
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
0x180019fa0  mov     [rsp+arg_0], rbx
0x180019fa5  push    rdi
0x180019fa6  sub     rsp, 40h
0x180019faa  mov     rdi, rdx
0x180019fad  mov     rbx, rcx
0x180019fb0  call    ?GetUniqueCOntrolString@DuiDataHandler@@AEAAPEAGXZ; DuiDataHandler::GetUniqueCOntrolString(void)
0x180019fb5  mov     rcx, rbx; this
0x180019fb8  mov     [rsp+48h+var_28], rax
0x180019fbd  call    ?GetUniqueCOntrolContainerString@DuiDataHandler@@AEAAPEAGXZ; DuiDataHandler::GetUniqueCOntrolContainerString(void)
0x180019fc2  mov     rcx, [rbx+8]
0x180019fc6  lea     rdx, [rsp+48h+var_28]
0x180019fcb  mov     [rsp+48h+var_20], rax
0x180019fd0  mov     [rsp+48h+var_18], rdi
0x180019fd5  call    ?push_back@?$vector@U_DUI_EAPDATA_MAPPING@@V?$allocator@U_DUI_EAPDATA_MAPPING@@@std@@@std@@QEAAXAEBU_DUI_EAPDATA_MAPPING@@@Z; std::vector<_DUI_EAPDATA_MAPPING>::push_back(_DUI_EAPDATA_MAPPING const &)
0x180019fda  mov     rax, [rbx+18h]
0x180019fde  test    rax, rax
0x180019fe1  jz      short loc_180019FF9
0x180019fe3  mov     rax, [rax+8]
0x180019fe7  test    rax, rax
0x180019fea  jz      short loc_180019FF9
0x180019fec  cmp     dword ptr [rax+14h], 1
0x180019ff0  jnz     short loc_180019FF9
0x180019ff2  mov     eax, 1
0x180019ff7  jmp     short loc_180019FFB
0x180019ff9  xor     eax, eax
0x180019ffb  test    eax, eax
0x180019ffd  lea     rcx, aElementLayoutp_3; "            <element layoutpos=\"top\" "...
0x18001a004  lea     rdx, aElementLayoutp_1; "            <element layoutpos=\"top\" "...
0x18001a00b  cmovnz  rdx, rcx; void *
0x18001a00f  mov     rcx, [rbx]; Src
0x18001a012  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x18001a017  mov     rax, [rbx+18h]
0x18001a01b  test    rax, rax
0x18001a01e  jz      short loc_18001A03C
0x18001a020  mov     rax, [rax+8]
0x18001a024  test    rax, rax
0x18001a027  jz      short loc_18001A03C
0x18001a029  cmp     dword ptr [rax+14h], 1
0x18001a02d  jnz     short loc_18001A03C
0x18001a02f  add     rdi, 0Ch
0x18001a033  lea     r8, String
0x18001a03a  jmp     short loc_18001A043
0x18001a03c  lea     r8, [rdi+0Ch]
0x18001a040  mov     rdi, r8
0x18001a043  mov     rcx, [rbx]; Src
0x18001a046  lea     rdx, a1; "%1"
0x18001a04d  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a052  mov     rcx, [rbx]; Src
0x18001a055  lea     rdx, a0_0; "%0"
0x18001a05c  mov     r8, rdi
0x18001a05f  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a064  mov     r8, [rsp+48h+var_28]
0x18001a069  lea     rdx, a2; "%2"
0x18001a070  mov     rcx, [rbx]; Src
0x18001a073  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a078  mov     r8, [rsp+48h+var_20]
0x18001a07d  lea     rdx, a3; "%3"
0x18001a084  mov     rcx, [rbx]; Src
0x18001a087  mov     rbx, [rsp+48h+arg_0]
0x18001a08c  add     rsp, 40h
0x18001a090  pop     rdi
0x18001a091  jmp     ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
```
