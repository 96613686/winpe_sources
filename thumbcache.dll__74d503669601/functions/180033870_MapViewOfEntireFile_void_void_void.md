# MapViewOfEntireFile(void *,void * *,void * *)

- ea: `0x180033870`
- end: `0x180033942`
- name: `?MapViewOfEntireFile@@YAJPEAXPEAPEAX1@Z`
- size: `210`
- prototype: `__int64 __fastcall(void *, void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e6a0`

## callees

- `0x18000b3c0`
- `0x18002a538`
- `0x180033870`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800338fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800338fc`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800338ac`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800338ac`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800338d7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800338d7`

## string_xrefs

- `0x18003391f`: `onecoreuap\shell\ext\thumbnailcache\common\util.cpp`
- `0x180033910`: `Thumbnail Cache: Couldn't map view!`

## pseudocode

```c
__int64 __fastcall MapViewOfEntireFile(void *a1, void **a2, void **a3)
{
  HANDLE FileMappingW; // rax
  void *v6; // rdi
  void *v7; // rax
  int Error; // ebx
  const char *v10; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a2 = 0;
  *a3 = 0;
  FileMappingW = CreateFileMappingW(a1, 0, 4u, 0, 0, 0);
  v6 = FileMappingW;
  if ( !FileMappingW )
  {
    Error = ResultFromKnownLastError();
    goto LABEL_8;
  }
  *a2 = 0;
  v7 = MapViewOfFile(FileMappingW, 6u, 0, 0, 0);
  if ( v7 )
  {
    *a2 = v7;
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      CloseHandle(v6);
      goto LABEL_8;
    }
  }
  *a3 = v6;
LABEL_8:
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x31,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\util.cpp",
    (const char *)(unsigned int)Error,
    (__int64)"Thumbnail Cache: Couldn't map view!",
    v10);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180033870  mov     rax, rsp
0x180033873  mov     [rax+8], rbx
0x180033877  mov     [rax+10h], rsi
0x18003387b  push    rdi
0x18003387c  sub     rsp, 30h
0x180033880  mov     qword ptr [rdx], 0
0x180033887  xor     r9d, r9d; dwMaximumSizeHigh
0x18003388a  mov     rsi, r8
0x18003388d  mov     qword ptr [r8], 0
0x180033894  mov     rbx, rdx
0x180033897  mov     qword ptr [rax-10h], 0
0x18003389f  xor     edx, edx; lpFileMappingAttributes
0x1800338a1  mov     dword ptr [rax-18h], 0
0x1800338a8  lea     r8d, [r9+4]; flProtect
0x1800338ac  call    cs:__imp_CreateFileMappingW
0x1800338b2  mov     rdi, rax
0x1800338b5  test    rax, rax
0x1800338b8  jz      short loc_180033904
0x1800338ba  xor     r9d, r9d; dwFileOffsetLow
0x1800338bd  mov     qword ptr [rbx], 0
0x1800338c4  xor     r8d, r8d; dwFileOffsetHigh
0x1800338c7  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x1800338d0  mov     rcx, rax; hFileMappingObject
0x1800338d3  lea     edx, [r9+6]; dwDesiredAccess
0x1800338d7  call    cs:__imp_MapViewOfFile
0x1800338dd  test    rax, rax
0x1800338e0  jz      short loc_1800338E9
0x1800338e2  mov     [rbx], rax
0x1800338e5  xor     ebx, ebx
0x1800338e7  jmp     short loc_1800338F4
0x1800338e9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800338ee  mov     ebx, eax
0x1800338f0  test    eax, eax
0x1800338f2  js      short loc_1800338F9
0x1800338f4  mov     [rsi], rdi
0x1800338f7  jmp     short loc_18003390B
0x1800338f9  mov     rcx, rdi; hObject
0x1800338fc  call    cs:__imp_CloseHandle
0x180033902  jmp     short loc_18003390B
0x180033904  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180033909  mov     ebx, eax
0x18003390b  mov     rcx, [rsp+38h]; this
0x180033910  lea     rax, aThumbnailCache; "Thumbnail Cache: Couldn't map view!"
0x180033917  mov     r9d, ebx; char *
0x18003391a  mov     [rsp+38h+dwNumberOfBytesToMap], rax; __int64
0x18003391f  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180033926  mov     edx, 31h ; '1'; void *
0x18003392b  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180033930  mov     rsi, [rsp+38h+arg_8]
0x180033935  mov     eax, ebx
0x180033937  mov     rbx, [rsp+38h+arg_0]
0x18003393c  add     rsp, 30h
0x180033940  pop     rdi
0x180033941  retn
```
