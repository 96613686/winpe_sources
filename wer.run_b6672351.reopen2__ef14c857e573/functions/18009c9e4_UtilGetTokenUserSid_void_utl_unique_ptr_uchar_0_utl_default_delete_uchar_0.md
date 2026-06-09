# UtilGetTokenUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x18009c9e4`
- end: `0x18009cc49`
- name: `?UtilGetTokenUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009c598`

## callees

- `0x180004c64`
- `0x18001c368`
- `0x18001e0d0`
- `0x18001e100`
- `0x180020680`
- `0x18002e94c`
- `0x18003de9c`
- `0x18009b728`
- `0x18009c9e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009ca3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009ca3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ca71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cb60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ca71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cb60`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009ca5d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009cb50`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009ca5d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009cb50`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilGetTokenUserSid(HANDLE TokenHandle, void **a2)
{
  void *v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  DWORD LastError; // eax
  int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  __int64 unique_oversize_for; // rax
  PSID *v13; // rbx
  DWORD v14; // eax
  _BYTE v16[16]; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+28h] BYREF
  PSID v18; // [rsp+70h] [rbp+30h] BYREF
  LPVOID TokenInformation; // [rsp+78h] [rbp+38h] BYREF

  TokenInformation = 0;
  TokenInformationLength = 0;
  v18 = 0;
  if ( a2 && TokenHandle )
  {
    v4 = *a2;
    *a2 = 0;
    if ( v4 )
      HeapFree(g_hWerheap, 0, v4);
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v9 = -2147418113;
      MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v7);
      goto LABEL_28;
    }
    LastError = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(LastError);
    if ( (_WORD)v9 == 122 )
    {
      unique_oversize_for = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(v16, TokenInformationLength);
      utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
        &TokenInformation,
        unique_oversize_for);
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v16);
      v13 = (PSID *)TokenInformation;
      if ( TokenInformation )
      {
        if ( GetTokenInformation(
               TokenHandle,
               TokenUser,
               TokenInformation,
               TokenInformationLength,
               &TokenInformationLength) )
        {
          v9 = UtilDuplicateSid(*v13, &v18);
          if ( v9 >= 0 )
          {
            utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
              a2,
              &v18);
            v9 = 0;
            goto LABEL_28;
          }
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v11 = 14;
            goto LABEL_10;
          }
        }
        else
        {
          v14 = GetLastError();
          v9 = ERROR_HR_FROM_WIN32(v14);
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v11 = 13;
            goto LABEL_10;
          }
        }
      }
      else
      {
        v9 = -2147024882;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
            TokenInformationLength);
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v11 = 11;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, (unsigned int)v9);
      }
    }
  }
  else
  {
    v9 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
  }
LABEL_28:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v18);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&TokenInformation);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18009c9e4  mov     [rsp-18h+arg_0], rbx
0x18009c9e9  push    rbp
0x18009c9ea  push    rsi
0x18009c9eb  push    r14
0x18009c9ed  mov     rbp, rsp
0x18009c9f0  sub     rsp, 40h
0x18009c9f4  mov     rsi, rdx
0x18009c9f7  mov     r14, rcx
0x18009c9fa  mov     [rbp+TokenInformation], 0
0x18009ca02  mov     [rbp+TokenInformationLength], 0
0x18009ca09  mov     [rbp+arg_10], 0
0x18009ca11  test    rdx, rdx
0x18009ca14  jz      loc_18009CBF1
0x18009ca1a  test    rcx, rcx
0x18009ca1d  jz      loc_18009CBF1
0x18009ca23  mov     r8, [rdx]; lpMem
0x18009ca26  mov     qword ptr [rdx], 0
0x18009ca2d  test    r8, r8
0x18009ca30  jz      short loc_18009CA47
0x18009ca32  xor     edx, edx; dwFlags
0x18009ca34  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18009ca3b  call    cs:__imp_HeapFree
0x18009ca42  nop     dword ptr [rax+rax+00h]
0x18009ca47  lea     rax, [rbp+TokenInformationLength]
0x18009ca4b  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18009ca50  xor     r9d, r9d; TokenInformationLength
0x18009ca53  xor     r8d, r8d; TokenInformation
0x18009ca56  lea     edx, [r9+1]; TokenInformationClass
0x18009ca5a  mov     rcx, r14; TokenHandle
0x18009ca5d  call    cs:__imp_GetTokenInformation
0x18009ca64  nop     dword ptr [rax+rax+00h]
0x18009ca69  test    eax, eax
0x18009ca6b  jnz     loc_18009CBE5
0x18009ca71  call    cs:__imp_GetLastError
0x18009ca78  nop     dword ptr [rax+rax+00h]
0x18009ca7d  mov     ecx, eax; unsigned int
0x18009ca7f  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009ca84  mov     ebx, eax
0x18009ca86  cmp     ax, 7Ah ; 'z'
0x18009ca8a  jz      short loc_18009CACA
0x18009ca8c  lea     rax, WPP_GLOBAL_Control
0x18009ca93  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ca9a  cmp     rcx, rax
0x18009ca9d  jz      loc_18009CC25
0x18009caa3  test    byte ptr [rcx+1Ch], 1
0x18009caa7  jz      loc_18009CC25
0x18009caad  mov     edx, 0Bh
0x18009cab2  mov     r9d, ebx
0x18009cab5  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009cabc  mov     rcx, [rcx+10h]
0x18009cac0  call    WPP_SF_d
0x18009cac5  jmp     loc_18009CC25
0x18009caca  mov     edx, [rbp+TokenInformationLength]
0x18009cacd  lea     rcx, [rbp+var_10]
0x18009cad1  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x18009cad6  mov     rdx, rax
0x18009cad9  lea     rcx, [rbp+TokenInformation]
0x18009cadd  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x18009cae2  lea     rcx, [rbp+var_10]; void *
0x18009cae6  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009caeb  mov     rbx, [rbp+TokenInformation]
0x18009caef  test    rbx, rbx
0x18009caf2  jnz     short loc_18009CB38
0x18009caf4  mov     ebx, 8007000Eh
0x18009caf9  lea     rax, WPP_GLOBAL_Control
0x18009cb00  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cb07  cmp     rcx, rax
0x18009cb0a  jz      loc_18009CC25
0x18009cb10  test    byte ptr [rcx+1Ch], 1
0x18009cb14  jz      loc_18009CC25
0x18009cb1a  mov     edx, 0Ch
0x18009cb1f  mov     r9d, [rbp+TokenInformationLength]
0x18009cb23  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009cb2a  mov     rcx, [rcx+10h]
0x18009cb2e  call    WPP_SF_d
0x18009cb33  jmp     loc_18009CC25
0x18009cb38  lea     rax, [rbp+TokenInformationLength]
0x18009cb3c  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18009cb41  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18009cb45  mov     r8, rbx; TokenInformation
0x18009cb48  mov     edx, 1; TokenInformationClass
0x18009cb4d  mov     rcx, r14; TokenHandle
0x18009cb50  call    cs:__imp_GetTokenInformation
0x18009cb57  nop     dword ptr [rax+rax+00h]
0x18009cb5c  test    eax, eax
0x18009cb5e  jnz     short loc_18009CBA0
0x18009cb60  call    cs:__imp_GetLastError
0x18009cb67  nop     dword ptr [rax+rax+00h]
0x18009cb6c  mov     ecx, eax; unsigned int
0x18009cb6e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009cb73  mov     ebx, eax
0x18009cb75  lea     rax, WPP_GLOBAL_Control
0x18009cb7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cb83  cmp     rcx, rax
0x18009cb86  jz      loc_18009CC25
0x18009cb8c  test    byte ptr [rcx+1Ch], 1
0x18009cb90  jz      loc_18009CC25
0x18009cb96  mov     edx, 0Dh
0x18009cb9b  jmp     loc_18009CAB2
0x18009cba0  lea     rdx, [rbp+arg_10]
0x18009cba4  mov     rcx, [rbx]; pSourceSid
0x18009cba7  call    ?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x18009cbac  mov     ebx, eax
0x18009cbae  test    eax, eax
0x18009cbb0  jns     short loc_18009CBD5
0x18009cbb2  lea     rax, WPP_GLOBAL_Control
0x18009cbb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cbc0  cmp     rcx, rax
0x18009cbc3  jz      short loc_18009CC25
0x18009cbc5  test    byte ptr [rcx+1Ch], 1
0x18009cbc9  jz      short loc_18009CC25
0x18009cbcb  mov     edx, 0Eh
0x18009cbd0  jmp     loc_18009CAB2
0x18009cbd5  lea     rdx, [rbp+arg_10]
0x18009cbd9  mov     rcx, rsi
0x18009cbdc  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x18009cbe1  xor     ebx, ebx
0x18009cbe3  jmp     short loc_18009CC25
0x18009cbe5  mov     ebx, 8000FFFFh
0x18009cbea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009cbef  jmp     short loc_18009CC25
0x18009cbf1  mov     ebx, 80070057h
0x18009cbf6  lea     rax, WPP_GLOBAL_Control
0x18009cbfd  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cc04  cmp     rcx, rax
0x18009cc07  jz      short loc_18009CC25
0x18009cc09  test    byte ptr [rcx+1Ch], 1
0x18009cc0d  jz      short loc_18009CC25
0x18009cc0f  mov     edx, 0Ah
0x18009cc14  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009cc1b  mov     rcx, [rcx+10h]
0x18009cc1f  call    WPP_SF_
0x18009cc24  nop
0x18009cc25  lea     rcx, [rbp+arg_10]; void *
0x18009cc29  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009cc2e  nop
0x18009cc2f  lea     rcx, [rbp+TokenInformation]; void *
0x18009cc33  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009cc38  mov     eax, ebx
0x18009cc3a  mov     rbx, [rsp+40h+arg_0]
0x18009cc3f  add     rsp, 40h
0x18009cc43  pop     r14
0x18009cc45  pop     rsi
0x18009cc46  pop     rbp
0x18009cc47  retn
```
