# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x180009428`
- end: `0x180009489`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a904`
- `0x18000ae14`
- `0x18000cd5c`

## callees

- `0x180009428`
- `0x18000c478`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000943a`
- `KERNEL32!CloseHandle` at `0x180009457`
- `KERNEL32!CloseHandle` at `0x18000943a`
- `KERNEL32!CloseHandle` at `0x180009457`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::SemaphoreValue::~SemaphoreValue(wil::details_abi::SemaphoreValue *this)
{
  void *v2; // rcx
  __int64 v3; // r8
  const char *v4; // r9
  __int64 v5; // r8
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v3, v4);
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v5, v6);
  }
}

```

## disassembly

```asm
0x180009428  push    rbx
0x18000942a  sub     rsp, 20h
0x18000942e  mov     rbx, rcx
0x180009431  mov     rcx, [rcx+8]; hObject
0x180009435  test    rcx, rcx
0x180009438  jz      short loc_18000944F
0x18000943a  call    cs:__imp_CloseHandle
0x180009441  nop     dword ptr [rax+rax+00h]
0x180009446  mov     rcx, [rsp+28h]; this
0x18000944b  test    eax, eax
0x18000944d  jz      short loc_18000947E
0x18000944f  mov     rcx, [rbx]; hObject
0x180009452  test    rcx, rcx
0x180009455  jz      short loc_18000946C
0x180009457  call    cs:__imp_CloseHandle
0x18000945e  nop     dword ptr [rax+rax+00h]
0x180009463  mov     rcx, [rsp+28h]; this
0x180009468  test    eax, eax
0x18000946a  jz      short loc_180009473
0x18000946c  add     rsp, 20h
0x180009470  pop     rbx
0x180009471  retn
0x180009473  mov     edx, 9DDh; void *
0x180009478  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000947e  mov     edx, 9DDh; void *
0x180009483  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
