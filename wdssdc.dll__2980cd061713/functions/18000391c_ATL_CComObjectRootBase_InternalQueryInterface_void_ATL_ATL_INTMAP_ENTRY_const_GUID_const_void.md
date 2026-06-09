# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18000391c`
- end: `0x180003a36`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `282`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003f90`
- `0x180004030`
- `0x180004060`
- `0x180007660`

## callees

- `0x18000391c`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::InternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  unsigned int v4; // edi
  __int64 v8; // rbx
  char *v9; // rbx
  _QWORD *i; // rsi
  _DWORD *v11; // rcx
  int v12; // ebp
  int v13; // eax

  v4 = 0;
  if ( !a1 || !a2 )
    return (unsigned int)-2147024809;
  if ( !a4 )
    return (unsigned int)-2147467261;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v8 = *((_QWORD *)a2 + 1);
    goto LABEL_9;
  }
  for ( i = (_QWORD *)((char *)a2 + 16); ; i += 3 )
  {
    if ( !*i )
      return (unsigned int)-2147467262;
    v11 = (_DWORD *)*(i - 2);
    if ( v11 )
    {
      v12 = 0;
      if ( *v11 != a3->Data1
        || v11[1] != *(_DWORD *)&a3->Data2
        || v11[2] != *(_DWORD *)a3->Data4
        || v11[3] != *(_DWORD *)&a3->Data4[4] )
      {
        continue;
      }
    }
    else
    {
      v12 = 1;
    }
    if ( *i == 1 )
      break;
    v13 = ((__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*i)(a1, a3, a4, *(i - 1));
    if ( !v13 || !v12 && v13 < 0 )
      return (unsigned int)v13;
  }
  v8 = *(i - 1);
LABEL_9:
  v9 = &a1[v8];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
  *a4 = v9;
  return v4;
}

```

## disassembly

```asm
0x18000391c  mov     [rsp+arg_0], rbx
0x180003921  mov     [rsp+arg_8], rbp
0x180003926  mov     [rsp+arg_10], rsi
0x18000392b  push    rdi
0x18000392c  push    r14
0x18000392e  push    r15
0x180003930  sub     rsp, 30h
0x180003934  xor     edi, edi
0x180003936  mov     r14, r9
0x180003939  mov     rbx, r8
0x18000393c  mov     r15, rcx
0x18000393f  test    rcx, rcx
0x180003942  jz      loc_180003A15
0x180003948  test    rdx, rdx
0x18000394b  jz      loc_180003A15
0x180003951  test    r9, r9
0x180003954  jnz     short loc_180003960
0x180003956  mov     edi, 80004003h
0x18000395b  jmp     loc_180003A1A
0x180003960  mov     [r9], rdi
0x180003963  cmp     [r8], edi
0x180003966  jnz     short loc_18000399D
0x180003968  cmp     [r8+4], edi
0x18000396c  jnz     short loc_18000399D
0x18000396e  cmp     dword ptr [r8+8], 0C0h
0x180003976  jnz     short loc_18000399D
0x180003978  cmp     dword ptr [r8+0Ch], 46000000h
0x180003980  jnz     short loc_18000399D
0x180003982  mov     rbx, [rdx+8]
0x180003986  add     rbx, r15
0x180003989  mov     rcx, rbx
0x18000398c  mov     rax, [rbx]
0x18000398f  mov     rax, [rax+8]
0x180003993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003998  mov     [r14], rbx
0x18000399b  jmp     short loc_180003A1A
0x18000399d  lea     rsi, [rdx+10h]
0x1800039a1  jmp     short loc_1800039FC
0x1800039a3  mov     rcx, [rsi-10h]
0x1800039a7  test    rcx, rcx
0x1800039aa  jnz     short loc_1800039B1
0x1800039ac  lea     ebp, [rcx+1]
0x1800039af  jmp     short loc_1800039D1
0x1800039b1  mov     eax, [rbx]
0x1800039b3  mov     ebp, edi
0x1800039b5  cmp     [rcx], eax
0x1800039b7  jnz     short loc_1800039F8
0x1800039b9  mov     eax, [rbx+4]
0x1800039bc  cmp     [rcx+4], eax
0x1800039bf  jnz     short loc_1800039F8
0x1800039c1  mov     eax, [rbx+8]
0x1800039c4  cmp     [rcx+8], eax
0x1800039c7  jnz     short loc_1800039F8
0x1800039c9  mov     eax, [rbx+0Ch]
0x1800039cc  cmp     [rcx+0Ch], eax
0x1800039cf  jnz     short loc_1800039F8
0x1800039d1  cmp     qword ptr [rsi], 1
0x1800039d5  jz      short loc_180003A0C
0x1800039d7  mov     r9, [rsi-8]
0x1800039db  mov     r8, r14
0x1800039de  mov     rax, [rsi]
0x1800039e1  mov     rdx, rbx
0x1800039e4  mov     rcx, r15
0x1800039e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ec  test    eax, eax
0x1800039ee  jz      short loc_180003A08
0x1800039f0  test    ebp, ebp
0x1800039f2  jnz     short loc_1800039F8
0x1800039f4  test    eax, eax
0x1800039f6  js      short loc_180003A08
0x1800039f8  add     rsi, 18h
0x1800039fc  cmp     [rsi], rdi
0x1800039ff  jnz     short loc_1800039A3
0x180003a01  mov     edi, 80004002h
0x180003a06  jmp     short loc_180003A1A
0x180003a08  mov     edi, eax
0x180003a0a  jmp     short loc_180003A1A
0x180003a0c  mov     rbx, [rsi-8]
0x180003a10  jmp     loc_180003986
0x180003a15  mov     edi, 80070057h
0x180003a1a  mov     rbx, [rsp+48h+arg_0]
0x180003a1f  mov     eax, edi
0x180003a21  mov     rbp, [rsp+48h+arg_8]
0x180003a26  mov     rsi, [rsp+48h+arg_10]
0x180003a2b  add     rsp, 30h
0x180003a2f  pop     r15
0x180003a31  pop     r14
0x180003a33  pop     rdi
0x180003a34  retn
```
