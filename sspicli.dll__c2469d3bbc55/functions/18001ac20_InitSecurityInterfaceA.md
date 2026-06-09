# InitSecurityInterfaceA

- ea: `0x18001ac20`
- end: `0x18001ac65`
- name: `InitSecurityInterfaceA`
- size: `69`
- prototype: `PSecurityFunctionTableA __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001ac20`
- `0x18001b500`

## pseudocode

```c
PSecurityFunctionTableA __stdcall InitSecurityInterfaceA()
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids, &SecTableA);
  return &SecTableA;
}

```

## disassembly

```asm
0x18001ac20  sub     rsp, 28h
0x18001ac24  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac2b  lea     rax, WPP_GLOBAL_Control
0x18001ac32  cmp     rcx, rax
0x18001ac35  jz      short loc_18001AC59
0x18001ac37  test    byte ptr [rcx+1Ch], 4
0x18001ac3b  jz      short loc_18001AC59
0x18001ac3d  mov     rcx, [rcx+10h]
0x18001ac41  lea     r9, ?SecTableA@@3U_SECURITY_FUNCTION_TABLE_A@@A; _SECURITY_FUNCTION_TABLE_A SecTableA
0x18001ac48  mov     edx, 22h ; '"'
0x18001ac4d  lea     r8, WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids
0x18001ac54  call    WPP_SF_q
0x18001ac59  lea     rax, ?SecTableA@@3U_SECURITY_FUNCTION_TABLE_A@@A; _SECURITY_FUNCTION_TABLE_A SecTableA
0x18001ac60  add     rsp, 28h
0x18001ac64  retn
```
