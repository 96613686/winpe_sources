# WinHvDeleteTdMigrationBundle

- ea: `0x140024670`
- end: `0x1400246ea`
- name: `WinHvDeleteTdMigrationBundle`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400243d0`

## callees

- `0x140002240`
- `0x140003610`
- `0x140009c90`
- `0x14000a040`

## pseudocode

```c
__int64 __fastcall WinHvDeleteTdMigrationBundle(__int64 a1, __int64 a2)
{
  __int64 *v4; // rax
  _QWORD v6[9]; // [rsp+20h] [rbp-48h] BYREF
  __int64 *v7; // [rsp+70h] [rbp+8h] BYREF

  v7 = 0;
  memset(v6, 0, 0x40u);
  WinHvpSetupHypercall(&v7, 0, (__int64)v6);
  v4 = v7;
  *(_OWORD *)v7 = 0;
  *v4 = a1;
  v4[1] = a2;
  LODWORD(a1) = WinHvpSimplePoolHypercall_CallViaMacro(v6[0], 313);
  ((void (__fastcall *)(_QWORD))v6[7])(v6[0]);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x140024670  mov     [rsp+arg_8], rbx
0x140024675  push    rdi
0x140024676  sub     rsp, 60h
0x14002467a  mov     rdi, rdx
0x14002467d  mov     [rsp+68h+arg_0], 0
0x140024686  xor     edx, edx; Val
0x140024688  mov     rbx, rcx
0x14002468b  lea     rcx, [rsp+68h+var_48]; void *
0x140024690  lea     r8d, [rdx+40h]; Size
0x140024694  call    memset
0x140024699  lea     r8, [rsp+68h+var_48]
0x14002469e  xor     edx, edx
0x1400246a0  lea     rcx, [rsp+68h+arg_0]
0x1400246a5  call    WinHvpSetupHypercall
0x1400246aa  mov     rax, [rsp+68h+arg_0]
0x1400246af  xorps   xmm0, xmm0
0x1400246b2  mov     edx, 139h
0x1400246b7  movups  xmmword ptr [rax], xmm0
0x1400246ba  mov     [rax], rbx
0x1400246bd  mov     [rax+8], rdi
0x1400246c1  mov     rcx, [rsp+68h+var_48]
0x1400246c6  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400246cb  mov     rcx, [rsp+68h+var_48]
0x1400246d0  mov     ebx, eax
0x1400246d2  mov     rax, [rsp+68h+var_10]
0x1400246d7  call    _guard_dispatch_icall
0x1400246dc  mov     eax, ebx
0x1400246de  mov     rbx, [rsp+68h+arg_8]
0x1400246e3  add     rsp, 60h
0x1400246e7  pop     rdi
0x1400246e8  retn
```
