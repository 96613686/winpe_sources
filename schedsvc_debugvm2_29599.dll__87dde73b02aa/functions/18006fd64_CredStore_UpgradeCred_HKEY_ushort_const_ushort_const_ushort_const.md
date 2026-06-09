# CredStore::UpgradeCred(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x18006fd64`
- end: `0x180070099`
- name: `?UpgradeCred@CredStore@@AEAAHPEAUHKEY__@@PEBG11@Z`
- size: `821`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, HKEY hKey@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006fbd0`

## callees

- `0x18000b4e0`
- `0x18000dc30`
- `0x180021300`
- `0x18002b1d0`
- `0x180033b40`
- `0x18003f940`
- `0x18006fd64`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070051`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070051`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fe1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fe1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006feae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006fedb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180070004`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180070048`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006feae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006fedb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180070004`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180070048`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006fef9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006fef9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006ff4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006ffbc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006ff4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006ffbc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006fe6d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006fe6d`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180070017`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180070017`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CredStore::UpgradeCred(
        LPCRITICAL_SECTION lpCriticalSection,
        HKEY hKey,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *lpAccountName)
{
  unsigned int v9; // ebx
  unsigned __int64 v10; // rdi
  const WCHAR *v11; // rdx
  BYTE *v12; // rax
  int v13; // r8d
  int v14; // edx
  BYTE v16[4]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v22[2]; // [rsp+70h] [rbp-90h] BYREF
  BYTE v23[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v24[78]; // [rsp+82h] [rbp-7Eh] BYREF
  BYTE v25[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v26[78]; // [rsp+D2h] [rbp-2Eh] BYREF

  v9 = 0;
  v22[0] = 0;
  v21 = 0;
  v10 = -1;
  do
    ++v10;
  while ( a3[v10] );
  if ( v10 >= 0x13 )
  {
    *(_WORD *)v23 = 0;
    memset_0(v24, 0, 0x4Cu);
    StringCchCopyNW((unsigned __int16 *)v23, 0x27u, a3 + 19, v10 - 19);
    if ( (int)User::FromUsername((struct User *)&v21, lpAccountName) >= 0
      && User::GetSidString((User *)&v21, (struct _bstr_t *)v22) >= 0 )
    {
      EnterCriticalSection(lpCriticalSection);
      hKeya = 0;
      dwDisposition = 0;
      if ( v22[0] )
        v11 = *(const WCHAR **)v22[0];
      else
        v11 = 0;
      if ( RegCreateKeyExW(hKey, v11, 0, 0, 0, 0xF003Fu, 0, &hKeya, &dwDisposition) )
        goto LABEL_26;
      if ( dwDisposition == 1 )
      {
        *(_DWORD *)Data = 1;
        if ( RegSetValueExW(hKeya, L"Count", 0, 4u, Data, 4u) || RegSetValueExW(hKeya, L"Index", 0, 1u, v23, 0x4Eu) )
        {
          v9 = 0;
          RegDeleteKeyExW(hKey, 0, 0xF003Fu, 0);
          goto LABEL_26;
        }
      }
      else
      {
        *(_DWORD *)Data = 0;
        *(_DWORD *)v16 = 0;
        *(_WORD *)v25 = 0;
        memset_0(v26, 0, 0x4Cu);
        cbData = 78;
        if ( RegQueryValueExW(hKeya, L"Index", 0, (LPDWORD)Data, v25, &cbData) )
          goto LABEL_26;
        v12 = v25;
        do
        {
          v13 = *((unsigned __int16 *)v12 - 40);
          v14 = *(unsigned __int16 *)v12 - v13;
          if ( v14 )
            break;
          v12 += 2;
        }
        while ( v13 );
        if ( v14 )
        {
          v9 = 0;
          cbData = 4;
          if ( !RegQueryValueExW(hKeya, L"Count", 0, (LPDWORD)Data, v16, &cbData) && *(_DWORD *)Data == 4 )
          {
            if ( *(_DWORD *)v16 == -1 )
            {
LABEL_27:
              wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKeya);
              goto LABEL_28;
            }
            ++*(_DWORD *)v16;
            if ( !RegSetValueExW(hKeya, L"Count", 0, 4u, v16, 4u) )
            {
              v9 = CredDeleteW(a4, 2u, 0);
              if ( !v9 )
              {
                --*(_DWORD *)v16;
                RegSetValueExW(hKeya, L"Count", 0, 4u, v16, 4u);
              }
            }
          }
LABEL_26:
          LeaveCriticalSection(lpCriticalSection);
          goto LABEL_27;
        }
      }
      v9 = 1;
      goto LABEL_26;
    }
  }
LABEL_28:
  wmi::AutoRef<User::UserEntry>::Release(&v21);
  _bstr_t::~_bstr_t((_bstr_t *)v22);
  return v9;
}

```

## disassembly

```asm
0x18006fd64  push    rbp
0x18006fd66  push    rbx
0x18006fd67  push    rsi
0x18006fd68  push    rdi
0x18006fd69  push    r12
0x18006fd6b  push    r13
0x18006fd6d  push    r14
0x18006fd6f  push    r15
0x18006fd71  lea     rbp, [rsp-38h]
0x18006fd76  sub     rsp, 138h
0x18006fd7d  mov     rax, cs:__security_cookie
0x18006fd84  xor     rax, rsp
0x18006fd87  mov     [rbp+70h+var_50], rax
0x18006fd8b  mov     r13, r9
0x18006fd8e  mov     rsi, r8
0x18006fd91  mov     r14, rdx
0x18006fd94  mov     r15, rcx
0x18006fd97  mov     r12, [rbp+70h+lpAccountName]
0x18006fd9e  xor     eax, eax
0x18006fda0  mov     ebx, eax
0x18006fda2  mov     [rsp+170h+var_100], rax
0x18006fda7  mov     [rsp+170h+var_108], rax
0x18006fdac  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006fdb0  inc     rdi
0x18006fdb3  cmp     [r8+rdi*2], ax
0x18006fdb8  jnz     short loc_18006FDB0
0x18006fdba  cmp     rdi, 13h
0x18006fdbe  jb      loc_180070062
0x18006fdc4  mov     word ptr [rbp+70h+var_F0], ax
0x18006fdc8  xor     edx, edx; Val
0x18006fdca  lea     r8d, [rdx+4Ch]; Size
0x18006fdce  lea     rcx, [rbp+70h+var_EE]; void *
0x18006fdd2  call    memset_0
0x18006fdd7  lea     r9, [rdi-13h]; unsigned __int64
0x18006fddb  lea     r8, [rsi+26h]; unsigned __int16 *
0x18006fddf  mov     edx, 27h ; '''; unsigned __int64
0x18006fde4  lea     rcx, [rbp+70h+var_F0]; unsigned __int16 *
0x18006fde8  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18006fded  mov     rdx, r12; lpAccountName
0x18006fdf0  lea     rcx, [rsp+170h+var_108]; this
0x18006fdf5  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x18006fdfa  xor     esi, esi
0x18006fdfc  test    eax, eax
0x18006fdfe  js      loc_180070062
0x18006fe04  lea     rdx, [rsp+170h+var_100]; struct _bstr_t *
0x18006fe09  lea     rcx, [rsp+170h+var_108]; this
0x18006fe0e  call    ?GetSidString@User@@QEBAJAEAV_bstr_t@@@Z; User::GetSidString(_bstr_t &)
0x18006fe13  test    eax, eax
0x18006fe15  js      loc_180070062
0x18006fe1b  mov     rcx, r15; lpCriticalSection
0x18006fe1e  call    cs:__imp_EnterCriticalSection
0x18006fe24  mov     [rsp+170h+hKey], rsi
0x18006fe29  mov     [rsp+170h+dwDisposition], esi
0x18006fe2d  mov     rax, [rsp+170h+var_100]
0x18006fe32  test    rax, rax
0x18006fe35  jz      short loc_18006FE3C
0x18006fe37  mov     rdx, [rax]
0x18006fe3a  jmp     short loc_18006FE3F
0x18006fe3c  mov     rdx, rsi; lpSubKey
0x18006fe3f  lea     rax, [rsp+170h+dwDisposition]
0x18006fe44  mov     [rsp+170h+lpdwDisposition], rax; lpdwDisposition
0x18006fe49  lea     rax, [rsp+170h+hKey]
0x18006fe4e  mov     [rsp+170h+phkResult], rax; phkResult
0x18006fe53  mov     [rsp+170h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18006fe58  mov     [rsp+170h+samDesired], 0F003Fh; samDesired
0x18006fe60  mov     [rsp+170h+dwOptions], esi; dwOptions
0x18006fe64  xor     r9d, r9d; lpClass
0x18006fe67  xor     r8d, r8d; Reserved
0x18006fe6a  mov     rcx, r14; hKey
0x18006fe6d  call    cs:__imp_RegCreateKeyExW
0x18006fe73  test    eax, eax
0x18006fe75  jnz     loc_18007004E
0x18006fe7b  lea     r12d, [rax+1]
0x18006fe7f  cmp     [rsp+170h+dwDisposition], r12d
0x18006fe84  jnz     short loc_18006FF04
0x18006fe86  mov     dword ptr [rsp+170h+Data], r12d
0x18006fe8b  lea     edi, [rax+4]
0x18006fe8e  mov     [rsp+170h+samDesired], edi; cbData
0x18006fe92  lea     rax, [rsp+170h+Data]
0x18006fe97  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x18006fe9c  mov     r9d, edi; dwType
0x18006fe9f  xor     r8d, r8d; Reserved
0x18006fea2  lea     rdx, aCount; "Count"
0x18006fea9  mov     rcx, [rsp+170h+hKey]; hKey
0x18006feae  call    cs:__imp_RegSetValueExW
0x18006feb4  test    eax, eax
0x18006feb6  jnz     short loc_18006FEE9
0x18006feb8  mov     [rsp+170h+samDesired], 4Eh ; 'N'; cbData
0x18006fec0  lea     rax, [rbp+70h+var_F0]
0x18006fec4  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x18006fec9  mov     r9d, r12d; dwType
0x18006fecc  xor     r8d, r8d; Reserved
0x18006fecf  lea     rdx, aIndex; "Index"
0x18006fed6  mov     rcx, [rsp+170h+hKey]; hKey
0x18006fedb  call    cs:__imp_RegSetValueExW
0x18006fee1  test    eax, eax
0x18006fee3  jz      loc_18006FF81
0x18006fee9  mov     ebx, esi
0x18006feeb  xor     r9d, r9d; Reserved
0x18006feee  xor     edx, edx; lpSubKey
0x18006fef0  mov     r8d, 0F003Fh; samDesired
0x18006fef6  mov     rcx, r14; hKey
0x18006fef9  call    cs:__imp_RegDeleteKeyExW
0x18006feff  jmp     loc_18007004E
0x18006ff04  mov     dword ptr [rsp+170h+Data], esi
0x18006ff08  mov     dword ptr [rsp+170h+var_120], esi
0x18006ff0c  mov     word ptr [rbp+70h+var_A0], si
0x18006ff10  xor     edx, edx; Val
0x18006ff12  lea     r8d, [rdx+4Ch]; Size
0x18006ff16  lea     rcx, [rbp+70h+var_9E]; void *
0x18006ff1a  call    memset_0
0x18006ff1f  mov     [rsp+170h+cbData], 4Eh ; 'N'
0x18006ff27  lea     rax, [rsp+170h+cbData]
0x18006ff2c  mov     qword ptr [rsp+170h+samDesired], rax; lpcbData
0x18006ff31  lea     rax, [rbp+70h+var_A0]
0x18006ff35  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x18006ff3a  lea     r9, [rsp+170h+Data]; lpType
0x18006ff3f  xor     r8d, r8d; lpReserved
0x18006ff42  lea     rdx, aIndex; "Index"
0x18006ff49  mov     rcx, [rsp+170h+hKey]; hKey
0x18006ff4e  call    cs:__imp_RegQueryValueExW
0x18006ff54  test    eax, eax
0x18006ff56  jnz     loc_18007004E
0x18006ff5c  lea     rax, [rbp+70h+var_A0]
0x18006ff60  lea     rcx, [rbp+70h+var_F0]
0x18006ff64  sub     rcx, rax
0x18006ff67  movzx   edx, word ptr [rax]
0x18006ff6a  movzx   r8d, word ptr [rax+rcx]
0x18006ff6f  sub     edx, r8d
0x18006ff72  jnz     short loc_18006FF7D
0x18006ff74  add     rax, 2
0x18006ff78  test    r8d, r8d
0x18006ff7b  jnz     short loc_18006FF67
0x18006ff7d  test    edx, edx
0x18006ff7f  jnz     short loc_18006FF89
0x18006ff81  mov     ebx, r12d
0x18006ff84  jmp     loc_18007004E
0x18006ff89  mov     ebx, esi
0x18006ff8b  mov     edi, 4
0x18006ff90  mov     [rsp+170h+cbData], edi
0x18006ff94  lea     rax, [rsp+170h+cbData]
0x18006ff99  mov     qword ptr [rsp+170h+samDesired], rax; lpcbData
0x18006ff9e  lea     rax, [rsp+170h+var_120]
0x18006ffa3  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x18006ffa8  lea     r9, [rsp+170h+Data]; lpType
0x18006ffad  xor     r8d, r8d; lpReserved
0x18006ffb0  lea     rdx, aCount; "Count"
0x18006ffb7  mov     rcx, [rsp+170h+hKey]; hKey
0x18006ffbc  call    cs:__imp_RegQueryValueExW
0x18006ffc2  test    eax, eax
0x18006ffc4  jnz     loc_18007004E
0x18006ffca  cmp     dword ptr [rsp+170h+Data], edi
0x18006ffce  jnz     short loc_18007004E
0x18006ffd0  mov     eax, dword ptr [rsp+170h+var_120]
0x18006ffd4  or      r14d, 0FFFFFFFFh
0x18006ffd8  cmp     eax, r14d
0x18006ffdb  jz      short loc_180070057
0x18006ffdd  add     eax, r12d
0x18006ffe0  mov     dword ptr [rsp+170h+var_120], eax
0x18006ffe4  mov     [rsp+170h+samDesired], edi; cbData
0x18006ffe8  lea     rax, [rsp+170h+var_120]
0x18006ffed  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x18006fff2  mov     r9d, edi; dwType
0x18006fff5  xor     r8d, r8d; Reserved
0x18006fff8  lea     rdx, aCount; "Count"
0x18006ffff  mov     rcx, [rsp+170h+hKey]; hKey
0x180070004  call    cs:__imp_RegSetValueExW
0x18007000a  test    eax, eax
0x18007000c  jnz     short loc_18007004E
0x18007000e  xor     r8d, r8d; Flags
0x180070011  lea     edx, [rdi-2]; Type
0x180070014  mov     rcx, r13; TargetName
0x180070017  call    cs:__imp_CredDeleteW
0x18007001d  mov     ebx, eax
0x18007001f  test    eax, eax
0x180070021  jnz     short loc_18007004E
0x180070023  add     dword ptr [rsp+170h+var_120], r14d
0x180070028  mov     [rsp+170h+samDesired], edi; cbData
0x18007002c  lea     rax, [rsp+170h+var_120]
0x180070031  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x180070036  mov     r9d, edi; dwType
0x180070039  xor     r8d, r8d; Reserved
0x18007003c  lea     rdx, aCount; "Count"
0x180070043  mov     rcx, [rsp+170h+hKey]; hKey
0x180070048  call    cs:__imp_RegSetValueExW
0x18007004e  mov     rcx, r15; lpCriticalSection
0x180070051  call    cs:__imp_LeaveCriticalSection
0x180070057  lea     rcx, [rsp+170h+hKey]; this
0x18007005c  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180070061  nop
0x180070062  lea     rcx, [rsp+170h+var_108]
0x180070067  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18007006c  nop
0x18007006d  lea     rcx, [rsp+170h+var_100]; this
0x180070072  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180070077  mov     eax, ebx
0x180070079  mov     rcx, [rbp+70h+var_50]
0x18007007d  xor     rcx, rsp; StackCookie
0x180070080  call    __security_check_cookie
0x180070085  add     rsp, 138h
0x18007008c  pop     r15
0x18007008e  pop     r14
0x180070090  pop     r13
0x180070092  pop     r12
0x180070094  pop     rdi
0x180070095  pop     rsi
0x180070096  pop     rbx
0x180070097  pop     rbp
0x180070098  retn
```
