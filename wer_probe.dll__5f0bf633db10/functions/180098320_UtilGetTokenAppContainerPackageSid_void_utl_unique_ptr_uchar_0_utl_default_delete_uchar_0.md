# UtilGetTokenAppContainerPackageSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x180098320`
- end: `0x18009858b`
- name: `?UtilGetTokenAppContainerPackageSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180097d30`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001c650`
- `0x18001fe24`
- `0x18002cdd0`
- `0x18003bf14`
- `0x1800973cc`
- `0x180098320`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180098376`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180098376`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180098410`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180098410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800983a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800984aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800983a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800984aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098392`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800984a0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098392`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800984a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilGetTokenAppContainerPackageSid(HANDLE TokenHandle, void **a2)
{
  void *v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  DWORD LastError; // eax
  int v8; // ebx
  wchar_t *v9; // rcx
  __int64 v10; // rdx
  PSID *v11; // rbx
  DWORD v12; // eax
  __int64 v14; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+28h] BYREF
  PSID v16; // [rsp+70h] [rbp+30h] BYREF
  PSID *v17; // [rsp+78h] [rbp+38h] BYREF

  v17 = 0;
  TokenInformationLength = 0;
  v16 = 0;
  if ( a2 && TokenHandle )
  {
    v4 = *a2;
    *a2 = 0;
    if ( v4 )
      HeapFree(g_hWerheap, 0, v4);
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
    {
      v8 = -2147418113;
      MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5);
      goto LABEL_30;
    }
    LastError = GetLastError();
    v8 = ERROR_HR_FROM_WIN32(LastError);
    if ( (_WORD)v8 == 122 )
    {
      if ( TokenInformationLength == 8 )
      {
        v8 = -2147020646;
        goto LABEL_30;
      }
      v11 = (PSID *)HeapAlloc(g_hWerheap, 0, TokenInformationLength);
      v17 = 0;
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v17);
      v14 = 0;
      v17 = v11;
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v14);
      if ( v11 )
      {
        if ( GetTokenInformation(
               TokenHandle,
               TokenAppContainerSid,
               v11,
               TokenInformationLength,
               &TokenInformationLength) )
        {
          v8 = UtilDuplicateSid(*v11, &v16);
          if ( v8 >= 0 )
          {
            utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
              a2,
              &v16);
            v8 = 0;
            goto LABEL_30;
          }
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v10 = 24;
            goto LABEL_10;
          }
        }
        else
        {
          v12 = GetLastError();
          v8 = ERROR_HR_FROM_WIN32(v12);
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v10 = 23;
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
            22,
            &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
            TokenInformationLength);
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v10 = 21;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v9 + 2), v10, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, (unsigned int)v8);
      }
    }
  }
  else
  {
    v8 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  }
LABEL_30:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v16);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180098320  mov     [rsp-18h+arg_0], rbx
0x180098325  push    rbp
0x180098326  push    rsi
0x180098327  push    rdi
0x180098328  mov     rbp, rsp
0x18009832b  sub     rsp, 40h
0x18009832f  mov     rdi, rdx
0x180098332  mov     rsi, rcx
0x180098335  mov     [rbp+arg_18], 0
0x18009833d  mov     [rbp+TokenInformationLength], 0
0x180098344  mov     [rbp+arg_10], 0
0x18009834c  test    rdx, rdx
0x18009834f  jz      loc_180098535
0x180098355  test    rcx, rcx
0x180098358  jz      loc_180098535
0x18009835e  mov     r8, [rdx]; lpMem
0x180098361  mov     qword ptr [rdx], 0
0x180098368  test    r8, r8
0x18009836b  jz      short loc_18009837C
0x18009836d  xor     edx, edx; dwFlags
0x18009836f  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180098376  call    cs:__imp_HeapFree
0x18009837c  lea     rax, [rbp+TokenInformationLength]
0x180098380  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180098385  xor     r9d, r9d; TokenInformationLength
0x180098388  xor     r8d, r8d; TokenInformation
0x18009838b  lea     edx, [r9+1Fh]; TokenInformationClass
0x18009838f  mov     rcx, rsi; TokenHandle
0x180098392  call    cs:__imp_GetTokenInformation
0x180098398  test    eax, eax
0x18009839a  jnz     loc_180098529
0x1800983a0  call    cs:__imp_GetLastError
0x1800983a6  mov     ecx, eax; unsigned int
0x1800983a8  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800983ad  mov     ebx, eax
0x1800983af  cmp     ax, 7Ah ; 'z'
0x1800983b3  jz      short loc_1800983F3
0x1800983b5  lea     rax, WPP_GLOBAL_Control
0x1800983bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800983c3  cmp     rcx, rax
0x1800983c6  jz      loc_180098569
0x1800983cc  test    byte ptr [rcx+1Ch], 1
0x1800983d0  jz      loc_180098569
0x1800983d6  mov     edx, 15h
0x1800983db  mov     r9d, ebx
0x1800983de  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800983e5  mov     rcx, [rcx+10h]
0x1800983e9  call    WPP_SF_d
0x1800983ee  jmp     loc_180098569
0x1800983f3  cmp     [rbp+TokenInformationLength], 8
0x1800983f7  jnz     short loc_180098403
0x1800983f9  mov     ebx, 8007109Ah
0x1800983fe  jmp     loc_180098569
0x180098403  mov     r8d, [rbp+TokenInformationLength]; dwBytes
0x180098407  xor     edx, edx; dwFlags
0x180098409  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180098410  call    cs:__imp_HeapAlloc
0x180098416  mov     rbx, rax
0x180098419  mov     [rbp+arg_18], 0
0x180098421  lea     rcx, [rbp+arg_18]; void *
0x180098425  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009842a  mov     [rbp+var_10], 0
0x180098432  mov     [rbp+arg_18], rbx
0x180098436  lea     rcx, [rbp+var_10]; void *
0x18009843a  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009843f  test    rbx, rbx
0x180098442  jnz     short loc_180098488
0x180098444  mov     ebx, 8007000Eh
0x180098449  lea     rax, WPP_GLOBAL_Control
0x180098450  mov     rcx, cs:WPP_GLOBAL_Control
0x180098457  cmp     rcx, rax
0x18009845a  jz      loc_180098569
0x180098460  test    byte ptr [rcx+1Ch], 1
0x180098464  jz      loc_180098569
0x18009846a  mov     edx, 16h
0x18009846f  mov     r9d, [rbp+TokenInformationLength]
0x180098473  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009847a  mov     rcx, [rcx+10h]
0x18009847e  call    WPP_SF_d
0x180098483  jmp     loc_180098569
0x180098488  lea     rax, [rbp+TokenInformationLength]
0x18009848c  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180098491  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180098495  mov     r8, rbx; TokenInformation
0x180098498  mov     edx, 1Fh; TokenInformationClass
0x18009849d  mov     rcx, rsi; TokenHandle
0x1800984a0  call    cs:__imp_GetTokenInformation
0x1800984a6  test    eax, eax
0x1800984a8  jnz     short loc_1800984E4
0x1800984aa  call    cs:__imp_GetLastError
0x1800984b0  mov     ecx, eax; unsigned int
0x1800984b2  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800984b7  mov     ebx, eax
0x1800984b9  lea     rax, WPP_GLOBAL_Control
0x1800984c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800984c7  cmp     rcx, rax
0x1800984ca  jz      loc_180098569
0x1800984d0  test    byte ptr [rcx+1Ch], 1
0x1800984d4  jz      loc_180098569
0x1800984da  mov     edx, 17h
0x1800984df  jmp     loc_1800983DB
0x1800984e4  lea     rdx, [rbp+arg_10]
0x1800984e8  mov     rcx, [rbx]; pSourceSid
0x1800984eb  call    ?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x1800984f0  mov     ebx, eax
0x1800984f2  test    eax, eax
0x1800984f4  jns     short loc_180098519
0x1800984f6  lea     rax, WPP_GLOBAL_Control
0x1800984fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180098504  cmp     rcx, rax
0x180098507  jz      short loc_180098569
0x180098509  test    byte ptr [rcx+1Ch], 1
0x18009850d  jz      short loc_180098569
0x18009850f  mov     edx, 18h
0x180098514  jmp     loc_1800983DB
0x180098519  lea     rdx, [rbp+arg_10]
0x18009851d  mov     rcx, rdi
0x180098520  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180098525  xor     ebx, ebx
0x180098527  jmp     short loc_180098569
0x180098529  mov     ebx, 8000FFFFh
0x18009852e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180098533  jmp     short loc_180098569
0x180098535  mov     ebx, 80070057h
0x18009853a  lea     rax, WPP_GLOBAL_Control
0x180098541  mov     rcx, cs:WPP_GLOBAL_Control
0x180098548  cmp     rcx, rax
0x18009854b  jz      short loc_180098569
0x18009854d  test    byte ptr [rcx+1Ch], 1
0x180098551  jz      short loc_180098569
0x180098553  mov     edx, 14h
0x180098558  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009855f  mov     rcx, [rcx+10h]
0x180098563  call    WPP_SF_
0x180098568  nop
0x180098569  lea     rcx, [rbp+arg_10]; void *
0x18009856d  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180098572  nop
0x180098573  lea     rcx, [rbp+arg_18]; void *
0x180098577  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009857c  mov     eax, ebx
0x18009857e  mov     rbx, [rsp+40h+arg_0]
0x180098583  add     rsp, 40h
0x180098587  pop     rdi
0x180098588  pop     rsi
0x180098589  pop     rbp
0x18009858a  retn
```
