# _CreateNamedSection

- ea: `0x180004860`
- end: `0x1800048eb`
- name: `_CreateNamedSection`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180005a64`

## callees

- `0x180004860`
- `0x1800048f4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800048e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800048e3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18000488f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18000488f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800048d5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800048d5`

## pseudocode

```c
HANDLE __fastcall CreateNamedSection(__int64 a1, __int64 a2, __int64 a3, const WCHAR *a4)
{
  HANDLE v4; // rbx
  int v6; // eax
  __int64 v7; // rdx
  _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+30h] [rbp-28h] BYREF

  v4 = 0;
  *(_QWORD *)&FileMappingAttributes.nLength = 24;
  *(_QWORD *)&FileMappingAttributes.bInheritHandle = 0;
  FileMappingAttributes.lpSecurityDescriptor = 0;
  v6 = StrCmpNICW(a4, L"Global\\", 7);
  if ( (int)_CreateSharedHandleACL(v6 == 0, v7, &FileMappingAttributes.lpSecurityDescriptor) >= 0 )
  {
    v4 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, 0xECu, a4);
    LocalFree(FileMappingAttributes.lpSecurityDescriptor);
  }
  return v4;
}

```

## disassembly

```asm
0x180004860  mov     rax, rsp
0x180004863  mov     [rax+8], rbx
0x180004867  push    rdi
0x180004868  sub     rsp, 50h
0x18000486c  xor     ebx, ebx
0x18000486e  mov     qword ptr [rax-28h], 18h
0x180004876  lea     rdx, pszStr2; "Global\\"
0x18000487d  mov     [rax-18h], rbx
0x180004881  mov     rcx, r9; pszStr1
0x180004884  mov     [rax-20h], rbx
0x180004888  mov     rdi, r9
0x18000488b  lea     r8d, [rbx+7]; nChar
0x18000488f  call    cs:__imp_StrCmpNICW
0x180004895  xor     ecx, ecx
0x180004897  lea     r8, [rsp+58h+FileMappingAttributes.lpSecurityDescriptor]; void **
0x18000489c  test    eax, eax
0x18000489e  setz    cl; int
0x1800048a1  call    ?_CreateSharedHandleACL@@YAJHKPEAPEAX@Z; _CreateSharedHandleACL(int,ulong,void * *)
0x1800048a6  test    eax, eax
0x1800048a8  jns     short loc_1800048B8
0x1800048aa  mov     rax, rbx
0x1800048ad  mov     rbx, [rsp+58h+arg_0]
0x1800048b2  add     rsp, 50h
0x1800048b6  pop     rdi
0x1800048b7  retn
0x1800048b8  xor     r9d, r9d; dwMaximumSizeHigh
0x1800048bb  mov     [rsp+58h+lpName], rdi; lpName
0x1800048c0  lea     rdx, [rsp+58h+FileMappingAttributes]; lpFileMappingAttributes
0x1800048c5  mov     [rsp+58h+dwMaximumSizeLow], 0ECh; dwMaximumSizeLow
0x1800048cd  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800048d1  lea     r8d, [r9+4]; flProtect
0x1800048d5  call    cs:__imp_CreateFileMappingW
0x1800048db  mov     rcx, [rsp+58h+FileMappingAttributes.lpSecurityDescriptor]; hMem
0x1800048e0  mov     rbx, rax
0x1800048e3  call    cs:__imp_LocalFree
0x1800048e9  jmp     short loc_1800048AA
```
