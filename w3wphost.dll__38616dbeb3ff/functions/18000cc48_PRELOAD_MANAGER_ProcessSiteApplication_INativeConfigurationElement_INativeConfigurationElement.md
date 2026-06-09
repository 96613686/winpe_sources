# PRELOAD_MANAGER::ProcessSiteApplication(INativeConfigurationElement *,INativeConfigurationElement *)

- ea: `0x18000cc48`
- end: `0x18000cde3`
- name: `?ProcessSiteApplication@PRELOAD_MANAGER@@AEAAJPEAVINativeConfigurationElement@@0@Z`
- size: `411`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this, struct INativeConfigurationElement *, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000c578`

## callees

- `0x18000c320`
- `0x18000cc48`
- `0x18000d2f0`
- `0x18000e010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cd8a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cd8a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000cd5a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000cd74`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000cd5a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000cd74`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cc76`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cc96`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cc76`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cc96`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000cd40`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000cd40`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cdaa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cdba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cdaa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cdba`

## pseudocode

```c
__int64 __fastcall PRELOAD_MANAGER::ProcessSiteApplication(
        PRELOAD_MANAGER *this,
        struct INativeConfigurationElement *a2,
        struct INativeConfigurationElement *a3)
{
  __int64 v6; // rax
  int v7; // ebx
  const unsigned __int16 *Str; // rax
  unsigned int v10; // [rsp+30h] [rbp-59h] BYREF
  const unsigned __int16 *v11; // [rsp+38h] [rbp-51h] BYREF
  const unsigned __int16 *v12; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v13[56]; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v14[56]; // [rsp+80h] [rbp-9h] BYREF

  STRU::STRU((STRU *)v13);
  v11 = 0;
  v12 = 0;
  STRU::STRU((STRU *)v14);
  v6 = *(_QWORD *)a2;
  v10 = 0;
  v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(v6 + 64))(
         a2,
         L"name",
         &v11,
         0,
         0);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
           a2,
           L"id",
           &v10,
           0,
           0);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a3 + 64LL))(
             a3,
             L"path",
             &v12,
             0,
             0);
      if ( v7 >= 0 )
      {
        v7 = STRU::Copy((STRU *)v13, L"MACHINE/WEBROOT/APPHOST/");
        if ( v7 >= 0 )
        {
          v7 = STRU::Append((STRU *)v13, v11);
          if ( v7 >= 0 )
          {
            v7 = STRU::Append((STRU *)v13, v12);
            if ( v7 >= 0 )
            {
              Str = STRU::QueryStr((STRU *)v13);
              v7 = PRELOAD_MANAGER::NotifyApplicationPreload(this, v10, Str);
            }
          }
        }
      }
    }
  }
  STRU::~STRU((STRU *)v14);
  STRU::~STRU((STRU *)v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000cc48  push    rbp
0x18000cc4a  push    rbx
0x18000cc4b  push    rsi
0x18000cc4c  push    rdi
0x18000cc4d  push    r14
0x18000cc4f  lea     rbp, [rsp-37h]
0x18000cc54  sub     rsp, 0C0h
0x18000cc5b  mov     rax, cs:__security_cookie
0x18000cc62  xor     rax, rsp
0x18000cc65  mov     [rbp+57h+var_28], rax
0x18000cc69  mov     r14, rcx
0x18000cc6c  mov     rsi, r8
0x18000cc6f  lea     rcx, [rbp+57h+var_98]
0x18000cc73  mov     rdi, rdx
0x18000cc76  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000cc7d  nop     dword ptr [rax+rax+00h]
0x18000cc82  lea     rcx, [rbp+57h+var_60]
0x18000cc86  mov     [rbp+57h+var_A8], 0
0x18000cc8e  mov     [rbp+57h+var_A0], 0
0x18000cc96  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000cc9d  nop     dword ptr [rax+rax+00h]
0x18000cca2  mov     rax, [rdi]
0x18000cca5  lea     r8, [rbp+57h+var_A8]
0x18000cca9  xor     r9d, r9d
0x18000ccac  mov     [rbp+57h+var_B0], 0
0x18000ccb3  lea     rdx, aName; "name"
0x18000ccba  mov     [rsp+0E0h+var_C0], 0
0x18000ccc3  mov     rcx, rdi
0x18000ccc6  mov     rax, [rax+40h]
0x18000ccca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cccf  mov     ebx, eax
0x18000ccd1  test    eax, eax
0x18000ccd3  js      loc_18000CDA6
0x18000ccd9  mov     rax, [rdi]
0x18000ccdc  lea     r8, [rbp+57h+var_B0]
0x18000cce0  xor     r9d, r9d
0x18000cce3  mov     [rsp+0E0h+var_C0], 0
0x18000ccec  lea     rdx, aId; "id"
0x18000ccf3  mov     rcx, rdi
0x18000ccf6  mov     rax, [rax+30h]
0x18000ccfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccff  mov     ebx, eax
0x18000cd01  test    eax, eax
0x18000cd03  js      loc_18000CDA6
0x18000cd09  mov     rax, [rsi]
0x18000cd0c  lea     r8, [rbp+57h+var_A0]
0x18000cd10  xor     r9d, r9d
0x18000cd13  mov     [rsp+0E0h+var_C0], 0
0x18000cd1c  lea     rdx, aPath; "path"
0x18000cd23  mov     rcx, rsi
0x18000cd26  mov     rax, [rax+40h]
0x18000cd2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd2f  mov     ebx, eax
0x18000cd31  test    eax, eax
0x18000cd33  js      short loc_18000CDA6
0x18000cd35  lea     rdx, aMachineWebroot_1; "MACHINE/WEBROOT/APPHOST/"
0x18000cd3c  lea     rcx, [rbp+57h+var_98]
0x18000cd40  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000cd47  nop     dword ptr [rax+rax+00h]
0x18000cd4c  mov     ebx, eax
0x18000cd4e  test    eax, eax
0x18000cd50  js      short loc_18000CDA6
0x18000cd52  mov     rdx, [rbp+57h+var_A8]
0x18000cd56  lea     rcx, [rbp+57h+var_98]
0x18000cd5a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000cd61  nop     dword ptr [rax+rax+00h]
0x18000cd66  mov     ebx, eax
0x18000cd68  test    eax, eax
0x18000cd6a  js      short loc_18000CDA6
0x18000cd6c  mov     rdx, [rbp+57h+var_A0]
0x18000cd70  lea     rcx, [rbp+57h+var_98]
0x18000cd74  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000cd7b  nop     dword ptr [rax+rax+00h]
0x18000cd80  mov     ebx, eax
0x18000cd82  test    eax, eax
0x18000cd84  js      short loc_18000CDA6
0x18000cd86  lea     rcx, [rbp+57h+var_98]
0x18000cd8a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000cd91  nop     dword ptr [rax+rax+00h]
0x18000cd96  mov     edx, [rbp+57h+var_B0]; unsigned int
0x18000cd99  mov     rcx, r14; this
0x18000cd9c  mov     r8, rax; unsigned __int16 *
0x18000cd9f  call    ?NotifyApplicationPreload@PRELOAD_MANAGER@@AEAAJKPEBG@Z; PRELOAD_MANAGER::NotifyApplicationPreload(ulong,ushort const *)
0x18000cda4  mov     ebx, eax
0x18000cda6  lea     rcx, [rbp+57h+var_60]
0x18000cdaa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000cdb1  nop     dword ptr [rax+rax+00h]
0x18000cdb6  lea     rcx, [rbp+57h+var_98]
0x18000cdba  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000cdc1  nop     dword ptr [rax+rax+00h]
0x18000cdc6  mov     eax, ebx
0x18000cdc8  mov     rcx, [rbp+57h+var_28]
0x18000cdcc  xor     rcx, rsp; StackCookie
0x18000cdcf  call    __security_check_cookie
0x18000cdd4  add     rsp, 0C0h
0x18000cddb  pop     r14
0x18000cddd  pop     rdi
0x18000cdde  pop     rsi
0x18000cddf  pop     rbx
0x18000cde0  pop     rbp
0x18000cde1  retn
```
