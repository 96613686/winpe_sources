# CDbAccessor::ReleaseRowBuffer(void)

- ea: `0x1800193f0`
- end: `0x1800194ba`
- name: `?ReleaseRowBuffer@CDbAccessor@@QEAAXXZ`
- size: `202`
- prototype: `void __fastcall(CDbAccessor *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180018720`
- `0x180018f60`
- `0x1800196b0`

## callees

- `0x1800193f0`
- `0x180030362`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180019488`
- `OLEAUT32!__imp_SysFreeString` at `0x180019488`
- `OLEAUT32!__imp_VariantClear` at `0x180019477`
- `OLEAUT32!__imp_VariantClear` at `0x180019477`

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
0x1800193f0  mov     [rsp+arg_0], rbx
0x1800193f5  push    rdi
0x1800193f6  sub     rsp, 20h
0x1800193fa  cmp     qword ptr [rcx+20h], 0
0x1800193ff  mov     rbx, rcx
0x180019402  jz      loc_1800194AE
0x180019408  xor     edi, edi
0x18001940a  cmp     [rcx+18h], edi
0x18001940d  jbe     loc_18001949F
0x180019413  mov     r8, [rbx+10h]
0x180019417  mov     rdx, [rbx+20h]
0x18001941b  mov     eax, edi
0x18001941d  imul    rcx, rax, 58h ; 'X'
0x180019421  mov     rax, [rcx+r8+18h]
0x180019426  test    dword ptr [rdx+rax], 0FFFFFFFBh
0x18001942d  jnz     short loc_180019494
0x18001942f  add     rdx, [rcx+r8+8]
0x180019434  mov     eax, 4000h
0x180019439  test    [r8+rcx+54h], ax
0x18001943f  jz      short loc_180019444
0x180019441  mov     rdx, [rdx]
0x180019444  movzx   ecx, word ptr [r8+rcx+54h]
0x18001944a  sub     ecx, 8
0x18001944d  jz      short loc_180019485
0x18001944f  sub     ecx, 1
0x180019452  jz      short loc_18001945E
0x180019454  sub     ecx, 3
0x180019457  jz      short loc_180019474
0x180019459  cmp     ecx, 1
0x18001945c  jnz     short loc_180019494
0x18001945e  mov     rcx, [rdx]
0x180019461  test    rcx, rcx
0x180019464  jz      short loc_180019494
0x180019466  mov     rax, [rcx]
0x180019469  mov     rax, [rax+10h]
0x18001946d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019472  jmp     short loc_180019494
0x180019474  mov     rcx, rdx; pvarg
0x180019477  call    cs:__imp_VariantClear
0x18001947e  nop     dword ptr [rax+rax+00h]
0x180019483  jmp     short loc_180019494
0x180019485  mov     rcx, [rdx]; bstrString
0x180019488  call    cs:__imp_SysFreeString
0x18001948f  nop     dword ptr [rax+rax+00h]
0x180019494  inc     edi
0x180019496  cmp     edi, [rbx+18h]
0x180019499  jb      loc_180019413
0x18001949f  mov     r8d, [rbx+28h]; Size
0x1800194a3  xor     edx, edx; Val
0x1800194a5  mov     rcx, [rbx+20h]; void *
0x1800194a9  call    memset_0
0x1800194ae  mov     rbx, [rsp+28h+arg_0]
0x1800194b3  add     rsp, 20h
0x1800194b7  pop     rdi
0x1800194b8  retn
```
