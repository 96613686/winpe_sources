# TdxShutdownEndpointConnection

- ea: `0x14000f4f0`
- end: `0x14000f63e`
- name: `TdxShutdownEndpointConnection`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400012b0`
- `0x1400023b0`
- `0x140002fb0`
- `0x140003c9c`
- `0x140005b00`
- `0x140006db0`
- `0x1400075b0`
- `0x140008620`
- `0x140009ad0`
- `0x14000aad0`
- `0x140017ad0`

## callees

- `0x1400043b0`
- `0x14000f4f0`
- `0x14001303c`
- `0x140018590`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000f533`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f5ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f5fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f628`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f533`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f5ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f5fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f628`

## pseudocode

```c
__int64 __fastcall TdxShutdownEndpointConnection(__int64 a1, KIRQL a2)
{
  unsigned int v4; // r8d
  unsigned int v5; // eax
  KSPIN_LOCK *v7; // rcx
  __int64 v8; // rcx
  __int64 (__fastcall **v9)(__int64, __int128 *); // rax
  NTSTATUS v10; // eax
  __int128 v11; // [rsp+30h] [rbp-18h] BYREF

  v11 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_sq(
      WPP_GLOBAL_Control->AttachedDevice,
      54,
      (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
      (unsigned int)"TdxShutdownEndpointConnection",
      a1);
  }
  v4 = *(_DWORD *)a1;
  if ( (*(_DWORD *)a1 & 0x80u) == 0 && (v5 = *(_DWORD *)(a1 + 76), v5 > 1) )
  {
    v7 = (KSPIN_LOCK *)(a1 + 8);
    if ( v5 - 2 <= 1 )
    {
      *(_DWORD *)a1 = v4 | 0x40;
      KeReleaseSpinLock(v7, a2);
      return 259;
    }
    else if ( *(_DWORD *)(a1 + 72) == ((*(_DWORD *)a1 & 0x200) == 0) )
    {
      *(_DWORD *)a1 = v4 | 0x80;
      KeReleaseSpinLock(v7, a2);
      v8 = *(_QWORD *)(a1 + 288);
      *(_QWORD *)&v11 = TdxCloseConnectionEndpointTlRequestComplete;
      v9 = *(__int64 (__fastcall ***)(__int64, __int128 *))(a1 + 264);
      *((_QWORD *)&v11 + 1) = a1;
      v10 = (*v9)(v8, &v11);
      if ( v10 != 259 )
        TdxCloseConnectionEndpointTlRequestComplete((unsigned int *)a1, v10);
      return 259;
    }
    else
    {
      KeReleaseSpinLock(v7, a2);
      return 3221226043LL;
    }
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), a2);
    return 0;
  }
}

```

## disassembly

```asm
0x14000f4f0  mov     [rsp+arg_0], rbx
0x14000f4f5  push    rdi
0x14000f4f6  sub     rsp, 40h
0x14000f4fa  xorps   xmm0, xmm0
0x14000f4fd  movzx   edi, dl
0x14000f500  movups  [rsp+48h+var_18], xmm0
0x14000f505  mov     rbx, rcx
0x14000f508  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f50f  lea     rax, WPP_GLOBAL_Control
0x14000f516  cmp     rcx, rax
0x14000f519  jnz     short loc_14000F54D
0x14000f51b  mov     r8d, [rbx]
0x14000f51e  test    r8b, r8b
0x14000f521  js      short loc_14000F52B
0x14000f523  mov     eax, [rbx+4Ch]
0x14000f526  cmp     eax, 1
0x14000f529  ja      short loc_14000F57F
0x14000f52b  lea     rcx, [rbx+8]; SpinLock
0x14000f52f  movzx   edx, dil; NewIrql
0x14000f533  call    cs:__imp_KeReleaseSpinLock
0x14000f53a  nop     dword ptr [rax+rax+00h]
0x14000f53f  xor     eax, eax
0x14000f541  mov     rbx, [rsp+48h+arg_0]
0x14000f546  add     rsp, 40h
0x14000f54a  pop     rdi
0x14000f54b  retn
0x14000f54d  cmp     byte ptr [rcx+29h], 4
0x14000f551  jb      short loc_14000F51B
0x14000f553  test    dword ptr [rcx+2Ch], 200h
0x14000f55a  jz      short loc_14000F51B
0x14000f55c  mov     rcx, [rcx+18h]
0x14000f560  lea     r9, aTdxshutdownend; "TdxShutdownEndpointConnection"
0x14000f567  mov     edx, 36h ; '6'
0x14000f56c  mov     [rsp+48h+var_28], rbx
0x14000f571  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x14000f578  call    WPP_SF_sq
0x14000f57d  jmp     short loc_14000F51B
0x14000f57f  add     eax, 0FFFFFFFEh
0x14000f582  lea     rcx, [rbx+8]; SpinLock
0x14000f586  cmp     eax, 1
0x14000f589  jbe     loc_14000F61D
0x14000f58f  mov     edx, r8d
0x14000f592  shr     edx, 9
0x14000f595  not     edx
0x14000f597  and     edx, 1
0x14000f59a  cmp     [rbx+48h], edx
0x14000f59d  movzx   edx, dil; NewIrql
0x14000f5a1  jnz     short loc_14000F5FB
0x14000f5a3  bts     r8d, 7
0x14000f5a8  mov     [rbx], r8d
0x14000f5ab  call    cs:__imp_KeReleaseSpinLock
0x14000f5b2  nop     dword ptr [rax+rax+00h]
0x14000f5b7  mov     rcx, [rbx+120h]
0x14000f5be  lea     rax, TdxCloseConnectionEndpointTlRequestComplete
0x14000f5c5  mov     qword ptr [rsp+48h+var_18], rax
0x14000f5ca  lea     rdx, [rsp+48h+var_18]
0x14000f5cf  mov     rax, [rbx+108h]
0x14000f5d6  mov     qword ptr [rsp+48h+var_18+8], rbx
0x14000f5db  mov     rax, [rax]
0x14000f5de  call    _guard_dispatch_icall
0x14000f5e3  cmp     eax, 103h
0x14000f5e8  jnz     short loc_14000F611
0x14000f5ea  mov     rbx, [rsp+48h+arg_0]
0x14000f5ef  mov     eax, 103h
0x14000f5f4  add     rsp, 40h
0x14000f5f8  pop     rdi
0x14000f5f9  retn
0x14000f5fb  call    cs:__imp_KeReleaseSpinLock
0x14000f602  nop     dword ptr [rax+rax+00h]
0x14000f607  mov     eax, 0C000023Bh
0x14000f60c  jmp     loc_14000F541
0x14000f611  mov     edx, eax
0x14000f613  mov     rcx, rbx
0x14000f616  call    TdxCloseConnectionEndpointTlRequestComplete
0x14000f61b  jmp     short loc_14000F5EA
0x14000f61d  or      r8d, 40h
0x14000f621  movzx   edx, dil; NewIrql
0x14000f625  mov     [rbx], r8d
0x14000f628  call    cs:__imp_KeReleaseSpinLock
0x14000f62f  nop     dword ptr [rax+rax+00h]
0x14000f634  mov     eax, 103h
0x14000f639  jmp     loc_14000F541
```
