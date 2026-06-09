# AesProtector::StoreKey(void *,void *)

- ea: `0x180092880`
- end: `0x180092a11`
- name: `?StoreKey@AesProtector@@AEAAJPEAX0@Z`
- size: `401`
- prototype: `int(AesProtector *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800926a0`

## callees

- `0x18002dd70`
- `0x18002ddb0`
- `0x180039344`
- `0x18003ecc8`
- `0x180060dc8`
- `0x180068f60`
- `0x1800921e0`
- `0x180092880`
- `0x1800985b8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800928d1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800928d1`
- `bcrypt!BCryptExportKey` at `0x18009290a`
- `bcrypt!BCryptExportKey` at `0x18009295a`
- `bcrypt!BCryptExportKey` at `0x18009290a`
- `bcrypt!BCryptExportKey` at `0x18009295a`

## pseudocode

```c
__int64 __fastcall AesProtector::StoreKey(AesProtector *this, void *a2, void *a3)
{
  unsigned __int16 *v3; // rsi
  __int64 v4; // r14
  __int64 v7; // rcx
  AesProtector *v8; // rcx
  NTSTATUS v9; // ebx
  UCHAR *v10; // rdi
  int v12; // ebx
  ULONG pcbResult; // [rsp+40h] [rbp-40h] BYREF
  ULONG v14; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned __int16 *v15; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v16[2]; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v17[24]; // [rsp+58h] [rbp-28h] BYREF

  v3 = 0;
  pcbResult = 0;
  v4 = 0;
  v15 = 0;
  *(_QWORD *)v16 = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !IsValidSid(a2) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  v9 = BCryptExportKey(a3, 0, L"KeyDataBlob", 0, 0, &pcbResult, 0);
  if ( v9 < 0 )
  {
    v10 = 0;
  }
  else
  {
    v10 = (UCHAR *)AesProtector::MemAllocate(v8, pcbResult);
    if ( !v10 )
      return 2147942414LL;
    v14 = 0;
    v9 = BCryptExportKey(a3, 0, L"KeyDataBlob", v10, pcbResult, &v14, 0);
    if ( v9 >= 0 )
    {
      v12 = AesProtector::EncodeKey(v8, v10, v14, &v15, (unsigned __int64 *)v16);
      if ( v12 < 0 )
      {
        v3 = v15;
        v4 = *(_QWORD *)v16;
      }
      else
      {
        CBioKeyVault::CBioKeyVault((CBioKeyVault *)v17);
        v4 = *(_QWORD *)v16;
        v3 = v15;
        v12 = CBioKeyVault::AddKey((CBioKeyVault *)v17, a2, v15, v16[0]);
        CBioKeyVault::~CBioKeyVault((CBioKeyVault *)v17);
      }
      goto LABEL_16;
    }
  }
  v12 = v9 | 0x10000000;
LABEL_16:
  if ( v3 )
    AesProtector::MemZeroAndRelease(v8, v3, 2 * v4);
  if ( v10 )
    AesProtector::MemZeroAndRelease(v8, v10, pcbResult);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180092880  mov     [rsp-28h+arg_0], rbx
0x180092885  mov     [rsp-28h+arg_18], rsi
0x18009288a  push    rbp
0x18009288b  push    rdi
0x18009288c  push    r12
0x18009288e  push    r14
0x180092890  push    r15
0x180092892  mov     rbp, rsp
0x180092895  sub     rsp, 80h
0x18009289c  mov     rax, cs:__security_cookie
0x1800928a3  xor     rax, rsp
0x1800928a6  mov     [rbp+var_10], rax
0x1800928aa  xor     esi, esi
0x1800928ac  mov     [rbp+var_40], 0
0x1800928b3  xor     r14d, r14d
0x1800928b6  mov     [rbp+var_38], rsi
0x1800928ba  mov     qword ptr [rbp+var_30], r14
0x1800928be  mov     r15, r8
0x1800928c1  mov     r12, rdx
0x1800928c4  test    rdx, rdx
0x1800928c7  jnz     short loc_1800928CE
0x1800928c9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800928ce  mov     rcx, r12; pSid
0x1800928d1  call    cs:__imp_IsValidSid
0x1800928d7  test    eax, eax
0x1800928d9  jnz     short loc_1800928E0
0x1800928db  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800928e0  test    r15, r15
0x1800928e3  jnz     short loc_1800928EA
0x1800928e5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800928ea  lea     rax, [rbp+var_40]
0x1800928ee  mov     [rsp+80h+dwFlags], esi; dwFlags
0x1800928f2  mov     [rsp+80h+pcbResult], rax; pcbResult
0x1800928f7  lea     r8, pszBlobType; "KeyDataBlob"
0x1800928fe  xor     r9d, r9d; pbOutput
0x180092901  mov     [rsp+80h+cbOutput], esi; cbOutput
0x180092905  xor     edx, edx; hExportKey
0x180092907  mov     rcx, r15; hKey
0x18009290a  call    cs:__imp_BCryptExportKey
0x180092910  mov     ebx, eax
0x180092912  test    eax, eax
0x180092914  js      loc_1800929BF
0x18009291a  mov     edx, [rbp+var_40]; unsigned __int64
0x18009291d  call    ?MemAllocate@AesProtector@@AEAAPEAX_K@Z; AesProtector::MemAllocate(unsigned __int64)
0x180092922  mov     rdi, rax
0x180092925  test    rax, rax
0x180092928  jnz     short loc_180092934
0x18009292a  mov     eax, 8007000Eh
0x18009292f  jmp     loc_1800929E9
0x180092934  lea     rax, [rbp+var_3C]
0x180092938  mov     [rsp+80h+dwFlags], esi; dwFlags
0x18009293c  mov     [rsp+80h+pcbResult], rax; pcbResult
0x180092941  lea     r8, pszBlobType; "KeyDataBlob"
0x180092948  mov     eax, [rbp+var_40]
0x18009294b  mov     r9, rdi; pbOutput
0x18009294e  xor     edx, edx; hExportKey
0x180092950  mov     [rsp+80h+cbOutput], eax; cbOutput
0x180092954  mov     rcx, r15; hKey
0x180092957  mov     [rbp+var_3C], esi
0x18009295a  call    cs:__imp_BCryptExportKey
0x180092960  mov     ebx, eax
0x180092962  test    eax, eax
0x180092964  js      short loc_1800929C1
0x180092966  mov     r8d, [rbp+var_3C]; unsigned __int64
0x18009296a  lea     rax, [rbp+var_30]
0x18009296e  lea     r9, [rbp+var_38]; unsigned __int16 **
0x180092972  mov     qword ptr [rsp+80h+cbOutput], rax; unsigned __int64 *
0x180092977  mov     rdx, rdi; unsigned __int8 *
0x18009297a  call    ?EncodeKey@AesProtector@@AEAAJPEAE_KPEAPEAGPEA_K@Z; AesProtector::EncodeKey(uchar *,unsigned __int64,ushort * *,unsigned __int64 *)
0x18009297f  mov     ebx, eax
0x180092981  test    eax, eax
0x180092983  js      short loc_1800929B5
0x180092985  lea     rcx, [rbp+var_28]; this
0x180092989  call    ??0CBioKeyVault@@QEAA@XZ; CBioKeyVault::CBioKeyVault(void)
0x18009298e  mov     r14, qword ptr [rbp+var_30]
0x180092992  lea     rcx, [rbp+var_28]; this
0x180092996  mov     rsi, [rbp+var_38]
0x18009299a  mov     r9d, r14d; unsigned int
0x18009299d  mov     r8, rsi; unsigned __int16 *
0x1800929a0  mov     rdx, r12; void *
0x1800929a3  call    ?AddKey@CBioKeyVault@@QEAAJPEAXPEAGK@Z; CBioKeyVault::AddKey(void *,ushort *,ulong)
0x1800929a8  lea     rcx, [rbp+var_28]; this
0x1800929ac  mov     ebx, eax
0x1800929ae  call    ??1CBioKeyVault@@QEAA@XZ; CBioKeyVault::~CBioKeyVault(void)
0x1800929b3  jmp     short loc_1800929C5
0x1800929b5  mov     rsi, [rbp+var_38]
0x1800929b9  mov     r14, qword ptr [rbp+var_30]
0x1800929bd  jmp     short loc_1800929C5
0x1800929bf  xor     edi, edi
0x1800929c1  bts     ebx, 1Ch
0x1800929c5  test    rsi, rsi
0x1800929c8  jz      short loc_1800929D6
0x1800929ca  lea     r8, [r14+r14]; unsigned __int64
0x1800929ce  mov     rdx, rsi; void *
0x1800929d1  call    ?MemZeroAndRelease@AesProtector@@AEAAXPEAX_K@Z; AesProtector::MemZeroAndRelease(void *,unsigned __int64)
0x1800929d6  test    rdi, rdi
0x1800929d9  jz      short loc_1800929E7
0x1800929db  mov     r8d, [rbp+var_40]; unsigned __int64
0x1800929df  mov     rdx, rdi; void *
0x1800929e2  call    ?MemZeroAndRelease@AesProtector@@AEAAXPEAX_K@Z; AesProtector::MemZeroAndRelease(void *,unsigned __int64)
0x1800929e7  mov     eax, ebx
0x1800929e9  mov     rcx, [rbp+var_10]
0x1800929ed  xor     rcx, rsp; StackCookie
0x1800929f0  call    __security_check_cookie
0x1800929f5  lea     r11, [rsp+80h+var_s0]
0x1800929fd  mov     rbx, [r11+30h]
0x180092a01  mov     rsi, [r11+48h]
0x180092a05  mov     rsp, r11
0x180092a08  pop     r15
0x180092a0a  pop     r14
0x180092a0c  pop     r12
0x180092a0e  pop     rdi
0x180092a0f  pop     rbp
0x180092a10  retn
```
