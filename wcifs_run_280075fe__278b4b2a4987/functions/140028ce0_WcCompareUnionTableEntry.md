# WcCompareUnionTableEntry

- ea: `0x140028ce0`
- end: `0x140028df7`
- name: `WcCompareUnionTableEntry`
- size: `279`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140028ce0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140028d70`
- `ntoskrnl!RtlCompareMemory` at `0x140028dd1`
- `ntoskrnl!RtlCompareMemory` at `0x140028d70`
- `ntoskrnl!RtlCompareMemory` at `0x140028dd1`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140028d36`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140028d36`

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
0x140028ce0  push    rbx
0x140028ce2  push    rsi
0x140028ce3  push    rdi
0x140028ce4  push    r14
0x140028ce6  sub     rsp, 38h
0x140028cea  mov     rcx, [rdx]
0x140028ced  xorps   xmm0, xmm0
0x140028cf0  mov     rax, [r8]
0x140028cf3  movups  xmmword ptr [rsp+58h+String1.Length], xmm0
0x140028cf8  lea     rbx, [rcx+8]
0x140028cfc  movzx   edx, word ptr [rbx]
0x140028cff  lea     rdi, [rax+8]
0x140028d03  movzx   r8d, word ptr [rdi]
0x140028d07  lea     r14, [rax+10h]
0x140028d0b  lea     rsi, [rcx+10h]
0x140028d0f  cmp     r8w, dx
0x140028d13  jnb     short loc_140028D92
0x140028d15  mov     [rsp+58h+String1.Length], r8w
0x140028d1b  lea     rcx, [rsp+58h+String1]; String1
0x140028d20  movzx   eax, word ptr [rdi]
0x140028d23  mov     rdx, rdi; String2
0x140028d26  mov     [rsp+58h+String1.MaximumLength], ax
0x140028d2b  mov     rax, [rsi]
0x140028d2e  mov     r8b, 1; CaseInSensitive
0x140028d31  mov     [rsp+58h+String1.Buffer], rax
0x140028d36  call    cs:__imp_RtlCompareUnicodeString
0x140028d3d  nop     dword ptr [rax+rax+00h]
0x140028d42  test    eax, eax
0x140028d44  jg      short loc_140028DAC
0x140028d46  js      loc_140028DF3
0x140028d4c  movzx   eax, word ptr [rdi]
0x140028d4f  movzx   ecx, word ptr [rbx]
0x140028d52  cmp     cx, ax
0x140028d55  jnb     short loc_140028DB3
0x140028d57  mov     rax, [r14]
0x140028d5a  lea     rdx, Source2; "\\"
0x140028d61  shr     rcx, 1
0x140028d64  mov     ebx, 2
0x140028d69  mov     r8d, ebx; Length
0x140028d6c  lea     rcx, [rax+rcx*2]; Source1
0x140028d70  call    cs:__imp_RtlCompareMemory
0x140028d77  nop     dword ptr [rax+rax+00h]
0x140028d7c  xor     ecx, ecx
0x140028d7e  cmp     rax, rbx
0x140028d81  setz    cl
0x140028d84  lea     eax, [rcx+1]
0x140028d87  add     rsp, 38h
0x140028d8b  pop     r14
0x140028d8d  pop     rdi
0x140028d8e  pop     rsi
0x140028d8f  pop     rbx
0x140028d90  retn
0x140028d92  mov     [rsp+58h+String1.Length], dx
0x140028d97  mov     rcx, rbx
0x140028d9a  movzx   eax, word ptr [rbx]
0x140028d9d  lea     rdx, [rsp+58h+String1]
0x140028da2  mov     [rsp+58h+String1.MaximumLength], ax
0x140028da7  mov     rax, [r14]
0x140028daa  jmp     short loc_140028D2E
0x140028dac  mov     eax, 1
0x140028db1  jmp     short loc_140028D87
0x140028db3  jbe     short loc_140028DEC
0x140028db5  mov     rcx, rax
0x140028db8  lea     rdx, Source2; "\\"
0x140028dbf  mov     rax, [rsi]
0x140028dc2  mov     ebx, 2
0x140028dc7  shr     rcx, 1
0x140028dca  mov     r8d, ebx; Length
0x140028dcd  lea     rcx, [rax+rcx*2]; Source1
0x140028dd1  call    cs:__imp_RtlCompareMemory
0x140028dd8  nop     dword ptr [rax+rax+00h]
0x140028ddd  mov     rcx, rax
0x140028de0  xor     eax, eax
0x140028de2  cmp     rcx, rbx
0x140028de5  cmovnz  ebx, eax
0x140028de8  mov     eax, ebx
0x140028dea  jmp     short loc_140028D87
0x140028dec  mov     eax, 2
0x140028df1  jmp     short loc_140028D87
0x140028df3  xor     eax, eax
0x140028df5  jmp     short loc_140028D87
```
