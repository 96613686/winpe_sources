# CVdsDiskLun::RemountDiskVolumes(void)

- ea: `0x140029cf4`
- end: `0x14002a086`
- name: `?RemountDiskVolumes@CVdsDiskLun@@QEAAJXZ`
- size: `914`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140044cd0`
- `0x14004a370`

## callees

- `0x1400069e8`
- `0x140028fc8`
- `0x140029cf4`
- `0x14002e123`
- `0x140039f84`
- `0x14003a2dc`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029faf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029fd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029fe8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029ffb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029faf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029fd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029fe8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029ffb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029e25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002a024`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002a03d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029e25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002a024`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002a03d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140029f82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a014`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140029f82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a014`
- `vdsutil!OpenDevice` at `0x140029f2f`
- `vdsutil!OpenDevice` at `0x140029f2f`
- `vdsutil!VdsHeapFree` at `0x140029e33`
- `vdsutil!VdsHeapFree` at `0x14002a032`
- `vdsutil!VdsHeapFree` at `0x14002a04c`
- `vdsutil!VdsHeapFree` at `0x140029e33`
- `vdsutil!VdsHeapFree` at `0x14002a032`
- `vdsutil!VdsHeapFree` at `0x14002a04c`
- `vdsutil!VdsTraceEx` at `0x140029da5`
- `vdsutil!VdsTraceEx` at `0x140029da5`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140029d5f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140029d5f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002a05a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002a05a`
- `vdsutil!VdsTraceW` at `0x140029dbf`
- `vdsutil!VdsTraceW` at `0x140029df6`
- `vdsutil!VdsTraceW` at `0x140029f0b`
- `vdsutil!VdsTraceW` at `0x140029f68`
- `vdsutil!VdsTraceW` at `0x140029dbf`
- `vdsutil!VdsTraceW` at `0x140029df6`
- `vdsutil!VdsTraceW` at `0x140029f0b`
- `vdsutil!VdsTraceW` at `0x140029f68`

## string_xrefs

- `0x140029f5c`: `CVdsDiskLun::RemountDiskVolumes, 4, %lX, name=%s`
- `0x140029d4f`: `CVdsDiskLun::RemountDiskVolumes`
- `0x140029d9a`: `CVdsDiskLun::RemountDiskVolumes, 1, hr=%lX`
- `0x140029db6`: `CVdsDiskLun::RemountDiskVolumes, 1.5`
- `0x140029ded`: `CVdsDiskLun::RemountDiskVolumes, 2, hr=%lX`
- `0x140029eff`: `CVdsDiskLun::RemountDiskVolumes, 3, ObjectId=%s, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsDiskLun::RemountDiskVolumes(CVdsDiskLun *this)
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
  unsigned int v12; // ecx
  unsigned __int16 *v13; // rbx
  HANDLE v14; // rax
  HANDLE v15; // rax
  __int64 v17; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+28h] [rbp-D8h]
  __int64 v19; // [rsp+30h] [rbp-D0h]
  __int64 v20; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v27; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID *v29[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v30; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v31; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v32[16]; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v33; // [rsp+C0h] [rbp-40h] BYREF
  int v34; // [rsp+D0h] [rbp-30h]
  LPVOID v35; // [rsp+118h] [rbp+18h]
  LPVOID pv; // [rsp+120h] [rbp+20h]
  LPVOID v37; // [rsp+128h] [rbp+28h]
  LPVOID v38; // [rsp+130h] [rbp+30h]
  LPVOID v39; // [rsp+138h] [rbp+38h]
  unsigned __int16 v40[64]; // [rsp+140h] [rbp+40h] BYREF

  v27 = 0;
  hObject = 0;
  v30 = 0;
  memset_0(&v33, 0, 0x80u);
  *(_OWORD *)v29 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v32, 0x5Eu, "CVdsDiskLun::RemountDiskVolumes");
  memset_0(&v33, 0, 0x80u);
  v2 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 28) + 24LL))(
         *((_QWORD *)this + 28),
         &v33);
  VolumeNameById = v2;
  if ( !*((_QWORD *)this + 28) )
  {
    VdsTraceEx(94, 0, "CVdsDiskLun::RemountDiskVolumes, 1, hr=%lX", v2);
    goto LABEL_22;
  }
  if ( v34 == 4 )
  {
    VdsTraceW(0, L"CVdsDiskLun::RemountDiskVolumes, 1.5");
    goto LABEL_22;
  }
  *(_OWORD *)v29 = 0;
  VolumeIdList = CVdsService::GetVolumeIdList(&v33, 1u, (struct _VDS_UNINSTALL_INFORMATION *)v29);
  VolumeNameById = VolumeIdList;
  if ( VolumeIdList < 0 )
  {
    VdsTraceW(0, L"CVdsDiskLun::RemountDiskVolumes, 2, hr=%lX", (unsigned int)VolumeIdList);
    goto LABEL_22;
  }
  v5 = v29[1];
  for ( i = 0; i < LODWORD(v29[0]); ++v5 )
  {
    memset_0(v40, 0, sizeof(v40));
    v7 = v27;
    ProcessHeap = GetProcessHeap();
    VdsHeapFree(ProcessHeap, 0, v7);
    v27 = 0;
    v31 = *v5;
    VolumeNameById = CVdsService::GetVolumeNameById(&v31, &v27, &v30);
    if ( VolumeNameById != -2147211503 )
    {
      if ( VolumeNameById < 0 )
      {
        memset_0(v40, 0, sizeof(v40));
        LODWORD(v26) = v5->Data4[7];
        LODWORD(v25) = v5->Data4[6];
        LODWORD(v24) = v5->Data4[5];
        LODWORD(v23) = v5->Data4[4];
        LODWORD(v22) = v5->Data4[3];
        LODWORD(v21) = v5->Data4[2];
        LODWORD(v20) = v5->Data4[1];
        LODWORD(v19) = v5->Data4[0];
        LODWORD(v18) = v5->Data3;
        LODWORD(v17) = v5->Data2;
        StringCchPrintfW(
          v40,
          0x40u,
          L"%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x",
          v5->Data1,
          v17,
          v18,
          v19,
          v20,
          v21,
          v22,
          v23,
          v24,
          v25,
          v26);
        VdsTraceW(1, L"CVdsDiskLun::RemountDiskVolumes, 3, ObjectId=%s, hr=%lX", v40, (unsigned int)VolumeNameById);
        VolumeNameById = 0;
        goto LABEL_21;
      }
      hObject = 0;
      v9 = OpenDevice(v27, 0x80000000LL, &hObject);
      v10 = (unsigned int)v9;
      if ( !v9 )
      {
        v12 = (unsigned int)hObject;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          CloseHandle(hObject);
          hObject = 0;
        }
        CVdsService::SendVolumeNotification(v12, v5);
        goto LABEL_21;
      }
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      v11 = L"UNKNOWN";
      if ( v27 )
        v11 = v27;
      VdsTraceW(1, L"CVdsDiskLun::RemountDiskVolumes, 4, %lX, name=%s", v10, v11);
    }
    VolumeNameById = 0;
LABEL_21:
    ++i;
  }
LABEL_22:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v37 )
  {
    CoTaskMemFree(v37);
    v37 = 0;
  }
  if ( v39 )
  {
    CoTaskMemFree(v39);
    v39 = 0;
  }
  if ( v35 )
  {
    CoTaskMemFree(v35);
    v35 = 0;
  }
  if ( v38 )
  {
    CoTaskMemFree(v38);
    v38 = 0;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v13 = v27;
  v14 = GetProcessHeap();
  VdsHeapFree(v14, 0, v13);
  v27 = 0;
  v15 = GetProcessHeap();
  VdsHeapFree(v15, 0, v29[1]);
  v29[1] = 0;
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v32);
  return (unsigned int)VolumeNameById;
}

```

## disassembly

```asm
0x140029cf4  push    rbp
0x140029cf6  push    rbx
0x140029cf7  push    rsi
0x140029cf8  push    rdi
0x140029cf9  push    r12
0x140029cfb  push    r13
0x140029cfd  push    r14
0x140029cff  push    r15
0x140029d01  lea     rbp, [rsp-0D8h]
0x140029d09  sub     rsp, 1D8h
0x140029d10  mov     rax, cs:__security_cookie
0x140029d17  xor     rax, rsp
0x140029d1a  mov     [rbp+110h+var_50], rax
0x140029d21  mov     rbx, rcx
0x140029d24  xor     r13d, r13d
0x140029d27  mov     [rsp+210h+var_1A0], r13
0x140029d2c  mov     [rsp+210h+hObject], r13
0x140029d31  mov     [rbp+110h+var_180], r13
0x140029d35  mov     esi, 80h
0x140029d3a  mov     r8d, esi; Size
0x140029d3d  xor     edx, edx; Val
0x140029d3f  lea     rcx, [rbp+110h+var_150]; void *
0x140029d43  call    memset_0
0x140029d48  xorps   xmm0, xmm0
0x140029d4b  movups  xmmword ptr [rbp+110h+var_190], xmm0
0x140029d4f  lea     r8, aCvdsdisklunRem_3; "CVdsDiskLun::RemountDiskVolumes"
0x140029d56  lea     edi, [rsi-22h]
0x140029d59  mov     edx, edi
0x140029d5b  lea     rcx, [rbp+110h+var_160]
0x140029d5f  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140029d65  nop
0x140029d66  mov     r8d, esi; Size
0x140029d69  xor     edx, edx; Val
0x140029d6b  lea     rcx, [rbp+110h+var_150]; void *
0x140029d6f  call    memset_0
0x140029d74  mov     rcx, [rbx+0E0h]
0x140029d7b  mov     rax, [rcx]
0x140029d7e  lea     rdx, [rbp+110h+var_150]
0x140029d82  mov     rax, [rax+18h]
0x140029d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029d8b  mov     r14d, eax
0x140029d8e  cmp     [rbx+0E0h], r13
0x140029d95  jnz     short loc_140029DB0
0x140029d97  mov     r9d, eax
0x140029d9a  lea     r8, aCvdsdisklunRem_1; "CVdsDiskLun::RemountDiskVolumes, 1, hr="...
0x140029da1  xor     edx, edx
0x140029da3  mov     ecx, edi
0x140029da5  call    cs:__imp_VdsTraceEx
0x140029dab  jmp     loc_140029FA6
0x140029db0  cmp     [rbp+110h+var_140], 4
0x140029db4  jnz     short loc_140029DCA
0x140029db6  lea     rdx, aCvdsdisklunRem; "CVdsDiskLun::RemountDiskVolumes, 1.5"
0x140029dbd  xor     ecx, ecx
0x140029dbf  call    cs:__imp_VdsTraceW
0x140029dc5  jmp     loc_140029FA6
0x140029dca  xorps   xmm0, xmm0
0x140029dcd  movups  xmmword ptr [rbp+110h+var_190], xmm0
0x140029dd1  lea     r8, [rbp+110h+var_190]; struct _VDS_UNINSTALL_INFORMATION *
0x140029dd5  mov     edx, 1; unsigned int
0x140029dda  lea     rcx, [rbp+110h+var_150]; struct _GUID *
0x140029dde  call    ?GetVolumeIdList@CVdsService@@SAJPEAU_GUID@@KPEAU_VDS_UNINSTALL_INFORMATION@@@Z; CVdsService::GetVolumeIdList(_GUID *,ulong,_VDS_UNINSTALL_INFORMATION *)
0x140029de3  mov     r14d, eax
0x140029de6  test    eax, eax
0x140029de8  jns     short loc_140029E01
0x140029dea  mov     r8d, eax
0x140029ded  lea     rdx, aCvdsdisklunRem_2; "CVdsDiskLun::RemountDiskVolumes, 2, hr="...
0x140029df4  xor     ecx, ecx
0x140029df6  call    cs:__imp_VdsTraceW
0x140029dfc  jmp     loc_140029FA6
0x140029e01  mov     r15, [rbp+110h+var_190+8]
0x140029e05  mov     r12d, r13d
0x140029e08  cmp     dword ptr [rbp+110h+var_190], r13d
0x140029e0c  jbe     loc_140029FA6
0x140029e12  mov     r8, rsi; Size
0x140029e15  xor     edx, edx; Val
0x140029e17  lea     rcx, [rbp+110h+var_D0]; void *
0x140029e1b  call    memset_0
0x140029e20  mov     rbx, [rsp+210h+var_1A0]
0x140029e25  call    cs:__imp_GetProcessHeap
0x140029e2b  mov     r8, rbx
0x140029e2e  xor     edx, edx
0x140029e30  mov     rcx, rax
0x140029e33  call    cs:__imp_VdsHeapFree
0x140029e39  mov     [rsp+210h+var_1A0], r13
0x140029e3e  movups  xmm0, xmmword ptr [r15]
0x140029e42  movdqu  xmmword ptr [rbp+110h+var_170.Data1], xmm0
0x140029e47  lea     r8, [rbp+110h+var_180]; unsigned __int64 *
0x140029e4b  lea     rdx, [rsp+210h+var_1A0]; unsigned __int16 **
0x140029e50  lea     rcx, [rbp+110h+var_170]; struct _GUID
0x140029e54  call    ?GetVolumeNameById@CVdsService@@SAJU_GUID@@PEAPEAGAEA_K@Z; CVdsService::GetVolumeNameById(_GUID,ushort * *,unsigned __int64 &)
0x140029e59  mov     r14d, eax
0x140029e5c  cmp     eax, 80042711h
0x140029e61  jnz     short loc_140029E6B
0x140029e63  mov     r14d, r13d
0x140029e66  jmp     loc_140029F95
0x140029e6b  test    r14d, r14d
0x140029e6e  jns     loc_140029F1B
0x140029e74  mov     r8, rsi; Size
0x140029e77  xor     edx, edx; Val
0x140029e79  lea     rcx, [rbp+110h+var_D0]; void *
0x140029e7d  call    memset_0
0x140029e82  movzx   eax, byte ptr [r15+0Fh]
0x140029e87  movzx   ecx, byte ptr [r15+0Eh]
0x140029e8c  movzx   edx, byte ptr [r15+0Dh]
0x140029e91  movzx   r8d, byte ptr [r15+0Ch]
0x140029e96  movzx   r9d, byte ptr [r15+0Bh]
0x140029e9b  movzx   r10d, byte ptr [r15+0Ah]
0x140029ea0  movzx   r11d, byte ptr [r15+9]
0x140029ea5  movzx   ebx, byte ptr [r15+8]
0x140029eaa  movzx   edi, word ptr [r15+6]
0x140029eaf  movzx   esi, word ptr [r15+4]
0x140029eb4  mov     dword ptr [rsp+210h+var_1A8], eax
0x140029eb8  mov     dword ptr [rsp+210h+var_1B0], ecx
0x140029ebc  mov     dword ptr [rsp+210h+var_1B8], edx
0x140029ec0  mov     dword ptr [rsp+210h+var_1C0], r8d
0x140029ec5  mov     dword ptr [rsp+210h+var_1C8], r9d
0x140029eca  mov     dword ptr [rsp+210h+var_1D0], r10d
0x140029ecf  mov     dword ptr [rsp+210h+var_1D8], r11d
0x140029ed4  mov     dword ptr [rsp+210h+var_1E0], ebx
0x140029ed8  mov     dword ptr [rsp+210h+var_1E8], edi
0x140029edc  mov     dword ptr [rsp+210h+var_1F0], esi
0x140029ee0  mov     r9d, [r15]
0x140029ee3  lea     r8, a8x4x4x2x2x2x2x; "%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2"...
0x140029eea  mov     edx, 40h ; '@'; unsigned __int64
0x140029eef  lea     rcx, [rbp+110h+var_D0]; unsigned __int16 *
0x140029ef3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140029ef8  mov     r9d, r14d
0x140029efb  lea     r8, [rbp+110h+var_D0]
0x140029eff  lea     rdx, aCvdsdisklunRem_6; "CVdsDiskLun::RemountDiskVolumes, 3, Obj"...
0x140029f06  mov     ecx, 1
0x140029f0b  call    cs:__imp_VdsTraceW
0x140029f11  mov     r14d, r13d
0x140029f14  mov     esi, 80h
0x140029f19  jmp     short loc_140029F95
0x140029f1b  mov     [rsp+210h+hObject], r13
0x140029f20  lea     r8, [rsp+210h+hObject]
0x140029f25  mov     edx, 80000000h
0x140029f2a  mov     rcx, [rsp+210h+var_1A0]
0x140029f2f  call    cs:__imp_OpenDevice
0x140029f35  mov     r8d, eax
0x140029f38  test    eax, eax
0x140029f3a  jz      short loc_140029F73
0x140029f3c  jle     short loc_140029F49
0x140029f3e  movzx   r8d, ax
0x140029f42  or      r8d, 80070000h
0x140029f49  lea     r9, aUnknown_0; "UNKNOWN"
0x140029f50  mov     rax, [rsp+210h+var_1A0]
0x140029f55  test    rax, rax
0x140029f58  cmovnz  r9, rax
0x140029f5c  lea     rdx, aCvdsdisklunRem_4; "CVdsDiskLun::RemountDiskVolumes, 4, %lX"...
0x140029f63  mov     ecx, 1
0x140029f68  call    cs:__imp_VdsTraceW
0x140029f6e  jmp     loc_140029E63
0x140029f73  mov     rcx, [rsp+210h+hObject]; hObject
0x140029f78  lea     rax, [rcx-1]
0x140029f7c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140029f80  ja      short loc_140029F8D
0x140029f82  call    cs:__imp_CloseHandle
0x140029f88  mov     [rsp+210h+hObject], r13
0x140029f8d  mov     rdx, r15; struct _GUID *
0x140029f90  call    ?SendVolumeNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendVolumeNotification(ulong,_GUID &)
0x140029f95  inc     r12d
0x140029f98  add     r15, 10h
0x140029f9c  cmp     r12d, dword ptr [rbp+110h+var_190]
0x140029fa0  jb      loc_140029E12
0x140029fa6  mov     rcx, [rbp+110h+pv]; pv
0x140029faa  test    rcx, rcx
0x140029fad  jz      short loc_140029FB9
0x140029faf  call    cs:__imp_CoTaskMemFree
0x140029fb5  mov     [rbp+110h+pv], r13
0x140029fb9  mov     rcx, [rbp+110h+var_E8]; pv
0x140029fbd  test    rcx, rcx
0x140029fc0  jz      short loc_140029FCC
0x140029fc2  call    cs:__imp_CoTaskMemFree
0x140029fc8  mov     [rbp+110h+var_E8], r13
0x140029fcc  mov     rcx, [rbp+110h+var_D8]; pv
0x140029fd0  test    rcx, rcx
0x140029fd3  jz      short loc_140029FDF
0x140029fd5  call    cs:__imp_CoTaskMemFree
0x140029fdb  mov     [rbp+110h+var_D8], r13
0x140029fdf  mov     rcx, [rbp+110h+var_F8]; pv
0x140029fe3  test    rcx, rcx
0x140029fe6  jz      short loc_140029FF2
0x140029fe8  call    cs:__imp_CoTaskMemFree
0x140029fee  mov     [rbp+110h+var_F8], r13
0x140029ff2  mov     rcx, [rbp+110h+var_E0]; pv
0x140029ff6  test    rcx, rcx
0x140029ff9  jz      short loc_14002A005
0x140029ffb  call    cs:__imp_CoTaskMemFree
0x14002a001  mov     [rbp+110h+var_E0], r13
0x14002a005  mov     rcx, [rsp+210h+hObject]; hObject
0x14002a00a  lea     rax, [rcx-1]
0x14002a00e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002a012  ja      short loc_14002A01F
0x14002a014  call    cs:__imp_CloseHandle
0x14002a01a  mov     [rsp+210h+hObject], r13
0x14002a01f  mov     rbx, [rsp+210h+var_1A0]
0x14002a024  call    cs:__imp_GetProcessHeap
0x14002a02a  mov     r8, rbx
0x14002a02d  xor     edx, edx
0x14002a02f  mov     rcx, rax
0x14002a032  call    cs:__imp_VdsHeapFree
0x14002a038  mov     [rsp+210h+var_1A0], r13
0x14002a03d  call    cs:__imp_GetProcessHeap
0x14002a043  mov     rcx, rax
0x14002a046  mov     r8, [rbp+110h+var_190+8]
0x14002a04a  xor     edx, edx
0x14002a04c  call    cs:__imp_VdsHeapFree
0x14002a052  mov     [rbp+110h+var_190+8], r13
0x14002a056  lea     rcx, [rbp+110h+var_160]
0x14002a05a  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002a060  mov     eax, r14d
0x14002a063  mov     rcx, [rbp+110h+var_50]
0x14002a06a  xor     rcx, rsp; StackCookie
0x14002a06d  call    __security_check_cookie
0x14002a072  add     rsp, 1D8h
0x14002a079  pop     r15
0x14002a07b  pop     r14
0x14002a07d  pop     r13
0x14002a07f  pop     r12
0x14002a081  pop     rdi
0x14002a082  pop     rsi
0x14002a083  pop     rbx
0x14002a084  pop     rbp
0x14002a085  retn
```
