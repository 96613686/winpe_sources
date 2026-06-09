# DrvCreatePhysicalMonitorObjects

- ea: `0x14017f960`
- end: `0x14017fdad`
- name: `DrvCreatePhysicalMonitorObjects`
- size: `1101`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, enum _MODE@<edx>, int, volatile void *, volatile void *Address)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x14017f8f0`

## callees

- `0x140013b20`
- `0x140014008`
- `0x14001983c`
- `0x14007ab04`
- `0x14007b930`
- `0x1400d31b8`
- `0x1400d4290`
- `0x1400d4c1c`
- `0x140150adc`
- `0x14017f960`
- `0x14018d7ac`
- `0x1402389c0`
- `0x1402bb310`
- `0x1402bb358`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14017fbf7`
- `ntoskrnl!ProbeForWrite` at `0x14017fc13`
- `ntoskrnl!ProbeForWrite` at `0x14017fbf7`
- `ntoskrnl!ProbeForWrite` at `0x14017fc13`
- `watchdog!WdLogSingleEntry4` at `0x14017f99e`
- `watchdog!WdLogSingleEntry4` at `0x14017f99e`
- `watchdog!WdLogSingleEntry0` at `0x14017fd71`
- `watchdog!WdLogSingleEntry0` at `0x14017fd71`
- `watchdog!WdLogSingleEntry1` at `0x14017f9db`
- `watchdog!WdLogSingleEntry1` at `0x14017fd3f`
- `watchdog!WdLogSingleEntry1` at `0x14017f9db`
- `watchdog!WdLogSingleEntry1` at `0x14017fd3f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017faf4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017fcc4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017fcf4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017faf4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017fcc4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017fcf4`

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
0x14017f960  mov     [rsp+arg_0], rbx
0x14017f965  mov     [rsp+arg_18], r9d
0x14017f96a  mov     [rsp+arg_10], r8d
0x14017f96f  push    rdi
0x14017f970  push    r12
0x14017f972  push    r13
0x14017f974  push    r14
0x14017f976  push    r15
0x14017f978  sub     rsp, 90h
0x14017f97f  movsxd  r8, r8d
0x14017f982  mov     ebx, edx
0x14017f984  mov     rdi, rcx
0x14017f987  mov     ecx, [rsp+0B8h+arg_20]
0x14017f98e  movsxd  r9, r9d
0x14017f991  mov     [rsp+0B8h+var_98], rcx
0x14017f996  mov     rdx, rdi
0x14017f999  mov     ecx, 4
0x14017f99e  call    cs:__imp_WdLogSingleEntry4
0x14017f9a5  nop     dword ptr [rax+rax+00h]
0x14017f9aa  mov     cs:WdLogGlobalForLineNumber, 6702h
0x14017f9b4  mov     [rsp+0B8h+var_80], 0
0x14017f9bd  lea     r8, [rsp+0B8h+var_80]; struct tagGRAPHICS_DEVICE **
0x14017f9c2  mov     edx, ebx; enum _MODE
0x14017f9c4  mov     rcx, rdi; struct _UNICODE_STRING *
0x14017f9c7  call    ?DrvGetDeviceFromNameAndValidateDevice@@YAJPEAU_UNICODE_STRING@@W4_MODE@@PEAPEAUtagGRAPHICS_DEVICE@@@Z; DrvGetDeviceFromNameAndValidateDevice(_UNICODE_STRING *,_MODE,tagGRAPHICS_DEVICE * *)
0x14017f9cc  movsxd  rbx, eax
0x14017f9cf  test    eax, eax
0x14017f9d1  jns     short loc_14017F9F8
0x14017f9d3  mov     rdx, rbx
0x14017f9d6  mov     ecx, 5
0x14017f9db  call    cs:__imp_WdLogSingleEntry1
0x14017f9e2  nop     dword ptr [rax+rax+00h]
0x14017f9e7  mov     cs:WdLogGlobalForLineNumber, 670Ch
0x14017f9f1  mov     eax, ebx
0x14017f9f3  jmp     loc_14017FD93
0x14017f9f8  xor     r15d, r15d
0x14017f9fb  mov     [rsp+0B8h+var_78], r15d
0x14017fa00  xor     edi, edi
0x14017fa02  mov     [rsp+0B8h+var_40], edi
0x14017fa06  mov     [rsp+0B8h+var_38], rdi
0x14017fa0e  mov     rdx, [rsp+0B8h+var_80]; struct tagGRAPHICS_DEVICE *
0x14017fa13  lea     rcx, [rsp+0B8h+var_48]; this
0x14017fa18  call    ?UpdateMonitorDevicesOnGraphicsDevice@EnsureMonitorDevices@@AEAAXPEAUtagGRAPHICS_DEVICE@@@Z; EnsureMonitorDevices::UpdateMonitorDevicesOnGraphicsDevice(tagGRAPHICS_DEVICE *)
0x14017fa1d  mov     dword ptr [rsp+0B8h+var_80], edi
0x14017fa21  lea     rdx, [rsp+0B8h+var_80]; unsigned int *
0x14017fa26  lea     rcx, [rsp+0B8h+var_48]; this
0x14017fa2b  call    ?DrvGetNumberOfPhysicalMonitors@@YAJAEAVEnsureMonitorDevices@@PEAK@Z; DrvGetNumberOfPhysicalMonitors(EnsureMonitorDevices &,ulong *)
0x14017fa30  mov     ebx, eax
0x14017fa32  mov     [rsp+0B8h+var_88], eax
0x14017fa36  test    eax, eax
0x14017fa38  js      loc_14017FC8E
0x14017fa3e  mov     r12d, dword ptr [rsp+0B8h+var_80]
0x14017fa43  cmp     [rsp+0B8h+arg_20], r12d
0x14017fa4b  jnb     short loc_14017FA5B
0x14017fa4d  mov     ebx, 0C01E05E6h
0x14017fa52  mov     [rsp+0B8h+var_88], ebx
0x14017fa56  jmp     loc_14017FC96
0x14017fa5b  mov     rcx, r12
0x14017fa5e  shl     rcx, 3
0x14017fa62  mov     ebx, 0FFFFFFFFh
0x14017fa67  cmp     rcx, rbx
0x14017fa6a  ja      loc_14017FC85
0x14017fa70  mov     edx, 76646747h
0x14017fa75  call    PALLOCMEM
0x14017fa7a  mov     rdi, rax
0x14017fa7d  mov     [rsp+0B8h+var_30], rax
0x14017fa85  test    rax, rax
0x14017fa88  jnz     short loc_14017FA91
0x14017fa8a  mov     ebx, 0C0000017h
0x14017fa8f  jmp     short loc_14017FA52
0x14017fa91  xor     r14d, r14d
0x14017fa94  xor     r13d, r13d
0x14017fa97  cmp     r14d, [rsp+0B8h+var_40]
0x14017fa9c  jnb     loc_14017FBAD
0x14017faa2  xorps   xmm0, xmm0
0x14017faa5  xor     eax, eax
0x14017faa7  movups  xmmword ptr [rsp+0B8h+var_60], xmm0
0x14017faac  mov     [rsp+0B8h+var_50], eax
0x14017fab0  lea     r8, [rsp+0B8h+var_60]; struct tagVIDEO_MONITOR_DEVICE *
0x14017fab5  mov     edx, r14d; unsigned int
0x14017fab8  lea     rcx, [rsp+0B8h+var_48]; this
0x14017fabd  call    ?GetMonitorDevice@EnsureMonitorDevices@@QEBAXKAEAUtagVIDEO_MONITOR_DEVICE@@@Z; EnsureMonitorDevices::GetMonitorDevice(ulong,tagVIDEO_MONITOR_DEVICE &)
0x14017fac2  mov     r8, qword ptr [rsp+0B8h+var_60+8]
0x14017fac7  mov     qword ptr [rsp+0B8h+var_68.LowPart], r8
0x14017facc  test    byte ptr [rsp+0B8h+var_60], 1
0x14017fad1  jz      loc_14017FB9B
0x14017fad7  cmp     r15d, r12d
0x14017fada  jz      loc_14017FBA3
0x14017fae0  mov     ecx, [rsp+0B8h+arg_10]
0x14017fae7  test    ecx, ecx
0x14017fae9  jz      short loc_14017FB4F
0x14017faeb  cmp     ecx, 1
0x14017faee  jnz     loc_14017FBA3
0x14017faf4  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14017fafb  nop     dword ptr [rax+rax+00h]
0x14017fb00  mov     rcx, [rax+18h]
0x14017fb04  mov     rax, [rcx+400h]
0x14017fb0b  test    rax, rax
0x14017fb0e  jz      short loc_14017FB1D
0x14017fb10  call    _guard_dispatch_icall
0x14017fb15  mov     ebx, eax
0x14017fb17  mov     [rsp+0B8h+var_88], eax
0x14017fb1b  jmp     short loc_14017FB26
0x14017fb1d  mov     ebx, 0C00000BBh
0x14017fb22  mov     [rsp+0B8h+var_88], ebx
0x14017fb26  test    ebx, ebx
0x14017fb28  js      loc_14017FC96
0x14017fb2e  lea     r8, [rdi+r13*8]
0x14017fb32  mov     edx, [rsp+0B8h+var_60+4]
0x14017fb36  lea     rcx, [rsp+0B8h+var_68]
0x14017fb3b  call    CreatePhysicalMonitorWrap
0x14017fb40  mov     ebx, eax
0x14017fb42  mov     [rsp+0B8h+var_88], eax
0x14017fb46  test    eax, eax
0x14017fb48  jns     short loc_14017FB90
0x14017fb4a  jmp     loc_14017FC96
0x14017fb4f  mov     dword ptr [rsp+0B8h+var_80], 0
0x14017fb57  lea     r9, [rdi+r13*8]; void **
0x14017fb5b  lea     rax, [rsp+0B8h+var_80]
0x14017fb60  mov     [rsp+0B8h+var_98], rax; int *
0x14017fb65  mov     r8d, [rsp+0B8h+var_60+4]; unsigned int
0x14017fb6a  lea     rdx, [rsp+0B8h+var_68]; struct _LUID *
0x14017fb6f  mov     ecx, [rsp+0B8h+arg_18]; enum _DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
0x14017fb76  call    ?OPMCreateProtectedOutput@@YAJW4_DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS@@AEAU_LUID@@KPEAPEAXPEAH@Z; OPMCreateProtectedOutput(_DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS,_LUID &,ulong,void * *,int *)
0x14017fb7b  mov     ebx, eax
0x14017fb7d  mov     [rsp+0B8h+var_88], eax
0x14017fb81  test    eax, eax
0x14017fb83  js      loc_14017FC8E
0x14017fb89  cmp     dword ptr [rsp+0B8h+var_80], 0
0x14017fb8e  jnz     short loc_14017FB9B
0x14017fb90  inc     r13d
0x14017fb93  inc     r15d
0x14017fb96  mov     [rsp+0B8h+var_78], r15d
0x14017fb9b  inc     r14d
0x14017fb9e  jmp     loc_14017FA97
0x14017fba3  mov     ebx, 0C01E05E7h
0x14017fba8  jmp     loc_14017FA52
0x14017fbad  mov     eax, [rsp+0B8h+arg_20]
0x14017fbb4  shl     rax, 3
0x14017fbb8  mov     ebx, 0FFFFFFFFh
0x14017fbbd  cmp     rax, rbx
0x14017fbc0  mov     ecx, eax
0x14017fbc2  jbe     short loc_14017FBC6
0x14017fbc4  mov     ecx, ebx
0x14017fbc6  cmp     rbx, rax
0x14017fbc9  sbb     ebx, ebx
0x14017fbcb  and     ebx, 0C0000095h
0x14017fbd1  mov     [rsp+0B8h+var_88], ebx
0x14017fbd5  mov     r8d, 0FFFFFFFFh
0x14017fbdb  cmp     rax, r8
0x14017fbde  ja      loc_14017FC8E
0x14017fbe4  mov     edx, ecx; Length
0x14017fbe6  mov     r8d, 8; Alignment
0x14017fbec  mov     r12, [rsp+0B8h+Address]
0x14017fbf4  mov     rcx, r12; Address
0x14017fbf7  call    cs:__imp_ProbeForWrite
0x14017fbfe  nop     dword ptr [rax+rax+00h]
0x14017fc03  mov     edx, 4; Length
0x14017fc08  mov     r8d, edx; Alignment
0x14017fc0b  mov     rcx, [rsp+0B8h+arg_28]; Address
0x14017fc13  call    cs:__imp_ProbeForWrite
0x14017fc1a  nop     dword ptr [rax+rax+00h]
0x14017fc1f  cmp     r15d, [rsp+0B8h+arg_20]
0x14017fc27  ja      short loc_14017FC5A
0x14017fc29  xor     r14d, r14d
0x14017fc2c  mov     [rsp+0B8h+var_74], r14d
0x14017fc31  cmp     r14d, r15d
0x14017fc34  jnb     short loc_14017FC48
0x14017fc36  lea     rcx, [r12+r14*8]
0x14017fc3a  mov     rdx, [rdi+r14*8]
0x14017fc3e  call    RtlWriteULong64ToUser
0x14017fc43  inc     r14d
0x14017fc46  jmp     short loc_14017FC2C
0x14017fc48  mov     edx, r15d
0x14017fc4b  mov     rcx, [rsp+0B8h+arg_28]
0x14017fc53  call    RtlWriteULongToUser
0x14017fc58  jmp     short loc_14017FC8E
0x14017fc5a  mov     ebx, 0C01E05E6h
0x14017fc5f  mov     [rsp+0B8h+var_88], ebx
0x14017fc63  mov     [rsp+0B8h+var_70], ebx
0x14017fc67  jmp     short loc_14017FC8E
0x14017fc69  mov     ebx, 0C01E05E4h
0x14017fc6e  mov     [rsp+0B8h+var_88], ebx
0x14017fc72  mov     [rsp+0B8h+var_70], ebx
0x14017fc76  mov     r15d, [rsp+0B8h+var_78]
0x14017fc7b  mov     rdi, [rsp+0B8h+var_30]
0x14017fc83  jmp     short loc_14017FC8E
0x14017fc85  mov     ebx, 0C0000095h
0x14017fc8a  mov     [rsp+0B8h+var_88], ebx
0x14017fc8e  test    ebx, ebx
0x14017fc90  jns     loc_14017FD64
0x14017fc96  test    rdi, rdi
0x14017fc99  jz      loc_14017FD37
0x14017fc9f  test    r15d, r15d
0x14017fca2  jz      loc_14017FD2F
0x14017fca8  xor     r14d, r14d
0x14017fcab  mov     ebx, [rsp+0B8h+arg_10]
0x14017fcb2  mov     rcx, [rdi+r14*8]; void *
0x14017fcb6  call    ?OPMDestroyProtectedOutput@@YAJPEAX@Z; OPMDestroyProtectedOutput(void *)
0x14017fcbb  test    ebx, ebx
0x14017fcbd  jz      short loc_14017FD1A
0x14017fcbf  cmp     ebx, 1
0x14017fcc2  jnz     short loc_14017FD23
0x14017fcc4  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14017fccb  nop     dword ptr [rax+rax+00h]
0x14017fcd0  mov     rcx, [rax+18h]
0x14017fcd4  mov     rax, [rcx+410h]
0x14017fcdb  test    rax, rax
0x14017fcde  jz      short loc_14017FCE7
0x14017fce0  call    _guard_dispatch_icall
0x14017fce5  jmp     short loc_14017FCEC
0x14017fce7  mov     eax, 0C00000BBh
0x14017fcec  test    eax, eax
0x14017fcee  js      short loc_14017FD23
0x14017fcf0  mov     r12, [rdi+r14*8]
0x14017fcf4  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14017fcfb  nop     dword ptr [rax+rax+00h]
0x14017fd00  mov     rdx, [rax+18h]
0x14017fd04  mov     rax, [rdx+418h]
0x14017fd0b  test    rax, rax
0x14017fd0e  jz      short loc_14017FD23
0x14017fd10  mov     rcx, r12
0x14017fd13  call    _guard_dispatch_icall
0x14017fd18  jmp     short loc_14017FD23
0x14017fd1a  mov     rcx, [rdi+r14*8]; void *
0x14017fd1e  call    ?OPMDestroyProtectedOutput@@YAJPEAX@Z; OPMDestroyProtectedOutput(void *)
0x14017fd23  inc     r14d
0x14017fd26  cmp     r14d, r15d
0x14017fd29  jb      short loc_14017FCB2
0x14017fd2b  mov     ebx, [rsp+0B8h+var_88]
0x14017fd2f  mov     rcx, rdi; Buffer
0x14017fd32  call    GreDeleteFastMutex
0x14017fd37  movsxd  rdx, ebx
0x14017fd3a  mov     ecx, 5
0x14017fd3f  call    cs:__imp_WdLogSingleEntry1
0x14017fd46  nop     dword ptr [rax+rax+00h]
0x14017fd4b  mov     cs:WdLogGlobalForLineNumber, 67B5h
0x14017fd55  lea     rcx, [rsp+0B8h+var_48]; this
0x14017fd5a  call    ??1EnsureMonitorDevices@@QEAA@XZ; EnsureMonitorDevices::~EnsureMonitorDevices(void)
0x14017fd5f  jmp     loc_14017F9F1
0x14017fd64  mov     rcx, rdi; Buffer
0x14017fd67  call    GreDeleteFastMutex
0x14017fd6c  mov     ecx, 5
0x14017fd71  call    cs:__imp_WdLogSingleEntry0
0x14017fd78  nop     dword ptr [rax+rax+00h]
0x14017fd7d  mov     cs:WdLogGlobalForLineNumber, 67BBh
0x14017fd87  lea     rcx, [rsp+0B8h+var_48]; this
0x14017fd8c  call    ??1EnsureMonitorDevices@@QEAA@XZ; EnsureMonitorDevices::~EnsureMonitorDevices(void)
0x14017fd91  xor     eax, eax
0x14017fd93  mov     rbx, [rsp+0B8h+arg_0]
0x14017fd9b  add     rsp, 90h
0x14017fda2  pop     r15
0x14017fda4  pop     r14
0x14017fda6  pop     r13
0x14017fda8  pop     r12
0x14017fdaa  pop     rdi
0x14017fdab  retn
```
