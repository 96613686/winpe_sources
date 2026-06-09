# DAV_TRACE::TracePropertyDeleteError(IHttpContext *,long,ushort const *,ushort const *)

- ea: `0x180007bb0`
- end: `0x180007c4f`
- name: `?TracePropertyDeleteError@DAV_TRACE@@SAXPEAVIHttpContext@@JPEBG1@Z`
- size: `159`
- prototype: `void __fastcall(struct IHttpContext *, int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007870`
- `0x180010c50`

## callees

- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!SAFE_snwprintf` at `0x180007bff`
- `iisutil!SAFE_snwprintf` at `0x180007bff`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007be7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007be7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007c33`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007c33`

## string_xrefs

- `0x180007bf0`: `Uri: %s, Phys: %s`

## pseudocode

```c
void __fastcall DAV_TRACE::TracePropertyDeleteError(
        struct IHttpContext *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rdi
  char v8; // [rsp+20h] [rbp-78h]
  _BYTE v9[32]; // [rsp+30h] [rbp-68h] BYREF
  const unsigned __int16 *v10; // [rsp+50h] [rbp-48h]

  v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
  STRU::STRU((STRU *)v9);
  v8 = 3;
  if ( (int)SAFE_snwprintf((struct STRU *)v9, L"Uri: %s, Phys: %s", a3, a4) >= 0 )
    a3 = v10;
  (*(void (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, _QWORD, char))(*(_QWORD *)v7 + 32LL))(
    v7,
    L"Error Deleting Properties",
    a3,
    a2,
    v8);
  STRU::~STRU((STRU *)v9);
}

```

## disassembly

```asm
0x180007bb0  push    rbx
0x180007bb2  push    rbp
0x180007bb3  push    rsi
0x180007bb4  push    rdi
0x180007bb5  sub     rsp, 78h
0x180007bb9  mov     rax, cs:__security_cookie
0x180007bc0  xor     rax, rsp
0x180007bc3  mov     [rsp+98h+var_30], rax
0x180007bc8  mov     rax, [rcx]
0x180007bcb  mov     rbx, r9
0x180007bce  mov     rbp, r8
0x180007bd1  mov     esi, edx
0x180007bd3  mov     rax, [rax+110h]
0x180007bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bdf  lea     rcx, [rsp+98h+var_68]
0x180007be4  mov     rdi, rax
0x180007be7  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180007bed  mov     r9, rbx
0x180007bf0  lea     rdx, aUriSPhysS; "Uri: %s, Phys: %s"
0x180007bf7  mov     r8, rbp
0x180007bfa  lea     rcx, [rsp+98h+var_68]
0x180007bff  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180007c05  mov     rcx, [rdi]
0x180007c08  lea     rdx, aErrorDeletingP; "Error Deleting Properties"
0x180007c0f  test    eax, eax
0x180007c11  mov     [rsp+98h+var_78], 3
0x180007c16  mov     r9d, esi
0x180007c19  cmovns  rbp, [rsp+98h+var_48]
0x180007c1f  mov     rax, [rcx+20h]
0x180007c23  mov     r8, rbp
0x180007c26  mov     rcx, rdi
0x180007c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c2e  lea     rcx, [rsp+98h+var_68]
0x180007c33  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007c39  mov     rcx, [rsp+98h+var_30]
0x180007c3e  xor     rcx, rsp; StackCookie
0x180007c41  call    __security_check_cookie
0x180007c46  add     rsp, 78h
0x180007c4a  pop     rdi
0x180007c4b  pop     rsi
0x180007c4c  pop     rbp
0x180007c4d  pop     rbx
0x180007c4e  retn
```
