# AuthPortMgrInitPort

- ea: `0x18007c308`
- end: `0x18007c425`
- name: `AuthPortMgrInitPort`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180042ec0`

## callees

- `0x18000431c`
- `0x18000892c`
- `0x180008998`
- `0x18007c308`
- `0x18007c5d0`
- `0x18007c7c4`
- `0x18007cc7c`

## import_xrefs

- `MobileNetworking!CreateReadWriteLock` at `0x18007c3a5`
- `MobileNetworking!CreateReadWriteLock` at `0x18007c3a5`

## pseudocode

```c
__int64 __fastcall AuthPortMgrInitPort(__int64 a1)
{
  unsigned int v1; // ebp
  unsigned int v3; // eax
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  unsigned int v6; // eax

  v1 = *(_DWORD *)(a1 + 132);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids);
  *(_QWORD *)(a1 + 8) = a1;
  *(_QWORD *)a1 = a1;
  v3 = SMInitStateMachine(a1 + 136, a1);
  v4 = v3;
  if ( !v3 )
  {
    SMStartStateMachine(a1 + 136);
    v6 = CreateReadWriteLock(a1 + 24);
    v4 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, v1, v6);
      SMDeInitStateMachine(a1 + 136);
    }
    goto LABEL_13;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, v3);
LABEL_13:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
    WPP_SF_d(v5[2], 22, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18007c308  push    rbx
0x18007c30a  push    rbp
0x18007c30b  push    rsi
0x18007c30c  push    rdi
0x18007c30d  push    r14
0x18007c30f  sub     rsp, 30h
0x18007c313  mov     ebp, [rcx+84h]
0x18007c319  mov     rdi, rcx
0x18007c31c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c323  lea     r14, WPP_GLOBAL_Control
0x18007c32a  cmp     rcx, r14
0x18007c32d  jz      short loc_18007C34A
0x18007c32f  test    byte ptr [rcx+1Ch], 1
0x18007c333  jz      short loc_18007C34A
0x18007c335  mov     rcx, [rcx+10h]
0x18007c339  lea     r8, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007c340  mov     edx, 13h
0x18007c345  call    WPP_SF_
0x18007c34a  lea     rsi, [rdi+88h]
0x18007c351  mov     [rdi+8], rdi
0x18007c355  mov     rcx, rsi
0x18007c358  mov     [rdi], rdi
0x18007c35b  mov     rdx, rdi
0x18007c35e  call    SMInitStateMachine
0x18007c363  mov     ebx, eax
0x18007c365  test    eax, eax
0x18007c367  jz      short loc_18007C399
0x18007c369  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c370  cmp     rcx, r14
0x18007c373  jz      loc_18007C417
0x18007c379  test    byte ptr [rcx+1Ch], 2
0x18007c37d  jz      short loc_18007C3F4
0x18007c37f  mov     rcx, [rcx+10h]
0x18007c383  lea     r8, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007c38a  mov     edx, 14h
0x18007c38f  mov     r9d, eax
0x18007c392  call    WPP_SF_d
0x18007c397  jmp     short loc_18007C3ED
0x18007c399  mov     rcx, rsi
0x18007c39c  call    SMStartStateMachine
0x18007c3a1  lea     rcx, [rdi+18h]
0x18007c3a5  call    cs:__imp_CreateReadWriteLock
0x18007c3ac  nop     dword ptr [rax+rax+00h]
0x18007c3b1  mov     ebx, eax
0x18007c3b3  test    eax, eax
0x18007c3b5  jz      short loc_18007C3ED
0x18007c3b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c3be  cmp     rcx, r14
0x18007c3c1  jz      short loc_18007C3E5
0x18007c3c3  test    byte ptr [rcx+1Ch], 2
0x18007c3c7  jz      short loc_18007C3E5
0x18007c3c9  mov     rcx, [rcx+10h]
0x18007c3cd  lea     r8, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007c3d4  mov     edx, 15h
0x18007c3d9  mov     [rsp+58h+var_38], eax
0x18007c3dd  mov     r9d, ebp
0x18007c3e0  call    WPP_SF_dd
0x18007c3e5  mov     rcx, rsi
0x18007c3e8  call    SMDeInitStateMachine
0x18007c3ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c3f4  cmp     rcx, r14
0x18007c3f7  jz      short loc_18007C417
0x18007c3f9  test    byte ptr [rcx+1Ch], 1
0x18007c3fd  jz      short loc_18007C417
0x18007c3ff  mov     rcx, [rcx+10h]
0x18007c403  lea     r8, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007c40a  mov     edx, 16h
0x18007c40f  mov     r9d, ebx
0x18007c412  call    WPP_SF_d
0x18007c417  mov     eax, ebx
0x18007c419  add     rsp, 30h
0x18007c41d  pop     r14
0x18007c41f  pop     rdi
0x18007c420  pop     rsi
0x18007c421  pop     rbp
0x18007c422  pop     rbx
0x18007c423  retn
```
