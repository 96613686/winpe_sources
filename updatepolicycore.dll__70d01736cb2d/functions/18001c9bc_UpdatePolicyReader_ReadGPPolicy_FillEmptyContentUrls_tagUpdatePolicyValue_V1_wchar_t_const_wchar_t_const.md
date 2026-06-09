# UpdatePolicyReader::ReadGPPolicy_FillEmptyContentUrls(tagUpdatePolicyValue_V1 *,wchar_t const *,wchar_t const *)

- ea: `0x18001c9bc`
- end: `0x18001cba6`
- name: `?ReadGPPolicy_FillEmptyContentUrls@UpdatePolicyReader@@CAJPEAUtagUpdatePolicyValue_V1@@PEB_W1@Z`
- size: `490`
- prototype: `__int64 __fastcall(struct tagUpdatePolicyValue_V1 *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001bf44`

## callees

- `0x18001c9bc`
- `0x18001e52c`
- `0x18001e704`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001caa0`
- `OLEAUT32!__imp_SysStringLen` at `0x18001cb0a`
- `OLEAUT32!__imp_SysStringLen` at `0x18001caa0`
- `OLEAUT32!__imp_SysStringLen` at `0x18001cb0a`
- `OLEAUT32!__imp_VariantInit` at `0x18001ca18`
- `OLEAUT32!__imp_VariantInit` at `0x18001ca38`
- `OLEAUT32!__imp_VariantInit` at `0x18001ca18`
- `OLEAUT32!__imp_VariantInit` at `0x18001ca38`
- `OLEAUT32!__imp_VariantClear` at `0x18001cb67`
- `OLEAUT32!__imp_VariantClear` at `0x18001cb71`
- `OLEAUT32!__imp_VariantClear` at `0x18001cb7b`
- `OLEAUT32!__imp_VariantClear` at `0x18001cb67`
- `OLEAUT32!__imp_VariantClear` at `0x18001cb71`
- `OLEAUT32!__imp_VariantClear` at `0x18001cb7b`

## string_xrefs

- `0x18001cac3`: `UpdateServiceUrlAlternate`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadGPPolicy_FillEmptyContentUrls(
        struct tagUpdatePolicyValue_V1 *a1,
        const wchar_t *a2,
        const wchar_t *a3)
{
  int GPStringPolicyValueWithPolicyState; // edi
  bool v7; // zf
  bool v8; // zf
  _BYTE v10[40]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v11[40]; // [rsp+68h] [rbp-1h] BYREF

  memset(v10, 0, sizeof(v10));
  memset(v11, 0, sizeof(v11));
  VariantInit((VARIANTARG *)&v10[16]);
  *(_QWORD *)&v10[4] = 0;
  *(_DWORD *)v10 = 0;
  memset(v11, 0, sizeof(v11));
  VariantInit((VARIANTARG *)&v11[16]);
  *(_QWORD *)&v11[4] = 0;
  *(_DWORD *)v11 = 0;
  GPStringPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(
                                         a3,
                                         L"UseWUServer",
                                         a2,
                                         L"WUServer",
                                         (struct tagUpdatePolicyValue_V1 *)v10);
  if ( GPStringPolicyValueWithPolicyState < 0 )
    goto LABEL_22;
  if ( *(_DWORD *)&v10[4] != 1 )
    goto LABEL_21;
  switch ( *(_WORD *)&v10[16] )
  {
    case 3:
      v7 = *(_DWORD *)&v10[24] == 0;
      break;
    case 8:
      v7 = SysStringLen(*(BSTR *)&v10[24]) == 0;
      break;
    case 0x15:
      v7 = *(_QWORD *)&v10[24] == 0;
      break;
    default:
      goto LABEL_21;
  }
  if ( v7 )
    goto LABEL_21;
  GPStringPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(
                                         a3,
                                         L"UseWUServer",
                                         a2,
                                         L"UpdateServiceUrlAlternate",
                                         (struct tagUpdatePolicyValue_V1 *)v11);
  if ( GPStringPolicyValueWithPolicyState < 0 )
  {
LABEL_22:
    *(_QWORD *)((char *)a1 + 4) = 0;
    VariantClear((VARIANTARG *)((char *)a1 + 16));
    goto LABEL_23;
  }
  if ( *(_DWORD *)&v11[4] != 1 )
  {
LABEL_21:
    GPStringPolicyValueWithPolicyState = -2145124326;
    goto LABEL_22;
  }
  switch ( *(_WORD *)&v11[16] )
  {
    case 3:
      v8 = *(_DWORD *)&v11[24] == 0;
      break;
    case 8:
      v8 = SysStringLen(*(BSTR *)&v11[24]) == 0;
      break;
    case 0x15:
      v8 = *(_QWORD *)&v11[24] == 0;
      break;
    default:
      goto LABEL_21;
  }
  if ( v8 )
    goto LABEL_21;
  GPStringPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPDWordPolicyValueWithPolicyState(
                                         a3,
                                         L"UseWUServer",
                                         a2,
                                         L"FillEmptyContentUrls",
                                         0,
                                         0,
                                         1u,
                                         a1);
  if ( GPStringPolicyValueWithPolicyState < 0 )
    goto LABEL_22;
LABEL_23:
  VariantClear((VARIANTARG *)&v10[16]);
  VariantClear((VARIANTARG *)&v11[16]);
  return (unsigned int)GPStringPolicyValueWithPolicyState;
}

```

## disassembly

```asm
0x18001c9bc  mov     [rsp-8+arg_18], rbx
0x18001c9c1  push    rbp
0x18001c9c2  push    rsi
0x18001c9c3  push    rdi
0x18001c9c4  push    r12
0x18001c9c6  push    r14
0x18001c9c8  lea     rbp, [rsp-37h]
0x18001c9cd  sub     rsp, 0A0h
0x18001c9d4  mov     rax, cs:__security_cookie
0x18001c9db  xor     rax, rsp
0x18001c9de  mov     [rbp+57h+var_30], rax
0x18001c9e2  xor     eax, eax
0x18001c9e4  lea     rdi, [rbp+57h+var_80]
0x18001c9e8  mov     rbx, rcx
0x18001c9eb  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001c9ef  xorps   xmm0, xmm0
0x18001c9f2  mov     qword ptr [rbp+57h+var_48+10h], rax
0x18001c9f6  xorps   xmm1, xmm1
0x18001c9f9  mov     r14, r8
0x18001c9fc  lea     ecx, [rax+28h]
0x18001c9ff  mov     rsi, rdx
0x18001ca02  movups  [rbp+57h+var_80], xmm0
0x18001ca06  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001ca0a  rep stosb
0x18001ca0c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001ca10  movups  [rbp+57h+var_58], xmm1
0x18001ca14  movups  xmmword ptr [rbp+57h+var_48], xmm1
0x18001ca18  call    cs:__imp_VariantInit
0x18001ca1e  xor     eax, eax
0x18001ca20  lea     rdi, [rbp+57h+var_58]
0x18001ca24  xor     r12d, r12d
0x18001ca27  mov     qword ptr [rbp+57h+var_80+4], r12
0x18001ca2b  mov     dword ptr [rbp+57h+var_80], r12d
0x18001ca2f  lea     ecx, [rax+28h]
0x18001ca32  rep stosb
0x18001ca34  lea     rcx, [rbp+57h+var_48]; pvarg
0x18001ca38  call    cs:__imp_VariantInit
0x18001ca3e  lea     rax, [rbp+57h+var_80]
0x18001ca42  mov     qword ptr [rbp+57h+var_58+4], r12
0x18001ca46  lea     r9, aWuserver; "WUServer"
0x18001ca4d  mov     [rsp+0C0h+var_A0], rax; struct tagUpdatePolicyValue_V1 *
0x18001ca52  mov     r8, rsi; wchar_t *
0x18001ca55  mov     dword ptr [rbp+57h+var_58], r12d
0x18001ca59  lea     rdx, aUsewuserver; "UseWUServer"
0x18001ca60  mov     rcx, r14; wchar_t *
0x18001ca63  call    ?ReadGPStringPolicyValueWithPolicyState@UpdatePolicyReader@@CAJPEB_W000PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001ca68  mov     edi, eax
0x18001ca6a  test    eax, eax
0x18001ca6c  js      loc_18001CB5F
0x18001ca72  cmp     dword ptr [rbp+57h+var_80+4], 1
0x18001ca76  jnz     loc_18001CB5A
0x18001ca7c  movzx   eax, word ptr [rbp+57h+pvarg]
0x18001ca80  cmp     ax, 3
0x18001ca84  jz      short loc_18001CAAA
0x18001ca86  cmp     ax, 8
0x18001ca8a  jz      short loc_18001CA9C
0x18001ca8c  cmp     ax, 15h
0x18001ca90  jnz     loc_18001CB5A
0x18001ca96  cmp     qword ptr [rbp+57h+pvarg+8], r12
0x18001ca9a  jmp     short loc_18001CAAE
0x18001ca9c  mov     rcx, qword ptr [rbp+57h+pvarg+8]; pbstr
0x18001caa0  call    cs:__imp_SysStringLen
0x18001caa6  test    eax, eax
0x18001caa8  jmp     short loc_18001CAAE
0x18001caaa  cmp     dword ptr [rbp+57h+pvarg+8], r12d
0x18001caae  mov     ecx, r12d
0x18001cab1  setnz   cl
0x18001cab4  test    ecx, ecx
0x18001cab6  jz      loc_18001CB5A
0x18001cabc  lea     rax, [rbp+57h+var_58]
0x18001cac0  mov     r8, rsi; wchar_t *
0x18001cac3  lea     r9, aUpdateserviceu; "UpdateServiceUrlAlternate"
0x18001caca  mov     [rsp+0C0h+var_A0], rax; struct tagUpdatePolicyValue_V1 *
0x18001cacf  lea     rdx, aUsewuserver; "UseWUServer"
0x18001cad6  mov     rcx, r14; wchar_t *
0x18001cad9  call    ?ReadGPStringPolicyValueWithPolicyState@UpdatePolicyReader@@CAJPEB_W000PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001cade  mov     edi, eax
0x18001cae0  test    eax, eax
0x18001cae2  js      short loc_18001CB5F
0x18001cae4  cmp     dword ptr [rbp+57h+var_58+4], 1
0x18001cae8  jnz     short loc_18001CB5A
0x18001caea  movzx   eax, word ptr [rbp+57h+var_48]
0x18001caee  cmp     ax, 3
0x18001caf2  jz      short loc_18001CB14
0x18001caf4  cmp     ax, 8
0x18001caf8  jz      short loc_18001CB06
0x18001cafa  cmp     ax, 15h
0x18001cafe  jnz     short loc_18001CB5A
0x18001cb00  cmp     qword ptr [rbp+57h+var_48+8], r12
0x18001cb04  jmp     short loc_18001CB18
0x18001cb06  mov     rcx, qword ptr [rbp+57h+var_48+8]; pbstr
0x18001cb0a  call    cs:__imp_SysStringLen
0x18001cb10  test    eax, eax
0x18001cb12  jmp     short loc_18001CB18
0x18001cb14  cmp     dword ptr [rbp+57h+var_48+8], r12d
0x18001cb18  mov     ecx, r12d
0x18001cb1b  setnz   cl
0x18001cb1e  test    ecx, ecx
0x18001cb20  jz      short loc_18001CB5A
0x18001cb22  mov     [rsp+0C0h+var_88], rbx; struct tagUpdatePolicyValue_V1 *
0x18001cb27  lea     r9, aFillemptyconte; "FillEmptyContentUrls"
0x18001cb2e  mov     [rsp+0C0h+var_90], 1; unsigned int
0x18001cb36  lea     rdx, aUsewuserver; "UseWUServer"
0x18001cb3d  mov     [rsp+0C0h+var_98], r12d; unsigned int
0x18001cb42  mov     r8, rsi; wchar_t *
0x18001cb45  mov     rcx, r14; wchar_t *
0x18001cb48  mov     dword ptr [rsp+0C0h+var_A0], r12d; unsigned int
0x18001cb4d  call    ?ReadGPDWordPolicyValueWithPolicyState@UpdatePolicyReader@@CAJPEB_W000KKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPDWordPolicyValueWithPolicyState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001cb52  mov     edi, eax
0x18001cb54  test    eax, eax
0x18001cb56  jns     short loc_18001CB6D
0x18001cb58  jmp     short loc_18001CB5F
0x18001cb5a  mov     edi, 8024001Ah
0x18001cb5f  lea     rcx, [rbx+10h]; pvarg
0x18001cb63  mov     [rbx+4], r12
0x18001cb67  call    cs:__imp_VariantClear
0x18001cb6d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001cb71  call    cs:__imp_VariantClear
0x18001cb77  lea     rcx, [rbp+57h+var_48]; pvarg
0x18001cb7b  call    cs:__imp_VariantClear
0x18001cb81  mov     eax, edi
0x18001cb83  mov     rcx, [rbp+57h+var_30]
0x18001cb87  xor     rcx, rsp; StackCookie
0x18001cb8a  call    __security_check_cookie
0x18001cb8f  mov     rbx, [rsp+0C0h+arg_18]
0x18001cb97  add     rsp, 0A0h
0x18001cb9e  pop     r14
0x18001cba0  pop     r12
0x18001cba2  pop     rdi
0x18001cba3  pop     rsi
0x18001cba4  pop     rbp
0x18001cba5  retn
```
