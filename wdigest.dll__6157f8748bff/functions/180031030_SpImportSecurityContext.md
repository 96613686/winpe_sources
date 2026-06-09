# SpImportSecurityContext

- ea: `0x180031030`
- end: `0x18003106f`
- name: `SpImportSecurityContext`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800192a8`
- `0x180031030`

## pseudocode

```c
__int64 __fastcall SpImportSecurityContext(__int64 a1, __int64 a2, __int64 a3)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, a3);
  return 2148074242LL;
}

```

## disassembly

```asm
0x180031030  sub     rsp, 28h
0x180031034  mov     rcx, cs:WPP_GLOBAL_Control
0x18003103b  lea     rax, WPP_GLOBAL_Control
0x180031042  cmp     rcx, rax
0x180031045  jz      short loc_180031065
0x180031047  test    byte ptr [rcx+1Ch], 80h
0x18003104b  jz      short loc_180031065
0x18003104d  mov     rcx, [rcx+10h]
0x180031051  mov     r9, r8
0x180031054  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18003105b  mov     edx, 54h ; 'T'
0x180031060  call    WPP_SF_q
0x180031065  mov     eax, 80090302h
0x18003106a  add     rsp, 28h
0x18003106e  retn
```
