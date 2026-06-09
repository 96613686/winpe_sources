# Sspi::MakeSignature(SNI_Packet *,ulong,ulong)

- ea: `0x100440770`
- end: `0x100440c24`
- name: `?MakeSignature@Sspi@@AEAAKPEAVSNI_Packet@@KK@Z`
- size: `1204`
- prototype: `unsigned int __fastcall(Sspi *__hidden this, struct SNI_Packet *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x10043fd90`
- `0x100442df0`

## callees

- `0x100405270`
- `0x100405390`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100440770`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1004409d9`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1004409d9`
- `sqldk!??_V@YAXPEAX@Z` at `0x100440bac`
- `sqldk!??_V@YAXPEAX@Z` at `0x100440bac`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100440879`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100440879`
- `sqldk!SystemThread_TlsIndex` at `0x100440806`
- `sqldk!SystemThread_TlsIndex` at `0x10044099a`
- `sqldk!SystemThread_TlsIndex` at `0x1004409ee`
- `sqldk!SystemThread_TlsOffset` at `0x10044080f`
- `sqldk!SystemThread_TlsOffset` at `0x1004409a3`
- `sqldk!SystemThread_TlsOffset` at `0x1004409f7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044082a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004409bc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100440a12`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044082a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004409bc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100440a12`

## string_xrefs

- `0x1004407a8`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100440a9c`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100440acb`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100440b22`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100440bb2`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Sspi::MakeSignature(Sspi *this, struct SNI_Packet *a2, unsigned int a3, int a4)
{
  __int64 v4; // r13
  __int64 v7; // rbx
  __int64 v8; // rax
  struct IMemObj *v9; // r10
  int v10; // ebx
  unsigned __int64 v11; // rax
  char *v12; // rax
  char *v13; // r12
  unsigned int v14; // ebx
  const wchar_t *v15; // r9
  struct SNI_Packet *v16; // rcx
  struct SNI_Packet *v17; // rsi
  char *v18; // rdx
  __int64 v19; // r8
  char *v20; // r13
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // rdx
  unsigned int v26; // eax
  int v27; // eax
  __int64 v28; // rcx
  __int64 v30; // [rsp+28h] [rbp-89h]
  __int64 v31; // [rsp+30h] [rbp-81h]
  __int64 v32; // [rsp+38h] [rbp-79h]
  _DWORD v33[2]; // [rsp+48h] [rbp-69h] BYREF
  char *v34; // [rsp+50h] [rbp-61h]
  int v35; // [rsp+58h] [rbp-59h] BYREF
  __int64 v36; // [rsp+60h] [rbp-51h]
  int v37; // [rsp+68h] [rbp-49h] BYREF
  int v38; // [rsp+6Ch] [rbp-45h]
  __int64 v39; // [rsp+70h] [rbp-41h]
  int v40; // [rsp+78h] [rbp-39h] BYREF
  __int64 v41; // [rsp+80h] [rbp-31h]
  __int64 v42; // [rsp+88h] [rbp-29h]
  __int64 v43; // [rsp+90h] [rbp-21h]
  __int64 v44; // [rsp+98h] [rbp-19h]
  bool v45; // [rsp+A8h] [rbp-9h]
  __int64 v46; // [rsp+B8h] [rbp+7h]
  int *v47; // [rsp+C0h] [rbp+Fh]
  const char *v48; // [rsp+C8h] [rbp+17h]
  const char *v49; // [rsp+D0h] [rbp+1Fh]
  int v50; // [rsp+D8h] [rbp+27h]

  v46 = -2;
  v4 = a3;
  v48 = "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp";
  v49 = "Sspi::MakeSignature";
  v50 = 1368;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::MakeSignature",
      1368,
      L"API|SNI%u#, pFirstPacket: %p{SNI_Packet*}, cPacketsInBatch: %d{DWORD}, cbBytesInBatch: %d{DWORD}\n",
      *((_DWORD *)this + 11),
      a2,
      a3,
      a4);
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v8 = *(_QWORD *)(v7 + 256);
  if ( !v8 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v8 = *(_QWORD *)(v7 + 256);
  }
  v9 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v8 + 992) + 56LL) + 8LL);
  v10 = v4 + 1;
  v11 = 16LL * (unsigned int)(v4 + 1);
  if ( !is_mul_ok((unsigned int)(v4 + 1), 0x10u) )
    v11 = -1;
  v12 = (char *)operator new[](v11, v9, 1, "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp", 1379, 6u);
  v13 = v12;
  if ( v12 )
  {
    v16 = a2;
    v17 = 0;
    if ( (_DWORD)v4 )
    {
      v18 = v12 + 4;
      v19 = v4;
      do
      {
        *(_QWORD *)(v18 + 4) = *((_QWORD *)v16 + 21) + *((unsigned int *)v16 + 46);
        *((_DWORD *)v18 - 1) = *((_DWORD *)v16 + 44);
        *(_DWORD *)v18 = 1;
        v17 = v16;
        v16 = (struct SNI_Packet *)*((_QWORD *)v16 + 26);
        v18 += 16;
        --v19;
      }
      while ( v19 );
    }
    v20 = &v12[16 * v4];
    *((_QWORD *)v20 + 1) = *((_QWORD *)v17 + 21) + *((unsigned int *)v17 + 46) + *((unsigned int *)v17 + 44);
    *(_DWORD *)v20 = *((_DWORD *)this + 20);
    *((_DWORD *)v20 + 1) = 2;
    v33[0] = 0;
    v33[1] = v10;
    v34 = v12;
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v35, 1);
    v47 = &v37;
    v40 = 536871401;
    v41 = 0;
    v43 = 0;
    v42 = 0;
    v44 = 0;
    v45 = 0;
    v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v22 = *(_QWORD *)(v21 + 256);
    if ( !v22 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v22 = *(_QWORD *)(v21 + 256);
    }
    v23 = *(_QWORD *)(v22 + 600);
    if ( v23 )
      v45 = (unsigned int)SOS_Task::PushWait(v23, &v40) == 0;
    v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v25 = *(_QWORD *)(v24 + 256);
    if ( !v25 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v25 = *(_QWORD *)(v24 + 256);
    }
    v39 = v25;
    v38 = (*(_DWORD *)(v25 + 800) >> 11) & 1;
    if ( v38 || (*(_BYTE *)(v25 + 800) & 4) == 0 )
    {
      v37 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v25 + 608) + 8LL))(*(_QWORD *)(v25 + 608));
    }
    else
    {
      v37 = 0;
    }
    v26 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _DWORD *, _QWORD))g_pFuncs->MakeSignature)(
            *(_QWORD *)(*((_QWORD *)this + 4) + 12808LL),
            0,
            v33,
            0);
    v14 = v26;
    if ( v26 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v30) = v26;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::MakeSignature",
          1438,
          L"ERR|SNIMakeSignature return value: %d{DWORD}\n",
          v30);
      }
    }
    else if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v30) = 0;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::MakeSignature",
        1438,
        L"SNIMakeSignature return value: %d{DWORD}\n",
        v30);
    }
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v37);
    *(_DWORD *)(v36 + 616) &= ~v35;
    if ( v14 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v32) = v14;
        LODWORD(v31) = 0;
        LODWORD(v30) = 3;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::MakeSignature",
          1444,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v30,
          v31,
          v32);
      }
      SNISetLastError(3, v14, 50100);
    }
    else
    {
      v27 = *(_DWORD *)v20;
      *((_DWORD *)v17 + 60) = *(_DWORD *)v20;
      *((_DWORD *)v17 + 44) += v27;
      *((_DWORD *)a2 + 46) -= *((_DWORD *)this + 18);
      *((_DWORD *)a2 + 44) += *((_DWORD *)this + 18);
      *((_BYTE *)a2 + 256) = 1;
      *((_BYTE *)v17 + 257) = 1;
      v28 = *((_QWORD *)a2 + 21) + *((unsigned int *)a2 + 46);
      *(_DWORD *)v28 = a4 + *(_DWORD *)v20 + *((_DWORD *)this + 18);
      *(_DWORD *)(v28 + 4) = a4;
      *(_QWORD *)(v28 + 8) = (*((_QWORD *)this + 45))++;
    }
    operator delete[](v13);
  }
  else
  {
    v14 = 14;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v32) = 14;
      LODWORD(v31) = 0;
      LODWORD(v30) = 3;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::MakeSignature",
        1384,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v30,
        v31,
        v32);
    }
    SNISetLastError(3, 14, 50100);
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v30) = v14;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::MakeSignature",
      1507,
      L"RET|SNI%d{WINERR}\n",
      v30);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp", "Sspi::MakeSignature", 1368, v15);
  return v14;
}

```

## disassembly

```asm
0x100440770  mov     rax, rsp
0x100440773  mov     [rax+20h], r9d
0x100440777  push    rbp
0x100440778  push    r12
0x10044077a  push    r13
0x10044077c  push    r14
0x10044077e  push    r15
0x100440780  lea     rbp, [rax-5Fh]
0x100440784  sub     rsp, 0E0h
0x10044078b  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x100440793  mov     [rax+8], rbx
0x100440797  mov     [rax+10h], rsi
0x10044079b  mov     [rax+18h], rdi
0x10044079f  mov     r13d, r8d
0x1004407a2  mov     r14, rdx
0x1004407a5  mov     r15, rcx
0x1004407a8  lea     rsi, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x1004407af  mov     [rbp+57h+var_40], rsi
0x1004407b3  lea     rcx, aSspiMakesignat; "Sspi::MakeSignature"
0x1004407ba  mov     [rbp+57h+var_38], rcx
0x1004407be  mov     [rbp+57h+var_30], 558h
0x1004407c5  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004407cc  jz      short loc_1004407FD
0x1004407ce  mov     [rsp+100h+var_C8], r9d
0x1004407d3  mov     dword ptr [rsp+100h+var_D0], r13d
0x1004407d8  mov     [rsp+100h+var_D8], rdx
0x1004407dd  mov     eax, [r15+2Ch]
0x1004407e1  mov     dword ptr [rsp+100h+var_E0], eax
0x1004407e5  lea     r9, aApiSniUPfirstp; "API|SNI%u#, pFirstPacket: %p{SNI_Packet"...
0x1004407ec  mov     r8d, 558h; int
0x1004407f2  mov     rdx, rcx; char *
0x1004407f5  mov     rcx, rsi; char *
0x1004407f8  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004407fd  mov     rdx, gs:58h
0x100440806  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044080d  mov     ecx, [rax]
0x10044080f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100440816  mov     ebx, [rax]
0x100440818  add     rbx, [rdx+rcx*8]
0x10044081c  mov     rax, [rbx+100h]
0x100440823  test    rax, rax
0x100440826  jnz     short loc_100440837
0x100440828  xor     ecx, ecx
0x10044082a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100440830  mov     rax, [rbx+100h]
0x100440837  mov     rax, [rax+3E0h]
0x10044083e  mov     rcx, [rax+38h]
0x100440842  mov     r10, [rcx+8]
0x100440846  lea     ebx, [r13+1]
0x10044084a  mov     ecx, ebx
0x10044084c  mov     eax, 10h
0x100440851  mul     rcx
0x100440854  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10044085b  cmovo   rax, rcx
0x10044085f  mov     byte ptr [rsp+100h+var_D8], 6
0x100440864  mov     dword ptr [rsp+100h+var_E0], 563h
0x10044086c  mov     r9, rsi
0x10044086f  lea     r8d, [rcx+2]
0x100440873  mov     rdx, r10
0x100440876  mov     rcx, rax
0x100440879  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10044087f  mov     r12, rax
0x100440882  test    rax, rax
0x100440885  jnz     short loc_1004408D8
0x100440887  lea     ebx, [rax+0Eh]
0x10044088a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440891  jz      short loc_1004408C1
0x100440893  mov     dword ptr [rsp+100h+var_D0], ebx
0x100440897  xor     edi, edi
0x100440899  mov     dword ptr [rsp+100h+var_D8], edi
0x10044089d  mov     dword ptr [rsp+100h+var_E0], 3
0x1004408a5  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004408ac  mov     r8d, 568h; int
0x1004408b2  lea     rdx, aSspiMakesignat; "Sspi::MakeSignature"
0x1004408b9  mov     rcx, rsi; char *
0x1004408bc  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004408c1  mov     r8d, 0C3B4h
0x1004408c7  mov     edx, ebx
0x1004408c9  mov     ecx, 3
0x1004408ce  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004408d3  jmp     loc_100440BB9
0x1004408d8  mov     rcx, r14
0x1004408db  xor     edi, edi
0x1004408dd  mov     esi, edi
0x1004408df  test    r13d, r13d
0x1004408e2  jz      short loc_100440924
0x1004408e4  lea     rdx, [rax+4]
0x1004408e8  mov     r8, r13
0x1004408eb  nop     dword ptr [rax+rax+00h]
0x1004408f0  mov     eax, [rcx+0B8h]
0x1004408f6  add     rax, [rcx+0A8h]
0x1004408fd  mov     [rdx+4], rax
0x100440901  mov     eax, [rcx+0B0h]
0x100440907  mov     [rdx-4], eax
0x10044090a  mov     dword ptr [rdx], 1
0x100440910  mov     rsi, rcx
0x100440913  mov     rcx, [rcx+0D0h]
0x10044091a  lea     rdx, [rdx+10h]
0x10044091e  sub     r8, 1
0x100440922  jnz     short loc_1004408F0
0x100440924  mov     ecx, [rsi+0B8h]
0x10044092a  add     rcx, [rsi+0A8h]
0x100440931  shl     r13, 4
0x100440935  add     r13, r12
0x100440938  mov     eax, [rsi+0B0h]
0x10044093e  add     rax, rcx
0x100440941  mov     [r13+8], rax
0x100440945  mov     eax, [r15+50h]
0x100440949  mov     [r13+0], eax
0x10044094d  mov     dword ptr [r13+4], 2
0x100440955  mov     [rbp+57h+var_C0], edi
0x100440958  mov     [rbp+57h+var_BC], ebx
0x10044095b  mov     [rbp+57h+var_B8], r12
0x10044095f  mov     edx, 1
0x100440964  lea     rcx, [rbp+57h+var_B0]
0x100440968  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10044096d  nop
0x10044096e  lea     rax, [rbp+57h+var_A0]
0x100440972  mov     [rbp+57h+var_48], rax
0x100440976  mov     [rbp+57h+var_90], 200001E9h
0x10044097d  mov     [rbp+57h+var_88], rdi
0x100440981  mov     [rbp+57h+var_78], rdi
0x100440985  mov     [rbp+57h+var_80], rdi
0x100440989  mov     [rbp+57h+var_70], rdi
0x10044098d  mov     [rbp+57h+var_60], 0
0x100440991  mov     rdx, gs:58h
0x10044099a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004409a1  mov     ecx, [rax]
0x1004409a3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004409aa  mov     ebx, [rax]
0x1004409ac  add     rbx, [rdx+rcx*8]
0x1004409b0  mov     rcx, [rbx+100h]
0x1004409b7  test    rcx, rcx
0x1004409ba  jnz     short loc_1004409C9
0x1004409bc  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004409c2  mov     rcx, [rbx+100h]
0x1004409c9  mov     rcx, [rcx+258h]
0x1004409d0  test    rcx, rcx
0x1004409d3  jz      short loc_1004409E5
0x1004409d5  lea     rdx, [rbp+57h+var_90]
0x1004409d9  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x1004409df  test    eax, eax
0x1004409e1  setz    [rbp+57h+var_60]
0x1004409e5  mov     rdx, gs:58h
0x1004409ee  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004409f5  mov     ecx, [rax]
0x1004409f7  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004409fe  mov     ebx, [rax]
0x100440a00  add     rbx, [rdx+rcx*8]
0x100440a04  mov     rdx, [rbx+100h]
0x100440a0b  test    rdx, rdx
0x100440a0e  jnz     short loc_100440A1F
0x100440a10  xor     ecx, ecx
0x100440a12  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100440a18  mov     rdx, [rbx+100h]
0x100440a1f  mov     [rbp+57h+var_98], rdx
0x100440a23  mov     eax, [rdx+320h]
0x100440a29  shr     eax, 0Bh
0x100440a2c  and     eax, 1
0x100440a2f  mov     [rbp+57h+var_9C], eax
0x100440a32  jnz     short loc_100440A42
0x100440a34  test    byte ptr [rdx+320h], 4
0x100440a3b  jz      short loc_100440A42
0x100440a3d  mov     [rbp+57h+var_A0], edi
0x100440a40  jmp     short loc_100440A57
0x100440a42  mov     [rbp+57h+var_A0], 1
0x100440a49  mov     rcx, [rdx+260h]
0x100440a50  mov     rax, [rcx]
0x100440a53  call    qword ptr [rax+8]
0x100440a56  nop
0x100440a57  mov     rcx, [r15+20h]
0x100440a5b  xor     r9d, r9d
0x100440a5e  lea     r8, [rbp+57h+var_C0]
0x100440a62  xor     edx, edx
0x100440a64  mov     rcx, [rcx+3208h]
0x100440a6b  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x100440a72  call    qword ptr [rax+70h]
0x100440a75  mov     ebx, eax
0x100440a77  test    eax, eax
0x100440a79  jnz     short loc_100440AAA
0x100440a7b  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440a82  jz      short loc_100440AD8
0x100440a84  mov     dword ptr [rsp+100h+var_E0], edi
0x100440a88  lea     r9, aSnimakesignatu; "SNIMakeSignature return value: %d{DWORD"...
0x100440a8f  mov     r8d, 59Eh; int
0x100440a95  lea     rdx, aSspiMakesignat; "Sspi::MakeSignature"
0x100440a9c  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x100440aa3  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100440aa8  jmp     short loc_100440AD8
0x100440aaa  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440ab1  jz      short loc_100440AD8
0x100440ab3  mov     dword ptr [rsp+100h+var_E0], ebx
0x100440ab7  lea     r9, aErrSnimakesign; "ERR|SNIMakeSignature return value: %d{D"...
0x100440abe  mov     r8d, 59Eh; int
0x100440ac4  lea     rdx, aSspiMakesignat; "Sspi::MakeSignature"
0x100440acb  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x100440ad2  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100440ad7  nop
0x100440ad8  lea     rcx, [rbp+57h+var_A0]; this
0x100440adc  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x100440ae1  nop
0x100440ae2  mov     ecx, [rbp+57h+var_B0]
0x100440ae5  not     ecx
0x100440ae7  mov     rax, [rbp+57h+var_A8]
0x100440aeb  and     [rax+268h], ecx
0x100440af1  test    ebx, ebx
0x100440af3  jz      short loc_100440B42
0x100440af5  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440afc  jz      short loc_100440B2E
0x100440afe  mov     dword ptr [rsp+100h+var_D0], ebx
0x100440b02  mov     dword ptr [rsp+100h+var_D8], edi
0x100440b06  mov     dword ptr [rsp+100h+var_E0], 3
0x100440b0e  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100440b15  mov     r8d, 5A4h; int
0x100440b1b  lea     rdx, aSspiMakesignat; "Sspi::MakeSignature"
0x100440b22  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x100440b29  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100440b2e  mov     r8d, 0C3B4h
0x100440b34  mov     edx, ebx
0x100440b36  mov     ecx, 3
0x100440b3b  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100440b40  jmp     short loc_100440BA9
0x100440b42  mov     eax, [r13+0]
0x100440b46  mov     [rsi+0F0h], eax
0x100440b4c  add     [rsi+0B0h], eax
0x100440b52  mov     eax, [r15+48h]
0x100440b56  sub     [r14+0B8h], eax
0x100440b5d  mov     eax, [r15+48h]
0x100440b61  add     [r14+0B0h], eax
0x100440b68  mov     byte ptr [r14+100h], 1
0x100440b70  mov     byte ptr [rsi+101h], 1
0x100440b77  mov     ecx, [r14+0B8h]
0x100440b7e  add     rcx, [r14+0A8h]
0x100440b85  mov     eax, [r15+48h]
0x100440b89  add     eax, [r13+0]
0x100440b8d  mov     edx, [rbp+57h+arg_18]
0x100440b90  add     eax, edx
0x100440b92  mov     [rcx], eax
0x100440b94  mov     [rcx+4], edx
0x100440b97  mov     rax, [r15+168h]
0x100440b9e  mov     [rcx+8], rax
0x100440ba2  inc     qword ptr [r15+168h]
0x100440ba9  mov     rcx, r12
0x100440bac  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100440bb2  lea     rsi, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x100440bb9  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440bc0  jz      short loc_100440BE3
0x100440bc2  mov     dword ptr [rsp+100h+var_E0], ebx
0x100440bc6  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100440bcd  mov     r8d, 5E3h; int
0x100440bd3  lea     rdx, aSspiMakesignat; "Sspi::MakeSignature"
0x100440bda  mov     rcx, rsi; char *
0x100440bdd  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100440be2  nop
0x100440be3  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440bea  jz      short loc_100440C01
0x100440bec  mov     r8d, 558h; int
0x100440bf2  lea     rdx, aSspiMakesignat; "Sspi::MakeSignature"
0x100440bf9  mov     rcx, rsi; char *
0x100440bfc  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100440c01  mov     eax, ebx
0x100440c03  lea     r11, [rsp+100h+var_20]
0x100440c0b  mov     rbx, [r11+30h]
0x100440c0f  mov     rsi, [r11+38h]
0x100440c13  mov     rdi, [r11+40h]
0x100440c17  mov     rsp, r11
0x100440c1a  pop     r15
0x100440c1c  pop     r14
0x100440c1e  pop     r13
0x100440c20  pop     r12
0x100440c22  pop     rbp
0x100440c23  retn
```
