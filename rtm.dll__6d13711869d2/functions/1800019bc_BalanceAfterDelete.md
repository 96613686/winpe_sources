# BalanceAfterDelete

- ea: `0x1800019bc`
- end: `0x180001a78`
- name: `BalanceAfterDelete`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001de0`

## callees

- `0x1800019bc`
- `0x180001f38`
- `0x1800026a0`

## pseudocode

```c
void __fastcall BalanceAfterDelete(__int64 a1, __int64 a2, unsigned int a3)
{
  int v4; // r8d
  __int64 v5; // rax
  bool v6; // zf
  __int64 v7; // rax
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  if ( *(_DWORD *)(a2 + 40) )
  {
    do
    {
      if ( *(_DWORD *)(a2 + 40) == a3 )
      {
        *(_DWORD *)(a2 + 40) = 0;
      }
      else
      {
        v4 = *(_DWORD *)(*(_QWORD *)(a2 + 8 * (3LL - (int)a3)) + 40LL);
        if ( v4 == -a3 )
        {
          SingleRotate(a1, a2, a3, &v8);
        }
        else
        {
          if ( v4 != a3 )
          {
            SingleRotate(a1, a2, a3, &v8);
            v7 = v8;
            *(_DWORD *)(v8 + 40) = a3;
            *(_DWORD *)(*(_QWORD *)(v7 + 8LL * (int)a3 + 24) + 40LL) = -a3;
            return;
          }
          DoubleRotate(a1, a2, a3, &v8);
        }
        a2 = v8;
      }
      v5 = *(_QWORD *)(a2 + 8);
      if ( !v5 )
        return;
      v8 = *(_QWORD *)(a2 + 8);
      v6 = *(_QWORD *)(v5 + 16) == a2;
      a3 = 1;
      a2 = v5;
      if ( v6 )
        a3 = -1;
    }
    while ( *(_DWORD *)(v5 + 40) );
  }
  *(_DWORD *)(a2 + 40) = -a3;
}

```

## disassembly

```asm
0x1800019bc  mov     [rsp+arg_0], rbx
0x1800019c1  mov     [rsp+arg_10], rsi
0x1800019c6  mov     [rsp+arg_8], rdx
0x1800019cb  push    rdi
0x1800019cc  sub     rsp, 20h
0x1800019d0  cmp     dword ptr [rdx+28h], 0
0x1800019d4  mov     ebx, r8d
0x1800019d7  jz      short loc_180001A4C
0x1800019d9  cmp     [rdx+28h], ebx
0x1800019dc  jnz     short loc_1800019E7
0x1800019de  mov     dword ptr [rdx+28h], 0
0x1800019e5  jmp     short loc_180001A24
0x1800019e7  movsxd  rsi, ebx
0x1800019ea  lea     r9, [rsp+28h+arg_8]
0x1800019ef  mov     eax, 3
0x1800019f4  mov     edi, ebx
0x1800019f6  sub     rax, rsi
0x1800019f9  neg     edi
0x1800019fb  mov     rax, [rdx+rax*8]
0x1800019ff  mov     r8d, [rax+28h]
0x180001a03  cmp     r8d, edi
0x180001a06  jnz     short loc_180001A12
0x180001a08  mov     r8d, ebx
0x180001a0b  call    SingleRotate
0x180001a10  jmp     short loc_180001A1F
0x180001a12  cmp     r8d, ebx
0x180001a15  mov     r8d, ebx
0x180001a18  jnz     short loc_180001A61
0x180001a1a  call    DoubleRotate
0x180001a1f  mov     rdx, [rsp+28h+arg_8]
0x180001a24  mov     rax, [rdx+8]
0x180001a28  test    rax, rax
0x180001a2b  jz      short loc_180001A51
0x180001a2d  or      r8d, 0FFFFFFFFh
0x180001a31  mov     [rsp+28h+arg_8], rax
0x180001a36  cmp     [rax+10h], rdx
0x180001a3a  mov     ebx, 1
0x180001a3f  mov     rdx, rax
0x180001a42  cmovz   ebx, r8d
0x180001a46  cmp     dword ptr [rax+28h], 0
0x180001a4a  jnz     short loc_1800019D9
0x180001a4c  neg     ebx
0x180001a4e  mov     [rdx+28h], ebx
0x180001a51  mov     rbx, [rsp+28h+arg_0]
0x180001a56  mov     rsi, [rsp+28h+arg_10]
0x180001a5b  add     rsp, 20h
0x180001a5f  pop     rdi
0x180001a60  retn
0x180001a61  call    SingleRotate
0x180001a66  mov     rax, [rsp+28h+arg_8]
0x180001a6b  mov     [rax+28h], ebx
0x180001a6e  mov     rax, [rax+rsi*8+18h]
0x180001a73  mov     [rax+28h], edi
0x180001a76  jmp     short loc_180001A51
```
