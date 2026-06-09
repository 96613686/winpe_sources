# CompareItemData(_ITEM_DATA *,_ITEM_DATA *)

- ea: `0x140029454`
- end: `0x1400294d7`
- name: `?CompareItemData@@YAJPEAU_ITEM_DATA@@0@Z`
- size: `131`
- prototype: `LONG __fastcall(struct _ITEM_DATA *, struct _ITEM_DATA *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140028464`
- `0x1400286b0`
- `0x140028b3c`
- `0x140028cc4`
- `0x14002956c`
- `0x14002c998`
- `0x14002df2c`

## callees

- `0x140029454`

## import_xrefs

- `ntdll!RtlCompareString` at `0x1400294cc`
- `ntdll!RtlCompareString` at `0x1400294cc`

## pseudocode

```c
LONG __fastcall CompareItemData(struct _ITEM_DATA *a1, struct _ITEM_DATA *a2)
{
  int v2; // eax
  double v3; // xmm0_8
  double v4; // xmm1_8
  STRING String2; // [rsp+20h] [rbp-28h] BYREF
  STRING String1; // [rsp+30h] [rbp-18h] BYREF

  v2 = 0;
  String1 = 0;
  String2 = 0;
  if ( *((_BYTE *)a1 + 25) )
  {
    v3 = *((double *)a2 + 1);
    v4 = *((double *)a1 + 1);
    if ( v4 <= v3 )
    {
      LOBYTE(v2) = v3 <= v4;
      return v2 - 1;
    }
    else
    {
      return 1;
    }
  }
  else
  {
    String1.Buffer = (PCHAR)*((_QWORD *)a1 + 1);
    String1.Length = *((_WORD *)a1 + 8);
    String1.MaximumLength = String1.Length;
    String2.Buffer = (PCHAR)*((_QWORD *)a2 + 1);
    String2.Length = *((_WORD *)a2 + 8);
    String2.MaximumLength = String2.Length;
    return RtlCompareString(&String1, &String2, 0);
  }
}

```

## disassembly

```asm
0x140029454  sub     rsp, 48h
0x140029458  xor     eax, eax
0x14002945a  xorps   xmm0, xmm0
0x14002945d  xorps   xmm1, xmm1
0x140029460  movups  xmmword ptr [rsp+48h+String1.Length], xmm0
0x140029465  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x14002946a  cmp     [rcx+19h], al
0x14002946d  jz      short loc_140029491
0x14002946f  movsd   xmm0, qword ptr [rdx+8]
0x140029474  movsd   xmm1, qword ptr [rcx+8]
0x140029479  comisd  xmm1, xmm0
0x14002947d  jbe     short loc_140029486
0x14002947f  mov     eax, 1
0x140029484  jmp     short loc_1400294D2
0x140029486  comisd  xmm0, xmm1
0x14002948a  setbe   al
0x14002948d  dec     eax
0x14002948f  jmp     short loc_1400294D2
0x140029491  mov     rax, [rcx+8]
0x140029495  xor     r8d, r8d; CaseInSensitive
0x140029498  mov     [rsp+48h+String1.Buffer], rax
0x14002949d  movzx   eax, word ptr [rcx+10h]
0x1400294a1  lea     rcx, [rsp+48h+String1]; String1
0x1400294a6  mov     [rsp+48h+String1.Length], ax
0x1400294ab  mov     [rsp+48h+String1.MaximumLength], ax
0x1400294b0  mov     rax, [rdx+8]
0x1400294b4  mov     [rsp+48h+String2.Buffer], rax
0x1400294b9  movzx   eax, word ptr [rdx+10h]
0x1400294bd  lea     rdx, [rsp+48h+String2]; String2
0x1400294c2  mov     [rsp+48h+String2.Length], ax
0x1400294c7  mov     [rsp+48h+String2.MaximumLength], ax
0x1400294cc  call    cs:__imp_RtlCompareString
0x1400294d2  add     rsp, 48h
0x1400294d6  retn
```
