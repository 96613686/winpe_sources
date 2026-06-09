# CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)

- ea: `0x180009684`
- end: `0x18000970e`
- name: `?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z`
- size: `138`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180008ec0`
- `0x1800093e0`
- `0x180009640`
- `0x180009770`
- `0x180009e70`
- `0x18000a6a0`
- `0x18000ba40`

## callees

- `0x180009684`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800096c8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800096c8`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::FindGroupIndex(__int64 a1, __int64 *a2, __int64 a3)
{
  int v3; // edi
  unsigned int v4; // ebx
  __int64 v5; // r15
  int v7; // esi
  int v8; // edi
  __int64 v9; // rbp
  int v10; // ecx
  int v11; // eax

  v3 = *((_DWORD *)a2 + 3);
  v4 = -1;
  v5 = *a2;
  if ( v3 )
  {
    v7 = 0;
    v8 = v3 - 1;
    if ( v8 >= 0 )
    {
      while ( 1 )
      {
        v9 = (v8 + v7) / 2;
        v10 = _o__wcsicmp(a3, **(_QWORD **)(v5 + 8 * v9));
        if ( !v10 )
          break;
        v11 = v9 - 1;
        if ( v10 >= 0 )
          v11 = v8;
        v8 = v11;
        if ( v10 >= 0 )
          v7 = v9 + 1;
        if ( v7 > v11 )
          return v4;
      }
      return (unsigned int)((v8 + v7) / 2);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180009684  mov     [rsp+arg_0], rbx
0x180009689  mov     [rsp+arg_8], rbp
0x18000968e  mov     [rsp+arg_10], rsi
0x180009693  push    rdi
0x180009694  push    r14
0x180009696  push    r15
0x180009698  sub     rsp, 20h
0x18000969c  mov     edi, [rdx+0Ch]
0x18000969f  or      ebx, 0FFFFFFFFh
0x1800096a2  mov     r15, [rdx]
0x1800096a5  mov     r14, r8
0x1800096a8  test    edi, edi
0x1800096aa  jz      short loc_1800096F2
0x1800096ac  xor     esi, esi
0x1800096ae  sub     edi, 1
0x1800096b1  js      short loc_1800096F2
0x1800096b3  lea     eax, [rdi+rsi]
0x1800096b6  mov     rcx, r14
0x1800096b9  cdq
0x1800096ba  sub     eax, edx
0x1800096bc  sar     eax, 1
0x1800096be  movsxd  rbp, eax
0x1800096c1  mov     rdx, [r15+rbp*8]
0x1800096c5  mov     rdx, [rdx]
0x1800096c8  call    cs:__imp__o__wcsicmp
0x1800096cf  nop     dword ptr [rax+rax+00h]
0x1800096d4  mov     ecx, eax
0x1800096d6  test    eax, eax
0x1800096d8  jz      short loc_1800096F0
0x1800096da  test    ecx, ecx
0x1800096dc  lea     eax, [rbp-1]
0x1800096df  cmovns  eax, edi
0x1800096e2  mov     edi, eax
0x1800096e4  lea     eax, [rbp+1]
0x1800096e7  cmovns  esi, eax
0x1800096ea  cmp     esi, edi
0x1800096ec  jle     short loc_1800096B3
0x1800096ee  jmp     short loc_1800096F2
0x1800096f0  mov     ebx, ebp
0x1800096f2  mov     rbp, [rsp+38h+arg_8]
0x1800096f7  mov     eax, ebx
0x1800096f9  mov     rbx, [rsp+38h+arg_0]
0x1800096fe  mov     rsi, [rsp+38h+arg_10]
0x180009703  add     rsp, 20h
0x180009707  pop     r15
0x180009709  pop     r14
0x18000970b  pop     rdi
0x18000970c  retn
```
