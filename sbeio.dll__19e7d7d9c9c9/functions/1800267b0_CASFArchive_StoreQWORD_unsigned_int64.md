# CASFArchive::StoreQWORD(unsigned __int64)

- ea: `0x1800267b0`
- end: `0x18002681d`
- name: `?StoreQWORD@CASFArchive@@QEAAJ_K@Z`
- size: `109`
- prototype: `__int64 __fastcall(CASFArchive *__hidden this, unsigned __int64)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e3d0`
- `0x18001e790`
- `0x18001e900`
- `0x18001e950`
- `0x18001ebb0`
- `0x18001efa0`
- `0x18001f0c0`
- `0x180026660`
- `0x1800266a0`
- `0x1800282d0`
- `0x180028340`

## callees

- `0x1800015f0`
- `0x1800267b0`
- `0x180026ae0`

## pseudocode

```c
__int64 __fastcall CASFArchive::StoreQWORD(CASFArchive *this, __int64 a2)
{
  CASFArchive *v2; // r9
  unsigned __int64 v3; // rax
  unsigned __int8 v5[8]; // [rsp+20h] [rbp-18h] BYREF

  v2 = this;
  v3 = *((_QWORD *)this + 1) + 8LL;
  *(_QWORD *)v5 = a2;
  if ( v3 > *((_QWORD *)this + 2) )
    return 3222079440LL;
  if ( *((_BYTE *)this + 28) != *((_BYTE *)this + 29) )
  {
    CASFArchive::SwapBlockEndian(this, v5, 8);
    a2 = *(_QWORD *)v5;
  }
  **((_QWORD **)v2 + 1) = a2;
  *((_QWORD *)v2 + 1) += 8LL;
  return 0;
}

```

## disassembly

```asm
0x1800267b0  sub     rsp, 38h
0x1800267b4  mov     rax, cs:__security_cookie
0x1800267bb  xor     rax, rsp
0x1800267be  mov     [rsp+38h+var_10], rax
0x1800267c3  mov     rax, [rcx+8]
0x1800267c7  mov     r9, rcx
0x1800267ca  add     rax, 8
0x1800267ce  mov     qword ptr [rsp+38h+var_18], rdx
0x1800267d3  cmp     rax, [rcx+10h]
0x1800267d7  jbe     short loc_1800267E0
0x1800267d9  mov     eax, 0C00D07D0h
0x1800267de  jmp     short loc_18002680B
0x1800267e0  mov     al, [rcx+1Dh]
0x1800267e3  cmp     [rcx+1Ch], al
0x1800267e6  jz      short loc_1800267FD
0x1800267e8  mov     r8d, 8; int
0x1800267ee  lea     rdx, [rsp+38h+var_18]; unsigned __int8 *
0x1800267f3  call    ?SwapBlockEndian@CASFArchive@@QEAAXPEAEH@Z; CASFArchive::SwapBlockEndian(uchar *,int)
0x1800267f8  mov     rdx, qword ptr [rsp+38h+var_18]
0x1800267fd  mov     rax, [r9+8]
0x180026801  mov     [rax], rdx
0x180026804  add     qword ptr [r9+8], 8
0x180026809  xor     eax, eax
0x18002680b  mov     rcx, [rsp+38h+var_10]
0x180026810  xor     rcx, rsp; StackCookie
0x180026813  call    __security_check_cookie
0x180026818  add     rsp, 38h
0x18002681c  retn
```
