# PolicyTransforms::ProcessEnterpriseFeatureControl(tagEnterprisePolicyValue_V1 *)

- ea: `0x180017e80`
- end: `0x180018010`
- name: `?ProcessEnterpriseFeatureControl@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(struct tagEnterprisePolicyValue_V1 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000aac0`
- `0x180017e80`
- `0x180018020`
- `0x18001efb4`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180017fb7`
- `OLEAUT32!__imp_SysStringLen` at `0x180017fb7`
- `OLEAUT32!__imp_VariantInit` at `0x180017f29`
- `OLEAUT32!__imp_VariantInit` at `0x180017f29`
- `OLEAUT32!__imp_VariantClear` at `0x180017f80`
- `OLEAUT32!__imp_VariantClear` at `0x180017fce`
- `OLEAUT32!__imp_VariantClear` at `0x180017f80`
- `OLEAUT32!__imp_VariantClear` at `0x180017fce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180017f42`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180017f42`

## pseudocode

```c
__int64 __fastcall PolicyTransforms::ProcessEnterpriseFeatureControl(struct tagEnterprisePolicyValue_V1 *a1)
{
  int v2; // esi
  unsigned int v3; // edi
  int IsWindowsUpdateManaged; // eax
  unsigned __int8 v6; // di
  bool v7; // zf
  int v8; // [rsp+20h] [rbp-50h]
  _OWORD v9[3]; // [rsp+30h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v2 = *((_DWORD *)a1 + 1);
  if ( v2 == 1 && *((_WORD *)a1 + 8) != 3 )
  {
    v3 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x582,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Enterprise\\PolicyTransforms.cpp",
      (const char *)0x80070057LL,
      v8);
    return v3;
  }
  if ( (unsigned int)PolicyHelpers::GetSkuUpdateManagementGroupHelper() )
  {
    if ( v2 == 1 && *((_DWORD *)a1 + 6) == 1 )
      return 0;
    memset(v9, 0, sizeof(v9));
    VariantInit((VARIANTARG *)&v9[1]);
    *(_QWORD *)((char *)v9 + 4) = 0;
    LODWORD(v9[0]) = 0;
    GetSystemTimeAsFileTime((LPFILETIME)&v9[2] + 1);
    IsWindowsUpdateManaged = PolicyTransforms::IsWindowsUpdateManaged((struct tagEnterprisePolicyValue_V1 *)v9);
    v3 = IsWindowsUpdateManaged;
    if ( IsWindowsUpdateManaged < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5AA,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Enterprise\\PolicyTransforms.cpp",
        (const char *)(unsigned int)IsWindowsUpdateManaged,
        (int)v9);
      VariantClear((VARIANTARG *)&v9[1]);
      return v3;
    }
    v6 = 1;
    if ( DWORD1(v9[0]) == 1 )
    {
      switch ( LOWORD(v9[1]) )
      {
        case 3:
          v7 = DWORD2(v9[1]) == 0;
          goto LABEL_18;
        case 8:
          v7 = SysStringLen(*((BSTR *)&v9[1] + 1)) == 0;
          goto LABEL_18;
        case 0x15:
          v7 = *((_QWORD *)&v9[1] + 1) == 0;
LABEL_18:
          v6 = v7;
          break;
      }
    }
    VariantClear((VARIANTARG *)&v9[1]);
    if ( v2 != 1 )
    {
      *(_QWORD *)((char *)a1 + 4) = 3;
      *((_WORD *)a1 + 8) = 3;
    }
    *((_DWORD *)a1 + 6) = v6;
    return 0;
  }
  *(_QWORD *)((char *)a1 + 4) = 3;
  *((_WORD *)a1 + 8) = 3;
  *((_DWORD *)a1 + 6) = 2;
  return 0;
}

```

## disassembly

```asm
0x180017e80  mov     [rsp-18h+arg_8], rbx
0x180017e85  mov     [rsp-18h+arg_10], rsi
0x180017e8a  push    rbp
0x180017e8b  push    rdi
0x180017e8c  push    r12
0x180017e8e  mov     rbp, rsp
0x180017e91  sub     rsp, 70h
0x180017e95  mov     rax, cs:__security_cookie
0x180017e9c  xor     rax, rsp
0x180017e9f  mov     [rbp+var_10], rax
0x180017ea3  mov     rbx, rcx
0x180017ea6  mov     esi, [rcx+4]
0x180017ea9  mov     r12d, 3
0x180017eaf  cmp     esi, 1
0x180017eb2  jnz     short loc_180017EDF
0x180017eb4  cmp     [rcx+10h], r12w
0x180017eb9  jz      short loc_180017EDF
0x180017ebb  mov     rcx, [rbp+18h]; this
0x180017ebf  mov     edi, 80070057h
0x180017ec4  mov     r9d, edi; char *
0x180017ec7  lea     r8, aCW1SSrcClientP_0; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180017ece  mov     edx, 582h; void *
0x180017ed3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ed8  mov     eax, edi
0x180017eda  jmp     loc_180017FEF
0x180017edf  call    ?GetSkuUpdateManagementGroupHelper@PolicyHelpers@@SA?AW4tagUpdateManagementGroup@@XZ; PolicyHelpers::GetSkuUpdateManagementGroupHelper(void)
0x180017ee4  test    eax, eax
0x180017ee6  jnz     short loc_180017EFD
0x180017ee8  mov     [rbx+4], r12
0x180017eec  mov     [rbx+10h], r12w
0x180017ef1  mov     dword ptr [rbx+18h], 2
0x180017ef8  jmp     loc_180017FED
0x180017efd  cmp     esi, 1
0x180017f00  jnz     short loc_180017F0B
0x180017f02  cmp     [rbx+18h], esi
0x180017f05  jz      loc_180017FED
0x180017f0b  xorps   xmm0, xmm0
0x180017f0e  movups  [rbp+var_40], xmm0
0x180017f12  movups  xmmword ptr [rbp+pvarg], xmm0
0x180017f16  movups  xmmword ptr [rbp+pvarg+10h], xmm0
0x180017f1a  lea     rdi, [rbp+var_40]
0x180017f1e  xor     eax, eax
0x180017f20  lea     ecx, [rax+30h]
0x180017f23  rep stosb
0x180017f25  lea     rcx, [rbp+pvarg]; pvarg
0x180017f29  call    cs:__imp_VariantInit
0x180017f2f  mov     qword ptr [rbp+var_40+4], 0
0x180017f37  mov     dword ptr [rbp+var_40], 0
0x180017f3e  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180017f42  call    cs:__imp_GetSystemTimeAsFileTime
0x180017f48  lea     rax, [rbp+var_40]
0x180017f4c  mov     [rbp+var_50], rax
0x180017f50  mov     [rbp+var_48], 1
0x180017f54  lea     rcx, [rbp+var_40]; struct tagEnterprisePolicyValue_V1 *
0x180017f58  call    ?IsWindowsUpdateManaged@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@@Z; PolicyTransforms::IsWindowsUpdateManaged(tagEnterprisePolicyValue_V1 *)
0x180017f5d  mov     edi, eax
0x180017f5f  test    eax, eax
0x180017f61  jns     short loc_180017F8B
0x180017f63  mov     rcx, [rbp+18h]; this
0x180017f67  mov     r9d, eax; char *
0x180017f6a  lea     r8, aCW1SSrcClientP_0; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180017f71  mov     edx, 5AAh; void *
0x180017f76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017f7b  nop
0x180017f7c  lea     rcx, [rbp+pvarg]; pvarg
0x180017f80  call    cs:__imp_VariantClear
0x180017f86  jmp     loc_180017ED8
0x180017f8b  mov     edi, 1
0x180017f90  cmp     dword ptr [rbp+var_40+4], edi
0x180017f93  jnz     short loc_180017FCA
0x180017f95  movzx   eax, word ptr [rbp+pvarg]
0x180017f99  cmp     ax, r12w
0x180017f9d  jz      short loc_180017FC1
0x180017f9f  cmp     ax, 8
0x180017fa3  jz      short loc_180017FB3
0x180017fa5  cmp     ax, 15h
0x180017fa9  jnz     short loc_180017FCA
0x180017fab  xor     edi, edi
0x180017fad  cmp     qword ptr [rbp+pvarg+8], rdi
0x180017fb1  jmp     short loc_180017FC6
0x180017fb3  mov     rcx, qword ptr [rbp+pvarg+8]; pbstr
0x180017fb7  call    cs:__imp_SysStringLen
0x180017fbd  test    eax, eax
0x180017fbf  jmp     short loc_180017FC6
0x180017fc1  xor     edi, edi
0x180017fc3  cmp     dword ptr [rbp+pvarg+8], edi
0x180017fc6  setz    dil
0x180017fca  lea     rcx, [rbp+pvarg]; pvarg
0x180017fce  call    cs:__imp_VariantClear
0x180017fd4  movzx   eax, dil
0x180017fd8  cmp     esi, 1
0x180017fdb  jz      short loc_180017FEA
0x180017fdd  mov     qword ptr [rbx+4], 3
0x180017fe5  mov     [rbx+10h], r12w
0x180017fea  mov     [rbx+18h], eax
0x180017fed  xor     eax, eax
0x180017fef  mov     rcx, [rbp+var_10]
0x180017ff3  xor     rcx, rsp; StackCookie
0x180017ff6  call    __security_check_cookie
0x180017ffb  lea     r11, [rsp+70h+var_s0]
0x180018000  mov     rbx, [r11+28h]
0x180018004  mov     rsi, [r11+30h]
0x180018008  mov     rsp, r11
0x18001800b  pop     r12
0x18001800d  pop     rdi
0x18001800e  pop     rbp
0x18001800f  retn
```
