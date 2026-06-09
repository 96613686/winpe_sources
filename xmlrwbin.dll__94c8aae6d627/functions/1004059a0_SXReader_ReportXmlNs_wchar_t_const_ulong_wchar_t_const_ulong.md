# SXReader::ReportXmlNs(wchar_t const *,ulong,wchar_t const *,ulong)

- ea: `0x1004059a0`
- end: `0x100405a26`
- name: `?ReportXmlNs@SXReader@@EEAAXPEB_WK0K@Z`
- size: `134`
- prototype: `void __fastcall(SXReader *__hidden this, const wchar_t *, unsigned int, const wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x100401350`
- `0x1004059a0`
- `0x100405f50`
- `0x100424580`

## pseudocode

```c
void __fastcall SXReader::ReportXmlNs(
        SXReader *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5)
{
  __int64 v9; // rcx
  int v10; // eax

  SXReader::AddNSDeclAtt(this, a2, a3, a4, a5);
  v9 = *((_QWORD *)this + 185);
  if ( v9 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, const wchar_t *, unsigned int))(*(_QWORD *)v9 + 48LL))(
            v9,
            a2,
            a3,
            a4,
            a5);
    if ( v10 < 0 )
    {
      _mm_lfence();
      MXRRaiseException(v10);
      JUMPOUT(0x100405A25LL);
    }
  }
}

```

## disassembly

```asm
0x1004059a0  mov     [rsp+arg_0], rbx
0x1004059a5  mov     [rsp+arg_8], rbp
0x1004059aa  mov     [rsp+arg_10], rsi
0x1004059af  mov     [rsp+arg_18], rdi
0x1004059b4  push    r14
0x1004059b6  sub     rsp, 30h
0x1004059ba  mov     r14d, [rsp+38h+arg_20]
0x1004059bf  mov     rdi, r9
0x1004059c2  mov     [rsp+38h+var_18], r14d; unsigned int
0x1004059c7  mov     esi, r8d
0x1004059ca  mov     rbp, rdx
0x1004059cd  mov     rbx, rcx
0x1004059d0  call    ?AddNSDeclAtt@SXReader@@AEAAXPEB_WK0K@Z; SXReader::AddNSDeclAtt(wchar_t const *,ulong,wchar_t const *,ulong)
0x1004059d5  mov     rcx, [rbx+5C8h]
0x1004059dc  test    rcx, rcx
0x1004059df  jz      short loc_100405A00
0x1004059e1  mov     rax, [rcx]
0x1004059e4  mov     r9, rdi
0x1004059e7  mov     r8d, esi
0x1004059ea  mov     [rsp+38h+var_18], r14d
0x1004059ef  mov     rdx, rbp
0x1004059f2  mov     rax, [rax+30h]
0x1004059f6  call    cs:__guard_dispatch_icall_fptr
0x1004059fc  test    eax, eax
0x1004059fe  js      short loc_100405A1B
0x100405a00  mov     rbx, [rsp+38h+arg_0]
0x100405a05  mov     rbp, [rsp+38h+arg_8]
0x100405a0a  mov     rsi, [rsp+38h+arg_10]
0x100405a0f  mov     rdi, [rsp+38h+arg_18]
0x100405a14  add     rsp, 30h
0x100405a18  pop     r14
0x100405a1a  retn
0x100405a1b  lfence
0x100405a1e  mov     ecx, eax; int
0x100405a20  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
