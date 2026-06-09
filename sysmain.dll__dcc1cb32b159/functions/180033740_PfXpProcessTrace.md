# PfXpProcessTrace

- ea: `0x180033740`
- end: `0x180033b31`
- name: `PfXpProcessTrace`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, int *, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006bf88`

## callees

- `0x180022058`
- `0x180023e88`
- `0x1800285e0`
- `0x180032574`
- `0x180032630`
- `0x180032678`
- `0x1800331e4`
- `0x180033740`
- `0x180033b38`
- `0x180034900`
- `0x1800349ac`
- `0x180034a7c`
- `0x180034b34`
- `0x180034e20`
- `0x180035878`
- `0x18003aa6c`
- `0x1800422b0`
- `0x18007092c`
- `0x180081770`
- `0x180094f68`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180033978`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180033a39`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180033978`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180033a39`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800339a1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180033a62`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800339a1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180033a62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003397e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003397e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180033a14`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180033b26`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180033a14`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180033b26`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180033ab1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180033b0b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180033ab1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180033b0b`

## pseudocode

```c
__int64 __fastcall PfXpProcessTrace(__int64 a1, int *a2, int a3)
{
  __int64 v6; // r8
  void *v7; // rbx
  unsigned int FilePath; // edi
  BOOL v9; // r15d
  unsigned int v10; // eax
  int v11; // r8d
  unsigned int v12; // edx
  __int64 v13; // rbx
  int v15; // ecx
  LPVOID lpAddress[2]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v17[88]; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+88h] [rbp-78h]
  int v19; // [rsp+90h] [rbp-70h]
  int v20; // [rsp+F8h] [rbp-8h]
  unsigned int v21; // [rsp+100h] [rbp+0h]
  __int64 v22; // [rsp+260h] [rbp+160h]
  _BYTE v23[176]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v24[304]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v25[208]; // [rsp+450h] [rbp+350h] BYREF
  WCHAR FileName[264]; // [rsp+520h] [rbp+420h] BYREF

  memset_0(v17, 0, 0x238u);
  memset_0(v23, 0, sizeof(v23));
  memset_0(v24, 0, 0x1F8u);
  v6 = (unsigned int)a2[19];
  v7 = 0;
  lpAddress[0] = 0;
  PfXpInitializeScenarioInfo(v17, a2 + 3, v6, a1);
  PfXpTraceSupportInitialize(v23);
  PfSiInitialize(v24);
  if ( a2[22] < (unsigned int)a2[23] >> 3 )
  {
    FilePath = 6622;
    goto LABEL_16;
  }
  FilePath = PfXpScenarioGetFilePath(FileName);
  if ( !FilePath )
  {
    FilePath = PfSvFIGetHandle(v25);
    if ( !FilePath )
    {
      FilePath = PfXpTraceSupportBuild(v23, a2, v24);
      if ( !FilePath )
      {
        PfXpScenarioOpen(FileName, a2[19], lpAddress);
        v7 = lpAddress[0];
        v9 = lpAddress[0] == 0;
        FilePath = PfXpScenarioInfoPreallocate(v17, lpAddress[0], v23);
        if ( !FilePath )
        {
          if ( v7 )
          {
            FilePath = PfXpAddExistingScenarioInfo(v17, v7);
            if ( FilePath )
              goto LABEL_16;
            VirtualFree(v7, 0, 0x8000u);
            v7 = 0;
          }
          if ( v20 == 1 )
          {
            RtlAcquireSRWLockExclusive(&qword_1800D3C30);
            v15 = dword_1800D3C38;
            if ( dword_1800D3C38 >= (unsigned int)(4 * *(_DWORD *)(a1 + 368)) )
            {
              PfXpCleanupPrefetchDirectory(0, a1);
              v15 = dword_1800D3C38;
              if ( dword_1800D3C38 >= (unsigned int)(4 * *(_DWORD *)(a1 + 368)) )
              {
                FilePath = 4;
                goto LABEL_16;
              }
            }
            dword_1800D3C38 = v15 + 1;
            RtlReleaseSRWLockExclusive(&qword_1800D3C30);
          }
          FilePath = PfXpAddTraceInfo(v17, v23);
          if ( FilePath )
            goto LABEL_16;
          v10 = PfXpApplyPrefetchPolicy(v17);
          FilePath = v10;
          if ( !v10 )
          {
            if ( !v18 || !v19 )
            {
              DeleteFileW(FileName);
              FilePath = 11;
              goto LABEL_16;
            }
            v11 = a2[40];
            if ( (*(_BYTE *)(*(_QWORD *)&PfSvcGlobals + 1604LL) & 2) != 0 )
            {
              if ( (v11 & 1) != 0 || *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 332LL) == 4 )
              {
                v12 = v21 | 3;
                goto LABEL_15;
              }
            }
            else if ( (v11 & 1) == 0 )
            {
              v12 = v21;
              if ( (v21 & 3) != 0 )
                v12 = v21 & 0xFFFFFFFC | ((_BYTE)v21 - 1) & 3;
              goto LABEL_15;
            }
            v12 = v21;
LABEL_15:
            v21 = v12 & 0xFFFFFFFB | (2 * (v11 & 2));
            FilePath = PfXpWriteScenario(a1, v17, FileName);
            if ( v9 && v22 )
              PfSvFirstLaunchNotify(*(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4096LL));
            goto LABEL_16;
          }
          if ( v10 == 1237 )
            DeleteFileW(FileName);
        }
      }
    }
  }
LABEL_16:
  if ( a3 )
    PfXpLogProcessTrace(v17, FilePath);
  PfXpCleanupScenarioInfo(v17);
  PfXpTraceSupportCleanup(v23);
  PfSiCleanup(v24);
  if ( v7 )
    VirtualFree(v7, 0, 0x8000u);
  v13 = *(_QWORD *)&PfSvcGlobals;
  RtlAcquireSRWLockExclusive(*(_QWORD *)&PfSvcGlobals + 96LL);
  *(_DWORD *)(v13 + 232) = GetCurrentThreadId();
  PfBhCompact(v13 + 120);
  *(_DWORD *)(v13 + 232) = 0;
  RtlReleaseSRWLockExclusive(v13 + 96);
  return FilePath;
}

```

## disassembly

```asm
0x180033740  mov     [rsp-8+arg_10], rbx
0x180033745  mov     [rsp-8+arg_18], rsi
0x18003374a  push    rbp
0x18003374b  push    rdi
0x18003374c  push    r12
0x18003374e  push    r14
0x180033750  push    r15
0x180033752  lea     rbp, [rsp-640h]
0x18003375a  sub     rsp, 740h
0x180033761  mov     rax, cs:__security_cookie
0x180033768  xor     rax, rsp
0x18003376b  mov     [rbp+660h+var_30], rax
0x180033772  mov     r12d, r8d
0x180033775  mov     rsi, rdx
0x180033778  mov     r14, rcx
0x18003377b  xor     edx, edx; Val
0x18003377d  mov     r8d, 238h; Size
0x180033783  lea     rcx, [rsp+760h+var_730]; void *
0x180033788  call    memset_0
0x18003378d  xor     edx, edx; Val
0x18003378f  lea     rcx, [rbp+660h+var_4F0]; void *
0x180033796  mov     r8d, 0B0h; Size
0x18003379c  call    memset_0
0x1800337a1  xor     edx, edx; Val
0x1800337a3  lea     rcx, [rbp+660h+var_440]; void *
0x1800337aa  mov     r8d, 1F8h; Size
0x1800337b0  call    memset_0
0x1800337b5  mov     r8d, [rsi+4Ch]
0x1800337b9  lea     rdx, [rsi+0Ch]
0x1800337bd  xor     ebx, ebx
0x1800337bf  lea     rcx, [rsp+760h+var_730]
0x1800337c4  mov     r9, r14
0x1800337c7  mov     [rsp+760h+lpAddress], rbx
0x1800337cc  call    PfXpInitializeScenarioInfo
0x1800337d1  lea     rcx, [rbp+660h+var_4F0]
0x1800337d8  call    PfXpTraceSupportInitialize
0x1800337dd  lea     rcx, [rbp+660h+var_440]
0x1800337e4  call    PfSiInitialize
0x1800337e9  mov     eax, [rsi+5Ch]
0x1800337ec  shr     eax, 3
0x1800337ef  cmp     [rsi+58h], eax
0x1800337f2  jb      loc_180033A6D
0x1800337f8  lea     r8, [rsi+0Ch]
0x1800337fc  lea     rcx, [rbp+660h+FileName]; pszDest
0x180033803  call    PfXpScenarioGetFilePath
0x180033808  mov     edi, eax
0x18003380a  test    eax, eax
0x18003380c  jnz     loc_180033939
0x180033812  lea     rcx, [rbp+660h+var_310]
0x180033819  call    PfSvFIGetHandle
0x18003381e  mov     edi, eax
0x180033820  test    eax, eax
0x180033822  jnz     loc_180033939
0x180033828  lea     r8, [rbp+660h+var_440]
0x18003382f  mov     rdx, rsi
0x180033832  lea     rcx, [rbp+660h+var_4F0]
0x180033839  call    PfXpTraceSupportBuild
0x18003383e  mov     edi, eax
0x180033840  test    eax, eax
0x180033842  jnz     loc_180033939
0x180033848  mov     edx, [rsi+4Ch]
0x18003384b  lea     r8, [rsp+760h+lpAddress]
0x180033850  lea     rcx, [rbp+660h+FileName]
0x180033857  call    PfXpScenarioOpen
0x18003385c  mov     rbx, [rsp+760h+lpAddress]
0x180033861  lea     r8, [rbp+660h+var_4F0]
0x180033868  xor     r15d, r15d
0x18003386b  lea     rcx, [rsp+760h+var_730]
0x180033870  test    rbx, rbx
0x180033873  mov     rdx, rbx
0x180033876  setz    r15b
0x18003387a  call    PfXpScenarioInfoPreallocate
0x18003387f  mov     edi, eax
0x180033881  test    eax, eax
0x180033883  jnz     loc_180033939
0x180033889  test    rbx, rbx
0x18003388c  jnz     loc_1800339F2
0x180033892  cmp     [rbp+660h+var_668], 1
0x180033896  jz      loc_180033A32
0x18003389c  lea     rdx, [rbp+660h+var_4F0]
0x1800338a3  lea     rcx, [rsp+760h+var_730]
0x1800338a8  call    PfXpAddTraceInfo
0x1800338ad  mov     edi, eax
0x1800338af  test    eax, eax
0x1800338b1  jnz     loc_180033939
0x1800338b7  lea     rcx, [rsp+760h+var_730]
0x1800338bc  call    PfXpApplyPrefetchPolicy
0x1800338c1  mov     edi, eax
0x1800338c3  test    eax, eax
0x1800338c5  jnz     loc_180033A9F
0x1800338cb  cmp     [rbp+660h+var_6D8], eax
0x1800338ce  jz      loc_180033B04
0x1800338d4  cmp     [rbp+660h+var_6D0], eax
0x1800338d7  jz      loc_180033B04
0x1800338dd  mov     r8d, [rsi+0A0h]
0x1800338e4  mov     eax, r8d
0x1800338e7  mov     rcx, cs:PfSvcGlobals
0x1800338ee  and     eax, 1
0x1800338f1  test    byte ptr [rcx+644h], 2
0x1800338f8  jnz     loc_1800339D4
0x1800338fe  test    eax, eax
0x180033900  jz      loc_180033ABC
0x180033906  mov     edx, [rbp+660h+var_660]
0x180033909  and     r8d, 2
0x18003390d  and     edx, 0FFFFFFFBh
0x180033910  add     r8d, r8d
0x180033913  mov     rcx, r14
0x180033916  or      r8d, edx
0x180033919  lea     rdx, [rsp+760h+var_730]
0x18003391e  mov     [rbp+660h+var_660], r8d
0x180033922  lea     r8, [rbp+660h+FileName]
0x180033929  call    PfXpWriteScenario
0x18003392e  mov     edi, eax
0x180033930  test    r15d, r15d
0x180033933  jnz     loc_180033ADC
0x180033939  test    r12d, r12d
0x18003393c  jnz     loc_180033A21
0x180033942  lea     rcx, [rsp+760h+var_730]
0x180033947  call    PfXpCleanupScenarioInfo
0x18003394c  lea     rcx, [rbp+660h+var_4F0]
0x180033953  call    PfXpTraceSupportCleanup
0x180033958  lea     rcx, [rbp+660h+var_440]
0x18003395f  call    PfSiCleanup
0x180033964  test    rbx, rbx
0x180033967  jnz     loc_180033B1B
0x18003396d  mov     rbx, cs:PfSvcGlobals
0x180033974  lea     rcx, [rbx+60h]
0x180033978  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18003397e  call    cs:__imp_GetCurrentThreadId
0x180033984  lea     rcx, [rbx+78h]
0x180033988  mov     [rbx+0E8h], eax
0x18003398e  call    PfBhCompact
0x180033993  lea     rcx, [rbx+60h]
0x180033997  mov     dword ptr [rbx+0E8h], 0
0x1800339a1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800339a7  mov     eax, edi
0x1800339a9  mov     rcx, [rbp+660h+var_30]
0x1800339b0  xor     rcx, rsp; StackCookie
0x1800339b3  call    __security_check_cookie
0x1800339b8  lea     r11, [rsp+760h+var_20]
0x1800339c0  mov     rbx, [r11+40h]
0x1800339c4  mov     rsi, [r11+48h]
0x1800339c8  mov     rsp, r11
0x1800339cb  pop     r15
0x1800339cd  pop     r14
0x1800339cf  pop     r12
0x1800339d1  pop     rdi
0x1800339d2  pop     rbp
0x1800339d3  retn
0x1800339d4  test    eax, eax
0x1800339d6  jnz     short loc_1800339E7
0x1800339d8  lea     edi, [rax+4]
0x1800339db  cmp     [rcx+14Ch], edi
0x1800339e1  jnz     loc_180033906
0x1800339e7  mov     edx, [rbp+660h+var_660]
0x1800339ea  or      edx, 3
0x1800339ed  jmp     loc_180033909
0x1800339f2  mov     rdx, rbx
0x1800339f5  lea     rcx, [rsp+760h+var_730]
0x1800339fa  call    PfXpAddExistingScenarioInfo
0x1800339ff  mov     edi, eax
0x180033a01  test    eax, eax
0x180033a03  jnz     loc_180033939
0x180033a09  xor     edx, edx; dwSize
0x180033a0b  mov     r8d, 8000h; dwFreeType
0x180033a11  mov     rcx, rbx; lpAddress
0x180033a14  call    cs:__imp_VirtualFree
0x180033a1a  xor     ebx, ebx
0x180033a1c  jmp     loc_180033892
0x180033a21  mov     edx, edi
0x180033a23  lea     rcx, [rsp+760h+var_730]
0x180033a28  call    PfXpLogProcessTrace
0x180033a2d  jmp     loc_180033942
0x180033a32  lea     rcx, qword_1800D3C30
0x180033a39  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180033a3f  mov     eax, [r14+170h]
0x180033a46  mov     ecx, cs:dword_1800D3C38
0x180033a4c  shl     eax, 2
0x180033a4f  cmp     ecx, eax
0x180033a51  jnb     short loc_180033A77
0x180033a53  inc     ecx
0x180033a55  mov     cs:dword_1800D3C38, ecx
0x180033a5b  lea     rcx, qword_1800D3C30
0x180033a62  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180033a68  jmp     loc_18003389C
0x180033a6d  mov     edi, 19DEh
0x180033a72  jmp     loc_180033939
0x180033a77  mov     rdx, r14
0x180033a7a  xor     ecx, ecx
0x180033a7c  call    PfXpCleanupPrefetchDirectory
0x180033a81  mov     eax, [r14+170h]
0x180033a88  mov     ecx, cs:dword_1800D3C38
0x180033a8e  shl     eax, 2
0x180033a91  cmp     ecx, eax
0x180033a93  jb      short loc_180033A53
0x180033a95  mov     edi, 4
0x180033a9a  jmp     loc_180033939
0x180033a9f  cmp     eax, 4D5h
0x180033aa4  jnz     loc_180033939
0x180033aaa  lea     rcx, [rbp+660h+FileName]; lpFileName
0x180033ab1  call    cs:__imp_DeleteFileW
0x180033ab7  jmp     loc_180033939
0x180033abc  mov     edx, [rbp+660h+var_660]
0x180033abf  test    dl, 3
0x180033ac2  jbe     loc_180033909
0x180033ac8  lea     ecx, [rdx-1]
0x180033acb  mov     eax, edx
0x180033acd  and     ecx, 3
0x180033ad0  and     eax, 0FFFFFFFCh
0x180033ad3  mov     edx, ecx
0x180033ad5  or      edx, eax
0x180033ad7  jmp     loc_180033909
0x180033adc  mov     rdx, [rbp+660h+var_500]
0x180033ae3  test    rdx, rdx
0x180033ae6  jz      loc_180033939
0x180033aec  mov     rcx, cs:PfSvcGlobals
0x180033af3  mov     rcx, [rcx+1000h]
0x180033afa  call    PfSvFirstLaunchNotify
0x180033aff  jmp     loc_180033939
0x180033b04  lea     rcx, [rbp+660h+FileName]; lpFileName
0x180033b0b  call    cs:__imp_DeleteFileW
0x180033b11  mov     edi, 0Bh
0x180033b16  jmp     loc_180033939
0x180033b1b  xor     edx, edx; dwSize
0x180033b1d  mov     r8d, 8000h; dwFreeType
0x180033b23  mov     rcx, rbx; lpAddress
0x180033b26  call    cs:__imp_VirtualFree
0x180033b2c  jmp     loc_18003396D
```
