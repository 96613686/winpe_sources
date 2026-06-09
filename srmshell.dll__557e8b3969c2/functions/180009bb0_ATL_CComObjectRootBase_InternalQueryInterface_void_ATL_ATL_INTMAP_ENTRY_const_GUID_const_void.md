# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180009bb0`
- end: `0x180009cb4`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cb70`
- `0x18000cb90`
- `0x1800144e0`
- `0x180014550`
- `0x180014610`
- `0x180014630`

## callees

- `0x180009bb0`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::InternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  const struct ATL::_ATL_INTMAP_ENTRY *v6; // rbx
  __int64 result; // rax
  __int64 v9; // rbx
  char *v10; // rbx
  _DWORD *v11; // rcx
  int v12; // ebp
  __int64 (__fastcall *v13)(char *, const struct _GUID *, char **, _QWORD); // rax

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v9 = *((_QWORD *)a2 + 1);
    goto LABEL_9;
  }
  if ( !*((_QWORD *)a2 + 2) )
    return 2147500034LL;
  while ( 1 )
  {
    v11 = *(_DWORD **)v6;
    if ( *(_QWORD *)v6 )
    {
      if ( *v11 != a3->Data1
        || v11[1] != *(_DWORD *)&a3->Data2
        || v11[2] != *(_DWORD *)a3->Data4
        || v11[3] != *(_DWORD *)&a3->Data4[4] )
      {
        goto LABEL_22;
      }
      v12 = 0;
    }
    else
    {
      v12 = 1;
    }
    v13 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v6 + 2);
    if ( v13 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      break;
    result = v13(a1, a3, a4, *((_QWORD *)v6 + 1));
    if ( !(_DWORD)result || !v12 && (int)result < 0 )
      return result;
LABEL_22:
    v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
    if ( !*((_QWORD *)v6 + 2) )
      return 2147500034LL;
  }
  v9 = *((_QWORD *)v6 + 1);
LABEL_9:
  v10 = &a1[v9];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
  result = 0;
  *a4 = v10;
  return result;
}

```

## disassembly

```asm
0x180009bb0  push    rbx
0x180009bb2  push    rbp
0x180009bb3  push    rsi
0x180009bb4  push    rdi
0x180009bb5  push    r14
0x180009bb7  sub     rsp, 30h
0x180009bbb  mov     rsi, r9
0x180009bbe  mov     rdi, r8
0x180009bc1  mov     rbx, rdx
0x180009bc4  mov     r14, rcx
0x180009bc7  test    rcx, rcx
0x180009bca  jz      loc_180009CA4
0x180009bd0  test    rdx, rdx
0x180009bd3  jz      loc_180009CA4
0x180009bd9  test    r9, r9
0x180009bdc  jnz     short loc_180009BE8
0x180009bde  mov     eax, 80004003h
0x180009be3  jmp     loc_180009CA9
0x180009be8  mov     qword ptr [r9], 0
0x180009bef  cmp     dword ptr [r8], 0
0x180009bf3  jnz     short loc_180009C2D
0x180009bf5  cmp     dword ptr [r8+4], 0
0x180009bfa  jnz     short loc_180009C2D
0x180009bfc  cmp     dword ptr [r8+8], 0C0h
0x180009c04  jnz     short loc_180009C2D
0x180009c06  cmp     dword ptr [r8+0Ch], 46000000h
0x180009c0e  jnz     short loc_180009C2D
0x180009c10  mov     rbx, [rdx+8]
0x180009c14  add     rbx, r14
0x180009c17  mov     rcx, rbx
0x180009c1a  mov     rax, [rbx]
0x180009c1d  mov     rax, [rax+8]
0x180009c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c26  xor     eax, eax
0x180009c28  mov     [rsi], rbx
0x180009c2b  jmp     short loc_180009CA9
0x180009c2d  cmp     qword ptr [rdx+10h], 0
0x180009c32  jz      short loc_180009C94
0x180009c34  mov     rcx, [rbx]
0x180009c37  test    rcx, rcx
0x180009c3a  jnz     short loc_180009C41
0x180009c3c  lea     ebp, [rcx+1]
0x180009c3f  jmp     short loc_180009C61
0x180009c41  mov     eax, [rdi]
0x180009c43  cmp     [rcx], eax
0x180009c45  jnz     short loc_180009C89
0x180009c47  mov     eax, [rdi+4]
0x180009c4a  cmp     [rcx+4], eax
0x180009c4d  jnz     short loc_180009C89
0x180009c4f  mov     eax, [rdi+8]
0x180009c52  cmp     [rcx+8], eax
0x180009c55  jnz     short loc_180009C89
0x180009c57  mov     eax, [rdi+0Ch]
0x180009c5a  cmp     [rcx+0Ch], eax
0x180009c5d  jnz     short loc_180009C89
0x180009c5f  xor     ebp, ebp
0x180009c61  mov     rax, [rbx+10h]
0x180009c65  cmp     rax, 1
0x180009c69  jz      short loc_180009C9B
0x180009c6b  mov     r9, [rbx+8]
0x180009c6f  mov     r8, rsi
0x180009c72  mov     rdx, rdi
0x180009c75  mov     rcx, r14
0x180009c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c7d  test    eax, eax
0x180009c7f  jz      short loc_180009CA9
0x180009c81  test    ebp, ebp
0x180009c83  jnz     short loc_180009C89
0x180009c85  test    eax, eax
0x180009c87  js      short loc_180009CA9
0x180009c89  add     rbx, 18h
0x180009c8d  cmp     qword ptr [rbx+10h], 0
0x180009c92  jnz     short loc_180009C34
0x180009c94  mov     eax, 80004002h
0x180009c99  jmp     short loc_180009CA9
0x180009c9b  mov     rbx, [rbx+8]
0x180009c9f  jmp     loc_180009C14
0x180009ca4  mov     eax, 80070057h
0x180009ca9  add     rsp, 30h
0x180009cad  pop     r14
0x180009caf  pop     rdi
0x180009cb0  pop     rsi
0x180009cb1  pop     rbp
0x180009cb2  pop     rbx
0x180009cb3  retn
```
