# DeleteSourceFromRefList

- ea: `0x18001bb28`
- end: `0x18001bc44`
- name: `DeleteSourceFromRefList`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180012800`

## callees

- `0x1800157ec`
- `0x18001bb28`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001bc35`
- `KERNEL32!HeapFree` at `0x18001bc35`

## string_xrefs

- `0x18001bb97`: `LEAVING DeleteSourceFromRefList : %x`

## pseudocode

```c
int __fastcall DeleteSourceFromRefList(int a1, int a2, __int64 a3, int a4, int a5, int a6)
{
  int v9; // r8d
  int result; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // [rsp+40h] [rbp-838h] BYREF
  _BYTE v14[2044]; // [rsp+44h] [rbp-834h] BYREF

  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  result = FindRefEntry(a1, a2, v9, a4);
  if ( result )
  {
    result = 0x7FFF;
    if ( !a6 )
      result = 49151;
    MEMORY[0x20] &= result;
    if ( MEMORY[0x20] >= 0 )
    {
      result = 0x4000;
      if ( (MEMORY[0x20] & 0x4000) == 0 )
      {
        v11 = MEMORY[0];
        if ( *(_QWORD *)(MEMORY[0] + 8LL) || (v12 = MEMORY[8], *MEMORY[8]) )
          __fastfail(3u);
        *MEMORY[8] = MEMORY[0];
        *(_QWORD *)(v11 + 8) = v12;
        return HeapFree(hHeap, 0, 0);
      }
    }
  }
  else if ( qword_18002B8A8 )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"LEAVING DeleteSourceFromRefList : %x", 0);
    return ((__int64 (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v13);
  }
  return result;
}

```

## disassembly

```asm
0x18001bb28  push    rbx
0x18001bb2a  push    rbp
0x18001bb2b  push    rsi
0x18001bb2c  push    rdi
0x18001bb2d  sub     rsp, 858h
0x18001bb34  mov     rax, cs:__security_cookie
0x18001bb3b  xor     rax, rsp
0x18001bb3e  mov     [rsp+878h+var_38], rax
0x18001bb46  mov     ebx, edx
0x18001bb48  mov     rdi, rcx
0x18001bb4b  xor     ebp, ebp
0x18001bb4d  lea     rcx, [rsp+878h+var_834]; void *
0x18001bb52  xor     edx, edx; Val
0x18001bb54  mov     [rsp+878h+lpMem], rbp
0x18001bb59  mov     r8d, 7FCh; Size
0x18001bb5f  mov     [rsp+878h+var_838], ebp
0x18001bb63  mov     esi, r9d
0x18001bb66  call    memset_0
0x18001bb6b  lea     rax, [rsp+878h+lpMem]
0x18001bb70  mov     r9d, esi
0x18001bb73  mov     edx, ebx
0x18001bb75  mov     [rsp+878h+var_850], rax
0x18001bb7a  mov     rcx, rdi
0x18001bb7d  call    FindRefEntry
0x18001bb82  test    eax, eax
0x18001bb84  jnz     short loc_18001BBE3
0x18001bb86  cmp     cs:qword_18002B8A8, rbp
0x18001bb8d  jz      short loc_18001BBC7
0x18001bb8f  xor     r8d, r8d
0x18001bb92  mov     word ptr [rsp+878h+var_838], bp
0x18001bb97  lea     rdx, aLeavingDeletes; "LEAVING DeleteSourceFromRefList : %x"
0x18001bb9e  lea     rcx, [rsp+878h+var_838]
0x18001bba3  call    FormatRRASErrorString
0x18001bba8  mov     rdx, cs:qword_18002B8A8
0x18001bbaf  lea     r8, [rsp+878h+var_838]
0x18001bbb4  mov     rcx, cs:gMgmEtwContext
0x18001bbbb  mov     rax, cs:gMgmTemplateFunc
0x18001bbc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbc7  mov     rcx, [rsp+878h+var_38]
0x18001bbcf  xor     rcx, rsp; StackCookie
0x18001bbd2  call    __security_check_cookie
0x18001bbd7  add     rsp, 858h
0x18001bbde  pop     rdi
0x18001bbdf  pop     rsi
0x18001bbe0  pop     rbp
0x18001bbe1  pop     rbx
0x18001bbe2  retn
0x18001bbe3  mov     eax, 7FFFh
0x18001bbe8  mov     r8, [rsp+878h+lpMem]; lpMem
0x18001bbed  cmp     [rsp+878h+arg_28], ebp
0x18001bbf4  jnz     short loc_18001BBFB
0x18001bbf6  mov     eax, 0BFFFh
0x18001bbfb  and     [r8+20h], ax
0x18001bc00  cmp     [r8+20h], bp
0x18001bc05  jl      short loc_18001BBC7
0x18001bc07  mov     eax, 4000h
0x18001bc0c  test    [r8+20h], ax
0x18001bc11  jnz     short loc_18001BBC7
0x18001bc13  mov     rax, [r8]
0x18001bc16  cmp     [rax+8], r8
0x18001bc1a  jnz     short loc_18001BC3D
0x18001bc1c  mov     rcx, [r8+8]
0x18001bc20  cmp     [rcx], r8
0x18001bc23  jnz     short loc_18001BC3D
0x18001bc25  mov     [rcx], rax
0x18001bc28  xor     edx, edx; dwFlags
0x18001bc2a  mov     [rax+8], rcx
0x18001bc2e  mov     rcx, cs:hHeap; hHeap
0x18001bc35  call    cs:__imp_HeapFree
0x18001bc3b  jmp     short loc_18001BBC7
0x18001bc3d  mov     ecx, 3
0x18001bc42  int     29h; Win8: RtlFailFast(ecx)
```
