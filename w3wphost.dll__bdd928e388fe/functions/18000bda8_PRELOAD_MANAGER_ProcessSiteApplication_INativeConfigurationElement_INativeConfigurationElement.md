# PRELOAD_MANAGER::ProcessSiteApplication(INativeConfigurationElement *,INativeConfigurationElement *)

- ea: `0x18000bda8`
- end: `0x18000bf12`
- name: `?ProcessSiteApplication@PRELOAD_MANAGER@@AEAAJPEAVINativeConfigurationElement@@0@Z`
- size: `362`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this, struct INativeConfigurationElement *, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000b744`

## callees

- `0x18000b50c`
- `0x18000bda8`
- `0x18000c3d0`
- `0x18000d010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000becc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000becc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bea8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bebc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bea8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bebc`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000bdd6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000bdf0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000bdd6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000bdf0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000be94`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000be94`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bee6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bef0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bee6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bef0`

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
0x18000bda8  push    rbp
0x18000bdaa  push    rbx
0x18000bdab  push    rsi
0x18000bdac  push    rdi
0x18000bdad  push    r14
0x18000bdaf  lea     rbp, [rsp-37h]
0x18000bdb4  sub     rsp, 0C0h
0x18000bdbb  mov     rax, cs:__security_cookie
0x18000bdc2  xor     rax, rsp
0x18000bdc5  mov     [rbp+57h+var_28], rax
0x18000bdc9  mov     r14, rcx
0x18000bdcc  mov     rsi, r8
0x18000bdcf  lea     rcx, [rbp+57h+var_98]
0x18000bdd3  mov     rdi, rdx
0x18000bdd6  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000bddc  lea     rcx, [rbp+57h+var_60]
0x18000bde0  mov     [rbp+57h+var_A8], 0
0x18000bde8  mov     [rbp+57h+var_A0], 0
0x18000bdf0  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000bdf6  mov     rax, [rdi]
0x18000bdf9  lea     r8, [rbp+57h+var_A8]
0x18000bdfd  xor     r9d, r9d
0x18000be00  mov     [rbp+57h+var_B0], 0
0x18000be07  lea     rdx, aName; "name"
0x18000be0e  mov     [rsp+0E0h+var_C0], 0
0x18000be17  mov     rcx, rdi
0x18000be1a  mov     rax, [rax+40h]
0x18000be1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be23  mov     ebx, eax
0x18000be25  test    eax, eax
0x18000be27  js      loc_18000BEE2
0x18000be2d  mov     rax, [rdi]
0x18000be30  lea     r8, [rbp+57h+var_B0]
0x18000be34  xor     r9d, r9d
0x18000be37  mov     [rsp+0E0h+var_C0], 0
0x18000be40  lea     rdx, aId; "id"
0x18000be47  mov     rcx, rdi
0x18000be4a  mov     rax, [rax+30h]
0x18000be4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be53  mov     ebx, eax
0x18000be55  test    eax, eax
0x18000be57  js      loc_18000BEE2
0x18000be5d  mov     rax, [rsi]
0x18000be60  lea     r8, [rbp+57h+var_A0]
0x18000be64  xor     r9d, r9d
0x18000be67  mov     [rsp+0E0h+var_C0], 0
0x18000be70  lea     rdx, aPath; "path"
0x18000be77  mov     rcx, rsi
0x18000be7a  mov     rax, [rax+40h]
0x18000be7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be83  mov     ebx, eax
0x18000be85  test    eax, eax
0x18000be87  js      short loc_18000BEE2
0x18000be89  lea     rdx, aMachineWebroot_1; "MACHINE/WEBROOT/APPHOST/"
0x18000be90  lea     rcx, [rbp+57h+var_98]
0x18000be94  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000be9a  mov     ebx, eax
0x18000be9c  test    eax, eax
0x18000be9e  js      short loc_18000BEE2
0x18000bea0  mov     rdx, [rbp+57h+var_A8]
0x18000bea4  lea     rcx, [rbp+57h+var_98]
0x18000bea8  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000beae  mov     ebx, eax
0x18000beb0  test    eax, eax
0x18000beb2  js      short loc_18000BEE2
0x18000beb4  mov     rdx, [rbp+57h+var_A0]
0x18000beb8  lea     rcx, [rbp+57h+var_98]
0x18000bebc  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000bec2  mov     ebx, eax
0x18000bec4  test    eax, eax
0x18000bec6  js      short loc_18000BEE2
0x18000bec8  lea     rcx, [rbp+57h+var_98]
0x18000becc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bed2  mov     edx, [rbp+57h+var_B0]; unsigned int
0x18000bed5  mov     rcx, r14; this
0x18000bed8  mov     r8, rax; unsigned __int16 *
0x18000bedb  call    ?NotifyApplicationPreload@PRELOAD_MANAGER@@AEAAJKPEBG@Z; PRELOAD_MANAGER::NotifyApplicationPreload(ulong,ushort const *)
0x18000bee0  mov     ebx, eax
0x18000bee2  lea     rcx, [rbp+57h+var_60]
0x18000bee6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000beec  lea     rcx, [rbp+57h+var_98]
0x18000bef0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000bef6  mov     eax, ebx
0x18000bef8  mov     rcx, [rbp+57h+var_28]
0x18000befc  xor     rcx, rsp; StackCookie
0x18000beff  call    __security_check_cookie
0x18000bf04  add     rsp, 0C0h
0x18000bf0b  pop     r14
0x18000bf0d  pop     rdi
0x18000bf0e  pop     rsi
0x18000bf0f  pop     rbx
0x18000bf10  pop     rbp
0x18000bf11  retn
```
