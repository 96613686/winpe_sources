# CServiceMonitorBase::InitializeServiceListening(ushort const *)

- ea: `0x18002c5b4`
- end: `0x18002c644`
- name: `?InitializeServiceListening@CServiceMonitorBase@@QEAAJPEBG@Z`
- size: `144`
- prototype: `__int64 __fastcall(CServiceMonitorBase *__hidden this, LPCWSTR lpServiceName)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000bab4`
- `0x180018730`
- `0x180020ee4`
- `0x18002dfa0`

## callees

- `0x180002590`
- `0x18000d4dc`
- `0x18002c5b4`
- `0x18002c7bc`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002c62c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002c62c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002c5d8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002c5d8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002c5fb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002c5fb`

## string_xrefs

- `0x18002c5c9`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CServiceMonitorBase::InitializeServiceListening(CServiceMonitorBase *this, LPCWSTR lpServiceName)
{
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  int Error; // ebx
  SC_HANDLE v7; // rax

  v4 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v5 = v4;
  if ( v4 )
  {
    v7 = OpenServiceW(v4, lpServiceName, 4u);
    *((_QWORD *)this + 11) = v7;
    if ( v7 )
    {
      Error = CServiceMonitorBase::_RegisterServiceNotifyCallback(this);
      if ( Error < 0 )
        CServiceMonitorBase::UninitializeServiceListening(this);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    CloseServiceHandle(v5);
  }
  else
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002c5b4  mov     [rsp+arg_0], rbx
0x18002c5b9  mov     [rsp+arg_8], rsi
0x18002c5be  push    rdi
0x18002c5bf  sub     rsp, 20h
0x18002c5c3  mov     rbx, rdx
0x18002c5c6  mov     rdi, rcx
0x18002c5c9  lea     rdx, DatabaseName; "ServicesActive"
0x18002c5d0  xor     ecx, ecx; lpMachineName
0x18002c5d2  mov     r8d, 1; dwDesiredAccess
0x18002c5d8  call    cs:__imp_OpenSCManagerW
0x18002c5de  mov     rsi, rax
0x18002c5e1  test    rax, rax
0x18002c5e4  jnz     short loc_18002C5EF
0x18002c5e6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002c5eb  mov     ebx, eax
0x18002c5ed  jmp     short loc_18002C632
0x18002c5ef  mov     r8d, 4; dwDesiredAccess
0x18002c5f5  mov     rdx, rbx; lpServiceName
0x18002c5f8  mov     rcx, rsi; hSCManager
0x18002c5fb  call    cs:__imp_OpenServiceW
0x18002c601  mov     [rdi+58h], rax
0x18002c605  test    rax, rax
0x18002c608  jnz     short loc_18002C613
0x18002c60a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002c60f  mov     ebx, eax
0x18002c611  jmp     short loc_18002C629
0x18002c613  mov     rcx, rdi; this
0x18002c616  call    ?_RegisterServiceNotifyCallback@CServiceMonitorBase@@AEAAJXZ; CServiceMonitorBase::_RegisterServiceNotifyCallback(void)
0x18002c61b  mov     ebx, eax
0x18002c61d  test    eax, eax
0x18002c61f  jns     short loc_18002C629
0x18002c621  mov     rcx, rdi; this
0x18002c624  call    ?UninitializeServiceListening@CServiceMonitorBase@@QEAAXXZ; CServiceMonitorBase::UninitializeServiceListening(void)
0x18002c629  mov     rcx, rsi; hSCObject
0x18002c62c  call    cs:__imp_CloseServiceHandle
0x18002c632  mov     rsi, [rsp+28h+arg_8]
0x18002c637  mov     eax, ebx
0x18002c639  mov     rbx, [rsp+28h+arg_0]
0x18002c63e  add     rsp, 20h
0x18002c642  pop     rdi
0x18002c643  retn
```
