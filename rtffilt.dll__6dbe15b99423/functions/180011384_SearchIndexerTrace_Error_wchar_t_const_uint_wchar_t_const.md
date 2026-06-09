# SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)

- ea: `0x180011384`
- end: `0x180011419`
- name: `?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ`
- size: `149`
- prototype: `void(wchar_t *this, const wchar_t *, unsigned int, const wchar_t *, ...)`
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x180010780`
- `0x1800108a4`
- `0x180010b80`
- `0x18001153c`
- `0x180011994`
- `0x180013a1c`
- `0x180013b90`
- `0x180013f00`

## callees

- `0x180001e40`
- `0x1800041b8`
- `0x180011384`
- `0x180011420`
- `0x1800143b4`
- `0x1800169b8`

## pseudocode

```c
void SearchIndexerTrace::Error(wchar_t *this, const wchar_t *a2, __int64 a3, const wchar_t *a4, ...)
{
  unsigned int v4; // edi
  _DWORD *v6; // rax
  const wchar_t *v7; // r8
  wchar_t *v8[4]; // [rsp+28h] [rbp-40h] BYREF
  const wchar_t *v10; // [rsp+88h] [rbp+20h] BYREF

  v10 = a4;
  v4 = (unsigned int)a2;
  v6 = (_DWORD *)*((_QWORD *)SearchIndexerTraceProvider::Instance() + 1);
  if ( v6 && *v6 > 2u )
  {
    format_string::format_va(v8, a3, &v10);
    v7 = (const wchar_t *)v8;
    if ( v8[3] > (wchar_t *)7 )
      v7 = v8[0];
    SearchIndexerTraceProvider::Error(this, v4, v7);
    std::wstring::~wstring(v8);
  }
}

```

## disassembly

```asm
0x180011384  mov     [rsp+arg_10], r8
0x180011389  mov     [rsp+arg_18], r9
0x18001138e  push    rbx
0x18001138f  push    rdi
0x180011390  sub     rsp, 58h
0x180011394  mov     rax, cs:__security_cookie
0x18001139b  xor     rax, rsp
0x18001139e  mov     [rsp+68h+var_20], rax
0x1800113a3  mov     edi, edx
0x1800113a5  mov     rbx, rcx
0x1800113a8  call    ?Instance@SearchIndexerTraceProvider@@KAPEAU1@XZ; SearchIndexerTraceProvider::Instance(void)
0x1800113ad  mov     rax, [rax+8]
0x1800113b1  test    rax, rax
0x1800113b4  jz      short loc_180011405
0x1800113b6  mov     eax, [rax]
0x1800113b8  cmp     eax, 2
0x1800113bb  jbe     short loc_180011405
0x1800113bd  mov     rdx, [rsp+68h+arg_10]
0x1800113c5  lea     r8, [rsp+68h+arg_18]
0x1800113cd  lea     rcx, [rsp+68h+var_40]
0x1800113d2  mov     [rsp+68h+var_48], 0
0x1800113db  call    ?format_va@format_string@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WPEAD@Z; format_string::format_va(wchar_t const *,char *)
0x1800113e0  cmp     [rsp+68h+var_28], 7
0x1800113e6  lea     r8, [rsp+68h+var_40]
0x1800113eb  mov     edx, edi; unsigned int
0x1800113ed  mov     rcx, rbx; wchar_t *
0x1800113f0  cmova   r8, [rsp+68h+var_40]; wchar_t *
0x1800113f6  call    ?Error@SearchIndexerTraceProvider@@SAXPEB_WI0@Z; SearchIndexerTraceProvider::Error(wchar_t const *,uint,wchar_t const *)
0x1800113fb  lea     rcx, [rsp+68h+var_40]
0x180011400  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011405  mov     rcx, [rsp+68h+var_20]
0x18001140a  xor     rcx, rsp; StackCookie
0x18001140d  call    __security_check_cookie
0x180011412  add     rsp, 58h
0x180011416  pop     rdi
0x180011417  pop     rbx
0x180011418  retn
```
