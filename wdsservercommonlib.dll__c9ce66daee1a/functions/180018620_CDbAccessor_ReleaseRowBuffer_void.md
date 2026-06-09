# CDbAccessor::ReleaseRowBuffer(void)

- ea: `0x180018620`
- end: `0x1800186ea`
- name: `?ReleaseRowBuffer@CDbAccessor@@QEAAXXZ`
- size: `202`
- prototype: `void __fastcall(CDbAccessor *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180017970`
- `0x180018190`
- `0x1800188e0`

## callees

- `0x180018620`
- `0x18002f3ba`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800186b8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800186b8`
- `OLEAUT32!__imp_VariantClear` at `0x1800186a7`
- `OLEAUT32!__imp_VariantClear` at `0x1800186a7`

## pseudocode

```c
void __fastcall CDbAccessor::ReleaseRowBuffer(CDbAccessor *this)
{
  unsigned int i; // edi
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // rcx
  VARIANTARG *v6; // rdx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx

  if ( *((_QWORD *)this + 4) )
  {
    for ( i = 0; i < *((_DWORD *)this + 6); ++i )
    {
      v3 = *((_QWORD *)this + 2);
      v4 = *((_QWORD *)this + 4);
      v5 = 88LL * i;
      if ( (*(_DWORD *)(v4 + *(_QWORD *)(v5 + v3 + 24)) & 0xFFFFFFFB) == 0 )
      {
        v6 = (VARIANTARG *)(*(_QWORD *)(v5 + v3 + 8) + v4);
        if ( (*(_WORD *)(v3 + v5 + 84) & 0x4000) != 0 )
          v6 = *(VARIANTARG **)&v6->vt;
        v7 = *(unsigned __int16 *)(v3 + v5 + 84) - 8;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( !v8 )
            goto LABEL_10;
          v9 = v8 - 3;
          if ( v9 )
          {
            if ( v9 == 1 )
            {
LABEL_10:
              if ( *(_QWORD *)&v6->vt )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v6->vt + 16LL))(*(_QWORD *)&v6->vt);
            }
          }
          else
          {
            VariantClear(v6);
          }
        }
        else
        {
          SysFreeString(*(BSTR *)&v6->vt);
        }
      }
    }
    memset_0(*((void **)this + 4), 0, *((unsigned int *)this + 10));
  }
}

```

## disassembly

```asm
0x180018620  mov     [rsp+arg_0], rbx
0x180018625  push    rdi
0x180018626  sub     rsp, 20h
0x18001862a  cmp     qword ptr [rcx+20h], 0
0x18001862f  mov     rbx, rcx
0x180018632  jz      loc_1800186DE
0x180018638  xor     edi, edi
0x18001863a  cmp     [rcx+18h], edi
0x18001863d  jbe     loc_1800186CF
0x180018643  mov     r8, [rbx+10h]
0x180018647  mov     rdx, [rbx+20h]
0x18001864b  mov     eax, edi
0x18001864d  imul    rcx, rax, 58h ; 'X'
0x180018651  mov     rax, [rcx+r8+18h]
0x180018656  test    dword ptr [rdx+rax], 0FFFFFFFBh
0x18001865d  jnz     short loc_1800186C4
0x18001865f  add     rdx, [rcx+r8+8]
0x180018664  mov     eax, 4000h
0x180018669  test    [r8+rcx+54h], ax
0x18001866f  jz      short loc_180018674
0x180018671  mov     rdx, [rdx]
0x180018674  movzx   ecx, word ptr [r8+rcx+54h]
0x18001867a  sub     ecx, 8
0x18001867d  jz      short loc_1800186B5
0x18001867f  sub     ecx, 1
0x180018682  jz      short loc_18001868E
0x180018684  sub     ecx, 3
0x180018687  jz      short loc_1800186A4
0x180018689  cmp     ecx, 1
0x18001868c  jnz     short loc_1800186C4
0x18001868e  mov     rcx, [rdx]
0x180018691  test    rcx, rcx
0x180018694  jz      short loc_1800186C4
0x180018696  mov     rax, [rcx]
0x180018699  mov     rax, [rax+10h]
0x18001869d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186a2  jmp     short loc_1800186C4
0x1800186a4  mov     rcx, rdx; pvarg
0x1800186a7  call    cs:__imp_VariantClear
0x1800186ae  nop     dword ptr [rax+rax+00h]
0x1800186b3  jmp     short loc_1800186C4
0x1800186b5  mov     rcx, [rdx]; bstrString
0x1800186b8  call    cs:__imp_SysFreeString
0x1800186bf  nop     dword ptr [rax+rax+00h]
0x1800186c4  inc     edi
0x1800186c6  cmp     edi, [rbx+18h]
0x1800186c9  jb      loc_180018643
0x1800186cf  mov     r8d, [rbx+28h]; Size
0x1800186d3  xor     edx, edx; Val
0x1800186d5  mov     rcx, [rbx+20h]; void *
0x1800186d9  call    memset_0
0x1800186de  mov     rbx, [rsp+28h+arg_0]
0x1800186e3  add     rsp, 20h
0x1800186e7  pop     rdi
0x1800186e8  retn
```
