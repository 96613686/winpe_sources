# CContentFolder::_AssocCreate(CONTENTITEM const *,_GUID const &,void * *)

- ea: `0x180002a80`
- end: `0x180002ce5`
- name: `?_AssocCreate@CContentFolder@@AEAAJPEFBUCONTENTITEM@@AEBU_GUID@@PEAPEAX@Z`
- size: `613`
- prototype: `int(CContentFolder *__hidden this, const struct CONTENTITEM *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001da0`

## callees

- `0x180002a80`
- `0x180004190`
- `0x18002ff5c`
- `0x180035590`
- `0x18003912c`
- `0x180039e80`
- `0x18006d7dc`
- `0x180078010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180002c0f`
- `KERNEL32!CompareStringOrdinal` at `0x180002c0f`
- `SHLWAPI!AssocCreate` at `0x180002af9`
- `SHLWAPI!AssocCreate` at `0x180002af9`
- `SHLWAPI!PathFindExtensionW` at `0x180002ba2`
- `SHLWAPI!PathFindExtensionW` at `0x180002ba2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentFolder::_AssocCreate(
        CContentFolder *this,
        const struct CONTENTITEM *a2,
        struct _GUID *a3,
        void **a4)
{
  int v7; // ebx
  HRESULT v8; // eax
  CContentFolder *v9; // rcx
  unsigned int v10; // r9d
  PVOID *v11; // rcx
  __int64 v12; // rdx
  const WCHAR *v13; // rax
  const WCHAR *ExtensionW; // rsi
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // r8
  unsigned int v17; // eax
  void *ppv; // [rsp+30h] [rbp-2E8h] BYREF
  CLSID clsid; // [rsp+40h] [rbp-2D8h] BYREF
  OLECHAR sz[64]; // [rsp+50h] [rbp-2C8h] BYREF
  unsigned __int16 v22[264]; // [rsp+D0h] [rbp-248h] BYREF

  ppv = 0;
  if ( !a4 )
  {
    v7 = -2147467261;
LABEL_23:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_24;
  }
  *a4 = 0;
  clsid = CLSID_QueryAssociations;
  v8 = AssocCreate(&clsid, &IID_IQueryAssociations, &ppv);
  v7 = v8;
  if ( v8 < 0 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_24;
    v12 = 179;
    goto LABEL_7;
  }
  if ( (*((_BYTE *)a2 + 10) & 2) != 0 )
  {
    v8 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
           ppv,
           0,
           L"Folder",
           0,
           0);
    v7 = v8;
    if ( v8 < 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_27;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v12 = 180;
      goto LABEL_7;
    }
  }
  else
  {
    v13 = CContentFolder::_Name(v9, a2, v22, v10);
    ExtensionW = PathFindExtensionW(v13);
    v8 = (*(__int64 (__fastcall **)(void *, _QWORD, const WCHAR *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
           ppv,
           0,
           ExtensionW,
           0,
           0);
    v7 = v8;
    if ( v8 < 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_27;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v12 = 181;
LABEL_7:
      WPP_SF_d(v11[2], v12, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v8);
      goto LABEL_23;
    }
    if ( CompareStringOrdinal(ExtensionW, -1, L".url", -1, 1) == 2 )
      InsertAtFrontProgIdWithFileExtensionOrUriScheme((struct IQueryAssociations *)ppv, v15, v16);
  }
  v7 = (**(__int64 (__fastcall ***)(void *, struct _GUID *, void **))ppv)(ppv, a3, a4);
  if ( v7 >= 0 )
    goto LABEL_27;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_27;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v17 = (unsigned int)CGuidToString::CGuidToString(sz, a3);
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      182,
      (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
      v17,
      v7);
    goto LABEL_23;
  }
LABEL_24:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
    WPP_SF_d(v11[2], 183, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v7);
LABEL_27:
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002a80  mov     [rsp+arg_0], rbx
0x180002a85  push    rbp
0x180002a86  push    rsi
0x180002a87  push    rdi
0x180002a88  push    r12
0x180002a8a  push    r13
0x180002a8c  sub     rsp, 2F0h
0x180002a93  mov     rax, cs:__security_cookie
0x180002a9a  xor     rax, rsp
0x180002a9d  mov     [rsp+318h+var_38], rax
0x180002aa5  mov     rdi, r9
0x180002aa8  mov     rbp, r8
0x180002aab  mov     rsi, rdx
0x180002aae  mov     [rsp+318h+ppv], 0
0x180002ab7  lea     r13, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180002abe  lea     r12, WPP_GLOBAL_Control
0x180002ac5  test    r9, r9
0x180002ac8  jnz     short loc_180002AD4
0x180002aca  mov     ebx, 80004003h
0x180002acf  jmp     loc_180002C7E
0x180002ad4  mov     qword ptr [r9], 0
0x180002adb  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x180002ae2  movdqu  xmmword ptr [rsp+318h+clsid.Data1], xmm0
0x180002ae8  lea     r8, [rsp+318h+ppv]; ppv
0x180002aed  lea     rdx, IID_IQueryAssociations; riid
0x180002af4  lea     rcx, [rsp+318h+clsid]; clsid
0x180002af9  call    cs:__imp_AssocCreate
0x180002aff  mov     ebx, eax
0x180002b01  test    eax, eax
0x180002b03  jns     short loc_180002B38
0x180002b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b0c  cmp     rcx, r12
0x180002b0f  jz      loc_180002CA5
0x180002b15  test    byte ptr [rcx+1Ch], 2
0x180002b19  jz      loc_180002C85
0x180002b1f  mov     edx, 0B3h
0x180002b24  mov     r9d, eax
0x180002b27  mov     r8, r13
0x180002b2a  mov     rcx, [rcx+10h]
0x180002b2e  call    WPP_SF_d
0x180002b33  jmp     loc_180002C7E
0x180002b38  test    byte ptr [rsi+0Ah], 2
0x180002b3c  jz      short loc_180002B8F
0x180002b3e  mov     rcx, [rsp+318h+ppv]
0x180002b43  mov     rax, [rcx]
0x180002b46  mov     qword ptr [rsp+318h+bIgnoreCase], 0
0x180002b4f  xor     r9d, r9d
0x180002b52  lea     r8, aFolder; "Folder"
0x180002b59  xor     edx, edx
0x180002b5b  mov     rax, [rax+18h]
0x180002b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b64  mov     ebx, eax
0x180002b66  test    eax, eax
0x180002b68  jns     loc_180002C24
0x180002b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b75  cmp     rcx, r12
0x180002b78  jz      loc_180002CA5
0x180002b7e  test    byte ptr [rcx+1Ch], 2
0x180002b82  jz      loc_180002C85
0x180002b88  mov     edx, 0B4h
0x180002b8d  jmp     short loc_180002B24
0x180002b8f  lea     r8, [rsp+318h+var_248]; unsigned __int16 *
0x180002b97  mov     rdx, rsi; struct CONTENTITEM *
0x180002b9a  call    ?_Name@CContentFolder@@QEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z; CContentFolder::_Name(CONTENTITEM const *,ushort *,uint)
0x180002b9f  mov     rcx, rax; pszPath
0x180002ba2  call    cs:__imp_PathFindExtensionW
0x180002ba8  mov     rsi, rax
0x180002bab  mov     rcx, [rsp+318h+ppv]
0x180002bb0  mov     rdx, [rcx]
0x180002bb3  mov     rax, [rdx+18h]
0x180002bb7  mov     qword ptr [rsp+318h+bIgnoreCase], 0
0x180002bc0  xor     r9d, r9d
0x180002bc3  mov     r8, rsi
0x180002bc6  xor     edx, edx
0x180002bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bcd  mov     ebx, eax
0x180002bcf  test    eax, eax
0x180002bd1  jns     short loc_180002BF7
0x180002bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bda  cmp     rcx, r12
0x180002bdd  jz      loc_180002CA5
0x180002be3  test    byte ptr [rcx+1Ch], 2
0x180002be7  jz      loc_180002C85
0x180002bed  mov     edx, 0B5h
0x180002bf2  jmp     loc_180002B24
0x180002bf7  mov     [rsp+318h+bIgnoreCase], 1; bIgnoreCase
0x180002bff  or      edx, 0FFFFFFFFh; cchCount1
0x180002c02  mov     r9d, edx; cchCount2
0x180002c05  lea     r8, String2; ".url"
0x180002c0c  mov     rcx, rsi; lpString1
0x180002c0f  call    cs:__imp_CompareStringOrdinal
0x180002c15  cmp     eax, 2
0x180002c18  jnz     short loc_180002C24
0x180002c1a  mov     rcx, [rsp+318h+ppv]; struct IQueryAssociations *
0x180002c1f  call    ?InsertAtFrontProgIdWithFileExtensionOrUriScheme@@YAJPEAUIQueryAssociations@@PEBG1@Z; InsertAtFrontProgIdWithFileExtensionOrUriScheme(IQueryAssociations *,ushort const *,ushort const *)
0x180002c24  mov     rcx, [rsp+318h+ppv]
0x180002c29  mov     rax, [rcx]
0x180002c2c  mov     r8, rdi
0x180002c2f  mov     rdx, rbp
0x180002c32  mov     rax, [rax]
0x180002c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c3a  mov     ebx, eax
0x180002c3c  test    eax, eax
0x180002c3e  jns     short loc_180002CA5
0x180002c40  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c47  cmp     rcx, r12
0x180002c4a  jz      short loc_180002CA5
0x180002c4c  test    byte ptr [rcx+1Ch], 2
0x180002c50  jz      short loc_180002C85
0x180002c52  mov     rdx, rbp; rguid
0x180002c55  lea     rcx, [rsp+318h+sz]; lpsz
0x180002c5a  call    ??0CGuidToString@@QEAA@AEBU_GUID@@@Z; CGuidToString::CGuidToString(_GUID const &)
0x180002c5f  mov     edx, 0B6h
0x180002c64  mov     [rsp+318h+bIgnoreCase], ebx
0x180002c68  mov     r9, rax
0x180002c6b  mov     r8, r13
0x180002c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c75  mov     rcx, [rcx+10h]
0x180002c79  call    WPP_SF_Sd
0x180002c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c85  cmp     rcx, r12
0x180002c88  jz      short loc_180002CA5
0x180002c8a  test    byte ptr [rcx+1Ch], 2
0x180002c8e  jz      short loc_180002CA5
0x180002c90  mov     edx, 0B7h
0x180002c95  mov     r9d, ebx
0x180002c98  mov     r8, r13
0x180002c9b  mov     rcx, [rcx+10h]
0x180002c9f  call    WPP_SF_d
0x180002ca4  nop
0x180002ca5  mov     rcx, [rsp+318h+ppv]
0x180002caa  test    rcx, rcx
0x180002cad  jz      short loc_180002CBC
0x180002caf  mov     rax, [rcx]
0x180002cb2  mov     rax, [rax+10h]
0x180002cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cbb  nop
0x180002cbc  mov     eax, ebx
0x180002cbe  mov     rcx, [rsp+318h+var_38]
0x180002cc6  xor     rcx, rsp; StackCookie
0x180002cc9  call    __security_check_cookie
0x180002cce  mov     rbx, [rsp+318h+arg_0]
0x180002cd6  add     rsp, 2F0h
0x180002cdd  pop     r13
0x180002cdf  pop     r12
0x180002ce1  pop     rdi
0x180002ce2  pop     rsi
0x180002ce3  pop     rbp
0x180002ce4  retn
```
