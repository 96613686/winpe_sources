# MinAsn1ParseAndDecodeRDNComponent

- ea: `0x18004c91c`
- end: `0x18004ca38`
- name: `MinAsn1ParseAndDecodeRDNComponent`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016ee0`

## callees

- `0x180033980`
- `0x18004c91c`
- `0x18004dd2c`
- `0x18004de78`

## pseudocode

```c
char __fastcall MinAsn1ParseAndDecodeRDNComponent(unsigned int *a1, __int64 a2, _BYTE *a3, __int64 a4)
{
  __int64 v4; // rdx
  __int64 v6; // rcx
  __int64 v8; // rdi
  int v9; // ebx
  int v10; // ecx
  _BYTE *v11; // rbx
  int v13; // [rsp+30h] [rbp-39h] BYREF
  __int64 v14; // [rsp+38h] [rbp-31h] BYREF
  int v15; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v16[16]; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v17; // [rsp+60h] [rbp-9h]
  int v18; // [rsp+70h] [rbp+7h]
  unsigned __int16 *v19; // [rsp+78h] [rbp+Fh]
  unsigned int v20; // [rsp+80h] [rbp+17h]
  _BYTE *v21; // [rsp+88h] [rbp+1Fh]

  v4 = *a1;
  v6 = *((_QWORD *)a1 + 1);
  v15 = 4;
  v14 = 0;
  v13 = 0;
  if ( (int)MinAsn1ExtractContent(v6, v4, &v13, &v14) > 0 )
  {
    v8 = v14;
    v9 = v13;
    while ( v9
         && (int)MinAsn1ExtractValues(v8, v9, (unsigned int)&v15, (unsigned int)&qword_180035DE0, 4, (__int64)v16) > 0 )
    {
      if ( v18 == 3 )
      {
        v10 = *v19 - 1109;
        if ( *v19 == 1109 )
          v10 = *((unsigned __int8 *)v19 + 2) - BYTE2(qword_180052008);
        if ( !v10 )
        {
          v11 = v21;
          if ( (int)MinAsn1ExtractContent(v21, v20, &v13, &v14) <= 0 )
            return 0;
          *a3 = *v11;
          *(_QWORD *)(a4 + 8) = v14;
          *(_DWORD *)a4 = v13;
          return 1;
        }
      }
      v8 += v17;
      v9 -= v17;
      v13 = v9;
      v14 = v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004c91c  push    rbp
0x18004c91e  push    rbx
0x18004c91f  push    rsi
0x18004c920  push    rdi
0x18004c921  push    r14
0x18004c923  lea     rbp, [rsp-37h]
0x18004c928  sub     rsp, 0A0h
0x18004c92f  mov     rax, cs:__security_cookie
0x18004c936  xor     rax, rsp
0x18004c939  mov     [rbp+57h+var_30], rax
0x18004c93d  mov     edx, [rcx]
0x18004c93f  mov     rsi, r9
0x18004c942  mov     rcx, [rcx+8]
0x18004c946  lea     r9, [rbp+57h+var_88]
0x18004c94a  mov     r14, r8
0x18004c94d  mov     [rbp+57h+var_80], 4
0x18004c954  lea     r8, [rbp+57h+var_90]
0x18004c958  mov     [rbp+57h+var_88], 0
0x18004c960  mov     [rbp+57h+var_90], 0
0x18004c967  call    MinAsn1ExtractContent
0x18004c96c  test    eax, eax
0x18004c96e  jle     loc_18004CA1B
0x18004c974  mov     rdi, [rbp+57h+var_88]
0x18004c978  mov     ebx, [rbp+57h+var_90]
0x18004c97b  test    ebx, ebx
0x18004c97d  jz      loc_18004CA1B
0x18004c983  lea     rax, [rbp+57h+var_70]
0x18004c987  mov     edx, ebx
0x18004c989  mov     [rsp+0C0h+var_98], rax
0x18004c98e  lea     r9, qword_180035DE0
0x18004c995  lea     r8, [rbp+57h+var_80]
0x18004c999  mov     [rsp+0C0h+var_A0], 4
0x18004c9a1  mov     rcx, rdi
0x18004c9a4  call    MinAsn1ExtractValues
0x18004c9a9  test    eax, eax
0x18004c9ab  jle     short loc_18004CA1B
0x18004c9ad  cmp     [rbp+57h+var_50], 3
0x18004c9b1  jnz     short loc_18004C9D8
0x18004c9b3  mov     rdx, [rbp+57h+var_48]
0x18004c9b7  mov     r8, cs:off_1800523D0
0x18004c9be  movzx   ecx, word ptr [rdx]
0x18004c9c1  movzx   eax, word ptr [r8]
0x18004c9c5  sub     ecx, eax
0x18004c9c7  jnz     short loc_18004C9D4
0x18004c9c9  movzx   ecx, byte ptr [rdx+2]
0x18004c9cd  movzx   eax, byte ptr [r8+2]
0x18004c9d2  sub     ecx, eax
0x18004c9d4  test    ecx, ecx
0x18004c9d6  jz      short loc_18004C9EA
0x18004c9d8  mov     eax, [rbp+57h+var_60]
0x18004c9db  add     rdi, rax
0x18004c9de  sub     ebx, [rbp+57h+var_60]
0x18004c9e1  mov     [rbp+57h+var_90], ebx
0x18004c9e4  mov     [rbp+57h+var_88], rdi
0x18004c9e8  jmp     short loc_18004C97B
0x18004c9ea  mov     rbx, [rbp+57h+var_38]
0x18004c9ee  lea     r9, [rbp+57h+var_88]
0x18004c9f2  mov     edx, [rbp+57h+var_40]
0x18004c9f5  lea     r8, [rbp+57h+var_90]
0x18004c9f9  mov     rcx, rbx
0x18004c9fc  call    MinAsn1ExtractContent
0x18004ca01  test    eax, eax
0x18004ca03  jle     short loc_18004CA1B
0x18004ca05  mov     al, [rbx]
0x18004ca07  mov     [r14], al
0x18004ca0a  mov     rax, [rbp+57h+var_88]
0x18004ca0e  mov     [rsi+8], rax
0x18004ca12  mov     eax, [rbp+57h+var_90]
0x18004ca15  mov     [rsi], eax
0x18004ca17  mov     al, 1
0x18004ca19  jmp     short loc_18004CA1D
0x18004ca1b  xor     al, al
0x18004ca1d  mov     rcx, [rbp+57h+var_30]
0x18004ca21  xor     rcx, rsp; StackCookie
0x18004ca24  call    __security_check_cookie
0x18004ca29  add     rsp, 0A0h
0x18004ca30  pop     r14
0x18004ca32  pop     rdi
0x18004ca33  pop     rsi
0x18004ca34  pop     rbx
0x18004ca35  pop     rbp
0x18004ca36  retn
```
