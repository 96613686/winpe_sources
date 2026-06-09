# os_smartscreen::ux::ExperienceTemplate::ReplaceTemplatedValues(std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,bool)

- ea: `0x140045d20`
- end: `0x14004624d`
- name: `?ReplaceTemplatedValues@ExperienceTemplate@ux@os_smartscreen@@QEBA?AUUrlRepExperience@23@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_N@Z`
- size: `1325`
- prototype: `__int64 __fastcall(struct browser::navigation *, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x1400413b4`

## callees

- `0x14000287c`
- `0x140002edc`
- `0x140004190`
- `0x140015810`
- `0x140015e60`
- `0x1400160b4`
- `0x140016260`
- `0x140016288`
- `0x140018674`
- `0x1400187b8`
- `0x140018a58`
- `0x140018bb4`
- `0x1400193dc`
- `0x14001b594`
- `0x14001d2d8`
- `0x140023774`
- `0x140025aa0`
- `0x140038a98`
- `0x1400396dc`
- `0x14003a9e8`
- `0x14003aa14`
- `0x14003aa40`
- `0x14003aa80`
- `0x14003b070`
- `0x14003b098`
- `0x14003b2b0`
- `0x140041ac4`
- `0x140041f88`
- `0x14004421c`
- `0x14004549c`
- `0x140045d20`

## pseudocode

```c
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
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rax
  __int64 v34; // rax
  os_smartscreen::ux::ExperienceNotification *v36; // [rsp+20h] [rbp-E0h]
  _QWORD v37[4]; // [rsp+28h] [rbp-D8h] BYREF
  int v38; // [rsp+48h] [rbp-B8h]
  _BYTE v39[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h]
  _BYTE v41[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v42[32]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+C0h] [rbp-40h]
  _BYTE v44[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v45[40]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v46[16]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v47[2]; // [rsp+128h] [rbp+28h] BYREF
  char v48; // [rsp+138h] [rbp+38h]
  _BYTE v49[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v50[8]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v51[32]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v52[40]; // [rsp+188h] [rbp+88h] BYREF
  __int64 v53; // [rsp+1B0h] [rbp+B0h]
  __int64 v54; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v55[32]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v56[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v57[40]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v58[16]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v59[16]; // [rsp+240h] [rbp+140h] BYREF
  char v60; // [rsp+250h] [rbp+150h]
  int v61; // [rsp+251h] [rbp+151h]
  __int16 v62; // [rsp+255h] [rbp+155h]
  char v63; // [rsp+257h] [rbp+157h]
  _BYTE v64[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v65[8]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v66[32]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v67[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  char v68; // [rsp+2C8h] [rbp+1C8h]
  __int64 v69; // [rsp+2D0h] [rbp+1D0h]

  v40 = a2;
  v43 = a3;
  v38 = 0;
  v8 = L"true";
  if ( !a4 )
    v8 = L"false";
  std::wstring::wstring(v41, L"overridesAllowed");
  std::wstring::wstring(v42, v8);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::pair<std::wstring const,std::wstring>>(
    a3,
    v37,
    v41);
  std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((path *)v41);
  std::wstring::wstring(v44);
  v45[32] = 0;
  std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>(v46);
  std::list<os_smartscreen::ux::NotificationButton>::list<os_smartscreen::ux::NotificationButton>(v47);
  v48 = 0;
  v9 = std::wstring::wstring(v37, (char *)a1 + 120);
  v10 = os_smartscreen::ux::ReplaceValues(v39, a3, v9, 3);
  std::wstring::operator=(v44, v10);
  path::~path((path *)v39);
  std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::operator=(
    v46,
    (char *)a1 + 192);
  v48 = *((_BYTE *)a1 + 224);
  if ( *((_BYTE *)a1 + 184) )
  {
    v11 = std::optional<std::wstring>::value((char *)a1 + 152);
    v12 = std::wstring::wstring(v39, v11);
    v13 = os_smartscreen::ux::ReplaceValues(v37, a3, v12, 3);
    std::optional<std::wstring>::operator=<std::wstring,0>(v45, v13);
    path::~path((path *)v37);
  }
  v14 = (_QWORD *)*((_QWORD *)a1 + 26);
  for ( i = (_QWORD *)*v14; i != v14; i = (_QWORD *)*i )
  {
    os_smartscreen::ux::NotificationButton::NotificationButton(
      (os_smartscreen::ux::NotificationButton *)v64,
      (const struct os_smartscreen::ux::NotificationButton *)(i + 2));
    if ( v68 || a4 )
    {
      v50[0] = 0;
      std::wstring::wstring(v51);
      v52[32] = 0;
      v53 = v69;
      v16 = std::wstring::wstring(v39, v66);
      v17 = os_smartscreen::ux::ReplaceValues(v37, a3, v16, 3);
      std::wstring::operator=(v51, v17);
      path::~path((path *)v37);
      if ( v68 )
      {
        v18 = std::optional<std::wstring>::value(v67);
        v19 = std::wstring::wstring(v39, v18);
        v20 = os_smartscreen::ux::ReplaceValues(v37, a3, v19, 3);
        std::optional<std::wstring>::operator=<std::wstring,0>(v52, v20);
        path::~path((path *)v37);
      }
      if ( v65[0] )
      {
        v21 = std::optional<std::wstring>::value(v64);
        v22 = std::wstring::wstring(v39, v21);
        v23 = os_smartscreen::ux::ReplaceValues(v37, a3, v22, 3);
        std::optional<std::wstring>::operator=<std::wstring,0>(v49, v23);
        path::~path((path *)v37);
      }
      std::list<os_smartscreen::ux::NotificationButton>::_Emplace<os_smartscreen::ux::NotificationButton const &>(
        v47,
        v47[0],
        v49);
      os_smartscreen::ux::NotificationButton::~NotificationButton((os_smartscreen::ux::NotificationButton *)v49);
    }
    os_smartscreen::ux::NotificationButton::~NotificationButton((os_smartscreen::ux::NotificationButton *)v64);
  }
  v54 = 0;
  std::wstring::wstring(v55);
  std::wstring::wstring(v56);
  v57[32] = 0;
  std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>(v58);
  std::list<os_smartscreen::ux::NotificationButton>::list<os_smartscreen::ux::NotificationButton>(v59);
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  LODWORD(v54) = *((_DWORD *)a1 + 20);
  std::wstring::operator=(v56, v44);
  std::optional<std::wstring>::operator=(v57, v45);
  std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::operator=(v58, v46);
  std::list<os_smartscreen::ux::NotificationButton>::_Assign_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<os_smartscreen::ux::NotificationButton>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<os_smartscreen::ux::NotificationButton>>,std::_Iterator_base0>>(
    v59,
    *(_QWORD *)v47[0],
    v47[0]);
  v60 = v48;
  v24 = std::wstring::wstring(v39, (char *)a1 + 88);
  v25 = os_smartscreen::ux::ReplaceValues(v37, a3, v24, 3);
  std::wstring::operator=(v55, v25);
  path::~path((path *)v37);
  v36 = (os_smartscreen::ux::ExperienceNotification *)os_smartscreen::ux::ExperienceNotification::ExperienceNotification(
                                                        (os_smartscreen::ux::ExperienceNotification *)v64,
                                                        (const struct os_smartscreen::ux::ExperienceNotification *)&v54);
  v52[0] = 0;
  v37[0] = v49;
  *(_BYTE *)(a2 + 72) = 0;
  os_smartscreen::ux::ExperienceNotification::ExperienceNotification(a2 + 80, v36);
  std::_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>::~_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>(v49);
  os_smartscreen::ux::ExperienceNotification::~ExperienceNotification(v36);
  v38 = 1;
  if ( *((_BYTE *)a1 + 72) )
  {
    browser::navigation::navigation((browser::navigation *)v49, a1);
    std::wstring::wstring(v64);
    v66[24] = 0;
    v28 = std::wstring::wstring(v39, v49, v26, v27);
    v29 = os_smartscreen::ux::ReplaceValues(v41, a3, v28, 0);
    std::wstring::operator=(v64, v29);
    path::~path((path *)v41);
    if ( v51[24] )
    {
      v30 = std::optional<std::wstring>::value(v50);
      v33 = std::wstring::wstring(v41, v30, v31, v32);
      v34 = os_smartscreen::ux::ReplaceValues(v39, a3, v33, 1);
      std::optional<std::wstring>::operator=<std::wstring,0>(v65, v34);
      path::~path((path *)v39);
    }
    std::optional<os_smartscreen::ux::ExperienceContent>::operator=<os_smartscreen::ux::ExperienceContent &,0>(a2, v64);
    browser::navigation::~navigation((browser::navigation *)v64);
    browser::navigation::~navigation((browser::navigation *)v49);
  }
  os_smartscreen::ux::ExperienceNotification::~ExperienceNotification((os_smartscreen::ux::ExperienceNotification *)&v54);
  os_smartscreen::ux::NotificationBody::~NotificationBody((os_smartscreen::ux::NotificationBody *)v44);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(a3);
  return a2;
}

```

## disassembly

```asm
0x140045d20  mov     [rsp-8+arg_18], rbx
0x140045d25  push    rbp
0x140045d26  push    rsi
0x140045d27  push    rdi
0x140045d28  push    r12
0x140045d2a  push    r13
0x140045d2c  push    r14
0x140045d2e  push    r15
0x140045d30  lea     rbp, [rsp-210h]
0x140045d38  sub     rsp, 310h
0x140045d3f  mov     rax, cs:__security_cookie
0x140045d46  xor     rax, rsp
0x140045d49  mov     [rbp+240h+var_40], rax
0x140045d50  mov     r12b, r9b
0x140045d53  mov     rsi, r8
0x140045d56  mov     r15, rdx
0x140045d59  mov     r14, rcx
0x140045d5c  mov     [rsp+340h+var_2D0], rdx
0x140045d61  mov     [rbp+240h+var_280], r8
0x140045d65  xor     r13d, r13d
0x140045d68  mov     [rsp+340h+var_2F8], r13d
0x140045d6d  lea     rax, aFalse_0; "false"
0x140045d74  lea     rbx, aTrue; "true"
0x140045d7b  test    r9b, r9b
0x140045d7e  cmovz   rbx, rax
0x140045d82  lea     rdx, aOverridesallow; "overridesAllowed"
0x140045d89  lea     rcx, [rbp+240h+var_2C0]
0x140045d8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140045d92  nop
0x140045d93  mov     rdx, rbx
0x140045d96  lea     rcx, [rbp+240h+var_2A0]
0x140045d9a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140045d9f  nop
0x140045da0  lea     r8, [rbp+240h+var_2C0]
0x140045da4  lea     rdx, [rsp+340h+var_318]
0x140045da9  mov     rcx, rsi
0x140045dac  call    ??$emplace@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::pair<std::wstring const,std::wstring>>(std::pair<std::wstring const,std::wstring> &&)
0x140045db1  nop
0x140045db2  lea     rcx, [rbp+240h+var_2C0]; this
0x140045db6  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x140045dbb  lea     rcx, [rbp+240h+var_270]
0x140045dbf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140045dc4  nop
0x140045dc5  mov     [rbp+240h+var_230], r13b
0x140045dc9  lea     rcx, [rbp+240h+var_228]
0x140045dcd  call    ??0?$list@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@V?$allocator@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@@2@@std@@QEAA@XZ; std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>(void)
0x140045dd2  nop
0x140045dd3  lea     rcx, [rbp+240h+var_218]
0x140045dd7  call    ??0?$list@UNotificationButton@ux@os_smartscreen@@V?$allocator@UNotificationButton@ux@os_smartscreen@@@std@@@std@@QEAA@XZ; std::list<os_smartscreen::ux::NotificationButton>::list<os_smartscreen::ux::NotificationButton>(void)
0x140045ddc  mov     [rbp+240h+var_208], r13b
0x140045de0  lea     rdx, [r14+78h]
0x140045de4  lea     rcx, [rsp+340h+var_318]
0x140045de9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045dee  lea     ebx, [r13+3]
0x140045df2  mov     r9d, ebx
0x140045df5  mov     r8, rax
0x140045df8  mov     rdx, rsi
0x140045dfb  lea     rcx, [rsp+340h+var_2F0]
0x140045e00  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x140045e05  mov     rdx, rax
0x140045e08  lea     rcx, [rbp+240h+var_270]
0x140045e0c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140045e11  lea     rcx, [rsp+340h+var_2F0]; this
0x140045e16  call    ??1path@@QEAA@XZ; path::~path(void)
0x140045e1b  lea     rdx, [r14+0C0h]
0x140045e22  lea     rcx, [rbp+240h+var_228]
0x140045e26  call    ??4?$list@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@V?$allocator@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::operator=(std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>> const &)
0x140045e2b  mov     al, [r14+0E0h]
0x140045e32  mov     [rbp+240h+var_208], al
0x140045e35  lea     rcx, [r14+98h]
0x140045e3c  cmp     [rcx+20h], r13b
0x140045e40  jz      short loc_140045E7D
0x140045e42  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x140045e47  mov     rdx, rax
0x140045e4a  lea     rcx, [rsp+340h+var_2F0]
0x140045e4f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045e54  mov     r9d, ebx
0x140045e57  mov     r8, rax
0x140045e5a  mov     rdx, rsi
0x140045e5d  lea     rcx, [rsp+340h+var_318]
0x140045e62  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x140045e67  mov     rdx, rax
0x140045e6a  lea     rcx, [rbp+240h+var_250]
0x140045e6e  call    ??$?4V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::optional<std::wstring>::operator=<std::wstring,0>(std::wstring &&)
0x140045e73  lea     rcx, [rsp+340h+var_318]; this
0x140045e78  call    ??1path@@QEAA@XZ; path::~path(void)
0x140045e7d  mov     rdi, [r14+0D0h]
0x140045e84  mov     rbx, [rdi]
0x140045e87  cmp     rbx, rdi
0x140045e8a  jz      loc_140045FE1
0x140045e90  lea     rdx, [rbx+10h]; struct os_smartscreen::ux::NotificationButton *
0x140045e94  lea     rcx, [rbp+240h+var_E0]; this
0x140045e9b  call    ??0NotificationButton@ux@os_smartscreen@@QEAA@AEBU012@@Z; os_smartscreen::ux::NotificationButton::NotificationButton(os_smartscreen::ux::NotificationButton const &)
0x140045ea0  nop
0x140045ea1  cmp     [rbp+240h+var_78], r13b
0x140045ea8  jnz     short loc_140045EB3
0x140045eaa  test    r12b, r12b
0x140045ead  jz      loc_140045FCD
0x140045eb3  mov     [rbp+240h+var_1E0], r13b
0x140045eb7  lea     rcx, [rbp+240h+var_1D8]
0x140045ebb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140045ec0  mov     [rbp+240h+var_198], r13b
0x140045ec7  mov     rax, [rbp+240h+var_70]
0x140045ece  mov     [rbp+240h+var_190], rax
0x140045ed5  lea     rdx, [rbp+240h+var_B8]
0x140045edc  lea     rcx, [rsp+340h+var_2F0]
0x140045ee1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045ee6  mov     r9d, 3
0x140045eec  mov     r8, rax
0x140045eef  mov     rdx, rsi
0x140045ef2  lea     rcx, [rsp+340h+var_318]
0x140045ef7  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x140045efc  mov     rdx, rax
0x140045eff  lea     rcx, [rbp+240h+var_1D8]
0x140045f03  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140045f08  lea     rcx, [rsp+340h+var_318]; this
0x140045f0d  call    ??1path@@QEAA@XZ; path::~path(void)
0x140045f12  cmp     [rbp+240h+var_78], r13b
0x140045f19  jz      short loc_140045F63
0x140045f1b  lea     rcx, [rbp+240h+var_98]
0x140045f22  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x140045f27  mov     rdx, rax
0x140045f2a  lea     rcx, [rsp+340h+var_2F0]
0x140045f2f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045f34  mov     r9d, 3
0x140045f3a  mov     r8, rax
0x140045f3d  mov     rdx, rsi
0x140045f40  lea     rcx, [rsp+340h+var_318]
0x140045f45  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x140045f4a  mov     rdx, rax
0x140045f4d  lea     rcx, [rbp+240h+var_1B8]
0x140045f54  call    ??$?4V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::optional<std::wstring>::operator=<std::wstring,0>(std::wstring &&)
0x140045f59  lea     rcx, [rsp+340h+var_318]; this
0x140045f5e  call    ??1path@@QEAA@XZ; path::~path(void)
0x140045f63  cmp     [rbp+240h+var_C0], r13b
0x140045f6a  jz      short loc_140045FB1
0x140045f6c  lea     rcx, [rbp+240h+var_E0]
0x140045f73  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x140045f78  mov     rdx, rax
0x140045f7b  lea     rcx, [rsp+340h+var_2F0]
0x140045f80  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045f85  mov     r9d, 3
0x140045f8b  mov     r8, rax
0x140045f8e  mov     rdx, rsi
0x140045f91  lea     rcx, [rsp+340h+var_318]
0x140045f96  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x140045f9b  mov     rdx, rax
0x140045f9e  lea     rcx, [rbp+240h+var_200]
0x140045fa2  call    ??$?4V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::optional<std::wstring>::operator=<std::wstring,0>(std::wstring &&)
0x140045fa7  lea     rcx, [rsp+340h+var_318]; this
0x140045fac  call    ??1path@@QEAA@XZ; path::~path(void)
0x140045fb1  lea     r8, [rbp+240h+var_200]
0x140045fb5  mov     rdx, [rbp+240h+var_218]
0x140045fb9  lea     rcx, [rbp+240h+var_218]
0x140045fbd  call    ??$_Emplace@AEBUNotificationButton@ux@os_smartscreen@@@?$list@UNotificationButton@ux@os_smartscreen@@V?$allocator@UNotificationButton@ux@os_smartscreen@@@std@@@std@@QEAAPEAU?$_List_node@UNotificationButton@ux@os_smartscreen@@PEAX@1@QEAU21@AEBUNotificationButton@ux@os_smartscreen@@@Z; std::list<os_smartscreen::ux::NotificationButton>::_Emplace<os_smartscreen::ux::NotificationButton const &>(std::_List_node<os_smartscreen::ux::NotificationButton,void *> * const,os_smartscreen::ux::NotificationButton const &)
0x140045fc2  nop
0x140045fc3  lea     rcx, [rbp+240h+var_200]; this
0x140045fc7  call    ??1NotificationButton@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::NotificationButton::~NotificationButton(void)
0x140045fcc  nop
0x140045fcd  lea     rcx, [rbp+240h+var_E0]; this
0x140045fd4  call    ??1NotificationButton@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::NotificationButton::~NotificationButton(void)
0x140045fd9  mov     rbx, [rbx]
0x140045fdc  jmp     loc_140045E87
0x140045fe1  xor     eax, eax
0x140045fe3  mov     [rbp+240h+var_180], rax
0x140045fea  lea     rcx, [rbp+240h+var_178]
0x140045ff1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140045ff6  nop
0x140045ff7  lea     rcx, [rbp+240h+var_158]
0x140045ffe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140046003  nop
0x140046004  mov     [rbp+240h+var_118], r13b
0x14004600b  lea     rcx, [rbp+240h+var_110]
0x140046012  call    ??0?$list@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@V?$allocator@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@@2@@std@@QEAA@XZ; std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>(void)
0x140046017  nop
0x140046018  lea     rcx, [rbp+240h+var_100]
0x14004601f  call    ??0?$list@UNotificationButton@ux@os_smartscreen@@V?$allocator@UNotificationButton@ux@os_smartscreen@@@std@@@std@@QEAA@XZ; std::list<os_smartscreen::ux::NotificationButton>::list<os_smartscreen::ux::NotificationButton>(void)
0x140046024  mov     [rbp+240h+var_F0], r13b
0x14004602b  xor     eax, eax
0x14004602d  mov     [rbp+240h+var_EF], eax
0x140046033  mov     [rbp+240h+var_EB], ax
0x14004603a  mov     [rbp+240h+var_E9], al
0x140046040  mov     eax, [r14+50h]
0x140046044  mov     dword ptr [rbp+240h+var_180], eax
0x14004604a  lea     rdx, [rbp+240h+var_270]
0x14004604e  lea     rcx, [rbp+240h+var_158]
0x140046055  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14004605a  lea     rdx, [rbp+240h+var_250]
0x14004605e  lea     rcx, [rbp+240h+var_138]
0x140046065  call    ??4?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::optional<std::wstring>::operator=(std::optional<std::wstring> const &)
0x14004606a  lea     rdx, [rbp+240h+var_228]
0x14004606e  lea     rcx, [rbp+240h+var_110]
0x140046075  call    ??4?$list@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@V?$allocator@V?$variant@UNotificationLink@ux@os_smartscreen@@UNotificationRun@23@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>>::operator=(std::list<std::variant<os_smartscreen::ux::NotificationLink,os_smartscreen::ux::NotificationRun>> const &)
0x14004607a  mov     rdx, [rbp+240h+var_218]
0x14004607e  mov     r8, rdx
0x140046081  mov     rdx, [rdx]
0x140046084  lea     rcx, [rbp+240h+var_100]
0x14004608b  call    ??$_Assign_unchecked@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UNotificationButton@ux@os_smartscreen@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$list@UNotificationButton@ux@os_smartscreen@@V?$allocator@UNotificationButton@ux@os_smartscreen@@@std@@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UNotificationButton@ux@os_smartscreen@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<os_smartscreen::ux::NotificationButton>::_Assign_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<os_smartscreen::ux::NotificationButton>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<os_smartscreen::ux::NotificationButton>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<os_smartscreen::ux::NotificationButton>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<os_smartscreen::ux::NotificationButton>>,std::_Iterator_base0>)
0x140046090  mov     al, [rbp+240h+var_208]
0x140046093  mov     [rbp+240h+var_F0], al
0x140046099  lea     rdx, [r14+58h]
0x14004609d  lea     rcx, [rsp+340h+var_2F0]
0x1400460a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400460a7  mov     r9d, 3
0x1400460ad  mov     r8, rax
0x1400460b0  mov     rdx, rsi
0x1400460b3  lea     rcx, [rsp+340h+var_318]
0x1400460b8  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x1400460bd  mov     rdx, rax
0x1400460c0  lea     rcx, [rbp+240h+var_178]
0x1400460c7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400460cc  lea     rcx, [rsp+340h+var_318]; this
0x1400460d1  call    ??1path@@QEAA@XZ; path::~path(void)
0x1400460d6  lea     rdx, [rbp+240h+var_180]; struct os_smartscreen::ux::ExperienceNotification *
0x1400460dd  lea     rcx, [rbp+240h+var_E0]; this
0x1400460e4  call    ??0ExperienceNotification@ux@os_smartscreen@@QEAA@AEBU012@@Z; os_smartscreen::ux::ExperienceNotification::ExperienceNotification(os_smartscreen::ux::ExperienceNotification const &)
0x1400460e9  mov     rbx, rax
0x1400460ec  mov     [rsp+340h+var_320], rax
0x1400460f1  mov     [rbp+240h+var_1B8], r13b
0x1400460f8  lea     rax, [rbp+240h+var_200]
0x1400460fc  mov     [rsp+340h+var_318], rax
0x140046101  mov     [r15+48h], r13b
0x140046105  lea     rcx, [r15+50h]
0x140046109  mov     rdx, rbx
0x14004610c  call    ??0ExperienceNotification@ux@os_smartscreen@@QEAA@$$QEAU012@@Z; os_smartscreen::ux::ExperienceNotification::ExperienceNotification(os_smartscreen::ux::ExperienceNotification &&)
0x140046111  nop
0x140046112  lea     rcx, [rbp+240h+var_200]
0x140046116  call    ??1?$_Optional_destruct_base@UExperienceContent@ux@os_smartscreen@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>::~_Optional_destruct_base<os_smartscreen::ux::ExperienceContent,0>(void)
0x14004611b  nop
0x14004611c  mov     rcx, rbx; this
0x14004611f  call    ??1ExperienceNotification@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::ExperienceNotification::~ExperienceNotification(void)
0x140046124  mov     ebx, 1
0x140046129  mov     [rsp+340h+var_2F8], ebx
0x14004612d  cmp     [r14+48h], r13b
0x140046131  jz      loc_140046200
0x140046137  mov     rdx, r14; struct browser::navigation *
0x14004613a  lea     rcx, [rbp+240h+var_200]; this
0x14004613e  call    ??0navigation@browser@@QEAA@AEBU01@@Z; browser::navigation::navigation(browser::navigation const &)
0x140046143  nop
0x140046144  lea     rcx, [rbp+240h+var_E0]
0x14004614b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140046150  mov     [rbp+240h+var_A0], r13b
0x140046157  lea     rdx, [rbp+240h+var_200]
0x14004615b  lea     rcx, [rsp+340h+var_2F0]
0x140046160  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x140046165  xor     r9d, r9d
0x140046168  mov     r8, rax
0x14004616b  mov     rdx, rsi
0x14004616e  lea     rcx, [rbp+240h+var_2C0]
0x140046172  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x140046177  mov     rdx, rax
0x14004617a  lea     rcx, [rbp+240h+var_E0]
0x140046181  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140046186  lea     rcx, [rbp+240h+var_2C0]; this
0x14004618a  call    ??1path@@QEAA@XZ; path::~path(void)
0x14004618f  cmp     [rbp+240h+var_1C0], r13b
0x140046196  jz      short loc_1400461D9
0x140046198  lea     rcx, [rbp+240h+var_1E0]
0x14004619c  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1400461a1  mov     rdx, rax
0x1400461a4  lea     rcx, [rbp+240h+var_2C0]
0x1400461a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1400461ad  mov     r9d, ebx
0x1400461b0  mov     r8, rax
0x1400461b3  mov     rdx, rsi
0x1400461b6  lea     rcx, [rsp+340h+var_2F0]
0x1400461bb  call    ?ReplaceValues@ux@os_smartscreen@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@V34@W4Encoding_t@12@@Z; os_smartscreen::ux::ReplaceValues(std::unordered_map<std::wstring,std::wstring> const &,std::wstring,os_smartscreen::ux::Encoding_t)
0x1400461c0  mov     rdx, rax
0x1400461c3  lea     rcx, [rbp+240h+var_C0]
0x1400461ca  call    ??$?4V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::optional<std::wstring>::operator=<std::wstring,0>(std::wstring &&)
0x1400461cf  lea     rcx, [rsp+340h+var_2F0]; this
0x1400461d4  call    ??1path@@QEAA@XZ; path::~path(void)
0x1400461d9  lea     rdx, [rbp+240h+var_E0]
0x1400461e0  mov     rcx, r15
0x1400461e3  call    ??$?4AEAUExperienceContent@ux@os_smartscreen@@$0A@@?$optional@UExperienceContent@ux@os_smartscreen@@@std@@QEAAAEAV01@AEAUExperienceContent@ux@os_smartscreen@@@Z; std::optional<os_smartscreen::ux::ExperienceContent>::operator=<os_smartscreen::ux::ExperienceContent &,0>(os_smartscreen::ux::ExperienceContent &)
0x1400461e8  nop
0x1400461e9  lea     rcx, [rbp+240h+var_E0]; this
0x1400461f0  call    ??1navigation@browser@@QEAA@XZ; browser::navigation::~navigation(void)
0x1400461f5  nop
0x1400461f6  lea     rcx, [rbp+240h+var_200]; this
0x1400461fa  call    ??1navigation@browser@@QEAA@XZ; browser::navigation::~navigation(void)
0x1400461ff  nop
0x140046200  lea     rcx, [rbp+240h+var_180]; this
0x140046207  call    ??1ExperienceNotification@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::ExperienceNotification::~ExperienceNotification(void)
0x14004620c  nop
0x14004620d  lea     rcx, [rbp+240h+var_270]; this
0x140046211  call    ??1NotificationBody@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::NotificationBody::~NotificationBody(void)
0x140046216  nop
0x140046217  mov     rcx, rsi
0x14004621a  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x14004621f  mov     rax, r15
0x140046222  mov     rcx, [rbp+240h+var_40]
0x140046229  xor     rcx, rsp; StackCookie
0x14004622c  call    __security_check_cookie
0x140046231  mov     rbx, [rsp+340h+arg_18]
0x140046239  add     rsp, 310h
0x140046240  pop     r15
0x140046242  pop     r14
0x140046244  pop     r13
0x140046246  pop     r12
  ... truncated ...
```
