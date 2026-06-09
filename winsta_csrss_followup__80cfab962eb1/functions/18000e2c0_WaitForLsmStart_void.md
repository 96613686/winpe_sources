# WaitForLsmStart(void)

- ea: `0x18000e2c0`
- end: `0x18000e362`
- name: `?WaitForLsmStart@@YAHXZ`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007690`
- `0x18000e000`
- `0x18000e160`
- `0x18002c050`

## callees

- `0x180005b40`
- `0x18000e2c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e32e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e32e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000e2ff`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000e2ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e2da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e2da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e320`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e320`

## string_xrefs

- `0x18000e2f1`: `Global\TermSrvReadyEvent`
- `0x18000e349`: `OpenEvent( Global\TermSrvReadyEvent ) failed: 0x%x`

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
0x18000e2c0  sub     rsp, 28h
0x18000e2c4  cmp     cs:?g_ReadyEventHandle@@3PEAXEA, 0; void * g_ReadyEventHandle
0x18000e2cc  jz      short loc_18000E2F1
0x18000e2ce  mov     rcx, cs:?g_ReadyEventHandle@@3PEAXEA; hHandle
0x18000e2d5  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000e2da  call    cs:__imp_WaitForSingleObject
0x18000e2e1  nop     dword ptr [rax+rax+00h]
0x18000e2e6  mov     eax, 1
0x18000e2eb  add     rsp, 28h
0x18000e2ef  retn
0x18000e2f1  lea     r8, Name; "Global\\TermSrvReadyEvent"
0x18000e2f8  xor     edx, edx; bInheritHandle
0x18000e2fa  mov     ecx, 100000h; dwDesiredAccess
0x18000e2ff  call    cs:__imp_OpenEventW
0x18000e306  nop     dword ptr [rax+rax+00h]
0x18000e30b  mov     rcx, rax; hObject
0x18000e30e  test    rax, rax
0x18000e311  jz      short loc_18000E32E
0x18000e313  xor     eax, eax
0x18000e315  lock cmpxchg cs:?g_ReadyEventHandle@@3PEAXEA, rcx; void * g_ReadyEventHandle
0x18000e31e  jz      short loc_18000E2CE
0x18000e320  call    cs:__imp_CloseHandle
0x18000e327  nop     dword ptr [rax+rax+00h]
0x18000e32c  jmp     short loc_18000E2CE
0x18000e32e  call    cs:__imp_GetLastError
0x18000e335  nop     dword ptr [rax+rax+00h]
0x18000e33a  test    eax, eax
0x18000e33c  jle     short loc_18000E346
0x18000e33e  movzx   eax, ax
0x18000e341  or      eax, 80070000h
0x18000e346  mov     r8d, eax
0x18000e349  lea     rdx, aOpeneventGloba; "OpenEvent( Global\\TermSrvReadyEvent ) "...
0x18000e350  mov     ecx, 8; int
0x18000e355  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e35a  xor     eax, eax
0x18000e35c  add     rsp, 28h
0x18000e360  retn
```
