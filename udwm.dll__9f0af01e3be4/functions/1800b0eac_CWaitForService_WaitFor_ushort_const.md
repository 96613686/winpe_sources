# CWaitForService::WaitFor(ushort const *)

- ea: `0x1800b0eac`
- end: `0x1800b0f4c`
- name: `?WaitFor@CWaitForService@@QEAA_NPEBG@Z`
- size: `160`
- prototype: `bool __fastcall(CWaitForService *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001d710`

## callees

- `0x18008ab10`
- `0x1800b0eac`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b0f26`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b0f26`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b0ec9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b0ec9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b0ee7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b0ee7`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800b0f17`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800b0f17`

## pseudocode

```c
bool __fastcall CWaitForService::WaitFor(CWaitForService *this, const unsigned __int16 *a2)
{
  bool v3; // di
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  SC_HANDLE v6; // rax

  v3 = 0;
  v4 = OpenSCManagerW(0, 0, 4u);
  v5 = v4;
  if ( !v4 )
    goto LABEL_5;
  v6 = OpenServiceW(v4, L"RPCSS", 4u);
  *(_QWORD *)this = v6;
  if ( v6 )
  {
    *((_QWORD *)this + 3) = this;
    *((_QWORD *)this + 2) = CWaitForService::s_ServiceStarted;
    *((_DWORD *)this + 2) = 2;
    v3 = NotifyServiceStatusChangeW(v6, 8u, (PSERVICE_NOTIFYW)((char *)this + 8)) == 0;
  }
  CloseServiceHandle(v5);
  if ( !v3 )
LABEL_5:
    CWaitForService::Cleanup(this);
  return v3;
}

```

## disassembly

```asm
0x1800b0eac  mov     [rsp+arg_0], rbx
0x1800b0eb1  mov     [rsp+arg_8], rsi
0x1800b0eb6  push    rdi
0x1800b0eb7  sub     rsp, 20h
0x1800b0ebb  xor     edx, edx; lpDatabaseName
0x1800b0ebd  mov     rbx, rcx
0x1800b0ec0  xor     ecx, ecx; lpMachineName
0x1800b0ec2  xor     dil, dil
0x1800b0ec5  lea     r8d, [rdx+4]; dwDesiredAccess
0x1800b0ec9  call    cs:__imp_OpenSCManagerW
0x1800b0ecf  mov     rsi, rax
0x1800b0ed2  test    rax, rax
0x1800b0ed5  jz      short loc_1800B0F31
0x1800b0ed7  mov     r8d, 4; dwDesiredAccess
0x1800b0edd  lea     rdx, ServiceName; "RPCSS"
0x1800b0ee4  mov     rcx, rax; hSCManager
0x1800b0ee7  call    cs:__imp_OpenServiceW
0x1800b0eed  mov     [rbx], rax
0x1800b0ef0  test    rax, rax
0x1800b0ef3  jz      short loc_1800B0F23
0x1800b0ef5  lea     rcx, ?s_ServiceStarted@CWaitForService@@CAXPEAX@Z; CWaitForService::s_ServiceStarted(void *)
0x1800b0efc  mov     [rbx+18h], rbx
0x1800b0f00  mov     [rbx+10h], rcx
0x1800b0f04  lea     r8, [rbx+8]; pNotifyBuffer
0x1800b0f08  mov     rcx, rax; hService
0x1800b0f0b  mov     dword ptr [r8], 2
0x1800b0f12  mov     edx, 8; dwNotifyMask
0x1800b0f17  call    cs:__imp_NotifyServiceStatusChangeW
0x1800b0f1d  test    eax, eax
0x1800b0f1f  setz    dil
0x1800b0f23  mov     rcx, rsi; hSCObject
0x1800b0f26  call    cs:__imp_CloseServiceHandle
0x1800b0f2c  test    dil, dil
0x1800b0f2f  jnz     short loc_1800B0F39
0x1800b0f31  mov     rcx, rbx; this
0x1800b0f34  call    ?Cleanup@CWaitForService@@QEAAXXZ; CWaitForService::Cleanup(void)
0x1800b0f39  mov     rbx, [rsp+28h+arg_0]
0x1800b0f3e  mov     al, dil
0x1800b0f41  mov     rsi, [rsp+28h+arg_8]
0x1800b0f46  add     rsp, 20h
0x1800b0f4a  pop     rdi
0x1800b0f4b  retn
```
