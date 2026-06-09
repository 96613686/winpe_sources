# SHMessageBoxCheckW

- ea: `0x180025310`
- end: `0x180025490`
- name: `SHMessageBoxCheckW`
- size: `384`
- prototype: `int __stdcall(HWND hwnd, LPCWSTR pszText, LPCWSTR pszCaption, UINT uType, int iDefault, LPCWSTR pszRegVal)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180024f50`

## callees

- `0x180012550`
- `0x180013066`
- `0x1800235ec`
- `0x180025310`
- `0x180035458`
- `0x180035e08`
- `0x180035e70`
- `0x1800362d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025467`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025467`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegSetUSValueW` at `0x18002542d`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegSetUSValueW` at `0x18002542d`
- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x180025362`
- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x180025362`
- `USER32!MessageBoxW` at `0x18002544c`
- `USER32!MessageBoxW` at `0x18002544c`

## pseudocode

```c
int __stdcall SHMessageBoxCheckW(
        HWND hwnd,
        LPCWSTR pszText,
        LPCWSTR pszCaption,
        UINT uType,
        int iDefault,
        LPCWSTR pszRegVal)
{
  const WCHAR *v10; // r13
  HRESULT v12; // ebx
  int *v13; // r8
  DWORD v14; // ecx
  TASKDIALOGCONFIG pTaskConfig; // [rsp+30h] [rbp-B9h] BYREF
  int pnButton; // [rsp+D0h] [rbp-19h] BYREF
  BOOL pfVerificationFlagChecked; // [rsp+D4h] [rbp-15h] BYREF
  ULONG_PTR ulCookie; // [rsp+D8h] [rbp-11h] BYREF

  pnButton = -1;
  v10 = GetMsgBoxCheckRegPath();
  if ( !SHRegGetBoolValueFromHKCUHKLM(v10, pszRegVal, 1) )
    return iDefault;
  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  pTaskConfig.hInstance = g_hinst;
  pTaskConfig.cbSize = 160;
  pTaskConfig.hwndParent = hwnd;
  pTaskConfig.pszContent = pszText;
  pTaskConfig.pszWindowTitle = pszCaption;
  pTaskConfig.pszVerificationText = (PCWSTR)4867;
  v12 = ConfigureDialogWithMessageBoxFlags(uType, &pTaskConfig);
  if ( v12 < 0 )
    goto LABEL_11;
  ulCookie = 0;
  SHActivateContext(&ulCookie);
  pfVerificationFlagChecked = 0;
  v12 = TaskDialogIndirect(&pTaskConfig, &pnButton, v13, &pfVerificationFlagChecked);
  if ( v12 >= 0 )
  {
    if ( (uType & 0xF) == 0 && pnButton == 2 )
      pnButton = 1;
    if ( pfVerificationFlagChecked )
      SHRegSetUSValueW(v10, pszRegVal, 1u, L"NO", 6u, 1u);
  }
  SHDeactivateContext(ulCookie);
  if ( v12 < 0 )
  {
LABEL_11:
    pnButton = MessageBoxW(hwnd, pszText, pszCaption, uType);
    v14 = (unsigned __int16)v12;
    if ( (v12 & 0x1FFF0000) != 0x70000 )
      v14 = v12;
    SetLastError(v14);
  }
  return pnButton;
}

```

## disassembly

```asm
0x180025310  push    rbp
0x180025312  push    rbx
0x180025313  push    rsi
0x180025314  push    rdi
0x180025315  push    r12
0x180025317  push    r13
0x180025319  push    r14
0x18002531b  push    r15
0x18002531d  lea     rbp, [rsp-0Fh]
0x180025322  sub     rsp, 0F8h
0x180025329  mov     rax, cs:__security_cookie
0x180025330  xor     rax, rsp
0x180025333  mov     [rbp+47h+var_50], rax
0x180025337  mov     r12, [rbp+47h+pszRegVal]
0x18002533b  mov     edi, r9d
0x18002533e  mov     r15, r8
0x180025341  mov     [rbp+47h+pnButton], 0FFFFFFFFh
0x180025348  mov     r14, rdx
0x18002534b  mov     rsi, rcx
0x18002534e  call    ?GetMsgBoxCheckRegPath@@YAPEBGXZ; GetMsgBoxCheckRegPath(void)
0x180025353  mov     r8d, 1; fDefault
0x180025359  mov     rdx, r12; pszValue
0x18002535c  mov     rcx, rax; pszKey
0x18002535f  mov     r13, rax
0x180025362  call    cs:__imp_SHRegGetBoolValueFromHKCUHKLM
0x180025368  test    eax, eax
0x18002536a  jnz     short loc_180025374
0x18002536c  mov     eax, [rbp+47h+iDefault]
0x18002536f  jmp     loc_180025470
0x180025374  mov     ebx, 0A0h
0x180025379  lea     rcx, [rsp+130h+pTaskConfig]; void *
0x18002537e  mov     r8d, ebx; Size
0x180025381  xor     edx, edx; Val
0x180025383  call    memset_0
0x180025388  mov     rax, cs:g_hinst
0x18002538f  lea     rdx, [rsp+130h+pTaskConfig]; struct _TASKDIALOGCONFIG *
0x180025394  mov     ecx, edi; unsigned int
0x180025396  mov     [rsp+130h+pTaskConfig.hInstance], rax
0x18002539b  mov     [rsp+130h+pTaskConfig.cbSize], ebx
0x18002539f  mov     [rsp+130h+pTaskConfig.hwndParent], rsi
0x1800253a4  mov     [rsp+130h+pTaskConfig.pszContent], r14
0x1800253a9  mov     [rsp+130h+pTaskConfig.pszWindowTitle], r15
0x1800253ae  mov     [rbp+47h+pTaskConfig.pszVerificationText], 1303h
0x1800253b6  call    ?ConfigureDialogWithMessageBoxFlags@@YAJKPEAU_TASKDIALOGCONFIG@@@Z; ConfigureDialogWithMessageBoxFlags(ulong,_TASKDIALOGCONFIG *)
0x1800253bb  mov     ebx, eax
0x1800253bd  test    eax, eax
0x1800253bf  js      short loc_180025440
0x1800253c1  lea     rcx, [rbp+47h+ulCookie]
0x1800253c5  mov     [rbp+47h+ulCookie], 0
0x1800253cd  call    SHActivateContext
0x1800253d2  lea     r9, [rbp+47h+pfVerificationFlagChecked]; pfVerificationFlagChecked
0x1800253d6  mov     [rbp+47h+pfVerificationFlagChecked], 0
0x1800253dd  lea     rdx, [rbp+47h+pnButton]; pnButton
0x1800253e1  lea     rcx, [rsp+130h+pTaskConfig]; pTaskConfig
0x1800253e6  call    TaskDialogIndirect
0x1800253eb  mov     ebx, eax
0x1800253ed  test    eax, eax
0x1800253ef  js      short loc_180025433
0x1800253f1  test    dil, 0Fh
0x1800253f5  jnz     short loc_180025404
0x1800253f7  cmp     [rbp+47h+pnButton], 2
0x1800253fb  jnz     short loc_180025404
0x1800253fd  mov     [rbp+47h+pnButton], 1
0x180025404  cmp     [rbp+47h+pfVerificationFlagChecked], 0
0x180025408  jz      short loc_180025433
0x18002540a  mov     [rsp+130h+dwFlags], 1; dwFlags
0x180025412  lea     r9, aNo; "NO"
0x180025419  mov     r8d, 1; dwType
0x18002541f  mov     [rsp+130h+cbData], 6; cbData
0x180025427  mov     rdx, r12; pwzValue
0x18002542a  mov     rcx, r13; pwzSubKey
0x18002542d  call    cs:__imp_SHRegSetUSValueW
0x180025433  mov     rcx, [rbp+47h+ulCookie]; ulCookie
0x180025437  call    SHDeactivateContext
0x18002543c  test    ebx, ebx
0x18002543e  jns     short loc_18002546D
0x180025440  mov     r9d, edi; uType
0x180025443  mov     r8, r15; lpCaption
0x180025446  mov     rdx, r14; lpText
0x180025449  mov     rcx, rsi; hWnd
0x18002544c  call    cs:__imp_MessageBoxW
0x180025452  mov     [rbp+47h+pnButton], eax
0x180025455  mov     eax, ebx
0x180025457  and     eax, 1FFF0000h
0x18002545c  movzx   ecx, bx
0x18002545f  cmp     eax, 70000h
0x180025464  cmovnz  ecx, ebx; dwErrCode
0x180025467  call    cs:__imp_SetLastError
0x18002546d  mov     eax, [rbp+47h+pnButton]
0x180025470  mov     rcx, [rbp+47h+var_50]
0x180025474  xor     rcx, rsp; StackCookie
0x180025477  call    __security_check_cookie
0x18002547c  add     rsp, 0F8h
0x180025483  pop     r15
0x180025485  pop     r14
0x180025487  pop     r13
0x180025489  pop     r12
0x18002548b  pop     rdi
0x18002548c  pop     rsi
0x18002548d  pop     rbx
0x18002548e  pop     rbp
0x18002548f  retn
```
