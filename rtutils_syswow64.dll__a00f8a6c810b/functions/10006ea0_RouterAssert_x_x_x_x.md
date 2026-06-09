# RouterAssert(x,x,x,x)

- ea: `0x10006ea0`
- end: `0x10006f1c`
- name: `_RouterAssert@16`
- size: `124`
- prototype: `void __stdcall(PSTR pszFailedAssertion, PSTR pszFileName, DWORD dwLineNumber, PSTR pszMessage)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x10006ea0`

## import_xrefs

- `ntdll!DbgPrint` at `0x10006ec9`
- `ntdll!DbgPrint` at `0x10006ec9`
- `ntdll!DbgPrompt` at `0x10006edd`
- `ntdll!DbgPrompt` at `0x10006edd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x10006f07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x10006f07`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x10006f0e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x10006f0e`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x10006f00`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x10006f00`

## string_xrefs

- `0x10006ed8`: `Break, Ignore, Terminate Process or Terminate Thread (bipt)? `

## pseudocode

```c
void __stdcall RouterAssert(PSTR pszFailedAssertion, PSTR pszFileName, DWORD dwLineNumber, PSTR pszMessage)
{
  const char *v4; // esi
  HANDLE CurrentProcess; // eax
  CHAR Response[4]; // [esp+4h] [ebp-4h] BYREF

  v4 = (const char *)&word_100013F6;
  if ( pszMessage )
    v4 = pszMessage;
  while ( 1 )
  {
    _DbgPrint(
      "\n***Assertion failed: %s%s\n*** Source File: %s, line %ld\n\n",
      v4,
      pszFailedAssertion,
      pszFileName,
      dwLineNumber);
    DbgPrompt("Break, Ignore, Terminate Process or Terminate Thread (bipt)? ", Response, 2u);
    if ( Response[0] == 73 )
      break;
    switch ( Response[0] )
    {
      case 'P':
        goto LABEL_10;
      case 'T':
        goto LABEL_9;
      case 'i':
        return;
      case 'p':
LABEL_10:
        CurrentProcess = GetCurrentProcess();
        TerminateProcess(CurrentProcess, 0xC0000001);
        break;
      case 't':
LABEL_9:
        ExitThread(0xC0000001);
    }
  }
}

```

## disassembly

```asm
0x10006ea0  mov     edi, edi
0x10006ea2  push    ebp
0x10006ea3  mov     ebp, esp
0x10006ea5  push    ecx
0x10006ea6  cmp     [ebp+pszMessage], 0
0x10006eaa  push    esi
0x10006eab  mov     esi, offset word_100013F6
0x10006eb0  cmovnz  esi, [ebp+pszMessage]
0x10006eb4  push    edi
0x10006eb5  mov     edi, 0C0000001h
0x10006eba  push    [ebp+dwLineNumber]
0x10006ebd  push    [ebp+pszFileName]
0x10006ec0  push    [ebp+pszFailedAssertion]
0x10006ec3  push    esi
0x10006ec4  push    offset Format; "\n***Assertion failed: %s%s\n*** Source"...
0x10006ec9  call    ds:__imp__DbgPrint
0x10006ecf  add     esp, 14h
0x10006ed2  lea     eax, [ebp+Response]
0x10006ed5  push    2; MaximumResponseLength
0x10006ed7  push    eax; Response
0x10006ed8  push    offset Prompt; "Break, Ignore, Terminate Process or Ter"...
0x10006edd  call    ds:__imp__DbgPrompt@12; DbgPrompt(x,x,x)
0x10006ee3  mov     ax, word ptr [ebp+Response]
0x10006ee7  cmp     al, 49h ; 'I'
0x10006ee9  jz      short loc_10006F16
0x10006eeb  cmp     al, 50h ; 'P'
0x10006eed  jz      short loc_10006F06
0x10006eef  cmp     al, 54h ; 'T'
0x10006ef1  jz      short loc_10006EFF
0x10006ef3  cmp     al, 69h ; 'i'
0x10006ef5  jz      short loc_10006F16
0x10006ef7  cmp     al, 70h ; 'p'
0x10006ef9  jz      short loc_10006F06
0x10006efb  cmp     al, 74h ; 't'
0x10006efd  jnz     short loc_10006EBA
0x10006eff  push    edi; dwExitCode
0x10006f00  call    ds:__imp__ExitThread@4; ExitThread(x)
0x10006f06  push    edi; uExitCode
0x10006f07  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x10006f0d  push    eax; hProcess
0x10006f0e  call    ds:__imp__TerminateProcess@8; TerminateProcess(x,x)
0x10006f14  jmp     short loc_10006EBA
0x10006f16  pop     edi
0x10006f17  pop     esi
0x10006f18  leave
0x10006f19  retn    10h
```
