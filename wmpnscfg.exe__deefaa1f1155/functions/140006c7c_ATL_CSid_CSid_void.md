# ATL::CSid::~CSid(void)

- ea: `0x140006c7c`
- end: `0x140006d31`
- name: `??1CSid@ATL@@UEAA@XZ`
- size: `181`
- prototype: `void __fastcall(ATL::CSid *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140006d40`
- `0x140006d7c`
- `0x140007754`

## callees

- `0x140006c7c`
- `0x140008010`

## pseudocode

```c
void __fastcall ATL::CSid::~CSid(ATL::CSid *this)
{
  volatile signed __int32 *v1; // rdx
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rdx
  volatile signed __int32 *v5; // rdx

  v1 = (volatile signed __int32 *)(*((_QWORD *)this + 14) - 24LL);
  *(_QWORD *)this = &ATL::CSid::`vftable';
  if ( _InterlockedDecrement(v1 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v1 + 8LL))(*(_QWORD *)v1);
  v3 = (volatile signed __int32 *)(*((_QWORD *)this + 13) - 24LL);
  if ( _InterlockedDecrement(v3 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
  v4 = (volatile signed __int32 *)(*((_QWORD *)this + 12) - 24LL);
  if ( _InterlockedDecrement(v4 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  v5 = (volatile signed __int32 *)(*((_QWORD *)this + 11) - 24LL);
  if ( _InterlockedDecrement(v5 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
}

```

## disassembly

```asm
0x140006c7c  mov     [rsp+arg_0], rbx
0x140006c81  push    rdi
0x140006c82  sub     rsp, 20h
0x140006c86  mov     rdx, [rcx+70h]
0x140006c8a  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x140006c91  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140006c95  mov     [rcx], rax
0x140006c98  or      edi, 0FFFFFFFFh
0x140006c9b  mov     rbx, rcx
0x140006c9e  mov     eax, edi
0x140006ca0  lock xadd [rdx+10h], eax
0x140006ca5  add     eax, edi
0x140006ca7  test    eax, eax
0x140006ca9  jg      short loc_140006CBA
0x140006cab  mov     rcx, [rdx]
0x140006cae  mov     rax, [rcx]
0x140006cb1  mov     rax, [rax+8]
0x140006cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cba  mov     rdx, [rbx+68h]
0x140006cbe  mov     eax, edi
0x140006cc0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140006cc4  lock xadd [rdx+10h], eax
0x140006cc9  add     eax, edi
0x140006ccb  test    eax, eax
0x140006ccd  jg      short loc_140006CDE
0x140006ccf  mov     rcx, [rdx]
0x140006cd2  mov     rax, [rcx]
0x140006cd5  mov     rax, [rax+8]
0x140006cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cde  mov     rdx, [rbx+60h]
0x140006ce2  mov     eax, edi
0x140006ce4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140006ce8  lock xadd [rdx+10h], eax
0x140006ced  add     eax, edi
0x140006cef  test    eax, eax
0x140006cf1  jg      short loc_140006D02
0x140006cf3  mov     rcx, [rdx]
0x140006cf6  mov     rax, [rcx]
0x140006cf9  mov     rax, [rax+8]
0x140006cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d02  mov     rdx, [rbx+58h]
0x140006d06  mov     eax, edi
0x140006d08  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140006d0c  lock xadd [rdx+10h], eax
0x140006d11  add     eax, edi
0x140006d13  test    eax, eax
0x140006d15  jg      short loc_140006D26
0x140006d17  mov     rcx, [rdx]
0x140006d1a  mov     rax, [rcx]
0x140006d1d  mov     rax, [rax+8]
0x140006d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d26  mov     rbx, [rsp+28h+arg_0]
0x140006d2b  add     rsp, 20h
0x140006d2f  pop     rdi
0x140006d30  retn
```
