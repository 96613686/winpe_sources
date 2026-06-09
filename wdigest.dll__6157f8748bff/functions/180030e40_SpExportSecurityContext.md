# SpExportSecurityContext

- ea: `0x180030e40`
- end: `0x180030e7f`
- name: `SpExportSecurityContext`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800192a8`
- `0x180030e40`

## pseudocode

```c
__int64 __fastcall SpExportSecurityContext(__int64 a1)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, a1);
  return 2148074242LL;
}

```

## disassembly

```asm
0x180030e40  sub     rsp, 28h
0x180030e44  mov     r9, rcx
0x180030e47  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e4e  lea     rax, WPP_GLOBAL_Control
0x180030e55  cmp     rcx, rax
0x180030e58  jz      short loc_180030E75
0x180030e5a  test    byte ptr [rcx+1Ch], 80h
0x180030e5e  jz      short loc_180030E75
0x180030e60  mov     rcx, [rcx+10h]
0x180030e64  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030e6b  mov     edx, 53h ; 'S'
0x180030e70  call    WPP_SF_q
0x180030e75  mov     eax, 80090302h
0x180030e7a  add     rsp, 28h
0x180030e7e  retn
```
