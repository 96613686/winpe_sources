# RegistryMonitor::~RegistryMonitor(void)

- ea: `0x1800d2950`
- end: `0x1800d299c`
- name: `??1RegistryMonitor@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(RegistryMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800c19d8`

## callees

- `0x180017b98`
- `0x18003420c`
- `0x1800d2950`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800d2967`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800d2967`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800d2980`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800d2980`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800d2976`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800d2976`

## pseudocode

```c
void __fastcall RegistryMonitor::~RegistryMonitor(RegistryMonitor *this)
{
  struct _TP_WAIT *v2; // rcx

  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    SetThreadpoolWait(v2, 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 4), 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 4));
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 8);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(this);
}

```

## disassembly

```asm
0x1800d2950  push    rbx
0x1800d2952  sub     rsp, 20h
0x1800d2956  mov     rbx, rcx
0x1800d2959  mov     rcx, [rcx+20h]; pwa
0x1800d295d  test    rcx, rcx
0x1800d2960  jz      short loc_1800D2986
0x1800d2962  xor     r8d, r8d; pftTimeout
0x1800d2965  xor     edx, edx; h
0x1800d2967  call    cs:__imp_SetThreadpoolWait
0x1800d296d  mov     rcx, [rbx+20h]; pwa
0x1800d2971  mov     edx, 1; fCancelPendingCallbacks
0x1800d2976  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800d297c  mov     rcx, [rbx+20h]; pwa
0x1800d2980  call    cs:__imp_CloseThreadpoolWait
0x1800d2986  lea     rcx, [rbx+8]
0x1800d298a  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800d298f  mov     rcx, rbx
0x1800d2992  add     rsp, 20h
0x1800d2996  pop     rbx
0x1800d2997  jmp     ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
```
