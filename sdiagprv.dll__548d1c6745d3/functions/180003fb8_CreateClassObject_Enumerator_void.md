# CreateClassObject<Enumerator>(void)

- ea: `0x180003fb8`
- end: `0x180004013`
- name: `??$CreateClassObject@VEnumerator@@@@YAPEAVEnumerator@@XZ`
- size: `91`
- prototype: `Enumerator *()`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180004cf0`
- `0x180005ce0`
- `0x1800113a0`

## callees

- `0x180001074`
- `0x180003fb8`
- `0x180005924`
- `0x180019010`

## pseudocode

```c
Enumerator *CreateClassObject<Enumerator>()
{
  Enumerator *v0; // rax
  Enumerator *v1; // rbx

  v0 = (Enumerator *)operator new(0x60u);
  if ( v0 )
    v1 = Enumerator::Enumerator(v0);
  else
    v1 = 0;
  if ( v1 && (**((int (__fastcall ***)(__int64))v1 + 1))((__int64)v1 + 8) < 0 )
  {
    (*(void (__fastcall **)(Enumerator *))(*(_QWORD *)v1 + 16LL))(v1);
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x180003fb8  push    rbx
0x180003fba  sub     rsp, 20h
0x180003fbe  mov     ecx, 60h ; '`'; Size
0x180003fc3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003fc8  mov     [rsp+28h+arg_0], rax
0x180003fcd  test    rax, rax
0x180003fd0  jz      short loc_180003FDF
0x180003fd2  mov     rcx, rax; this
0x180003fd5  call    ??0Enumerator@@QEAA@XZ; Enumerator::Enumerator(void)
0x180003fda  mov     rbx, rax
0x180003fdd  jmp     short loc_180003FE1
0x180003fdf  xor     ebx, ebx
0x180003fe1  test    rbx, rbx
0x180003fe4  jz      short loc_18000400A
0x180003fe6  lea     rcx, [rbx+8]
0x180003fea  mov     rax, [rcx]
0x180003fed  mov     rax, [rax]
0x180003ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ff5  test    eax, eax
0x180003ff7  jns     short loc_18000400A
0x180003ff9  mov     rax, [rbx]
0x180003ffc  mov     rcx, rbx
0x180003fff  mov     rax, [rax+10h]
0x180004003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004008  xor     ebx, ebx
0x18000400a  mov     rax, rbx
0x18000400d  add     rsp, 20h
0x180004011  pop     rbx
0x180004012  retn
```
