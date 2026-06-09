# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180011b14`
- end: `0x180011c18`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012100`
- `0x1800121b0`
- `0x1800121f0`

## callees

- `0x180011b14`
- `0x180017010`

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
0x180011b14  push    rbx
0x180011b16  push    rbp
0x180011b17  push    rsi
0x180011b18  push    rdi
0x180011b19  push    r14
0x180011b1b  sub     rsp, 30h
0x180011b1f  mov     rsi, r9
0x180011b22  mov     rdi, r8
0x180011b25  mov     rbx, rdx
0x180011b28  mov     r14, rcx
0x180011b2b  test    rcx, rcx
0x180011b2e  jz      loc_180011C08
0x180011b34  test    rdx, rdx
0x180011b37  jz      loc_180011C08
0x180011b3d  test    r9, r9
0x180011b40  jnz     short loc_180011B4C
0x180011b42  mov     eax, 80004003h
0x180011b47  jmp     loc_180011C0D
0x180011b4c  mov     qword ptr [r9], 0
0x180011b53  cmp     dword ptr [r8], 0
0x180011b57  jnz     short loc_180011B91
0x180011b59  cmp     dword ptr [r8+4], 0
0x180011b5e  jnz     short loc_180011B91
0x180011b60  cmp     dword ptr [r8+8], 0C0h
0x180011b68  jnz     short loc_180011B91
0x180011b6a  cmp     dword ptr [r8+0Ch], 46000000h
0x180011b72  jnz     short loc_180011B91
0x180011b74  mov     rbx, [rdx+8]
0x180011b78  add     rbx, r14
0x180011b7b  mov     rcx, rbx
0x180011b7e  mov     rax, [rbx]
0x180011b81  mov     rax, [rax+8]
0x180011b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b8a  xor     eax, eax
0x180011b8c  mov     [rsi], rbx
0x180011b8f  jmp     short loc_180011C0D
0x180011b91  cmp     qword ptr [rdx+10h], 0
0x180011b96  jz      short loc_180011BF8
0x180011b98  mov     rcx, [rbx]
0x180011b9b  test    rcx, rcx
0x180011b9e  jnz     short loc_180011BA5
0x180011ba0  lea     ebp, [rcx+1]
0x180011ba3  jmp     short loc_180011BC5
0x180011ba5  mov     eax, [rdi]
0x180011ba7  cmp     [rcx], eax
0x180011ba9  jnz     short loc_180011BED
0x180011bab  mov     eax, [rdi+4]
0x180011bae  cmp     [rcx+4], eax
0x180011bb1  jnz     short loc_180011BED
0x180011bb3  mov     eax, [rdi+8]
0x180011bb6  cmp     [rcx+8], eax
0x180011bb9  jnz     short loc_180011BED
0x180011bbb  mov     eax, [rdi+0Ch]
0x180011bbe  cmp     [rcx+0Ch], eax
0x180011bc1  jnz     short loc_180011BED
0x180011bc3  xor     ebp, ebp
0x180011bc5  mov     rax, [rbx+10h]
0x180011bc9  cmp     rax, 1
0x180011bcd  jz      short loc_180011BFF
0x180011bcf  mov     r9, [rbx+8]
0x180011bd3  mov     r8, rsi
0x180011bd6  mov     rdx, rdi
0x180011bd9  mov     rcx, r14
0x180011bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011be1  test    eax, eax
0x180011be3  jz      short loc_180011C0D
0x180011be5  test    ebp, ebp
0x180011be7  jnz     short loc_180011BED
0x180011be9  test    eax, eax
0x180011beb  js      short loc_180011C0D
0x180011bed  add     rbx, 18h
0x180011bf1  cmp     qword ptr [rbx+10h], 0
0x180011bf6  jnz     short loc_180011B98
0x180011bf8  mov     eax, 80004002h
0x180011bfd  jmp     short loc_180011C0D
0x180011bff  mov     rbx, [rbx+8]
0x180011c03  jmp     loc_180011B78
0x180011c08  mov     eax, 80070057h
0x180011c0d  add     rsp, 30h
0x180011c11  pop     r14
0x180011c13  pop     rdi
0x180011c14  pop     rsi
0x180011c15  pop     rbp
0x180011c16  pop     rbx
0x180011c17  retn
```
