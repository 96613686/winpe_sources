# WUServiceWatcher::~WUServiceWatcher(void)

- ea: `0x180085a10`
- end: `0x180085af4`
- name: `??1WUServiceWatcher@@QEAA@XZ`
- size: `228`
- prototype: `void __fastcall(WUServiceWatcher *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x18000e920`
- `0x180016c74`
- `0x18001fc0c`
- `0x180070ce8`

## callees

- `0x180081a38`
- `0x180085a10`
- `0x180090bc8`
- `0x18009b0b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180085a36`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180085a36`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180085a22`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180085a22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085aa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085abb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085ad2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085aa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085abb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085ad2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085ae8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085ae8`

## string_xrefs

- `0x180085a46`: `Waiting for watcher thread failed with status %d`

## pseudocode

```c
void __fastcall WUServiceWatcher::~WUServiceWatcher(WUServiceWatcher *this)
{
  void *v2; // rcx
  void *v3; // rcx
  DWORD v4; // eax
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  DWORD v10; // [rsp+30h] [rbp-18h]

  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
    SetEvent(v2);
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    v4 = WaitForSingleObject(v3, 0xEA60u);
    if ( v4 )
    {
      v10 = v4;
      WUTrace(0, 0, 32, 3, 0, L"Waiting for watcher thread failed with status %d", v10);
    }
  }
  v5 = (void *)*((_QWORD *)this + 6);
  if ( v5 )
  {
    SusFree(v5);
    *((_QWORD *)this + 6) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 5);
  if ( v6 )
  {
    operator delete(v6);
    *((_QWORD *)this + 5) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 4);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 4) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 3);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 3) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 2);
  if ( v9 )
  {
    CloseHandle(v9);
    *((_QWORD *)this + 2) = 0;
  }
  if ( *(_QWORD *)this )
    CloseServiceHandle(*(SC_HANDLE *)this);
}

```

## disassembly

```asm
0x180085a10  push    rbx
0x180085a12  sub     rsp, 40h
0x180085a16  mov     rbx, rcx
0x180085a19  mov     rcx, [rcx+18h]; hEvent
0x180085a1d  test    rcx, rcx
0x180085a20  jz      short loc_180085A28
0x180085a22  call    cs:__imp_SetEvent
0x180085a28  mov     rcx, [rbx+10h]; hHandle
0x180085a2c  test    rcx, rcx
0x180085a2f  jz      short loc_180085A6A
0x180085a31  mov     edx, 0EA60h; dwMilliseconds
0x180085a36  call    cs:__imp_WaitForSingleObject
0x180085a3c  test    eax, eax
0x180085a3e  jz      short loc_180085A6A
0x180085a40  mov     [rsp+48h+var_18], eax
0x180085a44  xor     edx, edx
0x180085a46  lea     rax, aWaitingForWatc; "Waiting for watcher thread failed with "...
0x180085a4d  xor     ecx, ecx
0x180085a4f  mov     [rsp+48h+var_20], rax
0x180085a54  mov     [rsp+48h+var_28], 0
0x180085a5d  lea     r9d, [rdx+3]
0x180085a61  lea     r8d, [rdx+20h]
0x180085a65  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180085a6a  mov     rcx, [rbx+30h]; lpMem
0x180085a6e  test    rcx, rcx
0x180085a71  jz      short loc_180085A80
0x180085a73  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180085a78  mov     qword ptr [rbx+30h], 0
0x180085a80  mov     rcx, [rbx+28h]; Block
0x180085a84  test    rcx, rcx
0x180085a87  jz      short loc_180085A9B
0x180085a89  mov     edx, 90h
0x180085a8e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180085a93  mov     qword ptr [rbx+28h], 0
0x180085a9b  mov     rcx, [rbx+20h]; hObject
0x180085a9f  test    rcx, rcx
0x180085aa2  jz      short loc_180085AB2
0x180085aa4  call    cs:__imp_CloseHandle
0x180085aaa  mov     qword ptr [rbx+20h], 0
0x180085ab2  mov     rcx, [rbx+18h]; hObject
0x180085ab6  test    rcx, rcx
0x180085ab9  jz      short loc_180085AC9
0x180085abb  call    cs:__imp_CloseHandle
0x180085ac1  mov     qword ptr [rbx+18h], 0
0x180085ac9  mov     rcx, [rbx+10h]; hObject
0x180085acd  test    rcx, rcx
0x180085ad0  jz      short loc_180085AE0
0x180085ad2  call    cs:__imp_CloseHandle
0x180085ad8  mov     qword ptr [rbx+10h], 0
0x180085ae0  mov     rcx, [rbx]; hSCObject
0x180085ae3  test    rcx, rcx
0x180085ae6  jz      short loc_180085AEE
0x180085ae8  call    cs:__imp_CloseServiceHandle
0x180085aee  add     rsp, 40h
0x180085af2  pop     rbx
0x180085af3  retn
```
