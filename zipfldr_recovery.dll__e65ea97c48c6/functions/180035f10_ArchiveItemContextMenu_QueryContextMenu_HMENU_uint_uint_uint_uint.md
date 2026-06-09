# ArchiveItemContextMenu::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x180035f10`
- end: `0x180036090`
- name: `?QueryContextMenu@ArchiveItemContextMenu@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `384`
- prototype: `int(ArchiveItemContextMenu *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180033aa8`
- `0x180035f10`
- `0x180036098`
- `0x180059ccc`

## import_xrefs

- `SHELL32!__imp_Shell_MergeMenus` at `0x180036013`
- `SHELL32!__imp_Shell_MergeMenus` at `0x180036013`
- `USER32!SetMenuDefaultItem` at `0x180036063`
- `USER32!SetMenuDefaultItem` at `0x180036063`
- `USER32!LoadMenuW` at `0x180035f5c`
- `USER32!LoadMenuW` at `0x180035f5c`
- `USER32!GetSubMenu` at `0x180035f8c`
- `USER32!GetSubMenu` at `0x180035f8c`
- `USER32!RemoveMenu` at `0x180035faf`
- `USER32!RemoveMenu` at `0x180035faf`
- `USER32!DeleteMenu` at `0x180036054`
- `USER32!DeleteMenu` at `0x180036054`

## pseudocode

```c
__int64 __fastcall ArchiveItemContextMenu::QueryContextMenu(
        ArchiveItemContextMenu *this,
        HMENU a2,
        UINT a3,
        UINT a4,
        UINT uIDAdjustMax,
        unsigned int a6)
{
  HMENU MenuW; // rax
  const char *v12; // r9
  HMENU v13; // rbx
  unsigned int LastError; // ebx
  HMENU SubMenu; // rdi
  const char *v16; // r9
  __int64 v17; // rdx
  UINT v18; // ebx
  __int64 v19; // rcx
  bool v20; // zf
  HMENU v21; // rcx
  UINT v22; // edx
  HMENU v23; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v24[8]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( (a6 & 2) != 0 )
    return 2147500037LL;
  MenuW = LoadMenuW(&_ImageBase, (LPCWSTR)((a6 & 0x10000 | 0x6A0000uLL) >> 16));
  v13 = MenuW;
  v24[0] = MenuW;
  if ( MenuW )
  {
    SubMenu = GetSubMenu(MenuW, 0);
    v23 = SubMenu;
    if ( SubMenu )
    {
      if ( RemoveMenu(v13, 0, 0x400u) )
      {
        wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>::reset(
          v24,
          0);
        v18 = Shell_MergeMenus(a2, SubMenu, a3, a4, uIDAdjustMax, 3u);
        wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>::reset(
          &v23,
          0);
        v19 = *((_QWORD *)this + 4);
        if ( v19 != *((_QWORD *)this + 5) )
        {
          v20 = (*(_BYTE *)(*(_QWORD *)v19 + 4LL) & 0x10) == 0;
          v21 = a2;
          if ( v20 )
          {
            DeleteMenu(a2, a4 + 103, 0);
            v22 = a4 + 102;
            v21 = a2;
          }
          else
          {
            v22 = ((a6 & 4 | 0x198) >> 2) + a4;
          }
          SetMenuDefaultItem(v21, v22, 0);
        }
        wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>(&v23);
        wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>(v24);
        return v18 - a4;
      }
      v17 = 57;
    }
    else
    {
      v17 = 56;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v17,
                  (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
                  v16);
    wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>(&v23);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x35,
                  (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
                  v12);
  }
  wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>(v24);
  return LastError;
}

```

## disassembly

```asm
0x180035f10  push    rbx
0x180035f12  push    rbp
0x180035f13  push    rsi
0x180035f14  push    rdi
0x180035f15  push    r12
0x180035f17  push    r14
0x180035f19  push    r15
0x180035f1b  sub     rsp, 40h
0x180035f1f  mov     ebp, r9d
0x180035f22  mov     r12d, r8d
0x180035f25  mov     r14, rdx
0x180035f28  mov     r15, rcx
0x180035f2b  mov     esi, [rsp+78h+arg_28]
0x180035f32  test    sil, 2
0x180035f36  jz      short loc_180035F42
0x180035f38  mov     eax, 80004005h
0x180035f3d  jmp     loc_180036081
0x180035f42  mov     edx, esi
0x180035f44  and     edx, 10000h
0x180035f4a  or      rdx, 6A0000h
0x180035f51  shr     rdx, 10h; lpMenuName
0x180035f55  lea     rcx, __ImageBase; hInstance
0x180035f5c  call    cs:__imp_LoadMenuW
0x180035f62  mov     rbx, rax
0x180035f65  mov     [rsp+78h+var_40], rax
0x180035f6a  test    rax, rax
0x180035f6d  jnz     short loc_180035F87
0x180035f6f  mov     rcx, [rsp+78h]; this
0x180035f74  lea     r8, aShellExtZipArc_12; "shell\\ext\\zip\\archive\\archiveitemco"...
0x180035f7b  lea     edx, [rax+35h]; void *
0x180035f7e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035f83  mov     ebx, eax
0x180035f85  jmp     short loc_180035FD9
0x180035f87  xor     edx, edx; nPos
0x180035f89  mov     rcx, rbx; hMenu
0x180035f8c  call    cs:__imp_GetSubMenu
0x180035f92  mov     rdi, rax
0x180035f95  mov     [rsp+78h+var_48], rax
0x180035f9a  test    rax, rax
0x180035f9d  jnz     short loc_180035FA4
0x180035f9f  lea     edx, [rax+38h]
0x180035fa2  jmp     short loc_180035FBC
0x180035fa4  xor     edx, edx; uPosition
0x180035fa6  mov     r8d, 400h; uFlags
0x180035fac  mov     rcx, rbx; hMenu
0x180035faf  call    cs:__imp_RemoveMenu
0x180035fb5  test    eax, eax
0x180035fb7  jnz     short loc_180035FE8
0x180035fb9  lea     edx, [rax+39h]; void *
0x180035fbc  lea     r8, aShellExtZipArc_12; "shell\\ext\\zip\\archive\\archiveitemco"...
0x180035fc3  mov     rcx, [rsp+78h]; this
0x180035fc8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035fcd  mov     ebx, eax
0x180035fcf  lea     rcx, [rsp+78h+var_48]
0x180035fd4  call    ??1?$unique_storage@U?$resource_policy@PEAUHMENU__@@P6AHPEAU1@@Z$1?DestroyMenu@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>(void)
0x180035fd9  lea     rcx, [rsp+78h+var_40]
0x180035fde  call    ??1?$unique_storage@U?$resource_policy@PEAUHMENU__@@P6AHPEAU1@@Z$1?DestroyMenu@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>(void)
0x180035fe3  jmp     loc_18003607F
0x180035fe8  xor     edx, edx
0x180035fea  lea     rcx, [rsp+78h+var_40]
0x180035fef  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHMENU__@@P6AHPEAU1@@Z$1?DestroyMenu@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHMENU__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>::reset(HMENU__ *)
0x180035ff4  mov     [rsp+78h+uFlags], 3; uFlags
0x180035ffc  mov     eax, [rsp+78h+arg_20]
0x180036003  mov     [rsp+78h+uIDAdjustMax], eax; uIDAdjustMax
0x180036007  mov     r9d, ebp; uIDAdjust
0x18003600a  mov     r8d, r12d; uInsert
0x18003600d  mov     rdx, rdi; hmSrc
0x180036010  mov     rcx, r14; hmDst
0x180036013  call    cs:__imp_Shell_MergeMenus
0x180036019  mov     ebx, eax
0x18003601b  xor     edx, edx
0x18003601d  lea     rcx, [rsp+78h+var_48]
0x180036022  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHMENU__@@P6AHPEAU1@@Z$1?DestroyMenu@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHMENU__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>::reset(HMENU__ *)
0x180036027  mov     rcx, [r15+20h]
0x18003602b  cmp     rcx, [r15+28h]
0x18003602f  jz      short loc_180036069
0x180036031  mov     rcx, [rcx]
0x180036034  xor     r8d, r8d; uFlags
0x180036037  test    byte ptr [rcx+4], 10h
0x18003603b  mov     rcx, r14; hMenu
0x18003603e  jz      short loc_180036051
0x180036040  and     esi, 4
0x180036043  or      esi, 198h
0x180036049  shr     esi, 2
0x18003604c  lea     edx, [rsi+rbp]
0x18003604f  jmp     short loc_180036063
0x180036051  lea     edx, [rbp+67h]; uPosition
0x180036054  call    cs:__imp_DeleteMenu
0x18003605a  lea     edx, [rbp+66h]; uItem
0x18003605d  xor     r8d, r8d; fByPos
0x180036060  mov     rcx, r14; hMenu
0x180036063  call    cs:__imp_SetMenuDefaultItem
0x180036069  lea     rcx, [rsp+78h+var_48]
0x18003606e  call    ??1?$unique_storage@U?$resource_policy@PEAUHMENU__@@P6AHPEAU1@@Z$1?DestroyMenu@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>(void)
0x180036073  lea     rcx, [rsp+78h+var_40]
0x180036078  call    ??1?$unique_storage@U?$resource_policy@PEAUHMENU__@@P6AHPEAU1@@Z$1?DestroyMenu@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>(void)
0x18003607d  sub     ebx, ebp
0x18003607f  mov     eax, ebx
0x180036081  add     rsp, 40h
0x180036085  pop     r15
0x180036087  pop     r14
0x180036089  pop     r12
0x18003608b  pop     rdi
0x18003608c  pop     rsi
0x18003608d  pop     rbp
0x18003608e  pop     rbx
0x18003608f  retn
```
