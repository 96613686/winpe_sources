# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18000ce10`
- end: `0x18000cf15`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `261`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000de50`
- `0x18000de70`
- `0x18000de90`
- `0x18000deb0`
- `0x180012830`
- `0x18001c380`
- `0x18001ff70`
- `0x180021380`
- `0x180027010`
- `0x18002af60`
- `0x18002bd20`
- `0x18002c0f0`
- `0x18002eac0`

## callees

- `0x18000ce10`
- `0x180034010`

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
0x18000ce10  push    rbx
0x18000ce12  push    rbp
0x18000ce13  push    rsi
0x18000ce14  push    rdi
0x18000ce15  push    r14
0x18000ce17  sub     rsp, 30h
0x18000ce1b  mov     rsi, r9
0x18000ce1e  mov     rdi, r8
0x18000ce21  mov     rbx, rdx
0x18000ce24  mov     r14, rcx
0x18000ce27  test    rcx, rcx
0x18000ce2a  jz      loc_18000CF04
0x18000ce30  test    rdx, rdx
0x18000ce33  jz      loc_18000CF04
0x18000ce39  test    r9, r9
0x18000ce3c  jnz     short loc_18000CE48
0x18000ce3e  mov     eax, 80004003h
0x18000ce43  jmp     loc_18000CF09
0x18000ce48  mov     qword ptr [r9], 0
0x18000ce4f  cmp     dword ptr [r8], 0
0x18000ce53  jnz     short loc_18000CE8D
0x18000ce55  cmp     dword ptr [r8+4], 0
0x18000ce5a  jnz     short loc_18000CE8D
0x18000ce5c  cmp     dword ptr [r8+8], 0C0h
0x18000ce64  jnz     short loc_18000CE8D
0x18000ce66  cmp     dword ptr [r8+0Ch], 46000000h
0x18000ce6e  jnz     short loc_18000CE8D
0x18000ce70  mov     rbx, [rdx+8]
0x18000ce74  add     rbx, r14
0x18000ce77  mov     rcx, rbx
0x18000ce7a  mov     rax, [rbx]
0x18000ce7d  mov     rax, [rax+8]
0x18000ce81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce86  xor     eax, eax
0x18000ce88  mov     [rsi], rbx
0x18000ce8b  jmp     short loc_18000CF09
0x18000ce8d  cmp     qword ptr [rdx+10h], 0
0x18000ce92  jz      short loc_18000CEF4
0x18000ce94  mov     rcx, [rbx]
0x18000ce97  test    rcx, rcx
0x18000ce9a  jnz     short loc_18000CEA1
0x18000ce9c  lea     ebp, [rcx+1]
0x18000ce9f  jmp     short loc_18000CEC1
0x18000cea1  mov     eax, [rdi]
0x18000cea3  cmp     [rcx], eax
0x18000cea5  jnz     short loc_18000CEE9
0x18000cea7  mov     eax, [rdi+4]
0x18000ceaa  cmp     [rcx+4], eax
0x18000cead  jnz     short loc_18000CEE9
0x18000ceaf  mov     eax, [rdi+8]
0x18000ceb2  cmp     [rcx+8], eax
0x18000ceb5  jnz     short loc_18000CEE9
0x18000ceb7  mov     eax, [rdi+0Ch]
0x18000ceba  cmp     [rcx+0Ch], eax
0x18000cebd  jnz     short loc_18000CEE9
0x18000cebf  xor     ebp, ebp
0x18000cec1  mov     rax, [rbx+10h]
0x18000cec5  cmp     rax, 1
0x18000cec9  jz      short loc_18000CEFB
0x18000cecb  mov     r9, [rbx+8]
0x18000cecf  mov     r8, rsi
0x18000ced2  mov     rdx, rdi
0x18000ced5  mov     rcx, r14
0x18000ced8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cedd  test    eax, eax
0x18000cedf  jz      short loc_18000CF09
0x18000cee1  test    ebp, ebp
0x18000cee3  jnz     short loc_18000CEE9
0x18000cee5  test    eax, eax
0x18000cee7  js      short loc_18000CF09
0x18000cee9  add     rbx, 18h
0x18000ceed  cmp     qword ptr [rbx+10h], 0
0x18000cef2  jnz     short loc_18000CE94
0x18000cef4  mov     eax, 80004002h
0x18000cef9  jmp     short loc_18000CF09
0x18000cefb  mov     rbx, [rbx+8]
0x18000ceff  jmp     loc_18000CE74
0x18000cf04  mov     eax, 80070057h
0x18000cf09  add     rsp, 30h
0x18000cf0d  pop     r14
0x18000cf0f  pop     rdi
0x18000cf10  pop     rsi
0x18000cf11  pop     rbp
0x18000cf12  pop     rbx
0x18000cf13  retn
```
