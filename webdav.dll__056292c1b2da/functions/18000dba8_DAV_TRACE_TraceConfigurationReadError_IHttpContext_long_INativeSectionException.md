# DAV_TRACE::TraceConfigurationReadError(IHttpContext *,long,INativeSectionException *)

- ea: `0x18000dba8`
- end: `0x18000dcb0`
- name: `?TraceConfigurationReadError@DAV_TRACE@@SAXPEAVIHttpContext@@JPEAVINativeSectionException@@@Z`
- size: `264`
- prototype: `void __fastcall(struct IHttpContext *, int, struct INativeSectionException *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000d718`
- `0x180010098`

## callees

- `0x18000dba8`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!SAFE_snwprintf` at `0x18000dc5e`
- `iisutil!SAFE_snwprintf` at `0x18000dc5e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000dbe5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000dbe5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000dc90`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000dc90`

## string_xrefs

- `0x18000dc6e`: `Error Reading Configuration`

## pseudocode

```c
void __fastcall DAV_TRACE::TraceConfigurationReadError(
        struct IHttpContext *a1,
        unsigned int a2,
        struct INativeSectionException *a3)
{
  __int64 v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // rcx
  int v8; // [rsp+20h] [rbp-39h]
  unsigned int v9; // [rsp+30h] [rbp-29h] BYREF
  __int64 v10; // [rsp+38h] [rbp-21h] BYREF
  __int64 v11; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v12[32]; // [rsp+48h] [rbp-11h] BYREF
  __int64 v13; // [rsp+68h] [rbp+Fh]

  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
  STRU::STRU((STRU *)v12);
  v6 = 0;
  if ( a3 )
  {
    v7 = *(_QWORD *)a3;
    v11 = 0;
    v10 = 0;
    v9 = 0;
    if ( (*(int (__fastcall **)(struct INativeSectionException *, __int64 *))(v7 + 40))(a3, &v11) >= 0
      && (*(int (__fastcall **)(struct INativeSectionException *, unsigned int *))(*(_QWORD *)a3 + 32LL))(a3, &v9) >= 0
      && (*(int (__fastcall **)(struct INativeSectionException *, __int64 *))(*(_QWORD *)a3 + 24LL))(a3, &v10) >= 0
      && (int)SAFE_snwprintf((struct STRU *)v12, L"File %s, Line %lu: %s", v11, v9, v10) >= 0 )
    {
      v6 = v13;
    }
  }
  LOBYTE(v8) = 3;
  (*(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v5 + 32LL))(
    v5,
    L"Error Reading Configuration",
    v6,
    a2,
    v8);
  STRU::~STRU((STRU *)v12);
}

```

## disassembly

```asm
0x18000dba8  push    rbp
0x18000dbaa  push    rbx
0x18000dbab  push    rsi
0x18000dbac  push    rdi
0x18000dbad  push    r14
0x18000dbaf  lea     rbp, [rsp-37h]
0x18000dbb4  sub     rsp, 90h
0x18000dbbb  mov     rax, cs:__security_cookie
0x18000dbc2  xor     rax, rsp
0x18000dbc5  mov     [rbp+57h+var_30], rax
0x18000dbc9  mov     rax, [rcx]
0x18000dbcc  mov     rbx, r8
0x18000dbcf  mov     r14d, edx
0x18000dbd2  mov     rax, [rax+110h]
0x18000dbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbde  lea     rcx, [rbp+57h+var_68]
0x18000dbe2  mov     rsi, rax
0x18000dbe5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000dbeb  xor     edi, edi
0x18000dbed  test    rbx, rbx
0x18000dbf0  jz      short loc_18000DC6B
0x18000dbf2  mov     rcx, [rbx]
0x18000dbf5  lea     rdx, [rbp+57h+var_70]
0x18000dbf9  mov     [rbp+57h+var_70], rdi
0x18000dbfd  mov     [rbp+57h+var_78], rdi
0x18000dc01  mov     [rbp+57h+var_80], edi
0x18000dc04  mov     rax, [rcx+28h]
0x18000dc08  mov     rcx, rbx
0x18000dc0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc10  test    eax, eax
0x18000dc12  js      short loc_18000DC6B
0x18000dc14  mov     rax, [rbx]
0x18000dc17  lea     rdx, [rbp+57h+var_80]
0x18000dc1b  mov     rcx, rbx
0x18000dc1e  mov     rax, [rax+20h]
0x18000dc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc27  test    eax, eax
0x18000dc29  js      short loc_18000DC6B
0x18000dc2b  mov     rax, [rbx]
0x18000dc2e  lea     rdx, [rbp+57h+var_78]
0x18000dc32  mov     rcx, rbx
0x18000dc35  mov     rax, [rax+18h]
0x18000dc39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc3e  test    eax, eax
0x18000dc40  js      short loc_18000DC6B
0x18000dc42  mov     rax, [rbp+57h+var_78]
0x18000dc46  lea     rdx, aFileSLineLuS; "File %s, Line %lu: %s"
0x18000dc4d  mov     r9d, [rbp+57h+var_80]
0x18000dc51  lea     rcx, [rbp+57h+var_68]
0x18000dc55  mov     r8, [rbp+57h+var_70]
0x18000dc59  mov     qword ptr [rsp+0B0h+var_90], rax
0x18000dc5e  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x18000dc64  test    eax, eax
0x18000dc66  cmovns  rdi, [rbp+57h+var_48]
0x18000dc6b  mov     rax, [rsi]
0x18000dc6e  lea     rdx, aErrorReadingCo; "Error Reading Configuration"
0x18000dc75  mov     r9d, r14d
0x18000dc78  mov     byte ptr [rsp+0B0h+var_90], 3
0x18000dc7d  mov     r8, rdi
0x18000dc80  mov     rcx, rsi
0x18000dc83  mov     rax, [rax+20h]
0x18000dc87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc8c  lea     rcx, [rbp+57h+var_68]
0x18000dc90  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000dc96  mov     rcx, [rbp+57h+var_30]
0x18000dc9a  xor     rcx, rsp; StackCookie
0x18000dc9d  call    __security_check_cookie
0x18000dca2  add     rsp, 90h
0x18000dca9  pop     r14
0x18000dcab  pop     rdi
0x18000dcac  pop     rsi
0x18000dcad  pop     rbx
0x18000dcae  pop     rbp
0x18000dcaf  retn
```
