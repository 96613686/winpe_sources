# CVdsService::GetLunInformationForDisk(ushort const *,_VDS_LUN_INFORMATION *,ulong *)

- ea: `0x140025e20`
- end: `0x140026548`
- name: `?GetLunInformationForDisk@CVdsService@@SAJPEBGPEAU_VDS_LUN_INFORMATION@@PEAK@Z`
- size: `1832`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct _VDS_LUN_INFORMATION *, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140027890`
- `0x14002c7a0`
- `0x140046130`

## callees

- `0x140025e20`
- `0x14002e123`
- `0x140037dec`
- `0x140037f00`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140025f86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140026125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002631a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140025f86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140026125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002631a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025f7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002611a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002630f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026509`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025f7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002611a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002630f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400262b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002637b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400264c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400262b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002637b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400264c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400264fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400264fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140025ef2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140025ef2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140025f39`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140025fd2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140026175`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002635e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140025f39`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140025fd2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140026175`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002635e`
- `vdsutil!VdsTraceEx` at `0x140025ece`
- `vdsutil!VdsTraceEx` at `0x140026078`
- `vdsutil!VdsTraceEx` at `0x14002609b`
- `vdsutil!VdsTraceEx` at `0x1400260ee`
- `vdsutil!VdsTraceEx` at `0x140026111`
- `vdsutil!VdsTraceEx` at `0x1400261bd`
- `vdsutil!VdsTraceEx` at `0x140026208`
- `vdsutil!VdsTraceEx` at `0x14002622b`
- `vdsutil!VdsTraceEx` at `0x14002627e`
- `vdsutil!VdsTraceEx` at `0x1400262cd`
- `vdsutil!VdsTraceEx` at `0x140026303`
- `vdsutil!VdsTraceEx` at `0x1400263a1`
- `vdsutil!VdsTraceEx` at `0x1400263ed`
- `vdsutil!VdsTraceEx` at `0x14002644b`
- `vdsutil!VdsTraceEx` at `0x140026497`
- `vdsutil!VdsTraceEx` at `0x1400264e4`
- `vdsutil!VdsTraceEx` at `0x140025ece`
- `vdsutil!VdsTraceEx` at `0x140026078`
- `vdsutil!VdsTraceEx` at `0x14002609b`
- `vdsutil!VdsTraceEx` at `0x1400260ee`
- `vdsutil!VdsTraceEx` at `0x140026111`
- `vdsutil!VdsTraceEx` at `0x1400261bd`
- `vdsutil!VdsTraceEx` at `0x140026208`
- `vdsutil!VdsTraceEx` at `0x14002622b`
- `vdsutil!VdsTraceEx` at `0x14002627e`
- `vdsutil!VdsTraceEx` at `0x1400262cd`
- `vdsutil!VdsTraceEx` at `0x140026303`
- `vdsutil!VdsTraceEx` at `0x1400263a1`
- `vdsutil!VdsTraceEx` at `0x1400263ed`
- `vdsutil!VdsTraceEx` at `0x14002644b`
- `vdsutil!VdsTraceEx` at `0x140026497`
- `vdsutil!VdsTraceEx` at `0x1400264e4`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140025e92`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140025e92`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140026514`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140026514`

## string_xrefs

- `0x140026393`: `CVdsService::GetLunInformationForDisk, 12, hr=%lX`
- `0x14002648b`: `CVdsService::GetLunInformationForDisk, 4, error=%ld`
- `0x140025f5b`: `CVdsService::GetLunInformationForDisk, 2, hr=%lX`
- `0x140025e82`: `CVdsService::GetLunInformationForDisk`
- `0x140025ec0`: `CVdsService::GetLunInformationForDisk, pathname=%S`
- `0x1400264d9`: `CVdsService::GetLunInformationForDisk, 1, hr=%lX`
- `0x1400264b5`: `CVdsService::GetLunInformationForDisk, 3, hr=%lX`
- `0x140025ff9`: `CVdsService::GetLunInformationForDisk, 4.5, hr=%lX`
- `0x14002606c`: `CVdsService::GetLunInformationForDisk, 5, hr=%lX`
- `0x1400261ab`: `CVdsService::GetLunInformationForDisk, 5b, VendorIdOffset=%ld, cbQueryBuffer=%ld, propertiesOffset=%ld`
- `0x1400261fc`: `CVdsService::GetLunInformationForDisk, 6, hr=%lX`
- `0x14002608f`: `CVdsService::GetLunInformationForDisk, 6b, ProductIdOffset=%ld, cbQueryBuffer=%ld, propertiesOffset=%ld`
- `0x1400260e2`: `CVdsService::GetLunInformationForDisk, 7, hr=%lX`
- `0x14002621f`: `CVdsService::GetLunInformationForDisk, 7b, ProductRevisionOffset=%ld, cbQueryBuffer=%ld, propertiesOffset=%ld`
- `0x140026272`: `CVdsService::GetLunInformationForDisk, 8, hr=%lX`
- `0x140026105`: `CVdsService::GetLunInformationForDisk, 8b, SerialNumberOffset=%ld, cbQueryBuffer=%ld, propertiesOffset=%ld`
- `0x140026474`: `CVdsService::GetLunInformationForDisk, 9, hr=%lX`
- `0x1400262c1`: `CVdsService::GetLunInformationForDisk, 9b, error=%ld`
- `0x1400262ac`: `CVdsService::GetLunInformationForDisk, 10, hr=%lX`
- `0x1400262f4`: `CVdsService::GetLunInformationForDisk, 10b, Size=%ld, cbSize=%ld, header size=%ld, error=%ld`
- `0x14002645f`: `CVdsService::GetLunInformationForDisk, 11, hr=%lX`
- `0x14002643f`: `CVdsService::GetLunInformationForDisk, 11.5, dwSize=%lu, Buffer=%lu, Size=%lu, hr=%lX`
- `0x1400263e1`: `CVdsService::GetLunInformationForDisk, 11.7, hr=%lX, cbQueryBuffer=%ld, dwSize=%ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsService::GetLunInformationForDisk(
        LPCWSTR lpFileName,
        struct _VDS_LUN_INFORMATION *a2,
        unsigned int *a3)
{
  __int64 v6; // xmm6_8
  const wchar_t *v7; // r9
  char *FileW; // r13
  unsigned __int8 *v9; // rdi
  signed int v10; // eax
  signed int v11; // ebx
  DWORD v12; // esi
  unsigned __int8 *v13; // rax
  __int64 v14; // r9
  const char *v15; // r8
  unsigned int v16; // r9d
  int v17; // eax
  unsigned int v18; // r8d
  int v19; // eax
  unsigned __int8 *v20; // rax
  BOOL v21; // r12d
  DWORD v22; // ecx
  unsigned int v23; // r8d
  int v24; // eax
  unsigned int v25; // r8d
  int v26; // eax
  DWORD v27; // eax
  int v28; // eax
  DWORD v29; // eax
  unsigned __int8 *v30; // rax
  signed int v31; // eax
  unsigned int v32; // ecx
  unsigned int v33; // edx
  int v34; // eax
  signed int LastError; // eax
  DWORD BytesReturned; // [rsp+48h] [rbp-29h] BYREF
  int v38; // [rsp+4Ch] [rbp-25h]
  _BYTE v39[16]; // [rsp+50h] [rbp-21h] BYREF
  __int64 InBuffer; // [rsp+60h] [rbp-11h] BYREF
  int v41; // [rsp+68h] [rbp-9h]
  __int64 OutBuffer; // [rsp+70h] [rbp-1h] BYREF
  int v43; // [rsp+78h] [rbp+7h]

  BytesReturned = 0;
  OutBuffer = 0;
  v43 = 0;
  v6 = *(_QWORD *)&GUID_NULL.Data2;
  v38 = *(_DWORD *)&GUID_NULL.Data4[4];
  InBuffer = 0;
  v41 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v39, 0x5Eu, "CVdsService::GetLunInformationForDisk");
  *a3 = 999999;
  memset_0(a2, 0, sizeof(struct _VDS_LUN_INFORMATION));
  v7 = lpFileName;
  if ( !lpFileName )
    v7 = L"UNKNOWN";
  VdsTraceEx(94, 3, "CVdsService::GetLunInformationForDisk, pathname=%S", v7);
  FileW = (char *)CreateFileW(lpFileName, 0xC0000000, 1u, 0, 3u, 0, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    VdsTraceEx(94, 0, "CVdsService::GetLunInformationForDisk, 1, hr=%lX", v11);
    if ( FileW )
    {
      v9 = 0;
      if ( FileW != (char *)-1LL )
        goto LABEL_80;
    }
    goto LABEL_82;
  }
  v9 = 0;
  if ( !DeviceIoControl(FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
  {
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    VdsTraceEx(94, 0, "CVdsService::GetLunInformationForDisk, 2, hr=%lX", (unsigned int)v11);
    goto LABEL_80;
  }
  v12 = 8;
  *a3 = HIDWORD(OutBuffer);
  while ( 1 )
  {
    if ( v9 )
      CoTaskMemFree(v9);
    v13 = (unsigned __int8 *)CoTaskMemAlloc(v12);
    v9 = v13;
    if ( !v13 )
    {
      v14 = 2147942414LL;
      v11 = -2147024882;
      v15 = "CVdsService::GetLunInformationForDisk, 3, hr=%lX";
      goto LABEL_58;
    }
    memset_0(v13, 0, v12);
    InBuffer = 0;
    if ( !DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, v9, v12, &BytesReturned, 0) )
    {
      v11 = GetLastError();
      VdsTraceEx(94, 0, "CVdsService::GetLunInformationForDisk, 4, error=%ld", v11);
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      goto LABEL_80;
    }
    if ( v12 >= *((_DWORD *)v9 + 1) )
      break;
    v12 = *((_DWORD *)v9 + 1);
  }
  if ( v12 < 0x28 )
  {
    v11 = -2147024774;
    v14 = 2147942522LL;
    v15 = "CVdsService::GetLunInformationForDisk, 4.5, hr=%lX";
    goto LABEL_58;
  }
  a2->m_version = 1;
  a2->m_DeviceType = v9[8];
  a2->m_DeviceTypeModifier = v9[9];
  a2->m_bCommandQueueing = v9[11];
  a2->m_BusType = *((_DWORD *)v9 + 7);
  v16 = *((_DWORD *)v9 + 3);
  if ( v16 && v16 < v12 && v16 >= 0x24 )
  {
    v17 = CVdsService::CopyStorageDescriptorString(
            &a2->m_szVendorId,
            (const struct _STORAGE_DEVICE_DESCRIPTOR *)v9,
            v16);
    v11 = v17;
    if ( v17 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsService::GetLunInformationForDisk, 5, hr=%lX", v17);
      goto LABEL_22;
    }
  }
  else
  {
    v11 = 0;
    VdsTraceEx(
      94,
      1,
      "CVdsService::GetLunInformationForDisk, 5b, VendorIdOffset=%ld, cbQueryBuffer=%ld, propertiesOffset=%ld",
      v16,
      v12,
      36);
  }
  v23 = *((_DWORD *)v9 + 4);
  if ( !v23 || v23 >= v12 || v23 < 0x24 )
  {
LABEL_22:
    VdsTraceEx(
      94,
      0,
      "CVdsService::GetLunInformationForDisk, 6b, ProductIdOffset=%ld, cbQueryBuffer=%ld, propertiesOffset=%ld",
      *((_DWORD *)v9 + 4),
      v12,
      36);
    if ( v11 < 0 )
      goto LABEL_39;
    goto LABEL_23;
  }
  v24 = CVdsService::CopyStorageDescriptorString(&a2->m_szProductId, (const struct _STORAGE_DEVICE_DESCRIPTOR *)v9, v23);
  v11 = v24;
  if ( v24 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsService::GetLunInformationForDisk, 6, hr=%lX", v24);
    goto LABEL_39;
  }
LABEL_23:
  v18 = *((_DWORD *)v9 + 5);
  if ( v18 && v18 < v12 && v18 >= 0x24 )
  {
    v19 = CVdsService::CopyStorageDescriptorString(
            &a2->m_szProductRevision,
            (const struct _STORAGE_DEVICE_DESCRIPTOR *)v9,
            v18);
    v11 = v19;
    if ( v19 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsService::GetLunInformationForDisk, 7, hr=%lX", v19);
LABEL_28:
      VdsTraceEx(
        94,
        0,
        "CVdsService::GetLunInformationForDisk, 8b, SerialNumberOffset=%ld, cbQueryBuffer=%ld, propertiesOffset=%ld",
        *((_DWORD *)v9 + 6),
        v12,
        36);
      goto LABEL_29;
    }
    goto LABEL_40;
  }
LABEL_39:
  VdsTraceEx(
    94,
    0,
    "CVdsService::GetLunInformationForDisk, 7b, ProductRevisionOffset=%ld, cbQueryBuffer=%ld, propertiesOffset=%ld",
    *((_DWORD *)v9 + 5),
    v12,
    36);
  if ( v11 < 0 )
    goto LABEL_28;
LABEL_40:
  v25 = *((_DWORD *)v9 + 6);
  if ( !v25 || v25 >= v12 || v25 < 0x24 )
    goto LABEL_28;
  v26 = CVdsService::CopyStorageDescriptorString(
          &a2->m_szSerialNumber,
          (const struct _STORAGE_DEVICE_DESCRIPTOR *)v9,
          v25);
  v11 = v26;
  if ( v26 < 0 )
    VdsTraceEx(94, 0, "CVdsService::GetLunInformationForDisk, 8, hr=%lX", v26);
  while ( 1 )
  {
LABEL_29:
    CoTaskMemFree(v9);
    v20 = (unsigned __int8 *)CoTaskMemAlloc(v12);
    v9 = v20;
    if ( !v20 )
    {
      v14 = 2147942414LL;
      v11 = -2147024882;
      v15 = "CVdsService::GetLunInformationForDisk, 9, hr=%lX";
      goto LABEL_58;
    }
    memset_0(v20, 0, v12);
    InBuffer = 2;
    v21 = DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, v9, v12, &BytesReturned, 0);
    if ( !v21 )
    {
      v29 = GetLastError();
      VdsTraceEx(94, 0, "CVdsService::GetLunInformationForDisk, 9b, error=%ld", v29);
      v27 = BytesReturned;
LABEL_50:
      *(_QWORD *)&a2->m_deviceIdDescriptor.m_version = 0;
      VdsTraceEx(
        94,
        1,
        "CVdsService::GetLunInformationForDisk, 10b, Size=%ld, cbSize=%ld, header size=%ld, error=%ld",
        *((_DWORD *)v9 + 1),
        v27,
        16,
        v21);
      while ( 1 )
      {
LABEL_51:
        CoTaskMemFree(v9);
        v30 = (unsigned __int8 *)CoTaskMemAlloc(v12);
        v9 = v30;
        if ( !v30 )
        {
          v14 = 2147942414LL;
          v11 = -2147024882;
          v15 = "CVdsService::GetLunInformationForDisk, 11, hr=%lX";
          goto LABEL_58;
        }
        memset_0(v30, 0, v12);
        if ( DeviceIoControl(FileW, 0x70050u, 0, 0, v9, v12, &BytesReturned, 0) )
          break;
        if ( GetLastError() != 122 )
        {
          v31 = GetLastError();
          v11 = v31;
          if ( v31 > 0 )
            v11 = (unsigned __int16)v31 | 0x80070000;
          v14 = (unsigned int)v11;
          v15 = "CVdsService::GetLunInformationForDisk, 12, hr=%lX";
          goto LABEL_58;
        }
        v12 += 9216;
      }
      if ( v12 < 0x30 || BytesReturned < 0x30 )
      {
        v11 = -2147024774;
        VdsTraceEx(
          94,
          0,
          "CVdsService::GetLunInformationForDisk, 11.5, dwSize=%lu, Buffer=%lu, Size=%lu, hr=%lX",
          48,
          v12,
          BytesReturned,
          -2147024774);
        goto LABEL_80;
      }
      v32 = 144 * *((_DWORD *)v9 + 1) + 48;
      if ( v12 < v32 )
      {
        v11 = -2147024774;
        VdsTraceEx(
          94,
          0,
          "CVdsService::GetLunInformationForDisk, 11.7, hr=%lX, cbQueryBuffer=%ld, dwSize=%ld",
          -2147024774,
          v12,
          v32);
        goto LABEL_80;
      }
      v33 = 0;
      if ( *(_DWORD *)v9 )
      {
        if ( *(_DWORD *)v9 == 1 )
        {
          v33 = *((_DWORD *)v9 + 2);
          v6 = *(_QWORD *)(v9 + 12);
          v34 = *((_DWORD *)v9 + 5);
LABEL_69:
          a2->m_diskSignature.Data1 = v33;
          *(_QWORD *)&a2->m_diskSignature.Data2 = v6;
          *(_DWORD *)&a2->m_diskSignature.Data4[4] = v34;
          goto LABEL_80;
        }
      }
      else
      {
        v33 = *((_DWORD *)v9 + 2);
      }
      v34 = v38;
      goto LABEL_69;
    }
    v22 = *((_DWORD *)v9 + 1);
    if ( v12 >= v22 )
      break;
    v12 = *((_DWORD *)v9 + 1);
  }
  v27 = BytesReturned;
  if ( BytesReturned < 0x10 || BytesReturned != v22 )
    goto LABEL_50;
  v28 = CVdsService::CopyStorageDeviceIdDescriptorToLun((const struct _STORAGE_DEVICE_ID_DESCRIPTOR *)v9, a2);
  v11 = v28;
  if ( v28 >= 0 )
    goto LABEL_51;
  v14 = (unsigned int)v28;
  v15 = "CVdsService::GetLunInformationForDisk, 10, hr=%lX";
LABEL_58:
  VdsTraceEx(94, 0, v15, v14);
LABEL_80:
  CloseHandle(FileW);
  if ( v9 )
    CoTaskMemFree(v9);
LABEL_82:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v39);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140025e20  mov     rax, rsp
0x140025e23  mov     [rax+20h], rbx
0x140025e27  push    rbp
0x140025e28  push    rsi
0x140025e29  push    rdi
0x140025e2a  push    r12
0x140025e2c  push    r13
0x140025e2e  push    r14
0x140025e30  push    r15
0x140025e32  lea     rbp, [rax-5Fh]
0x140025e36  sub     rsp, 90h
0x140025e3d  movaps  xmmword ptr [rax-48h], xmm6
0x140025e41  mov     rax, cs:__security_cookie
0x140025e48  xor     rax, rsp
0x140025e4b  mov     [rbp+57h+var_48], rax
0x140025e4f  mov     r15, r8
0x140025e52  mov     r14, rdx
0x140025e55  mov     rbx, rcx
0x140025e58  xor     r12d, r12d
0x140025e5b  mov     [rbp+57h+BytesReturned], r12d
0x140025e5f  xor     eax, eax
0x140025e61  mov     [rbp+57h+OutBuffer], rax
0x140025e65  mov     [rbp+57h+var_50], eax
0x140025e68  movsd   xmm6, qword ptr cs:GUID_NULL.Data2
0x140025e70  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x140025e76  mov     [rbp+57h+var_7C], eax
0x140025e79  xor     eax, eax
0x140025e7b  mov     [rbp+57h+InBuffer], rax
0x140025e7f  mov     [rbp+57h+var_60], eax
0x140025e82  lea     r8, aCvdsserviceGet_132; "CVdsService::GetLunInformationForDisk"
0x140025e89  lea     esi, [rax+5Eh]
0x140025e8c  mov     edx, esi
0x140025e8e  lea     rcx, [rbp+57h+var_78]
0x140025e92  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140025e98  nop
0x140025e99  mov     dword ptr [r15], 0F423Fh
0x140025ea0  xor     edx, edx; Val
0x140025ea2  lea     r8d, [r12+60h]; Size
0x140025ea7  mov     rcx, r14; void *
0x140025eaa  call    memset_0
0x140025eaf  lea     rax, aUnknown_0; "UNKNOWN"
0x140025eb6  mov     r9, rbx
0x140025eb9  test    rbx, rbx
0x140025ebc  cmovz   r9, rax
0x140025ec0  lea     r8, aCvdsserviceGet_97; "CVdsService::GetLunInformationForDisk, "...
0x140025ec7  lea     edi, [rsi-5Bh]
0x140025eca  mov     edx, edi
0x140025ecc  mov     ecx, esi
0x140025ece  call    cs:__imp_VdsTraceEx
0x140025ed4  mov     [rsp+0C0h+hTemplateFile], r12; hTemplateFile
0x140025ed9  mov     [rsp+0C0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x140025ede  mov     [rsp+0C0h+dwCreationDisposition], edi; dwCreationDisposition
0x140025ee2  xor     r9d, r9d; lpSecurityAttributes
0x140025ee5  mov     edx, 0C0000000h; dwDesiredAccess
0x140025eea  lea     r8d, [r12+1]; dwShareMode
0x140025eef  mov     rcx, rbx; lpFileName
0x140025ef2  call    cs:__imp_CreateFileW
0x140025ef8  mov     r13, rax
0x140025efb  lea     rcx, [rax-1]
0x140025eff  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140025f03  ja      loc_1400264C1
0x140025f09  mov     edi, r12d
0x140025f0c  mov     [rsp+0C0h+lpOverlapped], r12; lpOverlapped
0x140025f11  lea     rax, [rbp+57h+BytesReturned]
0x140025f15  mov     [rsp+0C0h+hTemplateFile], rax; lpBytesReturned
0x140025f1a  mov     [rsp+0C0h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x140025f22  lea     rax, [rbp+57h+OutBuffer]
0x140025f26  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; lpOutBuffer
0x140025f2b  xor     r9d, r9d; nInBufferSize
0x140025f2e  xor     r8d, r8d; lpInBuffer
0x140025f31  mov     edx, 2D1080h; dwIoControlCode
0x140025f36  mov     rcx, r13; hDevice
0x140025f39  call    cs:__imp_DeviceIoControl
0x140025f3f  test    eax, eax
0x140025f41  jnz     short loc_140025F69
0x140025f43  call    cs:__imp_GetLastError
0x140025f49  mov     ebx, eax
0x140025f4b  test    eax, eax
0x140025f4d  jle     short loc_140025F58
0x140025f4f  movzx   ebx, ax
0x140025f52  or      ebx, 80070000h
0x140025f58  mov     r9d, ebx
0x140025f5b  lea     r8, aCvdsserviceGet_38; "CVdsService::GetLunInformationForDisk, "...
0x140025f62  mov     ecx, esi
0x140025f64  jmp     loc_14002639F
0x140025f69  mov     esi, 8
0x140025f6e  mov     eax, dword ptr [rbp+57h+OutBuffer+4]
0x140025f71  mov     [r15], eax
0x140025f74  test    rdi, rdi
0x140025f77  jz      short loc_140025F82
0x140025f79  mov     rcx, rdi; pv
0x140025f7c  call    cs:__imp_CoTaskMemFree
0x140025f82  mov     ebx, esi
0x140025f84  mov     ecx, esi; cb
0x140025f86  call    cs:__imp_CoTaskMemAlloc
0x140025f8c  mov     rdi, rax
0x140025f8f  test    rax, rax
0x140025f92  jz      loc_1400264AC
0x140025f98  mov     r8d, ebx; Size
0x140025f9b  xor     edx, edx; Val
0x140025f9d  mov     rcx, rax; void *
0x140025fa0  call    memset_0
0x140025fa5  mov     [rbp+57h+InBuffer], r12
0x140025fa9  mov     [rsp+0C0h+lpOverlapped], r12; lpOverlapped
0x140025fae  lea     rax, [rbp+57h+BytesReturned]
0x140025fb2  mov     [rsp+0C0h+hTemplateFile], rax; lpBytesReturned
0x140025fb7  mov     [rsp+0C0h+dwFlagsAndAttributes], esi; nOutBufferSize
0x140025fbb  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdi; lpOutBuffer
0x140025fc0  mov     r9d, 0Ch; nInBufferSize
0x140025fc6  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x140025fca  mov     edx, 2D1400h; dwIoControlCode
0x140025fcf  mov     rcx, r13; hDevice
0x140025fd2  call    cs:__imp_DeviceIoControl
0x140025fd8  test    eax, eax
0x140025fda  jz      loc_140026480
0x140025fe0  cmp     esi, [rdi+4]
0x140025fe3  jnb     short loc_140025FEA
0x140025fe5  mov     esi, [rdi+4]
0x140025fe8  jmp     short loc_140025F74
0x140025fea  cmp     esi, 28h ; '('
0x140025fed  jnb     short loc_140026005
0x140025fef  mov     eax, 8007007Ah
0x140025ff4  mov     ebx, eax
0x140025ff6  mov     r9d, eax
0x140025ff9  lea     r8, aCvdsserviceGet_46; "CVdsService::GetLunInformationForDisk, "...
0x140026000  jmp     loc_14002639A
0x140026005  mov     ecx, 1
0x14002600a  mov     [r14], ecx
0x14002600d  mov     al, [rdi+8]
0x140026010  mov     [r14+4], al
0x140026014  mov     al, [rdi+9]
0x140026017  mov     [r14+5], al
0x14002601b  movzx   eax, byte ptr [rdi+0Bh]
0x14002601f  mov     [r14+8], eax
0x140026023  mov     eax, [rdi+1Ch]
0x140026026  mov     [r14+0Ch], eax
0x14002602a  mov     r9d, [rdi+0Ch]
0x14002602e  test    r9d, r9d
0x140026031  jz      loc_14002619B
0x140026037  cmp     r9d, esi
0x14002603a  jnb     loc_14002619B
0x140026040  cmp     r9d, 24h ; '$'
0x140026044  jb      loc_14002619B
0x14002604a  lea     rcx, [r14+10h]; char **
0x14002604e  mov     r8d, r9d; unsigned int
0x140026051  mov     rdx, rdi; struct _STORAGE_DEVICE_DESCRIPTOR *
0x140026054  call    ?CopyStorageDescriptorString@CVdsService@@CAJPEAPEADPEBU_STORAGE_DEVICE_DESCRIPTOR@@K@Z; CVdsService::CopyStorageDescriptorString(char * *,_STORAGE_DEVICE_DESCRIPTOR const *,ulong)
0x140026059  mov     ebx, eax
0x14002605b  mov     r15d, 5Eh ; '^'
0x140026061  test    eax, eax
0x140026063  jns     loc_1400261C3
0x140026069  mov     r9d, eax
0x14002606c  lea     r8, aCvdsserviceGet_31; "CVdsService::GetLunInformationForDisk, "...
0x140026073  xor     edx, edx
0x140026075  mov     ecx, r15d
0x140026078  call    cs:__imp_VdsTraceEx
0x14002607e  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], 24h ; '$'
0x140026087  mov     [rsp+0C0h+dwCreationDisposition], esi
0x14002608b  mov     r9d, [rdi+10h]
0x14002608f  lea     r8, aCvdsserviceGet_54; "CVdsService::GetLunInformationForDisk, "...
0x140026096  xor     edx, edx
0x140026098  mov     ecx, r15d
0x14002609b  call    cs:__imp_VdsTraceEx
0x1400260a1  test    ebx, ebx
0x1400260a3  js      loc_14002620E
0x1400260a9  mov     r8d, [rdi+14h]; unsigned int
0x1400260ad  test    r8d, r8d
0x1400260b0  jz      loc_14002620E
0x1400260b6  cmp     r8d, esi
0x1400260b9  jnb     loc_14002620E
0x1400260bf  cmp     r8d, 24h ; '$'
0x1400260c3  jb      loc_14002620E
0x1400260c9  lea     rcx, [r14+20h]; char **
0x1400260cd  mov     rdx, rdi; struct _STORAGE_DEVICE_DESCRIPTOR *
0x1400260d0  call    ?CopyStorageDescriptorString@CVdsService@@CAJPEAPEADPEBU_STORAGE_DEVICE_DESCRIPTOR@@K@Z; CVdsService::CopyStorageDescriptorString(char * *,_STORAGE_DEVICE_DESCRIPTOR const *,ulong)
0x1400260d5  mov     ebx, eax
0x1400260d7  test    eax, eax
0x1400260d9  jns     loc_140026239
0x1400260df  mov     r9d, eax
0x1400260e2  lea     r8, aCvdsserviceGet_42; "CVdsService::GetLunInformationForDisk, "...
0x1400260e9  xor     edx, edx
0x1400260eb  mov     ecx, r15d
0x1400260ee  call    cs:__imp_VdsTraceEx
0x1400260f4  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], 24h ; '$'
0x1400260fd  mov     [rsp+0C0h+dwCreationDisposition], esi
0x140026101  mov     r9d, [rdi+18h]
0x140026105  lea     r8, aCvdsserviceGet_67; "CVdsService::GetLunInformationForDisk, "...
0x14002610c  xor     edx, edx
0x14002610e  mov     ecx, r15d
0x140026111  call    cs:__imp_VdsTraceEx
0x140026117  mov     rcx, rdi; pv
0x14002611a  call    cs:__imp_CoTaskMemFree
0x140026120  mov     r15d, esi
0x140026123  mov     ecx, esi; cb
0x140026125  call    cs:__imp_CoTaskMemAlloc
0x14002612b  mov     rdi, rax
0x14002612e  test    rax, rax
0x140026131  jz      loc_14002646B
0x140026137  mov     r8d, r15d; Size
0x14002613a  xor     edx, edx; Val
0x14002613c  mov     rcx, rax; void *
0x14002613f  call    memset_0
0x140026144  mov     [rbp+57h+InBuffer], 2
0x14002614c  mov     [rsp+0C0h+lpOverlapped], r12; lpOverlapped
0x140026151  lea     rax, [rbp+57h+BytesReturned]
0x140026155  mov     [rsp+0C0h+hTemplateFile], rax; lpBytesReturned
0x14002615a  mov     [rsp+0C0h+dwFlagsAndAttributes], esi; nOutBufferSize
0x14002615e  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdi; lpOutBuffer
0x140026163  mov     r9d, 0Ch; nInBufferSize
0x140026169  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x14002616d  mov     edx, 2D1400h; dwIoControlCode
0x140026172  mov     rcx, r13; hDevice
0x140026175  call    cs:__imp_DeviceIoControl
0x14002617b  mov     r12d, eax
0x14002617e  test    eax, eax
0x140026180  jz      loc_1400262B8
0x140026186  mov     ecx, [rdi+4]
0x140026189  cmp     esi, ecx
0x14002618b  jnb     loc_140026289
0x140026191  mov     esi, ecx
0x140026193  xor     r12d, r12d
0x140026196  jmp     loc_140026117
0x14002619b  mov     ebx, r12d
0x14002619e  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], 24h ; '$'
0x1400261a7  mov     [rsp+0C0h+dwCreationDisposition], esi
0x1400261ab  lea     r8, aCvdsserviceGet_90; "CVdsService::GetLunInformationForDisk, "...
0x1400261b2  mov     edx, ecx
0x1400261b4  mov     r15d, 5Eh ; '^'
0x1400261ba  mov     ecx, r15d
0x1400261bd  call    cs:__imp_VdsTraceEx
0x1400261c3  mov     r8d, [rdi+10h]; unsigned int
0x1400261c7  test    r8d, r8d
0x1400261ca  jz      loc_14002607E
0x1400261d0  cmp     r8d, esi
0x1400261d3  jnb     loc_14002607E
0x1400261d9  cmp     r8d, 24h ; '$'
0x1400261dd  jb      loc_14002607E
0x1400261e3  lea     rcx, [r14+18h]; char **
0x1400261e7  mov     rdx, rdi; struct _STORAGE_DEVICE_DESCRIPTOR *
0x1400261ea  call    ?CopyStorageDescriptorString@CVdsService@@CAJPEAPEADPEBU_STORAGE_DEVICE_DESCRIPTOR@@K@Z; CVdsService::CopyStorageDescriptorString(char * *,_STORAGE_DEVICE_DESCRIPTOR const *,ulong)
0x1400261ef  mov     ebx, eax
0x1400261f1  test    eax, eax
0x1400261f3  jns     loc_1400260A9
0x1400261f9  mov     r9d, eax
0x1400261fc  lea     r8, aCvdsserviceGet_57; "CVdsService::GetLunInformationForDisk, "...
0x140026203  xor     edx, edx
0x140026205  mov     ecx, r15d
0x140026208  call    cs:__imp_VdsTraceEx
0x14002620e  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], 24h ; '$'
0x140026217  mov     [rsp+0C0h+dwCreationDisposition], esi
0x14002621b  mov     r9d, [rdi+14h]
0x14002621f  lea     r8, aCvdsserviceGet_109; "CVdsService::GetLunInformationForDisk, "...
0x140026226  xor     edx, edx
0x140026228  mov     ecx, r15d
0x14002622b  call    cs:__imp_VdsTraceEx
0x140026231  test    ebx, ebx
0x140026233  js      loc_1400260F4
0x140026239  mov     r8d, [rdi+18h]; unsigned int
0x14002623d  test    r8d, r8d
0x140026240  jz      loc_1400260F4
0x140026246  cmp     r8d, esi
0x140026249  jnb     loc_1400260F4
0x14002624f  cmp     r8d, 24h ; '$'
0x140026253  jb      loc_1400260F4
0x140026259  lea     rcx, [r14+28h]; char **
0x14002625d  mov     rdx, rdi; struct _STORAGE_DEVICE_DESCRIPTOR *
0x140026260  call    ?CopyStorageDescriptorString@CVdsService@@CAJPEAPEADPEBU_STORAGE_DEVICE_DESCRIPTOR@@K@Z; CVdsService::CopyStorageDescriptorString(char * *,_STORAGE_DEVICE_DESCRIPTOR const *,ulong)
0x140026265  mov     ebx, eax
0x140026267  test    eax, eax
0x140026269  jns     loc_140026117
0x14002626f  mov     r9d, eax
0x140026272  lea     r8, aCvdsserviceGet_28; "CVdsService::GetLunInformationForDisk, "...
0x140026279  xor     edx, edx
0x14002627b  mov     ecx, r15d
0x14002627e  call    cs:__imp_VdsTraceEx
0x140026284  jmp     loc_140026117
0x140026289  mov     eax, [rbp+57h+BytesReturned]
0x14002628c  cmp     eax, 10h
0x14002628f  jb      short loc_1400262D6
0x140026291  cmp     eax, ecx
0x140026293  jnz     short loc_1400262D6
0x140026295  mov     rdx, r14; struct _VDS_LUN_INFORMATION *
0x140026298  mov     rcx, rdi; struct _STORAGE_DEVICE_ID_DESCRIPTOR *
0x14002629b  call    ?CopyStorageDeviceIdDescriptorToLun@CVdsService@@CAJPEBU_STORAGE_DEVICE_ID_DESCRIPTOR@@PEAU_VDS_LUN_INFORMATION@@@Z; CVdsService::CopyStorageDeviceIdDescriptorToLun(_STORAGE_DEVICE_ID_DESCRIPTOR const *,_VDS_LUN_INFORMATION *)
0x1400262a0  mov     ebx, eax
0x1400262a2  xor     r12d, r12d
0x1400262a5  test    eax, eax
0x1400262a7  jns     short loc_14002630C
0x1400262a9  mov     r9d, eax
0x1400262ac  lea     r8, aCvdsserviceGet_27; "CVdsService::GetLunInformationForDisk, "...
0x1400262b3  jmp     loc_14002639A
0x1400262b8  call    cs:__imp_GetLastError
0x1400262be  mov     r9d, eax
0x1400262c1  lea     r8, aCvdsserviceGet_110; "CVdsService::GetLunInformationForDisk, "...
0x1400262c8  xor     edx, edx
0x1400262ca  lea     ecx, [rdx+5Eh]
0x1400262cd  call    cs:__imp_VdsTraceEx
0x1400262d3  mov     eax, [rbp+57h+BytesReturned]
0x1400262d6  mov     qword ptr [r14+40h], 0
0x1400262de  mov     dword ptr [rsp+0C0h+hTemplateFile], r12d
  ... truncated ...
```
