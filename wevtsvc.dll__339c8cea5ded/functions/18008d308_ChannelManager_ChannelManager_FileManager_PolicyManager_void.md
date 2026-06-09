# ChannelManager::ChannelManager(FileManager &,PolicyManager &,void *)

- ea: `0x18008d308`
- end: `0x18008d3fa`
- name: `??0ChannelManager@@QEAA@AEAVFileManager@@AEAVPolicyManager@@PEAX@Z`
- size: `242`
- prototype: `ChannelManager *__fastcall(ChannelManager *__hidden this, struct FileManager *, struct PolicyManager *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800978a0`

## callees

- `0x18000347c`
- `0x18008d308`
- `0x180092008`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d36d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d36d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008d35f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008d35f`

## pseudocode

```c
ChannelManager *__fastcall ChannelManager::ChannelManager(
        ChannelManager *this,
        struct FileManager *a2,
        struct PolicyManager *a3,
        void *a4)
{
  DWORD LastError; // ebx
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+30h] [rbp-28h]
  DWORD v9; // [rsp+38h] [rbp-20h]
  int v10; // [rsp+3Ch] [rbp-1Ch]
  int v11; // [rsp+40h] [rbp-18h]

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = a4;
  *((_QWORD *)this + 2) = a2;
  *((_QWORD *)this + 3) = a3;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>((_QWORD *)this + 6);
  *((_BYTE *)this + 88) = 0;
  *((_QWORD *)this + 10) = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:LSG:LSD:(A;;GR;;;LS)",
          1u,
          (PSECURITY_DESCRIPTOR *)this + 10,
          0) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a49f58dc00e136e65a5fe002c08ed3b5_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v8 = 0;
    v9 = LastError;
    v10 = -1;
    v11 = 47;
    throw (EvtException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18008d308  mov     [rsp+arg_0], rcx
0x18008d30d  push    rbx
0x18008d30e  sub     rsp, 50h
0x18008d312  mov     rbx, rcx
0x18008d315  mov     qword ptr [rcx], 0
0x18008d31c  mov     [rcx+8], r9
0x18008d320  mov     [rcx+10h], rdx
0x18008d324  mov     [rcx+18h], r8
0x18008d328  mov     qword ptr [rcx+20h], 0
0x18008d330  mov     qword ptr [rcx+28h], 0
0x18008d338  add     rcx, 30h ; '0'
0x18008d33c  call    ??0?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(void)
0x18008d341  nop
0x18008d342  lea     r8, [rbx+50h]; SecurityDescriptor
0x18008d346  mov     byte ptr [rbx+58h], 0
0x18008d34a  mov     qword ptr [r8], 0
0x18008d351  xor     r9d, r9d; SecurityDescriptorSize
0x18008d354  lea     edx, [r9+1]; StringSDRevision
0x18008d358  lea     rcx, StringSecurityDescriptor; "O:LSG:LSD:(A;;GR;;;LS)"
0x18008d35f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18008d365  test    eax, eax
0x18008d367  jnz     loc_18008D3F1
0x18008d36d  call    cs:__imp_GetLastError
0x18008d373  mov     ebx, eax
0x18008d375  mov     eax, 507h
0x18008d37a  test    ebx, ebx
0x18008d37c  cmovz   ebx, eax
0x18008d37f  lea     rax, WPP_GLOBAL_Control
0x18008d386  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d38d  cmp     rcx, rax
0x18008d390  jz      short loc_18008D3B9
0x18008d392  test    dword ptr [rcx+1Ch], 800h
0x18008d399  jz      short loc_18008D3B9
0x18008d39b  cmp     byte ptr [rcx+19h], 2
0x18008d39f  jb      short loc_18008D3B9
0x18008d3a1  mov     edx, 0Ah
0x18008d3a6  mov     r9d, ebx
0x18008d3a9  lea     r8, WPP_a49f58dc00e136e65a5fe002c08ed3b5_Traceguids
0x18008d3b0  mov     rcx, [rcx+10h]
0x18008d3b4  call    WPP_SF_d
0x18008d3b9  xorps   xmm0, xmm0
0x18008d3bc  movdqu  [rsp+58h+pExceptionObject], xmm0
0x18008d3c2  mov     [rsp+58h+var_28], 0
0x18008d3cb  mov     [rsp+58h+var_20], ebx
0x18008d3cf  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x18008d3d7  mov     [rsp+58h+var_18], 2Fh ; '/'
0x18008d3df  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008d3e6  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18008d3eb  call    _CxxThrowException_0
0x18008d3f1  mov     rax, rbx
0x18008d3f4  add     rsp, 50h
0x18008d3f8  pop     rbx
0x18008d3f9  retn
```
