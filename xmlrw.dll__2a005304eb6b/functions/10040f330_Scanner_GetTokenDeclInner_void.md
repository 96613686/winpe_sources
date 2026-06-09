# Scanner::GetTokenDeclInner(void)

- ea: `0x10040f330`
- end: `0x10040f506`
- name: `?GetTokenDeclInner@Scanner@@QEAAHXZ`
- size: `470`
- prototype: `__int64 __fastcall(Scanner *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10040a020`

## callees

- `0x10040ca10`
- `0x10040f330`
- `0x10040f5e0`
- `0x100413c70`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall Scanner::GetTokenDeclInner(Scanner *this)
{
  int v2; // eax
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned int v9; // ecx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx

  if ( *((_DWORD *)this + 18) != 12 )
    *((_WORD *)this + 92) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
  v2 = *((unsigned __int16 *)this + 92);
  while ( 2 )
  {
    switch ( v2 )
    {
      case 0:
        if ( !*(_BYTE *)(*((_QWORD *)this + 8) + 24LL) )
          goto LABEL_11;
        v9 = *((_DWORD *)this + 26);
        if ( *((_DWORD *)this + 27) == v9 )
        {
          _stack<void (Scanner::*)(void),8>::grow((__int64)this + 80, 0);
          v9 = *((_DWORD *)this + 26);
        }
        v10 = v9 + 1;
        v11 = v9;
        v12 = *((_QWORD *)this + 12);
        *((_DWORD *)this + 26) = v10;
        *(_QWORD *)(v12 + 8 * v11) = *((_QWORD *)this + 22);
        v13 = *((unsigned int *)this + 26);
        if ( *((_DWORD *)this + 27) == (_DWORD)v13 )
        {
          _stack<void (Scanner::*)(void),8>::grow((__int64)this + 80, 0);
          v13 = *((unsigned int *)this + 26);
        }
        *((_DWORD *)this + 26) = v13 + 1;
        *(_QWORD *)(*((_QWORD *)this + 12) + 8 * v13) = Scanner::CheckOmega;
        *((_QWORD *)this + 22) = Scanner::CheckOmega;
        Scanner::CheckOmega(this);
        return *((unsigned int *)this + 18);
      case 9:
      case 32:
        goto LABEL_9;
      case 10:
        v3 = *((_QWORD *)this + 8);
        ++*(_DWORD *)(v3 + 104);
        goto LABEL_8;
      case 13:
        v4 = *((_QWORD *)this + 8);
        v5 = *(_QWORD *)(v4 + 48);
        ++*(_DWORD *)(v4 + 104);
        *(_QWORD *)(v4 + 96) = v5;
        v6 = *((_QWORD *)this + 8);
        *(_QWORD *)(v6 + 56) = *(_QWORD *)(v6 + 48);
        *(_DWORD *)(v6 + 88) = 1;
        LOWORD(v2) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
        *((_WORD *)this + 92) = v2;
        if ( (_WORD)v2 != 10 )
          goto LABEL_10;
        v3 = *((_QWORD *)this + 8);
LABEL_8:
        *(_QWORD *)(v3 + 96) = *(_QWORD *)(v3 + 48);
LABEL_9:
        v7 = *((_QWORD *)this + 8);
        *(_QWORD *)(v7 + 56) = *(_QWORD *)(v7 + 48);
        *(_DWORD *)(v7 + 88) = 1;
        LOWORD(v2) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
        *((_WORD *)this + 92) = v2;
LABEL_10:
        v2 = (unsigned __int16)v2;
        if ( (unsigned __int16)v2 <= 0x25u )
          continue;
LABEL_11:
        (*((void (__fastcall **)(Scanner *))this + 22))(this);
        return *((unsigned int *)this + 18);
      case 37:
        Scanner::ScanPercentSubset(this);
        return *((unsigned int *)this + 18);
      default:
        goto LABEL_11;
    }
  }
}

```

## disassembly

```asm
0x10040f330  push    rbx
0x10040f332  sub     rsp, 20h
0x10040f336  cmp     dword ptr [rcx+48h], 0Ch
0x10040f33a  mov     rbx, rcx
0x10040f33d  jz      short loc_10040F357
0x10040f33f  mov     rcx, [rcx+40h]
0x10040f343  mov     rax, [rcx]
0x10040f346  mov     rax, [rax+58h]
0x10040f34a  call    cs:__guard_dispatch_icall_fptr
0x10040f350  mov     [rbx+0B8h], ax
0x10040f357  movzx   eax, word ptr [rbx+0B8h]
0x10040f35e  mov     [rsp+28h+arg_0], rdi
0x10040f363  cmp     eax, 25h; switch 38 cases
0x10040f366  ja      def_10040F387; jumptable 000000010040F387 default case, cases 1-8,11,12,14-31,33-36
0x10040f36c  lea     rdi, __ImageBase
0x10040f373  cdqe
0x10040f375  movzx   eax, ds:(byte_10040F4E0 - 100400000h)[rdi+rax]
0x10040f37d  mov     ecx, ds:(jpt_10040F387 - 100400000h)[rdi+rax*4]
0x10040f384  add     rcx, rdi
0x10040f387  jmp     rcx; switch jump
0x10040f389  mov     rcx, [rbx+40h]; jumptable 000000010040F387 case 10
0x10040f38d  inc     dword ptr [rcx+68h]
0x10040f390  jmp     short loc_10040F3D6
0x10040f392  mov     rcx, [rbx+40h]; jumptable 000000010040F387 case 13
0x10040f396  mov     rax, [rcx+30h]
0x10040f39a  inc     dword ptr [rcx+68h]
0x10040f39d  mov     [rcx+60h], rax
0x10040f3a1  mov     rcx, [rbx+40h]
0x10040f3a5  mov     rax, [rcx+30h]
0x10040f3a9  mov     [rcx+38h], rax
0x10040f3ad  mov     dword ptr [rcx+58h], 1
0x10040f3b4  mov     rcx, [rbx+40h]
0x10040f3b8  mov     rax, [rcx]
0x10040f3bb  mov     rax, [rax+58h]
0x10040f3bf  call    cs:__guard_dispatch_icall_fptr
0x10040f3c5  mov     [rbx+0B8h], ax
0x10040f3cc  cmp     ax, 0Ah
0x10040f3d0  jnz     short loc_10040F409
0x10040f3d2  mov     rcx, [rbx+40h]
0x10040f3d6  mov     rax, [rcx+30h]
0x10040f3da  mov     [rcx+60h], rax
0x10040f3de  mov     rcx, [rbx+40h]; jumptable 000000010040F387 cases 9,32
0x10040f3e2  mov     rax, [rcx+30h]
0x10040f3e6  mov     [rcx+38h], rax
0x10040f3ea  mov     dword ptr [rcx+58h], 1
0x10040f3f1  mov     rcx, [rbx+40h]
0x10040f3f5  mov     rax, [rcx]
0x10040f3f8  mov     rax, [rax+58h]
0x10040f3fc  call    cs:__guard_dispatch_icall_fptr
0x10040f402  mov     [rbx+0B8h], ax
0x10040f409  movzx   eax, ax
0x10040f40c  cmp     eax, 25h ; '%'
0x10040f40f  jbe     loc_10040F373
0x10040f415  mov     rax, [rbx+0B0h]; jumptable 000000010040F387 default case, cases 1-8,11,12,14-31,33-36
0x10040f41c  mov     rcx, rbx
0x10040f41f  call    cs:__guard_dispatch_icall_fptr
0x10040f425  mov     eax, [rbx+48h]
0x10040f428  mov     rdi, [rsp+28h+arg_0]
0x10040f42d  add     rsp, 20h
0x10040f431  pop     rbx
0x10040f432  retn
0x10040f433  mov     rax, [rbx+40h]; jumptable 000000010040F387 case 0
0x10040f437  cmp     byte ptr [rax+18h], 0
0x10040f43b  jz      short def_10040F387; jumptable 000000010040F387 default case, cases 1-8,11,12,14-31,33-36
0x10040f43d  mov     ecx, [rbx+68h]
0x10040f440  cmp     [rbx+6Ch], ecx
0x10040f443  jnz     short loc_10040F453
0x10040f445  xor     edx, edx
0x10040f447  lea     rcx, [rbx+50h]
0x10040f44b  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x10040f450  mov     ecx, [rbx+68h]
0x10040f453  lea     eax, [rcx+1]
0x10040f456  mov     edx, ecx
0x10040f458  mov     rcx, [rbx+60h]
0x10040f45c  mov     [rbx+68h], eax
0x10040f45f  mov     rax, [rbx+0B0h]
0x10040f466  mov     [rcx+rdx*8], rax
0x10040f46a  mov     ecx, [rbx+68h]
0x10040f46d  cmp     [rbx+6Ch], ecx
0x10040f470  jnz     short loc_10040F480
0x10040f472  xor     edx, edx
0x10040f474  lea     rcx, [rbx+50h]
0x10040f478  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x10040f47d  mov     ecx, [rbx+68h]
0x10040f480  lea     eax, [rcx+1]
0x10040f483  mov     [rbx+68h], eax
0x10040f486  lea     rdx, ?CheckOmega@Scanner@@AEAAXXZ; Scanner::CheckOmega(void)
0x10040f48d  mov     rax, [rbx+60h]
0x10040f491  mov     [rax+rcx*8], rdx
0x10040f495  mov     rcx, rbx; this
0x10040f498  mov     [rbx+0B0h], rdx
0x10040f49f  call    ?CheckOmega@Scanner@@AEAAXXZ; Scanner::CheckOmega(void)
0x10040f4a4  mov     eax, [rbx+48h]
0x10040f4a7  mov     rdi, [rsp+28h+arg_0]
0x10040f4ac  add     rsp, 20h
0x10040f4b0  pop     rbx
0x10040f4b1  retn
0x10040f4b2  mov     rcx, rbx; jumptable 000000010040F387 case 37
0x10040f4b5  call    ?ScanPercentSubset@Scanner@@AEAAXXZ; Scanner::ScanPercentSubset(void)
0x10040f4ba  mov     eax, [rbx+48h]
0x10040f4bd  mov     rdi, [rsp+28h+arg_0]
0x10040f4c2  add     rsp, 20h
0x10040f4c6  pop     rbx
0x10040f4c7  retn
```
