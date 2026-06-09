# META_SCRIPT_MAP_TABLE::~META_SCRIPT_MAP_TABLE(void)

- ea: `0x1800057f8`
- end: `0x180005899`
- name: `??1META_SCRIPT_MAP_TABLE@@AEAA@XZ`
- size: `161`
- prototype: `void __fastcall(META_SCRIPT_MAP_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004528`

## callees

- `0x1800057f8`
- `0x180007010`

## pseudocode

```c
void __fastcall META_SCRIPT_MAP_TABLE::~META_SCRIPT_MAP_TABLE(META_SCRIPT_MAP_TABLE *this)
{
  _QWORD **v2; // rbx
  _QWORD *v3; // rax
  __int64 v4; // rdx
  _QWORD *v5; // r8
  _QWORD **v6; // rbx
  _QWORD *v7; // rax
  __int64 v8; // rdx
  _QWORD *v9; // r8

  v2 = (_QWORD **)((char *)this + 24);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    v4 = *v3;
    if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
LABEL_13:
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    if ( v3 != (_QWORD *)8 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*(v3 - 1) + 88LL))(v3 - 1, 1);
  }
  v6 = (_QWORD **)((char *)this + 8);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == v6 )
      break;
    v8 = *v7;
    if ( *(_QWORD **)(*v7 + 8LL) != v7 )
      goto LABEL_13;
    v9 = (_QWORD *)v7[1];
    if ( (_QWORD *)*v9 != v7 )
      goto LABEL_13;
    *v9 = v8;
    *(_QWORD *)(v8 + 8) = v9;
    if ( v7 != (_QWORD *)8 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*(v7 - 1) + 88LL))(v7 - 1, 1);
  }
}

```

## disassembly

```asm
0x1800057f8  mov     [rsp+arg_0], rbx
0x1800057fd  push    rdi
0x1800057fe  sub     rsp, 20h
0x180005802  mov     rdi, rcx
0x180005805  lea     rbx, [rcx+18h]
0x180005809  mov     rax, [rbx]
0x18000580c  cmp     rax, rbx
0x18000580f  jz      short loc_180005846
0x180005811  mov     rdx, [rax]
0x180005814  cmp     [rdx+8], rax
0x180005818  jnz     short loc_180005887
0x18000581a  mov     r8, [rax+8]
0x18000581e  cmp     [r8], rax
0x180005821  jnz     short loc_180005887
0x180005823  lea     rcx, [rax-8]
0x180005827  mov     [r8], rdx
0x18000582a  mov     [rdx+8], r8
0x18000582e  test    rcx, rcx
0x180005831  jz      short loc_180005809
0x180005833  mov     rax, [rcx]
0x180005836  mov     edx, 1
0x18000583b  mov     rax, [rax+58h]
0x18000583f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005844  jmp     short loc_180005809
0x180005846  lea     rbx, [rdi+8]
0x18000584a  mov     rax, [rbx]
0x18000584d  cmp     rax, rbx
0x180005850  jz      short loc_18000588E
0x180005852  mov     rdx, [rax]
0x180005855  cmp     [rdx+8], rax
0x180005859  jnz     short loc_180005887
0x18000585b  mov     r8, [rax+8]
0x18000585f  cmp     [r8], rax
0x180005862  jnz     short loc_180005887
0x180005864  lea     rcx, [rax-8]
0x180005868  mov     [r8], rdx
0x18000586b  mov     [rdx+8], r8
0x18000586f  test    rcx, rcx
0x180005872  jz      short loc_18000584A
0x180005874  mov     rax, [rcx]
0x180005877  mov     edx, 1
0x18000587c  mov     rax, [rax+58h]
0x180005880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005885  jmp     short loc_18000584A
0x180005887  mov     ecx, 3
0x18000588c  int     29h; Win8: RtlFailFast(ecx)
0x18000588e  mov     rbx, [rsp+28h+arg_0]
0x180005893  add     rsp, 20h
0x180005897  pop     rdi
0x180005898  retn
```
