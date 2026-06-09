# CVdsRawDiskLun::GetProperties2(_VDS_DISK_PROP2 *)

- ea: `0x14002a810`
- end: `0x14002ae20`
- name: `?GetProperties2@CVdsRawDiskLun@@UEAAJPEAU_VDS_DISK_PROP2@@@Z`
- size: `1552`
- prototype: `int(CVdsRawDiskLun *__hidden this, struct _VDS_DISK_PROP2 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140006e60`
- `0x14002a810`
- `0x14002e123`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002adf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002adf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002a87e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002a87e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002a8c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002a8f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002a915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002a93a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002a964`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002a9b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002a8c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002a8f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002a915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002a93a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002a964`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002a9b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a8b1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a8e1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a906`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a92b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a955`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a981`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a9a5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a9ea`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002aa12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002aa34`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002aa56`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002aa78`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a8b1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a8e1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a906`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a92b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a955`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a981`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a9a5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002a9ea`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002aa12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002aa34`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002aa56`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14002aa78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002add0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002add0`
- `vdsutil!OpenDevice` at `0x14002ab13`
- `vdsutil!OpenDevice` at `0x14002ab13`
- `vdsutil!IsDiskClustered` at `0x14002abb5`
- `vdsutil!IsDiskClustered` at `0x14002abb5`
- `vdsutil!IsDiskReadOnly` at `0x14002aca7`
- `vdsutil!IsDiskReadOnly` at `0x14002aca7`
- `vdsutil!IsDiskCurrentStateReadOnly` at `0x14002ad23`
- `vdsutil!IsDiskCurrentStateReadOnly` at `0x14002ad23`
- `vdsutil!GetDiskOfflineReason` at `0x14002ac4c`
- `vdsutil!GetDiskOfflineReason` at `0x14002ac4c`
- `vdsutil!GetDiskRedundancyCount` at `0x14002ada4`
- `vdsutil!GetDiskRedundancyCount` at `0x14002ada4`
- `vdsutil!IsClientSKU` at `0x14002ad86`
- `vdsutil!IsClientSKU` at `0x14002ad86`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002a860`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002a860`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002adff`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002adff`
- `vdsutil!VdsTraceW` at `0x14002a9ce`
- `vdsutil!VdsTraceW` at `0x14002aaf4`
- `vdsutil!VdsTraceW` at `0x14002ab3c`
- `vdsutil!VdsTraceW` at `0x14002abde`
- `vdsutil!VdsTraceW` at `0x14002ac76`
- `vdsutil!VdsTraceW` at `0x14002acd6`
- `vdsutil!VdsTraceW` at `0x14002ad4a`
- `vdsutil!VdsTraceW` at `0x14002a9ce`
- `vdsutil!VdsTraceW` at `0x14002aaf4`
- `vdsutil!VdsTraceW` at `0x14002ab3c`
- `vdsutil!VdsTraceW` at `0x14002abde`
- `vdsutil!VdsTraceW` at `0x14002ac76`
- `vdsutil!VdsTraceW` at `0x14002acd6`
- `vdsutil!VdsTraceW` at `0x14002ad4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsRawDiskLun::GetProperties2(CVdsRawDiskLun *this, struct _VDS_DISK_PROP2 *a2)
{
  int v4; // r14d
  signed int v5; // esi
  int v6; // eax
  WCHAR *v7; // rax
  int v8; // eax
  WCHAR *v9; // rax
  int v10; // eax
  WCHAR *v11; // rax
  int v12; // eax
  WCHAR *v13; // rax
  const WCHAR *v14; // rcx
  int v15; // eax
  WCHAR *v16; // rax
  const WCHAR *v17; // rbx
  int v18; // eax
  const WCHAR *v19; // rcx
  int v20; // eax
  WCHAR *v21; // rax
  const WCHAR *v22; // rbx
  int v23; // eax
  const WCHAR *v24; // rbx
  int v25; // eax
  const WCHAR *v26; // rbx
  int v27; // eax
  const WCHAR *v28; // rbx
  int v29; // eax
  const WCHAR *v30; // rbx
  int v31; // eax
  __int64 v32; // rcx
  unsigned int v33; // eax
  int v34; // ebx
  int v35; // eax
  unsigned int v36; // eax
  int v37; // ebx
  int v38; // eax
  unsigned int v39; // eax
  unsigned int DiskOfflineReason; // eax
  int v41; // r12d
  VDS_DISK_OFFLINE_REASON v42; // eax
  unsigned int v43; // eax
  _DWORD *v44; // r12
  int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  int v48; // ebx
  int v49; // eax
  unsigned int v50; // eax
  __int64 v52; // [rsp+20h] [rbp-40h]
  char v53; // [rsp+30h] [rbp-30h] BYREF
  char v54; // [rsp+31h] [rbp-2Fh] BYREF
  _BYTE v55[2]; // [rsp+32h] [rbp-2Eh] BYREF
  VDS_DISK_OFFLINE_REASON v56; // [rsp+34h] [rbp-2Ch] BYREF
  int v57; // [rsp+38h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v59[24]; // [rsp+48h] [rbp-18h] BYREF
  char v60; // [rsp+A0h] [rbp+40h] BYREF
  char v61; // [rsp+B0h] [rbp+50h] BYREF
  char v62; // [rsp+B8h] [rbp+58h] BYREF

  v60 = 0;
  hObject = 0;
  v61 = 0;
  v62 = 0;
  v56 = VDSDiskOfflineReasonNone;
  v55[0] = 0;
  v54 = 0;
  v53 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v59, 0x5Eu, "CVdsRawDiskLun::GetProperties2() (IVdsDisk)");
  memset_0(a2, 0, sizeof(struct _VDS_DISK_PROP2));
  EnterCriticalSection(&g_GlobalCriticalSection);
  if ( *((_DWORD *)this + 80) == 1 )
  {
    v4 = -2147212277;
    goto LABEL_67;
  }
  v5 = 0;
  a2->id = *(VDS_OBJECT_ID *)((char *)this + 104);
  v6 = lstrlenW(*((LPCWSTR *)this + 26));
  v7 = (WCHAR *)CoTaskMemAlloc(2LL * (v6 + 1));
  if ( v7 )
  {
    a2->pwszFriendlyName = v7;
    v8 = lstrlenW(*((LPCWSTR *)this + 27));
    v9 = (WCHAR *)CoTaskMemAlloc(2LL * (v8 + 1));
    if ( v9 )
    {
      a2->pwszAdaptorName = v9;
      v10 = lstrlenW(*((LPCWSTR *)this + 28));
      v11 = (WCHAR *)CoTaskMemAlloc(2LL * (v10 + 1));
      if ( v11 )
      {
        a2->pwszDevicePath = v11;
        v12 = lstrlenW(*((LPCWSTR *)this + 25));
        v13 = (WCHAR *)CoTaskMemAlloc(2LL * (v12 + 1));
        if ( v13 )
        {
          a2->pwszName = v13;
          v14 = (const WCHAR *)*((_QWORD *)this + 24);
          if ( !v14 )
            goto LABEL_11;
          v15 = lstrlenW(v14);
          v16 = (WCHAR *)CoTaskMemAlloc(2LL * (v15 + 1));
          if ( v16 )
          {
            a2->pwszDiskAddress = v16;
            v17 = (const WCHAR *)*((_QWORD *)this + 24);
            v18 = lstrlenW(v17);
            StringCchCopyW(a2->pwszDiskAddress, v18 + 1, v17);
LABEL_11:
            v19 = (const WCHAR *)*((_QWORD *)this + 29);
            if ( v19 )
            {
              v20 = lstrlenW(v19);
              v21 = (WCHAR *)CoTaskMemAlloc(2LL * (v20 + 1));
              if ( !v21 )
              {
                v4 = -2147024882;
                VdsTraceW(0, L"CVdsRawDiskLun::GetProperties2(), 1");
                goto LABEL_62;
              }
              a2->pwszLocationPath = v21;
              v22 = (const WCHAR *)*((_QWORD *)this + 29);
              v23 = lstrlenW(v22);
              StringCchCopyW(a2->pwszLocationPath, v23 + 1, v22);
            }
            v4 = 0;
            v24 = (const WCHAR *)*((_QWORD *)this + 26);
            v25 = lstrlenW(v24);
            StringCchCopyW(a2->pwszFriendlyName, v25 + 1, v24);
            v26 = (const WCHAR *)*((_QWORD *)this + 27);
            v27 = lstrlenW(v26);
            StringCchCopyW(a2->pwszAdaptorName, v27 + 1, v26);
            v28 = (const WCHAR *)*((_QWORD *)this + 28);
            v29 = lstrlenW(v28);
            StringCchCopyW(a2->pwszDevicePath, v29 + 1, v28);
            v30 = (const WCHAR *)*((_QWORD *)this + 25);
            v31 = lstrlenW(v30);
            StringCchCopyW(a2->pwszName, v31 + 1, v30);
            a2->dwDeviceType = *((_DWORD *)this + 34);
            a2->dwMediaType = *((_DWORD *)this + 35);
            a2->BusType = *((_DWORD *)this + 42);
            a2->PartitionStyle = *((_DWORD *)this + 43);
            a2->ullSize = *((_QWORD *)this + 18);
            a2->ulBytesPerSector = *((_DWORD *)this + 38);
            a2->ulSectorsPerTrack = *((_DWORD *)this + 39);
            a2->ulTracksPerCylinder = *((_DWORD *)this + 40);
            v32 = *((_QWORD *)this + 25);
            if ( !v32 )
            {
              VdsTraceW(0, L"CVdsRawDiskLun::GetProperties2(), 1");
              *((_DWORD *)this + 30) = 0;
              *((_DWORD *)this + 33) = 0;
              goto LABEL_62;
            }
            v33 = OpenDevice(v32, 0x80000000LL, &hObject);
            v34 = v33;
            if ( v33 )
            {
              VdsTraceW(
                0,
                L"CVdsRawDiskLun::GetProperties2(), 2, error=%ld, name=%s, number=%ld",
                v33,
                *((_QWORD *)this + 25),
                *((_DWORD *)this + 76));
              if ( v34 == 5
                || v34 == 32
                || (*((_DWORD *)this + 30) = 0,
                    *((_DWORD *)this + 33) = 0,
                    a2->status = VDS_DS_UNKNOWN,
                    a2->health = *((_DWORD *)this + 33),
                    v34 > 0) )
              {
                v5 = (unsigned __int16)v34 | 0x80070000;
              }
              else
              {
                v5 = v34;
              }
              goto LABEL_62;
            }
            v35 = *((_DWORD *)this + 34);
            if ( v35 != 2 && v35 != 51 )
            {
              v36 = IsDiskClustered(hObject, &v60, v55, &v54, &v61);
              v37 = v36;
              if ( v36 )
              {
                LODWORD(v52) = *((_DWORD *)this + 76);
                VdsTraceW(
                  0,
                  L"CVdsRawDiskLun::GetProperties2(), 3, error=%ld, name=%s, number=%ld",
                  v36,
                  *((_QWORD *)this + 25),
                  v52);
                if ( v37 > 0 )
                  v5 = (unsigned __int16)v37 | 0x80070000;
                else
                  v5 = v37;
              }
              v38 = *((_DWORD *)this + 41);
              if ( v60 )
                v39 = v38 | 0x20;
              else
                v39 = v38 & 0xFFFFFFDF;
              *((_DWORD *)this + 41) = v39;
              *((_DWORD *)this + 33) = 1;
              *((_DWORD *)this + 30) = v61 != 0 ? 1 : 4;
            }
            a2->status = *((_DWORD *)this + 30);
            a2->health = *((_DWORD *)this + 33);
            if ( *((_DWORD *)this + 30) == 4 )
            {
              DiskOfflineReason = GetDiskOfflineReason(hObject, &v56);
              v41 = DiskOfflineReason;
              if ( !DiskOfflineReason )
              {
                v42 = v56;
                *((_DWORD *)this + 31) = v56;
                goto LABEL_40;
              }
              LODWORD(v52) = *((_DWORD *)this + 76);
              VdsTraceW(
                0,
                L"CVdsRawDiskLun::GetProperties2(), 4, error=%ld, name=%s, number=%ld",
                DiskOfflineReason,
                *((_QWORD *)this + 25),
                v52);
              if ( v5 >= 0 )
              {
                if ( v41 > 0 )
                  v5 = (unsigned __int16)v41 | 0x80070000;
                else
                  v5 = v41;
              }
            }
            v42 = VDSDiskOfflineReasonNone;
            *((_DWORD *)this + 31) = 0;
LABEL_40:
            a2->OfflineReason = v42;
            v43 = IsDiskReadOnly(hObject, &v62);
            v57 = v43;
            if ( v43 )
            {
              v44 = (_DWORD *)((char *)this + 304);
              LODWORD(v52) = *((_DWORD *)this + 76);
              VdsTraceW(
                0,
                L"CVdsRawDiskLun::GetProperties2(), 5, error=%ld, name=%s, number=%ld",
                v43,
                *((_QWORD *)this + 25),
                v52);
              if ( v5 >= 0 )
              {
                if ( v57 > 0 )
                  v5 = (unsigned __int16)v57 | 0x80070000;
                else
                  v5 = v57;
              }
            }
            else
            {
              v44 = (_DWORD *)((char *)this + 304);
            }
            v45 = *((_DWORD *)this + 41);
            if ( v62 )
            {
              v46 = v45 | 0x40;
            }
            else
            {
              v46 = v45 & 0xFFFFFFBF;
              v44 = (_DWORD *)((char *)this + 304);
            }
            *((_DWORD *)this + 41) = v46;
            v47 = IsDiskCurrentStateReadOnly(hObject, &v53);
            v48 = v47;
            if ( v47 )
            {
              LODWORD(v52) = *v44;
              VdsTraceW(
                0,
                L"CVdsRawDiskLun::GetProperties2(), 6, error=%ld, name=%s, number=%ld",
                v47,
                *((_QWORD *)this + 25),
                v52);
              if ( v5 >= 0 )
              {
                if ( v48 > 0 )
                  v5 = (unsigned __int16)v48 | 0x80070000;
                else
                  v5 = v48;
              }
            }
            v49 = *((_DWORD *)this + 41);
            if ( v53 )
              v50 = v49 | 0x8000;
            else
              v50 = v49 & 0xFFFF7FFF;
            *((_DWORD *)this + 41) = v50;
            if ( (unsigned int)IsClientSKU() )
            {
              v57 = 0;
              *((_DWORD *)this + 41) |= 0x10000u;
              GetDiskRedundancyCount(hObject, &v57);
              if ( (unsigned int)v57 >= 2 )
                *((_DWORD *)this + 41) &= ~0x10000u;
            }
            a2->ulFlags = *((_DWORD *)this + 41);
            goto LABEL_62;
          }
        }
      }
    }
  }
  v4 = -2147024882;
LABEL_62:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
  if ( v4 < 0 || v5 < 0 )
    v4 = 272149;
LABEL_67:
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v59);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002a810  mov     [rsp-38h+arg_8], rbx
0x14002a815  push    rbp
0x14002a816  push    rsi
0x14002a817  push    rdi
0x14002a818  push    r12
0x14002a81a  push    r13
0x14002a81c  push    r14
0x14002a81e  push    r15
0x14002a820  mov     rbp, rsp
0x14002a823  sub     rsp, 60h
0x14002a827  mov     r15, rdx
0x14002a82a  mov     rdi, rcx
0x14002a82d  xor     r12d, r12d
0x14002a830  mov     [rbp+arg_0], r12b
0x14002a834  mov     [rbp+hObject], r12
0x14002a838  mov     [rbp+arg_10], r12b
0x14002a83c  mov     [rbp+arg_18], r12b
0x14002a840  mov     [rbp+var_2C], r12d
0x14002a844  mov     [rbp+var_2E], r12b
0x14002a848  mov     [rbp+var_2F], r12b
0x14002a84c  mov     [rbp+var_30], r12b
0x14002a850  lea     r8, aCvdsrawdisklun_13; "CVdsRawDiskLun::GetProperties2() (IVdsD"...
0x14002a857  lea     edx, [r12+5Eh]
0x14002a85c  lea     rcx, [rbp+var_18]
0x14002a860  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002a866  nop
0x14002a867  xor     edx, edx; Val
0x14002a869  mov     r8d, 88h; Size
0x14002a86f  mov     rcx, r15; void *
0x14002a872  call    memset_0
0x14002a877  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002a87e  call    cs:__imp_EnterCriticalSection
0x14002a884  nop
0x14002a885  lea     r13d, [r12+1]
0x14002a88a  cmp     [rdi+140h], r13d
0x14002a891  jnz     short loc_14002A89E
0x14002a893  mov     r14d, 8004240Bh
0x14002a899  jmp     loc_14002ADED
0x14002a89e  mov     esi, r12d
0x14002a8a1  movups  xmm0, xmmword ptr [rdi+68h]
0x14002a8a5  movdqu  xmmword ptr [r15], xmm0
0x14002a8aa  mov     rcx, [rdi+0D0h]; lpString
0x14002a8b1  call    cs:__imp_lstrlenW
0x14002a8b7  add     eax, r13d
0x14002a8ba  movsxd  rcx, eax
0x14002a8bd  add     rcx, rcx; cb
0x14002a8c0  call    cs:__imp_CoTaskMemAlloc
0x14002a8c6  test    rax, rax
0x14002a8c9  jnz     short loc_14002A8D6
0x14002a8cb  mov     r14d, 8007000Eh
0x14002a8d1  jmp     loc_14002ADC2
0x14002a8d6  mov     [r15+68h], rax
0x14002a8da  mov     rcx, [rdi+0D8h]; lpString
0x14002a8e1  call    cs:__imp_lstrlenW
0x14002a8e7  add     eax, r13d
0x14002a8ea  movsxd  rcx, eax
0x14002a8ed  add     rcx, rcx; cb
0x14002a8f0  call    cs:__imp_CoTaskMemAlloc
0x14002a8f6  test    rax, rax
0x14002a8f9  jz      short loc_14002A8CB
0x14002a8fb  mov     [r15+70h], rax
0x14002a8ff  mov     rcx, [rdi+0E0h]; lpString
0x14002a906  call    cs:__imp_lstrlenW
0x14002a90c  add     eax, r13d
0x14002a90f  movsxd  rcx, eax
0x14002a912  add     rcx, rcx; cb
0x14002a915  call    cs:__imp_CoTaskMemAlloc
0x14002a91b  test    rax, rax
0x14002a91e  jz      short loc_14002A8CB
0x14002a920  mov     [r15+78h], rax
0x14002a924  mov     rcx, [rdi+0C8h]; lpString
0x14002a92b  call    cs:__imp_lstrlenW
0x14002a931  add     eax, r13d
0x14002a934  movsxd  rcx, eax
0x14002a937  add     rcx, rcx; cb
0x14002a93a  call    cs:__imp_CoTaskMemAlloc
0x14002a940  test    rax, rax
0x14002a943  jz      short loc_14002A8CB
0x14002a945  mov     [r15+60h], rax
0x14002a949  mov     rcx, [rdi+0C0h]; lpString
0x14002a950  test    rcx, rcx
0x14002a953  jz      short loc_14002A999
0x14002a955  call    cs:__imp_lstrlenW
0x14002a95b  add     eax, r13d
0x14002a95e  movsxd  rcx, eax
0x14002a961  add     rcx, rcx; cb
0x14002a964  call    cs:__imp_CoTaskMemAlloc
0x14002a96a  test    rax, rax
0x14002a96d  jz      loc_14002A8CB
0x14002a973  mov     [r15+58h], rax
0x14002a977  mov     rbx, [rdi+0C0h]
0x14002a97e  mov     rcx, rbx; lpString
0x14002a981  call    cs:__imp_lstrlenW
0x14002a987  add     eax, r13d
0x14002a98a  movsxd  rdx, eax; unsigned __int64
0x14002a98d  mov     r8, rbx; unsigned __int16 *
0x14002a990  mov     rcx, [r15+58h]; unsigned __int16 *
0x14002a994  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002a999  mov     rcx, [rdi+0E8h]; lpString
0x14002a9a0  test    rcx, rcx
0x14002a9a3  jz      short loc_14002AA05
0x14002a9a5  call    cs:__imp_lstrlenW
0x14002a9ab  add     eax, r13d
0x14002a9ae  movsxd  rcx, eax
0x14002a9b1  add     rcx, rcx; cb
0x14002a9b4  call    cs:__imp_CoTaskMemAlloc
0x14002a9ba  test    rax, rax
0x14002a9bd  jnz     short loc_14002A9D9
0x14002a9bf  mov     r14d, 8007000Eh
0x14002a9c5  lea     rdx, aCvdsrawdisklun_85; "CVdsRawDiskLun::GetProperties2(), 1"
0x14002a9cc  xor     ecx, ecx
0x14002a9ce  call    cs:__imp_VdsTraceW
0x14002a9d4  jmp     loc_14002ADC2
0x14002a9d9  mov     [r15+80h], rax
0x14002a9e0  mov     rbx, [rdi+0E8h]
0x14002a9e7  mov     rcx, rbx; lpString
0x14002a9ea  call    cs:__imp_lstrlenW
0x14002a9f0  add     eax, r13d
0x14002a9f3  movsxd  rdx, eax; unsigned __int64
0x14002a9f6  mov     r8, rbx; unsigned __int16 *
0x14002a9f9  mov     rcx, [r15+80h]; unsigned __int16 *
0x14002aa00  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002aa05  mov     r14d, r12d
0x14002aa08  mov     rbx, [rdi+0D0h]
0x14002aa0f  mov     rcx, rbx; lpString
0x14002aa12  call    cs:__imp_lstrlenW
0x14002aa18  add     eax, r13d
0x14002aa1b  movsxd  rdx, eax; unsigned __int64
0x14002aa1e  mov     r8, rbx; unsigned __int16 *
0x14002aa21  mov     rcx, [r15+68h]; unsigned __int16 *
0x14002aa25  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002aa2a  mov     rbx, [rdi+0D8h]
0x14002aa31  mov     rcx, rbx; lpString
0x14002aa34  call    cs:__imp_lstrlenW
0x14002aa3a  add     eax, r13d
0x14002aa3d  movsxd  rdx, eax; unsigned __int64
0x14002aa40  mov     r8, rbx; unsigned __int16 *
0x14002aa43  mov     rcx, [r15+70h]; unsigned __int16 *
0x14002aa47  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002aa4c  mov     rbx, [rdi+0E0h]
0x14002aa53  mov     rcx, rbx; lpString
0x14002aa56  call    cs:__imp_lstrlenW
0x14002aa5c  add     eax, r13d
0x14002aa5f  movsxd  rdx, eax; unsigned __int64
0x14002aa62  mov     r8, rbx; unsigned __int16 *
0x14002aa65  mov     rcx, [r15+78h]; unsigned __int16 *
0x14002aa69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002aa6e  mov     rbx, [rdi+0C8h]
0x14002aa75  mov     rcx, rbx; lpString
0x14002aa78  call    cs:__imp_lstrlenW
0x14002aa7e  add     eax, r13d
0x14002aa81  movsxd  rdx, eax; unsigned __int64
0x14002aa84  mov     r8, rbx; unsigned __int16 *
0x14002aa87  mov     rcx, [r15+60h]; unsigned __int16 *
0x14002aa8b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002aa90  mov     eax, [rdi+88h]
0x14002aa96  mov     [r15+20h], eax
0x14002aa9a  mov     eax, [rdi+8Ch]
0x14002aaa0  mov     [r15+24h], eax
0x14002aaa4  mov     eax, [rdi+0A8h]
0x14002aaaa  mov     [r15+40h], eax
0x14002aaae  mov     eax, [rdi+0ACh]
0x14002aab4  mov     [r15+44h], eax
0x14002aab8  mov     rax, [rdi+90h]
0x14002aabf  mov     [r15+28h], rax
0x14002aac3  mov     eax, [rdi+98h]
0x14002aac9  mov     [r15+30h], eax
0x14002aacd  mov     eax, [rdi+9Ch]
0x14002aad3  mov     [r15+34h], eax
0x14002aad7  mov     eax, [rdi+0A0h]
0x14002aadd  mov     [r15+38h], eax
0x14002aae1  mov     rcx, [rdi+0C8h]
0x14002aae8  test    rcx, rcx
0x14002aaeb  jnz     short loc_14002AB0A
0x14002aaed  lea     rdx, aCvdsrawdisklun_85; "CVdsRawDiskLun::GetProperties2(), 1"
0x14002aaf4  call    cs:__imp_VdsTraceW
0x14002aafa  mov     [rdi+78h], r12d
0x14002aafe  mov     [rdi+84h], r12d
0x14002ab05  jmp     loc_14002ADC2
0x14002ab0a  lea     r8, [rbp+hObject]
0x14002ab0e  mov     edx, 80000000h
0x14002ab13  call    cs:__imp_OpenDevice
0x14002ab19  mov     ebx, eax
0x14002ab1b  test    eax, eax
0x14002ab1d  jz      short loc_14002AB7E
0x14002ab1f  mov     ecx, [rdi+130h]
0x14002ab25  mov     dword ptr [rsp+60h+var_40], ecx
0x14002ab29  mov     r9, [rdi+0C8h]
0x14002ab30  mov     r8d, eax
0x14002ab33  lea     rdx, aCvdsrawdisklun_87; "CVdsRawDiskLun::GetProperties2(), 2, er"...
0x14002ab3a  xor     ecx, ecx
0x14002ab3c  call    cs:__imp_VdsTraceW
0x14002ab42  cmp     ebx, 5
0x14002ab45  jz      short loc_14002AB70
0x14002ab47  cmp     ebx, 20h ; ' '
0x14002ab4a  jz      short loc_14002AB70
0x14002ab4c  mov     [rdi+78h], r12d
0x14002ab50  mov     [rdi+84h], r12d
0x14002ab57  mov     [r15+10h], r12d
0x14002ab5b  mov     eax, [rdi+84h]
0x14002ab61  mov     [r15+1Ch], eax
0x14002ab65  test    ebx, ebx
0x14002ab67  jg      short loc_14002AB70
0x14002ab69  mov     esi, ebx
0x14002ab6b  jmp     loc_14002ADC2
0x14002ab70  movzx   esi, bx
0x14002ab73  or      esi, 80070000h
0x14002ab79  jmp     loc_14002ADC2
0x14002ab7e  mov     eax, [rdi+88h]
0x14002ab84  mov     r13d, 80070000h
0x14002ab8a  cmp     eax, 2
0x14002ab8d  jz      loc_14002AC26
0x14002ab93  cmp     eax, 33h ; '3'
0x14002ab96  jz      loc_14002AC26
0x14002ab9c  lea     rax, [rbp+arg_10]
0x14002aba0  mov     [rsp+60h+var_40], rax
0x14002aba5  lea     r9, [rbp+var_2F]
0x14002aba9  lea     r8, [rbp+var_2E]
0x14002abad  lea     rdx, [rbp+arg_0]
0x14002abb1  mov     rcx, [rbp+hObject]
0x14002abb5  call    cs:__imp_IsDiskClustered
0x14002abbb  mov     ebx, eax
0x14002abbd  test    eax, eax
0x14002abbf  jz      short loc_14002ABF2
0x14002abc1  mov     ecx, [rdi+130h]
0x14002abc7  mov     dword ptr [rsp+60h+var_40], ecx
0x14002abcb  mov     r9, [rdi+0C8h]
0x14002abd2  mov     r8d, eax
0x14002abd5  lea     rdx, aCvdsrawdisklun_14; "CVdsRawDiskLun::GetProperties2(), 3, er"...
0x14002abdc  xor     ecx, ecx
0x14002abde  call    cs:__imp_VdsTraceW
0x14002abe4  test    ebx, ebx
0x14002abe6  jg      short loc_14002ABEC
0x14002abe8  mov     esi, ebx
0x14002abea  jmp     short loc_14002ABF2
0x14002abec  movzx   esi, bx
0x14002abef  or      esi, r13d
0x14002abf2  mov     eax, [rdi+0A4h]
0x14002abf8  cmp     [rbp+arg_0], r12b
0x14002abfc  jz      short loc_14002AC03
0x14002abfe  or      eax, 20h
0x14002ac01  jmp     short loc_14002AC06
0x14002ac03  and     eax, 0FFFFFFDFh
0x14002ac06  mov     [rdi+0A4h], eax
0x14002ac0c  mov     dword ptr [rdi+84h], 1
0x14002ac16  mov     al, [rbp+arg_10]
0x14002ac19  neg     al
0x14002ac1b  sbb     ecx, ecx
0x14002ac1d  and     ecx, 0FFFFFFFDh
0x14002ac20  add     ecx, 4
0x14002ac23  mov     [rdi+78h], ecx
0x14002ac26  mov     eax, [rdi+78h]
0x14002ac29  mov     [r15+10h], eax
0x14002ac2d  mov     eax, [rdi+84h]
0x14002ac33  mov     [r15+1Ch], eax
0x14002ac37  lea     rbx, [rdi+130h]
0x14002ac3e  cmp     dword ptr [rdi+78h], 4
0x14002ac42  jnz     short loc_14002AC94
0x14002ac44  lea     rdx, [rbp+var_2C]
0x14002ac48  mov     rcx, [rbp+hObject]
0x14002ac4c  call    cs:__imp_GetDiskOfflineReason
0x14002ac52  mov     r12d, eax
0x14002ac55  test    eax, eax
0x14002ac57  jz      loc_14002ACEB
0x14002ac5d  mov     ecx, [rbx]
0x14002ac5f  mov     dword ptr [rsp+60h+var_40], ecx
0x14002ac63  mov     r9, [rdi+0C8h]
0x14002ac6a  mov     r8d, eax
0x14002ac6d  lea     rdx, aCvdsrawdisklun_10; "CVdsRawDiskLun::GetProperties2(), 4, er"...
0x14002ac74  xor     ecx, ecx
0x14002ac76  call    cs:__imp_VdsTraceW
0x14002ac7c  test    esi, esi
0x14002ac7e  js      short loc_14002AC91
0x14002ac80  test    r12d, r12d
0x14002ac83  jg      short loc_14002AC8A
0x14002ac85  mov     esi, r12d
0x14002ac88  jmp     short loc_14002AC91
0x14002ac8a  movzx   esi, r12w
0x14002ac8e  or      esi, r13d
0x14002ac91  xor     r12d, r12d
0x14002ac94  mov     eax, r12d
0x14002ac97  mov     [rdi+7Ch], r12d
0x14002ac9b  mov     [r15+14h], eax
0x14002ac9f  lea     rdx, [rbp+arg_18]
0x14002aca3  mov     rcx, [rbp+hObject]
0x14002aca7  call    cs:__imp_IsDiskReadOnly
0x14002acad  mov     [rbp+var_28], eax
0x14002acb0  test    eax, eax
0x14002acb2  jz      short loc_14002ACFB
0x14002acb4  lea     r12, [rdi+130h]
0x14002acbb  mov     ecx, [r12]
0x14002acbf  mov     dword ptr [rsp+60h+var_40], ecx
0x14002acc3  mov     r9, [rdi+0C8h]
0x14002acca  mov     r8d, eax
0x14002accd  lea     rdx, aCvdsrawdisklun_7; "CVdsRawDiskLun::GetProperties2(), 5, er"...
0x14002acd4  xor     ecx, ecx
0x14002acd6  call    cs:__imp_VdsTraceW
0x14002acdc  test    esi, esi
0x14002acde  js      short loc_14002ACFE
0x14002ace0  mov     eax, [rbp+var_28]
  ... truncated ...
```
