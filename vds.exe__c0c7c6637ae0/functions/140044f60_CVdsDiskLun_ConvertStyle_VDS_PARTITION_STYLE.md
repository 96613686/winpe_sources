# CVdsDiskLun::ConvertStyle(_VDS_PARTITION_STYLE)

- ea: `0x140044f60`
- end: `0x1400451c0`
- name: `?ConvertStyle@CVdsDiskLun@@UEAAJW4_VDS_PARTITION_STYLE@@@Z`
- size: `608`
- prototype: `__int64 __fastcall(CVdsDiskLun *this, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x14002e123`
- `0x140044f60`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004517f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004517f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140044fe0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140044fe0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004510e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004513c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045153`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004516a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004510e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004513c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045153`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004516a`
- `vdsutil!VdsTraceEx` at `0x140045004`
- `vdsutil!VdsTraceEx` at `0x140045064`
- `vdsutil!VdsTraceEx` at `0x1400450cd`
- `vdsutil!VdsTraceEx` at `0x1400450ff`
- `vdsutil!VdsTraceEx` at `0x140045004`
- `vdsutil!VdsTraceEx` at `0x140045064`
- `vdsutil!VdsTraceEx` at `0x1400450cd`
- `vdsutil!VdsTraceEx` at `0x1400450ff`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140044fa1`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140044fa1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140045194`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140045194`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::ConvertStyle(CVdsDiskLun *this, unsigned int a2)
{
  signed int v4; // ebx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  __int64 v9; // [rsp+20h] [rbp-69h] BYREF
  int v10; // [rsp+28h] [rbp-61h]
  _BYTE v11[16]; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v12[16]; // [rsp+40h] [rbp-49h] BYREF
  int v13; // [rsp+50h] [rbp-39h]
  int v14; // [rsp+7Ch] [rbp-Dh]
  LPVOID v15; // [rsp+98h] [rbp+Fh]
  LPVOID pv; // [rsp+A0h] [rbp+17h]
  LPVOID v17; // [rsp+A8h] [rbp+1Fh]
  LPVOID v18; // [rsp+B0h] [rbp+27h]
  LPVOID v19; // [rsp+B8h] [rbp+2Fh]

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v11, 0x5Eu, "CVdsDiskLun::ConvertStyle()");
  memset_0(v12, 0, 0x80u);
  v9 = 0;
  v10 = 0;
  v4 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v9);
  if ( v4 < 0 )
    goto LABEL_34;
  EnterCriticalSection(&g_GlobalCriticalSection);
  v5 = CVdsDiskLun::ValidateDiskInterfaces(this);
  v4 = v5;
  if ( v5 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsDiskLun::ConvertStyle, 1, hr=%lX", v5);
    if ( v4 == -2147212283 )
      v4 = -2147212277;
    goto LABEL_23;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 28) + 24LL))(*((_QWORD *)this + 28), v12);
  v4 = v6;
  if ( v6 >= 0 )
  {
    if ( (v14 & 0x40) != 0 )
    {
      v4 = -2147211253;
      VdsTraceEx(94, 2, "CVdsDiskLun::ConvertStyle, 2.1, NOT CONVERTABLE");
      goto LABEL_23;
    }
    if ( (v14 & 0x200) != 0 )
    {
      v4 = -2147211252;
    }
    else
    {
      if ( (v14 & 0x400) != 0 )
      {
        v4 = -2147211251;
        VdsTraceEx(94, 2, "CVdsDiskLun::ConvertStyle, 2.3, NOT CONVERTABLE");
        goto LABEL_23;
      }
      if ( (v14 & 0x800) != 0 )
      {
        v4 = -2147211250;
        VdsTraceEx(94, 2, "CVdsDiskLun::ConvertStyle, 2.4, NOT CONVERTABLE");
        goto LABEL_23;
      }
      if ( v13 != 4 )
      {
        if ( (v14 & 0x10) != 0 )
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 28) + 56LL))(*((_QWORD *)this + 28), a2);
          v4 = v7;
          if ( v7 < 0 )
            VdsTraceEx(94, 0, "CVdsDiskLun::ConvertStyle, 4, hr=%lX", (unsigned int)v7);
        }
        else
        {
          v4 = -2147211943;
          VdsTraceEx(94, 0, "CVdsDiskLun::ConvertStyle, 3.2, NOT CONVERTABLE");
        }
        goto LABEL_23;
      }
      v4 = -2147211254;
    }
    VdsTraceEx(94, 2, "CVdsDiskLun::ConvertStyle, 2.2, NOT CONVERTABLE");
  }
  else
  {
    VdsTraceEx(94, 0, "CVdsDiskLun::ConvertStyle, 2, hr=%lX", (unsigned int)v6);
  }
LABEL_23:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v17 )
  {
    CoTaskMemFree(v17);
    v17 = 0;
  }
  if ( v19 )
  {
    CoTaskMemFree(v19);
    v19 = 0;
  }
  if ( v15 )
  {
    CoTaskMemFree(v15);
    v15 = 0;
  }
  if ( v18 )
  {
    CoTaskMemFree(v18);
    v18 = 0;
  }
  LeaveCriticalSection(&g_GlobalCriticalSection);
LABEL_34:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v9);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140044f60  mov     [rsp-8+arg_10], rbx
0x140044f65  mov     [rsp-8+arg_18], rsi
0x140044f6a  push    rbp
0x140044f6b  push    rdi
0x140044f6c  push    r15
0x140044f6e  lea     rbp, [rsp-47h]
0x140044f73  sub     rsp, 0D0h
0x140044f7a  mov     rax, cs:__security_cookie
0x140044f81  xor     rax, rsp
0x140044f84  mov     [rbp+57h+var_18], rax
0x140044f88  mov     esi, edx
0x140044f8a  mov     rdi, rcx
0x140044f8d  lea     r8, aCvdsdisklunCon_5; "CVdsDiskLun::ConvertStyle()"
0x140044f94  mov     r15d, 5Eh ; '^'
0x140044f9a  mov     edx, r15d
0x140044f9d  lea     rcx, [rbp+57h+var_B0]
0x140044fa1  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140044fa7  nop
0x140044fa8  xor     edx, edx; Val
0x140044faa  lea     r8d, [r15+22h]; Size
0x140044fae  lea     rcx, [rbp+57h+var_A0]; void *
0x140044fb2  call    memset_0
0x140044fb7  mov     [rbp+57h+var_C0], 0
0x140044fbf  mov     [rbp+57h+var_B8], 0
0x140044fc6  lea     rcx, [rbp+57h+var_C0]; this
0x140044fca  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140044fcf  mov     ebx, eax
0x140044fd1  test    eax, eax
0x140044fd3  js      loc_140045186
0x140044fd9  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140044fe0  call    cs:__imp_EnterCriticalSection
0x140044fe6  nop
0x140044fe7  mov     rcx, rdi; this
0x140044fea  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140044fef  mov     ebx, eax
0x140044ff1  test    eax, eax
0x140044ff3  jns     short loc_140045020
0x140044ff5  mov     r9d, eax
0x140044ff8  lea     r8, aCvdsdisklunCon_7; "CVdsDiskLun::ConvertStyle, 1, hr=%lX"
0x140044fff  xor     edx, edx
0x140045001  mov     ecx, r15d
0x140045004  call    cs:__imp_VdsTraceEx
0x14004500a  cmp     ebx, 80042405h
0x140045010  jnz     loc_140045105
0x140045016  mov     ebx, 8004240Bh
0x14004501b  jmp     loc_140045105
0x140045020  mov     rcx, [rdi+0E0h]
0x140045027  mov     rax, [rcx]
0x14004502a  lea     rdx, [rbp+57h+var_A0]
0x14004502e  mov     rax, [rax+18h]
0x140045032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045037  mov     ebx, eax
0x140045039  test    eax, eax
0x14004503b  jns     short loc_140045049
0x14004503d  lea     r8, aCvdsdisklunCon_6; "CVdsDiskLun::ConvertStyle, 2, hr=%lX"
0x140045044  jmp     loc_1400450F7
0x140045049  mov     eax, [rbp+57h+var_64]
0x14004504c  test    al, 40h
0x14004504e  jz      short loc_14004506F
0x140045050  mov     ebx, 8004280Bh
0x140045055  lea     r8, aCvdsdisklunCon_3; "CVdsDiskLun::ConvertStyle, 2.1, NOT CON"...
0x14004505c  mov     edx, 2
0x140045061  mov     ecx, r15d
0x140045064  call    cs:__imp_VdsTraceEx
0x14004506a  jmp     loc_140045105
0x14004506f  bt      eax, 9
0x140045073  jnb     short loc_140045083
0x140045075  mov     ebx, 8004280Ch
0x14004507a  lea     r8, aCvdsdisklunCon_4; "CVdsDiskLun::ConvertStyle, 2.2, NOT CON"...
0x140045081  jmp     short loc_14004505C
0x140045083  bt      eax, 0Ah
0x140045087  jnb     short loc_140045097
0x140045089  mov     ebx, 8004280Dh
0x14004508e  lea     r8, aCvdsdisklunCon_2; "CVdsDiskLun::ConvertStyle, 2.3, NOT CON"...
0x140045095  jmp     short loc_14004505C
0x140045097  bt      eax, 0Bh
0x14004509b  jnb     short loc_1400450AB
0x14004509d  mov     ebx, 8004280Eh
0x1400450a2  lea     r8, aCvdsdisklunCon_1; "CVdsDiskLun::ConvertStyle, 2.4, NOT CON"...
0x1400450a9  jmp     short loc_14004505C
0x1400450ab  cmp     [rbp+57h+var_90], 4
0x1400450af  jnz     short loc_1400450B8
0x1400450b1  mov     ebx, 8004280Ah
0x1400450b6  jmp     short loc_14004507A
0x1400450b8  test    al, 10h
0x1400450ba  jnz     short loc_1400450D5
0x1400450bc  mov     ebx, 80042559h
0x1400450c1  lea     r8, aCvdsdisklunCon_0; "CVdsDiskLun::ConvertStyle, 3.2, NOT CON"...
0x1400450c8  xor     edx, edx
0x1400450ca  mov     ecx, r15d
0x1400450cd  call    cs:__imp_VdsTraceEx
0x1400450d3  jmp     short loc_140045105
0x1400450d5  mov     rcx, [rdi+0E0h]
0x1400450dc  mov     rax, [rcx]
0x1400450df  mov     edx, esi
0x1400450e1  mov     rax, [rax+38h]
0x1400450e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400450ea  mov     ebx, eax
0x1400450ec  test    eax, eax
0x1400450ee  jns     short loc_140045105
0x1400450f0  lea     r8, aCvdsdisklunCon; "CVdsDiskLun::ConvertStyle, 4, hr=%lX"
0x1400450f7  mov     r9d, eax
0x1400450fa  xor     edx, edx
0x1400450fc  mov     ecx, r15d
0x1400450ff  call    cs:__imp_VdsTraceEx
0x140045105  mov     rcx, [rbp+57h+pv]; pv
0x140045109  test    rcx, rcx
0x14004510c  jz      short loc_14004511C
0x14004510e  call    cs:__imp_CoTaskMemFree
0x140045114  mov     [rbp+57h+pv], 0
0x14004511c  mov     rcx, [rbp+57h+var_38]; pv
0x140045120  test    rcx, rcx
0x140045123  jz      short loc_140045133
0x140045125  call    cs:__imp_CoTaskMemFree
0x14004512b  mov     [rbp+57h+var_38], 0
0x140045133  mov     rcx, [rbp+57h+var_28]; pv
0x140045137  test    rcx, rcx
0x14004513a  jz      short loc_14004514A
0x14004513c  call    cs:__imp_CoTaskMemFree
0x140045142  mov     [rbp+57h+var_28], 0
0x14004514a  mov     rcx, [rbp+57h+var_48]; pv
0x14004514e  test    rcx, rcx
0x140045151  jz      short loc_140045161
0x140045153  call    cs:__imp_CoTaskMemFree
0x140045159  mov     [rbp+57h+var_48], 0
0x140045161  mov     rcx, [rbp+57h+var_30]; pv
0x140045165  test    rcx, rcx
0x140045168  jz      short loc_140045178
0x14004516a  call    cs:__imp_CoTaskMemFree
0x140045170  mov     [rbp+57h+var_30], 0
0x140045178  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004517f  call    cs:__imp_LeaveCriticalSection
0x140045185  nop
0x140045186  lea     rcx, [rbp+57h+var_C0]; this
0x14004518a  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14004518f  nop
0x140045190  lea     rcx, [rbp+57h+var_B0]
0x140045194  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004519a  mov     eax, ebx
0x14004519c  mov     rcx, [rbp+57h+var_18]
0x1400451a0  xor     rcx, rsp; StackCookie
0x1400451a3  call    __security_check_cookie
0x1400451a8  lea     r11, [rsp+0E0h+var_10]
0x1400451b0  mov     rbx, [r11+30h]
0x1400451b4  mov     rsi, [r11+38h]
0x1400451b8  mov     rsp, r11
0x1400451bb  pop     r15
0x1400451bd  pop     rdi
0x1400451be  pop     rbp
0x1400451bf  retn
```
