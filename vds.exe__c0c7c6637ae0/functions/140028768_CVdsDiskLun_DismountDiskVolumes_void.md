# CVdsDiskLun::DismountDiskVolumes(void)

- ea: `0x140028768`
- end: `0x140028b45`
- name: `?DismountDiskVolumes@CVdsDiskLun@@QEAAJXZ`
- size: `989`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140044cd0`
- `0x140049840`
- `0x14004a370`

## callees

- `0x1400069e8`
- `0x140028768`
- `0x140028fc8`
- `0x14002e123`
- `0x140039f84`
- `0x14003a2dc`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028a6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028a81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028aa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028aba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028a6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028a81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028aa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028aba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002889b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140028ae3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140028afc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002889b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140028ae3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140028afc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140028a0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140028ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140028a0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140028ad3`
- `vdsutil!OpenDevice` at `0x1400289a8`
- `vdsutil!OpenDevice` at `0x1400289a8`
- `vdsutil!LockDismountVolume` at `0x1400289f3`
- `vdsutil!LockDismountVolume` at `0x1400289f3`
- `vdsutil!VdsHeapFree` at `0x1400288a9`
- `vdsutil!VdsHeapFree` at `0x140028af1`
- `vdsutil!VdsHeapFree` at `0x140028b0b`
- `vdsutil!VdsHeapFree` at `0x1400288a9`
- `vdsutil!VdsHeapFree` at `0x140028af1`
- `vdsutil!VdsHeapFree` at `0x140028b0b`
- `vdsutil!VdsTraceEx` at `0x140028819`
- `vdsutil!VdsTraceEx` at `0x140028819`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400287d3`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400287d3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140028b19`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140028b19`
- `vdsutil!VdsTraceW` at `0x140028833`
- `vdsutil!VdsTraceW` at `0x14002886c`
- `vdsutil!VdsTraceW` at `0x140028983`
- `vdsutil!VdsTraceW` at `0x1400289de`
- `vdsutil!VdsTraceW` at `0x140028a43`
- `vdsutil!VdsTraceW` at `0x140028833`
- `vdsutil!VdsTraceW` at `0x14002886c`
- `vdsutil!VdsTraceW` at `0x140028983`
- `vdsutil!VdsTraceW` at `0x1400289de`
- `vdsutil!VdsTraceW` at `0x140028a43`

## string_xrefs

- `0x1400289d5`: `CVdsDiskLun::DismountDiskVolumes, 4, %lX, name=%s`
- `0x140028a3a`: `CVdsDiskLun::DismountDiskVolumes, 5, %lX, name=%s`
- `0x1400287c3`: `CVdsDiskLun::DismountDiskVolumes`
- `0x14002880e`: `CVdsDiskLun::DismountDiskVolumes, 1, hr=%lX`
- `0x140028863`: `CVdsDiskLun::DismountDiskVolumes, 2, hr=%lX`
- `0x140028975`: `CVdsDiskLun::DismountDiskVolumes, 3, ObjectId=%s, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsDiskLun::DismountDiskVolumes(CVdsDiskLun *this)
{
  int v2; // eax
  int VolumeNameById; // r14d
  int VolumeIdList; // eax
  struct _GUID *v5; // r15
  unsigned int i; // r12d
  unsigned __int16 *v7; // rbx
  HANDLE ProcessHeap; // rax
  int v9; // eax
  __int64 v10; // r8
  unsigned __int16 *v11; // r9
  signed int v12; // ebx
  unsigned int v13; // ecx
  unsigned __int16 *v14; // r9
  unsigned __int16 *v15; // rbx
  HANDLE v16; // rax
  HANDLE v17; // rax
  __int64 v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+28h] [rbp-D8h]
  __int64 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  __int64 v23; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v29; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID *v31[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v32; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v33; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v34[16]; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v35; // [rsp+C0h] [rbp-40h] BYREF
  int v36; // [rsp+D0h] [rbp-30h]
  LPVOID v37; // [rsp+118h] [rbp+18h]
  LPVOID pv; // [rsp+120h] [rbp+20h]
  LPVOID v39; // [rsp+128h] [rbp+28h]
  LPVOID v40; // [rsp+130h] [rbp+30h]
  LPVOID v41; // [rsp+138h] [rbp+38h]
  unsigned __int16 v42[64]; // [rsp+140h] [rbp+40h] BYREF

  v29 = 0;
  hObject = 0;
  v32 = 0;
  memset_0(&v35, 0, 0x80u);
  *(_OWORD *)v31 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v34, 0x5Eu, "CVdsDiskLun::DismountDiskVolumes");
  memset_0(&v35, 0, 0x80u);
  v2 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 28) + 24LL))(
         *((_QWORD *)this + 28),
         &v35);
  VolumeNameById = v2;
  if ( !*((_QWORD *)this + 28) )
  {
    VdsTraceEx(94, 0, "CVdsDiskLun::DismountDiskVolumes, 1, hr=%lX", v2);
    goto LABEL_28;
  }
  if ( v36 == 4 )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetIdentificationData, 1.5");
    goto LABEL_28;
  }
  *(_OWORD *)v31 = 0;
  VolumeIdList = CVdsService::GetVolumeIdList(&v35, 1u, (struct _VDS_UNINSTALL_INFORMATION *)v31);
  VolumeNameById = VolumeIdList;
  if ( VolumeIdList < 0 )
  {
    VdsTraceW(0, L"CVdsDiskLun::DismountDiskVolumes, 2, hr=%lX", (unsigned int)VolumeIdList);
    goto LABEL_28;
  }
  v5 = v31[1];
  for ( i = 0; i < LODWORD(v31[0]); ++v5 )
  {
    memset_0(v42, 0, sizeof(v42));
    v7 = v29;
    ProcessHeap = GetProcessHeap();
    VdsHeapFree(ProcessHeap, 0, v7);
    v29 = 0;
    v33 = *v5;
    VolumeNameById = CVdsService::GetVolumeNameById(&v33, &v29, &v32);
    if ( VolumeNameById != -2147211503 )
    {
      if ( VolumeNameById < 0 )
      {
        memset_0(v42, 0, sizeof(v42));
        LODWORD(v28) = v5->Data4[7];
        LODWORD(v27) = v5->Data4[6];
        LODWORD(v26) = v5->Data4[5];
        LODWORD(v25) = v5->Data4[4];
        LODWORD(v24) = v5->Data4[3];
        LODWORD(v23) = v5->Data4[2];
        LODWORD(v22) = v5->Data4[1];
        LODWORD(v21) = v5->Data4[0];
        LODWORD(v20) = v5->Data3;
        LODWORD(v19) = v5->Data2;
        StringCchPrintfW(
          v42,
          0x40u,
          L"%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x",
          v5->Data1,
          v19,
          v20,
          v21,
          v22,
          v23,
          v24,
          v25,
          v26,
          v27,
          v28);
        VdsTraceW(1, L"CVdsDiskLun::DismountDiskVolumes, 3, ObjectId=%s, hr=%lX", v42, (unsigned int)VolumeNameById);
        VolumeNameById = 0;
        goto LABEL_27;
      }
      hObject = 0;
      v9 = OpenDevice(v29, 0x80000000LL, &hObject);
      v10 = (unsigned int)v9;
      if ( !v9 )
      {
        LOBYTE(v10) = 1;
        v12 = LockDismountVolume(hObject, 1, v10);
        v13 = (unsigned int)hObject;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          CloseHandle(hObject);
          hObject = 0;
        }
        if ( v12 )
        {
          if ( v12 > 0 )
            v12 = (unsigned __int16)v12 | 0x80070000;
          v14 = L"UNKNOWN";
          if ( v29 )
            v14 = v29;
          VdsTraceW(1, L"CVdsDiskLun::DismountDiskVolumes, 5, %lX, name=%s", (unsigned int)v12, v14);
          VolumeNameById = 0;
        }
        CVdsService::SendVolumeNotification(v13, v5);
        goto LABEL_27;
      }
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      v11 = L"UNKNOWN";
      if ( v29 )
        v11 = v29;
      VdsTraceW(1, L"CVdsDiskLun::DismountDiskVolumes, 4, %lX, name=%s", v10, v11);
    }
    VolumeNameById = 0;
LABEL_27:
    ++i;
  }
LABEL_28:
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
  if ( v41 )
  {
    CoTaskMemFree(v41);
    v41 = 0;
  }
  if ( v37 )
  {
    CoTaskMemFree(v37);
    v37 = 0;
  }
  if ( v40 )
  {
    CoTaskMemFree(v40);
    v40 = 0;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v15 = v29;
  v16 = GetProcessHeap();
  VdsHeapFree(v16, 0, v15);
  v29 = 0;
  v17 = GetProcessHeap();
  VdsHeapFree(v17, 0, v31[1]);
  v31[1] = 0;
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
  return (unsigned int)VolumeNameById;
}

```

## disassembly

```asm
0x140028768  push    rbp
0x14002876a  push    rbx
0x14002876b  push    rsi
0x14002876c  push    rdi
0x14002876d  push    r12
0x14002876f  push    r13
0x140028771  push    r14
0x140028773  push    r15
0x140028775  lea     rbp, [rsp-0D8h]
0x14002877d  sub     rsp, 1D8h
0x140028784  mov     rax, cs:__security_cookie
0x14002878b  xor     rax, rsp
0x14002878e  mov     [rbp+110h+var_50], rax
0x140028795  mov     rbx, rcx
0x140028798  xor     r13d, r13d
0x14002879b  mov     [rsp+210h+var_1A0], r13
0x1400287a0  mov     [rsp+210h+hObject], r13
0x1400287a5  mov     [rbp+110h+var_180], r13
0x1400287a9  mov     esi, 80h
0x1400287ae  mov     r8d, esi; Size
0x1400287b1  xor     edx, edx; Val
0x1400287b3  lea     rcx, [rbp+110h+var_150]; void *
0x1400287b7  call    memset_0
0x1400287bc  xorps   xmm0, xmm0
0x1400287bf  movups  xmmword ptr [rbp+110h+var_190], xmm0
0x1400287c3  lea     r8, aCvdsdisklunDis_0; "CVdsDiskLun::DismountDiskVolumes"
0x1400287ca  lea     edi, [rsi-22h]
0x1400287cd  mov     edx, edi
0x1400287cf  lea     rcx, [rbp+110h+var_160]
0x1400287d3  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400287d9  nop
0x1400287da  mov     r8d, esi; Size
0x1400287dd  xor     edx, edx; Val
0x1400287df  lea     rcx, [rbp+110h+var_150]; void *
0x1400287e3  call    memset_0
0x1400287e8  mov     rcx, [rbx+0E0h]
0x1400287ef  mov     rax, [rcx]
0x1400287f2  lea     rdx, [rbp+110h+var_150]
0x1400287f6  mov     rax, [rax+18h]
0x1400287fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400287ff  mov     r14d, eax
0x140028802  cmp     [rbx+0E0h], r13
0x140028809  jnz     short loc_140028824
0x14002880b  mov     r9d, eax
0x14002880e  lea     r8, aCvdsdisklunDis_4; "CVdsDiskLun::DismountDiskVolumes, 1, hr"...
0x140028815  xor     edx, edx
0x140028817  mov     ecx, edi
0x140028819  call    cs:__imp_VdsTraceEx
0x14002881f  jmp     loc_140028A65
0x140028824  cmp     [rbp+110h+var_140], 4
0x140028828  jnz     short loc_14002883E
0x14002882a  lea     rdx, aCvdsdisklunGet_64; "CVdsDiskLun::GetIdentificationData, 1.5"
0x140028831  xor     ecx, ecx
0x140028833  call    cs:__imp_VdsTraceW
0x140028839  jmp     loc_140028A65
0x14002883e  xorps   xmm0, xmm0
0x140028841  movups  xmmword ptr [rbp+110h+var_190], xmm0
0x140028845  lea     r8, [rbp+110h+var_190]; struct _VDS_UNINSTALL_INFORMATION *
0x140028849  mov     edi, 1
0x14002884e  mov     edx, edi; unsigned int
0x140028850  lea     rcx, [rbp+110h+var_150]; struct _GUID *
0x140028854  call    ?GetVolumeIdList@CVdsService@@SAJPEAU_GUID@@KPEAU_VDS_UNINSTALL_INFORMATION@@@Z; CVdsService::GetVolumeIdList(_GUID *,ulong,_VDS_UNINSTALL_INFORMATION *)
0x140028859  mov     r14d, eax
0x14002885c  test    eax, eax
0x14002885e  jns     short loc_140028877
0x140028860  mov     r8d, eax
0x140028863  lea     rdx, aCvdsdisklunDis_3; "CVdsDiskLun::DismountDiskVolumes, 2, hr"...
0x14002886a  xor     ecx, ecx
0x14002886c  call    cs:__imp_VdsTraceW
0x140028872  jmp     loc_140028A65
0x140028877  mov     r15, [rbp+110h+var_190+8]
0x14002887b  mov     r12d, r13d
0x14002887e  cmp     dword ptr [rbp+110h+var_190], r13d
0x140028882  jbe     loc_140028A65
0x140028888  mov     r8, rsi; Size
0x14002888b  xor     edx, edx; Val
0x14002888d  lea     rcx, [rbp+110h+var_D0]; void *
0x140028891  call    memset_0
0x140028896  mov     rbx, [rsp+210h+var_1A0]
0x14002889b  call    cs:__imp_GetProcessHeap
0x1400288a1  mov     r8, rbx
0x1400288a4  xor     edx, edx
0x1400288a6  mov     rcx, rax
0x1400288a9  call    cs:__imp_VdsHeapFree
0x1400288af  mov     [rsp+210h+var_1A0], r13
0x1400288b4  movups  xmm0, xmmword ptr [r15]
0x1400288b8  movdqu  xmmword ptr [rbp+110h+var_170.Data1], xmm0
0x1400288bd  lea     r8, [rbp+110h+var_180]; unsigned __int64 *
0x1400288c1  lea     rdx, [rsp+210h+var_1A0]; unsigned __int16 **
0x1400288c6  lea     rcx, [rbp+110h+var_170]; struct _GUID
0x1400288ca  call    ?GetVolumeNameById@CVdsService@@SAJU_GUID@@PEAPEAGAEA_K@Z; CVdsService::GetVolumeNameById(_GUID,ushort * *,unsigned __int64 &)
0x1400288cf  mov     r14d, eax
0x1400288d2  cmp     eax, 80042711h
0x1400288d7  jnz     short loc_1400288E1
0x1400288d9  mov     r14d, r13d
0x1400288dc  jmp     loc_140028A54
0x1400288e1  test    r14d, r14d
0x1400288e4  jns     loc_140028994
0x1400288ea  mov     r8, rsi; Size
0x1400288ed  xor     edx, edx; Val
0x1400288ef  lea     rcx, [rbp+110h+var_D0]; void *
0x1400288f3  call    memset_0
0x1400288f8  movzx   eax, byte ptr [r15+0Fh]
0x1400288fd  movzx   ecx, byte ptr [r15+0Eh]
0x140028902  movzx   edx, byte ptr [r15+0Dh]
0x140028907  movzx   r8d, byte ptr [r15+0Ch]
0x14002890c  movzx   r9d, byte ptr [r15+0Bh]
0x140028911  movzx   r10d, byte ptr [r15+0Ah]
0x140028916  movzx   r11d, byte ptr [r15+9]
0x14002891b  movzx   ebx, byte ptr [r15+8]
0x140028920  movzx   edi, word ptr [r15+6]
0x140028925  movzx   esi, word ptr [r15+4]
0x14002892a  mov     dword ptr [rsp+210h+var_1A8], eax
0x14002892e  mov     dword ptr [rsp+210h+var_1B0], ecx
0x140028932  mov     dword ptr [rsp+210h+var_1B8], edx
0x140028936  mov     dword ptr [rsp+210h+var_1C0], r8d
0x14002893b  mov     dword ptr [rsp+210h+var_1C8], r9d
0x140028940  mov     dword ptr [rsp+210h+var_1D0], r10d
0x140028945  mov     dword ptr [rsp+210h+var_1D8], r11d
0x14002894a  mov     dword ptr [rsp+210h+var_1E0], ebx
0x14002894e  mov     dword ptr [rsp+210h+var_1E8], edi
0x140028952  mov     dword ptr [rsp+210h+var_1F0], esi
0x140028956  mov     r9d, [r15]
0x140028959  lea     r8, a8x4x4x2x2x2x2x; "%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2"...
0x140028960  mov     edx, 40h ; '@'; unsigned __int64
0x140028965  lea     rcx, [rbp+110h+var_D0]; unsigned __int16 *
0x140028969  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002896e  mov     r9d, r14d
0x140028971  lea     r8, [rbp+110h+var_D0]
0x140028975  lea     rdx, aCvdsdisklunDis_2; "CVdsDiskLun::DismountDiskVolumes, 3, Ob"...
0x14002897c  mov     edi, 1
0x140028981  mov     ecx, edi
0x140028983  call    cs:__imp_VdsTraceW
0x140028989  mov     r14d, r13d
0x14002898c  lea     esi, [rdi+7Fh]
0x14002898f  jmp     loc_140028A54
0x140028994  mov     [rsp+210h+hObject], r13
0x140028999  lea     r8, [rsp+210h+hObject]
0x14002899e  mov     edx, 80000000h
0x1400289a3  mov     rcx, [rsp+210h+var_1A0]
0x1400289a8  call    cs:__imp_OpenDevice
0x1400289ae  mov     r8d, eax
0x1400289b1  test    eax, eax
0x1400289b3  jz      short loc_1400289E9
0x1400289b5  jle     short loc_1400289C2
0x1400289b7  movzx   r8d, ax
0x1400289bb  or      r8d, 80070000h
0x1400289c2  lea     r9, aUnknown_0; "UNKNOWN"
0x1400289c9  mov     rax, [rsp+210h+var_1A0]
0x1400289ce  test    rax, rax
0x1400289d1  cmovnz  r9, rax
0x1400289d5  lea     rdx, aCvdsdisklunDis_1; "CVdsDiskLun::DismountDiskVolumes, 4, %l"...
0x1400289dc  mov     ecx, edi
0x1400289de  call    cs:__imp_VdsTraceW
0x1400289e4  jmp     loc_1400288D9
0x1400289e9  mov     r8b, dil
0x1400289ec  mov     edx, edi
0x1400289ee  mov     rcx, [rsp+210h+hObject]
0x1400289f3  call    cs:__imp_LockDismountVolume
0x1400289f9  mov     ebx, eax
0x1400289fb  mov     rcx, [rsp+210h+hObject]; hObject
0x140028a00  lea     rax, [rcx-1]
0x140028a04  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140028a08  ja      short loc_140028A15
0x140028a0a  call    cs:__imp_CloseHandle
0x140028a10  mov     [rsp+210h+hObject], r13
0x140028a15  test    ebx, ebx
0x140028a17  jz      short loc_140028A4C
0x140028a19  jle     short loc_140028A24
0x140028a1b  movzx   ebx, bx
0x140028a1e  or      ebx, 80070000h
0x140028a24  lea     r9, aUnknown_0; "UNKNOWN"
0x140028a2b  mov     rax, [rsp+210h+var_1A0]
0x140028a30  test    rax, rax
0x140028a33  cmovnz  r9, rax
0x140028a37  mov     r8d, ebx
0x140028a3a  lea     rdx, aCvdsdisklunDis; "CVdsDiskLun::DismountDiskVolumes, 5, %l"...
0x140028a41  mov     ecx, edi
0x140028a43  call    cs:__imp_VdsTraceW
0x140028a49  mov     r14d, r13d
0x140028a4c  mov     rdx, r15; struct _GUID *
0x140028a4f  call    ?SendVolumeNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendVolumeNotification(ulong,_GUID &)
0x140028a54  add     r12d, edi
0x140028a57  add     r15, 10h
0x140028a5b  cmp     r12d, dword ptr [rbp+110h+var_190]
0x140028a5f  jb      loc_140028888
0x140028a65  mov     rcx, [rbp+110h+pv]; pv
0x140028a69  test    rcx, rcx
0x140028a6c  jz      short loc_140028A78
0x140028a6e  call    cs:__imp_CoTaskMemFree
0x140028a74  mov     [rbp+110h+pv], r13
0x140028a78  mov     rcx, [rbp+110h+var_E8]; pv
0x140028a7c  test    rcx, rcx
0x140028a7f  jz      short loc_140028A8B
0x140028a81  call    cs:__imp_CoTaskMemFree
0x140028a87  mov     [rbp+110h+var_E8], r13
0x140028a8b  mov     rcx, [rbp+110h+var_D8]; pv
0x140028a8f  test    rcx, rcx
0x140028a92  jz      short loc_140028A9E
0x140028a94  call    cs:__imp_CoTaskMemFree
0x140028a9a  mov     [rbp+110h+var_D8], r13
0x140028a9e  mov     rcx, [rbp+110h+var_F8]; pv
0x140028aa2  test    rcx, rcx
0x140028aa5  jz      short loc_140028AB1
0x140028aa7  call    cs:__imp_CoTaskMemFree
0x140028aad  mov     [rbp+110h+var_F8], r13
0x140028ab1  mov     rcx, [rbp+110h+var_E0]; pv
0x140028ab5  test    rcx, rcx
0x140028ab8  jz      short loc_140028AC4
0x140028aba  call    cs:__imp_CoTaskMemFree
0x140028ac0  mov     [rbp+110h+var_E0], r13
0x140028ac4  mov     rcx, [rsp+210h+hObject]; hObject
0x140028ac9  lea     rax, [rcx-1]
0x140028acd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140028ad1  ja      short loc_140028ADE
0x140028ad3  call    cs:__imp_CloseHandle
0x140028ad9  mov     [rsp+210h+hObject], r13
0x140028ade  mov     rbx, [rsp+210h+var_1A0]
0x140028ae3  call    cs:__imp_GetProcessHeap
0x140028ae9  mov     r8, rbx
0x140028aec  xor     edx, edx
0x140028aee  mov     rcx, rax
0x140028af1  call    cs:__imp_VdsHeapFree
0x140028af7  mov     [rsp+210h+var_1A0], r13
0x140028afc  call    cs:__imp_GetProcessHeap
0x140028b02  mov     rcx, rax
0x140028b05  mov     r8, [rbp+110h+var_190+8]
0x140028b09  xor     edx, edx
0x140028b0b  call    cs:__imp_VdsHeapFree
0x140028b11  mov     [rbp+110h+var_190+8], r13
0x140028b15  lea     rcx, [rbp+110h+var_160]
0x140028b19  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140028b1f  mov     eax, r14d
0x140028b22  mov     rcx, [rbp+110h+var_50]
0x140028b29  xor     rcx, rsp; StackCookie
0x140028b2c  call    __security_check_cookie
0x140028b31  add     rsp, 1D8h
0x140028b38  pop     r15
0x140028b3a  pop     r14
0x140028b3c  pop     r13
0x140028b3e  pop     r12
0x140028b40  pop     rdi
0x140028b41  pop     rsi
0x140028b42  pop     rbx
0x140028b43  pop     rbp
0x140028b44  retn
```
