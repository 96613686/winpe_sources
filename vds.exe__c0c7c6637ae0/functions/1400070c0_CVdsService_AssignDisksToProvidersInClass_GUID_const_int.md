# CVdsService::AssignDisksToProvidersInClass(_GUID const &,int)

- ea: `0x1400070c0`
- end: `0x1400074ad`
- name: `?AssignDisksToProvidersInClass@CVdsService@@CAKAEBU_GUID@@H@Z`
- size: `1005`
- prototype: `__int64 __fastcall(const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1400171e8`

## callees

- `0x1400070c0`
- `0x1400074c0`
- `0x1400078a0`
- `0x140009710`
- `0x140013298`
- `0x140038924`
- `0x14003c150`
- `0x14003c194`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400073ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000745c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400073ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000745c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400071cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000720f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400071cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000720f`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x140007205`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x140007205`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140007169`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140007169`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400071c3`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400071c3`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x140007414`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x140007451`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x140007414`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x140007451`
- `vdsutil!InvalidateDiskCache` at `0x1400072a5`
- `vdsutil!InvalidateDiskCache` at `0x1400072a5`
- `vdsutil!VdsHeapFree` at `0x1400073fc`
- `vdsutil!VdsHeapFree` at `0x14000746a`
- `vdsutil!VdsHeapFree` at `0x1400073fc`
- `vdsutil!VdsHeapFree` at `0x14000746a`
- `vdsutil!VdsTraceEx` at `0x140007191`
- `vdsutil!VdsTraceEx` at `0x140007233`
- `vdsutil!VdsTraceEx` at `0x140007283`
- `vdsutil!VdsTraceEx` at `0x1400072c6`
- `vdsutil!VdsTraceEx` at `0x14000732a`
- `vdsutil!VdsTraceEx` at `0x14000736d`
- `vdsutil!VdsTraceEx` at `0x1400073a3`
- `vdsutil!VdsTraceEx` at `0x140007191`
- `vdsutil!VdsTraceEx` at `0x140007233`
- `vdsutil!VdsTraceEx` at `0x140007283`
- `vdsutil!VdsTraceEx` at `0x1400072c6`
- `vdsutil!VdsTraceEx` at `0x14000732a`
- `vdsutil!VdsTraceEx` at `0x14000736d`
- `vdsutil!VdsTraceEx` at `0x1400073a3`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140007128`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140007128`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000719d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140007420`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000747a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000719d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140007420`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000747a`
- `vdsutil!GetInterfaceDetailData` at `0x140007253`
- `vdsutil!GetInterfaceDetailData` at `0x140007253`

## string_xrefs

- `0x140007117`: `CVdsService::AssignDisksToProvidersInClass()`
- `0x1400071d3`: `CVdsService::AssignDisksToProvidersInClass, 2, error=%ld`
- `0x14000731c`: `CVdsService::AssignDisksToProvidersInClass, 6, error=%lX`
- `0x140007225`: `CVdsService::AssignDisksToProvidersInClass, 3, error=%ld`
- `0x140007275`: `CVdsService::AssignDisksToProvidersInClass, 4, error=%lX`
- `0x14000717e`: `CVdsService::AssignDisksToProvidersInClass, 1, error=%ld`
- `0x1400072b8`: `CVdsService::AssignDisksToProvidersInClass, 5, name=%S, hr=%lX`
- `0x14000735f`: `CVdsService::AssignDisksToProvidersInClass, 7, error=%lX`
- `0x140007395`: `CVdsService::AssignDisksToProvidersInClass, 8, error=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CVdsService::AssignDisksToProvidersInClass(const struct _GUID *a1, int a2)
{
  signed int v4; // edi
  __int64 v5; // rax
  __int64 DeviceInfoList; // rax
  __int64 v7; // r15
  DWORD LastError; // eax
  const char *v9; // r8
  DWORD v10; // ebx
  int v12; // r13d
  unsigned int i; // r14d
  DWORD v14; // eax
  signed int InterfaceDetailData; // eax
  unsigned int v16; // esi
  wchar_t *v17; // rbx
  int v18; // eax
  signed int v19; // eax
  int v20; // eax
  __int64 v21; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v23; // rbx
  HANDLE v24; // rax
  __int64 v25; // [rsp+40h] [rbp-98h] BYREF
  int v26; // [rsp+48h] [rbp-90h] BYREF
  BOOL v27; // [rsp+4Ch] [rbp-8Ch]
  _BYTE v28[16]; // [rsp+50h] [rbp-88h] BYREF
  struct _GUID v29; // [rsp+60h] [rbp-78h] BYREF
  _OWORD v30[2]; // [rsp+70h] [rbp-68h] BYREF

  v4 = 0;
  v26 = 0;
  v29 = GUID_NULL;
  v25 = 0;
  memset(v30, 0, sizeof(v30));
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v28, 0x5Eu, "CVdsService::AssignDisksToProvidersInClass()");
  v5 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&GUID_DEVINTERFACE_CDROM.Data1;
  if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_DEVINTERFACE_CDROM.Data1 )
    v5 = *(_QWORD *)a1->Data4 - *(_QWORD *)GUID_DEVINTERFACE_CDROM.Data4;
  v27 = v5 == 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v7 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v9 = "CVdsService::AssignDisksToProvidersInClass, 1, error=%ld";
LABEL_5:
    v10 = LastError;
    VdsTraceEx(94, 0, v9, LastError);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
    return v10;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, a1, 0, 18, 0, 0) )
  {
    LastError = GetLastError();
    v9 = "CVdsService::AssignDisksToProvidersInClass, 2, error=%ld";
    goto LABEL_5;
  }
  v12 = 0;
  LODWORD(v30[0]) = 32;
  for ( i = 0; ; ++i )
  {
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(v7, 0, a1, i, v30) )
    {
      v14 = GetLastError();
      v4 = v14;
      if ( v14 == 259 )
      {
        DevObjDestroyDeviceInfoList(v7);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
        return 0;
      }
      VdsTraceEx(94, 0, "CVdsService::AssignDisksToProvidersInClass, 3, error=%ld", v14);
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
    }
    InterfaceDetailData = GetInterfaceDetailData(v7, v30, &v25);
    v16 = InterfaceDetailData;
    if ( InterfaceDetailData )
    {
      v17 = 0;
      v4 = InterfaceDetailData > 0 ? (unsigned __int16)InterfaceDetailData | 0x80070000 : InterfaceDetailData;
      VdsTraceEx(94, 0, "CVdsService::AssignDisksToProvidersInClass, 4, error=%lX", v4);
    }
    else
    {
      v17 = (wchar_t *)(v25 + 4);
      if ( a2 )
      {
        if ( !v27 )
        {
          v18 = InvalidateDiskCache(v25 + 4);
          v4 = v18;
          if ( v18 < 0 )
            VdsTraceEx(94, 0, "CVdsService::AssignDisksToProvidersInClass, 5, name=%S, hr=%lX", v17, v18);
        }
      }
      if ( v17 )
      {
        v4 = CVdsService::AddDiskToVdProviders(v17);
        if ( !v4 )
          v12 = 1;
      }
      v29 = GUID_NULL;
      v19 = CVdsService::ClaimDiskIfRaw(v17, &v26, &v29);
      v16 = v19;
      if ( v19 )
      {
        v4 = v19 > 0 ? (unsigned __int16)v19 | 0x80070000 : v19;
        VdsTraceEx(94, 0, "CVdsService::AssignDisksToProvidersInClass, 6, error=%lX", v4);
      }
      else if ( v26 )
      {
        if ( a2 )
          CVdsService::RemoveOneDiskFromProviders(v17);
      }
      else
      {
        if ( a2 == 1 )
          CVdsService::RemoveObsoleteObject(v17);
        v20 = CVdsService::AssignOneDiskToProviders(v17, a2, v27);
        v4 = v20;
        if ( v20 < 0 )
          VdsTraceEx(94, 0, "CVdsService::AssignDisksToProvidersInClass, 7, error=%lX", v20);
      }
    }
    if ( v12 )
      CVdsService::FinishAddDiskToVdProviders(v17);
    if ( v4 < 0 )
      break;
LABEL_44:
    v21 = v25;
    ProcessHeap = GetProcessHeap();
    VdsHeapFree(ProcessHeap, 0, v21);
    v4 = 0;
    v25 = 0;
  }
  VdsTraceEx(94, 0, "CVdsService::AssignDisksToProvidersInClass, 8, error=%lX", v4);
  if ( v4 != -2147024882 )
  {
    if ( v4 != -2147024894 && v4 != -2147024841 )
      VdsLogError(0xC2000006, 0, 0, v4, 0x200000Fu, v17, 0);
    goto LABEL_44;
  }
  VdsLogError(0xC2000007, 0, 0, 0xEu, 0x2000010u, 0);
  DevObjDestroyDeviceInfoList(v7);
  v23 = v25;
  v24 = GetProcessHeap();
  VdsHeapFree(v24, 0, v23);
  v25 = 0;
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
  return v16;
}

```

## disassembly

```asm
0x1400070c0  mov     [rsp+arg_10], rbx
0x1400070c5  push    rbp
0x1400070c6  push    rsi
0x1400070c7  push    rdi
0x1400070c8  push    r12
0x1400070ca  push    r13
0x1400070cc  push    r14
0x1400070ce  push    r15
0x1400070d0  sub     rsp, 0A0h
0x1400070d7  mov     rax, cs:__security_cookie
0x1400070de  xor     rax, rsp
0x1400070e1  mov     [rsp+0D8h+var_48], rax
0x1400070e9  mov     ebp, edx
0x1400070eb  mov     r12, rcx
0x1400070ee  xor     edi, edi
0x1400070f0  mov     [rsp+0D8h+var_90], edi
0x1400070f4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400070fb  movups  xmmword ptr [rsp+0D8h+var_78.Data1], xmm0
0x140007100  xor     bl, bl
0x140007102  mov     [rsp+0D8h+var_98], rdi
0x140007107  xorps   xmm0, xmm0
0x14000710a  movups  [rsp+0D8h+var_68], xmm0
0x14000710f  movups  [rsp+0D8h+var_58], xmm0
0x140007117  lea     r8, aCvdsserviceAss_5; "CVdsService::AssignDisksToProvidersInCl"...
0x14000711e  mov     edx, 5Eh ; '^'
0x140007123  lea     rcx, [rsp+0D8h+var_88]
0x140007128  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000712e  nop
0x14000712f  mov     rax, [r12]
0x140007133  sub     rax, qword ptr cs:GUID_DEVINTERFACE_CDROM.Data1
0x14000713a  jnz     short loc_140007148
0x14000713c  mov     rax, [r12+8]
0x140007141  sub     rax, qword ptr cs:GUID_DEVINTERFACE_CDROM.Data4
0x140007148  movzx   ecx, bl
0x14000714b  mov     edx, 1
0x140007150  test    rax, rax
0x140007153  cmovz   ecx, edx
0x140007156  mov     [rsp+0D8h+var_8C], ecx
0x14000715a  mov     qword ptr [rsp+0D8h+var_B8], rdi
0x14000715f  xor     r9d, r9d
0x140007162  xor     r8d, r8d
0x140007165  xor     edx, edx
0x140007167  xor     ecx, ecx
0x140007169  call    cs:__imp_DevObjCreateDeviceInfoList
0x14000716f  mov     r15, rax
0x140007172  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140007176  jnz     short loc_1400071AA
0x140007178  call    cs:__imp_GetLastError
0x14000717e  lea     r8, aCvdsserviceAss; "CVdsService::AssignDisksToProvidersInCl"...
0x140007185  mov     r9d, eax
0x140007188  mov     ebx, eax
0x14000718a  xor     edx, edx
0x14000718c  mov     ecx, 5Eh ; '^'
0x140007191  call    cs:__imp_VdsTraceEx
0x140007197  nop
0x140007198  lea     rcx, [rsp+0D8h+var_88]
0x14000719d  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400071a3  mov     eax, ebx
0x1400071a5  jmp     loc_140007482
0x1400071aa  mov     [rsp+0D8h+var_B0], rdi
0x1400071af  mov     qword ptr [rsp+0D8h+var_B8], rdi
0x1400071b4  mov     r9d, 12h
0x1400071ba  xor     r8d, r8d
0x1400071bd  mov     rdx, r12
0x1400071c0  mov     rcx, r15
0x1400071c3  call    cs:__imp_DevObjGetClassDevs
0x1400071c9  test    eax, eax
0x1400071cb  jnz     short loc_1400071DC
0x1400071cd  call    cs:__imp_GetLastError
0x1400071d3  lea     r8, aCvdsserviceAss_10; "CVdsService::AssignDisksToProvidersInCl"...
0x1400071da  jmp     short loc_140007185
0x1400071dc  mov     r13d, edi
0x1400071df  mov     dword ptr [rsp+0D8h+var_68], 20h ; ' '
0x1400071e7  mov     r14d, edi
0x1400071ea  nop     word ptr [rax+rax+00h]
0x1400071f0  lea     rax, [rsp+0D8h+var_68]
0x1400071f5  mov     qword ptr [rsp+0D8h+var_B8], rax
0x1400071fa  mov     r9d, r14d
0x1400071fd  mov     r8, r12
0x140007200  xor     edx, edx
0x140007202  mov     rcx, r15
0x140007205  call    cs:__imp_DevObjEnumDeviceInterfaces
0x14000720b  test    eax, eax
0x14000720d  jnz     short loc_140007246
0x14000720f  call    cs:__imp_GetLastError
0x140007215  mov     edi, eax
0x140007217  cmp     eax, 103h
0x14000721c  jz      loc_140007411
0x140007222  mov     r9d, eax
0x140007225  lea     r8, aCvdsserviceAss_7; "CVdsService::AssignDisksToProvidersInCl"...
0x14000722c  xor     edx, edx
0x14000722e  mov     ecx, 5Eh ; '^'
0x140007233  call    cs:__imp_VdsTraceEx
0x140007239  test    edi, edi
0x14000723b  jle     short loc_140007246
0x14000723d  movzx   edi, di
0x140007240  or      edi, 80070000h
0x140007246  lea     r8, [rsp+0D8h+var_98]
0x14000724b  lea     rdx, [rsp+0D8h+var_68]
0x140007250  mov     rcx, r15
0x140007253  call    cs:__imp_GetInterfaceDetailData
0x140007259  mov     esi, eax
0x14000725b  test    eax, eax
0x14000725d  jz      short loc_14000728E
0x14000725f  xor     ebx, ebx
0x140007261  test    eax, eax
0x140007263  jg      short loc_140007269
0x140007265  mov     edi, eax
0x140007267  jmp     short loc_140007272
0x140007269  movzx   edi, ax
0x14000726c  or      edi, 80070000h
0x140007272  mov     r9d, edi
0x140007275  lea     r8, aCvdsserviceAss_9; "CVdsService::AssignDisksToProvidersInCl"...
0x14000727c  xor     edx, edx
0x14000727e  mov     ecx, 5Eh ; '^'
0x140007283  call    cs:__imp_VdsTraceEx
0x140007289  jmp     loc_140007381
0x14000728e  mov     rbx, [rsp+0D8h+var_98]
0x140007293  add     rbx, 4
0x140007297  test    ebp, ebp
0x140007299  jz      short loc_1400072CC
0x14000729b  cmp     byte ptr [rsp+0D8h+var_8C], 0
0x1400072a0  jnz     short loc_1400072CC
0x1400072a2  mov     rcx, rbx
0x1400072a5  call    cs:__imp_InvalidateDiskCache
0x1400072ab  mov     edi, eax
0x1400072ad  test    eax, eax
0x1400072af  jns     short loc_1400072CC
0x1400072b1  mov     [rsp+0D8h+var_B8], eax
0x1400072b5  mov     r9, rbx
0x1400072b8  lea     r8, aCvdsserviceAss_12; "CVdsService::AssignDisksToProvidersInCl"...
0x1400072bf  xor     edx, edx
0x1400072c1  mov     ecx, 5Eh ; '^'
0x1400072c6  call    cs:__imp_VdsTraceEx
0x1400072cc  test    rbx, rbx
0x1400072cf  jz      short loc_1400072E6
0x1400072d1  mov     rcx, rbx; unsigned __int16 *
0x1400072d4  call    ?AddDiskToVdProviders@CVdsService@@SAJPEAGH@Z; CVdsService::AddDiskToVdProviders(ushort *,int)
0x1400072d9  mov     edi, eax
0x1400072db  test    eax, eax
0x1400072dd  mov     eax, 1
0x1400072e2  cmovz   r13d, eax
0x1400072e6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400072ed  movups  xmmword ptr [rsp+0D8h+var_78.Data1], xmm0
0x1400072f2  lea     r8, [rsp+0D8h+var_78]; struct _GUID *
0x1400072f7  lea     rdx, [rsp+0D8h+var_90]; int *
0x1400072fc  mov     rcx, rbx; lpFileName
0x1400072ff  call    ?ClaimDiskIfRaw@CVdsService@@SAKPEAGPEAHAEAU_GUID@@@Z; CVdsService::ClaimDiskIfRaw(ushort *,int *,_GUID &)
0x140007304  mov     esi, eax
0x140007306  test    eax, eax
0x140007308  jz      short loc_140007332
0x14000730a  jg      short loc_140007310
0x14000730c  mov     edi, eax
0x14000730e  jmp     short loc_140007319
0x140007310  movzx   edi, ax
0x140007313  or      edi, 80070000h
0x140007319  mov     r9d, edi
0x14000731c  lea     r8, aCvdsserviceAss_1; "CVdsService::AssignDisksToProvidersInCl"...
0x140007323  xor     edx, edx
0x140007325  mov     ecx, 5Eh ; '^'
0x14000732a  call    cs:__imp_VdsTraceEx
0x140007330  jmp     short loc_140007381
0x140007332  cmp     [rsp+0D8h+var_90], 0
0x140007337  jnz     short loc_140007375
0x140007339  cmp     ebp, 1
0x14000733c  jnz     short loc_140007346
0x14000733e  mov     rcx, rbx; String1
0x140007341  call    ?RemoveObsoleteObject@CVdsService@@SAXPEAG@Z; CVdsService::RemoveObsoleteObject(ushort *)
0x140007346  movzx   r8d, byte ptr [rsp+0D8h+var_8C]; unsigned __int8
0x14000734c  mov     edx, ebp; int
0x14000734e  mov     rcx, rbx; lpFileName
0x140007351  call    ?AssignOneDiskToProviders@CVdsService@@SAJPEAGHE@Z; CVdsService::AssignOneDiskToProviders(ushort *,int,uchar)
0x140007356  mov     edi, eax
0x140007358  test    eax, eax
0x14000735a  jns     short loc_140007381
0x14000735c  mov     r9d, eax
0x14000735f  lea     r8, aCvdsserviceAss_11; "CVdsService::AssignDisksToProvidersInCl"...
0x140007366  xor     edx, edx
0x140007368  mov     ecx, 5Eh ; '^'
0x14000736d  call    cs:__imp_VdsTraceEx
0x140007373  jmp     short loc_140007381
0x140007375  test    ebp, ebp
0x140007377  jz      short loc_140007381
0x140007379  mov     rcx, rbx; String1
0x14000737c  call    ?RemoveOneDiskFromProviders@CVdsService@@SAHPEAG@Z; CVdsService::RemoveOneDiskFromProviders(ushort *)
0x140007381  test    r13d, r13d
0x140007384  jz      short loc_14000738E
0x140007386  mov     rcx, rbx; unsigned __int16 *
0x140007389  call    ?FinishAddDiskToVdProviders@CVdsService@@SAJPEAG@Z; CVdsService::FinishAddDiskToVdProviders(ushort *)
0x14000738e  test    edi, edi
0x140007390  jns     short loc_1400073E9
0x140007392  mov     r9d, edi
0x140007395  lea     r8, aCvdsserviceAss_4; "CVdsService::AssignDisksToProvidersInCl"...
0x14000739c  xor     edx, edx
0x14000739e  mov     ecx, 5Eh ; '^'
0x1400073a3  call    cs:__imp_VdsTraceEx
0x1400073a9  cmp     edi, 8007000Eh
0x1400073af  jz      short loc_14000742A
0x1400073b1  cmp     edi, 80070002h
0x1400073b7  jz      short loc_1400073E9
0x1400073b9  cmp     edi, 80070037h
0x1400073bf  jz      short loc_1400073E9
0x1400073c1  mov     [rsp+0D8h+var_A8], 0
0x1400073ca  mov     [rsp+0D8h+var_B0], rbx; unsigned __int16 *
0x1400073cf  mov     [rsp+0D8h+var_B8], 200000Fh; unsigned int
0x1400073d7  mov     r9d, edi; unsigned int
0x1400073da  xor     r8d, r8d; void *
0x1400073dd  xor     edx, edx; unsigned int
0x1400073df  mov     ecx, 0C2000006h; unsigned int
0x1400073e4  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x1400073e9  mov     rbx, [rsp+0D8h+var_98]
0x1400073ee  call    cs:__imp_GetProcessHeap
0x1400073f4  mov     r8, rbx
0x1400073f7  xor     edx, edx
0x1400073f9  mov     rcx, rax
0x1400073fc  call    cs:__imp_VdsHeapFree
0x140007402  xor     edi, edi
0x140007404  mov     [rsp+0D8h+var_98], rdi
0x140007409  inc     r14d
0x14000740c  jmp     loc_1400071F0
0x140007411  mov     rcx, r15
0x140007414  call    cs:__imp_DevObjDestroyDeviceInfoList
0x14000741a  nop
0x14000741b  lea     rcx, [rsp+0D8h+var_88]
0x140007420  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140007426  xor     eax, eax
0x140007428  jmp     short loc_140007482
0x14000742a  xor     edi, edi
0x14000742c  mov     [rsp+0D8h+var_B0], rdi; unsigned __int16 *
0x140007431  mov     [rsp+0D8h+var_B8], 2000010h; unsigned int
0x140007439  mov     r9d, 0Eh; unsigned int
0x14000743f  xor     r8d, r8d; void *
0x140007442  xor     edx, edx; unsigned int
0x140007444  mov     ecx, 0C2000007h; unsigned int
0x140007449  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000744e  mov     rcx, r15
0x140007451  call    cs:__imp_DevObjDestroyDeviceInfoList
0x140007457  mov     rbx, [rsp+0D8h+var_98]
0x14000745c  call    cs:__imp_GetProcessHeap
0x140007462  mov     r8, rbx
0x140007465  xor     edx, edx
0x140007467  mov     rcx, rax
0x14000746a  call    cs:__imp_VdsHeapFree
0x140007470  mov     [rsp+0D8h+var_98], rdi
0x140007475  lea     rcx, [rsp+0D8h+var_88]
0x14000747a  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140007480  mov     eax, esi
0x140007482  mov     rcx, [rsp+0D8h+var_48]
0x14000748a  xor     rcx, rsp; StackCookie
0x14000748d  call    __security_check_cookie
0x140007492  mov     rbx, [rsp+0D8h+arg_10]
0x14000749a  add     rsp, 0A0h
0x1400074a1  pop     r15
0x1400074a3  pop     r14
0x1400074a5  pop     r13
0x1400074a7  pop     r12
0x1400074a9  pop     rdi
0x1400074aa  pop     rsi
0x1400074ab  pop     rbp
0x1400074ac  retn
```
