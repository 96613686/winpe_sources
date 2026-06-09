# RemoveBrowserCapsFromGac(void)

- ea: `0x18003cbac`
- end: `0x18003ccd2`
- name: `?RemoveBrowserCapsFromGac@@YAJXZ`
- size: `294`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x1800376f8`

## callees

- `0x180038250`
- `0x180038400`
- `0x18003abe4`
- `0x18003cbac`
- `0x18004d854`
- `0x180065b60`

## import_xrefs

- `ole32!CoUninitialize` at `0x18003ccc2`
- `ole32!CoUninitialize` at `0x18003ccc2`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ccb6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ccb6`
- `OLEAUT32!__imp_SysStringLen` at `0x18003cc3c`
- `OLEAUT32!__imp_SysStringLen` at `0x18003cc6e`
- `OLEAUT32!__imp_SysStringLen` at `0x18003cc3c`
- `OLEAUT32!__imp_SysStringLen` at `0x18003cc6e`

## string_xrefs

- `0x18003cbc7`: `Remove ASP.BrowserCapsFactory from GAC`
- `0x18003cc90`: `Remove ASP.BrowserCapsFactory from GAC`
- `0x18003cbbc`: `RemoveBrowserCapsFromGac`
- `0x18003cc0c`: `Calling RegiisUtility.RemoveBrowserCaps`
- `0x18003cc47`: `Calling RegiisUtility.RemoveBrowserCaps`
- `0x18003cc7c`: `Remove ASP.BrowserCapsFactory from GAC with exception: `

## pseudocode

```c
__int64 RemoveBrowserCapsFromGac(void)
{
  unsigned int v0; // ebx
  int v2; // [rsp+50h] [rbp+20h] BYREF
  BSTR pbstr; // [rsp+58h] [rbp+28h] BYREF
  struct _GUID v4; // [rsp+60h] [rbp+30h] BYREF

  *(_QWORD *)&v4.Data1 = 0;
  v2 = 0;
  pbstr = 0;
  CSetupLogging::Log(1, "RemoveBrowserCapsFromGac", 0, "Remove ASP.BrowserCapsFactory from GAC", 0);
  v0 = EnsureCoInitialized(&v2);
  if ( !v0 )
  {
    v0 = CreateRegiisUtilityManagedRuntime(&v4);
    if ( !v0 )
    {
      CSetupLogging::Log(1, "RemoveBrowserCapsFromGac", 0, "Calling RegiisUtility.RemoveBrowserCaps", 0);
      v0 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)&v4.Data1 + 48LL))(*(_QWORD *)&v4.Data1, &pbstr);
      if ( SysStringLen(pbstr) )
        v0 = -2147467259;
      CSetupLogging::Log(v0, "RemoveBrowserCapsFromGac", 0, "Calling RegiisUtility.RemoveBrowserCaps", 0);
      if ( !v0 )
        goto LABEL_8;
    }
  }
  if ( SysStringLen(pbstr) )
    CSetupLogging::Log(
      v0,
      "RemoveBrowserCapsFromGac",
      0,
      "Remove ASP.BrowserCapsFactory from GAC with exception: ",
      pbstr);
  else
LABEL_8:
    CSetupLogging::Log(v0, "RemoveBrowserCapsFromGac", 0, "Remove ASP.BrowserCapsFactory from GAC", 0);
  if ( *(_QWORD *)&v4.Data1 )
    DeleteRegiisUtilityManagedRuntime(*(struct xspmrt::_RegiisUtility **)&v4.Data1);
  SysFreeString(pbstr);
  if ( v2 )
    CoUninitialize();
  return v0;
}

```

## disassembly

```asm
0x18003cbac  push    rbp
0x18003cbae  push    rbx
0x18003cbaf  push    rsi
0x18003cbb0  mov     rbp, rsp
0x18003cbb3  sub     rsp, 30h
0x18003cbb7  and     qword ptr [rbp+arg_10.Data1], 0
0x18003cbbc  lea     rsi, aRemovebrowserc; "RemoveBrowserCapsFromGac"
0x18003cbc3  and     [rbp+arg_0], 0
0x18003cbc7  lea     r9, aRemoveAspBrows; "Remove ASP.BrowserCapsFactory from GAC"
0x18003cbce  and     [rbp+pbstr], 0
0x18003cbd3  xor     r8d, r8d; unsigned int
0x18003cbd6  and     [rsp+30h+var_10], 0
0x18003cbdc  mov     rdx, rsi; char *
0x18003cbdf  lea     ecx, [r8+1]; int
0x18003cbe3  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003cbe8  lea     rcx, [rbp+arg_0]; int *
0x18003cbec  call    ?EnsureCoInitialized@@YAJPEAH@Z; EnsureCoInitialized(int *)
0x18003cbf1  mov     ebx, eax
0x18003cbf3  test    eax, eax
0x18003cbf5  jnz     short loc_18003CC6A
0x18003cbf7  lea     rcx, [rbp+arg_10]; struct _GUID *
0x18003cbfb  call    ?CreateRegiisUtilityManagedRuntime@@YAJPEAPEAU_RegiisUtility@xspmrt@@@Z; CreateRegiisUtilityManagedRuntime(xspmrt::_RegiisUtility * *)
0x18003cc00  mov     ebx, eax
0x18003cc02  test    eax, eax
0x18003cc04  jnz     short loc_18003CC6A
0x18003cc06  and     [rsp+30h+var_10], 0
0x18003cc0c  lea     r9, aCallingRegiisu; "Calling RegiisUtility.RemoveBrowserCaps"
0x18003cc13  xor     r8d, r8d; unsigned int
0x18003cc16  lea     ecx, [rax+1]; int
0x18003cc19  mov     rdx, rsi; char *
0x18003cc1c  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003cc21  mov     rcx, qword ptr [rbp+arg_10.Data1]
0x18003cc25  lea     rdx, [rbp+pbstr]
0x18003cc29  mov     rax, [rcx]
0x18003cc2c  mov     rax, [rax+30h]
0x18003cc30  call    cs:__guard_dispatch_icall_fptr
0x18003cc36  mov     rcx, [rbp+pbstr]; pbstr
0x18003cc3a  mov     ebx, eax
0x18003cc3c  call    cs:__imp_SysStringLen
0x18003cc42  mov     ecx, 80004005h
0x18003cc47  lea     r9, aCallingRegiisu; "Calling RegiisUtility.RemoveBrowserCaps"
0x18003cc4e  test    eax, eax
0x18003cc50  mov     rdx, rsi; char *
0x18003cc53  cmovnz  ebx, ecx
0x18003cc56  and     [rsp+30h+var_10], 0
0x18003cc5c  mov     ecx, ebx; int
0x18003cc5e  xor     r8d, r8d; unsigned int
0x18003cc61  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003cc66  test    ebx, ebx
0x18003cc68  jz      short loc_18003CC8A
0x18003cc6a  mov     rcx, [rbp+pbstr]; pbstr
0x18003cc6e  call    cs:__imp_SysStringLen
0x18003cc74  test    eax, eax
0x18003cc76  jz      short loc_18003CC8A
0x18003cc78  mov     rax, [rbp+pbstr]
0x18003cc7c  lea     r9, aRemoveAspBrows_0; "Remove ASP.BrowserCapsFactory from GAC "...
0x18003cc83  mov     [rsp+30h+var_10], rax
0x18003cc88  jmp     short loc_18003CC97
0x18003cc8a  and     [rsp+30h+var_10], 0
0x18003cc90  lea     r9, aRemoveAspBrows; "Remove ASP.BrowserCapsFactory from GAC"
0x18003cc97  xor     r8d, r8d; unsigned int
0x18003cc9a  mov     rdx, rsi; char *
0x18003cc9d  mov     ecx, ebx; int
0x18003cc9f  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003cca4  mov     rcx, qword ptr [rbp+arg_10.Data1]; struct xspmrt::_RegiisUtility *
0x18003cca8  test    rcx, rcx
0x18003ccab  jz      short loc_18003CCB2
0x18003ccad  call    ?DeleteRegiisUtilityManagedRuntime@@YAJPEAU_RegiisUtility@xspmrt@@@Z; DeleteRegiisUtilityManagedRuntime(xspmrt::_RegiisUtility *)
0x18003ccb2  mov     rcx, [rbp+pbstr]; bstrString
0x18003ccb6  call    cs:__imp_SysFreeString
0x18003ccbc  cmp     [rbp+arg_0], 0
0x18003ccc0  jz      short loc_18003CCC8
0x18003ccc2  call    cs:__imp_CoUninitialize
0x18003ccc8  mov     eax, ebx
0x18003ccca  add     rsp, 30h
0x18003ccce  pop     rsi
0x18003cccf  pop     rbx
0x18003ccd0  pop     rbp
0x18003ccd1  retn
```
