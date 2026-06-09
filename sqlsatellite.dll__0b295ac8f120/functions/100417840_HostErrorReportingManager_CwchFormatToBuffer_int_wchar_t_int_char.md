# HostErrorReportingManager::CwchFormatToBuffer(int,wchar_t *,int,char *)

- ea: `0x100417840`
- end: `0x100417da4`
- name: `?CwchFormatToBuffer@HostErrorReportingManager@@UEAAHHPEA_WHPEAD@Z`
- size: `1380`
- prototype: `__int64 __fastcall(HostErrorReportingManager *__hidden this, int, wchar_t *, int, char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x100416000`
- `0x1004166a0`
- `0x1004168e0`
- `0x100417840`
- `0x100418930`
- `0x1004189a0`
- `0x10045d510`

## import_xrefs

- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100417d7c`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100417d7c`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x1004178f9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100417a36`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100417a36`
- `sqldk!??_V@YAXPEAX@Z` at `0x100417bef`
- `sqldk!??_V@YAXPEAX@Z` at `0x100417bef`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100417aa0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100417cc5`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100417d26`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100417aa0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100417cc5`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100417d26`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100417b0e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100417b0e`
- `sqldk!SystemThread_TlsIndex` at `0x100417882`
- `sqldk!SystemThread_TlsIndex` at `0x1004178b4`
- `sqldk!SystemThread_TlsIndex` at `0x10041792b`
- `sqldk!SystemThread_TlsIndex` at `0x10041795c`
- `sqldk!SystemThread_TlsIndex` at `0x1004179d7`
- `sqldk!SystemThread_TlsIndex` at `0x100417ab7`
- `sqldk!SystemThread_TlsIndex` at `0x100417d44`
- `sqldk!SystemThread_TlsOffset` at `0x10041788c`
- `sqldk!SystemThread_TlsOffset` at `0x1004178bd`
- `sqldk!SystemThread_TlsOffset` at `0x100417934`
- `sqldk!SystemThread_TlsOffset` at `0x100417965`
- `sqldk!SystemThread_TlsOffset` at `0x1004179e0`
- `sqldk!SystemThread_TlsOffset` at `0x100417ac0`
- `sqldk!SystemThread_TlsOffset` at `0x100417d4d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004178a5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004178d8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041794d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417980`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004179fb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417adb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417d66`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004178a5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004178d8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041794d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417980`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004179fb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417adb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417d66`

## string_xrefs

- `0x100417a24`: `Sql\Ntdbms\xdb\common\hosterrorreport.cpp`
- `0x100417af5`: `Sql\Ntdbms\xdb\common\hosterrorreport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall HostErrorReportingManager::CwchFormatToBuffer(
        HostErrorReportingManager *this,
        int a2,
        wchar_t *a3,
        int a4,
        char *a5)
{
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rbx
  __int64 v15; // rdx
  struct CFormattedParams *v16; // rax
  struct CFormattedParams *v17; // rbx
  int i; // ecx
  __int64 v19; // rbx
  __int64 v20; // rdx
  wchar_t *v21; // rdi
  struct CFormattedParams *v22; // rbx
  int v23; // ecx
  int v24; // eax
  unsigned __int16 v25; // ax
  unsigned int v26; // esi
  __int64 v28; // rbx
  __int64 v29; // rcx
  wchar_t *v30; // [rsp+20h] [rbp-128h]
  BOOL v31; // [rsp+70h] [rbp-D8h]
  struct CFormattedParams *v32; // [rsp+78h] [rbp-D0h] BYREF
  int v33; // [rsp+80h] [rbp-C8h] BYREF
  __m128i si128; // [rsp+84h] [rbp-C4h]
  int v35; // [rsp+98h] [rbp-B0h]
  int v36; // [rsp+9Ch] [rbp-ACh] BYREF
  int v37; // [rsp+A0h] [rbp-A8h] BYREF
  struct CFormattedParams *v38; // [rsp+A8h] [rbp-A0h]
  int v39[2]; // [rsp+B0h] [rbp-98h] BYREF
  __int64 v40; // [rsp+C0h] [rbp-88h]
  struct CFormattedParams *v41; // [rsp+C8h] [rbp-80h]
  wchar_t *v42; // [rsp+D0h] [rbp-78h]
  _BYTE v43[72]; // [rsp+E8h] [rbp-60h] BYREF
  int v44; // [rsp+160h] [rbp+18h] BYREF

  v40 = -2;
  *a3 = 0;
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
  if ( (*(_BYTE *)(v10 + 616) & 0x40) != 0 )
    return 0;
  ExcHandler::ExcHandler((ExcHandler *)v43, 0, 0, 0, hdl_backout, 0);
  if ( a4 > 0 )
    *a3 = 0;
  if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 256LL) )
    SystemThread::MakeMiniSOSThread(0);
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v12 = *(_QWORD *)(v11 + 256);
  if ( !v12 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v12 = *(_QWORD *)(v11 + 256);
  }
  v13 = *(_DWORD *)(v12 + 616);
  v31 = 1;
  v33 = a2;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v38 = 0;
  if ( (v13 & 0x40) == 0 )
  {
    v44 = 109;
    v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v15 = *(_QWORD *)(v14 + 256);
    if ( !v15 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v15 = *(_QWORD *)(v14 + 256);
    }
    *(_QWORD *)v39 = *(_QWORD *)(v15 + 1000);
    v16 = (struct CFormattedParams *)operator new(
                                       0x1248u,
                                       *(struct IMemObj **)v39,
                                       1,
                                       "Sql\\Ntdbms\\xdb\\common\\hosterrorreport.cpp",
                                       109,
                                       6u);
    v17 = v16;
    v41 = v16;
    if ( v16 )
    {
      *((_QWORD *)v16 + 525) = v16;
      *((_DWORD *)v16 + 1052) = 0;
      *((_DWORD *)v16 + 1154) = 0;
      *((_DWORD *)v16 + 1155) = 0;
      for ( i = 0; ; ++i )
      {
        v35 = i;
        if ( i >= 50 )
          break;
        *((_BYTE *)v16 + i + 4624) = 0;
      }
    }
    else
    {
      v17 = 0;
    }
    v32 = v17;
    if ( v38 != v17 )
      operator delete(v38, 0x1248u);
    v38 = v17;
    v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v20 = *(_QWORD *)(v19 + 256);
    if ( !v20 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v20 = *(_QWORD *)(v19 + 256);
    }
    v21 = (wchar_t *)operator new[](
                       0x1000u,
                       *(struct IMemObj **)(v20 + 1000),
                       1,
                       "Sql\\Ntdbms\\xdb\\common\\hosterrorreport.cpp",
                       111,
                       6u);
    v42 = v21;
    v22 = v32;
    if ( v21 )
    {
      if ( v32 )
      {
        LODWORD(v32) = 0;
        v39[0] = 0;
        v44 = 0;
        if ( (unsigned int)FGetMsgFormatSpecs((struct SQLError *)&v33, (int *)&v32, v39, &v44, v21, 2048, &v36) )
          v31 = FFormatParams(v21, v36, 0, 0, 0, 0, 1, 1, 1, 0, v22, 0, a5) == 0;
      }
    }
    operator delete[](v21);
    a2 = v33;
    if ( !v31 )
    {
      if ( si128.m128i_i32[3] == 1 )
      {
        v23 = si128.m128i_i32[0];
        if ( si128.m128i_i32[1] >= 0 )
          v23 = si128.m128i_i32[1];
        if ( v23 )
        {
          v24 = -1073724761;
          if ( v23 <= 10 )
            v24 = 1073758885;
        }
        else
        {
          v24 = 1073758884;
        }
      }
      else
      {
        if ( (v33 & 0xFFFF0000) != 0 )
          goto LABEL_42;
        if ( si128.m128i_i32[1] >= 11 )
        {
          v24 = v33 | 0xC0000000;
          goto LABEL_43;
        }
        if ( si128.m128i_i32[1] <= 0 )
LABEL_42:
          v24 = v33;
        else
          v24 = v33 | 0x40000000;
      }
LABEL_43:
      v37 = v24;
      v25 = (*(__int64 (__fastcall **)(HostErrorReportingManager *, _QWORD))(*(_QWORD *)this + 120LL))(this, 0);
      v26 = CwchCallFormatMessage(2048, 0, &v37, v25, a3, a4, 0, 0, v22, 1);
      if ( v26 )
      {
        operator delete(v22, 0x1248u);
        ExcHandler::~ExcHandler((ExcHandler *)v43);
        return v26;
      }
    }
  }
  LODWORD(v30) = si128.m128i_i32[2];
  SOSLogToErrorLog(
    L"[CwchFormatToBuffer] SQLError: Major: %d, Minor: %d, Severity: %d, State: %d",
    (unsigned int)(a2 / 100),
    (unsigned int)(a2 % 100),
    si128.m128i_u32[0],
    v30);
  operator delete(v38, 0x1248u);
  ExcHandler::~ExcHandler((ExcHandler *)v43);
  v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v29 = *(_QWORD *)(v28 + 256);
  if ( !v29 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v29 = *(_QWORD *)(v28 + 256);
  }
  if ( *(_DWORD *)(v29 + 556) )
    ExceptionPostCatchActions((struct Worker *)v29);
  return 0;
}

```

## disassembly

```asm
0x100417840  mov     rax, rsp
0x100417843  push    r12
0x100417845  push    r14
0x100417847  push    r15
0x100417849  sub     rsp, 130h
0x100417850  mov     qword ptr [rax-88h], 0FFFFFFFFFFFFFFFEh
0x10041785b  mov     [rax+8], rbx
0x10041785f  mov     [rax+10h], rsi
0x100417863  mov     [rax+20h], rdi
0x100417867  mov     r14d, r9d
0x10041786a  mov     rsi, r8
0x10041786d  mov     edi, edx
0x10041786f  mov     r15, rcx
0x100417872  xor     r12d, r12d
0x100417875  mov     [r8], r12w
0x100417879  mov     rbx, gs:58h
0x100417882  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100417889  mov     r10d, [rax]
0x10041788c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100417893  mov     r11d, [rax]
0x100417896  add     r11, [rbx+r10*8]
0x10041789a  cmp     [r11+100h], r12
0x1004178a1  jnz     short loc_1004178AB
0x1004178a3  xor     ecx, ecx
0x1004178a5  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004178ab  mov     rdx, gs:58h
0x1004178b4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004178bb  mov     ecx, [rax]
0x1004178bd  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004178c4  mov     ebx, [rax]
0x1004178c6  add     rbx, [rdx+rcx*8]
0x1004178ca  mov     rax, [rbx+100h]
0x1004178d1  test    rax, rax
0x1004178d4  jnz     short loc_1004178E5
0x1004178d6  xor     ecx, ecx
0x1004178d8  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004178de  mov     rax, [rbx+100h]
0x1004178e5  test    byte ptr [rax+268h], 40h
0x1004178ec  jnz     loc_100417D82
0x1004178f2  xor     edx, edx; unsigned __int16
0x1004178f4  mov     [rsp+148h+var_120], r12; struct Worker *
0x1004178f9  mov     rax, cs:__imp_?hdl_backout@@YAHHHHHPEAD@Z; hdl_backout(int,int,int,int,char *)
0x100417900  mov     [rsp+148h+var_128], rax; int (*)(int, int, int, int, char *)
0x100417905  xor     r9d, r9d; unsigned __int8
0x100417908  xor     r8d, r8d; unsigned __int8
0x10041790b  lea     rcx, [rsp+148h+var_60]; this
0x100417913  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x100417918  nop
0x100417919  test    r14d, r14d
0x10041791c  jle     short loc_100417922
0x10041791e  mov     [rsi], r12w
0x100417922  mov     r8, gs:58h
0x10041792b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100417932  mov     ecx, [rax]
0x100417934  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041793b  mov     edx, [rax]
0x10041793d  add     rdx, [r8+rcx*8]
0x100417941  cmp     qword ptr [rdx+100h], 0
0x100417949  jnz     short loc_100417953
0x10041794b  xor     ecx, ecx
0x10041794d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100417953  mov     rdx, gs:58h
0x10041795c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100417963  mov     ecx, [rax]
0x100417965  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041796c  mov     ebx, [rax]
0x10041796e  add     rbx, [rdx+rcx*8]
0x100417972  mov     rax, [rbx+100h]
0x100417979  test    rax, rax
0x10041797c  jnz     short loc_10041798D
0x10041797e  xor     ecx, ecx
0x100417980  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100417986  mov     rax, [rbx+100h]
0x10041798d  mov     eax, [rax+268h]
0x100417993  mov     [rsp+148h+var_D8], 1
0x10041799b  mov     [rsp+148h+var_C8], edi
0x1004179a2  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x1004179aa  movdqu  [rsp+148h+var_C4], xmm0
0x1004179b3  mov     [rsp+148h+var_A0], r12
0x1004179bb  test    al, 40h
0x1004179bd  jnz     loc_100417CE0
0x1004179c3  mov     [rsp+148h+arg_10], 6Dh ; 'm'
0x1004179ce  mov     rdx, gs:58h
0x1004179d7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004179de  mov     ecx, [rax]
0x1004179e0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004179e7  mov     ebx, [rax]
0x1004179e9  add     rbx, [rdx+rcx*8]
0x1004179ed  mov     rdx, [rbx+100h]
0x1004179f4  test    rdx, rdx
0x1004179f7  jnz     short loc_100417A08
0x1004179f9  xor     ecx, ecx
0x1004179fb  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100417a01  mov     rdx, [rbx+100h]
0x100417a08  mov     rdx, [rdx+3E8h]
0x100417a0f  mov     qword ptr [rsp+148h+var_98], rdx
0x100417a17  mov     byte ptr [rsp+148h+var_120], 6
0x100417a1c  mov     dword ptr [rsp+148h+var_128], 6Dh ; 'm'
0x100417a24  lea     r9, aSqlNtdbmsXdbCo; "Sql\\Ntdbms\\xdb\\common\\hosterrorrepo"...
0x100417a2b  mov     ecx, 1248h
0x100417a30  mov     r8d, 1
0x100417a36  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100417a3c  mov     rbx, rax
0x100417a3f  mov     [rsp+148h+var_80], rax
0x100417a47  test    rax, rax
0x100417a4a  jz      short loc_100417A86
0x100417a4c  mov     [rax+1068h], rax
0x100417a53  mov     [rax+1070h], r12d
0x100417a5a  mov     [rax+1208h], r12d
0x100417a61  mov     [rax+120Ch], r12d
0x100417a68  mov     ecx, r12d
0x100417a6b  mov     [rsp+148h+var_B0], ecx
0x100417a72  cmp     ecx, 32h ; '2'
0x100417a75  jge     short loc_100417A89
0x100417a77  movsxd  rax, ecx
0x100417a7a  mov     byte ptr [rax+rbx+1210h], 0
0x100417a82  inc     ecx
0x100417a84  jmp     short loc_100417A6B
0x100417a86  mov     rbx, r12
0x100417a89  mov     [rsp+148h+var_D0], rbx
0x100417a8e  mov     rcx, [rsp+148h+var_A0]
0x100417a96  cmp     rcx, rbx
0x100417a99  jz      short loc_100417AA6
0x100417a9b  mov     edx, 1248h
0x100417aa0  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100417aa6  mov     [rsp+148h+var_A0], rbx
0x100417aae  mov     rdx, gs:58h
0x100417ab7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100417abe  mov     ecx, [rax]
0x100417ac0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100417ac7  mov     ebx, [rax]
0x100417ac9  add     rbx, [rdx+rcx*8]
0x100417acd  mov     rdx, [rbx+100h]
0x100417ad4  test    rdx, rdx
0x100417ad7  jnz     short loc_100417AE8
0x100417ad9  xor     ecx, ecx
0x100417adb  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100417ae1  mov     rdx, [rbx+100h]
0x100417ae8  mov     byte ptr [rsp+148h+var_120], 6
0x100417aed  mov     dword ptr [rsp+148h+var_128], 6Fh ; 'o'
0x100417af5  lea     r9, aSqlNtdbmsXdbCo; "Sql\\Ntdbms\\xdb\\common\\hosterrorrepo"...
0x100417afc  mov     r8d, 1
0x100417b02  mov     rdx, [rdx+3E8h]
0x100417b09  mov     ecx, 1000h
0x100417b0e  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100417b14  mov     rdi, rax
0x100417b17  mov     [rsp+148h+var_78], rax
0x100417b1f  mov     rbx, [rsp+148h+var_D0]
0x100417b24  test    rax, rax
0x100417b27  jz      loc_100417BEC
0x100417b2d  test    rbx, rbx
0x100417b30  jz      loc_100417BEC
0x100417b36  mov     dword ptr [rsp+148h+var_D0], r12d
0x100417b3b  mov     [rsp+148h+var_98], r12d
0x100417b43  mov     [rsp+148h+arg_10], r12d
0x100417b4b  lea     rax, [rsp+148h+var_AC]
0x100417b53  mov     [rsp+148h+var_118], rax; int *
0x100417b58  mov     dword ptr [rsp+148h+var_120], 800h; int
0x100417b60  mov     [rsp+148h+var_128], rdi; wchar_t *
0x100417b65  lea     r9, [rsp+148h+arg_10]; int *
0x100417b6d  lea     r8, [rsp+148h+var_98]; int *
0x100417b75  lea     rdx, [rsp+148h+var_D0]; int *
0x100417b7a  lea     rcx, [rsp+148h+var_C8]; struct SQLError *
0x100417b82  call    ?FGetMsgFormatSpecs@@YAHPEAVSQLError@@PEAH11PEA_WH1@Z; FGetMsgFormatSpecs(SQLError *,int *,int *,int *,wchar_t *,int,int *)
0x100417b87  test    eax, eax
0x100417b89  jz      short loc_100417BEC
0x100417b8b  mov     rax, [rsp+148h+arg_20]
0x100417b93  mov     [rsp+148h+var_E8], rax; char *
0x100417b98  mov     [rsp+148h+var_F0], r12; enum EFormatType *
0x100417b9d  mov     [rsp+148h+var_F8], rbx; struct CFormattedParams *
0x100417ba2  mov     [rsp+148h+var_100], r12d; int
0x100417ba7  mov     [rsp+148h+var_108], 1; int
0x100417baf  mov     [rsp+148h+var_110], 1; int
0x100417bb7  mov     dword ptr [rsp+148h+var_118], 1; int
0x100417bbf  mov     dword ptr [rsp+148h+var_120], r12d; int
0x100417bc4  mov     [rsp+148h+var_128], r12; wchar_t *
0x100417bc9  xor     r9d, r9d; int
0x100417bcc  xor     r8d, r8d; wchar_t *
0x100417bcf  mov     edx, [rsp+148h+var_AC]; int
0x100417bd6  mov     rcx, rdi; wchar_t *
0x100417bd9  call    ?FFormatParams@@YAHPEB_WHPEA_WH1HHHHHPEAVCFormattedParams@@PEBW4EFormatType@@PEAD@Z; FFormatParams(wchar_t const *,int,wchar_t *,int,wchar_t *,int,int,int,int,int,CFormattedParams *,EFormatType const *,char *)
0x100417bde  mov     ecx, [rsp+148h+var_D8]
0x100417be2  test    eax, eax
0x100417be4  cmovnz  ecx, r12d
0x100417be8  mov     [rsp+148h+var_D8], ecx
0x100417bec  mov     rcx, rdi
0x100417bef  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100417bf5  mov     edi, [rsp+148h+var_C8]
0x100417bfc  cmp     [rsp+148h+var_D8], 0
0x100417c01  jnz     loc_100417CE0
0x100417c07  cmp     dword ptr [rsp+148h+var_C4+0Ch], 1
0x100417c0f  jnz     short loc_100417C41
0x100417c11  mov     ecx, dword ptr [rsp+148h+var_C4]
0x100417c18  mov     eax, dword ptr [rsp+148h+var_C4+4]
0x100417c1f  test    eax, eax
0x100417c21  cmovns  ecx, eax
0x100417c24  test    ecx, ecx
0x100417c26  jnz     short loc_100417C2F
0x100417c28  mov     eax, 400042A4h
0x100417c2d  jmp     short loc_100417C6C
0x100417c2f  mov     eax, 0C00042A7h
0x100417c34  mov     edx, 400042A5h
0x100417c39  cmp     ecx, 0Ah
0x100417c3c  cmovle  eax, edx
0x100417c3f  jmp     short loc_100417C6C
0x100417c41  test    edi, 0FFFF0000h
0x100417c47  jnz     short loc_100417C6A
0x100417c49  mov     eax, dword ptr [rsp+148h+var_C4+4]
0x100417c50  cmp     eax, 0Bh
0x100417c53  jl      short loc_100417C5E
0x100417c55  mov     eax, edi
0x100417c57  or      eax, 0C0000000h
0x100417c5c  jmp     short loc_100417C6C
0x100417c5e  test    eax, eax
0x100417c60  jle     short loc_100417C6A
0x100417c62  mov     eax, edi
0x100417c64  bts     eax, 1Eh
0x100417c68  jmp     short loc_100417C6C
0x100417c6a  mov     eax, edi
0x100417c6c  mov     [rsp+148h+var_A8], eax
0x100417c73  mov     rax, [r15]
0x100417c76  xor     edx, edx
0x100417c78  mov     rcx, r15
0x100417c7b  call    qword ptr [rax+78h]
0x100417c7e  movzx   r9d, ax
0x100417c82  mov     [rsp+148h+var_100], 1
0x100417c8a  mov     qword ptr [rsp+148h+var_108], rbx
0x100417c8f  mov     [rsp+148h+var_110], r12d
0x100417c94  mov     [rsp+148h+var_118], r12
0x100417c99  mov     dword ptr [rsp+148h+var_120], r14d
0x100417c9e  mov     [rsp+148h+var_128], rsi
0x100417ca3  lea     r8, [rsp+148h+var_A8]
0x100417cab  xor     edx, edx
0x100417cad  mov     ecx, 800h
0x100417cb2  call    ?CwchCallFormatMessage@@YAHKPEAXPEBVCErrorEventId@@FPEA_WH2HPEAVCFormattedParams@@W4EFormatMethod@@@Z; CwchCallFormatMessage(ulong,void *,CErrorEventId const *,short,wchar_t *,int,wchar_t *,int,CFormattedParams *,EFormatMethod)
0x100417cb7  mov     esi, eax
0x100417cb9  test    eax, eax
0x100417cbb  jz      short loc_100417CE0
0x100417cbd  mov     edx, 1248h
0x100417cc2  mov     rcx, rbx
0x100417cc5  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100417ccb  nop
0x100417ccc  lea     rcx, [rsp+148h+var_60]; this
0x100417cd4  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x100417cd9  mov     eax, esi
0x100417cdb  jmp     loc_100417D84
0x100417ce0  mov     eax, 51EB851Fh
0x100417ce5  imul    edi
0x100417ce7  sar     edx, 5
0x100417cea  mov     eax, edx
0x100417cec  shr     eax, 1Fh
0x100417cef  add     edx, eax
0x100417cf1  imul    eax, edx, 64h ; 'd'
0x100417cf4  sub     edi, eax
0x100417cf6  mov     eax, dword ptr [rsp+148h+var_C4+8]
0x100417cfd  mov     dword ptr [rsp+148h+var_128], eax
0x100417d01  mov     r9d, dword ptr [rsp+148h+var_C4]
0x100417d09  mov     r8d, edi
0x100417d0c  lea     rcx, aCwchformattobu; "[CwchFormatToBuffer] SQLError: Major: %"...
0x100417d13  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x100417d18  nop
0x100417d19  mov     edx, 1248h
0x100417d1e  mov     rcx, [rsp+148h+var_A0]
0x100417d26  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100417d2c  nop
0x100417d2d  lea     rcx, [rsp+148h+var_60]; this
0x100417d35  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x100417d3a  nop
0x100417d3b  mov     rdx, gs:58h
0x100417d44  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100417d4b  mov     ecx, [rax]
0x100417d4d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100417d54  mov     ebx, [rax]
0x100417d56  add     rbx, [rdx+rcx*8]
0x100417d5a  mov     rcx, [rbx+100h]
0x100417d61  test    rcx, rcx
0x100417d64  jnz     short loc_100417D73
0x100417d66  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100417d6c  mov     rcx, [rbx+100h]
0x100417d73  cmp     dword ptr [rcx+22Ch], 0
0x100417d7a  jz      short loc_100417D82
0x100417d7c  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x100417d82  xor     eax, eax
0x100417d84  lea     r11, [rsp+148h+var_18]
0x100417d8c  mov     rbx, [r11+20h]
0x100417d90  mov     rsi, [r11+28h]
0x100417d94  mov     rdi, [r11+38h]
0x100417d98  mov     rsp, r11
0x100417d9b  pop     r15
0x100417d9d  pop     r14
0x100417d9f  pop     r12
0x100417da1  retn
0x100417da2  jmp     short loc_100417D82
```
