# WP_IPM::SetupCounters(int)

- ea: `0x180008c0c`
- end: `0x180008cf5`
- name: `?SetupCounters@WP_IPM@@AEAAXH@Z`
- size: `233`
- prototype: `void __fastcall(WP_IPM *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180008128`
- `0x180008cfc`

## callees

- `0x180008c0c`
- `0x18000e010`

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
0x180008c0c  push    rbx
0x180008c0e  sub     rsp, 30h
0x180008c12  mov     rbx, rcx
0x180008c15  mov     r8d, 1
0x180008c1b  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180008c22  add     rcx, 30h ; '0'
0x180008c26  mov     rax, [rcx]
0x180008c29  mov     rax, [rax+20h]
0x180008c2d  test    edx, edx
0x180008c2f  jnz     short loc_180008C7E
0x180008c31  xor     r9d, r9d
0x180008c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c39  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180008c40  xor     r9d, r9d
0x180008c43  add     rcx, 30h ; '0'
0x180008c47  xor     edx, edx
0x180008c49  lea     r8d, [r9+2]
0x180008c4d  mov     rax, [rcx]
0x180008c50  mov     rax, [rax+20h]
0x180008c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c59  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180008c60  xor     r9d, r9d
0x180008c63  add     rcx, 30h ; '0'
0x180008c67  xor     edx, edx
0x180008c69  lea     r8d, [r9+5]
0x180008c6d  mov     rax, [rcx]
0x180008c70  mov     rax, [rax+20h]
0x180008c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c79  xor     r9d, r9d
0x180008c7c  jmp     short loc_180008CCF
0x180008c7e  lea     r9, [rbx+3Ch]
0x180008c82  xor     edx, edx
0x180008c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c89  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180008c90  lea     r9, [rbx+40h]
0x180008c94  add     rcx, 30h ; '0'
0x180008c98  xor     edx, edx
0x180008c9a  mov     rax, [rcx]
0x180008c9d  lea     r8d, [rdx+2]
0x180008ca1  mov     rax, [rax+20h]
0x180008ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008caa  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180008cb1  lea     r9, [rbx+44h]
0x180008cb5  add     rcx, 30h ; '0'
0x180008cb9  xor     edx, edx
0x180008cbb  mov     rax, [rcx]
0x180008cbe  lea     r8d, [rdx+5]
0x180008cc2  mov     rax, [rax+20h]
0x180008cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ccb  lea     r9, [rbx+48h]
0x180008ccf  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180008cd6  mov     r8d, 6
0x180008cdc  add     rcx, 30h ; '0'
0x180008ce0  xor     edx, edx
0x180008ce2  mov     rax, [rcx]
0x180008ce5  mov     rax, [rax+20h]
0x180008ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cee  add     rsp, 30h
0x180008cf2  pop     rbx
0x180008cf3  retn
```
