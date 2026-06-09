# ClusApi::Cluster::Open(wchar_t const *)

- ea: `0x1800335f0`
- end: `0x18003371d`
- name: `?Open@Cluster@ClusApi@@UEAAJPEB_W@Z`
- size: `301`
- prototype: `int(ClusApi::Cluster *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002b50`
- `0x18000cde0`
- `0x18000d390`
- `0x18000daf8`
- `0x18000f89c`
- `0x180023d4c`
- `0x1800335f0`
- `0x180051f8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336c2`
- `CLUSAPI!OpenClusterEx` at `0x18003369c`
- `CLUSAPI!OpenClusterEx` at `0x18003369c`

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
0x1800335f0  mov     [rsp+arg_10], rbx
0x1800335f5  mov     [rsp+arg_18], rbp
0x1800335fa  push    rsi
0x1800335fb  push    rdi
0x1800335fc  push    r14
0x1800335fe  sub     rsp, 70h
0x180033602  mov     rax, cs:__security_cookie
0x180033609  xor     rax, rsp
0x18003360c  mov     [rsp+88h+var_28], rax
0x180033611  mov     rbx, rdx
0x180033614  mov     rsi, rcx
0x180033617  xor     ebp, ebp
0x180033619  mov     edi, ebp
0x18003361b  lea     r14, [rcx+18h]
0x18003361f  mov     rax, [r14]
0x180033622  inc     rax
0x180033625  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003362b  jnz     loc_1800336F8
0x180033631  lea     rcx, [rsp+88h+var_68]
0x180033636  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003363b  nop
0x18003363c  test    rdx, rdx
0x18003363f  jz      short loc_180033658
0x180033641  cmp     word ptr [rdx], 2Eh ; '.'
0x180033645  jz      short loc_180033658
0x180033647  cmp     [rdx], bp
0x18003364a  jz      short loc_180033658
0x18003364c  lea     rcx, [rsp+88h+var_68]
0x180033651  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180033656  jmp     short loc_180033691
0x180033658  lea     rcx, [rsp+88h+var_48]
0x18003365d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180033662  nop
0x180033663  lea     rcx, [rsp+88h+var_48]
0x180033668  call    ?GetHostComputerName@NetworkUtilities@Facade@ClusApi@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ClusApi::Facade::NetworkUtilities::GetHostComputerName(std::wstring &)
0x18003366d  mov     edi, eax
0x18003366f  test    eax, eax
0x180033671  js      short loc_180033683
0x180033673  lea     rdx, [rsp+88h+var_48]
0x180033678  lea     rcx, [rsp+88h+var_68]
0x18003367d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180033682  nop
0x180033683  lea     rcx, [rsp+88h+var_48]
0x180033688  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003368d  test    edi, edi
0x18003368f  js      short loc_1800336EE
0x180033691  xor     r8d, r8d; GrantedAccess
0x180033694  mov     edx, 2000000h; DesiredAccess
0x180033699  mov     rcx, rbx; lpszClusterName
0x18003369c  call    cs:__imp_OpenClusterEx
0x1800336a3  nop     dword ptr [rax+rax+00h]
0x1800336a8  mov     rbx, rax
0x1800336ab  mov     rcx, r14
0x1800336ae  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x1800336b3  mov     [r14], rbx
0x1800336b6  lea     rax, [rbx+1]
0x1800336ba  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800336c0  jnz     short loc_1800336DF
0x1800336c2  call    cs:__imp_GetLastError
0x1800336c9  nop     dword ptr [rax+rax+00h]
0x1800336ce  mov     edi, eax
0x1800336d0  test    eax, eax
0x1800336d2  jle     short loc_1800336EE
0x1800336d4  movzx   edi, ax
0x1800336d7  or      edi, 80070000h
0x1800336dd  jmp     short loc_1800336EE
0x1800336df  lea     rcx, [rsi+20h]
0x1800336e3  lea     rdx, [rsp+88h+var_68]
0x1800336e8  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800336ed  nop
0x1800336ee  lea     rcx, [rsp+88h+var_68]
0x1800336f3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800336f8  mov     eax, edi
0x1800336fa  mov     rcx, [rsp+88h+var_28]
0x1800336ff  xor     rcx, rsp; StackCookie
0x180033702  call    __security_check_cookie
0x180033707  lea     r11, [rsp+88h+var_18]
0x18003370c  mov     rbx, [r11+30h]
0x180033710  mov     rbp, [r11+38h]
0x180033714  mov     rsp, r11
0x180033717  pop     r14
0x180033719  pop     rdi
0x18003371a  pop     rsi
0x18003371b  retn
```
