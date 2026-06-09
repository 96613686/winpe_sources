# TSDuplicatePassword(_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x180006530`
- end: `0x180006643`
- name: `?TSDuplicatePassword@@YAJPEAU_UNICODE_STRING@@0@Z`
- size: `275`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180009b2c`
- `0x180013f70`
- `0x18001449c`
- `0x1800161a0`
- `0x180016b38`

## callees

- `0x180006530`
- `0x18000c1a4`
- `0x18001c63c`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall TSDuplicatePassword(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  USHORT Length; // dx
  __int16 v5; // si
  USHORT v6; // si
  WCHAR *v7; // r14
  size_t MaximumLength; // r8
  WCHAR *v10; // rax

  a1->Buffer = 0;
  *(_DWORD *)&a1->Length = 0;
  if ( !a2 || !a2->Buffer )
    return 0;
  Length = a2->Length;
  v5 = 0;
  if ( (Length & 7) != 0 )
    v5 = 8 - (Length & 7);
  if ( Length > 0xFFF4u )
    return 3221225579LL;
  v6 = Length + v5;
  if ( v6 < Length )
    return 3221225579LL;
  if ( TSGlobalState == 1 )
  {
    v7 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocatePrivateHeap)(v6);
  }
  else
  {
    v10 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))TSGlobalDllFunctions->AllocateHeap)(v6);
    v7 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, v6);
      a1->Buffer = v7;
      goto LABEL_10;
    }
  }
  a1->Buffer = v7;
  if ( v7 )
  {
LABEL_10:
    a1->Length = a2->Length;
    a1->MaximumLength = v6;
    if ( v6 == a2->MaximumLength )
      MaximumLength = a2->MaximumLength;
    else
      MaximumLength = a2->Length;
    memcpy_0(v7, a2->Buffer, MaximumLength);
    return 0;
  }
  return 3221225495LL;
}

```

## disassembly

```asm
0x180006530  push    rbx
0x180006532  push    rbp
0x180006533  push    rsi
0x180006534  push    rdi
0x180006535  sub     rsp, 28h
0x180006539  xor     ebp, ebp
0x18000653b  xor     eax, eax
0x18000653d  mov     [rcx+8], rbp
0x180006541  mov     rdi, rdx
0x180006544  mov     [rcx], eax
0x180006546  mov     rbx, rcx
0x180006549  test    rdx, rdx
0x18000654c  jz      loc_1800065E2
0x180006552  cmp     [rdx+8], rax
0x180006556  jz      loc_1800065E2
0x18000655c  movzx   edx, word ptr [rdx]
0x18000655f  xor     esi, esi
0x180006561  movzx   eax, dx
0x180006564  mov     ecx, 8
0x180006569  and     ax, 7
0x18000656d  sub     cx, ax
0x180006570  mov     eax, 0FFF4h
0x180006575  cmp     cx, 8
0x180006579  cmovnz  si, cx
0x18000657d  cmp     dx, ax
0x180006580  ja      short loc_1800065ED
0x180006582  add     si, dx
0x180006585  cmp     si, dx
0x180006588  jb      short loc_1800065ED
0x18000658a  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180006591  mov     [rsp+48h+arg_0], r14
0x180006596  movzx   ecx, si
0x180006599  jnz     short loc_180006610
0x18000659b  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800065a2  mov     rax, [rax+180h]
0x1800065a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ae  mov     r14, rax
0x1800065b1  mov     [rbx+8], r14
0x1800065b5  test    r14, r14
0x1800065b8  jz      short loc_1800065FB
0x1800065ba  movzx   eax, word ptr [rdi]
0x1800065bd  mov     rcx, r14; void *
0x1800065c0  mov     [rbx], ax
0x1800065c3  mov     [rbx+2], si
0x1800065c7  movzx   eax, word ptr [rdi+2]
0x1800065cb  mov     rdx, [rdi+8]; Src
0x1800065cf  cmp     si, ax
0x1800065d2  jz      short loc_18000663E
0x1800065d4  movzx   r8d, word ptr [rdi]; Size
0x1800065d8  call    memcpy_0
0x1800065dd  mov     r14, [rsp+48h+arg_0]
0x1800065e2  mov     eax, ebp
0x1800065e4  add     rsp, 28h
0x1800065e8  pop     rdi
0x1800065e9  pop     rsi
0x1800065ea  pop     rbp
0x1800065eb  pop     rbx
0x1800065ec  retn
0x1800065ed  mov     eax, 0C000006Bh
0x1800065f2  add     rsp, 28h
0x1800065f6  pop     rdi
0x1800065f7  pop     rsi
0x1800065f8  pop     rbp
0x1800065f9  pop     rbx
0x1800065fa  retn
0x1800065fb  mov     r14, [rsp+48h+arg_0]
0x180006600  mov     ebp, 0C0000017h
0x180006605  mov     eax, ebp
0x180006607  add     rsp, 28h
0x18000660b  pop     rdi
0x18000660c  pop     rsi
0x18000660d  pop     rbp
0x18000660e  pop     rbx
0x18000660f  retn
0x180006610  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180006617  mov     rax, [rax]
0x18000661a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000661f  mov     r14, rax
0x180006622  test    rax, rax
0x180006625  jz      short loc_1800065B1
0x180006627  movzx   r8d, si; Size
0x18000662b  xor     edx, edx; Val
0x18000662d  mov     rcx, rax; void *
0x180006630  call    memset_0
0x180006635  mov     [rbx+8], r14
0x180006639  jmp     loc_1800065BA
0x18000663e  mov     r8, rax
0x180006641  jmp     short loc_1800065D8
```
