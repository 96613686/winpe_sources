# CVdsServiceModule::IsInstalled(void)

- ea: `0x140024ea4`
- end: `0x140024f59`
- name: `?IsInstalled@CVdsServiceModule@@QEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(CVdsServiceModule *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x140033374`
- `0x140035f8c`

## callees

- `0x140024ea4`
- `0x140024f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024f15`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140024ed8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140024ed8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140024f04`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140024f0d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140024f04`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140024f0d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140024ef4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140024ef4`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140024ec7`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140024ec7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140024f41`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140024f41`

## string_xrefs

- `0x140024eb6`: `CVdsServiceModule::IsInstalled()`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsServiceModule::IsInstalled(WCHAR *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rdi
  unsigned int v4; // ebx
  SC_HANDLE v5; // rax
  signed int LastError; // eax
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v8, 0x5Eu, "CVdsServiceModule::IsInstalled()");
  v2 = OpenSCManagerW(0, 0, 0xF003Fu);
  v3 = v2;
  if ( v2 )
  {
    v4 = 1;
    v5 = OpenServiceW(v2, this, 1u);
    if ( v5 )
    {
      v4 = 0;
      CloseServiceHandle(v5);
    }
    CloseServiceHandle(v3);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    CVdsServiceModule::DisplayMessage((CVdsServiceModule *)this, 0x68u, 0x10u);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v8);
  return v4;
}

```

## disassembly

```asm
0x140024ea4  mov     [rsp+arg_0], rbx
0x140024ea9  mov     [rsp+arg_8], rsi
0x140024eae  push    rdi
0x140024eaf  sub     rsp, 30h
0x140024eb3  mov     rsi, rcx
0x140024eb6  lea     r8, aCvdsservicemod_29; "CVdsServiceModule::IsInstalled()"
0x140024ebd  mov     edx, 5Eh ; '^'
0x140024ec2  lea     rcx, [rsp+38h+var_18]
0x140024ec7  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140024ecd  nop
0x140024ece  xor     edx, edx; lpDatabaseName
0x140024ed0  xor     ecx, ecx; lpMachineName
0x140024ed2  mov     r8d, 0F003Fh; dwDesiredAccess
0x140024ed8  call    cs:__imp_OpenSCManagerW
0x140024ede  mov     rdi, rax
0x140024ee1  test    rax, rax
0x140024ee4  jz      short loc_140024F15
0x140024ee6  mov     ebx, 1
0x140024eeb  mov     r8d, ebx; dwDesiredAccess
0x140024eee  mov     rdx, rsi; lpServiceName
0x140024ef1  mov     rcx, rax; hSCManager
0x140024ef4  call    cs:__imp_OpenServiceW
0x140024efa  test    rax, rax
0x140024efd  jz      short loc_140024F0A
0x140024eff  xor     ebx, ebx
0x140024f01  mov     rcx, rax; hSCObject
0x140024f04  call    cs:__imp_CloseServiceHandle
0x140024f0a  mov     rcx, rdi; hSCObject
0x140024f0d  call    cs:__imp_CloseServiceHandle
0x140024f13  jmp     short loc_140024F3C
0x140024f15  call    cs:__imp_GetLastError
0x140024f1b  mov     ebx, eax
0x140024f1d  test    eax, eax
0x140024f1f  jle     short loc_140024F2A
0x140024f21  movzx   ebx, ax
0x140024f24  or      ebx, 80070000h
0x140024f2a  mov     edx, 68h ; 'h'; unsigned int
0x140024f2f  lea     r8d, [rdx-58h]; unsigned int
0x140024f33  mov     rcx, rsi; this
0x140024f36  call    ?DisplayMessage@CVdsServiceModule@@QEAAXKI@Z; CVdsServiceModule::DisplayMessage(ulong,uint)
0x140024f3b  nop
0x140024f3c  lea     rcx, [rsp+38h+var_18]
0x140024f41  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140024f47  mov     eax, ebx
0x140024f49  mov     rbx, [rsp+38h+arg_0]
0x140024f4e  mov     rsi, [rsp+38h+arg_8]
0x140024f53  add     rsp, 30h
0x140024f57  pop     rdi
0x140024f58  retn
```
