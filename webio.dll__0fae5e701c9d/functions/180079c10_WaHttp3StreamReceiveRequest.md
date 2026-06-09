# WaHttp3StreamReceiveRequest

- ea: `0x180079c10`
- end: `0x18007a0b9`
- name: `WaHttp3StreamReceiveRequest`
- size: `1193`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _QWORD *, __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180013820`
- `0x1800391c0`
- `0x18005fd88`
- `0x1800722f0`
- `0x180079c10`
- `0x18007b1dc`
- `0x18007b2ac`
- `0x18007f540`
- `0x18007f868`
- `0x180080394`
- `0x18008059c`
- `0x180091678`
- `0x180092564`
- `0x1800971ec`
- `0x180097810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079cc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079cc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079e42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079e8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079e42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079e8f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180079f70`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007a062`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180079f70`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007a062`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180079f18`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18007a012`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180079f18`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18007a012`

## pseudocode

```c
__int64 __fastcall WaHttp3StreamReceiveRequest(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6)
{
  unsigned int v8; // ebx
  unsigned __int64 v9; // r9
  __int64 v10; // rdi
  __int64 v11; // r14
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  size_t v15; // r8
  size_t v16; // rax
  __int64 v17; // rsi
  int v18; // eax
  __int64 Heap; // rax
  int v20; // ecx
  __int64 IoContext; // rsi
  char v22; // bl
  _DWORD *v23; // rbx
  __int64 v25; // [rsp+70h] [rbp-58h] BYREF
  unsigned int v26; // [rsp+78h] [rbp-50h] BYREF

  v26 = 0;
  *a4 = 0;
  if ( a3 > 1 )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
      WPP_SF_(538, 198, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids);
    return 50;
  }
  v9 = *(_QWORD *)(a2 + 16);
  if ( v9 > 0xFFFFFFFF )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
      WPP_SF_q(538, 199, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v9);
    return 50;
  }
  v10 = *(_QWORD *)(a1 + 72);
  v11 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
  if ( *(_BYTE *)(v10 + 88) )
  {
    v8 = *(_DWORD *)(v10 + 92);
    goto LABEL_31;
  }
  if ( *(_QWORD *)(v10 + 304) )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
      WPP_SF_(538, 200, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids);
    goto LABEL_13;
  }
  v13 = *(_DWORD *)(v10 + 336);
  if ( v13 )
  {
    v14 = *(unsigned int *)(v10 + 340);
    v8 = 0;
    v15 = *(_QWORD *)(a2 + 16);
    v16 = (unsigned int)(v13 - v14);
    if ( v15 >= v16 )
      v15 = (unsigned int)v16;
    v17 = (unsigned int)v15;
    memcpy_0(*(void **)(a2 + 8), (const void *)(*(_QWORD *)(v10 + 328) + v14), v15);
    *(_DWORD *)(v10 + 340) += v17;
    if ( *(_DWORD *)(v10 + 336) == *(_DWORD *)(v10 + 340) )
    {
      v11 = *(_QWORD *)(v10 + 328);
      *(_QWORD *)(v10 + 328) = 0;
      *(_QWORD *)(v10 + 336) = 0;
    }
    if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
      WPP_SF_d(1050, 201, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, (unsigned int)v17);
    *a4 = v17;
    goto LABEL_31;
  }
  v18 = *(_DWORD *)(v10 + 296);
  if ( v18 == 3 )
  {
    v8 = 0;
    goto LABEL_31;
  }
  if ( !v18 )
  {
    if ( *(_QWORD *)(v10 + 312) )
    {
LABEL_13:
      v8 = 1359;
      goto LABEL_31;
    }
    Heap = WxAllocateHeapEx(v12, 0x2000);
    *(_QWORD *)(v10 + 312) = Heap;
    if ( Heap )
    {
      *(_DWORD *)(v10 + 320) = 0x2000;
      IoContext = WapHttpApiAllocateIoContext(
                    v20,
                    0,
                    v10,
                    3,
                    (__int64)WapHttp3StreamReceiveHeadersCompletionRoutine,
                    a5,
                    a6);
      if ( IoContext )
      {
        v22 = 1;
        goto LABEL_34;
      }
    }
LABEL_30:
    v8 = 8;
LABEL_31:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
    if ( v11 )
    {
      v25 = v11;
      WxFreeHeapEx(&v25);
    }
    return v8;
  }
  IoContext = WapHttpApiAllocateIoContext(v12, 0, v10, 3, (__int64)WapHttp3StreamReceiveCompletionRoutine, a5, a6);
  if ( !IoContext )
    goto LABEL_30;
  v22 = 0;
LABEL_34:
  *(_QWORD *)(IoContext + 136) = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(IoContext + 144) = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(v10 + 304) = IoContext;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
  if ( v22 )
  {
    if ( (Microsoft_Windows_WebIOEnableBits & 0x2000) != 0 )
      McTemplateU0ppxppqxxxtt_EventWriteTransfer(
        IoContext + 24,
        (unsigned int)NetSocketRecvEntity,
        *(_QWORD *)(v10 + 8),
        0,
        0,
        *(_QWORD *)(v10 + 312),
        IoContext + 24,
        0,
        0,
        *(_QWORD *)(v10 + 24),
        *(_DWORD *)(v10 + 320),
        0,
        1);
    WapHttp3StreamUpdateTimerOnRequest(v10, v10 + 104);
    StartThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(v10 + 40) + 8LL));
    v8 = WaHttpApiStreamReceiveHeaders(
           **(_QWORD **)(v10 + 40),
           *(_QWORD *)(v10 + 24),
           0,
           *(_QWORD *)(v10 + 312),
           *(_DWORD *)(v10 + 320),
           IoContext + 32,
           (__int64)&v26);
    if ( v8 != 997 )
    {
      CancelThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(v10 + 40) + 8LL));
      *(_BYTE *)(IoContext + 132) = 1;
      return (unsigned int)WapHttp3StreamReceiveHeadersCommonCompletionRoutine(IoContext, v8, v26, a4);
    }
  }
  else
  {
    v23 = (_DWORD *)(IoContext + 144);
    if ( (Microsoft_Windows_WebIOEnableBits & 0x2000) != 0 )
      McTemplateU0ppxppqxxxtt_EventWriteTransfer(
        IoContext + 24,
        (unsigned int)NetSocketRecvEntity,
        *(_QWORD *)(v10 + 8),
        0,
        0,
        *(_QWORD *)(IoContext + 136),
        IoContext + 24,
        0,
        0,
        *(_QWORD *)(v10 + 24),
        *(_QWORD *)v23,
        0,
        0);
    WapHttp3StreamUpdateTimerOnRequest(v10, v10 + 104);
    StartThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(v10 + 40) + 8LL));
    v8 = WaHttpApiStreamReceiveEntityBody(
           **(_QWORD **)(v10 + 40),
           *(_QWORD *)(v10 + 24),
           0,
           *(_QWORD *)(IoContext + 136),
           *v23,
           IoContext + 32,
           (__int64)&v26);
    if ( v8 != 997 )
    {
      CancelThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(v10 + 40) + 8LL));
      *a4 = v26;
      *(_BYTE *)(IoContext + 132) = 1;
      WapHttp3StreamReceiveCompletionRoutine(IoContext, v8, v26);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180079c10  mov     [rsp+arg_10], rbx
0x180079c15  push    rbp
0x180079c16  push    rsi
0x180079c17  push    rdi
0x180079c18  push    r12
0x180079c1a  push    r13
0x180079c1c  push    r14
0x180079c1e  push    r15
0x180079c20  sub     rsp, 90h
0x180079c27  mov     rax, cs:__security_cookie
0x180079c2e  xor     rax, rsp
0x180079c31  mov     [rsp+0C8h+var_48], rax
0x180079c39  mov     rbx, [rsp+0C8h+arg_20]
0x180079c41  xor     r13d, r13d
0x180079c44  mov     rsi, [rsp+0C8h+arg_28]
0x180079c4c  mov     r15, r9
0x180079c4f  mov     [rsp+0C8h+var_50], r13d
0x180079c54  mov     rbp, rdx
0x180079c57  mov     [r9], r13
0x180079c5a  cmp     r8d, 1
0x180079c5e  jbe     short loc_180079C89
0x180079c60  test    byte ptr cs:xmmword_1800AD710+3, 4
0x180079c67  jz      short loc_180079C7F
0x180079c69  mov     edx, 0C6h
0x180079c6e  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x180079c75  mov     ecx, 21Ah
0x180079c7a  call    WPP_SF_
0x180079c7f  mov     ebx, 32h ; '2'
0x180079c84  jmp     loc_18007A08B
0x180079c89  mov     r9, [rdx+10h]
0x180079c8d  mov     eax, 0FFFFFFFFh
0x180079c92  cmp     r9, rax
0x180079c95  jbe     short loc_180079CB8
0x180079c97  test    byte ptr cs:xmmword_1800AD710+3, 4
0x180079c9e  jz      short loc_180079C7F
0x180079ca0  mov     edx, 0C7h
0x180079ca5  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x180079cac  mov     ecx, 21Ah
0x180079cb1  call    WPP_SF_q
0x180079cb6  jmp     short loc_180079C7F
0x180079cb8  mov     rdi, [rcx+48h]
0x180079cbc  mov     r14, r13
0x180079cbf  lea     rcx, [rdi+30h]; lpCriticalSection
0x180079cc3  call    cs:__imp_EnterCriticalSection
0x180079cca  nop     dword ptr [rax+rax+00h]
0x180079ccf  cmp     [rdi+58h], r13b
0x180079cd3  jz      short loc_180079CDD
0x180079cd5  mov     ebx, [rdi+5Ch]
0x180079cd8  jmp     loc_180079E3E
0x180079cdd  cmp     [rdi+130h], r13
0x180079ce4  jz      short loc_180079D0F
0x180079ce6  test    byte ptr cs:xmmword_1800AD710+3, 4
0x180079ced  jz      short loc_180079D05
0x180079cef  mov     edx, 0C8h
0x180079cf4  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x180079cfb  mov     ecx, 21Ah
0x180079d00  call    WPP_SF_
0x180079d05  mov     ebx, 54Fh
0x180079d0a  jmp     loc_180079E3E
0x180079d0f  mov     eax, [rdi+150h]
0x180079d15  test    eax, eax
0x180079d17  jz      short loc_180079D95
0x180079d19  mov     edx, [rdi+154h]
0x180079d1f  mov     ebx, r13d
0x180079d22  mov     r8, [rbp+10h]
0x180079d26  sub     eax, edx
0x180079d28  mov     rcx, [rbp+8]; void *
0x180079d2c  cmp     r8, rax
0x180079d2f  cmovnb  r8d, eax; Size
0x180079d33  add     rdx, [rdi+148h]; Src
0x180079d3a  mov     esi, r8d
0x180079d3d  call    memcpy_0
0x180079d42  add     [rdi+154h], esi
0x180079d48  mov     eax, [rdi+150h]
0x180079d4e  cmp     eax, [rdi+154h]
0x180079d54  jnz     short loc_180079D6B
0x180079d56  mov     r14, [rdi+148h]
0x180079d5d  mov     [rdi+148h], r13
0x180079d64  mov     [rdi+150h], r13
0x180079d6b  test    byte ptr cs:xmmword_1800AD720+3, 4
0x180079d72  jz      short loc_180079D8D
0x180079d74  mov     edx, 0C9h
0x180079d79  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x180079d80  mov     ecx, 41Ah
0x180079d85  mov     r9d, esi
0x180079d88  call    WPP_SF_d
0x180079d8d  mov     [r15], rsi
0x180079d90  jmp     loc_180079E3E
0x180079d95  mov     eax, [rdi+128h]
0x180079d9b  cmp     eax, 3
0x180079d9e  jnz     short loc_180079DA8
0x180079da0  mov     ebx, r13d
0x180079da3  jmp     loc_180079E3E
0x180079da8  test    eax, eax
0x180079daa  jnz     short loc_180079E0B
0x180079dac  cmp     [rdi+138h], r13
0x180079db3  jnz     loc_180079D05
0x180079db9  mov     edx, 2000h
0x180079dbe  call    WxAllocateHeapEx
0x180079dc3  mov     [rdi+138h], rax
0x180079dca  test    rax, rax
0x180079dcd  jz      short loc_180079E39
0x180079dcf  mov     [rsp+0C8h+var_98], rsi
0x180079dd4  lea     rax, WapHttp3StreamReceiveHeadersCompletionRoutine
0x180079ddb  mov     [rsp+0C8h+var_A0], rbx
0x180079de0  mov     r9d, 3
0x180079de6  mov     r8, rdi
0x180079de9  mov     [rsp+0C8h+var_A8], rax
0x180079dee  xor     edx, edx
0x180079df0  mov     dword ptr [rdi+140h], 2000h
0x180079dfa  call    WapHttpApiAllocateIoContext
0x180079dff  mov     rsi, rax
0x180079e02  test    rax, rax
0x180079e05  jz      short loc_180079E39
0x180079e07  mov     bl, 1
0x180079e09  jmp     short loc_180079E6E
0x180079e0b  mov     [rsp+0C8h+var_98], rsi
0x180079e10  lea     rax, WapHttp3StreamReceiveCompletionRoutine
0x180079e17  mov     [rsp+0C8h+var_A0], rbx
0x180079e1c  mov     r9d, 3
0x180079e22  mov     r8, rdi
0x180079e25  mov     [rsp+0C8h+var_A8], rax
0x180079e2a  xor     edx, edx
0x180079e2c  call    WapHttpApiAllocateIoContext
0x180079e31  mov     rsi, rax
0x180079e34  test    rax, rax
0x180079e37  jnz     short loc_180079E6B
0x180079e39  mov     ebx, 8
0x180079e3e  lea     rcx, [rdi+30h]; lpCriticalSection
0x180079e42  call    cs:__imp_LeaveCriticalSection
0x180079e49  nop     dword ptr [rax+rax+00h]
0x180079e4e  test    r14, r14
0x180079e51  jz      loc_18007A08B
0x180079e57  lea     rcx, [rsp+0C8h+var_58]
0x180079e5c  mov     [rsp+0C8h+var_58], r14
0x180079e61  call    WxFreeHeapEx
0x180079e66  jmp     loc_18007A08B
0x180079e6b  mov     bl, r13b
0x180079e6e  mov     rax, [rbp+8]
0x180079e72  lea     rcx, [rdi+30h]; lpCriticalSection
0x180079e76  mov     [rsi+88h], rax
0x180079e7d  mov     rax, [rbp+10h]
0x180079e81  mov     [rsi+90h], rax
0x180079e88  mov     [rdi+130h], rsi
0x180079e8f  call    cs:__imp_LeaveCriticalSection
0x180079e96  nop     dword ptr [rax+rax+00h]
0x180079e9b  test    bl, bl
0x180079e9d  jz      loc_180079F9C
0x180079ea3  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 20h
0x180079eaa  jz      short loc_180079F04
0x180079eac  mov     eax, [rdi+140h]
0x180079eb2  lea     rcx, [rsi+18h]
0x180079eb6  mov     r8, [rdi+8]
0x180079eba  lea     rdx, NetSocketRecvEntity
0x180079ec1  mov     [rsp+0C8h+var_68], 1
0x180079ec9  xor     r9d, r9d
0x180079ecc  mov     [rsp+0C8h+var_70], r13d
0x180079ed1  mov     [rsp+0C8h+var_78], rax
0x180079ed6  mov     rax, [rdi+18h]
0x180079eda  mov     [rsp+0C8h+var_80], rax
0x180079edf  mov     rax, [rdi+138h]
0x180079ee6  mov     [rsp+0C8h+var_88], r13
0x180079eeb  mov     [rsp+0C8h+var_90], r13d
0x180079ef0  mov     [rsp+0C8h+var_98], rcx
0x180079ef5  mov     [rsp+0C8h+var_A0], rax
0x180079efa  mov     [rsp+0C8h+var_A8], r13
0x180079eff  call    McTemplateU0ppxppqxxxtt_EventWriteTransfer
0x180079f04  lea     rdx, [rdi+68h]
0x180079f08  mov     rcx, rdi
0x180079f0b  call    WapHttp3StreamUpdateTimerOnRequest
0x180079f10  mov     rcx, [rdi+28h]
0x180079f14  mov     rcx, [rcx+8]; pio
0x180079f18  call    cs:__imp_StartThreadpoolIo
0x180079f1f  nop     dword ptr [rax+rax+00h]
0x180079f24  mov     rcx, [rdi+28h]
0x180079f28  lea     rax, [rsi+20h]
0x180079f2c  mov     r9, [rdi+138h]
0x180079f33  lea     rdx, [rsp+0C8h+var_50]
0x180079f38  mov     [rsp+0C8h+var_98], rdx
0x180079f3d  xor     r8d, r8d
0x180079f40  mov     rdx, [rdi+18h]
0x180079f44  mov     rcx, [rcx]
0x180079f47  mov     [rsp+0C8h+var_A0], rax
0x180079f4c  mov     eax, [rdi+140h]
0x180079f52  mov     dword ptr [rsp+0C8h+var_A8], eax
0x180079f56  call    WaHttpApiStreamReceiveHeaders
0x180079f5b  mov     ebx, eax
0x180079f5d  cmp     eax, 3E5h
0x180079f62  jz      loc_18007A08B
0x180079f68  mov     rcx, [rdi+28h]
0x180079f6c  mov     rcx, [rcx+8]; pio
0x180079f70  call    cs:__imp_CancelThreadpoolIo
0x180079f77  nop     dword ptr [rax+rax+00h]
0x180079f7c  mov     byte ptr [rsi+84h], 1
0x180079f83  mov     r9, r15
0x180079f86  mov     r8d, [rsp+0C8h+var_50]
0x180079f8b  mov     edx, ebx
0x180079f8d  mov     rcx, rsi
0x180079f90  call    WapHttp3StreamReceiveHeadersCommonCompletionRoutine
0x180079f95  mov     ebx, eax
0x180079f97  jmp     loc_18007A08B
0x180079f9c  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 20h
0x180079fa3  lea     rbx, [rsi+90h]
0x180079faa  jz      short loc_180079FFE
0x180079fac  mov     rax, [rbx]
0x180079faf  lea     rcx, [rsi+18h]
0x180079fb3  mov     r8, [rdi+8]
0x180079fb7  lea     rdx, NetSocketRecvEntity
0x180079fbe  mov     [rsp+0C8h+var_68], r13d
0x180079fc3  xor     r9d, r9d
0x180079fc6  mov     [rsp+0C8h+var_70], r13d
0x180079fcb  mov     [rsp+0C8h+var_78], rax
0x180079fd0  mov     rax, [rdi+18h]
0x180079fd4  mov     [rsp+0C8h+var_80], rax
0x180079fd9  mov     rax, [rsi+88h]
0x180079fe0  mov     [rsp+0C8h+var_88], r13
0x180079fe5  mov     [rsp+0C8h+var_90], r13d
0x180079fea  mov     [rsp+0C8h+var_98], rcx
0x180079fef  mov     [rsp+0C8h+var_A0], rax
0x180079ff4  mov     [rsp+0C8h+var_A8], r13
0x180079ff9  call    McTemplateU0ppxppqxxxtt_EventWriteTransfer
0x180079ffe  lea     rdx, [rdi+68h]
0x18007a002  mov     rcx, rdi
0x18007a005  call    WapHttp3StreamUpdateTimerOnRequest
0x18007a00a  mov     rcx, [rdi+28h]
0x18007a00e  mov     rcx, [rcx+8]; pio
0x18007a012  call    cs:__imp_StartThreadpoolIo
0x18007a019  nop     dword ptr [rax+rax+00h]
0x18007a01e  mov     rcx, [rdi+28h]
0x18007a022  lea     rax, [rsi+20h]
0x18007a026  mov     r9, [rsi+88h]
0x18007a02d  lea     rdx, [rsp+0C8h+var_50]
0x18007a032  mov     [rsp+0C8h+var_98], rdx
0x18007a037  xor     r8d, r8d
0x18007a03a  mov     rdx, [rdi+18h]
0x18007a03e  mov     rcx, [rcx]
0x18007a041  mov     [rsp+0C8h+var_A0], rax
0x18007a046  mov     eax, [rbx]
0x18007a048  mov     dword ptr [rsp+0C8h+var_A8], eax
0x18007a04c  call    WaHttpApiStreamReceiveEntityBody
0x18007a051  mov     ebx, eax
0x18007a053  cmp     eax, 3E5h
0x18007a058  jz      short loc_18007A08B
0x18007a05a  mov     rcx, [rdi+28h]
0x18007a05e  mov     rcx, [rcx+8]; pio
0x18007a062  call    cs:__imp_CancelThreadpoolIo
0x18007a069  nop     dword ptr [rax+rax+00h]
0x18007a06e  mov     eax, [rsp+0C8h+var_50]
0x18007a072  mov     edx, ebx
0x18007a074  mov     [r15], rax
0x18007a077  mov     rcx, rsi
0x18007a07a  mov     byte ptr [rsi+84h], 1
0x18007a081  mov     r8d, [rsp+0C8h+var_50]
0x18007a086  call    WapHttp3StreamReceiveCompletionRoutine
0x18007a08b  mov     eax, ebx
0x18007a08d  mov     rcx, [rsp+0C8h+var_48]
0x18007a095  xor     rcx, rsp; StackCookie
0x18007a098  call    __security_check_cookie
0x18007a09d  mov     rbx, [rsp+0C8h+arg_10]
0x18007a0a5  add     rsp, 90h
0x18007a0ac  pop     r15
0x18007a0ae  pop     r14
0x18007a0b0  pop     r13
0x18007a0b2  pop     r12
0x18007a0b4  pop     rdi
0x18007a0b5  pop     rsi
0x18007a0b6  pop     rbp
0x18007a0b7  retn
```
