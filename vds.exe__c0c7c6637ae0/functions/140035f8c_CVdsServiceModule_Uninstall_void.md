# CVdsServiceModule::Uninstall(void)

- ea: `0x140035f8c`
- end: `0x1400360d2`
- name: `?Uninstall@CVdsServiceModule@@QEAAHXZ`
- size: `326`
- prototype: `__int64 __fastcall(CVdsServiceModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x140022020`
- `0x14003618c`

## callees

- `0x140024ea4`
- `0x140024f60`
- `0x140035f8c`
- `0x140052e80`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140035ffd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140035ffd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140036039`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140036070`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140036079`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140036039`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140036070`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140036079`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x140036065`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x140036065`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140036028`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140036028`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x14003605c`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x14003605c`
- `vdsutil!RemoveEventSource` at `0x140036086`
- `vdsutil!RemoveEventSource` at `0x140036086`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140035fc1`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140035fc1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140035fe6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400360a8`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140035fe6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400360a8`

## string_xrefs

- `0x14003607f`: `Virtual Disk Service`
- `0x140035fb0`: `CVdsServiceModule::Uninstall()`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsServiceModule::Uninstall(CVdsServiceModule *this)
{
  int IsInstalled; // eax
  unsigned int v3; // esi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rbp
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // r14
  unsigned int v9; // edx
  BOOL v10; // ebx
  _BYTE v11[16]; // [rsp+20h] [rbp-58h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-48h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v11, 0x5Eu, "CVdsServiceModule::Uninstall()");
  IsInstalled = CVdsServiceModule::IsInstalled(this);
  v3 = 1;
  if ( IsInstalled == 1 )
    goto LABEL_11;
  if ( IsInstalled < 0 )
  {
LABEL_3:
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
    return 0;
  }
  v5 = OpenSCManagerW(0, 0, 0xF003Fu);
  v6 = v5;
  if ( !v5 )
  {
    CVdsServiceModule::DisplayMessage(this, 0x68u, 0x10u);
    goto LABEL_3;
  }
  v7 = OpenServiceW(v5, (LPCWSTR)this, 0x10020u);
  v8 = v7;
  if ( !v7 )
  {
    CloseServiceHandle(v6);
    v9 = 106;
LABEL_10:
    CVdsServiceModule::DisplayMessage(this, v9, 0x10u);
    v3 = 0;
    goto LABEL_11;
  }
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  ControlService(v7, 1u, &ServiceStatus);
  v10 = DeleteService(v8);
  CloseServiceHandle(v8);
  CloseServiceHandle(v6);
  RemoveEventSource(L"Virtual Disk Service");
  if ( !v10 )
  {
    v9 = 107;
    goto LABEL_10;
  }
LABEL_11:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
  return v3;
}

```

## disassembly

```asm
0x140035f8c  mov     [rsp+arg_8], rbx
0x140035f91  mov     [rsp+arg_10], rbp
0x140035f96  push    rsi
0x140035f97  push    rdi
0x140035f98  push    r14
0x140035f9a  sub     rsp, 60h
0x140035f9e  mov     rax, cs:__security_cookie
0x140035fa5  xor     rax, rsp
0x140035fa8  mov     [rsp+78h+var_28], rax
0x140035fad  mov     rdi, rcx
0x140035fb0  lea     r8, aCvdsservicemod_22; "CVdsServiceModule::Uninstall()"
0x140035fb7  mov     edx, 5Eh ; '^'
0x140035fbc  lea     rcx, [rsp+78h+var_58]
0x140035fc1  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140035fc7  nop
0x140035fc8  mov     rcx, rdi; this
0x140035fcb  call    ?IsInstalled@CVdsServiceModule@@QEAAJXZ; CVdsServiceModule::IsInstalled(void)
0x140035fd0  mov     esi, 1
0x140035fd5  cmp     eax, esi
0x140035fd7  jz      loc_1400360A3
0x140035fdd  test    eax, eax
0x140035fdf  jns     short loc_140035FF3
0x140035fe1  lea     rcx, [rsp+78h+var_58]
0x140035fe6  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140035fec  xor     eax, eax
0x140035fee  jmp     loc_1400360B0
0x140035ff3  xor     edx, edx; lpDatabaseName
0x140035ff5  xor     ecx, ecx; lpMachineName
0x140035ff7  mov     r8d, 0F003Fh; dwDesiredAccess
0x140035ffd  call    cs:__imp_OpenSCManagerW
0x140036003  mov     rbp, rax
0x140036006  test    rax, rax
0x140036009  jnz     short loc_14003601C
0x14003600b  lea     edx, [rax+68h]; unsigned int
0x14003600e  lea     r8d, [rax+10h]; unsigned int
0x140036012  mov     rcx, rdi; this
0x140036015  call    ?DisplayMessage@CVdsServiceModule@@QEAAXKI@Z; CVdsServiceModule::DisplayMessage(ulong,uint)
0x14003601a  jmp     short loc_140035FE1
0x14003601c  mov     r8d, 10020h; dwDesiredAccess
0x140036022  mov     rdx, rdi; lpServiceName
0x140036025  mov     rcx, rbp; hSCManager
0x140036028  call    cs:__imp_OpenServiceW
0x14003602e  mov     r14, rax
0x140036031  test    rax, rax
0x140036034  jnz     short loc_140036045
0x140036036  mov     rcx, rbp; hSCObject
0x140036039  call    cs:__imp_CloseServiceHandle
0x14003603f  lea     edx, [r14+6Ah]
0x140036043  jmp     short loc_140036093
0x140036045  xorps   xmm0, xmm0
0x140036048  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x14003604d  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x140036052  lea     r8, [rsp+78h+ServiceStatus]; lpServiceStatus
0x140036057  mov     edx, esi; dwControl
0x140036059  mov     rcx, r14; hService
0x14003605c  call    cs:__imp_ControlService
0x140036062  mov     rcx, r14; hService
0x140036065  call    cs:__imp_DeleteService
0x14003606b  mov     ebx, eax
0x14003606d  mov     rcx, r14; hSCObject
0x140036070  call    cs:__imp_CloseServiceHandle
0x140036076  mov     rcx, rbp; hSCObject
0x140036079  call    cs:__imp_CloseServiceHandle
0x14003607f  lea     rcx, aVirtualDiskSer; "Virtual Disk Service"
0x140036086  call    cs:__imp_RemoveEventSource
0x14003608c  test    ebx, ebx
0x14003608e  jnz     short loc_1400360A3
0x140036090  lea     edx, [rbx+6Bh]; unsigned int
0x140036093  mov     r8d, 10h; unsigned int
0x140036099  mov     rcx, rdi; this
0x14003609c  call    ?DisplayMessage@CVdsServiceModule@@QEAAXKI@Z; CVdsServiceModule::DisplayMessage(ulong,uint)
0x1400360a1  xor     esi, esi
0x1400360a3  lea     rcx, [rsp+78h+var_58]
0x1400360a8  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400360ae  mov     eax, esi
0x1400360b0  mov     rcx, [rsp+78h+var_28]
0x1400360b5  xor     rcx, rsp; StackCookie
0x1400360b8  call    __security_check_cookie
0x1400360bd  lea     r11, [rsp+78h+var_18]
0x1400360c2  mov     rbx, [r11+28h]
0x1400360c6  mov     rbp, [r11+30h]
0x1400360ca  mov     rsp, r11
0x1400360cd  pop     r14
0x1400360cf  pop     rdi
0x1400360d0  pop     rsi
0x1400360d1  retn
```
