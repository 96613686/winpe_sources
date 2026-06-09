# CWshEnvRegistry::get_Item(ushort *,ushort * *)

- ea: `0x18000bfc0`
- end: `0x18000c004`
- name: `?get_Item@CWshEnvRegistry@@UEAAJPEAGPEAPEAG@Z`
- size: `68`
- prototype: `int(CWshEnvRegistry *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000bfc0`
- `0x18000c128`
- `0x18000c3ec`

## pseudocode

```c
__int64 __fastcall CWshEnvRegistry::get_Item(CWshEnvRegistry *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 result; // rax
  const unsigned __int16 *v5; // rdx
  int ItemW; // eax
  int v7; // ecx

  if ( !a3 )
    return 2147500035LL;
  v5 = &psz;
  if ( a2 )
    v5 = a2;
  if ( Global::g_fWindowsNT )
    ItemW = CWshEnvRegistry::get_ItemW(this, v5, a3);
  else
    ItemW = CWshEnvRegistry::get_ItemA(this, v5, a3);
  v7 = ItemW;
  result = 0;
  if ( v7 < 0 )
    return (unsigned int)v7;
  return result;
}

```

## disassembly

```asm
0x18000bfc0  sub     rsp, 28h
0x18000bfc4  mov     rax, rdx
0x18000bfc7  test    r8, r8
0x18000bfca  jnz     short loc_18000BFD3
0x18000bfcc  mov     eax, 80004003h
0x18000bfd1  jmp     short loc_18000BFFF
0x18000bfd3  test    rax, rax
0x18000bfd6  lea     rdx, psz
0x18000bfdd  cmovnz  rdx, rax; unsigned __int16 *
0x18000bfe1  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x18000bfe8  jz      short loc_18000BFF1
0x18000bfea  call    ?get_ItemW@CWshEnvRegistry@@AEAAJPEBGPEAPEAG@Z; CWshEnvRegistry::get_ItemW(ushort const *,ushort * *)
0x18000bfef  jmp     short loc_18000BFF6
0x18000bff1  call    ?get_ItemA@CWshEnvRegistry@@AEAAJPEBGPEAPEAG@Z; CWshEnvRegistry::get_ItemA(ushort const *,ushort * *)
0x18000bff6  mov     ecx, eax
0x18000bff8  xor     eax, eax
0x18000bffa  test    ecx, ecx
0x18000bffc  cmovs   eax, ecx
0x18000bfff  add     rsp, 28h
0x18000c003  retn
```
