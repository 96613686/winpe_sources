# DrvCreatePhysicalMonitorObjects

- ea: `0x14017dd20`
- end: `0x14017e16d`
- name: `DrvCreatePhysicalMonitorObjects`
- size: `1101`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, enum _MODE@<edx>, int, volatile void *, volatile void *Address)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x14017dcb0`

## callees

- `0x14002eaec`
- `0x1400492a4`
- `0x14004a0d0`
- `0x1400a98a8`
- `0x1400aa980`
- `0x1400ab30c`
- `0x1400da840`
- `0x1400dacb0`
- `0x14014e92c`
- `0x14017dd20`
- `0x14018bedc`
- `0x140238240`
- `0x1402bb310`
- `0x1402bb358`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14017dfb7`
- `ntoskrnl!ProbeForWrite` at `0x14017dfd3`
- `ntoskrnl!ProbeForWrite` at `0x14017dfb7`
- `ntoskrnl!ProbeForWrite` at `0x14017dfd3`
- `watchdog!WdLogSingleEntry4` at `0x14017dd5e`
- `watchdog!WdLogSingleEntry4` at `0x14017dd5e`
- `watchdog!WdLogSingleEntry0` at `0x14017e131`
- `watchdog!WdLogSingleEntry0` at `0x14017e131`
- `watchdog!WdLogSingleEntry1` at `0x14017dd9b`
- `watchdog!WdLogSingleEntry1` at `0x14017e0ff`
- `watchdog!WdLogSingleEntry1` at `0x14017dd9b`
- `watchdog!WdLogSingleEntry1` at `0x14017e0ff`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017deb4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017e084`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017e0b4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017deb4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017e084`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017e0b4`

## pseudocode

```c
__int64 __fastcall DrvCreatePhysicalMonitorObjects(
        struct _UNICODE_STRING *a1,
        enum _MODE a2,
        int a3,
        enum _DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS a4,
        unsigned int a5,
        volatile void *a6,
        char *Address)
{
  int DeviceFromNameAndValidateDevice; // eax
  signed int NumberOfPhysicalMonitors; // ebx
  unsigned int v12; // r15d
  void **v13; // rdi
  int v14; // r12d
  unsigned int v15; // r14d
  __int64 v16; // r13
  __int64 v17; // rdx
  __int64 (*v18)(void); // rax
  unsigned __int64 v19; // rax
  unsigned int v20; // ecx
  __int64 i; // r14
  __int64 v22; // r14
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 (*v27)(void); // rax
  int v28; // eax
  void *v29; // r12
  void (__fastcall *v30)(void *); // rax
  int v31; // [rsp+30h] [rbp-88h]
  struct tagGRAPHICS_DEVICE *v32; // [rsp+38h] [rbp-80h] BYREF
  unsigned int v33; // [rsp+40h] [rbp-78h]
  int v34; // [rsp+44h] [rbp-74h]
  int v35; // [rsp+48h] [rbp-70h]
  struct _LUID v36; // [rsp+50h] [rbp-68h] BYREF
  unsigned int v37[4]; // [rsp+58h] [rbp-60h] BYREF
  int v38; // [rsp+68h] [rbp-50h]
  char v39[8]; // [rsp+70h] [rbp-48h] BYREF
  unsigned int v40; // [rsp+78h] [rbp-40h]
  __int64 v41; // [rsp+80h] [rbp-38h]
  void **v42; // [rsp+88h] [rbp-30h]

  WdLogSingleEntry4(4, a1, a3, a4, a5);
  WdLogGlobalForLineNumber = 26370;
  v32 = 0;
  DeviceFromNameAndValidateDevice = DrvGetDeviceFromNameAndValidateDevice(a1, a2, &v32);
  NumberOfPhysicalMonitors = DeviceFromNameAndValidateDevice;
  if ( DeviceFromNameAndValidateDevice < 0 )
  {
    WdLogSingleEntry1(5, DeviceFromNameAndValidateDevice);
    WdLogGlobalForLineNumber = 26380;
    return (unsigned int)NumberOfPhysicalMonitors;
  }
  v12 = 0;
  v33 = 0;
  v13 = 0;
  v40 = 0;
  v41 = 0;
  EnsureMonitorDevices::UpdateMonitorDevicesOnGraphicsDevice((EnsureMonitorDevices *)v39, v32);
  LODWORD(v32) = 0;
  NumberOfPhysicalMonitors = DrvGetNumberOfPhysicalMonitors((struct EnsureMonitorDevices *)v39, (unsigned int *)&v32);
  v31 = NumberOfPhysicalMonitors;
  if ( NumberOfPhysicalMonitors < 0 )
    goto LABEL_38;
  v14 = (int)v32;
  if ( a5 < (unsigned int)v32 )
  {
    NumberOfPhysicalMonitors = -1071774234;
LABEL_7:
    v31 = NumberOfPhysicalMonitors;
    goto LABEL_39;
  }
  if ( 8 * (unsigned __int64)(unsigned int)v32 > 0xFFFFFFFF )
  {
    NumberOfPhysicalMonitors = -1073741675;
    v31 = -1073741675;
    goto LABEL_38;
  }
  v13 = (void **)PALLOCMEM(8LL * (unsigned int)v32, 1986291527);
  v42 = v13;
  if ( !v13 )
  {
    NumberOfPhysicalMonitors = -1073741801;
    goto LABEL_7;
  }
  v15 = 0;
  v16 = 0;
  while ( v15 < v40 )
  {
    *(_OWORD *)v37 = 0;
    v38 = 0;
    EnsureMonitorDevices::GetMonitorDevice((EnsureMonitorDevices *)v39, v15, (struct tagVIDEO_MONITOR_DEVICE *)v37);
    v36 = *(struct _LUID *)&v37[2];
    if ( (v37[0] & 1) == 0 )
      goto LABEL_26;
    if ( v12 == v14 )
      goto LABEL_27;
    if ( a3 )
    {
      if ( a3 != 1 )
      {
LABEL_27:
        NumberOfPhysicalMonitors = -1071774233;
        goto LABEL_7;
      }
      v18 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(1, v17) + 24) + 1024LL);
      if ( v18 )
      {
        NumberOfPhysicalMonitors = v18();
        v31 = NumberOfPhysicalMonitors;
      }
      else
      {
        NumberOfPhysicalMonitors = -1073741637;
        v31 = -1073741637;
      }
      if ( NumberOfPhysicalMonitors < 0 )
        goto LABEL_39;
      NumberOfPhysicalMonitors = CreatePhysicalMonitorWrap(&v36, v37[1], &v13[v16]);
      v31 = NumberOfPhysicalMonitors;
      if ( NumberOfPhysicalMonitors < 0 )
        goto LABEL_39;
LABEL_25:
      v16 = (unsigned int)(v16 + 1);
      v33 = ++v12;
      goto LABEL_26;
    }
    LODWORD(v32) = 0;
    NumberOfPhysicalMonitors = OPMCreateProtectedOutput(a4, &v36, v37[1], &v13[v16], (int *)&v32);
    v31 = NumberOfPhysicalMonitors;
    if ( NumberOfPhysicalMonitors < 0 )
      goto LABEL_38;
    if ( !(_DWORD)v32 )
      goto LABEL_25;
LABEL_26:
    ++v15;
  }
  v19 = 8LL * a5;
  v20 = 8 * a5;
  if ( v19 > 0xFFFFFFFF )
    v20 = -1;
  NumberOfPhysicalMonitors = v19 > 0xFFFFFFFF ? 0xC0000095 : 0;
  v31 = NumberOfPhysicalMonitors;
  if ( v19 <= 0xFFFFFFFF )
  {
    ProbeForWrite(Address, v20, 8u);
    ProbeForWrite(a6, 4u, 4u);
    if ( v12 > a5 )
    {
      NumberOfPhysicalMonitors = -1071774234;
      v31 = -1071774234;
      v35 = -1071774234;
    }
    else
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v34 = i;
        if ( (unsigned int)i >= v12 )
          break;
        RtlWriteULong64ToUser(&Address[8 * i], v13[i]);
      }
      RtlWriteULongToUser(a6, v12);
    }
  }
LABEL_38:
  if ( NumberOfPhysicalMonitors >= 0 )
  {
    GreDeleteFastMutex(v13);
    WdLogSingleEntry0(5);
    WdLogGlobalForLineNumber = 26555;
    EnsureMonitorDevices::~EnsureMonitorDevices((EnsureMonitorDevices *)v39);
    return 0;
  }
  else
  {
LABEL_39:
    if ( v13 )
    {
      if ( v12 )
      {
        v22 = 0;
        do
        {
          OPMDestroyProtectedOutput(v13[v22]);
          if ( a3 )
          {
            if ( a3 == 1 )
            {
              v26 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v24, v23) + 24);
              v27 = *(__int64 (**)(void))(v26 + 1040);
              if ( v27 )
                v28 = v27();
              else
                v28 = -1073741637;
              if ( v28 >= 0 )
              {
                v29 = v13[v22];
                v30 = *(void (__fastcall **)(void *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v26, v25) + 24) + 1048LL);
                if ( v30 )
                  v30(v29);
              }
            }
          }
          else
          {
            OPMDestroyProtectedOutput(v13[v22]);
          }
          v22 = (unsigned int)(v22 + 1);
        }
        while ( (unsigned int)v22 < v12 );
        NumberOfPhysicalMonitors = v31;
      }
      GreDeleteFastMutex(v13);
    }
    WdLogSingleEntry1(5, NumberOfPhysicalMonitors);
    WdLogGlobalForLineNumber = 26549;
    EnsureMonitorDevices::~EnsureMonitorDevices((EnsureMonitorDevices *)v39);
    return (unsigned int)NumberOfPhysicalMonitors;
  }
}

```

## disassembly

```asm
0x14017dd20  mov     [rsp+arg_0], rbx
0x14017dd25  mov     [rsp+arg_18], r9d
0x14017dd2a  mov     [rsp+arg_10], r8d
0x14017dd2f  push    rdi
0x14017dd30  push    r12
0x14017dd32  push    r13
0x14017dd34  push    r14
0x14017dd36  push    r15
0x14017dd38  sub     rsp, 90h
0x14017dd3f  movsxd  r8, r8d
0x14017dd42  mov     ebx, edx
0x14017dd44  mov     rdi, rcx
0x14017dd47  mov     ecx, [rsp+0B8h+arg_20]
0x14017dd4e  movsxd  r9, r9d
0x14017dd51  mov     [rsp+0B8h+var_98], rcx
0x14017dd56  mov     rdx, rdi
0x14017dd59  mov     ecx, 4
0x14017dd5e  call    cs:__imp_WdLogSingleEntry4
0x14017dd65  nop     dword ptr [rax+rax+00h]
0x14017dd6a  mov     cs:WdLogGlobalForLineNumber, 6702h
0x14017dd74  mov     [rsp+0B8h+var_80], 0
0x14017dd7d  lea     r8, [rsp+0B8h+var_80]; struct tagGRAPHICS_DEVICE **
0x14017dd82  mov     edx, ebx; enum _MODE
0x14017dd84  mov     rcx, rdi; struct _UNICODE_STRING *
0x14017dd87  call    ?DrvGetDeviceFromNameAndValidateDevice@@YAJPEAU_UNICODE_STRING@@W4_MODE@@PEAPEAUtagGRAPHICS_DEVICE@@@Z; DrvGetDeviceFromNameAndValidateDevice(_UNICODE_STRING *,_MODE,tagGRAPHICS_DEVICE * *)
0x14017dd8c  movsxd  rbx, eax
0x14017dd8f  test    eax, eax
0x14017dd91  jns     short loc_14017DDB8
0x14017dd93  mov     rdx, rbx
0x14017dd96  mov     ecx, 5
0x14017dd9b  call    cs:__imp_WdLogSingleEntry1
0x14017dda2  nop     dword ptr [rax+rax+00h]
0x14017dda7  mov     cs:WdLogGlobalForLineNumber, 670Ch
0x14017ddb1  mov     eax, ebx
0x14017ddb3  jmp     loc_14017E153
0x14017ddb8  xor     r15d, r15d
0x14017ddbb  mov     [rsp+0B8h+var_78], r15d
0x14017ddc0  xor     edi, edi
0x14017ddc2  mov     [rsp+0B8h+var_40], edi
0x14017ddc6  mov     [rsp+0B8h+var_38], rdi
0x14017ddce  mov     rdx, [rsp+0B8h+var_80]; struct tagGRAPHICS_DEVICE *
0x14017ddd3  lea     rcx, [rsp+0B8h+var_48]; this
0x14017ddd8  call    ?UpdateMonitorDevicesOnGraphicsDevice@EnsureMonitorDevices@@AEAAXPEAUtagGRAPHICS_DEVICE@@@Z; EnsureMonitorDevices::UpdateMonitorDevicesOnGraphicsDevice(tagGRAPHICS_DEVICE *)
0x14017dddd  mov     dword ptr [rsp+0B8h+var_80], edi
0x14017dde1  lea     rdx, [rsp+0B8h+var_80]; unsigned int *
0x14017dde6  lea     rcx, [rsp+0B8h+var_48]; this
0x14017ddeb  call    ?DrvGetNumberOfPhysicalMonitors@@YAJAEAVEnsureMonitorDevices@@PEAK@Z; DrvGetNumberOfPhysicalMonitors(EnsureMonitorDevices &,ulong *)
0x14017ddf0  mov     ebx, eax
0x14017ddf2  mov     [rsp+0B8h+var_88], eax
0x14017ddf6  test    eax, eax
0x14017ddf8  js      loc_14017E04E
0x14017ddfe  mov     r12d, dword ptr [rsp+0B8h+var_80]
0x14017de03  cmp     [rsp+0B8h+arg_20], r12d
0x14017de0b  jnb     short loc_14017DE1B
0x14017de0d  mov     ebx, 0C01E05E6h
0x14017de12  mov     [rsp+0B8h+var_88], ebx
0x14017de16  jmp     loc_14017E056
0x14017de1b  mov     rcx, r12
0x14017de1e  shl     rcx, 3
0x14017de22  mov     ebx, 0FFFFFFFFh
0x14017de27  cmp     rcx, rbx
0x14017de2a  ja      loc_14017E045
0x14017de30  mov     edx, 76646747h
0x14017de35  call    PALLOCMEM
0x14017de3a  mov     rdi, rax
0x14017de3d  mov     [rsp+0B8h+var_30], rax
0x14017de45  test    rax, rax
0x14017de48  jnz     short loc_14017DE51
0x14017de4a  mov     ebx, 0C0000017h
0x14017de4f  jmp     short loc_14017DE12
0x14017de51  xor     r14d, r14d
0x14017de54  xor     r13d, r13d
0x14017de57  cmp     r14d, [rsp+0B8h+var_40]
0x14017de5c  jnb     loc_14017DF6D
0x14017de62  xorps   xmm0, xmm0
0x14017de65  xor     eax, eax
0x14017de67  movups  xmmword ptr [rsp+0B8h+var_60], xmm0
0x14017de6c  mov     [rsp+0B8h+var_50], eax
0x14017de70  lea     r8, [rsp+0B8h+var_60]; struct tagVIDEO_MONITOR_DEVICE *
0x14017de75  mov     edx, r14d; unsigned int
0x14017de78  lea     rcx, [rsp+0B8h+var_48]; this
0x14017de7d  call    ?GetMonitorDevice@EnsureMonitorDevices@@QEBAXKAEAUtagVIDEO_MONITOR_DEVICE@@@Z; EnsureMonitorDevices::GetMonitorDevice(ulong,tagVIDEO_MONITOR_DEVICE &)
0x14017de82  mov     r8, qword ptr [rsp+0B8h+var_60+8]
0x14017de87  mov     qword ptr [rsp+0B8h+var_68.LowPart], r8
0x14017de8c  test    byte ptr [rsp+0B8h+var_60], 1
0x14017de91  jz      loc_14017DF5B
0x14017de97  cmp     r15d, r12d
0x14017de9a  jz      loc_14017DF63
0x14017dea0  mov     ecx, [rsp+0B8h+arg_10]
0x14017dea7  test    ecx, ecx
0x14017dea9  jz      short loc_14017DF0F
0x14017deab  cmp     ecx, 1
0x14017deae  jnz     loc_14017DF63
0x14017deb4  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14017debb  nop     dword ptr [rax+rax+00h]
0x14017dec0  mov     rcx, [rax+18h]
0x14017dec4  mov     rax, [rcx+400h]
0x14017decb  test    rax, rax
0x14017dece  jz      short loc_14017DEDD
0x14017ded0  call    _guard_dispatch_icall
0x14017ded5  mov     ebx, eax
0x14017ded7  mov     [rsp+0B8h+var_88], eax
0x14017dedb  jmp     short loc_14017DEE6
0x14017dedd  mov     ebx, 0C00000BBh
0x14017dee2  mov     [rsp+0B8h+var_88], ebx
0x14017dee6  test    ebx, ebx
0x14017dee8  js      loc_14017E056
0x14017deee  lea     r8, [rdi+r13*8]
0x14017def2  mov     edx, [rsp+0B8h+var_60+4]
0x14017def6  lea     rcx, [rsp+0B8h+var_68]
0x14017defb  call    CreatePhysicalMonitorWrap
0x14017df00  mov     ebx, eax
0x14017df02  mov     [rsp+0B8h+var_88], eax
0x14017df06  test    eax, eax
0x14017df08  jns     short loc_14017DF50
0x14017df0a  jmp     loc_14017E056
0x14017df0f  mov     dword ptr [rsp+0B8h+var_80], 0
0x14017df17  lea     r9, [rdi+r13*8]; void **
0x14017df1b  lea     rax, [rsp+0B8h+var_80]
0x14017df20  mov     [rsp+0B8h+var_98], rax; int *
0x14017df25  mov     r8d, [rsp+0B8h+var_60+4]; unsigned int
0x14017df2a  lea     rdx, [rsp+0B8h+var_68]; struct _LUID *
0x14017df2f  mov     ecx, [rsp+0B8h+arg_18]; enum _DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
0x14017df36  call    ?OPMCreateProtectedOutput@@YAJW4_DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS@@AEAU_LUID@@KPEAPEAXPEAH@Z; OPMCreateProtectedOutput(_DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS,_LUID &,ulong,void * *,int *)
0x14017df3b  mov     ebx, eax
0x14017df3d  mov     [rsp+0B8h+var_88], eax
0x14017df41  test    eax, eax
0x14017df43  js      loc_14017E04E
0x14017df49  cmp     dword ptr [rsp+0B8h+var_80], 0
0x14017df4e  jnz     short loc_14017DF5B
0x14017df50  inc     r13d
0x14017df53  inc     r15d
0x14017df56  mov     [rsp+0B8h+var_78], r15d
0x14017df5b  inc     r14d
0x14017df5e  jmp     loc_14017DE57
0x14017df63  mov     ebx, 0C01E05E7h
0x14017df68  jmp     loc_14017DE12
0x14017df6d  mov     eax, [rsp+0B8h+arg_20]
0x14017df74  shl     rax, 3
0x14017df78  mov     ebx, 0FFFFFFFFh
0x14017df7d  cmp     rax, rbx
0x14017df80  mov     ecx, eax
0x14017df82  jbe     short loc_14017DF86
0x14017df84  mov     ecx, ebx
0x14017df86  cmp     rbx, rax
0x14017df89  sbb     ebx, ebx
0x14017df8b  and     ebx, 0C0000095h
0x14017df91  mov     [rsp+0B8h+var_88], ebx
0x14017df95  mov     r8d, 0FFFFFFFFh
0x14017df9b  cmp     rax, r8
0x14017df9e  ja      loc_14017E04E
0x14017dfa4  mov     edx, ecx; Length
0x14017dfa6  mov     r8d, 8; Alignment
0x14017dfac  mov     r12, [rsp+0B8h+Address]
0x14017dfb4  mov     rcx, r12; Address
0x14017dfb7  call    cs:__imp_ProbeForWrite
0x14017dfbe  nop     dword ptr [rax+rax+00h]
0x14017dfc3  mov     edx, 4; Length
0x14017dfc8  mov     r8d, edx; Alignment
0x14017dfcb  mov     rcx, [rsp+0B8h+arg_28]; Address
0x14017dfd3  call    cs:__imp_ProbeForWrite
0x14017dfda  nop     dword ptr [rax+rax+00h]
0x14017dfdf  cmp     r15d, [rsp+0B8h+arg_20]
0x14017dfe7  ja      short loc_14017E01A
0x14017dfe9  xor     r14d, r14d
0x14017dfec  mov     [rsp+0B8h+var_74], r14d
0x14017dff1  cmp     r14d, r15d
0x14017dff4  jnb     short loc_14017E008
0x14017dff6  lea     rcx, [r12+r14*8]
0x14017dffa  mov     rdx, [rdi+r14*8]
0x14017dffe  call    RtlWriteULong64ToUser
0x14017e003  inc     r14d
0x14017e006  jmp     short loc_14017DFEC
0x14017e008  mov     edx, r15d
0x14017e00b  mov     rcx, [rsp+0B8h+arg_28]
0x14017e013  call    RtlWriteULongToUser
0x14017e018  jmp     short loc_14017E04E
0x14017e01a  mov     ebx, 0C01E05E6h
0x14017e01f  mov     [rsp+0B8h+var_88], ebx
0x14017e023  mov     [rsp+0B8h+var_70], ebx
0x14017e027  jmp     short loc_14017E04E
0x14017e029  mov     ebx, 0C01E05E4h
0x14017e02e  mov     [rsp+0B8h+var_88], ebx
0x14017e032  mov     [rsp+0B8h+var_70], ebx
0x14017e036  mov     r15d, [rsp+0B8h+var_78]
0x14017e03b  mov     rdi, [rsp+0B8h+var_30]
0x14017e043  jmp     short loc_14017E04E
0x14017e045  mov     ebx, 0C0000095h
0x14017e04a  mov     [rsp+0B8h+var_88], ebx
0x14017e04e  test    ebx, ebx
0x14017e050  jns     loc_14017E124
0x14017e056  test    rdi, rdi
0x14017e059  jz      loc_14017E0F7
0x14017e05f  test    r15d, r15d
0x14017e062  jz      loc_14017E0EF
0x14017e068  xor     r14d, r14d
0x14017e06b  mov     ebx, [rsp+0B8h+arg_10]
0x14017e072  mov     rcx, [rdi+r14*8]; void *
0x14017e076  call    ?OPMDestroyProtectedOutput@@YAJPEAX@Z; OPMDestroyProtectedOutput(void *)
0x14017e07b  test    ebx, ebx
0x14017e07d  jz      short loc_14017E0DA
0x14017e07f  cmp     ebx, 1
0x14017e082  jnz     short loc_14017E0E3
0x14017e084  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14017e08b  nop     dword ptr [rax+rax+00h]
0x14017e090  mov     rcx, [rax+18h]
0x14017e094  mov     rax, [rcx+410h]
0x14017e09b  test    rax, rax
0x14017e09e  jz      short loc_14017E0A7
0x14017e0a0  call    _guard_dispatch_icall
0x14017e0a5  jmp     short loc_14017E0AC
0x14017e0a7  mov     eax, 0C00000BBh
0x14017e0ac  test    eax, eax
0x14017e0ae  js      short loc_14017E0E3
0x14017e0b0  mov     r12, [rdi+r14*8]
0x14017e0b4  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14017e0bb  nop     dword ptr [rax+rax+00h]
0x14017e0c0  mov     rdx, [rax+18h]
0x14017e0c4  mov     rax, [rdx+418h]
0x14017e0cb  test    rax, rax
0x14017e0ce  jz      short loc_14017E0E3
0x14017e0d0  mov     rcx, r12
0x14017e0d3  call    _guard_dispatch_icall
0x14017e0d8  jmp     short loc_14017E0E3
0x14017e0da  mov     rcx, [rdi+r14*8]; void *
0x14017e0de  call    ?OPMDestroyProtectedOutput@@YAJPEAX@Z; OPMDestroyProtectedOutput(void *)
0x14017e0e3  inc     r14d
0x14017e0e6  cmp     r14d, r15d
0x14017e0e9  jb      short loc_14017E072
0x14017e0eb  mov     ebx, [rsp+0B8h+var_88]
0x14017e0ef  mov     rcx, rdi; Buffer
0x14017e0f2  call    GreDeleteFastMutex
0x14017e0f7  movsxd  rdx, ebx
0x14017e0fa  mov     ecx, 5
0x14017e0ff  call    cs:__imp_WdLogSingleEntry1
0x14017e106  nop     dword ptr [rax+rax+00h]
0x14017e10b  mov     cs:WdLogGlobalForLineNumber, 67B5h
0x14017e115  lea     rcx, [rsp+0B8h+var_48]; this
0x14017e11a  call    ??1EnsureMonitorDevices@@QEAA@XZ; EnsureMonitorDevices::~EnsureMonitorDevices(void)
0x14017e11f  jmp     loc_14017DDB1
0x14017e124  mov     rcx, rdi; Buffer
0x14017e127  call    GreDeleteFastMutex
0x14017e12c  mov     ecx, 5
0x14017e131  call    cs:__imp_WdLogSingleEntry0
0x14017e138  nop     dword ptr [rax+rax+00h]
0x14017e13d  mov     cs:WdLogGlobalForLineNumber, 67BBh
0x14017e147  lea     rcx, [rsp+0B8h+var_48]; this
0x14017e14c  call    ??1EnsureMonitorDevices@@QEAA@XZ; EnsureMonitorDevices::~EnsureMonitorDevices(void)
0x14017e151  xor     eax, eax
0x14017e153  mov     rbx, [rsp+0B8h+arg_0]
0x14017e15b  add     rsp, 90h
0x14017e162  pop     r15
0x14017e164  pop     r14
0x14017e166  pop     r13
0x14017e168  pop     r12
0x14017e16a  pop     rdi
0x14017e16b  retn
```
