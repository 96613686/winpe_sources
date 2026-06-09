# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180003a80`
- end: `0x180003ac4`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `68`
- prototype: `__int64(unsigned __int16 *, size_t, const unsigned __int16 *, ...)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180003414`
- `0x180003600`
- `0x1800075e4`
- `0x180009c50`
- `0x180009d50`
- `0x180009e50`
- `0x18000ec18`

## callees

- `0x180003a80`
- `0x180003acc`
- `0x180003b20`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, size_t a2, const unsigned __int16 *a3, ...)
{
  size_t v3; // rdx
  wchar_t *v4; // rcx
  size_t *v5; // r8
  HRESULT v6; // r9d
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  v6 = StringValidateDestW(a1, a2, (const size_t)a3);
  if ( v6 < 0 )
  {
    if ( v3 )
      *v4 = 0;
  }
  else
  {
    return (unsigned int)StringVPrintfWorkerW(v4, v3, v5, (STRSAFE_LPCWSTR)v5, va);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003a80  mov     [rsp+arg_10], r8
0x180003a85  mov     qword ptr [rsp+arg_18], r9
0x180003a8a  sub     rsp, 48h
0x180003a8e  call    StringValidateDestW
0x180003a93  mov     r9d, eax
0x180003a96  xor     eax, eax
0x180003a98  test    r9d, r9d
0x180003a9b  js      short loc_180003AB4
0x180003a9d  lea     rax, [rsp+48h+arg_18]
0x180003aa2  mov     r9, r8; pszFormat
0x180003aa5  mov     [rsp+48h+argList], rax; argList
0x180003aaa  call    StringVPrintfWorkerW
0x180003aaf  mov     r9d, eax
0x180003ab2  jmp     short loc_180003ABC
0x180003ab4  test    rdx, rdx
0x180003ab7  jz      short loc_180003ABC
0x180003ab9  mov     [rcx], ax
0x180003abc  mov     eax, r9d
0x180003abf  add     rsp, 48h
0x180003ac3  retn
```
