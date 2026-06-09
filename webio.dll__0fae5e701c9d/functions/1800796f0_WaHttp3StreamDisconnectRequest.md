# WaHttp3StreamDisconnectRequest

- ea: `0x1800796f0`
- end: `0x1800798e6`
- name: `WaHttp3StreamDisconnectRequest`
- size: `502`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800796f0`
- `0x18007b14c`
- `0x18007f1b0`
- `0x180080394`
- `0x18008059c`
- `0x1800923bc`
- `0x180092564`
- `0x1800971ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007973c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007973c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007982e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079846`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007982e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079846`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007989a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007989a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180079869`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180079869`

## pseudocode

```c
__int64 __fastcall WaHttp3StreamDisconnectRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 *v5; // rdi
  __int64 v6; // rdi
  int v7; // ecx
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 IoContext; // rax
  __int64 v12; // rsi

  v5 = (__int64 *)(a1 + 72);
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_qq(1050, 203, (unsigned int)WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, a1, *v5);
  v6 = *v5;
  EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 48));
  if ( *(_BYTE *)(v6 + 88) )
  {
    v8 = *(_DWORD *)(v6 + 92);
LABEL_22:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 48));
    goto LABEL_25;
  }
  v9 = *(unsigned int *)(v6 + 264);
  if ( !(_DWORD)v9 )
  {
    if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
      WPP_SF_(1050, 204, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids);
    v8 = 995;
    goto LABEL_22;
  }
  if ( (_DWORD)v9 != 2 )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
      WPP_SF_d(538, 205, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v9);
    goto LABEL_12;
  }
  if ( *(_QWORD *)(v6 + 280) )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) == 0 )
    {
LABEL_12:
      v8 = 1359;
      goto LABEL_22;
    }
    v10 = 206;
LABEL_16:
    WPP_SF_(538, v10, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids);
    goto LABEL_12;
  }
  if ( *(_QWORD *)(v6 + 288) )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) == 0 )
      goto LABEL_12;
    v10 = 207;
    goto LABEL_16;
  }
  *(_DWORD *)(v6 + 264) = 3;
  IoContext = WapHttpApiAllocateIoContext(v7, 0, v6, 5, (__int64)WapHttp3StreamDisconnectCompletionRoutine, a2, a3);
  v12 = IoContext;
  if ( !IoContext )
  {
    v8 = 8;
    goto LABEL_22;
  }
  *(_QWORD *)(v6 + 288) = IoContext;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 48));
  WapHttp3StreamUpdateTimerOnRequest(v6, v6 + 184);
  StartThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(v6 + 40) + 8LL));
  v8 = WaHttpApiStreamNotifyDisconnect(**(_QWORD **)(v6 + 40), *(_QWORD *)(v6 + 24), v12 + 32);
  if ( v8 != 997 )
  {
    CancelThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(v6 + 40) + 8LL));
    *(_BYTE *)(v12 + 132) = 1;
    WapHttp3StreamDisconnectCompletionRoutine(v12, v8, 0);
  }
LABEL_25:
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 208, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800796f0  push    rbx
0x1800796f2  push    rbp
0x1800796f3  push    rsi
0x1800796f4  push    rdi
0x1800796f5  push    r15
0x1800796f7  sub     rsp, 40h
0x1800796fb  mov     rbx, r8
0x1800796fe  mov     rsi, rdx
0x180079701  mov     r9, rcx
0x180079704  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007970b  lea     rdi, [rcx+48h]
0x18007970f  lea     r15, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x180079716  jz      short loc_180079732
0x180079718  mov     rax, [rdi]
0x18007971b  mov     edx, 0CBh
0x180079720  mov     ecx, 41Ah
0x180079725  mov     [rsp+68h+var_48], rax
0x18007972a  mov     r8, r15
0x18007972d  call    WPP_SF_qq
0x180079732  mov     rdi, [rdi]
0x180079735  lea     rbp, [rdi+30h]
0x180079739  mov     rcx, rbp; lpCriticalSection
0x18007973c  call    cs:__imp_EnterCriticalSection
0x180079743  nop     dword ptr [rax+rax+00h]
0x180079748  cmp     byte ptr [rdi+58h], 0
0x18007974c  jz      short loc_180079756
0x18007974e  mov     ebx, [rdi+5Ch]
0x180079751  jmp     loc_18007982B
0x180079756  mov     r9d, [rdi+108h]
0x18007975d  test    r9d, r9d
0x180079760  jnz     short loc_180079787
0x180079762  test    byte ptr cs:xmmword_1800AD720+3, 4
0x180079769  jz      short loc_18007977D
0x18007976b  mov     edx, 0CCh
0x180079770  mov     ecx, 41Ah
0x180079775  mov     r8, r15
0x180079778  call    WPP_SF_
0x18007977d  mov     ebx, 3E3h
0x180079782  jmp     loc_18007982B
0x180079787  cmp     r9d, 2
0x18007978b  jz      short loc_1800797AF
0x18007978d  test    byte ptr cs:xmmword_1800AD710+3, 4
0x180079794  jz      short loc_1800797A8
0x180079796  mov     edx, 0CDh
0x18007979b  mov     ecx, 21Ah
0x1800797a0  mov     r8, r15
0x1800797a3  call    WPP_SF_d
0x1800797a8  mov     ebx, 54Fh
0x1800797ad  jmp     short loc_18007982B
0x1800797af  cmp     qword ptr [rdi+118h], 0
0x1800797b7  jz      short loc_1800797D6
0x1800797b9  test    byte ptr cs:xmmword_1800AD710+3, 4
0x1800797c0  jz      short loc_1800797A8
0x1800797c2  mov     edx, 0CEh
0x1800797c7  mov     ecx, 21Ah
0x1800797cc  mov     r8, r15
0x1800797cf  call    WPP_SF_
0x1800797d4  jmp     short loc_1800797A8
0x1800797d6  cmp     qword ptr [rdi+120h], 0
0x1800797de  jz      short loc_1800797F0
0x1800797e0  test    byte ptr cs:xmmword_1800AD710+3, 4
0x1800797e7  jz      short loc_1800797A8
0x1800797e9  mov     edx, 0CFh
0x1800797ee  jmp     short loc_1800797C7
0x1800797f0  mov     [rsp+68h+var_38], rbx
0x1800797f5  lea     rax, WapHttp3StreamDisconnectCompletionRoutine
0x1800797fc  mov     [rsp+68h+var_40], rsi
0x180079801  mov     r9d, 5
0x180079807  mov     r8, rdi
0x18007980a  mov     [rsp+68h+var_48], rax
0x18007980f  xor     edx, edx
0x180079811  mov     dword ptr [rdi+108h], 3
0x18007981b  call    WapHttpApiAllocateIoContext
0x180079820  mov     rsi, rax
0x180079823  test    rax, rax
0x180079826  jnz     short loc_18007983C
0x180079828  lea     ebx, [rax+8]
0x18007982b  mov     rcx, rbp; lpCriticalSection
0x18007982e  call    cs:__imp_LeaveCriticalSection
0x180079835  nop     dword ptr [rax+rax+00h]
0x18007983a  jmp     short loc_1800798BA
0x18007983c  mov     rcx, rbp; lpCriticalSection
0x18007983f  mov     [rdi+120h], rsi
0x180079846  call    cs:__imp_LeaveCriticalSection
0x18007984d  nop     dword ptr [rax+rax+00h]
0x180079852  lea     rdx, [rdi+0B8h]
0x180079859  mov     rcx, rdi
0x18007985c  call    WapHttp3StreamUpdateTimerOnRequest
0x180079861  mov     rcx, [rdi+28h]
0x180079865  mov     rcx, [rcx+8]; pio
0x180079869  call    cs:__imp_StartThreadpoolIo
0x180079870  nop     dword ptr [rax+rax+00h]
0x180079875  mov     rcx, [rdi+28h]
0x180079879  lea     r8, [rsi+20h]
0x18007987d  mov     rdx, [rdi+18h]
0x180079881  mov     rcx, [rcx]
0x180079884  call    WaHttpApiStreamNotifyDisconnect
0x180079889  mov     ebx, eax
0x18007988b  cmp     eax, 3E5h
0x180079890  jz      short loc_1800798BA
0x180079892  mov     rcx, [rdi+28h]
0x180079896  mov     rcx, [rcx+8]; pio
0x18007989a  call    cs:__imp_CancelThreadpoolIo
0x1800798a1  nop     dword ptr [rax+rax+00h]
0x1800798a6  xor     r8d, r8d
0x1800798a9  mov     byte ptr [rsi+84h], 1
0x1800798b0  mov     edx, ebx
0x1800798b2  mov     rcx, rsi
0x1800798b5  call    WapHttp3StreamDisconnectCompletionRoutine
0x1800798ba  test    byte ptr cs:xmmword_1800AD720+3, 4
0x1800798c1  jz      short loc_1800798D8
0x1800798c3  mov     edx, 0D0h
0x1800798c8  mov     ecx, 41Ah
0x1800798cd  mov     r9d, ebx
0x1800798d0  mov     r8, r15
0x1800798d3  call    WPP_SF_d
0x1800798d8  mov     eax, ebx
0x1800798da  add     rsp, 40h
0x1800798de  pop     r15
0x1800798e0  pop     rdi
0x1800798e1  pop     rsi
0x1800798e2  pop     rbp
0x1800798e3  pop     rbx
0x1800798e4  retn
```
