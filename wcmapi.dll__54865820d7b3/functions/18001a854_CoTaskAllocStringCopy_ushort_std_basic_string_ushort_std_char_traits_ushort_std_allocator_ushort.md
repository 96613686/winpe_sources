# CoTaskAllocStringCopy(ushort * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001a854`
- end: `0x18001a8ca`
- name: `?CoTaskAllocStringCopy@@YAJPEAPEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `118`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018df0`
- `0x180018e10`
- `0x180018e30`

## callees

- `0x180005280`
- `0x180018d84`
- `0x18001a854`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a8aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a8aa`

## pseudocode

```c
__int64 __fastcall CoTaskAllocStringCopy(LPVOID *a1, __int64 a2)
{
  unsigned __int64 v3; // r14
  int v5; // edi
  LPVOID v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  const unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // r9

  v3 = *(_QWORD *)(a2 + 16) + 1LL;
  v5 = -2147024882;
  v6 = CoTaskMemAlloc(2 * v3);
  *a1 = v6;
  if ( v6 )
  {
    v9 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v7, v8, v6);
    v5 = StringCchCopyW(v10, v3, v9);
    if ( v5 < 0 )
    {
      CoTaskMemFree(*a1);
      *a1 = 0;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001a854  push    rbx
0x18001a856  push    rsi
0x18001a857  push    rdi
0x18001a858  push    r14
0x18001a85a  sub     rsp, 28h
0x18001a85e  mov     r14, [rdx+10h]
0x18001a862  mov     rbx, rcx
0x18001a865  inc     r14
0x18001a868  mov     rsi, rdx
0x18001a86b  mov     edi, 8007000Eh
0x18001a870  lea     rcx, [r14+r14]; cb
0x18001a874  call    cs:__imp_CoTaskMemAlloc
0x18001a87b  nop     dword ptr [rax+rax+00h]
0x18001a880  mov     [rbx], rax
0x18001a883  mov     r9, rax
0x18001a886  test    rax, rax
0x18001a889  jz      short loc_18001A8BD
0x18001a88b  mov     rcx, rsi
0x18001a88e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001a893  mov     r8, rax; unsigned __int16 *
0x18001a896  mov     rcx, r9; unsigned __int16 *
0x18001a899  mov     rdx, r14; unsigned __int64
0x18001a89c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a8a1  mov     edi, eax
0x18001a8a3  test    eax, eax
0x18001a8a5  jns     short loc_18001A8BD
0x18001a8a7  mov     rcx, [rbx]; pv
0x18001a8aa  call    cs:__imp_CoTaskMemFree
0x18001a8b1  nop     dword ptr [rax+rax+00h]
0x18001a8b6  mov     qword ptr [rbx], 0
0x18001a8bd  mov     eax, edi
0x18001a8bf  add     rsp, 28h
0x18001a8c3  pop     r14
0x18001a8c5  pop     rdi
0x18001a8c6  pop     rsi
0x18001a8c7  pop     rbx
0x18001a8c8  retn
```
