# ATL::CSid::~CSid(void)

- ea: `0x1400028b0`
- end: `0x140002969`
- name: `??1CSid@ATL@@UEAA@XZ`
- size: `185`
- prototype: `void __fastcall(ATL::CSid *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400021f0`
- `0x1400022d0`
- `0x140009580`
- `0x14000aac0`
- `0x14000ab00`

## callees

- `0x1400028b0`
- `0x14000c010`

## pseudocode

```c
void __fastcall ATL::CSid::~CSid(ATL::CSid *this)
{
  __int64 v1; // rdx
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rdx
  volatile signed __int32 *v5; // rdx
  volatile signed __int32 *v6; // rdx

  v1 = *((_QWORD *)this + 14);
  *(_QWORD *)this = &ATL::CSid::`vftable';
  v3 = (volatile signed __int32 *)(v1 - 24);
  if ( _InterlockedExchangeAdd(v3 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
  v4 = (volatile signed __int32 *)(*((_QWORD *)this + 13) - 24LL);
  if ( _InterlockedExchangeAdd(v4 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  v5 = (volatile signed __int32 *)(*((_QWORD *)this + 12) - 24LL);
  if ( _InterlockedExchangeAdd(v5 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
  v6 = (volatile signed __int32 *)(*((_QWORD *)this + 11) - 24LL);
  if ( _InterlockedExchangeAdd(v6 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 8LL))(*(_QWORD *)v6);
}

```

## disassembly

```asm
0x1400028b0  mov     [rsp+arg_0], rbx
0x1400028b5  push    rdi
0x1400028b6  sub     rsp, 20h
0x1400028ba  mov     rdx, [rcx+70h]
0x1400028be  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x1400028c5  mov     ebx, 0FFFFFFFFh
0x1400028ca  mov     [rcx], rax
0x1400028cd  mov     eax, ebx
0x1400028cf  mov     rdi, rcx
0x1400028d2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400028d6  lock xadd [rdx+10h], eax
0x1400028db  sub     eax, 1
0x1400028de  jle     short loc_140002925
0x1400028e0  mov     rdx, [rdi+68h]
0x1400028e4  mov     eax, ebx
0x1400028e6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400028ea  lock xadd [rdx+10h], eax
0x1400028ef  sub     eax, 1
0x1400028f2  jle     short loc_140002936
0x1400028f4  mov     rdx, [rdi+60h]
0x1400028f8  mov     eax, ebx
0x1400028fa  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400028fe  lock xadd [rdx+10h], eax
0x140002903  sub     eax, 1
0x140002906  jle     short loc_140002947
0x140002908  mov     rdx, [rdi+58h]
0x14000290c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140002910  lock xadd [rdx+10h], ebx
0x140002915  sub     ebx, 1
0x140002918  jle     short loc_140002958
0x14000291a  mov     rbx, [rsp+28h+arg_0]
0x14000291f  add     rsp, 20h
0x140002923  pop     rdi
0x140002924  retn
0x140002925  mov     rcx, [rdx]
0x140002928  mov     rax, [rcx]
0x14000292b  mov     rax, [rax+8]
0x14000292f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002934  jmp     short loc_1400028E0
0x140002936  mov     rcx, [rdx]
0x140002939  mov     rax, [rcx]
0x14000293c  mov     rax, [rax+8]
0x140002940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002945  jmp     short loc_1400028F4
0x140002947  mov     rcx, [rdx]
0x14000294a  mov     rax, [rcx]
0x14000294d  mov     rax, [rax+8]
0x140002951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002956  jmp     short loc_140002908
0x140002958  mov     rcx, [rdx]
0x14000295b  mov     rax, [rcx]
0x14000295e  mov     rax, [rax+8]
0x140002962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002967  jmp     short loc_14000291A
```
