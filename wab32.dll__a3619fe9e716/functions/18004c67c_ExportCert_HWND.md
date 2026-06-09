# ExportCert(HWND__ *)

- ea: `0x18004c67c`
- end: `0x18004c8c5`
- name: `?ExportCert@@YAHPEAUHWND__@@@Z`
- size: `585`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056560`

## callees

- `0x18000597c`
- `0x18004c67c`
- `0x180069e24`
- `0x18008ebb0`
- `0x18008ec20`
- `0x18008f484`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `SHLWAPI!PathAddExtensionW` at `0x18004c82f`
- `SHLWAPI!PathAddExtensionW` at `0x18004c82f`
- `USER32!LoadStringW` at `0x18004c719`
- `USER32!LoadStringW` at `0x18004c735`
- `USER32!LoadStringW` at `0x18004c719`
- `USER32!LoadStringW` at `0x18004c735`
- `USER32!SendMessageW` at `0x18004c749`
- `USER32!SendMessageW` at `0x18004c778`
- `USER32!SendMessageW` at `0x18004c85d`
- `USER32!SendMessageW` at `0x18004c878`
- `USER32!SendMessageW` at `0x18004c749`
- `USER32!SendMessageW` at `0x18004c778`
- `USER32!SendMessageW` at `0x18004c85d`
- `USER32!SendMessageW` at `0x18004c878`
- `USER32!GetDlgItem` at `0x18004c6e7`
- `USER32!GetDlgItem` at `0x18004c6e7`

## pseudocode

```c
__int64 __fastcall ExportCert(HWND hWnd)
{
  unsigned int v2; // esi
  HWND DlgItem; // rdi
  int v4; // edx
  int v5; // ebx
  int v6; // eax
  ULONG_PTR ulCookie[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  HWND v10; // [rsp+48h] [rbp-B8h]
  HINSTANCE v11; // [rsp+50h] [rbp-B0h]
  WCHAR *v12; // [rsp+58h] [rbp-A8h]
  LPWSTR pszPath; // [rsp+70h] [rbp-90h]
  int v14; // [rsp+78h] [rbp-88h]
  WCHAR *v15; // [rsp+98h] [rbp-68h]
  int v16; // [rsp+A0h] [rbp-60h]
  int lParam; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD lParam_4[9]; // [rsp+E4h] [rbp-1Ch] BYREF
  __int64 v19; // [rsp+108h] [rbp+8h]
  WCHAR v20[200]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v21[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR Buffer[520]; // [rsp+4E0h] [rbp+3E0h] BYREF

  v2 = 0;
  memset_0(v20, 0, sizeof(v20));
  memset_0(v21, 0, 0x208u);
  memset_0(Buffer, 0, sizeof(Buffer));
  DlgItem = GetDlgItem(hWnd, 2475);
  memset_0(&v9, 0, 0x98u);
  LoadStringW(hinstMapiX, 0x3Du, Buffer, 520);
  LoadStringW(hinstMapiX, 0x108Fu, v20, 200);
  if ( (unsigned int)SendMessageW(DlgItem, 0x1032u, 0, 0) > 1 )
  {
    v4 = 21;
LABEL_3:
    ShowMessageBox(hWnd, v4, 48);
    return v2;
  }
  if ( !(unsigned int)SendMessageW(DlgItem, 0x1032u, 0, 0) )
  {
    v4 = 22;
    goto LABEL_3;
  }
  v11 = hinstMapiX;
  v9 = 152;
  v12 = Buffer;
  pszPath = v21;
  v15 = v20;
  v10 = hWnd;
  v14 = 260;
  v16 = 2054;
  ulCookie[0] = 0;
  GetProcFromComDlg((HMODULE *)&qword_1800ACF90, "GetSaveFileNameW");
  if ( qword_1800ACF90 )
  {
    SHActivateContext(ulCookie);
    v5 = ((__int64 (__fastcall *)(int *))qword_1800ACF90)(&v9);
    SHDeactivateContext(ulCookie[0]);
    if ( v5 )
    {
      PathAddExtensionW(pszPath, L".cer");
      memset_0(lParam_4, 0, 0x54u);
      lParam = 4;
      v6 = SendMessageW(DlgItem, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
      lParam_4[1] = 0;
      lParam_4[0] = v6;
      if ( (unsigned int)SendMessageW(DlgItem, 0x104Bu, 0, (LPARAM)&lParam) )
      {
        HrExportCertToFile(v21, *(const struct _CERT_CONTEXT **)(*(_QWORD *)v19 + 40LL), 0, 0, 0);
        return 1;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18004c67c  push    rbp
0x18004c67e  push    rbx
0x18004c67f  push    rsi
0x18004c680  push    rdi
0x18004c681  lea     rbp, [rsp-808h]
0x18004c689  sub     rsp, 908h
0x18004c690  mov     rax, cs:__security_cookie
0x18004c697  xor     rax, rsp
0x18004c69a  mov     [rbp+820h+var_30], rax
0x18004c6a1  mov     rbx, rcx
0x18004c6a4  xor     edx, edx; Val
0x18004c6a6  lea     rcx, [rbp+820h+var_7E0]; void *
0x18004c6aa  mov     r8d, 190h; Size
0x18004c6b0  xor     esi, esi
0x18004c6b2  call    memset_0
0x18004c6b7  xor     edx, edx; Val
0x18004c6b9  lea     rcx, [rbp+820h+var_650]; void *
0x18004c6c0  mov     r8d, 208h; Size
0x18004c6c6  call    memset_0
0x18004c6cb  xor     edx, edx; Val
0x18004c6cd  lea     rcx, [rbp+820h+Buffer]; void *
0x18004c6d4  mov     r8d, 410h; Size
0x18004c6da  call    memset_0
0x18004c6df  mov     edx, 9ABh; nIDDlgItem
0x18004c6e4  mov     rcx, rbx; hDlg
0x18004c6e7  call    cs:__imp_GetDlgItem
0x18004c6ed  xor     edx, edx; Val
0x18004c6ef  lea     rcx, [rsp+920h+var_8E0]; void *
0x18004c6f4  mov     r8d, 98h; Size
0x18004c6fa  mov     rdi, rax
0x18004c6fd  call    memset_0
0x18004c702  mov     rcx, cs:hinstMapiX; hInstance
0x18004c709  lea     r8, [rbp+820h+Buffer]; lpBuffer
0x18004c710  mov     r9d, 208h; cchBufferMax
0x18004c716  lea     edx, [rsi+3Dh]; uID
0x18004c719  call    cs:__imp_LoadStringW
0x18004c71f  mov     rcx, cs:hinstMapiX; hInstance
0x18004c726  lea     r8, [rbp+820h+var_7E0]; lpBuffer
0x18004c72a  mov     r9d, 0C8h; cchBufferMax
0x18004c730  mov     edx, 108Fh; uID
0x18004c735  call    cs:__imp_LoadStringW
0x18004c73b  xor     r9d, r9d; lParam
0x18004c73e  xor     r8d, r8d; wParam
0x18004c741  mov     edx, 1032h; Msg
0x18004c746  mov     rcx, rdi; hWnd
0x18004c749  call    cs:__imp_SendMessageW
0x18004c74f  cmp     eax, 1
0x18004c752  jbe     short loc_18004C76A
0x18004c754  lea     edx, [rsi+15h]; int
0x18004c757  mov     r8d, 30h ; '0'; int
0x18004c75d  mov     rcx, rbx; hWnd
0x18004c760  call    ?ShowMessageBox@@YAHPEAUHWND__@@HH@Z; ShowMessageBox(HWND__ *,int,int)
0x18004c765  jmp     loc_18004C8A8
0x18004c76a  xor     r9d, r9d; lParam
0x18004c76d  xor     r8d, r8d; wParam
0x18004c770  mov     edx, 1032h; Msg
0x18004c775  mov     rcx, rdi; hWnd
0x18004c778  call    cs:__imp_SendMessageW
0x18004c77e  test    eax, eax
0x18004c780  jnz     short loc_18004C787
0x18004c782  lea     edx, [rax+16h]
0x18004c785  jmp     short loc_18004C757
0x18004c787  mov     rax, cs:hinstMapiX
0x18004c78e  lea     rdx, aGetsavefilenam; "GetSaveFileNameW"
0x18004c795  mov     [rsp+920h+var_8D0], rax
0x18004c79a  lea     rcx, qword_1800ACF90
0x18004c7a1  lea     rax, [rbp+820h+Buffer]
0x18004c7a8  mov     [rsp+920h+var_8E0], 98h
0x18004c7b0  mov     [rsp+920h+var_8C8], rax
0x18004c7b5  lea     rax, [rbp+820h+var_650]
0x18004c7bc  mov     [rsp+920h+pszPath], rax
0x18004c7c1  lea     rax, [rbp+820h+var_7E0]
0x18004c7c5  mov     [rbp+820h+var_888], rax
0x18004c7c9  mov     [rsp+920h+var_8D8], rbx
0x18004c7ce  mov     [rsp+920h+var_8A8], 104h
0x18004c7d6  mov     [rbp+820h+var_880], 806h
0x18004c7dd  mov     [rsp+920h+ulCookie], rsi
0x18004c7e2  call    _GetProcFromComDlg
0x18004c7e7  cmp     cs:qword_1800ACF90, rsi
0x18004c7ee  jz      loc_18004C8A8
0x18004c7f4  lea     rcx, [rsp+920h+ulCookie]
0x18004c7f9  call    SHActivateContext
0x18004c7fe  mov     rax, cs:qword_1800ACF90
0x18004c805  lea     rcx, [rsp+920h+var_8E0]
0x18004c80a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c80f  mov     rcx, [rsp+920h+ulCookie]; ulCookie
0x18004c814  mov     ebx, eax
0x18004c816  call    SHDeactivateContext
0x18004c81b  test    ebx, ebx
0x18004c81d  jz      loc_18004C8A8
0x18004c823  mov     rcx, [rsp+920h+pszPath]; pszPath
0x18004c828  lea     rdx, aCer; ".cer"
0x18004c82f  call    cs:__imp_PathAddExtensionW
0x18004c835  xor     edx, edx; Val
0x18004c837  lea     rcx, [rbp+820h+lParam+4]; void *
0x18004c83b  lea     r8d, [rdx+54h]; Size
0x18004c83f  call    memset_0
0x18004c844  mov     r9d, 2; lParam
0x18004c84a  mov     dword ptr [rbp+820h+lParam], 4
0x18004c851  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18004c855  mov     edx, 100Ch; Msg
0x18004c85a  mov     rcx, rdi; hWnd
0x18004c85d  call    cs:__imp_SendMessageW
0x18004c863  lea     r9, [rbp+820h+lParam]; lParam
0x18004c867  mov     [rbp+820h+var_838], esi
0x18004c86a  xor     r8d, r8d; wParam
0x18004c86d  mov     dword ptr [rbp+820h+lParam+4], eax
0x18004c870  mov     edx, 104Bh; Msg
0x18004c875  mov     rcx, rdi; hWnd
0x18004c878  call    cs:__imp_SendMessageW
0x18004c87e  test    eax, eax
0x18004c880  jz      short loc_18004C8A8
0x18004c882  mov     rax, [rbp+820h+var_818]
0x18004c886  lea     rcx, [rbp+820h+var_650]; unsigned __int16 *
0x18004c88d  xor     r9d, r9d; unsigned int *
0x18004c890  mov     [rsp+920h+var_900], esi; int
0x18004c894  xor     r8d, r8d; unsigned __int8 **
0x18004c897  mov     rdx, [rax]
0x18004c89a  mov     rdx, [rdx+28h]; struct _CERT_CONTEXT *
0x18004c89e  call    ?HrExportCertToFile@@YAJPEAGPEBU_CERT_CONTEXT@@PEAPEAEPEAKH@Z; HrExportCertToFile(ushort *,_CERT_CONTEXT const *,uchar * *,ulong *,int)
0x18004c8a3  mov     esi, 1
0x18004c8a8  mov     eax, esi
0x18004c8aa  mov     rcx, [rbp+820h+var_30]
0x18004c8b1  xor     rcx, rsp; StackCookie
0x18004c8b4  call    __security_check_cookie
0x18004c8b9  add     rsp, 908h
0x18004c8c0  pop     rdi
0x18004c8c1  pop     rsi
0x18004c8c2  pop     rbx
0x18004c8c3  pop     rbp
0x18004c8c4  retn
```
