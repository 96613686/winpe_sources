# GetConfigString(IAppHostElement *,ushort const *,STRU *)

- ea: `0x180002bd8`
- end: `0x180002ca9`
- name: `?GetConfigString@@YAJPEAUIAppHostElement@@PEBGPEAVSTRU@@@Z`
- size: `209`
- prototype: `int(struct IAppHostElement *, const unsigned __int16 *, struct STRU *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180003818`
- `0x180003c74`

## callees

- `0x180002bd8`
- `0x180006010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002c01`
- `OLEAUT32!__imp_SysAllocString` at `0x180002c01`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c62`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c72`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c62`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c72`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002c57`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002c57`

## pseudocode

```c
__int64 __fastcall GetConfigString(struct IAppHostElement *a1, const unsigned __int16 *a2, struct STRU *a3)
{
  BSTR v5; // rax
  OLECHAR *v6; // rdi
  int v7; // ebx
  _QWORD v9[3]; // [rsp+20h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp+20h] BYREF

  bstrString = 0;
  v9[0] = 0;
  v5 = SysAllocString(a2);
  v6 = v5;
  if ( v5 )
  {
    v7 = ((__int64 (__fastcall *)(struct IAppHostElement *, BSTR, _QWORD *))a1->lpVtbl->GetPropertyByName)(a1, v5, v9);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)v9[0] + 56LL))(v9[0], &bstrString);
      if ( v7 >= 0 )
        v7 = STRU::Copy(a3, bstrString);
    }
    SysFreeString(v6);
  }
  else
  {
    v7 = -2147024882;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v9[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9[0] + 16LL))(v9[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002bd8  mov     rax, rsp
0x180002bdb  mov     [rax+8], rbx
0x180002bdf  mov     [rax+10h], rsi
0x180002be3  push    rdi
0x180002be4  sub     rsp, 30h
0x180002be8  mov     rbx, rcx
0x180002beb  mov     qword ptr [rax+20h], 0
0x180002bf3  mov     rcx, rdx; psz
0x180002bf6  mov     qword ptr [rax-18h], 0
0x180002bfe  mov     rsi, r8
0x180002c01  call    cs:__imp_SysAllocString
0x180002c07  mov     rdi, rax
0x180002c0a  test    rax, rax
0x180002c0d  jnz     short loc_180002C16
0x180002c0f  mov     ebx, 8007000Eh
0x180002c14  jmp     short loc_180002C68
0x180002c16  mov     rax, [rbx]
0x180002c19  lea     r8, [rsp+38h+var_18]
0x180002c1e  mov     rdx, rdi
0x180002c21  mov     rcx, rbx
0x180002c24  mov     rax, [rax+58h]
0x180002c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2d  mov     ebx, eax
0x180002c2f  test    eax, eax
0x180002c31  js      short loc_180002C5F
0x180002c33  mov     rcx, [rsp+38h+var_18]
0x180002c38  lea     rdx, [rsp+38h+bstrString]
0x180002c3d  mov     rax, [rcx]
0x180002c40  mov     rax, [rax+38h]
0x180002c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c49  mov     ebx, eax
0x180002c4b  test    eax, eax
0x180002c4d  js      short loc_180002C5F
0x180002c4f  mov     rdx, [rsp+38h+bstrString]
0x180002c54  mov     rcx, rsi
0x180002c57  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002c5d  mov     ebx, eax
0x180002c5f  mov     rcx, rdi; bstrString
0x180002c62  call    cs:__imp_SysFreeString
0x180002c68  mov     rcx, [rsp+38h+bstrString]; bstrString
0x180002c6d  test    rcx, rcx
0x180002c70  jz      short loc_180002C81
0x180002c72  call    cs:__imp_SysFreeString
0x180002c78  mov     [rsp+38h+bstrString], 0
0x180002c81  mov     rcx, [rsp+38h+var_18]
0x180002c86  test    rcx, rcx
0x180002c89  jz      short loc_180002C97
0x180002c8b  mov     rax, [rcx]
0x180002c8e  mov     rax, [rax+10h]
0x180002c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c97  mov     rsi, [rsp+38h+arg_8]
0x180002c9c  mov     eax, ebx
0x180002c9e  mov     rbx, [rsp+38h+arg_0]
0x180002ca3  add     rsp, 30h
0x180002ca7  pop     rdi
0x180002ca8  retn
```
