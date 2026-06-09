# RegReadConfigSettings

- ea: `0x18002e314`
- end: `0x18002e69b`
- name: `RegReadConfigSettings`
- size: `903`
- prototype: `__int64 __fastcall(CRegistry *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002e6a4`

## callees

- `0x18000bcf0`
- `0x18002e188`
- `0x18002e1d0`
- `0x18002e314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e512`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e4e8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e508`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e4e8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e508`

## string_xrefs

- `0x18002e3d4`: `MaxCacheIP`
- `0x18002e61d`: `AcquireIpAttempts`

## pseudocode

```c
__int64 __fastcall RegReadConfigSettings(CRegistry *this, int a2, __int64 a3)
{
  bool v6; // zf
  int v7; // eax
  int v8; // ecx
  int v9; // ecx
  BOOL v10; // eax
  int v11; // eax
  int v12; // r10d
  int v13; // r11d
  int v14; // r10d
  int v15; // r11d
  unsigned int RegString; // eax
  __int64 v17; // rcx
  DWORD v18; // eax
  int v19; // eax
  _BYTE *v20; // rax
  int v21; // eax
  int v22; // ecx
  int v23; // eax
  int v24; // ecx
  int v25; // eax
  int v26; // ecx
  int v27; // eax
  LPCWSTR lpSrc[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int Dst; // [rsp+68h] [rbp+38h] BYREF
  unsigned int v31; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int16 *v32; // [rsp+78h] [rbp+48h] BYREF

  LODWORD(v32) = 0;
  Dst = 0;
  v31 = 0;
  v6 = CRegistry::ReadRegDWord(this, L"EnableVirtualIP", &Dst) == 0;
  v7 = 0;
  if ( v6 )
  {
    v8 = a2;
    LOBYTE(v7) = Dst != 0;
  }
  else
  {
    v8 = 0;
  }
  *(_DWORD *)(a3 + 4) = v7;
  *(_DWORD *)a3 = v8;
  if ( CRegistry::ReadRegDWord(this, L"VirtualMode", &v31) )
  {
    v9 = 0;
    v10 = 1;
  }
  else
  {
    v9 = a2;
    v10 = v31 != 0;
  }
  *(_DWORD *)(a3 + 12) = v10;
  *(_DWORD *)(a3 + 8) = v9;
  *(_DWORD *)(a3 + 20) = 0;
  *(_DWORD *)(a3 + 16) = a2;
  if ( *(_DWORD *)(a3 + 4) )
  {
    if ( CRegistry::ReadRegDWord(this, L"VirtualizeLoopbackAdresses", &Dst) )
      *(_DWORD *)(a3 + 16) = 0;
    else
      *(_DWORD *)(a3 + 20) = Dst != 0;
  }
  if ( CRegistry::ReadRegDWord(this, L"MaxCacheIP", &v31) || v31 >= 0xA )
  {
    *(_DWORD *)(a3 + 28) = 2;
    v11 = 0;
  }
  else
  {
    *(_DWORD *)(a3 + 28) = v31;
    v11 = a2;
  }
  *(_DWORD *)(a3 + 24) = v11;
  lpSrc[0] = 0;
  Dst = 0;
  if ( CRegistry::ReadRegString(this, L"AdapterAddress", (unsigned __int16 **)lpSrc, &Dst) || Dst >> 1 >= 0x101 )
  {
    v13 = 0;
    v12 = 0;
  }
  else
  {
    StringCchCopyW((unsigned __int16 *)(a3 + 36), 0x101u, lpSrc[0]);
    v13 = a2;
  }
  *(_DWORD *)(a3 + 552) = v12;
  *(_DWORD *)(a3 + 32) = v13;
  lpSrc[0] = 0;
  Dst = 0;
  if ( CRegistry::ReadRegString(this, L"VIPAdapter", (unsigned __int16 **)lpSrc, &Dst) || Dst >> 1 >= 0x201 )
  {
    v15 = 0;
    v14 = 0;
  }
  else
  {
    StringCchCopyW((unsigned __int16 *)(a3 + 560), 0x201u, lpSrc[0]);
    v15 = a2;
  }
  *(_DWORD *)(a3 + 1588) = v14;
  *(_DWORD *)(a3 + 556) = v15;
  lpSrc[0] = 0;
  RegString = CRegistry::ReadRegString(this, L"IPPool", (unsigned __int16 **)lpSrc, (unsigned int *)&v32);
  v17 = 522;
  if ( RegString || (unsigned int)v32 >= 0x20A )
  {
    v20 = (_BYTE *)(a3 + 1596);
    do
    {
      *v20++ = 0;
      --v17;
    }
    while ( v17 );
    v19 = 0;
  }
  else
  {
    v18 = ExpandEnvironmentStringsW(lpSrc[0], (LPWSTR)&Dst, 0);
    if ( !v18 || v18 <= 0x105 && !ExpandEnvironmentStringsW(lpSrc[0], (LPWSTR)(a3 + 1596), 0x105u) )
      GetLastError();
    v19 = a2;
  }
  *(_DWORD *)(a3 + 1592) = v19;
  v6 = CRegistry::ReadRegDWord(this, L"AllowPerSessionInMultiNIC", &v31) == 0;
  v21 = 0;
  if ( v6 )
  {
    v22 = a2;
    LOBYTE(v21) = v31 != 0;
  }
  else
  {
    v22 = 0;
  }
  *(_DWORD *)(a3 + 2124) = v21;
  *(_DWORD *)(a3 + 2120) = v22;
  v32 = 0;
  Dst = 0;
  if ( !CRegistry::ReadRegString(this, L"RpcUUID", &v32, &Dst) && (Dst & 0xFFFFFFFE) < 0x102 )
    StringCchCopyW((unsigned __int16 *)(a3 + 2128), 0x81u, v32);
  v6 = CRegistry::ReadRegDWord(this, L"PromptOnIPLeaseFail", &v31) == 0;
  v23 = 0;
  if ( v6 )
  {
    v24 = a2;
    LOBYTE(v23) = v31 == 1;
  }
  else
  {
    v24 = 0;
  }
  *(_DWORD *)(a3 + 2392) = v23;
  *(_DWORD *)(a3 + 2388) = v24;
  v6 = CRegistry::ReadRegDWord(this, L"ForceLogoffOnIPLeaseFail", &v31) == 0;
  v25 = 0;
  if ( v6 )
  {
    v26 = a2;
    LOBYTE(v25) = v31 == 1;
  }
  else
  {
    v26 = 0;
  }
  *(_DWORD *)(a3 + 2400) = v25;
  *(_DWORD *)(a3 + 2396) = v26;
  if ( CRegistry::ReadRegDWord(this, L"AcquireIpAttempts", &v31) || !v31 )
  {
    *(_DWORD *)(a3 + 2408) = 10;
    v27 = 0;
  }
  else
  {
    *(_DWORD *)(a3 + 2408) = v31;
    v27 = a2;
  }
  *(_DWORD *)(a3 + 2404) = v27;
  if ( CRegistry::ReadRegDWord(this, L"AcquireIpRetrySleepTime", &v31) || v31 == -1 )
  {
    *(_DWORD *)(a3 + 2416) = 1000;
    a2 = 0;
  }
  else
  {
    *(_DWORD *)(a3 + 2416) = v31;
  }
  *(_DWORD *)(a3 + 2412) = a2;
  return 0;
}

```

## disassembly

```asm
0x18002e314  push    rbp
0x18002e316  push    rbx
0x18002e317  push    rsi
0x18002e318  push    rdi
0x18002e319  push    r14
0x18002e31b  mov     rbp, rsp
0x18002e31e  sub     rsp, 30h
0x18002e322  xor     r14d, r14d
0x18002e325  mov     rbx, r8
0x18002e328  mov     edi, edx
0x18002e32a  mov     dword ptr [rbp+arg_18], r14d
0x18002e32e  lea     r8, [rbp+Dst]; unsigned int *
0x18002e332  mov     [rbp+Dst], r14d
0x18002e336  lea     rdx, aEnablevirtuali; "EnableVirtualIP"
0x18002e33d  mov     [rbp+arg_10], r14d
0x18002e341  mov     rsi, rcx
0x18002e344  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18002e349  test    eax, eax
0x18002e34b  mov     eax, r14d
0x18002e34e  jnz     short loc_18002E35B
0x18002e350  cmp     [rbp+Dst], r14d
0x18002e354  mov     ecx, edi
0x18002e356  setnz   al
0x18002e359  jmp     short loc_18002E35E
0x18002e35b  mov     ecx, r14d
0x18002e35e  mov     [rbx+4], eax
0x18002e361  lea     r8, [rbp+arg_10]; unsigned int *
0x18002e365  mov     [rbx], ecx
0x18002e367  lea     rdx, aVirtualmode; "VirtualMode"
0x18002e36e  mov     rcx, rsi; this
0x18002e371  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18002e376  test    eax, eax
0x18002e378  jnz     short loc_18002E388
0x18002e37a  cmp     [rbp+arg_10], r14d
0x18002e37e  mov     eax, r14d
0x18002e381  mov     ecx, edi
0x18002e383  setnz   al
0x18002e386  jmp     short loc_18002E390
0x18002e388  mov     ecx, r14d
0x18002e38b  mov     eax, 1
0x18002e390  mov     [rbx+0Ch], eax
0x18002e393  mov     [rbx+8], ecx
0x18002e396  mov     [rbx+14h], r14d
0x18002e39a  mov     [rbx+10h], edi
0x18002e39d  cmp     [rbx+4], r14d
0x18002e3a1  jz      short loc_18002E3CD
0x18002e3a3  lea     r8, [rbp+Dst]; unsigned int *
0x18002e3a7  mov     rcx, rsi; this
0x18002e3aa  lea     rdx, aVirtualizeloop; "VirtualizeLoopbackAdresses"
0x18002e3b1  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18002e3b6  test    eax, eax
0x18002e3b8  jnz     short loc_18002E3C9
0x18002e3ba  cmp     [rbp+Dst], r14d
0x18002e3be  mov     eax, r14d
0x18002e3c1  setnz   al
0x18002e3c4  mov     [rbx+14h], eax
0x18002e3c7  jmp     short loc_18002E3CD
0x18002e3c9  mov     [rbx+10h], r14d
0x18002e3cd  lea     r8, [rbp+arg_10]; unsigned int *
0x18002e3d1  mov     rcx, rsi; this
0x18002e3d4  lea     rdx, aMaxcacheip; "MaxCacheIP"
0x18002e3db  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18002e3e0  test    eax, eax
0x18002e3e2  jnz     short loc_18002E3F3
0x18002e3e4  mov     eax, [rbp+arg_10]
0x18002e3e7  cmp     eax, 0Ah
0x18002e3ea  jnb     short loc_18002E3F3
0x18002e3ec  mov     [rbx+1Ch], eax
0x18002e3ef  mov     eax, edi
0x18002e3f1  jmp     short loc_18002E3FD
0x18002e3f3  mov     dword ptr [rbx+1Ch], 2
0x18002e3fa  mov     eax, r14d
0x18002e3fd  mov     [rbx+18h], eax
0x18002e400  lea     r9, [rbp+Dst]; unsigned int *
0x18002e404  lea     r8, [rbp+lpSrc]; unsigned __int16 **
0x18002e408  mov     [rbp+lpSrc], r14
0x18002e40c  lea     rdx, ValueName; "AdapterAddress"
0x18002e413  mov     [rbp+Dst], r14d
0x18002e417  mov     rcx, rsi; this
0x18002e41a  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x18002e41f  test    eax, eax
0x18002e421  jnz     short loc_18002E446
0x18002e423  mov     eax, [rbp+Dst]
0x18002e426  mov     edx, 101h; unsigned __int64
0x18002e42b  shr     eax, 1
0x18002e42d  mov     r10d, eax
0x18002e430  cmp     eax, edx
0x18002e432  jnb     short loc_18002E446
0x18002e434  mov     r8, [rbp+lpSrc]; unsigned __int16 *
0x18002e438  lea     rcx, [rbx+24h]; unsigned __int16 *
0x18002e43c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e441  mov     r11d, edi
0x18002e444  jmp     short loc_18002E44C
0x18002e446  mov     r11d, r14d
0x18002e449  mov     r10d, r14d
0x18002e44c  mov     [rbx+228h], r10d
0x18002e453  lea     r9, [rbp+Dst]; unsigned int *
0x18002e457  mov     [rbx+20h], r11d
0x18002e45b  lea     r8, [rbp+lpSrc]; unsigned __int16 **
0x18002e45f  lea     rdx, aVipadapter; "VIPAdapter"
0x18002e466  mov     [rbp+lpSrc], r14
0x18002e46a  mov     rcx, rsi; this
0x18002e46d  mov     [rbp+Dst], r14d
0x18002e471  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x18002e476  test    eax, eax
0x18002e478  jnz     short loc_18002E4A0
0x18002e47a  mov     eax, [rbp+Dst]
0x18002e47d  mov     edx, 201h; unsigned __int64
0x18002e482  shr     eax, 1
0x18002e484  mov     r10d, eax
0x18002e487  cmp     eax, edx
0x18002e489  jnb     short loc_18002E4A0
0x18002e48b  mov     r8, [rbp+lpSrc]; unsigned __int16 *
0x18002e48f  lea     rcx, [rbx+230h]; unsigned __int16 *
0x18002e496  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e49b  mov     r11d, edi
0x18002e49e  jmp     short loc_18002E4A6
0x18002e4a0  mov     r11d, r14d
0x18002e4a3  mov     r10d, r14d
0x18002e4a6  mov     [rbx+634h], r10d
0x18002e4ad  lea     r9, [rbp+arg_18]; unsigned int *
0x18002e4b1  mov     [rbx+22Ch], r11d
0x18002e4b8  lea     r8, [rbp+lpSrc]; unsigned __int16 **
0x18002e4bc  lea     rdx, aIppool; "IPPool"
0x18002e4c3  mov     [rbp+lpSrc], r14
0x18002e4c7  mov     rcx, rsi; this
0x18002e4ca  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x18002e4cf  mov     ecx, 20Ah
0x18002e4d4  test    eax, eax
0x18002e4d6  jnz     short loc_18002E51C
0x18002e4d8  cmp     dword ptr [rbp+arg_18], ecx
0x18002e4db  jnb     short loc_18002E51C
0x18002e4dd  mov     rcx, [rbp+lpSrc]; lpSrc
0x18002e4e1  lea     rdx, [rbp+Dst]; lpDst
0x18002e4e5  xor     r8d, r8d; nSize
0x18002e4e8  call    cs:__imp_ExpandEnvironmentStringsW
0x18002e4ee  test    eax, eax
0x18002e4f0  jz      short loc_18002E512
0x18002e4f2  mov     r8d, 105h; nSize
0x18002e4f8  cmp     eax, r8d
0x18002e4fb  ja      short loc_18002E518
0x18002e4fd  mov     rcx, [rbp+lpSrc]; lpSrc
0x18002e501  lea     rdx, [rbx+63Ch]; lpDst
0x18002e508  call    cs:__imp_ExpandEnvironmentStringsW
0x18002e50e  test    eax, eax
0x18002e510  jnz     short loc_18002E518
0x18002e512  call    cs:__imp_GetLastError
0x18002e518  mov     eax, edi
0x18002e51a  jmp     short loc_18002E532
0x18002e51c  lea     rax, [rbx+63Ch]
0x18002e523  mov     [rax], r14b
0x18002e526  inc     rax
0x18002e529  sub     rcx, 1
0x18002e52d  jnz     short loc_18002E523
0x18002e52f  mov     eax, r14d
0x18002e532  lea     r8, [rbp+arg_10]; unsigned int *
0x18002e536  mov     [rbx+638h], eax
0x18002e53c  lea     rdx, aAllowpersessio; "AllowPerSessionInMultiNIC"
0x18002e543  mov     rcx, rsi; this
0x18002e546  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18002e54b  test    eax, eax
0x18002e54d  mov     eax, r14d
0x18002e550  jnz     short loc_18002E55D
0x18002e552  cmp     [rbp+arg_10], r14d
0x18002e556  mov     ecx, edi
0x18002e558  setnz   al
0x18002e55b  jmp     short loc_18002E560
0x18002e55d  mov     ecx, r14d
0x18002e560  mov     [rbx+84Ch], eax
0x18002e566  lea     r9, [rbp+Dst]; unsigned int *
0x18002e56a  mov     [rbx+848h], ecx
0x18002e570  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x18002e574  mov     rcx, rsi; this
0x18002e577  mov     [rbp+arg_18], r14
0x18002e57b  lea     rdx, aRpcuuid; "RpcUUID"
0x18002e582  mov     [rbp+Dst], r14d
0x18002e586  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x18002e58b  test    eax, eax
0x18002e58d  jnz     short loc_18002E5B1
0x18002e58f  mov     eax, [rbp+Dst]
0x18002e592  and     eax, 0FFFFFFFEh
0x18002e595  cmp     eax, 102h
0x18002e59a  jnb     short loc_18002E5B1
0x18002e59c  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x18002e5a0  lea     rcx, [rbx+850h]; unsigned __int16 *
0x18002e5a7  mov     edx, 81h; unsigned __int64
0x18002e5ac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e5b1  lea     r8, [rbp+arg_10]; unsigned int *
0x18002e5b5  mov     rcx, rsi; this
0x18002e5b8  lea     rdx, aPromptonipleas; "PromptOnIPLeaseFail"
0x18002e5bf  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18002e5c4  test    eax, eax
0x18002e5c6  mov     eax, r14d
0x18002e5c9  jnz     short loc_18002E5D6
0x18002e5cb  cmp     [rbp+arg_10], 1
0x18002e5cf  mov     ecx, edi
0x18002e5d1  setz    al
0x18002e5d4  jmp     short loc_18002E5D9
0x18002e5d6  mov     ecx, r14d
0x18002e5d9  mov     [rbx+958h], eax
0x18002e5df  lea     r8, [rbp+arg_10]; unsigned int *
0x18002e5e3  mov     [rbx+954h], ecx
0x18002e5e9  lea     rdx, aForcelogoffoni; "ForceLogoffOnIPLeaseFail"
0x18002e5f0  mov     rcx, rsi; this
0x18002e5f3  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18002e5f8  test    eax, eax
0x18002e5fa  mov     eax, r14d
0x18002e5fd  jnz     short loc_18002E60A
0x18002e5ff  cmp     [rbp+arg_10], 1
0x18002e603  mov     ecx, edi
0x18002e605  setz    al
0x18002e608  jmp     short loc_18002E60D
0x18002e60a  mov     ecx, r14d
0x18002e60d  mov     [rbx+960h], eax
0x18002e613  lea     r8, [rbp+arg_10]; unsigned int *
0x18002e617  mov     [rbx+95Ch], ecx
0x18002e61d  lea     rdx, aAcquireipattem; "AcquireIpAttempts"
0x18002e624  mov     rcx, rsi; this
0x18002e627  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18002e62c  test    eax, eax
0x18002e62e  jnz     short loc_18002E641
0x18002e630  mov     eax, [rbp+arg_10]
0x18002e633  test    eax, eax
0x18002e635  jz      short loc_18002E641
0x18002e637  mov     [rbx+968h], eax
0x18002e63d  mov     eax, edi
0x18002e63f  jmp     short loc_18002E64E
0x18002e641  mov     dword ptr [rbx+968h], 0Ah
0x18002e64b  mov     eax, r14d
0x18002e64e  lea     r8, [rbp+arg_10]; unsigned int *
0x18002e652  mov     [rbx+964h], eax
0x18002e658  lea     rdx, aAcquireipretry; "AcquireIpRetrySleepTime"
0x18002e65f  mov     rcx, rsi; this
0x18002e662  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18002e667  test    eax, eax
0x18002e669  jnz     short loc_18002E67B
0x18002e66b  mov     eax, [rbp+arg_10]
0x18002e66e  cmp     eax, 0FFFFFFFFh
0x18002e671  jz      short loc_18002E67B
0x18002e673  mov     [rbx+970h], eax
0x18002e679  jmp     short loc_18002E688
0x18002e67b  mov     dword ptr [rbx+970h], 3E8h
0x18002e685  mov     edi, r14d
0x18002e688  mov     [rbx+96Ch], edi
0x18002e68e  xor     eax, eax
0x18002e690  add     rsp, 30h
0x18002e694  pop     r14
0x18002e696  pop     rdi
0x18002e697  pop     rsi
0x18002e698  pop     rbx
0x18002e699  pop     rbp
0x18002e69a  retn
```
