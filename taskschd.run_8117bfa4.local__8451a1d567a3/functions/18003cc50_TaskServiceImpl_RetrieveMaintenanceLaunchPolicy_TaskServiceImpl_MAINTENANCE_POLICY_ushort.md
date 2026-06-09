# TaskServiceImpl::RetrieveMaintenanceLaunchPolicy(TaskServiceImpl::_MAINTENANCE_POLICY *,ushort *)

- ea: `0x18003cc50`
- end: `0x18003cfe6`
- name: `?RetrieveMaintenanceLaunchPolicy@TaskServiceImpl@@AEAAJPEAU_MAINTENANCE_POLICY@1@PEAG@Z`
- size: `918`
- prototype: `int(TaskServiceImpl *__hidden this, struct TaskServiceImpl::_MAINTENANCE_POLICY *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004a5ac`

## callees

- `0x18003132c`
- `0x180036528`
- `0x18003cc18`
- `0x18003cc50`
- `0x1800490d8`
- `0x18004a1f8`
- `0x180052640`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cd17`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cd6e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cdd5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ce97`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cee1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cf62`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cd17`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cd6e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cdd5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ce97`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cee1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cf62`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003cca4`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003ccc0`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003ccdc`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003cdfb`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003cca4`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003ccc0`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003ccdc`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003cdfb`

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
0x18003cc50  mov     [rsp-8+arg_0], rbx
0x18003cc55  push    rbp
0x18003cc56  push    rsi
0x18003cc57  push    rdi
0x18003cc58  push    r12
0x18003cc5a  push    r13
0x18003cc5c  push    r14
0x18003cc5e  push    r15
0x18003cc60  lea     rbp, [rsp-80h]
0x18003cc65  sub     rsp, 180h
0x18003cc6c  mov     rax, cs:__security_cookie
0x18003cc73  xor     rax, rsp
0x18003cc76  mov     [rbp+0B0h+var_40], rax
0x18003cc7a  mov     rdi, r8
0x18003cc7d  mov     r14, rdx
0x18003cc80  xor     r12d, r12d
0x18003cc83  mov     [rbp+0B0h+var_D0], r12
0x18003cc87  mov     [rsp+1B0h+var_160], r12
0x18003cc8c  mov     [rsp+1B0h+var_170], r12d
0x18003cc91  mov     [rsp+1B0h+var_168], r12d
0x18003cc96  mov     [rsp+1B0h+var_16C], r12d
0x18003cc9b  xor     r9d, r9d; vt
0x18003cc9e  xor     r8d, r8d; wFlags
0x18003cca1  mov     rcx, rdx; pvargDest
0x18003cca4  call    cs:__imp_VariantChangeType
0x18003ccab  nop     dword ptr [rax+rax+00h]
0x18003ccb0  lea     rsi, [r14+18h]
0x18003ccb4  xor     r9d, r9d; vt
0x18003ccb7  xor     r8d, r8d; wFlags
0x18003ccba  mov     rdx, rsi; pvarSrc
0x18003ccbd  mov     rcx, rsi; pvargDest
0x18003ccc0  call    cs:__imp_VariantChangeType
0x18003ccc7  nop     dword ptr [rax+rax+00h]
0x18003cccc  lea     r15, [r14+30h]
0x18003ccd0  xor     r9d, r9d; vt
0x18003ccd3  xor     r8d, r8d; wFlags
0x18003ccd6  mov     rdx, r15; pvarSrc
0x18003ccd9  mov     rcx, r15; pvargDest
0x18003ccdc  call    cs:__imp_VariantChangeType
0x18003cce3  nop     dword ptr [rax+rax+00h]
0x18003cce8  mov     [rsp+1B0h+var_170], r12d
0x18003cced  lea     rax, [rsp+1B0h+var_170]
0x18003ccf2  mov     [rsp+1B0h+pcbData], rax; pcbData
0x18003ccf7  mov     [rsp+1B0h+pvData], r12; pvData
0x18003ccfc  mov     [rsp+1B0h+pdwType], r12; pdwType
0x18003cd01  lea     r9d, [r12+2]; dwFlags
0x18003cd06  lea     r8, ValueName; "Activation Boundary"
0x18003cd0d  mov     rdx, rdi; lpSubKey
0x18003cd10  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003cd17  call    cs:__imp_RegGetValueW
0x18003cd1e  nop     dword ptr [rax+rax+00h]
0x18003cd23  mov     ebx, eax
0x18003cd25  mov     r13d, 80070000h
0x18003cd2b  test    eax, eax
0x18003cd2d  jnz     loc_18003CE0D
0x18003cd33  mov     edx, [rsp+1B0h+var_170]
0x18003cd37  lea     rcx, [rbp+0B0h+var_D0]
0x18003cd3b  call    ?AllocateBytes@?$CTempBuffer@E$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAE_K@Z; ATL::CTempBuffer<uchar,128,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x18003cd40  mov     rax, [rbp+0B0h+var_D0]
0x18003cd44  lea     rcx, [rsp+1B0h+var_170]
0x18003cd49  mov     [rsp+1B0h+pcbData], rcx; pcbData
0x18003cd4e  mov     [rsp+1B0h+pvData], rax; pvData
0x18003cd53  mov     [rsp+1B0h+pdwType], r12; pdwType
0x18003cd58  lea     r9d, [r12+2]; dwFlags
0x18003cd5d  lea     r8, ValueName; "Activation Boundary"
0x18003cd64  mov     rdx, rdi; lpSubKey
0x18003cd67  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003cd6e  call    cs:__imp_RegGetValueW
0x18003cd75  nop     dword ptr [rax+rax+00h]
0x18003cd7a  mov     ebx, eax
0x18003cd7c  test    eax, eax
0x18003cd7e  jz      short loc_18003CD8E
0x18003cd80  jle     loc_18003CFA8
0x18003cd86  movzx   ebx, ax
0x18003cd89  jmp     loc_18003CE37
0x18003cd8e  mov     rdx, [rbp+0B0h+var_D0]
0x18003cd92  mov     rcx, r14
0x18003cd95  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18003cd9a  mov     [rsp+1B0h+var_170], 4
0x18003cda2  lea     rax, [rsp+1B0h+var_170]
0x18003cda7  mov     [rsp+1B0h+pcbData], rax; pcbData
0x18003cdac  lea     rax, [rsp+1B0h+var_16C]
0x18003cdb1  mov     [rsp+1B0h+pvData], rax; pvData
0x18003cdb6  mov     [rsp+1B0h+pdwType], r12; pdwType
0x18003cdbb  mov     r9d, 10h; dwFlags
0x18003cdc1  lea     r8, aRandomized; "Randomized"
0x18003cdc8  mov     rdx, rdi; lpSubKey
0x18003cdcb  mov     r14, 0FFFFFFFF80000002h
0x18003cdd2  mov     rcx, r14; hkey
0x18003cdd5  call    cs:__imp_RegGetValueW
0x18003cddc  nop     dword ptr [rax+rax+00h]
0x18003cde1  mov     ebx, eax
0x18003cde3  test    eax, eax
0x18003cde5  jnz     short loc_18003CE3F
0x18003cde7  cmp     [rsp+1B0h+var_16C], r12d
0x18003cdec  jnz     short loc_18003CE6B
0x18003cdee  lea     r9d, [rax+8]; vt
0x18003cdf2  xor     r8d, r8d; wFlags
0x18003cdf5  mov     rdx, rsi; pvarSrc
0x18003cdf8  mov     rcx, rsi; pvargDest
0x18003cdfb  call    cs:__imp_VariantChangeType
0x18003ce02  nop     dword ptr [rax+rax+00h]
0x18003ce07  mov     eax, [rsp+1B0h+var_16C]
0x18003ce0b  jmp     short loc_18003CE63
0x18003ce0d  movzx   r8d, bx
0x18003ce11  test    ebx, ebx
0x18003ce13  jg      short loc_18003CE19
0x18003ce15  mov     ecx, ebx
0x18003ce17  jmp     short loc_18003CE1F
0x18003ce19  mov     ecx, r8d
0x18003ce1c  or      ecx, r13d; this
0x18003ce1f  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18003ce24  test    al, al
0x18003ce26  jnz     loc_18003CD9A
0x18003ce2c  test    ebx, ebx
0x18003ce2e  jle     loc_18003CFA8
0x18003ce34  mov     ebx, r8d
0x18003ce37  or      ebx, r13d
0x18003ce3a  jmp     loc_18003CFA8
0x18003ce3f  movzx   r8d, bx
0x18003ce43  test    ebx, ebx
0x18003ce45  jg      short loc_18003CE4B
0x18003ce47  mov     ecx, ebx
0x18003ce49  jmp     short loc_18003CE51
0x18003ce4b  mov     ecx, r8d
0x18003ce4e  or      ecx, r13d; this
0x18003ce51  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18003ce56  test    al, al
0x18003ce58  jz      short loc_18003CE2C
0x18003ce5a  mov     eax, 1
0x18003ce5f  mov     [rsp+1B0h+var_16C], eax
0x18003ce63  test    eax, eax
0x18003ce65  jz      loc_18003CF2E
0x18003ce6b  mov     [rsp+1B0h+var_170], r12d
0x18003ce70  lea     rax, [rsp+1B0h+var_170]
0x18003ce75  mov     [rsp+1B0h+pcbData], rax; pcbData
0x18003ce7a  mov     [rsp+1B0h+pvData], r12; pvData
0x18003ce7f  mov     [rsp+1B0h+pdwType], r12; pdwType
0x18003ce84  mov     r9d, 2; dwFlags
0x18003ce8a  lea     r8, aRandomDelay; "Random Delay"
0x18003ce91  mov     rdx, rdi; lpSubKey
0x18003ce94  mov     rcx, r14; hkey
0x18003ce97  call    cs:__imp_RegGetValueW
0x18003ce9e  nop     dword ptr [rax+rax+00h]
0x18003cea3  mov     ebx, eax
0x18003cea5  test    eax, eax
0x18003cea7  jnz     short loc_18003CF0F
0x18003cea9  mov     edx, [rsp+1B0h+var_170]
0x18003cead  lea     rcx, [rsp+1B0h+var_160]
0x18003ceb2  call    ?AllocateBytes@?$CTempBuffer@E$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAE_K@Z; ATL::CTempBuffer<uchar,128,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x18003ceb7  mov     rax, [rsp+1B0h+var_160]
0x18003cebc  lea     rcx, [rsp+1B0h+var_170]
0x18003cec1  mov     [rsp+1B0h+pcbData], rcx; pcbData
0x18003cec6  mov     [rsp+1B0h+pvData], rax; pvData
0x18003cecb  mov     [rsp+1B0h+pdwType], r12; pdwType
0x18003ced0  lea     r9d, [rbx+2]; dwFlags
0x18003ced4  lea     r8, aRandomDelay; "Random Delay"
0x18003cedb  mov     rdx, rdi; lpSubKey
0x18003cede  mov     rcx, r14; hkey
0x18003cee1  call    cs:__imp_RegGetValueW
0x18003cee8  nop     dword ptr [rax+rax+00h]
0x18003ceed  test    eax, eax
0x18003ceef  jz      short loc_18003CF00
0x18003cef1  jle     short loc_18003CEF9
0x18003cef3  movzx   eax, ax
0x18003cef6  or      eax, r13d
0x18003cef9  mov     ebx, eax
0x18003cefb  jmp     loc_18003CFA8
0x18003cf00  mov     rdx, [rsp+1B0h+var_160]
0x18003cf05  mov     rcx, rsi
0x18003cf08  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18003cf0d  jmp     short loc_18003CF2E
0x18003cf0f  movzx   r8d, bx
0x18003cf13  test    ebx, ebx
0x18003cf15  jg      short loc_18003CF1B
0x18003cf17  mov     ecx, ebx
0x18003cf19  jmp     short loc_18003CF21
0x18003cf1b  mov     ecx, r8d
0x18003cf1e  or      ecx, r13d; this
0x18003cf21  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18003cf26  test    al, al
0x18003cf28  jz      loc_18003CE2C
0x18003cf2e  mov     [rsp+1B0h+var_170], 4
0x18003cf36  lea     rax, [rsp+1B0h+var_170]
0x18003cf3b  mov     [rsp+1B0h+pcbData], rax; pcbData
0x18003cf40  lea     rax, [rsp+1B0h+var_168]
0x18003cf45  mov     [rsp+1B0h+pvData], rax; pvData
0x18003cf4a  mov     [rsp+1B0h+pdwType], r12; pdwType
0x18003cf4f  mov     r9d, 10h; dwFlags
0x18003cf55  lea     r8, aWakeup; "WakeUp"
0x18003cf5c  mov     rdx, rdi; lpSubKey
0x18003cf5f  mov     rcx, r14; hkey
0x18003cf62  call    cs:__imp_RegGetValueW
0x18003cf69  nop     dword ptr [rax+rax+00h]
0x18003cf6e  mov     ebx, eax
0x18003cf70  test    eax, eax
0x18003cf72  jnz     short loc_18003CF86
0x18003cf74  cmp     [rsp+1B0h+var_168], r12d
0x18003cf79  setnz   dl
0x18003cf7c  mov     rcx, r15
0x18003cf7f  call    ??4CComVariant@ATL@@QEAAAEAV01@_N@Z; ATL::CComVariant::operator=(bool)
0x18003cf84  jmp     short loc_18003CFA5
0x18003cf86  movzx   r8d, bx
0x18003cf8a  test    ebx, ebx
0x18003cf8c  jg      short loc_18003CF92
0x18003cf8e  mov     ecx, ebx
0x18003cf90  jmp     short loc_18003CF98
0x18003cf92  mov     ecx, r8d
0x18003cf95  or      ecx, r13d; this
0x18003cf98  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18003cf9d  test    al, al
0x18003cf9f  jz      loc_18003CE2C
0x18003cfa5  mov     ebx, r12d
0x18003cfa8  lea     rcx, [rsp+1B0h+var_160]
0x18003cfad  call    ??1?$CTempBuffer@E$0IA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,128,ATL::CCRTAllocator>::~CTempBuffer<uchar,128,ATL::CCRTAllocator>(void)
0x18003cfb2  nop
0x18003cfb3  lea     rcx, [rbp+0B0h+var_D0]
0x18003cfb7  call    ??1?$CTempBuffer@E$0IA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,128,ATL::CCRTAllocator>::~CTempBuffer<uchar,128,ATL::CCRTAllocator>(void)
0x18003cfbc  mov     eax, ebx
0x18003cfbe  mov     rcx, [rbp+0B0h+var_40]
0x18003cfc2  xor     rcx, rsp; StackCookie
0x18003cfc5  call    __security_check_cookie
0x18003cfca  mov     rbx, [rsp+1B0h+arg_0]
0x18003cfd2  add     rsp, 180h
0x18003cfd9  pop     r15
0x18003cfdb  pop     r14
0x18003cfdd  pop     r13
0x18003cfdf  pop     r12
0x18003cfe1  pop     rdi
0x18003cfe2  pop     rsi
0x18003cfe3  pop     rbp
0x18003cfe4  retn
```
