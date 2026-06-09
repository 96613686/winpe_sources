# _AllocateAndCopyAnsiString

- ea: `0x180008a2c`
- end: `0x180008ac5`
- name: `_AllocateAndCopyAnsiString`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008720`

## callees

- `0x1800047e0`
- `0x180008a2c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008a7d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008a7d`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180008a9d`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180008a9d`

## pseudocode

```c
__int64 __fastcall AllocateAndCopyAnsiString(CHAR **a1, const wchar_t *a2)
{
  __int64 result; // rax
  int v5; // esi
  ULONG v6; // ebp
  CHAR *v7; // rax
  size_t pcchLength; // [rsp+68h] [rbp+10h] BYREF

  pcchLength = 0;
  if ( !a2 || !a1 )
    return 87;
  result = 0;
  *a1 = 0;
  if ( *a2 )
  {
    StringCchLengthW(a2, 0x7FFFFFFFu, &pcchLength);
    v5 = pcchLength;
    v6 = pcchLength + 1;
    v7 = (CHAR *)LocalAlloc(0x40u, (unsigned int)(pcchLength + 1));
    *a1 = v7;
    if ( v7 )
      return RtlUnicodeToMultiByteN(v7, v6, 0, a2, 2 * v5) != 0 ? 8 : 0;
    else
      return 8;
  }
  return result;
}

```

## disassembly

```asm
0x180008a2c  push    rbx
0x180008a2e  push    rbp
0x180008a2f  push    rsi
0x180008a30  push    rdi
0x180008a31  sub     rsp, 38h
0x180008a35  mov     [rsp+58h+pcchLength], 0
0x180008a3e  mov     rbx, rdx
0x180008a41  mov     rdi, rcx
0x180008a44  test    rdx, rdx
0x180008a47  jz      short loc_180008AB7
0x180008a49  test    rcx, rcx
0x180008a4c  jz      short loc_180008AB7
0x180008a4e  xor     eax, eax
0x180008a50  mov     qword ptr [rcx], 0
0x180008a57  cmp     ax, [rdx]
0x180008a5a  jz      short loc_180008ABC
0x180008a5c  lea     r8, [rsp+58h+pcchLength]; pcchLength
0x180008a61  mov     edx, 7FFFFFFFh; cchMax
0x180008a66  mov     rcx, rbx; psz
0x180008a69  call    StringCchLengthW
0x180008a6e  mov     rsi, [rsp+58h+pcchLength]
0x180008a73  mov     ecx, 40h ; '@'; uFlags
0x180008a78  lea     ebp, [rsi+1]
0x180008a7b  mov     edx, ebp; uBytes
0x180008a7d  call    cs:__imp_LocalAlloc
0x180008a83  mov     [rdi], rax
0x180008a86  test    rax, rax
0x180008a89  jz      short loc_180008AB0
0x180008a8b  lea     ecx, [rsi+rsi]
0x180008a8e  mov     r9, rbx; UnicodeString
0x180008a91  mov     [rsp+58h+UnicodeSize], ecx; UnicodeSize
0x180008a95  xor     r8d, r8d; ResultSize
0x180008a98  mov     rcx, rax; MbString
0x180008a9b  mov     edx, ebp; MbSize
0x180008a9d  call    cs:__imp_RtlUnicodeToMultiByteN
0x180008aa3  xor     ecx, ecx
0x180008aa5  sub     ecx, eax
0x180008aa7  neg     ecx
0x180008aa9  sbb     eax, eax
0x180008aab  and     eax, 8
0x180008aae  jmp     short loc_180008ABC
0x180008ab0  mov     eax, 8
0x180008ab5  jmp     short loc_180008ABC
0x180008ab7  mov     eax, 57h ; 'W'
0x180008abc  add     rsp, 38h
0x180008ac0  pop     rdi
0x180008ac1  pop     rsi
0x180008ac2  pop     rbp
0x180008ac3  pop     rbx
0x180008ac4  retn
```
