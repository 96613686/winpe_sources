# CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::SendOrQueue(IoOperation<CUdpEndpoint> *)

- ea: `0x180019a44`
- end: `0x180019c36`
- name: `?SendOrQueue@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKPEAU?$IoOperation@VCUdpEndpoint@@@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019c3c`
- `0x180019d14`

## callees

- `0x180003944`
- `0x180019434`
- `0x180019a44`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180019aed`
- `KERNEL32!LeaveCriticalSection` at `0x180019aed`
- `KERNEL32!EnterCriticalSection` at `0x180019a87`
- `KERNEL32!EnterCriticalSection` at `0x180019a87`
- `KERNEL32!SetEvent` at `0x180019bf7`
- `KERNEL32!SetEvent` at `0x180019bf7`
- `WS2_32!WSASendTo` at `0x180019b80`
- `WS2_32!WSASendTo` at `0x180019b80`
- `WS2_32!__imp_WSAGetLastError` at `0x180019b99`
- `WS2_32!__imp_WSAGetLastError` at `0x180019bac`
- `WS2_32!__imp_WSAGetLastError` at `0x180019b99`
- `WS2_32!__imp_WSAGetLastError` at `0x180019bac`
- `WdsServerCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x180019bd4`
- `WdsServerCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x180019bd4`
- `WdsServerCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180019c06`
- `WdsServerCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180019c06`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::SendOrQueue(__int64 a1, __int64 a2)
{
  unsigned int v2; // edi
  struct _RTL_CRITICAL_SECTION *v5; // rbp
  __int64 v7; // rcx
  int v8; // eax
  unsigned int Error; // eax
  __int64 v10; // rdx
  unsigned int v11; // esi
  unsigned int Requests; // eax
  __int64 v13; // rdx
  struct _WSABUF Buffers; // [rsp+50h] [rbp-18h] BYREF

  v2 = 0;
  Buffers = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 424)) <= *(_DWORD *)(a1 + 80) )
  {
    v7 = *(_QWORD *)(a2 + 48);
    Buffers.buf = *(CHAR **)(v7 + 40);
    Buffers.len = *(_DWORD *)(v7 + 48);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 480));
    if ( !(unsigned int)ElValidateWin32(0, a2, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 750) )
    {
      v8 = WSASendTo(
             *(_QWORD *)(a1 + 56),
             &Buffers,
             1u,
             0,
             0,
             (const struct sockaddr *)(a2 + 64),
             *(_DWORD *)(a2 + 192),
             (LPWSAOVERLAPPED)a2,
             0);
      if ( !v8 || v8 == -1 && WSAGetLastError() == 997 )
      {
        Requests = CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostMaximumReadRequests(a1);
        ElValidateWin32(Requests, v13, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 784);
        return v2;
      }
      Error = WSAGetLastError();
      v11 = ElValidateWin32(Error, v10, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 775);
      CMRSWLock::ReaderLock((CMRSWLock *)(a1 + 496));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 480), 0xFFFFFFFF) == 1 )
        SetEvent(*(HANDLE *)(a1 + 488));
      CMRSWLock::ReaderRelease((CMRSWLock *)(a1 + 496));
      v2 = v11;
    }
  }
  else
  {
    v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 376);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 376));
    if ( *(_QWORD *)(a1 + 360) )
    {
      *(_QWORD *)(a2 + 1264) = 0;
      *(_QWORD *)(a2 + 1272) = *(_QWORD *)(a1 + 368);
      *(_QWORD *)(*(_QWORD *)(a1 + 368) + 1264LL) = a2;
      *(_QWORD *)(a1 + 368) = a2;
    }
    else
    {
      *(_QWORD *)(a1 + 368) = a2;
      *(_QWORD *)(a1 + 360) = a2;
      *(_QWORD *)(a2 + 1264) = 0;
      *(_QWORD *)(a2 + 1272) = 0;
    }
    ++*(_DWORD *)(a1 + 416);
    LeaveCriticalSection(v5);
  }
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 424));
  return v2;
}

```

## disassembly

```asm
0x180019a44  mov     rax, rsp
0x180019a47  mov     [rax+10h], rbx
0x180019a4b  mov     [rax+18h], rbp
0x180019a4f  mov     [rax+20h], rsi
0x180019a53  push    rdi
0x180019a54  sub     rsp, 60h
0x180019a58  xor     edi, edi
0x180019a5a  xorps   xmm0, xmm0
0x180019a5d  movups  xmmword ptr [rax-18h], xmm0
0x180019a61  mov     rsi, rdx
0x180019a64  mov     rbx, rcx
0x180019a67  lea     eax, [rdi+1]
0x180019a6a  lock xadd [rcx+1A8h], eax
0x180019a72  inc     eax
0x180019a74  cmp     eax, [rcx+50h]
0x180019a77  jle     loc_180019B19
0x180019a7d  lea     rbp, [rcx+178h]
0x180019a84  mov     rcx, rbp; lpCriticalSection
0x180019a87  call    cs:__imp_EnterCriticalSection
0x180019a8e  nop     dword ptr [rax+rax+00h]
0x180019a93  cmp     [rbx+168h], rdi
0x180019a9a  jnz     short loc_180019ABA
0x180019a9c  mov     [rbx+170h], rsi
0x180019aa3  mov     [rbx+168h], rsi
0x180019aaa  mov     [rsi+4F0h], rdi
0x180019ab1  mov     [rsi+4F8h], rdi
0x180019ab8  jmp     short loc_180019AE4
0x180019aba  mov     [rsi+4F0h], rdi
0x180019ac1  mov     rax, [rbx+170h]
0x180019ac8  mov     [rsi+4F8h], rax
0x180019acf  mov     rax, [rbx+170h]
0x180019ad6  mov     [rax+4F0h], rsi
0x180019add  mov     [rbx+170h], rsi
0x180019ae4  inc     dword ptr [rbx+1A0h]
0x180019aea  mov     rcx, rbp; lpCriticalSection
0x180019aed  call    cs:__imp_LeaveCriticalSection
0x180019af4  nop     dword ptr [rax+rax+00h]
0x180019af9  lock dec dword ptr [rbx+1A8h]
0x180019b00  lea     r11, [rsp+68h+var_8]
0x180019b05  mov     eax, edi
0x180019b07  mov     rbx, [r11+18h]
0x180019b0b  mov     rbp, [r11+20h]
0x180019b0f  mov     rsi, [r11+28h]
0x180019b13  mov     rsp, r11
0x180019b16  pop     rdi
0x180019b17  retn
0x180019b19  mov     rcx, [rdx+30h]
0x180019b1d  mov     rax, [rcx+28h]
0x180019b21  mov     [rsp+68h+Buffers.buf], rax
0x180019b26  mov     eax, [rcx+30h]
0x180019b29  mov     [rsp+68h+Buffers.len], eax
0x180019b2d  lock inc dword ptr [rbx+1E0h]
0x180019b34  lea     rbp, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180019b3b  mov     r9d, 2EEh
0x180019b41  mov     r8, rbp
0x180019b44  xor     ecx, ecx
0x180019b46  call    ElValidateWin32
0x180019b4b  test    eax, eax
0x180019b4d  jnz     short loc_180019AF9
0x180019b4f  mov     eax, [rsi+0C0h]
0x180019b55  lea     rcx, [rsi+40h]
0x180019b59  mov     [rsp+68h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x180019b5e  lea     rdx, [rsp+68h+Buffers]; lpBuffers
0x180019b63  mov     [rsp+68h+lpOverlapped], rsi; lpOverlapped
0x180019b68  xor     r9d, r9d; lpNumberOfBytesSent
0x180019b6b  mov     [rsp+68h+iTolen], eax; iTolen
0x180019b6f  mov     [rsp+68h+lpTo], rcx; lpTo
0x180019b74  mov     rcx, [rbx+38h]; s
0x180019b78  lea     r8d, [r9+1]; dwBufferCount
0x180019b7c  mov     [rsp+68h+dwFlags], edi; dwFlags
0x180019b80  call    cs:__imp_WSASendTo
0x180019b87  nop     dword ptr [rax+rax+00h]
0x180019b8c  test    eax, eax
0x180019b8e  jz      loc_180019C19
0x180019b94  cmp     eax, 0FFFFFFFFh
0x180019b97  jnz     short loc_180019BAC
0x180019b99  call    cs:__imp_WSAGetLastError
0x180019ba0  nop     dword ptr [rax+rax+00h]
0x180019ba5  cmp     eax, 3E5h
0x180019baa  jz      short loc_180019C19
0x180019bac  call    cs:__imp_WSAGetLastError
0x180019bb3  nop     dword ptr [rax+rax+00h]
0x180019bb8  mov     r9d, 307h
0x180019bbe  mov     r8, rbp
0x180019bc1  mov     ecx, eax
0x180019bc3  call    ElValidateWin32
0x180019bc8  lea     rdi, [rbx+1F0h]
0x180019bcf  mov     esi, eax
0x180019bd1  mov     rcx, rdi
0x180019bd4  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x180019bdb  nop     dword ptr [rax+rax+00h]
0x180019be0  or      edx, 0FFFFFFFFh
0x180019be3  lock xadd [rbx+1E0h], edx
0x180019beb  cmp     edx, 1
0x180019bee  jnz     short loc_180019C03
0x180019bf0  mov     rcx, [rbx+1E8h]; hEvent
0x180019bf7  call    cs:__imp_SetEvent
0x180019bfe  nop     dword ptr [rax+rax+00h]
0x180019c03  mov     rcx, rdi
0x180019c06  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180019c0d  nop     dword ptr [rax+rax+00h]
0x180019c12  mov     edi, esi
0x180019c14  jmp     loc_180019AF9
0x180019c19  mov     rcx, rbx
0x180019c1c  call    ?PostMaximumReadRequests@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKXZ; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostMaximumReadRequests(void)
0x180019c21  mov     ecx, eax
0x180019c23  mov     r9d, 310h
0x180019c29  mov     r8, rbp
0x180019c2c  call    ElValidateWin32
0x180019c31  jmp     loc_180019B00
```
