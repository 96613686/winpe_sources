# SXReader::ReportEndXmlNs(wchar_t const *,ulong,wchar_t const *,ulong)

- ea: `0x100405a30`
- end: `0x100405a61`
- name: `?ReportEndXmlNs@SXReader@@EEAAXPEB_WK0K@Z`
- size: `49`
- prototype: `void __fastcall(SXReader *__hidden this, const wchar_t *, unsigned int, const wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x100401350`
- `0x100405a30`
- `0x100424580`

## pseudocode

```c
void __fastcall SXReader::ReportEndXmlNs(SXReader *this, const wchar_t *a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rcx
  int v5; // eax

  v4 = *((_QWORD *)this + 185);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, const wchar_t *))(*(_QWORD *)v4 + 56LL))(
           v4,
           a2,
           a3,
           a4);
    if ( v5 < 0 )
    {
      _mm_lfence();
      MXRRaiseException(v5);
      JUMPOUT(0x100405A60LL);
    }
  }
}

```

## disassembly

```asm
0x100405a30  sub     rsp, 28h
0x100405a34  mov     rcx, [rcx+5C8h]
0x100405a3b  test    rcx, rcx
0x100405a3e  jz      short loc_100405A51
0x100405a40  mov     rax, [rcx]
0x100405a43  mov     rax, [rax+38h]
0x100405a47  call    cs:__guard_dispatch_icall_fptr
0x100405a4d  test    eax, eax
0x100405a4f  js      short loc_100405A56
0x100405a51  add     rsp, 28h
0x100405a55  retn
0x100405a56  lfence
0x100405a59  mov     ecx, eax; int
0x100405a5b  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
