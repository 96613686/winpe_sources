# SrSmapipRemoveMemberSetReturn

- ea: `0x18000d2ac`
- end: `0x18000d3e4`
- name: `SrSmapipRemoveMemberSetReturn`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000bec0`

## callees

- `0x1800014e0`
- `0x180001e08`
- `0x180005cac`
- `0x180006778`
- `0x1800067a0`
- `0x18000d2ac`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall SrSmapipRemoveMemberSetReturn(unsigned int a1, __int64 a2)
{
  _QWORD *v4; // rbx
  unsigned int v5; // edi
  __int64 v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // rcx
  MI_Instance self; // [rsp+20h] [rbp-98h] BYREF
  unsigned int v11; // [rsp+60h] [rbp-58h]
  char v12; // [rsp+64h] [rbp-54h]

  v4 = WPP_GLOBAL_Control;
  v5 = 4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0x68u);
  v6 = *(_QWORD *)(a2 + 56);
  if ( v6 && *(_QWORD *)v6 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, MI_Instance *))(*(_QWORD *)v6 + 32LL))(
           v6,
           &WSP_ReplicationGroup_RemoveMember_rtti,
           &self);
    if ( v7 )
    {
      v5 = v7;
    }
    else
    {
      v8 = *(_QWORD *)(a2 + 56);
      v11 = a1;
      v12 = 1;
      if ( v8 )
      {
        if ( *(_QWORD *)v8 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, MI_Instance *))(*(_QWORD *)v8 + 8LL))(v8, &self);
          if ( !v5 )
            v5 = a1;
        }
      }
      MI_Instance_Destruct(&self);
    }
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
    WPP_SF_d(v4[2], 76, WPP_97259de4980931de249eb41af43a46d5_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18000d2ac  mov     [rsp+arg_10], rbx
0x18000d2b1  mov     [rsp+arg_18], rbp
0x18000d2b6  push    rsi
0x18000d2b7  push    rdi
0x18000d2b8  push    r14
0x18000d2ba  sub     rsp, 0A0h
0x18000d2c1  mov     rax, cs:__security_cookie
0x18000d2c8  xor     rax, rsp
0x18000d2cb  mov     [rsp+0B8h+var_28], rax
0x18000d2d3  mov     rsi, rdx
0x18000d2d6  mov     ebp, ecx
0x18000d2d8  mov     rbx, cs:WPP_GLOBAL_Control
0x18000d2df  lea     r14, WPP_GLOBAL_Control
0x18000d2e6  mov     edi, 4
0x18000d2eb  cmp     rbx, r14
0x18000d2ee  jz      short loc_18000D310
0x18000d2f0  test    [rbx+1Ch], dil
0x18000d2f4  jz      short loc_18000D310
0x18000d2f6  mov     rcx, [rbx+10h]
0x18000d2fa  lea     edx, [rdi+47h]
0x18000d2fd  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000d304  call    WPP_SF_
0x18000d309  mov     rbx, cs:WPP_GLOBAL_Control
0x18000d310  xor     edx, edx; Val
0x18000d312  mov     [rsp+0B8h+self.ft], 0
0x18000d31b  lea     rcx, [rsp+0B8h+self.classDecl]; void *
0x18000d320  lea     r8d, [rdx+68h]; Size
0x18000d324  call    memset_0
0x18000d329  mov     rcx, [rsi+38h]
0x18000d32d  test    rcx, rcx
0x18000d330  jz      short loc_18000D397
0x18000d332  mov     rax, [rcx]
0x18000d335  test    rax, rax
0x18000d338  jz      short loc_18000D397
0x18000d33a  mov     rax, [rax+20h]
0x18000d33e  lea     r8, [rsp+0B8h+self]
0x18000d343  lea     rdx, WSP_ReplicationGroup_RemoveMember_rtti
0x18000d34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d34f  test    eax, eax
0x18000d351  jnz     short loc_18000D38E
0x18000d353  mov     rcx, [rsi+38h]
0x18000d357  mov     [rsp+0B8h+var_58], ebp
0x18000d35b  mov     [rsp+0B8h+var_54], 1
0x18000d360  test    rcx, rcx
0x18000d363  jz      short loc_18000D382
0x18000d365  mov     rax, [rcx]
0x18000d368  test    rax, rax
0x18000d36b  jz      short loc_18000D382
0x18000d36d  mov     rax, [rax+8]
0x18000d371  lea     rdx, [rsp+0B8h+self]
0x18000d376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d37b  test    eax, eax
0x18000d37d  mov     edi, eax
0x18000d37f  cmovz   edi, ebp
0x18000d382  lea     rcx, [rsp+0B8h+self]; self
0x18000d387  call    MI_Instance_Destruct
0x18000d38c  jmp     short loc_18000D390
0x18000d38e  mov     edi, eax
0x18000d390  mov     rbx, cs:WPP_GLOBAL_Control
0x18000d397  cmp     rbx, r14
0x18000d39a  jz      short loc_18000D3BA
0x18000d39c  test    byte ptr [rbx+1Ch], 1
0x18000d3a0  jz      short loc_18000D3BA
0x18000d3a2  mov     rcx, [rbx+10h]
0x18000d3a6  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000d3ad  mov     edx, 4Ch ; 'L'
0x18000d3b2  mov     r9d, edi
0x18000d3b5  call    WPP_SF_d
0x18000d3ba  mov     eax, edi
0x18000d3bc  mov     rcx, [rsp+0B8h+var_28]
0x18000d3c4  xor     rcx, rsp; StackCookie
0x18000d3c7  call    __security_check_cookie
0x18000d3cc  lea     r11, [rsp+0B8h+var_18]
0x18000d3d4  mov     rbx, [r11+30h]
0x18000d3d8  mov     rbp, [r11+38h]
0x18000d3dc  mov     rsp, r11
0x18000d3df  pop     r14
0x18000d3e1  pop     rdi
0x18000d3e2  pop     rsi
0x18000d3e3  retn
```
