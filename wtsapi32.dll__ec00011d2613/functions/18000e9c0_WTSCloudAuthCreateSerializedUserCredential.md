# _WTSCloudAuthCreateSerializedUserCredential

- ea: `0x18000e9c0`
- end: `0x18000ea80`
- name: `_WTSCloudAuthCreateSerializedUserCredential`
- size: `192`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c270`
- `0x18000ed20`

## callees

- `0x18000dfb8`
- `0x18000e9c0`
- `0x180015582`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ea14`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ea14`

## pseudocode

```c
__int64 __fastcall WTSCloudAuthCreateSerializedUserCredential(void *Src, size_t Size, _QWORD *a3)
{
  size_t v3; // rsi
  unsigned int v6; // ebx
  __int64 v7; // rdx
  SIZE_T v8; // r14
  _BYTE *v9; // rax
  _BYTE *v10; // rbx
  _BYTE *i; // rcx
  __int64 result; // rax
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = (unsigned int)Size;
  if ( !a3 )
  {
    v6 = -2147467261;
    v7 = 104;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"clientcore\\termsrv\\wtsapi\\cloudauth.cpp",
      (const char *)v6,
      v13);
    return v6;
  }
  *a3 = 0;
  if ( !Src )
  {
    v6 = -2147024809;
    v7 = 107;
    goto LABEL_12;
  }
  if ( !(_DWORD)Size )
  {
    v6 = -2147024809;
    v7 = 108;
    goto LABEL_12;
  }
  v8 = (unsigned int)Size + 16LL;
  v9 = LocalAlloc(0, v8);
  v10 = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    v7 = 111;
    goto LABEL_12;
  }
  for ( i = &v9[v8]; v9 != i; ++v9 )
    *v9 = 0;
  *(_DWORD *)v10 = v3;
  *((_QWORD *)v10 + 1) = v10 + 16;
  memcpy_0(v10 + 16, Src, v3);
  result = 0;
  *a3 = v10;
  return result;
}

```

## disassembly

```asm
0x18000e9c0  push    rbx
0x18000e9c2  push    rbp
0x18000e9c3  push    rsi
0x18000e9c4  push    rdi
0x18000e9c5  push    r14
0x18000e9c7  push    r15
0x18000e9c9  sub     rsp, 28h
0x18000e9cd  mov     esi, edx
0x18000e9cf  mov     rdi, r8
0x18000e9d2  mov     rbp, rcx
0x18000e9d5  test    r8, r8
0x18000e9d8  jnz     short loc_18000E9E5
0x18000e9da  mov     ebx, 80004003h
0x18000e9df  lea     edx, [r8+68h]
0x18000e9e3  jmp     short loc_18000EA5D
0x18000e9e5  mov     qword ptr [r8], 0
0x18000e9ec  test    rbp, rbp
0x18000e9ef  jnz     short loc_18000E9FB
0x18000e9f1  mov     ebx, 80070057h
0x18000e9f6  lea     edx, [rbp+6Bh]
0x18000e9f9  jmp     short loc_18000EA5D
0x18000e9fb  test    edx, edx
0x18000e9fd  jnz     short loc_18000EA0B
0x18000e9ff  mov     ebx, 80070057h
0x18000ea04  mov     edx, 6Ch ; 'l'
0x18000ea09  jmp     short loc_18000EA5D
0x18000ea0b  lea     r14, [rsi+10h]
0x18000ea0f  xor     ecx, ecx; uFlags
0x18000ea11  mov     rdx, r14; uBytes
0x18000ea14  call    cs:__imp_LocalAlloc
0x18000ea1a  mov     rbx, rax
0x18000ea1d  test    rax, rax
0x18000ea20  jz      short loc_18000EA53
0x18000ea22  lea     rcx, [r14+rax]
0x18000ea26  cmp     rax, rcx
0x18000ea29  jz      short loc_18000EA37
0x18000ea2b  xor     edx, edx
0x18000ea2d  mov     [rax], dl
0x18000ea2f  inc     rax
0x18000ea32  cmp     rax, rcx
0x18000ea35  jnz     short loc_18000EA2B
0x18000ea37  lea     rcx, [rbx+10h]; void *
0x18000ea3b  mov     [rbx], esi
0x18000ea3d  mov     r8, rsi; Size
0x18000ea40  mov     [rbx+8], rcx
0x18000ea44  mov     rdx, rbp; Src
0x18000ea47  call    memcpy_0
0x18000ea4c  xor     eax, eax
0x18000ea4e  mov     [rdi], rbx
0x18000ea51  jmp     short loc_18000EA73
0x18000ea53  mov     ebx, 8007000Eh
0x18000ea58  mov     edx, 6Fh ; 'o'; void *
0x18000ea5d  mov     rcx, [rsp+58h]; this
0x18000ea62  lea     r8, aClientcoreTerm; "clientcore\\termsrv\\wtsapi\\cloudauth."...
0x18000ea69  mov     r9d, ebx; char *
0x18000ea6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea71  mov     eax, ebx
0x18000ea73  add     rsp, 28h
0x18000ea77  pop     r15
0x18000ea79  pop     r14
0x18000ea7b  pop     rdi
0x18000ea7c  pop     rsi
0x18000ea7d  pop     rbp
0x18000ea7e  pop     rbx
0x18000ea7f  retn
```
