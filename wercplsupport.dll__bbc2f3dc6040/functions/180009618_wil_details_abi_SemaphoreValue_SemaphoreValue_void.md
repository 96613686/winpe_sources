# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x180009618`
- end: `0x18000967a`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009078`
- `0x180009b78`
- `0x180009f58`
- `0x18000d784`

## callees

- `0x180009618`
- `0x18000f210`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000962a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000963c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000962a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000963c`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::~SemaphoreValue(wil::details_abi::SemaphoreValue *this)
{
  void *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r8
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
0x180009618  push    rbx; char *
0x18000961a  sub     rsp, 20h
0x18000961e  mov     rbx, rcx
0x180009621  mov     rcx, [rcx+8]; hObject
0x180009625  test    rcx, rcx
0x180009628  jz      short loc_180009634
0x18000962a  call    cs:__imp_CloseHandle
0x180009630  test    eax, eax
0x180009632  jz      short loc_180009663
0x180009634  mov     rcx, [rbx]; hObject
0x180009637  test    rcx, rcx
0x18000963a  jz      short loc_180009646
0x18000963c  call    cs:__imp_CloseHandle
0x180009642  test    eax, eax
0x180009644  jz      short loc_18000964C
0x180009646  add     rsp, 20h
0x18000964a  pop     rbx
0x18000964b  retn
0x18000964c  mov     rcx, [rsp+28h]; this
0x180009651  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x180009658  mov     edx, 0A0Bh; void *
0x18000965d  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x180009663  mov     rcx, [rsp+28h]; this
0x180009668  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x18000966f  mov     edx, 0A0Bh; void *
0x180009674  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
```
