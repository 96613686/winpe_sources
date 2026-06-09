# CMtPtLocal::_TryLowPrivilegeDeviceSafeRemoval(HWND__ *,bool *)

- ea: `0x18022d76c`
- end: `0x18022dced`
- name: `?_TryLowPrivilegeDeviceSafeRemoval@CMtPtLocal@@AEAAJPEAUHWND__@@PEA_N@Z`
- size: `1409`
- prototype: `__int64 __fastcall(CMtPtLocal *__hidden this, HWND, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18053d880`

## callees

- `0x18001bf10`
- `0x1800208d8`
- `0x1801a83d0`
- `0x18022d76c`
- `0x180233280`
- `0x1802342fc`
- `0x18053e0d0`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18022d960`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18022d960`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18022da89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18022dc9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18022da89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18022dc9f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18022d7f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18022da02`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18022d7f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18022da02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022da80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022da9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022daa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022dcbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022da80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022da9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022daa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022dcbb`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x18022d7c6`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x18022d7c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022dba7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022dba7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022dc1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022dc1c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18022dbfc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18022dbfc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18022d850`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18022da5b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18022d850`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18022da5b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18022dc35`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18022dc35`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18022d941`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18022d9be`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18022d941`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18022d9be`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18022d905`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18022d905`
- `DEVOBJ!DevObjGetClassDevs` at `0x18022d8b1`
- `DEVOBJ!DevObjGetClassDevs` at `0x18022d8b1`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18022d87a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18022d87a`
- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x18022dc69`
- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x18022dc69`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18022daea`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18022daea`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18022dace`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18022db66`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18022dace`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18022db66`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x18022db3e`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x18022db3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMtPtLocal::_TryLowPrivilegeDeviceSafeRemoval(CMtPtLocal *this, HWND a2, bool *a3)
{
  __int64 v4; // r10
  HANDLE FileW; // r15
  signed int Error; // ebx
  __int64 DeviceInfoList; // rsi
  unsigned int i; // r12d
  WCHAR *v9; // r14
  __int64 v10; // rdi
  CONFIGRET Device_IDW; // eax
  LSTATUS v12; // eax
  LSTATUS ValueW; // eax
  SIZE_T uBytes; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  DEVNODE pdnDevInst; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v20; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  __int64 OutBuffer; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+78h] [rbp-88h]
  __int64 v24; // [rsp+80h] [rbp-80h] BYREF
  int v25; // [rsp+88h] [rbp-78h]
  GUID pclsid; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v27[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v28; // [rsp+C0h] [rbp-40h] BYREF
  DEVINST dnDevInst[4]; // [rsp+D0h] [rbp-30h]
  __int128 v30; // [rsp+E0h] [rbp-20h]
  WCHAR FileName[8]; // [rsp+F0h] [rbp-10h] BYREF
  OLECHAR pvData[40]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR Buffer[200]; // [rsp+150h] [rbp+50h] BYREF

  *a3 = 0;
  StringCchCopyW(FileName, 7u, L"\\\\.\\A:");
  FileName[4] = (unsigned __int16)CharUpperW((LPWSTR)*(unsigned __int16 *)(v4 + 52));
  FileW = CreateFileW(FileName, 0x80u, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    Error = ResultFromKnownLastError();
  else
    Error = 0;
  OutBuffer = 0;
  v23 = 0;
  if ( Error >= 0 )
  {
    BytesReturned = 0;
    if ( DeviceIoControl(FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( (_DWORD)OutBuffer == 7 )
      {
        DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
        if ( DeviceInfoList != -1 || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_DISK, 0, 18, 0, 0) )
            Error = 0;
          else
            Error = ResultFromKnownLastError();
        }
        goto LABEL_15;
      }
      Error = -2147467259;
    }
  }
  DeviceInfoList = 0;
LABEL_15:
  for ( i = 0; ; ++i )
  {
    if ( Error < 0 )
    {
      if ( FileW != (HANDLE)-1LL )
        CloseHandle(FileW);
      return (unsigned int)Error;
    }
    v27[0] = 32;
    memset(&v27[1], 0, 28);
    if ( (unsigned int)DevObjEnumDeviceInterfaces(DeviceInfoList, 0, &GUID_DEVINTERFACE_DISK, i, v27) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
    v9 = 0;
    LODWORD(uBytes) = 0;
    if ( Error >= 0 )
    {
      if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v27, 0, 0, &uBytes, 0)
        || (unsigned int)ResultFromKnownLastError() != -2147024774 )
      {
        Error = -2147418113;
      }
      else
      {
        v9 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)uBytes);
        Error = v9 == 0 ? 0x8007000E : 0;
      }
    }
    v28 = 0;
    *(_OWORD *)dnDevInst = 0;
    v30 = 0;
    if ( Error >= 0 )
    {
      *(_DWORD *)v9 = 8;
      LODWORD(v28) = 48;
      if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v27, v9, (unsigned int)uBytes, 0, &v28) )
        Error = 0;
      else
        Error = ResultFromKnownLastError();
    }
    v10 = -1;
    if ( Error >= 0 )
    {
      v10 = (__int64)CreateFileW(v9 + 2, 0x100080u, 3u, 0, 3u, 0x80u, 0);
      if ( v10 == -1 )
        Error = ResultFromKnownLastError();
      else
        Error = 0;
    }
    v24 = 0;
    v25 = 0;
    if ( Error >= 0 )
    {
      BytesReturned = 0;
      if ( DeviceIoControl((HANDLE)v10, 0x2D1080u, 0, 0, &v24, 0xCu, &BytesReturned, 0) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_38;
      }
      if ( HIDWORD(v24) == HIDWORD(OutBuffer) )
        break;
    }
LABEL_38:
    CloseHandle((HANDLE)v10);
    LocalFree(v9);
  }
  CloseHandle(FileW);
  CloseHandle((HANDLE)v10);
  memset_0(Buffer, 0, sizeof(Buffer));
  Device_IDW = CM_Get_Device_IDW(dnDevInst[1], Buffer, 0xC8u, 0);
  pdnDevInst = 0;
  if ( Device_IDW )
    goto LABEL_41;
  Error = CM_Locate_DevNodeW(&pdnDevInst, Buffer, 0) != 0 ? 0x80004005 : 0;
  while ( Error >= 0 )
  {
    v20 = 0;
    Error = GetCapabilities(pdnDevInst, &v20);
    if ( Error >= 0 )
    {
      if ( (v20 & 4) != 0 )
      {
        Error = CM_Get_Device_IDW(pdnDevInst, Buffer, 0xC8u, 0) != 0 ? 0x80004005 : 0;
        break;
      }
      BytesReturned = 0;
      if ( CM_Get_Parent_Ex(&BytesReturned, pdnDevInst, 0, 0) || !BytesReturned )
      {
LABEL_41:
        Error = -2147467259;
      }
      else
      {
        Error = 0;
        pdnDevInst = BytesReturned;
      }
    }
  }
  phkResult = 0;
  if ( Error >= 0 )
  {
    v12 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\HotPlugProvider",
            0,
            0x20019u,
            &phkResult);
    if ( v12 )
    {
      if ( v12 > 0 )
        Error = (unsigned __int16)v12 | 0x80070000;
      else
        Error = v12;
    }
    else
    {
      BytesReturned = 78;
      ValueW = RegGetValueW(phkResult, 0, 0, 2u, 0, pvData, &BytesReturned);
      if ( ValueW )
      {
        if ( ValueW > 0 )
          Error = (unsigned __int16)ValueW | 0x80070000;
        else
          Error = ValueW;
      }
      RegCloseKey(phkResult);
    }
  }
  pclsid = 0;
  if ( Error >= 0 )
    Error = CLSIDFromString(pvData, &pclsid);
  v21 = 0;
  if ( Error >= 0 )
  {
    Error = SHExtCoCreateInstance(&pclsid, 0, 1, 2, &GUID_4d16bc13_22e4_4126_8cae_705a7a9dd787, &v21);
    if ( Error >= 0 )
    {
      *a3 = 1;
      Error = (*(__int64 (__fastcall **)(__int64, HWND, WCHAR *, __int64))(*(_QWORD *)v21 + 24LL))(v21, a2, Buffer, 5);
    }
  }
  LocalFree(v9);
  ATL::CComPtrBase<IConflictDialogDataMode>::~CComPtrBase<IConflictDialogDataMode>(&v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18022d76c  mov     [rsp-8+arg_18], rbx
0x18022d771  push    rbp
0x18022d772  push    rsi
0x18022d773  push    rdi
0x18022d774  push    r12
0x18022d776  push    r13
0x18022d778  push    r14
0x18022d77a  push    r15
0x18022d77c  lea     rbp, [rsp-1F0h]
0x18022d784  sub     rsp, 2F0h
0x18022d78b  mov     rax, cs:__security_cookie
0x18022d792  xor     rax, rsp
0x18022d795  mov     [rbp+220h+var_40], rax
0x18022d79c  mov     r13, r8
0x18022d79f  mov     [rsp+320h+var_2E0], rdx
0x18022d7a4  mov     r10, rcx
0x18022d7a7  xor     edi, edi
0x18022d7a9  mov     [r8], dil
0x18022d7ac  lea     r8, aA_0; "\\\\.\\A:"
0x18022d7b3  lea     esi, [rdi+7]
0x18022d7b6  mov     edx, esi; unsigned __int64
0x18022d7b8  lea     rcx, [rbp+220h+FileName]; unsigned __int16 *
0x18022d7bc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18022d7c1  movzx   ecx, word ptr [r10+34h]; lpsz
0x18022d7c6  call    cs:__imp_CharUpperW
0x18022d7cc  mov     [rbp+220h+var_228], ax
0x18022d7d0  mov     [rsp+320h+hTemplateFile], rdi; hTemplateFile
0x18022d7d5  lea     eax, [rsi+79h]
0x18022d7d8  mov     [rsp+320h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18022d7dc  mov     [rsp+320h+dwCreationDisposition], 3; dwCreationDisposition
0x18022d7e4  xor     r9d, r9d; lpSecurityAttributes
0x18022d7e7  mov     r8d, esi; dwShareMode
0x18022d7ea  mov     edx, eax; dwDesiredAccess
0x18022d7ec  lea     rcx, [rbp+220h+FileName]; lpFileName
0x18022d7f0  call    cs:__imp_CreateFileW
0x18022d7f6  mov     r15, rax
0x18022d7f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18022d7fd  jz      short loc_18022D803
0x18022d7ff  mov     ebx, edi
0x18022d801  jmp     short loc_18022D80A
0x18022d803  call    ResultFromKnownLastError
0x18022d808  mov     ebx, eax
0x18022d80a  xor     eax, eax
0x18022d80c  mov     [rsp+320h+OutBuffer], rax
0x18022d811  mov     [rsp+320h+var_2A8], eax
0x18022d815  test    ebx, ebx
0x18022d817  js      loc_18022D8CD
0x18022d81d  mov     [rsp+320h+BytesReturned], edi
0x18022d821  mov     [rsp+320h+lpOverlapped], rdi; lpOverlapped
0x18022d826  lea     rax, [rsp+320h+BytesReturned]
0x18022d82b  mov     [rsp+320h+hTemplateFile], rax; lpBytesReturned
0x18022d830  mov     [rsp+320h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x18022d838  lea     rax, [rsp+320h+OutBuffer]
0x18022d83d  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; lpOutBuffer
0x18022d842  xor     r9d, r9d; nInBufferSize
0x18022d845  xor     r8d, r8d; lpInBuffer
0x18022d848  mov     edx, 2D1080h; dwIoControlCode
0x18022d84d  mov     rcx, r15; hDevice
0x18022d850  call    cs:__imp_DeviceIoControl
0x18022d856  test    eax, eax
0x18022d858  jnz     short loc_18022D865
0x18022d85a  call    ResultFromKnownLastError
0x18022d85f  mov     ebx, eax
0x18022d861  test    eax, eax
0x18022d863  js      short loc_18022D8CD
0x18022d865  cmp     dword ptr [rsp+320h+OutBuffer], esi
0x18022d869  jnz     short loc_18022D8C8
0x18022d86b  mov     qword ptr [rsp+320h+dwCreationDisposition], rdi
0x18022d870  xor     r9d, r9d
0x18022d873  xor     r8d, r8d
0x18022d876  xor     edx, edx
0x18022d878  xor     ecx, ecx
0x18022d87a  call    cs:__imp_DevObjCreateDeviceInfoList
0x18022d880  mov     rsi, rax
0x18022d883  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18022d887  jnz     short loc_18022D894
0x18022d889  call    ResultFromKnownLastError
0x18022d88e  mov     ebx, eax
0x18022d890  test    eax, eax
0x18022d892  js      short loc_18022D8D0
0x18022d894  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], rdi
0x18022d899  mov     qword ptr [rsp+320h+dwCreationDisposition], rdi
0x18022d89e  mov     r9d, 12h
0x18022d8a4  xor     r8d, r8d
0x18022d8a7  lea     rdx, GUID_DEVINTERFACE_DISK
0x18022d8ae  mov     rcx, rsi
0x18022d8b1  call    cs:__imp_DevObjGetClassDevs
0x18022d8b7  test    eax, eax
0x18022d8b9  jz      short loc_18022D8BF
0x18022d8bb  mov     ebx, edi
0x18022d8bd  jmp     short loc_18022D8D0
0x18022d8bf  call    ResultFromKnownLastError
0x18022d8c4  mov     ebx, eax
0x18022d8c6  jmp     short loc_18022D8D0
0x18022d8c8  mov     ebx, 80004005h
0x18022d8cd  mov     rsi, rdi
0x18022d8d0  mov     r12d, edi
0x18022d8d3  test    ebx, ebx
0x18022d8d5  js      loc_18022DCB2
0x18022d8db  mov     [rbp+220h+var_280], 20h ; ' '
0x18022d8e2  xorps   xmm0, xmm0
0x18022d8e5  movups  xmmword ptr [rbp+220h+var_27C], xmm0
0x18022d8e9  movups  xmmword ptr [rbp+220h+var_27C+0Ch], xmm0
0x18022d8ed  lea     rax, [rbp+220h+var_280]
0x18022d8f1  mov     qword ptr [rsp+320h+dwCreationDisposition], rax
0x18022d8f6  mov     r9d, r12d
0x18022d8f9  lea     r8, GUID_DEVINTERFACE_DISK
0x18022d900  xor     edx, edx
0x18022d902  mov     rcx, rsi
0x18022d905  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18022d90b  test    eax, eax
0x18022d90d  jz      short loc_18022D913
0x18022d90f  mov     ebx, edi
0x18022d911  jmp     short loc_18022D91A
0x18022d913  call    ResultFromKnownLastError
0x18022d918  mov     ebx, eax
0x18022d91a  mov     r14, rdi
0x18022d91d  mov     dword ptr [rsp+320h+uBytes], edi
0x18022d921  test    ebx, ebx
0x18022d923  js      short loc_18022D980
0x18022d925  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], rdi
0x18022d92a  lea     rax, [rsp+320h+uBytes]
0x18022d92f  mov     qword ptr [rsp+320h+dwCreationDisposition], rax
0x18022d934  xor     r9d, r9d
0x18022d937  xor     r8d, r8d
0x18022d93a  lea     rdx, [rbp+220h+var_280]
0x18022d93e  mov     rcx, rsi
0x18022d941  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18022d947  test    eax, eax
0x18022d949  jnz     short loc_18022D97B
0x18022d94b  call    ResultFromKnownLastError
0x18022d950  cmp     eax, 8007007Ah
0x18022d955  jnz     short loc_18022D97B
0x18022d957  mov     edx, dword ptr [rsp+320h+uBytes]; uBytes
0x18022d95b  mov     ecx, 40h ; '@'; uFlags
0x18022d960  call    cs:__imp_LocalAlloc
0x18022d966  mov     r14, rax
0x18022d969  mov     rcx, rax
0x18022d96c  neg     rcx
0x18022d96f  sbb     ebx, ebx
0x18022d971  not     ebx
0x18022d973  and     ebx, 8007000Eh
0x18022d979  jmp     short loc_18022D980
0x18022d97b  mov     ebx, 8000FFFFh
0x18022d980  xorps   xmm0, xmm0
0x18022d983  movups  [rbp+220h+var_260], xmm0
0x18022d987  movups  xmmword ptr [rbp+220h+dnDevInst], xmm0
0x18022d98b  movups  [rbp+220h+var_240], xmm0
0x18022d98f  test    ebx, ebx
0x18022d991  js      short loc_18022D9D3
0x18022d993  mov     dword ptr [r14], 8
0x18022d99a  mov     dword ptr [rbp+220h+var_260], 30h ; '0'
0x18022d9a1  lea     rax, [rbp+220h+var_260]
0x18022d9a5  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], rax
0x18022d9aa  mov     qword ptr [rsp+320h+dwCreationDisposition], rdi
0x18022d9af  mov     r9d, dword ptr [rsp+320h+uBytes]
0x18022d9b4  mov     r8, r14
0x18022d9b7  lea     rdx, [rbp+220h+var_280]
0x18022d9bb  mov     rcx, rsi
0x18022d9be  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18022d9c4  test    eax, eax
0x18022d9c6  jz      short loc_18022D9CC
0x18022d9c8  mov     ebx, edi
0x18022d9ca  jmp     short loc_18022D9D3
0x18022d9cc  call    ResultFromKnownLastError
0x18022d9d1  mov     ebx, eax
0x18022d9d3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18022d9d7  test    ebx, ebx
0x18022d9d9  js      short loc_18022DA1C
0x18022d9db  lea     rcx, [r14+4]; lpFileName
0x18022d9df  mov     [rsp+320h+hTemplateFile], 0; hTemplateFile
0x18022d9e8  mov     [rsp+320h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18022d9f0  lea     eax, [rdi+4]
0x18022d9f3  mov     [rsp+320h+dwCreationDisposition], eax; dwCreationDisposition
0x18022d9f7  xor     r9d, r9d; lpSecurityAttributes
0x18022d9fa  mov     r8d, eax; dwShareMode
0x18022d9fd  mov     edx, 100080h; dwDesiredAccess
0x18022da02  call    cs:__imp_CreateFileW
0x18022da08  mov     rdi, rax
0x18022da0b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18022da0f  jz      short loc_18022DA15
0x18022da11  xor     ebx, ebx
0x18022da13  jmp     short loc_18022DA1C
0x18022da15  call    ResultFromKnownLastError
0x18022da1a  mov     ebx, eax
0x18022da1c  xor     eax, eax
0x18022da1e  mov     [rbp+220h+var_2A0], rax
0x18022da22  mov     [rbp+220h+var_298], eax
0x18022da25  test    ebx, ebx
0x18022da27  js      short loc_18022DA7D
0x18022da29  mov     [rsp+320h+BytesReturned], eax
0x18022da2d  mov     [rsp+320h+lpOverlapped], rax; lpOverlapped
0x18022da32  lea     rax, [rsp+320h+BytesReturned]
0x18022da37  mov     [rsp+320h+hTemplateFile], rax; lpBytesReturned
0x18022da3c  mov     [rsp+320h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x18022da44  lea     rax, [rbp+220h+var_2A0]
0x18022da48  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; lpOutBuffer
0x18022da4d  xor     r9d, r9d; nInBufferSize
0x18022da50  xor     r8d, r8d; lpInBuffer
0x18022da53  mov     edx, 2D1080h; dwIoControlCode
0x18022da58  mov     rcx, rdi; hDevice
0x18022da5b  call    cs:__imp_DeviceIoControl
0x18022da61  test    eax, eax
0x18022da63  jz      short loc_18022DA69
0x18022da65  xor     ebx, ebx
0x18022da67  jmp     short loc_18022DA74
0x18022da69  call    ResultFromKnownLastError
0x18022da6e  mov     ebx, eax
0x18022da70  test    eax, eax
0x18022da72  js      short loc_18022DA7D
0x18022da74  mov     eax, dword ptr [rsp+320h+OutBuffer+4]
0x18022da78  cmp     dword ptr [rbp+220h+var_2A0+4], eax
0x18022da7b  jz      short loc_18022DA99
0x18022da7d  mov     rcx, rdi; hObject
0x18022da80  call    cs:__imp_CloseHandle
0x18022da86  mov     rcx, r14; hMem
0x18022da89  call    cs:__imp_LocalFree
0x18022da8f  inc     r12d
0x18022da92  xor     edi, edi
0x18022da94  jmp     loc_18022D8D3
0x18022da99  mov     rcx, r15; hObject
0x18022da9c  call    cs:__imp_CloseHandle
0x18022daa2  mov     rcx, rdi; hObject
0x18022daa5  call    cs:__imp_CloseHandle
0x18022daab  xor     edx, edx; Val
0x18022daad  mov     r8d, 190h; Size
0x18022dab3  lea     rcx, [rbp+220h+Buffer]; void *
0x18022dab7  call    memset_0
0x18022dabc  xor     r9d, r9d; ulFlags
0x18022dabf  mov     edi, 0C8h
0x18022dac4  mov     r8d, edi; BufferLen
0x18022dac7  lea     rdx, [rbp+220h+Buffer]; Buffer
0x18022dacb  mov     ecx, [rbp+220h+dnDevInst+4]; dnDevInst
0x18022dace  call    cs:__imp_CM_Get_Device_IDW
0x18022dad4  xor     esi, esi
0x18022dad6  mov     [rsp+320h+pdnDevInst], esi
0x18022dada  test    eax, eax
0x18022dadc  jnz     short loc_18022DAFF
0x18022dade  xor     r8d, r8d; ulFlags
0x18022dae1  lea     rdx, [rbp+220h+Buffer]; pDeviceID
0x18022dae5  lea     rcx, [rsp+320h+pdnDevInst]; pdnDevInst
0x18022daea  call    cs:__imp_CM_Locate_DevNodeW
0x18022daf0  neg     eax
0x18022daf2  sbb     ebx, ebx
0x18022daf4  mov     r15d, 80004005h
0x18022dafa  and     ebx, r15d
0x18022dafd  jmp     short loc_18022DB08
0x18022daff  mov     r15d, 80004005h
0x18022db05  mov     ebx, r15d
0x18022db08  test    ebx, ebx
0x18022db0a  js      short loc_18022DB73
0x18022db0c  mov     [rsp+320h+var_2C0], esi
0x18022db10  lea     rdx, [rsp+320h+var_2C0]; unsigned int *
0x18022db15  mov     ecx, [rsp+320h+pdnDevInst]; unsigned int
0x18022db19  call    ?GetCapabilities@@YAJKPEAK@Z; GetCapabilities(ulong,ulong *)
0x18022db1e  mov     ebx, eax
0x18022db20  test    eax, eax
0x18022db22  js      short loc_18022DB08
0x18022db24  test    byte ptr [rsp+320h+var_2C0], 4
0x18022db29  jnz     short loc_18022DB58
0x18022db2b  mov     [rsp+320h+BytesReturned], esi
0x18022db2f  xor     r9d, r9d; hMachine
0x18022db32  xor     r8d, r8d; ulFlags
0x18022db35  mov     edx, [rsp+320h+pdnDevInst]; dnDevInst
0x18022db39  lea     rcx, [rsp+320h+BytesReturned]; pdnDevInst
0x18022db3e  call    cs:__imp_CM_Get_Parent_Ex
0x18022db44  test    eax, eax
0x18022db46  jnz     short loc_18022DB05
0x18022db48  mov     eax, [rsp+320h+BytesReturned]
0x18022db4c  test    eax, eax
0x18022db4e  jz      short loc_18022DB05
0x18022db50  mov     ebx, esi
0x18022db52  mov     [rsp+320h+pdnDevInst], eax
0x18022db56  jmp     short loc_18022DB08
0x18022db58  xor     r9d, r9d; ulFlags
0x18022db5b  mov     r8d, edi; BufferLen
0x18022db5e  lea     rdx, [rbp+220h+Buffer]; Buffer
0x18022db62  mov     ecx, [rsp+320h+pdnDevInst]; dnDevInst
0x18022db66  call    cs:__imp_CM_Get_Device_IDW
0x18022db6c  neg     eax
0x18022db6e  sbb     ebx, ebx
0x18022db70  and     ebx, r15d
0x18022db73  mov     [rsp+320h+phkResult], rsi
0x18022db78  mov     r12d, 2
0x18022db7e  test    ebx, ebx
0x18022db80  js      loc_18022DC22
0x18022db86  lea     rax, [rsp+320h+phkResult]
0x18022db8b  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; phkResult
0x18022db90  mov     r9d, 20019h; samDesired
0x18022db96  xor     r8d, r8d; ulOptions
0x18022db99  lea     rdx, aSoftwareMicros_185; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18022dba0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18022dba7  call    cs:__imp_RegOpenKeyExW
0x18022dbad  mov     r15d, 80070000h
0x18022dbb3  test    eax, eax
0x18022dbb5  jnz     short loc_18022DBBC
0x18022dbb7  mov     dil, 1
0x18022dbba  jmp     short loc_18022DBCF
0x18022dbbc  jg      short loc_18022DBC2
0x18022dbbe  mov     ebx, eax
  ... truncated ...
```
