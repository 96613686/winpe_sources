# GetLocalMachineName(bool &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18001b500`
- end: `0x18001b7b1`
- name: `?GetLocalMachineName@@YA?AW4_MI_Result@@AEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `689`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000cec8`
- `0x180011d40`
- `0x180015358`
- `0x18001c410`
- `0x18001c684`
- `0x18001c8f8`

## callees

- `0x180001e38`
- `0x18000559c`
- `0x180006794`
- `0x1800067cc`
- `0x1800067fc`
- `0x18000898c`
- `0x18000911c`
- `0x18001a478`
- `0x18001a598`
- `0x18001b500`
- `0x18001b7d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001b67d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001b70f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001b67d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001b70f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b691`
- `CLUSAPI!GetClusterInformation` at `0x18001b5c3`
- `CLUSAPI!GetClusterInformation` at `0x18001b643`
- `CLUSAPI!GetClusterInformation` at `0x18001b5c3`
- `CLUSAPI!GetClusterInformation` at `0x18001b643`
- `CLUSAPI!OpenCluster` at `0x18001b582`
- `CLUSAPI!OpenCluster` at `0x18001b582`
- `CLUSAPI!CloseCluster` at `0x18001b65d`
- `CLUSAPI!CloseCluster` at `0x18001b65d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetLocalMachineName(_BYTE *a1, _QWORD *a2)
{
  struct _HCLUSTER *v4; // rdi
  DWORD LastError; // ebx
  unsigned __int64 v6; // rbx
  LPWSTR v7; // r15
  unsigned __int64 v8; // rcx
  WCHAR *v9; // rax
  size_t v10; // rbx
  unsigned __int64 v11; // rbx
  LPWSTR v12; // rdi
  unsigned __int64 v13; // rcx
  WCHAR *v14; // rax
  size_t v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
  enum _MI_Result v18; // ebx
  LPWSTR lpszClusterName[2]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v21; // [rsp+30h] [rbp-10h]
  DWORD cchClusterName; // [rsp+80h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_48adfc4782573e03aeb9fed2aec01b95_Traceguids);
  cchClusterName = 32;
  *(_OWORD *)lpszClusterName = 0;
  v21 = 0;
  std::vector<wchar_t>::_Construct_n<>(lpszClusterName, 33);
  if ( !IsLocalNodeCluster() )
  {
    LastError = 0;
    *a1 = 0;
    if ( GetComputerNameExW(ComputerNameNetBIOS, lpszClusterName[0], &cchClusterName) )
    {
LABEL_34:
      v16 = std::_WChar_traits<wchar_t>::length(lpszClusterName[0]);
      std::wstring::_Assign<wchar_t>(a2, v17, v16);
      goto LABEL_35;
    }
    while ( 1 )
    {
      LastError = GetLastError();
      if ( LastError != 234 )
        goto LABEL_30;
      v11 = cchClusterName + 1;
      v12 = lpszClusterName[1];
      v13 = lpszClusterName[1] - lpszClusterName[0];
      if ( v11 < v13 )
        break;
      if ( v11 > v13 )
      {
        if ( v11 <= (signed __int64)(v21 - (unsigned __int64)lpszClusterName[0]) >> 1 )
        {
          v15 = v11 - v13;
          memset_0(lpszClusterName[1], 0, v15 * 2);
          v14 = &v12[v15];
          goto LABEL_28;
        }
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(lpszClusterName, cchClusterName + 1);
      }
LABEL_29:
      LastError = 0;
      if ( GetComputerNameExW(ComputerNameNetBIOS, lpszClusterName[0], &cchClusterName) )
        goto LABEL_30;
    }
    v14 = &lpszClusterName[0][cchClusterName + 1];
LABEL_28:
    lpszClusterName[1] = v14;
    goto LABEL_29;
  }
  v4 = OpenCluster(0);
  if ( v4 )
  {
    *a1 = 1;
  }
  else
  {
    LastError = GetLastError();
    *a1 = 1;
    if ( LastError )
      goto LABEL_30;
  }
  LastError = GetClusterInformation(v4, lpszClusterName[0], &cchClusterName, 0);
  if ( LastError == 234 )
  {
    v6 = cchClusterName + 1;
    v7 = lpszClusterName[1];
    v8 = lpszClusterName[1] - lpszClusterName[0];
    if ( v6 < v8 )
    {
      v9 = &lpszClusterName[0][cchClusterName + 1];
LABEL_16:
      lpszClusterName[1] = v9;
      goto LABEL_17;
    }
    if ( v6 > v8 )
    {
      if ( v6 <= (signed __int64)(v21 - (unsigned __int64)lpszClusterName[0]) >> 1 )
      {
        v10 = v6 - v8;
        memset_0(lpszClusterName[1], 0, v10 * 2);
        v9 = &v7[v10];
        goto LABEL_16;
      }
      std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(lpszClusterName, cchClusterName + 1);
    }
LABEL_17:
    LastError = GetClusterInformation(v4, lpszClusterName[0], &cchClusterName, 0);
  }
  if ( v4 )
    CloseCluster(v4);
LABEL_30:
  if ( !LastError )
    goto LABEL_34;
  *a1 = 0;
  a2[2] = 0;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  *(_WORD *)a2 = 0;
LABEL_35:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_48adfc4782573e03aeb9fed2aec01b95_Traceguids, LastError);
  v18 = MapWinErrorToMIResult(LastError);
  std::vector<wchar_t>::_Tidy(lpszClusterName);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18001b500  mov     [rsp-28h+arg_0], rbx
0x18001b505  mov     [rsp-28h+arg_8], rsi
0x18001b50a  push    rbp
0x18001b50b  push    rdi
0x18001b50c  push    r13
0x18001b50e  push    r14
0x18001b510  push    r15
0x18001b512  mov     rbp, rsp
0x18001b515  sub     rsp, 40h
0x18001b519  mov     rsi, rdx
0x18001b51c  mov     r14, rcx
0x18001b51f  lea     r13, WPP_GLOBAL_Control
0x18001b526  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b52d  cmp     rcx, r13
0x18001b530  jz      short loc_18001B54D
0x18001b532  test    byte ptr [rcx+1Ch], 4
0x18001b536  jz      short loc_18001B54D
0x18001b538  mov     edx, 1Fh
0x18001b53d  lea     r8, WPP_48adfc4782573e03aeb9fed2aec01b95_Traceguids
0x18001b544  mov     rcx, [rcx+10h]
0x18001b548  call    WPP_SF_
0x18001b54d  mov     [rbp+cchClusterName], 20h ; ' '
0x18001b554  xorps   xmm0, xmm0
0x18001b557  movdqu  xmmword ptr [rbp+lpszClusterName], xmm0
0x18001b55c  mov     [rbp+var_10], 0
0x18001b564  mov     edx, 21h ; '!'
0x18001b569  lea     rcx, [rbp+lpszClusterName]
0x18001b56d  call    ??$_Construct_n@$$V@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_K@Z; std::vector<wchar_t>::_Construct_n<>(unsigned __int64)
0x18001b572  nop
0x18001b573  call    ?IsLocalNodeCluster@@YA_NXZ; IsLocalNodeCluster(void)
0x18001b578  test    al, al
0x18001b57a  jz      loc_18001B66E
0x18001b580  xor     ecx, ecx; lpszClusterName
0x18001b582  call    cs:__imp_OpenCluster
0x18001b589  nop     dword ptr [rax+rax+00h]
0x18001b58e  mov     rdi, rax
0x18001b591  test    rax, rax
0x18001b594  jnz     short loc_18001B5B1
0x18001b596  call    cs:__imp_GetLastError
0x18001b59d  nop     dword ptr [rax+rax+00h]
0x18001b5a2  mov     ebx, eax
0x18001b5a4  mov     byte ptr [r14], 1
0x18001b5a8  test    eax, eax
0x18001b5aa  jz      short loc_18001B5B5
0x18001b5ac  jmp     loc_18001B723
0x18001b5b1  mov     byte ptr [r14], 1
0x18001b5b5  xor     r9d, r9d; lpClusterInfo
0x18001b5b8  lea     r8, [rbp+cchClusterName]; lpcchClusterName
0x18001b5bc  mov     rdx, [rbp+lpszClusterName]; lpszClusterName
0x18001b5c0  mov     rcx, rdi; hCluster
0x18001b5c3  call    cs:__imp_GetClusterInformation
0x18001b5ca  nop     dword ptr [rax+rax+00h]
0x18001b5cf  mov     ebx, eax
0x18001b5d1  cmp     eax, 0EAh
0x18001b5d6  jnz     short loc_18001B651
0x18001b5d8  mov     eax, [rbp+cchClusterName]
0x18001b5db  inc     eax
0x18001b5dd  mov     ebx, eax
0x18001b5df  mov     rdx, [rbp+lpszClusterName]
0x18001b5e3  mov     r15, [rbp+lpszClusterName+8]
0x18001b5e7  mov     rcx, r15
0x18001b5ea  sub     rcx, rdx
0x18001b5ed  sar     rcx, 1
0x18001b5f0  cmp     rbx, rcx
0x18001b5f3  jnb     short loc_18001B5FB
0x18001b5f5  lea     rax, [rdx+rax*2]
0x18001b5f9  jmp     short loc_18001B631
0x18001b5fb  jbe     short loc_18001B635
0x18001b5fd  mov     rax, [rbp+var_10]
0x18001b601  sub     rax, rdx
0x18001b604  sar     rax, 1
0x18001b607  cmp     rbx, rax
0x18001b60a  jbe     short loc_18001B61A
0x18001b60c  mov     rdx, rbx
0x18001b60f  lea     rcx, [rbp+lpszClusterName]
0x18001b613  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001b618  jmp     short loc_18001B635
0x18001b61a  sub     rbx, rcx
0x18001b61d  add     rbx, rbx
0x18001b620  mov     r8, rbx; Size
0x18001b623  xor     edx, edx; Val
0x18001b625  mov     rcx, r15; void *
0x18001b628  call    memset_0
0x18001b62d  lea     rax, [rbx+r15]
0x18001b631  mov     [rbp+lpszClusterName+8], rax
0x18001b635  xor     r9d, r9d; lpClusterInfo
0x18001b638  lea     r8, [rbp+cchClusterName]; lpcchClusterName
0x18001b63c  mov     rdx, [rbp+lpszClusterName]; lpszClusterName
0x18001b640  mov     rcx, rdi; hCluster
0x18001b643  call    cs:__imp_GetClusterInformation
0x18001b64a  nop     dword ptr [rax+rax+00h]
0x18001b64f  mov     ebx, eax
0x18001b651  test    rdi, rdi
0x18001b654  jz      loc_18001B723
0x18001b65a  mov     rcx, rdi; hCluster
0x18001b65d  call    cs:__imp_CloseCluster
0x18001b664  nop     dword ptr [rax+rax+00h]
0x18001b669  jmp     loc_18001B723
0x18001b66e  xor     ebx, ebx
0x18001b670  mov     [r14], bl
0x18001b673  lea     r8, [rbp+cchClusterName]; nSize
0x18001b677  mov     rdx, [rbp+lpszClusterName]; lpBuffer
0x18001b67b  xor     ecx, ecx; NameType
0x18001b67d  call    cs:__imp_GetComputerNameExW
0x18001b684  nop     dword ptr [rax+rax+00h]
0x18001b689  test    eax, eax
0x18001b68b  jnz     loc_18001B744
0x18001b691  call    cs:__imp_GetLastError
0x18001b698  nop     dword ptr [rax+rax+00h]
0x18001b69d  mov     ebx, eax
0x18001b69f  cmp     eax, 0EAh
0x18001b6a4  jnz     short loc_18001B723
0x18001b6a6  mov     eax, [rbp+cchClusterName]
0x18001b6a9  inc     eax
0x18001b6ab  mov     ebx, eax
0x18001b6ad  mov     rdx, [rbp+lpszClusterName]
0x18001b6b1  mov     rdi, [rbp+lpszClusterName+8]
0x18001b6b5  mov     rcx, rdi
0x18001b6b8  sub     rcx, rdx
0x18001b6bb  sar     rcx, 1
0x18001b6be  cmp     rbx, rcx
0x18001b6c1  jnb     short loc_18001B6C9
0x18001b6c3  lea     rax, [rdx+rax*2]
0x18001b6c7  jmp     short loc_18001B6FF
0x18001b6c9  jbe     short loc_18001B703
0x18001b6cb  mov     rax, [rbp+var_10]
0x18001b6cf  sub     rax, rdx
0x18001b6d2  sar     rax, 1
0x18001b6d5  cmp     rbx, rax
0x18001b6d8  jbe     short loc_18001B6E8
0x18001b6da  mov     rdx, rbx
0x18001b6dd  lea     rcx, [rbp+lpszClusterName]
0x18001b6e1  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001b6e6  jmp     short loc_18001B703
0x18001b6e8  sub     rbx, rcx
0x18001b6eb  add     rbx, rbx
0x18001b6ee  mov     r8, rbx; Size
0x18001b6f1  xor     edx, edx; Val
0x18001b6f3  mov     rcx, rdi; void *
0x18001b6f6  call    memset_0
0x18001b6fb  lea     rax, [rbx+rdi]
0x18001b6ff  mov     [rbp+lpszClusterName+8], rax
0x18001b703  xor     ebx, ebx
0x18001b705  lea     r8, [rbp+cchClusterName]; nSize
0x18001b709  mov     rdx, [rbp+lpszClusterName]; lpBuffer
0x18001b70d  xor     ecx, ecx; NameType
0x18001b70f  call    cs:__imp_GetComputerNameExW
0x18001b716  nop     dword ptr [rax+rax+00h]
0x18001b71b  test    eax, eax
0x18001b71d  jz      loc_18001B691
0x18001b723  test    ebx, ebx
0x18001b725  jz      short loc_18001B744
0x18001b727  mov     byte ptr [r14], 0
0x18001b72b  mov     qword ptr [rsi+10h], 0
0x18001b733  cmp     qword ptr [rsi+18h], 7
0x18001b738  jbe     short loc_18001B73D
0x18001b73a  mov     rsi, [rsi]
0x18001b73d  xor     eax, eax
0x18001b73f  mov     [rsi], ax
0x18001b742  jmp     short loc_18001B75B
0x18001b744  mov     rcx, [rbp+lpszClusterName]
0x18001b748  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18001b74d  mov     r8, rax
0x18001b750  mov     rdx, rcx
0x18001b753  mov     rcx, rsi
0x18001b756  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001b75b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b762  cmp     rcx, r13
0x18001b765  jz      short loc_18001B785
0x18001b767  test    byte ptr [rcx+1Ch], 1
0x18001b76b  jz      short loc_18001B785
0x18001b76d  mov     edx, 20h ; ' '
0x18001b772  mov     r9d, ebx
0x18001b775  lea     r8, WPP_48adfc4782573e03aeb9fed2aec01b95_Traceguids
0x18001b77c  mov     rcx, [rcx+10h]
0x18001b780  call    WPP_SF_d
0x18001b785  mov     ecx, ebx; unsigned int
0x18001b787  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18001b78c  mov     ebx, eax
0x18001b78e  lea     rcx, [rbp+lpszClusterName]
0x18001b792  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18001b797  mov     eax, ebx
0x18001b799  mov     rbx, [rsp+40h+arg_0]
0x18001b79e  mov     rsi, [rsp+40h+arg_8]
0x18001b7a3  add     rsp, 40h
0x18001b7a7  pop     r15
0x18001b7a9  pop     r14
0x18001b7ab  pop     r13
0x18001b7ad  pop     rdi
0x18001b7ae  pop     rbp
0x18001b7af  retn
```
