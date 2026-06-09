# CUWFCspCurrentSessionNode::Execute(tagVARIANT)

- ea: `0x18000d620`
- end: `0x18000d7e3`
- name: `?Execute@CUWFCspCurrentSessionNode@@UEAAJUtagVARIANT@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(CUWFCspCurrentSessionNode *this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000d620`
- `0x180019104`
- `0x180019144`
- `0x180019238`
- `0x18001b010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d749`
- `msvcrt!_wcsicmp` at `0x18000d749`
- `OLEAUT32!__imp_VariantInit` at `0x18000d684`
- `OLEAUT32!__imp_VariantInit` at `0x18000d684`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000d6c3`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000d7a1`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000d6c3`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000d7a1`
- `uwfcfgmgmt!UwfCfgCommitFile` at `0x18000d7bb`
- `uwfcfgmgmt!UwfCfgCommitFile` at `0x18000d7bb`
- `uwfcfgmgmt!UwfCfgCommitFileDeletion` at `0x18000d7c3`
- `uwfcfgmgmt!UwfCfgCommitFileDeletion` at `0x18000d7c3`
- `uwfcfgmgmt!UwfCfgCommitRegistry` at `0x18000d762`
- `uwfcfgmgmt!UwfCfgCommitRegistry` at `0x18000d762`
- `uwfcfgmgmt!UwfCfgCommitRegistryDeletion` at `0x18000d76a`
- `uwfcfgmgmt!UwfCfgCommitRegistryDeletion` at `0x18000d76a`

## string_xrefs

- `0x18000d6ee`: `CommitSpecifiedValue`
- `0x18000d70a`: `RegistryKey`
- `0x18000d726`: `RegistryValue`

## pseudocode

```c
__int64 __fastcall CUWFCspCurrentSessionNode::Execute(CUWFCspCurrentSessionNode *this, struct tagVARIANT *a2)
{
  HRESULT v4; // ebx
  bool v5; // cl
  HRESULT v6; // eax
  wchar_t *String2; // [rsp+20h] [rbp-30h] BYREF
  int v9; // [rsp+28h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-20h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v12; // [rsp+78h] [rbp+28h] BYREF
  unsigned __int16 *v13; // [rsp+80h] [rbp+30h] BYREF
  const unsigned __int16 *v14; // [rsp+88h] [rbp+38h] BYREF

  v14 = 0;
  String2 = 0;
  v13 = 0;
  v12 = 0;
  v10 = 0;
  v9 = 0;
  if ( !a2->vt )
  {
    v4 = -2147024809;
    goto LABEL_21;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( *((_DWORD *)this + 11) == 25 || *((_DWORD *)this + 11) == 26 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
           *((_QWORD *)this + 3),
           3,
           &v14);
    if ( v4 >= 0 )
    {
      v4 = VariantChangeType(&pvarg, a2, 0, 8u);
      if ( v4 >= 0 )
      {
        if ( *((_DWORD *)this + 11) == 25 )
          v6 = UwfCfgCommitFile(v14, pvarg.bstrVal);
        else
          v6 = UwfCfgCommitFileDeletion(v14, pvarg.bstrVal);
        goto LABEL_20;
      }
    }
  }
  else
  {
    if ( (unsigned int)(*((_DWORD *)this + 11) - 27) >= 2 )
    {
      v4 = -2046820335;
      goto LABEL_21;
    }
    v4 = VariantChangeType(&pvarg, a2, 0, 8u);
    if ( v4 >= 0 )
    {
      v4 = CJsonParser::Initialize((CJsonParser *)&v9, pvarg.bstrVal);
      if ( v4 >= 0
        && CJsonParser::GetString((CJsonParser *)&v9, L"CommitSpecifiedValue", (const unsigned __int16 **)&String2) >= 0
        && CJsonParser::GetString((CJsonParser *)&v9, L"RegistryKey", (const unsigned __int16 **)&v13) >= 0
        && CJsonParser::GetString((CJsonParser *)&v9, L"RegistryValue", (const unsigned __int16 **)&v12) >= 0 )
      {
        v5 = _wcsicmp(L"true", String2) == 0;
        if ( *((_DWORD *)this + 11) == 27 )
          v6 = UwfCfgCommitRegistry(v5, v13, v12);
        else
          v6 = UwfCfgCommitRegistryDeletion(v5, v13, v12);
LABEL_20:
        v4 = v6;
      }
    }
  }
LABEL_21:
  CJsonParser::~CJsonParser((CJsonParser *)&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d620  mov     [rsp-18h+arg_0], rbx
0x18000d625  push    rbp
0x18000d626  push    rsi
0x18000d627  push    rdi
0x18000d628  mov     rbp, rsp
0x18000d62b  sub     rsp, 50h
0x18000d62f  xor     eax, eax
0x18000d631  mov     [rbp+arg_18], 0
0x18000d639  mov     rsi, rdx
0x18000d63c  mov     rdi, rcx
0x18000d63f  mov     [rbp+String2], 0
0x18000d647  mov     [rbp+arg_10], 0
0x18000d64f  mov     [rbp+arg_8], 0
0x18000d657  mov     [rbp+var_20], 0
0x18000d65f  mov     [rbp+var_28], 0
0x18000d666  cmp     ax, [rdx]
0x18000d669  jnz     short loc_18000D675
0x18000d66b  mov     ebx, 80070057h
0x18000d670  jmp     loc_18000D7CB
0x18000d675  xorps   xmm0, xmm0
0x18000d678  mov     qword ptr [rbp+pvarg+10h], rax
0x18000d67c  lea     rcx, [rbp+pvarg]; pvarg
0x18000d680  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000d684  call    cs:__imp_VariantInit
0x18000d68a  mov     ecx, [rdi+2Ch]
0x18000d68d  sub     ecx, 19h
0x18000d690  jz      loc_18000D772
0x18000d696  sub     ecx, 1
0x18000d699  jz      loc_18000D772
0x18000d69f  sub     ecx, 1
0x18000d6a2  jz      short loc_18000D6B3
0x18000d6a4  cmp     ecx, 1
0x18000d6a7  jz      short loc_18000D6B3
0x18000d6a9  mov     ebx, 86000011h
0x18000d6ae  jmp     loc_18000D7CB
0x18000d6b3  mov     r9d, 8; vt
0x18000d6b9  lea     rcx, [rbp+pvarg]; pvargDest
0x18000d6bd  xor     r8d, r8d; wFlags
0x18000d6c0  mov     rdx, rsi; pvarSrc
0x18000d6c3  call    cs:__imp_VariantChangeType
0x18000d6c9  mov     ebx, eax
0x18000d6cb  test    eax, eax
0x18000d6cd  js      loc_18000D7CB
0x18000d6d3  mov     rdx, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x18000d6d7  lea     rcx, [rbp+var_28]; this
0x18000d6db  call    ?Initialize@CJsonParser@@QEAAJPEBG@Z; CJsonParser::Initialize(ushort const *)
0x18000d6e0  mov     ebx, eax
0x18000d6e2  test    eax, eax
0x18000d6e4  js      loc_18000D7CB
0x18000d6ea  lea     r8, [rbp+String2]; unsigned __int16 **
0x18000d6ee  lea     rdx, aCommitspecifie; "CommitSpecifiedValue"
0x18000d6f5  lea     rcx, [rbp+var_28]; this
0x18000d6f9  call    ?GetString@CJsonParser@@QEAAJPEBGPEAPEBG@Z; CJsonParser::GetString(ushort const *,ushort const * *)
0x18000d6fe  test    eax, eax
0x18000d700  js      loc_18000D7CB
0x18000d706  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x18000d70a  lea     rdx, aRegistrykey; "RegistryKey"
0x18000d711  lea     rcx, [rbp+var_28]; this
0x18000d715  call    ?GetString@CJsonParser@@QEAAJPEBGPEAPEBG@Z; CJsonParser::GetString(ushort const *,ushort const * *)
0x18000d71a  test    eax, eax
0x18000d71c  js      loc_18000D7CB
0x18000d722  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x18000d726  lea     rdx, aRegistryvalue; "RegistryValue"
0x18000d72d  lea     rcx, [rbp+var_28]; this
0x18000d731  call    ?GetString@CJsonParser@@QEAAJPEBGPEAPEBG@Z; CJsonParser::GetString(ushort const *,ushort const * *)
0x18000d736  test    eax, eax
0x18000d738  js      loc_18000D7CB
0x18000d73e  mov     rdx, [rbp+String2]; String2
0x18000d742  lea     rcx, aTrue; "true"
0x18000d749  call    cs:__imp__wcsicmp
0x18000d74f  mov     r8, [rbp+arg_8]
0x18000d753  test    eax, eax
0x18000d755  mov     rdx, [rbp+arg_10]
0x18000d759  setz    cl
0x18000d75c  cmp     dword ptr [rdi+2Ch], 1Bh
0x18000d760  jnz     short loc_18000D76A
0x18000d762  call    cs:__imp_?UwfCfgCommitRegistry@@YAJ_NPEBG1@Z; UwfCfgCommitRegistry(bool,ushort const *,ushort const *)
0x18000d768  jmp     short loc_18000D7C9
0x18000d76a  call    cs:__imp_?UwfCfgCommitRegistryDeletion@@YAJ_NPEBG1@Z; UwfCfgCommitRegistryDeletion(bool,ushort const *,ushort const *)
0x18000d770  jmp     short loc_18000D7C9
0x18000d772  mov     rcx, [rdi+18h]
0x18000d776  lea     r8, [rbp+arg_18]
0x18000d77a  mov     edx, 3
0x18000d77f  mov     rax, [rcx]
0x18000d782  mov     rax, [rax+58h]
0x18000d786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d78b  mov     ebx, eax
0x18000d78d  test    eax, eax
0x18000d78f  js      short loc_18000D7CB
0x18000d791  mov     r9d, 8; vt
0x18000d797  lea     rcx, [rbp+pvarg]; pvargDest
0x18000d79b  xor     r8d, r8d; wFlags
0x18000d79e  mov     rdx, rsi; pvarSrc
0x18000d7a1  call    cs:__imp_VariantChangeType
0x18000d7a7  mov     ebx, eax
0x18000d7a9  test    eax, eax
0x18000d7ab  js      short loc_18000D7CB
0x18000d7ad  cmp     dword ptr [rdi+2Ch], 19h
0x18000d7b1  mov     rdx, qword ptr [rbp+pvarg+8]
0x18000d7b5  mov     rcx, [rbp+arg_18]
0x18000d7b9  jnz     short loc_18000D7C3
0x18000d7bb  call    cs:__imp_?UwfCfgCommitFile@@YAJPEBG0@Z; UwfCfgCommitFile(ushort const *,ushort const *)
0x18000d7c1  jmp     short loc_18000D7C9
0x18000d7c3  call    cs:__imp_?UwfCfgCommitFileDeletion@@YAJPEBG0@Z; UwfCfgCommitFileDeletion(ushort const *,ushort const *)
0x18000d7c9  mov     ebx, eax
0x18000d7cb  lea     rcx, [rbp+var_28]; this
0x18000d7cf  call    ??1CJsonParser@@QEAA@XZ; CJsonParser::~CJsonParser(void)
0x18000d7d4  mov     eax, ebx
0x18000d7d6  mov     rbx, [rsp+50h+arg_0]
0x18000d7db  add     rsp, 50h
0x18000d7df  pop     rdi
0x18000d7e0  pop     rsi
0x18000d7e1  pop     rbp
0x18000d7e2  retn
```
