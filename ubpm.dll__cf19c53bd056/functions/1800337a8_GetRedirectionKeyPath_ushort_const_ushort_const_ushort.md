# GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)

- ea: `0x1800337a8`
- end: `0x1800338d7`
- name: `?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z`
- size: `303`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003370c`

## callees

- `0x180033224`
- `0x1800337a8`
- `0x180033dac`
- `0x180033e54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800337fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800337fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033877`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800337eb`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18003382e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800337eb`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18003382e`

## string_xrefs

- `0x1800337e1`: `OOBECompleteTimestamp`
- `0x180033827`: `OOBECompleteTimestamp`
- `0x1800337d3`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`
- `0x180033814`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`

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
0x1800337a8  mov     rax, rsp
0x1800337ab  mov     [rax+18h], rbx
0x1800337af  mov     [rax+20h], rbp
0x1800337b3  mov     [rax+10h], rdx
0x1800337b7  mov     [rax+8], rcx
0x1800337bb  push    rdi
0x1800337bc  sub     rsp, 40h
0x1800337c0  mov     dword ptr [rax+10h], 0
0x1800337c7  lea     rax, [rax+10h]
0x1800337cb  xor     r9d, r9d
0x1800337ce  mov     [rsp+48h+var_28], rax
0x1800337d3  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800337da  mov     qword ptr [r8], 0
0x1800337e1  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x1800337e8  mov     rdi, r8
0x1800337eb  call    cs:__imp_GetPersistedRegistryLocationW
0x1800337f1  cmp     eax, 0EAh
0x1800337f6  jnz     short loc_18003384E
0x1800337f8  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x1800337fc  call    cs:__imp_CoTaskMemAlloc
0x180033802  mov     [rsp+48h+arg_0], rax
0x180033807  mov     rbx, rax
0x18003380a  test    rax, rax
0x18003380d  jz      short loc_180033844
0x18003380f  mov     r9d, dword ptr [rsp+48h+cb]
0x180033814  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003381b  mov     r8, rax
0x18003381e  mov     [rsp+48h+var_28], 0; int
0x180033827  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x18003382e  call    cs:__imp_GetPersistedRegistryLocationW
0x180033834  test    eax, eax
0x180033836  jnz     short loc_180033844
0x180033838  mov     [rsp+48h+arg_0], 0
0x180033841  mov     [rdi], rbx
0x180033844  lea     rcx, [rsp+48h+arg_0]
0x180033849  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003384e  cmp     qword ptr [rdi], 0
0x180033852  jnz     short loc_1800338A3
0x180033854  mov     ebp, 45h ; 'E'
0x180033859  mov     qword ptr [rdi], 0
0x180033860  mov     [rsp+48h+arg_0], 0
0x180033869  lea     eax, [rbp-43h]
0x18003386c  mul     rbp
0x18003386f  test    rdx, rdx
0x180033872  jnz     short loc_1800338B5
0x180033874  mov     rcx, rax; cb
0x180033877  call    cs:__imp_CoTaskMemAlloc
0x18003387d  mov     rcx, rax
0x180033880  mov     [rdi], rax
0x180033883  neg     rcx
0x180033886  sbb     ebx, ebx
0x180033888  not     ebx
0x18003388a  and     ebx, 8007000Eh
0x180033890  test    rax, rax
0x180033893  jz      short loc_1800338BA
0x180033895  lea     r9d, [rbp-1]; unsigned __int64
0x180033899  mov     edx, ebp; unsigned __int64
0x18003389b  mov     rcx, rax; unsigned __int16 *
0x18003389e  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800338a3  xor     eax, eax
0x1800338a5  mov     rbx, [rsp+48h+arg_10]
0x1800338aa  mov     rbp, [rsp+48h+arg_18]
0x1800338af  add     rsp, 40h
0x1800338b3  pop     rdi
0x1800338b4  retn
0x1800338b5  mov     ebx, 80070216h
0x1800338ba  mov     rcx, [rsp+48h]; this
0x1800338bf  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\OobeR"...
0x1800338c6  mov     r9d, ebx; char *
0x1800338c9  mov     edx, 2Eh ; '.'; void *
0x1800338ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800338d3  mov     eax, ebx
0x1800338d5  jmp     short loc_1800338A5
```
