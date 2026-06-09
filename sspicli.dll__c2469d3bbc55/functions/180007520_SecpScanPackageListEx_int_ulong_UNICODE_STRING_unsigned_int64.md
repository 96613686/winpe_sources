# SecpScanPackageListEx(int,ulong,_UNICODE_STRING *,unsigned __int64)

- ea: `0x180007520`
- end: `0x180007607`
- name: `?SecpScanPackageListEx@@YAPEAU_DLL_SECURITY_PACKAGE@@HKPEAU_UNICODE_STRING@@_K@Z`
- size: `231`
- prototype: `struct _DLL_SECURITY_PACKAGE *(int, unsigned int, struct _UNICODE_STRING *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007200`
- `0x18000d6ec`

## callees

- `0x180007520`
- `0x18001d478`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800075d8`
- `ntdll!RtlEqualUnicodeString` at `0x1800075d8`

## pseudocode

```c
struct _DLL_SECURITY_PACKAGE *__fastcall SecpScanPackageListEx(int a1, int a2, struct _UNICODE_STRING *a3, WCHAR *a4)
{
  const UNICODE_STRING *v4; // rbx
  struct _DLL_SECURITY_PACKAGE *result; // rax

  v4 = (const UNICODE_STRING *)SecPackageControlList;
  result = 0;
  if ( SecPackageControlList == &SecPackageControlList )
    return result;
  while ( 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, a3, v4[6].Buffer);
    if ( a3 )
      break;
    if ( v4[1].Buffer == a4 && (a2 == 8 || (a2 & *(_DWORD *)&v4[1].Length) == a2) )
      goto LABEL_11;
LABEL_5:
    v4 = *(const UNICODE_STRING **)&v4->Length;
    result = 0;
    if ( v4 == (const UNICODE_STRING *)&SecPackageControlList )
      return result;
  }
  if ( !RtlEqualUnicodeString(v4 + 6, a3, 1u) || a2 != 8 && (a2 & *(_DWORD *)&v4[1].Length) != a2 )
    goto LABEL_5;
LABEL_11:
  if ( v4 && (*(_DWORD *)&v4[5].Length & 0x200000) != 0 && a1 )
  {
    if ( SecGlobalExtenderPackage )
      return SecGlobalExtenderPackage;
  }
  return (struct _DLL_SECURITY_PACKAGE *)v4;
}

```

## disassembly

```asm
0x180007520  push    rbx
0x180007522  push    rbp
0x180007523  push    rsi
0x180007524  push    rdi
0x180007525  push    r14
0x180007527  push    r15
0x180007529  sub     rsp, 28h
0x18000752d  mov     rbx, cs:?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x180007534  lea     r15, ?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x18000753b  xor     eax, eax
0x18000753d  mov     rbp, r9
0x180007540  mov     rsi, r8
0x180007543  mov     edi, edx
0x180007545  mov     r14d, ecx
0x180007548  cmp     rbx, r15
0x18000754b  jz      short loc_180007586
0x18000754d  mov     [rsp+58h+arg_0], r12
0x180007552  lea     r12, WPP_GLOBAL_Control
0x180007559  nop     dword ptr [rax+00000000h]
0x180007560  mov     rcx, cs:WPP_GLOBAL_Control
0x180007567  cmp     rcx, r12
0x18000756a  jnz     short loc_180007593
0x18000756c  test    rsi, rsi
0x18000756f  jnz     short loc_1800075CE
0x180007571  cmp     [rbx+18h], rbp
0x180007575  jz      short loc_1800075AD
0x180007577  mov     rbx, [rbx]
0x18000757a  xor     eax, eax
0x18000757c  cmp     rbx, r15
0x18000757f  jnz     short loc_180007560
0x180007581  mov     r12, [rsp+58h+arg_0]
0x180007586  add     rsp, 28h
0x18000758a  pop     r15
0x18000758c  pop     r14
0x18000758e  pop     rdi
0x18000758f  pop     rsi
0x180007590  pop     rbp
0x180007591  pop     rbx
0x180007592  retn
0x180007593  test    byte ptr [rcx+1Ch], 4
0x180007597  jz      short loc_18000756C
0x180007599  mov     r9, [rbx+68h]
0x18000759d  mov     edx, 0Bh
0x1800075a2  mov     rcx, [rcx+10h]
0x1800075a6  call    WPP_SF_S
0x1800075ab  jmp     short loc_18000756C
0x1800075ad  cmp     edi, 8
0x1800075b0  jz      short loc_1800075BB
0x1800075b2  mov     eax, [rbx+10h]
0x1800075b5  and     eax, edi
0x1800075b7  cmp     eax, edi
0x1800075b9  jnz     short loc_180007577
0x1800075bb  test    rbx, rbx
0x1800075be  jz      short loc_1800075C9
0x1800075c0  test    dword ptr [rbx+50h], 200000h
0x1800075c7  jnz     short loc_1800075F2
0x1800075c9  mov     rax, rbx
0x1800075cc  jmp     short loc_180007581
0x1800075ce  lea     rcx, [rbx+60h]; String1
0x1800075d2  mov     r8b, 1; CaseInsensitive
0x1800075d5  mov     rdx, rsi; String2
0x1800075d8  call    cs:__imp_RtlEqualUnicodeString
0x1800075de  test    al, al
0x1800075e0  jz      short loc_180007577
0x1800075e2  cmp     edi, 8
0x1800075e5  jz      short loc_1800075BB
0x1800075e7  mov     eax, [rbx+10h]
0x1800075ea  and     eax, edi
0x1800075ec  cmp     eax, edi
0x1800075ee  jz      short loc_1800075BB
0x1800075f0  jmp     short loc_180007577
0x1800075f2  test    r14d, r14d
0x1800075f5  jz      short loc_1800075C9
0x1800075f7  mov     rax, cs:?SecGlobalExtenderPackage@@3PEAU_DLL_SECURITY_PACKAGE@@EA; _DLL_SECURITY_PACKAGE * SecGlobalExtenderPackage
0x1800075fe  test    rax, rax
0x180007601  cmovnz  rbx, rax
0x180007605  jmp     short loc_1800075C9
```
