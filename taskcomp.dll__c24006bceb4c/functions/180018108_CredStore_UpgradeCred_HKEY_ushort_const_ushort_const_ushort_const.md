# CredStore::UpgradeCred(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180018108`
- end: `0x18001843d`
- name: `?UpgradeCred@CredStore@@AEAAHPEAUHKEY__@@PEBG11@Z`
- size: `821`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, HKEY hKey@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017f74`

## callees

- `0x180004e50`
- `0x180004ec0`
- `0x1800050fc`
- `0x18000518c`
- `0x18000e4d8`
- `0x180018108`
- `0x18001a288`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800181c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800181c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800183f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800183f5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001829d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001829d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800182f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018360`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800182f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018360`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018211`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018211`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018252`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001827f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800183a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800183ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018252`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001827f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800183a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800183ec`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800183bb`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800183bb`

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
              wmi::AutoRegKey::Close(&hKeya);
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
0x180018108  push    rbp
0x18001810a  push    rbx
0x18001810b  push    rsi
0x18001810c  push    rdi
0x18001810d  push    r12
0x18001810f  push    r13
0x180018111  push    r14
0x180018113  push    r15
0x180018115  lea     rbp, [rsp-38h]
0x18001811a  sub     rsp, 138h
0x180018121  mov     rax, cs:__security_cookie
0x180018128  xor     rax, rsp
0x18001812b  mov     [rbp+70h+var_50], rax
0x18001812f  mov     r13, r9
0x180018132  mov     rsi, r8
0x180018135  mov     r14, rdx
0x180018138  mov     r15, rcx
0x18001813b  mov     r12, [rbp+70h+lpAccountName]
0x180018142  xor     eax, eax
0x180018144  mov     ebx, eax
0x180018146  mov     [rsp+170h+var_100], rax
0x18001814b  mov     [rsp+170h+var_108], rax
0x180018150  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180018154  inc     rdi
0x180018157  cmp     [r8+rdi*2], ax
0x18001815c  jnz     short loc_180018154
0x18001815e  cmp     rdi, 13h
0x180018162  jb      loc_180018406
0x180018168  mov     word ptr [rbp+70h+var_F0], ax
0x18001816c  xor     edx, edx; Val
0x18001816e  lea     r8d, [rdx+4Ch]; Size
0x180018172  lea     rcx, [rbp+70h+var_EE]; void *
0x180018176  call    memset_0
0x18001817b  lea     r9, [rdi-13h]; unsigned __int64
0x18001817f  lea     r8, [rsi+26h]; unsigned __int16 *
0x180018183  mov     edx, 27h ; '''; unsigned __int64
0x180018188  lea     rcx, [rbp+70h+var_F0]; unsigned __int16 *
0x18001818c  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180018191  mov     rdx, r12; lpAccountName
0x180018194  lea     rcx, [rsp+170h+var_108]; this
0x180018199  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x18001819e  xor     esi, esi
0x1800181a0  test    eax, eax
0x1800181a2  js      loc_180018406
0x1800181a8  lea     rdx, [rsp+170h+var_100]; struct _bstr_t *
0x1800181ad  lea     rcx, [rsp+170h+var_108]; this
0x1800181b2  call    ?GetSidString@User@@QEBAJAEAV_bstr_t@@@Z; User::GetSidString(_bstr_t &)
0x1800181b7  test    eax, eax
0x1800181b9  js      loc_180018406
0x1800181bf  mov     rcx, r15; lpCriticalSection
0x1800181c2  call    cs:__imp_EnterCriticalSection
0x1800181c8  mov     [rsp+170h+hKey], rsi
0x1800181cd  mov     [rsp+170h+dwDisposition], esi
0x1800181d1  mov     rax, [rsp+170h+var_100]
0x1800181d6  test    rax, rax
0x1800181d9  jz      short loc_1800181E0
0x1800181db  mov     rdx, [rax]
0x1800181de  jmp     short loc_1800181E3
0x1800181e0  mov     rdx, rsi; lpSubKey
0x1800181e3  lea     rax, [rsp+170h+dwDisposition]
0x1800181e8  mov     [rsp+170h+lpdwDisposition], rax; lpdwDisposition
0x1800181ed  lea     rax, [rsp+170h+hKey]
0x1800181f2  mov     [rsp+170h+phkResult], rax; phkResult
0x1800181f7  mov     [rsp+170h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800181fc  mov     [rsp+170h+samDesired], 0F003Fh; samDesired
0x180018204  mov     [rsp+170h+dwOptions], esi; dwOptions
0x180018208  xor     r9d, r9d; lpClass
0x18001820b  xor     r8d, r8d; Reserved
0x18001820e  mov     rcx, r14; hKey
0x180018211  call    cs:__imp_RegCreateKeyExW
0x180018217  test    eax, eax
0x180018219  jnz     loc_1800183F2
0x18001821f  lea     r12d, [rax+1]
0x180018223  cmp     [rsp+170h+dwDisposition], r12d
0x180018228  jnz     short loc_1800182A8
0x18001822a  mov     dword ptr [rsp+170h+Data], r12d
0x18001822f  lea     edi, [rax+4]
0x180018232  mov     [rsp+170h+samDesired], edi; cbData
0x180018236  lea     rax, [rsp+170h+Data]
0x18001823b  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x180018240  mov     r9d, edi; dwType
0x180018243  xor     r8d, r8d; Reserved
0x180018246  lea     rdx, aCount; "Count"
0x18001824d  mov     rcx, [rsp+170h+hKey]; hKey
0x180018252  call    cs:__imp_RegSetValueExW
0x180018258  test    eax, eax
0x18001825a  jnz     short loc_18001828D
0x18001825c  mov     [rsp+170h+samDesired], 4Eh ; 'N'; cbData
0x180018264  lea     rax, [rbp+70h+var_F0]
0x180018268  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x18001826d  mov     r9d, r12d; dwType
0x180018270  xor     r8d, r8d; Reserved
0x180018273  lea     rdx, aIndex; "Index"
0x18001827a  mov     rcx, [rsp+170h+hKey]; hKey
0x18001827f  call    cs:__imp_RegSetValueExW
0x180018285  test    eax, eax
0x180018287  jz      loc_180018325
0x18001828d  mov     ebx, esi
0x18001828f  xor     r9d, r9d; Reserved
0x180018292  xor     edx, edx; lpSubKey
0x180018294  mov     r8d, 0F003Fh; samDesired
0x18001829a  mov     rcx, r14; hKey
0x18001829d  call    cs:__imp_RegDeleteKeyExW
0x1800182a3  jmp     loc_1800183F2
0x1800182a8  mov     dword ptr [rsp+170h+Data], esi
0x1800182ac  mov     dword ptr [rsp+170h+var_120], esi
0x1800182b0  mov     word ptr [rbp+70h+var_A0], si
0x1800182b4  xor     edx, edx; Val
0x1800182b6  lea     r8d, [rdx+4Ch]; Size
0x1800182ba  lea     rcx, [rbp+70h+var_9E]; void *
0x1800182be  call    memset_0
0x1800182c3  mov     [rsp+170h+cbData], 4Eh ; 'N'
0x1800182cb  lea     rax, [rsp+170h+cbData]
0x1800182d0  mov     qword ptr [rsp+170h+samDesired], rax; lpcbData
0x1800182d5  lea     rax, [rbp+70h+var_A0]
0x1800182d9  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x1800182de  lea     r9, [rsp+170h+Data]; lpType
0x1800182e3  xor     r8d, r8d; lpReserved
0x1800182e6  lea     rdx, aIndex; "Index"
0x1800182ed  mov     rcx, [rsp+170h+hKey]; hKey
0x1800182f2  call    cs:__imp_RegQueryValueExW
0x1800182f8  test    eax, eax
0x1800182fa  jnz     loc_1800183F2
0x180018300  lea     rax, [rbp+70h+var_A0]
0x180018304  lea     rcx, [rbp+70h+var_F0]
0x180018308  sub     rcx, rax
0x18001830b  movzx   edx, word ptr [rax]
0x18001830e  movzx   r8d, word ptr [rax+rcx]
0x180018313  sub     edx, r8d
0x180018316  jnz     short loc_180018321
0x180018318  add     rax, 2
0x18001831c  test    r8d, r8d
0x18001831f  jnz     short loc_18001830B
0x180018321  test    edx, edx
0x180018323  jnz     short loc_18001832D
0x180018325  mov     ebx, r12d
0x180018328  jmp     loc_1800183F2
0x18001832d  mov     ebx, esi
0x18001832f  mov     edi, 4
0x180018334  mov     [rsp+170h+cbData], edi
0x180018338  lea     rax, [rsp+170h+cbData]
0x18001833d  mov     qword ptr [rsp+170h+samDesired], rax; lpcbData
0x180018342  lea     rax, [rsp+170h+var_120]
0x180018347  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x18001834c  lea     r9, [rsp+170h+Data]; lpType
0x180018351  xor     r8d, r8d; lpReserved
0x180018354  lea     rdx, aCount; "Count"
0x18001835b  mov     rcx, [rsp+170h+hKey]; hKey
0x180018360  call    cs:__imp_RegQueryValueExW
0x180018366  test    eax, eax
0x180018368  jnz     loc_1800183F2
0x18001836e  cmp     dword ptr [rsp+170h+Data], edi
0x180018372  jnz     short loc_1800183F2
0x180018374  mov     eax, dword ptr [rsp+170h+var_120]
0x180018378  or      r14d, 0FFFFFFFFh
0x18001837c  cmp     eax, r14d
0x18001837f  jz      short loc_1800183FB
0x180018381  add     eax, r12d
0x180018384  mov     dword ptr [rsp+170h+var_120], eax
0x180018388  mov     [rsp+170h+samDesired], edi; cbData
0x18001838c  lea     rax, [rsp+170h+var_120]
0x180018391  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x180018396  mov     r9d, edi; dwType
0x180018399  xor     r8d, r8d; Reserved
0x18001839c  lea     rdx, aCount; "Count"
0x1800183a3  mov     rcx, [rsp+170h+hKey]; hKey
0x1800183a8  call    cs:__imp_RegSetValueExW
0x1800183ae  test    eax, eax
0x1800183b0  jnz     short loc_1800183F2
0x1800183b2  xor     r8d, r8d; Flags
0x1800183b5  lea     edx, [rdi-2]; Type
0x1800183b8  mov     rcx, r13; TargetName
0x1800183bb  call    cs:__imp_CredDeleteW
0x1800183c1  mov     ebx, eax
0x1800183c3  test    eax, eax
0x1800183c5  jnz     short loc_1800183F2
0x1800183c7  add     dword ptr [rsp+170h+var_120], r14d
0x1800183cc  mov     [rsp+170h+samDesired], edi; cbData
0x1800183d0  lea     rax, [rsp+170h+var_120]
0x1800183d5  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x1800183da  mov     r9d, edi; dwType
0x1800183dd  xor     r8d, r8d; Reserved
0x1800183e0  lea     rdx, aCount; "Count"
0x1800183e7  mov     rcx, [rsp+170h+hKey]; hKey
0x1800183ec  call    cs:__imp_RegSetValueExW
0x1800183f2  mov     rcx, r15; lpCriticalSection
0x1800183f5  call    cs:__imp_LeaveCriticalSection
0x1800183fb  lea     rcx, [rsp+170h+hKey]; this
0x180018400  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180018405  nop
0x180018406  lea     rcx, [rsp+170h+var_108]
0x18001840b  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180018410  nop
0x180018411  lea     rcx, [rsp+170h+var_100]; this
0x180018416  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001841b  mov     eax, ebx
0x18001841d  mov     rcx, [rbp+70h+var_50]
0x180018421  xor     rcx, rsp; StackCookie
0x180018424  call    __security_check_cookie
0x180018429  add     rsp, 138h
0x180018430  pop     r15
0x180018432  pop     r14
0x180018434  pop     r13
0x180018436  pop     r12
0x180018438  pop     rdi
0x180018439  pop     rsi
0x18001843a  pop     rbx
0x18001843b  pop     rbp
0x18001843c  retn
```
