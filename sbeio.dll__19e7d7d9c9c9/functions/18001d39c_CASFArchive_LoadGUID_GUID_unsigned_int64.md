# CASFArchive::LoadGUID(_GUID &,unsigned __int64 *)

- ea: `0x18001d39c`
- end: `0x18001d41c`
- name: `?LoadGUID@CASFArchive@@QEAAJAEAU_GUID@@PEA_K@Z`
- size: `128`
- prototype: `__int64 __fastcall(CASFArchive *__hidden this, struct _GUID *, unsigned __int64 *)`
- caller_count: `15`
- callee_count: `4`
- tags: ``

## callers

- `0x1800209d0`
- `0x180020d20`
- `0x180020e70`
- `0x180021130`
- `0x180021cf0`
- `0x180021e90`
- `0x180022350`
- `0x180022590`
- `0x180022980`
- `0x180022b30`
- `0x180022d80`
- `0x180022f60`
- `0x1800230f0`
- `0x180023570`
- `0x180023760`

## callees

- `0x18001d100`
- `0x18001d340`
- `0x18001d39c`
- `0x18001d484`

## pseudocode

```c
__int64 __fastcall CASFArchive::LoadGUID(CASFArchive *this, struct _GUID *a2, unsigned __int64 *a3)
{
  __int64 result; // rax
  int i; // r11d
  int v8; // r11d

  result = CASFArchive::LoadDWORD(this, &a2->Data1, a3);
  if ( (int)result >= 0 )
  {
    result = CASFArchive::LoadWORD(this, &a2->Data2, a3);
    if ( (int)result >= 0 )
    {
      result = CASFArchive::LoadWORD(this, &a2->Data3, a3);
      if ( (int)result >= 0 )
      {
        for ( i = 0; i < 8; i = v8 + 1 )
        {
          result = CASFArchive::LoadBYTE(this, &a2->Data4[i], a3);
          if ( (int)result < 0 )
            return result;
        }
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d39c  mov     [rsp+arg_0], rbx
0x18001d3a1  mov     [rsp+arg_8], rsi
0x18001d3a6  push    rdi
0x18001d3a7  sub     rsp, 20h
0x18001d3ab  mov     rbx, r8
0x18001d3ae  mov     rdi, rdx
0x18001d3b1  mov     rsi, rcx
0x18001d3b4  call    ?LoadDWORD@CASFArchive@@QEAAJAEAKPEA_K@Z; CASFArchive::LoadDWORD(ulong &,unsigned __int64 *)
0x18001d3b9  test    eax, eax
0x18001d3bb  js      short loc_18001D40C
0x18001d3bd  lea     rdx, [rdi+4]; unsigned __int16 *
0x18001d3c1  mov     r8, rbx; unsigned __int64 *
0x18001d3c4  mov     rcx, rsi; this
0x18001d3c7  call    ?LoadWORD@CASFArchive@@QEAAJAEAGPEA_K@Z; CASFArchive::LoadWORD(ushort &,unsigned __int64 *)
0x18001d3cc  test    eax, eax
0x18001d3ce  js      short loc_18001D40C
0x18001d3d0  lea     rdx, [rdi+6]; unsigned __int16 *
0x18001d3d4  mov     r8, rbx; unsigned __int64 *
0x18001d3d7  mov     rcx, rsi; this
0x18001d3da  call    ?LoadWORD@CASFArchive@@QEAAJAEAGPEA_K@Z; CASFArchive::LoadWORD(ushort &,unsigned __int64 *)
0x18001d3df  test    eax, eax
0x18001d3e1  js      short loc_18001D40C
0x18001d3e3  xor     r11d, r11d
0x18001d3e6  cmp     r11d, 8
0x18001d3ea  jge     short loc_18001D40A
0x18001d3ec  movsxd  rdx, r11d
0x18001d3ef  mov     r8, rbx; unsigned __int64 *
0x18001d3f2  add     rdx, 8
0x18001d3f6  mov     rcx, rsi; this
0x18001d3f9  add     rdx, rdi; unsigned __int8 *
0x18001d3fc  call    ?LoadBYTE@CASFArchive@@QEAAJAEAEPEA_K@Z; CASFArchive::LoadBYTE(uchar &,unsigned __int64 *)
0x18001d401  test    eax, eax
0x18001d403  js      short loc_18001D40C
0x18001d405  inc     r11d
0x18001d408  jmp     short loc_18001D3E6
0x18001d40a  xor     eax, eax
0x18001d40c  mov     rbx, [rsp+28h+arg_0]
0x18001d411  mov     rsi, [rsp+28h+arg_8]
0x18001d416  add     rsp, 20h
0x18001d41a  pop     rdi
0x18001d41b  retn
```
