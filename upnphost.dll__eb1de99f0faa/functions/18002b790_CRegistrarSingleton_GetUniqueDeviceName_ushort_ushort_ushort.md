# CRegistrarSingleton::GetUniqueDeviceName(ushort *,ushort *,ushort * *)

- ea: `0x18002b790`
- end: `0x18002b955`
- name: `?GetUniqueDeviceName@CRegistrarSingleton@@UEAAJPEAG0PEAPEAG@Z`
- size: `453`
- prototype: `__int64 __fastcall(CRegistrarSingleton *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180013180`
- `0x18001e478`
- `0x18002b790`
- `0x18002b95c`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002b80e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002b80e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b85e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b85e`

## pseudocode

```c
__int64 __fastcall CRegistrarSingleton::GetUniqueDeviceName(
        CRegistrarSingleton *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  struct IUnknown *v8; // rcx
  int IsAllowedCOMCallLocality; // ebx
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 result; // rax
  STRSAFE_PCNZWCH v13; // rcx
  LPVOID pv; // [rsp+30h] [rbp-58h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-50h] BYREF

  v8 = (struct IUnknown *)WPP_GLOBAL_Control;
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
0x18002b790  push    rbx
0x18002b792  push    rbp
0x18002b793  push    rsi
0x18002b794  push    rdi
0x18002b795  push    r12
0x18002b797  push    r14
0x18002b799  sub     rsp, 58h
0x18002b79d  mov     rax, cs:__security_cookie
0x18002b7a4  xor     rax, rsp
0x18002b7a7  mov     [rsp+88h+var_40], rax
0x18002b7ac  mov     rbp, r9
0x18002b7af  mov     r14, r8
0x18002b7b2  mov     rsi, rdx
0x18002b7b5  mov     rdi, rcx
0x18002b7b8  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18002b7bf  lea     r12, WPP_GLOBAL_Control
0x18002b7c6  cmp     rcx, r12
0x18002b7c9  jnz     loc_18002B8A2
0x18002b7cf  cmp     dword ptr [rdi+98h], 0
0x18002b7d6  jz      loc_18002B8C6
0x18002b7dc  mov     ecx, 3
0x18002b7e1  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18002b7e6  mov     ebx, eax
0x18002b7e8  test    eax, eax
0x18002b7ea  js      short loc_18002B864
0x18002b7ec  test    rsi, rsi
0x18002b7ef  jz      loc_18002B919
0x18002b7f5  test    rbp, rbp
0x18002b7f8  jz      loc_18002B919
0x18002b7fe  xorps   xmm0, xmm0
0x18002b801  lea     rdx, [rsp+88h+pclsid]; pclsid
0x18002b806  mov     rcx, rsi; lpsz
0x18002b809  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x18002b80e  call    cs:__imp_CLSIDFromString
0x18002b814  mov     ebx, eax
0x18002b816  test    eax, eax
0x18002b818  jnz     loc_18002B8E3
0x18002b81e  mov     rcx, [rdi+68h]
0x18002b822  lea     r9, [rsp+88h+pv]
0x18002b827  mov     [rsp+88h+pv], 0
0x18002b830  lea     rdx, [rsp+88h+pclsid]
0x18002b835  mov     r8, r14
0x18002b838  mov     rax, [rcx]
0x18002b83b  mov     rax, [rax+48h]
0x18002b83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b844  mov     ebx, eax
0x18002b846  test    eax, eax
0x18002b848  js      short loc_18002B864
0x18002b84a  mov     rcx, [rsp+88h+pv]; unsigned __int16 *
0x18002b84f  mov     rdx, rbp; unsigned __int16 **
0x18002b852  call    ?HrSysAllocString@@YAJPEBGPEAPEAG@Z; HrSysAllocString(ushort const *,ushort * *)
0x18002b857  mov     rcx, [rsp+88h+pv]; pv
0x18002b85c  mov     ebx, eax
0x18002b85e  call    cs:__imp_CoTaskMemFree
0x18002b864  test    ebx, ebx
0x18002b866  jnz     loc_18002B91E
0x18002b86c  mov     eax, ebx
0x18002b86e  mov     rcx, [rsp+88h+var_40]
0x18002b873  xor     rcx, rsp; StackCookie
0x18002b876  call    __security_check_cookie
0x18002b87b  add     rsp, 58h
0x18002b87f  pop     r14
0x18002b881  pop     r12
0x18002b883  pop     rdi
0x18002b884  pop     rsi
0x18002b885  pop     rbp
0x18002b886  pop     rbx
0x18002b887  retn
0x18002b888  test    ebx, ebx
0x18002b88a  jns     short loc_18002B81E
0x18002b88c  cmp     ebx, 800401F3h
0x18002b892  jnz     loc_18002B925
0x18002b898  mov     ebx, 80070057h
0x18002b89d  jmp     loc_18002B925
0x18002b8a2  test    byte ptr [rcx+1Ch], 40h
0x18002b8a6  jz      loc_18002B7CF
0x18002b8ac  mov     rcx, [rcx+10h]
0x18002b8b0  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18002b8b7  mov     edx, 33h ; '3'
0x18002b8bc  call    WPP_SF_
0x18002b8c1  jmp     loc_18002B7CF
0x18002b8c6  call    ?CompleteInitialization@CServiceModule@@QEAAJXZ; CServiceModule::CompleteInitialization(void)
0x18002b8cb  test    eax, eax
0x18002b8cd  js      short loc_18002B86E
0x18002b8cf  cmp     dword ptr [rdi+98h], 0
0x18002b8d6  jnz     loc_18002B7DC
0x18002b8dc  mov     eax, 80004005h
0x18002b8e1  jmp     short loc_18002B86E
0x18002b8e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8ea  cmp     rcx, r12
0x18002b8ed  jz      short loc_18002B888
0x18002b8ef  test    byte ptr [rcx+1Ch], 1
0x18002b8f3  jz      short loc_18002B888
0x18002b8f5  mov     rcx, [rcx+10h]
0x18002b8f9  lea     r8, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids
0x18002b900  mov     edx, 12h
0x18002b905  mov     r9d, ebx
0x18002b908  call    WPP_SF_d
0x18002b90d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b914  jmp     loc_18002B888
0x18002b919  mov     ebx, 80004003h
0x18002b91e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b925  cmp     rcx, r12
0x18002b928  jz      loc_18002B86C
0x18002b92e  test    byte ptr [rcx+1Ch], 1
0x18002b932  jz      loc_18002B86C
0x18002b938  mov     rcx, [rcx+10h]
0x18002b93c  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18002b943  mov     edx, 34h ; '4'
0x18002b948  mov     r9d, ebx
0x18002b94b  call    WPP_SF_d
0x18002b950  jmp     loc_18002B86C
```
