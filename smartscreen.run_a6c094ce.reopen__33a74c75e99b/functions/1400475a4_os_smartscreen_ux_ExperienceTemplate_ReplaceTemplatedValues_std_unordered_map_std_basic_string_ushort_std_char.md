# os_smartscreen::ux::ExperienceTemplate::ReplaceTemplatedValues(std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,bool)

- ea: `0x1400475a4`
- end: `0x140047ad1`
- name: `?ReplaceTemplatedValues@ExperienceTemplate@ux@os_smartscreen@@QEBA?AUUrlRepExperience@23@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_N@Z`
- size: `1325`
- prototype: `__int64 __fastcall(struct browser::navigation *)`
- caller_count: `1`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x140042b18`

## callees

- `0x140002990`
- `0x140002fe4`
- `0x140004370`
- `0x1400163ec`
- `0x140016a4c`
- `0x140016ca8`
- `0x140016e60`
- `0x140016e88`
- `0x140019338`
- `0x14001947c`
- `0x140019740`
- `0x1400198a0`
- `0x14001a0d4`
- `0x14001c58c`
- `0x14001e2b8`
- `0x1400248f8`
- `0x140026c20`
- `0x14003a084`
- `0x14003accc`
- `0x14003c040`
- `0x14003c070`
- `0x14003c0a0`
- `0x14003c0e0`
- `0x14003c6ec`
- `0x14003c714`
- `0x14003c92c`
- `0x140043234`
- `0x1400436fc`
- `0x1400459b4`
- `0x140046d04`
- `0x1400475a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall os_smartscreen::ux::ExperienceTemplate::ReplaceTemplatedValues(
        struct browser::navigation *a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  const wchar_t *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD *v14; // rdi
  _QWORD *i; // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  os_smartscreen::ux::ExperienceNotification *v31; // [rsp+20h] [rbp-E0h]
  _QWORD v32[4]; // [rsp+28h] [rbp-D8h] BYREF
  int v33; // [rsp+48h] [rbp-B8h]
  _BYTE v34[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h]
  _BYTE v36[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v37[32]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-40h]
  _BYTE v39[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v40[40]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v41[16]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v42[2]; // [rsp+128h] [rbp+28h] BYREF
  char v43; // [rsp+138h] [rbp+38h]
  _BYTE v44[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v45[8]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v46[32]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v47[40]; // [rsp+188h] [rbp+88h] BYREF
  __int64 v48; // [rsp+1B0h] [rbp+B0h]
  __int64 v49; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v50[32]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v51[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v52[40]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v53[16]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v54[16]; // [rsp+240h] [rbp+140h] BYREF
  char v55; // [rsp+250h] [rbp+150h]
  int v56; // [rsp+251h] [rbp+151h]
  __int16 v57; // [rsp+255h] [rbp+155h]
  char v58; // [rsp+257h] [rbp+157h]
  _BYTE v59[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v60[8]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v61[32]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v62[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  char v63; // [rsp+2C8h] [rbp+1C8h]
  __int64 v64; // [rsp+2D0h] [rbp+1D0h]

  v35 = a2;
  v38 = a3;
  v33 = 0;
  v8 = L"true";
  if ( !a4 )
    v8 = L"false";
  std::wstring::wstring(v36, L"overridesAllowed");
  std::wstring::wstring(v37, v8);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::pair<std::wstring const,std::wstring>>(
    a3,
    v32,
    v36);
  std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((path *)v36);
  std::wstring::wstring(v39);
  v40[32] = 0;
  std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>(v41);
  std::list<os_smartscreen::ux::NotificationButton>::list<os_smartscreen::ux::NotificationButton>(v42);
  v43 = 0;
  v9 = std::wstring::wstring(v32, (char *)a1 + 120);
  v10 = os_smartscreen::ux::ReplaceValues(v34, a3, v9, 3);
  std::wstring::operator=(v39, v10);
  path::~path((path *)v34);
  std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::operator=(
    v41,
    (char *)a1 + 192);
  v43 = *((_BYTE *)a1 + 224);
  if ( *((_BYTE *)a1 + 184) )
  {
    v11 = std::optional<std::wstring>::value((char *)a1 + 152);
    v12 = std::wstring::wstring(v34, v11);
    v13 = os_smartscreen::ux::ReplaceValues(v32, a3, v12, 3);
    std::optional<std::wstring>::operator=<std::wstring,0>(v40, v13);
    path::~path((path *)v32);
  }
  v14 = (_QWORD *)*((_QWORD *)a1 + 26);
  for ( i = (_QWORD *)*v14; i != v14; i = (_QWORD *)*i )
  {
    os_smartscreen::ux::NotificationButton::NotificationButton(
      (os_smartscreen::ux::NotificationButton *)v59,
      (const struct os_smartscreen::ux::NotificationButton *)(i + 2));
    if ( v63 || a4 )
    {
      v45[0] = 0;
      std::wstring::wstring(v46);
      v47[32] = 0;
      v48 = v64;
      v16 = std::wstring::wstring(v34, v61);
      v17 = os_smartscreen::ux::ReplaceValues(v32, a3, v16, 3);
      std::wstring::operator=(v46, v17);
      path::~path((path *)v32);
      if ( v63 )
      {
        v18 = std::optional<std::wstring>::value(v62);
        v19 = std::wstring::wstring(v34, v18);
        v20 = os_smartscreen::ux::ReplaceValues(v32, a3, v19, 3);
        std::optional<std::wstring>::operator=<std::wstring,0>(v47, v20);
        path::~path((path *)v32);
      }
      if ( v60[0] )
      {
        v21 = std::optional<std::wstring>::value(v59);
        v22 = std::wstring::wstring(v34, v21);
        v23 = os_smartscreen::ux::ReplaceValues(v32, a3, v22, 3);
        std::optional<std::wstring>::operator=<std::wstring,0>(v44, v23);
        path::~path((path *)v32);
      }
      std::list<os_smartscreen::ux::NotificationButton>::_Emplace<os_smartscreen::ux::NotificationButton const &>(
        v42,
        v42[0],
        v44);
      os_smartscreen::ux::NotificationButton::~NotificationButton((os_smartscreen::ux::NotificationButton *)v44);
    }
    os_smartscreen::ux::NotificationButton::~NotificationButton((os_smartscreen::ux::NotificationButton *)v59);
  }
  v49 = 0;
  std::wstring::wstring(v50);
  std::wstring::wstring(v51);
  v52[32] = 0;
  std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>(v53);
  std::list<os_smartscreen::ux::NotificationButton>::list<os_smartscreen::ux::NotificationButton>(v54);
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  LODWORD(v49) = *((_DWORD *)a1 + 20);
  std::wstring::operator=(v51, v39);
  std::optional<std::wstring>::operator=(v52, v40);
  std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::operator=(v53, v41);
  std::list<os_smartscreen::ux::NotificationButton>::_Assign_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<os_smartscreen::ux::NotificationButton>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<os_smartscreen::ux::NotificationButton>>,std::_Iterator_base0>>(
    v54,
    *(_QWORD *)v42[0],
    v42[0]);
  v55 = v43;
  v24 = std::wstring::wstring(v34, (char *)a1 + 88);
  v25 = os_smartscreen::ux::ReplaceValues(v32, a3, v24, 3);
  std::wstring::operator=(v50, v25);
  path::~path((path *)v32);
  v31 = (os_smartscreen::ux::ExperienceNotification *)os_smartscreen::ux::ExperienceNotification::ExperienceNotification(
                                                        (os_smartscreen::ux::ExperienceNotification *)v59,
                                                        (const struct os_smartscreen::ux::ExperienceNotification *)&v49);
  v47[0] = 0;
  v32[0] = v44;
  *(_BYTE *)(a2 + 72) = 0;
  os_smartscreen::ux::ExperienceNotification::ExperienceNotification(a2 + 80, v31);
  std::_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>::~_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>(v44);
  os_smartscreen::ux::ExperienceNotification::~ExperienceNotification(v31);
  v33 = 1;
  if ( *((_BYTE *)a1 + 72) )
  {
    browser::navigation::navigation((browser::navigation *)v44, a1);
    std::wstring::wstring(v59);
    v61[24] = 0;
    v26 = std::wstring::wstring(v34);
    v27 = os_smartscreen::ux::ReplaceValues(v36, a3, v26, 0);
    std::wstring::operator=(v59, v27);
    path::~path((path *)v36);
    if ( v46[24] )
    {
      std::optional<std::wstring>::value(v45);
      v28 = std::wstring::wstring(v36);
      v29 = os_smartscreen::ux::ReplaceValues(v34, a3, v28, 1);
      std::optional<std::wstring>::operator=<std::wstring,0>(v60, v29);
      path::~path((path *)v34);
    }
    std::optional<os_smartscreen::ux::ExperienceContent>::operator=<os_smartscreen::ux::ExperienceContent &,0>(a2, v59);
    browser::navigation::~navigation((browser::navigation *)v59);
    browser::navigation::~navigation((browser::navigation *)v44);
  }
  os_smartscreen::ux::ExperienceNotification::~ExperienceNotification((os_smartscreen::ux::ExperienceNotification *)&v49);
  os_smartscreen::ux::NotificationBody::~NotificationBody((os_smartscreen::ux::NotificationBody *)v39);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(a3);
  return a2;
}

```

## disassembly

```asm
0x1400475a4  mov     [rsp-8+arg_18], rbx
0x1400475a9  push    rbp
0x1400475aa  push    rsi
0x1400475ab  push    rdi
0x1400475ac  push    r12
0x1400475ae  push    r13
0x1400475b0  push    r14
0x1400475b2  push    r15
0x1400475b4  lea     rbp, [rsp-210h]
0x1400475bc  sub     rsp, 310h
0x1400475c3  mov     rax, cs:__security_cookie
0x1400475ca  xor     rax, rsp
0x1400475cd  mov     [rbp+240h+var_40], rax
0x1400475d4  mov     r12b, r9b
0x1400475d7  mov     rsi, r8
0x1400475da  mov     r15, rdx
0x1400475dd  mov     r14, rcx
0x1400475e0  mov     [rsp+340h+var_2D0], rdx
0x1400475e5  mov     [rbp+240h+var_280], r8
0x1400475e9  xor     r13d, r13d
0x1400475ec  mov     [rsp+340h+var_2F8], r13d
0x1400475f1  lea     rax, aFalse_0; "false"
0x1400475f8  lea     rbx, aTrue; "true"
0x1400475ff  test    r9b, r9b
0x140047602  cmovz   rbx, rax
0x140047606  lea     rdx, aOverridesallow; "overridesAllowed"
0x14004760d  lea     rcx, [rbp+240h+var_2C0]
0x140047611  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140047616  nop
0x140047617  mov     rdx, rbx
0x14004761a  lea     rcx, [rbp+240h+var_2A0]
0x14004761e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140047623  nop
0x140047624  lea     r8, [rbp+240h+var_2C0]
0x140047628  lea     rdx, [rsp+340h+var_318]
0x14004762d  mov     rcx, rsi
0x140047630  call    ??$emplace@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::pair<std::wstring const,std::wstring>>(std::pair<std::wstring const,std::wstring> &&)
0x140047635  nop
0x140047636  lea     rcx, [rbp+240h+var_2C0]; this
0x14004763a  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x14004763f  lea     rcx, [rbp+240h+var_270]
0x140047643  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140047648  nop
0x140047649  mov     [rbp+240h+var_230], r13b
0x14004764d  lea     rcx, [rbp+240h+var_228]
0x140047651  call    ??0?$list@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@V?$allocator@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@@2@@std@@QEAA@XZ; std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>(void)
0x140047656  nop
0x140047657  lea     rcx, [rbp+240h+var_218]
0x14004765b  call    ??0?$list@UNotificationButton@ux@os_smartscreen@@V?$allocator@UNotificationButton@ux@os_smartscreen@@@std@@@std@@QEAA@XZ; std::list<os_smartscreen::ux::NotificationButton>::list<os_smartscreen::ux::NotificationButton>(void)
0x140047660  mov     [rbp+240h+var_208], r13b
0x140047664  lea     rdx, [r14+78h]
0x140047668  lea     rcx, [rsp+340h+var_318]
0x14004766d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140047672  lea     ebx, [r13+3]
0x140047676  mov     r9d, ebx
0x140047679  mov     r8, rax
0x14004767c  mov     rdx, rsi
0x14004767f  lea     rcx, [rsp+340h+var_2F0]
0x140047684  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x140047689  mov     rdx, rax
0x14004768c  lea     rcx, [rbp+240h+var_270]
0x140047690  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140047695  lea     rcx, [rsp+340h+var_2F0]; this
0x14004769a  call    ??1path@@QEAA@XZ; path::~path(void)
0x14004769f  lea     rdx, [r14+0C0h]
0x1400476a6  lea     rcx, [rbp+240h+var_228]
0x1400476aa  call    ??4?$list@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@V?$allocator@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::operator=(std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>> const &)
0x1400476af  mov     al, [r14+0E0h]
0x1400476b6  mov     [rbp+240h+var_208], al
0x1400476b9  lea     rcx, [r14+98h]
0x1400476c0  cmp     [rcx+20h], r13b
0x1400476c4  jz      short loc_140047701
0x1400476c6  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1400476cb  mov     rdx, rax
0x1400476ce  lea     rcx, [rsp+340h+var_2F0]
0x1400476d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400476d8  mov     r9d, ebx
0x1400476db  mov     r8, rax
0x1400476de  mov     rdx, rsi
0x1400476e1  lea     rcx, [rsp+340h+var_318]
0x1400476e6  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x1400476eb  mov     rdx, rax
0x1400476ee  lea     rcx, [rbp+240h+var_250]
0x1400476f2  call    ??$?4V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::optional<std::wstring>::operator=<std::wstring,0>(std::wstring &&)
0x1400476f7  lea     rcx, [rsp+340h+var_318]; this
0x1400476fc  call    ??1path@@QEAA@XZ; path::~path(void)
0x140047701  mov     rdi, [r14+0D0h]
0x140047708  mov     rbx, [rdi]
0x14004770b  cmp     rbx, rdi
0x14004770e  jz      loc_140047865
0x140047714  lea     rdx, [rbx+10h]; struct os_smartscreen::ux::NotificationButton *
0x140047718  lea     rcx, [rbp+240h+var_E0]; this
0x14004771f  call    ??0NotificationButton@ux@os_smartscreen@@QEAA@AEBU012@@Z; os_smartscreen::ux::NotificationButton::NotificationButton(os_smartscreen::ux::NotificationButton const &)
0x140047724  nop
0x140047725  cmp     [rbp+240h+var_78], r13b
0x14004772c  jnz     short loc_140047737
0x14004772e  test    r12b, r12b
0x140047731  jz      loc_140047851
0x140047737  mov     [rbp+240h+var_1E0], r13b
0x14004773b  lea     rcx, [rbp+240h+var_1D8]
0x14004773f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140047744  mov     [rbp+240h+var_198], r13b
0x14004774b  mov     rax, [rbp+240h+var_70]
0x140047752  mov     [rbp+240h+var_190], rax
0x140047759  lea     rdx, [rbp+240h+var_B8]
0x140047760  lea     rcx, [rsp+340h+var_2F0]
0x140047765  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14004776a  mov     r9d, 3
0x140047770  mov     r8, rax
0x140047773  mov     rdx, rsi
0x140047776  lea     rcx, [rsp+340h+var_318]
0x14004777b  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x140047780  mov     rdx, rax
0x140047783  lea     rcx, [rbp+240h+var_1D8]
0x140047787  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14004778c  lea     rcx, [rsp+340h+var_318]; this
0x140047791  call    ??1path@@QEAA@XZ; path::~path(void)
0x140047796  cmp     [rbp+240h+var_78], r13b
0x14004779d  jz      short loc_1400477E7
0x14004779f  lea     rcx, [rbp+240h+var_98]
0x1400477a6  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1400477ab  mov     rdx, rax
0x1400477ae  lea     rcx, [rsp+340h+var_2F0]
0x1400477b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400477b8  mov     r9d, 3
0x1400477be  mov     r8, rax
0x1400477c1  mov     rdx, rsi
0x1400477c4  lea     rcx, [rsp+340h+var_318]
0x1400477c9  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x1400477ce  mov     rdx, rax
0x1400477d1  lea     rcx, [rbp+240h+var_1B8]
0x1400477d8  call    ??$?4V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::optional<std::wstring>::operator=<std::wstring,0>(std::wstring &&)
0x1400477dd  lea     rcx, [rsp+340h+var_318]; this
0x1400477e2  call    ??1path@@QEAA@XZ; path::~path(void)
0x1400477e7  cmp     [rbp+240h+var_C0], r13b
0x1400477ee  jz      short loc_140047835
0x1400477f0  lea     rcx, [rbp+240h+var_E0]
0x1400477f7  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1400477fc  mov     rdx, rax
0x1400477ff  lea     rcx, [rsp+340h+var_2F0]
0x140047804  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140047809  mov     r9d, 3
0x14004780f  mov     r8, rax
0x140047812  mov     rdx, rsi
0x140047815  lea     rcx, [rsp+340h+var_318]
0x14004781a  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x14004781f  mov     rdx, rax
0x140047822  lea     rcx, [rbp+240h+var_200]
0x140047826  call    ??$?4V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::optional<std::wstring>::operator=<std::wstring,0>(std::wstring &&)
0x14004782b  lea     rcx, [rsp+340h+var_318]; this
0x140047830  call    ??1path@@QEAA@XZ; path::~path(void)
0x140047835  lea     r8, [rbp+240h+var_200]
0x140047839  mov     rdx, [rbp+240h+var_218]
0x14004783d  lea     rcx, [rbp+240h+var_218]
0x140047841  call    ??$_Emplace@AEBUNotificationButton@ux@os_smartscreen@@@?$list@UNotificationButton@ux@os_smartscreen@@V?$allocator@UNotificationButton@ux@os_smartscreen@@@std@@@std@@QEAAPEAU?$_List_node@UNotificationButton@ux@os_smartscreen@@PEAX@1@QEAU21@AEBUNotificationButton@ux@os_smartscreen@@@Z; std::list<os_smartscreen::ux::NotificationButton>::_Emplace<os_smartscreen::ux::NotificationButton const &>(std::_List_node<os_smartscreen::ux::NotificationButton,void *> * const,os_smartscreen::ux::NotificationButton const &)
0x140047846  nop
0x140047847  lea     rcx, [rbp+240h+var_200]; this
0x14004784b  call    ??1NotificationButton@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::NotificationButton::~NotificationButton(void)
0x140047850  nop
0x140047851  lea     rcx, [rbp+240h+var_E0]; this
0x140047858  call    ??1NotificationButton@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::NotificationButton::~NotificationButton(void)
0x14004785d  mov     rbx, [rbx]
0x140047860  jmp     loc_14004770B
0x140047865  xor     eax, eax
0x140047867  mov     [rbp+240h+var_180], rax
0x14004786e  lea     rcx, [rbp+240h+var_178]
0x140047875  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14004787a  nop
0x14004787b  lea     rcx, [rbp+240h+var_158]
0x140047882  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140047887  nop
0x140047888  mov     [rbp+240h+var_118], r13b
0x14004788f  lea     rcx, [rbp+240h+var_110]
0x140047896  call    ??0?$list@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@V?$allocator@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@@2@@std@@QEAA@XZ; std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>(void)
0x14004789b  nop
0x14004789c  lea     rcx, [rbp+240h+var_100]
0x1400478a3  call    ??0?$list@UNotificationButton@ux@os_smartscreen@@V?$allocator@UNotificationButton@ux@os_smartscreen@@@std@@@std@@QEAA@XZ; std::list<os_smartscreen::ux::NotificationButton>::list<os_smartscreen::ux::NotificationButton>(void)
0x1400478a8  mov     [rbp+240h+var_F0], r13b
0x1400478af  xor     eax, eax
0x1400478b1  mov     [rbp+240h+var_EF], eax
0x1400478b7  mov     [rbp+240h+var_EB], ax
0x1400478be  mov     [rbp+240h+var_E9], al
0x1400478c4  mov     eax, [r14+50h]
0x1400478c8  mov     dword ptr [rbp+240h+var_180], eax
0x1400478ce  lea     rdx, [rbp+240h+var_270]
0x1400478d2  lea     rcx, [rbp+240h+var_158]
0x1400478d9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400478de  lea     rdx, [rbp+240h+var_250]
0x1400478e2  lea     rcx, [rbp+240h+var_138]
0x1400478e9  call    ??4?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::optional<std::wstring>::operator=(std::optional<std::wstring> const &)
0x1400478ee  lea     rdx, [rbp+240h+var_228]
0x1400478f2  lea     rcx, [rbp+240h+var_110]
0x1400478f9  call    ??4?$list@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@V?$allocator@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::operator=(std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>> const &)
0x1400478fe  mov     rdx, [rbp+240h+var_218]
0x140047902  mov     r8, rdx
0x140047905  mov     rdx, [rdx]
0x140047908  lea     rcx, [rbp+240h+var_100]
0x14004790f  call    ??$_Assign_unchecked@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UNotificationButton@ux@os_smartscreen@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$list@UNotificationButton@ux@os_smartscreen@@V?$allocator@UNotificationButton@ux@os_smartscreen@@@std@@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UNotificationButton@ux@os_smartscreen@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<os_smartscreen::ux::NotificationButton>::_Assign_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<os_smartscreen::ux::NotificationButton>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<os_smartscreen::ux::NotificationButton>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<os_smartscreen::ux::NotificationButton>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<os_smartscreen::ux::NotificationButton>>,std::_Iterator_base0>)
0x140047914  mov     al, [rbp+240h+var_208]
0x140047917  mov     [rbp+240h+var_F0], al
0x14004791d  lea     rdx, [r14+58h]
0x140047921  lea     rcx, [rsp+340h+var_2F0]
0x140047926  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14004792b  mov     r9d, 3
0x140047931  mov     r8, rax
0x140047934  mov     rdx, rsi
0x140047937  lea     rcx, [rsp+340h+var_318]
0x14004793c  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x140047941  mov     rdx, rax
0x140047944  lea     rcx, [rbp+240h+var_178]
0x14004794b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140047950  lea     rcx, [rsp+340h+var_318]; this
0x140047955  call    ??1path@@QEAA@XZ; path::~path(void)
0x14004795a  lea     rdx, [rbp+240h+var_180]; struct os_smartscreen::ux::ExperienceNotification *
0x140047961  lea     rcx, [rbp+240h+var_E0]; this
0x140047968  call    ??0ExperienceNotification@ux@os_smartscreen@@QEAA@AEBU012@@Z; os_smartscreen::ux::ExperienceNotification::ExperienceNotification(os_smartscreen::ux::ExperienceNotification const &)
0x14004796d  mov     rbx, rax
0x140047970  mov     [rsp+340h+var_320], rax
0x140047975  mov     [rbp+240h+var_1B8], r13b
0x14004797c  lea     rax, [rbp+240h+var_200]
0x140047980  mov     [rsp+340h+var_318], rax
0x140047985  mov     [r15+48h], r13b
0x140047989  lea     rcx, [r15+50h]
0x14004798d  mov     rdx, rbx
0x140047990  call    ??0ExperienceNotification@ux@os_smartscreen@@QEAA@$$QEAU012@@Z; os_smartscreen::ux::ExperienceNotification::ExperienceNotification(os_smartscreen::ux::ExperienceNotification &&)
0x140047995  nop
0x140047996  lea     rcx, [rbp+240h+var_200]
0x14004799a  call    ??1?$_Optional_destruct_base@UExperienceContent@ux@os_smartscreen@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>::~_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>(void)
0x14004799f  nop
0x1400479a0  mov     rcx, rbx; this
0x1400479a3  call    ??1ExperienceNotification@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::ExperienceNotification::~ExperienceNotification(void)
0x1400479a8  mov     ebx, 1
0x1400479ad  mov     [rsp+340h+var_2F8], ebx
0x1400479b1  cmp     [r14+48h], r13b
0x1400479b5  jz      loc_140047A84
0x1400479bb  mov     rdx, r14; struct browser::navigation *
0x1400479be  lea     rcx, [rbp+240h+var_200]; this
0x1400479c2  call    ??0navigation@browser@@QEAA@AEBU01@@Z; browser::navigation::navigation(browser::navigation const &)
0x1400479c7  nop
0x1400479c8  lea     rcx, [rbp+240h+var_E0]
0x1400479cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400479d4  mov     [rbp+240h+var_A0], r13b
0x1400479db  lea     rdx, [rbp+240h+var_200]
0x1400479df  lea     rcx, [rsp+340h+var_2F0]
0x1400479e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1400479e9  xor     r9d, r9d
0x1400479ec  mov     r8, rax
0x1400479ef  mov     rdx, rsi
0x1400479f2  lea     rcx, [rbp+240h+var_2C0]
0x1400479f6  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x1400479fb  mov     rdx, rax
0x1400479fe  lea     rcx, [rbp+240h+var_E0]
0x140047a05  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140047a0a  lea     rcx, [rbp+240h+var_2C0]; this
0x140047a0e  call    ??1path@@QEAA@XZ; path::~path(void)
0x140047a13  cmp     [rbp+240h+var_1C0], r13b
0x140047a1a  jz      short loc_140047A5D
0x140047a1c  lea     rcx, [rbp+240h+var_1E0]
0x140047a20  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x140047a25  mov     rdx, rax
0x140047a28  lea     rcx, [rbp+240h+var_2C0]
0x140047a2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x140047a31  mov     r9d, ebx
0x140047a34  mov     r8, rax
0x140047a37  mov     rdx, rsi
0x140047a3a  lea     rcx, [rsp+340h+var_2F0]
0x140047a3f  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x140047a44  mov     rdx, rax
0x140047a47  lea     rcx, [rbp+240h+var_C0]
0x140047a4e  call    ??$?4V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::optional<std::wstring>::operator=<std::wstring,0>(std::wstring &&)
0x140047a53  lea     rcx, [rsp+340h+var_2F0]; this
0x140047a58  call    ??1path@@QEAA@XZ; path::~path(void)
0x140047a5d  lea     rdx, [rbp+240h+var_E0]
0x140047a64  mov     rcx, r15
0x140047a67  call    ??$?4AEAUExperienceContent@ux@os_smartscreen@@$0A@@?$optional@UExperienceContent@ux@os_smartscreen@@@std@@QEAAAEAV01@AEAUExperienceContent@ux@os_smartscreen@@@Z; std::optional<os_smartscreen::ux::ExperienceContent>::operator=<os_smartscreen::ux::ExperienceContent &,0>(os_smartscreen::ux::ExperienceContent &)
0x140047a6c  nop
0x140047a6d  lea     rcx, [rbp+240h+var_E0]; this
0x140047a74  call    ??1navigation@browser@@QEAA@XZ; browser::navigation::~navigation(void)
0x140047a79  nop
0x140047a7a  lea     rcx, [rbp+240h+var_200]; this
0x140047a7e  call    ??1navigation@browser@@QEAA@XZ; browser::navigation::~navigation(void)
0x140047a83  nop
0x140047a84  lea     rcx, [rbp+240h+var_180]; this
0x140047a8b  call    ??1ExperienceNotification@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::ExperienceNotification::~ExperienceNotification(void)
0x140047a90  nop
0x140047a91  lea     rcx, [rbp+240h+var_270]; this
0x140047a95  call    ??1NotificationBody@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::NotificationBody::~NotificationBody(void)
0x140047a9a  nop
0x140047a9b  mov     rcx, rsi
0x140047a9e  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x140047aa3  mov     rax, r15
0x140047aa6  mov     rcx, [rbp+240h+var_40]
0x140047aad  xor     rcx, rsp; StackCookie
0x140047ab0  call    __security_check_cookie
0x140047ab5  mov     rbx, [rsp+340h+arg_18]
0x140047abd  add     rsp, 310h
0x140047ac4  pop     r15
0x140047ac6  pop     r14
0x140047ac8  pop     r13
0x140047aca  pop     r12
  ... truncated ...
```
