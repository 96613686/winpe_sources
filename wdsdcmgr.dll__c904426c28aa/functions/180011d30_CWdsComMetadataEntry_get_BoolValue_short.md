# CWdsComMetadataEntry::get_BoolValue(short *)

- ea: `0x180011d30`
- end: `0x180011de9`
- name: `?get_BoolValue@CWdsComMetadataEntry@@UEAAJPEAF@Z`
- size: `185`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180011d30`
- `0x180014d58`
- `0x180014ee0`

## string_xrefs

- `0x180011d5d`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180011da1`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::get_BoolValue(CWdsComMetadataEntry *this, char *a2)
{
  unsigned int v2; // ebx
  int v3; // esi
  signed int v6; // edi

  v2 = 0;
  v3 = 0;
  if ( a2
    || (v2 = -2147024809,
        (int)ElValidateHr(-2147024809, 0, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x1C0u) >= 0) )
  {
    v6 = 0;
    if ( *((_DWORD *)this + 26) == 2 )
      v3 = *((_DWORD *)this + 28);
    else
      v6 = ElValidateWin32(0xDu, a2, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x633u);
    if ( ElValidateWin32(v6, a2, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x1C4u) )
    {
      v2 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        return (unsigned int)v6;
    }
    else
    {
      *(_WORD *)a2 = -(v3 != 0);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180011d30  mov     rax, rsp
0x180011d33  mov     [rax+8], rbx
0x180011d37  mov     [rax+10h], rbp
0x180011d3b  mov     [rax+18h], rsi
0x180011d3f  mov     [rax+20h], rdi
0x180011d43  push    r14
0x180011d45  sub     rsp, 20h
0x180011d49  xor     ebx, ebx
0x180011d4b  xor     esi, esi
0x180011d4d  mov     r14, rdx
0x180011d50  mov     rbp, rcx
0x180011d53  test    rdx, rdx
0x180011d56  jnz     short loc_180011D75
0x180011d58  mov     ebx, 80070057h
0x180011d5d  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011d64  mov     ecx, ebx; int
0x180011d66  mov     r9d, 1C0h; unsigned int
0x180011d6c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011d71  test    eax, eax
0x180011d73  js      short loc_180011DCC
0x180011d75  xor     edi, edi
0x180011d77  cmp     dword ptr [rbp+68h], 2
0x180011d7b  jnz     short loc_180011D82
0x180011d7d  mov     esi, [rbp+70h]
0x180011d80  jmp     short loc_180011D9B
0x180011d82  mov     r9d, 633h; unsigned int
0x180011d88  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180011d8f  mov     ecx, 0Dh; unsigned int
0x180011d94  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011d99  mov     edi, eax
0x180011d9b  mov     r9d, 1C4h; unsigned int
0x180011da1  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011da8  mov     ecx, edi; unsigned int
0x180011daa  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011daf  test    eax, eax
0x180011db1  jz      short loc_180011DC3
0x180011db3  movzx   ebx, di
0x180011db6  or      ebx, 80070000h
0x180011dbc  test    edi, edi
0x180011dbe  cmovle  ebx, edi
0x180011dc1  jmp     short loc_180011DCC
0x180011dc3  neg     esi
0x180011dc5  sbb     cx, cx
0x180011dc8  mov     [r14], cx
0x180011dcc  mov     rbp, [rsp+28h+arg_8]
0x180011dd1  mov     eax, ebx
0x180011dd3  mov     rbx, [rsp+28h+arg_0]
0x180011dd8  mov     rsi, [rsp+28h+arg_10]
0x180011ddd  mov     rdi, [rsp+28h+arg_18]
0x180011de2  add     rsp, 20h
0x180011de6  pop     r14
0x180011de8  retn
```
