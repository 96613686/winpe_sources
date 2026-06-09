# CServiceMonitorBase::UninitializeServiceListening(void)

- ea: `0x18002c7bc`
- end: `0x18002c7e2`
- name: `?UninitializeServiceListening@CServiceMonitorBase@@QEAAXXZ`
- size: `38`
- prototype: `void __fastcall(CServiceMonitorBase *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180002590`
- `0x18000bab4`
- `0x180018730`
- `0x180020ee4`
- `0x18002c5b4`
- `0x18002e3e0`

## callees

- `0x18002c7bc`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002c7ce`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002c7ce`

## pseudocode

```c
void __fastcall CServiceMonitorBase::UninitializeServiceListening(CServiceMonitorBase *this)
{
  SC_HANDLE v2; // rcx

  v2 = (SC_HANDLE)*((_QWORD *)this + 11);
  if ( v2 )
  {
    CloseServiceHandle(v2);
    *((_QWORD *)this + 11) = 0;
  }
}

```

## disassembly

```asm
0x18002c7bc  push    rbx
0x18002c7be  sub     rsp, 20h
0x18002c7c2  mov     rbx, rcx
0x18002c7c5  mov     rcx, [rcx+58h]; hSCObject
0x18002c7c9  test    rcx, rcx
0x18002c7cc  jz      short loc_18002C7DC
0x18002c7ce  call    cs:__imp_CloseServiceHandle
0x18002c7d4  mov     qword ptr [rbx+58h], 0
0x18002c7dc  add     rsp, 20h
0x18002c7e0  pop     rbx
0x18002c7e1  retn
```
