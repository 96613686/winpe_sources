# WsSetOtherDomains

- ea: `0x18002a06c`
- end: `0x18002a4e6`
- name: `WsSetOtherDomains`
- size: `1146`
- prototype: `int __fastcall(int, BYTE **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180029f90`

## callees

- `0x180002a60`
- `0x1800051c0`
- `0x1800072d8`
- `0x180007400`
- `0x18001e420`
- `0x18001ed46`
- `0x18002a06c`
- `0x18002c1d0`
- `0x18002c364`
- `0x18002ed4c`
- `0x180032fa4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a48e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a48e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a12d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a12d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a213`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a11a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a205`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a11a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a205`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a4a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a4ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a4bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a4a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a4ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a4bb`
- `netutils!NetpwListTraverse` at `0x18002a232`
- `netutils!NetpwListTraverse` at `0x18002a232`
- `netutils!NetpwListCanonicalize` at `0x18002a166`
- `netutils!NetpwListCanonicalize` at `0x18002a166`

## pseudocode

```c
int __fastcall WsSetOtherDomains(int a1, BYTE **a2)
{
  int v4; // ecx
  BYTE *v5; // rax
  unsigned int v6; // ebx
  BYTE *v7; // r15
  int LogonId; // edi
  __int64 v9; // r8
  __int64 v10; // rdx
  _QWORD *v11; // rbx
  unsigned int v12; // eax
  _QWORD *v13; // r14
  unsigned int v14; // r12d
  __int64 v15; // rax
  __int64 v16; // r13
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned int i; // r15d
  __int64 v20; // rdx
  unsigned int v21; // esi
  __int64 v22; // r15
  unsigned int j; // esi
  unsigned int v24; // r15d
  int v25; // eax
  __int64 v26; // rdx
  unsigned int v27; // r12d
  __int64 v28; // r15
  unsigned int v29; // eax
  unsigned int k; // esi
  HKEY *v31; // rsi
  BYTE *lpData; // r15
  DWORD cbData; // eax
  SIZE_T v35; // [rsp+40h] [rbp-C0h]
  unsigned int v36; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v37; // [rsp+54h] [rbp-ACh]
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  BYTE *v39; // [rsp+60h] [rbp-A0h] BYREF
  BYTE *v40; // [rsp+68h] [rbp-98h]
  _DWORD v41[3]; // [rsp+70h] [rbp-90h] BYREF
  struct _LUID DestinationLuid; // [rsp+7Ch] [rbp-84h] BYREF
  int v43; // [rsp+A8h] [rbp-58h]

  memset_0(v41, 0, 0x3F0u);
  hMem = 0;
  v4 = 0;
  if ( a1 != 1101 )
    a2 += 2;
  v36 = 0;
  v5 = *a2;
  v39 = v5;
  if ( v5 )
  {
    if ( WsDgReceiverDeviceHandle )
    {
      while ( *(_WORD *)v5 )
      {
        v5 += 2;
        if ( (*(_WORD *)v5 & 0xFFDF) == 0 )
          v36 = ++v4;
      }
      v6 = 32 * v4 + 2;
      v40 = (BYTE *)LocalAlloc(0x40u, v6);
      v7 = v40;
      if ( v40 )
      {
        if ( (unsigned int)NetpwListCanonicalize(v39, L" ", v40, v6, &v36, 0, 0, 1286) )
        {
          LogonId = 87;
        }
        else
        {
          v41[1] = 6;
          v41[0] = 0;
          v43 = 4;
          LogonId = WsImpersonateAndGetLogonId(&DestinationLuid);
          if ( !LogonId )
          {
            LogonId = WsDeviceControlGetInfo(
                        1,
                        WsDgReceiverDeviceHandle,
                        0x130017u,
                        (__int64)v41,
                        0x7Eu,
                        &hMem,
                        0xFFFFFFFF,
                        0,
                        v35);
            if ( !LogonId )
            {
              v10 = v36;
              v11 = 0;
              v12 = v43;
              v13 = hMem;
              v37 = v43;
              if ( v36 )
              {
                v11 = LocalAlloc(0x40u, 16 * v36);
                if ( v11 )
                {
                  v14 = 0;
                  v39 = v7;
                  while ( 1 )
                  {
                    v15 = NetpwListTraverse(0, &v39, 0);
                    v16 = v15;
                    if ( !v15 )
                    {
                      v10 = v36;
                      v12 = v37;
                      goto LABEL_38;
                    }
                    v11[2 * v14] = v15;
                    v17 = -1;
                    do
                      ++v17;
                    while ( *(_WORD *)(v16 + 2 * v17) );
                    v18 = v37;
                    LODWORD(v11[2 * v14 + 1]) = 2 * v17;
                    for ( i = 0; i < (unsigned int)v18; ++i )
                    {
                      if ( LODWORD(v13[3 * i + 2]) == 4 )
                      {
                        if ( !(unsigned int)WsCompareStringU(
                                              v13[3 * i + 1],
                                              LOWORD(v13[3 * i]) >> 1,
                                              v16,
                                              LODWORD(v11[2 * v14 + 1]) >> 1) )
                          goto LABEL_30;
                        v18 = v37;
                      }
                    }
                    if ( i == (_DWORD)v18 )
                    {
                      v43 = 4;
                      LogonId = WsAddDomainName(v41, v18, v16, LODWORD(v11[2 * v14 + 1]));
                      if ( LogonId )
                      {
                        v21 = 0;
                        if ( v14 )
                        {
                          v22 = 0;
                          do
                          {
                            if ( HIDWORD(v11[2 * v22 + 1]) )
                            {
                              v43 = 4;
                              WsDeleteDomainName(v41, v20, v11[2 * v22], LODWORD(v11[2 * v22 + 1]));
                            }
                            ++v21;
                            ++v22;
                          }
                          while ( v21 < v14 );
                        }
                        goto LABEL_64;
                      }
                      HIDWORD(v11[2 * v14 + 1]) = 1;
                    }
LABEL_30:
                    ++v14;
                  }
                }
                LogonId = GetLastError();
              }
              else
              {
LABEL_38:
                for ( j = 0; j < v12; ++j )
                {
                  if ( LODWORD(v13[3 * j + 2]) == 4 )
                  {
                    v24 = 0;
                    if ( (_DWORD)v10 )
                    {
                      do
                      {
                        v25 = WsCompareStringU(
                                v13[3 * j + 1],
                                LOWORD(v13[3 * j]) >> 1,
                                v11[2 * v24],
                                LODWORD(v11[2 * v24 + 1]) >> 1);
                        v10 = v36;
                        if ( !v25 )
                          break;
                        ++v24;
                      }
                      while ( v24 < v36 );
                    }
                    if ( v24 == (_DWORD)v10 )
                    {
                      v43 = 4;
                      LogonId = WsDeleteDomainName(v41, v10, v13[3 * j + 1], LOWORD(v13[3 * j]));
                      if ( LogonId )
                      {
                        v27 = 0;
                        if ( j )
                        {
                          v28 = 0;
                          do
                          {
                            if ( LODWORD(v13[3 * v28 + 2]) == -1 )
                            {
                              v43 = 4;
                              WsAddDomainName(v41, v26, v13[3 * v28 + 1], LOWORD(v13[3 * v28]));
                            }
                            ++v27;
                            ++v28;
                          }
                          while ( v27 < j );
                        }
                        v29 = v36;
                        for ( k = 0; k < v29; ++k )
                        {
                          if ( HIDWORD(v11[2 * k + 1]) )
                          {
                            v43 = 4;
                            WsDeleteDomainName(v41, v26, v11[2 * k], LODWORD(v11[2 * k + 1]));
                            v29 = v36;
                          }
                        }
                        goto LABEL_63;
                      }
                      LODWORD(v13[3 * j + 2]) = -1;
                      v10 = v36;
                    }
                  }
                  v12 = v37;
                }
                hMem = 0;
                if ( !(unsigned int)NetpOpenConfigDataEx(&hMem, v10, v9, 0) )
                {
                  v31 = (HKEY *)hMem;
                  if ( hMem )
                  {
                    lpData = v40;
                    cbData = NetpTStrArraySize(v40);
                    if ( cbData )
                      RegSetValueExW(*v31, L"OtherDomains", 0, 7u, lpData, cbData);
                  }
                  NetpCloseConfigData(v31);
                }
LABEL_63:
                if ( v11 )
LABEL_64:
                  LocalFree(v11);
              }
              LocalFree(v13);
              v7 = v40;
            }
          }
        }
        LocalFree(v7);
        LODWORD(v5) = LogonId;
      }
      else
      {
        LODWORD(v5) = GetLastError();
      }
    }
    else
    {
      LODWORD(v5) = 50;
    }
  }
  return (int)v5;
}

```

## disassembly

```asm
0x18002a06c  push    rbp
0x18002a06e  push    rbx
0x18002a06f  push    rsi
0x18002a070  push    rdi
0x18002a071  push    r12
0x18002a073  push    r13
0x18002a075  push    r14
0x18002a077  push    r15
0x18002a079  lea     rbp, [rsp-378h]
0x18002a081  sub     rsp, 478h
0x18002a088  mov     rax, cs:__security_cookie
0x18002a08f  xor     rax, rsp
0x18002a092  mov     [rbp+3B0h+var_50], rax
0x18002a099  mov     rdi, rdx
0x18002a09c  mov     ebx, ecx
0x18002a09e  xor     edx, edx; Val
0x18002a0a0  lea     rcx, [rsp+4B0h+var_440]; void *
0x18002a0a5  mov     r8d, 3F0h; Size
0x18002a0ab  call    memset_0
0x18002a0b0  xor     r13d, r13d
0x18002a0b3  lea     rax, [rdi+10h]
0x18002a0b7  cmp     ebx, 44Dh
0x18002a0bd  mov     [rsp+4B0h+hMem], r13
0x18002a0c2  mov     ecx, r13d
0x18002a0c5  cmovnz  rdi, rax
0x18002a0c9  mov     [rsp+4B0h+var_460], ecx
0x18002a0cd  mov     rax, [rdi]
0x18002a0d0  mov     [rsp+4B0h+var_450], rax
0x18002a0d5  test    rax, rax
0x18002a0d8  jz      loc_18002A4C3
0x18002a0de  cmp     cs:WsDgReceiverDeviceHandle, r13
0x18002a0e5  jnz     short loc_18002A105
0x18002a0e7  mov     eax, 32h ; '2'
0x18002a0ec  jmp     loc_18002A4C3
0x18002a0f1  lea     rax, [rax+2]
0x18002a0f5  mov     edx, 0FFDFh
0x18002a0fa  test    [rax], dx
0x18002a0fd  jnz     short loc_18002A105
0x18002a0ff  inc     ecx
0x18002a101  mov     [rsp+4B0h+var_460], ecx
0x18002a105  cmp     [rax], r13w
0x18002a109  jnz     short loc_18002A0F1
0x18002a10b  shl     ecx, 5
0x18002a10e  mov     esi, 40h ; '@'
0x18002a113  lea     ebx, [rcx+2]
0x18002a116  mov     ecx, esi; uFlags
0x18002a118  mov     edx, ebx; uBytes
0x18002a11a  call    cs:__imp_LocalAlloc
0x18002a120  mov     [rsp+4B0h+var_448], rax
0x18002a125  mov     r15, rax
0x18002a128  test    rax, rax
0x18002a12b  jnz     short loc_18002A138
0x18002a12d  call    cs:__imp_GetLastError
0x18002a133  jmp     loc_18002A4C3
0x18002a138  mov     rcx, [rsp+4B0h+var_450]
0x18002a13d  lea     rax, [rsp+4B0h+var_460]
0x18002a142  mov     [rsp+4B0h+var_478], 506h
0x18002a14a  lea     rdx, asc_180040940; " "
0x18002a151  mov     [rsp+4B0h+var_480], r13d
0x18002a156  mov     r9d, ebx
0x18002a159  mov     qword ptr [rsp+4B0h+cbData], r13
0x18002a15e  mov     r8, r15
0x18002a161  mov     [rsp+4B0h+lpData], rax
0x18002a166  call    cs:__imp_NetpwListCanonicalize
0x18002a16c  test    eax, eax
0x18002a16e  jz      short loc_18002A17A
0x18002a170  mov     edi, 57h ; 'W'
0x18002a175  jmp     loc_18002A4B8
0x18002a17a  lea     rcx, [rsp+4B0h+DestinationLuid]; DestinationLuid
0x18002a17f  mov     [rsp+4B0h+var_43C], 6
0x18002a187  mov     [rsp+4B0h+var_440], r13d
0x18002a18c  mov     [rbp+3B0h+var_408], 4
0x18002a193  call    WsImpersonateAndGetLogonId
0x18002a198  mov     edi, eax
0x18002a19a  test    eax, eax
0x18002a19c  jnz     loc_18002A4B8
0x18002a1a2  mov     rdx, cs:WsDgReceiverDeviceHandle
0x18002a1a9  lea     rax, [rsp+4B0h+hMem]
0x18002a1ae  mov     [rsp+4B0h+var_478], r13d
0x18002a1b3  lea     r9, [rsp+4B0h+var_440]
0x18002a1b8  mov     [rsp+4B0h+var_480], 0FFFFFFFFh
0x18002a1c0  lea     ecx, [rdi+1]
0x18002a1c3  mov     qword ptr [rsp+4B0h+cbData], rax
0x18002a1c8  mov     r8d, 130017h
0x18002a1ce  mov     dword ptr [rsp+4B0h+lpData], 7Eh ; '~'
0x18002a1d6  call    WsDeviceControlGetInfo
0x18002a1db  mov     edi, eax
0x18002a1dd  test    eax, eax
0x18002a1df  jnz     loc_18002A4B8
0x18002a1e5  mov     edx, [rsp+4B0h+var_460]
0x18002a1e9  mov     rbx, r13
0x18002a1ec  mov     eax, [rbp+3B0h+var_408]
0x18002a1ef  mov     r14, [rsp+4B0h+hMem]
0x18002a1f4  mov     [rsp+4B0h+var_45C], eax
0x18002a1f8  test    edx, edx
0x18002a1fa  jz      loc_18002A332
0x18002a200  shl     edx, 4; uBytes
0x18002a203  mov     ecx, esi; uFlags
0x18002a205  call    cs:__imp_LocalAlloc
0x18002a20b  mov     rbx, rax
0x18002a20e  test    rax, rax
0x18002a211  jnz     short loc_18002A220
0x18002a213  call    cs:__imp_GetLastError
0x18002a219  mov     edi, eax
0x18002a21b  jmp     loc_18002A4AA
0x18002a220  mov     r12d, r13d
0x18002a223  mov     [rsp+4B0h+var_450], r15
0x18002a228  xor     r8d, r8d
0x18002a22b  lea     rdx, [rsp+4B0h+var_450]
0x18002a230  xor     ecx, ecx
0x18002a232  call    cs:__imp_NetpwListTraverse
0x18002a238  xor     ecx, ecx
0x18002a23a  mov     r13, rax
0x18002a23d  test    rax, rax
0x18002a240  jz      loc_18002A327
0x18002a246  mov     esi, r12d
0x18002a249  add     rsi, rsi
0x18002a24c  mov     [rbx+rsi*8], rax
0x18002a250  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a254  inc     rax
0x18002a257  cmp     [r13+rax*2+0], cx
0x18002a25d  jnz     short loc_18002A254
0x18002a25f  mov     edx, [rsp+4B0h+var_45C]
0x18002a263  add     eax, eax
0x18002a265  mov     [rbx+rsi*8+8], eax
0x18002a269  mov     r15d, ecx
0x18002a26c  test    edx, edx
0x18002a26e  jz      short loc_18002A2AB
0x18002a270  mov     eax, r15d
0x18002a273  lea     rcx, [rax+rax*2]
0x18002a277  cmp     dword ptr [r14+rcx*8+10h], 4
0x18002a27d  jnz     short loc_18002A2A3
0x18002a27f  movzx   edx, word ptr [r14+rcx*8]
0x18002a284  mov     r8, r13
0x18002a287  mov     r9d, [rbx+rsi*8+8]
0x18002a28c  mov     rcx, [r14+rcx*8+8]
0x18002a291  shr     r9d, 1
0x18002a294  shr     edx, 1
0x18002a296  call    WsCompareStringU
0x18002a29b  test    eax, eax
0x18002a29d  jz      short loc_18002A2D9
0x18002a29f  mov     edx, [rsp+4B0h+var_45C]
0x18002a2a3  inc     r15d
0x18002a2a6  cmp     r15d, edx
0x18002a2a9  jb      short loc_18002A270
0x18002a2ab  cmp     r15d, edx
0x18002a2ae  jnz     short loc_18002A2D9
0x18002a2b0  mov     [rbp+3B0h+var_408], 4
0x18002a2b7  lea     rcx, [rsp+4B0h+var_440]
0x18002a2bc  mov     r9d, [rbx+rsi*8+8]
0x18002a2c1  mov     r8, r13
0x18002a2c4  call    WsAddDomainName
0x18002a2c9  xor     ecx, ecx
0x18002a2cb  mov     edi, eax
0x18002a2cd  test    eax, eax
0x18002a2cf  jnz     short loc_18002A2E1
0x18002a2d1  mov     dword ptr [rbx+rsi*8+0Ch], 1
0x18002a2d9  inc     r12d
0x18002a2dc  jmp     loc_18002A228
0x18002a2e1  mov     esi, ecx
0x18002a2e3  test    r12d, r12d
0x18002a2e6  jz      loc_18002A4A1
0x18002a2ec  mov     r15, rcx
0x18002a2ef  mov     r8, r15
0x18002a2f2  add     r8, r8
0x18002a2f5  cmp     [rbx+r8*8+0Ch], ecx
0x18002a2fa  jz      short loc_18002A318
0x18002a2fc  mov     [rbp+3B0h+var_408], 4
0x18002a303  lea     rcx, [rsp+4B0h+var_440]
0x18002a308  mov     r9d, [rbx+r8*8+8]
0x18002a30d  mov     r8, [rbx+r8*8]
0x18002a311  call    WsDeleteDomainName
0x18002a316  xor     ecx, ecx
0x18002a318  inc     esi
0x18002a31a  inc     r15
0x18002a31d  cmp     esi, r12d
0x18002a320  jb      short loc_18002A2EF
0x18002a322  jmp     loc_18002A4A1
0x18002a327  mov     edx, [rsp+4B0h+var_460]
0x18002a32b  xor     r13d, r13d
0x18002a32e  mov     eax, [rsp+4B0h+var_45C]
0x18002a332  mov     esi, r13d
0x18002a335  cmp     esi, eax
0x18002a337  jnb     loc_18002A441
0x18002a33d  mov     eax, esi
0x18002a33f  lea     r12, [rax+rax*2]
0x18002a343  cmp     dword ptr [r14+r12*8+10h], 4
0x18002a349  jnz     short loc_18002A3B8
0x18002a34b  mov     r15d, r13d
0x18002a34e  test    edx, edx
0x18002a350  jz      short loc_18002A385
0x18002a352  movzx   edx, word ptr [r14+r12*8]
0x18002a357  mov     rcx, [r14+r12*8+8]
0x18002a35c  mov     r8d, r15d
0x18002a35f  add     r8, r8
0x18002a362  shr     edx, 1
0x18002a364  mov     r9d, [rbx+r8*8+8]
0x18002a369  mov     r8, [rbx+r8*8]
0x18002a36d  shr     r9d, 1
0x18002a370  call    WsCompareStringU
0x18002a375  mov     edx, [rsp+4B0h+var_460]
0x18002a379  test    eax, eax
0x18002a37b  jz      short loc_18002A385
0x18002a37d  inc     r15d
0x18002a380  cmp     r15d, edx
0x18002a383  jb      short loc_18002A352
0x18002a385  cmp     r15d, edx
0x18002a388  jnz     short loc_18002A3B8
0x18002a38a  mov     [rbp+3B0h+var_408], 4
0x18002a391  lea     rcx, [rsp+4B0h+var_440]
0x18002a396  movzx   r9d, word ptr [r14+r12*8]
0x18002a39b  mov     r8, [r14+r12*8+8]
0x18002a3a0  call    WsDeleteDomainName
0x18002a3a5  mov     edi, eax
0x18002a3a7  test    eax, eax
0x18002a3a9  jnz     short loc_18002A3C3
0x18002a3ab  mov     dword ptr [r14+r12*8+10h], 0FFFFFFFFh
0x18002a3b4  mov     edx, [rsp+4B0h+var_460]
0x18002a3b8  mov     eax, [rsp+4B0h+var_45C]
0x18002a3bc  inc     esi
0x18002a3be  jmp     loc_18002A335
0x18002a3c3  mov     r12d, r13d
0x18002a3c6  test    esi, esi
0x18002a3c8  jz      short loc_18002A3FF
0x18002a3ca  mov     r15, r13
0x18002a3cd  lea     r8, [r15+r15*2]
0x18002a3d1  cmp     dword ptr [r14+r8*8+10h], 0FFFFFFFFh
0x18002a3d7  jnz     short loc_18002A3F4
0x18002a3d9  mov     [rbp+3B0h+var_408], 4
0x18002a3e0  lea     rcx, [rsp+4B0h+var_440]
0x18002a3e5  movzx   r9d, word ptr [r14+r8*8]
0x18002a3ea  mov     r8, [r14+r8*8+8]
0x18002a3ef  call    WsAddDomainName
0x18002a3f4  inc     r12d
0x18002a3f7  inc     r15
0x18002a3fa  cmp     r12d, esi
0x18002a3fd  jb      short loc_18002A3CD
0x18002a3ff  mov     eax, [rsp+4B0h+var_460]
0x18002a403  mov     esi, r13d
0x18002a406  test    eax, eax
0x18002a408  jz      loc_18002A49C
0x18002a40e  mov     r8d, esi
0x18002a411  add     r8, r8
0x18002a414  cmp     [rbx+r8*8+0Ch], r13d
0x18002a419  jz      short loc_18002A439
0x18002a41b  mov     [rbp+3B0h+var_408], 4
0x18002a422  lea     rcx, [rsp+4B0h+var_440]
0x18002a427  mov     r9d, [rbx+r8*8+8]
0x18002a42c  mov     r8, [rbx+r8*8]
0x18002a430  call    WsDeleteDomainName
0x18002a435  mov     eax, [rsp+4B0h+var_460]
0x18002a439  inc     esi
0x18002a43b  cmp     esi, eax
0x18002a43d  jb      short loc_18002A40E
0x18002a43f  jmp     short loc_18002A49C
0x18002a441  xor     r9d, r9d
0x18002a444  mov     [rsp+4B0h+hMem], r13
0x18002a449  lea     rcx, [rsp+4B0h+hMem]
0x18002a44e  call    NetpOpenConfigDataEx
0x18002a453  test    eax, eax
0x18002a455  jnz     short loc_18002A49C
0x18002a457  mov     rsi, [rsp+4B0h+hMem]
0x18002a45c  test    rsi, rsi
0x18002a45f  jz      short loc_18002A494
0x18002a461  mov     r15, [rsp+4B0h+var_448]
0x18002a466  mov     rcx, r15
0x18002a469  call    NetpTStrArraySize
0x18002a46e  test    eax, eax
0x18002a470  jz      short loc_18002A494
0x18002a472  mov     rcx, [rsi]; hKey
0x18002a475  lea     rdx, aOtherdomains; "OtherDomains"
0x18002a47c  mov     [rsp+4B0h+cbData], eax; cbData
0x18002a480  mov     r9d, 7; dwType
0x18002a486  xor     r8d, r8d; Reserved
0x18002a489  mov     [rsp+4B0h+lpData], r15; lpData
0x18002a48e  call    cs:__imp_RegSetValueExW
0x18002a494  mov     rcx, rsi
0x18002a497  call    NetpCloseConfigData
0x18002a49c  test    rbx, rbx
0x18002a49f  jz      short loc_18002A4AA
0x18002a4a1  mov     rcx, rbx; hMem
0x18002a4a4  call    cs:__imp_LocalFree
0x18002a4aa  mov     rcx, r14; hMem
0x18002a4ad  call    cs:__imp_LocalFree
0x18002a4b3  mov     r15, [rsp+4B0h+var_448]
0x18002a4b8  mov     rcx, r15; hMem
0x18002a4bb  call    cs:__imp_LocalFree
0x18002a4c1  mov     eax, edi
0x18002a4c3  mov     rcx, [rbp+3B0h+var_50]
0x18002a4ca  xor     rcx, rsp; StackCookie
0x18002a4cd  call    __security_check_cookie
0x18002a4d2  add     rsp, 478h
0x18002a4d9  pop     r15
0x18002a4db  pop     r14
0x18002a4dd  pop     r13
0x18002a4df  pop     r12
0x18002a4e1  pop     rdi
0x18002a4e2  pop     rsi
0x18002a4e3  pop     rbx
0x18002a4e4  pop     rbp
  ... truncated ...
```
