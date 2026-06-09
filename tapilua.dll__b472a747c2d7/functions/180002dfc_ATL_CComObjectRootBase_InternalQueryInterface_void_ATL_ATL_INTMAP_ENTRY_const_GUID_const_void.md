# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180002dfc`
- end: `0x180002f00`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003360`
- `0x180003380`

## callees

- `0x180002dfc`
- `0x180006010`

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
0x180002dfc  push    rbx
0x180002dfe  push    rbp
0x180002dff  push    rsi
0x180002e00  push    rdi
0x180002e01  push    r14
0x180002e03  sub     rsp, 30h
0x180002e07  mov     rsi, r9
0x180002e0a  mov     rdi, r8
0x180002e0d  mov     rbx, rdx
0x180002e10  mov     r14, rcx
0x180002e13  test    rcx, rcx
0x180002e16  jz      loc_180002EF0
0x180002e1c  test    rdx, rdx
0x180002e1f  jz      loc_180002EF0
0x180002e25  test    r9, r9
0x180002e28  jnz     short loc_180002E34
0x180002e2a  mov     eax, 80004003h
0x180002e2f  jmp     loc_180002EF5
0x180002e34  mov     qword ptr [r9], 0
0x180002e3b  cmp     dword ptr [r8], 0
0x180002e3f  jnz     short loc_180002E79
0x180002e41  cmp     dword ptr [r8+4], 0
0x180002e46  jnz     short loc_180002E79
0x180002e48  cmp     dword ptr [r8+8], 0C0h
0x180002e50  jnz     short loc_180002E79
0x180002e52  cmp     dword ptr [r8+0Ch], 46000000h
0x180002e5a  jnz     short loc_180002E79
0x180002e5c  mov     rbx, [rdx+8]
0x180002e60  add     rbx, r14
0x180002e63  mov     rcx, rbx
0x180002e66  mov     rax, [rbx]
0x180002e69  mov     rax, [rax+8]
0x180002e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e72  xor     eax, eax
0x180002e74  mov     [rsi], rbx
0x180002e77  jmp     short loc_180002EF5
0x180002e79  cmp     qword ptr [rdx+10h], 0
0x180002e7e  jz      short loc_180002EE0
0x180002e80  mov     rcx, [rbx]
0x180002e83  test    rcx, rcx
0x180002e86  jnz     short loc_180002E8D
0x180002e88  lea     ebp, [rcx+1]
0x180002e8b  jmp     short loc_180002EAD
0x180002e8d  mov     eax, [rdi]
0x180002e8f  cmp     [rcx], eax
0x180002e91  jnz     short loc_180002ED5
0x180002e93  mov     eax, [rdi+4]
0x180002e96  cmp     [rcx+4], eax
0x180002e99  jnz     short loc_180002ED5
0x180002e9b  mov     eax, [rdi+8]
0x180002e9e  cmp     [rcx+8], eax
0x180002ea1  jnz     short loc_180002ED5
0x180002ea3  mov     eax, [rdi+0Ch]
0x180002ea6  cmp     [rcx+0Ch], eax
0x180002ea9  jnz     short loc_180002ED5
0x180002eab  xor     ebp, ebp
0x180002ead  mov     rax, [rbx+10h]
0x180002eb1  cmp     rax, 1
0x180002eb5  jz      short loc_180002EE7
0x180002eb7  mov     r9, [rbx+8]
0x180002ebb  mov     r8, rsi
0x180002ebe  mov     rdx, rdi
0x180002ec1  mov     rcx, r14
0x180002ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec9  test    eax, eax
0x180002ecb  jz      short loc_180002EF5
0x180002ecd  test    ebp, ebp
0x180002ecf  jnz     short loc_180002ED5
0x180002ed1  test    eax, eax
0x180002ed3  js      short loc_180002EF5
0x180002ed5  add     rbx, 18h
0x180002ed9  cmp     qword ptr [rbx+10h], 0
0x180002ede  jnz     short loc_180002E80
0x180002ee0  mov     eax, 80004002h
0x180002ee5  jmp     short loc_180002EF5
0x180002ee7  mov     rbx, [rbx+8]
0x180002eeb  jmp     loc_180002E60
0x180002ef0  mov     eax, 80070057h
0x180002ef5  add     rsp, 30h
0x180002ef9  pop     r14
0x180002efb  pop     rdi
0x180002efc  pop     rsi
0x180002efd  pop     rbp
0x180002efe  pop     rbx
0x180002eff  retn
```
