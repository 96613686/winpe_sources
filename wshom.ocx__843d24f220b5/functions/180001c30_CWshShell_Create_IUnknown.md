# CWshShell::Create(IUnknown *)

- ea: `0x180001c30`
- end: `0x180001db6`
- name: `?Create@CWshShell@@SAPEAUIUnknown@@PEAU2@@Z`
- size: `390`
- prototype: `struct IUnknown *__fastcall(struct IUnknownVtbl *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001c30`
- `0x1800060e4`
- `0x180010250`
- `0x180011010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180001d59`
- `msvcrt!_stricmp` at `0x180001d6d`
- `msvcrt!_stricmp` at `0x180001d59`
- `msvcrt!_stricmp` at `0x180001d6d`
- `KERNEL32!GetModuleFileNameA` at `0x180001ceb`
- `KERNEL32!GetModuleFileNameA` at `0x180001ceb`
- `KERNEL32!GetModuleHandleA` at `0x180001d79`
- `KERNEL32!GetModuleHandleA` at `0x180001d79`
- `KERNEL32!GetProcAddress` at `0x180001d8c`
- `KERNEL32!GetProcAddress` at `0x180001d8c`

## pseudocode

```c
struct IUnknown *__fastcall CWshShell::Create(struct IUnknownVtbl *a1)
{
  struct IUnknown *result; // rax
  struct IUnknown *v3; // rbx
  __int64 v4; // rax
  int v5; // eax
  const char *v6; // rdi
  HMODULE ModuleHandleA; // rax
  FARPROC ProcAddress; // rax
  _BYTE v9[16]; // [rsp+20h] [rbp-138h] BYREF
  CHAR Filename[260]; // [rsp+30h] [rbp-128h] BYREF
  char v11; // [rsp+134h] [rbp-24h]

  result = (struct IUnknown *)operator new(0x50u);
  v3 = result;
  if ( result )
  {
    result[2].lpVtbl = (struct IUnknownVtbl *)&CUnknown::`vftable';
    if ( !a1 )
      a1 = (struct IUnknownVtbl *)&result[5];
    LODWORD(result[6].lpVtbl) = 1;
    result[5].lpVtbl = (struct IUnknownVtbl *)&CUnknown::InnerUnknown::`vftable';
    result[3].lpVtbl = a1;
    result[4].lpVtbl = (struct IUnknownVtbl *)result;
    _InterlockedIncrement(&Global::g_cObjects);
    LOBYTE(result[8].lpVtbl) = 0;
    result[7].lpVtbl = (struct IUnknownVtbl *)&TaUser_DescCWshShell;
    v9[0] = 0;
    result->lpVtbl = (struct IUnknownVtbl *)&CWshShell::`vftable'{for `IWshShell3'};
    LOBYTE(result[9].lpVtbl) = 0;
    result[1].lpVtbl = (struct IUnknownVtbl *)&CWshEnvProcess::`vftable'{for `IProvideClassInfo'};
    v11 = 0;
    result[2].lpVtbl = (struct IUnknownVtbl *)&CWshShell::`vftable'{for `CAutoObj'};
    if ( GetModuleFileNameA(0, Filename, 0x105u) )
    {
      if ( !v11 )
      {
        v4 = -1;
        do
          ++v4;
        while ( Filename[v4] );
        v5 = v4 - 12;
        if ( v5 >= 0 )
        {
          v6 = &Filename[v5];
          if ( !_stricmp(v6, "\\wscript.exe") || !_stricmp(v6, "\\cscript.exe") )
          {
            ModuleHandleA = GetModuleHandleA(0);
            if ( ModuleHandleA )
            {
              ProcAddress = GetProcAddress(ModuleHandleA, (LPCSTR)1);
              if ( ProcAddress )
              {
                if ( ((int (__fastcall *)(_BYTE *))ProcAddress)(v9) >= 0 )
                  LOBYTE(v3[9].lpVtbl) = v9[0];
              }
            }
          }
        }
      }
    }
    return v3 + 5;
  }
  return result;
}

```

## disassembly

```asm
0x180001c30  mov     [rsp+arg_0], rbx
0x180001c35  push    rdi
0x180001c36  sub     rsp, 150h
0x180001c3d  mov     rax, cs:__security_cookie
0x180001c44  xor     rax, rsp
0x180001c47  mov     [rsp+158h+var_18], rax
0x180001c4f  mov     rdi, rcx
0x180001c52  mov     ecx, 50h ; 'P'; Size
0x180001c57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c5c  mov     rbx, rax
0x180001c5f  test    rax, rax
0x180001c62  jz      loc_180001D22
0x180001c68  lea     rdx, [rbx+28h]
0x180001c6c  test    rdi, rdi
0x180001c6f  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x180001c76  mov     [rbx+10h], rax
0x180001c7a  cmovz   rdi, rdx
0x180001c7e  mov     dword ptr [rdx+8], 1
0x180001c85  lea     rax, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x180001c8c  mov     [rdx], rax
0x180001c8f  mov     [rbx+18h], rdi
0x180001c93  mov     [rbx+20h], rbx
0x180001c97  lock inc cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x180001c9e  mov     byte ptr [rbx+40h], 0
0x180001ca2  lea     rax, ?TaUser_DescCWshShell@@3UTaDescDispatch@@A; TaDescDispatch TaUser_DescCWshShell
0x180001ca9  mov     [rbx+38h], rax
0x180001cad  lea     rdx, [rsp+158h+Filename]; lpFilename
0x180001cb2  lea     rax, ??_7CWshShell@@6BIWshShell3@@@; const CWshShell::`vftable'{for `IWshShell3'}
0x180001cb9  mov     [rsp+158h+var_138], 0
0x180001cbe  mov     [rbx], rax
0x180001cc1  mov     r8d, 105h; nSize
0x180001cc7  lea     rax, ??_7CWshEnvProcess@@6BIProvideClassInfo@@@; const CWshEnvProcess::`vftable'{for `IProvideClassInfo'}
0x180001cce  mov     byte ptr [rbx+48h], 0
0x180001cd2  mov     [rbx+8], rax
0x180001cd6  xor     ecx, ecx; hModule
0x180001cd8  lea     rax, ??_7CWshShell@@6BCAutoObj@@@; const CWshShell::`vftable'{for `CAutoObj'}
0x180001cdf  mov     [rsp+158h+var_24], 0
0x180001ce7  mov     [rbx+10h], rax
0x180001ceb  call    cs:__imp_GetModuleFileNameA
0x180001cf1  test    eax, eax
0x180001cf3  jz      short loc_180001D1E
0x180001cf5  cmp     [rsp+158h+var_24], 0
0x180001cfd  jnz     short loc_180001D1E
0x180001cff  lea     rcx, [rsp+158h+Filename]
0x180001d04  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001d0b  nop     dword ptr [rax+rax+00h]
0x180001d10  inc     rax
0x180001d13  cmp     byte ptr [rcx+rax], 0
0x180001d17  jnz     short loc_180001D10
0x180001d19  add     eax, 0FFFFFFF4h
0x180001d1c  jns     short loc_180001D45
0x180001d1e  lea     rax, [rbx+28h]
0x180001d22  mov     rcx, [rsp+158h+var_18]
0x180001d2a  xor     rcx, rsp; StackCookie
0x180001d2d  call    __security_check_cookie
0x180001d32  mov     rbx, [rsp+158h+arg_0]
0x180001d3a  add     rsp, 150h
0x180001d41  pop     rdi
0x180001d42  retn
0x180001d43  jmp     short loc_180001D22
0x180001d45  cdqe
0x180001d47  lea     rdi, [rsp+158h+Filename]
0x180001d4c  add     rdi, rax
0x180001d4f  lea     rdx, aWscriptExe; "\\wscript.exe"
0x180001d56  mov     rcx, rdi; String1
0x180001d59  call    cs:__imp__stricmp
0x180001d5f  test    eax, eax
0x180001d61  jz      short loc_180001D77
0x180001d63  lea     rdx, aCscriptExe; "\\cscript.exe"
0x180001d6a  mov     rcx, rdi; String1
0x180001d6d  call    cs:__imp__stricmp
0x180001d73  test    eax, eax
0x180001d75  jnz     short loc_180001D1E
0x180001d77  xor     ecx, ecx; lpModuleName
0x180001d79  call    cs:__imp_GetModuleHandleA
0x180001d7f  test    rax, rax
0x180001d82  jz      short loc_180001D1E
0x180001d84  mov     edx, 1; lpProcName
0x180001d89  mov     rcx, rax; hModule
0x180001d8c  call    cs:__imp_GetProcAddress
0x180001d92  test    rax, rax
0x180001d95  jz      short loc_180001D1E
0x180001d97  lea     rcx, [rsp+158h+var_138]
0x180001d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001da1  test    eax, eax
0x180001da3  js      loc_180001D1E
0x180001da9  movzx   eax, [rsp+158h+var_138]
0x180001dae  mov     [rbx+48h], al
0x180001db1  jmp     loc_180001D1E
```
