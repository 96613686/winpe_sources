# UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x1800973cc`
- end: `0x180097498`
- name: `?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180098320`
- `0x180098594`

## callees

- `0x18000716c`
- `0x18001c650`
- `0x18001daa8`
- `0x18002cdd0`
- `0x1800973cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097475`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009744e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009744e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180097407`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180097407`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800973f3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800973f3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180097444`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180097444`

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
0x1800973cc  mov     [rsp+arg_0], rbx
0x1800973d1  mov     [rsp+arg_10], rsi
0x1800973d6  push    rdi
0x1800973d7  sub     rsp, 20h
0x1800973db  mov     rdi, rdx
0x1800973de  mov     rbx, rcx
0x1800973e1  test    rdx, rdx
0x1800973e4  jz      loc_180097483
0x1800973ea  test    rcx, rcx
0x1800973ed  jz      loc_180097483
0x1800973f3  call    cs:__imp_IsValidSid
0x1800973f9  test    eax, eax
0x1800973fb  jnz     short loc_180097404
0x1800973fd  mov     ebx, 80070057h
0x180097402  jmp     short loc_18009747F
0x180097404  mov     rcx, rbx; pSid
0x180097407  call    cs:__imp_GetLengthSid
0x18009740d  mov     edx, eax
0x18009740f  lea     rcx, [rsp+28h+arg_8]
0x180097414  mov     esi, eax
0x180097416  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x18009741b  mov     rdx, rax
0x18009741e  mov     rcx, rdi
0x180097421  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180097426  lea     rcx, [rsp+28h+arg_8]; void *
0x18009742b  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180097430  mov     rdx, [rdi]; pDestinationSid
0x180097433  test    rdx, rdx
0x180097436  jnz     short loc_18009743F
0x180097438  mov     ebx, 8007000Eh
0x18009743d  jmp     short loc_18009747F
0x18009743f  mov     r8, rbx; pSourceSid
0x180097442  mov     ecx, esi; nDestinationSidLength
0x180097444  call    cs:__imp_CopySid
0x18009744a  test    eax, eax
0x18009744c  jnz     short loc_18009747D
0x18009744e  call    cs:__imp_GetLastError
0x180097454  mov     ecx, eax; unsigned int
0x180097456  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009745b  mov     r8, [rdi]; lpMem
0x18009745e  mov     ebx, eax
0x180097460  mov     qword ptr [rdi], 0
0x180097467  test    r8, r8
0x18009746a  jz      short loc_18009747F
0x18009746c  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180097473  xor     edx, edx; dwFlags
0x180097475  call    cs:__imp_HeapFree
0x18009747b  jmp     short loc_18009747F
0x18009747d  xor     ebx, ebx
0x18009747f  mov     eax, ebx
0x180097481  jmp     short loc_180097488
0x180097483  mov     eax, 80070057h
0x180097488  mov     rbx, [rsp+28h+arg_0]
0x18009748d  mov     rsi, [rsp+28h+arg_10]
0x180097492  add     rsp, 20h
0x180097496  pop     rdi
0x180097497  retn
```
