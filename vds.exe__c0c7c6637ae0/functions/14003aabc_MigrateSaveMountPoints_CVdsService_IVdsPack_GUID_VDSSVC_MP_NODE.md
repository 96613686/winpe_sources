# MigrateSaveMountPoints(CVdsService *,IVdsPack *,_GUID,_VDSSVC_MP_NODE * *)

- ea: `0x14003aabc`
- end: `0x14003b0d4`
- name: `?MigrateSaveMountPoints@@YAJPEAVCVdsService@@PEAUIVdsPack@@U_GUID@@PEAPEAU_VDSSVC_MP_NODE@@@Z`
- size: `1560`
- prototype: `__int64 __fastcall(struct CVdsService *, struct IVdsPack *, struct _GUID *__struct_ptr, struct _VDSSVC_MP_NODE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x140017250`

## callees

- `0x14003aabc`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003af1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003af32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003b026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003b071`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003b08c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003af1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003af32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003b026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003b071`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003b08c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ac91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ae8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003b035`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ac91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ae8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003b035`
- `vdsutil!IsDriveLetter` at `0x14003aed3`
- `vdsutil!IsDriveLetter` at `0x14003aed3`
- `vdsutil!VdsHeapAlloc` at `0x14003aea1`
- `vdsutil!VdsHeapAlloc` at `0x14003aea1`
- `vdsutil!VdsHeapFree` at `0x14003aca0`
- `vdsutil!VdsHeapFree` at `0x14003b044`
- `vdsutil!VdsHeapFree` at `0x14003aca0`
- `vdsutil!VdsHeapFree` at `0x14003b044`
- `vdsutil!VdsTraceEx` at `0x14003abc9`
- `vdsutil!VdsTraceEx` at `0x14003af6d`
- `vdsutil!VdsTraceEx` at `0x14003af9e`
- `vdsutil!VdsTraceEx` at `0x14003afc9`
- `vdsutil!VdsTraceEx` at `0x14003aff7`
- `vdsutil!VdsTraceEx` at `0x14003abc9`
- `vdsutil!VdsTraceEx` at `0x14003af6d`
- `vdsutil!VdsTraceEx` at `0x14003af9e`
- `vdsutil!VdsTraceEx` at `0x14003afc9`
- `vdsutil!VdsTraceEx` at `0x14003aff7`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003ab58`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003ab58`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003b0a4`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003b0a4`

## string_xrefs

- `0x14003ab4a`: `CVdsService::MigrateSaveMountPoints()`
- `0x14003afeb`: `CVdsService::MigrateSaveMountPoints, 1`
- `0x14003abba`: `CVdsService::MigrateSaveMountPoints, 2, hr=%lX`
- `0x14003abf6`: `CVdsService::MigrateSaveMountPoints, 3, hr=%lX`
- `0x14003ac59`: `CVdsService::MigrateSaveMountPoints, 4, hr=%lX`
- `0x14003ac7f`: `CVdsService::MigrateSaveMountPoints, 5, hr=%lX`
- `0x14003afda`: `CVdsService::MigrateSaveMountPoints, 6, hr=%lX`
- `0x14003afd1`: `CVdsService::MigrateSaveMountPoints, 7, hr=%lX`
- `0x14003afba`: `CVdsService::MigrateSaveMountPoints, 8, hr=%lX`
- `0x14003afb1`: `CVdsService::MigrateSaveMountPoints, 9, hr=%lX, name=%S`
- `0x14003afa8`: `CVdsService::MigrateSaveMountPoints, 10, hr=%lX, name=%S`
- `0x14003af78`: `CVdsService::MigrateSaveMountPoints, 11, hr=%lX, name=%S`
- `0x14003af61`: `CVdsService::MigrateSaveMountPoints, 12, name=%S`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MigrateSaveMountPoints(
        struct CVdsService *a1,
        struct IVdsPack *a2,
        struct _GUID *a3,
        struct _VDSSVC_MP_NODE **a4)
{
  struct CVdsService *v6; // r14
  __int128 v7; // xmm6
  unsigned int v8; // edi
  int v9; // eax
  int v10; // ebx
  const char *v11; // r8
  int v12; // r12d
  _QWORD *v13; // r15
  HANDLE ProcessHeap; // rax
  __int64 i; // rdx
  __int64 v16; // rax
  __int64 j; // rsi
  unsigned int v18; // edx
  __int16 *v19; // r14
  HANDLE v20; // rax
  struct _VDSSVC_MP_NODE *v21; // rax
  struct _VDSSVC_MP_NODE *v22; // rbx
  char v23; // al
  __int16 v24; // cx
  __int64 v25; // rbx
  void *v26; // rcx
  const wchar_t *v27; // r9
  const char *v28; // r8
  const wchar_t *v29; // rcx
  HANDLE v30; // rax
  void *v31; // rcx
  char *v32; // rax
  unsigned int v33; // esi
  unsigned int v34; // edx
  __int64 v36; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+40h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+70h] [rbp-98h] BYREF
  __int64 v44; // [rsp+78h] [rbp-90h] BYREF
  _QWORD *v45; // [rsp+80h] [rbp-88h] BYREF
  int v46; // [rsp+88h] [rbp-80h] BYREF
  struct CVdsService *v47; // [rsp+90h] [rbp-78h]
  __int128 v48; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v49[16]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v50; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v51; // [rsp+C8h] [rbp-40h]
  __int128 v52; // [rsp+D8h] [rbp-30h]
  const wchar_t *v53; // [rsp+E8h] [rbp-20h]

  v6 = a1;
  v47 = a1;
  v7 = (__int128)*a3;
  v8 = 0;
  v41 = 0;
  v45 = 0;
  v44 = 0;
  v37 = 0;
  v40 = 0;
  v42 = 0;
  v43 = 0;
  v46 = 0;
  LODWORD(v39) = 0;
  LODWORD(v36) = 0;
  pv = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v49, 0x5Eu, "CVdsService::MigrateSaveMountPoints()");
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  if ( v6 && a2 && a4 )
  {
    *a4 = 0;
    v48 = v7;
    v9 = (*(__int64 (__fastcall **)(struct CVdsService *, __int128 *, __int64, __int64 *))(*(_QWORD *)v6 + 72LL))(
           v6,
           &v48,
           13,
           &v40);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v40)(v40, &IID_IVdsDisk, &v41);
      v10 = v9;
      if ( v9 >= 0 )
      {
        if ( v40 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
          v40 = 0;
        }
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD **, __int64 *))(*(_QWORD *)v41 + 48LL))(v41, &v45, &v39);
        if ( v41 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
          v41 = 0;
        }
        if ( v10 < 0 )
        {
          VdsTraceEx(95, 0, "CVdsService::MigrateSaveMountPoints, 4, hr=%lX", (unsigned int)v10);
          goto LABEL_74;
        }
        v9 = ((__int64 (__fastcall *)(struct IVdsPack *, __int64 *))a2->lpVtbl->QueryVolumes)(a2, &v44);
        v10 = v9;
        if ( v9 >= 0 )
        {
          v12 = 0;
          v13 = 0;
          while ( 1 )
          {
LABEL_19:
            ProcessHeap = GetProcessHeap();
            VdsHeapFree(ProcessHeap, 0, v53);
            v53 = 0;
            v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v44 + 24LL))(
                   v44,
                   1,
                   &v37,
                   &v46);
            v10 = v9;
            if ( v9 == 1 )
              goto LABEL_74;
            if ( v9 < 0 )
              break;
            v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v37)(v37, &IID_IVdsVolume, &v42);
            if ( v37 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
              v37 = 0;
            }
            if ( v10 < 0 )
            {
              VdsTraceEx(95, 0, "CVdsService::MigrateSaveMountPoints, 7, hr=%lX", (unsigned int)v10);
LABEL_66:
              v8 = v10;
              goto LABEL_74;
            }
            v50 = 0;
            v51 = 0;
            v52 = 0;
            v53 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v42 + 24LL))(v42, &v50);
            if ( v42 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
              v42 = 0;
            }
            if ( v10 < 0 )
            {
              VdsTraceEx(95, 0, "CVdsService::MigrateSaveMountPoints, 8, hr=%lX", (unsigned int)v10);
              goto LABEL_66;
            }
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              if ( (unsigned int)i >= (unsigned int)v39 )
                goto LABEL_19;
              if ( LODWORD(v45[10 * i + 2]) == 2 )
              {
                v16 = v45[10 * i + 5] - v50;
                if ( !v16 )
                  v16 = v45[10 * i + 6] - *((_QWORD *)&v50 + 1);
                if ( !v16 )
                  break;
              }
            }
            v48 = v50;
            v10 = (*(__int64 (__fastcall **)(struct CVdsService *, __int128 *, __int64, __int64 *))(*(_QWORD *)v6 + 72LL))(
                    v6,
                    &v48,
                    11,
                    &v37);
            if ( v10 < 0 )
            {
              v28 = "CVdsService::MigrateSaveMountPoints, 9, hr=%lX, name=%S";
              goto LABEL_63;
            }
            v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v37)(v37, &IID_IVdsVolumeMF, &v43);
            if ( v37 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
              v37 = 0;
            }
            if ( v10 < 0 )
            {
              v28 = "CVdsService::MigrateSaveMountPoints, 10, hr=%lX, name=%S";
              goto LABEL_63;
            }
            v10 = (*(__int64 (__fastcall **)(__int64, LPVOID *, __int64 *))(*(_QWORD *)v43 + 48LL))(v43, &pv, &v36);
            if ( v43 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
              v43 = 0;
            }
            if ( v10 < 0 )
            {
              v28 = "CVdsService::MigrateSaveMountPoints, 11, hr=%lX, name=%S";
LABEL_63:
              v29 = L"UNKNOWN";
              if ( v53 )
                v29 = v53;
              VdsTraceEx(95, 0, v28, (unsigned int)v10, v29);
              goto LABEL_66;
            }
            if ( v10 != 1 )
            {
              for ( j = 0; ; j = (unsigned int)(j + 1) )
              {
                v18 = v36;
                if ( (unsigned int)j >= (unsigned int)v36 )
                  break;
                v19 = (__int16 *)*((_QWORD *)pv + j);
                v20 = GetProcessHeap();
                v21 = (struct _VDSSVC_MP_NODE *)VdsHeapAlloc(v20, 8, 32);
                v22 = v21;
                if ( ++v12 == 1 )
                  *a4 = v21;
                if ( v13 )
                  *v13 = v21;
                if ( !v21 )
                {
                  v10 = -2147024882;
                  v27 = L"UNKNOWN";
                  if ( v53 )
                    v27 = v53;
                  VdsTraceEx(95, 0, "CVdsService::MigrateSaveMountPoints, 12, name=%S", v27);
                  goto LABEL_74;
                }
                v13 = v21;
                if ( v19 && (unsigned int)IsDriveLetter(v19) )
                {
                  *(_OWORD *)((char *)v22 + 8) = v50;
                  v23 = 1;
                  v24 = *v19;
                }
                else
                {
                  *(_OWORD *)((char *)v22 + 8) = v50;
                  v23 = 0;
                  v24 = 0;
                }
                *((_WORD *)v22 + 12) = v24;
                *((_BYTE *)v22 + 26) = v23;
              }
              v25 = 0;
              if ( (_DWORD)v36 )
              {
                do
                {
                  v26 = (void *)*((_QWORD *)pv + v25);
                  if ( v26 )
                  {
                    CoTaskMemFree(v26);
                    v18 = v36;
                  }
                  v25 = (unsigned int)(v25 + 1);
                }
                while ( (unsigned int)v25 < v18 );
              }
              CoTaskMemFree(pv);
              pv = 0;
              v6 = v47;
            }
          }
          v11 = "CVdsService::MigrateSaveMountPoints, 6, hr=%lX";
        }
        else
        {
          v11 = "CVdsService::MigrateSaveMountPoints, 5, hr=%lX";
        }
      }
      else
      {
        v11 = "CVdsService::MigrateSaveMountPoints, 3, hr=%lX";
      }
    }
    else
    {
      v11 = "CVdsService::MigrateSaveMountPoints, 2, hr=%lX";
    }
    VdsTraceEx(95, 0, v11, (unsigned int)v9);
  }
  else
  {
    v10 = -2147024809;
    VdsTraceEx(95, 0, "CVdsService::MigrateSaveMountPoints, 1");
  }
LABEL_74:
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v45 )
  {
    CoTaskMemFree(v45);
    v45 = 0;
  }
  v30 = GetProcessHeap();
  VdsHeapFree(v30, 0, v53);
  v53 = 0;
  v31 = pv;
  if ( pv )
  {
    v32 = *(char **)pv;
    v33 = 0;
    v34 = v36;
    if ( (_DWORD)v36 )
    {
      do
      {
        if ( v32 )
        {
          CoTaskMemFree(v32);
          v32 = 0;
          v34 = v36;
        }
        v32 += 2;
        ++v33;
      }
      while ( v33 < v34 );
      v31 = pv;
    }
    CoTaskMemFree(v31);
    pv = 0;
  }
  if ( v10 < 0 )
    v8 = v10;
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v49);
  return v8;
}

```

## disassembly

```asm
0x14003aabc  mov     rax, rsp
0x14003aabf  push    rbp
0x14003aac0  push    rbx
0x14003aac1  push    rsi
0x14003aac2  push    rdi
0x14003aac3  push    r12
0x14003aac5  push    r13
0x14003aac7  push    r14
0x14003aac9  push    r15
0x14003aacb  lea     rbp, [rax-48h]
0x14003aacf  sub     rsp, 108h
0x14003aad6  movaps  xmmword ptr [rax-58h], xmm6
0x14003aada  mov     rax, cs:__security_cookie
0x14003aae1  xor     rax, rsp
0x14003aae4  mov     qword ptr [rbp+40h+var_58], rax
0x14003aae8  mov     r13, r9
0x14003aaeb  mov     rsi, rdx
0x14003aaee  mov     r14, rcx
0x14003aaf1  mov     [rbp+40h+var_B8], rcx
0x14003aaf5  movaps  xmm6, xmmword ptr [r8]
0x14003aaf9  xor     r15d, r15d
0x14003aafc  mov     edi, r15d
0x14003aaff  mov     [rsp+140h+var_E8], r15
0x14003ab04  mov     [rsp+140h+var_C8], r15
0x14003ab09  mov     [rsp+140h+var_D0], r15
0x14003ab0e  mov     [rsp+140h+var_108], r15
0x14003ab13  mov     [rsp+140h+var_F0], r15
0x14003ab18  mov     [rsp+140h+var_E0], r15
0x14003ab1d  mov     [rsp+140h+var_D8], r15
0x14003ab22  mov     [rbp+40h+var_C0], r15d
0x14003ab26  mov     dword ptr [rsp+140h+var_F8], r15d
0x14003ab2b  mov     dword ptr [rsp+140h+var_110], r15d
0x14003ab30  mov     [rsp+140h+pv], r15
0x14003ab35  xorps   xmm0, xmm0
0x14003ab38  xor     eax, eax
0x14003ab3a  movups  [rbp+40h+var_90], xmm0
0x14003ab3e  movups  [rbp+40h+var_80], xmm0
0x14003ab42  movups  [rbp+40h+var_70], xmm0
0x14003ab46  mov     [rbp+40h+var_60], rax
0x14003ab4a  lea     r8, aCvdsserviceMig_5; "CVdsService::MigrateSaveMountPoints()"
0x14003ab51  lea     edx, [rax+5Eh]
0x14003ab54  lea     rcx, [rbp+40h+var_A0]
0x14003ab58  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003ab5e  nop
0x14003ab5f  xorps   xmm0, xmm0
0x14003ab62  xor     eax, eax
0x14003ab64  movups  [rbp+40h+var_90], xmm0
0x14003ab68  movups  [rbp+40h+var_80], xmm0
0x14003ab6c  movups  [rbp+40h+var_70], xmm0
0x14003ab70  mov     [rbp+40h+var_60], rax
0x14003ab74  test    r14, r14
0x14003ab77  jz      loc_14003AFE6
0x14003ab7d  test    rsi, rsi
0x14003ab80  jz      loc_14003AFE6
0x14003ab86  test    r13, r13
0x14003ab89  jz      loc_14003AFE6
0x14003ab8f  mov     [r13+0], r15
0x14003ab93  movdqa  [rbp+40h+var_B0], xmm6
0x14003ab98  mov     rax, [r14]
0x14003ab9b  lea     r9, [rsp+140h+var_F0]
0x14003aba0  lea     r8d, [r15+0Dh]
0x14003aba4  lea     rdx, [rbp+40h+var_B0]
0x14003aba8  mov     rcx, r14
0x14003abab  mov     rax, [rax+48h]
0x14003abaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003abb4  mov     ebx, eax
0x14003abb6  test    eax, eax
0x14003abb8  jns     short loc_14003ABD4
0x14003abba  lea     r8, aCvdsserviceMig_6; "CVdsService::MigrateSaveMountPoints, 2,"...
0x14003abc1  mov     r9d, eax
0x14003abc4  xor     edx, edx
0x14003abc6  lea     ecx, [rdx+5Fh]
0x14003abc9  call    cs:__imp_VdsTraceEx
0x14003abcf  jmp     loc_14003AFFD
0x14003abd4  mov     rcx, [rsp+140h+var_F0]
0x14003abd9  mov     rax, [rcx]
0x14003abdc  lea     r8, [rsp+140h+var_E8]
0x14003abe1  lea     rdx, IID_IVdsDisk
0x14003abe8  mov     rax, [rax]
0x14003abeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003abf0  mov     ebx, eax
0x14003abf2  test    eax, eax
0x14003abf4  jns     short loc_14003ABFF
0x14003abf6  lea     r8, aCvdsserviceMig_10; "CVdsService::MigrateSaveMountPoints, 3,"...
0x14003abfd  jmp     short loc_14003ABC1
0x14003abff  mov     rcx, [rsp+140h+var_F0]
0x14003ac04  test    rcx, rcx
0x14003ac07  jz      short loc_14003AC1A
0x14003ac09  mov     rax, [rcx]
0x14003ac0c  mov     rax, [rax+10h]
0x14003ac10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ac15  mov     [rsp+140h+var_F0], r15
0x14003ac1a  mov     rcx, [rsp+140h+var_E8]
0x14003ac1f  mov     rax, [rcx]
0x14003ac22  lea     r8, [rsp+140h+var_F8]
0x14003ac27  lea     rdx, [rsp+140h+var_C8]
0x14003ac2c  mov     rax, [rax+30h]
0x14003ac30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ac35  mov     ebx, eax
0x14003ac37  mov     rcx, [rsp+140h+var_E8]
0x14003ac3c  test    rcx, rcx
0x14003ac3f  jz      short loc_14003AC52
0x14003ac41  mov     rax, [rcx]
0x14003ac44  mov     rax, [rax+10h]
0x14003ac48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ac4d  mov     [rsp+140h+var_E8], r15
0x14003ac52  test    ebx, ebx
0x14003ac54  jns     short loc_14003AC65
0x14003ac56  mov     r9d, ebx
0x14003ac59  lea     r8, aCvdsserviceMig_7; "CVdsService::MigrateSaveMountPoints, 4,"...
0x14003ac60  jmp     loc_14003ABC4
0x14003ac65  mov     rax, [rsi]
0x14003ac68  lea     rdx, [rsp+140h+var_D0]
0x14003ac6d  mov     rcx, rsi
0x14003ac70  mov     rax, [rax+28h]
0x14003ac74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ac79  mov     ebx, eax
0x14003ac7b  test    eax, eax
0x14003ac7d  jns     short loc_14003AC8B
0x14003ac7f  lea     r8, aCvdsserviceMig_4; "CVdsService::MigrateSaveMountPoints, 5,"...
0x14003ac86  jmp     loc_14003ABC1
0x14003ac8b  xor     r12d, r12d
0x14003ac8e  xor     r15d, r15d
0x14003ac91  call    cs:__imp_GetProcessHeap
0x14003ac97  mov     rcx, rax
0x14003ac9a  mov     r8, [rbp+40h+var_60]
0x14003ac9e  xor     edx, edx
0x14003aca0  call    cs:__imp_VdsHeapFree
0x14003aca6  mov     [rbp+40h+var_60], 0
0x14003acae  mov     rcx, [rsp+140h+var_D0]
0x14003acb3  mov     rax, [rcx]
0x14003acb6  lea     r9, [rbp+40h+var_C0]
0x14003acba  lea     r8, [rsp+140h+var_108]
0x14003acbf  mov     edx, 1
0x14003acc4  mov     rax, [rax+18h]
0x14003acc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003accd  mov     ebx, eax
0x14003accf  cmp     eax, 1
0x14003acd2  jz      loc_14003AFFD
0x14003acd8  test    eax, eax
0x14003acda  js      loc_14003AFDA
0x14003ace0  mov     rcx, [rsp+140h+var_108]
0x14003ace5  mov     rax, [rcx]
0x14003ace8  lea     r8, [rsp+140h+var_E0]
0x14003aced  lea     rdx, IID_IVdsVolume
0x14003acf4  mov     rax, [rax]
0x14003acf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003acfc  mov     ebx, eax
0x14003acfe  mov     rcx, [rsp+140h+var_108]
0x14003ad03  test    rcx, rcx
0x14003ad06  jz      short loc_14003AD1D
0x14003ad08  mov     rax, [rcx]
0x14003ad0b  mov     rax, [rax+10h]
0x14003ad0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ad14  mov     [rsp+140h+var_108], 0
0x14003ad1d  test    ebx, ebx
0x14003ad1f  js      loc_14003AFD1
0x14003ad25  xorps   xmm0, xmm0
0x14003ad28  xor     eax, eax
0x14003ad2a  movups  [rbp+40h+var_90], xmm0
0x14003ad2e  movups  [rbp+40h+var_80], xmm0
0x14003ad32  movups  [rbp+40h+var_70], xmm0
0x14003ad36  mov     [rbp+40h+var_60], rax
0x14003ad3a  mov     rcx, [rsp+140h+var_E0]
0x14003ad3f  mov     rax, [rcx]
0x14003ad42  lea     rdx, [rbp+40h+var_90]
0x14003ad46  mov     rax, [rax+18h]
0x14003ad4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ad4f  mov     ebx, eax
0x14003ad51  mov     rcx, [rsp+140h+var_E0]
0x14003ad56  test    rcx, rcx
0x14003ad59  jz      short loc_14003AD70
0x14003ad5b  mov     rax, [rcx]
0x14003ad5e  mov     rax, [rax+10h]
0x14003ad62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ad67  mov     [rsp+140h+var_E0], 0
0x14003ad70  test    ebx, ebx
0x14003ad72  js      loc_14003AFBA
0x14003ad78  xor     edx, edx
0x14003ad7a  mov     r8, [rsp+140h+var_C8]
0x14003ad7f  cmp     edx, dword ptr [rsp+140h+var_F8]
0x14003ad83  jnb     loc_14003AC91
0x14003ad89  lea     rcx, [rdx+rdx*4]
0x14003ad8d  add     rcx, rcx
0x14003ad90  cmp     dword ptr [r8+rcx*8+10h], 2
0x14003ad96  jnz     short loc_14003ADB1
0x14003ad98  mov     rax, [r8+rcx*8+28h]
0x14003ad9d  sub     rax, qword ptr [rbp+40h+var_90]
0x14003ada1  jnz     short loc_14003ADAC
0x14003ada3  mov     rax, [r8+rcx*8+30h]
0x14003ada8  sub     rax, qword ptr [rbp+40h+var_90+8]
0x14003adac  test    rax, rax
0x14003adaf  jz      short loc_14003ADB5
0x14003adb1  inc     edx
0x14003adb3  jmp     short loc_14003AD7F
0x14003adb5  movups  xmm0, [rbp+40h+var_90]
0x14003adb9  movdqu  [rbp+40h+var_B0], xmm0
0x14003adbe  mov     rax, [r14]
0x14003adc1  lea     r9, [rsp+140h+var_108]
0x14003adc6  mov     r8d, 0Bh
0x14003adcc  lea     rdx, [rbp+40h+var_B0]
0x14003add0  mov     rcx, r14
0x14003add3  mov     rax, [rax+48h]
0x14003add7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003addc  mov     ebx, eax
0x14003adde  test    eax, eax
0x14003ade0  js      loc_14003AFB1
0x14003ade6  mov     rcx, [rsp+140h+var_108]
0x14003adeb  mov     rax, [rcx]
0x14003adee  lea     r8, [rsp+140h+var_D8]
0x14003adf3  lea     rdx, IID_IVdsVolumeMF
0x14003adfa  mov     rax, [rax]
0x14003adfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ae02  mov     ebx, eax
0x14003ae04  mov     rcx, [rsp+140h+var_108]
0x14003ae09  test    rcx, rcx
0x14003ae0c  jz      short loc_14003AE23
0x14003ae0e  mov     rax, [rcx]
0x14003ae11  mov     rax, [rax+10h]
0x14003ae15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ae1a  mov     [rsp+140h+var_108], 0
0x14003ae23  test    ebx, ebx
0x14003ae25  js      loc_14003AFA8
0x14003ae2b  mov     rcx, [rsp+140h+var_D8]
0x14003ae30  mov     rax, [rcx]
0x14003ae33  lea     r8, [rsp+140h+var_110]
0x14003ae38  lea     rdx, [rsp+140h+pv]
0x14003ae3d  mov     rax, [rax+30h]
0x14003ae41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ae46  mov     ebx, eax
0x14003ae48  mov     rcx, [rsp+140h+var_D8]
0x14003ae4d  test    rcx, rcx
0x14003ae50  jz      short loc_14003AE67
0x14003ae52  mov     rax, [rcx]
0x14003ae55  mov     rax, [rax+10h]
0x14003ae59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ae5e  mov     [rsp+140h+var_D8], 0
0x14003ae67  test    ebx, ebx
0x14003ae69  js      loc_14003AF78
0x14003ae6f  cmp     ebx, 1
0x14003ae72  jz      loc_14003AC91
0x14003ae78  xor     esi, esi
0x14003ae7a  mov     edx, dword ptr [rsp+140h+var_110]
0x14003ae7e  cmp     esi, edx
0x14003ae80  jnb     loc_14003AF09
0x14003ae86  mov     rax, [rsp+140h+pv]
0x14003ae8b  mov     r14, [rax+rsi*8]
0x14003ae8f  call    cs:__imp_GetProcessHeap
0x14003ae95  mov     rcx, rax
0x14003ae98  mov     edx, 8
0x14003ae9d  lea     r8d, [rdx+18h]
0x14003aea1  call    cs:__imp_VdsHeapAlloc
0x14003aea7  mov     rbx, rax
0x14003aeaa  inc     r12d
0x14003aead  cmp     r12d, 1
0x14003aeb1  jnz     short loc_14003AEB7
0x14003aeb3  mov     [r13+0], rax
0x14003aeb7  test    r15, r15
0x14003aeba  jz      short loc_14003AEBF
0x14003aebc  mov     [r15], rbx
0x14003aebf  test    rbx, rbx
0x14003aec2  jz      loc_14003AF4A
0x14003aec8  mov     r15, rbx
0x14003aecb  test    r14, r14
0x14003aece  jz      short loc_14003AEEE
0x14003aed0  mov     rcx, r14
0x14003aed3  call    cs:__imp_IsDriveLetter
0x14003aed9  test    eax, eax
0x14003aedb  jz      short loc_14003AEEE
0x14003aedd  movups  xmm0, [rbp+40h+var_90]
0x14003aee1  movdqu  xmmword ptr [rbx+8], xmm0
0x14003aee6  mov     al, 1
0x14003aee8  movzx   ecx, word ptr [r14]
0x14003aeec  jmp     short loc_14003AEFB
0x14003aeee  movups  xmm0, [rbp+40h+var_90]
0x14003aef2  movdqu  xmmword ptr [rbx+8], xmm0
0x14003aef7  xor     al, al
0x14003aef9  xor     ecx, ecx
0x14003aefb  mov     [rbx+18h], cx
0x14003aeff  mov     [rbx+1Ah], al
0x14003af02  inc     esi
0x14003af04  jmp     loc_14003AE7A
0x14003af09  xor     ebx, ebx
0x14003af0b  test    edx, edx
0x14003af0d  jz      short loc_14003AF2D
0x14003af0f  mov     rax, [rsp+140h+pv]
0x14003af14  mov     rcx, [rax+rbx*8]; pv
0x14003af18  test    rcx, rcx
0x14003af1b  jz      short loc_14003AF27
0x14003af1d  call    cs:__imp_CoTaskMemFree
0x14003af23  mov     edx, dword ptr [rsp+140h+var_110]
0x14003af27  inc     ebx
0x14003af29  cmp     ebx, edx
0x14003af2b  jb      short loc_14003AF0F
0x14003af2d  mov     rcx, [rsp+140h+pv]; pv
0x14003af32  call    cs:__imp_CoTaskMemFree
0x14003af38  mov     [rsp+140h+pv], 0
0x14003af41  mov     r14, [rbp+40h+var_B8]
0x14003af45  jmp     loc_14003AC91
0x14003af4a  mov     ebx, 8007000Eh
  ... truncated ...
```
