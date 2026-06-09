# wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x18001ba9c`
- end: `0x18001bb21`
- name: `?LockExclusive@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `133`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001bc80`
- `0x18001c0f4`
- `0x18001c41c`
- `0x1800252c0`
- `0x180027148`

## callees

- `0x18001ba9c`
- `0x18001c1c8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18001bac4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001bac4`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        __int64 a1,
        RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v4; // rbx
  char *v5; // rax
  int v6; // ecx
  int v7; // esi
  char v9; // [rsp+30h] [rbp+8h] BYREF
  char v10; // [rsp+38h] [rbp+10h] BYREF

  v2 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v2 )
  {
    v4 = v2 + 33;
    AcquireSRWLockExclusive(v4);
    v5 = &v10;
    v6 = 0;
    v7 = 1;
  }
  else
  {
    v4 = 0;
    v5 = &v9;
    v7 = 0;
    v6 = 2;
  }
  *a2 = v4;
  *(_QWORD *)v5 = 0;
  if ( v6 )
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  if ( v7 )
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  return a2;
}

```

## disassembly

```asm
0x18001ba9c  mov     [rsp+arg_10], rbx
0x18001baa1  mov     [rsp+arg_18], rsi
0x18001baa6  push    rdi
0x18001baa7  sub     rsp, 20h
0x18001baab  mov     rbx, [rcx+118h]
0x18001bab2  mov     rdi, rdx
0x18001bab5  test    rbx, rbx
0x18001bab8  jz      short loc_18001BAFB
0x18001baba  add     rbx, 108h
0x18001bac1  mov     rcx, rbx; SRWLock
0x18001bac4  call    cs:__imp_AcquireSRWLockExclusive
0x18001baca  lea     rax, [rsp+28h+arg_8]
0x18001bacf  xor     ecx, ecx
0x18001bad1  mov     esi, 1
0x18001bad6  mov     [rdi], rbx
0x18001bad9  mov     qword ptr [rax], 0
0x18001bae0  test    ecx, ecx
0x18001bae2  jnz     short loc_18001BB09
0x18001bae4  test    esi, esi
0x18001bae6  jnz     short loc_18001BB15
0x18001bae8  mov     rbx, [rsp+28h+arg_10]
0x18001baed  mov     rax, rdi
0x18001baf0  mov     rsi, [rsp+28h+arg_18]
0x18001baf5  add     rsp, 20h
0x18001baf9  pop     rdi
0x18001bafa  retn
0x18001bafb  xor     ebx, ebx
0x18001bafd  lea     rax, [rsp+28h+arg_0]
0x18001bb02  xor     esi, esi
0x18001bb04  lea     ecx, [rbx+2]
0x18001bb07  jmp     short loc_18001BAD6
0x18001bb09  lea     rcx, [rsp+28h+arg_0]
0x18001bb0e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001bb13  jmp     short loc_18001BAE4
0x18001bb15  lea     rcx, [rsp+28h+arg_8]
0x18001bb1a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001bb1f  jmp     short loc_18001BAE8
```
