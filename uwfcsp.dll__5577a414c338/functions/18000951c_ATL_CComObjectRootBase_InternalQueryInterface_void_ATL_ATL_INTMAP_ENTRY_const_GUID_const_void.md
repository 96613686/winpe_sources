# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18000951c`
- end: `0x180009620`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a020`
- `0x18000e2d0`
- `0x18000f870`

## callees

- `0x18000951c`
- `0x18001b010`

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
0x18000951c  push    rbx
0x18000951e  push    rbp
0x18000951f  push    rsi
0x180009520  push    rdi
0x180009521  push    r14
0x180009523  sub     rsp, 30h
0x180009527  mov     rsi, r9
0x18000952a  mov     rdi, r8
0x18000952d  mov     rbx, rdx
0x180009530  mov     r14, rcx
0x180009533  test    rcx, rcx
0x180009536  jz      loc_180009610
0x18000953c  test    rdx, rdx
0x18000953f  jz      loc_180009610
0x180009545  test    r9, r9
0x180009548  jnz     short loc_180009554
0x18000954a  mov     eax, 80004003h
0x18000954f  jmp     loc_180009615
0x180009554  mov     qword ptr [r9], 0
0x18000955b  cmp     dword ptr [r8], 0
0x18000955f  jnz     short loc_180009599
0x180009561  cmp     dword ptr [r8+4], 0
0x180009566  jnz     short loc_180009599
0x180009568  cmp     dword ptr [r8+8], 0C0h
0x180009570  jnz     short loc_180009599
0x180009572  cmp     dword ptr [r8+0Ch], 46000000h
0x18000957a  jnz     short loc_180009599
0x18000957c  mov     rbx, [rdx+8]
0x180009580  add     rbx, r14
0x180009583  mov     rcx, rbx
0x180009586  mov     rax, [rbx]
0x180009589  mov     rax, [rax+8]
0x18000958d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009592  xor     eax, eax
0x180009594  mov     [rsi], rbx
0x180009597  jmp     short loc_180009615
0x180009599  cmp     qword ptr [rdx+10h], 0
0x18000959e  jz      short loc_180009600
0x1800095a0  mov     rcx, [rbx]
0x1800095a3  test    rcx, rcx
0x1800095a6  jnz     short loc_1800095AD
0x1800095a8  lea     ebp, [rcx+1]
0x1800095ab  jmp     short loc_1800095CD
0x1800095ad  mov     eax, [rdi]
0x1800095af  cmp     [rcx], eax
0x1800095b1  jnz     short loc_1800095F5
0x1800095b3  mov     eax, [rdi+4]
0x1800095b6  cmp     [rcx+4], eax
0x1800095b9  jnz     short loc_1800095F5
0x1800095bb  mov     eax, [rdi+8]
0x1800095be  cmp     [rcx+8], eax
0x1800095c1  jnz     short loc_1800095F5
0x1800095c3  mov     eax, [rdi+0Ch]
0x1800095c6  cmp     [rcx+0Ch], eax
0x1800095c9  jnz     short loc_1800095F5
0x1800095cb  xor     ebp, ebp
0x1800095cd  mov     rax, [rbx+10h]
0x1800095d1  cmp     rax, 1
0x1800095d5  jz      short loc_180009607
0x1800095d7  mov     r9, [rbx+8]
0x1800095db  mov     r8, rsi
0x1800095de  mov     rdx, rdi
0x1800095e1  mov     rcx, r14
0x1800095e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e9  test    eax, eax
0x1800095eb  jz      short loc_180009615
0x1800095ed  test    ebp, ebp
0x1800095ef  jnz     short loc_1800095F5
0x1800095f1  test    eax, eax
0x1800095f3  js      short loc_180009615
0x1800095f5  add     rbx, 18h
0x1800095f9  cmp     qword ptr [rbx+10h], 0
0x1800095fe  jnz     short loc_1800095A0
0x180009600  mov     eax, 80004002h
0x180009605  jmp     short loc_180009615
0x180009607  mov     rbx, [rbx+8]
0x18000960b  jmp     loc_180009580
0x180009610  mov     eax, 80070057h
0x180009615  add     rsp, 30h
0x180009619  pop     r14
0x18000961b  pop     rdi
0x18000961c  pop     rsi
0x18000961d  pop     rbp
0x18000961e  pop     rbx
0x18000961f  retn
```
