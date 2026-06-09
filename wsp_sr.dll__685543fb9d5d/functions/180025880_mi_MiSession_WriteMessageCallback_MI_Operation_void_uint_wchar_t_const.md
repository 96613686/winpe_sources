# mi::MiSession::WriteMessageCallback(_MI_Operation *,void *,uint,wchar_t const *)

- ea: `0x180025880`
- end: `0x180025941`
- name: `?WriteMessageCallback@MiSession@mi@@CAXPEAU_MI_Operation@@PEAXIPEB_W@Z`
- size: `193`
- prototype: `void __fastcall(struct _MI_Operation *, void *, unsigned int, const wchar_t *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180025880`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800258da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800258da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025911`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025911`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall mi::MiSession::WriteMessageCallback(
        struct _MI_Operation *a1,
        RTL_SRWLOCK *a2,
        int a3,
        const wchar_t *a4)
{
  PVOID Ptr; // rcx
  bool v7; // dl
  MI_CancellationReason v8; // edx
  int v9; // [rsp+20h] [rbp-68h] BYREF
  RTL_SRWLOCK *v10; // [rsp+28h] [rbp-60h]
  MI_Operation *v11; // [rsp+30h] [rbp-58h]
  RTL_SRWLOCK *v12; // [rsp+38h] [rbp-50h]
  _BYTE v13[32]; // [rsp+40h] [rbp-48h] BYREF

  if ( a2 )
  {
    v11 = a1;
    v10 = a2;
    if ( !a4 )
      a4 = (const wchar_t *)byte_1800AA3F0;
    try
    {
      std::wstring::wstring(v13, a4);
      v12 = a2 + 57;
      AcquireSRWLockShared(a2 + 57);
      Ptr = a2[41].Ptr;
      if ( Ptr )
      {
        v9 = a3;
        (*(void (__fastcall **)(PVOID, int *, _BYTE *))(*(_QWORD *)Ptr + 16LL))(Ptr, &v9, v13);
      }
      ReleaseSRWLockShared(a2 + 57);
      std::wstring::_Tidy_deallocate(v13);
    }
    catch ( ... )
    {
      mi::MiAsyncOperation::MiOperationArgs::store_exception((mi::MiAsyncOperation::MiOperationArgs *)v10);
      mi::MiAsyncOperation::MiOperationArgs::set_resultsCanceled((mi::MiAsyncOperation::MiOperationArgs *)v10, v7);
      MI_Operation_Cancel(v11, v8);
    }
  }
}

```

## disassembly

```asm
0x180025880  test    rdx, rdx
0x180025883  jz      locret_18002593F
0x180025889  push    rbx
0x18002588a  push    rsi
0x18002588b  push    rdi
0x18002588c  sub     rsp, 70h
0x180025890  mov     rax, cs:__security_cookie
0x180025897  xor     rax, rsp
0x18002589a  mov     [rsp+88h+var_28], rax
0x18002589f  mov     esi, r8d
0x1800258a2  mov     rdi, rdx
0x1800258a5  mov     [rsp+88h+var_58], rcx
0x1800258aa  mov     [rsp+88h+var_60], rdx
0x1800258af  lea     rax, byte_1800AA3F0
0x1800258b6  test    r9, r9
0x1800258b9  cmovz   r9, rax
0x1800258bd  mov     rdx, r9
0x1800258c0  lea     rcx, [rsp+88h+var_48]
0x1800258c5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800258ca  nop
0x1800258cb  lea     rbx, [rdi+1C8h]
0x1800258d2  mov     [rsp+88h+var_50], rbx
0x1800258d7  mov     rcx, rbx; SRWLock
0x1800258da  call    cs:__imp_AcquireSRWLockShared
0x1800258e1  nop     dword ptr [rax+rax+00h]
0x1800258e6  nop
0x1800258e7  mov     rcx, [rdi+148h]
0x1800258ee  test    rcx, rcx
0x1800258f1  jz      short loc_18002590E
0x1800258f3  mov     [rsp+88h+var_68], esi
0x1800258f7  mov     rax, [rcx]
0x1800258fa  lea     r8, [rsp+88h+var_48]
0x1800258ff  lea     rdx, [rsp+88h+var_68]
0x180025904  mov     rax, [rax+10h]
0x180025908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002590d  nop
0x18002590e  mov     rcx, rbx; SRWLock
0x180025911  call    cs:__imp_ReleaseSRWLockShared
0x180025918  nop     dword ptr [rax+rax+00h]
0x18002591d  nop
0x18002591e  lea     rcx, [rsp+88h+var_48]
0x180025923  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025928  nop
0x180025929  jmp     short $+2
0x18002592b  mov     rcx, [rsp+88h+var_28]
0x180025930  xor     rcx, rsp; StackCookie
0x180025933  call    __security_check_cookie
0x180025938  add     rsp, 70h
0x18002593c  pop     rdi
0x18002593d  pop     rsi
0x18002593e  pop     rbx
0x18002593f  retn
```
