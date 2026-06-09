# CVdsRawDiskLun::GetProperties(_VDS_ADVANCEDDISK_PROP *)

- ea: `0x14004dee0`
- end: `0x14004e2ac`
- name: `?GetProperties@CVdsRawDiskLun@@UEAAJPEAU_VDS_ADVANCEDDISK_PROP@@@Z`
- size: `972`
- prototype: `int(CVdsRawDiskLun *__hidden this, struct _VDS_ADVANCEDDISK_PROP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x14002e123`
- `0x14004dee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004e28b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004e28b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004df1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004df1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e18a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e19c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e1af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e1c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e1d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e1e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e1fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e20e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e221`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e18a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e19c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e1af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e1c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e1d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e1e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e1fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e20e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e221`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004e272`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004e272`
- `vdsutil!OpenDevice` at `0x14004e105`
- `vdsutil!OpenDevice` at `0x14004e105`
- `vdsutil!VdsAllocateString` at `0x14004df7c`
- `vdsutil!VdsAllocateString` at `0x14004df9e`
- `vdsutil!VdsAllocateString` at `0x14004dfc0`
- `vdsutil!VdsAllocateString` at `0x14004dfe2`
- `vdsutil!VdsAllocateString` at `0x14004e004`
- `vdsutil!VdsAllocateString` at `0x14004e026`
- `vdsutil!VdsAllocateString` at `0x14004e048`
- `vdsutil!VdsAllocateString` at `0x14004e06a`
- `vdsutil!VdsAllocateString` at `0x14004df7c`
- `vdsutil!VdsAllocateString` at `0x14004df9e`
- `vdsutil!VdsAllocateString` at `0x14004dfc0`
- `vdsutil!VdsAllocateString` at `0x14004dfe2`
- `vdsutil!VdsAllocateString` at `0x14004e004`
- `vdsutil!VdsAllocateString` at `0x14004e026`
- `vdsutil!VdsAllocateString` at `0x14004e048`
- `vdsutil!VdsAllocateString` at `0x14004e06a`
- `vdsutil!GetDiskIdentifiers` at `0x14004e090`
- `vdsutil!GetDiskIdentifiers` at `0x14004e090`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004df0d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004df0d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004e297`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004e297`
- `vdsutil!VdsTraceW` at `0x14004e0e5`
- `vdsutil!VdsTraceW` at `0x14004e132`
- `vdsutil!VdsTraceW` at `0x14004e17c`
- `vdsutil!VdsTraceW` at `0x14004e0e5`
- `vdsutil!VdsTraceW` at `0x14004e132`
- `vdsutil!VdsTraceW` at `0x14004e17c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsRawDiskLun::GetProperties(CVdsRawDiskLun *this, struct _VDS_ADVANCEDDISK_PROP *a2)
{
  signed int String; // edi
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned int v8; // eax
  int v9; // ebp
  LPWSTR pwszPathname; // rcx
  LPWSTR pwszLocation; // rcx
  LPWSTR pwszFriendlyName; // rcx
  LPWSTR pwszSerialNumber; // rcx
  LPWSTR pwszFirmwareVersion; // rcx
  LPWSTR pwszManufacturer; // rcx
  LPWSTR pwszModel; // rcx
  LPWSTR pswzIdentifier; // rcx
  _BYTE v19[88]; // [rsp+30h] [rbp-58h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp+8h] BYREF

  hObject = (HANDLE)-1LL;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v19, 0x5Eu, "CVdsRawDiskLun::GetProperties() (IVdsAdvancedDisk3)");
  EnterCriticalSection(&g_GlobalCriticalSection);
  if ( *((_DWORD *)this + 72) == 1 )
  {
    String = -2147212277;
    goto LABEL_55;
  }
  if ( !a2 )
  {
    String = -2147024809;
    v5 = 2792;
LABEL_34:
    VdsTraceW(
      0,
      L"CVdsRawDiskLun::GetProperties() (IVdsAdvancedDisk3), 3, line=%ld error=%lX",
      v5,
      (unsigned int)String);
    if ( a2->pwszId )
    {
      CoTaskMemFree(a2->pwszId);
      a2->pwszId = 0;
    }
    pwszPathname = a2->pwszPathname;
    if ( pwszPathname )
    {
      CoTaskMemFree(pwszPathname);
      a2->pwszPathname = 0;
    }
    pwszLocation = a2->pwszLocation;
    if ( pwszLocation )
    {
      CoTaskMemFree(pwszLocation);
      a2->pwszLocation = 0;
    }
    pwszFriendlyName = a2->pwszFriendlyName;
    if ( pwszFriendlyName )
    {
      CoTaskMemFree(pwszFriendlyName);
      a2->pwszFriendlyName = 0;
    }
    pwszSerialNumber = a2->pwszSerialNumber;
    if ( pwszSerialNumber )
    {
      CoTaskMemFree(pwszSerialNumber);
      a2->pwszSerialNumber = 0;
    }
    pwszFirmwareVersion = a2->pwszFirmwareVersion;
    if ( pwszFirmwareVersion )
    {
      CoTaskMemFree(pwszFirmwareVersion);
      a2->pwszFirmwareVersion = 0;
    }
    pwszManufacturer = a2->pwszManufacturer;
    if ( pwszManufacturer )
    {
      CoTaskMemFree(pwszManufacturer);
      a2->pwszManufacturer = 0;
    }
    pwszModel = a2->pwszModel;
    if ( pwszModel )
    {
      CoTaskMemFree(pwszModel);
      a2->pwszModel = 0;
    }
    pswzIdentifier = a2->pswzIdentifier;
    if ( pswzIdentifier )
    {
      CoTaskMemFree(pswzIdentifier);
      a2->pswzIdentifier = 0;
    }
    goto LABEL_53;
  }
  memset_0(a2, 0, sizeof(struct _VDS_ADVANCEDDISK_PROP));
  v6 = *((_QWORD *)this + 28);
  if ( !v6 )
  {
    String = -2147418113;
    v5 = 2800;
    goto LABEL_34;
  }
  String = VdsAllocateString(v6, a2);
  if ( String < 0 )
  {
    v5 = 2806;
    goto LABEL_34;
  }
  String = VdsAllocateString(*((_QWORD *)this + 24), &a2->pwszPathname);
  if ( String < 0 )
  {
    v5 = 2812;
    goto LABEL_34;
  }
  String = VdsAllocateString(*((_QWORD *)this + 25), &a2->pwszLocation);
  if ( String < 0 )
  {
    v5 = 2818;
    goto LABEL_34;
  }
  String = VdsAllocateString(*((_QWORD *)this + 22), &a2->pwszFriendlyName);
  if ( String < 0 )
  {
    v5 = 2824;
    goto LABEL_34;
  }
  String = VdsAllocateString(*((_QWORD *)this + 31), &a2->pwszSerialNumber);
  if ( String < 0 )
  {
    v5 = 2830;
    goto LABEL_34;
  }
  String = VdsAllocateString(*((_QWORD *)this + 32), &a2->pwszFirmwareVersion);
  if ( String < 0 )
  {
    v5 = 2836;
    goto LABEL_34;
  }
  String = VdsAllocateString(*((_QWORD *)this + 29), &a2->pwszManufacturer);
  if ( String < 0 )
  {
    v5 = 2842;
    goto LABEL_34;
  }
  String = VdsAllocateString(*((_QWORD *)this + 30), &a2->pwszModel);
  if ( String < 0 )
  {
    v5 = 2848;
    goto LABEL_34;
  }
  String = GetDiskIdentifiers(a2->pwszPathname, a2->pwszId, &a2->pswzIdentifier, &a2->usIdentifierFormat);
  if ( String < 0 )
  {
    v5 = 2859;
    goto LABEL_34;
  }
  a2->ulNumber = *((_DWORD *)this + 68);
  a2->ullTotalSize = *((_QWORD *)this + 14);
  a2->ullAllocatedSize = 0;
  a2->ulLogicalSectorSize = *((_DWORD *)this + 66);
  *(_QWORD *)&a2->ulPhysicalSectorSize = *((unsigned int *)this + 67);
  v7 = *((_QWORD *)this + 21);
  if ( v7 )
  {
    v8 = OpenDevice(v7, 0x80000000LL, &hObject);
    v9 = v8;
    if ( v8 )
    {
      VdsTraceW(
        0,
        L"CVdsRawDiskLun::GetProperties() (IVdsAdvancedDisk3), 2, error=%ld, name=%s, number=%ld",
        v8,
        *((_QWORD *)this + 21),
        *((_DWORD *)this + 68));
      if ( v9 == 5
        || v9 == 32
        || (*((_DWORD *)this + 22) = 0,
            *((_DWORD *)this + 25) = 0,
            a2->status = VDS_DS_UNKNOWN,
            a2->health = *((_DWORD *)this + 25),
            v9 > 0) )
      {
        String = (unsigned __int16)v9 | 0x80070000;
      }
      else
      {
        String = v9;
      }
      v5 = 0;
      if ( String < 0 )
        goto LABEL_34;
    }
    else
    {
      a2->status = *((_DWORD *)this + 22);
      a2->health = *((_DWORD *)this + 25);
      a2->BusType = *((_DWORD *)this + 34);
      a2->PartitionStyle = *((_DWORD *)this + 35);
      a2->ulFlags = *((_DWORD *)this + 33);
      a2->dwDeviceType = *((_DWORD *)this + 26);
    }
  }
  else
  {
    VdsTraceW(0, L"CVdsRawDiskLun::GetProperties() (IVdsAdvancedDisk3), 1");
    *((_DWORD *)this + 22) = 0;
    *((_DWORD *)this + 25) = 0;
  }
LABEL_53:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
LABEL_55:
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v19);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x14004dee0  mov     rax, rsp
0x14004dee3  push    rbx
0x14004dee4  push    rbp
0x14004dee5  push    rsi
0x14004dee6  push    rdi
0x14004dee7  push    r14
0x14004dee9  push    r15
0x14004deeb  sub     rsp, 58h
0x14004deef  mov     rbx, rdx
0x14004def2  mov     rsi, rcx
0x14004def5  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x14004defd  lea     r8, aCvdsrawdisklun_61; "CVdsRawDiskLun::GetProperties() (IVdsAd"...
0x14004df04  mov     edx, 5Eh ; '^'
0x14004df09  lea     rcx, [rax-58h]
0x14004df0d  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14004df13  nop
0x14004df14  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004df1b  call    cs:__imp_EnterCriticalSection
0x14004df21  nop
0x14004df22  cmp     dword ptr [rsi+120h], 1
0x14004df29  jnz     short loc_14004DF35
0x14004df2b  mov     edi, 8004240Bh
0x14004df30  jmp     loc_14004E284
0x14004df35  xor     r15d, r15d
0x14004df38  test    rbx, rbx
0x14004df3b  jnz     short loc_14004DF4D
0x14004df3d  mov     edi, 80070057h
0x14004df42  mov     r8d, 0AE8h
0x14004df48  jmp     loc_14004E170
0x14004df4d  xor     edx, edx; Val
0x14004df4f  mov     r8d, 98h; Size
0x14004df55  mov     rcx, rbx; void *
0x14004df58  call    memset_0
0x14004df5d  mov     rcx, [rsi+0E0h]
0x14004df64  test    rcx, rcx
0x14004df67  jnz     short loc_14004DF79
0x14004df69  mov     edi, 8000FFFFh
0x14004df6e  mov     r8d, 0AF0h
0x14004df74  jmp     loc_14004E170
0x14004df79  mov     rdx, rbx
0x14004df7c  call    cs:__imp_VdsAllocateString
0x14004df82  mov     edi, eax
0x14004df84  test    eax, eax
0x14004df86  jns     short loc_14004DF93
0x14004df88  mov     r8d, 0AF6h
0x14004df8e  jmp     loc_14004E170
0x14004df93  lea     rdx, [rbx+8]
0x14004df97  mov     rcx, [rsi+0C0h]
0x14004df9e  call    cs:__imp_VdsAllocateString
0x14004dfa4  mov     edi, eax
0x14004dfa6  test    eax, eax
0x14004dfa8  jns     short loc_14004DFB5
0x14004dfaa  mov     r8d, 0AFCh
0x14004dfb0  jmp     loc_14004E170
0x14004dfb5  lea     rdx, [rbx+10h]
0x14004dfb9  mov     rcx, [rsi+0C8h]
0x14004dfc0  call    cs:__imp_VdsAllocateString
0x14004dfc6  mov     edi, eax
0x14004dfc8  test    eax, eax
0x14004dfca  jns     short loc_14004DFD7
0x14004dfcc  mov     r8d, 0B02h
0x14004dfd2  jmp     loc_14004E170
0x14004dfd7  lea     rdx, [rbx+18h]
0x14004dfdb  mov     rcx, [rsi+0B0h]
0x14004dfe2  call    cs:__imp_VdsAllocateString
0x14004dfe8  mov     edi, eax
0x14004dfea  test    eax, eax
0x14004dfec  jns     short loc_14004DFF9
0x14004dfee  mov     r8d, 0B08h
0x14004dff4  jmp     loc_14004E170
0x14004dff9  lea     rdx, [rbx+30h]
0x14004dffd  mov     rcx, [rsi+0F8h]
0x14004e004  call    cs:__imp_VdsAllocateString
0x14004e00a  mov     edi, eax
0x14004e00c  test    eax, eax
0x14004e00e  jns     short loc_14004E01B
0x14004e010  mov     r8d, 0B0Eh
0x14004e016  jmp     loc_14004E170
0x14004e01b  lea     rdx, [rbx+38h]
0x14004e01f  mov     rcx, [rsi+100h]
0x14004e026  call    cs:__imp_VdsAllocateString
0x14004e02c  mov     edi, eax
0x14004e02e  test    eax, eax
0x14004e030  jns     short loc_14004E03D
0x14004e032  mov     r8d, 0B14h
0x14004e038  jmp     loc_14004E170
0x14004e03d  lea     rdx, [rbx+40h]
0x14004e041  mov     rcx, [rsi+0E8h]
0x14004e048  call    cs:__imp_VdsAllocateString
0x14004e04e  mov     edi, eax
0x14004e050  test    eax, eax
0x14004e052  jns     short loc_14004E05F
0x14004e054  mov     r8d, 0B1Ah
0x14004e05a  jmp     loc_14004E170
0x14004e05f  lea     rdx, [rbx+48h]
0x14004e063  mov     rcx, [rsi+0F0h]
0x14004e06a  call    cs:__imp_VdsAllocateString
0x14004e070  mov     edi, eax
0x14004e072  test    eax, eax
0x14004e074  jns     short loc_14004E081
0x14004e076  mov     r8d, 0B20h
0x14004e07c  jmp     loc_14004E170
0x14004e081  lea     r9, [rbx+28h]
0x14004e085  lea     r8, [rbx+20h]
0x14004e089  mov     rdx, [rbx]
0x14004e08c  mov     rcx, [rbx+8]
0x14004e090  call    cs:__imp_GetDiskIdentifiers
0x14004e096  mov     edi, eax
0x14004e098  test    eax, eax
0x14004e09a  jns     short loc_14004E0A7
0x14004e09c  mov     r8d, 0B2Bh
0x14004e0a2  jmp     loc_14004E170
0x14004e0a7  mov     eax, [rsi+110h]
0x14004e0ad  mov     [rbx+2Ch], eax
0x14004e0b0  mov     rax, [rsi+70h]
0x14004e0b4  mov     [rbx+50h], rax
0x14004e0b8  mov     [rbx+58h], r15
0x14004e0bc  mov     eax, [rsi+108h]
0x14004e0c2  mov     [rbx+60h], eax
0x14004e0c5  mov     eax, [rsi+10Ch]
0x14004e0cb  mov     [rbx+64h], eax
0x14004e0ce  mov     [rbx+68h], r15d
0x14004e0d2  mov     rcx, [rsi+0A8h]
0x14004e0d9  test    rcx, rcx
0x14004e0dc  jnz     short loc_14004E0F8
0x14004e0de  lea     rdx, aCvdsrawdisklun_22; "CVdsRawDiskLun::GetProperties() (IVdsAd"...
0x14004e0e5  call    cs:__imp_VdsTraceW
0x14004e0eb  mov     [rsi+58h], r15d
0x14004e0ef  mov     [rsi+64h], r15d
0x14004e0f3  jmp     loc_14004E260
0x14004e0f8  lea     r8, [rsp+88h+hObject]
0x14004e100  mov     edx, 80000000h
0x14004e105  call    cs:__imp_OpenDevice
0x14004e10b  mov     ebp, eax
0x14004e10d  test    eax, eax
0x14004e10f  jz      loc_14004E22D
0x14004e115  mov     ecx, [rsi+110h]
0x14004e11b  mov     [rsp+88h+var_68], ecx
0x14004e11f  mov     r9, [rsi+0A8h]
0x14004e126  mov     r8d, eax
0x14004e129  lea     rdx, aCvdsrawdisklun_77; "CVdsRawDiskLun::GetProperties() (IVdsAd"...
0x14004e130  xor     ecx, ecx
0x14004e132  call    cs:__imp_VdsTraceW
0x14004e138  cmp     ebp, 5
0x14004e13b  jz      short loc_14004E15C
0x14004e13d  cmp     ebp, 20h ; ' '
0x14004e140  jz      short loc_14004E15C
0x14004e142  mov     [rsi+58h], r15d
0x14004e146  mov     [rsi+64h], r15d
0x14004e14a  mov     [rbx+6Ch], r15d
0x14004e14e  mov     eax, [rsi+64h]
0x14004e151  mov     [rbx+70h], eax
0x14004e154  test    ebp, ebp
0x14004e156  jg      short loc_14004E15C
0x14004e158  mov     edi, ebp
0x14004e15a  jmp     short loc_14004E165
0x14004e15c  movzx   edi, bp
0x14004e15f  or      edi, 80070000h
0x14004e165  mov     r8d, r15d
0x14004e168  test    edi, edi
0x14004e16a  jns     loc_14004E260
0x14004e170  mov     r9d, edi
0x14004e173  lea     rdx, aCvdsrawdisklun_50; "CVdsRawDiskLun::GetProperties() (IVdsAd"...
0x14004e17a  xor     ecx, ecx
0x14004e17c  call    cs:__imp_VdsTraceW
0x14004e182  mov     rcx, [rbx]; pv
0x14004e185  test    rcx, rcx
0x14004e188  jz      short loc_14004E193
0x14004e18a  call    cs:__imp_CoTaskMemFree
0x14004e190  mov     [rbx], r15
0x14004e193  mov     rcx, [rbx+8]; pv
0x14004e197  test    rcx, rcx
0x14004e19a  jz      short loc_14004E1A6
0x14004e19c  call    cs:__imp_CoTaskMemFree
0x14004e1a2  mov     [rbx+8], r15
0x14004e1a6  mov     rcx, [rbx+10h]; pv
0x14004e1aa  test    rcx, rcx
0x14004e1ad  jz      short loc_14004E1B9
0x14004e1af  call    cs:__imp_CoTaskMemFree
0x14004e1b5  mov     [rbx+10h], r15
0x14004e1b9  mov     rcx, [rbx+18h]; pv
0x14004e1bd  test    rcx, rcx
0x14004e1c0  jz      short loc_14004E1CC
0x14004e1c2  call    cs:__imp_CoTaskMemFree
0x14004e1c8  mov     [rbx+18h], r15
0x14004e1cc  mov     rcx, [rbx+30h]; pv
0x14004e1d0  test    rcx, rcx
0x14004e1d3  jz      short loc_14004E1DF
0x14004e1d5  call    cs:__imp_CoTaskMemFree
0x14004e1db  mov     [rbx+30h], r15
0x14004e1df  mov     rcx, [rbx+38h]; pv
0x14004e1e3  test    rcx, rcx
0x14004e1e6  jz      short loc_14004E1F2
0x14004e1e8  call    cs:__imp_CoTaskMemFree
0x14004e1ee  mov     [rbx+38h], r15
0x14004e1f2  mov     rcx, [rbx+40h]; pv
0x14004e1f6  test    rcx, rcx
0x14004e1f9  jz      short loc_14004E205
0x14004e1fb  call    cs:__imp_CoTaskMemFree
0x14004e201  mov     [rbx+40h], r15
0x14004e205  mov     rcx, [rbx+48h]; pv
0x14004e209  test    rcx, rcx
0x14004e20c  jz      short loc_14004E218
0x14004e20e  call    cs:__imp_CoTaskMemFree
0x14004e214  mov     [rbx+48h], r15
0x14004e218  mov     rcx, [rbx+20h]; pv
0x14004e21c  test    rcx, rcx
0x14004e21f  jz      short loc_14004E260
0x14004e221  call    cs:__imp_CoTaskMemFree
0x14004e227  mov     [rbx+20h], r15
0x14004e22b  jmp     short loc_14004E260
0x14004e22d  mov     eax, [rsi+58h]
0x14004e230  mov     [rbx+6Ch], eax
0x14004e233  mov     eax, [rsi+64h]
0x14004e236  mov     [rbx+70h], eax
0x14004e239  mov     eax, [rsi+88h]
0x14004e23f  mov     [rbx+74h], eax
0x14004e242  mov     eax, [rsi+8Ch]
0x14004e248  mov     [rbx+78h], eax
0x14004e24b  mov     eax, [rsi+84h]
0x14004e251  mov     [rbx+8Ch], eax
0x14004e257  mov     eax, [rsi+68h]
0x14004e25a  mov     [rbx+90h], eax
0x14004e260  mov     rcx, [rsp+88h+hObject]; hObject
0x14004e268  lea     rax, [rcx-1]
0x14004e26c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14004e270  ja      short loc_14004E284
0x14004e272  call    cs:__imp_CloseHandle
0x14004e278  mov     [rsp+88h+hObject], 0FFFFFFFFFFFFFFFFh
0x14004e284  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004e28b  call    cs:__imp_LeaveCriticalSection
0x14004e291  nop
0x14004e292  lea     rcx, [rsp+88h+var_58]
0x14004e297  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004e29d  mov     eax, edi
0x14004e29f  add     rsp, 58h
0x14004e2a3  pop     r15
0x14004e2a5  pop     r14
0x14004e2a7  pop     rdi
0x14004e2a8  pop     rsi
0x14004e2a9  pop     rbp
0x14004e2aa  pop     rbx
0x14004e2ab  retn
```
