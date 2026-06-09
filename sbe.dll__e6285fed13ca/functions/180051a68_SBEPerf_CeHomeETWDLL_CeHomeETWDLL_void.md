# SBEPerf::CeHomeETWDLL::CeHomeETWDLL(void)

- ea: `0x180051a68`
- end: `0x180051bfe`
- name: `??0CeHomeETWDLL@SBEPerf@@QEAA@XZ`
- size: `406`
- prototype: `__int64 __fastcall(SBEPerf::CeHomeETWDLL *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180051c04`

## callees

- `0x180001c00`
- `0x180051a68`
- `0x1800558f0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180051aed`
- `KERNEL32!GetProcAddress` at `0x180051b01`
- `KERNEL32!GetProcAddress` at `0x180051b16`
- `KERNEL32!GetProcAddress` at `0x180051b2b`
- `KERNEL32!GetProcAddress` at `0x180051b40`
- `KERNEL32!GetProcAddress` at `0x180051b55`
- `KERNEL32!GetProcAddress` at `0x180051b6a`
- `KERNEL32!GetProcAddress` at `0x180051b7f`
- `KERNEL32!GetProcAddress` at `0x180051b94`
- `KERNEL32!GetProcAddress` at `0x180051aed`
- `KERNEL32!GetProcAddress` at `0x180051b01`
- `KERNEL32!GetProcAddress` at `0x180051b16`
- `KERNEL32!GetProcAddress` at `0x180051b2b`
- `KERNEL32!GetProcAddress` at `0x180051b40`
- `KERNEL32!GetProcAddress` at `0x180051b55`
- `KERNEL32!GetProcAddress` at `0x180051b6a`
- `KERNEL32!GetProcAddress` at `0x180051b7f`
- `KERNEL32!GetProcAddress` at `0x180051b94`
- `KERNEL32!LoadLibraryW` at `0x180051ad0`
- `KERNEL32!LoadLibraryW` at `0x180051ad0`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180051ac5`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180051ac5`

## string_xrefs

- `0x180051abe`: `%SystemRoot%\ehome\ehTrace.dll`

## pseudocode

```c
SBEPerf::CeHomeETWDLL *__fastcall SBEPerf::CeHomeETWDLL::CeHomeETWDLL(SBEPerf::CeHomeETWDLL *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  HMODULE v4; // rcx
  FARPROC v5; // rax
  HMODULE v6; // rcx
  FARPROC v7; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  HMODULE v12; // rcx
  FARPROC v13; // rax
  HMODULE v14; // rcx
  FARPROC v15; // rax
  HMODULE v16; // rcx
  FARPROC v17; // rax
  HMODULE v18; // rcx
  FARPROC v19; // rax
  WCHAR Dst[128]; // [rsp+20h] [rbp-118h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  ExpandEnvironmentStringsW(L"%SystemRoot%\\ehome\\ehTrace.dll", Dst, 0x80u);
  LibraryW = LoadLibraryW(Dst);
  *((_QWORD *)this + 9) = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "ehRegisterTraceGUIDs");
    v4 = (HMODULE)*((_QWORD *)this + 9);
    *(_QWORD *)this = ProcAddress;
    v5 = GetProcAddress(v4, "ehRegisterCounterGUID");
    v6 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 1) = v5;
    v7 = GetProcAddress(v6, "ehUnregisterTraceGUIDs");
    v8 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 2) = v7;
    v9 = GetProcAddress(v8, "ehUnregisterCounterGUIDs");
    v10 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 3) = v9;
    v11 = GetProcAddress(v10, "ehAllocateEventBuffer");
    v12 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 4) = v11;
    v13 = GetProcAddress(v12, "ehFreeEventBuffer");
    v14 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 5) = v13;
    v15 = GetProcAddress(v14, "ehIsTraceEnabled");
    v16 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 6) = v15;
    v17 = GetProcAddress(v16, "ehTraceCounter");
    v18 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 7) = v17;
    v19 = GetProcAddress(v18, "ehTraceEvent");
    *((_QWORD *)this + 8) = v19;
    if ( !*(_QWORD *)this
      || !*((_QWORD *)this + 1)
      || !*((_QWORD *)this + 2)
      || !*((_QWORD *)this + 3)
      || !*((_QWORD *)this + 4)
      || !*((_QWORD *)this + 5)
      || !*((_QWORD *)this + 6)
      || !*((_QWORD *)this + 7)
      || !v19 )
    {
      SBEPerf::CeHomeETWDLL::UnloadeHomeETWDll(this);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180051a68  mov     [rsp+arg_8], rbx
0x180051a6d  push    rdi
0x180051a6e  sub     rsp, 130h
0x180051a75  mov     rax, cs:__security_cookie
0x180051a7c  xor     rax, rsp
0x180051a7f  mov     [rsp+138h+var_18], rax
0x180051a87  xor     edi, edi
0x180051a89  lea     rdx, [rsp+138h+Dst]; lpDst
0x180051a8e  mov     [rcx], rdi
0x180051a91  mov     rbx, rcx
0x180051a94  mov     [rcx+8], rdi
0x180051a98  mov     r8d, 80h; nSize
0x180051a9e  mov     [rcx+10h], rdi
0x180051aa2  mov     [rcx+18h], rdi
0x180051aa6  mov     [rcx+20h], rdi
0x180051aaa  mov     [rcx+28h], rdi
0x180051aae  mov     [rcx+30h], rdi
0x180051ab2  mov     [rcx+38h], rdi
0x180051ab6  mov     [rcx+40h], rdi
0x180051aba  mov     [rcx+48h], rdi
0x180051abe  lea     rcx, Src; "%SystemRoot%\\ehome\\ehTrace.dll"
0x180051ac5  call    cs:__imp_ExpandEnvironmentStringsW
0x180051acb  lea     rcx, [rsp+138h+Dst]; lpLibFileName
0x180051ad0  call    cs:__imp_LoadLibraryW
0x180051ad6  mov     [rbx+48h], rax
0x180051ada  test    rax, rax
0x180051add  jz      loc_180051BDA
0x180051ae3  lea     rdx, aEhregistertrac; "ehRegisterTraceGUIDs"
0x180051aea  mov     rcx, rax; hModule
0x180051aed  call    cs:__imp_GetProcAddress
0x180051af3  mov     rcx, [rbx+48h]; hModule
0x180051af7  lea     rdx, aEhregistercoun; "ehRegisterCounterGUID"
0x180051afe  mov     [rbx], rax
0x180051b01  call    cs:__imp_GetProcAddress
0x180051b07  mov     rcx, [rbx+48h]; hModule
0x180051b0b  lea     rdx, aEhunregistertr; "ehUnregisterTraceGUIDs"
0x180051b12  mov     [rbx+8], rax
0x180051b16  call    cs:__imp_GetProcAddress
0x180051b1c  mov     rcx, [rbx+48h]; hModule
0x180051b20  lea     rdx, aEhunregisterco; "ehUnregisterCounterGUIDs"
0x180051b27  mov     [rbx+10h], rax
0x180051b2b  call    cs:__imp_GetProcAddress
0x180051b31  mov     rcx, [rbx+48h]; hModule
0x180051b35  lea     rdx, aEhallocateeven; "ehAllocateEventBuffer"
0x180051b3c  mov     [rbx+18h], rax
0x180051b40  call    cs:__imp_GetProcAddress
0x180051b46  mov     rcx, [rbx+48h]; hModule
0x180051b4a  lea     rdx, aEhfreeeventbuf; "ehFreeEventBuffer"
0x180051b51  mov     [rbx+20h], rax
0x180051b55  call    cs:__imp_GetProcAddress
0x180051b5b  mov     rcx, [rbx+48h]; hModule
0x180051b5f  lea     rdx, aEhistraceenabl; "ehIsTraceEnabled"
0x180051b66  mov     [rbx+28h], rax
0x180051b6a  call    cs:__imp_GetProcAddress
0x180051b70  mov     rcx, [rbx+48h]; hModule
0x180051b74  lea     rdx, aEhtracecounter; "ehTraceCounter"
0x180051b7b  mov     [rbx+30h], rax
0x180051b7f  call    cs:__imp_GetProcAddress
0x180051b85  mov     rcx, [rbx+48h]; hModule
0x180051b89  lea     rdx, aEhtraceevent; "ehTraceEvent"
0x180051b90  mov     [rbx+38h], rax
0x180051b94  call    cs:__imp_GetProcAddress
0x180051b9a  mov     [rbx+40h], rax
0x180051b9e  cmp     [rbx], rdi
0x180051ba1  jz      short loc_180051BD2
0x180051ba3  cmp     [rbx+8], rdi
0x180051ba7  jz      short loc_180051BD2
0x180051ba9  cmp     [rbx+10h], rdi
0x180051bad  jz      short loc_180051BD2
0x180051baf  cmp     [rbx+18h], rdi
0x180051bb3  jz      short loc_180051BD2
0x180051bb5  cmp     [rbx+20h], rdi
0x180051bb9  jz      short loc_180051BD2
0x180051bbb  cmp     [rbx+28h], rdi
0x180051bbf  jz      short loc_180051BD2
0x180051bc1  cmp     [rbx+30h], rdi
0x180051bc5  jz      short loc_180051BD2
0x180051bc7  cmp     [rbx+38h], rdi
0x180051bcb  jz      short loc_180051BD2
0x180051bcd  test    rax, rax
0x180051bd0  jnz     short loc_180051BDA
0x180051bd2  mov     rcx, rbx; this
0x180051bd5  call    ?UnloadeHomeETWDll@CeHomeETWDLL@SBEPerf@@AEAAXXZ; SBEPerf::CeHomeETWDLL::UnloadeHomeETWDll(void)
0x180051bda  mov     rax, rbx
0x180051bdd  mov     rcx, [rsp+138h+var_18]
0x180051be5  xor     rcx, rsp; StackCookie
0x180051be8  call    __security_check_cookie
0x180051bed  mov     rbx, [rsp+138h+arg_8]
0x180051bf5  add     rsp, 130h
0x180051bfc  pop     rdi
0x180051bfd  retn
```
