# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x180003870`
- end: `0x1800038d1`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b34`
- `0x180003f2c`
- `0x180009638`
- `0x1800097c8`

## callees

- `0x180003870`
- `0x18000b828`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180003882`
- `KERNEL32!CloseHandle` at `0x18000389a`
- `KERNEL32!CloseHandle` at `0x180003882`
- `KERNEL32!CloseHandle` at `0x18000389a`

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
0x180003870  push    rbx
0x180003872  sub     rsp, 20h
0x180003876  mov     rbx, rcx
0x180003879  mov     rcx, [rcx+8]; hObject
0x18000387d  test    rcx, rcx
0x180003880  jz      short loc_180003892
0x180003882  call    cs:__imp_CloseHandle
0x180003889  nop     dword ptr [rax+rax+00h]
0x18000388e  test    eax, eax
0x180003890  jz      short loc_1800038C1
0x180003892  mov     rcx, [rbx]; hObject
0x180003895  test    rcx, rcx
0x180003898  jz      short loc_1800038AA
0x18000389a  call    cs:__imp_CloseHandle
0x1800038a1  nop     dword ptr [rax+rax+00h]
0x1800038a6  test    eax, eax
0x1800038a8  jz      short loc_1800038B1
0x1800038aa  add     rsp, 20h
0x1800038ae  pop     rbx
0x1800038af  retn
0x1800038b1  mov     rcx, [rsp+28h]; this
0x1800038b6  mov     edx, 9CDh; void *
0x1800038bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800038c1  mov     rcx, [rsp+28h]; this
0x1800038c6  mov     edx, 9CDh; void *
0x1800038cb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
