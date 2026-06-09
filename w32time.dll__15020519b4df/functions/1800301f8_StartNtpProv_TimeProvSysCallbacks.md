# StartNtpProv(TimeProvSysCallbacks *)

- ea: `0x1800301f8`
- end: `0x1800305bf`
- name: `?StartNtpProv@@YAJPEAUTimeProvSysCallbacks@@@Z`
- size: `967`
- prototype: `__int64 __fastcall(struct TimeProvSysCallbacks *)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180030090`

## callees

- `0x180015460`
- `0x180015620`
- `0x180016454`
- `0x1800180c4`
- `0x180018138`
- `0x180019714`
- `0x18001d9a0`
- `0x180026200`
- `0x180029bbc`
- `0x18002a120`
- `0x18002b7b0`
- `0x1800301f8`
- `0x180030990`
- `0x18003d294`
- `0x18003dd2c`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180030280`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180030280`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800303a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030496`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800304c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800303a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030496`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800304c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800303c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800303c0`
- `DSROLE!DsRoleFreeMemory` at `0x180030592`
- `DSROLE!DsRoleFreeMemory` at `0x180030592`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180030338`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180030338`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StartNtpProv(struct TimeProvSysCallbacks *a1)
{
  _BYTE *v2; // rbx
  int InitialSockets; // ebx
  _NtpProvState *v4; // rax
  int v5; // edx
  signed int PrimaryDomainInformation; // eax
  bool v7; // cc
  int v8; // eax
  _NtpProvState *v9; // rdx
  HANDLE EventW; // rax
  _NtpProvState *v11; // rcx
  _NtpProvState *v12; // rcx
  _NtpProvState *v13; // rcx
  int AllowTimestampsSetting; // eax
  _NtpProvState *v15; // rcx
  HANDLE v16; // rax
  HANDLE v17; // rax
  _NtpProvState *v18; // rcx
  _NtpProvState *v19; // rcx
  void *v20; // rdx
  void *v21; // r9
  int v22; // eax
  unsigned int v24; // [rsp+30h] [rbp-18h]
  int v25; // [rsp+58h] [rbp+10h] BYREF
  PBYTE Buffer; // [rsp+60h] [rbp+18h] BYREF
  _BYTE *v27; // [rsp+68h] [rbp+20h]

  Buffer = 0;
  if ( (unsigned __int8)FileLogAllowEntry(59) )
    FileLogAdd(L"StartNtpProv\n");
  v2 = operator new(0x488u);
  v27 = v2;
  v2[50] = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>((_QWORD *)v2 + 51);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>((_QWORD *)v2 + 54);
  g_pnpstate = (_NtpProvState *)v2;
  memset_0(v2, 0, 0x488u);
  *((_QWORD *)v2 + 67) = v2 + 528;
  *((_QWORD *)v2 + 66) = v2 + 528;
  *v2 = 1;
  *((_QWORD *)g_pnpstate + 143) = GetTickCount64();
  if ( a1->dwSize != 40 )
  {
    InitialSockets = -2147024809;
    goto LABEL_34;
  }
  v4 = g_pnpstate;
  *(_OWORD *)((char *)g_pnpstate + 8) = *(_OWORD *)&a1->dwSize;
  *(_OWORD *)((char *)v4 + 24) = *(_OWORD *)&a1->pfnLogTimeProvEvent;
  *((_QWORD *)v4 + 5) = a1->pfnSetProviderStatus;
  v25 = 0;
  (*((void (__fastcall **)(__int64, int *))v4 + 2))(2, &v25);
  if ( v25 >= 0 )
    v5 = 10000000 << v25;
  else
    v5 = 10000000 >> -(char)v25;
  *((_DWORD *)g_pnpstate + 13) = v5;
  if ( (unsigned __int8)FileLogAllowEntry(59) )
    FileLogAdd(L"sysPrecision=%d, systmeClockResolution=%ld\n", (unsigned int)v25, *((unsigned int *)g_pnpstate + 13));
  PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
  InitialSockets = PrimaryDomainInformation;
  v7 = PrimaryDomainInformation <= 0;
  if ( PrimaryDomainInformation )
    goto LABEL_11;
  v8 = 15;
  if ( (unsigned int)(*(_DWORD *)Buffer - 4) > 1 )
    v8 = 17;
  v9 = g_pnpstate;
  *((_DWORD *)g_pnpstate + 70) = v8;
  *((_BYTE *)v9 + 508) = (*((_DWORD *)Buffer + 1) & 8) != 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v11 = g_pnpstate;
  *((_QWORD *)g_pnpstate + 58) = EventW;
  if ( !EventW )
    goto LABEL_16;
  InitialSockets = myInitializeCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 328));
  if ( InitialSockets < 0 )
    goto LABEL_34;
  v12 = g_pnpstate;
  *((_BYTE *)g_pnpstate + 285) = 1;
  InitialSockets = myInitializeCriticalSection((LPCRITICAL_SECTION)((char *)v12 + 288));
  if ( InitialSockets < 0 )
    goto LABEL_34;
  v13 = g_pnpstate;
  *((_BYTE *)g_pnpstate + 284) = 1;
  InitialSockets = myInitializeCriticalSection((LPCRITICAL_SECTION)((char *)v13 + 368));
  if ( InitialSockets < 0 )
    goto LABEL_34;
  *((_BYTE *)g_pnpstate + 286) = 1;
  InitialSockets = OpenSocketLayer();
  if ( InitialSockets < 0 )
    goto LABEL_34;
  *((_BYTE *)g_pnpstate + 56) = 1;
  AllowTimestampsSetting = ReadAllowTimestampsSetting();
  v15 = g_pnpstate;
  *((_BYTE *)g_pnpstate + 80) = AllowTimestampsSetting != 0;
  InitialSockets = GetInitialSockets((struct NicSocket ***)v15 + 8, (unsigned int *)v15 + 18, (unsigned int *)v15 + 19);
  if ( InitialSockets < 0 )
    goto LABEL_34;
  v16 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)g_pnpstate + 11) = v16;
  if ( !v16 || (v17 = CreateEventW(0, 0, 0, 0), v18 = g_pnpstate, (*((_QWORD *)g_pnpstate + 12) = v17) == 0) )
  {
LABEL_16:
    PrimaryDomainInformation = GetLastError();
    InitialSockets = PrimaryDomainInformation;
    v7 = PrimaryDomainInformation <= 0;
LABEL_11:
    if ( !v7 )
      InitialSockets = (unsigned __int16)PrimaryDomainInformation | 0x80070000;
    goto LABEL_34;
  }
  InitialSockets = myCreateTimerQueueTimer((struct _RTL_CRITICAL_SECTION **)v18 + 17);
  if ( InitialSockets < 0 )
    goto LABEL_34;
  v19 = g_pnpstate;
  if ( *((_BYTE *)g_pnpstate + 508) && !*((_BYTE *)g_pnpstate + 548) )
  {
    InitialSockets = myCreateTimerQueueTimer((struct _RTL_CRITICAL_SECTION **)g_pnpstate + 61);
    if ( InitialSockets < 0 )
      goto LABEL_34;
    v19 = g_pnpstate;
    v22 = *((_DWORD *)g_pnpstate + 130);
    if ( v22 )
    {
      InitialSockets = myStartTimerQueueTimer(
                         *((LPCRITICAL_SECTION *)g_pnpstate + 61),
                         v20,
                         (void (*)(void *, unsigned __int8))HandleChainingCountTimeout,
                         v21,
                         0,
                         60000 * v22,
                         v24);
      if ( InitialSockets < 0 )
        goto LABEL_34;
      v19 = g_pnpstate;
      *((_BYTE *)g_pnpstate + 524) = 1;
    }
  }
  *((_BYTE *)v19 + 50) = 0;
  InitialSockets = StartListeningThread();
  if ( InitialSockets >= 0 )
  {
    InitialSockets = StartPeerPollingThread();
    if ( InitialSockets >= 0 )
      InitialSockets = 0;
  }
LABEL_34:
  if ( Buffer )
    DsRoleFreeMemory(Buffer);
  if ( InitialSockets < 0 && g_pnpstate )
    StopNtpProv();
  return (unsigned int)InitialSockets;
}

```

## disassembly

```asm
0x1800301f8  mov     [rsp+arg_0], rbx
0x1800301fd  push    rdi
0x1800301fe  sub     rsp, 40h
0x180030202  mov     rdi, rcx
0x180030205  mov     [rsp+48h+Buffer], 0
0x18003020e  mov     ecx, 3Bh ; ';'
0x180030213  call    FileLogAllowEntry
0x180030218  test    al, al
0x18003021a  jz      short loc_180030228
0x18003021c  lea     rcx, aStartntpprov; "StartNtpProv\n"
0x180030223  call    FileLogAdd
0x180030228  mov     ecx, 488h; Size
0x18003022d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030232  mov     rbx, rax
0x180030235  mov     [rsp+48h+arg_18], rax
0x18003023a  mov     byte ptr [rax+32h], 0
0x18003023e  lea     rcx, [rax+198h]
0x180030245  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18003024a  nop
0x18003024b  lea     rcx, [rbx+1B0h]
0x180030252  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180030257  nop
0x180030258  mov     cs:?g_pnpstate@@3PEAU_NtpProvState@@EA, rbx; _NtpProvState * g_pnpstate
0x18003025f  xor     edx, edx; Val
0x180030261  mov     r8d, 488h; Size
0x180030267  mov     rcx, rbx; void *
0x18003026a  call    memset_0
0x18003026f  lea     rax, [rbx+210h]
0x180030276  mov     [rax+8], rax
0x18003027a  mov     [rax], rax
0x18003027d  mov     byte ptr [rbx], 1
0x180030280  call    cs:__imp_GetTickCount64
0x180030287  nop     dword ptr [rax+rax+00h]
0x18003028c  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180030293  mov     [rcx+478h], rax
0x18003029a  cmp     dword ptr [rdi], 28h ; '('
0x18003029d  jz      short loc_1800302A9
0x18003029f  mov     ebx, 80070057h
0x1800302a4  jmp     loc_180030588
0x1800302a9  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800302b0  movups  xmm0, xmmword ptr [rdi]
0x1800302b3  movups  xmmword ptr [rax+8], xmm0
0x1800302b7  movups  xmm1, xmmword ptr [rdi+10h]
0x1800302bb  movups  xmmword ptr [rax+18h], xmm1
0x1800302bf  movsd   xmm0, qword ptr [rdi+20h]
0x1800302c4  movsd   qword ptr [rax+28h], xmm0
0x1800302c9  mov     [rsp+48h+arg_8], 0
0x1800302d1  lea     rdx, [rsp+48h+arg_8]
0x1800302d6  mov     ecx, 2
0x1800302db  mov     rax, [rax+10h]
0x1800302df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302e4  mov     ecx, [rsp+48h+arg_8]
0x1800302e8  mov     edx, 989680h
0x1800302ed  test    ecx, ecx
0x1800302ef  jns     short loc_1800302F7
0x1800302f1  neg     ecx
0x1800302f3  sar     edx, cl
0x1800302f5  jmp     short loc_1800302F9
0x1800302f7  shl     edx, cl
0x1800302f9  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180030300  mov     [rax+34h], edx
0x180030303  mov     ecx, 3Bh ; ';'
0x180030308  call    FileLogAllowEntry
0x18003030d  test    al, al
0x18003030f  jz      short loc_18003032C
0x180030311  mov     r8, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180030318  mov     r8d, [r8+34h]
0x18003031c  mov     edx, [rsp+48h+arg_8]
0x180030320  lea     rcx, aSysprecisionDS; "sysPrecision=%d, systmeClockResolution="...
0x180030327  call    FileLogAdd
0x18003032c  lea     r8, [rsp+48h+Buffer]; Buffer
0x180030331  mov     edx, 1; InfoLevel
0x180030336  xor     ecx, ecx; lpServer
0x180030338  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x18003033f  nop     dword ptr [rax+rax+00h]
0x180030344  mov     ebx, eax
0x180030346  test    eax, eax
0x180030348  jz      short loc_18003035E
0x18003034a  jle     loc_180030588
0x180030350  movzx   ebx, ax
0x180030353  or      ebx, 80070000h
0x180030359  jmp     loc_180030588
0x18003035e  mov     rax, [rsp+48h+Buffer]
0x180030363  mov     ecx, [rax]
0x180030365  sub     ecx, 4
0x180030368  mov     eax, 0Fh
0x18003036d  lea     edx, [rax+2]
0x180030370  cmp     ecx, 1
0x180030373  cmova   eax, edx
0x180030376  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003037d  mov     [rdx+118h], eax
0x180030383  mov     rax, [rsp+48h+Buffer]
0x180030388  mov     ecx, [rax+4]
0x18003038b  shr     ecx, 3
0x18003038e  and     cl, 1
0x180030391  mov     [rdx+1FCh], cl
0x180030397  xor     r9d, r9d; lpName
0x18003039a  xor     r8d, r8d; bInitialState
0x18003039d  xor     edx, edx; bManualReset
0x18003039f  xor     ecx, ecx; lpEventAttributes
0x1800303a1  call    cs:__imp_CreateEventW
0x1800303a8  nop     dword ptr [rax+rax+00h]
0x1800303ad  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800303b4  mov     [rcx+1D0h], rax
0x1800303bb  test    rax, rax
0x1800303be  jnz     short loc_1800303D5
0x1800303c0  call    cs:__imp_GetLastError
0x1800303c7  nop     dword ptr [rax+rax+00h]
0x1800303cc  mov     ebx, eax
0x1800303ce  test    eax, eax
0x1800303d0  jmp     loc_18003034A
0x1800303d5  add     rcx, 148h; lpCriticalSection
0x1800303dc  call    ?myInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; myInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800303e1  mov     ebx, eax
0x1800303e3  test    eax, eax
0x1800303e5  js      loc_180030588
0x1800303eb  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800303f2  mov     byte ptr [rcx+11Dh], 1
0x1800303f9  add     rcx, 120h; lpCriticalSection
0x180030400  call    ?myInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; myInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x180030405  mov     ebx, eax
0x180030407  test    eax, eax
0x180030409  js      loc_180030588
0x18003040f  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180030416  mov     byte ptr [rcx+11Ch], 1
0x18003041d  add     rcx, 170h; lpCriticalSection
0x180030424  call    ?myInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; myInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x180030429  mov     ebx, eax
0x18003042b  test    eax, eax
0x18003042d  js      loc_180030588
0x180030433  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003043a  mov     byte ptr [rax+11Eh], 1
0x180030441  call    ?OpenSocketLayer@@YAJXZ; OpenSocketLayer(void)
0x180030446  mov     ebx, eax
0x180030448  test    eax, eax
0x18003044a  js      loc_180030588
0x180030450  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180030457  mov     byte ptr [rax+38h], 1
0x18003045b  call    ?ReadAllowTimestampsSetting@@YAKXZ; ReadAllowTimestampsSetting(void)
0x180030460  test    eax, eax
0x180030462  setnz   al
0x180030465  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003046c  mov     [rcx+50h], al
0x18003046f  lea     r8, [rcx+4Ch]; unsigned int *
0x180030473  lea     rdx, [rcx+48h]; unsigned int *
0x180030477  add     rcx, 40h ; '@'; struct NicSocket ***
0x18003047b  call    ?GetInitialSockets@@YAJPEAPEAPEAUNicSocket@@PEAI1@Z; GetInitialSockets(NicSocket * * *,uint *,uint *)
0x180030480  mov     ebx, eax
0x180030482  test    eax, eax
0x180030484  js      loc_180030588
0x18003048a  xor     r9d, r9d; lpName
0x18003048d  xor     r8d, r8d; bInitialState
0x180030490  lea     edx, [r9+1]; bManualReset
0x180030494  xor     ecx, ecx; lpEventAttributes
0x180030496  call    cs:__imp_CreateEventW
0x18003049d  nop     dword ptr [rax+rax+00h]
0x1800304a2  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800304a9  mov     [rcx+58h], rax
0x1800304ad  test    rax, rax
0x1800304b0  jz      loc_1800303C0
0x1800304b6  xor     r9d, r9d; lpName
0x1800304b9  xor     r8d, r8d; bInitialState
0x1800304bc  xor     edx, edx; bManualReset
0x1800304be  xor     ecx, ecx; lpEventAttributes
0x1800304c0  call    cs:__imp_CreateEventW
0x1800304c7  nop     dword ptr [rax+rax+00h]
0x1800304cc  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800304d3  mov     [rcx+60h], rax
0x1800304d7  test    rax, rax
0x1800304da  jz      loc_1800303C0
0x1800304e0  add     rcx, 88h; void **
0x1800304e7  call    ?myCreateTimerQueueTimer@@YAJPEAPEAX@Z; myCreateTimerQueueTimer(void * *)
0x1800304ec  mov     ebx, eax
0x1800304ee  test    eax, eax
0x1800304f0  js      loc_180030588
0x1800304f6  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800304fd  cmp     byte ptr [rcx+1FCh], 0
0x180030504  jz      short loc_18003056B
0x180030506  cmp     byte ptr [rcx+224h], 0
0x18003050d  jnz     short loc_18003056B
0x18003050f  add     rcx, 1E8h; void **
0x180030516  call    ?myCreateTimerQueueTimer@@YAJPEAPEAX@Z; myCreateTimerQueueTimer(void * *)
0x18003051b  mov     ebx, eax
0x18003051d  test    eax, eax
0x18003051f  js      short loc_180030588
0x180030521  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180030528  mov     eax, [rcx+208h]
0x18003052e  test    eax, eax
0x180030530  jz      short loc_18003056B
0x180030532  imul    eax, 0EA60h
0x180030538  mov     [rsp+48h+var_20], eax; unsigned int
0x18003053c  mov     [rsp+48h+var_28], 0; unsigned int
0x180030544  lea     r8, ?HandleChainingCountTimeout@@YAXPEAXE@Z; void (*)(void *, unsigned __int8)
0x18003054b  mov     rcx, [rcx+1E8h]; lpCriticalSection
0x180030552  call    ?myStartTimerQueueTimer@@YAJPEAX0P6AX0E@Z0KKK@Z; myStartTimerQueueTimer(void *,void *,void (*)(void *,uchar),void *,ulong,ulong,ulong)
0x180030557  mov     ebx, eax
0x180030559  test    eax, eax
0x18003055b  js      short loc_180030588
0x18003055d  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180030564  mov     byte ptr [rcx+20Ch], 1
0x18003056b  mov     byte ptr [rcx+32h], 0
0x18003056f  call    ?StartListeningThread@@YAJXZ; StartListeningThread(void)
0x180030574  mov     ebx, eax
0x180030576  test    eax, eax
0x180030578  js      short loc_180030588
0x18003057a  call    ?StartPeerPollingThread@@YAJXZ; StartPeerPollingThread(void)
0x18003057f  mov     ebx, eax
0x180030581  xor     eax, eax
0x180030583  test    ebx, ebx
0x180030585  cmovns  ebx, eax
0x180030588  mov     rcx, [rsp+48h+Buffer]; Buffer
0x18003058d  test    rcx, rcx
0x180030590  jz      short loc_18003059E
0x180030592  call    cs:__imp_DsRoleFreeMemory
0x180030599  nop     dword ptr [rax+rax+00h]
0x18003059e  test    ebx, ebx
0x1800305a0  jns     short loc_1800305B1
0x1800305a2  cmp     cs:?g_pnpstate@@3PEAU_NtpProvState@@EA, 0; _NtpProvState * g_pnpstate
0x1800305aa  jz      short loc_1800305B1
0x1800305ac  call    ?StopNtpProv@@YAJXZ; StopNtpProv(void)
0x1800305b1  mov     eax, ebx
0x1800305b3  mov     rbx, [rsp+48h+arg_0]
0x1800305b8  add     rsp, 40h
0x1800305bc  pop     rdi
0x1800305bd  retn
```
