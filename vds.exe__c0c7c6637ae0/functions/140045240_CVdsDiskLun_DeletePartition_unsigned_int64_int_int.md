# CVdsDiskLun::DeletePartition(unsigned __int64,int,int)

- ea: `0x140045240`
- end: `0x14004561a`
- name: `?DeletePartition@CVdsDiskLun@@UEAAJ_KHH@Z`
- size: `986`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this, unsigned __int64, int, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x1400069e8`
- `0x14000d0f0`
- `0x14000e270`
- `0x14002e123`
- `0x140045240`
- `0x140052e52`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `msvcrt!swscanf_s` at `0x14004543f`
- `msvcrt!swscanf_s` at `0x14004543f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400455c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400455c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140045309`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140045309`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004538a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400453a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400453c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400453de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004538a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400453a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400453c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400453de`
- `vdsutil!OpenDevice` at `0x1400454bc`
- `vdsutil!OpenDevice` at `0x1400454bc`
- `vdsutil!LockDismountVolume` at `0x1400454d9`
- `vdsutil!LockDismountVolume` at `0x1400454d9`
- `vdsutil!GetVolumeName` at `0x140045512`
- `vdsutil!GetVolumeName` at `0x140045512`
- `vdsutil!GarbageCollectDriveLetters` at `0x140045590`
- `vdsutil!GarbageCollectDriveLetters` at `0x140045590`
- `vdsutil!DeleteBcdObjects` at `0x14004559b`
- `vdsutil!DeleteBcdObjects` at `0x14004559b`
- `vdsutil!VdsTraceEx` at `0x14004532e`
- `vdsutil!VdsTraceEx` at `0x140045376`
- `vdsutil!VdsTraceEx` at `0x140045420`
- `vdsutil!VdsTraceEx` at `0x1400454ef`
- `vdsutil!VdsTraceEx` at `0x1400455b7`
- `vdsutil!VdsTraceEx` at `0x14004532e`
- `vdsutil!VdsTraceEx` at `0x140045376`
- `vdsutil!VdsTraceEx` at `0x140045420`
- `vdsutil!VdsTraceEx` at `0x1400454ef`
- `vdsutil!VdsTraceEx` at `0x1400455b7`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004528b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004528b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400455f1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400455f1`

## string_xrefs

- `0x140045277`: `CVdsDiskLun::DeletePartition()`
- `0x140045322`: `CVdsDiskLun::DeletePartition, 1, hr=%lX`
- `0x140045367`: `CVdsDiskLun::DeletePartition, 2, hr=%lX`
- `0x140045414`: `CVdsDiskLun::DeletePartition, 4`
- `0x14004544a`: `CVdsDiskLun::DeletePartition, 5`
- `0x140045473`: `CVdsDiskLun::DeletePartition, 6, hr=%lX`
- `0x1400454e3`: `CVdsDiskLun::DeletePartition, 7`
- `0x14004557e`: `CVdsDiskLun::DeletePartition, 10, hr=%lX`
- `0x1400455a8`: `CVdsDiskLun::DeletePartition, 12, status=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsDiskLun::DeletePartition(CVdsDiskLun *this, __int64 a2, unsigned int a3, unsigned int a4)
{
  signed int v8; // ebx
  int v9; // eax
  int v10; // eax
  wchar_t *v11; // rbx
  int v12; // eax
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h]
  wchar_t *v23; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[40]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v25[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[8]; // [rsp+90h] [rbp-70h] BYREF
  int v27; // [rsp+98h] [rbp-68h]
  __int64 v28; // [rsp+A0h] [rbp-60h]
  __int128 v29; // [rsp+C0h] [rbp-40h]
  _BYTE v30[68]; // [rsp+120h] [rbp+20h] BYREF
  int v31; // [rsp+164h] [rbp+64h]
  __int64 v32; // [rsp+168h] [rbp+68h]
  __int64 v33; // [rsp+170h] [rbp+70h]
  LPVOID pv; // [rsp+178h] [rbp+78h]
  wchar_t *String1; // [rsp+180h] [rbp+80h]
  LPVOID v36; // [rsp+188h] [rbp+88h]
  LPVOID v37; // [rsp+190h] [rbp+90h]
  LPVOID v38; // [rsp+198h] [rbp+98h]
  unsigned __int16 v39[40]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v40[536]; // [rsp+1F0h] [rbp+F0h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v25, 0x5Eu, "CVdsDiskLun::DeletePartition()");
  v20 = -1;
  memset_0(v30, 0, 0x80u);
  memset_0(v26, 0, 0x90u);
  v23 = 0;
  v19 = 0;
  memset(v24, 0, sizeof(v24));
  v21 = 0;
  v22 = 0;
  v8 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v21);
  if ( v8 >= 0 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    v9 = CVdsDiskLun::ValidateDiskInterfaces((CVdsDiskLun *)((char *)this - 32));
    v8 = v9;
    if ( v9 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::DeletePartition, 1, hr=%lX", v9);
      if ( v8 == -2147212283 )
        v8 = -2147212277;
      goto LABEL_40;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 24) + 24LL))(*((_QWORD *)this + 24), v30);
    v8 = v10;
    if ( v10 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::DeletePartition, 2, hr=%lX", (unsigned int)v10);
      goto LABEL_40;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v36 )
    {
      CoTaskMemFree(v36);
      v36 = 0;
    }
    if ( v37 )
    {
      CoTaskMemFree(v37);
      v37 = 0;
    }
    if ( v38 )
    {
      CoTaskMemFree(v38);
      v38 = 0;
    }
    v11 = String1;
    v23 = String1;
    if ( wcsncmp_0(String1, L"\\\\?\\PhysicalDrive", 0x11u) )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::DeletePartition, 4");
LABEL_18:
      v8 = -2147212223;
LABEL_40:
      LeaveCriticalSection(&g_GlobalCriticalSection);
      goto LABEL_41;
    }
    if ( swscanf_s(v11, L"\\\\?\\PhysicalDrive%d", &v19) != 1 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::DeletePartition, 5");
      goto LABEL_18;
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *))(**((_QWORD **)this + 26) + 24LL))(
            *((_QWORD *)this + 26),
            a2,
            v26);
    v8 = v12;
    if ( v12 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::DeletePartition, 6, hr=%lX", (unsigned int)v12);
      goto LABEL_40;
    }
    if ( v27 )
    {
      StringCchPrintfW(v39, 0x28u, L"\\Device\\Harddisk%d\\Partition%d", v19, v27);
      v13 = OpenDevice(v39, 0x80000000LL, &v20);
      if ( v13 != 2 )
      {
        if ( !a3 )
        {
          if ( v13 || (LOBYTE(v14) = 1, (unsigned int)LockDismountVolume(v20, 0, v14)) )
          {
            VdsTraceEx(94, 0, "CVdsDiskLun::DeletePartition, 7");
            v8 = -2147212269;
            goto LABEL_40;
          }
        }
        GetVolumeName(v39, 260, v40);
      }
      v24[0] = 0;
      *(_DWORD *)&v24[4] = v31;
      if ( v31 == 1 )
      {
        *(_QWORD *)&v24[4] = __PAIR64__(v32, 1);
        v15 = v28;
      }
      else
      {
        if ( v31 != 2 )
          goto LABEL_35;
        *(_QWORD *)&v24[8] = v32;
        v15 = v33;
        *(_OWORD *)&v24[24] = v29;
      }
      *(_QWORD *)&v24[16] = v15;
    }
LABEL_35:
    v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 26) + 48LL))(
            *((_QWORD *)this + 26),
            a2,
            a3,
            a4);
    v8 = v16;
    if ( v16 >= 0 )
    {
      if ( v27 )
      {
        GarbageCollectDriveLetters();
        v17 = DeleteBcdObjects(v24);
        if ( v17 < 0 )
          VdsTraceEx(94, 1, "CVdsDiskLun::DeletePartition, 12, status=%lX", v17);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::DeletePartition, 10, hr=%lX", (unsigned int)v16);
    }
    goto LABEL_40;
  }
LABEL_41:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v21);
  CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>((void **)&v23);
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>((void **)&v20);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140045240  push    rbp
0x140045242  push    rbx
0x140045243  push    rsi
0x140045244  push    rdi
0x140045245  push    r13
0x140045247  push    r14
0x140045249  push    r15
0x14004524b  lea     rbp, [rsp-310h]
0x140045253  sub     rsp, 410h
0x14004525a  mov     rax, cs:__security_cookie
0x140045261  xor     rax, rsp
0x140045264  mov     [rbp+340h+var_38], rax
0x14004526b  mov     r15d, r9d
0x14004526e  mov     esi, r8d
0x140045271  mov     r14, rdx
0x140045274  mov     rdi, rcx
0x140045277  lea     r8, aCvdsdisklunDel_6; "CVdsDiskLun::DeletePartition()"
0x14004527e  mov     r13d, 5Eh ; '^'
0x140045284  mov     edx, r13d
0x140045287  lea     rcx, [rbp+340h+var_3C0]
0x14004528b  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140045291  nop
0x140045292  mov     [rsp+440h+var_408], 0FFFFFFFFFFFFFFFFh
0x14004529b  xor     edx, edx; Val
0x14004529d  lea     r8d, [r13+22h]; Size
0x1400452a1  lea     rcx, [rbp+340h+var_320]; void *
0x1400452a5  call    memset_0
0x1400452aa  xor     edx, edx; Val
0x1400452ac  lea     r8d, [r13+32h]; Size
0x1400452b0  lea     rcx, [rbp+340h+var_3B0]; void *
0x1400452b4  call    memset_0
0x1400452b9  xorps   xmm0, xmm0
0x1400452bc  xor     eax, eax
0x1400452be  movups  [rsp+440h+var_3E8], xmm0
0x1400452c3  movups  [rsp+440h+var_3D8], xmm0
0x1400452c8  mov     [rsp+440h+var_3C8], rax
0x1400452cd  mov     [rsp+440h+var_3F0], rax
0x1400452d2  mov     [rsp+440h+var_410], eax
0x1400452d6  movups  [rsp+440h+var_3E8], xmm0
0x1400452db  movups  [rsp+440h+var_3D8], xmm0
0x1400452e0  mov     [rsp+440h+var_3C8], rax
0x1400452e5  mov     [rsp+440h+var_400], rax
0x1400452ea  mov     [rsp+440h+var_3F8], eax
0x1400452ee  lea     rcx, [rsp+440h+var_400]; this
0x1400452f3  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x1400452f8  mov     ebx, eax
0x1400452fa  test    eax, eax
0x1400452fc  js      loc_1400455CC
0x140045302  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140045309  call    cs:__imp_EnterCriticalSection
0x14004530f  nop
0x140045310  lea     rcx, [rdi-20h]; this
0x140045314  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140045319  mov     ebx, eax
0x14004531b  test    eax, eax
0x14004531d  jns     short loc_14004534A
0x14004531f  mov     r9d, eax
0x140045322  lea     r8, aCvdsdisklunDel_14; "CVdsDiskLun::DeletePartition, 1, hr=%lX"
0x140045329  xor     edx, edx
0x14004532b  mov     ecx, r13d
0x14004532e  call    cs:__imp_VdsTraceEx
0x140045334  cmp     ebx, 80042405h
0x14004533a  jnz     loc_1400455BE
0x140045340  mov     ebx, 8004240Bh
0x140045345  jmp     loc_1400455BE
0x14004534a  mov     rcx, [rdi+0C0h]
0x140045351  mov     rax, [rcx]
0x140045354  lea     rdx, [rbp+340h+var_320]
0x140045358  mov     rax, [rax+18h]
0x14004535c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045361  mov     ebx, eax
0x140045363  test    eax, eax
0x140045365  jns     short loc_140045381
0x140045367  lea     r8, aCvdsdisklunDel_15; "CVdsDiskLun::DeletePartition, 2, hr=%lX"
0x14004536e  mov     r9d, eax
0x140045371  xor     edx, edx
0x140045373  mov     ecx, r13d
0x140045376  call    cs:__imp_VdsTraceEx
0x14004537c  jmp     loc_1400455BE
0x140045381  mov     rcx, [rbp+340h+pv]; pv
0x140045385  test    rcx, rcx
0x140045388  jz      short loc_140045398
0x14004538a  call    cs:__imp_CoTaskMemFree
0x140045390  mov     [rbp+340h+pv], 0
0x140045398  mov     rcx, [rbp+340h+var_2B8]; pv
0x14004539f  test    rcx, rcx
0x1400453a2  jz      short loc_1400453B5
0x1400453a4  call    cs:__imp_CoTaskMemFree
0x1400453aa  mov     [rbp+340h+var_2B8], 0
0x1400453b5  mov     rcx, [rbp+340h+var_2B0]; pv
0x1400453bc  test    rcx, rcx
0x1400453bf  jz      short loc_1400453D2
0x1400453c1  call    cs:__imp_CoTaskMemFree
0x1400453c7  mov     [rbp+340h+var_2B0], 0
0x1400453d2  mov     rcx, [rbp+340h+var_2A8]; pv
0x1400453d9  test    rcx, rcx
0x1400453dc  jz      short loc_1400453EF
0x1400453de  call    cs:__imp_CoTaskMemFree
0x1400453e4  mov     [rbp+340h+var_2A8], 0
0x1400453ef  mov     rbx, [rbp+340h+String1]
0x1400453f6  mov     [rsp+440h+var_3F0], rbx
0x1400453fb  mov     r8d, 11h; MaxCount
0x140045401  lea     rdx, aPhysicaldrive; "\\\\?\\PhysicalDrive"
0x140045408  mov     rcx, rbx; String1
0x14004540b  call    wcsncmp_0
0x140045410  test    eax, eax
0x140045412  jz      short loc_140045430
0x140045414  lea     r8, aCvdsdisklunDel_10; "CVdsDiskLun::DeletePartition, 4"
0x14004541b  xor     edx, edx
0x14004541d  mov     ecx, r13d
0x140045420  call    cs:__imp_VdsTraceEx
0x140045426  mov     ebx, 80042441h
0x14004542b  jmp     loc_1400455BE
0x140045430  lea     r8, [rsp+440h+var_410]
0x140045435  lea     rdx, aPhysicaldriveD; "\\\\?\\PhysicalDrive%d"
0x14004543c  mov     rcx, rbx; Buffer
0x14004543f  call    cs:__imp_swscanf_s
0x140045445  cmp     eax, 1
0x140045448  jz      short loc_140045453
0x14004544a  lea     r8, aCvdsdisklunDel_9; "CVdsDiskLun::DeletePartition, 5"
0x140045451  jmp     short loc_14004541B
0x140045453  mov     rcx, [rdi+0D0h]
0x14004545a  mov     rax, [rcx]
0x14004545d  lea     r8, [rbp+340h+var_3B0]
0x140045461  mov     rdx, r14
0x140045464  mov     rax, [rax+18h]
0x140045468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004546d  mov     ebx, eax
0x14004546f  test    eax, eax
0x140045471  jns     short loc_14004547F
0x140045473  lea     r8, aCvdsdisklunDel_17; "CVdsDiskLun::DeletePartition, 6, hr=%lX"
0x14004547a  jmp     loc_14004536E
0x14004547f  mov     eax, [rbp+340h+var_3A8]
0x140045482  test    eax, eax
0x140045484  jz      loc_14004555C
0x14004548a  mov     [rsp+440h+var_420], eax
0x14004548e  mov     r9d, [rsp+440h+var_410]
0x140045493  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%d\\Partition%d"
0x14004549a  mov     edx, 28h ; '('; unsigned __int64
0x14004549f  lea     rcx, [rbp+340h+var_2A0]; unsigned __int16 *
0x1400454a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400454ab  lea     r8, [rsp+440h+var_408]
0x1400454b0  mov     edx, 80000000h
0x1400454b5  lea     rcx, [rbp+340h+var_2A0]
0x1400454bc  call    cs:__imp_OpenDevice
0x1400454c2  cmp     eax, 2
0x1400454c5  jz      short loc_140045518
0x1400454c7  test    esi, esi
0x1400454c9  jnz     short loc_1400454FF
0x1400454cb  test    eax, eax
0x1400454cd  jnz     short loc_1400454E3
0x1400454cf  mov     r8b, 1
0x1400454d2  xor     edx, edx
0x1400454d4  mov     rcx, [rsp+440h+var_408]
0x1400454d9  call    cs:__imp_LockDismountVolume
0x1400454df  test    eax, eax
0x1400454e1  jz      short loc_1400454FF
0x1400454e3  lea     r8, aCvdsdisklunDel; "CVdsDiskLun::DeletePartition, 7"
0x1400454ea  xor     edx, edx
0x1400454ec  mov     ecx, r13d
0x1400454ef  call    cs:__imp_VdsTraceEx
0x1400454f5  mov     ebx, 80042413h
0x1400454fa  jmp     loc_1400455BE
0x1400454ff  lea     r8, [rbp+340h+var_250]
0x140045506  mov     edx, 104h
0x14004550b  lea     rcx, [rbp+340h+var_2A0]
0x140045512  call    cs:__imp_GetVolumeName
0x140045518  mov     byte ptr [rsp+440h+var_3E8], 0
0x14004551d  mov     eax, [rbp+340h+var_2DC]
0x140045520  mov     dword ptr [rsp+440h+var_3E8+4], eax
0x140045524  cmp     eax, 1
0x140045527  jnz     short loc_140045536
0x140045529  mov     eax, dword ptr [rbp+340h+var_2D8]
0x14004552c  mov     dword ptr [rsp+440h+var_3E8+8], eax
0x140045530  mov     rax, [rbp+340h+var_3A0]
0x140045534  jmp     short loc_140045557
0x140045536  cmp     eax, 2
0x140045539  jnz     short loc_14004555C
0x14004553b  mov     eax, dword ptr [rbp+340h+var_2D8]
0x14004553e  mov     dword ptr [rsp+440h+var_3E8+8], eax
0x140045542  mov     eax, dword ptr [rbp+340h+var_2D8+4]
0x140045545  mov     dword ptr [rsp+440h+var_3E8+0Ch], eax
0x140045549  mov     rax, [rbp+340h+var_2D0]
0x14004554d  movaps  xmm0, [rbp+340h+var_380]
0x140045551  movdqu  [rsp+440h+var_3D8+8], xmm0
0x140045557  mov     qword ptr [rsp+440h+var_3D8], rax
0x14004555c  mov     rcx, [rdi+0D0h]
0x140045563  mov     rax, [rcx]
0x140045566  mov     r9d, r15d
0x140045569  mov     r8d, esi
0x14004556c  mov     rdx, r14
0x14004556f  mov     rax, [rax+30h]
0x140045573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045578  mov     ebx, eax
0x14004557a  test    eax, eax
0x14004557c  jns     short loc_14004558A
0x14004557e  lea     r8, aCvdsdisklunDel_13; "CVdsDiskLun::DeletePartition, 10, hr=%l"...
0x140045585  jmp     loc_14004536E
0x14004558a  cmp     [rbp+340h+var_3A8], 0
0x14004558e  jz      short loc_1400455BE
0x140045590  call    cs:__imp_GarbageCollectDriveLetters
0x140045596  lea     rcx, [rsp+440h+var_3E8]
0x14004559b  call    cs:__imp_DeleteBcdObjects
0x1400455a1  test    eax, eax
0x1400455a3  jns     short loc_1400455BE
0x1400455a5  mov     r9d, eax
0x1400455a8  lea     r8, aCvdsdisklunDel_0; "CVdsDiskLun::DeletePartition, 12, statu"...
0x1400455af  mov     edx, 1
0x1400455b4  mov     ecx, r13d
0x1400455b7  call    cs:__imp_VdsTraceEx
0x1400455bd  nop
0x1400455be  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400455c5  call    cs:__imp_LeaveCriticalSection
0x1400455cb  nop
0x1400455cc  lea     rcx, [rsp+440h+var_400]; this
0x1400455d1  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400455d6  nop
0x1400455d7  lea     rcx, [rsp+440h+var_3F0]
0x1400455dc  call    ??1?$CVdsCoTaskPtr@G@@QEAA@XZ; CVdsCoTaskPtr<ushort>::~CVdsCoTaskPtr<ushort>(void)
0x1400455e1  nop
0x1400455e2  lea     rcx, [rsp+440h+var_408]
0x1400455e7  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x1400455ec  nop
0x1400455ed  lea     rcx, [rbp+340h+var_3C0]
0x1400455f1  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400455f7  mov     eax, ebx
0x1400455f9  mov     rcx, [rbp+340h+var_38]
0x140045600  xor     rcx, rsp; StackCookie
0x140045603  call    __security_check_cookie
0x140045608  add     rsp, 410h
0x14004560f  pop     r15
0x140045611  pop     r14
0x140045613  pop     r13
0x140045615  pop     rdi
0x140045616  pop     rsi
0x140045617  pop     rbx
0x140045618  pop     rbp
0x140045619  retn
```
