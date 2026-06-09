# Sspi::EncryptPayload(SNI_Packet *,ulong,ulong)

- ea: `0x100440230`
- end: `0x100440760`
- name: `?EncryptPayload@Sspi@@AEAAKPEAVSNI_Packet@@KK@Z`
- size: `1328`
- prototype: `unsigned int __fastcall(Sspi *__hidden this, struct SNI_Packet *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
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
- `0x100440230`
- `0x100486250`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1004404d0`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1004404d0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004406e8`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004406e8`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100440339`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100440339`
- `sqldk!SystemThread_TlsIndex` at `0x1004402c6`
- `sqldk!SystemThread_TlsIndex` at `0x100440491`
- `sqldk!SystemThread_TlsIndex` at `0x1004404e5`
- `sqldk!SystemThread_TlsOffset` at `0x1004402cf`
- `sqldk!SystemThread_TlsOffset` at `0x10044049a`
- `sqldk!SystemThread_TlsOffset` at `0x1004404ee`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004402ea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004404b3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100440509`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004402ea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004404b3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100440509`

## string_xrefs

- `0x100440268`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100440596`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004405c5`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10044061c`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004406ee`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Sspi::EncryptPayload(Sspi *this, struct SNI_Packet *a2, unsigned int a3, int a4)
{
  __int64 v4; // r15
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
  char *v20; // r15
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // rdx
  unsigned int v26; // eax
  unsigned int v27; // r9d
  int v28; // ecx
  int v29; // ecx
  __int64 v30; // rcx
  __int64 v32; // [rsp+28h] [rbp-A9h]
  __int64 v33; // [rsp+30h] [rbp-A1h]
  __int64 v34; // [rsp+38h] [rbp-99h]
  char *v35; // [rsp+48h] [rbp-89h]
  __int64 v36; // [rsp+50h] [rbp-81h]
  __int64 v37; // [rsp+58h] [rbp-79h]
  _DWORD v38[2]; // [rsp+60h] [rbp-71h] BYREF
  char *v39; // [rsp+68h] [rbp-69h]
  int v40; // [rsp+78h] [rbp-59h] BYREF
  __int64 v41; // [rsp+80h] [rbp-51h]
  int v42; // [rsp+88h] [rbp-49h] BYREF
  int v43; // [rsp+8Ch] [rbp-45h]
  __int64 v44; // [rsp+90h] [rbp-41h]
  int v45; // [rsp+98h] [rbp-39h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-31h]
  __int64 v47; // [rsp+A8h] [rbp-29h]
  __int64 v48; // [rsp+B0h] [rbp-21h]
  __int64 v49; // [rsp+B8h] [rbp-19h]
  bool v50; // [rsp+C8h] [rbp-9h]
  __int64 v51; // [rsp+D8h] [rbp+7h]
  int *v52; // [rsp+E0h] [rbp+Fh]
  const char *v53; // [rsp+E8h] [rbp+17h]
  const char *v54; // [rsp+F0h] [rbp+1Fh]
  int v55; // [rsp+F8h] [rbp+27h]

  v51 = -2;
  v4 = a3;
  v53 = "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp";
  v54 = "Sspi::EncryptPayload";
  v55 = 1185;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::EncryptPayload",
      1185,
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
  v10 = v4 + 2;
  v11 = 16LL * (unsigned int)(v4 + 2);
  if ( !is_mul_ok((unsigned int)(v4 + 2), 0x10u) )
    v11 = -1;
  v12 = (char *)operator new[](v11, v9, 1, "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp", 1206, 6u);
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
    v37 = *((_QWORD *)v17 + 21) + *((unsigned int *)v17 + 46);
    v36 = *((unsigned int *)v17 + 44);
    v35 = &v12[16 * v4];
    *((_QWORD *)v35 + 1) = v36 + v37;
    *(_DWORD *)v35 = *((_DWORD *)this + 19);
    *((_DWORD *)v35 + 1) = 2;
    v20 = &v12[16 * (unsigned int)(v4 + 1)];
    *((_QWORD *)v20 + 1) = v37 + v36 + *((unsigned int *)this + 19);
    *(_DWORD *)v20 = *((_DWORD *)this + 21);
    *((_DWORD *)v20 + 1) = 9;
    v38[0] = 0;
    v38[1] = v10;
    v39 = v12;
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v40, 1);
    v52 = &v42;
    v45 = 536871401;
    v46 = 0;
    v48 = 0;
    v47 = 0;
    v49 = 0;
    v50 = 0;
    v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v22 = *(_QWORD *)(v21 + 256);
    if ( !v22 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v22 = *(_QWORD *)(v21 + 256);
    }
    v23 = *(_QWORD *)(v22 + 600);
    if ( v23 )
      v50 = (unsigned int)SOS_Task::PushWait(v23, &v45) == 0;
    v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v25 = *(_QWORD *)(v24 + 256);
    if ( !v25 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v25 = *(_QWORD *)(v24 + 256);
    }
    v44 = v25;
    v43 = (*(_DWORD *)(v25 + 800) >> 11) & 1;
    if ( v43 || (*(_BYTE *)(v25 + 800) & 4) == 0 )
    {
      v42 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v25 + 608) + 8LL))(*(_QWORD *)(v25 + 608));
    }
    else
    {
      v42 = 0;
    }
    v26 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _DWORD *, _QWORD))g_pFuncs->EncryptMessage)(
            *(_QWORD *)(*((_QWORD *)this + 4) + 12808LL),
            0,
            v38,
            0);
    v14 = v26;
    if ( v26 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v32) = v26;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::EncryptPayload",
          1263,
          L"ERR|SNIEncryptMessage return value: %d{DWORD}\n",
          v32);
      }
    }
    else if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v32) = 0;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::EncryptPayload",
        1263,
        L"SNIEncryptMessage return value: %d{DWORD}\n",
        v32);
    }
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v42);
    *(_DWORD *)(v41 + 616) &= ~v40;
    if ( v14 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v34) = v14;
        LODWORD(v33) = 0;
        LODWORD(v32) = 3;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::EncryptPayload",
          1269,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v32,
          v33,
          v34);
      }
      SNISetLastError(3, v14, 50100);
    }
    else
    {
      v27 = *((_DWORD *)this + 19);
      v28 = *(_DWORD *)v35;
      if ( *(_DWORD *)v35 < v27 && *(_DWORD *)v20 )
      {
        memmove((void *)(v37 + v36 + *(unsigned int *)v35), (const void *)(v37 + v36 + v27), *(unsigned int *)v20);
        v28 = *(_DWORD *)v35;
      }
      v29 = *(_DWORD *)v20 + v28;
      *((_DWORD *)v17 + 60) = v29;
      *((_DWORD *)v17 + 44) += v29;
      *((_DWORD *)a2 + 46) -= *((_DWORD *)this + 18);
      *((_DWORD *)a2 + 44) += *((_DWORD *)this + 18);
      *((_BYTE *)a2 + 256) = 1;
      *((_BYTE *)v17 + 257) = 1;
      v30 = *((_QWORD *)a2 + 21) + *((unsigned int *)a2 + 46);
      *(_DWORD *)v30 = *((_DWORD *)this + 18) + *(_DWORD *)v20 + a4 + *(_DWORD *)v35;
      *(_DWORD *)(v30 + 4) = a4;
      *(_DWORD *)(v30 + 8) = *(_DWORD *)v35;
      *(_QWORD *)(v30 + 16) = (*((_QWORD *)this + 45))++;
    }
    operator delete[](v13);
  }
  else
  {
    v14 = 14;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v34) = 14;
      LODWORD(v33) = 0;
      LODWORD(v32) = 3;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::EncryptPayload",
        1211,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v32,
        v33,
        v34);
    }
    SNISetLastError(3, 14, 50100);
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v32) = v14;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::EncryptPayload",
      1352,
      L"RET|SNI%d{WINERR}\n",
      v32);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp", "Sspi::EncryptPayload", 1185, v15);
  return v14;
}

```

## disassembly

```asm
0x100440230  mov     rax, rsp
0x100440233  mov     [rax+20h], r9d
0x100440237  push    rbp
0x100440238  push    r12
0x10044023a  push    r13
0x10044023c  push    r14
0x10044023e  push    r15
0x100440240  lea     rbp, [rax-5Fh]
0x100440244  sub     rsp, 100h
0x10044024b  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x100440253  mov     [rax+8], rbx
0x100440257  mov     [rax+10h], rsi
0x10044025b  mov     [rax+18h], rdi
0x10044025f  mov     r15d, r8d
0x100440262  mov     r13, rdx
0x100440265  mov     r14, rcx
0x100440268  lea     rsi, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10044026f  mov     [rbp+57h+var_40], rsi
0x100440273  lea     rcx, aSspiEncryptpay; "Sspi::EncryptPayload"
0x10044027a  mov     [rbp+57h+var_38], rcx
0x10044027e  mov     [rbp+57h+var_30], 4A1h
0x100440285  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044028c  jz      short loc_1004402BD
0x10044028e  mov     dword ptr [rsp+120h+var_E8], r9d
0x100440293  mov     dword ptr [rsp+120h+var_F0], r15d
0x100440298  mov     [rsp+120h+var_F8], rdx
0x10044029d  mov     eax, [r14+2Ch]
0x1004402a1  mov     dword ptr [rsp+120h+var_100], eax
0x1004402a5  lea     r9, aApiSniUPfirstp; "API|SNI%u#, pFirstPacket: %p{SNI_Packet"...
0x1004402ac  mov     r8d, 4A1h; int
0x1004402b2  mov     rdx, rcx; char *
0x1004402b5  mov     rcx, rsi; char *
0x1004402b8  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004402bd  mov     rdx, gs:58h
0x1004402c6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004402cd  mov     ecx, [rax]
0x1004402cf  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004402d6  mov     ebx, [rax]
0x1004402d8  add     rbx, [rdx+rcx*8]
0x1004402dc  mov     rax, [rbx+100h]
0x1004402e3  test    rax, rax
0x1004402e6  jnz     short loc_1004402F7
0x1004402e8  xor     ecx, ecx
0x1004402ea  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004402f0  mov     rax, [rbx+100h]
0x1004402f7  mov     rax, [rax+3E0h]
0x1004402fe  mov     rcx, [rax+38h]
0x100440302  mov     r10, [rcx+8]
0x100440306  lea     ebx, [r15+2]
0x10044030a  mov     ecx, ebx
0x10044030c  mov     eax, 10h
0x100440311  mul     rcx
0x100440314  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10044031b  cmovo   rax, rcx
0x10044031f  mov     byte ptr [rsp+120h+var_F8], 6
0x100440324  mov     dword ptr [rsp+120h+var_100], 4B6h
0x10044032c  mov     r9, rsi
0x10044032f  lea     r8d, [rcx+2]
0x100440333  mov     rdx, r10
0x100440336  mov     rcx, rax
0x100440339  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10044033f  mov     r12, rax
0x100440342  test    rax, rax
0x100440345  jnz     short loc_100440398
0x100440347  lea     ebx, [rax+0Eh]
0x10044034a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440351  jz      short loc_100440381
0x100440353  mov     dword ptr [rsp+120h+var_F0], ebx
0x100440357  xor     edi, edi
0x100440359  mov     dword ptr [rsp+120h+var_F8], edi
0x10044035d  mov     dword ptr [rsp+120h+var_100], 3
0x100440365  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10044036c  mov     r8d, 4BBh; int
0x100440372  lea     rdx, aSspiEncryptpay; "Sspi::EncryptPayload"
0x100440379  mov     rcx, rsi; char *
0x10044037c  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100440381  mov     r8d, 0C3B4h
0x100440387  mov     edx, ebx
0x100440389  mov     ecx, 3
0x10044038e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100440393  jmp     loc_1004406F5
0x100440398  mov     rcx, r13
0x10044039b  xor     edi, edi
0x10044039d  mov     esi, edi
0x10044039f  test    r15d, r15d
0x1004403a2  jz      short loc_1004403E4
0x1004403a4  lea     rdx, [rax+4]
0x1004403a8  mov     r8, r15
0x1004403ab  nop     dword ptr [rax+rax+00h]
0x1004403b0  mov     eax, [rcx+0B8h]
0x1004403b6  add     rax, [rcx+0A8h]
0x1004403bd  mov     [rdx+4], rax
0x1004403c1  mov     eax, [rcx+0B0h]
0x1004403c7  mov     [rdx-4], eax
0x1004403ca  mov     dword ptr [rdx], 1
0x1004403d0  mov     rsi, rcx
0x1004403d3  mov     rcx, [rcx+0D0h]
0x1004403da  lea     rdx, [rdx+10h]
0x1004403de  sub     r8, 1
0x1004403e2  jnz     short loc_1004403B0
0x1004403e4  mov     edx, [rsi+0B8h]
0x1004403ea  add     rdx, [rsi+0A8h]
0x1004403f1  mov     [rbp+57h+var_D0], rdx
0x1004403f5  mov     r8d, [rsi+0B0h]
0x1004403fc  mov     [rsp+120h+var_D8], r8
0x100440401  mov     rcx, r15
0x100440404  shl     rcx, 4
0x100440408  add     rcx, r12
0x10044040b  mov     [rsp+120h+var_E0], rcx
0x100440410  lea     rax, [r8+rdx]
0x100440414  mov     [rcx+8], rax
0x100440418  mov     eax, [r14+4Ch]
0x10044041c  mov     [rcx], eax
0x10044041e  mov     dword ptr [rcx+4], 2
0x100440425  inc     r15d
0x100440428  shl     r15, 4
0x10044042c  add     r15, r12
0x10044042f  mov     eax, [r14+4Ch]
0x100440433  add     rax, r8
0x100440436  add     rax, rdx
0x100440439  mov     [r15+8], rax
0x10044043d  mov     eax, [r14+54h]
0x100440441  mov     [r15], eax
0x100440444  mov     dword ptr [r15+4], 9
0x10044044c  mov     [rbp+57h+var_C8], edi
0x10044044f  mov     [rbp+57h+var_C4], ebx
0x100440452  mov     [rbp+57h+var_C0], r12
0x100440456  mov     edx, 1
0x10044045b  lea     rcx, [rbp+57h+var_B0]
0x10044045f  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x100440464  nop
0x100440465  lea     rax, [rbp+57h+var_A0]
0x100440469  mov     [rbp+57h+var_48], rax
0x10044046d  mov     [rbp+57h+var_90], 200001E9h
0x100440474  mov     [rbp+57h+var_88], rdi
0x100440478  mov     [rbp+57h+var_78], rdi
0x10044047c  mov     [rbp+57h+var_80], rdi
0x100440480  mov     [rbp+57h+var_70], rdi
0x100440484  mov     [rbp+57h+var_60], 0
0x100440488  mov     rdx, gs:58h
0x100440491  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100440498  mov     ecx, [rax]
0x10044049a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004404a1  mov     ebx, [rax]
0x1004404a3  add     rbx, [rdx+rcx*8]
0x1004404a7  mov     rcx, [rbx+100h]
0x1004404ae  test    rcx, rcx
0x1004404b1  jnz     short loc_1004404C0
0x1004404b3  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004404b9  mov     rcx, [rbx+100h]
0x1004404c0  mov     rcx, [rcx+258h]
0x1004404c7  test    rcx, rcx
0x1004404ca  jz      short loc_1004404DC
0x1004404cc  lea     rdx, [rbp+57h+var_90]
0x1004404d0  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x1004404d6  test    eax, eax
0x1004404d8  setz    [rbp+57h+var_60]
0x1004404dc  mov     rdx, gs:58h
0x1004404e5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004404ec  mov     ecx, [rax]
0x1004404ee  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004404f5  mov     ebx, [rax]
0x1004404f7  add     rbx, [rdx+rcx*8]
0x1004404fb  mov     rdx, [rbx+100h]
0x100440502  test    rdx, rdx
0x100440505  jnz     short loc_100440516
0x100440507  xor     ecx, ecx
0x100440509  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044050f  mov     rdx, [rbx+100h]
0x100440516  mov     [rbp+57h+var_98], rdx
0x10044051a  mov     eax, [rdx+320h]
0x100440520  shr     eax, 0Bh
0x100440523  and     eax, 1
0x100440526  mov     [rbp+57h+var_9C], eax
0x100440529  jnz     short loc_100440539
0x10044052b  test    byte ptr [rdx+320h], 4
0x100440532  jz      short loc_100440539
0x100440534  mov     [rbp+57h+var_A0], edi
0x100440537  jmp     short loc_10044054E
0x100440539  mov     [rbp+57h+var_A0], 1
0x100440540  mov     rcx, [rdx+260h]
0x100440547  mov     rax, [rcx]
0x10044054a  call    qword ptr [rax+8]
0x10044054d  nop
0x10044054e  mov     rcx, [r14+20h]
0x100440552  xor     r9d, r9d
0x100440555  lea     r8, [rbp+57h+var_C8]
0x100440559  xor     edx, edx
0x10044055b  mov     rcx, [rcx+3208h]
0x100440562  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x100440569  call    qword ptr [rax+0C8h]
0x10044056f  mov     ebx, eax
0x100440571  test    eax, eax
0x100440573  jnz     short loc_1004405A4
0x100440575  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044057c  jz      short loc_1004405D2
0x10044057e  mov     dword ptr [rsp+120h+var_100], edi
0x100440582  lea     r9, aSniencryptmess; "SNIEncryptMessage return value: %d{DWOR"...
0x100440589  mov     r8d, 4EFh; int
0x10044058f  lea     rdx, aSspiEncryptpay; "Sspi::EncryptPayload"
0x100440596  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10044059d  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004405a2  jmp     short loc_1004405D2
0x1004405a4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004405ab  jz      short loc_1004405D2
0x1004405ad  mov     dword ptr [rsp+120h+var_100], ebx
0x1004405b1  lea     r9, aErrSniencryptm; "ERR|SNIEncryptMessage return value: %d{"...
0x1004405b8  mov     r8d, 4EFh; int
0x1004405be  lea     rdx, aSspiEncryptpay; "Sspi::EncryptPayload"
0x1004405c5  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x1004405cc  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004405d1  nop
0x1004405d2  lea     rcx, [rbp+57h+var_A0]; this
0x1004405d6  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x1004405db  nop
0x1004405dc  mov     ecx, [rbp+57h+var_B0]
0x1004405df  not     ecx
0x1004405e1  mov     rax, [rbp+57h+var_A8]
0x1004405e5  and     [rax+268h], ecx
0x1004405eb  test    ebx, ebx
0x1004405ed  jz      short loc_10044063F
0x1004405ef  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004405f6  jz      short loc_100440628
0x1004405f8  mov     dword ptr [rsp+120h+var_F0], ebx
0x1004405fc  mov     dword ptr [rsp+120h+var_F8], edi
0x100440600  mov     dword ptr [rsp+120h+var_100], 3
0x100440608  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10044060f  mov     r8d, 4F5h; int
0x100440615  lea     rdx, aSspiEncryptpay; "Sspi::EncryptPayload"
0x10044061c  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x100440623  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100440628  mov     r8d, 0C3B4h
0x10044062e  mov     edx, ebx
0x100440630  mov     ecx, 3
0x100440635  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10044063a  jmp     loc_1004406E5
0x10044063f  mov     rdi, [rsp+120h+var_E0]
0x100440644  mov     eax, [rdi]
0x100440646  mov     r9d, [r14+4Ch]
0x10044064a  mov     ecx, eax
0x10044064c  cmp     eax, r9d
0x10044064f  jnb     short loc_100440679
0x100440651  mov     edx, [r15]
0x100440654  test    edx, edx
0x100440656  jz      short loc_100440679
0x100440658  mov     r8d, edx; Size
0x10044065b  mov     edx, r9d
0x10044065e  add     rdx, [rsp+120h+var_D8]
0x100440663  add     rdx, [rbp+57h+var_D0]; Src
0x100440667  mov     ecx, eax
0x100440669  add     rcx, [rsp+120h+var_D8]
0x10044066e  add     rcx, [rbp+57h+var_D0]; void *
0x100440672  call    memmove
0x100440677  mov     ecx, [rdi]
0x100440679  add     ecx, [r15]
0x10044067c  mov     [rsi+0F0h], ecx
0x100440682  add     [rsi+0B0h], ecx
0x100440688  mov     eax, [r14+48h]
0x10044068c  sub     [r13+0B8h], eax
0x100440693  mov     eax, [r14+48h]
0x100440697  add     [r13+0B0h], eax
0x10044069e  mov     byte ptr [r13+100h], 1
0x1004406a6  mov     byte ptr [rsi+101h], 1
0x1004406ad  mov     ecx, [r13+0B8h]
0x1004406b4  add     rcx, [r13+0A8h]
0x1004406bb  mov     eax, [rdi]
0x1004406bd  mov     edx, [rbp+57h+arg_18]
0x1004406c0  add     eax, edx
0x1004406c2  add     eax, [r15]
0x1004406c5  add     eax, [r14+48h]
0x1004406c9  mov     [rcx], eax
0x1004406cb  mov     [rcx+4], edx
0x1004406ce  mov     eax, [rdi]
0x1004406d0  mov     [rcx+8], eax
0x1004406d3  mov     rax, [r14+168h]
0x1004406da  mov     [rcx+10h], rax
0x1004406de  inc     qword ptr [r14+168h]
0x1004406e5  mov     rcx, r12
0x1004406e8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004406ee  lea     rsi, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x1004406f5  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004406fc  jz      short loc_10044071F
0x1004406fe  mov     dword ptr [rsp+120h+var_100], ebx
0x100440702  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100440709  mov     r8d, 548h; int
0x10044070f  lea     rdx, aSspiEncryptpay; "Sspi::EncryptPayload"
0x100440716  mov     rcx, rsi; char *
0x100440719  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044071e  nop
0x10044071f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440726  jz      short loc_10044073D
0x100440728  mov     r8d, 4A1h; int
0x10044072e  lea     rdx, aSspiEncryptpay; "Sspi::EncryptPayload"
0x100440735  mov     rcx, rsi; char *
0x100440738  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10044073d  mov     eax, ebx
0x10044073f  lea     r11, [rsp+120h+var_20]
0x100440747  mov     rbx, [r11+30h]
0x10044074b  mov     rsi, [r11+38h]
0x10044074f  mov     rdi, [r11+40h]
  ... truncated ...
```
