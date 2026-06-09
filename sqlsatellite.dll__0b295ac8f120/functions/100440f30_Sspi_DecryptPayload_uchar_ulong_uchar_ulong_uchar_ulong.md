# Sspi::DecryptPayload(uchar *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x100440f30`
- end: `0x100441280`
- name: `?DecryptPayload@Sspi@@AEAAKPEAEK0K0K@Z`
- size: `848`
- prototype: `unsigned int __fastcall(Sspi *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x10043ef20`

## callees

- `0x100405270`
- `0x100405390`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100440f30`
- `0x100486af0`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1004410a0`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1004410a0`
- `sqldk!SystemThread_TlsIndex` at `0x100441061`
- `sqldk!SystemThread_TlsIndex` at `0x1004410b5`
- `sqldk!SystemThread_TlsOffset` at `0x10044106a`
- `sqldk!SystemThread_TlsOffset` at `0x1004410be`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100441083`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004410d9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100441083`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004410d9`

## string_xrefs

- `0x100440f72`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441168`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441197`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004411f0`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10044122f`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441252`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Sspi::DecryptPayload(
        Sspi *this,
        unsigned __int8 *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7)
{
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  const wchar_t *v18; // r9
  __int64 v20; // [rsp+20h] [rbp-E0h]
  __int64 v21; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+30h] [rbp-D0h]
  _DWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h]
  int v27; // [rsp+80h] [rbp-80h] BYREF
  int v28; // [rsp+84h] [rbp-7Ch]
  __int64 v29; // [rsp+88h] [rbp-78h]
  int v30; // [rsp+90h] [rbp-70h] BYREF
  __int64 v31; // [rsp+98h] [rbp-68h]
  __int64 v32; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  __int64 v34; // [rsp+B0h] [rbp-50h]
  bool v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+D0h] [rbp-30h]
  int *v37; // [rsp+D8h] [rbp-28h]
  const char *v38; // [rsp+E0h] [rbp-20h]
  const char *v39; // [rsp+E8h] [rbp-18h]
  int v40; // [rsp+F0h] [rbp-10h]
  _DWORD v41[2]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int8 *v42; // [rsp+100h] [rbp+0h]
  unsigned int v43; // [rsp+108h] [rbp+8h]
  int v44; // [rsp+10Ch] [rbp+Ch]
  unsigned __int8 *v45; // [rsp+110h] [rbp+10h]
  unsigned int v46; // [rsp+118h] [rbp+18h]
  int v47; // [rsp+11Ch] [rbp+1Ch]
  unsigned __int8 *v48; // [rsp+120h] [rbp+20h]

  v36 = -2;
  v38 = "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp";
  v39 = "Sspi::DecryptPayload";
  v40 = 1639;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::DecryptPayload",
      1639,
      L"API|SNI%u#, pData: %p{BYTE*}, cbData: %d{DWORD}, pTrailer: %p{BYTE*}, cbTrailer: %d{DWORD}, pPadding: %p{BYTE*}, c"
       "bPadding: %d{DWORD}\n",
      *((_DWORD *)this + 11),
      a2,
      a3,
      a4,
      a5,
      a6,
      a7);
  v23[0] = 0;
  v23[1] = 3;
  v24 = v41;
  v42 = a2;
  v41[0] = a3;
  v41[1] = 1;
  v45 = a4;
  v43 = a5;
  v44 = 2;
  v48 = a6;
  v46 = a7;
  v47 = 9;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v25, 1);
  v37 = &v27;
  v30 = 536871399;
  v31 = 0;
  v33 = 0;
  v32 = 0;
  v34 = 0;
  v35 = 0;
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v12 = *(_QWORD *)(v11 + 256);
  if ( !v12 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v12 = *(_QWORD *)(v11 + 256);
  }
  v13 = *(_QWORD *)(v12 + 600);
  if ( v13 )
    v35 = (unsigned int)SOS_Task::PushWait(v13, &v30) == 0;
  v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v15 = *(_QWORD *)(v14 + 256);
  if ( !v15 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v15 = *(_QWORD *)(v14 + 256);
  }
  v29 = v15;
  v28 = (*(_DWORD *)(v15 + 800) >> 11) & 1;
  if ( v28 || (*(_BYTE *)(v15 + 800) & 4) == 0 )
  {
    v27 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v15 + 608) + 8LL))(*(_QWORD *)(v15 + 608));
  }
  else
  {
    v27 = 0;
  }
  v16 = ((__int64 (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD))g_pFuncs->DecryptMessage)(
          *(_QWORD *)(*((_QWORD *)this + 4) + 12808LL),
          v23,
          0,
          0);
  v17 = v16;
  if ( v16 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v20) = v16;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::DecryptPayload",
        1675,
        L"ERR|SNIDecryptMessage return value: %d{DWORD}\n",
        v20);
    }
  }
  else if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v20) = 0;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::DecryptPayload",
      1675,
      L"SNIDecryptMessage return value: %d{DWORD}\n",
      v20);
  }
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v27);
  *(_DWORD *)(v26 + 616) &= ~v25;
  if ( v17 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v22) = v17;
      LODWORD(v21) = 0;
      LODWORD(v20) = 3;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::DecryptPayload",
        1681,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v20,
        v21,
        v22);
    }
    SNISetLastError(3, v17, 50100);
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v20) = v17;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::DecryptPayload",
      1684,
      L"RET|SNI%d{WINERR}\n",
      v20);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp", "Sspi::DecryptPayload", 1639, v18);
  return v17;
}

```

## disassembly

```asm
0x100440f30  push    rbp
0x100440f32  push    rbx
0x100440f33  push    rsi
0x100440f34  push    rdi
0x100440f35  push    r12
0x100440f37  push    r13
0x100440f39  push    r14
0x100440f3b  push    r15
0x100440f3d  lea     rbp, [rsp-38h]
0x100440f42  sub     rsp, 138h
0x100440f49  mov     [rbp+70h+var_A0], 0FFFFFFFFFFFFFFFEh
0x100440f51  mov     rax, cs:__security_cookie
0x100440f58  xor     rax, rsp
0x100440f5b  mov     [rbp+70h+var_48], rax
0x100440f5f  mov     rsi, r9
0x100440f62  mov     edi, r8d
0x100440f65  mov     rbx, rdx
0x100440f68  mov     r13, rcx
0x100440f6b  mov     r14, [rbp+70h+arg_28]
0x100440f72  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x100440f79  mov     [rbp+70h+var_90], rcx
0x100440f7d  lea     rdx, aSspiDecryptpay; "Sspi::DecryptPayload"
0x100440f84  mov     [rbp+70h+var_88], rdx
0x100440f88  mov     [rbp+70h+var_80], 667h
0x100440f8f  mov     r15d, [rbp+70h+arg_30]
0x100440f96  mov     r12d, [rbp+70h+arg_20]
0x100440f9d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440fa4  jz      short loc_100440FDE
0x100440fa6  mov     [rsp+170h+var_120], r15d
0x100440fab  mov     [rsp+170h+var_128], r14
0x100440fb0  mov     [rsp+170h+var_130], r12d
0x100440fb5  mov     [rsp+170h+var_138], r9
0x100440fba  mov     dword ptr [rsp+170h+var_140], r8d
0x100440fbf  mov     [rsp+170h+var_148], rbx
0x100440fc4  mov     eax, [r13+2Ch]
0x100440fc8  mov     dword ptr [rsp+170h+var_150], eax
0x100440fcc  lea     r9, aApiSniUPdataPB_0; "API|SNI%u#, pData: %p{BYTE*}, cbData: %"...
0x100440fd3  mov     r8d, 667h; int
0x100440fd9  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100440fde  mov     [rsp+170h+var_110], 0
0x100440fe6  mov     [rsp+170h+var_10C], 3
0x100440fee  lea     rax, [rbp+70h+var_78]
0x100440ff2  mov     [rsp+170h+var_108], rax
0x100440ff7  mov     [rbp+70h+var_70], rbx
0x100440ffb  mov     [rbp+70h+var_78], edi
0x100440ffe  mov     [rbp+70h+var_74], 1
0x100441005  mov     [rbp+70h+var_60], rsi
0x100441009  mov     [rbp+70h+var_68], r12d
0x10044100d  mov     [rbp+70h+var_64], 2
0x100441014  mov     [rbp+70h+var_50], r14
0x100441018  mov     [rbp+70h+var_58], r15d
0x10044101c  mov     [rbp+70h+var_54], 9
0x100441023  mov     edx, 1
0x100441028  lea     rcx, [rsp+170h+var_100]
0x10044102d  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x100441032  nop
0x100441033  lea     rax, [rbp+70h+var_F0]
0x100441037  mov     [rbp+70h+var_98], rax
0x10044103b  mov     [rbp+70h+var_E0], 200001E7h
0x100441042  xor     edi, edi
0x100441044  mov     [rbp+70h+var_D8], rdi
0x100441048  mov     [rbp+70h+var_C8], rdi
0x10044104c  mov     [rbp+70h+var_D0], rdi
0x100441050  mov     [rbp+70h+var_C0], rdi
0x100441054  mov     [rbp+70h+var_B0], dil
0x100441058  mov     rdx, gs:58h
0x100441061  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100441068  mov     ecx, [rax]
0x10044106a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100441071  mov     ebx, [rax]
0x100441073  add     rbx, [rdx+rcx*8]
0x100441077  mov     rcx, [rbx+100h]
0x10044107e  test    rcx, rcx
0x100441081  jnz     short loc_100441090
0x100441083  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100441089  mov     rcx, [rbx+100h]
0x100441090  mov     rcx, [rcx+258h]
0x100441097  test    rcx, rcx
0x10044109a  jz      short loc_1004410AC
0x10044109c  lea     rdx, [rbp+70h+var_E0]
0x1004410a0  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x1004410a6  test    eax, eax
0x1004410a8  setz    [rbp+70h+var_B0]
0x1004410ac  mov     rdx, gs:58h
0x1004410b5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004410bc  mov     ecx, [rax]
0x1004410be  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004410c5  mov     ebx, [rax]
0x1004410c7  add     rbx, [rdx+rcx*8]
0x1004410cb  mov     rdx, [rbx+100h]
0x1004410d2  test    rdx, rdx
0x1004410d5  jnz     short loc_1004410E6
0x1004410d7  xor     ecx, ecx
0x1004410d9  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004410df  mov     rdx, [rbx+100h]
0x1004410e6  mov     [rbp+70h+var_E8], rdx
0x1004410ea  mov     eax, [rdx+320h]
0x1004410f0  shr     eax, 0Bh
0x1004410f3  and     eax, 1
0x1004410f6  mov     [rbp+70h+var_EC], eax
0x1004410f9  jnz     short loc_100441109
0x1004410fb  test    byte ptr [rdx+320h], 4
0x100441102  jz      short loc_100441109
0x100441104  mov     [rbp+70h+var_F0], edi
0x100441107  jmp     short loc_10044111E
0x100441109  mov     [rbp+70h+var_F0], 1
0x100441110  mov     rcx, [rdx+260h]
0x100441117  mov     rax, [rcx]
0x10044111a  call    qword ptr [rax+8]
0x10044111d  nop
0x10044111e  mov     rcx, [r13+20h]
0x100441122  xor     r9d, r9d
0x100441125  xor     r8d, r8d
0x100441128  lea     rdx, [rsp+170h+var_110]
0x10044112d  mov     rcx, [rcx+3208h]
0x100441134  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x10044113b  call    qword ptr [rax+0D0h]
0x100441141  mov     ebx, eax
0x100441143  test    eax, eax
0x100441145  jnz     short loc_100441176
0x100441147  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044114e  jz      short loc_1004411A4
0x100441150  mov     dword ptr [rsp+170h+var_150], edi
0x100441154  lea     r9, aSnidecryptmess; "SNIDecryptMessage return value: %d{DWOR"...
0x10044115b  mov     r8d, 68Bh; int
0x100441161  lea     rdx, aSspiDecryptpay; "Sspi::DecryptPayload"
0x100441168  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10044116f  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100441174  jmp     short loc_1004411A4
0x100441176  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044117d  jz      short loc_1004411A4
0x10044117f  mov     dword ptr [rsp+170h+var_150], ebx
0x100441183  lea     r9, aErrSnidecryptm; "ERR|SNIDecryptMessage return value: %d{"...
0x10044118a  mov     r8d, 68Bh; int
0x100441190  lea     rdx, aSspiDecryptpay; "Sspi::DecryptPayload"
0x100441197  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10044119e  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004411a3  nop
0x1004411a4  lea     rcx, [rbp+70h+var_F0]; this
0x1004411a8  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x1004411ad  nop
0x1004411ae  mov     ecx, [rsp+170h+var_100]
0x1004411b2  not     ecx
0x1004411b4  mov     rax, [rsp+170h+var_F8]
0x1004411b9  and     [rax+268h], ecx
0x1004411bf  test    ebx, ebx
0x1004411c1  jz      short loc_10044120E
0x1004411c3  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004411ca  jz      short loc_1004411FC
0x1004411cc  mov     dword ptr [rsp+170h+var_140], ebx
0x1004411d0  mov     dword ptr [rsp+170h+var_148], edi
0x1004411d4  mov     dword ptr [rsp+170h+var_150], 3
0x1004411dc  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004411e3  mov     r8d, 691h; int
0x1004411e9  lea     rdx, aSspiDecryptpay; "Sspi::DecryptPayload"
0x1004411f0  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x1004411f7  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004411fc  mov     r8d, 0C3B4h
0x100441202  mov     edx, ebx
0x100441204  mov     ecx, 3
0x100441209  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10044120e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100441215  jz      short loc_10044123C
0x100441217  mov     dword ptr [rsp+170h+var_150], ebx
0x10044121b  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100441222  mov     r8d, 694h; int
0x100441228  lea     rdx, aSspiDecryptpay; "Sspi::DecryptPayload"
0x10044122f  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x100441236  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044123b  nop
0x10044123c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100441243  jz      short loc_10044125E
0x100441245  mov     r8d, 667h; int
0x10044124b  lea     rdx, aSspiDecryptpay; "Sspi::DecryptPayload"
0x100441252  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x100441259  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10044125e  mov     eax, ebx
0x100441260  mov     rcx, [rbp+70h+var_48]
0x100441264  xor     rcx, rsp; StackCookie
0x100441267  call    __security_check_cookie
0x10044126c  add     rsp, 138h
0x100441273  pop     r15
0x100441275  pop     r14
0x100441277  pop     r13
0x100441279  pop     r12
0x10044127b  pop     rdi
0x10044127c  pop     rsi
0x10044127d  pop     rbx
0x10044127e  pop     rbp
0x10044127f  retn
```
