# CVdsDiskLun::ValidateDiskInterfaces(void)

- ea: `0x140005630`
- end: `0x140005b16`
- name: `?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ`
- size: `1254`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this)`
- caller_count: `32`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004b80`
- `0x140004d80`
- `0x1400113f0`
- `0x14001cb30`
- `0x14001d530`
- `0x14001f300`
- `0x140020260`
- `0x140020bb0`
- `0x1400210b0`
- `0x140021b50`
- `0x140027e20`
- `0x140029600`
- `0x140029a70`
- `0x140044ac0`
- `0x140044bc0`
- `0x140044cd0`
- `0x140044f60`
- `0x140045240`
- `0x140045620`
- `0x140045df0`
- `0x140046130`
- `0x140046bf0`
- `0x140046df0`
- `0x140048fa0`
- `0x140049090`
- `0x140049740`
- `0x140049840`
- `0x140049b00`
- `0x140049e60`
- `0x14004a110`
- `0x14004a250`
- `0x14004a370`

## callees

- `0x140005630`
- `0x140008410`
- `0x14000d6e0`
- `0x14000dd3c`
- `0x14000dfb4`
- `0x140013298`
- `0x14002e123`
- `0x140038858`
- `0x140038a70`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005731`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005ab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005ac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005ad8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005731`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005ab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005ac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005ad8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005a30`
- `vdsutil!VdsTraceEx` at `0x140005787`
- `vdsutil!VdsTraceEx` at `0x140005804`
- `vdsutil!VdsTraceEx` at `0x14000588d`
- `vdsutil!VdsTraceEx` at `0x1400058b2`
- `vdsutil!VdsTraceEx` at `0x14000594e`
- `vdsutil!VdsTraceEx` at `0x140005987`
- `vdsutil!VdsTraceEx` at `0x1400059c2`
- `vdsutil!VdsTraceEx` at `0x1400059ed`
- `vdsutil!VdsTraceEx` at `0x140005a47`
- `vdsutil!VdsTraceEx` at `0x140005a7a`
- `vdsutil!VdsTraceEx` at `0x140005787`
- `vdsutil!VdsTraceEx` at `0x140005804`
- `vdsutil!VdsTraceEx` at `0x14000588d`
- `vdsutil!VdsTraceEx` at `0x1400058b2`
- `vdsutil!VdsTraceEx` at `0x14000594e`
- `vdsutil!VdsTraceEx` at `0x140005987`
- `vdsutil!VdsTraceEx` at `0x1400059c2`
- `vdsutil!VdsTraceEx` at `0x1400059ed`
- `vdsutil!VdsTraceEx` at `0x140005a47`
- `vdsutil!VdsTraceEx` at `0x140005a7a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000566f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000566f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140005ae6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140005ae6`
- `vdsutil!VdsTraceW` at `0x1400056c8`
- `vdsutil!VdsTraceW` at `0x1400056ed`
- `vdsutil!VdsTraceW` at `0x1400056c8`
- `vdsutil!VdsTraceW` at `0x1400056ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsDiskLun::ValidateDiskInterfaces(CVdsDiskLun *this)
{
  unsigned int v2; // ebx
  int v3; // eax
  int DiskIdFromMap; // eax
  unsigned int v5; // ebx
  int Disk; // eax
  int ObjectFromProviders; // eax
  struct IUnknown *v8; // rdx
  DWORD LastError; // eax
  int DiskInterfaces; // eax
  struct _GUID v12; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v13[16]; // [rsp+80h] [rbp-49h] BYREF
  struct _GUID v14; // [rsp+90h] [rbp-39h] BYREF
  LPVOID v15[2]; // [rsp+A0h] [rbp-29h]
  LPVOID pv[2]; // [rsp+B0h] [rbp-19h]
  __int128 v17; // [rsp+C0h] [rbp-9h]
  __int64 v18; // [rsp+D0h] [rbp+7h]
  struct _GUID v19; // [rsp+E0h] [rbp+17h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v13, 0x5Eu, "CVdsDiskLun::ValidateDiskInterfaces()");
  *(_QWORD *)&v12.Data1 = 0;
  *(_QWORD *)v12.Data4 = 0;
  v14 = 0;
  *(_OWORD *)v15 = 0;
  *(_OWORD *)pv = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  if ( *((_QWORD *)this + 26) )
  {
    v2 = 0;
  }
  else
  {
    if ( !*((_QWORD *)this + 35) )
    {
      v2 = -2147212277;
      VdsTraceW(0, L"CVdsDiskLun::ValidateDiskInterfaces, 1, hr=%lX", 2147755019LL);
      goto LABEL_32;
    }
    if ( *((_QWORD *)this + 28) )
    {
      v2 = -2147212216;
      VdsTraceW(0, L"CVdsDiskLun::ValidateDiskInterfaces, 2, hr=%lX", 2147755080LL);
      VdsLogError(0xC2000009, 0, 0, 0x80042448, 0x205000Bu, 0);
      goto LABEL_32;
    }
    if ( *((_QWORD *)this + 35) )
    {
      if ( pv[1] )
        CoTaskMemFree(pv[1]);
      memset_0(&v14, 0, 0x48u);
      v3 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 35) + 24LL))(
             *((_QWORD *)this + 35),
             &v14);
      if ( v3 < 0 )
      {
        VdsTraceEx(94, 0, "CVdsDiskLun::ValidateDiskInterfaces, 3, hr=%lX", v3);
        v2 = -2147212222;
        goto LABEL_32;
      }
      VdsTraceEx(
        94,
        3,
        "CVdsDiskLun::ValidateDiskInterfaces, 4 LunId:{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
        v14.Data1,
        v14.Data2,
        v14.Data3,
        v14.Data4[0],
        v14.Data4[1],
        v14.Data4[2],
        v14.Data4[3],
        v14.Data4[4],
        v14.Data4[5],
        v14.Data4[6],
        v14.Data4[7]);
      v12 = v14;
    }
    v19 = 0;
    DiskIdFromMap = CVdsService::GetDiskIdFromMap(&v12, &v19);
    v5 = DiskIdFromMap;
    if ( DiskIdFromMap == 1 )
    {
      VdsTraceEx(94, 1, "CVdsDiskLun::ValidateDiskInterfaces, 5, hr=%lX", 1);
      v2 = -2147212283;
      goto LABEL_32;
    }
    if ( DiskIdFromMap < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::ValidateDiskInterfaces, 6, hr=%lX", DiskIdFromMap);
      VdsLogError(0xC2000009, 0, 0, v5, 0x205000Cu, 0);
LABEL_16:
      v2 = -2147212216;
      goto LABEL_32;
    }
    VdsTraceEx(
      94,
      3,
      "CVdsDiskLun::ValidateDiskInterfaces, 7 DiskId:{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
      v19.Data1,
      v19.Data2,
      v19.Data3,
      v19.Data4[0],
      v19.Data4[1],
      v19.Data4[2],
      v19.Data4[3],
      v19.Data4[4],
      v19.Data4[5],
      v19.Data4[6],
      v19.Data4[7]);
    v12 = v19;
    Disk = CVdsService::GetDisk(&v12, (struct IUnknown **)this + 26);
    v2 = Disk;
    if ( Disk < 0 )
    {
      VdsTraceEx(94, 2, "CVdsDiskLun::ValidateDiskInterfaces, 8, hr=%lX", Disk);
      v12 = v19;
      ObjectFromProviders = CVdsService::GetObjectFromProviders(&v12, VDS_OT_DISK, (struct IUnknown **)this + 26);
      v2 = ObjectFromProviders;
      if ( ObjectFromProviders < 0 )
      {
        VdsTraceEx(94, 0, "CVdsDiskLun::ValidateDiskInterfaces, 9, hr=%lX", ObjectFromProviders);
        v2 = -2147212283;
        goto LABEL_32;
      }
    }
    v8 = (struct IUnknown *)*((_QWORD *)this + 26);
    if ( !v8 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::ValidateDiskInterfaces, 10, hr=%lX", v2);
      VdsLogError(0xC2000009, 0, 0, v2, 0x205000Du, 0);
      goto LABEL_16;
    }
    if ( !CVdsService::FindWrapperInMap(*((CVdsService **)this + 27), v8)
      && !(unsigned int)CVdsService::AddObjectToMap(
                          *((struct _RTL_CRITICAL_SECTION **)this + 27),
                          *((struct IUnknown **)this + 26),
                          (struct IUnknown *)this) )
    {
      LastError = GetLastError();
      VdsTraceEx(94, 0, "CVdsDiskLun::ValidateDiskInterfaces, 11, Win32 error=%ld", LastError);
    }
  }
  if ( !*((_QWORD *)this + 28) )
  {
    DiskInterfaces = CVdsDiskLun::QueryDiskInterfaces(this);
    v2 = DiskInterfaces;
    if ( DiskInterfaces < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::ValidateDiskInterfaces, 12, hr=%lX", DiskInterfaces);
      VdsLogError(0xC2000009, 0, 0, v2, 0x205000Eu, 0);
      goto LABEL_16;
    }
  }
  if ( !*((_QWORD *)this + 34) || !*((_QWORD *)this + 32) )
    v2 = 1;
LABEL_32:
  if ( v15[1] )
  {
    CoTaskMemFree(v15[1]);
    v15[1] = 0;
  }
  if ( pv[0] )
  {
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
  }
  if ( pv[1] )
  {
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v13);
  return v2;
}

```

## disassembly

```asm
0x140005630  mov     [rsp-8+arg_8], rbx
0x140005635  mov     [rsp-8+arg_10], rsi
0x14000563a  push    rbp
0x14000563b  push    rdi
0x14000563c  push    r12
0x14000563e  push    r14
0x140005640  push    r15
0x140005642  lea     rbp, [rsp-37h]
0x140005647  sub     rsp, 100h
0x14000564e  mov     rax, cs:__security_cookie
0x140005655  xor     rax, rsp
0x140005658  mov     [rbp+57h+var_30], rax
0x14000565c  mov     r14, rcx
0x14000565f  lea     r8, aCvdsdisklunVal_10; "CVdsDiskLun::ValidateDiskInterfaces()"
0x140005666  mov     edx, 5Eh ; '^'
0x14000566b  lea     rcx, [rbp+57h+var_A0]
0x14000566f  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140005675  nop
0x140005676  xor     r12d, r12d
0x140005679  mov     qword ptr [rbp+57h+var_B0.Data1], r12
0x14000567d  mov     qword ptr [rbp+57h+var_B0.Data4], r12
0x140005681  xorps   xmm1, xmm1
0x140005684  xor     eax, eax
0x140005686  movups  [rbp+57h+var_90], xmm1
0x14000568a  movups  xmmword ptr [rbp+57h+var_80], xmm1
0x14000568e  movaps  xmmword ptr [rbp+57h+pv], xmm1
0x140005692  movups  [rbp+57h+var_60], xmm1
0x140005696  mov     [rbp+57h+var_50], rax
0x14000569a  xorps   xmm0, xmm0
0x14000569d  movups  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x1400056a1  cmp     [r14+0D0h], rax
0x1400056a8  jnz     loc_140005A4F
0x1400056ae  cmp     [r14+118h], rax
0x1400056b5  jnz     short loc_1400056D3
0x1400056b7  mov     ebx, 8004240Bh
0x1400056bc  mov     r8d, ebx
0x1400056bf  lea     rdx, aCvdsdisklunVal_8; "CVdsDiskLun::ValidateDiskInterfaces, 1,"...
0x1400056c6  xor     ecx, ecx
0x1400056c8  call    cs:__imp_VdsTraceW
0x1400056ce  jmp     loc_140005AA9
0x1400056d3  cmp     [r14+0E0h], rax
0x1400056da  jz      short loc_14000571A
0x1400056dc  mov     ebx, 80042448h
0x1400056e1  mov     r8d, ebx
0x1400056e4  lea     rdx, aCvdsdisklunVal_11; "CVdsDiskLun::ValidateDiskInterfaces, 2,"...
0x1400056eb  xor     ecx, ecx
0x1400056ed  call    cs:__imp_VdsTraceW
0x1400056f3  mov     [rsp+120h+var_F8], r12; unsigned __int16 *
0x1400056f8  mov     [rsp+120h+var_100], 205000Bh; unsigned int
0x140005700  mov     r9d, 80042448h; unsigned int
0x140005706  xor     r8d, r8d; void *
0x140005709  xor     edx, edx; unsigned int
0x14000570b  mov     ecx, 0C2000009h; unsigned int
0x140005710  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140005715  jmp     loc_140005AA9
0x14000571a  cmp     [r14+118h], rax
0x140005721  jz      loc_140005858
0x140005727  movq    rcx, xmm1; pv
0x14000572c  test    rcx, rcx
0x14000572f  jz      short loc_14000573B
0x140005731  call    cs:__imp_CoTaskMemFree
0x140005737  mov     [rbp+57h+pv], r12
0x14000573b  mov     rcx, [rbp+57h+pv+8]; pv
0x14000573f  test    rcx, rcx
0x140005742  jz      short loc_14000574A
0x140005744  call    cs:__imp_CoTaskMemFree
0x14000574a  xor     edx, edx; Val
0x14000574c  mov     r8d, 48h ; 'H'; Size
0x140005752  lea     rcx, [rbp+57h+var_90]; void *
0x140005756  call    memset_0
0x14000575b  mov     rcx, [r14+118h]
0x140005762  mov     rax, [rcx]
0x140005765  lea     rdx, [rbp+57h+var_90]
0x140005769  mov     rax, [rax+18h]
0x14000576d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005772  test    eax, eax
0x140005774  jns     short loc_140005797
0x140005776  mov     r9d, eax
0x140005779  lea     r8, aCvdsdisklunVal_1; "CVdsDiskLun::ValidateDiskInterfaces, 3,"...
0x140005780  xor     edx, edx
0x140005782  mov     ecx, 5Eh ; '^'
0x140005787  call    cs:__imp_VdsTraceEx
0x14000578d  mov     ebx, 80042442h
0x140005792  jmp     loc_140005AA9
0x140005797  movzx   eax, byte ptr [rbp+57h+var_90+0Fh]
0x14000579b  movzx   ecx, byte ptr [rbp+57h+var_90+0Eh]
0x14000579f  movzx   edx, byte ptr [rbp+57h+var_90+0Dh]
0x1400057a3  movzx   r8d, byte ptr [rbp+57h+var_90+0Ch]
0x1400057a8  movzx   r9d, byte ptr [rbp+57h+var_90+0Bh]
0x1400057ad  movzx   r10d, byte ptr [rbp+57h+var_90+0Ah]
0x1400057b2  movzx   r11d, byte ptr [rbp+57h+var_90+9]
0x1400057b7  movzx   ebx, byte ptr [rbp+57h+var_90+8]
0x1400057bb  movzx   edi, word ptr [rbp+57h+var_90+6]
0x1400057bf  movzx   esi, word ptr [rbp+57h+var_90+4]
0x1400057c3  mov     [rsp+120h+var_B8], eax
0x1400057c7  mov     [rsp+120h+var_C0], ecx
0x1400057cb  mov     [rsp+120h+var_C8], edx
0x1400057cf  mov     [rsp+120h+var_D0], r8d
0x1400057d4  mov     [rsp+120h+var_D8], r9d
0x1400057d9  mov     [rsp+120h+var_E0], r10d
0x1400057de  mov     [rsp+120h+var_E8], r11d
0x1400057e3  mov     [rsp+120h+var_F0], ebx
0x1400057e7  mov     dword ptr [rsp+120h+var_F8], edi
0x1400057eb  mov     [rsp+120h+var_100], esi
0x1400057ef  mov     r9d, dword ptr [rbp+57h+var_90]
0x1400057f3  lea     r8, aCvdsdisklunVal_0; "CVdsDiskLun::ValidateDiskInterfaces, 4 "...
0x1400057fa  mov     edx, 3
0x1400057ff  mov     ecx, 5Eh ; '^'
0x140005804  call    cs:__imp_VdsTraceEx
0x14000580a  mov     eax, dword ptr [rbp+57h+var_90]
0x14000580d  mov     [rbp+57h+var_B0.Data1], eax
0x140005810  movzx   eax, word ptr [rbp+57h+var_90+4]
0x140005814  mov     [rbp+57h+var_B0.Data2], ax
0x140005818  movzx   eax, word ptr [rbp+57h+var_90+6]
0x14000581c  mov     [rbp+57h+var_B0.Data3], ax
0x140005820  movzx   eax, byte ptr [rbp+57h+var_90+8]
0x140005824  mov     [rbp+57h+var_B0.Data4], al
0x140005827  movzx   eax, byte ptr [rbp+57h+var_90+9]
0x14000582b  mov     [rbp+57h+var_B0.Data4+1], al
0x14000582e  movzx   eax, byte ptr [rbp+57h+var_90+0Ah]
0x140005832  mov     [rbp+57h+var_B0.Data4+2], al
0x140005835  movzx   eax, byte ptr [rbp+57h+var_90+0Bh]
0x140005839  mov     [rbp+57h+var_B0.Data4+3], al
0x14000583c  movzx   eax, byte ptr [rbp+57h+var_90+0Ch]
0x140005840  mov     [rbp+57h+var_B0.Data4+4], al
0x140005843  movzx   eax, byte ptr [rbp+57h+var_90+0Dh]
0x140005847  mov     [rbp+57h+var_B0.Data4+5], al
0x14000584a  movzx   eax, byte ptr [rbp+57h+var_90+0Eh]
0x14000584e  mov     [rbp+57h+var_B0.Data4+6], al
0x140005851  movzx   eax, byte ptr [rbp+57h+var_90+0Fh]
0x140005855  mov     [rbp+57h+var_B0.Data4+7], al
0x140005858  xorps   xmm0, xmm0
0x14000585b  movups  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x14000585f  movaps  xmm1, xmmword ptr [rbp+57h+var_B0.Data1]
0x140005863  movdqa  xmmword ptr [rbp+57h+var_B0.Data1], xmm1
0x140005868  lea     rdx, [rbp+57h+var_40]; struct _GUID *
0x14000586c  lea     rcx, [rbp+57h+var_B0]; struct _GUID *
0x140005870  call    ?GetDiskIdFromMap@CVdsService@@SAJU_GUID@@PEAU2@@Z; CVdsService::GetDiskIdFromMap(_GUID,_GUID *)
0x140005875  mov     ebx, eax
0x140005877  cmp     eax, 1
0x14000587a  jnz     short loc_14000589D
0x14000587c  mov     r9d, eax
0x14000587f  lea     r8, aCvdsdisklunVal; "CVdsDiskLun::ValidateDiskInterfaces, 5,"...
0x140005886  mov     edx, eax
0x140005888  mov     ecx, 5Eh ; '^'
0x14000588d  call    cs:__imp_VdsTraceEx
0x140005893  mov     ebx, 80042405h
0x140005898  jmp     loc_140005AA9
0x14000589d  test    ebx, ebx
0x14000589f  jns     short loc_1400058E1
0x1400058a1  mov     r9d, ebx
0x1400058a4  lea     r8, aCvdsdisklunVal_3; "CVdsDiskLun::ValidateDiskInterfaces, 6,"...
0x1400058ab  xor     edx, edx
0x1400058ad  mov     ecx, 5Eh ; '^'
0x1400058b2  call    cs:__imp_VdsTraceEx
0x1400058b8  mov     [rsp+120h+var_F8], r12; unsigned __int16 *
0x1400058bd  mov     [rsp+120h+var_100], 205000Ch; unsigned int
0x1400058c5  mov     r9d, ebx; unsigned int
0x1400058c8  xor     r8d, r8d; void *
0x1400058cb  xor     edx, edx; unsigned int
0x1400058cd  mov     ecx, 0C2000009h; unsigned int
0x1400058d2  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x1400058d7  mov     ebx, 80042448h
0x1400058dc  jmp     loc_140005AA9
0x1400058e1  movzx   eax, [rbp+57h+var_40.Data4+7]
0x1400058e5  movzx   ecx, [rbp+57h+var_40.Data4+6]
0x1400058e9  movzx   edx, [rbp+57h+var_40.Data4+5]
0x1400058ed  movzx   r8d, [rbp+57h+var_40.Data4+4]
0x1400058f2  movzx   r9d, [rbp+57h+var_40.Data4+3]
0x1400058f7  movzx   r10d, [rbp+57h+var_40.Data4+2]
0x1400058fc  movzx   r11d, [rbp+57h+var_40.Data4+1]
0x140005901  movzx   ebx, [rbp+57h+var_40.Data4]
0x140005905  movzx   edi, [rbp+57h+var_40.Data3]
0x140005909  movzx   esi, [rbp+57h+var_40.Data2]
0x14000590d  mov     [rsp+120h+var_B8], eax
0x140005911  mov     [rsp+120h+var_C0], ecx
0x140005915  mov     [rsp+120h+var_C8], edx
0x140005919  mov     [rsp+120h+var_D0], r8d
0x14000591e  mov     [rsp+120h+var_D8], r9d
0x140005923  mov     [rsp+120h+var_E0], r10d
0x140005928  mov     [rsp+120h+var_E8], r11d
0x14000592d  mov     [rsp+120h+var_F0], ebx
0x140005931  mov     dword ptr [rsp+120h+var_F8], edi
0x140005935  mov     [rsp+120h+var_100], esi
0x140005939  mov     r9d, [rbp+57h+var_40.Data1]
0x14000593d  lea     r8, aCvdsdisklunVal_7; "CVdsDiskLun::ValidateDiskInterfaces, 7 "...
0x140005944  mov     edx, 3
0x140005949  mov     ecx, 5Eh ; '^'
0x14000594e  call    cs:__imp_VdsTraceEx
0x140005954  movaps  xmm0, xmmword ptr [rbp+57h+var_40.Data1]
0x140005958  movdqa  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x14000595d  lea     rdx, [r14+0D0h]; struct IUnknown **
0x140005964  lea     rcx, [rbp+57h+var_B0]; struct _GUID
0x140005968  call    ?GetDisk@CVdsService@@SAJU_GUID@@PEAPEAUIUnknown@@@Z; CVdsService::GetDisk(_GUID,IUnknown * *)
0x14000596d  mov     ebx, eax
0x14000596f  test    eax, eax
0x140005971  jns     short loc_1400059D2
0x140005973  mov     r9d, eax
0x140005976  lea     r8, aCvdsdisklunVal_2; "CVdsDiskLun::ValidateDiskInterfaces, 8,"...
0x14000597d  mov     edx, 2
0x140005982  mov     ecx, 5Eh ; '^'
0x140005987  call    cs:__imp_VdsTraceEx
0x14000598d  movaps  xmm0, xmmword ptr [rbp+57h+var_40.Data1]
0x140005991  movdqa  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x140005996  lea     r8, [r14+0D0h]; struct IUnknown **
0x14000599d  mov     edx, 0Dh; enum _VDS_OBJECT_TYPE
0x1400059a2  lea     rcx, [rbp+57h+var_B0]; struct _GUID
0x1400059a6  call    ?GetObjectFromProviders@CVdsService@@SAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z; CVdsService::GetObjectFromProviders(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)
0x1400059ab  mov     ebx, eax
0x1400059ad  test    eax, eax
0x1400059af  jns     short loc_1400059D2
0x1400059b1  mov     r9d, eax
0x1400059b4  lea     r8, aCvdsdisklunVal_4; "CVdsDiskLun::ValidateDiskInterfaces, 9,"...
0x1400059bb  xor     edx, edx
0x1400059bd  mov     ecx, 5Eh ; '^'
0x1400059c2  call    cs:__imp_VdsTraceEx
0x1400059c8  mov     ebx, 80042405h
0x1400059cd  jmp     loc_140005AA9
0x1400059d2  mov     rdx, [r14+0D0h]; struct IUnknown *
0x1400059d9  test    rdx, rdx
0x1400059dc  jnz     short loc_140005A05
0x1400059de  mov     r9d, ebx
0x1400059e1  lea     r8, aCvdsdisklunVal_6; "CVdsDiskLun::ValidateDiskInterfaces, 10"...
0x1400059e8  mov     ecx, 5Eh ; '^'
0x1400059ed  call    cs:__imp_VdsTraceEx
0x1400059f3  mov     [rsp+120h+var_F8], r12
0x1400059f8  mov     [rsp+120h+var_100], 205000Dh
0x140005a00  jmp     loc_1400058C5
0x140005a05  mov     rcx, [r14+0D8h]; this
0x140005a0c  call    ?FindWrapperInMap@CVdsService@@QEAAPEAUIUnknown@@PEAU2@@Z; CVdsService::FindWrapperInMap(IUnknown *)
0x140005a11  test    rax, rax
0x140005a14  jnz     short loc_140005A52
0x140005a16  mov     r8, r14; struct IUnknown *
0x140005a19  mov     rdx, [r14+0D0h]; struct IUnknown *
0x140005a20  mov     rcx, [r14+0D8h]; this
0x140005a27  call    ?AddObjectToMap@CVdsService@@QEAAHPEAUIUnknown@@0@Z; CVdsService::AddObjectToMap(IUnknown *,IUnknown *)
0x140005a2c  test    eax, eax
0x140005a2e  jnz     short loc_140005A52
0x140005a30  call    cs:__imp_GetLastError
0x140005a36  mov     r9d, eax
0x140005a39  lea     r8, aCvdsdisklunVal_5; "CVdsDiskLun::ValidateDiskInterfaces, 11"...
0x140005a40  xor     edx, edx
0x140005a42  mov     ecx, 5Eh ; '^'
0x140005a47  call    cs:__imp_VdsTraceEx
0x140005a4d  jmp     short loc_140005A52
0x140005a4f  mov     ebx, r12d
0x140005a52  cmp     [r14+0E0h], r12
0x140005a59  jnz     short loc_140005A92
0x140005a5b  mov     rcx, r14; this
0x140005a5e  call    ?QueryDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::QueryDiskInterfaces(void)
0x140005a63  mov     ebx, eax
0x140005a65  test    eax, eax
0x140005a67  jns     short loc_140005A92
0x140005a69  mov     r9d, eax
0x140005a6c  lea     r8, aCvdsdisklunVal_9; "CVdsDiskLun::ValidateDiskInterfaces, 12"...
0x140005a73  xor     edx, edx
0x140005a75  mov     ecx, 5Eh ; '^'
0x140005a7a  call    cs:__imp_VdsTraceEx
0x140005a80  mov     [rsp+120h+var_F8], r12
0x140005a85  mov     [rsp+120h+var_100], 205000Eh
0x140005a8d  jmp     loc_1400058C5
0x140005a92  cmp     [r14+110h], r12
0x140005a99  jz      short loc_140005AA4
0x140005a9b  cmp     [r14+100h], r12
0x140005aa2  jnz     short loc_140005AA9
0x140005aa4  mov     ebx, 1
0x140005aa9  mov     rcx, [rbp+57h+var_80+8]; pv
0x140005aad  test    rcx, rcx
0x140005ab0  jz      short loc_140005ABC
0x140005ab2  call    cs:__imp_CoTaskMemFree
0x140005ab8  mov     [rbp+57h+var_80+8], r12
0x140005abc  mov     rcx, [rbp+57h+pv]; pv
0x140005ac0  test    rcx, rcx
0x140005ac3  jz      short loc_140005ACF
0x140005ac5  call    cs:__imp_CoTaskMemFree
0x140005acb  mov     [rbp+57h+pv], r12
0x140005acf  mov     rcx, [rbp+57h+pv+8]; pv
0x140005ad3  test    rcx, rcx
0x140005ad6  jz      short loc_140005AE2
0x140005ad8  call    cs:__imp_CoTaskMemFree
0x140005ade  mov     [rbp+57h+pv+8], r12
0x140005ae2  lea     rcx, [rbp+57h+var_A0]
0x140005ae6  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140005aec  mov     eax, ebx
0x140005aee  mov     rcx, [rbp+57h+var_30]
0x140005af2  xor     rcx, rsp; StackCookie
0x140005af5  call    __security_check_cookie
0x140005afa  lea     r11, [rsp+120h+var_20]
0x140005b02  mov     rbx, [r11+38h]
0x140005b06  mov     rsi, [r11+40h]
0x140005b0a  mov     rsp, r11
0x140005b0d  pop     r15
0x140005b0f  pop     r14
0x140005b11  pop     r12
0x140005b13  pop     rdi
0x140005b14  pop     rbp
0x140005b15  retn
```
