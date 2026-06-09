# CSdFileSizeEstimate::_GetMftRecordsForRoot(ushort const *,unsigned __int64 *)

- ea: `0x180060208`
- end: `0x180060512`
- name: `?_GetMftRecordsForRoot@CSdFileSizeEstimate@@AEAAJPEBGPEA_K@Z`
- size: `778`
- prototype: `int(CSdFileSizeEstimate *__hidden this, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task`

## callers

- `0x180060518`

## callees

- `0x180011274`
- `0x180060208`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180070ac0`
- `0x18008f5d0`
- `0x18009a24c`
- `0x18009a608`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180060355`
- `KERNEL32!CreateFileW` at `0x180060355`
- `KERNEL32!CloseHandle` at `0x1800604d5`
- `KERNEL32!CloseHandle` at `0x1800604d5`
- `KERNEL32!DeviceIoControl` at `0x1800603cd`
- `KERNEL32!DeviceIoControl` at `0x180060478`
- `KERNEL32!DeviceIoControl` at `0x1800603cd`
- `KERNEL32!DeviceIoControl` at `0x180060478`
- `ole32!CoTaskMemFree` at `0x1800604ac`
- `ole32!CoTaskMemFree` at `0x1800604ac`
- `ole32!CoTaskMemAlloc` at `0x180060404`
- `ole32!CoTaskMemAlloc` at `0x180060404`

## pseudocode

```c
__int64 __fastcall CSdFileSizeEstimate::_GetMftRecordsForRoot(
        CSdFileSizeEstimate *this,
        const unsigned __int16 *a2,
        unsigned __int64 *a3)
{
  __int64 FileW; // rbx
  unsigned int *v7; // rdi
  __int16 v8; // ax
  unsigned __int16 v9; // dx
  bool v10; // sf
  __int64 v11; // rcx
  __int64 v12; // rcx
  DWORD v13; // esi
  __int64 v14; // rcx
  unsigned int v15; // edi
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  int StorageDevice; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v19; // [rsp+4Ch] [rbp-B4h]
  __int16 v20; // [rsp+4Eh] [rbp-B2h]
  __int64 InBuffer; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v23[18]; // [rsp+A0h] [rbp-60h] BYREF
  int OutBuffer; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v25[44]; // [rsp+134h] [rbp+34h] BYREF
  unsigned int v26; // [rsp+160h] [rbp+60h]
  __int64 v27; // [rsp+168h] [rbp+68h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&StorageDevice,
    "CSdFileSizeEstimate::_GetMftRecordsForRoot",
    461,
    1);
  FileW = -1;
  OutBuffer = 0;
  memset_0(v25, 0, 0x5Cu);
  BytesReturned = 0;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  InBuffer = 0;
  v7 = 0;
  memset_0(v23, 0, sizeof(v23));
  *a3 = 0;
  v8 = 472;
  if ( !a2 || (v19 = 472, v8 = 473, !a3) )
  {
    StorageDevice = -2147024809;
    goto LABEL_3;
  }
  StorageDevice = 0;
  v19 = 473;
  if ( *((_DWORD *)this + 32) == 6 )
  {
    StorageDevice = QueryStorageDevice(a2, (struct _SD_STORAGE_DEVICE_PROP *)v23);
    v8 = 477;
    if ( StorageDevice >= 0 )
    {
      v19 = 477;
      StorageDevice = CBsString::Set((CBsString *)lpFileName, v23[1]);
      v10 = StorageDevice < 0;
      v8 = 478;
      goto LABEL_8;
    }
LABEL_3:
    v20 = v8;
    goto LABEL_19;
  }
  StorageDevice = CBsString::Set((CBsString *)lpFileName, a2);
  v10 = StorageDevice < 0;
  v8 = 482;
LABEL_8:
  if ( v10 )
    goto LABEL_3;
  v19 = v8;
  CBsString::UnTrailing((CBsString *)lpFileName, v9);
  FileW = (__int64)CreateFileW(lpFileName[0], 0x80000000, 3u, 0, 3u, 0, 0);
  if ( FileW == -1 )
  {
    StorageDevice = GetLastFailureAsHRESULT(v11);
    v8 = 492;
    goto LABEL_3;
  }
  StorageDevice = 0;
  v19 = 492;
  if ( !DeviceIoControl((HANDLE)FileW, 0x90064u, 0, 0, &OutBuffer, 0x60u, &BytesReturned, 0) )
  {
    StorageDevice = GetLastFailureAsHRESULT(v12);
    v8 = 495;
    goto LABEL_3;
  }
  StorageDevice = 0;
  v19 = 495;
  v13 = v26 + 16;
  v7 = (unsigned int *)CoTaskMemAlloc(v26 + 16);
  v8 = 501;
  if ( !v7 )
  {
    StorageDevice = -2147024882;
    goto LABEL_3;
  }
  StorageDevice = 0;
  v19 = 501;
  memset_0(v7, 0, v13);
  InBuffer = v27 / v26 - 1;
  if ( !DeviceIoControl((HANDLE)FileW, 0x90068u, &InBuffer, 8u, v7, v13, &BytesReturned, 0) )
  {
    StorageDevice = GetLastFailureAsHRESULT(v14);
    v8 = 507;
    goto LABEL_3;
  }
  StorageDevice = 0;
  v19 = 507;
  *a3 = *v7;
LABEL_19:
  CoTaskMemFree(v7);
  CleanupStorageDeviceProp(v23);
  v15 = StorageDevice;
  CBsString::_Release((CBsString *)lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&StorageDevice);
  return v15;
}

```

## disassembly

```asm
0x180060208  mov     [rsp-8+arg_0], rbx
0x18006020d  mov     [rsp-8+arg_18], rsi
0x180060212  push    rbp
0x180060213  push    rdi
0x180060214  push    r12
0x180060216  push    r14
0x180060218  push    r15
0x18006021a  lea     rbp, [rsp-0A0h]
0x180060222  sub     rsp, 1A0h
0x180060229  mov     rax, cs:__security_cookie
0x180060230  xor     rax, rsp
0x180060233  mov     [rbp+0C0h+var_30], rax
0x18006023a  mov     r15, r8
0x18006023d  mov     rsi, rdx
0x180060240  mov     r14, rcx
0x180060243  mov     r9d, 1; unsigned __int16
0x180060249  mov     r8d, 1CDh; unsigned __int16
0x18006024f  lea     rdx, aCsdfilesizeest_3; "CSdFileSizeEstimate::_GetMftRecordsForR"...
0x180060256  lea     rcx, [rsp+1C0h+var_178]; this
0x18006025b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180060260  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180060264  xor     r12d, r12d
0x180060267  mov     [rbp+0C0h+OutBuffer], r12d
0x18006026b  xor     edx, edx; Val
0x18006026d  lea     r8d, [rbx+5Dh]; Size
0x180060271  lea     rcx, [rbp+0C0h+var_8C]; void *
0x180060275  call    memset_0
0x18006027a  mov     [rsp+1C0h+BytesReturned], r12d
0x18006027f  lea     rax, qword_1800E8530
0x180060286  mov     [rbp+0C0h+lpFileName], rax
0x18006028a  mov     [rbp+0C0h+var_130], r12
0x18006028e  mov     [rbp+0C0h+InBuffer], r12
0x180060292  mov     edi, r12d
0x180060295  xor     edx, edx; Val
0x180060297  mov     r8d, 90h; Size
0x18006029d  lea     rcx, [rbp+0C0h+var_120]; void *
0x1800602a1  call    memset_0
0x1800602a6  xor     eax, eax
0x1800602a8  mov     [r15], rax
0x1800602ab  mov     eax, 1D8h
0x1800602b0  test    rsi, rsi
0x1800602b3  jnz     short loc_1800602C7
0x1800602b5  mov     [rsp+1C0h+var_178], 80070057h
0x1800602bd  mov     [rsp+1C0h+var_172], ax
0x1800602c2  jmp     loc_1800604A9
0x1800602c7  mov     [rsp+1C0h+var_174], ax
0x1800602cc  mov     eax, 1D9h
0x1800602d1  test    r15, r15
0x1800602d4  jz      short loc_1800602B5
0x1800602d6  mov     [rsp+1C0h+var_178], r12d
0x1800602db  mov     [rsp+1C0h+var_174], ax
0x1800602e0  cmp     dword ptr [r14+80h], 6
0x1800602e8  jnz     loc_180060377
0x1800602ee  lea     rdx, [rbp+0C0h+var_120]; struct _SD_STORAGE_DEVICE_PROP *
0x1800602f2  mov     rcx, rsi; unsigned __int16 *
0x1800602f5  call    ?QueryStorageDevice@@YAJPEBGPEAU_SD_STORAGE_DEVICE_PROP@@@Z; QueryStorageDevice(ushort const *,_SD_STORAGE_DEVICE_PROP *)
0x1800602fa  mov     [rsp+1C0h+var_178], eax
0x1800602fe  test    eax, eax
0x180060300  mov     eax, 1DDh
0x180060305  js      short loc_1800602BD
0x180060307  mov     [rsp+1C0h+var_174], ax
0x18006030c  mov     rdx, [rbp+0C0h+var_118]; unsigned __int16 *
0x180060310  lea     rcx, [rbp+0C0h+lpFileName]; this
0x180060314  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180060319  mov     [rsp+1C0h+var_178], eax
0x18006031d  test    eax, eax
0x18006031f  mov     eax, 1DEh
0x180060324  js      short loc_1800602BD
0x180060326  mov     [rsp+1C0h+var_174], ax
0x18006032b  lea     rcx, [rbp+0C0h+lpFileName]; this
0x18006032f  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x180060334  mov     [rsp+1C0h+hTemplateFile], r12; hTemplateFile
0x180060339  mov     [rsp+1C0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18006033e  mov     r8d, 3; dwShareMode
0x180060344  mov     [rsp+1C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180060349  xor     r9d, r9d; lpSecurityAttributes
0x18006034c  mov     edx, 80000000h; dwDesiredAccess
0x180060351  mov     rcx, [rbp+0C0h+lpFileName]; lpFileName
0x180060355  call    cs:__imp_CreateFileW
0x18006035b  mov     rbx, rax
0x18006035e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180060362  jnz     short loc_180060390
0x180060364  call    GetLastFailureAsHRESULT
0x180060369  mov     [rsp+1C0h+var_178], eax
0x18006036d  mov     eax, 1ECh
0x180060372  jmp     loc_1800602BD
0x180060377  mov     rdx, rsi; unsigned __int16 *
0x18006037a  lea     rcx, [rbp+0C0h+lpFileName]; this
0x18006037e  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180060383  mov     [rsp+1C0h+var_178], eax
0x180060387  test    eax, eax
0x180060389  mov     eax, 1E2h
0x18006038e  jmp     short loc_180060324
0x180060390  mov     [rsp+1C0h+var_178], r12d
0x180060395  mov     eax, 1ECh
0x18006039a  mov     [rsp+1C0h+var_174], ax
0x18006039f  mov     [rsp+1C0h+lpOverlapped], r12; lpOverlapped
0x1800603a4  lea     rax, [rsp+1C0h+BytesReturned]
0x1800603a9  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x1800603ae  mov     [rsp+1C0h+dwFlagsAndAttributes], 60h ; '`'; nOutBufferSize
0x1800603b6  lea     rax, [rbp+0C0h+OutBuffer]
0x1800603ba  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rax; lpOutBuffer
0x1800603bf  xor     r9d, r9d; nInBufferSize
0x1800603c2  xor     r8d, r8d; lpInBuffer
0x1800603c5  mov     edx, 90064h; dwIoControlCode
0x1800603ca  mov     rcx, rbx; hDevice
0x1800603cd  call    cs:__imp_DeviceIoControl
0x1800603d3  test    eax, eax
0x1800603d5  jnz     short loc_1800603EA
0x1800603d7  call    GetLastFailureAsHRESULT
0x1800603dc  mov     [rsp+1C0h+var_178], eax
0x1800603e0  mov     eax, 1EFh
0x1800603e5  jmp     loc_1800602BD
0x1800603ea  mov     [rsp+1C0h+var_178], r12d
0x1800603ef  mov     eax, 1EFh
0x1800603f4  mov     [rsp+1C0h+var_174], ax
0x1800603f9  mov     esi, [rbp+0C0h+var_60]
0x1800603fc  add     esi, 10h
0x1800603ff  mov     r14d, esi
0x180060402  mov     ecx, esi; cb
0x180060404  call    cs:__imp_CoTaskMemAlloc
0x18006040a  mov     rdi, rax
0x18006040d  test    rax, rax
0x180060410  mov     eax, 1F5h
0x180060415  jnz     short loc_180060424
0x180060417  mov     [rsp+1C0h+var_178], 8007000Eh
0x18006041f  jmp     loc_1800602BD
0x180060424  mov     [rsp+1C0h+var_178], r12d
0x180060429  mov     [rsp+1C0h+var_174], ax
0x18006042e  mov     r8, r14; Size
0x180060431  xor     edx, edx; Val
0x180060433  mov     rcx, rdi; void *
0x180060436  call    memset_0
0x18006043b  mov     ecx, [rbp+0C0h+var_60]
0x18006043e  mov     rax, [rbp+0C0h+var_58]
0x180060442  cqo
0x180060444  idiv    rcx
0x180060447  dec     rax
0x18006044a  mov     [rbp+0C0h+InBuffer], rax
0x18006044e  mov     [rsp+1C0h+lpOverlapped], r12; lpOverlapped
0x180060453  lea     rax, [rsp+1C0h+BytesReturned]
0x180060458  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x18006045d  mov     [rsp+1C0h+dwFlagsAndAttributes], esi; nOutBufferSize
0x180060461  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rdi; lpOutBuffer
0x180060466  mov     r9d, 8; nInBufferSize
0x18006046c  lea     r8, [rbp+0C0h+InBuffer]; lpInBuffer
0x180060470  mov     edx, 90068h; dwIoControlCode
0x180060475  mov     rcx, rbx; hDevice
0x180060478  call    cs:__imp_DeviceIoControl
0x18006047e  test    eax, eax
0x180060480  jnz     short loc_180060495
0x180060482  call    GetLastFailureAsHRESULT
0x180060487  mov     [rsp+1C0h+var_178], eax
0x18006048b  mov     eax, 1FBh
0x180060490  jmp     loc_1800602BD
0x180060495  mov     [rsp+1C0h+var_178], r12d
0x18006049a  mov     eax, 1FBh
0x18006049f  mov     [rsp+1C0h+var_174], ax
0x1800604a4  mov     eax, [rdi]
0x1800604a6  mov     [r15], rax
0x1800604a9  mov     rcx, rdi; pv
0x1800604ac  call    cs:__imp_CoTaskMemFree
0x1800604b2  lea     rcx, [rbp+0C0h+var_120]; unsigned __int16 **
0x1800604b6  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x1800604bb  mov     edi, [rsp+1C0h+var_178]
0x1800604bf  lea     rcx, [rbp+0C0h+lpFileName]; this
0x1800604c3  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800604c8  lea     rcx, [rbx-1]
0x1800604cc  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800604d0  ja      short loc_1800604DB
0x1800604d2  mov     rcx, rbx; hObject
0x1800604d5  call    cs:__imp_CloseHandle
0x1800604db  lea     rcx, [rsp+1C0h+var_178]; this
0x1800604e0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800604e5  mov     eax, edi
0x1800604e7  mov     rcx, [rbp+0C0h+var_30]
0x1800604ee  xor     rcx, rsp; StackCookie
0x1800604f1  call    __security_check_cookie
0x1800604f6  lea     r11, [rsp+1C0h+var_20]
0x1800604fe  mov     rbx, [r11+30h]
0x180060502  mov     rsi, [r11+48h]
0x180060506  mov     rsp, r11
0x180060509  pop     r15
0x18006050b  pop     r14
0x18006050d  pop     r12
0x18006050f  pop     rdi
0x180060510  pop     rbp
0x180060511  retn
```
