# HTTP_LOG_PENDING_CONTEXT::HandleResponse(uchar *,ulong)

- ea: `0x180009720`
- end: `0x1800097f2`
- name: `?HandleResponse@HTTP_LOG_PENDING_CONTEXT@@QEAAXPEAEK@Z`
- size: `210`
- prototype: `void __fastcall(HTTP_LOG_PENDING_CONTEXT *this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009604`

## callees

- `0x180009720`
- `0x18000a2f8`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800097dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800097dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009793`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009793`
- `iisutil!PuDbgPrint` at `0x180009773`
- `iisutil!PuDbgPrint` at `0x180009773`

## string_xrefs

- `0x18000976c`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\pipeclient.cpp`

## pseudocode

```c
void __fastcall HTTP_LOG_PENDING_CONTEXT::HandleResponse(HTTP_LOG_PENDING_CONTEXT *this, unsigned __int8 *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  unsigned __int8 *v5; // r14
  unsigned __int8 *v6; // r15
  __int64 i; // r12
  HTTP_LOG_CONTEXT *v8; // rbx
  unsigned __int8 *v9; // rdx
  unsigned int v10; // r8d

  if ( *(_DWORD *)a2 == *((_DWORD *)this + 20010) )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 80048);
    v5 = &a2[*((unsigned int *)a2 + 1)];
    v6 = &a2[*((unsigned int *)a2 + 2)];
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 80048));
    for ( i = 0; (unsigned int)i < *(_DWORD *)a2; i = (unsigned int)(i + 1) )
    {
      v8 = (HTTP_LOG_CONTEXT *)*((_QWORD *)this + i + 5);
      v9 = &v6[*(unsigned int *)&v5[8 * i + 4]];
      v10 = *(_DWORD *)&v5[8 * i];
      *((_QWORD *)this + i + 5) = 0;
      HTTP_LOG_CONTEXT::HandleQueryCompletion(v8, v9, v10);
      (*(void (__fastcall **)(HTTP_LOG_CONTEXT *))(*(_QWORD *)v8 + 8LL))(v8);
    }
    LeaveCriticalSection(v4);
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\pipeclient.cpp",
      141,
      "HTTP_LOG_PENDING_CONTEXT::HandleResponse",
      "HandleResponse FAILED, Invalid data.\n");
  }
}

```

## disassembly

```asm
0x180009720  push    rbx
0x180009722  push    rbp
0x180009723  push    rsi
0x180009724  push    rdi
0x180009725  push    r12
0x180009727  push    r14
0x180009729  push    r15
0x18000972b  sub     rsp, 30h
0x18000972f  mov     eax, [rcx+138A8h]
0x180009735  mov     rdi, rdx
0x180009738  mov     rsi, rcx
0x18000973b  cmp     [rdx], eax
0x18000973d  jz      short loc_18000977B
0x18000973f  test    byte ptr cs:g_dwDebugFlags, 3
0x180009746  jz      loc_1800097E3
0x18000974c  mov     rcx, cs:g_pDebug
0x180009753  lea     rax, aHandleresponse; "HandleResponse FAILED, Invalid data.\n"
0x18000975a  lea     r9, aHttpLogPending; "HTTP_LOG_PENDING_CONTEXT::HandleRespons"...
0x180009761  mov     [rsp+68h+var_48], rax
0x180009766  mov     r8d, 8Dh
0x18000976c  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180009773  call    cs:__imp_PuDbgPrint
0x180009779  jmp     short loc_1800097E3
0x18000977b  mov     r14d, [rdx+4]
0x18000977f  lea     rbp, [rcx+138B0h]
0x180009786  mov     r15d, [rdx+8]
0x18000978a  mov     rcx, rbp; lpCriticalSection
0x18000978d  add     r14, rdi
0x180009790  add     r15, rdi
0x180009793  call    cs:__imp_EnterCriticalSection
0x180009799  xor     r12d, r12d
0x18000979c  cmp     [rdi], r12d
0x18000979f  jbe     short loc_1800097DA
0x1800097a1  mov     edx, [r14+r12*8+4]
0x1800097a6  mov     rbx, [rsi+r12*8+28h]
0x1800097ab  add     rdx, r15; void *
0x1800097ae  mov     r8d, [r14+r12*8]; unsigned int
0x1800097b2  mov     rcx, rbx; this
0x1800097b5  mov     qword ptr [rsi+r12*8+28h], 0
0x1800097be  call    ?HandleQueryCompletion@HTTP_LOG_CONTEXT@@QEAAJPEAXK@Z; HTTP_LOG_CONTEXT::HandleQueryCompletion(void *,ulong)
0x1800097c3  mov     rax, [rbx]
0x1800097c6  mov     rcx, rbx
0x1800097c9  mov     rax, [rax+8]
0x1800097cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097d2  inc     r12d
0x1800097d5  cmp     r12d, [rdi]
0x1800097d8  jb      short loc_1800097A1
0x1800097da  mov     rcx, rbp; lpCriticalSection
0x1800097dd  call    cs:__imp_LeaveCriticalSection
0x1800097e3  add     rsp, 30h
0x1800097e7  pop     r15
0x1800097e9  pop     r14
0x1800097eb  pop     r12
0x1800097ed  pop     rdi
0x1800097ee  pop     rsi
0x1800097ef  pop     rbp
0x1800097f0  pop     rbx
0x1800097f1  retn
```
