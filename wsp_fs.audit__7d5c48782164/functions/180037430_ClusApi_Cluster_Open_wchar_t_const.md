# ClusApi::Cluster::Open(wchar_t const *)

- ea: `0x180037430`
- end: `0x18003755d`
- name: `?Open@Cluster@ClusApi@@UEAAJPEB_W@Z`
- size: `301`
- prototype: `int(ClusApi::Cluster *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000d600`
- `0x18000db2c`
- `0x180010b90`
- `0x180027b8c`
- `0x180037430`
- `0x18008f03c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037502`
- `CLUSAPI!OpenClusterEx` at `0x1800374dc`
- `CLUSAPI!OpenClusterEx` at `0x1800374dc`

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
      std::wstring::assign(v10, v6);
    }
    else
    {
      std::wstring::wstring(v11);
      HostComputerName = ClusApi::Facade::NetworkUtilities::GetHostComputerName((__int64)v11);
      if ( HostComputerName >= 0 )
        std::wstring::operator=(v10, v11);
      std::wstring::_Tidy_deallocate(v11);
      if ( HostComputerName < 0 )
        goto LABEL_13;
    }
    v7 = OpenClusterEx(a2, 0x2000000u, 0);
    cxl::AutoHandle<_HCLUSTER *,int,&int CloseCluster(_HCLUSTER *),0>::Close(v5);
    *v5 = v7;
    if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      std::wstring::operator=((char *)this + 32, v10);
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
0x180037430  mov     [rsp+arg_10], rbx
0x180037435  mov     [rsp+arg_18], rbp
0x18003743a  push    rsi
0x18003743b  push    rdi
0x18003743c  push    r14
0x18003743e  sub     rsp, 70h
0x180037442  mov     rax, cs:__security_cookie
0x180037449  xor     rax, rsp
0x18003744c  mov     [rsp+88h+var_28], rax
0x180037451  mov     rbx, rdx
0x180037454  mov     rsi, rcx
0x180037457  xor     ebp, ebp
0x180037459  mov     edi, ebp
0x18003745b  lea     r14, [rcx+18h]
0x18003745f  mov     rax, [r14]
0x180037462  inc     rax
0x180037465  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003746b  jnz     loc_180037538
0x180037471  lea     rcx, [rsp+88h+var_68]
0x180037476  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003747b  nop
0x18003747c  test    rdx, rdx
0x18003747f  jz      short loc_180037498
0x180037481  cmp     word ptr [rdx], 2Eh ; '.'
0x180037485  jz      short loc_180037498
0x180037487  cmp     [rdx], bp
0x18003748a  jz      short loc_180037498
0x18003748c  lea     rcx, [rsp+88h+var_68]
0x180037491  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180037496  jmp     short loc_1800374D1
0x180037498  lea     rcx, [rsp+88h+var_48]
0x18003749d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800374a2  nop
0x1800374a3  lea     rcx, [rsp+88h+var_48]
0x1800374a8  call    ?GetHostComputerName@NetworkUtilities@Facade@ClusApi@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ClusApi::Facade::NetworkUtilities::GetHostComputerName(std::wstring &)
0x1800374ad  mov     edi, eax
0x1800374af  test    eax, eax
0x1800374b1  js      short loc_1800374C3
0x1800374b3  lea     rdx, [rsp+88h+var_48]
0x1800374b8  lea     rcx, [rsp+88h+var_68]
0x1800374bd  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800374c2  nop
0x1800374c3  lea     rcx, [rsp+88h+var_48]
0x1800374c8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800374cd  test    edi, edi
0x1800374cf  js      short loc_18003752E
0x1800374d1  xor     r8d, r8d; GrantedAccess
0x1800374d4  mov     edx, 2000000h; DesiredAccess
0x1800374d9  mov     rcx, rbx; lpszClusterName
0x1800374dc  call    cs:__imp_OpenClusterEx
0x1800374e3  nop     dword ptr [rax+rax+00h]
0x1800374e8  mov     rbx, rax
0x1800374eb  mov     rcx, r14
0x1800374ee  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x1800374f3  mov     [r14], rbx
0x1800374f6  lea     rax, [rbx+1]
0x1800374fa  test    rax, 0FFFFFFFFFFFFFFFEh
0x180037500  jnz     short loc_18003751F
0x180037502  call    cs:__imp_GetLastError
0x180037509  nop     dword ptr [rax+rax+00h]
0x18003750e  mov     edi, eax
0x180037510  test    eax, eax
0x180037512  jle     short loc_18003752E
0x180037514  movzx   edi, ax
0x180037517  or      edi, 80070000h
0x18003751d  jmp     short loc_18003752E
0x18003751f  lea     rcx, [rsi+20h]
0x180037523  lea     rdx, [rsp+88h+var_68]
0x180037528  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003752d  nop
0x18003752e  lea     rcx, [rsp+88h+var_68]
0x180037533  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037538  mov     eax, edi
0x18003753a  mov     rcx, [rsp+88h+var_28]
0x18003753f  xor     rcx, rsp; StackCookie
0x180037542  call    __security_check_cookie
0x180037547  lea     r11, [rsp+88h+var_18]
0x18003754c  mov     rbx, [r11+30h]
0x180037550  mov     rbp, [r11+38h]
0x180037554  mov     rsp, r11
0x180037557  pop     r14
0x180037559  pop     rdi
0x18003755a  pop     rsi
0x18003755b  retn
```
