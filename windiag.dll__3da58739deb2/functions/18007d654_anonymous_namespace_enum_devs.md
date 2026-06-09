# _anonymous_namespace_::enum_devs

- ea: `0x18007d654`
- end: `0x18007d8d5`
- name: `_anonymous_namespace_::enum_devs`
- size: `641`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18007e3d0`

## callees

- `0x180004510`
- `0x180005520`
- `0x18003af08`
- `0x1800428b4`
- `0x180049674`
- `0x18007d654`
- `0x18009d010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18007d894`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18007d894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d776`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d7ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d7ee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007d7ad`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007d7ad`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18007d6e7`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18007d76c`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18007d6e7`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18007d76c`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18007d69c`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18007d69c`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18007d82c`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18007d82c`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18007d843`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18007d843`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall anonymous_namespace_::enum_devs(__int64 a1, __int64 a2)
{
  HDEVINFO ClassDevsW; // rax
  __int64 v4; // rdx
  void *v5; // rbx
  DWORD v6; // r14d
  DWORD i; // r9d
  PSP_DEVICE_INTERFACE_DETAIL_DATA_W v8; // rdi
  DWORD LastError; // eax
  HANDLE FileW; // rax
  void *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rcx
  _BYTE v15[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD RequiredSize; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE v17; // [rsp+48h] [rbp-B8h] BYREF
  PSP_DEVICE_INTERFACE_DETAIL_DATA_W DeviceInterfaceDetailData; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h]
  __int64 v20; // [rsp+68h] [rbp-98h]
  HDEVINFO v21; // [rsp+70h] [rbp-90h]
  HANDLE v22; // [rsp+78h] [rbp-88h]
  _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+80h] [rbp-80h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+C0h] [rbp-40h] BYREF

  v20 = a2;
  ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVICE_ENERGY_METER, 0, 0, 0x12u);
  v5 = ClassDevsW;
  v21 = ClassDevsW;
  if ( ClassDevsW != (HDEVINFO)-1LL )
  {
    v6 = 0;
    for ( i = 0; ; i = v6 )
    {
      memset(&DeviceInterfaceData.InterfaceClassGuid, 0, 28);
      DeviceInterfaceData.cbSize = 32;
      LODWORD(ClassDevsW) = SetupDiEnumDeviceInterfaces(v5, 0, &GUID_DEVICE_ENERGY_METER, i, &DeviceInterfaceData);
      if ( !(_DWORD)ClassDevsW )
        break;
      RequiredSize = 0;
      if ( !SetupDiGetDeviceInterfaceDetailW(v5, &DeviceInterfaceData, 0, 0, &RequiredSize, 0)
        && GetLastError() == 122
        && RequiredSize >= 8 )
      {
        v15[0] = 0;
        std::vector<unsigned char>::vector<unsigned char>(&DeviceInterfaceDetailData, RequiredSize, v15);
        v8 = DeviceInterfaceDetailData;
        DeviceInterfaceDetailData->cbSize = 8;
        DeviceInfoData.cbSize = 32;
        memset(&DeviceInfoData.ClassGuid, 0, 28);
        if ( !SetupDiGetDeviceInterfaceDetailW(
                v5,
                &DeviceInterfaceData,
                v8,
                v19 - (_DWORD)DeviceInterfaceDetailData,
                &RequiredSize,
                &DeviceInfoData) )
        {
          LastError = GetLastError();
          if ( LastError )
            goto LABEL_22;
        }
        FileW = CreateFileW(v8->DevicePath, 0x80000000, 3u, 0, 3u, 0x80u, 0);
        v11 = FileW;
        v22 = FileW;
        if ( FileW != (HANDLE)-1LL )
        {
          v17 = FileW;
          v12 = *(_QWORD *)(a2 + 56);
          if ( !v12 )
          {
            std::_Xbad_function_call();
LABEL_22:
            windiag::system_exception::system_exception(
              (windiag::system_exception *)pExceptionObject,
              LastError,
              0,
              "[%s:%d] failed; ",
              "enum_devs",
              38);
            throw (windiag::system_exception *)pExceptionObject;
          }
          (*(void (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v12 + 16LL))(v12, &v17);
        }
        if ( v11 != (void *)-1LL )
          CloseHandle(v11);
        std::vector<char>::~vector<char>(&DeviceInterfaceDetailData);
      }
      ++v6;
    }
  }
  if ( v5 != (void *)-1LL )
    LODWORD(ClassDevsW) = SetupDiDestroyDeviceInfoList(v5);
  v13 = *(_QWORD *)(a2 + 56);
  if ( v13 )
  {
    LOBYTE(v4) = v13 != a2;
    LODWORD(ClassDevsW) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, v4);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return (int)ClassDevsW;
}

```

## disassembly

```asm
0x18007d654  mov     [rsp-8+arg_0], rbx
0x18007d659  mov     [rsp-8+arg_10], rsi
0x18007d65e  push    rbp
0x18007d65f  push    rdi
0x18007d660  push    r14
0x18007d662  lea     rbp, [rsp-400h]
0x18007d66a  sub     rsp, 500h
0x18007d671  mov     rax, cs:__security_cookie
0x18007d678  xor     rax, rsp
0x18007d67b  mov     [rbp+410h+var_20], rax
0x18007d682  mov     rsi, rdx
0x18007d685  mov     [rsp+510h+var_4A8], rdx
0x18007d68a  mov     r9d, 12h; Flags
0x18007d690  xor     r8d, r8d; hwndParent
0x18007d693  xor     edx, edx; Enumerator
0x18007d695  lea     rcx, GUID_DEVICE_ENERGY_METER; ClassGuid
0x18007d69c  call    cs:__imp_SetupDiGetClassDevsW
0x18007d6a2  mov     rbx, rax
0x18007d6a5  mov     [rsp+510h+var_4A0], rax
0x18007d6aa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007d6ae  jz      loc_18007D83A
0x18007d6b4  xor     r14d, r14d
0x18007d6b7  xor     r9d, r9d
0x18007d6ba  jmp     loc_18007D805
0x18007d6bf  mov     [rsp+510h+var_4CC], 0
0x18007d6c7  mov     [rsp+510h+DeviceInfoData], 0; DeviceInfoData
0x18007d6d0  lea     rax, [rsp+510h+var_4CC]
0x18007d6d5  mov     [rsp+510h+RequiredSize], rax; RequiredSize
0x18007d6da  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x18007d6dd  xor     r8d, r8d; DeviceInterfaceDetailData
0x18007d6e0  lea     rdx, [rbp+410h+DeviceInterfaceData]; DeviceInterfaceData
0x18007d6e4  mov     rcx, rbx; DeviceInfoSet
0x18007d6e7  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18007d6ed  test    eax, eax
0x18007d6ef  jnz     loc_18007D7FF
0x18007d6f5  call    cs:__imp_GetLastError
0x18007d6fb  cmp     eax, 7Ah ; 'z'
0x18007d6fe  jnz     loc_18007D7FF
0x18007d704  cmp     [rsp+510h+var_4CC], 8
0x18007d709  jb      loc_18007D7FF
0x18007d70f  mov     [rsp+510h+var_4D0], 0
0x18007d714  mov     edx, [rsp+510h+var_4CC]
0x18007d718  lea     r8, [rsp+510h+var_4D0]
0x18007d71d  lea     rcx, [rsp+510h+DeviceInterfaceDetailData]
0x18007d722  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x18007d727  nop
0x18007d728  mov     rdi, [rsp+510h+DeviceInterfaceDetailData]
0x18007d72d  mov     dword ptr [rdi], 8
0x18007d733  mov     [rbp+410h+var_470.cbSize], 20h ; ' '
0x18007d73a  xorps   xmm0, xmm0
0x18007d73d  movups  xmmword ptr [rbp+410h+var_470.ClassGuid.Data1], xmm0
0x18007d741  movups  xmmword ptr [rbp+410h+var_470.ClassGuid.Data4+4], xmm0
0x18007d745  mov     r9d, [rsp+510h+var_4B8]
0x18007d74a  sub     r9d, dword ptr [rsp+510h+DeviceInterfaceDetailData]; DeviceInterfaceDetailDataSize
0x18007d74f  lea     rax, [rbp+410h+var_470]
0x18007d753  mov     [rsp+510h+DeviceInfoData], rax; DeviceInfoData
0x18007d758  lea     rax, [rsp+510h+var_4CC]
0x18007d75d  mov     [rsp+510h+RequiredSize], rax; RequiredSize
0x18007d762  mov     r8, rdi; DeviceInterfaceDetailData
0x18007d765  lea     rdx, [rbp+410h+DeviceInterfaceData]; DeviceInterfaceData
0x18007d769  mov     rcx, rbx; DeviceInfoSet
0x18007d76c  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18007d772  test    eax, eax
0x18007d774  jnz     short loc_18007D784
0x18007d776  call    cs:__imp_GetLastError
0x18007d77c  test    eax, eax
0x18007d77e  jnz     loc_18007D89B
0x18007d784  lea     rcx, [rdi+4]; lpFileName
0x18007d788  mov     [rsp+510h+hTemplateFile], 0; hTemplateFile
0x18007d791  mov     dword ptr [rsp+510h+DeviceInfoData], 80h; dwFlagsAndAttributes
0x18007d799  mov     eax, 3
0x18007d79e  mov     dword ptr [rsp+510h+RequiredSize], eax; dwCreationDisposition
0x18007d7a2  xor     r9d, r9d; lpSecurityAttributes
0x18007d7a5  mov     r8d, eax; dwShareMode
0x18007d7a8  mov     edx, 80000000h; dwDesiredAccess
0x18007d7ad  call    cs:__imp_CreateFileW
0x18007d7b3  mov     rdi, rax
0x18007d7b6  mov     [rsp+510h+var_498], rax
0x18007d7bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007d7bf  jz      short loc_18007D7E5
0x18007d7c1  mov     [rsp+510h+var_4C8], rax
0x18007d7c6  mov     rcx, [rsi+38h]
0x18007d7ca  test    rcx, rcx
0x18007d7cd  jz      loc_18007D894
0x18007d7d3  mov     rax, [rcx]
0x18007d7d6  lea     rdx, [rsp+510h+var_4C8]
0x18007d7db  mov     rax, [rax+10h]
0x18007d7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7e4  nop
0x18007d7e5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18007d7e9  jz      short loc_18007D7F5
0x18007d7eb  mov     rcx, rdi; hObject
0x18007d7ee  call    cs:__imp_CloseHandle
0x18007d7f4  nop
0x18007d7f5  lea     rcx, [rsp+510h+DeviceInterfaceDetailData]
0x18007d7fa  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18007d7ff  inc     r14d
0x18007d802  mov     r9d, r14d; MemberIndex
0x18007d805  xorps   xmm0, xmm0
0x18007d808  lea     rax, [rbp+410h+DeviceInterfaceData]
0x18007d80c  movups  xmmword ptr [rbp+410h+DeviceInterfaceData.InterfaceClassGuid.Data1], xmm0
0x18007d810  mov     [rsp+510h+RequiredSize], rax; DeviceInterfaceData
0x18007d815  mov     [rbp+410h+DeviceInterfaceData.cbSize], 20h ; ' '
0x18007d81c  movups  xmmword ptr [rbp+410h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x18007d820  lea     r8, GUID_DEVICE_ENERGY_METER; InterfaceClassGuid
0x18007d827  xor     edx, edx; DeviceInfoData
0x18007d829  mov     rcx, rbx; DeviceInfoSet
0x18007d82c  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x18007d832  test    eax, eax
0x18007d834  jnz     loc_18007D6BF
0x18007d83a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007d83e  jz      short loc_18007D84A
0x18007d840  mov     rcx, rbx; DeviceInfoSet
0x18007d843  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18007d849  nop
0x18007d84a  mov     rcx, [rsi+38h]
0x18007d84e  test    rcx, rcx
0x18007d851  jz      short loc_18007D86D
0x18007d853  mov     rax, [rcx]
0x18007d856  cmp     rcx, rsi
0x18007d859  setnz   dl
0x18007d85c  mov     rax, [rax+20h]
0x18007d860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d865  mov     qword ptr [rsi+38h], 0
0x18007d86d  mov     rcx, [rbp+410h+var_20]
0x18007d874  xor     rcx, rsp; StackCookie
0x18007d877  call    __security_check_cookie
0x18007d87c  lea     r11, [rsp+510h+var_10]
0x18007d884  mov     rbx, [r11+20h]
0x18007d888  mov     rsi, [r11+30h]
0x18007d88c  mov     rsp, r11
0x18007d88f  pop     r14
0x18007d891  pop     rdi
0x18007d892  pop     rbp
0x18007d893  retn
0x18007d894  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18007d89a  nop
0x18007d89b  mov     edx, eax; __int64
0x18007d89d  mov     dword ptr [rsp+510h+DeviceInfoData], 26h ; '&'
0x18007d8a5  lea     rax, aEnumDevs; "enum_devs"
0x18007d8ac  mov     [rsp+510h+RequiredSize], rax
0x18007d8b1  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18007d8b8  xor     r8d, r8d; void *
0x18007d8bb  lea     rcx, [rbp+410h+pExceptionObject]; this
0x18007d8bf  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18007d8c4  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18007d8cb  lea     rcx, [rbp+410h+pExceptionObject]; pExceptionObject
0x18007d8cf  call    _CxxThrowException_0
```
