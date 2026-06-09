# COfflineActivation::get_InstallationID(ushort * *)

- ea: `0x180020b70`
- end: `0x180020d36`
- name: `?get_InstallationID@COfflineActivation@@UEAAJPEAPEAG@Z`
- size: `454`
- prototype: `__int64 __fastcall(COfflineActivation *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180003520`
- `0x180004288`
- `0x180004e18`
- `0x180020b70`
- `0x1800236b4`
- `0x180036c54`
- `0x18003c560`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ce6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ce6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020cfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020cfb`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180020cc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180020cd5`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180020cc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180020cd5`

## pseudocode

```c
__int64 __fastcall COfflineActivation::get_InstallationID(COfflineActivation *this, unsigned __int16 **a2)
{
  OLECHAR *v2; // r14
  unsigned __int16 *v3; // rbx
  unsigned __int16 *v4; // rdi
  unsigned int v7; // esi
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  unsigned __int16 *v13; // rax
  __int128 v14; // xmm1
  UINT64 qwValidityExpiration; // xmm0_8
  OLECHAR *v16; // rcx
  unsigned __int16 *v17; // r12
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v20; // [rsp+20h] [rbp-50h] BYREF
  int v21; // [rsp+28h] [rbp-48h] BYREF
  OLECHAR *strIn; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int16 *v23; // [rsp+38h] [rbp-38h] BYREF
  struct _tagSL_LICENSING_STATUS pProductSkuId; // [rsp+40h] [rbp-30h] BYREF

  v21 = 0;
  v2 = 0;
  v3 = 0;
  strIn = 0;
  v4 = 0;
  v20 = 0;
  v23 = 0;
  memset(&pProductSkuId, 0, sizeof(pProductSkuId));
  if ( !a2 )
  {
    v7 = -2147024809;
    v8 = 2147942487LL;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_15;
  }
  v9 = SPPGetWindowsLicenseStatus(&pProductSkuId, (enum tagE_LICENSING_CHANNEL *)&v21, 0);
  v7 = v9;
  if ( v9 < 0 )
  {
    v8 = (unsigned int)v9;
    goto LABEL_3;
  }
  v10 = SPPGetWindowsPhoneInstallationId(&pProductSkuId.SkuId, &strIn);
  v7 = v10;
  if ( v10 >= 0 )
  {
    v2 = strIn;
    v11 = CreateBSTRFromHString(strIn, &v20);
    v7 = v11;
    if ( v11 >= 0 )
    {
      v12 = CreateBSTRFromHString(v2, &v23);
      v7 = v12;
      if ( v12 >= 0 )
      {
        v13 = v20;
        v14 = *(_OWORD *)&pProductSkuId.eStatus;
        *((_OWORD *)this + 12) = pProductSkuId.SkuId;
        qwValidityExpiration = pProductSkuId.qwValidityExpiration;
        *((_OWORD *)this + 13) = v14;
        *((_QWORD *)this + 28) = qwValidityExpiration;
        *a2 = v13;
        v16 = (OLECHAR *)*((_QWORD *)this + 23);
        v17 = v23;
        if ( v16 )
          SysFreeString(v16);
        *((_QWORD *)this + 23) = v17;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
        v3 = v20;
        v4 = v23;
      }
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v11);
      v3 = v20;
    }
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v10);
    v2 = strIn;
  }
LABEL_15:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v4 )
    SysFreeString(v4);
  if ( v3 )
    SysFreeString(v3);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v7;
}

```

## disassembly

```asm
0x180020b70  mov     [rsp-28h+arg_10], rbx
0x180020b75  mov     [rsp-28h+arg_18], rsi
0x180020b7a  push    rbp
0x180020b7b  push    rdi
0x180020b7c  push    r12
0x180020b7e  push    r14
0x180020b80  push    r15
0x180020b82  mov     rbp, rsp
0x180020b85  sub     rsp, 70h
0x180020b89  mov     rax, cs:__security_cookie
0x180020b90  xor     rax, rsp
0x180020b93  mov     [rbp+var_8], rax
0x180020b97  xor     eax, eax
0x180020b99  mov     [rbp+var_48], 0
0x180020ba0  xor     r14d, r14d
0x180020ba3  mov     [rbp+pProductSkuId.qwValidityExpiration], rax
0x180020ba7  xor     ebx, ebx
0x180020ba9  mov     [rbp+strIn], r14
0x180020bad  xor     edi, edi
0x180020baf  mov     [rbp+var_50], rbx
0x180020bb3  mov     [rbp+var_38], rdi
0x180020bb7  xorps   xmm0, xmm0
0x180020bba  mov     r12, rdx
0x180020bbd  mov     r15, rcx
0x180020bc0  movups  xmmword ptr [rbp+pProductSkuId.SkuId.Data1], xmm0
0x180020bc4  movups  xmmword ptr [rbp+pProductSkuId.eStatus], xmm0
0x180020bc8  test    rdx, rdx
0x180020bcb  jnz     short loc_180020BDE
0x180020bcd  mov     esi, 80070057h
0x180020bd2  mov     ecx, esi
0x180020bd4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180020bd9  jmp     loc_180020CB2
0x180020bde  xor     r8d, r8d; struct _SYSTEMTIME *
0x180020be1  lea     rdx, [rbp+var_48]; enum tagE_LICENSING_CHANNEL *
0x180020be5  lea     rcx, [rbp+pProductSkuId]; struct _tagSL_LICENSING_STATUS *
0x180020be9  call    ?SPPGetWindowsLicenseStatus@@YAJPEAU_tagSL_LICENSING_STATUS@@PEAW4tagE_LICENSING_CHANNEL@@PEAU_SYSTEMTIME@@@Z; SPPGetWindowsLicenseStatus(_tagSL_LICENSING_STATUS *,tagE_LICENSING_CHANNEL *,_SYSTEMTIME *)
0x180020bee  mov     esi, eax
0x180020bf0  test    eax, eax
0x180020bf2  jns     short loc_180020BF8
0x180020bf4  mov     ecx, eax
0x180020bf6  jmp     short loc_180020BD4
0x180020bf8  lea     rdx, [rbp+strIn]; unsigned __int16 **
0x180020bfc  lea     rcx, [rbp+pProductSkuId]; pProductSkuId
0x180020c00  call    ?SPPGetWindowsPhoneInstallationId@@YAJPEBU_tagSL_LICENSING_STATUS@@PEAPEAG@Z; SPPGetWindowsPhoneInstallationId(_tagSL_LICENSING_STATUS const *,ushort * *)
0x180020c05  mov     esi, eax
0x180020c07  test    eax, eax
0x180020c09  jns     short loc_180020C1B
0x180020c0b  mov     ecx, eax
0x180020c0d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180020c12  mov     r14, [rbp+strIn]
0x180020c16  jmp     loc_180020CB2
0x180020c1b  mov     r14, [rbp+strIn]
0x180020c1f  lea     rdx, [rbp+var_50]; unsigned __int16 **
0x180020c23  mov     rcx, r14; strIn
0x180020c26  call    ?CreateBSTRFromHString@@YAJPEAGPEAPEAG@Z; CreateBSTRFromHString(ushort *,ushort * *)
0x180020c2b  mov     esi, eax
0x180020c2d  test    eax, eax
0x180020c2f  jns     short loc_180020C3E
0x180020c31  mov     ecx, eax
0x180020c33  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180020c38  mov     rbx, [rbp+var_50]
0x180020c3c  jmp     short loc_180020CB2
0x180020c3e  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x180020c42  mov     rcx, r14; strIn
0x180020c45  call    ?CreateBSTRFromHString@@YAJPEAGPEAPEAG@Z; CreateBSTRFromHString(ushort *,ushort * *)
0x180020c4a  mov     esi, eax
0x180020c4c  test    eax, eax
0x180020c4e  jns     short loc_180020C61
0x180020c50  mov     ecx, eax
0x180020c52  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180020c57  mov     rbx, [rbp+var_50]
0x180020c5b  mov     rdi, [rbp+var_38]
0x180020c5f  jmp     short loc_180020CB2
0x180020c61  movups  xmm0, xmmword ptr [rbp+pProductSkuId.SkuId.Data1]
0x180020c65  mov     rax, [rbp+var_50]
0x180020c69  movups  xmm1, xmmword ptr [rbp+pProductSkuId.eStatus]
0x180020c6d  movups  xmmword ptr [r15+0C0h], xmm0
0x180020c75  movsd   xmm0, [rbp+pProductSkuId.qwValidityExpiration]
0x180020c7a  movups  xmmword ptr [r15+0D0h], xmm1
0x180020c82  movsd   qword ptr [r15+0E0h], xmm0
0x180020c8b  mov     [r12], rax
0x180020c8f  mov     rcx, [r15+0B8h]; bstrString
0x180020c96  mov     r12, [rbp+var_38]
0x180020c9a  test    rcx, rcx
0x180020c9d  jz      short loc_180020CAB
0x180020c9f  call    cs:__imp_SysFreeString
0x180020ca6  nop     dword ptr [rax+rax+00h]
0x180020cab  mov     [r15+0B8h], r12
0x180020cb2  mov     ecx, esi
0x180020cb4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180020cb9  test    rdi, rdi
0x180020cbc  jz      short loc_180020CCD
0x180020cbe  mov     rcx, rdi; bstrString
0x180020cc1  call    cs:__imp_SysFreeString
0x180020cc8  nop     dword ptr [rax+rax+00h]
0x180020ccd  test    rbx, rbx
0x180020cd0  jz      short loc_180020CE1
0x180020cd2  mov     rcx, rbx; bstrString
0x180020cd5  call    cs:__imp_SysFreeString
0x180020cdc  nop     dword ptr [rax+rax+00h]
0x180020ce1  test    r14, r14
0x180020ce4  jz      short loc_180020D0E
0x180020ce6  call    cs:__imp_GetProcessHeap
0x180020ced  nop     dword ptr [rax+rax+00h]
0x180020cf2  lea     r8, [r14-4]; lpMem
0x180020cf6  xor     edx, edx; dwFlags
0x180020cf8  mov     rcx, rax; hHeap
0x180020cfb  call    cs:__imp_HeapFree
0x180020d02  nop     dword ptr [rax+rax+00h]
0x180020d07  xor     ecx, ecx
0x180020d09  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180020d0e  mov     eax, esi
0x180020d10  mov     rcx, [rbp+var_8]
0x180020d14  xor     rcx, rsp; StackCookie
0x180020d17  call    __security_check_cookie
0x180020d1c  lea     r11, [rsp+70h+var_s0]
0x180020d21  mov     rbx, [r11+40h]
0x180020d25  mov     rsi, [r11+48h]
0x180020d29  mov     rsp, r11
0x180020d2c  pop     r15
0x180020d2e  pop     r14
0x180020d30  pop     r12
0x180020d32  pop     rdi
0x180020d33  pop     rbp
0x180020d34  retn
```
