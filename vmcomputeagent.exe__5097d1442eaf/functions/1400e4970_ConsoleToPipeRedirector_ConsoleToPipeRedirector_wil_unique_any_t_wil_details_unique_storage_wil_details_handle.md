# ConsoleToPipeRedirector::ConsoleToPipeRedirector(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,ushort,ushort,ushort,ushort)

- ea: `0x1400e4970`
- end: `0x1400e4b82`
- name: `??0ConsoleToPipeRedirector@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@00GGGG@Z`
- size: `530`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, __int16, __int16, __int16, __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400e0b10`

## callees

- `0x14000ddac`
- `0x140044adc`
- `0x1400e4970`
- `0x1400e8290`
- `0x1400e8464`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e4a32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e4aa0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e4ada`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e4a32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e4aa0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e4ada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e4a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e4a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e4ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e4a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e4a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e4ac8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400e4a81`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400e4a81`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400e4a98`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400e4a98`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400e4a5c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400e4a5c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1400e4a0d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1400e4a0d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1400e4a2a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1400e4a2a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400e4a8f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400e4a8f`

## string_xrefs

- `0x1400e4b4c`: `onecore\vm\compute\service\cexec\lib\consoletostream.cpp`
- `0x1400e4b5e`: `onecore\vm\compute\service\cexec\lib\consoletostream.cpp`
- `0x1400e4b70`: `onecore\vm\compute\service\cexec\lib\consoletostream.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char *__fastcall ConsoleToPipeRedirector::ConsoleToPipeRedirector(
        char *pv,
        __int64 *a2,
        _QWORD *a3,
        _QWORD *a4,
        __int16 a5,
        __int16 a6,
        __int16 a7,
        unsigned __int16 a8)
{
  char *v10; // rcx
  PTP_IO ThreadpoolIo; // rsi
  const char *v12; // r9
  struct _TP_IO *v13; // rbp
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rbp
  const char *v16; // r9
  struct _TP_TIMER *v17; // rsi
  DWORD v18; // ebx
  __int64 v19; // rbp
  void *v20; // rsi
  DWORD v21; // ebx
  int Console; // eax
  int v24; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_QWORD *)pv = 0;
  *((_WORD *)pv + 4) = 0;
  *((_DWORD *)pv + 3) = 0;
  *((_QWORD *)pv + 2) = 0;
  *((_DWORD *)pv + 6) = 0;
  *((_QWORD *)pv + 4) = 0;
  *((_QWORD *)pv + 5) = 0;
  *((_QWORD *)pv + 6) = *a3;
  *a3 = -1;
  *((_QWORD *)pv + 7) = *a4;
  *a4 = -1;
  *((_QWORD *)pv + 8) = 0;
  *((_QWORD *)pv + 9) = 0;
  *((_QWORD *)pv + 10) = 0;
  *(_OWORD *)(pv + 344) = 0;
  *(_OWORD *)(pv + 360) = 0;
  pv[376] = 0;
  v10 = (char *)*((_QWORD *)pv + 6);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    ThreadpoolIo = CreateThreadpoolIo(v10, ConsoleToPipeRedirector::ReadCompleteCallback, pv, 0);
    v13 = (struct _TP_IO *)*((_QWORD *)pv + 8);
    if ( v13 )
    {
      LastError = GetLastError();
      CloseThreadpoolIo(v13);
      SetLastError(LastError);
    }
    *((_QWORD *)pv + 8) = ThreadpoolIo;
    if ( !ThreadpoolIo )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\consoletostream.cpp",
        v12);
    ThreadpoolTimer = CreateThreadpoolTimer(lambda_1f9302160d04f2df91acab1b083512b3_::_lambda_invoker_cdecl_, pv, 0);
    v17 = (struct _TP_TIMER *)*((_QWORD *)pv + 9);
    if ( v17 )
    {
      v18 = GetLastError();
      SetThreadpoolTimer(v17, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v17, 1);
      CloseThreadpoolTimer(v17);
      SetLastError(v18);
    }
    *((_QWORD *)pv + 9) = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\consoletostream.cpp",
        v16);
  }
  v19 = *a2;
  v20 = *(void **)pv;
  if ( *(_QWORD *)pv )
  {
    v21 = GetLastError();
    CsCloseConsole(v20);
    SetLastError(v21);
  }
  *(_QWORD *)pv = 0;
  LOWORD(v24) = a7;
  Console = CsCreateConsole(pv, v19, pv, a8);
  if ( Console < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\consoletostream.cpp",
      (const char *)(unsigned int)Console,
      v24);
  *a2 = -1;
  pv[376] = 1;
  return pv;
}

```

## disassembly

```asm
0x1400e4970  mov     [rsp+arg_0], rcx
0x1400e4975  push    rbx
0x1400e4976  push    rbp
0x1400e4977  push    rsi
0x1400e4978  push    rdi
0x1400e4979  push    r12
0x1400e497b  push    r14
0x1400e497d  sub     rsp, 48h
0x1400e4981  mov     r14, rdx
0x1400e4984  mov     rdi, rcx
0x1400e4987  mov     qword ptr [rcx], 0
0x1400e498e  xor     eax, eax
0x1400e4990  mov     [rcx+8], ax
0x1400e4994  mov     [rcx+0Ch], eax
0x1400e4997  mov     [rcx+10h], rax
0x1400e499b  mov     [rcx+18h], eax
0x1400e499e  mov     [rcx+20h], rax
0x1400e49a2  mov     [rcx+28h], rax
0x1400e49a6  mov     rax, [r8]
0x1400e49a9  mov     [rcx+30h], rax
0x1400e49ad  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400e49b1  mov     [r8], r12
0x1400e49b4  mov     rax, [r9]
0x1400e49b7  mov     [rcx+38h], rax
0x1400e49bb  mov     [r9], r12
0x1400e49be  mov     qword ptr [rcx+40h], 0
0x1400e49c6  mov     qword ptr [rcx+48h], 0
0x1400e49ce  mov     qword ptr [rcx+50h], 0
0x1400e49d6  xorps   xmm0, xmm0
0x1400e49d9  movups  xmmword ptr [rcx+158h], xmm0
0x1400e49e0  movups  xmmword ptr [rcx+168h], xmm0
0x1400e49e7  mov     byte ptr [rcx+178h], 0
0x1400e49ee  mov     rcx, [rcx+30h]; fl
0x1400e49f2  lea     rax, [rcx-1]
0x1400e49f6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e49fa  ja      loc_1400E4ABD
0x1400e4a00  xor     r9d, r9d; pcbe
0x1400e4a03  mov     r8, rdi; pv
0x1400e4a06  lea     rdx, ?ReadCompleteCallback@ConsoleToPipeRedirector@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1400e4a0d  call    cs:__imp_CreateThreadpoolIo
0x1400e4a13  mov     rsi, rax
0x1400e4a16  mov     rbp, [rdi+40h]
0x1400e4a1a  test    rbp, rbp
0x1400e4a1d  jz      short loc_1400E4A38
0x1400e4a1f  call    cs:__imp_GetLastError
0x1400e4a25  mov     ebx, eax
0x1400e4a27  mov     rcx, rbp; pio
0x1400e4a2a  call    cs:__imp_CloseThreadpoolIo
0x1400e4a30  mov     ecx, ebx; dwErrCode
0x1400e4a32  call    cs:__imp_SetLastError
0x1400e4a38  mov     [rdi+40h], rsi
0x1400e4a3c  test    rsi, rsi
0x1400e4a3f  setz    al
0x1400e4a42  mov     rcx, [rsp+78h]; this
0x1400e4a47  test    al, al
0x1400e4a49  jnz     loc_1400E4B5E
0x1400e4a4f  xor     r8d, r8d; pcbe
0x1400e4a52  mov     rdx, rdi; pv
0x1400e4a55  lea     rcx, _lambda_1f9302160d04f2df91acab1b083512b3____lambda_invoker_cdecl_; pfnti
0x1400e4a5c  call    cs:__imp_CreateThreadpoolTimer
0x1400e4a62  mov     rbp, rax
0x1400e4a65  mov     rsi, [rdi+48h]
0x1400e4a69  test    rsi, rsi
0x1400e4a6c  jz      short loc_1400E4AA6
0x1400e4a6e  call    cs:__imp_GetLastError
0x1400e4a74  mov     ebx, eax
0x1400e4a76  xor     r9d, r9d; msWindowLength
0x1400e4a79  xor     r8d, r8d; msPeriod
0x1400e4a7c  xor     edx, edx; pftDueTime
0x1400e4a7e  mov     rcx, rsi; pti
0x1400e4a81  call    cs:__imp_SetThreadpoolTimer
0x1400e4a87  mov     edx, 1; fCancelPendingCallbacks
0x1400e4a8c  mov     rcx, rsi; pti
0x1400e4a8f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400e4a95  mov     rcx, rsi; pti
0x1400e4a98  call    cs:__imp_CloseThreadpoolTimer
0x1400e4a9e  mov     ecx, ebx; dwErrCode
0x1400e4aa0  call    cs:__imp_SetLastError
0x1400e4aa6  mov     [rdi+48h], rbp
0x1400e4aaa  test    rbp, rbp
0x1400e4aad  setz    al
0x1400e4ab0  mov     rcx, [rsp+78h]; this
0x1400e4ab5  test    al, al
0x1400e4ab7  jnz     loc_1400E4B70
0x1400e4abd  mov     rbp, [r14]
0x1400e4ac0  mov     rsi, [rdi]
0x1400e4ac3  test    rsi, rsi
0x1400e4ac6  jz      short loc_1400E4AE1
0x1400e4ac8  call    cs:__imp_GetLastError
0x1400e4ace  mov     ebx, eax
0x1400e4ad0  mov     rcx, rsi; P
0x1400e4ad3  call    CsCloseConsole
0x1400e4ad8  mov     ecx, ebx; dwErrCode
0x1400e4ada  call    cs:__imp_SetLastError
0x1400e4ae0  nop
0x1400e4ae1  mov     qword ptr [rdi], 0
0x1400e4ae8  movzx   eax, [rsp+78h+arg_20]
0x1400e4af0  mov     [rsp+78h+var_48], ax
0x1400e4af5  movzx   eax, [rsp+78h+arg_28]
0x1400e4afd  mov     [rsp+78h+var_50], ax
0x1400e4b02  movzx   eax, [rsp+78h+arg_30]
0x1400e4b0a  mov     word ptr [rsp+78h+var_58], ax; int
0x1400e4b0f  movzx   r9d, [rsp+78h+arg_38]
0x1400e4b18  mov     r8, rdi
0x1400e4b1b  mov     rdx, rbp
0x1400e4b1e  mov     rcx, rdi
0x1400e4b21  call    CsCreateConsole
0x1400e4b26  mov     rcx, [rsp+78h]; this
0x1400e4b2b  test    eax, eax
0x1400e4b2d  js      short loc_1400E4B49
0x1400e4b2f  mov     [r14], r12
0x1400e4b32  mov     byte ptr [rdi+178h], 1
0x1400e4b39  mov     rax, rdi
0x1400e4b3c  add     rsp, 48h
0x1400e4b40  pop     r14
0x1400e4b42  pop     r12
0x1400e4b44  pop     rdi
0x1400e4b45  pop     rsi
0x1400e4b46  pop     rbp
0x1400e4b47  pop     rbx
0x1400e4b48  retn
0x1400e4b49  mov     r9d, eax; char *
0x1400e4b4c  lea     r8, aOnecoreVmCompu_30; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400e4b53  mov     edx, 0AAh; void *
0x1400e4b58  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400e4b5e  lea     r8, aOnecoreVmCompu_30; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400e4b65  mov     edx, 99h; void *
0x1400e4b6a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400e4b70  lea     r8, aOnecoreVmCompu_30; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400e4b77  mov     edx, 0A0h; void *
0x1400e4b7c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
