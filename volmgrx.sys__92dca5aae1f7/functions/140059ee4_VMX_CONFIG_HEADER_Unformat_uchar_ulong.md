# VMX_CONFIG_HEADER::Unformat(uchar * *,ulong)

- ea: `0x140059ee4`
- end: `0x14005a16f`
- name: `?Unformat@VMX_CONFIG_HEADER@@QEAAJPEAPEAEK@Z`
- size: `651`
- prototype: `__int64 __fastcall(VMX_CONFIG_HEADER *__hidden this, unsigned __int8 **, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140045ddc`
- `0x1400462ec`
- `0x14005a178`

## callees

- `0x1400099d8`
- `0x14001ae08`
- `0x140059ee4`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140059f50`
- `ntoskrnl!RtlCompareMemory` at `0x140059f50`

## pseudocode

```c
__int64 __fastcall VMX_CONFIG_HEADER::Unformat(VMX_CONFIG_HEADER *this, unsigned __int8 **a2, unsigned int a3)
{
  VMX_NOTIFICATION_QUEUE *v6; // rcx
  __int64 v7; // rdx
  const void *v8; // rbp
  unsigned int v9; // esi
  unsigned __int8 *v10; // r9
  unsigned __int8 *v11; // rax

  if ( a3 < 4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3224895490LL;
    }
    v7 = 10;
LABEL_42:
    WPP_SF_d(*((_QWORD *)v6 + 3), v7, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids, 3224895490LL);
    return 3224895490LL;
  }
  v8 = *a2;
  if ( RtlCompareMemory(*a2, "VMDB", 4u) != 4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3224895490LL;
    }
    v7 = 11;
    goto LABEL_42;
  }
  v9 = (_DWORD)v8 + a3;
  v10 = VmxpUnformatTable(
          (const struct VMX_FIELD *)qword_140020240,
          6u,
          (char *)this,
          *a2 + 4,
          v9 - (*(_DWORD *)a2 + 4));
  if ( !v10 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3224895490LL;
    }
    v7 = 12;
    goto LABEL_42;
  }
  if ( *((_WORD *)this + 7) != 4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3224895490LL;
    }
    v7 = 13;
    goto LABEL_42;
  }
  v11 = VmxpUnformatTable((const struct VMX_FIELD *)qword_140020000, 0x12u, (char *)this, v10, v9 - (unsigned int)v10);
  if ( !v11 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3224895490LL;
    }
    v7 = 14;
    goto LABEL_42;
  }
  if ( *((_WORD *)this + 8) >= 0xAu )
  {
    v11 = VmxpUnformatTable((const struct VMX_FIELD *)qword_140020360, 1u, (char *)this, v11, v9 - (unsigned int)v11);
    if ( !v11 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return 3224895490LL;
      }
      v7 = 15;
      goto LABEL_42;
    }
  }
  if ( *((_DWORD *)this + 1) != 128 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3224895490LL;
    }
    v7 = 16;
    goto LABEL_42;
  }
  if ( *((_DWORD *)this + 2) != 512 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3224895490LL;
    }
    v7 = 17;
    goto LABEL_42;
  }
  *a2 = v11;
  return 0;
}

```

## disassembly

```asm
0x140059ee4  push    rbx
0x140059ee6  push    rbp
0x140059ee7  push    rsi
0x140059ee8  push    rdi
0x140059ee9  push    r14
0x140059eeb  push    r15
0x140059eed  sub     rsp, 38h
0x140059ef1  mov     r15d, 4
0x140059ef7  mov     esi, r8d
0x140059efa  mov     rdi, rdx
0x140059efd  mov     rbx, rcx
0x140059f00  mov     r14d, 0C0380002h
0x140059f06  cmp     r8d, r15d
0x140059f09  jnb     short loc_140059F40
0x140059f0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140059f12  lea     rax, WPP_GLOBAL_Control
0x140059f19  cmp     rcx, rax
0x140059f1c  jz      loc_14005A157
0x140059f22  mov     eax, [rcx+2Ch]
0x140059f25  test    al, 40h
0x140059f27  jz      loc_14005A157
0x140059f2d  cmp     byte ptr [rcx+29h], 2
0x140059f31  jb      loc_14005A157
0x140059f37  lea     edx, [r15+6]
0x140059f3b  jmp     loc_14005A144
0x140059f40  mov     rbp, [rdx]
0x140059f43  mov     r8, r15; Length
0x140059f46  mov     rcx, rbp; Source1
0x140059f49  lea     rdx, aVmdb; "VMDB"
0x140059f50  call    cs:__imp_RtlCompareMemory
0x140059f57  nop     dword ptr [rax+rax+00h]
0x140059f5c  cmp     rax, r15
0x140059f5f  jz      short loc_140059F97
0x140059f61  mov     rcx, cs:WPP_GLOBAL_Control
0x140059f68  lea     rax, WPP_GLOBAL_Control
0x140059f6f  cmp     rcx, rax
0x140059f72  jz      loc_14005A157
0x140059f78  mov     eax, [rcx+2Ch]
0x140059f7b  test    al, 40h
0x140059f7d  jz      loc_14005A157
0x140059f83  cmp     byte ptr [rcx+29h], 2
0x140059f87  jb      loc_14005A157
0x140059f8d  mov     edx, 0Bh
0x140059f92  jmp     loc_14005A144
0x140059f97  mov     r9, [rdi]
0x140059f9a  lea     rcx, qword_140020240; struct VMX_FIELD *
0x140059fa1  add     r9, r15; unsigned __int8 *
0x140059fa4  add     esi, ebp
0x140059fa6  mov     eax, esi
0x140059fa8  mov     r8, rbx; void *
0x140059fab  sub     eax, r9d
0x140059fae  mov     edx, 6; unsigned int
0x140059fb3  mov     [rsp+68h+var_48], eax; unsigned int
0x140059fb7  call    ?VmxpUnformatTable@@YAPEAEPEBVVMX_FIELD@@KPEAXPEAEK@Z; VmxpUnformatTable(VMX_FIELD const *,ulong,void *,uchar *,ulong)
0x140059fbc  mov     r9, rax; unsigned __int8 *
0x140059fbf  test    rax, rax
0x140059fc2  jnz     short loc_140059FF9
0x140059fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140059fcb  lea     rax, WPP_GLOBAL_Control
0x140059fd2  cmp     rcx, rax
0x140059fd5  jz      loc_14005A157
0x140059fdb  mov     eax, [rcx+2Ch]
0x140059fde  test    al, 40h
0x140059fe0  jz      loc_14005A157
0x140059fe6  cmp     byte ptr [rcx+29h], 2
0x140059fea  jb      loc_14005A157
0x140059ff0  lea     edx, [r9+0Ch]
0x140059ff4  jmp     loc_14005A144
0x140059ff9  cmp     [rbx+0Eh], r15w
0x140059ffe  jz      short loc_14005A036
0x14005a000  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a007  lea     rax, WPP_GLOBAL_Control
0x14005a00e  cmp     rcx, rax
0x14005a011  jz      loc_14005A157
0x14005a017  mov     eax, [rcx+2Ch]
0x14005a01a  test    al, 40h
0x14005a01c  jz      loc_14005A157
0x14005a022  cmp     byte ptr [rcx+29h], 2
0x14005a026  jb      loc_14005A157
0x14005a02c  mov     edx, 0Dh
0x14005a031  jmp     loc_14005A144
0x14005a036  mov     eax, esi
0x14005a038  lea     rcx, qword_140020000; struct VMX_FIELD *
0x14005a03f  sub     eax, r9d
0x14005a042  mov     r8, rbx; void *
0x14005a045  mov     edx, 12h; unsigned int
0x14005a04a  mov     [rsp+68h+var_48], eax; unsigned int
0x14005a04e  call    ?VmxpUnformatTable@@YAPEAEPEBVVMX_FIELD@@KPEAXPEAEK@Z; VmxpUnformatTable(VMX_FIELD const *,ulong,void *,uchar *,ulong)
0x14005a053  test    rax, rax
0x14005a056  jnz     short loc_14005A08E
0x14005a058  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a05f  lea     rax, WPP_GLOBAL_Control
0x14005a066  cmp     rcx, rax
0x14005a069  jz      loc_14005A157
0x14005a06f  mov     eax, [rcx+2Ch]
0x14005a072  test    al, 40h
0x14005a074  jz      loc_14005A157
0x14005a07a  cmp     byte ptr [rcx+29h], 2
0x14005a07e  jb      loc_14005A157
0x14005a084  mov     edx, 0Eh
0x14005a089  jmp     loc_14005A144
0x14005a08e  mov     edx, 0Ah
0x14005a093  cmp     [rbx+10h], dx
0x14005a097  jb      short loc_14005A0E6
0x14005a099  sub     esi, eax
0x14005a09b  lea     rcx, qword_140020360; struct VMX_FIELD *
0x14005a0a2  mov     r9, rax; unsigned __int8 *
0x14005a0a5  mov     [rsp+68h+var_48], esi; unsigned int
0x14005a0a9  mov     r8, rbx; void *
0x14005a0ac  mov     edx, 1; unsigned int
0x14005a0b1  call    ?VmxpUnformatTable@@YAPEAEPEBVVMX_FIELD@@KPEAXPEAEK@Z; VmxpUnformatTable(VMX_FIELD const *,ulong,void *,uchar *,ulong)
0x14005a0b6  test    rax, rax
0x14005a0b9  jnz     short loc_14005A0E6
0x14005a0bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a0c2  lea     rax, WPP_GLOBAL_Control
0x14005a0c9  cmp     rcx, rax
0x14005a0cc  jz      loc_14005A157
0x14005a0d2  mov     eax, [rcx+2Ch]
0x14005a0d5  test    al, 40h
0x14005a0d7  jz      short loc_14005A157
0x14005a0d9  cmp     byte ptr [rcx+29h], 2
0x14005a0dd  jb      short loc_14005A157
0x14005a0df  mov     edx, 0Fh
0x14005a0e4  jmp     short loc_14005A144
0x14005a0e6  cmp     dword ptr [rbx+4], 80h
0x14005a0ed  jz      short loc_14005A116
0x14005a0ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a0f6  lea     rax, WPP_GLOBAL_Control
0x14005a0fd  cmp     rcx, rax
0x14005a100  jz      short loc_14005A157
0x14005a102  mov     eax, [rcx+2Ch]
0x14005a105  test    al, 40h
0x14005a107  jz      short loc_14005A157
0x14005a109  cmp     byte ptr [rcx+29h], 2
0x14005a10d  jb      short loc_14005A157
0x14005a10f  mov     edx, 10h
0x14005a114  jmp     short loc_14005A144
0x14005a116  cmp     dword ptr [rbx+8], 200h
0x14005a11d  jz      short loc_14005A15C
0x14005a11f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a126  lea     rax, WPP_GLOBAL_Control
0x14005a12d  cmp     rcx, rax
0x14005a130  jz      short loc_14005A157
0x14005a132  mov     eax, [rcx+2Ch]
0x14005a135  test    al, 40h
0x14005a137  jz      short loc_14005A157
0x14005a139  cmp     byte ptr [rcx+29h], 2
0x14005a13d  jb      short loc_14005A157
0x14005a13f  mov     edx, 11h
0x14005a144  mov     rcx, [rcx+18h]
0x14005a148  lea     r8, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids
0x14005a14f  mov     r9d, r14d
0x14005a152  call    WPP_SF_d
0x14005a157  mov     eax, r14d
0x14005a15a  jmp     short loc_14005A161
0x14005a15c  mov     [rdi], rax
0x14005a15f  xor     eax, eax
0x14005a161  add     rsp, 38h
0x14005a165  pop     r15
0x14005a167  pop     r14
0x14005a169  pop     rdi
0x14005a16a  pop     rsi
0x14005a16b  pop     rbp
0x14005a16c  pop     rbx
0x14005a16d  retn
```
