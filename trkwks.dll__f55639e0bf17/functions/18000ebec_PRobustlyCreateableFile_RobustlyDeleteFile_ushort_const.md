# PRobustlyCreateableFile::RobustlyDeleteFile(ushort const *)

- ea: `0x18000ebec`
- end: `0x18000ecae`
- name: `?RobustlyDeleteFile@PRobustlyCreateableFile@@IEAAXPEBG@Z`
- size: `194`
- prototype: `void __fastcall(PRobustlyCreateableFile *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000c158`
- `0x18000f440`

## callees

- `0x18000b3f0`
- `0x18000b4a0`
- `0x18000d038`
- `0x18000ebec`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000eca7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000eca7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000ec7b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000ec7b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000ec48`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000ec48`

## pseudocode

```c
void __fastcall PRobustlyCreateableFile::RobustlyDeleteFile(PRobustlyCreateableFile *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  WCHAR NewFileName[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( (int)StringCchCopyW(NewFileName, 0x105u, a2) < 0 || (int)StringCchCatW(NewFileName, 0x105u, L".bak") < 0 )
  {
    RaiseException(0x80000005, 0, 0, 0);
    JUMPOUT(0x18000ECADLL);
  }
  if ( MoveFileExW(a2, NewFileName, 1u) )
  {
    DeleteFileW(NewFileName);
  }
  else if ( GetLastError() != 3 && GetLastError() != 2 )
  {
    LastError = GetLastError();
    TrkRaiseWin32Error(LastError);
  }
}

```

## disassembly

```asm
0x18000ebec  push    rbx
0x18000ebee  sub     rsp, 250h
0x18000ebf5  mov     rax, cs:__security_cookie
0x18000ebfc  xor     rax, rsp
0x18000ebff  mov     [rsp+258h+var_18], rax
0x18000ec07  mov     rbx, rdx
0x18000ec0a  lea     rcx, [rsp+258h+NewFileName]; unsigned __int16 *
0x18000ec0f  mov     r8, rdx; unsigned __int16 *
0x18000ec12  mov     edx, 105h; unsigned __int64
0x18000ec17  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ec1c  test    eax, eax
0x18000ec1e  js      short loc_18000EC9A
0x18000ec20  lea     r8, aBak; ".bak"
0x18000ec27  mov     edx, 105h; unsigned __int64
0x18000ec2c  lea     rcx, [rsp+258h+NewFileName]; unsigned __int16 *
0x18000ec31  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ec36  test    eax, eax
0x18000ec38  js      short loc_18000EC9A
0x18000ec3a  mov     r8d, 1; dwFlags
0x18000ec40  lea     rdx, [rsp+258h+NewFileName]; lpNewFileName
0x18000ec45  mov     rcx, rbx; lpExistingFileName
0x18000ec48  call    cs:__imp_MoveFileExW
0x18000ec4e  test    eax, eax
0x18000ec50  jnz     short loc_18000EC76
0x18000ec52  call    cs:__imp_GetLastError
0x18000ec58  cmp     eax, 3
0x18000ec5b  jz      short loc_18000EC81
0x18000ec5d  call    cs:__imp_GetLastError
0x18000ec63  cmp     eax, 2
0x18000ec66  jz      short loc_18000EC81
0x18000ec68  call    cs:__imp_GetLastError
0x18000ec6e  mov     ecx, eax; int
0x18000ec70  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000ec76  lea     rcx, [rsp+258h+NewFileName]; lpFileName
0x18000ec7b  call    cs:__imp_DeleteFileW
0x18000ec81  mov     rcx, [rsp+258h+var_18]
0x18000ec89  xor     rcx, rsp; StackCookie
0x18000ec8c  call    __security_check_cookie
0x18000ec91  add     rsp, 250h
0x18000ec98  pop     rbx
0x18000ec99  retn
0x18000ec9a  xor     r9d, r9d; lpArguments
0x18000ec9d  xor     r8d, r8d; nNumberOfArguments
0x18000eca0  xor     edx, edx; dwExceptionFlags
0x18000eca2  mov     ecx, 80000005h; dwExceptionCode
0x18000eca7  call    cs:__imp_RaiseException
```
