# CShareMediaCplElementProvider_CreateInstance

- ea: `0x180003a20`
- end: `0x180003c28`
- name: `CShareMediaCplElementProvider_CreateInstance`
- size: `520`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task`

## callees

- `0x180001914`
- `0x180003254`
- `0x180003860`
- `0x180003888`
- `0x180003a20`
- `0x18000c89c`
- `0x18000cc2c`
- `0x18000ce10`
- `0x180013a04`
- `0x180018a00`
- `0x180018b98`
- `0x180018d20`
- `0x18001bb2c`
- `0x18001bccc`
- `0x18001e010`

## import_xrefs

- `DUI70!InitProcessPriv` at `0x180003b46`
- `DUI70!InitProcessPriv` at `0x180003b46`
- `DUI70!InitThread` at `0x180003b57`
- `DUI70!InitThread` at `0x180003b57`
- `DUI70!UnInitProcessPriv` at `0x180003b6a`
- `DUI70!UnInitProcessPriv` at `0x180003b6a`
- `DUI70!??0XProvider@DirectUI@@QEAA@XZ` at `0x180003a81`
- `DUI70!??0XProvider@DirectUI@@QEAA@XZ` at `0x180003a81`

## pseudocode

```c
__int64 __fastcall CShareMediaCplElementProvider_CreateInstance(__int64 a1, __int64 a2)
{
  DirectUI::XProvider *v3; // rax
  DirectUI::XProvider *v4; // rdi
  HINSTANCE v5; // rbx
  const wchar_t *v6; // r8
  unsigned int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // rcx
  _WORD *v10; // rax
  _WORD *v11; // rdx
  __int64 v12; // r8
  int inited; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_13d719e44d5638f61d35bd3924991706_Traceguids);
  v3 = (DirectUI::XProvider *)operator new(0x278u);
  v4 = v3;
  if ( v3 )
  {
    v5 = g_hinst;
    DirectUI::XProvider::XProvider(v3);
    *((_QWORD *)v4 + 10) = 0;
    *(_QWORD *)v4 = &FrameProvider::`vftable'{for `DirectUI::XProvider'};
    v6 = L"main";
    *((_QWORD *)v4 + 11) = v5;
    *((_QWORD *)v4 + 5) = &FrameProvider::`vftable'{for `IDUIElementProviderInit'};
    v7 = -2147467259;
    *((_DWORD *)v4 + 154) = -2147467259;
    *((_QWORD *)v4 + 6) = &FrameProvider::`vftable'{for `IFrameNotificationClient'};
    v8 = 2147483646;
    *((_QWORD *)v4 + 78) = 0;
    *((_QWORD *)v4 + 7) = &FrameProvider::`vftable'{for `IFrameShellViewClient'};
    v9 = 260;
    *((_QWORD *)v4 + 8) = &FrameProvider::`vftable'{for `IObjectWithSite'};
    *((_QWORD *)v4 + 9) = &FrameProvider::`vftable'{for `IServiceProvider'};
    v10 = (_WORD *)((char *)v4 + 96);
    do
    {
      if ( !v8 )
        break;
      if ( !*v6 )
        break;
      *v10++ = *v6++;
      --v8;
      --v9;
    }
    while ( v9 );
    v11 = v10 - 1;
    if ( v9 )
      v11 = v10;
    *v11 = 0;
    DllAddRef(v9, v11, v6);
    LOBYTE(v12) = 1;
    inited = InitProcessPriv(14, &_ImageBase, v12);
    if ( inited >= 0 )
    {
      inited = InitThread(2);
      if ( inited < 0 )
        UnInitProcessPriv(&_ImageBase);
    }
    *((_DWORD *)v4 + 154) = inited;
    if ( inited < 0 )
    {
      v7 = inited;
    }
    else if ( (int)CNavigateButton::Register() >= 0
           && (int)CElementWithIUnknown::Register() >= 0
           && (int)DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::Register() >= 0
           && (int)DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Register() >= 0
           && (int)CFocusIndicator::Register() >= 0 )
    {
      CCheckBoxButton::Register();
      CShareWithListItemUsers::Register();
      CShareWithListItemDevice::Register();
      CShareMediaPage::Register();
      v7 = (**(__int64 (__fastcall ***)(DirectUI::XProvider *, GUID *, __int64))v4)(
             v4,
             &GUID_00000000_0000_0000_c000_000000000046,
             a2);
    }
    (*(void (__fastcall **)(DirectUI::XProvider *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  else
  {
    v7 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_13d719e44d5638f61d35bd3924991706_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180003a20  push    rbx
0x180003a22  push    rbp
0x180003a23  push    rsi
0x180003a24  push    rdi
0x180003a25  push    r14
0x180003a27  push    r15
0x180003a29  sub     rsp, 38h
0x180003a2d  mov     rbp, rdx
0x180003a30  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a37  lea     r15, WPP_GLOBAL_Control
0x180003a3e  cmp     rcx, r15
0x180003a41  jz      short loc_180003A5E
0x180003a43  test    byte ptr [rcx+1Ch], 20h
0x180003a47  jz      short loc_180003A5E
0x180003a49  mov     rcx, [rcx+10h]
0x180003a4d  lea     r8, WPP_13d719e44d5638f61d35bd3924991706_Traceguids
0x180003a54  mov     edx, 0Ah
0x180003a59  call    WPP_SF_
0x180003a5e  mov     ecx, 278h; Size
0x180003a63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a68  xor     r14d, r14d
0x180003a6b  mov     rdi, rax
0x180003a6e  test    rax, rax
0x180003a71  jz      loc_180003BEA
0x180003a77  mov     rbx, cs:g_hinst
0x180003a7e  mov     rcx, rax
0x180003a81  call    cs:__imp_??0XProvider@DirectUI@@QEAA@XZ; DirectUI::XProvider::XProvider(void)
0x180003a87  lea     rax, ??_7FrameProvider@@6BXProvider@DirectUI@@@; const FrameProvider::`vftable'{for `DirectUI::XProvider'}
0x180003a8e  mov     [rdi+50h], r14
0x180003a92  mov     [rdi], rax
0x180003a95  lea     r8, aMain; "main"
0x180003a9c  lea     rax, ??_7FrameProvider@@6BIDUIElementProviderInit@@@; const FrameProvider::`vftable'{for `IDUIElementProviderInit'}
0x180003aa3  mov     [rdi+58h], rbx
0x180003aa7  mov     [rdi+28h], rax
0x180003aab  mov     esi, 80004005h
0x180003ab0  lea     rax, ??_7FrameProvider@@6BIFrameNotificationClient@@@; const FrameProvider::`vftable'{for `IFrameNotificationClient'}
0x180003ab7  mov     [rdi+268h], esi
0x180003abd  mov     [rdi+30h], rax
0x180003ac1  mov     edx, 7FFFFFFEh
0x180003ac6  lea     rax, ??_7FrameProvider@@6BIFrameShellViewClient@@@; const FrameProvider::`vftable'{for `IFrameShellViewClient'}
0x180003acd  mov     [rdi+270h], r14
0x180003ad4  mov     [rdi+38h], rax
0x180003ad8  mov     ecx, 104h
0x180003add  lea     rax, ??_7FrameProvider@@6BIObjectWithSite@@@; const FrameProvider::`vftable'{for `IObjectWithSite'}
0x180003ae4  mov     [rdi+40h], rax
0x180003ae8  lea     rax, ??_7FrameProvider@@6BIServiceProvider@@@; const FrameProvider::`vftable'{for `IServiceProvider'}
0x180003aef  mov     [rdi+48h], rax
0x180003af3  lea     rax, [rdi+60h]
0x180003af7  test    rdx, rdx
0x180003afa  jz      short loc_180003B1B
0x180003afc  movzx   r9d, word ptr [r8]
0x180003b00  test    r9w, r9w
0x180003b04  jz      short loc_180003B1B
0x180003b06  mov     [rax], r9w
0x180003b0a  add     r8, 2
0x180003b0e  add     rax, 2
0x180003b12  dec     rdx
0x180003b15  sub     rcx, 1
0x180003b19  jnz     short loc_180003AF7
0x180003b1b  test    rcx, rcx
0x180003b1e  lea     rdx, [rax-2]
0x180003b22  cmovnz  rdx, rax
0x180003b26  mov     [rdx], r14w
0x180003b2a  call    DllAddRef
0x180003b2f  mov     r9b, 1
0x180003b32  mov     [rsp+68h+var_48], 1
0x180003b37  mov     r8b, r9b
0x180003b3a  lea     rdx, __ImageBase
0x180003b41  mov     ecx, 0Eh
0x180003b46  call    cs:__imp_InitProcessPriv
0x180003b4c  mov     ebx, eax
0x180003b4e  test    eax, eax
0x180003b50  js      short loc_180003B70
0x180003b52  mov     ecx, 2
0x180003b57  call    cs:__imp_InitThread
0x180003b5d  mov     ebx, eax
0x180003b5f  test    eax, eax
0x180003b61  jns     short loc_180003B70
0x180003b63  lea     rcx, __ImageBase
0x180003b6a  call    cs:__imp_UnInitProcessPriv
0x180003b70  mov     [rdi+268h], ebx
0x180003b76  test    ebx, ebx
0x180003b78  js      short loc_180003BD7
0x180003b7a  call    ?Register@CNavigateButton@@SAJXZ; CNavigateButton::Register(void)
0x180003b7f  test    eax, eax
0x180003b81  js      short loc_180003BD9
0x180003b83  call    ?Register@CElementWithIUnknown@@SAJXZ; CElementWithIUnknown::Register(void)
0x180003b88  test    eax, eax
0x180003b8a  js      short loc_180003BD9
0x180003b8c  call    ?Register@?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@SAJPEBGPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::Register(ushort const *,DirectUI::PropertyInfo const * const *,uint)
0x180003b91  test    eax, eax
0x180003b93  js      short loc_180003BD9
0x180003b95  call    ?Register@?$ClassInfo@VCFrameModule@@VCElementWithSite@@V?$StandardCreator@VCFrameModule@@@DirectUI@@@DirectUI@@SAJPEBGPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Register(ushort const *,DirectUI::PropertyInfo const * const *,uint)
0x180003b9a  test    eax, eax
0x180003b9c  js      short loc_180003BD9
0x180003b9e  call    ?Register@CFocusIndicator@@SAJXZ; CFocusIndicator::Register(void)
0x180003ba3  test    eax, eax
0x180003ba5  js      short loc_180003BD9
0x180003ba7  call    ?Register@CCheckBoxButton@@SAJXZ; CCheckBoxButton::Register(void)
0x180003bac  call    ?Register@CShareWithListItemUsers@@SAJXZ; CShareWithListItemUsers::Register(void)
0x180003bb1  call    ?Register@CShareWithListItemDevice@@SAJXZ; CShareWithListItemDevice::Register(void)
0x180003bb6  call    ?Register@CShareMediaPage@@SAJXZ; CShareMediaPage::Register(void)
0x180003bbb  mov     rax, [rdi]
0x180003bbe  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180003bc5  mov     r8, rbp
0x180003bc8  mov     rcx, rdi
0x180003bcb  mov     rax, [rax]
0x180003bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bd3  mov     esi, eax
0x180003bd5  jmp     short loc_180003BD9
0x180003bd7  mov     esi, ebx
0x180003bd9  mov     rax, [rdi]
0x180003bdc  mov     rcx, rdi
0x180003bdf  mov     rax, [rax+10h]
0x180003be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003be8  jmp     short loc_180003BEF
0x180003bea  mov     esi, 8007000Eh
0x180003bef  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bf6  cmp     rcx, r15
0x180003bf9  jz      short loc_180003C19
0x180003bfb  test    byte ptr [rcx+1Ch], 20h
0x180003bff  jz      short loc_180003C19
0x180003c01  mov     rcx, [rcx+10h]
0x180003c05  lea     r8, WPP_13d719e44d5638f61d35bd3924991706_Traceguids
0x180003c0c  mov     edx, 0Bh
0x180003c11  mov     r9d, esi
0x180003c14  call    WPP_SF_d
0x180003c19  mov     eax, esi
0x180003c1b  add     rsp, 38h
0x180003c1f  pop     r15
0x180003c21  pop     r14
0x180003c23  pop     rdi
0x180003c24  pop     rsi
0x180003c25  pop     rbp
0x180003c26  pop     rbx
0x180003c27  retn
```
