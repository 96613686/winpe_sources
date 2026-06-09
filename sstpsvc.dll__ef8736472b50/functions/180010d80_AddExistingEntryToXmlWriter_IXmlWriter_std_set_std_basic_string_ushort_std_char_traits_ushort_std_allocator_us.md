# AddExistingEntryToXmlWriter(IXmlWriter *,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_lessstr,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x180010d80`
- end: `0x180010fe2`
- name: `?AddExistingEntryToXmlWriter@@YAKPEAUIXmlWriter@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `610`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014900`
- `0x180015500`

## callees

- `0x180008404`
- `0x1800089dc`
- `0x180008b90`
- `0x1800106b4`
- `0x1800108d0`
- `0x180010d80`
- `0x180013524`
- `0x180013e00`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## string_xrefs

- `0x180010f42`: `AddExistingEntryToXmlWriter: WriteStartElement of IXmlWriter object failed with error %d`
- `0x180010f30`: `AddExistingEntryToXmlWriter: WriteString of IXmlWriter object failed with error %d`
- `0x180010f1e`: `AddExistingEntryToXmlWriter: WriteFullEndElement of IXmlWriter object failed with error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AddExistingEntryToXmlWriter(__int64 a1, __int64 a2)
{
  struct TenantGatewayMap *Instance; // rsi
  _QWORD *v5; // rsi
  _QWORD *i; // rdi
  _QWORD *v7; // rbx
  int v8; // r14d
  _QWORD *j; // rbx
  _QWORD *v10; // rdx
  const wchar_t *v11; // rdx
  unsigned int v12; // ebx
  _QWORD v14[5]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[8]; // [rsp+58h] [rbp-A8h] BYREF
  int v16; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v14[4] = a2;
  Instance = TenantGatewayMap::GetInstance();
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  v5 = (_QWORD *)*((_QWORD *)Instance + 2);
  for ( i = (_QWORD *)*v5; ; i = (_QWORD *)*i )
  {
    if ( i == v5 )
    {
      v12 = 0;
      goto LABEL_32;
    }
    v7 = i + 2;
    std::vector<std::wstring>::vector<std::wstring>(v14, i + 7);
    if ( *(_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::find(
                      a2,
                      v15,
                      i + 2) != *(_QWORD *)(a2 + 8) )
      goto LABEL_18;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)a1 + 216LL))(
           a1,
           0,
           L"Tenant",
           0);
    if ( v8 )
      break;
    if ( i[5] >= 8u )
      v7 = (_QWORD *)*v7;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 224LL))(a1, v7);
    if ( v8 )
    {
LABEL_21:
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_27;
      v11 = L"AddExistingEntryToXmlWriter: WriteString of IXmlWriter object failed with error %d";
      goto LABEL_25;
    }
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 136LL))(a1);
    if ( v8 )
    {
LABEL_19:
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_27;
      v11 = L"AddExistingEntryToXmlWriter: WriteFullEndElement of IXmlWriter object failed with error %d";
      goto LABEL_25;
    }
    for ( j = (_QWORD *)v14[0]; j != (_QWORD *)v14[1]; j += 5 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)a1 + 216LL))(
             a1,
             0,
             L"Gateway",
             0);
      if ( v8 )
        goto LABEL_23;
      if ( j[3] < 8u )
        v10 = j;
      else
        v10 = (_QWORD *)*j;
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 224LL))(a1, v10);
      if ( v8 )
        goto LABEL_21;
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 136LL))(a1);
      if ( v8 )
        goto LABEL_19;
    }
LABEL_18:
    std::vector<std::wstring>::_Tidy(v14);
  }
LABEL_23:
  if ( (byte_18002E903 & 8) == 0 )
    goto LABEL_27;
  v11 = L"AddExistingEntryToXmlWriter: WriteStartElement of IXmlWriter object failed with error %d";
LABEL_25:
  LOWORD(v16) = 0;
  FormatRRASErrorString(&v16, v11, (unsigned int)v8);
  if ( (byte_18002E903 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v16);
LABEL_27:
  std::vector<std::wstring>::_Tidy(v14);
  v12 = 0;
  if ( v8 < 0 )
  {
    if ( (v8 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v8;
    else
      v12 = v8;
  }
LABEL_32:
  std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(a2);
  return v12;
}

```

## disassembly

```asm
0x180010d80  mov     [rsp-8+arg_10], rbx
0x180010d85  mov     [rsp-8+arg_18], rsi
0x180010d8a  push    rbp
0x180010d8b  push    rdi
0x180010d8c  push    r13
0x180010d8e  push    r14
0x180010d90  push    r15
0x180010d92  lea     rbp, [rsp-770h]
0x180010d9a  sub     rsp, 870h
0x180010da1  mov     rax, cs:__security_cookie
0x180010da8  xor     rax, rsp
0x180010dab  mov     [rbp+790h+var_30], rax
0x180010db2  mov     r13, rdx
0x180010db5  mov     r15, rcx
0x180010db8  mov     [rsp+890h+var_840], rdx
0x180010dbd  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x180010dc2  mov     rsi, rax
0x180010dc5  xor     edx, edx; Val
0x180010dc7  mov     [rsp+890h+var_830], edx
0x180010dcb  mov     r8d, 7FCh; Size
0x180010dd1  lea     rcx, [rsp+890h+var_82C]; void *
0x180010dd6  call    memset_0
0x180010ddb  mov     rsi, [rsi+10h]
0x180010ddf  mov     rdi, [rsi]
0x180010de2  cmp     rdi, rsi
0x180010de5  jz      loc_180010FAA
0x180010deb  lea     rbx, [rdi+10h]
0x180010def  lea     rdx, [rbx+28h]
0x180010df3  lea     rcx, [rsp+890h+var_860]
0x180010df8  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180010dfd  nop
0x180010dfe  mov     r8, rbx
0x180010e01  lea     rdx, [rsp+890h+var_838]
0x180010e06  mov     rcx, r13
0x180010e09  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180010e0e  mov     rcx, [r13+8]
0x180010e12  cmp     [rax], rcx
0x180010e15  jnz     loc_180010F03
0x180010e1b  mov     rax, [r15]
0x180010e1e  xor     r9d, r9d
0x180010e21  lea     r8, aTenant; "Tenant"
0x180010e28  xor     edx, edx
0x180010e2a  mov     rcx, r15
0x180010e2d  mov     rax, [rax+0D8h]
0x180010e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e39  mov     r14d, eax
0x180010e3c  test    eax, eax
0x180010e3e  jnz     loc_180010F39
0x180010e44  mov     rax, [r15]
0x180010e47  cmp     qword ptr [rbx+18h], 8
0x180010e4c  jb      short loc_180010E51
0x180010e4e  mov     rbx, [rbx]
0x180010e51  mov     rdx, rbx
0x180010e54  mov     rcx, r15
0x180010e57  mov     rax, [rax+0E0h]
0x180010e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e63  mov     r14d, eax
0x180010e66  test    eax, eax
0x180010e68  jnz     loc_180010F27
0x180010e6e  mov     rax, [r15]
0x180010e71  mov     rcx, r15
0x180010e74  mov     rax, [rax+88h]
0x180010e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e80  mov     r14d, eax
0x180010e83  test    eax, eax
0x180010e85  jnz     loc_180010F15
0x180010e8b  mov     rbx, [rsp+890h+var_860]
0x180010e90  cmp     rbx, [rsp+890h+var_858]
0x180010e95  jz      short loc_180010F03
0x180010e97  mov     rax, [r15]
0x180010e9a  xor     r9d, r9d
0x180010e9d  lea     r8, aGateway; "Gateway"
0x180010ea4  xor     edx, edx
0x180010ea6  mov     rcx, r15
0x180010ea9  mov     rax, [rax+0D8h]
0x180010eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010eb5  mov     r14d, eax
0x180010eb8  test    eax, eax
0x180010eba  jnz     short loc_180010F39
0x180010ebc  mov     rax, [r15]
0x180010ebf  cmp     qword ptr [rbx+18h], 8
0x180010ec4  jb      short loc_180010ECB
0x180010ec6  mov     rdx, [rbx]
0x180010ec9  jmp     short loc_180010ECE
0x180010ecb  mov     rdx, rbx
0x180010ece  mov     rcx, r15
0x180010ed1  mov     rax, [rax+0E0h]
0x180010ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010edd  mov     r14d, eax
0x180010ee0  test    eax, eax
0x180010ee2  jnz     short loc_180010F27
0x180010ee4  mov     rax, [r15]
0x180010ee7  mov     rcx, r15
0x180010eea  mov     rax, [rax+88h]
0x180010ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ef6  mov     r14d, eax
0x180010ef9  test    eax, eax
0x180010efb  jnz     short loc_180010F15
0x180010efd  add     rbx, 28h ; '('
0x180010f01  jmp     short loc_180010E90
0x180010f03  lea     rcx, [rsp+890h+var_860]
0x180010f08  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180010f0d  mov     rdi, [rdi]
0x180010f10  jmp     loc_180010DE2
0x180010f15  test    cs:byte_18002E903, 8
0x180010f1c  jz      short loc_180010F7F
0x180010f1e  lea     rdx, aAddexistingent; "AddExistingEntryToXmlWriter: WriteFullE"...
0x180010f25  jmp     short loc_180010F49
0x180010f27  test    cs:byte_18002E903, 8
0x180010f2e  jz      short loc_180010F7F
0x180010f30  lea     rdx, aAddexistingent_1; "AddExistingEntryToXmlWriter: WriteStrin"...
0x180010f37  jmp     short loc_180010F49
0x180010f39  test    cs:byte_18002E903, 8
0x180010f40  jz      short loc_180010F7F
0x180010f42  lea     rdx, aAddexistingent_0; "AddExistingEntryToXmlWriter: WriteStart"...
0x180010f49  xor     eax, eax
0x180010f4b  mov     word ptr [rsp+890h+var_830], ax
0x180010f50  mov     r8d, r14d
0x180010f53  lea     rcx, [rsp+890h+var_830]
0x180010f58  call    FormatRRASErrorString
0x180010f5d  test    cs:byte_18002E903, 8
0x180010f64  jz      short loc_180010F7F
0x180010f66  lea     r8, [rsp+890h+var_830]
0x180010f6b  lea     rdx, RasSSTPSvcTraceError
0x180010f72  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010f79  call    McTemplateU0z_EventWriteTransfer
0x180010f7e  nop
0x180010f7f  lea     rcx, [rsp+890h+var_860]
0x180010f84  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180010f89  xor     ebx, ebx
0x180010f8b  test    r14d, r14d
0x180010f8e  jns     short loc_180010FAC
0x180010f90  mov     eax, r14d
0x180010f93  and     eax, 1FFF0000h
0x180010f98  cmp     eax, 70000h
0x180010f9d  jnz     short loc_180010FA5
0x180010f9f  movzx   ebx, r14w
0x180010fa3  jmp     short loc_180010FAC
0x180010fa5  mov     ebx, r14d
0x180010fa8  jmp     short loc_180010FAC
0x180010faa  xor     ebx, ebx
0x180010fac  mov     rcx, r13
0x180010faf  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(void)
0x180010fb4  mov     eax, ebx
0x180010fb6  mov     rcx, [rbp+790h+var_30]
0x180010fbd  xor     rcx, rsp; StackCookie
0x180010fc0  call    __security_check_cookie
0x180010fc5  lea     r11, [rsp+890h+var_20]
0x180010fcd  mov     rbx, [r11+40h]
0x180010fd1  mov     rsi, [r11+48h]
0x180010fd5  mov     rsp, r11
0x180010fd8  pop     r15
0x180010fda  pop     r14
0x180010fdc  pop     r13
0x180010fde  pop     rdi
0x180010fdf  pop     rbp
0x180010fe0  retn
```
