# CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::ProcessSendQueue(void)

- ea: `0x1800197b0`
- end: `0x180019a3c`
- name: `?ProcessSendQueue@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKXZ`
- size: `652`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019340`

## callees

- `0x180003160`
- `0x180003944`
- `0x180019434`
- `0x1800197b0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180019821`
- `KERNEL32!LeaveCriticalSection` at `0x180019880`
- `KERNEL32!LeaveCriticalSection` at `0x1800198cf`
- `KERNEL32!LeaveCriticalSection` at `0x180019821`
- `KERNEL32!LeaveCriticalSection` at `0x180019880`
- `KERNEL32!LeaveCriticalSection` at `0x1800198cf`
- `KERNEL32!EnterCriticalSection` at `0x18001980b`
- `KERNEL32!EnterCriticalSection` at `0x18001985b`
- `KERNEL32!EnterCriticalSection` at `0x18001986a`
- `KERNEL32!EnterCriticalSection` at `0x18001980b`
- `KERNEL32!EnterCriticalSection` at `0x18001985b`
- `KERNEL32!EnterCriticalSection` at `0x18001986a`
- `KERNEL32!SetEvent` at `0x1800199da`
- `KERNEL32!SetEvent` at `0x1800199da`
- `WS2_32!WSASendTo` at `0x18001994f`
- `WS2_32!WSASendTo` at `0x18001994f`
- `WS2_32!__imp_WSAGetLastError` at `0x180019968`
- `WS2_32!__imp_WSAGetLastError` at `0x18001997f`
- `WS2_32!__imp_WSAGetLastError` at `0x180019968`
- `WS2_32!__imp_WSAGetLastError` at `0x18001997f`
- `WdsServerCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x1800199b7`
- `WdsServerCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x1800199b7`
- `WdsServerCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x1800199e9`
- `WdsServerCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x1800199e9`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::ProcessSendQueue(__int64 a1)
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
          IoOperation<CUdpEndpoint>::Release(lpOverlapped);
          CMRSWLock::ReaderLock((CMRSWLock *)(a1 + 496));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 480), 0xFFFFFFFF) == 1 )
            SetEvent(*(HANDLE *)(a1 + 488));
          CMRSWLock::ReaderRelease((CMRSWLock *)(a1 + 496));
        }
        goto LABEL_21;
      }
    }
    Requests = CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostMaximumReadRequests(a1);
    ElValidateWin32(Requests, v16, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1915);
    if ( !v7 )
      return v1;
LABEL_21:
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 424));
  }
  else
  {
    v3 = CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostMaximumReadRequests(a1);
    ElValidateWin32(v3, v4, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1835);
  }
  return v1;
}

```

## disassembly

```asm
0x1800197b0  mov     rax, rsp
0x1800197b3  mov     [rax+10h], rbx
0x1800197b7  mov     [rax+18h], rbp
0x1800197bb  mov     [rax+20h], rsi
0x1800197bf  push    rdi
0x1800197c0  push    r14
0x1800197c2  push    r15
0x1800197c4  sub     rsp, 60h
0x1800197c8  xorps   xmm0, xmm0
0x1800197cb  xor     esi, esi
0x1800197cd  movups  xmmword ptr [rax-28h], xmm0
0x1800197d1  xor     eax, eax
0x1800197d3  mov     rdi, rcx
0x1800197d6  lock xadd [rcx+1A8h], eax
0x1800197de  cmp     eax, [rcx+50h]
0x1800197e1  jl      short loc_180019801
0x1800197e3  call    ?PostMaximumReadRequests@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKXZ; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostMaximumReadRequests(void)
0x1800197e8  mov     ecx, eax
0x1800197ea  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x1800197f1  mov     r9d, 72Bh
0x1800197f7  call    ElValidateWin32
0x1800197fc  jmp     loc_180019A1F
0x180019801  lea     r14, [rcx+178h]
0x180019808  mov     rcx, r14; lpCriticalSection
0x18001980b  call    cs:__imp_EnterCriticalSection
0x180019812  nop     dword ptr [rax+rax+00h]
0x180019817  mov     rbx, [rdi+168h]
0x18001981e  mov     rcx, r14; lpCriticalSection
0x180019821  call    cs:__imp_LeaveCriticalSection
0x180019828  nop     dword ptr [rax+rax+00h]
0x18001982d  xor     r15d, r15d
0x180019830  test    rbx, rbx
0x180019833  jz      loc_1800199F7
0x180019839  lea     eax, [r15+1]
0x18001983d  lock xadd [rdi+1A8h], eax
0x180019845  inc     eax
0x180019847  mov     r15d, 1
0x18001984d  cmp     eax, [rdi+50h]
0x180019850  ja      loc_1800199F7
0x180019856  mov     rcx, r14; lpCriticalSection
0x180019859  xor     ebp, ebp
0x18001985b  call    cs:__imp_EnterCriticalSection
0x180019862  nop     dword ptr [rax+rax+00h]
0x180019867  mov     rcx, r14; lpCriticalSection
0x18001986a  call    cs:__imp_EnterCriticalSection
0x180019871  nop     dword ptr [rax+rax+00h]
0x180019876  mov     rbx, [rdi+168h]
0x18001987d  mov     rcx, r14; lpCriticalSection
0x180019880  call    cs:__imp_LeaveCriticalSection
0x180019887  nop     dword ptr [rax+rax+00h]
0x18001988c  test    rbx, rbx
0x18001988f  jz      short loc_1800198CC
0x180019891  mov     rbp, [rdi+168h]
0x180019898  cmp     rbp, [rdi+170h]
0x18001989f  jnz     short loc_1800198B1
0x1800198a1  and     [rdi+168h], rsi
0x1800198a8  and     [rdi+170h], rsi
0x1800198af  jmp     short loc_1800198C6
0x1800198b1  mov     rax, [rbp+4F0h]
0x1800198b8  mov     [rdi+168h], rax
0x1800198bf  and     [rax+4F8h], rsi
0x1800198c6  dec     dword ptr [rdi+1A0h]
0x1800198cc  mov     rcx, r14; lpCriticalSection
0x1800198cf  call    cs:__imp_LeaveCriticalSection
0x1800198d6  nop     dword ptr [rax+rax+00h]
0x1800198db  test    rbp, rbp
0x1800198de  jz      loc_1800199F7
0x1800198e4  mov     rax, [rbp+30h]
0x1800198e8  mov     rcx, [rax+28h]
0x1800198ec  mov     [rsp+78h+Buffers.buf], rcx
0x1800198f1  mov     rax, [rbp+30h]
0x1800198f5  mov     ecx, [rax+30h]
0x1800198f8  mov     [rsp+78h+Buffers.len], ecx
0x1800198fc  lock inc dword ptr [rdi+1E0h]
0x180019903  mov     r9d, 759h
0x180019909  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180019910  xor     ecx, ecx
0x180019912  call    ElValidateWin32
0x180019917  test    eax, eax
0x180019919  jnz     loc_180019A18
0x18001991f  and     [rsp+78h+var_38], rsi
0x180019924  lea     rcx, [rbp+40h]
0x180019928  mov     eax, [rbp+0C0h]
0x18001992e  lea     rdx, [rsp+78h+Buffers]; lpBuffers
0x180019933  mov     [rsp+78h+lpOverlapped], rbp; lpOverlapped
0x180019938  xor     r9d, r9d; lpNumberOfBytesSent
0x18001993b  mov     [rsp+78h+iTolen], eax; iTolen
0x18001993f  mov     r8d, r15d; dwBufferCount
0x180019942  mov     [rsp+78h+lpTo], rcx; lpTo
0x180019947  mov     rcx, [rdi+38h]; s
0x18001994b  and     [rsp+78h+var_58], esi
0x18001994f  call    cs:__imp_WSASendTo
0x180019956  nop     dword ptr [rax+rax+00h]
0x18001995b  test    eax, eax
0x18001995d  jz      loc_180019808
0x180019963  cmp     eax, 0FFFFFFFFh
0x180019966  jnz     short loc_18001997F
0x180019968  call    cs:__imp_WSAGetLastError
0x18001996f  nop     dword ptr [rax+rax+00h]
0x180019974  cmp     eax, 3E5h
0x180019979  jz      loc_180019808
0x18001997f  call    cs:__imp_WSAGetLastError
0x180019986  nop     dword ptr [rax+rax+00h]
0x18001998b  mov     r9d, 771h
0x180019991  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180019998  mov     ecx, eax
0x18001999a  call    ElValidateWin32
0x18001999f  mov     esi, eax
0x1800199a1  test    eax, eax
0x1800199a3  jz      short loc_180019A18
0x1800199a5  mov     rcx, rbp
0x1800199a8  call    ?Release@?$IoOperation@VCUdpEndpoint@@@@QEAAKXZ; IoOperation<CUdpEndpoint>::Release(void)
0x1800199ad  lea     rbx, [rdi+1F0h]
0x1800199b4  mov     rcx, rbx
0x1800199b7  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x1800199be  nop     dword ptr [rax+rax+00h]
0x1800199c3  or      eax, 0FFFFFFFFh
0x1800199c6  lock xadd [rdi+1E0h], eax
0x1800199ce  cmp     eax, r15d
0x1800199d1  jnz     short loc_1800199E6
0x1800199d3  mov     rcx, [rdi+1E8h]; hEvent
0x1800199da  call    cs:__imp_SetEvent
0x1800199e1  nop     dword ptr [rax+rax+00h]
0x1800199e6  mov     rcx, rbx
0x1800199e9  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x1800199f0  nop     dword ptr [rax+rax+00h]
0x1800199f5  jmp     short loc_180019A18
0x1800199f7  mov     rcx, rdi
0x1800199fa  call    ?PostMaximumReadRequests@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKXZ; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostMaximumReadRequests(void)
0x1800199ff  mov     ecx, eax
0x180019a01  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180019a08  mov     r9d, 77Bh
0x180019a0e  call    ElValidateWin32
0x180019a13  test    r15d, r15d
0x180019a16  jz      short loc_180019A1F
0x180019a18  lock dec dword ptr [rdi+1A8h]
0x180019a1f  lea     r11, [rsp+78h+var_18]
0x180019a24  mov     eax, esi
0x180019a26  mov     rbx, [r11+28h]
0x180019a2a  mov     rbp, [r11+30h]
0x180019a2e  mov     rsi, [r11+38h]
0x180019a32  mov     rsp, r11
0x180019a35  pop     r15
0x180019a37  pop     r14
0x180019a39  pop     rdi
0x180019a3a  retn
```
