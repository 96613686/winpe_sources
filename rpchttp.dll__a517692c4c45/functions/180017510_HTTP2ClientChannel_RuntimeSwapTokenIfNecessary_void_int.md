# HTTP2ClientChannel::RuntimeSwapTokenIfNecessary(void * *,int *)

- ea: `0x180017510`
- end: `0x180017577`
- name: `?RuntimeSwapTokenIfNecessary@HTTP2ClientChannel@@UEAAJPEAPEAXPEAH@Z`
- size: `103`
- prototype: `__int64 __fastcall(HTTP2ClientChannel *__hidden this, void **, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000f3fc`
- `0x180017510`
- `0x18001ac60`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2ClientChannel::RuntimeSwapTokenIfNecessary(HTTP2ClientChannel *this, void **a2, int *a3)
{
  struct HTTP2VirtualConnection *v6; // rax

  v6 = HTTP2Channel::LockParentPointer(this);
  if ( v6 )
  {
    *a3 = (*((__int64 (__fastcall **)(_QWORD, void **))pRuntimeImportTable + 74))(*((_QWORD *)v6 + 77), a2);
    HTTP2Channel::UnlockParentPointer(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 3221360658LL;
  }
}

```

## disassembly

```asm
0x180017510  mov     [rsp+arg_0], rbx
0x180017515  mov     [rsp+arg_8], rsi
0x18001751a  push    rdi
0x18001751b  sub     rsp, 20h
0x18001751f  mov     rbx, r8
0x180017522  mov     rsi, rdx
0x180017525  mov     rdi, rcx
0x180017528  call    ?LockParentPointer@HTTP2Channel@@QEAAPEAVHTTP2VirtualConnection@@XZ; HTTP2Channel::LockParentPointer(void)
0x18001752d  mov     rcx, rax
0x180017530  test    rax, rax
0x180017533  jnz     short loc_18001753E
0x180017535  mov     [rbx], eax
0x180017537  mov     eax, 0C0021012h
0x18001753c  jmp     short loc_180017567
0x18001753e  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180017545  mov     rdx, rsi
0x180017548  mov     rcx, [rcx+268h]
0x18001754f  mov     rax, [rax+250h]
0x180017556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001755b  mov     rcx, rdi; this
0x18001755e  mov     [rbx], eax
0x180017560  call    ?UnlockParentPointer@HTTP2Channel@@QEAAXXZ; HTTP2Channel::UnlockParentPointer(void)
0x180017565  xor     eax, eax
0x180017567  mov     rbx, [rsp+28h+arg_0]
0x18001756c  mov     rsi, [rsp+28h+arg_8]
0x180017571  add     rsp, 20h
0x180017575  pop     rdi
0x180017576  retn
```
