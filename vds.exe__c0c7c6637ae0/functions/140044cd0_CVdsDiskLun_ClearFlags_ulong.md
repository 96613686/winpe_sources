# CVdsDiskLun::ClearFlags(ulong)

- ea: `0x140044cd0`
- end: `0x140044f4c`
- name: `?ClearFlags@CVdsDiskLun@@UEAAJK@Z`
- size: `636`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x140028768`
- `0x140029cf4`
- `0x14002e123`
- `0x140044cd0`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140044f0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140044f0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140044d52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140044d52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044e92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044ea9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044ec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044ed7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044eee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044e92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044ea9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044ec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044ed7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044eee`
- `vdsutil!VdsTraceEx` at `0x140044d76`
- `vdsutil!VdsTraceEx` at `0x140044dbe`
- `vdsutil!VdsTraceEx` at `0x140044e57`
- `vdsutil!VdsTraceEx` at `0x140044e7d`
- `vdsutil!VdsTraceEx` at `0x140044d76`
- `vdsutil!VdsTraceEx` at `0x140044dbe`
- `vdsutil!VdsTraceEx` at `0x140044e57`
- `vdsutil!VdsTraceEx` at `0x140044e7d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140044d10`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140044d10`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140044f21`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140044f21`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::ClearFlags(CVdsDiskLun *this, unsigned int a2)
{
  signed int v4; // ebx
  int v5; // edi
  int v6; // eax
  int v7; // eax
  const char *v8; // r8
  int v9; // eax
  int v10; // eax
  __int64 v12; // [rsp+20h] [rbp-79h] BYREF
  int v13; // [rsp+28h] [rbp-71h]
  _BYTE v14[16]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v15[60]; // [rsp+40h] [rbp-59h] BYREF
  int v16; // [rsp+7Ch] [rbp-1Dh]
  LPVOID pv; // [rsp+98h] [rbp-1h]
  LPVOID v18; // [rsp+A0h] [rbp+7h]
  LPVOID v19; // [rsp+A8h] [rbp+Fh]
  LPVOID v20; // [rsp+B0h] [rbp+17h]
  LPVOID v21; // [rsp+B8h] [rbp+1Fh]

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v14, 0x5Eu, "CVdsDiskLun::ClearFlags");
  memset_0(v15, 0, 0x80u);
  v12 = 0;
  v13 = 0;
  v4 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v12);
  if ( v4 < 0 )
    goto LABEL_36;
  v5 = 0;
  EnterCriticalSection(&g_GlobalCriticalSection);
  v6 = CVdsDiskLun::ValidateDiskInterfaces(this);
  v4 = v6;
  if ( v6 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsDiskLun::ClearFlags, 1, hr=%lX", v6);
    if ( v4 == -2147212283 )
      v4 = -2147212277;
    goto LABEL_22;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 28) + 24LL))(*((_QWORD *)this + 28), v15);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = "CVdsDiskLun::ClearFlags, 2, hr=%lX";
LABEL_7:
    VdsTraceEx(94, 0, v8, (unsigned int)v7);
    goto LABEL_22;
  }
  if ( (v16 & 0x100) != 0 )
  {
    v4 = -2147211257;
    VdsTraceEx(94, 0, "CVdsDiskLun::ClearFlags, 3, hr=%lX", 2147756039LL);
  }
  else if ( (v16 & 0x80u) == 0 )
  {
    if ( (v16 & 0x4000) == 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 28) + 72LL))(*((_QWORD *)this + 28), a2);
      v4 = v7;
      if ( v7 >= 0 )
      {
        v9 = CVdsDiskLun::DismountDiskVolumes(this);
        if ( v9 < 0 )
        {
          VdsTraceEx(94, 0, "CVdsDiskLun::ClearFlags, 5, hr=%lX", v9);
          v5 = 272392;
        }
        v10 = CVdsDiskLun::RemountDiskVolumes(this);
        v4 = v10;
        if ( v10 < 0 )
        {
          VdsTraceEx(94, 0, "CVdsDiskLun::ClearFlags, 6, hr=%lX", v10);
          if ( !v5 )
            v5 = 272392;
        }
        goto LABEL_22;
      }
      v8 = "CVdsDiskLun::ClearFlags, 4, hr=%lX";
      goto LABEL_7;
    }
    v4 = -2147211247;
    VdsTraceEx(94, 0, "CVdsDiskLun::ClearFlags, 3.75, Boot from disk, hr=%lX", 2147756049LL);
  }
  else
  {
    v4 = -2147211247;
    VdsTraceEx(94, 0, "CVdsDiskLun::ClearFlags, 3.5, system disk, hr=%lX", 2147756049LL);
  }
LABEL_22:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v18 )
  {
    CoTaskMemFree(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    CoTaskMemFree(v19);
    v19 = 0;
  }
  if ( v20 )
  {
    CoTaskMemFree(v20);
    v20 = 0;
  }
  if ( v21 )
  {
    CoTaskMemFree(v21);
    v21 = 0;
  }
  if ( !v4 && v5 )
    v4 = v5;
  LeaveCriticalSection(&g_GlobalCriticalSection);
LABEL_36:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v12);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140044cd0  mov     [rsp-8+arg_10], rbx
0x140044cd5  push    rbp
0x140044cd6  push    rsi
0x140044cd7  push    rdi
0x140044cd8  push    r12
0x140044cda  push    r14
0x140044cdc  lea     rbp, [rsp-37h]
0x140044ce1  sub     rsp, 0D0h
0x140044ce8  mov     rax, cs:__security_cookie
0x140044cef  xor     rax, rsp
0x140044cf2  mov     [rbp+57h+var_28], rax
0x140044cf6  mov     r14d, edx
0x140044cf9  mov     rsi, rcx
0x140044cfc  lea     r8, aCvdsdisklunCle_0; "CVdsDiskLun::ClearFlags"
0x140044d03  mov     r12d, 5Eh ; '^'
0x140044d09  mov     edx, r12d
0x140044d0c  lea     rcx, [rbp+57h+var_C0]
0x140044d10  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140044d16  nop
0x140044d17  xor     edx, edx; Val
0x140044d19  lea     r8d, [r12+22h]; Size
0x140044d1e  lea     rcx, [rbp+57h+var_B0]; void *
0x140044d22  call    memset_0
0x140044d27  mov     [rbp+57h+var_D0], 0
0x140044d2f  mov     [rbp+57h+var_C8], 0
0x140044d36  lea     rcx, [rbp+57h+var_D0]; this
0x140044d3a  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140044d3f  mov     ebx, eax
0x140044d41  test    eax, eax
0x140044d43  js      loc_140044F13
0x140044d49  xor     edi, edi
0x140044d4b  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140044d52  call    cs:__imp_EnterCriticalSection
0x140044d58  nop
0x140044d59  mov     rcx, rsi; this
0x140044d5c  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140044d61  mov     ebx, eax
0x140044d63  test    eax, eax
0x140044d65  jns     short loc_140044D92
0x140044d67  mov     r9d, eax
0x140044d6a  lea     r8, aCvdsdisklunCle_10; "CVdsDiskLun::ClearFlags, 1, hr=%lX"
0x140044d71  xor     edx, edx
0x140044d73  mov     ecx, r12d
0x140044d76  call    cs:__imp_VdsTraceEx
0x140044d7c  cmp     ebx, 80042405h
0x140044d82  jnz     loc_140044E89
0x140044d88  mov     ebx, 8004240Bh
0x140044d8d  jmp     loc_140044E89
0x140044d92  mov     rcx, [rsi+0E0h]
0x140044d99  mov     rax, [rcx]
0x140044d9c  lea     rdx, [rbp+57h+var_B0]
0x140044da0  mov     rax, [rax+18h]
0x140044da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044da9  mov     ebx, eax
0x140044dab  test    eax, eax
0x140044dad  jns     short loc_140044DC9
0x140044daf  lea     r8, aCvdsdisklunCle_19; "CVdsDiskLun::ClearFlags, 2, hr=%lX"
0x140044db6  mov     r9d, eax
0x140044db9  xor     edx, edx
0x140044dbb  mov     ecx, r12d
0x140044dbe  call    cs:__imp_VdsTraceEx
0x140044dc4  jmp     loc_140044E89
0x140044dc9  mov     eax, [rbp+57h+var_74]
0x140044dcc  bt      eax, 8
0x140044dd0  jnb     short loc_140044DE3
0x140044dd2  mov     ebx, 80042807h
0x140044dd7  mov     r9d, ebx
0x140044dda  lea     r8, aCvdsdisklunCle_17; "CVdsDiskLun::ClearFlags, 3, hr=%lX"
0x140044de1  jmp     short loc_140044DB9
0x140044de3  test    al, al
0x140044de5  jns     short loc_140044DF9
0x140044de7  mov     r9d, 80042811h
0x140044ded  mov     ebx, r9d
0x140044df0  lea     r8, aCvdsdisklunCle_18; "CVdsDiskLun::ClearFlags, 3.5, system di"...
0x140044df7  jmp     short loc_140044DB9
0x140044df9  bt      eax, 0Eh
0x140044dfd  jnb     short loc_140044E11
0x140044dff  mov     r9d, 80042811h
0x140044e05  mov     ebx, r9d
0x140044e08  lea     r8, aCvdsdisklunCle_9; "CVdsDiskLun::ClearFlags, 3.75, Boot fro"...
0x140044e0f  jmp     short loc_140044DB9
0x140044e11  mov     rcx, [rsi+0E0h]
0x140044e18  mov     rax, [rcx]
0x140044e1b  mov     edx, r14d
0x140044e1e  mov     rax, [rax+48h]
0x140044e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044e27  mov     ebx, eax
0x140044e29  test    eax, eax
0x140044e2b  jns     short loc_140044E36
0x140044e2d  lea     r8, aCvdsdisklunCle_13; "CVdsDiskLun::ClearFlags, 4, hr=%lX"
0x140044e34  jmp     short loc_140044DB6
0x140044e36  mov     rcx, rsi; this
0x140044e39  call    ?DismountDiskVolumes@CVdsDiskLun@@QEAAJXZ; CVdsDiskLun::DismountDiskVolumes(void)
0x140044e3e  mov     r14d, 42808h
0x140044e44  test    eax, eax
0x140044e46  jns     short loc_140044E60
0x140044e48  mov     r9d, eax
0x140044e4b  lea     r8, aCvdsdisklunCle_5; "CVdsDiskLun::ClearFlags, 5, hr=%lX"
0x140044e52  xor     edx, edx
0x140044e54  mov     ecx, r12d
0x140044e57  call    cs:__imp_VdsTraceEx
0x140044e5d  mov     edi, r14d
0x140044e60  mov     rcx, rsi; this
0x140044e63  call    ?RemountDiskVolumes@CVdsDiskLun@@QEAAJXZ; CVdsDiskLun::RemountDiskVolumes(void)
0x140044e68  mov     ebx, eax
0x140044e6a  test    eax, eax
0x140044e6c  jns     short loc_140044E89
0x140044e6e  mov     r9d, eax
0x140044e71  lea     r8, aCvdsdisklunCle_4; "CVdsDiskLun::ClearFlags, 6, hr=%lX"
0x140044e78  xor     edx, edx
0x140044e7a  mov     ecx, r12d
0x140044e7d  call    cs:__imp_VdsTraceEx
0x140044e83  test    edi, edi
0x140044e85  cmovz   edi, r14d
0x140044e89  mov     rcx, [rbp+57h+pv]; pv
0x140044e8d  test    rcx, rcx
0x140044e90  jz      short loc_140044EA0
0x140044e92  call    cs:__imp_CoTaskMemFree
0x140044e98  mov     [rbp+57h+pv], 0
0x140044ea0  mov     rcx, [rbp+57h+var_50]; pv
0x140044ea4  test    rcx, rcx
0x140044ea7  jz      short loc_140044EB7
0x140044ea9  call    cs:__imp_CoTaskMemFree
0x140044eaf  mov     [rbp+57h+var_50], 0
0x140044eb7  mov     rcx, [rbp+57h+var_48]; pv
0x140044ebb  test    rcx, rcx
0x140044ebe  jz      short loc_140044ECE
0x140044ec0  call    cs:__imp_CoTaskMemFree
0x140044ec6  mov     [rbp+57h+var_48], 0
0x140044ece  mov     rcx, [rbp+57h+var_40]; pv
0x140044ed2  test    rcx, rcx
0x140044ed5  jz      short loc_140044EE5
0x140044ed7  call    cs:__imp_CoTaskMemFree
0x140044edd  mov     [rbp+57h+var_40], 0
0x140044ee5  mov     rcx, [rbp+57h+var_38]; pv
0x140044ee9  test    rcx, rcx
0x140044eec  jz      short loc_140044EFC
0x140044eee  call    cs:__imp_CoTaskMemFree
0x140044ef4  mov     [rbp+57h+var_38], 0
0x140044efc  test    ebx, ebx
0x140044efe  jnz     short loc_140044F05
0x140044f00  test    edi, edi
0x140044f02  cmovnz  ebx, edi
0x140044f05  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140044f0c  call    cs:__imp_LeaveCriticalSection
0x140044f12  nop
0x140044f13  lea     rcx, [rbp+57h+var_D0]; this
0x140044f17  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140044f1c  nop
0x140044f1d  lea     rcx, [rbp+57h+var_C0]
0x140044f21  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140044f27  mov     eax, ebx
0x140044f29  mov     rcx, [rbp+57h+var_28]
0x140044f2d  xor     rcx, rsp; StackCookie
0x140044f30  call    __security_check_cookie
0x140044f35  mov     rbx, [rsp+0F0h+arg_10]
0x140044f3d  add     rsp, 0D0h
0x140044f44  pop     r14
0x140044f46  pop     r12
0x140044f48  pop     rdi
0x140044f49  pop     rsi
0x140044f4a  pop     rbp
0x140044f4b  retn
```
