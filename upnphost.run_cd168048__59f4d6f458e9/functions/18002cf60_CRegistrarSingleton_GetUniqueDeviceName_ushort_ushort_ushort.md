# CRegistrarSingleton::GetUniqueDeviceName(ushort *,ushort *,ushort * *)

- ea: `0x18002cf60`
- end: `0x18002d136`
- name: `?GetUniqueDeviceName@CRegistrarSingleton@@UEAAJPEAG0PEAPEAG@Z`
- size: `470`
- prototype: `int(CRegistrarSingleton *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x1800134e4`
- `0x18002cf60`
- `0x18002d13c`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002cfe2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002cfe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d038`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d038`

## pseudocode

```c
__int64 __fastcall CRegistrarSingleton::GetUniqueDeviceName(
        CRegistrarSingleton *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  CServiceModule *v8; // rcx
  int IsAllowedCOMCallLocality; // ebx
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 result; // rax
  STRSAFE_PCNZWCH v13; // rcx
  LPVOID pv; // [rsp+30h] [rbp-58h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-50h] BYREF

  v8 = (CServiceModule *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids);
  if ( *((_DWORD *)this + 38) )
    goto LABEL_3;
  result = CServiceModule::CompleteInitialization(v8);
  if ( (int)result >= 0 )
  {
    if ( !*((_DWORD *)this + 38) )
      return 2147500037LL;
LABEL_3:
    IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(3);
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      if ( !a2 || !a4 )
      {
        IsAllowedCOMCallLocality = -2147467261;
LABEL_24:
        v13 = WPP_GLOBAL_Control;
LABEL_25:
        if ( v13 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v13[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)v13 + 2),
            52,
            WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
            (unsigned int)IsAllowedCOMCallLocality);
        return (unsigned int)IsAllowedCOMCallLocality;
      }
      pclsid = 0;
      v10 = CLSIDFromString(a2, &pclsid);
      IsAllowedCOMCallLocality = v10;
      if ( v10 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids, v10);
          v13 = WPP_GLOBAL_Control;
        }
        if ( IsAllowedCOMCallLocality < 0 )
        {
          if ( IsAllowedCOMCallLocality == -2147221005 )
            IsAllowedCOMCallLocality = -2147024809;
          goto LABEL_25;
        }
      }
      v11 = *((_QWORD *)this + 13);
      pv = 0;
      IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(__int64, GUID *, unsigned __int16 *, LPVOID *))(*(_QWORD *)v11 + 72LL))(
                                   v11,
                                   &pclsid,
                                   a3,
                                   &pv);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        IsAllowedCOMCallLocality = HrSysAllocString((const unsigned __int16 *)pv, a4);
        CoTaskMemFree(pv);
      }
    }
    if ( !IsAllowedCOMCallLocality )
      return (unsigned int)IsAllowedCOMCallLocality;
    goto LABEL_24;
  }
  return result;
}

```

## disassembly

```asm
0x18002cf60  push    rbx
0x18002cf62  push    rbp
0x18002cf63  push    rsi
0x18002cf64  push    rdi
0x18002cf65  push    r12
0x18002cf67  push    r14
0x18002cf69  sub     rsp, 58h
0x18002cf6d  mov     rax, cs:__security_cookie
0x18002cf74  xor     rax, rsp
0x18002cf77  mov     [rsp+88h+var_40], rax
0x18002cf7c  mov     rbp, r9
0x18002cf7f  mov     r14, r8
0x18002cf82  mov     rsi, rdx
0x18002cf85  mov     rdi, rcx
0x18002cf88  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18002cf8f  lea     r12, WPP_GLOBAL_Control
0x18002cf96  cmp     rcx, r12
0x18002cf99  jnz     loc_18002D083
0x18002cf9f  cmp     dword ptr [rdi+98h], 0
0x18002cfa6  jz      loc_18002D0A7
0x18002cfac  mov     ecx, 3
0x18002cfb1  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18002cfb6  mov     ebx, eax
0x18002cfb8  test    eax, eax
0x18002cfba  js      loc_18002D044
0x18002cfc0  test    rsi, rsi
0x18002cfc3  jz      loc_18002D0FA
0x18002cfc9  test    rbp, rbp
0x18002cfcc  jz      loc_18002D0FA
0x18002cfd2  xorps   xmm0, xmm0
0x18002cfd5  lea     rdx, [rsp+88h+pclsid]; pclsid
0x18002cfda  mov     rcx, rsi; lpsz
0x18002cfdd  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x18002cfe2  call    cs:__imp_CLSIDFromString
0x18002cfe9  nop     dword ptr [rax+rax+00h]
0x18002cfee  mov     ebx, eax
0x18002cff0  test    eax, eax
0x18002cff2  jnz     loc_18002D0C4
0x18002cff8  mov     rcx, [rdi+68h]
0x18002cffc  lea     r9, [rsp+88h+pv]
0x18002d001  mov     [rsp+88h+pv], 0
0x18002d00a  lea     rdx, [rsp+88h+pclsid]
0x18002d00f  mov     r8, r14
0x18002d012  mov     rax, [rcx]
0x18002d015  mov     rax, [rax+48h]
0x18002d019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d01e  mov     ebx, eax
0x18002d020  test    eax, eax
0x18002d022  js      short loc_18002D044
0x18002d024  mov     rcx, [rsp+88h+pv]; unsigned __int16 *
0x18002d029  mov     rdx, rbp; unsigned __int16 **
0x18002d02c  call    ?HrSysAllocString@@YAJPEBGPEAPEAG@Z; HrSysAllocString(ushort const *,ushort * *)
0x18002d031  mov     rcx, [rsp+88h+pv]; pv
0x18002d036  mov     ebx, eax
0x18002d038  call    cs:__imp_CoTaskMemFree
0x18002d03f  nop     dword ptr [rax+rax+00h]
0x18002d044  test    ebx, ebx
0x18002d046  jnz     loc_18002D0FF
0x18002d04c  mov     eax, ebx
0x18002d04e  mov     rcx, [rsp+88h+var_40]
0x18002d053  xor     rcx, rsp; StackCookie
0x18002d056  call    __security_check_cookie
0x18002d05b  add     rsp, 58h
0x18002d05f  pop     r14
0x18002d061  pop     r12
0x18002d063  pop     rdi
0x18002d064  pop     rsi
0x18002d065  pop     rbp
0x18002d066  pop     rbx
0x18002d067  retn
0x18002d069  test    ebx, ebx
0x18002d06b  jns     short loc_18002CFF8
0x18002d06d  cmp     ebx, 800401F3h
0x18002d073  jnz     loc_18002D106
0x18002d079  mov     ebx, 80070057h
0x18002d07e  jmp     loc_18002D106
0x18002d083  test    byte ptr [rcx+1Ch], 40h
0x18002d087  jz      loc_18002CF9F
0x18002d08d  mov     rcx, [rcx+10h]
0x18002d091  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18002d098  mov     edx, 33h ; '3'
0x18002d09d  call    WPP_SF_
0x18002d0a2  jmp     loc_18002CF9F
0x18002d0a7  call    ?CompleteInitialization@CServiceModule@@QEAAJXZ; CServiceModule::CompleteInitialization(void)
0x18002d0ac  test    eax, eax
0x18002d0ae  js      short loc_18002D04E
0x18002d0b0  cmp     dword ptr [rdi+98h], 0
0x18002d0b7  jnz     loc_18002CFAC
0x18002d0bd  mov     eax, 80004005h
0x18002d0c2  jmp     short loc_18002D04E
0x18002d0c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0cb  cmp     rcx, r12
0x18002d0ce  jz      short loc_18002D069
0x18002d0d0  test    byte ptr [rcx+1Ch], 1
0x18002d0d4  jz      short loc_18002D069
0x18002d0d6  mov     rcx, [rcx+10h]
0x18002d0da  lea     r8, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids
0x18002d0e1  mov     edx, 12h
0x18002d0e6  mov     r9d, ebx
0x18002d0e9  call    WPP_SF_d
0x18002d0ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0f5  jmp     loc_18002D069
0x18002d0fa  mov     ebx, 80004003h
0x18002d0ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d106  cmp     rcx, r12
0x18002d109  jz      loc_18002D04C
0x18002d10f  test    byte ptr [rcx+1Ch], 1
0x18002d113  jz      loc_18002D04C
0x18002d119  mov     rcx, [rcx+10h]
0x18002d11d  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18002d124  mov     edx, 34h ; '4'
0x18002d129  mov     r9d, ebx
0x18002d12c  call    WPP_SF_d
0x18002d131  jmp     loc_18002D04C
```
