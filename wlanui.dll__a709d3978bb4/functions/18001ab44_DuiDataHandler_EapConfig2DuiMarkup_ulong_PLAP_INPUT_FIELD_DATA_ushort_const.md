# DuiDataHandler::EapConfig2DuiMarkup(ulong,_PLAP_INPUT_FIELD_DATA *,ushort const * *)

- ea: `0x18001ab44`
- end: `0x18001ad1e`
- name: `?EapConfig2DuiMarkup@DuiDataHandler@@QEAAJKPEAU_PLAP_INPUT_FIELD_DATA@@PEAPEBG@Z`
- size: `474`
- prototype: `__int64 __fastcall(DuiDataHandler *__hidden this, unsigned int, struct _PLAP_INPUT_FIELD_DATA *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017ca0`

## callees

- `0x1800011d0`
- `0x180019c58`
- `0x180019ea4`
- `0x180019fa0`
- `0x18001a09c`
- `0x18001a660`
- `0x18001a84c`
- `0x18001a8c0`
- `0x18001ab44`

## string_xrefs

- `0x18001ac1b`: `            <element id="atom(ErrorArea)" layoutpos="top" layout="flowlayout(0,0,2,0)" sheet="CredDialog" class="Information" visible="false">                <element id="atom(ImageArea)" class="ImageAlignmentWrapper" layout="verticalflowlayout(0,2,1)" visible="false">                    <element id="atom(ErrorIcon)" class="SmallIcon" %errorAreaErrorIcon visible="false"/>                </element>                <element id="atom(ErrorText)" layoutpos="top" class="DialogText" sheet="CredDialog" `
- `0x18001ace7`: `            <element id="atom(buttonpane)" layout="borderlayout()"                      background="themeable(dtb(TaskDialog, 8, 0), threedface)"                      padding="themeable(gtmar(TaskDialog, 8, 0, 3602), rect(0rp,9rp,0rp,9rp))">                <element layoutpos="right" layout="flowlayout(0)" contentalign="wrapright | pathellipsis | wordellipsis" >                    <pushbutton id="atom(OKButton)" accessible="true" accRole="pushbutton"/>                    <pushbutton id="atom(Canc`
- `0x18001acde`: `            <element id="atom(buttonpane)" sheet="ButtonsStyle" layout="borderlayout()" layoutpos="top" >                <element layout="flowlayout(0,0,2,2)" contentalign="wrapright | pathellipsis | wordellipsis" padding="rect(0rp, 10rp, 0rp, 0rp)" margin="rect(0rp, 30rp, 0rp, 5rp)" >                    <button id="atom(OKButton)" sheet="ButtonsStyle" accessible="true" class="CommandButton" content="OK" selected="true" />                    <button id="atom(CancelButton)" sheet="ButtonsStyle" c`

## pseudocode

```c
__int64 __fastcall DuiDataHandler::EapConfig2DuiMarkup(
        DuiDataHandler *this,
        unsigned int a2,
        struct _PLAP_INPUT_FIELD_DATA *a3,
        const unsigned __int16 **a4)
{
  _QWORD *v8; // rax
  unsigned int v9; // esi
  int v10; // edi
  struct _PLAP_INPUT_FIELD_DATA *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  wchar_t *v17; // rdx
  const unsigned __int16 *v18; // rax

  v8 = operator new(0x20u);
  if ( v8 )
  {
    v8[3] = 7;
    v8[2] = 0;
    *(_WORD *)v8 = 0;
  }
  *(_QWORD *)this = v8;
  DuiDataHandler::AddDuiHeader(this);
  v9 = 0;
  v10 = 1;
  if ( a2 )
  {
    while ( 1 )
    {
      v11 = (struct _PLAP_INPUT_FIELD_DATA *)((char *)a3 + 2580 * v9);
      switch ( *(_DWORD *)v11 )
      {
        case 0:
LABEL_14:
          DuiDataHandler::AddDuiEditControlText(this, v11);
          goto LABEL_15;
        case 1:
          goto LABEL_13;
        case 2:
          goto LABEL_14;
        case 3:
        case 4:
        case 5:
          goto LABEL_13;
      }
      if ( *(_DWORD *)v11 == 7 )
        break;
      std::wstring::operator+=(
        *(void **)this,
        L"            <element layoutpos=\"top\" layout=\"rowlayout(1)\">                <element content=\"Unsupported ty"
         "pe\" />            </element>");
LABEL_15:
      if ( ++v9 >= a2 )
        goto LABEL_16;
    }
    if ( (*((_BYTE *)v11 + 4) & 1) == 0 )
      goto LABEL_14;
LABEL_13:
    DuiDataHandler::AddDuiEditControlHidden(this, v11);
    goto LABEL_15;
  }
LABEL_16:
  v12 = *((_QWORD *)this + 3);
  if ( v12 )
  {
    v13 = *(_QWORD *)(v12 + 8);
    if ( v13 )
    {
      if ( *(_DWORD *)(v13 + 20) == 1 )
      {
        std::wstring::operator+=(
          *(void **)this,
          L"            <element id=\"atom(ErrorArea)\" layoutpos=\"top\" layout=\"flowlayout(0,0,2,0)\" sheet=\"CredDialo"
           "g\" class=\"Information\" visible=\"false\">                <element id=\"atom(ImageArea)\" class=\"ImageAlig"
           "nmentWrapper\" layout=\"verticalflowlayout(0,2,1)\" visible=\"false\">                    <element id=\"atom("
           "ErrorIcon)\" class=\"SmallIcon\" %errorAreaErrorIcon visible=\"false\"/>                </element>           "
           "     <element id=\"atom(ErrorText)\" layoutpos=\"top\" class=\"DialogText\" sheet=\"CredDialog\" accessible=\""
           "true\" visible=\"false\"/>            </element>");
        v14 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL);
        if ( *(_DWORD *)(v14 + 176)
          && (!*(_DWORD *)(v14 + 184) || !*(_QWORD *)(v14 + 192))
          && *(_DWORD *)(v14 + 180)
          && *(_QWORD *)(v14 + 200) )
        {
          DuiStringFindAndReplace(*(void **)this);
          DuiStringFindAndReplace(*(void **)this);
        }
        DuiStringFindAndReplace(*(void **)this);
      }
    }
  }
  v15 = *((_QWORD *)this + 3);
  if ( !v15 || (v16 = *(_QWORD *)(v15 + 8)) == 0 || *(_DWORD *)(v16 + 20) != 1 )
    v10 = 0;
  v17 = L"            <element id=\"atom(buttonpane)\" layout=\"borderlayout()\"                      background=\"themeab"
         "le(dtb(TaskDialog, 8, 0), threedface)\"                      padding=\"themeable(gtmar(TaskDialog, 8, 0, 3602),"
         " rect(0rp,9rp,0rp,9rp))\">                <element layoutpos=\"right\" layout=\"flowlayout(0)\" contentalign=\""
         "wrapright | pathellipsis | wordellipsis\" >                    <pushbutton id=\"atom(OKButton)\" accessible=\"t"
         "rue\" accRole=\"pushbutton\"/>                    <pushbutton id=\"atom(CancelButton)\" accessible=\"true\" acc"
         "Role=\"pushbutton\"/>                </element>            </element>            <element id=\"atom(SKBSizing)\""
         " layout=\"borderlayout()\" layoutpos=\"none\" />";
  if ( v10 )
    v17 = L"            <element id=\"atom(buttonpane)\" sheet=\"ButtonsStyle\" layout=\"borderlayout()\" layoutpos=\"top\""
           " >                <element layout=\"flowlayout(0,0,2,2)\" contentalign=\"wrapright | pathellipsis | wordellip"
           "sis\" padding=\"rect(0rp, 10rp, 0rp, 0rp)\" margin=\"rect(0rp, 30rp, 0rp, 5rp)\" >                    <button"
           " id=\"atom(OKButton)\" sheet=\"ButtonsStyle\" accessible=\"true\" class=\"CommandButton\" content=\"OK\" sele"
           "cted=\"true\" />                    <button id=\"atom(CancelButton)\" sheet=\"ButtonsStyle\" class=\"CommandB"
           "utton\" content=\"Cancel\" />                </element>            </element>            <element id=\"atom(S"
           "KBSizing)\" layout=\"borderlayout()\" layoutpos=\"none\" />";
  std::wstring::operator+=(*(void **)this, v17);
  DuiDataHandler::AddDuiFooter(this);
  v18 = *(const unsigned __int16 **)this;
  if ( *(_QWORD *)(*(_QWORD *)this + 24LL) >= 8u )
    v18 = *(const unsigned __int16 **)v18;
  *a4 = v18;
  return 0;
}

```

## disassembly

```asm
0x18001ab44  push    rbx
0x18001ab46  push    rbp
0x18001ab47  push    rsi
0x18001ab48  push    rdi
0x18001ab49  push    r14
0x18001ab4b  push    r15
0x18001ab4d  sub     rsp, 28h
0x18001ab51  mov     rbx, rcx
0x18001ab54  mov     r15, r9
0x18001ab57  mov     ecx, 20h ; ' '; Size
0x18001ab5c  mov     r14, r8
0x18001ab5f  mov     ebp, edx
0x18001ab61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ab66  mov     [rsp+58h+arg_0], rax
0x18001ab6b  test    rax, rax
0x18001ab6e  jz      short loc_18001AB87
0x18001ab70  xor     r9d, r9d
0x18001ab73  mov     qword ptr [rax+18h], 7
0x18001ab7b  mov     qword ptr [rax+10h], 0
0x18001ab83  mov     [rax], r9w
0x18001ab87  mov     rcx, rbx; this
0x18001ab8a  mov     [rbx], rax
0x18001ab8d  call    ?AddDuiHeader@DuiDataHandler@@AEAAXXZ; DuiDataHandler::AddDuiHeader(void)
0x18001ab92  xor     esi, esi
0x18001ab94  lea     edi, [rsi+1]
0x18001ab97  test    ebp, ebp
0x18001ab99  jz      short loc_18001ABF5
0x18001ab9b  mov     eax, esi
0x18001ab9d  imul    rdx, rax, 0A14h
0x18001aba4  add     rdx, r14; struct _PLAP_INPUT_FIELD_DATA *
0x18001aba7  mov     ecx, [rdx]
0x18001aba9  test    ecx, ecx
0x18001abab  jz      short loc_18001ABE7
0x18001abad  sub     ecx, edi
0x18001abaf  jz      short loc_18001ABDD
0x18001abb1  sub     ecx, edi
0x18001abb3  jz      short loc_18001ABE7
0x18001abb5  sub     ecx, edi
0x18001abb7  jz      short loc_18001ABDD
0x18001abb9  sub     ecx, edi
0x18001abbb  jz      short loc_18001ABDD
0x18001abbd  sub     ecx, edi
0x18001abbf  jz      short loc_18001ABDD
0x18001abc1  cmp     ecx, 2
0x18001abc4  jz      short loc_18001ABD7
0x18001abc6  mov     rcx, [rbx]; Src
0x18001abc9  lea     rdx, aElementLayoutp; "            <element layoutpos=\"top\" "...
0x18001abd0  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x18001abd5  jmp     short loc_18001ABEF
0x18001abd7  test    [rdx+4], dil
0x18001abdb  jz      short loc_18001ABE7
0x18001abdd  mov     rcx, rbx; this
0x18001abe0  call    ?AddDuiEditControlHidden@DuiDataHandler@@AEAAXPEAU_PLAP_INPUT_FIELD_DATA@@@Z; DuiDataHandler::AddDuiEditControlHidden(_PLAP_INPUT_FIELD_DATA *)
0x18001abe5  jmp     short loc_18001ABEF
0x18001abe7  mov     rcx, rbx; this
0x18001abea  call    ?AddDuiEditControlText@DuiDataHandler@@AEAAXPEAU_PLAP_INPUT_FIELD_DATA@@@Z; DuiDataHandler::AddDuiEditControlText(_PLAP_INPUT_FIELD_DATA *)
0x18001abef  add     esi, edi
0x18001abf1  cmp     esi, ebp
0x18001abf3  jb      short loc_18001AB9B
0x18001abf5  mov     rax, [rbx+18h]
0x18001abf9  test    rax, rax
0x18001abfc  jz      loc_18001ACC2
0x18001ac02  mov     rcx, [rax+8]
0x18001ac06  test    rcx, rcx
0x18001ac09  jz      loc_18001ACC2
0x18001ac0f  cmp     [rcx+14h], edi
0x18001ac12  jnz     loc_18001ACC2
0x18001ac18  mov     rcx, [rbx]; Src
0x18001ac1b  lea     rdx, aElementIdAtomE; "            <element id=\"atom(ErrorAre"...
0x18001ac22  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x18001ac27  mov     rax, [rbx+18h]
0x18001ac2b  mov     rcx, [rax+8]
0x18001ac2f  cmp     dword ptr [rcx+0B0h], 0
0x18001ac36  jz      short loc_18001ACAC
0x18001ac38  cmp     dword ptr [rcx+0B8h], 0
0x18001ac3f  jz      short loc_18001AC54
0x18001ac41  cmp     qword ptr [rcx+0C0h], 0
0x18001ac49  jz      short loc_18001AC54
0x18001ac4b  lea     r8, aWidthSysmetric; "width=\"sysmetric(49)\" height=\"sysmet"...
0x18001ac52  jmp     short loc_18001ACB3
0x18001ac54  cmp     dword ptr [rcx+0B4h], 0
0x18001ac5b  jz      short loc_18001ACAC
0x18001ac5d  cmp     qword ptr [rcx+0C8h], 0
0x18001ac65  jz      short loc_18001ACAC
0x18001ac67  mov     rcx, [rbx]; Src
0x18001ac6a  lea     r8, aContentIcon1Sy; "content=\"icon(%1,sysmetric(49),sysmetr"...
0x18001ac71  lea     rdx, aErrorareaerror; "%errorAreaErrorIcon"
0x18001ac78  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001ac7d  mov     rax, [rbx+18h]
0x18001ac81  mov     rcx, [rbx]; Src
0x18001ac84  mov     r8, [rax+8]
0x18001ac88  mov     r8d, [r8+0BCh]
0x18001ac8f  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAGI@Z; DuiStringFindAndReplace(std::wstring *,ushort *,uint)
0x18001ac94  mov     rax, [rbx+18h]
0x18001ac98  lea     rdx, a2; "%2"
0x18001ac9f  mov     r8, [rax+8]
0x18001aca3  mov     r8, [r8+0C8h]
0x18001acaa  jmp     short loc_18001ACBA
0x18001acac  lea     r8, String
0x18001acb3  lea     rdx, aErrorareaerror; "%errorAreaErrorIcon"
0x18001acba  mov     rcx, [rbx]; Src
0x18001acbd  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001acc2  mov     rax, [rbx+18h]
0x18001acc6  test    rax, rax
0x18001acc9  jz      short loc_18001ACD9
0x18001accb  mov     rax, [rax+8]
0x18001accf  test    rax, rax
0x18001acd2  jz      short loc_18001ACD9
0x18001acd4  cmp     [rax+14h], edi
0x18001acd7  jz      short loc_18001ACDB
0x18001acd9  xor     edi, edi
0x18001acdb  mov     rcx, [rbx]; Src
0x18001acde  lea     rax, aElementIdAtomB_0; "            <element id=\"atom(buttonpa"...
0x18001ace5  test    edi, edi
0x18001ace7  lea     rdx, aElementIdAtomB; "            <element id=\"atom(buttonpa"...
0x18001acee  cmovnz  rdx, rax; void *
0x18001acf2  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x18001acf7  mov     rcx, rbx; this
0x18001acfa  call    ?AddDuiFooter@DuiDataHandler@@AEAAXXZ; DuiDataHandler::AddDuiFooter(void)
0x18001acff  mov     rax, [rbx]
0x18001ad02  cmp     qword ptr [rax+18h], 8
0x18001ad07  jb      short loc_18001AD0C
0x18001ad09  mov     rax, [rax]
0x18001ad0c  mov     [r15], rax
0x18001ad0f  xor     eax, eax
0x18001ad11  add     rsp, 28h
0x18001ad15  pop     r15
0x18001ad17  pop     r14
0x18001ad19  pop     rdi
0x18001ad1a  pop     rsi
0x18001ad1b  pop     rbp
0x18001ad1c  pop     rbx
0x18001ad1d  retn
```
