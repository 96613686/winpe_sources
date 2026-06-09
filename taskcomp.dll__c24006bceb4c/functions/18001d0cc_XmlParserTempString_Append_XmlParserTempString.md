# XmlParserTempString::Append(XmlParserTempString &)

- ea: `0x18001d0cc`
- end: `0x18001d2a2`
- name: `?Append@XmlParserTempString@@QEAAJAEAU1@@Z`
- size: `470`
- prototype: `HRESULT __fastcall(XmlParserTempString *this, const unsigned __int16 **, __int64, size_t)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001d7dc`

## callees

- `0x18000878c`
- `0x18000e4d8`
- `0x18000e524`
- `0x18001d0cc`
- `0x1800207d4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001d1b5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001d1b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d229`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d25f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d229`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d25f`

## pseudocode

```c
HRESULT __fastcall XmlParserTempString::Append(
        XmlParserTempString *this,
        const unsigned __int16 **a2,
        __int64 a3,
        size_t a4)
{
  int v6; // ecx
  char v7; // r8
  size_t v8; // rdx
  HRESULT result; // eax
  char *v10; // rsi
  size_t *v11; // r8
  __int64 v12; // r11
  unsigned __int16 *v13; // rax
  OLECHAR *v14; // rsi
  int v15; // r14d
  char v16; // cl
  void **pExceptionObject; // [rsp+30h] [rbp-40h] BYREF
  char v18; // [rsp+38h] [rbp-38h]
  char *v19; // [rsp+40h] [rbp-30h]
  __int64 v20; // [rsp+48h] [rbp-28h]
  __int64 v21; // [rsp+50h] [rbp-20h]
  int v22; // [rsp+58h] [rbp-18h]
  __int64 v23; // [rsp+5Ch] [rbp-14h]
  size_t pcchDestLength; // [rsp+98h] [rbp+28h] BYREF

  v6 = *(_DWORD *)a2;
  if ( !*(_DWORD *)a2 )
    return 0;
  v7 = *((_BYTE *)this + 1042);
  if ( (v7 & 1) != 0 || (v8 = *(unsigned int *)this, (unsigned int)(v8 + v6) >= 0x200) )
  {
    v13 = SysAllocStringLen(0, v6 + *(_DWORD *)this);
    v14 = v13;
    if ( !v13 )
    {
      v18 = 0;
      v20 = 0;
      v19 = byte_1800505F8;
      v21 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v22 = 14;
      v23 = -1;
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    if ( *(_DWORD *)this
      && (v15 = StringCchCopyNW(
                  v13,
                  (unsigned int)(*(_DWORD *)this + 1 + *(_DWORD *)a2),
                  *((const unsigned __int16 **)this + 1),
                  *(unsigned int *)this),
          v15 < 0)
      || (v15 = StringCchCopyNW(
                  &v14[*(unsigned int *)this],
                  (unsigned int)(*(_DWORD *)a2 + 1),
                  a2[1],
                  *(unsigned int *)a2),
          v15 < 0) )
    {
      SysFreeString(v14);
      return v15;
    }
    if ( (*((_BYTE *)this + 1042) & 1) != 0 )
      SysFreeString(*((BSTR *)this + 1));
    v16 = *((_BYTE *)this + 1042) & 0xFD;
    *((_WORD *)this + 8) = 0;
    *((_BYTE *)this + 1042) = v16;
    *((_QWORD *)this + 1) = v14;
    *(_DWORD *)this += *(_DWORD *)a2;
    *((_BYTE *)this + 1042) = v16 | 1;
    return 0;
  }
  if ( (_DWORD)v8 && (v7 & 2) == 0 )
  {
    result = StringCchCopyNW(
               (unsigned __int16 *)this + 8,
               0x200u,
               *((const unsigned __int16 **)this + 1),
               (unsigned int)v8);
    if ( result < 0 )
      return result;
    *((_QWORD *)this + 1) = (char *)this + 16;
  }
  v10 = (char *)this + 16;
  pcchDestLength = 0;
  result = StringValidateDestAndLengthW((STRSAFE_LPCWSTR)this + 8, v8, &pcchDestLength, a4);
  if ( result >= 0 )
  {
    if ( *(unsigned int *)a2 > 0x7FFFFFFEuLL )
      return -2147024809;
    result = StringCopyWorkerW(
               (STRSAFE_LPWSTR)&v10[2 * pcchDestLength],
               v12 - pcchDestLength,
               v11,
               a2[1],
               *(unsigned int *)a2);
    if ( result >= 0 )
    {
      *((_QWORD *)this + 1) = v10;
      *(_DWORD *)this += *(_DWORD *)a2;
      *((_BYTE *)this + 1042) |= 2u;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d0cc  mov     [rsp-18h+arg_0], rbx
0x18001d0d1  mov     [rsp-18h+arg_10], rsi
0x18001d0d6  push    rbp
0x18001d0d7  push    rdi
0x18001d0d8  push    r14
0x18001d0da  mov     rbp, rsp
0x18001d0dd  sub     rsp, 70h
0x18001d0e1  mov     rbx, rcx
0x18001d0e4  mov     rdi, rdx
0x18001d0e7  mov     ecx, [rdx]
0x18001d0e9  test    ecx, ecx
0x18001d0eb  jz      loc_18001D28B
0x18001d0f1  mov     r8b, [rbx+412h]
0x18001d0f8  test    r8b, 1
0x18001d0fc  jnz     loc_18001D1AF
0x18001d102  mov     edx, [rbx]
0x18001d104  mov     r11d, 200h
0x18001d10a  lea     eax, [rdx+rcx]
0x18001d10d  cmp     eax, r11d
0x18001d110  jnb     loc_18001D1AF
0x18001d116  test    edx, edx
0x18001d118  jz      short loc_18001D142
0x18001d11a  test    r8b, 2
0x18001d11e  jnz     short loc_18001D142
0x18001d120  mov     r8, [rbx+8]; unsigned __int16 *
0x18001d124  lea     rsi, [rbx+10h]
0x18001d128  mov     r9d, edx; unsigned __int64
0x18001d12b  mov     rcx, rsi; unsigned __int16 *
0x18001d12e  mov     edx, r11d; unsigned __int64
0x18001d131  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001d136  test    eax, eax
0x18001d138  js      loc_18001D28D
0x18001d13e  mov     [rbx+8], rsi
0x18001d142  lea     rsi, [rbx+10h]
0x18001d146  mov     [rbp+pcchDestLength], 0
0x18001d14e  mov     rcx, rsi; pszDest
0x18001d151  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x18001d155  call    StringValidateDestAndLengthW
0x18001d15a  test    eax, eax
0x18001d15c  js      loc_18001D28D
0x18001d162  mov     edx, [rdi]
0x18001d164  cmp     rdx, 7FFFFFFEh
0x18001d16b  jbe     short loc_18001D177
0x18001d16d  mov     eax, 80070057h
0x18001d172  jmp     loc_18001D28D
0x18001d177  mov     rax, [rbp+pcchDestLength]
0x18001d17b  mov     r9, [rdi+8]; pszSrc
0x18001d17f  sub     r11, rax
0x18001d182  mov     [rsp+70h+cchToCopy], rdx; cchToCopy
0x18001d187  mov     rdx, r11; cchDest
0x18001d18a  lea     rcx, [rsi+rax*2]; pszDest
0x18001d18e  call    StringCopyWorkerW
0x18001d193  test    eax, eax
0x18001d195  js      loc_18001D28D
0x18001d19b  mov     [rbx+8], rsi
0x18001d19f  mov     eax, [rdi]
0x18001d1a1  add     [rbx], eax
0x18001d1a3  or      byte ptr [rbx+412h], 2
0x18001d1aa  jmp     loc_18001D28B
0x18001d1af  mov     edx, [rbx]
0x18001d1b1  add     edx, ecx; ui
0x18001d1b3  xor     ecx, ecx; strIn
0x18001d1b5  call    cs:__imp_SysAllocStringLen
0x18001d1bb  mov     rsi, rax
0x18001d1be  test    rax, rax
0x18001d1c1  jnz     short loc_18001D204
0x18001d1c3  mov     [rbp+var_38], al
0x18001d1c6  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001d1cd  lea     rax, byte_1800505F8
0x18001d1d4  mov     [rbp+var_28], rsi
0x18001d1d8  mov     [rbp+var_30], rax
0x18001d1dc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d1e0  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001d1e7  mov     [rbp+var_20], rsi
0x18001d1eb  mov     [rbp+pExceptionObject], rax
0x18001d1ef  mov     [rbp+var_18], 0Eh
0x18001d1f6  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001d1fe  call    _CxxThrowException_0
0x18001d204  mov     ecx, [rbx]
0x18001d206  test    ecx, ecx
0x18001d208  jz      short loc_18001D234
0x18001d20a  mov     edx, [rdi]
0x18001d20c  mov     r9d, ecx; unsigned __int64
0x18001d20f  mov     r8, [rbx+8]; unsigned __int16 *
0x18001d213  inc     ecx
0x18001d215  add     edx, ecx; unsigned __int64
0x18001d217  mov     rcx, rsi; unsigned __int16 *
0x18001d21a  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001d21f  mov     r14d, eax
0x18001d222  test    eax, eax
0x18001d224  jns     short loc_18001D234
0x18001d226  mov     rcx, rsi; bstrString
0x18001d229  call    cs:__imp_SysFreeString
0x18001d22f  mov     eax, r14d
0x18001d232  jmp     short loc_18001D28D
0x18001d234  mov     eax, [rdi]
0x18001d236  mov     r8, [rdi+8]; unsigned __int16 *
0x18001d23a  mov     r9d, eax; unsigned __int64
0x18001d23d  lea     edx, [rax+1]; unsigned __int64
0x18001d240  mov     eax, [rbx]
0x18001d242  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x18001d246  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001d24b  mov     r14d, eax
0x18001d24e  test    eax, eax
0x18001d250  js      short loc_18001D226
0x18001d252  test    byte ptr [rbx+412h], 1
0x18001d259  jz      short loc_18001D265
0x18001d25b  mov     rcx, [rbx+8]; bstrString
0x18001d25f  call    cs:__imp_SysFreeString
0x18001d265  mov     cl, [rbx+412h]
0x18001d26b  xor     eax, eax
0x18001d26d  and     cl, 0FDh
0x18001d270  mov     [rbx+10h], ax
0x18001d274  mov     [rbx+412h], cl
0x18001d27a  mov     [rbx+8], rsi
0x18001d27e  mov     eax, [rdi]
0x18001d280  add     [rbx], eax
0x18001d282  or      cl, 1
0x18001d285  mov     [rbx+412h], cl
0x18001d28b  xor     eax, eax
0x18001d28d  lea     r11, [rsp+70h+var_s0]
0x18001d292  mov     rbx, [r11+20h]
0x18001d296  mov     rsi, [r11+30h]
0x18001d29a  mov     rsp, r11
0x18001d29d  pop     r14
0x18001d29f  pop     rdi
0x18001d2a0  pop     rbp
0x18001d2a1  retn
```
