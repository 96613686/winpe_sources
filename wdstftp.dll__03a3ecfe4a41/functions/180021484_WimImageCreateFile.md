# WimImageCreateFile

- ea: `0x180021484`
- end: `0x180021640`
- name: `WimImageCreateFile`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180014454`

## callees

- `0x1800206c8`
- `0x180021380`
- `0x180021484`
- `0x1800250c4`
- `0x1800607b0`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180021616`
- `KERNEL32!CreateFileW` at `0x180021616`
- `KERNEL32!SetLastError` at `0x1800215be`
- `KERNEL32!SetLastError` at `0x1800215be`
- `ntdll!RtlNtStatusToDosError` at `0x180021585`
- `ntdll!RtlNtStatusToDosError` at `0x18002159a`
- `ntdll!RtlNtStatusToDosError` at `0x180021585`
- `ntdll!RtlNtStatusToDosError` at `0x18002159a`

## pseudocode

```c
HANDLE __fastcall WimImageCreateFile(
        __int64 a1,
        const WCHAR *a2,
        DWORD a3,
        __int64 a4,
        __int64 a5,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes)
{
  __int64 PathRelative; // rax
  __int64 v11; // r10
  void *v12; // r11
  int v13; // edx
  int *v14; // rcx
  int v15; // r9d
  int v16; // r8d
  __int64 i; // rax
  NTSTATUS Child; // eax
  ULONG v19; // ebx
  int v21; // eax
  const WCHAR *v22; // rcx
  __int64 v23; // [rsp+40h] [rbp-668h] BYREF
  _BYTE v24[1568]; // [rsp+50h] [rbp-658h] BYREF

  PathRelative = SparseMakePathRelative();
  LODWORD(v11) = -1;
  v12 = (void *)PathRelative;
  v23 = -1;
  if ( PathRelative )
  {
    v13 = dword_1800770D0;
    v14 = &dword_1800770D0;
    v15 = 0;
    while ( v13 )
    {
      if ( (v13 & dwFlagsAndAttributes) != 0 )
        v15 |= v14[1];
      v14 += 2;
      v13 = *v14;
    }
    if ( (dwFlagsAndAttributes & 0x10) != 0 )
      v15 = 1;
    v16 = 0;
    switch ( dwCreationDisposition )
    {
      case 1u:
        v16 = 2;
        break;
      case 2u:
        v16 = 5;
        break;
      case 3u:
LABEL_14:
        v16 = 1;
        break;
      case 4u:
        v16 = 3;
        break;
      case 5u:
        goto LABEL_14;
      default:
        break;
    }
    if ( a1 )
    {
      for ( i = *(_QWORD *)(a1 + 64); i; i = *(_QWORD *)(i + 64) )
        a1 = i;
      if ( *(_QWORD *)(a1 + 88) )
        v11 = *(_QWORD *)(a1 + 88);
    }
    Child = FltCommStubCreateChild(v11, a3, v16, v15, (unsigned __int16)dwFlagsAndAttributes, v12, (__int64)&v23);
    v19 = Child;
    if ( Child < 0 )
    {
      if ( (Child & 0x10000000) != 0 )
      {
        if ( RtlNtStatusToDosError(Child) != 317 )
          v19 = RtlNtStatusToDosError(v19);
      }
      else if ( (Child & 0x1FFF0000) == 0x70000 )
      {
        v19 = (unsigned __int16)Child;
      }
      SetLastError(v19);
    }
    return (HANDLE)v23;
  }
  memset_0(v24, 0, 0x618u);
  v21 = BuildApplyPathIfRedirected(a1, a2, v24);
  v22 = (const WCHAR *)v24;
  if ( !v21 )
    v22 = a2;
  return CreateFileW(v22, a3, 7u, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
}

```

## disassembly

```asm
0x180021484  push    rbx
0x180021486  push    rbp
0x180021487  push    rsi
0x180021488  push    rdi
0x180021489  push    r14
0x18002148b  sub     rsp, 680h
0x180021492  mov     rax, cs:__security_cookie
0x180021499  xor     rax, rsp
0x18002149c  mov     [rsp+6A8h+var_38], rax
0x1800214a4  mov     ebx, [rsp+6A8h+arg_28]
0x1800214ab  mov     r14d, r8d
0x1800214ae  mov     esi, [rsp+6A8h+arg_30]
0x1800214b5  mov     rbp, rdx
0x1800214b8  mov     rdi, rcx
0x1800214bb  call    SparseMakePathRelative
0x1800214c0  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800214c4  mov     r11, rax
0x1800214c7  mov     [rsp+6A8h+var_668], r10
0x1800214cc  test    rax, rax
0x1800214cf  jz      loc_1800215D1
0x1800214d5  mov     edx, cs:dword_1800770D0
0x1800214db  lea     rcx, dword_1800770D0
0x1800214e2  movzx   ebp, si
0x1800214e5  xor     r9d, r9d
0x1800214e8  jmp     short loc_1800214F8
0x1800214ea  test    esi, edx
0x1800214ec  jz      short loc_1800214F2
0x1800214ee  or      r9d, [rcx+4]
0x1800214f2  add     rcx, 8
0x1800214f6  mov     edx, [rcx]
0x1800214f8  test    edx, edx
0x1800214fa  jnz     short loc_1800214EA
0x1800214fc  test    sil, 10h
0x180021500  lea     eax, [rdx+1]
0x180021503  cmovnz  r9d, eax; int
0x180021507  xor     r8d, r8d
0x18002150a  sub     ebx, eax
0x18002150c  jz      short loc_180021533
0x18002150e  sub     ebx, eax
0x180021510  jz      short loc_18002152B
0x180021512  sub     ebx, eax
0x180021514  jz      short loc_18002151E
0x180021516  sub     ebx, eax
0x180021518  jz      short loc_180021523
0x18002151a  cmp     ebx, eax
0x18002151c  jnz     short loc_180021539
0x18002151e  mov     r8d, eax
0x180021521  jmp     short loc_180021539
0x180021523  mov     r8d, 3
0x180021529  jmp     short loc_180021539
0x18002152b  mov     r8d, 5
0x180021531  jmp     short loc_180021539
0x180021533  mov     r8d, 2; int
0x180021539  test    rdi, rdi
0x18002153c  jz      short loc_180021559
0x18002153e  mov     rax, [rdi+40h]
0x180021542  jmp     short loc_18002154B
0x180021544  mov     rdi, rax
0x180021547  mov     rax, [rax+40h]
0x18002154b  test    rax, rax
0x18002154e  jnz     short loc_180021544
0x180021550  cmp     [rdi+58h], rax
0x180021554  cmovnz  r10, [rdi+58h]
0x180021559  lea     rax, [rsp+6A8h+var_668]
0x18002155e  mov     edx, r14d; int
0x180021561  mov     [rsp+6A8h+var_678], rax; __int64
0x180021566  mov     rcx, r10; int
0x180021569  mov     qword ptr [rsp+6A8h+dwFlagsAndAttributes], r11; Src
0x18002156e  mov     [rsp+6A8h+dwCreationDisposition], ebp; int
0x180021572  call    FltCommStubCreateChild
0x180021577  mov     ebx, eax
0x180021579  test    eax, eax
0x18002157b  jns     short loc_1800215CA
0x18002157d  mov     ecx, eax; Status
0x18002157f  bt      eax, 1Ch
0x180021583  jnb     short loc_1800215AA
0x180021585  call    cs:__imp_RtlNtStatusToDosError
0x18002158c  nop     dword ptr [rax+rax+00h]
0x180021591  cmp     eax, 13Dh
0x180021596  jz      short loc_1800215BC
0x180021598  mov     ecx, ebx; Status
0x18002159a  call    cs:__imp_RtlNtStatusToDosError
0x1800215a1  nop     dword ptr [rax+rax+00h]
0x1800215a6  mov     ebx, eax
0x1800215a8  jmp     short loc_1800215BC
0x1800215aa  and     ecx, 1FFF0000h
0x1800215b0  movzx   eax, bx
0x1800215b3  cmp     ecx, 70000h
0x1800215b9  cmovz   ebx, eax
0x1800215bc  mov     ecx, ebx; dwErrCode
0x1800215be  call    cs:__imp_SetLastError
0x1800215c5  nop     dword ptr [rax+rax+00h]
0x1800215ca  mov     rax, [rsp+6A8h+var_668]
0x1800215cf  jmp     short loc_180021622
0x1800215d1  xor     edx, edx; Val
0x1800215d3  lea     rcx, [rsp+6A8h+var_658]; void *
0x1800215d8  mov     r8d, 618h; Size
0x1800215de  call    memset_0
0x1800215e3  lea     r8, [rsp+6A8h+var_658]
0x1800215e8  mov     rdx, rbp
0x1800215eb  mov     rcx, rdi
0x1800215ee  call    BuildApplyPathIfRedirected
0x1800215f3  test    eax, eax
0x1800215f5  lea     rcx, [rsp+6A8h+var_658]
0x1800215fa  mov     edx, r14d; dwDesiredAccess
0x1800215fd  cmovz   rcx, rbp; lpFileName
0x180021601  and     [rsp+6A8h+var_678], 0
0x180021607  xor     r9d, r9d; lpSecurityAttributes
0x18002160a  mov     [rsp+6A8h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18002160e  mov     [rsp+6A8h+dwCreationDisposition], ebx; dwCreationDisposition
0x180021612  lea     r8d, [r9+7]; dwShareMode
0x180021616  call    cs:__imp_CreateFileW
0x18002161d  nop     dword ptr [rax+rax+00h]
0x180021622  mov     rcx, [rsp+6A8h+var_38]
0x18002162a  xor     rcx, rsp; StackCookie
0x18002162d  call    __security_check_cookie
0x180021632  add     rsp, 680h
0x180021639  pop     r14
0x18002163b  pop     rdi
0x18002163c  pop     rsi
0x18002163d  pop     rbp
0x18002163e  pop     rbx
0x18002163f  retn
```
