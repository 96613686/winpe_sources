# MakeAuthenticatorMessage

- ea: `0x180071d0c`
- end: `0x18007261f`
- name: `MakeAuthenticatorMessage`
- size: `2323`
- prototype: `DWORD __fastcall(__int64, _BYTE *, _BYTE *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180071470`

## callees

- `0x180014b90`
- `0x180065d28`
- `0x180065fc8`
- `0x180071d0c`
- `0x180072628`
- `0x180076ccc`
- `0x180077552`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072179`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071f0a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180072167`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180072238`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180072382`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071f0a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180072167`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180072238`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180072382`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071ec0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007213c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800721cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007224f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072258`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800722b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072337`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800724ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071ec0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007213c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800721cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007224f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072258`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800722b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072337`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800724ab`

## string_xrefs

- `0x180072583`: `pReceiveBuf->Length is less than PPP_CONFIG_HDR_LEN + 1 -- Dropping invalid packet`
- `0x1800720f1`: `Error %d while processing Access-Request`
- `0x180071fbb`: `The cached EapSendBufferr is NULL or its size is less than minimum size`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall MakeAuthenticatorMessage(__int64 a1, _BYTE *a2, _BYTE *a3, unsigned int a4, __int64 a5, __int64 a6)
{
  __int64 v9; // r14
  __int64 v11; // rax
  const wchar_t *v12; // r8
  DWORD RequestAttributes; // edx
  const void **v14; // rbx
  void *v15; // rcx
  HLOCAL v16; // rax
  void *v17; // rcx
  int v18; // eax
  __int64 v19; // rax
  void *v20; // rcx
  const void **v21; // rax
  const void **v22; // rbx
  HLOCAL v23; // rax
  char *ConcatString; // r14
  void *v25; // rcx
  char *v26; // rax
  unsigned __int16 v27; // r15
  HLOCAL v28; // rax
  size_t v29; // r8
  HLOCAL v30; // rdx
  __int64 v31; // rdx
  unsigned int v32; // r15d
  HLOCAL v33; // rax
  size_t v34; // r8
  void *v35; // rcx
  _DWORD *v36; // rax
  _DWORD *v37; // rax
  int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  __int64 v41; // rbx
  unsigned int Size; // [rsp+24h] [rbp-DCh] BYREF
  unsigned int Size_4; // [rsp+28h] [rbp-D8h]
  size_t v44; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h]
  int v46; // [rsp+40h] [rbp-C0h] BYREF
  char v47[2044]; // [rsp+44h] [rbp-BCh] BYREF

  Size = 0;
  LODWORD(v44) = 0;
  v46 = 0;
  Size_4 = a4;
  memset_0(v47, 0, sizeof(v47));
  v9 = *((_QWORD *)&xmmword_1800AB2C0 + 1);
  if ( *((_QWORD *)&xmmword_1800AB2C0 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_1800AB2C0 + 1),
      L"MakeAuthenticatorMessage...");
    v9 = *((_QWORD *)&xmmword_1800AB2C0 + 1);
  }
  if ( !a1 )
    return 87;
  *(_DWORD *)(a5 + 360) = *(_DWORD *)(a1 + 36);
  if ( !*(_DWORD *)a1 )
    goto LABEL_115;
  if ( *(_DWORD *)a1 == 1 )
  {
    if ( v9 )
    {
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
        gRasEapEtwContext,
        v9,
        L"EAPSTATE_IdentityRequestSent");
      v9 = *((_QWORD *)&xmmword_1800AB2C0 + 1);
    }
    if ( a2 )
    {
      v39 = (unsigned __int8)a2[3] + ((unsigned __int8)a2[2] << 8);
      if ( v39 < 5 )
      {
        if ( !v9 )
          goto LABEL_17;
        v12 = L"pReceiveBuf->Length is less than PPP_CONFIG_HDR_LEN + 1 -- Dropping invalid packet";
      }
      else
      {
        if ( *a2 == 2 && a2[4] == 1 )
        {
          v40 = v39 - 5;
          if ( v40 > 0x110 )
            v40 = 272;
          v41 = v40;
          memcpy_0((void *)(a1 + 44), a2 + 5, v40);
          *(_BYTE *)(a1 + v41 + 44) = 0;
          RequestAttributes = MakeRequestAttributes(a1, (__int64)a2);
          if ( !RequestAttributes )
          {
            *(_QWORD *)(a5 + 288) = *(_QWORD *)(a1 + 384);
            *(_DWORD *)a1 = 3;
            *(_DWORD *)a5 = 6;
          }
          return RequestAttributes;
        }
        if ( !v9 )
          goto LABEL_17;
        v12 = L"Dropping invalid packet";
      }
      goto LABEL_16;
    }
    if ( !v9 )
      goto LABEL_117;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      v9,
      L"No response from the client, timing out and retransmitting identity request.");
    v9 = *((_QWORD *)&xmmword_1800AB2C0 + 1);
LABEL_115:
    if ( v9 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
        gRasEapEtwContext,
        v9,
        L"EAPSTATE_Initial");
LABEL_117:
    *(_DWORD *)(a1 + 320) = (unsigned __int8)bNextId;
    *a3 = 1;
    a3[1] = *(_BYTE *)(a1 + 320);
    *((_WORD *)a3 + 1) = 1280;
    a3[4] = 1;
    *(_DWORD *)a5 = 4;
    *(_BYTE *)(a5 + 4) = *(_BYTE *)(a1 + 320);
    *(_DWORD *)a1 = 1;
    return 0;
  }
  if ( *(_DWORD *)a1 != 3 )
  {
    if ( *(_DWORD *)a1 == 4 )
    {
      if ( a2 )
      {
        v19 = *(_QWORD *)(a1 + 408);
        if ( v19 && *(_DWORD *)(a1 + 416) >= 5u )
        {
          if ( a2[1] == *(_BYTE *)(v19 + 1) )
          {
            if ( *a2 == 2 && a2[4] > 3u )
              *(_DWORD *)(a1 + 36) = (unsigned __int8)a2[4];
            RequestAttributes = MakeRequestAttributes(a1, (__int64)a2);
            if ( !RequestAttributes )
            {
              *(_QWORD *)(a5 + 288) = *(_QWORD *)(a1 + 384);
              *(_DWORD *)a5 = 6;
              *(_DWORD *)a1 = 3;
            }
            return RequestAttributes;
          }
          goto LABEL_14;
        }
        goto LABEL_35;
      }
      goto LABEL_47;
    }
    if ( *(_DWORD *)a1 == 5 )
    {
      if ( a2 )
      {
        v11 = *(_QWORD *)(a1 + 408);
        if ( v11 && *(_DWORD *)(a1 + 416) >= 5u )
        {
          if ( a2[1] != *(_BYTE *)(v11 + 1) )
          {
LABEL_14:
            if ( !v9 )
            {
LABEL_17:
              *(_DWORD *)a5 = 0;
              return 0;
            }
            v12 = L"Id of packet recvd doesn't match one sent";
LABEL_16:
            ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(gRasEapEtwContext, v9, v12);
            goto LABEL_17;
          }
          memset_0((void *)(a5 + 16), 0, 0x110u);
          StringCbCopyNA((STRSAFE_LPSTR)(a5 + 16), 0x110u, (STRSAFE_PCNZCH)(a1 + 44), 0x111u);
          v14 = (const void **)RasAuthAttributeGet(79, *(_QWORD *)(a1 + 392));
          if ( !v14 )
            goto LABEL_34;
          v15 = *(void **)(a1 + 408);
          if ( v15 )
          {
            LocalFree(v15);
            v9 = *((_QWORD *)&xmmword_1800AB2C0 + 1);
            *(_DWORD *)(a1 + 416) = 0;
          }
          if ( *((_DWORD *)v14 + 1) > Size_4 && v9 )
            ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
              gRasEapEtwContext,
              v9,
              L"Need a larger buffer to construct reply");
          v16 = LocalAlloc(0x40u, *((unsigned int *)v14 + 1));
          *(_QWORD *)(a1 + 408) = v16;
          if ( v16 )
          {
            if ( *((_QWORD *)&xmmword_1800AB2C0 + 1) )
              ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
                gRasEapEtwContext,
                *((_QWORD *)&xmmword_1800AB2C0 + 1),
                L"Sending packet to client");
            v17 = *(void **)(a1 + 408);
            *(_DWORD *)(a1 + 416) = *((_DWORD *)v14 + 1);
            memcpy_0(v17, v14[1], *((unsigned int *)v14 + 1));
            memcpy_0(a3, v14[1], *((unsigned int *)v14 + 1));
            v18 = *(_DWORD *)(a1 + 400);
            if ( v18 )
            {
              *(_DWORD *)(a5 + 8) = v18;
LABEL_31:
              *(_DWORD *)a5 = 2;
              return 0;
            }
            if ( *a3 == 3 )
            {
              *(_DWORD *)(a5 + 8) = 0;
              goto LABEL_31;
            }
LABEL_34:
            *(_DWORD *)(a5 + 8) = 691;
            *(_DWORD *)a5 = 1;
            return 0;
          }
          return GetLastError();
        }
LABEL_35:
        if ( v9 )
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
            gRasEapEtwContext,
            v9,
            L"The cached EapSendBufferr is NULL or its size is less than minimum size");
        *(_DWORD *)a5 = 0;
        return 0;
      }
LABEL_47:
      if ( v9 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
          gRasEapEtwContext,
          v9,
          L"Timed out, resending packet to client");
      memcpy_0(a3, *(const void **)(a1 + 408), *(unsigned int *)(a1 + 416));
      *(_DWORD *)a5 = (*(_DWORD *)(a1 + 424) != 0) + 4;
      *(_BYTE *)(a5 + 4) = *(_BYTE *)(a1 + 320);
    }
    return 0;
  }
  if ( !a6 || !*(_DWORD *)(a6 + 104) )
  {
    *(_DWORD *)a5 = 0;
    return 0;
  }
  memset_0((void *)(a5 + 16), 0, 0x110u);
  StringCbCopyNA((STRSAFE_LPSTR)(a5 + 16), 0x110u, (STRSAFE_PCNZCH)(a1 + 44), 0x111u);
  if ( !*(_DWORD *)(a6 + 108) )
  {
    v20 = *(void **)(a1 + 432);
    if ( v20 )
    {
      LocalFree(v20);
      *(_QWORD *)(a1 + 432) = 0;
    }
    v21 = (const void **)RasAuthAttributeGet(24, *(_QWORD *)(a6 + 120));
    v22 = v21;
    if ( v21 )
    {
      v23 = LocalAlloc(0x40u, *((unsigned int *)v21 + 1));
      *(_QWORD *)(a1 + 432) = v23;
      if ( !v23 )
        return GetLastError();
      memcpy_0(v23, v22[1], *((unsigned int *)v22 + 1));
      *(_DWORD *)(a1 + 440) = *((_DWORD *)v22 + 1);
    }
    ConcatString = RasAuthAttributeGetConcatString(79, *(_QWORD *)(a6 + 120), &v44);
    if ( ConcatString )
    {
      v25 = *(void **)(a1 + 408);
      if ( v25 )
      {
        LocalFree(v25);
        *(_DWORD *)(a1 + 416) = 0;
      }
      v26 = RasAuthAttributeGetConcatString(18, *(_QWORD *)(a6 + 120), &Size);
      hMem = v26;
      if ( v26 )
      {
        v27 = Size + 5;
        if ( (_WORD)Size != 0xFFFB && v27 <= Size_4 && (unsigned __int8)(*ConcatString - 3) <= 1u )
        {
          v44 = v27;
          v28 = LocalAlloc(0x40u, v27);
          *(_QWORD *)(a1 + 408) = v28;
          if ( v28 )
          {
            v29 = Size;
            v30 = hMem;
            *(_DWORD *)(a1 + 416) = v27;
            *a3 = 1;
            a3[1] = ++ConcatString[1];
            a3[2] = HIBYTE(v27);
            a3[3] = v27;
            a3[4] = 2;
            memcpy_0(a3 + 5, v30, v29);
            LocalFree(hMem);
            memcpy_0(*(void **)(a1 + 408), a3, v44);
            v31 = *((_QWORD *)&xmmword_1800AB2C0 + 1);
            *(_DWORD *)a5 = 4;
            *(_BYTE *)(a5 + 4) = a3[1];
            *(_DWORD *)(a1 + 424) = 0;
            *(_DWORD *)(a1 + 320) = (unsigned __int8)a3[1];
            *(_DWORD *)a1 = 5;
            *(_QWORD *)(a1 + 392) = *(_QWORD *)(a6 + 120);
            *(_DWORD *)(a1 + 400) = *(_DWORD *)(a6 + 112);
            if ( v31 )
              ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
                gRasEapEtwContext,
                v31,
                L"Sending notification to client");
            return 0;
          }
          LocalFree(hMem);
          goto LABEL_73;
        }
      }
      LocalFree(v26);
      v32 = v44;
      Size = v44;
      if ( (unsigned int)v44 > Size_4 )
      {
        v32 = Size_4;
        if ( *((_QWORD *)&xmmword_1800AB2C0 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
            gRasEapEtwContext,
            *((_QWORD *)&xmmword_1800AB2C0 + 1),
            L"Need a larger buffer to construct reply");
      }
      v33 = LocalAlloc(0x40u, Size);
      *(_QWORD *)(a1 + 408) = v33;
      if ( !v33 )
      {
LABEL_73:
        LocalFree(ConcatString);
        return GetLastError();
      }
      if ( *((_QWORD *)&xmmword_1800AB2C0 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
          gRasEapEtwContext,
          *((_QWORD *)&xmmword_1800AB2C0 + 1),
          L"Sending packet to client");
      v34 = Size;
      v35 = *(void **)(a1 + 408);
      *(_DWORD *)(a1 + 416) = v44;
      memcpy_0(v35, ConcatString, v34);
      memcpy_0(a3, ConcatString, v32);
      v36 = (_DWORD *)(a6 + 112);
    }
    else
    {
      if ( *((_QWORD *)&xmmword_1800AB2C0 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
          gRasEapEtwContext,
          *((_QWORD *)&xmmword_1800AB2C0 + 1),
          L"No EAP Message attribute received, failing auth");
      v36 = (_DWORD *)(a6 + 112);
      if ( !*(_DWORD *)(a6 + 112) )
        *v36 = 691;
    }
    if ( *v36 )
    {
      *(_DWORD *)(a5 + 8) = *v36;
      *(_DWORD *)a5 = (ConcatString != 0) + 1;
    }
    else
    {
      if ( ConcatString )
      {
        if ( *a3 == 3 )
        {
          *(_DWORD *)a5 = 2;
        }
        else
        {
          *(_DWORD *)a5 = 4;
          *(_DWORD *)(a1 + 424) = 0;
          v37 = RasAuthAttributeGet(27, *(_QWORD *)(a6 + 120));
          if ( v37 && v37[2] > 0xAu )
          {
            *(_DWORD *)a5 = 5;
            *(_DWORD *)(a1 + 424) = 1;
          }
          v38 = (unsigned __int8)a3[1];
          *(_DWORD *)(a1 + 320) = v38;
          *(_BYTE *)(a5 + 4) = v38;
          *(_DWORD *)a1 = 4;
        }
      }
      else
      {
        *(_DWORD *)a5 = 1;
      }
      *(_DWORD *)(a5 + 8) = 0;
    }
    LocalFree(ConcatString);
    return 0;
  }
  if ( (_QWORD)xmmword_1800AB2C0 )
  {
    LOWORD(v46) = 0;
    FormatRRASErrorString(&v46, L"Error %d while processing Access-Request");
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(gRasEapEtwContext, xmmword_1800AB2C0, &v46);
  }
  return *(_DWORD *)(a6 + 108);
}

```

## disassembly

```asm
0x180071d0c  push    rbp
0x180071d0e  push    rbx
0x180071d0f  push    rsi
0x180071d10  push    rdi
0x180071d11  push    r12
0x180071d13  push    r13
0x180071d15  push    r14
0x180071d17  push    r15
0x180071d19  lea     rbp, [rsp-758h]
0x180071d21  sub     rsp, 858h
0x180071d28  mov     rax, cs:__security_cookie
0x180071d2f  xor     rax, rsp
0x180071d32  mov     [rbp+790h+var_50], rax
0x180071d39  mov     rsi, [rbp+790h+arg_20]
0x180071d40  xor     ebx, ebx
0x180071d42  mov     r13, [rbp+790h+arg_28]
0x180071d49  mov     r12, r8
0x180071d4c  mov     r15, rdx
0x180071d4f  mov     dword ptr [rsp+890h+Size], ebx
0x180071d53  mov     rdi, rcx
0x180071d56  mov     dword ptr [rsp+890h+var_860], ebx
0x180071d5a  xor     edx, edx; Val
0x180071d5c  mov     [rsp+890h+var_850], ebx
0x180071d60  mov     r8d, 7FCh; Size
0x180071d66  mov     dword ptr [rsp+890h+Size+4], r9d
0x180071d6b  lea     rcx, [rsp+890h+var_84C]; void *
0x180071d70  call    memset_0
0x180071d75  mov     r14, qword ptr cs:xmmword_1800AB2C0+8
0x180071d7c  test    r14, r14
0x180071d7f  jz      short loc_180071DA5
0x180071d81  mov     rcx, cs:gRasEapEtwContext
0x180071d88  lea     r8, aMakeauthentica_0; "MakeAuthenticatorMessage..."
0x180071d8f  mov     rax, cs:gRasEapTemplateFunc
0x180071d96  mov     rdx, r14
0x180071d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071d9e  mov     r14, qword ptr cs:xmmword_1800AB2C0+8
0x180071da5  test    rdi, rdi
0x180071da8  jnz     short loc_180071DB2
0x180071daa  lea     eax, [rdi+57h]
0x180071dad  jmp     loc_180071E4C
0x180071db2  mov     eax, [rdi+24h]
0x180071db5  mov     [rsi+168h], eax
0x180071dbb  mov     ecx, [rdi]
0x180071dbd  mov     [rsp+890h+var_870], ebx
0x180071dc1  test    ecx, ecx
0x180071dc3  jz      loc_1800725B8
0x180071dc9  sub     ecx, 1
0x180071dcc  jz      loc_1800724B6
0x180071dd2  sub     ecx, 2
0x180071dd5  jz      loc_1800720A0
0x180071ddb  sub     ecx, 1
0x180071dde  jz      loc_180071FD8
0x180071de4  cmp     ecx, 1
0x180071de7  jnz     loc_1800720A7
0x180071ded  test    r15, r15
0x180071df0  jz      loc_18007204C
0x180071df6  mov     rax, [rdi+198h]
0x180071dfd  test    rax, rax
0x180071e00  jz      loc_180071FAF
0x180071e06  lea     ebx, [rcx+4]
0x180071e09  cmp     [rdi+1A0h], ebx
0x180071e0f  jb      loc_180071FAD
0x180071e15  mov     al, [rax+1]
0x180071e18  cmp     [r15+1], al
0x180071e1c  jz      short loc_180071E6F
0x180071e1e  test    r14, r14
0x180071e21  jz      short loc_180071E40
0x180071e23  lea     r8, aIdOfPacketRecv; "Id of packet recvd doesn't match one se"...
0x180071e2a  mov     rcx, cs:gRasEapEtwContext
0x180071e31  mov     rdx, r14
0x180071e34  mov     rax, cs:gRasEapTemplateFunc
0x180071e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e40  mov     dword ptr [rsi], 0
0x180071e46  mov     edx, [rsp+890h+var_870]
0x180071e4a  mov     eax, edx
0x180071e4c  mov     rcx, [rbp+790h+var_50]
0x180071e53  xor     rcx, rsp; StackCookie
0x180071e56  call    __security_check_cookie
0x180071e5b  add     rsp, 858h
0x180071e62  pop     r15
0x180071e64  pop     r14
0x180071e66  pop     r13
0x180071e68  pop     r12
0x180071e6a  pop     rdi
0x180071e6b  pop     rsi
0x180071e6c  pop     rbx
0x180071e6d  pop     rbp
0x180071e6e  retn
0x180071e6f  mov     r15d, 110h
0x180071e75  lea     rcx, [rsi+10h]; void *
0x180071e79  mov     r8d, r15d; Size
0x180071e7c  xor     edx, edx; Val
0x180071e7e  call    memset_0
0x180071e83  lea     r8, [rdi+2Ch]; pszSrc
0x180071e87  mov     edx, r15d; cbDest
0x180071e8a  lea     r9d, [r15+1]; cbToCopy
0x180071e8e  lea     rcx, [rsi+10h]; pszDest
0x180071e92  call    StringCbCopyNA
0x180071e97  mov     rdx, [rdi+188h]
0x180071e9e  mov     ecx, 4Fh ; 'O'
0x180071ea3  call    RasAuthAttributeGet
0x180071ea8  mov     rbx, rax
0x180071eab  test    rax, rax
0x180071eae  jz      loc_180071F9B
0x180071eb4  mov     rcx, [rdi+198h]; hMem
0x180071ebb  test    rcx, rcx
0x180071ebe  jz      short loc_180071ED7
0x180071ec0  call    cs:__imp_LocalFree
0x180071ec6  mov     r14, qword ptr cs:xmmword_1800AB2C0+8
0x180071ecd  mov     dword ptr [rdi+1A0h], 0
0x180071ed7  mov     ecx, dword ptr [rsp+890h+Size+4]
0x180071edb  cmp     [rbx+4], ecx
0x180071ede  jbe     short loc_180071F02
0x180071ee0  test    r14, r14
0x180071ee3  jz      short loc_180071F02
0x180071ee5  mov     rcx, cs:gRasEapEtwContext
0x180071eec  lea     r8, aNeedALargerBuf; "Need a larger buffer to construct reply"
0x180071ef3  mov     rax, cs:gRasEapTemplateFunc
0x180071efa  mov     rdx, r14
0x180071efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f02  mov     edx, [rbx+4]; uBytes
0x180071f05  mov     ecx, 40h ; '@'; uFlags
0x180071f0a  call    cs:__imp_LocalAlloc
0x180071f10  mov     [rdi+198h], rax
0x180071f17  test    rax, rax
0x180071f1a  jz      loc_180072179
0x180071f20  mov     rdx, qword ptr cs:xmmword_1800AB2C0+8
0x180071f27  test    rdx, rdx
0x180071f2a  jz      short loc_180071F46
0x180071f2c  mov     rcx, cs:gRasEapEtwContext
0x180071f33  lea     r8, aSendingPacketT; "Sending packet to client"
0x180071f3a  mov     rax, cs:gRasEapTemplateFunc
0x180071f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f46  mov     eax, [rbx+4]
0x180071f49  mov     rcx, [rdi+198h]; void *
0x180071f50  mov     [rdi+1A0h], eax
0x180071f56  mov     r8d, [rbx+4]; Size
0x180071f5a  mov     rdx, [rbx+8]; Src
0x180071f5e  call    memcpy_0
0x180071f63  mov     r8d, [rbx+4]; Size
0x180071f67  mov     rcx, r12; void *
0x180071f6a  mov     rdx, [rbx+8]; Src
0x180071f6e  call    memcpy_0
0x180071f73  mov     eax, [rdi+190h]
0x180071f79  test    eax, eax
0x180071f7b  jz      short loc_180071F8B
0x180071f7d  mov     [rsi+8], eax
0x180071f80  mov     dword ptr [rsi], 2
0x180071f86  jmp     loc_180071E46
0x180071f8b  cmp     byte ptr [r12], 3
0x180071f90  jnz     short loc_180071F9B
0x180071f92  mov     dword ptr [rsi+8], 0
0x180071f99  jmp     short loc_180071F80
0x180071f9b  mov     dword ptr [rsi+8], 2B3h
0x180071fa2  mov     dword ptr [rsi], 1
0x180071fa8  jmp     loc_180071E46
0x180071fad  xor     ebx, ebx
0x180071faf  test    r14, r14
0x180071fb2  jz      short loc_180071FD1
0x180071fb4  mov     rcx, cs:gRasEapEtwContext
0x180071fbb  lea     r8, aTheCachedEapse; "The cached EapSendBufferr is NULL or it"...
0x180071fc2  mov     rax, cs:gRasEapTemplateFunc
0x180071fc9  mov     rdx, r14
0x180071fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071fd1  mov     [rsi], ebx
0x180071fd3  jmp     loc_180071E46
0x180071fd8  test    r15, r15
0x180071fdb  jz      short loc_18007204C
0x180071fdd  mov     rax, [rdi+198h]
0x180071fe4  test    rax, rax
0x180071fe7  jz      short loc_180071FAF
0x180071fe9  mov     ebx, 5
0x180071fee  cmp     [rdi+1A0h], ebx
0x180071ff4  jb      short loc_180071FAD
0x180071ff6  mov     al, [rax+1]
0x180071ff9  cmp     [r15+1], al
0x180071ffd  jnz     loc_180071E1E
0x180072003  cmp     byte ptr [r15], 2
0x180072007  jnz     short loc_180072018
0x180072009  cmp     byte ptr [r15+4], 3
0x18007200e  jbe     short loc_180072018
0x180072010  movzx   eax, byte ptr [r15+4]
0x180072015  mov     [rdi+24h], eax
0x180072018  mov     rdx, r15
0x18007201b  mov     rcx, rdi
0x18007201e  call    MakeRequestAttributes
0x180072023  mov     edx, eax
0x180072025  test    eax, eax
0x180072027  jnz     loc_180071E4A
0x18007202d  mov     rcx, [rdi+180h]
0x180072034  mov     [rsi+120h], rcx
0x18007203b  mov     dword ptr [rsi], 6
0x180072041  mov     dword ptr [rdi], 3
0x180072047  jmp     loc_180071E4A
0x18007204c  test    r14, r14
0x18007204f  jz      short loc_18007206E
0x180072051  mov     rcx, cs:gRasEapEtwContext
0x180072058  lea     r8, aTimedOutResend; "Timed out, resending packet to client"
0x18007205f  mov     rax, cs:gRasEapTemplateFunc
0x180072066  mov     rdx, r14
0x180072069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007206e  mov     r8d, [rdi+1A0h]; Size
0x180072075  mov     rcx, r12; void *
0x180072078  mov     rdx, [rdi+198h]; Src
0x18007207f  call    memcpy_0
0x180072084  mov     eax, [rdi+1A8h]
0x18007208a  neg     eax
0x18007208c  sbb     ecx, ecx
0x18007208e  neg     ecx
0x180072090  add     ecx, 4
0x180072093  mov     [rsi], ecx
0x180072095  mov     al, [rdi+140h]
0x18007209b  mov     [rsi+4], al
0x18007209e  jmp     short loc_1800720A7
0x1800720a0  test    r13, r13
0x1800720a3  jnz     short loc_1800720AE
0x1800720a5  mov     [rsi], ebx
0x1800720a7  mov     edx, ebx
0x1800720a9  jmp     loc_180071E4A
0x1800720ae  cmp     [r13+68h], ebx
0x1800720b2  jz      short loc_1800720A5
0x1800720b4  mov     r15d, 110h
0x1800720ba  lea     rcx, [rsi+10h]; void *
0x1800720be  mov     r8d, r15d; Size
0x1800720c1  xor     edx, edx; Val
0x1800720c3  call    memset_0
0x1800720c8  lea     r8, [rdi+2Ch]; pszSrc
0x1800720cc  mov     edx, r15d; cbDest
0x1800720cf  lea     r9d, [r15+1]; cbToCopy
0x1800720d3  lea     rcx, [rsi+10h]; pszDest
0x1800720d7  call    StringCbCopyNA
0x1800720dc  mov     r8d, [r13+6Ch]
0x1800720e0  xor     r15d, r15d
0x1800720e3  test    r8d, r8d
0x1800720e6  jz      short loc_180072130
0x1800720e8  cmp     qword ptr cs:xmmword_1800AB2C0, r15
0x1800720ef  jz      short loc_180072127
0x1800720f1  lea     rdx, aErrorDWhilePro; "Error %d while processing Access-Reques"...
0x1800720f8  mov     word ptr [rsp+890h+var_850], r15w
0x1800720fe  lea     rcx, [rsp+890h+var_850]
0x180072103  call    FormatRRASErrorString
0x180072108  mov     rdx, qword ptr cs:xmmword_1800AB2C0
0x18007210f  lea     r8, [rsp+890h+var_850]
0x180072114  mov     rcx, cs:gRasEapEtwContext
0x18007211b  mov     rax, cs:gRasEapTemplateFunc
0x180072122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072127  mov     eax, [r13+6Ch]
0x18007212b  jmp     loc_180071E4C
0x180072130  mov     rcx, [rdi+1B0h]; hMem
0x180072137  test    rcx, rcx
0x18007213a  jz      short loc_180072149
0x18007213c  call    cs:__imp_LocalFree
0x180072142  mov     [rdi+1B0h], r15
0x180072149  mov     rdx, [r13+78h]
0x18007214d  mov     ecx, 18h
0x180072152  call    RasAuthAttributeGet
0x180072157  mov     rbx, rax
0x18007215a  test    rax, rax
0x18007215d  jz      short loc_18007219D
0x18007215f  mov     edx, [rax+4]; uBytes
0x180072162  mov     ecx, 40h ; '@'; uFlags
0x180072167  call    cs:__imp_LocalAlloc
0x18007216d  mov     [rdi+1B0h], rax
0x180072174  test    rax, rax
0x180072177  jnz     short loc_180072184
0x180072179  call    cs:__imp_GetLastError
0x18007217f  jmp     loc_180071E4C
0x180072184  mov     r8d, [rbx+4]; Size
0x180072188  mov     rcx, rax; void *
0x18007218b  mov     rdx, [rbx+8]; Src
0x18007218f  call    memcpy_0
0x180072194  mov     eax, [rbx+4]
0x180072197  mov     [rdi+1B8h], eax
0x18007219d  mov     rdx, [r13+78h]
0x1800721a1  lea     r8, [rsp+890h+var_860]
0x1800721a6  mov     ecx, 4Fh ; 'O'
0x1800721ab  call    RasAuthAttributeGetConcatString
0x1800721b0  mov     r14, rax
0x1800721b3  mov     ebx, 5
0x1800721b8  test    rax, rax
0x1800721bb  jz      loc_1800723F3
0x1800721c1  mov     rcx, [rdi+198h]; hMem
0x1800721c8  test    rcx, rcx
0x1800721cb  jz      short loc_1800721DA
0x1800721cd  call    cs:__imp_LocalFree
0x1800721d3  mov     [rdi+1A0h], r15d
0x1800721da  mov     rdx, [r13+78h]
0x1800721de  lea     r8, [rsp+890h+Size]
0x1800721e3  mov     ecx, 12h
0x1800721e8  call    RasAuthAttributeGetConcatString
0x1800721ed  mov     [rsp+890h+hMem], rax
0x1800721f2  test    rax, rax
0x1800721f5  jz      loc_180072334
0x1800721fb  movzx   r15d, word ptr [rsp+890h+Size]
0x180072201  add     r15w, bx
0x180072205  jz      loc_180072334
0x18007220b  movzx   edx, r15w
0x18007220f  cmp     edx, dword ptr [rsp+890h+Size+4]
0x180072213  ja      loc_180072334
0x180072219  mov     cl, [r14]
  ... truncated ...
```
