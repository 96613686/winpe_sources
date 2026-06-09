# CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x180012910`
- end: `0x1800129dc`
- name: `?AddString@CControlPacket@@QEAAKPEBG0K0@Z`
- size: `204`
- prototype: `__int64 __fastcall(CControlPacket *this, const char *, const unsigned __int16 *, int, unsigned __int16 *Src)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180002bd8`
- `0x18000d540`
- `0x18000dab4`
- `0x18000dbf4`
- `0x18000dcec`
- `0x1800114a4`

## callees

- `0x180012910`
- `0x180012bb4`
- `0x180014ee0`

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
  unsigned __int64 v10; // rsi
  int v11; // ebp
  unsigned int v12; // ebx
  int v14; // [rsp+20h] [rbp-48h]

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
  if ( (int)ElValidateHr(v12, a2, "base\\eco\\wds\\wdscsl\\lib\\controlpacket.cpp", 0x209u) >= 0 )
  {
    return (unsigned int)CControlPacket::AddVariable<unsigned short>(v6, v9, v8, a4, v14, v11, Src);
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
0x180012910  mov     [rsp+arg_0], rbx
0x180012915  mov     [rsp+arg_8], rbp
0x18001291a  mov     [rsp+arg_10], rsi
0x18001291f  push    rdi
0x180012920  push    r12
0x180012922  push    r13
0x180012924  push    r14
0x180012926  push    r15
0x180012928  sub     rsp, 40h
0x18001292c  mov     rdi, [rsp+68h+arg_20]
0x180012934  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012938  mov     r13, rcx
0x18001293b  mov     r14d, r9d
0x18001293e  xor     ecx, ecx
0x180012940  mov     r15, r8
0x180012943  mov     r12, rdx
0x180012946  inc     rax
0x180012949  cmp     [rdi+rax*2], cx
0x18001294d  jnz     short loc_180012946
0x18001294f  lea     rsi, [rax+1]
0x180012953  mov     r9d, 209h; unsigned int
0x180012959  mov     eax, 0FFFFFFFFh
0x18001295e  lea     r8, aBaseEcoWdsWdsc; "base\\eco\\wds\\wdscsl\\lib\\controlpac"...
0x180012965  cmp     rsi, rax
0x180012968  mov     ebp, eax
0x18001296a  cmovbe  ebp, esi
0x18001296d  cmp     rax, rsi
0x180012970  sbb     ebx, ebx
0x180012972  and     ebx, 80070216h
0x180012978  mov     ecx, ebx; int
0x18001297a  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18001297f  test    eax, eax
0x180012981  jns     short loc_1800129A0
0x180012983  mov     eax, 0FFFFFFFFh
0x180012988  cmp     rsi, rax
0x18001298b  jbe     short loc_1800129BC
0x18001298d  mov     eax, ebx
0x18001298f  and     eax, 1FFF0000h
0x180012994  cmp     eax, 70000h
0x180012999  jnz     short loc_1800129BC
0x18001299b  movzx   ebx, bx
0x18001299e  jmp     short loc_1800129BC
0x1800129a0  mov     [rsp+68h+Src], rdi; Src
0x1800129a5  mov     r9d, r14d; int
0x1800129a8  mov     r8, r15; int
0x1800129ab  mov     [rsp+68h+var_40], ebp; int
0x1800129af  mov     rdx, r12; int
0x1800129b2  mov     rcx, r13; int
0x1800129b5  call    ??$AddVariable@G@CControlPacket@@QEAAKPEBG0KKKPEAX@Z; CControlPacket::AddVariable<ushort>(ushort const *,ushort const *,ulong,ulong,ulong,void *)
0x1800129ba  mov     ebx, eax
0x1800129bc  lea     r11, [rsp+68h+var_28]
0x1800129c1  mov     eax, ebx
0x1800129c3  mov     rbx, [r11+30h]
0x1800129c7  mov     rbp, [r11+38h]
0x1800129cb  mov     rsi, [r11+40h]
0x1800129cf  mov     rsp, r11
0x1800129d2  pop     r15
0x1800129d4  pop     r14
0x1800129d6  pop     r13
0x1800129d8  pop     r12
0x1800129da  pop     rdi
0x1800129db  retn
```
