# XmlParserTempString::Append(XmlParserTempString &)

- ea: `0x18001e64c`
- end: `0x18001e835`
- name: `?Append@XmlParserTempString@@QEAAJAEAU1@@Z`
- size: `489`
- prototype: `__int64 __fastcall(XmlParserTempString *__hidden this, struct XmlParserTempString *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001ed88`

## callees

- `0x180008c4c`
- `0x18000edd8`
- `0x18000ee24`
- `0x18001e64c`
- `0x180021de4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001e735`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001e735`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e7af`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e7eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e7af`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e7eb`

## pseudocode

```c
int __fastcall XmlParserTempString::Append(
        XmlParserTempString *this,
        const unsigned __int16 **a2,
        __int64 a3,
        size_t a4)
{
  int v6; // ecx
  char v7; // r8
  size_t v8; // rdx
  int result; // eax
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
      v19 = byte_180052608;
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
                  *((const unsigned __int16 **)this + 1)),
          v15 < 0)
      || (v15 = StringCchCopyNW(&v14[*(unsigned int *)this], (unsigned int)(*(_DWORD *)a2 + 1), a2[1]), v15 < 0) )
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
    result = StringCchCopyNW((unsigned __int16 *)this + 8, 0x200u, *((const unsigned __int16 **)this + 1));
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
0x18001e64c  mov     [rsp-18h+arg_0], rbx
0x18001e651  mov     [rsp-18h+arg_10], rsi
0x18001e656  push    rbp
0x18001e657  push    rdi
0x18001e658  push    r14
0x18001e65a  mov     rbp, rsp
0x18001e65d  sub     rsp, 70h
0x18001e661  mov     rbx, rcx
0x18001e664  mov     rdi, rdx
0x18001e667  mov     ecx, [rdx]
0x18001e669  test    ecx, ecx
0x18001e66b  jz      loc_18001E81D
0x18001e671  mov     r8b, [rbx+412h]
0x18001e678  test    r8b, 1
0x18001e67c  jnz     loc_18001E72F
0x18001e682  mov     edx, [rbx]
0x18001e684  mov     r11d, 200h
0x18001e68a  lea     eax, [rdx+rcx]
0x18001e68d  cmp     eax, r11d
0x18001e690  jnb     loc_18001E72F
0x18001e696  test    edx, edx
0x18001e698  jz      short loc_18001E6C2
0x18001e69a  test    r8b, 2
0x18001e69e  jnz     short loc_18001E6C2
0x18001e6a0  mov     r8, [rbx+8]; unsigned __int16 *
0x18001e6a4  lea     rsi, [rbx+10h]
0x18001e6a8  mov     r9d, edx; unsigned __int64
0x18001e6ab  mov     rcx, rsi; unsigned __int16 *
0x18001e6ae  mov     edx, r11d; unsigned __int64
0x18001e6b1  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001e6b6  test    eax, eax
0x18001e6b8  js      loc_18001E81F
0x18001e6be  mov     [rbx+8], rsi
0x18001e6c2  lea     rsi, [rbx+10h]
0x18001e6c6  mov     [rbp+pcchDestLength], 0
0x18001e6ce  mov     rcx, rsi; pszDest
0x18001e6d1  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x18001e6d5  call    StringValidateDestAndLengthW
0x18001e6da  test    eax, eax
0x18001e6dc  js      loc_18001E81F
0x18001e6e2  mov     edx, [rdi]
0x18001e6e4  cmp     rdx, 7FFFFFFEh
0x18001e6eb  jbe     short loc_18001E6F7
0x18001e6ed  mov     eax, 80070057h
0x18001e6f2  jmp     loc_18001E81F
0x18001e6f7  mov     rax, [rbp+pcchDestLength]
0x18001e6fb  mov     r9, [rdi+8]; pszSrc
0x18001e6ff  sub     r11, rax
0x18001e702  mov     [rsp+70h+cchToCopy], rdx; cchToCopy
0x18001e707  mov     rdx, r11; cchDest
0x18001e70a  lea     rcx, [rsi+rax*2]; pszDest
0x18001e70e  call    StringCopyWorkerW
0x18001e713  test    eax, eax
0x18001e715  js      loc_18001E81F
0x18001e71b  mov     [rbx+8], rsi
0x18001e71f  mov     eax, [rdi]
0x18001e721  add     [rbx], eax
0x18001e723  or      byte ptr [rbx+412h], 2
0x18001e72a  jmp     loc_18001E81D
0x18001e72f  mov     edx, [rbx]
0x18001e731  add     edx, ecx; ui
0x18001e733  xor     ecx, ecx; strIn
0x18001e735  call    cs:__imp_SysAllocStringLen
0x18001e73c  nop     dword ptr [rax+rax+00h]
0x18001e741  mov     rsi, rax
0x18001e744  test    rax, rax
0x18001e747  jnz     short loc_18001E78A
0x18001e749  mov     [rbp+var_38], al
0x18001e74c  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001e753  lea     rax, byte_180052608
0x18001e75a  mov     [rbp+var_28], rsi
0x18001e75e  mov     [rbp+var_30], rax
0x18001e762  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e766  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001e76d  mov     [rbp+var_20], rsi
0x18001e771  mov     [rbp+pExceptionObject], rax
0x18001e775  mov     [rbp+var_18], 0Eh
0x18001e77c  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001e784  call    _CxxThrowException_0
0x18001e78a  mov     ecx, [rbx]
0x18001e78c  test    ecx, ecx
0x18001e78e  jz      short loc_18001E7C0
0x18001e790  mov     edx, [rdi]
0x18001e792  mov     r9d, ecx; unsigned __int64
0x18001e795  mov     r8, [rbx+8]; unsigned __int16 *
0x18001e799  inc     ecx
0x18001e79b  add     edx, ecx; unsigned __int64
0x18001e79d  mov     rcx, rsi; unsigned __int16 *
0x18001e7a0  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001e7a5  mov     r14d, eax
0x18001e7a8  test    eax, eax
0x18001e7aa  jns     short loc_18001E7C0
0x18001e7ac  mov     rcx, rsi; bstrString
0x18001e7af  call    cs:__imp_SysFreeString
0x18001e7b6  nop     dword ptr [rax+rax+00h]
0x18001e7bb  mov     eax, r14d
0x18001e7be  jmp     short loc_18001E81F
0x18001e7c0  mov     eax, [rdi]
0x18001e7c2  mov     r8, [rdi+8]; unsigned __int16 *
0x18001e7c6  mov     r9d, eax; unsigned __int64
0x18001e7c9  lea     edx, [rax+1]; unsigned __int64
0x18001e7cc  mov     eax, [rbx]
0x18001e7ce  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x18001e7d2  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001e7d7  mov     r14d, eax
0x18001e7da  test    eax, eax
0x18001e7dc  js      short loc_18001E7AC
0x18001e7de  test    byte ptr [rbx+412h], 1
0x18001e7e5  jz      short loc_18001E7F7
0x18001e7e7  mov     rcx, [rbx+8]; bstrString
0x18001e7eb  call    cs:__imp_SysFreeString
0x18001e7f2  nop     dword ptr [rax+rax+00h]
0x18001e7f7  mov     cl, [rbx+412h]
0x18001e7fd  xor     eax, eax
0x18001e7ff  and     cl, 0FDh
0x18001e802  mov     [rbx+10h], ax
0x18001e806  mov     [rbx+412h], cl
0x18001e80c  mov     [rbx+8], rsi
0x18001e810  mov     eax, [rdi]
0x18001e812  add     [rbx], eax
0x18001e814  or      cl, 1
0x18001e817  mov     [rbx+412h], cl
0x18001e81d  xor     eax, eax
0x18001e81f  lea     r11, [rsp+70h+var_s0]
0x18001e824  mov     rbx, [r11+20h]
0x18001e828  mov     rsi, [r11+30h]
0x18001e82c  mov     rsp, r11
0x18001e82f  pop     r14
0x18001e831  pop     rdi
0x18001e832  pop     rbp
0x18001e833  retn
```
