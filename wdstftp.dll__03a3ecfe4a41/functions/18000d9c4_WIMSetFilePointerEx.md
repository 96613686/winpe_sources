# WIMSetFilePointerEx

- ea: `0x18000d9c4`
- end: `0x18000da63`
- name: `WIMSetFilePointerEx`
- size: `159`
- prototype: `__int64 __fastcall(HANDLE hFile, LARGE_INTEGER liDistanceToMove)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ed20`
- `0x18000f7c4`
- `0x180013490`

## callees

- `0x18000d9c4`
- `0x180060e70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d9e7`
- `KERNEL32!GetLastError` at `0x18000d9e7`
- `KERNEL32!GetHandleInformation` at `0x18000da02`
- `KERNEL32!GetHandleInformation` at `0x18000da02`
- `KERNEL32!SetLastError` at `0x18000da14`
- `KERNEL32!SetLastError` at `0x18000da14`
- `KERNEL32!SetFilePointerEx` at `0x18000da47`
- `KERNEL32!SetFilePointerEx` at `0x18000da47`

## pseudocode

```c
int __fastcall WIMSetFilePointerEx(HANDLE hFile, LARGE_INTEGER liDistanceToMove, __int64 a3, DWORD a4)
{
  DWORD LastError; // eax
  DWORD v7; // esi
  DWORD dwFlags; // [rsp+58h] [rbp+20h] BYREF

  dwFlags = a4;
  if ( !g_useFileIOCallbacks )
    return SetFilePointerEx(hFile, liDistanceToMove, 0, 0);
  LastError = GetLastError();
  dwFlags = 0;
  v7 = LastError;
  if ( GetHandleInformation(hFile, &dwFlags) )
    return SetFilePointerEx(hFile, liDistanceToMove, 0, 0);
  SetLastError(v7);
  return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))qword_1800778C8)(
           hFile,
           (LARGE_INTEGER)liDistanceToMove.QuadPart,
           0,
           0);
}

```

## disassembly

```asm
0x18000d9c4  mov     [rsp+arg_0], rbx
0x18000d9c9  mov     [rsp+arg_8], rsi
0x18000d9ce  mov     [rsp+dwFlags], r9d
0x18000d9d3  push    rdi
0x18000d9d4  sub     rsp, 30h
0x18000d9d8  cmp     cs:g_useFileIOCallbacks, 0
0x18000d9df  mov     rbx, rdx
0x18000d9e2  mov     rdi, rcx
0x18000d9e5  jz      short loc_18000DA3B
0x18000d9e7  call    cs:__imp_GetLastError
0x18000d9ee  nop     dword ptr [rax+rax+00h]
0x18000d9f3  and     [rsp+38h+dwFlags], 0
0x18000d9f8  lea     rdx, [rsp+38h+dwFlags]; lpdwFlags
0x18000d9fd  mov     rcx, rdi; hObject
0x18000da00  mov     esi, eax
0x18000da02  call    cs:__imp_GetHandleInformation
0x18000da09  nop     dword ptr [rax+rax+00h]
0x18000da0e  test    eax, eax
0x18000da10  jnz     short loc_18000DA3B
0x18000da12  mov     ecx, esi; dwErrCode
0x18000da14  call    cs:__imp_SetLastError
0x18000da1b  nop     dword ptr [rax+rax+00h]
0x18000da20  mov     rax, cs:qword_1800778C8
0x18000da27  xor     r9d, r9d
0x18000da2a  xor     r8d, r8d
0x18000da2d  mov     rdx, rbx
0x18000da30  mov     rcx, rdi
0x18000da33  call    cs:__guard_dispatch_icall_fptr
0x18000da39  jmp     short loc_18000DA53
0x18000da3b  xor     r9d, r9d; dwMoveMethod
0x18000da3e  xor     r8d, r8d; lpNewFilePointer
0x18000da41  mov     rdx, rbx; liDistanceToMove
0x18000da44  mov     rcx, rdi; hFile
0x18000da47  call    cs:__imp_SetFilePointerEx
0x18000da4e  nop     dword ptr [rax+rax+00h]
0x18000da53  mov     rbx, [rsp+38h+arg_0]
0x18000da58  mov     rsi, [rsp+38h+arg_8]
0x18000da5d  add     rsp, 30h
0x18000da61  pop     rdi
0x18000da62  retn
```
