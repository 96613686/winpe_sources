# PRELOAD_MANAGER::ProcessSingleApplication(ushort const *)

- ea: `0x18000c88c`
- end: `0x18000cc3f`
- name: `?ProcessSingleApplication@PRELOAD_MANAGER@@AEAAJPEBG@Z`
- size: `947`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x18000c490`

## callees

- `0x18000c320`
- `0x18000c88c`
- `0x18000d2be`
- `0x18000d2f0`
- `0x18000e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ca79`
- `msvcrt!_wcsicmp` at `0x18000ca79`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c9f1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cb1c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cb6e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cb9d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c9f1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cb1c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cb6e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cb9d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000cb30`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000cb4c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000cb30`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000cb4c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c8fe`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c92a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c8fe`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c92a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000cb02`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000cb02`
- `iisutil!SkipTo` at `0x18000c971`
- `iisutil!SkipTo` at `0x18000c971`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000c9cb`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000c9cb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cbf5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cc05`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cbf5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cc05`

## string_xrefs

- `0x18000ca9f`: `serviceAutoStartEnabled`

## pseudocode

```c
__int64 __fastcall PRELOAD_MANAGER::ProcessSingleApplication(PRELOAD_MANAGER *this, unsigned __int16 *a2)
{
  __int64 v4; // rcx
  int v5; // ebx
  int i; // ebx
  unsigned __int16 *v7; // rax
  unsigned __int16 v8; // ax
  unsigned __int16 *v9; // rsi
  __int64 (__fastcall *v10)(__int64, unsigned __int16 *, unsigned __int16 *, _QWORD, _QWORD, _QWORD, __int64 *, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  const unsigned __int16 *v12; // rax
  __int64 (__fastcall *v13)(__int64, unsigned __int16 *, unsigned int *, _QWORD); // rbx
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // rax
  __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v20; // [rsp+64h] [rbp-9Ch] BYREF
  wchar_t *String2; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v22; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[56]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v24[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v25[256]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v26[256]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v17 = 0;
  v18 = 0;
  v22 = 0;
  v19 = 0;
  memset_0(v25, 0, sizeof(v25));
  STRU::STRU((STRU *)v24, v25, 0x100u);
  memset_0(v26, 0, sizeof(v26));
  STRU::STRU((STRU *)v23, v26, 0x100u);
  v4 = *((_QWORD *)this + 6);
  v20 = 0;
  String2 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 56LL))(v4, &v17);
  if ( v5 >= 0 )
  {
    for ( i = 0; i < 3; ++i )
    {
      v7 = SkipTo(a2, 0x2Fu);
      a2 = v7;
      if ( !v7 )
      {
        if ( i != 2 )
        {
          v5 = -2147024893;
          goto LABEL_24;
        }
        break;
      }
      a2 = v7 + 1;
    }
    v8 = *a2;
    v9 = a2;
    while ( v8 && v8 != 47 )
      v8 = *++v9;
    v5 = STRU::Copy((STRU *)v24, a2, v9 - a2);
    if ( v5 >= 0 )
    {
      v10 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, _QWORD, _QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v17 + 40LL);
      Str = STRU::QueryStr((STRU *)v24);
      v5 = v10(v17, Str, v9, 0, 0, 0, &v18, 0);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v18 + 64LL))(
               v18,
               L"applicationPool",
               &String2,
               0,
               0);
        if ( v5 >= 0 && !_wcsicmp(*(const wchar_t **)(*(_QWORD *)(*((_QWORD *)this + 4) + 312LL) + 24LL), String2) )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v18 + 72LL))(
                 v18,
                 L"serviceAutoStartEnabled",
                 &v19,
                 0,
                 0);
          if ( v5 >= 0 )
          {
            if ( v19 )
            {
              v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v18 + 64LL))(
                     v18,
                     L"path",
                     &v22,
                     0,
                     0);
              if ( v5 >= 0 )
              {
                v5 = STRU::Copy((STRU *)v23, L"MACHINE/WEBROOT/APPHOST/");
                if ( v5 >= 0 )
                {
                  v12 = STRU::QueryStr((STRU *)v24);
                  v5 = STRU::Append((STRU *)v23, v12);
                  if ( v5 >= 0 )
                  {
                    v5 = STRU::Append((STRU *)v23, v22);
                    if ( v5 >= 0 )
                    {
                      v13 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)v17 + 48LL);
                      v14 = STRU::QueryStr((STRU *)v24);
                      v5 = v13(v17, v14, &v20, 0);
                      if ( v5 >= 0 )
                      {
                        v15 = STRU::QueryStr((STRU *)v23);
                        v5 = PRELOAD_MANAGER::NotifyApplicationPreload(this, v20, v15);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_24:
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  STRU::~STRU((STRU *)v23);
  STRU::~STRU((STRU *)v24);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000c88c  mov     [rsp-8+arg_10], rbx
0x18000c891  mov     [rsp-8+arg_18], rsi
0x18000c896  push    rbp
0x18000c897  push    rdi
0x18000c898  push    r12
0x18000c89a  push    r14
0x18000c89c  push    r15
0x18000c89e  lea     rbp, [rsp-400h]
0x18000c8a6  sub     rsp, 500h
0x18000c8ad  mov     rax, cs:__security_cookie
0x18000c8b4  xor     rax, rsp
0x18000c8b7  mov     [rbp+420h+var_30], rax
0x18000c8be  xor     r15d, r15d
0x18000c8c1  mov     rdi, rdx
0x18000c8c4  mov     r14, rcx
0x18000c8c7  mov     [rsp+520h+var_4D0], r15
0x18000c8cc  mov     esi, 200h
0x18000c8d1  mov     [rsp+520h+var_4C8], r15
0x18000c8d6  mov     r8d, esi; Size
0x18000c8d9  mov     [rsp+520h+var_4B0], r15
0x18000c8de  xor     edx, edx; Val
0x18000c8e0  mov     [rsp+520h+var_4C0], r15d
0x18000c8e5  lea     rcx, [rbp+420h+var_430]; void *
0x18000c8e9  call    memset_0
0x18000c8ee  mov     ebx, 100h
0x18000c8f3  lea     rdx, [rbp+420h+var_430]
0x18000c8f7  mov     r8d, ebx
0x18000c8fa  lea     rcx, [rbp+420h+var_470]
0x18000c8fe  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000c905  nop     dword ptr [rax+rax+00h]
0x18000c90a  mov     r8d, esi; Size
0x18000c90d  lea     rcx, [rbp+420h+var_230]; void *
0x18000c914  xor     edx, edx; Val
0x18000c916  call    memset_0
0x18000c91b  mov     r8d, ebx
0x18000c91e  lea     rdx, [rbp+420h+var_230]
0x18000c925  lea     rcx, [rsp+520h+var_4A8]
0x18000c92a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000c931  nop     dword ptr [rax+rax+00h]
0x18000c936  mov     rcx, [r14+30h]
0x18000c93a  lea     rdx, [rsp+520h+var_4D0]
0x18000c93f  mov     [rsp+520h+var_4BC], r15d
0x18000c944  mov     [rsp+520h+String2], r15
0x18000c949  mov     rax, [rcx]
0x18000c94c  mov     rax, [rax+38h]
0x18000c950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c955  mov     ebx, eax
0x18000c957  test    eax, eax
0x18000c959  js      loc_18000CBBA
0x18000c95f  mov     ebx, r15d
0x18000c962  lea     r12d, [r15+2Fh]
0x18000c966  cmp     ebx, 3
0x18000c969  jge     short loc_18000C99C
0x18000c96b  mov     edx, r12d
0x18000c96e  mov     rcx, rdi
0x18000c971  call    cs:__imp_?SkipTo@@YAPEAGPEAGG@Z; SkipTo(ushort *,ushort)
0x18000c978  nop     dword ptr [rax+rax+00h]
0x18000c97d  mov     rdi, rax
0x18000c980  test    rax, rax
0x18000c983  jz      short loc_18000C98D
0x18000c985  add     rdi, 2
0x18000c989  inc     ebx
0x18000c98b  jmp     short loc_18000C966
0x18000c98d  cmp     ebx, 2
0x18000c990  jz      short loc_18000C99C
0x18000c992  mov     ebx, 80070003h
0x18000c997  jmp     loc_18000CBBA
0x18000c99c  movzx   eax, word ptr [rdi]
0x18000c99f  mov     rsi, rdi
0x18000c9a2  jmp     short loc_18000C9B6
0x18000c9a4  cmp     ax, r12w
0x18000c9a8  jz      short loc_18000C9BB
0x18000c9aa  test    ax, ax
0x18000c9ad  jz      short loc_18000C9BB
0x18000c9af  add     rsi, 2
0x18000c9b3  movzx   eax, word ptr [rsi]
0x18000c9b6  test    ax, ax
0x18000c9b9  jnz     short loc_18000C9A4
0x18000c9bb  mov     r8, rsi
0x18000c9be  lea     rcx, [rbp+420h+var_470]
0x18000c9c2  sub     r8, rdi
0x18000c9c5  mov     rdx, rdi
0x18000c9c8  sar     r8, 1
0x18000c9cb  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000c9d2  nop     dword ptr [rax+rax+00h]
0x18000c9d7  mov     ebx, eax
0x18000c9d9  test    eax, eax
0x18000c9db  js      loc_18000CBBA
0x18000c9e1  mov     rax, [rsp+520h+var_4D0]
0x18000c9e6  mov     rcx, [rax]
0x18000c9e9  mov     rbx, [rcx+28h]
0x18000c9ed  lea     rcx, [rbp+420h+var_470]
0x18000c9f1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c9f8  nop     dword ptr [rax+rax+00h]
0x18000c9fd  mov     [rsp+520h+var_4E8], r15
0x18000ca02  lea     rcx, [rsp+520h+var_4C8]
0x18000ca07  mov     [rsp+520h+var_4F0], rcx
0x18000ca0c  mov     rdx, rax
0x18000ca0f  mov     rcx, [rsp+520h+var_4D0]
0x18000ca14  xor     r9d, r9d
0x18000ca17  mov     [rsp+520h+var_4F8], r15
0x18000ca1c  mov     r8, rsi
0x18000ca1f  mov     rax, rbx
0x18000ca22  mov     [rsp+520h+var_500], r15
0x18000ca27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca2c  mov     ebx, eax
0x18000ca2e  test    eax, eax
0x18000ca30  js      loc_18000CBBA
0x18000ca36  mov     rcx, [rsp+520h+var_4C8]
0x18000ca3b  lea     r8, [rsp+520h+String2]
0x18000ca40  xor     r9d, r9d
0x18000ca43  mov     [rsp+520h+var_500], r15
0x18000ca48  lea     rdx, String1; "applicationPool"
0x18000ca4f  mov     rax, [rcx]
0x18000ca52  mov     rax, [rax+40h]
0x18000ca56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca5b  mov     ebx, eax
0x18000ca5d  test    eax, eax
0x18000ca5f  js      loc_18000CBBA
0x18000ca65  mov     rax, [r14+20h]
0x18000ca69  mov     rdx, [rsp+520h+String2]; String2
0x18000ca6e  mov     rcx, [rax+138h]
0x18000ca75  mov     rcx, [rcx+18h]; String1
0x18000ca79  call    cs:__imp__wcsicmp
0x18000ca80  nop     dword ptr [rax+rax+00h]
0x18000ca85  test    eax, eax
0x18000ca87  jnz     loc_18000CBBA
0x18000ca8d  mov     rcx, [rsp+520h+var_4C8]
0x18000ca92  lea     r8, [rsp+520h+var_4C0]
0x18000ca97  xor     r9d, r9d
0x18000ca9a  mov     [rsp+520h+var_500], r15
0x18000ca9f  lea     rdx, aServiceautosta; "serviceAutoStartEnabled"
0x18000caa6  mov     rax, [rcx]
0x18000caa9  mov     rax, [rax+48h]
0x18000caad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cab2  mov     ebx, eax
0x18000cab4  test    eax, eax
0x18000cab6  js      loc_18000CBBA
0x18000cabc  cmp     [rsp+520h+var_4C0], r15d
0x18000cac1  jz      loc_18000CBBA
0x18000cac7  mov     rcx, [rsp+520h+var_4C8]
0x18000cacc  lea     r8, [rsp+520h+var_4B0]
0x18000cad1  xor     r9d, r9d
0x18000cad4  mov     [rsp+520h+var_500], r15
0x18000cad9  lea     rdx, aPath; "path"
0x18000cae0  mov     rax, [rcx]
0x18000cae3  mov     rax, [rax+40h]
0x18000cae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000caec  mov     ebx, eax
0x18000caee  test    eax, eax
0x18000caf0  js      loc_18000CBBA
0x18000caf6  lea     rdx, aMachineWebroot_1; "MACHINE/WEBROOT/APPHOST/"
0x18000cafd  lea     rcx, [rsp+520h+var_4A8]
0x18000cb02  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000cb09  nop     dword ptr [rax+rax+00h]
0x18000cb0e  mov     ebx, eax
0x18000cb10  test    eax, eax
0x18000cb12  js      loc_18000CBBA
0x18000cb18  lea     rcx, [rbp+420h+var_470]
0x18000cb1c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000cb23  nop     dword ptr [rax+rax+00h]
0x18000cb28  mov     rdx, rax
0x18000cb2b  lea     rcx, [rsp+520h+var_4A8]
0x18000cb30  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000cb37  nop     dword ptr [rax+rax+00h]
0x18000cb3c  mov     ebx, eax
0x18000cb3e  test    eax, eax
0x18000cb40  js      short loc_18000CBBA
0x18000cb42  mov     rdx, [rsp+520h+var_4B0]
0x18000cb47  lea     rcx, [rsp+520h+var_4A8]
0x18000cb4c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000cb53  nop     dword ptr [rax+rax+00h]
0x18000cb58  mov     ebx, eax
0x18000cb5a  test    eax, eax
0x18000cb5c  js      short loc_18000CBBA
0x18000cb5e  mov     rax, [rsp+520h+var_4D0]
0x18000cb63  mov     rcx, [rax]
0x18000cb66  mov     rbx, [rcx+30h]
0x18000cb6a  lea     rcx, [rbp+420h+var_470]
0x18000cb6e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000cb75  nop     dword ptr [rax+rax+00h]
0x18000cb7a  mov     rcx, [rsp+520h+var_4D0]
0x18000cb7f  lea     r8, [rsp+520h+var_4BC]
0x18000cb84  mov     rdx, rax
0x18000cb87  xor     r9d, r9d
0x18000cb8a  mov     rax, rbx
0x18000cb8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb92  mov     ebx, eax
0x18000cb94  test    eax, eax
0x18000cb96  js      short loc_18000CBBA
0x18000cb98  lea     rcx, [rsp+520h+var_4A8]
0x18000cb9d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000cba4  nop     dword ptr [rax+rax+00h]
0x18000cba9  mov     edx, [rsp+520h+var_4BC]; unsigned int
0x18000cbad  mov     rcx, r14; this
0x18000cbb0  mov     r8, rax; unsigned __int16 *
0x18000cbb3  call    ?NotifyApplicationPreload@PRELOAD_MANAGER@@AEAAJKPEBG@Z; PRELOAD_MANAGER::NotifyApplicationPreload(ulong,ushort const *)
0x18000cbb8  mov     ebx, eax
0x18000cbba  mov     rcx, [rsp+520h+var_4C8]
0x18000cbbf  test    rcx, rcx
0x18000cbc2  jz      short loc_18000CBD5
0x18000cbc4  mov     rax, [rcx]
0x18000cbc7  mov     rax, [rax+10h]
0x18000cbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbd0  mov     [rsp+520h+var_4C8], r15
0x18000cbd5  mov     rcx, [rsp+520h+var_4D0]
0x18000cbda  test    rcx, rcx
0x18000cbdd  jz      short loc_18000CBF0
0x18000cbdf  mov     rax, [rcx]
0x18000cbe2  mov     rax, [rax+10h]
0x18000cbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbeb  mov     [rsp+520h+var_4D0], r15
0x18000cbf0  lea     rcx, [rsp+520h+var_4A8]
0x18000cbf5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000cbfc  nop     dword ptr [rax+rax+00h]
0x18000cc01  lea     rcx, [rbp+420h+var_470]
0x18000cc05  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000cc0c  nop     dword ptr [rax+rax+00h]
0x18000cc11  mov     eax, ebx
0x18000cc13  mov     rcx, [rbp+420h+var_30]
0x18000cc1a  xor     rcx, rsp; StackCookie
0x18000cc1d  call    __security_check_cookie
0x18000cc22  lea     r11, [rsp+520h+var_20]
0x18000cc2a  mov     rbx, [r11+40h]
0x18000cc2e  mov     rsi, [r11+48h]
0x18000cc32  mov     rsp, r11
0x18000cc35  pop     r15
0x18000cc37  pop     r14
0x18000cc39  pop     r12
0x18000cc3b  pop     rdi
0x18000cc3c  pop     rbp
0x18000cc3d  retn
```
