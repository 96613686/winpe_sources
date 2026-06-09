# WapTcpDnsQueryCompletionRoutine

- ea: `0x180052950`
- end: `0x180052f57`
- name: `WapTcpDnsQueryCompletionRoutine`
- size: `1543`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180051cd4`

## callees

- `0x1800052bc`
- `0x180013470`
- `0x1800154c0`
- `0x1800180e0`
- `0x180051cd4`
- `0x1800522a0`
- `0x180052950`
- `0x180052f60`
- `0x18005307c`
- `0x1800533d0`
- `0x1800535dc`
- `0x180053f5c`
- `0x180054794`
- `0x1800722f0`
- `0x18009218c`
- `0x180092564`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180052b05`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180052b05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800529c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052b6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800529c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052b6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800529f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052c68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052d92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052ea0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052ed2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052eeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800529f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052c68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052d92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052ea0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052ed2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052eeb`

## pseudocode

```c
__int64 __fastcall WapTcpDnsQueryCompletionRoutine(LPVOID lpMem, int a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v4; // r13
  int started; // esi
  char v7; // r12
  char v8; // bp
  bool v9; // zf
  __int64 result; // rax
  _WORD *v11; // rbp
  __int64 v12; // rcx
  unsigned int updated; // eax
  int ValidAddressForInterface; // eax
  __int64 v15; // rcx
  __int64 v16; // rbp
  __int64 v17; // r12
  int v18; // esi
  __int64 v19; // r8
  __int64 IoContext; // rax
  __int64 v21; // rbp
  struct _RTL_CRITICAL_SECTION *v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rcx
  __int16 v25; // ax
  int v26; // [rsp+54h] [rbp-84h]
  int v27; // [rsp+58h] [rbp-80h]
  int v28; // [rsp+5Ch] [rbp-7Ch]
  int v29; // [rsp+60h] [rbp-78h]
  __int64 v30; // [rsp+68h] [rbp-70h]
  __int64 v31; // [rsp+70h] [rbp-68h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+80h] [rbp-58h] BYREF
  __int64 *v34; // [rsp+90h] [rbp-48h]
  __int64 v35; // [rsp+98h] [rbp-40h]

  v3 = *((_QWORD *)lpMem + 1);
  SystemTimeAsFileTime = 0;
  v4 = a3;
  v27 = 0;
  started = a2;
  v7 = 0;
  v8 = 0;
  if ( a2 )
  {
    v4 = 0;
    *(_DWORD *)(v3 + 300) = 3;
    *(_DWORD *)(v3 + 304) = 2;
    *(_DWORD *)(v3 + 308) = 1;
    *(_DWORD *)(v3 + 296) = a2;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(*(_QWORD *)(v3 + 16) + 88LL))(
      *(_QWORD *)(v3 + 8),
      3,
      *(_QWORD *)(a3 + 32),
      128);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
  v9 = *(_DWORD *)(v3 + 224) == 1;
  *(_QWORD *)(v3 + 328) = 0;
  if ( v9 )
  {
    if ( started )
    {
      *(_DWORD *)(v3 + 224) = 0;
      goto LABEL_6;
    }
    v11 = (_WORD *)(v3 + 324);
    started = WaMapInterfaceToAddressFamily(*(unsigned int *)(v3 + 320), v3 + 324);
    if ( started )
      goto LABEL_45;
    if ( *v11 )
    {
      v25 = *(_WORD *)(v3 + 984);
      if ( v25 )
      {
        if ( v25 != *v11 )
        {
          started = 87;
          *(_DWORD *)(v3 + 300) = 3;
          *(_DWORD *)(v3 + 296) = 87;
          *(_DWORD *)(v3 + 304) = 3;
          *(_DWORD *)(v3 + 308) = 1;
LABEL_45:
          *(_DWORD *)(v3 + 224) = 0;
          v8 = 0;
          goto LABEL_6;
        }
      }
    }
    v12 = v4;
    *(_QWORD *)(v3 + 336) = v4;
    v4 = 0;
    updated = WaUpdateDnsQueryResultIndexByPort(v12, *(unsigned __int16 *)(v3 + 352), 0, 0);
    ValidAddressForInterface = WapTcpFindValidAddressForInterface(v3, updated);
    v27 = ValidAddressForInterface;
    if ( *(_BYTE *)(v3 + 355)
      && *(_DWORD *)(v3 + 348) == 1
      && *((_DWORD *)lpMem + 80)
      && ValidAddressForInterface == *(_QWORD *)(*(_QWORD *)(v3 + 336) + 40LL) )
    {
      if ( (xmmword_1800AD720 & 8) != 0 )
        WPP_SF_(1027, 20, WPP_14086b36644f38024399eb8d606249d9_Traceguids);
      *(_DWORD *)(v3 + 224) = 0;
      v7 = 1;
      v8 = 0;
    }
    else
    {
      v15 = *(_QWORD *)(v3 + 336);
      *(_QWORD *)(v3 + 1112) = *(_QWORD *)(v15 + 96);
      *(_QWORD *)(v3 + 1120) = *(_QWORD *)(v15 + 104);
      *(_BYTE *)(v3 + 356) = *(_BYTE *)(v15 + 88);
      *(_QWORD *)(v3 + 384) = *(_QWORD *)(v15 + 112);
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v8 = 1;
      *(struct _FILETIME *)(v3 + 392) = SystemTimeAsFileTime;
      *(_DWORD *)(v3 + 224) = 2;
    }
  }
  else
  {
    started = *(_DWORD *)(v3 + 232);
    if ( !started )
      started = 1359;
  }
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
  if ( v7 )
  {
    started = WapTcpStartDnsQuery(
                v3,
                *((_QWORD *)lpMem + 38),
                *((_QWORD *)lpMem + 39),
                *((_DWORD *)lpMem + 80),
                *((_DWORD *)lpMem + 81),
                *((_DWORD *)lpMem + 82),
                *((_QWORD *)lpMem + 42),
                *((_DWORD *)lpMem + 86),
                *((_QWORD *)lpMem + 11),
                *((_QWORD *)lpMem + 12));
    if ( started == 997 )
      *((_BYTE *)lpMem + 124) = 1;
  }
  else
  {
    if ( !v8 )
      goto LABEL_8;
    v16 = *((_QWORD *)lpMem + 12);
    v17 = *((_QWORD *)lpMem + 11);
    v18 = *((_DWORD *)lpMem + 80);
    v26 = *((_DWORD *)lpMem + 86);
    v30 = *((_QWORD *)lpMem + 42);
    v29 = *((_DWORD *)lpMem + 82);
    v28 = *((_DWORD *)lpMem + 81);
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
    if ( *(_DWORD *)(v3 + 224) == 2 )
    {
      if ( (Microsoft_Windows_WebIOEnableBits & 0x40) != 0 )
      {
        v31 = *(_QWORD *)(v3 + 8);
        v35 = 8;
        v34 = &v31;
        McGenEventWrite_EventWriteTransfer(
          &WEB_ETW_PROVIDER_ID_Context,
          (const EVENT_DESCRIPTOR *)ConnectionTCPConnect,
          v19,
          2u,
          &v33);
      }
      IoContext = WapTcpAllocateIoContext(0x160u, v3, 1, (__int64)WapTcpConnectCompletionRoutine, v17, v16);
      v21 = IoContext;
      if ( IoContext )
      {
        *(_QWORD *)(IoContext + 200) = *((_QWORD *)lpMem + 39);
        *((_QWORD *)lpMem + 39) = 0;
        *(_QWORD *)(IoContext + 192) = *((_QWORD *)lpMem + 38);
        *((_QWORD *)lpMem + 38) = 0;
        *(_DWORD *)(IoContext + 216) = v28;
        *(_DWORD *)(IoContext + 220) = v29;
        *(_QWORD *)(IoContext + 224) = v30;
        *(_DWORD *)(IoContext + 232) = v26;
        *(_DWORD *)(IoContext + 208) = v27;
        *(_DWORD *)(IoContext + 212) = v18;
        if ( !v18 || v27 == *(_QWORD *)(*(_QWORD *)(v3 + 336) + 40LL) )
        {
          if ( (xmmword_1800AD720 & 8) != 0 )
            WPP_SF_dd(
              1027,
              22,
              WPP_14086b36644f38024399eb8d606249d9_Traceguids,
              *(unsigned __int16 *)(v3 + 352),
              *(unsigned __int16 *)(v3 + 324));
          LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
          *(_BYTE *)(v21 + 124) = 1;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v21 + 4), 0xFFFFFFFF) == 1 )
            WapTcpFreeIoContext((LPVOID)v21);
          started = 10065;
        }
        else
        {
          started = WapTcpAllocateSocket(v3, IoContext);
          v22 = (struct _RTL_CRITICAL_SECTION *)(v3 + 24);
          if ( !started )
          {
            *(_QWORD *)(v3 + 688) = v21;
            *(_DWORD *)(v3 + 224) = 3;
            LeaveCriticalSection(v22);
            v23 = WapTcpConnectSocket(v3, v21);
            if ( v23 == 997 )
            {
              if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
                McTemplateU0pq_EventWriteTransfer(v24, ThreadActionQueue, v21 + 16, 3);
            }
            else
            {
              WapTcpConnectCompletionRoutine(v21, v23, 0);
            }
LABEL_27:
            *((_BYTE *)lpMem + 124) = 1;
            started = 0;
            goto LABEL_8;
          }
          LeaveCriticalSection(v22);
          *(_BYTE *)(v21 + 124) = 1;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v21 + 4), 0xFFFFFFFF) == 1 )
            WapTcpFreeIoContext((LPVOID)v21);
          if ( started == 997 )
            goto LABEL_27;
        }
      }
      else
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
        started = 8;
      }
    }
    else
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
      started = 5023;
    }
  }
LABEL_8:
  if ( v4 )
    WaDereferenceDnsQueryResult(v4);
  *((_DWORD *)lpMem + 26) = started;
  *((_QWORD *)lpMem + 14) = 0;
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)lpMem + 1, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return WapTcpFreeIoContext(lpMem);
  return result;
}

```

## disassembly

```asm
0x180052950  mov     [rsp+arg_8], rbx
0x180052955  mov     [rsp+arg_18], rbp
0x18005295a  push    rsi
0x18005295b  push    rdi
0x18005295c  push    r12
0x18005295e  push    r13
0x180052960  push    r14
0x180052962  sub     rsp, 0B0h
0x180052969  mov     rax, cs:__security_cookie
0x180052970  xor     rax, rsp
0x180052973  mov     [rsp+0D8h+var_38], rax
0x18005297b  mov     rbx, [rcx+8]
0x18005297f  xor     eax, eax
0x180052981  mov     qword ptr [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180052986  mov     r13, r8
0x180052989  mov     [rsp+0D8h+var_80], eax
0x18005298d  mov     esi, edx
0x18005298f  mov     rdi, rcx
0x180052992  mov     r12b, al
0x180052995  mov     bpl, al
0x180052998  test    edx, edx
0x18005299a  jnz     loc_180052CA2
0x1800529a0  mov     rax, [rbx+10h]
0x1800529a4  lea     edx, [rsi+3]
0x1800529a7  mov     r8, [r8+20h]
0x1800529ab  mov     r9d, 80h
0x1800529b1  mov     rcx, [rbx+8]
0x1800529b5  mov     rax, [rax+58h]
0x1800529b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529be  lea     r14, [rbx+18h]
0x1800529c2  mov     rcx, r14; lpCriticalSection
0x1800529c5  call    cs:__imp_EnterCriticalSection
0x1800529cc  nop     dword ptr [rax+rax+00h]
0x1800529d1  xor     ecx, ecx
0x1800529d3  cmp     dword ptr [rbx+0E0h], 1
0x1800529da  mov     [rbx+148h], rcx
0x1800529e1  jnz     loc_180052DC8
0x1800529e7  test    esi, esi
0x1800529e9  jz      short loc_180052A68
0x1800529eb  mov     [rbx+0E0h], ecx
0x1800529f1  mov     rcx, r14; lpCriticalSection
0x1800529f4  call    cs:__imp_LeaveCriticalSection
0x1800529fb  nop     dword ptr [rax+rax+00h]
0x180052a00  test    r12b, r12b
0x180052a03  jnz     loc_180052E2E
0x180052a09  test    bpl, bpl
0x180052a0c  jnz     loc_180052B2F
0x180052a12  test    r13, r13
0x180052a15  jnz     loc_180052F4A
0x180052a1b  mov     [rdi+68h], esi
0x180052a1e  or      eax, 0FFFFFFFFh
0x180052a21  mov     qword ptr [rdi+70h], 0
0x180052a29  lock xadd [rdi+4], eax
0x180052a2e  cmp     eax, 1
0x180052a31  jnz     short loc_180052A3B
0x180052a33  mov     rcx, rdi; lpMem
0x180052a36  call    WapTcpFreeIoContext
0x180052a3b  mov     rcx, [rsp+0D8h+var_38]
0x180052a43  xor     rcx, rsp; StackCookie
0x180052a46  call    __security_check_cookie
0x180052a4b  lea     r11, [rsp+0D8h+var_28]
0x180052a53  mov     rbx, [r11+38h]
0x180052a57  mov     rbp, [r11+48h]
0x180052a5b  mov     rsp, r11
0x180052a5e  pop     r14
0x180052a60  pop     r13
0x180052a62  pop     r12
0x180052a64  pop     rdi
0x180052a65  pop     rsi
0x180052a66  retn
0x180052a68  mov     ecx, [rbx+140h]
0x180052a6e  lea     rbp, [rbx+144h]
0x180052a75  mov     rdx, rbp
0x180052a78  call    WaMapInterfaceToAddressFamily
0x180052a7d  xor     edx, edx
0x180052a7f  mov     esi, eax
0x180052a81  test    eax, eax
0x180052a83  jnz     loc_180052E20
0x180052a89  cmp     [rbp+0], dx
0x180052a8d  jnz     loc_180052DDD
0x180052a93  mov     rcx, r13
0x180052a96  mov     [rbx+150h], r13
0x180052a9d  mov     r13, rdx
0x180052aa0  xor     r9d, r9d
0x180052aa3  movzx   edx, word ptr [rbx+160h]
0x180052aaa  xor     r8d, r8d
0x180052aad  call    WaUpdateDnsQueryResultIndexByPort
0x180052ab2  mov     edx, eax
0x180052ab4  mov     rcx, rbx
0x180052ab7  call    WapTcpFindValidAddressForInterface
0x180052abc  mov     ebp, eax
0x180052abe  mov     [rsp+0D8h+var_80], ebp
0x180052ac2  cmp     [rbx+163h], r12b
0x180052ac9  jnz     loc_180052CCE
0x180052acf  mov     rcx, [rbx+150h]
0x180052ad6  mov     rax, [rcx+60h]
0x180052ada  mov     [rbx+458h], rax
0x180052ae1  mov     rax, [rcx+68h]
0x180052ae5  mov     [rbx+460h], rax
0x180052aec  mov     al, [rcx+58h]
0x180052aef  mov     [rbx+164h], al
0x180052af5  mov     rax, [rcx+70h]
0x180052af9  lea     rcx, [rsp+0D8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180052afe  mov     [rbx+180h], rax
0x180052b05  call    cs:__imp_GetSystemTimeAsFileTime
0x180052b0c  nop     dword ptr [rax+rax+00h]
0x180052b11  mov     rax, qword ptr [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime]
0x180052b16  mov     bpl, 1
0x180052b19  mov     [rbx+188h], rax
0x180052b20  mov     dword ptr [rbx+0E0h], 2
0x180052b2a  jmp     loc_1800529F1
0x180052b2f  mov     eax, [rdi+158h]
0x180052b35  mov     rcx, r14; lpCriticalSection
0x180052b38  mov     rbp, [rdi+60h]
0x180052b3c  mov     r12, [rdi+58h]
0x180052b40  mov     esi, [rdi+140h]
0x180052b46  mov     [rsp+0D8h+var_84], eax
0x180052b4a  mov     rax, [rdi+150h]
0x180052b51  mov     [rsp+0D8h+var_70], rax
0x180052b56  mov     eax, [rdi+148h]
0x180052b5c  mov     [rsp+0D8h+var_78], eax
0x180052b60  mov     eax, [rdi+144h]
0x180052b66  mov     [rsp+0D8h+var_7C], eax
0x180052b6a  call    cs:__imp_EnterCriticalSection
0x180052b71  nop     dword ptr [rax+rax+00h]
0x180052b76  cmp     dword ptr [rbx+0E0h], 2
0x180052b7d  jnz     loc_180052ECF
0x180052b83  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 40h
0x180052b8a  jnz     loc_180052D45
0x180052b90  mov     [rsp+0D8h+var_B0], rbp; __int64
0x180052b95  lea     r9, WapTcpConnectCompletionRoutine
0x180052b9c  mov     r8d, 1
0x180052ba2  mov     [rsp+0D8h+var_B8], r12; __int64
0x180052ba7  mov     rdx, rbx
0x180052baa  mov     ecx, 160h; Size
0x180052baf  call    WapTcpAllocateIoContext
0x180052bb4  xor     ecx, ecx
0x180052bb6  mov     rbp, rax
0x180052bb9  test    rax, rax
0x180052bbc  jz      loc_180052EE8
0x180052bc2  mov     rax, [rdi+138h]
0x180052bc9  mov     edx, [rsp+0D8h+var_80]
0x180052bcd  mov     [rbp+0C8h], rax
0x180052bd4  mov     [rdi+138h], rcx
0x180052bdb  mov     rax, [rdi+130h]
0x180052be2  mov     [rbp+0C0h], rax
0x180052be9  mov     eax, [rsp+0D8h+var_7C]
0x180052bed  mov     [rdi+130h], rcx
0x180052bf4  mov     [rbp+0D8h], eax
0x180052bfa  mov     eax, [rsp+0D8h+var_78]
0x180052bfe  mov     [rbp+0DCh], eax
0x180052c04  mov     rax, [rsp+0D8h+var_70]
0x180052c09  mov     [rbp+0E0h], rax
0x180052c10  mov     eax, [rsp+0D8h+var_84]
0x180052c14  mov     [rbp+0E8h], eax
0x180052c1a  mov     [rbp+0D0h], edx
0x180052c20  mov     [rbp+0D4h], esi
0x180052c26  test    esi, esi
0x180052c28  jz      loc_180052F13
0x180052c2e  mov     rcx, [rbx+150h]
0x180052c35  cmp     rdx, [rcx+28h]
0x180052c39  jz      loc_180052F13
0x180052c3f  mov     rdx, rbp
0x180052c42  mov     rcx, rbx
0x180052c45  call    WapTcpAllocateSocket
0x180052c4a  mov     esi, eax
0x180052c4c  mov     rcx, r14; lpCriticalSection
0x180052c4f  test    eax, eax
0x180052c51  jnz     loc_180052D92
0x180052c57  mov     [rbx+2B0h], rbp
0x180052c5e  mov     dword ptr [rbx+0E0h], 3
0x180052c68  call    cs:__imp_LeaveCriticalSection
0x180052c6f  nop     dword ptr [rax+rax+00h]
0x180052c74  mov     rdx, rbp
0x180052c77  mov     rcx, rbx
0x180052c7a  call    WapTcpConnectSocket
0x180052c7f  cmp     eax, 3E5h
0x180052c84  jnz     loc_180052F01
0x180052c8a  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x180052c91  jnz     loc_180052D2A
0x180052c97  mov     byte ptr [rdi+7Ch], 1
0x180052c9b  xor     esi, esi
0x180052c9d  jmp     loc_180052A12
0x180052ca2  mov     r13, rax
0x180052ca5  mov     dword ptr [rbx+12Ch], 3
0x180052caf  mov     dword ptr [rbx+130h], 2
0x180052cb9  mov     dword ptr [rbx+134h], 1
0x180052cc3  mov     [rbx+128h], esi
0x180052cc9  jmp     loc_1800529BE
0x180052cce  cmp     dword ptr [rbx+15Ch], 1
0x180052cd5  jnz     loc_180052ACF
0x180052cdb  cmp     [rdi+140h], r13d
0x180052ce2  jbe     loc_180052ACF
0x180052ce8  mov     rdx, [rbx+150h]
0x180052cef  cmp     rbp, [rdx+28h]
0x180052cf3  jnz     loc_180052ACF
0x180052cf9  test    byte ptr cs:xmmword_1800AD720, 8
0x180052d00  jz      short loc_180052D18
0x180052d02  mov     edx, 14h
0x180052d07  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x180052d0e  mov     ecx, 403h
0x180052d13  call    WPP_SF_
0x180052d18  mov     [rbx+0E0h], r13d
0x180052d1f  mov     r12b, 1
0x180052d22  mov     bpl, r13b
0x180052d25  jmp     loc_1800529F1
0x180052d2a  lea     r8, [rbp+10h]
0x180052d2e  mov     r9d, 3
0x180052d34  lea     rdx, ThreadActionQueue
0x180052d3b  call    McTemplateU0pq_EventWriteTransfer
0x180052d40  jmp     loc_180052C97
0x180052d45  mov     rax, [rbx+8]
0x180052d49  lea     rdx, ConnectionTCPConnect
0x180052d50  mov     [rsp+0D8h+var_68], rax
0x180052d55  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180052d5c  lea     rax, [rsp+0D8h+var_68]
0x180052d61  mov     [rsp+0D8h+var_40], 8
0x180052d6d  mov     [rsp+0D8h+var_48], rax
0x180052d75  mov     r9d, 2
0x180052d7b  lea     rax, [rsp+0D8h+var_58]
0x180052d83  mov     [rsp+0D8h+var_B8], rax
0x180052d88  call    McGenEventWrite_EventWriteTransfer
0x180052d8d  jmp     loc_180052B90
0x180052d92  call    cs:__imp_LeaveCriticalSection
0x180052d99  nop     dword ptr [rax+rax+00h]
0x180052d9e  or      eax, 0FFFFFFFFh
0x180052da1  mov     byte ptr [rbp+7Ch], 1
0x180052da5  lock xadd [rbp+4], eax
0x180052daa  cmp     eax, 1
0x180052dad  jnz     short loc_180052DB7
0x180052daf  mov     rcx, rbp; lpMem
0x180052db2  call    WapTcpFreeIoContext
0x180052db7  cmp     esi, 3E5h
0x180052dbd  jz      loc_180052C97
0x180052dc3  jmp     loc_180052A12
0x180052dc8  mov     esi, [rbx+0E8h]
0x180052dce  mov     eax, 54Fh
0x180052dd3  test    esi, esi
0x180052dd5  cmovz   esi, eax
0x180052dd8  jmp     loc_1800529F1
0x180052ddd  movzx   eax, word ptr [rbx+3D8h]
0x180052de4  test    ax, ax
0x180052de7  jz      loc_180052A93
0x180052ded  cmp     ax, [rbp+0]
0x180052df1  jz      loc_180052A93
0x180052df7  mov     esi, 57h ; 'W'
0x180052dfc  mov     dword ptr [rbx+12Ch], 3
0x180052e06  mov     [rbx+128h], esi
0x180052e0c  mov     dword ptr [rbx+130h], 3
0x180052e16  mov     dword ptr [rbx+134h], 1
0x180052e20  mov     [rbx+0E0h], edx
0x180052e26  mov     bpl, dl
0x180052e29  jmp     loc_1800529F1
0x180052e2e  mov     rax, [rdi+60h]
0x180052e32  mov     rcx, rbx
0x180052e35  mov     r9d, [rdi+140h]
0x180052e3c  mov     r8, [rdi+138h]
0x180052e43  mov     rdx, [rdi+130h]
0x180052e4a  mov     [rsp+0D8h+var_90], rax
0x180052e4f  mov     rax, [rdi+58h]
0x180052e53  mov     [rsp+0D8h+var_98], rax
0x180052e58  mov     eax, [rdi+158h]
0x180052e5e  mov     [rsp+0D8h+var_A0], eax
0x180052e62  mov     rax, [rdi+150h]
0x180052e69  mov     [rsp+0D8h+var_A8], rax
0x180052e6e  mov     eax, [rdi+148h]
0x180052e74  mov     dword ptr [rsp+0D8h+var_B0], eax
0x180052e78  mov     eax, [rdi+144h]
0x180052e7e  mov     dword ptr [rsp+0D8h+var_B8], eax
0x180052e82  call    WapTcpStartDnsQuery
0x180052e87  mov     esi, eax
0x180052e89  cmp     eax, 3E5h
0x180052e8e  jnz     loc_180052A12
0x180052e94  mov     byte ptr [rdi+7Ch], 1
0x180052e98  jmp     loc_180052A12
0x180052e9d  mov     rcx, r14; lpCriticalSection
0x180052ea0  call    cs:__imp_LeaveCriticalSection
0x180052ea7  nop     dword ptr [rax+rax+00h]
0x180052eac  or      eax, 0FFFFFFFFh
0x180052eaf  mov     byte ptr [rbp+7Ch], 1
0x180052eb3  lock xadd [rbp+4], eax
0x180052eb8  cmp     eax, 1
0x180052ebb  jnz     short loc_180052EC5
0x180052ebd  mov     rcx, rbp; lpMem
0x180052ec0  call    WapTcpFreeIoContext
0x180052ec5  mov     esi, 2751h
0x180052eca  jmp     loc_180052A12
0x180052ecf  mov     rcx, r14; lpCriticalSection
0x180052ed2  call    cs:__imp_LeaveCriticalSection
0x180052ed9  nop     dword ptr [rax+rax+00h]
0x180052ede  mov     esi, 139Fh
0x180052ee3  jmp     loc_180052A12
0x180052ee8  mov     rcx, r14; lpCriticalSection
0x180052eeb  call    cs:__imp_LeaveCriticalSection
0x180052ef2  nop     dword ptr [rax+rax+00h]
0x180052ef7  mov     esi, 8
0x180052efc  jmp     loc_180052A12
0x180052f01  xor     r8d, r8d
0x180052f04  mov     edx, eax
0x180052f06  mov     rcx, rbp
  ... truncated ...
```
