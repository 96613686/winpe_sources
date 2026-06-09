# SrmCreateFileWithAlternateAccess(ushort const *,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,bool,ulong *)

- ea: `0x18007c030`
- end: `0x18007c166`
- name: `?SrmCreateFileWithAlternateAccess@@YAPEAXPEBGKKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX_NPEAK@Z`
- size: `310`
- prototype: `HANDLE __fastcall(LPCWSTR lpFileName, DWORD, DWORD, DWORD, struct _SECURITY_ATTRIBUTES *, unsigned int, DWORD dwFlagsAndAttributes, void *, bool, FILETIME LastAccessTime)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007cdec`
- `0x18008a024`
- `0x180096d3c`

## callees

- `0x18007c030`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18007c0b6`
- `KERNEL32!CreateFileW` at `0x18007c105`
- `KERNEL32!CreateFileW` at `0x18007c0b6`
- `KERNEL32!CreateFileW` at `0x18007c105`
- `KERNEL32!GetLastError` at `0x18007c0d2`
- `KERNEL32!GetLastError` at `0x18007c0d2`
- `KERNEL32!SetFileTime` at `0x18007c145`
- `KERNEL32!SetFileTime` at `0x18007c145`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18007c06e`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18007c083`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18007c06e`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18007c083`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
HANDLE __fastcall SrmCreateFileWithAlternateAccess(
        LPCWSTR lpFileName,
        DWORD a2,
        DWORD a3,
        DWORD a4,
        struct _SECURITY_ATTRIBUTES *a5,
        unsigned int a6,
        DWORD dwFlagsAndAttributes,
        void *a8,
        bool a9,
        FILETIME LastAccessTime)
{
  DWORD *v12; // rbx
  DWORD v13; // edi
  DWORD v14; // r15d
  HANDLE FileW; // rsi
  DWORD AccessMask; // [rsp+78h] [rbp+10h] BYREF
  DWORD dwDesiredAccess; // [rsp+80h] [rbp+18h] BYREF

  dwDesiredAccess = a3;
  AccessMask = a2;
  v12 = (DWORD *)LastAccessTime;
  if ( LastAccessTime )
    *(_DWORD *)LastAccessTime.dwLowDateTime = 0;
  MapGenericMask(&AccessMask, (PGENERIC_MAPPING)&GenericMapping);
  MapGenericMask(&dwDesiredAccess, (PGENERIC_MAPPING)&GenericMapping);
  v13 = AccessMask;
  v14 = dwFlagsAndAttributes;
  FileW = CreateFileW(lpFileName, AccessMask, a4, 0, 3u, dwFlagsAndAttributes, 0);
  if ( FileW != (HANDLE)-1LL
    || dwDesiredAccess != v13
    && GetLastError() == 5
    && (v13 = dwDesiredAccess, FileW = CreateFileW(lpFileName, dwDesiredAccess, a4, 0, 3u, v14, 0),
                               FileW != (HANDLE)-1LL) )
  {
    if ( a9 && (v13 & 0x100) != 0 )
    {
      LastAccessTime = (FILETIME)-1LL;
      SetFileTime(FileW, 0, &LastAccessTime, 0);
    }
    if ( v12 )
      *v12 = v13;
  }
  return FileW;
}

```

## disassembly

```asm
0x18007c030  mov     [rsp+arg_0], rbx
0x18007c035  mov     [rsp+dwDesiredAccess], r8d
0x18007c03a  mov     [rsp+AccessMask], edx
0x18007c03e  push    rbp
0x18007c03f  push    rsi
0x18007c040  push    rdi
0x18007c041  push    r14
0x18007c043  push    r15
0x18007c045  sub     rsp, 40h
0x18007c049  mov     ebp, r9d
0x18007c04c  mov     r14, rcx
0x18007c04f  mov     rbx, qword ptr [rsp+68h+LastAccessTime.dwLowDateTime]
0x18007c057  test    rbx, rbx
0x18007c05a  jz      short loc_18007C062
0x18007c05c  mov     dword ptr [rbx], 0
0x18007c062  lea     rdx, GenericMapping; GenericMapping
0x18007c069  lea     rcx, [rsp+68h+AccessMask]; AccessMask
0x18007c06e  call    cs:__imp_MapGenericMask
0x18007c074  lea     rdx, GenericMapping; GenericMapping
0x18007c07b  lea     rcx, [rsp+68h+dwDesiredAccess]; AccessMask
0x18007c083  call    cs:__imp_MapGenericMask
0x18007c089  mov     edi, [rsp+68h+AccessMask]
0x18007c08d  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18007c096  mov     r15d, [rsp+68h+arg_30]
0x18007c09e  mov     [rsp+68h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18007c0a3  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18007c0ab  xor     r9d, r9d; lpSecurityAttributes
0x18007c0ae  mov     r8d, ebp; dwShareMode
0x18007c0b1  mov     edx, edi; dwDesiredAccess
0x18007c0b3  mov     rcx, r14; lpFileName
0x18007c0b6  call    cs:__imp_CreateFileW
0x18007c0bc  mov     rsi, rax
0x18007c0bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007c0c3  jnz     short loc_18007C114
0x18007c0c5  cmp     [rsp+68h+dwDesiredAccess], edi
0x18007c0cc  jz      loc_18007C152
0x18007c0d2  call    cs:__imp_GetLastError
0x18007c0d8  cmp     eax, 5
0x18007c0db  jnz     short loc_18007C152
0x18007c0dd  mov     edi, [rsp+68h+dwDesiredAccess]
0x18007c0e4  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18007c0ed  mov     [rsp+68h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18007c0f2  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18007c0fa  xor     r9d, r9d; lpSecurityAttributes
0x18007c0fd  mov     r8d, ebp; dwShareMode
0x18007c100  mov     edx, edi; dwDesiredAccess
0x18007c102  mov     rcx, r14; lpFileName
0x18007c105  call    cs:__imp_CreateFileW
0x18007c10b  mov     rsi, rax
0x18007c10e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007c112  jz      short loc_18007C152
0x18007c114  cmp     [rsp+68h+arg_40], 0
0x18007c11c  jz      short loc_18007C14B
0x18007c11e  bt      edi, 8
0x18007c122  jnb     short loc_18007C14B
0x18007c124  or      eax, 0FFFFFFFFh
0x18007c127  mov     [rsp+68h+LastAccessTime.dwLowDateTime], eax
0x18007c12e  mov     [rsp+68h+LastAccessTime.dwHighDateTime], eax
0x18007c135  xor     r9d, r9d; lpLastWriteTime
0x18007c138  lea     r8, [rsp+68h+LastAccessTime]; lpLastAccessTime
0x18007c140  xor     edx, edx; lpCreationTime
0x18007c142  mov     rcx, rsi; hFile
0x18007c145  call    cs:__imp_SetFileTime
0x18007c14b  test    rbx, rbx
0x18007c14e  jz      short loc_18007C152
0x18007c150  mov     [rbx], edi
0x18007c152  mov     rax, rsi
0x18007c155  mov     rbx, [rsp+68h+arg_0]
0x18007c15a  add     rsp, 40h
0x18007c15e  pop     r15
0x18007c160  pop     r14
0x18007c162  pop     rdi
0x18007c163  pop     rsi
0x18007c164  pop     rbp
0x18007c165  retn
```
