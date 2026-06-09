# SdbpMergeAreTagValuesEqual

- ea: `0x14001b2f0`
- end: `0x14001b4a7`
- name: `SdbpMergeAreTagValuesEqual`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001cd7c`
- `0x14001d494`
- `0x14001d808`

## callees

- `0x14001008c`
- `0x140013898`
- `0x140013938`
- `0x140013f74`
- `0x140016148`
- `0x14001b2f0`

## import_xrefs

- `KERNEL32!RtlCompareMemory` at `0x14001b408`
- `KERNEL32!RtlCompareMemory` at `0x14001b408`
- `msvcrt!toupper` at `0x14001b460`
- `msvcrt!toupper` at `0x14001b46a`
- `msvcrt!toupper` at `0x14001b460`
- `msvcrt!toupper` at `0x14001b46a`

## pseudocode

```c
_BOOL8 __fastcall SdbpMergeAreTagValuesEqual(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, int a5)
{
  unsigned int v7; // edi
  __int16 TagFromTagID; // si
  __int16 v10; // ax
  SIZE_T TagDataSize; // rsi
  const void *MappedTagData; // rdi
  const void *v13; // rax
  const void *v14; // rdx
  const char *v15; // rax
  _WORD *StringTagPtr; // rsi
  __int64 v18; // rax
  _WORD *v19; // rbp
  int v21; // ebx
  int v22; // edi

  v7 = a2;
  if ( !(_DWORD)a2 || !a4 )
    return (_DWORD)a2 == a4;
  TagFromTagID = SdbGetTagFromTagID(a1, a2);
  v10 = SdbGetTagFromTagID(a3, a4);
  if ( a5 && TagFromTagID != v10 )
    return 0;
  if ( (TagFromTagID & 0xF000) == 0x1000 )
    return (v10 & 0xF000) == 4096;
  if ( (((TagFromTagID & 0xF000) - 24576) & 0xFFFFDFFF) == 0 )
  {
    if ( (((v10 & 0xF000) - 24576) & 0xDFFF) != 0 )
      return 0;
    StringTagPtr = (_WORD *)SdbGetStringTagPtr(a1, v7);
    v18 = SdbGetStringTagPtr(a3, a4);
    v19 = (_WORD *)v18;
    if ( StringTagPtr && v18 )
    {
      while ( *StringTagPtr )
      {
        v21 = (unsigned __int16)*StringTagPtr;
        v22 = toupper((unsigned __int16)*v19);
        if ( toupper(v21) != v22 )
          return 0;
        ++StringTagPtr;
        ++v19;
      }
      return *v19 == 0;
    }
    else
    {
      return StringTagPtr == (_WORD *)v18;
    }
  }
  TagDataSize = (unsigned int)SdbGetTagDataSize(a1, v7);
  if ( TagDataSize != (unsigned int)SdbGetTagDataSize(a3, a4) || TagDataSize == 0x20000000 )
    return 0;
  MappedTagData = (const void *)SdbpGetMappedTagData(a1, v7);
  v13 = (const void *)SdbpGetMappedTagData(a3, a4);
  v14 = v13;
  if ( TagDataSize )
  {
    if ( !MappedTagData )
    {
      v15 = "both tags";
      if ( v14 )
        v15 = "first tag";
      goto LABEL_15;
    }
    if ( !v13 )
    {
      v15 = "second tag";
LABEL_15:
      AslLogCallPrintf(
        1,
        "SdbpMergeAreTagValuesEqual",
        897,
        "SdbpGetMappedTagData returned null data pointer for data with size > 0. Null returned for %s",
        v15);
      return 0;
    }
  }
  return TagDataSize == RtlCompareMemory(MappedTagData, v13, TagDataSize);
}

```

## disassembly

```asm
0x14001b2f0  push    rbx
0x14001b2f2  push    rbp
0x14001b2f3  push    rsi
0x14001b2f4  push    rdi
0x14001b2f5  push    r14
0x14001b2f7  push    r15
0x14001b2f9  sub     rsp, 38h
0x14001b2fd  xor     r15d, r15d
0x14001b300  mov     ebx, r9d
0x14001b303  mov     rbp, r8
0x14001b306  mov     edi, edx
0x14001b308  mov     r14, rcx
0x14001b30b  test    edx, edx
0x14001b30d  jz      loc_14001B492
0x14001b313  test    ebx, ebx
0x14001b315  jz      loc_14001B492
0x14001b31b  call    SdbGetTagFromTagID
0x14001b320  mov     edx, ebx
0x14001b322  movzx   esi, ax
0x14001b325  mov     rcx, rbp
0x14001b328  call    SdbGetTagFromTagID
0x14001b32d  movzx   ecx, ax
0x14001b330  cmp     [rsp+68h+arg_20], r15d
0x14001b338  jz      short loc_14001B343
0x14001b33a  cmp     si, ax
0x14001b33d  jnz     loc_14001B3FB
0x14001b343  mov     eax, esi
0x14001b345  mov     edx, 0F000h
0x14001b34a  and     eax, edx
0x14001b34c  mov     r8d, 1000h
0x14001b352  cmp     eax, r8d
0x14001b355  jz      loc_14001B489
0x14001b35b  add     eax, 0FFFFA000h
0x14001b360  test    eax, 0FFFFDFFFh
0x14001b365  jz      loc_14001B41B
0x14001b36b  mov     edx, edi
0x14001b36d  mov     rcx, r14
0x14001b370  call    SdbGetTagDataSize
0x14001b375  mov     edx, ebx
0x14001b377  mov     esi, eax
0x14001b379  mov     rcx, rbp
0x14001b37c  call    SdbGetTagDataSize
0x14001b381  mov     eax, eax
0x14001b383  cmp     rsi, rax
0x14001b386  jnz     short loc_14001B3FB
0x14001b388  cmp     rsi, 20000000h
0x14001b38f  jz      short loc_14001B3FB
0x14001b391  mov     edx, edi
0x14001b393  mov     rcx, r14
0x14001b396  call    SdbpGetMappedTagData
0x14001b39b  mov     edx, ebx
0x14001b39d  mov     rcx, rbp
0x14001b3a0  mov     rdi, rax
0x14001b3a3  call    SdbpGetMappedTagData
0x14001b3a8  mov     rdx, rax; Source2
0x14001b3ab  test    rsi, rsi
0x14001b3ae  jz      short loc_14001B402
0x14001b3b0  test    rdi, rdi
0x14001b3b3  jz      short loc_14001B3C3
0x14001b3b5  test    rax, rax
0x14001b3b8  jnz     short loc_14001B402
0x14001b3ba  lea     rax, aSecondTag; "second tag"
0x14001b3c1  jmp     short loc_14001B3D8
0x14001b3c3  test    rdx, rdx
0x14001b3c6  lea     rcx, aFirstTag; "first tag"
0x14001b3cd  lea     rax, aBothTags; "both tags"
0x14001b3d4  cmovnz  rax, rcx
0x14001b3d8  lea     r9, aSdbpgetmappedt; "SdbpGetMappedTagData returned null data"...
0x14001b3df  mov     [rsp+68h+var_48], rax
0x14001b3e4  mov     r8d, 381h
0x14001b3ea  lea     rdx, aSdbpmergeareta; "SdbpMergeAreTagValuesEqual"
0x14001b3f1  mov     ecx, 1
0x14001b3f6  call    AslLogCallPrintf
0x14001b3fb  xor     eax, eax
0x14001b3fd  jmp     loc_14001B49A
0x14001b402  mov     r8, rsi; Length
0x14001b405  mov     rcx, rdi; Source1
0x14001b408  call    cs:__imp_RtlCompareMemory
0x14001b40e  cmp     rsi, rax
0x14001b411  mov     ecx, r15d
0x14001b414  setz    cl
0x14001b417  mov     eax, ecx
0x14001b419  jmp     short loc_14001B49A
0x14001b41b  and     cx, dx
0x14001b41e  mov     eax, 6000h
0x14001b423  sub     cx, ax
0x14001b426  mov     eax, 0DFFFh
0x14001b42b  test    ax, cx
0x14001b42e  jnz     short loc_14001B3FB
0x14001b430  mov     edx, edi
0x14001b432  mov     rcx, r14
0x14001b435  call    SdbGetStringTagPtr
0x14001b43a  mov     edx, ebx
0x14001b43c  mov     rcx, rbp
0x14001b43f  mov     rsi, rax
0x14001b442  call    SdbGetStringTagPtr
0x14001b447  mov     rbp, rax
0x14001b44a  test    rsi, rsi
0x14001b44d  jz      short loc_14001B454
0x14001b44f  test    rax, rax
0x14001b452  jnz     short loc_14001B47C
0x14001b454  cmp     rsi, rbp
0x14001b457  jmp     short loc_14001B494
0x14001b459  movzx   ecx, word ptr [rbp+0]; C
0x14001b45d  movzx   ebx, word ptr [rsi]
0x14001b460  call    cs:__imp_toupper
0x14001b466  mov     ecx, ebx; C
0x14001b468  mov     edi, eax
0x14001b46a  call    cs:__imp_toupper
0x14001b470  cmp     eax, edi
0x14001b472  jnz     short loc_14001B3FB
0x14001b474  add     rsi, 2
0x14001b478  add     rbp, 2
0x14001b47c  cmp     [rsi], r15w
0x14001b480  jnz     short loc_14001B459
0x14001b482  cmp     [rbp+0], r15w
0x14001b487  jmp     short loc_14001B494
0x14001b489  and     cx, dx
0x14001b48c  cmp     cx, r8w
0x14001b490  jmp     short loc_14001B494
0x14001b492  cmp     edi, ebx
0x14001b494  mov     eax, r15d
0x14001b497  setz    al
0x14001b49a  add     rsp, 38h
0x14001b49e  pop     r15
0x14001b4a0  pop     r14
0x14001b4a2  pop     rdi
0x14001b4a3  pop     rsi
0x14001b4a4  pop     rbp
0x14001b4a5  pop     rbx
0x14001b4a6  retn
```
