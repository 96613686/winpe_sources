# CEnumSubscription::Initialize(ulong)

- ea: `0x180019630`
- end: `0x18001984f`
- name: `?Initialize@CEnumSubscription@@QEAAJK@Z`
- size: `543`
- prototype: `__int64 __fastcall(CEnumSubscription *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000cc84`
- `0x180019410`

## callees

- `0x180019630`
- `0x180019ae0`
- `0x18001ba08`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001981f`
- `ADVAPI32!RegCloseKey` at `0x18001981f`
- `ADVAPI32!RegEnumKeyW` at `0x180019762`
- `ADVAPI32!RegEnumKeyW` at `0x180019762`
- `ADVAPI32!RegCreateKeyExW` at `0x1800196ae`
- `ADVAPI32!RegCreateKeyExW` at `0x1800196ae`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800196fb`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800196fb`
- `ole32!CLSIDFromString` at `0x180019778`
- `ole32!CLSIDFromString` at `0x180019778`

## pseudocode

```c
__int64 __fastcall CEnumSubscription::Initialize(CEnumSubscription *this, char a2)
{
  int v4; // ebx
  void *v5; // rax
  DWORD i; // edi
  __int64 v7; // rax
  __int64 v8; // rcx
  struct ISubscriptionItem *v9; // r14
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  struct ISubscriptionItem *v14; // [rsp+78h] [rbp-88h] BYREF
  GUID pclsid; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v16[3]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[40]; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  dwDisposition = 0;
  v4 = -2147467259;
  if ( !RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Webcheck\\Store.1",
          0,
          0,
          0,
          0x2001Fu,
          0,
          &hKey,
          &dwDisposition) )
  {
    cSubKeys = 0;
    if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0) )
    {
      pclsid = 0;
      v5 = operator new(saturated_mul(cSubKeys, 0x10u));
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        v4 = 0;
        for ( i = 0; i < cSubKeys; ++i )
        {
          if ( v4 )
            break;
          if ( !RegEnumKeyW(hKey, i, Name, 0x27u) && CLSIDFromString(Name, &pclsid) >= 0 )
          {
            v7 = *((_QWORD *)this + 3);
            v8 = 2LL * *((unsigned int *)this + 3);
            v14 = 0;
            *(GUID *)(v7 + 8 * v8) = pclsid;
            v4 = SubscriptionItemFromCookie(0, &pclsid, &v14);
            if ( v4 >= 0 )
            {
              v9 = v14;
              memset(v16, 0, 44);
              LODWORD(v16[0]) = 44;
              if ( ((int (__fastcall *)(struct ISubscriptionItem *, _OWORD *))v14->lpVtbl->GetSubscriptionItemInfo)(
                     v14,
                     v16) >= 0
                && ((SDWORD1(v16[0]) & 0x80000000) == 0 || (a2 & 1) != 0) )
              {
                ++*((_DWORD *)this + 3);
              }
              ((void (__fastcall *)(struct ISubscriptionItem *))v9->lpVtbl->Release)(v9);
            }
          }
        }
      }
      else
      {
        v4 = -2147024882;
      }
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019630  mov     [rsp-8+arg_8], rbx
0x180019635  mov     [rsp-8+arg_10], rsi
0x18001963a  push    rbp
0x18001963b  push    rdi
0x18001963c  push    r12
0x18001963e  push    r14
0x180019640  push    r15
0x180019642  lea     rbp, [rsp-20h]
0x180019647  sub     rsp, 120h
0x18001964e  mov     rax, cs:__security_cookie
0x180019655  xor     rax, rsp
0x180019658  mov     [rbp+40h+var_30], rax
0x18001965c  xor     r12d, r12d
0x18001965f  lea     rax, [rsp+140h+dwDisposition]
0x180019664  mov     [rsp+140h+lpdwDisposition], rax; lpdwDisposition
0x180019669  mov     r15d, edx
0x18001966c  lea     rax, [rsp+140h+hKey]
0x180019671  mov     [rsp+140h+hKey], r12
0x180019676  mov     [rsp+140h+phkResult], rax; phkResult
0x18001967b  lea     rdx, ?c_szRegKeyStore@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180019682  mov     [rsp+140h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180019687  mov     rsi, rcx
0x18001968a  mov     [rsp+140h+samDesired], 2001Fh; samDesired
0x180019692  xor     r9d, r9d; lpClass
0x180019695  xor     r8d, r8d; Reserved
0x180019698  mov     [rsp+140h+dwOptions], r12d; dwOptions
0x18001969d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800196a4  mov     [rsp+140h+dwDisposition], r12d
0x1800196a9  mov     ebx, 80004005h
0x1800196ae  call    cs:__imp_RegCreateKeyExW
0x1800196b4  test    eax, eax
0x1800196b6  jnz     loc_180019825
0x1800196bc  mov     rcx, [rsp+140h+hKey]; hKey
0x1800196c1  lea     rax, [rsp+140h+cSubKeys]
0x1800196c6  mov     [rsp+140h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800196cb  xor     r9d, r9d; lpReserved
0x1800196ce  mov     [rsp+140h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800196d3  xor     r8d, r8d; lpcchClass
0x1800196d6  mov     [rsp+140h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800196db  xor     edx, edx; lpClass
0x1800196dd  mov     [rsp+140h+lpdwDisposition], r12; lpcbMaxValueNameLen
0x1800196e2  mov     [rsp+140h+phkResult], r12; lpcValues
0x1800196e7  mov     [rsp+140h+lpSecurityAttributes], r12; lpcbMaxClassLen
0x1800196ec  mov     qword ptr [rsp+140h+samDesired], r12; lpcbMaxSubKeyLen
0x1800196f1  mov     qword ptr [rsp+140h+dwOptions], rax; lpcSubKeys
0x1800196f6  mov     [rsp+140h+cSubKeys], r12d
0x1800196fb  call    cs:__imp_RegQueryInfoKeyW
0x180019701  test    eax, eax
0x180019703  jnz     loc_18001981A
0x180019709  mov     ecx, [rsp+140h+cSubKeys]
0x18001970d  lea     eax, [r12+10h]
0x180019712  mul     rcx
0x180019715  xorps   xmm0, xmm0
0x180019718  movups  xmmword ptr [rbp+40h+pclsid.Data1], xmm0
0x18001971c  lea     rcx, [r12-1]
0x180019721  cmovb   rax, rcx
0x180019725  mov     rcx, rax; dwBytes
0x180019728  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001972d  mov     [rsi+18h], rax
0x180019731  test    rax, rax
0x180019734  jz      loc_180019815
0x18001973a  mov     ebx, r12d
0x18001973d  mov     edi, r12d
0x180019740  cmp     [rsp+140h+cSubKeys], r12d
0x180019745  jbe     loc_18001981A
0x18001974b  test    ebx, ebx
0x18001974d  jnz     loc_18001981A
0x180019753  mov     rcx, [rsp+140h+hKey]; hKey
0x180019758  lea     r9d, [rbx+27h]; cchName
0x18001975c  lea     r8, [rbp+40h+Name]; lpName
0x180019760  mov     edx, edi; dwIndex
0x180019762  call    cs:__imp_RegEnumKeyW
0x180019768  test    eax, eax
0x18001976a  jnz     loc_180019807
0x180019770  lea     rdx, [rbp+40h+pclsid]; pclsid
0x180019774  lea     rcx, [rbp+40h+Name]; lpsz
0x180019778  call    cs:__imp_CLSIDFromString
0x18001977e  test    eax, eax
0x180019780  js      loc_180019807
0x180019786  mov     ecx, [rsi+0Ch]
0x180019789  lea     r8, [rsp+140h+var_C8]; struct ISubscriptionItem **
0x18001978e  mov     rax, [rsi+18h]
0x180019792  lea     rdx, [rbp+40h+pclsid]; struct _GUID *
0x180019796  movups  xmm0, xmmword ptr [rbp+40h+pclsid.Data1]
0x18001979a  add     rcx, rcx
0x18001979d  mov     [rsp+140h+var_C8], r12
0x1800197a2  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x1800197a7  xor     ecx, ecx; int
0x1800197a9  call    ?SubscriptionItemFromCookie@@YAJHPEFBU_GUID@@PEAPEAUISubscriptionItem@@@Z; SubscriptionItemFromCookie(int,_GUID const *,ISubscriptionItem * *)
0x1800197ae  mov     ebx, eax
0x1800197b0  test    eax, eax
0x1800197b2  js      short loc_180019807
0x1800197b4  mov     r14, [rsp+140h+var_C8]
0x1800197b9  lea     rdx, [rbp+40h+var_B0]
0x1800197bd  xorps   xmm0, xmm0
0x1800197c0  movups  [rbp+40h+var_B0], xmm0
0x1800197c4  mov     dword ptr [rbp+40h+var_B0], 2Ch ; ','
0x1800197cb  movups  xmmword ptr [rbp+40h+var_A0], xmm0
0x1800197cf  movups  xmmword ptr [rbp+40h+var_A0+0Ch], xmm0
0x1800197d3  mov     rcx, [r14]
0x1800197d6  mov     rax, [rcx+20h]
0x1800197da  mov     rcx, r14
0x1800197dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197e2  test    eax, eax
0x1800197e4  js      short loc_1800197F8
0x1800197e6  test    dword ptr [rbp+40h+var_B0+4], 80000000h
0x1800197ed  jz      short loc_1800197F5
0x1800197ef  test    r15b, 1
0x1800197f3  jz      short loc_1800197F8
0x1800197f5  inc     dword ptr [rsi+0Ch]
0x1800197f8  mov     rax, [r14]
0x1800197fb  mov     rcx, r14
0x1800197fe  mov     rax, [rax+10h]
0x180019802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019807  inc     edi
0x180019809  cmp     edi, [rsp+140h+cSubKeys]
0x18001980d  jb      loc_18001974B
0x180019813  jmp     short loc_18001981A
0x180019815  mov     ebx, 8007000Eh
0x18001981a  mov     rcx, [rsp+140h+hKey]; hKey
0x18001981f  call    cs:__imp_RegCloseKey
0x180019825  mov     eax, ebx
0x180019827  mov     rcx, [rbp+40h+var_30]
0x18001982b  xor     rcx, rsp; StackCookie
0x18001982e  call    __security_check_cookie
0x180019833  lea     r11, [rsp+140h+var_20]
0x18001983b  mov     rbx, [r11+38h]
0x18001983f  mov     rsi, [r11+40h]
0x180019843  mov     rsp, r11
0x180019846  pop     r15
0x180019848  pop     r14
0x18001984a  pop     r12
0x18001984c  pop     rdi
0x18001984d  pop     rbp
0x18001984e  retn
```
