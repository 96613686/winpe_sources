# CredStore::StoreAlias(ushort const *,User const &,ushort *)

- ea: `0x180005efc`
- end: `0x18000630b`
- name: `?StoreAlias@CredStore@@QEAAJPEBGAEBVUser@@PEAG@Z`
- size: `1039`
- prototype: `__int64 __fastcall(CredStore *__hidden this, const unsigned __int16 *, const struct User *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180016620`

## callees

- `0x180003f7c`
- `0x1800040c0`
- `0x1800050d0`
- `0x18000525c`
- `0x180005efc`
- `0x180006314`
- `0x1800072c0`
- `0x180007988`
- `0x180007994`
- `0x18001822c`
- `0x18001845c`
- `0x180018534`
- `0x180018c68`
- `0x18001be88`
- `0x18001c3ac`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000623b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000623b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006067`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000608f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000628c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000628c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006057`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006057`

## string_xrefs

- `0x180006281`: `AtServiceAccount`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CredStore::StoreAlias(
        CredStore *this,
        const unsigned __int16 *a2,
        const struct User *a3,
        unsigned __int16 *a4)
{
  __int64 v6; // r8
  __int64 v8; // r8
  signed int updated; // esi
  __int64 v10; // rdx
  __int64 v11; // rdx
  User *v12; // rcx
  unsigned int v13; // ebx
  signed int LastError; // eax
  const unsigned __int16 **v15; // rsi
  const unsigned __int16 *v16; // rax
  __int64 v17; // r15
  _QWORD *v18; // rdi
  __int64 v19; // rax
  __int64 v20; // r12
  __int64 v21; // rax
  __int64 v22; // r13
  unsigned __int16 *v23; // rax
  BYTE *lpData; // rbx
  const unsigned __int16 *v25; // r8
  __int64 v26; // r11
  const unsigned __int16 *v27; // r8
  __int64 v28; // r10
  __int64 v29; // r10
  __int64 v30; // r11
  __int64 v31; // r11
  CredStore *v32; // r15
  struct _RTL_CRITICAL_SECTION *v33; // rdi
  CredStore *v34; // rcx
  bool v35; // r8
  bool v36; // r9
  int v37; // eax
  LSTATUS v38; // eax
  const unsigned __int16 **v39; // [rsp+30h] [rbp-59h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-51h] BYREF
  PSID Sid; // [rsp+40h] [rbp-49h] BYREF
  _QWORD *v42; // [rsp+48h] [rbp-41h] BYREF
  CredStore *v43; // [rsp+50h] [rbp-39h]
  _BYTE v44[8]; // [rsp+58h] [rbp-31h] BYREF
  HLOCAL (__stdcall *v45)(HLOCAL); // [rsp+60h] [rbp-29h]
  LPWSTR v46; // [rsp+68h] [rbp-21h]
  unsigned __int16 *v47; // [rsp+70h] [rbp-19h]
  unsigned __int64 v48; // [rsp+78h] [rbp-11h]
  unsigned __int16 *v49; // [rsp+80h] [rbp-9h]
  unsigned __int16 v50; // [rsp+88h] [rbp-1h] BYREF
  __int128 v51; // [rsp+8Ah] [rbp+1h]
  __int64 v52; // [rsp+9Ah] [rbp+11h]

  v47 = a4;
  v43 = this;
  v6 = *(_QWORD *)a3;
  if ( !v6 )
    return 2147942487LL;
  v42 = 0;
  if ( !(unsigned __int8)_bstr_t::operator!(v6 + 16) && !(unsigned __int8)_bstr_t::operator!(v8 + 24) )
  {
LABEL_8:
    _bstr_t::operator=(&v42, *(_QWORD *)a3 + 16LL);
    v39 = 0;
    if ( !*(_QWORD *)a3 || User::IsAlias(a3) )
      goto LABEL_9;
    if ( (unsigned __int8)_bstr_t::operator!(v10 + 24) )
    {
      updated = User::UpdateEntry(a3);
      if ( updated < 0 )
        goto LABEL_58;
    }
    _bstr_t::operator=(&v39, *(_QWORD *)a3 + 24LL);
    if ( !*(_QWORD *)a3 || User::IsAlias(a3) )
    {
LABEL_9:
      updated = -2147418113;
    }
    else if ( *(_DWORD *)(v11 + 40) != 8 || (updated = User::UpdateEntry(v12), updated >= 0) )
    {
      v13 = *(_DWORD *)(*(_QWORD *)a3 + 40LL);
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
            v44[0] = 0;
            v45 = LocalFree;
            v46 = StringSid;
            v50 = 0;
            v51 = 0;
            v52 = 0;
            StringCchPrintfW(&v50, 0xDu, L"%d", v13);
            v15 = v39;
            if ( v39 )
              v16 = *v39;
            else
              v16 = 0;
            v17 = -1;
            do
              ++v17;
            while ( v16[v17] );
            v18 = v42;
            if ( v42 )
              v19 = *v42;
            else
              v19 = 0;
            v20 = -1;
            do
              ++v20;
            while ( *(_WORD *)(v19 + 2 * v20) );
            v21 = -1;
            do
              ++v21;
            while ( *(&v50 + v21) );
            Sid = (PSID)v21;
            v22 = -1;
            do
              ++v22;
            while ( StringSid[v22] );
            v48 = v17 + v20 + v22 + v21 + 5;
            v23 = (unsigned __int16 *)operator new[](saturated_mul(v48, 2u));
            lpData = (BYTE *)v23;
            v49 = v23;
            if ( !v23 )
            {
              operator delete(0);
              wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>(v44);
              _bstr_t::~_bstr_t((_bstr_t *)&v39);
              updated = -2147024882;
              goto LABEL_59;
            }
            if ( v15 )
              v25 = *v15;
            else
              v25 = 0;
            updated = StringCchCopyW(v23, v17 + 1, v25);
            if ( updated >= 0 )
            {
              *(_WORD *)&lpData[2 * v17] = 92;
              v27 = (const unsigned __int16 *)(v18 ? *v18 : v26);
              updated = StringCchCopyW((unsigned __int16 *)&lpData[2 * v17 + 2], v20 + 1, v27);
              if ( updated >= 0 )
              {
                updated = StringCchCopyW((unsigned __int16 *)(v28 + 4 + 2 * v20), (unsigned __int64)Sid + 1, &v50);
                if ( updated >= 0 )
                {
                  updated = StringCchCopyW((unsigned __int16 *)(v30 + 2 * v29 + 2), v22 + 1, StringSid);
                  if ( updated >= 0 )
                  {
                    *(_WORD *)(v31 + 2 * v22 + 4) = 0;
                    v32 = v43;
                    v33 = (struct _RTL_CRITICAL_SECTION *)((char *)v43 + 48);
                    v43 = (CredStore *)v33;
                    EnterCriticalSection(v33);
                    if ( v47 )
                      v37 = CredStore::StoreNtCredential(v34, a3, v47, v36);
                    else
                      v37 = CredStore::DeleteNtCredential(v34, a3, v35);
                    updated = v37;
                    if ( v37 >= 0 )
                    {
                      v38 = RegSetValueExW(*((HKEY *)v32 + 5), L"AtServiceAccount", 0, 7u, lpData, 2 * v48);
                      if ( v38 )
                      {
                        if ( v38 > 0 )
                          updated = (unsigned __int16)v38 | 0x80070000;
                        else
                          updated = v38;
                      }
                    }
                    LeaveCriticalSection(v33);
                  }
                }
              }
            }
            operator delete(lpData);
            wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>(v44);
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
    _bstr_t::~_bstr_t((_bstr_t *)&v39);
    goto LABEL_59;
  }
  if ( !User::IsAlias(a3) )
  {
    updated = User::UpdateEntry(a3);
    if ( updated < 0 )
      goto LABEL_59;
    goto LABEL_8;
  }
  updated = -2147418113;
LABEL_59:
  _bstr_t::~_bstr_t((_bstr_t *)&v42);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180005efc  mov     [rsp-8+arg_8], rbx
0x180005f01  push    rbp
0x180005f02  push    rsi
0x180005f03  push    rdi
0x180005f04  push    r12
0x180005f06  push    r13
0x180005f08  push    r14
0x180005f0a  push    r15
0x180005f0c  lea     rbp, [rsp-27h]
0x180005f11  sub     rsp, 0B0h
0x180005f18  mov     rax, cs:__security_cookie
0x180005f1f  xor     rax, rsp
0x180005f22  mov     [rbp+57h+var_38], rax
0x180005f26  mov     [rbp+57h+var_70], r9
0x180005f2a  mov     r14, r8
0x180005f2d  mov     rdi, rcx
0x180005f30  mov     [rbp+57h+var_90], rcx
0x180005f34  mov     r8, [r8]
0x180005f37  xor     r13d, r13d
0x180005f3a  test    r8, r8
0x180005f3d  jnz     short loc_180005F49
0x180005f3f  mov     eax, 80070057h
0x180005f44  jmp     loc_1800062E3
0x180005f49  mov     [rbp+57h+var_98], r13
0x180005f4d  lea     rcx, [r8+10h]
0x180005f51  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180005f56  test    al, al
0x180005f58  jnz     short loc_180005F67
0x180005f5a  lea     rcx, [r8+18h]
0x180005f5e  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180005f63  test    al, al
0x180005f65  jz      short loc_180005F8F
0x180005f67  mov     rcx, r14; this
0x180005f6a  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x180005f6f  test    al, al
0x180005f71  jz      short loc_180005F7D
0x180005f73  mov     esi, 8000FFFFh
0x180005f78  jmp     loc_1800062D8
0x180005f7d  mov     rcx, r14; this
0x180005f80  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180005f85  mov     esi, eax
0x180005f87  test    eax, eax
0x180005f89  js      loc_1800062D8
0x180005f8f  mov     rdx, [r14]
0x180005f92  add     rdx, 10h
0x180005f96  lea     rcx, [rbp+57h+var_98]
0x180005f9a  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180005f9f  mov     [rbp+57h+var_B0], r13
0x180005fa3  mov     rdx, [r14]
0x180005fa6  test    rdx, rdx
0x180005fa9  jnz     short loc_180005FB5
0x180005fab  mov     esi, 8000FFFFh
0x180005fb0  jmp     loc_1800062CE
0x180005fb5  mov     rcx, r14; this
0x180005fb8  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x180005fbd  test    al, al
0x180005fbf  jnz     short loc_180005FAB
0x180005fc1  lea     rcx, [rdx+18h]
0x180005fc5  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180005fca  test    al, al
0x180005fcc  jz      short loc_180005FE0
0x180005fce  mov     rcx, r14; this
0x180005fd1  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180005fd6  mov     esi, eax
0x180005fd8  test    eax, eax
0x180005fda  js      loc_1800062CE
0x180005fe0  mov     rdx, [r14]
0x180005fe3  add     rdx, 18h
0x180005fe7  lea     rcx, [rbp+57h+var_B0]
0x180005feb  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180005ff0  mov     rdx, [r14]
0x180005ff3  test    rdx, rdx
0x180005ff6  jz      short loc_180005FAB
0x180005ff8  mov     rcx, r14; this
0x180005ffb  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x180006000  test    al, al
0x180006002  jnz     short loc_180005FAB
0x180006004  cmp     dword ptr [rdx+28h], 8
0x180006008  jnz     short loc_180006019
0x18000600a  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18000600f  mov     esi, eax
0x180006011  test    eax, eax
0x180006013  js      loc_1800062CE
0x180006019  mov     rax, [r14]
0x18000601c  mov     ebx, [rax+28h]
0x18000601f  mov     [rbp+57h+Sid], r13
0x180006023  lea     rdx, [rbp+57h+Sid]; void **
0x180006027  mov     rcx, r14; this
0x18000602a  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x18000602f  mov     esi, eax
0x180006031  test    eax, eax
0x180006033  js      loc_1800062CE
0x180006039  mov     rcx, rdi; this
0x18000603c  call    ?InitAliasesKey@CredStore@@AEAAJXZ; CredStore::InitAliasesKey(void)
0x180006041  mov     esi, eax
0x180006043  test    eax, eax
0x180006045  js      loc_1800062CE
0x18000604b  mov     [rbp+57h+StringSid], r13
0x18000604f  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180006053  mov     rcx, [rbp+57h+Sid]; Sid
0x180006057  call    cs:__imp_ConvertSidToStringSidW
0x18000605e  nop     dword ptr [rax+rax+00h]
0x180006063  test    eax, eax
0x180006065  jnz     short loc_18000608B
0x180006067  call    cs:__imp_GetLastError
0x18000606e  nop     dword ptr [rax+rax+00h]
0x180006073  mov     esi, eax
0x180006075  test    eax, eax
0x180006077  jle     loc_1800062CE
0x18000607d  movzx   esi, ax
0x180006080  or      esi, 80070000h
0x180006086  jmp     loc_1800062CE
0x18000608b  mov     rcx, [rbp+57h+StringSid]
0x18000608f  mov     rax, cs:__imp_LocalFree
0x180006096  mov     [rbp+57h+var_88], r13b
0x18000609a  mov     [rbp+57h+var_80], rax
0x18000609e  mov     [rbp+57h+var_78], rcx
0x1800060a2  mov     [rbp+57h+var_58], r13w
0x1800060a7  xorps   xmm0, xmm0
0x1800060aa  xor     eax, eax
0x1800060ac  movups  [rbp+57h+var_56], xmm0
0x1800060b0  mov     [rbp+57h+var_46], rax
0x1800060b4  mov     r9d, ebx
0x1800060b7  lea     r8, aD; "%d"
0x1800060be  lea     edx, [rax+0Dh]; unsigned __int64
0x1800060c1  lea     rcx, [rbp+57h+var_58]; unsigned __int16 *
0x1800060c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800060ca  mov     rsi, [rbp+57h+var_B0]
0x1800060ce  test    rsi, rsi
0x1800060d1  jz      short loc_1800060D8
0x1800060d3  mov     rax, [rsi]
0x1800060d6  jmp     short loc_1800060DB
0x1800060d8  mov     rax, r13
0x1800060db  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800060df  mov     r15, r8
0x1800060e2  inc     r15
0x1800060e5  cmp     [rax+r15*2], r13w
0x1800060ea  jnz     short loc_1800060E2
0x1800060ec  mov     rdi, [rbp+57h+var_98]
0x1800060f0  test    rdi, rdi
0x1800060f3  jz      short loc_1800060FA
0x1800060f5  mov     rax, [rdi]
0x1800060f8  jmp     short loc_1800060FD
0x1800060fa  mov     rax, r13
0x1800060fd  mov     r12, r8
0x180006100  inc     r12
0x180006103  cmp     [rax+r12*2], r13w
0x180006108  jnz     short loc_180006100
0x18000610a  lea     rcx, [rbp+57h+var_58]
0x18000610e  mov     rax, r8
0x180006111  inc     rax
0x180006114  cmp     [rcx+rax*2], r13w
0x180006119  jnz     short loc_180006111
0x18000611b  mov     [rbp+57h+Sid], rax
0x18000611f  mov     rcx, [rbp+57h+StringSid]
0x180006123  mov     r13, r8
0x180006126  xor     edx, edx
0x180006128  inc     r13
0x18000612b  cmp     [rcx+r13*2], dx
0x180006130  jnz     short loc_180006128
0x180006132  lea     rcx, [rax+5]
0x180006136  add     rcx, r13
0x180006139  add     rcx, r12
0x18000613c  add     rcx, r15
0x18000613f  mov     [rbp+57h+var_68], rcx
0x180006143  mov     eax, 2
0x180006148  mul     rcx
0x18000614b  cmovb   rax, r8
0x18000614f  mov     rcx, rax; unsigned __int64
0x180006152  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180006157  mov     rbx, rax
0x18000615a  mov     [rbp+57h+var_60], rax
0x18000615e  xor     r11d, r11d
0x180006161  test    rax, rax
0x180006164  jnz     short loc_18000618B
0x180006166  xor     ecx, ecx; Block
0x180006168  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000616d  nop
0x18000616e  lea     rcx, [rbp+57h+var_88]
0x180006172  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180006177  nop
0x180006178  lea     rcx, [rbp+57h+var_B0]; this
0x18000617c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180006181  mov     esi, 8007000Eh
0x180006186  jmp     loc_1800062D8
0x18000618b  test    rsi, rsi
0x18000618e  jz      short loc_180006195
0x180006190  mov     r8, [rsi]
0x180006193  jmp     short loc_180006198
0x180006195  mov     r8, r11; unsigned __int16 *
0x180006198  lea     rdx, [r15+1]; unsigned __int64
0x18000619c  mov     rcx, rbx; unsigned __int16 *
0x18000619f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800061a4  mov     esi, eax
0x1800061a6  test    eax, eax
0x1800061a8  js      loc_1800062BB
0x1800061ae  mov     word ptr [rbx+r15*2], 5Ch ; '\'
0x1800061b5  lea     r10, [rbx+r15*2]
0x1800061b9  test    rdi, rdi
0x1800061bc  jz      short loc_1800061C3
0x1800061be  mov     r8, [rdi]
0x1800061c1  jmp     short loc_1800061C6
0x1800061c3  mov     r8, r11; unsigned __int16 *
0x1800061c6  lea     rdx, [r12+1]; unsigned __int64
0x1800061cb  lea     rcx, [r10+2]; unsigned __int16 *
0x1800061cf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800061d4  mov     esi, eax
0x1800061d6  test    eax, eax
0x1800061d8  js      loc_1800062BB
0x1800061de  add     r10, 4
0x1800061e2  lea     r11, [r10+r12*2]
0x1800061e6  mov     r10, [rbp+57h+Sid]
0x1800061ea  lea     rdx, [r10+1]; unsigned __int64
0x1800061ee  lea     r8, [rbp+57h+var_58]; unsigned __int16 *
0x1800061f2  mov     rcx, r11; unsigned __int16 *
0x1800061f5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800061fa  mov     esi, eax
0x1800061fc  xor     r12d, r12d
0x1800061ff  test    eax, eax
0x180006201  js      loc_1800062BB
0x180006207  lea     r11, [r11+r10*2]
0x18000620b  lea     rdx, [r13+1]; unsigned __int64
0x18000620f  mov     r8, [rbp+57h+StringSid]; unsigned __int16 *
0x180006213  lea     rcx, [r11+2]; unsigned __int16 *
0x180006217  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000621c  mov     esi, eax
0x18000621e  test    eax, eax
0x180006220  js      loc_1800062BB
0x180006226  mov     [r11+r13*2+4], r12w
0x18000622c  mov     r15, [rbp+57h+var_90]
0x180006230  lea     rdi, [r15+30h]
0x180006234  mov     [rbp+57h+var_90], rdi
0x180006238  mov     rcx, rdi; lpCriticalSection
0x18000623b  call    cs:__imp_EnterCriticalSection
0x180006242  nop     dword ptr [rax+rax+00h]
0x180006247  nop
0x180006248  mov     rax, [rbp+57h+var_70]
0x18000624c  mov     rdx, r14; struct User *
0x18000624f  test    rax, rax
0x180006252  jz      short loc_18000625E
0x180006254  mov     r8, rax; unsigned __int16 *
0x180006257  call    ?StoreNtCredential@CredStore@@QEAAJAEBVUser@@PEAG_N@Z; CredStore::StoreNtCredential(User const &,ushort *,bool)
0x18000625c  jmp     short loc_180006263
0x18000625e  call    ?DeleteNtCredential@CredStore@@QEAAJAEBVUser@@_N@Z; CredStore::DeleteNtCredential(User const &,bool)
0x180006263  mov     esi, eax
0x180006265  test    eax, eax
0x180006267  js      short loc_1800062AB
0x180006269  mov     rax, [rbp+57h+var_68]
0x18000626d  add     eax, eax
0x18000626f  mov     [rsp+0E0h+cbData], eax; cbData
0x180006273  mov     [rsp+0E0h+lpData], rbx; lpData
0x180006278  mov     r9d, 7; dwType
0x18000627e  xor     r8d, r8d; Reserved
0x180006281  lea     rdx, ValueName; "AtServiceAccount"
0x180006288  mov     rcx, [r15+28h]; hKey
0x18000628c  call    cs:__imp_RegSetValueExW
0x180006293  nop     dword ptr [rax+rax+00h]
0x180006298  test    eax, eax
0x18000629a  jz      short loc_1800062AB
0x18000629c  jg      short loc_1800062A2
0x18000629e  mov     esi, eax
0x1800062a0  jmp     short loc_1800062AB
0x1800062a2  movzx   esi, ax
0x1800062a5  or      esi, 80070000h
0x1800062ab  mov     rcx, rdi; lpCriticalSection
0x1800062ae  call    cs:__imp_LeaveCriticalSection
0x1800062b5  nop     dword ptr [rax+rax+00h]
0x1800062ba  nop
0x1800062bb  mov     rcx, rbx; Block
0x1800062be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800062c3  nop
0x1800062c4  lea     rcx, [rbp+57h+var_88]
0x1800062c8  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x1800062cd  nop
0x1800062ce  lea     rcx, [rbp+57h+var_B0]; this
0x1800062d2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800062d7  nop
0x1800062d8  lea     rcx, [rbp+57h+var_98]; this
0x1800062dc  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800062e1  mov     eax, esi
0x1800062e3  mov     rcx, [rbp+57h+var_38]
0x1800062e7  xor     rcx, rsp; StackCookie
0x1800062ea  call    __security_check_cookie
0x1800062ef  mov     rbx, [rsp+0E0h+arg_8]
0x1800062f7  add     rsp, 0B0h
0x1800062fe  pop     r15
0x180006300  pop     r14
0x180006302  pop     r13
0x180006304  pop     r12
0x180006306  pop     rdi
0x180006307  pop     rsi
0x180006308  pop     rbp
0x180006309  retn
```
