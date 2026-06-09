# CVar::FillVariant(tagVARIANT *,int)

- ea: `0x180007770`
- end: `0x180007988`
- name: `?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z`
- size: `536`
- prototype: `void __fastcall(CVar *__hidden this, struct tagVARIANT *, int)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180004ff0`
- `0x180005a80`
- `0x180007300`
- `0x1800395c0`
- `0x180039720`

## callees

- `0x1800056c0`
- `0x18000723c`
- `0x180007770`
- `0x180008cc0`
- `0x180047010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000779e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000779e`
- `OLEAUT32!__imp_VariantClear` at `0x18000790f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180007927`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180007927`

## pseudocode

```c
void __fastcall CVar::FillVariant(const OLECHAR **this, struct tagVARIANT *a2, int a3)
{
  int v3; // eax
  BSTR v5; // rax
  CVarVector **v6; // rdi
  CVarVector *v7; // rsi
  __int64 v8; // rcx
  struct tagSAFEARRAY *NewSafeArray; // rbp
  __int64 v10; // rax
  CSafeArray *v11; // rcx
  const OLECHAR *v12; // rcx

  v3 = *(_DWORD *)this;
  if ( *(_DWORD *)this == 8 )
  {
    v5 = SysAllocString(this[1]);
    if ( !v5 )
      _ThrowMemoryException_();
    a2->vt = 8;
LABEL_8:
    a2->llVal = (LONGLONG)v5;
  }
  else if ( v3 == 3 )
  {
    a2->vt = 3;
    a2->lVal = *((_DWORD *)this + 2);
  }
  else if ( v3 > 1 )
  {
    switch ( v3 )
    {
      case 2:
        a2->vt = 2;
        a2->iVal = *((_WORD *)this + 4);
        return;
      case 4:
        a2->vt = 4;
        a2->lVal = *((_DWORD *)this + 2);
        return;
      case 5:
        a2->vt = 5;
        v5 = (BSTR)this[1];
        goto LABEL_8;
      case 9:
        a2->vt = 9;
        goto LABEL_24;
      case 11:
        a2->vt = 11;
        a2->iVal = -(*((_WORD *)this + 4) != 0);
        return;
      case 13:
        a2->vt = 13;
LABEL_24:
        a2->llVal = (LONGLONG)this[1];
        v12 = this[1];
        if ( v12 )
          (*(void (__fastcall **)(const OLECHAR *))(*(_QWORD *)v12 + 8LL))(v12);
        break;
      case 17:
        a2->vt = 17;
        a2->bVal = *((_BYTE *)this + 8);
        break;
      default:
        goto LABEL_29;
    }
  }
  else if ( v3 == 1 )
  {
    a2->vt = 1;
  }
  else if ( v3 == -2147418081 )
  {
    v6 = (CVarVector **)(this + 1);
    if ( a3 && (v7 = *v6, (v8 = *((_QWORD *)*v6 + 13)) != 0) )
    {
      if ( *((_QWORD *)v7 + 14) )
      {
        SafeArrayUnaccessData(*(SAFEARRAY **)(v8 + 32));
        *((_QWORD *)v7 + 14) = 0;
      }
      v10 = *((_QWORD *)v7 + 13);
      NewSafeArray = *(struct tagSAFEARRAY **)(v10 + 32);
      *(_DWORD *)(v10 + 4) = 1;
      v11 = (CSafeArray *)*((_QWORD *)v7 + 13);
      if ( v11 )
        CSafeArray::`scalar deleting destructor'(v11, (unsigned int)a2);
      *((_QWORD *)v7 + 13) = 0;
    }
    else
    {
      NewSafeArray = CVarVector::GetNewSafeArray(*v6);
    }
    a2->llVal = (LONGLONG)NewSafeArray;
    a2->vt = *(_WORD *)*v6 | 0x2000;
  }
  else
  {
LABEL_29:
    VariantClear(a2);
  }
}

```

## disassembly

```asm
0x180007770  push    rbx
0x180007772  sub     rsp, 20h
0x180007776  mov     eax, [rcx]
0x180007778  mov     rbx, rdx
0x18000777b  mov     r9, rcx
0x18000777e  cmp     eax, 8
0x180007781  jz      short loc_18000779A
0x180007783  cmp     eax, 3
0x180007786  jz      short loc_1800077BC
0x180007788  cmp     eax, 1
0x18000778b  jg      short loc_1800077CD
0x18000778d  jnz     short loc_180007808
0x18000778f  mov     word ptr [rdx], 1
0x180007794  add     rsp, 20h
0x180007798  pop     rbx
0x180007799  retn
0x18000779a  mov     rcx, [rcx+8]; psz
0x18000779e  call    cs:__imp_SysAllocString
0x1800077a4  test    rax, rax
0x1800077a7  jz      loc_180007916
0x1800077ad  mov     word ptr [rbx], 8
0x1800077b2  mov     [rbx+8], rax
0x1800077b6  add     rsp, 20h
0x1800077ba  pop     rbx
0x1800077bb  retn
0x1800077bc  mov     word ptr [rdx], 3
0x1800077c1  mov     eax, [rcx+8]
0x1800077c4  mov     [rdx+8], eax
0x1800077c7  add     rsp, 20h
0x1800077cb  pop     rbx
0x1800077cc  retn
0x1800077cd  add     eax, 0FFFFFFFEh; switch 16 cases
0x1800077d0  cmp     eax, 0Fh
0x1800077d3  ja      def_1800077EC; jumptable 00000001800077EC default case, cases 3,6-8,10,12,14-16
0x1800077d9  lea     rdx, __ImageBase
0x1800077e0  cdqe
0x1800077e2  mov     ecx, ds:(jpt_1800077EC - 180000000h)[rdx+rax*4]
0x1800077e9  add     rcx, rdx
0x1800077ec  jmp     rcx; switch jump
0x1800077ee  mov     word ptr [rbx], 0Bh; jumptable 00000001800077EC case 11
0x1800077f3  movzx   eax, word ptr [r9+8]
0x1800077f8  neg     ax
0x1800077fb  sbb     cx, cx
0x1800077fe  mov     [rbx+8], cx
0x180007802  add     rsp, 20h
0x180007806  pop     rbx
0x180007807  retn
0x180007808  cmp     eax, 8001001Fh
0x18000780d  jnz     def_1800077EC; jumptable 00000001800077EC default case, cases 3,6-8,10,12,14-16
0x180007813  mov     [rsp+28h+arg_0], rbp
0x180007818  mov     [rsp+28h+arg_10], rdi
0x18000781d  lea     rdi, [rcx+8]
0x180007821  mov     [rsp+28h+arg_8], rsi
0x180007826  test    r8d, r8d
0x180007829  jz      short loc_180007837
0x18000782b  mov     rsi, [rdi]
0x18000782e  mov     rcx, [rsi+68h]
0x180007832  test    rcx, rcx
0x180007835  jnz     short loc_180007871
0x180007837  mov     rcx, [rdi]; this
0x18000783a  call    ?GetNewSafeArray@CVarVector@@QEAAPEAUtagSAFEARRAY@@XZ; CVarVector::GetNewSafeArray(void)
0x18000783f  mov     rbp, rax
0x180007842  mov     eax, 8
0x180007847  mov     rcx, rbx
0x18000784a  mov     ecx, 2000h
0x18000784f  mov     [rax+rbx], rbp
0x180007853  mov     rax, [rdi]
0x180007856  or      cx, [rax]
0x180007859  mov     [rbx], cx
0x18000785c  mov     rdi, [rsp+28h+arg_10]
0x180007861  mov     rsi, [rsp+28h+arg_8]
0x180007866  mov     rbp, [rsp+28h+arg_0]
0x18000786b  add     rsp, 20h
0x18000786f  pop     rbx
0x180007870  retn
0x180007871  cmp     qword ptr [rsi+70h], 0
0x180007876  jnz     loc_180007923
0x18000787c  mov     rax, [rsi+68h]
0x180007880  mov     rbp, [rax+20h]
0x180007884  mov     dword ptr [rax+4], 1
0x18000788b  mov     rcx, [rsi+68h]; this
0x18000788f  test    rcx, rcx
0x180007892  jz      short loc_180007899
0x180007894  call    ??_GCSafeArray@@QEAAPEAXI@Z; CSafeArray::`scalar deleting destructor'(uint)
0x180007899  mov     qword ptr [rsi+68h], 0
0x1800078a1  jmp     short loc_180007842
0x1800078a3  mov     word ptr [rbx], 0Dh; jumptable 00000001800077EC case 13
0x1800078a8  mov     rax, [r9+8]
0x1800078ac  mov     [rbx+8], rax
0x1800078b0  mov     rcx, [r9+8]
0x1800078b4  test    rcx, rcx
0x1800078b7  jz      loc_1800077B6
0x1800078bd  mov     rax, [rcx]
0x1800078c0  mov     rax, [rax+8]
0x1800078c4  add     rsp, 20h
0x1800078c8  pop     rbx
0x1800078c9  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ce  mov     word ptr [rbx], 11h; jumptable 00000001800077EC case 17
0x1800078d3  movzx   eax, byte ptr [r9+8]
0x1800078d8  mov     [rbx+8], al
0x1800078db  add     rsp, 20h
0x1800078df  pop     rbx
0x1800078e0  retn
0x1800078e1  mov     word ptr [rbx], 2; jumptable 00000001800077EC case 2
0x1800078e6  movzx   eax, word ptr [r9+8]
0x1800078eb  mov     [rbx+8], ax
0x1800078ef  add     rsp, 20h
0x1800078f3  pop     rbx
0x1800078f4  retn
0x1800078f5  mov     word ptr [rbx], 4; jumptable 00000001800077EC case 4
0x1800078fa  mov     eax, [r9+8]
0x1800078fe  mov     [rbx+8], eax
0x180007901  add     rsp, 20h
0x180007905  pop     rbx
0x180007906  retn
0x180007907  mov     rcx, rbx; jumptable 00000001800077EC default case, cases 3,6-8,10,12,14-16
0x18000790a  add     rsp, 20h
0x18000790e  pop     rbx
0x18000790f  jmp     cs:__imp_VariantClear
0x180007916  call    ?_ThrowMemoryException_@@YAXXZ; _ThrowMemoryException_(void)
0x18000791c  mov     word ptr [rbx], 9; jumptable 00000001800077EC case 9
0x180007921  jmp     short loc_1800078A8
0x180007923  mov     rcx, [rcx+20h]; psa
0x180007927  call    cs:__imp_SafeArrayUnaccessData
0x18000792d  mov     qword ptr [rsi+70h], 0
0x180007935  jmp     loc_18000787C
0x18000793a  mov     word ptr [rbx], 5; jumptable 00000001800077EC case 5
0x18000793f  mov     rax, [r9+8]
0x180007943  jmp     loc_1800077B2
```
