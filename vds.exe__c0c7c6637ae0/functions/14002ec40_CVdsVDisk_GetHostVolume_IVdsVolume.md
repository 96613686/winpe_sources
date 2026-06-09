# CVdsVDisk::GetHostVolume(IVdsVolume * *)

- ea: `0x14002ec40`
- end: `0x14002ee09`
- name: `?GetHostVolume@CVdsVDisk@@UEAAJPEAPEAUIVdsVolume@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(CVdsVDisk *__hidden this, struct IVdsVolume **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006a80`
- `0x14002e123`
- `0x14002ec40`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002eda4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002edb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002eda4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002edb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002edbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002edbd`
- `vdsutil!VdsHeapFree` at `0x14002edcb`
- `vdsutil!VdsHeapFree` at `0x14002edcb`
- `vdsutil!AllocateAndGetVolumePathName` at `0x14002ece9`
- `vdsutil!AllocateAndGetVolumePathName` at `0x14002ece9`
- `vdsutil!VdsTraceEx` at `0x14002ed78`
- `vdsutil!VdsTraceEx` at `0x14002ed78`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002ec82`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002ec82`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002eddd`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002eddd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsVDisk::GetHostVolume(CVdsVDisk *this, struct IVdsVolume **a2)
{
  int v4; // eax
  unsigned int v5; // edi
  int VolumePathName; // eax
  int VolumeId; // eax
  __int64 v8; // rcx
  int v9; // eax
  unsigned __int16 *v10; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v13; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int16 *v14; // [rsp+38h] [rbp-61h] BYREF
  struct _GUID v15; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v16[16]; // [rsp+50h] [rbp-49h] BYREF
  int v17; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v18[52]; // [rsp+64h] [rbp-35h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-1h]
  LPVOID v20; // [rsp+A0h] [rbp+7h]
  struct _GUID v21; // [rsp+C0h] [rbp+27h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v16, 0x5Eu, "CVdsVDisk::GetHostVolume");
  v17 = 0;
  memset_0(v18, 0, 0x54u);
  v14 = 0;
  v21 = GUID_NULL;
  v13 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11), &v17);
  v5 = v4;
  if ( v4 >= 0 )
  {
    VolumePathName = AllocateAndGetVolumePathName(pv, &v14);
    v5 = VolumePathName;
    if ( VolumePathName >= 0 )
    {
      VolumeId = CVdsService::GetVolumeId(v14, &v21, 0);
      v5 = VolumeId;
      if ( VolumeId < 0
        || (v8 = *((_QWORD *)this + 9),
            v15 = v21,
            VolumeId = (*(__int64 (__fastcall **)(__int64, struct _GUID *, __int64, __int64 *))(*(_QWORD *)v8 + 72LL))(
                         v8,
                         &v15,
                         11,
                         &v13),
            v5 = VolumeId,
            VolumeId < 0) )
      {
        VdsTraceEx(94, 0, "CVdsVDisk::GetHostVolume, 3, hr=%lX", (unsigned int)VolumeId);
      }
      else
      {
        v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IVdsVolume **))v13)(v13, &IID_IVdsVolume, a2);
        v5 = v9;
        if ( v9 < 0 )
          VdsTraceEx(94, 0, "CVdsVDisk::GetHostVolume, 4, hr=%lX", (unsigned int)v9);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsVDisk::GetHostVolume, 2, hr=%lX", (unsigned int)VolumePathName);
    }
  }
  else
  {
    VdsTraceEx(94, 0, "CVdsVDisk::GetHostVolume, 1, hr=%lX", (unsigned int)v4);
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v20 )
    CoTaskMemFree(v20);
  v10 = v14;
  ProcessHeap = GetProcessHeap();
  VdsHeapFree(ProcessHeap, 0, v10);
  v14 = 0;
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
  return v5;
}

```

## disassembly

```asm
0x14002ec40  mov     [rsp-8+arg_10], rbx
0x14002ec45  mov     [rsp-8+arg_18], rsi
0x14002ec4a  push    rbp
0x14002ec4b  push    rdi
0x14002ec4c  push    r15
0x14002ec4e  lea     rbp, [rsp-47h]
0x14002ec53  sub     rsp, 0E0h
0x14002ec5a  mov     rax, cs:__security_cookie
0x14002ec61  xor     rax, rsp
0x14002ec64  mov     [rbp+57h+var_20], rax
0x14002ec68  mov     rsi, rdx
0x14002ec6b  mov     rbx, rcx
0x14002ec6e  lea     r8, aCvdsvdiskGetho_0; "CVdsVDisk::GetHostVolume"
0x14002ec75  mov     r15d, 5Eh ; '^'
0x14002ec7b  mov     edx, r15d
0x14002ec7e  lea     rcx, [rbp+57h+var_A0]
0x14002ec82  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002ec88  nop
0x14002ec89  mov     [rbp+57h+var_90], 0
0x14002ec90  xor     edx, edx; Val
0x14002ec92  lea     r8d, [r15-0Ah]; Size
0x14002ec96  lea     rcx, [rbp+57h+var_8C]; void *
0x14002ec9a  call    memset_0
0x14002ec9f  mov     [rbp+57h+var_B8], 0
0x14002eca7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14002ecae  movdqu  xmmword ptr [rbp+57h+var_30.Data1], xmm0
0x14002ecb3  mov     [rbp+57h+var_C0], 0
0x14002ecbb  mov     rcx, [rbx+58h]
0x14002ecbf  mov     rax, [rcx]
0x14002ecc2  lea     rdx, [rbp+57h+var_90]
0x14002ecc6  mov     rax, [rax+20h]
0x14002ecca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002eccf  mov     edi, eax
0x14002ecd1  test    eax, eax
0x14002ecd3  jns     short loc_14002ECE1
0x14002ecd5  lea     r8, aCvdsvdiskGetho_2; "CVdsVDisk::GetHostVolume, 1, hr=%lX"
0x14002ecdc  jmp     loc_14002ED70
0x14002ece1  lea     rdx, [rbp+57h+var_B8]
0x14002ece5  mov     rcx, [rbp+57h+pv]
0x14002ece9  call    cs:__imp_AllocateAndGetVolumePathName
0x14002ecef  mov     edi, eax
0x14002ecf1  test    eax, eax
0x14002ecf3  jns     short loc_14002ECFE
0x14002ecf5  lea     r8, aCvdsvdiskGetho; "CVdsVDisk::GetHostVolume, 2, hr=%lX"
0x14002ecfc  jmp     short loc_14002ED70
0x14002ecfe  xor     r8d, r8d; int *
0x14002ed01  lea     rdx, [rbp+57h+var_30]; struct _GUID *
0x14002ed05  mov     rcx, [rbp+57h+var_B8]; unsigned __int16 *
0x14002ed09  call    ?GetVolumeId@CVdsService@@SAJPEAGPEAU_GUID@@PEAH@Z; CVdsService::GetVolumeId(ushort *,_GUID *,int *)
0x14002ed0e  mov     edi, eax
0x14002ed10  test    eax, eax
0x14002ed12  jns     short loc_14002ED1D
0x14002ed14  lea     r8, aCvdsvdiskGetho_1; "CVdsVDisk::GetHostVolume, 3, hr=%lX"
0x14002ed1b  jmp     short loc_14002ED70
0x14002ed1d  mov     rcx, [rbx+48h]
0x14002ed21  movaps  xmm0, xmmword ptr [rbp+57h+var_30.Data1]
0x14002ed25  movdqa  [rbp+57h+var_B0], xmm0
0x14002ed2a  mov     rax, [rcx]
0x14002ed2d  lea     r9, [rbp+57h+var_C0]
0x14002ed31  mov     r8d, 0Bh
0x14002ed37  lea     rdx, [rbp+57h+var_B0]
0x14002ed3b  mov     rax, [rax+48h]
0x14002ed3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ed44  mov     edi, eax
0x14002ed46  test    eax, eax
0x14002ed48  js      short loc_14002ED14
0x14002ed4a  mov     rcx, [rbp+57h+var_C0]
0x14002ed4e  mov     rax, [rcx]
0x14002ed51  mov     r8, rsi
0x14002ed54  lea     rdx, IID_IVdsVolume
0x14002ed5b  mov     rax, [rax]
0x14002ed5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ed63  mov     edi, eax
0x14002ed65  test    eax, eax
0x14002ed67  jns     short loc_14002ED7E
0x14002ed69  lea     r8, aCvdsvdiskGetho_3; "CVdsVDisk::GetHostVolume, 4, hr=%lX"
0x14002ed70  mov     r9d, eax
0x14002ed73  xor     edx, edx
0x14002ed75  mov     ecx, r15d
0x14002ed78  call    cs:__imp_VdsTraceEx
0x14002ed7e  mov     rcx, [rbp+57h+var_C0]
0x14002ed82  test    rcx, rcx
0x14002ed85  jz      short loc_14002ED9B
0x14002ed87  mov     rax, [rcx]
0x14002ed8a  mov     rax, [rax+10h]
0x14002ed8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ed93  mov     [rbp+57h+var_C0], 0
0x14002ed9b  mov     rcx, [rbp+57h+pv]; pv
0x14002ed9f  test    rcx, rcx
0x14002eda2  jz      short loc_14002EDAA
0x14002eda4  call    cs:__imp_CoTaskMemFree
0x14002edaa  mov     rcx, [rbp+57h+var_50]; pv
0x14002edae  test    rcx, rcx
0x14002edb1  jz      short loc_14002EDB9
0x14002edb3  call    cs:__imp_CoTaskMemFree
0x14002edb9  mov     rbx, [rbp+57h+var_B8]
0x14002edbd  call    cs:__imp_GetProcessHeap
0x14002edc3  mov     r8, rbx
0x14002edc6  xor     edx, edx
0x14002edc8  mov     rcx, rax
0x14002edcb  call    cs:__imp_VdsHeapFree
0x14002edd1  mov     [rbp+57h+var_B8], 0
0x14002edd9  lea     rcx, [rbp+57h+var_A0]
0x14002eddd  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002ede3  mov     eax, edi
0x14002ede5  mov     rcx, [rbp+57h+var_20]
0x14002ede9  xor     rcx, rsp; StackCookie
0x14002edec  call    __security_check_cookie
0x14002edf1  lea     r11, [rsp+0F0h+var_10]
0x14002edf9  mov     rbx, [r11+30h]
0x14002edfd  mov     rsi, [r11+38h]
0x14002ee01  mov     rsp, r11
0x14002ee04  pop     r15
0x14002ee06  pop     rdi
0x14002ee07  pop     rbp
0x14002ee08  retn
```
