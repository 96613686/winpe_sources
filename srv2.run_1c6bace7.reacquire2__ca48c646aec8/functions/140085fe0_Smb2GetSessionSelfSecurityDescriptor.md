# Smb2GetSessionSelfSecurityDescriptor

- ea: `0x140085fe0`
- end: `0x140086049`
- name: `Smb2GetSessionSelfSecurityDescriptor`
- size: `105`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f4d0`
- `0x1400200ac`
- `0x14002d904`

## callees

- `0x140015960`
- `0x1400770a0`
- `0x140077390`
- `0x140085fe0`
- `0x140086050`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14009abb5`
- `ntoskrnl!ExAllocatePool2` at `0x14009abb5`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14009ac0f`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14009ac0f`
- `srvnet!SrvNetFreePool` at `0x14009abee`
- `srvnet!SrvNetFreePool` at `0x14009abee`
- `srvnet!SrvLibCreateSelfSD` at `0x14009ab91`
- `srvnet!SrvLibCreateSelfSD` at `0x14009ab91`

## pseudocode

```c
_QWORD *__fastcall Smb2GetSessionSelfSecurityDescriptor(__int64 a1, char a2)
{
  _QWORD *v4; // rdi
  _QWORD *result; // rax
  __int64 SessionSecurityContext; // rax
  __int64 v7; // r14
  __int64 SelfSD; // rbp
  _QWORD *Pool2; // rax

  if ( *(_QWORD *)(a1 + 88) )
  {
    v4 = *(_QWORD **)(a1 + 88);
  }
  else
  {
    v4 = 0;
    SessionSecurityContext = Smb2GetSessionSecurityContext();
    v7 = SessionSecurityContext;
    if ( !SessionSecurityContext )
      return 0;
    if ( a2 == 1 || Smb2ImpersonateSecurityContext(SessionSecurityContext) >= 0 )
    {
      SelfSD = SrvLibCreateSelfSD();
      if ( SelfSD )
      {
        Pool2 = (_QWORD *)ExAllocatePool2(258, 16, 1647465292);
        v4 = Pool2;
        if ( Pool2 )
        {
          *(_DWORD *)Pool2 = 1;
          Pool2[1] = SelfSD;
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 88), (signed __int64)Pool2, 0) )
          {
            Smb2DereferenceSecurityDescriptor(Pool2);
            v4 = *(_QWORD **)(a1 + 88);
          }
        }
        else
        {
          SrvNetFreePool(SelfSD);
        }
      }
      if ( !a2 )
        PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    }
    Smb2DereferenceSecurityContext(v7);
  }
  result = v4;
  if ( v4 )
    _InterlockedIncrement(*(volatile signed __int32 **)(a1 + 88));
  return result;
}

```

## disassembly

```asm
0x140085fe0  push    rbx
0x140085fe2  push    rsi
0x140085fe3  push    rdi
0x140085fe4  push    r14
0x140085fe6  sub     rsp, 28h
0x140085fea  mov     rax, [rcx+58h]
0x140085fee  movzx   esi, dl
0x140085ff1  mov     rbx, rcx
0x140085ff4  test    rax, rax
0x140085ff7  jz      short loc_140086017
0x140085ff9  mov     rdi, [rcx+58h]
0x140085ffd  mov     rax, rdi
0x140086000  test    rdi, rdi
0x140086003  jz      short loc_14008600C
0x140086005  mov     rcx, [rbx+58h]
0x140086009  lock inc dword ptr [rcx]
0x14008600c  add     rsp, 28h
0x140086010  pop     r14
0x140086012  pop     rdi
0x140086013  pop     rsi
0x140086014  pop     rbx
0x140086015  retn
0x140086017  xor     edi, edi
0x140086019  call    Smb2GetSessionSecurityContext
0x14008601e  mov     r14, rax
0x140086021  test    rax, rax
0x140086024  jz      loc_14009AC29
0x14008602a  cmp     sil, 1
0x14008602e  jz      loc_14009AB8C
0x140086034  mov     rcx, rax
0x140086037  call    Smb2ImpersonateSecurityContext
0x14008603c  test    eax, eax
0x14008603e  jns     loc_14009AB8C
0x140086044  jmp     loc_14009AC1B
0x14009ab8c  mov     [rsp+48h+arg_0], rbp
0x14009ab91  call    cs:__imp_SrvLibCreateSelfSD
0x14009ab98  nop     dword ptr [rax+rax+00h]
0x14009ab9d  mov     rbp, rax
0x14009aba0  test    rax, rax
0x14009aba3  jz      short loc_14009ABFA
0x14009aba5  mov     edx, 10h
0x14009abaa  mov     ecx, 102h
0x14009abaf  mov     r8d, 6232534Ch
0x14009abb5  call    cs:__imp_ExAllocatePool2
0x14009abbc  nop     dword ptr [rax+rax+00h]
0x14009abc1  mov     rdi, rax
0x14009abc4  test    rax, rax
0x14009abc7  jz      short loc_14009ABEB
0x14009abc9  mov     dword ptr [rax], 1
0x14009abcf  mov     [rax+8], rbp
0x14009abd3  xor     eax, eax
0x14009abd5  lock cmpxchg [rbx+58h], rdi
0x14009abdb  jz      short loc_14009ABFA
0x14009abdd  mov     rcx, rdi; P
0x14009abe0  call    Smb2DereferenceSecurityDescriptor
0x14009abe5  mov     rdi, [rbx+58h]
0x14009abe9  jmp     short loc_14009ABFA
0x14009abeb  mov     rcx, rbp
0x14009abee  call    cs:__imp_SrvNetFreePool
0x14009abf5  nop     dword ptr [rax+rax+00h]
0x14009abfa  mov     rbp, [rsp+48h+arg_0]
0x14009abff  test    sil, sil
0x14009ac02  jnz     short loc_14009AC1B
0x14009ac04  mov     rcx, gs:188h; Thread
0x14009ac0d  xor     edx, edx; Token
0x14009ac0f  call    cs:__imp_PsAssignImpersonationToken
0x14009ac16  nop     dword ptr [rax+rax+00h]
0x14009ac1b  mov     rcx, r14
0x14009ac1e  call    Smb2DereferenceSecurityContext
0x14009ac23  nop
0x14009ac24  jmp     loc_140085FFD
0x14009ac29  mov     rax, rdi
0x14009ac2c  jmp     loc_14008600C
```
