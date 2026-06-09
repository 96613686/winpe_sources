# CWbemPathCracker::GetNamespacePath(ATL::CComBSTR &,bool)

- ea: `0x180010794`
- end: `0x1800109c3`
- name: `?GetNamespacePath@CWbemPathCracker@@QEAA_NAEAVCComBSTR@ATL@@_N@Z`
- size: `559`
- prototype: `bool __fastcall(CWbemPathCracker *__hidden this, struct ATL::CComBSTR *, bool)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e9a0`
- `0x1800201f0`
- `0x18002eba0`
- `0x18002ec30`

## callees

- `0x180010794`
- `0x1800109cc`
- `0x180036010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180010982`
- `msvcrt!wcsrchr` at `0x180010993`
- `msvcrt!wcsrchr` at `0x180010982`
- `msvcrt!wcsrchr` at `0x180010993`
- `msvcrt!wcschr` at `0x18001095e`
- `msvcrt!wcschr` at `0x18001095e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001089b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800108e4`
- `OLEAUT32!__imp_SysAllocString` at `0x180010926`
- `OLEAUT32!__imp_SysAllocString` at `0x18001093c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001089b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800108e4`
- `OLEAUT32!__imp_SysAllocString` at `0x180010926`
- `OLEAUT32!__imp_SysAllocString` at `0x18001093c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800108f4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800108f4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001085b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001085b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800108ba`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800108ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CWbemPathCracker::GetNamespacePath(CWbemPathCracker *this, struct ATL::CComBSTR *a2, char a3)
{
  char v6; // r14
  __int64 v7; // rcx
  wchar_t *v8; // rbx
  __int64 v9; // rcx
  OLECHAR *v10; // rax
  OLECHAR *v11; // r15
  bool v12; // si
  wchar_t *v14; // rcx
  wchar_t *v15; // rdi
  wchar_t *v16; // rax
  int v17; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v18; // [rsp+98h] [rbp+58h] BYREF

  v6 = 0;
  v18 = 0;
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v7 = *((_QWORD *)this + 1);
    if ( v7 )
    {
      if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v7 + 64LL))(v7, &v18) >= 0 )
      {
        if ( a3 )
        {
          if ( v18 > 1 )
          {
LABEL_6:
            v8 = 0;
            if ( *((_DWORD *)this + 7) != 1 )
              goto LABEL_17;
            v9 = *((_QWORD *)this + 1);
            if ( !v9 )
              goto LABEL_17;
            v17 = 0;
            (*(void (__fastcall **)(__int64, __int64, int *, _QWORD))(*(_QWORD *)v9 + 32LL))(v9, 16, &v17, 0);
            if ( v17 )
            {
              v10 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v17 + 1), 2u));
              v11 = v10;
              if ( !v10 )
                goto LABEL_17;
              v12 = 0;
              v10[v17] = 0;
              if ( (*(int (__fastcall **)(_QWORD, __int64, int *, OLECHAR *))(**((_QWORD **)this + 1) + 32LL))(
                     *((_QWORD *)this + 1),
                     16,
                     &v17,
                     v10) >= 0 )
              {
                v8 = SysAllocString(v11);
                v12 = v8 != 0;
              }
              CWin32DefaultArena::WbemMemFree(v11);
            }
            else
            {
              v8 = SysAllocString(&SystemName);
              if ( !v8 )
                goto LABEL_17;
              v12 = 1;
            }
            if ( v12 )
            {
              if ( CWbemPathCracker::IsClassOrInstance(this) )
              {
                v14 = wcschr(v8, 0x3Au);
                if ( v14 )
                  *v14 = 0;
              }
              if ( !a3 )
                goto LABEL_16;
              v15 = wcsrchr(v8, 0x2Fu);
              v16 = wcsrchr(v8, 0x5Cu);
              if ( v15 )
              {
                if ( v16 && v15 < v16 )
                  v15 = v16;
              }
              else
              {
                if ( !v16 )
                {
LABEL_16:
                  *(_QWORD *)a2 = SysAllocString(v8);
                  v6 = 1;
                  goto LABEL_17;
                }
                v15 = v16;
              }
              *v15 = 0;
              goto LABEL_16;
            }
LABEL_17:
            SysFreeString(v8);
            return v6;
          }
        }
        else if ( v18 )
        {
          goto LABEL_6;
        }
        *(_QWORD *)a2 = SysAllocString(&SystemName);
        return 1;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180010794  mov     [rsp-38h+arg_8], rbx
0x180010799  push    rbp
0x18001079a  push    rsi
0x18001079b  push    rdi
0x18001079c  push    r12
0x18001079e  push    r13
0x1800107a0  push    r14
0x1800107a2  push    r15
0x1800107a4  mov     rbp, rsp
0x1800107a7  sub     rsp, 40h
0x1800107ab  mov     r12b, r8b
0x1800107ae  mov     r13, rdx
0x1800107b1  mov     rdi, rcx
0x1800107b4  xor     r14b, r14b
0x1800107b7  mov     [rbp+arg_18], 0
0x1800107be  cmp     dword ptr [rcx+1Ch], 1
0x1800107c2  jnz     loc_1800108FA
0x1800107c8  mov     rcx, [rcx+8]
0x1800107cc  test    rcx, rcx
0x1800107cf  jz      loc_1800108FA
0x1800107d5  mov     rax, [rcx]
0x1800107d8  lea     rdx, [rbp+arg_18]
0x1800107dc  mov     rax, [rax+40h]
0x1800107e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107e5  test    eax, eax
0x1800107e7  js      loc_1800108FA
0x1800107ed  mov     r15d, 1
0x1800107f3  test    r12b, r12b
0x1800107f6  jz      loc_180010915
0x1800107fc  cmp     [rbp+arg_18], r15d
0x180010800  jbe     loc_18001091F
0x180010806  xor     ebx, ebx
0x180010808  mov     [rbp+var_10], rbx
0x18001080c  cmp     dword ptr [rdi+1Ch], 1
0x180010810  jnz     loc_1800108F1
0x180010816  mov     rcx, [rdi+8]
0x18001081a  test    rcx, rcx
0x18001081d  jz      loc_1800108F1
0x180010823  mov     [rbp+arg_0], ebx
0x180010826  mov     rax, [rcx]
0x180010829  xor     r9d, r9d
0x18001082c  lea     r8, [rbp+arg_0]
0x180010830  lea     edx, [rbx+10h]
0x180010833  mov     rax, [rax+20h]
0x180010837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001083c  mov     eax, [rbp+arg_0]
0x18001083f  test    eax, eax
0x180010841  jz      loc_180010935
0x180010847  lea     ecx, [rax+1]
0x18001084a  lea     eax, [rbx+2]
0x18001084d  mul     rcx
0x180010850  lea     rcx, [rbx-1]
0x180010854  cmovb   rax, rcx
0x180010858  mov     rcx, rax
0x18001085b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010861  mov     r15, rax
0x180010864  test    rax, rax
0x180010867  jz      loc_1800108F1
0x18001086d  xor     sil, sil
0x180010870  mov     ecx, [rbp+arg_0]
0x180010873  xor     eax, eax
0x180010875  mov     [r15+rcx*2], ax
0x18001087a  mov     rcx, [rdi+8]
0x18001087e  mov     rax, [rcx]
0x180010881  mov     r9, r15
0x180010884  lea     r8, [rbp+arg_0]
0x180010888  lea     edx, [rbx+10h]
0x18001088b  mov     rax, [rax+20h]
0x18001088f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010894  test    eax, eax
0x180010896  js      short loc_1800108B7
0x180010898  mov     rcx, r15; psz
0x18001089b  call    cs:__imp_SysAllocString
0x1800108a1  mov     rbx, rax
0x1800108a4  mov     [rbp+var_10], rax
0x1800108a8  movzx   esi, sil
0x1800108ac  test    rax, rax
0x1800108af  mov     eax, 1
0x1800108b4  cmovnz  esi, eax
0x1800108b7  mov     rcx, r15
0x1800108ba  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800108c0  nop
0x1800108c1  mov     r15d, 1
0x1800108c7  test    sil, sil
0x1800108ca  jz      short loc_1800108F1
0x1800108cc  mov     rcx, rdi; this
0x1800108cf  call    ?IsClassOrInstance@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsClassOrInstance(void)
0x1800108d4  test    al, al
0x1800108d6  jnz     short loc_180010956
0x1800108d8  test    r12b, r12b
0x1800108db  jnz     loc_18001097A
0x1800108e1  mov     rcx, rbx; psz
0x1800108e4  call    cs:__imp_SysAllocString
0x1800108ea  mov     [r13+0], rax
0x1800108ee  mov     r14b, r15b
0x1800108f1  mov     rcx, rbx; bstrString
0x1800108f4  call    cs:__imp_SysFreeString
0x1800108fa  mov     al, r14b
0x1800108fd  mov     rbx, [rsp+40h+arg_8]
0x180010905  add     rsp, 40h
0x180010909  pop     r15
0x18001090b  pop     r14
0x18001090d  pop     r13
0x18001090f  pop     r12
0x180010911  pop     rdi
0x180010912  pop     rsi
0x180010913  pop     rbp
0x180010914  retn
0x180010915  cmp     [rbp+arg_18], 0
0x180010919  ja      loc_180010806
0x18001091f  lea     rcx, SystemName; psz
0x180010926  call    cs:__imp_SysAllocString
0x18001092c  mov     [r13+0], rax
0x180010930  mov     r14b, r15b
0x180010933  jmp     short loc_1800108FA
0x180010935  lea     rcx, SystemName; psz
0x18001093c  call    cs:__imp_SysAllocString
0x180010942  mov     rbx, rax
0x180010945  mov     [rbp+var_10], rax
0x180010949  test    rax, rax
0x18001094c  jz      short loc_1800108F1
0x18001094e  mov     sil, r15b
0x180010951  jmp     loc_1800108C7
0x180010956  mov     edx, 3Ah ; ':'; Ch
0x18001095b  mov     rcx, rbx; Str
0x18001095e  call    cs:__imp_wcschr
0x180010964  mov     rcx, rax
0x180010967  test    rax, rax
0x18001096a  jz      loc_1800108D8
0x180010970  xor     eax, eax
0x180010972  mov     [rcx], ax
0x180010975  jmp     loc_1800108D8
0x18001097a  mov     edx, 2Fh ; '/'; Ch
0x18001097f  mov     rcx, rbx; Str
0x180010982  call    cs:__imp_wcsrchr
0x180010988  mov     rdi, rax
0x18001098b  mov     edx, 5Ch ; '\'; Ch
0x180010990  mov     rcx, rbx; Str
0x180010993  call    cs:__imp_wcsrchr
0x180010999  test    rdi, rdi
0x18001099c  jz      short loc_1800109AC
0x18001099e  test    rax, rax
0x1800109a1  jz      short loc_1800109B8
0x1800109a3  cmp     rdi, rax
0x1800109a6  cmovb   rdi, rax
0x1800109aa  jmp     short loc_1800109B8
0x1800109ac  test    rax, rax
0x1800109af  jz      loc_1800108E1
0x1800109b5  mov     rdi, rax
0x1800109b8  xor     eax, eax
0x1800109ba  mov     [rdi], ax
0x1800109bd  jmp     loc_1800108E1
```
