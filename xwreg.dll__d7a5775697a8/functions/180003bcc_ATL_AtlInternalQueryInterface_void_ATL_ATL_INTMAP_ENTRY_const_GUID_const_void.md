# ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180003bcc`
- end: `0x180003ca2`
- name: `?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z`
- size: `214`
- prototype: `int(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180004f90`
- `0x180004ff0`
- `0x180005050`
- `0x1800050d0`
- `0x1800050f0`
- `0x180005110`
- `0x180005130`

## callees

- `0x180003bcc`
- `0x180004ab4`
- `0x1800066e0`
- `0x180013010`

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
        if ( !(unsigned int)InlineIsEqualGUID(*(_QWORD *)v6) )
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
0x180003bcc  push    rbx
0x180003bce  push    rbp
0x180003bcf  push    rsi
0x180003bd0  push    rdi
0x180003bd1  push    r14
0x180003bd3  sub     rsp, 30h
0x180003bd7  mov     rdi, r9
0x180003bda  mov     r14, r8
0x180003bdd  mov     rbx, rdx
0x180003be0  mov     rsi, rcx
0x180003be3  test    rcx, rcx
0x180003be6  jz      loc_180003C92
0x180003bec  test    rdx, rdx
0x180003bef  jz      loc_180003C92
0x180003bf5  test    r9, r9
0x180003bf8  jnz     short loc_180003C04
0x180003bfa  mov     eax, 80004003h
0x180003bff  jmp     loc_180003C97
0x180003c04  mov     rcx, r14; struct _GUID *
0x180003c07  mov     qword ptr [r9], 0
0x180003c0e  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180003c13  test    eax, eax
0x180003c15  jz      short loc_180003C34
0x180003c17  mov     rbx, [rdx+8]
0x180003c1b  add     rbx, rsi
0x180003c1e  mov     rcx, rbx
0x180003c21  mov     rax, [rbx]
0x180003c24  mov     rax, [rax+8]
0x180003c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c2d  xor     eax, eax
0x180003c2f  mov     [rdi], rbx
0x180003c32  jmp     short loc_180003C97
0x180003c34  mov     r10, [rbx+10h]
0x180003c38  test    r10, r10
0x180003c3b  jz      short loc_180003C8B
0x180003c3d  mov     rcx, [rbx]
0x180003c40  test    rcx, rcx
0x180003c43  jnz     short loc_180003C4A
0x180003c45  lea     ebp, [rcx+1]
0x180003c48  jmp     short loc_180003C58
0x180003c4a  mov     rdx, r14
0x180003c4d  xor     ebp, ebp
0x180003c4f  call    InlineIsEqualGUID
0x180003c54  test    eax, eax
0x180003c56  jz      short loc_180003C7F
0x180003c58  cmp     r10, 1
0x180003c5c  jz      short loc_180003C85
0x180003c5e  mov     r9, [rbx+8]
0x180003c62  mov     r8, rdi
0x180003c65  mov     rdx, r14
0x180003c68  mov     rcx, rsi
0x180003c6b  mov     rax, r10
0x180003c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c73  test    eax, eax
0x180003c75  jz      short loc_180003C97
0x180003c77  test    ebp, ebp
0x180003c79  jnz     short loc_180003C7F
0x180003c7b  test    eax, eax
0x180003c7d  js      short loc_180003C97
0x180003c7f  add     rbx, 18h
0x180003c83  jmp     short loc_180003C34
0x180003c85  mov     rbx, [rbx+8]
0x180003c89  jmp     short loc_180003C1B
0x180003c8b  mov     eax, 80004002h
0x180003c90  jmp     short loc_180003C97
0x180003c92  mov     eax, 80070057h
0x180003c97  add     rsp, 30h
0x180003c9b  pop     r14
0x180003c9d  pop     rdi
0x180003c9e  pop     rsi
0x180003c9f  pop     rbp
0x180003ca0  pop     rbx
0x180003ca1  retn
```
