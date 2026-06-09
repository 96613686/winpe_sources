# SxGetDrivers(ushort const *,ushort const *,long (*)(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *),void *)

- ea: `0x180004c2c`
- end: `0x180004e19`
- name: `?SxGetDrivers@@YAJPEBG0P6AJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z1@Z`
- size: `493`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int (__high *)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *), void *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000c6e0`

## callees

- `0x180003ce0`
- `0x180004c2c`
- `0x180005df0`
- `0x18000d348`
- `0x18000d43c`
- `0x18000f154`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004d8d`
- `KERNEL32!GetLastError` at `0x180004d8d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180004c9d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180004de3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180004c9d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180004de3`
- `drvstore!DriverStoreOpenW` at `0x180004ce6`
- `drvstore!DriverStoreOpenW` at `0x180004ce6`
- `drvstore!DriverStoreEnumW` at `0x180004d2f`
- `drvstore!DriverStoreEnumW` at `0x180004d2f`
- `drvstore!DriverStoreClose` at `0x180004df8`
- `drvstore!DriverStoreClose` at `0x180004df8`

## pseudocode

```c
__int64 __fastcall SxGetDrivers(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int (__high *a3)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *),
        void *a4)
{
  __int64 v6; // rdi
  unsigned int LastFailureAsHRESULT; // ebx
  int v8; // eax
  int v9; // r9d
  __int16 v10; // ax
  bool v11; // sf
  DWORD LastError; // eax
  signed int v13; // ebx
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+20h] [rbp-29h] BYREF
  _QWORD v16[2]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v17; // [rsp+40h] [rbp-9h]
  signed int v18; // [rsp+48h] [rbp-1h] BYREF
  __int16 v19; // [rsp+4Ch] [rbp+3h]
  __int16 v20; // [rsp+4Eh] [rbp+5h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "SxGetDrivers", 0x371u, (unsigned __int16)a4);
  SystemTimeAsFileTime[0] = 0;
  SystemTimeAsFileTime[1] = 0;
  GetSystemTimeAsFileTime(SystemTimeAsFileTime);
  v17 = 0;
  v19 = 892;
  v18 = 0;
  v16[0] = &CSrDrvWuHelper::_EnumDriverWUNameCollector;
  v16[1] = a4;
  v6 = DriverStoreOpenW(a1, (unsigned __int64)L"T:" & ((unsigned __int128)-(__int128)(unsigned __int64)a1 >> 64), 0, 0);
  if ( v6 )
  {
    v18 = 0;
    v19 = 907;
    v8 = DriverStoreEnumW(v6, 4, SxEnumPackageFunction, v16);
    v9 = v17;
    if ( !v8 || (int)v17 < 0 )
    {
      if ( (int)v17 >= 0 )
      {
        LastError = GetLastError();
        v13 = LastError;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids, LastError);
        }
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        v18 = v13;
        v10 = 922;
        v11 = v13 < 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids, v17);
          v9 = v17;
        }
        v18 = v9;
        v10 = 916;
        v11 = v9 < 0;
      }
      if ( v11 )
      {
        v20 = v10;
LABEL_23:
        DriverStoreClose(v6);
        LastFailureAsHRESULT = v18;
        goto LABEL_24;
      }
      v19 = v10;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
    xmmword_18001D980 = *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime;
    goto LABEL_23;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT();
  v18 = LastFailureAsHRESULT;
  v20 = 907;
LABEL_24:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180004c2c  push    rbp
0x180004c2e  push    rbx
0x180004c2f  push    rdi
0x180004c30  push    r14
0x180004c32  lea     rbp, [rsp-3Fh]
0x180004c37  sub     rsp, 88h
0x180004c3e  mov     rdi, r9
0x180004c41  mov     rbx, rcx
0x180004c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c4b  lea     r14, WPP_GLOBAL_Control
0x180004c52  cmp     rcx, r14
0x180004c55  jz      short loc_180004C75
0x180004c57  test    dword ptr [rcx+1Ch], 20000000h
0x180004c5e  jz      short loc_180004C75
0x180004c60  mov     rcx, [rcx+10h]
0x180004c64  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x180004c6b  mov     edx, 19h
0x180004c70  call    WPP_SF_
0x180004c75  mov     r8d, 371h; unsigned __int16
0x180004c7b  lea     rdx, aSxgetdrivers; "SxGetDrivers"
0x180004c82  lea     rcx, [rbp+57h+var_58]; this
0x180004c86  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180004c8b  xor     eax, eax
0x180004c8d  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180004c95  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004c99  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8], rax
0x180004c9d  call    cs:__imp_GetSystemTimeAsFileTime
0x180004ca3  mov     eax, 37Ch
0x180004ca8  mov     [rbp+57h+var_60], 0
0x180004cb0  mov     [rbp+57h+var_54], ax
0x180004cb4  lea     rcx, aT; "T:"
0x180004cbb  lea     rax, ?_EnumDriverWUNameCollector@CSrDrvWuHelper@@CAJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z; CSrDrvWuHelper::_EnumDriverWUNameCollector(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *)
0x180004cc2  mov     [rbp+57h+var_58], 0
0x180004cc9  mov     [rbp+57h+var_70], rax
0x180004ccd  mov     rax, rbx
0x180004cd0  neg     rax
0x180004cd3  mov     [rbp+57h+var_68], rdi
0x180004cd7  sbb     rdx, rdx
0x180004cda  xor     r9d, r9d
0x180004cdd  and     rdx, rcx
0x180004ce0  xor     r8d, r8d
0x180004ce3  mov     rcx, rbx
0x180004ce6  call    cs:__imp_DriverStoreOpenW
0x180004cec  mov     rdi, rax
0x180004cef  test    rax, rax
0x180004cf2  jnz     short loc_180004D0C
0x180004cf4  call    GetLastFailureAsHRESULT
0x180004cf9  mov     ebx, eax
0x180004cfb  mov     [rbp+57h+var_58], eax
0x180004cfe  mov     eax, 38Bh
0x180004d03  mov     [rbp+57h+var_52], ax
0x180004d07  jmp     loc_180004E01
0x180004d0c  mov     eax, 38Bh
0x180004d11  mov     [rbp+57h+var_58], 0
0x180004d18  lea     r9, [rbp+57h+var_70]
0x180004d1c  mov     [rbp+57h+var_54], ax
0x180004d20  lea     r8, ?SxEnumPackageFunction@@YAHPEAUHDRIVERSTORE__@@PEBGPEAU_DRIVERSTORE_DRIVERPACKAGE_INFOW@@_J@Z; SxEnumPackageFunction(HDRIVERSTORE__ *,ushort const *,_DRIVERSTORE_DRIVERPACKAGE_INFOW *,__int64)
0x180004d27  mov     edx, 4
0x180004d2c  mov     rcx, rdi
0x180004d2f  call    cs:__imp_DriverStoreEnumW
0x180004d35  mov     r9, [rbp+57h+var_60]
0x180004d39  test    eax, eax
0x180004d3b  jz      short loc_180004D46
0x180004d3d  test    r9d, r9d
0x180004d40  jns     loc_180004DDF
0x180004d46  test    r9d, r9d
0x180004d49  jns     short loc_180004D8D
0x180004d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d52  cmp     rcx, r14
0x180004d55  jz      short loc_180004D79
0x180004d57  test    dword ptr [rcx+1Ch], 2000000h
0x180004d5e  jz      short loc_180004D79
0x180004d60  mov     rcx, [rcx+10h]
0x180004d64  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x180004d6b  mov     edx, 1Ah
0x180004d70  call    WPP_SF_D
0x180004d75  mov     r9, [rbp+57h+var_60]
0x180004d79  mov     [rbp+57h+var_58], r9d
0x180004d7d  mov     eax, 394h
0x180004d82  test    r9d, r9d
0x180004d85  jns     short loc_180004DDB
0x180004d87  mov     [rbp+57h+var_52], ax
0x180004d8b  jmp     short loc_180004DF5
0x180004d8d  call    cs:__imp_GetLastError
0x180004d93  mov     ebx, eax
0x180004d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d9c  cmp     rcx, r14
0x180004d9f  jz      short loc_180004DC2
0x180004da1  test    dword ptr [rcx+1Ch], 2000000h
0x180004da8  jz      short loc_180004DC2
0x180004daa  mov     rcx, [rcx+10h]
0x180004dae  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x180004db5  mov     edx, 1Bh
0x180004dba  mov     r9d, eax
0x180004dbd  call    WPP_SF_D
0x180004dc2  test    ebx, ebx
0x180004dc4  jle     short loc_180004DCF
0x180004dc6  movzx   ebx, bx
0x180004dc9  or      ebx, 80070000h
0x180004dcf  mov     [rbp+57h+var_58], ebx
0x180004dd2  mov     eax, 39Ah
0x180004dd7  test    ebx, ebx
0x180004dd9  jmp     short loc_180004D85
0x180004ddb  mov     [rbp+57h+var_54], ax
0x180004ddf  lea     rcx, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x180004de3  call    cs:__imp_GetSystemTimeAsFileTime
0x180004de9  movups  xmm0, xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180004ded  movdqu  cs:xmmword_18001D980, xmm0
0x180004df5  mov     rcx, rdi
0x180004df8  call    cs:__imp_DriverStoreClose
0x180004dfe  mov     ebx, [rbp+57h+var_58]
0x180004e01  lea     rcx, [rbp+57h+var_58]; this
0x180004e05  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180004e0a  mov     eax, ebx
0x180004e0c  add     rsp, 88h
0x180004e13  pop     r14
0x180004e15  pop     rdi
0x180004e16  pop     rbx
0x180004e17  pop     rbp
0x180004e18  retn
```
