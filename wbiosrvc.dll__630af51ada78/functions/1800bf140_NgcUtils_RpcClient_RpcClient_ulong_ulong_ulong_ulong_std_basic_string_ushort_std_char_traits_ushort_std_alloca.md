# NgcUtils::RpcClient::RpcClient(ulong,ulong,ulong,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_SID const *,void * const)

- ea: `0x1800bf140`
- end: `0x1800bf3dd`
- name: `??0RpcClient@NgcUtils@@QEAA@KKKKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_SID@@QEAX@Z`
- size: `669`
- prototype: `__int64 __fastcall(__int64, int, int, int, DWORD, __int64, PSID pSid, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800baeb4`

## callees

- `0x180014894`
- `0x18002d3b4`
- `0x180044b1c`
- `0x180046aa8`
- `0x180069cc8`
- `0x180069cd4`
- `0x1800bf140`
- `0x1800bf420`
- `0x1800bf7c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800bf163`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800bf163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf2b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf2b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf37a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800bf1ce`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800bf1ce`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800bf242`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800bf242`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bf1df`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bf1df`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bf295`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bf295`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::RpcClient::RpcClient(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        DWORD a5,
        __int64 a6,
        PSID pSid,
        __int64 a8)
{
  PSID *v12; // rdi
  PSECURITY_DESCRIPTOR *v13; // r15
  PSID v14; // rsi
  DWORD LengthSid; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  DWORD v18; // r12d
  char *v19; // rdx
  __int64 v20; // r15
  unsigned __int64 v21; // rcx
  size_t v22; // rbx
  int v23; // eax
  __int64 v24; // rbx
  const WCHAR *v25; // rax
  DWORD v27; // ebx
  __int64 v28; // r9
  DWORD LastError; // ebx
  __int64 v30; // r9
  DWORD v31; // ebx
  __int64 v32; // r9
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF

  InitializeSRWLock((PSRWLOCK)a1);
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 24) = a2;
  *(_DWORD *)(a1 + 28) = a3;
  *(_DWORD *)(a1 + 32) = a4;
  *(_DWORD *)(a1 + 36) = a5;
  *(_QWORD *)(a1 + 40) = a8;
  *(_DWORD *)(a1 + 48) = 0;
  v12 = (PSID *)(a1 + 56);
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  v13 = (PSECURITY_DESCRIPTOR *)(a1 + 88);
  *(_QWORD *)(a1 + 88) = 0;
  v14 = pSid;
  if ( pSid )
  {
    if ( !IsValidSid(pSid) )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_18010F170 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0) )
      {
        a5 = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18010F170,
          (unsigned __int8 *)byte_1800F9F59,
          0,
          v30,
          (__int64)&a5);
      }
      win32_exception::win32_exception((win32_exception *)pExceptionObject, LastError);
      throw (win32_exception *)pExceptionObject;
    }
    LengthSid = GetLengthSid(v14);
    v18 = LengthSid;
    v19 = (char *)*v12;
    v20 = *(_QWORD *)(a1 + 64);
    v21 = v20 - *(_QWORD *)(a1 + 56);
    if ( LengthSid >= v21 )
    {
      if ( LengthSid > v21 )
      {
        if ( (unsigned __int64)LengthSid <= *(_QWORD *)(a1 + 72) - (_QWORD)v19 )
        {
          v22 = LengthSid - v21;
          memset_0(*(void **)(a1 + 64), 0, v22);
          *(_QWORD *)(a1 + 64) = v22 + v20;
        }
        else
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v12, LengthSid, v16, v17);
        }
      }
    }
    else
    {
      *(_QWORD *)(a1 + 64) = &v19[LengthSid];
    }
    if ( !CopySid(v18, *v12, v14) )
    {
      v31 = GetLastError();
      if ( (unsigned int)dword_18010F170 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0) )
      {
        a5 = v31;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18010F170,
          (unsigned __int8 *)byte_1800F9F25,
          0,
          v32,
          (__int64)&a5);
      }
      win32_exception::win32_exception((win32_exception *)pExceptionObject, v31);
      throw (win32_exception *)pExceptionObject;
    }
    v13 = (PSECURITY_DESCRIPTOR *)(a1 + 88);
    if ( *(_DWORD *)(a1 + 24) == 3 )
    {
      v23 = *(_DWORD *)(a1 + 28);
      if ( (v23 & 1) != 0 )
        *(_DWORD *)(a1 + 28) = v23 | 0x10;
    }
  }
  v24 = a6;
  if ( *(_QWORD *)(a6 + 16) )
  {
    Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(a1 + 80);
    v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v25, 1u, v13, 0) )
    {
      v27 = GetLastError();
      if ( (unsigned int)dword_18010F170 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0) )
      {
        a5 = v27;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18010F170,
          (unsigned __int8 *)byte_1800F9EE5,
          0,
          v28,
          (__int64)&a5);
      }
      win32_exception::win32_exception((win32_exception *)pExceptionObject, v27);
      throw (win32_exception *)pExceptionObject;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800bf140  mov     [rsp-40h+arg_0], rcx
0x1800bf145  push    rbp
0x1800bf146  push    rbx
0x1800bf147  push    rsi
0x1800bf148  push    rdi
0x1800bf149  push    r12
0x1800bf14b  push    r13
0x1800bf14d  push    r14
0x1800bf14f  push    r15
0x1800bf151  mov     rbp, rsp
0x1800bf154  sub     rsp, 58h
0x1800bf158  mov     esi, r9d
0x1800bf15b  mov     edi, r8d
0x1800bf15e  mov     ebx, edx
0x1800bf160  mov     r14, rcx
0x1800bf163  call    cs:__imp_InitializeSRWLock
0x1800bf169  lea     rax, ??_7?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable'
0x1800bf170  mov     [r14+8], rax
0x1800bf174  xor     r12d, r12d
0x1800bf177  mov     [r14+10h], r12
0x1800bf17b  mov     [r14+18h], ebx
0x1800bf17f  mov     [r14+1Ch], edi
0x1800bf183  mov     [r14+20h], esi
0x1800bf187  mov     eax, [rbp+arg_20]
0x1800bf18a  mov     [r14+24h], eax
0x1800bf18e  mov     rax, [rbp+arg_38]
0x1800bf195  mov     [r14+28h], rax
0x1800bf199  mov     [r14+30h], r12d
0x1800bf19d  lea     rdi, [r14+38h]
0x1800bf1a1  mov     [rdi], r12
0x1800bf1a4  mov     [rdi+8], r12
0x1800bf1a8  mov     [rdi+10h], r12
0x1800bf1ac  lea     rax, ??_7?$HandleT@USecurityDescriptorTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable'
0x1800bf1b3  mov     [r14+50h], rax
0x1800bf1b7  lea     r15, [r14+58h]
0x1800bf1bb  mov     [r15], r12
0x1800bf1be  mov     rsi, [rbp+pSid]
0x1800bf1c2  test    rsi, rsi
0x1800bf1c5  jz      loc_1800BF26D
0x1800bf1cb  mov     rcx, rsi; pSid
0x1800bf1ce  call    cs:__imp_IsValidSid
0x1800bf1d4  test    eax, eax
0x1800bf1d6  jz      loc_1800BF317
0x1800bf1dc  mov     rcx, rsi; pSid
0x1800bf1df  call    cs:__imp_GetLengthSid
0x1800bf1e5  mov     r12d, eax
0x1800bf1e8  mov     rdx, [rdi]
0x1800bf1eb  mov     r15, [rdi+8]
0x1800bf1ef  mov     rcx, r15
0x1800bf1f2  sub     rcx, rdx
0x1800bf1f5  mov     ebx, eax
0x1800bf1f7  cmp     r12, rcx
0x1800bf1fa  jnb     short loc_1800BF206
0x1800bf1fc  lea     rcx, [r12+rdx]
0x1800bf200  mov     [rdi+8], rcx
0x1800bf204  jmp     short loc_1800BF239
0x1800bf206  jbe     short loc_1800BF239
0x1800bf208  mov     rax, [rdi+10h]
0x1800bf20c  sub     rax, rdx
0x1800bf20f  cmp     rbx, rax
0x1800bf212  jbe     short loc_1800BF221
0x1800bf214  mov     rdx, rbx
0x1800bf217  mov     rcx, rdi
0x1800bf21a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800bf21f  jmp     short loc_1800BF239
0x1800bf221  sub     rbx, rcx
0x1800bf224  mov     r8, rbx; Size
0x1800bf227  xor     edx, edx; Val
0x1800bf229  mov     rcx, r15; void *
0x1800bf22c  call    memset_0
0x1800bf231  lea     rax, [rbx+r15]
0x1800bf235  mov     [rdi+8], rax
0x1800bf239  mov     r8, rsi; pSourceSid
0x1800bf23c  mov     rdx, [rdi]; pDestinationSid
0x1800bf23f  mov     ecx, r12d; nDestinationSidLength
0x1800bf242  call    cs:__imp_CopySid
0x1800bf248  xor     r12d, r12d
0x1800bf24b  test    eax, eax
0x1800bf24d  jz      loc_1800BF37A
0x1800bf253  lea     r15, [r14+58h]
0x1800bf257  cmp     dword ptr [r14+18h], 3
0x1800bf25c  jnz     short loc_1800BF26D
0x1800bf25e  mov     eax, [r14+1Ch]
0x1800bf262  test    al, 1
0x1800bf264  jz      short loc_1800BF26D
0x1800bf266  or      eax, 10h
0x1800bf269  mov     [r14+1Ch], eax
0x1800bf26d  mov     rbx, [rbp+arg_28]
0x1800bf271  cmp     [rbx+10h], r12
0x1800bf275  jz      short loc_1800BF29F
0x1800bf277  lea     rcx, [r14+50h]
0x1800bf27b  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x1800bf280  mov     rcx, rbx
0x1800bf283  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800bf288  xor     r9d, r9d; SecurityDescriptorSize
0x1800bf28b  mov     r8, r15; SecurityDescriptor
0x1800bf28e  lea     edx, [r9+1]; StringSDRevision
0x1800bf292  mov     rcx, rax; StringSecurityDescriptor
0x1800bf295  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800bf29b  test    eax, eax
0x1800bf29d  jz      short loc_1800BF2B3
0x1800bf29f  mov     rax, r14
0x1800bf2a2  add     rsp, 58h
0x1800bf2a6  pop     r15
0x1800bf2a8  pop     r14
0x1800bf2aa  pop     r13
0x1800bf2ac  pop     r12
0x1800bf2ae  pop     rdi
0x1800bf2af  pop     rsi
0x1800bf2b0  pop     rbx
0x1800bf2b1  pop     rbp
0x1800bf2b2  retn
0x1800bf2b3  call    cs:__imp_GetLastError
0x1800bf2b9  nop
0x1800bf2ba  mov     ebx, eax
0x1800bf2bc  mov     ecx, cs:dword_18010F170
0x1800bf2c2  cmp     ecx, 2
0x1800bf2c5  jbe     short loc_1800BF2FB
0x1800bf2c7  xor     edx, edx
0x1800bf2c9  lea     rcx, dword_18010F170
0x1800bf2d0  call    _tlgKeywordOn
0x1800bf2d5  test    al, al
0x1800bf2d7  jz      short loc_1800BF2FB
0x1800bf2d9  mov     [rbp+arg_20], ebx
0x1800bf2dc  lea     rax, [rbp+arg_20]
0x1800bf2e0  mov     [rsp+58h+var_38], rax
0x1800bf2e5  xor     r8d, r8d
0x1800bf2e8  lea     rdx, byte_1800F9EE5
0x1800bf2ef  lea     rcx, dword_18010F170
0x1800bf2f6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bf2fb  mov     edx, ebx; unsigned int
0x1800bf2fd  lea     rcx, [rbp+pExceptionObject]; this
0x1800bf301  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x1800bf306  lea     rdx, _TI3?AVwin32_exception@@; pThrowInfo
0x1800bf30d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800bf311  call    _CxxThrowException_0
0x1800bf317  call    cs:__imp_GetLastError
0x1800bf31d  mov     ebx, eax
0x1800bf31f  mov     ecx, cs:dword_18010F170
0x1800bf325  cmp     ecx, 2
0x1800bf328  jbe     short loc_1800BF35E
0x1800bf32a  xor     edx, edx
0x1800bf32c  lea     rcx, dword_18010F170
0x1800bf333  call    _tlgKeywordOn
0x1800bf338  test    al, al
0x1800bf33a  jz      short loc_1800BF35E
0x1800bf33c  mov     [rbp+arg_20], ebx
0x1800bf33f  lea     rax, [rbp+arg_20]
0x1800bf343  mov     [rsp+58h+var_38], rax
0x1800bf348  xor     r8d, r8d
0x1800bf34b  lea     rdx, byte_1800F9F59
0x1800bf352  lea     rcx, dword_18010F170
0x1800bf359  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bf35e  mov     edx, ebx; unsigned int
0x1800bf360  lea     rcx, [rbp+pExceptionObject]; this
0x1800bf364  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x1800bf369  lea     rdx, _TI3?AVwin32_exception@@; pThrowInfo
0x1800bf370  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800bf374  call    _CxxThrowException_0
0x1800bf37a  call    cs:__imp_GetLastError
0x1800bf380  mov     ebx, eax
0x1800bf382  mov     ecx, cs:dword_18010F170
0x1800bf388  cmp     ecx, 2
0x1800bf38b  jbe     short loc_1800BF3C1
0x1800bf38d  xor     edx, edx
0x1800bf38f  lea     rcx, dword_18010F170
0x1800bf396  call    _tlgKeywordOn
0x1800bf39b  test    al, al
0x1800bf39d  jz      short loc_1800BF3C1
0x1800bf39f  mov     [rbp+arg_20], ebx
0x1800bf3a2  lea     rax, [rbp+arg_20]
0x1800bf3a6  mov     [rsp+58h+var_38], rax
0x1800bf3ab  xor     r8d, r8d
0x1800bf3ae  lea     rdx, byte_1800F9F25
0x1800bf3b5  lea     rcx, dword_18010F170
0x1800bf3bc  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bf3c1  mov     edx, ebx; unsigned int
0x1800bf3c3  lea     rcx, [rbp+pExceptionObject]; this
0x1800bf3c7  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x1800bf3cc  lea     rdx, _TI3?AVwin32_exception@@; pThrowInfo
0x1800bf3d3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800bf3d7  call    _CxxThrowException_0
```
