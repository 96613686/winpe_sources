# _CreateRecycleBinDirectory(ushort const *,int)

- ea: `0x1805ae234`
- end: `0x1805ae410`
- name: `?_CreateRecycleBinDirectory@@YAJPEBGH@Z`
- size: `476`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180312150`

## callees

- `0x18004e06c`
- `0x180133f50`
- `0x1803b1f60`
- `0x1805ae234`
- `0x1805ae5b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ae339`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ae3a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ae339`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ae3a6`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1805ae290`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1805ae290`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1805ae328`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1805ae3dd`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1805ae328`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1805ae3dd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1805ae30e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1805ae386`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1805ae3b6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1805ae30e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1805ae386`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1805ae3b6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1805ae2a9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1805ae2a9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1805ae2d8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1805ae2d8`

## pseudocode

```c
__int64 __fastcall _CreateRecycleBinDirectory(const unsigned __int16 *a1, int a2)
{
  unsigned int v3; // r10d
  int RecycleBinSecurityDescriptor; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-E0h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-D8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( a2 )
  {
    if ( (int)StringCchCopyW(pszPath, 0x104u, a1) >= 0
      && PathCchRemoveFileSpec(pszPath, v3) >= 0
      && !PathFileExistsW(pszPath) )
    {
      SecurityDescriptor = 0;
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"D:P(A;CIOI;GA;;;BA)(A;CIOI;GA;;;SY)(A;NP;0x001201AD;;;BU)S:(ML;CIOIIO;1;;;LW)",
             1u,
             &SecurityDescriptor,
             0) )
      {
        SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
        *(_QWORD *)&SecurityAttributes.nLength = 24;
        *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
        if ( CreateDirectoryW(pszPath, &SecurityAttributes) )
          SetFileAttributesW(pszPath, 6u);
        LocalFree(SecurityDescriptor);
      }
    }
    hMem = 0;
    RecycleBinSecurityDescriptor = _GetRecycleBinSecurityDescriptor(&hMem);
    if ( RecycleBinSecurityDescriptor < 0 )
      return (unsigned int)RecycleBinSecurityDescriptor;
    SecurityAttributes.lpSecurityDescriptor = hMem;
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    if ( CreateDirectoryW(a1, &SecurityAttributes) )
      RecycleBinSecurityDescriptor = 0;
    else
      RecycleBinSecurityDescriptor = ResultFromKnownLastError();
    LocalFree(hMem);
  }
  else
  {
    if ( CreateDirectoryW(a1, 0) )
    {
      RecycleBinSecurityDescriptor = 0;
LABEL_18:
      SetFileAttributesW(a1, 6u);
      return (unsigned int)RecycleBinSecurityDescriptor;
    }
    RecycleBinSecurityDescriptor = ResultFromKnownLastError();
  }
  if ( RecycleBinSecurityDescriptor >= 0 )
    goto LABEL_18;
  return (unsigned int)RecycleBinSecurityDescriptor;
}

```

## disassembly

```asm
0x1805ae234  mov     [rsp-8+arg_8], rbx
0x1805ae239  mov     [rsp-8+arg_10], rdi
0x1805ae23e  push    rbp
0x1805ae23f  lea     rbp, [rsp-170h]
0x1805ae247  sub     rsp, 270h
0x1805ae24e  mov     rax, cs:__security_cookie
0x1805ae255  xor     rax, rsp
0x1805ae258  mov     [rbp+170h+var_10], rax
0x1805ae25f  mov     rdi, rcx
0x1805ae262  test    edx, edx
0x1805ae264  jz      loc_1805AE3B4
0x1805ae26a  mov     r8, rcx; unsigned __int16 *
0x1805ae26d  mov     r10d, 104h
0x1805ae273  mov     edx, r10d; unsigned __int64
0x1805ae276  lea     rcx, [rsp+270h+pszPath]; unsigned __int16 *
0x1805ae27b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805ae280  test    eax, eax
0x1805ae282  js      loc_1805AE345
0x1805ae288  mov     edx, r10d; cchPath
0x1805ae28b  lea     rcx, [rsp+270h+pszPath]; pszPath
0x1805ae290  call    cs:__imp_PathCchRemoveFileSpec
0x1805ae297  nop     dword ptr [rax+rax+00h]
0x1805ae29c  test    eax, eax
0x1805ae29e  js      loc_1805AE345
0x1805ae2a4  lea     rcx, [rsp+270h+pszPath]; pszPath
0x1805ae2a9  call    cs:__imp_PathFileExistsW
0x1805ae2b0  nop     dword ptr [rax+rax+00h]
0x1805ae2b5  test    eax, eax
0x1805ae2b7  jnz     loc_1805AE345
0x1805ae2bd  xor     r9d, r9d; SecurityDescriptorSize
0x1805ae2c0  mov     [rsp+270h+SecurityDescriptor], 0
0x1805ae2c9  lea     r8, [rsp+270h+SecurityDescriptor]; SecurityDescriptor
0x1805ae2ce  lea     edx, [rax+1]; StringSDRevision
0x1805ae2d1  lea     rcx, StringSecurityDescriptor; "D:P(A;CIOI;GA;;;BA)(A;CIOI;GA;;;SY)(A;N"...
0x1805ae2d8  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1805ae2df  nop     dword ptr [rax+rax+00h]
0x1805ae2e4  test    eax, eax
0x1805ae2e6  jz      short loc_1805AE345
0x1805ae2e8  mov     rax, [rsp+270h+SecurityDescriptor]
0x1805ae2ed  lea     rdx, [rsp+270h+SecurityAttributes]; lpSecurityAttributes
0x1805ae2f2  lea     rcx, [rsp+270h+pszPath]; lpPathName
0x1805ae2f7  mov     [rsp+270h+SecurityAttributes.lpSecurityDescriptor], rax
0x1805ae2fc  mov     qword ptr [rsp+270h+SecurityAttributes.nLength], 18h
0x1805ae305  mov     qword ptr [rsp+270h+SecurityAttributes.bInheritHandle], 0
0x1805ae30e  call    cs:__imp_CreateDirectoryW
0x1805ae315  nop     dword ptr [rax+rax+00h]
0x1805ae31a  test    eax, eax
0x1805ae31c  jz      short loc_1805AE334
0x1805ae31e  mov     edx, 6; dwFileAttributes
0x1805ae323  lea     rcx, [rsp+270h+pszPath]; lpFileName
0x1805ae328  call    cs:__imp_SetFileAttributesW
0x1805ae32f  nop     dword ptr [rax+rax+00h]
0x1805ae334  mov     rcx, [rsp+270h+SecurityDescriptor]; hMem
0x1805ae339  call    cs:__imp_LocalFree
0x1805ae340  nop     dword ptr [rax+rax+00h]
0x1805ae345  lea     rcx, [rsp+270h+hMem]; SecurityDescriptor
0x1805ae34a  mov     [rsp+270h+hMem], 0
0x1805ae353  call    ?_GetRecycleBinSecurityDescriptor@@YAJPEAPEAX@Z; _GetRecycleBinSecurityDescriptor(void * *)
0x1805ae358  mov     ebx, eax
0x1805ae35a  test    eax, eax
0x1805ae35c  js      loc_1805AE3E9
0x1805ae362  mov     rax, [rsp+270h+hMem]
0x1805ae367  lea     rdx, [rsp+270h+SecurityAttributes]; lpSecurityAttributes
0x1805ae36c  mov     rcx, rdi; lpPathName
0x1805ae36f  mov     [rsp+270h+SecurityAttributes.lpSecurityDescriptor], rax
0x1805ae374  mov     qword ptr [rsp+270h+SecurityAttributes.nLength], 18h
0x1805ae37d  mov     qword ptr [rsp+270h+SecurityAttributes.bInheritHandle], 0
0x1805ae386  call    cs:__imp_CreateDirectoryW
0x1805ae38d  nop     dword ptr [rax+rax+00h]
0x1805ae392  test    eax, eax
0x1805ae394  jz      short loc_1805AE39A
0x1805ae396  xor     ebx, ebx
0x1805ae398  jmp     short loc_1805AE3A1
0x1805ae39a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1805ae39f  mov     ebx, eax
0x1805ae3a1  mov     rcx, [rsp+270h+hMem]; hMem
0x1805ae3a6  call    cs:__imp_LocalFree
0x1805ae3ad  nop     dword ptr [rax+rax+00h]
0x1805ae3b2  jmp     short loc_1805AE3D1
0x1805ae3b4  xor     edx, edx; lpSecurityAttributes
0x1805ae3b6  call    cs:__imp_CreateDirectoryW
0x1805ae3bd  nop     dword ptr [rax+rax+00h]
0x1805ae3c2  test    eax, eax
0x1805ae3c4  jz      short loc_1805AE3CA
0x1805ae3c6  xor     ebx, ebx
0x1805ae3c8  jmp     short loc_1805AE3D5
0x1805ae3ca  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1805ae3cf  mov     ebx, eax
0x1805ae3d1  test    ebx, ebx
0x1805ae3d3  js      short loc_1805AE3E9
0x1805ae3d5  mov     edx, 6; dwFileAttributes
0x1805ae3da  mov     rcx, rdi; lpFileName
0x1805ae3dd  call    cs:__imp_SetFileAttributesW
0x1805ae3e4  nop     dword ptr [rax+rax+00h]
0x1805ae3e9  mov     eax, ebx
0x1805ae3eb  mov     rcx, [rbp+170h+var_10]
0x1805ae3f2  xor     rcx, rsp; StackCookie
0x1805ae3f5  call    __security_check_cookie
0x1805ae3fa  lea     r11, [rsp+270h+var_s0]
0x1805ae402  mov     rbx, [r11+18h]
0x1805ae406  mov     rdi, [r11+20h]
0x1805ae40a  mov     rsp, r11
0x1805ae40d  pop     rbp
0x1805ae40e  retn
```
