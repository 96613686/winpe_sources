# CThemeServer::LoadRemoteTheme(ushort const *,ushort const *,ushort const *,ulong,void *,void *)

- ea: `0x18000d91c`
- end: `0x18000da73`
- name: `?LoadRemoteTheme@CThemeServer@@QEAAJPEBG00KPEAX1@Z`
- size: `343`
- prototype: `__int64 __fastcall(CThemeServer *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, HANDLE hSourceHandle, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000d524`

## callees

- `0x180006a08`
- `0x18000d868`
- `0x18000d91c`
- `0x18000f2d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d9e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d9e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da5e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000da17`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000da17`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000da4c`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000da4c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000d981`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000d981`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000d953`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000d953`

## pseudocode

```c
__int64 __fastcall CThemeServer::LoadRemoteTheme(
        CThemeServer *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        HANDLE hSourceHandle,
        void *a7)
{
  HANDLE FileMappingW; // rax
  void *v12; // rsi
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rdi
  unsigned int v16; // r11d
  unsigned int v17; // r11d
  void *v18; // rbx
  HANDLE CurrentProcess; // rax
  int v20; // r8d
  unsigned int ErrorLast; // eax
  unsigned int v22; // ebx
  HANDLE TargetHandle; // [rsp+40h] [rbp-48h] BYREF

  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x628u, 0);
  v12 = FileMappingW;
  if ( !FileMappingW )
    return 2147942414LL;
  v14 = (unsigned __int16 *)MapViewOfFile(FileMappingW, 2u, 0, 0, 0);
  v15 = v14;
  if ( v14 )
  {
    StringCchCopyW(v14, 0x104u, a2);
    StringCchCopyW(v15 + 260, v16, a3);
    StringCchCopyW(v15 + 520, v17, a4);
    *((_DWORD *)v15 + 390) = a5;
    v18 = *(void **)this;
    TargetHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( DuplicateHandle(CurrentProcess, hSourceHandle, v18, &TargetHandle, 0, 0, 2u) )
    {
      *((_QWORD *)v15 + 196) = TargetHandle;
      ErrorLast = CThemeServer::InjectRemoteSection(this, v12, v20, a7);
    }
    else
    {
      ErrorLast = MakeErrorLast();
    }
    v22 = ErrorLast;
    UnmapViewOfFile(v15);
  }
  else
  {
    v22 = MakeErrorLast();
  }
  CloseHandle(v12);
  return v22;
}

```

## disassembly

```asm
0x18000d91c  push    rbx
0x18000d91e  push    rbp
0x18000d91f  push    rsi
0x18000d920  push    rdi
0x18000d921  push    r14
0x18000d923  push    r15
0x18000d925  sub     rsp, 58h
0x18000d929  mov     rbx, r9
0x18000d92c  mov     [rsp+88h+lpName], 0; lpName
0x18000d935  xor     r9d, r9d; dwMaximumSizeHigh
0x18000d938  mov     [rsp+88h+dwMaximumSizeLow], 628h; dwMaximumSizeLow
0x18000d940  mov     rbp, r8
0x18000d943  mov     r15, rdx
0x18000d946  mov     r14, rcx
0x18000d949  xor     edx, edx; lpFileMappingAttributes
0x18000d94b  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18000d94f  lea     r8d, [r9+4]; flProtect
0x18000d953  call    cs:__imp_CreateFileMappingW
0x18000d959  mov     rsi, rax
0x18000d95c  test    rax, rax
0x18000d95f  jnz     short loc_18000D96B
0x18000d961  mov     eax, 8007000Eh
0x18000d966  jmp     loc_18000DA66
0x18000d96b  xor     r9d, r9d; dwFileOffsetLow
0x18000d96e  mov     qword ptr [rsp+88h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18000d977  xor     r8d, r8d; dwFileOffsetHigh
0x18000d97a  mov     rcx, rsi; hFileMappingObject
0x18000d97d  lea     edx, [r9+2]; dwDesiredAccess
0x18000d981  call    cs:__imp_MapViewOfFile
0x18000d987  mov     rdi, rax
0x18000d98a  test    rax, rax
0x18000d98d  jz      loc_18000DA54
0x18000d993  mov     r11d, 104h
0x18000d999  mov     r8, r15; unsigned __int16 *
0x18000d99c  mov     edx, r11d; unsigned __int64
0x18000d99f  mov     rcx, rax; unsigned __int16 *
0x18000d9a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d9a7  lea     rcx, [rdi+208h]; unsigned __int16 *
0x18000d9ae  mov     r8, rbp; unsigned __int16 *
0x18000d9b1  mov     edx, r11d; unsigned __int64
0x18000d9b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d9b9  lea     rcx, [rdi+410h]; unsigned __int16 *
0x18000d9c0  mov     r8, rbx; unsigned __int16 *
0x18000d9c3  mov     edx, r11d; unsigned __int64
0x18000d9c6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d9cb  mov     r11d, [rsp+88h+arg_20]
0x18000d9d3  mov     [rdi+618h], r11d
0x18000d9da  mov     rbx, [r14]
0x18000d9dd  mov     [rsp+88h+TargetHandle], 0
0x18000d9e6  call    cs:__imp_GetCurrentProcess
0x18000d9ec  mov     rdx, [rsp+88h+hSourceHandle]; hSourceHandle
0x18000d9f4  lea     r9, [rsp+88h+TargetHandle]; lpTargetHandle
0x18000d9f9  mov     [rsp+88h+dwOptions], 2; dwOptions
0x18000da01  mov     rcx, rax; hSourceProcessHandle
0x18000da04  mov     dword ptr [rsp+88h+lpName], 0; bInheritHandle
0x18000da0c  mov     r8, rbx; hTargetProcessHandle
0x18000da0f  mov     [rsp+88h+dwMaximumSizeLow], 0; dwDesiredAccess
0x18000da17  call    cs:__imp_DuplicateHandle
0x18000da1d  test    eax, eax
0x18000da1f  jnz     short loc_18000DA28
0x18000da21  call    ?MakeErrorLast@@YAJXZ; MakeErrorLast(void)
0x18000da26  jmp     short loc_18000DA47
0x18000da28  mov     rax, [rsp+88h+TargetHandle]
0x18000da2d  mov     rdx, rsi; hSourceHandle
0x18000da30  mov     r9, [rsp+88h+arg_30]; void *
0x18000da38  mov     rcx, r14; this
0x18000da3b  mov     [rdi+620h], rax
0x18000da42  call    ?InjectRemoteSection@CThemeServer@@AEAAJPEAXH0@Z; CThemeServer::InjectRemoteSection(void *,int,void *)
0x18000da47  mov     rcx, rdi; lpBaseAddress
0x18000da4a  mov     ebx, eax
0x18000da4c  call    cs:__imp_UnmapViewOfFile
0x18000da52  jmp     short loc_18000DA5B
0x18000da54  call    ?MakeErrorLast@@YAJXZ; MakeErrorLast(void)
0x18000da59  mov     ebx, eax
0x18000da5b  mov     rcx, rsi; hObject
0x18000da5e  call    cs:__imp_CloseHandle
0x18000da64  mov     eax, ebx
0x18000da66  add     rsp, 58h
0x18000da6a  pop     r15
0x18000da6c  pop     r14
0x18000da6e  pop     rdi
0x18000da6f  pop     rsi
0x18000da70  pop     rbp
0x18000da71  pop     rbx
0x18000da72  retn
```
