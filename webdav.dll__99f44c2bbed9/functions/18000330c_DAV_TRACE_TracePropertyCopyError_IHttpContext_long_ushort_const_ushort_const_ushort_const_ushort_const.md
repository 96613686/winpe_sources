# DAV_TRACE::TracePropertyCopyError(IHttpContext *,long,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000330c`
- end: `0x1800033ce`
- name: `?TracePropertyCopyError@DAV_TRACE@@SAXPEAVIHttpContext@@JPEBG111@Z`
- size: `194`
- prototype: `void __fastcall(struct IHttpContext *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002fbc`
- `0x180010b70`

## callees

- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!SAFE_snwprintf` at `0x18000337a`
- `iisutil!SAFE_snwprintf` at `0x18000337a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003358`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003358`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800033ae`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800033ae`

## string_xrefs

- `0x18000336e`: `SrcUri: %s, SrcPhys: %s, DestUri: %s, DestPhys: %s`
- `0x18000338a`: `Error Copying Properties`

## pseudocode

```c
void __fastcall DAV_TRACE::TracePropertyCopyError(
        struct IHttpContext *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  __int64 v9; // rsi
  int v10; // eax
  int v11; // [rsp+20h] [rbp-88h]
  _BYTE v12[32]; // [rsp+30h] [rbp-78h] BYREF
  const unsigned __int16 *v13; // [rsp+50h] [rbp-58h]

  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
  STRU::STRU((STRU *)v12);
  v10 = SAFE_snwprintf((struct STRU *)v12, L"SrcUri: %s, SrcPhys: %s, DestUri: %s, DestPhys: %s", a3, a4, a5, a6);
  LOBYTE(v11) = 3;
  if ( v10 >= 0 )
    a3 = v13;
  (*(void (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, _QWORD, int))(*(_QWORD *)v9 + 32LL))(
    v9,
    L"Error Copying Properties",
    a3,
    a2,
    v11);
  STRU::~STRU((STRU *)v12);
}

```

## disassembly

```asm
0x18000330c  push    rbx
0x18000330e  push    rbp
0x18000330f  push    rsi
0x180003310  push    rdi
0x180003311  push    r14
0x180003313  push    r15
0x180003315  sub     rsp, 78h
0x180003319  mov     rax, cs:__security_cookie
0x180003320  xor     rax, rsp
0x180003323  mov     [rsp+0A8h+var_40], rax
0x180003328  mov     rax, [rcx]
0x18000332b  mov     rbp, r9
0x18000332e  mov     rdi, [rsp+0A8h+arg_20]
0x180003336  mov     r15, r8
0x180003339  mov     rbx, [rsp+0A8h+arg_28]
0x180003341  mov     r14d, edx
0x180003344  mov     rax, [rax+110h]
0x18000334b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003350  lea     rcx, [rsp+0A8h+var_78]
0x180003355  mov     rsi, rax
0x180003358  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000335e  mov     r9, rbp
0x180003361  mov     [rsp+0A8h+var_80], rbx
0x180003366  mov     r8, r15
0x180003369  mov     [rsp+0A8h+var_88], rdi
0x18000336e  lea     rdx, aSrcuriSSrcphys; "SrcUri: %s, SrcPhys: %s, DestUri: %s, D"...
0x180003375  lea     rcx, [rsp+0A8h+var_78]
0x18000337a  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180003380  mov     r9d, r14d
0x180003383  mov     byte ptr [rsp+0A8h+var_88], 3
0x180003388  test    eax, eax
0x18000338a  lea     rdx, aErrorCopyingPr; "Error Copying Properties"
0x180003391  mov     rax, [rsi]
0x180003394  mov     rcx, rsi
0x180003397  cmovns  r15, [rsp+0A8h+var_58]
0x18000339d  mov     r8, r15
0x1800033a0  mov     rax, [rax+20h]
0x1800033a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a9  lea     rcx, [rsp+0A8h+var_78]
0x1800033ae  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800033b4  mov     rcx, [rsp+0A8h+var_40]
0x1800033b9  xor     rcx, rsp; StackCookie
0x1800033bc  call    __security_check_cookie
0x1800033c1  add     rsp, 78h
0x1800033c5  pop     r15
0x1800033c7  pop     r14
0x1800033c9  pop     rdi
0x1800033ca  pop     rsi
0x1800033cb  pop     rbp
0x1800033cc  pop     rbx
0x1800033cd  retn
```
