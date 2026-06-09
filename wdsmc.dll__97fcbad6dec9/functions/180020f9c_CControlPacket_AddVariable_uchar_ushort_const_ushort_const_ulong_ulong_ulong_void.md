# CControlPacket::AddVariable<uchar>(ushort const *,ushort const *,ulong,ulong,ulong,void *)

- ea: `0x180020f9c`
- end: `0x180021053`
- name: `??$AddVariable@E@CControlPacket@@QEAAKPEBG0KKKPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(int, int, int, int, int, size_t Size, void *Src)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800156f0`
- `0x1800175b4`
- `0x180020840`
- `0x180021650`
- `0x1800218e0`

## callees

- `0x18001a9a8`
- `0x18002048c`
- `0x180020f9c`
- `0x180026d3a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002100c`
- `KERNEL32!GetLastError` at `0x18002100c`
- `WDSCSL!WdsCpParameterAdd` at `0x180021001`
- `WDSCSL!WdsCpParameterAdd` at `0x180021001`

## pseudocode

```c
__int64 __fastcall CControlPacket::AddVariable<unsigned char>(
        CControlPacket *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        size_t Size,
        void *Src)
{
  DWORD LastError; // edi
  unsigned __int16 *v8; // rbx
  int v10; // esi
  unsigned int v11; // eax
  void *v12; // rax
  __int64 v14; // [rsp+28h] [rbp-20h]
  unsigned __int16 *v15[3]; // [rsp+30h] [rbp-18h] BYREF

  LastError = 0;
  v8 = (unsigned __int16 *)a2;
  v15[0] = 0;
  if ( a4 != -1 || a3 )
  {
    v10 = 1;
    v11 = CControlPacket::ConstructName(a1, a2, a3, a4, v15, v14, (__int64)v15[0], (__int64)v15[1], (__int64)v15[2]);
    v8 = v15[0];
    LastError = v11;
    if ( v11 )
    {
LABEL_9:
      if ( v8 )
        operator delete(v8);
      return LastError;
    }
  }
  else
  {
    v10 = 0;
  }
  v12 = (void *)WdsCpParameterAdd(*((_QWORD *)a1 + 1), v8, 64);
  if ( v12 )
    memmove_0(v12, Src, (unsigned int)Size);
  else
    LastError = GetLastError();
  if ( v10 )
    goto LABEL_9;
  return LastError;
}

```

## disassembly

```asm
0x180020f9c  mov     rax, rsp
0x180020f9f  mov     [rax+8], rbx
0x180020fa3  mov     [rax+10h], rbp
0x180020fa7  mov     [rax+18h], rsi
0x180020fab  push    rdi
0x180020fac  sub     rsp, 40h
0x180020fb0  xor     edi, edi
0x180020fb2  mov     rbx, rdx
0x180020fb5  and     [rax-18h], rdi
0x180020fb9  mov     rbp, rcx
0x180020fbc  cmp     r9d, 0FFFFFFFFh
0x180020fc0  jnz     short loc_180020FCB
0x180020fc2  test    r8, r8
0x180020fc5  jnz     short loc_180020FCB
0x180020fc7  xor     esi, esi
0x180020fc9  jmp     short loc_180020FEA
0x180020fcb  lea     rax, [rsp+48h+var_18]
0x180020fd0  mov     esi, 1
0x180020fd5  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x180020fda  call    ?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)
0x180020fdf  mov     rbx, [rsp+48h+var_18]
0x180020fe4  mov     edi, eax
0x180020fe6  test    eax, eax
0x180020fe8  jnz     short loc_18002102F
0x180020fea  mov     r9d, dword ptr [rsp+48h+Size]
0x180020fef  mov     r8d, 40h ; '@'
0x180020ff5  mov     rcx, [rbp+8]
0x180020ff9  mov     rdx, rbx
0x180020ffc  and     dword ptr [rsp+48h+var_28], 0
0x180021001  call    cs:__imp_WdsCpParameterAdd
0x180021007  test    rax, rax
0x18002100a  jnz     short loc_180021016
0x18002100c  call    cs:__imp_GetLastError
0x180021012  mov     edi, eax
0x180021014  jmp     short loc_18002102B
0x180021016  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x18002101b  mov     rcx, rax; void *
0x18002101e  mov     rdx, [rsp+48h+Src]; Src
0x180021026  call    memmove_0
0x18002102b  test    esi, esi
0x18002102d  jz      short loc_18002103C
0x18002102f  test    rbx, rbx
0x180021032  jz      short loc_18002103C
0x180021034  mov     rcx, rbx; void *
0x180021037  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002103c  mov     rbx, [rsp+48h+arg_0]
0x180021041  mov     eax, edi
0x180021043  mov     rbp, [rsp+48h+arg_8]
0x180021048  mov     rsi, [rsp+48h+arg_10]
0x18002104d  add     rsp, 40h
0x180021051  pop     rdi
0x180021052  retn
```
