# CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)

- ea: `0x180020558`
- end: `0x180020613`
- name: `?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z`
- size: `187`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int Src)`
- caller_count: `13`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800067f0`
- `0x1800156f0`
- `0x1800175b4`
- `0x18001b9f8`
- `0x180020840`
- `0x180021110`
- `0x180021450`
- `0x180021504`
- `0x180021650`
- `0x180021828`
- `0x1800218e0`
- `0x180021c14`
- `0x180021ccc`

## callees

- `0x18001a9a8`
- `0x18002048c`
- `0x180020558`
- `0x180026d3a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800205ce`
- `KERNEL32!GetLastError` at `0x1800205ce`
- `WDSCSL!WdsCpParameterAdd` at `0x1800205c3`
- `WDSCSL!WdsCpParameterAdd` at `0x1800205c3`

## pseudocode

```c
__int64 __fastcall CControlPacket::AddULONG(
        CControlPacket *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int Src)
{
  DWORD LastError; // edi
  unsigned __int16 *v6; // rbx
  int v8; // esi
  unsigned int v9; // eax
  void *v10; // rax
  unsigned __int16 *v12; // [rsp+30h] [rbp-18h] BYREF

  LastError = 0;
  v12 = 0;
  v6 = a2;
  if ( a4 != -1 || a3 )
  {
    v8 = 1;
    v9 = CControlPacket::ConstructName(this, a2, a3, a4, &v12);
    v6 = v12;
    LastError = v9;
    if ( v9 )
    {
LABEL_9:
      if ( v6 )
        operator delete(v6);
      return LastError;
    }
  }
  else
  {
    v8 = 0;
  }
  v10 = (void *)WdsCpParameterAdd(*((_QWORD *)this + 1), v6, 4);
  if ( v10 )
    memmove_0(v10, &Src, 4u);
  else
    LastError = GetLastError();
  if ( v8 )
    goto LABEL_9;
  return LastError;
}

```

## disassembly

```asm
0x180020558  mov     r11, rsp
0x18002055b  mov     [r11+8], rbx
0x18002055f  mov     [r11+10h], rbp
0x180020563  mov     [r11+18h], rsi
0x180020567  push    rdi
0x180020568  sub     rsp, 40h
0x18002056c  mov     eax, [rsp+48h+Src]
0x180020570  xor     edi, edi
0x180020572  and     [r11-18h], rdi
0x180020576  mov     rbx, rdx
0x180020579  mov     [rsp+48h+Src], eax
0x18002057d  mov     rbp, rcx
0x180020580  cmp     r9d, 0FFFFFFFFh
0x180020584  jnz     short loc_18002058F
0x180020586  test    r8, r8
0x180020589  jnz     short loc_18002058F
0x18002058b  xor     esi, esi
0x18002058d  jmp     short loc_1800205AE
0x18002058f  lea     rax, [rsp+48h+var_18]
0x180020594  mov     esi, 1
0x180020599  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x18002059e  call    ?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)
0x1800205a3  mov     rbx, [rsp+48h+var_18]
0x1800205a8  mov     edi, eax
0x1800205aa  test    eax, eax
0x1800205ac  jnz     short loc_1800205EF
0x1800205ae  mov     rcx, [rbp+8]
0x1800205b2  mov     r9d, 4
0x1800205b8  and     dword ptr [rsp+48h+var_28], 0
0x1800205bd  mov     r8d, r9d
0x1800205c0  mov     rdx, rbx
0x1800205c3  call    cs:__imp_WdsCpParameterAdd
0x1800205c9  test    rax, rax
0x1800205cc  jnz     short loc_1800205D8
0x1800205ce  call    cs:__imp_GetLastError
0x1800205d4  mov     edi, eax
0x1800205d6  jmp     short loc_1800205EB
0x1800205d8  mov     r8d, 4; Size
0x1800205de  lea     rdx, [rsp+48h+Src]; Src
0x1800205e3  mov     rcx, rax; void *
0x1800205e6  call    memmove_0
0x1800205eb  test    esi, esi
0x1800205ed  jz      short loc_1800205FC
0x1800205ef  test    rbx, rbx
0x1800205f2  jz      short loc_1800205FC
0x1800205f4  mov     rcx, rbx; void *
0x1800205f7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800205fc  mov     rbx, [rsp+48h+arg_0]
0x180020601  mov     eax, edi
0x180020603  mov     rbp, [rsp+48h+arg_8]
0x180020608  mov     rsi, [rsp+48h+arg_10]
0x18002060d  add     rsp, 40h
0x180020611  pop     rdi
0x180020612  retn
```
