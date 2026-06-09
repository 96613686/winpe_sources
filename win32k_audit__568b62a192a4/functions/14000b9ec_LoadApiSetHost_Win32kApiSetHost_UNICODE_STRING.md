# LoadApiSetHost(_Win32kApiSetHost *,_UNICODE_STRING *)

- ea: `0x14000b9ec`
- end: `0x14000bafe`
- name: `?LoadApiSetHost@@YAJPEAU_Win32kApiSetHost@@PEAU_UNICODE_STRING@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(struct _Win32kApiSetHost *, const STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b8f4`

## callees

- `0x14000b9ec`
- `0x14000bb7c`
- `0x14000bc3c`

## import_xrefs

- `ntoskrnl!MmLoadSystemImage` at `0x14000ba6f`
- `ntoskrnl!MmLoadSystemImage` at `0x14000ba6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba98`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bac8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba98`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bac8`

## string_xrefs

- `0x14000ba0f`: `\SystemRoot\System32\Drivers\`
- `0x14000b9fa`: `\SystemRoot\System32\`

## pseudocode

```c
__int64 __fastcall LoadApiSetHost(struct _Win32kApiSetHost *a1, const STRING *a2)
{
  unsigned int v2; // ebx
  struct _UNICODE_STRING *v5; // rcx
  int v6; // esi
  int v7; // eax
  PVOID P[2]; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING v10; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v11[2]; // [rsp+50h] [rbp-10h] BYREF

  *(_QWORD *)&v10.Length = 2883626;
  v10.Buffer = L"\\SystemRoot\\System32\\";
  v2 = 0;
  v11[0] = 3932218;
  v11[1] = L"\\SystemRoot\\System32\\Drivers\\";
  v5 = &v10;
  v6 = 0;
  *(_OWORD *)P = 0;
  while ( 1 )
  {
    if ( v6 >= 2 )
      return v2;
    if ( !(unsigned int)FormFullImageName(v5, a2, (struct _STRING *)P) )
      return (unsigned int)-1073741801;
    v7 = ((__int64 (__fastcall *)(PVOID *, _QWORD, _QWORD, __int64, char *, char *))MmLoadSystemImage)(
           P,
           0,
           0,
           0x80000000LL,
           (char *)a1 + 40,
           (char *)a1 + 32);
    v2 = v7;
    if ( v7 == -1073741411 || v7 == -1073741554 )
    {
      AddApiSetHostLoadRefCount(a1, P);
      v2 = 0;
LABEL_6:
      ExFreePoolWithTag(P[1], 0);
      return v2;
    }
    if ( v7 != -1073741772 )
    {
      if ( v7 >= 0 )
        AddApiSetHostLoadRefCount(a1, P);
      goto LABEL_6;
    }
    ++v6;
    ExFreePoolWithTag(P[1], 0);
    v5 = (struct _UNICODE_STRING *)v11;
    P[1] = 0;
  }
}

```

## disassembly

```asm
0x14000b9ec  push    rbp
0x14000b9ee  push    rbx
0x14000b9ef  push    rsi
0x14000b9f0  push    rdi
0x14000b9f1  push    r14
0x14000b9f3  mov     rbp, rsp
0x14000b9f6  sub     rsp, 60h
0x14000b9fa  lea     rax, aSystemrootSyst_0; "\\SystemRoot\\System32\\"
0x14000ba01  mov     qword ptr [rbp+var_20.Length], 2C002Ah
0x14000ba09  mov     [rbp+var_20.Buffer], rax
0x14000ba0d  xor     ebx, ebx
0x14000ba0f  lea     rax, aSystemrootSyst_1; "\\SystemRoot\\System32\\Drivers\\"
0x14000ba16  mov     [rbp+var_10], 3C003Ah
0x14000ba1e  xorps   xmm0, xmm0
0x14000ba21  mov     [rbp+var_8], rax
0x14000ba25  mov     rdi, rcx
0x14000ba28  mov     r14, rdx
0x14000ba2b  lea     rcx, [rbp+var_20]; struct _UNICODE_STRING *
0x14000ba2f  xor     esi, esi
0x14000ba31  movups  xmmword ptr [rbp+P], xmm0
0x14000ba35  cmp     esi, 2
0x14000ba38  jge     short loc_14000BAA4
0x14000ba3a  lea     r8, [rbp+P]; struct _UNICODE_STRING *
0x14000ba3e  mov     rdx, r14; struct _UNICODE_STRING *
0x14000ba41  call    ?FormFullImageName@@YAKPEBU_UNICODE_STRING@@PEAU1@1@Z; FormFullImageName(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000ba46  test    eax, eax
0x14000ba48  jz      loc_14000BAE5
0x14000ba4e  lea     rax, [rdi+20h]
0x14000ba52  mov     r9d, 80000000h
0x14000ba58  lea     rcx, [rdi+28h]
0x14000ba5c  mov     [rsp+60h+var_38], rax
0x14000ba61  mov     [rsp+60h+var_40], rcx
0x14000ba66  xor     r8d, r8d
0x14000ba69  lea     rcx, [rbp+P]
0x14000ba6d  xor     edx, edx
0x14000ba6f  call    cs:__imp_MmLoadSystemImage
0x14000ba76  nop     dword ptr [rax+rax+00h]
0x14000ba7b  mov     ebx, eax
0x14000ba7d  cmp     eax, 0C000019Dh
0x14000ba82  jnz     short loc_14000BAB2
0x14000ba84  lea     rdx, [rbp+P]
0x14000ba88  mov     rcx, rdi
0x14000ba8b  call    AddApiSetHostLoadRefCount
0x14000ba90  xor     ebx, ebx
0x14000ba92  mov     rcx, [rbp+P+8]; P
0x14000ba96  xor     edx, edx; Tag
0x14000ba98  call    cs:__imp_ExFreePoolWithTag
0x14000ba9f  nop     dword ptr [rax+rax+00h]
0x14000baa4  mov     eax, ebx
0x14000baa6  add     rsp, 60h
0x14000baaa  pop     r14
0x14000baac  pop     rdi
0x14000baad  pop     rsi
0x14000baae  pop     rbx
0x14000baaf  pop     rbp
0x14000bab0  retn
0x14000bab2  cmp     eax, 0C000010Eh
0x14000bab7  jz      short loc_14000BA84
0x14000bab9  cmp     eax, 0C0000034h
0x14000babe  jnz     short loc_14000BAEC
0x14000bac0  mov     rcx, [rbp+P+8]; P
0x14000bac4  inc     esi
0x14000bac6  xor     edx, edx; Tag
0x14000bac8  call    cs:__imp_ExFreePoolWithTag
0x14000bacf  nop     dword ptr [rax+rax+00h]
0x14000bad4  lea     rcx, [rbp+var_10]
0x14000bad8  mov     [rbp+P+8], 0
0x14000bae0  jmp     loc_14000BA35
0x14000bae5  mov     ebx, 0C0000017h
0x14000baea  jmp     short loc_14000BAA4
0x14000baec  test    eax, eax
0x14000baee  js      short loc_14000BA92
0x14000baf0  lea     rdx, [rbp+P]
0x14000baf4  mov     rcx, rdi
0x14000baf7  call    AddApiSetHostLoadRefCount
0x14000bafc  jmp     short loc_14000BA92
```
