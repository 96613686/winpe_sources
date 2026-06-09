# Appx::Internal::GetFamilyKeyPathForPackageAcquisitionInfo(ushort const *,ushort *,unsigned __int64 *)

- ea: `0x18002e110`
- end: `0x18002e2d5`
- name: `?GetFamilyKeyPathForPackageAcquisitionInfo@Internal@Appx@@YAJPEBGPEAGPEA_K@Z`
- size: `453`
- prototype: `int(Appx::Internal *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002df3c`

## callees

- `0x180013300`
- `0x18002e110`
- `0x18003a580`
- `0x18003af10`
- `0x18004afcc`

## pseudocode

```c
__int64 __fastcall Appx::Internal::GetFamilyKeyPathForPackageAcquisitionInfo(
        Appx::Internal *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int64 *a4)
{
  Appx::Internal *v7; // rax
  __int64 v8; // r8
  unsigned int v9; // ebp
  __int64 v10; // rcx
  __int64 v11; // r8
  const wchar_t *v12; // r9
  __int64 v13; // rax
  int *v14; // rdx
  __int64 v15; // rbp
  unsigned int v16; // r8d
  unsigned int v17; // edi
  unsigned int v18; // r8d
  __int64 result; // rax
  int v20; // [rsp+20h] [rbp-248h]
  int v21; // [rsp+20h] [rbp-248h]
  int v22; // [rsp+20h] [rbp-248h]
  int v23; // [rsp+30h] [rbp-238h] BYREF
  char v24[524]; // [rsp+34h] [rbp-234h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v23 = 0;
  memset_0(v24, 0, 0x204u);
  if ( !this || !a2 || !a3 )
    return 2147942487LL;
  v7 = this;
  v8 = 65;
  do
  {
    if ( !*(_WORD *)v7 )
      break;
    v7 = (Appx::Internal *)((char *)v7 + 2);
    --v8;
  }
  while ( v8 );
  v9 = -2147024809;
  if ( v8 )
    v9 = 0;
  v10 = 65 - v8;
  if ( v8 )
  {
    v11 = 2147483646;
    v12 = L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\SystemAppData\\";
    v13 = 260;
    v14 = &v23;
    while ( v11 && *v12 )
    {
      *(_WORD *)v14 = *v12++;
      v14 = (int *)((char *)v14 + 2);
      --v11;
      if ( !--v13 )
      {
        *((_WORD *)v14 - 1) = 0;
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xCB, v11, (const char *)0x8007007ALL, v20);
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xDF, v18, (const char *)0x8007007ALL, v22);
        return 2147942522LL;
      }
    }
    v15 = v10 + 99;
    *(_WORD *)v14 = 0;
    if ( *(_QWORD *)a3 < (unsigned __int64)(v10 + 99) )
    {
      *(_QWORD *)a3 = v15;
      return 2147942522LL;
    }
    else
    {
      v21 = (int)this;
      result = StringCchPrintfW(a2, *(_QWORD *)a3, L"%s%s", &v23);
      v17 = result;
      if ( (int)result < 0 )
      {
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xE9, v16, (const char *)(unsigned int)result, v21);
        return v17;
      }
      else
      {
        *(_QWORD *)a3 = v15;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xDE, 0, (const char *)v9, v20);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x18002e110  mov     [rsp+arg_18], rbx
0x18002e115  push    rbp
0x18002e116  push    rsi
0x18002e117  push    rdi
0x18002e118  sub     rsp, 250h
0x18002e11f  mov     rax, cs:__security_cookie
0x18002e126  xor     rax, rsp
0x18002e129  mov     [rsp+268h+var_28], rax
0x18002e131  mov     rbx, r8
0x18002e134  mov     rsi, rdx
0x18002e137  mov     rdi, rcx
0x18002e13a  xor     eax, eax
0x18002e13c  xor     edx, edx; Val
0x18002e13e  mov     [rsp+268h+var_238], eax
0x18002e142  mov     r8d, 204h; Size
0x18002e148  lea     rcx, [rsp+268h+var_234]; void *
0x18002e14d  call    memset_0
0x18002e152  test    rdi, rdi
0x18002e155  jz      loc_18002E2CB
0x18002e15b  test    rsi, rsi
0x18002e15e  jz      loc_18002E2CB
0x18002e164  test    rbx, rbx
0x18002e167  jz      loc_18002E2CB
0x18002e16d  mov     ecx, 41h ; 'A'
0x18002e172  mov     rax, rdi
0x18002e175  mov     r8d, ecx
0x18002e178  cmp     word ptr [rax], 0
0x18002e17c  jz      short loc_18002E188
0x18002e17e  add     rax, 2
0x18002e182  sub     r8, 1; unsigned int
0x18002e186  jnz     short loc_18002E178
0x18002e188  xor     eax, eax
0x18002e18a  mov     ebp, 80070057h
0x18002e18f  test    r8, r8
0x18002e192  cmovnz  ebp, eax
0x18002e195  sub     rcx, r8
0x18002e198  xor     edx, edx
0x18002e19a  test    r8, r8
0x18002e19d  cmovz   rcx, rdx
0x18002e1a1  jz      loc_18002E286
0x18002e1a7  mov     r8d, 7FFFFFFEh
0x18002e1ad  lea     r9, aSoftwareClasse; "Software\\Classes\\Local Settings\\Soft"...
0x18002e1b4  mov     eax, 104h
0x18002e1b9  lea     rdx, [rsp+268h+var_238]
0x18002e1be  test    r8, r8
0x18002e1c1  jz      short loc_18002E1D2
0x18002e1c3  movzx   r10d, word ptr [r9]
0x18002e1c7  test    r10w, r10w
0x18002e1cb  jnz     short loc_18002E230
0x18002e1cd  test    rax, rax
0x18002e1d0  jz      short loc_18002E249
0x18002e1d2  xor     eax, eax
0x18002e1d4  lea     rbp, [rcx+63h]
0x18002e1d8  mov     [rdx], ax
0x18002e1db  mov     rdx, [rbx]; unsigned __int64
0x18002e1de  cmp     rdx, rbp
0x18002e1e1  jb      loc_18002E2A2
0x18002e1e7  lea     r9, [rsp+268h+var_238]
0x18002e1ec  mov     qword ptr [rsp+268h+var_248], rdi; int
0x18002e1f1  lea     r8, aSS; "%s%s"
0x18002e1f8  mov     rcx, rsi; unsigned __int16 *
0x18002e1fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e200  mov     edi, eax
0x18002e202  test    eax, eax
0x18002e204  js      loc_18002E2AF
0x18002e20a  mov     [rbx], rbp
0x18002e20d  mov     rcx, [rsp+268h+var_28]
0x18002e215  xor     rcx, rsp; StackCookie
0x18002e218  call    __security_check_cookie
0x18002e21d  mov     rbx, [rsp+268h+arg_18]
0x18002e225  add     rsp, 250h
0x18002e22c  pop     rdi
0x18002e22d  pop     rsi
0x18002e22e  pop     rbp
0x18002e22f  retn
0x18002e230  mov     [rdx], r10w
0x18002e234  add     r9, 2
0x18002e238  add     rdx, 2
0x18002e23c  dec     r8; unsigned int
0x18002e23f  sub     rax, 1
0x18002e243  jnz     loc_18002E1BE
0x18002e249  mov     rcx, [rsp+268h]; this
0x18002e251  xor     eax, eax
0x18002e253  mov     [rdx-2], ax
0x18002e257  mov     r9d, 8007007Ah; char *
0x18002e25d  mov     edx, 0CBh; void *
0x18002e262  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e267  mov     rcx, [rsp+268h]; this
0x18002e26f  mov     edx, 0DFh; void *
0x18002e274  mov     r9d, 8007007Ah; char *
0x18002e27a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e27f  mov     eax, 8007007Ah
0x18002e284  jmp     short loc_18002E20D
0x18002e286  mov     rcx, [rsp+268h]; this
0x18002e28e  mov     r9d, ebp; char *
0x18002e291  mov     edx, 0DEh; void *
0x18002e296  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e29b  mov     eax, ebp
0x18002e29d  jmp     loc_18002E20D
0x18002e2a2  mov     [rbx], rbp
0x18002e2a5  mov     eax, 8007007Ah
0x18002e2aa  jmp     loc_18002E20D
0x18002e2af  mov     rcx, [rsp+268h]; this
0x18002e2b7  mov     r9d, edi; char *
0x18002e2ba  mov     edx, 0E9h; void *
0x18002e2bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e2c4  mov     eax, edi
0x18002e2c6  jmp     loc_18002E20D
0x18002e2cb  mov     eax, 80070057h
0x18002e2d0  jmp     loc_18002E20D
```
