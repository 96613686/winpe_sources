# Microsoft::Diagnostics::FileWrapStream::SetSize(_ULARGE_INTEGER)

- ea: `0x1801e57c0`
- end: `0x1801e5897`
- name: `?SetSize@FileWrapStream@Diagnostics@Microsoft@@UEAAJT_ULARGE_INTEGER@@@Z`
- size: `215`
- prototype: `int(Microsoft::Diagnostics::FileWrapStream *__hidden this, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18008bd1c`
- `0x1801e57c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e5853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e5853`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1801e583f`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1801e583f`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801e57ef`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801e5824`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801e587d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801e57ef`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801e5824`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801e587d`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::FileWrapStream::SetSize(HANDLE *this, union _ULARGE_INTEGER a2)
{
  const char *v4; // r9
  __int64 v5; // rdx
  unsigned int v7; // ebx
  signed int LastError; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  union _LARGE_INTEGER NewFilePointer; // [rsp+30h] [rbp+8h] BYREF

  NewFilePointer.QuadPart = 0;
  if ( !SetFilePointerEx(
          this[2],
          `Microsoft::Diagnostics::FileWrapStream::SetSize'::`2'::zeroDisplacement,
          &NewFilePointer,
          1u) )
  {
    v5 = 303;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileWrapStream.h",
             v4);
  }
  if ( !SetFilePointerEx(this[2], (LARGE_INTEGER)a2.QuadPart, 0, 0) )
  {
    v5 = 311;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileWrapStream.h",
             v4);
  }
  if ( SetEndOfFile(this[2]) )
  {
    v7 = 0;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  SetFilePointerEx(this[2], NewFilePointer, 0, 0);
  return v7;
}

```

## disassembly

```asm
0x1801e57c0  mov     [rsp+arg_8], rbx
0x1801e57c5  push    rdi
0x1801e57c6  sub     rsp, 20h
0x1801e57ca  mov     rbx, rdx
0x1801e57cd  mov     qword ptr [rsp+28h+NewFilePointer], 0
0x1801e57d6  mov     rdx, qword ptr cs:?zeroDisplacement@?1??SetSize@FileWrapStream@Diagnostics@Microsoft@@UEAAJT_ULARGE_INTEGER@@@Z@4T_LARGE_INTEGER@@B; liDistanceToMove
0x1801e57dd  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x1801e57e2  mov     rdi, rcx
0x1801e57e5  mov     r9d, 1; dwMoveMethod
0x1801e57eb  mov     rcx, [rcx+10h]; hFile
0x1801e57ef  call    cs:__imp_SetFilePointerEx
0x1801e57f6  nop     dword ptr [rax+rax+00h]
0x1801e57fb  test    eax, eax
0x1801e57fd  jnz     short loc_1801E5817
0x1801e57ff  mov     edx, 12Fh; void *
0x1801e5804  mov     rcx, [rsp+28h]; this
0x1801e5809  lea     r8, aOnecoreBaseTel_62; "onecore\\base\\telemetry\\utc\\include"...
0x1801e5810  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e5815  jmp     short loc_1801E588B
0x1801e5817  mov     rcx, [rdi+10h]; hFile
0x1801e581b  xor     r9d, r9d; dwMoveMethod
0x1801e581e  xor     r8d, r8d; lpNewFilePointer
0x1801e5821  mov     rdx, rbx; liDistanceToMove
0x1801e5824  call    cs:__imp_SetFilePointerEx
0x1801e582b  nop     dword ptr [rax+rax+00h]
0x1801e5830  test    eax, eax
0x1801e5832  jnz     short loc_1801E583B
0x1801e5834  mov     edx, 137h
0x1801e5839  jmp     short loc_1801E5804
0x1801e583b  mov     rcx, [rdi+10h]; hFile
0x1801e583f  call    cs:__imp_SetEndOfFile
0x1801e5846  nop     dword ptr [rax+rax+00h]
0x1801e584b  test    eax, eax
0x1801e584d  jz      short loc_1801E5853
0x1801e584f  xor     ebx, ebx
0x1801e5851  jmp     short loc_1801E586E
0x1801e5853  call    cs:__imp_GetLastError
0x1801e585a  nop     dword ptr [rax+rax+00h]
0x1801e585f  mov     ebx, eax
0x1801e5861  test    eax, eax
0x1801e5863  jle     short loc_1801E586E
0x1801e5865  movzx   ebx, ax
0x1801e5868  or      ebx, 80070000h
0x1801e586e  mov     rdx, qword ptr [rsp+28h+NewFilePointer]; liDistanceToMove
0x1801e5873  xor     r9d, r9d; dwMoveMethod
0x1801e5876  mov     rcx, [rdi+10h]; hFile
0x1801e587a  xor     r8d, r8d; lpNewFilePointer
0x1801e587d  call    cs:__imp_SetFilePointerEx
0x1801e5884  nop     dword ptr [rax+rax+00h]
0x1801e5889  mov     eax, ebx
0x1801e588b  mov     rbx, [rsp+28h+arg_8]
0x1801e5890  add     rsp, 20h
0x1801e5894  pop     rdi
0x1801e5895  retn
```
