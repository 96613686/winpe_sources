# CDeviceDropTarget::_GetDevice(CProgressUI *)

- ea: `0x1800716fc`
- end: `0x180071985`
- name: `?_GetDevice@CDeviceDropTarget@@IEAAJPEAVCProgressUI@@@Z`
- size: `649`
- prototype: `int(CDeviceDropTarget *__hidden this, struct CProgressUI *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180070fe8`

## callees

- `0x18000c180`
- `0x1800285c8`
- `0x180028ea8`
- `0x18002ff5c`
- `0x180035590`
- `0x180054524`
- `0x1800545c8`
- `0x18006260c`
- `0x180070c88`
- `0x1800716fc`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180071907`
- `KERNEL32!Sleep` at `0x180071907`
- `KERNEL32!GetCurrentThreadId` at `0x180071843`
- `KERNEL32!GetCurrentThreadId` at `0x1800718b7`
- `KERNEL32!GetCurrentThreadId` at `0x180071843`
- `KERNEL32!GetCurrentThreadId` at `0x1800718b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDeviceDropTarget::_GetDevice(CDeviceDropTarget *this, struct CProgressUI *a2)
{
  int StringProperty; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r9
  _QWORD *v8; // rcx
  const struct _GUID *v9; // rdx
  int v10; // ebx
  DWORD v11; // eax
  int v12; // r15d
  int v13; // esi
  int IsDelegateFolder; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *v18; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v19[264]; // [rsp+40h] [rbp-C0h] BYREF

  v17 = 0;
  v18 = 0;
  StringProperty = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 5))(
                     *((_QWORD *)this + 5),
                     &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                     &v17);
  if ( StringProperty < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 5))(
             *((_QWORD *)this + 5),
             &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
             &v17);
      v6 = 82;
LABEL_5:
      v7 = v5;
      v8 = WPP_GLOBAL_Control;
LABEL_6:
      WPP_SF_d(v8[2], v6, WPP_bc9ae68cc7be344fb7a23f4b180ed5c8_Traceguids, v7);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  StringProperty = GetStringProperty(v17, *((_QWORD *)this + 7), &PKEY_WPDNSE_PnPDevicePath, v19, 260);
  if ( StringProperty >= 0 )
  {
    if ( a2 )
    {
      v12 = 0;
      v13 = 0;
      while ( !*((_DWORD *)a2 + 26) )
      {
        IsDelegateFolder = CBaseFolder::_IsDelegateFolder(*((CBaseFolder **)this + 5));
        CurrentThreadId = GetCurrentThreadId();
        StringProperty = CDeviceCache::s_BindToPortableDevice(
                           v19,
                           CurrentThreadId,
                           0,
                           0,
                           IsDelegateFolder,
                           (struct IPortableDevice **)&v18);
        if ( StringProperty != -2147024726 )
          goto LABEL_26;
        if ( !v12 )
        {
          v12 = 1;
          v13 = 1;
          CProgressUI::_StartMarquee(a2);
        }
        if ( *((_DWORD *)a2 + 26) )
          break;
        Sleep(0x5DCu);
      }
      StringProperty = -2147023673;
LABEL_26:
      if ( v13 )
        CProgressUI::_StopMarquee(a2);
      if ( *((_DWORD *)a2 + 26) )
      {
        StringProperty = -2147023673;
        goto LABEL_14;
      }
    }
    else
    {
      v10 = CBaseFolder::_IsDelegateFolder(*((CBaseFolder **)this + 5));
      v11 = GetCurrentThreadId();
      StringProperty = CDeviceCache::s_BindToPortableDevice(v19, v11, 0, 0, v10, (struct IPortableDevice **)&v18);
    }
    if ( StringProperty >= 0 )
    {
      CGITPtr::Set((CDeviceDropTarget *)((char *)this + 80), v9, v18);
      goto LABEL_31;
    }
LABEL_14:
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 84;
      v7 = (unsigned int)StringProperty;
      goto LABEL_6;
    }
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v5 = GetStringProperty(v17, *((_QWORD *)this + 7), &PKEY_WPDNSE_PnPDevicePath, v19, 260);
    v6 = 83;
    goto LABEL_5;
  }
LABEL_31:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  return (unsigned int)StringProperty;
}

```

## disassembly

```asm
0x1800716fc  mov     [rsp-8+arg_10], rbx
0x180071701  push    rbp
0x180071702  push    rsi
0x180071703  push    rdi
0x180071704  push    r14
0x180071706  push    r15
0x180071708  lea     rbp, [rsp-160h]
0x180071710  sub     rsp, 260h
0x180071717  mov     rax, cs:__security_cookie
0x18007171e  xor     rax, rsp
0x180071721  mov     [rbp+180h+var_30], rax
0x180071728  mov     rdi, rdx
0x18007172b  mov     r14, rcx
0x18007172e  mov     [rsp+280h+var_250], 0
0x180071737  mov     [rsp+280h+var_248], 0
0x180071740  mov     rcx, [rcx+28h]
0x180071744  mov     rax, [rcx]
0x180071747  lea     r8, [rsp+280h+var_250]
0x18007174c  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x180071753  mov     rax, [rax]
0x180071756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007175b  mov     ebx, eax
0x18007175d  test    eax, eax
0x18007175f  jns     short loc_1800717C1
0x180071761  lea     rax, WPP_GLOBAL_Control
0x180071768  mov     rcx, cs:WPP_GLOBAL_Control
0x18007176f  cmp     rcx, rax
0x180071772  jz      loc_180071948
0x180071778  test    byte ptr [rcx+1Ch], 2
0x18007177c  jz      loc_180071948
0x180071782  mov     rcx, [r14+28h]
0x180071786  mov     rax, [rcx]
0x180071789  lea     r8, [rsp+280h+var_250]
0x18007178e  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x180071795  mov     rax, [rax]
0x180071798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007179d  mov     edx, 52h ; 'R'
0x1800717a2  mov     r9d, eax
0x1800717a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800717ac  lea     r8, WPP_bc9ae68cc7be344fb7a23f4b180ed5c8_Traceguids
0x1800717b3  mov     rcx, [rcx+10h]
0x1800717b7  call    WPP_SF_d
0x1800717bc  jmp     loc_180071948
0x1800717c1  mov     esi, 104h
0x1800717c6  mov     [rsp+280h+var_260], esi
0x1800717ca  lea     r9, [rsp+280h+var_240]
0x1800717cf  lea     r8, PKEY_WPDNSE_PnPDevicePath
0x1800717d6  mov     rdx, [r14+38h]
0x1800717da  mov     rcx, [rsp+280h+var_250]
0x1800717df  call    GetStringProperty
0x1800717e4  mov     ebx, eax
0x1800717e6  test    eax, eax
0x1800717e8  jns     short loc_180071833
0x1800717ea  lea     rax, WPP_GLOBAL_Control
0x1800717f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800717f8  cmp     rcx, rax
0x1800717fb  jz      loc_180071948
0x180071801  test    byte ptr [rcx+1Ch], 2
0x180071805  jz      loc_180071948
0x18007180b  mov     [rsp+280h+var_260], esi
0x18007180f  lea     r9, [rsp+280h+var_240]
0x180071814  lea     r8, PKEY_WPDNSE_PnPDevicePath
0x18007181b  mov     rdx, [r14+38h]
0x18007181f  mov     rcx, [rsp+280h+var_250]
0x180071824  call    GetStringProperty
0x180071829  mov     edx, 53h ; 'S'
0x18007182e  jmp     loc_1800717A2
0x180071833  test    rdi, rdi
0x180071836  jnz     short loc_1800718A1
0x180071838  mov     rcx, [r14+28h]; this
0x18007183c  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x180071841  mov     ebx, eax
0x180071843  call    cs:__imp_GetCurrentThreadId
0x180071849  lea     rcx, [rsp+280h+var_248]
0x18007184e  mov     [rsp+280h+var_258], rcx; struct IPortableDevice **
0x180071853  mov     [rsp+280h+var_260], ebx; int
0x180071857  xor     r9d, r9d; struct _ITEMIDLIST *
0x18007185a  xor     r8d, r8d; struct _ITEMIDLIST *
0x18007185d  mov     edx, eax; unsigned int
0x18007185f  lea     rcx, [rsp+280h+var_240]; unsigned __int16 *
0x180071864  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x180071869  mov     ebx, eax
0x18007186b  test    ebx, ebx
0x18007186d  jns     loc_180071939
0x180071873  lea     rax, WPP_GLOBAL_Control
0x18007187a  mov     rcx, cs:WPP_GLOBAL_Control
0x180071881  cmp     rcx, rax
0x180071884  jz      loc_180071948
0x18007188a  test    byte ptr [rcx+1Ch], 2
0x18007188e  jz      loc_180071948
0x180071894  mov     edx, 54h ; 'T'
0x180071899  mov     r9d, ebx
0x18007189c  jmp     loc_1800717AC
0x1800718a1  xor     r15d, r15d
0x1800718a4  xor     esi, esi
0x1800718a6  cmp     dword ptr [rdi+68h], 0
0x1800718aa  jnz     short loc_180071914
0x1800718ac  mov     rcx, [r14+28h]; this
0x1800718b0  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x1800718b5  mov     ebx, eax
0x1800718b7  call    cs:__imp_GetCurrentThreadId
0x1800718bd  lea     rcx, [rsp+280h+var_248]
0x1800718c2  mov     [rsp+280h+var_258], rcx; struct IPortableDevice **
0x1800718c7  mov     [rsp+280h+var_260], ebx; int
0x1800718cb  xor     r9d, r9d; struct _ITEMIDLIST *
0x1800718ce  xor     r8d, r8d; struct _ITEMIDLIST *
0x1800718d1  mov     edx, eax; unsigned int
0x1800718d3  lea     rcx, [rsp+280h+var_240]; unsigned __int16 *
0x1800718d8  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x1800718dd  mov     ebx, eax
0x1800718df  cmp     eax, 800700AAh
0x1800718e4  jnz     short loc_180071919
0x1800718e6  test    r15d, r15d
0x1800718e9  jnz     short loc_1800718FC
0x1800718eb  lea     eax, [r15+1]
0x1800718ef  mov     r15d, eax
0x1800718f2  mov     esi, eax
0x1800718f4  mov     rcx, rdi; this
0x1800718f7  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x1800718fc  cmp     dword ptr [rdi+68h], 0
0x180071900  jnz     short loc_180071914
0x180071902  mov     ecx, 5DCh; dwMilliseconds
0x180071907  call    cs:__imp_Sleep
0x18007190d  test    r15d, r15d
0x180071910  jz      short loc_180071919
0x180071912  jmp     short loc_1800718A6
0x180071914  mov     ebx, 800704C7h
0x180071919  test    esi, esi
0x18007191b  jz      short loc_180071925
0x18007191d  mov     rcx, rdi; this
0x180071920  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180071925  cmp     dword ptr [rdi+68h], 0
0x180071929  jz      loc_18007186B
0x18007192f  mov     ebx, 800704C7h
0x180071934  jmp     loc_180071873
0x180071939  lea     rcx, [r14+50h]; this
0x18007193d  mov     r8, [rsp+280h+var_248]; struct IUnknown *
0x180071942  call    ?Set@CGITPtr@@QEAAXAEBU_GUID@@PEAUIUnknown@@@Z; CGITPtr::Set(_GUID const &,IUnknown *)
0x180071947  nop
0x180071948  lea     rcx, [rsp+280h+var_248]
0x18007194d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180071952  nop
0x180071953  lea     rcx, [rsp+280h+var_250]
0x180071958  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007195d  mov     eax, ebx
0x18007195f  mov     rcx, [rbp+180h+var_30]
0x180071966  xor     rcx, rsp; StackCookie
0x180071969  call    __security_check_cookie
0x18007196e  mov     rbx, [rsp+280h+arg_10]
0x180071976  add     rsp, 260h
0x18007197d  pop     r15
0x18007197f  pop     r14
0x180071981  pop     rdi
0x180071982  pop     rsi
0x180071983  pop     rbp
0x180071984  retn
```
