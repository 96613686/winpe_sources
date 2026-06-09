# RtlStringCbPrintfW

- ea: `0x14000db98`
- end: `0x14000dc12`
- name: `RtlStringCbPrintfW`
- size: `122`
- prototype: `NTSTATUS(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d9b4`
- `0x140025bd0`
- `0x14002610c`
- `0x14002c2cc`

## callees

- `0x14000db98`

## import_xrefs

- `ntoskrnl!_vsnwprintf` at `0x14000dbc8`
- `ntoskrnl!_vsnwprintf` at `0x14000dbc8`

## pseudocode

```c
NTSTATUS RtlStringCbPrintfW(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)
{
  size_t v4; // rdx
  unsigned __int64 v5; // rdi
  int v6; // eax
  NTSTATUS result; // eax
  bool v8; // zf
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  v4 = cbDest >> 1;
  if ( !v4 )
    return -1073741811;
  if ( v4 > 0x7FFFFFFF )
  {
    result = -1073741811;
    *pszDest = 0;
  }
  else
  {
    v5 = v4 - 1;
    v6 = _vsnwprintf(pszDest, v4 - 1, pszFormat, Args);
    if ( v6 < 0 || (v8 = v6 == v5, v6 > v5) )
    {
      pszDest[v5] = 0;
      return -2147483643;
    }
    else
    {
      result = 0;
      if ( v8 )
        pszDest[v5] = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000db98  mov     [rsp+arg_10], r8
0x14000db9d  mov     qword ptr [rsp+Args], r9
0x14000dba2  push    rbx
0x14000dba3  push    rsi
0x14000dba4  push    rdi
0x14000dba5  sub     rsp, 30h
0x14000dba9  xor     ebx, ebx
0x14000dbab  mov     rsi, rcx
0x14000dbae  shr     rdx, 1
0x14000dbb1  jz      short loc_14000DC03
0x14000dbb3  cmp     rdx, 7FFFFFFFh
0x14000dbba  ja      short loc_14000DBFC
0x14000dbbc  lea     rdi, [rdx-1]
0x14000dbc0  mov     rdx, rdi; Count
0x14000dbc3  lea     r9, [rsp+48h+Args]; Args
0x14000dbc8  call    cs:__imp__vsnwprintf
0x14000dbcf  nop     dword ptr [rax+rax+00h]
0x14000dbd4  test    eax, eax
0x14000dbd6  jns     short loc_14000DBEA
0x14000dbd8  mov     [rsi+rdi*2], bx
0x14000dbdc  mov     eax, 80000005h
0x14000dbe1  add     rsp, 30h
0x14000dbe5  pop     rdi
0x14000dbe6  pop     rsi
0x14000dbe7  pop     rbx
0x14000dbe8  retn
0x14000dbea  movsxd  rcx, eax
0x14000dbed  cmp     rcx, rdi
0x14000dbf0  ja      short loc_14000DBD8
0x14000dbf2  mov     eax, ebx
0x14000dbf4  jnz     short loc_14000DBE1
0x14000dbf6  mov     [rsi+rdi*2], bx
0x14000dbfa  jmp     short loc_14000DBE1
0x14000dbfc  mov     eax, 0C000000Dh
0x14000dc01  jmp     short loc_14000DC0D
0x14000dc03  mov     eax, 0C000000Dh
0x14000dc08  test    rdx, rdx
0x14000dc0b  jz      short loc_14000DBE1
0x14000dc0d  mov     [rcx], bx
0x14000dc10  jmp     short loc_14000DBE1
```
