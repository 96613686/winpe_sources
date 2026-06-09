# UdfVmcbCheckForNoOpRead

- ea: `0x140039ff4`
- end: `0x14003a0c1`
- name: `UdfVmcbCheckForNoOpRead`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400300ec`

## callees

- `0x14000e438`
- `0x140039ff4`
- `0x14003d810`

## pseudocode

```c
__int64 __fastcall UdfVmcbCheckForNoOpRead(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  int v8; // eax
  signed __int32 v9; // esi
  __int64 result; // rax
  __int64 i; // rcx
  int v12; // [rsp+70h] [rbp+18h] BYREF

  v12 = 0;
  v8 = UdfLookupPsnOfExtent(
         a1,
         a2,
         *(_WORD *)((-(__int64)(a3 != 0) & 0xFFFFFFFFFFFFFFFCuLL) + *(_QWORD *)(a2 + 16) + 88),
         a4,
         *(_DWORD *)(a2 + 68));
  v9 = v8 & ~*(_DWORD *)(a2 + 1276);
  result = (unsigned int)(v8 - v9);
  if ( (unsigned int)result <= a4 )
  {
    UdfChangeOrVerifyBitmapRun(a1, a3, a4 - result, *(_DWORD *)(a2 + 1272), 1, 1, (__int64)&v12);
    result = *(unsigned int *)(a2 + 1272);
    if ( v12 == (_DWORD)result )
    {
      for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
      {
        result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(a2 + 4 * i + 1384), v9, -1);
        if ( (_DWORD)result == -1 )
        {
          *(_DWORD *)(a1 + 28) |= 0x80000u;
          return result;
        }
        if ( *(_DWORD *)(a2 + 4 * i + 1384) == v9 )
          return result;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140039ff4  mov     [rsp+arg_0], rbx
0x140039ff9  mov     [rsp+arg_8], rbp
0x140039ffe  push    rsi
0x140039fff  push    rdi
0x14003a000  push    r14
0x14003a002  sub     rsp, 40h
0x14003a006  mov     eax, r8d
0x14003a009  mov     [rsp+58h+arg_10], 0
0x14003a011  neg     eax
0x14003a013  mov     r14d, r8d
0x14003a016  mov     r8, [rdx+10h]
0x14003a01a  mov     ebp, r9d
0x14003a01d  mov     eax, [rdx+44h]
0x14003a020  sbb     r10, r10
0x14003a023  and     r10, 0FFFFFFFFFFFFFFFCh
0x14003a027  mov     [rsp+58h+var_38], eax
0x14003a02b  mov     rbx, rdx
0x14003a02e  mov     rdi, rcx
0x14003a031  movzx   r8d, word ptr [r10+r8+58h]
0x14003a037  call    UdfLookupPsnOfExtent
0x14003a03c  mov     esi, [rbx+4FCh]
0x14003a042  not     esi
0x14003a044  and     esi, eax
0x14003a046  sub     eax, esi
0x14003a048  cmp     eax, ebp
0x14003a04a  ja      short loc_14003A0AD
0x14003a04c  mov     r9d, [rbx+4F8h]
0x14003a053  sub     ebp, eax
0x14003a055  lea     rax, [rsp+58h+arg_10]
0x14003a05a  mov     r8d, ebp
0x14003a05d  mov     [rsp+58h+var_28], rax
0x14003a062  mov     edx, r14d
0x14003a065  mov     [rsp+58h+var_30], 1
0x14003a06a  mov     rcx, rdi
0x14003a06d  mov     byte ptr [rsp+58h+var_38], 1
0x14003a072  call    UdfChangeOrVerifyBitmapRun
0x14003a077  mov     eax, [rbx+4F8h]
0x14003a07d  cmp     [rsp+58h+arg_10], eax
0x14003a081  jnz     short loc_14003A0AD
0x14003a083  xor     ecx, ecx
0x14003a085  cmp     ecx, 4
0x14003a088  jnb     short loc_14003A0AD
0x14003a08a  or      eax, 0FFFFFFFFh
0x14003a08d  lock cmpxchg [rbx+rcx*4+568h], esi
0x14003a096  cmp     eax, 0FFFFFFFFh
0x14003a099  jz      short loc_14003A0A8
0x14003a09b  cmp     [rbx+rcx*4+568h], esi
0x14003a0a2  jz      short loc_14003A0AD
0x14003a0a4  inc     ecx
0x14003a0a6  jmp     short loc_14003A085
0x14003a0a8  bts     dword ptr [rdi+1Ch], 13h
0x14003a0ad  mov     rbx, [rsp+58h+arg_0]
0x14003a0b2  mov     rbp, [rsp+58h+arg_8]
0x14003a0b7  add     rsp, 40h
0x14003a0bb  pop     r14
0x14003a0bd  pop     rdi
0x14003a0be  pop     rsi
0x14003a0bf  retn
```
