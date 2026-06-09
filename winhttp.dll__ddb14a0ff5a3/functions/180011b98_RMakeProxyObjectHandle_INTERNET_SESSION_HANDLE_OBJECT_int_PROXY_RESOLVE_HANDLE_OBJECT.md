# RMakeProxyObjectHandle(INTERNET_SESSION_HANDLE_OBJECT *,int,PROXY_RESOLVE_HANDLE_OBJECT * *)

- ea: `0x180011b98`
- end: `0x180011f7c`
- name: `?RMakeProxyObjectHandle@@YAKPEAVINTERNET_SESSION_HANDLE_OBJECT@@HPEAPEAVPROXY_RESOLVE_HANDLE_OBJECT@@@Z`
- size: `996`
- prototype: `unsigned int __fastcall(struct INTERNET_SESSION_HANDLE_OBJECT *, int, struct PROXY_RESOLVE_HANDLE_OBJECT **)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000ec00`
- `0x180023de0`

## callees

- `0x180004720`
- `0x1800065a0`
- `0x180011b98`
- `0x180012ad0`
- `0x180013680`
- `0x180013d70`
- `0x1800241a0`
- `0x180039120`
- `0x18007dc8c`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800cf008`
- `0x1800db704`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011d45`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011d45`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011d2c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011d2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011be5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011be5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011cc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011cc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011ccc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e7e`

## pseudocode

```c
__int64 __fastcall RMakeProxyObjectHandle(
        struct INTERNET_SESSION_HANDLE_OBJECT *a1,
        int a2,
        struct PROXY_RESOLVE_HANDLE_OBJECT **a3)
{
  struct PROXY_RESOLVE_HANDLE_OBJECT **v3; // rsi
  int v4; // edi
  char *v6; // rax
  char *v7; // r14
  int v8; // edi
  signed __int32 v9; // esi
  DWORD CurrentProcessId; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v12; // r15
  __int64 v13; // rbx
  int v14; // r12d
  __int64 v15; // rdi
  __int64 v16; // rsi
  int v17; // r13d
  unsigned int InvalidNotificationEvent; // eax
  HANDLE EventW; // rbp
  unsigned __int64 v20; // rdx
  unsigned int v21; // r9d
  unsigned int v22; // ebx
  HINTERNET hInternet; // [rsp+30h] [rbp-48h] BYREF

  v3 = a3;
  v4 = a2;
  hInternet = 0;
  v6 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x370u);
  v7 = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 0x370u);
    INTERNET_HANDLE_BASE::INTERNET_HANDLE_BASE((INTERNET_HANDLE_BASE *)v7, a1);
    *(_QWORD *)v7 = &PROXY_RESOLVE_HANDLE_OBJECT::`vftable'{for `INTERNET_HANDLE_BASE'};
    *((_QWORD *)v7 + 47) = &PROXY_RESOLVE_HANDLE_OBJECT::`vftable'{for `IHttpAsyncCallback'};
    *((_QWORD *)v7 + 55) = 0;
    *((_QWORD *)v7 + 57) = 0;
    *((_QWORD *)v7 + 56) = 0;
    *((_OWORD *)v7 + 29) = 0;
    *((_QWORD *)v7 + 54) = &HTTP_THREAD_POOL::WORK_ITEM::`vftable';
    *((_QWORD *)v7 + 63) = 0;
    *((_QWORD *)v7 + 84) = 0;
    *((_QWORD *)v7 + 85) = 0;
    *((_QWORD *)v7 + 86) = 0;
    *((_QWORD *)v7 + 97) = 0;
    *((_QWORD *)v7 + 98) = 0;
    *((_QWORD *)v7 + 62) = 0;
    if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
      WPP_SF_q(1032, 11, WPP_c838bc99915f32a6844c5bb5f02cb47c_Traceguids);
    if ( !*((_DWORD *)v7 + 18) )
    {
      *((_DWORD *)v7 + 10) = 2037936720;
      if ( v7 != (char *)-184LL )
      {
        v8 = *((_DWORD *)v7 + 8);
        v9 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
        CurrentProcessId = GetCurrentProcessId();
        CurrentThreadId = GetCurrentThreadId();
        *((_DWORD *)v7 + 46) = v8;
        *((_DWORD *)v7 + 48) = CurrentProcessId ^ (CurrentThreadId << 16);
        *((_DWORD *)v7 + 47) = v9;
        *((_DWORD *)v7 + 49) = (_DWORD)v7;
      }
      v12 = *((unsigned int *)a1 + 95);
      v13 = *((unsigned int *)a1 + 96);
      v14 = *((_DWORD *)a1 + 97);
      v15 = *((unsigned int *)a1 + 98);
      v16 = *((unsigned int *)a1 + 99);
      v17 = *((_DWORD *)a1 + 114);
      InvalidNotificationEvent = HANDLE_OBJECT::CreateInvalidNotificationEvent((HANDLE_OBJECT *)v7);
      *((_DWORD *)v7 + 18) = InvalidNotificationEvent;
      if ( !InvalidNotificationEvent )
      {
        EventW = CreateEventW(0, 1, 0, 0);
        if ( EventW )
        {
          InitializeCriticalSection((LPCRITICAL_SECTION)(v7 + 384));
          *((_QWORD *)v7 + 63) = EventW;
          *((_DWORD *)v7 + 159) = v12;
          *((_DWORD *)v7 + 160) = v13;
          *((_DWORD *)v7 + 161) = v14;
          *((_DWORD *)v7 + 162) = v15;
          *((_DWORD *)v7 + 163) = v16;
          *((_DWORD *)v7 + 164) = v17;
          *(_OWORD *)(v7 + 696) = 0;
          *(_OWORD *)(v7 + 712) = 0;
          *(_OWORD *)(v7 + 728) = 0;
          *((_QWORD *)v7 + 93) = 0;
          if ( (_DWORD)v12 == -1 || (_DWORD)v13 == -1 || (_DWORD)v16 == -1 || (_DWORD)v15 == -1 )
          {
            LODWORD(v20) = -1;
          }
          else
          {
            v20 = v12 + v13 + v15 + v16;
            if ( v20 >= 0xFFFFFFFF )
              LODWORD(v20) = -2;
          }
          *((_DWORD *)v7 + 165) = v20;
          *((_QWORD *)v7 + 62) = 0;
          *((_QWORD *)v7 + 53) = 0;
          *((_DWORD *)v7 + 128) = 0;
          *((_DWORD *)v7 + 129) = 5023;
          *((_DWORD *)v7 + 158) = 0;
          *((_QWORD *)v7 + 94) = 0;
          *((_QWORD *)v7 + 95) = 0;
          *((_DWORD *)v7 + 166) = 0x1000000;
          *((_QWORD *)v7 + 96) = 0;
          memset_0(v7 + 792, 0, 0x48u);
          *((_DWORD *)v7 + 216) = 0;
        }
        else
        {
          *((_DWORD *)v7 + 18) = GetLastError();
        }
      }
      v4 = a2;
      v3 = a3;
    }
    if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
      WPP_SF_(1032, 12, WPP_c838bc99915f32a6844c5bb5f02cb47c_Traceguids);
  }
  else
  {
    v7 = 0;
  }
  if ( v7 )
  {
    HANDLE_OBJECT::Reference((HANDLE_OBJECT *)v7);
    v22 = *((_DWORD *)v7 + 18);
    if ( v22 )
    {
      HANDLE_OBJECT::Invalidate((HANDLE_OBJECT *)v7);
      *((_QWORD *)v7 + 21) = 0;
      *((_QWORD *)v7 + 22) = 0;
      HANDLE_OBJECT::Dereference((HANDLE_OBJECT *)v7);
      HANDLE_OBJECT::Dereference((HANDLE_OBJECT *)v7);
    }
    else if ( v4
           && (hInternet = (HINTERNET)*((_QWORD *)v7 + 4),
               INTERNET_HANDLE_BASE::IndicateStatus((INTERNET_HANDLE_BASE *)v7, 0x400u, &hInternet, v21),
               (unsigned int)HANDLE_OBJECT::IsInvalidated((HANDLE_OBJECT *)v7)) )
    {
      WinHttpCloseHandle(hInternet);
      HANDLE_OBJECT::Dereference((HANDLE_OBJECT *)v7);
      return 12017;
    }
    else
    {
      *v3 = (struct PROXY_RESOLVE_HANDLE_OBJECT *)v7;
    }
  }
  else
  {
    return 8;
  }
  return v22;
}

```

## disassembly

```asm
0x180011b98  mov     [rsp+arg_8], rbx
0x180011b9d  push    rbp
0x180011b9e  push    rsi
0x180011b9f  push    rdi
0x180011ba0  push    r12
0x180011ba2  push    r13
0x180011ba4  push    r14
0x180011ba6  push    r15
0x180011ba8  sub     rsp, 40h
0x180011bac  mov     rax, cs:__security_cookie
0x180011bb3  xor     rax, rsp
0x180011bb6  mov     [rsp+78h+var_40], rax
0x180011bbb  mov     rsi, r8
0x180011bbe  mov     [rsp+78h+var_50], r8
0x180011bc3  mov     edi, edx
0x180011bc5  mov     [rsp+78h+var_58], edx
0x180011bc9  mov     rbp, rcx
0x180011bcc  mov     ebx, 370h
0x180011bd1  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180011bd8  xor     r12d, r12d
0x180011bdb  mov     r8d, ebx; dwBytes
0x180011bde  mov     [rsp+78h+hInternet], r12
0x180011be3  xor     edx, edx; dwFlags
0x180011be5  call    cs:__imp_HeapAlloc
0x180011beb  mov     r14, rax
0x180011bee  test    rax, rax
0x180011bf1  jz      loc_180011F0C
0x180011bf7  mov     r8d, ebx; Size
0x180011bfa  xor     edx, edx; Val
0x180011bfc  mov     rcx, rax; void *
0x180011bff  call    memset_0
0x180011c04  mov     rdx, rbp; struct INTERNET_HANDLE_BASE *
0x180011c07  mov     rcx, r14; this
0x180011c0a  call    ??0INTERNET_HANDLE_BASE@@QEAA@PEAV0@@Z; INTERNET_HANDLE_BASE::INTERNET_HANDLE_BASE(INTERNET_HANDLE_BASE *)
0x180011c0f  lea     rax, ??_7PROXY_RESOLVE_HANDLE_OBJECT@@6BINTERNET_HANDLE_BASE@@@; const PROXY_RESOLVE_HANDLE_OBJECT::`vftable'{for `INTERNET_HANDLE_BASE'}
0x180011c16  xorps   xmm0, xmm0
0x180011c19  mov     [r14], rax
0x180011c1c  lea     rax, ??_7PROXY_RESOLVE_HANDLE_OBJECT@@6BIHttpAsyncCallback@@@; const PROXY_RESOLVE_HANDLE_OBJECT::`vftable'{for `IHttpAsyncCallback'}
0x180011c23  mov     [r14+178h], rax
0x180011c2a  lea     rax, ??_7WORK_ITEM@HTTP_THREAD_POOL@@6B@; const HTTP_THREAD_POOL::WORK_ITEM::`vftable'
0x180011c31  mov     [r14+1B8h], r12
0x180011c38  mov     [r14+1C8h], r12
0x180011c3f  mov     [r14+1C0h], r12
0x180011c46  movups  xmmword ptr [r14+1D0h], xmm0
0x180011c4e  mov     [r14+1B0h], rax
0x180011c55  mov     [r14+1F8h], r12
0x180011c5c  mov     [r14+2A0h], r12
0x180011c63  mov     [r14+2A8h], r12
0x180011c6a  mov     [r14+2B0h], r12
0x180011c71  mov     [r14+308h], r12
0x180011c78  mov     [r14+310h], r12
0x180011c7f  mov     [r14+1F0h], r12
0x180011c86  test    byte ptr cs:xmmword_180107A60+1, 1
0x180011c8d  jnz     loc_180011F14
0x180011c93  cmp     [r14+48h], r12d
0x180011c97  jnz     loc_180011E26
0x180011c9d  lea     r15, [r14+0B8h]
0x180011ca4  mov     dword ptr [r14+28h], 79787250h
0x180011cac  test    r15, r15
0x180011caf  jz      short loc_180011CE6
0x180011cb1  mov     edi, [r14+20h]
0x180011cb5  mov     esi, 1
0x180011cba  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x180011cc2  inc     esi
0x180011cc4  call    cs:__imp_GetCurrentProcessId
0x180011cca  mov     ebx, eax
0x180011ccc  call    cs:__imp_GetCurrentThreadId
0x180011cd2  shl     eax, 10h
0x180011cd5  xor     eax, ebx
0x180011cd7  mov     [r15], edi
0x180011cda  mov     [r15+8], eax
0x180011cde  mov     [r15+4], esi
0x180011ce2  mov     [r15+0Ch], r14d
0x180011ce6  mov     r15d, [rbp+17Ch]
0x180011ced  mov     rcx, r14; this
0x180011cf0  mov     ebx, [rbp+180h]
0x180011cf6  mov     r12d, [rbp+184h]
0x180011cfd  mov     edi, [rbp+188h]
0x180011d03  mov     esi, [rbp+18Ch]
0x180011d09  mov     r13d, [rbp+1C8h]
0x180011d10  call    ?CreateInvalidNotificationEvent@HANDLE_OBJECT@@QEAAKXZ; HANDLE_OBJECT::CreateInvalidNotificationEvent(void)
0x180011d15  mov     [r14+48h], eax
0x180011d19  test    eax, eax
0x180011d1b  jnz     loc_180011E88
0x180011d21  xor     r9d, r9d; lpName
0x180011d24  lea     edx, [rax+1]; bManualReset
0x180011d27  xor     r8d, r8d; bInitialState
0x180011d2a  xor     ecx, ecx; lpEventAttributes
0x180011d2c  call    cs:__imp_CreateEventW
0x180011d32  mov     rbp, rax
0x180011d35  test    rax, rax
0x180011d38  jz      loc_180011E7E
0x180011d3e  lea     rcx, [r14+180h]; lpCriticalSection
0x180011d45  call    cs:__imp_InitializeCriticalSection
0x180011d4b  mov     [r14+1F8h], rbp
0x180011d52  xorps   xmm0, xmm0
0x180011d55  mov     [r14+27Ch], r15d
0x180011d5c  xor     eax, eax
0x180011d5e  mov     [r14+280h], ebx
0x180011d65  mov     r8d, 0FFFFFFFFh
0x180011d6b  mov     [r14+284h], r12d
0x180011d72  mov     [r14+288h], edi
0x180011d79  mov     [r14+28Ch], esi
0x180011d80  mov     [r14+290h], r13d
0x180011d87  movups  xmmword ptr [r14+2B8h], xmm0
0x180011d8f  movups  xmmword ptr [r14+2C8h], xmm0
0x180011d97  movups  xmmword ptr [r14+2D8h], xmm0
0x180011d9f  mov     [r14+2E8h], rax
0x180011da6  cmp     r15d, r8d
0x180011da9  jnz     loc_180011ED4
0x180011daf  mov     edx, r8d
0x180011db2  xor     r12d, r12d
0x180011db5  mov     [r14+294h], edx
0x180011dbc  lea     rcx, [r14+318h]; void *
0x180011dc3  mov     [r14+1F0h], r12
0x180011dca  xor     edx, edx; Val
0x180011dcc  mov     [r14+1A8h], r12
0x180011dd3  mov     [r14+200h], r12d
0x180011dda  lea     r8d, [r12+48h]; Size
0x180011ddf  mov     dword ptr [r14+204h], 139Fh
0x180011dea  mov     [r14+278h], r12d
0x180011df1  mov     [r14+2F0h], r12
0x180011df8  mov     [r14+2F8h], r12
0x180011dff  mov     dword ptr [r14+298h], 1000000h
0x180011e0a  mov     [r14+300h], r12
0x180011e11  call    memset_0
0x180011e16  mov     [r14+360h], r12d
0x180011e1d  mov     edi, [rsp+78h+var_58]
0x180011e21  mov     rsi, [rsp+78h+var_50]
0x180011e26  test    byte ptr cs:xmmword_180107A60+1, 1
0x180011e2d  jnz     loc_180011F32
0x180011e33  test    r14, r14
0x180011e36  jz      loc_180011ECD
0x180011e3c  mov     rcx, r14; this
0x180011e3f  call    ?Reference@HANDLE_OBJECT@@QEAAKXZ; HANDLE_OBJECT::Reference(void)
0x180011e44  mov     ebx, [r14+48h]
0x180011e48  test    ebx, ebx
0x180011e4a  jnz     loc_180011F4D
0x180011e50  test    edi, edi
0x180011e52  jnz     short loc_180011E8D
0x180011e54  mov     [rsi], r14
0x180011e57  mov     eax, ebx
0x180011e59  mov     rcx, [rsp+78h+var_40]
0x180011e5e  xor     rcx, rsp; StackCookie
0x180011e61  call    __security_check_cookie
0x180011e66  mov     rbx, [rsp+78h+arg_8]
0x180011e6e  add     rsp, 40h
0x180011e72  pop     r15
0x180011e74  pop     r14
0x180011e76  pop     r13
0x180011e78  pop     r12
0x180011e7a  pop     rdi
0x180011e7b  pop     rsi
0x180011e7c  pop     rbp
0x180011e7d  retn
0x180011e7e  call    cs:__imp_GetLastError
0x180011e84  mov     [r14+48h], eax
0x180011e88  xor     r12d, r12d
0x180011e8b  jmp     short loc_180011E1D
0x180011e8d  mov     rax, [r14+20h]
0x180011e91  lea     r8, [rsp+78h+hInternet]; void *
0x180011e96  mov     edx, 400h; unsigned int
0x180011e9b  mov     [rsp+78h+hInternet], rax
0x180011ea0  mov     rcx, r14; this
0x180011ea3  call    ?IndicateStatus@INTERNET_HANDLE_BASE@@QEAAXKPEAXK@Z; INTERNET_HANDLE_BASE::IndicateStatus(ulong,void *,ulong)
0x180011ea8  mov     rcx, r14; this
0x180011eab  call    ?IsInvalidated@HANDLE_OBJECT@@QEBAHXZ; HANDLE_OBJECT::IsInvalidated(void)
0x180011eb0  test    eax, eax
0x180011eb2  jz      short loc_180011E54
0x180011eb4  mov     rcx, [rsp+78h+hInternet]; hInternet
0x180011eb9  call    WinHttpCloseHandle
0x180011ebe  mov     rcx, r14; this
0x180011ec1  call    ?Dereference@HANDLE_OBJECT@@QEAAHXZ; HANDLE_OBJECT::Dereference(void)
0x180011ec6  mov     ebx, 2EF1h
0x180011ecb  jmp     short loc_180011E57
0x180011ecd  mov     ebx, 8
0x180011ed2  jmp     short loc_180011E57
0x180011ed4  cmp     ebx, r8d
0x180011ed7  jz      loc_180011DAF
0x180011edd  cmp     esi, r8d
0x180011ee0  jz      loc_180011DAF
0x180011ee6  cmp     edi, r8d
0x180011ee9  jz      loc_180011DAF
0x180011eef  lea     rdx, [rdi+rsi]
0x180011ef3  add     rdx, rbx
0x180011ef6  add     rdx, r15
0x180011ef9  cmp     rdx, r8
0x180011efc  jb      loc_180011DB2
0x180011f02  mov     edx, 0FFFFFFFEh
0x180011f07  jmp     loc_180011DB2
0x180011f0c  mov     r14, r12
0x180011f0f  jmp     loc_180011E33
0x180011f14  mov     edx, 0Bh
0x180011f19  lea     r8, WPP_c838bc99915f32a6844c5bb5f02cb47c_Traceguids
0x180011f20  mov     ecx, 408h
0x180011f25  mov     r9, rbp
0x180011f28  call    WPP_SF_q
0x180011f2d  jmp     loc_180011C93
0x180011f32  mov     edx, 0Ch
0x180011f37  lea     r8, WPP_c838bc99915f32a6844c5bb5f02cb47c_Traceguids
0x180011f3e  mov     ecx, 408h
0x180011f43  call    WPP_SF_
0x180011f48  jmp     loc_180011E33
0x180011f4d  mov     rcx, r14; this
0x180011f50  call    ?Invalidate@HANDLE_OBJECT@@QEAAXXZ; HANDLE_OBJECT::Invalidate(void)
0x180011f55  mov     rcx, r14; this
0x180011f58  mov     [r14+0A8h], r12
0x180011f5f  mov     qword ptr [r14+0B0h], 0
0x180011f6a  call    ?Dereference@HANDLE_OBJECT@@QEAAHXZ; HANDLE_OBJECT::Dereference(void)
0x180011f6f  mov     rcx, r14; this
0x180011f72  call    ?Dereference@HANDLE_OBJECT@@QEAAHXZ; HANDLE_OBJECT::Dereference(void)
0x180011f77  jmp     loc_180011E57
```
