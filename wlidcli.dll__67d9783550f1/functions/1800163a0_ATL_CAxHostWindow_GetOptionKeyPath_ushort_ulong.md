# ATL::CAxHostWindow::GetOptionKeyPath(ushort * *,ulong)

- ea: `0x1800163a0`
- end: `0x180016463`
- name: `?GetOptionKeyPath@CAxHostWindow@ATL@@UEAAJPEAPEAGK@Z`
- size: `195`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, unsigned __int16 **, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800163a0`
- `0x18001a784`
- `0x180063010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800163fe`
- `OLEAUT32!__imp_SysStringLen` at `0x1800163fe`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001640f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001640f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001641b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001641b`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::GetOptionKeyPath(ATL::CAxHostWindow *this, unsigned __int16 **a2)
{
  __int64 v5; // rcx
  int v6; // ebx
  unsigned __int64 v7; // rbp
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // r14

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = *((_QWORD *)this + 13);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 136LL))(v5);
    if ( v6 < 0 || !*a2 )
      return 1;
  }
  else
  {
    v6 = 1;
    if ( SysStringLen(*((BSTR *)this + 29)) )
    {
      v7 = SysStringByteLen(*((BSTR *)this + 29));
      v8 = (unsigned __int16 *)CoTaskMemAlloc(v7 + 2);
      v9 = v8;
      if ( !v8 )
        return 2147942414LL;
      if ( !ocscpy_s(v8, (v7 >> 1) + 1, *((const unsigned __int16 **)this + 29)) )
        return 2147500037LL;
      *a2 = v9;
      return 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800163a0  push    rbx
0x1800163a2  push    rbp
0x1800163a3  push    rsi
0x1800163a4  push    rdi
0x1800163a5  push    r14
0x1800163a7  sub     rsp, 20h
0x1800163ab  mov     rdi, rdx
0x1800163ae  mov     rsi, rcx
0x1800163b1  test    rdx, rdx
0x1800163b4  jnz     short loc_1800163C0
0x1800163b6  mov     eax, 80004003h
0x1800163bb  jmp     loc_180016458
0x1800163c0  mov     qword ptr [rdx], 0
0x1800163c7  mov     rcx, [rcx+68h]
0x1800163cb  test    rcx, rcx
0x1800163ce  jz      short loc_1800163F2
0x1800163d0  mov     rax, [rcx]
0x1800163d3  mov     rax, [rax+88h]
0x1800163da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163df  mov     ebx, eax
0x1800163e1  test    eax, eax
0x1800163e3  js      short loc_1800163EB
0x1800163e5  cmp     qword ptr [rdi], 0
0x1800163e9  jnz     short loc_180016456
0x1800163eb  mov     ebx, 1
0x1800163f0  jmp     short loc_180016456
0x1800163f2  mov     rcx, [rsi+0E8h]; pbstr
0x1800163f9  mov     ebx, 1
0x1800163fe  call    cs:__imp_SysStringLen
0x180016404  test    eax, eax
0x180016406  jz      short loc_180016456
0x180016408  mov     rcx, [rsi+0E8h]; bstr
0x18001640f  call    cs:__imp_SysStringByteLen
0x180016415  mov     ebp, eax
0x180016417  lea     rcx, [rbp+2]; cb
0x18001641b  call    cs:__imp_CoTaskMemAlloc
0x180016421  mov     r14, rax
0x180016424  test    rax, rax
0x180016427  jnz     short loc_180016430
0x180016429  mov     eax, 8007000Eh
0x18001642e  jmp     short loc_180016458
0x180016430  mov     r8, [rsi+0E8h]; unsigned __int16 *
0x180016437  mov     rcx, r14; unsigned __int16 *
0x18001643a  shr     rbp, 1
0x18001643d  lea     rdx, [rbx+rbp]; unsigned __int64
0x180016441  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180016446  test    al, al
0x180016448  jnz     short loc_180016451
0x18001644a  mov     eax, 80004005h
0x18001644f  jmp     short loc_180016458
0x180016451  mov     [rdi], r14
0x180016454  xor     ebx, ebx
0x180016456  mov     eax, ebx
0x180016458  add     rsp, 20h
0x18001645c  pop     r14
0x18001645e  pop     rdi
0x18001645f  pop     rsi
0x180016460  pop     rbp
0x180016461  pop     rbx
0x180016462  retn
```
