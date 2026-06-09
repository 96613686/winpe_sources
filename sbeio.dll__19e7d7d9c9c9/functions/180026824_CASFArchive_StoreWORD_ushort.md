# CASFArchive::StoreWORD(ushort)

- ea: `0x180026824`
- end: `0x180026891`
- name: `?StoreWORD@CASFArchive@@QEAAJG@Z`
- size: `109`
- prototype: `__int64 __fastcall(CASFArchive *__hidden this, unsigned __int16)`
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x18001da90`
- `0x18001dc30`
- `0x18001dce0`
- `0x18001dd70`
- `0x18001e080`
- `0x18001e4c0`
- `0x18001e5a0`
- `0x18001e640`
- `0x18001e790`
- `0x18001e850`
- `0x18001e950`
- `0x18001e9c0`
- `0x18001ea80`
- `0x18001ecf0`
- `0x18001eea0`
- `0x18001efa0`
- `0x18001f0c0`
- `0x18001f400`
- `0x18001f4c0`
- `0x18001f620`
- `0x180026600`
- `0x180026748`
- `0x180028340`
- `0x180028580`

## callees

- `0x1800015f0`
- `0x180026824`
- `0x180026ae0`

## pseudocode

```c
__int64 __fastcall CASFArchive::StoreWORD(CASFArchive *this, __int16 a2)
{
  CASFArchive *v2; // r9
  unsigned __int64 v3; // rax
  unsigned __int8 v5[8]; // [rsp+20h] [rbp-18h] BYREF

  v2 = this;
  v3 = *((_QWORD *)this + 1) + 2LL;
  *(_WORD *)v5 = a2;
  if ( v3 > *((_QWORD *)this + 2) )
    return 3222079440LL;
  if ( *((_BYTE *)this + 28) != *((_BYTE *)this + 29) )
  {
    CASFArchive::SwapBlockEndian(this, v5, 2);
    a2 = *(_WORD *)v5;
  }
  **((_WORD **)v2 + 1) = a2;
  *((_QWORD *)v2 + 1) += 2LL;
  return 0;
}

```

## disassembly

```asm
0x180026824  sub     rsp, 38h
0x180026828  mov     rax, cs:__security_cookie
0x18002682f  xor     rax, rsp
0x180026832  mov     [rsp+38h+var_10], rax
0x180026837  mov     rax, [rcx+8]
0x18002683b  mov     r9, rcx
0x18002683e  add     rax, 2
0x180026842  mov     word ptr [rsp+38h+var_18], dx
0x180026847  cmp     rax, [rcx+10h]
0x18002684b  jbe     short loc_180026854
0x18002684d  mov     eax, 0C00D07D0h
0x180026852  jmp     short loc_18002687F
0x180026854  mov     al, [rcx+1Dh]
0x180026857  cmp     [rcx+1Ch], al
0x18002685a  jz      short loc_180026871
0x18002685c  mov     r8d, 2; int
0x180026862  lea     rdx, [rsp+38h+var_18]; unsigned __int8 *
0x180026867  call    ?SwapBlockEndian@CASFArchive@@QEAAXPEAEH@Z; CASFArchive::SwapBlockEndian(uchar *,int)
0x18002686c  movzx   edx, word ptr [rsp+38h+var_18]
0x180026871  mov     rax, [r9+8]
0x180026875  mov     [rax], dx
0x180026878  add     qword ptr [r9+8], 2
0x18002687d  xor     eax, eax
0x18002687f  mov     rcx, [rsp+38h+var_10]
0x180026884  xor     rcx, rsp; StackCookie
0x180026887  call    __security_check_cookie
0x18002688c  add     rsp, 38h
0x180026890  retn
```
