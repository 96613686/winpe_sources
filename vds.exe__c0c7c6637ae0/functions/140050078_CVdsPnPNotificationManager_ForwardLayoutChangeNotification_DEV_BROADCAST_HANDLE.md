# CVdsPnPNotificationManager::ForwardLayoutChangeNotification(_DEV_BROADCAST_HANDLE *)

- ea: `0x140050078`
- end: `0x140050145`
- name: `?ForwardLayoutChangeNotification@CVdsPnPNotificationManager@@AEAAXPEAU_DEV_BROADCAST_HANDLE@@@Z`
- size: `205`
- prototype: `void(CVdsPnPNotificationManager *__hidden this, struct _DEV_BROADCAST_HANDLE *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007e20`

## callees

- `0x14002de26`
- `0x140050078`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x1400500f2`
- `USER32!PostThreadMessageW` at `0x1400500f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005009f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005011a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005009f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005011a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400500fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400500fc`
- `vdsutil!VdsHeapAlloc` at `0x1400500b0`
- `vdsutil!VdsHeapAlloc` at `0x1400500b0`
- `vdsutil!VdsHeapFree` at `0x140050128`
- `vdsutil!VdsHeapFree` at `0x140050128`
- `vdsutil!VdsTraceEx` at `0x1400500cb`
- `vdsutil!VdsTraceEx` at `0x140050114`
- `vdsutil!VdsTraceEx` at `0x1400500cb`
- `vdsutil!VdsTraceEx` at `0x140050114`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140050096`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140050096`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140050134`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140050134`

## string_xrefs

- `0x140050105`: `CVdsPnPNotificationManager::ForwardLayoutChangeNotification: PostThreadMessage failed: %X `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVdsPnPNotificationManager::ForwardLayoutChangeNotification(
        CVdsPnPNotificationManager *this,
        struct _DEV_BROADCAST_HANDLE *a2)
{
  DWORD dbch_size; // ebx
  HANDLE ProcessHeap; // rax
  void *v5; // rax
  LPARAM v6; // rbx
  DWORD LastError; // eax
  HANDLE v8; // rax
  _BYTE v9[24]; // [rsp+20h] [rbp-18h] BYREF

  CVdsCallTracer::CVdsCallTracer(
    (CVdsCallTracer *)v9,
    0x5Eu,
    "CVdsPnPNotificationManager::ForwardLayoutChangeNotification()");
  dbch_size = a2->dbch_size;
  ProcessHeap = GetProcessHeap();
  v5 = (void *)VdsHeapAlloc(ProcessHeap, 8, dbch_size);
  v6 = (LPARAM)v5;
  if ( v5 )
  {
    memcpy_0(v5, a2, a2->dbch_size);
    if ( !PostThreadMessageW(CVdsPnPNotificationManager::m_dwAuxThreadId, 0x405u, 0, v6) )
    {
      LastError = GetLastError();
      VdsTraceEx(
        94,
        1,
        "CVdsPnPNotificationManager::ForwardLayoutChangeNotification: PostThreadMessage failed: %X ",
        LastError);
      v8 = GetProcessHeap();
      VdsHeapFree(v8, 0, v6);
    }
  }
  else
  {
    VdsTraceEx(
      94,
      1,
      "CVdsPnPNotificationManager::ForwardLayoutChangeNotification: Out of memory. A disk layout change notification is lost.");
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v9);
}

```

## disassembly

```asm
0x140050078  mov     [rsp+arg_0], rbx
0x14005007d  push    rdi
0x14005007e  sub     rsp, 30h
0x140050082  mov     rdi, rdx
0x140050085  lea     r8, aCvdspnpnotific_12; "CVdsPnPNotificationManager::ForwardLayo"...
0x14005008c  mov     edx, 5Eh ; '^'
0x140050091  lea     rcx, [rsp+38h+var_18]
0x140050096  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14005009c  nop
0x14005009d  mov     ebx, [rdi]
0x14005009f  call    cs:__imp_GetProcessHeap
0x1400500a5  mov     r8d, ebx
0x1400500a8  mov     edx, 8
0x1400500ad  mov     rcx, rax
0x1400500b0  call    cs:__imp_VdsHeapAlloc
0x1400500b6  mov     rbx, rax
0x1400500b9  test    rax, rax
0x1400500bc  jnz     short loc_1400500D3
0x1400500be  lea     r8, aCvdspnpnotific_37; "CVdsPnPNotificationManager::ForwardLayo"...
0x1400500c5  lea     edx, [rax+1]
0x1400500c8  lea     ecx, [rax+5Eh]
0x1400500cb  call    cs:__imp_VdsTraceEx
0x1400500d1  jmp     short loc_14005012F
0x1400500d3  mov     r8d, [rdi]; Size
0x1400500d6  mov     rdx, rdi; Src
0x1400500d9  mov     rcx, rbx; void *
0x1400500dc  call    memcpy_0
0x1400500e1  mov     r9, rbx; lParam
0x1400500e4  xor     r8d, r8d; wParam
0x1400500e7  mov     edx, 405h; Msg
0x1400500ec  mov     ecx, cs:?m_dwAuxThreadId@CVdsPnPNotificationManager@@0KA; idThread
0x1400500f2  call    cs:__imp_PostThreadMessageW
0x1400500f8  test    eax, eax
0x1400500fa  jnz     short loc_14005012F
0x1400500fc  call    cs:__imp_GetLastError
0x140050102  mov     r9d, eax
0x140050105  lea     r8, aCvdspnpnotific; "CVdsPnPNotificationManager::ForwardLayo"...
0x14005010c  mov     edx, 1
0x140050111  lea     ecx, [rdx+5Dh]
0x140050114  call    cs:__imp_VdsTraceEx
0x14005011a  call    cs:__imp_GetProcessHeap
0x140050120  mov     rcx, rax
0x140050123  mov     r8, rbx
0x140050126  xor     edx, edx
0x140050128  call    cs:__imp_VdsHeapFree
0x14005012e  nop
0x14005012f  lea     rcx, [rsp+38h+var_18]
0x140050134  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14005013a  mov     rbx, [rsp+38h+arg_0]
0x14005013f  add     rsp, 30h
0x140050143  pop     rdi
0x140050144  retn
```
