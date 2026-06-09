# NetpWkstarClientCertificateMappingEnum

- ea: `0x180022dd0`
- end: `0x18002339e`
- name: `NetpWkstarClientCertificateMappingEnum`
- size: `1486`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180009010`
- `0x180009090`
- `0x18000a240`
- `0x180022dd0`
- `0x180023e54`
- `0x180024520`
- `0x180024550`
- `0x1800248a4`
- `0x180025d54`
- `0x180025eb0`
- `0x1800263bc`
- `0x180036191`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180022e86`
- `ntdll!RtlAcquireResourceExclusive` at `0x180022e86`
- `ntdll!RtlReleaseResource` at `0x180022f7c`
- `ntdll!RtlReleaseResource` at `0x180022f7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022f2e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022feb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023031`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023079`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800230c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023109`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023151`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023199`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800231e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023229`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022f2e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022feb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023031`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023079`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800230c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023109`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023151`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023199`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800231e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023229`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023351`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023351`

## string_xrefs

- `0x180022e4e`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetpWkstarClientCertificateMappingEnum(__int64 a1, void **a2, __int64 a3, _DWORD *a4)
{
  _QWORD *v6; // rcx
  __int64 v8; // rdi
  unsigned int CertificateMappings; // eax
  unsigned int v10; // ebx
  __int64 v11; // rax
  HLOCAL v12; // rax
  unsigned int v13; // ebp
  _QWORD *v14; // rcx
  __int64 v15; // rsi
  __int64 v16; // rax
  SIZE_T v17; // rbx
  HLOCAL v18; // rax
  __int64 v19; // rax
  SIZE_T v20; // rbx
  HLOCAL v21; // rax
  __int64 v22; // rax
  SIZE_T v23; // rbx
  HLOCAL v24; // rax
  __int64 v25; // rax
  SIZE_T v26; // rbx
  HLOCAL v27; // rax
  __int64 v28; // rax
  SIZE_T v29; // rbx
  HLOCAL v30; // rax
  __int64 v31; // rax
  SIZE_T v32; // rbx
  HLOCAL v33; // rax
  __int64 v34; // rax
  SIZE_T v35; // rbx
  HLOCAL v36; // rax
  __int64 v37; // rax
  SIZE_T v38; // rbx
  HLOCAL v39; // rax
  __int64 v40; // rax
  SIZE_T v41; // rbx
  HLOCAL v42; // rax
  int v43; // eax
  int v44; // edx
  int v45; // r8d
  void *v46; // rcx

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a2 && a4 )
  {
    if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, (__int64)a2, L"WkstaConfigurationInfo") )
    {
      return 5;
    }
    else
    {
      *a2 = 0;
      *a4 = 0;
      v8 = 0;
      RtlAcquireResourceExclusive(&stru_180051B90, 1u);
      WsFreeCertificateMappings();
      CertificateMappings = WsGetCertificateMappings();
      v10 = CertificateMappings;
      if ( CertificateMappings )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            101,
            &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids,
            CertificateMappings);
        }
      }
      else
      {
        v11 = *(unsigned int *)(*((_QWORD *)hMem + 1) + 4LL);
        if ( (_DWORD)v11 )
        {
          v12 = LocalAlloc(0x40u, 96 * v11);
          v8 = (__int64)v12;
          if ( v12 )
          {
            v13 = 0;
            *a4 = *(_DWORD *)(*((_QWORD *)hMem + 1) + 4LL);
            *a2 = v12;
            v14 = hMem;
            v15 = *(_QWORD *)(*((_QWORD *)hMem + 1) + 8LL);
            while ( v13 < *(_DWORD *)(v14[1] + 4LL) )
            {
              v16 = -1;
              do
                ++v16;
              while ( *(_WORD *)(*(_QWORD *)v15 + 2 * v16) );
              v17 = 2 * v16 + 2;
              v18 = LocalAlloc(0x40u, v17);
              *(_QWORD *)v8 = v18;
              if ( !v18 )
                goto LABEL_24;
              memcpy_0(v18, *(const void **)v15, v17);
              v19 = -1;
              do
                ++v19;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 8) + 2 * v19) );
              v20 = 2 * v19 + 2;
              v21 = LocalAlloc(0x40u, v20);
              *(_QWORD *)(v8 + 8) = v21;
              if ( !v21 )
                goto LABEL_24;
              memcpy_0(v21, *(const void **)(v15 + 8), v20);
              v22 = -1;
              do
                ++v22;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 16) + 2 * v22) );
              v23 = 2 * v22 + 2;
              v24 = LocalAlloc(0x40u, v23);
              *(_QWORD *)(v8 + 16) = v24;
              if ( !v24 )
                goto LABEL_24;
              memcpy_0(v24, *(const void **)(v15 + 16), v23);
              v25 = -1;
              do
                ++v25;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 24) + 2 * v25) );
              v26 = 2 * v25 + 2;
              v27 = LocalAlloc(0x40u, v26);
              *(_QWORD *)(v8 + 24) = v27;
              if ( !v27 )
                goto LABEL_24;
              memcpy_0(v27, *(const void **)(v15 + 24), v26);
              v28 = -1;
              do
                ++v28;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 32) + 2 * v28) );
              v29 = 2 * v28 + 2;
              v30 = LocalAlloc(0x40u, v29);
              *(_QWORD *)(v8 + 32) = v30;
              if ( !v30 )
                goto LABEL_24;
              memcpy_0(v30, *(const void **)(v15 + 32), v29);
              v31 = -1;
              do
                ++v31;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 40) + 2 * v31) );
              v32 = 2 * v31 + 2;
              v33 = LocalAlloc(0x40u, v32);
              *(_QWORD *)(v8 + 40) = v33;
              if ( !v33 )
                goto LABEL_24;
              memcpy_0(v33, *(const void **)(v15 + 40), v32);
              v34 = -1;
              do
                ++v34;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 48) + 2 * v34) );
              v35 = 2 * v34 + 2;
              v36 = LocalAlloc(0x40u, v35);
              *(_QWORD *)(v8 + 48) = v36;
              if ( !v36 )
                goto LABEL_24;
              memcpy_0(v36, *(const void **)(v15 + 48), v35);
              v37 = -1;
              do
                ++v37;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 56) + 2 * v37) );
              v38 = 2 * v37 + 2;
              v39 = LocalAlloc(0x40u, v38);
              *(_QWORD *)(v8 + 56) = v39;
              if ( !v39 )
                goto LABEL_24;
              memcpy_0(v39, *(const void **)(v15 + 56), v38);
              v40 = -1;
              do
                ++v40;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 64) + 2 * v40) );
              v41 = 2 * v40 + 2;
              v42 = LocalAlloc(0x40u, v41);
              *(_QWORD *)(v8 + 64) = v42;
              if ( !v42 )
                goto LABEL_24;
              memcpy_0(v42, *(const void **)(v15 + 64), v41);
              v10 = WsImpersonateClient2("NetpWkstarClientCertificateMappingEnum", 98);
              if ( v10 )
                break;
              PopulateRenewalChain(v8);
              WsRevertToSelf2("NetpWkstarClientCertificateMappingEnum", 3689);
              v43 = *(_DWORD *)(v15 + 80);
              *(_DWORD *)(v8 + 80) = v43;
              v44 = *(_DWORD *)(v15 + 84);
              *(_DWORD *)(v8 + 84) = v44;
              v45 = *(_DWORD *)(v15 + 88);
              *(_DWORD *)(v8 + 88) = v45;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_SSSSSSSSSSddd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v44,
                  v45,
                  *(_QWORD *)v8,
                  *(_QWORD *)(v8 + 8),
                  *(_QWORD *)(v8 + 16),
                  *(_QWORD *)(v8 + 24),
                  *(_QWORD *)(v8 + 32),
                  *(_QWORD *)(v8 + 40),
                  *(_QWORD *)(v8 + 48),
                  *(_QWORD *)(v8 + 56),
                  *(_QWORD *)(v8 + 64),
                  *(_QWORD *)(v8 + 72),
                  v43,
                  v44,
                  v45);
              }
              v14 = hMem;
              v15 += 96;
              v8 += 96;
              ++v13;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids);
            }
LABEL_24:
            v10 = 8;
          }
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids);
        }
      }
      RtlReleaseResource(&stru_180051B90);
      if ( v10 && v8 )
      {
        while ( 1 )
        {
          v46 = *a2;
          if ( (void *)v8 == *a2 )
            break;
          WsFreeCertificateMapping(v8);
          v8 -= 96;
        }
        if ( v46 )
          LocalFree(v46);
        *a2 = 0;
      }
      return v10;
    }
  }
  else
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) )
      WPP_SF_(v6[2], 100, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids);
    return 87;
  }
}

```

## disassembly

```asm
0x180022dd0  push    rbx
0x180022dd2  push    rbp
0x180022dd3  push    rsi
0x180022dd4  push    rdi
0x180022dd5  push    r13
0x180022dd7  push    r14
0x180022dd9  push    r15
0x180022ddb  sub     rsp, 80h
0x180022de2  mov     rsi, r9
0x180022de5  mov     r14, rdx
0x180022de8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180022def  lea     r13, WPP_GLOBAL_Control
0x180022df6  lea     rbp, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180022dfd  cmp     rcx, r13
0x180022e00  jz      short loc_180022E26
0x180022e02  test    byte ptr [rcx+1Ch], 2
0x180022e06  jz      short loc_180022E26
0x180022e08  cmp     byte ptr [rcx+19h], 2
0x180022e0c  jb      short loc_180022E26
0x180022e0e  mov     rcx, [rcx+10h]
0x180022e12  mov     edx, 63h ; 'c'
0x180022e17  mov     r8, rbp
0x180022e1a  call    WPP_SF_
0x180022e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e26  xor     r15d, r15d
0x180022e29  test    r14, r14
0x180022e2c  jz      loc_180023364
0x180022e32  test    rsi, rsi
0x180022e35  jz      loc_180023364
0x180022e3b  mov     rax, cs:ConfigurationInfoSd
0x180022e42  lea     rcx, WsConfigInfoMapping
0x180022e49  mov     [rsp+0B8h+var_88], rcx
0x180022e4e  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x180022e55  mov     dword ptr [rsp+0B8h+var_90], 2
0x180022e5d  mov     [rsp+0B8h+var_98], rax
0x180022e62  call    NetpAccessCheckAndAuditEx
0x180022e67  test    eax, eax
0x180022e69  jz      short loc_180022E74
0x180022e6b  lea     eax, [r15+5]
0x180022e6f  jmp     loc_18002338B
0x180022e74  mov     [r14], r15
0x180022e77  lea     rcx, stru_180051B90; Resource
0x180022e7e  mov     dl, 1; Wait
0x180022e80  mov     [rsi], r15d
0x180022e83  mov     rdi, r15
0x180022e86  call    cs:__imp_RtlAcquireResourceExclusive
0x180022e8d  nop     dword ptr [rax+rax+00h]
0x180022e92  call    WsFreeCertificateMappings
0x180022e97  call    WsGetCertificateMappings
0x180022e9c  mov     ebx, eax
0x180022e9e  test    eax, eax
0x180022ea0  jz      short loc_180022EDF
0x180022ea2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180022ea9  cmp     rcx, r13
0x180022eac  jz      loc_180022F75
0x180022eb2  test    byte ptr [rcx+1Ch], 2
0x180022eb6  jz      loc_180022F75
0x180022ebc  cmp     byte ptr [rcx+19h], 1
0x180022ec0  jb      loc_180022F75
0x180022ec6  mov     rcx, [rcx+10h]
0x180022eca  mov     edx, 65h ; 'e'
0x180022ecf  mov     r9d, eax
0x180022ed2  mov     r8, rbp
0x180022ed5  call    WPP_SF_d
0x180022eda  jmp     loc_180022F75
0x180022edf  mov     rax, cs:hMem
0x180022ee6  mov     rcx, [rax+8]
0x180022eea  mov     eax, [rcx+4]
0x180022eed  cmp     eax, 1
0x180022ef0  jnb     short loc_180022F1D
0x180022ef2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180022ef9  cmp     rcx, r13
0x180022efc  jz      short loc_180022F75
0x180022efe  test    byte ptr [rcx+1Ch], 2
0x180022f02  jz      short loc_180022F75
0x180022f04  cmp     byte ptr [rcx+19h], 2
0x180022f08  jb      short loc_180022F75
0x180022f0a  mov     rcx, [rcx+10h]
0x180022f0e  mov     edx, 66h ; 'f'
0x180022f13  mov     r8, rbp
0x180022f16  call    WPP_SF_
0x180022f1b  jmp     short loc_180022F75
0x180022f1d  lea     rdx, [rax+rax*2]
0x180022f21  mov     r13d, 40h ; '@'
0x180022f27  shl     rdx, 5; uBytes
0x180022f2b  mov     ecx, r13d; uFlags
0x180022f2e  call    cs:__imp_LocalAlloc
0x180022f35  nop     dword ptr [rax+rax+00h]
0x180022f3a  mov     rdi, rax
0x180022f3d  test    rax, rax
0x180022f40  jnz     short loc_180022F9E
0x180022f42  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180022f49  lea     rax, WPP_GLOBAL_Control
0x180022f50  cmp     rcx, rax
0x180022f53  jz      short loc_180022F70
0x180022f55  test    byte ptr [rcx+1Ch], 2
0x180022f59  jz      short loc_180022F70
0x180022f5b  cmp     byte ptr [rcx+19h], 1
0x180022f5f  jb      short loc_180022F70
0x180022f61  mov     rcx, [rcx+10h]
0x180022f65  lea     edx, [rdi+67h]
0x180022f68  mov     r8, rbp
0x180022f6b  call    WPP_SF_
0x180022f70  mov     ebx, 8
0x180022f75  lea     rcx, stru_180051B90; Resource
0x180022f7c  call    cs:__imp_RtlReleaseResource
0x180022f83  nop     dword ptr [rax+rax+00h]
0x180022f88  test    ebx, ebx
0x180022f8a  jz      loc_180023360
0x180022f90  test    rdi, rdi
0x180022f93  jz      loc_180023360
0x180022f99  jmp     loc_180023344
0x180022f9e  mov     rax, cs:hMem
0x180022fa5  mov     ebp, r15d
0x180022fa8  mov     rcx, [rax+8]
0x180022fac  mov     eax, [rcx+4]
0x180022faf  mov     [rsi], eax
0x180022fb1  mov     [r14], rdi
0x180022fb4  mov     rcx, cs:hMem
0x180022fbb  mov     rax, [rcx+8]
0x180022fbf  mov     rsi, [rax+8]
0x180022fc3  mov     rax, [rcx+8]
0x180022fc7  cmp     ebp, [rax+4]
0x180022fca  jnb     short loc_180022F75
0x180022fcc  mov     rcx, [rsi]
0x180022fcf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022fd3  inc     rax
0x180022fd6  cmp     [rcx+rax*2], r15w
0x180022fdb  jnz     short loc_180022FD3
0x180022fdd  lea     rbx, ds:2[rax*2]
0x180022fe5  mov     ecx, r13d; uFlags
0x180022fe8  mov     rdx, rbx; uBytes
0x180022feb  call    cs:__imp_LocalAlloc
0x180022ff2  nop     dword ptr [rax+rax+00h]
0x180022ff7  mov     [rdi], rax
0x180022ffa  test    rax, rax
0x180022ffd  jz      loc_180022F70
0x180023003  mov     rdx, [rsi]; Src
0x180023006  mov     r8, rbx; Size
0x180023009  mov     rcx, rax; void *
0x18002300c  call    memcpy_0
0x180023011  mov     rcx, [rsi+8]
0x180023015  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023019  inc     rax
0x18002301c  cmp     [rcx+rax*2], r15w
0x180023021  jnz     short loc_180023019
0x180023023  lea     rbx, ds:2[rax*2]
0x18002302b  mov     ecx, r13d; uFlags
0x18002302e  mov     rdx, rbx; uBytes
0x180023031  call    cs:__imp_LocalAlloc
0x180023038  nop     dword ptr [rax+rax+00h]
0x18002303d  mov     [rdi+8], rax
0x180023041  test    rax, rax
0x180023044  jz      loc_180022F70
0x18002304a  mov     rdx, [rsi+8]; Src
0x18002304e  mov     r8, rbx; Size
0x180023051  mov     rcx, rax; void *
0x180023054  call    memcpy_0
0x180023059  mov     rcx, [rsi+10h]
0x18002305d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023061  inc     rax
0x180023064  cmp     [rcx+rax*2], r15w
0x180023069  jnz     short loc_180023061
0x18002306b  lea     rbx, ds:2[rax*2]
0x180023073  mov     ecx, r13d; uFlags
0x180023076  mov     rdx, rbx; uBytes
0x180023079  call    cs:__imp_LocalAlloc
0x180023080  nop     dword ptr [rax+rax+00h]
0x180023085  mov     [rdi+10h], rax
0x180023089  test    rax, rax
0x18002308c  jz      loc_180022F70
0x180023092  mov     rdx, [rsi+10h]; Src
0x180023096  mov     r8, rbx; Size
0x180023099  mov     rcx, rax; void *
0x18002309c  call    memcpy_0
0x1800230a1  mov     rcx, [rsi+18h]
0x1800230a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800230a9  inc     rax
0x1800230ac  cmp     [rcx+rax*2], r15w
0x1800230b1  jnz     short loc_1800230A9
0x1800230b3  lea     rbx, ds:2[rax*2]
0x1800230bb  mov     ecx, r13d; uFlags
0x1800230be  mov     rdx, rbx; uBytes
0x1800230c1  call    cs:__imp_LocalAlloc
0x1800230c8  nop     dword ptr [rax+rax+00h]
0x1800230cd  mov     [rdi+18h], rax
0x1800230d1  test    rax, rax
0x1800230d4  jz      loc_180022F70
0x1800230da  mov     rdx, [rsi+18h]; Src
0x1800230de  mov     r8, rbx; Size
0x1800230e1  mov     rcx, rax; void *
0x1800230e4  call    memcpy_0
0x1800230e9  mov     rcx, [rsi+20h]
0x1800230ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800230f1  inc     rax
0x1800230f4  cmp     [rcx+rax*2], r15w
0x1800230f9  jnz     short loc_1800230F1
0x1800230fb  lea     rbx, ds:2[rax*2]
0x180023103  mov     ecx, r13d; uFlags
0x180023106  mov     rdx, rbx; uBytes
0x180023109  call    cs:__imp_LocalAlloc
0x180023110  nop     dword ptr [rax+rax+00h]
0x180023115  mov     [rdi+20h], rax
0x180023119  test    rax, rax
0x18002311c  jz      loc_180022F70
0x180023122  mov     rdx, [rsi+20h]; Src
0x180023126  mov     r8, rbx; Size
0x180023129  mov     rcx, rax; void *
0x18002312c  call    memcpy_0
0x180023131  mov     rcx, [rsi+28h]
0x180023135  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023139  inc     rax
0x18002313c  cmp     [rcx+rax*2], r15w
0x180023141  jnz     short loc_180023139
0x180023143  lea     rbx, ds:2[rax*2]
0x18002314b  mov     ecx, r13d; uFlags
0x18002314e  mov     rdx, rbx; uBytes
0x180023151  call    cs:__imp_LocalAlloc
0x180023158  nop     dword ptr [rax+rax+00h]
0x18002315d  mov     [rdi+28h], rax
0x180023161  test    rax, rax
0x180023164  jz      loc_180022F70
0x18002316a  mov     rdx, [rsi+28h]; Src
0x18002316e  mov     r8, rbx; Size
0x180023171  mov     rcx, rax; void *
0x180023174  call    memcpy_0
0x180023179  mov     rcx, [rsi+30h]
0x18002317d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023181  inc     rax
0x180023184  cmp     [rcx+rax*2], r15w
0x180023189  jnz     short loc_180023181
0x18002318b  lea     rbx, ds:2[rax*2]
0x180023193  mov     ecx, r13d; uFlags
0x180023196  mov     rdx, rbx; uBytes
0x180023199  call    cs:__imp_LocalAlloc
0x1800231a0  nop     dword ptr [rax+rax+00h]
0x1800231a5  mov     [rdi+30h], rax
0x1800231a9  test    rax, rax
0x1800231ac  jz      loc_180022F70
0x1800231b2  mov     rdx, [rsi+30h]; Src
0x1800231b6  mov     r8, rbx; Size
0x1800231b9  mov     rcx, rax; void *
0x1800231bc  call    memcpy_0
0x1800231c1  mov     rcx, [rsi+38h]
0x1800231c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800231c9  inc     rax
0x1800231cc  cmp     [rcx+rax*2], r15w
0x1800231d1  jnz     short loc_1800231C9
0x1800231d3  lea     rbx, ds:2[rax*2]
0x1800231db  mov     ecx, r13d; uFlags
0x1800231de  mov     rdx, rbx; uBytes
0x1800231e1  call    cs:__imp_LocalAlloc
0x1800231e8  nop     dword ptr [rax+rax+00h]
0x1800231ed  mov     [rdi+38h], rax
0x1800231f1  test    rax, rax
0x1800231f4  jz      loc_180022F70
0x1800231fa  mov     rdx, [rsi+38h]; Src
0x1800231fe  mov     r8, rbx; Size
0x180023201  mov     rcx, rax; void *
0x180023204  call    memcpy_0
0x180023209  mov     rcx, [rsi+40h]
0x18002320d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023211  inc     rax
0x180023214  cmp     [rcx+rax*2], r15w
0x180023219  jnz     short loc_180023211
0x18002321b  lea     rbx, ds:2[rax*2]
0x180023223  mov     ecx, r13d; uFlags
0x180023226  mov     rdx, rbx; uBytes
0x180023229  call    cs:__imp_LocalAlloc
0x180023230  nop     dword ptr [rax+rax+00h]
0x180023235  mov     [rdi+40h], rax
0x180023239  test    rax, rax
0x18002323c  jz      loc_180022F70
0x180023242  mov     rdx, [rsi+40h]; Src
0x180023246  mov     r8, rbx; Size
0x180023249  mov     rcx, rax; void *
0x18002324c  call    memcpy_0
0x180023251  mov     edx, 0E62h
0x180023256  lea     rcx, aNetpwkstarclie_0; "NetpWkstarClientCertificateMappingEnum"
0x18002325d  call    WsImpersonateClient2
0x180023262  mov     ebx, eax
0x180023264  test    eax, eax
0x180023266  jnz     loc_180022F75
0x18002326c  mov     rcx, rdi
0x18002326f  call    PopulateRenewalChain
0x180023274  mov     edx, 0E69h
0x180023279  lea     rcx, aNetpwkstarclie_0; "NetpWkstarClientCertificateMappingEnum"
0x180023280  call    WsRevertToSelf2
0x180023285  mov     eax, [rsi+50h]
0x180023288  mov     [rdi+50h], eax
0x18002328b  mov     edx, [rsi+54h]
0x18002328e  mov     [rdi+54h], edx
0x180023291  mov     r8d, [rsi+58h]
0x180023295  mov     [rdi+58h], r8d
0x180023299  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800232a0  lea     r9, WPP_GLOBAL_Control
0x1800232a7  cmp     rcx, r9
0x1800232aa  jz      short loc_180023322
0x1800232ac  test    byte ptr [rcx+1Ch], 2
0x1800232b0  jz      short loc_180023322
  ... truncated ...
```
