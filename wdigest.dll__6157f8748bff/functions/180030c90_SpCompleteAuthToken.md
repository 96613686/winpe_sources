# SpCompleteAuthToken

- ea: `0x180030c90`
- end: `0x180030d2b`
- name: `SpCompleteAuthToken`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800192a8`
- `0x18001a394`
- `0x180030c90`
- `0x180032670`

## pseudocode

```c
__int64 __fastcall SpCompleteAuthToken(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  char v7; // [rsp+50h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, a1);
  v4 = SpVerifySignature(a1, a2, 0, &v7);
  v5 = v4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, a1, v4);
  return v5;
}

```

## disassembly

```asm
0x180030c90  mov     [rsp+arg_0], rbx
0x180030c95  mov     [rsp+arg_8], rsi
0x180030c9a  push    rdi
0x180030c9b  sub     rsp, 30h
0x180030c9f  mov     rbx, rdx
0x180030ca2  mov     rdi, rcx
0x180030ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cac  lea     rsi, WPP_GLOBAL_Control
0x180030cb3  cmp     rcx, rsi
0x180030cb6  jz      short loc_180030CD6
0x180030cb8  test    byte ptr [rcx+1Ch], 80h
0x180030cbc  jz      short loc_180030CD6
0x180030cbe  mov     rcx, [rcx+10h]
0x180030cc2  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030cc9  mov     edx, 4Eh ; 'N'
0x180030cce  mov     r9, rdi
0x180030cd1  call    WPP_SF_q
0x180030cd6  lea     r9, [rsp+38h+arg_10]
0x180030cdb  xor     r8d, r8d
0x180030cde  mov     rdx, rbx
0x180030ce1  mov     rcx, rdi
0x180030ce4  call    SpVerifySignature
0x180030ce9  mov     ebx, eax
0x180030ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cf2  cmp     rcx, rsi
0x180030cf5  jz      short loc_180030D19
0x180030cf7  test    byte ptr [rcx+1Ch], 80h
0x180030cfb  jz      short loc_180030D19
0x180030cfd  mov     rcx, [rcx+10h]
0x180030d01  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030d08  mov     edx, 4Fh ; 'O'
0x180030d0d  mov     [rsp+38h+var_18], eax
0x180030d11  mov     r9, rdi
0x180030d14  call    WPP_SF_qD
0x180030d19  mov     rsi, [rsp+38h+arg_8]
0x180030d1e  mov     eax, ebx
0x180030d20  mov     rbx, [rsp+38h+arg_0]
0x180030d25  add     rsp, 30h
0x180030d29  pop     rdi
0x180030d2a  retn
```
