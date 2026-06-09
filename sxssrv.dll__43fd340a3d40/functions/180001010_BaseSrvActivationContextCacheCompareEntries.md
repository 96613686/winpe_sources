# BaseSrvActivationContextCacheCompareEntries

- ea: `0x180001010`
- end: `0x180001102`
- name: `BaseSrvActivationContextCacheCompareEntries`
- size: `242`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001010`
- `0x180006cb5`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18000106a`
- `ntdll!RtlCompareUnicodeString` at `0x180001093`
- `ntdll!RtlCompareUnicodeString` at `0x1800010b0`
- `ntdll!RtlCompareUnicodeString` at `0x18000106a`
- `ntdll!RtlCompareUnicodeString` at `0x180001093`
- `ntdll!RtlCompareUnicodeString` at `0x1800010b0`

## pseudocode

```c
__int64 __fastcall BaseSrvActivationContextCacheCompareEntries(
        struct _RTL_AVL_TABLE *Table,
        char *FirstStruct,
        char *SecondStruct)
{
  __int64 v3; // rax
  unsigned __int64 v7; // rax
  unsigned __int16 v8; // ax
  LONG v9; // eax
  unsigned __int16 v10; // ax
  LONG v11; // eax
  LONG v12; // eax
  int v13; // ecx

  v3 = *((_QWORD *)SecondStruct + 4);
  if ( *((_QWORD *)FirstStruct + 4) > v3 )
    return 1;
  if ( *((_QWORD *)FirstStruct + 4) < v3 )
    return 0;
  v7 = *((_QWORD *)SecondStruct + 7);
  if ( *((_QWORD *)FirstStruct + 7) > v7 )
    return 1;
  if ( *((_QWORD *)FirstStruct + 7) < v7 )
    return 0;
  v8 = *((_WORD *)SecondStruct + 41);
  if ( *((_WORD *)FirstStruct + 41) > v8 )
    return 1;
  if ( *((_WORD *)FirstStruct + 41) < v8 )
    return 0;
  v9 = RtlCompareUnicodeString((PCUNICODE_STRING)FirstStruct + 4, (PCUNICODE_STRING)SecondStruct + 4, 1u);
  if ( v9 < 0 )
    return 0;
  if ( v9 > 0 )
    return 1;
  v10 = *((_WORD *)SecondStruct + 40);
  if ( *((_WORD *)FirstStruct + 40) > v10 )
    return 1;
  if ( *((_WORD *)FirstStruct + 40) < v10 )
    return 0;
  v11 = RtlCompareUnicodeString((PCUNICODE_STRING)FirstStruct + 1, (PCUNICODE_STRING)SecondStruct + 1, 1u);
  if ( v11 < 0 )
    return 0;
  if ( v11 > 0 )
    return 1;
  v12 = RtlCompareUnicodeString((PCUNICODE_STRING)(FirstStruct + 40), (PCUNICODE_STRING)(SecondStruct + 40), 1u);
  if ( v12 < 0 )
    return 0;
  if ( v12 > 0 )
    return 1;
  v13 = memcmp_0(FirstStruct + 88, SecondStruct + 88, 0x18u);
  if ( v13 < 0 )
    return 0;
  return (unsigned int)(v13 <= 0) + 1;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_0], rbx
0x180001015  push    rdi
0x180001016  sub     rsp, 20h
0x18000101a  mov     rax, [r8+20h]
0x18000101e  mov     rdi, r8
0x180001021  mov     rbx, rdx
0x180001024  cmp     [rdx+20h], rax
0x180001028  jg      loc_1800010F8
0x18000102e  jge     short loc_18000103E
0x180001030  xor     eax, eax
0x180001032  mov     rbx, [rsp+28h+arg_0]
0x180001037  add     rsp, 20h
0x18000103b  pop     rdi
0x18000103c  retn
0x18000103e  mov     rax, [r8+38h]
0x180001042  cmp     [rdx+38h], rax
0x180001046  ja      loc_1800010F8
0x18000104c  jb      short loc_180001030
0x18000104e  movzx   eax, word ptr [r8+52h]
0x180001053  cmp     [rdx+52h], ax
0x180001057  ja      loc_1800010F8
0x18000105d  jb      short loc_180001030
0x18000105f  lea     rdx, [r8+40h]; String2
0x180001063  mov     r8b, 1; CaseInsensitive
0x180001066  lea     rcx, [rbx+40h]; String1
0x18000106a  call    cs:__imp_RtlCompareUnicodeString
0x180001071  nop     dword ptr [rax+rax+00h]
0x180001076  test    eax, eax
0x180001078  js      short loc_180001030
0x18000107a  jg      short loc_1800010F8
0x18000107c  movzx   eax, word ptr [rdi+50h]
0x180001080  cmp     [rbx+50h], ax
0x180001084  ja      short loc_1800010F8
0x180001086  jb      short loc_180001030
0x180001088  lea     rdx, [rdi+10h]; String2
0x18000108c  mov     r8b, 1; CaseInsensitive
0x18000108f  lea     rcx, [rbx+10h]; String1
0x180001093  call    cs:__imp_RtlCompareUnicodeString
0x18000109a  nop     dword ptr [rax+rax+00h]
0x18000109f  test    eax, eax
0x1800010a1  js      short loc_180001030
0x1800010a3  jg      short loc_1800010F8
0x1800010a5  lea     rdx, [rdi+28h]; String2
0x1800010a9  mov     r8b, 1; CaseInsensitive
0x1800010ac  lea     rcx, [rbx+28h]; String1
0x1800010b0  call    cs:__imp_RtlCompareUnicodeString
0x1800010b7  nop     dword ptr [rax+rax+00h]
0x1800010bc  test    eax, eax
0x1800010be  js      loc_180001030
0x1800010c4  jg      short loc_1800010F8
0x1800010c6  lea     rdx, [rdi+58h]; Buf2
0x1800010ca  mov     r8d, 18h; Size
0x1800010d0  lea     rcx, [rbx+58h]; Buf1
0x1800010d4  call    memcmp_0
0x1800010d9  mov     ecx, eax
0x1800010db  test    eax, eax
0x1800010dd  js      loc_180001030
0x1800010e3  mov     rbx, [rsp+28h+arg_0]
0x1800010e8  xor     eax, eax
0x1800010ea  test    ecx, ecx
0x1800010ec  setle   al
0x1800010ef  inc     eax
0x1800010f1  add     rsp, 20h
0x1800010f5  pop     rdi
0x1800010f6  retn
0x1800010f8  mov     eax, 1
0x1800010fd  jmp     loc_180001032
```
