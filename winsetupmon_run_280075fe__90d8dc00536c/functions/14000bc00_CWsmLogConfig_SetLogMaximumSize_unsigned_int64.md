# CWsmLogConfig::SetLogMaximumSize(unsigned __int64)

- ea: `0x14000bc00`
- end: `0x14000bc53`
- name: `?SetLogMaximumSize@CWsmLogConfig@@UEAAJ_K@Z`
- size: `83`
- prototype: `__int64 __fastcall(CWsmLogConfig *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x14000bc60`

## callees

- `0x14000bb50`
- `0x14000bc00`
- `0x14000f9e0`

## pseudocode

```c
__int64 __fastcall CWsmLogConfig::SetLogMaximumSize(__int64 (__fastcall ***this)(CWsmLogConfig *), __int64 a2)
{
  __int64 (__fastcall **v2)(CWsmLogConfig *); // rax
  __int128 *v5; // rax
  __int128 v7; // [rsp+20h] [rbp-18h] BYREF

  v2 = *this;
  *(_QWORD *)&v7 = 0;
  v5 = (__int128 *)(*v2)((CWsmLogConfig *)this);
  if ( v5 )
    v7 = *v5;
  *((_QWORD *)&v7 + 1) = a2;
  return CWsmLogConfig::Reset((CWsmLogConfig *)this, (const unsigned __int16 **)&v7, 1);
}

```

## disassembly

```asm
0x14000bc00  mov     [rsp+arg_0], rbx
0x14000bc05  push    rdi
0x14000bc06  sub     rsp, 30h
0x14000bc0a  mov     rax, [rcx]
0x14000bc0d  mov     rdi, rdx
0x14000bc10  mov     rbx, rcx
0x14000bc13  mov     qword ptr [rsp+38h+var_18], 0
0x14000bc1c  mov     rax, [rax]
0x14000bc1f  call    _guard_dispatch_icall
0x14000bc24  test    rax, rax
0x14000bc27  jz      short loc_14000BC32
0x14000bc29  movups  xmm0, xmmword ptr [rax]
0x14000bc2c  movdqu  [rsp+38h+var_18], xmm0
0x14000bc32  mov     r8b, 1; bool
0x14000bc35  mov     qword ptr [rsp+38h+var_18+8], rdi
0x14000bc3a  lea     rdx, [rsp+38h+var_18]; struct _WSM_LOG_CONFIG *
0x14000bc3f  mov     rcx, rbx; this
0x14000bc42  call    ?Reset@CWsmLogConfig@@IEAAJQEAU_WSM_LOG_CONFIG@@_N@Z; CWsmLogConfig::Reset(_WSM_LOG_CONFIG * const,bool)
0x14000bc47  mov     rbx, [rsp+38h+arg_0]
0x14000bc4c  add     rsp, 30h
0x14000bc50  pop     rdi
0x14000bc51  retn
```
