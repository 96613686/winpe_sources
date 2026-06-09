# CVdsVolume::QueryFileSystemFormatSupportInternal(void *,_VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP * *,long *)

- ea: `0x140005b1c`
- end: `0x140005e29`
- name: `?QueryFileSystemFormatSupportInternal@CVdsVolume@@SAJPEAXPEAPEAU_VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP@@PEAJ@Z`
- size: `781`
- prototype: `__int64 __fastcall(void *, struct _VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP **, int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140004a80`
- `0x1400210b0`
- `0x14002b3f8`

## callees

- `0x140003710`
- `0x140004360`
- `0x140005b1c`
- `0x14000f930`
- `0x14002e123`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140005cc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140005cc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005c43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005c62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005df2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005c43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005c62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005c2a`
- `vdsutil!GetFMIFSGetDefaultFilesystemRoutine` at `0x140005bc0`
- `vdsutil!GetFMIFSGetDefaultFilesystemRoutine` at `0x140005bc0`
- `vdsutil!VdsHeapAlloc` at `0x140005c54`
- `vdsutil!VdsHeapAlloc` at `0x140005c54`
- `vdsutil!VdsHeapFree` at `0x140005c70`
- `vdsutil!VdsHeapFree` at `0x140005e00`
- `vdsutil!VdsHeapFree` at `0x140005c70`
- `vdsutil!VdsHeapFree` at `0x140005e00`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140005b68`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140005b68`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140005bab`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140005de6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140005bab`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140005de6`
- `vdsutil!VdsTraceW` at `0x140005be2`
- `vdsutil!VdsTraceW` at `0x140005c99`
- `vdsutil!VdsTraceW` at `0x140005be2`
- `vdsutil!VdsTraceW` at `0x140005c99`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsVolume::QueryFileSystemFormatSupportInternal(
        void *a1,
        struct _VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP **a2,
        int *a3)
{
  __int64 v5; // rbx
  struct _VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP *LastError; // rdi
  unsigned __int8 (__fastcall *FMIFSGetDefaultFilesystemRoutine)(__int128 *, __int64, unsigned int *); // rsi
  __int64 v8; // r14
  __int64 v9; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v11; // rdi
  HANDLE v12; // rax
  const wchar_t *v13; // rdx
  int v14; // eax
  unsigned int v15; // r8d
  __int64 v16; // rdx
  __int64 v17; // rcx
  struct _VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP *v18; // rcx
  HANDLE v19; // rax
  unsigned int v21; // [rsp+20h] [rbp-50h] BYREF
  __int64 v22; // [rsp+28h] [rbp-48h] BYREF
  int v23; // [rsp+30h] [rbp-40h]
  _BYTE v24[16]; // [rsp+38h] [rbp-38h] BYREF
  __int128 v25; // [rsp+48h] [rbp-28h] BYREF
  __int128 v26; // [rsp+58h] [rbp-18h]
  __int64 v27; // [rsp+68h] [rbp-8h]
  void *v28; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v29; // [rsp+A8h] [rbp+38h] BYREF

  v28 = a1;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v5 = 0;
  v29 = 0;
  v21 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v24, 0x5Eu, "CVdsVolume::QueryFileSystemFormatSupportInternal()");
  v25 = 0;
  v26 = 0;
  v27 = 0;
  *a2 = 0;
  *a3 = 0;
  v22 = 0;
  v23 = 0;
  LODWORD(LastError) = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v22);
  if ( (int)LastError >= 0 )
  {
    FMIFSGetDefaultFilesystemRoutine = (unsigned __int8 (__fastcall *)(__int128 *, __int64, unsigned int *))GetFMIFSGetDefaultFilesystemRoutine();
    if ( FMIFSGetDefaultFilesystemRoutine )
    {
      LOWORD(v25) = 1;
      *((_QWORD *)&v25 + 1) = &v28;
      v8 = 0;
      while ( !FMIFSGetDefaultFilesystemRoutine(&v25, v5, &v21) )
      {
        LODWORD(LastError) = GetLastError();
        if ( (_DWORD)LastError != 234 )
        {
          VdsTraceW(
            0,
            L"CVdsVolume::QueryFileSystemFormatSupportInternal: failed to get supported file systems: %ld",
            (unsigned int)LastError);
          goto LABEL_5;
        }
        v9 = 200LL * v21;
        ProcessHeap = GetProcessHeap();
        v11 = VdsHeapAlloc(ProcessHeap, 8, v9);
        if ( v8 )
        {
          v12 = GetProcessHeap();
          VdsHeapFree(v12, 0, v5);
        }
        v5 = v11;
        v29 = v11;
        if ( !v11 )
        {
          v13 = L"CVdsVolume::QueryFileSystemFormatSupportInternal, 2, hr=%lX";
LABEL_15:
          LODWORD(LastError) = -2147024882;
          VdsTraceW(0, v13);
          goto LABEL_30;
        }
        v8 = v11;
      }
      LastError = 0;
      v14 = v21;
      if ( v21 )
      {
        LastError = (struct _VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP *)CoTaskMemAlloc(204LL * v21);
        if ( !LastError )
        {
          v13 = L"CVdsVolume::QueryFileSystemFormatSupportInternal, 3, hr=%lX";
          goto LABEL_15;
        }
        memset_0(LastError, 0, 204LL * v21);
        v14 = v21;
      }
      v15 = 0;
      if ( v14 )
      {
        do
        {
          v16 = 200LL * v15;
          v17 = v15;
          if ( (*(_BYTE *)(v16 + v5) & 1) != 0 )
            LastError[v17].ulFlags |= 1u;
          v18 = &LastError[v17];
          if ( (*(_BYTE *)(v16 + v5) & 2) != 0 )
            v18->ulFlags |= 2u;
          if ( (*(_BYTE *)(v16 + v5) & 4) != 0 )
            v18->ulFlags |= 4u;
          v18->usRevision = *(_WORD *)(v16 + v5 + 2);
          v18->ulDefaultUnitAllocationSize = *(_DWORD *)(v16 + v5 + 4);
          *(_OWORD *)v18->rgulAllowedUnitAllocationSizes = *(_OWORD *)(v16 + v5 + 8);
          *(_OWORD *)&v18->rgulAllowedUnitAllocationSizes[4] = *(_OWORD *)(v16 + v5 + 24);
          *(_OWORD *)&v18->rgulAllowedUnitAllocationSizes[8] = *(_OWORD *)(v16 + v5 + 40);
          *(_OWORD *)&v18->rgulAllowedUnitAllocationSizes[12] = *(_OWORD *)(v16 + v5 + 56);
          *(_OWORD *)&v18->rgulAllowedUnitAllocationSizes[16] = *(_OWORD *)(v16 + v5 + 72);
          *(_OWORD *)&v18->rgulAllowedUnitAllocationSizes[20] = *(_OWORD *)(v16 + v5 + 88);
          *(_OWORD *)&v18->rgulAllowedUnitAllocationSizes[24] = *(_OWORD *)(v16 + v5 + 104);
          *(_OWORD *)&v18->rgulAllowedUnitAllocationSizes[28] = *(_OWORD *)(v16 + v5 + 120);
          *(_OWORD *)v18->wszName = *(_OWORD *)(v16 + v5 + 136);
          *(_OWORD *)&v18->wszName[8] = *(_OWORD *)(v16 + v5 + 152);
          *(_OWORD *)&v18->wszName[16] = *(_OWORD *)(v16 + v5 + 168);
          *(_OWORD *)&v18->wszName[24] = *(_OWORD *)(v16 + v5 + 184);
          ++v15;
          v14 = v21;
        }
        while ( v15 < v21 );
      }
      *a2 = LastError;
      *a3 = v14;
      LODWORD(LastError) = 0;
    }
    else
    {
      LastError = (struct _VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP *)GetLastError();
      VdsTraceW(
        0,
        L"CVdsVolume::QueryFileSystemFormatSupportInternal: failed to get GetDefaultFileSystem address: %ld",
        LastError);
LABEL_5:
      if ( (int)LastError > 0 )
        LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    }
LABEL_30:
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v22);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
    if ( v5 )
    {
      v19 = GetProcessHeap();
      VdsHeapFree(v19, 0, v5);
      v29 = 0;
    }
  }
  else
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v22);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(&v29);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140005b1c  mov     [rsp-28h+arg_10], rbx
0x140005b21  mov     [rsp-28h+arg_18], rsi
0x140005b26  mov     [rsp-28h+arg_0], rcx
0x140005b2b  push    rbp
0x140005b2c  push    rdi
0x140005b2d  push    r12
0x140005b2f  push    r14
0x140005b31  push    r15
0x140005b33  mov     rbp, rsp
0x140005b36  sub     rsp, 70h
0x140005b3a  mov     r15, r8
0x140005b3d  mov     r12, rdx
0x140005b40  xorps   xmm0, xmm0
0x140005b43  xor     eax, eax
0x140005b45  movups  [rbp+var_28], xmm0
0x140005b49  movups  [rbp+var_18], xmm0
0x140005b4d  mov     [rbp+var_8], rax
0x140005b51  xor     ebx, ebx
0x140005b53  mov     [rbp+arg_8], rbx
0x140005b57  mov     [rbp+var_50], ebx
0x140005b5a  lea     r8, aCvdsvolumeQuer_19; "CVdsVolume::QueryFileSystemFormatSuppor"...
0x140005b61  lea     edx, [rax+5Eh]
0x140005b64  lea     rcx, [rbp+var_38]
0x140005b68  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140005b6e  nop
0x140005b6f  xorps   xmm0, xmm0
0x140005b72  xor     eax, eax
0x140005b74  movups  [rbp+var_28], xmm0
0x140005b78  movups  [rbp+var_18], xmm0
0x140005b7c  mov     [rbp+var_8], rax
0x140005b80  mov     [r12], rax
0x140005b84  mov     [r15], eax
0x140005b87  mov     [rbp+var_48], rax
0x140005b8b  mov     [rbp+var_40], eax
0x140005b8e  lea     rcx, [rbp+var_48]; this
0x140005b92  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140005b97  mov     edi, eax
0x140005b99  test    eax, eax
0x140005b9b  jns     short loc_140005BC0
0x140005b9d  lea     rcx, [rbp+var_48]; this
0x140005ba1  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140005ba6  nop
0x140005ba7  lea     rcx, [rbp+var_38]
0x140005bab  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140005bb1  nop
0x140005bb2  lea     rcx, [rbp+arg_8]
0x140005bb6  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140005bbb  jmp     loc_140005E0E
0x140005bc0  call    cs:__imp_GetFMIFSGetDefaultFilesystemRoutine
0x140005bc6  mov     rsi, rax
0x140005bc9  test    rax, rax
0x140005bcc  jnz     short loc_140005BFE
0x140005bce  call    cs:__imp_GetLastError
0x140005bd4  mov     edi, eax
0x140005bd6  mov     r8d, eax
0x140005bd9  lea     rdx, aCvdsvolumeQuer_25; "CVdsVolume::QueryFileSystemFormatSuppor"...
0x140005be0  xor     ecx, ecx
0x140005be2  call    cs:__imp_VdsTraceW
0x140005be8  test    edi, edi
0x140005bea  jle     loc_140005DD8
0x140005bf0  movzx   edi, di
0x140005bf3  or      edi, 80070000h
0x140005bf9  jmp     loc_140005DD8
0x140005bfe  mov     word ptr [rbp+var_28], 1
0x140005c04  lea     rax, [rbp+arg_0]
0x140005c08  mov     qword ptr [rbp+var_28+8], rax
0x140005c0c  xor     r14d, r14d
0x140005c0f  lea     r8, [rbp+var_50]
0x140005c13  mov     rdx, rbx
0x140005c16  lea     rcx, [rbp+var_28]
0x140005c1a  mov     rax, rsi
0x140005c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c22  test    al, al
0x140005c24  jnz     loc_140005CB3
0x140005c2a  call    cs:__imp_GetLastError
0x140005c30  mov     edi, eax
0x140005c32  cmp     eax, 0EAh
0x140005c37  jnz     short loc_140005CA4
0x140005c39  mov     eax, [rbp+var_50]
0x140005c3c  imul    rdi, rax, 0C8h
0x140005c43  call    cs:__imp_GetProcessHeap
0x140005c49  mov     r8, rdi
0x140005c4c  mov     edx, 8
0x140005c51  mov     rcx, rax
0x140005c54  call    cs:__imp_VdsHeapAlloc
0x140005c5a  mov     rdi, rax
0x140005c5d  test    r14, r14
0x140005c60  jz      short loc_140005C76
0x140005c62  call    cs:__imp_GetProcessHeap
0x140005c68  mov     r8, rbx
0x140005c6b  xor     edx, edx
0x140005c6d  mov     rcx, rax
0x140005c70  call    cs:__imp_VdsHeapFree
0x140005c76  mov     rbx, rdi
0x140005c79  mov     [rbp+arg_8], rbx
0x140005c7d  test    rdi, rdi
0x140005c80  jz      short loc_140005C87
0x140005c82  mov     r14, rdi
0x140005c85  jmp     short loc_140005C0F
0x140005c87  lea     rdx, aCvdsvolumeQuer_24; "CVdsVolume::QueryFileSystemFormatSuppor"...
0x140005c8e  mov     r8d, 8007000Eh
0x140005c94  mov     edi, r8d
0x140005c97  xor     ecx, ecx
0x140005c99  call    cs:__imp_VdsTraceW
0x140005c9f  jmp     loc_140005DD8
0x140005ca4  mov     r8d, edi
0x140005ca7  lea     rdx, aCvdsvolumeQuer_40; "CVdsVolume::QueryFileSystemFormatSuppor"...
0x140005cae  jmp     loc_140005BE0
0x140005cb3  xor     edi, edi
0x140005cb5  mov     eax, [rbp+var_50]
0x140005cb8  test    eax, eax
0x140005cba  jz      short loc_140005CF1
0x140005cbc  imul    rcx, rax, 0CCh; cb
0x140005cc3  call    cs:__imp_CoTaskMemAlloc
0x140005cc9  mov     rdi, rax
0x140005ccc  test    rax, rax
0x140005ccf  jnz     short loc_140005CDA
0x140005cd1  lea     rdx, aCvdsvolumeQuer_38; "CVdsVolume::QueryFileSystemFormatSuppor"...
0x140005cd8  jmp     short loc_140005C8E
0x140005cda  mov     eax, [rbp+var_50]
0x140005cdd  imul    r8, rax, 0CCh; Size
0x140005ce4  xor     edx, edx; Val
0x140005ce6  mov     rcx, rdi; void *
0x140005ce9  call    memset_0
0x140005cee  mov     eax, [rbp+var_50]
0x140005cf1  xor     r8d, r8d
0x140005cf4  test    eax, eax
0x140005cf6  jz      loc_140005DCF
0x140005cfc  mov     eax, r8d
0x140005cff  imul    rdx, rax, 0C8h
0x140005d06  imul    rcx, rax, 0CCh
0x140005d0d  test    byte ptr [rdx+rbx], 1
0x140005d11  jz      short loc_140005D17
0x140005d13  or      dword ptr [rcx+rdi], 1
0x140005d17  add     rcx, rdi
0x140005d1a  test    byte ptr [rdx+rbx], 2
0x140005d1e  jz      short loc_140005D23
0x140005d20  or      dword ptr [rcx], 2
0x140005d23  test    byte ptr [rdx+rbx], 4
0x140005d27  jz      short loc_140005D2C
0x140005d29  or      dword ptr [rcx], 4
0x140005d2c  movzx   eax, word ptr [rdx+rbx+2]
0x140005d31  mov     [rcx+4], ax
0x140005d35  mov     eax, [rdx+rbx+4]
0x140005d39  mov     [rcx+8], eax
0x140005d3c  movups  xmm0, xmmword ptr [rdx+rbx+8]
0x140005d41  movups  xmmword ptr [rcx+0Ch], xmm0
0x140005d45  movups  xmm1, xmmword ptr [rdx+rbx+18h]
0x140005d4a  movups  xmmword ptr [rcx+1Ch], xmm1
0x140005d4e  movups  xmm0, xmmword ptr [rdx+rbx+28h]
0x140005d53  movups  xmmword ptr [rcx+2Ch], xmm0
0x140005d57  movups  xmm1, xmmword ptr [rdx+rbx+38h]
0x140005d5c  movups  xmmword ptr [rcx+3Ch], xmm1
0x140005d60  movups  xmm0, xmmword ptr [rdx+rbx+48h]
0x140005d65  movups  xmmword ptr [rcx+4Ch], xmm0
0x140005d69  movups  xmm1, xmmword ptr [rdx+rbx+58h]
0x140005d6e  movups  xmmword ptr [rcx+5Ch], xmm1
0x140005d72  movups  xmm0, xmmword ptr [rdx+rbx+68h]
0x140005d77  movups  xmmword ptr [rcx+6Ch], xmm0
0x140005d7b  movups  xmm1, xmmword ptr [rdx+rbx+78h]
0x140005d80  movups  xmmword ptr [rcx+7Ch], xmm1
0x140005d84  movups  xmm0, xmmword ptr [rdx+rbx+88h]
0x140005d8c  movups  xmmword ptr [rcx+8Ch], xmm0
0x140005d93  movups  xmm1, xmmword ptr [rdx+rbx+98h]
0x140005d9b  movups  xmmword ptr [rcx+9Ch], xmm1
0x140005da2  movups  xmm0, xmmword ptr [rdx+rbx+0A8h]
0x140005daa  movups  xmmword ptr [rcx+0ACh], xmm0
0x140005db1  movups  xmm1, xmmword ptr [rdx+rbx+0B8h]
0x140005db9  movups  xmmword ptr [rcx+0BCh], xmm1
0x140005dc0  inc     r8d
0x140005dc3  mov     eax, [rbp+var_50]
0x140005dc6  cmp     r8d, eax
0x140005dc9  jb      loc_140005CFC
0x140005dcf  mov     [r12], rdi
0x140005dd3  mov     [r15], eax
0x140005dd6  xor     edi, edi
0x140005dd8  lea     rcx, [rbp+var_48]; this
0x140005ddc  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140005de1  nop
0x140005de2  lea     rcx, [rbp+var_38]
0x140005de6  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140005dec  nop
0x140005ded  test    rbx, rbx
0x140005df0  jz      short loc_140005E0E
0x140005df2  call    cs:__imp_GetProcessHeap
0x140005df8  mov     r8, rbx
0x140005dfb  xor     edx, edx
0x140005dfd  mov     rcx, rax
0x140005e00  call    cs:__imp_VdsHeapFree
0x140005e06  mov     [rbp+arg_8], 0
0x140005e0e  mov     eax, edi
0x140005e10  lea     r11, [rsp+70h+var_s0]
0x140005e15  mov     rbx, [r11+40h]
0x140005e19  mov     rsi, [r11+48h]
0x140005e1d  mov     rsp, r11
0x140005e20  pop     r15
0x140005e22  pop     r14
0x140005e24  pop     r12
0x140005e26  pop     rdi
0x140005e27  pop     rbp
0x140005e28  retn
```
