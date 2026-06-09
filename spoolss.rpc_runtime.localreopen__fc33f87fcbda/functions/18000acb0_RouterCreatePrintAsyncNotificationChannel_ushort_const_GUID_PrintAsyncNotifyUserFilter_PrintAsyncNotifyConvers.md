# RouterCreatePrintAsyncNotificationChannel(ushort const *,_GUID *,PrintAsyncNotifyUserFilter,PrintAsyncNotifyConversationStyle,IPrintAsyncNotifyCallback *,IPrintAsyncNotifyChannel * *)

- ea: `0x18000acb0`
- end: `0x18000add4`
- name: `?RouterCreatePrintAsyncNotificationChannel@@YAJPEBGPEAU_GUID@@W4PrintAsyncNotifyUserFilter@@W4PrintAsyncNotifyConversationStyle@@PEAUIPrintAsyncNotifyCallback@@PEAPEAUIPrintAsyncNotifyChannel@@@Z`
- size: `292`
- prototype: `HRESULT __stdcall(PCWSTR pName, PrintAsyncNotificationType *pNotificationType, PrintAsyncNotifyUserFilter eNotifyFilter, PrintAsyncNotifyConversationStyle eConversationStyle, IPrintAsyncNotifyCallback *pCallback, IPrintAsyncNotifyChannel **ppIAsynchNotification)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180001d00`
- `0x180001e60`
- `0x18000acb0`
- `0x18000aeb0`
- `0x1800126a0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18000ada3`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18000ada3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ad92`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ad92`

## string_xrefs

- `0x18000ad8b`: `ImpersonatePrinterClient failed!\n`

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
0x18000acb0  push    rbx
0x18000acb2  push    rbp
0x18000acb3  push    rsi
0x18000acb4  push    rdi
0x18000acb5  push    r14
0x18000acb7  sub     rsp, 50h
0x18000acbb  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000acc2  mov     esi, r9d
0x18000acc5  mov     ebp, r8d
0x18000acc8  mov     r14, rdx
0x18000accb  mov     rdi, rcx
0x18000acce  jnz     short loc_18000AD02
0x18000acd0  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000acd7  mov     r10, [rsp+78h+ppIAsynchNotification]
0x18000acdf  mov     [rsp+78h+var_50], r10
0x18000ace4  mov     r10, [rsp+78h+pCallback]
0x18000acec  mov     rax, [rax+5C0h]
0x18000acf3  mov     [rsp+78h+var_58], r10
0x18000acf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acfd  jmp     loc_18000ADC8
0x18000ad02  lea     rdx, [rsp+78h+var_38]; unsigned int *
0x18000ad07  mov     [rsp+78h+var_38], 0
0x18000ad0f  call    ?GetIdOfCurrentlyPrintingJob@@YAJPEBGPEAK@Z; GetIdOfCurrentlyPrintingJob(ushort const *,ulong *)
0x18000ad14  call    RevertToPrinterSelf
0x18000ad19  lea     r8, [rsp+78h+ppv]; ppv
0x18000ad1e  mov     [rsp+78h+ppv], 0
0x18000ad27  lea     rdx, IID_IPrintAsyncNotify; riid
0x18000ad2e  mov     rcx, rdi; pPrinter
0x18000ad31  mov     rbx, rax
0x18000ad34  call    ?RouterGetPrintClassObject@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; RouterGetPrintClassObject(ushort const *,_GUID const &,void * *)
0x18000ad39  mov     edi, eax
0x18000ad3b  test    eax, eax
0x18000ad3d  js      short loc_18000AD7A
0x18000ad3f  mov     rcx, [rsp+78h+ppv]
0x18000ad44  mov     r9d, ebp
0x18000ad47  mov     r8, r14
0x18000ad4a  mov     rdx, [rcx]
0x18000ad4d  mov     rax, [rdx+18h]
0x18000ad51  mov     rdx, [rsp+78h+ppIAsynchNotification]
0x18000ad59  mov     [rsp+78h+var_48], rdx
0x18000ad5e  mov     rdx, [rsp+78h+pCallback]
0x18000ad66  mov     [rsp+78h+var_50], rdx
0x18000ad6b  mov     edx, [rsp+78h+var_38]
0x18000ad6f  mov     dword ptr [rsp+78h+var_58], esi
0x18000ad73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad78  mov     edi, eax
0x18000ad7a  test    rbx, rbx
0x18000ad7d  jz      short loc_18000ADB0
0x18000ad7f  mov     rcx, rbx; hToken
0x18000ad82  call    ImpersonatePrinterClient
0x18000ad87  test    eax, eax
0x18000ad89  jnz     short loc_18000ADB0
0x18000ad8b  lea     rcx, aImpersonatepri_0; "ImpersonatePrinterClient failed!\n"
0x18000ad92  call    cs:__imp_OutputDebugStringW
0x18000ad99  nop     dword ptr [rax+rax+00h]
0x18000ad9e  mov     ecx, 1; uExitCode
0x18000ada3  call    cs:__imp_ExitProcess
0x18000adb0  mov     rcx, [rsp+78h+ppv]
0x18000adb5  test    rcx, rcx
0x18000adb8  jz      short loc_18000ADC6
0x18000adba  mov     rax, [rcx]
0x18000adbd  mov     rax, [rax+10h]
0x18000adc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adc6  mov     eax, edi
0x18000adc8  add     rsp, 50h
0x18000adcc  pop     r14
0x18000adce  pop     rdi
0x18000adcf  pop     rsi
0x18000add0  pop     rbp
0x18000add1  pop     rbx
0x18000add2  retn
```
