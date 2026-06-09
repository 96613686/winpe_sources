# Smb2GetSessionSelfSecurityDescriptor

- ea: `0x140085f90`
- end: `0x140085ff9`
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
- `0x140077050`
- `0x140077340`
- `0x140085f90`
- `0x140086000`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14009ab65`
- `ntoskrnl!ExAllocatePool2` at `0x14009ab65`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14009abbf`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14009abbf`
- `srvnet!SrvNetFreePool` at `0x14009ab9e`
- `srvnet!SrvNetFreePool` at `0x14009ab9e`
- `srvnet!SrvLibCreateSelfSD` at `0x14009ab41`
- `srvnet!SrvLibCreateSelfSD` at `0x14009ab41`

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
0x140085f90  push    rbx
0x140085f92  push    rsi
0x140085f93  push    rdi
0x140085f94  push    r14
0x140085f96  sub     rsp, 28h
0x140085f9a  mov     rax, [rcx+58h]
0x140085f9e  movzx   esi, dl
0x140085fa1  mov     rbx, rcx
0x140085fa4  test    rax, rax
0x140085fa7  jz      short loc_140085FC7
0x140085fa9  mov     rdi, [rcx+58h]
0x140085fad  mov     rax, rdi
0x140085fb0  test    rdi, rdi
0x140085fb3  jz      short loc_140085FBC
0x140085fb5  mov     rcx, [rbx+58h]
0x140085fb9  lock inc dword ptr [rcx]
0x140085fbc  add     rsp, 28h
0x140085fc0  pop     r14
0x140085fc2  pop     rdi
0x140085fc3  pop     rsi
0x140085fc4  pop     rbx
0x140085fc5  retn
0x140085fc7  xor     edi, edi
0x140085fc9  call    Smb2GetSessionSecurityContext
0x140085fce  mov     r14, rax
0x140085fd1  test    rax, rax
0x140085fd4  jz      loc_14009ABD9
0x140085fda  cmp     sil, 1
0x140085fde  jz      loc_14009AB3C
0x140085fe4  mov     rcx, rax
0x140085fe7  call    Smb2ImpersonateSecurityContext
0x140085fec  test    eax, eax
0x140085fee  jns     loc_14009AB3C
0x140085ff4  jmp     loc_14009ABCB
0x14009ab3c  mov     [rsp+48h+arg_0], rbp
0x14009ab41  call    cs:__imp_SrvLibCreateSelfSD
0x14009ab48  nop     dword ptr [rax+rax+00h]
0x14009ab4d  mov     rbp, rax
0x14009ab50  test    rax, rax
0x14009ab53  jz      short loc_14009ABAA
0x14009ab55  mov     edx, 10h
0x14009ab5a  mov     ecx, 102h
0x14009ab5f  mov     r8d, 6232534Ch
0x14009ab65  call    cs:__imp_ExAllocatePool2
0x14009ab6c  nop     dword ptr [rax+rax+00h]
0x14009ab71  mov     rdi, rax
0x14009ab74  test    rax, rax
0x14009ab77  jz      short loc_14009AB9B
0x14009ab79  mov     dword ptr [rax], 1
0x14009ab7f  mov     [rax+8], rbp
0x14009ab83  xor     eax, eax
0x14009ab85  lock cmpxchg [rbx+58h], rdi
0x14009ab8b  jz      short loc_14009ABAA
0x14009ab8d  mov     rcx, rdi; P
0x14009ab90  call    Smb2DereferenceSecurityDescriptor
0x14009ab95  mov     rdi, [rbx+58h]
0x14009ab99  jmp     short loc_14009ABAA
0x14009ab9b  mov     rcx, rbp
0x14009ab9e  call    cs:__imp_SrvNetFreePool
0x14009aba5  nop     dword ptr [rax+rax+00h]
0x14009abaa  mov     rbp, [rsp+48h+arg_0]
0x14009abaf  test    sil, sil
0x14009abb2  jnz     short loc_14009ABCB
0x14009abb4  mov     rcx, gs:188h; Thread
0x14009abbd  xor     edx, edx; Token
0x14009abbf  call    cs:__imp_PsAssignImpersonationToken
0x14009abc6  nop     dword ptr [rax+rax+00h]
0x14009abcb  mov     rcx, r14
0x14009abce  call    Smb2DereferenceSecurityContext
0x14009abd3  nop
0x14009abd4  jmp     loc_140085FAD
0x14009abd9  mov     rax, rdi
0x14009abdc  jmp     loc_140085FBC
```
