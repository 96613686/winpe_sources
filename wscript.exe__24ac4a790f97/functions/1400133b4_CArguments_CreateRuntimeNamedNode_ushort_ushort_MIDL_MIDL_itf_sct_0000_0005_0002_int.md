# CArguments::CreateRuntimeNamedNode(ushort *,ushort *,__MIDL___MIDL_itf_sct_0000_0005_0002,int)

- ea: `0x1400133b4`
- end: `0x14001347b`
- name: `?CreateRuntimeNamedNode@CArguments@@AEAAPEAURuntimeNode@@PEAG0W4__MIDL___MIDL_itf_sct_0000_0005_0002@@H@Z`
- size: `199`
- prototype: `struct RuntimeNode *__high(unsigned __int16 *, unsigned __int16 *, enum __MIDL___MIDL_itf_sct_0000_0005_0002, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011dd0`

## callees

- `0x140001464`
- `0x14000147c`
- `0x1400133b4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140013401`
- `OLEAUT32!__imp_SysAllocString` at `0x140013426`
- `OLEAUT32!__imp_SysAllocString` at `0x140013401`
- `OLEAUT32!__imp_SysAllocString` at `0x140013426`
- `OLEAUT32!__imp_SysFreeString` at `0x140013441`
- `OLEAUT32!__imp_SysFreeString` at `0x14001344f`
- `OLEAUT32!__imp_SysFreeString` at `0x140013441`
- `OLEAUT32!__imp_SysFreeString` at `0x14001344f`
- `OLEAUT32!__imp_SysStringLen` at `0x1400133f4`
- `OLEAUT32!__imp_SysStringLen` at `0x140013419`
- `OLEAUT32!__imp_SysStringLen` at `0x1400133f4`
- `OLEAUT32!__imp_SysStringLen` at `0x140013419`

## pseudocode

```c
void *__fastcall CArguments::CreateRuntimeNamedNode(__int64 a1, OLECHAR *a2, OLECHAR *a3, int a4, int a5)
{
  void *v8; // rbx
  void *result; // rax
  BSTR v10; // rax
  OLECHAR *v11; // rdi
  BSTR v12; // rax
  OLECHAR *v13; // rcx

  v8 = malloc_0(0x28u);
  if ( !v8 )
    return 0;
  *(_OWORD *)v8 = 0;
  *((_OWORD *)v8 + 1) = 0;
  *((_QWORD *)v8 + 4) = 0;
  if ( SysStringLen(a2) )
  {
    v10 = SysAllocString(a2);
    *((_QWORD *)v8 + 2) = v10;
    if ( !v10 )
    {
      v11 = (OLECHAR *)*((_QWORD *)v8 + 3);
LABEL_8:
      v13 = (OLECHAR *)*((_QWORD *)v8 + 2);
      if ( v13 )
        SysFreeString(v13);
      if ( v11 )
        SysFreeString(v11);
      free_0(v8);
      return 0;
    }
  }
  if ( SysStringLen(a3) )
  {
    v12 = SysAllocString(a3);
    *((_QWORD *)v8 + 3) = v12;
    v11 = v12;
    if ( !v12 )
      goto LABEL_8;
  }
  *((_DWORD *)v8 + 8) = a5;
  result = v8;
  *((_DWORD *)v8 + 9) = a4;
  return result;
}

```

## disassembly

```asm
0x1400133b4  push    rbx
0x1400133b6  push    rbp
0x1400133b7  push    rsi
0x1400133b8  push    rdi
0x1400133b9  push    r14
0x1400133bb  sub     rsp, 20h
0x1400133bf  mov     ecx, 28h ; '('; Size
0x1400133c4  mov     r14d, r9d
0x1400133c7  mov     rdi, r8
0x1400133ca  mov     rbp, rdx
0x1400133cd  call    malloc_0
0x1400133d2  mov     rbx, rax
0x1400133d5  test    rax, rax
0x1400133d8  jnz     short loc_1400133E1
0x1400133da  xor     eax, eax
0x1400133dc  jmp     loc_140013470
0x1400133e1  xorps   xmm0, xmm0
0x1400133e4  xor     eax, eax
0x1400133e6  movups  xmmword ptr [rbx], xmm0
0x1400133e9  mov     rcx, rbp; pbstr
0x1400133ec  movups  xmmword ptr [rbx+10h], xmm0
0x1400133f0  mov     [rbx+20h], rax
0x1400133f4  call    cs:__imp_SysStringLen
0x1400133fa  test    eax, eax
0x1400133fc  jz      short loc_140013416
0x1400133fe  mov     rcx, rbp; psz
0x140013401  call    cs:__imp_SysAllocString
0x140013407  mov     [rbx+10h], rax
0x14001340b  test    rax, rax
0x14001340e  jnz     short loc_140013416
0x140013410  mov     rdi, [rbx+18h]
0x140013414  jmp     short loc_140013438
0x140013416  mov     rcx, rdi; pbstr
0x140013419  call    cs:__imp_SysStringLen
0x14001341f  test    eax, eax
0x140013421  jz      short loc_140013462
0x140013423  mov     rcx, rdi; psz
0x140013426  call    cs:__imp_SysAllocString
0x14001342c  mov     [rbx+18h], rax
0x140013430  mov     rdi, rax
0x140013433  test    rax, rax
0x140013436  jnz     short loc_140013462
0x140013438  mov     rcx, [rbx+10h]; bstrString
0x14001343c  test    rcx, rcx
0x14001343f  jz      short loc_140013447
0x140013441  call    cs:__imp_SysFreeString
0x140013447  test    rdi, rdi
0x14001344a  jz      short loc_140013455
0x14001344c  mov     rcx, rdi; bstrString
0x14001344f  call    cs:__imp_SysFreeString
0x140013455  mov     rcx, rbx; Block
0x140013458  call    free_0
0x14001345d  jmp     loc_1400133DA
0x140013462  mov     eax, [rsp+48h+arg_20]
0x140013466  mov     [rbx+20h], eax
0x140013469  mov     rax, rbx
0x14001346c  mov     [rbx+24h], r14d
0x140013470  add     rsp, 20h
0x140013474  pop     r14
0x140013476  pop     rdi
0x140013477  pop     rsi
0x140013478  pop     rbp
0x140013479  pop     rbx
0x14001347a  retn
```
