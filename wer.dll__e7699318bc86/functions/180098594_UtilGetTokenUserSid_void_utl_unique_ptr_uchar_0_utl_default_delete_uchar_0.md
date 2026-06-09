# UtilGetTokenUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x180098594`
- end: `0x1800987da`
- name: `?UtilGetTokenUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009817c`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001c650`
- `0x18001daa8`
- `0x18001fe24`
- `0x18002cdd0`
- `0x18003bf14`
- `0x1800973cc`
- `0x180098594`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800985eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800985eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800986f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800986f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098607`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800986ee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098607`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800986ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilGetTokenUserSid(HANDLE TokenHandle, void **a2)
{
  void *v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  DWORD LastError; // eax
  int v8; // ebx
  wchar_t *v9; // rcx
  __int64 v10; // rdx
  void **unique_oversize_for; // rax
  PSID *v12; // rbx
  DWORD v13; // eax
  LPVOID v15[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+28h] BYREF
  void *v17; // [rsp+70h] [rbp+30h] BYREF
  LPVOID TokenInformation; // [rsp+78h] [rbp+38h] BYREF

  TokenInformation = 0;
  TokenInformationLength = 0;
  v17 = 0;
  if ( a2 && TokenHandle )
  {
    v4 = *a2;
    *a2 = 0;
    if ( v4 )
      HeapFree(g_hWerheap, 0, v4);
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v8 = -2147418113;
      MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5);
      goto LABEL_28;
    }
    LastError = GetLastError();
    v8 = ERROR_HR_FROM_WIN32(LastError);
    if ( (_WORD)v8 == 122 )
    {
      unique_oversize_for = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(v15, TokenInformationLength);
      utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
        &TokenInformation,
        unique_oversize_for);
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v15);
      v12 = (PSID *)TokenInformation;
      if ( TokenInformation )
      {
        if ( GetTokenInformation(
               TokenHandle,
               TokenUser,
               TokenInformation,
               TokenInformationLength,
               &TokenInformationLength) )
        {
          v8 = UtilDuplicateSid(*v12, &v17);
          if ( v8 >= 0 )
          {
            utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
              a2,
              &v17);
            v8 = 0;
            goto LABEL_28;
          }
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v10 = 14;
            goto LABEL_10;
          }
        }
        else
        {
          v13 = GetLastError();
          v8 = ERROR_HR_FROM_WIN32(v13);
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v10 = 13;
            goto LABEL_10;
          }
        }
      }
      else
      {
        v8 = -2147024882;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
            TokenInformationLength);
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v10 = 11;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, (unsigned int)v8);
      }
    }
  }
  else
  {
    v8 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  }
LABEL_28:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v17);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&TokenInformation);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180098594  mov     [rsp-18h+arg_0], rbx
0x180098599  push    rbp
0x18009859a  push    rsi
0x18009859b  push    r14
0x18009859d  mov     rbp, rsp
0x1800985a0  sub     rsp, 40h
0x1800985a4  mov     rsi, rdx
0x1800985a7  mov     r14, rcx
0x1800985aa  mov     [rbp+TokenInformation], 0
0x1800985b2  mov     [rbp+TokenInformationLength], 0
0x1800985b9  mov     [rbp+arg_10], 0
0x1800985c1  test    rdx, rdx
0x1800985c4  jz      loc_180098783
0x1800985ca  test    rcx, rcx
0x1800985cd  jz      loc_180098783
0x1800985d3  mov     r8, [rdx]; lpMem
0x1800985d6  mov     qword ptr [rdx], 0
0x1800985dd  test    r8, r8
0x1800985e0  jz      short loc_1800985F1
0x1800985e2  xor     edx, edx; dwFlags
0x1800985e4  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800985eb  call    cs:__imp_HeapFree
0x1800985f1  lea     rax, [rbp+TokenInformationLength]
0x1800985f5  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800985fa  xor     r9d, r9d; TokenInformationLength
0x1800985fd  xor     r8d, r8d; TokenInformation
0x180098600  lea     edx, [r9+1]; TokenInformationClass
0x180098604  mov     rcx, r14; TokenHandle
0x180098607  call    cs:__imp_GetTokenInformation
0x18009860d  test    eax, eax
0x18009860f  jnz     loc_180098777
0x180098615  call    cs:__imp_GetLastError
0x18009861b  mov     ecx, eax; unsigned int
0x18009861d  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180098622  mov     ebx, eax
0x180098624  cmp     ax, 7Ah ; 'z'
0x180098628  jz      short loc_180098668
0x18009862a  lea     rax, WPP_GLOBAL_Control
0x180098631  mov     rcx, cs:WPP_GLOBAL_Control
0x180098638  cmp     rcx, rax
0x18009863b  jz      loc_1800987B7
0x180098641  test    byte ptr [rcx+1Ch], 1
0x180098645  jz      loc_1800987B7
0x18009864b  mov     edx, 0Bh
0x180098650  mov     r9d, ebx
0x180098653  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009865a  mov     rcx, [rcx+10h]
0x18009865e  call    WPP_SF_d
0x180098663  jmp     loc_1800987B7
0x180098668  mov     edx, [rbp+TokenInformationLength]
0x18009866b  lea     rcx, [rbp+var_10]
0x18009866f  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x180098674  mov     rdx, rax
0x180098677  lea     rcx, [rbp+TokenInformation]
0x18009867b  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180098680  lea     rcx, [rbp+var_10]; void *
0x180098684  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180098689  mov     rbx, [rbp+TokenInformation]
0x18009868d  test    rbx, rbx
0x180098690  jnz     short loc_1800986D6
0x180098692  mov     ebx, 8007000Eh
0x180098697  lea     rax, WPP_GLOBAL_Control
0x18009869e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800986a5  cmp     rcx, rax
0x1800986a8  jz      loc_1800987B7
0x1800986ae  test    byte ptr [rcx+1Ch], 1
0x1800986b2  jz      loc_1800987B7
0x1800986b8  mov     edx, 0Ch
0x1800986bd  mov     r9d, [rbp+TokenInformationLength]
0x1800986c1  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800986c8  mov     rcx, [rcx+10h]
0x1800986cc  call    WPP_SF_d
0x1800986d1  jmp     loc_1800987B7
0x1800986d6  lea     rax, [rbp+TokenInformationLength]
0x1800986da  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800986df  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800986e3  mov     r8, rbx; TokenInformation
0x1800986e6  mov     edx, 1; TokenInformationClass
0x1800986eb  mov     rcx, r14; TokenHandle
0x1800986ee  call    cs:__imp_GetTokenInformation
0x1800986f4  test    eax, eax
0x1800986f6  jnz     short loc_180098732
0x1800986f8  call    cs:__imp_GetLastError
0x1800986fe  mov     ecx, eax; unsigned int
0x180098700  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180098705  mov     ebx, eax
0x180098707  lea     rax, WPP_GLOBAL_Control
0x18009870e  mov     rcx, cs:WPP_GLOBAL_Control
0x180098715  cmp     rcx, rax
0x180098718  jz      loc_1800987B7
0x18009871e  test    byte ptr [rcx+1Ch], 1
0x180098722  jz      loc_1800987B7
0x180098728  mov     edx, 0Dh
0x18009872d  jmp     loc_180098650
0x180098732  lea     rdx, [rbp+arg_10]
0x180098736  mov     rcx, [rbx]; pSourceSid
0x180098739  call    ?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x18009873e  mov     ebx, eax
0x180098740  test    eax, eax
0x180098742  jns     short loc_180098767
0x180098744  lea     rax, WPP_GLOBAL_Control
0x18009874b  mov     rcx, cs:WPP_GLOBAL_Control
0x180098752  cmp     rcx, rax
0x180098755  jz      short loc_1800987B7
0x180098757  test    byte ptr [rcx+1Ch], 1
0x18009875b  jz      short loc_1800987B7
0x18009875d  mov     edx, 0Eh
0x180098762  jmp     loc_180098650
0x180098767  lea     rdx, [rbp+arg_10]
0x18009876b  mov     rcx, rsi
0x18009876e  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180098773  xor     ebx, ebx
0x180098775  jmp     short loc_1800987B7
0x180098777  mov     ebx, 8000FFFFh
0x18009877c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180098781  jmp     short loc_1800987B7
0x180098783  mov     ebx, 80070057h
0x180098788  lea     rax, WPP_GLOBAL_Control
0x18009878f  mov     rcx, cs:WPP_GLOBAL_Control
0x180098796  cmp     rcx, rax
0x180098799  jz      short loc_1800987B7
0x18009879b  test    byte ptr [rcx+1Ch], 1
0x18009879f  jz      short loc_1800987B7
0x1800987a1  mov     edx, 0Ah
0x1800987a6  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800987ad  mov     rcx, [rcx+10h]
0x1800987b1  call    WPP_SF_
0x1800987b6  nop
0x1800987b7  lea     rcx, [rbp+arg_10]; void *
0x1800987bb  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800987c0  nop
0x1800987c1  lea     rcx, [rbp+TokenInformation]; void *
0x1800987c5  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800987ca  mov     eax, ebx
0x1800987cc  mov     rbx, [rsp+40h+arg_0]
0x1800987d1  add     rsp, 40h
0x1800987d5  pop     r14
0x1800987d7  pop     rsi
0x1800987d8  pop     rbp
0x1800987d9  retn
```
