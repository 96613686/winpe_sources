# CVdsVolume::IsBasicMbrAndCriticalFlags(uchar *)

- ea: `0x140026550`
- end: `0x140026a00`
- name: `?IsBasicMbrAndCriticalFlags@CVdsVolume@@AEAAJPEAE@Z`
- size: `1200`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140043350`

## callees

- `0x1400069e8`
- `0x140026550`
- `0x14002e123`
- `0x140042948`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026748`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002695a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026748`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002695a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400268e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002691e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400268e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002691e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002690e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002690e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026946`
- `vdsutil!OpenDevice` at `0x14002679c`
- `vdsutil!OpenDevice` at `0x140026849`
- `vdsutil!OpenDevice` at `0x14002679c`
- `vdsutil!OpenDevice` at `0x140026849`
- `vdsutil!GetDiskLayout` at `0x140026878`
- `vdsutil!GetDiskLayout` at `0x140026878`
- `vdsutil!GetVolumeDiskExtentInfo` at `0x1400267ce`
- `vdsutil!GetVolumeDiskExtentInfo` at `0x1400267ce`
- `vdsutil!VdsHeapFree` at `0x1400268f4`
- `vdsutil!VdsHeapFree` at `0x14002692c`
- `vdsutil!VdsHeapFree` at `0x1400268f4`
- `vdsutil!VdsHeapFree` at `0x14002692c`
- `vdsutil!VdsTraceEx` at `0x1400268db`
- `vdsutil!VdsTraceEx` at `0x1400268db`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400265d8`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400265d8`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400269d4`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400269d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsVolume::IsBasicMbrAndCriticalFlags(CVdsVolume *this, unsigned __int8 *a2)
{
  unsigned int IsVolumeOnDynamicDisk; // edi
  int v5; // eax
  const char *v6; // r8
  int v7; // eax
  int VolumeDiskExtentInfo; // eax
  _DWORD *v9; // rbx
  int v10; // eax
  int DiskLayout; // eax
  _DWORD *v12; // rbx
  HANDLE ProcessHeap; // rax
  _DWORD *v14; // rbx
  HANDLE v15; // rax
  unsigned __int8 v17[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD *v20; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v22; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  __int64 v25; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v27[16]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+90h] [rbp-70h] BYREF
  __int128 v29; // [rsp+A0h] [rbp-60h]
  __int128 v30; // [rsp+B0h] [rbp-50h]
  LPVOID pv; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v32[64]; // [rsp+D0h] [rbp-30h] BYREF

  v25 = 0;
  v24 = 0;
  v19 = 0;
  v26 = 0;
  v18 = 0;
  v23 = 0;
  v22 = 0;
  hObject = 0;
  v17[0] = 0;
  v20 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  pv = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v27, 0x5Eu, "CVdsVolume::IsBasicMbrAndCriticalFlags()");
  memset_0(v32, 0, sizeof(v32));
  v28 = 0;
  v29 = 0;
  v30 = 0;
  pv = 0;
  if ( !a2 )
  {
    IsVolumeOnDynamicDisk = -2147212216;
    VdsTraceEx(94, 0, "CVdsVolume::IsBasicMbrAndCriticalFlags, 1, hr=%lX", 2147942487LL);
    goto LABEL_53;
  }
  *a2 = 0;
  IsVolumeOnDynamicDisk = CVdsVolume::IsVolumeOnDynamicDisk(this, v17);
  if ( (IsVolumeOnDynamicDisk & 0x80000000) != 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::IsBasicMbrAndCriticalFlags, 2, hr=%lX", 2147942487LL);
    goto LABEL_53;
  }
  if ( !v17[0] )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 16) + 32LL))(*((_QWORD *)this + 16), &v25);
    IsVolumeOnDynamicDisk = v5;
    if ( v5 < 0 )
    {
      v6 = "CVdsVolume::IsBasicMbrAndCriticalFlags, 3, hr=%lX";
LABEL_52:
      VdsTraceEx(94, 0, v6, (unsigned int)v5);
      goto LABEL_53;
    }
    if ( !v25 )
    {
      IsVolumeOnDynamicDisk = -2147212216;
      VdsTraceEx(94, 0, "CVdsVolume::IsBasicMbrAndCriticalFlags, 4, hr=%lX", 2147755080LL);
      goto LABEL_53;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 40LL))(v25, &v24);
    IsVolumeOnDynamicDisk = v5;
    if ( v5 < 0 )
    {
      v6 = "CVdsVolume::IsBasicMbrAndCriticalFlags, 5, hr=%lX";
      goto LABEL_52;
    }
    do
    {
      v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v24 + 24LL))(v24, 1, &v19, &v26);
      IsVolumeOnDynamicDisk = v5;
      if ( v5 == 1 )
        break;
      if ( v5 < 0 )
      {
        v6 = "CVdsVolume::IsBasicMbrAndCriticalFlags, 6, hr=%lX";
        goto LABEL_52;
      }
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(v19, &IID_IVdsVolume, &v18);
      IsVolumeOnDynamicDisk = v5;
      if ( v5 < 0 )
      {
        v6 = "CVdsVolume::IsBasicMbrAndCriticalFlags, 7, hr=%lX";
        goto LABEL_52;
      }
      IsVolumeOnDynamicDisk = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v18 + 24LL))(v18, &v28);
      if ( (IsVolumeOnDynamicDisk & 0x80000000) != 0 )
      {
        VdsTraceEx(94, 0, "CVdsVolume::IsBasicMbrAndCriticalFlags, 8, hr=%lX", IsVolumeOnDynamicDisk);
        break;
      }
      if ( (DWORD2(v30) & 0x1000383) != 0 )
      {
        v7 = OpenDevice(pv, 0, &v23);
        if ( v7 )
        {
          if ( v7 > 0 )
            IsVolumeOnDynamicDisk = (unsigned __int16)v7 | 0x80070000;
          else
            IsVolumeOnDynamicDisk = v7;
          VdsTraceEx(94, 0, "CVdsVolume::IsBasicMbrAndCriticalFlags, 9, hr=%lX", IsVolumeOnDynamicDisk);
        }
        else
        {
          VolumeDiskExtentInfo = GetVolumeDiskExtentInfo(v23, &v22);
          if ( VolumeDiskExtentInfo )
          {
            if ( VolumeDiskExtentInfo > 0 )
              IsVolumeOnDynamicDisk = (unsigned __int16)VolumeDiskExtentInfo | 0x80070000;
            else
              IsVolumeOnDynamicDisk = VolumeDiskExtentInfo;
            VdsTraceEx(94, 0, "CVdsVolume::IsBasicMbrAndCriticalFlags, 10, hr=%lX", IsVolumeOnDynamicDisk);
          }
          else
          {
            v9 = v22;
            if ( *v22 )
            {
              memset_0(v32, 0, sizeof(v32));
              StringCchPrintfW(v32, 0x40u, L"\\Device\\Harddisk%ld\\Partition0", (unsigned int)v9[2]);
              v10 = OpenDevice(v32, 0, &hObject);
              if ( v10 )
              {
                if ( v10 > 0 )
                  IsVolumeOnDynamicDisk = (unsigned __int16)v10 | 0x80070000;
                else
                  IsVolumeOnDynamicDisk = v10;
                VdsTraceEx(94, 0, "CVdsVolume::IsBasicMbrAndCriticalFlags, 12, hr=%lX", IsVolumeOnDynamicDisk);
              }
              else
              {
                DiskLayout = GetDiskLayout(hObject, &v20);
                if ( DiskLayout )
                {
                  if ( DiskLayout > 0 )
                    IsVolumeOnDynamicDisk = (unsigned __int16)DiskLayout | 0x80070000;
                  else
                    IsVolumeOnDynamicDisk = DiskLayout;
                  VdsTraceEx(94, 0, "CVdsVolume::IsBasicMbrAndCriticalFlags, 13, hr=%lX", IsVolumeOnDynamicDisk);
                }
                else if ( !*v20 )
                {
                  IsVolumeOnDynamicDisk = -2147212278;
                  VdsTraceEx(94, 0, "CVdsVolume::IsBasicMbrAndCriticalFlags, 14, hr=%lX", 2147755018LL);
                }
              }
            }
            else
            {
              IsVolumeOnDynamicDisk = -2147212216;
              VdsTraceEx(94, 0, "CVdsVolume::IsBasicMbrAndCriticalFlags, 11, hr=%lX", 2147755080LL);
            }
          }
        }
        break;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v19 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        v19 = 0;
      }
      if ( v18 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        v18 = 0;
      }
    }
    while ( !IsVolumeOnDynamicDisk );
  }
LABEL_53:
  v12 = v20;
  ProcessHeap = GetProcessHeap();
  VdsHeapFree(ProcessHeap, 0, v12);
  v20 = 0;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v14 = v22;
  v15 = GetProcessHeap();
  VdsHeapFree(v15, 0, v14);
  v22 = 0;
  if ( (char *)v23 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(v23);
    v23 = 0;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v27);
  return IsVolumeOnDynamicDisk;
}

```

## disassembly

```asm
0x140026550  mov     [rsp-8+arg_10], rbx
0x140026555  mov     [rsp-8+arg_18], rsi
0x14002655a  push    rbp
0x14002655b  push    rdi
0x14002655c  push    r14
0x14002655e  lea     rbp, [rsp-60h]
0x140026563  sub     rsp, 160h
0x14002656a  mov     rax, cs:__security_cookie
0x140026571  xor     rax, rsp
0x140026574  mov     [rbp+70h+var_20], rax
0x140026578  mov     rdi, rdx
0x14002657b  mov     rbx, rcx
0x14002657e  xor     esi, esi
0x140026580  mov     [rsp+170h+var_100], rsi
0x140026585  mov     [rsp+170h+var_108], rsi
0x14002658a  mov     [rsp+170h+var_130], rsi
0x14002658f  mov     [rsp+170h+var_F8], esi
0x140026593  mov     [rsp+170h+var_138], rsi
0x140026598  mov     [rsp+170h+var_110], rsi
0x14002659d  mov     [rsp+170h+var_118], rsi
0x1400265a2  mov     [rsp+170h+hObject], rsi
0x1400265a7  mov     [rsp+170h+var_140], sil
0x1400265ac  mov     [rsp+170h+var_128], rsi
0x1400265b1  xorps   xmm0, xmm0
0x1400265b4  xor     eax, eax
0x1400265b6  movups  [rbp+70h+var_E0], xmm0
0x1400265ba  movups  [rbp+70h+var_D0], xmm0
0x1400265be  movups  [rbp+70h+var_C0], xmm0
0x1400265c2  mov     [rbp+70h+pv], rax
0x1400265c6  lea     r8, aCvdsvolumeIsba_8; "CVdsVolume::IsBasicMbrAndCriticalFlags("...
0x1400265cd  lea     r14d, [rsi+5Eh]
0x1400265d1  mov     edx, r14d
0x1400265d4  lea     rcx, [rbp+70h+var_F0]
0x1400265d8  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400265de  nop
0x1400265df  xor     edx, edx; Val
0x1400265e1  lea     r8d, [r14+22h]; Size
0x1400265e5  lea     rcx, [rbp+70h+var_A0]; void *
0x1400265e9  call    memset_0
0x1400265ee  xorps   xmm0, xmm0
0x1400265f1  xor     eax, eax
0x1400265f3  movups  [rbp+70h+var_E0], xmm0
0x1400265f7  movups  [rbp+70h+var_D0], xmm0
0x1400265fb  movups  [rbp+70h+var_C0], xmm0
0x1400265ff  mov     [rbp+70h+pv], rax
0x140026603  test    rdi, rdi
0x140026606  jnz     short loc_14002661F
0x140026608  mov     edi, 80042448h
0x14002660d  mov     r9d, 80070057h
0x140026613  lea     r8, aCvdsvolumeIsba_10; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x14002661a  jmp     loc_1400268D6
0x14002661f  mov     [rdi], sil
0x140026622  lea     rdx, [rsp+170h+var_140]; unsigned __int8 *
0x140026627  mov     rcx, rbx; this
0x14002662a  call    ?IsVolumeOnDynamicDisk@CVdsVolume@@AEAAJPEAE@Z; CVdsVolume::IsVolumeOnDynamicDisk(uchar *)
0x14002662f  mov     edi, eax
0x140026631  test    eax, eax
0x140026633  jns     short loc_140026647
0x140026635  mov     r9d, 80070057h
0x14002663b  lea     r8, aCvdsvolumeIsba_9; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x140026642  jmp     loc_1400268D6
0x140026647  cmp     [rsp+170h+var_140], sil
0x14002664c  jnz     loc_1400268E1
0x140026652  mov     rcx, [rbx+80h]
0x140026659  mov     rax, [rcx]
0x14002665c  lea     rdx, [rsp+170h+var_100]
0x140026661  mov     rax, [rax+20h]
0x140026665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002666a  mov     edi, eax
0x14002666c  test    eax, eax
0x14002666e  jns     short loc_14002667C
0x140026670  lea     r8, aCvdsvolumeIsba_2; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x140026677  jmp     loc_1400268D3
0x14002667c  mov     rcx, [rsp+170h+var_100]
0x140026681  test    rcx, rcx
0x140026684  jnz     short loc_14002669B
0x140026686  mov     r9d, 80042448h
0x14002668c  mov     edi, r9d
0x14002668f  lea     r8, aCvdsvolumeIsba_7; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x140026696  jmp     loc_1400268D6
0x14002669b  mov     rax, [rcx]
0x14002669e  lea     rdx, [rsp+170h+var_108]
0x1400266a3  mov     rax, [rax+28h]
0x1400266a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400266ac  mov     edi, eax
0x1400266ae  test    eax, eax
0x1400266b0  jns     short loc_1400266BE
0x1400266b2  lea     r8, aCvdsvolumeIsba_5; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x1400266b9  jmp     loc_1400268D3
0x1400266be  mov     rcx, [rsp+170h+var_108]
0x1400266c3  mov     rax, [rcx]
0x1400266c6  lea     r9, [rsp+170h+var_F8]
0x1400266cb  lea     r8, [rsp+170h+var_130]
0x1400266d0  mov     edx, 1
0x1400266d5  mov     rax, [rax+18h]
0x1400266d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400266de  mov     edi, eax
0x1400266e0  cmp     eax, 1
0x1400266e3  jz      loc_1400268E1
0x1400266e9  test    eax, eax
0x1400266eb  js      loc_1400268CC
0x1400266f1  mov     rcx, [rsp+170h+var_130]
0x1400266f6  mov     rax, [rcx]
0x1400266f9  lea     r8, [rsp+170h+var_138]
0x1400266fe  lea     rdx, IID_IVdsVolume
0x140026705  mov     rax, [rax]
0x140026708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002670d  mov     edi, eax
0x14002670f  test    eax, eax
0x140026711  js      loc_1400268C3
0x140026717  mov     rcx, [rsp+170h+var_138]
0x14002671c  mov     rax, [rcx]
0x14002671f  lea     rdx, [rbp+70h+var_E0]
0x140026723  mov     rax, [rax+18h]
0x140026727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002672c  mov     edi, eax
0x14002672e  test    eax, eax
0x140026730  js      loc_1400268B7
0x140026736  mov     rcx, [rbp+70h+pv]; pv
0x14002673a  test    dword ptr [rbp+70h+var_C0+8], 1000383h
0x140026741  jnz     short loc_140026795
0x140026743  test    rcx, rcx
0x140026746  jz      short loc_140026752
0x140026748  call    cs:__imp_CoTaskMemFree
0x14002674e  mov     [rbp+70h+pv], rsi
0x140026752  mov     rcx, [rsp+170h+var_130]
0x140026757  test    rcx, rcx
0x14002675a  jz      short loc_14002676D
0x14002675c  mov     rax, [rcx]
0x14002675f  mov     rax, [rax+10h]
0x140026763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026768  mov     [rsp+170h+var_130], rsi
0x14002676d  mov     rcx, [rsp+170h+var_138]
0x140026772  test    rcx, rcx
0x140026775  jz      short loc_140026788
0x140026777  mov     rax, [rcx]
0x14002677a  mov     rax, [rax+10h]
0x14002677e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026783  mov     [rsp+170h+var_138], rsi
0x140026788  test    edi, edi
0x14002678a  jz      loc_1400266BE
0x140026790  jmp     loc_1400268E1
0x140026795  lea     r8, [rsp+170h+var_110]
0x14002679a  xor     edx, edx
0x14002679c  call    cs:__imp_OpenDevice
0x1400267a2  test    eax, eax
0x1400267a4  jz      short loc_1400267C4
0x1400267a6  jg      short loc_1400267AC
0x1400267a8  mov     edi, eax
0x1400267aa  jmp     short loc_1400267B5
0x1400267ac  movzx   edi, ax
0x1400267af  or      edi, 80070000h
0x1400267b5  mov     r9d, edi
0x1400267b8  lea     r8, aCvdsvolumeIsba_12; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x1400267bf  jmp     loc_1400268D6
0x1400267c4  lea     rdx, [rsp+170h+var_118]
0x1400267c9  mov     rcx, [rsp+170h+var_110]
0x1400267ce  call    cs:__imp_GetVolumeDiskExtentInfo
0x1400267d4  test    eax, eax
0x1400267d6  jz      short loc_1400267F6
0x1400267d8  jg      short loc_1400267DE
0x1400267da  mov     edi, eax
0x1400267dc  jmp     short loc_1400267E7
0x1400267de  movzx   edi, ax
0x1400267e1  or      edi, 80070000h
0x1400267e7  mov     r9d, edi
0x1400267ea  lea     r8, aCvdsvolumeIsba_1; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x1400267f1  jmp     loc_1400268D6
0x1400267f6  mov     rbx, [rsp+170h+var_118]
0x1400267fb  cmp     [rbx], esi
0x1400267fd  jnz     short loc_140026814
0x1400267ff  mov     r9d, 80042448h
0x140026805  mov     edi, r9d
0x140026808  lea     r8, aCvdsvolumeIsba_13; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x14002680f  jmp     loc_1400268D6
0x140026814  xor     edx, edx; Val
0x140026816  mov     r8d, 80h; Size
0x14002681c  lea     rcx, [rbp+70h+var_A0]; void *
0x140026820  call    memset_0
0x140026825  mov     r9d, [rbx+8]
0x140026829  lea     r8, aDeviceHarddisk_0; "\\Device\\Harddisk%ld\\Partition0"
0x140026830  mov     edx, 40h ; '@'; unsigned __int64
0x140026835  lea     rcx, [rbp+70h+var_A0]; unsigned __int16 *
0x140026839  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002683e  lea     r8, [rsp+170h+hObject]
0x140026843  xor     edx, edx
0x140026845  lea     rcx, [rbp+70h+var_A0]
0x140026849  call    cs:__imp_OpenDevice
0x14002684f  test    eax, eax
0x140026851  jz      short loc_14002686E
0x140026853  jg      short loc_140026859
0x140026855  mov     edi, eax
0x140026857  jmp     short loc_140026862
0x140026859  movzx   edi, ax
0x14002685c  or      edi, 80070000h
0x140026862  mov     r9d, edi
0x140026865  lea     r8, aCvdsvolumeIsba_4; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x14002686c  jmp     short loc_1400268D6
0x14002686e  lea     rdx, [rsp+170h+var_128]
0x140026873  mov     rcx, [rsp+170h+hObject]
0x140026878  call    cs:__imp_GetDiskLayout
0x14002687e  test    eax, eax
0x140026880  jz      short loc_14002689D
0x140026882  jg      short loc_140026888
0x140026884  mov     edi, eax
0x140026886  jmp     short loc_140026891
0x140026888  movzx   edi, ax
0x14002688b  or      edi, 80070000h
0x140026891  mov     r9d, edi
0x140026894  lea     r8, aCvdsvolumeIsba_0; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x14002689b  jmp     short loc_1400268D6
0x14002689d  mov     rax, [rsp+170h+var_128]
0x1400268a2  cmp     [rax], esi
0x1400268a4  jnz     short loc_1400268E1
0x1400268a6  mov     edi, 8004240Ah
0x1400268ab  mov     r9d, edi
0x1400268ae  lea     r8, aCvdsvolumeIsba_6; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x1400268b5  jmp     short loc_1400268D6
0x1400268b7  mov     r9d, edi
0x1400268ba  lea     r8, aCvdsvolumeIsba_3; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x1400268c1  jmp     short loc_1400268D6
0x1400268c3  lea     r8, aCvdsvolumeIsba_11; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x1400268ca  jmp     short loc_1400268D3
0x1400268cc  lea     r8, aCvdsvolumeIsba; "CVdsVolume::IsBasicMbrAndCriticalFlags,"...
0x1400268d3  mov     r9d, eax
0x1400268d6  xor     edx, edx
0x1400268d8  mov     ecx, r14d
0x1400268db  call    cs:__imp_VdsTraceEx
0x1400268e1  mov     rbx, [rsp+170h+var_128]
0x1400268e6  call    cs:__imp_GetProcessHeap
0x1400268ec  mov     r8, rbx
0x1400268ef  xor     edx, edx
0x1400268f1  mov     rcx, rax
0x1400268f4  call    cs:__imp_VdsHeapFree
0x1400268fa  mov     [rsp+170h+var_128], rsi
0x1400268ff  mov     rcx, [rsp+170h+hObject]; hObject
0x140026904  lea     rax, [rcx-1]
0x140026908  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002690c  ja      short loc_140026919
0x14002690e  call    cs:__imp_CloseHandle
0x140026914  mov     [rsp+170h+hObject], rsi
0x140026919  mov     rbx, [rsp+170h+var_118]
0x14002691e  call    cs:__imp_GetProcessHeap
0x140026924  mov     r8, rbx
0x140026927  xor     edx, edx
0x140026929  mov     rcx, rax
0x14002692c  call    cs:__imp_VdsHeapFree
0x140026932  mov     [rsp+170h+var_118], rsi
0x140026937  mov     rcx, [rsp+170h+var_110]; hObject
0x14002693c  lea     rax, [rcx-1]
0x140026940  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140026944  ja      short loc_140026951
0x140026946  call    cs:__imp_CloseHandle
0x14002694c  mov     [rsp+170h+var_110], rsi
0x140026951  mov     rcx, [rbp+70h+pv]; pv
0x140026955  test    rcx, rcx
0x140026958  jz      short loc_140026964
0x14002695a  call    cs:__imp_CoTaskMemFree
0x140026960  mov     [rbp+70h+pv], rsi
0x140026964  mov     rcx, [rsp+170h+var_138]
0x140026969  test    rcx, rcx
0x14002696c  jz      short loc_14002697F
0x14002696e  mov     rax, [rcx]
0x140026971  mov     rax, [rax+10h]
0x140026975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002697a  mov     [rsp+170h+var_138], rsi
0x14002697f  mov     rcx, [rsp+170h+var_130]
0x140026984  test    rcx, rcx
0x140026987  jz      short loc_14002699A
0x140026989  mov     rax, [rcx]
0x14002698c  mov     rax, [rax+10h]
0x140026990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026995  mov     [rsp+170h+var_130], rsi
0x14002699a  mov     rcx, [rsp+170h+var_108]
0x14002699f  test    rcx, rcx
0x1400269a2  jz      short loc_1400269B5
0x1400269a4  mov     rax, [rcx]
0x1400269a7  mov     rax, [rax+10h]
0x1400269ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400269b0  mov     [rsp+170h+var_108], rsi
0x1400269b5  mov     rcx, [rsp+170h+var_100]
0x1400269ba  test    rcx, rcx
0x1400269bd  jz      short loc_1400269D0
0x1400269bf  mov     rax, [rcx]
0x1400269c2  mov     rax, [rax+10h]
0x1400269c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400269cb  mov     [rsp+170h+var_100], rsi
0x1400269d0  lea     rcx, [rbp+70h+var_F0]
0x1400269d4  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400269da  mov     eax, edi
0x1400269dc  mov     rcx, [rbp+70h+var_20]
0x1400269e0  xor     rcx, rsp; StackCookie
0x1400269e3  call    __security_check_cookie
0x1400269e8  lea     r11, [rsp+170h+var_10]
0x1400269f0  mov     rbx, [r11+30h]
0x1400269f4  mov     rsi, [r11+38h]
0x1400269f8  mov     rsp, r11
0x1400269fb  pop     r14
0x1400269fd  pop     rdi
0x1400269fe  pop     rbp
  ... truncated ...
```
