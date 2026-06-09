# _hypothesis_builder::SetCount(ulong)

- ea: `0x180012b74`
- end: `0x180012c76`
- name: `?SetCount@_hypothesis_builder@@QEAAJK@Z`
- size: `258`
- prototype: `__int64 __fastcall(_hypothesis_builder *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b30`
- `0x180012940`
- `0x1800129e8`

## callees

- `0x180004ac4`
- `0x180012b74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012ba4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012ba4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012bea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012bea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012c57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012c57`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::SetCount(_hypothesis_builder *this, unsigned int a2)
{
  __int64 v2; // rdi
  __int64 v4; // rsi
  _BYTE *v5; // rax
  void *v6; // rbp
  __int64 v7; // rsi
  _BYTE *v8; // rax
  __int64 i; // rsi

  v2 = a2;
  if ( a2 )
  {
    if ( a2 > 0x1C71C71 )
      return 2147942934LL;
    goto LABEL_4;
  }
  if ( *((_DWORD *)this + 4) || *((_QWORD *)this + 3) )
  {
LABEL_4:
    if ( !*((_QWORD *)this + 4) )
    {
      v4 = 32;
      v5 = CoTaskMemAlloc(0x20u);
      *((_QWORD *)this + 4) = v5;
      if ( !v5 )
        return 2147942414LL;
      do
      {
        *v5++ = 0;
        --v4;
      }
      while ( v4 );
    }
    v6 = (void *)*((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 4) = 0;
    if ( (_DWORD)v2 )
    {
      v7 = 144 * v2;
      v8 = CoTaskMemRealloc(v6, 144 * v2);
      v6 = v8;
      if ( !v8 )
        return 2147942414LL;
      for ( ; v7; --v7 )
        *v8++ = 0;
      *(_QWORD *)(*((_QWORD *)this + 4) + 24LL) = v6;
    }
    if ( *((_QWORD *)this + 3) )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
        _attribute_t::FreeAll((LPVOID *)(*((_QWORD *)this + 3) + 144 * i));
    }
    CoTaskMemFree(*((LPVOID *)this + 3));
    *((_DWORD *)this + 4) = v2;
    *((_QWORD *)this + 3) = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x180012b74  push    rbx
0x180012b76  push    rbp
0x180012b77  push    rsi
0x180012b78  push    rdi
0x180012b79  sub     rsp, 28h
0x180012b7d  mov     edi, edx
0x180012b7f  mov     rbx, rcx
0x180012b82  test    edx, edx
0x180012b84  jnz     short loc_180012C05
0x180012b86  cmp     [rcx+10h], edx
0x180012b89  jnz     short loc_180012B96
0x180012b8b  cmp     qword ptr [rcx+18h], 0
0x180012b90  jz      loc_180012C6A
0x180012b96  cmp     qword ptr [rcx+20h], 0
0x180012b9b  jnz     short loc_180012BC5
0x180012b9d  mov     esi, 20h ; ' '
0x180012ba2  mov     ecx, esi; cb
0x180012ba4  call    cs:__imp_CoTaskMemAlloc
0x180012bab  nop     dword ptr [rax+rax+00h]
0x180012bb0  mov     [rbx+20h], rax
0x180012bb4  test    rax, rax
0x180012bb7  jz      short loc_180012BFE
0x180012bb9  mov     byte ptr [rax], 0
0x180012bbc  inc     rax
0x180012bbf  sub     rsi, 1
0x180012bc3  jnz     short loc_180012BB9
0x180012bc5  mov     rbp, [rbx+18h]
0x180012bc9  mov     qword ptr [rbx+18h], 0
0x180012bd1  mov     dword ptr [rbx+10h], 0
0x180012bd8  test    edi, edi
0x180012bda  jz      short loc_180012C2D
0x180012bdc  lea     rsi, [rdi+rdi*8]
0x180012be0  mov     rcx, rbp; pv
0x180012be3  shl     rsi, 4
0x180012be7  mov     rdx, rsi; cb
0x180012bea  call    cs:__imp_CoTaskMemRealloc
0x180012bf1  nop     dword ptr [rax+rax+00h]
0x180012bf6  mov     rbp, rax
0x180012bf9  test    rax, rax
0x180012bfc  jnz     short loc_180012C14
0x180012bfe  mov     eax, 8007000Eh
0x180012c03  jmp     short loc_180012C6C
0x180012c05  cmp     edi, 1C71C71h
0x180012c0b  jbe     short loc_180012B96
0x180012c0d  mov     eax, 80070216h
0x180012c12  jmp     short loc_180012C6C
0x180012c14  test    rsi, rsi
0x180012c17  jz      short loc_180012C25
0x180012c19  mov     byte ptr [rax], 0
0x180012c1c  inc     rax
0x180012c1f  sub     rsi, 1
0x180012c23  jnz     short loc_180012C19
0x180012c25  mov     rax, [rbx+20h]
0x180012c29  mov     [rax+18h], rbp
0x180012c2d  cmp     qword ptr [rbx+18h], 0
0x180012c32  jz      short loc_180012C53
0x180012c34  xor     esi, esi
0x180012c36  cmp     [rbx+10h], esi
0x180012c39  jbe     short loc_180012C53
0x180012c3b  lea     rcx, [rsi+rsi*8]
0x180012c3f  shl     rcx, 4
0x180012c43  add     rcx, [rbx+18h]; this
0x180012c47  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180012c4c  inc     esi
0x180012c4e  cmp     esi, [rbx+10h]
0x180012c51  jb      short loc_180012C3B
0x180012c53  mov     rcx, [rbx+18h]; pv
0x180012c57  call    cs:__imp_CoTaskMemFree
0x180012c5e  nop     dword ptr [rax+rax+00h]
0x180012c63  mov     [rbx+10h], edi
0x180012c66  mov     [rbx+18h], rbp
0x180012c6a  xor     eax, eax
0x180012c6c  add     rsp, 28h
0x180012c70  pop     rdi
0x180012c71  pop     rsi
0x180012c72  pop     rbp
0x180012c73  pop     rbx
0x180012c74  retn
```
