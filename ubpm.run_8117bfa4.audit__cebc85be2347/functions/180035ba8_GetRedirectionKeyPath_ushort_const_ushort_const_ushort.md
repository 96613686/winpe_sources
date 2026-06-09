# GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)

- ea: `0x180035ba8`
- end: `0x180035cf0`
- name: `?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z`
- size: `328`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035b08`

## callees

- `0x1800355e8`
- `0x180035ba8`
- `0x1800361e4`
- `0x180036298`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035c02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035c89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035c02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035c89`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180035beb`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180035c3a`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180035beb`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180035c3a`

## string_xrefs

- `0x180035be1`: `OOBECompleteTimestamp`
- `0x180035c33`: `OOBECompleteTimestamp`
- `0x180035bd3`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`
- `0x180035c20`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`

## pseudocode

```c
__int64 __fastcall GetRedirectionKeyPath(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rbx
  unsigned __int16 *v6; // rax
  const unsigned __int16 *v7; // r8
  unsigned int v8; // ebx
  unsigned __int16 **p_cb; // [rsp+20h] [rbp-28h]
  unsigned __int64 *v11; // [rsp+28h] [rbp-20h]
  unsigned int v12; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  const unsigned __int16 *v14; // [rsp+50h] [rbp+8h] BYREF
  unsigned int cb; // [rsp+58h] [rbp+10h] BYREF
  int cb_4; // [rsp+5Ch] [rbp+14h]

  cb_4 = HIDWORD(a2);
  v14 = a1;
  cb = 0;
  p_cb = (unsigned __int16 **)&cb;
  *a3 = 0;
  if ( (unsigned int)GetPersistedRegistryLocationW(
                       L"OOBECompleteTimestamp",
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompleteTimestamp",
                       a3,
                       0) == 234 )
  {
    v4 = (unsigned __int16 *)CoTaskMemAlloc(cb);
    v14 = v4;
    v5 = v4;
    if ( v4 )
    {
      p_cb = 0;
      if ( !(unsigned int)GetPersistedRegistryLocationW(
                            L"OOBECompleteTimestamp",
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompleteTimestamp",
                            v4,
                            cb) )
      {
        v14 = 0;
        *a3 = v5;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
  }
  if ( *a3 )
    return 0;
  *a3 = 0;
  v14 = 0;
  if ( is_mul_ok(0x45u, 2u) )
  {
    v6 = (unsigned __int16 *)CoTaskMemAlloc(0x8Au);
    *a3 = v6;
    v8 = v6 == 0 ? 0x8007000E : 0;
    if ( v6 )
    {
      StringCchCopyNExW(v6, 0x45u, v7, 0x44u, p_cb, v11, v12);
      return 0;
    }
  }
  else
  {
    v8 = -2147024362;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2E,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\OobeRedirectionKeyHelper.h",
    (const char *)v8,
    (int)p_cb);
  return v8;
}

```

## disassembly

```asm
0x180035ba8  mov     rax, rsp
0x180035bab  mov     [rax+18h], rbx
0x180035baf  mov     [rax+20h], rbp
0x180035bb3  mov     [rax+10h], rdx
0x180035bb7  mov     [rax+8], rcx
0x180035bbb  push    rdi
0x180035bbc  sub     rsp, 40h
0x180035bc0  mov     dword ptr [rax+10h], 0
0x180035bc7  lea     rax, [rax+10h]
0x180035bcb  xor     r9d, r9d
0x180035bce  mov     [rsp+48h+var_28], rax
0x180035bd3  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180035bda  mov     qword ptr [r8], 0
0x180035be1  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x180035be8  mov     rdi, r8
0x180035beb  call    cs:__imp_GetPersistedRegistryLocationW
0x180035bf2  nop     dword ptr [rax+rax+00h]
0x180035bf7  cmp     eax, 0EAh
0x180035bfc  jnz     short loc_180035C60
0x180035bfe  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x180035c02  call    cs:__imp_CoTaskMemAlloc
0x180035c09  nop     dword ptr [rax+rax+00h]
0x180035c0e  mov     [rsp+48h+arg_0], rax
0x180035c13  mov     rbx, rax
0x180035c16  test    rax, rax
0x180035c19  jz      short loc_180035C56
0x180035c1b  mov     r9d, dword ptr [rsp+48h+cb]
0x180035c20  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180035c27  mov     r8, rax
0x180035c2a  mov     [rsp+48h+var_28], 0; int
0x180035c33  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x180035c3a  call    cs:__imp_GetPersistedRegistryLocationW
0x180035c41  nop     dword ptr [rax+rax+00h]
0x180035c46  test    eax, eax
0x180035c48  jnz     short loc_180035C56
0x180035c4a  mov     [rsp+48h+arg_0], 0
0x180035c53  mov     [rdi], rbx
0x180035c56  lea     rcx, [rsp+48h+arg_0]
0x180035c5b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180035c60  cmp     qword ptr [rdi], 0
0x180035c64  jnz     short loc_180035CBB
0x180035c66  mov     ebp, 45h ; 'E'
0x180035c6b  mov     qword ptr [rdi], 0
0x180035c72  mov     [rsp+48h+arg_0], 0
0x180035c7b  lea     eax, [rbp-43h]
0x180035c7e  mul     rbp
0x180035c81  test    rdx, rdx
0x180035c84  jnz     short loc_180035CCE
0x180035c86  mov     rcx, rax; cb
0x180035c89  call    cs:__imp_CoTaskMemAlloc
0x180035c90  nop     dword ptr [rax+rax+00h]
0x180035c95  mov     rcx, rax
0x180035c98  mov     [rdi], rax
0x180035c9b  neg     rcx
0x180035c9e  sbb     ebx, ebx
0x180035ca0  not     ebx
0x180035ca2  and     ebx, 8007000Eh
0x180035ca8  test    rax, rax
0x180035cab  jz      short loc_180035CD3
0x180035cad  lea     r9d, [rbp-1]; unsigned __int64
0x180035cb1  mov     edx, ebp; unsigned __int64
0x180035cb3  mov     rcx, rax; unsigned __int16 *
0x180035cb6  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180035cbb  xor     eax, eax
0x180035cbd  mov     rbx, [rsp+48h+arg_10]
0x180035cc2  mov     rbp, [rsp+48h+arg_18]
0x180035cc7  add     rsp, 40h
0x180035ccb  pop     rdi
0x180035ccc  retn
0x180035cce  mov     ebx, 80070216h
0x180035cd3  mov     rcx, [rsp+48h]; this
0x180035cd8  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\OobeR"...
0x180035cdf  mov     r9d, ebx; char *
0x180035ce2  mov     edx, 2Eh ; '.'; void *
0x180035ce7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035cec  mov     eax, ebx
0x180035cee  jmp     short loc_180035CBD
```
