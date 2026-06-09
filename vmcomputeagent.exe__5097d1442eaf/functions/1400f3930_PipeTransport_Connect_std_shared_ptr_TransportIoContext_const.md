# PipeTransport::Connect(std::shared_ptr<TransportIoContext> const &)

- ea: `0x1400f3930`
- end: `0x1400f3a2b`
- name: `?Connect@PipeTransport@@UEAA_NAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000ddac`
- `0x1400341ac`
- `0x1400f3930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f39cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f39cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f394c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f394c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400f3997`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400f3997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f3984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f3984`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1400f3972`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1400f3972`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1400f398f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1400f398f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x1400f39b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x1400f39b1`

## string_xrefs

- `0x1400f39ea`: `onecore\vm\compute\common\transport\pipetransport.cpp`
- `0x1400f3a07`: `onecore\vm\compute\common\transport\pipetransport.cpp`
- `0x1400f3a19`: `onecore\vm\compute\common\transport\pipetransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall PipeTransport::Connect(RTL_SRWLOCK *pv)
{
  RTL_SRWLOCK *v2; // rsi
  PTP_IO ThreadpoolIo; // rbp
  const char *v4; // r9
  struct _TP_IO *Ptr; // r14
  DWORD LastError; // ebx
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = pv + 4;
  AcquireSRWLockExclusive(pv + 4);
  if ( HIDWORD(pv[5].Ptr) != 3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\pipetransport.cpp",
      (const char *)0x139F,
      (unsigned int)v2);
  ThreadpoolIo = CreateThreadpoolIo(pv[1].Ptr, PipeTransport::IoCompletionCallback, pv, 0);
  Ptr = (struct _TP_IO *)pv[2].Ptr;
  if ( Ptr )
  {
    LastError = GetLastError();
    CloseThreadpoolIo(Ptr);
    SetLastError(LastError);
  }
  pv[2].Ptr = ThreadpoolIo;
  if ( !ThreadpoolIo )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\pipetransport.cpp",
      v4);
  if ( !SetFileCompletionNotificationModes(pv[1].Ptr, 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\pipetransport.cpp",
      v7);
  HIDWORD(pv[5].Ptr) = 4;
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return 1;
}

```

## disassembly

```asm
0x1400f3930  mov     [rsp+arg_8], rbx
0x1400f3935  mov     [rsp+arg_10], rbp
0x1400f393a  push    rsi
0x1400f393b  push    rdi
0x1400f393c  push    r14
0x1400f393e  sub     rsp, 30h
0x1400f3942  mov     rdi, rcx
0x1400f3945  lea     rsi, [rcx+20h]
0x1400f3949  mov     rcx, rsi; SRWLock
0x1400f394c  call    cs:__imp_AcquireSRWLockExclusive
0x1400f3952  mov     qword ptr [rsp+48h+var_28], rsi; unsigned int
0x1400f3957  cmp     dword ptr [rdi+2Ch], 3
0x1400f395b  jnz     loc_1400F39FC
0x1400f3961  xor     r9d, r9d; pcbe
0x1400f3964  mov     r8, rdi; pv
0x1400f3967  lea     rdx, ?IoCompletionCallback@PipeTransport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1400f396e  mov     rcx, [rdi+8]; fl
0x1400f3972  call    cs:__imp_CreateThreadpoolIo
0x1400f3978  mov     rbp, rax
0x1400f397b  mov     r14, [rdi+10h]
0x1400f397f  test    r14, r14
0x1400f3982  jz      short loc_1400F399D
0x1400f3984  call    cs:__imp_GetLastError
0x1400f398a  mov     ebx, eax
0x1400f398c  mov     rcx, r14; pio
0x1400f398f  call    cs:__imp_CloseThreadpoolIo
0x1400f3995  mov     ecx, ebx; dwErrCode
0x1400f3997  call    cs:__imp_SetLastError
0x1400f399d  mov     [rdi+10h], rbp
0x1400f39a1  mov     rcx, [rsp+48h]; this
0x1400f39a6  test    rbp, rbp
0x1400f39a9  jz      short loc_1400F3A19
0x1400f39ab  mov     dl, 1; Flags
0x1400f39ad  mov     rcx, [rdi+8]; FileHandle
0x1400f39b1  call    cs:__imp_SetFileCompletionNotificationModes
0x1400f39b7  mov     rcx, [rsp+48h]; this
0x1400f39bc  test    eax, eax
0x1400f39be  jz      short loc_1400F39EA
0x1400f39c0  mov     dword ptr [rdi+2Ch], 4
0x1400f39c7  test    rsi, rsi
0x1400f39ca  jz      short loc_1400F39D5
0x1400f39cc  mov     rcx, rsi; SRWLock
0x1400f39cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f39d5  mov     al, 1
0x1400f39d7  mov     rbx, [rsp+48h+arg_8]
0x1400f39dc  mov     rbp, [rsp+48h+arg_10]
0x1400f39e1  add     rsp, 30h
0x1400f39e5  pop     r14
0x1400f39e7  pop     rdi
0x1400f39e8  pop     rsi
0x1400f39e9  retn
0x1400f39ea  lea     r8, aOnecoreVmCompu_38; "onecore\\vm\\compute\\common\\transport"...
0x1400f39f1  mov     edx, 0CBh; void *
0x1400f39f6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400f39fc  mov     rcx, [rsp+48h]; this
0x1400f3a01  mov     r9d, 139Fh; char *
0x1400f3a07  lea     r8, aOnecoreVmCompu_38; "onecore\\vm\\compute\\common\\transport"...
0x1400f3a0e  mov     edx, 0BBh; void *
0x1400f3a13  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400f3a19  lea     r8, aOnecoreVmCompu_38; "onecore\\vm\\compute\\common\\transport"...
0x1400f3a20  mov     edx, 0C7h; void *
0x1400f3a25  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
