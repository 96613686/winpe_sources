# CredStore::UpgradeCred(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180019214`
- end: `0x180019598`
- name: `?UpgradeCred@CredStore@@AEAAHPEAUHKEY__@@PEBG11@Z`
- size: `900`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, HKEY hKey@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019064`

## callees

- `0x1800050d0`
- `0x180005150`
- `0x1800053bc`
- `0x1800053e8`
- `0x18000edd8`
- `0x180019214`
- `0x18001b5c4`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800192ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800192ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019549`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019549`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800193c5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800193c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019420`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019494`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019420`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019494`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019323`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019323`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001936e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800193a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800194ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001953a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001936e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800193a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800194ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001953a`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180019503`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180019503`

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
      && (int)User::GetSidString((User *)&v21, (struct _bstr_t *)v22) >= 0 )
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
0x180019214  push    rbp
0x180019216  push    rbx
0x180019217  push    rsi
0x180019218  push    rdi
0x180019219  push    r12
0x18001921b  push    r13
0x18001921d  push    r14
0x18001921f  push    r15
0x180019221  lea     rbp, [rsp-38h]
0x180019226  sub     rsp, 138h
0x18001922d  mov     rax, cs:__security_cookie
0x180019234  xor     rax, rsp
0x180019237  mov     [rbp+70h+var_50], rax
0x18001923b  mov     r13, r9
0x18001923e  mov     rsi, r8
0x180019241  mov     r14, rdx
0x180019244  mov     r15, rcx
0x180019247  mov     r12, [rbp+70h+lpAccountName]
0x18001924e  xor     eax, eax
0x180019250  mov     ebx, eax
0x180019252  mov     [rsp+170h+var_100], rax
0x180019257  mov     [rsp+170h+var_108], rax
0x18001925c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180019260  inc     rdi
0x180019263  cmp     [r8+rdi*2], ax
0x180019268  jnz     short loc_180019260
0x18001926a  cmp     rdi, 13h
0x18001926e  jb      loc_180019560
0x180019274  mov     word ptr [rbp+70h+var_F0], ax
0x180019278  xor     edx, edx; Val
0x18001927a  lea     r8d, [rdx+4Ch]; Size
0x18001927e  lea     rcx, [rbp+70h+var_EE]; void *
0x180019282  call    memset_0
0x180019287  lea     r9, [rdi-13h]; unsigned __int64
0x18001928b  lea     r8, [rsi+26h]; unsigned __int16 *
0x18001928f  mov     edx, 27h ; '''; unsigned __int64
0x180019294  lea     rcx, [rbp+70h+var_F0]; unsigned __int16 *
0x180019298  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001929d  mov     rdx, r12; lpAccountName
0x1800192a0  lea     rcx, [rsp+170h+var_108]; this
0x1800192a5  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x1800192aa  xor     esi, esi
0x1800192ac  test    eax, eax
0x1800192ae  js      loc_180019560
0x1800192b4  lea     rdx, [rsp+170h+var_100]; struct _bstr_t *
0x1800192b9  lea     rcx, [rsp+170h+var_108]; this
0x1800192be  call    ?GetSidString@User@@QEBAJAEAV_bstr_t@@@Z; User::GetSidString(_bstr_t &)
0x1800192c3  test    eax, eax
0x1800192c5  js      loc_180019560
0x1800192cb  mov     rcx, r15; lpCriticalSection
0x1800192ce  call    cs:__imp_EnterCriticalSection
0x1800192d5  nop     dword ptr [rax+rax+00h]
0x1800192da  mov     [rsp+170h+hKey], rsi
0x1800192df  mov     [rsp+170h+dwDisposition], esi
0x1800192e3  mov     rax, [rsp+170h+var_100]
0x1800192e8  test    rax, rax
0x1800192eb  jz      short loc_1800192F2
0x1800192ed  mov     rdx, [rax]
0x1800192f0  jmp     short loc_1800192F5
0x1800192f2  mov     rdx, rsi; lpSubKey
0x1800192f5  lea     rax, [rsp+170h+dwDisposition]
0x1800192fa  mov     [rsp+170h+lpdwDisposition], rax; lpdwDisposition
0x1800192ff  lea     rax, [rsp+170h+hKey]
0x180019304  mov     [rsp+170h+phkResult], rax; phkResult
0x180019309  mov     [rsp+170h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18001930e  mov     [rsp+170h+samDesired], 0F003Fh; samDesired
0x180019316  mov     [rsp+170h+dwOptions], esi; dwOptions
0x18001931a  xor     r9d, r9d; lpClass
0x18001931d  xor     r8d, r8d; Reserved
0x180019320  mov     rcx, r14; hKey
0x180019323  call    cs:__imp_RegCreateKeyExW
0x18001932a  nop     dword ptr [rax+rax+00h]
0x18001932f  test    eax, eax
0x180019331  jnz     loc_180019546
0x180019337  lea     r12d, [rax+1]
0x18001933b  cmp     [rsp+170h+dwDisposition], r12d
0x180019340  jnz     loc_1800193D6
0x180019346  mov     dword ptr [rsp+170h+Data], r12d
0x18001934b  lea     edi, [rax+4]
0x18001934e  mov     [rsp+170h+samDesired], edi; cbData
0x180019352  lea     rax, [rsp+170h+Data]
0x180019357  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x18001935c  mov     r9d, edi; dwType
0x18001935f  xor     r8d, r8d; Reserved
0x180019362  lea     rdx, aCount; "Count"
0x180019369  mov     rcx, [rsp+170h+hKey]; hKey
0x18001936e  call    cs:__imp_RegSetValueExW
0x180019375  nop     dword ptr [rax+rax+00h]
0x18001937a  test    eax, eax
0x18001937c  jnz     short loc_1800193B5
0x18001937e  mov     [rsp+170h+samDesired], 4Eh ; 'N'; cbData
0x180019386  lea     rax, [rbp+70h+var_F0]
0x18001938a  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x18001938f  mov     r9d, r12d; dwType
0x180019392  xor     r8d, r8d; Reserved
0x180019395  lea     rdx, aIndex; "Index"
0x18001939c  mov     rcx, [rsp+170h+hKey]; hKey
0x1800193a1  call    cs:__imp_RegSetValueExW
0x1800193a8  nop     dword ptr [rax+rax+00h]
0x1800193ad  test    eax, eax
0x1800193af  jz      loc_180019459
0x1800193b5  mov     ebx, esi
0x1800193b7  xor     r9d, r9d; Reserved
0x1800193ba  xor     edx, edx; lpSubKey
0x1800193bc  mov     r8d, 0F003Fh; samDesired
0x1800193c2  mov     rcx, r14; hKey
0x1800193c5  call    cs:__imp_RegDeleteKeyExW
0x1800193cc  nop     dword ptr [rax+rax+00h]
0x1800193d1  jmp     loc_180019546
0x1800193d6  mov     dword ptr [rsp+170h+Data], esi
0x1800193da  mov     dword ptr [rsp+170h+var_120], esi
0x1800193de  mov     word ptr [rbp+70h+var_A0], si
0x1800193e2  xor     edx, edx; Val
0x1800193e4  lea     r8d, [rdx+4Ch]; Size
0x1800193e8  lea     rcx, [rbp+70h+var_9E]; void *
0x1800193ec  call    memset_0
0x1800193f1  mov     [rsp+170h+cbData], 4Eh ; 'N'
0x1800193f9  lea     rax, [rsp+170h+cbData]
0x1800193fe  mov     qword ptr [rsp+170h+samDesired], rax; lpcbData
0x180019403  lea     rax, [rbp+70h+var_A0]
0x180019407  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x18001940c  lea     r9, [rsp+170h+Data]; lpType
0x180019411  xor     r8d, r8d; lpReserved
0x180019414  lea     rdx, aIndex; "Index"
0x18001941b  mov     rcx, [rsp+170h+hKey]; hKey
0x180019420  call    cs:__imp_RegQueryValueExW
0x180019427  nop     dword ptr [rax+rax+00h]
0x18001942c  test    eax, eax
0x18001942e  jnz     loc_180019546
0x180019434  lea     rax, [rbp+70h+var_A0]
0x180019438  lea     rcx, [rbp+70h+var_F0]
0x18001943c  sub     rcx, rax
0x18001943f  movzx   edx, word ptr [rax]
0x180019442  movzx   r8d, word ptr [rax+rcx]
0x180019447  sub     edx, r8d
0x18001944a  jnz     short loc_180019455
0x18001944c  add     rax, 2
0x180019450  test    r8d, r8d
0x180019453  jnz     short loc_18001943F
0x180019455  test    edx, edx
0x180019457  jnz     short loc_180019461
0x180019459  mov     ebx, r12d
0x18001945c  jmp     loc_180019546
0x180019461  mov     ebx, esi
0x180019463  mov     edi, 4
0x180019468  mov     [rsp+170h+cbData], edi
0x18001946c  lea     rax, [rsp+170h+cbData]
0x180019471  mov     qword ptr [rsp+170h+samDesired], rax; lpcbData
0x180019476  lea     rax, [rsp+170h+var_120]
0x18001947b  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x180019480  lea     r9, [rsp+170h+Data]; lpType
0x180019485  xor     r8d, r8d; lpReserved
0x180019488  lea     rdx, aCount; "Count"
0x18001948f  mov     rcx, [rsp+170h+hKey]; hKey
0x180019494  call    cs:__imp_RegQueryValueExW
0x18001949b  nop     dword ptr [rax+rax+00h]
0x1800194a0  test    eax, eax
0x1800194a2  jnz     loc_180019546
0x1800194a8  cmp     dword ptr [rsp+170h+Data], edi
0x1800194ac  jnz     loc_180019546
0x1800194b2  mov     eax, dword ptr [rsp+170h+var_120]
0x1800194b6  or      r14d, 0FFFFFFFFh
0x1800194ba  cmp     eax, r14d
0x1800194bd  jz      loc_180019555
0x1800194c3  add     eax, r12d
0x1800194c6  mov     dword ptr [rsp+170h+var_120], eax
0x1800194ca  mov     [rsp+170h+samDesired], edi; cbData
0x1800194ce  lea     rax, [rsp+170h+var_120]
0x1800194d3  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x1800194d8  mov     r9d, edi; dwType
0x1800194db  xor     r8d, r8d; Reserved
0x1800194de  lea     rdx, aCount; "Count"
0x1800194e5  mov     rcx, [rsp+170h+hKey]; hKey
0x1800194ea  call    cs:__imp_RegSetValueExW
0x1800194f1  nop     dword ptr [rax+rax+00h]
0x1800194f6  test    eax, eax
0x1800194f8  jnz     short loc_180019546
0x1800194fa  xor     r8d, r8d; Flags
0x1800194fd  lea     edx, [rdi-2]; Type
0x180019500  mov     rcx, r13; TargetName
0x180019503  call    cs:__imp_CredDeleteW
0x18001950a  nop     dword ptr [rax+rax+00h]
0x18001950f  mov     ebx, eax
0x180019511  test    eax, eax
0x180019513  jnz     short loc_180019546
0x180019515  add     dword ptr [rsp+170h+var_120], r14d
0x18001951a  mov     [rsp+170h+samDesired], edi; cbData
0x18001951e  lea     rax, [rsp+170h+var_120]
0x180019523  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x180019528  mov     r9d, edi; dwType
0x18001952b  xor     r8d, r8d; Reserved
0x18001952e  lea     rdx, aCount; "Count"
0x180019535  mov     rcx, [rsp+170h+hKey]; hKey
0x18001953a  call    cs:__imp_RegSetValueExW
0x180019541  nop     dword ptr [rax+rax+00h]
0x180019546  mov     rcx, r15; lpCriticalSection
0x180019549  call    cs:__imp_LeaveCriticalSection
0x180019550  nop     dword ptr [rax+rax+00h]
0x180019555  lea     rcx, [rsp+170h+hKey]; this
0x18001955a  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18001955f  nop
0x180019560  lea     rcx, [rsp+170h+var_108]
0x180019565  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001956a  nop
0x18001956b  lea     rcx, [rsp+170h+var_100]; this
0x180019570  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019575  mov     eax, ebx
0x180019577  mov     rcx, [rbp+70h+var_50]
0x18001957b  xor     rcx, rsp; StackCookie
0x18001957e  call    __security_check_cookie
0x180019583  add     rsp, 138h
0x18001958a  pop     r15
0x18001958c  pop     r14
0x18001958e  pop     r13
0x180019590  pop     r12
0x180019592  pop     rdi
0x180019593  pop     rsi
0x180019594  pop     rbx
0x180019595  pop     rbp
0x180019596  retn
```
