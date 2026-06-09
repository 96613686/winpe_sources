# CVdsVolume::GetVolumeName(ushort * const,int *,int,ulong,ushort *)

- ea: `0x140004460`
- end: `0x1400048be`
- name: `?GetVolumeName@CVdsVolume@@AEAAJQEAGPEAHHKPEAG@Z`
- size: `1118`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, unsigned __int16 *const, int *, int, unsigned int, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400037a0`
- `0x140015944`
- `0x140015b98`
- `0x14001fe40`
- `0x140022e80`
- `0x140041710`

## callees

- `0x140004460`
- `0x140006e60`
- `0x140013298`
- `0x1400427c4`
- `0x140052e52`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004550`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004586`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400045e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000460b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400046bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004740`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400047b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400047fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000487a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004550`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004586`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400045e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000460b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400046bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004740`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400047b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400047fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000487a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000467e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000467e`
- `vdsutil!AssignTempVolumeName` at `0x14000472c`
- `vdsutil!AssignTempVolumeName` at `0x1400047a3`
- `vdsutil!AssignTempVolumeName` at `0x14000472c`
- `vdsutil!AssignTempVolumeName` at `0x1400047a3`
- `vdsutil!GetVolumeName` at `0x14000476f`
- `vdsutil!GetVolumeName` at `0x14000476f`
- `vdsutil!VdsTraceEx` at `0x14000450e`
- `vdsutil!VdsTraceEx` at `0x1400045bc`
- `vdsutil!VdsTraceEx` at `0x140004653`
- `vdsutil!VdsTraceEx` at `0x14000469a`
- `vdsutil!VdsTraceEx` at `0x14000482a`
- `vdsutil!VdsTraceEx` at `0x14000450e`
- `vdsutil!VdsTraceEx` at `0x1400045bc`
- `vdsutil!VdsTraceEx` at `0x140004653`
- `vdsutil!VdsTraceEx` at `0x14000469a`
- `vdsutil!VdsTraceEx` at `0x14000482a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400044af`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400044af`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140004519`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000455e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140004598`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400045f3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000461d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400046d1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140004752`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400047c9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000480c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000488c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140004519`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000455e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140004598`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400045f3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000461d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400046d1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140004752`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400047c9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000480c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000488c`
- `vdsutil!VdsTraceW` at `0x1400047e6`
- `vdsutil!VdsTraceW` at `0x1400047e6`

## string_xrefs

- `0x14000468c`: `CVdsVolume::GetVolumeName: StringCchCopyW: %S, error=%ld.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsVolume::GetVolumeName(
        CVdsVolume *this,
        unsigned __int16 *const a2,
        int *a3,
        int a4,
        unsigned int a5,
        unsigned __int16 *a6)
{
  int v9; // eax
  signed int IsPackOffline; // r14d
  const char *v12; // rsi
  void *v13; // rbx
  __int64 v14; // rdi
  unsigned __int64 v15; // rax
  DWORD LastError; // eax
  int v17; // r15d
  int v18; // edi
  unsigned __int16 *v19; // r14
  int VolumeName; // eax
  unsigned int v21; // edx
  LPVOID v22; // [rsp+30h] [rbp-59h]
  _BYTE v23[16]; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 *v24; // [rsp+48h] [rbp-41h]
  CVdsVolume *v25; // [rsp+50h] [rbp-39h]
  __int128 v26; // [rsp+58h] [rbp-31h] BYREF
  __int128 v27; // [rsp+68h] [rbp-21h]
  __int128 v28; // [rsp+78h] [rbp-11h]
  LPVOID pv; // [rsp+88h] [rbp-1h]

  v24 = a2;
  v25 = this;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v23, 0x5Eu, "CVdsVolume::GetVolumeName()");
  v26 = 0;
  v27 = 0;
  v28 = 0;
  pv = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 16) + 24LL))(*((_QWORD *)this + 16), &v26);
  IsPackOffline = v9;
  if ( v9 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::GetVolumeName, 1, hr=%lX", v9);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
    return (unsigned int)IsPackOffline;
  }
  v12 = (const char *)pv;
  v13 = pv;
  v22 = pv;
  v14 = -1;
  if ( !pv )
  {
    if ( DWORD1(v27) == 5 )
    {
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
      return 2147755057LL;
    }
    IsPackOffline = CVdsVolume::IsPackOffline(v25);
    if ( !IsPackOffline )
    {
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
      return 2147755076LL;
    }
    if ( IsPackOffline == 1 )
    {
      VdsTraceEx(94, 0, "CVdsVolume::GetVolumeName: volume name is missing.");
LABEL_56:
      if ( v13 )
        CoTaskMemFree(v13);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
      return 2147755073LL;
    }
    if ( IsPackOffline < 0 )
    {
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
      if ( IsPackOffline == -2147024882 )
        return 2147942414LL;
      else
        return (unsigned int)IsPackOffline;
    }
    goto LABEL_22;
  }
  v15 = -1;
  do
    ++v15;
  while ( *((_WORD *)pv + v15) );
  if ( v15 >= 0x104 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::GetVolumeName: volume name is too long: %S.", (const wchar_t *)pv);
    goto LABEL_56;
  }
  if ( a6 && a5 )
  {
    IsPackOffline = StringCchCopyW(a6, a5, (const unsigned __int16 *)pv);
    if ( IsPackOffline < 0 )
    {
      LastError = GetLastError();
      VdsTraceEx(94, 0, "CVdsVolume::GetVolumeName: StringCchCopyW: %S, error=%ld.", (const wchar_t *)pv, LastError);
    }
LABEL_22:
    v12 = (const char *)pv;
  }
  if ( (BYTE8(v28) & 0x10) != 0 )
  {
    *a3 = 1;
    if ( !a4 )
    {
      if ( v13 )
        CoTaskMemFree(v13);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
      return 2147755382LL;
    }
    v17 = 1;
  }
  else
  {
    *a3 = 0;
    v17 = 0;
  }
  if ( !v12 || wcsncmp_0((const wchar_t *)v12, L"\\\\?\\GLOBALROOT", 0xEu) )
  {
    VdsTraceEx(94, 0, "CVdsVolume::GetVolumeName: bad volume name: %s", v12);
    if ( pv )
    {
      do
        ++v14;
      while ( *((_WORD *)pv + v14) );
      v21 = 2 * v14 + 2;
    }
    else
    {
      v21 = 0;
    }
    VdsLogError(0xC2000010, v21, pv, IsPackOffline, 0x20A000Au, 0, v22);
    goto LABEL_56;
  }
  if ( v17 && a4 )
  {
    v18 = AssignTempVolumeName(v12 + 28, v24);
    if ( v18 < 0 )
      goto LABEL_35;
LABEL_43:
    if ( v13 )
      CoTaskMemFree(v13);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
    return 1;
  }
  v19 = v24;
  VolumeName = GetVolumeName(v12 + 28, 260, v24);
  v18 = VolumeName;
  if ( VolumeName < 0 )
  {
    if ( VolumeName != -2147024894 )
      goto LABEL_35;
    if ( !CVdsService::m_bIsWinPE || (*a3 = 1, !a4) )
    {
      VdsTraceW(0, L"CVdsVolume::GetVolumeName: volume name not found: %s.", v12 + 28);
      goto LABEL_35;
    }
    v18 = AssignTempVolumeName((char *)pv + 28, v19);
    if ( v18 < 0 )
    {
LABEL_35:
      if ( v13 )
        CoTaskMemFree(v13);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
      return (unsigned int)v18;
    }
    goto LABEL_43;
  }
  if ( v13 )
    CoTaskMemFree(v13);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
  return 0;
}

```

## disassembly

```asm
0x140004460  mov     [rsp-8+arg_18], rbx
0x140004465  push    rbp
0x140004466  push    rsi
0x140004467  push    rdi
0x140004468  push    r12
0x14000446a  push    r13
0x14000446c  push    r14
0x14000446e  push    r15
0x140004470  lea     rbp, [rsp-17h]
0x140004475  sub     rsp, 0A0h
0x14000447c  mov     rax, cs:__security_cookie
0x140004483  xor     rax, rsp
0x140004486  mov     [rbp+47h+var_40], rax
0x14000448a  mov     r12d, r9d
0x14000448d  mov     r13, r8
0x140004490  mov     [rbp+47h+var_88], rdx
0x140004494  mov     rbx, rcx
0x140004497  mov     [rbp+47h+var_80], rcx
0x14000449b  mov     r15, [rbp+47h+arg_28]
0x14000449f  lea     r8, aCvdsvolumeGetv_5; "CVdsVolume::GetVolumeName()"
0x1400044a6  mov     edx, 5Eh ; '^'
0x1400044ab  lea     rcx, [rbp+47h+var_98]
0x1400044af  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400044b5  nop
0x1400044b6  xorps   xmm0, xmm0
0x1400044b9  xor     eax, eax
0x1400044bb  movups  [rbp+47h+var_78], xmm0
0x1400044bf  movups  [rbp+47h+var_68], xmm0
0x1400044c3  movups  [rbp+47h+var_58], xmm0
0x1400044c7  mov     [rbp+47h+pv], rax
0x1400044cb  mov     [rbp+47h+var_A0], rax
0x1400044cf  movups  [rbp+47h+var_78], xmm0
0x1400044d3  movups  [rbp+47h+var_68], xmm0
0x1400044d7  movups  [rbp+47h+var_58], xmm0
0x1400044db  mov     [rbp+47h+pv], rax
0x1400044df  mov     rcx, [rbx+80h]
0x1400044e6  mov     rax, [rcx]
0x1400044e9  lea     rdx, [rbp+47h+var_78]
0x1400044ed  mov     rax, [rax+18h]
0x1400044f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044f6  mov     r14d, eax
0x1400044f9  test    eax, eax
0x1400044fb  jns     short loc_140004527
0x1400044fd  mov     r9d, eax
0x140004500  lea     r8, aCvdsvolumeGetv_3; "CVdsVolume::GetVolumeName, 1, hr=%lX"
0x140004507  xor     edx, edx
0x140004509  mov     ecx, 5Eh ; '^'
0x14000450e  call    cs:__imp_VdsTraceEx
0x140004514  nop
0x140004515  lea     rcx, [rbp+47h+var_98]
0x140004519  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000451f  mov     eax, r14d
0x140004522  jmp     loc_140004897
0x140004527  mov     rsi, [rbp+47h+pv]
0x14000452b  mov     rbx, rsi
0x14000452e  mov     [rbp+47h+var_A0], rbx
0x140004532  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x140004539  test    rsi, rsi
0x14000453c  jnz     loc_14000462B
0x140004542  cmp     dword ptr [rbp+47h+var_68+4], 5
0x140004546  jnz     short loc_14000456E
0x140004548  test    rbx, rbx
0x14000454b  jz      short loc_14000455A
0x14000454d  mov     rcx, rbx; pv
0x140004550  call    cs:__imp_CoTaskMemFree
0x140004556  mov     [rbp+47h+var_A0], rsi
0x14000455a  lea     rcx, [rbp+47h+var_98]
0x14000455e  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140004564  mov     eax, 80042431h
0x140004569  jmp     loc_140004897
0x14000456e  mov     rcx, [rbp+47h+var_80]; this
0x140004572  call    ?IsPackOffline@CVdsVolume@@AEAAJXZ; CVdsVolume::IsPackOffline(void)
0x140004577  mov     r14d, eax
0x14000457a  test    eax, eax
0x14000457c  jnz     short loc_1400045A8
0x14000457e  test    rbx, rbx
0x140004581  jz      short loc_140004594
0x140004583  mov     rcx, rbx; pv
0x140004586  call    cs:__imp_CoTaskMemFree
0x14000458c  mov     [rbp+47h+var_A0], 0
0x140004594  lea     rcx, [rbp+47h+var_98]
0x140004598  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000459e  mov     eax, 80042444h
0x1400045a3  jmp     loc_140004897
0x1400045a8  cmp     r14d, 1
0x1400045ac  jnz     short loc_1400045C7
0x1400045ae  lea     r8, aCvdsvolumeGetv_4; "CVdsVolume::GetVolumeName: volume name "...
0x1400045b5  xor     edx, edx
0x1400045b7  mov     ecx, 5Eh ; '^'
0x1400045bc  call    cs:__imp_VdsTraceEx
0x1400045c2  jmp     loc_140004872
0x1400045c7  test    r14d, r14d
0x1400045ca  jns     loc_1400046A0
0x1400045d0  cmp     r14d, 8007000Eh
0x1400045d7  jnz     short loc_140004603
0x1400045d9  test    rbx, rbx
0x1400045dc  jz      short loc_1400045EF
0x1400045de  mov     rcx, rbx; pv
0x1400045e1  call    cs:__imp_CoTaskMemFree
0x1400045e7  mov     [rbp+47h+var_A0], 0
0x1400045ef  lea     rcx, [rbp+47h+var_98]
0x1400045f3  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400045f9  mov     eax, 8007000Eh
0x1400045fe  jmp     loc_140004897
0x140004603  test    rbx, rbx
0x140004606  jz      short loc_140004619
0x140004608  mov     rcx, rbx; pv
0x14000460b  call    cs:__imp_CoTaskMemFree
0x140004611  mov     [rbp+47h+var_A0], 0
0x140004619  lea     rcx, [rbp+47h+var_98]
0x14000461d  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140004623  mov     eax, r14d
0x140004626  jmp     loc_140004897
0x14000462b  mov     rax, rdi
0x14000462e  xchg    ax, ax
0x140004630  inc     rax
0x140004633  cmp     word ptr [rsi+rax*2], 0
0x140004638  jnz     short loc_140004630
0x14000463a  cmp     rax, 104h
0x140004640  jb      short loc_14000465E
0x140004642  mov     r9, rsi
0x140004645  lea     r8, aCvdsvolumeGetv_2; "CVdsVolume::GetVolumeName: volume name "...
0x14000464c  xor     edx, edx
0x14000464e  mov     ecx, 5Eh ; '^'
0x140004653  call    cs:__imp_VdsTraceEx
0x140004659  jmp     loc_140004872
0x14000465e  test    r15, r15
0x140004661  jz      short loc_1400046A4
0x140004663  mov     eax, [rbp+47h+arg_20]
0x140004666  test    eax, eax
0x140004668  jz      short loc_1400046A4
0x14000466a  mov     edx, eax; unsigned __int64
0x14000466c  mov     r8, rsi; unsigned __int16 *
0x14000466f  mov     rcx, r15; unsigned __int16 *
0x140004672  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140004677  mov     r14d, eax
0x14000467a  test    eax, eax
0x14000467c  jns     short loc_1400046A0
0x14000467e  call    cs:__imp_GetLastError
0x140004684  mov     [rsp+0D0h+var_B0], eax
0x140004688  mov     r9, [rbp+47h+pv]
0x14000468c  lea     r8, aCvdsvolumeGetv; "CVdsVolume::GetVolumeName: StringCchCop"...
0x140004693  xor     edx, edx
0x140004695  mov     ecx, 5Eh ; '^'
0x14000469a  call    cs:__imp_VdsTraceEx
0x1400046a0  mov     rsi, [rbp+47h+pv]
0x1400046a4  test    byte ptr [rbp+47h+var_58+8], 10h
0x1400046a8  jz      short loc_1400046E9
0x1400046aa  mov     dword ptr [r13+0], 1
0x1400046b2  test    r12d, r12d
0x1400046b5  jnz     short loc_1400046E1
0x1400046b7  test    rbx, rbx
0x1400046ba  jz      short loc_1400046CD
0x1400046bc  mov     rcx, rbx; pv
0x1400046bf  call    cs:__imp_CoTaskMemFree
0x1400046c5  mov     [rbp+47h+var_A0], 0
0x1400046cd  lea     rcx, [rbp+47h+var_98]
0x1400046d1  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400046d7  mov     eax, 80042576h
0x1400046dc  jmp     loc_140004897
0x1400046e1  mov     r15d, 1
0x1400046e7  jmp     short loc_1400046F4
0x1400046e9  mov     dword ptr [r13+0], 0
0x1400046f1  xor     r15d, r15d
0x1400046f4  test    rsi, rsi
0x1400046f7  jz      loc_140004819
0x1400046fd  mov     r8d, 0Eh; MaxCount
0x140004703  lea     rdx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x14000470a  mov     rcx, rsi; String1
0x14000470d  call    wcsncmp_0
0x140004712  test    eax, eax
0x140004714  jnz     loc_140004819
0x14000471a  test    r15d, r15d
0x14000471d  jz      short loc_14000475F
0x14000471f  test    r12d, r12d
0x140004722  jz      short loc_14000475F
0x140004724  lea     rcx, [rsi+1Ch]
0x140004728  mov     rdx, [rbp+47h+var_88]
0x14000472c  call    cs:__imp_AssignTempVolumeName
0x140004732  mov     edi, eax
0x140004734  test    eax, eax
0x140004736  jns     short loc_1400047AF
0x140004738  test    rbx, rbx
0x14000473b  jz      short loc_14000474E
0x14000473d  mov     rcx, rbx; pv
0x140004740  call    cs:__imp_CoTaskMemFree
0x140004746  mov     [rbp+47h+var_A0], 0
0x14000474e  lea     rcx, [rbp+47h+var_98]
0x140004752  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140004758  mov     eax, edi
0x14000475a  jmp     loc_140004897
0x14000475f  mov     r14, [rbp+47h+var_88]
0x140004763  mov     r8, r14
0x140004766  mov     edx, 104h
0x14000476b  lea     rcx, [rsi+1Ch]
0x14000476f  call    cs:__imp_GetVolumeName
0x140004775  mov     edi, eax
0x140004777  test    eax, eax
0x140004779  jns     short loc_1400047F2
0x14000477b  cmp     eax, 80070002h
0x140004780  jnz     short loc_1400047ED
0x140004782  cmp     cs:?m_bIsWinPE@CVdsService@@0HA, 0; int CVdsService::m_bIsWinPE
0x140004789  jz      short loc_1400047D9
0x14000478b  mov     dword ptr [r13+0], 1
0x140004793  test    r12d, r12d
0x140004796  jz      short loc_1400047D9
0x140004798  mov     rcx, [rbp+47h+pv]
0x14000479c  add     rcx, 1Ch
0x1400047a0  mov     rdx, r14
0x1400047a3  call    cs:__imp_AssignTempVolumeName
0x1400047a9  mov     edi, eax
0x1400047ab  test    eax, eax
0x1400047ad  js      short loc_140004738
0x1400047af  test    rbx, rbx
0x1400047b2  jz      short loc_1400047C5
0x1400047b4  mov     rcx, rbx; pv
0x1400047b7  call    cs:__imp_CoTaskMemFree
0x1400047bd  mov     [rbp+47h+var_A0], 0
0x1400047c5  lea     rcx, [rbp+47h+var_98]
0x1400047c9  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400047cf  mov     eax, 1
0x1400047d4  jmp     loc_140004897
0x1400047d9  lea     r8, [rsi+1Ch]
0x1400047dd  lea     rdx, aCvdsvolumeGetv_0; "CVdsVolume::GetVolumeName: volume name "...
0x1400047e4  xor     ecx, ecx
0x1400047e6  call    cs:__imp_VdsTraceW
0x1400047ec  nop
0x1400047ed  jmp     loc_140004738
0x1400047f2  test    rbx, rbx
0x1400047f5  jz      short loc_140004808
0x1400047f7  mov     rcx, rbx; pv
0x1400047fa  call    cs:__imp_CoTaskMemFree
0x140004800  mov     [rbp+47h+var_A0], 0
0x140004808  lea     rcx, [rbp+47h+var_98]
0x14000480c  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140004812  xor     eax, eax
0x140004814  jmp     loc_140004897
0x140004819  mov     r9, rsi
0x14000481c  lea     r8, aCvdsvolumeGetv_1; "CVdsVolume::GetVolumeName: bad volume n"...
0x140004823  xor     edx, edx
0x140004825  mov     ecx, 5Eh ; '^'
0x14000482a  call    cs:__imp_VdsTraceEx
0x140004830  mov     r8, [rbp+47h+pv]; void *
0x140004834  test    r8, r8
0x140004837  jnz     short loc_140004840
0x140004839  xor     edx, edx
0x14000483b  jmp     short loc_140004853
0x140004840  lea     rdi, [rdi+1]
0x140004844  cmp     word ptr [r8+rdi*2], 0
0x14000484a  jnz     short loc_140004840
0x14000484c  lea     edx, ds:2[rdi*2]; unsigned int
0x140004853  mov     [rsp+0D0h+var_A8], 0; unsigned __int16 *
0x14000485c  mov     [rsp+0D0h+var_B0], 20A000Ah; unsigned int
0x140004864  mov     r9d, r14d; unsigned int
0x140004867  mov     ecx, 0C2000010h; unsigned int
0x14000486c  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140004871  nop
0x140004872  test    rbx, rbx
0x140004875  jz      short loc_140004888
0x140004877  mov     rcx, rbx; pv
0x14000487a  call    cs:__imp_CoTaskMemFree
0x140004880  mov     [rbp+47h+var_A0], 0
0x140004888  lea     rcx, [rbp+47h+var_98]
0x14000488c  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140004892  mov     eax, 80042441h
0x140004897  mov     rcx, [rbp+47h+var_40]
0x14000489b  xor     rcx, rsp; StackCookie
0x14000489e  call    __security_check_cookie
0x1400048a3  mov     rbx, [rsp+0D0h+arg_18]
0x1400048ab  add     rsp, 0A0h
0x1400048b2  pop     r15
0x1400048b4  pop     r14
0x1400048b6  pop     r13
0x1400048b8  pop     r12
0x1400048ba  pop     rdi
0x1400048bb  pop     rsi
0x1400048bc  pop     rbp
0x1400048bd  retn
```
