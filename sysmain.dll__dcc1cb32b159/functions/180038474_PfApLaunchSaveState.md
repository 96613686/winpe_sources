# PfApLaunchSaveState

- ea: `0x180038474`
- end: `0x180038753`
- name: `PfApLaunchSaveState`
- size: `735`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003b118`
- `0x180057710`

## callees

- `0x180023480`
- `0x180038474`
- `0x18003875c`
- `0x180039f94`
- `0x18006d124`
- `0x180073e28`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800386bb`
- `ntdll!RtlNtStatusToDosError` at `0x1800386bb`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003872b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003872b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800386c9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800386c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038715`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038715`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800384e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800384e3`

## pseudocode

```c
__int64 __fastcall PfApLaunchSaveState(__int64 a1)
{
  __int64 v1; // rsi
  void *v2; // rbx
  bool v3; // cc
  unsigned int v4; // edi
  _DWORD *v5; // rax
  _DWORD *v6; // r14
  char *v7; // r15
  __int64 *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  _WORD *v11; // rax
  __int64 v12; // rcx
  _WORD *v13; // r9
  _WORD *v14; // rcx
  NTSTATUS v15; // eax
  __int64 v16; // r13
  ULONG v17; // eax
  DWORD LengthSid; // eax
  unsigned int SidHash; // eax
  ULONG v21; // [rsp+30h] [rbp-A9h]
  __int64 v22[2]; // [rsp+38h] [rbp-A1h] BYREF
  void *v23; // [rsp+48h] [rbp-91h]
  __int64 v24; // [rsp+50h] [rbp-89h]
  wchar_t pszDest[64]; // [rsp+60h] [rbp-79h] BYREF

  v24 = a1;
  v1 = a1 + 88;
  v2 = 0;
  v3 = *(_DWORD *)(a1 + 88) <= 0x5D1745u;
  v23 = 0;
  if ( v3 )
  {
    v21 = 352 * *(_DWORD *)v1 + 8;
    v5 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v21);
    v6 = v5;
    if ( v5 )
    {
      memset_0(v5, 0, v21);
      *v6 = 5;
      v7 = (char *)(v6 + 2);
      v6[1] = *(_DWORD *)v1;
      v8 = *(__int64 **)(v1 + 8);
      v9 = (__int64)v8;
      while ( 1 )
      {
        v22[0] = v9;
        if ( !v9 )
          break;
        if ( (*(_QWORD *)v9 & 0x8000000000000002uLL) == 0x8000000000000002uLL )
        {
          PfsHashTableCorruptionCallback(v1, 30, v22);
          v9 = v22[0];
        }
        if ( !v9 )
          break;
        v9 = *(_QWORD *)v9;
        if ( (v9 & 1) != 0 )
          break;
LABEL_16:
        if ( !v9 )
          goto LABEL_24;
        v10 = 130;
        *((_QWORD *)v7 + 33) = *(_QWORD *)(v9 + 24);
        *((_DWORD *)v7 + 85) = *(_DWORD *)(v9 + 8);
        *((_WORD *)v7 + 168) = *(_WORD *)(v9 + 104);
        *((_WORD *)v7 + 169) = *(_WORD *)(v9 + 106);
        v11 = v7;
        *((_DWORD *)v7 + 86) ^= ((unsigned __int8)*((_DWORD *)v7 + 86) ^ *(_BYTE *)(v9 + 37)) & 1;
        v12 = 2147483646;
        v13 = *(_WORD **)(v9 + 16);
        do
        {
          if ( !v12 )
            break;
          if ( !*v13 )
            break;
          *v11++ = *v13++;
          --v12;
          --v10;
        }
        while ( v10 );
        v14 = v11 - 1;
        if ( v10 )
          v14 = v11;
        *v14 = 0;
        *((_OWORD *)v7 + 17) = *(_OWORD *)(v9 + 40);
        *((_OWORD *)v7 + 18) = *(_OWORD *)(v9 + 56);
        *((_OWORD *)v7 + 19) = *(_OWORD *)(v9 + 72);
        *((_OWORD *)v7 + 20) = *(_OWORD *)(v9 + 88);
        v7 += 352;
      }
      for ( ++v8; (unsigned __int64)v8 < *(_QWORD *)(v1 + 8) + 8 * ((unsigned __int64)*(unsigned int *)(v1 + 4) >> 5); ++v8 )
      {
        v9 = *v8;
        if ( (*v8 & 1) == 0 )
        {
          v22[0] = *v8;
          goto LABEL_16;
        }
      }
LABEL_24:
      v22[0] = (__int64)PfsCompressAlloc;
      v22[1] = (__int64)PfsCompressFree;
      v15 = SmCompressBuffer((PUCHAR)v6, v21, (__int64)v22, 0x10000);
      v2 = v23;
      v16 = v24;
      if ( v15 >= 0 || (v17 = RtlNtStatusToDosError(v15)) == 0 )
      {
        LengthSid = GetLengthSid(*(PSID *)(v16 + 72));
        SidHash = PfsGetSidHash(*(_QWORD *)(v16 + 72), LengthSid);
        StringCbPrintfW(pszDest, 0x80u, L"ApLaunch_%08lx", SidHash);
        v17 = PfApRegValueSet(pszDest, v2, v21);
      }
      v4 = v17;
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v6);
    }
    else
    {
      v4 = 8;
    }
    if ( v2 )
      VirtualFree(v2, 0, 0x8000u);
  }
  else
  {
    return 111;
  }
  return v4;
}

```

## disassembly

```asm
0x180038474  push    rbp
0x180038476  push    rbx
0x180038477  push    rsi
0x180038478  push    rdi
0x180038479  push    r12
0x18003847b  push    r13
0x18003847d  push    r14
0x18003847f  push    r15
0x180038481  lea     rbp, [rsp-1Fh]
0x180038486  sub     rsp, 0F8h
0x18003848d  mov     rax, cs:__security_cookie
0x180038494  xor     rax, rsp
0x180038497  mov     [rbp+57h+var_50], rax
0x18003849b  xor     r15d, r15d
0x18003849e  mov     [rsp+130h+var_E0], rcx
0x1800384a3  lea     rsi, [rcx+58h]
0x1800384a7  mov     ebx, r15d
0x1800384aa  cmp     dword ptr [rsi], 5D1745h
0x1800384b0  mov     [rsp+130h+var_E8], rbx
0x1800384b5  jbe     short loc_1800384C0
0x1800384b7  lea     edi, [r15+6Fh]
0x1800384bb  jmp     loc_180038731
0x1800384c0  imul    r12d, [rsi], 160h
0x1800384c7  xor     edx, edx; dwFlags
0x1800384c9  mov     rcx, cs:PfSvcGlobals
0x1800384d0  mov     rcx, [rcx+58h]; hHeap
0x1800384d4  add     r12d, 8
0x1800384d8  mov     r8d, r12d; dwBytes
0x1800384db  mov     [rsp+130h+var_100], r12d
0x1800384e0  mov     edi, r12d
0x1800384e3  call    cs:__imp_HeapAlloc
0x1800384e9  mov     r14, rax
0x1800384ec  test    rax, rax
0x1800384ef  jnz     short loc_1800384F9
0x1800384f1  lea     edi, [rax+8]
0x1800384f4  jmp     loc_18003871B
0x1800384f9  mov     r8, rdi; Size
0x1800384fc  xor     edx, edx; Val
0x1800384fe  mov     rcx, r14; void *
0x180038501  call    memset_0
0x180038506  mov     dword ptr [r14], 5
0x18003850d  lea     r15, [r14+8]
0x180038511  mov     eax, [rsi]
0x180038513  mov     edi, 8
0x180038518  mov     [r14+4], eax
0x18003851c  mov     r13, 8000000000000002h
0x180038526  mov     rbx, [rsi+8]
0x18003852a  xor     r11d, r11d
0x18003852d  mov     rdx, rbx
0x180038530  mov     [rsp+130h+var_F8], rdx
0x180038535  test    rdx, rdx
0x180038538  jz      short loc_18003856C
0x18003853a  mov     rax, [rdx]
0x18003853d  and     rax, r13
0x180038540  cmp     rax, r13
0x180038543  jnz     short loc_18003855F
0x180038545  lea     r8, [rsp+130h+var_F8]
0x18003854a  mov     edx, 1Eh
0x18003854f  mov     rcx, rsi
0x180038552  call    PfsHashTableCorruptionCallback
0x180038557  mov     rdx, [rsp+130h+var_F8]
0x18003855c  xor     r11d, r11d
0x18003855f  test    rdx, rdx
0x180038562  jz      short loc_18003856C
0x180038564  mov     rdx, [rdx]
0x180038567  test    dl, 1
0x18003856a  jz      short loc_180038599
0x18003856c  mov     ecx, [rsi+4]
0x18003856f  add     rbx, rdi
0x180038572  mov     rax, [rsi+8]
0x180038576  shr     rcx, 5
0x18003857a  lea     r8, [rax+rcx*8]
0x18003857e  cmp     rbx, r8
0x180038581  jnb     loc_18003866C
0x180038587  mov     rdx, [rbx]
0x18003858a  test    dl, 1
0x18003858d  jz      short loc_180038594
0x18003858f  add     rbx, rdi
0x180038592  jmp     short loc_18003857E
0x180038594  mov     [rsp+130h+var_F8], rdx
0x180038599  mov     rax, rdx
0x18003859c  test    rax, rax
0x18003859f  jz      loc_18003866C
0x1800385a5  mov     rax, [rdx+18h]
0x1800385a9  mov     r8d, 82h
0x1800385af  mov     [r15+108h], rax
0x1800385b6  mov     eax, [rdx+8]
0x1800385b9  mov     [r15+154h], eax
0x1800385c0  movzx   eax, word ptr [rdx+68h]
0x1800385c4  mov     [r15+150h], ax
0x1800385cc  movzx   eax, word ptr [rdx+6Ah]
0x1800385d0  mov     [r15+152h], ax
0x1800385d8  mov     eax, [r15+158h]
0x1800385df  movzx   ecx, byte ptr [rdx+25h]
0x1800385e3  xor     ecx, eax
0x1800385e5  and     ecx, 1
0x1800385e8  xor     ecx, eax
0x1800385ea  mov     rax, r15
0x1800385ed  mov     [r15+158h], ecx
0x1800385f4  mov     ecx, 7FFFFFFEh
0x1800385f9  mov     r9, [rdx+10h]
0x1800385fd  test    rcx, rcx
0x180038600  jz      short loc_180038621
0x180038602  movzx   r10d, word ptr [r9]
0x180038606  test    r10w, r10w
0x18003860a  jz      short loc_180038621
0x18003860c  mov     [rax], r10w
0x180038610  add     r9, 2
0x180038614  add     rax, 2
0x180038618  dec     rcx
0x18003861b  sub     r8, 1
0x18003861f  jnz     short loc_1800385FD
0x180038621  test    r8, r8
0x180038624  lea     rcx, [rax-2]
0x180038628  cmovnz  rcx, rax
0x18003862c  mov     [rcx], r11w
0x180038630  movups  xmm0, xmmword ptr [rdx+28h]
0x180038634  movups  xmmword ptr [r15+110h], xmm0
0x18003863c  movups  xmm1, xmmword ptr [rdx+38h]
0x180038640  movups  xmmword ptr [r15+120h], xmm1
0x180038648  movups  xmm0, xmmword ptr [rdx+48h]
0x18003864c  movups  xmmword ptr [r15+130h], xmm0
0x180038654  movups  xmm1, xmmword ptr [rdx+58h]
0x180038658  movups  xmmword ptr [r15+140h], xmm1
0x180038660  add     r15, 160h
0x180038667  jmp     loc_180038530
0x18003866c  lea     rax, PfsCompressAlloc
0x180038673  mov     [rsp+130h+var_108], 10000h; int
0x18003867b  mov     [rsp+130h+var_F8], rax
0x180038680  lea     r9, [rsp+130h+var_100]
0x180038685  lea     rax, PfsCompressFree
0x18003868c  mov     edx, r12d; UncompressedBufferSize
0x18003868f  mov     [rsp+130h+var_F0], rax
0x180038694  lea     r8, [rsp+130h+var_E8]
0x180038699  lea     rax, [rsp+130h+var_F8]
0x18003869e  mov     rcx, r14; UncompressedBuffer
0x1800386a1  mov     [rsp+130h+var_110], rax; __int64
0x1800386a6  call    SmCompressBuffer
0x1800386ab  mov     rbx, [rsp+130h+var_E8]
0x1800386b0  mov     r13, [rsp+130h+var_E0]
0x1800386b5  test    eax, eax
0x1800386b7  jns     short loc_1800386C5
0x1800386b9  mov     ecx, eax; Status
0x1800386bb  call    cs:__imp_RtlNtStatusToDosError
0x1800386c1  test    eax, eax
0x1800386c3  jnz     short loc_180038703
0x1800386c5  mov     rcx, [r13+48h]; pSid
0x1800386c9  call    cs:__imp_GetLengthSid
0x1800386cf  mov     rcx, [r13+48h]
0x1800386d3  mov     edx, eax
0x1800386d5  call    PfsGetSidHash
0x1800386da  mov     r9d, eax
0x1800386dd  lea     r8, aAplaunch08lx; "ApLaunch_%08lx"
0x1800386e4  mov     edx, 80h; cbDest
0x1800386e9  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1800386ed  call    StringCbPrintfW
0x1800386f2  mov     r8d, [rsp+130h+var_100]
0x1800386f7  lea     rcx, [rbp+57h+pszDest]
0x1800386fb  mov     rdx, rbx
0x1800386fe  call    PfApRegValueSet
0x180038703  mov     rcx, cs:PfSvcGlobals
0x18003870a  mov     r8, r14; lpMem
0x18003870d  xor     edx, edx; dwFlags
0x18003870f  mov     edi, eax
0x180038711  mov     rcx, [rcx+58h]; hHeap
0x180038715  call    cs:__imp_HeapFree
0x18003871b  test    rbx, rbx
0x18003871e  jz      short loc_180038731
0x180038720  xor     edx, edx; dwSize
0x180038722  mov     r8d, 8000h; dwFreeType
0x180038728  mov     rcx, rbx; lpAddress
0x18003872b  call    cs:__imp_VirtualFree
0x180038731  mov     eax, edi
0x180038733  mov     rcx, [rbp+57h+var_50]
0x180038737  xor     rcx, rsp; StackCookie
0x18003873a  call    __security_check_cookie
0x18003873f  add     rsp, 0F8h
0x180038746  pop     r15
0x180038748  pop     r14
0x18003874a  pop     r13
0x18003874c  pop     r12
0x18003874e  pop     rdi
0x18003874f  pop     rsi
0x180038750  pop     rbx
0x180038751  pop     rbp
0x180038752  retn
```
