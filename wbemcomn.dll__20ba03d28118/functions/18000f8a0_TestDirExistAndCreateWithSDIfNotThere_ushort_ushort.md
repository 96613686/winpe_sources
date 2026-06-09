# TestDirExistAndCreateWithSDIfNotThere(ushort *,ushort *)

- ea: `0x18000f8a0`
- end: `0x18000f97f`
- name: `?TestDirExistAndCreateWithSDIfNotThere@@YAJPEAG0@Z`
- size: `223`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000eed4`

## callees

- `0x18000f8a0`
- `0x1800440ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f965`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f974`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f974`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000f95b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000f95b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000f8cf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000f8cf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000f8b2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000f8b2`

## pseudocode

```c
__int64 __fastcall TestDirExistAndCreateWithSDIfNotThere(LPCWSTR lpPathName, unsigned __int16 *a2)
{
  DWORD FileAttributesW; // ebx
  DWORD LastError; // eax
  unsigned int v6; // edx
  DWORD v7; // edi
  __int64 result; // rax
  HLOCAL v9; // rbx
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+20h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+18h] BYREF
  HLOCAL v12; // [rsp+78h] [rbp+20h]

  FileAttributesW = GetFileAttributesW(lpPathName);
  LastError = GetLastError();
  v7 = LastError;
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) != 0 )
      return 0;
    if ( !DeleteFileW(lpPathName) )
      return GetLastError() | 0x80070000;
    goto LABEL_11;
  }
  if ( LastError == 2 || LastError == 3 )
  {
LABEL_11:
    hMem = 0;
    if ( !(unsigned int)DLConvertStringSecurityDescriptorToSecurityDescriptorW(a2, v6, &hMem, 0) )
      return GetLastError() | 0x80070000;
    v9 = hMem;
    v12 = hMem;
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = hMem;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    if ( CreateDirectoryW(lpPathName, &SecurityAttributes) )
      v7 = 0;
    else
      v7 = GetLastError();
    LocalFree(v9);
  }
  result = 0;
  if ( v7 )
    return v7 | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000f8a0  mov     [rsp+arg_0], rbx
0x18000f8a5  push    rbp
0x18000f8a6  push    rsi
0x18000f8a7  push    rdi
0x18000f8a8  sub     rsp, 40h
0x18000f8ac  mov     rbp, rdx
0x18000f8af  mov     rsi, rcx
0x18000f8b2  call    cs:__imp_GetFileAttributesW
0x18000f8b8  mov     ebx, eax
0x18000f8ba  call    cs:__imp_GetLastError
0x18000f8c0  mov     edi, eax
0x18000f8c2  cmp     ebx, 0FFFFFFFFh
0x18000f8c5  jz      short loc_18000F90B
0x18000f8c7  test    bl, 10h
0x18000f8ca  jnz     short loc_18000F8E6
0x18000f8cc  mov     rcx, rsi; lpFileName
0x18000f8cf  call    cs:__imp_DeleteFileW
0x18000f8d5  test    eax, eax
0x18000f8d7  jnz     short loc_18000F910
0x18000f8d9  call    cs:__imp_GetLastError
0x18000f8df  or      eax, 80070000h
0x18000f8e4  jmp     short loc_18000F8FE
0x18000f8e6  xor     eax, eax
0x18000f8e8  jmp     short loc_18000F8FE
0x18000f8ea  cmp     eax, 3
0x18000f8ed  jz      short loc_18000F910
0x18000f8ef  mov     ecx, edi
0x18000f8f1  or      ecx, 80070000h
0x18000f8f7  xor     eax, eax
0x18000f8f9  test    edi, edi
0x18000f8fb  cmovnz  eax, ecx
0x18000f8fe  mov     rbx, [rsp+58h+arg_0]
0x18000f903  add     rsp, 40h
0x18000f907  pop     rdi
0x18000f908  pop     rsi
0x18000f909  pop     rbp
0x18000f90a  retn
0x18000f90b  cmp     eax, 2
0x18000f90e  jnz     short loc_18000F8EA
0x18000f910  mov     [rsp+58h+hMem], 0
0x18000f919  xor     r9d, r9d; unsigned int *
0x18000f91c  lea     r8, [rsp+58h+hMem]; void **
0x18000f921  mov     rcx, rbp; unsigned __int16 *
0x18000f924  call    ?DLConvertStringSecurityDescriptorToSecurityDescriptorW@@YAHPEBGKPEAPEAXPEAK@Z; DLConvertStringSecurityDescriptorToSecurityDescriptorW(ushort const *,ulong,void * *,ulong *)
0x18000f929  test    eax, eax
0x18000f92b  jz      short loc_18000F8D9
0x18000f92d  mov     rbx, [rsp+58h+hMem]
0x18000f932  mov     [rsp+58h+arg_18], rbx
0x18000f937  mov     qword ptr [rsp+58h+SecurityAttributes.nLength], 18h
0x18000f940  mov     rax, [rsp+58h+hMem]
0x18000f945  mov     [rsp+58h+SecurityAttributes.lpSecurityDescriptor], rax
0x18000f94a  mov     qword ptr [rsp+58h+SecurityAttributes.bInheritHandle], 0
0x18000f953  lea     rdx, [rsp+58h+SecurityAttributes]; lpSecurityAttributes
0x18000f958  mov     rcx, rsi; lpPathName
0x18000f95b  call    cs:__imp_CreateDirectoryW
0x18000f961  test    eax, eax
0x18000f963  jnz     short loc_18000F96F
0x18000f965  call    cs:__imp_GetLastError
0x18000f96b  mov     edi, eax
0x18000f96d  jmp     short loc_18000F971
0x18000f96f  xor     edi, edi
0x18000f971  mov     rcx, rbx; hMem
0x18000f974  call    cs:__imp_LocalFree
0x18000f97a  jmp     loc_18000F8EF
```
