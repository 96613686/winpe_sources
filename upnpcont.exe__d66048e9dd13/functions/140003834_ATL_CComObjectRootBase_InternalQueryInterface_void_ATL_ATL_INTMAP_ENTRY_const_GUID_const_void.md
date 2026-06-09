# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x140003834`
- end: `0x140003938`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004200`
- `0x140004220`

## callees

- `0x140003834`
- `0x140007010`

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
0x140003834  push    rbx
0x140003836  push    rbp
0x140003837  push    rsi
0x140003838  push    rdi
0x140003839  push    r14
0x14000383b  sub     rsp, 30h
0x14000383f  mov     rsi, r9
0x140003842  mov     rdi, r8
0x140003845  mov     rbx, rdx
0x140003848  mov     r14, rcx
0x14000384b  test    rcx, rcx
0x14000384e  jz      loc_140003928
0x140003854  test    rdx, rdx
0x140003857  jz      loc_140003928
0x14000385d  test    r9, r9
0x140003860  jnz     short loc_14000386C
0x140003862  mov     eax, 80004003h
0x140003867  jmp     loc_14000392D
0x14000386c  mov     qword ptr [r9], 0
0x140003873  cmp     dword ptr [r8], 0
0x140003877  jnz     short loc_1400038B1
0x140003879  cmp     dword ptr [r8+4], 0
0x14000387e  jnz     short loc_1400038B1
0x140003880  cmp     dword ptr [r8+8], 0C0h
0x140003888  jnz     short loc_1400038B1
0x14000388a  cmp     dword ptr [r8+0Ch], 46000000h
0x140003892  jnz     short loc_1400038B1
0x140003894  mov     rbx, [rdx+8]
0x140003898  add     rbx, r14
0x14000389b  mov     rcx, rbx
0x14000389e  mov     rax, [rbx]
0x1400038a1  mov     rax, [rax+8]
0x1400038a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038aa  xor     eax, eax
0x1400038ac  mov     [rsi], rbx
0x1400038af  jmp     short loc_14000392D
0x1400038b1  cmp     qword ptr [rdx+10h], 0
0x1400038b6  jz      short loc_140003918
0x1400038b8  mov     rcx, [rbx]
0x1400038bb  test    rcx, rcx
0x1400038be  jnz     short loc_1400038C5
0x1400038c0  lea     ebp, [rcx+1]
0x1400038c3  jmp     short loc_1400038E5
0x1400038c5  mov     eax, [rdi]
0x1400038c7  cmp     [rcx], eax
0x1400038c9  jnz     short loc_14000390D
0x1400038cb  mov     eax, [rdi+4]
0x1400038ce  cmp     [rcx+4], eax
0x1400038d1  jnz     short loc_14000390D
0x1400038d3  mov     eax, [rdi+8]
0x1400038d6  cmp     [rcx+8], eax
0x1400038d9  jnz     short loc_14000390D
0x1400038db  mov     eax, [rdi+0Ch]
0x1400038de  cmp     [rcx+0Ch], eax
0x1400038e1  jnz     short loc_14000390D
0x1400038e3  xor     ebp, ebp
0x1400038e5  mov     rax, [rbx+10h]
0x1400038e9  cmp     rax, 1
0x1400038ed  jz      short loc_14000391F
0x1400038ef  mov     r9, [rbx+8]
0x1400038f3  mov     r8, rsi
0x1400038f6  mov     rdx, rdi
0x1400038f9  mov     rcx, r14
0x1400038fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003901  test    eax, eax
0x140003903  jz      short loc_14000392D
0x140003905  test    ebp, ebp
0x140003907  jnz     short loc_14000390D
0x140003909  test    eax, eax
0x14000390b  js      short loc_14000392D
0x14000390d  add     rbx, 18h
0x140003911  cmp     qword ptr [rbx+10h], 0
0x140003916  jnz     short loc_1400038B8
0x140003918  mov     eax, 80004002h
0x14000391d  jmp     short loc_14000392D
0x14000391f  mov     rbx, [rbx+8]
0x140003923  jmp     loc_140003898
0x140003928  mov     eax, 80070057h
0x14000392d  add     rsp, 30h
0x140003931  pop     r14
0x140003933  pop     rdi
0x140003934  pop     rsi
0x140003935  pop     rbp
0x140003936  pop     rbx
0x140003937  retn
```
