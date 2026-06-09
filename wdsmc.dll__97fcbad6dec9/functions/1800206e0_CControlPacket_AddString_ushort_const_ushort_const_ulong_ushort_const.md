# CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x1800206e0`
- end: `0x1800207c1`
- name: `?AddString@CControlPacket@@QEAAKPEBG0K0@Z`
- size: `225`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b9f8`
- `0x180021110`
- `0x180021504`
- `0x180021650`
- `0x1800218e0`

## callees

- `0x1800206e0`
- `0x180020ecc`
- `0x180025914`
- `0x1800259d8`

## pseudocode

```c
__int64 __fastcall CControlPacket::AddString(
        CControlPacket *this,
        const char *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 *Src)
{
  __int64 v5; // rax
  int v6; // r13d
  int v8; // r15d
  int v9; // r12d
  unsigned __int64 v10; // rdi
  int v11; // ebp
  unsigned int v12; // ebx
  const char *v13; // rdx
  const char *v14; // r8
  unsigned int v15; // r9d
  signed int v16; // eax
  int v18; // [rsp+20h] [rbp-48h]

  v5 = -1;
  v6 = (int)this;
  v8 = (int)a3;
  v9 = (int)a2;
  do
    ++v5;
  while ( Src[v5] );
  v10 = v5 + 1;
  v11 = -1;
  if ( (unsigned __int64)(v5 + 1) <= 0xFFFFFFFF )
    v11 = v5 + 1;
  v12 = v10 > 0xFFFFFFFF ? 0x80070216 : 0;
  ElValidateHrLite(v12, a2, "base\\eco\\wds\\wdscsl\\lib\\controlpacket.cpp", 0x209u);
  if ( v10 <= 0xFFFFFFFF )
    v16 = v10 > 0xFFFFFFFF ? 0x80070216 : 0;
  else
    v16 = ElValidateHr(v12, v13, v14, v15);
  if ( v16 >= 0 )
  {
    return (unsigned int)CControlPacket::AddVariable<unsigned short>(v6, v9, v8, a4, v18, v11, Src);
  }
  else if ( v10 > 0xFFFFFFFF && (v10 > 0xFFFFFFFF ? 0x70000 : 0) == 0x70000 )
  {
    return (unsigned __int16)v12;
  }
  return v12;
}

```

## disassembly

```asm
0x1800206e0  mov     [rsp+arg_0], rbx
0x1800206e5  mov     [rsp+arg_8], rbp
0x1800206ea  mov     [rsp+arg_10], rsi
0x1800206ef  push    rdi
0x1800206f0  push    r12
0x1800206f2  push    r13
0x1800206f4  push    r14
0x1800206f6  push    r15
0x1800206f8  sub     rsp, 40h
0x1800206fc  mov     rsi, [rsp+68h+arg_20]
0x180020704  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020708  mov     r13, rcx
0x18002070b  mov     r14d, r9d
0x18002070e  xor     ecx, ecx
0x180020710  mov     r15, r8
0x180020713  mov     r12, rdx
0x180020716  inc     rax
0x180020719  cmp     [rsi+rax*2], cx
0x18002071d  jnz     short loc_180020716
0x18002071f  lea     rdi, [rax+1]
0x180020723  mov     r9d, 209h; unsigned int
0x180020729  mov     eax, 0FFFFFFFFh
0x18002072e  lea     r8, aBaseEcoWdsWdsc; "base\\eco\\wds\\wdscsl\\lib\\controlpac"...
0x180020735  cmp     rdi, rax
0x180020738  mov     ebp, eax
0x18002073a  cmovbe  ebp, edi
0x18002073d  cmp     rax, rdi
0x180020740  sbb     ebx, ebx
0x180020742  and     ebx, 80070216h
0x180020748  mov     ecx, ebx; int
0x18002074a  call    ?ElValidateHrLite@@YAJJPEBD0K@Z; ElValidateHrLite(long,char const *,char const *,ulong)
0x18002074f  mov     ecx, 0FFFFFFFFh
0x180020754  cmp     rdi, rcx
0x180020757  jbe     short loc_180020767
0x180020759  mov     ecx, ebx; int
0x18002075b  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180020760  mov     ecx, 0FFFFFFFFh
0x180020765  jmp     short loc_180020769
0x180020767  mov     eax, ebx
0x180020769  test    eax, eax
0x18002076b  jns     short loc_180020785
0x18002076d  cmp     rdi, rcx
0x180020770  jbe     short loc_1800207A1
0x180020772  mov     eax, ebx
0x180020774  and     eax, 1FFF0000h
0x180020779  cmp     eax, 70000h
0x18002077e  jnz     short loc_1800207A1
0x180020780  movzx   ebx, bx
0x180020783  jmp     short loc_1800207A1
0x180020785  mov     [rsp+68h+Src], rsi; Src
0x18002078a  mov     r9d, r14d; int
0x18002078d  mov     r8, r15; int
0x180020790  mov     [rsp+68h+var_40], ebp; int
0x180020794  mov     rdx, r12; int
0x180020797  mov     rcx, r13; int
0x18002079a  call    ??$AddVariable@G@CControlPacket@@QEAAKPEBG0KKKPEAX@Z; CControlPacket::AddVariable<ushort>(ushort const *,ushort const *,ulong,ulong,ulong,void *)
0x18002079f  mov     ebx, eax
0x1800207a1  lea     r11, [rsp+68h+var_28]
0x1800207a6  mov     eax, ebx
0x1800207a8  mov     rbx, [r11+30h]
0x1800207ac  mov     rbp, [r11+38h]
0x1800207b0  mov     rsi, [r11+40h]
0x1800207b4  mov     rsp, r11
0x1800207b7  pop     r15
0x1800207b9  pop     r14
0x1800207bb  pop     r13
0x1800207bd  pop     r12
0x1800207bf  pop     rdi
0x1800207c0  retn
```
