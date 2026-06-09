# CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices(void)

- ea: `0x18001a680`
- end: `0x18001a962`
- name: `?enumerateAlreadyArrivedDevices@CWwanDeviceEnumerator@@AEAAKXZ`
- size: `738`
- prototype: `unsigned int __fastcall(CWwanDeviceEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007a924`

## callees

- `0x1800085d0`
- `0x180011698`
- `0x1800119bc`
- `0x180012300`
- `0x18001387c`
- `0x180016c50`
- `0x1800196fc`
- `0x180019b1c`
- `0x180019d0c`
- `0x18001a408`
- `0x18001a680`
- `0x18001b928`
- `0x1800c5d28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a91c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a91c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a6d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a6d7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a73a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a7c6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a73a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a7c6`

## string_xrefs

- `0x18001a922`: `failed to open WwanProt device handle: %u`
- `0x18001a7f7`: `CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices`
- `0x18001a837`: `CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices`
- `0x18001a879`: `CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices`
- `0x18001a8c8`: `CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices`
- `0x18001a904`: `CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices`
- `0x18001a930`: `CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices(CWwanDeviceEnumerator *this)
{
  HANDLE FileW; // rax
  HANDLE v2; // rbx
  DWORD LastError; // eax
  const unsigned __int16 *v4; // r8
  DWORD v5; // edi
  int v6; // eax
  unsigned __int16 v7; // r14
  DWORD v8; // edi
  void **v9; // rax
  unsigned int *v10; // r15
  __int64 i; // r14
  __int64 v12; // rbx
  char *v13; // rbx
  CWwanDeviceEnumerator *v14; // rcx
  const unsigned __int16 *v15; // r8
  __int64 v17; // rbx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-58h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-50h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-48h]
  DWORD BytesReturned; // [rsp+40h] [rbp-38h] BYREF
  int OutBuffer; // [rsp+44h] [rbp-34h] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-30h] BYREF
  LPVOID lpOutBuffer; // [rsp+50h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+58h] [rbp-20h] BYREF

  tlx::unique_any<tlx::file_handle_traits>::unique_any<tlx::file_handle_traits>(&hDevice);
  FileW = CreateFileW(L"\\\\.\\\\WwanProt", 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hDevice, FileW);
  v2 = hDevice;
  if ( (unsigned __int64)hDevice + 1 <= 1 )
  {
    LastError = GetLastError();
    v4 = L"failed to open WwanProt device handle: %u";
LABEL_24:
    LODWORD(v17) = LastError;
    WwanLog::Error("CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices", 0, v4, LastError);
LABEL_25:
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hDevice);
    return (unsigned int)v17;
  }
  OutBuffer = 0;
  BytesReturned = 0;
  if ( !DeviceIoControl(hDevice, 0x12C824u, 0, 0, &OutBuffer, 4u, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    v4 = L"failed to get a count of WwanProt devices: %u. ";
    goto LABEL_24;
  }
  v5 = 0;
  lpOutBuffer = 0;
  v6 = OutBuffer;
  if ( OutBuffer )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = 260 * v6;
      v9 = (void **)std::make_unique<unsigned char [0],0>((__int64)&Uuid, (unsigned int)(260 * v6));
      std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(&lpOutBuffer, v9);
      std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>((void **)&Uuid);
      v10 = (unsigned int *)lpOutBuffer;
      if ( !lpOutBuffer )
      {
        v17 = GetLastError();
        WwanLog::Error(
          "CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices",
          0,
          L"Failed to allocate Memory: %u",
          v17);
        std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&lpOutBuffer);
        goto LABEL_25;
      }
      if ( DeviceIoControl(v2, 0x12C800u, 0, 0, lpOutBuffer, v8, &BytesReturned, 0) )
        break;
      v5 = GetLastError();
      LODWORD(hTemplateFile) = *v10;
      LODWORD(dwFlagsAndAttributes) = BytesReturned;
      dwCreationDisposition[0] = v5;
      WwanLog::Error(
        "CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices",
        0,
        L"failed to enumerate WwanProt devices Iter %d: %u. DeviceIoControl() Results: dwReturnedDataSize: %d; *((PULONG)b"
         "DeviceBuffer): %d",
        v7,
        *(_QWORD *)dwCreationDisposition,
        dwFlagsAndAttributes,
        hTemplateFile);
      if ( v5 != 122 )
        goto LABEL_21;
      ++v7;
      v6 = 2 * OutBuffer;
      OutBuffer *= 2;
      if ( v7 > 3u )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        goto LABEL_12;
      }
    }
    v5 = 0;
LABEL_12:
    WwanLog::Verbose(
      "CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices",
      0,
      L"%d devices enumerated by IOCTL_WWANPROT_GET_DEVICE_LIST",
      *v10);
    for ( i = 0; (unsigned int)i < *v10; i = (unsigned int)(i + 1) )
    {
      v12 = v10[i + 1];
      if ( (unsigned int)v12 >= BytesReturned )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (unsigned int)v12 >= BytesReturned )
        {
          dwCreationDisposition[0] = BytesReturned;
          WwanLog::Error(
            "CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices",
            0,
            L"invalid dwNameOffset found in result list returned by IOCTL_WWANPROT_GET_DEVICE_LIST: current dwNameOffset: "
             "%d, dwReturnedDataSize: %d",
            (unsigned int)v12,
            *(_QWORD *)dwCreationDisposition);
          v5 = 487;
          break;
        }
      }
      v13 = (char *)v10 + v12;
      WwanLog::Verbose(
        "CWwanDeviceEnumerator::enumerateAlreadyArrivedDevices",
        0,
        L"WwanProt enumerated device %d: %ws",
        (unsigned int)i,
        v13);
      Uuid = GUID_NULL;
      v5 = CWwanDeviceEnumerator::_NdisStringToGuid(v13, &Uuid);
      if ( v5 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      else
        CWwanDeviceEnumerator::onDeviceArrival(v14, &Uuid, v15);
    }
  }
LABEL_21:
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&lpOutBuffer);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hDevice);
  return v5;
}

```

## disassembly

```asm
0x18001a680  push    rbp
0x18001a682  push    rbx
0x18001a683  push    rdi
0x18001a684  push    r13
0x18001a686  push    r14
0x18001a688  push    r15
0x18001a68a  mov     rbp, rsp
0x18001a68d  sub     rsp, 78h
0x18001a691  mov     rax, cs:__security_cookie
0x18001a698  xor     rax, rsp
0x18001a69b  mov     [rbp+var_10], rax
0x18001a69f  lea     rcx, [rbp+hDevice]
0x18001a6a3  call    ??0?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::unique_any<tlx::file_handle_traits>(void)
0x18001a6a8  nop
0x18001a6a9  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18001a6b2  mov     dword ptr [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001a6ba  mov     r13d, 3
0x18001a6c0  mov     [rsp+78h+dwCreationDisposition], r13d; dwCreationDisposition
0x18001a6c5  xor     r9d, r9d; lpSecurityAttributes
0x18001a6c8  mov     r8d, r13d; dwShareMode
0x18001a6cb  mov     edx, 0C0000000h; dwDesiredAccess
0x18001a6d0  lea     rcx, ?sc_wszWwanProtocolDriverDevice@CWwanDeviceEnumerator@@0QBGB; "\\\\.\\\\WwanProt"
0x18001a6d7  call    cs:__imp_CreateFileW
0x18001a6dd  mov     rdx, rax
0x18001a6e0  lea     rcx, [rbp+hDevice]
0x18001a6e4  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18001a6e9  mov     rbx, [rbp+hDevice]
0x18001a6ed  lea     rax, [rbx+1]
0x18001a6f1  cmp     rax, 1
0x18001a6f5  jbe     loc_18001A91C
0x18001a6fb  mov     [rbp+OutBuffer], 0
0x18001a702  mov     [rbp+BytesReturned], 0
0x18001a709  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18001a712  lea     rax, [rbp+BytesReturned]
0x18001a716  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18001a71b  mov     dword ptr [rsp+78h+dwFlagsAndAttributes], 4; nOutBufferSize
0x18001a723  lea     rax, [rbp+OutBuffer]
0x18001a727  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpOutBuffer
0x18001a72c  xor     r9d, r9d; nInBufferSize
0x18001a72f  xor     r8d, r8d; lpInBuffer
0x18001a732  mov     edx, 12C824h; dwIoControlCode
0x18001a737  mov     rcx, rbx; hDevice
0x18001a73a  call    cs:__imp_DeviceIoControl
0x18001a740  test    eax, eax
0x18001a742  jnz     short loc_18001A756
0x18001a744  call    cs:__imp_GetLastError
0x18001a74a  lea     r8, aFailedToGetACo; "failed to get a count of WwanProt devic"...
0x18001a751  jmp     loc_18001A929
0x18001a756  xor     edi, edi
0x18001a758  mov     [rbp+lpOutBuffer], rdi
0x18001a75c  mov     eax, [rbp+OutBuffer]
0x18001a75f  test    eax, eax
0x18001a761  jz      loc_18001A8D9
0x18001a767  xor     r14d, r14d
0x18001a76a  imul    edi, eax, 104h
0x18001a770  mov     edx, edi
0x18001a772  lea     rcx, [rbp+Uuid]
0x18001a776  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x18001a77b  mov     rdx, rax
0x18001a77e  lea     rcx, [rbp+lpOutBuffer]
0x18001a782  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x18001a787  lea     rcx, [rbp+Uuid]
0x18001a78b  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18001a790  mov     r15, [rbp+lpOutBuffer]
0x18001a794  test    r15, r15
0x18001a797  jz      loc_18001A8F0
0x18001a79d  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18001a7a6  lea     rax, [rbp+BytesReturned]
0x18001a7aa  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18001a7af  mov     dword ptr [rsp+78h+dwFlagsAndAttributes], edi; nOutBufferSize
0x18001a7b3  mov     qword ptr [rsp+78h+dwCreationDisposition], r15; lpOutBuffer
0x18001a7b8  xor     r9d, r9d; nInBufferSize
0x18001a7bb  xor     r8d, r8d; lpInBuffer
0x18001a7be  mov     edx, 12C800h; dwIoControlCode
0x18001a7c3  mov     rcx, rbx; hDevice
0x18001a7c6  call    cs:__imp_DeviceIoControl
0x18001a7cc  test    eax, eax
0x18001a7ce  jnz     short loc_18001A829
0x18001a7d0  call    cs:__imp_GetLastError
0x18001a7d6  mov     edi, eax
0x18001a7d8  movzx   r9d, r14w
0x18001a7dc  mov     ecx, [r15]
0x18001a7df  mov     dword ptr [rsp+78h+hTemplateFile], ecx
0x18001a7e3  mov     ecx, [rbp+BytesReturned]
0x18001a7e6  mov     dword ptr [rsp+78h+dwFlagsAndAttributes], ecx
0x18001a7ea  mov     [rsp+78h+dwCreationDisposition], eax
0x18001a7ee  lea     r8, aFailedToEnumer_1; "failed to enumerate WwanProt devices It"...
0x18001a7f5  xor     edx, edx; struct _GUID *
0x18001a7f7  lea     rcx, aCwwandeviceenu_2; "CWwanDeviceEnumerator::enumerateAlready"...
0x18001a7fe  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001a803  cmp     edi, 7Ah ; 'z'
0x18001a806  jnz     loc_18001A8D9
0x18001a80c  inc     r14w
0x18001a810  mov     eax, [rbp+OutBuffer]
0x18001a813  add     eax, eax
0x18001a815  mov     [rbp+OutBuffer], eax
0x18001a818  cmp     r14w, r13w
0x18001a81c  jbe     loc_18001A76A
0x18001a822  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001a827  jmp     short loc_18001A82B
0x18001a829  xor     edi, edi
0x18001a82b  mov     r9d, [r15]
0x18001a82e  lea     r8, aDDevicesEnumer; "%d devices enumerated by IOCTL_WWANPROT"...
0x18001a835  xor     edx, edx; struct _GUID *
0x18001a837  lea     rcx, aCwwandeviceenu_2; "CWwanDeviceEnumerator::enumerateAlready"...
0x18001a83e  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18001a843  xor     r14d, r14d
0x18001a846  cmp     r14d, [r15]
0x18001a849  jnb     loc_18001A8D9
0x18001a84f  mov     ebx, [r15+r14*4+4]
0x18001a854  cmp     ebx, [rbp+BytesReturned]
0x18001a857  jb      short loc_18001A865
0x18001a859  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001a85e  mov     eax, [rbp+BytesReturned]
0x18001a861  cmp     ebx, eax
0x18001a863  jnb     short loc_18001A8B8
0x18001a865  add     rbx, r15
0x18001a868  mov     qword ptr [rsp+78h+dwCreationDisposition], rbx
0x18001a86d  mov     r9d, r14d
0x18001a870  lea     r8, aWwanprotEnumer; "WwanProt enumerated device %d: %ws"
0x18001a877  xor     edx, edx; struct _GUID *
0x18001a879  lea     rcx, aCwwandeviceenu_2; "CWwanDeviceEnumerator::enumerateAlready"...
0x18001a880  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18001a885  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001a88c  movdqu  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18001a891  lea     rdx, [rbp+Uuid]; Uuid
0x18001a895  mov     rcx, rbx; char *
0x18001a898  call    ?_NdisStringToGuid@CWwanDeviceEnumerator@@CAKPEBGAEAU_GUID@@@Z; CWwanDeviceEnumerator::_NdisStringToGuid(ushort const *,_GUID &)
0x18001a89d  mov     edi, eax
0x18001a89f  test    eax, eax
0x18001a8a1  jz      short loc_18001A8AA
0x18001a8a3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001a8a8  jmp     short loc_18001A8B3
0x18001a8aa  lea     rdx, [rbp+Uuid]; struct _GUID *
0x18001a8ae  call    ?onDeviceArrival@CWwanDeviceEnumerator@@AEAAKAEBU_GUID@@PEBG@Z; CWwanDeviceEnumerator::onDeviceArrival(_GUID const &,ushort const *)
0x18001a8b3  inc     r14d
0x18001a8b6  jmp     short loc_18001A846
0x18001a8b8  mov     [rsp+78h+dwCreationDisposition], eax
0x18001a8bc  mov     r9d, ebx
0x18001a8bf  lea     r8, aInvalidDwnameo; "invalid dwNameOffset found in result li"...
0x18001a8c6  xor     edx, edx; struct _GUID *
0x18001a8c8  lea     rcx, aCwwandeviceenu_2; "CWwanDeviceEnumerator::enumerateAlready"...
0x18001a8cf  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001a8d4  mov     edi, 1E7h
0x18001a8d9  lea     rcx, [rbp+lpOutBuffer]
0x18001a8dd  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18001a8e2  nop
0x18001a8e3  lea     rcx, [rbp+hDevice]
0x18001a8e7  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001a8ec  mov     eax, edi
0x18001a8ee  jmp     short loc_18001A948
0x18001a8f0  call    cs:__imp_GetLastError
0x18001a8f6  mov     ebx, eax
0x18001a8f8  mov     r9d, eax
0x18001a8fb  lea     r8, aFailedToAlloca_9; "Failed to allocate Memory: %u"
0x18001a902  xor     edx, edx; struct _GUID *
0x18001a904  lea     rcx, aCwwandeviceenu_2; "CWwanDeviceEnumerator::enumerateAlready"...
0x18001a90b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001a910  nop
0x18001a911  lea     rcx, [rbp+lpOutBuffer]
0x18001a915  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18001a91a  jmp     short loc_18001A93D
0x18001a91c  call    cs:__imp_GetLastError
0x18001a922  lea     r8, aFailedToOpenWw; "failed to open WwanProt device handle: "...
0x18001a929  mov     ebx, eax
0x18001a92b  mov     r9d, eax
0x18001a92e  xor     edx, edx; struct _GUID *
0x18001a930  lea     rcx, aCwwandeviceenu_2; "CWwanDeviceEnumerator::enumerateAlready"...
0x18001a937  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001a93c  nop
0x18001a93d  lea     rcx, [rbp+hDevice]
0x18001a941  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001a946  mov     eax, ebx
0x18001a948  mov     rcx, [rbp+var_10]
0x18001a94c  xor     rcx, rsp; StackCookie
0x18001a94f  call    __security_check_cookie
0x18001a954  add     rsp, 78h
0x18001a958  pop     r15
0x18001a95a  pop     r14
0x18001a95c  pop     r13
0x18001a95e  pop     rdi
0x18001a95f  pop     rbx
0x18001a960  pop     rbp
0x18001a961  retn
```
