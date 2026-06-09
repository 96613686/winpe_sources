# HTTP_LOG_EVENT_HANDLER::EvtRecCallback(_EVENT_RECORD *)

- ea: `0x18000e1a0`
- end: `0x18000e342`
- name: `?EvtRecCallback@HTTP_LOG_EVENT_HANDLER@@CAXPEAU_EVENT_RECORD@@@Z`
- size: `418`
- prototype: `void __fastcall(struct _EVENT_RECORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000e1a0`
- `0x18000e4c4`
- `0x18000e962`
- `0x18000e97a`
- `0x180010010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e2cc`
- `msvcrt!memcpy_s` at `0x18000e2cc`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000e2af`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000e2af`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000e1fc`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000e1fc`
- `iisutil!PuDbgPrintError` at `0x18000e323`
- `iisutil!PuDbgPrintError` at `0x18000e323`

## string_xrefs

- `0x18000e318`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\http_log_event_handler.cxx`

## pseudocode

```c
void __fastcall HTTP_LOG_EVENT_HANDLER::EvtRecCallback(struct _EVENT_RECORD *a1)
{
  void **v2; // rax
  void **v3; // rbx
  unsigned int UserDataLength; // esi
  PVOID UserData; // rdi
  int v6; // eax
  GUID Buf2; // [rsp+30h] [rbp-38h] BYREF

  if ( !*((_DWORD *)a1->UserContext + 56) )
  {
    Buf2 = a1->EventHeader.ProviderId;
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) && a1->EventHeader.EventDescriptor.Id == 1 )
    {
      v2 = (void **)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)HTTP_LOG_CONTEXT::sm_pAllocCacheHandler);
      v3 = v2;
      if ( v2 )
      {
        *v2 = &HTTP_LOG_CONTEXT::`vftable';
        *((_DWORD *)v2 + 2) = 1;
        *((_BYTE *)v2 + 304) = 0;
        v2[36] = v2 + 38;
        *((_DWORD *)v2 + 74) = 512;
        *((_WORD *)v2 + 150) = 256;
        v2[102] = 0;
        *((_DWORD *)v2 + 295) = 0;
        v2[148] = 0;
        *((_DWORD *)v2 + 298) = 0;
        memset_0(v2 + 103, 0, 0x62u);
        memset_0((char *)v3 + 922, 0, 0x100u);
        UserDataLength = a1->UserDataLength;
        UserData = a1->UserData;
        if ( BUFFER::Resize((BUFFER *)(v3 + 32), UserDataLength) )
        {
          memcpy_s(v3[36], *((unsigned int *)v3 + 74), UserData, UserDataLength);
          v6 = MULTI_WORK_QUEUE::GetAndQueueWorkItem(
                 (MULTI_WORK_QUEUE *)((char *)g_pLogSvcAdmin + 1584),
                 (struct MULTI_WORK_DISPATCH *)v3,
                 1u);
          if ( v6 >= 0 )
            return;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
              965,
              "HTTP_LOG_EVENT_HANDLER::EvtRecCallback",
              v6,
              "Couldn't queue HttpLogContextProcessETWWorkItem\n");
        }
        (*((void (__fastcall **)(void **))*v3 + 1))(v3);
      }
    }
  }
}

```

## disassembly

```asm
0x18000e1a0  push    rbx
0x18000e1a2  push    rsi
0x18000e1a3  push    rdi
0x18000e1a4  push    r14
0x18000e1a6  sub     rsp, 48h
0x18000e1aa  mov     rax, [rcx+68h]
0x18000e1ae  mov     rdi, rcx
0x18000e1b1  mov     edx, [rax+0E0h]
0x18000e1b7  test    edx, edx
0x18000e1b9  jnz     loc_18000E338
0x18000e1bf  movups  xmm0, xmmword ptr [rcx+18h]
0x18000e1c3  lea     r8d, [rdx+10h]; Size
0x18000e1c7  lea     rdx, [rsp+68h+Buf2]; Buf2
0x18000e1cc  lea     rcx, Buf1; Buf1
0x18000e1d3  movdqu  [rsp+68h+Buf2], xmm0
0x18000e1d9  call    memcmp_0
0x18000e1de  test    eax, eax
0x18000e1e0  jnz     loc_18000E338
0x18000e1e6  lea     r14d, [rax+1]
0x18000e1ea  cmp     [rdi+28h], r14w
0x18000e1ef  jnz     loc_18000E338
0x18000e1f5  mov     rcx, cs:?sm_pAllocCacheHandler@HTTP_LOG_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * HTTP_LOG_CONTEXT::sm_pAllocCacheHandler
0x18000e1fc  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000e202  mov     [rsp+68h+arg_0], rax
0x18000e207  mov     rbx, rax
0x18000e20a  test    rax, rax
0x18000e20d  jz      loc_18000E338
0x18000e213  lea     rax, ??_7HTTP_LOG_CONTEXT@@6B@; const HTTP_LOG_CONTEXT::`vftable'
0x18000e21a  xor     edx, edx; Val
0x18000e21c  mov     [rbx], rax
0x18000e21f  lea     rcx, [rbx+338h]; void *
0x18000e226  mov     [rbx+8], r14d
0x18000e22a  lea     rax, [rbx+130h]
0x18000e231  mov     byte ptr [rax], 0
0x18000e234  lea     r8d, [r14+61h]; Size
0x18000e238  mov     [rbx+120h], rax
0x18000e23f  mov     dword ptr [rbx+128h], 200h
0x18000e249  mov     word ptr [rbx+12Ch], 100h
0x18000e252  mov     qword ptr [rbx+330h], 0
0x18000e25d  mov     dword ptr [rbx+49Ch], 0
0x18000e267  mov     qword ptr [rbx+4A0h], 0
0x18000e272  mov     dword ptr [rbx+4A8h], 0
0x18000e27c  call    memset_0
0x18000e281  lea     rcx, [rbx+39Ah]; void *
0x18000e288  xor     edx, edx; Val
0x18000e28a  mov     r8d, 100h; Size
0x18000e290  call    memset_0
0x18000e295  test    rbx, rbx
0x18000e298  jz      loc_18000E338
0x18000e29e  movzx   esi, word ptr [rdi+56h]
0x18000e2a2  lea     rcx, [rbx+100h]
0x18000e2a9  mov     rdi, [rdi+60h]
0x18000e2ad  mov     edx, esi
0x18000e2af  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000e2b5  test    al, al
0x18000e2b7  jz      short loc_18000E329
0x18000e2b9  mov     edx, [rbx+128h]; DestinationSize
0x18000e2bf  mov     r9d, esi; SourceSize
0x18000e2c2  mov     rcx, [rbx+120h]; Destination
0x18000e2c9  mov     r8, rdi; Source
0x18000e2cc  call    cs:__imp_memcpy_s
0x18000e2d2  mov     rcx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000e2d9  mov     r8d, r14d; unsigned __int64
0x18000e2dc  add     rcx, 630h; this
0x18000e2e3  mov     rdx, rbx; struct MULTI_WORK_DISPATCH *
0x18000e2e6  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x18000e2eb  test    eax, eax
0x18000e2ed  jns     short loc_18000E338
0x18000e2ef  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000e2f6  jz      short loc_18000E329
0x18000e2f8  lea     rcx, aCouldnTQueueHt_1; "Couldn't queue HttpLogContextProcessETW"...
0x18000e2ff  mov     r8d, 3C5h
0x18000e305  mov     [rsp+68h+var_40], rcx
0x18000e30a  lea     r9, aHttpLogEventHa_3; "HTTP_LOG_EVENT_HANDLER::EvtRecCallback"
0x18000e311  mov     rcx, cs:g_pDebug
0x18000e318  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000e31f  mov     [rsp+68h+var_48], eax
0x18000e323  call    cs:__imp_PuDbgPrintError
0x18000e329  mov     rax, [rbx]
0x18000e32c  mov     rcx, rbx
0x18000e32f  mov     rax, [rax+8]
0x18000e333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e338  add     rsp, 48h
0x18000e33c  pop     r14
0x18000e33e  pop     rdi
0x18000e33f  pop     rsi
0x18000e340  pop     rbx
0x18000e341  retn
```
