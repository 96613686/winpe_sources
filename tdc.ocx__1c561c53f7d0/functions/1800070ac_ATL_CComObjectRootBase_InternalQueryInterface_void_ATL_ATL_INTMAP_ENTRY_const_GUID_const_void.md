# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800070ac`
- end: `0x1800071b0`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003fbc`
- `0x18000415c`
- `0x180005240`
- `0x180008680`
- `0x1800086a0`
- `0x1800086c0`
- `0x180011450`
- `0x180011500`

## callees

- `0x1800070ac`
- `0x180015010`

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
0x1800070ac  push    rbx
0x1800070ae  push    rbp
0x1800070af  push    rsi
0x1800070b0  push    rdi
0x1800070b1  push    r14
0x1800070b3  sub     rsp, 30h
0x1800070b7  mov     rsi, r9
0x1800070ba  mov     rdi, r8
0x1800070bd  mov     rbx, rdx
0x1800070c0  mov     r14, rcx
0x1800070c3  test    rcx, rcx
0x1800070c6  jz      loc_1800071A0
0x1800070cc  test    rdx, rdx
0x1800070cf  jz      loc_1800071A0
0x1800070d5  test    r9, r9
0x1800070d8  jnz     short loc_1800070E4
0x1800070da  mov     eax, 80004003h
0x1800070df  jmp     loc_1800071A5
0x1800070e4  mov     qword ptr [r9], 0
0x1800070eb  cmp     dword ptr [r8], 0
0x1800070ef  jnz     short loc_180007129
0x1800070f1  cmp     dword ptr [r8+4], 0
0x1800070f6  jnz     short loc_180007129
0x1800070f8  cmp     dword ptr [r8+8], 0C0h
0x180007100  jnz     short loc_180007129
0x180007102  cmp     dword ptr [r8+0Ch], 46000000h
0x18000710a  jnz     short loc_180007129
0x18000710c  mov     rbx, [rdx+8]
0x180007110  add     rbx, r14
0x180007113  mov     rcx, rbx
0x180007116  mov     rax, [rbx]
0x180007119  mov     rax, [rax+8]
0x18000711d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007122  xor     eax, eax
0x180007124  mov     [rsi], rbx
0x180007127  jmp     short loc_1800071A5
0x180007129  cmp     qword ptr [rdx+10h], 0
0x18000712e  jz      short loc_180007190
0x180007130  mov     rcx, [rbx]
0x180007133  test    rcx, rcx
0x180007136  jnz     short loc_18000713D
0x180007138  lea     ebp, [rcx+1]
0x18000713b  jmp     short loc_18000715D
0x18000713d  mov     eax, [rdi]
0x18000713f  cmp     [rcx], eax
0x180007141  jnz     short loc_180007185
0x180007143  mov     eax, [rdi+4]
0x180007146  cmp     [rcx+4], eax
0x180007149  jnz     short loc_180007185
0x18000714b  mov     eax, [rdi+8]
0x18000714e  cmp     [rcx+8], eax
0x180007151  jnz     short loc_180007185
0x180007153  mov     eax, [rdi+0Ch]
0x180007156  cmp     [rcx+0Ch], eax
0x180007159  jnz     short loc_180007185
0x18000715b  xor     ebp, ebp
0x18000715d  mov     rax, [rbx+10h]
0x180007161  cmp     rax, 1
0x180007165  jz      short loc_180007197
0x180007167  mov     r9, [rbx+8]
0x18000716b  mov     r8, rsi
0x18000716e  mov     rdx, rdi
0x180007171  mov     rcx, r14
0x180007174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007179  test    eax, eax
0x18000717b  jz      short loc_1800071A5
0x18000717d  test    ebp, ebp
0x18000717f  jnz     short loc_180007185
0x180007181  test    eax, eax
0x180007183  js      short loc_1800071A5
0x180007185  add     rbx, 18h
0x180007189  cmp     qword ptr [rbx+10h], 0
0x18000718e  jnz     short loc_180007130
0x180007190  mov     eax, 80004002h
0x180007195  jmp     short loc_1800071A5
0x180007197  mov     rbx, [rbx+8]
0x18000719b  jmp     loc_180007110
0x1800071a0  mov     eax, 80070057h
0x1800071a5  add     rsp, 30h
0x1800071a9  pop     r14
0x1800071ab  pop     rdi
0x1800071ac  pop     rsi
0x1800071ad  pop     rbp
0x1800071ae  pop     rbx
0x1800071af  retn
```
