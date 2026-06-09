# CServiceMonitor::Start(ulong)

- ea: `0x18002c558`
- end: `0x18002c5e0`
- name: `?Start@CServiceMonitor@@QEAAJK@Z`
- size: `136`
- prototype: `__int64 __fastcall(CServiceMonitor *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180029a08`

## callees

- `0x18002a06c`
- `0x18002c558`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002c5cd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002c5cd`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18002c5ad`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18002c5ad`

## pseudocode

```c
__int64 __fastcall CServiceMonitor::Start(CServiceMonitor *this)
{
  __int64 result; // rax
  unsigned int v3; // ebx
  int v4; // eax

  if ( !*((_QWORD *)this + 68) )
    return 2147500035LL;
  *((_DWORD *)this + 132) = 44;
  result = CServiceMonitor::AttachToService((const WCHAR *)this);
  v3 = result;
  if ( (int)result >= 0 )
  {
    v4 = SubscribeServiceChangeNotifications(
           *((_QWORD *)this + 67),
           2,
           CServiceMonitor::OnStatusChanged,
           this,
           (char *)this + 552);
    if ( v4 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      else
        v3 = v4;
      CloseServiceHandle(*((SC_HANDLE *)this + 67));
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18002c558  mov     [rsp+arg_0], rbx
0x18002c55d  push    rdi
0x18002c55e  sub     rsp, 30h
0x18002c562  cmp     qword ptr [rcx+220h], 0
0x18002c56a  mov     rdi, rcx
0x18002c56d  jnz     short loc_18002C576
0x18002c56f  mov     eax, 80004003h
0x18002c574  jmp     short loc_18002C5D5
0x18002c576  mov     dword ptr [rcx+210h], 2Ch ; ','
0x18002c580  call    ?AttachToService@CServiceMonitor@@IEAAJXZ; CServiceMonitor::AttachToService(void)
0x18002c585  mov     ebx, eax
0x18002c587  test    eax, eax
0x18002c589  js      short loc_18002C5D5
0x18002c58b  mov     rcx, [rdi+218h]
0x18002c592  lea     rax, [rdi+228h]
0x18002c599  mov     r9, rdi
0x18002c59c  mov     [rsp+38h+var_18], rax
0x18002c5a1  lea     r8, ?OnStatusChanged@CServiceMonitor@@KAXKPEAX@Z; CServiceMonitor::OnStatusChanged(ulong,void *)
0x18002c5a8  mov     edx, 2
0x18002c5ad  call    cs:__imp_SubscribeServiceChangeNotifications
0x18002c5b3  test    eax, eax
0x18002c5b5  jz      short loc_18002C5D3
0x18002c5b7  jg      short loc_18002C5BD
0x18002c5b9  mov     ebx, eax
0x18002c5bb  jmp     short loc_18002C5C6
0x18002c5bd  movzx   ebx, ax
0x18002c5c0  or      ebx, 80070000h
0x18002c5c6  mov     rcx, [rdi+218h]; hSCObject
0x18002c5cd  call    cs:__imp_CloseServiceHandle
0x18002c5d3  mov     eax, ebx
0x18002c5d5  mov     rbx, [rsp+38h+arg_0]
0x18002c5da  add     rsp, 30h
0x18002c5de  pop     rdi
0x18002c5df  retn
```
