# CVdsService::SetSANPolicy(_VDS_SAN_POLICY)

- ea: `0x140023470`
- end: `0x140023613`
- name: `?SetSANPolicy@CVdsService@@UEAAJW4_VDS_SAN_POLICY@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, enum _VDS_SAN_POLICY)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x140003710`
- `0x140004360`
- `0x140023470`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400235dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400235dd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002358d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002358d`
- `vdsutil!OpenDevice` at `0x1400234f8`
- `vdsutil!OpenDevice` at `0x1400234f8`
- `vdsutil!VdsTraceEx` at `0x140023526`
- `vdsutil!VdsTraceEx` at `0x1400235c9`
- `vdsutil!VdsTraceEx` at `0x140023526`
- `vdsutil!VdsTraceEx` at `0x1400235c9`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400234ab`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400234ab`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400235f9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400235f9`

## string_xrefs

- `0x1400235ac`: `CVdsService::SetSANPolicy, 4, hr=%lX`
- `0x140023517`: `CVdsService::SetSANPolicy, 3, hr=%lX`
- `0x14002349b`: `CVdsService::SetSANPolicy()`
- `0x1400235bd`: `CVdsService::SetSANPolicy, 1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::SetSANPolicy(CVdsService *this, enum _VDS_SAN_POLICY a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // eax
  signed int LastError; // eax
  HANDLE hDevice; // [rsp+40h] [rbp-30h] BYREF
  __int64 v9; // [rsp+48h] [rbp-28h] BYREF
  int v10; // [rsp+50h] [rbp-20h]
  _BYTE v11[24]; // [rsp+58h] [rbp-18h] BYREF
  DWORD BytesReturned; // [rsp+90h] [rbp+20h] BYREF
  __int64 InBuffer; // [rsp+98h] [rbp+28h] BYREF

  hDevice = 0;
  BytesReturned = 0;
  InBuffer = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v11, 0x5Eu, "CVdsService::SetSANPolicy()");
  v9 = 0;
  v10 = 0;
  v3 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v9);
  if ( (v3 & 0x80000000) == 0 )
  {
    InBuffer = 0;
    if ( (unsigned int)(a2 - 1) > 3 )
    {
      v3 = -2147024809;
      VdsTraceEx(94, 0, "CVdsService::SetSANPolicy, 1");
    }
    else
    {
      v4 = OpenDevice(L"\\\\.\\PartmgrControl", 3221225472LL, &hDevice);
      v3 = v4;
      if ( v4 )
      {
        if ( v4 > 0 )
          v3 = (unsigned __int16)v4 | 0x80070000;
        hDevice = 0;
        VdsTraceEx(94, 0, "CVdsService::SetSANPolicy, 3, hr=%lX", v3);
      }
      else
      {
        v3 = 0;
        LODWORD(InBuffer) = 8;
        switch ( a2 )
        {
          case VDS_SP_ONLINE:
            HIDWORD(InBuffer) = 1;
            break;
          case VDS_SP_OFFLINE_SHARED:
            HIDWORD(InBuffer) = 2;
            break;
          case VDS_SP_OFFLINE:
            HIDWORD(InBuffer) = 3;
            break;
          default:
            v5 = HIDWORD(InBuffer);
            if ( a2 == VDS_SP_OFFLINE_INTERNAL )
              v5 = 4;
            HIDWORD(InBuffer) = v5;
            break;
        }
        if ( !DeviceIoControl(hDevice, 0x7C204u, &InBuffer, 8u, 0, 0, &BytesReturned, 0) )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          VdsTraceEx(94, 0, "CVdsService::SetSANPolicy, 4, hr=%lX", v3);
        }
      }
    }
    if ( (char *)hDevice - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hDevice);
      hDevice = (HANDLE)-1LL;
    }
  }
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v9);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
  return v3;
}

```

## disassembly

```asm
0x140023470  mov     [rsp-8+arg_0], rbx
0x140023475  mov     [rsp-8+arg_8], rdi
0x14002347a  push    rbp
0x14002347b  mov     rbp, rsp
0x14002347e  sub     rsp, 70h
0x140023482  mov     edi, edx
0x140023484  mov     [rbp+hDevice], 0
0x14002348c  mov     [rbp+BytesReturned], 0
0x140023493  mov     [rbp+InBuffer], 0
0x14002349b  lea     r8, aCvdsserviceSet_12; "CVdsService::SetSANPolicy()"
0x1400234a2  mov     edx, 5Eh ; '^'
0x1400234a7  lea     rcx, [rbp+var_18]
0x1400234ab  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400234b1  nop
0x1400234b2  mov     [rbp+var_28], 0
0x1400234ba  mov     [rbp+var_20], 0
0x1400234c1  lea     rcx, [rbp+var_28]; this
0x1400234c5  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x1400234ca  mov     ebx, eax
0x1400234cc  test    eax, eax
0x1400234ce  js      loc_1400235EB
0x1400234d4  mov     [rbp+InBuffer], 0
0x1400234dc  lea     eax, [rdi-1]
0x1400234df  cmp     eax, 3
0x1400234e2  ja      loc_1400235B8
0x1400234e8  lea     r8, [rbp+hDevice]
0x1400234ec  mov     edx, 0C0000000h
0x1400234f1  lea     rcx, aPartmgrcontrol; "\\\\.\\PartmgrControl"
0x1400234f8  call    cs:__imp_OpenDevice
0x1400234fe  mov     ebx, eax
0x140023500  test    eax, eax
0x140023502  jz      short loc_140023531
0x140023504  jle     short loc_14002350F
0x140023506  movzx   ebx, ax
0x140023509  or      ebx, 80070000h
0x14002350f  mov     [rbp+hDevice], 0
0x140023517  lea     r8, aCvdsserviceSet_1; "CVdsService::SetSANPolicy, 3, hr=%lX"
0x14002351e  mov     r9d, ebx
0x140023521  xor     edx, edx
0x140023523  lea     ecx, [rdx+5Eh]
0x140023526  call    cs:__imp_VdsTraceEx
0x14002352c  jmp     loc_1400235CF
0x140023531  xor     ebx, ebx
0x140023533  lea     r9d, [rbx+8]; nInBufferSize
0x140023537  mov     dword ptr [rbp+InBuffer], r9d
0x14002353b  cmp     edi, 1
0x14002353e  jnz     short loc_140023545
0x140023540  mov     dword ptr [rbp+InBuffer+4], edi
0x140023543  jmp     short loc_140023569
0x140023545  cmp     edi, 2
0x140023548  jnz     short loc_14002354F
0x14002354a  mov     dword ptr [rbp+InBuffer+4], edi
0x14002354d  jmp     short loc_140023569
0x14002354f  cmp     edi, 3
0x140023552  jnz     short loc_140023559
0x140023554  mov     dword ptr [rbp+InBuffer+4], edi
0x140023557  jmp     short loc_140023569
0x140023559  mov     eax, dword ptr [rbp+InBuffer+4]
0x14002355c  mov     ecx, 4
0x140023561  cmp     edi, ecx
0x140023563  cmovz   eax, ecx
0x140023566  mov     dword ptr [rbp+InBuffer+4], eax
0x140023569  mov     [rsp+70h+lpOverlapped], rbx; lpOverlapped
0x14002356e  lea     rax, [rbp+BytesReturned]
0x140023572  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x140023577  mov     [rsp+70h+nOutBufferSize], ebx; nOutBufferSize
0x14002357b  mov     [rsp+70h+lpOutBuffer], rbx; lpOutBuffer
0x140023580  lea     r8, [rbp+InBuffer]; lpInBuffer
0x140023584  mov     edx, 7C204h; dwIoControlCode
0x140023589  mov     rcx, [rbp+hDevice]; hDevice
0x14002358d  call    cs:__imp_DeviceIoControl
0x140023593  test    eax, eax
0x140023595  jnz     short loc_1400235CF
0x140023597  call    cs:__imp_GetLastError
0x14002359d  mov     ebx, eax
0x14002359f  test    eax, eax
0x1400235a1  jle     short loc_1400235AC
0x1400235a3  movzx   ebx, ax
0x1400235a6  or      ebx, 80070000h
0x1400235ac  lea     r8, aCvdsserviceSet_10; "CVdsService::SetSANPolicy, 4, hr=%lX"
0x1400235b3  jmp     loc_14002351E
0x1400235b8  mov     ebx, 80070057h
0x1400235bd  lea     r8, aCvdsserviceSet_7; "CVdsService::SetSANPolicy, 1"
0x1400235c4  xor     edx, edx
0x1400235c6  lea     ecx, [rdx+5Eh]
0x1400235c9  call    cs:__imp_VdsTraceEx
0x1400235cf  mov     rcx, [rbp+hDevice]; hObject
0x1400235d3  lea     rax, [rcx-1]
0x1400235d7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400235db  ja      short loc_1400235EB
0x1400235dd  call    cs:__imp_CloseHandle
0x1400235e3  mov     [rbp+hDevice], 0FFFFFFFFFFFFFFFFh
0x1400235eb  lea     rcx, [rbp+var_28]; this
0x1400235ef  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400235f4  nop
0x1400235f5  lea     rcx, [rbp+var_18]
0x1400235f9  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400235ff  mov     eax, ebx
0x140023601  lea     r11, [rsp+70h+var_s0]
0x140023606  mov     rbx, [r11+10h]
0x14002360a  mov     rdi, [r11+18h]
0x14002360e  mov     rsp, r11
0x140023611  pop     rbp
0x140023612  retn
```
