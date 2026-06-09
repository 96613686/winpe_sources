# CMtPtLocal::_TryLowPrivilegeDeviceSafeRemoval(HWND__ *,bool *)

- ea: `0x1802445fc`
- end: `0x180244c1a`
- name: `?_TryLowPrivilegeDeviceSafeRemoval@CMtPtLocal@@AEAAJPEAUHWND__@@PEA_N@Z`
- size: `1566`
- prototype: `__int64 __fastcall(CMtPtLocal *__hidden this, HWND, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18057c530`

## callees

- `0x180018e4c`
- `0x18001aae0`
- `0x1801bcd70`
- `0x1802445fc`
- `0x180249490`
- `0x18024a53c`
- `0x18057cdc0`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18024481a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18024481a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180244961`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180244bbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180244961`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180244bbf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180244686`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802448c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180244686`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802448c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180244952`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024497a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180244989`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180244be1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180244952`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024497a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180244989`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180244be1`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x180244656`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x180244656`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180244b2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180244b2a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180244b04`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180244b04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180244aa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180244aa9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1802446ec`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180244927`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1802446ec`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180244927`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180244b49`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180244b49`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1802447f5`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18024487e`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1802447f5`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18024487e`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1802447b3`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1802447b3`
- `DEVOBJ!DevObjGetClassDevs` at `0x180244759`
- `DEVOBJ!DevObjGetClassDevs` at `0x180244759`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18024471c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18024471c`
- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x180244b83`
- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x180244b83`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1802449da`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1802449da`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x1802449b8`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x180244a62`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x1802449b8`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x180244a62`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x180244a34`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x180244a34`

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
0x1802445fc  mov     [rsp-8+arg_18], rbx
0x180244601  push    rbp
0x180244602  push    rsi
0x180244603  push    rdi
0x180244604  push    r12
0x180244606  push    r13
0x180244608  push    r14
0x18024460a  push    r15
0x18024460c  lea     rbp, [rsp-1F0h]
0x180244614  sub     rsp, 2F0h
0x18024461b  mov     rax, cs:__security_cookie
0x180244622  xor     rax, rsp
0x180244625  mov     [rbp+220h+var_40], rax
0x18024462c  mov     r13, r8
0x18024462f  mov     [rsp+320h+var_2E0], rdx
0x180244634  mov     r10, rcx
0x180244637  xor     edi, edi
0x180244639  mov     [r8], dil
0x18024463c  lea     r8, aA_0; "\\\\.\\A:"
0x180244643  lea     esi, [rdi+7]
0x180244646  mov     edx, esi; unsigned __int64
0x180244648  lea     rcx, [rbp+220h+FileName]; unsigned __int16 *
0x18024464c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180244651  movzx   ecx, word ptr [r10+34h]; lpsz
0x180244656  call    cs:__imp_CharUpperW
0x18024465d  nop     dword ptr [rax+rax+00h]
0x180244662  mov     [rbp+220h+var_228], ax
0x180244666  mov     [rsp+320h+hTemplateFile], rdi; hTemplateFile
0x18024466b  lea     eax, [rsi+79h]
0x18024466e  mov     [rsp+320h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180244672  mov     [rsp+320h+dwCreationDisposition], 3; dwCreationDisposition
0x18024467a  xor     r9d, r9d; lpSecurityAttributes
0x18024467d  mov     r8d, esi; dwShareMode
0x180244680  mov     edx, eax; dwDesiredAccess
0x180244682  lea     rcx, [rbp+220h+FileName]; lpFileName
0x180244686  call    cs:__imp_CreateFileW
0x18024468d  nop     dword ptr [rax+rax+00h]
0x180244692  mov     r15, rax
0x180244695  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180244699  jz      short loc_18024469F
0x18024469b  mov     ebx, edi
0x18024469d  jmp     short loc_1802446A6
0x18024469f  call    ResultFromKnownLastError
0x1802446a4  mov     ebx, eax
0x1802446a6  xor     eax, eax
0x1802446a8  mov     [rsp+320h+OutBuffer], rax
0x1802446ad  mov     [rsp+320h+var_2A8], eax
0x1802446b1  test    ebx, ebx
0x1802446b3  js      loc_18024477B
0x1802446b9  mov     [rsp+320h+BytesReturned], edi
0x1802446bd  mov     [rsp+320h+lpOverlapped], rdi; lpOverlapped
0x1802446c2  lea     rax, [rsp+320h+BytesReturned]
0x1802446c7  mov     [rsp+320h+hTemplateFile], rax; lpBytesReturned
0x1802446cc  mov     [rsp+320h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x1802446d4  lea     rax, [rsp+320h+OutBuffer]
0x1802446d9  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; lpOutBuffer
0x1802446de  xor     r9d, r9d; nInBufferSize
0x1802446e1  xor     r8d, r8d; lpInBuffer
0x1802446e4  mov     edx, 2D1080h; dwIoControlCode
0x1802446e9  mov     rcx, r15; hDevice
0x1802446ec  call    cs:__imp_DeviceIoControl
0x1802446f3  nop     dword ptr [rax+rax+00h]
0x1802446f8  test    eax, eax
0x1802446fa  jnz     short loc_180244707
0x1802446fc  call    ResultFromKnownLastError
0x180244701  mov     ebx, eax
0x180244703  test    eax, eax
0x180244705  js      short loc_18024477B
0x180244707  cmp     dword ptr [rsp+320h+OutBuffer], esi
0x18024470b  jnz     short loc_180244776
0x18024470d  mov     qword ptr [rsp+320h+dwCreationDisposition], rdi
0x180244712  xor     r9d, r9d
0x180244715  xor     r8d, r8d
0x180244718  xor     edx, edx
0x18024471a  xor     ecx, ecx
0x18024471c  call    cs:__imp_DevObjCreateDeviceInfoList
0x180244723  nop     dword ptr [rax+rax+00h]
0x180244728  mov     rsi, rax
0x18024472b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18024472f  jnz     short loc_18024473C
0x180244731  call    ResultFromKnownLastError
0x180244736  mov     ebx, eax
0x180244738  test    eax, eax
0x18024473a  js      short loc_18024477E
0x18024473c  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], rdi
0x180244741  mov     qword ptr [rsp+320h+dwCreationDisposition], rdi
0x180244746  mov     r9d, 12h
0x18024474c  xor     r8d, r8d
0x18024474f  lea     rdx, GUID_DEVINTERFACE_DISK
0x180244756  mov     rcx, rsi
0x180244759  call    cs:__imp_DevObjGetClassDevs
0x180244760  nop     dword ptr [rax+rax+00h]
0x180244765  test    eax, eax
0x180244767  jz      short loc_18024476D
0x180244769  mov     ebx, edi
0x18024476b  jmp     short loc_18024477E
0x18024476d  call    ResultFromKnownLastError
0x180244772  mov     ebx, eax
0x180244774  jmp     short loc_18024477E
0x180244776  mov     ebx, 80004005h
0x18024477b  mov     rsi, rdi
0x18024477e  mov     r12d, edi
0x180244781  test    ebx, ebx
0x180244783  js      loc_180244BD8
0x180244789  mov     [rbp+220h+var_280], 20h ; ' '
0x180244790  xorps   xmm0, xmm0
0x180244793  movups  xmmword ptr [rbp+220h+var_27C], xmm0
0x180244797  movups  xmmword ptr [rbp+220h+var_27C+0Ch], xmm0
0x18024479b  lea     rax, [rbp+220h+var_280]
0x18024479f  mov     qword ptr [rsp+320h+dwCreationDisposition], rax
0x1802447a4  mov     r9d, r12d
0x1802447a7  lea     r8, GUID_DEVINTERFACE_DISK
0x1802447ae  xor     edx, edx
0x1802447b0  mov     rcx, rsi
0x1802447b3  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1802447ba  nop     dword ptr [rax+rax+00h]
0x1802447bf  test    eax, eax
0x1802447c1  jz      short loc_1802447C7
0x1802447c3  mov     ebx, edi
0x1802447c5  jmp     short loc_1802447CE
0x1802447c7  call    ResultFromKnownLastError
0x1802447cc  mov     ebx, eax
0x1802447ce  mov     r14, rdi
0x1802447d1  mov     dword ptr [rsp+320h+uBytes], edi
0x1802447d5  test    ebx, ebx
0x1802447d7  js      short loc_180244840
0x1802447d9  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], rdi
0x1802447de  lea     rax, [rsp+320h+uBytes]
0x1802447e3  mov     qword ptr [rsp+320h+dwCreationDisposition], rax
0x1802447e8  xor     r9d, r9d
0x1802447eb  xor     r8d, r8d
0x1802447ee  lea     rdx, [rbp+220h+var_280]
0x1802447f2  mov     rcx, rsi
0x1802447f5  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1802447fc  nop     dword ptr [rax+rax+00h]
0x180244801  test    eax, eax
0x180244803  jnz     short loc_18024483B
0x180244805  call    ResultFromKnownLastError
0x18024480a  cmp     eax, 8007007Ah
0x18024480f  jnz     short loc_18024483B
0x180244811  mov     edx, dword ptr [rsp+320h+uBytes]; uBytes
0x180244815  mov     ecx, 40h ; '@'; uFlags
0x18024481a  call    cs:__imp_LocalAlloc
0x180244821  nop     dword ptr [rax+rax+00h]
0x180244826  mov     r14, rax
0x180244829  mov     rcx, rax
0x18024482c  neg     rcx
0x18024482f  sbb     ebx, ebx
0x180244831  not     ebx
0x180244833  and     ebx, 8007000Eh
0x180244839  jmp     short loc_180244840
0x18024483b  mov     ebx, 8000FFFFh
0x180244840  xorps   xmm0, xmm0
0x180244843  movups  [rbp+220h+var_260], xmm0
0x180244847  movups  xmmword ptr [rbp+220h+dnDevInst], xmm0
0x18024484b  movups  [rbp+220h+var_240], xmm0
0x18024484f  test    ebx, ebx
0x180244851  js      short loc_180244899
0x180244853  mov     dword ptr [r14], 8
0x18024485a  mov     dword ptr [rbp+220h+var_260], 30h ; '0'
0x180244861  lea     rax, [rbp+220h+var_260]
0x180244865  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], rax
0x18024486a  mov     qword ptr [rsp+320h+dwCreationDisposition], rdi
0x18024486f  mov     r9d, dword ptr [rsp+320h+uBytes]
0x180244874  mov     r8, r14
0x180244877  lea     rdx, [rbp+220h+var_280]
0x18024487b  mov     rcx, rsi
0x18024487e  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180244885  nop     dword ptr [rax+rax+00h]
0x18024488a  test    eax, eax
0x18024488c  jz      short loc_180244892
0x18024488e  mov     ebx, edi
0x180244890  jmp     short loc_180244899
0x180244892  call    ResultFromKnownLastError
0x180244897  mov     ebx, eax
0x180244899  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18024489d  test    ebx, ebx
0x18024489f  js      short loc_1802448E8
0x1802448a1  lea     rcx, [r14+4]; lpFileName
0x1802448a5  mov     [rsp+320h+hTemplateFile], 0; hTemplateFile
0x1802448ae  mov     [rsp+320h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1802448b6  lea     eax, [rdi+4]
0x1802448b9  mov     [rsp+320h+dwCreationDisposition], eax; dwCreationDisposition
0x1802448bd  xor     r9d, r9d; lpSecurityAttributes
0x1802448c0  mov     r8d, eax; dwShareMode
0x1802448c3  mov     edx, 100080h; dwDesiredAccess
0x1802448c8  call    cs:__imp_CreateFileW
0x1802448cf  nop     dword ptr [rax+rax+00h]
0x1802448d4  mov     rdi, rax
0x1802448d7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802448db  jz      short loc_1802448E1
0x1802448dd  xor     ebx, ebx
0x1802448df  jmp     short loc_1802448E8
0x1802448e1  call    ResultFromKnownLastError
0x1802448e6  mov     ebx, eax
0x1802448e8  xor     eax, eax
0x1802448ea  mov     [rbp+220h+var_2A0], rax
0x1802448ee  mov     [rbp+220h+var_298], eax
0x1802448f1  test    ebx, ebx
0x1802448f3  js      short loc_18024494F
0x1802448f5  mov     [rsp+320h+BytesReturned], eax
0x1802448f9  mov     [rsp+320h+lpOverlapped], rax; lpOverlapped
0x1802448fe  lea     rax, [rsp+320h+BytesReturned]
0x180244903  mov     [rsp+320h+hTemplateFile], rax; lpBytesReturned
0x180244908  mov     [rsp+320h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x180244910  lea     rax, [rbp+220h+var_2A0]
0x180244914  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; lpOutBuffer
0x180244919  xor     r9d, r9d; nInBufferSize
0x18024491c  xor     r8d, r8d; lpInBuffer
0x18024491f  mov     edx, 2D1080h; dwIoControlCode
0x180244924  mov     rcx, rdi; hDevice
0x180244927  call    cs:__imp_DeviceIoControl
0x18024492e  nop     dword ptr [rax+rax+00h]
0x180244933  test    eax, eax
0x180244935  jz      short loc_18024493B
0x180244937  xor     ebx, ebx
0x180244939  jmp     short loc_180244946
0x18024493b  call    ResultFromKnownLastError
0x180244940  mov     ebx, eax
0x180244942  test    eax, eax
0x180244944  js      short loc_18024494F
0x180244946  mov     eax, dword ptr [rsp+320h+OutBuffer+4]
0x18024494a  cmp     dword ptr [rbp+220h+var_2A0+4], eax
0x18024494d  jz      short loc_180244977
0x18024494f  mov     rcx, rdi; hObject
0x180244952  call    cs:__imp_CloseHandle
0x180244959  nop     dword ptr [rax+rax+00h]
0x18024495e  mov     rcx, r14; hMem
0x180244961  call    cs:__imp_LocalFree
0x180244968  nop     dword ptr [rax+rax+00h]
0x18024496d  inc     r12d
0x180244970  xor     edi, edi
0x180244972  jmp     loc_180244781
0x180244977  mov     rcx, r15; hObject
0x18024497a  call    cs:__imp_CloseHandle
0x180244981  nop     dword ptr [rax+rax+00h]
0x180244986  mov     rcx, rdi; hObject
0x180244989  call    cs:__imp_CloseHandle
0x180244990  nop     dword ptr [rax+rax+00h]
0x180244995  xor     edx, edx; Val
0x180244997  mov     r8d, 190h; Size
0x18024499d  lea     rcx, [rbp+220h+Buffer]; void *
0x1802449a1  call    memset_0
0x1802449a6  xor     r9d, r9d; ulFlags
0x1802449a9  mov     edi, 0C8h
0x1802449ae  mov     r8d, edi; BufferLen
0x1802449b1  lea     rdx, [rbp+220h+Buffer]; Buffer
0x1802449b5  mov     ecx, [rbp+220h+dnDevInst+4]; dnDevInst
0x1802449b8  call    cs:__imp_CM_Get_Device_IDW
0x1802449bf  nop     dword ptr [rax+rax+00h]
0x1802449c4  xor     esi, esi
0x1802449c6  mov     [rsp+320h+pdnDevInst], esi
0x1802449ca  test    eax, eax
0x1802449cc  jnz     short loc_1802449F5
0x1802449ce  xor     r8d, r8d; ulFlags
0x1802449d1  lea     rdx, [rbp+220h+Buffer]; pDeviceID
0x1802449d5  lea     rcx, [rsp+320h+pdnDevInst]; pdnDevInst
0x1802449da  call    cs:__imp_CM_Locate_DevNodeW
0x1802449e1  nop     dword ptr [rax+rax+00h]
0x1802449e6  neg     eax
0x1802449e8  sbb     ebx, ebx
0x1802449ea  mov     r15d, 80004005h
0x1802449f0  and     ebx, r15d
0x1802449f3  jmp     short loc_1802449FE
0x1802449f5  mov     r15d, 80004005h
0x1802449fb  mov     ebx, r15d
0x1802449fe  test    ebx, ebx
0x180244a00  js      short loc_180244A75
0x180244a02  mov     [rsp+320h+var_2C0], esi
0x180244a06  lea     rdx, [rsp+320h+var_2C0]; unsigned int *
0x180244a0b  mov     ecx, [rsp+320h+pdnDevInst]; unsigned int
0x180244a0f  call    ?GetCapabilities@@YAJKPEAK@Z; GetCapabilities(ulong,ulong *)
0x180244a14  mov     ebx, eax
0x180244a16  test    eax, eax
0x180244a18  js      short loc_1802449FE
0x180244a1a  test    byte ptr [rsp+320h+var_2C0], 4
0x180244a1f  jnz     short loc_180244A54
0x180244a21  mov     [rsp+320h+BytesReturned], esi
0x180244a25  xor     r9d, r9d; hMachine
0x180244a28  xor     r8d, r8d; ulFlags
0x180244a2b  mov     edx, [rsp+320h+pdnDevInst]; dnDevInst
0x180244a2f  lea     rcx, [rsp+320h+BytesReturned]; pdnDevInst
0x180244a34  call    cs:__imp_CM_Get_Parent_Ex
0x180244a3b  nop     dword ptr [rax+rax+00h]
0x180244a40  test    eax, eax
0x180244a42  jnz     short loc_1802449FB
0x180244a44  mov     eax, [rsp+320h+BytesReturned]
0x180244a48  test    eax, eax
0x180244a4a  jz      short loc_1802449FB
0x180244a4c  mov     ebx, esi
0x180244a4e  mov     [rsp+320h+pdnDevInst], eax
0x180244a52  jmp     short loc_1802449FE
0x180244a54  xor     r9d, r9d; ulFlags
0x180244a57  mov     r8d, edi; BufferLen
0x180244a5a  lea     rdx, [rbp+220h+Buffer]; Buffer
0x180244a5e  mov     ecx, [rsp+320h+pdnDevInst]; dnDevInst
0x180244a62  call    cs:__imp_CM_Get_Device_IDW
0x180244a69  nop     dword ptr [rax+rax+00h]
0x180244a6e  neg     eax
0x180244a70  sbb     ebx, ebx
  ... truncated ...
```
