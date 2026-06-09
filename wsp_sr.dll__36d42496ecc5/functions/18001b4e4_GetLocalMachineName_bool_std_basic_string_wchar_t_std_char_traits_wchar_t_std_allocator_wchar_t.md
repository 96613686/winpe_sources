# GetLocalMachineName(bool &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18001b4e4`
- end: `0x18001b764`
- name: `?GetLocalMachineName@@YA?AW4_MI_Result@@AEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `640`
- prototype: `__int64 __fastcall(_BYTE *, _QWORD *)`
- caller_count: `6`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000cfa4`
- `0x180011e78`
- `0x1800154a4`
- `0x18001c318`
- `0x18001c588`
- `0x18001c7f8`

## callees

- `0x180001e08`
- `0x180005570`
- `0x18000673c`
- `0x180006778`
- `0x1800067a0`
- `0x180008814`
- `0x180008f64`
- `0x18001a43c`
- `0x18001a58c`
- `0x18001b4e4`
- `0x18001b784`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001b643`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001b6c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001b643`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001b6c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b651`
- `CLUSAPI!GetClusterInformation` at `0x18001b59b`
- `CLUSAPI!GetClusterInformation` at `0x18001b615`
- `CLUSAPI!GetClusterInformation` at `0x18001b59b`
- `CLUSAPI!GetClusterInformation` at `0x18001b615`
- `CLUSAPI!OpenCluster` at `0x18001b566`
- `CLUSAPI!OpenCluster` at `0x18001b566`
- `CLUSAPI!CloseCluster` at `0x18001b629`
- `CLUSAPI!CloseCluster` at `0x18001b629`

## pseudocode

```c
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
0x18001b4e4  mov     [rsp-28h+arg_0], rbx
0x18001b4e9  mov     [rsp-28h+arg_8], rsi
0x18001b4ee  push    rbp
0x18001b4ef  push    rdi
0x18001b4f0  push    r13
0x18001b4f2  push    r14
0x18001b4f4  push    r15
0x18001b4f6  mov     rbp, rsp
0x18001b4f9  sub     rsp, 40h
0x18001b4fd  mov     rsi, rdx
0x18001b500  mov     r14, rcx
0x18001b503  lea     r13, WPP_GLOBAL_Control
0x18001b50a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b511  cmp     rcx, r13
0x18001b514  jz      short loc_18001B531
0x18001b516  test    byte ptr [rcx+1Ch], 4
0x18001b51a  jz      short loc_18001B531
0x18001b51c  mov     edx, 1Fh
0x18001b521  lea     r8, WPP_48adfc4782573e03aeb9fed2aec01b95_Traceguids
0x18001b528  mov     rcx, [rcx+10h]
0x18001b52c  call    WPP_SF_
0x18001b531  mov     [rbp+cchClusterName], 20h ; ' '
0x18001b538  xorps   xmm0, xmm0
0x18001b53b  movdqu  xmmword ptr [rbp+lpszClusterName], xmm0
0x18001b540  mov     [rbp+var_10], 0
0x18001b548  mov     edx, 21h ; '!'
0x18001b54d  lea     rcx, [rbp+lpszClusterName]
0x18001b551  call    ??$_Construct_n@$$V@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_K@Z; std::vector<wchar_t>::_Construct_n<>(unsigned __int64)
0x18001b556  nop
0x18001b557  call    ?IsLocalNodeCluster@@YA_NXZ; IsLocalNodeCluster(void)
0x18001b55c  test    al, al
0x18001b55e  jz      loc_18001B634
0x18001b564  xor     ecx, ecx; lpszClusterName
0x18001b566  call    cs:__imp_OpenCluster
0x18001b56c  mov     rdi, rax
0x18001b56f  test    rax, rax
0x18001b572  jnz     short loc_18001B589
0x18001b574  call    cs:__imp_GetLastError
0x18001b57a  mov     ebx, eax
0x18001b57c  mov     byte ptr [r14], 1
0x18001b580  test    eax, eax
0x18001b582  jz      short loc_18001B58D
0x18001b584  jmp     loc_18001B6D7
0x18001b589  mov     byte ptr [r14], 1
0x18001b58d  xor     r9d, r9d; lpClusterInfo
0x18001b590  lea     r8, [rbp+cchClusterName]; lpcchClusterName
0x18001b594  mov     rdx, [rbp+lpszClusterName]; lpszClusterName
0x18001b598  mov     rcx, rdi; hCluster
0x18001b59b  call    cs:__imp_GetClusterInformation
0x18001b5a1  mov     ebx, eax
0x18001b5a3  cmp     eax, 0EAh
0x18001b5a8  jnz     short loc_18001B61D
0x18001b5aa  mov     eax, [rbp+cchClusterName]
0x18001b5ad  inc     eax
0x18001b5af  mov     ebx, eax
0x18001b5b1  mov     rdx, [rbp+lpszClusterName]
0x18001b5b5  mov     r15, [rbp+lpszClusterName+8]
0x18001b5b9  mov     rcx, r15
0x18001b5bc  sub     rcx, rdx
0x18001b5bf  sar     rcx, 1
0x18001b5c2  cmp     rbx, rcx
0x18001b5c5  jnb     short loc_18001B5CD
0x18001b5c7  lea     rax, [rdx+rax*2]
0x18001b5cb  jmp     short loc_18001B603
0x18001b5cd  jbe     short loc_18001B607
0x18001b5cf  mov     rax, [rbp+var_10]
0x18001b5d3  sub     rax, rdx
0x18001b5d6  sar     rax, 1
0x18001b5d9  cmp     rbx, rax
0x18001b5dc  jbe     short loc_18001B5EC
0x18001b5de  mov     rdx, rbx
0x18001b5e1  lea     rcx, [rbp+lpszClusterName]
0x18001b5e5  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001b5ea  jmp     short loc_18001B607
0x18001b5ec  sub     rbx, rcx
0x18001b5ef  add     rbx, rbx
0x18001b5f2  mov     r8, rbx; Size
0x18001b5f5  xor     edx, edx; Val
0x18001b5f7  mov     rcx, r15; void *
0x18001b5fa  call    memset_0
0x18001b5ff  lea     rax, [rbx+r15]
0x18001b603  mov     [rbp+lpszClusterName+8], rax
0x18001b607  xor     r9d, r9d; lpClusterInfo
0x18001b60a  lea     r8, [rbp+cchClusterName]; lpcchClusterName
0x18001b60e  mov     rdx, [rbp+lpszClusterName]; lpszClusterName
0x18001b612  mov     rcx, rdi; hCluster
0x18001b615  call    cs:__imp_GetClusterInformation
0x18001b61b  mov     ebx, eax
0x18001b61d  test    rdi, rdi
0x18001b620  jz      loc_18001B6D7
0x18001b626  mov     rcx, rdi; hCluster
0x18001b629  call    cs:__imp_CloseCluster
0x18001b62f  jmp     loc_18001B6D7
0x18001b634  xor     ebx, ebx
0x18001b636  mov     [r14], bl
0x18001b639  lea     r8, [rbp+cchClusterName]; nSize
0x18001b63d  mov     rdx, [rbp+lpszClusterName]; lpBuffer
0x18001b641  xor     ecx, ecx; NameType
0x18001b643  call    cs:__imp_GetComputerNameExW
0x18001b649  test    eax, eax
0x18001b64b  jnz     loc_18001B6F8
0x18001b651  call    cs:__imp_GetLastError
0x18001b657  mov     ebx, eax
0x18001b659  cmp     eax, 0EAh
0x18001b65e  jnz     short loc_18001B6D7
0x18001b660  mov     eax, [rbp+cchClusterName]
0x18001b663  inc     eax
0x18001b665  mov     ebx, eax
0x18001b667  mov     rdx, [rbp+lpszClusterName]
0x18001b66b  mov     rdi, [rbp+lpszClusterName+8]
0x18001b66f  mov     rcx, rdi
0x18001b672  sub     rcx, rdx
0x18001b675  sar     rcx, 1
0x18001b678  cmp     rbx, rcx
0x18001b67b  jnb     short loc_18001B683
0x18001b67d  lea     rax, [rdx+rax*2]
0x18001b681  jmp     short loc_18001B6B9
0x18001b683  jbe     short loc_18001B6BD
0x18001b685  mov     rax, [rbp+var_10]
0x18001b689  sub     rax, rdx
0x18001b68c  sar     rax, 1
0x18001b68f  cmp     rbx, rax
0x18001b692  jbe     short loc_18001B6A2
0x18001b694  mov     rdx, rbx
0x18001b697  lea     rcx, [rbp+lpszClusterName]
0x18001b69b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001b6a0  jmp     short loc_18001B6BD
0x18001b6a2  sub     rbx, rcx
0x18001b6a5  add     rbx, rbx
0x18001b6a8  mov     r8, rbx; Size
0x18001b6ab  xor     edx, edx; Val
0x18001b6ad  mov     rcx, rdi; void *
0x18001b6b0  call    memset_0
0x18001b6b5  lea     rax, [rbx+rdi]
0x18001b6b9  mov     [rbp+lpszClusterName+8], rax
0x18001b6bd  xor     ebx, ebx
0x18001b6bf  lea     r8, [rbp+cchClusterName]; nSize
0x18001b6c3  mov     rdx, [rbp+lpszClusterName]; lpBuffer
0x18001b6c7  xor     ecx, ecx; NameType
0x18001b6c9  call    cs:__imp_GetComputerNameExW
0x18001b6cf  test    eax, eax
0x18001b6d1  jz      loc_18001B651
0x18001b6d7  test    ebx, ebx
0x18001b6d9  jz      short loc_18001B6F8
0x18001b6db  mov     byte ptr [r14], 0
0x18001b6df  mov     qword ptr [rsi+10h], 0
0x18001b6e7  cmp     qword ptr [rsi+18h], 7
0x18001b6ec  jbe     short loc_18001B6F1
0x18001b6ee  mov     rsi, [rsi]
0x18001b6f1  xor     eax, eax
0x18001b6f3  mov     [rsi], ax
0x18001b6f6  jmp     short loc_18001B70F
0x18001b6f8  mov     rcx, [rbp+lpszClusterName]
0x18001b6fc  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18001b701  mov     r8, rax
0x18001b704  mov     rdx, rcx
0x18001b707  mov     rcx, rsi
0x18001b70a  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001b70f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b716  cmp     rcx, r13
0x18001b719  jz      short loc_18001B739
0x18001b71b  test    byte ptr [rcx+1Ch], 1
0x18001b71f  jz      short loc_18001B739
0x18001b721  mov     edx, 20h ; ' '
0x18001b726  mov     r9d, ebx
0x18001b729  lea     r8, WPP_48adfc4782573e03aeb9fed2aec01b95_Traceguids
0x18001b730  mov     rcx, [rcx+10h]
0x18001b734  call    WPP_SF_d
0x18001b739  mov     ecx, ebx; unsigned int
0x18001b73b  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18001b740  mov     ebx, eax
0x18001b742  lea     rcx, [rbp+lpszClusterName]
0x18001b746  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18001b74b  mov     eax, ebx
0x18001b74d  mov     rbx, [rsp+40h+arg_0]
0x18001b752  mov     rsi, [rsp+40h+arg_8]
0x18001b757  add     rsp, 40h
0x18001b75b  pop     r15
0x18001b75d  pop     r14
0x18001b75f  pop     r13
0x18001b761  pop     rdi
0x18001b762  pop     rbp
0x18001b763  retn
```
