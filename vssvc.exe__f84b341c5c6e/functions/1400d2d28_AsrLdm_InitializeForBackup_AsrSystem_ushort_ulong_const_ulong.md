# AsrLdm::InitializeForBackup(AsrSystem *,ushort *,ulong const *,ulong)

- ea: `0x1400d2d28`
- end: `0x1400d318f`
- name: `?InitializeForBackup@AsrLdm@@QEAAHPEAVAsrSystem@@PEAGPEBKK@Z`
- size: `1127`
- prototype: `__int64 __fastcall(AsrLdm *__hidden this, struct AsrSystem *, unsigned __int16 *, const unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14006168c`

## callees

- `0x140010170`
- `0x140021ca0`
- `0x1400235a8`
- `0x14005b208`
- `0x140091560`
- `0x1400919a0`
- `0x1400919c4`
- `0x1400921dc`
- `0x1400d257c`
- `0x1400d2cbc`
- `0x1400d2d28`
- `0x1400d3354`
- `0x1400d365c`
- `0x1400d969c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d3163`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d3163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3079`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d30c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d30c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400d2e5e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400d2e5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d314f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d314f`

## string_xrefs

- `0x1400d2e11`: `DevicePathToWin32Path(DD_VOLMGR_CONTROL_DEVICE_NAME, ARRAY_COUNT_PARAM(wszVolMgmtCtlPath))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AsrLdm::InitializeForBackup(
        AsrLdm *this,
        struct AsrSystem *a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        unsigned int a5)
{
  struct AsrSystem *v6; // rdi
  char *v8; // r12
  int v9; // eax
  DWORD LastError; // ebx
  int v11; // eax
  HANDLE v12; // r14
  DWORD v13; // eax
  DynPack *v14; // rsi
  int v15; // eax
  unsigned int v16; // edx
  DWORD v17; // eax
  unsigned __int64 v18; // r15
  __int64 v19; // rax
  bool v20; // cf
  unsigned __int64 v21; // rax
  _QWORD *v22; // rax
  unsigned int v23; // ebp
  DWORD v24; // eax
  struct _DRIVE_LAYOUT_INFORMATION_EX *v25; // rax
  int v26; // edx
  const char *dwCreationDisposition; // [rsp+20h] [rbp-2A8h]
  void *v29; // [rsp+40h] [rbp-288h] BYREF
  unsigned int *v30; // [rsp+48h] [rbp-280h]
  unsigned __int16 *v31; // [rsp+50h] [rbp-278h]
  struct AsrSystem *v32; // [rsp+58h] [rbp-270h]
  WCHAR FileName; // [rsp+60h] [rbp-268h] BYREF
  _BYTE v34[526]; // [rsp+62h] [rbp-266h] BYREF

  v30 = a4;
  v31 = a3;
  v6 = a2;
  v32 = a2;
  TraceFunctionEnter(L"AsrLdm::InitializeForBackup");
  FileName = 0;
  memset_0(v34, 0, 0x206u);
  v8 = 0;
  v29 = 0;
  if ( !v6 )
  {
    LastError = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_47;
    }
    v26 = 24;
    dwCreationDisposition = "pAsrSys";
LABEL_46:
    WPP_SF_Ds(
      *(_QWORD *)v25->Gpt.DiskId.Data4,
      v26,
      (unsigned int)WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids,
      87,
      dwCreationDisposition);
    goto LABEL_47;
  }
  if ( !a3 )
  {
    LODWORD(v6) = 0;
    LastError = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_47;
    }
    v26 = 25;
    dwCreationDisposition = "pmwszCriticalVolumes";
    goto LABEL_46;
  }
  v9 = StringCchPrintfW(&FileName, 0x104u, L"\\\\?\\GLOBALROOT%s", L"\\Device\\VolMgrControl");
  if ( v9 >= 0 )
  {
    v12 = CreateFileW(&FileName, 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( v12 == (HANDLE)-1LL )
    {
      LODWORD(v6) = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v13 = GetLastError();
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          27,
          (unsigned int)WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids,
          v13,
          "GetLastError()");
      }
    }
    else
    {
      v14 = 0;
      v15 = DoIoctlCall(v12, 0x764324u, 0, 0, &v29);
      v8 = (char *)v29;
      if ( v15 )
      {
        v18 = *(unsigned int *)v29;
        if ( !(_DWORD)v18 )
          goto LABEL_28;
        v19 = 136LL * *(unsigned int *)v29;
        if ( !is_mul_ok(v18, 0x88u) )
          v19 = -1;
        v20 = __CFADD__(v19, 8);
        v21 = v19 + 8;
        if ( v20 )
          v21 = -1;
        v22 = operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
        v29 = v22;
        if ( v22 )
        {
          *v22 = (unsigned int)v18;
          v14 = (DynPack *)(v22 + 1);
          `eh vector constructor iterator'(
            v22 + 1,
            0x88u,
            (unsigned int)v18,
            (void (*)(void *))DynPack::DynPack,
            (void (*)(void *))DynPack::~DynPack);
        }
        else
        {
          v14 = 0;
        }
        if ( v14 )
        {
LABEL_28:
          v23 = 0;
          LODWORD(v6) = 1;
          while ( 1 )
          {
            if ( v23 >= (unsigned int)v18 )
            {
              LastError = 0;
              *((_QWORD *)this + 1) = v14;
              v14 = 0;
              *(_DWORD *)this = v18;
              goto LABEL_36;
            }
            if ( !(unsigned int)DynPack::Initialize(
                                  (DynPack *)((char *)v14 + 136 * v23),
                                  v32,
                                  v12,
                                  (struct _GUID *)&v8[16 * v23 + 4],
                                  v31,
                                  v30,
                                  a5) )
              break;
            ++v23;
          }
          LODWORD(v6) = 0;
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v24 = GetLastError();
            WPP_SF_Dsd(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              30,
              (unsigned int)WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids,
              v24,
              (__int64)"GetLastError()",
              v23);
          }
        }
        else
        {
          LODWORD(v6) = 0;
          LastError = 14;
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              29,
              (unsigned int)WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids,
              14,
              "pPackList");
          }
        }
      }
      else
      {
        LODWORD(v6) = 0;
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v17 = GetLastError();
          WPP_SF_Ds(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            28,
            (unsigned int)WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids,
            v17,
            "DoVdsIoctlCall(hVdsDriver, IOCTL_VOLMGR_ENUM_PACKS, NULL, 0, (void **)&pOutBuffer)");
        }
      }
LABEL_36:
      if ( v12 )
        CloseHandle(v12);
      if ( v14 )
        DynPack::`vector deleting destructor'(v14, v16);
    }
  }
  else
  {
    LODWORD(v6) = 0;
    LastError = WIN32_FROM_HRESULT((unsigned int)v9);
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v11 = StringCchPrintfW(&FileName, 0x104u, L"\\\\?\\GLOBALROOT%s", L"\\Device\\VolMgrControl");
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        26,
        (unsigned int)WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids,
        v11,
        "DevicePathToWin32Path(DD_VOLMGR_CONTROL_DEVICE_NAME, ARRAY_COUNT_PARAM(wszVolMgmtCtlPath))");
    }
  }
LABEL_47:
  CoTaskMemFree(v8);
  TraceFunctionExit(L"AsrLdm::InitializeForBackup");
  SetLastError(LastError);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400d2d28  push    rbx
0x1400d2d2a  push    rbp
0x1400d2d2b  push    rsi
0x1400d2d2c  push    rdi
0x1400d2d2d  push    r12
0x1400d2d2f  push    r13
0x1400d2d31  push    r14
0x1400d2d33  push    r15
0x1400d2d35  sub     rsp, 288h
0x1400d2d3c  mov     rax, cs:__security_cookie
0x1400d2d43  xor     rax, rsp
0x1400d2d46  mov     [rsp+2C8h+var_58], rax
0x1400d2d4e  mov     [rsp+2C8h+var_280], r9
0x1400d2d53  mov     rbx, r8
0x1400d2d56  mov     [rsp+2C8h+var_278], rbx
0x1400d2d5b  mov     rdi, rdx
0x1400d2d5e  mov     [rsp+2C8h+var_270], rdx
0x1400d2d63  mov     r13, rcx
0x1400d2d66  lea     rcx, aAsrldmInitiali; "AsrLdm::InitializeForBackup"
0x1400d2d6d  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400d2d72  xor     eax, eax
0x1400d2d74  mov     [rsp+2C8h+FileName], ax
0x1400d2d79  xor     edx, edx; Val
0x1400d2d7b  mov     r8d, 206h; Size
0x1400d2d81  lea     rcx, [rsp+2C8h+var_266]; void *
0x1400d2d86  call    memset_0
0x1400d2d8b  xor     r12d, r12d
0x1400d2d8e  mov     [rsp+2C8h+var_288], r12
0x1400d2d93  test    rdi, rdi
0x1400d2d96  jz      loc_1400D310A
0x1400d2d9c  test    rbx, rbx
0x1400d2d9f  jz      loc_1400D30D7
0x1400d2da5  lea     r9, aDeviceVolmgrco; "\\Device\\VolMgrControl"
0x1400d2dac  lea     r8, aGlobalrootS; "\\\\?\\GLOBALROOT%s"
0x1400d2db3  mov     esi, 104h
0x1400d2db8  mov     edx, esi; unsigned __int64
0x1400d2dba  lea     rcx, [rsp+2C8h+FileName]; unsigned __int16 *
0x1400d2dbf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400d2dc4  test    eax, eax
0x1400d2dc6  jns     short loc_1400D2E3C
0x1400d2dc8  xor     edi, edi
0x1400d2dca  mov     ecx, eax
0x1400d2dcc  call    WIN32_FROM_HRESULT
0x1400d2dd1  mov     ebx, eax
0x1400d2dd3  lea     rcx, WPP_GLOBAL_Control
0x1400d2dda  mov     rax, cs:WPP_GLOBAL_Control
0x1400d2de1  cmp     rax, rcx
0x1400d2de4  jz      loc_1400D314C
0x1400d2dea  test    byte ptr [rax+1Ch], 8
0x1400d2dee  jz      loc_1400D314C
0x1400d2df4  lea     r9, aDeviceVolmgrco; "\\Device\\VolMgrControl"
0x1400d2dfb  lea     r8, aGlobalrootS; "\\\\?\\GLOBALROOT%s"
0x1400d2e02  mov     edx, esi; unsigned __int64
0x1400d2e04  lea     rcx, [rsp+2C8h+FileName]; unsigned __int16 *
0x1400d2e09  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400d2e0e  lea     edx, [rdi+1Ah]
0x1400d2e11  lea     rcx, aDevicepathtowi; "DevicePathToWin32Path(DD_VOLMGR_CONTROL"...
0x1400d2e18  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rcx
0x1400d2e1d  mov     r9d, eax
0x1400d2e20  lea     r8, WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids
0x1400d2e27  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d2e2e  mov     rcx, [rcx+10h]
0x1400d2e32  call    WPP_SF_Ds
0x1400d2e37  jmp     loc_1400D314C
0x1400d2e3c  mov     [rsp+2C8h+hTemplateFile], r12; hTemplateFile
0x1400d2e41  mov     [rsp+2C8h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1400d2e46  mov     r8d, 3; dwShareMode
0x1400d2e4c  mov     [rsp+2C8h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400d2e51  xor     r9d, r9d; lpSecurityAttributes
0x1400d2e54  mov     edx, 0C0000000h; dwDesiredAccess
0x1400d2e59  lea     rcx, [rsp+2C8h+FileName]; lpFileName
0x1400d2e5e  call    cs:__imp_CreateFileW
0x1400d2e64  mov     r14, rax
0x1400d2e67  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400d2e6b  cmp     rax, rdi
0x1400d2e6e  jnz     short loc_1400D2EC3
0x1400d2e70  xor     edi, edi
0x1400d2e72  call    cs:__imp_GetLastError
0x1400d2e78  mov     ebx, eax
0x1400d2e7a  lea     rcx, WPP_GLOBAL_Control
0x1400d2e81  mov     rax, cs:WPP_GLOBAL_Control
0x1400d2e88  cmp     rax, rcx
0x1400d2e8b  jz      loc_1400D314C
0x1400d2e91  test    byte ptr [rax+1Ch], 8
0x1400d2e95  jz      loc_1400D314C
0x1400d2e9b  call    cs:__imp_GetLastError
0x1400d2ea1  lea     edx, [rdi+1Bh]
0x1400d2ea4  lea     rcx, aGetlasterror_1; "GetLastError()"
0x1400d2eab  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rcx
0x1400d2eb0  mov     r9d, eax
0x1400d2eb3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d2eba  mov     rcx, [rcx+10h]
0x1400d2ebe  jmp     loc_1400D3140
0x1400d2ec3  xor     esi, esi
0x1400d2ec5  lea     rax, [rsp+2C8h+var_288]
0x1400d2eca  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rax; void **
0x1400d2ecf  xor     r9d, r9d; nInBufferSize
0x1400d2ed2  xor     r8d, r8d; lpInBuffer
0x1400d2ed5  mov     edx, 764324h; dwIoControlCode
0x1400d2eda  mov     rcx, r14; hDevice
0x1400d2edd  call    ?DoIoctlCall@@YAHPEAXK0KPEAPEAX@Z; DoIoctlCall(void *,ulong,void *,ulong,void * *)
0x1400d2ee2  mov     r12, [rsp+2C8h+var_288]
0x1400d2ee7  test    eax, eax
0x1400d2ee9  jnz     short loc_1400D2F4A
0x1400d2eeb  xor     edi, edi
0x1400d2eed  call    cs:__imp_GetLastError
0x1400d2ef3  mov     ebx, eax
0x1400d2ef5  lea     rcx, WPP_GLOBAL_Control
0x1400d2efc  mov     rax, cs:WPP_GLOBAL_Control
0x1400d2f03  cmp     rax, rcx
0x1400d2f06  jz      loc_1400D30BA
0x1400d2f0c  test    byte ptr [rax+1Ch], 8
0x1400d2f10  jz      loc_1400D30BA
0x1400d2f16  call    cs:__imp_GetLastError
0x1400d2f1c  lea     edx, [rsi+1Ch]
0x1400d2f1f  lea     rcx, aDovdsioctlcall; "DoVdsIoctlCall(hVdsDriver, IOCTL_VOLMGR"...
0x1400d2f26  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rcx
0x1400d2f2b  mov     r9d, eax
0x1400d2f2e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d2f35  mov     rcx, [rcx+10h]
0x1400d2f39  lea     r8, WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids
0x1400d2f40  call    WPP_SF_Ds
0x1400d2f45  jmp     loc_1400D30BA
0x1400d2f4a  mov     r15d, [r12]
0x1400d2f4e  test    r15d, r15d
0x1400d2f51  jz      loc_1400D2FFA
0x1400d2f57  mov     ebx, r15d
0x1400d2f5a  mov     ebp, 88h
0x1400d2f5f  mov     eax, ebp
0x1400d2f61  mul     r15
0x1400d2f64  cmovb   rax, rdi
0x1400d2f68  add     rax, 8
0x1400d2f6c  cmovb   rax, rdi
0x1400d2f70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400d2f77  mov     rcx, rax; unsigned __int64
0x1400d2f7a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400d2f7f  mov     [rsp+2C8h+var_288], rax
0x1400d2f84  test    rax, rax
0x1400d2f87  jz      short loc_1400D2FB2
0x1400d2f89  mov     [rax], rbx
0x1400d2f8c  lea     rsi, [rax+8]
0x1400d2f90  lea     rax, ??1DynPack@@QEAA@XZ; DynPack::~DynPack(void)
0x1400d2f97  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rax; void (*)(void *)
0x1400d2f9c  lea     r9, ??0DynPack@@QEAA@XZ; void (*)(void *)
0x1400d2fa3  mov     r8d, ebx; unsigned __int64
0x1400d2fa6  mov     edx, ebp; unsigned __int64
0x1400d2fa8  mov     rcx, rsi; void *
0x1400d2fab  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400d2fb0  jmp     short loc_1400D2FB4
0x1400d2fb2  xor     esi, esi
0x1400d2fb4  test    rsi, rsi
0x1400d2fb7  jnz     short loc_1400D2FFA
0x1400d2fb9  xor     edi, edi
0x1400d2fbb  lea     ebx, [rsi+0Eh]
0x1400d2fbe  lea     rcx, WPP_GLOBAL_Control
0x1400d2fc5  mov     rax, cs:WPP_GLOBAL_Control
0x1400d2fcc  cmp     rax, rcx
0x1400d2fcf  jz      loc_1400D30BA
0x1400d2fd5  test    byte ptr [rax+1Ch], 8
0x1400d2fd9  jz      loc_1400D30BA
0x1400d2fdf  lea     edx, [rsi+1Dh]
0x1400d2fe2  lea     rcx, aPpacklist; "pPackList"
0x1400d2fe9  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rcx
0x1400d2fee  mov     r9d, ebx
0x1400d2ff1  mov     rcx, [rax+10h]
0x1400d2ff5  jmp     loc_1400D2F39
0x1400d2ffa  xor     ebp, ebp
0x1400d2ffc  lea     edi, [rbp+1]
0x1400d2fff  mov     ebx, [rsp+2C8h+arg_20]
0x1400d3006  cmp     ebp, r15d
0x1400d3009  jnb     loc_1400D30AE
0x1400d300f  mov     ecx, ebp
0x1400d3011  mov     r9d, ebp
0x1400d3014  shl     r9, 4
0x1400d3018  add     r9, 4
0x1400d301c  add     r9, r12; struct _GUID *
0x1400d301f  imul    rcx, 88h
0x1400d3026  add     rcx, rsi; this
0x1400d3029  mov     dword ptr [rsp+2C8h+hTemplateFile], ebx; unsigned int
0x1400d302d  mov     rax, [rsp+2C8h+var_280]
0x1400d3032  mov     qword ptr [rsp+2C8h+dwFlagsAndAttributes], rax; unsigned int *
0x1400d3037  mov     rax, [rsp+2C8h+var_278]
0x1400d303c  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rax; unsigned __int16 *
0x1400d3041  mov     r8, r14; void *
0x1400d3044  mov     rdx, [rsp+2C8h+var_270]; struct AsrSystem *
0x1400d3049  call    ?Initialize@DynPack@@QEAAHPEAVAsrSystem@@PEAXPEAU_GUID@@PEAGPEBKK@Z; DynPack::Initialize(AsrSystem *,void *,_GUID *,ushort *,ulong const *,ulong)
0x1400d304e  test    eax, eax
0x1400d3050  jz      short loc_1400D3056
0x1400d3052  add     ebp, edi
0x1400d3054  jmp     short loc_1400D3006
0x1400d3056  xor     edi, edi
0x1400d3058  call    cs:__imp_GetLastError
0x1400d305e  mov     ebx, eax
0x1400d3060  lea     rcx, WPP_GLOBAL_Control
0x1400d3067  mov     rax, cs:WPP_GLOBAL_Control
0x1400d306e  cmp     rax, rcx
0x1400d3071  jz      short loc_1400D30BA
0x1400d3073  test    byte ptr [rax+1Ch], 8
0x1400d3077  jz      short loc_1400D30BA
0x1400d3079  call    cs:__imp_GetLastError
0x1400d307f  lea     edx, [rdi+1Eh]
0x1400d3082  mov     [rsp+2C8h+dwFlagsAndAttributes], ebp
0x1400d3086  lea     rcx, aGetlasterror_1; "GetLastError()"
0x1400d308d  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rcx
0x1400d3092  mov     r9d, eax
0x1400d3095  lea     r8, WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids
0x1400d309c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d30a3  mov     rcx, [rcx+10h]
0x1400d30a7  call    WPP_SF_Dsd
0x1400d30ac  jmp     short loc_1400D30BA
0x1400d30ae  xor     ebx, ebx
0x1400d30b0  mov     [r13+8], rsi
0x1400d30b4  xor     esi, esi
0x1400d30b6  mov     [r13+0], r15d
0x1400d30ba  test    r14, r14
0x1400d30bd  jz      short loc_1400D30C8
0x1400d30bf  mov     rcx, r14; hObject
0x1400d30c2  call    cs:__imp_CloseHandle
0x1400d30c8  test    rsi, rsi
0x1400d30cb  jz      short loc_1400D314C
0x1400d30cd  mov     rcx, rsi; this
0x1400d30d0  call    ??_EDynPack@@QEAAPEAXI@Z; DynPack::`vector deleting destructor'(uint)
0x1400d30d5  jmp     short loc_1400D314C
0x1400d30d7  xor     edi, edi
0x1400d30d9  lea     r9d, [rdi+57h]
0x1400d30dd  mov     ebx, r9d
0x1400d30e0  lea     rcx, WPP_GLOBAL_Control
0x1400d30e7  mov     rax, cs:WPP_GLOBAL_Control
0x1400d30ee  cmp     rax, rcx
0x1400d30f1  jz      short loc_1400D314C
0x1400d30f3  test    byte ptr [rax+1Ch], 8
0x1400d30f7  jz      short loc_1400D314C
0x1400d30f9  lea     edx, [rdi+19h]
0x1400d30fc  lea     rcx, aPmwszcriticalv; "pmwszCriticalVolumes"
0x1400d3103  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rcx
0x1400d3108  jmp     short loc_1400D313C
0x1400d310a  mov     r9d, 57h ; 'W'
0x1400d3110  mov     ebx, r9d
0x1400d3113  lea     rcx, WPP_GLOBAL_Control
0x1400d311a  mov     rax, cs:WPP_GLOBAL_Control
0x1400d3121  cmp     rax, rcx
0x1400d3124  jz      short loc_1400D314C
0x1400d3126  test    byte ptr [rax+1Ch], 8
0x1400d312a  jz      short loc_1400D314C
0x1400d312c  lea     edx, [r9-3Fh]
0x1400d3130  lea     r8, aPasrsys; "pAsrSys"
0x1400d3137  mov     qword ptr [rsp+2C8h+dwCreationDisposition], r8
0x1400d313c  mov     rcx, [rax+10h]
0x1400d3140  lea     r8, WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids
0x1400d3147  call    WPP_SF_Ds
0x1400d314c  mov     rcx, r12; pv
0x1400d314f  call    cs:__imp_CoTaskMemFree
0x1400d3155  lea     rcx, aAsrldmInitiali; "AsrLdm::InitializeForBackup"
0x1400d315c  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400d3161  mov     ecx, ebx; dwErrCode
0x1400d3163  call    cs:__imp_SetLastError
0x1400d3169  mov     eax, edi
0x1400d316b  mov     rcx, [rsp+2C8h+var_58]
0x1400d3173  xor     rcx, rsp; StackCookie
0x1400d3176  call    __security_check_cookie
0x1400d317b  add     rsp, 288h
0x1400d3182  pop     r15
0x1400d3184  pop     r14
0x1400d3186  pop     r13
0x1400d3188  pop     r12
0x1400d318a  pop     rdi
0x1400d318b  pop     rsi
0x1400d318c  pop     rbp
0x1400d318d  pop     rbx
0x1400d318e  retn
```
