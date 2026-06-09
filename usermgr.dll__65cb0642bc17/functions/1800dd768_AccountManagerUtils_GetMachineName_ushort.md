# AccountManagerUtils::GetMachineName(ushort * *)

- ea: `0x1800dd768`
- end: `0x1800dd880`
- name: `?GetMachineName@AccountManagerUtils@@YAJPEAPEAG@Z`
- size: `280`
- prototype: `__int64 __fastcall(AccountManagerUtils *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ddc10`

## callees

- `0x1800088e8`
- `0x180014e7c`
- `0x180014e9c`
- `0x18004aa68`
- `0x180061e1c`
- `0x1800d72bc`
- `0x1800dd768`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd79e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd79e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800dd790`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800dd807`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800dd790`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800dd807`

## string_xrefs

- `0x1800dd7e2`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800dd816`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800dd862`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800dd84e`: `Expected GetComputerNameExW to fail with ERROR_MORE_DATA (actual error: %d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AccountManagerUtils::GetMachineName(AccountManagerUtils *this, unsigned __int16 **a2)
{
  DWORD v3; // ebx
  __int64 v4; // r8
  const char *v5; // r9
  int v6; // eax
  unsigned int LastError; // ebx
  LPWSTR v8; // rbx
  const char *v9; // r9
  int v11; // [rsp+20h] [rbp-18h]
  char *v12; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD nSize; // [rsp+40h] [rbp+8h] BYREF
  LPWSTR lpBuffer; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = 0;
  nSize = 0;
  v3 = 0;
  if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, 0, &nSize) || (v3 = GetLastError(), v3 != 234) )
  {
    LODWORD(v12) = v3;
    LastError = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
      (const char *)0x8000FFFFLL,
      (int)"Expected GetComputerNameExW to fail with ERROR_MORE_DATA (actual error: %d)",
      v12);
  }
  else
  {
    lpBuffer = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpBuffer,
      0);
    v6 = CamAllocBuffer<unsigned short>(nSize, (char **)&lpBuffer, v4, v5);
    LastError = v6;
    if ( v6 >= 0 )
    {
      v8 = lpBuffer;
      if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, lpBuffer, &nSize) )
      {
        lpBuffer = 0;
        *(_QWORD *)this = v8;
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xA1,
                      (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
                      v9);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
        (const char *)(unsigned int)v6,
        v11);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpBuffer);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800dd768  mov     [rsp+arg_10], rbx
0x1800dd76d  push    rdi
0x1800dd76e  sub     rsp, 30h
0x1800dd772  mov     rdi, rcx
0x1800dd775  mov     qword ptr [rcx], 0
0x1800dd77c  mov     [rsp+38h+nSize], 0
0x1800dd784  xor     ebx, ebx
0x1800dd786  lea     r8, [rsp+38h+nSize]; nSize
0x1800dd78b  xor     edx, edx; lpBuffer
0x1800dd78d  lea     ecx, [rbx+4]; NameType
0x1800dd790  call    cs:__imp_GetComputerNameExW
0x1800dd796  test    eax, eax
0x1800dd798  jnz     loc_1800DD845
0x1800dd79e  call    cs:__imp_GetLastError
0x1800dd7a4  mov     ebx, eax
0x1800dd7a6  cmp     eax, 0EAh
0x1800dd7ab  jnz     loc_1800DD845
0x1800dd7b1  mov     [rsp+38h+lpBuffer], 0
0x1800dd7ba  xor     edx, edx
0x1800dd7bc  lea     rcx, [rsp+38h+lpBuffer]
0x1800dd7c1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800dd7c6  mov     ecx, [rsp+38h+nSize]
0x1800dd7ca  lea     rdx, [rsp+38h+lpBuffer]
0x1800dd7cf  call    ??$CamAllocBuffer@G@@YAJ_KPEAPEAG@Z; CamAllocBuffer<ushort>(unsigned __int64,ushort * *)
0x1800dd7d4  mov     ebx, eax
0x1800dd7d6  test    eax, eax
0x1800dd7d8  jns     short loc_1800DD7F5
0x1800dd7da  mov     rcx, [rsp+38h]; this
0x1800dd7df  mov     r9d, eax; char *
0x1800dd7e2  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dd7e9  mov     edx, 0A0h; void *
0x1800dd7ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd7f3  jmp     short loc_1800DD839
0x1800dd7f5  lea     r8, [rsp+38h+nSize]; nSize
0x1800dd7fa  mov     rbx, [rsp+38h+lpBuffer]
0x1800dd7ff  mov     rdx, rbx; lpBuffer
0x1800dd802  mov     ecx, 4; NameType
0x1800dd807  call    cs:__imp_GetComputerNameExW
0x1800dd80d  test    eax, eax
0x1800dd80f  jnz     short loc_1800DD82B
0x1800dd811  mov     rcx, [rsp+38h]; this
0x1800dd816  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dd81d  mov     edx, 0A1h; void *
0x1800dd822  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800dd827  mov     ebx, eax
0x1800dd829  jmp     short loc_1800DD839
0x1800dd82b  mov     [rsp+38h+lpBuffer], 0
0x1800dd834  mov     [rdi], rbx
0x1800dd837  xor     ebx, ebx
0x1800dd839  lea     rcx, [rsp+38h+lpBuffer]
0x1800dd83e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800dd843  jmp     short loc_1800DD873
0x1800dd845  mov     rcx, [rsp+38h]; this
0x1800dd84a  mov     dword ptr [rsp+38h+var_10], ebx; char *
0x1800dd84e  lea     rax, aExpectedGetcom; "Expected GetComputerNameExW to fail wit"...
0x1800dd855  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800dd85a  mov     ebx, 8000FFFFh
0x1800dd85f  mov     r9d, ebx; char *
0x1800dd862  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dd869  mov     edx, 9Dh; void *
0x1800dd86e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800dd873  mov     eax, ebx
0x1800dd875  mov     rbx, [rsp+38h+arg_10]
0x1800dd87a  add     rsp, 30h
0x1800dd87e  pop     rdi
0x1800dd87f  retn
```
