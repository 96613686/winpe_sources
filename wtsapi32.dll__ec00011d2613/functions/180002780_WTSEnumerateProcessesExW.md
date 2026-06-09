# WTSEnumerateProcessesExW

- ea: `0x180002780`
- end: `0x180002b30`
- name: `WTSEnumerateProcessesExW`
- size: `944`
- prototype: `BOOL __stdcall(HANDLE hServer, DWORD *pLevel, DWORD SessionId, LPWSTR *ppProcessInfo, DWORD *pCount)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002450`

## callees

- `0x180002780`
- `0x180002d20`
- `0x180003920`
- `0x180015582`
- `0x18001558e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002acd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002acd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002a6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002a6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002884`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800028f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000294f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002884`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800028f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000294f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180002940`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180002940`
- `WINSTA!WinStationGetAllProcesses` at `0x18000282b`
- `WINSTA!WinStationGetAllProcesses` at `0x18000282b`
- `WINSTA!WinStationFreeGAPMemory` at `0x180002a5d`
- `WINSTA!WinStationFreeGAPMemory` at `0x180002a5d`

## pseudocode

```c
BOOL __stdcall WTSEnumerateProcessesExW(
        HANDLE hServer,
        DWORD *pLevel,
        DWORD SessionId,
        LPWSTR *ppProcessInfo,
        DWORD *pCount)
{
  char *v9; // rsi
  ULONG v10; // r12d
  unsigned int v11; // eax
  __int64 v12; // r13
  unsigned int v13; // ebx
  char *v14; // r14
  __int64 i; // rbx
  __int64 v16; // rsi
  __int64 v17; // rdi
  HLOCAL v18; // rax
  void *v19; // rcx
  __int64 v20; // rax
  void *v21; // rcx
  DWORD LengthSid; // edi
  HLOCAL v23; // rax
  BOOL v24; // ebx
  __int64 v26; // rdx
  ULONG v27; // eax
  DWORD v28; // ecx
  ULONG NumberOfEntries; // [rsp+30h] [rbp-48h] BYREF
  BOOL v30; // [rsp+34h] [rbp-44h]
  WTS_TYPE_CLASS WTSTypeClass; // [rsp+38h] [rbp-40h]
  DWORD v32; // [rsp+3Ch] [rbp-3Ch] BYREF
  __int64 v33; // [rsp+40h] [rbp-38h] BYREF
  LPWSTR ppBuffer; // [rsp+48h] [rbp-30h] BYREF
  PVOID pMemory; // [rsp+50h] [rbp-28h]

  v30 = 0;
  NumberOfEntries = 0;
  v9 = 0;
  v33 = 0;
  v10 = 0;
  ppBuffer = 0;
  v32 = 0;
  WTSTypeClass = WTSTypeProcessInfoLevel0;
  if ( !ppProcessInfo || !pLevel || !pCount )
  {
LABEL_43:
    v28 = 87;
LABEL_44:
    SetLastError(v28);
    v24 = 0;
    goto LABEL_29;
  }
  if ( *pLevel >= 2 )
  {
    *pLevel = 1;
    v28 = 1305;
    goto LABEL_44;
  }
  if ( SessionId != -2 && !WTSQuerySessionInformationW(hServer, SessionId, WTSSessionId, &ppBuffer, &v32)
    || !(unsigned __int8)WinStationGetAllProcesses(hServer, 0, &NumberOfEntries, &v33) )
  {
LABEL_36:
    v24 = v30;
    goto LABEL_29;
  }
  if ( SessionId == -2 )
  {
    v10 = NumberOfEntries;
  }
  else
  {
    if ( !NumberOfEntries )
      goto LABEL_46;
    v26 = 0;
    do
    {
      v27 = v10 + 1;
      if ( *(_DWORD *)(*(_QWORD *)(v33 + 24 * v26) + 88LL) != *(_DWORD *)ppBuffer )
        v27 = v10;
      v26 = (unsigned int)(v26 + 1);
      v10 = v27;
    }
    while ( (unsigned int)v26 < NumberOfEntries );
  }
  if ( v10 )
  {
    if ( !*pLevel )
    {
      WTSTypeClass = WTSTypeProcessInfoLevel0;
      v11 = 24 * v10;
      v12 = 24;
      goto LABEL_14;
    }
    if ( *pLevel == 1 )
    {
      WTSTypeClass = WTSTypeProcessInfoLevel1;
      v11 = v10 << 6;
      v12 = 64;
LABEL_14:
      if ( v11 >= v10 )
      {
        v13 = v11;
        pMemory = LocalAlloc(0x40u, v11);
        v9 = (char *)pMemory;
        memset_0(pMemory, 0, v13);
        if ( !v9 )
          goto LABEL_36;
        v14 = v9;
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= NumberOfEntries )
          {
            v24 = 1;
            v9 = (char *)pMemory;
            *ppProcessInfo = (LPWSTR)pMemory;
            *pCount = v10;
            goto LABEL_29;
          }
          v16 = 24 * i;
          if ( SessionId == -2 || *(_DWORD *)(*(_QWORD *)(v16 + v33) + 88LL) == *(_DWORD *)ppBuffer )
          {
            v17 = *(unsigned __int16 *)(*(_QWORD *)(v16 + v33) + 56LL);
            v18 = LocalAlloc(0x40u, v17 + 2);
            *((_QWORD *)v14 + 1) = v18;
            memset_0(v18, 0, v17 + 2);
            v19 = (void *)*((_QWORD *)v14 + 1);
            if ( !v19 )
              goto LABEL_35;
            memcpy_0(
              v19,
              *(const void **)(*(_QWORD *)(v16 + v33) + 64LL),
              *(unsigned __int16 *)(*(_QWORD *)(v16 + v33) + 56LL));
            v20 = v33;
            v21 = *(void **)(v16 + v33 + 16);
            if ( v21 )
            {
              LengthSid = GetLengthSid(v21);
              v23 = LocalAlloc(0x40u, LengthSid);
              *((_QWORD *)v14 + 2) = v23;
              if ( !v23 )
              {
LABEL_35:
                v9 = (char *)pMemory;
                goto LABEL_36;
              }
              memcpy_0(v23, *(const void **)(v16 + v33 + 16), LengthSid);
              v20 = v33;
            }
            *(_DWORD *)v14 = *(_DWORD *)(*(_QWORD *)(v16 + v20) + 88LL);
            *((_DWORD *)v14 + 1) = *(_DWORD *)(*(_QWORD *)(v16 + v33) + 76LL);
            if ( *pLevel == 1 )
            {
              *((_DWORD *)v14 + 6) = *(_DWORD *)(*(_QWORD *)(v16 + v33) + 4LL);
              *((_DWORD *)v14 + 7) = *(_DWORD *)(*(_QWORD *)(v16 + v33) + 84LL);
              *((_DWORD *)v14 + 8) = *(_DWORD *)(*(_QWORD *)(v16 + v33) + 104LL);
              *((_DWORD *)v14 + 9) = *(_DWORD *)(*(_QWORD *)(v16 + v33) + 96LL);
              *((_DWORD *)v14 + 10) = *(_DWORD *)(*(_QWORD *)(v16 + v33) + 120LL);
              *((_DWORD *)v14 + 11) = *(_DWORD *)(*(_QWORD *)(v16 + v33) + 116LL);
              *((_QWORD *)v14 + 6) = *(_QWORD *)(*(_QWORD *)(v16 + v33) + 40LL);
              *((_QWORD *)v14 + 7) = *(_QWORD *)(*(_QWORD *)(v16 + v33) + 48LL);
            }
            v14 += v12;
          }
        }
      }
      v28 = 534;
      goto LABEL_44;
    }
    goto LABEL_43;
  }
LABEL_46:
  *ppProcessInfo = 0;
  v24 = 1;
  *pCount = 0;
LABEL_29:
  if ( v33 )
    WinStationFreeGAPMemory(0, v33, NumberOfEntries);
  if ( ppBuffer )
    LocalFree(ppBuffer);
  if ( !v24 && v9 )
    WTSFreeMemoryExW(WTSTypeClass, v9, v10);
  return v24;
}

```

## disassembly

```asm
0x180002780  mov     r11, rsp
0x180002783  mov     [r11+20h], r9
0x180002787  mov     [r11+10h], rdx
0x18000278b  push    rbp
0x18000278c  push    rbx
0x18000278d  push    rsi
0x18000278e  push    r12
0x180002790  mov     rbp, rsp
0x180002793  sub     rsp, 78h
0x180002797  xor     eax, eax
0x180002799  mov     [r11+8], rdi
0x18000279d  mov     [r11-28h], r13
0x1800027a1  mov     r13, r9
0x1800027a4  mov     [r11-30h], r14
0x1800027a8  mov     rdi, rdx
0x1800027ab  mov     [r11-38h], r15
0x1800027af  mov     r15d, r8d
0x1800027b2  mov     [rbp+var_44], eax
0x1800027b5  mov     rbx, rcx
0x1800027b8  mov     [rbp+NumberOfEntries], eax
0x1800027bb  mov     esi, eax
0x1800027bd  mov     [rbp+var_38], rax
0x1800027c1  mov     r12d, eax
0x1800027c4  mov     [rbp+ppBuffer], rax
0x1800027c8  mov     [rbp+var_3C], eax
0x1800027cb  mov     [rbp+WTSTypeClass], eax
0x1800027ce  test    r9, r9
0x1800027d1  jz      loc_180002AC8
0x1800027d7  test    rdx, rdx
0x1800027da  jz      loc_180002AC8
0x1800027e0  mov     r14, [rbp+pCount]
0x1800027e4  test    r14, r14
0x1800027e7  jz      loc_180002AC8
0x1800027ed  cmp     dword ptr [rdx], 2
0x1800027f0  jnb     loc_180002B00
0x1800027f6  cmp     r8d, 0FFFFFFFEh
0x1800027fa  jz      short loc_18000281E
0x1800027fc  lea     rax, [rbp+var_3C]
0x180002800  mov     r8d, 4; WTSInfoClass
0x180002806  lea     r9, [rbp+ppBuffer]; ppBuffer
0x18000280a  mov     [r11-78h], rax
0x18000280e  mov     edx, r15d; SessionId
0x180002811  call    WTSQuerySessionInformationW
0x180002816  test    eax, eax
0x180002818  jz      loc_180002A8A
0x18000281e  lea     r9, [rbp+var_38]
0x180002822  xor     edx, edx
0x180002824  lea     r8, [rbp+NumberOfEntries]
0x180002828  mov     rcx, rbx
0x18000282b  call    cs:__imp_WinStationGetAllProcesses
0x180002831  test    al, al
0x180002833  jz      loc_180002A8A
0x180002839  cmp     r15d, 0FFFFFFFEh
0x18000283d  jnz     loc_180002A8F
0x180002843  mov     r12d, [rbp+NumberOfEntries]
0x180002847  test    r12d, r12d
0x18000284a  jz      loc_180002AEF
0x180002850  mov     ecx, [rdi]
0x180002852  test    ecx, ecx
0x180002854  jz      loc_180002ADA
0x18000285a  cmp     ecx, 1
0x18000285d  jnz     loc_180002AC8
0x180002863  mov     eax, r12d
0x180002866  mov     [rbp+WTSTypeClass], ecx
0x180002869  shl     eax, 6
0x18000286c  mov     r13d, 40h ; '@'
0x180002872  cmp     eax, r12d
0x180002875  jb      loc_180002B0D
0x18000287b  mov     edx, eax; uBytes
0x18000287d  mov     ecx, 40h ; '@'; uFlags
0x180002882  mov     ebx, eax
0x180002884  call    cs:__imp_LocalAlloc
0x18000288a  mov     r8d, ebx; Size
0x18000288d  xor     edx, edx; Val
0x18000288f  mov     rcx, rax; void *
0x180002892  mov     [rbp+pMemory], rax
0x180002896  mov     rsi, rax
0x180002899  call    memset_0
0x18000289e  test    rsi, rsi
0x1800028a1  jz      loc_180002A8A
0x1800028a7  mov     r14, rsi
0x1800028aa  xor     ebx, ebx
0x1800028ac  nop     dword ptr [rax+00h]
0x1800028b0  cmp     ebx, [rbp+NumberOfEntries]
0x1800028b3  jnb     loc_180002A20
0x1800028b9  lea     rcx, [rbx+rbx*2]
0x1800028bd  lea     rsi, ds:0[rcx*8]
0x1800028c5  cmp     r15d, 0FFFFFFFEh
0x1800028c9  jz      short loc_1800028E2
0x1800028cb  mov     rax, [rbp+var_38]
0x1800028cf  mov     rdx, [rsi+rax]
0x1800028d3  mov     rax, [rbp+ppBuffer]
0x1800028d7  mov     ecx, [rax]
0x1800028d9  cmp     [rdx+58h], ecx
0x1800028dc  jnz     loc_180002A19
0x1800028e2  mov     rax, [rbp+var_38]
0x1800028e6  mov     rcx, [rsi+rax]
0x1800028ea  movzx   edi, word ptr [rcx+38h]
0x1800028ee  mov     ecx, 40h ; '@'; uFlags
0x1800028f3  lea     rdx, [rdi+2]; uBytes
0x1800028f7  call    cs:__imp_LocalAlloc
0x1800028fd  lea     r8, [rdi+2]; Size
0x180002901  xor     edx, edx; Val
0x180002903  mov     rcx, rax; void *
0x180002906  mov     [r14+8], rax
0x18000290a  call    memset_0
0x18000290f  mov     rcx, [r14+8]; void *
0x180002913  test    rcx, rcx
0x180002916  jz      loc_180002A86
0x18000291c  mov     rax, [rbp+var_38]
0x180002920  mov     rdx, [rsi+rax]
0x180002924  movzx   r8d, word ptr [rdx+38h]; Size
0x180002929  mov     rdx, [rdx+40h]; Src
0x18000292d  call    memcpy_0
0x180002932  mov     rax, [rbp+var_38]
0x180002936  mov     rcx, [rsi+rax+10h]; pSid
0x18000293b  test    rcx, rcx
0x18000293e  jz      short loc_18000297A
0x180002940  call    cs:__imp_GetLengthSid
0x180002946  mov     edx, eax; uBytes
0x180002948  mov     ecx, 40h ; '@'; uFlags
0x18000294d  mov     edi, eax
0x18000294f  call    cs:__imp_LocalAlloc
0x180002955  mov     [r14+10h], rax
0x180002959  test    rax, rax
0x18000295c  jz      loc_180002A86
0x180002962  mov     rdx, [rbp+var_38]
0x180002966  mov     r8d, edi; Size
0x180002969  mov     rcx, rax; void *
0x18000296c  mov     rdx, [rsi+rdx+10h]; Src
0x180002971  call    memcpy_0
0x180002976  mov     rax, [rbp+var_38]
0x18000297a  mov     rax, [rsi+rax]
0x18000297e  mov     rdi, [rbp+arg_8]
0x180002982  mov     ecx, [rax+58h]
0x180002985  mov     [r14], ecx
0x180002988  mov     rax, [rbp+var_38]
0x18000298c  mov     rcx, [rsi+rax]
0x180002990  mov     eax, [rcx+4Ch]
0x180002993  mov     [r14+4], eax
0x180002997  cmp     dword ptr [rdi], 1
0x18000299a  jnz     short loc_180002A16
0x18000299c  mov     rax, [rbp+var_38]
0x1800029a0  mov     rcx, [rsi+rax]
0x1800029a4  mov     eax, [rcx+4]
0x1800029a7  mov     [r14+18h], eax
0x1800029ab  mov     rax, [rbp+var_38]
0x1800029af  mov     rcx, [rsi+rax]
0x1800029b3  mov     eax, [rcx+54h]
0x1800029b6  mov     [r14+1Ch], eax
0x1800029ba  mov     rax, [rbp+var_38]
0x1800029be  mov     rcx, [rsi+rax]
0x1800029c2  mov     eax, [rcx+68h]
0x1800029c5  mov     [r14+20h], eax
0x1800029c9  mov     rax, [rbp+var_38]
0x1800029cd  mov     rcx, [rsi+rax]
0x1800029d1  mov     eax, [rcx+60h]
0x1800029d4  mov     [r14+24h], eax
0x1800029d8  mov     rax, [rbp+var_38]
0x1800029dc  mov     rcx, [rsi+rax]
0x1800029e0  mov     eax, [rcx+78h]
0x1800029e3  mov     [r14+28h], eax
0x1800029e7  mov     rax, [rbp+var_38]
0x1800029eb  mov     rcx, [rsi+rax]
0x1800029ef  mov     eax, [rcx+74h]
0x1800029f2  mov     [r14+2Ch], eax
0x1800029f6  mov     rax, [rbp+var_38]
0x1800029fa  mov     rcx, [rsi+rax]
0x1800029fe  mov     rax, [rcx+28h]
0x180002a02  mov     [r14+30h], rax
0x180002a06  mov     rax, [rbp+var_38]
0x180002a0a  mov     rcx, [rsi+rax]
0x180002a0e  mov     rax, [rcx+30h]
0x180002a12  mov     [r14+38h], rax
0x180002a16  add     r14, r13
0x180002a19  inc     ebx
0x180002a1b  jmp     loc_1800028B0
0x180002a20  mov     rax, [rbp+arg_18]
0x180002a24  mov     ebx, 1
0x180002a29  mov     rsi, [rbp+pMemory]
0x180002a2d  mov     [rax], rsi
0x180002a30  mov     rax, [rbp+pCount]
0x180002a34  mov     [rax], r12d
0x180002a37  mov     rdx, [rbp+var_38]
0x180002a3b  mov     r15, [rsp+78h+var_18]
0x180002a40  mov     r14, [rsp+78h+var_10]
0x180002a45  mov     r13, [rsp+78h+var_8]
0x180002a4a  mov     rdi, [rsp+78h+arg_0]
0x180002a52  test    rdx, rdx
0x180002a55  jz      short loc_180002A63
0x180002a57  mov     r8d, [rbp+NumberOfEntries]
0x180002a5b  xor     ecx, ecx
0x180002a5d  call    cs:__imp_WinStationFreeGAPMemory
0x180002a63  mov     rcx, [rbp+ppBuffer]; hMem
0x180002a67  test    rcx, rcx
0x180002a6a  jz      short loc_180002A72
0x180002a6c  call    cs:__imp_LocalFree
0x180002a72  test    ebx, ebx
0x180002a74  jz      loc_180002B14
0x180002a7a  mov     eax, ebx
0x180002a7c  add     rsp, 78h
0x180002a80  pop     r12
0x180002a82  pop     rsi
0x180002a83  pop     rbx
0x180002a84  pop     rbp
0x180002a85  retn
0x180002a86  mov     rsi, [rbp+pMemory]
0x180002a8a  mov     ebx, [rbp+var_44]
0x180002a8d  jmp     short loc_180002A37
0x180002a8f  cmp     [rbp+NumberOfEntries], esi
0x180002a92  jbe     short loc_180002AEF
0x180002a94  mov     rax, [rbp+ppBuffer]
0x180002a98  xor     edx, edx
0x180002a9a  mov     r8d, [rax]
0x180002a9d  nop     dword ptr [rax]
0x180002aa0  mov     rax, [rbp+var_38]
0x180002aa4  lea     rcx, [rdx+rdx*2]
0x180002aa8  mov     rcx, [rax+rcx*8]
0x180002aac  lea     eax, [r12+1]
0x180002ab1  cmp     [rcx+58h], r8d
0x180002ab5  cmovnz  eax, r12d
0x180002ab9  inc     edx
0x180002abb  mov     r12d, eax
0x180002abe  cmp     edx, [rbp+NumberOfEntries]
0x180002ac1  jb      short loc_180002AA0
0x180002ac3  jmp     loc_180002847
0x180002ac8  mov     ecx, 57h ; 'W'; dwErrCode
0x180002acd  call    cs:__imp_SetLastError
0x180002ad3  mov     ebx, esi
0x180002ad5  jmp     loc_180002A37
0x180002ada  lea     eax, [r12+r12*2]
0x180002ade  mov     [rbp+WTSTypeClass], esi
0x180002ae1  shl     eax, 3
0x180002ae4  mov     r13d, 18h
0x180002aea  jmp     loc_180002872
0x180002aef  mov     [r13+0], rsi
0x180002af3  mov     ebx, 1
0x180002af8  mov     [r14], esi
0x180002afb  jmp     loc_180002A37
0x180002b00  mov     dword ptr [rdx], 1
0x180002b06  mov     ecx, 519h
0x180002b0b  jmp     short loc_180002ACD
0x180002b0d  mov     ecx, 216h
0x180002b12  jmp     short loc_180002ACD
0x180002b14  test    rsi, rsi
0x180002b17  jz      loc_180002A7A
0x180002b1d  mov     ecx, [rbp+WTSTypeClass]; WTSTypeClass
0x180002b20  mov     r8d, r12d; NumberOfEntries
0x180002b23  mov     rdx, rsi; pMemory
0x180002b26  call    WTSFreeMemoryExW
0x180002b2b  jmp     loc_180002A7A
```
