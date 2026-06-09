# ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext(void)

- ea: `0x1800188a4`
- end: `0x180018986`
- name: `??1NotificationContext@NotificationCallbacks@Client@ComputeService@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(ComputeService::Client::NotificationCallbacks::NotificationContext *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800158d0`
- `0x180017e80`
- `0x18001839c`
- `0x180039290`
- `0x180039648`
- `0x1800399dc`

## callees

- `0x1800188a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800188eb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180018945`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800188eb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180018945`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800188ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800188ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800188d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180018931`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800188d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180018931`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800188fa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180018954`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800188fa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180018954`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001896e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001896e`

## pseudocode

```c
void __fastcall ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext(
        ComputeService::Client::NotificationCallbacks::NotificationContext *this)
{
  struct _TP_WORK *v2; // rcx
  struct _TP_WAIT *v3; // rdi
  char *v4; // rcx
  struct _TP_WAIT *v5; // rdi
  char *v6; // rcx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 11);
  if ( v2 )
    CloseThreadpoolWork(v2);
  v3 = (struct _TP_WAIT *)*((_QWORD *)this + 7);
  if ( v3 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 7), 0, 0);
    WaitForThreadpoolWaitCallbacks(v3, 1);
    CloseThreadpoolWait(v3);
  }
  v4 = (char *)*((_QWORD *)this + 6);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  v5 = (struct _TP_WAIT *)*((_QWORD *)this + 5);
  if ( v5 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 5), 0, 0);
    WaitForThreadpoolWaitCallbacks(v5, 1);
    CloseThreadpoolWait(v5);
  }
  v6 = (char *)*((_QWORD *)this + 4);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
}

```

## disassembly

```asm
0x1800188a4  mov     [rsp+arg_0], rbx
0x1800188a9  push    rdi
0x1800188aa  sub     rsp, 20h
0x1800188ae  mov     rbx, rcx
0x1800188b1  mov     rcx, [rcx+58h]; pwk
0x1800188b5  test    rcx, rcx
0x1800188b8  jz      short loc_1800188C6
0x1800188ba  call    cs:__imp_CloseThreadpoolWork
0x1800188c1  nop     dword ptr [rax+rax+00h]
0x1800188c6  mov     rdi, [rbx+38h]
0x1800188ca  test    rdi, rdi
0x1800188cd  jz      short loc_180018906
0x1800188cf  xor     r8d, r8d; pftTimeout
0x1800188d2  xor     edx, edx; h
0x1800188d4  mov     rcx, rdi; pwa
0x1800188d7  call    cs:__imp_SetThreadpoolWait
0x1800188de  nop     dword ptr [rax+rax+00h]
0x1800188e3  mov     edx, 1; fCancelPendingCallbacks
0x1800188e8  mov     rcx, rdi; pwa
0x1800188eb  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800188f2  nop     dword ptr [rax+rax+00h]
0x1800188f7  mov     rcx, rdi; pwa
0x1800188fa  call    cs:__imp_CloseThreadpoolWait
0x180018901  nop     dword ptr [rax+rax+00h]
0x180018906  mov     rcx, [rbx+30h]; hObject
0x18001890a  lea     rax, [rcx-1]
0x18001890e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018912  ja      short loc_180018920
0x180018914  call    cs:__imp_CloseHandle
0x18001891b  nop     dword ptr [rax+rax+00h]
0x180018920  mov     rdi, [rbx+28h]
0x180018924  test    rdi, rdi
0x180018927  jz      short loc_180018960
0x180018929  xor     r8d, r8d; pftTimeout
0x18001892c  xor     edx, edx; h
0x18001892e  mov     rcx, rdi; pwa
0x180018931  call    cs:__imp_SetThreadpoolWait
0x180018938  nop     dword ptr [rax+rax+00h]
0x18001893d  mov     edx, 1; fCancelPendingCallbacks
0x180018942  mov     rcx, rdi; pwa
0x180018945  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18001894c  nop     dword ptr [rax+rax+00h]
0x180018951  mov     rcx, rdi; pwa
0x180018954  call    cs:__imp_CloseThreadpoolWait
0x18001895b  nop     dword ptr [rax+rax+00h]
0x180018960  mov     rcx, [rbx+20h]; hObject
0x180018964  lea     rax, [rcx-1]
0x180018968  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001896c  ja      short loc_18001897A
0x18001896e  call    cs:__imp_CloseHandle
0x180018975  nop     dword ptr [rax+rax+00h]
0x18001897a  mov     rbx, [rsp+28h+arg_0]
0x18001897f  add     rsp, 20h
0x180018983  pop     rdi
0x180018984  retn
```
