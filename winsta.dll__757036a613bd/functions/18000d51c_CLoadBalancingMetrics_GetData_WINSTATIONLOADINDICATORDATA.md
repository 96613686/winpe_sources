# CLoadBalancingMetrics::GetData(_WINSTATIONLOADINDICATORDATA *)

- ea: `0x18000d51c`
- end: `0x18000db64`
- name: `?GetData@CLoadBalancingMetrics@@QEAAKPEAU_WINSTATIONLOADINDICATORDATA@@@Z`
- size: `1608`
- prototype: `unsigned int __fastcall(CLoadBalancingMetrics *__hidden this, struct _WINSTATIONLOADINDICATORDATA *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c820`

## callees

- `0x180007890`
- `0x18000d51c`
- `0x18000db70`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18000d64a`
- `ntdll!NtQuerySystemInformation` at `0x18000d662`
- `ntdll!NtQuerySystemInformation` at `0x18000d67f`
- `ntdll!NtQuerySystemInformation` at `0x18000d64a`
- `ntdll!NtQuerySystemInformation` at `0x18000d662`
- `ntdll!NtQuerySystemInformation` at `0x18000d67f`

## string_xrefs

- `0x18000d98c`: `Remaining Sessions:   Raw: [%4ld], Est: [%4ld], Factor = %s, Commit = %ld`
- `0x18000d6f0`: `   Commit:       Base [%6ld], Used [%6ld], Avail: [%6ld], AvgPerUser: [%6ld]%s`
- `0x18000d7cb`: `   Session Raw: Commit  [%4ld], Pte    [%4ld], Paged    [%4ld]`
- `0x18000d8c8`: `   Session Avg: Commit  [%4ld], Pte    [%4ld], Paged    [%4ld]`
- `0x18000db2c`: `SystemPtes`

## pseudocode

```c
__int64 __fastcall CLoadBalancingMetrics::GetData(CLoadBalancingMetrics *this, struct _WINSTATIONLOADINDICATORDATA *a2)
{
  __int64 i; // rcx
  unsigned int v5; // r9d
  unsigned int v6; // r8d
  unsigned int v7; // r15d
  NTSTATUS v8; // r12d
  NTSTATUS v9; // r13d
  NTSTATUS v10; // eax
  unsigned int v11; // ecx
  unsigned int v12; // r10d
  unsigned int v13; // r12d
  unsigned int v14; // r8d
  int v15; // edx
  int v16; // r9d
  const char *v17; // rax
  unsigned int v18; // r10d
  unsigned int v19; // r8d
  unsigned int v20; // ecx
  unsigned int v21; // r9d
  __int64 v22; // r8
  unsigned int v23; // ecx
  unsigned int v24; // eax
  int v25; // r9d
  __int64 v26; // rax
  unsigned int v27; // r10d
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r13
  __int64 v31; // rax
  unsigned int v32; // ecx
  unsigned int v33; // r14d
  unsigned int v34; // r14d
  unsigned int v35; // r8d
  unsigned int v36; // r9d
  int v37; // ecx
  int v38; // eax
  unsigned int v39; // r10d
  unsigned int v40; // ecx
  unsigned int v41; // eax
  unsigned int v42; // r8d
  int v43; // r12d
  unsigned int v44; // eax
  unsigned int v45; // ecx
  int v46; // ecx
  const char *v47; // rax
  __int64 v49; // r9
  __int64 v50; // r8
  int v51; // [rsp+40h] [rbp-C0h]
  __int64 v52; // [rsp+48h] [rbp-B8h]
  int v53; // [rsp+50h] [rbp-B0h]
  _BYTE v54[48]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v55; // [rsp+90h] [rbp-70h]
  int v56; // [rsp+94h] [rbp-6Ch]
  unsigned int v57; // [rsp+D0h] [rbp-30h]
  unsigned int v58; // [rsp+E8h] [rbp-18h]
  unsigned int v59; // [rsp+100h] [rbp+0h]
  _BYTE SystemInformation[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v61; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v62[4]; // [rsp+224h] [rbp+124h]
  _QWORD v63[2]; // [rsp+228h] [rbp+128h]
  int v64; // [rsp+238h] [rbp+138h]
  int v65; // [rsp+250h] [rbp+150h]
  _QWORD v66[192]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(v54, 0, 0x178u);
  memset_0(SystemInformation, 0, sizeof(SystemInformation));
  v61 = 5;
  v64 = 4;
  v65 = 6;
  if ( (unsigned __int8)WinStationGetTermSrvCountersValue(0, 3u, &v61) )
  {
    if ( v62[0] )
      *((_DWORD *)this + 26) = v63[0];
    for ( i = 0; i != 3; ++i )
    {
      if ( v62[24 * i] )
        *((_DWORD *)this + 25) += LODWORD(v63[3 * i]);
    }
  }
  else
  {
    *((_DWORD *)this + 25) = 1;
  }
  *(_OWORD *)((char *)a2 + 36) = 0;
  *(_OWORD *)((char *)a2 + 52) = 0;
  *((_DWORD *)a2 + 17) = 0;
  v5 = *((_DWORD *)this + 24);
  v6 = *((_DWORD *)this + 25);
  if ( v6 <= v5 )
    v7 = 1;
  else
    v7 = v6 - v5;
  _DbgPrintMessage(1, "Session Statistics: Total [%ld], Idle [%ld], Disc [%ld]", v6, v5, *((_DWORD *)this + 26));
  v8 = NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
  v9 = NtQuerySystemInformation(SystemPerformanceInformation, v54, 0x178u, 0);
  v10 = NtQuerySystemInformation(SystemProcessorPerformanceInformation, v66, 0x600u, 0);
  if ( *(_BYTE *)this && v9 >= 0 && v10 >= 0 && v8 >= 0 )
  {
    v11 = v55;
    v12 = *((_DWORD *)this + 6);
    v13 = v56 - v55;
    if ( v12 < v55 )
    {
      v16 = v55 - v12;
      v15 = 0;
      v14 = (v55 - v12) / v7;
      if ( v14 <= *((_DWORD *)this + 9) )
        v14 = *((_DWORD *)this + 9);
    }
    else
    {
      v14 = *((_DWORD *)this + 9);
      v15 = 1;
      *((_DWORD *)this + 6) = v55;
      v16 = 0;
      v12 = v11;
    }
    *((_DWORD *)this + 12) = v16;
    *((_DWORD *)this + 15) = v14;
    v17 = "*";
    if ( !v15 )
      v17 = (const char *)&byte_18003E6E1;
    _DbgPrintMessage(
      1,
      "   Commit:       Base [%6ld], Used [%6ld], Avail: [%6ld], AvgPerUser: [%6ld]%s",
      v12,
      v16,
      v13,
      v14,
      v17);
    v18 = *((_DWORD *)this + 4);
    v19 = v58;
    if ( v18 > v58 )
    {
      v21 = v18 - v58;
      v20 = (v18 - v58) / v7;
      if ( v20 <= *((_DWORD *)this + 7) )
        v20 = *((_DWORD *)this + 7);
    }
    else
    {
      v20 = *((_DWORD *)this + 7);
      *((_DWORD *)this + 4) = v58;
      v21 = 0;
      v18 = v19;
    }
    *((_DWORD *)this + 10) = v21;
    *((_DWORD *)this + 13) = v20;
    _DbgPrintMessage(1, "   Ptes:         Base [%6ld], Used [%6ld], Avail: [%6ld], AvgPerUser: [%6ld]%s\n", v18);
    v22 = *((unsigned int *)this + 5);
    v23 = v57;
    if ( (unsigned int)v22 < v57 )
    {
      v25 = v57 - v22;
      v24 = (v57 - (unsigned int)v22) / v7;
      if ( v24 <= *((_DWORD *)this + 8) )
        v24 = *((_DWORD *)this + 8);
    }
    else
    {
      v24 = *((_DWORD *)this + 8);
      *((_DWORD *)this + 5) = v57;
      v25 = 0;
      v22 = v23;
    }
    *((_DWORD *)this + 11) = v25;
    *((_DWORD *)this + 14) = v24;
    _DbgPrintMessage(1, "   PagedPool:    Base [%6ld], Used [%6ld], Avail: [%6ld], AvgPerUser: [%6ld]%s", v22);
    _DbgPrintMessage(
      1,
      "   Session Raw: Commit  [%4ld], Pte    [%4ld], Paged    [%4ld]",
      v13 / *((_DWORD *)this + 15),
      v58 / *((_DWORD *)this + 13),
      v59 / *((_DWORD *)this + 14));
    v26 = 0;
    v27 = 0;
    v28 = 0;
    if ( *((_DWORD *)this + 1) )
    {
      v49 = 0;
      do
      {
        ++v27;
        v50 = 6 * v49++;
        v28 += v66[v50];
        v26 += v66[v50 + 1] + v66[v50 + 2];
      }
      while ( v27 < *((_DWORD *)this + 1) );
    }
    v29 = v28 - *((_QWORD *)this + 11);
    v30 = v26 - *((_QWORD *)this + 10);
    v52 = v29 >> 32;
    v53 = v29;
    *((_QWORD *)this + 11) = v28;
    *((_QWORD *)this + 10) = v26;
    if ( v30 )
      v31 = (v29 << 8) / v30;
    else
      LODWORD(v31) = 0;
    v51 = v31;
    v32 = (unsigned int)(v31 + 2 * *((_DWORD *)this + 18) + *((_DWORD *)this + 18)) >> 2;
    *((_DWORD *)this + 18) = v32;
    if ( 255 - v32 - 1 > 0xFE )
      v33 = -1;
    else
      v33 = (v7 << 8) / (255 - v32);
    if ( v33 <= v7 )
      v34 = 1;
    else
      v34 = v33 - v7;
    v35 = *((_DWORD *)this + 14) + (*((_DWORD *)this + 14) >> 1);
    v36 = *((_DWORD *)this + 13) + (*((_DWORD *)this + 13) >> 1);
    v37 = v59 / v35;
    v38 = v58 / v36;
    v39 = *((_DWORD *)this + 15) + (*((_DWORD *)this + 15) >> 1);
    *((_DWORD *)this + 13) = v36;
    *((_DWORD *)this + 14) = v35;
    *((_DWORD *)this + 15) = v39;
    _DbgPrintMessage(1, "   Session Avg: Commit  [%4ld], Pte    [%4ld], Paged    [%4ld]", v13 / v39, v38, v37);
    _DbgPrintMessage(
      1,
      "   CPU Idle:    Current [%4ld], Avg    [%4ld], Est      [%4ld]",
      100 * v51 / 0xFFu,
      100 * *((_DWORD *)this + 18) / 0xFFu,
      v34);
    v40 = v13 / *((_DWORD *)this + 15);
    *((_DWORD *)a2 + 12) = v40;
    v41 = v58 / *((_DWORD *)this + 13);
    *((_DWORD *)a2 + 13) = v41;
    v42 = v41;
    v43 = (v41 < v40) + 3;
    if ( v41 >= v40 )
      v42 = v40;
    v44 = v59 / *((_DWORD *)this + 14);
    *((_DWORD *)a2 + 10) = v44;
    v45 = v44;
    if ( v44 < v42 )
      v43 = 1;
    else
      v45 = v42;
    *((_DWORD *)this + 16) = v45;
    if ( v34 >= v45 )
      v34 = v45;
    else
      v43 = 5;
    v46 = v55;
    *((_DWORD *)a2 + 14) = v44;
    *((_DWORD *)this + 17) = v34;
    switch ( v43 )
    {
      case 3:
        v47 = "Available Memory";
        break;
      case 4:
        v47 = "SystemPtes";
        break;
      case 1:
        v47 = "PagedPool";
        break;
      default:
        v47 = "CPU";
        if ( v43 != 5 )
          v47 = "Unknown!";
        break;
    }
    _DbgPrintMessage(
      1,
      "Remaining Sessions:   Raw: [%4ld], Est: [%4ld], Factor = %s, Commit = %ld",
      *((_DWORD *)this + 16),
      v34,
      v47,
      v46);
    *(_DWORD *)a2 = *((_DWORD *)this + 17);
    *((_DWORD *)a2 + 8) = *((_DWORD *)this + 16);
    *((_DWORD *)a2 + 1) = v43;
    *((_DWORD *)a2 + 2) = v7;
    *((_DWORD *)a2 + 3) = *((_DWORD *)this + 26);
    *((_DWORD *)a2 + 5) = v52;
    *((_DWORD *)a2 + 4) = v53;
    *((_QWORD *)a2 + 3) = v30;
  }
  else
  {
    *((_DWORD *)this + 16) = -1;
    *(_DWORD *)a2 = -1;
    *((_DWORD *)a2 + 8) = *((_DWORD *)this + 16);
    *((_DWORD *)a2 + 1) = 0;
    *((_DWORD *)a2 + 2) = v7;
    *((_DWORD *)a2 + 3) = *((_DWORD *)this + 26);
    *((_QWORD *)a2 + 2) = 99;
    *((_QWORD *)a2 + 3) = 100;
    _DbgPrintMessage(
      8,
      "GetLoadMetrics failed: init [%ld], Proc [%lx], Perf [%lx], Basic [%lx]!",
      *(unsigned __int8 *)this,
      v10,
      v9,
      v8);
  }
  return *((unsigned int *)this + 16);
}

```

## disassembly

```asm
0x18000d51c  mov     [rsp-8+arg_10], rbx
0x18000d521  push    rbp
0x18000d522  push    rsi
0x18000d523  push    rdi
0x18000d524  push    r12
0x18000d526  push    r13
0x18000d528  push    r14
0x18000d52a  push    r15
0x18000d52c  lea     rbp, [rsp-780h]
0x18000d534  sub     rsp, 880h
0x18000d53b  mov     rax, cs:__security_cookie
0x18000d542  xor     rax, rsp
0x18000d545  mov     [rbp+7B0h+var_40], rax
0x18000d54c  mov     rdi, rdx
0x18000d54f  mov     rbx, rcx
0x18000d552  mov     r13d, 178h
0x18000d558  lea     rcx, [rsp+8B0h+var_850]; void *
0x18000d55d  mov     r8d, r13d; Size
0x18000d560  xor     edx, edx; Val
0x18000d562  call    memset_0
0x18000d567  mov     r12d, 40h ; '@'
0x18000d56d  lea     rcx, [rbp+7B0h+SystemInformation]; void *
0x18000d574  mov     r8d, r12d; Size
0x18000d577  xor     edx, edx; Val
0x18000d579  call    memset_0
0x18000d57e  xor     r14d, r14d
0x18000d581  mov     [rbp+7B0h+var_690], 5
0x18000d58b  lea     r8, [rbp+7B0h+var_690]; void *
0x18000d592  mov     [rsp+8B0h+var_868], r14
0x18000d597  lea     edx, [r12-3Dh]; unsigned int
0x18000d59c  mov     [rsp+8B0h+var_870], r14
0x18000d5a1  xor     ecx, ecx; this
0x18000d5a3  mov     [rbp+7B0h+var_678], 4
0x18000d5ad  mov     [rbp+7B0h+var_660], 6
0x18000d5b7  call    WinStationGetTermSrvCountersValue
0x18000d5bc  test    al, al
0x18000d5be  jz      short loc_18000D5F7
0x18000d5c0  cmp     [rbp+7B0h+var_68C], r14b
0x18000d5c7  jz      short loc_18000D5D2
0x18000d5c9  mov     eax, [rbp+7B0h+var_688]
0x18000d5cf  mov     [rbx+68h], eax
0x18000d5d2  mov     rcx, r14
0x18000d5d5  mov     esi, 1
0x18000d5da  lea     rax, [rcx+rcx*2]
0x18000d5de  cmp     [rbp+rax*8+7B0h+var_68C], r14b
0x18000d5e6  jnz     loc_18000DAD5
0x18000d5ec  add     rcx, rsi
0x18000d5ef  cmp     rcx, 3
0x18000d5f3  jnz     short loc_18000D5DA
0x18000d5f5  jmp     short loc_18000D5FF
0x18000d5f7  mov     esi, 1
0x18000d5fc  mov     [rbx+64h], esi
0x18000d5ff  xorps   xmm0, xmm0
0x18000d602  xor     eax, eax
0x18000d604  movups  xmmword ptr [rdi+24h], xmm0
0x18000d608  movups  xmmword ptr [rdi+34h], xmm0
0x18000d60c  mov     [rdi+44h], eax
0x18000d60f  mov     r9d, [rbx+60h]
0x18000d613  mov     r8d, [rbx+64h]
0x18000d617  cmp     r8d, r9d
0x18000d61a  jbe     loc_18000DA08
0x18000d620  mov     r15d, r8d
0x18000d623  sub     r15d, r9d
0x18000d626  mov     eax, [rbx+68h]
0x18000d629  lea     rdx, aSessionStatist; "Session Statistics: Total [%ld], Idle ["...
0x18000d630  mov     ecx, esi; int
0x18000d632  mov     dword ptr [rsp+8B0h+var_890], eax
0x18000d636  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d63b  xor     r9d, r9d; ReturnLength
0x18000d63e  lea     rdx, [rbp+7B0h+SystemInformation]; SystemInformation
0x18000d645  mov     r8d, r12d; SystemInformationLength
0x18000d648  xor     ecx, ecx; SystemInformationClass
0x18000d64a  call    cs:__imp_NtQuerySystemInformation
0x18000d650  xor     r9d, r9d; ReturnLength
0x18000d653  lea     rdx, [rsp+8B0h+var_850]; SystemInformation
0x18000d658  mov     r8d, r13d; SystemInformationLength
0x18000d65b  mov     r12d, eax
0x18000d65e  lea     ecx, [r9+2]; SystemInformationClass
0x18000d662  call    cs:__imp_NtQuerySystemInformation
0x18000d668  xor     r9d, r9d; ReturnLength
0x18000d66b  lea     rdx, [rbp+7B0h+var_640]; SystemInformation
0x18000d672  mov     r8d, 600h; SystemInformationLength
0x18000d678  mov     r13d, eax
0x18000d67b  lea     ecx, [r9+8]; SystemInformationClass
0x18000d67f  call    cs:__imp_NtQuerySystemInformation
0x18000d685  mov     r9d, eax
0x18000d688  cmp     [rbx], r14b
0x18000d68b  jz      loc_18000DA10
0x18000d691  test    r13d, r13d
0x18000d694  js      loc_18000DA10
0x18000d69a  test    eax, eax
0x18000d69c  js      loc_18000DA10
0x18000d6a2  test    r12d, r12d
0x18000d6a5  js      loc_18000DA10
0x18000d6ab  mov     ecx, [rbp+7B0h+var_820]
0x18000d6ae  mov     r12d, [rbp+7B0h+var_81C]
0x18000d6b2  mov     r10d, [rbx+18h]
0x18000d6b6  sub     r12d, ecx
0x18000d6b9  cmp     r10d, ecx
0x18000d6bc  jb      loc_18000DAA6
0x18000d6c2  mov     r8d, [rbx+24h]
0x18000d6c6  mov     edx, esi
0x18000d6c8  mov     [rbx+18h], ecx
0x18000d6cb  mov     r9d, r14d
0x18000d6ce  mov     r10d, ecx
0x18000d6d1  test    edx, edx
0x18000d6d3  mov     [rbx+30h], r9d
0x18000d6d7  mov     [rbx+3Ch], r8d
0x18000d6db  lea     r14, asc_18003E5A8; "*"
0x18000d6e2  mov     rax, r14
0x18000d6e5  lea     r13, byte_18003E6E1
0x18000d6ec  cmovz   rax, r13
0x18000d6f0  lea     rdx, aCommitBase6ldU; "   Commit:       Base [%6ld], Used [%6l"...
0x18000d6f7  mov     [rsp+8B0h+var_880], rax
0x18000d6fc  mov     ecx, esi; int
0x18000d6fe  mov     [rsp+8B0h+var_888], r8d
0x18000d703  mov     r8d, r10d
0x18000d706  mov     dword ptr [rsp+8B0h+var_890], r12d
0x18000d70b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d710  mov     r10d, [rbx+10h]
0x18000d714  mov     r8d, [rbp+7B0h+var_7C8]
0x18000d718  cmp     r10d, r8d
0x18000d71b  ja      loc_18000DAE4
0x18000d721  mov     ecx, [rbx+1Ch]
0x18000d724  mov     edx, esi
0x18000d726  mov     [rbx+10h], r8d
0x18000d72a  xor     r9d, r9d
0x18000d72d  mov     r10d, r8d
0x18000d730  test    edx, edx
0x18000d732  mov     [rbx+28h], r9d
0x18000d736  mov     [rbx+34h], ecx
0x18000d739  lea     rdx, aPtesBase6ldUse; "   Ptes:         Base [%6ld], Used [%6l"...
0x18000d740  mov     rax, r14
0x18000d743  cmovz   rax, r13
0x18000d747  mov     [rsp+8B0h+var_880], rax
0x18000d74c  mov     [rsp+8B0h+var_888], ecx
0x18000d750  mov     ecx, esi; int
0x18000d752  mov     dword ptr [rsp+8B0h+var_890], r8d
0x18000d757  mov     r8d, r10d
0x18000d75a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d75f  mov     r8d, [rbx+14h]
0x18000d763  mov     ecx, [rbp+7B0h+var_7E0]
0x18000d766  cmp     r8d, ecx
0x18000d769  jb      loc_18000DB02
0x18000d76f  mov     eax, [rbx+20h]
0x18000d772  mov     edx, esi
0x18000d774  mov     [rbx+14h], ecx
0x18000d777  xor     r9d, r9d
0x18000d77a  mov     r8d, ecx
0x18000d77d  test    edx, edx
0x18000d77f  mov     [rbx+2Ch], r9d
0x18000d783  mov     [rbx+38h], eax
0x18000d786  lea     rdx, aPagedpoolBase6; "   PagedPool:    Base [%6ld], Used [%6l"...
0x18000d78d  cmovz   r14, r13
0x18000d791  mov     ecx, esi; int
0x18000d793  mov     [rsp+8B0h+var_880], r14
0x18000d798  mov     [rsp+8B0h+var_888], eax
0x18000d79c  mov     eax, [rbp+7B0h+var_7B0]
0x18000d79f  mov     dword ptr [rsp+8B0h+var_890], eax
0x18000d7a3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d7a8  mov     eax, [rbp+7B0h+var_7B0]
0x18000d7ab  xor     edx, edx
0x18000d7ad  div     dword ptr [rbx+38h]
0x18000d7b0  xor     edx, edx
0x18000d7b2  mov     ecx, eax
0x18000d7b4  mov     eax, [rbp+7B0h+var_7C8]
0x18000d7b7  div     dword ptr [rbx+34h]
0x18000d7ba  xor     edx, edx
0x18000d7bc  mov     dword ptr [rsp+8B0h+var_890], ecx
0x18000d7c0  mov     r9d, eax
0x18000d7c3  mov     ecx, esi; int
0x18000d7c5  mov     eax, r12d
0x18000d7c8  div     dword ptr [rbx+3Ch]
0x18000d7cb  lea     rdx, aSessionRawComm; "   Session Raw: Commit  [%4ld], Pte    "...
0x18000d7d2  mov     r8d, eax
0x18000d7d5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d7da  mov     rax, [rsp+8B0h+var_868]
0x18000d7df  xor     r10d, r10d
0x18000d7e2  mov     rcx, [rsp+8B0h+var_870]
0x18000d7e7  cmp     [rbx+4], r10d
0x18000d7eb  ja      loc_18000DA6E
0x18000d7f1  mov     rdx, rcx
0x18000d7f4  mov     r13, rax
0x18000d7f7  sub     rdx, [rbx+58h]
0x18000d7fb  sub     r13, [rbx+50h]
0x18000d7ff  mov     r8, rdx
0x18000d802  sar     r8, 20h
0x18000d806  mov     [rsp+8B0h+var_868], r8
0x18000d80b  mov     r8, r13
0x18000d80e  sar     r8, 20h
0x18000d812  mov     [rsp+8B0h+var_860], rdx
0x18000d817  mov     [rsp+8B0h+var_858], r8
0x18000d81c  mov     [rbx+58h], rcx
0x18000d820  mov     [rbx+50h], rax
0x18000d824  test    r13, r13
0x18000d827  jz      loc_18000DACE
0x18000d82d  mov     rax, rdx
0x18000d830  shl     rax, 8
0x18000d834  cqo
0x18000d836  idiv    r13
0x18000d839  mov     ecx, [rbx+48h]
0x18000d83c  mov     r8d, 0FFh
0x18000d842  mov     [rsp+8B0h+var_870], rax
0x18000d847  lea     eax, [rax+rcx*2]
0x18000d84a  add     ecx, eax
0x18000d84c  shr     ecx, 2
0x18000d84f  sub     r8d, ecx
0x18000d852  mov     [rbx+48h], ecx
0x18000d855  lea     eax, [r8-1]
0x18000d859  cmp     eax, 0FEh
0x18000d85e  ja      loc_18000DB1D
0x18000d864  mov     eax, r15d
0x18000d867  xor     edx, edx
0x18000d869  shl     eax, 8
0x18000d86c  div     r8d
0x18000d86f  mov     r14d, eax
0x18000d872  cmp     r14d, r15d
0x18000d875  jbe     loc_18000DA66
0x18000d87b  sub     r14d, r15d
0x18000d87e  mov     r8d, [rbx+38h]
0x18000d882  xor     edx, edx
0x18000d884  mov     eax, [rbp+7B0h+var_7B0]
0x18000d887  mov     r9d, [rbx+34h]
0x18000d88b  mov     r10d, [rbx+3Ch]
0x18000d88f  shr     r8d, 1
0x18000d892  add     r8d, [rbx+38h]
0x18000d896  div     r8d
0x18000d899  xor     edx, edx
0x18000d89b  shr     r9d, 1
0x18000d89e  add     r9d, [rbx+34h]
0x18000d8a2  mov     ecx, eax
0x18000d8a4  mov     eax, [rbp+7B0h+var_7C8]
0x18000d8a7  div     r9d
0x18000d8aa  xor     edx, edx
0x18000d8ac  shr     r10d, 1
0x18000d8af  add     r10d, [rbx+3Ch]
0x18000d8b3  mov     [rbx+34h], r9d
0x18000d8b7  mov     r9d, eax
0x18000d8ba  mov     eax, r12d
0x18000d8bd  mov     [rbx+38h], r8d
0x18000d8c1  div     r10d
0x18000d8c4  mov     dword ptr [rsp+8B0h+var_890], ecx
0x18000d8c8  lea     rdx, aSessionAvgComm; "   Session Avg: Commit  [%4ld], Pte    "...
0x18000d8cf  mov     r8d, eax
0x18000d8d2  mov     [rbx+3Ch], r10d
0x18000d8d6  mov     ecx, esi; int
0x18000d8d8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d8dd  imul    ecx, [rbx+48h], 64h ; 'd'
0x18000d8e1  mov     r8d, 80808081h
0x18000d8e7  mov     eax, r8d
0x18000d8ea  mov     dword ptr [rsp+8B0h+var_890], r14d
0x18000d8ef  mul     ecx
0x18000d8f1  imul    ecx, dword ptr [rsp+8B0h+var_870], 64h ; 'd'
0x18000d8f6  mov     eax, r8d
0x18000d8f9  mov     r9d, edx
0x18000d8fc  shr     r9d, 7
0x18000d900  mul     ecx
0x18000d902  mov     ecx, esi; int
0x18000d904  shr     edx, 7
0x18000d907  mov     r8d, edx
0x18000d90a  lea     rdx, aCpuIdleCurrent; "   CPU Idle:    Current [%4ld], Avg    "...
0x18000d911  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d916  xor     edx, edx
0x18000d918  mov     eax, r12d
0x18000d91b  div     dword ptr [rbx+3Ch]
0x18000d91e  xor     edx, edx
0x18000d920  mov     ecx, eax
0x18000d922  mov     [rdi+30h], eax
0x18000d925  mov     eax, [rbp+7B0h+var_7C8]
0x18000d928  div     dword ptr [rbx+34h]
0x18000d92b  cmp     eax, ecx
0x18000d92d  mov     [rdi+34h], eax
0x18000d930  mov     r8d, eax
0x18000d933  sbb     r12d, r12d
0x18000d936  neg     r12d
0x18000d939  add     r12d, 3
0x18000d93d  cmp     eax, ecx
0x18000d93f  mov     eax, [rbp+7B0h+var_7B0]
0x18000d942  cmovnb  r8d, ecx
0x18000d946  xor     edx, edx
0x18000d948  div     dword ptr [rbx+38h]
0x18000d94b  cmp     eax, r8d
0x18000d94e  mov     [rdi+28h], eax
0x18000d951  mov     ecx, eax
0x18000d953  cmovnb  ecx, r8d
0x18000d957  cmovb   r12d, esi
0x18000d95b  mov     [rbx+40h], ecx
0x18000d95e  cmp     r14d, ecx
0x18000d961  jnb     loc_18000DAC6
0x18000d967  mov     r12d, 5
0x18000d96d  mov     ecx, [rbp+7B0h+var_820]
0x18000d970  mov     [rdi+38h], eax
0x18000d973  mov     [rbx+44h], r14d
0x18000d977  cmp     r12d, 3
0x18000d97b  jnz     loc_18000DB26
0x18000d981  lea     rax, aAvailableMemor; "Available Memory"
0x18000d988  mov     r8d, [rbx+40h]
0x18000d98c  lea     rdx, aRemainingSessi; "Remaining Sessions:   Raw: [%4ld], Est:"...
0x18000d993  mov     [rsp+8B0h+var_888], ecx
0x18000d997  mov     r9d, r14d
  ... truncated ...
```
