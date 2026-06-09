# WPP_SF_Z

- ea: `0x14000bcfc`
- end: `0x14000bd6d`
- name: `WPP_SF_Z`
- size: `113`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b9e0`
- `0x14000baf0`
- `0x1400388d4`

## callees

- `0x14000bcfc`
- `0x14001ce30`

## pseudocode

```c
__int64 __fastcall WPP_SF_Z(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // r10
  const wchar_t *v5; // r11

  if ( a4 )
  {
    v4 = *a4;
    if ( *a4 )
    {
      v5 = (const wchar_t *)*((_QWORD *)a4 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 8;
  }
  v5 = L"NULL";
LABEL_6:
  if ( !a4 )
    a4 = L"\b";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           2,
           v5,
           v4,
           0);
}

```

## disassembly

```asm
0x14000bcfc  push    rbx
0x14000bcfe  sub     rsp, 50h
0x14000bd02  xor     ebx, ebx
0x14000bd04  test    r9, r9
0x14000bd07  jz      short loc_14000BD19
0x14000bd09  movzx   r10d, word ptr [r9]
0x14000bd0d  cmp     [r9], bx
0x14000bd11  jz      short loc_14000BD1F
0x14000bd13  mov     r11, [r9+8]
0x14000bd17  jmp     short loc_14000BD26
0x14000bd19  mov     r10d, 8
0x14000bd1f  lea     r11, aNull_0; "NULL"
0x14000bd26  mov     [rsp+58h+var_18], rbx
0x14000bd2b  lea     rax, asc_14001F4C0; "\b"
0x14000bd32  mov     [rsp+58h+var_20], r10
0x14000bd37  test    r9, r9
0x14000bd3a  mov     [rsp+58h+var_28], r11
0x14000bd3f  cmovz   r9, rax
0x14000bd43  mov     [rsp+58h+var_30], 2
0x14000bd4c  mov     rax, cs:pfnWppTraceMessage
0x14000bd53  mov     [rsp+58h+var_38], r9
0x14000bd58  movzx   r9d, dx
0x14000bd5c  mov     edx, 2Bh ; '+'
0x14000bd61  call    _guard_dispatch_icall
0x14000bd66  add     rsp, 50h
0x14000bd6a  pop     rbx
0x14000bd6b  retn
```
