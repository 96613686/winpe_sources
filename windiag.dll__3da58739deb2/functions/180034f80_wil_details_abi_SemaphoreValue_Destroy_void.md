# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x180034f80`
- end: `0x18003502a`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `170`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180037b6c`
- `0x180037c90`

## callees

- `0x180034f80`
- `0x1800396fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034fb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034fde`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034fb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034fde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034f9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034f9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034fa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034fd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034fa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034fd2`

## string_xrefs

- `0x180035001`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180035018`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::Destroy(wil::details_abi::SemaphoreValue *this)
{
  void *v1; // rdi
  DWORD LastError; // esi
  const char *v4; // r9
  void *v5; // rdi
  DWORD v6; // esi
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
  {
    v6 = GetLastError();
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v7);
    SetLastError(v6);
  }
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x180034f80  mov     [rsp+arg_0], rbx
0x180034f85  mov     [rsp+arg_8], rsi
0x180034f8a  push    rdi
0x180034f8b  sub     rsp, 20h
0x180034f8f  mov     rdi, [rcx]
0x180034f92  mov     rbx, rcx
0x180034f95  test    rdi, rdi
0x180034f98  jz      short loc_180034FB7
0x180034f9a  call    cs:__imp_GetLastError
0x180034fa0  mov     rcx, rdi; hObject
0x180034fa3  mov     esi, eax
0x180034fa5  call    cs:__imp_CloseHandle
0x180034fab  test    eax, eax
0x180034fad  jz      short loc_180035013
0x180034faf  mov     ecx, esi; dwErrCode
0x180034fb1  call    cs:__imp_SetLastError
0x180034fb7  mov     qword ptr [rbx], 0
0x180034fbe  mov     rdi, [rbx+8]
0x180034fc2  test    rdi, rdi
0x180034fc5  jz      short loc_180034FE4
0x180034fc7  call    cs:__imp_GetLastError
0x180034fcd  mov     rcx, rdi; hObject
0x180034fd0  mov     esi, eax
0x180034fd2  call    cs:__imp_CloseHandle
0x180034fd8  test    eax, eax
0x180034fda  jz      short loc_180034FFC
0x180034fdc  mov     ecx, esi; dwErrCode
0x180034fde  call    cs:__imp_SetLastError
0x180034fe4  mov     rsi, [rsp+28h+arg_8]
0x180034fe9  mov     qword ptr [rbx+8], 0
0x180034ff1  mov     rbx, [rsp+28h+arg_0]
0x180034ff6  add     rsp, 20h
0x180034ffa  pop     rdi
0x180034ffb  retn
0x180034ffc  mov     rcx, [rsp+28h]; this
0x180035001  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180035008  mov     edx, 0A0Bh; void *
0x18003500d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180035013  mov     rcx, [rsp+28h]; this
0x180035018  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003501f  mov     edx, 0A0Bh; void *
0x180035024  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
