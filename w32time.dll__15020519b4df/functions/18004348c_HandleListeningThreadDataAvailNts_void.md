# HandleListeningThreadDataAvailNts(void *)

- ea: `0x18004348c`
- end: `0x180043ae8`
- name: `?HandleListeningThreadDataAvailNts@@YAXPEAX@Z`
- size: `1628`
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
- `0x18001d9a0`
- `0x18002bbf8`
- `0x18002c918`
- `0x18002f768`
- `0x180035560`
- `0x18003d270`
- `0x18003dd2c`
- `0x180042658`
- `0x18004348c`
- `0x18004d928`
- `0x18006c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18004354d`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180043aba`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18004354d`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180043aba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043a02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043a02`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180043819`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180043819`
- `ntdll!RtlInitUnicodeString` at `0x1800439b5`
- `ntdll!RtlInitUnicodeString` at `0x1800439b5`
- `WS2_32!__imp_WSAGetLastError` at `0x1800436c4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800436c4`

## string_xrefs

- `0x18004356f`: `ListeningThread -- DataAvailEvent set for socket %u (`
- `0x1800436f9`: `ListeningThread -- no NTP service running at `
- `0x18004373a`: `ListeningThread: recvfrom failed with 0x%08X. Ignoring.\n`
- `0x180043798`: `ListeningThread -- Recvd %d of %u/%u bytes. Ignoring.\n`
- `0x180043a9f`: `ListeningThread -- Recvd %d of %u/%u bytes. Ignoring.\n`
- `0x1800438b6`: `ListeningThread -- response heard from `
- `0x180043993`: `ListeningThread: ignoring e_NtDigest-format request from %s as per RequireSecureTimeSyncRequests setting\n`
- `0x1800434d1`: `Failing as we are attempting to call HandleListeningThreadDataAvailNts when nts feature is not enabled.\n`

## pseudocode

```c
void __fastcall HandleListeningThreadDataAvailNts(void *a1)
{
  unsigned int v1; // esi
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned int v4; // edi
  int v5; // ebx
  int Error; // eax
  unsigned int v7; // ebx
  unsigned int v8; // r15d
  __int64 v9; // rbx
  unsigned __int64 v10; // rdx
  LARGE_INTEGER v11; // rcx
  PCWSTR v12; // r14
  char *v13; // rbx
  bool v14; // cl
  const WCHAR *v15; // rbx
  WCHAR *v16; // rdi
  unsigned int v17; // [rsp+30h] [rbp-6E8h]
  int v18; // [rsp+70h] [rbp-6A8h]
  unsigned int v19; // [rsp+74h] [rbp-6A4h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+78h] [rbp-6A0h] BYREF
  unsigned int v21; // [rsp+80h] [rbp-698h] BYREF
  __int64 v22; // [rsp+88h] [rbp-690h] BYREF
  PCWSTR SourceString; // [rsp+90h] [rbp-688h] BYREF
  char *v24; // [rsp+98h] [rbp-680h] BYREF
  struct _LIST_ENTRY v25; // [rsp+A0h] [rbp-678h] BYREF
  __int64 v26; // [rsp+B0h] [rbp-668h]
  __int64 v27; // [rsp+B8h] [rbp-660h]
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-658h] BYREF
  struct sockaddr saAddress; // [rsp+110h] [rbp-608h] BYREF
  char v30[64]; // [rsp+190h] [rbp-588h] BYREF
  char v31[1280]; // [rsp+1D0h] [rbp-548h] BYREF

  v1 = (unsigned int)a1;
  if ( !*((_BYTE *)g_pnpstate + 50) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"Failing as we are attempting to call HandleListeningThreadDataAvailNts when nts feature is not enabled.\n");
    return;
  }
  v19 = 0;
  v22 = 0;
  v25.Blink = 0;
  memset_0(&saAddress, 0, 0x80u);
  v25.Flink = 0;
  SourceString = 0;
  memset_0(v30, 0, sizeof(v30));
  PerformanceCount.LowPart = 0;
  v24 = 0;
  v21 = 0;
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
           v31,
           0x500u,
           v30,
           v17,
           &v19,
           (unsigned __int64 *)&SourceString,
           &v24,
           &v21,
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
    switch ( v19 )
    {
      case 'x':
        goto LABEL_26;
      case 'D':
        v4 = 1;
        goto LABEL_26;
      case '0':
        v4 = 0;
        goto LABEL_26;
    }
    if ( v19 == 84 || v19 - 124 <= 0x484 )
    {
      if ( *((_BYTE *)g_pnpstate + 50) )
      {
        v4 = 3;
LABEL_26:
        v8 = v21;
        if ( v21 <= PerformanceCount.LowPart )
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
          else if ( (int)HandleIncomingPacketNts(
                           v4,
                           v31,
                           v1,
                           (__int64)&saAddress,
                           *(_DWORD *)(*(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8LL * v1) + 128LL),
                           (SOCKET)v13,
                           v8,
                           (const WCHAR *)&v22,
                           (__int64 *)&v25.Blink,
                           &v25,
                           v19) >= 0 )
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
          v21 = 0;
        }
        return;
      }
      if ( !(unsigned __int8)FileLogAllowEntry(8) )
        return;
    }
    else if ( !(unsigned __int8)FileLogAllowEntry(8) )
    {
      return;
    }
    FileLogAdd(L"ListeningThread -- Recvd %d of %u/%u bytes. Ignoring.\n", v19, 48, 68);
  }
}

```

## disassembly

```asm
0x18004348c  push    rbx
0x18004348e  push    rsi
0x18004348f  push    rdi
0x180043490  push    r12
0x180043492  push    r14
0x180043494  push    r15
0x180043496  sub     rsp, 6E8h
0x18004349d  mov     rax, cs:__security_cookie
0x1800434a4  xor     rax, rsp
0x1800434a7  mov     [rsp+718h+var_48], rax
0x1800434af  mov     rsi, rcx
0x1800434b2  xor     r12d, r12d
0x1800434b5  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800434bc  cmp     [rax+32h], r12b
0x1800434c0  jnz     short loc_1800434E2
0x1800434c2  xor     ecx, ecx
0x1800434c4  call    FileLogAllowEntry
0x1800434c9  test    al, al
0x1800434cb  jz      loc_180043AC6
0x1800434d1  lea     rcx, aFailingAsWeAre; "Failing as we are attempting to call Ha"...
0x1800434d8  call    FileLogAdd
0x1800434dd  jmp     loc_180043AC6
0x1800434e2  mov     [rsp+718h+var_6A4], r12d
0x1800434e7  mov     [rsp+718h+var_690], r12
0x1800434ef  mov     [rsp+718h+var_670], r12
0x1800434f7  mov     ebx, 80h
0x1800434fc  mov     r8d, ebx; Size
0x1800434ff  xor     edx, edx; Val
0x180043501  lea     rcx, [rsp+718h+saAddress]; void *
0x180043509  call    memset_0
0x18004350e  mov     [rsp+718h+var_678], r12
0x180043516  mov     [rsp+718h+SourceString], r12
0x18004351e  xor     edx, edx; Val
0x180043520  lea     r8d, [rbx-40h]; Size
0x180043524  lea     rcx, [rsp+718h+var_588]; void *
0x18004352c  call    memset_0
0x180043531  mov     dword ptr [rsp+718h+PerformanceCount], r12d
0x180043536  mov     [rsp+718h+var_680], r12
0x18004353e  mov     [rsp+718h+var_698], r12d
0x180043546  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18004354d  call    cs:__imp__set_se_translator
0x180043554  nop     dword ptr [rax+rax+00h]
0x180043559  mov     [rsp+718h+var_660], rax
0x180043561  lea     ecx, [rbx-17h]
0x180043564  call    FileLogAllowEntry
0x180043569  test    al, al
0x18004356b  jz      short loc_1800435A6
0x18004356d  mov     edx, esi
0x18004356f  lea     rcx, aListeningthrea_7; "ListeningThread -- DataAvailEvent set f"...
0x180043576  call    FileLogAdd
0x18004357b  mov     edx, esi
0x18004357d  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180043584  mov     rcx, [rax+40h]
0x180043588  mov     rdx, [rcx+rdx*8]; struct sockaddr_storage *
0x18004358c  mov     r8d, [rdx+80h]; unsigned int
0x180043593  mov     cl, 1; bool
0x180043595  call    ?FileLogSockaddrInEx2@@YAX_NPEAUsockaddr_storage@@I@Z; FileLogSockaddrInEx2(bool,sockaddr_storage *,uint)
0x18004359a  lea     rcx, asc_180073DC8; ")\n"
0x1800435a1  call    FileLogAppend
0x1800435a6  mov     r8, rbx; Size
0x1800435a9  xor     edx, edx; Val
0x1800435ab  lea     rcx, [rsp+718h+saAddress]; void *
0x1800435b3  call    memset_0
0x1800435b8  mov     r14d, esi
0x1800435bb  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800435c2  mov     rcx, [rax+40h]
0x1800435c6  mov     rcx, [rcx+r14*8]
0x1800435ca  mov     edi, 2
0x1800435cf  cmp     di, [rcx]
0x1800435d2  jz      short loc_1800435E1
0x1800435d4  lea     eax, [rdi+15h]
0x1800435d7  cmp     ax, [rcx]
0x1800435da  jz      short loc_1800435E1
0x1800435dc  jmp     loc_180043AC6
0x1800435e1  mov     rax, [rcx+0A0h]
0x1800435e8  mov     [rsp+718h+var_6B8], rax; int (*)(unsigned __int64, struct _WSAMSG *, unsigned int *, struct _OVERLAPPED *, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *, unsigned int))
0x1800435ed  lea     rax, [rsp+718h+PerformanceCount]
0x1800435f2  mov     [rsp+718h+var_6C0], rax; unsigned int *
0x1800435f7  lea     rax, [rsp+718h+var_698]
0x1800435ff  mov     [rsp+718h+var_6C8], rax; unsigned int *
0x180043604  lea     rax, [rsp+718h+var_680]
0x18004360c  mov     [rsp+718h+var_6D0], rax; char **
0x180043611  lea     rax, [rsp+718h+SourceString]
0x180043619  mov     [rsp+718h+var_6D8], rax; unsigned __int64 *
0x18004361e  lea     rax, [rsp+718h+var_6A4]
0x180043623  mov     [rsp+718h+var_6E0], rax; unsigned int *
0x180043628  lea     rax, [rsp+718h+var_588]
0x180043630  mov     [rsp+718h+var_6F0], rax; char *
0x180043635  mov     [rsp+718h+var_6F8], 500h; unsigned int
0x18004363d  lea     r9, [rsp+718h+var_548]; char *
0x180043645  mov     r8d, [rcx+80h]; int
0x18004364c  lea     rdx, [rsp+718h+saAddress]; struct sockaddr *
0x180043654  mov     rcx, [rcx+88h]; unsigned __int64
0x18004365b  call    ?MyWSARecvMsg@@YAH_KPEAUsockaddr@@HPEADK2KPEAKPEA_KPEAPEAD33P6AH0PEAU_WSAMSG@@3PEAU_OVERLAPPED@@P6AXKK7K@Z@Z@Z; MyWSARecvMsg(unsigned __int64,sockaddr *,int,char *,ulong,char *,ulong,ulong *,unsigned __int64 *,char * *,ulong *,ulong *,int (*)(unsigned __int64,_WSAMSG *,ulong *,_OVERLAPPED *,void (*)(ulong,ulong,_OVERLAPPED *,ulong)))
0x180043660  mov     ebx, eax
0x180043662  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180043669  mov     rax, [rcx+10h]
0x18004366d  lea     rdx, [rsp+718h+var_690]
0x180043675  mov     r15d, 3
0x18004367b  mov     ecx, r15d
0x18004367e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043683  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18004368a  mov     rax, [rcx+10h]
0x18004368e  lea     rdx, [rsp+718h+var_670]
0x180043696  lea     ecx, [r15+1]
0x18004369a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004369f  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800436a6  lea     rdx, [rsp+718h+var_678]
0x1800436ae  lea     ecx, [r15+2]
0x1800436b2  mov     rax, [rax+10h]
0x1800436b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436bb  cmp     ebx, 0FFFFFFFFh
0x1800436be  jnz     loc_18004374C
0x1800436c4  call    cs:__imp_WSAGetLastError
0x1800436cb  nop     dword ptr [rax+rax+00h]
0x1800436d0  mov     ebx, eax
0x1800436d2  test    eax, eax
0x1800436d4  jle     short loc_1800436DF
0x1800436d6  movzx   ebx, ax
0x1800436d9  or      ebx, 80070000h
0x1800436df  mov     [rsp+718h+var_6A8], ebx
0x1800436e3  mov     ecx, 8
0x1800436e8  call    FileLogAllowEntry
0x1800436ed  test    al, al
0x1800436ef  jz      short loc_180043747
0x1800436f1  cmp     ebx, 80072746h
0x1800436f7  jnz     short loc_180043738
0x1800436f9  lea     rcx, aListeningthrea_5; "ListeningThread -- no NTP service runni"...
0x180043700  call    FileLogAdd
0x180043705  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18004370c  mov     rdx, [rax+40h]
0x180043710  mov     r8, [rdx+r14*8]
0x180043714  mov     r8d, [r8+80h]; unsigned int
0x18004371b  lea     rdx, [rsp+718h+saAddress]; struct sockaddr_storage *
0x180043723  mov     cl, 1; bool
0x180043725  call    ?FileLogSockaddrInEx2@@YAX_NPEAUsockaddr_storage@@I@Z; FileLogSockaddrInEx2(bool,sockaddr_storage *,uint)
0x18004372a  lea     rcx, asc_18007145C; "\n"
0x180043731  call    FileLogAppend
0x180043736  jmp     short loc_180043747
0x180043738  mov     edx, ebx
0x18004373a  lea     rcx, aListeningthrea_8; "ListeningThread: recvfrom failed with 0"...
0x180043741  call    FileLogAdd
0x180043746  nop
0x180043747  jmp     loc_180043AC6
0x18004374c  mov     eax, [rsp+718h+var_6A4]
0x180043750  cmp     eax, 78h ; 'x'
0x180043753  jz      short loc_1800437BE
0x180043755  mov     ebx, 44h ; 'D'
0x18004375a  cmp     eax, ebx
0x18004375c  jnz     short loc_180043763
0x18004375e  lea     edi, [rbx-43h]
0x180043761  jmp     short loc_1800437BE
0x180043763  mov     edi, 30h ; '0'
0x180043768  cmp     eax, edi
0x18004376a  jnz     short loc_180043771
0x18004376c  mov     edi, r12d
0x18004376f  jmp     short loc_1800437BE
0x180043771  cmp     eax, 54h ; 'T'
0x180043774  jz      short loc_1800437AA
0x180043776  add     eax, 0FFFFFF84h
0x180043779  cmp     eax, 484h
0x18004377e  jbe     short loc_1800437AA
0x180043780  mov     ecx, 8
0x180043785  call    FileLogAllowEntry
0x18004378a  test    al, al
0x18004378c  jz      short loc_1800437A5
0x18004378e  mov     r9d, ebx
0x180043791  mov     r8d, edi
0x180043794  mov     edx, [rsp+718h+var_6A4]
0x180043798  lea     rcx, aListeningthrea_4; "ListeningThread -- Recvd %d of %u/%u by"...
0x18004379f  call    FileLogAdd
0x1800437a4  nop
0x1800437a5  jmp     loc_180043AC6
0x1800437aa  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800437b1  cmp     [rax+32h], r12b
0x1800437b5  jz      loc_180043A87
0x1800437bb  mov     edi, r15d
0x1800437be  mov     r15d, [rsp+718h+var_698]
0x1800437c6  cmp     r15d, dword ptr [rsp+718h+PerformanceCount]
0x1800437cb  jbe     short loc_180043804
0x1800437cd  mov     ecx, 8
0x1800437d2  call    FileLogAllowEntry
0x1800437d7  test    al, al
0x1800437d9  jz      short loc_1800437EF
0x1800437db  mov     r8d, dword ptr [rsp+718h+PerformanceCount]
0x1800437e0  mov     edx, r15d
0x1800437e3  lea     rcx, aPacketInfoLeng; "Packet info length %d larger than ancil"...
0x1800437ea  call    FileLogAdd
0x1800437ef  mov     [rsp+718h+var_680], r12
0x1800437f7  mov     [rsp+718h+var_698], r12d
0x1800437ff  jmp     loc_180043AC6
0x180043804  mov     qword ptr [rsp+718h+PerformanceCount], r12
0x180043809  mov     rbx, r12
0x18004380c  mov     [rsp+718h+var_668], rbx
0x180043814  lea     rcx, [rsp+718h+PerformanceCount]; lpPerformanceCount
0x180043819  call    cs:__imp_QueryPerformanceCounter
0x180043820  nop     dword ptr [rax+rax+00h]
0x180043825  test    eax, eax
0x180043827  jnz     short loc_180043833
0x180043829  mov     rcx, r12
0x18004382c  mov     qword ptr [rsp+718h+PerformanceCount], rcx
0x180043831  jmp     short loc_180043838
0x180043833  mov     rcx, qword ptr [rsp+718h+PerformanceCount]
0x180043838  mov     r14, [rsp+718h+SourceString]
0x180043840  test    r14, r14
0x180043843  jz      short loc_18004385D
0x180043845  cmp     r14, rcx
0x180043848  jnb     short loc_18004385D
0x18004384a  sub     rcx, r14; unsigned __int64
0x18004384d  call    ?QPCUnitsToFileTimeUnitsWithLimits@@YA_J_K0@Z; QPCUnitsToFileTimeUnitsWithLimits(unsigned __int64,unsigned __int64)
0x180043852  mov     rbx, rax
0x180043855  mov     [rsp+718h+var_668], rax
0x18004385d  mov     ecx, 73h ; 's'
0x180043862  call    FileLogAllowEntry
0x180043867  test    al, al
0x180043869  jz      short loc_180043882
0x18004386b  mov     r8, [rsp+718h+var_690]
0x180043873  mov     rdx, rbx
0x180043876  lea     rcx, aHaPktRcvDelayI; "HA Pkt Rcv: delay:%I64u DestTimeStamp:%"...
0x18004387d  call    FileLogAdd
0x180043882  test    r14, r14
0x180043885  jnz     short loc_1800438A0
0x180043887  lea     ecx, [r14+73h]
0x18004388b  call    FileLogAllowEntry
0x180043890  test    al, al
0x180043892  jz      short loc_1800438A0
0x180043894  lea     rcx, aRxTimestampNot; "Rx timestamp not returned and may be un"...
0x18004389b  call    FileLogAdd
0x1800438a0  sub     [rsp+718h+var_690], rbx
0x1800438a8  mov     ecx, 69h ; 'i'
0x1800438ad  call    FileLogAllowEntry
0x1800438b2  test    al, al
0x1800438b4  jz      short loc_180043917
0x1800438b6  lea     rcx, aListeningthrea; "ListeningThread -- response heard from "
0x1800438bd  call    FileLogAdd
0x1800438c2  mov     r8d, esi
0x1800438c5  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800438cc  mov     rcx, [rax+40h]
0x1800438d0  mov     r8, [rcx+r8*8]
0x1800438d4  mov     r8d, [r8+80h]; unsigned int
0x1800438db  lea     rdx, [rsp+718h+saAddress]; struct sockaddr_storage *
0x1800438e3  mov     cl, 1; bool
0x1800438e5  call    ?FileLogSockaddrInEx2@@YAX_NPEAUsockaddr_storage@@I@Z; FileLogSockaddrInEx2(bool,sockaddr_storage *,uint)
0x1800438ea  lea     rcx, asc_18007C070; " <- "
0x1800438f1  call    FileLogAppend
0x1800438f6  mov     r8d, r15d; unsigned int
0x1800438f9  mov     rbx, [rsp+718h+var_680]
0x180043901  mov     rdx, rbx; char *
0x180043904  call    ?FileLogMsgAncillaryDataEx2@@YAX_NPEADI@Z; FileLogMsgAncillaryDataEx2(bool,char *,uint)
0x180043909  lea     rcx, asc_18007145C; "\n"
0x180043910  call    FileLogAppend
0x180043915  jmp     short loc_18004391F
0x180043917  mov     rbx, [rsp+718h+var_680]
0x18004391f  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180043926  cmp     edi, 1
0x180043929  jnz     loc_180043A14
0x18004392f  cmp     [rax+108h], r12b
0x180043936  jz      loc_180043A14
0x18004393c  mov     [rsp+718h+SourceString], r12
0x180043944  mov     edx, esi
0x180043946  mov     rax, [rax+40h]
0x18004394a  mov     rdx, [rax+rdx*8]
0x18004394e  lea     r8, [rsp+718h+SourceString]; unsigned __int16 **
0x180043956  mov     edx, [rdx+80h]; dwAddressLength
0x18004395c  lea     rcx, [rsp+718h+saAddress]; lpsaAddress
0x180043964  call    ?MyAddressToString@@YAJPEAUsockaddr@@IPEAPEAG@Z; MyAddressToString(sockaddr *,uint,ushort * *)
0x180043969  mov     [rsp+718h+var_6A8], eax
0x18004396d  lea     rbx, aUnknown; "<unknown>"
0x180043974  mov     rdi, [rsp+718h+SourceString]
0x18004397c  test    eax, eax
0x18004397e  cmovns  rbx, rdi
0x180043982  mov     ecx, 73h ; 's'
0x180043987  call    FileLogAllowEntry
0x18004398c  test    al, al
0x18004398e  jz      short loc_18004399F
0x180043990  mov     rdx, rbx
0x180043993  lea     rcx, aListeningthrea_0; "ListeningThread: ignoring e_NtDigest-fo"...
0x18004399a  call    FileLogAdd
0x18004399f  xorps   xmm0, xmm0
0x1800439a2  movups  xmmword ptr [rsp+718h+DestinationString.Length], xmm0
0x1800439aa  mov     rdx, rbx; SourceString
0x1800439ad  lea     rcx, [rsp+718h+DestinationString]; DestinationString
0x1800439b5  call    cs:__imp_RtlInitUnicodeString
0x1800439bc  nop     dword ptr [rax+rax+00h]
0x1800439c1  lea     rax, [rsp+718h+DestinationString]
0x1800439c9  mov     qword ptr [rsp+718h+var_6F8], rax
0x1800439ce  mov     r9, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800439d5  mov     r9d, [r9+110h]
0x1800439dc  lea     r8, aU; "u"
0x1800439e3  lea     rdx, W32TIME_EVENT_DOWNLEVELSYNCREQUESTIGNORED
0x1800439ea  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x1800439f1  call    LogThrottledEvent
0x1800439f6  mov     [rsp+718h+var_6A8], eax
0x1800439fa  test    rdi, rdi
0x1800439fd  jz      short loc_180043A0F
0x1800439ff  mov     rcx, rdi; hMem
0x180043a02  call    cs:__imp_LocalFree
0x180043a09  nop     dword ptr [rax+rax+00h]
0x180043a0e  nop
0x180043a0f  jmp     loc_180043AC6
  ... truncated ...
```
