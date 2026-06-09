# CVdsDiskLun::SetFlags(ulong)

- ea: `0x14004a370`
- end: `0x14004a63f`
- name: `?SetFlags@CVdsDiskLun@@UEAAJK@Z`
- size: `719`
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
- `0x14004a370`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004a5ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004a5ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004a3f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004a3f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004a585`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004a59c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004a5b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004a5ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004a5e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004a585`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004a59c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004a5b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004a5ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004a5e1`
- `vdsutil!VdsTraceEx` at `0x14004a416`
- `vdsutil!VdsTraceEx` at `0x14004a45e`
- `vdsutil!VdsTraceEx` at `0x14004a4ce`
- `vdsutil!VdsTraceEx` at `0x14004a51c`
- `vdsutil!VdsTraceEx` at `0x14004a56c`
- `vdsutil!VdsTraceEx` at `0x14004a416`
- `vdsutil!VdsTraceEx` at `0x14004a45e`
- `vdsutil!VdsTraceEx` at `0x14004a4ce`
- `vdsutil!VdsTraceEx` at `0x14004a51c`
- `vdsutil!VdsTraceEx` at `0x14004a56c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004a3b0`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004a3b0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004a614`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004a614`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::SetFlags(CVdsDiskLun *this, unsigned int a2)
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

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v14, 0x5Eu, "CVdsDiskLun::SetFlags");
  memset_0(v15, 0, 0x80u);
  v12 = 0;
  v13 = 0;
  v4 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v12);
  if ( v4 < 0 )
    goto LABEL_43;
  v5 = 0;
  EnterCriticalSection(&g_GlobalCriticalSection);
  v6 = CVdsDiskLun::ValidateDiskInterfaces(this);
  v4 = v6;
  if ( v6 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsDiskLun::SetFlags, 1, hr=%lX", v6);
    if ( v4 == -2147212283 )
      v4 = -2147212277;
    goto LABEL_29;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 28) + 24LL))(*((_QWORD *)this + 28), v15);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = "CVdsDiskLun::SetFlags, 2, hr=%lX";
LABEL_7:
    VdsTraceEx(94, 0, v8, (unsigned int)v7);
    goto LABEL_29;
  }
  if ( (v16 & 0x100) != 0 )
  {
    v4 = -2147211257;
    VdsTraceEx(94, 0, "CVdsDiskLun::SetFlags, 3, hr=%lX", 2147756039LL);
  }
  else if ( (v16 & 0x80u) == 0 )
  {
    if ( (v16 & 0x4000) != 0 )
    {
      v4 = -2147211247;
      VdsTraceEx(94, 0, "CVdsDiskLun::SetFlags, 3.75, boot from disk, hr=%lX", 2147756049LL);
    }
    else
    {
      if ( (v16 & 0x200) != 0 )
      {
        v4 = -2147211252;
        VdsTraceEx(94, 1, "CVdsDiskLun::SetFlags, 4, hr=%lX", 2147756044LL);
        goto LABEL_29;
      }
      if ( (v16 & 0x400) != 0 )
      {
        v4 = -2147211251;
        VdsTraceEx(94, 1, "CVdsDiskLun::SetFlags, 5, hr=%lX", 2147756045LL);
      }
      else
      {
        if ( (v16 & 0x800) == 0 )
        {
          v9 = CVdsDiskLun::DismountDiskVolumes(this);
          if ( v9 < 0 )
          {
            VdsTraceEx(94, 0, "CVdsDiskLun::SetFlags, 7, hr=%lX", v9);
            v5 = 272393;
          }
          v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 28) + 64LL))(*((_QWORD *)this + 28), a2);
          v4 = v7;
          if ( v7 >= 0 )
          {
            v10 = CVdsDiskLun::RemountDiskVolumes(this);
            v4 = v10;
            if ( v10 < 0 )
            {
              VdsTraceEx(94, 0, "CVdsDiskLun::SetFlags, 9, hr=%lX", v10);
              if ( !v5 )
                v5 = 272392;
            }
            goto LABEL_29;
          }
          v8 = "CVdsDiskLun::SetFlags, 8, hr=%lX";
          goto LABEL_7;
        }
        v4 = -2147211250;
        VdsTraceEx(94, 1, "CVdsDiskLun::SetFlags, 6, hr=%lX", 2147756046LL);
      }
    }
  }
  else
  {
    v4 = -2147211247;
    VdsTraceEx(94, 0, "CVdsDiskLun::SetFlags, 3.5, system disk, hr=%lX", 2147756049LL);
  }
LABEL_29:
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
LABEL_43:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v12);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14004a370  mov     [rsp-8+arg_10], rbx
0x14004a375  push    rbp
0x14004a376  push    rsi
0x14004a377  push    rdi
0x14004a378  push    r12
0x14004a37a  push    r14
0x14004a37c  lea     rbp, [rsp-37h]
0x14004a381  sub     rsp, 0D0h
0x14004a388  mov     rax, cs:__security_cookie
0x14004a38f  xor     rax, rsp
0x14004a392  mov     [rbp+57h+var_28], rax
0x14004a396  mov     r14d, edx
0x14004a399  mov     rsi, rcx
0x14004a39c  lea     r8, aCvdsdisklunSet_23; "CVdsDiskLun::SetFlags"
0x14004a3a3  mov     r12d, 5Eh ; '^'
0x14004a3a9  mov     edx, r12d
0x14004a3ac  lea     rcx, [rbp+57h+var_C0]
0x14004a3b0  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14004a3b6  nop
0x14004a3b7  xor     edx, edx; Val
0x14004a3b9  lea     r8d, [r12+22h]; Size
0x14004a3be  lea     rcx, [rbp+57h+var_B0]; void *
0x14004a3c2  call    memset_0
0x14004a3c7  mov     [rbp+57h+var_D0], 0
0x14004a3cf  mov     [rbp+57h+var_C8], 0
0x14004a3d6  lea     rcx, [rbp+57h+var_D0]; this
0x14004a3da  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x14004a3df  mov     ebx, eax
0x14004a3e1  test    eax, eax
0x14004a3e3  js      loc_14004A606
0x14004a3e9  xor     edi, edi
0x14004a3eb  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004a3f2  call    cs:__imp_EnterCriticalSection
0x14004a3f8  nop
0x14004a3f9  mov     rcx, rsi; this
0x14004a3fc  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x14004a401  mov     ebx, eax
0x14004a403  test    eax, eax
0x14004a405  jns     short loc_14004A432
0x14004a407  mov     r9d, eax
0x14004a40a  lea     r8, aCvdsdisklunSet_34; "CVdsDiskLun::SetFlags, 1, hr=%lX"
0x14004a411  xor     edx, edx
0x14004a413  mov     ecx, r12d
0x14004a416  call    cs:__imp_VdsTraceEx
0x14004a41c  cmp     ebx, 80042405h
0x14004a422  jnz     loc_14004A57C
0x14004a428  mov     ebx, 8004240Bh
0x14004a42d  jmp     loc_14004A57C
0x14004a432  mov     rcx, [rsi+0E0h]
0x14004a439  mov     rax, [rcx]
0x14004a43c  lea     rdx, [rbp+57h+var_B0]
0x14004a440  mov     rax, [rax+18h]
0x14004a444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a449  mov     ebx, eax
0x14004a44b  test    eax, eax
0x14004a44d  jns     short loc_14004A469
0x14004a44f  lea     r8, aCvdsdisklunSet_35; "CVdsDiskLun::SetFlags, 2, hr=%lX"
0x14004a456  mov     r9d, eax
0x14004a459  xor     edx, edx
0x14004a45b  mov     ecx, r12d
0x14004a45e  call    cs:__imp_VdsTraceEx
0x14004a464  jmp     loc_14004A57C
0x14004a469  mov     eax, [rbp+57h+var_74]
0x14004a46c  bt      eax, 8
0x14004a470  jnb     short loc_14004A483
0x14004a472  mov     ebx, 80042807h
0x14004a477  mov     r9d, ebx
0x14004a47a  lea     r8, aCvdsdisklunSet_10; "CVdsDiskLun::SetFlags, 3, hr=%lX"
0x14004a481  jmp     short loc_14004A459
0x14004a483  test    al, al
0x14004a485  jns     short loc_14004A499
0x14004a487  mov     r9d, 80042811h
0x14004a48d  mov     ebx, r9d
0x14004a490  lea     r8, aCvdsdisklunSet_37; "CVdsDiskLun::SetFlags, 3.5, system disk"...
0x14004a497  jmp     short loc_14004A459
0x14004a499  bt      eax, 0Eh
0x14004a49d  jnb     short loc_14004A4B1
0x14004a49f  mov     r9d, 80042811h
0x14004a4a5  mov     ebx, r9d
0x14004a4a8  lea     r8, aCvdsdisklunSet_20; "CVdsDiskLun::SetFlags, 3.75, boot from "...
0x14004a4af  jmp     short loc_14004A459
0x14004a4b1  bt      eax, 9
0x14004a4b5  jnb     short loc_14004A4D9
0x14004a4b7  mov     ebx, 8004280Ch
0x14004a4bc  lea     r8, aCvdsdisklunSet_19; "CVdsDiskLun::SetFlags, 4, hr=%lX"
0x14004a4c3  mov     r9d, ebx
0x14004a4c6  mov     edx, 1
0x14004a4cb  mov     ecx, r12d
0x14004a4ce  call    cs:__imp_VdsTraceEx
0x14004a4d4  jmp     loc_14004A57C
0x14004a4d9  bt      eax, 0Ah
0x14004a4dd  jnb     short loc_14004A4ED
0x14004a4df  mov     ebx, 8004280Dh
0x14004a4e4  lea     r8, aCvdsdisklunSet_29; "CVdsDiskLun::SetFlags, 5, hr=%lX"
0x14004a4eb  jmp     short loc_14004A4C3
0x14004a4ed  bt      eax, 0Bh
0x14004a4f1  jnb     short loc_14004A501
0x14004a4f3  mov     ebx, 8004280Eh
0x14004a4f8  lea     r8, aCvdsdisklunSet_6; "CVdsDiskLun::SetFlags, 6, hr=%lX"
0x14004a4ff  jmp     short loc_14004A4C3
0x14004a501  mov     rcx, rsi; this
0x14004a504  call    ?DismountDiskVolumes@CVdsDiskLun@@QEAAJXZ; CVdsDiskLun::DismountDiskVolumes(void)
0x14004a509  test    eax, eax
0x14004a50b  jns     short loc_14004A527
0x14004a50d  mov     r9d, eax
0x14004a510  lea     r8, aCvdsdisklunSet_31; "CVdsDiskLun::SetFlags, 7, hr=%lX"
0x14004a517  xor     edx, edx
0x14004a519  mov     ecx, r12d
0x14004a51c  call    cs:__imp_VdsTraceEx
0x14004a522  mov     edi, 42809h
0x14004a527  mov     rcx, [rsi+0E0h]
0x14004a52e  mov     rax, [rcx]
0x14004a531  mov     edx, r14d
0x14004a534  mov     rax, [rax+40h]
0x14004a538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a53d  mov     ebx, eax
0x14004a53f  test    eax, eax
0x14004a541  jns     short loc_14004A54F
0x14004a543  lea     r8, aCvdsdisklunSet_32; "CVdsDiskLun::SetFlags, 8, hr=%lX"
0x14004a54a  jmp     loc_14004A456
0x14004a54f  mov     rcx, rsi; this
0x14004a552  call    ?RemountDiskVolumes@CVdsDiskLun@@QEAAJXZ; CVdsDiskLun::RemountDiskVolumes(void)
0x14004a557  mov     ebx, eax
0x14004a559  test    eax, eax
0x14004a55b  jns     short loc_14004A57C
0x14004a55d  mov     r9d, eax
0x14004a560  lea     r8, aCvdsdisklunSet_46; "CVdsDiskLun::SetFlags, 9, hr=%lX"
0x14004a567  xor     edx, edx
0x14004a569  mov     ecx, r12d
0x14004a56c  call    cs:__imp_VdsTraceEx
0x14004a572  mov     eax, 42808h
0x14004a577  test    edi, edi
0x14004a579  cmovz   edi, eax
0x14004a57c  mov     rcx, [rbp+57h+pv]; pv
0x14004a580  test    rcx, rcx
0x14004a583  jz      short loc_14004A593
0x14004a585  call    cs:__imp_CoTaskMemFree
0x14004a58b  mov     [rbp+57h+pv], 0
0x14004a593  mov     rcx, [rbp+57h+var_50]; pv
0x14004a597  test    rcx, rcx
0x14004a59a  jz      short loc_14004A5AA
0x14004a59c  call    cs:__imp_CoTaskMemFree
0x14004a5a2  mov     [rbp+57h+var_50], 0
0x14004a5aa  mov     rcx, [rbp+57h+var_48]; pv
0x14004a5ae  test    rcx, rcx
0x14004a5b1  jz      short loc_14004A5C1
0x14004a5b3  call    cs:__imp_CoTaskMemFree
0x14004a5b9  mov     [rbp+57h+var_48], 0
0x14004a5c1  mov     rcx, [rbp+57h+var_40]; pv
0x14004a5c5  test    rcx, rcx
0x14004a5c8  jz      short loc_14004A5D8
0x14004a5ca  call    cs:__imp_CoTaskMemFree
0x14004a5d0  mov     [rbp+57h+var_40], 0
0x14004a5d8  mov     rcx, [rbp+57h+var_38]; pv
0x14004a5dc  test    rcx, rcx
0x14004a5df  jz      short loc_14004A5EF
0x14004a5e1  call    cs:__imp_CoTaskMemFree
0x14004a5e7  mov     [rbp+57h+var_38], 0
0x14004a5ef  test    ebx, ebx
0x14004a5f1  jnz     short loc_14004A5F8
0x14004a5f3  test    edi, edi
0x14004a5f5  cmovnz  ebx, edi
0x14004a5f8  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004a5ff  call    cs:__imp_LeaveCriticalSection
0x14004a605  nop
0x14004a606  lea     rcx, [rbp+57h+var_D0]; this
0x14004a60a  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14004a60f  nop
0x14004a610  lea     rcx, [rbp+57h+var_C0]
0x14004a614  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004a61a  mov     eax, ebx
0x14004a61c  mov     rcx, [rbp+57h+var_28]
0x14004a620  xor     rcx, rsp; StackCookie
0x14004a623  call    __security_check_cookie
0x14004a628  mov     rbx, [rsp+0F0h+arg_10]
0x14004a630  add     rsp, 0D0h
0x14004a637  pop     r14
0x14004a639  pop     r12
0x14004a63b  pop     rdi
0x14004a63c  pop     rsi
0x14004a63d  pop     rbp
0x14004a63e  retn
```
