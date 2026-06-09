# URI_LOCK_LIST::FindLockByToken(ushort const *)

- ea: `0x180003710`
- end: `0x1800037ac`
- name: `?FindLockByToken@URI_LOCK_LIST@@UEAAPEAVIPubLock@@PEBG@Z`
- size: `156`
- prototype: `struct IPubLock *__fastcall(URI_LOCK_LIST *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003710`
- `0x180003c30`
- `0x180004010`

## pseudocode

```c
struct IPubLock *__fastcall URI_LOCK_LIST::FindLockByToken(URI_LOCK_LIST *this, char *a2)
{
  __int64 i; // rax
  __int64 v5; // rax
  char *v6; // r8
  int v7; // edx
  int v8; // ecx
  __int64 v9; // rbx
  _BYTE v11[64]; // [rsp+20h] [rbp-58h] BYREF

  for ( i = (*(__int64 (__fastcall **)(URI_LOCK_LIST *, _BYTE *))(*(_QWORD *)this + 32LL))(this, v11);
        ;
        i = (*(__int64 (__fastcall **)(URI_LOCK_LIST *, _BYTE *))(*(_QWORD *)this + 40LL))(this, v11) )
  {
    v9 = i;
    if ( !i )
      return 0;
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 24LL))(i);
    v6 = &a2[-v5];
    do
    {
      v7 = *(unsigned __int16 *)&v6[v5];
      v8 = *(unsigned __int16 *)v5 - v7;
      if ( v8 )
        break;
      v5 += 2;
    }
    while ( v7 );
    if ( !v8 )
      break;
  }
  return (struct IPubLock *)v9;
}

```

## disassembly

```asm
0x180003710  mov     [rsp+arg_8], rbx
0x180003715  mov     [rsp+arg_10], rsi
0x18000371a  push    rdi
0x18000371b  sub     rsp, 70h
0x18000371f  mov     rax, cs:__security_cookie
0x180003726  xor     rax, rsp
0x180003729  mov     [rsp+78h+var_18], rax
0x18000372e  mov     rax, [rcx]
0x180003731  mov     rsi, rdx
0x180003734  mov     rdi, rcx
0x180003737  mov     rax, [rax+20h]
0x18000373b  jmp     short loc_180003774
0x18000373d  mov     rcx, [rbx]
0x180003740  mov     rax, [rcx+18h]
0x180003744  mov     rcx, rbx
0x180003747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000374c  mov     r8, rsi
0x18000374f  sub     r8, rax
0x180003752  movzx   ecx, word ptr [rax]
0x180003755  movzx   edx, word ptr [rax+r8]
0x18000375a  sub     ecx, edx
0x18000375c  jnz     short loc_180003766
0x18000375e  add     rax, 2
0x180003762  test    edx, edx
0x180003764  jnz     short loc_180003752
0x180003766  test    ecx, ecx
0x180003768  jz      short loc_1800037A7
0x18000376a  mov     rax, [rdi]
0x18000376d  mov     rcx, rdi
0x180003770  mov     rax, [rax+28h]
0x180003774  lea     rdx, [rsp+78h+var_58]
0x180003779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000377e  mov     rbx, rax
0x180003781  test    rax, rax
0x180003784  jnz     short loc_18000373D
0x180003786  xor     eax, eax
0x180003788  mov     rcx, [rsp+78h+var_18]
0x18000378d  xor     rcx, rsp; StackCookie
0x180003790  call    __security_check_cookie
0x180003795  lea     r11, [rsp+78h+var_8]
0x18000379a  mov     rbx, [r11+18h]
0x18000379e  mov     rsi, [r11+20h]
0x1800037a2  mov     rsp, r11
0x1800037a5  pop     rdi
0x1800037a6  retn
0x1800037a7  mov     rax, rbx
0x1800037aa  jmp     short loc_180003788
```
