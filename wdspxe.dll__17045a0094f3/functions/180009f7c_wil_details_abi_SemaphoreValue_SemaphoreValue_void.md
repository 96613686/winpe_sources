# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x180009f7c`
- end: `0x180009fdd`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a204`
- `0x18000a5fc`
- `0x18000e64c`
- `0x18000e7dc`

## callees

- `0x180009f7c`
- `0x180010a48`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180009f8e`
- `KERNEL32!CloseHandle` at `0x180009fa6`
- `KERNEL32!CloseHandle` at `0x180009f8e`
- `KERNEL32!CloseHandle` at `0x180009fa6`

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
0x180009f7c  push    rbx
0x180009f7e  sub     rsp, 20h
0x180009f82  mov     rbx, rcx
0x180009f85  mov     rcx, [rcx+8]; hObject
0x180009f89  test    rcx, rcx
0x180009f8c  jz      short loc_180009F9E
0x180009f8e  call    cs:__imp_CloseHandle
0x180009f95  nop     dword ptr [rax+rax+00h]
0x180009f9a  test    eax, eax
0x180009f9c  jz      short loc_180009FCD
0x180009f9e  mov     rcx, [rbx]; hObject
0x180009fa1  test    rcx, rcx
0x180009fa4  jz      short loc_180009FB6
0x180009fa6  call    cs:__imp_CloseHandle
0x180009fad  nop     dword ptr [rax+rax+00h]
0x180009fb2  test    eax, eax
0x180009fb4  jz      short loc_180009FBD
0x180009fb6  add     rsp, 20h
0x180009fba  pop     rbx
0x180009fbb  retn
0x180009fbd  mov     rcx, [rsp+28h]; this
0x180009fc2  mov     edx, 9CDh; void *
0x180009fc7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009fcd  mov     rcx, [rsp+28h]; this
0x180009fd2  mov     edx, 9CDh; void *
0x180009fd7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
