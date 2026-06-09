# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x180007648`
- end: `0x1800076a9`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000794c`
- `0x180007d44`
- `0x18000c490`
- `0x18000c620`

## callees

- `0x180007648`
- `0x18000eac4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000765a`
- `KERNEL32!CloseHandle` at `0x180007672`
- `KERNEL32!CloseHandle` at `0x18000765a`
- `KERNEL32!CloseHandle` at `0x180007672`

## pseudocode

```c
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
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v3, v4);
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v5, v6);
  }
}

```

## disassembly

```asm
0x180007648  push    rbx
0x18000764a  sub     rsp, 20h
0x18000764e  mov     rbx, rcx
0x180007651  mov     rcx, [rcx+8]; hObject
0x180007655  test    rcx, rcx
0x180007658  jz      short loc_18000766A
0x18000765a  call    cs:__imp_CloseHandle
0x180007661  nop     dword ptr [rax+rax+00h]
0x180007666  test    eax, eax
0x180007668  jz      short loc_180007699
0x18000766a  mov     rcx, [rbx]; hObject
0x18000766d  test    rcx, rcx
0x180007670  jz      short loc_180007682
0x180007672  call    cs:__imp_CloseHandle
0x180007679  nop     dword ptr [rax+rax+00h]
0x18000767e  test    eax, eax
0x180007680  jz      short loc_180007689
0x180007682  add     rsp, 20h
0x180007686  pop     rbx
0x180007687  retn
0x180007689  mov     rcx, [rsp+28h]; this
0x18000768e  mov     edx, 9CDh; void *
0x180007693  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007699  mov     rcx, [rsp+28h]; this
0x18000769e  mov     edx, 9CDh; void *
0x1800076a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
