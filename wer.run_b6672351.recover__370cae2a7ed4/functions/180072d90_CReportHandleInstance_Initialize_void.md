# CReportHandleInstance::Initialize(void)

- ea: `0x180072d90`
- end: `0x180072e4c`
- name: `?Initialize@CReportHandleInstance@@QEAAJXZ`
- size: `188`
- prototype: `__int64 __fastcall(CReportHandleInstance *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180032910`
- `0x1800420c0`

## callees

- `0x180008004`
- `0x18001c368`
- `0x180072d90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ddc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072db9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072e0a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072db9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072e0a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180072e32`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180072e32`

## pseudocode

```c
__int64 __fastcall CReportHandleInstance::Initialize(CReportHandleInstance *this)
{
  HANDLE *v1; // rbx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  HANDLE v6; // rax

  v1 = (HANDLE *)((char *)this + 56);
  if ( (*((_QWORD *)this + 7) == -1 || *((_QWORD *)this + 7) == 0)
    && (EventW = CreateEventW(0, 1, 1, 0),
        tlx::unique_any<tlx::file_handle_traits>::reset(v1, EventW),
        *v1 == (HANDLE)-1LL || (char *)*v1 + 1 == HANDLE_FLAG_INHERIT)
    || (*((_QWORD *)this + 8) == -1 || *((_QWORD *)this + 8) == 0)
    && (v6 = CreateEventW(0, 1, 0, 0),
        tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 64, v6),
        *((_QWORD *)this + 8) == -1 || *((_QWORD *)this + 8) == 0) )
  {
    LastError = GetLastError();
    return ERROR_HR_FROM_WIN32(LastError);
  }
  else
  {
    SetEvent(*v1);
    return 0;
  }
}

```

## disassembly

```asm
0x180072d90  mov     [rsp+arg_0], rbx
0x180072d95  push    rdi
0x180072d96  sub     rsp, 20h
0x180072d9a  lea     rbx, [rcx+38h]
0x180072d9e  mov     rdi, rcx
0x180072da1  mov     rax, [rbx]
0x180072da4  inc     rax
0x180072da7  cmp     rax, 1
0x180072dab  ja      short loc_180072DF1
0x180072dad  xor     r9d, r9d; lpName
0x180072db0  xor     ecx, ecx; lpEventAttributes
0x180072db2  lea     edx, [r9+1]; bManualReset
0x180072db6  mov     r8d, edx; bInitialState
0x180072db9  call    cs:__imp_CreateEventW
0x180072dc0  nop     dword ptr [rax+rax+00h]
0x180072dc5  mov     rdx, rax
0x180072dc8  mov     rcx, rbx
0x180072dcb  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180072dd0  mov     rax, [rbx]
0x180072dd3  inc     rax
0x180072dd6  cmp     rax, 1
0x180072dda  ja      short loc_180072DF1
0x180072ddc  call    cs:__imp_GetLastError
0x180072de3  nop     dword ptr [rax+rax+00h]
0x180072de8  mov     ecx, eax; unsigned int
0x180072dea  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180072def  jmp     short loc_180072E40
0x180072df1  mov     rax, [rdi+40h]
0x180072df5  inc     rax
0x180072df8  cmp     rax, 1
0x180072dfc  ja      short loc_180072E2F
0x180072dfe  xor     r9d, r9d; lpName
0x180072e01  xor     r8d, r8d; bInitialState
0x180072e04  xor     ecx, ecx; lpEventAttributes
0x180072e06  lea     edx, [r9+1]; bManualReset
0x180072e0a  call    cs:__imp_CreateEventW
0x180072e11  nop     dword ptr [rax+rax+00h]
0x180072e16  mov     rdx, rax
0x180072e19  lea     rcx, [rdi+40h]
0x180072e1d  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180072e22  mov     rax, [rdi+40h]
0x180072e26  inc     rax
0x180072e29  cmp     rax, 1
0x180072e2d  jbe     short loc_180072DDC
0x180072e2f  mov     rcx, [rbx]; hEvent
0x180072e32  call    cs:__imp_SetEvent
0x180072e39  nop     dword ptr [rax+rax+00h]
0x180072e3e  xor     eax, eax
0x180072e40  mov     rbx, [rsp+28h+arg_0]
0x180072e45  add     rsp, 20h
0x180072e49  pop     rdi
0x180072e4a  retn
```
