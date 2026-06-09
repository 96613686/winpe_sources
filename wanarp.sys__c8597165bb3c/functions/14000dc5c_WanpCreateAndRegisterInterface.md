# WanpCreateAndRegisterInterface

- ea: `0x14000dc5c`
- end: `0x14000ddc8`
- name: `WanpCreateAndRegisterInterface`
- size: `364`
- prototype: `__int64 __fastcall(_OWORD *, const UNICODE_STRING *, _QWORD *, int, __int64, char, unsigned int, volatile signed __int32 **, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140011618`

## callees

- `0x14000d090`
- `0x14000d1c0`
- `0x14000d8c4`
- `0x14000dc5c`
- `0x14000ddd0`
- `0x14000ef18`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000dd94`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ddaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dd94`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ddaa`

## pseudocode

```c
__int64 __fastcall WanpCreateAndRegisterInterface(
        _OWORD *a1,
        const UNICODE_STRING *a2,
        _QWORD *a3,
        int a4,
        __int64 a5,
        char a6,
        unsigned int a7,
        volatile signed __int32 **a8,
        _QWORD *a9)
{
  __int64 v10; // rdi
  char AdapterFromDeviceGuid; // al
  __int64 v15; // rcx
  __int64 v16; // r8
  volatile signed __int32 *v17; // rbx
  char v19; // bp
  int v20; // eax
  int v21; // esi
  int InterfaceContext; // eax
  PVOID P; // [rsp+30h] [rbp-48h] BYREF
  __int64 v24[8]; // [rsp+38h] [rbp-40h] BYREF

  P = 0;
  v10 = 0;
  v24[0] = 0;
  AdapterFromDeviceGuid = GetAdapterFromDeviceGuid(a1, &P);
  v17 = (volatile signed __int32 *)P;
  if ( AdapterFromDeviceGuid )
  {
    LOBYTE(v15) = a6;
    if ( (unsigned __int8)IsBindingPresent(v15, P) )
      return 3221225485LL;
  }
  if ( v17 )
  {
    v19 = 1;
  }
  else
  {
    v19 = 0;
    v20 = WanpCreateAdapterContext(a1, a2, v16, &P);
    v17 = (volatile signed __int32 *)P;
    v21 = v20;
    if ( v20 < 0 )
    {
LABEL_14:
      if ( v17 && !v19 )
        ExFreePoolWithTag((PVOID)v17, 0);
      if ( v10 )
        ExFreePoolWithTag((PVOID)v10, 0);
      return (unsigned int)v21;
    }
  }
  LOBYTE(v15) = a6;
  InterfaceContext = WanpCreateInterfaceContext(v15, a4, v16, a7, (__int64)v24);
  v10 = v24[0];
  v21 = InterfaceContext;
  if ( InterfaceContext < 0 )
    goto LABEL_14;
  *((_QWORD *)v17 + 44) = *a3;
  if ( v19 != 1 )
  {
    v21 = WanpRegisterInterface(a7, a2, v17, v10);
    if ( v21 < 0 )
      goto LABEL_14;
  }
  *((_QWORD *)v17 + 44) = *a3;
  *(_QWORD *)(v10 + 24) = v17;
  _InterlockedIncrement(v17 + 32);
  if ( a6 )
    *((_QWORD *)v17 + 21) = v10;
  else
    *((_QWORD *)v17 + 22) = v10;
  _InterlockedIncrement((volatile signed __int32 *)(v10 + 64));
  *a8 = v17;
  *a9 = v10;
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x14000dc5c  push    rbx
0x14000dc5e  push    rbp
0x14000dc5f  push    rsi
0x14000dc60  push    rdi
0x14000dc61  push    r12
0x14000dc63  push    r13
0x14000dc65  push    r15
0x14000dc67  sub     rsp, 40h
0x14000dc6b  mov     r12, rdx
0x14000dc6e  mov     [rsp+78h+P], 0
0x14000dc77  xor     edi, edi
0x14000dc79  lea     rdx, [rsp+78h+P]
0x14000dc7e  mov     [rsp+78h+var_40], rdi
0x14000dc83  mov     r13d, r9d
0x14000dc86  mov     r15, r8
0x14000dc89  mov     rsi, rcx
0x14000dc8c  call    GetAdapterFromDeviceGuid
0x14000dc91  mov     rbx, [rsp+78h+P]
0x14000dc96  test    al, al
0x14000dc98  jz      short loc_14000DCB7
0x14000dc9a  mov     cl, [rsp+78h+arg_28]
0x14000dca1  mov     rdx, rbx
0x14000dca4  call    IsBindingPresent
0x14000dca9  test    al, al
0x14000dcab  jz      short loc_14000DCB7
0x14000dcad  mov     eax, 0C000000Dh
0x14000dcb2  jmp     loc_14000DDB8
0x14000dcb7  test    rbx, rbx
0x14000dcba  jz      short loc_14000DCC1
0x14000dcbc  mov     bpl, 1
0x14000dcbf  jmp     short loc_14000DCE3
0x14000dcc1  lea     r9, [rsp+78h+P]
0x14000dcc6  mov     rdx, r12
0x14000dcc9  mov     rcx, rsi
0x14000dccc  xor     bpl, bpl
0x14000dccf  call    WanpCreateAdapterContext
0x14000dcd4  mov     rbx, [rsp+78h+P]
0x14000dcd9  mov     esi, eax
0x14000dcdb  test    eax, eax
0x14000dcdd  js      loc_14000DD85
0x14000dce3  mov     r9d, [rsp+78h+arg_30]
0x14000dceb  lea     rax, [rsp+78h+var_40]
0x14000dcf0  mov     cl, [rsp+78h+arg_28]
0x14000dcf7  mov     edx, r13d
0x14000dcfa  mov     [rsp+78h+var_58], rax
0x14000dcff  call    WanpCreateInterfaceContext
0x14000dd04  mov     rdi, [rsp+78h+var_40]
0x14000dd09  mov     esi, eax
0x14000dd0b  test    eax, eax
0x14000dd0d  js      short loc_14000DD85
0x14000dd0f  mov     rax, [r15]
0x14000dd12  mov     [rbx+160h], rax
0x14000dd19  cmp     bpl, 1
0x14000dd1d  jz      short loc_14000DD3A
0x14000dd1f  mov     ecx, [rsp+78h+arg_30]
0x14000dd26  mov     r9, rdi
0x14000dd29  mov     r8, rbx
0x14000dd2c  mov     rdx, r12
0x14000dd2f  call    WanpRegisterInterface
0x14000dd34  mov     esi, eax
0x14000dd36  test    eax, eax
0x14000dd38  js      short loc_14000DD85
0x14000dd3a  mov     rax, [r15]
0x14000dd3d  mov     [rbx+160h], rax
0x14000dd44  mov     [rdi+18h], rbx
0x14000dd48  lock inc dword ptr [rbx+80h]
0x14000dd4f  cmp     [rsp+78h+arg_28], 0
0x14000dd57  jz      short loc_14000DD62
0x14000dd59  mov     [rbx+0A8h], rdi
0x14000dd60  jmp     short loc_14000DD69
0x14000dd62  mov     [rbx+0B0h], rdi
0x14000dd69  lock inc dword ptr [rdi+40h]
0x14000dd6d  mov     rax, [rsp+78h+arg_38]
0x14000dd75  mov     [rax], rbx
0x14000dd78  mov     rax, [rsp+78h+arg_40]
0x14000dd80  mov     [rax], rdi
0x14000dd83  jmp     short loc_14000DDB6
0x14000dd85  test    rbx, rbx
0x14000dd88  jz      short loc_14000DDA0
0x14000dd8a  test    bpl, bpl
0x14000dd8d  jnz     short loc_14000DDA0
0x14000dd8f  xor     edx, edx; Tag
0x14000dd91  mov     rcx, rbx; P
0x14000dd94  call    cs:__imp_ExFreePoolWithTag
0x14000dd9b  nop     dword ptr [rax+rax+00h]
0x14000dda0  test    rdi, rdi
0x14000dda3  jz      short loc_14000DDB6
0x14000dda5  xor     edx, edx; Tag
0x14000dda7  mov     rcx, rdi; P
0x14000ddaa  call    cs:__imp_ExFreePoolWithTag
0x14000ddb1  nop     dword ptr [rax+rax+00h]
0x14000ddb6  mov     eax, esi
0x14000ddb8  add     rsp, 40h
0x14000ddbc  pop     r15
0x14000ddbe  pop     r13
0x14000ddc0  pop     r12
0x14000ddc2  pop     rdi
0x14000ddc3  pop     rsi
0x14000ddc4  pop     rbp
0x14000ddc5  pop     rbx
0x14000ddc6  retn
```
