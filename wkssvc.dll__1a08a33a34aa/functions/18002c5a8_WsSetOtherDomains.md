# WsSetOtherDomains

- ea: `0x18002c5a8`
- end: `0x18002ca5f`
- name: `WsSetOtherDomains`
- size: `1207`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002c4c0`

## callees

- `0x180002c20`
- `0x180005504`
- `0x180007958`
- `0x180007a90`
- `0x18001fbd0`
- `0x1800204f6`
- `0x18002c5a8`
- `0x18002ea24`
- `0x18002ebf4`
- `0x18003190c`
- `0x180035fdc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c9ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c9ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c66f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c66f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c767`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c656`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c753`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c656`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ca0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ca19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ca2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ca0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ca19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ca2d`
- `netutils!NetpwListTraverse` at `0x18002c78c`
- `netutils!NetpwListTraverse` at `0x18002c78c`
- `netutils!NetpwListCanonicalize` at `0x18002c6ae`
- `netutils!NetpwListCanonicalize` at `0x18002c6ae`

## pseudocode

```c
int __fastcall WsSetOtherDomains(int a1, BYTE **a2)
{
  int v4; // ecx
  BYTE *v5; // rax
  unsigned int v6; // ebx
  BYTE *v7; // r15
  DWORD LogonId; // edi
  HKEY v9; // r8
  __int64 v10; // rdx
  _QWORD *v11; // rbx
  unsigned int v12; // eax
  WCHAR **v13; // r14
  unsigned int v14; // r12d
  __int64 v15; // rax
  WCHAR *v16; // r13
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned int i; // r15d
  __int64 v20; // rdx
  unsigned int v21; // esi
  __int64 v22; // r15
  unsigned int j; // esi
  unsigned int v24; // r15d
  LONG v25; // eax
  __int64 v26; // rdx
  unsigned int v27; // r12d
  __int64 v28; // r15
  unsigned int v29; // eax
  unsigned int k; // esi
  HKEY *v31; // rsi
  BYTE *lpData; // r15
  DWORD cbData; // eax
  unsigned int v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v36; // [rsp+54h] [rbp-ACh]
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  BYTE *v38; // [rsp+60h] [rbp-A0h] BYREF
  BYTE *v39; // [rsp+68h] [rbp-98h]
  _DWORD v40[3]; // [rsp+70h] [rbp-90h] BYREF
  struct _LUID DestinationLuid; // [rsp+7Ch] [rbp-84h] BYREF
  int v42; // [rsp+A8h] [rbp-58h]

  memset_0(v40, 0, 0x3F0u);
  hMem = 0;
  v4 = 0;
  if ( a1 != 1101 )
    a2 += 2;
  v35 = 0;
  v5 = *a2;
  v38 = v5;
  if ( v5 )
  {
    if ( WsDgReceiverDeviceHandle )
    {
      while ( *(_WORD *)v5 )
      {
        v5 += 2;
        if ( (*(_WORD *)v5 & 0xFFDF) == 0 )
          v35 = ++v4;
      }
      v6 = 32 * v4 + 2;
      v39 = (BYTE *)LocalAlloc(0x40u, v6);
      v7 = v39;
      if ( v39 )
      {
        if ( (unsigned int)NetpwListCanonicalize(v38, L" ", v39, v6, &v35, 0, 0, 1286) )
        {
          LogonId = 87;
        }
        else
        {
          v40[1] = 6;
          v40[0] = 0;
          v42 = 4;
          LogonId = WsImpersonateAndGetLogonId(&DestinationLuid);
          if ( !LogonId )
          {
            LogonId = WsDeviceControlGetInfo(1, WsDgReceiverDeviceHandle, 1245207, v40, 126, &hMem, -1, 0);
            if ( !LogonId )
            {
              v10 = v35;
              v11 = 0;
              v12 = v42;
              v13 = (WCHAR **)hMem;
              v36 = v42;
              if ( v35 )
              {
                v11 = LocalAlloc(0x40u, 16 * v35);
                if ( v11 )
                {
                  v14 = 0;
                  v38 = v7;
                  while ( 1 )
                  {
                    v15 = NetpwListTraverse(0, &v38, 0);
                    v16 = (WCHAR *)v15;
                    if ( !v15 )
                    {
                      v10 = v35;
                      v12 = v36;
                      goto LABEL_38;
                    }
                    v11[2 * v14] = v15;
                    v17 = -1;
                    do
                      ++v17;
                    while ( v16[v17] );
                    v18 = v36;
                    LODWORD(v11[2 * v14 + 1]) = 2 * v17;
                    for ( i = 0; i < (unsigned int)v18; ++i )
                    {
                      if ( LODWORD(v13[3 * i + 2]) == 4 )
                      {
                        if ( !WsCompareStringU(
                                v13[3 * i + 1],
                                LOWORD(v13[3 * i]) >> 1,
                                v16,
                                LODWORD(v11[2 * v14 + 1]) >> 1) )
                          goto LABEL_30;
                        v18 = v36;
                      }
                    }
                    if ( i == (_DWORD)v18 )
                    {
                      v42 = 4;
                      LogonId = WsAddDomainName(v40, v18, v16, LODWORD(v11[2 * v14 + 1]));
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
                              v42 = 4;
                              WsDeleteDomainName(v40, v20, v11[2 * v22], LODWORD(v11[2 * v22 + 1]));
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
                                (WCHAR *)v11[2 * v24],
                                LODWORD(v11[2 * v24 + 1]) >> 1);
                        v10 = v35;
                        if ( !v25 )
                          break;
                        ++v24;
                      }
                      while ( v24 < v35 );
                    }
                    if ( v24 == (_DWORD)v10 )
                    {
                      v42 = 4;
                      LogonId = WsDeleteDomainName(v40, v10, v13[3 * j + 1], LOWORD(v13[3 * j]));
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
                              v42 = 4;
                              WsAddDomainName(v40, v26, v13[3 * v28 + 1], LOWORD(v13[3 * v28]));
                            }
                            ++v27;
                            ++v28;
                          }
                          while ( v27 < j );
                        }
                        v29 = v35;
                        for ( k = 0; k < v29; ++k )
                        {
                          if ( HIDWORD(v11[2 * k + 1]) )
                          {
                            v42 = 4;
                            WsDeleteDomainName(v40, v26, v11[2 * k], LODWORD(v11[2 * k + 1]));
                            v29 = v35;
                          }
                        }
                        goto LABEL_63;
                      }
                      LODWORD(v13[3 * j + 2]) = -1;
                      v10 = v35;
                    }
                  }
                  v12 = v36;
                }
                hMem = 0;
                if ( !(unsigned int)NetpOpenConfigDataEx(&hMem, v10, v9, 0) )
                {
                  v31 = (HKEY *)hMem;
                  if ( hMem )
                  {
                    lpData = v39;
                    cbData = NetpTStrArraySize(v39);
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
              v7 = v39;
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
0x18002c5a8  push    rbp
0x18002c5aa  push    rbx
0x18002c5ab  push    rsi
0x18002c5ac  push    rdi
0x18002c5ad  push    r12
0x18002c5af  push    r13
0x18002c5b1  push    r14
0x18002c5b3  push    r15
0x18002c5b5  lea     rbp, [rsp-378h]
0x18002c5bd  sub     rsp, 478h
0x18002c5c4  mov     rax, cs:__security_cookie
0x18002c5cb  xor     rax, rsp
0x18002c5ce  mov     [rbp+3B0h+var_50], rax
0x18002c5d5  mov     rdi, rdx
0x18002c5d8  mov     ebx, ecx
0x18002c5da  xor     edx, edx; Val
0x18002c5dc  lea     rcx, [rsp+4B0h+var_440]; void *
0x18002c5e1  mov     r8d, 3F0h; Size
0x18002c5e7  call    memset_0
0x18002c5ec  xor     r13d, r13d
0x18002c5ef  lea     rax, [rdi+10h]
0x18002c5f3  cmp     ebx, 44Dh
0x18002c5f9  mov     [rsp+4B0h+hMem], r13
0x18002c5fe  mov     ecx, r13d
0x18002c601  cmovnz  rdi, rax
0x18002c605  mov     [rsp+4B0h+var_460], ecx
0x18002c609  mov     rax, [rdi]
0x18002c60c  mov     [rsp+4B0h+var_450], rax
0x18002c611  test    rax, rax
0x18002c614  jz      loc_18002CA3B
0x18002c61a  cmp     cs:WsDgReceiverDeviceHandle, r13
0x18002c621  jnz     short loc_18002C641
0x18002c623  mov     eax, 32h ; '2'
0x18002c628  jmp     loc_18002CA3B
0x18002c62d  lea     rax, [rax+2]
0x18002c631  mov     edx, 0FFDFh
0x18002c636  test    [rax], dx
0x18002c639  jnz     short loc_18002C641
0x18002c63b  inc     ecx
0x18002c63d  mov     [rsp+4B0h+var_460], ecx
0x18002c641  cmp     [rax], r13w
0x18002c645  jnz     short loc_18002C62D
0x18002c647  shl     ecx, 5
0x18002c64a  mov     esi, 40h ; '@'
0x18002c64f  lea     ebx, [rcx+2]
0x18002c652  mov     ecx, esi; uFlags
0x18002c654  mov     edx, ebx; uBytes
0x18002c656  call    cs:__imp_LocalAlloc
0x18002c65d  nop     dword ptr [rax+rax+00h]
0x18002c662  mov     [rsp+4B0h+var_448], rax
0x18002c667  mov     r15, rax
0x18002c66a  test    rax, rax
0x18002c66d  jnz     short loc_18002C680
0x18002c66f  call    cs:__imp_GetLastError
0x18002c676  nop     dword ptr [rax+rax+00h]
0x18002c67b  jmp     loc_18002CA3B
0x18002c680  mov     rcx, [rsp+4B0h+var_450]
0x18002c685  lea     rax, [rsp+4B0h+var_460]
0x18002c68a  mov     [rsp+4B0h+var_478], 506h
0x18002c692  lea     rdx, asc_180043940; " "
0x18002c699  mov     [rsp+4B0h+var_480], r13d
0x18002c69e  mov     r9d, ebx
0x18002c6a1  mov     qword ptr [rsp+4B0h+cbData], r13
0x18002c6a6  mov     r8, r15
0x18002c6a9  mov     [rsp+4B0h+lpData], rax
0x18002c6ae  call    cs:__imp_NetpwListCanonicalize
0x18002c6b5  nop     dword ptr [rax+rax+00h]
0x18002c6ba  test    eax, eax
0x18002c6bc  jz      short loc_18002C6C8
0x18002c6be  mov     edi, 57h ; 'W'
0x18002c6c3  jmp     loc_18002CA2A
0x18002c6c8  lea     rcx, [rsp+4B0h+DestinationLuid]; DestinationLuid
0x18002c6cd  mov     [rsp+4B0h+var_43C], 6
0x18002c6d5  mov     [rsp+4B0h+var_440], r13d
0x18002c6da  mov     [rbp+3B0h+var_408], 4
0x18002c6e1  call    WsImpersonateAndGetLogonId
0x18002c6e6  mov     edi, eax
0x18002c6e8  test    eax, eax
0x18002c6ea  jnz     loc_18002CA2A
0x18002c6f0  mov     rdx, cs:WsDgReceiverDeviceHandle
0x18002c6f7  lea     rax, [rsp+4B0h+hMem]
0x18002c6fc  mov     [rsp+4B0h+var_478], r13d
0x18002c701  lea     r9, [rsp+4B0h+var_440]
0x18002c706  mov     [rsp+4B0h+var_480], 0FFFFFFFFh
0x18002c70e  lea     ecx, [rdi+1]
0x18002c711  mov     qword ptr [rsp+4B0h+cbData], rax
0x18002c716  mov     r8d, 130017h
0x18002c71c  mov     dword ptr [rsp+4B0h+lpData], 7Eh ; '~'
0x18002c724  call    WsDeviceControlGetInfo
0x18002c729  mov     edi, eax
0x18002c72b  test    eax, eax
0x18002c72d  jnz     loc_18002CA2A
0x18002c733  mov     edx, [rsp+4B0h+var_460]
0x18002c737  mov     rbx, r13
0x18002c73a  mov     eax, [rbp+3B0h+var_408]
0x18002c73d  mov     r14, [rsp+4B0h+hMem]
0x18002c742  mov     [rsp+4B0h+var_45C], eax
0x18002c746  test    edx, edx
0x18002c748  jz      loc_18002C892
0x18002c74e  shl     edx, 4; uBytes
0x18002c751  mov     ecx, esi; uFlags
0x18002c753  call    cs:__imp_LocalAlloc
0x18002c75a  nop     dword ptr [rax+rax+00h]
0x18002c75f  mov     rbx, rax
0x18002c762  test    rax, rax
0x18002c765  jnz     short loc_18002C77A
0x18002c767  call    cs:__imp_GetLastError
0x18002c76e  nop     dword ptr [rax+rax+00h]
0x18002c773  mov     edi, eax
0x18002c775  jmp     loc_18002CA16
0x18002c77a  mov     r12d, r13d
0x18002c77d  mov     [rsp+4B0h+var_450], r15
0x18002c782  xor     r8d, r8d
0x18002c785  lea     rdx, [rsp+4B0h+var_450]
0x18002c78a  xor     ecx, ecx
0x18002c78c  call    cs:__imp_NetpwListTraverse
0x18002c793  nop     dword ptr [rax+rax+00h]
0x18002c798  xor     ecx, ecx
0x18002c79a  mov     r13, rax
0x18002c79d  test    rax, rax
0x18002c7a0  jz      loc_18002C887
0x18002c7a6  mov     esi, r12d
0x18002c7a9  add     rsi, rsi
0x18002c7ac  mov     [rbx+rsi*8], rax
0x18002c7b0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c7b4  inc     rax
0x18002c7b7  cmp     [r13+rax*2+0], cx
0x18002c7bd  jnz     short loc_18002C7B4
0x18002c7bf  mov     edx, [rsp+4B0h+var_45C]
0x18002c7c3  add     eax, eax
0x18002c7c5  mov     [rbx+rsi*8+8], eax
0x18002c7c9  mov     r15d, ecx
0x18002c7cc  test    edx, edx
0x18002c7ce  jz      short loc_18002C80B
0x18002c7d0  mov     eax, r15d
0x18002c7d3  lea     rcx, [rax+rax*2]
0x18002c7d7  cmp     dword ptr [r14+rcx*8+10h], 4
0x18002c7dd  jnz     short loc_18002C803
0x18002c7df  movzx   edx, word ptr [r14+rcx*8]
0x18002c7e4  mov     r8, r13
0x18002c7e7  mov     r9d, [rbx+rsi*8+8]
0x18002c7ec  mov     rcx, [r14+rcx*8+8]
0x18002c7f1  shr     r9d, 1
0x18002c7f4  shr     edx, 1
0x18002c7f6  call    WsCompareStringU
0x18002c7fb  test    eax, eax
0x18002c7fd  jz      short loc_18002C839
0x18002c7ff  mov     edx, [rsp+4B0h+var_45C]
0x18002c803  inc     r15d
0x18002c806  cmp     r15d, edx
0x18002c809  jb      short loc_18002C7D0
0x18002c80b  cmp     r15d, edx
0x18002c80e  jnz     short loc_18002C839
0x18002c810  mov     [rbp+3B0h+var_408], 4
0x18002c817  lea     rcx, [rsp+4B0h+var_440]
0x18002c81c  mov     r9d, [rbx+rsi*8+8]
0x18002c821  mov     r8, r13
0x18002c824  call    WsAddDomainName
0x18002c829  xor     ecx, ecx
0x18002c82b  mov     edi, eax
0x18002c82d  test    eax, eax
0x18002c82f  jnz     short loc_18002C841
0x18002c831  mov     dword ptr [rbx+rsi*8+0Ch], 1
0x18002c839  inc     r12d
0x18002c83c  jmp     loc_18002C782
0x18002c841  mov     esi, ecx
0x18002c843  test    r12d, r12d
0x18002c846  jz      loc_18002CA07
0x18002c84c  mov     r15, rcx
0x18002c84f  mov     r8, r15
0x18002c852  add     r8, r8
0x18002c855  cmp     [rbx+r8*8+0Ch], ecx
0x18002c85a  jz      short loc_18002C878
0x18002c85c  mov     [rbp+3B0h+var_408], 4
0x18002c863  lea     rcx, [rsp+4B0h+var_440]
0x18002c868  mov     r9d, [rbx+r8*8+8]
0x18002c86d  mov     r8, [rbx+r8*8]
0x18002c871  call    WsDeleteDomainName
0x18002c876  xor     ecx, ecx
0x18002c878  inc     esi
0x18002c87a  inc     r15
0x18002c87d  cmp     esi, r12d
0x18002c880  jb      short loc_18002C84F
0x18002c882  jmp     loc_18002CA07
0x18002c887  mov     edx, [rsp+4B0h+var_460]
0x18002c88b  xor     r13d, r13d
0x18002c88e  mov     eax, [rsp+4B0h+var_45C]
0x18002c892  mov     esi, r13d
0x18002c895  cmp     esi, eax
0x18002c897  jnb     loc_18002C9A1
0x18002c89d  mov     eax, esi
0x18002c89f  lea     r12, [rax+rax*2]
0x18002c8a3  cmp     dword ptr [r14+r12*8+10h], 4
0x18002c8a9  jnz     short loc_18002C918
0x18002c8ab  mov     r15d, r13d
0x18002c8ae  test    edx, edx
0x18002c8b0  jz      short loc_18002C8E5
0x18002c8b2  movzx   edx, word ptr [r14+r12*8]
0x18002c8b7  mov     rcx, [r14+r12*8+8]
0x18002c8bc  mov     r8d, r15d
0x18002c8bf  add     r8, r8
0x18002c8c2  shr     edx, 1
0x18002c8c4  mov     r9d, [rbx+r8*8+8]
0x18002c8c9  mov     r8, [rbx+r8*8]
0x18002c8cd  shr     r9d, 1
0x18002c8d0  call    WsCompareStringU
0x18002c8d5  mov     edx, [rsp+4B0h+var_460]
0x18002c8d9  test    eax, eax
0x18002c8db  jz      short loc_18002C8E5
0x18002c8dd  inc     r15d
0x18002c8e0  cmp     r15d, edx
0x18002c8e3  jb      short loc_18002C8B2
0x18002c8e5  cmp     r15d, edx
0x18002c8e8  jnz     short loc_18002C918
0x18002c8ea  mov     [rbp+3B0h+var_408], 4
0x18002c8f1  lea     rcx, [rsp+4B0h+var_440]
0x18002c8f6  movzx   r9d, word ptr [r14+r12*8]
0x18002c8fb  mov     r8, [r14+r12*8+8]
0x18002c900  call    WsDeleteDomainName
0x18002c905  mov     edi, eax
0x18002c907  test    eax, eax
0x18002c909  jnz     short loc_18002C923
0x18002c90b  mov     dword ptr [r14+r12*8+10h], 0FFFFFFFFh
0x18002c914  mov     edx, [rsp+4B0h+var_460]
0x18002c918  mov     eax, [rsp+4B0h+var_45C]
0x18002c91c  inc     esi
0x18002c91e  jmp     loc_18002C895
0x18002c923  mov     r12d, r13d
0x18002c926  test    esi, esi
0x18002c928  jz      short loc_18002C95F
0x18002c92a  mov     r15, r13
0x18002c92d  lea     r8, [r15+r15*2]
0x18002c931  cmp     dword ptr [r14+r8*8+10h], 0FFFFFFFFh
0x18002c937  jnz     short loc_18002C954
0x18002c939  mov     [rbp+3B0h+var_408], 4
0x18002c940  lea     rcx, [rsp+4B0h+var_440]
0x18002c945  movzx   r9d, word ptr [r14+r8*8]
0x18002c94a  mov     r8, [r14+r8*8+8]
0x18002c94f  call    WsAddDomainName
0x18002c954  inc     r12d
0x18002c957  inc     r15
0x18002c95a  cmp     r12d, esi
0x18002c95d  jb      short loc_18002C92D
0x18002c95f  mov     eax, [rsp+4B0h+var_460]
0x18002c963  mov     esi, r13d
0x18002c966  test    eax, eax
0x18002c968  jz      loc_18002CA02
0x18002c96e  mov     r8d, esi
0x18002c971  add     r8, r8
0x18002c974  cmp     [rbx+r8*8+0Ch], r13d
0x18002c979  jz      short loc_18002C999
0x18002c97b  mov     [rbp+3B0h+var_408], 4
0x18002c982  lea     rcx, [rsp+4B0h+var_440]
0x18002c987  mov     r9d, [rbx+r8*8+8]
0x18002c98c  mov     r8, [rbx+r8*8]
0x18002c990  call    WsDeleteDomainName
0x18002c995  mov     eax, [rsp+4B0h+var_460]
0x18002c999  inc     esi
0x18002c99b  cmp     esi, eax
0x18002c99d  jb      short loc_18002C96E
0x18002c99f  jmp     short loc_18002CA02
0x18002c9a1  xor     r9d, r9d
0x18002c9a4  mov     [rsp+4B0h+hMem], r13
0x18002c9a9  lea     rcx, [rsp+4B0h+hMem]
0x18002c9ae  call    NetpOpenConfigDataEx
0x18002c9b3  test    eax, eax
0x18002c9b5  jnz     short loc_18002CA02
0x18002c9b7  mov     rsi, [rsp+4B0h+hMem]
0x18002c9bc  test    rsi, rsi
0x18002c9bf  jz      short loc_18002C9FA
0x18002c9c1  mov     r15, [rsp+4B0h+var_448]
0x18002c9c6  mov     rcx, r15
0x18002c9c9  call    NetpTStrArraySize
0x18002c9ce  test    eax, eax
0x18002c9d0  jz      short loc_18002C9FA
0x18002c9d2  mov     rcx, [rsi]; hKey
0x18002c9d5  lea     rdx, aOtherdomains; "OtherDomains"
0x18002c9dc  mov     [rsp+4B0h+cbData], eax; cbData
0x18002c9e0  mov     r9d, 7; dwType
0x18002c9e6  xor     r8d, r8d; Reserved
0x18002c9e9  mov     [rsp+4B0h+lpData], r15; lpData
0x18002c9ee  call    cs:__imp_RegSetValueExW
0x18002c9f5  nop     dword ptr [rax+rax+00h]
0x18002c9fa  mov     rcx, rsi
0x18002c9fd  call    NetpCloseConfigData
0x18002ca02  test    rbx, rbx
0x18002ca05  jz      short loc_18002CA16
0x18002ca07  mov     rcx, rbx; hMem
0x18002ca0a  call    cs:__imp_LocalFree
0x18002ca11  nop     dword ptr [rax+rax+00h]
0x18002ca16  mov     rcx, r14; hMem
0x18002ca19  call    cs:__imp_LocalFree
0x18002ca20  nop     dword ptr [rax+rax+00h]
0x18002ca25  mov     r15, [rsp+4B0h+var_448]
0x18002ca2a  mov     rcx, r15; hMem
0x18002ca2d  call    cs:__imp_LocalFree
0x18002ca34  nop     dword ptr [rax+rax+00h]
0x18002ca39  mov     eax, edi
0x18002ca3b  mov     rcx, [rbp+3B0h+var_50]
0x18002ca42  xor     rcx, rsp; StackCookie
  ... truncated ...
```
