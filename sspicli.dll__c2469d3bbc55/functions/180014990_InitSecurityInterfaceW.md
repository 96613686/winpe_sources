# InitSecurityInterfaceW

- ea: `0x180014990`
- end: `0x1800149d5`
- name: `InitSecurityInterfaceW`
- size: `69`
- prototype: `PSecurityFunctionTableW __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014990`
- `0x18001b500`

## pseudocode

```c
PSecurityFunctionTableW __stdcall InitSecurityInterfaceW()
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids, &SecTableW);
  return &SecTableW;
}

```

## disassembly

```asm
0x180014990  sub     rsp, 28h
0x180014994  mov     rcx, cs:WPP_GLOBAL_Control
0x18001499b  lea     rax, WPP_GLOBAL_Control
0x1800149a2  cmp     rcx, rax
0x1800149a5  jz      short loc_1800149C9
0x1800149a7  test    byte ptr [rcx+1Ch], 4
0x1800149ab  jz      short loc_1800149C9
0x1800149ad  mov     rcx, [rcx+10h]
0x1800149b1  lea     r9, ?SecTableW@@3U_SECURITY_FUNCTION_TABLE_W@@A; _SECURITY_FUNCTION_TABLE_W SecTableW
0x1800149b8  mov     edx, 23h ; '#'
0x1800149bd  lea     r8, WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids
0x1800149c4  call    WPP_SF_q
0x1800149c9  lea     rax, ?SecTableW@@3U_SECURITY_FUNCTION_TABLE_W@@A; _SECURITY_FUNCTION_TABLE_W SecTableW
0x1800149d0  add     rsp, 28h
0x1800149d4  retn
```
