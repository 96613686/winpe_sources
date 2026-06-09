# ClusApi::ResourceType::Delete(int,wchar_t const *)

- ea: `0x1800320b0`
- end: `0x180032117`
- name: `?Delete@ResourceType@ClusApi@@UEAAJHPEB_W@Z`
- size: `103`
- prototype: `__int64 __fastcall(ClusApi::ResourceType *__hidden this, int, const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18000e14c`
- `0x1800320b0`
- `0x1800ab010`

## import_xrefs

- `CLUSAPI!DeleteClusterResourceTypeEx` at `0x1800320f3`
- `CLUSAPI!DeleteClusterResourceTypeEx` at `0x1800320f3`

## string_xrefs

- `0x1800320e2`: `cluswmiext!ClusApi::ResourceType::Delete`

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
0x1800320b0  mov     [rsp+arg_0], rbx
0x1800320b5  push    rdi
0x1800320b6  sub     rsp, 20h
0x1800320ba  mov     rdx, rcx
0x1800320bd  mov     rdi, r8
0x1800320c0  add     rcx, 38h ; '8'
0x1800320c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800320c9  mov     rcx, [rdx+28h]
0x1800320cd  mov     rbx, rax
0x1800320d0  mov     rdx, [rcx]
0x1800320d3  mov     rax, [rdx+188h]
0x1800320da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320df  test    rdi, rdi
0x1800320e2  lea     r8, aCluswmiextClus_14; "cluswmiext!ClusApi::ResourceType::Delet"...
0x1800320e9  mov     rdx, rbx
0x1800320ec  mov     rcx, rax
0x1800320ef  cmovnz  r8, rdi
0x1800320f3  call    cs:__imp_DeleteClusterResourceTypeEx
0x1800320fa  nop     dword ptr [rax+rax+00h]
0x1800320ff  test    eax, eax
0x180032101  jle     short loc_18003210B
0x180032103  movzx   eax, ax
0x180032106  or      eax, 80070000h
0x18003210b  mov     rbx, [rsp+28h+arg_0]
0x180032110  add     rsp, 20h
0x180032114  pop     rdi
0x180032115  retn
```
