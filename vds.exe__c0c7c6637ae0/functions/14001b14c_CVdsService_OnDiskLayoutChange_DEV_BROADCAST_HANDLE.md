# CVdsService::OnDiskLayoutChange(_DEV_BROADCAST_HANDLE *)

- ea: `0x14001b14c`
- end: `0x14001b6ea`
- name: `?OnDiskLayoutChange@CVdsService@@SAXPEAU_DEV_BROADCAST_HANDLE@@@Z`
- size: `1438`
- prototype: `void __fastcall(struct _DEV_BROADCAST_HANDLE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400066a0`

## callees

- `0x140012c48`
- `0x140013298`
- `0x14001b14c`
- `0x14002de26`
- `0x14002e123`
- `0x14003c424`
- `0x14003c514`
- `0x14003ca88`
- `0x14004e6a0`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001b6b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001b6b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001b214`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001b214`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b322`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b335`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b35b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b36e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b322`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b335`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b35b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b36e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b3ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b663`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b67c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b3ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b663`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b67c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b69f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b69f`
- `vdsutil!OpenDevice` at `0x14001b3fe`
- `vdsutil!OpenDevice` at `0x14001b3fe`
- `vdsutil!GetDiskLayout` at `0x14001b42c`
- `vdsutil!GetDiskLayout` at `0x14001b42c`
- `vdsutil!VdsHeapAlloc` at `0x14001b3bd`
- `vdsutil!VdsHeapAlloc` at `0x14001b3bd`
- `vdsutil!VdsHeapFree` at `0x14001b671`
- `vdsutil!VdsHeapFree` at `0x14001b68a`
- `vdsutil!VdsHeapFree` at `0x14001b671`
- `vdsutil!VdsHeapFree` at `0x14001b68a`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001b4cd`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001b4cd`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001b4e7`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001b4e7`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14001b51d`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14001b51d`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14001b5e3`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14001b5e3`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001b1ba`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001b4ac`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001b1ba`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001b4ac`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001b640`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001b6c0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001b640`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001b6c0`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14001b2b3`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14001b2b3`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14001b226`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14001b226`
- `vdsutil!VdsTraceW` at `0x14001b1dd`
- `vdsutil!VdsTraceW` at `0x14001b26a`
- `vdsutil!VdsTraceW` at `0x14001b2d8`
- `vdsutil!VdsTraceW` at `0x14001b313`
- `vdsutil!VdsTraceW` at `0x14001b38b`
- `vdsutil!VdsTraceW` at `0x14001b3d4`
- `vdsutil!VdsTraceW` at `0x14001b417`
- `vdsutil!VdsTraceW` at `0x14001b532`
- `vdsutil!VdsTraceW` at `0x14001b586`
- `vdsutil!VdsTraceW` at `0x14001b5cd`
- `vdsutil!VdsTraceW` at `0x14001b635`
- `vdsutil!VdsTraceW` at `0x14001b1dd`
- `vdsutil!VdsTraceW` at `0x14001b26a`
- `vdsutil!VdsTraceW` at `0x14001b2d8`
- `vdsutil!VdsTraceW` at `0x14001b313`
- `vdsutil!VdsTraceW` at `0x14001b38b`
- `vdsutil!VdsTraceW` at `0x14001b3d4`
- `vdsutil!VdsTraceW` at `0x14001b417`
- `vdsutil!VdsTraceW` at `0x14001b532`
- `vdsutil!VdsTraceW` at `0x14001b586`
- `vdsutil!VdsTraceW` at `0x14001b5cd`
- `vdsutil!VdsTraceW` at `0x14001b635`

## string_xrefs

- `0x14001b1ac`: `CVdsService::OnDiskLayoutChange()`
- `0x14001b1d4`: `CVdsService::OnDiskLayoutChange, 1`
- `0x14001b261`: `CVdsService::OnDiskLayoutChange, 2`
- `0x14001b2cf`: `CVdsService::OnDiskLayoutChange, 2.9, %lX`
- `0x14001b30a`: `CVdsService::OnDiskLayoutChange, 3, %lX, path=%s`
- `0x14001b384`: `CVdsService::OnDiskLayoutChange, 4`
- `0x14001b3cb`: `CVdsService::OnDiskLayoutChange, 5`
- `0x14001b408`: `CVdsService::OnDiskLayoutChange, 6, path=%s, %ld`
- `0x14001b436`: `CVdsService::OnDiskLayoutChange, 7, path=%s, %ld`
- `0x14001b49c`: `CVdsService::HandleDiskLayoutChange()`
- `0x14001b62c`: `CVdsService::HandleDiskLayoutChange, 1, Path=%p, Layout=%p, pbDisable=%p, name=%s`
- `0x14001b52b`: `CVdsService::HandleDiskLayoutChange, 1a`
- `0x14001b57d`: `CVdsService::HandleDiskLayoutChange, 1b, hr=%lX`
- `0x14001b5c4`: `CVdsService::HandleDiskLayoutChange, 2, name=%s, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CVdsService::OnDiskLayoutChange(struct _DEV_BROADCAST_HANDLE *a1)
{
  void *v2; // rdi
  __int64 v3; // rax
  __int64 v4; // rbx
  int updated; // eax
  int v6; // eax
  __int64 v7; // r8
  const wchar_t *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rax
  size_t v11; // rsi
  HANDLE ProcessHeap; // rax
  void *v13; // rax
  unsigned int v14; // eax
  unsigned int DiskLayout; // eax
  GUID v16; // xmm6
  _DWORD *v17; // r14
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rax
  signed int v19; // eax
  unsigned int v20; // esi
  int v21; // eax
  _DWORD *v22; // rbx
  HANDLE v23; // rax
  HANDLE v24; // rax
  char v25[8]; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD *v26; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  GUID Buf2; // [rsp+50h] [rbp-B0h] BYREF
  struct CRtlEntry *v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h]
  __int128 Buf1; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v33[16]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v34[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v35[24]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v36[88]; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+118h] [rbp+18h]
  LPVOID v38; // [rsp+120h] [rbp+20h]
  LPVOID v39; // [rsp+128h] [rbp+28h]
  LPVOID v40; // [rsp+130h] [rbp+30h]
  LPVOID v41; // [rsp+138h] [rbp+38h]

  memset_0(v36, 0, 0x80u);
  *(_OWORD *)v30 = 0;
  v31 = 0;
  v26 = 0;
  hObject = 0;
  v25[0] = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v34, 0x5Eu, "CVdsService::OnDiskLayoutChange()");
  memset_0(v36, 0, 0x80u);
  if ( !a1 )
  {
    VdsTraceW(0, L"CVdsService::OnDiskLayoutChange, 1");
    VdsLogError(0xC2000009, 0, 0, 0x80042448, 0x2000019u, 0);
    goto LABEL_62;
  }
  v2 = 0;
  EnterCriticalSection(&g_GlobalCriticalSection);
LABEL_4:
  v3 = CRtlMap::Begin(CVdsService::m_mapUnallocatedDisks, v35);
  *(_OWORD *)v30 = *(_OWORD *)v3;
  v31 = *(_QWORD *)(v3 + 16);
  while ( 1 )
  {
    if ( !v30[0] || !v30[1] )
      goto LABEL_59;
    v4 = *((_QWORD *)v30[1] + 6);
    if ( !v4 )
    {
      VdsTraceW(0, L"CVdsService::OnDiskLayoutChange, 2");
      VdsLogError(0xC2000009, 0, 0, 0x80042448, 0x200001Au, 0);
      CVdsService::RemoveUnallocatedDiskFromMap(v30[1]);
      goto LABEL_4;
    }
    if ( *(HDEVNOTIFY *)(v4 + 328) == a1->dbch_hdevnotify )
      break;
    CRtlMapIter::Next((CRtlMapIter *)v30);
  }
  updated = CVdsRawDiskLun::UpdateSize((CVdsRawDiskLun *)v4);
  if ( updated < 0 )
    VdsTraceW(2, L"CVdsService::OnDiskLayoutChange, 2.9, %lX", (unsigned int)updated);
  v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v4 + 24LL))(v4, v36);
  v7 = (unsigned int)v6;
  if ( v6 < 0 )
  {
    v8 = L"UNKNOWN";
    if ( v38 )
      v8 = (const wchar_t *)v38;
    VdsTraceW(2, L"CVdsService::OnDiskLayoutChange, 3, %lX, path=%s", (unsigned int)v6, v8);
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v39 )
  {
    CoTaskMemFree(v39);
    v39 = 0;
  }
  if ( v40 )
  {
    CoTaskMemFree(v40);
    v40 = 0;
  }
  if ( v41 )
  {
    CoTaskMemFree(v41);
    v41 = 0;
  }
  if ( v38 )
  {
    CoTaskMemFree(v38);
    v38 = 0;
  }
  v9 = *(_QWORD *)(v4 + 240);
  if ( !v9 )
  {
    VdsTraceW(0, L"CVdsService::OnDiskLayoutChange, 4", v7);
LABEL_58:
    *(_DWORD *)(v4 + 136) = 0;
    *(_DWORD *)(v4 + 340) = 1;
    goto LABEL_59;
  }
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(v9 + 2 * v10) );
  v11 = 2 * v10 + 2;
  ProcessHeap = GetProcessHeap();
  v13 = (void *)VdsHeapAlloc(ProcessHeap, 8, v11);
  v2 = v13;
  if ( !v13 )
  {
    VdsTraceW(0, L"CVdsService::OnDiskLayoutChange, 5");
    goto LABEL_59;
  }
  memcpy_0(v13, *(const void **)(v4 + 240), v11);
  v14 = OpenDevice(v2, 0x80000000LL, &hObject);
  if ( v14 )
  {
    VdsTraceW(0, L"CVdsService::OnDiskLayoutChange, 6, path=%s, %ld", v2, v14);
    goto LABEL_58;
  }
  DiskLayout = GetDiskLayout(hObject, &v26);
  if ( DiskLayout )
  {
    VdsTraceW(0, L"CVdsService::OnDiskLayoutChange, 7, path=%s, %ld", v2, DiskLayout);
    goto LABEL_58;
  }
  v16 = *(GUID *)(v4 + 120);
  Buf2 = v16;
  if ( *v26 == 1 || !*v26 && v26[2] )
  {
    v17 = v26;
    Buf1 = 0;
    CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v33, 0x5Eu, "CVdsService::HandleDiskLayoutChange()");
    if ( v17 )
    {
      v25[0] = 0;
      for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstSoftwareProviders, &Buf2);
            ;
            CRtlListIter::Next((CRtlListIter *)&Buf1) )
      {
        Buf2 = *(GUID *)CRtlList::End(CVdsService::m_lstSoftwareProviders, v35);
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
          break;
        v27 = 0;
        EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
        if ( EntryPointer )
        {
          v19 = (**EntryPointer)(EntryPointer, &IID_IVdsOwnershipChangeQuery, &v27);
          v20 = v19;
          if ( v19 >= 0 )
          {
            Buf2 = GUID_NULL;
            v21 = (*(__int64 (__fastcall **)(__int64, GUID *, void *, _DWORD *))(*(_QWORD *)v27 + 24LL))(
                    v27,
                    &Buf2,
                    v2,
                    v17);
            if ( !v21 )
            {
              Buf2 = v16;
              CVdsService::RemoveRawDisk(&Buf2, 9u);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
              goto LABEL_57;
            }
            if ( v21 < 0 )
              VdsTraceW(0, L"CVdsService::HandleDiskLayoutChange, 2, name=%s, hr=%lX", v2, (unsigned int)v21);
          }
          else
          {
            VdsLogError(0xC2000009, 0, 0, v19, 0x200001Bu, 0);
            VdsTraceW(0, L"CVdsService::HandleDiskLayoutChange, 1b, hr=%lX", v20);
          }
        }
        else
        {
          VdsTraceW(0, L"CVdsService::HandleDiskLayoutChange, 1a");
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
      }
      v25[0] = 1;
    }
    else
    {
      VdsTraceW(0, L"CVdsService::HandleDiskLayoutChange, 1, Path=%p, Layout=%p, pbDisable=%p, name=%s", v2, 0, v25, v2);
    }
LABEL_57:
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v33);
    if ( v25[0] )
      goto LABEL_58;
  }
  else if ( *(_DWORD *)(v4 + 340) )
  {
    *(_DWORD *)(v4 + 340) = 0;
    *(_DWORD *)(v4 + 136) = 1;
    CVdsService::SendDiskNotification(0xAu, &Buf2);
  }
LABEL_59:
  v22 = v26;
  v23 = GetProcessHeap();
  VdsHeapFree(v23, 0, v22);
  v26 = 0;
  v24 = GetProcessHeap();
  VdsHeapFree(v24, 0, v2);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
  LeaveCriticalSection(&g_GlobalCriticalSection);
LABEL_62:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
}

```

## disassembly

```asm
0x14001b14c  mov     rax, rsp
0x14001b14f  push    rbp
0x14001b150  push    rbx
0x14001b151  push    rsi
0x14001b152  push    rdi
0x14001b153  push    r14
0x14001b155  push    r15
0x14001b157  lea     rbp, [rsp-68h]
0x14001b15c  sub     rsp, 168h
0x14001b163  movaps  xmmword ptr [rax-48h], xmm6
0x14001b167  mov     rax, cs:__security_cookie
0x14001b16e  xor     rax, rsp
0x14001b171  mov     [rbp+90h+var_48], rax
0x14001b175  mov     rsi, rcx
0x14001b178  mov     ebx, 80h
0x14001b17d  mov     r8d, ebx; Size
0x14001b180  xor     edx, edx; Val
0x14001b182  lea     rcx, [rbp+90h+var_D0]; void *
0x14001b186  call    memset_0
0x14001b18b  xorps   xmm0, xmm0
0x14001b18e  xor     eax, eax
0x14001b190  movups  xmmword ptr [rsp+190h+var_130], xmm0
0x14001b195  mov     [rsp+190h+var_120], rax
0x14001b19a  xor     r15d, r15d
0x14001b19d  mov     [rsp+190h+var_158], r15
0x14001b1a2  mov     [rsp+190h+hObject], r15
0x14001b1a7  mov     [rsp+190h+var_160], r15b
0x14001b1ac  lea     r8, aCvdsserviceOnd_1; "CVdsService::OnDiskLayoutChange()"
0x14001b1b3  lea     edx, [rbx-22h]
0x14001b1b6  lea     rcx, [rbp+90h+var_F8]
0x14001b1ba  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001b1c0  nop
0x14001b1c1  mov     r8d, ebx; Size
0x14001b1c4  xor     edx, edx; Val
0x14001b1c6  lea     rcx, [rbp+90h+var_D0]; void *
0x14001b1ca  call    memset_0
0x14001b1cf  test    rsi, rsi
0x14001b1d2  jnz     short loc_14001B20A
0x14001b1d4  lea     rdx, aCvdsserviceOnd_4; "CVdsService::OnDiskLayoutChange, 1"
0x14001b1db  xor     ecx, ecx
0x14001b1dd  call    cs:__imp_VdsTraceW
0x14001b1e3  mov     [rsp+190h+var_168], r15; unsigned __int16 *
0x14001b1e8  mov     [rsp+190h+var_170], 2000019h; unsigned int
0x14001b1f0  mov     r9d, 80042448h; unsigned int
0x14001b1f6  xor     r8d, r8d; void *
0x14001b1f9  xor     edx, edx; unsigned int
0x14001b1fb  mov     ecx, 0C2000009h; unsigned int
0x14001b200  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14001b205  jmp     loc_14001B6BC
0x14001b20a  mov     rdi, r15
0x14001b20d  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001b214  call    cs:__imp_EnterCriticalSection
0x14001b21a  nop
0x14001b21b  lea     rdx, [rbp+90h+var_E8]
0x14001b21f  lea     rcx, ?m_mapUnallocatedDisks@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisks
0x14001b226  call    cs:__imp_?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ; CRtlMap::Begin(void)
0x14001b22c  movups  xmm0, xmmword ptr [rax]
0x14001b22f  movups  xmmword ptr [rsp+190h+var_130], xmm0
0x14001b234  movsd   xmm1, qword ptr [rax+10h]
0x14001b239  movsd   [rsp+190h+var_120], xmm1
0x14001b23f  cmp     [rsp+190h+var_130], r15
0x14001b244  jz      loc_14001B65E
0x14001b24a  mov     rbx, [rsp+190h+var_130+8]
0x14001b24f  test    rbx, rbx
0x14001b252  jz      loc_14001B65E
0x14001b258  mov     rbx, [rbx+30h]
0x14001b25c  test    rbx, rbx
0x14001b25f  jnz     short loc_14001B2A1
0x14001b261  lea     rdx, aCvdsserviceOnd; "CVdsService::OnDiskLayoutChange, 2"
0x14001b268  xor     ecx, ecx
0x14001b26a  call    cs:__imp_VdsTraceW
0x14001b270  mov     [rsp+190h+var_168], r15; unsigned __int16 *
0x14001b275  mov     [rsp+190h+var_170], 200001Ah; unsigned int
0x14001b27d  mov     r9d, 80042448h; unsigned int
0x14001b283  xor     r8d, r8d; void *
0x14001b286  xor     edx, edx; unsigned int
0x14001b288  mov     ecx, 0C2000009h; unsigned int
0x14001b28d  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14001b292  mov     rcx, [rsp+190h+var_130+8]; struct CRtlEntry *
0x14001b297  call    ?RemoveUnallocatedDiskFromMap@CVdsService@@CAXAEAVCRtlEntry@@@Z; CVdsService::RemoveUnallocatedDiskFromMap(CRtlEntry &)
0x14001b29c  jmp     loc_14001B21B
0x14001b2a1  mov     rax, [rsi+18h]
0x14001b2a5  cmp     [rbx+148h], rax
0x14001b2ac  jz      short loc_14001B2BB
0x14001b2ae  lea     rcx, [rsp+190h+var_130]
0x14001b2b3  call    cs:__imp_?Next@CRtlMapIter@@QEAAAEAV1@XZ; CRtlMapIter::Next(void)
0x14001b2b9  jmp     short loc_14001B23F
0x14001b2bb  mov     rcx, rbx; this
0x14001b2be  call    ?UpdateSize@CVdsRawDiskLun@@QEAAJXZ; CVdsRawDiskLun::UpdateSize(void)
0x14001b2c3  mov     esi, 2
0x14001b2c8  test    eax, eax
0x14001b2ca  jns     short loc_14001B2DE
0x14001b2cc  mov     r8d, eax
0x14001b2cf  lea     rdx, aCvdsserviceOnd_10; "CVdsService::OnDiskLayoutChange, 2.9, %"...
0x14001b2d6  mov     ecx, esi
0x14001b2d8  call    cs:__imp_VdsTraceW
0x14001b2de  mov     rax, [rbx]
0x14001b2e1  lea     rdx, [rbp+90h+var_D0]
0x14001b2e5  mov     rcx, rbx
0x14001b2e8  mov     rax, [rax+18h]
0x14001b2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b2f1  mov     r8d, eax
0x14001b2f4  test    eax, eax
0x14001b2f6  jns     short loc_14001B319
0x14001b2f8  lea     r9, aUnknown_0; "UNKNOWN"
0x14001b2ff  mov     rax, [rbp+90h+var_70]
0x14001b303  test    rax, rax
0x14001b306  cmovnz  r9, rax
0x14001b30a  lea     rdx, aCvdsserviceOnd_8; "CVdsService::OnDiskLayoutChange, 3, %lX"...
0x14001b311  mov     ecx, esi
0x14001b313  call    cs:__imp_VdsTraceW
0x14001b319  mov     rcx, [rbp+90h+pv]; pv
0x14001b31d  test    rcx, rcx
0x14001b320  jz      short loc_14001B32C
0x14001b322  call    cs:__imp_CoTaskMemFree
0x14001b328  mov     [rbp+90h+pv], r15
0x14001b32c  mov     rcx, [rbp+90h+var_68]; pv
0x14001b330  test    rcx, rcx
0x14001b333  jz      short loc_14001B33F
0x14001b335  call    cs:__imp_CoTaskMemFree
0x14001b33b  mov     [rbp+90h+var_68], r15
0x14001b33f  mov     rcx, [rbp+90h+var_60]; pv
0x14001b343  test    rcx, rcx
0x14001b346  jz      short loc_14001B352
0x14001b348  call    cs:__imp_CoTaskMemFree
0x14001b34e  mov     [rbp+90h+var_60], r15
0x14001b352  mov     rcx, [rbp+90h+var_58]; pv
0x14001b356  test    rcx, rcx
0x14001b359  jz      short loc_14001B365
0x14001b35b  call    cs:__imp_CoTaskMemFree
0x14001b361  mov     [rbp+90h+var_58], r15
0x14001b365  mov     rcx, [rbp+90h+var_70]; pv
0x14001b369  test    rcx, rcx
0x14001b36c  jz      short loc_14001B378
0x14001b36e  call    cs:__imp_CoTaskMemFree
0x14001b374  mov     [rbp+90h+var_70], r15
0x14001b378  mov     rcx, [rbx+0F0h]
0x14001b37f  test    rcx, rcx
0x14001b382  jnz     short loc_14001B396
0x14001b384  lea     rdx, aCvdsserviceOnd_3; "CVdsService::OnDiskLayoutChange, 4"
0x14001b38b  call    cs:__imp_VdsTraceW
0x14001b391  jmp     loc_14001B64D
0x14001b396  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001b39a  inc     rax
0x14001b39d  cmp     [rcx+rax*2], r15w
0x14001b3a2  jnz     short loc_14001B39A
0x14001b3a4  lea     rsi, ds:2[rax*2]
0x14001b3ac  call    cs:__imp_GetProcessHeap
0x14001b3b2  mov     rcx, rax
0x14001b3b5  mov     r8, rsi
0x14001b3b8  mov     edx, 8
0x14001b3bd  call    cs:__imp_VdsHeapAlloc
0x14001b3c3  mov     rdi, rax
0x14001b3c6  test    rax, rax
0x14001b3c9  jnz     short loc_14001B3DF
0x14001b3cb  lea     rdx, aCvdsserviceOnd_2; "CVdsService::OnDiskLayoutChange, 5"
0x14001b3d2  xor     ecx, ecx
0x14001b3d4  call    cs:__imp_VdsTraceW
0x14001b3da  jmp     loc_14001B65E
0x14001b3df  mov     r8, rsi; Size
0x14001b3e2  mov     rdx, [rbx+0F0h]; Src
0x14001b3e9  mov     rcx, rdi; void *
0x14001b3ec  call    memcpy_0
0x14001b3f1  lea     r8, [rsp+190h+hObject]
0x14001b3f6  mov     edx, 80000000h
0x14001b3fb  mov     rcx, rdi
0x14001b3fe  call    cs:__imp_OpenDevice
0x14001b404  test    eax, eax
0x14001b406  jz      short loc_14001B422
0x14001b408  lea     rdx, aCvdsserviceOnd_7; "CVdsService::OnDiskLayoutChange, 6, pat"...
0x14001b40f  mov     r8, rdi
0x14001b412  mov     r9d, eax
0x14001b415  xor     ecx, ecx
0x14001b417  call    cs:__imp_VdsTraceW
0x14001b41d  jmp     loc_14001B64D
0x14001b422  lea     rdx, [rsp+190h+var_158]
0x14001b427  mov     rcx, [rsp+190h+hObject]
0x14001b42c  call    cs:__imp_GetDiskLayout
0x14001b432  test    eax, eax
0x14001b434  jz      short loc_14001B43F
0x14001b436  lea     rdx, aCvdsserviceOnd_13; "CVdsService::OnDiskLayoutChange, 7, pat"...
0x14001b43d  jmp     short loc_14001B40F
0x14001b43f  movups  xmm6, xmmword ptr [rbx+78h]
0x14001b443  movaps  [rsp+190h+Buf2], xmm6
0x14001b448  mov     rax, [rsp+190h+var_158]
0x14001b44d  cmp     dword ptr [rax], 1
0x14001b450  jz      short loc_14001B48F
0x14001b452  cmp     [rax], r15d
0x14001b455  jnz     short loc_14001B45D
0x14001b457  cmp     [rax+8], r15d
0x14001b45b  jnz     short loc_14001B48F
0x14001b45d  cmp     [rbx+154h], r15d
0x14001b464  jz      loc_14001B65E
0x14001b46a  mov     [rbx+154h], r15d
0x14001b471  mov     dword ptr [rbx+88h], 1
0x14001b47b  lea     rdx, [rsp+190h+Buf2]; struct _GUID *
0x14001b480  mov     ecx, 0Ah; unsigned int
0x14001b485  call    ?SendDiskNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendDiskNotification(ulong,_GUID &)
0x14001b48a  jmp     loc_14001B65E
0x14001b48f  mov     r14, [rsp+190h+var_158]
0x14001b494  xorps   xmm0, xmm0
0x14001b497  movups  [rsp+190h+Buf1], xmm0
0x14001b49c  lea     r8, aCvdsserviceHan_3; "CVdsService::HandleDiskLayoutChange()"
0x14001b4a3  mov     edx, 5Eh ; '^'
0x14001b4a8  lea     rcx, [rbp+90h+var_108]
0x14001b4ac  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001b4b2  nop
0x14001b4b3  test    r14, r14
0x14001b4b6  jz      loc_14001B617
0x14001b4bc  mov     [rsp+190h+var_160], r15b
0x14001b4c1  lea     rdx, [rsp+190h+Buf2]
0x14001b4c6  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x14001b4cd  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14001b4d3  movups  xmm0, xmmword ptr [rax]
0x14001b4d6  movdqu  [rsp+190h+Buf1], xmm0
0x14001b4dc  lea     rdx, [rbp+90h+var_E8]
0x14001b4e0  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x14001b4e7  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14001b4ed  movups  xmm0, xmmword ptr [rax]
0x14001b4f0  movdqu  [rsp+190h+Buf2], xmm0
0x14001b4f6  mov     r8d, 10h; Size
0x14001b4fc  lea     rdx, [rsp+190h+Buf2]; Buf2
0x14001b501  lea     rcx, [rsp+190h+Buf1]; Buf1
0x14001b506  call    memcmp_0
0x14001b50b  test    eax, eax
0x14001b50d  jz      loc_14001B610
0x14001b513  mov     [rsp+190h+var_150], r15
0x14001b518  lea     rcx, [rsp+190h+Buf1]
0x14001b51d  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14001b523  mov     rcx, rax
0x14001b526  test    rax, rax
0x14001b529  jnz     short loc_14001B53E
0x14001b52b  lea     rdx, aCvdsserviceHan_0; "CVdsService::HandleDiskLayoutChange, 1a"
0x14001b532  call    cs:__imp_VdsTraceW
0x14001b538  nop
0x14001b539  jmp     loc_14001B5D4
0x14001b53e  mov     rax, [rax]
0x14001b541  lea     r8, [rsp+190h+var_150]
0x14001b546  lea     rdx, IID_IVdsOwnershipChangeQuery
0x14001b54d  mov     rax, [rax]
0x14001b550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b555  mov     esi, eax
0x14001b557  test    eax, eax
0x14001b559  jns     short loc_14001B58F
0x14001b55b  mov     [rsp+190h+var_168], r15; unsigned __int16 *
0x14001b560  mov     [rsp+190h+var_170], 200001Bh; unsigned int
0x14001b568  mov     r9d, eax; unsigned int
0x14001b56b  xor     r8d, r8d; void *
0x14001b56e  xor     edx, edx; unsigned int
0x14001b570  mov     ecx, 0C2000009h; unsigned int
0x14001b575  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14001b57a  mov     r8d, esi
0x14001b57d  lea     rdx, aCvdsserviceHan_1; "CVdsService::HandleDiskLayoutChange, 1b"...
0x14001b584  xor     ecx, ecx
0x14001b586  call    cs:__imp_VdsTraceW
0x14001b58c  nop
0x14001b58d  jmp     short loc_14001B5D4
0x14001b58f  mov     rcx, [rsp+190h+var_150]
0x14001b594  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14001b59b  movdqu  [rsp+190h+Buf2], xmm0
0x14001b5a1  mov     rax, [rcx]
0x14001b5a4  mov     r9, r14
0x14001b5a7  mov     r8, rdi
0x14001b5aa  lea     rdx, [rsp+190h+Buf2]
0x14001b5af  mov     rax, [rax+18h]
0x14001b5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b5b8  test    eax, eax
0x14001b5ba  jz      short loc_14001B5EE
0x14001b5bc  jns     short loc_14001B5D4
0x14001b5be  mov     r9d, eax
0x14001b5c1  mov     r8, rdi
0x14001b5c4  lea     rdx, aCvdsserviceHan; "CVdsService::HandleDiskLayoutChange, 2,"...
0x14001b5cb  xor     ecx, ecx
0x14001b5cd  call    cs:__imp_VdsTraceW
0x14001b5d3  nop
0x14001b5d4  lea     rcx, [rsp+190h+var_150]
0x14001b5d9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001b5de  lea     rcx, [rsp+190h+Buf1]
0x14001b5e3  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14001b5e9  jmp     loc_14001B4DC
0x14001b5ee  movdqa  [rsp+190h+Buf2], xmm6
0x14001b5f4  mov     edx, 9; unsigned int
0x14001b5f9  lea     rcx, [rsp+190h+Buf2]; struct _GUID
0x14001b5fe  call    ?RemoveRawDisk@CVdsService@@SAHU_GUID@@K@Z; CVdsService::RemoveRawDisk(_GUID,ulong)
0x14001b603  nop
0x14001b604  lea     rcx, [rsp+190h+var_150]
0x14001b609  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001b60e  jmp     short loc_14001B63C
0x14001b610  mov     [rsp+190h+var_160], 1
0x14001b615  jmp     short loc_14001B63C
0x14001b617  mov     [rsp+190h+var_168], rdi
0x14001b61c  lea     rax, [rsp+190h+var_160]
0x14001b621  mov     qword ptr [rsp+190h+var_170], rax
0x14001b626  mov     r9, r14
0x14001b629  mov     r8, rdi
0x14001b62c  lea     rdx, aCvdsserviceHan_2; "CVdsService::HandleDiskLayoutChange, 1,"...
0x14001b633  xor     ecx, ecx
0x14001b635  call    cs:__imp_VdsTraceW
0x14001b63b  nop
0x14001b63c  lea     rcx, [rbp+90h+var_108]
  ... truncated ...
```
