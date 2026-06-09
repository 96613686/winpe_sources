# HTTP_LOG_PIPE_CLIENT::Flush(void)

- ea: `0x18000921c`
- end: `0x18000954d`
- name: `?Flush@HTTP_LOG_PIPE_CLIENT@@AEAAJXZ`
- size: `817`
- prototype: `__int64 __fastcall(HTTP_LOG_PIPE_CLIENT *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180009ae4`
- `0x18000b6f0`
- `0x18000cf20`

## callees

- `0x180001008`
- `0x180001048`
- `0x180008cf4`
- `0x18000921c`
- `0x1800099e0`
- `0x18000e9a0`
- `0x180010010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x18000949a`
- `msvcrt!_ultow_s` at `0x18000949a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800093b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000945b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800093b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000945b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009385`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009431`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009385`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009431`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009474`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800094d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009474`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800094d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800092fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800092fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094ea`
- `iisutil!?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@HKKPEAXK1@Z` at `0x1800093e4`
- `iisutil!?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@HKKPEAXK1@Z` at `0x1800093e4`
- `iisutil!IISInitializeCriticalSection` at `0x1800092c9`
- `iisutil!IISInitializeCriticalSection` at `0x1800092c9`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800094cc`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800094cc`
- `iisutil!PuDbgPrintError` at `0x180009428`
- `iisutil!PuDbgPrintError` at `0x180009428`

## string_xrefs

- `0x18000941a`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\pipeclient.cpp`
- `0x1800093fd`: `Write Message failed\n`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_PIPE_CLIENT::Flush(HTTP_LOG_PIPE_CLIENT *this)
{
  _DWORD *v3; // rdi
  int v4; // eax
  __int64 i; // rbx
  void (__fastcall ***v6)(_QWORD); // rcx
  unsigned int v7; // ebp
  unsigned int v8; // ebp
  HANDLE ProcessHeap; // rax
  _DWORD *v10; // r14
  _DWORD *v11; // rdx
  __int64 j; // r8
  __int64 v13; // rcx
  signed __int32 v14; // eax
  HTTP_LOG_PIPE_CLIENT **v15; // rcx
  _QWORD *v16; // rdx
  void **v17; // rax
  __int64 v18; // rbx
  _QWORD *v19; // rbx
  HANDLE v20; // rax
  wchar_t *v21; // [rsp+40h] [rbp-48h] BYREF
  _DWORD *v22; // [rsp+48h] [rbp-40h]
  wchar_t Buffer[12]; // [rsp+50h] [rbp-38h] BYREF

  v21 = 0;
  if ( !*((_DWORD *)this + 20086) )
    return 0;
  v3 = operator new(0x138D8u);
  v22 = v3;
  if ( v3 )
  {
    v4 = *((_DWORD *)this + 20086);
    v3[4] = -1;
    *((_QWORD *)v3 + 3) = 0;
    v3[20010] = v4;
    *(_QWORD *)v3 = 0;
    *((_QWORD *)v3 + 1) = 0;
    for ( i = 0; (unsigned int)i < v3[20010]; i = (unsigned int)(i + 1) )
    {
      v6 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + i + 43);
      *(_QWORD *)&v3[2 * i + 10] = v6;
      (**v6)(v6);
    }
    IISInitializeCriticalSection(v3 + 20012);
  }
  else
  {
    v3 = 0;
  }
  if ( v3 )
  {
    v8 = 38 * *((_DWORD *)this + 20086) + 4;
    ProcessHeap = GetProcessHeap();
    v10 = HeapAlloc(ProcessHeap, 8u, v8);
    if ( !v10 )
    {
      HTTP_LOG_PIPE_CLIENT::ResetLogContextQueue(this);
      v7 = -2147024882;
      goto LABEL_29;
    }
    *v10 = *((_DWORD *)this + 20086);
    v11 = v10 + 1;
    for ( j = 0; (unsigned int)j < *((_DWORD *)this + 20086); j = (unsigned int)(j + 1) )
    {
      v13 = *((_QWORD *)this + j + 43);
      *v11 = 34;
      *(_OWORD *)(v11 + 1) = *(_OWORD *)(v13 + 889);
      *(_OWORD *)((char *)v11 + 21) = *(_OWORD *)(v13 + 905);
      v11 = (_DWORD *)((char *)v11 + 38);
    }
    HTTP_LOG_PIPE_CLIENT::ResetLogContextQueue(this);
    do
      v14 = _InterlockedIncrement((volatile signed __int32 *)this + 41);
    while ( !v14 );
    v3[4] = v14;
    AcquireSRWLockExclusive((PSRWLOCK)this + 27);
    v15 = (HTTP_LOG_PIPE_CLIENT **)*((_QWORD *)this + 26);
    if ( *v15 == (HTTP_LOG_PIPE_CLIENT *)((char *)this + 200) )
    {
      *(_QWORD *)v3 = (char *)this + 200;
      *((_QWORD *)v3 + 1) = v15;
      *v15 = (HTTP_LOG_PIPE_CLIENT *)v3;
      *((_QWORD *)this + 26) = v3;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 27);
      v7 = IPM2_MESSAGE_PIPE::WriteMessage(*((_QWORD *)this + 42), 4, 1, (unsigned int)v3[4], 0, 0, v8, v10, v21, v22);
      if ( (v7 & 0x80000000) == 0 )
      {
        v3 = 0;
        goto LABEL_25;
      }
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\pipeclient.cpp",
          1196,
          "HTTP_LOG_PIPE_CLIENT::Flush",
          v7,
          "Write Message failed\n");
      AcquireSRWLockExclusive((PSRWLOCK)this + 27);
      v16 = *(_QWORD **)v3;
      if ( *(_DWORD **)(*(_QWORD *)v3 + 8LL) == v3 )
      {
        v17 = (void **)*((_QWORD *)v3 + 1);
        if ( *v17 == v3 )
        {
          *v17 = v16;
          v16[1] = v17;
          ReleaseSRWLockExclusive((PSRWLOCK)this + 27);
          v18 = *((_QWORD *)g_pLogSvcAdmin + 244);
          if ( !v18 || GetTickCount64() - v18 > 0x36EE80 )
          {
            _ultow_s(*((_DWORD *)this + 38), Buffer, 0xBu, 10);
            v21 = Buffer;
            EVENT_LOG::LogEvent(
              (EVENT_LOG *)((char *)g_pLogSvcAdmin + 1896),
              0xC0001776,
              1u,
              (const unsigned __int16 **const)&v21,
              v7);
            v19 = g_pLogSvcAdmin;
            v19[244] = GetTickCount64();
          }
LABEL_25:
          v20 = GetProcessHeap();
          HeapFree(v20, 0, v10);
          if ( !v3 )
            return v7;
LABEL_29:
          HTTP_LOG_PENDING_CONTEXT::~HTTP_LOG_PENDING_CONTEXT((HTTP_LOG_PENDING_CONTEXT *)v3);
          operator delete(v3);
          return v7;
        }
      }
    }
    __fastfail(3u);
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18000921c  mov     [rsp+arg_8], rbx
0x180009221  mov     [rsp+arg_10], rbp
0x180009226  push    rsi
0x180009227  push    rdi
0x180009228  push    r14
0x18000922a  sub     rsp, 70h
0x18000922e  mov     rax, cs:__security_cookie
0x180009235  xor     rax, rsp
0x180009238  mov     [rsp+88h+var_20], rax
0x18000923d  mov     rsi, rcx
0x180009240  mov     [rsp+88h+var_48], 0
0x180009249  cmp     dword ptr [rcx+139D8h], 0
0x180009250  jnz     short loc_180009259
0x180009252  xor     eax, eax
0x180009254  jmp     loc_18000952B
0x180009259  mov     ecx, 138D8h; Size
0x18000925e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009263  mov     rdi, rax
0x180009266  mov     [rsp+88h+var_40], rax
0x18000926b  test    rax, rax
0x18000926e  jz      short loc_1800092D1
0x180009270  mov     eax, [rsi+139D8h]
0x180009276  mov     dword ptr [rdi+10h], 0FFFFFFFFh
0x18000927d  mov     qword ptr [rdi+18h], 0
0x180009285  mov     [rdi+138A8h], eax
0x18000928b  mov     qword ptr [rdi], 0
0x180009292  mov     qword ptr [rdi+8], 0
0x18000929a  xor     ebx, ebx
0x18000929c  test    eax, eax
0x18000929e  jz      short loc_1800092C2
0x1800092a0  mov     rcx, [rsi+rbx*8+158h]
0x1800092a8  mov     [rdi+rbx*8+28h], rcx
0x1800092ad  mov     rax, [rcx]
0x1800092b0  mov     rax, [rax]
0x1800092b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092b8  inc     ebx
0x1800092ba  cmp     ebx, [rdi+138A8h]
0x1800092c0  jb      short loc_1800092A0
0x1800092c2  lea     rcx, [rdi+138B0h]
0x1800092c9  call    cs:__imp_IISInitializeCriticalSection
0x1800092cf  jmp     short loc_1800092D3
0x1800092d1  xor     edi, edi
0x1800092d3  test    rdi, rdi
0x1800092d6  jnz     short loc_1800092E2
0x1800092d8  mov     ebp, 8007000Eh
0x1800092dd  jmp     loc_180009529
0x1800092e2  imul    ebp, [rsi+139D8h], 26h ; '&'
0x1800092e9  add     ebp, 4
0x1800092ec  call    cs:__imp_GetProcessHeap
0x1800092f2  mov     rcx, rax; hHeap
0x1800092f5  mov     r8d, ebp; dwBytes
0x1800092f8  mov     edx, 8; dwFlags
0x1800092fd  call    cs:__imp_HeapAlloc
0x180009303  mov     r14, rax
0x180009306  test    rax, rax
0x180009309  jz      loc_18000950C
0x18000930f  mov     eax, [rsi+139D8h]
0x180009315  mov     [r14], eax
0x180009318  lea     rdx, [r14+4]
0x18000931c  xor     r8d, r8d
0x18000931f  cmp     [rsi+139D8h], r8d
0x180009326  jbe     short loc_18000935E
0x180009328  mov     rcx, [rsi+r8*8+158h]
0x180009330  mov     dword ptr [rdx], 22h ; '"'
0x180009336  movups  xmm0, xmmword ptr [rcx+379h]
0x18000933d  movdqu  xmmword ptr [rdx+4], xmm0
0x180009342  movups  xmm1, xmmword ptr [rcx+389h]
0x180009349  movdqu  xmmword ptr [rdx+15h], xmm1
0x18000934e  lea     rdx, [rdx+26h]
0x180009352  inc     r8d
0x180009355  cmp     r8d, [rsi+139D8h]
0x18000935c  jb      short loc_180009328
0x18000935e  mov     rcx, rsi; this
0x180009361  call    ?ResetLogContextQueue@HTTP_LOG_PIPE_CLIENT@@AEAAXXZ; HTTP_LOG_PIPE_CLIENT::ResetLogContextQueue(void)
0x180009366  mov     eax, 1
0x18000936b  lock xadd [rsi+0A4h], eax
0x180009373  add     eax, 1
0x180009376  jz      short loc_180009366
0x180009378  mov     [rdi+10h], eax
0x18000937b  lea     rbx, [rsi+0D8h]
0x180009382  mov     rcx, rbx; SRWLock
0x180009385  call    cs:__imp_AcquireSRWLockExclusive
0x18000938b  lea     rax, [rsi+0C8h]
0x180009392  mov     rcx, [rax+8]
0x180009396  cmp     [rcx], rax
0x180009399  jnz     loc_180009505
0x18000939f  mov     [rdi], rax
0x1800093a2  mov     [rdi+8], rcx
0x1800093a6  mov     [rcx], rdi
0x1800093a9  mov     [rax+8], rdi
0x1800093ad  mov     rcx, rbx; SRWLock
0x1800093b0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800093b6  mov     [rsp+88h+var_50], r14
0x1800093bb  mov     [rsp+88h+var_58], ebp
0x1800093bf  mov     [rsp+88h+var_60], 0
0x1800093c8  mov     [rsp+88h+var_68], 0
0x1800093d0  mov     r9d, [rdi+10h]
0x1800093d4  mov     edx, 4
0x1800093d9  lea     r8d, [rdx-3]
0x1800093dd  mov     rcx, [rsi+150h]
0x1800093e4  call    cs:__imp_?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@HKKPEAXK1@Z; IPM2_MESSAGE_PIPE::WriteMessage(IPM2_OPCODE,int,ulong,ulong,void *,ulong,void *)
0x1800093ea  mov     ebp, eax
0x1800093ec  test    eax, eax
0x1800093ee  jns     loc_1800094E8
0x1800093f4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800093fb  jz      short loc_18000942E
0x1800093fd  lea     rax, aWriteMessageFa; "Write Message failed\n"
0x180009404  mov     [rsp+88h+var_60], rax
0x180009409  mov     [rsp+88h+var_68], ebp
0x18000940d  lea     r9, aHttpLogPipeCli; "HTTP_LOG_PIPE_CLIENT::Flush"
0x180009414  mov     r8d, 4ACh
0x18000941a  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180009421  mov     rcx, cs:g_pDebug
0x180009428  call    cs:__imp_PuDbgPrintError
0x18000942e  mov     rcx, rbx; SRWLock
0x180009431  call    cs:__imp_AcquireSRWLockExclusive
0x180009437  mov     rdx, [rdi]
0x18000943a  cmp     [rdx+8], rdi
0x18000943e  jnz     loc_180009505
0x180009444  mov     rax, [rdi+8]
0x180009448  cmp     [rax], rdi
0x18000944b  jnz     loc_180009505
0x180009451  mov     [rax], rdx
0x180009454  mov     [rdx+8], rax
0x180009458  mov     rcx, rbx; SRWLock
0x18000945b  call    cs:__imp_ReleaseSRWLockExclusive
0x180009461  mov     rax, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x180009468  mov     rbx, [rax+7A0h]
0x18000946f  test    rbx, rbx
0x180009472  jz      short loc_180009485
0x180009474  call    cs:__imp_GetTickCount64
0x18000947a  sub     rax, rbx
0x18000947d  cmp     rax, 36EE80h
0x180009483  jbe     short loc_1800094EA
0x180009485  mov     r9d, 0Ah; Radix
0x18000948b  lea     r8d, [r9+1]; BufferCount
0x18000948f  lea     rdx, [rsp+88h+Buffer]; Buffer
0x180009494  mov     ecx, [rsi+98h]; Value
0x18000949a  call    cs:__imp__ultow_s
0x1800094a0  lea     rax, [rsp+88h+Buffer]
0x1800094a5  mov     [rsp+88h+var_48], rax
0x1800094aa  mov     r8d, 1
0x1800094b0  mov     rcx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x1800094b7  add     rcx, 768h
0x1800094be  mov     [rsp+88h+var_68], ebp
0x1800094c2  lea     r9, [rsp+88h+var_48]
0x1800094c7  mov     edx, 0C0001776h
0x1800094cc  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800094d2  mov     rbx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x1800094d9  call    cs:__imp_GetTickCount64
0x1800094df  mov     [rbx+7A0h], rax
0x1800094e6  jmp     short loc_1800094EA
0x1800094e8  xor     edi, edi
0x1800094ea  call    cs:__imp_GetProcessHeap
0x1800094f0  mov     rcx, rax; hHeap
0x1800094f3  mov     r8, r14; lpMem
0x1800094f6  xor     edx, edx; dwFlags
0x1800094f8  call    cs:__imp_HeapFree
0x1800094fe  test    rdi, rdi
0x180009501  jz      short loc_180009529
0x180009503  jmp     short loc_180009519
0x180009505  mov     ecx, 3
0x18000950a  int     29h; Win8: RtlFailFast(ecx)
0x18000950c  mov     rcx, rsi; this
0x18000950f  call    ?ResetLogContextQueue@HTTP_LOG_PIPE_CLIENT@@AEAAXXZ; HTTP_LOG_PIPE_CLIENT::ResetLogContextQueue(void)
0x180009514  mov     ebp, 8007000Eh
0x180009519  mov     rcx, rdi; this
0x18000951c  call    ??1HTTP_LOG_PENDING_CONTEXT@@QEAA@XZ; HTTP_LOG_PENDING_CONTEXT::~HTTP_LOG_PENDING_CONTEXT(void)
0x180009521  mov     rcx, rdi; Block
0x180009524  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009529  mov     eax, ebp
0x18000952b  mov     rcx, [rsp+88h+var_20]
0x180009530  xor     rcx, rsp; StackCookie
0x180009533  call    __security_check_cookie
0x180009538  lea     r11, [rsp+88h+var_18]
0x18000953d  mov     rbx, [r11+28h]
0x180009541  mov     rbp, [r11+30h]
0x180009545  mov     rsp, r11
0x180009548  pop     r14
0x18000954a  pop     rdi
0x18000954b  pop     rsi
0x18000954c  retn
```
