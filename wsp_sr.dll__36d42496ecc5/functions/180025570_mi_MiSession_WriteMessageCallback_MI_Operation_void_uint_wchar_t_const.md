# mi::MiSession::WriteMessageCallback(_MI_Operation *,void *,uint,wchar_t const *)

- ea: `0x180025570`
- end: `0x180025624`
- name: `?WriteMessageCallback@MiSession@mi@@CAXPEAU_MI_Operation@@PEAXIPEB_W@Z`
- size: `180`
- prototype: `void __fastcall(struct _MI_Operation *, RTL_SRWLOCK *, int, const wchar_t *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x180025570`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800255ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800255ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800255fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800255fb`

## pseudocode

```c
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
      a4 = (const wchar_t *)byte_1800AA410;
    try
    {
      std::wstring::wstring((__int64)v13, (__int64)a4);
      v12 = a2 + 57;
      AcquireSRWLockShared(a2 + 57);
      Ptr = a2[41].Ptr;
      if ( Ptr )
      {
        v9 = a3;
        (*(void (__fastcall **)(PVOID, int *, _BYTE *))(*(_QWORD *)Ptr + 16LL))(Ptr, &v9, v13);
      }
      ReleaseSRWLockShared(a2 + 57);
      std::wstring::_Tidy_deallocate((__int64)v13);
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
0x180025570  test    rdx, rdx
0x180025573  jz      locret_180025623
0x180025579  push    rbx
0x18002557a  push    rsi
0x18002557b  push    rdi
0x18002557c  sub     rsp, 70h
0x180025580  mov     rax, cs:__security_cookie
0x180025587  xor     rax, rsp
0x18002558a  mov     [rsp+88h+var_28], rax
0x18002558f  mov     esi, r8d
0x180025592  mov     rdi, rdx
0x180025595  mov     [rsp+88h+var_58], rcx
0x18002559a  mov     [rsp+88h+var_60], rdx
0x18002559f  lea     rax, byte_1800AA410
0x1800255a6  test    r9, r9
0x1800255a9  cmovz   r9, rax
0x1800255ad  mov     rdx, r9
0x1800255b0  lea     rcx, [rsp+88h+var_48]
0x1800255b5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800255ba  nop
0x1800255bb  lea     rbx, [rdi+1C8h]
0x1800255c2  mov     [rsp+88h+var_50], rbx
0x1800255c7  mov     rcx, rbx; SRWLock
0x1800255ca  call    cs:__imp_AcquireSRWLockShared
0x1800255d0  nop
0x1800255d1  mov     rcx, [rdi+148h]
0x1800255d8  test    rcx, rcx
0x1800255db  jz      short loc_1800255F8
0x1800255dd  mov     [rsp+88h+var_68], esi
0x1800255e1  mov     rax, [rcx]
0x1800255e4  lea     r8, [rsp+88h+var_48]
0x1800255e9  lea     rdx, [rsp+88h+var_68]
0x1800255ee  mov     rax, [rax+10h]
0x1800255f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255f7  nop
0x1800255f8  mov     rcx, rbx; SRWLock
0x1800255fb  call    cs:__imp_ReleaseSRWLockShared
0x180025601  nop
0x180025602  lea     rcx, [rsp+88h+var_48]
0x180025607  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002560c  nop
0x18002560d  jmp     short $+2
0x18002560f  mov     rcx, [rsp+88h+var_28]
0x180025614  xor     rcx, rsp; StackCookie
0x180025617  call    __security_check_cookie
0x18002561c  add     rsp, 70h
0x180025620  pop     rdi
0x180025621  pop     rsi
0x180025622  pop     rbx
0x180025623  retn
```
