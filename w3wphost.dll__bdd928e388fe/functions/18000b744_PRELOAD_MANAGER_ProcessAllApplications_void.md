# PRELOAD_MANAGER::ProcessAllApplications(void)

- ea: `0x18000b744`
- end: `0x18000ba3c`
- name: `?ProcessAllApplications@PRELOAD_MANAGER@@QEAAJXZ`
- size: `760`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800062a0`
- `0x18000b670`

## callees

- `0x18000b744`
- `0x18000bda8`
- `0x18000d010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b8d8`
- `msvcrt!_wcsicmp` at `0x18000b8d8`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b993`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b993`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b788`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b788`

## string_xrefs

- `0x18000b8f2`: `serviceAutoStartEnabled`

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
0x18000b744  push    rbp
0x18000b746  push    rbx
0x18000b747  push    rsi
0x18000b748  push    rdi
0x18000b749  push    r12
0x18000b74b  push    r14
0x18000b74d  push    r15
0x18000b74f  mov     rbp, rsp
0x18000b752  sub     rsp, 70h
0x18000b756  xor     r12d, r12d
0x18000b759  mov     r14, rcx
0x18000b75c  add     rcx, 10h
0x18000b760  mov     [rbp+var_18], r12
0x18000b764  mov     [rbp+var_20], r12
0x18000b768  mov     [rbp+var_28], r12
0x18000b76c  mov     [rbp+var_10], r12
0x18000b770  mov     [rbp+var_30], r12
0x18000b774  mov     [rbp+arg_18], r12
0x18000b778  mov     [rbp+String2], r12
0x18000b77c  mov     [rbp+arg_0], r12d
0x18000b780  mov     [rbp+arg_8], r12d
0x18000b784  mov     [rbp+arg_10], r12d
0x18000b788  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b78e  mov     rcx, [r14+30h]
0x18000b792  lea     rdx, [rbp+var_10]
0x18000b796  mov     [rsp+70h+var_48], r12
0x18000b79b  lea     r9, [rbp+var_18]
0x18000b79f  mov     [rsp+70h+var_50], rdx
0x18000b7a4  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000b7ab  lea     rdx, aSystemApplicat; "system.applicationHost/sites"
0x18000b7b2  mov     rax, [rcx]
0x18000b7b5  mov     rax, [rax+18h]
0x18000b7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7be  mov     ebx, eax
0x18000b7c0  test    eax, eax
0x18000b7c2  js      loc_18000B98F
0x18000b7c8  mov     rcx, [rbp+var_18]
0x18000b7cc  lea     rdx, [rbp+var_20]
0x18000b7d0  mov     rax, [rcx]
0x18000b7d3  mov     rax, [rax+28h]
0x18000b7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7dc  mov     ebx, eax
0x18000b7de  test    eax, eax
0x18000b7e0  js      loc_18000B98F
0x18000b7e6  mov     rcx, [rbp+var_20]
0x18000b7ea  lea     rdx, [rbp+arg_0]
0x18000b7ee  mov     rax, [rcx]
0x18000b7f1  mov     rax, [rax+18h]
0x18000b7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7fa  mov     ebx, eax
0x18000b7fc  test    eax, eax
0x18000b7fe  js      loc_18000B98F
0x18000b804  mov     esi, r12d
0x18000b807  mov     rcx, [rbp+var_20]
0x18000b80b  mov     rax, [rcx]
0x18000b80e  cmp     esi, [rbp+arg_0]
0x18000b811  jnb     loc_18000B96E
0x18000b817  mov     rax, [rax+20h]
0x18000b81b  lea     r8, [rbp+var_28]
0x18000b81f  mov     edx, esi
0x18000b821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b826  mov     ebx, eax
0x18000b828  test    eax, eax
0x18000b82a  js      loc_18000B98F
0x18000b830  mov     rcx, [rbp+var_28]
0x18000b834  lea     rdx, [rbp+var_30]
0x18000b838  mov     rax, [rcx]
0x18000b83b  mov     rax, [rax+28h]
0x18000b83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b844  mov     ebx, eax
0x18000b846  test    eax, eax
0x18000b848  js      loc_18000B98F
0x18000b84e  mov     rcx, [rbp+var_30]
0x18000b852  lea     rdx, [rbp+arg_8]
0x18000b856  mov     rax, [rcx]
0x18000b859  mov     rax, [rax+18h]
0x18000b85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b862  mov     ebx, eax
0x18000b864  test    eax, eax
0x18000b866  js      loc_18000B98F
0x18000b86c  mov     edi, r12d
0x18000b86f  mov     rcx, [rbp+var_30]
0x18000b873  mov     rax, [rcx]
0x18000b876  cmp     edi, [rbp+arg_8]
0x18000b879  jnb     loc_18000B946
0x18000b87f  mov     rax, [rax+20h]
0x18000b883  lea     r8, [rbp+arg_18]
0x18000b887  mov     edx, edi
0x18000b889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b88e  mov     ebx, eax
0x18000b890  test    eax, eax
0x18000b892  js      loc_18000B98F
0x18000b898  mov     rcx, [rbp+arg_18]
0x18000b89c  lea     r8, [rbp+String2]
0x18000b8a0  xor     r9d, r9d
0x18000b8a3  mov     [rsp+70h+var_50], r12
0x18000b8a8  lea     rdx, aApplicationpoo; "applicationPool"
0x18000b8af  mov     rax, [rcx]
0x18000b8b2  mov     rax, [rax+40h]
0x18000b8b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8bb  mov     ebx, eax
0x18000b8bd  test    eax, eax
0x18000b8bf  js      loc_18000B98F
0x18000b8c5  mov     rax, [r14+20h]
0x18000b8c9  mov     rdx, [rbp+String2]; String2
0x18000b8cd  mov     rcx, [rax+138h]
0x18000b8d4  mov     rcx, [rcx+18h]; String1
0x18000b8d8  call    cs:__imp__wcsicmp
0x18000b8de  test    eax, eax
0x18000b8e0  jnz     short loc_18000B92B
0x18000b8e2  mov     rcx, [rbp+arg_18]
0x18000b8e6  lea     r8, [rbp+arg_10]
0x18000b8ea  xor     r9d, r9d
0x18000b8ed  mov     [rsp+70h+var_50], r12
0x18000b8f2  lea     rdx, aServiceautosta; "serviceAutoStartEnabled"
0x18000b8f9  mov     rax, [rcx]
0x18000b8fc  mov     rax, [rax+48h]
0x18000b900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b905  mov     ebx, eax
0x18000b907  test    eax, eax
0x18000b909  js      loc_18000B98F
0x18000b90f  cmp     [rbp+arg_10], r12d
0x18000b913  jz      short loc_18000B92B
0x18000b915  mov     r8, [rbp+arg_18]; struct INativeConfigurationElement *
0x18000b919  mov     rcx, r14; this
0x18000b91c  mov     rdx, [rbp+var_28]; struct INativeConfigurationElement *
0x18000b920  call    ?ProcessSiteApplication@PRELOAD_MANAGER@@AEAAJPEAVINativeConfigurationElement@@0@Z; PRELOAD_MANAGER::ProcessSiteApplication(INativeConfigurationElement *,INativeConfigurationElement *)
0x18000b925  mov     ebx, eax
0x18000b927  test    eax, eax
0x18000b929  js      short loc_18000B98F
0x18000b92b  mov     rcx, [rbp+arg_18]
0x18000b92f  mov     rax, [rcx]
0x18000b932  mov     rax, [rax+10h]
0x18000b936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b93b  inc     edi
0x18000b93d  mov     [rbp+arg_18], r12
0x18000b941  jmp     loc_18000B86F
0x18000b946  mov     rax, [rax+10h]
0x18000b94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b94f  mov     rcx, [rbp+var_28]
0x18000b953  mov     [rbp+var_30], r12
0x18000b957  mov     rax, [rcx]
0x18000b95a  mov     rax, [rax+10h]
0x18000b95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b963  inc     esi
0x18000b965  mov     [rbp+var_28], r12
0x18000b969  jmp     loc_18000B807
0x18000b96e  mov     rax, [rax+10h]
0x18000b972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b977  mov     rcx, [rbp+var_18]
0x18000b97b  mov     [rbp+var_20], r12
0x18000b97f  mov     rax, [rcx]
0x18000b982  mov     rax, [rax+10h]
0x18000b986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b98b  mov     [rbp+var_18], r12
0x18000b98f  lea     rcx, [r14+10h]
0x18000b993  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b999  mov     rcx, [rbp+var_10]
0x18000b99d  test    rcx, rcx
0x18000b9a0  jz      short loc_18000B9B2
0x18000b9a2  mov     rax, [rcx]
0x18000b9a5  mov     rax, [rax+10h]
0x18000b9a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9ae  mov     [rbp+var_10], r12
0x18000b9b2  mov     rcx, [rbp+arg_18]
0x18000b9b6  test    rcx, rcx
0x18000b9b9  jz      short loc_18000B9CB
0x18000b9bb  mov     rax, [rcx]
0x18000b9be  mov     rax, [rax+10h]
0x18000b9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9c7  mov     [rbp+arg_18], r12
0x18000b9cb  mov     rcx, [rbp+var_30]
0x18000b9cf  test    rcx, rcx
0x18000b9d2  jz      short loc_18000B9E4
0x18000b9d4  mov     rax, [rcx]
0x18000b9d7  mov     rax, [rax+10h]
0x18000b9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9e0  mov     [rbp+var_30], r12
0x18000b9e4  mov     rcx, [rbp+var_28]
0x18000b9e8  test    rcx, rcx
0x18000b9eb  jz      short loc_18000B9FD
0x18000b9ed  mov     rax, [rcx]
0x18000b9f0  mov     rax, [rax+10h]
0x18000b9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9f9  mov     [rbp+var_28], r12
0x18000b9fd  mov     rcx, [rbp+var_20]
0x18000ba01  test    rcx, rcx
0x18000ba04  jz      short loc_18000BA16
0x18000ba06  mov     rax, [rcx]
0x18000ba09  mov     rax, [rax+10h]
0x18000ba0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba12  mov     [rbp+var_20], r12
0x18000ba16  mov     rcx, [rbp+var_18]
0x18000ba1a  test    rcx, rcx
0x18000ba1d  jz      short loc_18000BA2B
0x18000ba1f  mov     rax, [rcx]
0x18000ba22  mov     rax, [rax+10h]
0x18000ba26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba2b  mov     eax, ebx
0x18000ba2d  add     rsp, 70h
0x18000ba31  pop     r15
0x18000ba33  pop     r14
0x18000ba35  pop     r12
0x18000ba37  pop     rdi
0x18000ba38  pop     rsi
0x18000ba39  pop     rbx
0x18000ba3a  pop     rbp
0x18000ba3b  retn
```
