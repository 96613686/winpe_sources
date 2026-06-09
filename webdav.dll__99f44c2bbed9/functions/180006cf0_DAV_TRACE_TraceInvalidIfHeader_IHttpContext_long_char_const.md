# DAV_TRACE::TraceInvalidIfHeader(IHttpContext *,long,char const *)

- ea: `0x180006cf0`
- end: `0x180006d90`
- name: `?TraceInvalidIfHeader@DAV_TRACE@@SAXPEAVIHttpContext@@JPEBD@Z`
- size: `160`
- prototype: `void __fastcall(struct IHttpContext *, int, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c304`

## callees

- `0x180006cf0`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180006d26`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006d26`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006d72`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006d72`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180006d42`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180006d42`

## pseudocode

```c
void __fastcall DAV_TRACE::TraceInvalidIfHeader(struct IHttpContext *a1, unsigned int a2, const char *a3)
{
  __int64 v5; // rsi
  __int64 v6; // rbx
  void (__fastcall *v7)(__int64, const wchar_t *, __int64, _QWORD, char); // r14
  char v8; // [rsp+20h] [rbp-78h]
  _BYTE v9[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v10; // [rsp+50h] [rbp-48h]

  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
  STRU::STRU((STRU *)v9);
  v6 = 0;
  v7 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, char))(*(_QWORD *)v5 + 32LL);
  if ( a3 && (int)STRU::CopyA((STRU *)v9, a3) >= 0 )
    v6 = v10;
  v8 = 3;
  v7(v5, L"If: Header Invalid", v6, a2, v8);
  STRU::~STRU((STRU *)v9);
}

```

## disassembly

```asm
0x180006cf0  push    rbx
0x180006cf2  push    rbp
0x180006cf3  push    rsi
0x180006cf4  push    rdi
0x180006cf5  push    r14
0x180006cf7  sub     rsp, 70h
0x180006cfb  mov     rax, cs:__security_cookie
0x180006d02  xor     rax, rsp
0x180006d05  mov     [rsp+98h+var_30], rax
0x180006d0a  mov     rax, [rcx]
0x180006d0d  mov     rdi, r8
0x180006d10  mov     ebp, edx
0x180006d12  mov     rax, [rax+110h]
0x180006d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d1e  lea     rcx, [rsp+98h+var_68]
0x180006d23  mov     rsi, rax
0x180006d26  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006d2c  mov     rcx, [rsi]
0x180006d2f  xor     ebx, ebx
0x180006d31  mov     r14, [rcx+20h]
0x180006d35  test    rdi, rdi
0x180006d38  jz      short loc_180006D50
0x180006d3a  mov     rdx, rdi
0x180006d3d  lea     rcx, [rsp+98h+var_68]
0x180006d42  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180006d48  test    eax, eax
0x180006d4a  cmovns  rbx, [rsp+98h+var_48]
0x180006d50  mov     r9d, ebp
0x180006d53  mov     [rsp+98h+var_78], 3
0x180006d58  mov     r8, rbx
0x180006d5b  lea     rdx, aIfHeaderInvali; "If: Header Invalid"
0x180006d62  mov     rcx, rsi
0x180006d65  mov     rax, r14
0x180006d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d6d  lea     rcx, [rsp+98h+var_68]
0x180006d72  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006d78  mov     rcx, [rsp+98h+var_30]
0x180006d7d  xor     rcx, rsp; StackCookie
0x180006d80  call    __security_check_cookie
0x180006d85  add     rsp, 70h
0x180006d89  pop     r14
0x180006d8b  pop     rdi
0x180006d8c  pop     rsi
0x180006d8d  pop     rbp
0x180006d8e  pop     rbx
0x180006d8f  retn
```
