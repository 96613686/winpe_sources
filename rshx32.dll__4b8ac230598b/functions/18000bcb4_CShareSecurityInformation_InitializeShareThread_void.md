# CShareSecurityInformation::InitializeShareThread(void)

- ea: `0x18000bcb4`
- end: `0x18000bd5f`
- name: `?InitializeShareThread@CShareSecurityInformation@@AEAAJXZ`
- size: `171`
- prototype: `__int64 __fastcall(_QWORD *pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b6b4`

## callees

- `0x18000bcb4`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bce0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bce0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd28`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000bd1a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000bd1a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000bcff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000bcff`

## pseudocode

```c
__int64 __fastcall CShareSecurityInformation::InitializeShareThread(_QWORD *pv)
{
  HANDLE EventW; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int LastError; // eax
  unsigned int v6; // edi

  if ( pv )
    (*(void (__fastcall **)(_QWORD *))(*pv + 8LL))(pv);
  EventW = CreateEventW(0, 1, 0, 0);
  pv[29] = EventW;
  if ( EventW
    && (ThreadpoolWork = CreateThreadpoolWork((PTP_WORK_CALLBACK)CShareSecurityInformation::GetShareInfoThread, pv, 0),
        (pv[31] = ThreadpoolWork) != 0) )
  {
    *((_DWORD *)pv + 60) = 1;
    SubmitThreadpoolWork(ThreadpoolWork);
    return *((unsigned int *)pv + 60);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    *((_DWORD *)pv + 60) = v6;
    (*(void (__fastcall **)(_QWORD *))(*pv + 16LL))(pv);
    return v6;
  }
}

```

## disassembly

```asm
0x18000bcb4  mov     [rsp+arg_0], rbx
0x18000bcb9  push    rdi
0x18000bcba  sub     rsp, 20h
0x18000bcbe  mov     rbx, rcx
0x18000bcc1  test    rcx, rcx
0x18000bcc4  jz      short loc_18000BCD2
0x18000bcc6  mov     rax, [rcx]
0x18000bcc9  mov     rax, [rax+8]
0x18000bccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcd2  xor     r9d, r9d; lpName
0x18000bcd5  xor     r8d, r8d; bInitialState
0x18000bcd8  xor     ecx, ecx; lpEventAttributes
0x18000bcda  lea     edi, [r9+1]
0x18000bcde  mov     edx, edi; bManualReset
0x18000bce0  call    cs:__imp_CreateEventW
0x18000bce6  mov     [rbx+0E8h], rax
0x18000bced  test    rax, rax
0x18000bcf0  jz      short loc_18000BD28
0x18000bcf2  xor     r8d, r8d; pcbe
0x18000bcf5  lea     rcx, ?GetShareInfoThread@CShareSecurityInformation@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000bcfc  mov     rdx, rbx; pv
0x18000bcff  call    cs:__imp_CreateThreadpoolWork
0x18000bd05  mov     [rbx+0F8h], rax
0x18000bd0c  test    rax, rax
0x18000bd0f  jz      short loc_18000BD28
0x18000bd11  mov     rcx, rax; pwk
0x18000bd14  mov     [rbx+0F0h], edi
0x18000bd1a  call    cs:__imp_SubmitThreadpoolWork
0x18000bd20  mov     eax, [rbx+0F0h]
0x18000bd26  jmp     short loc_18000BD54
0x18000bd28  call    cs:__imp_GetLastError
0x18000bd2e  mov     edi, eax
0x18000bd30  test    eax, eax
0x18000bd32  jle     short loc_18000BD3D
0x18000bd34  movzx   edi, ax
0x18000bd37  or      edi, 80070000h
0x18000bd3d  mov     [rbx+0F0h], edi
0x18000bd43  mov     rcx, [rbx]
0x18000bd46  mov     rax, [rcx+10h]
0x18000bd4a  mov     rcx, rbx
0x18000bd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd52  mov     eax, edi
0x18000bd54  mov     rbx, [rsp+28h+arg_0]
0x18000bd59  add     rsp, 20h
0x18000bd5d  pop     rdi
0x18000bd5e  retn
```
