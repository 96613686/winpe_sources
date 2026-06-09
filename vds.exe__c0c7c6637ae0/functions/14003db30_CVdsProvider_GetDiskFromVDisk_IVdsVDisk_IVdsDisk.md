# CVdsProvider::GetDiskFromVDisk(IVdsVDisk *,IVdsDisk * *)

- ea: `0x14003db30`
- end: `0x14003dd10`
- name: `?GetDiskFromVDisk@CVdsProvider@@UEAAJPEAUIVdsVDisk@@PEAPEAUIVdsDisk@@@Z`
- size: `480`
- prototype: `__int64 __fastcall(CVdsProvider *__hidden this, struct IVdsVDisk *, struct IVdsDisk **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x14001b958`
- `0x14003db30`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003dcda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003dcda`
- `vdsutil!VdsTraceEx` at `0x14003dbd0`
- `vdsutil!VdsTraceEx` at `0x14003dbfc`
- `vdsutil!VdsTraceEx` at `0x14003dcae`
- `vdsutil!VdsTraceEx` at `0x14003dbd0`
- `vdsutil!VdsTraceEx` at `0x14003dbfc`
- `vdsutil!VdsTraceEx` at `0x14003dcae`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003db71`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003db71`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003dce5`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003dce5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsProvider::GetDiskFromVDisk(CVdsProvider *this, struct IVdsVDisk *a2, struct IVdsDisk **a3)
{
  int DiskId; // eax
  unsigned int v7; // ebx
  const char *v8; // r8
  __int64 v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-48h] BYREF
  struct _GUID v13; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v14[16]; // [rsp+50h] [rbp-30h] BYREF
  struct _GUID v15; // [rsp+60h] [rbp-20h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v14, 0x5Eu, "CVdsProvider::GetDiskFromVDisk");
  v15 = 0;
  pv = 0;
  v11 = 0;
  if ( a2 && a3 )
  {
    *a3 = 0;
    DiskId = ((__int64 (__fastcall *)(struct IVdsVDisk *, LPVOID *))a2->lpVtbl->GetDeviceName)(a2, &pv);
    v7 = DiskId;
    if ( DiskId < 0 )
    {
      v8 = "CVdsProvider::GetDiskFromVDisk, 1, hr=%lX";
LABEL_5:
      VdsTraceEx(94, 0, v8, (unsigned int)DiskId);
      goto LABEL_17;
    }
    if ( !pv )
    {
      v7 = -2147212283;
      v8 = "CVdsProvider::GetDiskFromVDisk, 1.1, hr=%lX";
LABEL_8:
      VdsTraceEx(94, 3, v8);
      goto LABEL_17;
    }
    DiskId = CVdsService::GetDiskId((wchar_t *)pv, &v15);
    v7 = DiskId;
    if ( DiskId < 0 )
    {
      v8 = "CVdsProvider::GetDiskFromVDisk, 2, hr=%lX";
      if ( DiskId != -2147212283 )
        goto LABEL_5;
      goto LABEL_8;
    }
    v9 = *((_QWORD *)this + 10);
    v13 = v15;
    DiskId = (*(__int64 (__fastcall **)(__int64, struct _GUID *, __int64, __int64 *))(*(_QWORD *)v9 + 72LL))(
               v9,
               &v13,
               13,
               &v11);
    v7 = DiskId;
    if ( DiskId < 0 )
    {
      v8 = "CVdsProvider::GetDiskFromVDisk, 3, hr=%lX";
      goto LABEL_5;
    }
    DiskId = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IVdsDisk **))v11)(v11, &IID_IVdsDisk, a3);
    v7 = DiskId;
    if ( DiskId < 0 )
    {
      v8 = "CVdsProvider::GetDiskFromVDisk, 4, hr=%lX";
      goto LABEL_5;
    }
  }
  else
  {
    v7 = -2147024809;
    VdsTraceEx(94, 0, "CVdsProvider::GetDiskFromVDisk, pVDisk=%p, ppDisk=%p, hr=%lX", a2, a3, -2147024809);
  }
LABEL_17:
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
  return v7;
}

```

## disassembly

```asm
0x14003db30  mov     [rsp-28h+arg_18], rbx
0x14003db35  push    rbp
0x14003db36  push    rsi
0x14003db37  push    rdi
0x14003db38  push    r12
0x14003db3a  push    r14
0x14003db3c  mov     rbp, rsp
0x14003db3f  sub     rsp, 80h
0x14003db46  mov     rax, cs:__security_cookie
0x14003db4d  xor     rax, rsp
0x14003db50  mov     [rbp+var_10], rax
0x14003db54  mov     rdi, r8
0x14003db57  mov     rsi, rdx
0x14003db5a  mov     r14, rcx
0x14003db5d  lea     r8, aCvdsproviderGe_9; "CVdsProvider::GetDiskFromVDisk"
0x14003db64  mov     r12d, 5Eh ; '^'
0x14003db6a  mov     edx, r12d
0x14003db6d  lea     rcx, [rbp+var_30]
0x14003db71  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003db77  nop
0x14003db78  xorps   xmm0, xmm0
0x14003db7b  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x14003db7f  mov     [rbp+pv], 0
0x14003db87  mov     [rbp+var_50], 0
0x14003db8f  test    rsi, rsi
0x14003db92  jz      loc_14003DC91
0x14003db98  test    rdi, rdi
0x14003db9b  jz      loc_14003DC91
0x14003dba1  mov     qword ptr [rdi], 0
0x14003dba8  mov     rax, [rsi]
0x14003dbab  lea     rdx, [rbp+pv]
0x14003dbaf  mov     rcx, rsi
0x14003dbb2  mov     rax, [rax+30h]
0x14003dbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dbbb  mov     ebx, eax
0x14003dbbd  test    eax, eax
0x14003dbbf  jns     short loc_14003DBDB
0x14003dbc1  lea     r8, aCvdsproviderGe_10; "CVdsProvider::GetDiskFromVDisk, 1, hr=%"...
0x14003dbc8  mov     ecx, r12d
0x14003dbcb  mov     r9d, eax
0x14003dbce  xor     edx, edx
0x14003dbd0  call    cs:__imp_VdsTraceEx
0x14003dbd6  jmp     loc_14003DCB4
0x14003dbdb  mov     rcx, [rbp+pv]; String1
0x14003dbdf  test    rcx, rcx
0x14003dbe2  jnz     short loc_14003DC07
0x14003dbe4  mov     r9d, 80042405h
0x14003dbea  mov     ebx, r9d
0x14003dbed  lea     r8, aCvdsproviderGe_4; "CVdsProvider::GetDiskFromVDisk, 1.1, hr"...
0x14003dbf4  mov     ecx, r12d
0x14003dbf7  mov     edx, 3
0x14003dbfc  call    cs:__imp_VdsTraceEx
0x14003dc02  jmp     loc_14003DCB4
0x14003dc07  lea     rdx, [rbp+var_20]; struct _GUID *
0x14003dc0b  call    ?GetDiskId@CVdsService@@SAJPEAGPEAU_GUID@@@Z; CVdsService::GetDiskId(ushort *,_GUID *)
0x14003dc10  mov     ebx, eax
0x14003dc12  test    eax, eax
0x14003dc14  jns     short loc_14003DC2D
0x14003dc16  mov     r9d, 80042405h
0x14003dc1c  lea     r8, aCvdsproviderGe_7; "CVdsProvider::GetDiskFromVDisk, 2, hr=%"...
0x14003dc23  mov     ecx, r12d
0x14003dc26  cmp     eax, r9d
0x14003dc29  jz      short loc_14003DBF7
0x14003dc2b  jmp     short loc_14003DBCB
0x14003dc2d  mov     rcx, [r14+50h]
0x14003dc31  movaps  xmm0, xmmword ptr [rbp+var_20.Data1]
0x14003dc35  movdqa  [rbp+var_40], xmm0
0x14003dc3a  mov     rax, [rcx]
0x14003dc3d  lea     r9, [rbp+var_50]
0x14003dc41  mov     r8d, 0Dh
0x14003dc47  lea     rdx, [rbp+var_40]
0x14003dc4b  mov     rax, [rax+48h]
0x14003dc4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dc54  mov     ebx, eax
0x14003dc56  test    eax, eax
0x14003dc58  jns     short loc_14003DC66
0x14003dc5a  lea     r8, aCvdsproviderGe_19; "CVdsProvider::GetDiskFromVDisk, 3, hr=%"...
0x14003dc61  jmp     loc_14003DBC8
0x14003dc66  mov     rcx, [rbp+var_50]
0x14003dc6a  mov     rax, [rcx]
0x14003dc6d  mov     r8, rdi
0x14003dc70  lea     rdx, IID_IVdsDisk
0x14003dc77  mov     rax, [rax]
0x14003dc7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dc7f  mov     ebx, eax
0x14003dc81  test    eax, eax
0x14003dc83  jns     short loc_14003DCB4
0x14003dc85  lea     r8, aCvdsproviderGe_2; "CVdsProvider::GetDiskFromVDisk, 4, hr=%"...
0x14003dc8c  jmp     loc_14003DBC8
0x14003dc91  mov     ebx, 80070057h
0x14003dc96  mov     [rsp+80h+var_58], ebx
0x14003dc9a  mov     [rsp+80h+var_60], rdi
0x14003dc9f  mov     r9, rsi
0x14003dca2  lea     r8, aCvdsproviderGe_8; "CVdsProvider::GetDiskFromVDisk, pVDisk="...
0x14003dca9  xor     edx, edx
0x14003dcab  mov     ecx, r12d
0x14003dcae  call    cs:__imp_VdsTraceEx
0x14003dcb4  mov     rcx, [rbp+var_50]
0x14003dcb8  test    rcx, rcx
0x14003dcbb  jz      short loc_14003DCD1
0x14003dcbd  mov     rax, [rcx]
0x14003dcc0  mov     rax, [rax+10h]
0x14003dcc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dcc9  mov     [rbp+var_50], 0
0x14003dcd1  mov     rcx, [rbp+pv]; pv
0x14003dcd5  test    rcx, rcx
0x14003dcd8  jz      short loc_14003DCE1
0x14003dcda  call    cs:__imp_CoTaskMemFree
0x14003dce0  nop
0x14003dce1  lea     rcx, [rbp+var_30]
0x14003dce5  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003dceb  mov     eax, ebx
0x14003dced  mov     rcx, [rbp+var_10]
0x14003dcf1  xor     rcx, rsp; StackCookie
0x14003dcf4  call    __security_check_cookie
0x14003dcf9  mov     rbx, [rsp+80h+arg_18]
0x14003dd01  add     rsp, 80h
0x14003dd08  pop     r14
0x14003dd0a  pop     r12
0x14003dd0c  pop     rdi
0x14003dd0d  pop     rsi
0x14003dd0e  pop     rbp
0x14003dd0f  retn
```
