# ClusApi::ResourceType::Delete(int,wchar_t const *)

- ea: `0x18002d370`
- end: `0x18002d3d0`
- name: `?Delete@ResourceType@ClusApi@@UEAAJHPEB_W@Z`
- size: `96`
- prototype: `__int64 __fastcall(ClusApi::ResourceType *__hidden this, int, const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18000d618`
- `0x18002d370`
- `0x18008c010`

## import_xrefs

- `CLUSAPI!DeleteClusterResourceTypeEx` at `0x18002d3b3`
- `CLUSAPI!DeleteClusterResourceTypeEx` at `0x18002d3b3`

## string_xrefs

- `0x18002d3a2`: `cluswmiext!ClusApi::ResourceType::Delete`

## pseudocode

```c
__int64 __fastcall ClusApi::ResourceType::Delete(ClusApi::ResourceType *this, __int64 a2, const wchar_t *a3)
{
  __int64 v4; // rdx
  __int64 v5; // rbx
  __int64 v6; // rax
  const wchar_t *v7; // r8
  __int64 result; // rax

  v5 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 56);
  v6 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 40) + 392LL))(*(_QWORD *)(v4 + 40));
  v7 = L"cluswmiext!ClusApi::ResourceType::Delete";
  if ( a3 )
    v7 = a3;
  result = DeleteClusterResourceTypeEx(v6, v5, v7);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002d370  mov     [rsp+arg_0], rbx
0x18002d375  push    rdi
0x18002d376  sub     rsp, 20h
0x18002d37a  mov     rdx, rcx
0x18002d37d  mov     rdi, r8
0x18002d380  add     rcx, 38h ; '8'
0x18002d384  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d389  mov     rcx, [rdx+28h]
0x18002d38d  mov     rbx, rax
0x18002d390  mov     rdx, [rcx]
0x18002d393  mov     rax, [rdx+188h]
0x18002d39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d39f  test    rdi, rdi
0x18002d3a2  lea     r8, aCluswmiextClus_14; "cluswmiext!ClusApi::ResourceType::Delet"...
0x18002d3a9  mov     rdx, rbx
0x18002d3ac  mov     rcx, rax
0x18002d3af  cmovnz  r8, rdi
0x18002d3b3  call    cs:__imp_DeleteClusterResourceTypeEx
0x18002d3b9  test    eax, eax
0x18002d3bb  jle     short loc_18002D3C5
0x18002d3bd  movzx   eax, ax
0x18002d3c0  or      eax, 80070000h
0x18002d3c5  mov     rbx, [rsp+28h+arg_0]
0x18002d3ca  add     rsp, 20h
0x18002d3ce  pop     rdi
0x18002d3cf  retn
```
