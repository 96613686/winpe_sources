# LogMachineCount(void)

- ea: `0x180007754`
- end: `0x1800078d7`
- name: `?LogMachineCount@@YAXXZ`
- size: `387`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x180005da0`

## callees

- `0x180001294`
- `0x180001990`
- `0x180002410`
- `0x180003fec`
- `0x180005cb8`
- `0x180005ce4`
- `0x180005d58`
- `0x180007754`
- `0x18000bc7c`
- `0x18000bd24`
- `0x18000c01c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800077f8`
- `ntdll!RtlInitUnicodeString` at `0x1800077f8`
- `ntdll!RtlGUIDFromString` at `0x180007806`
- `ntdll!RtlGUIDFromString` at `0x180007806`

## string_xrefs

- `0x180007790`: `System\HardwareConfig`

## pseudocode

```c
void LogMachineCount(void)
{
  __int64 v0; // rdx
  __int64 v1; // r8
  __int64 v2; // r9
  int v3; // edi
  __int64 *v4; // rbx
  const WCHAR *v5; // rdx
  NTSTATUS v6; // eax
  int v7; // ecx
  __int64 **v8; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+30h] [rbp-19h] BYREF
  const WCHAR **v14; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v15[2]; // [rsp+40h] [rbp-9h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+7h] BYREF
  HKEY phkResult[4]; // [rsp+60h] [rbp+17h] BYREF
  GUID Guid; // [rsp+80h] [rbp+37h] BYREF

  std::set<_bstr_t>::set<_bstr_t>(v15);
  Guid = 0;
  CRegistryKey::CRegistryKey(phkResult, HKEY_LOCAL_MACHINE, L"System\\HardwareConfig");
  v14 = 0;
  DestinationString = 0;
  CRegistryKey::EnumerateChildKeyNames((CRegistryKey *)phkResult, (__int64)v15);
  v3 = 0;
  v4 = *(__int64 **)v15[0];
  while ( v4 != (__int64 *)v15[0] )
  {
    _bstr_t::operator=((_bstr_t *)&v14, (__int64)(v4 + 4));
    if ( v14 )
      v5 = *v14;
    else
      v5 = 0;
    RtlInitUnicodeString(&DestinationString, v5);
    v6 = RtlGUIDFromString(&DestinationString, &Guid);
    v7 = v3 + 1;
    if ( v6 < 0 )
      v7 = v3;
    v3 = v7;
    v8 = (__int64 **)v4[2];
    if ( *((_BYTE *)v8 + 25) )
    {
      for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v4 = i;
      v4 = i;
    }
    else
    {
      v4 = (__int64 *)v4[2];
      for ( j = *v8; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v4 = j;
    }
  }
  if ( (unsigned int)dword_18001C000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18001C000, v0, v1, v2) )
  {
    v13 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18001C000,
      (__int64)&word_180017D3E,
      v11,
      v12,
      (__int64)&v13);
  }
  _bstr_t::_Free((_bstr_t *)&v14);
  CRegistryKey::~CRegistryKey(phkResult);
  std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::~_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>(v15);
}

```

## disassembly

```asm
0x180007754  mov     [rsp-8+arg_0], rbx
0x180007759  mov     [rsp-8+arg_8], rdi
0x18000775e  push    rbp
0x18000775f  lea     rbp, [rsp-57h]
0x180007764  sub     rsp, 0A0h
0x18000776b  mov     rax, cs:__security_cookie
0x180007772  xor     rax, rsp
0x180007775  mov     [rbp+57h+var_10], rax
0x180007779  lea     rcx, [rbp+57h+var_60]
0x18000777d  call    ??0?$set@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@@std@@QEAA@XZ; std::set<_bstr_t>::set<_bstr_t>(void)
0x180007782  nop
0x180007783  xorps   xmm0, xmm0
0x180007786  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x18000778a  mov     r9d, 20019h; unsigned int
0x180007790  lea     r8, aSystemHardware; "System\\HardwareConfig"
0x180007797  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18000779e  lea     rcx, [rbp+57h+phkResult]; phkResult
0x1800077a2  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x1800077a7  nop
0x1800077a8  mov     [rbp+57h+var_68], 0
0x1800077b0  xorps   xmm0, xmm0
0x1800077b3  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800077b7  lea     rdx, [rbp+57h+var_60]
0x1800077bb  lea     rcx, [rbp+57h+phkResult]; this
0x1800077bf  call    ?EnumerateChildKeyNames@CRegistryKey@@QEAAXAEAV?$set@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@@std@@@Z; CRegistryKey::EnumerateChildKeyNames(std::set<_bstr_t> &)
0x1800077c4  xor     edi, edi
0x1800077c6  mov     rbx, [rbp+57h+var_60]
0x1800077ca  mov     rbx, [rbx]
0x1800077cd  cmp     rbx, [rbp+57h+var_60]
0x1800077d1  jz      loc_18000785E
0x1800077d7  lea     rdx, [rbx+20h]
0x1800077db  lea     rcx, [rbp+57h+var_68]
0x1800077df  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x1800077e4  mov     rax, [rbp+57h+var_68]
0x1800077e8  test    rax, rax
0x1800077eb  jz      short loc_1800077F2
0x1800077ed  mov     rdx, [rax]
0x1800077f0  jmp     short loc_1800077F4
0x1800077f2  xor     edx, edx; SourceString
0x1800077f4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800077f8  call    cs:__imp_RtlInitUnicodeString
0x1800077fe  lea     rdx, [rbp+57h+Guid]; Guid
0x180007802  lea     rcx, [rbp+57h+DestinationString]; GuidString
0x180007806  call    cs:__imp_RtlGUIDFromString
0x18000780c  lea     ecx, [rdi+1]
0x18000780f  test    eax, eax
0x180007811  cmovs   ecx, edi
0x180007814  mov     edi, ecx
0x180007816  mov     rcx, [rbx+10h]
0x18000781a  cmp     byte ptr [rcx+19h], 0
0x18000781e  jz      short loc_18000783E
0x180007820  mov     rax, [rbx+8]
0x180007824  jmp     short loc_180007833
0x180007826  cmp     rbx, [rax+10h]
0x18000782a  jnz     short loc_180007839
0x18000782c  mov     rbx, rax
0x18000782f  mov     rax, [rax+8]
0x180007833  cmp     byte ptr [rax+19h], 0
0x180007837  jz      short loc_180007826
0x180007839  mov     rbx, rax
0x18000783c  jmp     short loc_1800077CD
0x18000783e  mov     rbx, rcx
0x180007841  mov     rcx, [rcx]
0x180007844  cmp     byte ptr [rcx+19h], 0
0x180007848  jnz     short loc_1800077CD
0x18000784a  mov     rbx, rcx
0x18000784d  mov     rax, [rcx]
0x180007850  mov     rcx, rax
0x180007853  cmp     byte ptr [rax+19h], 0
0x180007857  jz      short loc_18000784A
0x180007859  jmp     loc_1800077CD
0x18000785e  mov     eax, cs:dword_18001C000
0x180007864  cmp     eax, 5
0x180007867  jbe     short loc_180007899
0x180007869  lea     rcx, dword_18001C000
0x180007870  call    _tlgKeywordOn
0x180007875  test    al, al
0x180007877  jz      short loc_180007899
0x180007879  mov     [rbp+57h+var_70], edi
0x18000787c  lea     rax, [rbp+57h+var_70]
0x180007880  mov     [rsp+0A0h+var_80], rax
0x180007885  lea     rdx, word_180017D3E
0x18000788c  lea     rcx, dword_18001C000
0x180007893  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180007898  nop
0x180007899  lea     rcx, [rbp+57h+var_68]; this
0x18000789d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800078a2  nop
0x1800078a3  lea     rcx, [rbp+57h+phkResult]; this
0x1800078a7  call    ??1CRegistryKey@@QEAA@XZ; CRegistryKey::~CRegistryKey(void)
0x1800078ac  nop
0x1800078ad  lea     rcx, [rbp+57h+var_60]
0x1800078b1  call    ??1?$_Tree@V?$_Tset_traits@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::~_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>(void)
0x1800078b6  mov     rcx, [rbp+57h+var_10]
0x1800078ba  xor     rcx, rsp; StackCookie
0x1800078bd  call    __security_check_cookie
0x1800078c2  lea     r11, [rsp+0A0h+var_s0]
0x1800078ca  mov     rbx, [r11+10h]
0x1800078ce  mov     rdi, [r11+18h]
0x1800078d2  mov     rsp, r11
0x1800078d5  pop     rbp
0x1800078d6  retn
```
