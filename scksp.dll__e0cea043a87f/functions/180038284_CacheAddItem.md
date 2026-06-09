# CacheAddItem

- ea: `0x180038284`
- end: `0x180038335`
- name: `CacheAddItem`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180037a4c`

## callees

- `0x18002b140`
- `0x180038284`
- `0x18003852c`
- `0x1800385f0`
- `0x18003c240`

## pseudocode

```c
unsigned int __fastcall CacheAddItem(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v7; // rax
  __int64 v8; // rdx
  _QWORD *v9; // rbx
  unsigned int v11; // eax
  int v12; // edx
  __int64 v13; // rax
  __int64 v14; // rcx
  _OWORD v15[2]; // [rsp+20h] [rbp-48h] BYREF

  v7 = MIDL_user_allocate(0x38u);
  v9 = v7;
  if ( !v7 )
    return 8;
  *(_DWORD *)v7 = *(_DWORD *)a4;
  v7[1] = *(_QWORD *)(a4 + 8);
  v11 = I_CacheHashKeys(a2, v8, (UCHAR *)v15);
  if ( v11 )
    return errcntrctlib::WIN32_FROM_NTSTATUS((errcntrctlib *)v11, v12);
  *(_OWORD *)(v9 + 3) = v15[0];
  *(_OWORD *)(v9 + 5) = v15[1];
  v13 = v15[0] & 0xF;
  v14 = *(_QWORD *)(a1 + 8 * v13);
  if ( v14 )
    v9[2] = v14;
  *(_QWORD *)(a1 + 8 * v13) = v9;
  ++*(_DWORD *)(a1 + 128);
  return 0;
}

```

## disassembly

```asm
0x180038284  mov     [rsp+arg_10], rbx
0x180038289  push    rbp
0x18003828a  push    rsi
0x18003828b  push    rdi
0x18003828c  sub     rsp, 50h
0x180038290  mov     rax, cs:__security_cookie
0x180038297  xor     rax, rsp
0x18003829a  mov     [rsp+68h+var_28], rax
0x18003829f  mov     rdi, rcx
0x1800382a2  mov     rsi, r9
0x1800382a5  mov     ecx, 38h ; '8'; size
0x1800382aa  mov     rbp, rdx
0x1800382ad  call    MIDL_user_allocate
0x1800382b2  mov     rbx, rax
0x1800382b5  test    rax, rax
0x1800382b8  jnz     short loc_1800382BF
0x1800382ba  lea     eax, [rbx+8]
0x1800382bd  jmp     short loc_180038318
0x1800382bf  mov     eax, [rsi]
0x1800382c1  lea     r8, [rsp+68h+var_48]
0x1800382c6  mov     [rbx], eax
0x1800382c8  mov     rcx, rbp
0x1800382cb  mov     rax, [rsi+8]
0x1800382cf  mov     [rbx+8], rax
0x1800382d3  call    I_CacheHashKeys
0x1800382d8  test    eax, eax
0x1800382da  jz      short loc_1800382E5
0x1800382dc  mov     ecx, eax; this
0x1800382de  call    ?WIN32_FROM_NTSTATUS@errcntrctlib@@YAKJ@Z; errcntrctlib::WIN32_FROM_NTSTATUS(long)
0x1800382e3  jmp     short loc_180038318
0x1800382e5  movups  xmm0, [rsp+68h+var_48]
0x1800382ea  movups  xmmword ptr [rbx+18h], xmm0
0x1800382ee  movups  xmm1, [rsp+68h+var_38]
0x1800382f3  movups  xmmword ptr [rbx+28h], xmm1
0x1800382f7  movzx   eax, byte ptr [rsp+68h+var_48]
0x1800382fc  and     eax, 0Fh
0x1800382ff  mov     rcx, [rdi+rax*8]
0x180038303  test    rcx, rcx
0x180038306  jz      short loc_18003830C
0x180038308  mov     [rbx+10h], rcx
0x18003830c  mov     [rdi+rax*8], rbx
0x180038310  inc     dword ptr [rdi+80h]
0x180038316  xor     eax, eax
0x180038318  mov     rcx, [rsp+68h+var_28]
0x18003831d  xor     rcx, rsp; StackCookie
0x180038320  call    __security_check_cookie
0x180038325  mov     rbx, [rsp+68h+arg_10]
0x18003832d  add     rsp, 50h
0x180038331  pop     rdi
0x180038332  pop     rsi
0x180038333  pop     rbp
0x180038334  retn
```
