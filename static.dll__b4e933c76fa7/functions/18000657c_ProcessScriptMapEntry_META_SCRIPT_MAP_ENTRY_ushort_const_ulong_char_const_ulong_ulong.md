# ProcessScriptMapEntry(META_SCRIPT_MAP_ENTRY *,ushort const *,ulong,char const *,ulong,ulong *)

- ea: `0x18000657c`
- end: `0x1800066a8`
- name: `?ProcessScriptMapEntry@@YAHPEAVMETA_SCRIPT_MAP_ENTRY@@PEBGKPEBDKPEAK@Z`
- size: `300`
- prototype: `_BOOL8 __fastcall(struct META_SCRIPT_MAP_ENTRY *, wchar_t *, unsigned int, const char *, char, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800058d8`

## callees

- `0x18000632c`
- `0x18000657c`
- `0x1800067d2`
- `0x180007010`

## string_xrefs

- `0x180006666`: `*.DLL`

## pseudocode

```c
_BOOL8 __fastcall ProcessScriptMapEntry(
        struct META_SCRIPT_MAP_ENTRY *a1,
        wchar_t *a2,
        unsigned int a3,
        const char *a4,
        char a5,
        unsigned int *a6)
{
  unsigned __int8 *v10; // r10
  unsigned __int8 v11; // al
  unsigned __int8 *v12; // rax
  int v13; // r8d
  int v14; // ecx
  __int64 v15; // rax
  const unsigned __int16 *v16; // rax
  const unsigned __int16 *matched; // rax
  const wchar_t *v18; // rbx

  v10 = (unsigned __int8 *)(*(__int64 (__fastcall **)(struct META_SCRIPT_MAP_ENTRY *))(*(_QWORD *)a1 + 8LL))(a1);
  v11 = *v10;
  if ( *v10 == 42 || !v10[1] )
  {
LABEL_11:
    v16 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(struct META_SCRIPT_MAP_ENTRY *))a1)(a1);
    matched = MatchPathInUrl(a2, a3, v16);
    if ( matched )
    {
      *a6 = matched - a2;
      if ( (*(unsigned int (__fastcall **)(struct META_SCRIPT_MAP_ENTRY *))(*(_QWORD *)a1 + 48LL))(a1) != 4
        || (a5 & 4) != 0
        || *(_WORD *)(*(__int64 (__fastcall **)(struct META_SCRIPT_MAP_ENTRY *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, 0) )
      {
        return 1;
      }
      v18 = (const wchar_t *)(**(__int64 (__fastcall ***)(struct META_SCRIPT_MAP_ENTRY *))a1)(a1);
      if ( wcscmp_0(L"*.DLL", v18) )
        return wcscmp_0(L"*.EXE", v18) != 0;
    }
  }
  else
  {
    while ( v11 )
    {
      v12 = v10;
      do
      {
        v13 = v12[a4 - (const char *)v10];
        v14 = *v12 - v13;
        if ( v14 )
          break;
        ++v12;
      }
      while ( v13 );
      if ( !v14 )
        goto LABEL_11;
      v15 = -1;
      do
        ++v15;
      while ( v10[v15] );
      v10 += v15 + 1;
      v11 = *v10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000657c  push    rbx
0x18000657e  push    rbp
0x18000657f  push    rsi
0x180006580  push    rdi
0x180006581  push    r14
0x180006583  sub     rsp, 20h
0x180006587  mov     rax, [rcx]
0x18000658a  mov     rdi, r9
0x18000658d  mov     ebp, r8d
0x180006590  mov     rsi, rdx
0x180006593  mov     rbx, rcx
0x180006596  mov     rax, [rax+8]
0x18000659a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000659f  mov     r10, rax
0x1800065a2  xor     r14d, r14d
0x1800065a5  mov     al, [rax]
0x1800065a7  cmp     al, 2Ah ; '*'
0x1800065a9  jz      short loc_1800065F3
0x1800065ab  cmp     [r10+1], r14b
0x1800065af  jz      short loc_1800065F3
0x1800065b1  test    al, al
0x1800065b3  jz      loc_18000669B
0x1800065b9  mov     rdx, rdi
0x1800065bc  mov     rax, r10
0x1800065bf  sub     rdx, r10
0x1800065c2  movzx   ecx, byte ptr [rax]
0x1800065c5  movzx   r8d, byte ptr [rax+rdx]
0x1800065ca  sub     ecx, r8d
0x1800065cd  jnz     short loc_1800065D7
0x1800065cf  inc     rax
0x1800065d2  test    r8d, r8d
0x1800065d5  jnz     short loc_1800065C2
0x1800065d7  test    ecx, ecx
0x1800065d9  jz      short loc_1800065F3
0x1800065db  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800065df  inc     rax
0x1800065e2  cmp     [r10+rax], r14b
0x1800065e6  jnz     short loc_1800065DF
0x1800065e8  inc     r10
0x1800065eb  add     r10, rax
0x1800065ee  mov     al, [r10]
0x1800065f1  jmp     short loc_1800065B1
0x1800065f3  mov     rax, [rbx]
0x1800065f6  mov     rcx, rbx
0x1800065f9  mov     rax, [rax]
0x1800065fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006601  mov     r8, rax; unsigned __int16 *
0x180006604  mov     edx, ebp; unsigned int
0x180006606  mov     rcx, rsi; String1
0x180006609  call    ?MatchPathInUrl@@YAPEBGPEBGK0@Z; MatchPathInUrl(ushort const *,ulong,ushort const *)
0x18000660e  test    rax, rax
0x180006611  jz      loc_18000669B
0x180006617  mov     rcx, [rsp+48h+arg_28]
0x18000661c  sub     rax, rsi
0x18000661f  sar     rax, 1
0x180006622  mov     [rcx], eax
0x180006624  mov     rcx, rbx
0x180006627  mov     rax, [rbx]
0x18000662a  mov     rax, [rax+30h]
0x18000662e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006633  cmp     eax, 4
0x180006636  jnz     short loc_180006694
0x180006638  test    [rsp+48h+arg_20], al
0x18000663c  jnz     short loc_180006694
0x18000663e  mov     rax, [rbx]
0x180006641  xor     edx, edx
0x180006643  mov     rcx, rbx
0x180006646  mov     rax, [rax+18h]
0x18000664a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000664f  cmp     [rax], r14w
0x180006653  jnz     short loc_180006694
0x180006655  mov     rax, [rbx]
0x180006658  mov     rcx, rbx
0x18000665b  mov     rax, [rax]
0x18000665e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006663  mov     rdx, rax; String2
0x180006666  lea     rcx, aDll; "*.DLL"
0x18000666d  mov     rbx, rax
0x180006670  call    wcscmp_0
0x180006675  test    eax, eax
0x180006677  jz      short loc_18000669B
0x180006679  mov     rdx, rbx; String2
0x18000667c  lea     rcx, aExe; "*.EXE"
0x180006683  call    wcscmp_0
0x180006688  test    eax, eax
0x18000668a  mov     ecx, r14d
0x18000668d  setnz   cl
0x180006690  mov     eax, ecx
0x180006692  jmp     short loc_18000669D
0x180006694  mov     eax, 1
0x180006699  jmp     short loc_18000669D
0x18000669b  xor     eax, eax
0x18000669d  add     rsp, 20h
0x1800066a1  pop     r14
0x1800066a3  pop     rdi
0x1800066a4  pop     rsi
0x1800066a5  pop     rbp
0x1800066a6  pop     rbx
0x1800066a7  retn
```
