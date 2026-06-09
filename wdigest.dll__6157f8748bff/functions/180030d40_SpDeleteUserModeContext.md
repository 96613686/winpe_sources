# SpDeleteUserModeContext

- ea: `0x180030d40`
- end: `0x180030e38`
- name: `SpDeleteUserModeContext`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800185b8`
- `0x1800192a8`
- `0x18001a394`
- `0x18002c498`
- `0x18002c6dc`
- `0x180030d40`

## pseudocode

```c
__int64 __fastcall SpDeleteUserModeContext(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  int v7; // eax
  HLOCAL hMem; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, a1);
  hMem = 0;
  LOBYTE(a2) = 1;
  if ( (int)UserCtxtHandlerHandleToContext(a1, a2, 0, &hMem) >= 0 )
  {
    v7 = UserCtxtHandlerRelease(hMem);
    v3 = v7;
    if ( v7 >= 0 )
    {
LABEL_13:
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_14;
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v5 = 18;
    v6 = (unsigned int)v7;
LABEL_12:
    WPP_SF_d(v4[2], v5, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v6);
    goto LABEL_13;
  }
  v3 = 0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v5 = 17;
    v6 = 0;
    goto LABEL_12;
  }
LABEL_14:
  if ( v4 != &WPP_GLOBAL_Control && *((char *)v4 + 28) < 0 )
    WPP_SF_qD(v4[2], 19, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, a1, v3);
  return v3;
}

```

## disassembly

```asm
0x180030d40  mov     [rsp+arg_0], rbx
0x180030d45  mov     [rsp+arg_10], rsi
0x180030d4a  push    rdi
0x180030d4b  sub     rsp, 30h
0x180030d4f  mov     rdi, rcx
0x180030d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d59  lea     rsi, WPP_GLOBAL_Control
0x180030d60  cmp     rcx, rsi
0x180030d63  jz      short loc_180030D83
0x180030d65  test    byte ptr [rcx+1Ch], 80h
0x180030d69  jz      short loc_180030D83
0x180030d6b  mov     rcx, [rcx+10h]
0x180030d6f  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030d76  mov     edx, 10h
0x180030d7b  mov     r9, rdi
0x180030d7e  call    WPP_SF_q
0x180030d83  lea     r9, [rsp+38h+hMem]
0x180030d88  mov     [rsp+38h+hMem], 0
0x180030d91  xor     r8d, r8d
0x180030d94  mov     dl, 1
0x180030d96  mov     rcx, rdi
0x180030d99  call    UserCtxtHandlerHandleToContext
0x180030d9e  test    eax, eax
0x180030da0  jns     short loc_180030DBE
0x180030da2  xor     ebx, ebx
0x180030da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180030dab  cmp     rcx, rsi
0x180030dae  jz      short loc_180030E26
0x180030db0  test    byte ptr [rcx+1Ch], 2
0x180030db4  jz      short loc_180030DFF
0x180030db6  lea     edx, [rbx+11h]
0x180030db9  xor     r9d, r9d
0x180030dbc  jmp     short loc_180030DE8
0x180030dbe  mov     rcx, [rsp+38h+hMem]; hMem
0x180030dc3  call    UserCtxtHandlerRelease
0x180030dc8  mov     ebx, eax
0x180030dca  test    eax, eax
0x180030dcc  jns     short loc_180030DF8
0x180030dce  mov     rcx, cs:WPP_GLOBAL_Control
0x180030dd5  cmp     rcx, rsi
0x180030dd8  jz      short loc_180030E26
0x180030dda  test    byte ptr [rcx+1Ch], 1
0x180030dde  jz      short loc_180030DFF
0x180030de0  mov     edx, 12h
0x180030de5  mov     r9d, eax
0x180030de8  mov     rcx, [rcx+10h]
0x180030dec  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030df3  call    WPP_SF_d
0x180030df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180030dff  cmp     rcx, rsi
0x180030e02  jz      short loc_180030E26
0x180030e04  test    byte ptr [rcx+1Ch], 80h
0x180030e08  jz      short loc_180030E26
0x180030e0a  mov     rcx, [rcx+10h]
0x180030e0e  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030e15  mov     edx, 13h
0x180030e1a  mov     [rsp+38h+var_18], ebx
0x180030e1e  mov     r9, rdi
0x180030e21  call    WPP_SF_qD
0x180030e26  mov     rsi, [rsp+38h+arg_10]
0x180030e2b  mov     eax, ebx
0x180030e2d  mov     rbx, [rsp+38h+arg_0]
0x180030e32  add     rsp, 30h
0x180030e36  pop     rdi
0x180030e37  retn
```
