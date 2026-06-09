# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800086a8`
- end: `0x1800087ad`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `261`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000af50`
- `0x18000af90`

## callees

- `0x1800086a8`
- `0x180014010`

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
0x1800086a8  push    rbx
0x1800086aa  push    rbp
0x1800086ab  push    rsi
0x1800086ac  push    rdi
0x1800086ad  push    r14
0x1800086af  sub     rsp, 30h
0x1800086b3  mov     rsi, r9
0x1800086b6  mov     rdi, r8
0x1800086b9  mov     rbx, rdx
0x1800086bc  mov     r14, rcx
0x1800086bf  test    rcx, rcx
0x1800086c2  jz      loc_18000879C
0x1800086c8  test    rdx, rdx
0x1800086cb  jz      loc_18000879C
0x1800086d1  test    r9, r9
0x1800086d4  jnz     short loc_1800086E0
0x1800086d6  mov     eax, 80004003h
0x1800086db  jmp     loc_1800087A1
0x1800086e0  mov     qword ptr [r9], 0
0x1800086e7  cmp     dword ptr [r8], 0
0x1800086eb  jnz     short loc_180008725
0x1800086ed  cmp     dword ptr [r8+4], 0
0x1800086f2  jnz     short loc_180008725
0x1800086f4  cmp     dword ptr [r8+8], 0C0h
0x1800086fc  jnz     short loc_180008725
0x1800086fe  cmp     dword ptr [r8+0Ch], 46000000h
0x180008706  jnz     short loc_180008725
0x180008708  mov     rbx, [rdx+8]
0x18000870c  add     rbx, r14
0x18000870f  mov     rcx, rbx
0x180008712  mov     rax, [rbx]
0x180008715  mov     rax, [rax+8]
0x180008719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000871e  xor     eax, eax
0x180008720  mov     [rsi], rbx
0x180008723  jmp     short loc_1800087A1
0x180008725  cmp     qword ptr [rdx+10h], 0
0x18000872a  jz      short loc_18000878C
0x18000872c  mov     rcx, [rbx]
0x18000872f  test    rcx, rcx
0x180008732  jnz     short loc_180008739
0x180008734  lea     ebp, [rcx+1]
0x180008737  jmp     short loc_180008759
0x180008739  mov     eax, [rdi]
0x18000873b  cmp     [rcx], eax
0x18000873d  jnz     short loc_180008781
0x18000873f  mov     eax, [rdi+4]
0x180008742  cmp     [rcx+4], eax
0x180008745  jnz     short loc_180008781
0x180008747  mov     eax, [rdi+8]
0x18000874a  cmp     [rcx+8], eax
0x18000874d  jnz     short loc_180008781
0x18000874f  mov     eax, [rdi+0Ch]
0x180008752  cmp     [rcx+0Ch], eax
0x180008755  jnz     short loc_180008781
0x180008757  xor     ebp, ebp
0x180008759  mov     rax, [rbx+10h]
0x18000875d  cmp     rax, 1
0x180008761  jz      short loc_180008793
0x180008763  mov     r9, [rbx+8]
0x180008767  mov     r8, rsi
0x18000876a  mov     rdx, rdi
0x18000876d  mov     rcx, r14
0x180008770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008775  test    eax, eax
0x180008777  jz      short loc_1800087A1
0x180008779  test    ebp, ebp
0x18000877b  jnz     short loc_180008781
0x18000877d  test    eax, eax
0x18000877f  js      short loc_1800087A1
0x180008781  add     rbx, 18h
0x180008785  cmp     qword ptr [rbx+10h], 0
0x18000878a  jnz     short loc_18000872C
0x18000878c  mov     eax, 80004002h
0x180008791  jmp     short loc_1800087A1
0x180008793  mov     rbx, [rbx+8]
0x180008797  jmp     loc_18000870C
0x18000879c  mov     eax, 80070057h
0x1800087a1  add     rsp, 30h
0x1800087a5  pop     r14
0x1800087a7  pop     rdi
0x1800087a8  pop     rsi
0x1800087a9  pop     rbp
0x1800087aa  pop     rbx
0x1800087ab  retn
```
