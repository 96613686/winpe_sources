# CVdsVolume::QueryAccessPathsToVolume(ushort *,ushort * * *,long *)

- ea: `0x140008580`
- end: `0x140008825`
- name: `?QueryAccessPathsToVolume@CVdsVolume@@SAKPEAGPEAPEAPEAGPEAJ@Z`
- size: `677`
- prototype: `unsigned int __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 ***, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001fe40`

## callees

- `0x140008580`
- `0x14000f930`
- `0x14002e123`
- `0x14003cd8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400086bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140008726`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400086bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140008726`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000878e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400087a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000878e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400087a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400085e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400086d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008808`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400085e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400086d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400085da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400085da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008629`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1400085d4`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x14000861f`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1400085d4`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x14000861f`
- `vdsutil!VdsHeapAlloc` at `0x1400085f8`
- `vdsutil!VdsHeapAlloc` at `0x1400085f8`
- `vdsutil!VdsHeapFree` at `0x1400086e4`
- `vdsutil!VdsHeapFree` at `0x140008816`
- `vdsutil!VdsHeapFree` at `0x1400086e4`
- `vdsutil!VdsHeapFree` at `0x140008816`
- `vdsutil!VdsTraceEx` at `0x140008642`
- `vdsutil!VdsTraceEx` at `0x140008642`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400085c0`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400085c0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000864e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400086cf`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400087b7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400087e7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140008801`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000864e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400086cf`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400087b7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400087e7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140008801`

## string_xrefs

- `0x1400085af`: `CVdsVolume::QueryAccessPathsToVolume()`
- `0x140008634`: `CVdsVolume::QueryAccessPathsToVolume: GetVolumePathNamesForVolumeName failed: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsVolume::QueryAccessPathsToVolume(LPCWSTR lpszVolumeName, LPVOID *a2, unsigned int *a3)
{
  __int64 v6; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // rax
  const unsigned __int16 *v9; // rbp
  DWORD LastError; // ebx
  unsigned int v12; // ebx
  const unsigned __int16 *v13; // rcx
  __int64 v14; // rax
  unsigned __int16 **v15; // rax
  HANDLE v16; // rax
  unsigned int i; // edi
  unsigned __int64 v18; // rsi
  __int64 v19; // r14
  unsigned __int16 *v20; // rcx
  unsigned int j; // ebx
  __int64 v22; // rsi
  unsigned __int16 *v23; // rcx
  HANDLE v24; // rax
  DWORD cchReturnLength; // [rsp+20h] [rbp-68h] BYREF
  DWORD v26; // [rsp+24h] [rbp-64h] BYREF
  WCHAR *v27; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v28[88]; // [rsp+30h] [rbp-58h] BYREF

  cchReturnLength = 0;
  v27 = 0;
  v26 = 0;
  *a2 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v28, 0x5Eu, "CVdsVolume::QueryAccessPathsToVolume()");
  GetVolumePathNamesForVolumeNameW(lpszVolumeName, 0, 0, &cchReturnLength);
  GetLastError();
  v6 = 2LL * cchReturnLength;
  ProcessHeap = GetProcessHeap();
  v8 = (WCHAR *)VdsHeapAlloc(ProcessHeap, 8, v6);
  v9 = v8;
  v27 = v8;
  if ( !v8 )
    goto LABEL_24;
  if ( !GetVolumePathNamesForVolumeNameW(lpszVolumeName, v8, cchReturnLength, &v26) )
  {
    LastError = GetLastError();
    VdsTraceEx(94, 0, "CVdsVolume::QueryAccessPathsToVolume: GetVolumePathNamesForVolumeName failed: %X", LastError);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v27);
    return LastError;
  }
  if ( *v9 )
  {
    v12 = 0;
    v13 = v9;
    do
    {
      v14 = -1;
      do
        ++v14;
      while ( v13[v14] );
      v13 += v14 + 1;
      ++v12;
    }
    while ( *v13 );
    if ( v12 )
    {
      v15 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v12);
      *a2 = v15;
      if ( !v15 )
      {
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
        v16 = GetProcessHeap();
        VdsHeapFree(v16, 0, v9);
        v27 = 0;
        return 8;
      }
      memset_0(v15, 0, 8LL * v12);
      for ( i = 0; ; ++i )
      {
        if ( i >= v12 )
        {
          *a3 = v12;
          CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
          CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v27);
          return 0;
        }
        v18 = -1;
        do
          ++v18;
        while ( v9[v18] );
        v19 = 8LL * i;
        *(_QWORD *)((char *)*a2 + v19) = CoTaskMemAlloc(2 * v18 + 2);
        v20 = *(unsigned __int16 **)((char *)*a2 + v19);
        if ( !v20 )
          break;
        StringCchCopyNW(v20, v18 + 1, v9, v18);
        *(_WORD *)(*(_QWORD *)((char *)*a2 + v19) + 2 * v18) = 0;
        v9 += v18 + 1;
      }
      for ( j = 0; j < i; ++j )
      {
        v22 = 8LL * j;
        v23 = *(unsigned __int16 **)((char *)*a2 + v22);
        if ( v23 )
        {
          CoTaskMemFree(v23);
          *(_QWORD *)((char *)*a2 + v22) = 0;
        }
      }
      if ( *a2 )
      {
        CoTaskMemFree(*a2);
        *a2 = 0;
      }
LABEL_24:
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
      CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v27);
      return 8;
    }
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
  v24 = GetProcessHeap();
  VdsHeapFree(v24, 0, v9);
  return 0;
}

```

## disassembly

```asm
0x140008580  push    rbx
0x140008582  push    rbp
0x140008583  push    rsi
0x140008584  push    rdi
0x140008585  push    r12
0x140008587  push    r13
0x140008589  push    r14
0x14000858b  push    r15
0x14000858d  sub     rsp, 48h
0x140008591  mov     r12, r8
0x140008594  mov     r15, rdx
0x140008597  mov     rdi, rcx
0x14000859a  xor     r13d, r13d
0x14000859d  mov     [rsp+88h+cchReturnLength], r13d
0x1400085a2  mov     [rsp+88h+var_60], r13
0x1400085a7  mov     [rsp+88h+var_64], r13d
0x1400085ac  mov     [rdx], r13
0x1400085af  lea     r8, aCvdsvolumeQuer_7; "CVdsVolume::QueryAccessPathsToVolume()"
0x1400085b6  mov     edx, 5Eh ; '^'
0x1400085bb  lea     rcx, [rsp+88h+var_58]
0x1400085c0  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400085c6  nop
0x1400085c7  lea     r9, [rsp+88h+cchReturnLength]; lpcchReturnLength
0x1400085cc  xor     r8d, r8d; cchBufferLength
0x1400085cf  xor     edx, edx; lpszVolumePathNames
0x1400085d1  mov     rcx, rdi; lpszVolumeName
0x1400085d4  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1400085da  call    cs:__imp_GetLastError
0x1400085e0  mov     ebx, [rsp+88h+cchReturnLength]
0x1400085e4  add     rbx, rbx
0x1400085e7  call    cs:__imp_GetProcessHeap
0x1400085ed  mov     r8, rbx
0x1400085f0  mov     edx, 8
0x1400085f5  mov     rcx, rax
0x1400085f8  call    cs:__imp_VdsHeapAlloc
0x1400085fe  mov     rbp, rax
0x140008601  mov     [rsp+88h+var_60], rax
0x140008606  test    rax, rax
0x140008609  jz      loc_1400087B2
0x14000860f  lea     r9, [rsp+88h+var_64]; lpcchReturnLength
0x140008614  mov     r8d, [rsp+88h+cchReturnLength]; cchBufferLength
0x140008619  mov     rdx, rax; lpszVolumePathNames
0x14000861c  mov     rcx, rdi; lpszVolumeName
0x14000861f  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x140008625  test    eax, eax
0x140008627  jnz     short loc_140008666
0x140008629  call    cs:__imp_GetLastError
0x14000862f  mov     ebx, eax
0x140008631  mov     r9d, eax
0x140008634  lea     r8, aCvdsvolumeQuer_13; "CVdsVolume::QueryAccessPathsToVolume: G"...
0x14000863b  xor     edx, edx
0x14000863d  mov     ecx, 5Eh ; '^'
0x140008642  call    cs:__imp_VdsTraceEx
0x140008648  nop
0x140008649  lea     rcx, [rsp+88h+var_58]
0x14000864e  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140008654  nop
0x140008655  lea     rcx, [rsp+88h+var_60]
0x14000865a  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x14000865f  mov     eax, ebx
0x140008661  jmp     loc_1400087CD
0x140008666  cmp     word ptr [rbp+0], 0
0x14000866b  jz      loc_1400087FC
0x140008671  mov     ebx, r13d
0x140008674  mov     rcx, rbp
0x140008677  nop     word ptr [rax+rax+00000000h]
0x140008680  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140008687  nop     word ptr [rax+rax+00000000h]
0x140008690  lea     rax, [rax+1]
0x140008694  cmp     word ptr [rcx+rax*2], 0
0x140008699  jnz     short loc_140008690
0x14000869b  lea     rcx, [rcx+rax*2]
0x14000869f  add     rcx, 2
0x1400086a3  inc     ebx
0x1400086a5  cmp     word ptr [rcx], 0
0x1400086a9  jnz     short loc_140008680
0x1400086ab  test    ebx, ebx
0x1400086ad  jz      loc_1400087FC
0x1400086b3  mov     edi, ebx
0x1400086b5  shl     rdi, 3
0x1400086b9  mov     rcx, rdi; cb
0x1400086bc  call    cs:__imp_CoTaskMemAlloc
0x1400086c2  mov     [r15], rax
0x1400086c5  test    rax, rax
0x1400086c8  jnz     short loc_1400086F4
0x1400086ca  lea     rcx, [rsp+88h+var_58]
0x1400086cf  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400086d5  nop
0x1400086d6  call    cs:__imp_GetProcessHeap
0x1400086dc  mov     r8, rbp
0x1400086df  xor     edx, edx
0x1400086e1  mov     rcx, rax
0x1400086e4  call    cs:__imp_VdsHeapFree
0x1400086ea  mov     [rsp+88h+var_60], r13
0x1400086ef  jmp     loc_1400087C8
0x1400086f4  mov     r8, rdi; Size
0x1400086f7  xor     edx, edx; Val
0x1400086f9  mov     rcx, rax; void *
0x1400086fc  call    memset_0
0x140008701  mov     edi, r13d
0x140008704  cmp     edi, ebx
0x140008706  jnb     loc_1400087DE
0x14000870c  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x140008713  inc     rsi
0x140008716  cmp     word ptr [rbp+rsi*2+0], 0
0x14000871c  jnz     short loc_140008713
0x14000871e  lea     rcx, ds:2[rsi*2]; cb
0x140008726  call    cs:__imp_CoTaskMemAlloc
0x14000872c  mov     ecx, edi
0x14000872e  lea     r14, ds:0[rcx*8]
0x140008736  mov     rcx, [r15]
0x140008739  mov     [r14+rcx], rax
0x14000873d  mov     rax, [r15]
0x140008740  mov     rcx, [r14+rax]; unsigned __int16 *
0x140008744  test    rcx, rcx
0x140008747  jz      short loc_140008771
0x140008749  lea     rdx, [rsi+1]; unsigned __int64
0x14000874d  mov     r9, rsi; unsigned __int64
0x140008750  mov     r8, rbp; unsigned __int16 *
0x140008753  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140008758  mov     r11, [r15]
0x14000875b  mov     rcx, [r14+r11]
0x14000875f  mov     [rcx+rsi*2], r13w
0x140008764  lea     rbp, [rbp+rsi*2+0]
0x140008769  add     rbp, 2
0x14000876d  inc     edi
0x14000876f  jmp     short loc_140008704
0x140008771  mov     ebx, r13d
0x140008774  test    edi, edi
0x140008776  jz      short loc_1400087A1
0x140008778  mov     eax, ebx
0x14000877a  lea     rsi, ds:0[rax*8]
0x140008782  mov     rax, [r15]
0x140008785  mov     rcx, [rsi+rax]; pv
0x140008789  test    rcx, rcx
0x14000878c  jz      short loc_14000879B
0x14000878e  call    cs:__imp_CoTaskMemFree
0x140008794  mov     rax, [r15]
0x140008797  mov     [rsi+rax], r13
0x14000879b  inc     ebx
0x14000879d  cmp     ebx, edi
0x14000879f  jb      short loc_140008778
0x1400087a1  mov     rcx, [r15]; pv
0x1400087a4  test    rcx, rcx
0x1400087a7  jz      short loc_1400087B2
0x1400087a9  call    cs:__imp_CoTaskMemFree
0x1400087af  mov     [r15], r13
0x1400087b2  lea     rcx, [rsp+88h+var_58]
0x1400087b7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400087bd  nop
0x1400087be  lea     rcx, [rsp+88h+var_60]
0x1400087c3  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x1400087c8  mov     eax, 8
0x1400087cd  add     rsp, 48h
0x1400087d1  pop     r15
0x1400087d3  pop     r14
0x1400087d5  pop     r13
0x1400087d7  pop     r12
0x1400087d9  pop     rdi
0x1400087da  pop     rsi
0x1400087db  pop     rbp
0x1400087dc  pop     rbx
0x1400087dd  retn
0x1400087de  mov     [r12], ebx
0x1400087e2  lea     rcx, [rsp+88h+var_58]
0x1400087e7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400087ed  nop
0x1400087ee  lea     rcx, [rsp+88h+var_60]
0x1400087f3  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x1400087f8  xor     eax, eax
0x1400087fa  jmp     short loc_1400087CD
0x1400087fc  lea     rcx, [rsp+88h+var_58]
0x140008801  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140008807  nop
0x140008808  call    cs:__imp_GetProcessHeap
0x14000880e  mov     r8, rbp
0x140008811  xor     edx, edx
0x140008813  mov     rcx, rax
0x140008816  call    cs:__imp_VdsHeapFree
0x14000881c  mov     [rsp+88h+var_60], r13
0x140008821  xor     eax, eax
0x140008823  jmp     short loc_1400087CD
```
