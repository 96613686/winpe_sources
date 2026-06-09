# VsIeProviderManagerWorkItemListAdd(void (*)(ulong,void *),void *,ulong (*)(void *),void *)

- ea: `0x180085a24`
- end: `0x180085b06`
- name: `?VsIeProviderManagerWorkItemListAdd@@YAKP6AXKPEAX@Z0P6AK0@Z0@Z`
- size: `226`
- prototype: `unsigned int __fastcall(void (*)(unsigned int, void *), void *, unsigned int (*)(void *), void *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180085764`
- `0x180085930`
- `0x1800d483c`
- `0x1801a939c`
- `0x1801a95f4`

## callees

- `0x18000c5a0`
- `0x18002f450`
- `0x180085a24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180085a99`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180085a99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085aa3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180085a7a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180085a7a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180085aae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180085aae`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180085ac1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180085ac1`

## pseudocode

```c
__int64 __fastcall VsIeProviderManagerWorkItemListAdd(
        void (*a1)(unsigned int, void *),
        void *a2,
        unsigned int (*a3)(void *),
        void *a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  DWORD LastError; // edi
  struct _TP_WORK *ThreadpoolWork; // rsi

  v8 = (_QWORD *)AllocWLMem(0x30u);
  v9 = v8;
  if ( v8 )
  {
    v8[2] = a1;
    v8[3] = a2;
    v8[4] = a3;
    v8[5] = a4;
    if ( !dword_1802A3460 )
    {
      ThreadpoolWork = CreateThreadpoolWork(VsIeProviderManagerWorkItemListRun, 0, 0);
      if ( !ThreadpoolWork )
      {
        LastError = GetLastError();
LABEL_8:
        FreeWLMem(v9);
        return LastError;
      }
      if ( !ResetEvent(hObject) )
      {
        LastError = GetLastError();
        CloseThreadpoolWork(ThreadpoolWork);
        goto LABEL_8;
      }
      SubmitThreadpoolWork(ThreadpoolWork);
      dword_1802A3460 = 1;
    }
    LastError = 0;
    v9[1] = qword_1802A3430;
    *v9 = &qword_1802A3428;
    *(_QWORD *)qword_1802A3430 = v9;
    qword_1802A3430 = (__int64)v9;
    return LastError;
  }
  return 14;
}

```

## disassembly

```asm
0x180085a24  push    rbx
0x180085a26  push    rbp
0x180085a27  push    rsi
0x180085a28  push    rdi
0x180085a29  push    r14
0x180085a2b  sub     rsp, 20h
0x180085a2f  mov     r14, rcx
0x180085a32  mov     rdi, r9
0x180085a35  mov     ecx, 30h ; '0'; dwBytes
0x180085a3a  mov     rsi, r8
0x180085a3d  mov     rbp, rdx
0x180085a40  call    AllocWLMem
0x180085a45  mov     rbx, rax
0x180085a48  test    rax, rax
0x180085a4b  jnz     short loc_180085A55
0x180085a4d  lea     edi, [rax+0Eh]
0x180085a50  jmp     loc_180085AF9
0x180085a55  mov     [rax+10h], r14
0x180085a59  mov     [rax+18h], rbp
0x180085a5d  mov     [rax+20h], rsi
0x180085a61  mov     [rax+28h], rdi
0x180085a65  cmp     cs:dword_1802A3460, 0
0x180085a6c  jnz     short loc_180085AD1
0x180085a6e  xor     r8d, r8d; pcbe
0x180085a71  lea     rcx, ?VsIeProviderManagerWorkItemListRun@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180085a78  xor     edx, edx; pv
0x180085a7a  call    cs:__imp_CreateThreadpoolWork
0x180085a80  mov     rsi, rax
0x180085a83  test    rax, rax
0x180085a86  jnz     short loc_180085A92
0x180085a88  call    cs:__imp_GetLastError
0x180085a8e  mov     edi, eax
0x180085a90  jmp     short loc_180085AB4
0x180085a92  mov     rcx, cs:hObject; hEvent
0x180085a99  call    cs:__imp_ResetEvent
0x180085a9f  test    eax, eax
0x180085aa1  jnz     short loc_180085ABE
0x180085aa3  call    cs:__imp_GetLastError
0x180085aa9  mov     rcx, rsi; pwk
0x180085aac  mov     edi, eax
0x180085aae  call    cs:__imp_CloseThreadpoolWork
0x180085ab4  mov     rcx, rbx
0x180085ab7  call    FreeWLMem
0x180085abc  jmp     short loc_180085AF9
0x180085abe  mov     rcx, rsi; pwk
0x180085ac1  call    cs:__imp_SubmitThreadpoolWork
0x180085ac7  mov     cs:dword_1802A3460, 1
0x180085ad1  mov     rax, cs:qword_1802A3430
0x180085ad8  xor     edi, edi
0x180085ada  mov     [rbx+8], rax
0x180085ade  lea     rax, qword_1802A3428
0x180085ae5  mov     [rbx], rax
0x180085ae8  mov     rax, cs:qword_1802A3430
0x180085aef  mov     [rax], rbx
0x180085af2  mov     cs:qword_1802A3430, rbx
0x180085af9  mov     eax, edi
0x180085afb  add     rsp, 20h
0x180085aff  pop     r14
0x180085b01  pop     rdi
0x180085b02  pop     rsi
0x180085b03  pop     rbp
0x180085b04  pop     rbx
0x180085b05  retn
```
