# ConvertProcessInfoFromUnicodeToAnsi

- ea: `0x180002500`
- end: `0x18000276e`
- name: `ConvertProcessInfoFromUnicodeToAnsi`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002450`

## callees

- `0x180002500`
- `0x180007c30`
- `0x180015582`
- `0x18001558e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002723`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002737`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000274f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002763`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002723`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002737`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000274f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002763`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002588`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002612`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002669`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002588`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002612`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002669`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180002643`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180002643`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000265a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000265a`

## pseudocode

```c
__int64 __fastcall ConvertProcessInfoFromUnicodeToAnsi(__int64 a1, PVOID *a2, _DWORD *a3, ULONG *a4)
{
  WTS_TYPE_CLASS v4; // ebp
  ULONG v8; // ecx
  unsigned int v9; // r13d
  unsigned int v10; // edi
  HLOCAL v11; // rax
  char *v12; // rdi
  ULONG i; // r15d
  _WORD *v14; // rax
  __int64 v15; // rcx
  ULONG UnicodeSize; // esi
  int v17; // eax
  DWORD v18; // ecx
  HLOCAL v19; // rax
  void *v20; // rcx
  DWORD LengthSid; // esi
  HLOCAL v22; // rax

  v4 = WTSTypeProcessInfoLevel0;
  if ( !a2 || !a4 || !a3 )
    goto LABEL_35;
  *a2 = 0;
  v8 = *a4;
  if ( !*a4 )
    return 1;
  if ( !a1 )
    goto LABEL_35;
  if ( *a3 )
  {
    if ( *a3 != 1 )
    {
LABEL_35:
      SetLastError(0x57u);
      goto LABEL_28;
    }
    v4 = WTSTypeProcessInfoLevel1;
    v9 = 64;
  }
  else
  {
    v9 = 24;
  }
  v10 = v9 * v8;
  v11 = LocalAlloc(0x40u, v9 * v8);
  *a2 = v11;
  if ( v11 )
  {
    memset_0(v11, 0, v10);
    v12 = (char *)*a2;
    if ( *a2 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= *a4 )
          return 1;
        v14 = *(_WORD **)(a1 + 8);
        if ( !v14 )
          break;
        v15 = 261;
        while ( *v14 )
        {
          ++v14;
          if ( !--v15 )
          {
            UnicodeSize = 0;
            v17 = -2147024809;
            goto LABEL_19;
          }
        }
        UnicodeSize = 261 - v15;
        v17 = 0;
LABEL_19:
        LOWORD(v18) = v17;
        if ( v17 < 0 )
          goto LABEL_38;
        v19 = LocalAlloc(0x40u, UnicodeSize + 1);
        *((_QWORD *)v12 + 1) = v19;
        if ( !v19 )
          goto LABEL_28;
        memset_0(v19, 0, UnicodeSize + 1);
        if ( RtlUnicodeToMultiByteN(*((PCHAR *)v12 + 1), UnicodeSize + 1, 0, *(PCWCH *)(a1 + 8), UnicodeSize) )
        {
          v18 = 0;
          goto LABEL_39;
        }
        v20 = *(void **)(a1 + 16);
        if ( v20 )
        {
          LengthSid = GetLengthSid(v20);
          v22 = LocalAlloc(0x40u, LengthSid);
          *((_QWORD *)v12 + 2) = v22;
          if ( !v22 )
            goto LABEL_28;
          memcpy_0(v22, *(const void **)(a1 + 16), LengthSid);
        }
        *(_DWORD *)v12 = *(_DWORD *)a1;
        *((_DWORD *)v12 + 1) = *(_DWORD *)(a1 + 4);
        if ( *a3 == 1 )
        {
          *((_DWORD *)v12 + 6) = *(_DWORD *)(a1 + 24);
          *((_DWORD *)v12 + 7) = *(_DWORD *)(a1 + 28);
          *((_DWORD *)v12 + 8) = *(_DWORD *)(a1 + 32);
          *((_DWORD *)v12 + 9) = *(_DWORD *)(a1 + 36);
          *((_DWORD *)v12 + 10) = *(_DWORD *)(a1 + 40);
          *((_DWORD *)v12 + 11) = *(_DWORD *)(a1 + 44);
          *((_QWORD *)v12 + 6) = *(_QWORD *)(a1 + 48);
          *((_QWORD *)v12 + 7) = *(_QWORD *)(a1 + 56);
        }
        a1 += v9;
        v12 += v9;
      }
      LOWORD(v18) = 87;
LABEL_38:
      v18 = (unsigned __int16)v18;
LABEL_39:
      SetLastError(v18);
      goto LABEL_28;
    }
    goto LABEL_35;
  }
LABEL_28:
  if ( *a2 )
    WTSFreeMemoryExA(v4, *a2, *a4);
  return 0;
}

```

## disassembly

```asm
0x180002500  mov     [rsp+arg_0], rbx
0x180002505  mov     [rsp+arg_10], r8
0x18000250a  mov     [rsp+arg_8], rdx
0x18000250f  push    rbp
0x180002510  push    rsi
0x180002511  push    rdi
0x180002512  push    r12
0x180002514  push    r13
0x180002516  push    r14
0x180002518  push    r15
0x18000251a  sub     rsp, 40h
0x18000251e  xor     ebp, ebp
0x180002520  mov     r12, r9
0x180002523  mov     rsi, rdx
0x180002526  mov     rbx, rcx
0x180002529  test    rdx, rdx
0x18000252c  jz      loc_18000271E
0x180002532  test    r9, r9
0x180002535  jz      loc_18000271E
0x18000253b  test    r8, r8
0x18000253e  jz      loc_18000271E
0x180002544  mov     [rdx], rbp
0x180002547  mov     ecx, [r9]
0x18000254a  test    ecx, ecx
0x18000254c  jz      loc_18000272B
0x180002552  test    rbx, rbx
0x180002555  jz      loc_18000271E
0x18000255b  mov     edx, [r8]
0x18000255e  test    edx, edx
0x180002560  jz      loc_18000273F
0x180002566  cmp     edx, 1
0x180002569  jnz     loc_180002732
0x18000256f  mov     ebp, edx
0x180002571  mov     r13d, 40h ; '@'
0x180002577  imul    ecx, r13d
0x18000257b  mov     [rsp+78h+var_48], ebp
0x18000257f  mov     edi, ecx
0x180002581  mov     edx, ecx; uBytes
0x180002583  mov     ecx, 40h ; '@'; uFlags
0x180002588  call    cs:__imp_LocalAlloc
0x18000258e  mov     [rsi], rax
0x180002591  test    rax, rax
0x180002594  jz      loc_1800026E7
0x18000259a  mov     r8d, edi; Size
0x18000259d  xor     edx, edx; Val
0x18000259f  mov     rcx, rax; void *
0x1800025a2  call    memset_0
0x1800025a7  mov     rdi, [rsi]
0x1800025aa  test    rdi, rdi
0x1800025ad  jz      loc_18000274A
0x1800025b3  xor     r15d, r15d
0x1800025b6  cmp     r15d, [r12]
0x1800025ba  jnb     loc_18000272B
0x1800025c0  mov     rax, [rbx+8]
0x1800025c4  test    rax, rax
0x1800025c7  jz      loc_18000275B
0x1800025cd  mov     ecx, 105h
0x1800025d2  cmp     word ptr [rax], 0
0x1800025d6  jz      short loc_1800025EB
0x1800025d8  add     rax, 2
0x1800025dc  sub     rcx, 1
0x1800025e0  jnz     short loc_1800025D2
0x1800025e2  xor     esi, esi
0x1800025e4  mov     eax, 80070057h
0x1800025e9  jmp     short loc_1800025F5
0x1800025eb  mov     esi, 105h
0x1800025f0  sub     rsi, rcx
0x1800025f3  xor     eax, eax
0x1800025f5  mov     ecx, eax
0x1800025f7  test    eax, eax
0x1800025f9  js      loc_180002760
0x1800025ff  jnz     loc_180002760
0x180002605  lea     ebp, [rsi+1]
0x180002608  mov     ecx, 40h ; '@'; uFlags
0x18000260d  mov     edx, ebp; uBytes
0x18000260f  mov     r14d, ebp
0x180002612  call    cs:__imp_LocalAlloc
0x180002618  mov     [rdi+8], rax
0x18000261c  test    rax, rax
0x18000261f  jz      loc_1800026E3
0x180002625  mov     r8d, r14d; Size
0x180002628  xor     edx, edx; Val
0x18000262a  mov     rcx, rax; void *
0x18000262d  call    memset_0
0x180002632  mov     r9, [rbx+8]; UnicodeString
0x180002636  xor     r8d, r8d; ResultSize
0x180002639  mov     rcx, [rdi+8]; MbString
0x18000263d  mov     edx, ebp; MbSize
0x18000263f  mov     [rsp+78h+UnicodeSize], esi; UnicodeSize
0x180002643  call    cs:__imp_RtlUnicodeToMultiByteN
0x180002649  test    eax, eax
0x18000264b  jnz     loc_180002757
0x180002651  mov     rcx, [rbx+10h]; pSid
0x180002655  test    rcx, rcx
0x180002658  jz      short loc_180002687
0x18000265a  call    cs:__imp_GetLengthSid
0x180002660  mov     edx, eax; uBytes
0x180002662  mov     ecx, 40h ; '@'; uFlags
0x180002667  mov     esi, eax
0x180002669  call    cs:__imp_LocalAlloc
0x18000266f  mov     [rdi+10h], rax
0x180002673  test    rax, rax
0x180002676  jz      short loc_1800026E3
0x180002678  mov     rdx, [rbx+10h]; Src
0x18000267c  mov     r8d, esi; Size
0x18000267f  mov     rcx, rax; void *
0x180002682  call    memcpy_0
0x180002687  mov     eax, [rbx]
0x180002689  mov     [rdi], eax
0x18000268b  mov     eax, [rbx+4]
0x18000268e  mov     [rdi+4], eax
0x180002691  mov     rax, [rsp+78h+arg_10]
0x180002699  cmp     dword ptr [rax], 1
0x18000269c  jnz     short loc_1800026D2
0x18000269e  mov     eax, [rbx+18h]
0x1800026a1  mov     [rdi+18h], eax
0x1800026a4  mov     eax, [rbx+1Ch]
0x1800026a7  mov     [rdi+1Ch], eax
0x1800026aa  mov     eax, [rbx+20h]
0x1800026ad  mov     [rdi+20h], eax
0x1800026b0  mov     eax, [rbx+24h]
0x1800026b3  mov     [rdi+24h], eax
0x1800026b6  mov     eax, [rbx+28h]
0x1800026b9  mov     [rdi+28h], eax
0x1800026bc  mov     eax, [rbx+2Ch]
0x1800026bf  mov     [rdi+2Ch], eax
0x1800026c2  mov     rax, [rbx+30h]
0x1800026c6  mov     [rdi+30h], rax
0x1800026ca  mov     rax, [rbx+38h]
0x1800026ce  mov     [rdi+38h], rax
0x1800026d2  mov     eax, r13d
0x1800026d5  add     rbx, rax
0x1800026d8  add     rdi, rax
0x1800026db  inc     r15d
0x1800026de  jmp     loc_1800025B6
0x1800026e3  mov     ebp, [rsp+78h+var_48]
0x1800026e7  mov     rdx, [rsp+78h+arg_8]
0x1800026ef  xor     ebx, ebx
0x1800026f1  mov     rdx, [rdx]; pMemory
0x1800026f4  test    rdx, rdx
0x1800026f7  jz      short loc_180002704
0x1800026f9  mov     r8d, [r12]; NumberOfEntries
0x1800026fd  mov     ecx, ebp; WTSTypeClass
0x1800026ff  call    WTSFreeMemoryExA
0x180002704  mov     eax, ebx
0x180002706  mov     rbx, [rsp+78h+arg_0]
0x18000270e  add     rsp, 40h
0x180002712  pop     r15
0x180002714  pop     r14
0x180002716  pop     r13
0x180002718  pop     r12
0x18000271a  pop     rdi
0x18000271b  pop     rsi
0x18000271c  pop     rbp
0x18000271d  retn
0x18000271e  mov     ecx, 57h ; 'W'; dwErrCode
0x180002723  call    cs:__imp_SetLastError
0x180002729  jmp     short loc_1800026E7
0x18000272b  mov     eax, 1
0x180002730  jmp     short loc_180002706
0x180002732  mov     ecx, 57h ; 'W'; dwErrCode
0x180002737  call    cs:__imp_SetLastError
0x18000273d  jmp     short loc_1800026E7
0x18000273f  mov     r13d, 18h
0x180002745  jmp     loc_180002577
0x18000274a  mov     ecx, 57h ; 'W'; dwErrCode
0x18000274f  call    cs:__imp_SetLastError
0x180002755  jmp     short loc_1800026E7
0x180002757  xor     ecx, ecx
0x180002759  jmp     short loc_180002763
0x18000275b  mov     ecx, 80070057h
0x180002760  movzx   ecx, cx; dwErrCode
0x180002763  call    cs:__imp_SetLastError
0x180002769  jmp     loc_1800026E3
```
