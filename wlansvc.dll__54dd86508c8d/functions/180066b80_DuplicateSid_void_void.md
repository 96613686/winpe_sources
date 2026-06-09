# DuplicateSid(void *,void * *)

- ea: `0x180066b80`
- end: `0x180066c59`
- name: `?DuplicateSid@@YAKPEAXPEAPEAX@Z`
- size: `217`
- prototype: `unsigned int __fastcall(PSID pSourceSid, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036dfc`
- `0x1800cbfd8`

## callees

- `0x18000c5a0`
- `0x180066b80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066bc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066bc3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180066bd9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180066bd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066c1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066c3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066c1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066c3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c26`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180066bf4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180066bf4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180066b9a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180066b9a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180066bb5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180066bb5`

## pseudocode

```c
__int64 __fastcall DuplicateSid(PSID pSourceSid, void **a2)
{
  DWORD LengthSid; // edi
  void *v5; // rsi
  HANDLE ProcessHeap; // rax
  DWORD LastError; // ebx

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
  if ( LastError )
  {
    if ( v5 )
      FreeWLMem(v5);
  }
  return LastError;
}

```

## disassembly

```asm
0x180066b80  mov     [rsp+arg_10], rbx
0x180066b85  push    r14
0x180066b87  sub     rsp, 20h
0x180066b8b  mov     r14, rdx
0x180066b8e  mov     rbx, rcx
0x180066b91  test    rcx, rcx
0x180066b94  jz      loc_180066C52
0x180066b9a  call    cs:__imp_IsValidSid
0x180066ba0  test    eax, eax
0x180066ba2  jz      loc_180066C52
0x180066ba8  mov     [rsp+28h+arg_8], rdi
0x180066bad  mov     rcx, rbx; pSid
0x180066bb0  mov     [rsp+28h+arg_0], rsi
0x180066bb5  call    cs:__imp_GetLengthSid
0x180066bbb  mov     edi, eax
0x180066bbd  test    eax, eax
0x180066bbf  jz      short loc_180066C19
0x180066bc1  xor     esi, esi
0x180066bc3  call    cs:__imp_GetProcessHeap
0x180066bc9  test    rax, rax
0x180066bcc  jz      short loc_180066BE7
0x180066bce  mov     r8d, edi; dwBytes
0x180066bd1  mov     edx, 8; dwFlags
0x180066bd6  mov     rcx, rax; hHeap
0x180066bd9  call    cs:__imp_HeapAlloc
0x180066bdf  mov     rsi, rax
0x180066be2  test    rax, rax
0x180066be5  jz      short loc_180066C36
0x180066be7  test    rsi, rsi
0x180066bea  jz      short loc_180066C26
0x180066bec  mov     r8, rbx; pSourceSid
0x180066bef  mov     rdx, rsi; pDestinationSid
0x180066bf2  mov     ecx, edi; nDestinationSidLength
0x180066bf4  call    cs:__imp_CopySid
0x180066bfa  test    eax, eax
0x180066bfc  jz      short loc_180066C26
0x180066bfe  mov     [r14], rsi
0x180066c01  xor     eax, eax
0x180066c03  mov     rsi, [rsp+28h+arg_0]
0x180066c08  mov     rdi, [rsp+28h+arg_8]
0x180066c0d  mov     rbx, [rsp+28h+arg_10]
0x180066c12  add     rsp, 20h
0x180066c16  pop     r14
0x180066c18  retn
0x180066c19  mov     ecx, 57h ; 'W'; dwErrCode
0x180066c1e  call    cs:__imp_SetLastError
0x180066c24  xor     esi, esi
0x180066c26  call    cs:__imp_GetLastError
0x180066c2c  mov     ebx, eax
0x180066c2e  test    eax, eax
0x180066c30  jnz     short loc_180066C43
0x180066c32  mov     eax, ebx
0x180066c34  jmp     short loc_180066C03
0x180066c36  mov     ecx, 8; dwErrCode
0x180066c3b  call    cs:__imp_SetLastError
0x180066c41  jmp     short loc_180066C26
0x180066c43  test    rsi, rsi
0x180066c46  jz      short loc_180066C32
0x180066c48  mov     rcx, rsi
0x180066c4b  call    FreeWLMem
0x180066c50  jmp     short loc_180066C32
0x180066c52  mov     eax, 57h ; 'W'
0x180066c57  jmp     short loc_180066C0D
```
