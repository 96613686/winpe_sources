# CredStore::StoreAlias(ushort const *,User const &,ushort *)

- ea: `0x180005b98`
- end: `0x180005f76`
- name: `?StoreAlias@CredStore@@QEAAJPEBGAEBVUser@@PEAG@Z`
- size: `990`
- prototype: `__int64 __fastcall(CredStore *__hidden this, const unsigned __int16 *, const struct User *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800157e0`

## callees

- `0x180003dac`
- `0x180003ef0`
- `0x180004e50`
- `0x180004fbc`
- `0x180005b98`
- `0x180005f7c`
- `0x180006e6c`
- `0x1800074c8`
- `0x1800074d4`
- `0x18001724c`
- `0x180017454`
- `0x180017b90`
- `0x18001aacc`
- `0x18001af08`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005eb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005eb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ceb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005d0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005f04`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005f04`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005ce1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005ce1`

## string_xrefs

- `0x180005ef9`: `AtServiceAccount`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CredStore::StoreAlias(
        CredStore *this,
        const unsigned __int16 *a2,
        const struct User *a3,
        unsigned __int16 *a4)
{
  _BYTE *v6; // r8
  _BYTE *v8; // r8
  signed int updated; // esi
  _BYTE *v10; // rcx
  __int64 v11; // rax
  unsigned int v12; // ebx
  signed int LastError; // eax
  const unsigned __int16 **v14; // rsi
  const unsigned __int16 *v15; // rax
  __int64 v16; // r15
  _QWORD *v17; // rdi
  __int64 v18; // rax
  __int64 v19; // r12
  __int64 v20; // rax
  __int64 v21; // r13
  unsigned __int16 *v22; // rax
  BYTE *lpData; // rbx
  const unsigned __int16 *v24; // r8
  __int64 v25; // r11
  const unsigned __int16 *v26; // r8
  __int64 v27; // r10
  __int64 v28; // r10
  __int64 v29; // r11
  __int64 v30; // r11
  CredStore *v31; // r15
  struct _RTL_CRITICAL_SECTION *v32; // rdi
  CredStore *v33; // rcx
  bool v34; // r9
  int v35; // eax
  LSTATUS v36; // eax
  const unsigned __int16 **v37; // [rsp+30h] [rbp-59h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-51h] BYREF
  PSID Sid; // [rsp+40h] [rbp-49h] BYREF
  _QWORD *v40; // [rsp+48h] [rbp-41h] BYREF
  CredStore *v41; // [rsp+50h] [rbp-39h]
  _BYTE v42[8]; // [rsp+58h] [rbp-31h] BYREF
  HLOCAL (__stdcall *v43)(HLOCAL); // [rsp+60h] [rbp-29h]
  LPWSTR v44; // [rsp+68h] [rbp-21h]
  unsigned __int16 *v45; // [rsp+70h] [rbp-19h]
  unsigned __int64 v46; // [rsp+78h] [rbp-11h]
  unsigned __int16 *v47; // [rsp+80h] [rbp-9h]
  unsigned __int16 v48; // [rsp+88h] [rbp-1h] BYREF
  __int128 v49; // [rsp+8Ah] [rbp+1h]
  __int64 v50; // [rsp+9Ah] [rbp+11h]

  v45 = a4;
  v41 = this;
  v6 = *(_BYTE **)a3;
  if ( !v6 )
    return 2147942487LL;
  v40 = 0;
  if ( !(unsigned __int8)_bstr_t::operator!(v6 + 16) && !(unsigned __int8)_bstr_t::operator!(v8 + 24) )
  {
LABEL_8:
    _bstr_t::operator=((_bstr_t *)&v40, *(_QWORD *)a3 + 16LL);
    v37 = 0;
    v10 = *(_BYTE **)a3;
    if ( !*(_QWORD *)a3 || *v10 )
      goto LABEL_9;
    if ( (unsigned __int8)_bstr_t::operator!(v10 + 24) )
    {
      updated = User::UpdateEntry(a3);
      if ( updated < 0 )
        goto LABEL_58;
    }
    _bstr_t::operator=((_bstr_t *)&v37, *(_QWORD *)a3 + 24LL);
    v11 = *(_QWORD *)a3;
    if ( !*(_QWORD *)a3 || *(_BYTE *)v11 )
    {
LABEL_9:
      updated = -2147418113;
    }
    else if ( *(_DWORD *)(v11 + 40) != 8 || (updated = User::UpdateEntry(a3), updated >= 0) )
    {
      v12 = *(_DWORD *)(*(_QWORD *)a3 + 40LL);
      Sid = 0;
      updated = User::LookupSid(a3, &Sid);
      if ( updated >= 0 )
      {
        updated = CredStore::InitAliasesKey(this);
        if ( updated >= 0 )
        {
          StringSid = 0;
          if ( ConvertSidToStringSidW(Sid, &StringSid) )
          {
            v42[0] = 0;
            v43 = LocalFree;
            v44 = StringSid;
            v48 = 0;
            v49 = 0;
            v50 = 0;
            StringCchPrintfW(&v48, 0xDu, L"%d", v12);
            v14 = v37;
            if ( v37 )
              v15 = *v37;
            else
              v15 = 0;
            v16 = -1;
            do
              ++v16;
            while ( v15[v16] );
            v17 = v40;
            if ( v40 )
              v18 = *v40;
            else
              v18 = 0;
            v19 = -1;
            do
              ++v19;
            while ( *(_WORD *)(v18 + 2 * v19) );
            v20 = -1;
            do
              ++v20;
            while ( *(&v48 + v20) );
            Sid = (PSID)v20;
            v21 = -1;
            do
              ++v21;
            while ( StringSid[v21] );
            v46 = v16 + v19 + v21 + v20 + 5;
            v22 = (unsigned __int16 *)operator new[](saturated_mul(v46, 2u));
            lpData = (BYTE *)v22;
            v47 = v22;
            if ( !v22 )
            {
              operator delete(0);
              wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>((__int64)v42);
              _bstr_t::~_bstr_t((_bstr_t *)&v37);
              updated = -2147024882;
              goto LABEL_59;
            }
            if ( v14 )
              v24 = *v14;
            else
              v24 = 0;
            updated = StringCchCopyW(v22, v16 + 1, v24);
            if ( updated >= 0 )
            {
              *(_WORD *)&lpData[2 * v16] = 92;
              v26 = (const unsigned __int16 *)(v17 ? *v17 : v25);
              updated = StringCchCopyW((unsigned __int16 *)&lpData[2 * v16 + 2], v19 + 1, v26);
              if ( updated >= 0 )
              {
                updated = StringCchCopyW((unsigned __int16 *)(v27 + 4 + 2 * v19), (unsigned __int64)Sid + 1, &v48);
                if ( updated >= 0 )
                {
                  updated = StringCchCopyW((unsigned __int16 *)(v29 + 2 * v28 + 2), v21 + 1, StringSid);
                  if ( updated >= 0 )
                  {
                    *(_WORD *)(v30 + 2 * v21 + 4) = 0;
                    v31 = v41;
                    v32 = (struct _RTL_CRITICAL_SECTION *)((char *)v41 + 48);
                    v41 = (CredStore *)v32;
                    EnterCriticalSection(v32);
                    if ( v45 )
                      v35 = CredStore::StoreNtCredential(v33, a3, v45, v34);
                    else
                      v35 = CredStore::DeleteNtCredential(v33, a3);
                    updated = v35;
                    if ( v35 >= 0 )
                    {
                      v36 = RegSetValueExW(*((HKEY *)v31 + 5), L"AtServiceAccount", 0, 7u, lpData, 2 * v46);
                      if ( v36 )
                      {
                        if ( v36 > 0 )
                          updated = (unsigned __int16)v36 | 0x80070000;
                        else
                          updated = v36;
                      }
                    }
                    LeaveCriticalSection(v32);
                  }
                }
              }
            }
            operator delete(lpData);
            wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>((__int64)v42);
          }
          else
          {
            LastError = GetLastError();
            updated = LastError;
            if ( LastError > 0 )
              updated = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
LABEL_58:
    _bstr_t::~_bstr_t((_bstr_t *)&v37);
    goto LABEL_59;
  }
  if ( !*v8 )
  {
    updated = User::UpdateEntry(a3);
    if ( updated < 0 )
      goto LABEL_59;
    goto LABEL_8;
  }
  updated = -2147418113;
LABEL_59:
  _bstr_t::~_bstr_t((_bstr_t *)&v40);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180005b98  mov     [rsp-8+arg_8], rbx
0x180005b9d  push    rbp
0x180005b9e  push    rsi
0x180005b9f  push    rdi
0x180005ba0  push    r12
0x180005ba2  push    r13
0x180005ba4  push    r14
0x180005ba6  push    r15
0x180005ba8  lea     rbp, [rsp-27h]
0x180005bad  sub     rsp, 0B0h
0x180005bb4  mov     rax, cs:__security_cookie
0x180005bbb  xor     rax, rsp
0x180005bbe  mov     [rbp+57h+var_38], rax
0x180005bc2  mov     [rbp+57h+var_70], r9
0x180005bc6  mov     r14, r8
0x180005bc9  mov     rdi, rcx
0x180005bcc  mov     [rbp+57h+var_90], rcx
0x180005bd0  mov     r8, [r8]
0x180005bd3  xor     r13d, r13d
0x180005bd6  test    r8, r8
0x180005bd9  jnz     short loc_180005BE5
0x180005bdb  mov     eax, 80070057h
0x180005be0  jmp     loc_180005F4F
0x180005be5  mov     [rbp+57h+var_98], r13
0x180005be9  lea     rcx, [r8+10h]
0x180005bed  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180005bf2  test    al, al
0x180005bf4  jnz     short loc_180005C03
0x180005bf6  lea     rcx, [r8+18h]
0x180005bfa  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180005bff  test    al, al
0x180005c01  jz      short loc_180005C24
0x180005c03  cmp     [r8], r13b
0x180005c06  jz      short loc_180005C12
0x180005c08  mov     esi, 8000FFFFh
0x180005c0d  jmp     loc_180005F44
0x180005c12  mov     rcx, r14; this
0x180005c15  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180005c1a  mov     esi, eax
0x180005c1c  test    eax, eax
0x180005c1e  js      loc_180005F44
0x180005c24  mov     rdx, [r14]
0x180005c27  add     rdx, 10h
0x180005c2b  lea     rcx, [rbp+57h+var_98]
0x180005c2f  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180005c34  mov     [rbp+57h+var_B0], r13
0x180005c38  mov     rcx, [r14]
0x180005c3b  test    rcx, rcx
0x180005c3e  jnz     short loc_180005C4A
0x180005c40  mov     esi, 8000FFFFh
0x180005c45  jmp     loc_180005F3A
0x180005c4a  cmp     [rcx], r13b
0x180005c4d  jnz     short loc_180005C40
0x180005c4f  add     rcx, 18h
0x180005c53  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180005c58  test    al, al
0x180005c5a  jz      short loc_180005C6E
0x180005c5c  mov     rcx, r14; this
0x180005c5f  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180005c64  mov     esi, eax
0x180005c66  test    eax, eax
0x180005c68  js      loc_180005F3A
0x180005c6e  mov     rdx, [r14]
0x180005c71  add     rdx, 18h
0x180005c75  lea     rcx, [rbp+57h+var_B0]
0x180005c79  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180005c7e  mov     rax, [r14]
0x180005c81  test    rax, rax
0x180005c84  jz      short loc_180005C40
0x180005c86  cmp     [rax], r13b
0x180005c89  jnz     short loc_180005C40
0x180005c8b  cmp     dword ptr [rax+28h], 8
0x180005c8f  jnz     short loc_180005CA3
0x180005c91  mov     rcx, r14; this
0x180005c94  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180005c99  mov     esi, eax
0x180005c9b  test    eax, eax
0x180005c9d  js      loc_180005F3A
0x180005ca3  mov     rax, [r14]
0x180005ca6  mov     ebx, [rax+28h]
0x180005ca9  mov     [rbp+57h+Sid], r13
0x180005cad  lea     rdx, [rbp+57h+Sid]; void **
0x180005cb1  mov     rcx, r14; this
0x180005cb4  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x180005cb9  mov     esi, eax
0x180005cbb  test    eax, eax
0x180005cbd  js      loc_180005F3A
0x180005cc3  mov     rcx, rdi; this
0x180005cc6  call    ?InitAliasesKey@CredStore@@AEAAJXZ; CredStore::InitAliasesKey(void)
0x180005ccb  mov     esi, eax
0x180005ccd  test    eax, eax
0x180005ccf  js      loc_180005F3A
0x180005cd5  mov     [rbp+57h+StringSid], r13
0x180005cd9  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180005cdd  mov     rcx, [rbp+57h+Sid]; Sid
0x180005ce1  call    cs:__imp_ConvertSidToStringSidW
0x180005ce7  test    eax, eax
0x180005ce9  jnz     short loc_180005D09
0x180005ceb  call    cs:__imp_GetLastError
0x180005cf1  mov     esi, eax
0x180005cf3  test    eax, eax
0x180005cf5  jle     loc_180005F3A
0x180005cfb  movzx   esi, ax
0x180005cfe  or      esi, 80070000h
0x180005d04  jmp     loc_180005F3A
0x180005d09  mov     rcx, [rbp+57h+StringSid]
0x180005d0d  mov     rax, cs:__imp_LocalFree
0x180005d14  mov     [rbp+57h+var_88], r13b
0x180005d18  mov     [rbp+57h+var_80], rax
0x180005d1c  mov     [rbp+57h+var_78], rcx
0x180005d20  mov     [rbp+57h+var_58], r13w
0x180005d25  xorps   xmm0, xmm0
0x180005d28  xor     eax, eax
0x180005d2a  movups  [rbp+57h+var_56], xmm0
0x180005d2e  mov     [rbp+57h+var_46], rax
0x180005d32  mov     r9d, ebx
0x180005d35  lea     r8, aD; "%d"
0x180005d3c  lea     edx, [rax+0Dh]; unsigned __int64
0x180005d3f  lea     rcx, [rbp+57h+var_58]; unsigned __int16 *
0x180005d43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005d48  mov     rsi, [rbp+57h+var_B0]
0x180005d4c  test    rsi, rsi
0x180005d4f  jz      short loc_180005D56
0x180005d51  mov     rax, [rsi]
0x180005d54  jmp     short loc_180005D59
0x180005d56  mov     rax, r13
0x180005d59  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005d5d  mov     r15, r8
0x180005d60  inc     r15
0x180005d63  cmp     [rax+r15*2], r13w
0x180005d68  jnz     short loc_180005D60
0x180005d6a  mov     rdi, [rbp+57h+var_98]
0x180005d6e  test    rdi, rdi
0x180005d71  jz      short loc_180005D78
0x180005d73  mov     rax, [rdi]
0x180005d76  jmp     short loc_180005D7B
0x180005d78  mov     rax, r13
0x180005d7b  mov     r12, r8
0x180005d7e  inc     r12
0x180005d81  cmp     [rax+r12*2], r13w
0x180005d86  jnz     short loc_180005D7E
0x180005d88  lea     rcx, [rbp+57h+var_58]
0x180005d8c  mov     rax, r8
0x180005d8f  inc     rax
0x180005d92  cmp     [rcx+rax*2], r13w
0x180005d97  jnz     short loc_180005D8F
0x180005d99  mov     [rbp+57h+Sid], rax
0x180005d9d  mov     rcx, [rbp+57h+StringSid]
0x180005da1  mov     r13, r8
0x180005da4  xor     edx, edx
0x180005da6  inc     r13
0x180005da9  cmp     [rcx+r13*2], dx
0x180005dae  jnz     short loc_180005DA6
0x180005db0  lea     rcx, [rax+5]
0x180005db4  add     rcx, r13
0x180005db7  add     rcx, r12
0x180005dba  add     rcx, r15
0x180005dbd  mov     [rbp+57h+var_68], rcx
0x180005dc1  mov     eax, 2
0x180005dc6  mul     rcx
0x180005dc9  cmovb   rax, r8
0x180005dcd  mov     rcx, rax; unsigned __int64
0x180005dd0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005dd5  mov     rbx, rax
0x180005dd8  mov     [rbp+57h+var_60], rax
0x180005ddc  xor     r11d, r11d
0x180005ddf  test    rax, rax
0x180005de2  jnz     short loc_180005E09
0x180005de4  xor     ecx, ecx; Block
0x180005de6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005deb  nop
0x180005dec  lea     rcx, [rbp+57h+var_88]
0x180005df0  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180005df5  nop
0x180005df6  lea     rcx, [rbp+57h+var_B0]; this
0x180005dfa  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180005dff  mov     esi, 8007000Eh
0x180005e04  jmp     loc_180005F44
0x180005e09  test    rsi, rsi
0x180005e0c  jz      short loc_180005E13
0x180005e0e  mov     r8, [rsi]
0x180005e11  jmp     short loc_180005E16
0x180005e13  mov     r8, r11; unsigned __int16 *
0x180005e16  lea     rdx, [r15+1]; unsigned __int64
0x180005e1a  mov     rcx, rbx; unsigned __int16 *
0x180005e1d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005e22  mov     esi, eax
0x180005e24  test    eax, eax
0x180005e26  js      loc_180005F27
0x180005e2c  mov     word ptr [rbx+r15*2], 5Ch ; '\'
0x180005e33  lea     r10, [rbx+r15*2]
0x180005e37  test    rdi, rdi
0x180005e3a  jz      short loc_180005E41
0x180005e3c  mov     r8, [rdi]
0x180005e3f  jmp     short loc_180005E44
0x180005e41  mov     r8, r11; unsigned __int16 *
0x180005e44  lea     rdx, [r12+1]; unsigned __int64
0x180005e49  lea     rcx, [r10+2]; unsigned __int16 *
0x180005e4d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005e52  mov     esi, eax
0x180005e54  test    eax, eax
0x180005e56  js      loc_180005F27
0x180005e5c  add     r10, 4
0x180005e60  lea     r11, [r10+r12*2]
0x180005e64  mov     r10, [rbp+57h+Sid]
0x180005e68  lea     rdx, [r10+1]; unsigned __int64
0x180005e6c  lea     r8, [rbp+57h+var_58]; unsigned __int16 *
0x180005e70  mov     rcx, r11; unsigned __int16 *
0x180005e73  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005e78  mov     esi, eax
0x180005e7a  xor     r12d, r12d
0x180005e7d  test    eax, eax
0x180005e7f  js      loc_180005F27
0x180005e85  lea     r11, [r11+r10*2]
0x180005e89  lea     rdx, [r13+1]; unsigned __int64
0x180005e8d  mov     r8, [rbp+57h+StringSid]; unsigned __int16 *
0x180005e91  lea     rcx, [r11+2]; unsigned __int16 *
0x180005e95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005e9a  mov     esi, eax
0x180005e9c  test    eax, eax
0x180005e9e  js      loc_180005F27
0x180005ea4  mov     [r11+r13*2+4], r12w
0x180005eaa  mov     r15, [rbp+57h+var_90]
0x180005eae  lea     rdi, [r15+30h]
0x180005eb2  mov     [rbp+57h+var_90], rdi
0x180005eb6  mov     rcx, rdi; lpCriticalSection
0x180005eb9  call    cs:__imp_EnterCriticalSection
0x180005ebf  nop
0x180005ec0  mov     rax, [rbp+57h+var_70]
0x180005ec4  mov     rdx, r14; struct User *
0x180005ec7  test    rax, rax
0x180005eca  jz      short loc_180005ED6
0x180005ecc  mov     r8, rax; unsigned __int16 *
0x180005ecf  call    ?StoreNtCredential@CredStore@@QEAAJAEBVUser@@PEAG_N@Z; CredStore::StoreNtCredential(User const &,ushort *,bool)
0x180005ed4  jmp     short loc_180005EDB
0x180005ed6  call    ?DeleteNtCredential@CredStore@@QEAAJAEBVUser@@_N@Z; CredStore::DeleteNtCredential(User const &,bool)
0x180005edb  mov     esi, eax
0x180005edd  test    eax, eax
0x180005edf  js      short loc_180005F1D
0x180005ee1  mov     rax, [rbp+57h+var_68]
0x180005ee5  add     eax, eax
0x180005ee7  mov     [rsp+0E0h+cbData], eax; cbData
0x180005eeb  mov     [rsp+0E0h+lpData], rbx; lpData
0x180005ef0  mov     r9d, 7; dwType
0x180005ef6  xor     r8d, r8d; Reserved
0x180005ef9  lea     rdx, ValueName; "AtServiceAccount"
0x180005f00  mov     rcx, [r15+28h]; hKey
0x180005f04  call    cs:__imp_RegSetValueExW
0x180005f0a  test    eax, eax
0x180005f0c  jz      short loc_180005F1D
0x180005f0e  jg      short loc_180005F14
0x180005f10  mov     esi, eax
0x180005f12  jmp     short loc_180005F1D
0x180005f14  movzx   esi, ax
0x180005f17  or      esi, 80070000h
0x180005f1d  mov     rcx, rdi; lpCriticalSection
0x180005f20  call    cs:__imp_LeaveCriticalSection
0x180005f26  nop
0x180005f27  mov     rcx, rbx; Block
0x180005f2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005f2f  nop
0x180005f30  lea     rcx, [rbp+57h+var_88]
0x180005f34  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180005f39  nop
0x180005f3a  lea     rcx, [rbp+57h+var_B0]; this
0x180005f3e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180005f43  nop
0x180005f44  lea     rcx, [rbp+57h+var_98]; this
0x180005f48  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180005f4d  mov     eax, esi
0x180005f4f  mov     rcx, [rbp+57h+var_38]
0x180005f53  xor     rcx, rsp; StackCookie
0x180005f56  call    __security_check_cookie
0x180005f5b  mov     rbx, [rsp+0E0h+arg_8]
0x180005f63  add     rsp, 0B0h
0x180005f6a  pop     r15
0x180005f6c  pop     r14
0x180005f6e  pop     r13
0x180005f70  pop     r12
0x180005f72  pop     rdi
0x180005f73  pop     rsi
0x180005f74  pop     rbp
0x180005f75  retn
```
