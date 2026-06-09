# CLoggedOnAccounts::FindBySID(ushort const *,IPropertyStore * *)

- ea: `0x180009c10`
- end: `0x180009d3c`
- name: `?FindBySID@CLoggedOnAccounts@@UEAAJPEBGPEAPEAUIPropertyStore@@@Z`
- size: `300`
- prototype: `int(CLoggedOnAccounts *__hidden this, const unsigned __int16 *, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009230`
- `0x180009c10`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009cf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009cf0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009cc3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009cc3`

## pseudocode

```c
__int64 __fastcall CLoggedOnAccounts::FindBySID(
        CLoggedOnAccounts *this,
        const unsigned __int16 *a2,
        struct IPropertyStore **a3)
{
  __int64 v4; // rax
  __int64 result; // rax
  unsigned int v7; // ebx
  char v8; // bp
  __int64 v9; // rdx
  struct IPropertyStore *v10; // rcx
  __int64 v11; // [rsp+30h] [rbp-38h] BYREF
  int v12; // [rsp+70h] [rbp+8h] BYREF
  struct IPropertyStore *v13; // [rsp+80h] [rbp+18h] BYREF
  LPCWCH lpString2; // [rsp+88h] [rbp+20h] BYREF

  *a3 = 0;
  v4 = *(_QWORD *)this;
  v11 = 0;
  result = (*(__int64 (__fastcall **)(CLoggedOnAccounts *, __int64 *))(v4 + 24))(this, &v11);
  v7 = result;
  if ( (int)result >= 0 )
  {
    v8 = 0;
    v13 = 0;
    v12 = 0;
    while ( !(*(unsigned int (__fastcall **)(__int64, __int64, struct IPropertyStore **, int *))(*(_QWORD *)v11 + 24LL))(
               v11,
               1,
               &v13,
               &v12) )
    {
      lpString2 = 0;
      if ( (int)IPropertyStore_GetSecurityIDString(v13, v9, &lpString2) >= 0 )
      {
        if ( CompareStringOrdinal(a2, -1, lpString2, -1, 1) == 2 )
        {
          v10 = v13;
          *a3 = v13;
          ((void (__fastcall *)(struct IPropertyStore *))v10->lpVtbl->AddRef)(v10);
          v8 = 1;
        }
        LocalFree((HLOCAL)lpString2);
      }
      ((void (__fastcall *)(struct IPropertyStore *))v13->lpVtbl->Release)(v13);
      if ( v8 )
        goto LABEL_11;
    }
    v7 = -2147023728;
LABEL_11:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180009c10  push    rbx
0x180009c12  push    rsi
0x180009c13  push    rdi
0x180009c14  push    r14
0x180009c16  sub     rsp, 48h
0x180009c1a  xor     r14d, r14d
0x180009c1d  mov     rsi, rdx
0x180009c20  mov     [r8], r14
0x180009c23  lea     rdx, [rsp+68h+var_38]
0x180009c28  mov     rax, [rcx]
0x180009c2b  mov     rdi, r8
0x180009c2e  mov     [rsp+68h+var_38], r14
0x180009c33  mov     rax, [rax+18h]
0x180009c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c3c  mov     ebx, eax
0x180009c3e  test    eax, eax
0x180009c40  js      loc_180009D32
0x180009c46  mov     [rsp+68h+var_28], rbp
0x180009c4b  xor     bpl, bpl
0x180009c4e  mov     [rsp+68h+arg_10], r14
0x180009c56  mov     [rsp+68h+arg_0], r14d
0x180009c5b  mov     rcx, [rsp+68h+var_38]
0x180009c60  lea     r9, [rsp+68h+arg_0]
0x180009c65  lea     r8, [rsp+68h+arg_10]
0x180009c6d  mov     edx, 1
0x180009c72  mov     rax, [rcx]
0x180009c75  mov     rax, [rax+18h]
0x180009c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c7e  test    eax, eax
0x180009c80  jnz     loc_180009D15
0x180009c86  mov     rcx, [rsp+68h+arg_10]
0x180009c8e  lea     r8, [rsp+68h+lpString2]
0x180009c96  mov     [rsp+68h+lpString2], r14
0x180009c9e  call    IPropertyStore_GetSecurityIDString
0x180009ca3  test    eax, eax
0x180009ca5  js      short loc_180009CF6
0x180009ca7  mov     r8, [rsp+68h+lpString2]; lpString2
0x180009caf  mov     r9d, 0FFFFFFFFh; cchCount2
0x180009cb5  mov     edx, r9d; cchCount1
0x180009cb8  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180009cc0  mov     rcx, rsi; lpString1
0x180009cc3  call    cs:__imp_CompareStringOrdinal
0x180009cc9  cmp     eax, 2
0x180009ccc  jnz     short loc_180009CE8
0x180009cce  mov     rcx, [rsp+68h+arg_10]
0x180009cd6  mov     [rdi], rcx
0x180009cd9  mov     rax, [rcx]
0x180009cdc  mov     rax, [rax+8]
0x180009ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ce5  mov     bpl, 1
0x180009ce8  mov     rcx, [rsp+68h+lpString2]; hMem
0x180009cf0  call    cs:__imp_LocalFree
0x180009cf6  mov     rcx, [rsp+68h+arg_10]
0x180009cfe  mov     rax, [rcx]
0x180009d01  mov     rax, [rax+10h]
0x180009d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d0a  test    bpl, bpl
0x180009d0d  jz      loc_180009C5B
0x180009d13  jmp     short loc_180009D1A
0x180009d15  mov     ebx, 80070490h
0x180009d1a  mov     rcx, [rsp+68h+var_38]
0x180009d1f  mov     rax, [rcx]
0x180009d22  mov     rax, [rax+10h]
0x180009d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d2b  mov     rbp, [rsp+68h+var_28]
0x180009d30  mov     eax, ebx
0x180009d32  add     rsp, 48h
0x180009d36  pop     r14
0x180009d38  pop     rdi
0x180009d39  pop     rsi
0x180009d3a  pop     rbx
0x180009d3b  retn
```
