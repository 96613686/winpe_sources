# DAV_TRACE::TracePropertyMoveError(IHttpContext *,long,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000e320`
- end: `0x18000e3e2`
- name: `?TracePropertyMoveError@DAV_TRACE@@SAXPEAVIHttpContext@@JPEBG111@Z`
- size: `194`
- prototype: `void __fastcall(struct IHttpContext *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dfb4`
- `0x180010da0`

## callees

- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!SAFE_snwprintf` at `0x18000e38e`
- `iisutil!SAFE_snwprintf` at `0x18000e38e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000e36c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000e36c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e3c2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e3c2`

## string_xrefs

- `0x18000e382`: `SrcUri: %s, SrcPhys: %s, DestUri: %s, DestPhys: %s`

## pseudocode

```c
void __fastcall DAV_TRACE::TracePropertyMoveError(
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
    L"Error Moving Properties",
    a3,
    a2,
    v11);
  STRU::~STRU((STRU *)v12);
}

```

## disassembly

```asm
0x18000e320  push    rbx
0x18000e322  push    rbp
0x18000e323  push    rsi
0x18000e324  push    rdi
0x18000e325  push    r14
0x18000e327  push    r15
0x18000e329  sub     rsp, 78h
0x18000e32d  mov     rax, cs:__security_cookie
0x18000e334  xor     rax, rsp
0x18000e337  mov     [rsp+0A8h+var_40], rax
0x18000e33c  mov     rax, [rcx]
0x18000e33f  mov     rbp, r9
0x18000e342  mov     rdi, [rsp+0A8h+arg_20]
0x18000e34a  mov     r15, r8
0x18000e34d  mov     rbx, [rsp+0A8h+arg_28]
0x18000e355  mov     r14d, edx
0x18000e358  mov     rax, [rax+110h]
0x18000e35f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e364  lea     rcx, [rsp+0A8h+var_78]
0x18000e369  mov     rsi, rax
0x18000e36c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000e372  mov     r9, rbp
0x18000e375  mov     [rsp+0A8h+var_80], rbx
0x18000e37a  mov     r8, r15
0x18000e37d  mov     [rsp+0A8h+var_88], rdi
0x18000e382  lea     rdx, aSrcuriSSrcphys; "SrcUri: %s, SrcPhys: %s, DestUri: %s, D"...
0x18000e389  lea     rcx, [rsp+0A8h+var_78]
0x18000e38e  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x18000e394  mov     r9d, r14d
0x18000e397  mov     byte ptr [rsp+0A8h+var_88], 3
0x18000e39c  test    eax, eax
0x18000e39e  lea     rdx, aErrorMovingPro; "Error Moving Properties"
0x18000e3a5  mov     rax, [rsi]
0x18000e3a8  mov     rcx, rsi
0x18000e3ab  cmovns  r15, [rsp+0A8h+var_58]
0x18000e3b1  mov     r8, r15
0x18000e3b4  mov     rax, [rax+20h]
0x18000e3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3bd  lea     rcx, [rsp+0A8h+var_78]
0x18000e3c2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e3c8  mov     rcx, [rsp+0A8h+var_40]
0x18000e3cd  xor     rcx, rsp; StackCookie
0x18000e3d0  call    __security_check_cookie
0x18000e3d5  add     rsp, 78h
0x18000e3d9  pop     r15
0x18000e3db  pop     r14
0x18000e3dd  pop     rdi
0x18000e3de  pop     rsi
0x18000e3df  pop     rbp
0x18000e3e0  pop     rbx
0x18000e3e1  retn
```
