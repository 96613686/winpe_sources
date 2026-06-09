# CNamespaceManagement::DeleteUnusedClassAndDriverInfo(int,ushort *,ushort *)

- ea: `0x1800183b8`
- end: `0x180018555`
- name: `?DeleteUnusedClassAndDriverInfo@CNamespaceManagement@@QEAAJHPEAG0@Z`
- size: `413`
- prototype: `__int64 __fastcall(CNamespaceManagement *this, int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e230`

## callees

- `0x1800039f4`
- `0x180003e10`
- `0x18000d904`
- `0x18000dc88`
- `0x1800183b8`
- `0x180020010`

## import_xrefs

- `wbemcomn!DebugTrace` at `0x180018409`
- `wbemcomn!DebugTrace` at `0x18001841e`
- `wbemcomn!DebugTrace` at `0x180018409`
- `wbemcomn!DebugTrace` at `0x18001841e`
- `wbemcomn!ErrorTrace` at `0x1800184a0`
- `wbemcomn!ErrorTrace` at `0x180018536`
- `wbemcomn!ErrorTrace` at `0x1800184a0`
- `wbemcomn!ErrorTrace` at `0x180018536`

## string_xrefs

- `0x180018494`: `Tried to delete class but couldn't, return code: 0x%08lx for class: \n`
- `0x1800183fd`: `Tried to delete class but skipped: \n`
- `0x18001852a`: `Tried to delete instance but couldn't, return code: 0x%08lx for instance: \n `

## pseudocode

```c
__int64 __fastcall CNamespaceManagement::DeleteUnusedClassAndDriverInfo(
        CNamespaceManagement *this,
        int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 i; // rbx
  __int64 v8; // rdx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, OLECHAR *, __int64, __int64, _QWORD); // rdi
  __int64 v11; // rbx
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, OLECHAR *, __int64, __int64, _QWORD); // rdi
  __int64 v16; // rbx
  OLECHAR *v18[9]; // [rsp+30h] [rbp-48h] BYREF

  if ( !a2 )
    goto LABEL_13;
  if ( a3 )
  {
    for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
    {
      if ( !(unsigned int)wbem_wcsicmp(a3, off_180021F20[i]) )
      {
        DebugTrace(10, "Tried to delete class but skipped: \n");
        DebugTrace(10, "%S is PSEUDO system class \n", a3);
        goto LABEL_13;
      }
    }
  }
  v8 = *(_QWORD *)(*((_QWORD *)this + 8) + 24LL);
  v9 = *(_QWORD *)(v8 + 8);
  v10 = *(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, __int64, _QWORD))(*(_QWORD *)v9 + 80LL);
  v11 = *(_QWORD *)(v8 + 24);
  v18[0] = 0;
  CBSTR::SetStr((CBSTR *)v18, a3);
  v12 = v10(v9, v18[0], 0x10000, v11, 0);
  CBSTR::Clear(v18);
  if ( !v12 )
    goto LABEL_13;
  if ( v12 == -2147217406 )
  {
    v12 = 0;
  }
  else
  {
    ErrorTrace(10, "Tried to delete class but couldn't, return code: 0x%08lx for class: \n", v12);
    TranslateAndLog(a3, 0);
  }
  if ( !v12 )
  {
LABEL_13:
    v13 = *(_QWORD *)(*((_QWORD *)this + 8) + 24LL);
    v14 = *(_QWORD *)(v13 + 8);
    v15 = *(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, __int64, _QWORD))(*(_QWORD *)v14 + 128LL);
    v16 = *(_QWORD *)(v13 + 24);
    v18[0] = 0;
    CBSTR::SetStr((CBSTR *)v18, a4);
    v12 = v15(v14, v18[0], 0x10000, v16, 0);
    CBSTR::Clear(v18);
    if ( v12 && v12 != -2147217406 )
    {
      ErrorTrace(10, "Tried to delete instance but couldn't, return code: 0x%08lx for instance: \n ", v12);
      TranslateAndLog(a4, 0);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x1800183b8  push    rbx
0x1800183ba  push    rbp
0x1800183bb  push    rsi
0x1800183bc  push    rdi
0x1800183bd  push    r14
0x1800183bf  push    r15
0x1800183c1  sub     rsp, 48h
0x1800183c5  mov     r14, r9
0x1800183c8  mov     rbp, r8
0x1800183cb  mov     r15, rcx
0x1800183ce  test    edx, edx
0x1800183d0  jz      loc_1800184BC
0x1800183d6  test    r8, r8
0x1800183d9  jz      short loc_180018429
0x1800183db  xor     ebx, ebx
0x1800183dd  cmp     ebx, 4
0x1800183e0  jnb     short loc_180018429
0x1800183e2  lea     rax, off_180021F20; "WMIEvent"
0x1800183e9  mov     rdx, [rax+rbx*8]; unsigned __int16 *
0x1800183ed  mov     rcx, rbp; unsigned __int16 *
0x1800183f0  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800183f5  test    eax, eax
0x1800183f7  jz      short loc_1800183FD
0x1800183f9  inc     ebx
0x1800183fb  jmp     short loc_1800183DD
0x1800183fd  lea     rdx, aTriedToDeleteC_0; "Tried to delete class but skipped: \n"
0x180018404  mov     ecx, 0Ah
0x180018409  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18001840f  mov     r8, rbp
0x180018412  lea     rdx, aSIsPseudoSyste; "%S is PSEUDO system class \n"
0x180018419  mov     ecx, 0Ah
0x18001841e  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x180018424  jmp     loc_1800184BC
0x180018429  mov     rax, [r15+40h]
0x18001842d  mov     rdx, [rax+18h]
0x180018431  mov     rsi, [rdx+8]
0x180018435  mov     rax, [rsi]
0x180018438  mov     rdi, [rax+50h]
0x18001843c  mov     rbx, [rdx+18h]
0x180018440  mov     [rsp+78h+var_48], 0
0x180018449  mov     rdx, rbp; psz
0x18001844c  lea     rcx, [rsp+78h+var_48]; this
0x180018451  call    ?SetStr@CBSTR@@QEAAXPEAG@Z; CBSTR::SetStr(ushort *)
0x180018456  nop
0x180018457  mov     [rsp+78h+var_58], 0
0x180018460  mov     r9, rbx
0x180018463  mov     r8d, 10000h
0x180018469  mov     rdx, [rsp+78h+var_48]
0x18001846e  mov     rcx, rsi
0x180018471  mov     rax, rdi
0x180018474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018479  mov     ebx, eax
0x18001847b  lea     rcx, [rsp+78h+var_48]; this
0x180018480  call    ?Clear@CBSTR@@QEAAXXZ; CBSTR::Clear(void)
0x180018485  test    ebx, ebx
0x180018487  jz      short loc_1800184BC
0x180018489  cmp     ebx, 80041002h
0x18001848f  jz      short loc_1800184B2
0x180018491  mov     r8d, ebx
0x180018494  lea     rdx, aTriedToDeleteC; "Tried to delete class but couldn't, ret"...
0x18001849b  mov     ecx, 0Ah
0x1800184a0  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x1800184a6  xor     edx, edx; int
0x1800184a8  mov     rcx, rbp; lpWideCharStr
0x1800184ab  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x1800184b0  jmp     short loc_1800184B4
0x1800184b2  xor     ebx, ebx
0x1800184b4  test    ebx, ebx
0x1800184b6  jnz     loc_180018546
0x1800184bc  mov     rax, [r15+40h]
0x1800184c0  mov     rdx, [rax+18h]
0x1800184c4  mov     rsi, [rdx+8]
0x1800184c8  mov     rax, [rsi]
0x1800184cb  mov     rdi, [rax+80h]
0x1800184d2  mov     rbx, [rdx+18h]
0x1800184d6  mov     [rsp+78h+var_48], 0
0x1800184df  mov     rdx, r14; psz
0x1800184e2  lea     rcx, [rsp+78h+var_48]; this
0x1800184e7  call    ?SetStr@CBSTR@@QEAAXPEAG@Z; CBSTR::SetStr(ushort *)
0x1800184ec  nop
0x1800184ed  mov     [rsp+78h+var_58], 0
0x1800184f6  mov     r9, rbx
0x1800184f9  mov     r8d, 10000h
0x1800184ff  mov     rdx, [rsp+78h+var_48]
0x180018504  mov     rcx, rsi
0x180018507  mov     rax, rdi
0x18001850a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001850f  mov     ebx, eax
0x180018511  lea     rcx, [rsp+78h+var_48]; this
0x180018516  call    ?Clear@CBSTR@@QEAAXXZ; CBSTR::Clear(void)
0x18001851b  test    ebx, ebx
0x18001851d  jz      short loc_180018546
0x18001851f  cmp     ebx, 80041002h
0x180018525  jz      short loc_180018546
0x180018527  mov     r8d, ebx
0x18001852a  lea     rdx, aTriedToDeleteI; "Tried to delete instance but couldn't, "...
0x180018531  mov     ecx, 0Ah
0x180018536  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x18001853c  xor     edx, edx; int
0x18001853e  mov     rcx, r14; lpWideCharStr
0x180018541  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x180018546  mov     eax, ebx
0x180018548  add     rsp, 48h
0x18001854c  pop     r15
0x18001854e  pop     r14
0x180018550  pop     rdi
0x180018551  pop     rsi
0x180018552  pop     rbp
0x180018553  pop     rbx
0x180018554  retn
```
