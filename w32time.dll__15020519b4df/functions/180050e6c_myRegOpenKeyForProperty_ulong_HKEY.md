# myRegOpenKeyForProperty(ulong,HKEY__ * *)

- ea: `0x180050e6c`
- end: `0x18005100b`
- name: `?myRegOpenKeyForProperty@@YAJKPEAPEAUHKEY__@@@Z`
- size: `415`
- prototype: `LSTATUS __fastcall(int, HKEY *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180051020`
- `0x1800510d0`
- `0x1800511d0`

## callees

- `0x18003d270`
- `0x18003dd2c`
- `0x180050e6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180050f42`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180050f6d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180050f42`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180050f6d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180050f03`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180050f22`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180050f03`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180050f22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050fd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050fd3`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180050f9d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180050f9d`

## pseudocode

```c
LSTATUS __fastcall myRegOpenKeyForProperty(int a1, HKEY *a2)
{
  unsigned int i; // eax
  __int64 v5; // rbx
  __int64 v6; // r8
  LSTATUS result; // eax
  bool v8; // cc
  WCHAR SubKey; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[526]; // [rsp+32h] [rbp-CEh] BYREF
  __int16 v11; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v12[526]; // [rsp+242h] [rbp+142h] BYREF

  SubKey = 0;
  memset_0(v10, 0, 0x206u);
  v11 = 0;
  memset_0(v12, 0, 0x206u);
  for ( i = 0; i < 6; ++i )
  {
    v5 = 32LL * i;
    if ( a1 == *(_DWORD *)((char *)&g_rgProperties + v5) )
    {
      _o_wcscpy_s(&SubKey, 260, *(struct PropertyTable near **)((char *)&g_rgProperties + v5 + 8));
      v6 = *(__int64 *)((char *)&g_rgProperties + v5 + 24);
      if ( v6 )
        _o_wcscpy_s(&v11, 260, v6);
      break;
    }
  }
  if ( !(unsigned int)_o__wcsnicmp(&SubKey, &qword_180071478, 259) )
    return -2147023728;
  if ( (unsigned int)_o__wcsnicmp(&v11, &qword_180071478, 259)
    && (result = GetPersistedRegistryLocationW(&v11, &SubKey, &SubKey, 520, 0), v8 = result <= 0, result)
    || (result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 3u, a2), v8 = result <= 0, result) )
  {
    if ( !v8 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180050e6c  mov     [rsp-8+arg_0], rbx
0x180050e71  mov     [rsp-8+arg_10], rsi
0x180050e76  push    rbp
0x180050e77  push    rdi
0x180050e78  push    r14
0x180050e7a  lea     rbp, [rsp-360h]
0x180050e82  sub     rsp, 460h
0x180050e89  mov     rax, cs:__security_cookie
0x180050e90  xor     rax, rsp
0x180050e93  mov     [rbp+370h+var_20], rax
0x180050e9a  mov     rsi, rdx
0x180050e9d  mov     edi, ecx
0x180050e9f  xor     eax, eax
0x180050ea1  lea     rcx, [rsp+470h+var_43E]; void *
0x180050ea6  mov     ebx, 206h
0x180050eab  mov     [rsp+470h+SubKey], ax
0x180050eb0  mov     r8d, ebx; Size
0x180050eb3  xor     edx, edx; Val
0x180050eb5  call    memset_0
0x180050eba  xor     eax, eax
0x180050ebc  lea     rcx, [rbp+370h+var_22E]; void *
0x180050ec3  mov     r8d, ebx; Size
0x180050ec6  mov     [rbp+370h+var_230], ax
0x180050ecd  xor     edx, edx; Val
0x180050ecf  call    memset_0
0x180050ed4  xor     eax, eax
0x180050ed6  lea     r14, ?g_rgProperties@@3PAUPropertyTable@@A; PropertyTable near * g_rgProperties
0x180050edd  cmp     eax, 6
0x180050ee0  jnb     short loc_180050F2E
0x180050ee2  mov     ebx, eax
0x180050ee4  shl     rbx, 5
0x180050ee8  cmp     edi, [rbx+r14]
0x180050eec  jz      short loc_180050EF2
0x180050eee  inc     eax
0x180050ef0  jmp     short loc_180050EDD
0x180050ef2  mov     r8, [rbx+r14+8]
0x180050ef7  lea     rcx, [rsp+470h+SubKey]
0x180050efc  mov     edi, 104h
0x180050f01  mov     edx, edi
0x180050f03  call    cs:__imp__o_wcscpy_s
0x180050f0a  nop     dword ptr [rax+rax+00h]
0x180050f0f  mov     r8, [rbx+r14+18h]
0x180050f14  test    r8, r8
0x180050f17  jz      short loc_180050F2E
0x180050f19  mov     edx, edi
0x180050f1b  lea     rcx, [rbp+370h+var_230]
0x180050f22  call    cs:__imp__o_wcscpy_s
0x180050f29  nop     dword ptr [rax+rax+00h]
0x180050f2e  mov     ebx, 103h
0x180050f33  lea     rdx, qword_180071478
0x180050f3a  mov     r8d, ebx
0x180050f3d  lea     rcx, [rsp+470h+SubKey]
0x180050f42  call    cs:__imp__o__wcsnicmp
0x180050f49  nop     dword ptr [rax+rax+00h]
0x180050f4e  test    eax, eax
0x180050f50  jnz     short loc_180050F5C
0x180050f52  mov     eax, 80070490h
0x180050f57  jmp     loc_180050FE3
0x180050f5c  mov     r8, rbx
0x180050f5f  lea     rdx, qword_180071478
0x180050f66  lea     rcx, [rbp+370h+var_230]
0x180050f6d  call    cs:__imp__o__wcsnicmp
0x180050f74  nop     dword ptr [rax+rax+00h]
0x180050f79  test    eax, eax
0x180050f7b  jz      short loc_180050FB9
0x180050f7d  mov     r9d, 208h
0x180050f83  mov     [rsp+470h+phkResult], 0
0x180050f8c  lea     r8, [rsp+470h+SubKey]
0x180050f91  lea     rdx, [rsp+470h+SubKey]
0x180050f96  lea     rcx, [rbp+370h+var_230]
0x180050f9d  call    cs:__imp_GetPersistedRegistryLocationW
0x180050fa4  nop     dword ptr [rax+rax+00h]
0x180050fa9  test    eax, eax
0x180050fab  jz      short loc_180050FB9
0x180050fad  jle     short loc_180050FE3
0x180050faf  movzx   eax, ax
0x180050fb2  or      eax, 80070000h
0x180050fb7  jmp     short loc_180050FE3
0x180050fb9  mov     r9d, 3; samDesired
0x180050fbf  mov     [rsp+470h+phkResult], rsi; phkResult
0x180050fc4  xor     r8d, r8d; ulOptions
0x180050fc7  lea     rdx, [rsp+470h+SubKey]; lpSubKey
0x180050fcc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050fd3  call    cs:__imp_RegOpenKeyExW
0x180050fda  nop     dword ptr [rax+rax+00h]
0x180050fdf  test    eax, eax
0x180050fe1  jnz     short loc_180050FAD
0x180050fe3  mov     rcx, [rbp+370h+var_20]
0x180050fea  xor     rcx, rsp; StackCookie
0x180050fed  call    __security_check_cookie
0x180050ff2  lea     r11, [rsp+470h+var_10]
0x180050ffa  mov     rbx, [r11+20h]
0x180050ffe  mov     rsi, [r11+30h]
0x180051002  mov     rsp, r11
0x180051005  pop     r14
0x180051007  pop     rdi
0x180051008  pop     rbp
0x180051009  retn
```
