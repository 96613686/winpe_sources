# SymCommonNativeResourceOnlyDll

- ea: `0x1800304c8`
- end: `0x1800305d6`
- name: `SymCommonNativeResourceOnlyDll`
- size: `270`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002fae4`

## callees

- `0x1800304c8`

## import_xrefs

- `ntdll!RtlImageDirectoryEntryToData` at `0x1800304fd`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18003051f`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18003053d`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18003059c`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800304fd`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18003051f`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18003053d`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18003059c`

## pseudocode

```c
__int64 __fastcall SymCommonNativeResourceOnlyDll(unsigned int *BaseAddress, BOOLEAN a2)
{
  unsigned int v4; // ebx
  PVOID v5; // r14
  PVOID v6; // rbp
  __int64 v7; // rcx
  _DWORD *v8; // rax
  ULONG v10[10]; // [rsp+20h] [rbp-28h] BYREF
  ULONG v11; // [rsp+60h] [rbp+18h] BYREF
  ULONG Size; // [rsp+68h] [rbp+20h] BYREF

  v10[0] = 0;
  Size = 0;
  v11 = 0;
  v4 = 1;
  v5 = RtlImageDirectoryEntryToData(BaseAddress, a2, 0, v10);
  v6 = RtlImageDirectoryEntryToData(BaseAddress, a2, 1u, &Size);
  if ( !RtlImageDirectoryEntryToData(BaseAddress, a2, 2u, &v11) )
    return 0;
  if ( !v11 )
    return 0;
  if ( v6 )
    return 0;
  if ( Size )
    return 0;
  if ( v5 )
    return 0;
  if ( v10[0] )
    return 0;
  v7 = BaseAddress[15];
  if ( ((*(_WORD *)((char *)BaseAddress + v7 + 24) - 267) & 0xFEFF) != 0
    || *(unsigned int *)((char *)BaseAddress + v7 + 40) )
  {
    return 0;
  }
  else
  {
    v8 = RtlImageDirectoryEntryToData(BaseAddress, a2, 0xEu, &v11);
    if ( v11 == 72 && v8 )
      return *v8 != 72;
  }
  return v4;
}

```

## disassembly

```asm
0x1800304c8  mov     rax, rsp
0x1800304cb  mov     [rax+8], rbx
0x1800304cf  mov     [rax+10h], rbp
0x1800304d3  push    rsi
0x1800304d4  push    rdi
0x1800304d5  push    r14
0x1800304d7  sub     rsp, 30h
0x1800304db  xor     r8d, r8d; Directory
0x1800304de  mov     dword ptr [rax-28h], 0
0x1800304e5  lea     r9, [rax-28h]; Size
0x1800304e9  mov     dword ptr [rax+20h], 0
0x1800304f0  mov     sil, dl
0x1800304f3  mov     dword ptr [rax+18h], 0
0x1800304fa  mov     rdi, rcx
0x1800304fd  call    cs:__imp_RtlImageDirectoryEntryToData
0x180030504  nop     dword ptr [rax+rax+00h]
0x180030509  mov     ebx, 1
0x18003050e  lea     r9, [rsp+48h+Size]; Size
0x180030513  mov     r8d, ebx; Directory
0x180030516  mov     dl, sil; MappedAsImage
0x180030519  mov     rcx, rdi; BaseAddress
0x18003051c  mov     r14, rax
0x18003051f  call    cs:__imp_RtlImageDirectoryEntryToData
0x180030526  nop     dword ptr [rax+rax+00h]
0x18003052b  lea     r8d, [rbx+1]; Directory
0x18003052f  mov     dl, sil; MappedAsImage
0x180030532  lea     r9, [rsp+48h+arg_10]; Size
0x180030537  mov     rcx, rdi; BaseAddress
0x18003053a  mov     rbp, rax
0x18003053d  call    cs:__imp_RtlImageDirectoryEntryToData
0x180030544  nop     dword ptr [rax+rax+00h]
0x180030549  test    rax, rax
0x18003054c  jz      short loc_1800305BE
0x18003054e  cmp     [rsp+48h+arg_10], 0
0x180030553  jz      short loc_1800305BE
0x180030555  test    rbp, rbp
0x180030558  jnz     short loc_1800305BE
0x18003055a  cmp     [rsp+48h+Size], ebp
0x18003055e  jnz     short loc_1800305BE
0x180030560  test    r14, r14
0x180030563  jnz     short loc_1800305BE
0x180030565  cmp     [rsp+48h+var_28], r14d
0x18003056a  jnz     short loc_1800305BE
0x18003056c  mov     ecx, [rdi+3Ch]
0x18003056f  mov     edx, 10Bh
0x180030574  movzx   eax, word ptr [rcx+rdi+18h]
0x180030579  sub     ax, dx
0x18003057c  mov     edx, 0FEFFh
0x180030581  test    dx, ax
0x180030584  jnz     short loc_1800305BE
0x180030586  cmp     [rcx+rdi+28h], r14d
0x18003058b  jnz     short loc_1800305BE
0x18003058d  lea     r8d, [rbx+0Dh]; Directory
0x180030591  mov     dl, sil; MappedAsImage
0x180030594  lea     r9, [rsp+48h+arg_10]; Size
0x180030599  mov     rcx, rdi; BaseAddress
0x18003059c  call    cs:__imp_RtlImageDirectoryEntryToData
0x1800305a3  nop     dword ptr [rax+rax+00h]
0x1800305a8  cmp     [rsp+48h+arg_10], 48h ; 'H'
0x1800305ad  jnz     short loc_1800305C0
0x1800305af  test    rax, rax
0x1800305b2  jz      short loc_1800305C0
0x1800305b4  xor     ebx, ebx
0x1800305b6  cmp     dword ptr [rax], 48h ; 'H'
0x1800305b9  setnz   bl
0x1800305bc  jmp     short loc_1800305C0
0x1800305be  xor     ebx, ebx
0x1800305c0  mov     rbp, [rsp+48h+arg_8]
0x1800305c5  mov     eax, ebx
0x1800305c7  mov     rbx, [rsp+48h+arg_0]
0x1800305cc  add     rsp, 30h
0x1800305d0  pop     r14
0x1800305d2  pop     rdi
0x1800305d3  pop     rsi
0x1800305d4  retn
```
