# CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Shutdown(void)

- ea: `0x18000a858`
- end: `0x18000aa74`
- name: `?Shutdown@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAAKXZ`
- size: `540`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000342c`
- `0x180006dac`
- `0x1800077f4`
- `0x180009fc8`

## callees

- `0x1800095ac`
- `0x18000a7fc`
- `0x18000a858`
- `0x18000e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000a86e`
- `KERNEL32!EnterCriticalSection` at `0x18000a950`
- `KERNEL32!EnterCriticalSection` at `0x18000a95f`
- `KERNEL32!EnterCriticalSection` at `0x18000a86e`
- `KERNEL32!EnterCriticalSection` at `0x18000a950`
- `KERNEL32!EnterCriticalSection` at `0x18000a95f`
- `KERNEL32!LeaveCriticalSection` at `0x18000a8a3`
- `KERNEL32!LeaveCriticalSection` at `0x18000a975`
- `KERNEL32!LeaveCriticalSection` at `0x18000aa49`
- `KERNEL32!LeaveCriticalSection` at `0x18000a8a3`
- `KERNEL32!LeaveCriticalSection` at `0x18000a975`
- `KERNEL32!LeaveCriticalSection` at `0x18000aa49`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000a8c0`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000a8c0`
- `WS2_32!__imp_closesocket` at `0x18000a88e`
- `WS2_32!__imp_closesocket` at `0x18000a88e`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x18000a93a`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x18000a93a`

## string_xrefs

- `0x18000a924`: `_InterlockedExchangeAdd((LONG volatile*)&(m_lPendingWriteOperations), 0) == 0`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Shutdown(__int64 a1)
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
      IoOperation<CClientLibrary>::Release(v7);
    }
    *(_QWORD *)(a1 + 368) = 0;
    *(_QWORD *)(a1 + 360) = 0;
LABEL_21:
    v5 = 0;
    goto LABEL_23;
  }
LABEL_26:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 376));
  CPool<IoOperation<CClientLibrary>>::Shutdown((PSLIST_HEADER)(a1 + 432));
  return 0;
}

```

## disassembly

```asm
0x18000a858  mov     [rsp+arg_0], rbx
0x18000a85d  mov     [rsp+arg_8], rsi
0x18000a862  push    rdi
0x18000a863  sub     rsp, 30h
0x18000a867  mov     rdi, rcx
0x18000a86a  add     rcx, 8; lpCriticalSection
0x18000a86e  call    cs:__imp_EnterCriticalSection
0x18000a875  nop     dword ptr [rax+rax+00h]
0x18000a87a  mov     esi, 1
0x18000a87f  mov     eax, esi
0x18000a881  xchg    eax, [rdi+44h]
0x18000a884  mov     rcx, [rdi+38h]; s
0x18000a888  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a88c  jz      short loc_18000A89F
0x18000a88e  call    cs:__imp_closesocket
0x18000a895  nop     dword ptr [rax+rax+00h]
0x18000a89a  or      qword ptr [rdi+38h], 0FFFFFFFFFFFFFFFFh
0x18000a89f  lea     rcx, [rdi+8]; lpCriticalSection
0x18000a8a3  call    cs:__imp_LeaveCriticalSection
0x18000a8aa  nop     dword ptr [rax+rax+00h]
0x18000a8af  jmp     short loc_18000A8DE
0x18000a8b1  mov     rcx, [rdi+1E8h]; hHandle
0x18000a8b8  mov     r8d, esi; bAlertable
0x18000a8bb  mov     edx, 1F4h; dwMilliseconds
0x18000a8c0  call    cs:__imp_WaitForSingleObjectEx
0x18000a8c7  nop     dword ptr [rax+rax+00h]
0x18000a8cc  test    eax, eax
0x18000a8ce  jz      short loc_18000A8DE
0x18000a8d0  cmp     eax, 102h
0x18000a8d5  jz      short loc_18000A8DE
0x18000a8d7  cmp     eax, 0C0h
0x18000a8dc  jnz     short loc_18000A8EE
0x18000a8de  xor     eax, eax
0x18000a8e0  lock xadd [rdi+1E0h], eax
0x18000a8e8  test    eax, eax
0x18000a8ea  jnz     short loc_18000A8B1
0x18000a8ec  jmp     short loc_18000A911
0x18000a8ee  mov     r10, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000a8f5  test    r10, r10
0x18000a8f8  jz      short loc_18000A911
0x18000a8fa  mov     r8d, eax
0x18000a8fd  lea     rdx, aCchildcountWai; "CChildCount::WaitForChildren failed; %u"
0x18000a904  mov     rax, r10
0x18000a907  mov     ecx, 80000h
0x18000a90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a911  xor     eax, eax
0x18000a913  lock xadd [rdi+1A8h], eax
0x18000a91b  test    eax, eax
0x18000a91d  jz      short loc_18000A946
0x18000a91f  and     [rsp+38h+var_18], 0
0x18000a924  lea     r8, aInterlockedexc; "_InterlockedExchangeAdd((LONG volatile*"...
0x18000a92b  mov     r9d, esi
0x18000a92e  lea     rcx, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x18000a935  mov     edx, 1F6h
0x18000a93a  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000a941  nop     dword ptr [rax+rax+00h]
0x18000a946  lea     rsi, [rdi+178h]
0x18000a94d  mov     rcx, rsi; lpCriticalSection
0x18000a950  call    cs:__imp_EnterCriticalSection
0x18000a957  nop     dword ptr [rax+rax+00h]
0x18000a95c  mov     rcx, rsi; lpCriticalSection
0x18000a95f  call    cs:__imp_EnterCriticalSection
0x18000a966  nop     dword ptr [rax+rax+00h]
0x18000a96b  mov     rbx, [rdi+168h]
0x18000a972  mov     rcx, rsi; lpCriticalSection
0x18000a975  call    cs:__imp_LeaveCriticalSection
0x18000a97c  nop     dword ptr [rax+rax+00h]
0x18000a981  test    rbx, rbx
0x18000a984  jz      loc_18000AA46
0x18000a98a  mov     rbx, [rdi+168h]
0x18000a991  jmp     loc_18000AA3D
0x18000a996  mov     rax, [rdi+168h]
0x18000a99d  mov     r8, rbx
0x18000a9a0  mov     rcx, [rdi+170h]
0x18000a9a7  cmp     rax, rcx
0x18000a9aa  jnz     short loc_18000A9BE
0x18000a9ac  and     qword ptr [rdi+170h], 0
0x18000a9b4  and     qword ptr [rdi+168h], 0
0x18000a9bc  jmp     short loc_18000A9FD
0x18000a9be  cmp     rbx, rax
0x18000a9c1  jnz     short loc_18000A9E2
0x18000a9c3  mov     rax, [rax+4F0h]
0x18000a9ca  mov     [rdi+168h], rax
0x18000a9d1  and     qword ptr [rax+4F8h], 0
0x18000a9d9  mov     rbx, [rdi+168h]
0x18000a9e0  jmp     short loc_18000AA2A
0x18000a9e2  cmp     rbx, rcx
0x18000a9e5  jnz     short loc_18000AA01
0x18000a9e7  mov     rax, [rcx+4F8h]
0x18000a9ee  mov     [rdi+170h], rax
0x18000a9f5  and     qword ptr [rax+4F0h], 0
0x18000a9fd  xor     ebx, ebx
0x18000a9ff  jmp     short loc_18000AA2A
0x18000aa01  mov     rax, [r8+4F8h]
0x18000aa08  lea     rdx, [rbx+4F0h]
0x18000aa0f  mov     rbx, [rdx]
0x18000aa12  mov     [rax+4F0h], rbx
0x18000aa19  mov     rdx, [rdx]
0x18000aa1c  mov     rax, [r8+4F8h]
0x18000aa23  mov     [rdx+4F8h], rax
0x18000aa2a  dec     dword ptr [rdi+1A0h]
0x18000aa30  test    r8, r8
0x18000aa33  jz      short loc_18000AA3D
0x18000aa35  mov     rcx, r8
0x18000aa38  call    ?Release@?$IoOperation@VCClientLibrary@@@@QEAAKXZ; IoOperation<CClientLibrary>::Release(void)
0x18000aa3d  test    rbx, rbx
0x18000aa40  jnz     loc_18000A996
0x18000aa46  mov     rcx, rsi; lpCriticalSection
0x18000aa49  call    cs:__imp_LeaveCriticalSection
0x18000aa50  nop     dword ptr [rax+rax+00h]
0x18000aa55  lea     rcx, [rdi+1B0h]; ListHead
0x18000aa5c  call    ?Shutdown@?$CPool@U?$IoOperation@VCClientLibrary@@@@@@QEAAXXZ; CPool<IoOperation<CClientLibrary>>::Shutdown(void)
0x18000aa61  mov     rbx, [rsp+38h+arg_0]
0x18000aa66  xor     eax, eax
0x18000aa68  mov     rsi, [rsp+38h+arg_8]
0x18000aa6d  add     rsp, 30h
0x18000aa71  pop     rdi
0x18000aa72  retn
```
