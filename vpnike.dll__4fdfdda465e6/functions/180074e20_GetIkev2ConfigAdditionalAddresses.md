# GetIkev2ConfigAdditionalAddresses

- ea: `0x180074e20`
- end: `0x1800751ee`
- name: `GetIkev2ConfigAdditionalAddresses`
- size: `974`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180002e70`
- `0x180004640`

## callees

- `0x180039fa8`
- `0x180074c74`
- `0x180074e20`
- `0x180077590`

## import_xrefs

- `msvcrt!wcsstr` at `0x180074fcb`
- `msvcrt!wcsstr` at `0x180074fcb`
- `ntdll!RtlIpv4StringToAddressW` at `0x180074fee`
- `ntdll!RtlIpv4StringToAddressW` at `0x180074fee`
- `ntdll!RtlIpv6StringToAddressW` at `0x180075085`
- `ntdll!RtlIpv6StringToAddressW` at `0x180075085`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180075048`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800750db`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180075048`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800750db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007513c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180075190`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800751b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007513c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180075190`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800751b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074f0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074f72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074f95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074f0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074f72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074f95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074efd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074f63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074f86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075032`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800750c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007512d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075182`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800751a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074efd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074f63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074f86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075032`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800750c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007512d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075182`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800751a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074f1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007514b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007514b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074eea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074f48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074eea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074f48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074eb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074eb0`

## string_xrefs

- `0x180074e97`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters\Ikev2`

## pseudocode

```c
__int64 __fastcall GetIkev2ConfigAdditionalAddresses(
        __int64 a1,
        unsigned int *a2,
        LPVOID *a3,
        unsigned int *a4,
        LPVOID *a5)
{
  DWORD LastError; // esi
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  wchar_t *v11; // rax
  SIZE_T v12; // rbx
  HANDLE v13; // rax
  SIZE_T v14; // rbx
  HANDLE v15; // rax
  LPVOID v16; // rax
  wchar_t *v17; // rbx
  wchar_t *v18; // rax
  ULONG S_addr; // ecx
  unsigned int v20; // r9d
  void *v21; // rdi
  SIZE_T v22; // rbx
  HANDLE v23; // rax
  LPVOID v24; // rax
  unsigned int v25; // r8d
  void *v26; // rdi
  SIZE_T v27; // rbx
  HANDLE v28; // rax
  LPVOID v29; // rax
  __int64 v30; // rax
  HANDLE v31; // rax
  void *v32; // rbx
  HANDLE v33; // rax
  void *v34; // rbx
  HANDLE v35; // rax
  DWORD cbData; // [rsp+30h] [rbp-50h] BYREF
  DWORD Type; // [rsp+34h] [rbp-4Ch] BYREF
  struct in_addr Addr; // [rsp+38h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-40h] BYREF
  wchar_t *v41; // [rsp+48h] [rbp-38h]
  LPCWSTR Terminator; // [rsp+50h] [rbp-30h] BYREF
  wchar_t *Str; // [rsp+58h] [rbp-28h]
  IN6_ADDR a; // [rsp+60h] [rbp-20h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( !a2 || !a3 || !a4 || !a5 )
    return 87;
  *a4 = 0;
  *a2 = 0;
  *a3 = 0;
  *a5 = 0;
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ikev2",
                0,
                0x20019u,
                &hKey);
  if ( !LastError )
  {
    cbData = 0;
    Type = 7;
    LastError = RegQueryValueExW(hKey, L"AdditionalAddresses", 0, &Type, 0, &cbData);
    if ( !LastError )
    {
      v9 = cbData;
      ProcessHeap = GetProcessHeap();
      v11 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v9);
      Str = v11;
      if ( v11 )
      {
        LastError = RegQueryValueExW(hKey, L"AdditionalAddresses", 0, &Type, (LPBYTE)v11, &cbData);
        if ( !LastError )
        {
          v12 = 4LL * (*a2 + 10);
          v13 = GetProcessHeap();
          *a3 = HeapAlloc(v13, 8u, v12);
          v14 = 16LL * (*a4 + 10);
          v15 = GetProcessHeap();
          v16 = HeapAlloc(v15, 8u, v14);
          *a5 = v16;
          if ( *a3 && (v17 = Str, v41 = Str, v16) )
          {
            while ( *v17 )
            {
              v18 = wcsstr(v17, L":");
              Terminator = 0;
              if ( v18 )
              {
                a = 0;
                if ( !RtlIpv6StringToAddressW(v17, &Terminator, &a) && !IN6_IS_ADDR_UNSPECIFIED(&a) )
                {
                  v25 = *a4;
                  if ( *a4 && v25 == 10 * (v25 / 0xA) )
                  {
                    v26 = *a5;
                    v27 = 16LL * (v25 + 10);
                    v28 = GetProcessHeap();
                    v29 = HeapReAlloc(v28, 8u, v26, v27);
                    if ( !v29 )
                    {
LABEL_31:
                      LastError = 8;
                      break;
                    }
                    v17 = v41;
                    *a5 = v29;
                  }
                  *((IN6_ADDR *)*a5 + (*a4)++) = a;
                }
              }
              else
              {
                Addr = 0;
                if ( !RtlIpv4StringToAddressW(v17, 1u, &Terminator, &Addr) )
                {
                  S_addr = Addr.S_un.S_addr;
                  if ( Addr )
                  {
                    v20 = *a2;
                    if ( *a2 && v20 == 10 * (v20 / 0xA) )
                    {
                      v21 = *a3;
                      v22 = 4LL * (v20 + 10);
                      v23 = GetProcessHeap();
                      v24 = HeapReAlloc(v23, 8u, v21, v22);
                      if ( !v24 )
                        goto LABEL_31;
                      S_addr = Addr.S_un.S_addr;
                      v17 = v41;
                      *a3 = v24;
                    }
                    *((_DWORD *)*a3 + (*a2)++) = S_addr;
                  }
                }
              }
              v30 = -1;
              do
                ++v30;
              while ( v17[v30] );
              v17 += v30 + 1;
              v41 = v17;
            }
          }
          else
          {
            LastError = 8;
          }
        }
        v31 = GetProcessHeap();
        HeapFree(v31, 0, Str);
      }
      else
      {
        LastError = GetLastError();
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( LastError )
  {
    FreeIPAddress(*a3, *a5);
    *a3 = 0;
    *a2 = 0;
    *a5 = 0;
    *a4 = 0;
  }
  else
  {
    if ( !*a2 )
    {
      v32 = *a3;
      if ( *a3 )
      {
        v33 = GetProcessHeap();
        HeapFree(v33, 0, v32);
        *a3 = 0;
      }
    }
    if ( !*a4 )
    {
      v34 = *a5;
      if ( *a5 )
      {
        v35 = GetProcessHeap();
        HeapFree(v35, 0, v34);
        *a5 = 0;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180074e20  mov     [rsp-38h+arg_0], rbx
0x180074e25  push    rbp
0x180074e26  push    rsi
0x180074e27  push    rdi
0x180074e28  push    r12
0x180074e2a  push    r13
0x180074e2c  push    r14
0x180074e2e  push    r15
0x180074e30  mov     rbp, rsp
0x180074e33  sub     rsp, 80h
0x180074e3a  mov     rax, cs:__security_cookie
0x180074e41  xor     rax, rsp
0x180074e44  mov     [rbp+var_10], rax
0x180074e48  mov     r15, [rbp+arg_20]
0x180074e4c  xor     edi, edi
0x180074e4e  mov     [rbp+hKey], rdi
0x180074e52  mov     r12, r9
0x180074e55  mov     [rbp+cbData], edi
0x180074e58  mov     r14, r8
0x180074e5b  mov     [rbp+Type], edi
0x180074e5e  mov     r13, rdx
0x180074e61  test    rdx, rdx
0x180074e64  jz      loc_1800751C2
0x180074e6a  test    r8, r8
0x180074e6d  jz      loc_1800751C2
0x180074e73  test    r9, r9
0x180074e76  jz      loc_1800751C2
0x180074e7c  test    r15, r15
0x180074e7f  jz      loc_1800751C2
0x180074e85  mov     [r9], edi
0x180074e88  lea     rax, [rbp+hKey]
0x180074e8c  mov     [rdx], edi
0x180074e8e  mov     r9d, 20019h; samDesired
0x180074e94  mov     [r8], rdi
0x180074e97  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180074e9e  xor     r8d, r8d; ulOptions
0x180074ea1  mov     [r15], rdi
0x180074ea4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180074eab  mov     [rsp+80h+phkResult], rax; phkResult
0x180074eb0  call    cs:__imp_RegOpenKeyExW
0x180074eb6  mov     esi, eax
0x180074eb8  test    eax, eax
0x180074eba  jnz     loc_180075142
0x180074ec0  mov     rcx, [rbp+hKey]; hKey
0x180074ec4  lea     rax, [rbp+cbData]
0x180074ec8  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180074ecd  lea     r9, [rbp+Type]; lpType
0x180074ed1  xor     r8d, r8d; lpReserved
0x180074ed4  mov     [rsp+80h+phkResult], rdi; lpData
0x180074ed9  lea     rdx, aAdditionaladdr; "AdditionalAddresses"
0x180074ee0  mov     [rbp+cbData], edi
0x180074ee3  mov     [rbp+Type], 7
0x180074eea  call    cs:__imp_RegQueryValueExW
0x180074ef0  mov     esi, eax
0x180074ef2  test    eax, eax
0x180074ef4  jnz     loc_180075142
0x180074efa  mov     ebx, [rbp+cbData]
0x180074efd  call    cs:__imp_GetProcessHeap
0x180074f03  mov     r8d, ebx; dwBytes
0x180074f06  lea     edx, [rdi+8]; dwFlags
0x180074f09  mov     rcx, rax; hHeap
0x180074f0c  call    cs:__imp_HeapAlloc
0x180074f12  mov     [rbp+Str], rax
0x180074f16  test    rax, rax
0x180074f19  jnz     short loc_180074F28
0x180074f1b  call    cs:__imp_GetLastError
0x180074f21  mov     esi, eax
0x180074f23  jmp     loc_180075142
0x180074f28  lea     rcx, [rbp+cbData]
0x180074f2c  xor     r8d, r8d; lpReserved
0x180074f2f  mov     [rsp+80h+lpcbData], rcx; lpcbData
0x180074f34  lea     r9, [rbp+Type]; lpType
0x180074f38  mov     rcx, [rbp+hKey]; hKey
0x180074f3c  lea     rdx, aAdditionaladdr; "AdditionalAddresses"
0x180074f43  mov     [rsp+80h+phkResult], rax; lpData
0x180074f48  call    cs:__imp_RegQueryValueExW
0x180074f4e  mov     esi, eax
0x180074f50  test    eax, eax
0x180074f52  jnz     loc_18007512D
0x180074f58  mov     ebx, [r13+0]
0x180074f5c  add     ebx, 0Ah
0x180074f5f  shl     rbx, 2
0x180074f63  call    cs:__imp_GetProcessHeap
0x180074f69  mov     r8, rbx; dwBytes
0x180074f6c  lea     edx, [rsi+8]; dwFlags
0x180074f6f  mov     rcx, rax; hHeap
0x180074f72  call    cs:__imp_HeapAlloc
0x180074f78  mov     [r14], rax
0x180074f7b  mov     ebx, [r12]
0x180074f7f  add     ebx, 0Ah
0x180074f82  shl     rbx, 4
0x180074f86  call    cs:__imp_GetProcessHeap
0x180074f8c  mov     r8, rbx; dwBytes
0x180074f8f  lea     edx, [rsi+8]; dwFlags
0x180074f92  mov     rcx, rax; hHeap
0x180074f95  call    cs:__imp_HeapAlloc
0x180074f9b  mov     [r15], rax
0x180074f9e  cmp     [r14], rdi
0x180074fa1  jz      loc_180075128
0x180074fa7  mov     rbx, [rbp+Str]
0x180074fab  mov     [rbp+var_38], rbx
0x180074faf  test    rax, rax
0x180074fb2  jz      loc_180075128
0x180074fb8  cmp     [rbx], di
0x180074fbb  jz      loc_18007512D
0x180074fc1  lea     rdx, asc_18009FE28; ":"
0x180074fc8  mov     rcx, rbx; Str
0x180074fcb  call    cs:__imp_wcsstr
0x180074fd1  mov     [rbp+Terminator], rdi
0x180074fd5  mov     rcx, rbx; S
0x180074fd8  test    rax, rax
0x180074fdb  jnz     loc_180075076
0x180074fe1  lea     r9, [rbp+Addr]; Addr
0x180074fe5  mov     dword ptr [rbp+Addr.S_un], edi
0x180074fe8  lea     r8, [rbp+Terminator]; Terminator
0x180074fec  mov     dl, 1; Strict
0x180074fee  call    cs:__imp_RtlIpv4StringToAddressW
0x180074ff4  test    eax, eax
0x180074ff6  jnz     loc_180075106
0x180074ffc  mov     ecx, dword ptr [rbp+Addr.S_un]
0x180074fff  test    ecx, ecx
0x180075001  jz      loc_180075106
0x180075007  mov     r9d, [r13+0]
0x18007500b  test    r9d, r9d
0x18007500e  jz      short loc_180075063
0x180075010  mov     eax, 0CCCCCCCDh
0x180075015  mul     r9d
0x180075018  shr     edx, 3
0x18007501b  lea     r8d, [rdx+rdx*4]
0x18007501f  add     r8d, r8d
0x180075022  cmp     r9d, r8d
0x180075025  jnz     short loc_180075063
0x180075027  mov     rdi, [r14]
0x18007502a  lea     ebx, [r9+0Ah]
0x18007502e  shl     rbx, 2
0x180075032  call    cs:__imp_GetProcessHeap
0x180075038  mov     r9, rbx; dwBytes
0x18007503b  mov     r8, rdi; lpMem
0x18007503e  mov     ebx, 8
0x180075043  mov     rcx, rax; hHeap
0x180075046  mov     edx, ebx; dwFlags
0x180075048  call    cs:__imp_HeapReAlloc
0x18007504e  xor     edi, edi
0x180075050  test    rax, rax
0x180075053  jz      loc_180075124
0x180075059  mov     ecx, dword ptr [rbp+Addr.S_un]
0x18007505c  mov     rbx, [rbp+var_38]
0x180075060  mov     [r14], rax
0x180075063  mov     edx, [r13+0]
0x180075067  mov     rax, [r14]
0x18007506a  mov     [rax+rdx*4], ecx
0x18007506d  inc     dword ptr [r13+0]
0x180075071  jmp     loc_180075106
0x180075076  xorps   xmm0, xmm0
0x180075079  lea     r8, [rbp+a]; Addr
0x18007507d  lea     rdx, [rbp+Terminator]; Terminator
0x180075081  movups  xmmword ptr [rbp+a.u], xmm0
0x180075085  call    cs:__imp_RtlIpv6StringToAddressW
0x18007508b  test    eax, eax
0x18007508d  jnz     short loc_180075106
0x18007508f  lea     rcx, [rbp+a]; a
0x180075093  call    IN6_IS_ADDR_UNSPECIFIED
0x180075098  test    al, al
0x18007509a  jnz     short loc_180075106
0x18007509c  mov     r8d, [r12]
0x1800750a0  test    r8d, r8d
0x1800750a3  jz      short loc_1800750EF
0x1800750a5  mov     eax, 0CCCCCCCDh
0x1800750aa  mul     r8d
0x1800750ad  shr     edx, 3
0x1800750b0  lea     ecx, [rdx+rdx*4]
0x1800750b3  add     ecx, ecx
0x1800750b5  cmp     r8d, ecx
0x1800750b8  jnz     short loc_1800750EF
0x1800750ba  mov     rdi, [r15]
0x1800750bd  lea     ebx, [r8+0Ah]
0x1800750c1  shl     rbx, 4
0x1800750c5  call    cs:__imp_GetProcessHeap
0x1800750cb  mov     r9, rbx; dwBytes
0x1800750ce  mov     r8, rdi; lpMem
0x1800750d1  mov     ebx, 8
0x1800750d6  mov     rcx, rax; hHeap
0x1800750d9  mov     edx, ebx; dwFlags
0x1800750db  call    cs:__imp_HeapReAlloc
0x1800750e1  xor     edi, edi
0x1800750e3  test    rax, rax
0x1800750e6  jz      short loc_180075124
0x1800750e8  mov     rbx, [rbp+var_38]
0x1800750ec  mov     [r15], rax
0x1800750ef  mov     ecx, [r12]
0x1800750f3  mov     rax, [r15]
0x1800750f6  add     rcx, rcx
0x1800750f9  movups  xmm0, xmmword ptr [rbp+a.u]
0x1800750fd  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x180075102  inc     dword ptr [r12]
0x180075106  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007510a  inc     rax
0x18007510d  cmp     [rbx+rax*2], di
0x180075111  jnz     short loc_18007510A
0x180075113  lea     rbx, [rbx+rax*2]
0x180075117  add     rbx, 2
0x18007511b  mov     [rbp+var_38], rbx
0x18007511f  jmp     loc_180074FB8
0x180075124  mov     esi, ebx
0x180075126  jmp     short loc_18007512D
0x180075128  mov     esi, 8
0x18007512d  call    cs:__imp_GetProcessHeap
0x180075133  mov     r8, [rbp+Str]; lpMem
0x180075137  xor     edx, edx; dwFlags
0x180075139  mov     rcx, rax; hHeap
0x18007513c  call    cs:__imp_HeapFree
0x180075142  mov     rcx, [rbp+hKey]; hKey
0x180075146  test    rcx, rcx
0x180075149  jz      short loc_180075155
0x18007514b  call    cs:__imp_RegCloseKey
0x180075151  mov     [rbp+hKey], rdi
0x180075155  test    esi, esi
0x180075157  jz      short loc_180075174
0x180075159  mov     rdx, [r15]; LPVOID
0x18007515c  mov     rcx, [r14]; lpMem
0x18007515f  call    FreeIPAddress
0x180075164  mov     [r14], rdi
0x180075167  mov     [r13+0], edi
0x18007516b  mov     [r15], rdi
0x18007516e  mov     [r12], edi
0x180075172  jmp     short loc_1800751BE
0x180075174  cmp     [r13+0], edi
0x180075178  jnz     short loc_180075199
0x18007517a  mov     rbx, [r14]
0x18007517d  test    rbx, rbx
0x180075180  jz      short loc_180075199
0x180075182  call    cs:__imp_GetProcessHeap
0x180075188  mov     r8, rbx; lpMem
0x18007518b  xor     edx, edx; dwFlags
0x18007518d  mov     rcx, rax; hHeap
0x180075190  call    cs:__imp_HeapFree
0x180075196  mov     [r14], rdi
0x180075199  cmp     [r12], edi
0x18007519d  jnz     short loc_1800751BE
0x18007519f  mov     rbx, [r15]
0x1800751a2  test    rbx, rbx
0x1800751a5  jz      short loc_1800751BE
0x1800751a7  call    cs:__imp_GetProcessHeap
0x1800751ad  mov     r8, rbx; lpMem
0x1800751b0  xor     edx, edx; dwFlags
0x1800751b2  mov     rcx, rax; hHeap
0x1800751b5  call    cs:__imp_HeapFree
0x1800751bb  mov     [r15], rdi
0x1800751be  mov     eax, esi
0x1800751c0  jmp     short loc_1800751C7
0x1800751c2  mov     eax, 57h ; 'W'
0x1800751c7  mov     rcx, [rbp+var_10]
0x1800751cb  xor     rcx, rsp; StackCookie
0x1800751ce  call    __security_check_cookie
0x1800751d3  mov     rbx, [rsp+80h+arg_0]
0x1800751db  add     rsp, 80h
0x1800751e2  pop     r15
0x1800751e4  pop     r14
0x1800751e6  pop     r13
0x1800751e8  pop     r12
0x1800751ea  pop     rdi
0x1800751eb  pop     rsi
0x1800751ec  pop     rbp
0x1800751ed  retn
```
