# WapTcpConnectSocket

- ea: `0x180053f5c`
- end: `0x18005434b`
- name: `WapTcpConnectSocket`
- size: `1007`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800522a0`
- `0x180052950`

## callees

- `0x180053f5c`
- `0x180054354`
- `0x1800545cc`
- `0x180068018`
- `0x1800722f0`
- `0x180072c70`
- `0x1800923bc`
- `0x1800971ec`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180054016`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180054016`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800540bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800540bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800541e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800541e4`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800542bf`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800542bf`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180054174`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180054174`
- `WS2_32!WSAIoctl` at `0x180054119`
- `WS2_32!WSAIoctl` at `0x180054119`
- `WS2_32!__imp_htons` at `0x1800540a1`
- `WS2_32!__imp_htons` at `0x1800540a1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800541bf`
- `WS2_32!__imp_WSAGetLastError` at `0x180054223`
- `WS2_32!__imp_WSAGetLastError` at `0x1800541bf`
- `WS2_32!__imp_WSAGetLastError` at `0x180054223`

## pseudocode

```c
__int64 __fastcall WapTcpConnectSocket(__int64 a1, __int64 a2)
{
  _OWORD *v4; // rbx
  u_short v5; // cx
  SOCKET v6; // rcx
  unsigned int v7; // r14d
  __int64 v8; // r9
  unsigned int Error; // ebx
  unsigned int (__fastcall *vOutBuffer)(_QWORD, _OWORD *, _QWORD, _QWORD, _DWORD, _QWORD, __int64); // [rsp+50h] [rbp-B0h] BYREF
  _DWORD vInBuffer[4]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbBytesReturned; // [rsp+68h] [rbp-98h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v15[8]; // [rsp+80h] [rbp-80h] BYREF

  cbBytesReturned = 0;
  vInBuffer[0] = 631375801;
  vInBuffer[1] = 1180753395;
  vInBuffer[2] = -445191794;
  vInBuffer[3] = 1040610444;
  memset_0(v15, 0, sizeof(v15));
  vOutBuffer = 0;
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_qq(1027, 48, (unsigned int)WPP_14086b36644f38024399eb8d606249d9_Traceguids, a1, a2);
  v4 = (_OWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 336) + 32LL) + ((unsigned __int64)*(unsigned int *)(a2 + 208) << 7));
  (*(void (__fastcall **)(_QWORD, _QWORD, _OWORD *, __int64))(*(_QWORD *)(a1 + 16) + 88LL))(
    *(_QWORD *)(a1 + 8),
    0,
    v4,
    128);
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  *(LARGE_INTEGER *)(a1 + 1128) = PerformanceCount;
  if ( *(_DWORD *)(a2 + 220) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 4));
    WaSetTwTimer(a2 + 128, *(unsigned int *)(a2 + 220), &WapTcpConnectTimeoutRoutine, a2);
  }
  v5 = *(_WORD *)(a1 + 352);
  v15[0] = *v4;
  v15[1] = v4[1];
  v15[2] = v4[2];
  v15[3] = v4[3];
  v15[4] = v4[4];
  v15[5] = v4[5];
  v15[6] = v4[6];
  v15[7] = v4[7];
  WORD1(v15[0]) = htons(v5);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 696));
  v6 = *(_QWORD *)(a1 + 704);
  if ( v6 == -1 )
  {
    Error = *(_DWORD *)(a1 + 232);
  }
  else
  {
    v7 = 16;
    if ( WSAIoctl(v6, 0xC8000006, vInBuffer, 0x10u, &vOutBuffer, 8u, &cbBytesReturned, 0, 0) != -1 )
    {
      if ( LOWORD(v15[0]) != 2 )
      {
        v7 = 128;
        if ( LOWORD(v15[0]) == 23 )
          v7 = 28;
      }
      WapTcpConnectSocketStartTrace(a1, v15, v7, a2);
      v8 = *(unsigned int *)(a2 + 232);
      Error = *(_BYTE *)(a1 + 981) == 0 ? 0x3E5 : 0;
      if ( (_DWORD)v8 && (xmmword_1800AD720 & 8) != 0 )
        WPP_SF_d(1027, 49, WPP_14086b36644f38024399eb8d606249d9_Traceguids, v8);
      StartThreadpoolIo(*(PTP_IO *)(a1 + 712));
      if ( !vOutBuffer(*(_QWORD *)(a1 + 704), v15, v7, *(_QWORD *)(a2 + 224), *(_DWORD *)(a2 + 232), 0, a2 + 24) )
      {
        Error = WSAGetLastError();
        if ( !Error )
          __fastfail(7u);
      }
      if ( Error != 997 )
      {
        CancelThreadpoolIo(*(PTP_IO *)(a1 + 712));
        if ( (Microsoft_Windows_WebIOEnableBits & 0x8000) != 0 )
          McTemplateU0pxqzr2pxqx_EventWriteTransfer(
            (unsigned int)&WEB_ETW_PROVIDER_ID_Context,
            (unsigned int)NetSocketConnectFailed,
            *(_QWORD *)(a1 + 8),
            *(_QWORD *)(a1 + 704),
            0,
            0,
            a2 + 16,
            *(_DWORD *)(a2 + 212),
            Error,
            0);
      }
      goto LABEL_12;
    }
    Error = WSAGetLastError();
  }
  if ( !Error )
    Error = 1359;
LABEL_12:
  ReleaseSRWLockShared((PSRWLOCK)(a1 + 696));
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_d(1027, 50, WPP_14086b36644f38024399eb8d606249d9_Traceguids, Error);
  return Error;
}

```

## disassembly

```asm
0x180053f5c  mov     [rsp-8+arg_10], rbx
0x180053f61  push    rbp
0x180053f62  push    rsi
0x180053f63  push    rdi
0x180053f64  push    r14
0x180053f66  push    r15
0x180053f68  lea     rbp, [rsp-10h]
0x180053f6d  sub     rsp, 110h
0x180053f74  mov     rax, cs:__security_cookie
0x180053f7b  xor     rax, rsp
0x180053f7e  mov     [rbp+30h+var_30], rax
0x180053f82  mov     rsi, rdx
0x180053f85  mov     [rsp+130h+cbBytesReturned], 0
0x180053f8d  mov     rdi, rcx
0x180053f90  mov     [rsp+130h+vInBuffer], 25A207B9h
0x180053f98  mov     r14d, 80h
0x180053f9e  mov     [rsp+130h+var_D4], 4660DDF3h
0x180053fa6  mov     r8d, r14d; Size
0x180053fa9  mov     [rsp+130h+var_D0], 0E576E98Eh
0x180053fb1  xor     edx, edx; Val
0x180053fb3  mov     [rsp+130h+var_CC], 3E06748Ch
0x180053fbb  lea     rcx, [rbp+30h+var_B0]; void *
0x180053fbf  call    memset_0
0x180053fc4  mov     [rsp+130h+vOutBuffer], 0
0x180053fcd  test    byte ptr cs:xmmword_1800AD720, 8
0x180053fd4  jnz     loc_18005425C
0x180053fda  mov     rax, [rdi+150h]
0x180053fe1  mov     r9, r14
0x180053fe4  mov     ebx, [rsi+0D0h]
0x180053fea  xor     edx, edx
0x180053fec  mov     rcx, [rdi+8]
0x180053ff0  shl     rbx, 7
0x180053ff4  add     rbx, [rax+20h]
0x180053ff8  mov     rax, [rdi+10h]
0x180053ffc  mov     r8, rbx
0x180053fff  mov     rax, [rax+58h]
0x180054003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054008  lea     rcx, [rsp+130h+PerformanceCount]; lpPerformanceCount
0x18005400d  mov     qword ptr [rsp+130h+PerformanceCount], 0
0x180054016  call    cs:__imp_QueryPerformanceCounter
0x18005401d  nop     dword ptr [rax+rax+00h]
0x180054022  mov     rax, qword ptr [rsp+130h+PerformanceCount]
0x180054027  mov     [rdi+468h], rax
0x18005402e  cmp     dword ptr [rsi+0DCh], 0
0x180054035  jz      short loc_180054057
0x180054037  lock inc dword ptr [rsi+4]
0x18005403b  mov     edx, [rsi+0DCh]
0x180054041  lea     rcx, [rsi+80h]
0x180054048  mov     r9, rsi
0x18005404b  lea     r8, WapTcpConnectTimeoutRoutine
0x180054052  call    WaSetTwTimer
0x180054057  movups  xmm2, xmmword ptr [rbx]
0x18005405a  movzx   ecx, word ptr [rdi+160h]; hostshort
0x180054061  movaps  [rbp+30h+var_B0], xmm2
0x180054065  movups  xmm0, xmmword ptr [rbx+10h]
0x180054069  movd    eax, xmm2
0x18005406d  movaps  [rbp+30h+var_A0], xmm0
0x180054071  movups  xmm1, xmmword ptr [rbx+20h]
0x180054075  movaps  [rbp+30h+var_90], xmm1
0x180054079  movups  xmm0, xmmword ptr [rbx+30h]
0x18005407d  movaps  [rbp+30h+var_80], xmm0
0x180054081  movups  xmm1, xmmword ptr [rbx+40h]
0x180054085  movaps  [rbp+30h+var_70], xmm1
0x180054089  movups  xmm0, xmmword ptr [rbx+50h]
0x18005408d  movaps  [rbp+30h+var_60], xmm0
0x180054091  movups  xmm1, xmmword ptr [rbx+60h]
0x180054095  movaps  [rbp+30h+var_50], xmm1
0x180054099  movups  xmm0, xmmword ptr [rbx+70h]
0x18005409d  movaps  [rbp+30h+var_40], xmm0
0x1800540a1  call    cs:__imp_htons
0x1800540a8  nop     dword ptr [rax+rax+00h]
0x1800540ad  lea     r15, [rdi+2B8h]
0x1800540b4  mov     word ptr [rbp+30h+var_B0+2], ax
0x1800540b8  mov     rcx, r15; SRWLock
0x1800540bb  call    cs:__imp_AcquireSRWLockShared
0x1800540c2  nop     dword ptr [rax+rax+00h]
0x1800540c7  mov     rcx, [rdi+2C0h]; s
0x1800540ce  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800540d2  jz      loc_180054254
0x1800540d8  mov     [rsp+130h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1800540e1  lea     rax, [rsp+130h+cbBytesReturned]
0x1800540e6  mov     [rsp+130h+lpOverlapped], 0; lpOverlapped
0x1800540ef  lea     r8, [rsp+130h+vInBuffer]; lpvInBuffer
0x1800540f4  mov     [rsp+130h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800540f9  mov     r14d, 10h
0x1800540ff  lea     rax, [rsp+130h+vOutBuffer]
0x180054104  mov     [rsp+130h+cbOutBuffer], 8; cbOutBuffer
0x18005410c  mov     r9d, r14d; cbInBuffer
0x18005410f  mov     [rsp+130h+lpvOutBuffer], rax; lpvOutBuffer
0x180054114  mov     edx, 0C8000006h; dwIoControlCode
0x180054119  call    cs:__imp_WSAIoctl
0x180054120  nop     dword ptr [rax+rax+00h]
0x180054125  cmp     eax, 0FFFFFFFFh
0x180054128  jz      loc_180054223
0x18005412e  cmp     word ptr [rbp+30h+var_B0], 2
0x180054133  jnz     loc_18005423D
0x180054139  mov     r9, rsi
0x18005413c  lea     rdx, [rbp+30h+var_B0]
0x180054140  mov     r8d, r14d
0x180054143  mov     rcx, rdi
0x180054146  call    WapTcpConnectSocketStartTrace
0x18005414b  mov     al, [rdi+3D5h]
0x180054151  mov     r9d, [rsi+0E8h]
0x180054158  neg     al
0x18005415a  sbb     ebx, ebx
0x18005415c  not     ebx
0x18005415e  and     ebx, 3E5h
0x180054164  test    r9d, r9d
0x180054167  jnz     loc_18005427F
0x18005416d  mov     rcx, [rdi+2C8h]; pio
0x180054174  call    cs:__imp_StartThreadpoolIo
0x18005417b  nop     dword ptr [rax+rax+00h]
0x180054180  mov     r9, [rsi+0E0h]
0x180054187  lea     rcx, [rsi+18h]
0x18005418b  mov     rax, [rsp+130h+vOutBuffer]
0x180054190  lea     rdx, [rbp+30h+var_B0]
0x180054194  mov     [rsp+130h+lpcbBytesReturned], rcx
0x180054199  mov     r8d, r14d
0x18005419c  mov     ecx, [rsi+0E8h]
0x1800541a2  mov     qword ptr [rsp+130h+cbOutBuffer], 0
0x1800541ab  mov     dword ptr [rsp+130h+lpvOutBuffer], ecx
0x1800541af  mov     rcx, [rdi+2C0h]
0x1800541b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541bb  test    eax, eax
0x1800541bd  jnz     short loc_1800541D5
0x1800541bf  call    cs:__imp_WSAGetLastError
0x1800541c6  nop     dword ptr [rax+rax+00h]
0x1800541cb  mov     ebx, eax
0x1800541cd  test    eax, eax
0x1800541cf  jz      loc_1800542A7
0x1800541d5  cmp     ebx, 3E5h
0x1800541db  jnz     loc_1800542B8
0x1800541e1  mov     rcx, r15; SRWLock
0x1800541e4  call    cs:__imp_ReleaseSRWLockShared
0x1800541eb  nop     dword ptr [rax+rax+00h]
0x1800541f0  test    byte ptr cs:xmmword_1800AD720, 8
0x1800541f7  jnz     loc_18005432D
0x1800541fd  mov     eax, ebx
0x1800541ff  mov     rcx, [rbp+30h+var_30]
0x180054203  xor     rcx, rsp; StackCookie
0x180054206  call    __security_check_cookie
0x18005420b  mov     rbx, [rsp+130h+arg_10]
0x180054213  add     rsp, 110h
0x18005421a  pop     r15
0x18005421c  pop     r14
0x18005421e  pop     rdi
0x18005421f  pop     rsi
0x180054220  pop     rbp
0x180054221  retn
0x180054223  call    cs:__imp_WSAGetLastError
0x18005422a  nop     dword ptr [rax+rax+00h]
0x18005422f  mov     ebx, eax
0x180054231  test    ebx, ebx
0x180054233  mov     eax, 54Fh
0x180054238  cmovz   ebx, eax
0x18005423b  jmp     short loc_1800541E1
0x18005423d  cmp     word ptr [rbp+30h+var_B0], 17h
0x180054242  mov     eax, 1Ch
0x180054247  lea     r14d, [rax+64h]
0x18005424b  cmovz   r14d, eax
0x18005424f  jmp     loc_180054139
0x180054254  mov     ebx, [rdi+0E8h]
0x18005425a  jmp     short loc_180054231
0x18005425c  mov     edx, 30h ; '0'
0x180054261  mov     [rsp+130h+lpvOutBuffer], rsi
0x180054266  mov     ecx, 403h
0x18005426b  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x180054272  mov     r9, rdi
0x180054275  call    WPP_SF_qq
0x18005427a  jmp     loc_180053FDA
0x18005427f  test    byte ptr cs:xmmword_1800AD720, 8
0x180054286  jz      loc_18005416D
0x18005428c  mov     edx, 31h ; '1'
0x180054291  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x180054298  mov     ecx, 403h
0x18005429d  call    WPP_SF_d
0x1800542a2  jmp     loc_18005416D
0x1800542a7  mov     ecx, 7
0x1800542ac  int     29h; Win8: RtlFailFast(ecx)
0x1800542ae  mov     ebx, 54Fh
0x1800542b3  jmp     loc_1800541D5
0x1800542b8  mov     rcx, [rdi+2C8h]; pio
0x1800542bf  call    cs:__imp_CancelThreadpoolIo
0x1800542c6  nop     dword ptr [rax+rax+00h]
0x1800542cb  cmp     byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 0
0x1800542d2  jge     loc_1800541E1
0x1800542d8  mov     eax, [rsi+0D4h]
0x1800542de  lea     rdx, [rsi+10h]
0x1800542e2  mov     r9, [rdi+2C0h]
0x1800542e9  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x1800542f0  mov     r8, [rdi+8]
0x1800542f4  mov     [rsp+130h+var_E8], 0
0x1800542fd  mov     dword ptr [rsp+130h+lpCompletionRoutine], ebx
0x180054301  mov     [rsp+130h+lpOverlapped], rax
0x180054306  mov     [rsp+130h+lpcbBytesReturned], rdx
0x18005430b  lea     rdx, NetSocketConnectFailed
0x180054312  mov     qword ptr [rsp+130h+cbOutBuffer], 0
0x18005431b  mov     dword ptr [rsp+130h+lpvOutBuffer], 0
0x180054323  call    McTemplateU0pxqzr2pxqx_EventWriteTransfer
0x180054328  jmp     loc_1800541E1
0x18005432d  mov     edx, 32h ; '2'
0x180054332  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x180054339  mov     ecx, 403h
0x18005433e  mov     r9d, ebx
0x180054341  call    WPP_SF_d
0x180054346  jmp     loc_1800541FD
```
