# CVdsService::ToggleAutoMountPoint(int)

- ea: `0x140015570`
- end: `0x14001568e`
- name: `?ToggleAutoMountPoint@CVdsService@@SAJH@Z`
- size: `286`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, service_task`

## callers

- `0x140037d80`
- `0x14003ccd0`

## callees

- `0x14000d0f0`
- `0x140015570`
- `0x140015dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400155ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400155ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015642`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400155cc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400155cc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140015638`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140015638`
- `vdsutil!VdsTraceEx` at `0x140015659`
- `vdsutil!VdsTraceEx` at `0x140015659`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140015589`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140015589`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140015680`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140015680`

## string_xrefs

- `0x1400155c5`: `\\.\MountPointManager`
- `0x140015578`: `CVdsService::ToggleAutoMountPoint()`
- `0x140015648`: `CVdsService::ToggleAutoMountPoint: IOCTL_MOUNTMGR_SET_AUTO_MOUNT failed: %X`
- `0x1400155f0`: `CVdsService::ToggleAutoMountPoint: CreateFile failed: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::ToggleAutoMountPoint(int a1)
{
  HANDLE FileW; // rax
  DWORD LastError; // eax
  const char *v4; // r8
  signed int v5; // ebx
  _BYTE v7[24]; // [rsp+40h] [rbp-18h] BYREF
  DWORD BytesReturned; // [rsp+68h] [rbp+10h] BYREF
  BOOL InBuffer; // [rsp+70h] [rbp+18h] BYREF
  HANDLE hDevice; // [rsp+78h] [rbp+20h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v7, 0x5Eu, "CVdsService::ToggleAutoMountPoint()");
  hDevice = (HANDLE)-1LL;
  BytesReturned = 0;
  FileW = CreateFileW(L"\\\\.\\MountPointManager", 0xC0000000, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  CVdsHandleImpl<-1>::operator=(&hDevice, FileW);
  if ( hDevice == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v4 = "CVdsService::ToggleAutoMountPoint: CreateFile failed: %X";
  }
  else
  {
    InBuffer = a1 == 0;
    if ( DeviceIoControl(hDevice, 0x6DC040u, &InBuffer, 4u, 0, 0, &BytesReturned, 0) )
    {
      v5 = 0;
      goto LABEL_8;
    }
    LastError = GetLastError();
    v4 = "CVdsService::ToggleAutoMountPoint: IOCTL_MOUNTMGR_SET_AUTO_MOUNT failed: %X";
  }
  v5 = LastError;
  VdsTraceEx(94, 0, v4, LastError);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_8:
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&hDevice);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140015570  push    rbx
0x140015572  sub     rsp, 50h
0x140015576  mov     ebx, ecx
0x140015578  lea     r8, aCvdsserviceTog; "CVdsService::ToggleAutoMountPoint()"
0x14001557f  mov     edx, 5Eh ; '^'
0x140015584  lea     rcx, [rsp+58h+var_18]
0x140015589  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001558f  nop
0x140015590  mov     [rsp+58h+hDevice], 0FFFFFFFFFFFFFFFFh
0x140015599  mov     [rsp+58h+BytesReturned], 0
0x1400155a1  mov     [rsp+58h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x1400155aa  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400155b2  mov     r8d, 3; dwShareMode
0x1400155b8  mov     [rsp+58h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400155bd  xor     r9d, r9d; lpSecurityAttributes
0x1400155c0  mov     edx, 0C0000000h; dwDesiredAccess
0x1400155c5  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x1400155cc  call    cs:__imp_CreateFileW
0x1400155d2  mov     rdx, rax
0x1400155d5  lea     rcx, [rsp+58h+hDevice]
0x1400155da  call    ??4?$CVdsHandleImpl@$0?0@@QEAAPEAXPEAX@Z; CVdsHandleImpl<-1>::operator=(void *)
0x1400155df  mov     rcx, [rsp+58h+hDevice]; hDevice
0x1400155e4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400155e8  jnz     short loc_1400155F9
0x1400155ea  call    cs:__imp_GetLastError
0x1400155f0  lea     r8, aCvdsserviceTog_1; "CVdsService::ToggleAutoMountPoint: Crea"...
0x1400155f7  jmp     short loc_14001564F
0x1400155f9  xor     eax, eax
0x1400155fb  test    ebx, ebx
0x1400155fd  setz    al
0x140015600  mov     [rsp+58h+InBuffer], eax
0x140015604  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x14001560d  lea     rax, [rsp+58h+BytesReturned]
0x140015612  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x140015617  mov     [rsp+58h+dwFlagsAndAttributes], 0; nOutBufferSize
0x14001561f  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOutBuffer
0x140015628  mov     r9d, 4; nInBufferSize
0x14001562e  lea     r8, [rsp+58h+InBuffer]; lpInBuffer
0x140015633  mov     edx, 6DC040h; dwIoControlCode
0x140015638  call    cs:__imp_DeviceIoControl
0x14001563e  test    eax, eax
0x140015640  jnz     short loc_14001566E
0x140015642  call    cs:__imp_GetLastError
0x140015648  lea     r8, aCvdsserviceTog_0; "CVdsService::ToggleAutoMountPoint: IOCT"...
0x14001564f  mov     r9d, eax
0x140015652  mov     ebx, eax
0x140015654  xor     edx, edx
0x140015656  lea     ecx, [rdx+5Eh]
0x140015659  call    cs:__imp_VdsTraceEx
0x14001565f  test    ebx, ebx
0x140015661  jle     short loc_140015670
0x140015663  movzx   ebx, bx
0x140015666  or      ebx, 80070000h
0x14001566c  jmp     short loc_140015670
0x14001566e  xor     ebx, ebx
0x140015670  lea     rcx, [rsp+58h+hDevice]
0x140015675  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14001567a  nop
0x14001567b  lea     rcx, [rsp+58h+var_18]
0x140015680  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140015686  mov     eax, ebx
0x140015688  add     rsp, 50h
0x14001568c  pop     rbx
0x14001568d  retn
```
