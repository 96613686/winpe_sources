# ProfileHolder::AddProfile(WWAN_PROFILE &,bool)

- ea: `0x1800a8c44`
- end: `0x1800a904c`
- name: `?AddProfile@ProfileHolder@@QEAAKAEAUWWAN_PROFILE@@_N@Z`
- size: `1032`
- prototype: `unsigned int __fastcall(ProfileHolder *__hidden this, struct WWAN_PROFILE *, bool)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800a6664`
- `0x1800aa4d8`

## callees

- `0x1800085d0`
- `0x1800094dc`
- `0x1800094f4`
- `0x180010fd8`
- `0x180012300`
- `0x180013288`
- `0x180014f1c`
- `0x1800a78d8`
- `0x1800a82a8`
- `0x1800a888c`
- `0x1800a8c44`
- `0x1800a9c80`
- `0x1800aa8a4`
- `0x1800c8520`
- `0x1800c858c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a8d01`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a8e64`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a8d01`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a8e64`
- `WwanPrfl!WwanProfileInit` at `0x1800a8e17`
- `WwanPrfl!WwanProfileInit` at `0x1800a8f28`
- `WwanPrfl!WwanProfileInit` at `0x1800a8e17`
- `WwanPrfl!WwanProfileInit` at `0x1800a8f28`
- `WwanPrfl!WwanProfileCopyProfile` at `0x1800a8e27`
- `WwanPrfl!WwanProfileCopyProfile` at `0x1800a8f38`
- `WwanPrfl!WwanProfileCopyProfile` at `0x1800a8e27`
- `WwanPrfl!WwanProfileCopyProfile` at `0x1800a8f38`

## string_xrefs

- `0x1800a8cca`: `a ModemOperatorProvisioned profile %s already exists`
- `0x1800a8de2`: `pri %d purchase profile %s already exists`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProfileHolder::AddProfile(ProfileHolder *this, struct WWAN_PROFILE *a2, char a3)
{
  unsigned int v5; // r14d
  unsigned int v6; // r9d
  char *v7; // rdi
  const wchar_t **v8; // r12
  const wchar_t *v9; // r15
  const wchar_t *i; // rbx
  _QWORD *v11; // rbx
  _QWORD *v12; // rcx
  int v13; // r9d
  __int64 CreationTypePriority; // r12
  __int64 ****v15; // r15
  const wchar_t **v16; // rdi
  const wchar_t *j; // rbx
  __int64 ***v18; // r9
  __int64 **k; // rbx
  __int64 *v20; // rdi
  __int64 *v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  __int64 *m; // rbx
  char *v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[6328]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE Src[6320]; // [rsp+1930h] [rbp+1830h] BYREF

  v5 = 0;
  v6 = *((_DWORD *)a2 + 769);
  if ( v6 == 5 )
  {
    v7 = (char *)this + 56;
    v8 = (const wchar_t **)*((_QWORD *)this + 7);
    v9 = *v8;
    for ( i = *v8; i != (const wchar_t *)v8; i = *(const wchar_t **)i )
    {
      if ( !wcsncmp_0((const wchar_t *)a2, i + 8, 0x100u) )
      {
        WwanLog::Error("ProfileHolder::AddProfile", 0, L"a ModemOperatorProvisioned profile %s already exists", a2);
        goto LABEL_7;
      }
    }
    if ( *((_QWORD *)v7 + 1) == 0xA57EB50295FADLL )
      std::_Xlength_error("list too long");
    v27 = v7;
    v28 = 0;
    v11 = std::_Allocate<16,std::_Default_allocate_traits>(0x18C0u);
    memcpy_0(v11 + 2, a2, 0x18B0u);
    ++*((_QWORD *)v7 + 1);
    v12 = (_QWORD *)*((_QWORD *)v9 + 1);
    *v11 = v9;
    v11[1] = v12;
    v28 = 0;
    *((_QWORD *)v9 + 1) = v11;
    *v12 = v11;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<WWAN_PROFILE,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<WWAN_PROFILE,void *>>>(&v27);
    if ( v11 == *(_QWORD **)v7 )
    {
      WwanLog::Error(
        "ProfileHolder::AddProfile",
        0,
        L"failed to insert a ModemOperatorProvisioned profile %s failed",
        a2);
LABEL_12:
      v5 = 14;
    }
    else
    {
      WwanLog::Info("ProfileHolder::AddProfile", 0, L" inserted a ModemOperatorProvisioned purchase profile %s", a2);
    }
  }
  else
  {
    CreationTypePriority = (unsigned int)GetCreationTypePriority(v6);
    if ( *((_DWORD *)a2 + 1120) )
    {
      v15 = (__int64 ****)((char *)this + 40);
      v16 = (const wchar_t **)*((_QWORD *)this + 5);
      for ( j = *v16; j != (const wchar_t *)v16; j = *(const wchar_t **)j )
      {
        if ( !wcsncmp_0((const wchar_t *)a2, j + 8, 0x100u) )
        {
          WwanLog::Error(
            "ProfileHolder::AddProfile",
            0,
            L"pri %d purchase profile %s already exists",
            (unsigned int)CreationTypePriority,
            a2);
LABEL_7:
          v5 = 52;
          goto LABEL_33;
        }
      }
      memset_0(Src, 0, sizeof(Src));
      WwanProfileInit(Src);
      WwanProfileCopyProfile(Src, a2);
      v18 = *v15;
      for ( k = **v15;
            k != (__int64 **)v18
         && (unsigned int)CreationTypePriority > (unsigned int)GetCreationTypePriority(*((unsigned int *)k + 773));
            k = (__int64 **)*k )
      {
        ;
      }
      if ( *((_QWORD *)this + 6) == 0xA57EB50295FADLL )
        std::_Xlength_error("list too long");
      v27 = (char *)this + 40;
      v28 = 0;
      v20 = std::_Allocate<16,std::_Default_allocate_traits>(0x18C0u);
      memcpy_0(v20 + 2, Src, 0x18B0u);
      ++*((_QWORD *)this + 6);
      v21 = k[1];
      *v20 = (__int64)k;
      v20[1] = (__int64)v21;
      v28 = 0;
      k[1] = v20;
      *v21 = (__int64)v20;
      std::_Alloc_construct_ptr<std::allocator<std::_List_node<WWAN_PROFILE,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<WWAN_PROFILE,void *>>>(&v27);
      if ( v20 == (__int64 *)*v15 )
      {
        WwanLog::Error(
          "ProfileHolder::AddProfile",
          0,
          L"failed to insert pri %d purchase profile %s failed",
          (unsigned int)CreationTypePriority,
          a2);
        goto LABEL_12;
      }
      WwanLog::Info(
        "ProfileHolder::AddProfile",
        0,
        L" inserted a pri %d purchase profile %s",
        (unsigned int)CreationTypePriority,
        a2);
    }
    else
    {
      if ( v13 == 4 )
        *((_DWORD *)a2 + 1312) = 0;
      memset_0(Src, 0, sizeof(Src));
      WwanProfileInit(Src);
      WwanProfileCopyProfile(Src, a2);
      v29 = *((_DWORD *)a2 + 1312);
      memcpy_0(v30, Src, 0x18B0u);
      std::_Tree<std::_Tmap_traits<unsigned long,WWAN_PROFILE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,WWAN_PROFILE>>,1>>::_Emplace<std::pair<unsigned long,WWAN_PROFILE>>(
        *((_QWORD *)this + 4) + 16 * CreationTypePriority,
        &v27,
        &v29);
      v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
      WwanLog::Info(
        "ProfileHolder::AddProfile",
        0,
        L"iccid %s added pri %d profile %s, connMode %d, additional %d creation %d",
        v22,
        CreationTypePriority,
        a2,
        *((_DWORD *)a2 + 799),
        *((_DWORD *)a2 + 1155),
        *((_DWORD *)a2 + 769));
      if ( (byte_1801528C4 & 0x10) != 0 )
      {
        v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
        McTemplateU0zzqtq_EventWriteTransfer(
          *((_DWORD *)a2 + 799),
          *((_DWORD *)a2 + 1155) != 0,
          v23,
          (_DWORD)a2,
          *((_DWORD *)a2 + 799),
          *((_DWORD *)a2 + 1155) != 0,
          *((_DWORD *)a2 + 769));
      }
    }
  }
LABEL_33:
  if ( a3 )
  {
    for ( m = (__int64 *)*((_QWORD *)this + 10); ; ProfileHandler::OnProfileAdded((ProfileHandler *)m[4], a2) )
    {
      m = (__int64 *)*m;
      if ( m == *((__int64 **)this + 10) )
        break;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800a8c44  mov     [rsp-8+arg_10], rbx
0x1800a8c49  push    rbp
0x1800a8c4a  push    rsi
0x1800a8c4b  push    rdi
0x1800a8c4c  push    r12
0x1800a8c4e  push    r13
0x1800a8c50  push    r14
0x1800a8c52  push    r15
0x1800a8c54  lea     rbp, [rsp-30F0h]
0x1800a8c5c  mov     eax, 31F0h
0x1800a8c61  call    _alloca_probe
0x1800a8c66  sub     rsp, rax
0x1800a8c69  mov     rax, cs:__security_cookie
0x1800a8c70  xor     rax, rsp
0x1800a8c73  mov     [rbp+3120h+var_40], rax
0x1800a8c7a  mov     [rsp+3220h+var_31D0], r8b
0x1800a8c7f  mov     rsi, rdx
0x1800a8c82  mov     r13, rcx
0x1800a8c85  xor     r14d, r14d
0x1800a8c88  mov     r9d, [rdx+0C04h]
0x1800a8c8f  cmp     r9d, 5
0x1800a8c93  jnz     loc_1800A8D98
0x1800a8c99  lea     rdi, [rcx+38h]
0x1800a8c9d  mov     r12, [rdi]
0x1800a8ca0  mov     r15, [r12]
0x1800a8ca4  mov     rbx, r15
0x1800a8ca7  cmp     rbx, r12
0x1800a8caa  jz      short loc_1800A8CEA
0x1800a8cac  lea     rdx, [rbx+10h]; String2
0x1800a8cb0  mov     r8d, 100h; MaxCount
0x1800a8cb6  mov     rcx, rsi; String1
0x1800a8cb9  call    wcsncmp_0
0x1800a8cbe  test    eax, eax
0x1800a8cc0  jz      short loc_1800A8CC7
0x1800a8cc2  mov     rbx, [rbx]
0x1800a8cc5  jmp     short loc_1800A8CA7
0x1800a8cc7  mov     r9, rsi
0x1800a8cca  lea     r8, aAModemoperator; "a ModemOperatorProvisioned profile %s a"...
0x1800a8cd1  xor     edx, edx; struct _GUID *
0x1800a8cd3  lea     rcx, aProfileholderA; "ProfileHolder::AddProfile"
0x1800a8cda  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a8cdf  mov     r14d, 34h ; '4'
0x1800a8ce5  jmp     loc_1800A8FFD
0x1800a8cea  mov     rax, 0A57EB50295FADh
0x1800a8cf4  cmp     [rdi+8], rax
0x1800a8cf8  jnz     short loc_1800A8D08
0x1800a8cfa  lea     rcx, aListTooLong; "list too long"
0x1800a8d01  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800a8d08  mov     [rsp+3220h+var_31C8], rdi
0x1800a8d0d  mov     [rsp+3220h+var_31C0], 0
0x1800a8d16  mov     ecx, 18C0h
0x1800a8d1b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800a8d20  mov     rbx, rax
0x1800a8d23  lea     rcx, [rax+10h]; void *
0x1800a8d27  mov     r8d, 18B0h; Size
0x1800a8d2d  mov     rdx, rsi; Src
0x1800a8d30  call    memcpy_0
0x1800a8d35  nop
0x1800a8d36  inc     qword ptr [rdi+8]
0x1800a8d3a  mov     rcx, [r15+8]
0x1800a8d3e  mov     [rbx], r15
0x1800a8d41  mov     [rbx+8], rcx
0x1800a8d45  mov     [rsp+3220h+var_31C0], 0
0x1800a8d4e  mov     [r15+8], rbx
0x1800a8d52  mov     [rcx], rbx
0x1800a8d55  lea     rcx, [rsp+3220h+var_31C8]
0x1800a8d5a  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@UWWAN_PROFILE@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<WWAN_PROFILE,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<WWAN_PROFILE,void *>>>(void)
0x1800a8d5f  mov     r9, rsi
0x1800a8d62  xor     edx, edx; struct _GUID *
0x1800a8d64  lea     rcx, aProfileholderA; "ProfileHolder::AddProfile"
0x1800a8d6b  cmp     rbx, [rdi]
0x1800a8d6e  jnz     short loc_1800A8D87
0x1800a8d70  lea     r8, aFailedToInsert_7; "failed to insert a ModemOperatorProvisi"...
0x1800a8d77  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a8d7c  mov     r14d, 0Eh
0x1800a8d82  jmp     loc_1800A8FFD
0x1800a8d87  lea     r8, aInsertedAModem; " inserted a ModemOperatorProvisioned pu"...
0x1800a8d8e  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800a8d93  jmp     loc_1800A8FFD
0x1800a8d98  mov     ecx, r9d
0x1800a8d9b  call    ?GetCreationTypePriority@@YAKW4WWAN_PROFILE_CREATION_TYPE@@@Z; GetCreationTypePriority(WWAN_PROFILE_CREATION_TYPE)
0x1800a8da0  mov     r12d, eax
0x1800a8da3  cmp     [rsi+1180h], r14d
0x1800a8daa  jz      loc_1800A8EFE
0x1800a8db0  lea     r15, [r13+28h]
0x1800a8db4  mov     rdi, [r15]
0x1800a8db7  mov     rbx, [rdi]
0x1800a8dba  cmp     rbx, rdi
0x1800a8dbd  jz      short loc_1800A8DFC
0x1800a8dbf  lea     rdx, [rbx+10h]; String2
0x1800a8dc3  mov     r8d, 100h; MaxCount
0x1800a8dc9  mov     rcx, rsi; String1
0x1800a8dcc  call    wcsncmp_0
0x1800a8dd1  test    eax, eax
0x1800a8dd3  jz      short loc_1800A8DDA
0x1800a8dd5  mov     rbx, [rbx]
0x1800a8dd8  jmp     short loc_1800A8DBA
0x1800a8dda  mov     [rsp+3220h+var_3200], rsi
0x1800a8ddf  mov     r9d, r12d
0x1800a8de2  lea     r8, aPriDPurchasePr; "pri %d purchase profile %s already exis"...
0x1800a8de9  xor     edx, edx; struct _GUID *
0x1800a8deb  lea     rcx, aProfileholderA; "ProfileHolder::AddProfile"
0x1800a8df2  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a8df7  jmp     loc_1800A8CDF
0x1800a8dfc  xor     edx, edx; Val
0x1800a8dfe  mov     r8d, 18B0h; Size
0x1800a8e04  lea     rcx, [rbp+3120h+Src]; void *
0x1800a8e0b  call    memset_0
0x1800a8e10  lea     rcx, [rbp+3120h+Src]
0x1800a8e17  call    cs:__imp_WwanProfileInit
0x1800a8e1d  mov     rdx, rsi
0x1800a8e20  lea     rcx, [rbp+3120h+Src]
0x1800a8e27  call    cs:__imp_WwanProfileCopyProfile
0x1800a8e2d  mov     r9, [r15]
0x1800a8e30  mov     rbx, [r9]
0x1800a8e33  cmp     rbx, r9
0x1800a8e36  jz      short loc_1800A8E4D
0x1800a8e38  mov     ecx, [rbx+0C14h]
0x1800a8e3e  call    ?GetCreationTypePriority@@YAKW4WWAN_PROFILE_CREATION_TYPE@@@Z; GetCreationTypePriority(WWAN_PROFILE_CREATION_TYPE)
0x1800a8e43  cmp     r12d, eax
0x1800a8e46  jbe     short loc_1800A8E4D
0x1800a8e48  mov     rbx, [rbx]
0x1800a8e4b  jmp     short loc_1800A8E33
0x1800a8e4d  mov     rax, 0A57EB50295FADh
0x1800a8e57  cmp     [r15+8], rax
0x1800a8e5b  jnz     short loc_1800A8E6B
0x1800a8e5d  lea     rcx, aListTooLong; "list too long"
0x1800a8e64  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800a8e6b  mov     [rsp+3220h+var_31C8], r15
0x1800a8e70  mov     [rsp+3220h+var_31C0], 0
0x1800a8e79  mov     ecx, 18C0h
0x1800a8e7e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800a8e83  mov     rdi, rax
0x1800a8e86  lea     rcx, [rax+10h]; void *
0x1800a8e8a  mov     r8d, 18B0h; Size
0x1800a8e90  lea     rdx, [rbp+3120h+Src]; Src
0x1800a8e97  call    memcpy_0
0x1800a8e9c  nop
0x1800a8e9d  inc     qword ptr [r15+8]
0x1800a8ea1  mov     rcx, [rbx+8]
0x1800a8ea5  mov     [rdi], rbx
0x1800a8ea8  mov     [rdi+8], rcx
0x1800a8eac  mov     [rsp+3220h+var_31C0], 0
0x1800a8eb5  mov     [rbx+8], rdi
0x1800a8eb9  mov     [rcx], rdi
0x1800a8ebc  lea     rcx, [rsp+3220h+var_31C8]
0x1800a8ec1  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@UWWAN_PROFILE@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<WWAN_PROFILE,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<WWAN_PROFILE,void *>>>(void)
0x1800a8ec6  mov     [rsp+3220h+var_3200], rsi
0x1800a8ecb  mov     r9d, r12d
0x1800a8ece  xor     edx, edx; struct _GUID *
0x1800a8ed0  lea     rcx, aProfileholderA; "ProfileHolder::AddProfile"
0x1800a8ed7  cmp     rdi, [r15]
0x1800a8eda  jnz     short loc_1800A8EED
0x1800a8edc  lea     r8, aFailedToInsert_8; "failed to insert pri %d purchase profil"...
0x1800a8ee3  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a8ee8  jmp     loc_1800A8D7C
0x1800a8eed  lea     r8, aInsertedAPriDP; " inserted a pri %d purchase profile %s"
0x1800a8ef4  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800a8ef9  jmp     loc_1800A8FFD
0x1800a8efe  cmp     r9d, 4
0x1800a8f02  jnz     short loc_1800A8F0B
0x1800a8f04  mov     [rsi+1480h], r14d
0x1800a8f0b  mov     ebx, 18B0h
0x1800a8f10  mov     r8d, ebx; Size
0x1800a8f13  xor     edx, edx; Val
0x1800a8f15  lea     rcx, [rbp+3120h+Src]; void *
0x1800a8f1c  call    memset_0
0x1800a8f21  lea     rcx, [rbp+3120h+Src]
0x1800a8f28  call    cs:__imp_WwanProfileInit
0x1800a8f2e  mov     rdx, rsi
0x1800a8f31  lea     rcx, [rbp+3120h+Src]
0x1800a8f38  call    cs:__imp_WwanProfileCopyProfile
0x1800a8f3e  mov     eax, [rsi+1480h]
0x1800a8f44  mov     [rsp+3220h+var_31B0], eax
0x1800a8f48  mov     r8d, ebx; Size
0x1800a8f4b  lea     rdx, [rbp+3120h+Src]; Src
0x1800a8f52  lea     rcx, [rsp+3220h+var_31A8]; void *
0x1800a8f57  call    memcpy_0
0x1800a8f5c  mov     rcx, r12
0x1800a8f5f  shl     rcx, 4
0x1800a8f63  add     rcx, [r13+20h]
0x1800a8f67  lea     r8, [rsp+3220h+var_31B0]
0x1800a8f6c  lea     rdx, [rsp+3220h+var_31C8]
0x1800a8f71  call    ??$_Emplace@U?$pair@KUWWAN_PROFILE@@@std@@@?$_Tree@V?$_Tmap_traits@KUWWAN_PROFILE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUWWAN_PROFILE@@@std@@@3@$00@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKUWWAN_PROFILE@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@KUWWAN_PROFILE@@@1@@Z; std::_Tree<std::_Tmap_traits<ulong,WWAN_PROFILE,std::less<ulong>,std::allocator<std::pair<ulong const,WWAN_PROFILE>>,1>>::_Emplace<std::pair<ulong,WWAN_PROFILE>>(std::pair<ulong,WWAN_PROFILE> &&)
0x1800a8f76  mov     rcx, r13
0x1800a8f79  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a8f7e  mov     ecx, [rsi+0C04h]
0x1800a8f84  mov     [rsp+3220h+var_31E0], ecx
0x1800a8f88  mov     ecx, [rsi+120Ch]
0x1800a8f8e  mov     [rsp+3220h+var_31E8], ecx
0x1800a8f92  mov     ecx, [rsi+0C7Ch]
0x1800a8f98  mov     [rsp+3220h+var_31F0], ecx
0x1800a8f9c  mov     [rsp+3220h+var_31F8], rsi
0x1800a8fa1  mov     dword ptr [rsp+3220h+var_3200], r12d
0x1800a8fa6  mov     r9, rax
0x1800a8fa9  lea     r8, aIccidSAddedPri; "iccid %s added pri %d profile %s, connM"...
0x1800a8fb0  xor     edx, edx; struct _GUID *
0x1800a8fb2  lea     rcx, aProfileholderA; "ProfileHolder::AddProfile"
0x1800a8fb9  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800a8fbe  test    cs:byte_1801528C4, 10h
0x1800a8fc5  jz      short loc_1800A8FFD
0x1800a8fc7  mov     rcx, r13
0x1800a8fca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a8fcf  xor     edx, edx
0x1800a8fd1  cmp     [rsi+120Ch], edx
0x1800a8fd7  setnz   dl
0x1800a8fda  mov     ecx, [rsi+0C04h]
0x1800a8fe0  mov     [rsp+3220h+var_31F0], ecx
0x1800a8fe4  mov     dword ptr [rsp+3220h+var_31F8], edx
0x1800a8fe8  mov     ecx, [rsi+0C7Ch]
0x1800a8fee  mov     dword ptr [rsp+3220h+var_3200], ecx
0x1800a8ff2  mov     r9, rsi
0x1800a8ff5  mov     r8, rax
0x1800a8ff8  call    McTemplateU0zzqtq_EventWriteTransfer
0x1800a8ffd  cmp     [rsp+3220h+var_31D0], 0
0x1800a9002  jz      short loc_1800A901F
0x1800a9004  mov     rbx, [r13+50h]
0x1800a9008  mov     rbx, [rbx]
0x1800a900b  cmp     rbx, [r13+50h]
0x1800a900f  jz      short loc_1800A901F
0x1800a9011  mov     rdx, rsi; struct WWAN_PROFILE *
0x1800a9014  mov     rcx, [rbx+20h]; this
0x1800a9018  call    ?OnProfileAdded@ProfileHandler@@QEAAXAEAUWWAN_PROFILE@@@Z; ProfileHandler::OnProfileAdded(WWAN_PROFILE &)
0x1800a901d  jmp     short loc_1800A9008
0x1800a901f  mov     eax, r14d
0x1800a9022  mov     rcx, [rbp+3120h+var_40]
0x1800a9029  xor     rcx, rsp; StackCookie
0x1800a902c  call    __security_check_cookie
0x1800a9031  mov     rbx, [rsp+3220h+arg_10]
0x1800a9039  add     rsp, 31F0h
0x1800a9040  pop     r15
0x1800a9042  pop     r14
0x1800a9044  pop     r13
0x1800a9046  pop     r12
0x1800a9048  pop     rdi
0x1800a9049  pop     rsi
0x1800a904a  pop     rbp
0x1800a904b  retn
```
