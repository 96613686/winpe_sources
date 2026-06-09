# SaferContextDump(_EXCEPTION_POINTERS * const,wchar_t const *,wchar_t const *,unsigned __int64 &)

- ea: `0x100464930`
- end: `0x100464c4c`
- name: `?SaferContextDump@@YAHQEAU_EXCEPTION_POINTERS@@PEB_W1AEA_K@Z`
- size: `796`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *const, const wchar_t *, const wchar_t *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x100419190`
- `0x100419360`

## callees

- `0x10045d480`
- `0x100464930`
- `0x100486af0`

## import_xrefs

- `KERNEL32!RtlCaptureStackBackTrace` at `0x100464b00`
- `KERNEL32!RtlCaptureStackBackTrace` at `0x100464b00`
- `KERNEL32!GetCurrentProcess` at `0x100464a24`
- `KERNEL32!GetCurrentProcess` at `0x100464a24`
- `KERNEL32!LoadLibraryW` at `0x100464a49`
- `KERNEL32!LoadLibraryW` at `0x100464a49`
- `KERNEL32!GetProcAddress` at `0x100464a65`
- `KERNEL32!GetProcAddress` at `0x100464a7a`
- `KERNEL32!GetProcAddress` at `0x100464a8d`
- `KERNEL32!GetProcAddress` at `0x100464aa0`
- `KERNEL32!GetProcAddress` at `0x100464a65`
- `KERNEL32!GetProcAddress` at `0x100464a7a`
- `KERNEL32!GetProcAddress` at `0x100464a8d`
- `KERNEL32!GetProcAddress` at `0x100464aa0`
- `KERNEL32!GetModuleHandleW` at `0x100464a34`
- `KERNEL32!GetModuleHandleW` at `0x100464a34`
- `sqldk!?GetVMAccess@SOS_OS@@SAHPEBX_KH@Z` at `0x100464c06`
- `sqldk!?GetVMAccess@SOS_OS@@SAHPEBX_KH@Z` at `0x100464c06`

## string_xrefs

- `0x100464a2a`: `dbghelp.dll`
- `0x100464a42`: `dbghelp.dll`

## pseudocode

```c
__int64 __fastcall SaferContextDump(
        struct _EXCEPTION_POINTERS *const a1,
        const wchar_t *a2,
        const wchar_t *a3,
        unsigned __int64 *a4)
{
  PCONTEXT ContextRecord; // rsi
  unsigned int v6; // ebx
  unsigned int v7; // ebp
  HANDLE CurrentProcess; // r15
  HMODULE ModuleHandleW; // rdi
  FARPROC v10; // r12
  FARPROC v11; // r13
  FARPROC v12; // rcx
  USHORT v13; // ax
  __int64 v14; // r13
  __int64 v15; // rsi
  char *v16; // rdi
  __int64 v17; // rax
  unsigned __int64 v18; // rdi
  unsigned int v19; // eax
  char v20; // di
  PVOID *v21; // rdi
  DWORD64 Rip; // rdi
  _QWORD *Rbp; // rsi
  unsigned int v24; // eax
  __int64 v26; // [rsp+20h] [rbp-108h]
  bool v27; // [rsp+41h] [rbp-E7h]
  struct _CONTEXT *v28; // [rsp+48h] [rbp-E0h]
  FARPROC ProcAddress; // [rsp+50h] [rbp-D8h]
  void (__fastcall *v30)(HANDLE); // [rsp+58h] [rbp-D0h]
  PVOID BackTrace[16]; // [rsp+60h] [rbp-C8h] BYREF

  ContextRecord = a1->ContextRecord;
  v28 = ContextRecord;
  StackDumpScErrLog(
    L"%ls: Address=0x%p Exception Code = %lx\n",
    a2,
    a1->ExceptionRecord->ExceptionAddress,
    a1->ExceptionRecord->ExceptionCode);
  StackDumpScErrLog(
    L"Rax=%016lx Rbx=%016lx Rcx=%016lx Rdx=%016lx\n",
    ContextRecord->Rax,
    ContextRecord->Rbx,
    ContextRecord->Rcx,
    ContextRecord->Rdx);
  StackDumpScErrLog(
    L"Rsi=%016lx Rdi=%016lx Rip=%016lx Rsp=%016lx\n",
    ContextRecord->Rsi,
    ContextRecord->Rdi,
    ContextRecord->Rip,
    ContextRecord->Rsp);
  StackDumpScErrLog(L"Rbp=%016lx EFlags=%016lx\n", ContextRecord->Rbp, ContextRecord->EFlags);
  LODWORD(v26) = ContextRecord->SegEs;
  StackDumpScErrLog(
    L"cs=%016lx ss=%016lx ds=%016lx\nes=%016lx fs=%016lx gs=%016lx\n",
    ContextRecord->SegCs,
    ContextRecord->SegSs,
    ContextRecord->SegDs,
    v26,
    ContextRecord->SegFs,
    ContextRecord->SegGs);
  v6 = 0;
  *a4 = 0;
  v7 = 0;
  CurrentProcess = GetCurrentProcess();
  ModuleHandleW = GetModuleHandleW(L"dbghelp.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = LoadLibraryW(L"dbghelp.dll");
    if ( !ModuleHandleW )
      goto LABEL_22;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "SymInitializeW");
  v10 = GetProcAddress(ModuleHandleW, "SymGetModuleBase64");
  v11 = GetProcAddress(ModuleHandleW, "SymRefreshModuleList");
  v12 = GetProcAddress(ModuleHandleW, "SymCleanup");
  v30 = (void (__fastcall *)(HANDLE))v12;
  if ( !ProcAddress || !v10 || !v11 || !v12 )
    goto LABEL_22;
  v27 = ((unsigned int (__fastcall *)(HANDLE, _QWORD, _QWORD))ProcAddress)(CurrentProcess, 0, 0) != 0;
  if ( ((unsigned int (__fastcall *)(HANDLE))v11)(CurrentProcess) )
  {
    v13 = RtlCaptureStackBackTrace(0, 0x10u, BackTrace, 0);
    if ( v13 )
    {
      v7 = v13;
      v14 = v13;
      v15 = 0;
      while ( 1 )
      {
        v16 = (char *)BackTrace[v15];
        v17 = ((__int64 (__fastcall *)(HANDLE, char *))v10)(CurrentProcess, v16);
        if ( !v17 )
          break;
        v18 = (unsigned __int64)&v16[-v17];
        ++v15;
        v19 = v18 ^ __ROL4__(*(_DWORD *)a4, 1);
        *a4 = v19 + (HIDWORD(v18) ^ __ROL4__(v19, 1));
        if ( v15 >= v14 )
        {
          ContextRecord = v28;
          v20 = 1;
          goto LABEL_15;
        }
      }
      ContextRecord = v28;
    }
  }
  v20 = 0;
LABEL_15:
  if ( v27 )
    v30(CurrentProcess);
  if ( v20 )
  {
    if ( v7 )
    {
      v21 = BackTrace;
      do
        StackDumpScErrLog(L"Frame %d: 0x%p", v6++, *v21++);
      while ( v6 < v7 );
    }
  }
  else
  {
LABEL_22:
    *a4 = 0;
    Rip = ContextRecord->Rip;
    Rbp = (_QWORD *)ContextRecord->Rbp;
    do
    {
      ++v6;
      if ( !Rip )
        break;
      StackDumpScErrLog(L"%d: Frame %p Return Address %p\n", v6, Rbp, Rip);
      if ( v6 < 0x10 )
      {
        v24 = Rip ^ __ROL4__(*(_DWORD *)a4, 1);
        *a4 = v24 + (HIDWORD(Rip) ^ __ROL4__(v24, 1));
      }
      if ( !SOS_OS::GetVMAccess(Rbp, 0x10u, 1) )
        break;
      Rip = Rbp[1];
      Rbp = (_QWORD *)*Rbp;
    }
    while ( v6 < 0x14 );
  }
  return 1;
}

```

## disassembly

```asm
0x100464930  mov     [rsp+arg_10], rbx
0x100464935  push    rbp
0x100464936  push    rsi
0x100464937  push    rdi
0x100464938  push    r12
0x10046493a  push    r13
0x10046493c  push    r14
0x10046493e  push    r15
0x100464940  sub     rsp, 0F0h
0x100464947  mov     rax, cs:__security_cookie
0x10046494e  xor     rax, rsp
0x100464951  mov     [rsp+128h+var_48], rax
0x100464959  mov     r8, [rcx]
0x10046495c  mov     r14, r9
0x10046495f  mov     rsi, [rcx+8]
0x100464963  lea     rcx, aLsAddress0xPEx; "%ls: Address=0x%p Exception Code = %lx"...
0x10046496a  mov     [rsp+128h+var_E0], rsi
0x10046496f  mov     r9d, [r8]
0x100464972  mov     r8, [r8+10h]
0x100464976  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x10046497b  mov     rax, [rsi+88h]
0x100464982  lea     rcx, aRax016lxRbx016; "Rax=%016lx Rbx=%016lx Rcx=%016lx Rdx=%0"...
0x100464989  mov     r9, [rsi+80h]
0x100464990  mov     r8, [rsi+90h]
0x100464997  mov     rdx, [rsi+78h]
0x10046499b  mov     [rsp+128h+var_108], rax
0x1004649a0  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x1004649a5  mov     rax, [rsi+98h]
0x1004649ac  lea     rcx, aRsi016lxRdi016; "Rsi=%016lx Rdi=%016lx Rip=%016lx Rsp=%0"...
0x1004649b3  mov     r9, [rsi+0F8h]
0x1004649ba  mov     r8, [rsi+0B0h]
0x1004649c1  mov     rdx, [rsi+0A8h]
0x1004649c8  mov     [rsp+128h+var_108], rax
0x1004649cd  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x1004649d2  mov     r8d, [rsi+44h]
0x1004649d6  lea     rcx, aRbp016lxEflags; "Rbp=%016lx EFlags=%016lx\n"
0x1004649dd  mov     rdx, [rsi+0A0h]
0x1004649e4  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x1004649e9  movzx   ecx, word ptr [rsi+3Eh]
0x1004649ed  movzx   eax, word ptr [rsi+40h]
0x1004649f1  movzx   r10d, word ptr [rsi+3Ch]
0x1004649f6  movzx   r9d, word ptr [rsi+3Ah]
0x1004649fb  movzx   r8d, word ptr [rsi+42h]
0x100464a00  movzx   edx, word ptr [rsi+38h]
0x100464a04  mov     [rsp+128h+var_F8], eax
0x100464a08  mov     [rsp+128h+var_100], ecx
0x100464a0c  lea     rcx, aCs016lxSs016lx; "cs=%016lx ss=%016lx ds=%016lx\nes=%016l"...
0x100464a13  mov     dword ptr [rsp+128h+var_108], r10d
0x100464a18  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x100464a1d  xor     ebx, ebx
0x100464a1f  mov     [r14], rbx
0x100464a22  mov     ebp, ebx
0x100464a24  call    cs:__imp_GetCurrentProcess
0x100464a2a  lea     rcx, aDbghelpDll; "dbghelp.dll"
0x100464a31  mov     r15, rax
0x100464a34  call    cs:__imp_GetModuleHandleW
0x100464a3a  mov     rdi, rax
0x100464a3d  test    rax, rax
0x100464a40  jnz     short loc_100464A5B
0x100464a42  lea     rcx, aDbghelpDll; "dbghelp.dll"
0x100464a49  call    cs:__imp_LoadLibraryW
0x100464a4f  mov     rdi, rax
0x100464a52  test    rax, rax
0x100464a55  jz      loc_100464BAD
0x100464a5b  lea     rdx, aSyminitializew; "SymInitializeW"
0x100464a62  mov     rcx, rdi; hModule
0x100464a65  call    cs:__imp_GetProcAddress
0x100464a6b  lea     rdx, aSymgetmoduleba; "SymGetModuleBase64"
0x100464a72  mov     rcx, rdi; hModule
0x100464a75  mov     [rsp+128h+var_D8], rax
0x100464a7a  call    cs:__imp_GetProcAddress
0x100464a80  lea     rdx, aSymrefreshmodu; "SymRefreshModuleList"
0x100464a87  mov     rcx, rdi; hModule
0x100464a8a  mov     r12, rax
0x100464a8d  call    cs:__imp_GetProcAddress
0x100464a93  lea     rdx, aSymcleanup; "SymCleanup"
0x100464a9a  mov     rcx, rdi; hModule
0x100464a9d  mov     r13, rax
0x100464aa0  call    cs:__imp_GetProcAddress
0x100464aa6  mov     rcx, rax
0x100464aa9  mov     [rsp+128h+var_D0], rax
0x100464aae  mov     rax, [rsp+128h+var_D8]
0x100464ab3  test    rax, rax
0x100464ab6  jz      loc_100464BAD
0x100464abc  test    r12, r12
0x100464abf  jz      loc_100464BAD
0x100464ac5  test    r13, r13
0x100464ac8  jz      loc_100464BAD
0x100464ace  test    rcx, rcx
0x100464ad1  jz      loc_100464BAD
0x100464ad7  xor     r8d, r8d
0x100464ada  xor     edx, edx
0x100464adc  mov     rcx, r15
0x100464adf  call    rax
0x100464ae1  test    eax, eax
0x100464ae3  mov     rcx, r15
0x100464ae6  setnz   [rsp+128h+var_E7]
0x100464aeb  call    r13
0x100464aee  test    eax, eax
0x100464af0  jz      short loc_100464B69
0x100464af2  xor     r9d, r9d; BackTraceHash
0x100464af5  lea     r8, [rsp+128h+BackTrace]; BackTrace
0x100464afa  xor     ecx, ecx; FramesToSkip
0x100464afc  lea     edx, [r9+10h]; FramesToCapture
0x100464b00  call    cs:__imp_RtlCaptureStackBackTrace
0x100464b06  movzx   eax, ax
0x100464b09  test    eax, eax
0x100464b0b  jz      short loc_100464B69
0x100464b0d  mov     dil, 1
0x100464b10  mov     ebp, eax
0x100464b12  mov     [rsp+128h+var_E8], dil
0x100464b17  mov     r13d, eax
0x100464b1a  mov     rsi, rbx
0x100464b1d  nop     dword ptr [rax]
0x100464b20  mov     rdi, [rsp+rsi*8+128h+BackTrace]
0x100464b25  mov     rcx, r15
0x100464b28  mov     rdx, rdi
0x100464b2b  call    r12
0x100464b2e  test    rax, rax
0x100464b31  jz      short loc_100464B64
0x100464b33  sub     rdi, rax
0x100464b36  inc     rsi
0x100464b39  mov     eax, [r14]
0x100464b3c  rol     eax, 1
0x100464b3e  xor     eax, edi
0x100464b40  shr     rdi, 20h
0x100464b44  mov     ecx, eax
0x100464b46  mov     edx, eax
0x100464b48  rol     ecx, 1
0x100464b4a  xor     rcx, rdi
0x100464b4d  add     rcx, rdx
0x100464b50  mov     [r14], rcx
0x100464b53  cmp     rsi, r13
0x100464b56  jl      short loc_100464B20
0x100464b58  mov     rsi, [rsp+128h+var_E0]
0x100464b5d  movzx   edi, [rsp+128h+var_E8]
0x100464b62  jmp     short loc_100464B6C
0x100464b64  mov     rsi, [rsp+128h+var_E0]
0x100464b69  xor     dil, dil
0x100464b6c  cmp     [rsp+128h+var_E7], bl
0x100464b70  jz      short loc_100464B79
0x100464b72  mov     rcx, r15
0x100464b75  call    [rsp+128h+var_D0]
0x100464b79  test    dil, dil
0x100464b7c  jz      short loc_100464BAD
0x100464b7e  test    ebp, ebp
0x100464b80  jz      loc_100464C1C
0x100464b86  lea     rdi, [rsp+128h+BackTrace]
0x100464b8b  nop     dword ptr [rax+rax+00h]
0x100464b90  mov     r8, [rdi]
0x100464b93  lea     rcx, aFrameD0xP; "Frame %d: 0x%p"
0x100464b9a  mov     edx, ebx
0x100464b9c  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x100464ba1  inc     ebx
0x100464ba3  lea     rdi, [rdi+8]
0x100464ba7  cmp     ebx, ebp
0x100464ba9  jb      short loc_100464B90
0x100464bab  jmp     short loc_100464C1C
0x100464bad  mov     [r14], rbx
0x100464bb0  mov     rdi, [rsi+0F8h]
0x100464bb7  mov     rsi, [rsi+0A0h]
0x100464bbe  xchg    ax, ax
0x100464bc0  inc     ebx
0x100464bc2  test    rdi, rdi
0x100464bc5  jz      short loc_100464C1C
0x100464bc7  mov     r9, rdi
0x100464bca  lea     rcx, aDFramePReturnA; "%d: Frame %p Return Address %p\n"
0x100464bd1  mov     r8, rsi
0x100464bd4  mov     edx, ebx
0x100464bd6  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x100464bdb  cmp     ebx, 10h
0x100464bde  jnb     short loc_100464BFA
0x100464be0  mov     eax, [r14]
0x100464be3  rol     eax, 1
0x100464be5  xor     eax, edi
0x100464be7  shr     rdi, 20h
0x100464beb  mov     ecx, eax
0x100464bed  mov     edx, eax
0x100464bef  rol     ecx, 1
0x100464bf1  xor     rcx, rdi
0x100464bf4  add     rcx, rdx
0x100464bf7  mov     [r14], rcx
0x100464bfa  mov     edx, 10h
0x100464bff  mov     rcx, rsi
0x100464c02  lea     r8d, [rdx-0Fh]
0x100464c06  call    cs:__imp_?GetVMAccess@SOS_OS@@SAHPEBX_KH@Z; SOS_OS::GetVMAccess(void const *,unsigned __int64,int)
0x100464c0c  test    eax, eax
0x100464c0e  jz      short loc_100464C1C
0x100464c10  mov     rdi, [rsi+8]
0x100464c14  mov     rsi, [rsi]
0x100464c17  cmp     ebx, 14h
0x100464c1a  jb      short loc_100464BC0
0x100464c1c  mov     eax, 1
0x100464c21  mov     rcx, [rsp+128h+var_48]
0x100464c29  xor     rcx, rsp; StackCookie
0x100464c2c  call    __security_check_cookie
0x100464c31  mov     rbx, [rsp+128h+arg_10]
0x100464c39  add     rsp, 0F0h
0x100464c40  pop     r15
0x100464c42  pop     r14
0x100464c44  pop     r13
0x100464c46  pop     r12
0x100464c48  pop     rdi
0x100464c49  pop     rsi
0x100464c4a  pop     rbp
0x100464c4b  retn
```
