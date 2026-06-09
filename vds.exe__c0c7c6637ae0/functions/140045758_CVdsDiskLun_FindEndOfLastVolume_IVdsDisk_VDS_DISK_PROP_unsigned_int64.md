# CVdsDiskLun::FindEndOfLastVolume(IVdsDisk *,_VDS_DISK_PROP *,unsigned __int64 *)

- ea: `0x140045758`
- end: `0x140045c5c`
- name: `?FindEndOfLastVolume@CVdsDiskLun@@AEAAJPEAUIVdsDisk@@PEAU_VDS_DISK_PROP@@PEA_K@Z`
- size: `1284`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this, struct IVdsDisk *, struct _VDS_DISK_PROP *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001c250`

## callees

- `0x140045758`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400459a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045a2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045b9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400459a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045a2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045b9d`
- `vdsutil!VdsTraceEx` at `0x140045809`
- `vdsutil!VdsTraceEx` at `0x140045b8e`
- `vdsutil!VdsTraceEx` at `0x140045809`
- `vdsutil!VdsTraceEx` at `0x140045b8e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400457b7`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400457b7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140045c41`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140045c41`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsDiskLun::FindEndOfLastVolume(
        CVdsDiskLun *this,
        struct IVdsDisk *a2,
        struct _VDS_DISK_PROP *a3,
        unsigned __int64 *a4)
{
  int v7; // eax
  int v8; // ebx
  unsigned __int64 v9; // rsi
  __int64 v10; // r8
  int v11; // ecx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  unsigned __int64 v20; // rdx
  __int64 i; // r8
  __int64 v22; // rax
  int v24; // [rsp+40h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-31h] BYREF
  __int64 v26; // [rsp+50h] [rbp-29h] BYREF
  __int64 v27; // [rsp+58h] [rbp-21h] BYREF
  __int64 v28; // [rsp+60h] [rbp-19h] BYREF
  __int64 v29; // [rsp+68h] [rbp-11h] BYREF
  __int64 v30; // [rsp+70h] [rbp-9h] BYREF
  __int64 v31; // [rsp+78h] [rbp-1h] BYREF
  int v32; // [rsp+80h] [rbp+7h] BYREF
  int v33; // [rsp+84h] [rbp+Bh] BYREF
  __int64 v34; // [rsp+88h] [rbp+Fh] BYREF
  _BYTE v35[64]; // [rsp+90h] [rbp+17h] BYREF

  v30 = 0;
  v32 = 0;
  v27 = 0;
  v33 = 0;
  v29 = 0;
  v26 = 0;
  v31 = 0;
  v28 = 0;
  v24 = 0;
  pv = 0;
  v34 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v35, 0x5Eu, "CVdsDiskLun::FindEndOfLastVolume()");
  if ( a2 && a3 && a4 )
  {
    *a4 = 0;
    v7 = ((__int64 (__fastcall *)(struct IVdsDisk *, LPVOID *, int *))a2->lpVtbl->QueryExtents)(a2, &pv, &v24);
    v8 = v7;
    if ( v7 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::FindEndOfLastVolume, 2, hr=%lX", (unsigned int)v7);
      goto LABEL_65;
    }
    v9 = 0;
    v10 = 0;
    if ( (a3->ulFlags & 0x2000) != 0 )
    {
      if ( v24 > 0 )
      {
        do
        {
          v11 = *((_DWORD *)pv + 20 * (int)v10 + 4);
          if ( (unsigned int)(v11 - 1) > 1
            && v11 != 0x7FFF
            && *((_QWORD *)pv + 10 * (int)v10 + 4) + *((_QWORD *)pv + 10 * (int)v10 + 3) > v9 )
          {
            v9 = *((_QWORD *)pv + 10 * (int)v10 + 4) + *((_QWORD *)pv + 10 * (int)v10 + 3);
          }
          v10 = (unsigned int)(v10 + 1);
        }
        while ( (int)v10 < v24 );
      }
      v12 = ((__int64 (__fastcall *)(struct IVdsDisk *, __int64 *, __int64))a2->lpVtbl->GetPack)(a2, &v34, v10);
      v8 = v12;
      if ( v12 < 0 )
      {
        VdsTraceEx(94, 0, "CVdsDiskLun::FindEndOfLastVolume, 3, hr=%lX", (unsigned int)v12);
        goto LABEL_65;
      }
      v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 40LL))(v34, &v31);
      v8 = v13;
      if ( v13 < 0 )
      {
        VdsTraceEx(94, 0, "CVdsDiskLun::FindEndOfLastVolume, 3.5, hr=%lX", (unsigned int)v13);
        goto LABEL_65;
      }
      while ( v8 >= 0 )
      {
        if ( v8 == 1 )
          break;
        v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v31 + 24LL))(
                v31,
                1,
                &v30,
                &v32);
        v8 = v14;
        if ( v14 == 1 )
          break;
        if ( v14 < 0 )
        {
          VdsTraceEx(94, 0, "CVdsDiskLun::FindEndOfLastVolume, 4, hr=%lX", (unsigned int)v14);
          goto LABEL_65;
        }
        v15 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v30)(v30, &IID_IVdsVolume, &v29);
        v8 = v15;
        if ( v15 < 0 )
        {
          VdsTraceEx(94, 0, "CVdsDiskLun::FindEndOfLastVolume, 5, hr=%lX", (unsigned int)v15);
          goto LABEL_65;
        }
        v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 40LL))(v29, &v28);
        v8 = v16;
        if ( v16 < 0 )
        {
          VdsTraceEx(94, 0, "CVdsDiskLun::FindEndOfLastVolume, 6, hr=%lX", (unsigned int)v16);
          goto LABEL_65;
        }
        while ( v8 != 1 )
        {
          v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v28 + 24LL))(
                  v28,
                  1,
                  &v27,
                  &v33);
          v8 = v17;
          if ( v17 == 1 )
            break;
          if ( v17 < 0 )
          {
            VdsTraceEx(94, 0, "CVdsDiskLun::FindEndOfLastVolume, 7, hr=%lX", (unsigned int)v17);
            goto LABEL_65;
          }
          v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v27)(v27, &IID_IVdsVolumePlex, &v26);
          v8 = v18;
          if ( v18 < 0 )
          {
            VdsTraceEx(94, 0, "CVdsDiskLun::FindEndOfLastVolume, 8, hr=%lX", (unsigned int)v18);
            goto LABEL_65;
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          v24 = 0;
          v19 = (*(__int64 (__fastcall **)(__int64, LPVOID *, int *))(*(_QWORD *)v26 + 40LL))(v26, &pv, &v24);
          v8 = v19;
          if ( v19 < 0 )
          {
            VdsTraceEx(94, 0, "CVdsDiskLun::FindEndOfLastVolume, 9, hr=%lX", (unsigned int)v19);
            goto LABEL_65;
          }
          for ( i = 0; (int)i < v24; i = (unsigned int)(i + 1) )
          {
            v20 = 10LL * (int)i;
            v22 = *((_QWORD *)pv + 10 * (int)i) - *(_QWORD *)&a3->id.Data1;
            if ( !v22 )
              v22 = *((_QWORD *)pv + 10 * (int)i + 1) - *(_QWORD *)a3->id.Data4;
            if ( !v22 )
            {
              v20 = *((_QWORD *)pv + 10 * (int)i + 4) + *((_QWORD *)pv + 10 * (int)i + 3);
              if ( v20 > v9 )
                v9 = *((_QWORD *)pv + 10 * (int)i + 4) + *((_QWORD *)pv + 10 * (int)i + 3);
            }
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( v26 )
          {
            (*(void (__fastcall **)(__int64, unsigned __int64, __int64))(*(_QWORD *)v26 + 16LL))(v26, v20, i);
            v26 = 0;
          }
          if ( v27 )
          {
            (*(void (__fastcall **)(__int64, unsigned __int64, __int64))(*(_QWORD *)v27 + 16LL))(v27, v20, i);
            v27 = 0;
          }
        }
        if ( v28 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          v28 = 0;
        }
        if ( v29 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          v29 = 0;
        }
        if ( v30 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          v30 = 0;
        }
      }
      if ( v31 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        v31 = 0;
      }
    }
    else if ( v24 > 0 )
    {
      do
      {
        if ( *((_DWORD *)pv + 20 * (int)v10 + 4) != 0x7FFF
          && *((_DWORD *)pv + 20 * (int)v10 + 4) != 1
          && *((_QWORD *)pv + 10 * (int)v10 + 4) + *((_QWORD *)pv + 10 * (int)v10 + 3) > v9 )
        {
          v9 = *((_QWORD *)pv + 10 * (int)v10 + 4) + *((_QWORD *)pv + 10 * (int)v10 + 3);
        }
        LODWORD(v10) = v10 + 1;
      }
      while ( (int)v10 < v24 );
    }
    *a4 = v9;
  }
  else
  {
    v8 = -2147024809;
    VdsTraceEx(
      94,
      0,
      "CVdsDiskLun::FindEndOfLastVolume, 1, disk=%p, prop=%p, offset=%p, hr=%lX",
      a2,
      a3,
      a4,
      -2147024809);
  }
LABEL_65:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v35);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140045758  push    rbp
0x14004575a  push    rbx
0x14004575b  push    rsi
0x14004575c  push    r12
0x14004575e  push    r13
0x140045760  push    r14
0x140045762  push    r15
0x140045764  lea     rbp, [rsp-27h]
0x140045769  sub     rsp, 0A0h
0x140045770  mov     r12, r9
0x140045773  mov     r15, r8
0x140045776  mov     r14, rdx
0x140045779  xor     r13d, r13d
0x14004577c  mov     [rbp+57h+var_60], r13
0x140045780  mov     [rbp+57h+var_50], r13d
0x140045784  mov     [rbp+57h+var_78], r13
0x140045788  mov     [rbp+57h+var_4C], r13d
0x14004578c  mov     [rbp+57h+var_68], r13
0x140045790  mov     [rbp+57h+var_80], r13
0x140045794  mov     [rbp+57h+var_58], r13
0x140045798  mov     [rbp+57h+var_70], r13
0x14004579c  mov     [rbp+57h+var_90], r13d
0x1400457a0  mov     [rbp+57h+pv], r13
0x1400457a4  mov     [rbp+57h+var_48], r13
0x1400457a8  lea     r8, aCvdsdisklunFin_7; "CVdsDiskLun::FindEndOfLastVolume()"
0x1400457af  lea     edx, [r13+5Eh]
0x1400457b3  lea     rcx, [rbp+57h+var_40]
0x1400457b7  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400457bd  nop
0x1400457be  test    r14, r14
0x1400457c1  jz      loc_140045B6C
0x1400457c7  test    r15, r15
0x1400457ca  jz      loc_140045B6C
0x1400457d0  test    r12, r12
0x1400457d3  jz      loc_140045B6C
0x1400457d9  mov     [r12], r13
0x1400457dd  mov     rax, [r14]
0x1400457e0  lea     r8, [rbp+57h+var_90]
0x1400457e4  lea     rdx, [rbp+57h+pv]
0x1400457e8  mov     rcx, r14
0x1400457eb  mov     rax, [rax+30h]
0x1400457ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400457f4  mov     ebx, eax
0x1400457f6  test    eax, eax
0x1400457f8  jns     short loc_140045814
0x1400457fa  lea     r8, aCvdsdisklunFin; "CVdsDiskLun::FindEndOfLastVolume, 2, hr"...
0x140045801  mov     r9d, eax
0x140045804  xor     edx, edx
0x140045806  lea     ecx, [rdx+5Eh]
0x140045809  call    cs:__imp_VdsTraceEx
0x14004580f  jmp     loc_140045B94
0x140045814  mov     rsi, r13
0x140045817  mov     r8d, r13d
0x14004581a  mov     r9d, [rbp+57h+var_90]
0x14004581e  test    dword ptr [r15+3Ch], 2000h
0x140045826  jz      loc_140045B26
0x14004582c  test    r9d, r9d
0x14004582f  jle     short loc_140045870
0x140045831  mov     r10, [rbp+57h+pv]
0x140045835  movsxd  rax, r8d
0x140045838  lea     rdx, [rax+rax*4]
0x14004583c  add     rdx, rdx
0x14004583f  mov     ecx, [r10+rdx*8+10h]
0x140045844  lea     eax, [rcx-1]
0x140045847  cmp     eax, 1
0x14004584a  jbe     short loc_140045868
0x14004584c  cmp     ecx, 7FFFh
0x140045852  jz      short loc_140045868
0x140045854  mov     rcx, [r10+rdx*8+20h]
0x140045859  mov     rdx, [r10+rdx*8+18h]
0x14004585e  add     rdx, rcx
0x140045861  cmp     rdx, rsi
0x140045864  cmova   rsi, rdx
0x140045868  inc     r8d
0x14004586b  cmp     r8d, r9d
0x14004586e  jl      short loc_140045835
0x140045870  mov     rax, [r14]
0x140045873  lea     rdx, [rbp+57h+var_48]
0x140045877  mov     rcx, r14
0x14004587a  mov     rax, [rax+20h]
0x14004587e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045883  mov     ebx, eax
0x140045885  test    eax, eax
0x140045887  jns     short loc_140045895
0x140045889  lea     r8, aCvdsdisklunFin_5; "CVdsDiskLun::FindEndOfLastVolume, 3, hr"...
0x140045890  jmp     loc_140045801
0x140045895  mov     rcx, [rbp+57h+var_48]
0x140045899  mov     rax, [rcx]
0x14004589c  lea     rdx, [rbp+57h+var_58]
0x1400458a0  mov     rax, [rax+28h]
0x1400458a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400458a9  mov     ebx, eax
0x1400458ab  test    eax, eax
0x1400458ad  jns     short loc_1400458BB
0x1400458af  lea     r8, aCvdsdisklunFin_18; "CVdsDiskLun::FindEndOfLastVolume, 3.5, "...
0x1400458b6  jmp     loc_140045801
0x1400458bb  test    ebx, ebx
0x1400458bd  js      loc_140045B0B
0x1400458c3  cmp     ebx, 1
0x1400458c6  jz      loc_140045B0B
0x1400458cc  mov     rcx, [rbp+57h+var_58]
0x1400458d0  mov     rax, [rcx]
0x1400458d3  lea     r9, [rbp+57h+var_50]
0x1400458d7  lea     r8, [rbp+57h+var_60]
0x1400458db  mov     edx, 1
0x1400458e0  mov     rax, [rax+18h]
0x1400458e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400458e9  mov     ebx, eax
0x1400458eb  cmp     eax, 1
0x1400458ee  jz      loc_140045B0B
0x1400458f4  test    eax, eax
0x1400458f6  js      loc_140045AFF
0x1400458fc  mov     rcx, [rbp+57h+var_60]
0x140045900  mov     rax, [rcx]
0x140045903  lea     r8, [rbp+57h+var_68]
0x140045907  lea     rdx, IID_IVdsVolume
0x14004590e  mov     rax, [rax]
0x140045911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045916  mov     ebx, eax
0x140045918  test    eax, eax
0x14004591a  js      loc_140045AF3
0x140045920  mov     rcx, [rbp+57h+var_68]
0x140045924  mov     rax, [rcx]
0x140045927  lea     rdx, [rbp+57h+var_70]
0x14004592b  mov     rax, [rax+28h]
0x14004592f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045934  mov     ebx, eax
0x140045936  test    eax, eax
0x140045938  js      loc_140045AE7
0x14004593e  cmp     ebx, 1
0x140045941  jz      loc_140045A6F
0x140045947  mov     rcx, [rbp+57h+var_70]
0x14004594b  mov     rax, [rcx]
0x14004594e  lea     r9, [rbp+57h+var_4C]
0x140045952  lea     r8, [rbp+57h+var_78]
0x140045956  mov     edx, 1
0x14004595b  mov     rax, [rax+18h]
0x14004595f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045964  mov     ebx, eax
0x140045966  cmp     eax, 1
0x140045969  jz      loc_140045A6F
0x14004596f  test    eax, eax
0x140045971  js      loc_140045ADB
0x140045977  mov     rcx, [rbp+57h+var_78]
0x14004597b  mov     rax, [rcx]
0x14004597e  lea     r8, [rbp+57h+var_80]
0x140045982  lea     rdx, IID_IVdsVolumePlex
0x140045989  mov     rax, [rax]
0x14004598c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045991  mov     ebx, eax
0x140045993  test    eax, eax
0x140045995  js      loc_140045ACF
0x14004599b  mov     rcx, [rbp+57h+pv]; pv
0x14004599f  test    rcx, rcx
0x1400459a2  jz      short loc_1400459AE
0x1400459a4  call    cs:__imp_CoTaskMemFree
0x1400459aa  mov     [rbp+57h+pv], r13
0x1400459ae  mov     [rbp+57h+var_90], r13d
0x1400459b2  mov     rcx, [rbp+57h+var_80]
0x1400459b6  mov     rax, [rcx]
0x1400459b9  lea     r8, [rbp+57h+var_90]
0x1400459bd  lea     rdx, [rbp+57h+pv]
0x1400459c1  mov     rax, [rax+28h]
0x1400459c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400459ca  mov     ebx, eax
0x1400459cc  test    eax, eax
0x1400459ce  js      loc_140045AC3
0x1400459d4  mov     r8d, r13d
0x1400459d7  mov     r9d, [rbp+57h+var_90]
0x1400459db  test    r9d, r9d
0x1400459de  jle     short loc_140045A21
0x1400459e0  movsxd  rax, r8d
0x1400459e3  lea     rdx, [rax+rax*4]
0x1400459e7  add     rdx, rdx
0x1400459ea  mov     r10, [rbp+57h+pv]
0x1400459ee  mov     rax, [r10+rdx*8]
0x1400459f2  sub     rax, [r15]
0x1400459f5  jnz     short loc_140045A00
0x1400459f7  mov     rax, [r10+rdx*8+8]
0x1400459fc  sub     rax, [r15+8]
0x140045a00  test    rax, rax
0x140045a03  jnz     short loc_140045A19
0x140045a05  mov     rcx, [r10+rdx*8+20h]
0x140045a0a  mov     rdx, [r10+rdx*8+18h]
0x140045a0f  add     rdx, rcx
0x140045a12  cmp     rdx, rsi
0x140045a15  cmova   rsi, rdx
0x140045a19  inc     r8d
0x140045a1c  cmp     r8d, r9d
0x140045a1f  jl      short loc_1400459E0
0x140045a21  mov     rcx, [rbp+57h+pv]; pv
0x140045a25  test    rcx, rcx
0x140045a28  jz      short loc_140045A34
0x140045a2a  call    cs:__imp_CoTaskMemFree
0x140045a30  mov     [rbp+57h+pv], r13
0x140045a34  mov     rcx, [rbp+57h+var_80]
0x140045a38  test    rcx, rcx
0x140045a3b  jz      short loc_140045A4D
0x140045a3d  mov     rax, [rcx]
0x140045a40  mov     rax, [rax+10h]
0x140045a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045a49  mov     [rbp+57h+var_80], r13
0x140045a4d  mov     rcx, [rbp+57h+var_78]
0x140045a51  test    rcx, rcx
0x140045a54  jz      loc_14004593E
0x140045a5a  mov     rax, [rcx]
0x140045a5d  mov     rax, [rax+10h]
0x140045a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045a66  mov     [rbp+57h+var_78], r13
0x140045a6a  jmp     loc_14004593E
0x140045a6f  mov     rcx, [rbp+57h+var_70]
0x140045a73  test    rcx, rcx
0x140045a76  jz      short loc_140045A88
0x140045a78  mov     rax, [rcx]
0x140045a7b  mov     rax, [rax+10h]
0x140045a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045a84  mov     [rbp+57h+var_70], r13
0x140045a88  mov     rcx, [rbp+57h+var_68]
0x140045a8c  test    rcx, rcx
0x140045a8f  jz      short loc_140045AA1
0x140045a91  mov     rax, [rcx]
0x140045a94  mov     rax, [rax+10h]
0x140045a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045a9d  mov     [rbp+57h+var_68], r13
0x140045aa1  mov     rcx, [rbp+57h+var_60]
0x140045aa5  test    rcx, rcx
0x140045aa8  jz      loc_1400458BB
0x140045aae  mov     rax, [rcx]
0x140045ab1  mov     rax, [rax+10h]
0x140045ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045aba  mov     [rbp+57h+var_60], r13
0x140045abe  jmp     loc_1400458BB
0x140045ac3  lea     r8, aCvdsdisklunFin_14; "CVdsDiskLun::FindEndOfLastVolume, 9, hr"...
0x140045aca  jmp     loc_140045801
0x140045acf  lea     r8, aCvdsdisklunFin_15; "CVdsDiskLun::FindEndOfLastVolume, 8, hr"...
0x140045ad6  jmp     loc_140045801
0x140045adb  lea     r8, aCvdsdisklunFin_22; "CVdsDiskLun::FindEndOfLastVolume, 7, hr"...
0x140045ae2  jmp     loc_140045801
0x140045ae7  lea     r8, aCvdsdisklunFin_12; "CVdsDiskLun::FindEndOfLastVolume, 6, hr"...
0x140045aee  jmp     loc_140045801
0x140045af3  lea     r8, aCvdsdisklunFin_4; "CVdsDiskLun::FindEndOfLastVolume, 5, hr"...
0x140045afa  jmp     loc_140045801
0x140045aff  lea     r8, aCvdsdisklunFin_6; "CVdsDiskLun::FindEndOfLastVolume, 4, hr"...
0x140045b06  jmp     loc_140045801
0x140045b0b  mov     rcx, [rbp+57h+var_58]
0x140045b0f  test    rcx, rcx
0x140045b12  jz      short loc_140045B66
0x140045b14  mov     rax, [rcx]
0x140045b17  mov     rax, [rax+10h]
0x140045b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045b20  mov     [rbp+57h+var_58], r13
0x140045b24  jmp     short loc_140045B66
0x140045b26  test    r9d, r9d
0x140045b29  jle     short loc_140045B66
0x140045b2b  movsxd  rax, r8d
0x140045b2e  lea     rax, [rax+rax*4]
0x140045b32  add     rax, rax
0x140045b35  mov     rdx, [rbp+57h+pv]
0x140045b39  cmp     dword ptr [rdx+rax*8+10h], 7FFFh
0x140045b41  jz      short loc_140045B5E
0x140045b43  cmp     dword ptr [rdx+rax*8+10h], 1
0x140045b48  jz      short loc_140045B5E
0x140045b4a  mov     rcx, [rdx+rax*8+20h]
0x140045b4f  mov     rdx, [rdx+rax*8+18h]
0x140045b54  add     rdx, rcx
0x140045b57  cmp     rdx, rsi
0x140045b5a  cmova   rsi, rdx
0x140045b5e  inc     r8d
0x140045b61  cmp     r8d, r9d
0x140045b64  jl      short loc_140045B2B
0x140045b66  mov     [r12], rsi
0x140045b6a  jmp     short loc_140045B94
0x140045b6c  mov     ebx, 80070057h
0x140045b71  mov     [rsp+0D0h+var_A0], ebx
0x140045b75  mov     [rsp+0D0h+var_A8], r12
0x140045b7a  mov     [rsp+0D0h+var_B0], r15
0x140045b7f  mov     r9, r14
0x140045b82  lea     r8, aCvdsdisklunFin_3; "CVdsDiskLun::FindEndOfLastVolume, 1, di"...
0x140045b89  xor     edx, edx
0x140045b8b  lea     ecx, [rdx+5Eh]
0x140045b8e  call    cs:__imp_VdsTraceEx
0x140045b94  mov     rcx, [rbp+57h+pv]; pv
0x140045b98  test    rcx, rcx
0x140045b9b  jz      short loc_140045BA7
0x140045b9d  call    cs:__imp_CoTaskMemFree
0x140045ba3  mov     [rbp+57h+pv], r13
0x140045ba7  mov     rcx, [rbp+57h+var_80]
0x140045bab  test    rcx, rcx
0x140045bae  jz      short loc_140045BC0
0x140045bb0  mov     rax, [rcx]
0x140045bb3  mov     rax, [rax+10h]
0x140045bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045bbc  mov     [rbp+57h+var_80], r13
0x140045bc0  mov     rcx, [rbp+57h+var_78]
0x140045bc4  test    rcx, rcx
0x140045bc7  jz      short loc_140045BD9
0x140045bc9  mov     rax, [rcx]
0x140045bcc  mov     rax, [rax+10h]
0x140045bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045bd5  mov     [rbp+57h+var_78], r13
  ... truncated ...
```
