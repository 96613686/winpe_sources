# AddRegCacheProviderNodeChannelReferences(HKEY__ *,REG_CACHE_PROVIDERNODE *)

- ea: `0x18005d854`
- end: `0x18005de24`
- name: `?AddRegCacheProviderNodeChannelReferences@@YAKPEAUHKEY__@@PEAUREG_CACHE_PROVIDERNODE@@@Z`
- size: `1488`
- prototype: `unsigned int __fastcall(HKEY, struct REG_CACHE_PROVIDERNODE *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18005a814`
- `0x18005cab8`

## callees

- `0x180006770`
- `0x180006fb0`
- `0x180008d30`
- `0x180016250`
- `0x180017b98`
- `0x18002c6f4`
- `0x18005d854`
- `0x1800660ac`
- `0x18006c144`
- `0x18006febc`
- `0x180073de0`
- `0x180092008`
- `0x18009aee0`
- `0x18009cc7c`
- `0x18009cd4c`
- `0x1800d3370`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d99c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d99c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d8a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d8a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d8c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d8c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AddRegCacheProviderNodeChannelReferences(HKEY a1, RTL_SRWLOCK *a2)
{
  RTL_SRWLOCK *v2; // r14
  HKEY v3; // r12
  RTL_SRWLOCK *v4; // rbx
  unsigned int DWORDValueNoThrow; // ebx
  unsigned int v7; // edi
  HKEY v8; // rsi
  __int64 v9; // r15
  __int64 v10; // rdi
  HKEY *phkResult; // rax
  LSTATUS v12; // eax
  void **v13; // r12
  _BYTE *v14; // rbx
  _BYTE *v15; // rsi
  __int64 v16; // rbx
  char *v17; // r14
  __int64 v18; // r15
  HKEY v19; // rbx
  _BYTE *v20; // r13
  __int64 v21; // rdi
  signed __int64 v22; // rax
  unsigned int v23[2]; // [rsp+38h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  HKEY v25; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR SubKey[4]; // [rsp+50h] [rbp-B8h] BYREF
  HKEY v27; // [rsp+58h] [rbp-B0h] BYREF
  RTL_SRWLOCK *v28; // [rsp+60h] [rbp-A8h]
  _BYTE *v29; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+70h] [rbp-98h]
  _BYTE *v31; // [rsp+78h] [rbp-90h] BYREF
  __int64 v32; // [rsp+80h] [rbp-88h]
  RTL_SRWLOCK *v33; // [rsp+88h] [rbp-80h] BYREF
  char v34; // [rsp+90h] [rbp-78h]
  _OWORD v35[2]; // [rsp+98h] [rbp-70h] BYREF
  _OWORD v36[2]; // [rsp+B8h] [rbp-50h] BYREF
  void *Src[32]; // [rsp+D8h] [rbp-30h] BYREF

  v2 = a2;
  v28 = a2;
  v3 = a1;
  v27 = a1;
  v4 = a2 + 2;
  v33 = a2 + 2;
  AcquireSRWLockExclusive(a2 + 2);
  v34 = 1;
  if ( v2[23].Ptr )
  {
    ReleaseSRWLockExclusive(v4);
    return 0;
  }
  else
  {
    v23[0] = 0;
    DWORDValueNoThrow = RegReadDWORDValueNoThrow(v3, 0, L"Count", v23);
    if ( !DWORDValueNoThrow )
    {
      v7 = v23[0];
      if ( v23[0] <= 8 )
      {
        v8 = 0;
        v25 = 0;
        if ( v23[0] )
        {
          memset(v35, 0, sizeof(v35));
          memset(v36, 0, sizeof(v36));
          `eh vector constructor iterator'(
            Src,
            0x20u,
            8u,
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit);
          v9 = 0;
          wcscpy(SubKey, L"0");
          v10 = 0;
          while ( (unsigned int)v10 < v23[0] )
          {
            SubKey[0] = v10 + 48;
            hKey = 0;
            phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
            v12 = RegOpenKeyExW(v3, SubKey, 0, 0x20019u, phkResult);
            DWORDValueNoThrow = v12;
            if ( v12 == 2 )
            {
              DWORDValueNoThrow = 15010;
LABEL_40:
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  13,
                  WPP_85f31c24d3db3aa75d76f685e4bf8a71_Traceguids,
                  DWORDValueNoThrow);
              }
LABEL_44:
              tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
              `eh vector destructor iterator'(
                Src,
                0x20u,
                8u,
                utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit);
              utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v25);
              goto LABEL_56;
            }
            if ( v12 )
              goto LABEL_40;
            v13 = &Src[4 * (unsigned int)v10];
            DWORDValueNoThrow = RegReadStringValueNoThrow(hKey, 0, &pszFormat, (__int64)v13);
            if ( DWORDValueNoThrow )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  14,
                  WPP_85f31c24d3db3aa75d76f685e4bf8a71_Traceguids,
                  DWORDValueNoThrow);
              }
              goto LABEL_44;
            }
            v14 = Src[4 * (unsigned int)v10 + 1];
            v15 = *v13;
            if ( *v13 == v14 )
            {
              DWORDValueNoThrow = 15010;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  15,
                  WPP_85f31c24d3db3aa75d76f685e4bf8a71_Traceguids,
                  15010);
              }
              goto LABEL_44;
            }
            v16 = (v14 - v15) >> 1;
            v29 = *v13;
            v30 = v16;
            if ( !(unsigned __int8)IsApplicationChannel(&v29) )
            {
              v31 = v15;
              v32 = v16;
              if ( !(unsigned __int8)IsSystemChannel(&v31) )
                v9 += v16;
            }
            DWORDValueNoThrow = RegReadDWORDValueNoThrow(hKey, 0, L"Flags", (unsigned int *)v35 + v10);
            if ( DWORDValueNoThrow )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  16,
                  WPP_85f31c24d3db3aa75d76f685e4bf8a71_Traceguids,
                  DWORDValueNoThrow);
              }
              goto LABEL_44;
            }
            DWORDValueNoThrow = RegReadDWORDValueNoThrow(hKey, 0, L"Id", (unsigned int *)v36 + v10);
            if ( DWORDValueNoThrow )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  17,
                  WPP_85f31c24d3db3aa75d76f685e4bf8a71_Traceguids,
                  DWORDValueNoThrow);
              }
              goto LABEL_44;
            }
            tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
            v10 = (unsigned int)(v10 + 1);
            v3 = v27;
          }
          v8 = (HKEY)operator new(2 * (v9 + 12LL * v23[0]));
          v25 = v8;
          if ( v23[0] )
          {
            v17 = (char *)(v8 + 6 * v23[0]);
            v18 = 0;
            v19 = v8;
            do
            {
              v20 = Src[4 * (unsigned int)v18];
              v21 = ((_BYTE *)Src[4 * (unsigned int)v18 + 1] - v20) >> 1;
              v31 = v20;
              v32 = v21;
              if ( (unsigned __int8)IsApplicationChannel(&v31) )
              {
                *(_OWORD *)v19 = *(_OWORD *)&off_1800E2938;
              }
              else
              {
                v29 = v20;
                v30 = v21;
                if ( (unsigned __int8)IsSystemChannel(&v29) )
                {
                  *(_OWORD *)v19 = *(_OWORD *)&off_1800E2948;
                }
                else
                {
                  memcpy_0(v17, v20, 2 * v21);
                  v22 = ((_BYTE *)Src[4 * (unsigned int)v18 + 1] - (_BYTE *)Src[4 * (unsigned int)v18]) >> 1;
                  *(_QWORD *)v19 = v17;
                  *((_QWORD *)v19 + 1) = v22;
                  v17 += 2 * (((_BYTE *)Src[4 * (unsigned int)v18 + 1] - (_BYTE *)Src[4 * (unsigned int)v18]) >> 1);
                }
              }
              v19[4] = *(_DWORD *)(HKEY)((_DWORD)v35 + 4 * v18);
              v19[5] = *(_DWORD *)(HKEY)((_DWORD)v36 + 4 * v18);
              v19 += 6;
              v18 = (unsigned int)(v18 + 1);
            }
            while ( (unsigned int)v18 < v23[0] );
            v2 = v28;
          }
          `eh vector destructor iterator'(
            Src,
            0x20u,
            8u,
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit);
          v7 = v23[0];
        }
        v25 = 0;
        v27 = v8;
        utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(&v2[20], &v27);
        v2[21].Ptr = v2[20].Ptr;
        v2[22].Ptr = (PVOID)v7;
        _InterlockedExchange64((volatile __int64 *)&v2[23], (__int64)&v2[21]);
        utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v27);
        utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v25);
        DWORDValueNoThrow = 0;
      }
      else
      {
        DWORDValueNoThrow = 15010;
      }
    }
LABEL_56:
    utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&v33);
    return DWORDValueNoThrow;
  }
}

```

## disassembly

```asm
0x18005d854  mov     rax, rsp
0x18005d857  mov     [rax+18h], rbx
0x18005d85b  push    rbp
0x18005d85c  push    rsi
0x18005d85d  push    rdi
0x18005d85e  push    r12
0x18005d860  push    r13
0x18005d862  push    r14
0x18005d864  push    r15
0x18005d866  lea     rbp, [rax-138h]
0x18005d86d  sub     rsp, 200h
0x18005d874  movaps  xmmword ptr [rax-48h], xmm6
0x18005d878  movaps  xmmword ptr [rax-58h], xmm7
0x18005d87c  mov     rax, cs:__security_cookie
0x18005d883  xor     rax, rsp
0x18005d886  mov     [rbp+130h+var_60], rax
0x18005d88d  mov     r14, rdx
0x18005d890  mov     [rsp+230h+var_1D8], rdx
0x18005d895  mov     r12, rcx
0x18005d898  mov     [rsp+230h+var_1E0], rcx
0x18005d89d  lea     rbx, [rdx+10h]
0x18005d8a1  mov     [rbp+130h+var_1B0], rbx
0x18005d8a5  mov     rcx, rbx; SRWLock
0x18005d8a8  call    cs:__imp_AcquireSRWLockExclusive
0x18005d8ae  mov     [rbp+130h+var_1A8], 1
0x18005d8b2  mov     rax, [r14+0B8h]
0x18005d8b9  test    rax, rax
0x18005d8bc  jz      short loc_18005D8CE
0x18005d8be  mov     rcx, rbx; SRWLock
0x18005d8c1  call    cs:__imp_ReleaseSRWLockExclusive
0x18005d8c7  xor     eax, eax
0x18005d8c9  jmp     loc_18005DDF0
0x18005d8ce  mov     [rsp+230h+var_200], 0
0x18005d8d6  lea     r9, [rsp+230h+var_200]; unsigned int *
0x18005d8db  lea     r8, aCount_1; "Count"
0x18005d8e2  xor     edx, edx; wchar_t *
0x18005d8e4  mov     rcx, r12; HKEY
0x18005d8e7  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x18005d8ec  mov     ebx, eax
0x18005d8ee  test    eax, eax
0x18005d8f0  jnz     loc_18005DDE5
0x18005d8f6  mov     edi, [rsp+230h+var_200]
0x18005d8fa  cmp     edi, 8
0x18005d8fd  jbe     short loc_18005D909
0x18005d8ff  mov     ebx, 3AA2h
0x18005d904  jmp     loc_18005DDE5
0x18005d909  xor     esi, esi
0x18005d90b  mov     [rsp+230h+var_1F0], rsi
0x18005d910  test    edi, edi
0x18005d912  jz      loc_18005DD92
0x18005d918  xorps   xmm0, xmm0
0x18005d91b  movups  [rbp+130h+var_1A0], xmm0
0x18005d91f  movups  [rbp+130h+var_190], xmm0
0x18005d923  xorps   xmm1, xmm1
0x18005d926  movups  [rbp+130h+var_180], xmm1
0x18005d92a  movups  [rbp+130h+var_170], xmm1
0x18005d92e  lea     rsi, ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18005d935  mov     [rsp+230h+phkResult], rsi; void (*)(void *)
0x18005d93a  lea     r9, ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; void (*)(void *)
0x18005d941  mov     edx, 20h ; ' '; unsigned __int64
0x18005d946  lea     r8d, [rdx-18h]; unsigned __int64
0x18005d94a  lea     rcx, [rbp+130h+Src]; void *
0x18005d94e  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18005d953  nop
0x18005d954  xor     r15d, r15d
0x18005d957  lea     ecx, [r15+30h]
0x18005d95b  mov     dword ptr [rsp+230h+SubKey], ecx
0x18005d95f  xor     edi, edi
0x18005d961  cmp     edi, [rsp+230h+var_200]
0x18005d965  jnb     loc_18005DC82
0x18005d96b  lea     eax, [rcx+rdi]
0x18005d96e  mov     [rsp+230h+SubKey], ax
0x18005d973  mov     [rsp+230h+hKey], 0
0x18005d97c  lea     rcx, [rsp+230h+hKey]
0x18005d981  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18005d986  mov     [rsp+230h+phkResult], rax; phkResult
0x18005d98b  mov     r9d, 20019h; samDesired
0x18005d991  xor     r8d, r8d; ulOptions
0x18005d994  lea     rdx, [rsp+230h+SubKey]; lpSubKey
0x18005d999  mov     rcx, r12; hKey
0x18005d99c  call    cs:__imp_RegOpenKeyExW
0x18005d9a2  mov     ebx, eax
0x18005d9a4  cmp     eax, 2
0x18005d9a7  jz      loc_18005DC12
0x18005d9ad  test    eax, eax
0x18005d9af  jnz     loc_18005DC17
0x18005d9b5  mov     esi, edi
0x18005d9b7  shl     rsi, 5
0x18005d9bb  lea     r12, [rbp+130h+Src]
0x18005d9bf  add     r12, rsi
0x18005d9c2  mov     r9, r12
0x18005d9c5  lea     r8, pszFormat
0x18005d9cc  xor     edx, edx
0x18005d9ce  mov     rcx, [rsp+230h+hKey]; hKey
0x18005d9d3  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18005d9d8  mov     ebx, eax
0x18005d9da  test    eax, eax
0x18005d9dc  jnz     loc_18005DBB4
0x18005d9e2  mov     rbx, [rbp+rsi+130h+var_158]
0x18005d9e7  mov     rsi, [r12]
0x18005d9eb  cmp     rsi, rbx
0x18005d9ee  jz      loc_18005DB4E
0x18005d9f4  sub     rbx, rsi
0x18005d9f7  sar     rbx, 1
0x18005d9fa  mov     [rsp+230h+var_1D0], rsi
0x18005d9ff  mov     [rsp+230h+var_1C8], rbx
0x18005da04  lea     rcx, [rsp+230h+var_1D0]
0x18005da09  call    ?IsApplicationChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsApplicationChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18005da0e  test    al, al
0x18005da10  jnz     short loc_18005DA2D
0x18005da12  mov     [rsp+230h+var_1C0], rsi
0x18005da17  mov     [rsp+230h+var_1B8], rbx
0x18005da1c  lea     rcx, [rsp+230h+var_1C0]
0x18005da21  call    ?IsSystemChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSystemChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18005da26  test    al, al
0x18005da28  jnz     short loc_18005DA2D
0x18005da2a  add     r15, rbx
0x18005da2d  lea     r9, [rbp+130h+var_1A0]
0x18005da31  lea     r9, [r9+rdi*4]; unsigned int *
0x18005da35  lea     r8, aFlags; "Flags"
0x18005da3c  xor     edx, edx; wchar_t *
0x18005da3e  mov     rcx, [rsp+230h+hKey]; HKEY
0x18005da43  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x18005da48  mov     ebx, eax
0x18005da4a  test    eax, eax
0x18005da4c  jnz     loc_18005DAED
0x18005da52  lea     r9, [rbp+130h+var_180]
0x18005da56  lea     r9, [r9+rdi*4]; unsigned int *
0x18005da5a  lea     r8, aId_0; "Id"
0x18005da61  xor     edx, edx; wchar_t *
0x18005da63  mov     rcx, [rsp+230h+hKey]; HKEY
0x18005da68  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x18005da6d  mov     ebx, eax
0x18005da6f  test    eax, eax
0x18005da71  jnz     short loc_18005DA8C
0x18005da73  lea     rcx, [rsp+230h+hKey]
0x18005da78  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005da7d  inc     edi
0x18005da7f  mov     r12, [rsp+230h+var_1E0]
0x18005da84  lea     ecx, [rbx+30h]
0x18005da87  jmp     loc_18005D961
0x18005da8c  lea     rax, WPP_GLOBAL_Control
0x18005da93  mov     rcx, cs:WPP_GLOBAL_Control
0x18005da9a  cmp     rcx, rax
0x18005da9d  jz      short loc_18005DAC3
0x18005da9f  test    byte ptr [rcx+1Ch], 4
0x18005daa3  jz      short loc_18005DAC3
0x18005daa5  cmp     byte ptr [rcx+19h], 2
0x18005daa9  jb      short loc_18005DAC3
0x18005daab  mov     edx, 11h
0x18005dab0  mov     r9d, ebx
0x18005dab3  lea     r8, WPP_85f31c24d3db3aa75d76f685e4bf8a71_Traceguids
0x18005daba  mov     rcx, [rcx+10h]
0x18005dabe  call    WPP_SF_d
0x18005dac3  lea     rcx, [rsp+230h+hKey]
0x18005dac8  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005dacd  nop
0x18005dace  lea     r9, ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; void (*)(void *)
0x18005dad5  mov     edx, 20h ; ' '; unsigned __int64
0x18005dada  lea     r8d, [rdx-18h]; unsigned __int64
0x18005dade  lea     rcx, [rbp+130h+Src]; void *
0x18005dae2  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18005dae7  nop
0x18005dae8  jmp     loc_18005DC73
0x18005daed  lea     rax, WPP_GLOBAL_Control
0x18005daf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dafb  cmp     rcx, rax
0x18005dafe  jz      short loc_18005DB24
0x18005db00  test    byte ptr [rcx+1Ch], 4
0x18005db04  jz      short loc_18005DB24
0x18005db06  cmp     byte ptr [rcx+19h], 2
0x18005db0a  jb      short loc_18005DB24
0x18005db0c  mov     edx, 10h
0x18005db11  mov     r9d, ebx
0x18005db14  lea     r8, WPP_85f31c24d3db3aa75d76f685e4bf8a71_Traceguids
0x18005db1b  mov     rcx, [rcx+10h]
0x18005db1f  call    WPP_SF_d
0x18005db24  lea     rcx, [rsp+230h+hKey]
0x18005db29  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005db2e  nop
0x18005db2f  lea     r9, ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; void (*)(void *)
0x18005db36  mov     edx, 20h ; ' '; unsigned __int64
0x18005db3b  lea     r8d, [rdx-18h]; unsigned __int64
0x18005db3f  lea     rcx, [rbp+130h+Src]; void *
0x18005db43  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18005db48  nop
0x18005db49  jmp     loc_18005DC73
0x18005db4e  lea     rax, WPP_GLOBAL_Control
0x18005db55  mov     ebx, 3AA2h
0x18005db5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005db61  cmp     rcx, rax
0x18005db64  jz      short loc_18005DB8A
0x18005db66  test    byte ptr [rcx+1Ch], 4
0x18005db6a  jz      short loc_18005DB8A
0x18005db6c  cmp     byte ptr [rcx+19h], 2
0x18005db70  jb      short loc_18005DB8A
0x18005db72  mov     edx, 0Fh
0x18005db77  mov     r9d, ebx
0x18005db7a  lea     r8, WPP_85f31c24d3db3aa75d76f685e4bf8a71_Traceguids
0x18005db81  mov     rcx, [rcx+10h]
0x18005db85  call    WPP_SF_d
0x18005db8a  lea     rcx, [rsp+230h+hKey]
0x18005db8f  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005db94  nop
0x18005db95  lea     r9, ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; void (*)(void *)
0x18005db9c  mov     edx, 20h ; ' '; unsigned __int64
0x18005dba1  lea     r8d, [rdx-18h]; unsigned __int64
0x18005dba5  lea     rcx, [rbp+130h+Src]; void *
0x18005dba9  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18005dbae  nop
0x18005dbaf  jmp     loc_18005DC73
0x18005dbb4  lea     rax, WPP_GLOBAL_Control
0x18005dbbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dbc2  cmp     rcx, rax
0x18005dbc5  jz      short loc_18005DBEB
0x18005dbc7  test    byte ptr [rcx+1Ch], 4
0x18005dbcb  jz      short loc_18005DBEB
0x18005dbcd  cmp     byte ptr [rcx+19h], 2
0x18005dbd1  jb      short loc_18005DBEB
0x18005dbd3  mov     edx, 0Eh
0x18005dbd8  mov     r9d, ebx
0x18005dbdb  lea     r8, WPP_85f31c24d3db3aa75d76f685e4bf8a71_Traceguids
0x18005dbe2  mov     rcx, [rcx+10h]
0x18005dbe6  call    WPP_SF_d
0x18005dbeb  lea     rcx, [rsp+230h+hKey]
0x18005dbf0  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005dbf5  nop
0x18005dbf6  lea     r9, ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; void (*)(void *)
0x18005dbfd  mov     edx, 20h ; ' '; unsigned __int64
0x18005dc02  lea     r8d, [rdx-18h]; unsigned __int64
0x18005dc06  lea     rcx, [rbp+130h+Src]; void *
0x18005dc0a  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18005dc0f  nop
0x18005dc10  jmp     short loc_18005DC73
0x18005dc12  mov     ebx, 3AA2h
0x18005dc17  lea     rax, WPP_GLOBAL_Control
0x18005dc1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dc25  cmp     rcx, rax
0x18005dc28  jz      short loc_18005DC4E
0x18005dc2a  test    byte ptr [rcx+1Ch], 4
0x18005dc2e  jz      short loc_18005DC4E
0x18005dc30  cmp     byte ptr [rcx+19h], 2
0x18005dc34  jb      short loc_18005DC4E
0x18005dc36  mov     edx, 0Dh
0x18005dc3b  mov     r9d, ebx
0x18005dc3e  lea     r8, WPP_85f31c24d3db3aa75d76f685e4bf8a71_Traceguids
0x18005dc45  mov     rcx, [rcx+10h]
0x18005dc49  call    WPP_SF_d
0x18005dc4e  lea     rcx, [rsp+230h+hKey]
0x18005dc53  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005dc58  nop
0x18005dc59  lea     r9, ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; void (*)(void *)
0x18005dc60  mov     edx, 20h ; ' '; unsigned __int64
0x18005dc65  lea     r8d, [rdx-18h]; unsigned __int64
0x18005dc69  lea     rcx, [rbp+130h+Src]; void *
0x18005dc6d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18005dc72  nop
0x18005dc73  lea     rcx, [rsp+230h+var_1F0]
0x18005dc78  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x18005dc7d  jmp     loc_18005DDE5
0x18005dc82  mov     eax, [rsp+230h+var_200]
0x18005dc86  lea     rcx, [rax+rax*2]
0x18005dc8a  lea     rcx, [r15+rcx*4]
0x18005dc8e  add     rcx, rcx; dwBytes
0x18005dc91  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005dc96  mov     rsi, rax
0x18005dc99  mov     [rsp+230h+var_1F0], rax
0x18005dc9e  mov     eax, [rsp+230h+var_200]
0x18005dca2  test    eax, eax
0x18005dca4  jz      loc_18005DD74
0x18005dcaa  lea     rdx, [rax+rax*2]
0x18005dcae  lea     r14, [rsi+rdx*8]
0x18005dcb2  xor     r15d, r15d
0x18005dcb5  mov     rbx, rsi
0x18005dcb8  movups  xmm6, xmmword ptr cs:off_1800E2938; "Application"
0x18005dcbf  movups  xmm7, xmmword ptr cs:off_1800E2948; "System"
0x18005dcc6  mov     r12d, r15d
0x18005dcc9  shl     r12, 5
0x18005dccd  mov     r13, [rbp+r12+130h+Src]
0x18005dcd2  mov     rdi, [rbp+r12+130h+var_158]
0x18005dcd7  sub     rdi, r13
0x18005dcda  sar     rdi, 1
0x18005dcdd  mov     [rsp+230h+var_1C0], r13
0x18005dce2  mov     [rsp+230h+var_1B8], rdi
0x18005dce7  lea     rcx, [rsp+230h+var_1C0]
0x18005dcec  call    ?IsApplicationChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsApplicationChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18005dcf1  test    al, al
0x18005dcf3  jz      short loc_18005DCFB
0x18005dcf5  movdqu  xmmword ptr [rbx], xmm6
0x18005dcf9  jmp     short loc_18005DD4D
0x18005dcfb  mov     [rsp+230h+var_1D0], r13
0x18005dd00  mov     [rsp+230h+var_1C8], rdi
0x18005dd05  lea     rcx, [rsp+230h+var_1D0]
0x18005dd0a  call    ?IsSystemChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSystemChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18005dd0f  test    al, al
0x18005dd11  jz      short loc_18005DD19
0x18005dd13  movdqu  xmmword ptr [rbx], xmm7
0x18005dd17  jmp     short loc_18005DD4D
0x18005dd19  lea     r8, [rdi+rdi]; Size
0x18005dd1d  mov     rdx, r13; Src
  ... truncated ...
```
