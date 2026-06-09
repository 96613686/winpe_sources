# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1400059b4`
- end: `0x140005ab8`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000310c`
- `0x140007540`
- `0x140007640`
- `0x140007660`
- `0x140007680`
- `0x1400076a0`
- `0x1400076e0`
- `0x14000b550`
- `0x14000b5c0`
- `0x14000b650`
- `0x14000b6a0`

## callees

- `0x1400059b4`
- `0x14000f010`

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
0x1400059b4  push    rbx
0x1400059b6  push    rbp
0x1400059b7  push    rsi
0x1400059b8  push    rdi
0x1400059b9  push    r14
0x1400059bb  sub     rsp, 30h
0x1400059bf  mov     rsi, r9
0x1400059c2  mov     rdi, r8
0x1400059c5  mov     rbx, rdx
0x1400059c8  mov     r14, rcx
0x1400059cb  test    rcx, rcx
0x1400059ce  jz      loc_140005AA8
0x1400059d4  test    rdx, rdx
0x1400059d7  jz      loc_140005AA8
0x1400059dd  test    r9, r9
0x1400059e0  jnz     short loc_1400059EC
0x1400059e2  mov     eax, 80004003h
0x1400059e7  jmp     loc_140005AAD
0x1400059ec  mov     qword ptr [r9], 0
0x1400059f3  cmp     dword ptr [r8], 0
0x1400059f7  jnz     short loc_140005A31
0x1400059f9  cmp     dword ptr [r8+4], 0
0x1400059fe  jnz     short loc_140005A31
0x140005a00  cmp     dword ptr [r8+8], 0C0h
0x140005a08  jnz     short loc_140005A31
0x140005a0a  cmp     dword ptr [r8+0Ch], 46000000h
0x140005a12  jnz     short loc_140005A31
0x140005a14  mov     rbx, [rdx+8]
0x140005a18  add     rbx, r14
0x140005a1b  mov     rcx, rbx
0x140005a1e  mov     rax, [rbx]
0x140005a21  mov     rax, [rax+8]
0x140005a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a2a  xor     eax, eax
0x140005a2c  mov     [rsi], rbx
0x140005a2f  jmp     short loc_140005AAD
0x140005a31  cmp     qword ptr [rdx+10h], 0
0x140005a36  jz      short loc_140005A98
0x140005a38  mov     rcx, [rbx]
0x140005a3b  test    rcx, rcx
0x140005a3e  jnz     short loc_140005A45
0x140005a40  lea     ebp, [rcx+1]
0x140005a43  jmp     short loc_140005A65
0x140005a45  mov     eax, [rdi]
0x140005a47  cmp     [rcx], eax
0x140005a49  jnz     short loc_140005A8D
0x140005a4b  mov     eax, [rdi+4]
0x140005a4e  cmp     [rcx+4], eax
0x140005a51  jnz     short loc_140005A8D
0x140005a53  mov     eax, [rdi+8]
0x140005a56  cmp     [rcx+8], eax
0x140005a59  jnz     short loc_140005A8D
0x140005a5b  mov     eax, [rdi+0Ch]
0x140005a5e  cmp     [rcx+0Ch], eax
0x140005a61  jnz     short loc_140005A8D
0x140005a63  xor     ebp, ebp
0x140005a65  mov     rax, [rbx+10h]
0x140005a69  cmp     rax, 1
0x140005a6d  jz      short loc_140005A9F
0x140005a6f  mov     r9, [rbx+8]
0x140005a73  mov     r8, rsi
0x140005a76  mov     rdx, rdi
0x140005a79  mov     rcx, r14
0x140005a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a81  test    eax, eax
0x140005a83  jz      short loc_140005AAD
0x140005a85  test    ebp, ebp
0x140005a87  jnz     short loc_140005A8D
0x140005a89  test    eax, eax
0x140005a8b  js      short loc_140005AAD
0x140005a8d  add     rbx, 18h
0x140005a91  cmp     qword ptr [rbx+10h], 0
0x140005a96  jnz     short loc_140005A38
0x140005a98  mov     eax, 80004002h
0x140005a9d  jmp     short loc_140005AAD
0x140005a9f  mov     rbx, [rbx+8]
0x140005aa3  jmp     loc_140005A18
0x140005aa8  mov     eax, 80070057h
0x140005aad  add     rsp, 30h
0x140005ab1  pop     r14
0x140005ab3  pop     rdi
0x140005ab4  pop     rsi
0x140005ab5  pop     rbp
0x140005ab6  pop     rbx
0x140005ab7  retn
```
