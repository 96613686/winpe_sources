# CObjectPathParser::key_const(void)

- ea: `0x180014d28`
- end: `0x180014eeb`
- name: `?key_const@CObjectPathParser@@AEAAHXZ`
- size: `451`
- prototype: `__int64 __fastcall(CObjectPathParser *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180014ef4`
- `0x180015220`

## callees

- `0x180006fe0`
- `0x1800147b8`
- `0x180014ba4`
- `0x180014d28`
- `0x180015680`

## import_xrefs

- `msvcrt!sscanf_s` at `0x180014e4e`
- `msvcrt!sscanf_s` at `0x180014e4e`
- `msvcrt!atol` at `0x180014dd6`
- `msvcrt!atol` at `0x180014dd6`
- `OLEAUT32!__imp_SysAllocString` at `0x180014d53`
- `OLEAUT32!__imp_SysAllocString` at `0x180014d53`

## pseudocode

```c
__int64 __fastcall CObjectPathParser::key_const(CObjectPathParser *this)
{
  int v1; // eax
  BSTR v3; // rcx
  const wchar_t *v5; // r9
  unsigned __int64 v6; // rax
  const wchar_t *v7; // r9
  unsigned __int64 v8; // rax
  int v9; // [rsp+20h] [rbp-38h] BYREF
  char String[32]; // [rsp+28h] [rbp-30h] BYREF

  v1 = *((_DWORD *)this + 2);
  switch ( v1 )
  {
    case 'e':
      v3 = SysAllocString(**((const OLECHAR ***)this + 2));
      if ( !v3 )
        return 3;
      *(_WORD *)(*((_QWORD *)this + 4) + 8LL) = 8;
      *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = v3;
      break;
    case 'f':
      *(_WORD *)(*((_QWORD *)this + 4) + 8LL) = 3;
      v5 = (const wchar_t *)**((_QWORD **)this + 2);
      if ( !v5 )
        return 1;
      v6 = -1;
      do
        ++v6;
      while ( v5[v6] );
      if ( v6 > 0x1F )
        return 1;
      StringCchPrintfA(String, 0x20u, "%S", v5);
      *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = atol(String);
      break;
    case 'g':
      *(_WORD *)(*((_QWORD *)this + 4) + 8LL) = 3;
      v7 = (const wchar_t *)**((_QWORD **)this + 2);
      if ( !v7 )
        return 1;
      v8 = -1;
      do
        ++v8;
      while ( v7[v8] );
      if ( v8 > 0x1F )
        return 1;
      StringCchPrintfA(String, 0x20u, "%S", v7);
      v9 = 0;
      sscanf_s(String, "%x", &v9);
      *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = v9;
      break;
    case 'd':
      if ( (unsigned int)wbem_wcsicmp(**((const unsigned __int16 ***)this + 2), L"TRUE") )
      {
        if ( (unsigned int)wbem_wcsicmp(**((const unsigned __int16 ***)this + 2), L"FALSE") )
          return 1;
        *(_WORD *)(*((_QWORD *)this + 4) + 8LL) = 3;
        *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = 0;
      }
      else
      {
        *(_WORD *)(*((_QWORD *)this + 4) + 8LL) = 3;
        *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = 1;
      }
      break;
    default:
      return 1;
  }
  return !(unsigned int)CObjectPathParser::NextToken(this);
}

```

## disassembly

```asm
0x180014d28  mov     [rsp+arg_8], rbx
0x180014d2d  push    rdi
0x180014d2e  sub     rsp, 50h
0x180014d32  mov     rax, cs:__security_cookie
0x180014d39  xor     rax, rsp
0x180014d3c  mov     [rsp+58h+var_10], rax
0x180014d41  mov     eax, [rcx+8]
0x180014d44  mov     rbx, rcx
0x180014d47  cmp     eax, 65h ; 'e'
0x180014d4a  jnz     short loc_180014D82
0x180014d4c  mov     rcx, [rcx+10h]
0x180014d50  mov     rcx, [rcx]; psz
0x180014d53  call    cs:__imp_SysAllocString
0x180014d59  mov     rcx, rax
0x180014d5c  test    rax, rax
0x180014d5f  jz      short loc_180014D78
0x180014d61  mov     rax, [rbx+20h]
0x180014d65  mov     word ptr [rax+8], 8
0x180014d6b  mov     rax, [rbx+20h]
0x180014d6f  mov     [rax+10h], rcx
0x180014d73  jmp     loc_180014EBE
0x180014d78  mov     eax, 3
0x180014d7d  jmp     loc_180014ED3
0x180014d82  cmp     eax, 66h ; 'f'
0x180014d85  jnz     short loc_180014DEA
0x180014d87  mov     rax, [rcx+20h]
0x180014d8b  xor     edi, edi
0x180014d8d  mov     word ptr [rax+8], 3
0x180014d93  mov     rax, [rcx+10h]
0x180014d97  mov     r9, [rax]
0x180014d9a  test    r9, r9
0x180014d9d  jz      loc_180014ECE
0x180014da3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014da7  inc     rax
0x180014daa  cmp     [r9+rax*2], di
0x180014daf  jnz     short loc_180014DA7
0x180014db1  cmp     rax, 1Fh
0x180014db5  ja      loc_180014ECE
0x180014dbb  lea     r8, aS; "%S"
0x180014dc2  mov     edx, 20h ; ' '; unsigned __int64
0x180014dc7  lea     rcx, [rsp+58h+String]; char *
0x180014dcc  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180014dd1  lea     rcx, [rsp+58h+String]; String
0x180014dd6  call    cs:__imp_atol
0x180014ddc  mov     ecx, eax
0x180014dde  mov     rax, [rbx+20h]
0x180014de2  mov     [rax+10h], ecx
0x180014de5  jmp     loc_180014EBE
0x180014dea  cmp     eax, 67h ; 'g'
0x180014ded  jnz     short loc_180014E61
0x180014def  mov     rax, [rcx+20h]
0x180014df3  xor     edi, edi
0x180014df5  mov     word ptr [rax+8], 3
0x180014dfb  mov     rax, [rcx+10h]
0x180014dff  mov     r9, [rax]
0x180014e02  test    r9, r9
0x180014e05  jz      loc_180014ECE
0x180014e0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014e0f  inc     rax
0x180014e12  cmp     [r9+rax*2], di
0x180014e17  jnz     short loc_180014E0F
0x180014e19  cmp     rax, 1Fh
0x180014e1d  ja      loc_180014ECE
0x180014e23  lea     r8, aS; "%S"
0x180014e2a  mov     edx, 20h ; ' '; unsigned __int64
0x180014e2f  lea     rcx, [rsp+58h+String]; char *
0x180014e34  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180014e39  lea     r8, [rsp+58h+var_38]
0x180014e3e  mov     [rsp+58h+var_38], edi
0x180014e42  lea     rdx, Format; "%x"
0x180014e49  lea     rcx, [rsp+58h+String]; Buffer
0x180014e4e  call    cs:__imp_sscanf_s
0x180014e54  mov     rcx, [rbx+20h]
0x180014e58  mov     eax, [rsp+58h+var_38]
0x180014e5c  mov     [rcx+10h], eax
0x180014e5f  jmp     short loc_180014EBE
0x180014e61  cmp     eax, 64h ; 'd'
0x180014e64  jnz     short loc_180014ECE
0x180014e66  mov     rcx, [rcx+10h]
0x180014e6a  lea     rdx, aTrue; "TRUE"
0x180014e71  mov     rcx, [rcx]; unsigned __int16 *
0x180014e74  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180014e79  xor     edi, edi
0x180014e7b  test    eax, eax
0x180014e7d  jnz     short loc_180014E96
0x180014e7f  mov     rax, [rbx+20h]
0x180014e83  mov     word ptr [rax+8], 3
0x180014e89  mov     rax, [rbx+20h]
0x180014e8d  mov     dword ptr [rax+10h], 1
0x180014e94  jmp     short loc_180014EBE
0x180014e96  mov     rcx, [rbx+10h]
0x180014e9a  lea     rdx, aFalse; "FALSE"
0x180014ea1  mov     rcx, [rcx]; unsigned __int16 *
0x180014ea4  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180014ea9  test    eax, eax
0x180014eab  jnz     short loc_180014ECE
0x180014ead  mov     rax, [rbx+20h]
0x180014eb1  mov     word ptr [rax+8], 3
0x180014eb7  mov     rax, [rbx+20h]
0x180014ebb  mov     [rax+10h], edi
0x180014ebe  mov     rcx, rbx; this
0x180014ec1  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x180014ec6  test    eax, eax
0x180014ec8  jz      short loc_180014ECE
0x180014eca  xor     eax, eax
0x180014ecc  jmp     short loc_180014ED3
0x180014ece  mov     eax, 1
0x180014ed3  mov     rcx, [rsp+58h+var_10]
0x180014ed8  xor     rcx, rsp; StackCookie
0x180014edb  call    __security_check_cookie
0x180014ee0  mov     rbx, [rsp+58h+arg_8]
0x180014ee5  add     rsp, 50h
0x180014ee9  pop     rdi
0x180014eea  retn
```
