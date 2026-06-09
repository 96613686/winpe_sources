# HandleClockDisplnThread(void *,uchar)

- ea: `0x18004cb80`
- end: `0x18004cc1b`
- name: `?HandleClockDisplnThread@@YAXPEAXE@Z`
- size: `155`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18004cb80`
- `0x18004cd1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18004cb95`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18004cc09`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18004cb95`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18004cc09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cbc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cbc8`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18004cbb8`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18004cbb8`

## string_xrefs

- `0x18004cbe2`: `Shutdown clock disciplining thread, restart service async`

## pseudocode

```c
void __fastcall HandleClockDisplnThread(void *a1)
{
  _BYTE v1[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v2[48]; // [rsp+38h] [rbp-30h] BYREF
  DWORD ExitCode; // [rsp+80h] [rbp+18h] BYREF
  __int64 v4; // [rsp+88h] [rbp+20h]

  ExitCode = -2147467259;
  v4 = _set_se_translator(SeTransFunc);
  try
  {
    if ( !GetExitCodeThread(hThread, &ExitCode) )
      GetLastError();
    if ( (unsigned __int8)FileLogAllowEntry(73) )
      FileLogAdd(L"Shutdown clock disciplining thread, restart service async");
    NotifyShutdown(ExitCode);
  }
  catch ( SeException v2 )
  {
    SeException::~SeException((SeException *)v2);
  }
  catch ( std::bad_alloc v1 )
  {
    SeException::~SeException((SeException *)v1);
  }
  catch ( ... )
  {
  }
  _set_se_translator(v4);
}

```

## disassembly

```asm
0x18004cb80  mov     rax, rsp
0x18004cb83  sub     rsp, 68h
0x18004cb87  mov     dword ptr [rax+18h], 80004005h
0x18004cb8e  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18004cb95  call    cs:__imp__set_se_translator
0x18004cb9c  nop     dword ptr [rax+rax+00h]
0x18004cba1  mov     [rsp+68h+arg_18], rax
0x18004cba9  lea     rdx, [rsp+68h+ExitCode]; lpExitCode
0x18004cbb1  mov     rcx, cs:hThread; hThread
0x18004cbb8  call    cs:__imp_GetExitCodeThread
0x18004cbbf  nop     dword ptr [rax+rax+00h]
0x18004cbc4  test    eax, eax
0x18004cbc6  jnz     short loc_18004CBD4
0x18004cbc8  call    cs:__imp_GetLastError
0x18004cbcf  nop     dword ptr [rax+rax+00h]
0x18004cbd4  mov     ecx, 49h ; 'I'
0x18004cbd9  call    FileLogAllowEntry
0x18004cbde  test    al, al
0x18004cbe0  jz      short loc_18004CBEE
0x18004cbe2  lea     rcx, aShutdownClockD; "Shutdown clock disciplining thread, res"...
0x18004cbe9  call    FileLogAdd
0x18004cbee  mov     ecx, [rsp+68h+ExitCode]; unsigned int
0x18004cbf5  call    ?NotifyShutdown@@YAJK@Z; NotifyShutdown(ulong)
0x18004cbfa  nop
0x18004cbfb  jmp     short loc_18004CC01
0x18004cbfd  jmp     short loc_18004CC01
0x18004cbff  jmp     short $+2
0x18004cc01  mov     rcx, [rsp+68h+arg_18]
0x18004cc09  call    cs:__imp__set_se_translator
0x18004cc10  nop     dword ptr [rax+rax+00h]
0x18004cc15  add     rsp, 68h
0x18004cc19  retn
```
