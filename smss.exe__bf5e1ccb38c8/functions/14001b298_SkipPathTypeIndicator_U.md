# SkipPathTypeIndicator_U

- ea: `0x14001b298`
- end: `0x14001b336`
- name: `SkipPathTypeIndicator_U`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x14001ae48`

## callees

- `0x14001b298`

## import_xrefs

- `ntdll!_wcsnicmp` at `0x14001b2f5`
- `ntdll!_wcsnicmp` at `0x14001b2f5`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x14001b2a5`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x14001b2a5`

## pseudocode

```c
const WCHAR *__fastcall SkipPathTypeIndicator_U(const WCHAR *a1)
{
  const WCHAR *v1; // rbx
  __int32 v2; // eax
  __int32 v3; // eax
  __int32 v4; // eax
  __int32 v5; // eax
  int v6; // eax
  int v7; // edi

  v1 = a1;
  v2 = RtlDetermineDosPathNameType_U(a1) - 1;
  if ( !v2 )
  {
LABEL_11:
    v7 = 2;
    v1 = (const WCHAR *)((char *)v1 + (-(__int64)(_wcsnicmp(v1 + 2, L"?\\UNC", 5u) != 0) & 0xFFFFFFFFFFFFFFF4uLL) + 16);
    do
    {
      if ( !*v1 )
        break;
      if ( *v1 == 92 || *v1 == 47 )
        --v7;
      ++v1;
    }
    while ( v7 );
    return v1;
  }
  v3 = v2 - 1;
  if ( !v3 )
  {
    v1 += 3;
    return v1;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v1 += 2;
    return v1;
  }
  v5 = v4 - 1;
  if ( !v5 )
    return ++v1;
  v6 = v5 - 1;
  if ( v6 )
  {
    if ( v6 != 1 )
      return 0;
    goto LABEL_11;
  }
  return v1;
}

```

## disassembly

```asm
0x14001b298  mov     [rsp+arg_0], rbx
0x14001b29d  push    rdi
0x14001b29e  sub     rsp, 20h
0x14001b2a2  mov     rbx, rcx
0x14001b2a5  call    cs:__imp_RtlDetermineDosPathNameType_U
0x14001b2ab  sub     eax, 1
0x14001b2ae  jz      short loc_14001B2E1
0x14001b2b0  sub     eax, 1
0x14001b2b3  jz      short loc_14001B2DB
0x14001b2b5  sub     eax, 1
0x14001b2b8  jz      short loc_14001B2D5
0x14001b2ba  sub     eax, 1
0x14001b2bd  jz      short loc_14001B2CF
0x14001b2bf  sub     eax, 1
0x14001b2c2  jz      short loc_14001B328
0x14001b2c4  sub     eax, 1
0x14001b2c7  jz      short loc_14001B2E1
0x14001b2c9  xor     eax, eax
0x14001b2cb  mov     ebx, eax
0x14001b2cd  jmp     short loc_14001B328
0x14001b2cf  add     rbx, 2
0x14001b2d3  jmp     short loc_14001B328
0x14001b2d5  add     rbx, 4
0x14001b2d9  jmp     short loc_14001B328
0x14001b2db  add     rbx, 6
0x14001b2df  jmp     short loc_14001B328
0x14001b2e1  mov     edi, 2
0x14001b2e6  lea     rcx, [rbx+4]; Str1
0x14001b2ea  lea     rdx, aUnc_2; "?\\UNC"
0x14001b2f1  lea     r8d, [rdi+3]; MaxCount
0x14001b2f5  call    cs:__imp__wcsnicmp
0x14001b2fb  neg     eax
0x14001b2fd  sbb     rcx, rcx
0x14001b300  and     rcx, 0FFFFFFFFFFFFFFF4h
0x14001b304  add     rcx, 10h
0x14001b308  add     rbx, rcx
0x14001b30b  xor     eax, eax
0x14001b30d  cmp     [rbx], ax
0x14001b310  jz      short loc_14001B328
0x14001b312  cmp     word ptr [rbx], 5Ch ; '\'
0x14001b316  jz      short loc_14001B31E
0x14001b318  cmp     word ptr [rbx], 2Fh ; '/'
0x14001b31c  jnz     short loc_14001B320
0x14001b31e  dec     edi
0x14001b320  add     rbx, 2
0x14001b324  test    edi, edi
0x14001b326  jnz     short loc_14001B30D
0x14001b328  mov     rax, rbx
0x14001b32b  mov     rbx, [rsp+28h+arg_0]
0x14001b330  add     rsp, 20h
0x14001b334  pop     rdi
0x14001b335  retn
```
