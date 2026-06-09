# WPP_SF_sqZ_guid_DD

- ea: `0x140008880`
- end: `0x1400089b0`
- name: `WPP_SF_sqZ_guid_DD`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140014420`
- `0x1400147e0`

## callees

- `0x140008880`
- `0x140008d60`

## pseudocode

```c
__int64 WPP_SF_sqZ_guid_DD(__int64 a1, __int64 a2, __int64 a3, const char *a4, ...)
{
  const wchar_t *v4; // rdx
  __int64 v5; // r8
  const wchar_t *v6; // r11
  __int64 v7; // rax
  __int64 v8; // r10
  __int64 v10; // [rsp+D0h] [rbp+28h] BYREF
  va_list va; // [rsp+D0h] [rbp+28h]
  unsigned __int16 *v12; // [rsp+D8h] [rbp+30h]
  __int64 v13; // [rsp+E0h] [rbp+38h]
  __int64 v14; // [rsp+E8h] [rbp+40h] BYREF
  va_list va1; // [rsp+E8h] [rbp+40h]
  va_list va2; // [rsp+F0h] [rbp+48h] BYREF

  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v10 = va_arg(va1, _QWORD);
  v12 = va_arg(va1, unsigned __int16 *);
  v13 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v14 = va_arg(va2, _QWORD);
  v4 = v12;
  if ( v12 )
  {
    v5 = *v12;
    if ( *v12 )
    {
      v6 = (const wchar_t *)*((_QWORD *)v12 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v5 = 8;
  }
  v6 = L"NULL";
LABEL_6:
  if ( !v12 )
    v4 = L"\b";
  if ( a4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a4[v7] );
    v8 = v7 + 1;
  }
  else
  {
    v8 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64, const char *, __int64, __int64 *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, __int64, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_c5bfb05de4fc3e0c8e6f97300ddf0622_Traceguids,
           11,
           a4,
           v8,
           (__int64 *)va,
           8,
           v4,
           2,
           v6,
           v5,
           v13,
           16,
           (__int64 *)va1,
           4,
           va2,
           4,
           0);
}

```

## disassembly

```asm
0x140008880  mov     [rsp+arg_0], rbx
0x140008885  push    rsi
0x140008886  sub     rsp, 0A0h
0x14000888d  mov     rdx, [rsp+0A8h+arg_28]
0x140008895  mov     rbx, rcx
0x140008898  xor     ecx, ecx
0x14000889a  test    rdx, rdx
0x14000889d  jz      short loc_1400088AE
0x14000889f  movzx   r8d, word ptr [rdx]
0x1400088a3  cmp     [rdx], cx
0x1400088a6  jz      short loc_1400088B4
0x1400088a8  mov     r11, [rdx+8]
0x1400088ac  jmp     short loc_1400088BB
0x1400088ae  mov     r8d, 8
0x1400088b4  lea     r11, aNull_0; "NULL"
0x1400088bb  test    rdx, rdx
0x1400088be  lea     rax, asc_14000B8C4; "\b"
0x1400088c5  cmovz   rdx, rax
0x1400088c9  test    r9, r9
0x1400088cc  jz      short loc_1400088E1
0x1400088ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400088d2  inc     rax
0x1400088d5  cmp     [r9+rax], cl
0x1400088d9  jnz     short loc_1400088D2
0x1400088db  lea     r10, [rax+1]
0x1400088df  jmp     short loc_1400088E7
0x1400088e1  mov     r10d, 5
0x1400088e7  mov     [rsp+0A8h+var_18], rcx
0x1400088ef  lea     rax, aNull; "NULL"
0x1400088f6  mov     [rsp+0A8h+var_20], 4
0x140008902  lea     rcx, [rsp+0A8h+arg_40]
0x14000890a  mov     [rsp+0A8h+var_28], rcx
0x140008912  test    r9, r9
0x140008915  mov     [rsp+0A8h+var_30], 4
0x14000891e  lea     rcx, [rsp+0A8h+arg_38]
0x140008926  mov     [rsp+0A8h+var_38], rcx
0x14000892b  cmovz   r9, rax
0x14000892f  mov     rcx, [rsp+0A8h+arg_30]
0x140008937  mov     esi, 0Bh
0x14000893c  mov     rax, cs:pfnWppTraceMessage
0x140008943  mov     [rsp+0A8h+var_40], 10h
0x14000894c  mov     [rsp+0A8h+var_48], rcx
0x140008951  lea     rcx, [rsp+0A8h+arg_20]
0x140008959  mov     [rsp+0A8h+var_50], r8
0x14000895e  lea     r8, WPP_c5bfb05de4fc3e0c8e6f97300ddf0622_Traceguids
0x140008965  mov     [rsp+0A8h+var_58], r11
0x14000896a  mov     [rsp+0A8h+var_60], 2
0x140008973  mov     [rsp+0A8h+var_68], rdx
0x140008978  lea     edx, [rsi+20h]
0x14000897b  mov     [rsp+0A8h+var_70], 8
0x140008984  mov     [rsp+0A8h+var_78], rcx
0x140008989  mov     rcx, rbx
0x14000898c  mov     [rsp+0A8h+var_80], r10
0x140008991  mov     [rsp+0A8h+var_88], r9
0x140008996  mov     r9d, esi
0x140008999  call    _guard_dispatch_icall
0x14000899e  mov     rbx, [rsp+0A8h+arg_0]
0x1400089a6  add     rsp, 0A0h
0x1400089ad  pop     rsi
0x1400089ae  retn
```
