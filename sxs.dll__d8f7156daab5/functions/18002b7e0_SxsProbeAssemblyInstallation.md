# SxsProbeAssemblyInstallation

- ea: `0x18002b7e0`
- end: `0x18002bc5c`
- name: `SxsProbeAssemblyInstallation`
- size: `1148`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18005c168`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180011910`
- `0x180017654`
- `0x18001c270`
- `0x180023ee0`
- `0x18002b580`
- `0x18002b6ac`
- `0x18002b7e0`
- `0x18002bc64`
- `0x18002cc78`
- `0x18002d3dc`
- `0x18005a884`
- `0x18005d2b0`
- `0x180062db0`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b92e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b970`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b9b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b9d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b9f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ba23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ba6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bad6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bb1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bb82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bbe0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b92e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b970`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b9b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b9d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b9f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ba23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ba6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bad6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bb1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bb82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bbe0`

## pseudocode

```c
__int64 __fastcall SxsProbeAssemblyInstallation(int a1, struct _ASSEMBLY_IDENTITY *a2, int *a3)
{
  const char *v6; // rcx
  char **v7; // rcx
  unsigned int v8; // edx
  unsigned int v9; // ecx
  int v10; // edi
  int v11; // eax
  unsigned int v12; // ebx
  struct _ASSEMBLY_IDENTITY *v14; // [rsp+20h] [rbp-E0h]
  struct _ASSEMBLY_IDENTITY *v15; // [rsp+20h] [rbp-E0h]
  void *v16; // [rsp+28h] [rbp-D8h]
  void *v17; // [rsp+28h] [rbp-D8h]
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-BCh] BYREF
  struct _ASSEMBLY_IDENTITY *v20; // [rsp+48h] [rbp-B8h] BYREF
  char v21; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h]
  __int64 *v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  int v27; // [rsp+80h] [rbp-80h]
  unsigned int *v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+90h] [rbp-70h] BYREF
  __int128 v30; // [rsp+98h] [rbp-68h] BYREF
  __int64 v31; // [rsp+A8h] [rbp-58h]
  void **v32; // [rsp+B0h] [rbp-50h] BYREF
  int v33; // [rsp+B8h] [rbp-48h]
  int v34[2]; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  int v36[2]; // [rsp+D0h] [rbp-30h]
  __int16 v37; // [rsp+D8h] [rbp-28h]
  __int64 v38; // [rsp+1E0h] [rbp+E0h] BYREF
  int v39; // [rsp+1E8h] [rbp+E8h]
  LPCWSTR lpFileName; // [rsp+1F0h] [rbp+F0h]
  __int64 v41; // [rsp+1F8h] [rbp+F8h]
  __int64 v42; // [rsp+200h] [rbp+100h]
  __int16 v43; // [rsp+208h] [rbp+108h]
  __int64 v44; // [rsp+310h] [rbp+210h] BYREF
  int v45; // [rsp+318h] [rbp+218h]
  LPCWSTR v46; // [rsp+320h] [rbp+220h]
  __int64 v47; // [rsp+328h] [rbp+228h]
  __int64 v48; // [rsp+330h] [rbp+230h]
  __int16 v49; // [rsp+338h] [rbp+238h]

  v26 = 544438355;
  v29 = 0;
  v25 = &qword_18006E0C8;
  v24 = 0;
  v27 = 23;
  v23 = 1;
  v28 = (unsigned int *)&v29;
  CFrame::BaseEnter((CFrame *)&v23);
  v45 = 0;
  v44 = (__int64)&CGenericStringBuffer<128,CUnicodeCharTraits>::`vftable';
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  CGenericBaseStringBuffer<CUnicodeCharTraits>::InitializeInlineBuffer(&v44);
  v33 = 0;
  *(_QWORD *)v34 = 0;
  v35 = 0;
  *(_QWORD *)v36 = 0;
  v32 = &CGenericStringBuffer<128,CUnicodeCharTraits>::`vftable';
  v37 = 0;
  CGenericBaseStringBuffer<CUnicodeCharTraits>::InitializeInlineBuffer(&v32);
  v39 = 0;
  lpFileName = 0;
  v41 = 0;
  v42 = 0;
  v38 = (__int64)&CGenericStringBuffer<128,CUnicodeCharTraits>::`vftable';
  v43 = 0;
  CGenericBaseStringBuffer<CUnicodeCharTraits>::InitializeInlineBuffer(&v38);
  v20 = 0;
  v21 = 0;
  LODWORD(v22) = 0;
  v19 = 0;
  v18 = 0;
  if ( a3 )
    *a3 = 0;
  if ( (a1 & 0xFFFFFFFE) == 0 )
  {
    if ( !a2 )
    {
      v27 = 35;
      goto LABEL_5;
    }
    if ( !a3 )
    {
      v27 = 36;
      goto LABEL_5;
    }
    if ( (a1 & 1) != 0 )
    {
      v20 = a2;
    }
    else
    {
      SetLastError(0);
      v21 = 1;
      if ( !(unsigned int)SxspCreateAssemblyIdentityFromTextualString(a2, &v20) )
      {
        v7 = off_180076980;
        goto LABEL_14;
      }
      a2 = v20;
    }
    SetLastError(0);
    if ( (unsigned int)SxspGetAssemblyRootDirectory(&v32) )
    {
      SetLastError(0);
      if ( SxspValidateIdentity(v9, v8, a2) )
      {
        SetLastError(0);
        if ( (unsigned int)SxspDetermineAssemblyType(a2, (int *)&v22) )
        {
          SetLastError(0);
          if ( (unsigned int)SxspGetInstalledPath(8, 1u, *(__int64 *)v34, *(__int64 *)v36, a2, 0, (__int64)&v38) )
          {
            SetLastError(0);
            LODWORD(v16) = 3;
            v10 = 2;
            LODWORD(v14) = 2;
            if ( (unsigned int)SxspGetFileAttributesW(lpFileName, &v19, &v18, 2u, v14, v16) )
            {
              if ( v18 )
              {
                v11 = 1;
              }
              else
              {
                if ( (_DWORD)v22 )
                  goto LABEL_29;
                SetLastError(0);
                if ( !(unsigned int)SxspGetInstalledPath(8, 2u, *(__int64 *)v34, *(__int64 *)v36, a2, 0, (__int64)&v44) )
                {
                  v7 = off_1800768C0;
                  goto LABEL_14;
                }
                SetLastError(0);
                LODWORD(v17) = 3;
                LODWORD(v15) = 2;
                if ( !(unsigned int)SxspGetFileAttributesW(v46, &v19, &v18, 2u, v15, v17) )
                {
                  v7 = off_1800768A0;
                  goto LABEL_14;
                }
                if ( !v18 && (v19 & 0x10) != 0 )
                {
LABEL_29:
                  v11 = 6;
                }
                else
                {
                  v22 = 0;
                  v30 = 0;
                  v31 = 0;
                  SetLastError(0);
                  if ( !(unsigned int)SxsQueryManifestInformation(0, (unsigned __int16 *)lpFileName, 0x18u, &v30, &v22) )
                  {
                    v7 = off_180076880;
                    goto LABEL_14;
                  }
                  if ( !(_DWORD)v31 )
                    v10 = 6;
                  v11 = v10;
                }
              }
              *a3 = v11;
              SetLastError(0);
              *v28 = 1;
              goto LABEL_42;
            }
            v7 = off_1800768E0;
          }
          else
          {
            v7 = off_180076900;
          }
        }
        else
        {
          v7 = off_180076920;
        }
      }
      else
      {
        v7 = off_180076940;
      }
    }
    else
    {
      v7 = off_180076960;
    }
LABEL_14:
    *v28 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v7);
    goto LABEL_42;
  }
  v27 = 34;
LABEL_5:
  FusionpTraceParameterCheck(v6);
  SetLastError(0x57u);
  *v28 = 0;
LABEL_42:
  v12 = *v28;
  CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>::~CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>(&v20);
  CGenericStringBuffer<128,CUnicodeCharTraits>::~CGenericStringBuffer<128,CUnicodeCharTraits>(&v38);
  CGenericStringBuffer<128,CUnicodeCharTraits>::~CGenericStringBuffer<128,CUnicodeCharTraits>(&v32);
  CGenericStringBuffer<128,CUnicodeCharTraits>::~CGenericStringBuffer<128,CUnicodeCharTraits>(&v44);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v23);
  return v12;
}

```

## disassembly

```asm
0x18002b7e0  mov     [rsp-8+arg_0], rbx
0x18002b7e5  mov     [rsp-8+arg_18], rsi
0x18002b7ea  push    rbp
0x18002b7eb  push    rdi
0x18002b7ec  push    r12
0x18002b7ee  push    r14
0x18002b7f0  push    r15
0x18002b7f2  lea     rbp, [rsp-350h]
0x18002b7fa  sub     rsp, 450h
0x18002b801  mov     rax, cs:__security_cookie
0x18002b808  xor     rax, rsp
0x18002b80b  mov     [rbp+370h+var_30], rax
0x18002b812  xor     r15d, r15d
0x18002b815  mov     [rsp+470h+var_3F8], 20737853h
0x18002b81e  lea     rax, qword_18006E0C8
0x18002b825  mov     [rbp+370h+var_3E0], r15d
0x18002b829  mov     [rsp+470h+var_400], rax
0x18002b82e  mov     edi, ecx
0x18002b830  lea     rax, [rbp+370h+var_3E0]
0x18002b834  mov     [rsp+470h+var_408], r15
0x18002b839  lea     r12d, [r15+1]
0x18002b83d  mov     [rbp+370h+var_3F0], 17h
0x18002b844  lea     rcx, [rsp+470h+var_410]; this
0x18002b849  mov     [rsp+470h+var_410], r12d
0x18002b84e  mov     rsi, r8
0x18002b851  mov     [rbp+370h+var_3E8], rax
0x18002b855  mov     rbx, rdx
0x18002b858  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002b85d  lea     r14, ??_7?$CGenericStringBuffer@$0IA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<128,CUnicodeCharTraits>::`vftable'
0x18002b864  mov     [rbp+370h+var_158], r15d
0x18002b86b  lea     rcx, [rbp+370h+var_160]
0x18002b872  mov     [rbp+370h+var_160], r14
0x18002b879  mov     [rbp+370h+var_150], r15
0x18002b880  mov     [rbp+370h+var_148], r15
0x18002b887  mov     [rbp+370h+var_140], r15
0x18002b88e  mov     [rbp+370h+var_138], r15w
0x18002b896  call    ?InitializeInlineBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@IEAAXXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::InitializeInlineBuffer(void)
0x18002b89b  lea     rcx, [rbp+370h+var_3C0]
0x18002b89f  mov     [rbp+370h+var_3B8], r15d
0x18002b8a3  mov     qword ptr [rbp+370h+var_3B0], r15
0x18002b8a7  mov     [rbp+370h+var_3A8], r15
0x18002b8ab  mov     qword ptr [rbp+370h+var_3A0], r15
0x18002b8af  mov     [rbp+370h+var_3C0], r14
0x18002b8b3  mov     [rbp+370h+var_398], r15w
0x18002b8b8  call    ?InitializeInlineBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@IEAAXXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::InitializeInlineBuffer(void)
0x18002b8bd  lea     rcx, [rbp+370h+var_290]
0x18002b8c4  mov     [rbp+370h+var_288], r15d
0x18002b8cb  mov     [rbp+370h+lpFileName], r15
0x18002b8d2  mov     [rbp+370h+var_278], r15
0x18002b8d9  mov     [rbp+370h+var_270], r15
0x18002b8e0  mov     [rbp+370h+var_290], r14
0x18002b8e7  mov     [rbp+370h+var_268], r15w
0x18002b8ef  call    ?InitializeInlineBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@IEAAXXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::InitializeInlineBuffer(void)
0x18002b8f4  mov     [rsp+470h+var_428], r15
0x18002b8f9  mov     [rsp+470h+var_420], r15b
0x18002b8fe  mov     dword ptr [rsp+470h+var_418], r15d
0x18002b903  mov     [rsp+470h+var_42C], r15d
0x18002b908  mov     [rsp+470h+var_430], r15d
0x18002b90d  test    rsi, rsi
0x18002b910  jz      short loc_18002B915
0x18002b912  mov     [rsi], r15d
0x18002b915  test    edi, 0FFFFFFFEh
0x18002b91b  jz      short loc_18002B946
0x18002b91d  mov     [rbp+370h+var_3F0], 22h ; '"'
0x18002b924  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18002b929  mov     ecx, 57h ; 'W'; dwErrCode
0x18002b92e  call    cs:__imp_SetLastError
0x18002b935  nop     dword ptr [rax+rax+00h]
0x18002b93a  mov     rax, [rbp+370h+var_3E8]
0x18002b93e  mov     [rax], r15d
0x18002b941  jmp     loc_18002BBF3
0x18002b946  test    rbx, rbx
0x18002b949  jnz     short loc_18002B954
0x18002b94b  mov     [rbp+370h+var_3F0], 23h ; '#'
0x18002b952  jmp     short loc_18002B924
0x18002b954  test    rsi, rsi
0x18002b957  jnz     short loc_18002B962
0x18002b959  mov     [rbp+370h+var_3F0], 24h ; '$'
0x18002b960  jmp     short loc_18002B924
0x18002b962  test    r12b, dil
0x18002b965  jz      short loc_18002B96E
0x18002b967  mov     [rsp+470h+var_428], rbx
0x18002b96c  jmp     short loc_18002B9AF
0x18002b96e  xor     ecx, ecx; dwErrCode
0x18002b970  call    cs:__imp_SetLastError
0x18002b977  nop     dword ptr [rax+rax+00h]
0x18002b97c  lea     rdx, [rsp+470h+var_428]
0x18002b981  mov     [rsp+470h+var_420], r12b
0x18002b986  mov     rcx, rbx
0x18002b989  call    SxspCreateAssemblyIdentityFromTextualString
0x18002b98e  test    eax, eax
0x18002b990  jnz     short loc_18002B9AA
0x18002b992  lea     rcx, off_180076980; struct _CALL_SITE_INFO *
0x18002b999  mov     rax, [rbp+370h+var_3E8]
0x18002b99d  mov     [rax], r15d
0x18002b9a0  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002b9a5  jmp     loc_18002BBF3
0x18002b9aa  mov     rbx, [rsp+470h+var_428]
0x18002b9af  xor     ecx, ecx; dwErrCode
0x18002b9b1  call    cs:__imp_SetLastError
0x18002b9b8  nop     dword ptr [rax+rax+00h]
0x18002b9bd  lea     rcx, [rbp+370h+var_3C0]
0x18002b9c1  call    ?SxspGetAssemblyRootDirectory@@YAHAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspGetAssemblyRootDirectory(CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18002b9c6  test    eax, eax
0x18002b9c8  jnz     short loc_18002B9D3
0x18002b9ca  lea     rcx, off_180076960; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18002b9d1  jmp     short loc_18002B999
0x18002b9d3  xor     ecx, ecx; dwErrCode
0x18002b9d5  call    cs:__imp_SetLastError
0x18002b9dc  nop     dword ptr [rax+rax+00h]
0x18002b9e1  mov     r8, rbx; struct _ASSEMBLY_IDENTITY *
0x18002b9e4  call    ?SxspValidateIdentity@@YAHKKPEBU_ASSEMBLY_IDENTITY@@@Z; SxspValidateIdentity(ulong,ulong,_ASSEMBLY_IDENTITY const *)
0x18002b9e9  test    eax, eax
0x18002b9eb  jnz     short loc_18002B9F6
0x18002b9ed  lea     rcx, off_180076940; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18002b9f4  jmp     short loc_18002B999
0x18002b9f6  xor     ecx, ecx; dwErrCode
0x18002b9f8  call    cs:__imp_SetLastError
0x18002b9ff  nop     dword ptr [rax+rax+00h]
0x18002ba04  lea     rdx, [rsp+470h+var_418]; int *
0x18002ba09  mov     rcx, rbx; struct _ASSEMBLY_IDENTITY *
0x18002ba0c  call    ?SxspDetermineAssemblyType@@YAHPEBU_ASSEMBLY_IDENTITY@@AEAH@Z; SxspDetermineAssemblyType(_ASSEMBLY_IDENTITY const *,int &)
0x18002ba11  test    eax, eax
0x18002ba13  jnz     short loc_18002BA21
0x18002ba15  lea     rcx, off_180076920; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18002ba1c  jmp     loc_18002B999
0x18002ba21  xor     ecx, ecx; dwErrCode
0x18002ba23  call    cs:__imp_SetLastError
0x18002ba2a  nop     dword ptr [rax+rax+00h]
0x18002ba2f  mov     r9, qword ptr [rbp+370h+var_3A0]; int
0x18002ba33  lea     rax, [rbp+370h+var_290]
0x18002ba3a  mov     r8, qword ptr [rbp+370h+var_3B0]; int
0x18002ba3e  mov     edx, r12d; int
0x18002ba41  mov     [rsp+470h+var_440], rax; __int64
0x18002ba46  mov     ecx, 8; int
0x18002ba4b  mov     [rsp+470h+var_448], r15; __int64
0x18002ba50  mov     [rsp+470h+var_450], rbx; struct _ASSEMBLY_IDENTITY *
0x18002ba55  call    ?SxspGetInstalledPath@@YAHKKPEBG_KPEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspGetInstalledPath(ulong,ulong,ushort const *,unsigned __int64,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18002ba5a  test    eax, eax
0x18002ba5c  jnz     short loc_18002BA6A
0x18002ba5e  lea     rcx, off_180076900; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18002ba65  jmp     loc_18002B999
0x18002ba6a  xor     ecx, ecx; dwErrCode
0x18002ba6c  call    cs:__imp_SetLastError
0x18002ba73  nop     dword ptr [rax+rax+00h]
0x18002ba78  mov     rcx, [rbp+370h+lpFileName]; lpFileName
0x18002ba7f  lea     r8, [rsp+470h+var_430]; unsigned int *
0x18002ba84  mov     r14d, 3
0x18002ba8a  lea     rdx, [rsp+470h+var_42C]; unsigned int *
0x18002ba8f  mov     dword ptr [rsp+470h+var_448], r14d
0x18002ba94  lea     edi, [r14-1]
0x18002ba98  mov     r9d, edi; unsigned __int64
0x18002ba9b  mov     dword ptr [rsp+470h+var_450], edi
0x18002ba9f  call    ?SxspGetFileAttributesW@@YAHPEBGAEAK1_KZZ; SxspGetFileAttributesW(ushort const *,ulong &,ulong &,unsigned __int64,...)
0x18002baa4  test    eax, eax
0x18002baa6  jnz     short loc_18002BAB4
0x18002baa8  lea     rcx, off_1800768E0; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18002baaf  jmp     loc_18002B999
0x18002bab4  cmp     [rsp+470h+var_430], r15d
0x18002bab9  jz      short loc_18002BAC3
0x18002babb  mov     eax, r12d
0x18002babe  jmp     loc_18002BBDC
0x18002bac3  cmp     dword ptr [rsp+470h+var_418], r15d
0x18002bac8  jz      short loc_18002BAD4
0x18002baca  mov     eax, 6
0x18002bacf  jmp     loc_18002BBDC
0x18002bad4  xor     ecx, ecx; dwErrCode
0x18002bad6  call    cs:__imp_SetLastError
0x18002badd  nop     dword ptr [rax+rax+00h]
0x18002bae2  mov     r9, qword ptr [rbp+370h+var_3A0]; int
0x18002bae6  lea     rax, [rbp+370h+var_160]
0x18002baed  mov     r8, qword ptr [rbp+370h+var_3B0]; int
0x18002baf1  mov     edx, edi; int
0x18002baf3  mov     [rsp+470h+var_440], rax; __int64
0x18002baf8  mov     ecx, 8; int
0x18002bafd  mov     [rsp+470h+var_448], r15; __int64
0x18002bb02  mov     [rsp+470h+var_450], rbx; struct _ASSEMBLY_IDENTITY *
0x18002bb07  call    ?SxspGetInstalledPath@@YAHKKPEBG_KPEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspGetInstalledPath(ulong,ulong,ushort const *,unsigned __int64,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18002bb0c  test    eax, eax
0x18002bb0e  jnz     short loc_18002BB1C
0x18002bb10  lea     rcx, off_1800768C0; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18002bb17  jmp     loc_18002B999
0x18002bb1c  xor     ecx, ecx; dwErrCode
0x18002bb1e  call    cs:__imp_SetLastError
0x18002bb25  nop     dword ptr [rax+rax+00h]
0x18002bb2a  mov     rcx, [rbp+370h+var_150]; lpFileName
0x18002bb31  lea     r8, [rsp+470h+var_430]; unsigned int *
0x18002bb36  mov     r9, rdi; unsigned __int64
0x18002bb39  mov     dword ptr [rsp+470h+var_448], r14d
0x18002bb3e  lea     rdx, [rsp+470h+var_42C]; unsigned int *
0x18002bb43  mov     dword ptr [rsp+470h+var_450], edi
0x18002bb47  call    ?SxspGetFileAttributesW@@YAHPEBGAEAK1_KZZ; SxspGetFileAttributesW(ushort const *,ulong &,ulong &,unsigned __int64,...)
0x18002bb4c  test    eax, eax
0x18002bb4e  jnz     short loc_18002BB5C
0x18002bb50  lea     rcx, off_1800768A0; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18002bb57  jmp     loc_18002B999
0x18002bb5c  cmp     [rsp+470h+var_430], r15d
0x18002bb61  jnz     short loc_18002BB6E
0x18002bb63  test    byte ptr [rsp+470h+var_42C], 10h
0x18002bb68  jnz     loc_18002BACA
0x18002bb6e  xorps   xmm0, xmm0
0x18002bb71  mov     [rsp+470h+var_418], r15
0x18002bb76  xor     eax, eax
0x18002bb78  xor     ecx, ecx; dwErrCode
0x18002bb7a  movups  [rbp+370h+var_3D8], xmm0
0x18002bb7e  mov     [rbp+370h+var_3C8], rax
0x18002bb82  call    cs:__imp_SetLastError
0x18002bb89  nop     dword ptr [rax+rax+00h]
0x18002bb8e  mov     rdx, [rbp+370h+lpFileName]; unsigned __int16 *
0x18002bb95  lea     rax, [rsp+470h+var_418]
0x18002bb9a  mov     [rsp+470h+var_440], rax; unsigned __int64 *
0x18002bb9f  mov     r9d, r14d
0x18002bba2  lea     rax, [rbp+370h+var_3D8]
0x18002bba6  mov     r8d, r12d
0x18002bba9  mov     [rsp+470h+var_448], rax; void *
0x18002bbae  xor     ecx, ecx; unsigned int
0x18002bbb0  mov     [rsp+470h+var_450], 18h; unsigned __int64
0x18002bbb9  call    SxsQueryManifestInformation
0x18002bbbe  test    eax, eax
0x18002bbc0  jnz     short loc_18002BBCE
0x18002bbc2  lea     rcx, off_180076880; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18002bbc9  jmp     loc_18002B999
0x18002bbce  cmp     dword ptr [rbp+370h+var_3C8], r15d
0x18002bbd2  mov     eax, 6
0x18002bbd7  cmovz   edi, eax
0x18002bbda  mov     eax, edi
0x18002bbdc  xor     ecx, ecx; dwErrCode
0x18002bbde  mov     [rsi], eax
0x18002bbe0  call    cs:__imp_SetLastError
0x18002bbe7  nop     dword ptr [rax+rax+00h]
0x18002bbec  mov     rax, [rbp+370h+var_3E8]
0x18002bbf0  mov     [rax], r12d
0x18002bbf3  mov     rax, [rbp+370h+var_3E8]
0x18002bbf7  lea     rcx, [rsp+470h+var_428]
0x18002bbfc  mov     ebx, [rax]
0x18002bbfe  call    ??1?$CSmartPtrWithNamedDestructor@U_ASSEMBLY_IDENTITY@@$1?SxsDestroyAssemblyIdentity@@YAXPEAU1@@ZV?$CSmartPtrWithNamedDestructorHelper@U_ASSEMBLY_IDENTITY@@$1?SxsDestroyAssemblyIdentity@@YAXPEAU1@@Z@@@@QEAA@XZ; CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>::~CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>(void)
0x18002bc03  lea     rcx, [rbp+370h+var_290]
0x18002bc0a  call    ??1?$CGenericStringBuffer@$0IA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<128,CUnicodeCharTraits>::~CGenericStringBuffer<128,CUnicodeCharTraits>(void)
0x18002bc0f  lea     rcx, [rbp+370h+var_3C0]
0x18002bc13  call    ??1?$CGenericStringBuffer@$0IA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<128,CUnicodeCharTraits>::~CGenericStringBuffer<128,CUnicodeCharTraits>(void)
0x18002bc18  lea     rcx, [rbp+370h+var_160]
0x18002bc1f  call    ??1?$CGenericStringBuffer@$0IA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<128,CUnicodeCharTraits>::~CGenericStringBuffer<128,CUnicodeCharTraits>(void)
0x18002bc24  lea     rcx, [rsp+470h+var_410]; this
0x18002bc29  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18002bc2e  mov     eax, ebx
0x18002bc30  mov     rcx, [rbp+370h+var_30]
0x18002bc37  xor     rcx, rsp; StackCookie
0x18002bc3a  call    __security_check_cookie
0x18002bc3f  lea     r11, [rsp+470h+var_20]
0x18002bc47  mov     rbx, [r11+30h]
0x18002bc4b  mov     rsi, [r11+48h]
0x18002bc4f  mov     rsp, r11
0x18002bc52  pop     r15
0x18002bc54  pop     r14
0x18002bc56  pop     r12
0x18002bc58  pop     rdi
0x18002bc59  pop     rbp
0x18002bc5a  retn
```
