# PRELOAD_MANAGER::ProcessAllApplications(void)

- ea: `0x18000c578`
- end: `0x18000c883`
- name: `?ProcessAllApplications@PRELOAD_MANAGER@@QEAAJXZ`
- size: `779`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800068bc`
- `0x18000c490`

## callees

- `0x18000c578`
- `0x18000cc48`
- `0x18000e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c712`
- `msvcrt!_wcsicmp` at `0x18000c712`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c7d3`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c7d3`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c5bc`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c5bc`

## string_xrefs

- `0x18000c732`: `serviceAutoStartEnabled`

## pseudocode

```c
__int64 __fastcall PRELOAD_MANAGER::ProcessAllApplications(PRELOAD_MANAGER *this)
{
  int v2; // ebx
  unsigned int i; // esi
  __int64 v4; // rax
  unsigned int j; // edi
  __int64 v6; // rax
  __int64 *v8; // [rsp+40h] [rbp-30h] BYREF
  struct INativeConfigurationElement *v9; // [rsp+48h] [rbp-28h] BYREF
  __int64 *v10; // [rsp+50h] [rbp-20h] BYREF
  __int64 v11; // [rsp+58h] [rbp-18h] BYREF
  __int64 v12; // [rsp+60h] [rbp-10h] BYREF
  wchar_t *String2; // [rsp+68h] [rbp-8h] BYREF
  unsigned int v14; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v15; // [rsp+B8h] [rbp+48h] BYREF
  int v16; // [rsp+C0h] [rbp+50h] BYREF
  struct INativeConfigurationElement *v17; // [rsp+C8h] [rbp+58h] BYREF

  v11 = 0;
  v10 = 0;
  v9 = 0;
  v12 = 0;
  v8 = 0;
  v17 = 0;
  String2 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  CReaderWriterLock3::WriteLock((PRELOAD_MANAGER *)((char *)this + 16));
  v2 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64 *, __int64 *, _QWORD))(**((_QWORD **)this + 6) + 24LL))(
         *((_QWORD *)this + 6),
         L"system.applicationHost/sites",
         L"MACHINE/WEBROOT/APPHOST",
         &v11,
         &v12,
         0);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v11 + 40LL))(v11, &v10);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v10 + 24))(v10, &v14);
      if ( v2 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          v4 = *v10;
          if ( i >= v14 )
            break;
          v2 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct INativeConfigurationElement **))(v4 + 32))(
                 v10,
                 i,
                 &v9);
          if ( v2 < 0 )
            goto LABEL_20;
          v2 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 **))(*(_QWORD *)v9 + 40LL))(
                 v9,
                 &v8);
          if ( v2 < 0 )
            goto LABEL_20;
          v2 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v8 + 24))(v8, &v15);
          if ( v2 < 0 )
            goto LABEL_20;
          for ( j = 0; ; ++j )
          {
            v6 = *v8;
            if ( j >= v15 )
              break;
            v2 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct INativeConfigurationElement **))(v6 + 32))(
                   v8,
                   j,
                   &v17);
            if ( v2 < 0 )
              goto LABEL_20;
            v2 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                   v17,
                   L"applicationPool",
                   &String2,
                   0,
                   0);
            if ( v2 < 0 )
              goto LABEL_20;
            if ( !_wcsicmp(*(const wchar_t **)(*(_QWORD *)(*((_QWORD *)this + 4) + 312LL) + 24LL), String2) )
            {
              v2 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v17 + 72LL))(
                     v17,
                     L"serviceAutoStartEnabled",
                     &v16,
                     0,
                     0);
              if ( v2 < 0 )
                goto LABEL_20;
              if ( v16 )
              {
                v2 = PRELOAD_MANAGER::ProcessSiteApplication(this, v9, v17);
                if ( v2 < 0 )
                  goto LABEL_20;
              }
            }
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v17 + 16LL))(v17);
            v17 = 0;
          }
          (*(void (**)(void))(v6 + 16))();
          v8 = 0;
          (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v9 + 16LL))(v9);
          v9 = 0;
        }
        (*(void (**)(void))(v4 + 16))();
        v10 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        v11 = 0;
      }
    }
  }
LABEL_20:
  CReaderWriterLock3::WriteUnlock((PRELOAD_MANAGER *)((char *)this + 16));
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64 *))(*v8 + 16))(v8);
    v8 = 0;
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
    v10 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000c578  push    rbp
0x18000c57a  push    rbx
0x18000c57b  push    rsi
0x18000c57c  push    rdi
0x18000c57d  push    r12
0x18000c57f  push    r14
0x18000c581  push    r15
0x18000c583  mov     rbp, rsp
0x18000c586  sub     rsp, 70h
0x18000c58a  xor     r12d, r12d
0x18000c58d  mov     r14, rcx
0x18000c590  add     rcx, 10h
0x18000c594  mov     [rbp+var_18], r12
0x18000c598  mov     [rbp+var_20], r12
0x18000c59c  mov     [rbp+var_28], r12
0x18000c5a0  mov     [rbp+var_10], r12
0x18000c5a4  mov     [rbp+var_30], r12
0x18000c5a8  mov     [rbp+arg_18], r12
0x18000c5ac  mov     [rbp+String2], r12
0x18000c5b0  mov     [rbp+arg_0], r12d
0x18000c5b4  mov     [rbp+arg_8], r12d
0x18000c5b8  mov     [rbp+arg_10], r12d
0x18000c5bc  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000c5c3  nop     dword ptr [rax+rax+00h]
0x18000c5c8  mov     rcx, [r14+30h]
0x18000c5cc  lea     rdx, [rbp+var_10]
0x18000c5d0  mov     [rsp+70h+var_48], r12
0x18000c5d5  lea     r9, [rbp+var_18]
0x18000c5d9  mov     [rsp+70h+var_50], rdx
0x18000c5de  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000c5e5  lea     rdx, aSystemApplicat; "system.applicationHost/sites"
0x18000c5ec  mov     rax, [rcx]
0x18000c5ef  mov     rax, [rax+18h]
0x18000c5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5f8  mov     ebx, eax
0x18000c5fa  test    eax, eax
0x18000c5fc  js      loc_18000C7CF
0x18000c602  mov     rcx, [rbp+var_18]
0x18000c606  lea     rdx, [rbp+var_20]
0x18000c60a  mov     rax, [rcx]
0x18000c60d  mov     rax, [rax+28h]
0x18000c611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c616  mov     ebx, eax
0x18000c618  test    eax, eax
0x18000c61a  js      loc_18000C7CF
0x18000c620  mov     rcx, [rbp+var_20]
0x18000c624  lea     rdx, [rbp+arg_0]
0x18000c628  mov     rax, [rcx]
0x18000c62b  mov     rax, [rax+18h]
0x18000c62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c634  mov     ebx, eax
0x18000c636  test    eax, eax
0x18000c638  js      loc_18000C7CF
0x18000c63e  mov     esi, r12d
0x18000c641  mov     rcx, [rbp+var_20]
0x18000c645  mov     rax, [rcx]
0x18000c648  cmp     esi, [rbp+arg_0]
0x18000c64b  jnb     loc_18000C7AE
0x18000c651  mov     rax, [rax+20h]
0x18000c655  lea     r8, [rbp+var_28]
0x18000c659  mov     edx, esi
0x18000c65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c660  mov     ebx, eax
0x18000c662  test    eax, eax
0x18000c664  js      loc_18000C7CF
0x18000c66a  mov     rcx, [rbp+var_28]
0x18000c66e  lea     rdx, [rbp+var_30]
0x18000c672  mov     rax, [rcx]
0x18000c675  mov     rax, [rax+28h]
0x18000c679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c67e  mov     ebx, eax
0x18000c680  test    eax, eax
0x18000c682  js      loc_18000C7CF
0x18000c688  mov     rcx, [rbp+var_30]
0x18000c68c  lea     rdx, [rbp+arg_8]
0x18000c690  mov     rax, [rcx]
0x18000c693  mov     rax, [rax+18h]
0x18000c697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c69c  mov     ebx, eax
0x18000c69e  test    eax, eax
0x18000c6a0  js      loc_18000C7CF
0x18000c6a6  mov     edi, r12d
0x18000c6a9  mov     rcx, [rbp+var_30]
0x18000c6ad  mov     rax, [rcx]
0x18000c6b0  cmp     edi, [rbp+arg_8]
0x18000c6b3  jnb     loc_18000C786
0x18000c6b9  mov     rax, [rax+20h]
0x18000c6bd  lea     r8, [rbp+arg_18]
0x18000c6c1  mov     edx, edi
0x18000c6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6c8  mov     ebx, eax
0x18000c6ca  test    eax, eax
0x18000c6cc  js      loc_18000C7CF
0x18000c6d2  mov     rcx, [rbp+arg_18]
0x18000c6d6  lea     r8, [rbp+String2]
0x18000c6da  xor     r9d, r9d
0x18000c6dd  mov     [rsp+70h+var_50], r12
0x18000c6e2  lea     rdx, String1; "applicationPool"
0x18000c6e9  mov     rax, [rcx]
0x18000c6ec  mov     rax, [rax+40h]
0x18000c6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6f5  mov     ebx, eax
0x18000c6f7  test    eax, eax
0x18000c6f9  js      loc_18000C7CF
0x18000c6ff  mov     rax, [r14+20h]
0x18000c703  mov     rdx, [rbp+String2]; String2
0x18000c707  mov     rcx, [rax+138h]
0x18000c70e  mov     rcx, [rcx+18h]; String1
0x18000c712  call    cs:__imp__wcsicmp
0x18000c719  nop     dword ptr [rax+rax+00h]
0x18000c71e  test    eax, eax
0x18000c720  jnz     short loc_18000C76B
0x18000c722  mov     rcx, [rbp+arg_18]
0x18000c726  lea     r8, [rbp+arg_10]
0x18000c72a  xor     r9d, r9d
0x18000c72d  mov     [rsp+70h+var_50], r12
0x18000c732  lea     rdx, aServiceautosta; "serviceAutoStartEnabled"
0x18000c739  mov     rax, [rcx]
0x18000c73c  mov     rax, [rax+48h]
0x18000c740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c745  mov     ebx, eax
0x18000c747  test    eax, eax
0x18000c749  js      loc_18000C7CF
0x18000c74f  cmp     [rbp+arg_10], r12d
0x18000c753  jz      short loc_18000C76B
0x18000c755  mov     r8, [rbp+arg_18]; struct INativeConfigurationElement *
0x18000c759  mov     rcx, r14; this
0x18000c75c  mov     rdx, [rbp+var_28]; struct INativeConfigurationElement *
0x18000c760  call    ?ProcessSiteApplication@PRELOAD_MANAGER@@AEAAJPEAVINativeConfigurationElement@@0@Z; PRELOAD_MANAGER::ProcessSiteApplication(INativeConfigurationElement *,INativeConfigurationElement *)
0x18000c765  mov     ebx, eax
0x18000c767  test    eax, eax
0x18000c769  js      short loc_18000C7CF
0x18000c76b  mov     rcx, [rbp+arg_18]
0x18000c76f  mov     rax, [rcx]
0x18000c772  mov     rax, [rax+10h]
0x18000c776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c77b  inc     edi
0x18000c77d  mov     [rbp+arg_18], r12
0x18000c781  jmp     loc_18000C6A9
0x18000c786  mov     rax, [rax+10h]
0x18000c78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c78f  mov     rcx, [rbp+var_28]
0x18000c793  mov     [rbp+var_30], r12
0x18000c797  mov     rax, [rcx]
0x18000c79a  mov     rax, [rax+10h]
0x18000c79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7a3  inc     esi
0x18000c7a5  mov     [rbp+var_28], r12
0x18000c7a9  jmp     loc_18000C641
0x18000c7ae  mov     rax, [rax+10h]
0x18000c7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7b7  mov     rcx, [rbp+var_18]
0x18000c7bb  mov     [rbp+var_20], r12
0x18000c7bf  mov     rax, [rcx]
0x18000c7c2  mov     rax, [rax+10h]
0x18000c7c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7cb  mov     [rbp+var_18], r12
0x18000c7cf  lea     rcx, [r14+10h]
0x18000c7d3  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000c7da  nop     dword ptr [rax+rax+00h]
0x18000c7df  mov     rcx, [rbp+var_10]
0x18000c7e3  test    rcx, rcx
0x18000c7e6  jz      short loc_18000C7F8
0x18000c7e8  mov     rax, [rcx]
0x18000c7eb  mov     rax, [rax+10h]
0x18000c7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7f4  mov     [rbp+var_10], r12
0x18000c7f8  mov     rcx, [rbp+arg_18]
0x18000c7fc  test    rcx, rcx
0x18000c7ff  jz      short loc_18000C811
0x18000c801  mov     rax, [rcx]
0x18000c804  mov     rax, [rax+10h]
0x18000c808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c80d  mov     [rbp+arg_18], r12
0x18000c811  mov     rcx, [rbp+var_30]
0x18000c815  test    rcx, rcx
0x18000c818  jz      short loc_18000C82A
0x18000c81a  mov     rax, [rcx]
0x18000c81d  mov     rax, [rax+10h]
0x18000c821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c826  mov     [rbp+var_30], r12
0x18000c82a  mov     rcx, [rbp+var_28]
0x18000c82e  test    rcx, rcx
0x18000c831  jz      short loc_18000C843
0x18000c833  mov     rax, [rcx]
0x18000c836  mov     rax, [rax+10h]
0x18000c83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c83f  mov     [rbp+var_28], r12
0x18000c843  mov     rcx, [rbp+var_20]
0x18000c847  test    rcx, rcx
0x18000c84a  jz      short loc_18000C85C
0x18000c84c  mov     rax, [rcx]
0x18000c84f  mov     rax, [rax+10h]
0x18000c853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c858  mov     [rbp+var_20], r12
0x18000c85c  mov     rcx, [rbp+var_18]
0x18000c860  test    rcx, rcx
0x18000c863  jz      short loc_18000C871
0x18000c865  mov     rax, [rcx]
0x18000c868  mov     rax, [rax+10h]
0x18000c86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c871  mov     eax, ebx
0x18000c873  add     rsp, 70h
0x18000c877  pop     r15
0x18000c879  pop     r14
0x18000c87b  pop     r12
0x18000c87d  pop     rdi
0x18000c87e  pop     rsi
0x18000c87f  pop     rbx
0x18000c880  pop     rbp
0x18000c881  retn
```
