# CConfirmationInterrupt::_FormatDescription(ushort const *,ushort * *)

- ea: `0x18032e8dc`
- end: `0x18032ebe0`
- name: `?_FormatDescription@CConfirmationInterrupt@@AEAAJPEBGPEAPEAG@Z`
- size: `772`
- prototype: `__int64 __fastcall(CConfirmationInterrupt *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18032c320`

## callees

- `0x1800210a8`
- `0x1801e0668`
- `0x180249490`
- `0x18032e8dc`
- `0x18032edf0`
- `0x18032f0f8`
- `0x18032f1b8`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18032eb45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18032eb45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032e975`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032e9b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ea01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ea4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ea8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032eac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032eb56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032eb66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032eb77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032eb88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032eb99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ebaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032e975`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032e9b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ea01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ea4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ea8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032eac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032eb56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032eb66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032eb77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032eb88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032eb99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ebaa`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18032eb34`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18032eb34`
- `ext-ms-win-shell-fileplaceholder-l1-1-0!FECommon_GetStorageProviderDisplayName` at `0x18032e9c4`
- `ext-ms-win-shell-fileplaceholder-l1-1-0!FECommon_GetStorageProviderDisplayName` at `0x18032e9c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CConfirmationInterrupt::_FormatDescription(
        CConfirmationInterrupt *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  const wchar_t *v4; // r15
  unsigned __int16 *v5; // r12
  const wchar_t *v6; // r13
  _QWORD *v7; // r14
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, LPVOID *); // rbx
  HRESULT OwnerInformation; // edi
  __int64 *v11; // rcx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, LPVOID *); // rbx
  unsigned __int16 *v14; // r14
  unsigned __int16 *v15; // rbx
  const WCHAR *v16; // rax
  WCHAR *v17; // rsi
  unsigned __int16 *v19; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int16 *v20; // [rsp+58h] [rbp-31h]
  const wchar_t *v21; // [rsp+60h] [rbp-29h]
  const wchar_t *v22; // [rsp+68h] [rbp-21h]
  const unsigned __int16 *v23; // [rsp+70h] [rbp-19h]
  LPWSTR *ppwsz; // [rsp+78h] [rbp-11h]
  LPVOID pv; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int16 *v26; // [rsp+88h] [rbp-1h] BYREF
  unsigned __int16 *v27; // [rsp+90h] [rbp+7h] BYREF
  LPVOID v28; // [rsp+98h] [rbp+Fh] BYREF
  LPVOID v29; // [rsp+A0h] [rbp+17h] BYREF

  ppwsz = a3;
  v23 = a2;
  v22 = L"<%1 NULL:NameDest>";
  v4 = L"<%2 NULL:NameItem>";
  v21 = L"<%3 NULL:OpText>";
  v20 = L"<%5 NULL:Error>";
  v5 = L"<%6 NULL:CreationDateItem>";
  v6 = L"<%7 NULL:StorageProviderNameDest>";
  v29 = 0;
  pv = 0;
  v7 = (_QWORD *)((char *)this + 80);
  if ( !(unsigned __int8)ATL::CComPtrBase<IShellFolder>::operator!=((char *)this + 80, 0) )
  {
LABEL_6:
    v28 = 0;
    if ( (unsigned __int8)ATL::CComPtrBase<IShellFolder>::operator!=((char *)this + 72, 0) )
    {
      v12 = *v11;
      v13 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)*v11 + 40LL);
      CoTaskMemFree(0);
      OwnerInformation = v13(v12, 2147684353LL, &v28);
      if ( OwnerInformation < 0 )
      {
LABEL_27:
        CoTaskMemFree(v28);
        goto LABEL_28;
      }
      v4 = (const wchar_t *)v28;
    }
    if ( (*((_BYTE *)this + 48) & 4) != 0 )
      v21 = (const wchar_t *)*((_QWORD *)this + 8);
    v27 = 0;
    if ( (*((_BYTE *)this + 48) & 8) != 0 )
    {
      CoTaskMemFree(0);
      OwnerInformation = CConfirmationInterrupt::_GetOwnerInformation(this, &v27);
      if ( OwnerInformation < 0 )
      {
LABEL_26:
        CoTaskMemFree(v27);
        goto LABEL_27;
      }
      v14 = v27;
    }
    else
    {
      v14 = L"<%4 NULL:Owner>";
    }
    v15 = 0;
    v19 = 0;
    if ( (*((_BYTE *)this + 48) & 0x10) != 0 )
    {
      CoTaskMemFree(0);
      OwnerInformation = CConfirmationInterrupt::_GetErrorInformation(this, &v19);
      v15 = v19;
      if ( OwnerInformation < 0 )
      {
LABEL_25:
        CoTaskMemFree(v15);
        goto LABEL_26;
      }
      v20 = v19;
    }
    v26 = 0;
    if ( (*((_BYTE *)this + 48) & 0x40) != 0 )
    {
      CoTaskMemFree(0);
      OwnerInformation = CConfirmationInterrupt::_GetMergeFolderInfo(this, &v26);
      if ( OwnerInformation < 0 )
      {
LABEL_24:
        CoTaskMemFree(v26);
        goto LABEL_25;
      }
      v5 = v26;
    }
    v16 = (const WCHAR *)ShellConstructMessageStringW(g_hinst, v23, v22, v4, v21, v14, v20, v5, v6);
    v17 = (WCHAR *)v16;
    if ( v16 )
    {
      OwnerInformation = SHStrDupW(v16, ppwsz);
      LocalFree(v17);
    }
    else
    {
      OwnerInformation = -2147024882;
    }
    goto LABEL_24;
  }
  v8 = *v7;
  v9 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)*v7 + 40LL);
  CoTaskMemFree(0);
  OwnerInformation = v9(v8, 2147684353LL, &v29);
  if ( OwnerInformation >= 0 )
  {
    v22 = (const wchar_t *)v29;
    if ( *((char *)this + 48) >= 0 )
      goto LABEL_6;
    CoTaskMemFree(pv);
    OwnerInformation = FECommon_GetStorageProviderDisplayName(*v7, &pv);
    if ( OwnerInformation >= 0 )
    {
      v6 = (const wchar_t *)pv;
      goto LABEL_6;
    }
  }
LABEL_28:
  CoTaskMemFree(pv);
  CoTaskMemFree(v29);
  return (unsigned int)OwnerInformation;
}

```

## disassembly

```asm
0x18032e8dc  mov     [rsp-8+arg_18], rbx
0x18032e8e1  push    rbp
0x18032e8e2  push    rsi
0x18032e8e3  push    rdi
0x18032e8e4  push    r12
0x18032e8e6  push    r13
0x18032e8e8  push    r14
0x18032e8ea  push    r15
0x18032e8ec  lea     rbp, [rsp-27h]
0x18032e8f1  sub     rsp, 0B0h
0x18032e8f8  mov     rax, cs:__security_cookie
0x18032e8ff  xor     rax, rsp
0x18032e902  mov     [rbp+57h+var_38], rax
0x18032e906  mov     [rbp+57h+ppwsz], r8
0x18032e90a  mov     [rbp+57h+var_70], rdx
0x18032e90e  mov     rsi, rcx
0x18032e911  lea     r8, a1NullNamedest; "<%1 NULL:NameDest>"
0x18032e918  mov     [rbp+57h+var_78], r8
0x18032e91c  lea     r15, a2NullNameitem; "<%2 NULL:NameItem>"
0x18032e923  lea     rax, a3NullOptext; "<%3 NULL:OpText>"
0x18032e92a  mov     [rbp+57h+var_80], rax
0x18032e92e  lea     rax, a5NullError; "<%5 NULL:Error>"
0x18032e935  mov     [rbp+57h+var_88], rax
0x18032e939  lea     r12, a6NullCreationd; "<%6 NULL:CreationDateItem>"
0x18032e940  lea     r13, a7NullStoragepr_0; "<%7 NULL:StorageProviderNameDest>"
0x18032e947  mov     [rbp+57h+var_40], 0
0x18032e94f  mov     [rbp+57h+pv], 0
0x18032e957  lea     r14, [rcx+50h]
0x18032e95b  xor     edx, edx
0x18032e95d  mov     rcx, r14
0x18032e960  call    ??9?$CComPtrBase@UIShellFolder@@@ATL@@QEBA_NPEAUIShellFolder@@@Z; ATL::CComPtrBase<IShellFolder>::operator!=(IShellFolder *)
0x18032e965  test    al, al
0x18032e967  jz      short loc_18032E9DE
0x18032e969  mov     rdi, [r14]
0x18032e96c  mov     rax, [rdi]
0x18032e96f  mov     rbx, [rax+28h]
0x18032e973  xor     ecx, ecx; pv
0x18032e975  call    cs:__imp_CoTaskMemFree
0x18032e97c  nop     dword ptr [rax+rax+00h]
0x18032e981  lea     r8, [rbp+57h+var_40]
0x18032e985  mov     edx, 80031001h
0x18032e98a  mov     rcx, rdi
0x18032e98d  mov     rax, rbx
0x18032e990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032e995  mov     edi, eax
0x18032e997  test    eax, eax
0x18032e999  js      loc_18032EB95
0x18032e99f  mov     rax, [rbp+57h+var_40]
0x18032e9a3  mov     [rbp+57h+var_78], rax
0x18032e9a7  test    byte ptr [rsi+30h], 80h
0x18032e9ab  jz      short loc_18032E9DE
0x18032e9ad  mov     rcx, [rbp+57h+pv]; pv
0x18032e9b1  call    cs:__imp_CoTaskMemFree
0x18032e9b8  nop     dword ptr [rax+rax+00h]
0x18032e9bd  lea     rdx, [rbp+57h+pv]
0x18032e9c1  mov     rcx, [r14]
0x18032e9c4  call    cs:__imp_FECommon_GetStorageProviderDisplayName
0x18032e9cb  nop     dword ptr [rax+rax+00h]
0x18032e9d0  mov     edi, eax
0x18032e9d2  test    eax, eax
0x18032e9d4  js      loc_18032EB95
0x18032e9da  mov     r13, [rbp+57h+pv]
0x18032e9de  mov     [rbp+57h+var_48], 0
0x18032e9e6  lea     rcx, [rsi+48h]
0x18032e9ea  xor     edx, edx
0x18032e9ec  call    ??9?$CComPtrBase@UIShellFolder@@@ATL@@QEBA_NPEAUIShellFolder@@@Z; ATL::CComPtrBase<IShellFolder>::operator!=(IShellFolder *)
0x18032e9f1  test    al, al
0x18032e9f3  jz      short loc_18032EA2F
0x18032e9f5  mov     rdi, [rcx]
0x18032e9f8  mov     rax, [rdi]
0x18032e9fb  mov     rbx, [rax+28h]
0x18032e9ff  xor     ecx, ecx; pv
0x18032ea01  call    cs:__imp_CoTaskMemFree
0x18032ea08  nop     dword ptr [rax+rax+00h]
0x18032ea0d  lea     r8, [rbp+57h+var_48]
0x18032ea11  mov     edx, 80031001h
0x18032ea16  mov     rcx, rdi
0x18032ea19  mov     rax, rbx
0x18032ea1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032ea21  mov     edi, eax
0x18032ea23  test    eax, eax
0x18032ea25  js      loc_18032EB84
0x18032ea2b  mov     r15, [rbp+57h+var_48]
0x18032ea2f  test    byte ptr [rsi+30h], 4
0x18032ea33  jz      short loc_18032EA3D
0x18032ea35  mov     rax, [rsi+40h]
0x18032ea39  mov     [rbp+57h+var_80], rax
0x18032ea3d  mov     [rbp+57h+var_50], 0
0x18032ea45  test    byte ptr [rsi+30h], 8
0x18032ea49  jz      short loc_18032EA75
0x18032ea4b  xor     ecx, ecx; pv
0x18032ea4d  call    cs:__imp_CoTaskMemFree
0x18032ea54  nop     dword ptr [rax+rax+00h]
0x18032ea59  lea     rdx, [rbp+57h+var_50]; unsigned __int16 **
0x18032ea5d  mov     rcx, rsi; this
0x18032ea60  call    ?_GetOwnerInformation@CConfirmationInterrupt@@AEAAJPEAPEAG@Z; CConfirmationInterrupt::_GetOwnerInformation(ushort * *)
0x18032ea65  mov     edi, eax
0x18032ea67  test    eax, eax
0x18032ea69  js      loc_18032EB73
0x18032ea6f  mov     r14, [rbp+57h+var_50]
0x18032ea73  jmp     short loc_18032EA7C
0x18032ea75  lea     r14, a4NullOwner; "<%4 NULL:Owner>"
0x18032ea7c  xor     ebx, ebx
0x18032ea7e  mov     [rbp+57h+var_90], rbx
0x18032ea82  test    byte ptr [rsi+30h], 10h
0x18032ea86  jz      short loc_18032EAB4
0x18032ea88  xor     ecx, ecx; pv
0x18032ea8a  call    cs:__imp_CoTaskMemFree
0x18032ea91  nop     dword ptr [rax+rax+00h]
0x18032ea96  lea     rdx, [rbp+57h+var_90]; unsigned __int16 **
0x18032ea9a  mov     rcx, rsi; this
0x18032ea9d  call    ?_GetErrorInformation@CConfirmationInterrupt@@AEAAJPEAPEAG@Z; CConfirmationInterrupt::_GetErrorInformation(ushort * *)
0x18032eaa2  mov     edi, eax
0x18032eaa4  mov     rbx, [rbp+57h+var_90]
0x18032eaa8  test    eax, eax
0x18032eaaa  js      loc_18032EB63
0x18032eab0  mov     [rbp+57h+var_88], rbx
0x18032eab4  mov     [rbp+57h+var_58], 0
0x18032eabc  test    byte ptr [rsi+30h], 40h
0x18032eac0  jz      short loc_18032EAE6
0x18032eac2  xor     ecx, ecx; pv
0x18032eac4  call    cs:__imp_CoTaskMemFree
0x18032eacb  nop     dword ptr [rax+rax+00h]
0x18032ead0  lea     rdx, [rbp+57h+var_58]; unsigned __int16 **
0x18032ead4  mov     rcx, rsi; this
0x18032ead7  call    ?_GetMergeFolderInfo@CConfirmationInterrupt@@AEAAJPEAPEAG@Z; CConfirmationInterrupt::_GetMergeFolderInfo(ushort * *)
0x18032eadc  mov     edi, eax
0x18032eade  test    eax, eax
0x18032eae0  js      short loc_18032EB52
0x18032eae2  mov     r12, [rbp+57h+var_58]
0x18032eae6  mov     [rsp+0E0h+var_A0], r13
0x18032eaeb  mov     [rsp+0E0h+var_A8], r12
0x18032eaf0  mov     rax, [rbp+57h+var_88]
0x18032eaf4  mov     [rsp+0E0h+var_B0], rax
0x18032eaf9  mov     [rsp+0E0h+var_B8], r14
0x18032eafe  mov     rax, [rbp+57h+var_80]
0x18032eb02  mov     [rsp+0E0h+var_C0], rax
0x18032eb07  mov     r9, r15
0x18032eb0a  mov     r8, [rbp+57h+var_78]
0x18032eb0e  mov     rdx, [rbp+57h+var_70]
0x18032eb12  mov     rcx, cs:g_hinst
0x18032eb19  call    ShellConstructMessageStringW
0x18032eb1e  mov     rsi, rax
0x18032eb21  test    rax, rax
0x18032eb24  jnz     short loc_18032EB2D
0x18032eb26  mov     edi, 8007000Eh
0x18032eb2b  jmp     short loc_18032EB52
0x18032eb2d  mov     rdx, [rbp+57h+ppwsz]; ppwsz
0x18032eb31  mov     rcx, rsi; psz
0x18032eb34  call    cs:__imp_SHStrDupW
0x18032eb3b  nop     dword ptr [rax+rax+00h]
0x18032eb40  mov     edi, eax
0x18032eb42  mov     rcx, rsi; hMem
0x18032eb45  call    cs:__imp_LocalFree
0x18032eb4c  nop     dword ptr [rax+rax+00h]
0x18032eb51  nop
0x18032eb52  mov     rcx, [rbp+57h+var_58]; pv
0x18032eb56  call    cs:__imp_CoTaskMemFree
0x18032eb5d  nop     dword ptr [rax+rax+00h]
0x18032eb62  nop
0x18032eb63  mov     rcx, rbx; pv
0x18032eb66  call    cs:__imp_CoTaskMemFree
0x18032eb6d  nop     dword ptr [rax+rax+00h]
0x18032eb72  nop
0x18032eb73  mov     rcx, [rbp+57h+var_50]; pv
0x18032eb77  call    cs:__imp_CoTaskMemFree
0x18032eb7e  nop     dword ptr [rax+rax+00h]
0x18032eb83  nop
0x18032eb84  mov     rcx, [rbp+57h+var_48]; pv
0x18032eb88  call    cs:__imp_CoTaskMemFree
0x18032eb8f  nop     dword ptr [rax+rax+00h]
0x18032eb94  nop
0x18032eb95  mov     rcx, [rbp+57h+pv]; pv
0x18032eb99  call    cs:__imp_CoTaskMemFree
0x18032eba0  nop     dword ptr [rax+rax+00h]
0x18032eba5  nop
0x18032eba6  mov     rcx, [rbp+57h+var_40]; pv
0x18032ebaa  call    cs:__imp_CoTaskMemFree
0x18032ebb1  nop     dword ptr [rax+rax+00h]
0x18032ebb6  mov     eax, edi
0x18032ebb8  mov     rcx, [rbp+57h+var_38]
0x18032ebbc  xor     rcx, rsp; StackCookie
0x18032ebbf  call    __security_check_cookie
0x18032ebc4  mov     rbx, [rsp+0E0h+arg_18]
0x18032ebcc  add     rsp, 0B0h
0x18032ebd3  pop     r15
0x18032ebd5  pop     r14
0x18032ebd7  pop     r13
0x18032ebd9  pop     r12
0x18032ebdb  pop     rdi
0x18032ebdc  pop     rsi
0x18032ebdd  pop     rbp
0x18032ebde  retn
```
