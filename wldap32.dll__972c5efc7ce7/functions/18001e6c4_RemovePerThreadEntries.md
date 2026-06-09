# RemovePerThreadEntries

- ea: `0x18001e6c4`
- end: `0x18001e79c`
- name: `RemovePerThreadEntries`
- size: `216`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001e2c0`
- `0x180025cc8`

## callees

- `0x18000b440`
- `0x18001e6c4`
- `0x180029560`
- `0x180032bd8`

## string_xrefs

- `0x18001e74c`: `Removing all per thread data entries that are marked as deleted\n`

## pseudocode

```c
void RemovePerThreadEntries()
{
  __int64 *v0; // rdi
  __int64 v1; // rcx
  __int64 *v2; // rsi
  __int64 *v3; // rax
  __int64 *v4; // rax
  _QWORD *v5; // rbx
  _QWORD *v6; // rcx
  CHAR *v7; // rcx
  _QWORD *v8; // rbp
  _QWORD *v9; // rbx

  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x200000) != 0 )
    LDAPClientTraceEvent(0x200000, (__int64)"Removing all per thread data entries that are marked as deleted\n");
  v0 = (__int64 *)GlobalPerThreadList;
  while ( v0 != &GlobalPerThreadList )
  {
    v1 = *v0;
    v2 = v0;
    v3 = v0;
    v0 = (__int64 *)*v0;
    if ( *((_BYTE *)v2 + 40) == 1 )
    {
      v4 = (__int64 *)v3[1];
      *v4 = v1;
      *(_QWORD *)(v1 + 8) = v4;
      v5 = (_QWORD *)v2[3];
      if ( v5 )
      {
        do
        {
          v7 = (CHAR *)v5[3];
          v8 = (_QWORD *)*v5;
          if ( v7 )
            ldap_memfree(v7);
          ldapFree(v5, 1920091468);
          v5 = v8;
        }
        while ( v8 );
      }
      v6 = (_QWORD *)v2[4];
      if ( v6 )
      {
        do
        {
          v9 = (_QWORD *)*v6;
          ldapFree(v6, 1920221516);
          v6 = v9;
        }
        while ( v9 );
      }
      ldapFree(v2, 1817471076);
    }
  }
}

```

## disassembly

```asm
0x18001e6c4  push    rbx
0x18001e6c6  push    rbp
0x18001e6c7  push    rsi
0x18001e6c8  push    rdi
0x18001e6c9  push    r14
0x18001e6cb  sub     rsp, 20h
0x18001e6cf  cmp     cs:g_fTracingOn, 0
0x18001e6d6  jnz     short loc_18001E735
0x18001e6d8  mov     rdi, cs:GlobalPerThreadList
0x18001e6df  lea     r14, GlobalPerThreadList
0x18001e6e6  cmp     rdi, r14
0x18001e6e9  jnz     short loc_18001E6F7
0x18001e6eb  add     rsp, 20h
0x18001e6ef  pop     r14
0x18001e6f1  pop     rdi
0x18001e6f2  pop     rsi
0x18001e6f3  pop     rbp
0x18001e6f4  pop     rbx
0x18001e6f5  retn
0x18001e6f7  mov     rcx, [rdi]
0x18001e6fa  mov     rsi, rdi
0x18001e6fd  mov     rax, rdi
0x18001e700  mov     rdi, rcx
0x18001e703  cmp     byte ptr [rsi+28h], 1
0x18001e707  jnz     short loc_18001E6E6
0x18001e709  mov     rax, [rax+8]
0x18001e70d  mov     [rax], rcx
0x18001e710  mov     [rcx+8], rax
0x18001e714  mov     rbx, [rsi+18h]
0x18001e718  test    rbx, rbx
0x18001e71b  jnz     short loc_18001E75D
0x18001e71d  mov     rcx, [rsi+20h]
0x18001e721  test    rcx, rcx
0x18001e724  jnz     short loc_18001E785
0x18001e726  mov     edx, 6C546864h
0x18001e72b  mov     rcx, rsi
0x18001e72e  call    ldapFree
0x18001e733  jmp     short loc_18001E6E6
0x18001e735  cmp     cs:g_fProviderEnabled, 0
0x18001e73c  jz      short loc_18001E6D8
0x18001e73e  mov     ecx, 200000h
0x18001e743  test    cs:g_ulTraceFlags, rcx
0x18001e74a  jz      short loc_18001E6D8
0x18001e74c  lea     rdx, aRemovingAllPer; "Removing all per thread data entries th"...
0x18001e753  call    LDAPClientTraceEvent
0x18001e758  jmp     loc_18001E6D8
0x18001e75d  mov     rcx, [rbx+18h]; Block
0x18001e761  mov     rbp, [rbx]
0x18001e764  test    rcx, rcx
0x18001e767  jz      short loc_18001E76E
0x18001e769  call    ldap_memfree
0x18001e76e  mov     edx, 7272454Ch
0x18001e773  mov     rcx, rbx
0x18001e776  call    ldapFree
0x18001e77b  mov     rbx, rbp
0x18001e77e  test    rbp, rbp
0x18001e781  jnz     short loc_18001E75D
0x18001e783  jmp     short loc_18001E71D
0x18001e785  mov     rbx, [rcx]
0x18001e788  mov     edx, 7274414Ch
0x18001e78d  call    ldapFree
0x18001e792  mov     rcx, rbx
0x18001e795  test    rbx, rbx
0x18001e798  jnz     short loc_18001E785
0x18001e79a  jmp     short loc_18001E726
```
