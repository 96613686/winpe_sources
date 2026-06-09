# UpdatePolicyReader::ReadGPPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection(tagUpdatePolicyValue_V1 *,wchar_t const *,wchar_t const *)

- ea: `0x18001cbac`
- end: `0x18001cce8`
- name: `?ReadGPPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection@UpdatePolicyReader@@CAJPEAUtagUpdatePolicyValue_V1@@PEB_W1@Z`
- size: `316`
- prototype: `__int64 __fastcall(struct tagUpdatePolicyValue_V1 *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18001bf44`

## callees

- `0x18001cbac`
- `0x18001e52c`
- `0x18001e704`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001cc58`
- `OLEAUT32!__imp_SysStringLen` at `0x18001cc58`
- `OLEAUT32!__imp_VariantInit` at `0x18001cbef`
- `OLEAUT32!__imp_VariantInit` at `0x18001cbef`
- `OLEAUT32!__imp_VariantClear` at `0x18001ccbf`
- `OLEAUT32!__imp_VariantClear` at `0x18001ccc9`
- `OLEAUT32!__imp_VariantClear` at `0x18001ccbf`
- `OLEAUT32!__imp_VariantClear` at `0x18001ccc9`

## string_xrefs

- `0x18001cc75`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadGPPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection(
        struct tagUpdatePolicyValue_V1 *a1,
        const wchar_t *a2,
        const wchar_t *a3)
{
  int GPStringPolicyValueWithPolicyState; // edi
  int v7; // ecx
  bool v8; // zf
  UINT v9; // eax
  _BYTE v11[40]; // [rsp+40h] [rbp-30h] BYREF

  memset(v11, 0, sizeof(v11));
  VariantInit((VARIANTARG *)&v11[16]);
  *(_QWORD *)&v11[4] = 0;
  *(_DWORD *)v11 = 0;
  GPStringPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(
                                         a3,
                                         L"UseWUServer",
                                         a2,
                                         L"WUServer",
                                         (struct tagUpdatePolicyValue_V1 *)v11);
  if ( GPStringPolicyValueWithPolicyState < 0 )
    goto LABEL_13;
  if ( *(_DWORD *)&v11[4] != 1 )
    goto LABEL_12;
  switch ( *(_WORD *)&v11[16] )
  {
    case 3:
      v7 = 0;
      v8 = *(_DWORD *)&v11[24] == 0;
      break;
    case 8:
      v9 = SysStringLen(*(BSTR *)&v11[24]);
      v7 = 0;
      v8 = v9 == 0;
      break;
    case 0x15:
      v7 = 0;
      v8 = *(_QWORD *)&v11[24] == 0;
      break;
    default:
LABEL_12:
      GPStringPolicyValueWithPolicyState = -2145124326;
LABEL_13:
      *(_QWORD *)((char *)a1 + 4) = 0;
      VariantClear((VARIANTARG *)((char *)a1 + 16));
      goto LABEL_14;
  }
  LOBYTE(v7) = !v8;
  if ( !v7 )
    goto LABEL_12;
  GPStringPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPDWordPolicyValueWithPolicyState(
                                         a3,
                                         L"UseWUServer",
                                         a2,
                                         L"DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection",
                                         0,
                                         0,
                                         1u,
                                         a1);
  if ( GPStringPolicyValueWithPolicyState < 0 )
    goto LABEL_13;
LABEL_14:
  VariantClear((VARIANTARG *)&v11[16]);
  return (unsigned int)GPStringPolicyValueWithPolicyState;
}

```

## disassembly

```asm
0x18001cbac  push    rbp
0x18001cbae  push    rbx
0x18001cbaf  push    rsi
0x18001cbb0  push    rdi
0x18001cbb1  push    r14
0x18001cbb3  mov     rbp, rsp
0x18001cbb6  sub     rsp, 70h
0x18001cbba  mov     rax, cs:__security_cookie
0x18001cbc1  xor     rax, rsp
0x18001cbc4  mov     [rbp+var_8], rax
0x18001cbc8  xor     eax, eax
0x18001cbca  lea     rdi, [rbp+var_30]
0x18001cbce  mov     rbx, rcx
0x18001cbd1  mov     qword ptr [rbp+pvarg+10h], rax
0x18001cbd5  xorps   xmm0, xmm0
0x18001cbd8  mov     r14, r8
0x18001cbdb  movups  [rbp+var_30], xmm0
0x18001cbdf  lea     ecx, [rax+28h]
0x18001cbe2  mov     rsi, rdx
0x18001cbe5  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001cbe9  rep stosb
0x18001cbeb  lea     rcx, [rbp+pvarg]; pvarg
0x18001cbef  call    cs:__imp_VariantInit
0x18001cbf5  lea     rax, [rbp+var_30]
0x18001cbf9  mov     qword ptr [rbp+var_30+4], 0
0x18001cc01  lea     r9, aWuserver; "WUServer"
0x18001cc08  mov     [rsp+70h+var_50], rax; struct tagUpdatePolicyValue_V1 *
0x18001cc0d  mov     r8, rsi; wchar_t *
0x18001cc10  mov     dword ptr [rbp+var_30], 0
0x18001cc17  lea     rdx, aUsewuserver; "UseWUServer"
0x18001cc1e  mov     rcx, r14; wchar_t *
0x18001cc21  call    ?ReadGPStringPolicyValueWithPolicyState@UpdatePolicyReader@@CAJPEB_W000PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001cc26  mov     edi, eax
0x18001cc28  test    eax, eax
0x18001cc2a  js      loc_18001CCB3
0x18001cc30  cmp     dword ptr [rbp+var_30+4], 1
0x18001cc34  jnz     short loc_18001CCAE
0x18001cc36  movzx   eax, word ptr [rbp+pvarg]
0x18001cc3a  cmp     ax, 3
0x18001cc3e  jz      short loc_18001CC64
0x18001cc40  cmp     ax, 8
0x18001cc44  jz      short loc_18001CC54
0x18001cc46  cmp     ax, 15h
0x18001cc4a  jnz     short loc_18001CCAE
0x18001cc4c  xor     ecx, ecx
0x18001cc4e  cmp     qword ptr [rbp+pvarg+8], rcx
0x18001cc52  jmp     short loc_18001CC69
0x18001cc54  mov     rcx, qword ptr [rbp+pvarg+8]; pbstr
0x18001cc58  call    cs:__imp_SysStringLen
0x18001cc5e  xor     ecx, ecx
0x18001cc60  test    eax, eax
0x18001cc62  jmp     short loc_18001CC69
0x18001cc64  xor     ecx, ecx
0x18001cc66  cmp     dword ptr [rbp+pvarg+8], ecx
0x18001cc69  setnz   cl
0x18001cc6c  test    ecx, ecx
0x18001cc6e  jz      short loc_18001CCAE
0x18001cc70  mov     [rsp+70h+var_38], rbx; struct tagUpdatePolicyValue_V1 *
0x18001cc75  lea     r9, aDonotenforceen; "DoNotEnforceEnterpriseTLSCertPinningFor"...
0x18001cc7c  mov     [rsp+70h+var_40], 1; unsigned int
0x18001cc84  lea     rdx, aUsewuserver; "UseWUServer"
0x18001cc8b  mov     [rsp+70h+var_48], 0; unsigned int
0x18001cc93  mov     r8, rsi; wchar_t *
0x18001cc96  mov     rcx, r14; wchar_t *
0x18001cc99  mov     dword ptr [rsp+70h+var_50], 0; unsigned int
0x18001cca1  call    ?ReadGPDWordPolicyValueWithPolicyState@UpdatePolicyReader@@CAJPEB_W000KKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPDWordPolicyValueWithPolicyState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001cca6  mov     edi, eax
0x18001cca8  test    eax, eax
0x18001ccaa  jns     short loc_18001CCC5
0x18001ccac  jmp     short loc_18001CCB3
0x18001ccae  mov     edi, 8024001Ah
0x18001ccb3  lea     rcx, [rbx+10h]; pvarg
0x18001ccb7  mov     qword ptr [rbx+4], 0
0x18001ccbf  call    cs:__imp_VariantClear
0x18001ccc5  lea     rcx, [rbp+pvarg]; pvarg
0x18001ccc9  call    cs:__imp_VariantClear
0x18001cccf  mov     eax, edi
0x18001ccd1  mov     rcx, [rbp+var_8]
0x18001ccd5  xor     rcx, rsp; StackCookie
0x18001ccd8  call    __security_check_cookie
0x18001ccdd  add     rsp, 70h
0x18001cce1  pop     r14
0x18001cce3  pop     rdi
0x18001cce4  pop     rsi
0x18001cce5  pop     rbx
0x18001cce6  pop     rbp
0x18001cce7  retn
```
