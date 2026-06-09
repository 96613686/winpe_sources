# CReportHandleInstance::Initialize(void)

- ea: `0x18006fa68`
- end: `0x18006fb0b`
- name: `?Initialize@CReportHandleInstance@@QEAAJXZ`
- size: `163`
- prototype: `__int64 __fastcall(CReportHandleInstance *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180030fc0`
- `0x18004015c`

## callees

- `0x18000716c`
- `0x180007e34`
- `0x18006fa68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006faae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006faae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fa91`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fad6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fa91`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fad6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006faf8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006faf8`

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
0x18006fa68  mov     [rsp+arg_0], rbx
0x18006fa6d  push    rdi
0x18006fa6e  sub     rsp, 20h
0x18006fa72  lea     rbx, [rcx+38h]
0x18006fa76  mov     rdi, rcx
0x18006fa79  mov     rax, [rbx]
0x18006fa7c  inc     rax
0x18006fa7f  cmp     rax, 1
0x18006fa83  ja      short loc_18006FABD
0x18006fa85  xor     r9d, r9d; lpName
0x18006fa88  xor     ecx, ecx; lpEventAttributes
0x18006fa8a  lea     edx, [r9+1]; bManualReset
0x18006fa8e  mov     r8d, edx; bInitialState
0x18006fa91  call    cs:__imp_CreateEventW
0x18006fa97  mov     rdx, rax
0x18006fa9a  mov     rcx, rbx
0x18006fa9d  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18006faa2  mov     rax, [rbx]
0x18006faa5  inc     rax
0x18006faa8  cmp     rax, 1
0x18006faac  ja      short loc_18006FABD
0x18006faae  call    cs:__imp_GetLastError
0x18006fab4  mov     ecx, eax; unsigned int
0x18006fab6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18006fabb  jmp     short loc_18006FB00
0x18006fabd  mov     rax, [rdi+40h]
0x18006fac1  inc     rax
0x18006fac4  cmp     rax, 1
0x18006fac8  ja      short loc_18006FAF5
0x18006faca  xor     r9d, r9d; lpName
0x18006facd  xor     r8d, r8d; bInitialState
0x18006fad0  xor     ecx, ecx; lpEventAttributes
0x18006fad2  lea     edx, [r9+1]; bManualReset
0x18006fad6  call    cs:__imp_CreateEventW
0x18006fadc  mov     rdx, rax
0x18006fadf  lea     rcx, [rdi+40h]
0x18006fae3  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18006fae8  mov     rax, [rdi+40h]
0x18006faec  inc     rax
0x18006faef  cmp     rax, 1
0x18006faf3  jbe     short loc_18006FAAE
0x18006faf5  mov     rcx, [rbx]; hEvent
0x18006faf8  call    cs:__imp_SetEvent
0x18006fafe  xor     eax, eax
0x18006fb00  mov     rbx, [rsp+28h+arg_0]
0x18006fb05  add     rsp, 20h
0x18006fb09  pop     rdi
0x18006fb0a  retn
```
