# CVdsDiskLun::Offline(void)

- ea: `0x140049840`
- end: `0x140049af5`
- name: `?Offline@CVdsDiskLun@@UEAAJXZ`
- size: `693`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x140025a6c`
- `0x140028768`
- `0x14002e123`
- `0x140049840`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140049ab4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140049ab4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400498be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400498be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049a43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049a5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049a71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049a88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049a9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049a43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049a5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049a71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049a88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049a9f`
- `vdsutil!VdsTraceExW` at `0x14004994d`
- `vdsutil!VdsTraceExW` at `0x140049a34`
- `vdsutil!VdsTraceExW` at `0x14004994d`
- `vdsutil!VdsTraceExW` at `0x140049a34`
- `vdsutil!VdsTraceEx` at `0x1400498e3`
- `vdsutil!VdsTraceEx` at `0x14004992b`
- `vdsutil!VdsTraceEx` at `0x140049978`
- `vdsutil!VdsTraceEx` at `0x1400498e3`
- `vdsutil!VdsTraceEx` at `0x14004992b`
- `vdsutil!VdsTraceEx` at `0x140049978`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004987f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004987f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140049ac9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140049ac9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::Offline(CVdsDiskLun *this)
{
  signed int v2; // ebx
  int v3; // eax
  int v4; // eax
  int v5; // eax
  CVdsDiskLun *v6; // rcx
  LPWSTR pwszDevicePath; // r9
  __int64 v9; // [rsp+30h] [rbp-69h] BYREF
  int v10; // [rsp+38h] [rbp-61h]
  _BYTE v11[16]; // [rsp+40h] [rbp-59h] BYREF
  struct _VDS_DISK_PROP v12; // [rsp+50h] [rbp-49h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v11, 0x5Eu, "CVdsDiskLun::Offline()");
  memset_0(&v12, 0, sizeof(v12));
  v9 = 0;
  v10 = 0;
  v2 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v9);
  if ( v2 >= 0 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    v3 = CVdsDiskLun::ValidateDiskInterfaces((CVdsDiskLun *)((char *)this - 24));
    v2 = v3;
    if ( v3 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, struct _VDS_DISK_PROP *))(**((_QWORD **)this + 25) + 24LL))(
             *((_QWORD *)this + 25),
             &v12);
      v2 = v4;
      if ( v4 >= 0 )
      {
        if ( v12.status == VDS_DS_OFFLINE )
        {
          v2 = -2147212213;
          VdsTraceExW(96, 0, L"CVdsDiskLun::Offline, 3");
        }
        else if ( (v12.ulFlags & 0x100) != 0 )
        {
          v2 = -2147211257;
          VdsTraceEx(94, 1, "CVdsDiskLun::Offline, 3.5, boot disk, hr=%lX", 2147756039LL);
        }
        else if ( SLOBYTE(v12.ulFlags) >= 0 )
        {
          if ( (v12.ulFlags & 0x200) != 0 )
          {
            v2 = -2147211252;
            VdsTraceEx(94, 1, "CVdsDiskLun::Offline, 5, hr=%lX", 2147756044LL);
          }
          else if ( (v12.ulFlags & 0x400) != 0 )
          {
            v2 = -2147211251;
            VdsTraceEx(94, 1, "CVdsDiskLun::Offline, 6, hr=%lX", 2147756045LL);
          }
          else if ( (v12.ulFlags & 0x800) != 0 )
          {
            v2 = -2147211250;
            VdsTraceEx(94, 1, "CVdsDiskLun::Offline, 7, hr=%lX", 2147756046LL);
          }
          else if ( v12.dwMediaType == 12 )
          {
            v5 = CVdsDiskLun::DismountDiskVolumes((CVdsDiskLun *)((char *)this - 24));
            v2 = v5;
            if ( v5 >= 0 )
            {
              v2 = CVdsDiskLun::DoOfflineOnline(v6, &v12, 1u);
              if ( v2 < 0 )
              {
                pwszDevicePath = L"UNKNOWN";
                if ( v12.pwszDevicePath )
                  pwszDevicePath = v12.pwszDevicePath;
                VdsTraceExW(94, 0, L"CVdsDiskLun::Offline, 9 Name=%s, hr=%lX", pwszDevicePath, v2);
              }
            }
            else
            {
              VdsTraceEx(94, 0, "CVdsDiskLun::Offline, 8b, hr=%lX", (unsigned int)v5);
            }
          }
          else
          {
            v2 = -2147211942;
            VdsTraceEx(94, 1, "CVdsDiskLun::Offline, 8, hr=%lX", 2147755354LL);
          }
        }
        else
        {
          v2 = -2147211247;
          VdsTraceEx(94, 1, "CVdsDiskLun::Offline, 4, system disk, hr=%lX", 2147756049LL);
        }
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsDiskLun::Offline, 2, hr=%lX", (unsigned int)v4);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::Offline, 1, hr=%lX", v3);
      if ( v2 == -2147212283 )
        v2 = -2147212277;
    }
    if ( v12.pwszDiskAddress )
    {
      CoTaskMemFree(v12.pwszDiskAddress);
      v12.pwszDiskAddress = 0;
    }
    if ( v12.pwszFriendlyName )
    {
      CoTaskMemFree(v12.pwszFriendlyName);
      v12.pwszFriendlyName = 0;
    }
    if ( v12.pwszAdaptorName )
    {
      CoTaskMemFree(v12.pwszAdaptorName);
      v12.pwszAdaptorName = 0;
    }
    if ( v12.pwszDevicePath )
    {
      CoTaskMemFree(v12.pwszDevicePath);
      v12.pwszDevicePath = 0;
    }
    if ( v12.pwszName )
    {
      CoTaskMemFree(v12.pwszName);
      v12.pwszName = 0;
    }
    LeaveCriticalSection(&g_GlobalCriticalSection);
  }
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v9);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140049840  mov     [rsp-8+arg_8], rbx
0x140049845  mov     [rsp-8+arg_10], rsi
0x14004984a  push    rbp
0x14004984b  push    rdi
0x14004984c  push    r15
0x14004984e  lea     rbp, [rsp-47h]
0x140049853  sub     rsp, 0E0h
0x14004985a  mov     rax, cs:__security_cookie
0x140049861  xor     rax, rsp
0x140049864  mov     [rbp+57h+var_18], rax
0x140049868  mov     rsi, rcx
0x14004986b  lea     r8, aCvdsdisklunOff_10; "CVdsDiskLun::Offline()"
0x140049872  mov     r15d, 5Eh ; '^'
0x140049878  mov     edx, r15d
0x14004987b  lea     rcx, [rbp+57h+var_B0]
0x14004987f  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140049885  nop
0x140049886  xor     edx, edx; Val
0x140049888  lea     r8d, [r15+22h]; Size
0x14004988c  lea     rcx, [rbp+57h+var_A0]; void *
0x140049890  call    memset_0
0x140049895  mov     [rbp+57h+var_C0], 0
0x14004989d  mov     [rbp+57h+var_B8], 0
0x1400498a4  lea     rcx, [rbp+57h+var_C0]; this
0x1400498a8  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x1400498ad  mov     ebx, eax
0x1400498af  test    eax, eax
0x1400498b1  js      loc_140049ABB
0x1400498b7  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400498be  call    cs:__imp_EnterCriticalSection
0x1400498c4  nop
0x1400498c5  lea     rcx, [rsi-18h]; this
0x1400498c9  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x1400498ce  mov     ebx, eax
0x1400498d0  test    eax, eax
0x1400498d2  jns     short loc_1400498FF
0x1400498d4  mov     r9d, eax
0x1400498d7  lea     r8, aCvdsdisklunOff_3; "CVdsDiskLun::Offline, 1, hr=%lX"
0x1400498de  xor     edx, edx
0x1400498e0  mov     ecx, r15d
0x1400498e3  call    cs:__imp_VdsTraceEx
0x1400498e9  cmp     ebx, 80042405h
0x1400498ef  jnz     loc_140049A3A
0x1400498f5  mov     ebx, 8004240Bh
0x1400498fa  jmp     loc_140049A3A
0x1400498ff  mov     rcx, [rsi+0C8h]
0x140049906  mov     rax, [rcx]
0x140049909  lea     rdx, [rbp+57h+var_A0]
0x14004990d  mov     rax, [rax+18h]
0x140049911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049916  mov     ebx, eax
0x140049918  test    eax, eax
0x14004991a  jns     short loc_140049936
0x14004991c  lea     r8, aCvdsdisklunOff_4; "CVdsDiskLun::Offline, 2, hr=%lX"
0x140049923  mov     r9d, eax
0x140049926  xor     edx, edx
0x140049928  mov     ecx, r15d
0x14004992b  call    cs:__imp_VdsTraceEx
0x140049931  jmp     loc_140049A3A
0x140049936  cmp     [rbp+57h+var_A0.status], 4
0x14004993a  jnz     short loc_140049958
0x14004993c  mov     ebx, 8004244Bh
0x140049941  lea     r8, aCvdsdisklunOff_9; "CVdsDiskLun::Offline, 3"
0x140049948  xor     edx, edx
0x14004994a  lea     ecx, [rdx+60h]
0x14004994d  call    cs:__imp_VdsTraceExW
0x140049953  jmp     loc_140049A3A
0x140049958  mov     eax, [rbp+57h+var_A0.ulFlags]
0x14004995b  bt      eax, 8
0x14004995f  jnb     short loc_140049983
0x140049961  mov     ebx, 80042807h
0x140049966  lea     r8, aCvdsdisklunOff_8; "CVdsDiskLun::Offline, 3.5, boot disk, h"...
0x14004996d  mov     r9d, ebx
0x140049970  mov     edx, 1
0x140049975  mov     ecx, r15d
0x140049978  call    cs:__imp_VdsTraceEx
0x14004997e  jmp     loc_140049A3A
0x140049983  test    al, al
0x140049985  jns     short loc_140049995
0x140049987  mov     ebx, 80042811h
0x14004998c  lea     r8, aCvdsdisklunOff_0; "CVdsDiskLun::Offline, 4, system disk, h"...
0x140049993  jmp     short loc_14004996D
0x140049995  bt      eax, 9
0x140049999  jnb     short loc_1400499A9
0x14004999b  mov     ebx, 8004280Ch
0x1400499a0  lea     r8, aCvdsdisklunOff_7; "CVdsDiskLun::Offline, 5, hr=%lX"
0x1400499a7  jmp     short loc_14004996D
0x1400499a9  bt      eax, 0Ah
0x1400499ad  jnb     short loc_1400499BD
0x1400499af  mov     ebx, 8004280Dh
0x1400499b4  lea     r8, aCvdsdisklunOff_5; "CVdsDiskLun::Offline, 6, hr=%lX"
0x1400499bb  jmp     short loc_14004996D
0x1400499bd  bt      eax, 0Bh
0x1400499c1  jnb     short loc_1400499D1
0x1400499c3  mov     ebx, 8004280Eh
0x1400499c8  lea     r8, aCvdsdisklunOff_2; "CVdsDiskLun::Offline, 7, hr=%lX"
0x1400499cf  jmp     short loc_14004996D
0x1400499d1  cmp     [rbp+57h+var_A0.dwMediaType], 0Ch
0x1400499d5  jz      short loc_1400499E5
0x1400499d7  mov     ebx, 8004255Ah
0x1400499dc  lea     r8, aCvdsdisklunOff_6; "CVdsDiskLun::Offline, 8, hr=%lX"
0x1400499e3  jmp     short loc_14004996D
0x1400499e5  lea     rcx, [rsi-18h]; this
0x1400499e9  call    ?DismountDiskVolumes@CVdsDiskLun@@QEAAJXZ; CVdsDiskLun::DismountDiskVolumes(void)
0x1400499ee  mov     ebx, eax
0x1400499f0  test    eax, eax
0x1400499f2  jns     short loc_140049A00
0x1400499f4  lea     r8, aCvdsdisklunOff; "CVdsDiskLun::Offline, 8b, hr=%lX"
0x1400499fb  jmp     loc_140049923
0x140049a00  mov     r8b, 1; unsigned __int8
0x140049a03  lea     rdx, [rbp+57h+var_A0]; struct _VDS_DISK_PROP *
0x140049a07  call    ?DoOfflineOnline@CVdsDiskLun@@AEAAJPEAU_VDS_DISK_PROP@@E@Z; CVdsDiskLun::DoOfflineOnline(_VDS_DISK_PROP *,uchar)
0x140049a0c  mov     ebx, eax
0x140049a0e  test    eax, eax
0x140049a10  jns     short loc_140049A3A
0x140049a12  lea     r9, aUnknown_0; "UNKNOWN"
0x140049a19  mov     rax, [rbp+57h+var_A0.pwszDevicePath]
0x140049a1d  test    rax, rax
0x140049a20  cmovnz  r9, rax
0x140049a24  mov     [rsp+0F0h+var_D0], ebx
0x140049a28  lea     r8, aCvdsdisklunOff_1; "CVdsDiskLun::Offline, 9 Name=%s, hr=%lX"
0x140049a2f  xor     edx, edx
0x140049a31  mov     ecx, r15d
0x140049a34  call    cs:__imp_VdsTraceExW
0x140049a3a  mov     rcx, [rbp+57h+var_A0.pwszDiskAddress]; pv
0x140049a3e  test    rcx, rcx
0x140049a41  jz      short loc_140049A51
0x140049a43  call    cs:__imp_CoTaskMemFree
0x140049a49  mov     [rbp+57h+var_A0.pwszDiskAddress], 0
0x140049a51  mov     rcx, [rbp+57h+var_A0.pwszFriendlyName]; pv
0x140049a55  test    rcx, rcx
0x140049a58  jz      short loc_140049A68
0x140049a5a  call    cs:__imp_CoTaskMemFree
0x140049a60  mov     [rbp+57h+var_A0.pwszFriendlyName], 0
0x140049a68  mov     rcx, [rbp+57h+var_A0.pwszAdaptorName]; pv
0x140049a6c  test    rcx, rcx
0x140049a6f  jz      short loc_140049A7F
0x140049a71  call    cs:__imp_CoTaskMemFree
0x140049a77  mov     [rbp+57h+var_A0.pwszAdaptorName], 0
0x140049a7f  mov     rcx, [rbp+57h+var_A0.pwszDevicePath]; pv
0x140049a83  test    rcx, rcx
0x140049a86  jz      short loc_140049A96
0x140049a88  call    cs:__imp_CoTaskMemFree
0x140049a8e  mov     [rbp+57h+var_A0.pwszDevicePath], 0
0x140049a96  mov     rcx, [rbp+57h+var_A0.pwszName]; pv
0x140049a9a  test    rcx, rcx
0x140049a9d  jz      short loc_140049AAD
0x140049a9f  call    cs:__imp_CoTaskMemFree
0x140049aa5  mov     [rbp+57h+var_A0.pwszName], 0
0x140049aad  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140049ab4  call    cs:__imp_LeaveCriticalSection
0x140049aba  nop
0x140049abb  lea     rcx, [rbp+57h+var_C0]; this
0x140049abf  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140049ac4  nop
0x140049ac5  lea     rcx, [rbp+57h+var_B0]
0x140049ac9  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140049acf  mov     eax, ebx
0x140049ad1  mov     rcx, [rbp+57h+var_18]
0x140049ad5  xor     rcx, rsp; StackCookie
0x140049ad8  call    __security_check_cookie
0x140049add  lea     r11, [rsp+0F0h+var_10]
0x140049ae5  mov     rbx, [r11+28h]
0x140049ae9  mov     rsi, [r11+30h]
0x140049aed  mov     rsp, r11
0x140049af0  pop     r15
0x140049af2  pop     rdi
0x140049af3  pop     rbp
0x140049af4  retn
```
