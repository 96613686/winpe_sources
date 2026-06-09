# HostErrorReportingManager::FormatMessageAndPrint(wchar_t *,bool,bool,bool,char *)

- ea: `0x1004183a0`
- end: `0x10041885b`
- name: `?FormatMessageAndPrint@HostErrorReportingManager@@UEAAXPEA_W_N11PEAD@Z`
- size: `1211`
- prototype: `void(HostErrorReportingManager *__hidden this, wchar_t *, bool, bool, bool, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x100416000`
- `0x1004168e0`
- `0x1004183a0`
- `0x100418930`
- `0x1004189a0`

## import_xrefs

- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100418804`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100418804`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x10041846e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100418501`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100418501`
- `sqldk!??_V@YAXPEAX@Z` at `0x100418616`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004186aa`
- `sqldk!??_V@YAXPEAX@Z` at `0x100418824`
- `sqldk!??_V@YAXPEAX@Z` at `0x100418833`
- `sqldk!??_V@YAXPEAX@Z` at `0x100418616`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004186aa`
- `sqldk!??_V@YAXPEAX@Z` at `0x100418824`
- `sqldk!??_V@YAXPEAX@Z` at `0x100418833`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10041857a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100418815`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10041857a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100418815`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004185f0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100418684`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004185f0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100418684`
- `sqldk!SystemThread_TlsIndex` at `0x1004183de`
- `sqldk!SystemThread_TlsIndex` at `0x100418411`
- `sqldk!SystemThread_TlsIndex` at `0x1004184a2`
- `sqldk!SystemThread_TlsIndex` at `0x100418599`
- `sqldk!SystemThread_TlsIndex` at `0x10041862d`
- `sqldk!SystemThread_TlsIndex` at `0x1004187cc`
- `sqldk!SystemThread_TlsOffset` at `0x1004183e8`
- `sqldk!SystemThread_TlsOffset` at `0x10041841a`
- `sqldk!SystemThread_TlsOffset` at `0x1004184ab`
- `sqldk!SystemThread_TlsOffset` at `0x1004185a2`
- `sqldk!SystemThread_TlsOffset` at `0x100418636`
- `sqldk!SystemThread_TlsOffset` at `0x1004187d5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100418402`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100418435`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004184c6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004185bd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100418651`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004187ee`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100418402`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100418435`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004184c6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004185bd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100418651`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004187ee`

## string_xrefs

- `0x1004184ef`: `Sql\Ntdbms\xdb\common\hosterrorreport.cpp`
- `0x1004185d7`: `Sql\Ntdbms\xdb\common\hosterrorreport.cpp`
- `0x10041866b`: `Sql\Ntdbms\xdb\common\hosterrorreport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall HostErrorReportingManager::FormatMessageAndPrint(
        HostErrorReportingManager *this,
        wchar_t *a2,
        __int64 a3,
        unsigned __int8 a4,
        bool a5,
        char *a6)
{
  int v6; // r12d
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rdx
  struct CFormattedParams *v13; // rax
  struct CFormattedParams *v14; // rbx
  int i; // ecx
  __int64 v16; // rbx
  __int64 v17; // rdx
  wchar_t *v18; // rbx
  __int64 v19; // rbx
  __int64 v20; // rdx
  void *v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 v24; // rcx
  unsigned int v25; // [rsp+74h] [rbp-E4h]
  struct CFormattedParams *v26; // [rsp+78h] [rbp-E0h]
  void *v27; // [rsp+80h] [rbp-D8h]
  wchar_t *v28; // [rsp+88h] [rbp-D0h]
  struct CFormattedParams *v29; // [rsp+90h] [rbp-C8h]
  wchar_t *v30; // [rsp+A0h] [rbp-B8h]
  _BYTE v31[16]; // [rsp+E8h] [rbp-70h] BYREF
  _BYTE v32[24]; // [rsp+F8h] [rbp-60h] BYREF
  _BYTE v33[48]; // [rsp+110h] [rbp-48h] BYREF

  v6 = a4;
  if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 256LL) )
    SystemThread::MakeMiniSOSThread(0);
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  if ( (*(_BYTE *)(v10 + 616) & 0x40) == 0 )
  {
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v33, 0, 0, 0, hdl_backout, 0);
      v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v12 = *(_QWORD *)(v11 + 256);
      if ( !v12 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v12 = *(_QWORD *)(v11 + 256);
      }
      v13 = (struct CFormattedParams *)operator new(
                                         0x1248u,
                                         *(struct IMemObj **)(v12 + 1000),
                                         1,
                                         "Sql\\Ntdbms\\xdb\\common\\hosterrorreport.cpp",
                                         379,
                                         6u);
      v14 = v13;
      if ( v13 )
      {
        *((_QWORD *)v13 + 525) = v13;
        *((_DWORD *)v13 + 1052) = 0;
        *((_DWORD *)v13 + 1154) = 0;
        *((_DWORD *)v13 + 1155) = 0;
        for ( i = 0; i < 50; ++i )
          *((_BYTE *)v13 + i + 4624) = 0;
      }
      else
      {
        v14 = 0;
      }
      v29 = v14;
      if ( v14 )
        operator delete(0, 0x1248u);
      v26 = v14;
      v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v17 = *(_QWORD *)(v16 + 256);
      if ( !v17 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v17 = *(_QWORD *)(v16 + 256);
      }
      v18 = (wchar_t *)operator new[](
                         0x1002u,
                         *(struct IMemObj **)(v17 + 1000),
                         1,
                         "Sql\\Ntdbms\\xdb\\common\\hosterrorreport.cpp",
                         383,
                         6u);
      v30 = v18;
      if ( v18 )
        operator delete[](0);
      v28 = v18;
      v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v20 = *(_QWORD *)(v19 + 256);
      if ( !v20 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v20 = *(_QWORD *)(v19 + 256);
      }
      v21 = operator new[](
              0x1002u,
              *(struct IMemObj **)(v20 + 1000),
              1,
              "Sql\\Ntdbms\\xdb\\common\\hosterrorreport.cpp",
              384,
              6u);
      if ( v21 )
        operator delete[](0);
      v27 = v21;
      if ( v29 )
      {
        if ( v30 )
        {
          if ( v21 )
          {
            v22 = -1;
            do
              ++v22;
            while ( a2[v22] );
            if ( (unsigned int)FFormatParams(a2, v22, 0, 0, v30, 2049, 1, a5, v6, 0, v29, 0, a6) )
            {
              v25 = CwchCallFormatMessage(1024, v30, 0, 0, v21, 2048, 0, 0, v29, 1);
              if ( v25 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(HostErrorReportingManager *, void *, _QWORD))(*(_QWORD *)this + 136LL))(
                  this,
                  v21,
                  v25);
              }
            }
          }
        }
      }
      ExcHandler::~ExcHandler((ExcHandler *)v33);
    }
    catch ( SQLError v32 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v31, (const struct SQLError *)v32);
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v31);
      }
      catch ( ShortStackException )
      {
      }
    }
    v23 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v24 = *(_QWORD *)(v23 + 256);
    if ( !v24 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v24 = *(_QWORD *)(v23 + 256);
    }
    if ( *(_DWORD *)(v24 + 556) )
      ExceptionPostCatchActions((struct Worker *)v24);
    operator delete(v26, 0x1248u);
    operator delete[](v27);
    operator delete[](v28);
  }
}

```

## disassembly

```asm
0x1004183a0  mov     rax, rsp
0x1004183a3  push    r13
0x1004183a5  push    r14
0x1004183a7  push    r15
0x1004183a9  sub     rsp, 140h
0x1004183b0  mov     qword ptr [rax-0A8h], 0FFFFFFFFFFFFFFFEh
0x1004183bb  mov     [rax+8], rbx
0x1004183bf  mov     [rax+10h], rsi
0x1004183c3  mov     [rax+18h], rdi
0x1004183c7  mov     [rax+20h], r12
0x1004183cb  movzx   r12d, r9b
0x1004183cf  mov     r14, rdx
0x1004183d2  mov     r15, rcx
0x1004183d5  mov     r11, gs:58h
0x1004183de  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004183e5  mov     r8d, [rax]
0x1004183e8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004183ef  mov     r10d, [rax]
0x1004183f2  add     r10, [r11+r8*8]
0x1004183f6  cmp     qword ptr [r10+100h], 0
0x1004183fe  jnz     short loc_100418408
0x100418400  xor     ecx, ecx
0x100418402  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100418408  mov     rdx, gs:58h
0x100418411  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100418418  mov     ecx, [rax]
0x10041841a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100418421  mov     ebx, [rax]
0x100418423  add     rbx, [rdx+rcx*8]
0x100418427  mov     rax, [rbx+100h]
0x10041842e  test    rax, rax
0x100418431  jnz     short loc_100418442
0x100418433  xor     ecx, ecx
0x100418435  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041843b  mov     rax, [rbx+100h]
0x100418442  test    byte ptr [rax+268h], 40h
0x100418449  jnz     loc_100418839
0x10041844f  xor     r13d, r13d
0x100418452  mov     [rsp+158h+var_D0], r13
0x10041845a  mov     [rsp+158h+var_D8], r13
0x100418462  mov     [rsp+158h+var_E0], r13
0x100418467  xor     edx, edx; unsigned __int16
0x100418469  mov     [rsp+158h+var_130], r13; struct Worker *
0x10041846e  mov     rax, cs:__imp_?hdl_backout@@YAHHHHHPEAD@Z; hdl_backout(int,int,int,int,char *)
0x100418475  mov     [rsp+158h+var_138], rax; int (*)(int, int, int, int, char *)
0x10041847a  xor     r9d, r9d; unsigned __int8
0x10041847d  xor     r8d, r8d; unsigned __int8
0x100418480  lea     rcx, [rsp+158h+var_48]; this
0x100418488  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10041848d  nop
0x10041848e  mov     [rsp+158h+var_C0], 17Bh
0x100418499  mov     rdx, gs:58h
0x1004184a2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004184a9  mov     ecx, [rax]
0x1004184ab  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004184b2  mov     ebx, [rax]
0x1004184b4  add     rbx, [rdx+rcx*8]
0x1004184b8  mov     rdx, [rbx+100h]
0x1004184bf  test    rdx, rdx
0x1004184c2  jnz     short loc_1004184D3
0x1004184c4  xor     ecx, ecx
0x1004184c6  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004184cc  mov     rdx, [rbx+100h]
0x1004184d3  mov     rdx, [rdx+3E8h]
0x1004184da  mov     [rsp+158h+var_A0], rdx
0x1004184e2  mov     byte ptr [rsp+158h+var_130], 6
0x1004184e7  mov     dword ptr [rsp+158h+var_138], 17Bh
0x1004184ef  lea     r9, aSqlNtdbmsXdbCo; "Sql\\Ntdbms\\xdb\\common\\hosterrorrepo"...
0x1004184f6  mov     ecx, 1248h
0x1004184fb  mov     r8d, 1
0x100418501  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100418507  mov     rbx, rax
0x10041850a  mov     [rsp+158h+var_98], rax
0x100418512  test    rax, rax
0x100418515  jz      short loc_100418558
0x100418517  mov     [rax+1068h], rax
0x10041851e  mov     [rax+1070h], r13d
0x100418525  mov     [rax+1208h], r13d
0x10041852c  mov     [rax+120Ch], r13d
0x100418533  mov     [rsp+158h+var_E8], r13d
0x100418538  mov     ecx, r13d
0x10041853b  nop     dword ptr [rax+rax+00h]
0x100418540  cmp     ecx, 32h ; '2'
0x100418543  jge     short loc_10041855B
0x100418545  movsxd  rax, ecx
0x100418548  mov     byte ptr [rax+rbx+1210h], 0
0x100418550  inc     ecx
0x100418552  mov     [rsp+158h+var_E8], ecx
0x100418556  jmp     short loc_100418540
0x100418558  mov     rbx, r13
0x10041855b  mov     [rsp+158h+var_C8], rbx
0x100418563  mov     rcx, [rsp+158h+var_E0]
0x100418568  cmp     rcx, rbx
0x10041856b  jz      short loc_100418580
0x10041856d  mov     [rsp+158h+var_90], rcx
0x100418575  mov     edx, 1248h
0x10041857a  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100418580  mov     [rsp+158h+var_E0], rbx
0x100418585  mov     [rsp+158h+var_BC], 801h
0x100418590  mov     rdx, gs:58h
0x100418599  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004185a0  mov     ecx, [rax]
0x1004185a2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004185a9  mov     ebx, [rax]
0x1004185ab  add     rbx, [rdx+rcx*8]
0x1004185af  mov     rdx, [rbx+100h]
0x1004185b6  test    rdx, rdx
0x1004185b9  jnz     short loc_1004185CA
0x1004185bb  xor     ecx, ecx
0x1004185bd  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004185c3  mov     rdx, [rbx+100h]
0x1004185ca  mov     byte ptr [rsp+158h+var_130], 6
0x1004185cf  mov     dword ptr [rsp+158h+var_138], 17Fh
0x1004185d7  lea     r9, aSqlNtdbmsXdbCo; "Sql\\Ntdbms\\xdb\\common\\hosterrorrepo"...
0x1004185de  mov     r8d, 1
0x1004185e4  mov     rdx, [rdx+3E8h]
0x1004185eb  mov     ecx, 1002h
0x1004185f0  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004185f6  mov     rbx, rax
0x1004185f9  mov     [rsp+158h+var_B8], rax
0x100418601  mov     rcx, [rsp+158h+var_D0]
0x100418609  cmp     rcx, rax
0x10041860c  jz      short loc_10041861C
0x10041860e  mov     [rsp+158h+var_88], rcx
0x100418616  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10041861c  mov     [rsp+158h+var_D0], rbx
0x100418624  mov     rdx, gs:58h
0x10041862d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100418634  mov     ecx, [rax]
0x100418636  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041863d  mov     ebx, [rax]
0x10041863f  add     rbx, [rdx+rcx*8]
0x100418643  mov     rdx, [rbx+100h]
0x10041864a  test    rdx, rdx
0x10041864d  jnz     short loc_10041865E
0x10041864f  xor     ecx, ecx
0x100418651  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100418657  mov     rdx, [rbx+100h]
0x10041865e  mov     byte ptr [rsp+158h+var_130], 6
0x100418663  mov     dword ptr [rsp+158h+var_138], 180h
0x10041866b  lea     r9, aSqlNtdbmsXdbCo; "Sql\\Ntdbms\\xdb\\common\\hosterrorrepo"...
0x100418672  mov     r8d, 1
0x100418678  mov     rdx, [rdx+3E8h]
0x10041867f  mov     ecx, 1002h
0x100418684  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10041868a  mov     rbx, rax
0x10041868d  mov     [rsp+158h+var_B0], rax
0x100418695  mov     rcx, [rsp+158h+var_D8]
0x10041869d  cmp     rcx, rax
0x1004186a0  jz      short loc_1004186B0
0x1004186a2  mov     [rsp+158h+var_80], rcx
0x1004186aa  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004186b0  mov     [rsp+158h+var_D8], rbx
0x1004186b8  mov     rdi, [rsp+158h+var_C8]
0x1004186c0  test    rdi, rdi
0x1004186c3  jz      loc_1004187B5
0x1004186c9  mov     rsi, [rsp+158h+var_B8]
0x1004186d1  test    rsi, rsi
0x1004186d4  jz      loc_1004187B5
0x1004186da  test    rbx, rbx
0x1004186dd  jz      loc_1004187B5
0x1004186e3  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1004186ea  nop     word ptr [rax+rax+00h]
0x1004186f0  inc     rdx; int
0x1004186f3  cmp     word ptr [r14+rdx*2], 0
0x1004186f9  jnz     short loc_1004186F0
0x1004186fb  mov     [rsp+158h+var_78], rdx
0x100418703  movzx   r8d, [rsp+158h+arg_20]
0x10041870c  mov     rax, [rsp+158h+arg_28]
0x100418714  mov     [rsp+158h+var_F8], rax; char *
0x100418719  mov     [rsp+158h+var_100], r13; enum EFormatType *
0x10041871e  mov     [rsp+158h+var_108], rdi; struct CFormattedParams *
0x100418723  mov     [rsp+158h+var_110], r13d; int
0x100418728  mov     [rsp+158h+var_118], r12d; int
0x10041872d  mov     [rsp+158h+var_120], r8d; int
0x100418732  mov     [rsp+158h+var_128], 1; int
0x10041873a  mov     dword ptr [rsp+158h+var_130], 801h; int
0x100418742  mov     [rsp+158h+var_138], rsi; wchar_t *
0x100418747  xor     r9d, r9d; int
0x10041874a  xor     r8d, r8d; wchar_t *
0x10041874d  mov     rcx, r14; wchar_t *
0x100418750  call    ?FFormatParams@@YAHPEB_WHPEA_WH1HHHHHPEAVCFormattedParams@@PEBW4EFormatType@@PEAD@Z; FFormatParams(wchar_t const *,int,wchar_t *,int,wchar_t *,int,int,int,int,int,CFormattedParams *,EFormatType const *,char *)
0x100418755  test    eax, eax
0x100418757  jz      short loc_1004187B5
0x100418759  xor     r9d, r9d
0x10041875c  mov     [rsp+158h+var_110], 1
0x100418764  mov     qword ptr [rsp+158h+var_118], rdi
0x100418769  mov     [rsp+158h+var_120], r13d
0x10041876e  mov     qword ptr [rsp+158h+var_128], r13
0x100418773  mov     dword ptr [rsp+158h+var_130], 800h
0x10041877b  mov     [rsp+158h+var_138], rbx
0x100418780  xor     r8d, r8d
0x100418783  mov     rdx, rsi
0x100418786  mov     ecx, 400h
0x10041878b  call    ?CwchCallFormatMessage@@YAHKPEAXPEBVCErrorEventId@@FPEA_WH2HPEAVCFormattedParams@@W4EFormatMethod@@@Z; CwchCallFormatMessage(ulong,void *,CErrorEventId const *,short,wchar_t *,int,wchar_t *,int,CFormattedParams *,EFormatMethod)
0x100418790  mov     [rsp+158h+var_E4], eax
0x100418794  test    eax, eax
0x100418796  jz      short loc_1004187B5
0x100418798  lfence
0x10041879b  mov     rax, [r15]
0x10041879e  mov     r8d, [rsp+158h+var_E4]
0x1004187a3  mov     rdx, [rsp+158h+var_B0]
0x1004187ab  mov     rcx, r15
0x1004187ae  call    qword ptr [rax+88h]
0x1004187b4  nop
0x1004187b5  lea     rcx, [rsp+158h+var_48]; this
0x1004187bd  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x1004187c2  nop
0x1004187c3  mov     rdx, gs:58h
0x1004187cc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004187d3  mov     ecx, [rax]
0x1004187d5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004187dc  mov     ebx, [rax]
0x1004187de  add     rbx, [rdx+rcx*8]
0x1004187e2  mov     rcx, [rbx+100h]
0x1004187e9  test    rcx, rcx
0x1004187ec  jnz     short loc_1004187FB
0x1004187ee  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004187f4  mov     rcx, [rbx+100h]
0x1004187fb  cmp     dword ptr [rcx+22Ch], 0
0x100418802  jz      short loc_10041880B
0x100418804  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x10041880a  nop
0x10041880b  mov     edx, 1248h
0x100418810  mov     rcx, [rsp+158h+var_E0]
0x100418815  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10041881b  nop
0x10041881c  mov     rcx, [rsp+158h+var_D8]
0x100418824  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10041882a  nop
0x10041882b  mov     rcx, [rsp+158h+var_D0]
0x100418833  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100418839  lea     r11, [rsp+158h+var_18]
0x100418841  mov     rbx, [r11+20h]
0x100418845  mov     rsi, [r11+28h]
0x100418849  mov     rdi, [r11+30h]
0x10041884d  mov     r12, [r11+38h]
0x100418851  mov     rsp, r11
0x100418854  pop     r15
0x100418856  pop     r14
0x100418858  pop     r13
0x10041885a  retn
```
