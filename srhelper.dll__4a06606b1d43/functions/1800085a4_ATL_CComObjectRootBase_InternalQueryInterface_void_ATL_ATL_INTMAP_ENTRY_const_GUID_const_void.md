# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800085a4`
- end: `0x1800086a8`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008b40`
- `0x180008b60`

## callees

- `0x1800085a4`
- `0x180016010`

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
0x1800085a4  push    rbx
0x1800085a6  push    rbp
0x1800085a7  push    rsi
0x1800085a8  push    rdi
0x1800085a9  push    r14
0x1800085ab  sub     rsp, 30h
0x1800085af  mov     rsi, r9
0x1800085b2  mov     rdi, r8
0x1800085b5  mov     rbx, rdx
0x1800085b8  mov     r14, rcx
0x1800085bb  test    rcx, rcx
0x1800085be  jz      loc_180008698
0x1800085c4  test    rdx, rdx
0x1800085c7  jz      loc_180008698
0x1800085cd  test    r9, r9
0x1800085d0  jnz     short loc_1800085DC
0x1800085d2  mov     eax, 80004003h
0x1800085d7  jmp     loc_18000869D
0x1800085dc  mov     qword ptr [r9], 0
0x1800085e3  cmp     dword ptr [r8], 0
0x1800085e7  jnz     short loc_180008621
0x1800085e9  cmp     dword ptr [r8+4], 0
0x1800085ee  jnz     short loc_180008621
0x1800085f0  cmp     dword ptr [r8+8], 0C0h
0x1800085f8  jnz     short loc_180008621
0x1800085fa  cmp     dword ptr [r8+0Ch], 46000000h
0x180008602  jnz     short loc_180008621
0x180008604  mov     rbx, [rdx+8]
0x180008608  add     rbx, r14
0x18000860b  mov     rcx, rbx
0x18000860e  mov     rax, [rbx]
0x180008611  mov     rax, [rax+8]
0x180008615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000861a  xor     eax, eax
0x18000861c  mov     [rsi], rbx
0x18000861f  jmp     short loc_18000869D
0x180008621  cmp     qword ptr [rdx+10h], 0
0x180008626  jz      short loc_180008688
0x180008628  mov     rcx, [rbx]
0x18000862b  test    rcx, rcx
0x18000862e  jnz     short loc_180008635
0x180008630  lea     ebp, [rcx+1]
0x180008633  jmp     short loc_180008655
0x180008635  mov     eax, [rdi]
0x180008637  cmp     [rcx], eax
0x180008639  jnz     short loc_18000867D
0x18000863b  mov     eax, [rdi+4]
0x18000863e  cmp     [rcx+4], eax
0x180008641  jnz     short loc_18000867D
0x180008643  mov     eax, [rdi+8]
0x180008646  cmp     [rcx+8], eax
0x180008649  jnz     short loc_18000867D
0x18000864b  mov     eax, [rdi+0Ch]
0x18000864e  cmp     [rcx+0Ch], eax
0x180008651  jnz     short loc_18000867D
0x180008653  xor     ebp, ebp
0x180008655  mov     rax, [rbx+10h]
0x180008659  cmp     rax, 1
0x18000865d  jz      short loc_18000868F
0x18000865f  mov     r9, [rbx+8]
0x180008663  mov     r8, rsi
0x180008666  mov     rdx, rdi
0x180008669  mov     rcx, r14
0x18000866c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008671  test    eax, eax
0x180008673  jz      short loc_18000869D
0x180008675  test    ebp, ebp
0x180008677  jnz     short loc_18000867D
0x180008679  test    eax, eax
0x18000867b  js      short loc_18000869D
0x18000867d  add     rbx, 18h
0x180008681  cmp     qword ptr [rbx+10h], 0
0x180008686  jnz     short loc_180008628
0x180008688  mov     eax, 80004002h
0x18000868d  jmp     short loc_18000869D
0x18000868f  mov     rbx, [rbx+8]
0x180008693  jmp     loc_180008608
0x180008698  mov     eax, 80070057h
0x18000869d  add     rsp, 30h
0x1800086a1  pop     r14
0x1800086a3  pop     rdi
0x1800086a4  pop     rsi
0x1800086a5  pop     rbp
0x1800086a6  pop     rbx
0x1800086a7  retn
```
