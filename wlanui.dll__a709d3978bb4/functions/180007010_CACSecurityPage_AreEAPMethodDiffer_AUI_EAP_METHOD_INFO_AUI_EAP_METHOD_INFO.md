# CACSecurityPage::AreEAPMethodDiffer(_AUI_EAP_METHOD_INFO *,_AUI_EAP_METHOD_INFO *)

- ea: `0x180007010`
- end: `0x18000706a`
- name: `?AreEAPMethodDiffer@CACSecurityPage@@AEAAHPEAU_AUI_EAP_METHOD_INFO@@0@Z`
- size: `90`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this, struct _AUI_EAP_METHOD_INFO *, struct _AUI_EAP_METHOD_INFO *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009380`
- `0x18000c824`

## callees

- `0x180007010`
- `0x18001befe`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::AreEAPMethodDiffer(
        CACSecurityPage *this,
        struct _AUI_EAP_METHOD_INFO *a2,
        const void **a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // ecx
  _QWORD *v7; // rdx
  _QWORD *v8; // r8

  v5 = 1;
  if ( a2 )
  {
    if ( a3 )
    {
      v6 = *((_DWORD *)a2 + 2);
      if ( v6 == *((_DWORD *)a3 + 2) )
      {
        v7 = *(_QWORD **)a2;
        v8 = *a3;
        if ( *v7 == *v8 && v7[1] == v8[1] )
          return memcmp_0(*((const void **)a2 + 2), a3[2], v6) != 0;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180007010  push    rbx
0x180007012  sub     rsp, 20h
0x180007016  mov     r9, r8
0x180007019  mov     r10, rdx
0x18000701c  mov     ebx, 1
0x180007021  test    rdx, rdx
0x180007024  jz      short loc_180007062
0x180007026  test    r8, r8
0x180007029  jz      short loc_180007062
0x18000702b  mov     ecx, [rdx+8]
0x18000702e  cmp     ecx, [r8+8]
0x180007032  jnz     short loc_180007062
0x180007034  mov     rdx, [rdx]
0x180007037  mov     r8, [r8]
0x18000703a  mov     rax, [rdx]
0x18000703d  cmp     rax, [r8]
0x180007040  jnz     short loc_180007062
0x180007042  mov     rax, [rdx+8]
0x180007046  cmp     rax, [r8+8]
0x18000704a  jnz     short loc_180007062
0x18000704c  mov     rdx, [r9+10h]; Buf2
0x180007050  mov     r8d, ecx; Size
0x180007053  mov     rcx, [r10+10h]; Buf1
0x180007057  call    memcmp_0
0x18000705c  neg     eax
0x18000705e  sbb     ecx, ecx
0x180007060  and     ebx, ecx
0x180007062  mov     eax, ebx
0x180007064  add     rsp, 20h
0x180007068  pop     rbx
0x180007069  retn
```
