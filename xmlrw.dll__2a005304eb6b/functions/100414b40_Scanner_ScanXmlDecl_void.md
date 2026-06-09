# Scanner::ScanXmlDecl(void)

- ea: `0x100414b40`
- end: `0x100414ce1`
- name: `?ScanXmlDecl@Scanner@@AEAAXXZ`
- size: `417`
- prototype: `void __fastcall(Scanner *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x10040ca10`
- `0x10040f530`
- `0x100414b40`
- `0x100439df0`

## pseudocode

```c
void __fastcall Scanner::ScanXmlDecl(Scanner *this)
{
  __int64 v2; // rdx
  __int16 v3; // ax
  __int16 v4; // ax
  __int16 v5; // ax
  __int16 v6; // ax
  __int16 v7; // ax
  __int64 v8; // rcx
  __int16 v9; // ax
  __int64 v10; // rcx
  __int64 v11; // rcx

  *(_BYTE *)(*((_QWORD *)this + 8) + 25LL) = 1;
  v2 = *((_QWORD *)this + 8);
  *(_QWORD *)(v2 + 56) = *(_QWORD *)(v2 + 48);
  *(_DWORD *)(v2 + 88) = 1;
  *((_QWORD *)this + 22) = *(_QWORD *)(*((_QWORD *)this + 12) + 8LL * (unsigned int)(--*((_DWORD *)this + 26) - 1));
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
  *((_WORD *)this + 92) = v3;
  if ( v3 != 60 )
    goto LABEL_16;
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
  *((_WORD *)this + 92) = v4;
  if ( v4 != 63
    || (v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8)),
        *((_WORD *)this + 92) = v5,
        v5 != 120)
    || (v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8)),
        *((_WORD *)this + 92) = v6,
        v6 != 109)
    || (v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8)),
        *((_WORD *)this + 92) = v7,
        v7 != 108) )
  {
LABEL_16:
    *(_BYTE *)(*((_QWORD *)this + 8) + 25LL) = 0;
    v11 = *((_QWORD *)this + 8);
    *(_QWORD *)(v11 + 48) = *(_QWORD *)(v11 + 56);
    *(_DWORD *)(v11 + 88) = 1;
    *((_DWORD *)this + 18) = 0;
    return;
  }
  v8 = *((_QWORD *)this + 8);
  *((_DWORD *)this + 18) = 1;
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 88LL))(v8);
  *((_WORD *)this + 92) = v9;
  if ( v9 != 9 && v9 != 10 && v9 != 13 && v9 != 32 && v9 != 63 )
  {
    if ( *(_BYTE *)(*((_QWORD *)this + 8) + 24LL) )
    {
      Scanner::CheckEndOfInput(this);
      return;
    }
    goto LABEL_16;
  }
  v10 = *((unsigned int *)this + 26);
  if ( *((_DWORD *)this + 27) == (_DWORD)v10 )
  {
    _stack<void (Scanner::*)(void),8>::grow((__int64)this + 80, 0);
    v10 = *((unsigned int *)this + 26);
  }
  *((_DWORD *)this + 26) = v10 + 1;
  *(_QWORD *)(*((_QWORD *)this + 12) + 8 * v10) = Scanner::ScanXmlDeclAttribute;
  *((_QWORD *)this + 22) = Scanner::ScanXmlDeclAttribute;
}

```

## disassembly

```asm
0x100414b40  push    rbx
0x100414b42  sub     rsp, 20h
0x100414b46  mov     rax, [rcx+40h]
0x100414b4a  mov     rbx, rcx
0x100414b4d  mov     byte ptr [rax+19h], 1
0x100414b51  mov     rdx, [rcx+40h]
0x100414b55  mov     rax, [rdx+30h]
0x100414b59  mov     [rdx+38h], rax
0x100414b5d  mov     dword ptr [rdx+58h], 1
0x100414b64  dec     dword ptr [rcx+68h]
0x100414b67  mov     ecx, [rcx+68h]
0x100414b6a  mov     rax, [rbx+60h]
0x100414b6e  dec     ecx
0x100414b70  mov     rcx, [rax+rcx*8]
0x100414b74  mov     [rbx+0B0h], rcx
0x100414b7b  mov     rcx, [rbx+40h]
0x100414b7f  mov     rax, [rcx]
0x100414b82  mov     rax, [rax+58h]
0x100414b86  call    cs:__guard_dispatch_icall_fptr
0x100414b8c  mov     [rbx+0B8h], ax
0x100414b93  cmp     ax, 3Ch ; '<'
0x100414b97  jnz     loc_100414CB9
0x100414b9d  mov     rcx, [rbx+40h]
0x100414ba1  mov     rax, [rcx]
0x100414ba4  mov     rax, [rax+58h]
0x100414ba8  call    cs:__guard_dispatch_icall_fptr
0x100414bae  mov     [rbx+0B8h], ax
0x100414bb5  cmp     ax, 3Fh ; '?'
0x100414bb9  jnz     loc_100414CB9
0x100414bbf  mov     rcx, [rbx+40h]
0x100414bc3  mov     rax, [rcx]
0x100414bc6  mov     rax, [rax+58h]
0x100414bca  call    cs:__guard_dispatch_icall_fptr
0x100414bd0  mov     [rbx+0B8h], ax
0x100414bd7  cmp     ax, 78h ; 'x'
0x100414bdb  jnz     loc_100414CB9
0x100414be1  mov     rcx, [rbx+40h]
0x100414be5  mov     rax, [rcx]
0x100414be8  mov     rax, [rax+58h]
0x100414bec  call    cs:__guard_dispatch_icall_fptr
0x100414bf2  mov     [rbx+0B8h], ax
0x100414bf9  cmp     ax, 6Dh ; 'm'
0x100414bfd  jnz     loc_100414CB9
0x100414c03  mov     rcx, [rbx+40h]
0x100414c07  mov     rax, [rcx]
0x100414c0a  mov     rax, [rax+58h]
0x100414c0e  call    cs:__guard_dispatch_icall_fptr
0x100414c14  mov     [rbx+0B8h], ax
0x100414c1b  cmp     ax, 6Ch ; 'l'
0x100414c1f  jnz     loc_100414CB9
0x100414c25  mov     rcx, [rbx+40h]
0x100414c29  mov     dword ptr [rbx+48h], 1
0x100414c30  mov     rax, [rcx]
0x100414c33  mov     rax, [rax+58h]
0x100414c37  call    cs:__guard_dispatch_icall_fptr
0x100414c3d  movzx   ecx, ax
0x100414c40  mov     [rbx+0B8h], cx
0x100414c47  sub     ecx, 9
0x100414c4a  jz      short loc_100414C77
0x100414c4c  sub     ecx, 1
0x100414c4f  jz      short loc_100414C77
0x100414c51  sub     ecx, 3
0x100414c54  jz      short loc_100414C77
0x100414c56  sub     ecx, 13h
0x100414c59  jz      short loc_100414C77
0x100414c5b  cmp     ecx, 1Fh
0x100414c5e  jz      short loc_100414C77
0x100414c60  mov     rax, [rbx+40h]
0x100414c64  cmp     byte ptr [rax+18h], 0
0x100414c68  jz      short loc_100414CB9
0x100414c6a  mov     rcx, rbx; this
0x100414c6d  add     rsp, 20h
0x100414c71  pop     rbx
0x100414c72  jmp     ?CheckEndOfInput@Scanner@@AEAAXXZ; Scanner::CheckEndOfInput(void)
0x100414c77  mov     ecx, [rbx+68h]
0x100414c7a  mov     [rsp+28h+arg_0], rdi
0x100414c7f  cmp     [rbx+6Ch], ecx
0x100414c82  jnz     short loc_100414C92
0x100414c84  xor     edx, edx
0x100414c86  lea     rcx, [rbx+50h]
0x100414c8a  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x100414c8f  mov     ecx, [rbx+68h]
0x100414c92  mov     rdi, [rsp+28h+arg_0]
0x100414c97  lea     eax, [rcx+1]
0x100414c9a  mov     [rbx+68h], eax
0x100414c9d  lea     rdx, ?ScanXmlDeclAttribute@Scanner@@AEAAXXZ; Scanner::ScanXmlDeclAttribute(void)
0x100414ca4  mov     rax, [rbx+60h]
0x100414ca8  mov     [rax+rcx*8], rdx
0x100414cac  mov     [rbx+0B0h], rdx
0x100414cb3  add     rsp, 20h
0x100414cb7  pop     rbx
0x100414cb8  retn
0x100414cb9  mov     rax, [rbx+40h]
0x100414cbd  mov     byte ptr [rax+19h], 0
0x100414cc1  mov     rcx, [rbx+40h]
0x100414cc5  mov     rax, [rcx+38h]
0x100414cc9  mov     [rcx+30h], rax
0x100414ccd  mov     dword ptr [rcx+58h], 1
0x100414cd4  mov     dword ptr [rbx+48h], 0
0x100414cdb  add     rsp, 20h
0x100414cdf  pop     rbx
0x100414ce0  retn
```
