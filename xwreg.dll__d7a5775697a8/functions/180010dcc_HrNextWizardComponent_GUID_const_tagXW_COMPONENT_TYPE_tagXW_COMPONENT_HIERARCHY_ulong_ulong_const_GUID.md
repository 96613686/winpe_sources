# HrNextWizardComponent(_GUID const *,tagXW_COMPONENT_TYPE,tagXW_COMPONENT_HIERARCHY,ulong,ulong * const,_GUID *)

- ea: `0x180010dcc`
- end: `0x180010fed`
- name: `?HrNextWizardComponent@@YAJPEBU_GUID@@W4tagXW_COMPONENT_TYPE@@W4tagXW_COMPONENT_HIERARCHY@@KQEAKPEAU1@@Z`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a768`

## callees

- `0x180007820`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x180010a54`
- `0x180010dcc`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010ead`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010ead`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010f10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010f10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f44`

## string_xrefs

- `0x180010e4f`: `Components`

## pseudocode

```c
__int64 __fastcall HrNextWizardComponent(const GUID *a1, __int64 a2, int a3, __int64 a4, _DWORD *a5, CLSID *a6)
{
  int v8; // r14d
  unsigned int v9; // ebx
  __int64 v10; // rax
  const unsigned __int16 *v11; // r8
  LSTATUS v12; // eax
  __int64 v13; // r9
  PVOID *v14; // rcx
  int v15; // edx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR SubKey; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[122]; // [rsp+42h] [rbp-BEh] BYREF
  OLECHAR sz[58]; // [rsp+BCh] [rbp-44h] BYREF

  memset_0(v20, 0, 0xE6u);
  hKey = 0;
  if ( a6 )
    *a6 = 0;
  v8 = 0;
  SubKey = 0;
  StringCchCopyW(&SubKey, 0x74u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(&SubKey, 0x74u, L"Components");
  v9 = 1;
  if ( a1 )
  {
    v10 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v10 = *(_QWORD *)a1->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( v10 )
    {
      StringCchCatW(&SubKey, 0x74u, L"\\");
      StringFromGUID2(a1, sz, 39);
      StringCchCatW(&SubKey, 0x74u, L"\\");
      v11 = L"Parents";
      if ( a3 != 2 )
        v11 = L"Children";
      StringCchCatW(&SubKey, 0x74u, v11);
      if ( a3 == 1 )
        v8 = 1;
    }
  }
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 0x20019u, &hKey);
  if ( !v12 )
  {
    v9 = HrEnumSubkeyComponent(hKey, a5, v8, v13, (__int64)phkResult, a6);
    RegCloseKey(hKey);
LABEL_24:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  if ( v12 == 2 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_25;
    v15 = 17;
LABEL_23:
    WPP_SF_SD(
      (unsigned int)v14[2],
      v15,
      (unsigned int)WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids,
      (unsigned int)&SubKey,
      v9);
    goto LABEL_24;
  }
  if ( v12 > 0 )
    v9 = (unsigned __int16)v12 | 0x80070000;
  else
    v9 = v12;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_25:
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x10) != 0 )
        WPP_SF_D(v14[2], 19, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids, v9);
      return v9;
    }
    v15 = 18;
    goto LABEL_23;
  }
  return v9;
}

```

## disassembly

```asm
0x180010dcc  push    rbp
0x180010dce  push    rbx
0x180010dcf  push    rsi
0x180010dd0  push    rdi
0x180010dd1  push    r12
0x180010dd3  push    r13
0x180010dd5  push    r14
0x180010dd7  push    r15
0x180010dd9  lea     rbp, [rsp-48h]
0x180010dde  sub     rsp, 148h
0x180010de5  mov     rax, cs:__security_cookie
0x180010dec  xor     rax, rsp
0x180010def  mov     [rbp+80h+var_50], rax
0x180010df3  mov     r15, [rbp+80h+arg_20]
0x180010dfa  mov     r12d, r8d
0x180010dfd  mov     rsi, [rbp+80h+arg_28]
0x180010e04  mov     rdi, rcx
0x180010e07  mov     r8d, 0E6h; Size
0x180010e0d  lea     rcx, [rsp+180h+var_13E]; void *
0x180010e12  xor     edx, edx; Val
0x180010e14  call    memset_0
0x180010e19  mov     [rsp+180h+hKey], 0
0x180010e22  test    rsi, rsi
0x180010e25  jz      short loc_180010E2D
0x180010e27  xorps   xmm0, xmm0
0x180010e2a  movups  xmmword ptr [rsi], xmm0
0x180010e2d  xor     eax, eax
0x180010e2f  lea     r8, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180010e36  xor     r14d, r14d
0x180010e39  mov     [rsp+180h+SubKey], ax
0x180010e3e  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x180010e43  lea     r13d, [r14+74h]
0x180010e47  mov     edx, r13d; unsigned __int64
0x180010e4a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010e4f  lea     r8, aComponents_1; "Components"
0x180010e56  mov     edx, r13d; unsigned __int64
0x180010e59  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x180010e5e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010e63  lea     ebx, [r14+1]
0x180010e67  test    rdi, rdi
0x180010e6a  jz      loc_180010EF1
0x180010e70  mov     rax, [rdi]
0x180010e73  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180010e7a  jnz     short loc_180010E87
0x180010e7c  mov     rax, [rdi+8]
0x180010e80  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180010e87  test    rax, rax
0x180010e8a  jz      short loc_180010EF1
0x180010e8c  lea     r8, asc_180018484; "\\"
0x180010e93  mov     rdx, r13; unsigned __int64
0x180010e96  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x180010e9b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010ea0  mov     r8d, 27h ; '''; cchMax
0x180010ea6  lea     rdx, [rbp+80h+sz]; lpsz
0x180010eaa  mov     rcx, rdi; rguid
0x180010ead  call    cs:__imp_StringFromGUID2
0x180010eb3  lea     r8, asc_180018484; "\\"
0x180010eba  mov     rdx, r13; unsigned __int64
0x180010ebd  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x180010ec2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010ec7  lea     rax, aChildren_1; "Children"
0x180010ece  cmp     r12d, 2
0x180010ed2  lea     r8, aParents_0; "Parents"
0x180010ed9  mov     rdx, r13; unsigned __int64
0x180010edc  cmovnz  r8, rax; unsigned __int16 *
0x180010ee0  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x180010ee5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010eea  cmp     r12d, ebx
0x180010eed  cmovz   r14d, ebx
0x180010ef1  lea     rax, [rsp+180h+hKey]
0x180010ef6  mov     r9d, 20019h; samDesired
0x180010efc  xor     r8d, r8d; ulOptions
0x180010eff  mov     [rsp+180h+phkResult], rax; phkResult
0x180010f04  lea     rdx, [rsp+180h+SubKey]; lpSubKey
0x180010f09  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010f10  call    cs:__imp_RegOpenKeyExW
0x180010f16  lea     rdi, WPP_GLOBAL_Control
0x180010f1d  lea     r12, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x180010f24  test    eax, eax
0x180010f26  jnz     short loc_180010F4C
0x180010f28  mov     rcx, [rsp+180h+hKey]
0x180010f2d  mov     r8d, r14d
0x180010f30  mov     rdx, r15
0x180010f33  mov     [rsp+180h+var_158], rsi
0x180010f38  call    ?HrEnumSubkeyComponent@@YAJQEAUHKEY__@@QEAKHW4tagXW_COMPONENT_TYPE@@KPEAU_GUID@@@Z; HrEnumSubkeyComponent(HKEY__ * const,ulong * const,int,tagXW_COMPONENT_TYPE,ulong,_GUID *)
0x180010f3d  mov     rcx, [rsp+180h+hKey]; hKey
0x180010f42  mov     ebx, eax
0x180010f44  call    cs:__imp_RegCloseKey
0x180010f4a  jmp     short loc_180010FA5
0x180010f4c  cmp     eax, 2
0x180010f4f  jnz     short loc_180010F68
0x180010f51  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f58  cmp     rcx, rdi
0x180010f5b  jz      short loc_180010FCB
0x180010f5d  test    byte ptr [rcx+1Ch], 10h
0x180010f61  jz      short loc_180010FAC
0x180010f63  lea     edx, [rax+0Fh]
0x180010f66  jmp     short loc_180010F90
0x180010f68  test    eax, eax
0x180010f6a  jg      short loc_180010F70
0x180010f6c  mov     ebx, eax
0x180010f6e  jmp     short loc_180010F79
0x180010f70  movzx   ebx, ax
0x180010f73  or      ebx, 80070000h
0x180010f79  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f80  cmp     rcx, rdi
0x180010f83  jz      short loc_180010FCB
0x180010f85  test    byte ptr [rcx+1Ch], 4
0x180010f89  jz      short loc_180010FAC
0x180010f8b  mov     edx, 12h
0x180010f90  mov     rcx, [rcx+10h]
0x180010f94  lea     r9, [rsp+180h+SubKey]
0x180010f99  mov     r8, r12
0x180010f9c  mov     dword ptr [rsp+180h+phkResult], ebx
0x180010fa0  call    WPP_SF_SD
0x180010fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fac  cmp     rcx, rdi
0x180010faf  jz      short loc_180010FCB
0x180010fb1  test    byte ptr [rcx+1Ch], 10h
0x180010fb5  jz      short loc_180010FCB
0x180010fb7  mov     rcx, [rcx+10h]
0x180010fbb  mov     edx, 13h
0x180010fc0  mov     r9d, ebx
0x180010fc3  mov     r8, r12
0x180010fc6  call    WPP_SF_D
0x180010fcb  mov     eax, ebx
0x180010fcd  mov     rcx, [rbp+80h+var_50]
0x180010fd1  xor     rcx, rsp; StackCookie
0x180010fd4  call    __security_check_cookie
0x180010fd9  add     rsp, 148h
0x180010fe0  pop     r15
0x180010fe2  pop     r14
0x180010fe4  pop     r13
0x180010fe6  pop     r12
0x180010fe8  pop     rdi
0x180010fe9  pop     rsi
0x180010fea  pop     rbx
0x180010feb  pop     rbp
0x180010fec  retn
```
