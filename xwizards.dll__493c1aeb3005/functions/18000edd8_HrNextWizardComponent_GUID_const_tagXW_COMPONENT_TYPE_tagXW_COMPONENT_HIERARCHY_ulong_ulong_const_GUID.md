# HrNextWizardComponent(_GUID const *,tagXW_COMPONENT_TYPE,tagXW_COMPONENT_HIERARCHY,ulong,ulong * const,_GUID *)

- ea: `0x18000edd8`
- end: `0x18000f01c`
- name: `?HrNextWizardComponent@@YAJPEBU_GUID@@W4tagXW_COMPONENT_TYPE@@W4tagXW_COMPONENT_HIERARCHY@@KQEAKPEAU1@@Z`
- size: `580`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d43c`
- `0x18000f45c`
- `0x18000f5cc`

## callees

- `0x1800085a8`
- `0x180008634`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000e950`
- `0x18000edd8`
- `0x180032a02`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ef64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ef64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ef2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ef2f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000eec6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000eec6`

## string_xrefs

- `0x18000ee66`: `Components`

## pseudocode

```c
__int64 __fastcall HrNextWizardComponent(const GUID *a1, int a2, int a3, int a4, _DWORD *a5, GUID *a6)
{
  int v9; // r14d
  unsigned int v10; // r11d
  unsigned int v11; // ebx
  __int64 v12; // rax
  const unsigned __int16 *v13; // r8
  LSTATUS v14; // eax
  PVOID *v15; // rcx
  int v16; // edx
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[122]; // [rsp+42h] [rbp-BEh] BYREF
  OLECHAR sz[58]; // [rsp+BCh] [rbp-44h] BYREF

  memset_0(v21, 0, 0xE6u);
  hKey = 0;
  if ( a6 )
    *a6 = 0;
  v9 = 0;
  SubKey = 0;
  StringCchCopyW(&SubKey, 0x74u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(&SubKey, v10, L"Components");
  v11 = 1;
  if ( a1 )
  {
    v12 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v12 = *(_QWORD *)a1->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( v12 )
    {
      StringCchCatW(&SubKey, 0x74u, L"\\");
      StringFromGUID2(a1, sz, 39);
      StringCchCatW(&SubKey, 0x74u, L"\\");
      v13 = L"Parents";
      if ( a3 != 2 )
        v13 = L"Children";
      StringCchCatW(&SubKey, 0x74u, v13);
      if ( a3 == 1 )
        v9 = 1;
    }
  }
  v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 0x20019u, &hKey);
  if ( !v14 )
  {
    v11 = HrEnumSubkeyComponent(hKey, a5, v9, a2, a4, a6);
    RegCloseKey(hKey);
LABEL_24:
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  if ( v14 == 2 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v11;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_25;
    v16 = 17;
LABEL_23:
    WPP_SF_SD(
      (unsigned int)v15[2],
      v16,
      (unsigned int)WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids,
      (unsigned int)&SubKey,
      v11);
    goto LABEL_24;
  }
  if ( v14 > 0 )
    v11 = (unsigned __int16)v14 | 0x80070000;
  else
    v11 = v14;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_25:
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x10) != 0 )
        WPP_SF_d(v15[2], 19, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids, v11);
      return v11;
    }
    v16 = 18;
    goto LABEL_23;
  }
  return v11;
}

```

## disassembly

```asm
0x18000edd8  mov     [rsp-8+arg_10], rbx
0x18000eddd  push    rbp
0x18000edde  push    rsi
0x18000eddf  push    rdi
0x18000ede0  push    r12
0x18000ede2  push    r13
0x18000ede4  push    r14
0x18000ede6  push    r15
0x18000ede8  lea     rbp, [rsp-40h]
0x18000eded  sub     rsp, 140h
0x18000edf4  mov     rax, cs:__security_cookie
0x18000edfb  xor     rax, rsp
0x18000edfe  mov     [rbp+70h+var_40], rax
0x18000ee02  mov     r13, [rbp+70h+arg_20]
0x18000ee09  mov     r15d, edx
0x18000ee0c  mov     rsi, [rbp+70h+arg_28]
0x18000ee13  mov     rdi, rcx
0x18000ee16  mov     [rsp+170h+var_140], r8d
0x18000ee1b  lea     rcx, [rsp+170h+var_12E]; void *
0x18000ee20  xor     edx, edx; Val
0x18000ee22  mov     r8d, 0E6h; Size
0x18000ee28  mov     r12d, r9d
0x18000ee2b  call    memset_0
0x18000ee30  mov     [rsp+170h+hKey], 0
0x18000ee39  test    rsi, rsi
0x18000ee3c  jz      short loc_18000EE44
0x18000ee3e  xorps   xmm0, xmm0
0x18000ee41  movups  xmmword ptr [rsi], xmm0
0x18000ee44  xor     eax, eax
0x18000ee46  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000ee4d  xor     r14d, r14d
0x18000ee50  mov     [rsp+170h+SubKey], ax
0x18000ee55  lea     rcx, [rsp+170h+SubKey]; unsigned __int16 *
0x18000ee5a  lea     r11d, [r14+74h]
0x18000ee5e  mov     edx, r11d; unsigned __int64
0x18000ee61  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ee66  lea     r8, aComponents_0; "Components"
0x18000ee6d  mov     edx, r11d; unsigned __int64
0x18000ee70  lea     rcx, [rsp+170h+SubKey]; unsigned __int16 *
0x18000ee75  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ee7a  lea     ebx, [r14+1]
0x18000ee7e  test    rdi, rdi
0x18000ee81  jz      loc_18000EF10
0x18000ee87  mov     rax, [rdi]
0x18000ee8a  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18000ee91  jnz     short loc_18000EE9E
0x18000ee93  mov     rax, [rdi+8]
0x18000ee97  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18000ee9e  test    rax, rax
0x18000eea1  jz      short loc_18000EF10
0x18000eea3  lea     r8, asc_18003C7AC; "\\"
0x18000eeaa  mov     edx, 74h ; 't'; unsigned __int64
0x18000eeaf  lea     rcx, [rsp+170h+SubKey]; unsigned __int16 *
0x18000eeb4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000eeb9  mov     r8d, 27h ; '''; cchMax
0x18000eebf  lea     rdx, [rbp+70h+sz]; lpsz
0x18000eec3  mov     rcx, rdi; rguid
0x18000eec6  call    cs:__imp_StringFromGUID2
0x18000eecc  lea     r8, asc_18003C7AC; "\\"
0x18000eed3  mov     edx, 74h ; 't'; unsigned __int64
0x18000eed8  lea     rcx, [rsp+170h+SubKey]; unsigned __int16 *
0x18000eedd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000eee2  cmp     [rsp+170h+var_140], 2
0x18000eee7  lea     rax, aChildren_0; "Children"
0x18000eeee  lea     r8, aParents_0; "Parents"
0x18000eef5  mov     edx, 74h ; 't'; unsigned __int64
0x18000eefa  cmovnz  r8, rax; unsigned __int16 *
0x18000eefe  lea     rcx, [rsp+170h+SubKey]; unsigned __int16 *
0x18000ef03  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ef08  cmp     [rsp+170h+var_140], ebx
0x18000ef0c  cmovz   r14d, ebx
0x18000ef10  lea     rax, [rsp+170h+hKey]
0x18000ef15  mov     r9d, 20019h; samDesired
0x18000ef1b  xor     r8d, r8d; ulOptions
0x18000ef1e  mov     [rsp+170h+phkResult], rax; phkResult
0x18000ef23  lea     rdx, [rsp+170h+SubKey]; lpSubKey
0x18000ef28  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ef2f  call    cs:__imp_RegOpenKeyExW
0x18000ef35  lea     rdi, WPP_GLOBAL_Control
0x18000ef3c  test    eax, eax
0x18000ef3e  jnz     short loc_18000EF6C
0x18000ef40  mov     rcx, [rsp+170h+hKey]
0x18000ef45  mov     r9d, r15d
0x18000ef48  mov     [rsp+170h+var_148], rsi
0x18000ef4d  mov     r8d, r14d
0x18000ef50  mov     rdx, r13
0x18000ef53  mov     dword ptr [rsp+170h+phkResult], r12d
0x18000ef58  call    ?HrEnumSubkeyComponent@@YAJQEAUHKEY__@@QEAKHW4tagXW_COMPONENT_TYPE@@KPEAU_GUID@@@Z; HrEnumSubkeyComponent(HKEY__ * const,ulong * const,int,tagXW_COMPONENT_TYPE,ulong,_GUID *)
0x18000ef5d  mov     rcx, [rsp+170h+hKey]; hKey
0x18000ef62  mov     ebx, eax
0x18000ef64  call    cs:__imp_RegCloseKey
0x18000ef6a  jmp     short loc_18000EFC9
0x18000ef6c  cmp     eax, 2
0x18000ef6f  jnz     short loc_18000EF88
0x18000ef71  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef78  cmp     rcx, rdi
0x18000ef7b  jz      short loc_18000EFF3
0x18000ef7d  test    byte ptr [rcx+1Ch], 10h
0x18000ef81  jz      short loc_18000EFD0
0x18000ef83  lea     edx, [rax+0Fh]
0x18000ef86  jmp     short loc_18000EFB0
0x18000ef88  test    eax, eax
0x18000ef8a  jg      short loc_18000EF90
0x18000ef8c  mov     ebx, eax
0x18000ef8e  jmp     short loc_18000EF99
0x18000ef90  movzx   ebx, ax
0x18000ef93  or      ebx, 80070000h
0x18000ef99  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efa0  cmp     rcx, rdi
0x18000efa3  jz      short loc_18000EFF3
0x18000efa5  test    byte ptr [rcx+1Ch], 4
0x18000efa9  jz      short loc_18000EFD0
0x18000efab  mov     edx, 12h
0x18000efb0  mov     rcx, [rcx+10h]
0x18000efb4  lea     r9, [rsp+170h+SubKey]
0x18000efb9  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x18000efc0  mov     dword ptr [rsp+170h+phkResult], ebx
0x18000efc4  call    WPP_SF_SD
0x18000efc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efd0  cmp     rcx, rdi
0x18000efd3  jz      short loc_18000EFF3
0x18000efd5  test    byte ptr [rcx+1Ch], 10h
0x18000efd9  jz      short loc_18000EFF3
0x18000efdb  mov     rcx, [rcx+10h]
0x18000efdf  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x18000efe6  mov     edx, 13h
0x18000efeb  mov     r9d, ebx
0x18000efee  call    WPP_SF_d
0x18000eff3  mov     eax, ebx
0x18000eff5  mov     rcx, [rbp+70h+var_40]
0x18000eff9  xor     rcx, rsp; StackCookie
0x18000effc  call    __security_check_cookie
0x18000f001  mov     rbx, [rsp+170h+arg_10]
0x18000f009  add     rsp, 140h
0x18000f010  pop     r15
0x18000f012  pop     r14
0x18000f014  pop     r13
0x18000f016  pop     r12
0x18000f018  pop     rdi
0x18000f019  pop     rsi
0x18000f01a  pop     rbp
0x18000f01b  retn
```
