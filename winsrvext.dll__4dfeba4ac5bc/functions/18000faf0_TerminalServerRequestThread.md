# TerminalServerRequestThread

- ea: `0x18000faf0`
- end: `0x18000fe8c`
- name: `TerminalServerRequestThread`
- size: `924`
- prototype: `void __fastcall(HANDLE Handle)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000faf0`
- `0x1800138c5`
- `0x180014010`

## import_xrefs

- `ntdll!NtAlpcConnectPort` at `0x18000fc75`
- `ntdll!NtAlpcConnectPort` at `0x18000fc75`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000fcce`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000fe19`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000fcce`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000fe19`
- `ntdll!NtWaitForSingleObject` at `0x18000fbb4`
- `ntdll!NtWaitForSingleObject` at `0x18000fbb4`
- `ntdll!RtlExitUserThread` at `0x18000fb73`
- `ntdll!RtlExitUserThread` at `0x18000fe69`
- `ntdll!RtlExitUserThread` at `0x18000fe7f`
- `ntdll!RtlExitUserThread` at `0x18000fb73`
- `ntdll!RtlExitUserThread` at `0x18000fe69`
- `ntdll!RtlExitUserThread` at `0x18000fe7f`
- `ntdll!RtlInitUnicodeString` at `0x18000fbcb`
- `ntdll!RtlInitUnicodeString` at `0x18000fbcb`
- `ntdll!NtClose` at `0x18000fe45`
- `ntdll!NtClose` at `0x18000fe5b`
- `ntdll!NtClose` at `0x18000fe45`
- `ntdll!NtClose` at `0x18000fe5b`
- `win32u!NtUserSetInformationThread` at `0x18000fd6d`
- `win32u!NtUserSetInformationThread` at `0x18000fdb8`
- `win32u!NtUserSetInformationThread` at `0x18000fd6d`
- `win32u!NtUserSetInformationThread` at `0x18000fdb8`

## pseudocode

```c
void __fastcall TerminalServerRequestThread(HANDLE Handle)
{
  NTSTATUS v2; // eax
  __int64 v3; // rsi
  BOOL v4; // ebx
  NTSTATUS v5; // edi
  int v6; // ecx
  int v7; // eax
  __int64 v8; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v9; // [rsp+68h] [rbp-98h] BYREF
  __int128 v10; // [rsp+78h] [rbp-88h]
  __int128 v11; // [rsp+88h] [rbp-78h]
  __int64 v12; // [rsp+98h] [rbp-68h]
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v14; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v15; // [rsp+C0h] [rbp-40h]
  _BYTE v16[8]; // [rsp+D0h] [rbp-30h] BYREF
  int v17; // [rsp+D8h] [rbp-28h]
  __int16 v18; // [rsp+DCh] [rbp-24h]
  __int64 v19; // [rsp+E0h] [rbp-20h]
  __int64 v20; // [rsp+F0h] [rbp-10h]

  DestinationString = 0;
  memset_0(v16, 0, 0x48u);
  v12 = 0;
  v9 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  if ( _InterlockedIncrement(&gNumTerminalServerRequestThreads) > 1 )
  {
    _InterlockedDecrement(&gNumTerminalServerRequestThreads);
    RtlExitUserThread(-1073740004);
    __debugbreak();
  }
  while ( 1 )
  {
LABEL_3:
    if ( gSessionId == gServiceSessionId )
      g_bInitialConnected = 1;
    NtWaitForSingleObject(Handle, 0, 0);
    RtlInitUnicodeString(&DestinationString, L"\\SmSsWinStationApiPort");
    memset_0(v16, 0, 0x48u);
    v12 = 0;
    v17 = 2;
    v18 = 257;
    *(_QWORD *)&v11 = 0;
    v19 = 16496;
    v20 = 527872;
    v10 = 0;
    v9 = 0xA00380010uLL;
    *((_QWORD *)&v11 + 1) = 1;
    v8 = 56;
    v2 = NtAlpcConnectPort(&WinStationApiPort, &DestinationString, 0, v16, 0x20000, 0, &v9, &v8, 0, 0, 0);
    if ( v2 < 0 )
      break;
    memset_0(&gApiMsg, 0, 0x4070u);
    gApiMsg = 1081098312;
    dword_18001DAAC = 0;
    if ( (int)NtAlpcSendWaitReceivePort(WinStationApiPort, 0x20000, &gApiMsg, 0, &gApiMsg, 0, 0, 0) >= 0 )
    {
      while ( 1 )
      {
        if ( dword_18001DAAC < 27
          && (v3 = dword_18001DAAC,
              xmmword_18001DA88 = (__int128)NtCurrentTeb()->ClientId,
              Win32WinStationDispatch[dword_18001DAAC]) )
        {
          v15 = 0;
          v4 = 0;
          v5 = 0;
          v14 = 0;
          if ( (unsigned int)dword_18001DAAC <= 0x1A && (v6 = 67240064, _bittest(&v6, dword_18001DAAC))
            || dword_18001DAAC == 4 && !byte_18001DAB8 && !g_bInitialConnected
            || (v7 = NtUserSetInformationThread(-2, 7, &v14), v5 = v7, v4 = v7 >= 0, !v7) )
          {
            v7 = ((__int64 (__fastcall *)(__int64 *))Win32WinStationDispatch[v3])(&gApiMsg);
          }
          dword_18001DAB4 = v7;
          if ( v4 )
            NtUserSetInformationThread(-2, 9, &v14);
          if ( dword_18001DAAC == 7 )
          {
            _InterlockedDecrement(&gNumTerminalServerRequestThreads);
            if ( WinStationApiPort )
            {
              NtClose(WinStationApiPort);
              WinStationApiPort = 0;
            }
            NtClose(Handle);
            RtlExitUserThread(v5);
            __debugbreak();
            goto LABEL_26;
          }
        }
        else
        {
          dword_18001DAB4 = -1073741822;
        }
        gApiMsg = 1081098312;
        dword_18001DAAC = 0;
        if ( (int)NtAlpcSendWaitReceivePort(WinStationApiPort, 0x20000, &gApiMsg, 0, &gApiMsg, 0, 0, 0) < 0 )
          goto LABEL_3;
      }
    }
  }
LABEL_26:
  _InterlockedDecrement(&gNumTerminalServerRequestThreads);
  RtlExitUserThread(v2);
  __debugbreak();
  JUMPOUT(0x18000FE8CLL);
}

```

## disassembly

```asm
0x18000faf0  mov     [rsp-8+arg_8], rbx
0x18000faf5  mov     [rsp-8+arg_10], rsi
0x18000fafa  push    rbp
0x18000fafb  push    rdi
0x18000fafc  push    r13
0x18000fafe  push    r14
0x18000fb00  push    r15
0x18000fb02  lea     rbp, [rsp-30h]
0x18000fb07  sub     rsp, 130h
0x18000fb0e  mov     rax, cs:__security_cookie
0x18000fb15  xor     rax, rsp
0x18000fb18  mov     [rbp+50h+var_30], rax
0x18000fb1c  xor     edx, edx; Val
0x18000fb1e  mov     r14, rcx
0x18000fb21  xorps   xmm0, xmm0
0x18000fb24  lea     rcx, [rbp+50h+var_80]; void *
0x18000fb28  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x18000fb2c  lea     r8d, [rdx+48h]; Size
0x18000fb30  call    memset_0
0x18000fb35  xor     eax, eax
0x18000fb37  xorps   xmm0, xmm0
0x18000fb3a  xor     r15d, r15d
0x18000fb3d  mov     [rbp+50h+var_B8], rax
0x18000fb41  movups  [rsp+150h+var_E8], xmm0
0x18000fb46  mov     [rsp+150h+var_F0], r15
0x18000fb4b  movups  [rsp+150h+var_D8], xmm0
0x18000fb50  lea     eax, [r15+1]
0x18000fb54  movups  [rbp+50h+var_C8], xmm0
0x18000fb58  lock xadd cs:gNumTerminalServerRequestThreads, eax
0x18000fb60  inc     eax
0x18000fb62  cmp     eax, 1
0x18000fb65  jle     short loc_18000FB80
0x18000fb67  lock dec cs:gNumTerminalServerRequestThreads
0x18000fb6e  mov     ecx, 0C000071Ch; Status
0x18000fb73  call    cs:__imp_RtlExitUserThread
0x18000fb7a  nop     dword ptr [rax+rax+00h]
0x18000fb7f  int     3; Trap to Debugger
0x18000fb80  mov     ebx, 4070h
0x18000fb85  lea     r13, gApiMsg
0x18000fb8c  lea     edi, [rbx-28h]
0x18000fb8f  mov     esi, 38h ; '8'
0x18000fb94  mov     eax, cs:gServiceSessionId
0x18000fb9a  cmp     cs:gSessionId, eax
0x18000fba0  jnz     short loc_18000FBAC
0x18000fba2  mov     cs:g_bInitialConnected, 1
0x18000fbac  xor     r8d, r8d; Timeout
0x18000fbaf  xor     edx, edx; Alertable
0x18000fbb1  mov     rcx, r14; Handle
0x18000fbb4  call    cs:__imp_NtWaitForSingleObject
0x18000fbbb  nop     dword ptr [rax+rax+00h]
0x18000fbc0  lea     rdx, aSmsswinstation; "\\SmSsWinStationApiPort"
0x18000fbc7  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x18000fbcb  call    cs:__imp_RtlInitUnicodeString
0x18000fbd2  nop     dword ptr [rax+rax+00h]
0x18000fbd7  xor     edx, edx; Val
0x18000fbd9  lea     rcx, [rbp+50h+var_80]; void *
0x18000fbdd  lea     r8d, [rdx+48h]; Size
0x18000fbe1  call    memset_0
0x18000fbe6  mov     [rsp+150h+var_100], r15
0x18000fbeb  lea     r9, [rbp+50h+var_80]
0x18000fbef  mov     [rsp+150h+var_108], r15
0x18000fbf4  lea     rdx, [rbp+50h+DestinationString]
0x18000fbf8  xor     eax, eax
0x18000fbfa  mov     [rsp+150h+var_110], r15
0x18000fbff  xorps   xmm0, xmm0
0x18000fc02  mov     [rbp+50h+var_B8], rax
0x18000fc06  movups  [rsp+150h+var_E8], xmm0
0x18000fc0b  lea     rax, [rsp+150h+var_F0]
0x18000fc10  mov     [rbp+50h+var_78], 2
0x18000fc17  mov     [rsp+150h+var_118], rax
0x18000fc1c  lea     rcx, WinStationApiPort
0x18000fc23  lea     rax, [rsp+150h+var_E8]
0x18000fc28  mov     [rbp+50h+var_74], 101h
0x18000fc2e  mov     [rsp+150h+var_120], rax
0x18000fc33  xor     r8d, r8d
0x18000fc36  movups  [rbp+50h+var_C8], xmm0
0x18000fc3a  mov     [rsp+150h+var_128], r15
0x18000fc3f  mov     dword ptr [rsp+150h+var_130], 20000h
0x18000fc47  mov     [rbp+50h+var_70], rbx
0x18000fc4b  mov     [rbp+50h+var_60], 80E00h
0x18000fc53  movups  [rsp+150h+var_D8], xmm0
0x18000fc58  mov     dword ptr [rsp+150h+var_E8], 380010h
0x18000fc60  mov     dword ptr [rsp+150h+var_E8+4], 0Ah
0x18000fc68  mov     qword ptr [rbp+50h+var_C8+8], 1
0x18000fc70  mov     [rsp+150h+var_F0], rsi
0x18000fc75  call    cs:__imp_NtAlpcConnectPort
0x18000fc7c  nop     dword ptr [rax+rax+00h]
0x18000fc81  test    eax, eax
0x18000fc83  js      loc_18000FE76
0x18000fc89  mov     r8, rbx; Size
0x18000fc8c  xor     edx, edx; Val
0x18000fc8e  mov     rcx, r13; void *
0x18000fc91  call    memset_0
0x18000fc96  mov     rcx, cs:WinStationApiPort
0x18000fc9d  xor     r9d, r9d
0x18000fca0  mov     [rsp+150h+var_118], r15
0x18000fca5  mov     r8, r13
0x18000fca8  mov     [rsp+150h+var_120], r15
0x18000fcad  mov     edx, 20000h
0x18000fcb2  mov     [rsp+150h+var_128], r15
0x18000fcb7  mov     [rsp+150h+var_130], r13
0x18000fcbc  mov     cs:gApiMsg, 40704048h
0x18000fcc7  mov     cs:dword_18001DAAC, r15d
0x18000fcce  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18000fcd5  nop     dword ptr [rax+rax+00h]
0x18000fcda  test    eax, eax
0x18000fcdc  js      loc_18000FB94
0x18000fce2  cmp     cs:dword_18001DAAC, 1Bh
0x18000fce9  jge     loc_18000FDD7
0x18000fcef  mov     rax, gs:30h
0x18000fcf8  lea     rcx, Win32WinStationDispatch
0x18000fcff  movups  xmm0, xmmword ptr [rax+40h]
0x18000fd03  movsxd  rax, cs:dword_18001DAAC
0x18000fd0a  mov     rsi, rax
0x18000fd0d  movdqu  cs:xmmword_18001DA88, xmm0
0x18000fd15  cmp     [rcx+rax*8], r15
0x18000fd19  jz      loc_18000FDD7
0x18000fd1f  xor     ecx, ecx
0x18000fd21  xorps   xmm0, xmm0
0x18000fd24  mov     [rbp+50h+var_90], rcx
0x18000fd28  mov     ebx, r15d
0x18000fd2b  mov     edi, r15d
0x18000fd2e  movups  [rbp+50h+var_A0], xmm0
0x18000fd32  cmp     eax, 1Ah
0x18000fd35  ja      short loc_18000FD41
0x18000fd37  mov     ecx, 4020080h
0x18000fd3c  bt      ecx, eax
0x18000fd3f  jb      short loc_18000FD86
0x18000fd41  cmp     eax, 4
0x18000fd44  jnz     short loc_18000FD58
0x18000fd46  cmp     cs:byte_18001DAB8, r15b
0x18000fd4d  jnz     short loc_18000FD58
0x18000fd4f  cmp     cs:g_bInitialConnected, r15d
0x18000fd56  jz      short loc_18000FD86
0x18000fd58  mov     r9d, 18h
0x18000fd5e  lea     r8, [rbp+50h+var_A0]
0x18000fd62  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x18000fd69  lea     edx, [r9-11h]
0x18000fd6d  call    cs:__imp_NtUserSetInformationThread
0x18000fd74  nop     dword ptr [rax+rax+00h]
0x18000fd79  mov     ebx, eax
0x18000fd7b  mov     edi, eax
0x18000fd7d  not     ebx
0x18000fd7f  shr     ebx, 1Fh
0x18000fd82  test    eax, eax
0x18000fd84  jnz     short loc_18000FD99
0x18000fd86  lea     rax, Win32WinStationDispatch
0x18000fd8d  mov     rcx, r13
0x18000fd90  mov     rax, (Win32WinStationDispatch - 18001D000h)[rax+rsi*8]
0x18000fd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd99  mov     cs:dword_18001DAB4, eax
0x18000fd9f  test    ebx, ebx
0x18000fda1  jz      short loc_18000FDC4
0x18000fda3  mov     r9d, 18h
0x18000fda9  lea     r8, [rbp+50h+var_A0]
0x18000fdad  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x18000fdb4  lea     edx, [r9-0Fh]
0x18000fdb8  call    cs:__imp_NtUserSetInformationThread
0x18000fdbf  nop     dword ptr [rax+rax+00h]
0x18000fdc4  cmp     cs:dword_18001DAAC, 7
0x18000fdcb  jz      short loc_18000FE32
0x18000fdcd  mov     ebx, 4070h
0x18000fdd2  lea     edi, [rbx-28h]
0x18000fdd5  jmp     short loc_18000FDE1
0x18000fdd7  mov     cs:dword_18001DAB4, 0C0000002h
0x18000fde1  mov     rcx, cs:WinStationApiPort
0x18000fde8  xor     r9d, r9d
0x18000fdeb  mov     [rsp+150h+var_118], r15
0x18000fdf0  mov     r8, r13
0x18000fdf3  mov     [rsp+150h+var_120], r15
0x18000fdf8  mov     edx, 20000h
0x18000fdfd  mov     [rsp+150h+var_128], r15
0x18000fe02  mov     [rsp+150h+var_130], r13
0x18000fe07  mov     cs:gApiMsg, 40704048h
0x18000fe12  mov     cs:dword_18001DAAC, r15d
0x18000fe19  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18000fe20  nop     dword ptr [rax+rax+00h]
0x18000fe25  test    eax, eax
0x18000fe27  jns     loc_18000FCE2
0x18000fe2d  jmp     loc_18000FB8F
0x18000fe32  lock dec cs:gNumTerminalServerRequestThreads
0x18000fe39  mov     rcx, cs:WinStationApiPort; Handle
0x18000fe40  test    rcx, rcx
0x18000fe43  jz      short loc_18000FE58
0x18000fe45  call    cs:__imp_NtClose
0x18000fe4c  nop     dword ptr [rax+rax+00h]
0x18000fe51  mov     cs:WinStationApiPort, r15
0x18000fe58  mov     rcx, r14; Handle
0x18000fe5b  call    cs:__imp_NtClose
0x18000fe62  nop     dword ptr [rax+rax+00h]
0x18000fe67  mov     ecx, edi; Status
0x18000fe69  call    cs:__imp_RtlExitUserThread
0x18000fe70  nop     dword ptr [rax+rax+00h]
0x18000fe75  int     3; Trap to Debugger
0x18000fe76  lock dec cs:gNumTerminalServerRequestThreads
0x18000fe7d  mov     ecx, eax; Status
0x18000fe7f  call    cs:__imp_RtlExitUserThread
0x18000fe86  nop     dword ptr [rax+rax+00h]
0x18000fe8b  int     3; Trap to Debugger
```
