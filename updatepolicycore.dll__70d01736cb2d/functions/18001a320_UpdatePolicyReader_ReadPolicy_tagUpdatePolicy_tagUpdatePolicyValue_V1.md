# UpdatePolicyReader::ReadPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 * *)

- ea: `0x18001a320`
- end: `0x18001a5a6`
- name: `?ReadPolicy@UpdatePolicyReader@@SAJW4tagUpdatePolicy@@PEAPEAUtagUpdatePolicyValue_V1@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(unsigned int, _QWORD *)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x18000c940`
- `0x180017c70`
- `0x180018020`
- `0x18001ba20`

## callees

- `0x18000aac0`
- `0x1800163c8`
- `0x180018ac8`
- `0x18001a320`
- `0x18001a5ac`
- `0x18001bb5c`
- `0x18001ccf0`
- `0x18001d64c`
- `0x18001da6c`
- `0x18001e25c`
- `0x18001efb4`
- `0x18001f2e0`
- `0x18001f9e8`
- `0x18002d630`
- `0x18002ffd0`
- `0x180030734`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001a556`
- `OLEAUT32!__imp_VariantClear` at `0x18001a575`
- `OLEAUT32!__imp_VariantClear` at `0x18001a556`
- `OLEAUT32!__imp_VariantClear` at `0x18001a575`

## string_xrefs

- `0x18001a404`: `C:\__w\1\s\src\Client\policy\src\Update\PolicyReader.cpp`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadPolicy(unsigned int a1, _QWORD *a2)
{
  unsigned __int64 v3; // rsi
  _OWORD *v4; // rbx
  int GPPolicy; // edi
  _OWORD *v6; // rax
  __int64 v7; // rcx
  int v8; // ebp
  int SkuUpdateManagementGroupHelper; // eax
  __int64 v10; // rcx
  int TestHookPolicy; // eax
  int *v12; // rdx
  int v14; // [rsp+20h] [rbp-48h]
  int v15; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = (int)a1;
  v4 = 0;
  if ( !a2 )
  {
    GPPolicy = -2147467261;
    goto LABEL_41;
  }
  if ( a1 > 0x2B )
  {
    GPPolicy = -2147024809;
    goto LABEL_41;
  }
  v6 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v6 )
  {
    GPPolicy = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\inc\\PolicyHelpers.h",
      (const char *)0x8007000ELL,
      v14);
    goto LABEL_41;
  }
  *v6 = 0;
  v6[1] = 0;
  *((_QWORD *)v6 + 4) = 0;
  v4 = v6;
  PolicyHelpers::InitPolicyState((struct tagUpdatePolicyValue_V1 *)v6);
  GPPolicy = 0;
  if ( (_DWORD)v3 == 18 )
  {
    v8 = 2;
  }
  else
  {
    SkuUpdateManagementGroupHelper = PolicyHelpers::GetSkuUpdateManagementGroupHelper(v7);
    v8 = SkuUpdateManagementGroupHelper;
    if ( !SkuUpdateManagementGroupHelper )
      goto LABEL_38;
    if ( SkuUpdateManagementGroupHelper == 1 )
    {
      v10 = 0xFA00C01D060LL;
      if ( _bittest64(&v10, v3) )
        goto LABEL_38;
    }
  }
  if ( TestHookPolicyReader::AreTestHooksEnabled() )
  {
    TestHookPolicy = UpdatePolicyReader::ReadTestHookPolicy((unsigned int)v3, v4);
    if ( TestHookPolicy < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Update\\PolicyReader.cpp",
        (const char *)(unsigned int)TestHookPolicy,
        (int)v4);
    goto LABEL_41;
  }
  if ( PolicyHelpers::IsGroupPolicySupported() )
  {
    GPPolicy = UpdatePolicyReader::ReadGPPolicy((unsigned int)v3, v4);
    if ( GPPolicy < 0 )
    {
      *(_QWORD *)((char *)v4 + 4) = 0;
      GPPolicy = 0;
    }
    if ( *((_DWORD *)v4 + 1) == 1 )
    {
      if ( v8 != 1 || (_DWORD)v3 != 3 || *((_DWORD *)v4 + 6) == 4 || *((_DWORD *)v4 + 6) == 5 )
        goto LABEL_41;
LABEL_38:
      *((_DWORD *)v4 + 1) = 2;
      goto LABEL_41;
    }
  }
  if ( (unsigned int)UpdatePolicyReader::IsPolicyEnabledInSkuMdmAllowList((unsigned int)v3) )
  {
    GPPolicy = UpdatePolicyReader::ReadMDMPolicy((unsigned int)v3, v4);
    if ( GPPolicy < 0 )
    {
      *(_QWORD *)((char *)v4 + 4) = 0;
      GPPolicy = 0;
    }
    if ( *((_DWORD *)v4 + 1) == 1 )
      goto LABEL_37;
  }
  GPPolicy = 0;
  *(_DWORD *)v4 = v3;
  if ( (_DWORD)v3 == 18 )
  {
    v15 = 0;
    GPPolicy = WUSystemInterfaceHelper::IsFlightingEnabled((WUSystemInterfaceHelper *)&v15, v12);
    if ( GPPolicy >= 0 )
    {
      *((_DWORD *)v4 + 6) = v15 != 0;
      *((_WORD *)v4 + 8) = 3;
      *((_DWORD *)v4 + 2) = 3;
      *((_DWORD *)v4 + 1) = 1;
    }
  }
  if ( *((_DWORD *)v4 + 1) != 1 )
  {
    GPPolicy = UpdatePolicyReader::ReadUXPolicy((unsigned int)v3, v4);
    if ( *((_DWORD *)v4 + 1) == 1 )
      goto LABEL_37;
    GPPolicy = UpdatePolicyReader::ReadLusPolicy((unsigned int)v3, v4);
    if ( GPPolicy < 0 )
    {
      *(_QWORD *)((char *)v4 + 4) = 0;
      GPPolicy = 0;
    }
    if ( *((_DWORD *)v4 + 1) == 1 )
    {
LABEL_37:
      if ( v8 == 1 && (_DWORD)v3 == 7 && (!*((_DWORD *)v4 + 6) || *((_DWORD *)v4 + 6) == 5) )
        goto LABEL_38;
    }
  }
LABEL_41:
  if ( v4 )
  {
    if ( GPPolicy >= 0 )
    {
      if ( *((_DWORD *)v4 + 1) == 2 )
      {
        *((_DWORD *)v4 + 2) = 0;
        *(_DWORD *)v4 = v3;
        VariantClear((VARIANTARG *)(v4 + 1));
      }
    }
    else
    {
      VariantClear((VARIANTARG *)(v4 + 1));
      *(_QWORD *)((char *)v4 + 4) = 0;
      GPPolicy = 0;
    }
    *a2 = v4;
  }
  return (unsigned int)GPPolicy;
}

```

## disassembly

```asm
0x18001a320  mov     [rsp+arg_10], rbx
0x18001a325  mov     [rsp+arg_18], rbp
0x18001a32a  push    rsi
0x18001a32b  push    rdi
0x18001a32c  push    r13
0x18001a32e  push    r14
0x18001a330  push    r15
0x18001a332  sub     rsp, 40h
0x18001a336  mov     rax, cs:__security_cookie
0x18001a33d  xor     rax, rsp
0x18001a340  mov     [rsp+68h+var_38], rax
0x18001a345  mov     r14, rdx
0x18001a348  movsxd  rsi, ecx
0x18001a34b  xor     r15d, r15d
0x18001a34e  mov     ebx, r15d
0x18001a351  lea     r13d, [r15+2]
0x18001a355  test    rdx, rdx
0x18001a358  jnz     short loc_18001A364
0x18001a35a  mov     edi, 80004003h
0x18001a35f  jmp     loc_18001A549
0x18001a364  cmp     esi, 2Bh ; '+'
0x18001a367  ja      loc_18001A544
0x18001a36d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a374  mov     ecx, 28h ; '('; unsigned __int64
0x18001a379  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a37e  test    rax, rax
0x18001a381  jz      loc_18001A524
0x18001a387  xorps   xmm0, xmm0
0x18001a38a  xor     ecx, ecx
0x18001a38c  movups  xmmword ptr [rax], xmm0
0x18001a38f  movups  xmmword ptr [rax+10h], xmm0
0x18001a393  mov     [rax+20h], rcx
0x18001a397  mov     rbx, rax
0x18001a39a  mov     rcx, rax; struct tagUpdatePolicyValue_V1 *
0x18001a39d  call    ?InitPolicyState@PolicyHelpers@@SAXPEAUtagUpdatePolicyValue_V1@@@Z; PolicyHelpers::InitPolicyState(tagUpdatePolicyValue_V1 *)
0x18001a3a2  mov     qword ptr [rsp+68h+var_48], rbx; int
0x18001a3a7  mov     edi, r15d
0x18001a3aa  cmp     esi, 12h
0x18001a3ad  jnz     short loc_18001A3B4
0x18001a3af  mov     ebp, r13d
0x18001a3b2  jmp     short loc_18001A3E1
0x18001a3b4  call    ?GetSkuUpdateManagementGroupHelper@PolicyHelpers@@SA?AW4tagUpdateManagementGroup@@XZ; PolicyHelpers::GetSkuUpdateManagementGroupHelper(void)
0x18001a3b9  mov     ebp, eax
0x18001a3bb  test    eax, eax
0x18001a3bd  jz      loc_18001A51E
0x18001a3c3  cmp     eax, 1
0x18001a3c6  jnz     short loc_18001A3E1
0x18001a3c8  cmp     esi, 2Bh ; '+'
0x18001a3cb  ja      short loc_18001A3E1
0x18001a3cd  mov     rcx, 0FA00C01D060h
0x18001a3d7  bt      rcx, rsi
0x18001a3db  jb      loc_18001A51E
0x18001a3e1  call    ?AreTestHooksEnabled@TestHookPolicyReader@@SA_NXZ; TestHookPolicyReader::AreTestHooksEnabled(void)
0x18001a3e6  test    al, al
0x18001a3e8  jz      short loc_18001A41A
0x18001a3ea  mov     rdx, rbx
0x18001a3ed  mov     ecx, esi
0x18001a3ef  call    ?ReadTestHookPolicy@UpdatePolicyReader@@CAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadTestHookPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 *)
0x18001a3f4  mov     rcx, [rsp+68h]; this
0x18001a3f9  test    eax, eax
0x18001a3fb  jns     loc_18001A549
0x18001a401  mov     r9d, eax; char *
0x18001a404  lea     r8, aCW1SSrcClientP_9; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001a40b  mov     edx, 0A8h; void *
0x18001a410  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a415  jmp     loc_18001A549
0x18001a41a  call    ?IsGroupPolicySupported@PolicyHelpers@@SA_NXZ; PolicyHelpers::IsGroupPolicySupported(void)
0x18001a41f  test    al, al
0x18001a421  jz      short loc_18001A46D
0x18001a423  mov     rdx, rbx
0x18001a426  mov     ecx, esi
0x18001a428  call    ?ReadGPPolicy@UpdatePolicyReader@@CAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 *)
0x18001a42d  mov     edi, eax
0x18001a42f  test    eax, eax
0x18001a431  jns     short loc_18001A43A
0x18001a433  mov     [rbx+4], r15
0x18001a437  mov     edi, r15d
0x18001a43a  cmp     dword ptr [rbx+4], 1
0x18001a43e  jnz     short loc_18001A46D
0x18001a440  cmp     ebp, 1
0x18001a443  jnz     loc_18001A549
0x18001a449  lea     eax, [rbp+2]
0x18001a44c  cmp     esi, eax
0x18001a44e  jnz     loc_18001A549
0x18001a454  cmp     dword ptr [rbx+18h], 4
0x18001a458  jz      loc_18001A549
0x18001a45e  cmp     dword ptr [rbx+18h], 5
0x18001a462  jz      loc_18001A549
0x18001a468  jmp     loc_18001A51E
0x18001a46d  mov     ecx, esi
0x18001a46f  call    ?IsPolicyEnabledInSkuMdmAllowList@UpdatePolicyReader@@CAHW4tagUpdatePolicy@@@Z; UpdatePolicyReader::IsPolicyEnabledInSkuMdmAllowList(tagUpdatePolicy)
0x18001a474  test    eax, eax
0x18001a476  jz      short loc_18001A495
0x18001a478  mov     rdx, rbx
0x18001a47b  mov     ecx, esi
0x18001a47d  call    ?ReadMDMPolicy@UpdatePolicyReader@@CAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadMDMPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 *)
0x18001a482  mov     edi, eax
0x18001a484  test    eax, eax
0x18001a486  jns     short loc_18001A48F
0x18001a488  mov     [rbx+4], r15
0x18001a48c  mov     edi, r15d
0x18001a48f  cmp     dword ptr [rbx+4], 1
0x18001a493  jz      short loc_18001A508
0x18001a495  mov     edi, r15d
0x18001a498  mov     [rbx], esi
0x18001a49a  cmp     esi, 12h
0x18001a49d  jnz     short loc_18001A4D3
0x18001a49f  mov     [rsp+68h+var_40], r15d
0x18001a4a4  lea     rcx, [rsp+68h+var_40]; this
0x18001a4a9  call    ?IsFlightingEnabled@WUSystemInterfaceHelper@@YAJPEAH@Z; WUSystemInterfaceHelper::IsFlightingEnabled(int *)
0x18001a4ae  mov     edi, eax
0x18001a4b0  test    eax, eax
0x18001a4b2  js      short loc_18001A4D3
0x18001a4b4  mov     eax, r15d
0x18001a4b7  cmp     [rsp+68h+var_40], r15d
0x18001a4bc  setnz   al
0x18001a4bf  mov     [rbx+18h], eax
0x18001a4c2  lea     eax, [rsi-0Fh]
0x18001a4c5  mov     [rbx+10h], ax
0x18001a4c9  mov     [rbx+8], eax
0x18001a4cc  mov     dword ptr [rbx+4], 1
0x18001a4d3  cmp     dword ptr [rbx+4], 1
0x18001a4d7  jz      short loc_18001A549
0x18001a4d9  mov     rdx, rbx
0x18001a4dc  mov     ecx, esi
0x18001a4de  call    ?ReadUXPolicy@UpdatePolicyReader@@CAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadUXPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 *)
0x18001a4e3  mov     edi, eax
0x18001a4e5  cmp     dword ptr [rbx+4], 1
0x18001a4e9  jz      short loc_18001A508
0x18001a4eb  mov     rdx, rbx
0x18001a4ee  mov     ecx, esi
0x18001a4f0  call    ?ReadLusPolicy@UpdatePolicyReader@@CAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadLusPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 *)
0x18001a4f5  mov     edi, eax
0x18001a4f7  test    eax, eax
0x18001a4f9  jns     short loc_18001A502
0x18001a4fb  mov     [rbx+4], r15
0x18001a4ff  mov     edi, r15d
0x18001a502  cmp     dword ptr [rbx+4], 1
0x18001a506  jnz     short loc_18001A549
0x18001a508  cmp     ebp, 1
0x18001a50b  jnz     short loc_18001A549
0x18001a50d  cmp     esi, 7
0x18001a510  jnz     short loc_18001A549
0x18001a512  cmp     [rbx+18h], r15d
0x18001a516  jz      short loc_18001A51E
0x18001a518  cmp     dword ptr [rbx+18h], 5
0x18001a51c  jnz     short loc_18001A549
0x18001a51e  mov     [rbx+4], r13d
0x18001a522  jmp     short loc_18001A549
0x18001a524  mov     edi, 8007000Eh
0x18001a529  mov     rcx, [rsp+68h]; this
0x18001a52e  mov     r9d, edi; char *
0x18001a531  lea     r8, aCW1SSrcClientP_5; "C:\\__w\\1\\s\\src\\Client\\policy\\inc"...
0x18001a538  mov     edx, 4Ah ; 'J'; void *
0x18001a53d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a542  jmp     short loc_18001A549
0x18001a544  mov     edi, 80070057h
0x18001a549  test    rbx, rbx
0x18001a54c  jz      short loc_18001A57E
0x18001a54e  test    edi, edi
0x18001a550  jns     short loc_18001A565
0x18001a552  lea     rcx, [rbx+10h]; pvarg
0x18001a556  call    cs:__imp_VariantClear
0x18001a55c  mov     [rbx+4], r15
0x18001a560  mov     edi, r15d
0x18001a563  jmp     short loc_18001A57B
0x18001a565  cmp     [rbx+4], r13d
0x18001a569  jnz     short loc_18001A57B
0x18001a56b  mov     [rbx+8], r15d
0x18001a56f  mov     [rbx], esi
0x18001a571  lea     rcx, [rbx+10h]; pvarg
0x18001a575  call    cs:__imp_VariantClear
0x18001a57b  mov     [r14], rbx
0x18001a57e  mov     eax, edi
0x18001a580  mov     rcx, [rsp+68h+var_38]
0x18001a585  xor     rcx, rsp; StackCookie
0x18001a588  call    __security_check_cookie
0x18001a58d  lea     r11, [rsp+68h+var_28]
0x18001a592  mov     rbx, [r11+40h]
0x18001a596  mov     rbp, [r11+48h]
0x18001a59a  mov     rsp, r11
0x18001a59d  pop     r15
0x18001a59f  pop     r14
0x18001a5a1  pop     r13
0x18001a5a3  pop     rdi
0x18001a5a4  pop     rsi
0x18001a5a5  retn
```
