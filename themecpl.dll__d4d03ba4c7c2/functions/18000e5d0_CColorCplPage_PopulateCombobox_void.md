# CColorCplPage::_PopulateCombobox(void)

- ea: `0x18000e5d0`
- end: `0x18000e95b`
- name: `?_PopulateCombobox@CColorCplPage@@AEAAXXZ`
- size: `907`
- prototype: `void __fastcall(CColorCplPage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000ddb0`

## callees

- `0x180002280`
- `0x180002f34`
- `0x180007fd8`
- `0x18000e5d0`
- `0x180057010`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x18000e78d`
- `SHELL32!SHGetFolderPathEx` at `0x18000e78d`
- `SHLWAPI!StrRStrIW` at `0x18000e730`
- `SHLWAPI!StrRStrIW` at `0x18000e730`
- `SHLWAPI!__imp_IsOS` at `0x18000e83d`
- `SHLWAPI!__imp_IsOS` at `0x18000e864`
- `SHLWAPI!__imp_IsOS` at `0x18000e83d`
- `SHLWAPI!__imp_IsOS` at `0x18000e864`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18000e88b`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18000e88b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e65e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e65e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e7d2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e7e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e7d2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e7e4`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18000e7c0`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18000e7c0`
- `USER32!SendMessageW` at `0x18000e624`
- `USER32!SendMessageW` at `0x18000e8de`
- `USER32!SendMessageW` at `0x18000e624`
- `USER32!SendMessageW` at `0x18000e8de`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x18000e8ab`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x18000e8ab`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x18000e91a`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x18000e91a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CColorCplPage::_PopulateCombobox(CColorCplPage *this)
{
  HWND v2; // rax
  char v3; // r12
  LPARAM v4; // rsi
  __int64 v5; // rdi
  WPARAM v6; // r14
  HWND v7; // rax
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v9; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR pszSource[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 102) + 360LL))(*((_QWORD *)this + 102));
  SendMessageW(v2, 0x14Bu, 0, 0);
  v8 = 0;
  v3 = 1;
  ppv = 0;
  if ( CoCreateInstance(&CLSID_ThemeManager2, 0, 1u, &GUID_c1e8c83e_845d_4d95_81db_e283fdffc000, &ppv) >= 0 )
  {
    v9 = 0;
    if ( (*(int (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0) >= 0
      && (*(int (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 88LL))(ppv, &v9) >= 0 )
    {
      v10 = 0;
      if ( (*(int (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 72LL))(ppv, v9, &v10) >= 0 )
      {
        if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 464LL))(v10, &v8) >= 0 )
        {
          pszSource[0] = 0;
          if ( (*(int (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v10 + 40LL))(v10, pszSource) >= 0 )
          {
            if ( v8 || !StrRStrIW(pszSource[0], 0, L"aero.msstyles") )
              v3 = 0;
            lpExistingFileName = 0;
            if ( (*(int (__fastcall **)(__int64, __int64, LPCWSTR *))(*(_QWORD *)v10 + 288LL))(
                   v10,
                   0xFFFFFFFFLL,
                   &lpExistingFileName) >= 0
              && (*((_WORD *)this + 131)
               || (int)SHGetFolderPathEx(&FOLDERID_LocalAppData, 0, 0, (char *)this + 262, 260) >= 0
               && (int)StringCchCatW(
                         (unsigned __int16 *)this + 131,
                         0x104u,
                         L"\\Microsoft\\Windows\\Themes\\Saved.theme") >= 0) )
            {
              CopyFileW(lpExistingFileName, (LPCWSTR)this + 131, 0);
            }
            SysFreeString((BSTR)lpExistingFileName);
          }
          SysFreeString((BSTR)pszSource[0]);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  v4 = 0;
  v5 = 0;
  do
  {
    memset_0(pszOutBuf, 0, 0x208u);
    if ( *((_BYTE *)&CColorCplPage::cs_rgComboboxThemes + v5 + 20) )
    {
      if ( IsOS(0x1Du) )
        goto LABEL_32;
      if ( *((_BYTE *)&CColorCplPage::cs_rgComboboxThemes + v5 + 20) )
        goto LABEL_25;
    }
    if ( *(_DWORD *)((char *)&CColorCplPage::cs_rgComboboxThemes + v5 + 16) || IsOS(0x1Du) )
    {
LABEL_25:
      if ( SHLoadIndirectString(*(PCWSTR *)((char *)&CColorCplPage::cs_rgComboboxThemes + v5 + 8), pszOutBuf, 0x104u, 0) >= 0 )
      {
        v6 = (int)DirectUI::Combobox::AddString(*((DirectUI::Combobox **)this + 102), pszOutBuf);
        v7 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 102) + 360LL))(*((_QWORD *)this + 102));
        SendMessageW(v7, 0x151u, v6, v4);
        if ( v3 )
        {
          if ( *((_BYTE *)&CColorCplPage::cs_rgComboboxThemes + v5 + 20) )
            goto LABEL_31;
        }
        else if ( !*((_BYTE *)&CColorCplPage::cs_rgComboboxThemes + v5 + 20)
               && *(_DWORD *)((char *)&CColorCplPage::cs_rgComboboxThemes + v5 + 16) == v8 )
        {
LABEL_31:
          DirectUI::Combobox::SetSelection(*((DirectUI::Combobox **)this + 102), v6);
        }
      }
    }
LABEL_32:
    ++v4;
    v5 += 24;
  }
  while ( v4 != 5 );
}

```

## disassembly

```asm
0x18000e5d0  push    rbp
0x18000e5d2  push    rbx
0x18000e5d3  push    rsi
0x18000e5d4  push    rdi
0x18000e5d5  push    r12
0x18000e5d7  push    r13
0x18000e5d9  push    r14
0x18000e5db  push    r15
0x18000e5dd  lea     rbp, [rsp-188h]
0x18000e5e5  sub     rsp, 288h
0x18000e5ec  mov     rax, cs:__security_cookie
0x18000e5f3  xor     rax, rsp
0x18000e5f6  mov     [rbp+1C0h+var_50], rax
0x18000e5fd  mov     r15, rcx
0x18000e600  mov     rcx, [rcx+330h]
0x18000e607  mov     rax, [rcx]
0x18000e60a  mov     rax, [rax+168h]
0x18000e611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e616  mov     rcx, rax; hWnd
0x18000e619  xor     r9d, r9d; lParam
0x18000e61c  xor     r8d, r8d; wParam
0x18000e61f  mov     edx, 14Bh; Msg
0x18000e624  call    cs:__imp_SendMessageW
0x18000e62b  nop     dword ptr [rax+rax+00h]
0x18000e630  xor     r13d, r13d
0x18000e633  mov     [rsp+2C0h+var_290], r13d
0x18000e638  mov     r12b, 1
0x18000e63b  mov     [rsp+2C0h+var_280], r13
0x18000e640  lea     rax, [rsp+2C0h+var_280]
0x18000e645  mov     [rsp+2C0h+ppv], rax; ppv
0x18000e64a  lea     r9, _GUID_c1e8c83e_845d_4d95_81db_e283fdffc000; riid
0x18000e651  xor     edx, edx; pUnkOuter
0x18000e653  lea     r8d, [r13+1]; dwClsContext
0x18000e657  lea     rcx, CLSID_ThemeManager2; rclsid
0x18000e65e  call    cs:__imp_CoCreateInstance
0x18000e665  nop     dword ptr [rax+rax+00h]
0x18000e66a  test    eax, eax
0x18000e66c  js      loc_18000E812
0x18000e672  mov     [rsp+2C0h+var_28C], r13d
0x18000e677  mov     rcx, [rsp+2C0h+var_280]
0x18000e67c  mov     rax, [rcx]
0x18000e67f  xor     edx, edx
0x18000e681  mov     rax, [rax+18h]
0x18000e685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e68a  test    eax, eax
0x18000e68c  js      loc_18000E801
0x18000e692  mov     rcx, [rsp+2C0h+var_280]
0x18000e697  mov     rax, [rcx]
0x18000e69a  lea     rdx, [rsp+2C0h+var_28C]
0x18000e69f  mov     rax, [rax+58h]
0x18000e6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6a8  test    eax, eax
0x18000e6aa  js      loc_18000E801
0x18000e6b0  mov     [rsp+2C0h+var_288], r13
0x18000e6b5  mov     rcx, [rsp+2C0h+var_280]
0x18000e6ba  mov     rax, [rcx]
0x18000e6bd  lea     r8, [rsp+2C0h+var_288]
0x18000e6c2  mov     edx, [rsp+2C0h+var_28C]
0x18000e6c6  mov     rax, [rax+48h]
0x18000e6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6cf  test    eax, eax
0x18000e6d1  js      loc_18000E801
0x18000e6d7  mov     rcx, [rsp+2C0h+var_288]
0x18000e6dc  mov     rax, [rcx]
0x18000e6df  lea     rdx, [rsp+2C0h+var_290]
0x18000e6e4  mov     rax, [rax+1D0h]
0x18000e6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6f0  test    eax, eax
0x18000e6f2  js      loc_18000E7F0
0x18000e6f8  mov     [rsp+2C0h+pszSource], r13
0x18000e6fd  mov     rcx, [rsp+2C0h+var_288]
0x18000e702  mov     rax, [rcx]
0x18000e705  lea     rdx, [rsp+2C0h+pszSource]
0x18000e70a  mov     rax, [rax+28h]
0x18000e70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e713  test    eax, eax
0x18000e715  js      loc_18000E7DF
0x18000e71b  cmp     [rsp+2C0h+var_290], r13d
0x18000e720  jnz     short loc_18000E741
0x18000e722  lea     r8, pszSrch; "aero.msstyles"
0x18000e729  xor     edx, edx; pszLast
0x18000e72b  mov     rcx, [rsp+2C0h+pszSource]; pszSource
0x18000e730  call    cs:__imp_StrRStrIW
0x18000e737  nop     dword ptr [rax+rax+00h]
0x18000e73c  test    rax, rax
0x18000e73f  jnz     short loc_18000E744
0x18000e741  mov     r12b, r13b
0x18000e744  mov     [rsp+2C0h+lpExistingFileName], r13
0x18000e749  mov     rcx, [rsp+2C0h+var_288]
0x18000e74e  mov     rax, [rcx]
0x18000e751  or      edx, 0FFFFFFFFh
0x18000e754  lea     r8, [rsp+2C0h+lpExistingFileName]
0x18000e759  mov     rax, [rax+120h]
0x18000e760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e765  test    eax, eax
0x18000e767  js      short loc_18000E7CD
0x18000e769  lea     rbx, [r15+106h]
0x18000e770  cmp     [rbx], r13w
0x18000e774  jnz     short loc_18000E7B5
0x18000e776  mov     dword ptr [rsp+2C0h+ppv], 104h
0x18000e77e  mov     r9, rbx
0x18000e781  xor     r8d, r8d
0x18000e784  xor     edx, edx
0x18000e786  lea     rcx, FOLDERID_LocalAppData
0x18000e78d  call    cs:__imp_SHGetFolderPathEx
0x18000e794  nop     dword ptr [rax+rax+00h]
0x18000e799  test    eax, eax
0x18000e79b  js      short loc_18000E7CD
0x18000e79d  lea     r8, aMicrosoftWindo; "\\Microsoft\\Windows\\Themes\\Saved.the"...
0x18000e7a4  mov     edx, 104h; unsigned __int64
0x18000e7a9  mov     rcx, rbx; unsigned __int16 *
0x18000e7ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e7b1  test    eax, eax
0x18000e7b3  js      short loc_18000E7CD
0x18000e7b5  xor     r8d, r8d; bFailIfExists
0x18000e7b8  mov     rdx, rbx; lpNewFileName
0x18000e7bb  mov     rcx, [rsp+2C0h+lpExistingFileName]; lpExistingFileName
0x18000e7c0  call    cs:__imp_CopyFileW
0x18000e7c7  nop     dword ptr [rax+rax+00h]
0x18000e7cc  nop
0x18000e7cd  mov     rcx, [rsp+2C0h+lpExistingFileName]; bstrString
0x18000e7d2  call    cs:__imp_SysFreeString
0x18000e7d9  nop     dword ptr [rax+rax+00h]
0x18000e7de  nop
0x18000e7df  mov     rcx, [rsp+2C0h+pszSource]; bstrString
0x18000e7e4  call    cs:__imp_SysFreeString
0x18000e7eb  nop     dword ptr [rax+rax+00h]
0x18000e7f0  mov     rcx, [rsp+2C0h+var_288]
0x18000e7f5  mov     rax, [rcx]
0x18000e7f8  mov     rax, [rax+10h]
0x18000e7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e801  mov     rcx, [rsp+2C0h+var_280]
0x18000e806  mov     rax, [rcx]
0x18000e809  mov     rax, [rax+10h]
0x18000e80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e812  mov     rsi, r13
0x18000e815  mov     rdi, r13
0x18000e818  lea     rbx, ?cs_rgComboboxThemes@CColorCplPage@@0QBUCOMBOBOX_THEMES@@B; COMBOBOX_THEMES const near * const CColorCplPage::cs_rgComboboxThemes
0x18000e81f  xor     edx, edx; Val
0x18000e821  mov     r8d, 208h; Size
0x18000e827  lea     rcx, [rsp+2C0h+pszOutBuf]; void *
0x18000e82c  call    memset_0
0x18000e831  cmp     [rdi+rbx+14h], r13b
0x18000e836  jz      short loc_18000E858
0x18000e838  mov     ecx, 1Dh; dwOS
0x18000e83d  call    cs:__imp_IsOS
0x18000e844  nop     dword ptr [rax+rax+00h]
0x18000e849  test    eax, eax
0x18000e84b  jnz     loc_18000E926
0x18000e851  cmp     [rdi+rbx+14h], r13b
0x18000e856  jnz     short loc_18000E878
0x18000e858  cmp     [rdi+rbx+10h], r13d
0x18000e85d  jnz     short loc_18000E878
0x18000e85f  mov     ecx, 1Dh; dwOS
0x18000e864  call    cs:__imp_IsOS
0x18000e86b  nop     dword ptr [rax+rax+00h]
0x18000e870  test    eax, eax
0x18000e872  jz      loc_18000E926
0x18000e878  xor     r9d, r9d; ppvReserved
0x18000e87b  mov     r8d, 104h; cchOutBuf
0x18000e881  lea     rdx, [rsp+2C0h+pszOutBuf]; pszOutBuf
0x18000e886  mov     rcx, [rdi+rbx+8]; pszSource
0x18000e88b  call    cs:__imp_SHLoadIndirectString
0x18000e892  nop     dword ptr [rax+rax+00h]
0x18000e897  test    eax, eax
0x18000e899  js      loc_18000E926
0x18000e89f  lea     rdx, [rsp+2C0h+pszOutBuf]
0x18000e8a4  mov     rcx, [r15+330h]
0x18000e8ab  call    cs:__imp_?AddString@Combobox@DirectUI@@QEAAHPEBG@Z; DirectUI::Combobox::AddString(ushort const *)
0x18000e8b2  nop     dword ptr [rax+rax+00h]
0x18000e8b7  movsxd  r14, eax
0x18000e8ba  mov     rcx, [r15+330h]
0x18000e8c1  mov     rdx, [rcx]
0x18000e8c4  mov     rax, [rdx+168h]
0x18000e8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8d0  mov     rcx, rax; hWnd
0x18000e8d3  mov     r9, rsi; lParam
0x18000e8d6  mov     r8, r14; wParam
0x18000e8d9  mov     edx, 151h; Msg
0x18000e8de  call    cs:__imp_SendMessageW
0x18000e8e5  nop     dword ptr [rax+rax+00h]
0x18000e8ea  lea     rbx, ?cs_rgComboboxThemes@CColorCplPage@@0QBUCOMBOBOX_THEMES@@B; COMBOBOX_THEMES const near * const CColorCplPage::cs_rgComboboxThemes
0x18000e8f1  test    r12b, r12b
0x18000e8f4  jz      short loc_18000E8FF
0x18000e8f6  cmp     [rdi+rbx+14h], r13b
0x18000e8fb  jnz     short loc_18000E910
0x18000e8fd  jmp     short loc_18000E926
0x18000e8ff  cmp     [rdi+rbx+14h], r13b
0x18000e904  jnz     short loc_18000E926
0x18000e906  mov     eax, [rsp+2C0h+var_290]
0x18000e90a  cmp     [rdi+rbx+10h], eax
0x18000e90e  jnz     short loc_18000E926
0x18000e910  mov     edx, r14d
0x18000e913  mov     rcx, [r15+330h]
0x18000e91a  call    cs:__imp_?SetSelection@Combobox@DirectUI@@QEAAJH@Z; DirectUI::Combobox::SetSelection(int)
0x18000e921  nop     dword ptr [rax+rax+00h]
0x18000e926  inc     rsi
0x18000e929  add     rdi, 18h
0x18000e92d  cmp     rsi, 5
0x18000e931  jnz     loc_18000E81F
0x18000e937  mov     rcx, [rbp+1C0h+var_50]
0x18000e93e  xor     rcx, rsp; StackCookie
0x18000e941  call    __security_check_cookie
0x18000e946  add     rsp, 288h
0x18000e94d  pop     r15
0x18000e94f  pop     r14
0x18000e951  pop     r13
0x18000e953  pop     r12
0x18000e955  pop     rdi
0x18000e956  pop     rsi
0x18000e957  pop     rbx
0x18000e958  pop     rbp
0x18000e959  retn
```
