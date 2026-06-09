# CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)

- ea: `0x18001284c`
- end: `0x180012909`
- name: `?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z`
- size: `189`
- prototype: `__int64 __fastcall(CControlPacket *this, unsigned __int16 *, const unsigned __int16 *, __int64, unsigned int)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002bd8`
- `0x18000d540`
- `0x18000dab4`
- `0x18000dbf4`
- `0x18000dd30`
- `0x1800114a4`

## callees

- `0x180012780`
- `0x18001284c`
- `0x1800150b8`
- `0x180015c91`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800128c4`
- `KERNEL32!GetLastError` at `0x1800128c4`
- `WDSCSL!WdsCpParameterAdd` at `0x1800128b9`
- `WDSCSL!WdsCpParameterAdd` at `0x1800128b9`

## pseudocode

```c
__int64 __fastcall CControlPacket::AddULONG(
        CControlPacket *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5)
{
  DWORD LastError; // edi
  unsigned __int16 *v6; // rbx
  int v8; // esi
  unsigned int v9; // eax
  void *v10; // rax
  __int64 v12; // [rsp+28h] [rbp-20h]
  void *Block[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int Src; // [rsp+68h] [rbp+20h] BYREF

  LastError = 0;
  Block[0] = 0;
  v6 = a2;
  Src = a5;
  if ( a3 )
  {
    v8 = 1;
    v9 = CControlPacket::ConstructName(
           this,
           a2,
           a3,
           -1,
           (unsigned __int16 **)Block,
           v12,
           (__int64)Block[0],
           (__int64)Block[1],
           (__int64)Block[2]);
    v6 = (unsigned __int16 *)Block[0];
    LastError = v9;
    if ( v9 )
    {
LABEL_8:
      if ( v6 )
        operator delete(v6);
      return LastError;
    }
  }
  else
  {
    v8 = 0;
  }
  v10 = (void *)WdsCpParameterAdd(*((_QWORD *)this + 1), v6, 4, 4, 0);
  if ( v10 )
    memmove_0(v10, &Src, 4u);
  else
    LastError = GetLastError();
  if ( v8 )
    goto LABEL_8;
  return LastError;
}

```

## disassembly

```asm
0x18001284c  mov     r11, rsp
0x18001284f  mov     [r11+8], rbx
0x180012853  mov     [r11+10h], rbp
0x180012857  mov     [r11+18h], rsi
0x18001285b  mov     [r11+20h], r9d
0x18001285f  push    rdi
0x180012860  sub     rsp, 40h
0x180012864  mov     eax, [rsp+48h+arg_20]
0x180012868  xor     edi, edi
0x18001286a  and     [r11-18h], rdi
0x18001286e  mov     rbx, rdx
0x180012871  mov     [rsp+48h+Src], eax
0x180012875  mov     rbp, rcx
0x180012878  test    r8, r8
0x18001287b  jnz     short loc_180012881
0x18001287d  xor     esi, esi
0x18001287f  jmp     short loc_1800128A4
0x180012881  lea     rax, [rsp+48h+Block]
0x180012886  or      r9d, 0FFFFFFFFh; unsigned int
0x18001288a  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x18001288f  mov     esi, 1
0x180012894  call    ?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)
0x180012899  mov     rbx, [rsp+48h+Block]
0x18001289e  mov     edi, eax
0x1800128a0  test    eax, eax
0x1800128a2  jnz     short loc_1800128E5
0x1800128a4  mov     rcx, [rbp+8]
0x1800128a8  mov     r9d, 4
0x1800128ae  and     dword ptr [rsp+48h+var_28], 0
0x1800128b3  mov     r8d, r9d
0x1800128b6  mov     rdx, rbx
0x1800128b9  call    cs:__imp_WdsCpParameterAdd
0x1800128bf  test    rax, rax
0x1800128c2  jnz     short loc_1800128CE
0x1800128c4  call    cs:__imp_GetLastError
0x1800128ca  mov     edi, eax
0x1800128cc  jmp     short loc_1800128E1
0x1800128ce  mov     r8d, 4; Size
0x1800128d4  lea     rdx, [rsp+48h+Src]; Src
0x1800128d9  mov     rcx, rax; void *
0x1800128dc  call    memmove_0
0x1800128e1  test    esi, esi
0x1800128e3  jz      short loc_1800128F2
0x1800128e5  test    rbx, rbx
0x1800128e8  jz      short loc_1800128F2
0x1800128ea  mov     rcx, rbx; Block
0x1800128ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800128f2  mov     rbx, [rsp+48h+arg_0]
0x1800128f7  mov     eax, edi
0x1800128f9  mov     rbp, [rsp+48h+arg_8]
0x1800128fe  mov     rsi, [rsp+48h+arg_10]
0x180012903  add     rsp, 40h
0x180012907  pop     rdi
0x180012908  retn
```
