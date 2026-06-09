# UpdatePolicyReader::ReadGPPolicy_UpdateServiceUrlAlternate(tagUpdatePolicyValue_V1 *,wchar_t const *,wchar_t const *)

- ea: `0x18001c88c`
- end: `0x18001c9b6`
- name: `?ReadGPPolicy_UpdateServiceUrlAlternate@UpdatePolicyReader@@CAJPEAUtagUpdatePolicyValue_V1@@PEB_W1@Z`
- size: `298`
- prototype: `__int64 __fastcall(struct tagUpdatePolicyValue_V1 *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001bf44`

## callees

- `0x18001c88c`
- `0x18001e704`
- `0x18001f09c`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001c934`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c934`
- `OLEAUT32!__imp_VariantInit` at `0x18001c8cf`
- `OLEAUT32!__imp_VariantInit` at `0x18001c8cf`
- `OLEAUT32!__imp_VariantClear` at `0x18001c98d`
- `OLEAUT32!__imp_VariantClear` at `0x18001c997`
- `OLEAUT32!__imp_VariantClear` at `0x18001c98d`
- `OLEAUT32!__imp_VariantClear` at `0x18001c997`

## string_xrefs

- `0x18001c94c`: `UpdateServiceUrlAlternate`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadGPPolicy_UpdateServiceUrlAlternate(
        struct tagUpdatePolicyValue_V1 *a1,
        const wchar_t *a2,
        const wchar_t *a3)
{
  int GPStringPolicyValueWithPolicyState; // edi
  int v7; // ecx
  bool v8; // zf
  UINT v9; // eax
  _BYTE v11[40]; // [rsp+30h] [rbp-30h] BYREF

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
      goto LABEL_12;
  }
  LOBYTE(v7) = !v8;
  if ( !v7 )
    goto LABEL_12;
  GPStringPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(
                                         a3,
                                         L"UseWUServer",
                                         a2,
                                         L"UpdateServiceUrlAlternate",
                                         a1);
  if ( GPStringPolicyValueWithPolicyState < 0 )
  {
LABEL_13:
    *(_QWORD *)((char *)a1 + 4) = 0;
    VariantClear((VARIANTARG *)((char *)a1 + 16));
    goto LABEL_14;
  }
  if ( !(unsigned int)PolicyHelpers::IsPolicyConfiguredAndEnabled(a1) )
  {
LABEL_12:
    GPStringPolicyValueWithPolicyState = -2145124326;
    goto LABEL_13;
  }
LABEL_14:
  VariantClear((VARIANTARG *)&v11[16]);
  return (unsigned int)GPStringPolicyValueWithPolicyState;
}

```

## disassembly

```asm
0x18001c88c  push    rbp
0x18001c88e  push    rbx
0x18001c88f  push    rsi
0x18001c890  push    rdi
0x18001c891  push    r14
0x18001c893  mov     rbp, rsp
0x18001c896  sub     rsp, 60h
0x18001c89a  mov     rax, cs:__security_cookie
0x18001c8a1  xor     rax, rsp
0x18001c8a4  mov     [rbp+var_8], rax
0x18001c8a8  xor     eax, eax
0x18001c8aa  lea     rdi, [rbp+var_30]
0x18001c8ae  mov     rbx, rcx
0x18001c8b1  mov     qword ptr [rbp+pvarg+10h], rax
0x18001c8b5  xorps   xmm0, xmm0
0x18001c8b8  mov     r14, r8
0x18001c8bb  movups  [rbp+var_30], xmm0
0x18001c8bf  lea     ecx, [rax+28h]
0x18001c8c2  mov     rsi, rdx
0x18001c8c5  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001c8c9  rep stosb
0x18001c8cb  lea     rcx, [rbp+pvarg]; pvarg
0x18001c8cf  call    cs:__imp_VariantInit
0x18001c8d5  lea     rax, [rbp+var_30]
0x18001c8d9  mov     qword ptr [rbp+var_30+4], 0
0x18001c8e1  lea     r9, aWuserver; "WUServer"
0x18001c8e8  mov     [rsp+60h+var_40], rax; struct tagUpdatePolicyValue_V1 *
0x18001c8ed  mov     r8, rsi; wchar_t *
0x18001c8f0  mov     dword ptr [rbp+var_30], 0
0x18001c8f7  lea     rdx, aUsewuserver; "UseWUServer"
0x18001c8fe  mov     rcx, r14; wchar_t *
0x18001c901  call    ?ReadGPStringPolicyValueWithPolicyState@UpdatePolicyReader@@CAJPEB_W000PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001c906  mov     edi, eax
0x18001c908  test    eax, eax
0x18001c90a  js      short loc_18001C981
0x18001c90c  cmp     dword ptr [rbp+var_30+4], 1
0x18001c910  jnz     short loc_18001C97C
0x18001c912  movzx   eax, word ptr [rbp+pvarg]
0x18001c916  cmp     ax, 3
0x18001c91a  jz      short loc_18001C940
0x18001c91c  cmp     ax, 8
0x18001c920  jz      short loc_18001C930
0x18001c922  cmp     ax, 15h
0x18001c926  jnz     short loc_18001C97C
0x18001c928  xor     ecx, ecx
0x18001c92a  cmp     qword ptr [rbp+pvarg+8], rcx
0x18001c92e  jmp     short loc_18001C945
0x18001c930  mov     rcx, qword ptr [rbp+pvarg+8]; pbstr
0x18001c934  call    cs:__imp_SysStringLen
0x18001c93a  xor     ecx, ecx
0x18001c93c  test    eax, eax
0x18001c93e  jmp     short loc_18001C945
0x18001c940  xor     ecx, ecx
0x18001c942  cmp     dword ptr [rbp+pvarg+8], ecx
0x18001c945  setnz   cl
0x18001c948  test    ecx, ecx
0x18001c94a  jz      short loc_18001C97C
0x18001c94c  lea     r9, aUpdateserviceu; "UpdateServiceUrlAlternate"
0x18001c953  mov     [rsp+60h+var_40], rbx; struct tagUpdatePolicyValue_V1 *
0x18001c958  mov     r8, rsi; wchar_t *
0x18001c95b  lea     rdx, aUsewuserver; "UseWUServer"
0x18001c962  mov     rcx, r14; wchar_t *
0x18001c965  call    ?ReadGPStringPolicyValueWithPolicyState@UpdatePolicyReader@@CAJPEB_W000PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001c96a  mov     edi, eax
0x18001c96c  test    eax, eax
0x18001c96e  js      short loc_18001C981
0x18001c970  mov     rcx, rbx; struct tagUpdatePolicyValue_V1 *
0x18001c973  call    ?IsPolicyConfiguredAndEnabled@PolicyHelpers@@SAHPEAUtagUpdatePolicyValue_V1@@@Z; PolicyHelpers::IsPolicyConfiguredAndEnabled(tagUpdatePolicyValue_V1 *)
0x18001c978  test    eax, eax
0x18001c97a  jnz     short loc_18001C993
0x18001c97c  mov     edi, 8024001Ah
0x18001c981  lea     rcx, [rbx+10h]; pvarg
0x18001c985  mov     qword ptr [rbx+4], 0
0x18001c98d  call    cs:__imp_VariantClear
0x18001c993  lea     rcx, [rbp+pvarg]; pvarg
0x18001c997  call    cs:__imp_VariantClear
0x18001c99d  mov     eax, edi
0x18001c99f  mov     rcx, [rbp+var_8]
0x18001c9a3  xor     rcx, rsp; StackCookie
0x18001c9a6  call    __security_check_cookie
0x18001c9ab  add     rsp, 60h
0x18001c9af  pop     r14
0x18001c9b1  pop     rdi
0x18001c9b2  pop     rsi
0x18001c9b3  pop     rbx
0x18001c9b4  pop     rbp
0x18001c9b5  retn
```
