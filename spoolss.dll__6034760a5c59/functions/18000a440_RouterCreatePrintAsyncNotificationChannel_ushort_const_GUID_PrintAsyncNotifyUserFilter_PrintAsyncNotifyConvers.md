# RouterCreatePrintAsyncNotificationChannel(ushort const *,_GUID *,PrintAsyncNotifyUserFilter,PrintAsyncNotifyConversationStyle,IPrintAsyncNotifyCallback *,IPrintAsyncNotifyChannel * *)

- ea: `0x18000a440`
- end: `0x18000a557`
- name: `?RouterCreatePrintAsyncNotificationChannel@@YAJPEBGPEAU_GUID@@W4PrintAsyncNotifyUserFilter@@W4PrintAsyncNotifyConversationStyle@@PEAUIPrintAsyncNotifyCallback@@PEAPEAUIPrintAsyncNotifyChannel@@@Z`
- size: `279`
- prototype: `HRESULT __stdcall(PCWSTR pName, PrintAsyncNotificationType *pNotificationType, PrintAsyncNotifyUserFilter eNotifyFilter, PrintAsyncNotifyConversationStyle eConversationStyle, IPrintAsyncNotifyCallback *pCallback, IPrintAsyncNotifyChannel **ppIAsynchNotification)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180001cd0`
- `0x180001e00`
- `0x18000a440`
- `0x18000a610`
- `0x180011050`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18000a52d`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18000a52d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a522`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a522`

## string_xrefs

- `0x18000a51b`: `ImpersonatePrinterClient failed!\n`

## pseudocode

```c
HRESULT __stdcall RouterCreatePrintAsyncNotificationChannel(
        PCWSTR pName,
        PrintAsyncNotificationType *pNotificationType,
        PrintAsyncNotifyUserFilter eNotifyFilter,
        PrintAsyncNotifyConversationStyle eConversationStyle,
        IPrintAsyncNotifyCallback *pCallback,
        IPrintAsyncNotifyChannel **ppIAsynchNotification)
{
  HANDLE v11; // rax
  void *v12; // rbx
  int PrintClassObject; // edi
  unsigned int v14; // [rsp+40h] [rbp-38h] BYREF
  void *ppv; // [rsp+48h] [rbp-30h] BYREF

  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(PCWSTR, PrintAsyncNotificationType *))g_pSpoolSvForwards + 184))(
             pName,
             pNotificationType);
  v14 = 0;
  GetIdOfCurrentlyPrintingJob(pName, &v14);
  v11 = RevertToPrinterSelf();
  ppv = 0;
  v12 = v11;
  PrintClassObject = RouterGetPrintClassObject(pName, &IID_IPrintAsyncNotify, &ppv);
  if ( PrintClassObject >= 0 )
    PrintClassObject = (*(__int64 (__fastcall **)(void *, _QWORD, PrintAsyncNotificationType *, _QWORD, PrintAsyncNotifyConversationStyle, IPrintAsyncNotifyCallback *, IPrintAsyncNotifyChannel **))(*(_QWORD *)ppv + 24LL))(
                         ppv,
                         v14,
                         pNotificationType,
                         (unsigned int)eNotifyFilter,
                         eConversationStyle,
                         pCallback,
                         ppIAsynchNotification);
  if ( v12 && !ImpersonatePrinterClient(v12) )
  {
    OutputDebugStringW(L"ImpersonatePrinterClient failed!\n");
    ExitProcess(1u);
  }
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  return PrintClassObject;
}

```

## disassembly

```asm
0x18000a440  push    rbx
0x18000a442  push    rbp
0x18000a443  push    rsi
0x18000a444  push    rdi
0x18000a445  push    r14
0x18000a447  sub     rsp, 50h
0x18000a44b  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000a452  mov     esi, r9d
0x18000a455  mov     ebp, r8d
0x18000a458  mov     r14, rdx
0x18000a45b  mov     rdi, rcx
0x18000a45e  jnz     short loc_18000A492
0x18000a460  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000a467  mov     r10, [rsp+78h+ppIAsynchNotification]
0x18000a46f  mov     [rsp+78h+var_50], r10
0x18000a474  mov     r10, [rsp+78h+pCallback]
0x18000a47c  mov     rax, [rax+5C0h]
0x18000a483  mov     [rsp+78h+var_58], r10
0x18000a488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a48d  jmp     loc_18000A54C
0x18000a492  lea     rdx, [rsp+78h+var_38]; unsigned int *
0x18000a497  mov     [rsp+78h+var_38], 0
0x18000a49f  call    ?GetIdOfCurrentlyPrintingJob@@YAJPEBGPEAK@Z; GetIdOfCurrentlyPrintingJob(ushort const *,ulong *)
0x18000a4a4  call    RevertToPrinterSelf
0x18000a4a9  lea     r8, [rsp+78h+ppv]; ppv
0x18000a4ae  mov     [rsp+78h+ppv], 0
0x18000a4b7  lea     rdx, IID_IPrintAsyncNotify; riid
0x18000a4be  mov     rcx, rdi; pPrinter
0x18000a4c1  mov     rbx, rax
0x18000a4c4  call    ?RouterGetPrintClassObject@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; RouterGetPrintClassObject(ushort const *,_GUID const &,void * *)
0x18000a4c9  mov     edi, eax
0x18000a4cb  test    eax, eax
0x18000a4cd  js      short loc_18000A50A
0x18000a4cf  mov     rcx, [rsp+78h+ppv]
0x18000a4d4  mov     r9d, ebp
0x18000a4d7  mov     r8, r14
0x18000a4da  mov     rdx, [rcx]
0x18000a4dd  mov     rax, [rdx+18h]
0x18000a4e1  mov     rdx, [rsp+78h+ppIAsynchNotification]
0x18000a4e9  mov     [rsp+78h+var_48], rdx
0x18000a4ee  mov     rdx, [rsp+78h+pCallback]
0x18000a4f6  mov     [rsp+78h+var_50], rdx
0x18000a4fb  mov     edx, [rsp+78h+var_38]
0x18000a4ff  mov     dword ptr [rsp+78h+var_58], esi
0x18000a503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a508  mov     edi, eax
0x18000a50a  test    rbx, rbx
0x18000a50d  jz      short loc_18000A534
0x18000a50f  mov     rcx, rbx; hToken
0x18000a512  call    ImpersonatePrinterClient
0x18000a517  test    eax, eax
0x18000a519  jnz     short loc_18000A534
0x18000a51b  lea     rcx, aImpersonatepri_0; "ImpersonatePrinterClient failed!\n"
0x18000a522  call    cs:__imp_OutputDebugStringW
0x18000a528  mov     ecx, 1; uExitCode
0x18000a52d  call    cs:__imp_ExitProcess
0x18000a534  mov     rcx, [rsp+78h+ppv]
0x18000a539  test    rcx, rcx
0x18000a53c  jz      short loc_18000A54A
0x18000a53e  mov     rax, [rcx]
0x18000a541  mov     rax, [rax+10h]
0x18000a545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a54a  mov     eax, edi
0x18000a54c  add     rsp, 50h
0x18000a550  pop     r14
0x18000a552  pop     rdi
0x18000a553  pop     rsi
0x18000a554  pop     rbp
0x18000a555  pop     rbx
0x18000a556  retn
```
