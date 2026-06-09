# RouterAssert

- ea: `0x180005b00`
- end: `0x180005b9d`
- name: `RouterAssert`
- size: `157`
- prototype: `void __stdcall(PSTR pszFailedAssertion, PSTR pszFileName, DWORD dwLineNumber, PSTR pszMessage)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005b00`

## import_xrefs

- `ntdll!DbgPrint` at `0x180005b37`
- `ntdll!DbgPrint` at `0x180005b37`
- `ntdll!DbgPrompt` at `0x180005b4f`
- `ntdll!DbgPrompt` at `0x180005b4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005b7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005b7e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180005b8c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180005b8c`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180005b77`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180005b77`

## string_xrefs

- `0x180005b48`: `Break, Ignore, Terminate Process or Terminate Thread (bipt)? `

## pseudocode

```c
void __stdcall RouterAssert(PSTR pszFailedAssertion, PSTR pszFileName, DWORD dwLineNumber, PSTR pszMessage)
{
  const char *v4; // rbx
  HANDLE CurrentProcess; // rax
  CHAR Response; // [rsp+78h] [rbp+20h] BYREF

  v4 = pszMessage;
  if ( !pszMessage )
    v4 = (const char *)&dword_18000C88C;
  while ( 1 )
  {
    DbgPrint(
      "\n***Assertion failed: %s%s\n*** Source File: %s, line %ld\n\n",
      v4,
      pszFailedAssertion,
      pszFileName,
      dwLineNumber);
    DbgPrompt("Break, Ignore, Terminate Process or Terminate Thread (bipt)? ", &Response, 2u);
    if ( Response == 73 )
      break;
    switch ( Response )
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
0x180005b00  push    rbx
0x180005b02  push    rbp
0x180005b03  push    rsi
0x180005b04  push    rdi
0x180005b05  sub     rsp, 38h
0x180005b09  test    r9, r9
0x180005b0c  lea     rax, dword_18000C88C
0x180005b13  mov     rbx, r9
0x180005b16  mov     edi, r8d
0x180005b19  cmovz   rbx, rax
0x180005b1d  mov     rsi, rdx
0x180005b20  mov     rbp, rcx
0x180005b23  mov     r9, rsi
0x180005b26  mov     [rsp+58h+var_38], edi
0x180005b2a  mov     r8, rbp
0x180005b2d  lea     rcx, Format; "\n***Assertion failed: %s%s\n*** Source"...
0x180005b34  mov     rdx, rbx
0x180005b37  call    cs:__imp_DbgPrint
0x180005b3d  mov     r8d, 2; MaximumResponseLength
0x180005b43  lea     rdx, [rsp+58h+Response]; Response
0x180005b48  lea     rcx, Prompt; "Break, Ignore, Terminate Process or Ter"...
0x180005b4f  call    cs:__imp_DbgPrompt
0x180005b55  movzx   eax, word ptr [rsp+58h+Response]
0x180005b5a  cmp     al, 49h ; 'I'
0x180005b5c  jz      short loc_180005B94
0x180005b5e  cmp     al, 50h ; 'P'
0x180005b60  jz      short loc_180005B7E
0x180005b62  cmp     al, 54h ; 'T'
0x180005b64  jz      short loc_180005B72
0x180005b66  cmp     al, 69h ; 'i'
0x180005b68  jz      short loc_180005B94
0x180005b6a  cmp     al, 70h ; 'p'
0x180005b6c  jz      short loc_180005B7E
0x180005b6e  cmp     al, 74h ; 't'
0x180005b70  jnz     short loc_180005B23
0x180005b72  mov     ecx, 0C0000001h; dwExitCode
0x180005b77  call    cs:__imp_ExitThread
0x180005b7e  call    cs:__imp_GetCurrentProcess
0x180005b84  mov     rcx, rax; hProcess
0x180005b87  mov     edx, 0C0000001h; uExitCode
0x180005b8c  call    cs:__imp_TerminateProcess
0x180005b92  jmp     short loc_180005B23
0x180005b94  add     rsp, 38h
0x180005b98  pop     rdi
0x180005b99  pop     rsi
0x180005b9a  pop     rbp
0x180005b9b  pop     rbx
0x180005b9c  retn
```
