# UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x18009b728`
- end: `0x18009b816`
- name: `?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009c74c`
- `0x18009c9e4`

## callees

- `0x18001c368`
- `0x18001e0d0`
- `0x18001e100`
- `0x18002e94c`
- `0x18009b728`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009b7ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009b7ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b7bf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009b76c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009b76c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18009b74f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18009b74f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009b7af`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009b7af`

## pseudocode

```c
__int64 __fastcall UtilDuplicateSid(PSID pSourceSid, PSID *a2)
{
  unsigned int v4; // ebx
  DWORD LengthSid; // esi
  __int64 unique_oversize_for; // rax
  DWORD LastError; // eax
  unsigned int v8; // eax
  PSID v9; // r8
  char v11; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 || !pSourceSid )
    return 2147942487LL;
  if ( IsValidSid(pSourceSid) )
  {
    LengthSid = GetLengthSid(pSourceSid);
    unique_oversize_for = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(&v11, LengthSid);
    utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
      a2,
      unique_oversize_for);
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v11);
    if ( *a2 )
    {
      if ( CopySid(LengthSid, *a2, pSourceSid) )
      {
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v8 = ERROR_HR_FROM_WIN32(LastError);
        v9 = *a2;
        v4 = v8;
        *a2 = 0;
        if ( v9 )
          HeapFree(g_hWerheap, 0, v9);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18009b728  mov     [rsp+arg_0], rbx
0x18009b72d  mov     [rsp+arg_10], rsi
0x18009b732  push    rdi
0x18009b733  sub     rsp, 20h
0x18009b737  mov     rdi, rdx
0x18009b73a  mov     rbx, rcx
0x18009b73d  test    rdx, rdx
0x18009b740  jz      loc_18009B800
0x18009b746  test    rcx, rcx
0x18009b749  jz      loc_18009B800
0x18009b74f  call    cs:__imp_IsValidSid
0x18009b756  nop     dword ptr [rax+rax+00h]
0x18009b75b  test    eax, eax
0x18009b75d  jnz     short loc_18009B769
0x18009b75f  mov     ebx, 80070057h
0x18009b764  jmp     loc_18009B7FC
0x18009b769  mov     rcx, rbx; pSid
0x18009b76c  call    cs:__imp_GetLengthSid
0x18009b773  nop     dword ptr [rax+rax+00h]
0x18009b778  mov     edx, eax
0x18009b77a  lea     rcx, [rsp+28h+arg_8]
0x18009b77f  mov     esi, eax
0x18009b781  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x18009b786  mov     rdx, rax
0x18009b789  mov     rcx, rdi
0x18009b78c  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x18009b791  lea     rcx, [rsp+28h+arg_8]; void *
0x18009b796  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009b79b  mov     rdx, [rdi]; pDestinationSid
0x18009b79e  test    rdx, rdx
0x18009b7a1  jnz     short loc_18009B7AA
0x18009b7a3  mov     ebx, 8007000Eh
0x18009b7a8  jmp     short loc_18009B7FC
0x18009b7aa  mov     r8, rbx; pSourceSid
0x18009b7ad  mov     ecx, esi; nDestinationSidLength
0x18009b7af  call    cs:__imp_CopySid
0x18009b7b6  nop     dword ptr [rax+rax+00h]
0x18009b7bb  test    eax, eax
0x18009b7bd  jnz     short loc_18009B7FA
0x18009b7bf  call    cs:__imp_GetLastError
0x18009b7c6  nop     dword ptr [rax+rax+00h]
0x18009b7cb  mov     ecx, eax; unsigned int
0x18009b7cd  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009b7d2  mov     r8, [rdi]; lpMem
0x18009b7d5  mov     ebx, eax
0x18009b7d7  mov     qword ptr [rdi], 0
0x18009b7de  test    r8, r8
0x18009b7e1  jz      short loc_18009B7FC
0x18009b7e3  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18009b7ea  xor     edx, edx; dwFlags
0x18009b7ec  call    cs:__imp_HeapFree
0x18009b7f3  nop     dword ptr [rax+rax+00h]
0x18009b7f8  jmp     short loc_18009B7FC
0x18009b7fa  xor     ebx, ebx
0x18009b7fc  mov     eax, ebx
0x18009b7fe  jmp     short loc_18009B805
0x18009b800  mov     eax, 80070057h
0x18009b805  mov     rbx, [rsp+28h+arg_0]
0x18009b80a  mov     rsi, [rsp+28h+arg_10]
0x18009b80f  add     rsp, 20h
0x18009b813  pop     rdi
0x18009b814  retn
```
