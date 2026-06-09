# AcmDuplicateSid(void *,void * *)

- ea: `0x180068e70`
- end: `0x180068f60`
- name: `?AcmDuplicateSid@@YAKPEAXPEAPEAX@Z`
- size: `240`
- prototype: `unsigned int __fastcall(PSID pSourceSid, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180163098`

## callees

- `0x180068e70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068f2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068f2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068eaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068f1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068eaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068f1b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180068ec5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180068ec5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068f3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068f4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068f3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068f4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068f52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068f52`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180068ee0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180068ee0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180068e86`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180068e86`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180068e9d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180068e9d`

## pseudocode

```c
__int64 __fastcall AcmDuplicateSid(PSID pSourceSid, void **a2)
{
  DWORD LengthSid; // esi
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v8; // rax
  DWORD LastError; // edi

  if ( !pSourceSid || !IsValidSid(pSourceSid) )
    return 87;
  LengthSid = GetLengthSid(pSourceSid);
  if ( LengthSid )
  {
    v5 = 0;
    ProcessHeap = GetProcessHeap();
    if ( ProcessHeap && (v5 = HeapAlloc(ProcessHeap, 8u, LengthSid)) == 0 )
    {
      SetLastError(8u);
    }
    else if ( v5 && CopySid(LengthSid, v5, pSourceSid) )
    {
      *a2 = v5;
      return 0;
    }
  }
  else
  {
    SetLastError(0x57u);
    v5 = 0;
  }
  LastError = GetLastError();
  if ( LastError && v5 )
  {
    v8 = GetProcessHeap();
    if ( v8 )
      HeapFree(v8, 0, v5);
  }
  return LastError;
}

```

## disassembly

```asm
0x180068e70  mov     [rsp+arg_10], rdi
0x180068e75  push    r14
0x180068e77  sub     rsp, 20h
0x180068e7b  mov     r14, rdx
0x180068e7e  mov     rdi, rcx
0x180068e81  test    rcx, rcx
0x180068e84  jz      short loc_180068F05
0x180068e86  call    cs:__imp_IsValidSid
0x180068e8c  test    eax, eax
0x180068e8e  jz      short loc_180068F05
0x180068e90  mov     [rsp+28h+arg_8], rsi
0x180068e95  mov     rcx, rdi; pSid
0x180068e98  mov     [rsp+28h+arg_0], rbx
0x180068e9d  call    cs:__imp_GetLengthSid
0x180068ea3  mov     esi, eax
0x180068ea5  test    eax, eax
0x180068ea7  jz      loc_180068F38
0x180068ead  xor     ebx, ebx
0x180068eaf  call    cs:__imp_GetProcessHeap
0x180068eb5  test    rax, rax
0x180068eb8  jz      short loc_180068ED3
0x180068eba  mov     r8d, esi; dwBytes
0x180068ebd  mov     edx, 8; dwFlags
0x180068ec2  mov     rcx, rax; hHeap
0x180068ec5  call    cs:__imp_HeapAlloc
0x180068ecb  mov     rbx, rax
0x180068ece  test    rax, rax
0x180068ed1  jz      short loc_180068F47
0x180068ed3  test    rbx, rbx
0x180068ed6  jz      short loc_180068F52
0x180068ed8  mov     r8, rdi; pSourceSid
0x180068edb  mov     rdx, rbx; pDestinationSid
0x180068ede  mov     ecx, esi; nDestinationSidLength
0x180068ee0  call    cs:__imp_CopySid
0x180068ee6  test    eax, eax
0x180068ee8  jz      short loc_180068F52
0x180068eea  mov     [r14], rbx
0x180068eed  xor     eax, eax
0x180068eef  mov     rbx, [rsp+28h+arg_0]
0x180068ef4  mov     rsi, [rsp+28h+arg_8]
0x180068ef9  mov     rdi, [rsp+28h+arg_10]
0x180068efe  add     rsp, 20h
0x180068f02  pop     r14
0x180068f04  retn
0x180068f05  mov     rdi, [rsp+28h+arg_10]
0x180068f0a  mov     eax, 57h ; 'W'
0x180068f0f  add     rsp, 20h
0x180068f13  pop     r14
0x180068f15  retn
0x180068f16  test    rbx, rbx
0x180068f19  jz      short loc_180068F34
0x180068f1b  call    cs:__imp_GetProcessHeap
0x180068f21  test    rax, rax
0x180068f24  jz      short loc_180068F34
0x180068f26  mov     r8, rbx; lpMem
0x180068f29  xor     edx, edx; dwFlags
0x180068f2b  mov     rcx, rax; hHeap
0x180068f2e  call    cs:__imp_HeapFree
0x180068f34  mov     eax, edi
0x180068f36  jmp     short loc_180068EEF
0x180068f38  mov     ecx, 57h ; 'W'; dwErrCode
0x180068f3d  call    cs:__imp_SetLastError
0x180068f43  xor     ebx, ebx
0x180068f45  jmp     short loc_180068F52
0x180068f47  mov     ecx, 8; dwErrCode
0x180068f4c  call    cs:__imp_SetLastError
0x180068f52  call    cs:__imp_GetLastError
0x180068f58  mov     edi, eax
0x180068f5a  test    eax, eax
0x180068f5c  jz      short loc_180068F34
0x180068f5e  jmp     short loc_180068F16
```
