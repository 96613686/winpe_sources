# SrSmapipRemoveMemberSetReturn

- ea: `0x18000d1d0`
- end: `0x18000d2d0`
- name: `SrSmapipRemoveMemberSetReturn`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000bf54`

## callees

- `0x1800014e0`
- `0x180001e38`
- `0x180005cec`
- `0x1800067cc`
- `0x1800067fc`
- `0x180009028`
- `0x18000d1d0`

## pseudocode

```c
__int64 __fastcall SrSmapipRemoveMemberSetReturn(MI_Result a1, __int64 a2)
{
  MI_Result v4; // ebx
  MI_Instance *v5; // rcx
  MI_Instance instance; // [rsp+20h] [rbp-98h] BYREF
  MI_Result v8; // [rsp+60h] [rbp-58h]
  char v9; // [rsp+64h] [rbp-54h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x68u);
  v4 = MI_Context_ConstructParameters(*(MI_Context **)(a2 + 56), &WSP_ReplicationGroup_RemoveMember_rtti, &instance);
  if ( v4 == MI_RESULT_OK )
  {
    v5 = *(MI_Instance **)(a2 + 56);
    v8 = a1;
    v9 = 1;
    v4 = MI_Instance_Destruct(v5);
    if ( v4 == MI_RESULT_OK )
      v4 = a1;
    MI_Instance_Destruct(&instance);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_97259de4980931de249eb41af43a46d5_Traceguids, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d1d0  mov     [rsp+arg_10], rbx
0x18000d1d5  push    rbp
0x18000d1d6  push    rsi
0x18000d1d7  push    rdi
0x18000d1d8  sub     rsp, 0A0h
0x18000d1df  mov     rax, cs:__security_cookie
0x18000d1e6  xor     rax, rsp
0x18000d1e9  mov     [rsp+0B8h+var_28], rax
0x18000d1f1  mov     rdi, rdx
0x18000d1f4  mov     esi, ecx
0x18000d1f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1fd  lea     rbp, WPP_GLOBAL_Control
0x18000d204  cmp     rcx, rbp
0x18000d207  jz      short loc_18000D224
0x18000d209  test    byte ptr [rcx+1Ch], 4
0x18000d20d  jz      short loc_18000D224
0x18000d20f  mov     rcx, [rcx+10h]
0x18000d213  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000d21a  mov     edx, 4Bh ; 'K'
0x18000d21f  call    WPP_SF_
0x18000d224  xor     edx, edx; Val
0x18000d226  mov     [rsp+0B8h+instance.ft], 0
0x18000d22f  lea     rcx, [rsp+0B8h+instance.classDecl]; void *
0x18000d234  lea     r8d, [rdx+68h]; Size
0x18000d238  call    memset_0
0x18000d23d  mov     rcx, [rdi+38h]; context
0x18000d241  lea     r8, [rsp+0B8h+instance]; instance
0x18000d246  lea     rdx, WSP_ReplicationGroup_RemoveMember_rtti; methodDecl
0x18000d24d  call    MI_Context_ConstructParameters
0x18000d252  mov     ebx, eax
0x18000d254  test    eax, eax
0x18000d256  jnz     short loc_18000D280
0x18000d258  mov     rcx, [rdi+38h]; self
0x18000d25c  lea     rdx, [rsp+0B8h+instance]
0x18000d261  mov     [rsp+0B8h+var_58], esi
0x18000d265  mov     [rsp+0B8h+var_54], 1
0x18000d26a  call    MI_Instance_Destruct
0x18000d26f  test    eax, eax
0x18000d271  lea     rcx, [rsp+0B8h+instance]; self
0x18000d276  mov     ebx, eax
0x18000d278  cmovz   ebx, esi
0x18000d27b  call    MI_Instance_Destruct
0x18000d280  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d287  cmp     rcx, rbp
0x18000d28a  jz      short loc_18000D2AA
0x18000d28c  test    byte ptr [rcx+1Ch], 1
0x18000d290  jz      short loc_18000D2AA
0x18000d292  mov     rcx, [rcx+10h]
0x18000d296  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000d29d  mov     edx, 4Ch ; 'L'
0x18000d2a2  mov     r9d, ebx
0x18000d2a5  call    WPP_SF_d
0x18000d2aa  mov     eax, ebx
0x18000d2ac  mov     rcx, [rsp+0B8h+var_28]
0x18000d2b4  xor     rcx, rsp; StackCookie
0x18000d2b7  call    __security_check_cookie
0x18000d2bc  mov     rbx, [rsp+0B8h+arg_10]
0x18000d2c4  add     rsp, 0A0h
0x18000d2cb  pop     rdi
0x18000d2cc  pop     rsi
0x18000d2cd  pop     rbp
0x18000d2ce  retn
```
