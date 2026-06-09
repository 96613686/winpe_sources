# OOBE::CompleteTime::details::GetOOBECompleteKey

- ea: `0x18003370c`
- end: `0x18003379f`
- name: `OOBE::CompleteTime::details::GetOOBECompleteKey`
- size: `147`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033f58`

## callees

- `0x180033224`
- `0x18003370c`
- `0x1800337a8`
- `0x180033dac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003376e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003376e`

## string_xrefs

- `0x18003373e`: `onecoreuap\internal\shell\inc\OobeCompleteTime.h`

## pseudocode

```c
__int64 __fastcall OOBE::CompleteTime::details::GetOOBECompleteKey(
        unsigned __int16 *phkResult,
        const unsigned __int16 *a2)
{
  int RedirectionKeyPath; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)phkResult = 0;
  lpSubKey = 0;
  RedirectionKeyPath = GetRedirectionKeyPath(phkResult, a2, (unsigned __int16 **)&lpSubKey);
  v4 = RedirectionKeyPath;
  if ( RedirectionKeyPath >= 0 )
  {
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, (PHKEY)phkResult);
    if ( v5 )
    {
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      v4 = v5;
    }
    else
    {
      v4 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OobeCompleteTime.h",
      (const char *)(unsigned int)RedirectionKeyPath,
      phkResulta);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  return v4;
}

```

## disassembly

```asm
0x18003370c  mov     [rsp+arg_8], rbx
0x180033711  push    rdi
0x180033712  sub     rsp, 30h
0x180033716  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x18003371b  mov     qword ptr [rcx], 0
0x180033722  mov     rdi, rcx
0x180033725  mov     [rsp+38h+lpSubKey], 0
0x18003372e  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180033733  mov     ebx, eax
0x180033735  test    eax, eax
0x180033737  jns     short loc_180033754
0x180033739  mov     rcx, [rsp+38h]; this
0x18003373e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OobeC"...
0x180033745  mov     r9d, eax; char *
0x180033748  mov     edx, 16h; void *
0x18003374d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033752  jmp     short loc_180033788
0x180033754  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x180033759  mov     r9d, 2001Fh; samDesired
0x18003375f  xor     r8d, r8d; ulOptions
0x180033762  mov     qword ptr [rsp+38h+phkResult], rdi; phkResult
0x180033767  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003376e  call    cs:__imp_RegOpenKeyExW
0x180033774  test    eax, eax
0x180033776  jz      short loc_180033786
0x180033778  jle     short loc_180033782
0x18003377a  movzx   eax, ax
0x18003377d  or      eax, 80070000h
0x180033782  mov     ebx, eax
0x180033784  jmp     short loc_180033788
0x180033786  xor     ebx, ebx
0x180033788  lea     rcx, [rsp+38h+lpSubKey]
0x18003378d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180033792  mov     eax, ebx
0x180033794  mov     rbx, [rsp+38h+arg_8]
0x180033799  add     rsp, 30h
0x18003379d  pop     rdi
0x18003379e  retn
```
