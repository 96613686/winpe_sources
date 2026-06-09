# CControlPacket::AddULONG64(ushort const *,ushort const *,ulong,unsigned __int64)

- ea: `0x18002061c`
- end: `0x1800206d8`
- name: `?AddULONG64@CControlPacket@@QEAAKPEBG0K_K@Z`
- size: `188`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800175b4`
- `0x1800207c8`
- `0x180021110`
- `0x180021504`
- `0x180021650`
- `0x1800218e0`
- `0x180021ccc`

## callees

- `0x18001a9a8`
- `0x18002048c`
- `0x18002061c`
- `0x180026d3a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020693`
- `KERNEL32!GetLastError` at `0x180020693`
- `WDSCSL!WdsCpParameterAdd` at `0x180020688`
- `WDSCSL!WdsCpParameterAdd` at `0x180020688`

## pseudocode

```c
__int64 __fastcall CControlPacket::AddULONG64(
        CControlPacket *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v5; // rax
  DWORD LastError; // edi
  unsigned __int16 *v7; // rbx
  int v9; // esi
  unsigned int v10; // eax
  void *v11; // rax
  __int64 v13; // [rsp+28h] [rbp-20h]
  __int64 Src[3]; // [rsp+30h] [rbp-18h] BYREF

  v5 = a5;
  LastError = 0;
  a5 = 0;
  v7 = a2;
  Src[0] = (__int64)v5;
  if ( a4 != -1 || a3 )
  {
    v9 = 1;
    v10 = CControlPacket::ConstructName(this, a2, a3, a4, &a5, v13, Src[0], Src[1], Src[2]);
    v7 = a5;
    LastError = v10;
    if ( v10 )
    {
LABEL_9:
      if ( v7 )
        operator delete(v7);
      return LastError;
    }
  }
  else
  {
    v9 = 0;
  }
  v11 = (void *)WdsCpParameterAdd(*((_QWORD *)this + 1), v7, 8);
  if ( v11 )
    memmove_0(v11, Src, 8u);
  else
    LastError = GetLastError();
  if ( v9 )
    goto LABEL_9;
  return LastError;
}

```

## disassembly

```asm
0x18002061c  mov     r11, rsp
0x18002061f  mov     [r11+8], rbx
0x180020623  mov     [r11+10h], rbp
0x180020627  mov     [r11+18h], rsi
0x18002062b  push    rdi
0x18002062c  sub     rsp, 40h
0x180020630  mov     rax, [rsp+48h+arg_20]
0x180020635  xor     edi, edi
0x180020637  and     [r11+28h], rdi
0x18002063b  mov     rbx, rdx
0x18002063e  mov     [r11-18h], rax
0x180020642  mov     rbp, rcx
0x180020645  cmp     r9d, 0FFFFFFFFh
0x180020649  jnz     short loc_180020654
0x18002064b  test    r8, r8
0x18002064e  jnz     short loc_180020654
0x180020650  xor     esi, esi
0x180020652  jmp     short loc_180020673
0x180020654  lea     rax, [rsp+48h+arg_20]
0x180020659  mov     esi, 1
0x18002065e  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x180020663  call    ?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)
0x180020668  mov     rbx, [rsp+48h+arg_20]
0x18002066d  mov     edi, eax
0x18002066f  test    eax, eax
0x180020671  jnz     short loc_1800206B4
0x180020673  mov     rcx, [rbp+8]
0x180020677  mov     r9d, 8
0x18002067d  and     dword ptr [rsp+48h+var_28], 0
0x180020682  mov     r8d, r9d
0x180020685  mov     rdx, rbx
0x180020688  call    cs:__imp_WdsCpParameterAdd
0x18002068e  test    rax, rax
0x180020691  jnz     short loc_18002069D
0x180020693  call    cs:__imp_GetLastError
0x180020699  mov     edi, eax
0x18002069b  jmp     short loc_1800206B0
0x18002069d  mov     r8d, 8; Size
0x1800206a3  lea     rdx, [rsp+48h+Src]; Src
0x1800206a8  mov     rcx, rax; void *
0x1800206ab  call    memmove_0
0x1800206b0  test    esi, esi
0x1800206b2  jz      short loc_1800206C1
0x1800206b4  test    rbx, rbx
0x1800206b7  jz      short loc_1800206C1
0x1800206b9  mov     rcx, rbx; void *
0x1800206bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800206c1  mov     rbx, [rsp+48h+arg_0]
0x1800206c6  mov     eax, edi
0x1800206c8  mov     rbp, [rsp+48h+arg_8]
0x1800206cd  mov     rsi, [rsp+48h+arg_10]
0x1800206d2  add     rsp, 40h
0x1800206d6  pop     rdi
0x1800206d7  retn
```
