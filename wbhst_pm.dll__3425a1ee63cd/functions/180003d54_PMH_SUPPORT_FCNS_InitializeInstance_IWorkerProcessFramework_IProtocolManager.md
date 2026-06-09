# PMH_SUPPORT_FCNS::InitializeInstance(IWorkerProcessFramework *,IProtocolManager *)

- ea: `0x180003d54`
- end: `0x180003f9a`
- name: `?InitializeInstance@PMH_SUPPORT_FCNS@@QEAAJPEAVIWorkerProcessFramework@@PEAVIProtocolManager@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(PMH_SUPPORT_FCNS *__hidden this, struct IWorkerProcessFramework *, struct IProtocolManager *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002230`

## callees

- `0x180003d54`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d95`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003d8b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003d8b`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003ee0`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003f62`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003ee0`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003f62`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003e9f`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003f23`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003e9f`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003f23`

## pseudocode

```c
__int64 __fastcall PMH_SUPPORT_FCNS::InitializeInstance(
        PMH_SUPPORT_FCNS *this,
        struct IWorkerProcessFramework *a2,
        struct IProtocolManager *a3)
{
  signed int LastError; // eax
  signed int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r8
  int v13; // [rsp+60h] [rbp+30h] BYREF
  __int64 v14; // [rsp+78h] [rbp+48h] BYREF

  v14 = 0;
  v13 = 0;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 192), 0x3E8u) )
  {
    *((_DWORD *)this + 47) = 1;
    v7 = (*(__int64 (__fastcall **)(struct IWorkerProcessFramework *, __int64, char *))(*(_QWORD *)a2 + 16LL))(
           a2,
           1,
           (char *)this + 32);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(struct IWorkerProcessFramework *, __int64, char *))(*(_QWORD *)a2 + 16LL))(
             a2,
             6,
             (char *)this + 176);
      if ( v7 >= 0 )
      {
        v7 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))this + 4))(
               *((_QWORD *)this + 4),
               &IID_IAppHostAdminManager,
               (char *)this + 40);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(struct IWorkerProcessFramework *, __int64, char *))(*(_QWORD *)a2 + 16LL))(
                 a2,
                 2,
                 (char *)this + 48);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(struct IWorkerProcessFramework *, __int64, __int64 *))(*(_QWORD *)a2 + 16LL))(
                   a2,
                   3,
                   &v14);
            if ( v7 >= 0 )
            {
              v8 = *((_QWORD *)this + 12);
              v13 = *((_DWORD *)this + 26) >> 1;
              v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v14 + 32LL))(
                     v14,
                     2,
                     v8,
                     &v13);
              if ( v7 == -2147024774 )
              {
                v7 = STRU::Resize((PMH_SUPPORT_FCNS *)((char *)this + 64), 2 * v13);
                if ( v7 < 0 )
                  goto LABEL_18;
                v9 = *((_QWORD *)this + 12);
                v13 = *((_DWORD *)this + 26);
                v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v14 + 32LL))(
                       v14,
                       2,
                       v9,
                       &v13);
              }
              if ( v7 >= 0 )
              {
                STRU::SyncWithBuffer((PMH_SUPPORT_FCNS *)((char *)this + 64));
                v10 = *((_QWORD *)this + 19);
                v13 = *((_DWORD *)this + 40) >> 1;
                v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v14 + 32LL))(
                       v14,
                       3,
                       v10,
                       &v13);
                if ( v7 == -2147024774 )
                {
                  v7 = STRU::Resize((PMH_SUPPORT_FCNS *)((char *)this + 120), 2 * v13);
                  if ( v7 < 0 )
                    goto LABEL_18;
                  v11 = *((_QWORD *)this + 19);
                  v13 = *((_DWORD *)this + 40);
                  v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v14 + 32LL))(
                         v14,
                         3,
                         v11,
                         &v13);
                }
                if ( v7 >= 0 )
                {
                  STRU::SyncWithBuffer((PMH_SUPPORT_FCNS *)((char *)this + 120));
                  v7 = 0;
                  *((_QWORD *)this + 3) = a2;
                  *((_QWORD *)this + 7) = a3;
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_18:
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003d54  mov     [rsp-28h+arg_8], rbx
0x180003d59  push    rbp
0x180003d5a  push    rsi
0x180003d5b  push    rdi
0x180003d5c  push    r14
0x180003d5e  push    r15
0x180003d60  mov     rbp, rsp
0x180003d63  sub     rsp, 30h
0x180003d67  mov     rsi, rdx
0x180003d6a  mov     [rbp+arg_18], 0
0x180003d72  mov     rdi, rcx
0x180003d75  mov     [rbp+arg_0], 0
0x180003d7c  add     rcx, 0C0h; lpCriticalSection
0x180003d83  mov     edx, 3E8h; dwSpinCount
0x180003d88  mov     r15, r8
0x180003d8b  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180003d91  test    eax, eax
0x180003d93  jnz     short loc_180003DB3
0x180003d95  call    cs:__imp_GetLastError
0x180003d9b  mov     ebx, eax
0x180003d9d  test    eax, eax
0x180003d9f  jle     loc_180003F72
0x180003da5  movzx   ebx, ax
0x180003da8  or      ebx, 80070000h
0x180003dae  jmp     loc_180003F72
0x180003db3  mov     edx, 1
0x180003db8  lea     r8, [rdi+20h]
0x180003dbc  mov     [rdi+0BCh], edx
0x180003dc2  mov     rcx, rsi
0x180003dc5  mov     rax, [rsi]
0x180003dc8  mov     rax, [rax+10h]
0x180003dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dd1  mov     ebx, eax
0x180003dd3  test    eax, eax
0x180003dd5  js      loc_180003F72
0x180003ddb  mov     rax, [rsi]
0x180003dde  lea     r8, [rdi+0B0h]
0x180003de5  mov     edx, 6
0x180003dea  mov     rcx, rsi
0x180003ded  mov     rax, [rax+10h]
0x180003df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003df6  mov     ebx, eax
0x180003df8  test    eax, eax
0x180003dfa  js      loc_180003F72
0x180003e00  mov     rcx, [rdi+20h]
0x180003e04  lea     r8, [rdi+28h]
0x180003e08  lea     rdx, IID_IAppHostAdminManager
0x180003e0f  mov     rax, [rcx]
0x180003e12  mov     rax, [rax]
0x180003e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e1a  mov     ebx, eax
0x180003e1c  test    eax, eax
0x180003e1e  js      loc_180003F72
0x180003e24  mov     rax, [rsi]
0x180003e27  lea     r8, [rdi+30h]
0x180003e2b  mov     edx, 2
0x180003e30  mov     rcx, rsi
0x180003e33  mov     rax, [rax+10h]
0x180003e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e3c  mov     ebx, eax
0x180003e3e  test    eax, eax
0x180003e40  js      loc_180003F72
0x180003e46  mov     rax, [rsi]
0x180003e49  lea     r8, [rbp+arg_18]
0x180003e4d  mov     edx, 3
0x180003e52  mov     rcx, rsi
0x180003e55  mov     rax, [rax+10h]
0x180003e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e5e  mov     ebx, eax
0x180003e60  test    eax, eax
0x180003e62  js      loc_180003F72
0x180003e68  mov     eax, [rdi+68h]
0x180003e6b  lea     r9, [rbp+arg_0]
0x180003e6f  mov     rcx, [rbp+arg_18]
0x180003e73  mov     edx, 2
0x180003e78  mov     r8, [rdi+60h]
0x180003e7c  shr     eax, 1
0x180003e7e  mov     [rbp+arg_0], eax
0x180003e81  mov     rax, [rcx]
0x180003e84  mov     rax, [rax+20h]
0x180003e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e8d  mov     ebx, eax
0x180003e8f  cmp     eax, 8007007Ah
0x180003e94  jnz     short loc_180003ED4
0x180003e96  mov     edx, [rbp+arg_0]
0x180003e99  lea     rcx, [rdi+40h]
0x180003e9d  add     edx, edx
0x180003e9f  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180003ea5  mov     ebx, eax
0x180003ea7  test    eax, eax
0x180003ea9  js      loc_180003F72
0x180003eaf  mov     eax, [rdi+68h]
0x180003eb2  lea     r9, [rbp+arg_0]
0x180003eb6  mov     rcx, [rbp+arg_18]
0x180003eba  mov     edx, 2
0x180003ebf  mov     r8, [rdi+60h]
0x180003ec3  mov     [rbp+arg_0], eax
0x180003ec6  mov     rax, [rcx]
0x180003ec9  mov     rax, [rax+20h]
0x180003ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ed2  mov     ebx, eax
0x180003ed4  test    ebx, ebx
0x180003ed6  js      loc_180003F72
0x180003edc  lea     rcx, [rdi+40h]
0x180003ee0  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180003ee6  mov     eax, [rdi+0A0h]
0x180003eec  lea     r9, [rbp+arg_0]
0x180003ef0  mov     rcx, [rbp+arg_18]
0x180003ef4  mov     edx, 3
0x180003ef9  mov     r8, [rdi+98h]
0x180003f00  shr     eax, 1
0x180003f02  mov     [rbp+arg_0], eax
0x180003f05  mov     rax, [rcx]
0x180003f08  mov     rax, [rax+20h]
0x180003f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f11  mov     ebx, eax
0x180003f13  cmp     eax, 8007007Ah
0x180003f18  jnz     short loc_180003F5A
0x180003f1a  mov     edx, [rbp+arg_0]
0x180003f1d  lea     rcx, [rdi+78h]
0x180003f21  add     edx, edx
0x180003f23  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180003f29  mov     ebx, eax
0x180003f2b  test    eax, eax
0x180003f2d  js      short loc_180003F72
0x180003f2f  mov     eax, [rdi+0A0h]
0x180003f35  lea     r9, [rbp+arg_0]
0x180003f39  mov     rcx, [rbp+arg_18]
0x180003f3d  mov     edx, 3
0x180003f42  mov     r8, [rdi+98h]
0x180003f49  mov     [rbp+arg_0], eax
0x180003f4c  mov     rax, [rcx]
0x180003f4f  mov     rax, [rax+20h]
0x180003f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f58  mov     ebx, eax
0x180003f5a  test    ebx, ebx
0x180003f5c  js      short loc_180003F72
0x180003f5e  lea     rcx, [rdi+78h]
0x180003f62  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180003f68  xor     ebx, ebx
0x180003f6a  mov     [rdi+18h], rsi
0x180003f6e  mov     [rdi+38h], r15
0x180003f72  mov     rcx, [rbp+arg_18]
0x180003f76  test    rcx, rcx
0x180003f79  jz      short loc_180003F87
0x180003f7b  mov     rax, [rcx]
0x180003f7e  mov     rax, [rax+8]
0x180003f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f87  mov     eax, ebx
0x180003f89  mov     rbx, [rsp+30h+arg_8]
0x180003f8e  add     rsp, 30h
0x180003f92  pop     r15
0x180003f94  pop     r14
0x180003f96  pop     rdi
0x180003f97  pop     rsi
0x180003f98  pop     rbp
0x180003f99  retn
```
