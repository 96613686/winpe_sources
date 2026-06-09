# CryptStream::GetChannelBindingToken(_SecPkgContext_Bindings *)

- ea: `0x18003d2fc`
- end: `0x18003d3c9`
- name: `?GetChannelBindingToken@CryptStream@@QEAAJPEAU_SecPkgContext_Bindings@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(CryptStream *__hidden this, struct _SecPkgContext_Bindings *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017854`

## callees

- `0x1800037a8`
- `0x180035f30`
- `0x18003d2fc`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003d327`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003d327`

## pseudocode

```c
__int64 __fastcall CryptStream::GetChannelBindingToken(RTL_SRWLOCK *this, struct _SecPkgContext_Bindings *a2)
{
  unsigned int v4; // ebx
  RTL_SRWLOCK *v5; // rbx
  __int64 (__fastcall **Ptr)(RTL_SRWLOCK *, __int64, struct _SecPkgContext_Bindings *); // rax
  unsigned int v7; // eax
  RTL_SRWLOCK *v9; // [rsp+30h] [rbp+8h] BYREF

  v4 = -2146893054;
  if ( LOBYTE(this[5].Ptr) )
  {
    v5 = this + 6;
    AcquireSRWLockShared(this + 6);
    Ptr = (__int64 (__fastcall **)(RTL_SRWLOCK *, __int64, struct _SecPkgContext_Bindings *))this[3].Ptr;
    v9 = v5;
    v7 = Ptr[11](this + 9, 26, a2);
    v4 = v7;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
      LDAPClientPrint(32, "QCA for channel bindings returned 0x%x\n", v7);
    if ( v4 )
    {
      if ( a2->Bindings )
        (*((void (**)(void))this[3].Ptr + 16))();
      a2->Bindings = 0;
      a2->BindingsLength = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
  return v4;
}

```

## disassembly

```asm
0x18003d2fc  mov     [rsp+arg_8], rbx
0x18003d301  mov     [rsp+arg_10], rsi
0x18003d306  push    rdi
0x18003d307  sub     rsp, 20h
0x18003d30b  cmp     byte ptr [rcx+28h], 0
0x18003d30f  mov     rdi, rdx
0x18003d312  mov     rsi, rcx
0x18003d315  mov     ebx, 80090302h
0x18003d31a  jz      loc_18003D3B6
0x18003d320  lea     rbx, [rcx+30h]
0x18003d324  mov     rcx, rbx; SRWLock
0x18003d327  call    cs:__imp_AcquireSRWLockShared
0x18003d32e  nop     dword ptr [rax+rax+00h]
0x18003d333  mov     rax, [rsi+18h]
0x18003d337  lea     rcx, [rsi+48h]
0x18003d33b  mov     r8, rdi
0x18003d33e  mov     [rsp+28h+arg_0], rbx
0x18003d343  mov     edx, 1Ah
0x18003d348  mov     rax, [rax+58h]
0x18003d34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d351  cmp     cs:g_fTracingOn, 0
0x18003d358  mov     ebx, eax
0x18003d35a  jz      short loc_18003D381
0x18003d35c  cmp     cs:g_fProviderEnabled, 0
0x18003d363  jz      short loc_18003D381
0x18003d365  mov     ecx, 20h ; ' '
0x18003d36a  test    byte ptr cs:g_ulTraceFlags, cl
0x18003d370  jz      short loc_18003D381
0x18003d372  mov     r8d, eax
0x18003d375  lea     rdx, aQcaForChannelB; "QCA for channel bindings returned 0x%x"...
0x18003d37c  call    LDAPClientPrint
0x18003d381  test    ebx, ebx
0x18003d383  jz      short loc_18003D3AC
0x18003d385  mov     rcx, [rdi+8]
0x18003d389  test    rcx, rcx
0x18003d38c  jz      short loc_18003D39E
0x18003d38e  mov     rax, [rsi+18h]
0x18003d392  mov     rax, [rax+80h]
0x18003d399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d39e  mov     qword ptr [rdi+8], 0
0x18003d3a6  mov     dword ptr [rdi], 0
0x18003d3ac  lea     rcx, [rsp+28h+arg_0]
0x18003d3b1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003d3b6  mov     rsi, [rsp+28h+arg_10]
0x18003d3bb  mov     eax, ebx
0x18003d3bd  mov     rbx, [rsp+28h+arg_8]
0x18003d3c2  add     rsp, 20h
0x18003d3c6  pop     rdi
0x18003d3c7  retn
```
