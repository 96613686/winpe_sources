# TaskServiceImpl::RetrieveMaintenanceLaunchPolicy(TaskServiceImpl::_MAINTENANCE_POLICY *,ushort *)

- ea: `0x180039ab0`
- end: `0x180039e09`
- name: `?RetrieveMaintenanceLaunchPolicy@TaskServiceImpl@@AEAAJPEAU_MAINTENANCE_POLICY@1@PEAG@Z`
- size: `857`
- prototype: `int(TaskServiceImpl *__hidden this, struct TaskServiceImpl::_MAINTENANCE_POLICY *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180046c5c`

## callees

- `0x18002eeec`
- `0x1800338ec`
- `0x180039a80`
- `0x180039ab0`
- `0x180045974`
- `0x180046918`
- `0x18004e950`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039b65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039bb6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039c17`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039ccd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039d11`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039d8c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039b65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039bb6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039c17`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039ccd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039d11`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039d8c`
- `OLEAUT32!__imp_VariantChangeType` at `0x180039b04`
- `OLEAUT32!__imp_VariantChangeType` at `0x180039b1a`
- `OLEAUT32!__imp_VariantChangeType` at `0x180039b30`
- `OLEAUT32!__imp_VariantChangeType` at `0x180039c37`
- `OLEAUT32!__imp_VariantChangeType` at `0x180039b04`
- `OLEAUT32!__imp_VariantChangeType` at `0x180039b1a`
- `OLEAUT32!__imp_VariantChangeType` at `0x180039b30`
- `OLEAUT32!__imp_VariantChangeType` at `0x180039c37`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TaskServiceImpl::RetrieveMaintenanceLaunchPolicy(
        TaskServiceImpl *this,
        VARIANTARG *a2,
        unsigned __int16 *a3)
{
  VARIANTARG *v5; // rsi
  int v6; // edx
  int ValueW; // ebx
  LSTATUS v8; // eax
  int v9; // ebx
  int v10; // edx
  int v11; // eax
  unsigned __int64 v12; // rcx
  int v13; // r8d
  unsigned __int64 v14; // rcx
  int v15; // edx
  int v16; // eax
  unsigned __int64 v17; // rcx
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  int v23; // [rsp+48h] [rbp-B8h] BYREF
  PVOID v24[18]; // [rsp+50h] [rbp-B0h] BYREF
  PVOID pvData[18]; // [rsp+E0h] [rbp-20h] BYREF

  pvData[0] = 0;
  v24[0] = 0;
  v23 = 0;
  v22 = 0;
  VariantChangeType(a2, a2, 0, 0);
  v5 = a2 + 1;
  VariantChangeType(a2 + 1, a2 + 1, 0, 0);
  VariantChangeType(a2 + 2, a2 + 2, 0, 0);
  pcbData = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, a3, L"Activation Boundary", 2u, 0, 0, &pcbData);
  if ( ValueW )
  {
    if ( ValueW > 0 )
      v12 = (unsigned __int16)ValueW | 0x80070000;
    else
      v12 = (unsigned int)ValueW;
    if ( !tsched::IsErrorNotFound((tsched *)v12, v6) )
      goto LABEL_13;
  }
  else
  {
    ATL::CTempBuffer<unsigned char,128,ATL::CCRTAllocator>::AllocateBytes(pvData, pcbData);
    v8 = RegGetValueW(HKEY_LOCAL_MACHINE, a3, L"Activation Boundary", 2u, 0, pvData[0], &pcbData);
    ValueW = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
      {
        v9 = (unsigned __int16)v8;
LABEL_15:
        ValueW = v9 | 0x80070000;
        goto LABEL_39;
      }
      goto LABEL_39;
    }
    ATL::CComVariant::operator=(a2, pvData[0]);
  }
  pcbData = 4;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, a3, L"Randomized", 0x10u, 0, &v22, &pcbData);
  if ( ValueW )
  {
    if ( ValueW > 0 )
      v14 = (unsigned __int16)ValueW | 0x80070000;
    else
      v14 = (unsigned int)ValueW;
    if ( !tsched::IsErrorNotFound((tsched *)v14, v10) )
      goto LABEL_13;
    v11 = 1;
    v22 = 1;
  }
  else
  {
    if ( v22 )
      goto LABEL_22;
    VariantChangeType(v5, v5, 0, 8u);
    v11 = v22;
  }
  if ( v11 )
  {
LABEL_22:
    pcbData = 0;
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, a3, L"Random Delay", 2u, 0, 0, &pcbData);
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v17 = (unsigned __int16)ValueW | 0x80070000;
      else
        v17 = (unsigned int)ValueW;
      if ( !tsched::IsErrorNotFound((tsched *)v17, v15) )
        goto LABEL_13;
    }
    else
    {
      ATL::CTempBuffer<unsigned char,128,ATL::CCRTAllocator>::AllocateBytes(v24, pcbData);
      v16 = RegGetValueW(HKEY_LOCAL_MACHINE, a3, L"Random Delay", 2u, 0, v24[0], &pcbData);
      if ( v16 )
      {
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        ValueW = v16;
        goto LABEL_39;
      }
      ATL::CComVariant::operator=(v5, v24[0]);
    }
  }
  pcbData = 4;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, a3, L"WakeUp", 0x10u, 0, &v23, &pcbData);
  if ( !ValueW )
  {
    LOBYTE(v18) = v23 != 0;
    ATL::CComVariant::operator=(&a2[2], v18);
LABEL_38:
    ValueW = 0;
    goto LABEL_39;
  }
  if ( ValueW > 0 )
    v19 = (unsigned __int16)ValueW | 0x80070000;
  else
    v19 = (unsigned int)ValueW;
  if ( tsched::IsErrorNotFound((tsched *)v19, v18) )
    goto LABEL_38;
LABEL_13:
  if ( ValueW > 0 )
  {
    v9 = v13;
    goto LABEL_15;
  }
LABEL_39:
  ATL::CTempBuffer<unsigned char,128,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,128,ATL::CCRTAllocator>(v24);
  ATL::CTempBuffer<unsigned char,128,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,128,ATL::CCRTAllocator>(pvData);
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x180039ab0  mov     [rsp-8+arg_0], rbx
0x180039ab5  push    rbp
0x180039ab6  push    rsi
0x180039ab7  push    rdi
0x180039ab8  push    r12
0x180039aba  push    r13
0x180039abc  push    r14
0x180039abe  push    r15
0x180039ac0  lea     rbp, [rsp-80h]
0x180039ac5  sub     rsp, 180h
0x180039acc  mov     rax, cs:__security_cookie
0x180039ad3  xor     rax, rsp
0x180039ad6  mov     [rbp+0B0h+var_40], rax
0x180039ada  mov     rdi, r8
0x180039add  mov     r14, rdx
0x180039ae0  xor     r12d, r12d
0x180039ae3  mov     [rbp+0B0h+var_D0], r12
0x180039ae7  mov     [rsp+1B0h+var_160], r12
0x180039aec  mov     [rsp+1B0h+var_170], r12d
0x180039af1  mov     [rsp+1B0h+var_168], r12d
0x180039af6  mov     [rsp+1B0h+var_16C], r12d
0x180039afb  xor     r9d, r9d; vt
0x180039afe  xor     r8d, r8d; wFlags
0x180039b01  mov     rcx, rdx; pvargDest
0x180039b04  call    cs:__imp_VariantChangeType
0x180039b0a  lea     rsi, [r14+18h]
0x180039b0e  xor     r9d, r9d; vt
0x180039b11  xor     r8d, r8d; wFlags
0x180039b14  mov     rdx, rsi; pvarSrc
0x180039b17  mov     rcx, rsi; pvargDest
0x180039b1a  call    cs:__imp_VariantChangeType
0x180039b20  lea     r15, [r14+30h]
0x180039b24  xor     r9d, r9d; vt
0x180039b27  xor     r8d, r8d; wFlags
0x180039b2a  mov     rdx, r15; pvarSrc
0x180039b2d  mov     rcx, r15; pvargDest
0x180039b30  call    cs:__imp_VariantChangeType
0x180039b36  mov     [rsp+1B0h+var_170], r12d
0x180039b3b  lea     rax, [rsp+1B0h+var_170]
0x180039b40  mov     [rsp+1B0h+pcbData], rax; pcbData
0x180039b45  mov     [rsp+1B0h+pvData], r12; pvData
0x180039b4a  mov     [rsp+1B0h+pdwType], r12; pdwType
0x180039b4f  lea     r9d, [r12+2]; dwFlags
0x180039b54  lea     r8, ValueName; "Activation Boundary"
0x180039b5b  mov     rdx, rdi; lpSubKey
0x180039b5e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180039b65  call    cs:__imp_RegGetValueW
0x180039b6b  mov     ebx, eax
0x180039b6d  mov     r13d, 80070000h
0x180039b73  test    eax, eax
0x180039b75  jnz     loc_180039C43
0x180039b7b  mov     edx, [rsp+1B0h+var_170]
0x180039b7f  lea     rcx, [rbp+0B0h+var_D0]
0x180039b83  call    ?AllocateBytes@?$CTempBuffer@E$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAE_K@Z; ATL::CTempBuffer<uchar,128,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x180039b88  mov     rax, [rbp+0B0h+var_D0]
0x180039b8c  lea     rcx, [rsp+1B0h+var_170]
0x180039b91  mov     [rsp+1B0h+pcbData], rcx; pcbData
0x180039b96  mov     [rsp+1B0h+pvData], rax; pvData
0x180039b9b  mov     [rsp+1B0h+pdwType], r12; pdwType
0x180039ba0  lea     r9d, [r12+2]; dwFlags
0x180039ba5  lea     r8, ValueName; "Activation Boundary"
0x180039bac  mov     rdx, rdi; lpSubKey
0x180039baf  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180039bb6  call    cs:__imp_RegGetValueW
0x180039bbc  mov     ebx, eax
0x180039bbe  test    eax, eax
0x180039bc0  jz      short loc_180039BD0
0x180039bc2  jle     loc_180039DCC
0x180039bc8  movzx   ebx, ax
0x180039bcb  jmp     loc_180039C6D
0x180039bd0  mov     rdx, [rbp+0B0h+var_D0]
0x180039bd4  mov     rcx, r14
0x180039bd7  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x180039bdc  mov     [rsp+1B0h+var_170], 4
0x180039be4  lea     rax, [rsp+1B0h+var_170]
0x180039be9  mov     [rsp+1B0h+pcbData], rax; pcbData
0x180039bee  lea     rax, [rsp+1B0h+var_16C]
0x180039bf3  mov     [rsp+1B0h+pvData], rax; pvData
0x180039bf8  mov     [rsp+1B0h+pdwType], r12; pdwType
0x180039bfd  mov     r9d, 10h; dwFlags
0x180039c03  lea     r8, aRandomized; "Randomized"
0x180039c0a  mov     rdx, rdi; lpSubKey
0x180039c0d  mov     r14, 0FFFFFFFF80000002h
0x180039c14  mov     rcx, r14; hkey
0x180039c17  call    cs:__imp_RegGetValueW
0x180039c1d  mov     ebx, eax
0x180039c1f  test    eax, eax
0x180039c21  jnz     short loc_180039C75
0x180039c23  cmp     [rsp+1B0h+var_16C], r12d
0x180039c28  jnz     short loc_180039CA1
0x180039c2a  lea     r9d, [rax+8]; vt
0x180039c2e  xor     r8d, r8d; wFlags
0x180039c31  mov     rdx, rsi; pvarSrc
0x180039c34  mov     rcx, rsi; pvargDest
0x180039c37  call    cs:__imp_VariantChangeType
0x180039c3d  mov     eax, [rsp+1B0h+var_16C]
0x180039c41  jmp     short loc_180039C99
0x180039c43  movzx   r8d, bx
0x180039c47  test    ebx, ebx
0x180039c49  jg      short loc_180039C4F
0x180039c4b  mov     ecx, ebx
0x180039c4d  jmp     short loc_180039C55
0x180039c4f  mov     ecx, r8d
0x180039c52  or      ecx, r13d; this
0x180039c55  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180039c5a  test    al, al
0x180039c5c  jnz     loc_180039BDC
0x180039c62  test    ebx, ebx
0x180039c64  jle     loc_180039DCC
0x180039c6a  mov     ebx, r8d
0x180039c6d  or      ebx, r13d
0x180039c70  jmp     loc_180039DCC
0x180039c75  movzx   r8d, bx
0x180039c79  test    ebx, ebx
0x180039c7b  jg      short loc_180039C81
0x180039c7d  mov     ecx, ebx
0x180039c7f  jmp     short loc_180039C87
0x180039c81  mov     ecx, r8d
0x180039c84  or      ecx, r13d; this
0x180039c87  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180039c8c  test    al, al
0x180039c8e  jz      short loc_180039C62
0x180039c90  mov     eax, 1
0x180039c95  mov     [rsp+1B0h+var_16C], eax
0x180039c99  test    eax, eax
0x180039c9b  jz      loc_180039D58
0x180039ca1  mov     [rsp+1B0h+var_170], r12d
0x180039ca6  lea     rax, [rsp+1B0h+var_170]
0x180039cab  mov     [rsp+1B0h+pcbData], rax; pcbData
0x180039cb0  mov     [rsp+1B0h+pvData], r12; pvData
0x180039cb5  mov     [rsp+1B0h+pdwType], r12; pdwType
0x180039cba  mov     r9d, 2; dwFlags
0x180039cc0  lea     r8, aRandomDelay; "Random Delay"
0x180039cc7  mov     rdx, rdi; lpSubKey
0x180039cca  mov     rcx, r14; hkey
0x180039ccd  call    cs:__imp_RegGetValueW
0x180039cd3  mov     ebx, eax
0x180039cd5  test    eax, eax
0x180039cd7  jnz     short loc_180039D39
0x180039cd9  mov     edx, [rsp+1B0h+var_170]
0x180039cdd  lea     rcx, [rsp+1B0h+var_160]
0x180039ce2  call    ?AllocateBytes@?$CTempBuffer@E$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAE_K@Z; ATL::CTempBuffer<uchar,128,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x180039ce7  mov     rax, [rsp+1B0h+var_160]
0x180039cec  lea     rcx, [rsp+1B0h+var_170]
0x180039cf1  mov     [rsp+1B0h+pcbData], rcx; pcbData
0x180039cf6  mov     [rsp+1B0h+pvData], rax; pvData
0x180039cfb  mov     [rsp+1B0h+pdwType], r12; pdwType
0x180039d00  lea     r9d, [rbx+2]; dwFlags
0x180039d04  lea     r8, aRandomDelay; "Random Delay"
0x180039d0b  mov     rdx, rdi; lpSubKey
0x180039d0e  mov     rcx, r14; hkey
0x180039d11  call    cs:__imp_RegGetValueW
0x180039d17  test    eax, eax
0x180039d19  jz      short loc_180039D2A
0x180039d1b  jle     short loc_180039D23
0x180039d1d  movzx   eax, ax
0x180039d20  or      eax, r13d
0x180039d23  mov     ebx, eax
0x180039d25  jmp     loc_180039DCC
0x180039d2a  mov     rdx, [rsp+1B0h+var_160]
0x180039d2f  mov     rcx, rsi
0x180039d32  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x180039d37  jmp     short loc_180039D58
0x180039d39  movzx   r8d, bx
0x180039d3d  test    ebx, ebx
0x180039d3f  jg      short loc_180039D45
0x180039d41  mov     ecx, ebx
0x180039d43  jmp     short loc_180039D4B
0x180039d45  mov     ecx, r8d
0x180039d48  or      ecx, r13d; this
0x180039d4b  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180039d50  test    al, al
0x180039d52  jz      loc_180039C62
0x180039d58  mov     [rsp+1B0h+var_170], 4
0x180039d60  lea     rax, [rsp+1B0h+var_170]
0x180039d65  mov     [rsp+1B0h+pcbData], rax; pcbData
0x180039d6a  lea     rax, [rsp+1B0h+var_168]
0x180039d6f  mov     [rsp+1B0h+pvData], rax; pvData
0x180039d74  mov     [rsp+1B0h+pdwType], r12; pdwType
0x180039d79  mov     r9d, 10h; dwFlags
0x180039d7f  lea     r8, aWakeup; "WakeUp"
0x180039d86  mov     rdx, rdi; lpSubKey
0x180039d89  mov     rcx, r14; hkey
0x180039d8c  call    cs:__imp_RegGetValueW
0x180039d92  mov     ebx, eax
0x180039d94  test    eax, eax
0x180039d96  jnz     short loc_180039DAA
0x180039d98  cmp     [rsp+1B0h+var_168], r12d
0x180039d9d  setnz   dl
0x180039da0  mov     rcx, r15
0x180039da3  call    ??4CComVariant@ATL@@QEAAAEAV01@_N@Z; ATL::CComVariant::operator=(bool)
0x180039da8  jmp     short loc_180039DC9
0x180039daa  movzx   r8d, bx
0x180039dae  test    ebx, ebx
0x180039db0  jg      short loc_180039DB6
0x180039db2  mov     ecx, ebx
0x180039db4  jmp     short loc_180039DBC
0x180039db6  mov     ecx, r8d
0x180039db9  or      ecx, r13d; this
0x180039dbc  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180039dc1  test    al, al
0x180039dc3  jz      loc_180039C62
0x180039dc9  mov     ebx, r12d
0x180039dcc  lea     rcx, [rsp+1B0h+var_160]
0x180039dd1  call    ??1?$CTempBuffer@E$0IA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,128,ATL::CCRTAllocator>::~CTempBuffer<uchar,128,ATL::CCRTAllocator>(void)
0x180039dd6  nop
0x180039dd7  lea     rcx, [rbp+0B0h+var_D0]
0x180039ddb  call    ??1?$CTempBuffer@E$0IA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,128,ATL::CCRTAllocator>::~CTempBuffer<uchar,128,ATL::CCRTAllocator>(void)
0x180039de0  mov     eax, ebx
0x180039de2  mov     rcx, [rbp+0B0h+var_40]
0x180039de6  xor     rcx, rsp; StackCookie
0x180039de9  call    __security_check_cookie
0x180039dee  mov     rbx, [rsp+1B0h+arg_0]
0x180039df6  add     rsp, 180h
0x180039dfd  pop     r15
0x180039dff  pop     r14
0x180039e01  pop     r13
0x180039e03  pop     r12
0x180039e05  pop     rdi
0x180039e06  pop     rsi
0x180039e07  pop     rbp
0x180039e08  retn
```
