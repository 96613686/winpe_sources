# WaHttp3StreamSendHeadersRequest

- ea: `0x180064310`
- end: `0x1800645d8`
- name: `WaHttp3StreamSendHeadersRequest`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018370`

## callees

- `0x18005fd88`
- `0x180064310`
- `0x18007b448`
- `0x18007fd90`
- `0x180080394`
- `0x18008059c`
- `0x180092564`
- `0x180094cc8`
- `0x1800971ec`
- `0x180097810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800643c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800643c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006445b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800644a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006445b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800644a0`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180064588`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180064588`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180064535`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180064535`

## pseudocode

```c
__int64 __fastcall WaHttp3StreamSendHeadersRequest(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        char a5,
        int a6,
        __int64 a7)
{
  __int64 *v10; // rdi
  unsigned int v11; // ebx
  unsigned __int64 v12; // r9
  __int64 v13; // rdi
  int v14; // ecx
  __int64 v15; // r9
  __int64 IoContext; // rax
  __int64 v17; // rsi
  __int64 v18; // r9

  v10 = (__int64 *)(a1 + 72);
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_qqqddl(a1, a2, a3, a1, *v10, a2);
  if ( a3 > 1 )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
      WPP_SF_(538, 188, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids);
LABEL_6:
    v11 = 50;
    goto LABEL_25;
  }
  v12 = *(_QWORD *)(a2 + 16);
  if ( v12 > 0xFFFFFFFF )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
      WPP_SF_q(538, 189, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v12);
    goto LABEL_6;
  }
  v13 = *v10;
  EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 48));
  if ( *(_BYTE *)(v13 + 88) )
  {
    v11 = *(_DWORD *)(v13 + 92);
LABEL_18:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 48));
    goto LABEL_25;
  }
  v15 = *(unsigned int *)(v13 + 264);
  if ( (_DWORD)v15 )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
      WPP_SF_d(538, 190, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v15);
    v11 = 1359;
    goto LABEL_18;
  }
  *(_DWORD *)(v13 + 264) = 1;
  IoContext = WapHttpApiAllocateIoContext(
                v14,
                0,
                v13,
                2,
                (__int64)WapHttp3StreamSendHeadersCompletionRoutine,
                (__int64)WapSendHttpRequestEntityCompletion,
                a7);
  v17 = IoContext;
  if ( !IoContext )
  {
    v11 = 8;
    goto LABEL_18;
  }
  *(_QWORD *)(IoContext + 136) = *(_QWORD *)(a2 + 8);
  *(_DWORD *)(IoContext + 144) = *(_DWORD *)(a2 + 16);
  *(_BYTE *)(IoContext + 148) = a5;
  *(_QWORD *)(v13 + 272) = IoContext;
  if ( a5 )
    *(_DWORD *)(v13 + 264) = 2;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 48));
  if ( (Microsoft_Windows_WebIOEnableBits & 0x100) != 0 )
    McTemplateU0ppxppqxxxtt_EventWriteTransfer(
      *(_DWORD *)(v17 + 144),
      (unsigned int)NetSocketSendEntity,
      *(_QWORD *)(v13 + 8),
      0,
      0,
      *(_QWORD *)(v17 + 136),
      v17 + 24,
      0,
      0,
      *(_QWORD *)(v13 + 24),
      *(_DWORD *)(v17 + 144),
      *(_BYTE *)(v17 + 148),
      1);
  WapHttp3StreamUpdateTimerOnRequest(v13, v13 + 184);
  StartThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(v13 + 40) + 8LL));
  v11 = WaHttpApiStreamSendHeaders(
          **(_QWORD **)(v13 + 40),
          *(_QWORD *)(v13 + 24),
          *(_QWORD *)(v17 + 136),
          *(_DWORD *)(v17 + 144),
          a4,
          *(_BYTE *)(v17 + 148),
          v17 + 32);
  if ( v11 != 997 )
  {
    CancelThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(v13 + 40) + 8LL));
    LOBYTE(v18) = 1;
    v11 = WapHttp3StreamSendHeadersCommonCompletionRoutine(v17, v11, 0, v18);
  }
LABEL_25:
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 191, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180064310  mov     rax, rsp
0x180064313  push    rbx
0x180064314  push    rbp
0x180064315  push    rsi
0x180064316  push    rdi
0x180064317  push    r14
0x180064319  push    r15
0x18006431b  sub     rsp, 78h
0x18006431f  mov     r15d, r9d
0x180064322  mov     esi, r8d
0x180064325  mov     rbx, rdx
0x180064328  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18006432f  lea     rdi, [rcx+48h]
0x180064333  movzx   r14d, [rsp+0A8h+arg_20]
0x18006433c  jz      short loc_18006435E
0x18006433e  mov     [rax-68h], r14d
0x180064342  mov     [rax-70h], r9d
0x180064346  mov     r9, rcx
0x180064349  mov     [rax-78h], r8d
0x18006434d  mov     [rax-80h], rdx
0x180064351  mov     rax, [rdi]
0x180064354  mov     [rsp+0A8h+var_88], rax
0x180064359  call    WPP_SF_qqqddl
0x18006435e  cmp     esi, 1
0x180064361  jbe     short loc_18006438C
0x180064363  test    byte ptr cs:xmmword_1800AD710+3, 4
0x18006436a  jz      short loc_180064382
0x18006436c  mov     edx, 0BCh
0x180064371  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x180064378  mov     ecx, 21Ah
0x18006437d  call    WPP_SF_
0x180064382  mov     ebx, 32h ; '2'
0x180064387  jmp     loc_1800645A6
0x18006438c  mov     r9, [rbx+10h]
0x180064390  mov     eax, 0FFFFFFFFh
0x180064395  cmp     r9, rax
0x180064398  jbe     short loc_1800643BB
0x18006439a  test    byte ptr cs:xmmword_1800AD710+3, 4
0x1800643a1  jz      short loc_180064382
0x1800643a3  mov     edx, 0BDh
0x1800643a8  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x1800643af  mov     ecx, 21Ah
0x1800643b4  call    WPP_SF_q
0x1800643b9  jmp     short loc_180064382
0x1800643bb  mov     rdi, [rdi]
0x1800643be  lea     rbp, [rdi+30h]
0x1800643c2  mov     rcx, rbp; lpCriticalSection
0x1800643c5  call    cs:__imp_EnterCriticalSection
0x1800643cc  nop     dword ptr [rax+rax+00h]
0x1800643d1  cmp     byte ptr [rdi+58h], 0
0x1800643d5  jz      short loc_1800643DC
0x1800643d7  mov     ebx, [rdi+5Ch]
0x1800643da  jmp     short loc_180064458
0x1800643dc  mov     r9d, [rdi+108h]
0x1800643e3  test    r9d, r9d
0x1800643e6  jz      short loc_18006440E
0x1800643e8  test    byte ptr cs:xmmword_1800AD710+3, 4
0x1800643ef  jz      short loc_180064407
0x1800643f1  mov     edx, 0BEh
0x1800643f6  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x1800643fd  mov     ecx, 21Ah
0x180064402  call    WPP_SF_d
0x180064407  mov     ebx, 54Fh
0x18006440c  jmp     short loc_180064458
0x18006440e  mov     rax, [rsp+0A8h+arg_30]
0x180064416  mov     r9d, 2
0x18006441c  mov     [rsp+0A8h+var_78], rax
0x180064421  mov     r8, rdi
0x180064424  lea     rax, WapSendHttpRequestEntityCompletion
0x18006442b  mov     dword ptr [rdi+108h], 1
0x180064435  mov     [rsp+0A8h+var_80], rax
0x18006443a  xor     edx, edx
0x18006443c  lea     rax, WapHttp3StreamSendHeadersCompletionRoutine
0x180064443  mov     [rsp+0A8h+var_88], rax
0x180064448  call    WapHttpApiAllocateIoContext
0x18006444d  mov     rsi, rax
0x180064450  test    rax, rax
0x180064453  jnz     short loc_18006446C
0x180064455  lea     ebx, [rax+8]
0x180064458  mov     rcx, rbp; lpCriticalSection
0x18006445b  call    cs:__imp_LeaveCriticalSection
0x180064462  nop     dword ptr [rax+rax+00h]
0x180064467  jmp     loc_1800645A6
0x18006446c  mov     rax, [rbx+8]
0x180064470  mov     [rsi+88h], rax
0x180064477  mov     eax, [rbx+10h]
0x18006447a  mov     [rsi+90h], eax
0x180064480  mov     [rsi+94h], r14b
0x180064487  mov     [rdi+110h], rsi
0x18006448e  test    r14b, r14b
0x180064491  jz      short loc_18006449D
0x180064493  mov     dword ptr [rdi+108h], 2
0x18006449d  mov     rcx, rbp; lpCriticalSection
0x1800644a0  call    cs:__imp_LeaveCriticalSection
0x1800644a7  nop     dword ptr [rax+rax+00h]
0x1800644ac  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 1
0x1800644b3  jz      short loc_18006451E
0x1800644b5  movzx   eax, byte ptr [rsi+94h]
0x1800644bc  lea     rdx, [rsi+18h]
0x1800644c0  mov     ecx, [rsi+90h]
0x1800644c6  xor     r9d, r9d
0x1800644c9  mov     r8, [rdi+8]
0x1800644cd  mov     [rsp+0A8h+var_48], 1
0x1800644d5  mov     [rsp+0A8h+var_50], eax
0x1800644d9  mov     rax, [rdi+18h]
0x1800644dd  mov     [rsp+0A8h+var_58], rcx
0x1800644e2  mov     [rsp+0A8h+var_60], rax
0x1800644e7  mov     rax, [rsi+88h]
0x1800644ee  mov     [rsp+0A8h+var_68], 0
0x1800644f7  mov     [rsp+0A8h+var_70], 0
0x1800644ff  mov     [rsp+0A8h+var_78], rdx
0x180064504  lea     rdx, NetSocketSendEntity
0x18006450b  mov     [rsp+0A8h+var_80], rax
0x180064510  mov     [rsp+0A8h+var_88], 0
0x180064519  call    McTemplateU0ppxppqxxxtt_EventWriteTransfer
0x18006451e  lea     rdx, [rdi+0B8h]
0x180064525  mov     rcx, rdi
0x180064528  call    WapHttp3StreamUpdateTimerOnRequest
0x18006452d  mov     rcx, [rdi+28h]
0x180064531  mov     rcx, [rcx+8]; pio
0x180064535  call    cs:__imp_StartThreadpoolIo
0x18006453c  nop     dword ptr [rax+rax+00h]
0x180064541  mov     rcx, [rdi+28h]
0x180064545  lea     rax, [rsi+20h]
0x180064549  mov     r9d, [rsi+90h]
0x180064550  mov     r8, [rsi+88h]
0x180064557  mov     rdx, [rdi+18h]
0x18006455b  mov     rcx, [rcx]
0x18006455e  mov     [rsp+0A8h+var_78], rax
0x180064563  mov     al, [rsi+94h]
0x180064569  mov     byte ptr [rsp+0A8h+var_80], al
0x18006456d  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180064572  call    WaHttpApiStreamSendHeaders
0x180064577  mov     ebx, eax
0x180064579  cmp     eax, 3E5h
0x18006457e  jz      short loc_1800645A6
0x180064580  mov     rcx, [rdi+28h]
0x180064584  mov     rcx, [rcx+8]; pio
0x180064588  call    cs:__imp_CancelThreadpoolIo
0x18006458f  nop     dword ptr [rax+rax+00h]
0x180064594  mov     r9b, 1
0x180064597  xor     r8d, r8d
0x18006459a  mov     edx, ebx
0x18006459c  mov     rcx, rsi
0x18006459f  call    WapHttp3StreamSendHeadersCommonCompletionRoutine
0x1800645a4  mov     ebx, eax
0x1800645a6  test    byte ptr cs:xmmword_1800AD720+3, 4
0x1800645ad  jz      short loc_1800645C8
0x1800645af  mov     edx, 0BFh
0x1800645b4  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x1800645bb  mov     ecx, 41Ah
0x1800645c0  mov     r9d, ebx
0x1800645c3  call    WPP_SF_d
0x1800645c8  mov     eax, ebx
0x1800645ca  add     rsp, 78h
0x1800645ce  pop     r15
0x1800645d0  pop     r14
0x1800645d2  pop     rdi
0x1800645d3  pop     rsi
0x1800645d4  pop     rbp
0x1800645d5  pop     rbx
0x1800645d6  retn
```
