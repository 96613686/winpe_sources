# WapHttp3Connect

- ea: `0x18007bd28`
- end: `0x18007bf1b`
- name: `WapHttp3Connect`
- size: `499`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007bf30`
- `0x18007e4dc`

## callees

- `0x180054354`
- `0x180068018`
- `0x1800722f0`
- `0x180072c70`
- `0x18007b7f0`
- `0x18007bd28`
- `0x18007c468`
- `0x180093eb4`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007bd9e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007bd9e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007beed`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007beed`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18007be34`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18007be34`

## pseudocode

```c
__int64 __fastcall WapHttp3Connect(LARGE_INTEGER *a1, __int64 a2)
{
  _OWORD *v4; // rsi
  unsigned int started; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // esi
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-59h] BYREF
  _OWORD v11[8]; // [rsp+60h] [rbp-49h] BYREF

  memset_0(v11, 0, sizeof(v11));
  v4 = (_OWORD *)(*(_QWORD *)(a1[35].QuadPart + 32) + ((unsigned __int64)*(unsigned int *)(a2 + 216) << 7));
  (*(void (__fastcall **)(LARGE_INTEGER, _QWORD, _OWORD *, __int64))(a1[2].QuadPart + 88))(a1[1], 0, v4, 128);
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  a1[131] = PerformanceCount;
  if ( *(_DWORD *)(a2 + 228) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 4));
    WaSetTwTimer(a2 + 136, *(unsigned int *)(a2 + 228), WapHttp3ConnectTimeoutRoutine, a2);
  }
  v11[0] = *v4;
  v11[1] = v4[1];
  v11[2] = v4[2];
  v11[3] = v4[3];
  v11[4] = v4[4];
  v11[5] = v4[5];
  v11[6] = v4[6];
  v11[7] = v4[7];
  WapHttp3ConnectionConnectStartTrace(a1, v11, a2);
  StartThreadpoolIo(*(PTP_IO *)(a1[11].QuadPart + 8));
  started = WaStartHttpApiConnection(
              *(_QWORD *)a1[11].QuadPart,
              a1[10].QuadPart,
              (unsigned int)v11,
              (int)a1 + 904,
              a2 + 32);
  v8 = started;
  if ( started != 997 )
  {
    if ( (xmmword_1800AD720 & 8) != 0 )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qiD)(
        (LARGE_INTEGER)a1[10].QuadPart,
        v6,
        v7,
        (LARGE_INTEGER)a1[1].QuadPart,
        (LARGE_INTEGER)a1[10].QuadPart,
        started);
    if ( (Microsoft_Windows_WebIOEnableBits & 0x8000) != 0 )
      McTemplateU0pxqzr2pxqx_EventWriteTransfer(
        (unsigned int)&WEB_ETW_PROVIDER_ID_Context,
        (unsigned int)NetSocketConnectFailed,
        a1[1].QuadPart,
        0,
        0,
        0,
        a2 + 24,
        *(_DWORD *)(a2 + 220),
        v8,
        a1[10].QuadPart);
    CancelThreadpoolIo(*(PTP_IO *)(a1[11].QuadPart + 8));
  }
  return v8;
}

```

## disassembly

```asm
0x18007bd28  mov     [rsp-8+arg_10], rbx
0x18007bd2d  push    rbp
0x18007bd2e  push    rsi
0x18007bd2f  push    rdi
0x18007bd30  lea     rbp, [rsp-47h]
0x18007bd35  sub     rsp, 0F0h
0x18007bd3c  mov     rax, cs:__security_cookie
0x18007bd43  xor     rax, rsp
0x18007bd46  mov     [rbp+57h+var_20], rax
0x18007bd4a  mov     rbx, rdx
0x18007bd4d  mov     rdi, rcx
0x18007bd50  xor     edx, edx; Val
0x18007bd52  lea     rcx, [rbp+57h+var_A0]; void *
0x18007bd56  mov     r8d, 80h; Size
0x18007bd5c  call    memset_0
0x18007bd61  mov     rax, [rdi+118h]
0x18007bd68  mov     r9d, 80h
0x18007bd6e  mov     esi, [rbx+0D8h]
0x18007bd74  xor     edx, edx
0x18007bd76  mov     rcx, [rdi+8]
0x18007bd7a  shl     rsi, 7
0x18007bd7e  add     rsi, [rax+20h]
0x18007bd82  mov     rax, [rdi+10h]
0x18007bd86  mov     r8, rsi
0x18007bd89  mov     rax, [rax+58h]
0x18007bd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bd92  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18007bd96  mov     qword ptr [rbp+57h+PerformanceCount], 0
0x18007bd9e  call    cs:__imp_QueryPerformanceCounter
0x18007bda5  nop     dword ptr [rax+rax+00h]
0x18007bdaa  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x18007bdae  mov     [rdi+418h], rax
0x18007bdb5  cmp     dword ptr [rbx+0E4h], 0
0x18007bdbc  jz      short loc_18007BDDE
0x18007bdbe  lock inc dword ptr [rbx+4]
0x18007bdc2  mov     edx, [rbx+0E4h]
0x18007bdc8  lea     rcx, [rbx+88h]
0x18007bdcf  mov     r9, rbx
0x18007bdd2  lea     r8, WapHttp3ConnectTimeoutRoutine
0x18007bdd9  call    WaSetTwTimer
0x18007bdde  movups  xmm0, xmmword ptr [rsi]
0x18007bde1  mov     r8, rbx
0x18007bde4  lea     rdx, [rbp+57h+var_A0]
0x18007bde8  mov     rcx, rdi
0x18007bdeb  movaps  [rbp+57h+var_A0], xmm0
0x18007bdef  movups  xmm1, xmmword ptr [rsi+10h]
0x18007bdf3  movaps  [rbp+57h+var_90], xmm1
0x18007bdf7  movups  xmm0, xmmword ptr [rsi+20h]
0x18007bdfb  movaps  [rbp+57h+var_80], xmm0
0x18007bdff  movups  xmm1, xmmword ptr [rsi+30h]
0x18007be03  movaps  [rbp+57h+var_70], xmm1
0x18007be07  movups  xmm0, xmmword ptr [rsi+40h]
0x18007be0b  movaps  [rbp+57h+var_60], xmm0
0x18007be0f  movups  xmm1, xmmword ptr [rsi+50h]
0x18007be13  movaps  [rbp+57h+var_50], xmm1
0x18007be17  movups  xmm0, xmmword ptr [rsi+60h]
0x18007be1b  movaps  [rbp+57h+var_40], xmm0
0x18007be1f  movups  xmm1, xmmword ptr [rsi+70h]
0x18007be23  movaps  [rbp+57h+var_30], xmm1
0x18007be27  call    WapHttp3ConnectionConnectStartTrace
0x18007be2c  mov     rcx, [rdi+58h]
0x18007be30  mov     rcx, [rcx+8]; pio
0x18007be34  call    cs:__imp_StartThreadpoolIo
0x18007be3b  nop     dword ptr [rax+rax+00h]
0x18007be40  mov     rcx, [rdi+58h]
0x18007be44  lea     rax, [rbx+20h]
0x18007be48  mov     rdx, [rdi+50h]
0x18007be4c  lea     r9, [rdi+388h]
0x18007be53  lea     r8, [rbp+57h+var_A0]
0x18007be57  mov     [rsp+100h+var_E0], rax
0x18007be5c  mov     rcx, [rcx]
0x18007be5f  call    WaStartHttpApiConnection
0x18007be64  mov     esi, eax
0x18007be66  cmp     eax, 3E5h
0x18007be6b  jz      loc_18007BEF9
0x18007be71  test    byte ptr cs:xmmword_1800AD720, 8
0x18007be78  jz      short loc_18007BE90
0x18007be7a  mov     rcx, [rdi+50h]
0x18007be7e  mov     r9, [rdi+8]
0x18007be82  mov     dword ptr [rsp+100h+var_D8], eax
0x18007be86  mov     [rsp+100h+var_E0], rcx
0x18007be8b  call    WPP_SF_qiD
0x18007be90  cmp     byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 0
0x18007be97  jge     short loc_18007BEE5
0x18007be99  mov     ecx, [rbx+0DCh]
0x18007be9f  lea     rdx, [rbx+18h]
0x18007bea3  mov     rax, [rdi+50h]
0x18007bea7  xor     r9d, r9d
0x18007beaa  mov     r8, [rdi+8]
0x18007beae  mov     [rsp+100h+var_B8], rax
0x18007beb3  mov     [rsp+100h+var_C0], esi
0x18007beb7  mov     [rsp+100h+var_C8], rcx
0x18007bebc  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x18007bec3  mov     [rsp+100h+var_D0], rdx
0x18007bec8  lea     rdx, NetSocketConnectFailed
0x18007becf  mov     [rsp+100h+var_D8], 0
0x18007bed8  mov     dword ptr [rsp+100h+var_E0], 0
0x18007bee0  call    McTemplateU0pxqzr2pxqx_EventWriteTransfer
0x18007bee5  mov     rcx, [rdi+58h]
0x18007bee9  mov     rcx, [rcx+8]; pio
0x18007beed  call    cs:__imp_CancelThreadpoolIo
0x18007bef4  nop     dword ptr [rax+rax+00h]
0x18007bef9  mov     eax, esi
0x18007befb  mov     rcx, [rbp+57h+var_20]
0x18007beff  xor     rcx, rsp; StackCookie
0x18007bf02  call    __security_check_cookie
0x18007bf07  mov     rbx, [rsp+100h+arg_10]
0x18007bf0f  add     rsp, 0F0h
0x18007bf16  pop     rdi
0x18007bf17  pop     rsi
0x18007bf18  pop     rbp
0x18007bf19  retn
```
