# DeletePathEngine

- ea: `0x18000b5f8`
- end: `0x18000b718`
- name: `DeletePathEngine`
- size: `288`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b720`

## callees

- `0x180008f64`
- `0x180009ee4`
- `0x18000b348`
- `0x18000b5f8`
- `0x18000bb18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b6fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b6fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b66d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b6e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b6e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b6f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b6f1`

## string_xrefs

- `0x18000b69d`: `DeletePathEngine: Hit %u failure%s during recursive deletion of [%s]; 1st error = 0x%x, cd = [%s]`

## pseudocode

```c
__int64 __fastcall DeletePathEngine(const WCHAR *a1)
{
  unsigned int v2; // ebx
  void *CurrDirectory; // rbx
  HANDLE ProcessHeap; // rax
  __int64 dwErrCode; // [rsp+40h] [rbp-20h]

  dwErrCode = 0;
  v2 = EnumeratePathEx(a1, 1);
  if ( !(unsigned int)WdsRemoveDirectoryWithFlags((__int64)a1, 32) )
    dwErrCode = GetLastError() | 0x100000000LL;
  if ( HIDWORD(dwErrCode) )
  {
    CurrDirectory = (void *)GetCurrDirectory();
    LibLog(
      &g_WdsLibLog,
      0x4000000,
      L"DeletePathEngine: Hit %u failure%s during recursive deletion of [%s]; 1st error = 0x%x, cd = [%s]");
    if ( CurrDirectory )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, CurrDirectory);
    }
    if ( (_DWORD)dwErrCode )
      SetLastError(dwErrCode);
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18000b5f8  mov     [rsp-8+arg_0], rbx
0x18000b5fd  mov     [rsp-8+arg_8], rdi
0x18000b602  push    rbp
0x18000b603  mov     rbp, rsp
0x18000b606  sub     rsp, 60h
0x18000b60a  lea     r9, [rbp+dwErrCode]
0x18000b60e  mov     qword ptr [rbp+dwErrCode], 0
0x18000b616  lea     r8, DeletePathFileCallback
0x18000b61d  mov     [rbp+var_18], 1
0x18000b624  lea     rdx, DeletePathDirectoryCallback
0x18000b62b  mov     [rbp+var_14], 20h ; ' '
0x18000b632  mov     rdi, rcx
0x18000b635  mov     [rbp+var_8], 0
0x18000b63d  mov     [rbp+var_10], 0
0x18000b645  mov     [rsp+60h+var_40], 1; int
0x18000b64d  call    EnumeratePathEx
0x18000b652  mov     edx, 20h ; ' '
0x18000b657  mov     rcx, rdi
0x18000b65a  mov     ebx, eax
0x18000b65c  call    WdsRemoveDirectoryWithFlags
0x18000b661  test    eax, eax
0x18000b663  jnz     short loc_18000B676
0x18000b665  inc     [rbp+dwErrCode+4]
0x18000b668  cmp     [rbp+dwErrCode], eax
0x18000b66b  jnz     short loc_18000B676
0x18000b66d  call    cs:__imp_GetLastError
0x18000b673  mov     [rbp+dwErrCode], eax
0x18000b676  cmp     [rbp+dwErrCode+4], 0
0x18000b67a  jbe     loc_18000B706
0x18000b680  call    GetCurrDirectory
0x18000b685  mov     r9d, [rbp+dwErrCode+4]
0x18000b689  lea     rcx, aUnavailable; "<unavailable>"
0x18000b690  test    rax, rax
0x18000b693  lea     rdx, aS_0; "s"
0x18000b69a  mov     rbx, rax
0x18000b69d  lea     r8, aDeletepathengi; "DeletePathEngine: Hit %u failure%s duri"...
0x18000b6a4  cmovnz  rcx, rax
0x18000b6a8  cmp     r9d, 1
0x18000b6ac  mov     [rsp+60h+var_28], rcx
0x18000b6b1  lea     rax, dword_180017A6C
0x18000b6b8  mov     ecx, [rbp+dwErrCode]
0x18000b6bb  cmovz   rdx, rax
0x18000b6bf  mov     [rsp+60h+var_30], ecx
0x18000b6c3  lea     rcx, g_WdsLibLog
0x18000b6ca  mov     [rsp+60h+var_38], rdi
0x18000b6cf  mov     qword ptr [rsp+60h+var_40], rdx
0x18000b6d4  mov     edx, 4000000h
0x18000b6d9  call    LibLog
0x18000b6de  test    rbx, rbx
0x18000b6e1  jz      short loc_18000B6F7
0x18000b6e3  call    cs:__imp_GetProcessHeap
0x18000b6e9  mov     r8, rbx; lpMem
0x18000b6ec  xor     edx, edx; dwFlags
0x18000b6ee  mov     rcx, rax; hHeap
0x18000b6f1  call    cs:__imp_HeapFree
0x18000b6f7  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18000b6fa  test    ecx, ecx
0x18000b6fc  jz      short loc_18000B704
0x18000b6fe  call    cs:__imp_SetLastError
0x18000b704  xor     ebx, ebx
0x18000b706  mov     rdi, [rsp+60h+arg_8]
0x18000b70b  mov     eax, ebx
0x18000b70d  mov     rbx, [rsp+60h+arg_0]
0x18000b712  add     rsp, 60h
0x18000b716  pop     rbp
0x18000b717  retn
```
