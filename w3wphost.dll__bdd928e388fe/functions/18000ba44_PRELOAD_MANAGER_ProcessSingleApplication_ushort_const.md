# PRELOAD_MANAGER::ProcessSingleApplication(ushort const *)

- ea: `0x18000ba44`
- end: `0x18000bda2`
- name: `?ProcessSingleApplication@PRELOAD_MANAGER@@AEAAJPEBG@Z`
- size: `862`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x18000b670`

## callees

- `0x18000b50c`
- `0x18000ba44`
- `0x18000c39e`
- `0x18000c3d0`
- `0x18000d010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000bc13`
- `msvcrt!_wcsicmp` at `0x18000bc13`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bb91`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bcaa`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bcea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bd13`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bb91`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bcaa`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bcea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bd13`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bcb8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bcce`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bcb8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bcce`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bab6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000badc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bab6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000badc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000bc96`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000bc96`
- `iisutil!SkipTo` at `0x18000bb1d`
- `iisutil!SkipTo` at `0x18000bb1d`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000bb71`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000bb71`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bd65`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bd6f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bd65`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bd6f`

## string_xrefs

- `0x18000bc33`: `serviceAutoStartEnabled`

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
0x18000ba44  mov     [rsp-8+arg_10], rbx
0x18000ba49  mov     [rsp-8+arg_18], rsi
0x18000ba4e  push    rbp
0x18000ba4f  push    rdi
0x18000ba50  push    r12
0x18000ba52  push    r14
0x18000ba54  push    r15
0x18000ba56  lea     rbp, [rsp-400h]
0x18000ba5e  sub     rsp, 500h
0x18000ba65  mov     rax, cs:__security_cookie
0x18000ba6c  xor     rax, rsp
0x18000ba6f  mov     [rbp+420h+var_30], rax
0x18000ba76  xor     r15d, r15d
0x18000ba79  mov     rdi, rdx
0x18000ba7c  mov     r14, rcx
0x18000ba7f  mov     [rsp+520h+var_4D0], r15
0x18000ba84  mov     esi, 200h
0x18000ba89  mov     [rsp+520h+var_4C8], r15
0x18000ba8e  mov     r8d, esi; Size
0x18000ba91  mov     [rsp+520h+var_4B0], r15
0x18000ba96  xor     edx, edx; Val
0x18000ba98  mov     [rsp+520h+var_4C0], r15d
0x18000ba9d  lea     rcx, [rbp+420h+var_430]; void *
0x18000baa1  call    memset_0
0x18000baa6  mov     ebx, 100h
0x18000baab  lea     rdx, [rbp+420h+var_430]
0x18000baaf  mov     r8d, ebx
0x18000bab2  lea     rcx, [rbp+420h+var_470]
0x18000bab6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000babc  mov     r8d, esi; Size
0x18000babf  lea     rcx, [rbp+420h+var_230]; void *
0x18000bac6  xor     edx, edx; Val
0x18000bac8  call    memset_0
0x18000bacd  mov     r8d, ebx
0x18000bad0  lea     rdx, [rbp+420h+var_230]
0x18000bad7  lea     rcx, [rsp+520h+var_4A8]
0x18000badc  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000bae2  mov     rcx, [r14+30h]
0x18000bae6  lea     rdx, [rsp+520h+var_4D0]
0x18000baeb  mov     [rsp+520h+var_4BC], r15d
0x18000baf0  mov     [rsp+520h+String2], r15
0x18000baf5  mov     rax, [rcx]
0x18000baf8  mov     rax, [rax+38h]
0x18000bafc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb01  mov     ebx, eax
0x18000bb03  test    eax, eax
0x18000bb05  js      loc_18000BD2A
0x18000bb0b  mov     ebx, r15d
0x18000bb0e  lea     r12d, [r15+2Fh]
0x18000bb12  cmp     ebx, 3
0x18000bb15  jge     short loc_18000BB42
0x18000bb17  mov     edx, r12d
0x18000bb1a  mov     rcx, rdi
0x18000bb1d  call    cs:__imp_?SkipTo@@YAPEAGPEAGG@Z; SkipTo(ushort *,ushort)
0x18000bb23  mov     rdi, rax
0x18000bb26  test    rax, rax
0x18000bb29  jz      short loc_18000BB33
0x18000bb2b  add     rdi, 2
0x18000bb2f  inc     ebx
0x18000bb31  jmp     short loc_18000BB12
0x18000bb33  cmp     ebx, 2
0x18000bb36  jz      short loc_18000BB42
0x18000bb38  mov     ebx, 80070003h
0x18000bb3d  jmp     loc_18000BD2A
0x18000bb42  movzx   eax, word ptr [rdi]
0x18000bb45  mov     rsi, rdi
0x18000bb48  jmp     short loc_18000BB5C
0x18000bb4a  cmp     ax, r12w
0x18000bb4e  jz      short loc_18000BB61
0x18000bb50  test    ax, ax
0x18000bb53  jz      short loc_18000BB61
0x18000bb55  add     rsi, 2
0x18000bb59  movzx   eax, word ptr [rsi]
0x18000bb5c  test    ax, ax
0x18000bb5f  jnz     short loc_18000BB4A
0x18000bb61  mov     r8, rsi
0x18000bb64  lea     rcx, [rbp+420h+var_470]
0x18000bb68  sub     r8, rdi
0x18000bb6b  mov     rdx, rdi
0x18000bb6e  sar     r8, 1
0x18000bb71  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000bb77  mov     ebx, eax
0x18000bb79  test    eax, eax
0x18000bb7b  js      loc_18000BD2A
0x18000bb81  mov     rax, [rsp+520h+var_4D0]
0x18000bb86  mov     rcx, [rax]
0x18000bb89  mov     rbx, [rcx+28h]
0x18000bb8d  lea     rcx, [rbp+420h+var_470]
0x18000bb91  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bb97  mov     [rsp+520h+var_4E8], r15
0x18000bb9c  lea     rcx, [rsp+520h+var_4C8]
0x18000bba1  mov     [rsp+520h+var_4F0], rcx
0x18000bba6  mov     rdx, rax
0x18000bba9  mov     rcx, [rsp+520h+var_4D0]
0x18000bbae  xor     r9d, r9d
0x18000bbb1  mov     [rsp+520h+var_4F8], r15
0x18000bbb6  mov     r8, rsi
0x18000bbb9  mov     rax, rbx
0x18000bbbc  mov     [rsp+520h+var_500], r15
0x18000bbc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbc6  mov     ebx, eax
0x18000bbc8  test    eax, eax
0x18000bbca  js      loc_18000BD2A
0x18000bbd0  mov     rcx, [rsp+520h+var_4C8]
0x18000bbd5  lea     r8, [rsp+520h+String2]
0x18000bbda  xor     r9d, r9d
0x18000bbdd  mov     [rsp+520h+var_500], r15
0x18000bbe2  lea     rdx, aApplicationpoo; "applicationPool"
0x18000bbe9  mov     rax, [rcx]
0x18000bbec  mov     rax, [rax+40h]
0x18000bbf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbf5  mov     ebx, eax
0x18000bbf7  test    eax, eax
0x18000bbf9  js      loc_18000BD2A
0x18000bbff  mov     rax, [r14+20h]
0x18000bc03  mov     rdx, [rsp+520h+String2]; String2
0x18000bc08  mov     rcx, [rax+138h]
0x18000bc0f  mov     rcx, [rcx+18h]; String1
0x18000bc13  call    cs:__imp__wcsicmp
0x18000bc19  test    eax, eax
0x18000bc1b  jnz     loc_18000BD2A
0x18000bc21  mov     rcx, [rsp+520h+var_4C8]
0x18000bc26  lea     r8, [rsp+520h+var_4C0]
0x18000bc2b  xor     r9d, r9d
0x18000bc2e  mov     [rsp+520h+var_500], r15
0x18000bc33  lea     rdx, aServiceautosta; "serviceAutoStartEnabled"
0x18000bc3a  mov     rax, [rcx]
0x18000bc3d  mov     rax, [rax+48h]
0x18000bc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc46  mov     ebx, eax
0x18000bc48  test    eax, eax
0x18000bc4a  js      loc_18000BD2A
0x18000bc50  cmp     [rsp+520h+var_4C0], r15d
0x18000bc55  jz      loc_18000BD2A
0x18000bc5b  mov     rcx, [rsp+520h+var_4C8]
0x18000bc60  lea     r8, [rsp+520h+var_4B0]
0x18000bc65  xor     r9d, r9d
0x18000bc68  mov     [rsp+520h+var_500], r15
0x18000bc6d  lea     rdx, aPath; "path"
0x18000bc74  mov     rax, [rcx]
0x18000bc77  mov     rax, [rax+40h]
0x18000bc7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc80  mov     ebx, eax
0x18000bc82  test    eax, eax
0x18000bc84  js      loc_18000BD2A
0x18000bc8a  lea     rdx, aMachineWebroot_1; "MACHINE/WEBROOT/APPHOST/"
0x18000bc91  lea     rcx, [rsp+520h+var_4A8]
0x18000bc96  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000bc9c  mov     ebx, eax
0x18000bc9e  test    eax, eax
0x18000bca0  js      loc_18000BD2A
0x18000bca6  lea     rcx, [rbp+420h+var_470]
0x18000bcaa  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bcb0  mov     rdx, rax
0x18000bcb3  lea     rcx, [rsp+520h+var_4A8]
0x18000bcb8  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000bcbe  mov     ebx, eax
0x18000bcc0  test    eax, eax
0x18000bcc2  js      short loc_18000BD2A
0x18000bcc4  mov     rdx, [rsp+520h+var_4B0]
0x18000bcc9  lea     rcx, [rsp+520h+var_4A8]
0x18000bcce  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000bcd4  mov     ebx, eax
0x18000bcd6  test    eax, eax
0x18000bcd8  js      short loc_18000BD2A
0x18000bcda  mov     rax, [rsp+520h+var_4D0]
0x18000bcdf  mov     rcx, [rax]
0x18000bce2  mov     rbx, [rcx+30h]
0x18000bce6  lea     rcx, [rbp+420h+var_470]
0x18000bcea  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bcf0  mov     rcx, [rsp+520h+var_4D0]
0x18000bcf5  lea     r8, [rsp+520h+var_4BC]
0x18000bcfa  mov     rdx, rax
0x18000bcfd  xor     r9d, r9d
0x18000bd00  mov     rax, rbx
0x18000bd03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd08  mov     ebx, eax
0x18000bd0a  test    eax, eax
0x18000bd0c  js      short loc_18000BD2A
0x18000bd0e  lea     rcx, [rsp+520h+var_4A8]
0x18000bd13  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bd19  mov     edx, [rsp+520h+var_4BC]; unsigned int
0x18000bd1d  mov     rcx, r14; this
0x18000bd20  mov     r8, rax; unsigned __int16 *
0x18000bd23  call    ?NotifyApplicationPreload@PRELOAD_MANAGER@@AEAAJKPEBG@Z; PRELOAD_MANAGER::NotifyApplicationPreload(ulong,ushort const *)
0x18000bd28  mov     ebx, eax
0x18000bd2a  mov     rcx, [rsp+520h+var_4C8]
0x18000bd2f  test    rcx, rcx
0x18000bd32  jz      short loc_18000BD45
0x18000bd34  mov     rax, [rcx]
0x18000bd37  mov     rax, [rax+10h]
0x18000bd3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd40  mov     [rsp+520h+var_4C8], r15
0x18000bd45  mov     rcx, [rsp+520h+var_4D0]
0x18000bd4a  test    rcx, rcx
0x18000bd4d  jz      short loc_18000BD60
0x18000bd4f  mov     rax, [rcx]
0x18000bd52  mov     rax, [rax+10h]
0x18000bd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd5b  mov     [rsp+520h+var_4D0], r15
0x18000bd60  lea     rcx, [rsp+520h+var_4A8]
0x18000bd65  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000bd6b  lea     rcx, [rbp+420h+var_470]
0x18000bd6f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000bd75  mov     eax, ebx
0x18000bd77  mov     rcx, [rbp+420h+var_30]
0x18000bd7e  xor     rcx, rsp; StackCookie
0x18000bd81  call    __security_check_cookie
0x18000bd86  lea     r11, [rsp+520h+var_20]
0x18000bd8e  mov     rbx, [r11+40h]
0x18000bd92  mov     rsi, [r11+48h]
0x18000bd96  mov     rsp, r11
0x18000bd99  pop     r15
0x18000bd9b  pop     r14
0x18000bd9d  pop     r12
0x18000bd9f  pop     rdi
0x18000bda0  pop     rbp
0x18000bda1  retn
```
