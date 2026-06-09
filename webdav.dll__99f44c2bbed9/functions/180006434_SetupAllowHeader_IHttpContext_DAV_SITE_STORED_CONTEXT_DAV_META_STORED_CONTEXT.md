# SetupAllowHeader(IHttpContext *,DAV_SITE_STORED_CONTEXT *,DAV_META_STORED_CONTEXT *)

- ea: `0x180006434`
- end: `0x180006939`
- name: `?SetupAllowHeader@@YAJPEAVIHttpContext@@PEAVDAV_SITE_STORED_CONTEXT@@PEAVDAV_META_STORED_CONTEXT@@@Z`
- size: `1285`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct DAV_SITE_STORED_CONTEXT *, struct DAV_META_STORED_CONTEXT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000a050`
- `0x18000e3e8`

## callees

- `0x1800054f8`
- `0x180006310`
- `0x180006434`
- `0x18001b2cc`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000677f`
- `msvcrt!wcsrchr` at `0x18000677f`
- `msvcrt!strrchr` at `0x180006714`
- `msvcrt!strrchr` at `0x180006714`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006558`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000680d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006890`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006558`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000680d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066d5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180006548`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800067f4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180006548`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800067f4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000675e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000675e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006800`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006883`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006800`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006883`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800067e0`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800067e0`

## string_xrefs

- `0x180006619`: `, DELETE`
- `0x180006570`: `, COPY`
- `0x18000663a`: `, MOVE`

## pseudocode

```c
__int64 __fastcall SetupAllowHeader(
        struct IHttpContext *a1,
        struct DAV_SITE_STORED_CONTEXT *a2,
        struct DAV_META_STORED_CONTEXT *a3)
{
  __int64 v3; // rax
  int v7; // edi
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rbx
  struct IHttpResponse *v12; // rax
  __int64 result; // rax
  struct IHttpResponse *v14; // rax
  unsigned int v15; // r9d
  const char **v16; // r8
  const WCHAR *v17; // rax
  DWORD FileAttributesW; // r15d
  int v19; // esi
  unsigned int v20; // edi
  __int64 v21; // rax
  __int64 v22; // rax
  const unsigned __int16 *v23; // rbx
  struct IHttpUser *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  const char *v28; // rcx
  __int64 v29; // rax
  unsigned __int64 v30; // rax
  BOOL v31; // r15d
  char *v32; // rax
  const wchar_t *v33; // rbx
  wchar_t *v34; // rax
  const wchar_t *v35; // rcx
  int v36; // ebx
  DWORD v37; // ebx
  __int64 v38; // rax
  __int64 v39; // rax
  unsigned int v40; // [rsp+20h] [rbp-E0h] BYREF
  int v41; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v42; // [rsp+30h] [rbp-D0h]
  int v43; // [rsp+38h] [rbp-C8h]
  const char *v44; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v45[2]; // [rsp+48h] [rbp-B8h]
  const char *v46; // [rsp+50h] [rbp-B0h]
  int v47; // [rsp+58h] [rbp-A8h]
  _BYTE v48[32]; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR lpFileName; // [rsp+F0h] [rbp-10h]
  int v50; // [rsp+100h] [rbp+0h]

  v3 = *((_QWORD *)a2 + 416);
  v40 = 0;
  v7 = *(_DWORD *)(v3 + 28);
  v8 = *(_QWORD *)a1;
  v43 = v7;
  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v8 + 24))(a1);
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  v11 = *(_QWORD *)(v10 + 56);
  if ( !v11 || *(_BYTE *)v11 != 42 || *(_BYTE *)(v11 + 1) && (*(_BYTE *)(v11 + 1) != 47 || *(_BYTE *)(v11 + 2)) )
  {
    v41 = 0;
    v42 = 0;
    AUTO_IMPERSONATE::Impersonate((AUTO_IMPERSONATE *)&v41, a1);
    v17 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a1 + 168LL))(a1, 0);
    FileAttributesW = GetFileAttributesW(v17);
    if ( v41 )
      RevertToSelf();
    v19 = *(_DWORD *)(v10 + 36);
    if ( FileAttributesW == -1 )
    {
      v20 = 0;
      if ( v19 == 3 && GetLastError() == 2 )
      {
        if ( v11 )
        {
          v30 = -1;
          do
            ++v30;
          while ( *(_BYTE *)(v11 + v30) );
          if ( v30 > 1 )
          {
            v31 = 0;
            v32 = strrchr((const char *)v11, 47);
            if ( v32 && *v32 == 47 )
              v31 = v32[1] == 0;
            v41 = 0;
            v42 = 0;
            AUTO_IMPERSONATE::Impersonate((AUTO_IMPERSONATE *)&v41, a1);
            v33 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a1 + 168LL))(
                                     a1,
                                     0);
            STRU::STRU((STRU *)v48);
            if ( !v33 || v50 )
            {
              v36 = -2147024809;
            }
            else
            {
              v34 = wcsrchr(v33, 0x5Cu);
              if ( !v34 || v34 == v33 || (v35 = v34 - 1, *(v34 - 1) == 92) || *v35 == 58 )
              {
                v36 = -2147024893;
              }
              else
              {
                if ( !v34[1] )
                {
                  --v34;
                  if ( v35 != v33 )
                  {
                    do
                    {
                      if ( *v34 == 92 )
                        break;
                      --v34;
                    }
                    while ( v34 != v33 );
                  }
                }
                v36 = STRU::Copy((STRU *)v48, v33, v34 - v33);
                if ( v36 >= 0 )
                {
                  v37 = GetFileAttributesW(lpFileName);
                  STRU::~STRU((STRU *)v48);
                  if ( v41 )
                    RevertToSelf();
                  if ( v37 != -1 )
                  {
                    if ( v31 )
                    {
                      if ( (v37 & 0x10) != 0 )
                      {
                        v45[0] = 5;
                        v44 = ", MKCOL";
                        v20 = 1;
                      }
                    }
                    else if ( (v37 & 0x10) != 0 )
                    {
                      v45[0] = 5;
                      v44 = ", MKCOL";
                      v20 = 2;
                      v47 = 3;
                      v46 = ", PUT";
                    }
                  }
                  goto LABEL_64;
                }
              }
            }
            STRU::~STRU((STRU *)v48);
            if ( v41 )
              RevertToSelf();
            return (unsigned int)v36;
          }
        }
      }
    }
    else
    {
      if ( v19 != 13 )
      {
        v45[0] = 4;
        v44 = ", COPY";
      }
      v20 = v19 != 13;
      if ( v19 != 14 )
      {
        v21 = 2LL * (v19 != 13);
        ++v20;
        *(_QWORD *)&v45[2 * v21 - 2] = ", PROPFIND";
        v45[2 * v21] = 8;
      }
      v22 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
      v23 = *(const unsigned __int16 **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22) + 88);
      v24 = (struct IHttpUser *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 48LL))(a1);
      if ( DAV_URI_CONFIG::QueryAccessForUri((struct DAV_META_STORED_CONTEXT *)((char *)a3 + 288), v24, v23, &v40) < 0
        || (v40 & 2) == 0 )
      {
        goto LABEL_64;
      }
      if ( v19 == 8 || (v25 = 2LL * v20, ++v20, *(_QWORD *)&v45[2 * v25 - 2] = ", DELETE", v45[2 * v25] = 6, v19 != 12) )
      {
        v26 = 2LL * v20++;
        *(_QWORD *)&v45[2 * v26 - 2] = ", MOVE";
        v45[2 * v26] = 4;
      }
      if ( *((_DWORD *)a2 + 12) && v19 != 15 )
      {
        v27 = 2LL * v20++;
        *(_QWORD *)&v45[2 * v27 - 2] = ", PROPPATCH";
        v45[2 * v27] = 9;
      }
      if ( (FileAttributesW & 0x10) != 0 )
      {
        if ( v19 == 16 )
          goto LABEL_64;
        v28 = ", MKCOL";
        v29 = 2LL * v20;
        v45[4 * v20] = 5;
      }
      else
      {
        if ( v19 == 7 )
          goto LABEL_64;
        v28 = ", PUT";
        v29 = 2LL * v20;
        v45[4 * v20] = 3;
      }
      *(_QWORD *)&v45[2 * v29 - 2] = v28;
      ++v20;
    }
LABEL_64:
    if ( v43 )
    {
      if ( v19 == 17 || (v38 = 2LL * v20, ++v20, *(_QWORD *)&v45[2 * v38 - 2] = ", LOCK", v45[2 * v38] = 4, v19 != 18) )
      {
        v39 = 2LL * v20++;
        *(_QWORD *)&v45[2 * v39 - 2] = ", UNLOCK";
        v45[2 * v39] = 6;
      }
    }
    v14 = (struct IHttpResponse *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
    v15 = v20;
    v16 = &v44;
    return AppendVerbListToHeader(v14, "Allow", v16, v15);
  }
  v12 = (struct IHttpResponse *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
  result = AppendVerbListToHeader(v12, "Allow", (const char **)&g_DavVerbs, 7u);
  if ( (int)result >= 0 && v7 )
  {
    v14 = (struct IHttpResponse *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
    v15 = 2;
    v16 = (const char **)&g_DavLockVerbs;
    return AppendVerbListToHeader(v14, "Allow", v16, v15);
  }
  return result;
}

```

## disassembly

```asm
0x180006434  mov     [rsp-8+arg_8], rbx
0x180006439  push    rbp
0x18000643a  push    rsi
0x18000643b  push    rdi
0x18000643c  push    r12
0x18000643e  push    r13
0x180006440  push    r14
0x180006442  push    r15
0x180006444  lea     rbp, [rsp-10h]
0x180006449  sub     rsp, 110h
0x180006450  mov     rax, cs:__security_cookie
0x180006457  xor     rax, rsp
0x18000645a  mov     [rbp+40h+var_38], rax
0x18000645e  mov     rax, [rdx+0D00h]
0x180006465  xor     r15d, r15d
0x180006468  mov     r12, r8
0x18000646b  mov     [rsp+140h+var_120], r15d
0x180006470  mov     r13, rdx
0x180006473  mov     r14, rcx
0x180006476  mov     edi, [rax+1Ch]
0x180006479  mov     rax, [rcx]
0x18000647c  mov     [rsp+140h+var_108], edi
0x180006480  mov     rax, [rax+18h]
0x180006484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006489  mov     rdx, rax
0x18000648c  mov     rcx, [rax]
0x18000648f  mov     rax, [rcx+8]
0x180006493  mov     rcx, rdx
0x180006496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000649b  mov     rsi, rax
0x18000649e  mov     rbx, [rax+38h]
0x1800064a2  test    rbx, rbx
0x1800064a5  jz      short loc_18000651A
0x1800064a7  cmp     byte ptr [rbx], 2Ah ; '*'
0x1800064aa  jnz     short loc_18000651A
0x1800064ac  cmp     [rbx+1], r15b
0x1800064b0  jz      short loc_1800064BE
0x1800064b2  cmp     byte ptr [rbx+1], 2Fh ; '/'
0x1800064b6  jnz     short loc_18000651A
0x1800064b8  cmp     [rbx+2], r15b
0x1800064bc  jnz     short loc_18000651A
0x1800064be  mov     rax, [r14]
0x1800064c1  mov     rcx, r14
0x1800064c4  mov     rax, [rax+20h]
0x1800064c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064cd  mov     rcx, rax; struct IHttpResponse *
0x1800064d0  lea     r8, ?g_DavVerbs@@3PAUDAV_VERB@@A; struct DAV_VERB *
0x1800064d7  mov     r9d, 7; unsigned int
0x1800064dd  lea     rdx, aAllow; "Allow"
0x1800064e4  call    ?AppendVerbListToHeader@@YAJPEAVIHttpResponse@@PEBDPEAUDAV_VERB@@K@Z; AppendVerbListToHeader(IHttpResponse *,char const *,DAV_VERB *,ulong)
0x1800064e9  test    eax, eax
0x1800064eb  js      loc_180006912
0x1800064f1  test    edi, edi
0x1800064f3  jz      loc_180006912
0x1800064f9  mov     rax, [r14]
0x1800064fc  mov     rcx, r14
0x1800064ff  mov     rax, [rax+20h]
0x180006503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006508  mov     r9d, 2
0x18000650e  lea     r8, ?g_DavLockVerbs@@3PAUDAV_VERB@@A; DAV_VERB near * g_DavLockVerbs
0x180006515  jmp     loc_180006903
0x18000651a  mov     rdx, r14; struct IHttpContext *
0x18000651d  mov     [rsp+140h+var_118], r15d
0x180006522  lea     rcx, [rsp+140h+var_118]; this
0x180006527  mov     [rsp+140h+var_110], r15
0x18000652c  call    ?Impersonate@AUTO_IMPERSONATE@@QEAAJPEAVIHttpContext@@@Z; AUTO_IMPERSONATE::Impersonate(IHttpContext *)
0x180006531  mov     rax, [r14]
0x180006534  xor     edx, edx
0x180006536  mov     rcx, r14
0x180006539  mov     rax, [rax+0A8h]
0x180006540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006545  mov     rcx, rax; lpFileName
0x180006548  call    cs:__imp_GetFileAttributesW
0x18000654e  cmp     [rsp+140h+var_118], 0
0x180006553  mov     r15d, eax
0x180006556  jz      short loc_18000655E
0x180006558  call    cs:__imp_RevertToSelf
0x18000655e  mov     esi, [rsi+24h]
0x180006561  cmp     r15d, 0FFFFFFFFh
0x180006565  jz      loc_1800066C6
0x18000656b  cmp     esi, 0Dh
0x18000656e  jz      short loc_180006584
0x180006570  lea     rax, aCopy; ", COPY"
0x180006577  mov     [rsp+140h+var_F8], 4
0x18000657f  mov     [rsp+140h+var_100], rax
0x180006584  xor     edi, edi
0x180006586  cmp     esi, 0Dh
0x180006589  setnz   dil
0x18000658d  cmp     esi, 0Eh
0x180006590  jz      short loc_1800065AD
0x180006592  mov     eax, edi
0x180006594  lea     rcx, aPropfind; ", PROPFIND"
0x18000659b  add     rax, rax
0x18000659e  inc     edi
0x1800065a0  mov     [rsp+rax*8+140h+var_100], rcx
0x1800065a5  mov     [rsp+rax*8+140h+var_F8], 8
0x1800065ad  mov     rax, [r14]
0x1800065b0  mov     rcx, r14
0x1800065b3  mov     rax, [rax+18h]
0x1800065b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065bc  mov     rdx, rax
0x1800065bf  mov     rcx, [rax]
0x1800065c2  mov     rax, [rcx+8]
0x1800065c6  mov     rcx, rdx
0x1800065c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ce  mov     rcx, r14
0x1800065d1  mov     rbx, [rax+58h]
0x1800065d5  mov     rax, [r14]
0x1800065d8  mov     rax, [rax+30h]
0x1800065dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065e1  lea     rcx, [r12+120h]; this
0x1800065e9  mov     r8, rbx; unsigned __int16 *
0x1800065ec  lea     r9, [rsp+140h+var_120]; unsigned int *
0x1800065f1  mov     rdx, rax; struct IHttpUser *
0x1800065f4  call    ?QueryAccessForUri@DAV_URI_CONFIG@@QEAAJPEAVIHttpUser@@PEBGPEAK@Z; DAV_URI_CONFIG::QueryAccessForUri(IHttpUser *,ushort const *,ulong *)
0x1800065f9  test    eax, eax
0x1800065fb  js      loc_18000689A
0x180006601  test    byte ptr [rsp+140h+var_120], 2
0x180006606  jz      loc_18000689A
0x18000660c  mov     r12d, 1
0x180006612  cmp     esi, 8
0x180006615  jz      short loc_180006638
0x180006617  mov     eax, edi
0x180006619  lea     rcx, aDelete_0; ", DELETE"
0x180006620  add     rax, rax
0x180006623  add     edi, r12d
0x180006626  mov     [rsp+rax*8+140h+var_100], rcx
0x18000662b  mov     [rsp+rax*8+140h+var_F8], 6
0x180006633  cmp     esi, 0Ch
0x180006636  jz      short loc_180006654
0x180006638  mov     eax, edi
0x18000663a  lea     rcx, aMove; ", MOVE"
0x180006641  add     rax, rax
0x180006644  add     edi, r12d
0x180006647  mov     [rsp+rax*8+140h+var_100], rcx
0x18000664c  mov     [rsp+rax*8+140h+var_F8], 4
0x180006654  cmp     dword ptr [r13+30h], 0
0x180006659  jz      short loc_18000667C
0x18000665b  cmp     esi, 0Fh
0x18000665e  jz      short loc_18000667C
0x180006660  mov     eax, edi
0x180006662  lea     rcx, aProppatch_0; ", PROPPATCH"
0x180006669  add     rax, rax
0x18000666c  add     edi, r12d
0x18000666f  mov     [rsp+rax*8+140h+var_100], rcx
0x180006674  mov     [rsp+rax*8+140h+var_F8], 9
0x18000667c  test    r15b, 10h
0x180006680  jz      short loc_18000669D
0x180006682  cmp     esi, 10h
0x180006685  jz      short loc_1800066BE
0x180006687  mov     eax, edi
0x180006689  lea     rcx, aMkcol; ", MKCOL"
0x180006690  add     rax, rax
0x180006693  mov     [rsp+rax*8+140h+var_F8], 5
0x18000669b  jmp     short loc_1800066B6
0x18000669d  cmp     esi, 7
0x1800066a0  jz      short loc_1800066BE
0x1800066a2  mov     eax, edi
0x1800066a4  lea     rcx, aPut_0; ", PUT"
0x1800066ab  add     rax, rax
0x1800066ae  mov     [rsp+rax*8+140h+var_F8], 3
0x1800066b6  mov     [rsp+rax*8+140h+var_100], rcx
0x1800066bb  add     edi, r12d
0x1800066be  xor     r13d, r13d
0x1800066c1  jmp     loc_1800068A3
0x1800066c6  xor     r13d, r13d
0x1800066c9  mov     edi, r13d
0x1800066cc  cmp     esi, 3
0x1800066cf  jnz     loc_18000689D
0x1800066d5  call    cs:__imp_GetLastError
0x1800066db  cmp     eax, 2
0x1800066de  jnz     loc_18000689D
0x1800066e4  test    rbx, rbx
0x1800066e7  jz      loc_18000689D
0x1800066ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800066f1  inc     rax
0x1800066f4  cmp     [rbx+rax], r13b
0x1800066f8  jnz     short loc_1800066F1
0x1800066fa  mov     r12d, 1
0x180006700  cmp     rax, r12
0x180006703  jbe     loc_1800068A3
0x180006709  lea     edx, [r12+2Eh]; Ch
0x18000670e  mov     rcx, rbx; Str
0x180006711  mov     r15d, r13d
0x180006714  call    cs:__imp_strrchr
0x18000671a  test    rax, rax
0x18000671d  jz      short loc_18000672C
0x18000671f  cmp     byte ptr [rax], 2Fh ; '/'
0x180006722  jnz     short loc_18000672C
0x180006724  cmp     [rax+1], r13b
0x180006728  cmovz   r15d, r12d
0x18000672c  mov     rdx, r14; struct IHttpContext *
0x18000672f  mov     [rsp+140h+var_118], r13d
0x180006734  lea     rcx, [rsp+140h+var_118]; this
0x180006739  mov     [rsp+140h+var_110], r13
0x18000673e  call    ?Impersonate@AUTO_IMPERSONATE@@QEAAJPEAVIHttpContext@@@Z; AUTO_IMPERSONATE::Impersonate(IHttpContext *)
0x180006743  mov     rax, [r14]
0x180006746  xor     edx, edx
0x180006748  mov     rcx, r14
0x18000674b  mov     rax, [rax+0A8h]
0x180006752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006757  lea     rcx, [rbp+40h+var_70]
0x18000675b  mov     rbx, rax
0x18000675e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006764  test    rbx, rbx
0x180006767  jz      loc_18000687A
0x18000676d  cmp     [rbp+40h+var_40], r13d
0x180006771  jnz     loc_18000687A
0x180006777  mov     edx, 5Ch ; '\'; Ch
0x18000677c  mov     rcx, rbx; Str
0x18000677f  call    cs:__imp_wcsrchr
0x180006785  test    rax, rax
0x180006788  jz      loc_180006873
0x18000678e  cmp     rax, rbx
0x180006791  jz      loc_180006873
0x180006797  lea     rcx, [rax-2]
0x18000679b  mov     edx, 5Ch ; '\'
0x1800067a0  cmp     [rcx], dx
0x1800067a3  jz      loc_180006873
0x1800067a9  cmp     word ptr [rcx], 3Ah ; ':'
0x1800067ad  jz      loc_180006873
0x1800067b3  cmp     [rax+2], r13w
0x1800067b8  jnz     short loc_1800067D0
0x1800067ba  mov     rax, rcx
0x1800067bd  cmp     rcx, rbx
0x1800067c0  jz      short loc_1800067D0
0x1800067c2  cmp     [rax], dx
0x1800067c5  jz      short loc_1800067D0
0x1800067c7  sub     rax, 2
0x1800067cb  cmp     rax, rbx
0x1800067ce  jnz     short loc_1800067C2
0x1800067d0  sub     rax, rbx
0x1800067d3  lea     rcx, [rbp+40h+var_70]
0x1800067d7  sar     rax, 1
0x1800067da  mov     rdx, rbx
0x1800067dd  mov     r8d, eax
0x1800067e0  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800067e6  mov     ebx, eax
0x1800067e8  test    eax, eax
0x1800067ea  js      loc_18000687F
0x1800067f0  mov     rcx, [rbp+40h+lpFileName]; lpFileName
0x1800067f4  call    cs:__imp_GetFileAttributesW
0x1800067fa  lea     rcx, [rbp+40h+var_70]
0x1800067fe  mov     ebx, eax
0x180006800  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006806  cmp     [rsp+140h+var_118], r13d
0x18000680b  jz      short loc_180006813
0x18000680d  call    cs:__imp_RevertToSelf
0x180006813  cmp     ebx, 0FFFFFFFFh
0x180006816  jz      loc_1800068A3
0x18000681c  test    r15d, r15d
0x18000681f  jz      short loc_18000683F
0x180006821  test    bl, 10h
0x180006824  jz      short loc_1800068A3
0x180006826  lea     rcx, aMkcol; ", MKCOL"
0x18000682d  mov     [rsp+140h+var_F8], 5
0x180006835  mov     [rsp+140h+var_100], rcx
0x18000683a  mov     edi, r12d
0x18000683d  jmp     short loc_1800068A3
0x18000683f  test    bl, 10h
0x180006842  jz      short loc_1800068A3
0x180006844  lea     rcx, aMkcol; ", MKCOL"
0x18000684b  mov     [rsp+140h+var_F8], 5
0x180006853  mov     [rsp+140h+var_100], rcx
0x180006858  mov     edi, 2
0x18000685d  lea     rcx, aPut_0; ", PUT"
0x180006864  mov     [rsp+140h+var_E8], 3
0x18000686c  mov     [rsp+140h+var_F0], rcx
0x180006871  jmp     short loc_1800068A3
0x180006873  mov     ebx, 80070003h
0x180006878  jmp     short loc_18000687F
0x18000687a  mov     ebx, 80070057h
0x18000687f  lea     rcx, [rbp+40h+var_70]
0x180006883  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006889  cmp     [rsp+140h+var_118], r13d
0x18000688e  jz      short loc_180006896
0x180006890  call    cs:__imp_RevertToSelf
0x180006896  mov     eax, ebx
0x180006898  jmp     short loc_180006912
0x18000689a  xor     r13d, r13d
0x18000689d  mov     r12d, 1
0x1800068a3  cmp     [rsp+140h+var_108], r13d
0x1800068a8  jz      short loc_1800068EC
0x1800068aa  cmp     esi, 11h
0x1800068ad  jz      short loc_1800068D0
0x1800068af  mov     eax, edi
0x1800068b1  lea     rcx, aLock; ", LOCK"
0x1800068b8  add     rax, rax
0x1800068bb  add     edi, r12d
0x1800068be  mov     [rsp+rax*8+140h+var_100], rcx
0x1800068c3  mov     [rsp+rax*8+140h+var_F8], 4
0x1800068cb  cmp     esi, 12h
0x1800068ce  jz      short loc_1800068EC
0x1800068d0  mov     eax, edi
0x1800068d2  lea     rcx, aUnlock; ", UNLOCK"
0x1800068d9  add     rax, rax
0x1800068dc  add     edi, r12d
0x1800068df  mov     [rsp+rax*8+140h+var_100], rcx
0x1800068e4  mov     [rsp+rax*8+140h+var_F8], 6
0x1800068ec  mov     rax, [r14]
  ... truncated ...
```
