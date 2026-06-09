# VaultAuditEnumerateCredentials(VaultContext *,ulong,ulong)

- ea: `0x180015b30`
- end: `0x180015e27`
- name: `?VaultAuditEnumerateCredentials@@YAXPEAUVaultContext@@KK@Z`
- size: `759`
- prototype: `void __fastcall(struct VaultContext *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800151d0`

## callees

- `0x18000ae60`
- `0x180015b30`
- `0x1800311e0`
- `0x18003a580`
- `0x18003af10`
- `0x18004b430`
- `0x18004d010`

## import_xrefs

- `LSASRV!LsapQueryClientInfo` at `0x180015d11`
- `LSASRV!LsapQueryClientInfo` at `0x180015d11`
- `LSASRV!LsapAdtGetCallerProcessInfo` at `0x180015cfb`
- `LSASRV!LsapAdtGetCallerProcessInfo` at `0x180015cfb`
- `LSASRV!LsapAuditFailed` at `0x180015df1`
- `LSASRV!LsapAuditFailed` at `0x180015df1`
- `LSASRV!LsapAdtWriteLog` at `0x180015dd5`
- `LSASRV!LsapAdtWriteLog` at `0x180015dd5`
- `ntdll!RtlInitUnicodeString` at `0x180015d2a`
- `ntdll!RtlInitUnicodeString` at `0x180015d2a`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180015cdb`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180015cdb`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x180015dc7`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x180015dc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall VaultAuditEnumerateCredentials(struct VaultContext *a1, int a2, int a3)
{
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rbx
  signed int CallerProcessInfo; // eax
  void (__fastcall ***v10)(_QWORD); // rcx
  bool v11; // sf
  int v12; // [rsp+A0h] [rbp-80h] BYREF
  int v13; // [rsp+A4h] [rbp-7Ch] BYREF
  __int64 v14; // [rsp+A8h] [rbp-78h] BYREF
  _QWORD *v15; // [rsp+B0h] [rbp-70h] BYREF
  __int64 v16; // [rsp+B8h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-50h] BYREF
  char v19; // [rsp+D8h] [rbp-48h]
  __int64 (__fastcall *v20)(_QWORD); // [rsp+E0h] [rbp-40h]
  __int64 v21; // [rsp+E8h] [rbp-38h]
  int v22; // [rsp+F0h] [rbp-30h]
  __int128 Buf2; // [rsp+F8h] [rbp-28h] BYREF
  _BYTE v24[1056]; // [rsp+110h] [rbp-10h] BYREF

  memset_0(v24, 0, 0x418u);
  LOBYTE(v12) = 1;
  v13 = 0;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  DestinationString = 0;
  v20 = AutoDereference<IVaultKeyManager>;
  v6 = 0;
  v21 = 0;
  v22 = 0;
  Buf2 = 0;
  v7 = *(_QWORD *)a1;
  v8 = *(_QWORD *)(*(_QWORD *)a1 + 8LL);
  v18 = v8;
  if ( v8 )
  {
    (**(void (__fastcall ***)(__int64))v8)(v8);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 200LL))(v8, 0);
  }
  v19 = 1;
  if ( *(_DWORD *)(v7 + 108) == 2 )
  {
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 208LL))(v8);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    }
    CallerProcessInfo = -2147024841;
    goto LABEL_22;
  }
  v10 = *(void (__fastcall ****)(_QWORD))(v7 + 8);
  if ( !v10 )
  {
    CVaultStoreLock::~CVaultStoreLock((CVaultStoreLock *)&v18);
    CallerProcessInfo = -2147023728;
    goto LABEL_22;
  }
  (**v10)(v10);
  v6 = *(_QWORD *)(v7 + 8);
  v21 = v6;
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 208LL))(v8);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  }
  CallerProcessInfo = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v6 + 24LL))(v6, &Buf2);
  v11 = CallerProcessInfo < 0;
  if ( CallerProcessInfo )
  {
    if ( CallerProcessInfo <= 0 )
      goto LABEL_23;
    CallerProcessInfo = (unsigned __int16)CallerProcessInfo | 0x80070000;
LABEL_22:
    v11 = CallerProcessInfo < 0;
LABEL_23:
    if ( !v11 )
      goto LABEL_25;
    goto LABEL_24;
  }
  if ( memcmp_0(&Vault_DefaultVault_ID, &Buf2, 0x10u) && memcmp_0(&Vault_CredmanVault_ID, &Buf2, 0x10u) )
    goto LABEL_25;
  CallerProcessInfo = LsapAdtAuditingEnabledByLogonId(146, (char *)a1 + 76, 8, &v12);
  if ( CallerProcessInfo >= 0 )
  {
    if ( !(_BYTE)v12 )
      goto LABEL_25;
    CallerProcessInfo = LsapAdtGetCallerProcessInfo(&v13, &v14);
    if ( CallerProcessInfo >= 0 )
    {
      CallerProcessInfo = LsapQueryClientInfo(&v15, &v16);
      if ( CallerProcessInfo >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"VAULT");
        CallerProcessInfo = ((__int64 (__fastcall *)(_BYTE *, __int64, __int64, __int64, __int16, __int16, int, _QWORD, int, struct _UNICODE_STRING *, int, _QWORD, int, int, int, int, int, __int64, int, int, int, __int64, _DWORD, _DWORD))LsapAdtInitParametersArray)(
                              v24,
                              7,
                              5381,
                              146,
                              8,
                              7,
                              4,
                              *v15,
                              1,
                              &DestinationString,
                              5,
                              *(_QWORD *)((char *)a1 + 76),
                              27,
                              a2,
                              27,
                              a3,
                              12,
                              v14,
                              27,
                              v13,
                              v12,
                              v14,
                              (_DWORD)v15,
                              v16);
        if ( CallerProcessInfo >= 0 )
        {
          LsapAdtWriteLog(v24);
          goto LABEL_25;
        }
      }
    }
  }
LABEL_24:
  LsapAuditFailed((unsigned int)CallerProcessInfo);
LABEL_25:
  if ( v6 )
    AutoDereference<IVaultKeyManager>(v6);
}

```

## disassembly

```asm
0x180015b30  push    rbp
0x180015b32  push    rbx
0x180015b33  push    rsi
0x180015b34  push    rdi
0x180015b35  push    r12
0x180015b37  push    r14
0x180015b39  push    r15
0x180015b3b  lea     rbp, [rsp-420h]
0x180015b43  sub     rsp, 540h
0x180015b4a  mov     rax, cs:__security_cookie
0x180015b51  xor     rax, rsp
0x180015b54  mov     [rbp+450h+var_40], rax
0x180015b5b  mov     r12d, r8d
0x180015b5e  mov     r15d, edx
0x180015b61  mov     r14, rcx
0x180015b64  xor     edx, edx; Val
0x180015b66  mov     r8d, 418h; Size
0x180015b6c  lea     rcx, [rbp+450h+var_460]; void *
0x180015b70  call    memset_0
0x180015b75  mov     byte ptr [rbp+450h+var_4D0], 1
0x180015b79  xor     ecx, ecx
0x180015b7b  mov     [rbp+450h+var_4CC], ecx
0x180015b7e  mov     [rbp+450h+var_4C8], rcx
0x180015b82  mov     [rbp+450h+var_4B8], rcx
0x180015b86  mov     [rbp+450h+var_4C0], rcx
0x180015b8a  xorps   xmm0, xmm0
0x180015b8d  movups  xmmword ptr [rbp+450h+DestinationString.Length], xmm0
0x180015b91  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180015b98  mov     [rbp+450h+var_490], rax
0x180015b9c  mov     edi, ecx
0x180015b9e  mov     [rbp+450h+var_488], rcx
0x180015ba2  mov     [rbp+450h+var_480], ecx
0x180015ba5  movups  [rbp+450h+Buf2], xmm0
0x180015ba9  mov     rsi, [r14]
0x180015bac  mov     rbx, [rsi+8]
0x180015bb0  mov     [rbp+450h+var_4A0], rbx
0x180015bb4  test    rbx, rbx
0x180015bb7  jz      short loc_180015BDB
0x180015bb9  mov     rax, [rbx]
0x180015bbc  mov     rcx, rbx
0x180015bbf  mov     rax, [rax]
0x180015bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bc7  mov     rax, [rbx]
0x180015bca  xor     edx, edx
0x180015bcc  mov     rcx, rbx
0x180015bcf  mov     rax, [rax+0C8h]
0x180015bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bdb  mov     [rbp+450h+var_498], 1
0x180015bdf  cmp     dword ptr [rsi+6Ch], 2
0x180015be3  jnz     short loc_180015C16
0x180015be5  test    rbx, rbx
0x180015be8  jz      short loc_180015C0C
0x180015bea  mov     rax, [rbx]
0x180015bed  mov     rcx, rbx
0x180015bf0  mov     rax, [rax+0D0h]
0x180015bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bfc  mov     rax, [rbx]
0x180015bff  mov     rcx, rbx
0x180015c02  mov     rax, [rax+8]
0x180015c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c0b  nop
0x180015c0c  mov     eax, 80070037h
0x180015c11  jmp     loc_180015DEB
0x180015c16  mov     rcx, [rsi+8]
0x180015c1a  test    rcx, rcx
0x180015c1d  jz      loc_180015DDD
0x180015c23  mov     rax, [rcx]
0x180015c26  mov     rax, [rax]
0x180015c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c2e  mov     rdi, [rsi+8]
0x180015c32  mov     [rbp+450h+var_488], rdi
0x180015c36  test    rbx, rbx
0x180015c39  jz      short loc_180015C5D
0x180015c3b  mov     rax, [rbx]
0x180015c3e  mov     rcx, rbx
0x180015c41  mov     rax, [rax+0D0h]
0x180015c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c4d  mov     rax, [rbx]
0x180015c50  mov     rcx, rbx
0x180015c53  mov     rax, [rax+8]
0x180015c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c5c  nop
0x180015c5d  mov     rax, [rdi]
0x180015c60  lea     rdx, [rbp+450h+Buf2]
0x180015c64  mov     rcx, rdi
0x180015c67  mov     rax, [rax+18h]
0x180015c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c70  test    eax, eax
0x180015c72  jz      short loc_180015C87
0x180015c74  jle     loc_180015DED
0x180015c7a  movzx   eax, ax
0x180015c7d  or      eax, 80070000h
0x180015c82  jmp     loc_180015DEB
0x180015c87  mov     r8d, 10h; Size
0x180015c8d  lea     rdx, [rbp+450h+Buf2]; Buf2
0x180015c91  lea     rcx, Vault_DefaultVault_ID; Buf1
0x180015c98  call    memcmp_0
0x180015c9d  test    eax, eax
0x180015c9f  jz      short loc_180015CBF
0x180015ca1  mov     r8d, 10h; Size
0x180015ca7  lea     rdx, [rbp+450h+Buf2]; Buf2
0x180015cab  lea     rcx, Vault_CredmanVault_ID; Buf1
0x180015cb2  call    memcmp_0
0x180015cb7  test    eax, eax
0x180015cb9  jnz     loc_180015DF8
0x180015cbf  lea     rbx, [r14+4Ch]
0x180015cc3  lea     r9, [rbp+450h+var_4D0]
0x180015cc7  mov     esi, 8
0x180015ccc  mov     r8d, esi
0x180015ccf  mov     rdx, rbx
0x180015cd2  mov     r14d, 92h
0x180015cd8  mov     ecx, r14d
0x180015cdb  call    cs:__imp_LsapAdtAuditingEnabledByLogonId
0x180015ce1  test    eax, eax
0x180015ce3  js      loc_180015DEF
0x180015ce9  cmp     byte ptr [rbp+450h+var_4D0], 0
0x180015ced  jz      loc_180015DF8
0x180015cf3  lea     rdx, [rbp+450h+var_4C8]
0x180015cf7  lea     rcx, [rbp+450h+var_4CC]
0x180015cfb  call    cs:__imp_LsapAdtGetCallerProcessInfo
0x180015d01  test    eax, eax
0x180015d03  js      loc_180015DEF
0x180015d09  lea     rdx, [rbp+450h+var_4B8]
0x180015d0d  lea     rcx, [rbp+450h+var_4C0]
0x180015d11  call    cs:__imp_LsapQueryClientInfo
0x180015d17  test    eax, eax
0x180015d19  js      loc_180015DEF
0x180015d1f  lea     rdx, SourceString; "VAULT"
0x180015d26  lea     rcx, [rbp+450h+DestinationString]; DestinationString
0x180015d2a  call    cs:__imp_RtlInitUnicodeString
0x180015d30  mov     edx, 7
0x180015d35  mov     eax, [rbp+450h+var_4CC]
0x180015d38  mov     [rsp+570h+var_4D8], eax
0x180015d3f  mov     [rsp+570h+var_4E0], 1Bh
0x180015d4a  mov     rax, [rbp+450h+var_4C8]
0x180015d4e  mov     [rsp+570h+var_4E8], rax
0x180015d56  mov     [rsp+570h+var_4F0], 0Ch
0x180015d61  mov     [rsp+570h+var_4F8], r12d
0x180015d66  mov     [rsp+570h+var_500], 1Bh
0x180015d6e  mov     [rsp+570h+var_508], r15d
0x180015d73  mov     [rsp+570h+var_510], 1Bh
0x180015d7b  mov     rax, [rbx]
0x180015d7e  mov     [rsp+570h+var_518], rax
0x180015d83  mov     [rsp+570h+var_520], 5
0x180015d8b  lea     rax, [rbp+450h+DestinationString]
0x180015d8f  mov     [rsp+570h+var_528], rax
0x180015d94  mov     [rsp+570h+var_530], 1
0x180015d9c  mov     rax, [rbp+450h+var_4C0]
0x180015da0  mov     rcx, [rax]
0x180015da3  mov     [rsp+570h+var_538], rcx
0x180015da8  mov     [rsp+570h+var_540], 4
0x180015db0  mov     [rsp+570h+var_548], dx
0x180015db5  mov     [rsp+570h+var_550], si
0x180015dba  mov     r9d, r14d
0x180015dbd  mov     r8d, 1505h
0x180015dc3  lea     rcx, [rbp+450h+var_460]
0x180015dc7  call    cs:__imp_LsapAdtInitParametersArray
0x180015dcd  test    eax, eax
0x180015dcf  js      short loc_180015DEF
0x180015dd1  lea     rcx, [rbp+450h+var_460]
0x180015dd5  call    cs:__imp_LsapAdtWriteLog
0x180015ddb  jmp     short loc_180015DF8
0x180015ddd  lea     rcx, [rbp+450h+var_4A0]; this
0x180015de1  call    ??1CVaultStoreLock@@QEAA@XZ; CVaultStoreLock::~CVaultStoreLock(void)
0x180015de6  mov     eax, 80070490h
0x180015deb  test    eax, eax
0x180015ded  jns     short loc_180015DF8
0x180015def  mov     ecx, eax
0x180015df1  call    cs:__imp_LsapAuditFailed
0x180015df7  nop
0x180015df8  test    rdi, rdi
0x180015dfb  jz      short loc_180015E06
0x180015dfd  mov     rcx, rdi
0x180015e00  call    ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180015e05  nop
0x180015e06  mov     rcx, [rbp+450h+var_40]
0x180015e0d  xor     rcx, rsp; StackCookie
0x180015e10  call    __security_check_cookie
0x180015e15  add     rsp, 540h
0x180015e1c  pop     r15
0x180015e1e  pop     r14
0x180015e20  pop     r12
0x180015e22  pop     rdi
0x180015e23  pop     rsi
0x180015e24  pop     rbx
0x180015e25  pop     rbp
0x180015e26  retn
```
