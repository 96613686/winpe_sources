# Sspi::VerifySignature(uchar *,ulong,uchar *,ulong)

- ea: `0x100440c30`
- end: `0x100440f28`
- name: `?VerifySignature@Sspi@@AEAAKPEAEK0K@Z`
- size: `760`
- prototype: `unsigned int __fastcall(Sspi *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
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
- `0x100440c30`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100440d74`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100440d74`
- `sqldk!SystemThread_TlsIndex` at `0x100440d35`
- `sqldk!SystemThread_TlsIndex` at `0x100440d89`
- `sqldk!SystemThread_TlsOffset` at `0x100440d3e`
- `sqldk!SystemThread_TlsOffset` at `0x100440d92`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100440d57`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100440dad`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100440d57`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100440dad`

## string_xrefs

- `0x100440c67`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Sspi::VerifySignature(Sspi *this, unsigned __int8 *a2, int a3, unsigned __int8 *a4, unsigned int a5)
{
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  const wchar_t *v16; // r9
  __int64 v18; // [rsp+28h] [rbp-B1h]
  __int64 v19; // [rsp+30h] [rbp-A9h]
  __int64 v20; // [rsp+38h] [rbp-A1h]
  _DWORD v21[2]; // [rsp+58h] [rbp-81h] BYREF
  _DWORD *v22; // [rsp+60h] [rbp-79h]
  _DWORD v23[2]; // [rsp+68h] [rbp-71h] BYREF
  unsigned __int8 *v24; // [rsp+70h] [rbp-69h]
  unsigned int v25; // [rsp+78h] [rbp-61h]
  int v26; // [rsp+7Ch] [rbp-5Dh]
  unsigned __int8 *v27; // [rsp+80h] [rbp-59h]
  int v28; // [rsp+88h] [rbp-51h] BYREF
  __int64 v29; // [rsp+90h] [rbp-49h]
  int v30; // [rsp+98h] [rbp-41h] BYREF
  int v31; // [rsp+9Ch] [rbp-3Dh]
  __int64 v32; // [rsp+A0h] [rbp-39h]
  int v33; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-29h]
  __int64 v35; // [rsp+B8h] [rbp-21h]
  __int64 v36; // [rsp+C0h] [rbp-19h]
  __int64 v37; // [rsp+C8h] [rbp-11h]
  bool v38; // [rsp+D8h] [rbp-1h]
  __int64 v39; // [rsp+E8h] [rbp+Fh]
  const char *v40; // [rsp+F0h] [rbp+17h]
  const char *v41; // [rsp+F8h] [rbp+1Fh]
  int v42; // [rsp+100h] [rbp+27h]

  v39 = -2;
  v40 = "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp";
  v41 = "Sspi::VerifySignature";
  v42 = 1556;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::VerifySignature",
      1556,
      L"API|SNI%u#, pData: %p{BYTE*}, cbData: %d{DWORD}, pSignature: %p{BYTE*}, cbSignature: %d{DWORD}\n",
      *((_DWORD *)this + 11),
      a2,
      a3,
      a4,
      a5);
  v21[0] = 0;
  v21[1] = 2;
  v22 = v23;
  v24 = a2;
  v23[0] = a3;
  v23[1] = 1;
  v27 = a4;
  v25 = a5;
  v26 = 2;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v28, 1);
  v33 = 536871399;
  v34 = 0;
  v36 = 0;
  v35 = 0;
  v37 = 0;
  v38 = 0;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v11 = *(_QWORD *)(v10 + 600);
  if ( v11 )
    v38 = (unsigned int)SOS_Task::PushWait(v11, &v33) == 0;
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v13 = *(_QWORD *)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(_QWORD *)(v12 + 256);
  }
  v32 = v13;
  v31 = (*(_DWORD *)(v13 + 800) >> 11) & 1;
  if ( v31 || (*(_BYTE *)(v13 + 800) & 4) == 0 )
  {
    v30 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v13 + 608) + 8LL))(*(_QWORD *)(v13 + 608));
  }
  else
  {
    v30 = 0;
  }
  v14 = ((__int64 (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD))g_pFuncs->VerifySignature)(
          *(_QWORD *)(*((_QWORD *)this + 4) + 12808LL),
          v21,
          0,
          0);
  v15 = v14;
  if ( v14 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v18) = v14;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::VerifySignature",
        1587,
        L"ERR|SNIVerifySignature return value: %d{DWORD}\n",
        v18);
    }
  }
  else if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v18) = 0;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::VerifySignature",
      1587,
      L"SNIVerifySignature return value: %d{DWORD}\n",
      v18);
  }
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v30);
  *(_DWORD *)(v29 + 616) &= ~v28;
  if ( v15 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v20) = v15;
      LODWORD(v19) = 0;
      LODWORD(v18) = 3;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::VerifySignature",
        1593,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v18,
        v19,
        v20);
    }
    SNISetLastError(3, v15, 50100);
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v18) = v15;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::VerifySignature",
      1596,
      L"RET|SNI%d{WINERR}\n",
      v18);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp", "Sspi::VerifySignature", 1556, v16);
  return v15;
}

```

## disassembly

```asm
0x100440c30  mov     rax, rsp
0x100440c33  push    rbp
0x100440c34  push    r12
0x100440c36  push    r13
0x100440c38  push    r14
0x100440c3a  push    r15
0x100440c3c  lea     rbp, [rax-57h]
0x100440c40  sub     rsp, 100h
0x100440c47  mov     [rbp+4Fh+var_40], 0FFFFFFFFFFFFFFFEh
0x100440c4f  mov     [rax+10h], rbx
0x100440c53  mov     [rax+18h], rsi
0x100440c57  mov     [rax+20h], rdi
0x100440c5b  mov     rbx, r9
0x100440c5e  mov     edi, r8d
0x100440c61  mov     rsi, rdx
0x100440c64  mov     r15, rcx
0x100440c67  lea     r12, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x100440c6e  mov     [rbp+4Fh+var_38], r12
0x100440c72  lea     r13, aSspiVerifysign; "Sspi::VerifySignature"
0x100440c79  mov     [rbp+4Fh+var_30], r13
0x100440c7d  mov     [rbp+4Fh+var_28], 614h
0x100440c84  mov     r14d, [rbp+4Fh+arg_20]
0x100440c88  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440c8f  jz      short loc_100440CC4
0x100440c91  mov     [rsp+120h+var_E0], r14d
0x100440c96  mov     qword ptr [rsp+120h+var_E8], rbx
0x100440c9b  mov     dword ptr [rsp+120h+var_F0], r8d
0x100440ca0  mov     [rsp+120h+var_F8], rdx
0x100440ca5  mov     eax, [rcx+2Ch]
0x100440ca8  mov     dword ptr [rsp+120h+var_100], eax
0x100440cac  lea     r9, aApiSniUPdataPB; "API|SNI%u#, pData: %p{BYTE*}, cbData: %"...
0x100440cb3  mov     r8d, 614h; int
0x100440cb9  mov     rdx, r13; char *
0x100440cbc  mov     rcx, r12; char *
0x100440cbf  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100440cc4  mov     [rsp+120h+var_D0], 0
0x100440ccc  mov     [rbp+4Fh+var_CC], 2
0x100440cd3  lea     rax, [rbp+4Fh+var_C0]
0x100440cd7  mov     [rbp+4Fh+var_C8], rax
0x100440cdb  mov     [rbp+4Fh+var_B8], rsi
0x100440cdf  mov     [rbp+4Fh+var_C0], edi
0x100440ce2  mov     [rbp+4Fh+var_BC], 1
0x100440ce9  mov     [rbp+4Fh+var_A8], rbx
0x100440ced  mov     [rbp+4Fh+var_B0], r14d
0x100440cf1  mov     [rbp+4Fh+var_AC], 2
0x100440cf8  mov     edx, 1
0x100440cfd  lea     rcx, [rbp+4Fh+var_A0]
0x100440d01  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x100440d06  nop
0x100440d07  lea     rax, [rbp+4Fh+var_90]
0x100440d0b  mov     [rbp+4Fh+arg_0], rax
0x100440d0f  mov     [rbp+4Fh+var_80], 200001E7h
0x100440d16  xor     edi, edi
0x100440d18  mov     [rbp+4Fh+var_78], rdi
0x100440d1c  mov     [rbp+4Fh+var_68], rdi
0x100440d20  mov     [rbp+4Fh+var_70], rdi
0x100440d24  mov     [rbp+4Fh+var_60], rdi
0x100440d28  mov     [rbp+4Fh+var_50], dil
0x100440d2c  mov     rdx, gs:58h
0x100440d35  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100440d3c  mov     ecx, [rax]
0x100440d3e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100440d45  mov     ebx, [rax]
0x100440d47  add     rbx, [rdx+rcx*8]
0x100440d4b  mov     rcx, [rbx+100h]
0x100440d52  test    rcx, rcx
0x100440d55  jnz     short loc_100440D64
0x100440d57  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100440d5d  mov     rcx, [rbx+100h]
0x100440d64  mov     rcx, [rcx+258h]
0x100440d6b  test    rcx, rcx
0x100440d6e  jz      short loc_100440D80
0x100440d70  lea     rdx, [rbp+4Fh+var_80]
0x100440d74  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x100440d7a  test    eax, eax
0x100440d7c  setz    [rbp+4Fh+var_50]
0x100440d80  mov     rdx, gs:58h
0x100440d89  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100440d90  mov     ecx, [rax]
0x100440d92  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100440d99  mov     ebx, [rax]
0x100440d9b  add     rbx, [rdx+rcx*8]
0x100440d9f  mov     rdx, [rbx+100h]
0x100440da6  test    rdx, rdx
0x100440da9  jnz     short loc_100440DBA
0x100440dab  xor     ecx, ecx
0x100440dad  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100440db3  mov     rdx, [rbx+100h]
0x100440dba  mov     [rbp+4Fh+var_88], rdx
0x100440dbe  mov     eax, [rdx+320h]
0x100440dc4  shr     eax, 0Bh
0x100440dc7  and     eax, 1
0x100440dca  mov     [rbp+4Fh+var_8C], eax
0x100440dcd  jnz     short loc_100440DDD
0x100440dcf  test    byte ptr [rdx+320h], 4
0x100440dd6  jz      short loc_100440DDD
0x100440dd8  mov     [rbp+4Fh+var_90], edi
0x100440ddb  jmp     short loc_100440DF2
0x100440ddd  mov     [rbp+4Fh+var_90], 1
0x100440de4  mov     rcx, [rdx+260h]
0x100440deb  mov     rax, [rcx]
0x100440dee  call    qword ptr [rax+8]
0x100440df1  nop
0x100440df2  mov     rcx, [r15+20h]
0x100440df6  xor     r9d, r9d
0x100440df9  xor     r8d, r8d
0x100440dfc  lea     rdx, [rsp+120h+var_D0]
0x100440e01  mov     rcx, [rcx+3208h]
0x100440e08  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x100440e0f  call    qword ptr [rax+78h]
0x100440e12  mov     ebx, eax
0x100440e14  test    eax, eax
0x100440e16  jnz     short loc_100440E3F
0x100440e18  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440e1f  jz      short loc_100440E65
0x100440e21  mov     dword ptr [rsp+120h+var_100], edi
0x100440e25  lea     r9, aSniverifysigna; "SNIVerifySignature return value: %d{DWO"...
0x100440e2c  mov     r8d, 633h; int
0x100440e32  mov     rdx, r13; char *
0x100440e35  mov     rcx, r12; char *
0x100440e38  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100440e3d  jmp     short loc_100440E65
0x100440e3f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440e46  jz      short loc_100440E65
0x100440e48  mov     dword ptr [rsp+120h+var_100], ebx
0x100440e4c  lea     r9, aErrSniverifysi; "ERR|SNIVerifySignature return value: %d"...
0x100440e53  mov     r8d, 633h; int
0x100440e59  mov     rdx, r13; char *
0x100440e5c  mov     rcx, r12; char *
0x100440e5f  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100440e64  nop
0x100440e65  lea     rcx, [rbp+4Fh+var_90]; this
0x100440e69  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x100440e6e  nop
0x100440e6f  mov     ecx, [rbp+4Fh+var_A0]
0x100440e72  not     ecx
0x100440e74  mov     rax, [rbp+4Fh+var_98]
0x100440e78  and     [rax+268h], ecx
0x100440e7e  test    ebx, ebx
0x100440e80  jz      short loc_100440EC5
0x100440e82  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440e89  jz      short loc_100440EB3
0x100440e8b  mov     dword ptr [rsp+120h+var_F0], ebx
0x100440e8f  mov     dword ptr [rsp+120h+var_F8], edi
0x100440e93  mov     dword ptr [rsp+120h+var_100], 3
0x100440e9b  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100440ea2  mov     r8d, 639h; int
0x100440ea8  mov     rdx, r13; char *
0x100440eab  mov     rcx, r12; char *
0x100440eae  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100440eb3  mov     r8d, 0C3B4h
0x100440eb9  mov     edx, ebx
0x100440ebb  mov     ecx, 3
0x100440ec0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100440ec5  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440ecc  jz      short loc_100440EEB
0x100440ece  mov     dword ptr [rsp+120h+var_100], ebx
0x100440ed2  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100440ed9  mov     r8d, 63Ch; int
0x100440edf  mov     rdx, r13; char *
0x100440ee2  mov     rcx, r12; char *
0x100440ee5  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100440eea  nop
0x100440eeb  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100440ef2  jz      short loc_100440F05
0x100440ef4  mov     r8d, 614h; int
0x100440efa  mov     rdx, r13; char *
0x100440efd  mov     rcx, r12; char *
0x100440f00  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100440f05  mov     eax, ebx
0x100440f07  lea     r11, [rsp+120h+var_20]
0x100440f0f  mov     rbx, [r11+38h]
0x100440f13  mov     rsi, [r11+40h]
0x100440f17  mov     rdi, [r11+48h]
0x100440f1b  mov     rsp, r11
0x100440f1e  pop     r15
0x100440f20  pop     r14
0x100440f22  pop     r13
0x100440f24  pop     r12
0x100440f26  pop     rbp
0x100440f27  retn
```
