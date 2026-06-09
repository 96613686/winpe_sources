# WapHttp3StreamNotifyDisconnect

- ea: `0x18007f2bc`
- end: `0x18007f478`
- name: `WapHttp3StreamNotifyDisconnect`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007fd90`
- `0x18007ff20`

## callees

- `0x18007b14c`
- `0x18007f2bc`
- `0x18007f480`
- `0x180080394`
- `0x18008059c`
- `0x180092564`
- `0x1800971ec`
- `0x180097810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f301`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f301`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f3bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f3db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f3bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f3db`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007f42f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007f42f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18007f3fe`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18007f3fe`

## pseudocode

```c
__int64 __fastcall WapHttp3StreamNotifyDisconnect(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v8; // ecx
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 IoContext; // rax
  __int64 v13; // rsi
  __int64 v14; // r9
  __int64 v15; // r8

  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_q(1050, 176, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, a1);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  if ( *(_BYTE *)(a1 + 88) )
  {
    v9 = *(_DWORD *)(a1 + 92);
LABEL_18:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
    goto LABEL_21;
  }
  v10 = *(unsigned int *)(a1 + 264);
  if ( (_DWORD)v10 != 2 )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
      WPP_SF_d(538, 177, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v10);
    goto LABEL_8;
  }
  if ( *(_QWORD *)(a1 + 280) )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) == 0 )
    {
LABEL_8:
      v9 = 1359;
      goto LABEL_18;
    }
    v11 = 178;
LABEL_12:
    WPP_SF_(538, v11, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids);
    goto LABEL_8;
  }
  if ( *(_QWORD *)(a1 + 288) )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) == 0 )
      goto LABEL_8;
    v11 = 179;
    goto LABEL_12;
  }
  IoContext = WapHttpApiAllocateIoContext(
                v8,
                0,
                a1,
                5,
                (__int64)WapHttp3StreamNotifyDisconnectCompletionRoutine,
                a3,
                a4);
  v13 = IoContext;
  if ( !IoContext )
  {
    v9 = 8;
    goto LABEL_18;
  }
  *(_QWORD *)(IoContext + 120) = a2;
  *(_QWORD *)(a1 + 288) = IoContext;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  WapHttp3StreamUpdateTimerOnRequest(a1, a1 + 184);
  StartThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(a1 + 40) + 8LL));
  v9 = WaHttpApiStreamNotifyDisconnect(**(_QWORD **)(a1 + 40), *(_QWORD *)(a1 + 24), v13 + 32);
  if ( v9 != 997 )
  {
    CancelThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(a1 + 40) + 8LL));
    LOBYTE(v14) = 1;
    v9 = WapHttp3StreamNotifyDisconnectCommonCompletionRoutine(v13, v9, v15, v14);
  }
LABEL_21:
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 180, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18007f2bc  push    rbx
0x18007f2be  push    rbp
0x18007f2bf  push    rsi
0x18007f2c0  push    rdi
0x18007f2c1  push    r12
0x18007f2c3  push    r14
0x18007f2c5  sub     rsp, 48h
0x18007f2c9  mov     rbx, r9
0x18007f2cc  mov     rsi, r8
0x18007f2cf  mov     r14, rdx
0x18007f2d2  mov     rdi, rcx
0x18007f2d5  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007f2dc  lea     r12, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007f2e3  jz      short loc_18007F2FA
0x18007f2e5  mov     edx, 0B0h
0x18007f2ea  mov     ecx, 41Ah
0x18007f2ef  mov     r9, rdi
0x18007f2f2  mov     r8, r12
0x18007f2f5  call    WPP_SF_q
0x18007f2fa  lea     rbp, [rdi+30h]
0x18007f2fe  mov     rcx, rbp; lpCriticalSection
0x18007f301  call    cs:__imp_EnterCriticalSection
0x18007f308  nop     dword ptr [rax+rax+00h]
0x18007f30d  cmp     byte ptr [rdi+58h], 0
0x18007f311  jz      short loc_18007F31B
0x18007f313  mov     ebx, [rdi+5Ch]
0x18007f316  jmp     loc_18007F3BC
0x18007f31b  mov     r9d, [rdi+108h]
0x18007f322  cmp     r9d, 2
0x18007f326  jz      short loc_18007F34A
0x18007f328  test    byte ptr cs:xmmword_1800AD710+3, 4
0x18007f32f  jz      short loc_18007F343
0x18007f331  mov     edx, 0B1h
0x18007f336  mov     ecx, 21Ah
0x18007f33b  mov     r8, r12
0x18007f33e  call    WPP_SF_d
0x18007f343  mov     ebx, 54Fh
0x18007f348  jmp     short loc_18007F3BC
0x18007f34a  cmp     qword ptr [rdi+118h], 0
0x18007f352  jz      short loc_18007F371
0x18007f354  test    byte ptr cs:xmmword_1800AD710+3, 4
0x18007f35b  jz      short loc_18007F343
0x18007f35d  mov     edx, 0B2h
0x18007f362  mov     ecx, 21Ah
0x18007f367  mov     r8, r12
0x18007f36a  call    WPP_SF_
0x18007f36f  jmp     short loc_18007F343
0x18007f371  cmp     qword ptr [rdi+120h], 0
0x18007f379  jz      short loc_18007F38B
0x18007f37b  test    byte ptr cs:xmmword_1800AD710+3, 4
0x18007f382  jz      short loc_18007F343
0x18007f384  mov     edx, 0B3h
0x18007f389  jmp     short loc_18007F362
0x18007f38b  mov     [rsp+78h+var_48], rbx
0x18007f390  lea     rax, WapHttp3StreamNotifyDisconnectCompletionRoutine
0x18007f397  mov     [rsp+78h+var_50], rsi
0x18007f39c  mov     r9d, 5
0x18007f3a2  mov     r8, rdi
0x18007f3a5  mov     [rsp+78h+var_58], rax
0x18007f3aa  xor     edx, edx
0x18007f3ac  call    WapHttpApiAllocateIoContext
0x18007f3b1  mov     rsi, rax
0x18007f3b4  test    rax, rax
0x18007f3b7  jnz     short loc_18007F3CD
0x18007f3b9  lea     ebx, [rax+8]
0x18007f3bc  mov     rcx, rbp; lpCriticalSection
0x18007f3bf  call    cs:__imp_LeaveCriticalSection
0x18007f3c6  nop     dword ptr [rax+rax+00h]
0x18007f3cb  jmp     short loc_18007F44A
0x18007f3cd  mov     [rax+78h], r14
0x18007f3d1  mov     rcx, rbp; lpCriticalSection
0x18007f3d4  mov     [rdi+120h], rsi
0x18007f3db  call    cs:__imp_LeaveCriticalSection
0x18007f3e2  nop     dword ptr [rax+rax+00h]
0x18007f3e7  lea     rdx, [rdi+0B8h]
0x18007f3ee  mov     rcx, rdi
0x18007f3f1  call    WapHttp3StreamUpdateTimerOnRequest
0x18007f3f6  mov     rcx, [rdi+28h]
0x18007f3fa  mov     rcx, [rcx+8]; pio
0x18007f3fe  call    cs:__imp_StartThreadpoolIo
0x18007f405  nop     dword ptr [rax+rax+00h]
0x18007f40a  mov     rcx, [rdi+28h]
0x18007f40e  lea     r8, [rsi+20h]
0x18007f412  mov     rdx, [rdi+18h]
0x18007f416  mov     rcx, [rcx]
0x18007f419  call    WaHttpApiStreamNotifyDisconnect
0x18007f41e  mov     ebx, eax
0x18007f420  cmp     eax, 3E5h
0x18007f425  jz      short loc_18007F44A
0x18007f427  mov     rcx, [rdi+28h]
0x18007f42b  mov     rcx, [rcx+8]; pio
0x18007f42f  call    cs:__imp_CancelThreadpoolIo
0x18007f436  nop     dword ptr [rax+rax+00h]
0x18007f43b  mov     r9b, 1
0x18007f43e  mov     edx, ebx
0x18007f440  mov     rcx, rsi
0x18007f443  call    WapHttp3StreamNotifyDisconnectCommonCompletionRoutine
0x18007f448  mov     ebx, eax
0x18007f44a  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007f451  jz      short loc_18007F468
0x18007f453  mov     edx, 0B4h
0x18007f458  mov     ecx, 41Ah
0x18007f45d  mov     r9d, ebx
0x18007f460  mov     r8, r12
0x18007f463  call    WPP_SF_d
0x18007f468  mov     eax, ebx
0x18007f46a  add     rsp, 48h
0x18007f46e  pop     r14
0x18007f470  pop     r12
0x18007f472  pop     rdi
0x18007f473  pop     rsi
0x18007f474  pop     rbp
0x18007f475  pop     rbx
0x18007f476  retn
```
