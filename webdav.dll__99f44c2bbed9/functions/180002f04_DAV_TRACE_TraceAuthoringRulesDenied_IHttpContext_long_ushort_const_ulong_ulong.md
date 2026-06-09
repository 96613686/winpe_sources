# DAV_TRACE::TraceAuthoringRulesDenied(IHttpContext *,long,ushort const *,ulong,ulong)

- ea: `0x180002f04`
- end: `0x180002fb5`
- name: `?TraceAuthoringRulesDenied@DAV_TRACE@@SAXPEAVIHttpContext@@JPEBGKK@Z`
- size: `177`
- prototype: `void __fastcall(struct IHttpContext *, int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002740`
- `0x180006c54`
- `0x18000da04`
- `0x18000e6e0`

## callees

- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!SAFE_snwprintf` at `0x180002f63`
- `iisutil!SAFE_snwprintf` at `0x180002f63`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002f3e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002f3e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002f97`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002f97`

## string_xrefs

- `0x180002f73`: `Access Denied By Authoring Rules`

## pseudocode

```c
void __fastcall DAV_TRACE::TraceAuthoringRulesDenied(
        struct IHttpContext *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v8; // rdi
  __int64 v9; // rbx
  int v10; // eax
  int v12; // [rsp+20h] [rbp-78h]
  _BYTE v13[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v14; // [rsp+50h] [rbp-48h]

  v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
  STRU::STRU((STRU *)v13);
  v9 = 0;
  v10 = SAFE_snwprintf((struct STRU *)v13, L"%s: Required %08lx, Granted %08lx", a3, a4, a5);
  LOBYTE(v12) = 3;
  if ( v10 >= 0 )
    v9 = v14;
  (*(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v8 + 32LL))(
    v8,
    L"Access Denied By Authoring Rules",
    v9,
    a2,
    v12);
  STRU::~STRU((STRU *)v13);
}

```

## disassembly

```asm
0x180002f04  push    rbx
0x180002f06  push    rbp
0x180002f07  push    rsi
0x180002f08  push    rdi
0x180002f09  push    r14
0x180002f0b  sub     rsp, 70h
0x180002f0f  mov     rax, cs:__security_cookie
0x180002f16  xor     rax, rsp
0x180002f19  mov     [rsp+98h+var_30], rax
0x180002f1e  mov     rax, [rcx]
0x180002f21  mov     ebp, r9d
0x180002f24  mov     rsi, r8
0x180002f27  mov     r14d, edx
0x180002f2a  mov     rax, [rax+110h]
0x180002f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f36  lea     rcx, [rsp+98h+var_68]
0x180002f3b  mov     rdi, rax
0x180002f3e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002f44  mov     ecx, [rsp+98h+arg_20]
0x180002f4b  lea     rdx, aSRequired08lxG; "%s: Required %08lx, Granted %08lx"
0x180002f52  mov     [rsp+98h+var_78], ecx
0x180002f56  mov     r9d, ebp
0x180002f59  lea     rcx, [rsp+98h+var_68]
0x180002f5e  mov     r8, rsi
0x180002f61  xor     ebx, ebx
0x180002f63  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180002f69  mov     r9d, r14d
0x180002f6c  mov     byte ptr [rsp+98h+var_78], 3
0x180002f71  test    eax, eax
0x180002f73  lea     rdx, aAccessDeniedBy; "Access Denied By Authoring Rules"
0x180002f7a  mov     rax, [rdi]
0x180002f7d  mov     rcx, rdi
0x180002f80  cmovns  rbx, [rsp+98h+var_48]
0x180002f86  mov     r8, rbx
0x180002f89  mov     rax, [rax+20h]
0x180002f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f92  lea     rcx, [rsp+98h+var_68]
0x180002f97  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002f9d  mov     rcx, [rsp+98h+var_30]
0x180002fa2  xor     rcx, rsp; StackCookie
0x180002fa5  call    __security_check_cookie
0x180002faa  add     rsp, 70h
0x180002fae  pop     r14
0x180002fb0  pop     rdi
0x180002fb1  pop     rsi
0x180002fb2  pop     rbp
0x180002fb3  pop     rbx
0x180002fb4  retn
```
