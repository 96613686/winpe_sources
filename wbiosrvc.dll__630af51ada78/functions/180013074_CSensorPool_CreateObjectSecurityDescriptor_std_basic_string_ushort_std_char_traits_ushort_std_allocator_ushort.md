# CSensorPool::CreateObjectSecurityDescriptor(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180013074`
- end: `0x180013182`
- name: `?CreateObjectSecurityDescriptor@CSensorPool@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012758`

## callees

- `0x180013074`
- `0x180013188`
- `0x1800131e4`
- `0x180014894`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001311c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001311c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013159`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001316a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013159`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001316a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180013112`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180013112`

## string_xrefs

- `0x180013099`: `CSensorPool::CreateObjectSecurityDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSensorPool::CreateObjectSecurityDescriptor(__int64 a1, __int64 a2)
{
  const WCHAR *v4; // rax
  DWORD v5; // edx
  void *v7; // rcx
  int v8; // [rsp+20h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+28h] [rbp-11h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+30h] [rbp-9h] BYREF
  _QWORD *v11; // [rsp+38h] [rbp-1h] BYREF
  _QWORD v12[2]; // [rsp+40h] [rbp+7h] BYREF
  char v13[48]; // [rsp+50h] [rbp+17h] BYREF

  v12[0] = v13;
  strcpy(v13, "CSensorPool::CreateObjectSecurityDescriptor");
  v8 = 0;
  v12[1] = &v8;
  lambda_efe50bc157c2507d0f33f87adf87f131_::operator()(v12);
  SecurityDescriptor = 0;
  v11 = v12;
  v8 = 1;
  SecurityDescriptorSize = 0;
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v4, v5, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    v7 = *(void **)(a1 + 120);
    if ( v7 )
      LocalFree(v7);
    *(_QWORD *)(a1 + 120) = SecurityDescriptor;
    goto LABEL_9;
  }
  if ( GetLastError() && SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
LABEL_9:
    SecurityDescriptor = 0;
  }
  return WppTraceUnwinder__lambda_efe50bc157c2507d0f33f87adf87f131____::_WppTraceUnwinder__lambda_efe50bc157c2507d0f33f87adf87f131____(&v11);
}

```

## disassembly

```asm
0x180013074  mov     [rsp-8+arg_10], rbx
0x180013079  mov     [rsp-8+arg_18], rdi
0x18001307e  push    rbp
0x18001307f  lea     rbp, [rsp-57h]
0x180013084  sub     rsp, 90h
0x18001308b  mov     rax, cs:__security_cookie
0x180013092  xor     rax, rsp
0x180013095  mov     [rbp+57h+var_10], rax
0x180013099  movups  xmm0, xmmword ptr cs:aCsensorpoolCre; "CSensorPool::CreateObjectSecurityDescri"...
0x1800130a0  lea     rax, [rbp+57h+var_40]
0x1800130a4  mov     rdi, rcx
0x1800130a7  movups  xmm1, xmmword ptr cs:aCsensorpoolCre+10h; "ateObjectSecurityDescriptor"
0x1800130ae  mov     [rbp+57h+var_50], rax
0x1800130b2  lea     rax, [rbp+57h+var_70]
0x1800130b6  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x1800130ba  lea     rcx, [rbp+57h+var_50]
0x1800130be  mov     rbx, rdx
0x1800130c1  movups  xmm0, xmmword ptr cs:aCsensorpoolCre+1Ch; "urityDescriptor"
0x1800130c8  mov     [rbp+57h+var_70], 0
0x1800130cf  movups  xmmword ptr [rbp+57h+var_40+10h], xmm1
0x1800130d3  mov     [rbp+57h+var_48], rax
0x1800130d7  movups  xmmword ptr [rbp+57h+var_40+1Ch], xmm0
0x1800130db  call    _lambda_efe50bc157c2507d0f33f87adf87f131___operator__
0x1800130e0  lea     rax, [rbp+57h+var_50]
0x1800130e4  mov     [rbp+57h+SecurityDescriptor], 0
0x1800130ec  mov     edx, 1
0x1800130f1  mov     [rbp+57h+var_58], rax
0x1800130f5  mov     rcx, rbx
0x1800130f8  mov     [rbp+57h+var_70], edx
0x1800130fb  mov     [rbp+57h+SecurityDescriptorSize], 0
0x180013102  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013107  mov     rcx, rax; StringSecurityDescriptor
0x18001310a  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18001310e  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180013112  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180013118  test    eax, eax
0x18001311a  jnz     short loc_180013161
0x18001311c  call    cs:__imp_GetLastError
0x180013122  test    eax, eax
0x180013124  jnz     short loc_180013150
0x180013126  lea     rcx, [rbp+57h+var_58]
0x18001312a  call    WppTraceUnwinder__lambda_efe50bc157c2507d0f33f87adf87f131_______WppTraceUnwinder__lambda_efe50bc157c2507d0f33f87adf87f131____
0x18001312f  mov     rcx, [rbp+57h+var_10]
0x180013133  xor     rcx, rsp; StackCookie
0x180013136  call    __security_check_cookie
0x18001313b  lea     r11, [rsp+90h+var_s0]
0x180013143  mov     rbx, [r11+20h]
0x180013147  mov     rdi, [r11+28h]
0x18001314b  mov     rsp, r11
0x18001314e  pop     rbp
0x18001314f  retn
0x180013150  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180013154  test    rcx, rcx
0x180013157  jz      short loc_180013126
0x180013159  call    cs:__imp_LocalFree
0x18001315f  jmp     short loc_180013178
0x180013161  mov     rcx, [rdi+78h]; hMem
0x180013165  test    rcx, rcx
0x180013168  jz      short loc_180013170
0x18001316a  call    cs:__imp_LocalFree
0x180013170  mov     rax, [rbp+57h+SecurityDescriptor]
0x180013174  mov     [rdi+78h], rax
0x180013178  mov     [rbp+57h+SecurityDescriptor], 0
0x180013180  jmp     short loc_180013126
```
