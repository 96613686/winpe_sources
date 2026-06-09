# CRegistryEventRequest::Activate(void)

- ea: `0x180013d88`
- end: `0x180013e5b`
- name: `?Activate@CRegistryEventRequest@@QEAAJXZ`
- size: `211`
- prototype: `signed int __fastcall(CRegistryEventRequest *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008570`

## callees

- `0x1800080b8`
- `0x180013d88`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013db1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013db1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013dcf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013dcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e16`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180013e0c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180013e0c`

## pseudocode

```c
signed int __fastcall CRegistryEventRequest::Activate(CRegistryEventRequest *this)
{
  signed int result; // eax
  HANDLE EventW; // rax
  HKEY v4; // rax

  if ( RegOpenKeyExW(*((HKEY *)this + 15), *((LPCWSTR *)this + 17), 0, 0x20019u, (PHKEY)this + 18) )
    return -2147217400;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 19) = EventW;
  if ( !EventW )
    return -2147217402;
  if ( RegisterWaitForSingleObject((PHANDLE)this + 22, EventW, CRegEventProvider::EnqueueEvent, this, 0xFFFFFFFF, 4u) )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    v4 = *(HKEY *)this;
    *((_DWORD *)this + 42) = 1;
    (*((void (__fastcall **)(CRegistryEventRequest *))v4 + 2))(this);
    CRegEventProvider::EnqueueEvent(*((CRegEventProvider **)this + 2), this);
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180013d88  push    rbx
0x180013d8a  sub     rsp, 30h
0x180013d8e  mov     rdx, [rcx+88h]; lpSubKey
0x180013d95  lea     rax, [rcx+90h]
0x180013d9c  mov     rbx, rcx
0x180013d9f  mov     [rsp+38h+phkResult], rax; phkResult
0x180013da4  mov     rcx, [rcx+78h]; hKey
0x180013da8  mov     r9d, 20019h; samDesired
0x180013dae  xor     r8d, r8d; ulOptions
0x180013db1  call    cs:__imp_RegOpenKeyExW
0x180013db7  test    eax, eax
0x180013db9  jz      short loc_180013DC5
0x180013dbb  mov     eax, 80041008h
0x180013dc0  jmp     loc_180013E55
0x180013dc5  xor     r9d, r9d; lpName
0x180013dc8  xor     r8d, r8d; bInitialState
0x180013dcb  xor     edx, edx; bManualReset
0x180013dcd  xor     ecx, ecx; lpEventAttributes
0x180013dcf  call    cs:__imp_CreateEventW
0x180013dd5  mov     [rbx+98h], rax
0x180013ddc  test    rax, rax
0x180013ddf  jnz     short loc_180013DE8
0x180013de1  mov     eax, 80041006h
0x180013de6  jmp     short loc_180013E55
0x180013de8  lea     rcx, [rbx+0B0h]; phNewWaitObject
0x180013def  mov     [rsp+38h+dwFlags], 4; dwFlags
0x180013df7  mov     r9, rbx; Context
0x180013dfa  mov     dword ptr [rsp+38h+phkResult], 0FFFFFFFFh; dwMilliseconds
0x180013e02  lea     r8, ?EnqueueEvent@CRegEventProvider@@SAXPEAXE@Z; Callback
0x180013e09  mov     rdx, rax; hObject
0x180013e0c  call    cs:__imp_RegisterWaitForSingleObject
0x180013e12  test    eax, eax
0x180013e14  jnz     short loc_180013E2A
0x180013e16  call    cs:__imp_GetLastError
0x180013e1c  test    eax, eax
0x180013e1e  jle     short loc_180013E55
0x180013e20  movzx   eax, ax
0x180013e23  or      eax, 80070000h
0x180013e28  jmp     short loc_180013E55
0x180013e2a  lock inc dword ptr [rbx+8]
0x180013e2e  mov     rax, [rbx]
0x180013e31  mov     rcx, rbx
0x180013e34  mov     dword ptr [rbx+0A8h], 1
0x180013e3e  mov     rax, [rax+10h]
0x180013e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e47  mov     rcx, [rbx+10h]; this
0x180013e4b  mov     rdx, rbx; struct CRegistryEventRequest *
0x180013e4e  call    ?EnqueueEvent@CRegEventProvider@@QEAAXPEAVCRegistryEventRequest@@@Z; CRegEventProvider::EnqueueEvent(CRegistryEventRequest *)
0x180013e53  xor     eax, eax
0x180013e55  add     rsp, 30h
0x180013e59  pop     rbx
0x180013e5a  retn
```
