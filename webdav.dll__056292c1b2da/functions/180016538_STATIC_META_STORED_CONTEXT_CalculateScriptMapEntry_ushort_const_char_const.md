# STATIC_META_STORED_CONTEXT::CalculateScriptMapEntry(ushort const *,char const *)

- ea: `0x180016538`
- end: `0x1800166c2`
- name: `?CalculateScriptMapEntry@STATIC_META_STORED_CONTEXT@@QEAAPEAVIScriptMapInfo@@PEBGPEBD@Z`
- size: `394`
- prototype: `struct IScriptMapInfo *(STATIC_META_STORED_CONTEXT *__hidden this, const unsigned __int16 *, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016708`

## callees

- `0x180016538`
- `0x180019248`
- `0x1800224e6`
- `0x180023010`

## string_xrefs

- `0x18001662d`: `*.DLL`

## pseudocode

```c
struct IScriptMapInfo *__fastcall STATIC_META_STORED_CONTEXT::CalculateScriptMapEntry(
        STATIC_META_STORED_CONTEXT *this,
        wchar_t *a2,
        const char *a3)
{
  int v3; // r15d
  __int64 v4; // rsi
  _QWORD *v7; // r14
  _QWORD *i; // rcx
  unsigned __int8 *v9; // rax
  const unsigned __int16 *v10; // rax
  const wchar_t *v11; // rdi
  _QWORD *v12; // rbx
  unsigned __int8 *v14; // rcx
  int v15; // r8d
  int v16; // edx
  __int64 v17; // rcx

  v3 = *((_DWORD *)this + 70);
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v7 = (_QWORD *)(*((_QWORD *)this + 34) + 8LL);
  for ( i = (_QWORD *)*v7; ; i = (_QWORD *)v12[1] )
  {
    v12 = i - 1;
    if ( i == v7 )
      v12 = 0;
    if ( !v12 )
      break;
    if ( !*(_WORD *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v12 + 24LL))(v12, 0) )
      (*(void (__fastcall **)(_QWORD *))(*v12 + 80LL))(v12);
    (*(void (__fastcall **)(_QWORD *))*v12)(v12);
    v9 = (unsigned __int8 *)(*(__int64 (__fastcall **)(_QWORD *))(*v12 + 8LL))(v12);
    if ( *v9 != 42 && v9[1] )
    {
      while ( *v9 )
      {
        v14 = v9;
        do
        {
          v15 = v14[a3 - (const char *)v9];
          v16 = *v14 - v15;
          if ( v16 )
            break;
          ++v14;
        }
        while ( v15 );
        if ( !v16 )
          goto LABEL_8;
        v17 = -1;
        do
          ++v17;
        while ( v9[v17] );
        v9 += v17 + 1;
      }
    }
    else
    {
LABEL_8:
      v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD *))*v12)(v12);
      if ( MatchPathInUrl(a2, v4, v10) )
      {
        if ( (*(unsigned int (__fastcall **)(_QWORD *))(*v12 + 48LL))(v12) != 4 )
          return (struct IScriptMapInfo *)v12;
        if ( (v3 & 4) != 0 )
          return (struct IScriptMapInfo *)v12;
        if ( *(_WORD *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v12 + 24LL))(v12, 0) )
          return (struct IScriptMapInfo *)v12;
        v11 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD *))*v12)(v12);
        if ( wcscmp_0(L"*.DLL", v11) )
        {
          if ( wcscmp_0(L"*.EXE", v11) )
            return (struct IScriptMapInfo *)v12;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016538  push    rbx
0x18001653a  push    rbp
0x18001653b  push    rsi
0x18001653c  push    rdi
0x18001653d  push    r12
0x18001653f  push    r13
0x180016541  push    r14
0x180016543  push    r15
0x180016545  sub     rsp, 28h
0x180016549  mov     r15d, [rcx+118h]
0x180016550  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016554  xor     r13d, r13d
0x180016557  mov     r12, r8
0x18001655a  mov     rbp, rdx
0x18001655d  inc     rsi
0x180016560  cmp     [rdx+rsi*2], r13w
0x180016565  jnz     short loc_18001655D
0x180016567  mov     r14, [rcx+110h]
0x18001656e  add     r14, 8
0x180016572  mov     rcx, [r14]
0x180016575  jmp     loc_180016657
0x18001657a  mov     rax, [rbx]
0x18001657d  xor     edx, edx
0x18001657f  mov     rcx, rbx
0x180016582  mov     rax, [rax+18h]
0x180016586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001658b  cmp     [rax], r13w
0x18001658f  jnz     short loc_1800165A0
0x180016591  mov     rax, [rbx]
0x180016594  mov     rcx, rbx
0x180016597  mov     rax, [rax+50h]
0x18001659b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165a0  mov     rax, [rbx]
0x1800165a3  mov     rcx, rbx
0x1800165a6  mov     rax, [rax]
0x1800165a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165ae  mov     rax, [rbx]
0x1800165b1  mov     rcx, rbx
0x1800165b4  mov     rax, [rax+8]
0x1800165b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165bd  cmp     byte ptr [rax], 2Ah ; '*'
0x1800165c0  jz      short loc_1800165CC
0x1800165c2  cmp     [rax+1], r13b
0x1800165c6  jnz     loc_1800166BB
0x1800165cc  mov     rax, [rbx]
0x1800165cf  mov     rcx, rbx
0x1800165d2  mov     rax, [rax]
0x1800165d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165da  mov     r8, rax; unsigned __int16 *
0x1800165dd  mov     edx, esi; unsigned int
0x1800165df  mov     rcx, rbp; String1
0x1800165e2  call    ?MatchPathInUrl@@YAPEBGPEBGK0@Z; MatchPathInUrl(ushort const *,ulong,ushort const *)
0x1800165e7  test    rax, rax
0x1800165ea  jz      short loc_180016653
0x1800165ec  mov     rax, [rbx]
0x1800165ef  mov     rcx, rbx
0x1800165f2  mov     rax, [rax+30h]
0x1800165f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165fb  cmp     eax, 4
0x1800165fe  jnz     short loc_18001666E
0x180016600  test    al, r15b
0x180016603  jnz     short loc_18001666E
0x180016605  mov     rax, [rbx]
0x180016608  xor     edx, edx
0x18001660a  mov     rcx, rbx
0x18001660d  mov     rax, [rax+18h]
0x180016611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016616  cmp     [rax], r13w
0x18001661a  jnz     short loc_18001666E
0x18001661c  mov     rax, [rbx]
0x18001661f  mov     rcx, rbx
0x180016622  mov     rax, [rax]
0x180016625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001662a  mov     rdx, rax; String2
0x18001662d  lea     rcx, aDll; "*.DLL"
0x180016634  mov     rdi, rax
0x180016637  call    wcscmp_0
0x18001663c  test    eax, eax
0x18001663e  jz      short loc_180016653
0x180016640  mov     rdx, rdi; String2
0x180016643  lea     rcx, aExe; "*.EXE"
0x18001664a  call    wcscmp_0
0x18001664f  test    eax, eax
0x180016651  jnz     short loc_18001666E
0x180016653  mov     rcx, [rbx+8]
0x180016657  cmp     rcx, r14
0x18001665a  lea     rbx, [rcx-8]
0x18001665e  cmovz   rbx, r13
0x180016662  test    rbx, rbx
0x180016665  jnz     loc_18001657A
0x18001666b  mov     rbx, r13
0x18001666e  mov     rax, rbx
0x180016671  add     rsp, 28h
0x180016675  pop     r15
0x180016677  pop     r14
0x180016679  pop     r13
0x18001667b  pop     r12
0x18001667d  pop     rdi
0x18001667e  pop     rsi
0x18001667f  pop     rbp
0x180016680  pop     rbx
0x180016681  retn
0x180016682  mov     r9, r12
0x180016685  mov     rcx, rax
0x180016688  sub     r9, rax
0x18001668b  movzx   edx, byte ptr [rcx]
0x18001668e  movzx   r8d, byte ptr [rcx+r9]
0x180016693  sub     edx, r8d
0x180016696  jnz     short loc_1800166A0
0x180016698  inc     rcx
0x18001669b  test    r8d, r8d
0x18001669e  jnz     short loc_18001668B
0x1800166a0  test    edx, edx
0x1800166a2  jz      loc_1800165CC
0x1800166a8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800166ac  inc     rcx
0x1800166af  cmp     [rax+rcx], r13b
0x1800166b3  jnz     short loc_1800166AC
0x1800166b5  inc     rax
0x1800166b8  add     rax, rcx
0x1800166bb  cmp     [rax], r13b
0x1800166be  jnz     short loc_180016682
0x1800166c0  jmp     short loc_180016653
```
