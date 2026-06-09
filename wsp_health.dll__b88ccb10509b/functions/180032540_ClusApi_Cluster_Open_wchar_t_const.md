# ClusApi::Cluster::Open(wchar_t const *)

- ea: `0x180032540`
- end: `0x180032660`
- name: `?Open@Cluster@ClusApi@@UEAAJPEB_W@Z`
- size: `288`
- prototype: `int(ClusApi::Cluster *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002ae0`
- `0x18000ca34`
- `0x18000cfb4`
- `0x18000d6dc`
- `0x18000f3e8`
- `0x18002314c`
- `0x180032540`
- `0x180050534`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003260c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003260c`
- `CLUSAPI!OpenClusterEx` at `0x1800325ec`
- `CLUSAPI!OpenClusterEx` at `0x1800325ec`

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
0x180032540  mov     [rsp+arg_10], rbx
0x180032545  mov     [rsp+arg_18], rbp
0x18003254a  push    rsi
0x18003254b  push    rdi
0x18003254c  push    r14
0x18003254e  sub     rsp, 70h
0x180032552  mov     rax, cs:__security_cookie
0x180032559  xor     rax, rsp
0x18003255c  mov     [rsp+88h+var_28], rax
0x180032561  mov     rbx, rdx
0x180032564  mov     rsi, rcx
0x180032567  xor     ebp, ebp
0x180032569  mov     edi, ebp
0x18003256b  lea     r14, [rcx+18h]
0x18003256f  mov     rax, [r14]
0x180032572  inc     rax
0x180032575  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003257b  jnz     loc_18003263C
0x180032581  lea     rcx, [rsp+88h+var_68]
0x180032586  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003258b  nop
0x18003258c  test    rdx, rdx
0x18003258f  jz      short loc_1800325A8
0x180032591  cmp     word ptr [rdx], 2Eh ; '.'
0x180032595  jz      short loc_1800325A8
0x180032597  cmp     [rdx], bp
0x18003259a  jz      short loc_1800325A8
0x18003259c  lea     rcx, [rsp+88h+var_68]
0x1800325a1  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800325a6  jmp     short loc_1800325E1
0x1800325a8  lea     rcx, [rsp+88h+var_48]
0x1800325ad  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800325b2  nop
0x1800325b3  lea     rcx, [rsp+88h+var_48]
0x1800325b8  call    ?GetHostComputerName@NetworkUtilities@Facade@ClusApi@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ClusApi::Facade::NetworkUtilities::GetHostComputerName(std::wstring &)
0x1800325bd  mov     edi, eax
0x1800325bf  test    eax, eax
0x1800325c1  js      short loc_1800325D3
0x1800325c3  lea     rdx, [rsp+88h+var_48]
0x1800325c8  lea     rcx, [rsp+88h+var_68]
0x1800325cd  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800325d2  nop
0x1800325d3  lea     rcx, [rsp+88h+var_48]
0x1800325d8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800325dd  test    edi, edi
0x1800325df  js      short loc_180032632
0x1800325e1  xor     r8d, r8d; GrantedAccess
0x1800325e4  mov     edx, 2000000h; DesiredAccess
0x1800325e9  mov     rcx, rbx; lpszClusterName
0x1800325ec  call    cs:__imp_OpenClusterEx
0x1800325f2  mov     rbx, rax
0x1800325f5  mov     rcx, r14
0x1800325f8  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x1800325fd  mov     [r14], rbx
0x180032600  lea     rax, [rbx+1]
0x180032604  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003260a  jnz     short loc_180032623
0x18003260c  call    cs:__imp_GetLastError
0x180032612  mov     edi, eax
0x180032614  test    eax, eax
0x180032616  jle     short loc_180032632
0x180032618  movzx   edi, ax
0x18003261b  or      edi, 80070000h
0x180032621  jmp     short loc_180032632
0x180032623  lea     rcx, [rsi+20h]
0x180032627  lea     rdx, [rsp+88h+var_68]
0x18003262c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180032631  nop
0x180032632  lea     rcx, [rsp+88h+var_68]
0x180032637  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003263c  mov     eax, edi
0x18003263e  mov     rcx, [rsp+88h+var_28]
0x180032643  xor     rcx, rsp; StackCookie
0x180032646  call    __security_check_cookie
0x18003264b  lea     r11, [rsp+88h+var_18]
0x180032650  mov     rbx, [r11+30h]
0x180032654  mov     rbp, [r11+38h]
0x180032658  mov     rsp, r11
0x18003265b  pop     r14
0x18003265d  pop     rdi
0x18003265e  pop     rsi
0x18003265f  retn
```
