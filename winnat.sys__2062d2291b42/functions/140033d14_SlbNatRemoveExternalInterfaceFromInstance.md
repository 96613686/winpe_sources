# SlbNatRemoveExternalInterfaceFromInstance

- ea: `0x140033d14`
- end: `0x140033db9`
- name: `SlbNatRemoveExternalInterfaceFromInstance`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140033dc0`

## callees

- `0x14002e060`
- `0x14002e108`
- `0x140032228`
- `0x140033d14`

## pseudocode

```c
void __fastcall SlbNatRemoveExternalInterfaceFromInstance(__int64 a1, int a2, __int64 a3)
{
  __int64 *v5; // rbx
  __int64 *v6; // r14
  __int64 *v7; // rax
  __int64 **v8; // rcx

  if ( (xmmword_1400272E0 & 2) != 0 )
    WPP_SF_S(a1, 39, a3, a1 + 80);
  v5 = *(__int64 **)(a1 + 24);
  if ( v5 != (__int64 *)(a1 + 24) )
  {
    do
    {
      v6 = (__int64 *)*v5;
      if ( (xmmword_1400272E0 & 2) != 0 )
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
0x140033d14  push    rbx
0x140033d16  push    rbp
0x140033d17  push    rsi
0x140033d18  push    rdi
0x140033d19  push    r14
0x140033d1b  push    r15
0x140033d1d  sub     rsp, 38h
0x140033d21  mov     r15d, edx
0x140033d24  mov     rbp, rcx
0x140033d27  test    byte ptr cs:xmmword_1400272E0, 2
0x140033d2e  jz      short loc_140033D3E
0x140033d30  lea     r9, [rcx+50h]
0x140033d34  mov     edx, 27h ; '''
0x140033d39  call    WPP_SF_S
0x140033d3e  lea     rsi, [rbp+18h]
0x140033d42  mov     rbx, [rsi]
0x140033d45  cmp     rbx, rsi
0x140033d48  jz      short loc_140033DA4
0x140033d4a  mov     r14, [rbx]
0x140033d4d  test    byte ptr cs:xmmword_1400272E0, 2
0x140033d54  jz      short loc_140033D72
0x140033d56  mov     eax, [rbx+38h]
0x140033d59  mov     edx, 28h ; '('
0x140033d5e  mov     r9d, [rbx+58h]
0x140033d62  mov     [rsp+68h+var_40], eax
0x140033d66  mov     eax, [rbx+30h]
0x140033d69  mov     [rsp+68h+var_48], eax
0x140033d6d  call    WPP_SF_ddD
0x140033d72  cmp     [rbx+58h], r15d
0x140033d76  jnz     short loc_140033D9C
0x140033d78  mov     rax, [rbx]
0x140033d7b  cmp     [rax+8], rbx
0x140033d7f  jnz     short loc_140033DB2
0x140033d81  mov     rcx, [rbx+8]
0x140033d85  cmp     [rcx], rbx
0x140033d88  jnz     short loc_140033DB2
0x140033d8a  mov     [rcx], rax
0x140033d8d  mov     rdx, rbp
0x140033d90  mov     [rax+8], rcx
0x140033d94  mov     rcx, rbx; P
0x140033d97  call    SlbNatDeleteExternalAddress
0x140033d9c  mov     rbx, r14
0x140033d9f  cmp     r14, rsi
0x140033da2  jnz     short loc_140033D4A
0x140033da4  add     rsp, 38h
0x140033da8  pop     r15
0x140033daa  pop     r14
0x140033dac  pop     rdi
0x140033dad  pop     rsi
0x140033dae  pop     rbp
0x140033daf  pop     rbx
0x140033db0  retn
0x140033db2  mov     ecx, 3
0x140033db7  int     29h; Win8: RtlFailFast(ecx)
```
