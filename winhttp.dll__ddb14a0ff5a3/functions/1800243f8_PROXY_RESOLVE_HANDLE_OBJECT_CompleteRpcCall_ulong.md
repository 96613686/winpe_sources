# PROXY_RESOLVE_HANDLE_OBJECT::CompleteRpcCall(ulong)

- ea: `0x1800243f8`
- end: `0x1800246a6`
- name: `?CompleteRpcCall@PROXY_RESOLVE_HANDLE_OBJECT@@AEAAJK@Z`
- size: `686`
- prototype: `__int64 __fastcall(PROXY_RESOLVE_HANDLE_OBJECT *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800242d0`
- `0x18002622c`

## callees

- `0x1800243f8`
- `0x1800a1d10`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800244a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800244e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800244a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800244e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800244c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800244f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800244c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800244f6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800245b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800245b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800244b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800244b3`
- `ntdll!RtlNtStatusToDosError` at `0x18002466d`
- `ntdll!RtlNtStatusToDosError` at `0x18002466d`
- `RPCRT4!RpcAsyncCancelCall` at `0x180024568`
- `RPCRT4!RpcAsyncCancelCall` at `0x180024568`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180024445`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180024445`

## pseudocode

```c
__int64 __fastcall PROXY_RESOLVE_HANDLE_OBJECT::CompleteRpcCall(PROXY_RESOLVE_HANDLE_OBJECT *this, int a2)
{
  signed int v2; // edi
  struct _RPC_ASYNC_STATE *v3; // rsi
  unsigned int v6; // eax
  signed int v7; // esi
  ULONG v8; // ebx
  ULONG v9; // eax
  __int64 v10; // r9
  bool v12; // sf
  RPC_STATUS v13; // eax
  int v14; // ebx
  int v15; // ebx
  unsigned int v16; // edi
  __int64 Reply; // [rsp+20h] [rbp-28h] BYREF

  v2 = 0;
  v3 = (struct _RPC_ASYNC_STATE *)((char *)this + 520);
  Reply = 0;
  if ( a2 )
  {
    v13 = RpcAsyncCancelCall((PRPC_ASYNC_STATE)((char *)this + 520), 1);
    v2 = v13;
    if ( v13 > 0 )
      v2 = (unsigned __int16)v13 | 0x80070000;
    if ( v2 < 0 )
    {
      HIDWORD(Reply) = 882;
      return (unsigned int)v2;
    }
    WaitForSingleObjectEx(*((HANDLE *)this + 63), 0xFFFFFFFF, 0);
  }
  v6 = RpcAsyncCompleteCall(v3, &Reply);
  v7 = v6;
  if ( v6 == 1818 )
  {
    v14 = a2 - 1;
    if ( v14 && (v15 = v14 - 1) != 0 )
    {
      if ( v15 == 256 )
        v16 = 12002;
      else
        v16 = 12004;
    }
    else
    {
      v16 = 12017;
    }
    if ( (xmmword_180107A50 & 2) != 0 )
      WPP_SF_d(513, 16, WPP_c838bc99915f32a6844c5bb5f02cb47c_Traceguids, v16, Reply);
    v2 = v16 | 0x80070000;
    HIDWORD(Reply) = 906;
  }
  else
  {
    if ( !v6 )
      goto LABEL_4;
    if ( (xmmword_180107A50 & 2) != 0 )
      WPP_SF_d(513, 17, WPP_c838bc99915f32a6844c5bb5f02cb47c_Traceguids, v6, Reply);
    v2 = v7 <= 0 ? v7 : (unsigned __int16)v7 | 0x80070000;
    if ( v2 < 0 )
    {
      HIDWORD(Reply) = 914;
    }
    else
    {
LABEL_4:
      v8 = Reply;
      if ( (Reply & 0x1FFF0000) == 0xC0000 )
      {
        v9 = (unsigned __int16)Reply;
      }
      else if ( (int)Reply < 0 )
      {
        if ( (Reply & 0x1FFF0000) == 0x70000 )
        {
          v9 = (unsigned __int16)Reply;
          if ( !(_WORD)Reply )
            v9 = 317;
        }
        else if ( (Reply & 0x10000000) == 0 || (v9 = RtlNtStatusToDosError(Reply & 0xEFFFFFFF)) == 0 || v9 == 317 )
        {
          v9 = v8;
        }
      }
      else
      {
        v9 = 0;
      }
      *((_DWORD *)this + 129) = v9;
      if ( v9 == 12017 || v9 == -2147467260 )
      {
        v2 = -2147023174;
        HIDWORD(Reply) = 927;
      }
      else
      {
        EnterCriticalSection(&g_csAPLock);
        g_fIsAPSvcAvailable = 1;
        g_ullAPSvcIdleTimeStamp = GetTickCount64();
        LeaveCriticalSection(&g_csAPLock);
        v10 = *((unsigned int *)this + 129);
        if ( !(_DWORD)v10 )
          goto LABEL_10;
        if ( (xmmword_180107A50 & 2) != 0 )
          WPP_SF_d(513, 18, WPP_c838bc99915f32a6844c5bb5f02cb47c_Traceguids, v10, Reply);
        v2 = *((_DWORD *)this + 129);
        v12 = v2 < 0;
        if ( v2 > 0 )
        {
          v2 = (unsigned __int16)v2 | 0x80070000;
          v12 = v2 < 0;
        }
        if ( v12 )
        {
          HIDWORD(Reply) = 945;
        }
        else
        {
LABEL_10:
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
          *((_DWORD *)this + 107) = 1;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800243f8  mov     [rsp+arg_8], rbx
0x1800243fd  mov     [rsp+arg_10], rbp
0x180024402  push    rsi
0x180024403  push    rdi
0x180024404  push    r14
0x180024406  sub     rsp, 30h
0x18002440a  mov     rax, cs:__security_cookie
0x180024411  xor     rax, rsp
0x180024414  mov     [rsp+48h+var_20], rax
0x180024419  xor     edi, edi
0x18002441b  lea     rsi, [rcx+208h]
0x180024422  mov     [rsp+48h+var_24], edi
0x180024426  mov     ebx, edx
0x180024428  mov     [rsp+48h+Reply], edi
0x18002442c  mov     rbp, rcx
0x18002442f  mov     r14d, 80070000h
0x180024435  test    edx, edx
0x180024437  jnz     loc_180024560
0x18002443d  lea     rdx, [rsp+48h+Reply]; Reply
0x180024442  mov     rcx, rsi; pAsync
0x180024445  call    cs:__imp_RpcAsyncCompleteCall
0x18002444b  mov     esi, eax
0x18002444d  cmp     eax, 71Ah
0x180024452  jz      loc_1800245EC
0x180024458  test    eax, eax
0x18002445a  jnz     loc_1800245C0
0x180024460  mov     ebx, [rsp+48h+Reply]
0x180024464  mov     eax, ebx
0x180024466  and     eax, 1FFF0000h
0x18002446b  cmp     eax, 0C0000h
0x180024470  jz      loc_180024549
0x180024476  test    ebx, ebx
0x180024478  js      loc_18002458B
0x18002447e  xor     eax, eax
0x180024480  mov     [rbp+204h], eax
0x180024486  cmp     eax, 2EF1h
0x18002448b  jz      loc_180024551
0x180024491  cmp     eax, 80004004h
0x180024496  jz      loc_180024551
0x18002449c  lea     rcx, ?g_csAPLock@@3UCCritSec@@A; lpCriticalSection
0x1800244a3  call    cs:__imp_EnterCriticalSection
0x1800244a9  mov     cs:?g_fIsAPSvcAvailable@@3HA, 1; int g_fIsAPSvcAvailable
0x1800244b3  call    cs:__imp_GetTickCount64
0x1800244b9  lea     rcx, ?g_csAPLock@@3UCCritSec@@A; lpCriticalSection
0x1800244c0  mov     cs:?g_ullAPSvcIdleTimeStamp@@3_KA, rax; unsigned __int64 g_ullAPSvcIdleTimeStamp
0x1800244c7  call    cs:__imp_LeaveCriticalSection
0x1800244cd  mov     r9d, [rbp+204h]
0x1800244d4  test    r9d, r9d
0x1800244d7  jnz     short loc_18002451E
0x1800244d9  lea     rbx, [rbp+180h]
0x1800244e0  mov     rcx, rbx; lpCriticalSection
0x1800244e3  call    cs:__imp_EnterCriticalSection
0x1800244e9  mov     rcx, rbx; lpCriticalSection
0x1800244ec  mov     dword ptr [rbp+1ACh], 1
0x1800244f6  call    cs:__imp_LeaveCriticalSection
0x1800244fc  mov     eax, edi
0x1800244fe  mov     rcx, [rsp+48h+var_20]
0x180024503  xor     rcx, rsp; StackCookie
0x180024506  call    __security_check_cookie
0x18002450b  mov     rbx, [rsp+48h+arg_8]
0x180024510  mov     rbp, [rsp+48h+arg_10]
0x180024515  add     rsp, 30h
0x180024519  pop     r14
0x18002451b  pop     rdi
0x18002451c  pop     rsi
0x18002451d  retn
0x18002451e  test    byte ptr cs:xmmword_180107A50, 2
0x180024525  jnz     loc_18002468B
0x18002452b  mov     edi, [rbp+204h]
0x180024531  test    edi, edi
0x180024533  jle     short loc_18002453D
0x180024535  movzx   edi, di
0x180024538  or      edi, r14d
0x18002453b  test    edi, edi
0x18002453d  jns     short loc_1800244D9
0x18002453f  mov     [rsp+48h+var_24], 3B1h
0x180024547  jmp     short loc_1800244FC
0x180024549  movzx   eax, bx
0x18002454c  jmp     loc_180024480
0x180024551  mov     edi, 800706BAh
0x180024556  mov     [rsp+48h+var_24], 39Fh
0x18002455e  jmp     short loc_1800244FC
0x180024560  mov     edx, 1; fAbort
0x180024565  mov     rcx, rsi; pAsync
0x180024568  call    cs:__imp_RpcAsyncCancelCall
0x18002456e  mov     edi, eax
0x180024570  test    eax, eax
0x180024572  jle     short loc_18002457A
0x180024574  movzx   edi, ax
0x180024577  or      edi, r14d
0x18002457a  test    edi, edi
0x18002457c  jns     short loc_1800245A8
0x18002457e  mov     [rsp+48h+var_24], 372h
0x180024586  jmp     loc_1800244FC
0x18002458b  cmp     eax, 70000h
0x180024590  jnz     loc_180024661
0x180024596  movzx   eax, bx
0x180024599  mov     ecx, 13Dh
0x18002459e  test    eax, eax
0x1800245a0  cmovz   eax, ecx
0x1800245a3  jmp     loc_180024480
0x1800245a8  mov     rcx, [rbp+1F8h]; hHandle
0x1800245af  xor     r8d, r8d; bAlertable
0x1800245b2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800245b5  call    cs:__imp_WaitForSingleObjectEx
0x1800245bb  jmp     loc_18002443D
0x1800245c0  test    byte ptr cs:xmmword_180107A50, 2
0x1800245c7  jnz     short loc_180024643
0x1800245c9  test    esi, esi
0x1800245cb  jle     short loc_1800245E8
0x1800245cd  movzx   edi, si
0x1800245d0  or      edi, r14d
0x1800245d3  test    edi, edi
0x1800245d5  jns     loc_180024460
0x1800245db  mov     [rsp+48h+var_24], 392h
0x1800245e3  jmp     loc_1800244FC
0x1800245e8  mov     edi, esi
0x1800245ea  jmp     short loc_1800245D3
0x1800245ec  sub     ebx, 1
0x1800245ef  jz      short loc_18002460C
0x1800245f1  sub     ebx, 1
0x1800245f4  jz      short loc_18002460C
0x1800245f6  cmp     ebx, 100h
0x1800245fc  jz      short loc_180024605
0x1800245fe  mov     edi, 2EE4h
0x180024603  jmp     short loc_180024611
0x180024605  mov     edi, 2EE2h
0x18002460a  jmp     short loc_180024611
0x18002460c  mov     edi, 2EF1h
0x180024611  test    byte ptr cs:xmmword_180107A50, 2
0x180024618  jz      short loc_180024633
0x18002461a  mov     edx, 10h
0x18002461f  lea     r8, WPP_c838bc99915f32a6844c5bb5f02cb47c_Traceguids
0x180024626  mov     ecx, 201h
0x18002462b  mov     r9d, edi
0x18002462e  call    WPP_SF_d
0x180024633  or      edi, r14d
0x180024636  mov     [rsp+48h+var_24], 38Ah
0x18002463e  jmp     loc_1800244FC
0x180024643  mov     edx, 11h
0x180024648  lea     r8, WPP_c838bc99915f32a6844c5bb5f02cb47c_Traceguids
0x18002464f  mov     ecx, 201h
0x180024654  mov     r9d, esi
0x180024657  call    WPP_SF_d
0x18002465c  jmp     loc_1800245C9
0x180024661  bt      ebx, 1Ch
0x180024665  jnb     short loc_180024684
0x180024667  mov     ecx, ebx
0x180024669  btr     ecx, 1Ch; Status
0x18002466d  call    cs:__imp_RtlNtStatusToDosError
0x180024673  test    eax, eax
0x180024675  jz      short loc_180024684
0x180024677  mov     ecx, 13Dh
0x18002467c  cmp     eax, ecx
0x18002467e  jnz     loc_180024480
0x180024684  mov     eax, ebx
0x180024686  jmp     loc_180024480
0x18002468b  mov     edx, 12h
0x180024690  lea     r8, WPP_c838bc99915f32a6844c5bb5f02cb47c_Traceguids
0x180024697  mov     ecx, 201h
0x18002469c  call    WPP_SF_d
0x1800246a1  jmp     loc_18002452B
```
