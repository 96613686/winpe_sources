# CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::ProcessSendQueue(void)

- ea: `0x180008404`
- end: `0x180008690`
- name: `?ProcessSendQueue@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@AEAAKXZ`
- size: `652`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007e80`

## callees

- `0x180008110`
- `0x180008404`
- `0x1800095ac`
- `0x18000bd5c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000845f`
- `KERNEL32!EnterCriticalSection` at `0x1800084af`
- `KERNEL32!EnterCriticalSection` at `0x1800084be`
- `KERNEL32!EnterCriticalSection` at `0x18000845f`
- `KERNEL32!EnterCriticalSection` at `0x1800084af`
- `KERNEL32!EnterCriticalSection` at `0x1800084be`
- `KERNEL32!LeaveCriticalSection` at `0x180008475`
- `KERNEL32!LeaveCriticalSection` at `0x1800084d4`
- `KERNEL32!LeaveCriticalSection` at `0x180008523`
- `KERNEL32!LeaveCriticalSection` at `0x180008475`
- `KERNEL32!LeaveCriticalSection` at `0x1800084d4`
- `KERNEL32!LeaveCriticalSection` at `0x180008523`
- `KERNEL32!SetEvent` at `0x18000862e`
- `KERNEL32!SetEvent` at `0x18000862e`
- `WS2_32!WSASendTo` at `0x1800085a3`
- `WS2_32!WSASendTo` at `0x1800085a3`
- `WS2_32!__imp_WSAGetLastError` at `0x1800085bc`
- `WS2_32!__imp_WSAGetLastError` at `0x1800085d3`
- `WS2_32!__imp_WSAGetLastError` at `0x1800085bc`
- `WS2_32!__imp_WSAGetLastError` at `0x1800085d3`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x18000860b`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x18000860b`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000863d`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000863d`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::ProcessSendQueue(__int64 a1)
{
  unsigned int v1; // esi
  unsigned int v3; // eax
  __int64 v4; // rdx
  struct _RTL_CRITICAL_SECTION *v5; // r14
  __int64 v6; // rbx
  int v7; // r15d
  __int64 lpOverlapped; // rbp
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdx
  int v12; // eax
  unsigned int Error; // eax
  __int64 v14; // rdx
  unsigned int Requests; // eax
  __int64 v16; // rdx
  struct _WSABUF Buffers; // [rsp+50h] [rbp-28h] BYREF

  v1 = 0;
  Buffers = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 424), 0) < *(_DWORD *)(a1 + 80) )
  {
    v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 376);
    while ( 1 )
    {
      EnterCriticalSection(v5);
      v6 = *(_QWORD *)(a1 + 360);
      LeaveCriticalSection(v5);
      v7 = 0;
      if ( !v6 )
        break;
      v7 = 1;
      if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 424)) > *(_DWORD *)(a1 + 80) )
        break;
      lpOverlapped = 0;
      EnterCriticalSection(v5);
      EnterCriticalSection(v5);
      v9 = *(_QWORD *)(a1 + 360);
      LeaveCriticalSection(v5);
      if ( v9 )
      {
        lpOverlapped = *(_QWORD *)(a1 + 360);
        if ( lpOverlapped == *(_QWORD *)(a1 + 368) )
        {
          *(_QWORD *)(a1 + 360) = 0;
          *(_QWORD *)(a1 + 368) = 0;
        }
        else
        {
          v10 = *(_QWORD *)(lpOverlapped + 1264);
          *(_QWORD *)(a1 + 360) = v10;
          *(_QWORD *)(v10 + 1272) = 0;
        }
        --*(_DWORD *)(a1 + 416);
      }
      LeaveCriticalSection(v5);
      if ( !lpOverlapped )
        break;
      Buffers.buf = *(CHAR **)(*(_QWORD *)(lpOverlapped + 48) + 40LL);
      Buffers.len = *(_DWORD *)(*(_QWORD *)(lpOverlapped + 48) + 48LL);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 480));
      if ( (unsigned int)ElValidateWin32(0, v11, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1881) )
        goto LABEL_21;
      v12 = WSASendTo(
              *(_QWORD *)(a1 + 56),
              &Buffers,
              1u,
              0,
              0,
              (const struct sockaddr *)(lpOverlapped + 64),
              *(_DWORD *)(lpOverlapped + 192),
              (LPWSAOVERLAPPED)lpOverlapped,
              0);
      if ( v12 && (v12 != -1 || WSAGetLastError() != 997) )
      {
        Error = WSAGetLastError();
        v1 = ElValidateWin32(Error, v14, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1905);
        if ( v1 )
        {
          IoOperation<CClientLibrary>::Release(lpOverlapped);
          CMRSWLock::ReaderLock((CMRSWLock *)(a1 + 496));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 480), 0xFFFFFFFF) == 1 )
            SetEvent(*(HANDLE *)(a1 + 488));
          CMRSWLock::ReaderRelease((CMRSWLock *)(a1 + 496));
        }
        goto LABEL_21;
      }
    }
    Requests = CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostMaximumReadRequests(a1);
    ElValidateWin32(Requests, v16, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1915);
    if ( !v7 )
      return v1;
LABEL_21:
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 424));
  }
  else
  {
    v3 = CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostMaximumReadRequests(a1);
    ElValidateWin32(v3, v4, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1835);
  }
  return v1;
}

```

## disassembly

```asm
0x180008404  mov     rax, rsp
0x180008407  mov     [rax+10h], rbx
0x18000840b  mov     [rax+18h], rbp
0x18000840f  mov     [rax+20h], rsi
0x180008413  push    rdi
0x180008414  push    r14
0x180008416  push    r15
0x180008418  sub     rsp, 60h
0x18000841c  xorps   xmm0, xmm0
0x18000841f  xor     esi, esi
0x180008421  movups  xmmword ptr [rax-28h], xmm0
0x180008425  xor     eax, eax
0x180008427  mov     rdi, rcx
0x18000842a  lock xadd [rcx+1A8h], eax
0x180008432  cmp     eax, [rcx+50h]
0x180008435  jl      short loc_180008455
0x180008437  call    ?PostMaximumReadRequests@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@AEAAKXZ; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostMaximumReadRequests(void)
0x18000843c  mov     ecx, eax
0x18000843e  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180008445  mov     r9d, 72Bh
0x18000844b  call    ElValidateWin32
0x180008450  jmp     loc_180008673
0x180008455  lea     r14, [rcx+178h]
0x18000845c  mov     rcx, r14; lpCriticalSection
0x18000845f  call    cs:__imp_EnterCriticalSection
0x180008466  nop     dword ptr [rax+rax+00h]
0x18000846b  mov     rbx, [rdi+168h]
0x180008472  mov     rcx, r14; lpCriticalSection
0x180008475  call    cs:__imp_LeaveCriticalSection
0x18000847c  nop     dword ptr [rax+rax+00h]
0x180008481  xor     r15d, r15d
0x180008484  test    rbx, rbx
0x180008487  jz      loc_18000864B
0x18000848d  lea     eax, [r15+1]
0x180008491  lock xadd [rdi+1A8h], eax
0x180008499  inc     eax
0x18000849b  mov     r15d, 1
0x1800084a1  cmp     eax, [rdi+50h]
0x1800084a4  ja      loc_18000864B
0x1800084aa  mov     rcx, r14; lpCriticalSection
0x1800084ad  xor     ebp, ebp
0x1800084af  call    cs:__imp_EnterCriticalSection
0x1800084b6  nop     dword ptr [rax+rax+00h]
0x1800084bb  mov     rcx, r14; lpCriticalSection
0x1800084be  call    cs:__imp_EnterCriticalSection
0x1800084c5  nop     dword ptr [rax+rax+00h]
0x1800084ca  mov     rbx, [rdi+168h]
0x1800084d1  mov     rcx, r14; lpCriticalSection
0x1800084d4  call    cs:__imp_LeaveCriticalSection
0x1800084db  nop     dword ptr [rax+rax+00h]
0x1800084e0  test    rbx, rbx
0x1800084e3  jz      short loc_180008520
0x1800084e5  mov     rbp, [rdi+168h]
0x1800084ec  cmp     rbp, [rdi+170h]
0x1800084f3  jnz     short loc_180008505
0x1800084f5  and     [rdi+168h], rsi
0x1800084fc  and     [rdi+170h], rsi
0x180008503  jmp     short loc_18000851A
0x180008505  mov     rax, [rbp+4F0h]
0x18000850c  mov     [rdi+168h], rax
0x180008513  and     [rax+4F8h], rsi
0x18000851a  dec     dword ptr [rdi+1A0h]
0x180008520  mov     rcx, r14; lpCriticalSection
0x180008523  call    cs:__imp_LeaveCriticalSection
0x18000852a  nop     dword ptr [rax+rax+00h]
0x18000852f  test    rbp, rbp
0x180008532  jz      loc_18000864B
0x180008538  mov     rax, [rbp+30h]
0x18000853c  mov     rcx, [rax+28h]
0x180008540  mov     [rsp+78h+Buffers.buf], rcx
0x180008545  mov     rax, [rbp+30h]
0x180008549  mov     ecx, [rax+30h]
0x18000854c  mov     [rsp+78h+Buffers.len], ecx
0x180008550  lock inc dword ptr [rdi+1E0h]
0x180008557  mov     r9d, 759h
0x18000855d  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180008564  xor     ecx, ecx
0x180008566  call    ElValidateWin32
0x18000856b  test    eax, eax
0x18000856d  jnz     loc_18000866C
0x180008573  and     [rsp+78h+var_38], rsi
0x180008578  lea     rcx, [rbp+40h]
0x18000857c  mov     eax, [rbp+0C0h]
0x180008582  lea     rdx, [rsp+78h+Buffers]; lpBuffers
0x180008587  mov     [rsp+78h+lpOverlapped], rbp; lpOverlapped
0x18000858c  xor     r9d, r9d; lpNumberOfBytesSent
0x18000858f  mov     [rsp+78h+iTolen], eax; iTolen
0x180008593  mov     r8d, r15d; dwBufferCount
0x180008596  mov     [rsp+78h+lpTo], rcx; lpTo
0x18000859b  mov     rcx, [rdi+38h]; s
0x18000859f  and     [rsp+78h+var_58], esi
0x1800085a3  call    cs:__imp_WSASendTo
0x1800085aa  nop     dword ptr [rax+rax+00h]
0x1800085af  test    eax, eax
0x1800085b1  jz      loc_18000845C
0x1800085b7  cmp     eax, 0FFFFFFFFh
0x1800085ba  jnz     short loc_1800085D3
0x1800085bc  call    cs:__imp_WSAGetLastError
0x1800085c3  nop     dword ptr [rax+rax+00h]
0x1800085c8  cmp     eax, 3E5h
0x1800085cd  jz      loc_18000845C
0x1800085d3  call    cs:__imp_WSAGetLastError
0x1800085da  nop     dword ptr [rax+rax+00h]
0x1800085df  mov     r9d, 771h
0x1800085e5  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x1800085ec  mov     ecx, eax
0x1800085ee  call    ElValidateWin32
0x1800085f3  mov     esi, eax
0x1800085f5  test    eax, eax
0x1800085f7  jz      short loc_18000866C
0x1800085f9  mov     rcx, rbp
0x1800085fc  call    ?Release@?$IoOperation@VCClientLibrary@@@@QEAAKXZ; IoOperation<CClientLibrary>::Release(void)
0x180008601  lea     rbx, [rdi+1F0h]
0x180008608  mov     rcx, rbx
0x18000860b  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x180008612  nop     dword ptr [rax+rax+00h]
0x180008617  or      eax, 0FFFFFFFFh
0x18000861a  lock xadd [rdi+1E0h], eax
0x180008622  cmp     eax, r15d
0x180008625  jnz     short loc_18000863A
0x180008627  mov     rcx, [rdi+1E8h]; hEvent
0x18000862e  call    cs:__imp_SetEvent
0x180008635  nop     dword ptr [rax+rax+00h]
0x18000863a  mov     rcx, rbx
0x18000863d  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180008644  nop     dword ptr [rax+rax+00h]
0x180008649  jmp     short loc_18000866C
0x18000864b  mov     rcx, rdi
0x18000864e  call    ?PostMaximumReadRequests@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@AEAAKXZ; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostMaximumReadRequests(void)
0x180008653  mov     ecx, eax
0x180008655  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x18000865c  mov     r9d, 77Bh
0x180008662  call    ElValidateWin32
0x180008667  test    r15d, r15d
0x18000866a  jz      short loc_180008673
0x18000866c  lock dec dword ptr [rdi+1A8h]
0x180008673  lea     r11, [rsp+78h+var_18]
0x180008678  mov     eax, esi
0x18000867a  mov     rbx, [r11+28h]
0x18000867e  mov     rbp, [r11+30h]
0x180008682  mov     rsi, [r11+38h]
0x180008686  mov     rsp, r11
0x180008689  pop     r15
0x18000868b  pop     r14
0x18000868d  pop     rdi
0x18000868e  retn
```
