# CWsmLogConfig::SetLogStablePath(ushort const *)

- ea: `0x14000bf50`
- end: `0x14000bfaf`
- name: `?SetLogStablePath@CWsmLogConfig@@UEAAJPEBG@Z`
- size: `95`
- prototype: `__int64 __fastcall(CWsmLogConfig *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14000bb50`
- `0x14000bf50`
- `0x14000f9e0`

## pseudocode

```c
__int64 __fastcall CWsmLogConfig::SetLogStablePath(
        __int64 (__fastcall ***this)(CWsmLogConfig *),
        const unsigned __int16 *a2)
{
  __int64 (__fastcall **v5)(CWsmLogConfig *); // rax
  __int128 *v6; // rax
  __int128 v7; // [rsp+20h] [rbp-18h] BYREF

  if ( !a2 )
    return 3221225485LL;
  v5 = *this;
  *((_QWORD *)&v7 + 1) = 0;
  v6 = (__int128 *)(*v5)((CWsmLogConfig *)this);
  if ( v6 )
    v7 = *v6;
  *(_QWORD *)&v7 = a2;
  return CWsmLogConfig::Reset((CWsmLogConfig *)this, (const unsigned __int16 **)&v7, 1);
}

```

## disassembly

```asm
0x14000bf50  mov     [rsp+arg_0], rbx
0x14000bf55  push    rdi
0x14000bf56  sub     rsp, 30h
0x14000bf5a  mov     rdi, rdx
0x14000bf5d  mov     rbx, rcx
0x14000bf60  test    rdx, rdx
0x14000bf63  jnz     short loc_14000BF6C
0x14000bf65  mov     eax, 0C000000Dh
0x14000bf6a  jmp     short loc_14000BFA3
0x14000bf6c  mov     rax, [rcx]
0x14000bf6f  mov     [rsp+38h+var_10], 0
0x14000bf78  mov     rax, [rax]
0x14000bf7b  call    _guard_dispatch_icall
0x14000bf80  test    rax, rax
0x14000bf83  jz      short loc_14000BF8E
0x14000bf85  movups  xmm0, xmmword ptr [rax]
0x14000bf88  movdqu  xmmword ptr [rsp+20h], xmm0
0x14000bf8e  mov     r8b, 1; bool
0x14000bf91  mov     [rsp+38h+var_18], rdi
0x14000bf96  lea     rdx, [rsp+38h+var_18]; struct _WSM_LOG_CONFIG *
0x14000bf9b  mov     rcx, rbx; this
0x14000bf9e  call    ?Reset@CWsmLogConfig@@IEAAJQEAU_WSM_LOG_CONFIG@@_N@Z; CWsmLogConfig::Reset(_WSM_LOG_CONFIG * const,bool)
0x14000bfa3  mov     rbx, [rsp+38h+arg_0]
0x14000bfa8  add     rsp, 30h
0x14000bfac  pop     rdi
0x14000bfad  retn
```
