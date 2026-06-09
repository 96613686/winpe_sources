# AssertW(ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1800e05d4`
- end: `0x1800e079c`
- name: `?AssertW@@YAXPEBG000K@Z`
- size: `456`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180027bf4`
- `0x18003b038`
- `0x180060080`
- `0x18006cb88`
- `0x18006cbe0`
- `0x1800dbbb0`
- `0x1800dd278`
- `0x1800dd378`
- `0x1800e0900`

## callees

- `0x1800e05d4`
- `0x1800e07e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800e0764`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800e0764`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0740`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0740`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e0756`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e0756`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x1800e074e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x1800e074e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e05f1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e0661`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e05f1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e0661`
- `ntdll!DbgPrintEx` at `0x1800e06ca`
- `ntdll!DbgPrintEx` at `0x1800e0709`
- `ntdll!DbgPrintEx` at `0x1800e077f`
- `ntdll!DbgPrintEx` at `0x1800e06ca`
- `ntdll!DbgPrintEx` at `0x1800e0709`
- `ntdll!DbgPrintEx` at `0x1800e077f`
- `ntdll!DbgPrompt` at `0x1800e06e6`
- `ntdll!DbgPrompt` at `0x1800e06e6`

## string_xrefs

- `0x1800e06df`: `Break, Go (continue), terminate Process, or terminate Thread (bgpt)? `
- `0x1800e06ff`: `(No kernel debugger is present.) Respond with:\n  g                    -- Go (continue)\n  eb 0x%p 'p';g  -- terminate Process\n  eb 0x%p 't';g  -- terminate Thread\n or regular debugging.\n`

## pseudocode

```c
void __fastcall AssertW(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  const wchar_t *v9; // r15
  const char *v10; // r14
  const char *v11; // r12
  const wchar_t *v12; // r13
  const wchar_t *v13; // rax
  int v14; // eax
  int v15; // ebx
  BOOL v16; // eax
  CHAR v17; // cl
  const wchar_t *v18; // rax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  CHAR Response[8]; // [rsp+60h] [rbp-58h] BYREF
  const wchar_t *v22; // [rsp+68h] [rbp-50h]

  if ( IsDebuggerPresent() || (unsigned int)IsKernelDebuggerPresent() )
  {
    v9 = a3;
    if ( !a3 )
      v9 = (const wchar_t *)&dword_1800F6FBC;
    v10 = ", ";
    if ( !a3 )
      v10 = (const char *)&qword_1800F81A8;
    v11 = "Function: ";
    if ( !a3 )
      v11 = (const char *)&qword_1800F81A8;
    v12 = a2;
    v13 = a1;
    if ( !a2 )
      v12 = (const wchar_t *)&dword_1800F6FBC;
    if ( !a1 )
      v13 = (const wchar_t *)&dword_1800F6FBC;
    v22 = v13;
    while ( 1 )
    {
      while ( 1 )
      {
        v14 = IsKernelDebuggerPresent();
        strcpy(Response, "?");
        v15 = v14;
        if ( !v14 )
        {
          v16 = IsDebuggerPresent();
          v17 = Response[0];
          if ( v16 )
            v17 = 103;
          Response[0] = v17;
        }
        if ( !a1 || (v18 = L"\n***  ", !a2) )
          v18 = (const wchar_t *)&dword_1800F6FBC;
        DbgPrintEx(
          0x65u,
          0,
          "\n*** Assertion failed: %ls%ls%ls\n***   %s%ls%sSource: `%ls:%ld`\n\n",
          v22,
          v18,
          v12,
          v11,
          v9,
          v10,
          a4,
          a5);
        if ( !v15 )
        {
          DbgPrintEx(
            0x65u,
            0,
            "(No kernel debugger is present.) Respond with:\n"
            "  g                    -- Go (continue)\n"
            "  eb 0x%p 'p';g  -- terminate Process\n"
            "  eb 0x%p 't';g  -- terminate Thread\n"
            " or regular debugging.\n",
            Response,
            Response);
          __debugbreak();
        }
        DbgPrompt("Break, Go (continue), terminate Process, or terminate Thread (bgpt)? ", Response, 2u);
        if ( Response[0] <= 98 )
          break;
        if ( Response[0] == 103 )
          return;
        if ( Response[0] != 105 )
        {
          if ( Response[0] != 112 )
          {
            if ( Response[0] != 116 )
              goto LABEL_38;
LABEL_36:
            CurrentThread = GetCurrentThread();
            TerminateThread(CurrentThread, 0xC0000001);
            goto LABEL_38;
          }
LABEL_37:
          CurrentProcess = GetCurrentProcess();
          TerminateProcess(CurrentProcess, 0xC0000001);
          goto LABEL_38;
        }
LABEL_39:
        DbgPrintEx(0x65u, 0, "'i' is only supported with debug builds.\n");
      }
      switch ( Response[0] )
      {
        case 'b':
        case 'B':
          __debugbreak();
          return;
        case 'G':
          return;
        case 'I':
          goto LABEL_39;
        case 'P':
          goto LABEL_37;
        case 'T':
          goto LABEL_36;
      }
LABEL_38:
      DbgPrintEx(0x65u, 0, "Unrecognized response.\n");
    }
  }
}

```

## disassembly

```asm
0x1800e05d4  push    rbx
0x1800e05d6  push    rbp
0x1800e05d7  push    rsi
0x1800e05d8  push    rdi
0x1800e05d9  push    r12
0x1800e05db  push    r13
0x1800e05dd  push    r14
0x1800e05df  push    r15
0x1800e05e1  sub     rsp, 78h
0x1800e05e5  mov     rbp, r9
0x1800e05e8  mov     rbx, r8
0x1800e05eb  mov     rdi, rdx
0x1800e05ee  mov     rsi, rcx
0x1800e05f1  call    cs:__imp_IsDebuggerPresent
0x1800e05f7  test    eax, eax
0x1800e05f9  jnz     short loc_1800E0608
0x1800e05fb  call    ?IsKernelDebuggerPresent@@YAHXZ; IsKernelDebuggerPresent(void)
0x1800e0600  test    eax, eax
0x1800e0602  jz      loc_1800E078B
0x1800e0608  test    rbx, rbx
0x1800e060b  lea     rax, qword_1800F81A8
0x1800e0612  lea     rcx, dword_1800F6FBC
0x1800e0619  mov     r15, rbx
0x1800e061c  cmovz   r15, rcx
0x1800e0620  lea     r14, asc_1800FB3E4; ", "
0x1800e0627  cmovz   r14, rax
0x1800e062b  lea     r12, aFunction; "Function: "
0x1800e0632  cmovz   r12, rax
0x1800e0636  mov     r13, rdi
0x1800e0639  test    rdi, rdi
0x1800e063c  mov     rax, rsi
0x1800e063f  cmovz   r13, rcx
0x1800e0643  test    rsi, rsi
0x1800e0646  cmovz   rax, rcx
0x1800e064a  mov     [rsp+0B8h+var_50], rax
0x1800e064f  call    ?IsKernelDebuggerPresent@@YAHXZ; IsKernelDebuggerPresent(void)
0x1800e0654  mov     word ptr [rsp+0B8h+Response], 3Fh ; '?'
0x1800e065b  mov     ebx, eax
0x1800e065d  test    eax, eax
0x1800e065f  jnz     short loc_1800E0678
0x1800e0661  call    cs:__imp_IsDebuggerPresent
0x1800e0667  movzx   ecx, [rsp+0B8h+Response]
0x1800e066c  test    eax, eax
0x1800e066e  lea     eax, [rbx+67h]
0x1800e0671  cmovnz  ecx, eax
0x1800e0674  mov     [rsp+0B8h+Response], cl
0x1800e0678  test    rsi, rsi
0x1800e067b  jz      short loc_1800E0689
0x1800e067d  lea     rax, asc_1800FB438; "\n***  "
0x1800e0684  test    rdi, rdi
0x1800e0687  jnz     short loc_1800E0690
0x1800e0689  lea     rax, dword_1800F6FBC
0x1800e0690  mov     ecx, [rsp+0B8h+arg_20]
0x1800e0697  lea     r8, Format; "\n*** Assertion failed: %ls%ls%ls\n*** "...
0x1800e069e  mov     r9, [rsp+0B8h+var_50]
0x1800e06a3  xor     edx, edx; Level
0x1800e06a5  mov     [rsp+0B8h+var_68], ecx
0x1800e06a9  mov     [rsp+0B8h+var_70], rbp
0x1800e06ae  mov     [rsp+0B8h+var_78], r14
0x1800e06b3  mov     [rsp+0B8h+var_80], r15
0x1800e06b8  lea     ecx, [rdx+65h]; ComponentId
0x1800e06bb  mov     [rsp+0B8h+var_88], r12
0x1800e06c0  mov     [rsp+0B8h+var_90], r13
0x1800e06c5  mov     [rsp+0B8h+var_98], rax
0x1800e06ca  call    cs:__imp_DbgPrintEx
0x1800e06d0  test    ebx, ebx
0x1800e06d2  jz      short loc_1800E06EE
0x1800e06d4  mov     r8d, 2; MaximumResponseLength
0x1800e06da  lea     rdx, [rsp+0B8h+Response]; Response
0x1800e06df  lea     rcx, Prompt; "Break, Go (continue), terminate Process"...
0x1800e06e6  call    cs:__imp_DbgPrompt
0x1800e06ec  jmp     short loc_1800E0710
0x1800e06ee  xor     edx, edx; Level
0x1800e06f0  lea     rax, [rsp+0B8h+Response]
0x1800e06f5  lea     r9, [rsp+0B8h+Response]
0x1800e06fa  mov     [rsp+0B8h+var_98], rax
0x1800e06ff  lea     r8, aNoKernelDebugg; "(No kernel debugger is present.) Respon"...
0x1800e0706  lea     ecx, [rdx+65h]; ComponentId
0x1800e0709  call    cs:__imp_DbgPrintEx
0x1800e070f  int     3; Trap to Debugger
0x1800e0710  mov     al, [rsp+0B8h+Response]
0x1800e0714  cmp     al, 62h ; 'b'
0x1800e0716  jg      short loc_1800E0730
0x1800e0718  jz      short loc_1800E078A
0x1800e071a  cmp     al, 42h ; 'B'
0x1800e071c  jz      short loc_1800E078A
0x1800e071e  cmp     al, 47h ; 'G'
0x1800e0720  jz      short loc_1800E078B
0x1800e0722  cmp     al, 49h ; 'I'
0x1800e0724  jz      short loc_1800E0773
0x1800e0726  cmp     al, 50h ; 'P'
0x1800e0728  jz      short loc_1800E0756
0x1800e072a  cmp     al, 54h ; 'T'
0x1800e072c  jz      short loc_1800E0740
0x1800e072e  jmp     short loc_1800E076A
0x1800e0730  cmp     al, 67h ; 'g'
0x1800e0732  jz      short loc_1800E078B
0x1800e0734  cmp     al, 69h ; 'i'
0x1800e0736  jz      short loc_1800E0773
0x1800e0738  cmp     al, 70h ; 'p'
0x1800e073a  jz      short loc_1800E0756
0x1800e073c  cmp     al, 74h ; 't'
0x1800e073e  jnz     short loc_1800E076A
0x1800e0740  call    cs:__imp_GetCurrentThread
0x1800e0746  mov     rcx, rax; hThread
0x1800e0749  mov     edx, 0C0000001h; dwExitCode
0x1800e074e  call    cs:__imp_TerminateThread
0x1800e0754  jmp     short loc_1800E076A
0x1800e0756  call    cs:__imp_GetCurrentProcess
0x1800e075c  mov     rcx, rax; hProcess
0x1800e075f  mov     edx, 0C0000001h; uExitCode
0x1800e0764  call    cs:__imp_TerminateProcess
0x1800e076a  lea     r8, aUnrecognizedRe; "Unrecognized response.\n"
0x1800e0771  jmp     short loc_1800E077A
0x1800e0773  lea     r8, aIIsOnlySupport; "'i' is only supported with debug builds"...
0x1800e077a  xor     edx, edx; Level
0x1800e077c  lea     ecx, [rdx+65h]; ComponentId
0x1800e077f  call    cs:__imp_DbgPrintEx
0x1800e0785  jmp     loc_1800E064F
0x1800e078a  int     3; Trap to Debugger
0x1800e078b  add     rsp, 78h
0x1800e078f  pop     r15
0x1800e0791  pop     r14
0x1800e0793  pop     r13
0x1800e0795  pop     r12
0x1800e0797  pop     rdi
0x1800e0798  pop     rsi
0x1800e0799  pop     rbp
0x1800e079a  pop     rbx
0x1800e079b  retn
```
