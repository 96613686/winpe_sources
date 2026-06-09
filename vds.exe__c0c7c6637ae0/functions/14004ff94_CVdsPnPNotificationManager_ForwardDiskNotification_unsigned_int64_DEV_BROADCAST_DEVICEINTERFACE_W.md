# CVdsPnPNotificationManager::ForwardDiskNotification(unsigned __int64,_DEV_BROADCAST_DEVICEINTERFACE_W *)

- ea: `0x14004ff94`
- end: `0x140050072`
- name: `?ForwardDiskNotification@CVdsPnPNotificationManager@@AEAAX_KPEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@@Z`
- size: `222`
- prototype: `void(CVdsPnPNotificationManager *__hidden this, unsigned __int64, struct _DEV_BROADCAST_DEVICEINTERFACE_W *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007e20`

## callees

- `0x14002de26`
- `0x14004ff94`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x14005001a`
- `USER32!PostThreadMessageW` at `0x14005001a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004ffc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140050042`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004ffc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140050042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050024`
- `vdsutil!VdsHeapAlloc` at `0x14004ffd4`
- `vdsutil!VdsHeapAlloc` at `0x14004ffd4`
- `vdsutil!VdsHeapFree` at `0x140050050`
- `vdsutil!VdsHeapFree` at `0x140050050`
- `vdsutil!VdsTraceEx` at `0x14004fff3`
- `vdsutil!VdsTraceEx` at `0x14005003c`
- `vdsutil!VdsTraceEx` at `0x14004fff3`
- `vdsutil!VdsTraceEx` at `0x14005003c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004ffba`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004ffba`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14005005c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14005005c`

## string_xrefs

- `0x14005002d`: `CVdsPnPNotificationManager::ForwardDiskNotification: PostThreadMessage failed: %X `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVdsPnPNotificationManager::ForwardDiskNotification(
        CVdsPnPNotificationManager *this,
        WPARAM a2,
        struct _DEV_BROADCAST_DEVICEINTERFACE_W *a3)
{
  DWORD dbcc_size; // ebx
  HANDLE ProcessHeap; // rax
  void *v7; // rax
  LPARAM v8; // rbx
  DWORD LastError; // eax
  HANDLE v10; // rax
  _BYTE v11[24]; // [rsp+20h] [rbp-18h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v11, 0x5Eu, "CVdsPnPNotificationManager::ForwardDiskNotification()");
  dbcc_size = a3->dbcc_size;
  ProcessHeap = GetProcessHeap();
  v7 = (void *)VdsHeapAlloc(ProcessHeap, 8, dbcc_size);
  v8 = (LPARAM)v7;
  if ( v7 )
  {
    memcpy_0(v7, a3, a3->dbcc_size);
    if ( !PostThreadMessageW(CVdsPnPNotificationManager::m_dwAuxThreadId, 0x404u, a2, v8) )
    {
      LastError = GetLastError();
      VdsTraceEx(94, 1, "CVdsPnPNotificationManager::ForwardDiskNotification: PostThreadMessage failed: %X ", LastError);
      v10 = GetProcessHeap();
      VdsHeapFree(v10, 0, v8);
    }
  }
  else
  {
    VdsTraceEx(
      94,
      1,
      "CVdsPnPNotificationManager::ForwardDiskNotification: Out of memory. A disk arrival/removal notification is lost: %S",
      a3->dbcc_name);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
}

```

## disassembly

```asm
0x14004ff94  mov     [rsp+arg_0], rbx
0x14004ff99  mov     [rsp+arg_8], rsi
0x14004ff9e  push    rdi
0x14004ff9f  sub     rsp, 30h
0x14004ffa3  mov     rdi, r8
0x14004ffa6  mov     rsi, rdx
0x14004ffa9  lea     r8, aCvdspnpnotific_18; "CVdsPnPNotificationManager::ForwardDisk"...
0x14004ffb0  mov     edx, 5Eh ; '^'
0x14004ffb5  lea     rcx, [rsp+38h+var_18]
0x14004ffba  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14004ffc0  nop
0x14004ffc1  mov     ebx, [rdi]
0x14004ffc3  call    cs:__imp_GetProcessHeap
0x14004ffc9  mov     r8d, ebx
0x14004ffcc  mov     edx, 8
0x14004ffd1  mov     rcx, rax
0x14004ffd4  call    cs:__imp_VdsHeapAlloc
0x14004ffda  mov     rbx, rax
0x14004ffdd  test    rax, rax
0x14004ffe0  jnz     short loc_14004FFFB
0x14004ffe2  lea     r9, [rdi+1Ch]
0x14004ffe6  lea     r8, aCvdspnpnotific_25; "CVdsPnPNotificationManager::ForwardDisk"...
0x14004ffed  lea     edx, [rax+1]
0x14004fff0  lea     ecx, [rax+5Eh]
0x14004fff3  call    cs:__imp_VdsTraceEx
0x14004fff9  jmp     short loc_140050057
0x14004fffb  mov     r8d, [rdi]; Size
0x14004fffe  mov     rdx, rdi; Src
0x140050001  mov     rcx, rbx; void *
0x140050004  call    memcpy_0
0x140050009  mov     r9, rbx; lParam
0x14005000c  mov     r8, rsi; wParam
0x14005000f  mov     edx, 404h; Msg
0x140050014  mov     ecx, cs:?m_dwAuxThreadId@CVdsPnPNotificationManager@@0KA; idThread
0x14005001a  call    cs:__imp_PostThreadMessageW
0x140050020  test    eax, eax
0x140050022  jnz     short loc_140050057
0x140050024  call    cs:__imp_GetLastError
0x14005002a  mov     r9d, eax
0x14005002d  lea     r8, aCvdspnpnotific_0; "CVdsPnPNotificationManager::ForwardDisk"...
0x140050034  mov     edx, 1
0x140050039  lea     ecx, [rdx+5Dh]
0x14005003c  call    cs:__imp_VdsTraceEx
0x140050042  call    cs:__imp_GetProcessHeap
0x140050048  mov     rcx, rax
0x14005004b  mov     r8, rbx
0x14005004e  xor     edx, edx
0x140050050  call    cs:__imp_VdsHeapFree
0x140050056  nop
0x140050057  lea     rcx, [rsp+38h+var_18]
0x14005005c  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140050062  mov     rbx, [rsp+38h+arg_0]
0x140050067  mov     rsi, [rsp+38h+arg_8]
0x14005006c  add     rsp, 30h
0x140050070  pop     rdi
0x140050071  retn
```
