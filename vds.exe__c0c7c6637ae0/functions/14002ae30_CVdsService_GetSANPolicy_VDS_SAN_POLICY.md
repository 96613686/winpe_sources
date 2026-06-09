# CVdsService::GetSANPolicy(_VDS_SAN_POLICY *)

- ea: `0x14002ae30`
- end: `0x14002afe0`
- name: `?GetSANPolicy@CVdsService@@UEAAJPEAW4_VDS_SAN_POLICY@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, enum _VDS_SAN_POLICY *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x140003710`
- `0x140004360`
- `0x14002ae30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002af44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002af44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002afab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002afab`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002af3a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002af3a`
- `vdsutil!OpenDevice` at `0x14002aecb`
- `vdsutil!OpenDevice` at `0x14002aecb`
- `vdsutil!VdsTraceEx` at `0x14002aef9`
- `vdsutil!VdsTraceEx` at `0x14002af97`
- `vdsutil!VdsTraceEx` at `0x14002aef9`
- `vdsutil!VdsTraceEx` at `0x14002af97`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002ae6e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002ae6e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002afc7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002afc7`

## string_xrefs

- `0x14002af59`: `CVdsService::GetSANPolicy, 5, hr=%lX`
- `0x14002aeea`: `CVdsService::GetSANPolicy, 4, hr=%lX`
- `0x14002ae5a`: `CVdsService::GetSANPolicy()`
- `0x14002aea9`: `CVdsService::GetSANPolicy, 1`
- `0x14002af8b`: `CVdsService::GetSANPolicy, 6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::GetSANPolicy(CVdsService *this, enum _VDS_SAN_POLICY *a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  signed int LastError; // eax
  __int64 OutBuffer; // [rsp+40h] [rbp-30h] BYREF
  __int64 v8; // [rsp+48h] [rbp-28h] BYREF
  int v9; // [rsp+50h] [rbp-20h]
  _BYTE v10[24]; // [rsp+58h] [rbp-18h] BYREF
  DWORD BytesReturned; // [rsp+A0h] [rbp+30h] BYREF
  HANDLE hDevice; // [rsp+A8h] [rbp+38h] BYREF

  hDevice = 0;
  BytesReturned = 0;
  OutBuffer = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v10, 0x5Eu, "CVdsService::GetSANPolicy()");
  v8 = 0;
  v9 = 0;
  v3 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v8);
  if ( (v3 & 0x80000000) == 0 )
  {
    OutBuffer = 0;
    if ( a2 )
    {
      *a2 = VDS_SP_UNKNOWN;
      v4 = OpenDevice(L"\\\\.\\PartmgrControl", 0x80000000LL, &hDevice);
      v3 = v4;
      if ( v4 )
      {
        if ( v4 > 0 )
          v3 = (unsigned __int16)v4 | 0x80070000;
        hDevice = 0;
        VdsTraceEx(94, 0, "CVdsService::GetSANPolicy, 4, hr=%lX", v3);
      }
      else
      {
        LODWORD(OutBuffer) = 8;
        if ( DeviceIoControl(hDevice, 0x74200u, 0, 0, &OutBuffer, 8u, &BytesReturned, 0) )
        {
          v3 = 0;
          switch ( HIDWORD(OutBuffer) )
          {
            case 1:
              *a2 = VDS_SP_ONLINE;
              break;
            case 2:
              *a2 = VDS_SP_OFFLINE_SHARED;
              break;
            case 3:
              *a2 = VDS_SP_OFFLINE;
              break;
            case 4:
              *a2 = VDS_SP_OFFLINE_INTERNAL;
              break;
            default:
              VdsTraceEx(94, 0, "CVdsService::GetSANPolicy, 6");
              break;
          }
        }
        else
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          VdsTraceEx(94, 0, "CVdsService::GetSANPolicy, 5, hr=%lX", v3);
        }
      }
    }
    else
    {
      v3 = -2147024809;
      VdsTraceEx(94, 0, "CVdsService::GetSANPolicy, 1");
    }
    if ( (char *)hDevice - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hDevice);
      hDevice = (HANDLE)-1LL;
    }
  }
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v8);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v10);
  return v3;
}

```

## disassembly

```asm
0x14002ae30  mov     [rsp-18h+arg_0], rbx
0x14002ae35  push    rbp
0x14002ae36  push    rdi
0x14002ae37  push    r14
0x14002ae39  mov     rbp, rsp
0x14002ae3c  sub     rsp, 70h
0x14002ae40  mov     rdi, rdx
0x14002ae43  mov     [rbp+hDevice], 0
0x14002ae4b  mov     [rbp+BytesReturned], 0
0x14002ae52  mov     [rbp+OutBuffer], 0
0x14002ae5a  lea     r8, aCvdsserviceGet_5; "CVdsService::GetSANPolicy()"
0x14002ae61  mov     r14d, 5Eh ; '^'
0x14002ae67  mov     edx, r14d
0x14002ae6a  lea     rcx, [rbp+var_18]
0x14002ae6e  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002ae74  nop
0x14002ae75  mov     [rbp+var_28], 0
0x14002ae7d  mov     [rbp+var_20], 0
0x14002ae84  lea     rcx, [rbp+var_28]; this
0x14002ae88  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x14002ae8d  mov     ebx, eax
0x14002ae8f  test    eax, eax
0x14002ae91  js      loc_14002AFB9
0x14002ae97  mov     [rbp+OutBuffer], 0
0x14002ae9f  test    rdi, rdi
0x14002aea2  jnz     short loc_14002AEB5
0x14002aea4  mov     ebx, 80070057h
0x14002aea9  lea     r8, aCvdsserviceGet_76; "CVdsService::GetSANPolicy, 1"
0x14002aeb0  jmp     loc_14002AF92
0x14002aeb5  mov     dword ptr [rdi], 0
0x14002aebb  lea     r8, [rbp+hDevice]
0x14002aebf  mov     edx, 80000000h
0x14002aec4  lea     rcx, aPartmgrcontrol; "\\\\.\\PartmgrControl"
0x14002aecb  call    cs:__imp_OpenDevice
0x14002aed1  mov     ebx, eax
0x14002aed3  test    eax, eax
0x14002aed5  jz      short loc_14002AF04
0x14002aed7  jle     short loc_14002AEE2
0x14002aed9  movzx   ebx, ax
0x14002aedc  or      ebx, 80070000h
0x14002aee2  mov     [rbp+hDevice], 0
0x14002aeea  lea     r8, aCvdsserviceGet_77; "CVdsService::GetSANPolicy, 4, hr=%lX"
0x14002aef1  mov     r9d, ebx
0x14002aef4  xor     edx, edx
0x14002aef6  mov     ecx, r14d
0x14002aef9  call    cs:__imp_VdsTraceEx
0x14002aeff  jmp     loc_14002AF9D
0x14002af04  mov     ecx, 8
0x14002af09  mov     dword ptr [rbp+OutBuffer], ecx
0x14002af0c  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x14002af15  lea     rax, [rbp+BytesReturned]
0x14002af19  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x14002af1e  mov     [rsp+70h+nOutBufferSize], ecx; nOutBufferSize
0x14002af22  lea     rax, [rbp+OutBuffer]
0x14002af26  mov     [rsp+70h+lpOutBuffer], rax; lpOutBuffer
0x14002af2b  xor     r9d, r9d; nInBufferSize
0x14002af2e  xor     r8d, r8d; lpInBuffer
0x14002af31  mov     edx, 74200h; dwIoControlCode
0x14002af36  mov     rcx, [rbp+hDevice]; hDevice
0x14002af3a  call    cs:__imp_DeviceIoControl
0x14002af40  test    eax, eax
0x14002af42  jnz     short loc_14002AF62
0x14002af44  call    cs:__imp_GetLastError
0x14002af4a  mov     ebx, eax
0x14002af4c  test    eax, eax
0x14002af4e  jle     short loc_14002AF59
0x14002af50  movzx   ebx, ax
0x14002af53  or      ebx, 80070000h
0x14002af59  lea     r8, aCvdsserviceGet_83; "CVdsService::GetSANPolicy, 5, hr=%lX"
0x14002af60  jmp     short loc_14002AEF1
0x14002af62  xor     ebx, ebx
0x14002af64  mov     eax, dword ptr [rbp+OutBuffer+4]
0x14002af67  cmp     eax, 1
0x14002af6a  jnz     short loc_14002AF70
0x14002af6c  mov     [rdi], eax
0x14002af6e  jmp     short loc_14002AF9D
0x14002af70  cmp     eax, 2
0x14002af73  jnz     short loc_14002AF79
0x14002af75  mov     [rdi], eax
0x14002af77  jmp     short loc_14002AF9D
0x14002af79  cmp     eax, 3
0x14002af7c  jnz     short loc_14002AF82
0x14002af7e  mov     [rdi], eax
0x14002af80  jmp     short loc_14002AF9D
0x14002af82  cmp     eax, 4
0x14002af85  jnz     short loc_14002AF8B
0x14002af87  mov     [rdi], eax
0x14002af89  jmp     short loc_14002AF9D
0x14002af8b  lea     r8, aCvdsserviceGet_107; "CVdsService::GetSANPolicy, 6"
0x14002af92  xor     edx, edx
0x14002af94  mov     ecx, r14d
0x14002af97  call    cs:__imp_VdsTraceEx
0x14002af9d  mov     rcx, [rbp+hDevice]; hObject
0x14002afa1  lea     rax, [rcx-1]
0x14002afa5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002afa9  ja      short loc_14002AFB9
0x14002afab  call    cs:__imp_CloseHandle
0x14002afb1  mov     [rbp+hDevice], 0FFFFFFFFFFFFFFFFh
0x14002afb9  lea     rcx, [rbp+var_28]; this
0x14002afbd  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14002afc2  nop
0x14002afc3  lea     rcx, [rbp+var_18]
0x14002afc7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002afcd  mov     eax, ebx
0x14002afcf  mov     rbx, [rsp+70h+arg_0]
0x14002afd7  add     rsp, 70h
0x14002afdb  pop     r14
0x14002afdd  pop     rdi
0x14002afde  pop     rbp
0x14002afdf  retn
```
