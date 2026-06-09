# CWcnPageWlanPbcCombo::_ValidateKeyAndPromptError(void)

- ea: `0x180017840`
- end: `0x1800179af`
- name: `?_ValidateKeyAndPromptError@CWcnPageWlanPbcCombo@@AEAA_NXZ`
- size: `367`
- prototype: `bool __fastcall(CWcnPageWlanPbcCombo *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180016f60`

## callees

- `0x18000e1dc`
- `0x18001294c`
- `0x180013354`
- `0x1800172f8`
- `0x180017840`
- `0x18001b618`
- `0x180027804`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017881`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017881`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800178ca`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800178ca`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001795a`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001795a`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180017946`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180017946`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800178dc`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800178dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall CWcnPageWlanPbcCombo::_ValidateKeyAndPromptError(CWcnPageWlanPbcCombo *this)
{
  int WlanPreconnectBlob; // edi
  char *v3; // r14
  void *v4; // rcx
  unsigned int *v5; // r8
  DirectUI::Element *v6; // rbx
  const unsigned __int16 *OnlyStringResource; // rax
  __int64 v8; // r8
  unsigned int *v9; // r9
  unsigned int Indent; // eax
  __int64 v11; // r10
  char v12; // r11
  __int64 v13; // rax
  void *v15; // [rsp+50h] [rbp+8h] BYREF

  CWcnPageWlanPbcCombo::_ReadPassword(this);
  WlanPreconnectBlob = -2147467259;
  v3 = (char *)this + 376;
  if ( *((_WORD *)this + 188) )
  {
    v4 = (void *)*((_QWORD *)this + 68);
    if ( v4 )
    {
      free(v4);
      *((_QWORD *)this + 68) = 0;
    }
    WlanPreconnectBlob = WcnCreateWlanPreconnectBlob(
                           (enum _DOT11_AUTH_ALGORITHM)*(_DWORD *)(*((_QWORD *)this + 45) + 216LL),
                           (const unsigned __int16 *)this + 188,
                           (struct _WLAN_PRECONNECT_INPUT_RESPONSE **)this + 68);
    if ( WlanPreconnectBlob < 0 )
    {
      v6 = (DirectUI::Element *)*((_QWORD *)this + 72);
      OnlyStringResource = LoadReadOnlyStringResource(hModule, 0x324u, v5);
      DirectUI::Element::SetContentString(v6, OnlyStringResource);
      DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 72), 1);
      v15 = 0;
      if ( DirectUI::DuiPVLTrigger::TriggerFade(&v15, *((struct DirectUI::Element **)this + 72), v8, v9) < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          Indent = (unsigned int)GetIndent(0);
          WPP_SF_sd(
            *(_QWORD *)(v11 + 16),
            33,
            (unsigned int)WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids,
            Indent,
            v12);
        }
        DirectUI::Element::SetVisible(*((DirectUI::Element **)this + 72), 1);
      }
      DirectUI::Element::SetClass(*((DirectUI::Element **)this + 73), L"InputPaddingWithText");
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 71) + 168LL))(*((_QWORD *)this + 71));
      DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)&v15);
    }
  }
  v13 = 130;
  do
  {
    *v3++ = 0;
    --v13;
  }
  while ( v13 );
  return WlanPreconnectBlob >= 0;
}

```

## disassembly

```asm
0x180017840  mov     [rsp+arg_8], rbx
0x180017845  mov     [rsp+arg_10], rbp
0x18001784a  push    rsi
0x18001784b  push    rdi
0x18001784c  push    r14
0x18001784e  sub     rsp, 30h
0x180017852  mov     rsi, rcx
0x180017855  call    ?_ReadPassword@CWcnPageWlanPbcCombo@@AEAA_NXZ; CWcnPageWlanPbcCombo::_ReadPassword(void)
0x18001785a  mov     edi, 80004005h
0x18001785f  lea     r14, [rsi+178h]
0x180017866  xor     ebp, ebp
0x180017868  cmp     [r14], bp
0x18001786c  jz      loc_180017981
0x180017872  lea     rbx, [rsi+220h]
0x180017879  mov     rcx, [rbx]; Block
0x18001787c  test    rcx, rcx
0x18001787f  jz      short loc_18001788A
0x180017881  call    cs:__imp_free
0x180017887  mov     [rbx], rbp
0x18001788a  mov     rcx, [rsi+168h]
0x180017891  mov     r8, rbx; struct _WLAN_PRECONNECT_INPUT_RESPONSE **
0x180017894  mov     rdx, r14; unsigned __int16 *
0x180017897  mov     ecx, [rcx+0D8h]; enum _DOT11_AUTH_ALGORITHM
0x18001789d  call    ?WcnCreateWlanPreconnectBlob@@YAJW4_DOT11_AUTH_ALGORITHM@@PEBGPEAPEAU_WLAN_PRECONNECT_INPUT_RESPONSE@@@Z; WcnCreateWlanPreconnectBlob(_DOT11_AUTH_ALGORITHM,ushort const *,_WLAN_PRECONNECT_INPUT_RESPONSE * *)
0x1800178a2  mov     edi, eax
0x1800178a4  test    eax, eax
0x1800178a6  jns     loc_180017981
0x1800178ac  mov     rbx, [rsi+240h]
0x1800178b3  mov     edx, 324h; unsigned int
0x1800178b8  mov     rcx, cs:hModule; hModule
0x1800178bf  call    ?LoadReadOnlyStringResource@@YAPEBGPEAUHINSTANCE__@@IPEAK@Z; LoadReadOnlyStringResource(HINSTANCE__ *,uint,ulong *)
0x1800178c4  mov     rdx, rax
0x1800178c7  mov     rcx, rbx
0x1800178ca  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800178d0  mov     edx, 1
0x1800178d5  mov     rcx, [rsi+240h]
0x1800178dc  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800178e2  mov     [rsp+48h+arg_0], rbp
0x1800178e7  mov     rdx, [rsi+240h]; struct DirectUI::Element *
0x1800178ee  lea     rcx, [rsp+48h+arg_0]; this
0x1800178f3  call    ?TriggerFade@DuiPVLTrigger@DirectUI@@QEAAJPEAVElement@2@IPEAK@Z; DirectUI::DuiPVLTrigger::TriggerFade(DirectUI::Element *,uint,ulong *)
0x1800178f8  mov     r11d, eax
0x1800178fb  test    eax, eax
0x1800178fd  jns     short loc_18001794C
0x1800178ff  lea     rax, WPP_GLOBAL_Control
0x180017906  mov     r10, cs:WPP_GLOBAL_Control
0x18001790d  cmp     r10, rax
0x180017910  jz      short loc_18001793D
0x180017912  cmp     byte ptr [r10+19h], 2
0x180017917  jb      short loc_18001793D
0x180017919  xor     ecx, ecx; int
0x18001791b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180017920  mov     edx, 21h ; '!'
0x180017925  mov     [rsp+48h+var_28], r11d
0x18001792a  mov     r9, rax
0x18001792d  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x180017934  mov     rcx, [r10+10h]
0x180017938  call    WPP_SF_sd
0x18001793d  mov     dl, 1
0x18001793f  mov     rcx, [rsi+240h]
0x180017946  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18001794c  lea     rdx, aInputpaddingwi; "InputPaddingWithText"
0x180017953  mov     rcx, [rsi+248h]
0x18001795a  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x180017960  mov     rcx, [rsi+238h]
0x180017967  mov     rax, [rcx]
0x18001796a  mov     rax, [rax+0A8h]
0x180017971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017976  nop
0x180017977  lea     rcx, [rsp+48h+arg_0]; this
0x18001797c  call    ??1DuiPVLTrigger@DirectUI@@QEAA@XZ; DirectUI::DuiPVLTrigger::~DuiPVLTrigger(void)
0x180017981  mov     eax, 82h
0x180017986  mov     [r14], bpl
0x180017989  inc     r14
0x18001798c  sub     rax, 1
0x180017990  jnz     short loc_180017986
0x180017992  shr     edi, 1Fh
0x180017995  xor     dil, 1
0x180017999  mov     al, dil
0x18001799c  mov     rbx, [rsp+48h+arg_8]
0x1800179a1  mov     rbp, [rsp+48h+arg_10]
0x1800179a6  add     rsp, 30h
0x1800179aa  pop     r14
0x1800179ac  pop     rdi
0x1800179ad  pop     rsi
0x1800179ae  retn
```
