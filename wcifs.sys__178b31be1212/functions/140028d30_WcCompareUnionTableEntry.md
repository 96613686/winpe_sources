# WcCompareUnionTableEntry

- ea: `0x140028d30`
- end: `0x140028e47`
- name: `WcCompareUnionTableEntry`
- size: `279`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, __int64 *FirstStruct, __int64 *SecondStruct)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140028d30`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140028dc0`
- `ntoskrnl!RtlCompareMemory` at `0x140028e21`
- `ntoskrnl!RtlCompareMemory` at `0x140028dc0`
- `ntoskrnl!RtlCompareMemory` at `0x140028e21`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140028d86`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140028d86`

## pseudocode

```c
__int64 __fastcall WcCompareUnionTableEntry(struct _RTL_AVL_TABLE *Table, __int64 *FirstStruct, __int64 *SecondStruct)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  USHORT *v5; // rbx
  USHORT *v6; // rdi
  WCHAR **v7; // r14
  WCHAR **v8; // rsi
  UNICODE_STRING *v9; // rcx
  UNICODE_STRING *p_String1; // rdx
  WCHAR *v11; // rax
  LONG v12; // eax
  unsigned __int64 v13; // rcx
  unsigned int v15; // ebx
  UNICODE_STRING String1; // [rsp+20h] [rbp-38h] BYREF

  v3 = *FirstStruct;
  v4 = *SecondStruct;
  String1 = 0;
  v5 = (USHORT *)(v3 + 8);
  v6 = (USHORT *)(v4 + 8);
  v7 = (WCHAR **)(v4 + 16);
  v8 = (WCHAR **)(v3 + 16);
  if ( *(_WORD *)(v4 + 8) >= *(_WORD *)(v3 + 8) )
  {
    String1.Length = *(_WORD *)(v3 + 8);
    v9 = (UNICODE_STRING *)(v3 + 8);
    p_String1 = &String1;
    String1.MaximumLength = *v5;
    v11 = *v7;
  }
  else
  {
    String1.Length = *(_WORD *)(v4 + 8);
    v9 = &String1;
    p_String1 = (UNICODE_STRING *)(v4 + 8);
    String1.MaximumLength = *v6;
    v11 = *v8;
  }
  String1.Buffer = v11;
  v12 = RtlCompareUnicodeString(v9, p_String1, 1u);
  if ( v12 > 0 )
    return 1;
  if ( v12 < 0 )
    return 0;
  v13 = *v5;
  if ( (unsigned __int16)v13 < *v6 )
    return (unsigned int)(RtlCompareMemory(&(*v7)[v13 >> 1], L"\\", 2u) == 2) + 1;
  if ( (unsigned __int16)v13 <= *v6 )
    return 2;
  v15 = 2;
  if ( RtlCompareMemory(&(*v8)[(unsigned __int64)*v6 >> 1], L"\\", 2u) != 2 )
    return 0;
  return v15;
}

```

## disassembly

```asm
0x140028d30  push    rbx
0x140028d32  push    rsi
0x140028d33  push    rdi
0x140028d34  push    r14
0x140028d36  sub     rsp, 38h
0x140028d3a  mov     rcx, [rdx]
0x140028d3d  xorps   xmm0, xmm0
0x140028d40  mov     rax, [r8]
0x140028d43  movups  xmmword ptr [rsp+58h+String1.Length], xmm0
0x140028d48  lea     rbx, [rcx+8]
0x140028d4c  movzx   edx, word ptr [rbx]
0x140028d4f  lea     rdi, [rax+8]
0x140028d53  movzx   r8d, word ptr [rdi]
0x140028d57  lea     r14, [rax+10h]
0x140028d5b  lea     rsi, [rcx+10h]
0x140028d5f  cmp     r8w, dx
0x140028d63  jnb     short loc_140028DE2
0x140028d65  mov     [rsp+58h+String1.Length], r8w
0x140028d6b  lea     rcx, [rsp+58h+String1]; String1
0x140028d70  movzx   eax, word ptr [rdi]
0x140028d73  mov     rdx, rdi; String2
0x140028d76  mov     [rsp+58h+String1.MaximumLength], ax
0x140028d7b  mov     rax, [rsi]
0x140028d7e  mov     r8b, 1; CaseInSensitive
0x140028d81  mov     [rsp+58h+String1.Buffer], rax
0x140028d86  call    cs:__imp_RtlCompareUnicodeString
0x140028d8d  nop     dword ptr [rax+rax+00h]
0x140028d92  test    eax, eax
0x140028d94  jg      short loc_140028DFC
0x140028d96  js      loc_140028E43
0x140028d9c  movzx   eax, word ptr [rdi]
0x140028d9f  movzx   ecx, word ptr [rbx]
0x140028da2  cmp     cx, ax
0x140028da5  jnb     short loc_140028E03
0x140028da7  mov     rax, [r14]
0x140028daa  lea     rdx, Source2; "\\"
0x140028db1  shr     rcx, 1
0x140028db4  mov     ebx, 2
0x140028db9  mov     r8d, ebx; Length
0x140028dbc  lea     rcx, [rax+rcx*2]; Source1
0x140028dc0  call    cs:__imp_RtlCompareMemory
0x140028dc7  nop     dword ptr [rax+rax+00h]
0x140028dcc  xor     ecx, ecx
0x140028dce  cmp     rax, rbx
0x140028dd1  setz    cl
0x140028dd4  lea     eax, [rcx+1]
0x140028dd7  add     rsp, 38h
0x140028ddb  pop     r14
0x140028ddd  pop     rdi
0x140028dde  pop     rsi
0x140028ddf  pop     rbx
0x140028de0  retn
0x140028de2  mov     [rsp+58h+String1.Length], dx
0x140028de7  mov     rcx, rbx
0x140028dea  movzx   eax, word ptr [rbx]
0x140028ded  lea     rdx, [rsp+58h+String1]
0x140028df2  mov     [rsp+58h+String1.MaximumLength], ax
0x140028df7  mov     rax, [r14]
0x140028dfa  jmp     short loc_140028D7E
0x140028dfc  mov     eax, 1
0x140028e01  jmp     short loc_140028DD7
0x140028e03  jbe     short loc_140028E3C
0x140028e05  mov     rcx, rax
0x140028e08  lea     rdx, Source2; "\\"
0x140028e0f  mov     rax, [rsi]
0x140028e12  mov     ebx, 2
0x140028e17  shr     rcx, 1
0x140028e1a  mov     r8d, ebx; Length
0x140028e1d  lea     rcx, [rax+rcx*2]; Source1
0x140028e21  call    cs:__imp_RtlCompareMemory
0x140028e28  nop     dword ptr [rax+rax+00h]
0x140028e2d  mov     rcx, rax
0x140028e30  xor     eax, eax
0x140028e32  cmp     rcx, rbx
0x140028e35  cmovnz  ebx, eax
0x140028e38  mov     eax, ebx
0x140028e3a  jmp     short loc_140028DD7
0x140028e3c  mov     eax, 2
0x140028e41  jmp     short loc_140028DD7
0x140028e43  xor     eax, eax
0x140028e45  jmp     short loc_140028DD7
```
