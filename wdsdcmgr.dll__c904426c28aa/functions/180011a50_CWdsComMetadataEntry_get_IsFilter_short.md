# CWdsComMetadataEntry::get_IsFilter(short *)

- ea: `0x180011a50`
- end: `0x180011aa6`
- name: `?get_IsFilter@CWdsComMetadataEntry@@UEAAJPEAF@Z`
- size: `86`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180011a50`
- `0x180014ee0`

## string_xrefs

- `0x180011a71`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::get_IsFilter(CWdsComMetadataEntry *this, __int16 *a2)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( a2
    || (v2 = -2147024809,
        (int)ElValidateHr(-2147024809, 0, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0xF6u) >= 0) )
  {
    *a2 = -(*((_DWORD *)this + 24) != 0);
  }
  return v2;
}

```

## disassembly

```asm
0x180011a50  mov     [rsp+arg_0], rbx
0x180011a55  mov     [rsp+arg_8], rsi
0x180011a5a  push    rdi
0x180011a5b  sub     rsp, 20h
0x180011a5f  xor     ebx, ebx
0x180011a61  mov     rdi, rdx
0x180011a64  mov     rsi, rcx
0x180011a67  test    rdx, rdx
0x180011a6a  jnz     short loc_180011A89
0x180011a6c  mov     ebx, 80070057h
0x180011a71  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011a78  mov     ecx, ebx; int
0x180011a7a  mov     r9d, 0F6h; unsigned int
0x180011a80  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011a85  test    eax, eax
0x180011a87  js      short loc_180011A94
0x180011a89  mov     ecx, [rsi+60h]
0x180011a8c  neg     ecx
0x180011a8e  sbb     dx, dx
0x180011a91  mov     [rdi], dx
0x180011a94  mov     rsi, [rsp+28h+arg_8]
0x180011a99  mov     eax, ebx
0x180011a9b  mov     rbx, [rsp+28h+arg_0]
0x180011aa0  add     rsp, 20h
0x180011aa4  pop     rdi
0x180011aa5  retn
```
