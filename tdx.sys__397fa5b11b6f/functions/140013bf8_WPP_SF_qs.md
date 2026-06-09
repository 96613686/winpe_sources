# WPP_SF_qs

- ea: `0x140013bf8`
- end: `0x140013c7c`
- name: `WPP_SF_qs`
- size: `132`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x1400023b0`
- `0x140002ccc`
- `0x1400039c0`
- `0x1400043b0`
- `0x140004df4`
- `0x140005fe0`
- `0x1400087a0`
- `0x14000aad0`
- `0x14000cfc0`
- `0x14000f8d0`
- `0x14000fc90`

## callees

- `0x140013bf8`
- `0x140018590`

## pseudocode

```c
__int64 WPP_SF_qs(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  const char *v3; // r9
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v8; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  const char *v10; // [rsp+80h] [rbp+28h]
  va_list va1; // [rsp+88h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v8 = va_arg(va1, _QWORD);
  v10 = va_arg(va1, const char *);
  v3 = v10;
  if ( v10 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v10[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  if ( !v10 )
    v3 = "NULL";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, const char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           v3,
           v6,
           0);
}

```

## disassembly

```asm
0x140013bf8  mov     [rsp+arg_18], r9
0x140013bfd  sub     rsp, 58h
0x140013c01  mov     r9, [rsp+58h+arg_20]
0x140013c09  mov     r10, rcx
0x140013c0c  test    r9, r9
0x140013c0f  jz      short loc_140013C25
0x140013c11  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013c15  inc     rax
0x140013c18  cmp     byte ptr [r9+rax], 0
0x140013c1d  jnz     short loc_140013C15
0x140013c1f  lea     rcx, [rax+1]
0x140013c23  jmp     short loc_140013C2A
0x140013c25  mov     ecx, 5
0x140013c2a  mov     [rsp+58h+var_18], 0
0x140013c33  lea     rax, aNull; "NULL"
0x140013c3a  mov     [rsp+58h+var_20], rcx
0x140013c3f  test    r9, r9
0x140013c42  lea     rcx, [rsp+58h+arg_18]
0x140013c47  cmovz   r9, rax
0x140013c4b  mov     rax, cs:pfnWppTraceMessage
0x140013c52  mov     [rsp+58h+var_28], r9
0x140013c57  movzx   r9d, dx
0x140013c5b  mov     edx, 2Bh ; '+'
0x140013c60  mov     [rsp+58h+var_30], 8
0x140013c69  mov     [rsp+58h+var_38], rcx
0x140013c6e  mov     rcx, r10
0x140013c71  call    _guard_dispatch_icall
0x140013c76  add     rsp, 58h
0x140013c7a  retn
```
