# SxCompressLogFile(ushort const *)

- ea: `0x14000ef3c`
- end: `0x14000f0a8`
- name: `?SxCompressLogFile@@YAJPEBG@Z`
- size: `364`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003dc4`
- `0x14000f7a0`

## callees

- `0x140002e1c`
- `0x140006cc8`
- `0x14000e324`
- `0x14000e41c`
- `0x14000ef3c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000f082`
- `KERNEL32!CloseHandle` at `0x14000f082`
- `KERNEL32!CreateFileW` at `0x14000efd3`
- `KERNEL32!CreateFileW` at `0x14000efd3`
- `KERNEL32!DeviceIoControl` at `0x14000f052`
- `KERNEL32!DeviceIoControl` at `0x14000f052`

## string_xrefs

- `0x14000ef8a`: `SxCompressLogFile`

## pseudocode

```c
__int64 __fastcall SxCompressLogFile(LPCWSTR lpFileName)
{
  HANDLE FileW; // rdi
  unsigned int LastFailureAsHRESULT; // ebx
  unsigned int v5; // [rsp+40h] [rbp-40h] BYREF
  __int16 v6; // [rsp+44h] [rbp-3Ch]
  __int16 v7; // [rsp+46h] [rbp-3Ah]
  __int16 InBuffer; // [rsp+98h] [rbp+18h] BYREF
  DWORD BytesReturned; // [rsp+A0h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v5, "SxCompressLogFile", 0xF7u, 1u);
  InBuffer = 1;
  BytesReturned = 0;
  FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v5 = 0;
    v6 = 261;
    if ( DeviceIoControl(FileW, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
    {
      LastFailureAsHRESULT = 0;
      v5 = 0;
      v6 = 270;
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v5 = LastFailureAsHRESULT;
      v7 = 270;
    }
    goto LABEL_11;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT();
  v5 = LastFailureAsHRESULT;
  v7 = 261;
  if ( FileW != (HANDLE)-1LL && FileW )
LABEL_11:
    CloseHandle(FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v5);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x14000ef3c  mov     [rsp-8+arg_0], rbx
0x14000ef41  mov     [rsp-8+arg_18], rdi
0x14000ef46  push    rbp
0x14000ef47  mov     rbp, rsp
0x14000ef4a  sub     rsp, 80h
0x14000ef51  mov     rbx, rcx
0x14000ef54  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef5b  lea     rax, WPP_GLOBAL_Control
0x14000ef62  cmp     rcx, rax
0x14000ef65  jz      short loc_14000EF85
0x14000ef67  test    dword ptr [rcx+1Ch], 20000000h
0x14000ef6e  jz      short loc_14000EF85
0x14000ef70  mov     rcx, [rcx+10h]
0x14000ef74  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x14000ef7b  mov     edx, 0Eh
0x14000ef80  call    WPP_SF_
0x14000ef85  mov     edi, 1
0x14000ef8a  lea     rdx, aSxcompresslogf; "SxCompressLogFile"
0x14000ef91  mov     r9d, edi; unsigned __int16
0x14000ef94  lea     rcx, [rbp+var_40]; this
0x14000ef98  mov     r8d, 0F7h; unsigned __int16
0x14000ef9e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000efa3  lea     r8d, [rdi+2]; dwShareMode
0x14000efa7  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x14000efb0  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000efb8  xor     r9d, r9d; lpSecurityAttributes
0x14000efbb  mov     edx, 0C0000000h; dwDesiredAccess
0x14000efc0  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x14000efc5  mov     rcx, rbx; lpFileName
0x14000efc8  mov     [rbp+InBuffer], di
0x14000efcc  mov     [rbp+BytesReturned], 0
0x14000efd3  call    cs:__imp_CreateFileW
0x14000efd9  mov     rdi, rax
0x14000efdc  lea     rcx, [rax+1]
0x14000efe0  test    rcx, 0FFFFFFFFFFFFFFFEh
0x14000efe7  jnz     short loc_14000F00D
0x14000efe9  call    GetLastFailureAsHRESULT
0x14000efee  mov     ebx, eax
0x14000eff0  mov     [rbp+var_40], eax
0x14000eff3  mov     eax, 105h
0x14000eff8  mov     [rbp+var_3A], ax
0x14000effc  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000f000  jz      loc_14000F088
0x14000f006  test    rdi, rdi
0x14000f009  jz      short loc_14000F088
0x14000f00b  jmp     short loc_14000F07F
0x14000f00d  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x14000f016  lea     r8, [rbp+InBuffer]; lpInBuffer
0x14000f01a  mov     eax, 105h
0x14000f01f  mov     [rbp+var_40], 0
0x14000f026  mov     [rbp+var_3C], ax
0x14000f02a  mov     r9d, 2; nInBufferSize
0x14000f030  lea     rax, [rbp+BytesReturned]
0x14000f034  mov     edx, 9C040h; dwIoControlCode
0x14000f039  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x14000f03e  mov     rcx, rdi; hDevice
0x14000f041  mov     [rsp+80h+dwFlagsAndAttributes], 0; nOutBufferSize
0x14000f049  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOutBuffer
0x14000f052  call    cs:__imp_DeviceIoControl
0x14000f058  test    eax, eax
0x14000f05a  jnz     short loc_14000F071
0x14000f05c  call    GetLastFailureAsHRESULT
0x14000f061  mov     ebx, eax
0x14000f063  mov     [rbp+var_40], eax
0x14000f066  mov     eax, 10Eh
0x14000f06b  mov     [rbp+var_3A], ax
0x14000f06f  jmp     short loc_14000F07F
0x14000f071  xor     ebx, ebx
0x14000f073  mov     eax, 10Eh
0x14000f078  mov     [rbp+var_40], ebx
0x14000f07b  mov     [rbp+var_3C], ax
0x14000f07f  mov     rcx, rdi; hObject
0x14000f082  call    cs:__imp_CloseHandle
0x14000f088  lea     rcx, [rbp+var_40]; this
0x14000f08c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000f091  lea     r11, [rsp+80h+var_s0]
0x14000f099  mov     eax, ebx
0x14000f09b  mov     rbx, [r11+10h]
0x14000f09f  mov     rdi, [r11+28h]
0x14000f0a3  mov     rsp, r11
0x14000f0a6  pop     rbp
0x14000f0a7  retn
```
