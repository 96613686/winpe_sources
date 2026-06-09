# PfSiEnumerate

- ea: `0x1800351f4`
- end: `0x180035870`
- name: `PfSiEnumerate`
- size: `1660`
- prototype: `__int64 __fastcall(__int64, char, int)`
- caller_count: `5`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027114`
- `0x18003252c`
- `0x180036818`
- `0x18005ecfc`
- `0x180071db8`

## callees

- `0x180018c4c`
- `0x180023244`
- `0x18002341c`
- `0x1800351f4`
- `0x180035ae0`
- `0x180036818`
- `0x180039f94`
- `0x180061714`
- `0x180073e28`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x1800352f0`
- `ntdll!NtQueryInformationThread` at `0x1800352f0`
- `ntdll!NtDeviceIoControlFile` at `0x180035369`
- `ntdll!NtDeviceIoControlFile` at `0x180035369`
- `ntdll!RtlNtStatusToDosError` at `0x1800355fd`
- `ntdll!RtlNtStatusToDosError` at `0x180035758`
- `ntdll!RtlNtStatusToDosError` at `0x1800355fd`
- `ntdll!RtlNtStatusToDosError` at `0x180035758`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800352ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035308`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035384`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800355a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800352ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035308`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035384`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800355a6`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180035790`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180035857`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180035790`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180035857`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003565f`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003565f`

## pseudocode

```c
__int64 __fastcall PfSiEnumerate(__int64 a1, char a2, int a3)
{
  int v3; // eax
  int v4; // r10d
  __int64 v7; // rdx
  unsigned int v8; // r14d
  HANDLE CurrentThread; // rax
  int v10; // eax
  int v11; // r12d
  HANDLE v12; // rax
  void *v13; // rcx
  int v14; // eax
  int v15; // esi
  int Information; // r15d
  HANDLE v17; // rax
  _QWORD *v18; // rsi
  _QWORD **v19; // rdi
  _QWORD **v20; // rdx
  _DWORD *v21; // rsi
  _QWORD *v22; // rdi
  _QWORD *v23; // rax
  char v24; // r14
  int v25; // r8d
  _QWORD *v26; // r13
  __int64 v27; // r14
  _QWORD **j; // rdx
  unsigned int v29; // ecx
  unsigned int v30; // eax
  ULONG v31; // edi
  HANDLE v32; // rax
  void *v33; // rcx
  unsigned int v34; // edi
  LPVOID v35; // rax
  _QWORD *v36; // r14
  _QWORD **Pointer; // rdi
  PVOID *k; // rdx
  int i; // r9d
  int v40; // r9d
  unsigned int v41; // edi
  PVOID OutputBuffer; // [rsp+40h] [rbp-C0h]
  ULONG OutputBufferLength; // [rsp+48h] [rbp-B8h]
  int ThreadInformation; // [rsp+50h] [rbp-B0h] BYREF
  int v45; // [rsp+54h] [rbp-ACh]
  int v46; // [rsp+58h] [rbp-A8h]
  _QWORD **v47; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v48; // [rsp+68h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+80h] [rbp-80h]
  _DWORD InputBuffer[6]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t pszDest[264]; // [rsp+A0h] [rbp-60h] BYREF

  v3 = *(_DWORD *)(a1 + 276);
  v4 = a3;
  if ( (v3 & 1) != 0 )
    return 1074;
  *(_DWORD *)(a1 + 276) = v3 | 1;
  if ( a2 || (unsigned int)(*(_DWORD *)(a1 + 280) - *(_DWORD *)(a1 + 316)) >= 0x708 )
  {
    v7 = 0;
    *(_DWORD *)(a1 + 316) = *(_DWORD *)(a1 + 280);
    v8 = 0;
    ++*(_WORD *)(a1 + 2LL * a3 + 472);
    if ( (unsigned int)(*(_DWORD *)(a1 + 280) - *(_DWORD *)(a1 + 320)) >= 0xE10 )
    {
      for ( i = 0; i < 3; i = v40 + 1 )
      {
        if ( (unsigned int)PfHpCompactionNeeded(a1 + 80LL * i + 16, v7) )
        {
          LODWORD(v7) = 1;
          goto LABEL_5;
        }
      }
      LODWORD(v7) = 0;
    }
LABEL_5:
    InputBuffer[0] = 15;
    InputBuffer[1] = 3;
    if ( v4 == 4 )
      LODWORD(v7) = 1;
    InputBuffer[2] = 1;
    v45 = v7;
    CurrentThread = GetCurrentThread();
    ThreadInformation = 0;
    v10 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
    if ( v10 < 0 )
    {
      v11 = 8;
      v46 = 8;
      RtlNtStatusToDosError(v10);
    }
    else
    {
      v11 = ThreadInformation;
      v46 = ThreadInformation;
    }
    v12 = GetCurrentThread();
    PfSetPagePriorityThread(v12);
    while ( 1 )
    {
      v13 = *(void **)(a1 + 304);
      OutputBufferLength = *(_DWORD *)(a1 + 272);
      OutputBuffer = *(PVOID *)(a1 + 264);
      IoStatusBlock = 0;
      v14 = NtDeviceIoControlFile(
              v13,
              0,
              0,
              0,
              &IoStatusBlock,
              0x22000Fu,
              InputBuffer,
              0xCu,
              OutputBuffer,
              OutputBufferLength);
      v15 = v14;
      if ( v14 >= 0 )
      {
        Information = IoStatusBlock.Information;
        goto LABEL_12;
      }
      v31 = RtlNtStatusToDosError(v14);
      if ( v31 != 234 )
        break;
      if ( v15 != -2147483643 )
      {
        v31 = 8;
        break;
      }
      v41 = IoStatusBlock.Information;
      v33 = *(void **)(a1 + 264);
      if ( v33 )
      {
        VirtualFree(v33, 0, 0x8000u);
        *(_DWORD *)(a1 + 272) = 0;
      }
      v34 = (v41 >> 3) + v41;
      v35 = VirtualAlloc(0, v34, 0x1000u, 4u);
      *(_QWORD *)(a1 + 264) = v35;
      if ( !v35 )
      {
        v31 = 8;
        goto LABEL_48;
      }
      ++v8;
      *(_DWORD *)(a1 + 272) = v34;
      if ( v8 >= 3 )
      {
        v31 = 7059;
        goto LABEL_48;
      }
    }
    Information = 0;
    if ( v31 )
      goto LABEL_48;
LABEL_12:
    if ( v11 != 8 )
    {
      v17 = GetCurrentThread();
      PfSetPagePriorityThread(v17);
      v46 = 8;
    }
    if ( (*(_BYTE *)(*(_QWORD *)&PfSvcGlobals + 244LL) & 4) != 0 )
    {
      StringCbPrintfW(pszDest, 0x208u, L"%ws\\%ws", *(_QWORD *)&PfSvcGlobals + 888LL, L"SectInfoEnum.trc");
      PfSvWriteBufferEx(pszDest, *(LPCVOID *)(a1 + 264), *(_DWORD *)(*(_QWORD *)(a1 + 264) + 8LL), 0x10000);
    }
    ThreadInformation = 2;
    do
    {
      v18 = *(_QWORD **)(a1 + 8);
      v47 = (_QWORD **)v18;
      v19 = (_QWORD **)v18;
      if ( v18 && (*v18 & 0x8000000000000002uLL) == 0x8000000000000002uLL )
      {
        PfsHashTableCorruptionCallback(a1, 30, &v47);
        v19 = v47;
      }
      if ( !v19 || (v22 = *v19, ((unsigned __int8)v22 & 1) != 0) )
      {
        v20 = (_QWORD **)(v18 + 1);
        v21 = (_DWORD *)(a1 + 4);
        while ( (unsigned __int64)v20 < *(_QWORD *)(a1 + 8) + 8 * ((unsigned __int64)*(unsigned int *)(a1 + 4) >> 5) )
        {
          v22 = *v20;
          if ( ((unsigned __int8)*v20 & 1) == 0 )
          {
            v47 = (_QWORD **)*v20;
            goto LABEL_29;
          }
          ++v20;
        }
      }
      else
      {
        v21 = (_DWORD *)(a1 + 4);
LABEL_29:
        while ( v22 )
        {
          v25 = *v21 >> 5;
          v26 = v22;
          v50 = v22[1] & (-1LL << (*v21 & 0x1F));
          v48 = v22;
          v27 = *(_QWORD *)(a1 + 8)
              + 8LL
              * ((v25 - 1)
               & (HIBYTE(v50)
                + 37
                * (BYTE6(v50)
                 + 37
                 * (BYTE5(v50)
                  + 37
                  * (BYTE4(v50)
                   + 37
                   * (BYTE3(v50)
                    + 37 * (BYTE2(v50) + 37 * (BYTE1(v50) + 37 * ((unsigned int)(unsigned __int8)v50 + 11623883)))))))));
          if ( (*v22 & 0x8000000000000002uLL) == 0x8000000000000002uLL )
          {
            PfsHashTableCorruptionCallback(a1, 30, &v48);
            v22 = v48;
          }
          if ( !v22 || (v22 = (_QWORD *)*v22, ((unsigned __int8)v22 & 1) != 0) )
          {
            for ( j = (_QWORD **)(v27 + 8);
                  (unsigned __int64)j < *(_QWORD *)(a1 + 8) + 8 * ((unsigned __int64)(unsigned int)*v21 >> 5);
                  ++j )
            {
              v22 = *j;
              if ( ((unsigned __int8)*j & 1) == 0 )
              {
                v48 = *j;
                goto LABEL_25;
              }
            }
            v22 = 0;
          }
LABEL_25:
          if ( (v26[2] & 0x3FFFFFF8) == 0 )
          {
            v23 = (_QWORD *)v26[3];
            v24 = 0;
            while ( v23 )
            {
              if ( v22 == v23 )
              {
                v24 = 1;
                break;
              }
              v23 = (_QWORD *)v23[3];
            }
            PfSiEntryFree(a1, v26);
            if ( v24 )
            {
              v36 = *(_QWORD **)(a1 + 8);
              IoStatusBlock.Pointer = v36;
              Pointer = (_QWORD **)v36;
              if ( v36 && (*v36 & 0x8000000000000002uLL) == 0x8000000000000002uLL )
              {
                PfsHashTableCorruptionCallback(a1, 30, &IoStatusBlock);
                Pointer = (_QWORD **)IoStatusBlock.Pointer;
              }
              if ( !Pointer || (v22 = *Pointer, ((unsigned __int8)v22 & 1) != 0) )
              {
                for ( k = (PVOID *)(v36 + 1);
                      (unsigned __int64)k < *(_QWORD *)(a1 + 8) + 8 * ((unsigned __int64)(unsigned int)*v21 >> 5);
                      ++k )
                {
                  v22 = *k;
                  if ( ((unsigned __int8)*k & 1) == 0 )
                  {
                    IoStatusBlock.Pointer = *k;
                    goto LABEL_29;
                  }
                }
                v22 = 0;
              }
            }
          }
        }
      }
      --ThreadInformation;
    }
    while ( ThreadInformation );
    v11 = v46;
    if ( v45 )
      PfSiCompactData(a1);
    PfSiProcessLogBuffer(a1, *(_QWORD *)(a1 + 264) + 16LL);
    v29 = *(_DWORD *)(a1 + 272) - Information;
    v30 = *(_DWORD *)(a1 + 272) >> 2;
    *(_DWORD *)(a1 + 292) = 0;
    if ( v29 > v30 || v29 >= 0x100000 )
    {
      VirtualFree(*(LPVOID *)(a1 + 264), 0, 0x8000u);
      *(_QWORD *)(a1 + 264) = 0;
      *(_DWORD *)(a1 + 272) = 0;
    }
    v31 = 0;
LABEL_48:
    if ( v11 != 8 )
    {
      v32 = GetCurrentThread();
      PfSetPagePriorityThread(v32);
    }
  }
  else
  {
    v31 = 1901;
  }
  *(_DWORD *)(a1 + 276) &= ~1u;
  return v31;
}

```

## disassembly

```asm
0x1800351f4  mov     [rsp-8+arg_8], rbx
0x1800351f9  push    rbp
0x1800351fa  push    rsi
0x1800351fb  push    rdi
0x1800351fc  push    r12
0x1800351fe  push    r13
0x180035200  push    r14
0x180035202  push    r15
0x180035204  lea     rbp, [rsp-1C0h]
0x18003520c  sub     rsp, 2C0h
0x180035213  mov     rax, cs:__security_cookie
0x18003521a  xor     rax, rsp
0x18003521d  mov     [rbp+1F0h+var_40], rax
0x180035224  mov     eax, [rcx+114h]
0x18003522a  mov     r15d, 1
0x180035230  movsxd  r10, r8d
0x180035233  mov     rbx, rcx
0x180035236  test    r15b, al
0x180035239  jz      short loc_18003526A
0x18003523b  mov     eax, 432h
0x180035240  mov     rcx, [rbp+1F0h+var_40]
0x180035247  xor     rcx, rsp; StackCookie
0x18003524a  call    __security_check_cookie
0x18003524f  mov     rbx, [rsp+2F0h+arg_8]
0x180035257  add     rsp, 2C0h
0x18003525e  pop     r15
0x180035260  pop     r14
0x180035262  pop     r13
0x180035264  pop     r12
0x180035266  pop     rdi
0x180035267  pop     rsi
0x180035268  pop     rbp
0x180035269  retn
0x18003526a  or      eax, r15d
0x18003526d  xor     r13d, r13d
0x180035270  mov     [rcx+114h], eax
0x180035276  test    dl, dl
0x180035278  jz      loc_1800356FC
0x18003527e  mov     eax, [rcx+118h]
0x180035284  mov     edx, r13d
0x180035287  mov     [rcx+13Ch], eax
0x18003528d  mov     r14d, r13d
0x180035290  add     [rcx+r10*2+1D8h], r15w
0x180035299  mov     eax, [rcx+118h]
0x18003529f  sub     eax, [rcx+140h]
0x1800352a5  cmp     eax, 0E10h
0x1800352aa  jnb     loc_18003571D
0x1800352b0  cmp     r10d, 4
0x1800352b4  mov     [rbp+1F0h+var_268], 0Fh
0x1800352bb  mov     [rbp+1F0h+var_264], 3
0x1800352c2  cmovz   edx, r15d
0x1800352c6  mov     [rbp+1F0h+var_260], r15d
0x1800352ca  mov     [rsp+2F0h+var_29C], edx
0x1800352ce  call    cs:__imp_GetCurrentThread
0x1800352d4  mov     r9d, 4; ThreadInformationLength
0x1800352da  mov     [rsp+2F0h+ThreadInformation], r13d
0x1800352df  lea     r8, [rsp+2F0h+ThreadInformation]; ThreadInformation
0x1800352e4  mov     [rsp+2F0h+ReturnLength], r13; ReturnLength
0x1800352e9  mov     rcx, rax; ThreadHandle
0x1800352ec  lea     edx, [r9+14h]; ThreadInformationClass
0x1800352f0  call    cs:__imp_NtQueryInformationThread
0x1800352f6  test    eax, eax
0x1800352f8  js      loc_1800355F0
0x1800352fe  mov     r12d, [rsp+2F0h+ThreadInformation]
0x180035303  mov     [rsp+2F0h+var_298], r12d
0x180035308  call    cs:__imp_GetCurrentThread
0x18003530e  mov     rcx, rax; ThreadHandle
0x180035311  mov     edx, r15d
0x180035314  call    PfSetPagePriorityThread
0x180035319  mov     eax, [rbx+110h]
0x18003531f  xorps   xmm0, xmm0
0x180035322  mov     rcx, [rbx+130h]; FileHandle
0x180035329  xor     r9d, r9d; ApcContext
0x18003532c  mov     [rsp+2F0h+OutputBufferLength], eax; OutputBufferLength
0x180035330  xor     r8d, r8d; ApcRoutine
0x180035333  mov     rax, [rbx+108h]
0x18003533a  xor     edx, edx; Event
0x18003533c  mov     [rsp+2F0h+OutputBuffer], rax; OutputBuffer
0x180035341  lea     rax, [rbp+1F0h+var_268]
0x180035345  mov     [rsp+2F0h+InputBufferLength], 0Ch; InputBufferLength
0x18003534d  mov     [rsp+2F0h+InputBuffer], rax; InputBuffer
0x180035352  lea     rax, [rsp+2F0h+IoStatusBlock]
0x180035357  mov     [rsp+2F0h+IoControlCode], 22000Fh; IoControlCode
0x18003535f  mov     [rsp+2F0h+ReturnLength], rax; IoStatusBlock
0x180035364  movups  xmmword ptr [rsp+2F0h+IoStatusBlock], xmm0
0x180035369  call    cs:__imp_NtDeviceIoControlFile
0x18003536f  mov     esi, eax
0x180035371  test    eax, eax
0x180035373  js      loc_180035756
0x180035379  mov     r15d, dword ptr [rsp+2F0h+IoStatusBlock.Information]
0x18003537e  cmp     r12d, 8
0x180035382  jz      short loc_18003539D
0x180035384  call    cs:__imp_GetCurrentThread
0x18003538a  mov     rcx, rax; ThreadHandle
0x18003538d  mov     edx, r12d
0x180035390  call    PfSetPagePriorityThread
0x180035395  mov     [rsp+2F0h+var_298], 8
0x18003539d  mov     r9, cs:PfSvcGlobals
0x1800353a4  test    byte ptr [r9+0F4h], 4
0x1800353ac  jnz     loc_1800357AC
0x1800353b2  mov     [rsp+2F0h+ThreadInformation], 2
0x1800353ba  mov     r12, 8000000000000002h
0x1800353c4  mov     rsi, [rbx+8]
0x1800353c8  mov     [rsp+2F0h+var_290], rsi
0x1800353cd  mov     rdi, rsi
0x1800353d0  test    rsi, rsi
0x1800353d3  jnz     loc_1800355C5
0x1800353d9  test    rdi, rdi
0x1800353dc  jnz     loc_180035608
0x1800353e2  mov     rax, [rbx+8]
0x1800353e6  lea     rdx, [rsi+8]
0x1800353ea  lea     rsi, [rbx+4]
0x1800353ee  mov     ecx, [rsi]
0x1800353f0  shr     rcx, 5
0x1800353f4  lea     r8, [rax+rcx*8]
0x1800353f8  cmp     rdx, r8
0x1800353fb  jnb     loc_180035546
0x180035401  mov     rdi, [rdx]
0x180035404  test    dil, 1
0x180035408  jz      short loc_180035410
0x18003540a  add     rdx, 8
0x18003540e  jmp     short loc_1800353F8
0x180035410  mov     [rsp+2F0h+var_290], rdi
0x180035415  jmp     short loc_180035451
0x180035417  mov     [rsp+2F0h+var_288], rdi
0x18003541c  test    dword ptr [r13+10h], 3FFFFFF8h
0x180035424  jnz     loc_180035833
0x18003542a  mov     rax, [r13+18h]
0x18003542e  xor     r14b, r14b
0x180035431  test    rax, rax
0x180035434  jnz     loc_18003551E
0x18003543a  mov     rdx, r13
0x18003543d  mov     rcx, rbx
0x180035440  call    PfSiEntryFree
0x180035445  xor     r13d, r13d
0x180035448  test    r14b, r14b
0x18003544b  jnz     loc_180035692
0x180035451  test    rdi, rdi
0x180035454  jz      loc_180035546
0x18003545a  mov     r8d, [rsi]
0x18003545d  lea     r9, [rbp+1F0h+var_270]
0x180035461  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035465  mov     ecx, r8d
0x180035468  and     ecx, 1Fh
0x18003546b  shr     r8d, 5
0x18003546f  shl     rax, cl
0x180035472  mov     r13, rdi
0x180035475  and     rax, [rdi+8]
0x180035479  mov     [rbp+1F0h+var_270], rax
0x18003547d  movzx   eax, byte ptr [r9]
0x180035481  add     eax, 0B15DCBh
0x180035486  mov     [rsp+2F0h+var_288], rdi
0x18003548b  imul    ecx, eax, 25h ; '%'
0x18003548e  movzx   eax, byte ptr [r9+1]
0x180035493  add     ecx, eax
0x180035495  movzx   eax, byte ptr [r9+2]
0x18003549a  imul    edx, ecx, 25h ; '%'
0x18003549d  add     edx, eax
0x18003549f  movzx   eax, byte ptr [r9+3]
0x1800354a4  imul    ecx, edx, 25h ; '%'
0x1800354a7  add     ecx, eax
0x1800354a9  movzx   eax, byte ptr [r9+4]
0x1800354ae  imul    edx, ecx, 25h ; '%'
0x1800354b1  add     edx, eax
0x1800354b3  movzx   eax, byte ptr [r9+5]
0x1800354b8  imul    ecx, edx, 25h ; '%'
0x1800354bb  add     ecx, eax
0x1800354bd  movzx   eax, byte ptr [r9+6]
0x1800354c2  imul    edx, ecx, 25h ; '%'
0x1800354c5  add     edx, eax
0x1800354c7  movzx   eax, byte ptr [r9+7]
0x1800354cc  imul    edx, 25h ; '%'
0x1800354cf  add     edx, eax
0x1800354d1  lea     eax, [r8-1]
0x1800354d5  and     rdx, rax
0x1800354d8  mov     rax, [rbx+8]
0x1800354dc  lea     r14, [rax+rdx*8]
0x1800354e0  mov     rax, [rdi]
0x1800354e3  and     rax, r12
0x1800354e6  cmp     rax, r12
0x1800354e9  jz      loc_1800357F3
0x1800354ef  test    rdi, rdi
0x1800354f2  jnz     short loc_180035530
0x1800354f4  mov     ecx, [rsi]
0x1800354f6  lea     rdx, [r14+8]
0x1800354fa  mov     rax, [rbx+8]
0x1800354fe  shr     rcx, 5
0x180035502  lea     r8, [rax+rcx*8]
0x180035506  cmp     rdx, r8
0x180035509  jnb     short loc_18003553F
0x18003550b  mov     rdi, [rdx]
0x18003550e  test    dil, 1
0x180035512  jz      loc_180035417
0x180035518  add     rdx, 8
0x18003551c  jmp     short loc_180035506
0x18003551e  cmp     rdi, rax
0x180035521  jz      loc_18003580F
0x180035527  mov     rax, [rax+18h]
0x18003552b  jmp     loc_180035431
0x180035530  mov     rdi, [rdi]
0x180035533  test    dil, 1
0x180035537  jz      loc_18003541C
0x18003553d  jmp     short loc_1800354F4
0x18003553f  xor     edi, edi
0x180035541  jmp     loc_18003541C
0x180035546  sub     [rsp+2F0h+ThreadInformation], 1
0x18003554b  jnz     loc_1800353C4
0x180035551  mov     r12d, [rsp+2F0h+var_298]
0x180035556  cmp     [rsp+2F0h+var_29C], r13d
0x18003555b  jnz     loc_18003583B
0x180035561  mov     rdx, [rbx+108h]
0x180035568  mov     rcx, rbx
0x18003556b  add     rdx, 10h
0x18003556f  call    PfSiProcessLogBuffer
0x180035574  mov     eax, [rbx+110h]
0x18003557a  mov     ecx, eax
0x18003557c  sub     ecx, r15d
0x18003557f  shr     eax, 2
0x180035582  mov     [rbx+124h], r13d
0x180035589  cmp     ecx, eax
0x18003558b  ja      loc_180035848
0x180035591  cmp     ecx, 100000h
0x180035597  jnb     loc_180035848
0x18003559d  mov     edi, r13d
0x1800355a0  cmp     r12d, 8
0x1800355a4  jz      short loc_1800355B7
0x1800355a6  call    cs:__imp_GetCurrentThread
0x1800355ac  mov     rcx, rax; ThreadHandle
0x1800355af  mov     edx, r12d
0x1800355b2  call    PfSetPagePriorityThread
0x1800355b7  and     dword ptr [rbx+114h], 0FFFFFFFEh
0x1800355be  mov     eax, edi
0x1800355c0  jmp     loc_180035240
0x1800355c5  mov     rax, [rsi]
0x1800355c8  and     rax, r12
0x1800355cb  cmp     rax, r12
0x1800355ce  jnz     loc_1800353D9
0x1800355d4  lea     r8, [rsp+2F0h+var_290]
0x1800355d9  mov     edx, 1Eh
0x1800355de  mov     rcx, rbx
0x1800355e1  call    PfsHashTableCorruptionCallback
0x1800355e6  mov     rdi, [rsp+2F0h+var_290]
0x1800355eb  jmp     loc_1800353D9
0x1800355f0  mov     r12d, 8
0x1800355f6  mov     ecx, eax; Status
0x1800355f8  mov     [rsp+2F0h+var_298], r12d
0x1800355fd  call    cs:__imp_RtlNtStatusToDosError
0x180035603  jmp     loc_180035308
0x180035608  mov     rdi, [rdi]
0x18003560b  test    dil, 1
0x18003560f  jnz     loc_1800353E2
0x180035615  lea     rsi, [rbx+4]
0x180035619  jmp     loc_180035451
0x18003561e  mov     r15d, r13d
0x180035621  test    edi, edi
0x180035623  jz      loc_18003537E
0x180035629  cmp     edi, eax
0x18003562b  jnz     loc_1800355A0
0x180035631  mov     edi, r13d
0x180035634  mov     r15d, 1
0x18003563a  mov     rcx, [rbx+108h]; lpAddress
0x180035641  test    rcx, rcx
0x180035644  jnz     loc_180035788
0x18003564a  mov     eax, edi
0x18003564c  xor     ecx, ecx; lpAddress
0x18003564e  shr     eax, 3
0x180035651  mov     r8d, 1000h; flAllocationType
0x180035657  add     edi, eax
0x180035659  mov     edx, edi; dwSize
0x18003565b  lea     r9d, [rcx+4]; flProtect
0x18003565f  call    cs:__imp_VirtualAlloc
0x180035665  mov     [rbx+108h], rax
0x18003566c  test    rax, rax
0x18003566f  jz      loc_1800357A2
0x180035675  add     r14d, r15d
0x180035678  mov     [rbx+110h], edi
0x18003567e  cmp     r14d, 3
0x180035682  jb      loc_180035319
0x180035688  mov     edi, 1B93h
0x18003568d  jmp     loc_1800355A0
0x180035692  mov     r14, [rbx+8]
0x180035696  mov     qword ptr [rsp+2F0h+IoStatusBlock], r14
0x18003569b  mov     rdi, r14
0x18003569e  test    r14, r14
0x1800356a1  jz      short loc_1800356B2
0x1800356a3  mov     rax, [r14]
0x1800356a6  and     rax, r12
0x1800356a9  cmp     rax, r12
0x1800356ac  jz      loc_180035817
0x1800356b2  test    rdi, rdi
0x1800356b5  jz      short loc_1800356C4
0x1800356b7  mov     rdi, [rdi]
0x1800356ba  test    dil, 1
0x1800356be  jz      loc_180035451
0x1800356c4  mov     ecx, [rsi]
0x1800356c6  lea     rdx, [r14+8]
0x1800356ca  mov     rax, [rbx+8]
0x1800356ce  shr     rcx, 5
0x1800356d2  lea     r8, [rax+rcx*8]
0x1800356d6  cmp     rdx, r8
  ... truncated ...
```
