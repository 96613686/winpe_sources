# `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x1800038c0`
- end: `0x180003942`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z`
- size: `130`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800038c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800038d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800038d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003931`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003931`

## pseudocode

```c
void __fastcall `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_(
        __int64 a1)
{
  RTL_SRWLOCK *v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rcx
  int v5; // ecx

  if ( *(_BYTE *)a1 )
  {
    v2 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    v3 = *(_QWORD *)(a1 + 80);
    v4 = *(_QWORD *)(a1 + 88);
    while ( v3 != v4 )
    {
      _InterlockedAnd(*(volatile signed __int32 **)(v3 + 8), *(_DWORD *)v3 != 0 ? -5 : -2111);
      v3 += 16;
    }
    v5 = 1;
    *(_QWORD *)(a1 + 88) = *(_QWORD *)(a1 + 80);
    if ( *(_DWORD *)(a1 + 28) != -1 )
      v5 = *(_DWORD *)(a1 + 28) + 1;
    *(_DWORD *)(a1 + 28) = v5;
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
  }
}

```

## disassembly

```asm
0x1800038c0  mov     [rsp+arg_8], rbx
0x1800038c5  push    rdi
0x1800038c6  sub     rsp, 20h
0x1800038ca  cmp     byte ptr [rcx], 0
0x1800038cd  mov     rdi, rcx
0x1800038d0  jz      short loc_180003937
0x1800038d2  lea     rbx, [rcx+8]
0x1800038d6  mov     rcx, rbx; SRWLock
0x1800038d9  call    cs:__imp_AcquireSRWLockExclusive
0x1800038df  mov     rax, [rdi+50h]
0x1800038e3  mov     rcx, [rdi+58h]
0x1800038e7  jmp     short loc_18000390A
0x1800038e9  mov     edx, [rax]
0x1800038eb  neg     edx
0x1800038ed  mov     rdx, [rax+8]
0x1800038f1  sbb     r8d, r8d
0x1800038f4  and     r8d, 83Ah
0x1800038fb  add     r8d, 0FFFFF7C1h
0x180003902  lock and [rdx], r8d
0x180003906  add     rax, 10h
0x18000390a  cmp     rax, rcx
0x18000390d  jnz     short loc_1800038E9
0x18000390f  mov     rax, [rdi+50h]
0x180003913  mov     ecx, 1
0x180003918  mov     [rdi+58h], rax
0x18000391c  mov     eax, [rdi+1Ch]
0x18000391f  nop
0x180003920  add     eax, 1
0x180003923  cmovnz  ecx, eax
0x180003926  mov     [rdi+1Ch], ecx
0x180003929  test    rbx, rbx
0x18000392c  jz      short loc_180003937
0x18000392e  mov     rcx, rbx; SRWLock
0x180003931  call    cs:__imp_ReleaseSRWLockExclusive
0x180003937  mov     rbx, [rsp+28h+arg_8]
0x18000393c  add     rsp, 20h
0x180003940  pop     rdi
0x180003941  retn
```
