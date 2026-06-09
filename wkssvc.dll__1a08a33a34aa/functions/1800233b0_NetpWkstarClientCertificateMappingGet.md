# NetpWkstarClientCertificateMappingGet

- ea: `0x1800233b0`
- end: `0x180023929`
- name: `NetpWkstarClientCertificateMappingGet`
- size: `1401`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180009010`
- `0x180009090`
- `0x18000a240`
- `0x1800233b0`
- `0x180023e54`
- `0x180024520`
- `0x180024778`
- `0x180024c7c`
- `0x180036191`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180023448`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023448`
- `ntdll!RtlReleaseResource` at `0x180023862`
- `ntdll!RtlReleaseResource` at `0x180023862`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002348d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002363e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023687`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800236d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002371d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023768`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002348d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002363e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023687`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800236d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002371d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023768`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002388c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002388c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238f5`

## string_xrefs

- `0x180023418`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetpWkstarClientCertificateMappingGet(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _DWORD *a7,
        HLOCAL *a8)
{
  unsigned int v9; // ebx
  HLOCAL *v11; // rdi
  int v12; // ebp
  unsigned int v13; // r15d
  __int64 v14; // rsi
  _UNKNOWN **v15; // r10
  unsigned __int16 *v16; // rax
  int v17; // ecx
  int v18; // edx
  unsigned __int16 *v19; // rax
  int v20; // ecx
  int v21; // edx
  unsigned __int16 *v22; // rax
  int v23; // ecx
  int v24; // edx
  unsigned __int16 *v25; // rax
  int v26; // ecx
  int v27; // edx
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
  HLOCAL v43; // rcx
  HLOCAL v44; // rcx
  HLOCAL v45; // rcx
  HLOCAL v46; // rcx
  HLOCAL v47; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids);
  }
  v9 = 0;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  RtlAcquireResourceExclusive(&stru_180051B90, 1u);
  if ( a6 )
  {
    v11 = 0;
    v9 = 775;
  }
  else
  {
    v11 = (HLOCAL *)LocalAlloc(0x40u, 96LL * *(unsigned int *)(*((_QWORD *)hMem + 1) + 4LL));
    if ( v11 )
    {
      v12 = 0;
      v13 = 0;
      v14 = *(_QWORD *)(*((_QWORD *)hMem + 1) + 8LL);
      *a8 = v11;
      v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
      while ( v13 < *(_DWORD *)(*((_QWORD *)hMem + 1) + 4LL) )
      {
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 2u )
        {
          WPP_SF_SSSS((TRACEHANDLE)v15[2], a3, a4, a5);
          v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
        }
        v16 = (unsigned __int16 *)a2;
        if ( !a2 )
          goto LABEL_34;
        do
        {
          v17 = *(unsigned __int16 *)((char *)v16 + *(_QWORD *)v14 - a2);
          v18 = *v16 - v17;
          if ( v18 )
            break;
          ++v16;
        }
        while ( v17 );
        if ( !v18 )
        {
LABEL_34:
          v19 = (unsigned __int16 *)a3;
          if ( !a3 )
            goto LABEL_82;
          do
          {
            v20 = *(unsigned __int16 *)((char *)v19 + *(_QWORD *)(v14 + 8) - a3);
            v21 = *v19 - v20;
            if ( v21 )
              break;
            ++v19;
          }
          while ( v20 );
          if ( !v21 )
          {
LABEL_82:
            if ( !a4 )
              goto LABEL_83;
            v22 = (unsigned __int16 *)a4;
            do
            {
              v23 = *(unsigned __int16 *)((char *)v22 + *(_QWORD *)(v14 + 24) - a4);
              v24 = *v22 - v23;
              if ( v24 )
                break;
              ++v22;
            }
            while ( v23 );
            if ( !v24 )
            {
LABEL_83:
              if ( !a5 )
                goto LABEL_37;
              v25 = (unsigned __int16 *)a5;
              do
              {
                v26 = *(unsigned __int16 *)((char *)v25 + *(_QWORD *)(v14 + 32) - a5);
                v27 = *v25 - v26;
                if ( v27 )
                  break;
                ++v25;
              }
              while ( v26 );
              if ( !v27 )
              {
LABEL_37:
                if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 2u )
                  WPP_SF_(v15[2], 75, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids);
                v28 = -1;
                do
                  ++v28;
                while ( *(_WORD *)(*(_QWORD *)v14 + 2 * v28) );
                v29 = 2 * v28 + 2;
                v30 = LocalAlloc(0x40u, v29);
                *v11 = v30;
                if ( !v30 )
                  goto LABEL_10;
                memcpy_0(v30, *(const void **)v14, v29);
                v31 = -1;
                do
                  ++v31;
                while ( *(_WORD *)(*(_QWORD *)(v14 + 8) + 2 * v31) );
                v32 = 2 * v31 + 2;
                v33 = LocalAlloc(0x40u, v32);
                v11[1] = v33;
                if ( !v33 )
                  goto LABEL_10;
                memcpy_0(v33, *(const void **)(v14 + 8), v32);
                v34 = -1;
                do
                  ++v34;
                while ( *(_WORD *)(*(_QWORD *)(v14 + 24) + 2 * v34) );
                v35 = 2 * v34 + 2;
                v36 = LocalAlloc(0x40u, v35);
                v11[3] = v36;
                if ( !v36 )
                  goto LABEL_10;
                memcpy_0(v36, *(const void **)(v14 + 24), v35);
                v37 = -1;
                do
                  ++v37;
                while ( *(_WORD *)(*(_QWORD *)(v14 + 64) + 2 * v37) );
                v38 = 2 * v37 + 2;
                v39 = LocalAlloc(0x40u, v38);
                v11[8] = v39;
                if ( !v39 )
                  goto LABEL_10;
                memcpy_0(v39, *(const void **)(v14 + 64), v38);
                v40 = -1;
                do
                  ++v40;
                while ( *(_WORD *)(*(_QWORD *)(v14 + 32) + 2 * v40) );
                v41 = 2 * v40 + 2;
                v42 = LocalAlloc(0x40u, v41);
                v11[4] = v42;
                if ( !v42 )
                  goto LABEL_10;
                memcpy_0(v42, *(const void **)(v14 + 32), v41);
                *((_DWORD *)v11 + 20) = *(_DWORD *)(v14 + 80);
                *((_DWORD *)v11 + 21) = *(_DWORD *)(v14 + 84);
                *((_DWORD *)v11 + 22) = *(_DWORD *)(v14 + 88);
                v9 = WsImpersonateClient2("NetpWkstarClientCertificateMappingGet", 245);
                if ( v9 )
                  goto LABEL_62;
                PopulateRenewalChain((__int64)v11);
                WsRevertToSelf2("NetpWkstarClientCertificateMappingGet", 2554);
                v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_SSSSSdd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    (__int64)v11[1],
                    (__int64)v11[3],
                    (__int64)v11[4],
                    (__int64)v11[8],
                    *((_DWORD *)v11 + 20),
                    *((_DWORD *)v11 + 21));
                  v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
                }
                ++v12;
                v11 += 12;
              }
            }
          }
        }
        v14 += 96;
        ++v13;
      }
      *a7 = v12;
    }
    else
    {
LABEL_10:
      v9 = 8;
    }
  }
LABEL_62:
  RtlReleaseResource(&stru_180051B90);
  if ( v9 && v11 )
  {
    while ( v11 != *a8 )
    {
      if ( *v11 )
        LocalFree(*v11);
      v43 = v11[1];
      if ( v43 )
        LocalFree(v43);
      v44 = v11[3];
      if ( v44 )
        LocalFree(v44);
      v45 = v11[8];
      if ( v45 )
        LocalFree(v45);
      v46 = v11[4];
      if ( v46 )
        LocalFree(v46);
      v47 = v11[9];
      if ( v47 )
        LocalFree(v47);
      v11 -= 12;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800233b0  mov     [rsp+arg_0], rbx
0x1800233b5  mov     [rsp+arg_10], r8
0x1800233ba  mov     [rsp+arg_8], rdx
0x1800233bf  push    rbp
0x1800233c0  push    rsi
0x1800233c1  push    rdi
0x1800233c2  push    r12
0x1800233c4  push    r13
0x1800233c6  push    r14
0x1800233c8  push    r15
0x1800233ca  sub     rsp, 50h
0x1800233ce  mov     r13, r9
0x1800233d1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800233d8  lea     rax, WPP_GLOBAL_Control
0x1800233df  cmp     rcx, rax
0x1800233e2  jz      short loc_180023405
0x1800233e4  test    byte ptr [rcx+1Ch], 2
0x1800233e8  jz      short loc_180023405
0x1800233ea  cmp     byte ptr [rcx+19h], 2
0x1800233ee  jb      short loc_180023405
0x1800233f0  mov     rcx, [rcx+10h]
0x1800233f4  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x1800233fb  mov     edx, 49h ; 'I'
0x180023400  call    WPP_SF_
0x180023405  mov     rax, cs:ConfigurationInfoSd
0x18002340c  lea     rcx, WsConfigInfoMapping
0x180023413  mov     [rsp+88h+var_58], rcx
0x180023418  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x18002341f  mov     dword ptr [rsp+88h+var_60], 2
0x180023427  mov     [rsp+88h+var_68], rax
0x18002342c  call    NetpAccessCheckAndAuditEx
0x180023431  xor     ebx, ebx
0x180023433  test    eax, eax
0x180023435  jz      short loc_18002343F
0x180023437  lea     eax, [rbx+5]
0x18002343a  jmp     loc_180023910
0x18002343f  mov     dl, 1; Wait
0x180023441  lea     rcx, stru_180051B90; Resource
0x180023448  call    cs:__imp_RtlAcquireResourceExclusive
0x18002344f  nop     dword ptr [rax+rax+00h]
0x180023454  mov     r14, [rsp+88h+arg_38]
0x18002345c  cmp     [rsp+88h+arg_28], ebx
0x180023463  jz      short loc_180023472
0x180023465  mov     rdi, rbx
0x180023468  mov     ebx, 307h
0x18002346d  jmp     loc_18002385B
0x180023472  mov     rax, cs:hMem
0x180023479  mov     rcx, [rax+8]
0x18002347d  mov     eax, [rcx+4]
0x180023480  mov     ecx, 40h ; '@'; uFlags
0x180023485  lea     rdx, [rax+rax*2]
0x180023489  shl     rdx, 5; uBytes
0x18002348d  call    cs:__imp_LocalAlloc
0x180023494  nop     dword ptr [rax+rax+00h]
0x180023499  xor     r9d, r9d
0x18002349c  mov     rdi, rax
0x18002349f  test    rax, rax
0x1800234a2  jnz     short loc_1800234AE
0x1800234a4  mov     ebx, 8
0x1800234a9  jmp     loc_18002385B
0x1800234ae  mov     rax, cs:hMem
0x1800234b5  mov     ebp, r9d
0x1800234b8  mov     r12, [rsp+88h+arg_20]
0x1800234c0  mov     r15d, r9d
0x1800234c3  mov     rcx, [rax+8]
0x1800234c7  mov     rsi, [rcx+8]
0x1800234cb  mov     [r14], rdi
0x1800234ce  mov     r10, cs:WPP_GLOBAL_Control
0x1800234d5  mov     rax, cs:hMem
0x1800234dc  mov     rcx, [rax+8]
0x1800234e0  cmp     r15d, [rcx+4]
0x1800234e4  jnb     loc_180023851
0x1800234ea  lea     r11, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800234f1  cmp     r10, r11
0x1800234f4  jz      short loc_18002353D
0x1800234f6  test    byte ptr [r10+1Ch], 2
0x1800234fb  jz      short loc_18002353D
0x1800234fd  cmp     byte ptr [r10+19h], 2
0x180023502  jb      short loc_18002353D
0x180023504  mov     rax, [rsp+88h+arg_10]
0x18002350c  mov     r9, [rsp+88h+arg_8]
0x180023514  mov     rcx, [r10+10h]; LoggerHandle
0x180023518  mov     [rsp+88h+var_58], r12; __int64
0x18002351d  mov     [rsp+88h+var_60], r13; __int64
0x180023522  mov     [rsp+88h+var_68], rax; __int64
0x180023527  call    WPP_SF_SSSS
0x18002352c  mov     r10, cs:WPP_GLOBAL_Control
0x180023533  lea     r11, WPP_GLOBAL_Control
0x18002353a  xor     r9d, r9d
0x18002353d  mov     rax, [rsp+88h+arg_8]
0x180023545  test    rax, rax
0x180023548  jz      short loc_18002356C
0x18002354a  mov     r8, [rsi]
0x18002354d  sub     r8, rax
0x180023550  movzx   edx, word ptr [rax]
0x180023553  movzx   ecx, word ptr [rax+r8]
0x180023558  sub     edx, ecx
0x18002355a  jnz     short loc_180023564
0x18002355c  add     rax, 2
0x180023560  test    ecx, ecx
0x180023562  jnz     short loc_180023550
0x180023564  test    edx, edx
0x180023566  jnz     loc_180023845
0x18002356c  mov     rax, [rsp+88h+arg_10]
0x180023574  test    rax, rax
0x180023577  jz      short loc_18002359C
0x180023579  mov     r8, [rsi+8]
0x18002357d  sub     r8, rax
0x180023580  movzx   edx, word ptr [rax]
0x180023583  movzx   ecx, word ptr [rax+r8]
0x180023588  sub     edx, ecx
0x18002358a  jnz     short loc_180023594
0x18002358c  add     rax, 2
0x180023590  test    ecx, ecx
0x180023592  jnz     short loc_180023580
0x180023594  test    edx, edx
0x180023596  jnz     loc_180023845
0x18002359c  test    r13, r13
0x18002359f  jz      short loc_1800235C7
0x1800235a1  mov     r8, [rsi+18h]
0x1800235a5  mov     rax, r13
0x1800235a8  sub     r8, r13
0x1800235ab  movzx   edx, word ptr [rax]
0x1800235ae  movzx   ecx, word ptr [rax+r8]
0x1800235b3  sub     edx, ecx
0x1800235b5  jnz     short loc_1800235BF
0x1800235b7  add     rax, 2
0x1800235bb  test    ecx, ecx
0x1800235bd  jnz     short loc_1800235AB
0x1800235bf  test    edx, edx
0x1800235c1  jnz     loc_180023845
0x1800235c7  test    r12, r12
0x1800235ca  jz      short loc_1800235F2
0x1800235cc  mov     r8, [rsi+20h]
0x1800235d0  mov     rax, r12
0x1800235d3  sub     r8, r12
0x1800235d6  movzx   edx, word ptr [rax]
0x1800235d9  movzx   ecx, word ptr [rax+r8]
0x1800235de  sub     edx, ecx
0x1800235e0  jnz     short loc_1800235EA
0x1800235e2  add     rax, 2
0x1800235e6  test    ecx, ecx
0x1800235e8  jnz     short loc_1800235D6
0x1800235ea  test    edx, edx
0x1800235ec  jnz     loc_180023845
0x1800235f2  cmp     r10, r11; __annotation("TMF:",
0x1800235f5  jz      short loc_18002361D
0x1800235f7  test    byte ptr [r10+1Ch], 2
0x1800235fc  jz      short loc_18002361D
0x1800235fe  cmp     byte ptr [r10+19h], 2
0x180023603  jb      short loc_18002361D
0x180023605  mov     rcx, [r10+10h]
0x180023609  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180023610  mov     edx, 4Bh ; 'K'
0x180023615  call    WPP_SF_
0x18002361a  xor     r9d, r9d
0x18002361d  mov     rcx, [rsi]
0x180023620  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023624  inc     rax
0x180023627  cmp     [rcx+rax*2], r9w
0x18002362c  jnz     short loc_180023624
0x18002362e  lea     rbx, ds:2[rax*2]
0x180023636  mov     ecx, 40h ; '@'; uFlags
0x18002363b  mov     rdx, rbx; uBytes
0x18002363e  call    cs:__imp_LocalAlloc
0x180023645  nop     dword ptr [rax+rax+00h]
0x18002364a  mov     [rdi], rax
0x18002364d  test    rax, rax
0x180023650  jz      loc_1800234A4
0x180023656  mov     rdx, [rsi]; Src
0x180023659  mov     r8, rbx; Size
0x18002365c  mov     rcx, rax; void *
0x18002365f  call    memcpy_0
0x180023664  mov     rcx, [rsi+8]
0x180023668  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002366c  xor     edx, edx
0x18002366e  inc     rax
0x180023671  cmp     [rcx+rax*2], dx
0x180023675  jnz     short loc_18002366E
0x180023677  lea     rbx, ds:2[rax*2]
0x18002367f  mov     ecx, 40h ; '@'; uFlags
0x180023684  mov     rdx, rbx; uBytes
0x180023687  call    cs:__imp_LocalAlloc
0x18002368e  nop     dword ptr [rax+rax+00h]
0x180023693  mov     [rdi+8], rax
0x180023697  test    rax, rax
0x18002369a  jz      loc_1800234A4
0x1800236a0  mov     rdx, [rsi+8]; Src
0x1800236a4  mov     r8, rbx; Size
0x1800236a7  mov     rcx, rax; void *
0x1800236aa  call    memcpy_0
0x1800236af  mov     rcx, [rsi+18h]
0x1800236b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800236b7  xor     edx, edx
0x1800236b9  inc     rax
0x1800236bc  cmp     [rcx+rax*2], dx
0x1800236c0  jnz     short loc_1800236B9
0x1800236c2  lea     rbx, ds:2[rax*2]
0x1800236ca  mov     ecx, 40h ; '@'; uFlags
0x1800236cf  mov     rdx, rbx; uBytes
0x1800236d2  call    cs:__imp_LocalAlloc
0x1800236d9  nop     dword ptr [rax+rax+00h]
0x1800236de  mov     [rdi+18h], rax
0x1800236e2  test    rax, rax
0x1800236e5  jz      loc_1800234A4
0x1800236eb  mov     rdx, [rsi+18h]; Src
0x1800236ef  mov     r8, rbx; Size
0x1800236f2  mov     rcx, rax; void *
0x1800236f5  call    memcpy_0
0x1800236fa  mov     rcx, [rsi+40h]
0x1800236fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023702  xor     edx, edx
0x180023704  inc     rax
0x180023707  cmp     [rcx+rax*2], dx
0x18002370b  jnz     short loc_180023704
0x18002370d  lea     rbx, ds:2[rax*2]
0x180023715  mov     ecx, 40h ; '@'; uFlags
0x18002371a  mov     rdx, rbx; uBytes
0x18002371d  call    cs:__imp_LocalAlloc
0x180023724  nop     dword ptr [rax+rax+00h]
0x180023729  mov     [rdi+40h], rax
0x18002372d  test    rax, rax
0x180023730  jz      loc_1800234A4
0x180023736  mov     rdx, [rsi+40h]; Src
0x18002373a  mov     r8, rbx; Size
0x18002373d  mov     rcx, rax; void *
0x180023740  call    memcpy_0
0x180023745  mov     rcx, [rsi+20h]
0x180023749  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002374d  xor     edx, edx
0x18002374f  inc     rax
0x180023752  cmp     [rcx+rax*2], dx
0x180023756  jnz     short loc_18002374F
0x180023758  lea     rbx, ds:2[rax*2]
0x180023760  mov     ecx, 40h ; '@'; uFlags
0x180023765  mov     rdx, rbx; uBytes
0x180023768  call    cs:__imp_LocalAlloc
0x18002376f  nop     dword ptr [rax+rax+00h]
0x180023774  mov     [rdi+20h], rax
0x180023778  test    rax, rax
0x18002377b  jz      loc_1800234A4
0x180023781  mov     rdx, [rsi+20h]; Src
0x180023785  mov     r8, rbx; Size
0x180023788  mov     rcx, rax; void *
0x18002378b  call    memcpy_0
0x180023790  mov     eax, [rsi+50h]
0x180023793  lea     rcx, aNetpwkstarclie_2; "NetpWkstarClientCertificateMappingGet"
0x18002379a  mov     [rdi+50h], eax
0x18002379d  mov     edx, 9F5h
0x1800237a2  mov     eax, [rsi+54h]
0x1800237a5  mov     [rdi+54h], eax
0x1800237a8  mov     eax, [rsi+58h]
0x1800237ab  mov     [rdi+58h], eax
0x1800237ae  call    WsImpersonateClient2
0x1800237b3  mov     ebx, eax
0x1800237b5  test    eax, eax
0x1800237b7  jnz     loc_18002385B
0x1800237bd  mov     rcx, rdi
0x1800237c0  call    PopulateRenewalChain
0x1800237c5  mov     edx, 9FAh
0x1800237ca  lea     rcx, aNetpwkstarclie_2; "NetpWkstarClientCertificateMappingGet"
0x1800237d1  call    WsRevertToSelf2
0x1800237d6  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800237dd  lea     rax, WPP_GLOBAL_Control
0x1800237e4  cmp     r10, rax
0x1800237e7  jz      short loc_18002383C
0x1800237e9  test    byte ptr [r10+1Ch], 2
0x1800237ee  jz      short loc_18002383C
0x1800237f0  cmp     byte ptr [r10+19h], 2
0x1800237f5  jb      short loc_18002383C
0x1800237f7  mov     eax, [rdi+54h]
0x1800237fa  mov     r9, [rdi]
0x1800237fd  mov     rcx, [r10+10h]; LoggerHandle
0x180023801  mov     dword ptr [rsp+88h+var_40], eax; char
0x180023805  mov     eax, [rdi+50h]
0x180023808  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002380c  mov     rax, [rdi+40h]
0x180023810  mov     [rsp+88h+var_50], rax; __int64
0x180023815  mov     rax, [rdi+20h]
0x180023819  mov     [rsp+88h+var_58], rax; __int64
0x18002381e  mov     rax, [rdi+18h]
0x180023822  mov     [rsp+88h+var_60], rax; __int64
0x180023827  mov     rax, [rdi+8]
0x18002382b  mov     [rsp+88h+var_68], rax; __int64
0x180023830  call    WPP_SF_SSSSSdd
0x180023835  mov     r10, cs:WPP_GLOBAL_Control
0x18002383c  inc     ebp
0x18002383e  add     rdi, 60h ; '`'
0x180023842  xor     r9d, r9d
0x180023845  add     rsi, 60h ; '`'
0x180023849  inc     r15d
0x18002384c  jmp     loc_1800234D5
0x180023851  mov     rax, [rsp+88h+arg_30]
0x180023859  mov     [rax], ebp
0x18002385b  lea     rcx, stru_180051B90; Resource
0x180023862  call    cs:__imp_RtlReleaseResource
0x180023869  nop     dword ptr [rax+rax+00h]
0x18002386e  test    ebx, ebx
0x180023870  jz      loc_18002390E
0x180023876  test    rdi, rdi
  ... truncated ...
```
