# CWsmLogConfig::SetLogPath(ushort const *)

- ea: `0x14000bc70`
- end: `0x14000bcd3`
- name: `?SetLogPath@CWsmLogConfig@@UEAAJPEBG@Z`
- size: `99`
- prototype: `__int64 __fastcall(CWsmLogConfig *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14000bb50`
- `0x14000bc70`
- `0x14000f9e0`

## pseudocode

```c
__int64 __fastcall CWsmLogConfig::SetLogPath(__int64 (__fastcall ***this)(char *), const unsigned __int16 *a2)
{
  CWsmLogConfig *v4; // rdi
  __int128 *v5; // rax
  __int128 v6; // [rsp+20h] [rbp-18h] BYREF

  if ( !a2 )
    return 3221225485LL;
  v4 = (CWsmLogConfig *)(this - 1);
  *((_QWORD *)&v6 + 1) = 0;
  v5 = (__int128 *)(**(this - 1))((char *)this - 8);
  if ( v5 )
    v6 = *v5;
  *(_QWORD *)&v6 = a2;
  return CWsmLogConfig::Reset(v4, (const unsigned __int16 **)&v6, 0);
}

```

## disassembly

```asm
0x14000bc70  mov     [rsp+arg_0], rbx
0x14000bc75  push    rdi
0x14000bc76  sub     rsp, 30h
0x14000bc7a  mov     rbx, rdx
0x14000bc7d  test    rdx, rdx
0x14000bc80  jnz     short loc_14000BC89
0x14000bc82  mov     eax, 0C000000Dh
0x14000bc87  jmp     short loc_14000BCC7
0x14000bc89  lea     rdi, [rcx-8]
0x14000bc8d  mov     [rsp+38h+var_10], 0
0x14000bc96  mov     rax, [rdi]
0x14000bc99  mov     rcx, rdi
0x14000bc9c  mov     rax, [rax]
0x14000bc9f  call    _guard_dispatch_icall
0x14000bca4  test    rax, rax
0x14000bca7  jz      short loc_14000BCB2
0x14000bca9  movups  xmm0, xmmword ptr [rax]
0x14000bcac  movdqu  xmmword ptr [rsp+20h], xmm0
0x14000bcb2  xor     r8d, r8d; bool
0x14000bcb5  mov     [rsp+38h+var_18], rbx
0x14000bcba  lea     rdx, [rsp+38h+var_18]; struct _WSM_LOG_CONFIG *
0x14000bcbf  mov     rcx, rdi; this
0x14000bcc2  call    ?Reset@CWsmLogConfig@@IEAAJQEAU_WSM_LOG_CONFIG@@_N@Z; CWsmLogConfig::Reset(_WSM_LOG_CONFIG * const,bool)
0x14000bcc7  mov     rbx, [rsp+38h+arg_0]
0x14000bccc  add     rsp, 30h
0x14000bcd0  pop     rdi
0x14000bcd1  retn
```
