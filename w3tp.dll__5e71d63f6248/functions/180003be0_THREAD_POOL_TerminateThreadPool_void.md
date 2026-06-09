# THREAD_POOL::TerminateThreadPool(void)

- ea: `0x180003be0`
- end: `0x180003c7b`
- name: `?TerminateThreadPool@THREAD_POOL@@QEAAXXZ`
- size: `155`
- prototype: `void __fastcall(THREAD_POOL *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800037c0`
- `0x180003ef0`

## callees

- `0x180003418`
- `0x180003768`
- `0x180003be0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c5c`
- `iisutil!PuDbgPrint` at `0x180003c19`
- `iisutil!PuDbgPrint` at `0x180003c19`

## string_xrefs

- `0x180003bf9`: `W3TP: Cleaning up thread pool.\n`
- `0x180003c00`: `THREAD_POOL::TerminateThreadPool`
- `0x180003c12`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_pool.cxx`

## pseudocode

```c
void __fastcall THREAD_POOL::TerminateThreadPool(void **this, void (*a2)(void *))
{
  _DWORD *v3; // rax
  THREAD_MANAGER *v4; // rcx
  void *v5; // rcx

  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_pool.cxx",
      671,
      "THREAD_POOL::TerminateThreadPool",
      "W3TP: Cleaning up thread pool.\n");
  v3 = *this;
  if ( *this && !v3[7] )
  {
    v3[7] = 1;
    v4 = (THREAD_MANAGER *)*((_QWORD *)*this + 4);
    if ( v4 )
    {
      THREAD_MANAGER::TerminateThreadManager(v4, a2, *this);
      *((_QWORD *)*this + 4) = 0;
    }
    v5 = (void *)*((_QWORD *)*this + 1);
    if ( v5 )
    {
      CloseHandle(v5);
      *((_QWORD *)*this + 1) = 0;
    }
    THREAD_POOL::`scalar deleting destructor'((THREAD_POOL *)this, (unsigned int)a2);
  }
}

```

## disassembly

```asm
0x180003be0  push    rbx
0x180003be2  sub     rsp, 30h
0x180003be6  test    cs:g_dwDebugFlags, 3
0x180003bed  mov     rbx, rcx
0x180003bf0  jz      short loc_180003C1F
0x180003bf2  mov     rcx, cs:g_pDebug
0x180003bf9  lea     rax, aW3tpCleaningUp; "W3TP: Cleaning up thread pool.\n"
0x180003c00  lea     r9, aThreadPoolTerm; "THREAD_POOL::TerminateThreadPool"
0x180003c07  mov     [rsp+38h+var_18], rax
0x180003c0c  mov     r8d, 29Fh
0x180003c12  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003c19  call    cs:__imp_PuDbgPrint
0x180003c1f  mov     rax, [rbx]
0x180003c22  test    rax, rax
0x180003c25  jz      short loc_180003C75
0x180003c27  cmp     dword ptr [rax+1Ch], 0
0x180003c2b  jnz     short loc_180003C75
0x180003c2d  mov     dword ptr [rax+1Ch], 1
0x180003c34  mov     r8, [rbx]; void *
0x180003c37  mov     rcx, [r8+20h]; this
0x180003c3b  test    rcx, rcx
0x180003c3e  jz      short loc_180003C50
0x180003c40  call    ?TerminateThreadManager@THREAD_MANAGER@@QEAAXP6AXPEAX@Z0@Z; THREAD_MANAGER::TerminateThreadManager(void (*)(void *),void *)
0x180003c45  mov     rax, [rbx]
0x180003c48  mov     qword ptr [rax+20h], 0
0x180003c50  mov     rax, [rbx]
0x180003c53  mov     rcx, [rax+8]; hObject
0x180003c57  test    rcx, rcx
0x180003c5a  jz      short loc_180003C6D
0x180003c5c  call    cs:__imp_CloseHandle
0x180003c62  mov     rax, [rbx]
0x180003c65  mov     qword ptr [rax+8], 0
0x180003c6d  mov     rcx, rbx; this
0x180003c70  call    ??_GTHREAD_POOL@@AEAAPEAXI@Z; THREAD_POOL::`scalar deleting destructor'(uint)
0x180003c75  add     rsp, 30h
0x180003c79  pop     rbx
0x180003c7a  retn
```
