# _attributes_array_t::SetCount(ulong)

- ea: `0x1800126c0`
- end: `0x180012772`
- name: `?SetCount@_attributes_array_t@@QEAAJK@Z`
- size: `178`
- prototype: `__int64 __fastcall(_attributes_array_t *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011ef0`
- `0x180012350`

## callees

- `0x180004ac4`
- `0x1800126c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012730`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012730`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001270b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001270b`

## pseudocode

```c
__int64 __fastcall _attributes_array_t::SetCount(_attributes_array_t *this, unsigned int a2)
{
  __int64 v2; // rsi
  __int64 i; // rdi
  __int64 v6; // rdi
  _BYTE *v7; // rax

  v2 = a2;
  if ( a2 > 0x1C71C71 )
    return 2147942934LL;
  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)this; i = (unsigned int)(i + 1) )
      _attribute_t::FreeAll((LPVOID *)(*((_QWORD *)this + 1) + 144 * i));
  }
  CoTaskMemFree(*((LPVOID *)this + 1));
  *((_QWORD *)this + 1) = 0;
  v6 = 144 * v2;
  *(_DWORD *)this = 0;
  v7 = CoTaskMemAlloc(144 * v2);
  *((_QWORD *)this + 1) = v7;
  if ( !v7 )
    return 2147942414LL;
  for ( ; v6; --v6 )
    *v7++ = 0;
  *(_DWORD *)this = v2;
  return 0;
}

```

## disassembly

```asm
0x1800126c0  mov     [rsp+arg_0], rbx
0x1800126c5  mov     [rsp+arg_8], rsi
0x1800126ca  push    rdi
0x1800126cb  sub     rsp, 20h
0x1800126cf  mov     esi, edx
0x1800126d1  mov     rbx, rcx
0x1800126d4  cmp     edx, 1C71C71h
0x1800126da  jbe     short loc_1800126E3
0x1800126dc  mov     eax, 80070216h
0x1800126e1  jmp     short loc_180012761
0x1800126e3  cmp     qword ptr [rcx+8], 0
0x1800126e8  jz      short loc_180012707
0x1800126ea  xor     edi, edi
0x1800126ec  cmp     [rcx], edi
0x1800126ee  jbe     short loc_180012707
0x1800126f0  lea     rcx, [rdi+rdi*8]
0x1800126f4  shl     rcx, 4
0x1800126f8  add     rcx, [rbx+8]; this
0x1800126fc  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180012701  inc     edi
0x180012703  cmp     edi, [rbx]
0x180012705  jb      short loc_1800126F0
0x180012707  mov     rcx, [rbx+8]; pv
0x18001270b  call    cs:__imp_CoTaskMemFree
0x180012712  nop     dword ptr [rax+rax+00h]
0x180012717  lea     rdi, [rsi+rsi*8]
0x18001271b  mov     qword ptr [rbx+8], 0
0x180012723  shl     rdi, 4
0x180012727  mov     rcx, rdi; cb
0x18001272a  mov     dword ptr [rbx], 0
0x180012730  call    cs:__imp_CoTaskMemAlloc
0x180012737  nop     dword ptr [rax+rax+00h]
0x18001273c  mov     [rbx+8], rax
0x180012740  test    rax, rax
0x180012743  jnz     short loc_18001274C
0x180012745  mov     eax, 8007000Eh
0x18001274a  jmp     short loc_180012761
0x18001274c  test    rdi, rdi
0x18001274f  jz      short loc_18001275D
0x180012751  mov     byte ptr [rax], 0
0x180012754  inc     rax
0x180012757  sub     rdi, 1
0x18001275b  jnz     short loc_180012751
0x18001275d  mov     [rbx], esi
0x18001275f  xor     eax, eax
0x180012761  mov     rbx, [rsp+28h+arg_0]
0x180012766  mov     rsi, [rsp+28h+arg_8]
0x18001276b  add     rsp, 20h
0x18001276f  pop     rdi
0x180012770  retn
```
