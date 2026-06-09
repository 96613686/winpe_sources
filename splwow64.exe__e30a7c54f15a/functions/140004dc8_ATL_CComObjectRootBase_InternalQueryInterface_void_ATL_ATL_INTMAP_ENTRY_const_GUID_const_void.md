# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x140004dc8`
- end: `0x140004ecc`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400054d0`
- `0x1400054f0`

## callees

- `0x140004dc8`
- `0x140016010`

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
0x140004dc8  push    rbx
0x140004dca  push    rbp
0x140004dcb  push    rsi
0x140004dcc  push    rdi
0x140004dcd  push    r14
0x140004dcf  sub     rsp, 30h
0x140004dd3  mov     rsi, r9
0x140004dd6  mov     rdi, r8
0x140004dd9  mov     rbx, rdx
0x140004ddc  mov     r14, rcx
0x140004ddf  test    rcx, rcx
0x140004de2  jz      loc_140004EBC
0x140004de8  test    rdx, rdx
0x140004deb  jz      loc_140004EBC
0x140004df1  test    r9, r9
0x140004df4  jnz     short loc_140004E00
0x140004df6  mov     eax, 80004003h
0x140004dfb  jmp     loc_140004EC1
0x140004e00  mov     qword ptr [r9], 0
0x140004e07  cmp     dword ptr [r8], 0
0x140004e0b  jnz     short loc_140004E45
0x140004e0d  cmp     dword ptr [r8+4], 0
0x140004e12  jnz     short loc_140004E45
0x140004e14  cmp     dword ptr [r8+8], 0C0h
0x140004e1c  jnz     short loc_140004E45
0x140004e1e  cmp     dword ptr [r8+0Ch], 46000000h
0x140004e26  jnz     short loc_140004E45
0x140004e28  mov     rbx, [rdx+8]
0x140004e2c  add     rbx, r14
0x140004e2f  mov     rcx, rbx
0x140004e32  mov     rax, [rbx]
0x140004e35  mov     rax, [rax+8]
0x140004e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e3e  xor     eax, eax
0x140004e40  mov     [rsi], rbx
0x140004e43  jmp     short loc_140004EC1
0x140004e45  cmp     qword ptr [rdx+10h], 0
0x140004e4a  jz      short loc_140004EAC
0x140004e4c  mov     rcx, [rbx]
0x140004e4f  test    rcx, rcx
0x140004e52  jnz     short loc_140004E59
0x140004e54  lea     ebp, [rcx+1]
0x140004e57  jmp     short loc_140004E79
0x140004e59  mov     eax, [rdi]
0x140004e5b  cmp     [rcx], eax
0x140004e5d  jnz     short loc_140004EA1
0x140004e5f  mov     eax, [rdi+4]
0x140004e62  cmp     [rcx+4], eax
0x140004e65  jnz     short loc_140004EA1
0x140004e67  mov     eax, [rdi+8]
0x140004e6a  cmp     [rcx+8], eax
0x140004e6d  jnz     short loc_140004EA1
0x140004e6f  mov     eax, [rdi+0Ch]
0x140004e72  cmp     [rcx+0Ch], eax
0x140004e75  jnz     short loc_140004EA1
0x140004e77  xor     ebp, ebp
0x140004e79  mov     rax, [rbx+10h]
0x140004e7d  cmp     rax, 1
0x140004e81  jz      short loc_140004EB3
0x140004e83  mov     r9, [rbx+8]
0x140004e87  mov     r8, rsi
0x140004e8a  mov     rdx, rdi
0x140004e8d  mov     rcx, r14
0x140004e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e95  test    eax, eax
0x140004e97  jz      short loc_140004EC1
0x140004e99  test    ebp, ebp
0x140004e9b  jnz     short loc_140004EA1
0x140004e9d  test    eax, eax
0x140004e9f  js      short loc_140004EC1
0x140004ea1  add     rbx, 18h
0x140004ea5  cmp     qword ptr [rbx+10h], 0
0x140004eaa  jnz     short loc_140004E4C
0x140004eac  mov     eax, 80004002h
0x140004eb1  jmp     short loc_140004EC1
0x140004eb3  mov     rbx, [rbx+8]
0x140004eb7  jmp     loc_140004E2C
0x140004ebc  mov     eax, 80070057h
0x140004ec1  add     rsp, 30h
0x140004ec5  pop     r14
0x140004ec7  pop     rdi
0x140004ec8  pop     rsi
0x140004ec9  pop     rbp
0x140004eca  pop     rbx
0x140004ecb  retn
```
