# TestServiceStarted(ulong)

- ea: `0x180008590`
- end: `0x18000862e`
- name: `?TestServiceStarted@@YAHK@Z`
- size: `158`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007d20`
- `0x1800090a0`
- `0x180009350`
- `0x18000a7b0`
- `0x180022840`

## callees

- `0x180005b40`
- `0x180008590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085f4`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800085a8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800085a8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800085c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800085c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085d8`

## string_xrefs

- `0x18000859a`: `Global\TermSrvReadyEvent`
- `0x18000860f`: `OpenEvent( Global\TermSrvReadyEvent ) failed: 0x%x`

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
0x180008590  mov     [rsp+arg_0], rbx
0x180008595  push    rdi
0x180008596  sub     rsp, 20h
0x18000859a  lea     r8, Name; "Global\\TermSrvReadyEvent"
0x1800085a1  xor     edx, edx; bInheritHandle
0x1800085a3  mov     ecx, 100000h; dwDesiredAccess
0x1800085a8  call    cs:__imp_OpenEventW
0x1800085af  nop     dword ptr [rax+rax+00h]
0x1800085b4  mov     rbx, rax
0x1800085b7  test    rax, rax
0x1800085ba  jz      short loc_1800085F2
0x1800085bc  xor     edx, edx; dwMilliseconds
0x1800085be  mov     rcx, rax; hHandle
0x1800085c1  call    cs:__imp_WaitForSingleObject
0x1800085c8  nop     dword ptr [rax+rax+00h]
0x1800085cd  xor     edi, edi
0x1800085cf  mov     rcx, rbx; hObject
0x1800085d2  test    eax, eax
0x1800085d4  setz    dil
0x1800085d8  call    cs:__imp_CloseHandle
0x1800085df  nop     dword ptr [rax+rax+00h]
0x1800085e4  mov     eax, edi
0x1800085e6  mov     rbx, [rsp+28h+arg_0]
0x1800085eb  add     rsp, 20h
0x1800085ef  pop     rdi
0x1800085f0  retn
0x1800085f2  xor     edi, edi
0x1800085f4  call    cs:__imp_GetLastError
0x1800085fb  nop     dword ptr [rax+rax+00h]
0x180008600  test    eax, eax
0x180008602  jle     short loc_18000860C
0x180008604  movzx   eax, ax
0x180008607  or      eax, 80070000h
0x18000860c  mov     r8d, eax
0x18000860f  lea     rdx, aOpeneventGloba; "OpenEvent( Global\\TermSrvReadyEvent ) "...
0x180008616  mov     ecx, 8; int
0x18000861b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008620  mov     rbx, [rsp+28h+arg_0]
0x180008625  mov     eax, edi
0x180008627  add     rsp, 20h
0x18000862b  pop     rdi
0x18000862c  retn
```
