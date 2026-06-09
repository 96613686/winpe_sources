# GetSidFromToken(void *,void * *,ulong *)

- ea: `0x18000c5e0`
- end: `0x18000c7f5`
- name: `?GetSidFromToken@@YAKPEAXPEAPEAXPEAK@Z`
- size: `533`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, void **, unsigned int *)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180088574`
- `0x1800c46d8`
- `0x1801243f8`
- `0x1802017d4`

## callees

- `0x18000aa0c`
- `0x18000c5a0`
- `0x18000c5e0`
- `0x18000c800`
- `0x180011530`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c71b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c71b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c693`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c708`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c693`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c708`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c6a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c6a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c76a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c7d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c76a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c7d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c773`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000c6cd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000c6cd`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c66e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c66e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000c67f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000c7de`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000c67f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000c7de`

## pseudocode

```c
__int64 __fastcall GetSidFromToken(HANDLE TokenHandle, void **a2, unsigned int *a3)
{
  unsigned int TokenUserInfo; // eax
  void *v7; // rbx
  DWORD LastError; // edi
  PSID v9; // rdi
  DWORD LengthSid; // r15d
  void *v11; // rbp
  HANDLE ProcessHeap; // rax
  HANDLE v13; // rax
  LPVOID lpMem; // [rsp+58h] [rbp+10h] BYREF

  lpMem = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids);
  }
  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  TokenUserInfo = GetTokenUserInfo(TokenHandle, (struct _TOKEN_USER **)&lpMem);
  v7 = lpMem;
  LastError = TokenUserInfo;
  if ( !TokenUserInfo )
  {
    v9 = *(PSID *)lpMem;
    if ( !*(_QWORD *)lpMem || !IsValidSid(*(PSID *)lpMem) )
    {
      LastError = 87;
      goto LABEL_16;
    }
    LengthSid = GetLengthSid(v9);
    if ( LengthSid )
    {
      v11 = 0;
      ProcessHeap = GetProcessHeap();
      if ( ProcessHeap && (v11 = HeapAlloc(ProcessHeap, 8u, LengthSid)) == 0 )
      {
        SetLastError(8u);
      }
      else if ( v11 && CopySid(LengthSid, v11, v9) )
      {
        *a2 = v11;
        LastError = 0;
        goto LABEL_14;
      }
    }
    else
    {
      SetLastError(0x57u);
      v11 = 0;
    }
    LastError = GetLastError();
    if ( !LastError )
    {
LABEL_14:
      if ( a3 )
        *a3 = GetLengthSid(*a2);
      goto LABEL_16;
    }
    if ( v11 )
      FreeWLMem(v11);
  }
LABEL_16:
  if ( v7 )
  {
    v13 = GetProcessHeap();
    if ( v13 )
      HeapFree(v13, 0, v7);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000c5e0  push    rdi
0x18000c5e2  sub     rsp, 40h
0x18000c5e6  mov     [rsp+48h+arg_0], rbx
0x18000c5eb  mov     rbx, rcx
0x18000c5ee  mov     [rsp+48h+arg_18], rsi
0x18000c5f3  mov     rsi, r8
0x18000c5f6  mov     [rsp+48h+var_10], r12
0x18000c5fb  xor     r12d, r12d
0x18000c5fe  mov     [rsp+48h+var_18], r13
0x18000c603  mov     [rsp+48h+var_20], r14
0x18000c608  mov     r14, rdx
0x18000c60b  mov     [rsp+48h+lpMem], r12
0x18000c610  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c617  lea     r13, WPP_GLOBAL_Control
0x18000c61e  cmp     rcx, r13
0x18000c621  jz      short loc_18000C62D
0x18000c623  cmp     byte ptr [rcx+69h], 4
0x18000c627  jnb     loc_18000C7A2
0x18000c62d  mov     [r14], r12
0x18000c630  test    rsi, rsi
0x18000c633  jnz     loc_18000C7C6
0x18000c639  mov     [rsp+48h+arg_10], rbp
0x18000c63e  lea     rdx, [rsp+48h+lpMem]; struct _TOKEN_USER **
0x18000c643  mov     rcx, rbx; TokenHandle
0x18000c646  mov     [rsp+48h+var_28], r15
0x18000c64b  call    ?GetTokenUserInfo@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenUserInfo(void *,_TOKEN_USER * *)
0x18000c650  mov     rbx, [rsp+48h+lpMem]
0x18000c655  mov     edi, eax
0x18000c657  test    eax, eax
0x18000c659  jnz     loc_18000C6EA
0x18000c65f  mov     rdi, [rbx]
0x18000c662  test    rdi, rdi
0x18000c665  jz      loc_18000C7EB
0x18000c66b  mov     rcx, rdi; pSid
0x18000c66e  call    cs:__imp_IsValidSid
0x18000c674  test    eax, eax
0x18000c676  jz      loc_18000C7EB
0x18000c67c  mov     rcx, rdi; pSid
0x18000c67f  call    cs:__imp_GetLengthSid
0x18000c685  mov     r15d, eax
0x18000c688  test    eax, eax
0x18000c68a  jz      loc_18000C765
0x18000c690  mov     rbp, r12
0x18000c693  call    cs:__imp_GetProcessHeap
0x18000c699  test    rax, rax
0x18000c69c  jz      short loc_18000C6BB
0x18000c69e  mov     r8d, r15d; dwBytes
0x18000c6a1  mov     edx, 8; dwFlags
0x18000c6a6  mov     rcx, rax; hHeap
0x18000c6a9  call    cs:__imp_HeapAlloc
0x18000c6af  mov     rbp, rax
0x18000c6b2  test    rax, rax
0x18000c6b5  jz      loc_18000C7CE
0x18000c6bb  test    rbp, rbp
0x18000c6be  jz      loc_18000C773
0x18000c6c4  mov     r8, rdi; pSourceSid
0x18000c6c7  mov     rdx, rbp; pDestinationSid
0x18000c6ca  mov     ecx, r15d; nDestinationSidLength
0x18000c6cd  call    cs:__imp_CopySid
0x18000c6d3  test    eax, eax
0x18000c6d5  jz      loc_18000C773
0x18000c6db  mov     [r14], rbp
0x18000c6de  mov     edi, r12d
0x18000c6e1  test    rsi, rsi
0x18000c6e4  jnz     loc_18000C7DB
0x18000c6ea  mov     r15, [rsp+48h+var_28]
0x18000c6ef  mov     r14, [rsp+48h+var_20]
0x18000c6f4  mov     r12, [rsp+48h+var_10]
0x18000c6f9  mov     rsi, [rsp+48h+arg_18]
0x18000c6fe  mov     rbp, [rsp+48h+arg_10]
0x18000c703  test    rbx, rbx
0x18000c706  jz      short loc_18000C721
0x18000c708  call    cs:__imp_GetProcessHeap
0x18000c70e  test    rax, rax
0x18000c711  jz      short loc_18000C721
0x18000c713  mov     r8, rbx; lpMem
0x18000c716  xor     edx, edx; dwFlags
0x18000c718  mov     rcx, rax; hHeap
0x18000c71b  call    cs:__imp_HeapFree
0x18000c721  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c728  mov     rbx, [rsp+48h+arg_0]
0x18000c72d  cmp     rcx, r13
0x18000c730  mov     r13, [rsp+48h+var_18]
0x18000c735  jnz     short loc_18000C73F
0x18000c737  mov     eax, edi
0x18000c739  add     rsp, 40h
0x18000c73d  pop     rdi
0x18000c73e  retn
0x18000c73f  cmp     byte ptr [rcx+69h], 4
0x18000c743  jb      short loc_18000C737
0x18000c745  test    byte ptr [rcx+6Ch], 1
0x18000c749  jz      short loc_18000C737
0x18000c74b  mov     rcx, [rcx+60h]
0x18000c74f  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x18000c756  mov     edx, 17h
0x18000c75b  mov     r9d, edi
0x18000c75e  call    WPP_SF_d
0x18000c763  jmp     short loc_18000C737
0x18000c765  mov     ecx, 57h ; 'W'; dwErrCode
0x18000c76a  call    cs:__imp_SetLastError
0x18000c770  mov     rbp, r12
0x18000c773  call    cs:__imp_GetLastError
0x18000c779  mov     edi, eax
0x18000c77b  test    eax, eax
0x18000c77d  jz      loc_18000C6E1
0x18000c783  test    rbp, rbp
0x18000c786  jz      short loc_18000C795
0x18000c788  mov     rcx, rbp
0x18000c78b  call    FreeWLMem
0x18000c790  jmp     loc_18000C6EA
0x18000c795  test    edi, edi
0x18000c797  jnz     loc_18000C6EA
0x18000c79d  jmp     loc_18000C6E1
0x18000c7a2  test    byte ptr [rcx+6Ch], 1
0x18000c7a6  jz      loc_18000C62D
0x18000c7ac  mov     rcx, [rcx+60h]
0x18000c7b0  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x18000c7b7  mov     edx, 16h
0x18000c7bc  call    WPP_SF_
0x18000c7c1  jmp     loc_18000C62D
0x18000c7c6  mov     [rsi], r12d
0x18000c7c9  jmp     loc_18000C639
0x18000c7ce  mov     ecx, 8; dwErrCode
0x18000c7d3  call    cs:__imp_SetLastError
0x18000c7d9  jmp     short loc_18000C773
0x18000c7db  mov     rcx, [r14]; pSid
0x18000c7de  call    cs:__imp_GetLengthSid
0x18000c7e4  mov     [rsi], eax
0x18000c7e6  jmp     loc_18000C6EA
0x18000c7eb  mov     edi, 57h ; 'W'
0x18000c7f0  jmp     loc_18000C6EA
```
