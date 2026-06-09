# CVdsDiskLun::GetDiskIdentificationData(_VDS_LUN_INFORMATION *)

- ea: `0x140046130`
- end: `0x140046385`
- name: `?GetDiskIdentificationData@CVdsDiskLun@@UEAAJPEAU_VDS_LUN_INFORMATION@@@Z`
- size: `597`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this, struct _VDS_LUN_INFORMATION *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x140025e20`
- `0x14002e123`
- `0x140046130`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140046342`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140046342`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400461dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400461dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400462d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400462e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400462ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140046316`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004632d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400462d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400462e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400462ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140046316`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004632d`
- `vdsutil!VdsTraceEx` at `0x140046201`
- `vdsutil!VdsTraceEx` at `0x14004624a`
- `vdsutil!VdsTraceEx` at `0x140046270`
- `vdsutil!VdsTraceEx` at `0x140046201`
- `vdsutil!VdsTraceEx` at `0x14004624a`
- `vdsutil!VdsTraceEx` at `0x140046270`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140046173`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140046173`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140046359`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140046359`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::GetDiskIdentificationData(CVdsDiskLun *this, struct _VDS_LUN_INFORMATION *a2)
{
  signed int v4; // ebx
  int v5; // eax
  int v6; // eax
  int LunInformationForDisk; // eax
  unsigned int v9; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v10; // [rsp+28h] [rbp-D8h] BYREF
  int v11; // [rsp+30h] [rbp-D0h]
  _BYTE v12[24]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[16]; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+60h] [rbp-A0h]
  LPVOID v15; // [rsp+A8h] [rbp-58h]
  LPVOID pv; // [rsp+B0h] [rbp-50h]
  LPVOID v17; // [rsp+B8h] [rbp-48h]
  LPVOID v18; // [rsp+C0h] [rbp-40h]
  LPCWSTR lpFileName; // [rsp+C8h] [rbp-38h]
  struct _VDS_LUN_INFORMATION v20; // [rsp+D0h] [rbp-30h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v12, 0x5Eu, "CVdsDiskLun::GetIdentificationData");
  memset_0(&v20, 0, sizeof(v20));
  v9 = 999999;
  memset_0(v13, 0, 0x80u);
  memset_0(a2, 0, sizeof(struct _VDS_LUN_INFORMATION));
  v10 = 0;
  v11 = 0;
  v4 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v10);
  if ( v4 >= 0 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    v5 = CVdsDiskLun::ValidateDiskInterfaces(this);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 28) + 24LL))(*((_QWORD *)this + 28), v13);
      v4 = v6;
      if ( v6 >= 0 )
      {
        if ( v14 == 6 )
        {
          v4 = -2147212204;
          VdsTraceEx(94, 2, "CVdsDiskLun::GetIdentificationData, 2.1, hr=%lX", -2147212204);
        }
        else
        {
          LunInformationForDisk = CVdsService::GetLunInformationForDisk(lpFileName, &v20, &v9);
          v4 = LunInformationForDisk;
          if ( LunInformationForDisk >= 0 )
            *a2 = v20;
          else
            VdsTraceEx(94, 0, "CVdsDiskLun::GetIdentificationData, 3, hr=%lX", (unsigned int)LunInformationForDisk);
        }
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsDiskLun::GetIdentificationData, 2, hr=%lX", (unsigned int)v6);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::GetIdentificationData, 1, hr=%lX", v5);
      if ( v4 == -2147212283 )
        v4 = -2147212277;
    }
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
    if ( lpFileName )
    {
      CoTaskMemFree((LPVOID)lpFileName);
      lpFileName = 0;
    }
    LeaveCriticalSection(&g_GlobalCriticalSection);
  }
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v10);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140046130  mov     [rsp-8+arg_10], rbx
0x140046135  mov     [rsp-8+arg_18], rsi
0x14004613a  push    rbp
0x14004613b  push    rdi
0x14004613c  push    r15
0x14004613e  lea     rbp, [rsp-40h]
0x140046143  sub     rsp, 140h
0x14004614a  mov     rax, cs:__security_cookie
0x140046151  xor     rax, rsp
0x140046154  mov     [rbp+50h+var_18], rax
0x140046158  mov     rdi, rdx
0x14004615b  mov     rsi, rcx
0x14004615e  lea     r8, aCvdsdisklunGet_20; "CVdsDiskLun::GetIdentificationData"
0x140046165  mov     r15d, 5Eh ; '^'
0x14004616b  mov     edx, r15d
0x14004616e  lea     rcx, [rsp+150h+var_118]
0x140046173  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140046179  nop
0x14004617a  lea     ebx, [r15+2]
0x14004617e  mov     r8d, ebx; Size
0x140046181  xor     edx, edx; Val
0x140046183  lea     rcx, [rbp+50h+var_80]; void *
0x140046187  call    memset_0
0x14004618c  mov     [rsp+150h+var_130], 0F423Fh
0x140046194  xor     edx, edx; Val
0x140046196  lea     r8d, [r15+22h]; Size
0x14004619a  lea     rcx, [rsp+150h+var_100]; void *
0x14004619f  call    memset_0
0x1400461a4  mov     r8d, ebx; Size
0x1400461a7  xor     edx, edx; Val
0x1400461a9  mov     rcx, rdi; void *
0x1400461ac  call    memset_0
0x1400461b1  mov     [rsp+150h+var_128], 0
0x1400461ba  mov     [rsp+150h+var_120], 0
0x1400461c2  lea     rcx, [rsp+150h+var_128]; this
0x1400461c7  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x1400461cc  mov     ebx, eax
0x1400461ce  test    eax, eax
0x1400461d0  js      loc_140046349
0x1400461d6  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400461dd  call    cs:__imp_EnterCriticalSection
0x1400461e3  nop
0x1400461e4  mov     rcx, rsi; this
0x1400461e7  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x1400461ec  mov     ebx, eax
0x1400461ee  test    eax, eax
0x1400461f0  jns     short loc_14004621D
0x1400461f2  mov     r9d, eax
0x1400461f5  lea     r8, aCvdsdisklunGet_137; "CVdsDiskLun::GetIdentificationData, 1, "...
0x1400461fc  xor     edx, edx
0x1400461fe  mov     ecx, r15d
0x140046201  call    cs:__imp_VdsTraceEx
0x140046207  cmp     ebx, 80042405h
0x14004620d  jnz     loc_1400462C8
0x140046213  mov     ebx, 8004240Bh
0x140046218  jmp     loc_1400462C8
0x14004621d  mov     rcx, [rsi+0E0h]
0x140046224  mov     rax, [rcx]
0x140046227  lea     rdx, [rsp+150h+var_100]
0x14004622c  mov     rax, [rax+18h]
0x140046230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046235  mov     ebx, eax
0x140046237  test    eax, eax
0x140046239  jns     short loc_140046252
0x14004623b  lea     r8, aCvdsdisklunGet_83; "CVdsDiskLun::GetIdentificationData, 2, "...
0x140046242  mov     r9d, eax
0x140046245  xor     edx, edx
0x140046247  mov     ecx, r15d
0x14004624a  call    cs:__imp_VdsTraceEx
0x140046250  jmp     short loc_1400462C8
0x140046252  cmp     [rsp+150h+var_F0], 6
0x140046257  jnz     short loc_140046278
0x140046259  mov     ebx, 80042454h
0x14004625e  mov     r9d, ebx
0x140046261  lea     r8, aCvdsdisklunGet_51; "CVdsDiskLun::GetIdentificationData, 2.1"...
0x140046268  mov     edx, 2
0x14004626d  mov     ecx, r15d
0x140046270  call    cs:__imp_VdsTraceEx
0x140046276  jmp     short loc_1400462C8
0x140046278  lea     r8, [rsp+150h+var_130]; unsigned int *
0x14004627d  lea     rdx, [rbp+50h+var_80]; struct _VDS_LUN_INFORMATION *
0x140046281  mov     rcx, [rbp+50h+lpFileName]; lpFileName
0x140046285  call    ?GetLunInformationForDisk@CVdsService@@SAJPEBGPEAU_VDS_LUN_INFORMATION@@PEAK@Z; CVdsService::GetLunInformationForDisk(ushort const *,_VDS_LUN_INFORMATION *,ulong *)
0x14004628a  mov     ebx, eax
0x14004628c  test    eax, eax
0x14004628e  jns     short loc_140046299
0x140046290  lea     r8, aCvdsdisklunGet_26; "CVdsDiskLun::GetIdentificationData, 3, "...
0x140046297  jmp     short loc_140046242
0x140046299  movaps  xmm0, xmmword ptr [rbp+50h+var_80.m_version]
0x14004629d  movups  xmmword ptr [rdi], xmm0
0x1400462a0  movaps  xmm1, xmmword ptr [rbp+50h+var_80.m_szVendorId]
0x1400462a4  movups  xmmword ptr [rdi+10h], xmm1
0x1400462a8  movaps  xmm0, xmmword ptr [rbp+50h+var_80.m_szProductRevision]
0x1400462ac  movups  xmmword ptr [rdi+20h], xmm0
0x1400462b0  movaps  xmm1, xmmword ptr [rbp+50h+var_80.m_diskSignature.Data1]
0x1400462b4  movups  xmmword ptr [rdi+30h], xmm1
0x1400462b8  movaps  xmm0, xmmword ptr [rbp+50h+var_80.m_deviceIdDescriptor.m_version]
0x1400462bc  movups  xmmword ptr [rdi+40h], xmm0
0x1400462c0  movaps  xmm1, xmmword ptr [rbp+50h+var_80.m_cInterconnects]
0x1400462c4  movups  xmmword ptr [rdi+50h], xmm1
0x1400462c8  mov     rcx, [rbp+50h+pv]; pv
0x1400462cc  test    rcx, rcx
0x1400462cf  jz      short loc_1400462DF
0x1400462d1  call    cs:__imp_CoTaskMemFree
0x1400462d7  mov     [rbp+50h+pv], 0
0x1400462df  mov     rcx, [rbp+50h+var_98]; pv
0x1400462e3  test    rcx, rcx
0x1400462e6  jz      short loc_1400462F6
0x1400462e8  call    cs:__imp_CoTaskMemFree
0x1400462ee  mov     [rbp+50h+var_98], 0
0x1400462f6  mov     rcx, [rbp+50h+var_A8]; pv
0x1400462fa  test    rcx, rcx
0x1400462fd  jz      short loc_14004630D
0x1400462ff  call    cs:__imp_CoTaskMemFree
0x140046305  mov     [rbp+50h+var_A8], 0
0x14004630d  mov     rcx, [rbp+50h+var_90]; pv
0x140046311  test    rcx, rcx
0x140046314  jz      short loc_140046324
0x140046316  call    cs:__imp_CoTaskMemFree
0x14004631c  mov     [rbp+50h+var_90], 0
0x140046324  mov     rcx, [rbp+50h+lpFileName]; pv
0x140046328  test    rcx, rcx
0x14004632b  jz      short loc_14004633B
0x14004632d  call    cs:__imp_CoTaskMemFree
0x140046333  mov     [rbp+50h+lpFileName], 0
0x14004633b  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140046342  call    cs:__imp_LeaveCriticalSection
0x140046348  nop
0x140046349  lea     rcx, [rsp+150h+var_128]; this
0x14004634e  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140046353  nop
0x140046354  lea     rcx, [rsp+150h+var_118]
0x140046359  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004635f  mov     eax, ebx
0x140046361  mov     rcx, [rbp+50h+var_18]
0x140046365  xor     rcx, rsp; StackCookie
0x140046368  call    __security_check_cookie
0x14004636d  lea     r11, [rsp+150h+var_10]
0x140046375  mov     rbx, [r11+30h]
0x140046379  mov     rsi, [r11+38h]
0x14004637d  mov     rsp, r11
0x140046380  pop     r15
0x140046382  pop     rdi
0x140046383  pop     rbp
0x140046384  retn
```
