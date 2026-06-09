# TestServiceStarted(ulong)

- ea: `0x180009d10`
- end: `0x180009d94`
- name: `?TestServiceStarted@@YAHK@Z`
- size: `132`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003f10`
- `0x1800094f0`
- `0x18000a790`
- `0x18000b870`
- `0x180021050`

## callees

- `0x180007890`
- `0x180009d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d61`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180009d28`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180009d28`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009d3b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009d3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d4c`

## string_xrefs

- `0x180009d1a`: `Global\TermSrvReadyEvent`
- `0x180009d76`: `OpenEvent( Global\TermSrvReadyEvent ) failed: 0x%x`

## pseudocode

```c
_BOOL8 __fastcall TestServiceStarted()
{
  HANDLE v0; // rax
  void *v1; // rbx
  BOOL v2; // edi
  signed int LastError; // eax

  v0 = OpenEventW(0x100000u, 0, L"Global\\TermSrvReadyEvent");
  v1 = v0;
  if ( v0 )
  {
    v2 = WaitForSingleObject(v0, 0) == 0;
    CloseHandle(v1);
    return v2;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "OpenEvent( Global\\TermSrvReadyEvent ) failed: 0x%x", LastError);
    return 0;
  }
}

```

## disassembly

```asm
0x180009d10  mov     [rsp+arg_0], rbx
0x180009d15  push    rdi
0x180009d16  sub     rsp, 20h
0x180009d1a  lea     r8, Name; "Global\\TermSrvReadyEvent"
0x180009d21  xor     edx, edx; bInheritHandle
0x180009d23  mov     ecx, 100000h; dwDesiredAccess
0x180009d28  call    cs:__imp_OpenEventW
0x180009d2e  mov     rbx, rax
0x180009d31  test    rax, rax
0x180009d34  jz      short loc_180009D5F
0x180009d36  xor     edx, edx; dwMilliseconds
0x180009d38  mov     rcx, rax; hHandle
0x180009d3b  call    cs:__imp_WaitForSingleObject
0x180009d41  xor     edi, edi
0x180009d43  mov     rcx, rbx; hObject
0x180009d46  test    eax, eax
0x180009d48  setz    dil
0x180009d4c  call    cs:__imp_CloseHandle
0x180009d52  mov     eax, edi
0x180009d54  mov     rbx, [rsp+28h+arg_0]
0x180009d59  add     rsp, 20h
0x180009d5d  pop     rdi
0x180009d5e  retn
0x180009d5f  xor     edi, edi
0x180009d61  call    cs:__imp_GetLastError
0x180009d67  test    eax, eax
0x180009d69  jle     short loc_180009D73
0x180009d6b  movzx   eax, ax
0x180009d6e  or      eax, 80070000h
0x180009d73  mov     r8d, eax
0x180009d76  lea     rdx, aOpeneventGloba; "OpenEvent( Global\\TermSrvReadyEvent ) "...
0x180009d7d  mov     ecx, 8; int
0x180009d82  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009d87  mov     rbx, [rsp+28h+arg_0]
0x180009d8c  mov     eax, edi
0x180009d8e  add     rsp, 20h
0x180009d92  pop     rdi
0x180009d93  retn
```
