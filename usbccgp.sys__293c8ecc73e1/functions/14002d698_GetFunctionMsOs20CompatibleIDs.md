# GetFunctionMsOs20CompatibleIDs

- ea: `0x14002d698`
- end: `0x14002d742`
- name: `GetFunctionMsOs20CompatibleIDs`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002d610`

## callees

- `0x1400088b4`
- `0x14000ed84`
- `0x14002d698`
- `0x14002d748`

## pseudocode

```c
char __fastcall GetFunctionMsOs20CompatibleIDs(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  unsigned __int16 *FunctionMsOs20FunctionSubset; // rax
  __int64 v7; // r10
  bool v8; // zf
  char *v9; // r10
  char *v10; // rbx
  int v11; // edx
  char *v13; // [rsp+78h] [rbp+20h] BYREF

  FunctionMsOs20FunctionSubset = (unsigned __int16 *)GetFunctionMsOs20FunctionSubset();
  if ( FunctionMsOs20FunctionSubset )
  {
    v7 = *FunctionMsOs20FunctionSubset;
    v8 = (unsigned __int16 *)((char *)FunctionMsOs20FunctionSubset + v7) == 0;
    v9 = (char *)FunctionMsOs20FunctionSubset + v7;
    v13 = v9;
    if ( !v8 )
    {
      v10 = (char *)FunctionMsOs20FunctionSubset + FunctionMsOs20FunctionSubset[3];
      while ( 1 )
      {
        if ( *((_WORD *)v9 + 1) == 3 )
        {
          *a2 = v9 + 4;
          *a3 = v9 + 12;
          return 1;
        }
        if ( !(unsigned __int8)GetNextMsOs20Descriptor(v10, &v13) )
          break;
        v9 = v13;
        if ( !v13 )
          return 0;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 392), v11, 8, 73, (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002d698  push    rbx
0x14002d69a  push    rsi
0x14002d69b  push    rdi
0x14002d69c  push    r14
0x14002d69e  sub     rsp, 38h
0x14002d6a2  mov     rsi, r8
0x14002d6a5  mov     r14, rdx
0x14002d6a8  mov     rdi, rcx
0x14002d6ab  call    GetFunctionMsOs20FunctionSubset
0x14002d6b0  test    rax, rax
0x14002d6b3  jz      short loc_14002D6ED
0x14002d6b5  movzx   r10d, word ptr [rax]
0x14002d6b9  add     r10, rax
0x14002d6bc  mov     [rsp+58h+arg_18], r10
0x14002d6c1  jz      short loc_14002D6ED
0x14002d6c3  movzx   ebx, word ptr [rax+6]
0x14002d6c7  add     rbx, rax
0x14002d6ca  cmp     word ptr [r10+2], 3
0x14002d6d0  jz      short loc_14002D730
0x14002d6d2  lea     rdx, [rsp+58h+arg_18]
0x14002d6d7  mov     rcx, rbx
0x14002d6da  call    GetNextMsOs20Descriptor
0x14002d6df  test    al, al
0x14002d6e1  jz      short loc_14002D6FA
0x14002d6e3  mov     r10, [rsp+58h+arg_18]
0x14002d6e8  test    r10, r10
0x14002d6eb  jnz     short loc_14002D6CA
0x14002d6ed  xor     al, al
0x14002d6ef  add     rsp, 38h
0x14002d6f3  pop     r14
0x14002d6f5  pop     rdi
0x14002d6f6  pop     rsi
0x14002d6f7  pop     rbx
0x14002d6f8  retn
0x14002d6fa  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002d701  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d708  jz      short loc_14002D6ED
0x14002d70a  mov     rcx, [rdi+188h]
0x14002d711  lea     rax, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x14002d718  mov     r9d, 49h ; 'I'
0x14002d71e  mov     [rsp+58h+var_38], rax
0x14002d723  mov     dl, 2
0x14002d725  lea     r8d, [r9-41h]
0x14002d729  call    WPP_RECORDER_SF_
0x14002d72e  jmp     short loc_14002D6ED
0x14002d730  lea     rax, [r10+4]
0x14002d734  mov     [r14], rax
0x14002d737  lea     rax, [r10+0Ch]
0x14002d73b  mov     [rsi], rax
0x14002d73e  mov     al, 1
0x14002d740  jmp     short loc_14002D6EF
```
