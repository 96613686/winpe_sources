# DuiDataHandler::AddDuiHeader(void)

- ea: `0x18001a660`
- end: `0x18001a845`
- name: `?AddDuiHeader@DuiDataHandler@@AEAAXXZ`
- size: `485`
- prototype: `void __fastcall(DuiDataHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ab44`

## callees

- `0x180019c58`
- `0x18001a660`
- `0x18001a84c`
- `0x18001bf40`

## import_xrefs

- `msvcrt!_itow` at `0x18001a74e`
- `msvcrt!_itow` at `0x18001a782`
- `msvcrt!_itow` at `0x18001a7c4`
- `msvcrt!_itow` at `0x18001a806`
- `msvcrt!_itow` at `0x18001a74e`
- `msvcrt!_itow` at `0x18001a782`
- `msvcrt!_itow` at `0x18001a7c4`
- `msvcrt!_itow` at `0x18001a806`
- `USER32!GetSystemMetrics` at `0x18001a71e`
- `USER32!GetSystemMetrics` at `0x18001a72b`
- `USER32!GetSystemMetrics` at `0x18001a71e`
- `USER32!GetSystemMetrics` at `0x18001a72b`

## string_xrefs

- `0x18001a824`: `<duixml>    <element resid="main" id="atom(dialogroot)" layout="filllayout()" sheet="common" width="350rp" visible="true" accessible="true">        <element layoutpos="top" layout="borderlayout()" >            <element layoutpos="top" layout="borderlayout()" >               <element id="atom(MessageText)" layoutpos="none"                         contentalign="wrapleft | pathellipsis | wordellipsis" overhang="false"                         accessible="true" padding="rect(10rp,10rp,10rp,10rp)" acc`
- `0x18001a6b5`: `<duixml>    <element resid="main" id="atom(dialogroot)" layout="filllayout()" width="%dialogwidth" height="%dialogheight" background="%backgroundcolor" >        <element id="atom(InsideFrame)" layout="borderlayout()" background="argb(0,0,0,0)" >         <element layout="ninegridlayout()" background="argb(0,0,0,0)" >          <element layoutpos="ninetop" layout="borderlayout()"  width="%topelementwidth" height="%topelementheight"  background="argb(0,0,0,0)" >          </element>          <element`

## pseudocode

```c
void __fastcall DuiDataHandler::AddDuiHeader(DuiDataHandler *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  wchar_t *v4; // r8
  __int64 v5; // r8
  unsigned __int16 *v6; // r8
  int SystemMetrics; // ebx
  int v8; // edi
  wchar_t Buffer[8]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v10; // [rsp+30h] [rbp-28h]
  __int64 v11; // [rsp+40h] [rbp-18h]

  v11 = 0;
  v2 = *((_QWORD *)this + 3);
  *(_OWORD *)Buffer = 0;
  v10 = 0;
  if ( v2 && (v3 = *(_QWORD *)(v2 + 8)) != 0 && *(_DWORD *)(v3 + 20) == 1 )
  {
    std::wstring::operator+=(
      *(void **)this,
      L"<duixml>    <element resid=\"main\" id=\"atom(dialogroot)\" layout=\"filllayout()\" width=\"%dialogwidth\" height="
       "\"%dialogheight\" background=\"%backgroundcolor\" >        <element id=\"atom(InsideFrame)\" layout=\"borderlayou"
       "t()\" background=\"argb(0,0,0,0)\" >         <element layout=\"ninegridlayout()\" background=\"argb(0,0,0,0)\" > "
       "         <element layoutpos=\"ninetop\" layout=\"borderlayout()\"  width=\"%topelementwidth\" height=\"%topelemen"
       "theight\"  background=\"argb(0,0,0,0)\" >          </element>          <element layoutpos=\"client\" layout=\"bor"
       "derlayout()\" background=\"argb(0,0,0,0)\" >            <element layoutpos=\"top\" layout=\"flowlayout(1,0,2,2)\""
       " background=\"argb(0,0,0,0)\" >                <element id=\"atom(TitleString)\" content=\"%duititlestring\" clas"
       "s=\"TitleString\" sheet=\"CredDialog\" />            </element>");
    v4 = L"argb(0,0,0,0)";
    if ( !*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + 8LL) )
      v4 = L"argb(255,24,0,82)";
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%backgroundcolor", v4);
    v5 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL);
    if ( !*(_DWORD *)(v5 + 4) || (v6 = *(unsigned __int16 **)(v5 + 24)) == 0 )
      v6 = L" ";
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%duititlestring", v6);
    SystemMetrics = GetSystemMetrics(0);
    v8 = GetSystemMetrics(1);
    *(_OWORD *)Buffer = 0;
    v11 = 0;
    v10 = 0;
    _itow(SystemMetrics, Buffer, 10);
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%dialogwidth", Buffer);
    v11 = 0;
    *(_OWORD *)Buffer = 0;
    v10 = 0;
    _itow(v8, Buffer, 10);
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%dialogheight", Buffer);
    v11 = 0;
    *(_OWORD *)Buffer = 0;
    v10 = 0;
    _itow(SystemMetrics / 3, Buffer, 10);
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%topelementwidth", Buffer);
    v11 = 0;
    *(_OWORD *)Buffer = 0;
    v10 = 0;
    _itow(v8 / 3, Buffer, 10);
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%topelementheight", Buffer);
  }
  else
  {
    std::wstring::operator+=(
      *(void **)this,
      L"<duixml>    <element resid=\"main\" id=\"atom(dialogroot)\" layout=\"filllayout()\" sheet=\"common\" width=\"350rp"
       "\" visible=\"true\" accessible=\"true\">        <element layoutpos=\"top\" layout=\"borderlayout()\" >           "
       " <element layoutpos=\"top\" layout=\"borderlayout()\" >               <element id=\"atom(MessageText)\" layoutpos"
       "=\"none\"                         contentalign=\"wrapleft | pathellipsis | wordellipsis\" overhang=\"false\"     "
       "                    accessible=\"true\" padding=\"rect(10rp,10rp,10rp,10rp)\" accrole=\"statictext\"             "
       "/>            </element>            <element id=\"atom(ProgramSeparator)\" layoutpos=\"top\" layout=\"filllayout("
       ")\" margin=\"rect(0rp,5rp,0rp,15rp)\">                <element height=\"themeable(gtmet(TaskDialog, 17, 0, 2417),"
       "'2rp')\"                          background=\"themeable(dtb(TaskDialog, 17, 0), graytext)\"                     "
       "     padding=\"rect(0rp,1rp,0rp,1rp)\"                 />            </element>");
  }
}

```

## disassembly

```asm
0x18001a660  push    rbp
0x18001a662  push    rbx
0x18001a663  push    rsi
0x18001a664  push    rdi
0x18001a665  mov     rbp, rsp
0x18001a668  sub     rsp, 58h
0x18001a66c  mov     rax, cs:__security_cookie
0x18001a673  xor     rax, rsp
0x18001a676  mov     [rbp+var_10], rax
0x18001a67a  xor     eax, eax
0x18001a67c  xorps   xmm0, xmm0
0x18001a67f  mov     [rbp+var_18], rax
0x18001a683  mov     rsi, rcx
0x18001a686  mov     rax, [rcx+18h]
0x18001a68a  movups  xmmword ptr [rbp+Buffer], xmm0
0x18001a68e  movups  [rbp+var_28], xmm0
0x18001a692  test    rax, rax
0x18001a695  jz      loc_18001A821
0x18001a69b  mov     rax, [rax+8]
0x18001a69f  test    rax, rax
0x18001a6a2  jz      loc_18001A821
0x18001a6a8  cmp     dword ptr [rax+14h], 1
0x18001a6ac  jnz     loc_18001A821
0x18001a6b2  mov     rcx, [rcx]; Src
0x18001a6b5  lea     rdx, aDuixmlElementR; "<duixml>    <element resid=\"main\" id="...
0x18001a6bc  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x18001a6c1  mov     rax, [rsi+18h]
0x18001a6c5  lea     r8, aArgb0000; "argb(0,0,0,0)"
0x18001a6cc  lea     rdx, aBackgroundcolo; "%backgroundcolor"
0x18001a6d3  mov     rcx, [rax+8]
0x18001a6d7  lea     rax, aArgb25524082; "argb(255,24,0,82)"
0x18001a6de  cmp     dword ptr [rcx+8], 0
0x18001a6e2  mov     rcx, [rsi]; Src
0x18001a6e5  cmovz   r8, rax
0x18001a6e9  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a6ee  mov     rax, [rsi+18h]
0x18001a6f2  mov     r8, [rax+8]
0x18001a6f6  cmp     dword ptr [r8+4], 0
0x18001a6fb  jz      short loc_18001A706
0x18001a6fd  mov     r8, [r8+18h]
0x18001a701  test    r8, r8
0x18001a704  jnz     short loc_18001A70D
0x18001a706  lea     r8, asc_1800218D4; " "
0x18001a70d  mov     rcx, [rsi]; Src
0x18001a710  lea     rdx, aDuititlestring; "%duititlestring"
0x18001a717  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a71c  xor     ecx, ecx; nIndex
0x18001a71e  call    cs:__imp_GetSystemMetrics
0x18001a724  mov     ecx, 1; nIndex
0x18001a729  mov     ebx, eax
0x18001a72b  call    cs:__imp_GetSystemMetrics
0x18001a731  xorps   xmm0, xmm0
0x18001a734  lea     rdx, [rbp+Buffer]; Buffer
0x18001a738  mov     edi, eax
0x18001a73a  mov     ecx, ebx; Value
0x18001a73c  xor     eax, eax
0x18001a73e  movups  xmmword ptr [rbp+Buffer], xmm0
0x18001a742  mov     [rbp+var_18], rax
0x18001a746  movups  [rbp+var_28], xmm0
0x18001a74a  lea     r8d, [rax+0Ah]; Radix
0x18001a74e  call    cs:__imp__itow
0x18001a754  mov     rcx, [rsi]; Src
0x18001a757  lea     r8, [rbp+Buffer]
0x18001a75b  lea     rdx, aDialogwidth; "%dialogwidth"
0x18001a762  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a767  xor     eax, eax
0x18001a769  lea     rdx, [rbp+Buffer]; Buffer
0x18001a76d  xorps   xmm0, xmm0
0x18001a770  mov     [rbp+var_18], rax
0x18001a774  mov     ecx, edi; Value
0x18001a776  movups  xmmword ptr [rbp+Buffer], xmm0
0x18001a77a  lea     r8d, [rax+0Ah]; Radix
0x18001a77e  movups  [rbp+var_28], xmm0
0x18001a782  call    cs:__imp__itow
0x18001a788  mov     rcx, [rsi]; Src
0x18001a78b  lea     r8, [rbp+Buffer]
0x18001a78f  lea     rdx, aDialogheight; "%dialogheight"
0x18001a796  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a79b  xor     eax, eax
0x18001a79d  xorps   xmm0, xmm0
0x18001a7a0  mov     [rbp+var_18], rax
0x18001a7a4  mov     r8d, 0Ah; Radix
0x18001a7aa  mov     eax, 55555556h
0x18001a7af  imul    ebx
0x18001a7b1  movups  xmmword ptr [rbp+Buffer], xmm0
0x18001a7b5  movups  [rbp+var_28], xmm0
0x18001a7b9  mov     ecx, edx
0x18001a7bb  shr     ecx, 1Fh
0x18001a7be  add     ecx, edx; Value
0x18001a7c0  lea     rdx, [rbp+Buffer]; Buffer
0x18001a7c4  call    cs:__imp__itow
0x18001a7ca  mov     rcx, [rsi]; Src
0x18001a7cd  lea     r8, [rbp+Buffer]
0x18001a7d1  lea     rdx, aTopelementwidt; "%topelementwidth"
0x18001a7d8  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a7dd  xor     ecx, ecx
0x18001a7df  xorps   xmm0, xmm0
0x18001a7e2  mov     [rbp+var_18], rcx
0x18001a7e6  mov     eax, 55555556h
0x18001a7eb  imul    edi
0x18001a7ed  movups  xmmword ptr [rbp+Buffer], xmm0
0x18001a7f1  movups  [rbp+var_28], xmm0
0x18001a7f5  mov     r8d, 0Ah; Radix
0x18001a7fb  mov     ecx, edx
0x18001a7fd  shr     ecx, 1Fh
0x18001a800  add     ecx, edx; Value
0x18001a802  lea     rdx, [rbp+Buffer]; Buffer
0x18001a806  call    cs:__imp__itow
0x18001a80c  mov     rcx, [rsi]; Src
0x18001a80f  lea     r8, [rbp+Buffer]
0x18001a813  lea     rdx, aTopelementheig; "%topelementheight"
0x18001a81a  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a81f  jmp     short loc_18001A830
0x18001a821  mov     rcx, [rcx]; Src
0x18001a824  lea     rdx, aDuixmlElementR_0; "<duixml>    <element resid=\"main\" id="...
0x18001a82b  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x18001a830  mov     rcx, [rbp+var_10]
0x18001a834  xor     rcx, rsp; StackCookie
0x18001a837  call    __security_check_cookie
0x18001a83c  add     rsp, 58h
0x18001a840  pop     rdi
0x18001a841  pop     rsi
0x18001a842  pop     rbx
0x18001a843  pop     rbp
0x18001a844  retn
```
