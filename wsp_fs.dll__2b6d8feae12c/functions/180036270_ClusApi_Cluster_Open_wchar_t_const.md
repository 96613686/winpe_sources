# ClusApi::Cluster::Open(wchar_t const *)

- ea: `0x180036270`
- end: `0x180036390`
- name: `?Open@Cluster@ClusApi@@UEAAJPEB_W@Z`
- size: `288`
- prototype: `int(ClusApi::Cluster *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000d298`
- `0x18000d794`
- `0x18001072c`
- `0x180026e8c`
- `0x180036270`
- `0x18008cdb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003633c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003633c`
- `CLUSAPI!OpenClusterEx` at `0x18003631c`
- `CLUSAPI!OpenClusterEx` at `0x18003631c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ClusApi::Cluster::Open(ClusApi::Cluster *this, const wchar_t *a2)
{
  int HostComputerName; // edi
  HCLUSTER *v5; // r14
  _WORD *v6; // rdx
  HCLUSTER v7; // rbx
  signed int LastError; // eax
  _BYTE v10[32]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-48h] BYREF

  HostComputerName = 0;
  v5 = (HCLUSTER *)((char *)this + 24);
  if ( ((*((_QWORD *)this + 3) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    std::wstring::wstring(v10);
    if ( v6 && *v6 != 46 && *v6 )
    {
      std::wstring::assign(v10);
    }
    else
    {
      std::wstring::wstring(v11);
      HostComputerName = ClusApi::Facade::NetworkUtilities::GetHostComputerName((__int64)v11);
      if ( HostComputerName >= 0 )
        std::wstring::operator=(v10);
      std::wstring::_Tidy_deallocate(v11);
      if ( HostComputerName < 0 )
        goto LABEL_13;
    }
    v7 = OpenClusterEx(a2, 0x2000000u, 0);
    cxl::AutoHandle<_HCLUSTER *,int,&int CloseCluster(_HCLUSTER *),0>::Close(v5);
    *v5 = v7;
    if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      std::wstring::operator=((char *)this + 32);
    }
    else
    {
      LastError = GetLastError();
      HostComputerName = LastError;
      if ( LastError > 0 )
        HostComputerName = (unsigned __int16)LastError | 0x80070000;
    }
LABEL_13:
    std::wstring::_Tidy_deallocate(v10);
  }
  return (unsigned int)HostComputerName;
}

```

## disassembly

```asm
0x180036270  mov     [rsp+arg_10], rbx
0x180036275  mov     [rsp+arg_18], rbp
0x18003627a  push    rsi
0x18003627b  push    rdi
0x18003627c  push    r14
0x18003627e  sub     rsp, 70h
0x180036282  mov     rax, cs:__security_cookie
0x180036289  xor     rax, rsp
0x18003628c  mov     [rsp+88h+var_28], rax
0x180036291  mov     rbx, rdx
0x180036294  mov     rsi, rcx
0x180036297  xor     ebp, ebp
0x180036299  mov     edi, ebp
0x18003629b  lea     r14, [rcx+18h]
0x18003629f  mov     rax, [r14]
0x1800362a2  inc     rax
0x1800362a5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800362ab  jnz     loc_18003636C
0x1800362b1  lea     rcx, [rsp+88h+var_68]
0x1800362b6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800362bb  nop
0x1800362bc  test    rdx, rdx
0x1800362bf  jz      short loc_1800362D8
0x1800362c1  cmp     word ptr [rdx], 2Eh ; '.'
0x1800362c5  jz      short loc_1800362D8
0x1800362c7  cmp     [rdx], bp
0x1800362ca  jz      short loc_1800362D8
0x1800362cc  lea     rcx, [rsp+88h+var_68]
0x1800362d1  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800362d6  jmp     short loc_180036311
0x1800362d8  lea     rcx, [rsp+88h+var_48]
0x1800362dd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800362e2  nop
0x1800362e3  lea     rcx, [rsp+88h+var_48]
0x1800362e8  call    ?GetHostComputerName@NetworkUtilities@Facade@ClusApi@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ClusApi::Facade::NetworkUtilities::GetHostComputerName(std::wstring &)
0x1800362ed  mov     edi, eax
0x1800362ef  test    eax, eax
0x1800362f1  js      short loc_180036303
0x1800362f3  lea     rdx, [rsp+88h+var_48]
0x1800362f8  lea     rcx, [rsp+88h+var_68]
0x1800362fd  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180036302  nop
0x180036303  lea     rcx, [rsp+88h+var_48]
0x180036308  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003630d  test    edi, edi
0x18003630f  js      short loc_180036362
0x180036311  xor     r8d, r8d; GrantedAccess
0x180036314  mov     edx, 2000000h; DesiredAccess
0x180036319  mov     rcx, rbx; lpszClusterName
0x18003631c  call    cs:__imp_OpenClusterEx
0x180036322  mov     rbx, rax
0x180036325  mov     rcx, r14
0x180036328  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x18003632d  mov     [r14], rbx
0x180036330  lea     rax, [rbx+1]
0x180036334  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003633a  jnz     short loc_180036353
0x18003633c  call    cs:__imp_GetLastError
0x180036342  mov     edi, eax
0x180036344  test    eax, eax
0x180036346  jle     short loc_180036362
0x180036348  movzx   edi, ax
0x18003634b  or      edi, 80070000h
0x180036351  jmp     short loc_180036362
0x180036353  lea     rcx, [rsi+20h]
0x180036357  lea     rdx, [rsp+88h+var_68]
0x18003635c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180036361  nop
0x180036362  lea     rcx, [rsp+88h+var_68]
0x180036367  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003636c  mov     eax, edi
0x18003636e  mov     rcx, [rsp+88h+var_28]
0x180036373  xor     rcx, rsp; StackCookie
0x180036376  call    __security_check_cookie
0x18003637b  lea     r11, [rsp+88h+var_18]
0x180036380  mov     rbx, [r11+30h]
0x180036384  mov     rbp, [r11+38h]
0x180036388  mov     rsp, r11
0x18003638b  pop     r14
0x18003638d  pop     rdi
0x18003638e  pop     rsi
0x18003638f  retn
```
