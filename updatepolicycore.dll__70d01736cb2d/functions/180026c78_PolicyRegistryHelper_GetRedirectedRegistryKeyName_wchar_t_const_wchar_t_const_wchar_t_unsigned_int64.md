# PolicyRegistryHelper::GetRedirectedRegistryKeyName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)

- ea: `0x180026c78`
- end: `0x180026f96`
- name: `?GetRedirectedRegistryKeyName@PolicyRegistryHelper@@SAJPEB_W0PEA_W_K@Z`
- size: `798`
- prototype: `__int64 __fastcall(wchar_t *, const wchar_t *, wchar_t *, wchar_t **)`
- caller_count: `10`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010c1c`
- `0x18001e25c`
- `0x18001f560`
- `0x18001f6c8`
- `0x180022634`
- `0x1800236b8`
- `0x180026f9c`
- `0x180027058`
- `0x180027144`
- `0x180027234`

## callees

- `0x180008ec8`
- `0x180008f38`
- `0x18000aac0`
- `0x18000f3a4`
- `0x18000fb34`
- `0x1800258bc`
- `0x180026c78`
- `0x1800275d0`
- `0x18002d6a0`
- `0x18002fda9`
- `0x18002ffd0`
- `0x180030cb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f10`

## string_xrefs

- `0x180026ded`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`
- `0x180026eee`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`
- `0x180026f38`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`
- `0x180026f58`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyRegistryHelper::GetRedirectedRegistryKeyName(
        wchar_t *a1,
        const wchar_t *a2,
        wchar_t *a3,
        wchar_t **a4)
{
  __int64 v8; // rdx
  void *v9; // rdi
  _QWORD *v10; // rax
  _BYTE *v11; // rcx
  _QWORD *v12; // rax
  void *inserted; // rdx
  _QWORD *v14; // rax
  unsigned int PersistedRegistryLocation; // eax
  unsigned int v16; // ebx
  const OLECHAR *v17; // r8
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  signed __int64 v20; // r8
  wchar_t v21; // ax
  wchar_t *v22; // rax
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  unsigned __int64 v26; // r11
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  char *v29; // [rsp+28h] [rbp-D8h]
  __int128 v30; // [rsp+30h] [rbp-D0h]
  __int128 v31; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v33[256]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  if ( !a1 || !*a1 )
  {
    v8 = 64;
    goto LABEL_49;
  }
  if ( !a3 )
  {
    v8 = 65;
LABEL_49:
    v16 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
      (const char *)0x80070057LL,
      v28);
    return v16;
  }
  v9 = PolicyRegistryHelper::s_defaultRedirectionMap;
  v10 = (_QWORD *)*((_QWORD *)PolicyRegistryHelper::s_defaultRedirectionMap + 1);
  v11 = PolicyRegistryHelper::s_defaultRedirectionMap;
  while ( !*((_BYTE *)v10 + 25) )
  {
    if ( v10[4] >= (unsigned __int64)a1 )
      v11 = v10;
    else
      v10 += 2;
    v10 = (_QWORD *)*v10;
  }
  if ( v11[25] || (unsigned __int64)a1 < *((_QWORD *)v11 + 4) )
  {
    v29 = (char *)a1;
    v16 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x46,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
      (const char *)0x80070057LL,
      (int)"Redirection Id %ws not found in default map.",
      v29);
    return v16;
  }
  pv[0] = 0;
  v12 = (_QWORD *)*((_QWORD *)PolicyRegistryHelper::s_defaultRedirectionMap + 1);
  v30 = (unsigned __int64)v12;
  inserted = PolicyRegistryHelper::s_defaultRedirectionMap;
  while ( !*((_BYTE *)v12 + 25) )
  {
    *(_QWORD *)&v30 = v12;
    if ( v12[4] >= (unsigned __int64)a1 )
    {
      DWORD2(v30) = 1;
      inserted = v12;
    }
    else
    {
      DWORD2(v30) = 0;
      v12 += 2;
    }
    v12 = (_QWORD *)*v12;
  }
  if ( *((_BYTE *)inserted + 25) || (unsigned __int64)a1 < *((_QWORD *)inserted + 4) )
  {
    if ( qword_18004EFB8 == 0x555555555555555LL )
      std::_Throw_tree_length_error();
    v14 = operator new(0x30u);
    v14[4] = a1;
    v14[5] = 0;
    *v14 = v9;
    v14[1] = v9;
    v14[2] = v9;
    *((_WORD *)v14 + 12) = 0;
    v31 = v30;
    inserted = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<enum tagUpdatePolicy const,AllowInfo>>>::_Insert_node(
                         &PolicyRegistryHelper::s_defaultRedirectionMap,
                         &v31,
                         v14);
  }
  PersistedRegistryLocation = WUSystemInterfaceHelper::GetPersistedRegistryLocation(
                                (WUSystemInterfaceHelper *)a1,
                                *((const wchar_t **)inserted + 5),
                                (const wchar_t *)pv,
                                a4);
  if ( PersistedRegistryLocation )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4D,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
            (const char *)PersistedRegistryLocation,
            v28);
    goto LABEL_45;
  }
  memset_0(v33, 0, sizeof(v33));
  v17 = &psz;
  if ( pv[0] )
    v17 = (const OLECHAR *)pv[0];
  v18 = 256;
  v19 = v33;
  v20 = (char *)v17 - (char *)v33;
  do
  {
    if ( v18 == -2147483390 )
      break;
    v21 = *(wchar_t *)((char *)v19 + v20);
    if ( !v21 )
      break;
    *v19++ = v21;
    --v18;
  }
  while ( v18 );
  v22 = v19 - 1;
  if ( v18 )
    v22 = v19;
  *v22 = 0;
  v16 = v18 == 0 ? 0x8007007A : 0;
  if ( !v18 )
  {
    v23 = v16;
    v24 = 80;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
      (const char *)v23,
      v28);
    goto LABEL_45;
  }
  v25 = StringCchCopyW(a3, (unsigned __int64)a4, v33);
  v16 = v25;
  if ( v25 < 0 )
  {
    v24 = 82;
LABEL_42:
    v23 = (unsigned int)v25;
    goto LABEL_43;
  }
  if ( a2 )
  {
    v25 = StringCchCatW(v33, v26, a2);
    v16 = v25;
    if ( v25 < 0 )
    {
      v24 = 86;
      goto LABEL_42;
    }
  }
  v25 = StringCchCopyW(a3, (unsigned __int64)a4, v33);
  v16 = v25;
  if ( v25 < 0 )
  {
    v24 = 89;
    goto LABEL_42;
  }
  v16 = 0;
LABEL_45:
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return v16;
}

```

## disassembly

```asm
0x180026c78  push    rbp
0x180026c7a  push    rbx
0x180026c7b  push    rsi
0x180026c7c  push    rdi
0x180026c7d  push    r12
0x180026c7f  push    r13
0x180026c81  push    r14
0x180026c83  push    r15
0x180026c85  lea     rbp, [rsp-188h]
0x180026c8d  sub     rsp, 288h
0x180026c94  mov     rax, cs:__security_cookie
0x180026c9b  xor     rax, rsp
0x180026c9e  mov     [rbp+1C0h+var_50], rax
0x180026ca5  mov     r15, r9
0x180026ca8  mov     rsi, r8
0x180026cab  mov     r14, rdx
0x180026cae  mov     rbx, rcx
0x180026cb1  xor     r13d, r13d
0x180026cb4  test    rcx, rcx
0x180026cb7  jz      loc_180026F4B
0x180026cbd  cmp     [rcx], r13w
0x180026cc1  jz      loc_180026F4B
0x180026cc7  test    r8, r8
0x180026cca  jnz     short loc_180026CD5
0x180026ccc  lea     edx, [r8+41h]
0x180026cd0  jmp     loc_180026F50
0x180026cd5  mov     rdi, cs:?s_defaultRedirectionMap@PolicyRegistryHelper@@0V?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@A; std::map<wchar_t const *,wchar_t const *> PolicyRegistryHelper::s_defaultRedirectionMap
0x180026cdc  mov     rax, [rdi+8]
0x180026ce0  xor     ecx, ecx
0x180026ce2  mov     dword ptr [rsp+2C0h+var_290+0Ch], ecx
0x180026ce6  mov     rcx, rdi
0x180026ce9  jmp     short loc_180026CFD
0x180026ceb  cmp     [rax+20h], rbx
0x180026cef  jnb     short loc_180026CF7
0x180026cf1  add     rax, 10h
0x180026cf5  jmp     short loc_180026CFA
0x180026cf7  mov     rcx, rax
0x180026cfa  mov     rax, [rax]
0x180026cfd  cmp     [rax+19h], r13b
0x180026d01  jz      short loc_180026CEB
0x180026d03  cmp     [rcx+19h], r13b
0x180026d07  jnz     loc_180026F18
0x180026d0d  cmp     rbx, [rcx+20h]
0x180026d11  jb      loc_180026F18
0x180026d17  mov     [rsp+2C0h+pv], r13
0x180026d1c  mov     rax, [rdi+8]
0x180026d20  mov     qword ptr [rsp+2C0h+var_290], rax
0x180026d25  mov     [rsp+38h], r13
0x180026d2a  mov     rdx, rdi
0x180026d2d  jmp     short loc_180026D53
0x180026d2f  mov     qword ptr [rsp+2C0h+var_290], rax
0x180026d34  cmp     [rax+20h], rbx
0x180026d38  jnb     short loc_180026D45
0x180026d3a  mov     dword ptr [rsp+2C0h+var_290+8], r13d
0x180026d3f  add     rax, 10h
0x180026d43  jmp     short loc_180026D50
0x180026d45  mov     dword ptr [rsp+2C0h+var_290+8], 1
0x180026d4d  mov     rdx, rax
0x180026d50  mov     rax, [rax]
0x180026d53  cmp     [rax+19h], r13b
0x180026d57  jz      short loc_180026D2F
0x180026d59  cmp     [rdx+19h], r13b
0x180026d5d  jnz     short loc_180026D65
0x180026d5f  cmp     rbx, [rdx+20h]
0x180026d63  jnb     short loc_180026DCE
0x180026d65  mov     rax, 555555555555555h
0x180026d6f  cmp     cs:qword_18004EFB8, rax
0x180026d76  jz      loc_180026F90
0x180026d7c  lea     r12, ?s_defaultRedirectionMap@PolicyRegistryHelper@@0V?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@A; std::map<wchar_t const *,wchar_t const *> PolicyRegistryHelper::s_defaultRedirectionMap
0x180026d83  mov     qword ptr [rsp+2C0h+var_270], r12
0x180026d88  mov     qword ptr [rsp+2C0h+var_270+8], r13
0x180026d8d  mov     ecx, 30h ; '0'; Size
0x180026d92  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026d97  nop
0x180026d98  mov     [rax+20h], rbx
0x180026d9c  mov     [rax+28h], r13
0x180026da0  mov     [rax], rdi
0x180026da3  mov     [rax+8], rdi
0x180026da7  mov     [rax+10h], rdi
0x180026dab  mov     [rax+18h], r13w
0x180026db0  movups  xmm0, [rsp+2C0h+var_290]
0x180026db5  movdqu  [rsp+2C0h+var_270], xmm0
0x180026dbb  mov     r8, rax
0x180026dbe  lea     rdx, [rsp+2C0h+var_270]
0x180026dc3  mov     rcx, r12
0x180026dc6  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<tagUpdatePolicy const,AllowInfo>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<tagUpdatePolicy const,AllowInfo>,void *> *>,std::_Tree_node<std::pair<tagUpdatePolicy const,AllowInfo>,void *> * const)
0x180026dcb  mov     rdx, rax
0x180026dce  lea     r8, [rsp+2C0h+pv]; wchar_t *
0x180026dd3  mov     rdx, [rdx+28h]; wchar_t *
0x180026dd7  mov     rcx, rbx; this
0x180026dda  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x180026ddf  test    eax, eax
0x180026de1  jz      short loc_180026E05
0x180026de3  mov     rcx, [rbp+1C8h]; this
0x180026dea  mov     r9d, eax; char *
0x180026ded  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180026df4  mov     edx, 4Dh ; 'M'; void *
0x180026df9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180026dfe  mov     ebx, eax
0x180026e00  jmp     loc_180026F06
0x180026e05  xor     edx, edx; Val
0x180026e07  mov     r8d, 200h; Size
0x180026e0d  lea     rcx, [rsp+2C0h+var_250]; void *
0x180026e12  call    memset_0
0x180026e17  mov     rax, [rsp+2C0h+pv]
0x180026e1c  lea     r8, psz
0x180026e23  test    rax, rax
0x180026e26  cmovnz  r8, rax
0x180026e2a  mov     r11d, 100h
0x180026e30  mov     edx, r11d
0x180026e33  lea     rcx, [rsp+2C0h+var_250]
0x180026e38  lea     rax, [rsp+2C0h+var_250]
0x180026e3d  sub     r8, rax
0x180026e40  lea     rax, [rdx+7FFFFEFEh]
0x180026e47  test    rax, rax
0x180026e4a  jz      short loc_180026E63
0x180026e4c  movzx   eax, word ptr [rcx+r8]
0x180026e51  test    ax, ax
0x180026e54  jz      short loc_180026E63
0x180026e56  mov     [rcx], ax
0x180026e59  add     rcx, 2
0x180026e5d  sub     rdx, 1
0x180026e61  jnz     short loc_180026E40
0x180026e63  lea     rax, [rcx-2]
0x180026e67  test    rdx, rdx
0x180026e6a  cmovnz  rax, rcx
0x180026e6e  mov     [rax], r13w
0x180026e72  mov     rax, rdx
0x180026e75  neg     rax
0x180026e78  sbb     ebx, ebx
0x180026e7a  not     ebx
0x180026e7c  and     ebx, 8007007Ah
0x180026e82  test    rdx, rdx
0x180026e85  jnz     short loc_180026E91
0x180026e87  mov     r9d, ebx
0x180026e8a  mov     edx, 50h ; 'P'
0x180026e8f  jmp     short loc_180026EEE
0x180026e91  lea     r8, [rsp+2C0h+var_250]; wchar_t *
0x180026e96  mov     rdx, r15; unsigned __int64
0x180026e99  mov     rcx, rsi; wchar_t *
0x180026e9c  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180026ea1  mov     ebx, eax
0x180026ea3  test    eax, eax
0x180026ea5  jns     short loc_180026EAE
0x180026ea7  mov     edx, 52h ; 'R'
0x180026eac  jmp     short loc_180026EEB
0x180026eae  test    r14, r14
0x180026eb1  jz      short loc_180026ED0
0x180026eb3  mov     r8, r14; wchar_t *
0x180026eb6  mov     rdx, r11; unsigned __int64
0x180026eb9  lea     rcx, [rsp+2C0h+var_250]; wchar_t *
0x180026ebe  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180026ec3  mov     ebx, eax
0x180026ec5  test    eax, eax
0x180026ec7  jns     short loc_180026ED0
0x180026ec9  mov     edx, 56h ; 'V'
0x180026ece  jmp     short loc_180026EEB
0x180026ed0  lea     r8, [rsp+2C0h+var_250]; wchar_t *
0x180026ed5  mov     rdx, r15; unsigned __int64
0x180026ed8  mov     rcx, rsi; wchar_t *
0x180026edb  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180026ee0  mov     ebx, eax
0x180026ee2  test    eax, eax
0x180026ee4  jns     short loc_180026F03
0x180026ee6  mov     edx, 59h ; 'Y'; void *
0x180026eeb  mov     r9d, eax; char *
0x180026eee  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180026ef5  mov     rcx, [rbp+1C8h]; this
0x180026efc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f01  jmp     short loc_180026F06
0x180026f03  mov     ebx, r13d
0x180026f06  mov     rcx, [rsp+2C0h+pv]; pv
0x180026f0b  test    rcx, rcx
0x180026f0e  jz      short loc_180026F6B
0x180026f10  call    cs:__imp_CoTaskMemFree
0x180026f16  jmp     short loc_180026F6B
0x180026f18  mov     rcx, [rbp+1C8h]; this
0x180026f1f  mov     [rsp+2C0h+var_298], rbx; char *
0x180026f24  lea     rax, aRedirectionIdW; "Redirection Id %ws not found in default"...
0x180026f2b  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x180026f30  mov     ebx, 80070057h
0x180026f35  mov     r9d, ebx; char *
0x180026f38  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180026f3f  mov     edx, 46h ; 'F'; void *
0x180026f44  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180026f49  jmp     short loc_180026F6B
0x180026f4b  mov     edx, 40h ; '@'; void *
0x180026f50  mov     ebx, 80070057h
0x180026f55  mov     r9d, ebx; char *
0x180026f58  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180026f5f  mov     rcx, [rbp+1C8h]; this
0x180026f66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f6b  mov     eax, ebx
0x180026f6d  mov     rcx, [rbp+1C0h+var_50]
0x180026f74  xor     rcx, rsp; StackCookie
0x180026f77  call    __security_check_cookie
0x180026f7c  add     rsp, 288h
0x180026f83  pop     r15
0x180026f85  pop     r14
0x180026f87  pop     r13
0x180026f89  pop     r12
0x180026f8b  pop     rdi
0x180026f8c  pop     rsi
0x180026f8d  pop     rbx
0x180026f8e  pop     rbp
0x180026f8f  retn
0x180026f90  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
