# ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180004c88`
- end: `0x180004d5e`
- name: `?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z`
- size: `214`
- prototype: `int(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `31`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a270`
- `0x18000a2d0`
- `0x18000a330`
- `0x18000a390`
- `0x18000a3f0`
- `0x18000a450`
- `0x18000a4b0`
- `0x18000a510`
- `0x18000a570`
- `0x18000a5d0`
- `0x18000a630`
- `0x18000a6b0`
- `0x18000a6d0`
- `0x18000a6f0`
- `0x18000a710`
- `0x18000a730`
- `0x18000a750`
- `0x18000a770`
- `0x18000a790`
- `0x18000a7b0`
- `0x18000a850`
- `0x18000a870`
- `0x18000a890`
- `0x18000a8b0`
- `0x180011000`
- `0x180011020`
- `0x1800122c0`
- `0x180013070`
- `0x180013ab0`
- `0x180013f50`
- `0x180014590`

## callees

- `0x180004c88`
- `0x1800080c4`
- `0x1800080f4`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::AtlInternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  const struct ATL::_ATL_INTMAP_ENTRY *v6; // rbx
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // rbx
  char *v11; // rbx
  __int64 (__fastcall *v12)(char *, const struct _GUID *, char **, _QWORD); // r10
  int v13; // ebp

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !(unsigned int)ATL::InlineIsEqualUnknown(a3) )
  {
    while ( 1 )
    {
      v12 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v6 + 2);
      if ( !v12 )
        return 2147500034LL;
      if ( *(_QWORD *)v6 )
      {
        v13 = 0;
        if ( !(unsigned int)InlineIsEqualGUID(*(const struct _GUID **)v6, a3) )
          goto LABEL_16;
      }
      else
      {
        v13 = 1;
      }
      if ( v12 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      {
        v10 = *((_QWORD *)v6 + 1);
        goto LABEL_7;
      }
      result = v12(a1, a3, a4, *((_QWORD *)v6 + 1));
      if ( !(_DWORD)result || !v13 && (int)result < 0 )
        return result;
LABEL_16:
      v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
    }
  }
  v10 = *(_QWORD *)(v9 + 8);
LABEL_7:
  v11 = &a1[v10];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
  result = 0;
  *a4 = v11;
  return result;
}

```

## disassembly

```asm
0x180004c88  push    rbx
0x180004c8a  push    rbp
0x180004c8b  push    rsi
0x180004c8c  push    rdi
0x180004c8d  push    r14
0x180004c8f  sub     rsp, 30h
0x180004c93  mov     rdi, r9
0x180004c96  mov     r14, r8
0x180004c99  mov     rbx, rdx
0x180004c9c  mov     rsi, rcx
0x180004c9f  test    rcx, rcx
0x180004ca2  jz      loc_180004D4E
0x180004ca8  test    rdx, rdx
0x180004cab  jz      loc_180004D4E
0x180004cb1  test    r9, r9
0x180004cb4  jnz     short loc_180004CC0
0x180004cb6  mov     eax, 80004003h
0x180004cbb  jmp     loc_180004D53
0x180004cc0  mov     rcx, r14; struct _GUID *
0x180004cc3  mov     qword ptr [r9], 0
0x180004cca  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180004ccf  test    eax, eax
0x180004cd1  jz      short loc_180004CF0
0x180004cd3  mov     rbx, [rdx+8]
0x180004cd7  add     rbx, rsi
0x180004cda  mov     rcx, rbx
0x180004cdd  mov     rax, [rbx]
0x180004ce0  mov     rax, [rax+8]
0x180004ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce9  xor     eax, eax
0x180004ceb  mov     [rdi], rbx
0x180004cee  jmp     short loc_180004D53
0x180004cf0  mov     r10, [rbx+10h]
0x180004cf4  test    r10, r10
0x180004cf7  jz      short loc_180004D47
0x180004cf9  mov     rcx, [rbx]; struct _GUID *
0x180004cfc  test    rcx, rcx
0x180004cff  jnz     short loc_180004D06
0x180004d01  lea     ebp, [rcx+1]
0x180004d04  jmp     short loc_180004D14
0x180004d06  mov     rdx, r14; struct _GUID *
0x180004d09  xor     ebp, ebp
0x180004d0b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004d10  test    eax, eax
0x180004d12  jz      short loc_180004D3B
0x180004d14  cmp     r10, 1
0x180004d18  jz      short loc_180004D41
0x180004d1a  mov     r9, [rbx+8]
0x180004d1e  mov     r8, rdi
0x180004d21  mov     rdx, r14
0x180004d24  mov     rcx, rsi
0x180004d27  mov     rax, r10
0x180004d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d2f  test    eax, eax
0x180004d31  jz      short loc_180004D53
0x180004d33  test    ebp, ebp
0x180004d35  jnz     short loc_180004D3B
0x180004d37  test    eax, eax
0x180004d39  js      short loc_180004D53
0x180004d3b  add     rbx, 18h
0x180004d3f  jmp     short loc_180004CF0
0x180004d41  mov     rbx, [rbx+8]
0x180004d45  jmp     short loc_180004CD7
0x180004d47  mov     eax, 80004002h
0x180004d4c  jmp     short loc_180004D53
0x180004d4e  mov     eax, 80070057h
0x180004d53  add     rsp, 30h
0x180004d57  pop     r14
0x180004d59  pop     rdi
0x180004d5a  pop     rsi
0x180004d5b  pop     rbp
0x180004d5c  pop     rbx
0x180004d5d  retn
```
