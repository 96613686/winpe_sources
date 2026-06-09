# WP_IPM::SetupCounters(int)

- ea: `0x18000831c`
- end: `0x180008404`
- name: `?SetupCounters@WP_IPM@@AEAAXH@Z`
- size: `232`
- prototype: `void __fastcall(WP_IPM *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180007958`
- `0x18000840c`

## callees

- `0x18000831c`
- `0x18000d010`

## pseudocode

```c
void __fastcall WP_IPM::SetupCounters(WP_IPM *this, __int64 a2)
{
  char *v3; // rcx
  void (__fastcall *v4)(char *, __int64, __int64, char *); // rax
  char *v5; // r9

  v3 = (char *)g_pW3WPHost + 48;
  v4 = *(void (__fastcall **)(char *, __int64, __int64, char *))(*((_QWORD *)g_pW3WPHost + 6) + 32LL);
  if ( (_DWORD)a2 )
  {
    v4(v3, 0, 1, (char *)this + 60);
    (*(void (__fastcall **)(char *, _QWORD, __int64, char *))(*((_QWORD *)g_pW3WPHost + 6) + 32LL))(
      (char *)g_pW3WPHost + 48,
      0,
      2,
      (char *)this + 64);
    (*(void (__fastcall **)(char *, _QWORD, __int64, char *))(*((_QWORD *)g_pW3WPHost + 6) + 32LL))(
      (char *)g_pW3WPHost + 48,
      0,
      5,
      (char *)this + 68);
    v5 = (char *)this + 72;
  }
  else
  {
    v4(v3, a2, 1, 0);
    (*(void (__fastcall **)(char *, _QWORD, __int64))(*((_QWORD *)g_pW3WPHost + 6) + 32LL))(
      (char *)g_pW3WPHost + 48,
      0,
      2);
    (*(void (__fastcall **)(char *, _QWORD, __int64))(*((_QWORD *)g_pW3WPHost + 6) + 32LL))(
      (char *)g_pW3WPHost + 48,
      0,
      5);
    v5 = 0;
  }
  (*(void (__fastcall **)(char *, _QWORD, __int64, char *))(*((_QWORD *)g_pW3WPHost + 6) + 32LL))(
    (char *)g_pW3WPHost + 48,
    0,
    6,
    v5);
}

```

## disassembly

```asm
0x18000831c  push    rbx
0x18000831e  sub     rsp, 30h
0x180008322  mov     rbx, rcx
0x180008325  mov     r8d, 1
0x18000832b  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180008332  add     rcx, 30h ; '0'
0x180008336  mov     rax, [rcx]
0x180008339  mov     rax, [rax+20h]
0x18000833d  test    edx, edx
0x18000833f  jnz     short loc_18000838E
0x180008341  xor     r9d, r9d
0x180008344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008349  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180008350  xor     r9d, r9d
0x180008353  add     rcx, 30h ; '0'
0x180008357  xor     edx, edx
0x180008359  lea     r8d, [r9+2]
0x18000835d  mov     rax, [rcx]
0x180008360  mov     rax, [rax+20h]
0x180008364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008369  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180008370  xor     r9d, r9d
0x180008373  add     rcx, 30h ; '0'
0x180008377  xor     edx, edx
0x180008379  lea     r8d, [r9+5]
0x18000837d  mov     rax, [rcx]
0x180008380  mov     rax, [rax+20h]
0x180008384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008389  xor     r9d, r9d
0x18000838c  jmp     short loc_1800083DF
0x18000838e  lea     r9, [rbx+3Ch]
0x180008392  xor     edx, edx
0x180008394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008399  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800083a0  lea     r9, [rbx+40h]
0x1800083a4  add     rcx, 30h ; '0'
0x1800083a8  xor     edx, edx
0x1800083aa  mov     rax, [rcx]
0x1800083ad  lea     r8d, [rdx+2]
0x1800083b1  mov     rax, [rax+20h]
0x1800083b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083ba  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800083c1  lea     r9, [rbx+44h]
0x1800083c5  add     rcx, 30h ; '0'
0x1800083c9  xor     edx, edx
0x1800083cb  mov     rax, [rcx]
0x1800083ce  lea     r8d, [rdx+5]
0x1800083d2  mov     rax, [rax+20h]
0x1800083d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083db  lea     r9, [rbx+48h]
0x1800083df  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800083e6  mov     r8d, 6
0x1800083ec  add     rcx, 30h ; '0'
0x1800083f0  xor     edx, edx
0x1800083f2  mov     rax, [rcx]
0x1800083f5  mov     rax, [rax+20h]
0x1800083f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083fe  add     rsp, 30h
0x180008402  pop     rbx
0x180008403  retn
```
