# ServiceStateManager::AddExistingStateFromRootKey(HKEY__ *,ServiceStateManager::RegistryStateRootId,utl::set<utl::basic_string_view<ushort,utl::char_traits<ushort>>,ServiceStateManager::InsensitiveWstringCompare,utl::allocator<utl::basic_string_view<ushort,utl::char_traits<ushort>>>> &)

- ea: `0x140076194`
- end: `0x1400764f5`
- name: `?AddExistingStateFromRootKey@ServiceStateManager@@AEAAKPEAUHKEY__@@W4RegistryStateRootId@1@AEAV?$set@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@UInsensitiveWstringCompare@ServiceStateManager@@V?$allocator@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@2@@utl@@@Z`
- size: `865`
- prototype: `__int64 __fastcall(__int64, HKEY, int, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140078130`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140005824`
- `0x14000bcc4`
- `0x1400409f8`
- `0x140043c80`
- `0x1400575b0`
- `0x140057844`
- `0x14006e0d0`
- `0x14006f68c`
- `0x1400757c0`
- `0x140075944`
- `0x140075f38`
- `0x140076194`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400762d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400762d1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14007621d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14007621d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007646e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007647e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007646e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007647e`

## pseudocode

```c
__int64 __fastcall ServiceStateManager::AddExistingStateFromRootKey(__int64 a1, HKEY a2, int a3, _QWORD *a4)
{
  DWORD v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // edi
  __int64 v12; // rax
  __int64 v13; // r8
  int v14; // eax
  PRPC_ASYNC_STATE v15; // rcx
  int v16; // edx
  void **i; // rbx
  unsigned __int16 *v18; // rdi
  ULONG v19; // eax
  void *v20; // rbx
  _QWORD *v21; // rdx
  char *v22; // rcx
  __int64 v23; // rax
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  void *v28[3]; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v29[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[32]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v30);
  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(v28);
  phkResult = 0;
  v8 = 0;
  hKey = 0;
  while ( 1 )
  {
    cchName = 260;
    v9 = RegEnumKeyExW(a2, v8, Name, &cchName, 0, 0, 0, 0);
    v11 = v9;
    if ( v9 == 259 )
      break;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 411, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v9);
      goto LABEL_40;
    }
    if ( !*(_DWORD *)(a1 + 88) || *(_DWORD *)(a1 + 92) && a3 == 3 )
      goto LABEL_14;
    v29[0] = Name;
    v12 = -1;
    do
      ++v12;
    while ( Name[v12] );
    v29[1] = (const wchar_t *)v12;
    if ( utl::_Tree<utl::basic_string_view<unsigned short,utl::char_traits<unsigned short>>,utl::basic_string_view<unsigned short,utl::char_traits<unsigned short>>,ServiceStateManager::InsensitiveWstringCompare,utl::allocator<utl::basic_string_view<unsigned short,utl::char_traits<unsigned short>>>,0>::contains<void>(
           a4,
           v29) )
    {
LABEL_14:
      v14 = RegOpenKeyExW(a2, Name, 0, 0x20019u, &phkResult);
      if ( v14 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v16 = 413;
          goto LABEL_22;
        }
      }
      else
      {
        v14 = ServiceStateManager::AddExistingStateFromPerServiceKey(a1, (__int64)Name, phkResult);
        if ( v14 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            v16 = 412;
LABEL_22:
            WPP_SF_Sd(
              v15->StubInfo,
              v16,
              (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
              (unsigned int)Name,
              v14);
          }
        }
      }
    }
    else
    {
      v13 = -1;
      do
        ++v13;
      while ( Name[v13] );
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                              v30,
                              Name) )
        utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::emplace_back<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>(
          v28,
          v30);
    }
    ++v8;
  }
  for ( i = (void **)v28[0]; i != v28; i = (void **)*i )
  {
    v18 = (unsigned __int16 *)i[2];
    v19 = ScRegOpenKeyExW(a2, v18, v10, 0x3001Fu, &hKey);
    if ( v19 )
    {
      if ( v19 != 2
        && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          414,
          (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
          (_DWORD)v18,
          v19);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          415,
          (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
          (_DWORD)v18,
          a3);
      ScDeleteRegTree(a2, hKey, v18);
      hKey = 0;
    }
  }
  v11 = 0;
LABEL_40:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  while ( 1 )
  {
    v20 = v28[0];
    if ( v28[0] == v28 )
      break;
    v21 = (_QWORD *)*((_QWORD *)v28[0] + 1);
    v22 = (char *)v28[0] + 16;
    v23 = *(_QWORD *)v28[0];
    *v21 = *(_QWORD *)v28[0];
    *(_QWORD *)(v23 + 8) = v21;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v22);
    operator delete(v20, (const struct std::nothrow_t *)std::nothrow);
  }
  v28[2] = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v30);
  return v11;
}

```

## disassembly

```asm
0x140076194  mov     [rsp-8+arg_10], rbx
0x140076199  push    rbp
0x14007619a  push    rsi
0x14007619b  push    rdi
0x14007619c  push    r12
0x14007619e  push    r13
0x1400761a0  push    r14
0x1400761a2  push    r15
0x1400761a4  lea     rbp, [rsp-1C0h]
0x1400761ac  sub     rsp, 2C0h
0x1400761b3  mov     rax, cs:__security_cookie
0x1400761ba  xor     rax, rsp
0x1400761bd  mov     [rbp+1F0h+var_40], rax
0x1400761c4  mov     rsi, rcx
0x1400761c7  mov     r12, r9
0x1400761ca  lea     rcx, [rbp+1F0h+var_270]
0x1400761ce  mov     r15d, r8d
0x1400761d1  mov     r14, rdx
0x1400761d4  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1400761d9  lea     rcx, [rsp+2F0h+var_298]
0x1400761de  call    ??0?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAA@XZ; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(void)
0x1400761e3  xor     r13d, r13d
0x1400761e6  mov     [rsp+2F0h+phkResult], r13
0x1400761eb  mov     ebx, r13d
0x1400761ee  mov     [rsp+2F0h+hKey], r13
0x1400761f3  mov     [rsp+2F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1400761f8  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x1400761fd  mov     [rsp+2F0h+lpcchClass], r13; lpcchClass
0x140076202  lea     r8, [rbp+1F0h+Name]; lpName
0x140076206  mov     [rsp+2F0h+lpClass], r13; lpClass
0x14007620b  mov     edx, ebx; dwIndex
0x14007620d  mov     rcx, r14; hKey
0x140076210  mov     [rsp+2F0h+lpReserved], r13; lpReserved
0x140076215  mov     [rsp+2F0h+cchName], 104h
0x14007621d  call    cs:__imp_RegEnumKeyExW
0x140076223  mov     edi, eax
0x140076225  cmp     eax, 103h
0x14007622a  jz      loc_140076398
0x140076230  test    eax, eax
0x140076232  jnz     loc_14007635A
0x140076238  cmp     [rsi+58h], r13d
0x14007623c  jz      short loc_1400762B7
0x14007623e  cmp     [rsi+5Ch], r13d
0x140076242  jz      short loc_14007624A
0x140076244  cmp     r15d, 3
0x140076248  jz      short loc_1400762B7
0x14007624a  lea     rax, [rbp+1F0h+Name]
0x14007624e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140076252  mov     [rsp+2F0h+var_280], rax
0x140076257  lea     rcx, [rbp+1F0h+Name]
0x14007625b  mov     rax, rdi
0x14007625e  inc     rax
0x140076261  cmp     [rcx+rax*2], r13w
0x140076266  jnz     short loc_14007625E
0x140076268  lea     rdx, [rsp+2F0h+var_280]
0x14007626d  mov     [rsp+2F0h+var_278], rax
0x140076272  mov     rcx, r12
0x140076275  call    ??$contains@X@?$_Tree@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@V12@UInsensitiveWstringCompare@ServiceStateManager@@V?$allocator@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@2@$0A@@utl@@QEBA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@1@@Z; utl::_Tree<utl::basic_string_view<ushort,utl::char_traits<ushort>>,utl::basic_string_view<ushort,utl::char_traits<ushort>>,ServiceStateManager::InsensitiveWstringCompare,utl::allocator<utl::basic_string_view<ushort,utl::char_traits<ushort>>>,0>::contains<void>(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14007627a  test    al, al
0x14007627c  jnz     short loc_1400762B7
0x14007627e  lea     rax, [rbp+1F0h+Name]
0x140076282  mov     r8, rdi
0x140076285  inc     r8
0x140076288  cmp     [rax+r8*2], r13w
0x14007628d  jnz     short loc_140076285
0x14007628f  lea     rdx, [rbp+1F0h+Name]
0x140076293  lea     rcx, [rbp+1F0h+var_270]
0x140076297  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14007629c  test    al, al
0x14007629e  jz      loc_14007634E
0x1400762a4  lea     rdx, [rbp+1F0h+var_270]
0x1400762a8  lea     rcx, [rsp+2F0h+var_298]
0x1400762ad  call    ??$emplace_back@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@$0A@@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_N$$QEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::emplace_back<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,0>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1400762b2  jmp     loc_14007634E
0x1400762b7  lea     rax, [rsp+2F0h+phkResult]
0x1400762bc  mov     r9d, 20019h; samDesired
0x1400762c2  xor     r8d, r8d; ulOptions
0x1400762c5  mov     [rsp+2F0h+lpReserved], rax; phkResult
0x1400762ca  lea     rdx, [rbp+1F0h+Name]; lpSubKey
0x1400762ce  mov     rcx, r14; hKey
0x1400762d1  call    cs:__imp_RegOpenKeyExW
0x1400762d7  test    eax, eax
0x1400762d9  jnz     short loc_140076318
0x1400762db  mov     r8, [rsp+2F0h+phkResult]
0x1400762e0  lea     rdx, [rbp+1F0h+Name]
0x1400762e4  mov     r9d, r15d
0x1400762e7  mov     [rsp+2F0h+lpReserved], r13
0x1400762ec  mov     rcx, rsi
0x1400762ef  call    ?AddExistingStateFromPerServiceKey@ServiceStateManager@@AEAAKPEBGPEAUHKEY__@@W4RegistryStateRootId@1@PEAU_SERVICE_CONFIG_ROOT@@@Z; ServiceStateManager::AddExistingStateFromPerServiceKey(ushort const *,HKEY__ *,ServiceStateManager::RegistryStateRootId,_SERVICE_CONFIG_ROOT *)
0x1400762f4  test    eax, eax
0x1400762f6  jz      short loc_14007634E
0x1400762f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400762ff  lea     rdx, WPP_GLOBAL_Control
0x140076306  cmp     rcx, rdx
0x140076309  jz      short loc_14007634E
0x14007630b  test    byte ptr [rcx+1Ch], 1
0x14007630f  jz      short loc_14007634E
0x140076311  mov     edx, 19Ch
0x140076316  jmp     short loc_140076336
0x140076318  mov     rcx, cs:WPP_GLOBAL_Control
0x14007631f  lea     rdx, WPP_GLOBAL_Control
0x140076326  cmp     rcx, rdx
0x140076329  jz      short loc_14007634E
0x14007632b  test    byte ptr [rcx+1Ch], 1
0x14007632f  jz      short loc_14007634E
0x140076331  mov     edx, 19Dh
0x140076336  mov     rcx, [rcx+10h]
0x14007633a  lea     r9, [rbp+1F0h+Name]
0x14007633e  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140076345  mov     dword ptr [rsp+2F0h+lpReserved], eax
0x140076349  call    WPP_SF_Sd
0x14007634e  mov     eax, 1
0x140076353  add     ebx, eax
0x140076355  jmp     loc_1400761F3
0x14007635a  mov     rcx, cs:WPP_GLOBAL_Control
0x140076361  lea     rax, WPP_GLOBAL_Control
0x140076368  cmp     rcx, rax
0x14007636b  jz      loc_140076464
0x140076371  test    byte ptr [rcx+1Ch], 1
0x140076375  jz      loc_140076464
0x14007637b  mov     rcx, [rcx+10h]
0x14007637f  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140076386  mov     edx, 19Bh
0x14007638b  mov     r9d, edi
0x14007638e  call    WPP_SF_d
0x140076393  jmp     loc_140076464
0x140076398  mov     rbx, [rsp+2F0h+var_298]
0x14007639d  lea     rax, [rsp+2F0h+var_298]
0x1400763a2  cmp     rbx, rax
0x1400763a5  jz      loc_140076461
0x1400763ab  mov     rdi, [rbx+10h]
0x1400763af  lea     rax, [rsp+2F0h+hKey]
0x1400763b4  mov     rdx, rdi; unsigned __int16 *
0x1400763b7  mov     [rsp+2F0h+lpReserved], rax; HKEY *
0x1400763bc  mov     r9d, 3001Fh; unsigned int
0x1400763c2  mov     rcx, r14; HKEY
0x1400763c5  call    ?ScRegOpenKeyExW@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; ScRegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1400763ca  test    eax, eax
0x1400763cc  jz      short loc_14007640E
0x1400763ce  cmp     eax, 2
0x1400763d1  jz      loc_140076459
0x1400763d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400763de  lea     rdx, WPP_GLOBAL_Control
0x1400763e5  cmp     rcx, rdx
0x1400763e8  jz      short loc_140076459
0x1400763ea  test    byte ptr [rcx+1Ch], 1
0x1400763ee  jz      short loc_140076459
0x1400763f0  mov     rcx, [rcx+10h]
0x1400763f4  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x1400763fb  mov     edx, 19Eh
0x140076400  mov     dword ptr [rsp+2F0h+lpReserved], eax
0x140076404  mov     r9, rdi
0x140076407  call    WPP_SF_Sd
0x14007640c  jmp     short loc_140076459
0x14007640e  mov     rcx, cs:WPP_GLOBAL_Control
0x140076415  lea     rax, WPP_GLOBAL_Control
0x14007641c  cmp     rcx, rax
0x14007641f  jz      short loc_140076444
0x140076421  test    byte ptr [rcx+1Ch], 4
0x140076425  jz      short loc_140076444
0x140076427  mov     rcx, [rcx+10h]
0x14007642b  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140076432  mov     edx, 19Fh
0x140076437  mov     dword ptr [rsp+2F0h+lpReserved], r15d
0x14007643c  mov     r9, rdi
0x14007643f  call    WPP_SF_Sd
0x140076444  mov     rdx, [rsp+2F0h+hKey]; HKEY
0x140076449  mov     r8, rdi; unsigned __int16 *
0x14007644c  mov     rcx, r14; HKEY
0x14007644f  call    ?ScDeleteRegTree@@YAXPEAUHKEY__@@0PEBG@Z; ScDeleteRegTree(HKEY__ *,HKEY__ *,ushort const *)
0x140076454  mov     [rsp+2F0h+hKey], r13
0x140076459  mov     rbx, [rbx]
0x14007645c  jmp     loc_14007639D
0x140076461  mov     edi, r13d
0x140076464  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x140076469  test    rcx, rcx
0x14007646c  jz      short loc_140076474
0x14007646e  call    cs:__imp_RegCloseKey
0x140076474  mov     rcx, [rsp+2F0h+hKey]; hKey
0x140076479  test    rcx, rcx
0x14007647c  jz      short loc_140076484
0x14007647e  call    cs:__imp_RegCloseKey
0x140076484  mov     rbx, [rsp+2F0h+var_298]
0x140076489  lea     rax, [rsp+2F0h+var_298]
0x14007648e  cmp     rbx, rax
0x140076491  jz      short loc_1400764BB
0x140076493  mov     rdx, [rbx+8]
0x140076497  lea     rcx, [rbx+10h]
0x14007649b  mov     rax, [rbx]
0x14007649e  mov     [rdx], rax
0x1400764a1  mov     [rax+8], rdx
0x1400764a5  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1400764aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400764b1  mov     rcx, rbx; void *
0x1400764b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400764b9  jmp     short loc_140076484
0x1400764bb  lea     rcx, [rbp+1F0h+var_270]
0x1400764bf  mov     [rsp+2F0h+var_288], r13
0x1400764c4  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1400764c9  mov     eax, edi
0x1400764cb  mov     rcx, [rbp+1F0h+var_40]
0x1400764d2  xor     rcx, rsp; StackCookie
0x1400764d5  call    __security_check_cookie
0x1400764da  mov     rbx, [rsp+2F0h+arg_10]
0x1400764e2  add     rsp, 2C0h
0x1400764e9  pop     r15
0x1400764eb  pop     r14
0x1400764ed  pop     r13
0x1400764ef  pop     r12
0x1400764f1  pop     rdi
0x1400764f2  pop     rsi
0x1400764f3  pop     rbp
0x1400764f4  retn
```
