# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x180034278`
- end: `0x1800342da`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180033c68`
- `0x1800345d8`
- `0x18003497c`
- `0x180037c90`

## callees

- `0x180034278`
- `0x1800396fc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003428a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003429c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003428a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003429c`

## string_xrefs

- `0x1800342b1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800342c8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::~SemaphoreValue(wil::details_abi::SemaphoreValue *this)
{
  void *v2; // rcx
  const char *v3; // r9
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
  }
}

```

## disassembly

```asm
0x180034278  push    rbx
0x18003427a  sub     rsp, 20h
0x18003427e  mov     rbx, rcx
0x180034281  mov     rcx, [rcx+8]; hObject
0x180034285  test    rcx, rcx
0x180034288  jz      short loc_180034294
0x18003428a  call    cs:__imp_CloseHandle
0x180034290  test    eax, eax
0x180034292  jz      short loc_1800342C3
0x180034294  mov     rcx, [rbx]; hObject
0x180034297  test    rcx, rcx
0x18003429a  jz      short loc_1800342A6
0x18003429c  call    cs:__imp_CloseHandle
0x1800342a2  test    eax, eax
0x1800342a4  jz      short loc_1800342AC
0x1800342a6  add     rsp, 20h
0x1800342aa  pop     rbx
0x1800342ab  retn
0x1800342ac  mov     rcx, [rsp+28h]; this
0x1800342b1  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800342b8  mov     edx, 0A0Bh; void *
0x1800342bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800342c3  mov     rcx, [rsp+28h]; this
0x1800342c8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800342cf  mov     edx, 0A0Bh; void *
0x1800342d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
