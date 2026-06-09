# GenericLexer<XmlTokenizer<GenericLexerSource>,GenericLexerSource>::NextToken(ulong &)

- ea: `0x180013794`
- end: `0x180013a04`
- name: `?NextToken@?$GenericLexer@V?$XmlTokenizer@VGenericLexerSource@@@@VGenericLexerSource@@@@QEAA_NAEAK@Z`
- size: `624`
- prototype: `char __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180013a0c`

## callees

- `0x180003430`
- `0x1800034f0`
- `0x180013794`
- `0x180013de4`
- `0x180013e30`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180013978`
- `msvcrt!wcsncpy_s` at `0x180013978`

## pseudocode

```c
char __fastcall GenericLexer<XmlTokenizer<GenericLexerSource>,GenericLexerSource>::NextToken(__int64 a1, _DWORD *a2)
{
  unsigned __int64 v3; // rdi
  char v4; // r11
  __int64 v5; // rax
  __int64 v6; // r12
  __int64 v7; // r15
  __int16 v8; // r13
  unsigned __int16 *v9; // rax
  int v10; // ecx
  unsigned __int16 v11; // ax
  bool v12; // al
  int v13; // ecx
  int v14; // ecx
  __int64 v15; // rcx
  bool v16; // cf
  __int64 v17; // rcx
  unsigned __int16 v18; // r8
  __int64 v19; // rcx
  int v20; // ecx
  int v21; // ecx
  unsigned int v22; // ebp
  wchar_t *v23; // r14
  void *v24; // rcx
  int v25; // eax

  v3 = 0;
  v4 = 1;
  **(_WORD **)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 36) = 0;
  do
  {
    while ( 1 )
    {
      v5 = *(int *)(a1 + 16);
      v6 = *(_QWORD *)(a1 + 8);
      v7 = 3 * v5;
      v8 = *(_WORD *)(v6 + 12 * v5 + 10);
      if ( v4 )
      {
        v9 = *(unsigned __int16 **)(*(_QWORD *)a1 + 8LL);
        v3 = *v9;
        *(_QWORD *)(*(_QWORD *)a1 + 8LL) = v9 + 1;
      }
      v10 = *(unsigned __int16 *)(v6 + 4 * v7 + 2);
      v4 = 0;
      v11 = *(_WORD *)(v6 + 4 * v7);
      if ( (_WORD)v10 == 0xFFFE )
      {
        if ( v11 != 0xFFFF )
        {
          v12 = (_WORD)v3 == v11;
          goto LABEL_31;
        }
LABEL_7:
        v12 = 1;
        goto LABEL_31;
      }
      if ( v11 == 0xFFFD )
        break;
      if ( (unsigned __int16)v3 >= v11 && (unsigned __int16)v3 <= (unsigned __int16)v10 )
        goto LABEL_35;
LABEL_32:
      ++*(_DWORD *)(a1 + 16);
    }
    if ( !*(_WORD *)(v6 + 4 * v7 + 2) )
    {
      if ( (unsigned __int16)(v3 + 10240) > 0x7FFu )
      {
        if ( (unsigned __int16)v3 > 0x13u || (v20 = 1038847, !_bittest(&v20, v3)) )
        {
          v16 = (unsigned __int16)v3 < 0xFFFEu;
LABEL_29:
          v12 = 1;
          if ( v16 )
            goto LABEL_31;
        }
      }
LABEL_30:
      v12 = 0;
      goto LABEL_31;
    }
    v13 = v10 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 == 1 && (unsigned __int16)v3 <= 0x20u )
        {
          v15 = 0x100002600LL;
          v16 = _bittest64(&v15, v3);
          goto LABEL_29;
        }
        goto LABEL_30;
      }
      if ( (unsigned __int16)(v3 - 65) <= 0x39u )
      {
        v17 = 0x3FFFFFF43FFFFFFLL;
        if ( _bittest64(&v17, (unsigned int)(v3 - 65)) )
          goto LABEL_7;
      }
      if ( (_WORD)v3 == 58 )
        goto LABEL_7;
      if ( (unsigned int)IsInTable((struct SRange *)&g_BaseCharTbl, 202, v3) )
        v12 = 1;
      else
        v12 = (unsigned int)IsInTable((struct SRange *)&g_IdeographicTbl, 3, v18) != 0;
    }
    else
    {
      if ( (unsigned __int16)(v3 - 97) <= 0x19u )
        goto LABEL_7;
      if ( (unsigned __int16)(v3 - 45) <= 0x32u )
      {
        v19 = 0x43FFFFFF03FFBLL;
        if ( _bittest64(&v19, (unsigned int)(v3 - 45)) )
          goto LABEL_7;
      }
      v12 = IsNameCharSlow(v3);
    }
LABEL_31:
    if ( !v12 )
      goto LABEL_32;
LABEL_35:
    if ( (v8 & 1) != 0 )
    {
      v21 = *(_DWORD *)(a1 + 32);
      if ( *(_DWORD *)(a1 + 36) + 1 >= v21 )
      {
        v22 = 2 * v21;
        v23 = (wchar_t *)operator new(saturated_mul((unsigned int)(2 * v21), 2u));
        wcsncpy_s(v23, v22, *(const wchar_t **)(a1 + 24), *(int *)(a1 + 36));
        v24 = *(void **)(a1 + 24);
        if ( v24 != (void *)(a1 + 40) )
          operator delete(v24);
        *(_QWORD *)(a1 + 24) = v23;
        *(_DWORD *)(a1 + 32) = v22;
      }
      *(_WORD *)(*(_QWORD *)(a1 + 24) + 2LL * (int)(*(_DWORD *)(a1 + 36))++) = v3;
      goto LABEL_44;
    }
    if ( (v8 & 2) != 0 )
      goto LABEL_44;
    if ( (v8 & 4) != 0 )
    {
      *(_QWORD *)(*(_QWORD *)a1 + 8LL) += -2LL * *(unsigned __int16 *)(v6 + 4 * v7 + 8);
LABEL_44:
      v4 = 1;
    }
    *(_DWORD *)(a1 + 16) = *(unsigned __int16 *)(v6 + 4 * v7 + 4);
    v25 = *(unsigned __int16 *)(v6 + 4 * v7 + 6);
  }
  while ( !(_WORD)v25 && (v8 & 0x20) == 0 );
  *a2 = v25;
  return 1;
}

```

## disassembly

```asm
0x180013794  mov     [rsp+arg_8], rdx
0x180013799  push    rbx
0x18001379a  push    rbp
0x18001379b  push    rsi
0x18001379c  push    rdi
0x18001379d  push    r12
0x18001379f  push    r13
0x1800137a1  push    r14
0x1800137a3  push    r15
0x1800137a5  sub     rsp, 28h
0x1800137a9  mov     r8, [rcx+18h]
0x1800137ad  xor     ebx, ebx
0x1800137af  mov     rsi, rcx
0x1800137b2  mov     edi, ebx
0x1800137b4  mov     r11b, 1
0x1800137b7  mov     [r8], bx
0x1800137bb  mov     [rcx+24h], ebx
0x1800137be  mov     r8d, 0FFFEh
0x1800137c4  movsxd  rax, dword ptr [rsi+10h]
0x1800137c8  mov     r12, [rsi+8]
0x1800137cc  lea     r15, [rax+rax*2]
0x1800137d0  movzx   r13d, word ptr [r12+r15*4+0Ah]
0x1800137d6  test    r11b, r11b
0x1800137d9  jz      short loc_1800137ED
0x1800137db  mov     rdx, [rsi]
0x1800137de  mov     rax, [rdx+8]
0x1800137e2  movzx   edi, word ptr [rax]
0x1800137e5  add     rax, 2
0x1800137e9  mov     [rdx+8], rax
0x1800137ed  movzx   ecx, word ptr [r12+r15*4+2]
0x1800137f3  mov     r11b, bl
0x1800137f6  movzx   eax, word ptr [r12+r15*4]
0x1800137fb  cmp     cx, r8w
0x1800137ff  jnz     short loc_18001381D
0x180013801  mov     ecx, 0FFFFh
0x180013806  cmp     ax, cx
0x180013809  jz      short loc_180013816
0x18001380b  cmp     di, ax
0x18001380e  setz    al
0x180013811  jmp     loc_180013920
0x180013816  mov     al, 1
0x180013818  jmp     loc_180013920
0x18001381d  mov     edx, 0FFFDh
0x180013822  cmp     ax, dx
0x180013825  jnz     loc_18001392C
0x18001382b  test    ecx, ecx
0x18001382d  jz      loc_1800138F5
0x180013833  sub     ecx, 1
0x180013836  jz      loc_1800138C1
0x18001383c  sub     ecx, 1
0x18001383f  jz      short loc_180013867
0x180013841  cmp     ecx, 1
0x180013844  jnz     loc_18001391E
0x18001384a  cmp     di, 20h ; ' '
0x18001384e  ja      loc_18001391E
0x180013854  mov     rcx, 100002600h
0x18001385e  bt      rcx, rdi
0x180013862  jmp     loc_18001391A
0x180013867  lea     eax, [rdi-41h]
0x18001386a  cmp     ax, 39h ; '9'
0x18001386e  ja      short loc_180013880
0x180013870  mov     rcx, 3FFFFFF43FFFFFFh
0x18001387a  bt      rcx, rax
0x18001387e  jb      short loc_180013816
0x180013880  cmp     di, 3Ah ; ':'
0x180013884  jz      short loc_180013816
0x180013886  movzx   r8d, di; unsigned __int16
0x18001388a  lea     rcx, ?g_BaseCharTbl@@3PAUSRange@@A; "AZaz"
0x180013891  mov     edx, 0CAh; int
0x180013896  call    ?IsInTable@@YAHPEAUSRange@@HG@Z; IsInTable(SRange *,int,ushort)
0x18001389b  test    eax, eax
0x18001389d  jz      short loc_1800138A3
0x18001389f  mov     al, 1
0x1800138a1  jmp     short loc_1800138B9
0x1800138a3  mov     edx, 3; int
0x1800138a8  lea     rcx, ?g_IdeographicTbl@@3PAUSRange@@A; struct SRange *
0x1800138af  call    ?IsInTable@@YAHPEAUSRange@@HG@Z; IsInTable(SRange *,int,ushort)
0x1800138b4  test    eax, eax
0x1800138b6  setnz   al
0x1800138b9  mov     r8d, 0FFFEh
0x1800138bf  jmp     short loc_180013920
0x1800138c1  lea     eax, [rdi-61h]
0x1800138c4  cmp     ax, 19h
0x1800138c8  jbe     loc_180013816
0x1800138ce  lea     eax, [rdi-2Dh]
0x1800138d1  cmp     ax, 32h ; '2'
0x1800138d5  ja      short loc_1800138EB
0x1800138d7  mov     rcx, 43FFFFFF03FFBh
0x1800138e1  bt      rcx, rax
0x1800138e5  jb      loc_180013816
0x1800138eb  movzx   ecx, di; unsigned __int16
0x1800138ee  call    ?IsNameCharSlow@@YA_NG@Z; IsNameCharSlow(ushort)
0x1800138f3  jmp     short loc_1800138B9
0x1800138f5  mov     eax, 2800h
0x1800138fa  mov     ecx, 7FFh
0x1800138ff  add     eax, edi
0x180013901  cmp     ax, cx
0x180013904  jbe     short loc_18001391E
0x180013906  cmp     di, 13h
0x18001390a  ja      short loc_180013916
0x18001390c  mov     ecx, 0FD9FFh
0x180013911  bt      ecx, edi
0x180013914  jb      short loc_18001391E
0x180013916  cmp     di, r8w
0x18001391a  mov     al, 1
0x18001391c  jb      short loc_180013920
0x18001391e  mov     al, bl
0x180013920  test    al, al
0x180013922  jnz     short loc_180013936
0x180013924  inc     dword ptr [rsi+10h]
0x180013927  jmp     loc_1800137C4
0x18001392c  cmp     di, ax
0x18001392f  jb      short loc_180013924
0x180013931  cmp     di, cx
0x180013934  ja      short loc_180013924
0x180013936  test    r13b, 1
0x18001393a  jz      short loc_1800139AA
0x18001393c  mov     eax, [rsi+24h]
0x18001393f  mov     ecx, [rsi+20h]
0x180013942  inc     eax
0x180013944  cmp     eax, ecx
0x180013946  jl      short loc_180013999
0x180013948  lea     ebp, [rcx+rcx]
0x18001394b  mov     eax, 2
0x180013950  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180013957  mov     ebx, ebp
0x180013959  mul     rbx
0x18001395c  cmovb   rax, rcx
0x180013960  mov     rcx, rax; dwBytes
0x180013963  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013968  movsxd  r9, dword ptr [rsi+24h]; MaxCount
0x18001396c  mov     rcx, rax; Destination
0x18001396f  mov     r8, [rsi+18h]; Source
0x180013973  mov     r14, rax
0x180013976  mov     edx, ebp; SizeInWords
0x180013978  call    cs:__imp_wcsncpy_s
0x18001397e  mov     rcx, [rsi+18h]; void *
0x180013982  lea     rax, [rsi+28h]
0x180013986  cmp     rcx, rax
0x180013989  jz      short loc_180013990
0x18001398b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013990  mov     [rsi+18h], r14
0x180013994  xor     ebx, ebx
0x180013996  mov     [rsi+20h], ebp
0x180013999  movsxd  rcx, dword ptr [rsi+24h]
0x18001399d  mov     rax, [rsi+18h]
0x1800139a1  mov     [rax+rcx*2], di
0x1800139a5  inc     dword ptr [rsi+24h]
0x1800139a8  jmp     short loc_1800139C9
0x1800139aa  test    r13b, 2
0x1800139ae  jnz     short loc_1800139C9
0x1800139b0  test    r13b, 4
0x1800139b4  jz      short loc_1800139CC
0x1800139b6  movzx   eax, word ptr [r12+r15*4+8]
0x1800139bc  mov     rcx, [rsi]
0x1800139bf  neg     rax
0x1800139c2  add     rax, rax
0x1800139c5  add     [rcx+8], rax
0x1800139c9  mov     r11b, 1
0x1800139cc  movzx   eax, word ptr [r12+r15*4+4]
0x1800139d2  mov     [rsi+10h], eax
0x1800139d5  movzx   eax, word ptr [r12+r15*4+6]
0x1800139db  test    ax, ax
0x1800139de  jnz     short loc_1800139EA
0x1800139e0  test    r13b, 20h
0x1800139e4  jz      loc_1800137BE
0x1800139ea  mov     rdx, [rsp+68h+arg_8]
0x1800139ef  mov     [rdx], eax
0x1800139f1  mov     al, 1
0x1800139f3  add     rsp, 28h
0x1800139f7  pop     r15
0x1800139f9  pop     r14
0x1800139fb  pop     r13
0x1800139fd  pop     r12
0x1800139ff  pop     rdi
0x180013a00  pop     rsi
0x180013a01  pop     rbp
0x180013a02  pop     rbx
0x180013a03  retn
```
