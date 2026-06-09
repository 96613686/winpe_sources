# WPP_SF_qdssD

- ea: `0x140013af4`
- end: `0x140013bef`
- name: `WPP_SF_qdssD`
- size: `251`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x1400023b0`
- `0x140003590`
- `0x140003840`
- `0x1400047d0`
- `0x140006db0`
- `0x1400075b0`
- `0x140008620`
- `0x1400087a0`
- `0x140008c90`
- `0x140008ef0`
- `0x140009010`
- `0x140009290`
- `0x140009ad0`
- `0x14000a5f0`
- `0x14000aad0`
- `0x14000f8d0`

## callees

- `0x140013af4`
- `0x140018590`

## pseudocode

```c
__int64 WPP_SF_qdssD(__int64 a1, __int64 a2, __int64 a3, ...)
{
  const char *v3; // rdx
  __int64 v4; // rax
  __int64 v6; // r9
  __int64 v7; // r8
  __int64 v8; // r8
  const char *v9; // rcx
  bool v10; // zf
  __int64 v12; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+A8h] [rbp+20h]
  __int64 v14; // [rsp+B0h] [rbp+28h] BYREF
  va_list va1; // [rsp+B0h] [rbp+28h]
  const char *v16; // [rsp+B8h] [rbp+30h]
  const char *v17; // [rsp+C0h] [rbp+38h]
  va_list va2; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v12 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v14 = va_arg(va2, _QWORD);
  v16 = va_arg(va2, const char *);
  v17 = va_arg(va2, const char *);
  v3 = v17;
  v4 = -1;
  v6 = 5;
  if ( v17 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v17[v7] );
    v8 = v7 + 1;
  }
  else
  {
    v8 = 5;
  }
  v9 = v16;
  if ( !v17 )
    v3 = "NULL";
  v10 = v16 == 0;
  if ( v16 )
  {
    do
      ++v4;
    while ( v16[v4] );
    v6 = v4 + 1;
    v10 = v16 == 0;
  }
  if ( v10 )
    v9 = "NULL";
  return pfnWppTraceMessage(
           a1,
           43,
           WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
           10,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           4,
           v9,
           v6,
           v3,
           v8,
           va2);
}

```

## disassembly

```asm
0x140013af4  mov     [rsp+arg_0], rbx
0x140013af9  mov     [rsp+arg_18], r9
0x140013afe  push    rdi
0x140013aff  sub     rsp, 80h
0x140013b06  mov     rdx, [rsp+88h+arg_30]
0x140013b0e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013b12  xor     r11d, r11d
0x140013b15  mov     r10, rcx
0x140013b18  mov     r9d, 5
0x140013b1e  test    rdx, rdx
0x140013b21  jz      short loc_140013B34
0x140013b23  mov     r8, rax
0x140013b26  inc     r8
0x140013b29  cmp     [rdx+r8], r11b
0x140013b2d  jnz     short loc_140013B26
0x140013b2f  inc     r8
0x140013b32  jmp     short loc_140013B37
0x140013b34  mov     r8, r9
0x140013b37  mov     rcx, [rsp+88h+arg_28]
0x140013b3f  lea     rbx, aNull; "NULL"
0x140013b46  test    rdx, rdx
0x140013b49  cmovz   rdx, rbx
0x140013b4d  test    rcx, rcx
0x140013b50  jz      short loc_140013B62
0x140013b52  inc     rax
0x140013b55  cmp     [rcx+rax], r11b
0x140013b59  jnz     short loc_140013B52
0x140013b5b  lea     r9, [rax+1]
0x140013b5f  test    rcx, rcx
0x140013b62  mov     rax, cs:pfnWppTraceMessage
0x140013b69  cmovz   rcx, rbx
0x140013b6d  mov     [rsp+88h+var_18], r11
0x140013b72  mov     edi, 0Ah
0x140013b77  lea     r11, [rsp+88h+arg_38]
0x140013b7f  lea     ebx, [rdi-6]
0x140013b82  mov     [rsp+88h+var_20], rbx
0x140013b87  mov     [rsp+88h+var_28], r11
0x140013b8c  mov     [rsp+88h+var_30], r8
0x140013b91  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140013b98  mov     [rsp+88h+var_38], rdx
0x140013b9d  lea     edx, [rdi+21h]
0x140013ba0  mov     [rsp+88h+var_40], r9
0x140013ba5  mov     r9d, edi
0x140013ba8  mov     [rsp+88h+var_48], rcx
0x140013bad  lea     rcx, [rsp+88h+arg_20]
0x140013bb5  mov     [rsp+88h+var_50], rbx
0x140013bba  mov     [rsp+88h+var_58], rcx
0x140013bbf  lea     rcx, [rsp+88h+arg_18]
0x140013bc7  mov     [rsp+88h+var_60], 8
0x140013bd0  mov     [rsp+88h+var_68], rcx
0x140013bd5  mov     rcx, r10
0x140013bd8  call    _guard_dispatch_icall
0x140013bdd  mov     rbx, [rsp+88h+arg_0]
0x140013be5  add     rsp, 80h
0x140013bec  pop     rdi
0x140013bed  retn
```
