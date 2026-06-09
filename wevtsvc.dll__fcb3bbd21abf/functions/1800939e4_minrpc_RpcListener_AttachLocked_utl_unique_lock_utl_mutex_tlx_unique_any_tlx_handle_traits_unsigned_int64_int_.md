# minrpc::RpcListener::AttachLocked(utl::unique_lock<utl::mutex> &,tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>> &&,bool)

- ea: `0x1800939e4`
- end: `0x180093a90`
- name: `?AttachLocked@RpcListener@minrpc@@QEAA_NAEAV?$unique_lock@Vmutex@utl@@@utl@@$$QEAV?$unique_any@U?$handle_traits@_KP6AH_K@Z$1?closesocket@@YAH0@Z$0?0@tlx@@@tlx@@_N@Z`
- size: `172`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180098ffc`

## callees

- `0x1800939e4`
- `0x180093a98`
- `0x180098dfc`
- `0x1800d2ad8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x180093a25`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x180093a25`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180093a38`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180093a38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093a45`

## string_xrefs

- `0x180093a57`: `Attach[CreateThreadpoolIo]`

## pseudocode

```c
char __fastcall minrpc::RpcListener::AttachLocked(char *pv, __int64 a2, __int64 a3)
{
  char v3; // si
  bool v6; // zf
  PTP_IO ThreadpoolIo; // rax
  struct _TP_IO *v8; // rcx
  signed int LastError; // eax

  v3 = pv[48];
  v6 = v3 == 0;
  if ( !v3 )
  {
    pv[48] = 2;
    tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),-1>>::operator=(
      pv + 24,
      a3);
    ThreadpoolIo = CreateThreadpoolIo(*((HANDLE *)pv + 3), minrpc::RpcListener::IoCompletionCallbackStatic, pv, 0);
    v8 = (struct _TP_IO *)*((_QWORD *)pv + 2);
    *((_QWORD *)pv + 2) = ThreadpoolIo;
    if ( v8 )
      CloseThreadpoolIo(v8);
    if ( *((_QWORD *)pv + 2) )
    {
      pv[48] = 4;
      minrpc::RpcListener::StartAccept(pv, a2);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      minrpc::RpcListener::StopLocked(pv, a2, (unsigned int)LastError, "Attach[CreateThreadpoolIo]");
    }
    return 1;
  }
  return v6;
}

```

## disassembly

```asm
0x1800939e4  push    rbx
0x1800939e6  push    rbp
0x1800939e7  push    rsi
0x1800939e8  push    rdi
0x1800939e9  sub     rsp, 28h
0x1800939ed  mov     sil, [rcx+30h]
0x1800939f1  mov     rbp, rdx
0x1800939f4  mov     rdi, rcx
0x1800939f7  test    sil, sil
0x1800939fa  jnz     loc_180093A84
0x180093a00  mov     eax, 2
0x180093a05  mov     rdx, r8
0x180093a08  xchg    al, [rcx+30h]
0x180093a0b  add     rcx, 18h
0x180093a0f  call    ??4?$unique_any@U?$handle_traits@_KP6AH_K@Z$1?closesocket@@YAH0@Z$0?0@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>>::operator=(tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>> &&)
0x180093a14  mov     rcx, [rdi+18h]; fl
0x180093a18  lea     rdx, ?IoCompletionCallbackStatic@RpcListener@minrpc@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x180093a1f  xor     r9d, r9d; pcbe
0x180093a22  mov     r8, rdi; pv
0x180093a25  call    cs:__imp_CreateThreadpoolIo
0x180093a2b  mov     rcx, [rdi+10h]; pio
0x180093a2f  mov     [rdi+10h], rax
0x180093a33  test    rcx, rcx
0x180093a36  jz      short loc_180093A3E
0x180093a38  call    cs:__imp_CloseThreadpoolIo
0x180093a3e  cmp     qword ptr [rdi+10h], 0
0x180093a43  jnz     short loc_180093A6E
0x180093a45  call    cs:__imp_GetLastError
0x180093a4b  test    eax, eax
0x180093a4d  jle     short loc_180093A57
0x180093a4f  movzx   eax, ax
0x180093a52  or      eax, 80070000h
0x180093a57  lea     r9, aAttachCreateth; "Attach[CreateThreadpoolIo]"
0x180093a5e  mov     r8d, eax
0x180093a61  mov     rdx, rbp
0x180093a64  mov     rcx, rdi
0x180093a67  call    ?StopLocked@RpcListener@minrpc@@QEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@JPEBD@Z; minrpc::RpcListener::StopLocked(utl::unique_lock<utl::mutex> &,long,char const *)
0x180093a6c  jmp     short loc_180093A81
0x180093a6e  mov     eax, 4
0x180093a73  mov     rdx, rbp
0x180093a76  xchg    al, [rdi+30h]
0x180093a79  mov     rcx, rdi
0x180093a7c  call    ?StartAccept@RpcListener@minrpc@@AEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@@Z; minrpc::RpcListener::StartAccept(utl::unique_lock<utl::mutex> &)
0x180093a81  test    sil, sil
0x180093a84  setz    al
0x180093a87  add     rsp, 28h
0x180093a8b  pop     rdi
0x180093a8c  pop     rsi
0x180093a8d  pop     rbp
0x180093a8e  pop     rbx
0x180093a8f  retn
```
