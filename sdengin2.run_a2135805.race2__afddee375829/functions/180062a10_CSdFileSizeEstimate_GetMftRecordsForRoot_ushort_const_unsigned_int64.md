# CSdFileSizeEstimate::_GetMftRecordsForRoot(ushort const *,unsigned __int64 *)

- ea: `0x180062a10`
- end: `0x180062d3f`
- name: `?_GetMftRecordsForRoot@CSdFileSizeEstimate@@AEAAJPEBGPEA_K@Z`
- size: `815`
- prototype: `int(CSdFileSizeEstimate *__hidden this, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task`

## callers

- `0x180062d48`

## callees

- `0x1800119c4`
- `0x180062a10`
- `0x180072e08`
- `0x180072f14`
- `0x180073ad8`
- `0x1800935fc`
- `0x18009e904`
- `0x18009ece8`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180062b5d`
- `KERNEL32!CreateFileW` at `0x180062b5d`
- `KERNEL32!CloseHandle` at `0x180062cfb`
- `KERNEL32!CloseHandle` at `0x180062cfb`
- `KERNEL32!DeviceIoControl` at `0x180062bdb`
- `KERNEL32!DeviceIoControl` at `0x180062c92`
- `KERNEL32!DeviceIoControl` at `0x180062bdb`
- `KERNEL32!DeviceIoControl` at `0x180062c92`
- `ole32!CoTaskMemFree` at `0x180062ccc`
- `ole32!CoTaskMemFree` at `0x180062ccc`
- `ole32!CoTaskMemAlloc` at `0x180062c18`
- `ole32!CoTaskMemAlloc` at `0x180062c18`

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
    0x1CDu,
    1u);
  FileW = -1;
  OutBuffer = 0;
  memset_0(v25, 0, 0x5Cu);
  BytesReturned = 0;
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
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
0x180062a10  mov     [rsp-8+arg_0], rbx
0x180062a15  mov     [rsp-8+arg_18], rsi
0x180062a1a  push    rbp
0x180062a1b  push    rdi
0x180062a1c  push    r12
0x180062a1e  push    r14
0x180062a20  push    r15
0x180062a22  lea     rbp, [rsp-0A0h]
0x180062a2a  sub     rsp, 1A0h
0x180062a31  mov     rax, cs:__security_cookie
0x180062a38  xor     rax, rsp
0x180062a3b  mov     [rbp+0C0h+var_30], rax
0x180062a42  mov     r15, r8
0x180062a45  mov     rsi, rdx
0x180062a48  mov     r14, rcx
0x180062a4b  mov     r9d, 1; unsigned __int16
0x180062a51  mov     r8d, 1CDh; unsigned __int16
0x180062a57  lea     rdx, aCsdfilesizeest_3; "CSdFileSizeEstimate::_GetMftRecordsForR"...
0x180062a5e  lea     rcx, [rsp+1C0h+var_178]; this
0x180062a63  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180062a68  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180062a6c  xor     r12d, r12d
0x180062a6f  mov     [rbp+0C0h+OutBuffer], r12d
0x180062a73  xor     edx, edx; Val
0x180062a75  lea     r8d, [rbx+5Dh]; Size
0x180062a79  lea     rcx, [rbp+0C0h+var_8C]; void *
0x180062a7d  call    memset_0
0x180062a82  mov     [rsp+1C0h+BytesReturned], r12d
0x180062a87  lea     rax, qword_1800EE510
0x180062a8e  mov     [rbp+0C0h+lpFileName], rax
0x180062a92  mov     [rbp+0C0h+var_130], r12
0x180062a96  mov     [rbp+0C0h+InBuffer], r12
0x180062a9a  mov     edi, r12d
0x180062a9d  xor     edx, edx; Val
0x180062a9f  mov     r8d, 90h; Size
0x180062aa5  lea     rcx, [rbp+0C0h+var_120]; void *
0x180062aa9  call    memset_0
0x180062aae  xor     eax, eax
0x180062ab0  mov     [r15], rax
0x180062ab3  mov     eax, 1D8h
0x180062ab8  test    rsi, rsi
0x180062abb  jnz     short loc_180062ACF
0x180062abd  mov     [rsp+1C0h+var_178], 80070057h
0x180062ac5  mov     [rsp+1C0h+var_172], ax
0x180062aca  jmp     loc_180062CC9
0x180062acf  mov     [rsp+1C0h+var_174], ax
0x180062ad4  mov     eax, 1D9h
0x180062ad9  test    r15, r15
0x180062adc  jz      short loc_180062ABD
0x180062ade  mov     [rsp+1C0h+var_178], r12d
0x180062ae3  mov     [rsp+1C0h+var_174], ax
0x180062ae8  cmp     dword ptr [r14+80h], 6
0x180062af0  jnz     loc_180062B85
0x180062af6  lea     rdx, [rbp+0C0h+var_120]; struct _SD_STORAGE_DEVICE_PROP *
0x180062afa  mov     rcx, rsi; unsigned __int16 *
0x180062afd  call    ?QueryStorageDevice@@YAJPEBGPEAU_SD_STORAGE_DEVICE_PROP@@@Z; QueryStorageDevice(ushort const *,_SD_STORAGE_DEVICE_PROP *)
0x180062b02  mov     [rsp+1C0h+var_178], eax
0x180062b06  test    eax, eax
0x180062b08  mov     eax, 1DDh
0x180062b0d  js      short loc_180062AC5
0x180062b0f  mov     [rsp+1C0h+var_174], ax
0x180062b14  mov     rdx, [rbp+0C0h+var_118]; unsigned __int16 *
0x180062b18  lea     rcx, [rbp+0C0h+lpFileName]; this
0x180062b1c  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180062b21  mov     [rsp+1C0h+var_178], eax
0x180062b25  test    eax, eax
0x180062b27  mov     eax, 1DEh
0x180062b2c  js      short loc_180062AC5
0x180062b2e  mov     [rsp+1C0h+var_174], ax
0x180062b33  lea     rcx, [rbp+0C0h+lpFileName]; this
0x180062b37  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x180062b3c  mov     [rsp+1C0h+hTemplateFile], r12; hTemplateFile
0x180062b41  mov     [rsp+1C0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180062b46  mov     r8d, 3; dwShareMode
0x180062b4c  mov     [rsp+1C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180062b51  xor     r9d, r9d; lpSecurityAttributes
0x180062b54  mov     edx, 80000000h; dwDesiredAccess
0x180062b59  mov     rcx, [rbp+0C0h+lpFileName]; lpFileName
0x180062b5d  call    cs:__imp_CreateFileW
0x180062b64  nop     dword ptr [rax+rax+00h]
0x180062b69  mov     rbx, rax
0x180062b6c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180062b70  jnz     short loc_180062B9E
0x180062b72  call    GetLastFailureAsHRESULT
0x180062b77  mov     [rsp+1C0h+var_178], eax
0x180062b7b  mov     eax, 1ECh
0x180062b80  jmp     loc_180062AC5
0x180062b85  mov     rdx, rsi; unsigned __int16 *
0x180062b88  lea     rcx, [rbp+0C0h+lpFileName]; this
0x180062b8c  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180062b91  mov     [rsp+1C0h+var_178], eax
0x180062b95  test    eax, eax
0x180062b97  mov     eax, 1E2h
0x180062b9c  jmp     short loc_180062B2C
0x180062b9e  mov     [rsp+1C0h+var_178], r12d
0x180062ba3  mov     eax, 1ECh
0x180062ba8  mov     [rsp+1C0h+var_174], ax
0x180062bad  mov     [rsp+1C0h+lpOverlapped], r12; lpOverlapped
0x180062bb2  lea     rax, [rsp+1C0h+BytesReturned]
0x180062bb7  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x180062bbc  mov     [rsp+1C0h+dwFlagsAndAttributes], 60h ; '`'; nOutBufferSize
0x180062bc4  lea     rax, [rbp+0C0h+OutBuffer]
0x180062bc8  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rax; lpOutBuffer
0x180062bcd  xor     r9d, r9d; nInBufferSize
0x180062bd0  xor     r8d, r8d; lpInBuffer
0x180062bd3  mov     edx, 90064h; dwIoControlCode
0x180062bd8  mov     rcx, rbx; hDevice
0x180062bdb  call    cs:__imp_DeviceIoControl
0x180062be2  nop     dword ptr [rax+rax+00h]
0x180062be7  test    eax, eax
0x180062be9  jnz     short loc_180062BFE
0x180062beb  call    GetLastFailureAsHRESULT
0x180062bf0  mov     [rsp+1C0h+var_178], eax
0x180062bf4  mov     eax, 1EFh
0x180062bf9  jmp     loc_180062AC5
0x180062bfe  mov     [rsp+1C0h+var_178], r12d
0x180062c03  mov     eax, 1EFh
0x180062c08  mov     [rsp+1C0h+var_174], ax
0x180062c0d  mov     esi, [rbp+0C0h+var_60]
0x180062c10  add     esi, 10h
0x180062c13  mov     r14d, esi
0x180062c16  mov     ecx, esi; cb
0x180062c18  call    cs:__imp_CoTaskMemAlloc
0x180062c1f  nop     dword ptr [rax+rax+00h]
0x180062c24  mov     rdi, rax
0x180062c27  test    rax, rax
0x180062c2a  mov     eax, 1F5h
0x180062c2f  jnz     short loc_180062C3E
0x180062c31  mov     [rsp+1C0h+var_178], 8007000Eh
0x180062c39  jmp     loc_180062AC5
0x180062c3e  mov     [rsp+1C0h+var_178], r12d
0x180062c43  mov     [rsp+1C0h+var_174], ax
0x180062c48  mov     r8, r14; Size
0x180062c4b  xor     edx, edx; Val
0x180062c4d  mov     rcx, rdi; void *
0x180062c50  call    memset_0
0x180062c55  mov     ecx, [rbp+0C0h+var_60]
0x180062c58  mov     rax, [rbp+0C0h+var_58]
0x180062c5c  cqo
0x180062c5e  idiv    rcx
0x180062c61  dec     rax
0x180062c64  mov     [rbp+0C0h+InBuffer], rax
0x180062c68  mov     [rsp+1C0h+lpOverlapped], r12; lpOverlapped
0x180062c6d  lea     rax, [rsp+1C0h+BytesReturned]
0x180062c72  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x180062c77  mov     [rsp+1C0h+dwFlagsAndAttributes], esi; nOutBufferSize
0x180062c7b  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rdi; lpOutBuffer
0x180062c80  mov     r9d, 8; nInBufferSize
0x180062c86  lea     r8, [rbp+0C0h+InBuffer]; lpInBuffer
0x180062c8a  mov     edx, 90068h; dwIoControlCode
0x180062c8f  mov     rcx, rbx; hDevice
0x180062c92  call    cs:__imp_DeviceIoControl
0x180062c99  nop     dword ptr [rax+rax+00h]
0x180062c9e  test    eax, eax
0x180062ca0  jnz     short loc_180062CB5
0x180062ca2  call    GetLastFailureAsHRESULT
0x180062ca7  mov     [rsp+1C0h+var_178], eax
0x180062cab  mov     eax, 1FBh
0x180062cb0  jmp     loc_180062AC5
0x180062cb5  mov     [rsp+1C0h+var_178], r12d
0x180062cba  mov     eax, 1FBh
0x180062cbf  mov     [rsp+1C0h+var_174], ax
0x180062cc4  mov     eax, [rdi]
0x180062cc6  mov     [r15], rax
0x180062cc9  mov     rcx, rdi; pv
0x180062ccc  call    cs:__imp_CoTaskMemFree
0x180062cd3  nop     dword ptr [rax+rax+00h]
0x180062cd8  lea     rcx, [rbp+0C0h+var_120]; unsigned __int16 **
0x180062cdc  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x180062ce1  mov     edi, [rsp+1C0h+var_178]
0x180062ce5  lea     rcx, [rbp+0C0h+lpFileName]; this
0x180062ce9  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180062cee  lea     rcx, [rbx-1]
0x180062cf2  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180062cf6  ja      short loc_180062D07
0x180062cf8  mov     rcx, rbx; hObject
0x180062cfb  call    cs:__imp_CloseHandle
0x180062d02  nop     dword ptr [rax+rax+00h]
0x180062d07  lea     rcx, [rsp+1C0h+var_178]; this
0x180062d0c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180062d11  mov     eax, edi
0x180062d13  mov     rcx, [rbp+0C0h+var_30]
0x180062d1a  xor     rcx, rsp; StackCookie
0x180062d1d  call    __security_check_cookie
0x180062d22  lea     r11, [rsp+1C0h+var_20]
0x180062d2a  mov     rbx, [r11+30h]
0x180062d2e  mov     rsi, [r11+48h]
0x180062d32  mov     rsp, r11
0x180062d35  pop     r15
0x180062d37  pop     r14
0x180062d39  pop     r12
0x180062d3b  pop     rdi
0x180062d3c  pop     rbp
0x180062d3d  retn
```
