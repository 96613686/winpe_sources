# CSFPIntegrityCheckAndRepair::CheckIntegrity(__MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *,STORE_TYPE,ushort *,int,ushort *,ISFPRebootCallback *,ISFPProgressCallback *,int *,__MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *,ulong *)

- ea: `0x1800038e0`
- end: `0x180003a38`
- name: `?CheckIntegrity@CSFPIntegrityCheckAndRepair@@EEAAJPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0001@@W4STORE_TYPE@@PEAGH2PEAUISFPRebootCallback@@PEAUISFPProgressCallback@@PEAHPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0002@@PEAK@Z`
- size: `344`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, unsigned int, __int64, __int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180006e50`
- `0x180007424`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::CheckIntegrity(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        _DWORD *a11)
{
  __int64 result; // rax
  int v16; // ebx
  _DWORD v17[14]; // [rsp+60h] [rbp-38h] BYREF

  v17[0] = 0;
  if ( !vpfnGetSystemStore || !vpfnOpenExistingOfflineStore || !vpfnGetIdentityAuthority || !a11 )
    return 2147500035LL;
  if ( a3 > 3 )
    return 2147942487LL;
  *a11 = 1;
  if ( !a2 )
    goto LABEL_12;
  result = IsOnlineWindows(*(_QWORD *)(a2 + 8), v17);
  if ( (int)result < 0 )
    return result;
  if ( v17[0] )
    return 2147753984LL;
  result = WrpSetPrivilegesByName();
  if ( (int)result >= 0 )
  {
LABEL_12:
    v16 = a3 - 1;
    if ( v16 )
    {
      if ( v16 != 1 )
        return 2147942487LL;
      return (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64))(*(_QWORD *)a1 + 88LL))(
               a1,
               a4,
               a5,
               a9,
               a10);
    }
    else
    {
      return (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, __int64, __int64, __int64, __int64, __int64, _DWORD *))(*(_QWORD *)a1 + 96LL))(
               a1,
               a2,
               a4,
               a5,
               a6,
               a7,
               a8,
               a9,
               a10,
               a11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800038e0  push    rbx
0x1800038e2  push    rbp
0x1800038e3  push    rsi
0x1800038e4  push    rdi
0x1800038e5  push    r14
0x1800038e7  sub     rsp, 70h
0x1800038eb  cmp     cs:?vpfnGetSystemStore@@3P6AJKAEBU_GUID@@PEAPEAUIUnknown@@@ZEA, 0; long (*vpfnGetSystemStore)(ulong,_GUID const &,IUnknown * *)
0x1800038f3  mov     rbp, r9
0x1800038f6  mov     ebx, r8d
0x1800038f9  mov     [rsp+98h+var_38], 0
0x180003901  mov     rsi, rdx
0x180003904  mov     r14, rcx
0x180003907  jz      loc_180003A28
0x18000390d  cmp     cs:?vpfnOpenExistingOfflineStore@@3P6AJKPEBU_OFFLINE_STORE_CREATION_PARAMETERS@@AEBU_GUID@@PEAPEAUIUnknown@@PEAK@ZEA, 0; long (*vpfnOpenExistingOfflineStore)(ulong,_OFFLINE_STORE_CREATION_PARAMETERS const *,_GUID const &,IUnknown * *,ulong *)
0x180003915  jz      loc_180003A28
0x18000391b  cmp     cs:?vpfnGetIdentityAuthority@@3P6AJPEAPEAUIIdentityAuthority@@@ZEA, 0; long (*vpfnGetIdentityAuthority)(IIdentityAuthority * *)
0x180003923  jz      loc_180003A28
0x180003929  mov     rdi, [rsp+98h+arg_50]
0x180003931  test    rdi, rdi
0x180003934  jz      loc_180003A28
0x18000393a  cmp     ebx, 3
0x18000393d  jle     short loc_180003949
0x18000393f  mov     eax, 80070057h
0x180003944  jmp     loc_180003A2D
0x180003949  mov     dword ptr [rdi], 1
0x18000394f  test    rsi, rsi
0x180003952  jz      short loc_180003988
0x180003954  mov     rcx, [rsi+8]
0x180003958  lea     rdx, [rsp+98h+var_38]
0x18000395d  call    IsOnlineWindows
0x180003962  test    eax, eax
0x180003964  js      loc_180003A2D
0x18000396a  cmp     [rsp+98h+var_38], 0
0x18000396f  jz      short loc_18000397B
0x180003971  mov     eax, 80042000h
0x180003976  jmp     loc_180003A2D
0x18000397b  call    WrpSetPrivilegesByName
0x180003980  test    eax, eax
0x180003982  js      loc_180003A2D
0x180003988  sub     ebx, 1
0x18000398b  jz      short loc_1800039C3
0x18000398d  cmp     ebx, 1
0x180003990  jnz     short loc_18000393F
0x180003992  mov     rax, [r14]
0x180003995  mov     rdx, rbp
0x180003998  mov     rcx, [rsp+98h+arg_48]
0x1800039a0  mov     r9, [rsp+98h+arg_40]
0x1800039a8  mov     r8d, [rsp+98h+arg_20]
0x1800039b0  mov     rax, [rax+58h]
0x1800039b4  mov     [rsp+98h+var_78], rcx
0x1800039b9  mov     rcx, r14
0x1800039bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039c1  jmp     short loc_180003A2D
0x1800039c3  mov     rcx, [rsp+98h+arg_48]
0x1800039cb  mov     r8, rbp
0x1800039ce  mov     rax, [r14]
0x1800039d1  mov     rdx, rsi
0x1800039d4  mov     r9d, [rsp+98h+arg_20]
0x1800039dc  mov     [rsp+98h+var_50], rdi
0x1800039e1  mov     [rsp+98h+var_58], rcx
0x1800039e6  mov     rcx, [rsp+98h+arg_40]
0x1800039ee  mov     rax, [rax+60h]
0x1800039f2  mov     [rsp+98h+var_60], rcx
0x1800039f7  mov     rcx, [rsp+98h+arg_38]
0x1800039ff  mov     [rsp+98h+var_68], rcx
0x180003a04  mov     rcx, [rsp+98h+arg_30]
0x180003a0c  mov     [rsp+98h+var_70], rcx
0x180003a11  mov     rcx, [rsp+98h+arg_28]
0x180003a19  mov     [rsp+98h+var_78], rcx
0x180003a1e  mov     rcx, r14
0x180003a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a26  jmp     short loc_180003A2D
0x180003a28  mov     eax, 80004003h
0x180003a2d  add     rsp, 70h
0x180003a31  pop     r14
0x180003a33  pop     rdi
0x180003a34  pop     rsi
0x180003a35  pop     rbp
0x180003a36  pop     rbx
0x180003a37  retn
```
