# CServiceMonitor::`scalar deleting destructor'(uint)

- ea: `0x180029e80`
- end: `0x180029ef3`
- name: `??_GCServiceMonitor@@UEAAPEAXI@Z`
- size: `115`
- prototype: `void *__fastcall(CServiceMonitor *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x1800012e8`
- `0x180029e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ed1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ed1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180029ebc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180029ebc`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180029eaf`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180029eaf`

## pseudocode

```c
CServiceMonitor *__fastcall CServiceMonitor::`scalar deleting destructor'(CServiceMonitor *this, char a2)
{
  bool v2; // zf
  BOOL v5; // eax

  v2 = *((_QWORD *)this + 67) == 0;
  *(_QWORD *)this = &CServiceMonitor::`vftable';
  if ( !v2 )
  {
    if ( *((_QWORD *)this + 69) )
      UnsubscribeServiceChangeNotifications();
    v5 = CloseServiceHandle(*((SC_HANDLE *)this + 67));
    *((_QWORD *)this + 67) = 0;
    if ( !v5 )
      GetLastError();
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180029e80  mov     [rsp+arg_0], rbx
0x180029e85  push    rdi
0x180029e86  sub     rsp, 20h
0x180029e8a  cmp     qword ptr [rcx+218h], 0
0x180029e92  lea     rax, ??_7CServiceMonitor@@6B@; const CServiceMonitor::`vftable'
0x180029e99  mov     [rcx], rax
0x180029e9c  mov     edi, edx
0x180029e9e  mov     rbx, rcx
0x180029ea1  jz      short loc_180029ED7
0x180029ea3  mov     rcx, [rcx+228h]
0x180029eaa  test    rcx, rcx
0x180029ead  jz      short loc_180029EB5
0x180029eaf  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180029eb5  mov     rcx, [rbx+218h]; hSCObject
0x180029ebc  call    cs:__imp_CloseServiceHandle
0x180029ec2  mov     qword ptr [rbx+218h], 0
0x180029ecd  test    eax, eax
0x180029ecf  jnz     short loc_180029ED7
0x180029ed1  call    cs:__imp_GetLastError
0x180029ed7  test    dil, 1
0x180029edb  jz      short loc_180029EE5
0x180029edd  mov     rcx, rbx; Block
0x180029ee0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029ee5  mov     rax, rbx
0x180029ee8  mov     rbx, [rsp+28h+arg_0]
0x180029eed  add     rsp, 20h
0x180029ef1  pop     rdi
0x180029ef2  retn
```
