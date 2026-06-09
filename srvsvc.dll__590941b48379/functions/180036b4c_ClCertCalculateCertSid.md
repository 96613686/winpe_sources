# ClCertCalculateCertSid

- ea: `0x180036b4c`
- end: `0x180036fb0`
- name: `ClCertCalculateCertSid`
- size: `1124`
- prototype: `__int64 __fastcall(int, unsigned int, _WORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180036fb8`
- `0x180039214`
- `0x1800395a4`

## callees

- `0x18001e8bc`
- `0x180020dc0`
- `0x180020de8`
- `0x180021504`
- `0x180036364`
- `0x180036928`
- `0x180036b4c`
- `0x180037510`
- `0x18003756c`
- `0x180038aa0`
- `0x180038d98`
- `0x18003a3b8`
- `0x18003a740`
- `0x18003b040`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180036d19`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180036d19`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036c9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036df8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036c9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036df8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180036c04`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180036c04`

## pseudocode

```c
__int64 __fastcall ClCertCalculateCertSid(int a1, unsigned int a2, _WORD *a3, _QWORD *a4)
{
  wchar_t *v6; // rsi
  __int64 v8; // rbp
  ULONG v9; // r8d
  __int64 v10; // r15
  int v11; // edx
  wchar_t *v12; // r14
  NTSTATUS v13; // ebx
  wchar_t *v14; // rax
  int v15; // edx
  int v16; // r8d
  ULONG v17; // ebx
  __int64 v18; // rax
  unsigned __int64 v19; // rsi
  unsigned int v20; // eax
  int v21; // r10d
  wchar_t *v22; // rax
  wchar_t *v23; // rbx
  __int64 v24; // rdx
  unsigned int v25; // eax
  ULONG v26; // eax
  int v27; // edx
  __int64 v28; // rax
  size_t v29; // rsi
  unsigned int v30; // eax
  int v31; // r10d
  int v32; // edx
  const wchar_t *v33; // r9
  int v34; // edx
  wchar_t *v35; // rax
  int v36; // edx
  int v37; // r8d
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-48h] BYREF
  _WORD *v40; // [rsp+48h] [rbp-40h]
  wchar_t *v42; // [rsp+A8h] [rbp+20h]

  hHash = 0;
  v6 = 0;
  v40 = 0;
  v42 = 0;
  *a4 = 0;
  v8 = -1;
  v10 = ClCertIdentifierTypeToString(a2);
  if ( v11 != 1 )
  {
    v17 = v9;
    goto LABEL_35;
  }
  v12 = (wchar_t *)v9;
  v13 = ClCertDuplicateHashHandle(&phAlgorithm, &hHash);
  if ( v13 >= 0 )
  {
    v18 = -1;
    do
      ++v18;
    while ( a3[v18] );
    v19 = 2 * v18 + 2;
    if ( v19 > 0xFFFFFFFF )
    {
      v17 = 534;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v20 = (unsigned int)ClCertAccessControlTypeToString(a1);
        WPP_SF_SSS(v21, 82, (unsigned int)WPP_053b19d310c5352633ee666709ba12ba_Traceguids, v20, v10, (__int64)a3);
        v6 = v12;
      }
      else
      {
        v6 = 0;
      }
      goto LABEL_58;
    }
    v22 = (wchar_t *)LocalAlloc(0, v19);
    v42 = v22;
    v23 = v22;
    if ( !v22 )
    {
      v17 = 8;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_053b19d310c5352633ee666709ba12ba_Traceguids);
      }
      goto LABEL_20;
    }
    memcpy_0(v22, a3, v19);
    v24 = -1;
    do
      ++v24;
    while ( a3[v24] );
    v25 = _wcslwr_s(v23, v24 + 1);
    if ( v25 )
    {
      v17 = 1359;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_053b19d310c5352633ee666709ba12ba_Traceguids, v25);
      }
      goto LABEL_20;
    }
    v26 = ClCertCalculateBlobHash((PUCHAR)v23, v19, hHash);
    LOWORD(v9) = 0;
    v17 = v26;
    if ( v26 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_DSI(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, 0, v26, (__int64)a3, v19);
      }
      goto LABEL_20;
    }
    a3 = v40;
LABEL_35:
    v28 = -1;
    do
      ++v28;
    while ( a3[v28] != (_WORD)v9 );
    do
      ++v8;
    while ( *(_WORD *)(v10 + 2 * v8) != (_WORD)v9 );
    v29 = v28 + v8 + 4;
    v12 = (wchar_t *)LocalAlloc(0, 2 * v29);
    if ( v12 )
    {
      v33 = L"A";
      if ( a1 )
        v33 = L"D";
      v34 = swprintf_s(v12, v29, L"%s_%s_%s", v33, v10, a3);
      if ( v34 >= 0 )
      {
        if ( v34 == (_DWORD)v29 - 1 )
        {
          *a4 = v12;
          v12 = 0;
        }
        else
        {
          v17 = 13;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            v35 = ClCertAccessControlTypeToString(a1);
            WPP_SF_IdSSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, v37, v29 - 1, v36, (__int64)v35, v10, (__int64)a3);
          }
        }
        goto LABEL_20;
      }
      v17 = 122;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
LABEL_20:
        v6 = v42;
        goto LABEL_58;
      }
      v30 = (unsigned int)ClCertAccessControlTypeToString(a1);
      v32 = 87;
    }
    else
    {
      v17 = 8;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_20;
      }
      v30 = (unsigned int)ClCertAccessControlTypeToString(a1);
      v32 = 86;
    }
    WPP_SF_SSS(v31, v32, (unsigned int)WPP_053b19d310c5352633ee666709ba12ba_Traceguids, v30, v10, (__int64)a3);
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v14 = ClCertAccessControlTypeToString(a1);
    WPP_SF_dSSS(v15, v15, v16, v13, (__int64)v14, v10, (__int64)a3);
  }
  v17 = RtlNtStatusToDosErrorNoTeb(v13);
LABEL_58:
  ClCertDestroyHashHandle(hHash);
  if ( a2 == 1 )
    ClCertLocalFree(v40);
  ClCertLocalFree(v12);
  ClCertLocalFree(v6);
  return v17;
}

```

## disassembly

```asm
0x180036b4c  mov     rax, rsp
0x180036b4f  mov     [rax+8], rbx
0x180036b53  mov     [rax+10h], edx
0x180036b56  push    rbp
0x180036b57  push    rsi
0x180036b58  push    rdi
0x180036b59  push    r12
0x180036b5b  push    r13
0x180036b5d  push    r14
0x180036b5f  push    r15
0x180036b61  sub     rsp, 50h
0x180036b65  mov     r13d, ecx
0x180036b68  mov     rdi, r8
0x180036b6b  xor     r8d, r8d
0x180036b6e  mov     ecx, edx
0x180036b70  mov     [rax-48h], r8
0x180036b74  mov     esi, r8d
0x180036b77  mov     [rax-40h], r8
0x180036b7b  mov     r12, r9
0x180036b7e  mov     [rsp+88h+arg_18], r8
0x180036b86  mov     [r9], r8
0x180036b89  call    ClCertIdentifierTypeToString
0x180036b8e  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180036b92  mov     r15, rax
0x180036b95  cmp     edx, 1
0x180036b98  jnz     loc_180036DD1
0x180036b9e  lea     rdx, [rsp+88h+hHash]
0x180036ba3  mov     r14d, r8d
0x180036ba6  lea     rcx, phAlgorithm
0x180036bad  call    ClCertDuplicateHashHandle
0x180036bb2  xor     ecx, ecx; uFlags
0x180036bb4  mov     ebx, eax
0x180036bb6  test    eax, eax
0x180036bb8  jns     short loc_180036C11
0x180036bba  mov     rdx, cs:WPP_GLOBAL_Control
0x180036bc1  lea     rax, WPP_GLOBAL_Control
0x180036bc8  cmp     rdx, rax
0x180036bcb  jz      short loc_180036C02
0x180036bcd  test    dword ptr [rdx+1Ch], 800h
0x180036bd4  jz      short loc_180036C02
0x180036bd6  cmp     byte ptr [rdx+19h], 1
0x180036bda  jb      short loc_180036C02
0x180036bdc  mov     rdx, [rdx+10h]
0x180036be0  mov     ecx, r13d
0x180036be3  call    ClCertAccessControlTypeToString
0x180036be8  mov     [rsp+88h+var_58], rdi
0x180036bed  mov     rcx, rdx
0x180036bf0  mov     [rsp+88h+var_60], r15
0x180036bf5  mov     r9d, ebx
0x180036bf8  mov     [rsp+88h+var_68], rax
0x180036bfd  call    WPP_SF_dSSS
0x180036c02  mov     ecx, ebx; Status
0x180036c04  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180036c0a  mov     ebx, eax
0x180036c0c  jmp     loc_180036F68
0x180036c11  mov     rax, rbp
0x180036c14  inc     rax
0x180036c17  cmp     [rdi+rax*2], cx
0x180036c1b  jnz     short loc_180036C14
0x180036c1d  lea     rsi, ds:2[rax*2]
0x180036c25  mov     eax, 0FFFFFFFFh
0x180036c2a  cmp     rsi, rax
0x180036c2d  jbe     short loc_180036C99
0x180036c2f  mov     ebx, 216h
0x180036c34  mov     r10, cs:WPP_GLOBAL_Control
0x180036c3b  lea     rax, WPP_GLOBAL_Control
0x180036c42  cmp     r10, rax
0x180036c45  jz      loc_180036F65
0x180036c4b  test    dword ptr [r10+1Ch], 800h
0x180036c53  jz      loc_180036F65
0x180036c59  cmp     byte ptr [r10+19h], 1
0x180036c5e  jb      loc_180036F65
0x180036c64  mov     r10, [r10+10h]
0x180036c68  mov     ecx, r13d
0x180036c6b  call    ClCertAccessControlTypeToString
0x180036c70  mov     r9, rax
0x180036c73  mov     [rsp+88h+var_60], rdi
0x180036c78  mov     rcx, r10
0x180036c7b  mov     [rsp+88h+var_68], r15
0x180036c80  mov     edx, 52h ; 'R'
0x180036c85  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180036c8c  call    WPP_SF_SSS
0x180036c91  mov     rsi, r14
0x180036c94  jmp     loc_180036F68
0x180036c99  mov     rdx, rsi; uBytes
0x180036c9c  call    cs:__imp_LocalAlloc
0x180036ca2  mov     [rsp+88h+arg_18], rax
0x180036caa  mov     rbx, rax
0x180036cad  test    rax, rax
0x180036cb0  jnz     short loc_180036CF7
0x180036cb2  lea     ebx, [rax+8]
0x180036cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cbc  lea     rax, WPP_GLOBAL_Control
0x180036cc3  cmp     rcx, rax
0x180036cc6  jz      short loc_180036CEA
0x180036cc8  test    dword ptr [rcx+1Ch], 800h
0x180036ccf  jz      short loc_180036CEA
0x180036cd1  cmp     byte ptr [rcx+19h], 1
0x180036cd5  jb      short loc_180036CEA
0x180036cd7  mov     rcx, [rcx+10h]
0x180036cdb  lea     edx, [rbx+4Bh]
0x180036cde  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180036ce5  call    WPP_SF_
0x180036cea  mov     rsi, [rsp+88h+arg_18]
0x180036cf2  jmp     loc_180036F68
0x180036cf7  mov     r8, rsi; Size
0x180036cfa  mov     rdx, rdi; Src
0x180036cfd  mov     rcx, rbx; void *
0x180036d00  call    memcpy_0
0x180036d05  mov     rdx, rbp
0x180036d08  xor     eax, eax
0x180036d0a  inc     rdx
0x180036d0d  cmp     [rdi+rdx*2], ax
0x180036d11  jnz     short loc_180036D0A
0x180036d13  inc     rdx; SizeInWords
0x180036d16  mov     rcx, rbx; String
0x180036d19  call    cs:__imp__wcslwr_s
0x180036d1f  mov     r9d, eax
0x180036d22  test    eax, eax
0x180036d24  jz      short loc_180036D64
0x180036d26  mov     ebx, 54Fh
0x180036d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d32  lea     rax, WPP_GLOBAL_Control
0x180036d39  cmp     rcx, rax
0x180036d3c  jz      short loc_180036CEA
0x180036d3e  test    dword ptr [rcx+1Ch], 800h
0x180036d45  jz      short loc_180036CEA
0x180036d47  cmp     byte ptr [rcx+19h], 1
0x180036d4b  jb      short loc_180036CEA
0x180036d4d  mov     rcx, [rcx+10h]
0x180036d51  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180036d58  mov     edx, 54h ; 'T'
0x180036d5d  call    WPP_SF_d
0x180036d62  jmp     short loc_180036CEA
0x180036d64  mov     r8, [rsp+88h+hHash]; hHash
0x180036d69  lea     r9, [rsp+88h+var_40]
0x180036d6e  mov     edx, esi; cbInput
0x180036d70  mov     rcx, rbx; pbInput
0x180036d73  call    ClCertCalculateBlobHash
0x180036d78  xor     r8d, r8d
0x180036d7b  mov     ebx, eax
0x180036d7d  test    eax, eax
0x180036d7f  jz      short loc_180036DCA
0x180036d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d88  lea     rax, WPP_GLOBAL_Control
0x180036d8f  cmp     rcx, rax
0x180036d92  jz      loc_180036CEA
0x180036d98  test    dword ptr [rcx+1Ch], 800h
0x180036d9f  jz      loc_180036CEA
0x180036da5  cmp     byte ptr [rcx+19h], 1
0x180036da9  jb      loc_180036CEA
0x180036daf  mov     rcx, [rcx+10h]
0x180036db3  mov     r9d, ebx
0x180036db6  mov     [rsp+88h+var_60], rsi
0x180036dbb  mov     [rsp+88h+var_68], rdi
0x180036dc0  call    WPP_SF_DSI
0x180036dc5  jmp     loc_180036CEA
0x180036dca  mov     rdi, [rsp+88h+var_40]
0x180036dcf  jmp     short loc_180036DD4
0x180036dd1  mov     ebx, r8d
0x180036dd4  mov     rax, rbp
0x180036dd7  inc     rax
0x180036dda  cmp     [rdi+rax*2], r8w
0x180036ddf  jnz     short loc_180036DD7
0x180036de1  inc     rbp
0x180036de4  cmp     [r15+rbp*2], r8w
0x180036de9  jnz     short loc_180036DE1
0x180036deb  lea     rsi, [rbp+4]
0x180036def  xor     ecx, ecx; uFlags
0x180036df1  add     rsi, rax
0x180036df4  lea     rdx, [rsi+rsi]; uBytes
0x180036df8  call    cs:__imp_LocalAlloc
0x180036dfe  xor     ebp, ebp
0x180036e00  mov     r14, rax
0x180036e03  test    rax, rax
0x180036e06  jnz     short loc_180036E6B
0x180036e08  lea     ebx, [rax+8]
0x180036e0b  mov     r10, cs:WPP_GLOBAL_Control
0x180036e12  lea     rax, WPP_GLOBAL_Control
0x180036e19  cmp     r10, rax
0x180036e1c  jz      loc_180036CEA
0x180036e22  test    dword ptr [r10+1Ch], 800h
0x180036e2a  jz      loc_180036CEA
0x180036e30  cmp     byte ptr [r10+19h], 1
0x180036e35  jb      loc_180036CEA
0x180036e3b  mov     r10, [r10+10h]
0x180036e3f  mov     ecx, r13d
0x180036e42  call    ClCertAccessControlTypeToString
0x180036e47  lea     edx, [rbp+56h]
0x180036e4a  mov     r9, rax
0x180036e4d  mov     [rsp+88h+var_60], rdi
0x180036e52  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180036e59  mov     [rsp+88h+var_68], r15
0x180036e5e  mov     rcx, r10
0x180036e61  call    WPP_SF_SSS
0x180036e66  jmp     loc_180036CEA
0x180036e6b  lea     rax, aD; "D"
0x180036e72  mov     [rsp+88h+var_60], rdi
0x180036e77  test    r13d, r13d
0x180036e7a  mov     [rsp+88h+var_68], r15
0x180036e7f  lea     r9, aA; "A"
0x180036e86  mov     rdx, rsi; BufferCount
0x180036e89  cmovnz  r9, rax
0x180036e8d  lea     r8, aSSS_0; "%s_%s_%s"
0x180036e94  mov     rcx, r14; Buffer
0x180036e97  call    swprintf_s
0x180036e9c  mov     edx, eax
0x180036e9e  test    eax, eax
0x180036ea0  jns     short loc_180036EEB
0x180036ea2  mov     ebx, 7Ah ; 'z'
0x180036ea7  mov     r10, cs:WPP_GLOBAL_Control
0x180036eae  lea     rax, WPP_GLOBAL_Control
0x180036eb5  cmp     r10, rax
0x180036eb8  jz      loc_180036CEA
0x180036ebe  test    dword ptr [r10+1Ch], 800h
0x180036ec6  jz      loc_180036CEA
0x180036ecc  cmp     byte ptr [r10+19h], 1
0x180036ed1  jb      loc_180036CEA
0x180036ed7  mov     r10, [r10+10h]
0x180036edb  mov     ecx, r13d
0x180036ede  call    ClCertAccessControlTypeToString
0x180036ee3  lea     edx, [rbx-23h]
0x180036ee6  jmp     loc_180036E4A
0x180036eeb  lea     eax, [rsi-1]
0x180036eee  cmp     edx, eax
0x180036ef0  jz      short loc_180036F59
0x180036ef2  mov     ebx, 0Dh
0x180036ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x180036efe  lea     rax, WPP_GLOBAL_Control
0x180036f05  cmp     rcx, rax
0x180036f08  jz      loc_180036CEA
0x180036f0e  test    dword ptr [rcx+1Ch], 800h
0x180036f15  jz      loc_180036CEA
0x180036f1b  cmp     byte ptr [rcx+19h], 1
0x180036f1f  jb      loc_180036CEA
0x180036f25  mov     ecx, r13d
0x180036f28  call    ClCertAccessControlTypeToString
0x180036f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f34  lea     r9, [rsi-1]
0x180036f38  mov     [rsp+88h+var_50], rdi
0x180036f3d  mov     [rsp+88h+var_58], r15
0x180036f42  mov     [rsp+88h+var_60], rax
0x180036f47  mov     rcx, [rcx+10h]
0x180036f4b  mov     dword ptr [rsp+88h+var_68], edx
0x180036f4f  call    WPP_SF_IdSSS
0x180036f54  jmp     loc_180036CEA
0x180036f59  mov     [r12], r14
0x180036f5d  mov     r14, rbp
0x180036f60  jmp     loc_180036CEA
0x180036f65  mov     rsi, rcx
0x180036f68  mov     rcx, [rsp+88h+hHash]
0x180036f6d  call    ClCertDestroyHashHandle
0x180036f72  cmp     [rsp+88h+arg_8], 1
0x180036f7a  jnz     short loc_180036F86
0x180036f7c  mov     rcx, [rsp+88h+var_40]
0x180036f81  call    ClCertLocalFree
0x180036f86  mov     rcx, r14
0x180036f89  call    ClCertLocalFree
0x180036f8e  mov     rcx, rsi
0x180036f91  call    ClCertLocalFree
0x180036f96  mov     eax, ebx
0x180036f98  mov     rbx, [rsp+88h+arg_0]
0x180036fa0  add     rsp, 50h
0x180036fa4  pop     r15
0x180036fa6  pop     r14
0x180036fa8  pop     r13
0x180036faa  pop     r12
0x180036fac  pop     rdi
0x180036fad  pop     rsi
0x180036fae  pop     rbp
0x180036faf  retn
```
