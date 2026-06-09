# WapCreateDnsIoContext

- ea: `0x180060068`
- end: `0x1800601ae`
- name: `WapCreateDnsIoContext`
- size: `326`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005176c`
- `0x18005fe9c`

## callees

- `0x180020b24`
- `0x18002e460`
- `0x1800391c0`
- `0x180060068`
- `0x1800722f0`
- `0x180072c70`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800600d9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800600d9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180060142`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180060142`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180060114`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180060114`
- `WS2_32!WSACreateEvent` at `0x1800600ee`
- `WS2_32!WSACreateEvent` at `0x1800600ee`
- `WS2_32!__imp_WSAGetLastError` at `0x18006017a`
- `WS2_32!__imp_WSAGetLastError` at `0x18006017a`

## pseudocode

```c
__int64 __fastcall WapCreateDnsIoContext(LARGE_INTEGER a1, LARGE_INTEGER a2, LARGE_INTEGER **a3)
{
  __int64 v6; // rax
  LARGE_INTEGER *v7; // rbx
  HANDLE v8; // rax
  PTP_WAIT ThreadpoolWait; // rax
  unsigned int Error; // edi
  LARGE_INTEGER PerformanceCount[2]; // [rsp+20h] [rbp-38h] BYREF

  *a3 = 0;
  v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD))WxAllocateHeapEx)((LARGE_INTEGER)a1.QuadPart, 104);
  v7 = (LARGE_INTEGER *)v6;
  if ( !v6 )
    return 8;
  memset_0((void *)(v6 + 4), 0, 0x64u);
  v7->LowPart = 1230196292;
  _InterlockedIncrement((volatile signed __int32 *)(a1.QuadPart + 4));
  v7[2] = a1;
  v7[1] = a2;
  PerformanceCount[0].QuadPart = 0;
  QueryPerformanceCounter(PerformanceCount);
  v7[5] = PerformanceCount[0];
  v8 = WSACreateEvent();
  v7[10].QuadPart = (LONGLONG)v8;
  if ( !v8 )
  {
    Error = WSAGetLastError();
    if ( !Error )
      Error = 1359;
    goto LABEL_11;
  }
  ThreadpoolWait = CreateThreadpoolWait(WapGetAddrInfoDnsWaitCompletionRoutine, v7, &WaDnsCacheEnvironment);
  v7[12].QuadPart = (LONGLONG)ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    Error = WaGetLastError();
LABEL_11:
    WapDestroyDnsIoContext(v7);
    return Error;
  }
  v7[9] = v7[10];
  Error = 0;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  if ( EventActivityIdControl(1u, (LPGUID)&v7[3]) )
    *(_OWORD *)&v7[3].LowPart = 0;
  *a3 = v7;
  return Error;
}

```

## disassembly

```asm
0x180060068  mov     [rsp+arg_8], rbx
0x18006006d  push    rsi
0x18006006e  push    rdi
0x18006006f  push    r14
0x180060071  sub     rsp, 40h
0x180060075  mov     rax, cs:__security_cookie
0x18006007c  xor     rax, rsp
0x18006007f  mov     [rsp+58h+var_28], rax
0x180060084  mov     rsi, rdx
0x180060087  mov     qword ptr [r8], 0
0x18006008e  mov     edx, 68h ; 'h'
0x180060093  mov     r14, r8
0x180060096  mov     rdi, rcx
0x180060099  call    WxAllocateHeapEx
0x18006009e  mov     rbx, rax
0x1800600a1  test    rax, rax
0x1800600a4  jz      loc_180060173
0x1800600aa  xor     edx, edx; Val
0x1800600ac  lea     rcx, [rax+4]; void *
0x1800600b0  lea     r8d, [rdx+64h]; Size
0x1800600b4  call    memset_0
0x1800600b9  mov     dword ptr [rbx], 49534E44h
0x1800600bf  lock inc dword ptr [rdi+4]
0x1800600c3  lea     rcx, [rsp+58h+PerformanceCount]; lpPerformanceCount
0x1800600c8  mov     [rbx+10h], rdi
0x1800600cc  mov     [rbx+8], rsi
0x1800600d0  mov     qword ptr [rsp+58h+PerformanceCount], 0
0x1800600d9  call    cs:__imp_QueryPerformanceCounter
0x1800600e0  nop     dword ptr [rax+rax+00h]
0x1800600e5  mov     rax, qword ptr [rsp+58h+PerformanceCount]
0x1800600ea  mov     [rbx+28h], rax
0x1800600ee  call    cs:__imp_WSACreateEvent
0x1800600f5  nop     dword ptr [rax+rax+00h]
0x1800600fa  mov     [rbx+50h], rax
0x1800600fe  test    rax, rax
0x180060101  jz      short loc_18006017A
0x180060103  lea     r8, WaDnsCacheEnvironment; pcbe
0x18006010a  mov     rdx, rbx; pv
0x18006010d  lea     rcx, WapGetAddrInfoDnsWaitCompletionRoutine; pfnwa
0x180060114  call    cs:__imp_CreateThreadpoolWait
0x18006011b  nop     dword ptr [rax+rax+00h]
0x180060120  mov     [rbx+60h], rax
0x180060124  test    rax, rax
0x180060127  jz      short loc_18006019C
0x180060129  mov     rax, [rbx+50h]
0x18006012d  lea     rdx, [rbx+18h]; ActivityId
0x180060131  xorps   xmm0, xmm0
0x180060134  mov     [rbx+48h], rax
0x180060138  xor     edi, edi
0x18006013a  movups  xmmword ptr [rsp+58h+PerformanceCount], xmm0
0x18006013f  lea     ecx, [rdi+1]; ControlCode
0x180060142  call    cs:__imp_EventActivityIdControl
0x180060149  nop     dword ptr [rax+rax+00h]
0x18006014e  test    eax, eax
0x180060150  jnz     short loc_1800601A5
0x180060152  mov     [r14], rbx
0x180060155  mov     eax, edi
0x180060157  mov     rcx, [rsp+58h+var_28]
0x18006015c  xor     rcx, rsp; StackCookie
0x18006015f  call    __security_check_cookie
0x180060164  mov     rbx, [rsp+58h+arg_8]
0x180060169  add     rsp, 40h
0x18006016d  pop     r14
0x18006016f  pop     rdi
0x180060170  pop     rsi
0x180060171  retn
0x180060173  mov     edi, 8
0x180060178  jmp     short loc_180060155
0x18006017a  call    cs:__imp_WSAGetLastError
0x180060181  nop     dword ptr [rax+rax+00h]
0x180060186  mov     edi, eax
0x180060188  mov     eax, 54Fh
0x18006018d  test    edi, edi
0x18006018f  cmovz   edi, eax
0x180060192  mov     rcx, rbx; lpMem
0x180060195  call    WapDestroyDnsIoContext
0x18006019a  jmp     short loc_180060155
0x18006019c  call    WaGetLastError
0x1800601a1  mov     edi, eax
0x1800601a3  jmp     short loc_180060192
0x1800601a5  xorps   xmm0, xmm0
0x1800601a8  movups  xmmword ptr [rbx+18h], xmm0
0x1800601ac  jmp     short loc_180060152
```
