# Np::StatusWriteNoComplPort(ulong,ulong *)

- ea: `0x10043d0e0`
- end: `0x10043d3f0`
- name: `?StatusWriteNoComplPort@Np@@UEAAKKPEAK@Z`
- size: `784`
- prototype: `unsigned int(Np *__hidden this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x100405270`
- `0x100405390`
- `0x10041f180`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x10043d0e0`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x10043d315`
- `KERNEL32!GetOverlappedResult` at `0x10043d315`
- `KERNEL32!WaitForSingleObject` at `0x10043d268`
- `KERNEL32!WaitForSingleObject` at `0x10043d268`
- `KERNEL32!GetLastError` at `0x10043d27f`
- `KERNEL32!GetLastError` at `0x10043d28c`
- `KERNEL32!GetLastError` at `0x10043d31f`
- `KERNEL32!GetLastError` at `0x10043d27f`
- `KERNEL32!GetLastError` at `0x10043d28c`
- `KERNEL32!GetLastError` at `0x10043d31f`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10043d1df`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10043d1df`
- `sqldk!SystemThread_TlsIndex` at `0x10043d1a0`
- `sqldk!SystemThread_TlsIndex` at `0x10043d1f4`
- `sqldk!SystemThread_TlsOffset` at `0x10043d1a9`
- `sqldk!SystemThread_TlsOffset` at `0x10043d1fd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043d1c2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043d218`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043d1c2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043d218`

## string_xrefs

- `0x10043d111`: `sql\common\dk\sni\src\np.cpp`
- `0x10043d147`: `API|SNI%u#, dwTimeOut: %d, pdwWriteCount: %p{DWORD*}\n`
- `0x10043d11c`: `Np::StatusWriteNoComplPort`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Np::StatusWriteNoComplPort(Np *this, DWORD a2, unsigned int *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rdx
  DWORD v11; // eax
  unsigned int v12; // ebx
  DWORD LastError; // eax
  const wchar_t *v14; // r9
  DWORD v15; // eax
  __int64 v17; // [rsp+20h] [rbp-79h]
  __int64 v18; // [rsp+28h] [rbp-71h]
  __int64 v19; // [rsp+30h] [rbp-69h]
  int v20; // [rsp+40h] [rbp-59h] BYREF
  __int64 v21; // [rsp+48h] [rbp-51h]
  int v22; // [rsp+50h] [rbp-49h] BYREF
  int v23; // [rsp+54h] [rbp-45h]
  __int64 v24; // [rsp+58h] [rbp-41h]
  int v25; // [rsp+60h] [rbp-39h] BYREF
  __int64 v26; // [rsp+68h] [rbp-31h]
  __int64 v27; // [rsp+70h] [rbp-29h]
  __int64 v28; // [rsp+78h] [rbp-21h]
  __int64 v29; // [rsp+80h] [rbp-19h]
  bool v30; // [rsp+90h] [rbp-9h]
  __int64 v31; // [rsp+A0h] [rbp+7h]
  const char *v32; // [rsp+A8h] [rbp+Fh]
  const char *v33; // [rsp+B0h] [rbp+17h]
  int v34; // [rsp+B8h] [rbp+1Fh]
  DWORD NumberOfBytesTransferred; // [rsp+100h] [rbp+67h] BYREF
  int *v36; // [rsp+110h] [rbp+77h]

  v31 = -2;
  v32 = "sql\\common\\dk\\sni\\src\\np.cpp";
  v33 = "Np::StatusWriteNoComplPort";
  v34 = 2335;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::StatusWriteNoComplPort",
      2335,
      L"API|SNI%u#, dwTimeOut: %d, pdwWriteCount: %p{DWORD*}\n",
      *((_DWORD *)this + 11),
      a2,
      a3);
  NumberOfBytesTransferred = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v20, 1);
  v36 = &v22;
  v25 = 536871529;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(_QWORD *)(v7 + 600);
  if ( v8 )
    v30 = (unsigned int)SOS_Task::PushWait(v8, &v25) == 0;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v24 = v10;
  v23 = (*(_DWORD *)(v10 + 800) >> 11) & 1;
  if ( v23 || (*(_BYTE *)(v10 + 800) & 4) == 0 )
  {
    v22 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 608) + 8LL))(*(_QWORD *)(v10 + 608));
  }
  else
  {
    v22 = 0;
  }
  *a3 = 0;
  v11 = WaitForSingleObject(*((HANDLE *)this + 14), a2);
  v12 = v11;
  if ( v11 )
  {
    if ( v11 != 258 && GetLastError() != 997 )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v19) = LastError;
        LODWORD(v18) = 0;
        LODWORD(v17) = *((_DWORD *)this + 18);
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\np.cpp",
          "Np::StatusWriteNoComplPort",
          2364,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v17,
          v18,
          v19);
      }
LABEL_18:
      SNISetLastError(*((unsigned int *)this + 18), v12, 50100);
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v22);
      goto LABEL_25;
    }
    v12 = 997;
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v22);
  }
  else
  {
    SNIPacketRelease(*((struct SNI_Packet **)this + 15));
    *((_QWORD *)this + 15) = 0;
    if ( !GetOverlappedResult(*((HANDLE *)this + 8), (LPOVERLAPPED)((char *)this + 88), &NumberOfBytesTransferred, 0) )
    {
      v15 = GetLastError();
      v12 = v15;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v19) = v15;
        LODWORD(v18) = 0;
        LODWORD(v17) = *((_DWORD *)this + 18);
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\np.cpp",
          "Np::StatusWriteNoComplPort",
          2382,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v17,
          v18,
          v19);
      }
      goto LABEL_18;
    }
    *a3 = NumberOfBytesTransferred;
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v22);
  }
LABEL_25:
  *(_DWORD *)(v21 + 616) &= ~v20;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v17) = v12;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::StatusWriteNoComplPort",
      2392,
      L"RET|SNI%d{WINERR}\n",
      v17);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::StatusWriteNoComplPort", 2335, v14);
  return v12;
}

```

## disassembly

```asm
0x10043d0e0  push    rbp
0x10043d0e2  push    rsi
0x10043d0e3  push    rdi
0x10043d0e4  push    r12
0x10043d0e6  push    r13
0x10043d0e8  push    r14
0x10043d0ea  push    r15
0x10043d0ec  lea     rbp, [rsp-27h]
0x10043d0f1  sub     rsp, 0C0h
0x10043d0f8  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x10043d100  mov     [rsp+0F0h+arg_8], rbx
0x10043d108  mov     rsi, r8
0x10043d10b  mov     r14d, edx
0x10043d10e  mov     rdi, rcx
0x10043d111  lea     r12, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043d118  mov     [rbp+57h+var_48], r12
0x10043d11c  lea     r13, aNpStatuswriten; "Np::StatusWriteNoComplPort"
0x10043d123  mov     [rbp+57h+var_40], r13
0x10043d127  mov     [rbp+57h+var_38], 91Fh
0x10043d12e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043d135  jz      short loc_10043D15F
0x10043d137  mov     [rsp+0F0h+var_C0], r8
0x10043d13c  mov     dword ptr [rsp+0F0h+var_C8], edx
0x10043d140  mov     eax, [rcx+2Ch]
0x10043d143  mov     dword ptr [rsp+0F0h+var_D0], eax
0x10043d147  lea     r9, aApiSniUDwtimeo; "API|SNI%u#, dwTimeOut: %d, pdwWriteCoun"...
0x10043d14e  mov     r8d, 91Fh; int
0x10043d154  mov     rdx, r13; char *
0x10043d157  mov     rcx, r12; char *
0x10043d15a  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10043d15f  xor     r15d, r15d
0x10043d162  mov     [rbp+57h+NumberOfBytesTransferred], r15d
0x10043d166  lea     edx, [r15+1]
0x10043d16a  lea     rcx, [rbp+57h+var_B0]
0x10043d16e  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10043d173  nop
0x10043d174  lea     rax, [rbp+57h+var_A0]
0x10043d178  mov     [rbp+57h+arg_10], rax
0x10043d17c  mov     [rbp+57h+var_90], 20000269h
0x10043d183  mov     [rbp+57h+var_88], r15
0x10043d187  mov     [rbp+57h+var_78], r15
0x10043d18b  mov     [rbp+57h+var_80], r15
0x10043d18f  mov     [rbp+57h+var_70], r15
0x10043d193  mov     [rbp+57h+var_60], r15b
0x10043d197  mov     rdx, gs:58h
0x10043d1a0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043d1a7  mov     ecx, [rax]
0x10043d1a9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043d1b0  mov     ebx, [rax]
0x10043d1b2  add     rbx, [rdx+rcx*8]
0x10043d1b6  mov     rcx, [rbx+100h]
0x10043d1bd  test    rcx, rcx
0x10043d1c0  jnz     short loc_10043D1CF
0x10043d1c2  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043d1c8  mov     rcx, [rbx+100h]
0x10043d1cf  mov     rcx, [rcx+258h]
0x10043d1d6  test    rcx, rcx
0x10043d1d9  jz      short loc_10043D1EB
0x10043d1db  lea     rdx, [rbp+57h+var_90]
0x10043d1df  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10043d1e5  test    eax, eax
0x10043d1e7  setz    [rbp+57h+var_60]
0x10043d1eb  mov     rdx, gs:58h
0x10043d1f4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043d1fb  mov     ecx, [rax]
0x10043d1fd  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043d204  mov     ebx, [rax]
0x10043d206  add     rbx, [rdx+rcx*8]
0x10043d20a  mov     rdx, [rbx+100h]
0x10043d211  test    rdx, rdx
0x10043d214  jnz     short loc_10043D225
0x10043d216  xor     ecx, ecx
0x10043d218  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043d21e  mov     rdx, [rbx+100h]
0x10043d225  mov     [rbp+57h+var_98], rdx
0x10043d229  mov     eax, [rdx+320h]
0x10043d22f  shr     eax, 0Bh
0x10043d232  and     eax, 1
0x10043d235  mov     [rbp+57h+var_9C], eax
0x10043d238  jnz     short loc_10043D249
0x10043d23a  test    byte ptr [rdx+320h], 4
0x10043d241  jz      short loc_10043D249
0x10043d243  mov     [rbp+57h+var_A0], r15d
0x10043d247  jmp     short loc_10043D25E
0x10043d249  mov     [rbp+57h+var_A0], 1
0x10043d250  mov     rcx, [rdx+260h]
0x10043d257  mov     rax, [rcx]
0x10043d25a  call    qword ptr [rax+8]
0x10043d25d  nop
0x10043d25e  mov     [rsi], r15d
0x10043d261  mov     edx, r14d; dwMilliseconds
0x10043d264  mov     rcx, [rdi+70h]; hHandle
0x10043d268  call    cs:__imp_WaitForSingleObject
0x10043d26e  mov     ebx, eax
0x10043d270  test    eax, eax
0x10043d272  jz      loc_10043D2F9
0x10043d278  cmp     eax, 102h
0x10043d27d  jz      short loc_10043D2E5
0x10043d27f  call    cs:__imp_GetLastError
0x10043d285  cmp     eax, 3E5h
0x10043d28a  jz      short loc_10043D2E5
0x10043d28c  call    cs:__imp_GetLastError
0x10043d292  mov     ebx, eax
0x10043d294  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043d29b  jz      short loc_10043D2C5
0x10043d29d  mov     dword ptr [rsp+0F0h+var_C0], eax
0x10043d2a1  mov     dword ptr [rsp+0F0h+var_C8], r15d
0x10043d2a6  mov     eax, [rdi+48h]
0x10043d2a9  mov     dword ptr [rsp+0F0h+var_D0], eax
0x10043d2ad  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043d2b4  mov     r8d, 93Ch; int
0x10043d2ba  mov     rdx, r13; char *
0x10043d2bd  mov     rcx, r12; char *
0x10043d2c0  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043d2c5  mov     r8d, 0C3B4h
0x10043d2cb  mov     edx, ebx
0x10043d2cd  mov     ecx, [rdi+48h]
0x10043d2d0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043d2d5  nop
0x10043d2d6  lea     rcx, [rbp+57h+var_A0]; this
0x10043d2da  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10043d2df  nop
0x10043d2e0  jmp     loc_10043D384
0x10043d2e5  mov     ebx, 3E5h
0x10043d2ea  lea     rcx, [rbp+57h+var_A0]; this
0x10043d2ee  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10043d2f3  nop
0x10043d2f4  jmp     loc_10043D384
0x10043d2f9  mov     rcx, [rdi+78h]; struct SNI_Packet *
0x10043d2fd  call    SNIPacketRelease
0x10043d302  mov     [rdi+78h], r15
0x10043d306  lea     rdx, [rdi+58h]; lpOverlapped
0x10043d30a  xor     r9d, r9d; bWait
0x10043d30d  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x10043d311  mov     rcx, [rdi+40h]; hFile
0x10043d315  call    cs:__imp_GetOverlappedResult
0x10043d31b  test    eax, eax
0x10043d31d  jnz     short loc_10043D375
0x10043d31f  call    cs:__imp_GetLastError
0x10043d325  mov     ebx, eax
0x10043d327  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043d32e  jz      short loc_10043D358
0x10043d330  mov     dword ptr [rsp+0F0h+var_C0], eax
0x10043d334  mov     dword ptr [rsp+0F0h+var_C8], r15d
0x10043d339  mov     eax, [rdi+48h]
0x10043d33c  mov     dword ptr [rsp+0F0h+var_D0], eax
0x10043d340  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043d347  mov     r8d, 94Eh; int
0x10043d34d  mov     rdx, r13; char *
0x10043d350  mov     rcx, r12; char *
0x10043d353  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043d358  mov     r8d, 0C3B4h
0x10043d35e  mov     edx, ebx
0x10043d360  mov     ecx, [rdi+48h]
0x10043d363  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043d368  nop
0x10043d369  lea     rcx, [rbp+57h+var_A0]; this
0x10043d36d  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10043d372  nop
0x10043d373  jmp     short loc_10043D384
0x10043d375  mov     eax, [rbp+57h+NumberOfBytesTransferred]
0x10043d378  mov     [rsi], eax
0x10043d37a  lea     rcx, [rbp+57h+var_A0]; this
0x10043d37e  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10043d383  nop
0x10043d384  mov     ecx, [rbp+57h+var_B0]
0x10043d387  mov     rax, [rbp+57h+var_A8]
0x10043d38b  not     ecx
0x10043d38d  and     [rax+268h], ecx
0x10043d393  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043d39a  jz      short loc_10043D3B9
0x10043d39c  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x10043d3a0  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043d3a7  mov     r8d, 958h; int
0x10043d3ad  mov     rdx, r13; char *
0x10043d3b0  mov     rcx, r12; char *
0x10043d3b3  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043d3b8  nop
0x10043d3b9  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043d3c0  jz      short loc_10043D3D3
0x10043d3c2  mov     r8d, 91Fh; int
0x10043d3c8  mov     rdx, r13; char *
0x10043d3cb  mov     rcx, r12; char *
0x10043d3ce  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10043d3d3  mov     eax, ebx
0x10043d3d5  mov     rbx, [rsp+0F0h+arg_8]
0x10043d3dd  add     rsp, 0C0h
0x10043d3e4  pop     r15
0x10043d3e6  pop     r14
0x10043d3e8  pop     r13
0x10043d3ea  pop     r12
0x10043d3ec  pop     rdi
0x10043d3ed  pop     rsi
0x10043d3ee  pop     rbp
0x10043d3ef  retn
```
