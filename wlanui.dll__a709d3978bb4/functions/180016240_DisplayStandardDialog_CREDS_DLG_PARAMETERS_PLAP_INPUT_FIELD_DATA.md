# DisplayStandardDialog(_CREDS_DLG_PARAMETERS *,_PLAP_INPUT_FIELD_DATA *)

- ea: `0x180016240`
- end: `0x1800164be`
- name: `?DisplayStandardDialog@@YAKPEAU_CREDS_DLG_PARAMETERS@@PEAU_PLAP_INPUT_FIELD_DATA@@@Z`
- size: `638`
- prototype: `__int64 __fastcall(struct _CREDS_DLG_PARAMETERS *, struct _PLAP_INPUT_FIELD_DATA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180016b60`

## callees

- `0x180001e26`
- `0x180016240`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001632b`
- `KERNEL32!GetLastError` at `0x18001632b`
- `KERNEL32!HeapAlloc` at `0x180016351`
- `KERNEL32!HeapAlloc` at `0x18001636e`
- `KERNEL32!HeapAlloc` at `0x180016351`
- `KERNEL32!HeapAlloc` at `0x18001636e`
- `KERNEL32!GetProcessHeap` at `0x180016340`
- `KERNEL32!GetProcessHeap` at `0x180016360`
- `KERNEL32!GetProcessHeap` at `0x180016461`
- `KERNEL32!GetProcessHeap` at `0x18001647a`
- `KERNEL32!GetProcessHeap` at `0x180016340`
- `KERNEL32!GetProcessHeap` at `0x180016360`
- `KERNEL32!GetProcessHeap` at `0x180016461`
- `KERNEL32!GetProcessHeap` at `0x18001647a`
- `KERNEL32!HeapFree` at `0x18001646f`
- `KERNEL32!HeapFree` at `0x180016488`
- `KERNEL32!HeapFree` at `0x18001646f`
- `KERNEL32!HeapFree` at `0x180016488`
- `ole32!CoTaskMemFree` at `0x1800164a3`
- `ole32!CoTaskMemFree` at `0x1800164a3`
- `credui!CredUnPackAuthenticationBufferW` at `0x18001631d`
- `credui!CredUnPackAuthenticationBufferW` at `0x1800163b7`
- `credui!CredUnPackAuthenticationBufferW` at `0x18001631d`
- `credui!CredUnPackAuthenticationBufferW` at `0x1800163b7`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x1800162c9`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x1800162c9`

## pseudocode

```c
__int64 __fastcall DisplayStandardDialog(struct _CREDS_DLG_PARAMETERS *a1, struct _PLAP_INPUT_FIELD_DATA *a2)
{
  DWORD v4; // eax
  unsigned int v5; // r12d
  PVOID v6; // rcx
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  void *v9; // rdi
  SIZE_T v10; // rbx
  HANDLE v11; // rax
  WCHAR *v12; // rax
  WCHAR *v13; // rsi
  size_t v14; // rbx
  size_t v15; // r8
  char *v16; // rcx
  size_t v17; // r8
  HANDLE v18; // rax
  HANDLE v19; // rax
  ULONG pulAuthPackage; // [rsp+50h] [rbp-19h] BYREF
  PVOID pAuthBuffer; // [rsp+58h] [rbp-11h] BYREF
  _CREDUI_INFOW pUiInfo; // [rsp+60h] [rbp-9h] BYREF
  DWORD pcchMaxUserName; // [rsp+D0h] [rbp+67h] BYREF
  DWORD pcchMaxPassword; // [rsp+E0h] [rbp+77h] BYREF
  ULONG cbAuthBuffer; // [rsp+E8h] [rbp+7Fh] BYREF

  pUiInfo.hwndParent = (HWND)*((_QWORD *)a1 + 7);
  pUiInfo.pszMessageText = (PCWSTR)*((_QWORD *)a1 + 4);
  pUiInfo.pszCaptionText = (PCWSTR)*((_QWORD *)a1 + 3);
  pcchMaxUserName = 0;
  pcchMaxPassword = 0;
  *(_QWORD *)&pUiInfo.cbSize = 40;
  pulAuthPackage = 0;
  pAuthBuffer = 0;
  cbAuthBuffer = 0;
  pUiInfo.hbmBanner = 0;
  v4 = CredUIPromptForWindowsCredentialsW(&pUiInfo, 0, &pulAuthPackage, 0, 0, &pAuthBuffer, &cbAuthBuffer, 0, 1u);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 == 1223 )
      *((_DWORD *)a1 + 4) = 1;
    goto LABEL_29;
  }
  v6 = pAuthBuffer;
  if ( !pAuthBuffer )
    return v5;
  if ( cbAuthBuffer )
  {
    if ( CredUnPackAuthenticationBufferW(0, pAuthBuffer, cbAuthBuffer, 0, &pcchMaxUserName, 0, 0, 0, &pcchMaxPassword)
      || GetLastError() != 122 )
    {
LABEL_29:
      v6 = pAuthBuffer;
      goto LABEL_30;
    }
    v7 = 2LL * pcchMaxUserName;
    ProcessHeap = GetProcessHeap();
    v9 = HeapAlloc(ProcessHeap, 8u, v7);
    v10 = 2LL * pcchMaxPassword;
    v11 = GetProcessHeap();
    v12 = (WCHAR *)HeapAlloc(v11, 8u, v10);
    v13 = v12;
    if ( v9 && v12 )
    {
      if ( CredUnPackAuthenticationBufferW(
             0,
             pAuthBuffer,
             cbAuthBuffer,
             (LPWSTR)v9,
             &pcchMaxUserName,
             0,
             0,
             v12,
             &pcchMaxPassword) )
      {
        v14 = 2048;
        if ( (*(_DWORD *)a2 & 0xFFFFFFFD) != 0 )
        {
          if ( pcchMaxUserName >= 0x400 )
            v15 = 2048;
          else
            v15 = 2LL * pcchMaxUserName;
          memcpy_0((char *)a2 + 3104, v9, v15);
          if ( pcchMaxPassword < 0x400 )
            v14 = 2LL * pcchMaxPassword;
          v16 = (char *)a2 + 524;
        }
        else
        {
          if ( pcchMaxUserName >= 0x400 )
            v17 = 2048;
          else
            v17 = 2LL * pcchMaxUserName;
          memcpy_0((char *)a2 + 524, v9, v17);
          if ( pcchMaxPassword < 0x400 )
            v14 = 2LL * pcchMaxPassword;
          v16 = (char *)a2 + 3104;
        }
        memcpy_0(v16, v13, v14);
      }
    }
    else
    {
      v5 = 14;
      if ( !v9 )
        goto LABEL_25;
    }
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v9);
LABEL_25:
    if ( v13 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v13);
    }
    goto LABEL_29;
  }
LABEL_30:
  if ( v6 )
    CoTaskMemFree(v6);
  return v5;
}

```

## disassembly

```asm
0x180016240  push    rbp
0x180016242  push    rbx
0x180016243  push    rsi
0x180016244  push    rdi
0x180016245  push    r12
0x180016247  push    r13
0x180016249  push    r15
0x18001624b  lea     rbp, [rsp-27h]
0x180016250  sub     rsp, 90h
0x180016257  mov     rax, [rcx+38h]
0x18001625b  lea     r8, [rbp+57h+pulAuthPackage]; pulAuthPackage
0x18001625f  xor     r13d, r13d
0x180016262  mov     [rbp+57h+pUiInfo.hwndParent], rax
0x180016266  mov     rax, [rcx+20h]
0x18001626a  mov     r15, rdx
0x18001626d  mov     [rbp+57h+pUiInfo.pszMessageText], rax
0x180016271  mov     rbx, rcx
0x180016274  mov     rax, [rcx+18h]
0x180016278  xor     r9d, r9d; pvInAuthBuffer
0x18001627b  mov     [rbp+57h+pUiInfo.pszCaptionText], rax
0x18001627f  lea     edi, [r13+1]
0x180016283  mov     [rsp+0C0h+dwFlags], edi; dwFlags
0x180016287  lea     rax, [rbp+57h+cbAuthBuffer]
0x18001628b  mov     [rsp+0C0h+pfSave], r13; pfSave
0x180016290  lea     rcx, [rbp+57h+pUiInfo]; pUiInfo
0x180016294  mov     [rsp+0C0h+pulOutAuthBufferSize], rax; pulOutAuthBufferSize
0x180016299  xor     edx, edx; dwAuthError
0x18001629b  lea     rax, [rbp+57h+pAuthBuffer]
0x18001629f  mov     [rbp+57h+pcchMaxUserName], r13d
0x1800162a3  mov     [rsp+0C0h+ppvOutAuthBuffer], rax; ppvOutAuthBuffer
0x1800162a8  mov     [rsp+0C0h+ulInAuthBufferSize], r13d; ulInAuthBufferSize
0x1800162ad  mov     [rbp+57h+pcchMaxPassword], r13d
0x1800162b1  mov     qword ptr [rbp+57h+pUiInfo.cbSize], 28h ; '('
0x1800162b9  mov     [rbp+57h+pulAuthPackage], r13d
0x1800162bd  mov     [rbp+57h+pAuthBuffer], r13
0x1800162c1  mov     [rbp+57h+cbAuthBuffer], r13d
0x1800162c5  mov     [rbp+57h+pUiInfo.hbmBanner], r13
0x1800162c9  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x1800162cf  mov     r12d, eax
0x1800162d2  test    eax, eax
0x1800162d4  jnz     loc_180016490
0x1800162da  mov     rcx, [rbp+57h+pAuthBuffer]
0x1800162de  test    rcx, rcx
0x1800162e1  jz      loc_1800164A9
0x1800162e7  mov     r8d, [rbp+57h+cbAuthBuffer]; cbAuthBuffer
0x1800162eb  test    r8d, r8d
0x1800162ee  jz      loc_18001649E
0x1800162f4  lea     rax, [rbp+57h+pcchMaxPassword]
0x1800162f8  mov     rdx, rcx; pAuthBuffer
0x1800162fb  mov     qword ptr [rsp+0C0h+dwFlags], rax; pcchMaxPassword
0x180016300  xor     r9d, r9d; pszUserName
0x180016303  mov     [rsp+0C0h+pfSave], r13; pszPassword
0x180016308  lea     rax, [rbp+57h+pcchMaxUserName]
0x18001630c  mov     [rsp+0C0h+pulOutAuthBufferSize], r13; pcchMaxDomainName
0x180016311  xor     ecx, ecx; dwFlags
0x180016313  mov     [rsp+0C0h+ppvOutAuthBuffer], r13; pszDomainName
0x180016318  mov     qword ptr [rsp+0C0h+ulInAuthBufferSize], rax; pcchMaxUserName
0x18001631d  call    cs:__imp_CredUnPackAuthenticationBufferW
0x180016323  test    eax, eax
0x180016325  jnz     loc_18001649A
0x18001632b  call    cs:__imp_GetLastError
0x180016331  cmp     eax, 7Ah ; 'z'
0x180016334  jnz     loc_18001649A
0x18001633a  mov     ebx, [rbp+57h+pcchMaxUserName]
0x18001633d  add     rbx, rbx
0x180016340  call    cs:__imp_GetProcessHeap
0x180016346  lea     esi, [rdi+7]
0x180016349  mov     r8, rbx; dwBytes
0x18001634c  mov     edx, esi; dwFlags
0x18001634e  mov     rcx, rax; hHeap
0x180016351  call    cs:__imp_HeapAlloc
0x180016357  mov     ebx, [rbp+57h+pcchMaxPassword]
0x18001635a  mov     rdi, rax
0x18001635d  add     rbx, rbx
0x180016360  call    cs:__imp_GetProcessHeap
0x180016366  mov     r8, rbx; dwBytes
0x180016369  mov     edx, esi; dwFlags
0x18001636b  mov     rcx, rax; hHeap
0x18001636e  call    cs:__imp_HeapAlloc
0x180016374  mov     rsi, rax
0x180016377  test    rdi, rdi
0x18001637a  jz      loc_180016456
0x180016380  test    rax, rax
0x180016383  jz      loc_180016456
0x180016389  mov     r8d, [rbp+57h+cbAuthBuffer]; cbAuthBuffer
0x18001638d  lea     rax, [rbp+57h+pcchMaxPassword]
0x180016391  mov     rdx, [rbp+57h+pAuthBuffer]; pAuthBuffer
0x180016395  mov     r9, rdi; pszUserName
0x180016398  mov     qword ptr [rsp+0C0h+dwFlags], rax; pcchMaxPassword
0x18001639d  xor     ecx, ecx; dwFlags
0x18001639f  mov     [rsp+0C0h+pfSave], rsi; pszPassword
0x1800163a4  lea     rax, [rbp+57h+pcchMaxUserName]
0x1800163a8  mov     [rsp+0C0h+pulOutAuthBufferSize], r13; pcchMaxDomainName
0x1800163ad  mov     [rsp+0C0h+ppvOutAuthBuffer], r13; pszDomainName
0x1800163b2  mov     qword ptr [rsp+0C0h+ulInAuthBufferSize], rax; pcchMaxUserName
0x1800163b7  call    cs:__imp_CredUnPackAuthenticationBufferW
0x1800163bd  test    eax, eax
0x1800163bf  jz      loc_180016461
0x1800163c5  test    dword ptr [r15], 0FFFFFFFDh
0x1800163cc  mov     ebx, 800h
0x1800163d1  jz      short loc_18001640F
0x1800163d3  cmp     [rbp+57h+pcchMaxUserName], 400h
0x1800163da  jnb     short loc_1800163E5
0x1800163dc  mov     r8d, [rbp+57h+pcchMaxUserName]
0x1800163e0  add     r8, r8
0x1800163e3  jmp     short loc_1800163E8
0x1800163e5  mov     r8, rbx; Size
0x1800163e8  lea     rcx, [r15+0C20h]; void *
0x1800163ef  mov     rdx, rdi; Src
0x1800163f2  call    memcpy_0
0x1800163f7  cmp     [rbp+57h+pcchMaxPassword], 400h
0x1800163fe  jnb     short loc_180016406
0x180016400  mov     ebx, [rbp+57h+pcchMaxPassword]
0x180016403  add     rbx, rbx
0x180016406  lea     rcx, [r15+20Ch]
0x18001640d  jmp     short loc_180016449
0x18001640f  cmp     [rbp+57h+pcchMaxUserName], 400h
0x180016416  jnb     short loc_180016421
0x180016418  mov     r8d, [rbp+57h+pcchMaxUserName]
0x18001641c  add     r8, r8
0x18001641f  jmp     short loc_180016424
0x180016421  mov     r8, rbx; Size
0x180016424  lea     rcx, [r15+20Ch]; void *
0x18001642b  mov     rdx, rdi; Src
0x18001642e  call    memcpy_0
0x180016433  cmp     [rbp+57h+pcchMaxPassword], 400h
0x18001643a  jnb     short loc_180016442
0x18001643c  mov     ebx, [rbp+57h+pcchMaxPassword]
0x18001643f  add     rbx, rbx
0x180016442  lea     rcx, [r15+0C20h]; void *
0x180016449  mov     r8, rbx; Size
0x18001644c  mov     rdx, rsi; Src
0x18001644f  call    memcpy_0
0x180016454  jmp     short loc_180016461
0x180016456  mov     r12d, 0Eh
0x18001645c  test    rdi, rdi
0x18001645f  jz      short loc_180016475
0x180016461  call    cs:__imp_GetProcessHeap
0x180016467  mov     r8, rdi; lpMem
0x18001646a  xor     edx, edx; dwFlags
0x18001646c  mov     rcx, rax; hHeap
0x18001646f  call    cs:__imp_HeapFree
0x180016475  test    rsi, rsi
0x180016478  jz      short loc_18001649A
0x18001647a  call    cs:__imp_GetProcessHeap
0x180016480  mov     r8, rsi; lpMem
0x180016483  xor     edx, edx; dwFlags
0x180016485  mov     rcx, rax; hHeap
0x180016488  call    cs:__imp_HeapFree
0x18001648e  jmp     short loc_18001649A
0x180016490  cmp     eax, 4C7h
0x180016495  jnz     short loc_18001649A
0x180016497  mov     [rbx+10h], edi
0x18001649a  mov     rcx, [rbp+57h+pAuthBuffer]; pv
0x18001649e  test    rcx, rcx
0x1800164a1  jz      short loc_1800164A9
0x1800164a3  call    cs:__imp_CoTaskMemFree
0x1800164a9  mov     eax, r12d
0x1800164ac  add     rsp, 90h
0x1800164b3  pop     r15
0x1800164b5  pop     r13
0x1800164b7  pop     r12
0x1800164b9  pop     rdi
0x1800164ba  pop     rsi
0x1800164bb  pop     rbx
0x1800164bc  pop     rbp
0x1800164bd  retn
```
