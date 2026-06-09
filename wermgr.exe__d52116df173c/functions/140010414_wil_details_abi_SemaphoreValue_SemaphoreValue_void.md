# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x140010414`
- end: `0x140010476`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ff64`
- `0x140010778`
- `0x140010b80`
- `0x140013248`

## callees

- `0x140010414`
- `0x1400148d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010426`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010438`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010426`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010438`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::~SemaphoreValue(wil::details_abi::SemaphoreValue *this)
{
  void *v2; // rcx
  unsigned int v3; // r8d
  unsigned int v4; // r8d
  const char *v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag4 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag4::_FailFast_GetLastError(retaddr, (void *)0xA0B, v3, "wil::details::CloseHandle", v5);
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag4::_FailFast_GetLastError(retaddr, (void *)0xA0B, v4, "wil::details::CloseHandle", v5);
  }
}

```

## disassembly

```asm
0x140010414  push    rbx; char *
0x140010416  sub     rsp, 20h
0x14001041a  mov     rbx, rcx
0x14001041d  mov     rcx, [rcx+8]; hObject
0x140010421  test    rcx, rcx
0x140010424  jz      short loc_140010430
0x140010426  call    cs:__imp_CloseHandle
0x14001042c  test    eax, eax
0x14001042e  jz      short loc_14001045F
0x140010430  mov     rcx, [rbx]; hObject
0x140010433  test    rcx, rcx
0x140010436  jz      short loc_140010442
0x140010438  call    cs:__imp_CloseHandle
0x14001043e  test    eax, eax
0x140010440  jz      short loc_140010448
0x140010442  add     rsp, 20h
0x140010446  pop     rbx
0x140010447  retn
0x140010448  mov     rcx, [rsp+28h]; this
0x14001044d  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140010454  mov     edx, 0A0Bh; void *
0x140010459  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x14001045f  mov     rcx, [rsp+28h]; this
0x140010464  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x14001046b  mov     edx, 0A0Bh; void *
0x140010470  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
```
