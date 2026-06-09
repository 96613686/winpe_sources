# ComputeService::ContainerDefinition::ApplyHiveStackSettings(gsl::span<Schema::Containers::Definition::RegistryHiveStack,-1>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,gsl::span<Schema::Common::Resources::Layer const,-1>)

- ea: `0x1400cfac8`
- end: `0x1400cff50`
- name: `?ApplyHiveStackSettings@ContainerDefinition@ComputeService@@YAXV?$span@URegistryHiveStack@Definition@Containers@Schema@@$0?0@gsl@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$span@$$CBULayer@Resources@Common@Schema@@$0?0@4@@Z`
- size: `1160`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d051c`

## callees

- `0x140005360`
- `0x140006098`
- `0x140008760`
- `0x14001bfa4`
- `0x140022b78`
- `0x1400274b4`
- `0x140027858`
- `0x14002dd18`
- `0x140030078`
- `0x14003bc60`
- `0x1400433ac`
- `0x14004346c`
- `0x140044afc`
- `0x1400863f4`
- `0x1400cfac8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400cfb62`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400cfb86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400cfda6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400cfb62`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400cfb86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400cfda6`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1400cfbf5`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1400cfbf5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1400cfd4e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1400cfd4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ComputeService::ContainerDefinition::ApplyHiveStackSettings(
        _QWORD *a1,
        unsigned __int64 *a2,
        __int64 *a3)
{
  __int64 *v3; // r12
  int v6; // esi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _QWORD *v9; // r15
  _QWORD *v10; // rcx
  _QWORD *v11; // rcx
  gsl::details *v12; // rcx
  __int64 v13; // rdi
  char v14; // r14
  __int64 v15; // r12
  _BYTE *v16; // rax
  LPCWSTR *v17; // rdx
  __int64 v18; // rax
  wchar_t *v19; // rdx
  const WCHAR *v20; // rcx
  __int64 v21; // r14
  LPCWSTR *v22; // rdx
  _QWORD *v23; // rcx
  __int64 v24; // r14
  __int64 *v25; // rdi
  const void *v26; // rdx
  unsigned __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rdi
  _QWORD *v32; // rdx
  _QWORD *v34; // [rsp+40h] [rbp-C0h]
  _BYTE v35[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v37[32]; // [rsp+88h] [rbp-78h] BYREF
  int v38; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR pszPath[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v40; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v41; // [rsp+C8h] [rbp-38h]
  _QWORD v42[4]; // [rsp+D0h] [rbp-30h] BYREF
  char v43[8]; // [rsp+F0h] [rbp-10h] BYREF
  int v44; // [rsp+F8h] [rbp-8h]
  const wchar_t *v45; // [rsp+100h] [rbp+0h]
  int *v46; // [rsp+108h] [rbp+8h]
  int v47; // [rsp+110h] [rbp+10h]
  int *v48; // [rsp+118h] [rbp+18h]
  int v49; // [rsp+120h] [rbp+20h]

  v3 = a3;
  v6 = 0;
  v7 = (_QWORD *)Vml::AppendToSystemPath(v37, L"containers\\machine_user");
  if ( v7[3] > 7u )
    v7 = (_QWORD *)*v7;
  Vml::DosToNtPath(v42, v7);
  std::wstring::~wstring(v37);
  v8 = (_QWORD *)a1[1];
  v9 = &v8[13 * *a1];
  v34 = v9;
  while ( v8 != v9 )
  {
    if ( v8[3] <= 7u )
      v10 = v8;
    else
      v10 = (_QWORD *)*v8;
    if ( (unsigned int)_o__wcsicmp(v10, L"User")
      && (v8[3] <= 7u ? (v11 = v8) : (v11 = (_QWORD *)*v8), (unsigned int)_o__wcsicmp(v11, L"Machine")) )
    {
      v38 = 2;
      memset_0(v43, 0, 0x70u);
      v45 = L"DeltaHivePolicy";
      v46 = &v38;
      v44 = 288;
      v47 = 67108868;
      v48 = &v38;
      v49 = 4;
      RtlQueryRegistryValuesEx(2, L"Windows Containers", v43);
      if ( v38 )
        v13 = *v3;
      else
        v13 = 1;
      if ( v13 )
      {
        v14 = 1;
        do
        {
          if ( --v13 >= (unsigned __int64)*v3 )
            gsl::details::terminate(v12);
          v15 = v3[1];
          *(_OWORD *)pszPath = 0;
          v40 = 0;
          v41 = 7;
          LOWORD(pszPath[0]) = 0;
          if ( *(_DWORD *)(56 * v13 + v15 + 48) == 1 )
          {
            Vml::FormatString(Src, (wchar_t *)L"\\\\?\\VMSMB\\VSMB-{dcc079ae-60ba-4d07-847c-3493609c0870}\\%ls");
            v16 = Src;
            v6 |= 5u;
          }
          else
          {
            v16 = (_BYTE *)std::wstring::wstring(v35, 56 * v13 + v15 + 16);
            v6 |= 2u;
          }
          std::wstring::operator=(pszPath, v16);
          if ( (v6 & 2) != 0 )
          {
            v6 &= ~2u;
            std::wstring::~wstring(v35);
          }
          if ( (v6 & 1) != 0 )
          {
            v6 &= ~1u;
            std::wstring::~wstring(Src);
          }
          std::wstring::operator+=(pszPath, L"\\Hives\\");
          std::wstring::append(pszPath);
          v17 = pszPath;
          if ( v41 > 7 )
            v17 = (LPCWSTR *)pszPath[0];
          v18 = Vml::DosToNtPath(v35, v17);
          std::wstring::operator=(pszPath, v18);
          std::wstring::~wstring(v35);
          v19 = L"_Base";
          if ( !v14 )
            v19 = L"_Delta";
          std::wstring::operator+=(pszPath, v19);
          if ( v14 )
            goto LABEL_33;
          v20 = (const WCHAR *)pszPath;
          if ( v41 > 7 )
            v20 = pszPath[0];
          if ( PathFileExistsW(v20) )
          {
LABEL_33:
            std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<>(v8 + 4);
            v21 = v8[5];
            if ( (LPCWSTR *)(v21 - 64) != pszPath )
            {
              v22 = pszPath;
              if ( v41 > 7 )
                v22 = (LPCWSTR *)pszPath[0];
              std::wstring::_Assign<unsigned short>((void **)(v21 - 64), v22, v40);
            }
            *(_WORD *)(v21 - 16) = 257;
            if ( v8[3] <= 7u )
              v23 = v8;
            else
              v23 = (_QWORD *)*v8;
            *(_BYTE *)(v21 - 13) = (unsigned int)_o__wcsicmp(v23, L"defaultuser") != 0;
            *(_OWORD *)(v21 - 32) = *(_OWORD *)(56 * v13 + v15);
          }
          v14 = 0;
          std::wstring::~wstring(pszPath);
          v3 = a3;
        }
        while ( v13 );
        v9 = v34;
      }
      std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<>(v8 + 4);
      v24 = v8[5];
      v25 = (__int64 *)(v24 - 64);
      if ( (unsigned __int64 *)(v24 - 64) != a2 )
      {
        if ( a2[3] <= 7 )
          v26 = a2;
        else
          v26 = (const void *)*a2;
        std::wstring::_Assign<unsigned short>((void **)(v24 - 64), v26, a2[2]);
      }
      v27 = *(_QWORD *)(v24 - 48);
      if ( v27 >= *(_QWORD *)(v24 - 40) )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>((void *)(v24 - 64));
      }
      else
      {
        *(_QWORD *)(v24 - 48) = v27 + 1;
        if ( *(_QWORD *)(v24 - 40) <= 7u )
          v28 = v24 - 64;
        else
          v28 = *v25;
        *(_DWORD *)(v28 + 2 * v27) = 92;
      }
      std::wstring::operator+=((void *)(v24 - 64), (void *)L"WcSandboxState");
      std::wstring::operator+=((void *)(v24 - 64), L"\\Hives\\");
      std::wstring::append((void *)(v24 - 64));
      if ( *(_QWORD *)(v24 - 40) <= 7u )
        v29 = v24 - 64;
      else
        v29 = *v25;
      v30 = Vml::DosToNtPath(v35, v29);
      std::wstring::operator=(v24 - 64, v30);
      std::wstring::~wstring(v35);
      std::wstring::operator+=((void *)(v24 - 64), L"_Delta");
      *(GUID *)(v24 - 32) = ComputeService::ContainerDefinition::SiloIdPlaceholder;
      *(_BYTE *)(v24 - 16) = 0;
      *(_BYTE *)(v24 - 14) = 1;
    }
    else
    {
      std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<>(v8 + 4);
      v31 = v8[5];
      if ( (_QWORD *)(v31 - 64) != v42 )
      {
        v32 = v42;
        if ( v42[3] > 7u )
          v32 = (_QWORD *)v42[0];
        std::wstring::_Assign<unsigned short>((void **)(v31 - 64), v32, v42[2]);
      }
      *(GUID *)(v31 - 32) = ComputeService::ContainerDefinition::SiloIdPlaceholder;
      *(_BYTE *)(v31 - 16) = 1;
      *(_BYTE *)(v31 - 13) = 1;
    }
    v8 += 13;
  }
  std::wstring::~wstring(v42);
}

```

## disassembly

```asm
0x1400cfac8  mov     [rsp-8+arg_18], rbx
0x1400cfacd  push    rbp
0x1400cface  push    rsi
0x1400cfacf  push    rdi
0x1400cfad0  push    r12
0x1400cfad2  push    r13
0x1400cfad4  push    r14
0x1400cfad6  push    r15
0x1400cfad8  lea     rbp, [rsp-70h]
0x1400cfadd  sub     rsp, 170h
0x1400cfae4  mov     rax, cs:__security_cookie
0x1400cfaeb  xor     rax, rsp
0x1400cfaee  mov     [rbp+0A0h+var_40], rax
0x1400cfaf2  mov     r12, r8
0x1400cfaf5  mov     [rsp+1A0h+var_168], r8
0x1400cfafa  mov     r13, rdx
0x1400cfafd  mov     rdi, rcx
0x1400cfb00  xor     esi, esi
0x1400cfb02  mov     [rsp+1A0h+var_170], esi
0x1400cfb06  lea     rdx, aContainersMach; "containers\\machine_user"
0x1400cfb0d  lea     rcx, [rbp+0A0h+var_118]; Src
0x1400cfb11  call    ?AppendToSystemPath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Vml::AppendToSystemPath(ushort const *)
0x1400cfb16  nop
0x1400cfb17  cmp     qword ptr [rax+18h], 7
0x1400cfb1c  jbe     short loc_1400CFB21
0x1400cfb1e  mov     rax, [rax]
0x1400cfb21  mov     rdx, rax
0x1400cfb24  lea     rcx, [rbp+0A0h+var_D0]
0x1400cfb28  call    ?DosToNtPath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Vml::DosToNtPath(ushort const *)
0x1400cfb2d  nop
0x1400cfb2e  lea     rcx, [rbp+0A0h+var_118]; void *
0x1400cfb32  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400cfb37  mov     rbx, [rdi+8]
0x1400cfb3b  imul    r15, [rdi], 68h ; 'h'
0x1400cfb3f  add     r15, rbx
0x1400cfb42  mov     [rsp+1A0h+var_160], r15
0x1400cfb47  jmp     loc_1400CFF11
0x1400cfb4c  cmp     qword ptr [rbx+18h], 7
0x1400cfb51  jbe     short loc_1400CFB58
0x1400cfb53  mov     rcx, [rbx]
0x1400cfb56  jmp     short loc_1400CFB5B
0x1400cfb58  mov     rcx, rbx
0x1400cfb5b  lea     rdx, aUser; "User"
0x1400cfb62  call    cs:__imp__o__wcsicmp
0x1400cfb68  test    eax, eax
0x1400cfb6a  jz      loc_1400CFEC8
0x1400cfb70  cmp     qword ptr [rbx+18h], 7
0x1400cfb75  jbe     short loc_1400CFB7C
0x1400cfb77  mov     rcx, [rbx]
0x1400cfb7a  jmp     short loc_1400CFB7F
0x1400cfb7c  mov     rcx, rbx
0x1400cfb7f  lea     rdx, aMachine; "Machine"
0x1400cfb86  call    cs:__imp__o__wcsicmp
0x1400cfb8c  test    eax, eax
0x1400cfb8e  jz      loc_1400CFEC8
0x1400cfb94  mov     [rbp+0A0h+var_F8], 2
0x1400cfb9b  xor     edx, edx; Val
0x1400cfb9d  lea     r8d, [rdx+70h]; Size
0x1400cfba1  lea     rcx, [rbp+0A0h+var_B0]; void *
0x1400cfba5  call    memset_0
0x1400cfbaa  lea     rax, aDeltahivepolic; "DeltaHivePolicy"
0x1400cfbb1  mov     [rbp+0A0h+var_A0], rax
0x1400cfbb5  lea     rax, [rbp+0A0h+var_F8]
0x1400cfbb9  mov     [rbp+0A0h+var_98], rax
0x1400cfbbd  mov     [rbp+0A0h+var_A8], 120h
0x1400cfbc4  mov     [rbp+0A0h+var_90], 4000004h
0x1400cfbcb  lea     rax, [rbp+0A0h+var_F8]
0x1400cfbcf  mov     [rbp+0A0h+var_88], rax
0x1400cfbd3  mov     [rbp+0A0h+var_80], 4
0x1400cfbda  mov     [rsp+1A0h+var_180], 0
0x1400cfbe3  xor     r9d, r9d
0x1400cfbe6  lea     r8, [rbp+0A0h+var_B0]
0x1400cfbea  lea     rdx, aWindowsContain; "Windows Containers"
0x1400cfbf1  lea     ecx, [r9+2]
0x1400cfbf5  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400cfbfb  cmp     [rbp+0A0h+var_F8], 0
0x1400cfbff  jbe     short loc_1400CFC07
0x1400cfc01  mov     rdi, [r12]
0x1400cfc05  jmp     short loc_1400CFC0C
0x1400cfc07  mov     edi, 1
0x1400cfc0c  test    rdi, rdi
0x1400cfc0f  jz      loc_1400CFDDF
0x1400cfc15  mov     r14b, 1
0x1400cfc18  dec     rdi
0x1400cfc1b  cmp     rdi, [r12]
0x1400cfc1f  jnb     loc_1400CFF4A
0x1400cfc25  imul    r15, rdi, 38h ; '8'
0x1400cfc29  mov     r12, [r12+8]
0x1400cfc2e  xorps   xmm0, xmm0
0x1400cfc31  movups  xmmword ptr [rbp+0A0h+pszPath], xmm0
0x1400cfc35  mov     [rbp+0A0h+var_E0], 0
0x1400cfc3d  mov     [rbp+0A0h+var_D8], 7
0x1400cfc45  xor     eax, eax
0x1400cfc47  mov     word ptr [rbp+0A0h+pszPath], ax
0x1400cfc4b  lea     rdx, [r12+10h]
0x1400cfc50  add     rdx, r15
0x1400cfc53  cmp     dword ptr [r15+r12+30h], 1
0x1400cfc59  jnz     short loc_1400CFC87
0x1400cfc5b  cmp     qword ptr [r15+r12+28h], 7
0x1400cfc61  jbe     short loc_1400CFC66
0x1400cfc63  mov     rdx, [rdx]
0x1400cfc66  mov     r8, rdx
0x1400cfc69  lea     rdx, aVmsmbVsmbDcc07; "\\\\?\\VMSMB\\VSMB-{dcc079ae-60ba-4d07-"...
0x1400cfc70  lea     rcx, [rsp+1A0h+Src]; Src
0x1400cfc75  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400cfc7a  or      esi, 4
0x1400cfc7d  lea     rax, [rsp+1A0h+Src]
0x1400cfc82  or      esi, 1
0x1400cfc85  jmp     short loc_1400CFC94
0x1400cfc87  lea     rcx, [rsp+1A0h+var_158]
0x1400cfc8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400cfc91  or      esi, 2
0x1400cfc94  mov     [rsp+1A0h+var_170], esi
0x1400cfc98  mov     rdx, rax
0x1400cfc9b  lea     rcx, [rbp+0A0h+pszPath]
0x1400cfc9f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400cfca4  test    sil, 2
0x1400cfca8  jz      short loc_1400CFCBC
0x1400cfcaa  and     esi, 0FFFFFFFDh
0x1400cfcad  mov     [rsp+1A0h+var_170], esi
0x1400cfcb1  lea     rcx, [rsp+1A0h+var_158]; void *
0x1400cfcb6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400cfcbb  nop
0x1400cfcbc  test    sil, 1
0x1400cfcc0  jz      short loc_1400CFCD3
0x1400cfcc2  and     esi, 0FFFFFFFEh
0x1400cfcc5  mov     [rsp+1A0h+var_170], esi
0x1400cfcc9  lea     rcx, [rsp+1A0h+Src]; void *
0x1400cfcce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400cfcd3  lea     rdx, aHives; "\\Hives\\"
0x1400cfcda  lea     rcx, [rbp+0A0h+pszPath]; Src
0x1400cfcde  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1400cfce3  mov     rdx, rbx
0x1400cfce6  lea     rcx, [rbp+0A0h+pszPath]; Src
0x1400cfcea  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1400cfcef  lea     rdx, [rbp+0A0h+pszPath]
0x1400cfcf3  cmp     [rbp+0A0h+var_D8], 7
0x1400cfcf8  cmova   rdx, [rbp+0A0h+pszPath]
0x1400cfcfd  lea     rcx, [rsp+1A0h+var_158]
0x1400cfd02  call    ?DosToNtPath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Vml::DosToNtPath(ushort const *)
0x1400cfd07  mov     rdx, rax
0x1400cfd0a  lea     rcx, [rbp+0A0h+pszPath]
0x1400cfd0e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400cfd13  lea     rcx, [rsp+1A0h+var_158]; void *
0x1400cfd18  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400cfd1d  lea     rdx, aBase; "_Base"
0x1400cfd24  test    r14b, r14b
0x1400cfd27  lea     rax, aDelta; "_Delta"
0x1400cfd2e  cmovz   rdx, rax; void *
0x1400cfd32  lea     rcx, [rbp+0A0h+pszPath]; Src
0x1400cfd36  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1400cfd3b  test    r14b, r14b
0x1400cfd3e  jnz     short loc_1400CFD58
0x1400cfd40  lea     rcx, [rbp+0A0h+pszPath]
0x1400cfd44  cmp     [rbp+0A0h+var_D8], 7
0x1400cfd49  cmova   rcx, [rbp+0A0h+pszPath]; pszPath
0x1400cfd4e  call    cs:__imp_PathFileExistsW
0x1400cfd54  test    eax, eax
0x1400cfd56  jz      short loc_1400CFDC0
0x1400cfd58  lea     rcx, [rbx+20h]
0x1400cfd5c  call    ??$emplace_back@$$V@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@QEAAAEAURegistryLayer@Definition@Containers@Schema@@XZ; std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<>(void)
0x1400cfd61  mov     r14, [rbx+28h]
0x1400cfd65  lea     rcx, [r14-40h]
0x1400cfd69  lea     rax, [rbp+0A0h+pszPath]
0x1400cfd6d  cmp     rcx, rax
0x1400cfd70  jz      short loc_1400CFD89
0x1400cfd72  lea     rdx, [rbp+0A0h+pszPath]
0x1400cfd76  cmp     [rbp+0A0h+var_D8], 7
0x1400cfd7b  cmova   rdx, [rbp+0A0h+pszPath]
0x1400cfd80  mov     r8, [rbp+0A0h+var_E0]
0x1400cfd84  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400cfd89  mov     word ptr [r14-10h], 101h
0x1400cfd90  cmp     qword ptr [rbx+18h], 7
0x1400cfd95  jbe     short loc_1400CFD9C
0x1400cfd97  mov     rcx, [rbx]
0x1400cfd9a  jmp     short loc_1400CFD9F
0x1400cfd9c  mov     rcx, rbx
0x1400cfd9f  lea     rdx, aDefaultuser; "defaultuser"
0x1400cfda6  call    cs:__imp__o__wcsicmp
0x1400cfdac  test    eax, eax
0x1400cfdae  setnz   al
0x1400cfdb1  mov     [r14-0Dh], al
0x1400cfdb5  movups  xmm0, xmmword ptr [r15+r12]
0x1400cfdba  movdqu  xmmword ptr [r14-20h], xmm0
0x1400cfdc0  xor     r14b, r14b
0x1400cfdc3  lea     rcx, [rbp+0A0h+pszPath]; void *
0x1400cfdc7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400cfdcc  test    rdi, rdi
0x1400cfdcf  mov     r12, [rsp+1A0h+var_168]
0x1400cfdd4  jnz     loc_1400CFC18
0x1400cfdda  mov     r15, [rsp+1A0h+var_160]
0x1400cfddf  lea     rcx, [rbx+20h]
0x1400cfde3  call    ??$emplace_back@$$V@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@QEAAAEAURegistryLayer@Definition@Containers@Schema@@XZ; std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<>(void)
0x1400cfde8  mov     r14, [rbx+28h]
0x1400cfdec  lea     rdi, [r14-40h]
0x1400cfdf0  cmp     rdi, r13
0x1400cfdf3  jz      short loc_1400CFE11
0x1400cfdf5  cmp     qword ptr [r13+18h], 7
0x1400cfdfa  jbe     short loc_1400CFE02
0x1400cfdfc  mov     rdx, [r13+0]
0x1400cfe00  jmp     short loc_1400CFE05
0x1400cfe02  mov     rdx, r13
0x1400cfe05  mov     r8, [r13+10h]
0x1400cfe09  mov     rcx, rdi
0x1400cfe0c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400cfe11  mov     rcx, [r14-30h]
0x1400cfe15  cmp     rcx, [r14-28h]
0x1400cfe19  jnb     short loc_1400CFE3B
0x1400cfe1b  lea     rax, [rcx+1]
0x1400cfe1f  mov     [r14-30h], rax
0x1400cfe23  cmp     qword ptr [r14-28h], 7
0x1400cfe28  jbe     short loc_1400CFE2F
0x1400cfe2a  mov     rdx, [rdi]
0x1400cfe2d  jmp     short loc_1400CFE32
0x1400cfe2f  mov     rdx, rdi
0x1400cfe32  mov     dword ptr [rdx+rcx*2], 5Ch ; '\'
0x1400cfe39  jmp     short loc_1400CFE49
0x1400cfe3b  mov     r9d, 5Ch ; '\'
0x1400cfe41  mov     rcx, rdi; Src
0x1400cfe44  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1400cfe49  lea     rdx, aWcsandboxstate; "WcSandboxState"
0x1400cfe50  mov     rcx, rdi; Src
0x1400cfe53  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1400cfe58  lea     rdx, aHives; "\\Hives\\"
0x1400cfe5f  mov     rcx, rdi; Src
0x1400cfe62  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1400cfe67  mov     rdx, rbx
0x1400cfe6a  mov     rcx, rdi; Src
0x1400cfe6d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1400cfe72  cmp     qword ptr [r14-28h], 7
0x1400cfe77  jbe     short loc_1400CFE7E
0x1400cfe79  mov     rdx, [rdi]
0x1400cfe7c  jmp     short loc_1400CFE81
0x1400cfe7e  mov     rdx, rdi
0x1400cfe81  lea     rcx, [rsp+1A0h+var_158]
0x1400cfe86  call    ?DosToNtPath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Vml::DosToNtPath(ushort const *)
0x1400cfe8b  mov     rdx, rax
0x1400cfe8e  mov     rcx, rdi
0x1400cfe91  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400cfe96  lea     rcx, [rsp+1A0h+var_158]; void *
0x1400cfe9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400cfea0  lea     rdx, aDelta; "_Delta"
0x1400cfea7  mov     rcx, rdi; Src
0x1400cfeaa  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1400cfeaf  movups  xmm0, xmmword ptr cs:?SiloIdPlaceholder@ContainerDefinition@ComputeService@@3U_GUID@@B.Data1; _GUID const ComputeService::ContainerDefinition::SiloIdPlaceholder ...
0x1400cfeb6  movdqu  xmmword ptr [r14-20h], xmm0
0x1400cfebc  mov     byte ptr [r14-10h], 0
0x1400cfec1  mov     byte ptr [r14-0Eh], 1
0x1400cfec6  jmp     short loc_1400CFF0D
0x1400cfec8  lea     rcx, [rbx+20h]
0x1400cfecc  call    ??$emplace_back@$$V@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@QEAAAEAURegistryLayer@Definition@Containers@Schema@@XZ; std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<>(void)
0x1400cfed1  mov     rdi, [rbx+28h]
0x1400cfed5  lea     rcx, [rdi-40h]
0x1400cfed9  lea     rax, [rbp+0A0h+var_D0]
0x1400cfedd  cmp     rcx, rax
0x1400cfee0  jz      short loc_1400CFEF9
0x1400cfee2  lea     rdx, [rbp+0A0h+var_D0]
0x1400cfee6  cmp     [rbp+0A0h+var_B8], 7
0x1400cfeeb  cmova   rdx, [rbp+0A0h+var_D0]
0x1400cfef0  mov     r8, [rbp+0A0h+var_C0]
0x1400cfef4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400cfef9  movups  xmm0, xmmword ptr cs:?SiloIdPlaceholder@ContainerDefinition@ComputeService@@3U_GUID@@B.Data1; _GUID const ComputeService::ContainerDefinition::SiloIdPlaceholder ...
0x1400cff00  movdqu  xmmword ptr [rdi-20h], xmm0
0x1400cff05  mov     byte ptr [rdi-10h], 1
0x1400cff09  mov     byte ptr [rdi-0Dh], 1
0x1400cff0d  add     rbx, 68h ; 'h'
0x1400cff11  cmp     rbx, r15
0x1400cff14  jnz     loc_1400CFB4C
0x1400cff1a  lea     rcx, [rbp+0A0h+var_D0]; void *
0x1400cff1e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400cff23  mov     rcx, [rbp+0A0h+var_40]
0x1400cff27  xor     rcx, rsp; StackCookie
0x1400cff2a  call    __security_check_cookie
0x1400cff2f  mov     rbx, [rsp+1A0h+arg_18]
0x1400cff37  add     rsp, 170h
0x1400cff3e  pop     r15
0x1400cff40  pop     r14
0x1400cff42  pop     r13
0x1400cff44  pop     r12
0x1400cff46  pop     rdi
0x1400cff47  pop     rsi
0x1400cff48  pop     rbp
0x1400cff49  retn
0x1400cff4a  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
