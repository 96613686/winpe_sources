# CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)

- ea: `0x18000a7ec`
- end: `0x18000a867`
- name: `?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z`
- size: `123`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a644`
- `0x18000a870`
- `0x18000aaac`
- `0x18000ab70`
- `0x18000adf4`
- `0x18000ae38`
- `0x18000b47c`
- `0x18000c4e0`
- `0x18000c8c4`
- `0x18000ce50`
- `0x18000d160`

## callees

- `0x18000a7ec`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000a830`
- `msvcrt!_wcsicmp` at `0x18000a830`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::FindGroupIndex(__int64 a1, __int64 *a2, const wchar_t *a3)
{
  int v3; // ebx
  unsigned int v4; // ebp
  __int64 v5; // r15
  int v7; // esi
  int v8; // ebx
  __int64 v9; // rdi
  int v10; // eax

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
        v10 = _wcsicmp(a3, **(const wchar_t ***)(v5 + 8 * v9));
        if ( !v10 )
          break;
        if ( v10 >= 0 )
          v7 = v9 + 1;
        else
          v8 = v9 - 1;
        if ( v7 > v8 )
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
0x18000a7ec  mov     [rsp+arg_0], rbx
0x18000a7f1  mov     [rsp+arg_8], rbp
0x18000a7f6  mov     [rsp+arg_10], rsi
0x18000a7fb  push    rdi
0x18000a7fc  push    r14
0x18000a7fe  push    r15
0x18000a800  sub     rsp, 20h
0x18000a804  mov     ebx, [rdx+0Ch]
0x18000a807  or      ebp, 0FFFFFFFFh
0x18000a80a  mov     r15, [rdx]
0x18000a80d  mov     r14, r8
0x18000a810  test    ebx, ebx
0x18000a812  jz      short loc_18000A84C
0x18000a814  xor     esi, esi
0x18000a816  sub     ebx, 1
0x18000a819  js      short loc_18000A84C
0x18000a81b  lea     eax, [rbx+rsi]
0x18000a81e  mov     rcx, r14; String1
0x18000a821  cdq
0x18000a822  sub     eax, edx
0x18000a824  sar     eax, 1
0x18000a826  movsxd  rdi, eax
0x18000a829  mov     rdx, [r15+rdi*8]
0x18000a82d  mov     rdx, [rdx]; String2
0x18000a830  call    cs:__imp__wcsicmp
0x18000a836  test    eax, eax
0x18000a838  jz      short loc_18000A84A
0x18000a83a  jns     short loc_18000A841
0x18000a83c  lea     ebx, [rdi-1]
0x18000a83f  jmp     short loc_18000A844
0x18000a841  lea     esi, [rdi+1]
0x18000a844  cmp     esi, ebx
0x18000a846  jle     short loc_18000A81B
0x18000a848  jmp     short loc_18000A84C
0x18000a84a  mov     ebp, edi
0x18000a84c  mov     rbx, [rsp+38h+arg_0]
0x18000a851  mov     eax, ebp
0x18000a853  mov     rbp, [rsp+38h+arg_8]
0x18000a858  mov     rsi, [rsp+38h+arg_10]
0x18000a85d  add     rsp, 20h
0x18000a861  pop     r15
0x18000a863  pop     r14
0x18000a865  pop     rdi
0x18000a866  retn
```
