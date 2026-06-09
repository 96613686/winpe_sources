# CShellLink::_DecodeSpecialFolder(void)

- ea: `0x180104bf0`
- end: `0x180104f1f`
- name: `?_DecodeSpecialFolder@CShellLink@@AEAAJXZ`
- size: `815`
- prototype: `__int64 __fastcall(CShellLink *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180251bf4`
- `0x180626074`

## callees

- `0x1800376a0`
- `0x180038f50`
- `0x180045230`
- `0x1800abf10`
- `0x1800b1a00`
- `0x1800c4ae0`
- `0x180104bf0`
- `0x180104f28`
- `0x180105184`
- `0x1801051e0`
- `0x1801052c0`
- `0x180183160`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104c6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104d0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104def`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104e08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104e17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104e30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104e75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104e91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104ec1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104c6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104d0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104def`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104e08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104e17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104e30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104e75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104e91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104ec1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104edd`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFindDataBlock` at `0x180104c28`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFindDataBlock` at `0x180104c48`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFindDataBlock` at `0x180104c28`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFindDataBlock` at `0x180104c48`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CShellLink::_DecodeSpecialFolder(CShellLink *this)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rdi
  void *v6; // rcx
  bool v8; // si
  void *v9; // rcx
  unsigned int v10; // eax
  unsigned __int16 *v11; // r8
  unsigned __int16 *v12; // rdx
  unsigned __int16 *i; // rcx
  __int64 v14; // rax
  bool v15; // zf
  void *v16; // rdi
  int v17; // eax
  unsigned int v18; // esi
  int v19; // eax
  struct _ITEMIDLIST_ABSOLUTE *v20; // rbp
  LPITEMIDLIST v21; // rsi
  void *v22; // rcx
  void *v23; // rcx
  LPITEMIDLIST v24; // rax
  LPVOID *p_pv; // [rsp+20h] [rbp-48h]
  struct _ITEMIDLIST_ABSOLUTE *TokenHandle; // [rsp+28h] [rbp-40h] BYREF
  char v27; // [rsp+30h] [rbp-38h]
  void *v28; // [rsp+38h] [rbp-30h]
  LPVOID pv; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  pv = 0;
  v2 = SHFindDataBlock(*((_QWORD *)this + 57), 2684354571LL);
  v3 = v2;
  if ( v2 )
  {
    if ( !(unsigned int)CShellLink::_ShouldDecodeSpecialFolder(this, (const struct _GUID *)(v2 + 8)) )
      goto LABEL_3;
    p_pv = &pv;
    TokenHandle = 0;
    v27 = 1;
    v8 = (int)SHGetKnownFolderIDList_Internal(
                (struct _GUID *)(v3 + 8),
                (*((_DWORD *)this + 124) & 0x400000 | 0x1000000u) >> 10,
                0,
                &TokenHandle) >= 0;
    if ( v27 )
    {
      v9 = pv;
      pv = TokenHandle;
      if ( v9 )
        CoTaskMemFree(v9);
    }
    if ( !v8 )
      goto LABEL_3;
    v10 = *(_DWORD *)(v3 + 24);
LABEL_12:
    v11 = (unsigned __int16 *)*((_QWORD *)this + 47);
    v12 = (unsigned __int16 *)((char *)v11 + v10);
    for ( i = v11; i; i = (unsigned __int16 *)((char *)i + v14) )
    {
      v14 = *i;
      if ( !(_WORD)v14 )
        break;
      v15 = i == v12;
      if ( i >= v12 )
        goto LABEL_18;
    }
    v15 = i == v12;
LABEL_18:
    if ( !v15 )
      goto LABEL_3;
    v16 = (void *)ILCloneCB(*((void **)this + 47), (unsigned int)((_DWORD)v12 - (_DWORD)v11));
    v28 = v16;
    if ( !v16 )
      goto LABEL_26;
    v17 = ILValidateInnerPidlIfRooted(*((const struct _ITEMIDLIST_ABSOLUTE **)this + 47));
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCDD,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\shelllnk.cpp",
        (const char *)(unsigned int)v17,
        (int)p_pv);
      CoTaskMemFree(v16);
      v22 = pv;
      pv = 0;
      if ( v22 )
        CoTaskMemFree(v22);
    }
    else
    {
      v19 = ILValidateInnerPidlIfRooted((const struct _ITEMIDLIST_ABSOLUTE *)v16);
      v18 = v19;
      if ( v19 >= 0 )
      {
        v20 = TranslateAliasWithEvent(
                0,
                *((const struct _ITEMIDLIST_ABSOLUTE **)this + 47),
                (const struct _ITEMIDLIST_ABSOLUTE *)v16,
                (const struct _ITEMIDLIST_ABSOLUTE *)pv);
        if ( v20 )
        {
          v21 = ILClone(*((LPCITEMIDLIST *)this + 47));
          if ( (int)CShellLink::_SetPIDLPath(this, v20, 0, 2) < 0 )
          {
            *((_DWORD *)this + 154) = 0;
            Pidl_Set((char *)this + 384, 0);
          }
          else
          {
            *((_DWORD *)this + 154) = 1;
            CoTaskMemFree(*((LPVOID *)this + 48));
            *((_QWORD *)this + 48) = v21;
            v21 = 0;
          }
          CoTaskMemFree(v21);
          CoTaskMemFree(v20);
        }
LABEL_26:
        if ( v16 )
          CoTaskMemFree(v16);
        goto LABEL_3;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCDE,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\shelllnk.cpp",
        (const char *)(unsigned int)v19,
        (int)p_pv);
      CoTaskMemFree(v16);
      v23 = pv;
      pv = 0;
      if ( v23 )
      {
        CoTaskMemFree(v23);
        return v18;
      }
    }
    return v18;
  }
  v4 = SHFindDataBlock(*((_QWORD *)this + 57), 2684354565LL);
  v5 = v4;
  if ( v4 )
  {
    v24 = SHCloneSpecialIDList(0, *(_DWORD *)(v4 + 8), 0);
    wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &pv,
      v24);
    if ( pv )
    {
      v10 = *(_DWORD *)(v5 + 12);
      goto LABEL_12;
    }
  }
LABEL_3:
  v6 = pv;
  pv = 0;
  if ( v6 )
    CoTaskMemFree(v6);
  return 0;
}

```

## disassembly

```asm
0x180104bf0  mov     [rsp+arg_8], rbx
0x180104bf5  mov     [rsp+arg_10], rbp
0x180104bfa  push    rsi
0x180104bfb  push    rdi
0x180104bfc  push    r14
0x180104bfe  sub     rsp, 50h
0x180104c02  mov     rax, cs:__security_cookie
0x180104c09  xor     rax, rsp
0x180104c0c  mov     [rsp+68h+var_20], rax
0x180104c11  mov     rbx, rcx
0x180104c14  xor     r14d, r14d
0x180104c17  mov     [rsp+68h+pv], r14
0x180104c1c  mov     edx, 0A000000Bh
0x180104c21  mov     rcx, [rcx+1C8h]
0x180104c28  call    cs:__imp_SHFindDataBlock
0x180104c2f  nop     dword ptr [rax+rax+00h]
0x180104c34  mov     rdi, rax
0x180104c37  test    rax, rax
0x180104c3a  jnz     short loc_180104CA1
0x180104c3c  mov     edx, 0A0000005h
0x180104c41  mov     rcx, [rbx+1C8h]
0x180104c48  call    cs:__imp_SHFindDataBlock
0x180104c4f  nop     dword ptr [rax+rax+00h]
0x180104c54  mov     rdi, rax
0x180104c57  test    rax, rax
0x180104c5a  jnz     loc_180104EF0
0x180104c60  mov     rcx, [rsp+68h+pv]; pv
0x180104c65  mov     [rsp+68h+pv], r14
0x180104c6a  test    rcx, rcx
0x180104c6d  jz      short loc_180104C7B
0x180104c6f  call    cs:__imp_CoTaskMemFree
0x180104c76  nop     dword ptr [rax+rax+00h]
0x180104c7b  xor     eax, eax
0x180104c7d  mov     rcx, [rsp+68h+var_20]
0x180104c82  xor     rcx, rsp; StackCookie
0x180104c85  call    __security_check_cookie
0x180104c8a  mov     rbx, [rsp+68h+arg_8]
0x180104c8f  mov     rbp, [rsp+68h+arg_10]
0x180104c97  add     rsp, 50h
0x180104c9b  pop     r14
0x180104c9d  pop     rdi
0x180104c9e  pop     rsi
0x180104c9f  retn
0x180104ca1  lea     rdx, [rax+8]; struct _GUID *
0x180104ca5  mov     rcx, rbx; this
0x180104ca8  call    ?_ShouldDecodeSpecialFolder@CShellLink@@AEAAHAEBU_GUID@@@Z; CShellLink::_ShouldDecodeSpecialFolder(_GUID const &)
0x180104cad  test    eax, eax
0x180104caf  jz      short loc_180104C60
0x180104cb1  lea     rax, [rsp+68h+pv]
0x180104cb6  mov     qword ptr [rsp+68h+var_48], rax; int
0x180104cbb  mov     [rsp+68h+TokenHandle], r14
0x180104cc0  mov     [rsp+68h+var_38], 1
0x180104cc5  mov     edx, [rbx+1F0h]
0x180104ccb  and     edx, 400000h
0x180104cd1  bts     edx, 18h
0x180104cd5  shr     edx, 0Ah; unsigned int
0x180104cd8  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x180104cdd  xor     r8d, r8d; void *
0x180104ce0  lea     rcx, [rdi+8]; struct _GUID *
0x180104ce4  call    SHGetKnownFolderIDList_Internal
0x180104ce9  mov     esi, eax
0x180104ceb  shr     esi, 1Fh
0x180104cee  xor     sil, 1
0x180104cf2  cmp     [rsp+68h+var_38], 0
0x180104cf7  jz      short loc_180104D1A
0x180104cf9  mov     r8, qword ptr [rsp+68h+var_48]
0x180104cfe  mov     rcx, [r8]; pv
0x180104d01  mov     rdx, [rsp+68h+TokenHandle]
0x180104d06  mov     [r8], rdx
0x180104d09  test    rcx, rcx
0x180104d0c  jz      short loc_180104D1A
0x180104d0e  call    cs:__imp_CoTaskMemFree
0x180104d15  nop     dword ptr [rax+rax+00h]
0x180104d1a  test    sil, sil
0x180104d1d  jz      loc_180104C60
0x180104d23  mov     eax, [rdi+18h]
0x180104d26  mov     r8, [rbx+178h]
0x180104d2d  mov     edx, eax
0x180104d2f  add     rdx, r8
0x180104d32  mov     rcx, r8
0x180104d35  test    rcx, rcx
0x180104d38  jz      short loc_180104D4C
0x180104d3a  movzx   eax, word ptr [rcx]
0x180104d3d  test    ax, ax
0x180104d40  jz      short loc_180104D4C
0x180104d42  cmp     rcx, rdx
0x180104d45  jnb     short loc_180104D4F
0x180104d47  add     rcx, rax
0x180104d4a  jmp     short loc_180104D35
0x180104d4c  cmp     rcx, rdx
0x180104d4f  jnz     loc_180104C60
0x180104d55  sub     edx, r8d; Size
0x180104d58  mov     rcx, r8; Src
0x180104d5b  call    ILCloneCB
0x180104d60  mov     rdi, rax
0x180104d63  mov     [rsp+68h+var_30], rax
0x180104d68  test    rax, rax
0x180104d6b  jz      loc_180104E24
0x180104d71  mov     rcx, [rbx+178h]; struct _ITEMIDLIST_ABSOLUTE *
0x180104d78  call    ?ILValidateInnerPidlIfRooted@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; ILValidateInnerPidlIfRooted(_ITEMIDLIST_ABSOLUTE const *)
0x180104d7d  mov     esi, eax
0x180104d7f  test    eax, eax
0x180104d81  js      loc_180104E58
0x180104d87  mov     rcx, rdi; struct _ITEMIDLIST_ABSOLUTE *
0x180104d8a  call    ?ILValidateInnerPidlIfRooted@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; ILValidateInnerPidlIfRooted(_ITEMIDLIST_ABSOLUTE const *)
0x180104d8f  mov     esi, eax
0x180104d91  test    eax, eax
0x180104d93  js      loc_180104EA4
0x180104d99  mov     r9, [rsp+68h+pv]; struct _ITEMIDLIST_ABSOLUTE *
0x180104d9e  mov     r8, rdi; struct _ITEMIDLIST_ABSOLUTE *
0x180104da1  mov     rdx, [rbx+178h]; struct _ITEMIDLIST_ABSOLUTE *
0x180104da8  xor     ecx, ecx; int
0x180104daa  call    ?TranslateAliasWithEvent@@YAPEAU_ITEMIDLIST_ABSOLUTE@@JPEBU1@00@Z; TranslateAliasWithEvent(long,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)
0x180104daf  mov     rbp, rax
0x180104db2  test    rax, rax
0x180104db5  jz      short loc_180104E24
0x180104db7  mov     rcx, [rbx+178h]; pidl
0x180104dbe  call    ILClone
0x180104dc3  mov     rsi, rax
0x180104dc6  mov     r9d, 2
0x180104dcc  xor     r8d, r8d
0x180104dcf  mov     rdx, rbp
0x180104dd2  mov     rcx, rbx
0x180104dd5  call    ?_SetPIDLPath@CShellLink@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBGW4SLSPPFLAGS@@@Z; CShellLink::_SetPIDLPath(_ITEMIDLIST_ABSOLUTE const *,ushort const *,SLSPPFLAGS)
0x180104dda  test    eax, eax
0x180104ddc  js      short loc_180104E41
0x180104dde  mov     dword ptr [rbx+268h], 1
0x180104de8  mov     rcx, [rbx+180h]; pv
0x180104def  call    cs:__imp_CoTaskMemFree
0x180104df6  nop     dword ptr [rax+rax+00h]
0x180104dfb  mov     [rbx+180h], rsi
0x180104e02  mov     rsi, r14
0x180104e05  mov     rcx, rsi; pv
0x180104e08  call    cs:__imp_CoTaskMemFree
0x180104e0f  nop     dword ptr [rax+rax+00h]
0x180104e14  mov     rcx, rbp; pv
0x180104e17  call    cs:__imp_CoTaskMemFree
0x180104e1e  nop     dword ptr [rax+rax+00h]
0x180104e23  nop
0x180104e24  test    rdi, rdi
0x180104e27  jz      loc_180104C60
0x180104e2d  mov     rcx, rdi; pv
0x180104e30  call    cs:__imp_CoTaskMemFree
0x180104e37  nop     dword ptr [rax+rax+00h]
0x180104e3c  jmp     loc_180104C60
0x180104e41  mov     [rbx+268h], r14d
0x180104e48  lea     rcx, [rbx+180h]
0x180104e4f  xor     edx, edx
0x180104e51  call    Pidl_Set
0x180104e56  jmp     short loc_180104E05
0x180104e58  mov     rcx, [rsp+68h]; this
0x180104e5d  mov     r9d, esi; char *
0x180104e60  lea     r8, aOnecoreuapShel_87; "onecoreuap\\shell\\windows.storage\\she"...
0x180104e67  mov     edx, 0CDDh; void *
0x180104e6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104e71  nop
0x180104e72  mov     rcx, rdi; pv
0x180104e75  call    cs:__imp_CoTaskMemFree
0x180104e7c  nop     dword ptr [rax+rax+00h]
0x180104e81  nop
0x180104e82  mov     rcx, [rsp+68h+pv]; pv
0x180104e87  mov     [rsp+68h+pv], r14
0x180104e8c  test    rcx, rcx
0x180104e8f  jz      short loc_180104E9D
0x180104e91  call    cs:__imp_CoTaskMemFree
0x180104e98  nop     dword ptr [rax+rax+00h]
0x180104e9d  mov     eax, esi
0x180104e9f  jmp     loc_180104C7D
0x180104ea4  mov     rcx, [rsp+68h]; this
0x180104ea9  mov     r9d, esi; char *
0x180104eac  lea     r8, aOnecoreuapShel_87; "onecoreuap\\shell\\windows.storage\\she"...
0x180104eb3  mov     edx, 0CDEh; void *
0x180104eb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104ebd  nop
0x180104ebe  mov     rcx, rdi; pv
0x180104ec1  call    cs:__imp_CoTaskMemFree
0x180104ec8  nop     dword ptr [rax+rax+00h]
0x180104ecd  nop
0x180104ece  mov     rcx, [rsp+68h+pv]; pv
0x180104ed3  mov     [rsp+68h+pv], r14
0x180104ed8  test    rcx, rcx
0x180104edb  jz      short loc_180104E9D
0x180104edd  call    cs:__imp_CoTaskMemFree
0x180104ee4  nop     dword ptr [rax+rax+00h]
0x180104ee9  mov     eax, esi
0x180104eeb  jmp     loc_180104C7D
0x180104ef0  xor     r8d, r8d; fCreate
0x180104ef3  mov     edx, [rax+8]; csidl
0x180104ef6  xor     ecx, ecx; hwnd
0x180104ef8  call    SHCloneSpecialIDList
0x180104efd  mov     rdx, rax
0x180104f00  lea     rcx, [rsp+68h+pv]
0x180104f05  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x180104f0a  cmp     [rsp+68h+pv], 0
0x180104f10  jz      loc_180104C60
0x180104f16  mov     eax, [rdi+0Ch]
0x180104f19  jmp     loc_180104D26
```
