# CreateArchiveWizard::CreateProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180050fe4`
- end: `0x1800513fa`
- name: `?CreateProc@CreateArchiveWizard@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1046`
- prototype: `__int64 __usercall@<rax>(CreateArchiveWizard *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180050fa0`

## callees

- `0x1800207f8`
- `0x180020cbc`
- `0x180020d1c`
- `0x1800210b0`
- `0x180034760`
- `0x180036f50`
- `0x180048d3c`
- `0x180048dac`
- `0x18005098c`
- `0x180050b40`
- `0x180050fe4`
- `0x180051400`
- `0x1800524b8`
- `0x180052634`
- `0x1800526a0`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x180051172`
- `SHELL32!SHGetFolderPathEx` at `0x180051172`
- `SHELL32!__imp_PathIsTemporaryW` at `0x18005114c`
- `SHELL32!__imp_PathIsTemporaryW` at `0x18005114c`
- `SHLWAPI!SHAutoComplete` at `0x180051255`
- `SHLWAPI!SHAutoComplete` at `0x180051255`
- `SHLWAPI!PathIsDirectoryW` at `0x1800510bc`
- `SHLWAPI!PathIsDirectoryW` at `0x1800510bc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180051365`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180051365`
- `USER32!SetDlgItemTextW` at `0x18005123b`
- `USER32!SetDlgItemTextW` at `0x18005123b`
- `USER32!GetParent` at `0x18005136e`
- `USER32!GetParent` at `0x18005136e`
- `USER32!SetWindowLongPtrW` at `0x1800513b6`
- `USER32!SetWindowLongPtrW` at `0x1800513b6`
- `USER32!PostMessageW` at `0x180051345`
- `USER32!PostMessageW` at `0x180051345`
- `USER32!SendMessageW` at `0x1800512ec`
- `USER32!SendMessageW` at `0x180051387`
- `USER32!SendMessageW` at `0x1800512ec`
- `USER32!SendMessageW` at `0x180051387`
- `USER32!EnableWindow` at `0x1800513a3`
- `USER32!EnableWindow` at `0x1800513a3`
- `USER32!GetDlgItem` at `0x180051247`
- `USER32!GetDlgItem` at `0x180051288`
- `USER32!GetDlgItem` at `0x180051395`
- `USER32!GetDlgItem` at `0x180051247`
- `USER32!GetDlgItem` at `0x180051288`
- `USER32!GetDlgItem` at `0x180051395`
- `USER32!CheckDlgButton` at `0x180051268`
- `USER32!CheckDlgButton` at `0x18005127b`
- `USER32!CheckDlgButton` at `0x180051268`
- `USER32!CheckDlgButton` at `0x18005127b`

## pseudocode

```c
__int64 __fastcall CreateArchiveWizard::CreateProc(LPCWSTR **this, HWND a2, int a3, int a4, HWND hWnd)
{
  HWND v5; // rsi
  CreateArchiveWizard *v6; // rbx
  int v7; // r8d
  int v8; // r8d
  LPCWSTR *v10; // rcx
  bool v11; // r15
  __int64 v12; // r12
  __int64 v13; // rax
  __int64 v14; // r13
  char *v15; // r14
  const char *v16; // r9
  const WCHAR *v17; // rax
  HWND DlgItem; // rax
  HWND v19; // rax
  HWND v20; // r12
  const struct ArchiveFormatSupportData *v21; // r14
  const void **v22; // rdi
  int v23; // ecx
  HWND Parent; // rax
  HWND v25; // rax
  __int64 v26; // [rsp+40h] [rbp-2A8h] BYREF
  __int64 v27; // [rsp+48h] [rbp-2A0h]
  CreateArchiveWizard *v28; // [rsp+50h] [rbp-298h]
  HWND v29; // [rsp+58h] [rbp-290h]
  __int64 v30; // [rsp+60h] [rbp-288h] BYREF
  __int64 v31; // [rsp+68h] [rbp-280h]
  __int64 v32; // [rsp+70h] [rbp-278h]
  __int64 v33; // [rsp+78h] [rbp-270h]
  _QWORD v34[4]; // [rsp+80h] [rbp-268h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v5 = a2;
  v6 = (CreateArchiveWizard *)this;
  v28 = (CreateArchiveWizard *)this;
  v29 = a2;
  v7 = a3 - 78;
  if ( v7 )
  {
    v8 = v7 - 194;
    if ( !v8 )
    {
      v10 = this[2];
      v11 = *((_QWORD *)v6 + 3) - (_QWORD)v10 == 8 && !PathIsDirectoryW(*v10);
      v12 = -1;
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)(**((_QWORD **)v6 + 2) + 2 * v13) );
      v26 = **((_QWORD **)v6 + 2);
      v27 = v13;
      split_filename(&v30, &v26);
      v26 = v32;
      v14 = v33;
      v27 = v33;
      try
      {
        split_extension(v34, &v26);
        v15 = (char *)v6 + 40;
        std::wstring::reserve((char *)v6 + 40, v14 + v31 + 4);
        if ( (unsigned int)PathIsTemporaryW(**((_QWORD **)v6 + 2))
          && (int)SHGetFolderPathEx(&FOLDERID_Documents, 0, 0, Buffer, 260) >= 0 )
        {
          do
            ++v12;
          while ( Buffer[v12] );
          std::wstring::_Assign<unsigned short>((char *)v6 + 40, Buffer, v12);
          if ( *(_WORD *)(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v6 + 40)
                        + 2LL * *((_QWORD *)v6 + 7)
                        - 2) != 92 )
            std::wstring::push_back((char *)v6 + 40);
        }
        if ( !*((_QWORD *)v6 + 7) )
          std::wstring::_Assign<unsigned short>((char *)v6 + 40, v30, v31);
        std::wstring::_Append<unsigned short>((char *)v6 + 40, v34[0], v34[1]);
        if ( v11 )
          std::wstring::_Append<unsigned short>((char *)v6 + 40, v34[2], v34[3]);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xAE,
          (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
          v16);
        v6 = v28;
        v15 = (char *)v28 + 40;
        v5 = v29;
      }
      v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
      SetDlgItemTextW(v5, 10650, v17);
      DlgItem = GetDlgItem(v5, 10650);
      SHAutoComplete(DlgItem, 0x20u);
      CheckDlgButton(v5, 10654, 1u);
      CheckDlgButton(v5, 10655, 1u);
      v19 = GetDlgItem(v5, 10651);
      v20 = v19;
      if ( v11 )
      {
        v21 = (const struct ArchiveFormatSupportData *)&g_rawFormatData;
        CreateArchiveWizard::AddComboBoxString(v19, 10620, &g_rawFormatData);
      }
      else
      {
        v21 = (const struct ArchiveFormatSupportData *)g_SupportedFormats;
      }
      v22 = (const void **)&g_SupportedFormats;
      do
      {
        CreateArchiveWizard::AddComboBoxString(v20, *((_DWORD *)*v22 + 1), *v22);
        ++v22;
      }
      while ( v22 != (const void **)&g_paxFormatData );
      SendMessageW(v20, 0x14Eu, 0, 0);
      CreateArchiveWizard::UpdateSelectedFormat(v6, v5, v21);
      return 1;
    }
    if ( v8 == 1 )
    {
      if ( (unsigned __int16)a4 == 1021 )
      {
        CreateArchiveWizard::Browse((CreateArchiveWizard *)this, a2);
      }
      else if ( (unsigned __int16)a4 == 10651 )
      {
        if ( HIWORD(a4) == 1 )
          CreateArchiveWizard::UpdateSelectedFormat((CreateArchiveWizard *)this, a2, hWnd);
      }
      else if ( (unsigned __int16)a4 == 10652 && HIWORD(a4) == 1 )
      {
        CreateArchiveWizard::UpdateCompressionMethod((CreateArchiveWizard *)this, a2, hWnd);
      }
      return 1;
    }
    return 0;
  }
  v23 = *((_DWORD *)hWnd + 4);
  if ( v23 != -208 )
  {
    if ( ((v23 + 203) & 0xFFFFFFFD) != 0 )
    {
      if ( v23 != -200 )
        return 0;
      PostMessageW(a2, 0x470u, 0, 4);
      LoadStringW(&_ImageBase, 0x2974u, Buffer, 260);
      Parent = GetParent(v5);
      SendMessageW(Parent, 0x479u, 0, (LPARAM)Buffer);
      v25 = GetDlgItem(v5, 1021);
      EnableWindow(v25, 1);
    }
    else
    {
      SetWindowLongPtrW(a2, 0, 0);
    }
    return 1;
  }
  return CreateArchiveWizard::DoCreateArchive(v6, a2);
}

```

## disassembly

```asm
0x180050fe4  mov     [rsp+arg_10], rbx
0x180050fe9  mov     [rsp+arg_18], rsi
0x180050fee  push    rdi
0x180050fef  push    r12
0x180050ff1  push    r13
0x180050ff3  push    r14
0x180050ff5  push    r15
0x180050ff7  sub     rsp, 2C0h
0x180050ffe  mov     rax, cs:__security_cookie
0x180051005  xor     rax, rsp
0x180051008  mov     [rsp+2E8h+var_38], rax
0x180051010  mov     rsi, rdx
0x180051013  mov     rbx, rcx
0x180051016  mov     [rsp+2E8h+var_298], rcx
0x18005101b  mov     [rsp+2E8h+var_290], rdx
0x180051020  mov     rdx, [rsp+2E8h+hWnd]
0x180051028  sub     r8d, 4Eh ; 'N'
0x18005102c  jz      loc_180051305
0x180051032  sub     r8d, 0C2h
0x180051039  jz      short loc_1800510A8
0x18005103b  cmp     r8d, 1
0x18005103f  jnz     loc_18005132D
0x180051045  movzx   ecx, r9w
0x180051049  sub     ecx, 3FDh
0x18005104f  jz      short loc_180051093
0x180051051  sub     ecx, 259Eh
0x180051057  jz      short loc_180051078
0x180051059  cmp     ecx, r8d
0x18005105c  jnz     short loc_18005109E
0x18005105e  shr     r9, 10h
0x180051062  cmp     r9w, r8w
0x180051066  jnz     short loc_18005109E
0x180051068  mov     r8, rdx; hWnd
0x18005106b  mov     rdx, rsi; HWND
0x18005106e  mov     rcx, rbx; this
0x180051071  call    ?UpdateCompressionMethod@CreateArchiveWizard@@AEAAXPEAUHWND__@@0@Z; CreateArchiveWizard::UpdateCompressionMethod(HWND__ *,HWND__ *)
0x180051076  jmp     short loc_18005109E
0x180051078  shr     r9, 10h
0x18005107c  cmp     r9w, 1
0x180051081  jnz     short loc_18005109E
0x180051083  mov     r8, rdx; HWND
0x180051086  mov     rdx, rsi; HWND
0x180051089  mov     rcx, rbx; this
0x18005108c  call    ?UpdateSelectedFormat@CreateArchiveWizard@@AEAAXPEAUHWND__@@0@Z; CreateArchiveWizard::UpdateSelectedFormat(HWND__ *,HWND__ *)
0x180051091  jmp     short loc_18005109E
0x180051093  mov     rdx, rsi; HWND
0x180051096  mov     rcx, rbx; this
0x180051099  call    ?Browse@CreateArchiveWizard@@AEAAJPEAUHWND__@@@Z; CreateArchiveWizard::Browse(HWND__ *)
0x18005109e  mov     eax, 1
0x1800510a3  jmp     loc_1800513CD
0x1800510a8  mov     rcx, [rcx+10h]
0x1800510ac  mov     rax, [rbx+18h]
0x1800510b0  sub     rax, rcx
0x1800510b3  cmp     rax, 8
0x1800510b7  jnz     short loc_1800510CD
0x1800510b9  mov     rcx, [rcx]; pszPath
0x1800510bc  call    cs:__imp_PathIsDirectoryW
0x1800510c2  xor     edi, edi
0x1800510c4  test    eax, eax
0x1800510c6  jnz     short loc_1800510CF
0x1800510c8  mov     r15b, 1
0x1800510cb  jmp     short loc_1800510D2
0x1800510cd  xor     edi, edi
0x1800510cf  mov     r15b, dil
0x1800510d2  mov     [rsp+2E8h+var_2B8], r15b
0x1800510d7  mov     rax, [rbx+10h]
0x1800510db  mov     rcx, [rax]
0x1800510de  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800510e2  mov     rax, r12
0x1800510e5  inc     rax
0x1800510e8  cmp     [rcx+rax*2], di
0x1800510ec  jnz     short loc_1800510E5
0x1800510ee  mov     [rsp+2E8h+var_2A8], rcx
0x1800510f3  mov     [rsp+2E8h+var_2A0], rax
0x1800510f8  lea     rdx, [rsp+2E8h+var_2A8]
0x1800510fd  lea     rcx, [rsp+2E8h+var_288]
0x180051102  call    ?split_filename@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_filename(std::basic_string_view<ushort>)
0x180051107  mov     rax, [rsp+2E8h+var_278]
0x18005110c  mov     [rsp+2E8h+var_2A8], rax
0x180051111  mov     r13, [rsp+2E8h+var_270]
0x180051116  mov     [rsp+2E8h+var_2A0], r13
0x18005111b  lea     rdx, [rsp+2E8h+var_2A8]
0x180051120  lea     rcx, [rsp+2E8h+var_268]
0x180051128  call    ?split_extension@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_extension(std::basic_string_view<ushort>)
0x18005112d  lea     r14, [rbx+28h]
0x180051131  mov     rdx, [rsp+2E8h+var_280]
0x180051136  add     rdx, 4
0x18005113a  add     rdx, r13
0x18005113d  mov     rcx, r14
0x180051140  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x180051145  mov     rcx, [rbx+10h]
0x180051149  mov     rcx, [rcx]
0x18005114c  call    cs:__imp_PathIsTemporaryW
0x180051152  test    eax, eax
0x180051154  jz      short loc_1800511C1
0x180051156  mov     [rsp+2E8h+var_2C8], 104h
0x18005115e  lea     r9, [rsp+2E8h+Buffer]
0x180051166  xor     r8d, r8d
0x180051169  xor     edx, edx
0x18005116b  lea     rcx, FOLDERID_Documents
0x180051172  call    cs:__imp_SHGetFolderPathEx
0x180051178  test    eax, eax
0x18005117a  js      short loc_1800511C1
0x18005117c  lea     rax, [rsp+2E8h+Buffer]
0x180051184  inc     r12
0x180051187  cmp     [rax+r12*2], di
0x18005118c  jnz     short loc_180051184
0x18005118e  mov     r8, r12
0x180051191  lea     rdx, [rsp+2E8h+Buffer]
0x180051199  mov     rcx, r14
0x18005119c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800511a1  mov     rcx, r14
0x1800511a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800511a9  mov     rcx, [r14+10h]
0x1800511ad  mov     edx, 5Ch ; '\'
0x1800511b2  cmp     [rax+rcx*2-2], dx
0x1800511b7  jz      short loc_1800511C1
0x1800511b9  mov     rcx, r14
0x1800511bc  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x1800511c1  cmp     [rbx+38h], rdi
0x1800511c5  jnz     short loc_1800511D9
0x1800511c7  mov     r8, [rsp+2E8h+var_280]
0x1800511cc  mov     rdx, [rsp+2E8h+var_288]
0x1800511d1  mov     rcx, r14
0x1800511d4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800511d9  mov     r8, [rsp+2E8h+var_260]
0x1800511e1  mov     rdx, [rsp+2E8h+var_268]
0x1800511e9  mov     rcx, r14
0x1800511ec  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800511f1  test    r15b, r15b
0x1800511f4  jz      short loc_18005120F
0x1800511f6  mov     r8, [rsp+2E8h+var_250]
0x1800511fe  mov     rdx, [rsp+2E8h+var_258]
0x180051206  mov     rcx, r14
0x180051209  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005120e  nop
0x18005120f  jmp     short loc_180051224
0x180051211  mov     rbx, [rsp+2E8h+var_298]
0x180051216  lea     r14, [rbx+28h]
0x18005121a  mov     r15b, [rsp+2E8h+var_2B8]
0x18005121f  mov     rsi, [rsp+2E8h+var_290]
0x180051224  mov     rcx, r14
0x180051227  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005122c  mov     r8, rax; lpString
0x18005122f  mov     r14d, 299Ah
0x180051235  mov     edx, r14d; nIDDlgItem
0x180051238  mov     rcx, rsi; hDlg
0x18005123b  call    cs:__imp_SetDlgItemTextW
0x180051241  mov     edx, r14d; nIDDlgItem
0x180051244  mov     rcx, rsi; hDlg
0x180051247  call    cs:__imp_GetDlgItem
0x18005124d  mov     rcx, rax; hwndEdit
0x180051250  mov     edx, 20h ; ' '; dwFlags
0x180051255  call    cs:__imp_SHAutoComplete
0x18005125b  lea     edx, [r14+4]; nIDButton
0x18005125f  mov     r8d, 1; uCheck
0x180051265  mov     rcx, rsi; hDlg
0x180051268  call    cs:__imp_CheckDlgButton
0x18005126e  lea     edx, [r14+5]; nIDButton
0x180051272  mov     r8d, 1; uCheck
0x180051278  mov     rcx, rsi; hDlg
0x18005127b  call    cs:__imp_CheckDlgButton
0x180051281  lea     edx, [r14+1]; nIDDlgItem
0x180051285  mov     rcx, rsi; hDlg
0x180051288  call    cs:__imp_GetDlgItem
0x18005128e  mov     r12, rax
0x180051291  test    r15b, r15b
0x180051294  jz      short loc_1800512AF
0x180051296  lea     r14, ?g_rawFormatData@@3UArchiveFormatSupportData@@B; ArchiveFormatSupportData const g_rawFormatData
0x18005129d  mov     r8, r14; void *
0x1800512a0  mov     edx, 297Ch; int
0x1800512a5  mov     rcx, rax; hWnd
0x1800512a8  call    ?AddComboBoxString@CreateArchiveWizard@@CA_NPEAUHWND__@@HPEBX@Z; CreateArchiveWizard::AddComboBoxString(HWND__ *,int,void const *)
0x1800512ad  jmp     short loc_1800512B6
0x1800512af  mov     r14, cs:?g_SupportedFormats@@3QBQEBUArchiveFormatSupportData@@B; ArchiveFormatSupportData const * const near * const g_SupportedFormats
0x1800512b6  lea     rdi, ?g_SupportedFormats@@3QBQEBUArchiveFormatSupportData@@B; ArchiveFormatSupportData const * const near * const g_SupportedFormats
0x1800512bd  mov     rdx, [rdi]
0x1800512c0  mov     r8, rdx; void *
0x1800512c3  mov     edx, [rdx+4]; int
0x1800512c6  mov     rcx, r12; hWnd
0x1800512c9  call    ?AddComboBoxString@CreateArchiveWizard@@CA_NPEAUHWND__@@HPEBX@Z; CreateArchiveWizard::AddComboBoxString(HWND__ *,int,void const *)
0x1800512ce  add     rdi, 8
0x1800512d2  lea     rax, ?g_paxFormatData@@3UArchiveFormatSupportData@@B; ArchiveFormatSupportData const g_paxFormatData
0x1800512d9  cmp     rdi, rax
0x1800512dc  jnz     short loc_1800512BD
0x1800512de  xor     r9d, r9d; lParam
0x1800512e1  xor     r8d, r8d; wParam
0x1800512e4  mov     edx, 14Eh; Msg
0x1800512e9  mov     rcx, r12; hWnd
0x1800512ec  call    cs:__imp_SendMessageW
0x1800512f2  mov     r8, r14; struct ArchiveFormatSupportData *
0x1800512f5  mov     rdx, rsi; HWND
0x1800512f8  mov     rcx, rbx; this
0x1800512fb  call    ?UpdateSelectedFormat@CreateArchiveWizard@@AEAAXPEAUHWND__@@PEBUArchiveFormatSupportData@@@Z; CreateArchiveWizard::UpdateSelectedFormat(HWND__ *,ArchiveFormatSupportData const *)
0x180051300  jmp     loc_18005109E
0x180051305  mov     ecx, [rdx+10h]
0x180051308  cmp     ecx, 0FFFFFF30h
0x18005130e  jz      loc_1800513C1
0x180051314  lea     eax, [rcx+0CBh]
0x18005131a  test    eax, 0FFFFFFFDh
0x18005131f  jz      loc_1800513AE
0x180051325  cmp     ecx, 0FFFFFF38h
0x18005132b  jz      short loc_180051334
0x18005132d  xor     eax, eax
0x18005132f  jmp     loc_1800513CD
0x180051334  mov     r9d, 4; lParam
0x18005133a  xor     r8d, r8d; wParam
0x18005133d  mov     edx, 470h; Msg
0x180051342  mov     rcx, rsi; hWnd
0x180051345  call    cs:__imp_PostMessageW
0x18005134b  mov     r9d, 104h; cchBufferMax
0x180051351  lea     r8, [rsp+2E8h+Buffer]; lpBuffer
0x180051359  mov     edx, 2974h; uID
0x18005135e  lea     rcx, __ImageBase; hInstance
0x180051365  call    cs:__imp_LoadStringW
0x18005136b  mov     rcx, rsi; hWnd
0x18005136e  call    cs:__imp_GetParent
0x180051374  mov     rcx, rax; hWnd
0x180051377  lea     r9, [rsp+2E8h+Buffer]; lParam
0x18005137f  xor     r8d, r8d; wParam
0x180051382  mov     edx, 479h; Msg
0x180051387  call    cs:__imp_SendMessageW
0x18005138d  mov     edx, 3FDh; nIDDlgItem
0x180051392  mov     rcx, rsi; hDlg
0x180051395  call    cs:__imp_GetDlgItem
0x18005139b  mov     rcx, rax; hWnd
0x18005139e  mov     edx, 1; bEnable
0x1800513a3  call    cs:__imp_EnableWindow
0x1800513a9  jmp     loc_18005109E
0x1800513ae  xor     r8d, r8d; dwNewLong
0x1800513b1  xor     edx, edx; nIndex
0x1800513b3  mov     rcx, rsi; hWnd
0x1800513b6  call    cs:__imp_SetWindowLongPtrW
0x1800513bc  jmp     loc_18005109E
0x1800513c1  mov     rdx, rsi; hDlg
0x1800513c4  mov     rcx, rbx; this
0x1800513c7  call    ?DoCreateArchive@CreateArchiveWizard@@AEAA_JPEAUHWND__@@@Z; CreateArchiveWizard::DoCreateArchive(HWND__ *)
0x1800513cc  nop
0x1800513cd  mov     rcx, [rsp+2E8h+var_38]
0x1800513d5  xor     rcx, rsp; StackCookie
0x1800513d8  call    __security_check_cookie
0x1800513dd  lea     r11, [rsp+2E8h+var_28]
0x1800513e5  mov     rbx, [r11+40h]
0x1800513e9  mov     rsi, [r11+48h]
0x1800513ed  mov     rsp, r11
0x1800513f0  pop     r15
0x1800513f2  pop     r14
0x1800513f4  pop     r13
0x1800513f6  pop     r12
0x1800513f8  pop     rdi
0x1800513f9  retn
```
