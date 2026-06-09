# DAV_TRACE::TraceValidationError(IHttpContext *,long,INativeSectionException *)

- ea: `0x180011e14`
- end: `0x180011f1c`
- name: `?TraceValidationError@DAV_TRACE@@SAXPEAVIHttpContext@@JPEAVINativeSectionException@@@Z`
- size: `264`
- prototype: `void __fastcall(struct IHttpContext *, int, struct INativeSectionException *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011f30`

## callees

- `0x180011e14`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!SAFE_snwprintf` at `0x180011eca`
- `iisutil!SAFE_snwprintf` at `0x180011eca`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011e51`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011e51`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011efc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011efc`

## string_xrefs

- `0x180011eda`: `Error validating web.config`

## pseudocode

```c
void __fastcall DAV_TRACE::TraceValidationError(
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
    L"Error validating web.config",
    v6,
    a2,
    v8);
  STRU::~STRU((STRU *)v12);
}

```

## disassembly

```asm
0x180011e14  push    rbp
0x180011e16  push    rbx
0x180011e17  push    rsi
0x180011e18  push    rdi
0x180011e19  push    r14
0x180011e1b  lea     rbp, [rsp-37h]
0x180011e20  sub     rsp, 90h
0x180011e27  mov     rax, cs:__security_cookie
0x180011e2e  xor     rax, rsp
0x180011e31  mov     [rbp+57h+var_30], rax
0x180011e35  mov     rax, [rcx]
0x180011e38  mov     rbx, r8
0x180011e3b  mov     r14d, edx
0x180011e3e  mov     rax, [rax+110h]
0x180011e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e4a  lea     rcx, [rbp+57h+var_68]
0x180011e4e  mov     rsi, rax
0x180011e51  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180011e57  xor     edi, edi
0x180011e59  test    rbx, rbx
0x180011e5c  jz      short loc_180011ED7
0x180011e5e  mov     rcx, [rbx]
0x180011e61  lea     rdx, [rbp+57h+var_70]
0x180011e65  mov     [rbp+57h+var_70], rdi
0x180011e69  mov     [rbp+57h+var_78], rdi
0x180011e6d  mov     [rbp+57h+var_80], edi
0x180011e70  mov     rax, [rcx+28h]
0x180011e74  mov     rcx, rbx
0x180011e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e7c  test    eax, eax
0x180011e7e  js      short loc_180011ED7
0x180011e80  mov     rax, [rbx]
0x180011e83  lea     rdx, [rbp+57h+var_80]
0x180011e87  mov     rcx, rbx
0x180011e8a  mov     rax, [rax+20h]
0x180011e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e93  test    eax, eax
0x180011e95  js      short loc_180011ED7
0x180011e97  mov     rax, [rbx]
0x180011e9a  lea     rdx, [rbp+57h+var_78]
0x180011e9e  mov     rcx, rbx
0x180011ea1  mov     rax, [rax+18h]
0x180011ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eaa  test    eax, eax
0x180011eac  js      short loc_180011ED7
0x180011eae  mov     rax, [rbp+57h+var_78]
0x180011eb2  lea     rdx, aFileSLineLuS; "File %s, Line %lu: %s"
0x180011eb9  mov     r9d, [rbp+57h+var_80]
0x180011ebd  lea     rcx, [rbp+57h+var_68]
0x180011ec1  mov     r8, [rbp+57h+var_70]
0x180011ec5  mov     qword ptr [rsp+0B0h+var_90], rax
0x180011eca  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180011ed0  test    eax, eax
0x180011ed2  cmovns  rdi, [rbp+57h+var_48]
0x180011ed7  mov     rax, [rsi]
0x180011eda  lea     rdx, aErrorValidatin; "Error validating web.config"
0x180011ee1  mov     r9d, r14d
0x180011ee4  mov     byte ptr [rsp+0B0h+var_90], 3
0x180011ee9  mov     r8, rdi
0x180011eec  mov     rcx, rsi
0x180011eef  mov     rax, [rax+20h]
0x180011ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ef8  lea     rcx, [rbp+57h+var_68]
0x180011efc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180011f02  mov     rcx, [rbp+57h+var_30]
0x180011f06  xor     rcx, rsp; StackCookie
0x180011f09  call    __security_check_cookie
0x180011f0e  add     rsp, 90h
0x180011f15  pop     r14
0x180011f17  pop     rdi
0x180011f18  pop     rsi
0x180011f19  pop     rbx
0x180011f1a  pop     rbp
0x180011f1b  retn
```
