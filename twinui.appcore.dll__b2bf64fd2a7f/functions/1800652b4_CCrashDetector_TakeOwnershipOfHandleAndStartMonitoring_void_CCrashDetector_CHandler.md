# CCrashDetector::_TakeOwnershipOfHandleAndStartMonitoring(void *,CCrashDetector::CHandler *)

- ea: `0x1800652b4`
- end: `0x18006537c`
- name: `?_TakeOwnershipOfHandleAndStartMonitoring@CCrashDetector@@AEAAJPEAXPEAVCHandler@1@@Z`
- size: `200`
- prototype: `__int64 __fastcall(PVOID pv, void *, struct CCrashDetector::CHandler *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028754`

## callees

- `0x1800299c8`
- `0x18005f518`
- `0x18005f54c`
- `0x1800652b4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180065353`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180065353`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180065317`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180065317`

## pseudocode

```c
__int64 __fastcall CCrashDetector::_TakeOwnershipOfHandleAndStartMonitoring(
        PTP_WAIT *pv,
        void *a2,
        struct CCrashDetector::CHandler *a3)
{
  int Error; // ebx
  HANDLE *v7; // rsi
  PTP_WAIT ThreadpoolWait; // rax
  struct CCrashDetector::CHandler *v10; // [rsp+48h] [rbp+10h] BYREF
  void *v11; // [rsp+50h] [rbp+18h] BYREF

  v11 = a2;
  v10 = a3;
  if ( !a3 )
  {
LABEL_5:
    Error = -2147024809;
    goto LABEL_10;
  }
  if ( !pv[2] )
  {
    v7 = (HANDLE *)(pv + 1);
    v11 = 0;
    CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(pv + 1);
    *v7 = a2;
    if ( a2 )
    {
      ThreadpoolWait = CreateThreadpoolWait(CCrashDetector::s_ObjectSignaledHandler, pv, 0);
      pv[2] = ThreadpoolWait;
      if ( ThreadpoolWait )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_10;
      }
      v10 = 0;
      CTSmartObj<CCrashDetector::CHandler *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(pv);
      *pv = a3;
      SetThreadpoolWait(pv[2], *v7, 0);
      goto LABEL_10;
    }
    goto LABEL_5;
  }
  Error = -2147418113;
LABEL_10:
  CTSmartObj<CCrashDetector::CHandler *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(&v10);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v11);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800652b4  mov     [rsp+arg_0], rbx
0x1800652b9  push    rbp
0x1800652ba  push    rsi
0x1800652bb  push    rdi
0x1800652bc  sub     rsp, 20h
0x1800652c0  mov     [rsp+38h+arg_10], rdx
0x1800652c5  mov     rbp, r8
0x1800652c8  mov     [rsp+38h+arg_8], r8
0x1800652cd  mov     rbx, rdx
0x1800652d0  mov     rdi, rcx
0x1800652d3  test    r8, r8
0x1800652d6  jz      short loc_180065303
0x1800652d8  cmp     qword ptr [rcx+10h], 0
0x1800652dd  jz      short loc_1800652E6
0x1800652df  mov     ebx, 8000FFFFh
0x1800652e4  jmp     short loc_180065359
0x1800652e6  lea     rsi, [rcx+8]
0x1800652ea  mov     [rsp+38h+arg_10], 0
0x1800652f3  mov     rcx, rsi
0x1800652f6  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x1800652fb  mov     [rsi], rbx
0x1800652fe  test    rbx, rbx
0x180065301  jnz     short loc_18006530A
0x180065303  mov     ebx, 80070057h
0x180065308  jmp     short loc_180065359
0x18006530a  xor     r8d, r8d; pcbe
0x18006530d  lea     rcx, ?s_ObjectSignaledHandler@CCrashDetector@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180065314  mov     rdx, rdi; pv
0x180065317  call    cs:__imp_CreateThreadpoolWait
0x18006531d  mov     [rdi+10h], rax
0x180065321  test    rax, rax
0x180065324  jz      short loc_18006532A
0x180065326  xor     ebx, ebx
0x180065328  jmp     short loc_180065335
0x18006532a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006532f  mov     ebx, eax
0x180065331  test    eax, eax
0x180065333  js      short loc_180065359
0x180065335  mov     rcx, rdi
0x180065338  mov     [rsp+38h+arg_8], 0
0x180065341  call    ?Release@?$CTSmartObj@PEAVCHandler@CCrashDetector@@V?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyNewMem@@@@@@QEAAXXZ; CTSmartObj<CCrashDetector::CHandler *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(void)
0x180065346  mov     [rdi], rbp
0x180065349  xor     r8d, r8d; pftTimeout
0x18006534c  mov     rdx, [rsi]; h
0x18006534f  mov     rcx, [rdi+10h]; pwa
0x180065353  call    cs:__imp_SetThreadpoolWait
0x180065359  lea     rcx, [rsp+38h+arg_8]
0x18006535e  call    ?Release@?$CTSmartObj@PEAVCHandler@CCrashDetector@@V?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyNewMem@@@@@@QEAAXXZ; CTSmartObj<CCrashDetector::CHandler *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(void)
0x180065363  lea     rcx, [rsp+38h+arg_10]
0x180065368  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18006536d  mov     eax, ebx
0x18006536f  mov     rbx, [rsp+38h+arg_0]
0x180065374  add     rsp, 20h
0x180065378  pop     rdi
0x180065379  pop     rsi
0x18006537a  pop     rbp
0x18006537b  retn
```
