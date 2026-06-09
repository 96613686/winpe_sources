# BasicHwndUtils::GetPropertyValue(HWND__ *,int,UIA_TIMEOUTDATA &,tagVARIANT *)

- ea: `0x18009cc20`
- end: `0x18009cfab`
- name: `?GetPropertyValue@BasicHwndUtils@@SAJPEAUHWND__@@HAEAUUIA_TIMEOUTDATA@@PEAUtagVARIANT@@@Z`
- size: `907`
- prototype: `__int64 __fastcall(HWND, int, struct UIA_TIMEOUTDATA *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18009c9c0`
- `0x18024dd10`

## callees

- `0x180032724`
- `0x180083bc8`
- `0x1800984e0`
- `0x18009cc20`
- `0x18009cfb4`
- `0x18009d088`
- `0x18009d0e0`
- `0x18009d300`
- `0x18009df40`
- `0x1800dba8c`
- `0x1801e7ef0`
- `0x1801e8320`
- `0x1801e9258`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18009ce89`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18009ce89`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x18009ce74`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x18009ce74`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x18009cda1`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x18009cda1`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetGUIThreadInfo` at `0x18009cf35`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetGUIThreadInfo` at `0x18009cf35`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18009cf6a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18009cf6a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsChild` at `0x18009cf8e`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsChild` at `0x18009cf8e`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x18009cd2e`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x18009ce5e`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x18009cd2e`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x18009ce5e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009ce00`
- `OLEAUT32!__imp_SysFreeString` at `0x18009ce0b`
- `OLEAUT32!__imp_SysFreeString` at `0x18009ce00`
- `OLEAUT32!__imp_SysFreeString` at `0x18009ce0b`
- `OLEAUT32!__imp_VariantInit` at `0x18009cc54`
- `OLEAUT32!__imp_VariantInit` at `0x18009cc54`

## string_xrefs

- `0x18009ced1`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x18009cf00`: `onecore\windows\accessibletech\common\basichwndutils.cpp`

## pseudocode

```c
__int64 __fastcall BasicHwndUtils::GetPropertyValue(
        HWND a1,
        unsigned int a2,
        struct UIA_TIMEOUTDATA *a3,
        struct tagVARIANT *a4)
{
  int IsWindowPatternWindow; // eax
  LONGLONG *v10; // rax
  LONGLONG v11; // rcx
  OLECHAR *v12; // rcx
  unsigned int WindowLongW; // eax
  LONGLONG *bstr; // rax
  LONGLONG v15; // rcx
  int IsWinFormsControl; // eax
  const wchar_t *v17; // rdx
  bool v18; // cf
  int WindowTextAsBstr; // eax
  int WinFormsId; // eax
  int v21; // edi
  BSTR bstrString[2]; // [rsp+20h] [rbp-1A8h] BYREF
  tagGUITHREADINFO pgui; // [rsp+30h] [rbp-198h] BYREF
  WCHAR ClassName[128]; // [rsp+80h] [rbp-148h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  VariantInit(a4);
  if ( (int *)_std_find_trivial_4(";u", &dword_18030F244, a2) != &dword_18030F244 )
  {
    if ( a2 == 30011 )
    {
      if ( (unsigned int)BasicHwndUtils::IsWinFormsControl(a1) )
      {
        WinFormsId = BasicHwndUtils::GetWinFormsId(a1, a3, &a4->bstrVal);
        if ( WinFormsId < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x24F,
            (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
            (const char *)(unsigned int)WinFormsId,
            (int)bstrString[0]);
        if ( a4->llVal )
          a4->vt = 8;
      }
      if ( a4->vt )
        return 0;
      if ( (unsigned int)BasicHwndUtils::IsTopLevelWindow(a1) )
        return 0;
      WindowLongW = GetWindowLongW(a1, -12);
      if ( !WindowLongW
        || WindowLongW == -1
        || (int)StringCchPrintfW((unsigned __int16 *)&pgui, 0x20u, L"%d", WindowLongW) < 0 )
      {
        return 0;
      }
      bstr = (LONGLONG *)wil::make_bstr(bstrString, &pgui);
      v15 = *bstr;
      *bstr = 0;
      a4->llVal = v15;
      v12 = bstrString[0];
      if ( !bstrString[0] )
        goto LABEL_17;
    }
    else
    {
      switch ( a2 )
      {
        case 0x753Cu:
          if ( !GetClassNameW(a1, ClassName, 128) )
            return 0;
          v10 = (LONGLONG *)wil::make_bstr(bstrString, ClassName);
          break;
        case 0x7535u:
          WindowTextAsBstr = BasicHwndUtils::GetWindowTextAsBstr(a1, a3, &a4->bstrVal);
          if ( WindowTextAsBstr < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x273,
              (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
              (const char *)(unsigned int)WindowTextAsBstr,
              (int)bstrString[0]);
          goto LABEL_17;
        case 0x753Au:
          v18 = (unsigned int)BasicHwndUtils::IsWindowReallyEnabled(a1) != 0;
          goto LABEL_33;
        case 0x7532u:
          LODWORD(bstrString[0]) = 0;
          GetWindowThreadProcessId(a1, (LPDWORD)bstrString);
          a4->vt = 3;
          a4->lVal = (LONG)bstrString[0];
          return 0;
        case 0x7538u:
          v21 = 0;
          memset_0(&pgui, 0, sizeof(pgui));
          pgui.cbSize = 72;
          if ( GetGUIThreadInfo(0, &pgui) )
          {
            if ( pgui.hwndFocus == a1 || (v21 = 0, IsChild(a1, pgui.hwndFocus)) )
              v21 = 1;
          }
          v18 = v21 != 0;
          goto LABEL_33;
        case 0x7548u:
          IsWinFormsControl = BasicHwndUtils::IsWinFormsControl(a1);
          v17 = L"WinForm";
          if ( !IsWinFormsControl )
            v17 = L"Win32";
          v10 = (LONGLONG *)wil::make_bstr(bstrString, v17);
          break;
        case 0x7533u:
          IsWindowPatternWindow = BasicHwndUtils::IsWindowPatternWindow(a1);
          a4->vt = 3;
          a4->lVal = 50033 - (IsWindowPatternWindow != 0);
          return 0;
        default:
          if ( a2 != 30174 || !GetClassNameW(a1, ClassName, 128) )
            return 0;
          CharLowerW(ClassName);
          v18 = wcsstr(ClassName, L"dialog") != 0;
LABEL_33:
          a4->vt = 11;
          a4->iVal = -v18;
          return 0;
      }
      v11 = *v10;
      *v10 = 0;
      a4->llVal = v11;
      v12 = bstrString[0];
      if ( !bstrString[0] )
      {
LABEL_17:
        a4->vt = 8;
        return 0;
      }
    }
    SysFreeString(v12);
    goto LABEL_17;
  }
  return 0;
}

```

## disassembly

```asm
0x18009cc20  push    rbx
0x18009cc22  push    rsi
0x18009cc23  push    rdi
0x18009cc24  push    r12
0x18009cc26  push    r14
0x18009cc28  push    r15
0x18009cc2a  sub     rsp, 198h
0x18009cc31  mov     rax, cs:__security_cookie
0x18009cc38  xor     rax, rsp
0x18009cc3b  mov     [rsp+1C8h+var_48], rax
0x18009cc43  mov     rbx, r9
0x18009cc46  mov     r14, r8
0x18009cc49  mov     edi, edx
0x18009cc4b  mov     rsi, rcx
0x18009cc4e  xor     r12d, r12d
0x18009cc51  mov     rcx, rbx; pvarg
0x18009cc54  call    cs:__imp_VariantInit
0x18009cc5a  mov     r8d, edi
0x18009cc5d  lea     r15, dword_18030F244
0x18009cc64  mov     rdx, r15
0x18009cc67  lea     rcx, ?s_hwndProvidedProperties@BasicHwndUtils@@2V?$array@H$08@std@@B; ";u"
0x18009cc6e  call    __std_find_trivial_4
0x18009cc73  cmp     rax, r15
0x18009cc76  jz      loc_18009CD19
0x18009cc7c  cmp     edi, 753Bh
0x18009cc82  jz      loc_18009CD6C
0x18009cc88  cmp     edi, 753Ch
0x18009cc8e  jz      loc_18009CD1D
0x18009cc94  cmp     edi, 7535h
0x18009cc9a  jz      loc_18009CEAF
0x18009cca0  cmp     edi, 753Ah
0x18009cca6  jz      loc_18009CE94
0x18009ccac  cmp     edi, 7532h
0x18009ccb2  jz      loc_18009CF5D
0x18009ccb8  cmp     edi, 7538h
0x18009ccbe  jz      loc_18009CF11
0x18009ccc4  cmp     edi, 7548h
0x18009ccca  jz      loc_18009CE16
0x18009ccd0  cmp     edi, 7533h
0x18009ccd6  jnz     loc_18009CE41
0x18009ccdc  mov     rcx, rsi; HWND
0x18009ccdf  call    ?IsWindowPatternWindow@BasicHwndUtils@@SAHPEAUHWND__@@@Z; BasicHwndUtils::IsWindowPatternWindow(HWND__ *)
0x18009cce4  neg     eax
0x18009cce6  sbb     ecx, ecx
0x18009cce8  add     ecx, 0C371h
0x18009ccee  mov     word ptr [rbx], 3
0x18009ccf3  mov     [rbx+8], ecx
0x18009ccf6  xor     eax, eax
0x18009ccf8  mov     rcx, [rsp+1C8h+var_48]
0x18009cd00  xor     rcx, rsp; StackCookie
0x18009cd03  call    __security_check_cookie
0x18009cd08  add     rsp, 198h
0x18009cd0f  pop     r15
0x18009cd11  pop     r14
0x18009cd13  pop     r12
0x18009cd15  pop     rdi
0x18009cd16  pop     rsi
0x18009cd17  pop     rbx
0x18009cd18  retn
0x18009cd19  xor     eax, eax
0x18009cd1b  jmp     short loc_18009CCF8
0x18009cd1d  mov     r8d, 80h; nMaxCount
0x18009cd23  lea     rdx, [rsp+1C8h+ClassName]; lpClassName
0x18009cd2b  mov     rcx, rsi; hWnd
0x18009cd2e  call    cs:__imp_GetClassNameW
0x18009cd34  test    eax, eax
0x18009cd36  jz      short loc_18009CCF6
0x18009cd38  lea     rdx, [rsp+1C8h+ClassName]
0x18009cd40  lea     rcx, [rsp+1C8h+bstrString]
0x18009cd45  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18009cd4a  mov     rcx, [rax]
0x18009cd4d  mov     [rax], r12
0x18009cd50  mov     [rbx+8], rcx
0x18009cd54  mov     rcx, [rsp+1C8h+bstrString]; bstrString
0x18009cd59  test    rcx, rcx
0x18009cd5c  jnz     loc_18009CE0B
0x18009cd62  mov     edi, 8
0x18009cd67  mov     [rbx], di
0x18009cd6a  jmp     short loc_18009CCF6
0x18009cd6c  mov     rcx, rsi; hWnd
0x18009cd6f  call    ?IsWinFormsControl@BasicHwndUtils@@SAHPEAUHWND__@@@Z; BasicHwndUtils::IsWinFormsControl(HWND__ *)
0x18009cd74  test    eax, eax
0x18009cd76  jnz     loc_18009CEE2
0x18009cd7c  mov     edi, 8
0x18009cd81  cmp     [rbx], r12w
0x18009cd85  jnz     loc_18009CCF6
0x18009cd8b  mov     rcx, rsi; HWND
0x18009cd8e  call    ?IsTopLevelWindow@BasicHwndUtils@@SAHPEAUHWND__@@@Z; BasicHwndUtils::IsTopLevelWindow(HWND__ *)
0x18009cd93  test    eax, eax
0x18009cd95  jnz     loc_18009CCF6
0x18009cd9b  lea     edx, [rax-0Ch]; nIndex
0x18009cd9e  mov     rcx, rsi; hWnd
0x18009cda1  call    cs:__imp_GetWindowLongW
0x18009cda7  test    eax, eax
0x18009cda9  jz      loc_18009CCF6
0x18009cdaf  cmp     eax, 0FFFFFFFFh
0x18009cdb2  jz      loc_18009CCF6
0x18009cdb8  mov     r9d, eax
0x18009cdbb  lea     r8, aD; "%d"
0x18009cdc2  mov     edx, 20h ; ' '; unsigned __int64
0x18009cdc7  lea     rcx, [rsp+1C8h+pgui]; unsigned __int16 *
0x18009cdcc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009cdd1  test    eax, eax
0x18009cdd3  js      loc_18009CCF6
0x18009cdd9  lea     rdx, [rsp+1C8h+pgui]
0x18009cdde  lea     rcx, [rsp+1C8h+bstrString]
0x18009cde3  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18009cde8  mov     rcx, [rax]
0x18009cdeb  mov     [rax], r12
0x18009cdee  mov     [rbx+8], rcx
0x18009cdf2  mov     rcx, [rsp+1C8h+bstrString]; bstrString
0x18009cdf7  test    rcx, rcx
0x18009cdfa  jz      loc_18009CD67
0x18009ce00  call    cs:__imp_SysFreeString
0x18009ce06  jmp     loc_18009CD67
0x18009ce0b  call    cs:__imp_SysFreeString
0x18009ce11  jmp     loc_18009CD62
0x18009ce16  mov     rcx, rsi; hWnd
0x18009ce19  call    ?IsWinFormsControl@BasicHwndUtils@@SAHPEAUHWND__@@@Z; BasicHwndUtils::IsWinFormsControl(HWND__ *)
0x18009ce1e  lea     rcx, aWin32; "Win32"
0x18009ce25  lea     rdx, aWinform; "WinForm"
0x18009ce2c  test    eax, eax
0x18009ce2e  cmovz   rdx, rcx
0x18009ce32  lea     rcx, [rsp+1C8h+bstrString]
0x18009ce37  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18009ce3c  jmp     loc_18009CD4A
0x18009ce41  cmp     edi, 75DEh
0x18009ce47  jnz     loc_18009CCF6
0x18009ce4d  mov     r8d, 80h; nMaxCount
0x18009ce53  lea     rdx, [rsp+1C8h+ClassName]; lpClassName
0x18009ce5b  mov     rcx, rsi; hWnd
0x18009ce5e  call    cs:__imp_GetClassNameW
0x18009ce64  test    eax, eax
0x18009ce66  jz      loc_18009CCF6
0x18009ce6c  lea     rcx, [rsp+1C8h+ClassName]; lpsz
0x18009ce74  call    cs:__imp_CharLowerW
0x18009ce7a  lea     rdx, aDialog; "dialog"
0x18009ce81  lea     rcx, [rsp+1C8h+ClassName]; Str
0x18009ce89  call    cs:__imp_wcsstr
0x18009ce8f  neg     rax
0x18009ce92  jmp     short loc_18009CE9E
0x18009ce94  mov     rcx, rsi; hwnd
0x18009ce97  call    ?IsWindowReallyEnabled@BasicHwndUtils@@SAHPEAUHWND__@@@Z; BasicHwndUtils::IsWindowReallyEnabled(HWND__ *)
0x18009ce9c  neg     eax
0x18009ce9e  sbb     ax, ax
0x18009cea1  mov     word ptr [rbx], 0Bh
0x18009cea6  mov     [rbx+8], ax
0x18009ceaa  jmp     loc_18009CCF6
0x18009ceaf  lea     r8, [rbx+8]; unsigned __int16 **
0x18009ceb3  mov     rdx, r14; struct UIA_TIMEOUTDATA *
0x18009ceb6  mov     rcx, rsi; HWND
0x18009ceb9  call    ?GetWindowTextAsBstr@BasicHwndUtils@@SAJPEAUHWND__@@AEAUUIA_TIMEOUTDATA@@PEAPEAG@Z; BasicHwndUtils::GetWindowTextAsBstr(HWND__ *,UIA_TIMEOUTDATA &,ushort * *)
0x18009cebe  mov     rcx, [rsp+1C8h]; this
0x18009cec6  test    eax, eax
0x18009cec8  jns     loc_18009CD62
0x18009cece  mov     r9d, eax; char *
0x18009ced1  lea     r8, aOnecoreWindows_88; "onecore\\windows\\accessibletech\\commo"...
0x18009ced8  mov     edx, 273h; void *
0x18009cedd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009cee2  lea     r8, [rbx+8]; unsigned __int16 **
0x18009cee6  mov     rdx, r14; struct UIA_TIMEOUTDATA *
0x18009cee9  mov     rcx, rsi; HWND
0x18009ceec  call    ?GetWinFormsId@BasicHwndUtils@@SAJPEAUHWND__@@AEAUUIA_TIMEOUTDATA@@PEAPEAG@Z; BasicHwndUtils::GetWinFormsId(HWND__ *,UIA_TIMEOUTDATA &,ushort * *)
0x18009cef1  mov     rcx, [rsp+1C8h]; this
0x18009cef9  test    eax, eax
0x18009cefb  jns     short loc_18009CF46
0x18009cefd  mov     r9d, eax; char *
0x18009cf00  lea     r8, aOnecoreWindows_88; "onecore\\windows\\accessibletech\\commo"...
0x18009cf07  mov     edx, 24Fh; void *
0x18009cf0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009cf11  mov     edi, r12d
0x18009cf14  mov     r14d, 48h ; 'H'
0x18009cf1a  mov     r8d, r14d; Size
0x18009cf1d  xor     edx, edx; Val
0x18009cf1f  lea     rcx, [rsp+1C8h+pgui]; void *
0x18009cf24  call    memset_0
0x18009cf29  mov     [rsp+1C8h+pgui.cbSize], r14d
0x18009cf2e  lea     rdx, [rsp+1C8h+pgui]; pgui
0x18009cf33  xor     ecx, ecx; idThread
0x18009cf35  call    cs:__imp_GetGUIThreadInfo
0x18009cf3b  test    eax, eax
0x18009cf3d  jnz     short loc_18009CF81
0x18009cf3f  neg     edi
0x18009cf41  jmp     loc_18009CE9E
0x18009cf46  cmp     [rbx+8], r12
0x18009cf4a  jz      loc_18009CD7C
0x18009cf50  mov     edi, 8
0x18009cf55  mov     [rbx], di
0x18009cf58  jmp     loc_18009CD81
0x18009cf5d  mov     dword ptr [rsp+1C8h+bstrString], r12d
0x18009cf62  lea     rdx, [rsp+1C8h+bstrString]; lpdwProcessId
0x18009cf67  mov     rcx, rsi; hWnd
0x18009cf6a  call    cs:__imp_GetWindowThreadProcessId
0x18009cf70  mov     word ptr [rbx], 3
0x18009cf75  mov     eax, dword ptr [rsp+1C8h+bstrString]
0x18009cf79  mov     [rbx+8], eax
0x18009cf7c  jmp     loc_18009CCF6
0x18009cf81  mov     rdx, [rsp+1C8h+pgui.hwndFocus]; hWnd
0x18009cf86  cmp     rdx, rsi
0x18009cf89  jz      short loc_18009CF9B
0x18009cf8b  mov     rcx, rsi; hWndParent
0x18009cf8e  call    cs:__imp_IsChild
0x18009cf94  test    eax, eax
0x18009cf96  mov     edi, r12d
0x18009cf99  jz      short loc_18009CF3F
0x18009cf9b  mov     edi, 1
0x18009cfa0  jmp     short loc_18009CF3F
0x18009cfa2  mov     eax, dword ptr [rsp+1C8h+bstrString]
0x18009cfa6  jmp     loc_18009CCF8
```
