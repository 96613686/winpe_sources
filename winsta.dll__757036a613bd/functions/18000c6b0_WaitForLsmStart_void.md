# WaitForLsmStart(void)

- ea: `0x18000c6b0`
- end: `0x18000c738`
- name: `?WaitForLsmStart@@YAHXZ`
- size: `136`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008f10`
- `0x18000c420`
- `0x18000c570`
- `0x18002a360`

## callees

- `0x180007890`
- `0x18000c6b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c70b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c70b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000c6e8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000c6e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c6ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c6ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c703`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c703`

## string_xrefs

- `0x18000c6da`: `Global\TermSrvReadyEvent`
- `0x18000c720`: `OpenEvent( Global\TermSrvReadyEvent ) failed: 0x%x`

## pseudocode

```c
__int64 WaitForLsmStart(void)
{
  HANDLE v1; // rax
  signed int LastError; // eax

  if ( g_ReadyEventHandle )
    goto LABEL_2;
  v1 = OpenEventW(0x100000u, 0, L"Global\\TermSrvReadyEvent");
  if ( v1 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_ReadyEventHandle, (signed __int64)v1, 0) )
      CloseHandle(v1);
LABEL_2:
    WaitForSingleObject(g_ReadyEventHandle, 0xFFFFFFFF);
    return 1;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  _DbgPrintMessage(8, "OpenEvent( Global\\TermSrvReadyEvent ) failed: 0x%x", LastError);
  return 0;
}

```

## disassembly

```asm
0x18000c6b0  sub     rsp, 28h
0x18000c6b4  cmp     cs:?g_ReadyEventHandle@@3PEAXEA, 0; void * g_ReadyEventHandle
0x18000c6bc  jz      short loc_18000C6DA
0x18000c6be  mov     rcx, cs:?g_ReadyEventHandle@@3PEAXEA; hHandle
0x18000c6c5  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000c6ca  call    cs:__imp_WaitForSingleObject
0x18000c6d0  mov     eax, 1
0x18000c6d5  add     rsp, 28h
0x18000c6d9  retn
0x18000c6da  lea     r8, Name; "Global\\TermSrvReadyEvent"
0x18000c6e1  xor     edx, edx; bInheritHandle
0x18000c6e3  mov     ecx, 100000h; dwDesiredAccess
0x18000c6e8  call    cs:__imp_OpenEventW
0x18000c6ee  mov     rcx, rax; hObject
0x18000c6f1  test    rax, rax
0x18000c6f4  jz      short loc_18000C70B
0x18000c6f6  xor     eax, eax
0x18000c6f8  lock cmpxchg cs:?g_ReadyEventHandle@@3PEAXEA, rcx; void * g_ReadyEventHandle
0x18000c701  jz      short loc_18000C6BE
0x18000c703  call    cs:__imp_CloseHandle
0x18000c709  jmp     short loc_18000C6BE
0x18000c70b  call    cs:__imp_GetLastError
0x18000c711  test    eax, eax
0x18000c713  jle     short loc_18000C71D
0x18000c715  movzx   eax, ax
0x18000c718  or      eax, 80070000h
0x18000c71d  mov     r8d, eax
0x18000c720  lea     rdx, aOpeneventGloba; "OpenEvent( Global\\TermSrvReadyEvent ) "...
0x18000c727  mov     ecx, 8; int
0x18000c72c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c731  xor     eax, eax
0x18000c733  add     rsp, 28h
0x18000c737  retn
```
