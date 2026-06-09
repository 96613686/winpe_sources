# CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Shutdown(void)

- ea: `0x18001a250`
- end: `0x18001a46c`
- name: `?Shutdown@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAKXZ`
- size: `540`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800181bc`
- `0x180018b08`
- `0x18001a474`

## callees

- `0x180003160`
- `0x18001a1f4`
- `0x18001a250`
- `0x18001d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001a29b`
- `KERNEL32!LeaveCriticalSection` at `0x18001a36d`
- `KERNEL32!LeaveCriticalSection` at `0x18001a441`
- `KERNEL32!LeaveCriticalSection` at `0x18001a29b`
- `KERNEL32!LeaveCriticalSection` at `0x18001a36d`
- `KERNEL32!LeaveCriticalSection` at `0x18001a441`
- `KERNEL32!EnterCriticalSection` at `0x18001a266`
- `KERNEL32!EnterCriticalSection` at `0x18001a348`
- `KERNEL32!EnterCriticalSection` at `0x18001a357`
- `KERNEL32!EnterCriticalSection` at `0x18001a266`
- `KERNEL32!EnterCriticalSection` at `0x18001a348`
- `KERNEL32!EnterCriticalSection` at `0x18001a357`
- `KERNEL32!WaitForSingleObjectEx` at `0x18001a2b8`
- `KERNEL32!WaitForSingleObjectEx` at `0x18001a2b8`
- `WS2_32!__imp_closesocket` at `0x18001a286`
- `WS2_32!__imp_closesocket` at `0x18001a286`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x18001a332`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x18001a332`

## string_xrefs

- `0x18001a31c`: `_InterlockedExchangeAdd((LONG volatile*)&(m_lPendingWriteOperations), 0) == 0`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Shutdown(__int64 a1)
{
  SOCKET v2; // rcx
  DWORD v3; // eax
  __int64 v4; // rbx
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  _InterlockedExchange((volatile __int32 *)(a1 + 68), 1);
  v2 = *(_QWORD *)(a1 + 56);
  if ( v2 != -1 )
  {
    closesocket(v2);
    *(_QWORD *)(a1 + 56) = -1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  while ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 480), 0) )
  {
    v3 = WaitForSingleObjectEx(*(HANDLE *)(a1 + 488), 0x1F4u, 1);
    if ( v3 && v3 != 258 && v3 != 192 )
    {
      if ( g_ErrLibTraceFunctionEx )
        g_ErrLibTraceFunctionEx(0x80000u, L"CChildCount::WaitForChildren failed; %u", v3);
      break;
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 424), 0) )
    WdsAssert(
      "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h",
      0x1F6u,
      "_InterlockedExchangeAdd((LONG volatile*)&(m_lPendingWriteOperations), 0) == 0",
      1,
      0);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 376));
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 376));
  v4 = *(_QWORD *)(a1 + 360);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 376));
  if ( v4 )
  {
    v5 = *(_QWORD *)(a1 + 360);
    while ( 1 )
    {
      if ( !v5 )
        goto LABEL_26;
      v6 = *(_QWORD *)(a1 + 360);
      v7 = v5;
      v8 = *(_QWORD *)(a1 + 368);
      if ( v6 == v8 )
        break;
      if ( v5 != v6 )
      {
        if ( v5 != v8 )
        {
          v11 = v5 + 1264;
          v5 = *(_QWORD *)(v5 + 1264);
          *(_QWORD *)(*(_QWORD *)(v7 + 1272) + 1264LL) = v5;
          *(_QWORD *)(*(_QWORD *)v11 + 1272LL) = *(_QWORD *)(v7 + 1272);
          goto LABEL_23;
        }
        v10 = *(_QWORD *)(v8 + 1272);
        *(_QWORD *)(a1 + 368) = v10;
        *(_QWORD *)(v10 + 1264) = 0;
        goto LABEL_21;
      }
      v9 = *(_QWORD *)(v6 + 1264);
      *(_QWORD *)(a1 + 360) = v9;
      *(_QWORD *)(v9 + 1272) = 0;
      v5 = *(_QWORD *)(a1 + 360);
LABEL_23:
      --*(_DWORD *)(a1 + 416);
      IoOperation<CUdpEndpoint>::Release(v7);
    }
    *(_QWORD *)(a1 + 368) = 0;
    *(_QWORD *)(a1 + 360) = 0;
LABEL_21:
    v5 = 0;
    goto LABEL_23;
  }
LABEL_26:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 376));
  CPool<IoOperation<CUdpEndpoint>>::Shutdown((PSLIST_HEADER)(a1 + 432));
  return 0;
}

```

## disassembly

```asm
0x18001a250  mov     [rsp+arg_0], rbx
0x18001a255  mov     [rsp+arg_8], rsi
0x18001a25a  push    rdi
0x18001a25b  sub     rsp, 30h
0x18001a25f  mov     rdi, rcx
0x18001a262  add     rcx, 8; lpCriticalSection
0x18001a266  call    cs:__imp_EnterCriticalSection
0x18001a26d  nop     dword ptr [rax+rax+00h]
0x18001a272  mov     esi, 1
0x18001a277  mov     eax, esi
0x18001a279  xchg    eax, [rdi+44h]
0x18001a27c  mov     rcx, [rdi+38h]; s
0x18001a280  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001a284  jz      short loc_18001A297
0x18001a286  call    cs:__imp_closesocket
0x18001a28d  nop     dword ptr [rax+rax+00h]
0x18001a292  or      qword ptr [rdi+38h], 0FFFFFFFFFFFFFFFFh
0x18001a297  lea     rcx, [rdi+8]; lpCriticalSection
0x18001a29b  call    cs:__imp_LeaveCriticalSection
0x18001a2a2  nop     dword ptr [rax+rax+00h]
0x18001a2a7  jmp     short loc_18001A2D6
0x18001a2a9  mov     rcx, [rdi+1E8h]; hHandle
0x18001a2b0  mov     r8d, esi; bAlertable
0x18001a2b3  mov     edx, 1F4h; dwMilliseconds
0x18001a2b8  call    cs:__imp_WaitForSingleObjectEx
0x18001a2bf  nop     dword ptr [rax+rax+00h]
0x18001a2c4  test    eax, eax
0x18001a2c6  jz      short loc_18001A2D6
0x18001a2c8  cmp     eax, 102h
0x18001a2cd  jz      short loc_18001A2D6
0x18001a2cf  cmp     eax, 0C0h
0x18001a2d4  jnz     short loc_18001A2E6
0x18001a2d6  xor     eax, eax
0x18001a2d8  lock xadd [rdi+1E0h], eax
0x18001a2e0  test    eax, eax
0x18001a2e2  jnz     short loc_18001A2A9
0x18001a2e4  jmp     short loc_18001A309
0x18001a2e6  mov     r10, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001a2ed  test    r10, r10
0x18001a2f0  jz      short loc_18001A309
0x18001a2f2  mov     r8d, eax
0x18001a2f5  lea     rdx, aCchildcountWai; "CChildCount::WaitForChildren failed; %u"
0x18001a2fc  mov     rax, r10
0x18001a2ff  mov     ecx, 80000h
0x18001a304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a309  xor     eax, eax
0x18001a30b  lock xadd [rdi+1A8h], eax
0x18001a313  test    eax, eax
0x18001a315  jz      short loc_18001A33E
0x18001a317  and     [rsp+38h+var_18], 0
0x18001a31c  lea     r8, aInterlockedexc; "_InterlockedExchangeAdd((LONG volatile*"...
0x18001a323  mov     r9d, esi
0x18001a326  lea     rcx, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x18001a32d  mov     edx, 1F6h
0x18001a332  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a339  nop     dword ptr [rax+rax+00h]
0x18001a33e  lea     rsi, [rdi+178h]
0x18001a345  mov     rcx, rsi; lpCriticalSection
0x18001a348  call    cs:__imp_EnterCriticalSection
0x18001a34f  nop     dword ptr [rax+rax+00h]
0x18001a354  mov     rcx, rsi; lpCriticalSection
0x18001a357  call    cs:__imp_EnterCriticalSection
0x18001a35e  nop     dword ptr [rax+rax+00h]
0x18001a363  mov     rbx, [rdi+168h]
0x18001a36a  mov     rcx, rsi; lpCriticalSection
0x18001a36d  call    cs:__imp_LeaveCriticalSection
0x18001a374  nop     dword ptr [rax+rax+00h]
0x18001a379  test    rbx, rbx
0x18001a37c  jz      loc_18001A43E
0x18001a382  mov     rbx, [rdi+168h]
0x18001a389  jmp     loc_18001A435
0x18001a38e  mov     rax, [rdi+168h]
0x18001a395  mov     r8, rbx
0x18001a398  mov     rcx, [rdi+170h]
0x18001a39f  cmp     rax, rcx
0x18001a3a2  jnz     short loc_18001A3B6
0x18001a3a4  and     qword ptr [rdi+170h], 0
0x18001a3ac  and     qword ptr [rdi+168h], 0
0x18001a3b4  jmp     short loc_18001A3F5
0x18001a3b6  cmp     rbx, rax
0x18001a3b9  jnz     short loc_18001A3DA
0x18001a3bb  mov     rax, [rax+4F0h]
0x18001a3c2  mov     [rdi+168h], rax
0x18001a3c9  and     qword ptr [rax+4F8h], 0
0x18001a3d1  mov     rbx, [rdi+168h]
0x18001a3d8  jmp     short loc_18001A422
0x18001a3da  cmp     rbx, rcx
0x18001a3dd  jnz     short loc_18001A3F9
0x18001a3df  mov     rax, [rcx+4F8h]
0x18001a3e6  mov     [rdi+170h], rax
0x18001a3ed  and     qword ptr [rax+4F0h], 0
0x18001a3f5  xor     ebx, ebx
0x18001a3f7  jmp     short loc_18001A422
0x18001a3f9  mov     rax, [r8+4F8h]
0x18001a400  lea     rdx, [rbx+4F0h]
0x18001a407  mov     rbx, [rdx]
0x18001a40a  mov     [rax+4F0h], rbx
0x18001a411  mov     rdx, [rdx]
0x18001a414  mov     rax, [r8+4F8h]
0x18001a41b  mov     [rdx+4F8h], rax
0x18001a422  dec     dword ptr [rdi+1A0h]
0x18001a428  test    r8, r8
0x18001a42b  jz      short loc_18001A435
0x18001a42d  mov     rcx, r8
0x18001a430  call    ?Release@?$IoOperation@VCUdpEndpoint@@@@QEAAKXZ; IoOperation<CUdpEndpoint>::Release(void)
0x18001a435  test    rbx, rbx
0x18001a438  jnz     loc_18001A38E
0x18001a43e  mov     rcx, rsi; lpCriticalSection
0x18001a441  call    cs:__imp_LeaveCriticalSection
0x18001a448  nop     dword ptr [rax+rax+00h]
0x18001a44d  lea     rcx, [rdi+1B0h]; ListHead
0x18001a454  call    ?Shutdown@?$CPool@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAXXZ; CPool<IoOperation<CUdpEndpoint>>::Shutdown(void)
0x18001a459  mov     rbx, [rsp+38h+arg_0]
0x18001a45e  xor     eax, eax
0x18001a460  mov     rsi, [rsp+38h+arg_8]
0x18001a465  add     rsp, 30h
0x18001a469  pop     rdi
0x18001a46a  retn
```
