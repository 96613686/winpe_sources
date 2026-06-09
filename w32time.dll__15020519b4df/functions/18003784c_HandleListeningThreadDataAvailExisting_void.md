# HandleListeningThreadDataAvailExisting(void *)

- ea: `0x18003784c`
- end: `0x180037e45`
- name: `?HandleListeningThreadDataAvailExisting@@YAXPEAX@Z`
- size: `1529`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180043470`

## callees

- `0x18000a818`
- `0x180018138`
- `0x180018dfc`
- `0x18001bdb0`
- `0x18001d9a0`
- `0x18002bbf8`
- `0x18002c918`
- `0x18002f768`
- `0x18003784c`
- `0x18003d270`
- `0x18003dd2c`
- `0x180042658`
- `0x18004d928`
- `0x18006c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800378fa`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180037e17`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800378fa`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180037e17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037d5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037d5f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180037b77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180037b77`
- `ntdll!RtlInitUnicodeString` at `0x180037d12`
- `ntdll!RtlInitUnicodeString` at `0x180037d12`
- `WS2_32!__imp_WSAGetLastError` at `0x180037a71`
- `WS2_32!__imp_WSAGetLastError` at `0x180037a71`

## string_xrefs

- `0x18003791c`: `ListeningThread -- DataAvailEvent set for socket %u (`
- `0x180037aa6`: `ListeningThread -- no NTP service running at `
- `0x180037ae7`: `ListeningThread: recvfrom failed with 0x%08X. Ignoring.\n`
- `0x180037dfc`: `ListeningThread -- Recvd %d of %u/%u bytes. Ignoring.\n`
- `0x180037c13`: `ListeningThread -- response heard from `
- `0x180037cf0`: `ListeningThread: ignoring e_NtDigest-format request from %s as per RequireSecureTimeSyncRequests setting\n`

## pseudocode

```c
void __fastcall HandleListeningThreadDataAvailExisting(void *a1)
{
  unsigned int v1; // edi
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned int v4; // r14d
  int v5; // ebx
  int Error; // eax
  unsigned int v7; // ebx
  unsigned int v8; // r15d
  __int64 v9; // rbx
  unsigned __int64 v10; // rdx
  LARGE_INTEGER v11; // rcx
  PCWSTR v12; // rsi
  char *v13; // rbx
  bool v14; // cl
  const WCHAR *v15; // rbx
  WCHAR *v16; // rdi
  unsigned int v17; // [rsp+30h] [rbp-268h]
  int v18; // [rsp+70h] [rbp-228h]
  LARGE_INTEGER PerformanceCount; // [rsp+78h] [rbp-220h] BYREF
  unsigned int v20; // [rsp+80h] [rbp-218h] BYREF
  unsigned int v21; // [rsp+84h] [rbp-214h] BYREF
  __int64 v22; // [rsp+88h] [rbp-210h] BYREF
  PCWSTR SourceString; // [rsp+90h] [rbp-208h] BYREF
  char *v24; // [rsp+98h] [rbp-200h] BYREF
  struct _LIST_ENTRY v25; // [rsp+A0h] [rbp-1F8h] BYREF
  __int64 v26; // [rsp+B0h] [rbp-1E8h]
  __int64 v27; // [rsp+B8h] [rbp-1E0h]
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-1D8h] BYREF
  struct sockaddr saAddress; // [rsp+110h] [rbp-188h] BYREF
  char v30[128]; // [rsp+190h] [rbp-108h] BYREF
  char v31[64]; // [rsp+210h] [rbp-88h] BYREF

  v1 = (unsigned int)a1;
  memset_0(v30, 0, 0x78u);
  v21 = 0;
  v22 = 0;
  v25.Blink = 0;
  memset_0(&saAddress, 0, 0x80u);
  v25.Flink = 0;
  SourceString = 0;
  memset_0(v31, 0, sizeof(v31));
  PerformanceCount.LowPart = 0;
  v24 = 0;
  v20 = 0;
  v27 = _set_se_translator(SeTransFunc);
  if ( (unsigned __int8)FileLogAllowEntry(105) )
  {
    FileLogAdd(L"ListeningThread -- DataAvailEvent set for socket %u (", v1);
    v2 = *(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8LL * v1);
    FileLogSockaddrInEx2(1, (struct sockaddr *)v2, *(_DWORD *)(v2 + 128));
    FileLogAppend(L")\n");
  }
  memset_0(&saAddress, 0, 0x80u);
  v3 = *(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8LL * v1);
  v4 = 2;
  if ( *(_WORD *)v3 == 2 || *(_WORD *)v3 == 23 )
  {
    v5 = MyWSARecvMsg(
           *(_QWORD *)(v3 + 136),
           &saAddress,
           *(_DWORD *)(v3 + 128),
           v30,
           0x78u,
           v31,
           v17,
           &v21,
           (unsigned __int64 *)&SourceString,
           &v24,
           &v20,
           (unsigned int *)&PerformanceCount,
           *(int (**)(unsigned __int64, struct _WSAMSG *, unsigned int *, struct _OVERLAPPED *, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *, unsigned int)))(v3 + 160));
    (*((void (__fastcall **)(__int64, __int64 *))g_pnpstate + 2))(3, &v22);
    (*((void (__fastcall **)(__int64, struct _LIST_ENTRY **))g_pnpstate + 2))(4, &v25.Blink);
    (*((void (__fastcall **)(__int64, struct _LIST_ENTRY *))g_pnpstate + 2))(5, &v25);
    if ( v5 == -1 )
    {
      Error = WSAGetLastError();
      v7 = Error;
      if ( Error > 0 )
        v7 = (unsigned __int16)Error | 0x80070000;
      if ( (unsigned __int8)FileLogAllowEntry(8) )
      {
        if ( v7 == -2147014842 )
        {
          FileLogAdd(L"ListeningThread -- no NTP service running at ");
          FileLogSockaddrInEx2(1, &saAddress, *(_DWORD *)(*(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8LL * v1) + 128LL));
          FileLogAppend(L"\n");
        }
        else
        {
          FileLogAdd(L"ListeningThread: recvfrom failed with 0x%08X. Ignoring.\n", v7);
        }
      }
      return;
    }
    switch ( v21 )
    {
      case 'x':
        goto LABEL_17;
      case 'D':
        v4 = 1;
        goto LABEL_17;
      case '0':
        v4 = 0;
LABEL_17:
        v8 = v20;
        if ( v20 <= PerformanceCount.LowPart )
        {
          PerformanceCount.QuadPart = 0;
          v9 = 0;
          v26 = 0;
          if ( QueryPerformanceCounter(&PerformanceCount) )
          {
            v11 = PerformanceCount;
          }
          else
          {
            v11.QuadPart = 0;
            PerformanceCount.QuadPart = 0;
          }
          v12 = SourceString;
          if ( SourceString && (unsigned __int64)SourceString < v11.QuadPart )
          {
            v9 = QPCUnitsToFileTimeUnitsWithLimits(v11.QuadPart - (_QWORD)SourceString, v10);
            v26 = v9;
          }
          if ( (unsigned __int8)FileLogAllowEntry(115) )
            FileLogAdd(L"HA Pkt Rcv: delay:%I64u DestTimeStamp:%I64u\n", v9, v22);
          if ( !v12 && (unsigned __int8)FileLogAllowEntry(115) )
            FileLogAdd(L"Rx timestamp not returned and may be unsupported on the current network interface.\n");
          v22 -= v9;
          if ( (unsigned __int8)FileLogAllowEntry(105) )
          {
            FileLogAdd(L"ListeningThread -- response heard from ");
            FileLogSockaddrInEx2(
              1,
              &saAddress,
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8LL * v1) + 128LL));
            FileLogAppend(L" <- ");
            v13 = v24;
            FileLogMsgAncillaryDataEx2(v14, v24, v8);
            FileLogAppend(L"\n");
          }
          else
          {
            v13 = v24;
          }
          if ( v4 == 1 && *((_BYTE *)g_pnpstate + 264) )
          {
            SourceString = 0;
            v18 = MyAddressToString(
                    &saAddress,
                    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8LL * v1) + 128LL),
                    (unsigned __int16 **)&SourceString);
            v15 = L"<unknown>";
            v16 = (WCHAR *)SourceString;
            if ( v18 >= 0 )
              v15 = SourceString;
            if ( (unsigned __int8)FileLogAllowEntry(115) )
              FileLogAdd(
                L"ListeningThread: ignoring e_NtDigest-format request from %s as per RequireSecureTimeSyncRequests setting\n",
                v15);
            DestinationString = 0;
            RtlInitUnicodeString(&DestinationString, v15);
            LogThrottledEvent(
              &_W32TimeRegistrationHandle,
              W32TIME_EVENT_DOWNLEVELSYNCREQUESTIGNORED,
              L"u",
              *((unsigned int *)g_pnpstate + 68),
              &DestinationString);
            if ( v16 )
              LocalFree(v16);
          }
          else if ( (int)HandleIncomingPacket(
                           v4,
                           (unsigned __int8 *)v30,
                           v1,
                           (__int64)&saAddress,
                           *(_DWORD *)(*(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8LL * v1) + 128LL),
                           (__int64)v13,
                           v8,
                           (const WCHAR *)&v22,
                           (__int64 *)&v25.Blink,
                           &v25) >= 0 )
          {
            _set_se_translator(v27);
          }
        }
        else
        {
          if ( (unsigned __int8)FileLogAllowEntry(8) )
            FileLogAdd(
              L"Packet info length %d larger than ancilliary data length %d. Ignoring this request\n",
              v8,
              PerformanceCount.LowPart);
          v24 = 0;
          v20 = 0;
        }
        return;
    }
    if ( (unsigned __int8)FileLogAllowEntry(8) )
      FileLogAdd(L"ListeningThread -- Recvd %d of %u/%u bytes. Ignoring.\n", v21, 48);
  }
}

```

## disassembly

```asm
0x18003784c  push    rbx
0x18003784e  push    rsi
0x18003784f  push    rdi
0x180037850  push    r12
0x180037852  push    r14
0x180037854  push    r15
0x180037856  sub     rsp, 268h
0x18003785d  mov     rax, cs:__security_cookie
0x180037864  xor     rax, rsp
0x180037867  mov     [rsp+298h+var_48], rax
0x18003786f  mov     rdi, rcx
0x180037872  mov     r15d, 78h ; 'x'
0x180037878  mov     r8d, r15d; Size
0x18003787b  xor     edx, edx; Val
0x18003787d  lea     rcx, [rsp+298h+var_108]; void *
0x180037885  call    memset_0
0x18003788a  xor     r12d, r12d
0x18003788d  mov     [rsp+298h+var_214], r12d
0x180037895  mov     [rsp+298h+var_210], r12
0x18003789d  mov     [rsp+298h+var_1F0], r12
0x1800378a5  lea     ebx, [r15+8]
0x1800378a9  mov     r8d, ebx; Size
0x1800378ac  xor     edx, edx; Val
0x1800378ae  lea     rcx, [rsp+298h+saAddress]; void *
0x1800378b6  call    memset_0
0x1800378bb  mov     [rsp+298h+var_1F8], r12
0x1800378c3  mov     [rsp+298h+SourceString], r12
0x1800378cb  xor     edx, edx; Val
0x1800378cd  lea     r8d, [r15-38h]; Size
0x1800378d1  lea     rcx, [rsp+298h+var_88]; void *
0x1800378d9  call    memset_0
0x1800378de  mov     dword ptr [rsp+298h+PerformanceCount], r12d
0x1800378e3  mov     [rsp+298h+var_200], r12
0x1800378eb  mov     [rsp+298h+var_218], r12d
0x1800378f3  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x1800378fa  call    cs:__imp__set_se_translator
0x180037901  nop     dword ptr [rax+rax+00h]
0x180037906  mov     [rsp+298h+var_1E0], rax
0x18003790e  lea     ecx, [rbx-17h]
0x180037911  call    FileLogAllowEntry
0x180037916  test    al, al
0x180037918  jz      short loc_180037953
0x18003791a  mov     edx, edi
0x18003791c  lea     rcx, aListeningthrea_7; "ListeningThread -- DataAvailEvent set f"...
0x180037923  call    FileLogAdd
0x180037928  mov     edx, edi
0x18003792a  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180037931  mov     rcx, [rax+40h]
0x180037935  mov     rdx, [rcx+rdx*8]; struct sockaddr_storage *
0x180037939  mov     r8d, [rdx+80h]; unsigned int
0x180037940  mov     cl, 1; bool
0x180037942  call    ?FileLogSockaddrInEx2@@YAX_NPEAUsockaddr_storage@@I@Z; FileLogSockaddrInEx2(bool,sockaddr_storage *,uint)
0x180037947  lea     rcx, asc_180073DC8; ")\n"
0x18003794e  call    FileLogAppend
0x180037953  mov     r8, rbx; Size
0x180037956  xor     edx, edx; Val
0x180037958  lea     rcx, [rsp+298h+saAddress]; void *
0x180037960  call    memset_0
0x180037965  mov     esi, edi
0x180037967  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003796e  mov     rcx, [rax+40h]
0x180037972  mov     rcx, [rcx+rsi*8]
0x180037976  mov     r14d, 2
0x18003797c  cmp     r14w, [rcx]
0x180037980  jz      short loc_180037990
0x180037982  lea     eax, [r14+15h]
0x180037986  cmp     ax, [rcx]
0x180037989  jz      short loc_180037990
0x18003798b  jmp     loc_180037E23
0x180037990  mov     rax, [rcx+0A0h]
0x180037997  mov     [rsp+298h+var_238], rax; int (*)(unsigned __int64, struct _WSAMSG *, unsigned int *, struct _OVERLAPPED *, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *, unsigned int))
0x18003799c  lea     rax, [rsp+298h+PerformanceCount]
0x1800379a1  mov     [rsp+298h+var_240], rax; unsigned int *
0x1800379a6  lea     rax, [rsp+298h+var_218]
0x1800379ae  mov     [rsp+298h+var_248], rax; unsigned int *
0x1800379b3  lea     rax, [rsp+298h+var_200]
0x1800379bb  mov     [rsp+298h+var_250], rax; char **
0x1800379c0  lea     rax, [rsp+298h+SourceString]
0x1800379c8  mov     [rsp+298h+var_258], rax; unsigned __int64 *
0x1800379cd  lea     rax, [rsp+298h+var_214]
0x1800379d5  mov     [rsp+298h+var_260], rax; unsigned int *
0x1800379da  lea     rax, [rsp+298h+var_88]
0x1800379e2  mov     [rsp+298h+var_270], rax; char *
0x1800379e7  mov     [rsp+298h+var_278], r15d; unsigned int
0x1800379ec  lea     r9, [rsp+298h+var_108]; char *
0x1800379f4  mov     r8d, [rcx+80h]; int
0x1800379fb  lea     rdx, [rsp+298h+saAddress]; struct sockaddr *
0x180037a03  mov     rcx, [rcx+88h]; unsigned __int64
0x180037a0a  call    ?MyWSARecvMsg@@YAH_KPEAUsockaddr@@HPEADK2KPEAKPEA_KPEAPEAD33P6AH0PEAU_WSAMSG@@3PEAU_OVERLAPPED@@P6AXKK7K@Z@Z@Z; MyWSARecvMsg(unsigned __int64,sockaddr *,int,char *,ulong,char *,ulong,ulong *,unsigned __int64 *,char * *,ulong *,ulong *,int (*)(unsigned __int64,_WSAMSG *,ulong *,_OVERLAPPED *,void (*)(ulong,ulong,_OVERLAPPED *,ulong)))
0x180037a0f  mov     ebx, eax
0x180037a11  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180037a18  mov     rax, [rcx+10h]
0x180037a1c  lea     rdx, [rsp+298h+var_210]
0x180037a24  mov     ecx, 3
0x180037a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a2e  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180037a35  mov     rax, [rcx+10h]
0x180037a39  lea     rdx, [rsp+298h+var_1F0]
0x180037a41  mov     ecx, 4
0x180037a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a4b  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180037a52  lea     rdx, [rsp+298h+var_1F8]
0x180037a5a  mov     ecx, 5
0x180037a5f  mov     rax, [rax+10h]
0x180037a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a68  cmp     ebx, 0FFFFFFFFh
0x180037a6b  jnz     loc_180037AF9
0x180037a71  call    cs:__imp_WSAGetLastError
0x180037a78  nop     dword ptr [rax+rax+00h]
0x180037a7d  mov     ebx, eax
0x180037a7f  test    eax, eax
0x180037a81  jle     short loc_180037A8C
0x180037a83  movzx   ebx, ax
0x180037a86  or      ebx, 80070000h
0x180037a8c  mov     [rsp+298h+var_228], ebx
0x180037a90  mov     ecx, 8
0x180037a95  call    FileLogAllowEntry
0x180037a9a  test    al, al
0x180037a9c  jz      short loc_180037AF4
0x180037a9e  cmp     ebx, 80072746h
0x180037aa4  jnz     short loc_180037AE5
0x180037aa6  lea     rcx, aListeningthrea_5; "ListeningThread -- no NTP service runni"...
0x180037aad  call    FileLogAdd
0x180037ab2  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180037ab9  mov     rdx, [rax+40h]
0x180037abd  mov     r8, [rdx+rsi*8]
0x180037ac1  mov     r8d, [r8+80h]; unsigned int
0x180037ac8  lea     rdx, [rsp+298h+saAddress]; struct sockaddr_storage *
0x180037ad0  mov     cl, 1; bool
0x180037ad2  call    ?FileLogSockaddrInEx2@@YAX_NPEAUsockaddr_storage@@I@Z; FileLogSockaddrInEx2(bool,sockaddr_storage *,uint)
0x180037ad7  lea     rcx, asc_18007145C; "\n"
0x180037ade  call    FileLogAppend
0x180037ae3  jmp     short loc_180037AF4
0x180037ae5  mov     edx, ebx
0x180037ae7  lea     rcx, aListeningthrea_8; "ListeningThread: recvfrom failed with 0"...
0x180037aee  call    FileLogAdd
0x180037af3  nop
0x180037af4  jmp     loc_180037E23
0x180037af9  mov     eax, [rsp+298h+var_214]
0x180037b00  cmp     eax, r15d
0x180037b03  jz      short loc_180037B1C
0x180037b05  cmp     eax, 44h ; 'D'
0x180037b08  jnz     short loc_180037B10
0x180037b0a  lea     r14d, [rax-43h]
0x180037b0e  jmp     short loc_180037B1C
0x180037b10  cmp     eax, 30h ; '0'
0x180037b13  jnz     loc_180037DDD
0x180037b19  mov     r14d, r12d
0x180037b1c  mov     r15d, [rsp+298h+var_218]
0x180037b24  cmp     r15d, dword ptr [rsp+298h+PerformanceCount]
0x180037b29  jbe     short loc_180037B62
0x180037b2b  mov     ecx, 8
0x180037b30  call    FileLogAllowEntry
0x180037b35  test    al, al
0x180037b37  jz      short loc_180037B4D
0x180037b39  mov     r8d, dword ptr [rsp+298h+PerformanceCount]
0x180037b3e  mov     edx, r15d
0x180037b41  lea     rcx, aPacketInfoLeng; "Packet info length %d larger than ancil"...
0x180037b48  call    FileLogAdd
0x180037b4d  mov     [rsp+298h+var_200], r12
0x180037b55  mov     [rsp+298h+var_218], r12d
0x180037b5d  jmp     loc_180037E23
0x180037b62  mov     qword ptr [rsp+298h+PerformanceCount], r12
0x180037b67  mov     rbx, r12
0x180037b6a  mov     [rsp+298h+var_1E8], rbx
0x180037b72  lea     rcx, [rsp+298h+PerformanceCount]; lpPerformanceCount
0x180037b77  call    cs:__imp_QueryPerformanceCounter
0x180037b7e  nop     dword ptr [rax+rax+00h]
0x180037b83  test    eax, eax
0x180037b85  jnz     short loc_180037B91
0x180037b87  mov     rcx, r12
0x180037b8a  mov     qword ptr [rsp+298h+PerformanceCount], rcx
0x180037b8f  jmp     short loc_180037B96
0x180037b91  mov     rcx, qword ptr [rsp+298h+PerformanceCount]
0x180037b96  mov     rsi, [rsp+298h+SourceString]
0x180037b9e  test    rsi, rsi
0x180037ba1  jz      short loc_180037BBB
0x180037ba3  cmp     rsi, rcx
0x180037ba6  jnb     short loc_180037BBB
0x180037ba8  sub     rcx, rsi; unsigned __int64
0x180037bab  call    ?QPCUnitsToFileTimeUnitsWithLimits@@YA_J_K0@Z; QPCUnitsToFileTimeUnitsWithLimits(unsigned __int64,unsigned __int64)
0x180037bb0  mov     rbx, rax
0x180037bb3  mov     [rsp+298h+var_1E8], rax
0x180037bbb  mov     ecx, 73h ; 's'
0x180037bc0  call    FileLogAllowEntry
0x180037bc5  test    al, al
0x180037bc7  jz      short loc_180037BE0
0x180037bc9  mov     r8, [rsp+298h+var_210]
0x180037bd1  mov     rdx, rbx
0x180037bd4  lea     rcx, aHaPktRcvDelayI; "HA Pkt Rcv: delay:%I64u DestTimeStamp:%"...
0x180037bdb  call    FileLogAdd
0x180037be0  test    rsi, rsi
0x180037be3  jnz     short loc_180037BFD
0x180037be5  lea     ecx, [rsi+73h]
0x180037be8  call    FileLogAllowEntry
0x180037bed  test    al, al
0x180037bef  jz      short loc_180037BFD
0x180037bf1  lea     rcx, aRxTimestampNot; "Rx timestamp not returned and may be un"...
0x180037bf8  call    FileLogAdd
0x180037bfd  sub     [rsp+298h+var_210], rbx
0x180037c05  mov     ecx, 69h ; 'i'
0x180037c0a  call    FileLogAllowEntry
0x180037c0f  test    al, al
0x180037c11  jz      short loc_180037C74
0x180037c13  lea     rcx, aListeningthrea; "ListeningThread -- response heard from "
0x180037c1a  call    FileLogAdd
0x180037c1f  mov     r8d, edi
0x180037c22  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180037c29  mov     rcx, [rax+40h]
0x180037c2d  mov     r8, [rcx+r8*8]
0x180037c31  mov     r8d, [r8+80h]; unsigned int
0x180037c38  lea     rdx, [rsp+298h+saAddress]; struct sockaddr_storage *
0x180037c40  mov     cl, 1; bool
0x180037c42  call    ?FileLogSockaddrInEx2@@YAX_NPEAUsockaddr_storage@@I@Z; FileLogSockaddrInEx2(bool,sockaddr_storage *,uint)
0x180037c47  lea     rcx, asc_18007C070; " <- "
0x180037c4e  call    FileLogAppend
0x180037c53  mov     r8d, r15d; unsigned int
0x180037c56  mov     rbx, [rsp+298h+var_200]
0x180037c5e  mov     rdx, rbx; char *
0x180037c61  call    ?FileLogMsgAncillaryDataEx2@@YAX_NPEADI@Z; FileLogMsgAncillaryDataEx2(bool,char *,uint)
0x180037c66  lea     rcx, asc_18007145C; "\n"
0x180037c6d  call    FileLogAppend
0x180037c72  jmp     short loc_180037C7C
0x180037c74  mov     rbx, [rsp+298h+var_200]
0x180037c7c  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180037c83  cmp     r14d, 1
0x180037c87  jnz     loc_180037D71
0x180037c8d  cmp     [rax+108h], r12b
0x180037c94  jz      loc_180037D71
0x180037c9a  mov     [rsp+298h+SourceString], r12
0x180037ca2  mov     edx, edi
0x180037ca4  mov     rax, [rax+40h]
0x180037ca8  mov     rdx, [rax+rdx*8]
0x180037cac  lea     r8, [rsp+298h+SourceString]; unsigned __int16 **
0x180037cb4  mov     edx, [rdx+80h]; dwAddressLength
0x180037cba  lea     rcx, [rsp+298h+saAddress]; lpsaAddress
0x180037cc2  call    ?MyAddressToString@@YAJPEAUsockaddr@@IPEAPEAG@Z; MyAddressToString(sockaddr *,uint,ushort * *)
0x180037cc7  mov     [rsp+298h+var_228], eax
0x180037ccb  lea     rbx, aUnknown; "<unknown>"
0x180037cd2  mov     rdi, [rsp+298h+SourceString]
0x180037cda  test    eax, eax
0x180037cdc  cmovns  rbx, rdi
0x180037ce0  lea     ecx, [r14+72h]
0x180037ce4  call    FileLogAllowEntry
0x180037ce9  test    al, al
0x180037ceb  jz      short loc_180037CFC
0x180037ced  mov     rdx, rbx
0x180037cf0  lea     rcx, aListeningthrea_0; "ListeningThread: ignoring e_NtDigest-fo"...
0x180037cf7  call    FileLogAdd
0x180037cfc  xorps   xmm0, xmm0
0x180037cff  movups  xmmword ptr [rsp+298h+DestinationString.Length], xmm0
0x180037d07  mov     rdx, rbx; SourceString
0x180037d0a  lea     rcx, [rsp+298h+DestinationString]; DestinationString
0x180037d12  call    cs:__imp_RtlInitUnicodeString
0x180037d19  nop     dword ptr [rax+rax+00h]
0x180037d1e  lea     rax, [rsp+298h+DestinationString]
0x180037d26  mov     qword ptr [rsp+298h+var_278], rax
0x180037d2b  mov     r9, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180037d32  mov     r9d, [r9+110h]
0x180037d39  lea     r8, aU; "u"
0x180037d40  lea     rdx, W32TIME_EVENT_DOWNLEVELSYNCREQUESTIGNORED
0x180037d47  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x180037d4e  call    LogThrottledEvent
0x180037d53  mov     [rsp+298h+var_228], eax
0x180037d57  test    rdi, rdi
0x180037d5a  jz      short loc_180037D6C
0x180037d5c  mov     rcx, rdi; hMem
0x180037d5f  call    cs:__imp_LocalFree
0x180037d66  nop     dword ptr [rax+rax+00h]
0x180037d6b  nop
0x180037d6c  jmp     loc_180037E23
0x180037d71  mov     edx, edi
0x180037d73  mov     rax, [rax+40h]
0x180037d77  mov     rax, [rax+rdx*8]
0x180037d7b  lea     rcx, [rsp+298h+var_1F8]
0x180037d83  mov     [rsp+298h+var_250], rcx
0x180037d88  lea     rcx, [rsp+298h+var_1F0]
0x180037d90  mov     [rsp+298h+var_258], rcx
0x180037d95  lea     rcx, [rsp+298h+var_210]
0x180037d9d  mov     [rsp+298h+var_260], rcx
0x180037da2  mov     [rsp+298h+var_268], r15d
0x180037da7  mov     [rsp+298h+var_270], rbx
0x180037dac  mov     eax, [rax+80h]
0x180037db2  mov     [rsp+298h+var_278], eax
0x180037db6  lea     r9, [rsp+298h+saAddress]
0x180037dbe  mov     r8d, edi
0x180037dc1  lea     rdx, [rsp+298h+var_108]
0x180037dc9  mov     ecx, r14d
0x180037dcc  call    ?HandleIncomingPacket@@YAJW4AuthType@@PEAEIPEAUsockaddr_storage@@IPEADKPEAUNtTimeEpoch@@PEA_JPEA_K@Z; HandleIncomingPacket(AuthType,uchar *,uint,sockaddr_storage *,uint,char *,ulong,NtTimeEpoch *,__int64 *,unsigned __int64 *)
0x180037dd1  mov     [rsp+298h+var_228], eax
0x180037dd5  test    eax, eax
0x180037dd7  jns     short loc_180037DDB
0x180037dd9  jmp     short loc_180037E23
0x180037ddb  jmp     short loc_180037E0F
0x180037ddd  mov     ecx, 8
0x180037de2  call    FileLogAllowEntry
0x180037de7  test    al, al
0x180037de9  jz      short loc_180037E09
0x180037deb  mov     r9d, 44h ; 'D'
0x180037df1  lea     r8d, [r9-14h]
  ... truncated ...
```
