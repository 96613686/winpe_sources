# CWdsComMetadataEntry::ToString(ushort * *)

- ea: `0x180012480`
- end: `0x180012510`
- name: `?ToString@CWdsComMetadataEntry@@UEAAJPEAPEAG@Z`
- size: `144`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a3f0`
- `0x180012480`
- `0x180014d58`
- `0x1800150b8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800124d6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800124d6`

## string_xrefs

- `0x1800124ad`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::ToString(CWdsComMetadataEntry *this, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  signed int v4; // esi
  const char *v5; // rdx
  unsigned __int16 *v6; // rax
  OLECHAR *psz; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  psz = 0;
  v4 = CWdsMetadataEntry::ToString((CWdsComMetadataEntry *)((char *)this + 64), &psz);
  if ( ElValidateWin32(v4, v5, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x2FAu) )
  {
    v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 <= 0 )
      v3 = v4;
  }
  else
  {
    v6 = SysAllocString(psz);
    if ( v6 )
      *a2 = v6;
    else
      v3 = -2147024882;
  }
  if ( psz )
    operator delete(psz);
  return v3;
}

```

## disassembly

```asm
0x180012480  mov     rax, rsp
0x180012483  mov     [rax+10h], rbx
0x180012487  mov     [rax+18h], rsi
0x18001248b  push    r14
0x18001248d  sub     rsp, 20h
0x180012491  mov     r14, rdx
0x180012494  xor     ebx, ebx
0x180012496  and     [rax+8], rbx
0x18001249a  lea     rdx, [rax+8]; unsigned __int16 **
0x18001249e  add     rcx, 40h ; '@'; this
0x1800124a2  call    ?ToString@CWdsMetadataEntry@@QEBAKPEAPEAG@Z; CWdsMetadataEntry::ToString(ushort * *)
0x1800124a7  mov     r9d, 2FAh; unsigned int
0x1800124ad  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800124b4  mov     ecx, eax; unsigned int
0x1800124b6  mov     esi, eax
0x1800124b8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800124bd  test    eax, eax
0x1800124bf  jz      short loc_1800124D1
0x1800124c1  movzx   ebx, si
0x1800124c4  or      ebx, 80070000h
0x1800124ca  test    esi, esi
0x1800124cc  cmovle  ebx, esi
0x1800124cf  jmp     short loc_1800124EB
0x1800124d1  mov     rcx, [rsp+28h+psz]; psz
0x1800124d6  call    cs:__imp_SysAllocString
0x1800124dc  test    rax, rax
0x1800124df  jnz     short loc_1800124E8
0x1800124e1  mov     ebx, 8007000Eh
0x1800124e6  jmp     short loc_1800124EB
0x1800124e8  mov     [r14], rax
0x1800124eb  cmp     [rsp+28h+psz], 0
0x1800124f1  jz      short loc_1800124FD
0x1800124f3  mov     rcx, [rsp+28h+psz]; Block
0x1800124f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800124fd  mov     rsi, [rsp+28h+arg_10]
0x180012502  mov     eax, ebx
0x180012504  mov     rbx, [rsp+28h+arg_8]
0x180012509  add     rsp, 20h
0x18001250d  pop     r14
0x18001250f  retn
```
