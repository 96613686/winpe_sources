# SlbNatRemoveExternalInterfaceFromInstance

- ea: `0x140032be4`
- end: `0x140032c89`
- name: `SlbNatRemoveExternalInterfaceFromInstance`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140032c90`

## callees

- `0x14002d060`
- `0x14002d108`
- `0x1400310f8`
- `0x140032be4`

## pseudocode

```c
void __fastcall SlbNatRemoveExternalInterfaceFromInstance(__int64 a1, int a2, __int64 a3)
{
  __int64 *v5; // rbx
  __int64 *v6; // r14
  __int64 *v7; // rax
  __int64 **v8; // rcx

  if ( (xmmword_1400262E0 & 2) != 0 )
    WPP_SF_S(a1, 39, a3, a1 + 80);
  v5 = *(__int64 **)(a1 + 24);
  if ( v5 != (__int64 *)(a1 + 24) )
  {
    do
    {
      v6 = (__int64 *)*v5;
      if ( (xmmword_1400262E0 & 2) != 0 )
        WPP_SF_ddD(a1, 40, a3, *((unsigned int *)v5 + 22), *((_DWORD *)v5 + 12), *((_DWORD *)v5 + 14));
      if ( *((_DWORD *)v5 + 22) == a2 )
      {
        v7 = (__int64 *)*v5;
        if ( *(__int64 **)(*v5 + 8) != v5 || (v8 = (__int64 **)v5[1], *v8 != v5) )
          __fastfail(3u);
        *v8 = v7;
        v7[1] = (__int64)v8;
        SlbNatDeleteExternalAddress((char *)v5, a1);
      }
      v5 = v6;
    }
    while ( v6 != (__int64 *)(a1 + 24) );
  }
}

```

## disassembly

```asm
0x140032be4  push    rbx
0x140032be6  push    rbp
0x140032be7  push    rsi
0x140032be8  push    rdi
0x140032be9  push    r14
0x140032beb  push    r15
0x140032bed  sub     rsp, 38h
0x140032bf1  mov     r15d, edx
0x140032bf4  mov     rbp, rcx
0x140032bf7  test    byte ptr cs:xmmword_1400262E0, 2
0x140032bfe  jz      short loc_140032C0E
0x140032c00  lea     r9, [rcx+50h]
0x140032c04  mov     edx, 27h ; '''
0x140032c09  call    WPP_SF_S
0x140032c0e  lea     rsi, [rbp+18h]
0x140032c12  mov     rbx, [rsi]
0x140032c15  cmp     rbx, rsi
0x140032c18  jz      short loc_140032C74
0x140032c1a  mov     r14, [rbx]
0x140032c1d  test    byte ptr cs:xmmword_1400262E0, 2
0x140032c24  jz      short loc_140032C42
0x140032c26  mov     eax, [rbx+38h]
0x140032c29  mov     edx, 28h ; '('
0x140032c2e  mov     r9d, [rbx+58h]
0x140032c32  mov     [rsp+68h+var_40], eax
0x140032c36  mov     eax, [rbx+30h]
0x140032c39  mov     [rsp+68h+var_48], eax
0x140032c3d  call    WPP_SF_ddD
0x140032c42  cmp     [rbx+58h], r15d
0x140032c46  jnz     short loc_140032C6C
0x140032c48  mov     rax, [rbx]
0x140032c4b  cmp     [rax+8], rbx
0x140032c4f  jnz     short loc_140032C82
0x140032c51  mov     rcx, [rbx+8]
0x140032c55  cmp     [rcx], rbx
0x140032c58  jnz     short loc_140032C82
0x140032c5a  mov     [rcx], rax
0x140032c5d  mov     rdx, rbp
0x140032c60  mov     [rax+8], rcx
0x140032c64  mov     rcx, rbx; P
0x140032c67  call    SlbNatDeleteExternalAddress
0x140032c6c  mov     rbx, r14
0x140032c6f  cmp     r14, rsi
0x140032c72  jnz     short loc_140032C1A
0x140032c74  add     rsp, 38h
0x140032c78  pop     r15
0x140032c7a  pop     r14
0x140032c7c  pop     rdi
0x140032c7d  pop     rsi
0x140032c7e  pop     rbp
0x140032c7f  pop     rbx
0x140032c80  retn
0x140032c82  mov     ecx, 3
0x140032c87  int     29h; Win8: RtlFailFast(ecx)
```
