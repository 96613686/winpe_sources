# RequestNetTopoChangeNotification(unsigned __int64 *)

- ea: `0x1800279b0`
- end: `0x180027e77`
- name: `?RequestNetTopoChangeNotification@@YAJPEA_K@Z`
- size: `1223`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180010748`
- `0x180039100`

## callees

- `0x18000a7e0`
- `0x180018138`
- `0x18001d9a0`
- `0x1800279b0`
- `0x18004ceac`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180027c5a`
- `ntdll!RtlReleaseResource` at `0x180027c5a`
- `ntdll!RtlAcquireResourceShared` at `0x180027c19`
- `ntdll!RtlAcquireResourceShared` at `0x180027c19`
- `WS2_32!WSAIoctl` at `0x180027a2f`
- `WS2_32!WSAIoctl` at `0x180027b19`
- `WS2_32!WSAIoctl` at `0x180027a2f`
- `WS2_32!WSAIoctl` at `0x180027b19`
- `WS2_32!WSASocketW` at `0x180027b61`
- `WS2_32!WSASocketW` at `0x180027bdc`
- `WS2_32!WSASocketW` at `0x180027b61`
- `WS2_32!WSASocketW` at `0x180027bdc`
- `WS2_32!__imp_closesocket` at `0x180027b98`
- `WS2_32!__imp_closesocket` at `0x180027b98`
- `WS2_32!__imp_WSAGetLastError` at `0x180027a40`
- `WS2_32!__imp_WSAGetLastError` at `0x180027b2a`
- `WS2_32!__imp_WSAGetLastError` at `0x180027b7a`
- `WS2_32!__imp_WSAGetLastError` at `0x180027a40`
- `WS2_32!__imp_WSAGetLastError` at `0x180027b2a`
- `WS2_32!__imp_WSAGetLastError` at `0x180027b7a`

## string_xrefs

- `0x180027d14`: `| Name:%s, Started:%1d, Input:%1d, Marked:%1d, RefCount:%d, DllName:%s\n`
- `0x180027de7`: `| Name:%s, Started:%1d, Input:%1d, Marked:%1d, RefCount:%d, DllName:%s\n`
- `0x180027cbc`: `Net topology change before remove default providers`
- `0x180027d8f`: `Net topology change after remove default providers`
- `0x180027e66`: `W32TmServiceMain: RequestNetTopoChangeNotification Failed\n`
- `0x180027c6e`: `W32TmServiceMain: RequestNetTopoChangeNotification Succeed\n`

## pseudocode

```c
__int64 __fastcall RequestNetTopoChangeNotification(unsigned __int64 *a1)
{
  SOCKET v1; // rsi
  HANDLE v2; // rbx
  int Error; // eax
  signed int v4; // ebx
  HANDLE v6; // rbx
  int v7; // eax
  char v8; // bl
  __int64 i; // rdx
  unsigned int v10; // esi
  unsigned int v11; // r14d
  unsigned int v12; // ebp
  __int64 v13; // rbx
  unsigned int v14; // esi
  unsigned int v15; // r14d
  unsigned int v16; // ebp
  __int64 v17; // rbx
  LPVOID lpvOutBuffer; // [rsp+20h] [rbp-48h]
  __int64 cbOutBuffer; // [rsp+28h] [rbp-40h]
  DWORD cbBytesReturned; // [rsp+70h] [rbp+8h] BYREF
  DWORD lpcbBytesReturned; // [rsp+78h] [rbp+10h] BYREF

  if ( a1 != &qword_1800A37B8 )
  {
    if ( a1 != &s )
      goto LABEL_40;
    v1 = s;
    v6 = qword_1800A3718;
    lpcbBytesReturned = 0;
    if ( !s )
    {
      v1 = WSASocketW(23, 2, 0, 0, 0, 1u);
      if ( v1 == -1 )
        goto LABEL_21;
    }
    *(_OWORD *)&stru_1800A37E8.Offset = 0;
    *(_OWORD *)&stru_1800A37E8.Internal = 0;
    stru_1800A37E8.hEvent = v6;
    if ( WSAIoctl(v1, 0x28000017u, 0, 0, 0, 0, &lpcbBytesReturned, &stru_1800A37E8, 0) == -1 )
    {
      Error = WSAGetLastError();
      v4 = Error;
      if ( Error )
      {
        if ( Error != 997 && Error != 10035 )
          goto LABEL_9;
      }
    }
    s = v1;
LABEL_6:
    v4 = 0;
    goto LABEL_12;
  }
  v1 = qword_1800A37B8;
  v2 = qword_1800A3710;
  cbBytesReturned = 0;
  if ( !qword_1800A37B8 )
  {
    v1 = WSASocketW(2, 2, 0, 0, 0, 1u);
    if ( v1 == -1 )
    {
LABEL_21:
      v7 = WSAGetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
LABEL_23:
      closesocket(v1);
      goto LABEL_12;
    }
  }
  *(_OWORD *)&Overlapped.Offset = 0;
  *(_OWORD *)&Overlapped.Internal = 0;
  Overlapped.hEvent = v2;
  if ( WSAIoctl(v1, 0x28000017u, 0, 0, 0, 0, &cbBytesReturned, &Overlapped, 0) != -1
    || (Error = WSAGetLastError(), (v4 = Error) == 0)
    || Error == 997
    || Error == 10035 )
  {
    qword_1800A37B8 = v1;
    goto LABEL_6;
  }
LABEL_9:
  if ( Error > 0 )
    v4 = (unsigned __int16)Error | 0x80070000;
  if ( v1 )
    goto LABEL_23;
LABEL_12:
  if ( v4 < 0 )
  {
LABEL_40:
    LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_TCP_NOT_INSTALLED, 0, 0);
    if ( (unsigned __int8)FileLogAllowEntry(121) )
    {
      v10 = 0;
      v11 = 0;
      v12 = 0;
      v13 = *(_QWORD *)qword_1800A42F0;
      FileLogAdd(L"/--TimeProvider: %s\n", L"Net topology change before remove default providers");
      for ( ; v13; v13 = *(_QWORD *)(v13 + 24) )
      {
        LODWORD(cbOutBuffer) = *(_DWORD *)(v13 + 72);
        LODWORD(lpvOutBuffer) = *(_BYTE *)(v13 + 68) != 0;
        FileLogAdd(
          L"| Name:%s, Started:%1d, Input:%1d, Marked:%1d, RefCount:%d, DllName:%s\n",
          *(_QWORD *)(v13 + 8),
          *(_BYTE *)(v13 + 18) != 0,
          *(_BYTE *)(v13 + 16) != 0,
          lpvOutBuffer,
          cbOutBuffer,
          *(_QWORD *)v13);
        ++v11;
        if ( !*(_BYTE *)(v13 + 16) || *(_BYTE *)(v13 + 68) )
        {
          if ( *(_BYTE *)(v13 + 68) == 1 )
            ++v12;
        }
        else
        {
          ++v10;
        }
      }
      FileLogAdd(L">--\n");
      FileLogAdd(L"| Total:%d, Input: %d, Marked: %d\n", v11, v10, v12);
      FileLogAdd(L"\\--\n");
    }
    RemoveDefaultProvidersFromList();
    if ( (unsigned __int8)FileLogAllowEntry(121) )
    {
      v14 = 0;
      v15 = 0;
      v16 = 0;
      v17 = *(_QWORD *)qword_1800A42F0;
      FileLogAdd(L"/--TimeProvider: %s\n", L"Net topology change after remove default providers");
      for ( ; v17; v17 = *(_QWORD *)(v17 + 24) )
      {
        LODWORD(cbOutBuffer) = *(_DWORD *)(v17 + 72);
        LODWORD(lpvOutBuffer) = *(_BYTE *)(v17 + 68) != 0;
        FileLogAdd(
          L"| Name:%s, Started:%1d, Input:%1d, Marked:%1d, RefCount:%d, DllName:%s\n",
          *(_QWORD *)(v17 + 8),
          *(_BYTE *)(v17 + 18) != 0,
          *(_BYTE *)(v17 + 16) != 0,
          lpvOutBuffer,
          cbOutBuffer,
          *(_QWORD *)v17);
        ++v15;
        if ( !*(_BYTE *)(v17 + 16) || *(_BYTE *)(v17 + 68) )
        {
          if ( *(_BYTE *)(v17 + 68) == 1 )
            ++v16;
        }
        else
        {
          ++v14;
        }
      }
      FileLogAdd(L">--\n");
      FileLogAdd(L"| Total:%d, Input: %d, Marked: %d\n", v15, v14, v16);
      FileLogAdd(L"\\--\n");
    }
    if ( (unsigned __int8)FileLogAllowEntry(67) )
      FileLogAdd(L"W32TmServiceMain: RequestNetTopoChangeNotification Failed\n");
    return 0;
  }
  if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
    && _pflstate
    && *((_BYTE *)_pflstate + 315)
    && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
  {
    v8 = 0;
    for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x43u; i = *(_QWORD *)(i + 8) )
    {
      if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x43 )
      {
        v8 = 1;
        break;
      }
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
    if ( v8 )
      FileLogAdd(L"W32TmServiceMain: RequestNetTopoChangeNotification Succeed\n");
  }
  return 0;
}

```

## disassembly

```asm
0x1800279b0  push    rbx
0x1800279b2  push    rsi
0x1800279b3  push    rdi
0x1800279b4  sub     rsp, 50h
0x1800279b8  lea     rax, qword_1800A37B8
0x1800279bf  xor     edi, edi
0x1800279c1  cmp     rcx, rax
0x1800279c4  jnz     loc_180027AA4
0x1800279ca  mov     rsi, cs:qword_1800A37B8
0x1800279d1  mov     rbx, cs:qword_1800A3710
0x1800279d8  mov     [rsp+68h+cbBytesReturned], edi
0x1800279dc  test    rsi, rsi
0x1800279df  jz      loc_180027B48
0x1800279e5  mov     [rsp+68h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x1800279ea  lea     rax, Overlapped
0x1800279f1  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x1800279f6  xorps   xmm0, xmm0
0x1800279f9  lea     rax, [rsp+68h+cbBytesReturned]
0x1800279fe  xor     r9d, r9d; cbInBuffer
0x180027a01  mov     [rsp+68h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180027a06  xor     r8d, r8d; lpvInBuffer
0x180027a09  movups  xmmword ptr cs:Overlapped.10h, xmm0
0x180027a10  mov     dword ptr [rsp+68h+cbOutBuffer], edi; cbOutBuffer
0x180027a14  mov     edx, 28000017h; dwIoControlCode
0x180027a19  mov     rcx, rsi; s
0x180027a1c  mov     [rsp+68h+lpvOutBuffer], rdi; lpvOutBuffer
0x180027a21  movups  xmmword ptr cs:Overlapped.Internal, xmm0
0x180027a28  mov     cs:Overlapped.hEvent, rbx
0x180027a2f  call    cs:__imp_WSAIoctl
0x180027a36  nop     dword ptr [rax+rax+00h]
0x180027a3b  cmp     eax, 0FFFFFFFFh
0x180027a3e  jnz     short loc_180027A52
0x180027a40  call    cs:__imp_WSAGetLastError
0x180027a47  nop     dword ptr [rax+rax+00h]
0x180027a4c  mov     ebx, eax
0x180027a4e  test    eax, eax
0x180027a50  jnz     short loc_180027A5D
0x180027a52  mov     cs:qword_1800A37B8, rsi
0x180027a59  mov     ebx, edi
0x180027a5b  jmp     short loc_180027A81
0x180027a5d  cmp     eax, 3E5h
0x180027a62  jz      short loc_180027A52
0x180027a64  cmp     eax, 2733h
0x180027a69  jz      short loc_180027A52
0x180027a6b  test    eax, eax
0x180027a6d  jle     short loc_180027A78
0x180027a6f  movzx   ebx, ax
0x180027a72  or      ebx, 80070000h
0x180027a78  test    rsi, rsi
0x180027a7b  jnz     loc_180027B95
0x180027a81  test    ebx, ebx
0x180027a83  js      loc_180027C7A
0x180027a89  xor     eax, eax
0x180027a8b  lock cmpxchg cs:?_lLoggingEnabled@@3JC, edi; long volatile _lLoggingEnabled
0x180027a93  jnz     loc_180027BF6
0x180027a99  xor     eax, eax
0x180027a9b  add     rsp, 50h
0x180027a9f  pop     rdi
0x180027aa0  pop     rsi
0x180027aa1  pop     rbx
0x180027aa2  retn
0x180027aa4  lea     rax, s
0x180027aab  cmp     rcx, rax
0x180027aae  jnz     loc_180027C7A
0x180027ab4  mov     rsi, cs:s
0x180027abb  mov     rbx, cs:qword_1800A3718
0x180027ac2  mov     [rsp+68h+arg_8], edi
0x180027ac6  test    rsi, rsi
0x180027ac9  jz      loc_180027BC0
0x180027acf  mov     [rsp+68h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x180027ad4  lea     rax, stru_1800A37E8
0x180027adb  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x180027ae0  xorps   xmm0, xmm0
0x180027ae3  lea     rax, [rsp+68h+arg_8]
0x180027ae8  xor     r9d, r9d; cbInBuffer
0x180027aeb  mov     [rsp+68h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180027af0  xor     r8d, r8d; lpvInBuffer
0x180027af3  movups  xmmword ptr cs:stru_1800A37E8.10h, xmm0
0x180027afa  mov     dword ptr [rsp+68h+cbOutBuffer], edi; cbOutBuffer
0x180027afe  mov     edx, 28000017h; dwIoControlCode
0x180027b03  mov     rcx, rsi; s
0x180027b06  mov     [rsp+68h+lpvOutBuffer], rdi; lpvOutBuffer
0x180027b0b  movups  xmmword ptr cs:stru_1800A37E8.Internal, xmm0
0x180027b12  mov     cs:stru_1800A37E8.hEvent, rbx
0x180027b19  call    cs:__imp_WSAIoctl
0x180027b20  nop     dword ptr [rax+rax+00h]
0x180027b25  cmp     eax, 0FFFFFFFFh
0x180027b28  jnz     short loc_180027B3C
0x180027b2a  call    cs:__imp_WSAGetLastError
0x180027b31  nop     dword ptr [rax+rax+00h]
0x180027b36  mov     ebx, eax
0x180027b38  test    eax, eax
0x180027b3a  jnz     short loc_180027BA9
0x180027b3c  mov     cs:s, rsi
0x180027b43  jmp     loc_180027A59
0x180027b48  mov     edx, 2; type
0x180027b4d  mov     dword ptr [rsp+68h+cbOutBuffer], 1; dwFlags
0x180027b55  mov     ecx, edx; af
0x180027b57  mov     dword ptr [rsp+68h+lpvOutBuffer], edi; g
0x180027b5b  xor     r9d, r9d; lpProtocolInfo
0x180027b5e  xor     r8d, r8d; protocol
0x180027b61  call    cs:__imp_WSASocketW
0x180027b68  nop     dword ptr [rax+rax+00h]
0x180027b6d  mov     rsi, rax
0x180027b70  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027b74  jnz     loc_1800279E5
0x180027b7a  call    cs:__imp_WSAGetLastError
0x180027b81  nop     dword ptr [rax+rax+00h]
0x180027b86  mov     ebx, eax
0x180027b88  test    eax, eax
0x180027b8a  jle     short loc_180027B95
0x180027b8c  movzx   ebx, ax
0x180027b8f  or      ebx, 80070000h
0x180027b95  mov     rcx, rsi; s
0x180027b98  call    cs:__imp_closesocket
0x180027b9f  nop     dword ptr [rax+rax+00h]
0x180027ba4  jmp     loc_180027A81
0x180027ba9  cmp     eax, 3E5h
0x180027bae  jz      short loc_180027B3C
0x180027bb0  cmp     eax, 2733h
0x180027bb5  jnz     loc_180027A6B
0x180027bbb  jmp     loc_180027B3C
0x180027bc0  mov     dword ptr [rsp+68h+cbOutBuffer], 1; dwFlags
0x180027bc8  xor     r9d, r9d; lpProtocolInfo
0x180027bcb  xor     r8d, r8d; protocol
0x180027bce  mov     dword ptr [rsp+68h+lpvOutBuffer], edi; g
0x180027bd2  mov     edx, 2; type
0x180027bd7  mov     ecx, 17h; af
0x180027bdc  call    cs:__imp_WSASocketW
0x180027be3  nop     dword ptr [rax+rax+00h]
0x180027be8  mov     rsi, rax
0x180027beb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027bef  jz      short loc_180027B7A
0x180027bf1  jmp     loc_180027ACF
0x180027bf6  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180027bfd  test    rcx, rcx
0x180027c00  jz      loc_180027A99
0x180027c06  cmp     byte ptr [rcx+13Bh], 0
0x180027c0d  jz      loc_180027A99
0x180027c13  add     rcx, 50h ; 'P'; Resource
0x180027c17  mov     dl, 1; Wait
0x180027c19  call    cs:__imp_RtlAcquireResourceShared
0x180027c20  nop     dword ptr [rax+rax+00h]
0x180027c25  test    al, al
0x180027c27  jz      loc_180027A99
0x180027c2d  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180027c34  xor     bl, bl
0x180027c36  mov     rdx, [r8+18h]
0x180027c3a  test    rdx, rdx
0x180027c3d  jz      short loc_180027C56
0x180027c3f  mov     ecx, [rdx]
0x180027c41  cmp     ecx, 43h ; 'C'
0x180027c44  ja      short loc_180027C56
0x180027c46  add     ecx, [rdx+4]
0x180027c49  cmp     ecx, 43h ; 'C'
0x180027c4c  ja      short loc_180027C54
0x180027c4e  mov     rdx, [rdx+8]
0x180027c52  jmp     short loc_180027C3A
0x180027c54  mov     bl, 1
0x180027c56  lea     rcx, [r8+50h]; Resource
0x180027c5a  call    cs:__imp_RtlReleaseResource
0x180027c61  nop     dword ptr [rax+rax+00h]
0x180027c66  test    bl, bl
0x180027c68  jz      loc_180027A99
0x180027c6e  lea     rcx, aW32tmservicema_8; "W32TmServiceMain: RequestNetTopoChangeN"...
0x180027c75  jmp     loc_180027E6D
0x180027c7a  mov     [rsp+68h+arg_10], rbp
0x180027c82  lea     rdx, W32TIME_EVENT_TCP_NOT_INSTALLED
0x180027c89  xor     r9d, r9d
0x180027c8c  mov     [rsp+68h+arg_18], r14
0x180027c94  xor     r8d, r8d
0x180027c97  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x180027c9e  call    LogEvent
0x180027ca3  mov     ecx, 79h ; 'y'
0x180027ca8  call    FileLogAllowEntry
0x180027cad  test    al, al
0x180027caf  jz      loc_180027D71
0x180027cb5  mov     rax, cs:qword_1800A42F0
0x180027cbc  lea     rdx, aNetTopologyCha; "Net topology change before remove defau"...
0x180027cc3  lea     rcx, aTimeproviderS; "/--TimeProvider: %s\n"
0x180027cca  mov     esi, edi
0x180027ccc  mov     r14d, edi
0x180027ccf  mov     ebp, edi
0x180027cd1  mov     rbx, [rax]
0x180027cd4  call    FileLogAdd
0x180027cd9  test    rbx, rbx
0x180027cdc  jz      short loc_180027D44
0x180027cde  cmp     byte ptr [rbx+44h], 0
0x180027ce2  mov     ecx, edi
0x180027ce4  mov     rax, [rbx]
0x180027ce7  mov     r9d, edi
0x180027cea  mov     rdx, [rbx+8]
0x180027cee  setnz   cl
0x180027cf1  cmp     byte ptr [rbx+10h], 0
0x180027cf5  mov     r8d, edi
0x180027cf8  mov     [rsp+68h+lpcbBytesReturned], rax
0x180027cfd  mov     eax, [rbx+48h]
0x180027d00  setnz   r9b
0x180027d04  cmp     byte ptr [rbx+12h], 0
0x180027d08  mov     dword ptr [rsp+68h+cbOutBuffer], eax
0x180027d0c  mov     dword ptr [rsp+68h+lpvOutBuffer], ecx
0x180027d10  setnz   r8b
0x180027d14  lea     rcx, aNameSStarted1d; "| Name:%s, Started:%1d, Input:%1d, Mark"...
0x180027d1b  call    FileLogAdd
0x180027d20  inc     r14d
0x180027d23  cmp     byte ptr [rbx+10h], 0
0x180027d27  jz      short loc_180027D33
0x180027d29  cmp     byte ptr [rbx+44h], 0
0x180027d2d  jnz     short loc_180027D33
0x180027d2f  inc     esi
0x180027d31  jmp     short loc_180027D3B
0x180027d33  cmp     byte ptr [rbx+44h], 1
0x180027d37  jnz     short loc_180027D3B
0x180027d39  inc     ebp
0x180027d3b  mov     rbx, [rbx+18h]
0x180027d3f  test    rbx, rbx
0x180027d42  jnz     short loc_180027CDE
0x180027d44  lea     rcx, asc_18007ED80; ">--\n"
0x180027d4b  call    FileLogAdd
0x180027d50  mov     r9d, ebp
0x180027d53  lea     rcx, aTotalDInputDMa; "| Total:%d, Input: %d, Marked: %d\n"
0x180027d5a  mov     r8d, esi
0x180027d5d  mov     edx, r14d
0x180027d60  call    FileLogAdd
0x180027d65  lea     rcx, asc_18007EDD8; "\\--\n"
0x180027d6c  call    FileLogAdd
0x180027d71  call    ?RemoveDefaultProvidersFromList@@YAJXZ; RemoveDefaultProvidersFromList(void)
0x180027d76  mov     ecx, 79h ; 'y'
0x180027d7b  call    FileLogAllowEntry
0x180027d80  test    al, al
0x180027d82  jz      loc_180027E44
0x180027d88  mov     rax, cs:qword_1800A42F0
0x180027d8f  lea     rdx, aNetTopologyCha_0; "Net topology change after remove defaul"...
0x180027d96  lea     rcx, aTimeproviderS; "/--TimeProvider: %s\n"
0x180027d9d  mov     esi, edi
0x180027d9f  mov     r14d, edi
0x180027da2  mov     ebp, edi
0x180027da4  mov     rbx, [rax]
0x180027da7  call    FileLogAdd
0x180027dac  test    rbx, rbx
0x180027daf  jz      short loc_180027E17
0x180027db1  cmp     byte ptr [rbx+44h], 0
0x180027db5  mov     ecx, edi
0x180027db7  mov     rax, [rbx]
0x180027dba  mov     r9d, edi
0x180027dbd  mov     rdx, [rbx+8]
0x180027dc1  setnz   cl
0x180027dc4  cmp     byte ptr [rbx+10h], 0
0x180027dc8  mov     r8d, edi
0x180027dcb  mov     [rsp+68h+lpcbBytesReturned], rax
0x180027dd0  mov     eax, [rbx+48h]
0x180027dd3  setnz   r9b
0x180027dd7  cmp     byte ptr [rbx+12h], 0
0x180027ddb  mov     dword ptr [rsp+68h+cbOutBuffer], eax
0x180027ddf  mov     dword ptr [rsp+68h+lpvOutBuffer], ecx
0x180027de3  setnz   r8b
0x180027de7  lea     rcx, aNameSStarted1d; "| Name:%s, Started:%1d, Input:%1d, Mark"...
0x180027dee  call    FileLogAdd
0x180027df3  inc     r14d
0x180027df6  cmp     byte ptr [rbx+10h], 0
0x180027dfa  jz      short loc_180027E06
0x180027dfc  cmp     byte ptr [rbx+44h], 0
0x180027e00  jnz     short loc_180027E06
0x180027e02  inc     esi
0x180027e04  jmp     short loc_180027E0E
0x180027e06  cmp     byte ptr [rbx+44h], 1
0x180027e0a  jnz     short loc_180027E0E
0x180027e0c  inc     ebp
0x180027e0e  mov     rbx, [rbx+18h]
0x180027e12  test    rbx, rbx
0x180027e15  jnz     short loc_180027DB1
0x180027e17  lea     rcx, asc_18007ED80; ">--\n"
0x180027e1e  call    FileLogAdd
0x180027e23  mov     r9d, ebp
0x180027e26  lea     rcx, aTotalDInputDMa; "| Total:%d, Input: %d, Marked: %d\n"
0x180027e2d  mov     r8d, esi
0x180027e30  mov     edx, r14d
0x180027e33  call    FileLogAdd
0x180027e38  lea     rcx, asc_18007EDD8; "\\--\n"
0x180027e3f  call    FileLogAdd
0x180027e44  mov     ecx, 43h ; 'C'
0x180027e49  call    FileLogAllowEntry
0x180027e4e  mov     r14, [rsp+68h+arg_18]
0x180027e56  mov     rbp, [rsp+68h+arg_10]
0x180027e5e  test    al, al
0x180027e60  jz      loc_180027A99
0x180027e66  lea     rcx, aW32tmservicema_9; "W32TmServiceMain: RequestNetTopoChangeN"...
0x180027e6d  call    FileLogAdd
0x180027e72  jmp     loc_180027A99
```
