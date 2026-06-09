# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180003e84`
- end: `0x180003f88`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004460`
- `0x1800044f0`
- `0x180004510`

## callees

- `0x180003e84`
- `0x18001d010`

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
0x180003e84  push    rbx
0x180003e86  push    rbp
0x180003e87  push    rsi
0x180003e88  push    rdi
0x180003e89  push    r14
0x180003e8b  sub     rsp, 30h
0x180003e8f  mov     rsi, r9
0x180003e92  mov     rdi, r8
0x180003e95  mov     rbx, rdx
0x180003e98  mov     r14, rcx
0x180003e9b  test    rcx, rcx
0x180003e9e  jz      loc_180003F78
0x180003ea4  test    rdx, rdx
0x180003ea7  jz      loc_180003F78
0x180003ead  test    r9, r9
0x180003eb0  jnz     short loc_180003EBC
0x180003eb2  mov     eax, 80004003h
0x180003eb7  jmp     loc_180003F7D
0x180003ebc  mov     qword ptr [r9], 0
0x180003ec3  cmp     dword ptr [r8], 0
0x180003ec7  jnz     short loc_180003F01
0x180003ec9  cmp     dword ptr [r8+4], 0
0x180003ece  jnz     short loc_180003F01
0x180003ed0  cmp     dword ptr [r8+8], 0C0h
0x180003ed8  jnz     short loc_180003F01
0x180003eda  cmp     dword ptr [r8+0Ch], 46000000h
0x180003ee2  jnz     short loc_180003F01
0x180003ee4  mov     rbx, [rdx+8]
0x180003ee8  add     rbx, r14
0x180003eeb  mov     rcx, rbx
0x180003eee  mov     rax, [rbx]
0x180003ef1  mov     rax, [rax+8]
0x180003ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003efa  xor     eax, eax
0x180003efc  mov     [rsi], rbx
0x180003eff  jmp     short loc_180003F7D
0x180003f01  cmp     qword ptr [rdx+10h], 0
0x180003f06  jz      short loc_180003F68
0x180003f08  mov     rcx, [rbx]
0x180003f0b  test    rcx, rcx
0x180003f0e  jnz     short loc_180003F15
0x180003f10  lea     ebp, [rcx+1]
0x180003f13  jmp     short loc_180003F35
0x180003f15  mov     eax, [rdi]
0x180003f17  cmp     [rcx], eax
0x180003f19  jnz     short loc_180003F5D
0x180003f1b  mov     eax, [rdi+4]
0x180003f1e  cmp     [rcx+4], eax
0x180003f21  jnz     short loc_180003F5D
0x180003f23  mov     eax, [rdi+8]
0x180003f26  cmp     [rcx+8], eax
0x180003f29  jnz     short loc_180003F5D
0x180003f2b  mov     eax, [rdi+0Ch]
0x180003f2e  cmp     [rcx+0Ch], eax
0x180003f31  jnz     short loc_180003F5D
0x180003f33  xor     ebp, ebp
0x180003f35  mov     rax, [rbx+10h]
0x180003f39  cmp     rax, 1
0x180003f3d  jz      short loc_180003F6F
0x180003f3f  mov     r9, [rbx+8]
0x180003f43  mov     r8, rsi
0x180003f46  mov     rdx, rdi
0x180003f49  mov     rcx, r14
0x180003f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f51  test    eax, eax
0x180003f53  jz      short loc_180003F7D
0x180003f55  test    ebp, ebp
0x180003f57  jnz     short loc_180003F5D
0x180003f59  test    eax, eax
0x180003f5b  js      short loc_180003F7D
0x180003f5d  add     rbx, 18h
0x180003f61  cmp     qword ptr [rbx+10h], 0
0x180003f66  jnz     short loc_180003F08
0x180003f68  mov     eax, 80004002h
0x180003f6d  jmp     short loc_180003F7D
0x180003f6f  mov     rbx, [rbx+8]
0x180003f73  jmp     loc_180003EE8
0x180003f78  mov     eax, 80070057h
0x180003f7d  add     rsp, 30h
0x180003f81  pop     r14
0x180003f83  pop     rdi
0x180003f84  pop     rsi
0x180003f85  pop     rbp
0x180003f86  pop     rbx
0x180003f87  retn
```
