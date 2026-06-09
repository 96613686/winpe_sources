# ConvertIpAddressToFilterDescriptor

- ea: `0x180063be4`
- end: `0x180063dde`
- name: `ConvertIpAddressToFilterDescriptor`
- size: `506`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180066084`

## callees

- `0x180063be4`
- `0x180075c80`
- `0x180075eec`
- `0x180075f5c`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063c3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063c3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063d96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063d9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063d96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063d9f`
- `rtutils!TracePrintfExA` at `0x180063d4c`
- `rtutils!TracePrintfExA` at `0x180063d4c`

## string_xrefs

- `0x180063cf5`: `MprInfoCreate failed  in ConvertIpAddressToFilterDescriptor and returned %d`
- `0x180063d40`: `MprInfoCreate failed  in ConvertIpAddressToFilterDescriptor and returned %d`

## pseudocode

```c
__int64 __fastcall ConvertIpAddressToFilterDescriptor(HLOCAL *a1, unsigned int a2)
{
  unsigned int v2; // esi
  BYTE *lpItemData; // rdi
  HLOCAL v6; // rcx
  unsigned int v7; // r11d
  __int64 v8; // r10
  __int64 v9; // rax
  __int64 v10; // r9
  int v11; // edx
  DWORD v12; // eax
  DWORD v13; // ebx
  int v14; // r8d
  void *v15; // rsi
  LPVOID lpNewHeader; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lplpNewHeader; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  char v20[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v2 = a2 - 1;
  lpNewHeader = 0;
  lplpNewHeader = 0;
  lpItemData = (BYTE *)LocalAlloc(0x40u, 28LL * (a2 - 1) + 40);
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v7 = 0;
  if ( a2 )
  {
    v8 = 0;
    do
    {
      v6 = *a1;
      v9 = 4 * v7;
      v10 = 28 * v8;
      ++v7;
      ++v8;
      v11 = (*((unsigned __int8 *)*a1 + v9 + 3) << 16)
          | ((*((unsigned __int8 *)*a1 + v9 + 2) | (*((unsigned __int8 *)*a1 + v9 + 4) << 16)) << 8);
      LODWORD(v9) = *((unsigned __int8 *)*a1 + v9 + 1);
      *(_DWORD *)&lpItemData[v10 + 32] |= 0x11u;
      *(_DWORD *)&lpItemData[v10 + 20] = v9 | v11;
      *(_DWORD *)&lpItemData[v10 + 24] = -1;
    }
    while ( v7 < a2 );
  }
  *((_DWORD *)lpItemData + 2) = 1;
  *(_DWORD *)lpItemData = 1;
  *((_DWORD *)lpItemData + 1) = a2;
  v12 = MprInfoCreate((DWORD)v6, &lpNewHeader);
  v13 = v12;
  if ( v12 )
  {
    if ( gIsProtocolCommonTracingEnabled )
    {
      if ( *((_QWORD *)&xmmword_1800AB3E0 + 1) )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v19, L"MprInfoCreate failed  in ConvertIpAddressToFilterDescriptor and returned %d", v12);
        ((void (__fastcall *)(__int64, _QWORD, int *))gProtocolCommonTemplateFunc)(
          gProtocolCommonEtwContext,
          *((_QWORD *)&xmmword_1800AB3E0 + 1),
          &v19);
      }
    }
    else if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "MprInfoCreate failed  in ConvertIpAddressToFilterDescriptor and returned %d",
        v12);
    }
  }
  else
  {
    v14 = 28 * v2;
    v15 = lpNewHeader;
    v13 = MprInfoBlockAdd(lpNewHeader, 0xFFFF0001, v14 + 40, 1u, lpItemData, &lplpNewHeader);
    if ( v13 )
    {
      MprInfoDelete(v15);
    }
    else
    {
      LocalFree(*a1);
      LocalFree(lpItemData);
      MprInfoDelete(v15);
      *a1 = lplpNewHeader;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180063be4  mov     [rsp-8+arg_10], rbx
0x180063be9  mov     [rsp-8+arg_18], rsi
0x180063bee  push    rbp
0x180063bef  push    rdi
0x180063bf0  push    r14
0x180063bf2  lea     rbp, [rsp-750h]
0x180063bfa  sub     rsp, 850h
0x180063c01  mov     rax, cs:__security_cookie
0x180063c08  xor     rax, rsp
0x180063c0b  mov     [rbp+760h+var_20], rax
0x180063c12  lea     esi, [rdx-1]
0x180063c15  mov     [rsp+860h+lpNewHeader], 0
0x180063c1e  mov     ebx, edx
0x180063c20  mov     eax, esi
0x180063c22  imul    rdx, rax, 1Ch
0x180063c26  mov     r14, rcx
0x180063c29  mov     [rsp+860h+var_828], 0
0x180063c32  add     rdx, 28h ; '('; uBytes
0x180063c36  mov     ecx, 40h ; '@'; uFlags
0x180063c3b  call    cs:__imp_LocalAlloc
0x180063c41  xor     edx, edx; Val
0x180063c43  lea     rcx, [rsp+860h+var_81C]; void *
0x180063c48  mov     rdi, rax
0x180063c4b  mov     r8d, 7FCh; Size
0x180063c51  xor     eax, eax
0x180063c53  mov     [rsp+860h+var_820], eax
0x180063c57  call    memset_0
0x180063c5c  xor     r11d, r11d
0x180063c5f  test    ebx, ebx
0x180063c61  jz      short loc_180063CBC
0x180063c63  xor     r10d, r10d
0x180063c66  mov     rcx, [r14]; dwVersion
0x180063c69  lea     eax, ds:0[r11*4]
0x180063c71  imul    r9, r10, 1Ch
0x180063c75  mov     r8d, eax
0x180063c78  inc     r11d
0x180063c7b  movzx   edx, byte ptr [rax+rcx+4]
0x180063c80  inc     r10
0x180063c83  movzx   eax, byte ptr [rax+rcx+2]
0x180063c88  shl     edx, 10h
0x180063c8b  or      edx, eax
0x180063c8d  movzx   eax, byte ptr [r8+rcx+3]
0x180063c93  shl     edx, 8
0x180063c96  shl     eax, 10h
0x180063c99  or      edx, eax
0x180063c9b  movzx   eax, byte ptr [r8+rcx+1]
0x180063ca1  or      dword ptr [r9+rdi+20h], 11h
0x180063ca7  or      edx, eax
0x180063ca9  mov     [r9+rdi+14h], edx
0x180063cae  mov     dword ptr [r9+rdi+18h], 0FFFFFFFFh
0x180063cb7  cmp     r11d, ebx
0x180063cba  jb      short loc_180063C66
0x180063cbc  lea     rdx, [rsp+860h+lpNewHeader]; lplpNewHeader
0x180063cc1  mov     dword ptr [rdi+8], 1
0x180063cc8  mov     dword ptr [rdi], 1
0x180063cce  mov     [rdi+4], ebx
0x180063cd1  call    MprInfoCreate
0x180063cd6  mov     ebx, eax
0x180063cd8  test    eax, eax
0x180063cda  jz      short loc_180063D54
0x180063cdc  cmp     cs:gIsProtocolCommonTracingEnabled, 0
0x180063ce3  jz      short loc_180063D32
0x180063ce5  cmp     qword ptr cs:xmmword_1800AB3E0+8, 0
0x180063ced  jz      loc_180063DB5
0x180063cf3  xor     ecx, ecx
0x180063cf5  lea     rdx, aMprinfocreateF_0; "MprInfoCreate failed  in ConvertIpAddre"...
0x180063cfc  mov     word ptr [rsp+860h+var_820], cx
0x180063d01  mov     r8d, eax
0x180063d04  lea     rcx, [rsp+860h+var_820]
0x180063d09  call    FormatRRASErrorString
0x180063d0e  mov     rdx, qword ptr cs:xmmword_1800AB3E0+8
0x180063d15  lea     r8, [rsp+860h+var_820]
0x180063d1a  mov     rcx, cs:gProtocolCommonEtwContext
0x180063d21  mov     rax, cs:gProtocolCommonTemplateFunc
0x180063d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d2d  jmp     loc_180063DB5
0x180063d32  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180063d38  cmp     ecx, 0FFFFFFFFh
0x180063d3b  jz      short loc_180063DB5
0x180063d3d  mov     r9d, eax
0x180063d40  lea     r8, szFormat; "MprInfoCreate failed  in ConvertIpAddre"...
0x180063d47  mov     edx, 0Ch; dwFlags
0x180063d4c  call    cs:__imp_TracePrintfExA
0x180063d52  jmp     short loc_180063DB5
0x180063d54  imul    r8d, esi, 1Ch
0x180063d58  lea     rax, [rsp+860h+var_828]
0x180063d5d  mov     rsi, [rsp+860h+lpNewHeader]
0x180063d62  mov     edx, 0FFFF0001h; dwInfoType
0x180063d67  mov     [rsp+860h+lplpNewHeader], rax; lplpNewHeader
0x180063d6c  mov     r9d, 1; dwItemCount
0x180063d72  mov     rcx, rsi; lpHeader
0x180063d75  mov     [rsp+860h+lpItemData], rdi; lpItemData
0x180063d7a  add     r8d, 28h ; '('; dwItemSize
0x180063d7e  call    MprInfoBlockAdd
0x180063d83  mov     ebx, eax
0x180063d85  test    eax, eax
0x180063d87  jz      short loc_180063D93
0x180063d89  mov     rcx, rsi; lpHeader
0x180063d8c  call    MprInfoDelete
0x180063d91  jmp     short loc_180063DB5
0x180063d93  mov     rcx, [r14]; hMem
0x180063d96  call    cs:__imp_LocalFree
0x180063d9c  mov     rcx, rdi; hMem
0x180063d9f  call    cs:__imp_LocalFree
0x180063da5  mov     rcx, rsi; lpHeader
0x180063da8  call    MprInfoDelete
0x180063dad  mov     rax, [rsp+860h+var_828]
0x180063db2  mov     [r14], rax
0x180063db5  mov     eax, ebx
0x180063db7  mov     rcx, [rbp+760h+var_20]
0x180063dbe  xor     rcx, rsp; StackCookie
0x180063dc1  call    __security_check_cookie
0x180063dc6  lea     r11, [rsp+860h+var_10]
0x180063dce  mov     rbx, [r11+30h]
0x180063dd2  mov     rsi, [r11+38h]
0x180063dd6  mov     rsp, r11
0x180063dd9  pop     r14
0x180063ddb  pop     rdi
0x180063ddc  pop     rbp
0x180063ddd  retn
```
