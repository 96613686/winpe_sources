# Vml::VmComFileStream::SetSize(_ULARGE_INTEGER)

- ea: `0x1400cc1b0`
- end: `0x1400cc2b7`
- name: `?SetSize@VmComFileStream@Vml@@UEAAJT_ULARGE_INTEGER@@@Z`
- size: `263`
- prototype: `int(Vml::VmComFileStream *__hidden this, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140005360`
- `0x14000ddac`
- `0x1400cc1b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1400cc1e7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1400cc20a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1400cc242`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1400cc1e7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1400cc20a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1400cc242`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1400cc21d`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1400cc21d`

## string_xrefs

- `0x1400cc271`: `onecore\vm\common\vml\VmFiles.h`
- `0x1400cc282`: `onecore\vm\common\vml\VmFiles.h`
- `0x1400cc293`: `onecore\vm\common\vml\VmFiles.h`
- `0x1400cc2a4`: `onecore\vm\common\vml\VmFiles.h`

## pseudocode

```c
__int64 __fastcall Vml::VmComFileStream::SetSize(HANDLE *this, union _ULARGE_INTEGER a2)
{
  const char *v4; // r9
  const char *v5; // r9
  const char *v6; // r9
  __int64 result; // rax
  unsigned int v8; // eax
  int v9; // edx
  union _LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  NewFilePointer.QuadPart = 0;
  if ( !SetFilePointerEx(this[1], 0, &NewFilePointer, 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x58F,
      (unsigned int)"onecore\\vm\\common\\vml\\VmFiles.h",
      v4);
  if ( a2.QuadPart != NewFilePointer.QuadPart && !SetFilePointerEx(this[1], (LARGE_INTEGER)a2.QuadPart, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x5B4,
      (unsigned int)"onecore\\vm\\common\\vml\\VmFiles.h",
      v5);
  if ( !SetEndOfFile(this[1]) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x574,
      (unsigned int)"onecore\\vm\\common\\vml\\VmFiles.h",
      v6);
  if ( a2.QuadPart != NewFilePointer.QuadPart && !SetFilePointerEx(this[1], NewFilePointer, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x5B4,
      (unsigned int)"onecore\\vm\\common\\vml\\VmFiles.h",
      v6);
  result = 0;
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v8 = wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x5DF,
             (unsigned int)"onecore\\vm\\common\\vml\\VmComStorage.h",
             v6);
      NewFilePointer.LowPart = Vml::VmlStgResultFromHResult((Vml *)v8, v9);
      result = NewFilePointer.LowPart;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x1400cc1b0  mov     [rsp+arg_10], rbx
0x1400cc1b5  push    rsi
0x1400cc1b6  sub     rsp, 30h
0x1400cc1ba  mov     rax, cs:__security_cookie
0x1400cc1c1  xor     rax, rsp
0x1400cc1c4  mov     [rsp+38h+var_10], rax
0x1400cc1c9  mov     rbx, rdx
0x1400cc1cc  mov     rsi, rcx
0x1400cc1cf  mov     qword ptr [rsp+38h+NewFilePointer], 0
0x1400cc1d8  xor     edx, edx; liDistanceToMove
0x1400cc1da  lea     r9d, [rdx+1]; dwMoveMethod
0x1400cc1de  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x1400cc1e3  mov     rcx, [rcx+8]; hFile
0x1400cc1e7  call    cs:__imp_SetFilePointerEx
0x1400cc1ed  mov     rcx, [rsp+38h]; this
0x1400cc1f2  test    eax, eax
0x1400cc1f4  jz      short loc_1400CC271
0x1400cc1f6  cmp     rbx, qword ptr [rsp+38h+NewFilePointer]
0x1400cc1fb  jz      short loc_1400CC219
0x1400cc1fd  xor     r9d, r9d; dwMoveMethod
0x1400cc200  xor     r8d, r8d; lpNewFilePointer
0x1400cc203  mov     rdx, rbx; liDistanceToMove
0x1400cc206  mov     rcx, [rsi+8]; hFile
0x1400cc20a  call    cs:__imp_SetFilePointerEx
0x1400cc210  mov     rcx, [rsp+38h]; this
0x1400cc215  test    eax, eax
0x1400cc217  jz      short loc_1400CC282
0x1400cc219  mov     rcx, [rsi+8]; hFile
0x1400cc21d  call    cs:__imp_SetEndOfFile
0x1400cc223  mov     rcx, [rsp+38h]; this
0x1400cc228  test    eax, eax
0x1400cc22a  jz      short loc_1400CC293
0x1400cc22c  cmp     rbx, qword ptr [rsp+38h+NewFilePointer]
0x1400cc231  jz      short loc_1400CC251
0x1400cc233  xor     r9d, r9d; dwMoveMethod
0x1400cc236  xor     r8d, r8d; lpNewFilePointer
0x1400cc239  mov     rdx, qword ptr [rsp+38h+NewFilePointer]; liDistanceToMove
0x1400cc23e  mov     rcx, [rsi+8]; hFile
0x1400cc242  call    cs:__imp_SetFilePointerEx
0x1400cc248  mov     rcx, [rsp+38h]; this
0x1400cc24d  test    eax, eax
0x1400cc24f  jz      short loc_1400CC2A4
0x1400cc251  xor     eax, eax
0x1400cc253  jmp     short loc_1400CC259
0x1400cc255  mov     eax, dword ptr [rsp+38h+NewFilePointer]
0x1400cc259  mov     rcx, [rsp+38h+var_10]
0x1400cc25e  xor     rcx, rsp; StackCookie
0x1400cc261  call    __security_check_cookie
0x1400cc266  mov     rbx, [rsp+38h+arg_10]
0x1400cc26b  add     rsp, 30h
0x1400cc26f  pop     rsi
0x1400cc270  retn
0x1400cc271  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\vml\\VmFiles.h"
0x1400cc278  mov     edx, 58Fh; void *
0x1400cc27d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400cc282  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\vml\\VmFiles.h"
0x1400cc289  mov     edx, 5B4h; void *
0x1400cc28e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400cc293  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\vml\\VmFiles.h"
0x1400cc29a  mov     edx, 574h; void *
0x1400cc29f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400cc2a4  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\vml\\VmFiles.h"
0x1400cc2ab  mov     edx, 5B4h; void *
0x1400cc2b0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
