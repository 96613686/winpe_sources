# CArguments::CreateRuntimeUnnamedNode(ushort *,ushort *,int,ulong)

- ea: `0x140013484`
- end: `0x140013551`
- name: `?CreateRuntimeUnnamedNode@CArguments@@AEAAPEAURuntimeNode@@PEAG0HK@Z`
- size: `205`
- prototype: `struct RuntimeNode *(CArguments *__hidden this, unsigned __int16 *, unsigned __int16 *, int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011e30`

## callees

- `0x140001464`
- `0x14000147c`
- `0x140013484`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400134d7`
- `OLEAUT32!__imp_SysAllocString` at `0x1400134fc`
- `OLEAUT32!__imp_SysAllocString` at `0x1400134d7`
- `OLEAUT32!__imp_SysAllocString` at `0x1400134fc`
- `OLEAUT32!__imp_SysFreeString` at `0x140013517`
- `OLEAUT32!__imp_SysFreeString` at `0x140013525`
- `OLEAUT32!__imp_SysFreeString` at `0x140013517`
- `OLEAUT32!__imp_SysFreeString` at `0x140013525`
- `OLEAUT32!__imp_SysStringLen` at `0x1400134ca`
- `OLEAUT32!__imp_SysStringLen` at `0x1400134ef`
- `OLEAUT32!__imp_SysStringLen` at `0x1400134ca`
- `OLEAUT32!__imp_SysStringLen` at `0x1400134ef`

## pseudocode

```c
struct RuntimeNode *__fastcall CArguments::CreateRuntimeUnnamedNode(
        CArguments *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned int a5)
{
  void *v8; // rbx
  struct RuntimeNode *result; // rax
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
  *(_DWORD *)v8 = 1;
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
  result = (struct RuntimeNode *)v8;
  *((_DWORD *)v8 + 9) = a4;
  return result;
}

```

## disassembly

```asm
0x140013484  push    rbx
0x140013486  push    rbp
0x140013487  push    rsi
0x140013488  push    rdi
0x140013489  push    r14
0x14001348b  sub     rsp, 20h
0x14001348f  mov     ecx, 28h ; '('; Size
0x140013494  mov     r14d, r9d
0x140013497  mov     rdi, r8
0x14001349a  mov     rbp, rdx
0x14001349d  call    malloc_0
0x1400134a2  mov     rbx, rax
0x1400134a5  test    rax, rax
0x1400134a8  jnz     short loc_1400134B1
0x1400134aa  xor     eax, eax
0x1400134ac  jmp     loc_140013546
0x1400134b1  xorps   xmm0, xmm0
0x1400134b4  xor     eax, eax
0x1400134b6  movups  xmmword ptr [rbx], xmm0
0x1400134b9  mov     rcx, rbp; pbstr
0x1400134bc  movups  xmmword ptr [rbx+10h], xmm0
0x1400134c0  mov     [rbx+20h], rax
0x1400134c4  mov     dword ptr [rbx], 1
0x1400134ca  call    cs:__imp_SysStringLen
0x1400134d0  test    eax, eax
0x1400134d2  jz      short loc_1400134EC
0x1400134d4  mov     rcx, rbp; psz
0x1400134d7  call    cs:__imp_SysAllocString
0x1400134dd  mov     [rbx+10h], rax
0x1400134e1  test    rax, rax
0x1400134e4  jnz     short loc_1400134EC
0x1400134e6  mov     rdi, [rbx+18h]
0x1400134ea  jmp     short loc_14001350E
0x1400134ec  mov     rcx, rdi; pbstr
0x1400134ef  call    cs:__imp_SysStringLen
0x1400134f5  test    eax, eax
0x1400134f7  jz      short loc_140013538
0x1400134f9  mov     rcx, rdi; psz
0x1400134fc  call    cs:__imp_SysAllocString
0x140013502  mov     [rbx+18h], rax
0x140013506  mov     rdi, rax
0x140013509  test    rax, rax
0x14001350c  jnz     short loc_140013538
0x14001350e  mov     rcx, [rbx+10h]; bstrString
0x140013512  test    rcx, rcx
0x140013515  jz      short loc_14001351D
0x140013517  call    cs:__imp_SysFreeString
0x14001351d  test    rdi, rdi
0x140013520  jz      short loc_14001352B
0x140013522  mov     rcx, rdi; bstrString
0x140013525  call    cs:__imp_SysFreeString
0x14001352b  mov     rcx, rbx; Block
0x14001352e  call    free_0
0x140013533  jmp     loc_1400134AA
0x140013538  mov     eax, [rsp+48h+arg_20]
0x14001353c  mov     [rbx+20h], eax
0x14001353f  mov     rax, rbx
0x140013542  mov     [rbx+24h], r14d
0x140013546  add     rsp, 20h
0x14001354a  pop     r14
0x14001354c  pop     rdi
0x14001354d  pop     rsi
0x14001354e  pop     rbp
0x14001354f  pop     rbx
0x140013550  retn
```
