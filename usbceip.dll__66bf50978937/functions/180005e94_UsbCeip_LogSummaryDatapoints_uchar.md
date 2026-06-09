# UsbCeip_LogSummaryDatapoints(uchar)

- ea: `0x180005e94`
- end: `0x18000631a`
- name: `?UsbCeip_LogSummaryDatapoints@@YAXE@Z`
- size: `1158`
- prototype: `void __fastcall(char)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x180006320`

## callees

- `0x180001010`
- `0x180001294`
- `0x180002410`
- `0x180003fec`
- `0x180005cb8`
- `0x180005ce4`
- `0x180005d58`
- `0x180005e94`
- `0x18000bc7c`
- `0x18000bd24`
- `0x18000bfa0`
- `0x18000c01c`
- `0x18000c088`
- `0x18000c114`
- `0x18000c16c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180005fbf`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180005fbf`

## string_xrefs

- `0x180005ed3`: `System\CurrentControlSet\Services\USBHUB\Hubg`
- `0x180005ef7`: `System\CurrentControlSet\Services\USBHUB\Hubg`

## pseudocode

```c
void __fastcall UsbCeip_LogSummaryDatapoints(char a1)
{
  __int64 *v2; // rbx
  const wchar_t **v3; // rdi
  const wchar_t *v4; // rcx
  const unsigned __int16 *v5; // rdx
  __int64 **v6; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 *v9; // rbx
  const unsigned __int16 *v10; // r8
  __int64 **v11; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned __int8 v17[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v18[4]; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int8 v19[4]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 v20[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  const wchar_t **v21; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 **v22; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh] BYREF
  HKEY phkResult[4]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v26[2]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v27[2]; // [rsp+88h] [rbp-78h] BYREF
  HKEY v28[5]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v29[32]; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 ***v30; // [rsp+E0h] [rbp-20h]
  __int64 v31; // [rsp+E8h] [rbp-18h]
  const wchar_t ***v32; // [rsp+F0h] [rbp-10h]
  __int64 v33; // [rsp+F8h] [rbp-8h]
  int *v34; // [rsp+100h] [rbp+0h]
  __int64 v35; // [rsp+108h] [rbp+8h]
  int *v36; // [rsp+110h] [rbp+10h]
  __int64 v37; // [rsp+118h] [rbp+18h]

  *(_DWORD *)v19 = 0;
  *(_DWORD *)v17 = 0;
  *(_DWORD *)v18 = 0;
  *(_DWORD *)v20 = 0;
  if ( CRegistryKey::KeyExists(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\USBHUB\\Hubg") )
  {
    CRegistryKey::CRegistryKey(phkResult, HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\USBHUB\\Hubg");
    *(_DWORD *)v20 = 0;
    CRegistryKey::QueryFixedLengthValue(phkResult, L"DisableSelectiveSuspend", 4u, v20);
    CRegistryKey::~CRegistryKey(phkResult);
  }
  *(_DWORD *)v17 = 0;
  if ( CRegistryKey::KeyExists(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\UsbFlags") )
  {
    std::set<_bstr_t>::set<_bstr_t>(v27);
    CRegistryKey::CRegistryKey(v28, HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\UsbFlags");
    v21 = 0;
    CRegistryKey::EnumValueNames((CRegistryKey *)v28, (__int64)v27);
    v2 = *(__int64 **)v27[0];
    while ( v2 != (__int64 *)v27[0] )
    {
      _bstr_t::operator=((_bstr_t *)&v21, (__int64)(v2 + 4));
      v3 = v21;
      if ( v21 )
        v4 = *v21;
      else
        v4 = 0;
      if ( wcsstr(v4, L"IgnoreHWSerNum") )
      {
        v5 = v3 ? *v3 : 0LL;
        *(_DWORD *)v17 = 0;
        CRegistryKey::QueryFixedLengthValue(v28, v5, 4u, v17);
        if ( *(_DWORD *)v17 )
          goto LABEL_41;
      }
      v6 = (__int64 **)v2[2];
      if ( *((_BYTE *)v6 + 25) )
      {
        for ( i = (__int64 *)v2[1]; !*((_BYTE *)i + 25) && v2 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v2 = i;
        v2 = i;
      }
      else
      {
        v2 = (__int64 *)v2[2];
        for ( j = *v6; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v2 = j;
      }
    }
    if ( !*(_DWORD *)v17 )
    {
      std::set<_bstr_t>::set<_bstr_t>(v26);
      v22 = 0;
      CRegistryKey::EnumerateChildKeyNames((CRegistryKey *)v28, (__int64)v26);
      v9 = *(__int64 **)v26[0];
      while ( v9 != (__int64 *)v26[0] )
      {
        _bstr_t::operator=((_bstr_t *)&v22, (__int64)(v9 + 4));
        if ( v22 )
          v10 = *v22;
        else
          v10 = 0;
        CRegistryKey::CRegistryKey(phkResult, v28[0], v10);
        *(_DWORD *)v17 = 0;
        CRegistryKey::QueryFixedLengthValue(phkResult, L"IgnoreHWSerNum", 4u, v17);
        if ( *(_DWORD *)v17 )
        {
          CRegistryKey::~CRegistryKey(phkResult);
          break;
        }
        CRegistryKey::~CRegistryKey(phkResult);
        v11 = (__int64 **)v9[2];
        if ( *((_BYTE *)v11 + 25) )
        {
          for ( k = (__int64 *)v9[1]; !*((_BYTE *)k + 25) && v9 == (__int64 *)k[2]; k = (__int64 *)k[1] )
            v9 = k;
          v9 = k;
        }
        else
        {
          v9 = (__int64 *)v9[2];
          for ( m = *v11; !*((_BYTE *)m + 25); m = (__int64 *)*m )
            v9 = m;
        }
      }
      _bstr_t::_Free((_bstr_t *)&v22);
      std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::~_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>(v26);
    }
LABEL_41:
    _bstr_t::_Free((_bstr_t *)&v21);
    CRegistryKey::~CRegistryKey(v28);
    std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::~_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>(v27);
  }
  *(_DWORD *)v19 = 0;
  if ( CRegistryKey::KeyExists(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Usb\\Ceip") )
  {
    CRegistryKey::CRegistryKey(phkResult, HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Usb\\Ceip");
    *(_DWORD *)v19 = 0;
    CRegistryKey::QueryFixedLengthValue(phkResult, L"APIUsage", 4u, v19);
    if ( !a1 )
      CRegistryKey::SetUlongValue(phkResult, L"APIUsage");
    CRegistryKey::~CRegistryKey(phkResult);
  }
  *(_DWORD *)v18 = 0;
  if ( CRegistryKey::KeyExists(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Usb\\Ceip") )
  {
    CRegistryKey::CRegistryKey(phkResult, HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Usb\\Ceip");
    *(_DWORD *)v18 = 0;
    CRegistryKey::QueryFixedLengthValue(phkResult, L"UsbInformation", 4u, v18);
    if ( !a1 )
      CRegistryKey::SetUlongValue(phkResult, L"UsbInformation");
    CRegistryKey::~CRegistryKey(phkResult);
  }
  if ( (unsigned int)dword_18001C038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18001C038, v14, v15, v16) )
  {
    v23 = *(_DWORD *)v18;
    v24 = *(_DWORD *)v19;
    LODWORD(v21) = *(_DWORD *)v17;
    LODWORD(v22) = *(_DWORD *)v20;
    v36 = &v23;
    v37 = 4;
    v34 = &v24;
    v35 = 4;
    v32 = &v21;
    v33 = 4;
    v30 = &v22;
    v31 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18001C038, &word_180017B66, 0, 0, 6, v29);
  }
}

```

## disassembly

```asm
0x180005e94  push    rbp
0x180005e96  push    rbx
0x180005e97  push    rsi
0x180005e98  push    rdi
0x180005e99  push    r12
0x180005e9b  push    r14
0x180005e9d  push    r15
0x180005e9f  lea     rbp, [rsp-30h]
0x180005ea4  sub     rsp, 130h
0x180005eab  mov     rax, cs:__security_cookie
0x180005eb2  xor     rax, rsp
0x180005eb5  mov     [rbp+60h+var_40], rax
0x180005eb9  mov     sil, cl
0x180005ebc  xor     r14d, r14d
0x180005ebf  mov     dword ptr [rsp+160h+var_128], r14d
0x180005ec4  mov     dword ptr [rsp+160h+var_130], r14d
0x180005ec9  mov     dword ptr [rsp+160h+var_12C], r14d
0x180005ece  mov     dword ptr [rsp+160h+var_124], r14d
0x180005ed3  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\US"...
0x180005eda  mov     r15, 0FFFFFFFF80000002h
0x180005ee1  mov     rcx, r15; HKEY
0x180005ee4  call    ?KeyExists@CRegistryKey@@SAEPEAUHKEY__@@PEBG@Z; CRegistryKey::KeyExists(HKEY__ *,ushort const *)
0x180005ee9  lea     r12d, [r14+4]
0x180005eed  test    al, al
0x180005eef  jz      short loc_180005F35
0x180005ef1  mov     r9d, 20019h; unsigned int
0x180005ef7  lea     r8, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\US"...
0x180005efe  mov     rdx, r15; HKEY
0x180005f01  lea     rcx, [rsp+160h+phkResult]; phkResult
0x180005f06  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x180005f0b  nop
0x180005f0c  mov     dword ptr [rsp+160h+var_124], r14d
0x180005f11  lea     r9, [rsp+160h+var_124]; unsigned __int8 *
0x180005f16  mov     r8d, r12d; unsigned int
0x180005f19  lea     rdx, aDisableselecti; "DisableSelectiveSuspend"
0x180005f20  lea     rcx, [rsp+160h+phkResult]; this
0x180005f25  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x180005f2a  nop
0x180005f2b  lea     rcx, [rsp+160h+phkResult]; this
0x180005f30  call    ??1CRegistryKey@@QEAA@XZ; CRegistryKey::~CRegistryKey(void)
0x180005f35  mov     dword ptr [rsp+160h+var_130], r14d
0x180005f3a  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Usb"...
0x180005f41  mov     rcx, r15; HKEY
0x180005f44  call    ?KeyExists@CRegistryKey@@SAEPEAUHKEY__@@PEBG@Z; CRegistryKey::KeyExists(HKEY__ *,ushort const *)
0x180005f49  test    al, al
0x180005f4b  jz      loc_180006171
0x180005f51  lea     rcx, [rbp+60h+var_D8]
0x180005f55  call    ??0?$set@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@@std@@QEAA@XZ; std::set<_bstr_t>::set<_bstr_t>(void)
0x180005f5a  nop
0x180005f5b  mov     r9d, 20019h; unsigned int
0x180005f61  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Usb"...
0x180005f68  mov     rdx, r15; HKEY
0x180005f6b  lea     rcx, [rbp+60h+var_C8]; phkResult
0x180005f6f  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x180005f74  nop
0x180005f75  mov     [rsp+160h+var_120], r14
0x180005f7a  lea     rdx, [rbp+60h+var_D8]
0x180005f7e  lea     rcx, [rbp+60h+var_C8]; this
0x180005f82  call    ?EnumValueNames@CRegistryKey@@QEAAXAEAV?$set@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@@std@@@Z; CRegistryKey::EnumValueNames(std::set<_bstr_t> &)
0x180005f87  mov     rbx, [rbp+60h+var_D8]
0x180005f8b  mov     rbx, [rbx]
0x180005f8e  cmp     rbx, [rbp+60h+var_D8]
0x180005f92  jz      loc_180006047
0x180005f98  lea     rdx, [rbx+20h]
0x180005f9c  lea     rcx, [rsp+160h+var_120]
0x180005fa1  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180005fa6  mov     rdi, [rsp+160h+var_120]
0x180005fab  test    rdi, rdi
0x180005fae  jz      short loc_180005FB5
0x180005fb0  mov     rcx, [rdi]
0x180005fb3  jmp     short loc_180005FB8
0x180005fb5  mov     rcx, r14; Str
0x180005fb8  lea     rdx, aIgnorehwsernum; "IgnoreHWSerNum"
0x180005fbf  call    cs:__imp_wcsstr
0x180005fc5  test    rax, rax
0x180005fc8  jz      short loc_180005FF8
0x180005fca  test    rdi, rdi
0x180005fcd  jz      short loc_180005FD4
0x180005fcf  mov     rdx, [rdi]
0x180005fd2  jmp     short loc_180005FD7
0x180005fd4  mov     rdx, r14; unsigned __int16 *
0x180005fd7  mov     dword ptr [rsp+160h+var_130], r14d
0x180005fdc  lea     r9, [rsp+160h+var_130]; unsigned __int8 *
0x180005fe1  mov     r8d, r12d; unsigned int
0x180005fe4  lea     rcx, [rbp+60h+var_C8]; this
0x180005fe8  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x180005fed  cmp     dword ptr [rsp+160h+var_130], r14d
0x180005ff2  jnz     loc_180006153
0x180005ff8  mov     rcx, [rbx+10h]
0x180005ffc  cmp     [rcx+19h], r14b
0x180006000  jz      short loc_180006023
0x180006002  mov     rax, [rbx+8]
0x180006006  jmp     short loc_180006015
0x180006008  cmp     rbx, [rax+10h]
0x18000600c  jnz     short loc_18000601B
0x18000600e  mov     rbx, rax
0x180006011  mov     rax, [rax+8]
0x180006015  cmp     [rax+19h], r14b
0x180006019  jz      short loc_180006008
0x18000601b  mov     rbx, rax
0x18000601e  jmp     loc_180005F8E
0x180006023  mov     rbx, rcx
0x180006026  mov     rcx, [rcx]
0x180006029  cmp     [rcx+19h], r14b
0x18000602d  jnz     loc_180005F8E
0x180006033  mov     rbx, rcx
0x180006036  mov     rax, [rcx]
0x180006039  mov     rcx, rax
0x18000603c  cmp     [rax+19h], r14b
0x180006040  jz      short loc_180006033
0x180006042  jmp     loc_180005F8E
0x180006047  cmp     dword ptr [rsp+160h+var_130], r14d
0x18000604c  jnz     loc_180006153
0x180006052  lea     rcx, [rsp+160h+var_E8]
0x180006057  call    ??0?$set@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@@std@@QEAA@XZ; std::set<_bstr_t>::set<_bstr_t>(void)
0x18000605c  nop
0x18000605d  mov     [rsp+160h+var_118], r14
0x180006062  lea     rdx, [rsp+160h+var_E8]
0x180006067  lea     rcx, [rbp+60h+var_C8]; this
0x18000606b  call    ?EnumerateChildKeyNames@CRegistryKey@@QEAAXAEAV?$set@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@@std@@@Z; CRegistryKey::EnumerateChildKeyNames(std::set<_bstr_t> &)
0x180006070  mov     rbx, [rsp+160h+var_E8]
0x180006075  mov     rbx, [rbx]
0x180006078  cmp     rbx, [rsp+160h+var_E8]
0x18000607d  jz      loc_18000613D
0x180006083  lea     rdx, [rbx+20h]
0x180006087  lea     rcx, [rsp+160h+var_118]
0x18000608c  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180006091  mov     rax, [rsp+160h+var_118]
0x180006096  test    rax, rax
0x180006099  jz      short loc_1800060A0
0x18000609b  mov     r8, [rax]
0x18000609e  jmp     short loc_1800060A3
0x1800060a0  mov     r8, r14; unsigned __int16 *
0x1800060a3  mov     r9d, 20019h; unsigned int
0x1800060a9  mov     rdx, [rbp+60h+var_C8]; HKEY
0x1800060ad  lea     rcx, [rsp+160h+phkResult]; phkResult
0x1800060b2  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x1800060b7  nop
0x1800060b8  mov     dword ptr [rsp+160h+var_130], r14d
0x1800060bd  lea     r9, [rsp+160h+var_130]; unsigned __int8 *
0x1800060c2  mov     r8d, r12d; unsigned int
0x1800060c5  lea     rdx, aIgnorehwsernum; "IgnoreHWSerNum"
0x1800060cc  lea     rcx, [rsp+160h+phkResult]; this
0x1800060d1  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x1800060d6  nop
0x1800060d7  lea     rcx, [rsp+160h+phkResult]; this
0x1800060dc  cmp     dword ptr [rsp+160h+var_130], r14d
0x1800060e1  jnz     short loc_180006137
0x1800060e3  call    ??1CRegistryKey@@QEAA@XZ; CRegistryKey::~CRegistryKey(void)
0x1800060e8  mov     rcx, [rbx+10h]
0x1800060ec  cmp     [rcx+19h], r14b
0x1800060f0  jz      short loc_180006113
0x1800060f2  mov     rax, [rbx+8]
0x1800060f6  jmp     short loc_180006105
0x1800060f8  cmp     rbx, [rax+10h]
0x1800060fc  jnz     short loc_18000610B
0x1800060fe  mov     rbx, rax
0x180006101  mov     rax, [rax+8]
0x180006105  cmp     [rax+19h], r14b
0x180006109  jz      short loc_1800060F8
0x18000610b  mov     rbx, rax
0x18000610e  jmp     loc_180006078
0x180006113  mov     rbx, rcx
0x180006116  mov     rcx, [rcx]
0x180006119  cmp     [rcx+19h], r14b
0x18000611d  jnz     loc_180006078
0x180006123  mov     rbx, rcx
0x180006126  mov     rax, [rcx]
0x180006129  mov     rcx, rax
0x18000612c  cmp     [rax+19h], r14b
0x180006130  jz      short loc_180006123
0x180006132  jmp     loc_180006078
0x180006137  call    ??1CRegistryKey@@QEAA@XZ; CRegistryKey::~CRegistryKey(void)
0x18000613c  nop
0x18000613d  lea     rcx, [rsp+160h+var_118]; this
0x180006142  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180006147  nop
0x180006148  lea     rcx, [rsp+160h+var_E8]
0x18000614d  call    ??1?$_Tree@V?$_Tset_traits@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::~_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>(void)
0x180006152  nop
0x180006153  lea     rcx, [rsp+160h+var_120]; this
0x180006158  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000615d  nop
0x18000615e  lea     rcx, [rbp+60h+var_C8]; this
0x180006162  call    ??1CRegistryKey@@QEAA@XZ; CRegistryKey::~CRegistryKey(void)
0x180006167  nop
0x180006168  lea     rcx, [rbp+60h+var_D8]
0x18000616c  call    ??1?$_Tree@V?$_Tset_traits@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::~_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>(void)
0x180006171  mov     dword ptr [rsp+160h+var_128], r14d
0x180006176  lea     rbx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Usb"...
0x18000617d  mov     rdx, rbx; unsigned __int16 *
0x180006180  mov     rcx, r15; HKEY
0x180006183  call    ?KeyExists@CRegistryKey@@SAEPEAUHKEY__@@PEBG@Z; CRegistryKey::KeyExists(HKEY__ *,ushort const *)
0x180006188  mov     edi, 3
0x18000618d  test    al, al
0x18000618f  jz      short loc_1800061E4
0x180006191  mov     r9d, edi; unsigned int
0x180006194  mov     r8, rbx; unsigned __int16 *
0x180006197  mov     rdx, r15; HKEY
0x18000619a  lea     rcx, [rsp+160h+phkResult]; phkResult
0x18000619f  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x1800061a4  nop
0x1800061a5  mov     dword ptr [rsp+160h+var_128], r14d
0x1800061aa  lea     r9, [rsp+160h+var_128]; unsigned __int8 *
0x1800061af  mov     r8d, r12d; unsigned int
0x1800061b2  lea     rdx, aApiusage; "APIUsage"
0x1800061b9  lea     rcx, [rsp+160h+phkResult]; this
0x1800061be  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x1800061c3  test    sil, sil
0x1800061c6  jnz     short loc_1800061DA
0x1800061c8  lea     rdx, aApiusage; "APIUsage"
0x1800061cf  lea     rcx, [rsp+160h+phkResult]; this
0x1800061d4  call    ?SetUlongValue@CRegistryKey@@QEAAXPEBGK@Z; CRegistryKey::SetUlongValue(ushort const *,ulong)
0x1800061d9  nop
0x1800061da  lea     rcx, [rsp+160h+phkResult]; this
0x1800061df  call    ??1CRegistryKey@@QEAA@XZ; CRegistryKey::~CRegistryKey(void)
0x1800061e4  mov     dword ptr [rsp+160h+var_12C], r14d
0x1800061e9  mov     rdx, rbx; unsigned __int16 *
0x1800061ec  mov     rcx, r15; HKEY
0x1800061ef  call    ?KeyExists@CRegistryKey@@SAEPEAUHKEY__@@PEBG@Z; CRegistryKey::KeyExists(HKEY__ *,ushort const *)
0x1800061f4  test    al, al
0x1800061f6  jz      short loc_18000624B
0x1800061f8  mov     r9d, edi; unsigned int
0x1800061fb  mov     r8, rbx; unsigned __int16 *
0x1800061fe  mov     rdx, r15; HKEY
0x180006201  lea     rcx, [rsp+160h+phkResult]; phkResult
0x180006206  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x18000620b  nop
0x18000620c  mov     dword ptr [rsp+160h+var_12C], r14d
0x180006211  lea     r9, [rsp+160h+var_12C]; unsigned __int8 *
0x180006216  mov     r8d, r12d; unsigned int
0x180006219  lea     rdx, aUsbinformation; "UsbInformation"
0x180006220  lea     rcx, [rsp+160h+phkResult]; this
0x180006225  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x18000622a  test    sil, sil
0x18000622d  jnz     short loc_180006241
0x18000622f  lea     rdx, aUsbinformation; "UsbInformation"
0x180006236  lea     rcx, [rsp+160h+phkResult]; this
0x18000623b  call    ?SetUlongValue@CRegistryKey@@QEAAXPEBGK@Z; CRegistryKey::SetUlongValue(ushort const *,ulong)
0x180006240  nop
0x180006241  lea     rcx, [rsp+160h+phkResult]; this
0x180006246  call    ??1CRegistryKey@@QEAA@XZ; CRegistryKey::~CRegistryKey(void)
0x18000624b  mov     eax, cs:dword_18001C038
0x180006251  cmp     eax, 5
0x180006254  jbe     loc_1800062FC
0x18000625a  lea     rcx, dword_18001C038
0x180006261  call    _tlgKeywordOn
0x180006266  test    al, al
0x180006268  jz      loc_1800062FC
0x18000626e  mov     eax, dword ptr [rsp+160h+var_12C]
0x180006272  mov     [rsp+160h+var_110], eax
0x180006276  mov     eax, dword ptr [rsp+160h+var_128]
0x18000627a  mov     [rsp+160h+var_10C], eax
0x18000627e  mov     eax, dword ptr [rsp+160h+var_130]
0x180006282  mov     dword ptr [rsp+160h+var_120], eax
0x180006286  mov     eax, dword ptr [rsp+160h+var_124]
0x18000628a  mov     dword ptr [rsp+160h+var_118], eax
0x18000628e  lea     rax, [rsp+160h+var_110]
0x180006293  mov     [rbp+60h+var_50], rax
0x180006297  mov     [rbp+60h+var_48], 4
0x18000629f  lea     rax, [rsp+160h+var_10C]
0x1800062a4  mov     [rbp+60h+var_60], rax
0x1800062a8  mov     [rbp+60h+var_58], 4
0x1800062b0  lea     rax, [rsp+160h+var_120]
0x1800062b5  mov     [rbp+60h+var_70], rax
0x1800062b9  mov     [rbp+60h+var_68], 4
0x1800062c1  lea     rax, [rsp+160h+var_118]
0x1800062c6  mov     [rbp+60h+var_80], rax
0x1800062ca  mov     [rbp+60h+var_78], 4
0x1800062d2  lea     rax, [rbp+60h+var_A0]
0x1800062d6  mov     [rsp+160h+var_138], rax
0x1800062db  mov     [rsp+160h+var_140], 6
0x1800062e3  xor     r9d, r9d
0x1800062e6  xor     r8d, r8d
0x1800062e9  lea     rdx, word_180017B66
0x1800062f0  lea     rcx, dword_18001C038
0x1800062f7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800062fc  mov     rcx, [rbp+60h+var_40]
0x180006300  xor     rcx, rsp; StackCookie
0x180006303  call    __security_check_cookie
0x180006308  add     rsp, 130h
0x18000630f  pop     r15
0x180006311  pop     r14
0x180006313  pop     r12
0x180006315  pop     rdi
0x180006316  pop     rsi
0x180006317  pop     rbx
0x180006318  pop     rbp
0x180006319  retn
```
