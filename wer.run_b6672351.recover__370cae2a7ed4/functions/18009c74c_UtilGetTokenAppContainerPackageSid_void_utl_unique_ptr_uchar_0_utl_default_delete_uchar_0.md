# UtilGetTokenAppContainerPackageSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x18009c74c`
- end: `0x18009c9dc`
- name: `?UtilGetTokenAppContainerPackageSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `656`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009c110`

## callees

- `0x180004c64`
- `0x18001c368`
- `0x18001e0d0`
- `0x180020680`
- `0x18002e94c`
- `0x18003de9c`
- `0x18009b728`
- `0x18009c74c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c7a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c7a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009c84e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009c84e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c7d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c8f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c7d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c8f4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009c7c4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009c8e4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009c7c4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009c8e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilGetTokenAppContainerPackageSid(HANDLE TokenHandle, void **a2)
{
  void *v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  DWORD LastError; // eax
  int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  PSID *v12; // rbx
  DWORD v13; // eax
  __int64 v15; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+28h] BYREF
  PSID v17; // [rsp+70h] [rbp+30h] BYREF
  PSID *v18; // [rsp+78h] [rbp+38h] BYREF

  v18 = 0;
  TokenInformationLength = 0;
  v17 = 0;
  if ( a2 && TokenHandle )
  {
    v4 = *a2;
    *a2 = 0;
    if ( v4 )
      HeapFree(g_hWerheap, 0, v4);
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
    {
      v9 = -2147418113;
      MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v7);
      goto LABEL_30;
    }
    LastError = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(LastError);
    if ( (_WORD)v9 == 122 )
    {
      if ( TokenInformationLength == 8 )
      {
        v9 = -2147020646;
        goto LABEL_30;
      }
      v12 = (PSID *)HeapAlloc(g_hWerheap, 0, TokenInformationLength);
      v18 = 0;
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v18);
      v15 = 0;
      v18 = v12;
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v15);
      if ( v12 )
      {
        if ( GetTokenInformation(
               TokenHandle,
               TokenAppContainerSid,
               v12,
               TokenInformationLength,
               &TokenInformationLength) )
        {
          v9 = UtilDuplicateSid(*v12, &v17);
          if ( v9 >= 0 )
          {
            utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
              a2,
              &v17);
            v9 = 0;
            goto LABEL_30;
          }
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v11 = 24;
            goto LABEL_10;
          }
        }
        else
        {
          v13 = GetLastError();
          v9 = ERROR_HR_FROM_WIN32(v13);
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v11 = 23;
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
            22,
            WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
            TokenInformationLength);
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v11 = 21;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, (unsigned int)v9);
      }
    }
  }
  else
  {
    v9 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
  }
LABEL_30:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v17);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18009c74c  mov     [rsp-18h+arg_0], rbx
0x18009c751  push    rbp
0x18009c752  push    rsi
0x18009c753  push    rdi
0x18009c754  mov     rbp, rsp
0x18009c757  sub     rsp, 40h
0x18009c75b  mov     rdi, rdx
0x18009c75e  mov     rsi, rcx
0x18009c761  mov     [rbp+arg_18], 0
0x18009c769  mov     [rbp+TokenInformationLength], 0
0x18009c770  mov     [rbp+arg_10], 0
0x18009c778  test    rdx, rdx
0x18009c77b  jz      loc_18009C985
0x18009c781  test    rcx, rcx
0x18009c784  jz      loc_18009C985
0x18009c78a  mov     r8, [rdx]; lpMem
0x18009c78d  mov     qword ptr [rdx], 0
0x18009c794  test    r8, r8
0x18009c797  jz      short loc_18009C7AE
0x18009c799  xor     edx, edx; dwFlags
0x18009c79b  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18009c7a2  call    cs:__imp_HeapFree
0x18009c7a9  nop     dword ptr [rax+rax+00h]
0x18009c7ae  lea     rax, [rbp+TokenInformationLength]
0x18009c7b2  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18009c7b7  xor     r9d, r9d; TokenInformationLength
0x18009c7ba  xor     r8d, r8d; TokenInformation
0x18009c7bd  lea     edx, [r9+1Fh]; TokenInformationClass
0x18009c7c1  mov     rcx, rsi; TokenHandle
0x18009c7c4  call    cs:__imp_GetTokenInformation
0x18009c7cb  nop     dword ptr [rax+rax+00h]
0x18009c7d0  test    eax, eax
0x18009c7d2  jnz     loc_18009C979
0x18009c7d8  call    cs:__imp_GetLastError
0x18009c7df  nop     dword ptr [rax+rax+00h]
0x18009c7e4  mov     ecx, eax; unsigned int
0x18009c7e6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009c7eb  mov     ebx, eax
0x18009c7ed  cmp     ax, 7Ah ; 'z'
0x18009c7f1  jz      short loc_18009C831
0x18009c7f3  lea     rax, WPP_GLOBAL_Control
0x18009c7fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c801  cmp     rcx, rax
0x18009c804  jz      loc_18009C9B9
0x18009c80a  test    byte ptr [rcx+1Ch], 1
0x18009c80e  jz      loc_18009C9B9
0x18009c814  mov     edx, 15h
0x18009c819  mov     r9d, ebx
0x18009c81c  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009c823  mov     rcx, [rcx+10h]
0x18009c827  call    WPP_SF_d
0x18009c82c  jmp     loc_18009C9B9
0x18009c831  cmp     [rbp+TokenInformationLength], 8
0x18009c835  jnz     short loc_18009C841
0x18009c837  mov     ebx, 8007109Ah
0x18009c83c  jmp     loc_18009C9B9
0x18009c841  mov     r8d, [rbp+TokenInformationLength]; dwBytes
0x18009c845  xor     edx, edx; dwFlags
0x18009c847  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18009c84e  call    cs:__imp_HeapAlloc
0x18009c855  nop     dword ptr [rax+rax+00h]
0x18009c85a  mov     rbx, rax
0x18009c85d  mov     [rbp+arg_18], 0
0x18009c865  lea     rcx, [rbp+arg_18]; void *
0x18009c869  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009c86e  mov     [rbp+var_10], 0
0x18009c876  mov     [rbp+arg_18], rbx
0x18009c87a  lea     rcx, [rbp+var_10]; void *
0x18009c87e  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009c883  test    rbx, rbx
0x18009c886  jnz     short loc_18009C8CC
0x18009c888  mov     ebx, 8007000Eh
0x18009c88d  lea     rax, WPP_GLOBAL_Control
0x18009c894  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c89b  cmp     rcx, rax
0x18009c89e  jz      loc_18009C9B9
0x18009c8a4  test    byte ptr [rcx+1Ch], 1
0x18009c8a8  jz      loc_18009C9B9
0x18009c8ae  mov     edx, 16h
0x18009c8b3  mov     r9d, [rbp+TokenInformationLength]
0x18009c8b7  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009c8be  mov     rcx, [rcx+10h]
0x18009c8c2  call    WPP_SF_d
0x18009c8c7  jmp     loc_18009C9B9
0x18009c8cc  lea     rax, [rbp+TokenInformationLength]
0x18009c8d0  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18009c8d5  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18009c8d9  mov     r8, rbx; TokenInformation
0x18009c8dc  mov     edx, 1Fh; TokenInformationClass
0x18009c8e1  mov     rcx, rsi; TokenHandle
0x18009c8e4  call    cs:__imp_GetTokenInformation
0x18009c8eb  nop     dword ptr [rax+rax+00h]
0x18009c8f0  test    eax, eax
0x18009c8f2  jnz     short loc_18009C934
0x18009c8f4  call    cs:__imp_GetLastError
0x18009c8fb  nop     dword ptr [rax+rax+00h]
0x18009c900  mov     ecx, eax; unsigned int
0x18009c902  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009c907  mov     ebx, eax
0x18009c909  lea     rax, WPP_GLOBAL_Control
0x18009c910  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c917  cmp     rcx, rax
0x18009c91a  jz      loc_18009C9B9
0x18009c920  test    byte ptr [rcx+1Ch], 1
0x18009c924  jz      loc_18009C9B9
0x18009c92a  mov     edx, 17h
0x18009c92f  jmp     loc_18009C819
0x18009c934  lea     rdx, [rbp+arg_10]
0x18009c938  mov     rcx, [rbx]; pSourceSid
0x18009c93b  call    ?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x18009c940  mov     ebx, eax
0x18009c942  test    eax, eax
0x18009c944  jns     short loc_18009C969
0x18009c946  lea     rax, WPP_GLOBAL_Control
0x18009c94d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c954  cmp     rcx, rax
0x18009c957  jz      short loc_18009C9B9
0x18009c959  test    byte ptr [rcx+1Ch], 1
0x18009c95d  jz      short loc_18009C9B9
0x18009c95f  mov     edx, 18h
0x18009c964  jmp     loc_18009C819
0x18009c969  lea     rdx, [rbp+arg_10]
0x18009c96d  mov     rcx, rdi
0x18009c970  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x18009c975  xor     ebx, ebx
0x18009c977  jmp     short loc_18009C9B9
0x18009c979  mov     ebx, 8000FFFFh
0x18009c97e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009c983  jmp     short loc_18009C9B9
0x18009c985  mov     ebx, 80070057h
0x18009c98a  lea     rax, WPP_GLOBAL_Control
0x18009c991  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c998  cmp     rcx, rax
0x18009c99b  jz      short loc_18009C9B9
0x18009c99d  test    byte ptr [rcx+1Ch], 1
0x18009c9a1  jz      short loc_18009C9B9
0x18009c9a3  mov     edx, 14h
0x18009c9a8  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009c9af  mov     rcx, [rcx+10h]
0x18009c9b3  call    WPP_SF_
0x18009c9b8  nop
0x18009c9b9  lea     rcx, [rbp+arg_10]; void *
0x18009c9bd  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009c9c2  nop
0x18009c9c3  lea     rcx, [rbp+arg_18]; void *
0x18009c9c7  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009c9cc  mov     eax, ebx
0x18009c9ce  mov     rbx, [rsp+40h+arg_0]
0x18009c9d3  add     rsp, 40h
0x18009c9d7  pop     rdi
0x18009c9d8  pop     rsi
0x18009c9d9  pop     rbp
0x18009c9da  retn
```
