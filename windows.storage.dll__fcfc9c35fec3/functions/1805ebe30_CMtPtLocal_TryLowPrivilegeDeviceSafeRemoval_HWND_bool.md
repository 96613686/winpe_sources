# CMtPtLocal::_TryLowPrivilegeDeviceSafeRemoval(HWND__ *,bool *)

- ea: `0x1805ebe30`
- end: `0x1805ec435`
- name: `?_TryLowPrivilegeDeviceSafeRemoval@CMtPtLocal@@AEAAJPEAUHWND__@@PEA_N@Z`
- size: `1541`
- prototype: `__int64 __fastcall(CMtPtLocal *__hidden this, HWND, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1805eab60`

## callees

- `0x180033c60`
- `0x18004e06c`
- `0x1800ff160`
- `0x1801122d4`
- `0x180133f50`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1805eb144`
- `0x1805ebe30`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ec172`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ec19a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ec1a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ec3fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ec172`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ec19a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ec1a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ec3fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805ec346`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805ec346`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1805ec2c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1805ec2c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1805ec320`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1805ec320`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1805ec040`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1805ec040`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ec181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ec3da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ec181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ec3da`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x1805ebe8a`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x1805ebe8a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1805ebeba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1805ec0e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1805ebeba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1805ec0e8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1805ebf20`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1805ec147`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1805ebf20`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1805ec147`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1805ec365`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1805ec365`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1805ebf50`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1805ebf50`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805ec01d`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805ec0a4`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805ec01d`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805ec0a4`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1805ebfe1`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1805ebfe1`
- `DEVOBJ!DevObjGetClassDevs` at `0x1805ebf8d`
- `DEVOBJ!DevObjGetClassDevs` at `0x1805ebf8d`
- `CFGMGR32!CM_Locate_DevNodeW` at `0x1805ec1fb`
- `CFGMGR32!CM_Locate_DevNodeW` at `0x1805ec1fb`
- `CFGMGR32!CM_Get_Device_IDW` at `0x1805ec1d9`
- `CFGMGR32!CM_Get_Device_IDW` at `0x1805ec27f`
- `CFGMGR32!CM_Get_Device_IDW` at `0x1805ec1d9`
- `CFGMGR32!CM_Get_Device_IDW` at `0x1805ec27f`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x1805ec251`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x1805ec251`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMtPtLocal::_TryLowPrivilegeDeviceSafeRemoval(CMtPtLocal *this, HWND a2, bool *a3)
{
  __int64 v4; // r10
  HANDLE FileW; // r14
  signed int Error; // ebx
  __int64 DeviceInfoList; // rdi
  int ClassDevs; // eax
  unsigned int i; // r12d
  int v10; // eax
  WCHAR *v11; // r15
  int DeviceInterfaceDetail; // eax
  int v13; // eax
  __int64 v14; // rsi
  CONFIGRET Device_IDW; // eax
  LSTATUS v16; // eax
  LSTATUS ValueW; // eax
  SIZE_T uBytes; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  DEVNODE pdnDevInst; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v24; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 OutBuffer; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+78h] [rbp-88h]
  __int64 v28; // [rsp+80h] [rbp-80h] BYREF
  int v29; // [rsp+88h] [rbp-78h]
  GUID pclsid; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v31[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v32; // [rsp+C0h] [rbp-40h] BYREF
  DEVINST dnDevInst[4]; // [rsp+D0h] [rbp-30h]
  __int128 v34; // [rsp+E0h] [rbp-20h]
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
  v27 = 0;
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
          ClassDevs = DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_DISK, 0, 18, 0, 0);
          Error = ResultFromWin32Bool(ClassDevs);
        }
        goto LABEL_13;
      }
      Error = -2147467259;
    }
  }
  DeviceInfoList = 0;
LABEL_13:
  for ( i = 0; ; ++i )
  {
    if ( Error < 0 )
    {
      if ( FileW != (HANDLE)-1LL )
        CloseHandle(FileW);
      return (unsigned int)Error;
    }
    v31[0] = 32;
    memset(&v31[1], 0, 28);
    v10 = DevObjEnumDeviceInterfaces(DeviceInfoList, 0, &GUID_DEVINTERFACE_DISK, i, v31);
    Error = ResultFromWin32Bool(v10);
    v11 = 0;
    LODWORD(uBytes) = 0;
    if ( Error >= 0 )
    {
      DeviceInterfaceDetail = DevObjGetDeviceInterfaceDetail(DeviceInfoList, v31, 0, 0, &uBytes, 0);
      if ( (unsigned int)ResultFromWin32Bool(DeviceInterfaceDetail) == -2147024774 )
      {
        v11 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)uBytes);
        Error = v11 == 0 ? 0x8007000E : 0;
      }
      else
      {
        Error = -2147418113;
      }
    }
    v32 = 0;
    *(_OWORD *)dnDevInst = 0;
    v34 = 0;
    if ( Error >= 0 )
    {
      *(_DWORD *)v11 = 8;
      LODWORD(v32) = 48;
      v13 = DevObjGetDeviceInterfaceDetail(DeviceInfoList, v31, v11, (unsigned int)uBytes, 0, &v32);
      Error = ResultFromWin32Bool(v13);
    }
    v14 = -1;
    if ( Error >= 0 )
    {
      v14 = (__int64)CreateFileW(v11 + 2, 0x100080u, 3u, 0, 3u, 0x80u, 0);
      if ( v14 == -1 )
        Error = ResultFromKnownLastError();
      else
        Error = 0;
    }
    v28 = 0;
    v29 = 0;
    if ( Error >= 0 )
    {
      BytesReturned = 0;
      if ( DeviceIoControl((HANDLE)v14, 0x2D1080u, 0, 0, &v28, 0xCu, &BytesReturned, 0) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_30;
      }
      if ( HIDWORD(v28) == HIDWORD(OutBuffer) )
        break;
    }
LABEL_30:
    CloseHandle((HANDLE)v14);
    LocalFree(v11);
  }
  CloseHandle(FileW);
  CloseHandle((HANDLE)v14);
  memset_0(Buffer, 0, sizeof(Buffer));
  Device_IDW = CM_Get_Device_IDW(dnDevInst[1], Buffer, 0xC8u, 0);
  pdnDevInst = 0;
  if ( Device_IDW )
    goto LABEL_33;
  Error = CM_Locate_DevNodeW(&pdnDevInst, Buffer, 0) != 0 ? 0x80004005 : 0;
  while ( Error >= 0 )
  {
    v24 = 0;
    Error = GetCapabilities(pdnDevInst, &v24);
    if ( Error >= 0 )
    {
      if ( (v24 & 4) != 0 )
      {
        Error = CM_Get_Device_IDW(pdnDevInst, Buffer, 0xC8u, 0) != 0 ? 0x80004005 : 0;
        break;
      }
      BytesReturned = 0;
      if ( CM_Get_Parent_Ex(&BytesReturned, pdnDevInst, 0, 0) || !BytesReturned )
      {
LABEL_33:
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
    v16 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\HotPlugProvider",
            0,
            0x20019u,
            &phkResult);
    if ( v16 )
    {
      if ( v16 > 0 )
        Error = (unsigned __int16)v16 | 0x80070000;
      else
        Error = v16;
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
  v25 = 0;
  if ( Error >= 0 )
  {
    Error = _SHCoCreateInstance(&pclsid, 0, 1u, 1, 2, &GUID_4d16bc13_22e4_4126_8cae_705a7a9dd787, &v25);
    if ( Error >= 0 )
    {
      *a3 = 1;
      Error = (*(__int64 (__fastcall **)(LPVOID, HWND, WCHAR *, __int64))(*(_QWORD *)v25 + 24LL))(v25, a2, Buffer, 5);
    }
  }
  LocalFree(v11);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v25);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1805ebe30  mov     [rsp-8+arg_18], rbx
0x1805ebe35  push    rbp
0x1805ebe36  push    rsi
0x1805ebe37  push    rdi
0x1805ebe38  push    r12
0x1805ebe3a  push    r13
0x1805ebe3c  push    r14
0x1805ebe3e  push    r15
0x1805ebe40  lea     rbp, [rsp-1F0h]
0x1805ebe48  sub     rsp, 2F0h
0x1805ebe4f  mov     rax, cs:__security_cookie
0x1805ebe56  xor     rax, rsp
0x1805ebe59  mov     [rbp+220h+var_40], rax
0x1805ebe60  mov     r13, r8
0x1805ebe63  mov     [rsp+320h+var_2E0], rdx
0x1805ebe68  mov     r10, rcx
0x1805ebe6b  xor     esi, esi
0x1805ebe6d  mov     [r8], sil
0x1805ebe70  lea     r8, aA_0; "\\\\.\\A:"
0x1805ebe77  lea     edi, [rsi+7]
0x1805ebe7a  mov     edx, edi; unsigned __int64
0x1805ebe7c  lea     rcx, [rbp+220h+FileName]; unsigned __int16 *
0x1805ebe80  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805ebe85  movzx   ecx, word ptr [r10+34h]; lpsz
0x1805ebe8a  call    cs:__imp_CharUpperW
0x1805ebe91  nop     dword ptr [rax+rax+00h]
0x1805ebe96  mov     [rbp+220h+var_228], ax
0x1805ebe9a  mov     [rsp+320h+hTemplateFile], rsi; hTemplateFile
0x1805ebe9f  lea     eax, [rdi+79h]
0x1805ebea2  mov     [rsp+320h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1805ebea6  mov     [rsp+320h+dwCreationDisposition], 3; dwCreationDisposition
0x1805ebeae  xor     r9d, r9d; lpSecurityAttributes
0x1805ebeb1  mov     r8d, edi; dwShareMode
0x1805ebeb4  mov     edx, eax; dwDesiredAccess
0x1805ebeb6  lea     rcx, [rbp+220h+FileName]; lpFileName
0x1805ebeba  call    cs:__imp_CreateFileW
0x1805ebec1  nop     dword ptr [rax+rax+00h]
0x1805ebec6  mov     r14, rax
0x1805ebec9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1805ebecd  jz      short loc_1805EBED3
0x1805ebecf  mov     ebx, esi
0x1805ebed1  jmp     short loc_1805EBEDA
0x1805ebed3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1805ebed8  mov     ebx, eax
0x1805ebeda  xor     eax, eax
0x1805ebedc  mov     [rsp+320h+OutBuffer], rax
0x1805ebee1  mov     [rsp+320h+var_2A8], eax
0x1805ebee5  test    ebx, ebx
0x1805ebee7  js      loc_1805EBFA9
0x1805ebeed  mov     [rsp+320h+BytesReturned], esi
0x1805ebef1  mov     [rsp+320h+lpOverlapped], rsi; lpOverlapped
0x1805ebef6  lea     rax, [rsp+320h+BytesReturned]
0x1805ebefb  mov     [rsp+320h+hTemplateFile], rax; lpBytesReturned
0x1805ebf00  mov     [rsp+320h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x1805ebf08  lea     rax, [rsp+320h+OutBuffer]
0x1805ebf0d  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; lpOutBuffer
0x1805ebf12  xor     r9d, r9d; nInBufferSize
0x1805ebf15  xor     r8d, r8d; lpInBuffer
0x1805ebf18  mov     edx, 2D1080h; dwIoControlCode
0x1805ebf1d  mov     rcx, r14; hDevice
0x1805ebf20  call    cs:__imp_DeviceIoControl
0x1805ebf27  nop     dword ptr [rax+rax+00h]
0x1805ebf2c  test    eax, eax
0x1805ebf2e  jnz     short loc_1805EBF3B
0x1805ebf30  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1805ebf35  mov     ebx, eax
0x1805ebf37  test    eax, eax
0x1805ebf39  js      short loc_1805EBFA9
0x1805ebf3b  cmp     dword ptr [rsp+320h+OutBuffer], edi
0x1805ebf3f  jnz     short loc_1805EBFA4
0x1805ebf41  mov     qword ptr [rsp+320h+dwCreationDisposition], rsi
0x1805ebf46  xor     r9d, r9d
0x1805ebf49  xor     r8d, r8d
0x1805ebf4c  xor     edx, edx
0x1805ebf4e  xor     ecx, ecx
0x1805ebf50  call    cs:__imp_DevObjCreateDeviceInfoList
0x1805ebf57  nop     dword ptr [rax+rax+00h]
0x1805ebf5c  mov     rdi, rax
0x1805ebf5f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1805ebf63  jnz     short loc_1805EBF70
0x1805ebf65  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1805ebf6a  mov     ebx, eax
0x1805ebf6c  test    eax, eax
0x1805ebf6e  js      short loc_1805EBFAC
0x1805ebf70  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], rsi
0x1805ebf75  mov     qword ptr [rsp+320h+dwCreationDisposition], rsi
0x1805ebf7a  mov     r9d, 12h
0x1805ebf80  xor     r8d, r8d
0x1805ebf83  lea     rdx, GUID_DEVINTERFACE_DISK
0x1805ebf8a  mov     rcx, rdi
0x1805ebf8d  call    cs:__imp_DevObjGetClassDevs
0x1805ebf94  nop     dword ptr [rax+rax+00h]
0x1805ebf99  mov     ecx, eax; int
0x1805ebf9b  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1805ebfa0  mov     ebx, eax
0x1805ebfa2  jmp     short loc_1805EBFAC
0x1805ebfa4  mov     ebx, 80004005h
0x1805ebfa9  mov     rdi, rsi
0x1805ebfac  mov     r12d, esi
0x1805ebfaf  test    ebx, ebx
0x1805ebfb1  js      loc_1805EC3F3
0x1805ebfb7  mov     [rbp+220h+var_280], 20h ; ' '
0x1805ebfbe  xorps   xmm0, xmm0
0x1805ebfc1  movups  xmmword ptr [rbp+220h+var_27C], xmm0
0x1805ebfc5  movups  xmmword ptr [rbp+220h+var_27C+0Ch], xmm0
0x1805ebfc9  lea     rax, [rbp+220h+var_280]
0x1805ebfcd  mov     qword ptr [rsp+320h+dwCreationDisposition], rax
0x1805ebfd2  mov     r9d, r12d
0x1805ebfd5  lea     r8, GUID_DEVINTERFACE_DISK
0x1805ebfdc  xor     edx, edx
0x1805ebfde  mov     rcx, rdi
0x1805ebfe1  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1805ebfe8  nop     dword ptr [rax+rax+00h]
0x1805ebfed  mov     ecx, eax; int
0x1805ebfef  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1805ebff4  mov     ebx, eax
0x1805ebff6  mov     r15, rsi
0x1805ebff9  mov     dword ptr [rsp+320h+uBytes], esi
0x1805ebffd  test    eax, eax
0x1805ebfff  js      short loc_1805EC066
0x1805ec001  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], rsi
0x1805ec006  lea     rax, [rsp+320h+uBytes]
0x1805ec00b  mov     qword ptr [rsp+320h+dwCreationDisposition], rax
0x1805ec010  xor     r9d, r9d
0x1805ec013  xor     r8d, r8d
0x1805ec016  lea     rdx, [rbp+220h+var_280]
0x1805ec01a  mov     rcx, rdi
0x1805ec01d  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1805ec024  nop     dword ptr [rax+rax+00h]
0x1805ec029  mov     ecx, eax; int
0x1805ec02b  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1805ec030  cmp     eax, 8007007Ah
0x1805ec035  jnz     short loc_1805EC061
0x1805ec037  mov     edx, dword ptr [rsp+320h+uBytes]; uBytes
0x1805ec03b  mov     ecx, 40h ; '@'; uFlags
0x1805ec040  call    cs:__imp_LocalAlloc
0x1805ec047  nop     dword ptr [rax+rax+00h]
0x1805ec04c  mov     r15, rax
0x1805ec04f  mov     rcx, rax
0x1805ec052  neg     rcx
0x1805ec055  sbb     ebx, ebx
0x1805ec057  not     ebx
0x1805ec059  and     ebx, 8007000Eh
0x1805ec05f  jmp     short loc_1805EC066
0x1805ec061  mov     ebx, 8000FFFFh
0x1805ec066  xorps   xmm0, xmm0
0x1805ec069  movups  [rbp+220h+var_260], xmm0
0x1805ec06d  movups  xmmword ptr [rbp+220h+dnDevInst], xmm0
0x1805ec071  movups  [rbp+220h+var_240], xmm0
0x1805ec075  test    ebx, ebx
0x1805ec077  js      short loc_1805EC0B9
0x1805ec079  mov     dword ptr [r15], 8
0x1805ec080  mov     dword ptr [rbp+220h+var_260], 30h ; '0'
0x1805ec087  lea     rax, [rbp+220h+var_260]
0x1805ec08b  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], rax
0x1805ec090  mov     qword ptr [rsp+320h+dwCreationDisposition], rsi
0x1805ec095  mov     r9d, dword ptr [rsp+320h+uBytes]
0x1805ec09a  mov     r8, r15
0x1805ec09d  lea     rdx, [rbp+220h+var_280]
0x1805ec0a1  mov     rcx, rdi
0x1805ec0a4  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1805ec0ab  nop     dword ptr [rax+rax+00h]
0x1805ec0b0  mov     ecx, eax; int
0x1805ec0b2  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1805ec0b7  mov     ebx, eax
0x1805ec0b9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1805ec0bd  test    ebx, ebx
0x1805ec0bf  js      short loc_1805EC108
0x1805ec0c1  lea     rcx, [r15+4]; lpFileName
0x1805ec0c5  mov     [rsp+320h+hTemplateFile], 0; hTemplateFile
0x1805ec0ce  mov     [rsp+320h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1805ec0d6  lea     eax, [rsi+4]
0x1805ec0d9  mov     [rsp+320h+dwCreationDisposition], eax; dwCreationDisposition
0x1805ec0dd  xor     r9d, r9d; lpSecurityAttributes
0x1805ec0e0  mov     r8d, eax; dwShareMode
0x1805ec0e3  mov     edx, 100080h; dwDesiredAccess
0x1805ec0e8  call    cs:__imp_CreateFileW
0x1805ec0ef  nop     dword ptr [rax+rax+00h]
0x1805ec0f4  mov     rsi, rax
0x1805ec0f7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1805ec0fb  jz      short loc_1805EC101
0x1805ec0fd  xor     ebx, ebx
0x1805ec0ff  jmp     short loc_1805EC108
0x1805ec101  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1805ec106  mov     ebx, eax
0x1805ec108  xor     eax, eax
0x1805ec10a  mov     [rbp+220h+var_2A0], rax
0x1805ec10e  mov     [rbp+220h+var_298], eax
0x1805ec111  test    ebx, ebx
0x1805ec113  js      short loc_1805EC16F
0x1805ec115  mov     [rsp+320h+BytesReturned], eax
0x1805ec119  mov     [rsp+320h+lpOverlapped], rax; lpOverlapped
0x1805ec11e  lea     rax, [rsp+320h+BytesReturned]
0x1805ec123  mov     [rsp+320h+hTemplateFile], rax; lpBytesReturned
0x1805ec128  mov     [rsp+320h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x1805ec130  lea     rax, [rbp+220h+var_2A0]
0x1805ec134  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; lpOutBuffer
0x1805ec139  xor     r9d, r9d; nInBufferSize
0x1805ec13c  xor     r8d, r8d; lpInBuffer
0x1805ec13f  mov     edx, 2D1080h; dwIoControlCode
0x1805ec144  mov     rcx, rsi; hDevice
0x1805ec147  call    cs:__imp_DeviceIoControl
0x1805ec14e  nop     dword ptr [rax+rax+00h]
0x1805ec153  test    eax, eax
0x1805ec155  jz      short loc_1805EC15B
0x1805ec157  xor     ebx, ebx
0x1805ec159  jmp     short loc_1805EC166
0x1805ec15b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1805ec160  mov     ebx, eax
0x1805ec162  test    eax, eax
0x1805ec164  js      short loc_1805EC16F
0x1805ec166  mov     eax, dword ptr [rsp+320h+OutBuffer+4]
0x1805ec16a  cmp     dword ptr [rbp+220h+var_2A0+4], eax
0x1805ec16d  jz      short loc_1805EC197
0x1805ec16f  mov     rcx, rsi; hObject
0x1805ec172  call    cs:__imp_CloseHandle
0x1805ec179  nop     dword ptr [rax+rax+00h]
0x1805ec17e  mov     rcx, r15; hMem
0x1805ec181  call    cs:__imp_LocalFree
0x1805ec188  nop     dword ptr [rax+rax+00h]
0x1805ec18d  inc     r12d
0x1805ec190  xor     esi, esi
0x1805ec192  jmp     loc_1805EBFAF
0x1805ec197  mov     rcx, r14; hObject
0x1805ec19a  call    cs:__imp_CloseHandle
0x1805ec1a1  nop     dword ptr [rax+rax+00h]
0x1805ec1a6  mov     rcx, rsi; hObject
0x1805ec1a9  call    cs:__imp_CloseHandle
0x1805ec1b0  nop     dword ptr [rax+rax+00h]
0x1805ec1b5  xor     edx, edx; Val
0x1805ec1b7  mov     r8d, 190h; Size
0x1805ec1bd  lea     rcx, [rbp+220h+Buffer]; void *
0x1805ec1c1  call    memset_0
0x1805ec1c6  xor     r9d, r9d; ulFlags
0x1805ec1c9  mov     r14d, 0C8h
0x1805ec1cf  mov     r8d, r14d; BufferLen
0x1805ec1d2  lea     rdx, [rbp+220h+Buffer]; Buffer
0x1805ec1d6  mov     ecx, [rbp+220h+dnDevInst+4]; dnDevInst
0x1805ec1d9  call    cs:__imp_CM_Get_Device_IDW
0x1805ec1e0  nop     dword ptr [rax+rax+00h]
0x1805ec1e5  xor     esi, esi
0x1805ec1e7  mov     [rsp+320h+pdnDevInst], esi
0x1805ec1eb  test    eax, eax
0x1805ec1ed  jnz     short loc_1805EC214
0x1805ec1ef  xor     r8d, r8d; ulFlags
0x1805ec1f2  lea     rdx, [rbp+220h+Buffer]; pDeviceID
0x1805ec1f6  lea     rcx, [rsp+320h+pdnDevInst]; pdnDevInst
0x1805ec1fb  call    cs:__imp_CM_Locate_DevNodeW
0x1805ec202  nop     dword ptr [rax+rax+00h]
0x1805ec207  neg     eax
0x1805ec209  sbb     ebx, ebx
0x1805ec20b  mov     edi, 80004005h
0x1805ec210  and     ebx, edi
0x1805ec212  jmp     short loc_1805EC21B
0x1805ec214  mov     edi, 80004005h
0x1805ec219  mov     ebx, edi
0x1805ec21b  test    ebx, ebx
0x1805ec21d  js      short loc_1805EC291
0x1805ec21f  mov     [rsp+320h+var_2C0], esi
0x1805ec223  lea     rdx, [rsp+320h+var_2C0]; unsigned int *
0x1805ec228  mov     ecx, [rsp+320h+pdnDevInst]; unsigned int
0x1805ec22c  call    ?GetCapabilities@@YAJKPEAK@Z; GetCapabilities(ulong,ulong *)
0x1805ec231  mov     ebx, eax
0x1805ec233  test    eax, eax
0x1805ec235  js      short loc_1805EC21B
0x1805ec237  test    byte ptr [rsp+320h+var_2C0], 4
0x1805ec23c  jnz     short loc_1805EC271
0x1805ec23e  mov     [rsp+320h+BytesReturned], esi
0x1805ec242  xor     r9d, r9d; hMachine
0x1805ec245  xor     r8d, r8d; ulFlags
0x1805ec248  mov     edx, [rsp+320h+pdnDevInst]; dnDevInst
0x1805ec24c  lea     rcx, [rsp+320h+BytesReturned]; pdnDevInst
0x1805ec251  call    cs:__imp_CM_Get_Parent_Ex
0x1805ec258  nop     dword ptr [rax+rax+00h]
0x1805ec25d  test    eax, eax
0x1805ec25f  jnz     short loc_1805EC219
0x1805ec261  mov     eax, [rsp+320h+BytesReturned]
0x1805ec265  test    eax, eax
0x1805ec267  jz      short loc_1805EC219
0x1805ec269  mov     ebx, esi
0x1805ec26b  mov     [rsp+320h+pdnDevInst], eax
0x1805ec26f  jmp     short loc_1805EC21B
0x1805ec271  xor     r9d, r9d; ulFlags
0x1805ec274  mov     r8d, r14d; BufferLen
0x1805ec277  lea     rdx, [rbp+220h+Buffer]; Buffer
0x1805ec27b  mov     ecx, [rsp+320h+pdnDevInst]; dnDevInst
0x1805ec27f  call    cs:__imp_CM_Get_Device_IDW
0x1805ec286  nop     dword ptr [rax+rax+00h]
0x1805ec28b  neg     eax
0x1805ec28d  sbb     ebx, ebx
0x1805ec28f  and     ebx, edi
0x1805ec291  mov     [rsp+320h+phkResult], rsi
0x1805ec296  mov     r12d, 2
0x1805ec29c  test    ebx, ebx
0x1805ec29e  js      loc_1805EC352
0x1805ec2a4  lea     rax, [rsp+320h+phkResult]
0x1805ec2a9  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; phkResult
0x1805ec2ae  mov     r9d, 20019h; samDesired
0x1805ec2b4  xor     r8d, r8d; ulOptions
0x1805ec2b7  lea     rdx, aSoftwareMicros_128; "Software\\Microsoft\\Windows\\CurrentVe"...
  ... truncated ...
```
