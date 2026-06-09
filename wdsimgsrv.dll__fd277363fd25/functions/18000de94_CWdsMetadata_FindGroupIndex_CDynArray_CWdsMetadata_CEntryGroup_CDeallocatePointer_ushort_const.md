# CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)

- ea: `0x18000de94`
- end: `0x18000df1e`
- name: `?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800096e8`
- `0x18000d1b8`
- `0x18000df74`
- `0x18000e724`
- `0x18000f6b4`
- `0x18000f784`

## callees

- `0x18000de94`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000dedc`
- `msvcrt!_wcsicmp` at `0x18000dedc`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::FindGroupIndex(__int64 a1, __int64 *a2, const wchar_t *a3)
{
  int v3; // esi
  unsigned int v4; // edi
  __int64 v5; // r15
  int v7; // ebx
  int i; // esi
  __int64 v9; // rbp
  int v10; // ecx
  int v11; // eax

  v3 = *((_DWORD *)a2 + 3);
  v4 = -1;
  v5 = *a2;
  if ( v3 )
  {
    v7 = 0;
    for ( i = v3 - 1; v7 <= i; i = v11 )
    {
      v9 = (i + v7) / 2;
      v10 = _wcsicmp(a3, **(const wchar_t ***)(v5 + 8 * v9));
      if ( !v10 )
        return (unsigned int)((i + v7) / 2);
      if ( v10 >= 0 )
        v7 = v9 + 1;
      v11 = v9 - 1;
      if ( v10 >= 0 )
        v11 = i;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000de94  mov     [rsp+arg_0], rbx
0x18000de99  mov     [rsp+arg_8], rbp
0x18000de9e  mov     [rsp+arg_10], rsi
0x18000dea3  push    rdi
0x18000dea4  push    r14
0x18000dea6  push    r15
0x18000dea8  sub     rsp, 20h
0x18000deac  mov     esi, [rdx+0Ch]
0x18000deaf  or      edi, 0FFFFFFFFh
0x18000deb2  mov     r15, [rdx]
0x18000deb5  mov     r14, r8
0x18000deb8  test    esi, esi
0x18000deba  jz      short loc_18000DF02
0x18000debc  xor     ebx, ebx
0x18000debe  dec     esi
0x18000dec0  cmp     ebx, esi
0x18000dec2  jg      short loc_18000DF02
0x18000dec4  lea     eax, [rsi+rbx]
0x18000dec7  mov     ecx, 2
0x18000decc  cdq
0x18000decd  idiv    ecx
0x18000decf  mov     rcx, r14; String1
0x18000ded2  movsxd  rbp, eax
0x18000ded5  mov     rdx, [r15+rbp*8]
0x18000ded9  mov     rdx, [rdx]; String2
0x18000dedc  call    cs:__imp__wcsicmp
0x18000dee3  nop     dword ptr [rax+rax+00h]
0x18000dee8  mov     ecx, eax
0x18000deea  test    eax, eax
0x18000deec  jz      short loc_18000DF00
0x18000deee  test    ecx, ecx
0x18000def0  lea     eax, [rbp+1]
0x18000def3  cmovns  ebx, eax
0x18000def6  lea     eax, [rbp-1]
0x18000def9  cmovns  eax, esi
0x18000defc  mov     esi, eax
0x18000defe  jmp     short loc_18000DEC0
0x18000df00  mov     edi, ebp
0x18000df02  mov     rbx, [rsp+38h+arg_0]
0x18000df07  mov     eax, edi
0x18000df09  mov     rbp, [rsp+38h+arg_8]
0x18000df0e  mov     rsi, [rsp+38h+arg_10]
0x18000df13  add     rsp, 20h
0x18000df17  pop     r15
0x18000df19  pop     r14
0x18000df1b  pop     rdi
0x18000df1c  retn
```
