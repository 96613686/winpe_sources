# ConfigCiPackageFamilyNameCheck

- ea: `0x180043670`
- end: `0x180043a1c`
- name: `ConfigCiPackageFamilyNameCheck`
- size: `940`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, unsigned __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180026494`
- `0x18002c728`
- `0x18002e5d0`
- `0x180030224`
- `0x180040970`
- `0x180041e8c`
- `0x180043670`
- `0x180048924`
- `0x180048eec`
- `0x180049568`
- `0x18004c230`
- `0x18004de6a`
- `0x18004deb0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800436d0`
- `ntdll!NtQuerySystemInformation` at `0x18004373a`
- `ntdll!NtQuerySystemInformation` at `0x1800436d0`
- `ntdll!NtQuerySystemInformation` at `0x18004373a`

## pseudocode

```c
__int64 __fastcall ConfigCiPackageFamilyNameCheck(struct _UNICODE_STRING *a1, unsigned __int64 a2)
{
  unsigned int v2; // r13d
  PVOID v5; // rbx
  NTSTATUS v6; // eax
  NTSTATUS v7; // r14d
  void *v9; // rax
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rsi
  unsigned __int64 v14; // r12
  unsigned __int64 v15; // rax
  void *v16; // rax
  int v17; // edx
  char *v18; // rdi
  unsigned int v19; // r11d
  __int64 v20; // r9
  __int64 v21; // r10
  char *v22; // rsi
  __int64 v23; // rcx
  unsigned __int64 v24; // rax
  char *v25; // rsi
  __int64 v26; // r15
  unsigned __int64 v27; // rax
  int v28; // eax
  unsigned __int8 v29; // r9
  NTSTATUS v30; // r10d
  unsigned __int8 v31; // [rsp+20h] [rbp-E0h]
  ULONG ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  PVOID SystemInformation; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v35; // [rsp+48h] [rbp-B8h]
  struct _UNICODE_STRING *v36; // [rsp+50h] [rbp-B0h]
  _BYTE v37[64]; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING *v38; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v39; // [rsp+A8h] [rbp-58h]
  _OWORD v40[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v41; // [rsp+120h] [rbp+20h]

  v2 = 0;
  v35 = a2;
  v36 = a1;
  ReturnLength = 0;
  v34 = 0;
  v5 = 0;
  SystemInformation = 0;
  v6 = NtQuerySystemInformation(SystemProcessorPowerInformation|0x80, 0, 0, &ReturnLength);
  v7 = v6;
  if ( v6 >= 0 )
  {
    wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v34);
    operator delete(0);
    return 0;
  }
  if ( v6 != -1073741820 )
    goto LABEL_40;
  v9 = operator new[](ReturnLength, (const struct std::nothrow_t *)std::nothrow);
  std::unique_ptr<_SIPOLICY_EXEC_STATUS [0]>::reset(&SystemInformation, v9);
  v5 = SystemInformation;
  if ( !SystemInformation )
    goto LABEL_40;
  v7 = NtQuerySystemInformation(SystemProcessorPowerInformation|0x80, SystemInformation, ReturnLength, &ReturnLength);
  if ( v7 < 0 )
    goto LABEL_40;
  v11 = InitializeSiPolicy(v10, v5, ReturnLength, &v34);
  v7 = v11;
  if ( v11 >= 0 )
  {
    v13 = v34;
    v14 = *(unsigned int *)(v34 + 36);
    memset_0(v37, 0, 0x88u);
    v38 = a1;
    v41 = 0;
    v39 = a2;
    memset(v40, 0, sizeof(v40));
    LODWORD(v40[0]) = 1;
    v15 = 24 * v14;
    SystemInformation = 0;
    if ( !is_mul_ok(v14, 0x18u) )
      v15 = -1;
    v16 = operator new[](v15, (const struct std::nothrow_t *)std::nothrow);
    std::unique_ptr<_SIPOLICY_EXEC_STATUS [0]>::reset(&SystemInformation, v16);
    v18 = (char *)SystemInformation;
    if ( !SystemInformation )
    {
      operator delete(0);
      v12 = -2147024882;
      goto LABEL_42;
    }
    if ( (_DWORD)v14 )
    {
      LOBYTE(v17) = 0;
      memset_0(SystemInformation, v17, 24 * v14);
    }
    SIPolicyObjectValidationEngine(v13, v40, v37, v18);
    v19 = 0;
    if ( (_DWORD)v14 )
    {
      v20 = 0x48F222A00D2EB091LL;
      v21 = SiPolicyIDEndpointSec;
      do
      {
        v22 = &v18[24 * v19];
        v23 = *(_QWORD *)v22;
        SystemInformation = v22;
        v24 = -(__int64)(*(_DWORD *)(v23 + 40) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
        if ( *(_QWORD *)(v24 + v23 + 720) == v21
          && *(_QWORD *)(v24 + v23 + 728) == v20
          && (unsigned __int8)SIPolicyIsBasePolicy() )
        {
          v7 = SIPolicyAggregatePolicyValidationResult(v22, v18, (unsigned int)v14);
          v22[8] = v7 >= 0;
          v20 = 0x48F222A00D2EB091LL;
          v21 = SiPolicyIDEndpointSec;
          goto LABEL_21;
        }
        ++v19;
      }
      while ( v19 < (unsigned int)v14 );
      SystemInformation = 0;
      do
      {
LABEL_21:
        v25 = &v18[24 * v2];
        v26 = *(_QWORD *)v25;
        v27 = -(__int64)(*(_DWORD *)(*(_QWORD *)v25 + 40LL) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
        if ( *(_QWORD *)(v27 + *(_QWORD *)v25 + 720) != v21 || *(_QWORD *)(v27 + v26 + 728) != v20 )
        {
          v28 = SIPolicyAggregatePolicyValidationResult(&v18[24 * v2], v18, (unsigned int)v14);
          v30 = 0;
          v7 = v28;
          if ( v28 < 0 )
          {
            if ( SystemInformation
              && *((_BYTE *)SystemInformation + 8)
              && !(unsigned __int8)SIPolicyIsSystemPolicy(
                                     *(_QWORD *)v25
                                   + 704LL
                                   + (-(__int64)(*(_DWORD *)(*(_QWORD *)v25 + 40LL) < 6u) & 0xFFFFFFFFFFFFFD50uLL)) )
            {
              *((_WORD *)v25 + 4) = 1;
              v7 = v30;
              *((_DWORD *)v25 + 3) = v30;
              *((_DWORD *)v25 + 5) |= 0x10000000u;
            }
            else if ( v7 == -1058471934 && v25[9] == (_BYTE)v30 && (*(_BYTE *)(v26 + 672) & 2) == 0 )
            {
              v7 = v30;
            }
            else
            {
              if ( (*(_DWORD *)(v26 + 44) & 0x10000) == 0 )
              {
                ConfigCiPackageFamilyNameCheckEventLog(v36, v35, (const void *)v26, v29, v31, v7);
                break;
              }
              ConfigCiPackageFamilyNameCheckEventLog(v36, v35, (const void *)v26, v29, v31, v7);
              v7 = 0;
            }
          }
          v21 = SiPolicyIDEndpointSec;
          v20 = 0x48F222A00D2EB091LL;
        }
        ++v2;
      }
      while ( v2 < (unsigned int)v14 );
    }
    operator delete(v18);
LABEL_40:
    wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v34);
    operator delete(v5);
    return v7 | 0x10000000u;
  }
  if ( v11 != -1073741637 )
    goto LABEL_40;
  v12 = 0;
LABEL_42:
  wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v34);
  operator delete(v5);
  return v12;
}

```

## disassembly

```asm
0x180043670  mov     [rsp-8+arg_10], rbx
0x180043675  push    rbp
0x180043676  push    rsi
0x180043677  push    rdi
0x180043678  push    r12
0x18004367a  push    r13
0x18004367c  push    r14
0x18004367e  push    r15
0x180043680  lea     rbp, [rsp-30h]
0x180043685  sub     rsp, 130h
0x18004368c  mov     rax, cs:__security_cookie
0x180043693  xor     rax, rsp
0x180043696  mov     [rbp+60h+var_38], rax
0x18004369a  xor     r13d, r13d
0x18004369d  mov     [rsp+160h+var_118], rdx
0x1800436a2  mov     r15, rdx
0x1800436a5  mov     [rsp+160h+var_110], rcx
0x1800436aa  mov     rdi, rcx
0x1800436ad  mov     [rsp+160h+ReturnLength], r13d
0x1800436b2  mov     esi, 0BDh
0x1800436b7  mov     [rsp+160h+var_120], r13
0x1800436bc  mov     ebx, r13d
0x1800436bf  lea     r9, [rsp+160h+ReturnLength]; ReturnLength
0x1800436c4  xor     r8d, r8d; SystemInformationLength
0x1800436c7  mov     [rsp+160h+SystemInformation], rbx
0x1800436cc  xor     edx, edx; SystemInformation
0x1800436ce  mov     ecx, esi; SystemInformationClass
0x1800436d0  call    cs:__imp_NtQuerySystemInformation
0x1800436d6  mov     r14d, eax
0x1800436d9  test    eax, eax
0x1800436db  js      short loc_1800436F5
0x1800436dd  lea     rcx, [rsp+160h+var_120]
0x1800436e2  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t______unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t___
0x1800436e7  xor     ecx, ecx; Block
0x1800436e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800436ee  xor     eax, eax
0x1800436f0  jmp     loc_1800439D3
0x1800436f5  cmp     eax, 0C0000004h
0x1800436fa  jnz     loc_1800439B9
0x180043700  mov     ecx, [rsp+160h+ReturnLength]; unsigned __int64
0x180043704  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004370b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180043710  mov     rdx, rax
0x180043713  lea     rcx, [rsp+160h+SystemInformation]
0x180043718  call    ?reset@?$unique_ptr@$$BY0A@U_SIPOLICY_EXEC_STATUS@@U?$default_delete@$$BY0A@U_SIPOLICY_EXEC_STATUS@@@std@@@std@@QEAAXPEAU_SIPOLICY_EXEC_STATUS@@@Z; std::unique_ptr<_SIPOLICY_EXEC_STATUS [0]>::reset(_SIPOLICY_EXEC_STATUS *)
0x18004371d  mov     rbx, [rsp+160h+SystemInformation]
0x180043722  test    rbx, rbx
0x180043725  jz      loc_1800439B9
0x18004372b  mov     r8d, [rsp+160h+ReturnLength]; SystemInformationLength
0x180043730  lea     r9, [rsp+160h+ReturnLength]; ReturnLength
0x180043735  mov     rdx, rbx; SystemInformation
0x180043738  mov     ecx, esi; SystemInformationClass
0x18004373a  call    cs:__imp_NtQuerySystemInformation
0x180043740  mov     r14d, eax
0x180043743  test    eax, eax
0x180043745  js      loc_1800439B9
0x18004374b  mov     r8d, [rsp+160h+ReturnLength]
0x180043750  lea     r9, [rsp+160h+var_120]
0x180043755  mov     rdx, rbx
0x180043758  call    InitializeSiPolicy
0x18004375d  mov     r14d, eax
0x180043760  test    eax, eax
0x180043762  jns     short loc_180043777
0x180043764  cmp     eax, 0C00000BBh
0x180043769  jnz     loc_1800439B9
0x18004376f  mov     edi, r13d
0x180043772  jmp     loc_180043A06
0x180043777  mov     rsi, [rsp+160h+var_120]
0x18004377c  lea     rcx, [rsp+160h+var_100]; void *
0x180043781  xor     edx, edx; Val
0x180043783  mov     r8d, 88h; Size
0x180043789  mov     r12d, [rsi+24h]
0x18004378d  call    memset_0
0x180043792  xor     eax, eax
0x180043794  mov     [rbp+60h+var_C0], rdi
0x180043798  mov     [rbp+60h+var_40], rax
0x18004379c  xorps   xmm0, xmm0
0x18004379f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800437a6  mov     [rbp+60h+var_B8], r15
0x1800437aa  movups  [rbp+60h+var_70], xmm0
0x1800437ae  mov     eax, 18h
0x1800437b3  mov     dword ptr [rbp+60h+var_70], 1
0x1800437ba  mul     r12
0x1800437bd  movups  [rbp+60h+var_60], xmm0
0x1800437c1  movups  [rbp+60h+var_50], xmm0
0x1800437c5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800437cc  mov     [rsp+160h+SystemInformation], r13
0x1800437d1  cmovb   rax, rcx
0x1800437d5  mov     rcx, rax; unsigned __int64
0x1800437d8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800437dd  mov     rdx, rax
0x1800437e0  lea     rcx, [rsp+160h+SystemInformation]
0x1800437e5  call    ?reset@?$unique_ptr@$$BY0A@U_SIPOLICY_EXEC_STATUS@@U?$default_delete@$$BY0A@U_SIPOLICY_EXEC_STATUS@@@std@@@std@@QEAAXPEAU_SIPOLICY_EXEC_STATUS@@@Z; std::unique_ptr<_SIPOLICY_EXEC_STATUS [0]>::reset(_SIPOLICY_EXEC_STATUS *)
0x1800437ea  mov     rdi, [rsp+160h+SystemInformation]
0x1800437ef  test    rdi, rdi
0x1800437f2  jz      loc_1800439FA
0x1800437f8  test    r12d, r12d
0x1800437fb  jz      short loc_18004380F
0x1800437fd  lea     r8, [r12+r12*2]
0x180043801  xor     dl, dl; Val
0x180043803  shl     r8, 3; Size
0x180043807  mov     rcx, rdi; void *
0x18004380a  call    memset_0
0x18004380f  mov     r9, rdi
0x180043812  lea     r8, [rsp+160h+var_100]
0x180043817  lea     rdx, [rbp+60h+var_70]
0x18004381b  mov     rcx, rsi
0x18004381e  call    SIPolicyObjectValidationEngine
0x180043823  mov     r11d, r13d
0x180043826  test    r12d, r12d
0x180043829  jz      loc_1800439B1
0x18004382f  mov     r9, cs:qword_180058D98
0x180043836  mov     r10, cs:SiPolicyIDEndpointSec
0x18004383d  mov     eax, r11d
0x180043840  lea     rcx, [rax+rax*2]
0x180043844  lea     rsi, [rdi+rcx*8]
0x180043848  mov     rcx, [rsi]
0x18004384b  mov     [rsp+160h+SystemInformation], rsi
0x180043850  cmp     dword ptr [rcx+28h], 6
0x180043854  sbb     rax, rax
0x180043857  and     rax, 0FFFFFFFFFFFFFD40h
0x18004385d  cmp     [rax+rcx+2D0h], r10
0x180043865  jnz     short loc_18004387E
0x180043867  cmp     [rax+rcx+2D8h], r9
0x18004386f  jnz     short loc_18004387E
0x180043871  call    SIPolicyIsBasePolicy
0x180043876  test    al, al
0x180043878  jnz     loc_180043922
0x18004387e  inc     r11d
0x180043881  cmp     r11d, r12d
0x180043884  jb      short loc_18004383D
0x180043886  mov     [rsp+160h+SystemInformation], r13
0x18004388b  mov     eax, r13d
0x18004388e  lea     rcx, [rax+rax*2]
0x180043892  lea     rsi, [rdi+rcx*8]
0x180043896  mov     r15, [rsi]
0x180043899  cmp     dword ptr [r15+28h], 6
0x18004389e  sbb     rax, rax
0x1800438a1  and     rax, 0FFFFFFFFFFFFFD40h
0x1800438a7  cmp     [rax+r15+2D0h], r10
0x1800438af  jnz     short loc_1800438BF
0x1800438b1  cmp     [rax+r15+2D8h], r9
0x1800438b9  jz      loc_18004399E
0x1800438bf  mov     r8d, r12d
0x1800438c2  mov     rdx, rdi
0x1800438c5  mov     rcx, rsi
0x1800438c8  call    SIPolicyAggregatePolicyValidationResult
0x1800438cd  xor     r10d, r10d
0x1800438d0  mov     r14d, eax
0x1800438d3  test    eax, eax
0x1800438d5  jns     loc_180043990
0x1800438db  mov     r11, [rsp+160h+SystemInformation]
0x1800438e0  test    r11, r11
0x1800438e3  jz      short loc_18004394E
0x1800438e5  cmp     [r11+8], r10b
0x1800438e9  jz      short loc_18004394E
0x1800438eb  mov     rax, [rsi]
0x1800438ee  cmp     dword ptr [rax+28h], 6
0x1800438f2  sbb     rcx, rcx
0x1800438f5  add     rax, 2C0h
0x1800438fb  and     rcx, 0FFFFFFFFFFFFFD50h
0x180043902  add     rcx, rax
0x180043905  call    SIPolicyIsSystemPolicy
0x18004390a  test    al, al
0x18004390c  jnz     short loc_18004394E
0x18004390e  mov     word ptr [rsi+8], 1
0x180043914  mov     r14d, r10d
0x180043917  mov     [rsi+0Ch], r10d
0x18004391b  bts     dword ptr [rsi+14h], 1Ch
0x180043920  jmp     short loc_180043990
0x180043922  mov     r8d, r12d
0x180043925  mov     rdx, rdi
0x180043928  mov     rcx, rsi
0x18004392b  call    SIPolicyAggregatePolicyValidationResult
0x180043930  mov     r14d, eax
0x180043933  shr     eax, 1Fh
0x180043936  xor     al, 1
0x180043938  mov     [rsi+8], al
0x18004393b  mov     r9, cs:qword_180058D98
0x180043942  mov     r10, cs:SiPolicyIDEndpointSec
0x180043949  jmp     loc_18004388B
0x18004394e  cmp     r14d, 0C0E90002h
0x180043955  jnz     short loc_18004396C
0x180043957  cmp     [rsi+9], r10b
0x18004395b  jnz     short loc_18004396C
0x18004395d  test    byte ptr [r15+2A0h], 2
0x180043965  jnz     short loc_18004396C
0x180043967  mov     r14d, r10d
0x18004396a  jmp     short loc_180043990
0x18004396c  test    dword ptr [r15+2Ch], 10000h
0x180043974  mov     r8, r15; void *
0x180043977  mov     rdx, [rsp+160h+var_118]; unsigned __int64
0x18004397c  mov     rcx, [rsp+160h+var_110]; struct _UNICODE_STRING *
0x180043981  mov     dword ptr [rsp+160h+var_138], r14d; char
0x180043986  jz      short loc_1800439AC
0x180043988  call    ?ConfigCiPackageFamilyNameCheckEventLog@@YAJPEBU_UNICODE_STRING@@_KPEBXEEJ@Z; ConfigCiPackageFamilyNameCheckEventLog(_UNICODE_STRING const *,unsigned __int64,void const *,uchar,uchar,long)
0x18004398d  xor     r14d, r14d
0x180043990  mov     r10, cs:SiPolicyIDEndpointSec
0x180043997  mov     r9, cs:qword_180058D98
0x18004399e  inc     r13d
0x1800439a1  cmp     r13d, r12d
0x1800439a4  jb      loc_18004388B
0x1800439aa  jmp     short loc_1800439B1
0x1800439ac  call    ?ConfigCiPackageFamilyNameCheckEventLog@@YAJPEBU_UNICODE_STRING@@_KPEBXEEJ@Z; ConfigCiPackageFamilyNameCheckEventLog(_UNICODE_STRING const *,unsigned __int64,void const *,uchar,uchar,long)
0x1800439b1  mov     rcx, rdi; Block
0x1800439b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800439b9  lea     rcx, [rsp+160h+var_120]
0x1800439be  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t______unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t___
0x1800439c3  mov     rcx, rbx; Block
0x1800439c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800439cb  bts     r14d, 1Ch
0x1800439d0  mov     eax, r14d
0x1800439d3  mov     rcx, [rbp+60h+var_38]
0x1800439d7  xor     rcx, rsp; StackCookie
0x1800439da  call    __security_check_cookie
0x1800439df  mov     rbx, [rsp+160h+arg_10]
0x1800439e7  add     rsp, 130h
0x1800439ee  pop     r15
0x1800439f0  pop     r14
0x1800439f2  pop     r13
0x1800439f4  pop     r12
0x1800439f6  pop     rdi
0x1800439f7  pop     rsi
0x1800439f8  pop     rbp
0x1800439f9  retn
0x1800439fa  xor     ecx, ecx; Block
0x1800439fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180043a01  mov     edi, 8007000Eh
0x180043a06  lea     rcx, [rsp+160h+var_120]
0x180043a0b  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t______unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t___
0x180043a10  mov     rcx, rbx; Block
0x180043a13  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180043a18  mov     eax, edi
0x180043a1a  jmp     short loc_1800439D3
```
