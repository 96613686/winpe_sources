# CThreadInfo::GetAllTheText(XInterface<ITextDocument> &,CAllRuns *)

- ea: `0x180011cd8`
- end: `0x180011e54`
- name: `?GetAllTheText@CThreadInfo@@AEAAJAEAV?$XInterface@UITextDocument@@@@PEAVCAllRuns@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180010f28`

## callees

- `0x180011cd8`
- `0x18001929c`
- `0x1800193d4`
- `0x18001b010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011e00`
- `OLEAUT32!__imp_SysFreeString` at `0x180011e00`

## pseudocode

```c
__int64 __fastcall CThreadInfo::GetAllTheText(__int64 a1, _QWORD *a2, __int64 a3)
{
  int v5; // ebx
  int v6; // esi
  int v7; // eax
  __int64 v8; // rcx
  unsigned int v10; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+38h] [rbp-18h] BYREF
  BSTR bstrString[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v13; // [rsp+80h] [rbp+30h] BYREF
  int v14; // [rsp+88h] [rbp+38h] BYREF
  int v15; // [rsp+98h] [rbp+48h] BYREF

  v13 = a1;
  v14 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a2 + 72LL))(*a2, &v14);
  if ( v5 < 0 )
    return (unsigned int)-2147215613;
  if ( v14 == 1 )
  {
    v11 = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)*a2 + 192LL))(*a2, 0, 0, &v11);
    if ( v5 >= 0 )
    {
      v15 = 0;
      v6 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 176LL))(v11, &v15);
      while ( 1 )
      {
        v5 = v7;
        if ( v7 < 0 )
          break;
        if ( v6 >= v15 )
        {
          if ( *(_DWORD *)(a3 + 8) )
          {
            v5 = 0;
            *(_QWORD *)(a3 + 24) = 0;
            *(_DWORD *)(a3 + 8) = 0;
            *(_QWORD *)(a3 + 16) = 0;
          }
          else
          {
            v5 = -2147467259;
          }
          break;
        }
        LODWORD(v13) = 0;
        v10 = 0;
        v5 = IAdvancedTextRange::MoveEndForLCID((IAdvancedTextRange *)&v11, v6, v15, (int *)&v13, (int *)&v10);
        if ( v5 < 0 )
          break;
        bstrString[0] = 0;
        v5 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v11 + 56LL))(v11, bstrString);
        if ( v5 < 0 )
          break;
        v5 = CAllRuns::Add((CAllRuns *)a3, v13, bstrString[0], v10);
        if ( v5 < 0 )
        {
          SysFreeString(bstrString[0]);
          break;
        }
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, 0);
        v6 += v13;
      }
    }
    v8 = v11;
    v11 = 0;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v5 < 0 )
      return (unsigned int)-2147215613;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180011cd8  mov     [rsp-28h+arg_0], rcx
0x180011cdd  push    rbp
0x180011cde  push    rbx
0x180011cdf  push    rsi
0x180011ce0  push    rdi
0x180011ce1  push    r14
0x180011ce3  mov     rbp, rsp
0x180011ce6  sub     rsp, 50h
0x180011cea  mov     rdi, r8
0x180011ced  mov     rsi, rdx
0x180011cf0  xor     r14d, r14d
0x180011cf3  mov     [rbp+arg_8], r14d
0x180011cf7  mov     rcx, [rdx]
0x180011cfa  mov     rax, [rcx]
0x180011cfd  lea     rdx, [rbp+arg_8]
0x180011d01  mov     rax, [rax+48h]
0x180011d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d0a  mov     ebx, eax
0x180011d0c  test    eax, eax
0x180011d0e  js      loc_180011E42
0x180011d14  cmp     [rbp+arg_8], 1
0x180011d18  jnz     loc_180011E47
0x180011d1e  mov     [rbp+var_18], r14
0x180011d22  mov     rcx, [rsi]
0x180011d25  mov     rax, [rcx]
0x180011d28  lea     r9, [rbp+var_18]
0x180011d2c  xor     r8d, r8d
0x180011d2f  xor     edx, edx
0x180011d31  mov     rax, [rax+0C0h]
0x180011d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d3d  mov     ebx, eax
0x180011d3f  test    eax, eax
0x180011d41  js      loc_180011E24
0x180011d47  mov     [rbp+arg_18], r14d
0x180011d4b  mov     esi, r14d
0x180011d4e  mov     rcx, [rbp+var_18]
0x180011d52  mov     rax, [rcx]
0x180011d55  lea     rdx, [rbp+arg_18]
0x180011d59  mov     rax, [rax+0B0h]
0x180011d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d65  jmp     loc_180011DF0
0x180011d6a  mov     r8d, [rbp+arg_18]; int
0x180011d6e  cmp     esi, r8d
0x180011d71  jge     loc_180011E08
0x180011d77  mov     dword ptr [rbp+arg_0], r14d
0x180011d7b  mov     [rbp+var_20], r14d
0x180011d7f  lea     rax, [rbp+var_20]
0x180011d83  mov     [rsp+50h+var_30], rax; int *
0x180011d88  lea     r9, [rbp+arg_0]; int *
0x180011d8c  mov     edx, esi; int
0x180011d8e  lea     rcx, [rbp+var_18]; this
0x180011d92  call    ?MoveEndForLCID@IAdvancedTextRange@@QEAAJJJPEAJ0@Z; IAdvancedTextRange::MoveEndForLCID(long,long,long *,long *)
0x180011d97  mov     ebx, eax
0x180011d99  test    eax, eax
0x180011d9b  js      loc_180011E24
0x180011da1  mov     [rbp+bstrString], r14
0x180011da5  mov     rcx, [rbp+var_18]
0x180011da9  mov     rax, [rcx]
0x180011dac  lea     rdx, [rbp+bstrString]
0x180011db0  mov     rax, [rax+38h]
0x180011db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011db9  mov     ebx, eax
0x180011dbb  test    eax, eax
0x180011dbd  js      short loc_180011E24
0x180011dbf  mov     r9d, [rbp+var_20]; unsigned int
0x180011dc3  mov     r8, [rbp+bstrString]; wchar_t *
0x180011dc7  mov     edx, dword ptr [rbp+arg_0]; int
0x180011dca  mov     rcx, rdi; this
0x180011dcd  call    ?Add@CAllRuns@@QEAAJJPEA_WK@Z; CAllRuns::Add(long,wchar_t *,ulong)
0x180011dd2  mov     ebx, eax
0x180011dd4  test    eax, eax
0x180011dd6  js      short loc_180011DFC
0x180011dd8  mov     rcx, [rbp+var_18]
0x180011ddc  mov     rax, [rcx]
0x180011ddf  xor     edx, edx
0x180011de1  mov     rax, [rax+0C0h]
0x180011de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ded  add     esi, dword ptr [rbp+arg_0]
0x180011df0  test    eax, eax
0x180011df2  mov     ebx, eax
0x180011df4  jns     loc_180011D6A
0x180011dfa  jmp     short loc_180011E24
0x180011dfc  mov     rcx, [rbp+bstrString]; bstrString
0x180011e00  call    cs:__imp_SysFreeString
0x180011e06  jmp     short loc_180011E24
0x180011e08  cmp     [rdi+8], r14d
0x180011e0c  jz      short loc_180011E1F
0x180011e0e  mov     ebx, r14d
0x180011e11  mov     [rdi+18h], r14
0x180011e15  mov     [rdi+8], r14d
0x180011e19  mov     [rdi+10h], r14
0x180011e1d  jmp     short loc_180011E24
0x180011e1f  mov     ebx, 80004005h
0x180011e24  mov     rcx, [rbp+var_18]
0x180011e28  mov     [rbp+var_18], r14
0x180011e2c  test    rcx, rcx
0x180011e2f  jz      short loc_180011E3E
0x180011e31  mov     rax, [rcx]
0x180011e34  mov     rax, [rax+10h]
0x180011e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e3d  nop
0x180011e3e  test    ebx, ebx
0x180011e40  jns     short loc_180011E47
0x180011e42  mov     ebx, 80041703h
0x180011e47  mov     eax, ebx
0x180011e49  add     rsp, 50h
0x180011e4d  pop     r14
0x180011e4f  pop     rdi
0x180011e50  pop     rsi
0x180011e51  pop     rbx
0x180011e52  pop     rbp
0x180011e53  retn
```
