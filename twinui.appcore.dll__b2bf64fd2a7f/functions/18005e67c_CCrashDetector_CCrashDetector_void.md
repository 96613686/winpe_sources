# CCrashDetector::~CCrashDetector(void)

- ea: `0x18005e67c`
- end: `0x18005e6df`
- name: `??1CCrashDetector@@QEAA@XZ`
- size: `99`
- prototype: `void __fastcall(CCrashDetector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005f4e0`

## callees

- `0x18005e67c`
- `0x18005f518`
- `0x18005f54c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005e6ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005e6ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005e6a3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005e6a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005e697`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005e697`

## pseudocode

```c
void __fastcall CCrashDetector::~CCrashDetector(CCrashDetector *this)
{
  struct _TP_WAIT *v2; // rcx

  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    SetThreadpoolWait(v2, 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 2), 0);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 2));
    *((_QWORD *)this + 2) = 0;
    CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release((char *)this + 8);
  }
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release((char *)this + 8);
  CTSmartObj<CCrashDetector::CHandler *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(this);
}

```

## disassembly

```asm
0x18005e67c  mov     [rsp+arg_0], rbx
0x18005e681  push    rdi
0x18005e682  sub     rsp, 20h
0x18005e686  mov     rdi, rcx
0x18005e689  mov     rcx, [rcx+10h]; pwa
0x18005e68d  test    rcx, rcx
0x18005e690  jz      short loc_18005E6C4
0x18005e692  xor     r8d, r8d; pftTimeout
0x18005e695  xor     edx, edx; h
0x18005e697  call    cs:__imp_SetThreadpoolWait
0x18005e69d  mov     rcx, [rdi+10h]; pwa
0x18005e6a1  xor     edx, edx; fCancelPendingCallbacks
0x18005e6a3  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005e6a9  mov     rcx, [rdi+10h]; pwa
0x18005e6ad  call    cs:__imp_CloseThreadpoolWait
0x18005e6b3  lea     rcx, [rdi+8]
0x18005e6b7  mov     qword ptr [rdi+10h], 0
0x18005e6bf  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18005e6c4  lea     rcx, [rdi+8]
0x18005e6c8  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18005e6cd  mov     rcx, rdi
0x18005e6d0  mov     rbx, [rsp+28h+arg_0]
0x18005e6d5  add     rsp, 20h
0x18005e6d9  pop     rdi
0x18005e6da  jmp     ?Release@?$CTSmartObj@PEAVCHandler@CCrashDetector@@V?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyNewMem@@@@@@QEAAXXZ; CTSmartObj<CCrashDetector::CHandler *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(void)
```
