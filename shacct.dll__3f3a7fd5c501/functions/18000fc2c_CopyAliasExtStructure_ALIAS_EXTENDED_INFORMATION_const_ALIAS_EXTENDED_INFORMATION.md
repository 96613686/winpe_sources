# CopyAliasExtStructure(_ALIAS_EXTENDED_INFORMATION * const,_ALIAS_EXTENDED_INFORMATION *)

- ea: `0x18000fc2c`
- end: `0x18000fcdb`
- name: `?CopyAliasExtStructure@@YAJQEAU_ALIAS_EXTENDED_INFORMATION@@PEAU1@@Z`
- size: `175`
- prototype: `__int64 __fastcall(struct _ALIAS_EXTENDED_INFORMATION *const, struct _ALIAS_EXTENDED_INFORMATION *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011e80`
- `0x180014d90`

## callees

- `0x18000fc2c`
- `0x180012f18`
- `0x180016ce9`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc65`

## pseudocode

```c
__int64 __fastcall CopyAliasExtStructure(
        struct _ALIAS_EXTENDED_INFORMATION *const a1,
        struct _ALIAS_EXTENDED_INFORMATION *a2)
{
  unsigned int v4; // edi
  void *v5; // rax

  if ( a1 && a2 )
  {
    v4 = 0;
    *(_DWORD *)a2 = *(_DWORD *)a1;
    *((_DWORD *)a2 + 2) = *((_DWORD *)a1 + 2);
    if ( !*((_DWORD *)a1 + 2) || !*((_QWORD *)a1 + 2) )
    {
      *((_QWORD *)a2 + 2) = 0;
      return v4;
    }
    v5 = CoTaskMemAlloc(*((unsigned int *)a1 + 2));
    *((_QWORD *)a2 + 2) = v5;
    if ( v5 )
    {
      memcpy_0(v5, *((const void **)a1 + 2), *((unsigned int *)a1 + 2));
      return v4;
    }
    v4 = -2147024882;
  }
  else
  {
    v4 = -2147467261;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18000fc2c  mov     [rsp+arg_0], rbx
0x18000fc31  mov     [rsp+arg_8], rsi
0x18000fc36  push    rdi
0x18000fc37  sub     rsp, 20h
0x18000fc3b  mov     rsi, rdx
0x18000fc3e  mov     rbx, rcx
0x18000fc41  test    rcx, rcx
0x18000fc44  jz      short loc_18000FC93
0x18000fc46  test    rdx, rdx
0x18000fc49  jz      short loc_18000FC93
0x18000fc4b  mov     eax, [rcx]
0x18000fc4d  xor     edi, edi
0x18000fc4f  mov     [rdx], eax
0x18000fc51  mov     eax, [rcx+8]
0x18000fc54  mov     [rdx+8], eax
0x18000fc57  cmp     [rcx+8], edi
0x18000fc5a  jz      short loc_18000FC8D
0x18000fc5c  cmp     [rcx+10h], rdi
0x18000fc60  jz      short loc_18000FC8D
0x18000fc62  mov     ecx, [rcx+8]; cb
0x18000fc65  call    cs:__imp_CoTaskMemAlloc
0x18000fc6b  mov     [rsi+10h], rax
0x18000fc6f  test    rax, rax
0x18000fc72  jnz     short loc_18000FC7B
0x18000fc74  mov     edi, 8007000Eh
0x18000fc79  jmp     short loc_18000FC98
0x18000fc7b  mov     r8d, [rbx+8]; Size
0x18000fc7f  mov     rcx, rax; void *
0x18000fc82  mov     rdx, [rbx+10h]; Src
0x18000fc86  call    memcpy_0
0x18000fc8b  jmp     short loc_18000FCC9
0x18000fc8d  mov     [rdx+10h], rdi
0x18000fc91  jmp     short loc_18000FCC9
0x18000fc93  mov     edi, 80004003h
0x18000fc98  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc9f  lea     rax, WPP_GLOBAL_Control
0x18000fca6  cmp     rcx, rax
0x18000fca9  jz      short loc_18000FCC9
0x18000fcab  test    byte ptr [rcx+1Ch], 2
0x18000fcaf  jz      short loc_18000FCC9
0x18000fcb1  mov     rcx, [rcx+10h]
0x18000fcb5  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x18000fcbc  mov     edx, 25h ; '%'
0x18000fcc1  mov     r9d, edi
0x18000fcc4  call    WPP_SF_d
0x18000fcc9  mov     rbx, [rsp+28h+arg_0]
0x18000fcce  mov     eax, edi
0x18000fcd0  mov     rsi, [rsp+28h+arg_8]
0x18000fcd5  add     rsp, 20h
0x18000fcd9  pop     rdi
0x18000fcda  retn
```
