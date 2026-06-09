# CScriptBlock::Create(CScriptFile *,CScriptingEngine *,ulong,ulong,CScriptBlock * *)

- ea: `0x140011954`
- end: `0x140011a2b`
- name: `?Create@CScriptBlock@@SAJPEAVCScriptFile@@PEAVCScriptingEngine@@KKPEAPEAV1@@Z`
- size: `215`
- prototype: `__int64 __fastcall(struct CScriptFile *, struct CScriptingEngine *, unsigned int, unsigned int, struct CScriptBlock **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d190`

## callees

- `0x140001008`
- `0x140011954`

## pseudocode

```c
__int64 __fastcall CScriptBlock::Create(
        struct CScriptFile *a1,
        struct CScriptingEngine *a2,
        int a3,
        int a4,
        struct CScriptBlock **a5)
{
  _DWORD *v9; // rax
  _DWORD *v10; // rdx
  __int64 result; // rax

  if ( !a1 || !a2 || !a5 )
    return 2147500035LL;
  v9 = operator new(0x58u);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  v9[12] = 1;
  *((_QWORD *)v9 + 1) = &IPrivateDocumentContext::`vftable';
  *((_QWORD *)v9 + 2) = &CUnknown::`vftable';
  *((_QWORD *)v9 + 5) = &CUnknown::InnerUnknown::`vftable';
  *((_QWORD *)v9 + 3) = v9 + 10;
  *((_QWORD *)v9 + 4) = v9;
  _InterlockedIncrement(&Global::g_cObjects);
  *(_QWORD *)v9 = &CScriptBlock::`vftable'{for `IDebugDocumentContext'};
  *((_QWORD *)v9 + 1) = &CScriptBlock::`vftable'{for `IPrivateDocumentContext'};
  *((_QWORD *)v9 + 2) = &CScriptBlock::`vftable'{for `CUnknown'};
  v9[20] = a3 + a4;
  result = 0;
  *((_QWORD *)v10 + 7) = a1;
  *((_QWORD *)v10 + 8) = a2;
  v10[18] = a3;
  v10[19] = a4;
  *a5 = (struct CScriptBlock *)v10;
  return result;
}

```

## disassembly

```asm
0x140011954  push    rbx
0x140011956  push    rbp
0x140011957  push    rsi
0x140011958  push    rdi
0x140011959  push    r14
0x14001195b  sub     rsp, 20h
0x14001195f  mov     ebp, r9d
0x140011962  mov     r14d, r8d
0x140011965  mov     rdi, rdx
0x140011968  mov     rsi, rcx
0x14001196b  test    rcx, rcx
0x14001196e  jz      loc_140011A1B
0x140011974  test    rdx, rdx
0x140011977  jz      loc_140011A1B
0x14001197d  mov     rbx, [rsp+48h+arg_20]
0x140011982  test    rbx, rbx
0x140011985  jz      loc_140011A1B
0x14001198b  mov     ecx, 58h ; 'X'; Size
0x140011990  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140011995  mov     rdx, rax
0x140011998  test    rax, rax
0x14001199b  jz      short loc_140011A14
0x14001199d  lea     rcx, [rdx+28h]
0x1400119a1  lea     rax, ??_7IPrivateDocumentContext@@6B@; const IPrivateDocumentContext::`vftable'
0x1400119a8  mov     dword ptr [rcx+8], 1
0x1400119af  mov     [rdx+8], rax
0x1400119b3  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x1400119ba  mov     [rdx+10h], rax
0x1400119be  lea     rax, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x1400119c5  mov     [rcx], rax
0x1400119c8  mov     [rdx+18h], rcx
0x1400119cc  mov     [rdx+20h], rdx
0x1400119d0  lock inc cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x1400119d7  lea     rax, ??_7CScriptBlock@@6BIDebugDocumentContext@@@; const CScriptBlock::`vftable'{for `IDebugDocumentContext'}
0x1400119de  mov     [rdx], rax
0x1400119e1  lea     rax, ??_7CScriptBlock@@6BIPrivateDocumentContext@@@; const CScriptBlock::`vftable'{for `IPrivateDocumentContext'}
0x1400119e8  mov     [rdx+8], rax
0x1400119ec  lea     rax, ??_7CScriptBlock@@6BCUnknown@@@; const CScriptBlock::`vftable'{for `CUnknown'}
0x1400119f3  mov     [rdx+10h], rax
0x1400119f7  lea     eax, [r14+rbp]
0x1400119fb  mov     [rdx+50h], eax
0x1400119fe  xor     eax, eax
0x140011a00  mov     [rdx+38h], rsi
0x140011a04  mov     [rdx+40h], rdi
0x140011a08  mov     [rdx+48h], r14d
0x140011a0c  mov     [rdx+4Ch], ebp
0x140011a0f  mov     [rbx], rdx
0x140011a12  jmp     short loc_140011A20
0x140011a14  mov     eax, 8007000Eh
0x140011a19  jmp     short loc_140011A20
0x140011a1b  mov     eax, 80004003h
0x140011a20  add     rsp, 20h
0x140011a24  pop     r14
0x140011a26  pop     rdi
0x140011a27  pop     rsi
0x140011a28  pop     rbp
0x140011a29  pop     rbx
0x140011a2a  retn
```
