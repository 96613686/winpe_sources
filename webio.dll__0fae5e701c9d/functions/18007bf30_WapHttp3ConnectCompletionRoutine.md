# WapHttp3ConnectCompletionRoutine

- ea: `0x18007bf30`
- end: `0x18007c304`
- name: `WapHttp3ConnectCompletionRoutine`
- size: `980`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007bf30`
- `0x18007e4dc`

## callees

- `0x18002c94c`
- `0x18005307c`
- `0x180068018`
- `0x180071600`
- `0x1800722f0`
- `0x18007bd28`
- `0x18007bf30`
- `0x18007c30c`
- `0x18007c3c0`
- `0x18007c5ac`
- `0x18007cecc`
- `0x18007e754`
- `0x180080510`
- `0x180080830`
- `0x180092564`
- `0x180093944`
- `0x180097810`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007c103`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007c103`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007bfe6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007bfe6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c11f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c11f`

## pseudocode

```c
__int64 __fastcall WapHttp3ConnectCompletionRoutine(__int64 a1, int Connection)
{
  __int64 v2; // rdi
  char v4; // r14
  unsigned int v6; // eax
  unsigned int updated; // eax
  __int64 v8; // r8
  bool v9; // zf
  char v10; // bp
  unsigned int v11; // eax
  unsigned int ValidAddressForInterface; // eax
  int v13; // edx
  __int64 v14; // r8
  int started; // eax
  __int64 v16; // rax
  unsigned int v17; // eax
  __int64 result; // rax
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-38h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  v4 = 0;
  if ( (unsigned __int8)WaCancelTwTimer(a1 + 136) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF) == 1 )
      WapHttpApiFreeIoContext(a1);
  }
  else if ( *(_DWORD *)(a1 + 228) )
  {
    WaHttp3AbortRequest(*(_QWORD *)(v2 + 8), 0, 1460);
  }
  if ( Connection == 10054 )
  {
    v6 = WapHttp3ConnectionCheckForClientAuthRequired(v2);
    Connection = WapHttp3ConnectionCheckForServerCertError(v2, v6);
  }
  if ( !Connection )
  {
    updated = WapHttp3UpdateConnectedState(v2);
    Connection = updated;
    if ( updated )
      WaHttp3AbortRequest(*(_QWORD *)(v2 + 8), 0, updated);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 24));
  v9 = *(_DWORD *)(v2 + 64) == 3;
  v10 = 1;
  *(_QWORD *)(v2 + 632) = 0;
  if ( v9 )
  {
    if ( !Connection )
    {
      *(_DWORD *)(v2 + 64) = 4;
      *(_QWORD *)(v2 + 120) = 0;
      goto LABEL_29;
    }
    if ( Connection != 590624 )
    {
      *(_DWORD *)(v2 + 64) = 2;
      LOBYTE(v8) = 1;
      ++*(_DWORD *)(a1 + 216);
      --*(_DWORD *)(a1 + 220);
      ++*(_DWORD *)(v2 + 288);
      v11 = WaUpdateDnsQueryResultIndexByPort(
              *(_QWORD *)(v2 + 280),
              *(unsigned __int16 *)(v2 + 296),
              v8,
              *(unsigned int *)(a1 + 216));
      *(_DWORD *)(a1 + 216) = v11;
      ValidAddressForInterface = WapHttp3FindValidAddressForInterface(v2, v11);
      v13 = *(_DWORD *)(a1 + 220);
      *(_DWORD *)(a1 + 216) = ValidAddressForInterface;
      if ( v13 && (unsigned __int64)ValidAddressForInterface < *(_QWORD *)(*(_QWORD *)(v2 + 280) + 40LL) )
      {
        Connection = WapHttp3CreateConnection(v2, a1);
        if ( Connection )
          goto LABEL_29;
        *(_QWORD *)(v2 + 632) = a1;
        *(_DWORD *)(v2 + 64) = 3;
      }
      else
      {
        if ( !*(_BYTE *)(v2 + 299) || *(_DWORD *)(v2 + 292) != 1 || !v13 )
          goto LABEL_29;
        if ( (xmmword_1800AD720 & 8) != 0 )
          WPP_SF_(1027, 112, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids);
        *(_DWORD *)(v2 + 64) = 0;
        v4 = 1;
      }
      v10 = 0;
    }
  }
  else
  {
    Connection = *(_DWORD *)(v2 + 72);
    if ( !Connection )
      Connection = 1359;
  }
LABEL_29:
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  *(LARGE_INTEGER *)(v2 + 1056) = PerformanceCount;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 24));
  if ( v4 )
  {
    started = WapHttp3StartDnsQuery(
                v2,
                *(_QWORD *)(a1 + 200),
                *(_QWORD *)(a1 + 208),
                *(_DWORD *)(a1 + 220),
                *(_DWORD *)(a1 + 224),
                *(_DWORD *)(a1 + 228),
                *(_QWORD *)(a1 + 96),
                *(_QWORD *)(a1 + 104));
    if ( started == 997 )
      *(_BYTE *)(a1 + 132) = 1;
    else
      *(_DWORD *)(a1 + 112) = started;
  }
  else if ( v10 )
  {
    *(_DWORD *)(a1 + 112) = Connection;
    v16 = 0;
    if ( !Connection )
    {
      (*(void (__fastcall **)(_QWORD, __int64, unsigned __int64, __int64))(*(_QWORD *)(v2 + 16) + 88LL))(
        *(_QWORD *)(v2 + 8),
        1,
        *(_QWORD *)(*(_QWORD *)(v2 + 280) + 32LL) + ((unsigned __int64)*(unsigned int *)(a1 + 216) << 7),
        128);
      v16 = 0x1000000;
    }
    *(_QWORD *)(a1 + 120) = v16;
    if ( Connection )
    {
      if ( (xmmword_1800AD710 & 8) != 0 )
        WPP_SF_iD(515, 114, v14, *(_QWORD *)(v2 + 80), Connection);
      if ( (Microsoft_Windows_WebIOEnableBits & 0x8000) != 0 )
        McTemplateU0pxqzr2pxqx_EventWriteTransfer(
          (unsigned int)&WEB_ETW_PROVIDER_ID_Context,
          (unsigned int)NetSocketConnectFailed,
          *(_QWORD *)(v2 + 8),
          0,
          0,
          0,
          a1 + 24,
          *(_DWORD *)(a1 + 220),
          Connection,
          *(_QWORD *)(v2 + 80));
    }
    else
    {
      if ( (xmmword_1800AD720 & 8) != 0 )
        WPP_SF_q(1027, 113, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, *(_QWORD *)(v2 + 80));
      if ( (Microsoft_Windows_WebIOEnableBits & 0x4000) != 0 )
        McTemplateU0pxqzr2pxqx_EventWriteTransfer(
          (unsigned int)&WEB_ETW_PROVIDER_ID_Context,
          (unsigned int)NetSocketConnectComplete,
          *(_QWORD *)(v2 + 8),
          0,
          0,
          0,
          a1 + 24,
          *(_DWORD *)(a1 + 220),
          0,
          *(_QWORD *)(v2 + 80));
    }
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
    v17 = WapHttp3Connect((LARGE_INTEGER *)v2, a1);
    if ( v17 != 997 )
      WapHttp3ConnectCompletionRoutine(a1, v17, 0);
  }
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return WapHttpApiFreeIoContext(a1);
  return result;
}

```

## disassembly

```asm
0x18007bf30  mov     [rsp+arg_10], rbx
0x18007bf35  mov     [rsp+arg_18], rbp
0x18007bf3a  push    rsi
0x18007bf3b  push    rdi
0x18007bf3c  push    r12
0x18007bf3e  push    r14
0x18007bf40  push    r15
0x18007bf42  sub     rsp, 60h
0x18007bf46  mov     rax, cs:__security_cookie
0x18007bf4d  xor     rax, rsp
0x18007bf50  mov     [rsp+88h+var_30], rax
0x18007bf55  mov     rdi, [rcx+10h]
0x18007bf59  mov     rbx, rcx
0x18007bf5c  xor     r12d, r12d
0x18007bf5f  add     rcx, 88h
0x18007bf66  mov     r14b, r12b
0x18007bf69  mov     esi, edx
0x18007bf6b  call    WaCancelTwTimer
0x18007bf70  test    al, al
0x18007bf72  jz      short loc_18007BF8B
0x18007bf74  or      eax, 0FFFFFFFFh
0x18007bf77  lock xadd [rbx+4], eax
0x18007bf7c  cmp     eax, 1
0x18007bf7f  jnz     short loc_18007BFA5
0x18007bf81  mov     rcx, rbx
0x18007bf84  call    WapHttpApiFreeIoContext
0x18007bf89  jmp     short loc_18007BFA5
0x18007bf8b  cmp     [rbx+0E4h], r12d
0x18007bf92  jz      short loc_18007BFA5
0x18007bf94  mov     rcx, [rdi+8]
0x18007bf98  xor     edx, edx
0x18007bf9a  mov     r8d, 5B4h
0x18007bfa0  call    WaHttp3AbortRequest
0x18007bfa5  mov     edx, 2746h
0x18007bfaa  cmp     esi, edx
0x18007bfac  jnz     short loc_18007BFC2
0x18007bfae  mov     rcx, rdi
0x18007bfb1  call    WapHttp3ConnectionCheckForClientAuthRequired
0x18007bfb6  mov     edx, eax
0x18007bfb8  mov     rcx, rdi
0x18007bfbb  call    WapHttp3ConnectionCheckForServerCertError
0x18007bfc0  mov     esi, eax
0x18007bfc2  test    esi, esi
0x18007bfc4  jnz     short loc_18007BFE2
0x18007bfc6  mov     rcx, rdi
0x18007bfc9  call    WapHttp3UpdateConnectedState
0x18007bfce  mov     esi, eax
0x18007bfd0  test    eax, eax
0x18007bfd2  jz      short loc_18007BFE2
0x18007bfd4  mov     rcx, [rdi+8]
0x18007bfd8  mov     r8d, eax
0x18007bfdb  xor     edx, edx
0x18007bfdd  call    WaHttp3AbortRequest
0x18007bfe2  lea     rcx, [rdi+18h]; lpCriticalSection
0x18007bfe6  call    cs:__imp_EnterCriticalSection
0x18007bfed  nop     dword ptr [rax+rax+00h]
0x18007bff2  cmp     dword ptr [rdi+40h], 3
0x18007bff6  mov     bpl, 1
0x18007bff9  mov     [rdi+278h], r12
0x18007c000  jz      short loc_18007C014
0x18007c002  mov     esi, [rdi+48h]
0x18007c005  mov     eax, 54Fh
0x18007c00a  test    esi, esi
0x18007c00c  cmovz   esi, eax
0x18007c00f  jmp     loc_18007C0F9
0x18007c014  test    esi, esi
0x18007c016  jnz     short loc_18007C028
0x18007c018  mov     dword ptr [rdi+40h], 4
0x18007c01f  mov     [rdi+78h], r12
0x18007c023  jmp     loc_18007C0F9
0x18007c028  cmp     esi, 90320h
0x18007c02e  jz      loc_18007C0F9
0x18007c034  mov     dword ptr [rdi+40h], 2
0x18007c03b  mov     r8b, bpl
0x18007c03e  inc     dword ptr [rbx+0D8h]
0x18007c044  dec     dword ptr [rbx+0DCh]
0x18007c04a  inc     dword ptr [rdi+120h]
0x18007c050  mov     r9d, [rbx+0D8h]
0x18007c057  movzx   edx, word ptr [rdi+128h]
0x18007c05e  mov     rcx, [rdi+118h]
0x18007c065  call    WaUpdateDnsQueryResultIndexByPort
0x18007c06a  mov     edx, eax
0x18007c06c  mov     [rbx+0D8h], eax
0x18007c072  mov     rcx, rdi
0x18007c075  call    WapHttp3FindValidAddressForInterface
0x18007c07a  mov     edx, [rbx+0DCh]
0x18007c080  mov     [rbx+0D8h], eax
0x18007c086  test    edx, edx
0x18007c088  jz      short loc_18007C0BA
0x18007c08a  mov     rcx, [rdi+118h]
0x18007c091  mov     eax, eax
0x18007c093  cmp     rax, [rcx+28h]
0x18007c097  jnb     short loc_18007C0BA
0x18007c099  mov     rdx, rbx
0x18007c09c  mov     rcx, rdi
0x18007c09f  call    WapHttp3CreateConnection
0x18007c0a4  mov     esi, eax
0x18007c0a6  test    eax, eax
0x18007c0a8  jnz     short loc_18007C0F9
0x18007c0aa  mov     [rdi+278h], rbx
0x18007c0b1  mov     dword ptr [rdi+40h], 3
0x18007c0b8  jmp     short loc_18007C0F6
0x18007c0ba  cmp     [rdi+12Bh], r12b
0x18007c0c1  jz      short loc_18007C0F9
0x18007c0c3  cmp     dword ptr [rdi+124h], 1
0x18007c0ca  jnz     short loc_18007C0F9
0x18007c0cc  test    edx, edx
0x18007c0ce  jz      short loc_18007C0F9
0x18007c0d0  test    byte ptr cs:xmmword_1800AD720, 8
0x18007c0d7  jz      short loc_18007C0EF
0x18007c0d9  mov     edx, 70h ; 'p'
0x18007c0de  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007c0e5  mov     ecx, 403h
0x18007c0ea  call    WPP_SF_
0x18007c0ef  mov     [rdi+40h], r12d
0x18007c0f3  mov     r14b, 1
0x18007c0f6  mov     bpl, r12b
0x18007c0f9  lea     rcx, [rsp+88h+PerformanceCount]; lpPerformanceCount
0x18007c0fe  mov     qword ptr [rsp+88h+PerformanceCount], r12
0x18007c103  call    cs:__imp_QueryPerformanceCounter
0x18007c10a  nop     dword ptr [rax+rax+00h]
0x18007c10f  mov     rax, qword ptr [rsp+88h+PerformanceCount]
0x18007c114  lea     rcx, [rdi+18h]; lpCriticalSection
0x18007c118  mov     [rdi+420h], rax
0x18007c11f  call    cs:__imp_LeaveCriticalSection
0x18007c126  nop     dword ptr [rax+rax+00h]
0x18007c12b  test    r14b, r14b
0x18007c12e  jz      short loc_18007C18E
0x18007c130  mov     rax, [rbx+68h]
0x18007c134  mov     rcx, rdi
0x18007c137  mov     r9d, [rbx+0DCh]
0x18007c13e  mov     r8, [rbx+0D0h]
0x18007c145  mov     rdx, [rbx+0C8h]
0x18007c14c  mov     [rsp+88h+var_50], rax
0x18007c151  mov     rax, [rbx+60h]
0x18007c155  mov     [rsp+88h+var_58], rax
0x18007c15a  mov     eax, [rbx+0E4h]
0x18007c160  mov     dword ptr [rsp+88h+var_60], eax
0x18007c164  mov     eax, [rbx+0E0h]
0x18007c16a  mov     [rsp+88h+var_68], eax
0x18007c16e  call    WapHttp3StartDnsQuery
0x18007c173  cmp     eax, 3E5h
0x18007c178  jnz     short loc_18007C186
0x18007c17a  mov     byte ptr [rbx+84h], 1
0x18007c181  jmp     loc_18007C2C8
0x18007c186  mov     [rbx+70h], eax
0x18007c189  jmp     loc_18007C2C8
0x18007c18e  test    bpl, bpl
0x18007c191  jz      loc_18007C2A5
0x18007c197  mov     [rbx+70h], esi
0x18007c19a  mov     rax, r12
0x18007c19d  test    esi, esi
0x18007c19f  jnz     short loc_18007C1D4
0x18007c1a1  mov     rax, [rdi+118h]
0x18007c1a8  lea     edx, [rsi+1]
0x18007c1ab  mov     rcx, [rdi+10h]
0x18007c1af  lea     r9d, [rdx+7Fh]
0x18007c1b3  mov     r8d, [rbx+0D8h]
0x18007c1ba  shl     r8, 7
0x18007c1be  add     r8, [rax+20h]
0x18007c1c2  mov     rax, [rcx+58h]
0x18007c1c6  mov     rcx, [rdi+8]
0x18007c1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c1cf  mov     eax, 1000000h
0x18007c1d4  mov     [rbx+78h], rax
0x18007c1d8  test    esi, esi
0x18007c1da  jnz     short loc_18007C235
0x18007c1dc  test    byte ptr cs:xmmword_1800AD720, 8
0x18007c1e3  jz      short loc_18007C1FD
0x18007c1e5  mov     r9, [rdi+50h]
0x18007c1e9  lea     edx, [rsi+71h]
0x18007c1ec  mov     ecx, 403h
0x18007c1f1  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007c1f8  call    WPP_SF_q
0x18007c1fd  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 40h
0x18007c204  jz      loc_18007C2C8
0x18007c20a  mov     rax, [rdi+50h]
0x18007c20e  lea     rdx, [rbx+18h]
0x18007c212  mov     ecx, [rbx+0DCh]
0x18007c218  mov     [rsp+88h+var_40], rax
0x18007c21d  mov     [rsp+88h+var_48], r12d
0x18007c222  mov     [rsp+88h+var_50], rcx
0x18007c227  mov     [rsp+88h+var_58], rdx
0x18007c22c  lea     rdx, NetSocketConnectComplete
0x18007c233  jmp     short loc_18007C286
0x18007c235  test    byte ptr cs:xmmword_1800AD710, 8
0x18007c23c  jz      short loc_18007C255
0x18007c23e  mov     r9, [rdi+50h]
0x18007c242  mov     edx, 72h ; 'r'
0x18007c247  mov     ecx, 203h
0x18007c24c  mov     [rsp+88h+var_68], esi
0x18007c250  call    WPP_SF_iD
0x18007c255  cmp     byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, r12b
0x18007c25c  jge     short loc_18007C2C8
0x18007c25e  mov     rax, [rdi+50h]
0x18007c262  lea     rdx, [rbx+18h]
0x18007c266  mov     ecx, [rbx+0DCh]
0x18007c26c  mov     [rsp+88h+var_40], rax
0x18007c271  mov     [rsp+88h+var_48], esi
0x18007c275  mov     [rsp+88h+var_50], rcx
0x18007c27a  mov     [rsp+88h+var_58], rdx
0x18007c27f  lea     rdx, NetSocketConnectFailed
0x18007c286  mov     r8, [rdi+8]
0x18007c28a  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x18007c291  mov     [rsp+88h+var_60], r12
0x18007c296  xor     r9d, r9d
0x18007c299  mov     [rsp+88h+var_68], r12d
0x18007c29e  call    McTemplateU0pxqzr2pxqx_EventWriteTransfer
0x18007c2a3  jmp     short loc_18007C2C8
0x18007c2a5  lock inc dword ptr [rbx+4]
0x18007c2a9  mov     rdx, rbx
0x18007c2ac  mov     rcx, rdi
0x18007c2af  call    WapHttp3Connect
0x18007c2b4  cmp     eax, 3E5h
0x18007c2b9  jz      short loc_18007C2C8
0x18007c2bb  xor     r8d, r8d
0x18007c2be  mov     edx, eax
0x18007c2c0  mov     rcx, rbx
0x18007c2c3  call    WapHttp3ConnectCompletionRoutine
0x18007c2c8  or      eax, 0FFFFFFFFh
0x18007c2cb  lock xadd [rbx+4], eax
0x18007c2d0  cmp     eax, 1
0x18007c2d3  jnz     short loc_18007C2DD
0x18007c2d5  mov     rcx, rbx
0x18007c2d8  call    WapHttpApiFreeIoContext
0x18007c2dd  mov     rcx, [rsp+88h+var_30]
0x18007c2e2  xor     rcx, rsp; StackCookie
0x18007c2e5  call    __security_check_cookie
0x18007c2ea  lea     r11, [rsp+88h+var_28]
0x18007c2ef  mov     rbx, [r11+40h]
0x18007c2f3  mov     rbp, [r11+48h]
0x18007c2f7  mov     rsp, r11
0x18007c2fa  pop     r15
0x18007c2fc  pop     r14
0x18007c2fe  pop     r12
0x18007c300  pop     rdi
0x18007c301  pop     rsi
0x18007c302  retn
```
