# CLoadBalancingMetrics::GetData(_WINSTATIONLOADINDICATORDATA *)

- ea: `0x18000eda4`
- end: `0x18000f3ff`
- name: `?GetData@CLoadBalancingMetrics@@QEAAKPEAU_WINSTATIONLOADINDICATORDATA@@@Z`
- size: `1627`
- prototype: `unsigned int __fastcall(CLoadBalancingMetrics *__hidden this, struct _WINSTATIONLOADINDICATORDATA *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800096c0`

## callees

- `0x180005b40`
- `0x18000eda4`
- `0x18000f410`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18000eed2`
- `ntdll!NtQuerySystemInformation` at `0x18000eef0`
- `ntdll!NtQuerySystemInformation` at `0x18000ef13`
- `ntdll!NtQuerySystemInformation` at `0x18000eed2`
- `ntdll!NtQuerySystemInformation` at `0x18000eef0`
- `ntdll!NtQuerySystemInformation` at `0x18000ef13`

## string_xrefs

- `0x18000f226`: `Remaining Sessions:   Raw: [%4ld], Est: [%4ld], Factor = %s, Commit = %ld`
- `0x18000ef8a`: `   Commit:       Base [%6ld], Used [%6ld], Avail: [%6ld], AvgPerUser: [%6ld]%s`
- `0x18000f065`: `   Session Raw: Commit  [%4ld], Pte    [%4ld], Paged    [%4ld]`
- `0x18000f162`: `   Session Avg: Commit  [%4ld], Pte    [%4ld], Paged    [%4ld]`
- `0x18000f3c7`: `SystemPtes`

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
      v17 = (const char *)&byte_1800416E1;
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
0x18000eda4  mov     [rsp-8+arg_10], rbx
0x18000eda9  push    rbp
0x18000edaa  push    rsi
0x18000edab  push    rdi
0x18000edac  push    r12
0x18000edae  push    r13
0x18000edb0  push    r14
0x18000edb2  push    r15
0x18000edb4  lea     rbp, [rsp-780h]
0x18000edbc  sub     rsp, 880h
0x18000edc3  mov     rax, cs:__security_cookie
0x18000edca  xor     rax, rsp
0x18000edcd  mov     [rbp+7B0h+var_40], rax
0x18000edd4  mov     rdi, rdx
0x18000edd7  mov     rbx, rcx
0x18000edda  mov     r13d, 178h
0x18000ede0  lea     rcx, [rsp+8B0h+var_850]; void *
0x18000ede5  mov     r8d, r13d; Size
0x18000ede8  xor     edx, edx; Val
0x18000edea  call    memset_0
0x18000edef  mov     r12d, 40h ; '@'
0x18000edf5  lea     rcx, [rbp+7B0h+SystemInformation]; void *
0x18000edfc  mov     r8d, r12d; Size
0x18000edff  xor     edx, edx; Val
0x18000ee01  call    memset_0
0x18000ee06  xor     r14d, r14d
0x18000ee09  mov     [rbp+7B0h+var_690], 5
0x18000ee13  lea     r8, [rbp+7B0h+var_690]; void *
0x18000ee1a  mov     [rsp+8B0h+var_868], r14
0x18000ee1f  lea     edx, [r12-3Dh]; unsigned int
0x18000ee24  mov     [rsp+8B0h+var_870], r14
0x18000ee29  xor     ecx, ecx; this
0x18000ee2b  mov     [rbp+7B0h+var_678], 4
0x18000ee35  mov     [rbp+7B0h+var_660], 6
0x18000ee3f  call    WinStationGetTermSrvCountersValue
0x18000ee44  test    al, al
0x18000ee46  jz      short loc_18000EE7F
0x18000ee48  cmp     [rbp+7B0h+var_68C], r14b
0x18000ee4f  jz      short loc_18000EE5A
0x18000ee51  mov     eax, [rbp+7B0h+var_688]
0x18000ee57  mov     [rbx+68h], eax
0x18000ee5a  mov     rcx, r14
0x18000ee5d  mov     esi, 1
0x18000ee62  lea     rax, [rcx+rcx*2]
0x18000ee66  cmp     [rbp+rax*8+7B0h+var_68C], r14b
0x18000ee6e  jnz     loc_18000F370
0x18000ee74  add     rcx, rsi
0x18000ee77  cmp     rcx, 3
0x18000ee7b  jnz     short loc_18000EE62
0x18000ee7d  jmp     short loc_18000EE87
0x18000ee7f  mov     esi, 1
0x18000ee84  mov     [rbx+64h], esi
0x18000ee87  xorps   xmm0, xmm0
0x18000ee8a  xor     eax, eax
0x18000ee8c  movups  xmmword ptr [rdi+24h], xmm0
0x18000ee90  movups  xmmword ptr [rdi+34h], xmm0
0x18000ee94  mov     [rdi+44h], eax
0x18000ee97  mov     r9d, [rbx+60h]
0x18000ee9b  mov     r8d, [rbx+64h]
0x18000ee9f  cmp     r8d, r9d
0x18000eea2  jbe     loc_18000F2A3
0x18000eea8  mov     r15d, r8d
0x18000eeab  sub     r15d, r9d
0x18000eeae  mov     eax, [rbx+68h]
0x18000eeb1  lea     rdx, aSessionStatist; "Session Statistics: Total [%ld], Idle ["...
0x18000eeb8  mov     ecx, esi; int
0x18000eeba  mov     dword ptr [rsp+8B0h+var_890], eax
0x18000eebe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000eec3  xor     r9d, r9d; ReturnLength
0x18000eec6  lea     rdx, [rbp+7B0h+SystemInformation]; SystemInformation
0x18000eecd  mov     r8d, r12d; SystemInformationLength
0x18000eed0  xor     ecx, ecx; SystemInformationClass
0x18000eed2  call    cs:__imp_NtQuerySystemInformation
0x18000eed9  nop     dword ptr [rax+rax+00h]
0x18000eede  xor     r9d, r9d; ReturnLength
0x18000eee1  lea     rdx, [rsp+8B0h+var_850]; SystemInformation
0x18000eee6  mov     r8d, r13d; SystemInformationLength
0x18000eee9  mov     r12d, eax
0x18000eeec  lea     ecx, [r9+2]; SystemInformationClass
0x18000eef0  call    cs:__imp_NtQuerySystemInformation
0x18000eef7  nop     dword ptr [rax+rax+00h]
0x18000eefc  xor     r9d, r9d; ReturnLength
0x18000eeff  lea     rdx, [rbp+7B0h+var_640]; SystemInformation
0x18000ef06  mov     r8d, 600h; SystemInformationLength
0x18000ef0c  mov     r13d, eax
0x18000ef0f  lea     ecx, [r9+8]; SystemInformationClass
0x18000ef13  call    cs:__imp_NtQuerySystemInformation
0x18000ef1a  nop     dword ptr [rax+rax+00h]
0x18000ef1f  mov     r9d, eax
0x18000ef22  cmp     [rbx], r14b
0x18000ef25  jz      loc_18000F2AB
0x18000ef2b  test    r13d, r13d
0x18000ef2e  js      loc_18000F2AB
0x18000ef34  test    eax, eax
0x18000ef36  js      loc_18000F2AB
0x18000ef3c  test    r12d, r12d
0x18000ef3f  js      loc_18000F2AB
0x18000ef45  mov     ecx, [rbp+7B0h+var_820]
0x18000ef48  mov     r12d, [rbp+7B0h+var_81C]
0x18000ef4c  mov     r10d, [rbx+18h]
0x18000ef50  sub     r12d, ecx
0x18000ef53  cmp     r10d, ecx
0x18000ef56  jb      loc_18000F341
0x18000ef5c  mov     r8d, [rbx+24h]
0x18000ef60  mov     edx, esi
0x18000ef62  mov     [rbx+18h], ecx
0x18000ef65  mov     r9d, r14d
0x18000ef68  mov     r10d, ecx
0x18000ef6b  test    edx, edx
0x18000ef6d  mov     [rbx+30h], r9d
0x18000ef71  mov     [rbx+3Ch], r8d
0x18000ef75  lea     r14, asc_1800415A8; "*"
0x18000ef7c  mov     rax, r14
0x18000ef7f  lea     r13, byte_1800416E1
0x18000ef86  cmovz   rax, r13
0x18000ef8a  lea     rdx, aCommitBase6ldU; "   Commit:       Base [%6ld], Used [%6l"...
0x18000ef91  mov     [rsp+8B0h+var_880], rax
0x18000ef96  mov     ecx, esi; int
0x18000ef98  mov     [rsp+8B0h+var_888], r8d
0x18000ef9d  mov     r8d, r10d
0x18000efa0  mov     dword ptr [rsp+8B0h+var_890], r12d
0x18000efa5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000efaa  mov     r10d, [rbx+10h]
0x18000efae  mov     r8d, [rbp+7B0h+var_7C8]
0x18000efb2  cmp     r10d, r8d
0x18000efb5  ja      loc_18000F37F
0x18000efbb  mov     ecx, [rbx+1Ch]
0x18000efbe  mov     edx, esi
0x18000efc0  mov     [rbx+10h], r8d
0x18000efc4  xor     r9d, r9d
0x18000efc7  mov     r10d, r8d
0x18000efca  test    edx, edx
0x18000efcc  mov     [rbx+28h], r9d
0x18000efd0  mov     [rbx+34h], ecx
0x18000efd3  lea     rdx, aPtesBase6ldUse; "   Ptes:         Base [%6ld], Used [%6l"...
0x18000efda  mov     rax, r14
0x18000efdd  cmovz   rax, r13
0x18000efe1  mov     [rsp+8B0h+var_880], rax
0x18000efe6  mov     [rsp+8B0h+var_888], ecx
0x18000efea  mov     ecx, esi; int
0x18000efec  mov     dword ptr [rsp+8B0h+var_890], r8d
0x18000eff1  mov     r8d, r10d
0x18000eff4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000eff9  mov     r8d, [rbx+14h]
0x18000effd  mov     ecx, [rbp+7B0h+var_7E0]
0x18000f000  cmp     r8d, ecx
0x18000f003  jb      loc_18000F39D
0x18000f009  mov     eax, [rbx+20h]
0x18000f00c  mov     edx, esi
0x18000f00e  mov     [rbx+14h], ecx
0x18000f011  xor     r9d, r9d
0x18000f014  mov     r8d, ecx
0x18000f017  test    edx, edx
0x18000f019  mov     [rbx+2Ch], r9d
0x18000f01d  mov     [rbx+38h], eax
0x18000f020  lea     rdx, aPagedpoolBase6; "   PagedPool:    Base [%6ld], Used [%6l"...
0x18000f027  cmovz   r14, r13
0x18000f02b  mov     ecx, esi; int
0x18000f02d  mov     [rsp+8B0h+var_880], r14
0x18000f032  mov     [rsp+8B0h+var_888], eax
0x18000f036  mov     eax, [rbp+7B0h+var_7B0]
0x18000f039  mov     dword ptr [rsp+8B0h+var_890], eax
0x18000f03d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f042  mov     eax, [rbp+7B0h+var_7B0]
0x18000f045  xor     edx, edx
0x18000f047  div     dword ptr [rbx+38h]
0x18000f04a  xor     edx, edx
0x18000f04c  mov     ecx, eax
0x18000f04e  mov     eax, [rbp+7B0h+var_7C8]
0x18000f051  div     dword ptr [rbx+34h]
0x18000f054  xor     edx, edx
0x18000f056  mov     dword ptr [rsp+8B0h+var_890], ecx
0x18000f05a  mov     r9d, eax
0x18000f05d  mov     ecx, esi; int
0x18000f05f  mov     eax, r12d
0x18000f062  div     dword ptr [rbx+3Ch]
0x18000f065  lea     rdx, aSessionRawComm; "   Session Raw: Commit  [%4ld], Pte    "...
0x18000f06c  mov     r8d, eax
0x18000f06f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f074  mov     rax, [rsp+8B0h+var_868]
0x18000f079  xor     r10d, r10d
0x18000f07c  mov     rcx, [rsp+8B0h+var_870]
0x18000f081  cmp     [rbx+4], r10d
0x18000f085  ja      loc_18000F309
0x18000f08b  mov     rdx, rcx
0x18000f08e  mov     r13, rax
0x18000f091  sub     rdx, [rbx+58h]
0x18000f095  sub     r13, [rbx+50h]
0x18000f099  mov     r8, rdx
0x18000f09c  sar     r8, 20h
0x18000f0a0  mov     [rsp+8B0h+var_868], r8
0x18000f0a5  mov     r8, r13
0x18000f0a8  sar     r8, 20h
0x18000f0ac  mov     [rsp+8B0h+var_860], rdx
0x18000f0b1  mov     [rsp+8B0h+var_858], r8
0x18000f0b6  mov     [rbx+58h], rcx
0x18000f0ba  mov     [rbx+50h], rax
0x18000f0be  test    r13, r13
0x18000f0c1  jz      loc_18000F369
0x18000f0c7  mov     rax, rdx
0x18000f0ca  shl     rax, 8
0x18000f0ce  cqo
0x18000f0d0  idiv    r13
0x18000f0d3  mov     ecx, [rbx+48h]
0x18000f0d6  mov     r8d, 0FFh
0x18000f0dc  mov     [rsp+8B0h+var_870], rax
0x18000f0e1  lea     eax, [rax+rcx*2]
0x18000f0e4  add     ecx, eax
0x18000f0e6  shr     ecx, 2
0x18000f0e9  sub     r8d, ecx
0x18000f0ec  mov     [rbx+48h], ecx
0x18000f0ef  lea     eax, [r8-1]
0x18000f0f3  cmp     eax, 0FEh
0x18000f0f8  ja      loc_18000F3B8
0x18000f0fe  mov     eax, r15d
0x18000f101  xor     edx, edx
0x18000f103  shl     eax, 8
0x18000f106  div     r8d
0x18000f109  mov     r14d, eax
0x18000f10c  cmp     r14d, r15d
0x18000f10f  jbe     loc_18000F301
0x18000f115  sub     r14d, r15d
0x18000f118  mov     r8d, [rbx+38h]
0x18000f11c  xor     edx, edx
0x18000f11e  mov     eax, [rbp+7B0h+var_7B0]
0x18000f121  mov     r9d, [rbx+34h]
0x18000f125  mov     r10d, [rbx+3Ch]
0x18000f129  shr     r8d, 1
0x18000f12c  add     r8d, [rbx+38h]
0x18000f130  div     r8d
0x18000f133  xor     edx, edx
0x18000f135  shr     r9d, 1
0x18000f138  add     r9d, [rbx+34h]
0x18000f13c  mov     ecx, eax
0x18000f13e  mov     eax, [rbp+7B0h+var_7C8]
0x18000f141  div     r9d
0x18000f144  xor     edx, edx
0x18000f146  shr     r10d, 1
0x18000f149  add     r10d, [rbx+3Ch]
0x18000f14d  mov     [rbx+34h], r9d
0x18000f151  mov     r9d, eax
0x18000f154  mov     eax, r12d
0x18000f157  mov     [rbx+38h], r8d
0x18000f15b  div     r10d
0x18000f15e  mov     dword ptr [rsp+8B0h+var_890], ecx
0x18000f162  lea     rdx, aSessionAvgComm; "   Session Avg: Commit  [%4ld], Pte    "...
0x18000f169  mov     r8d, eax
0x18000f16c  mov     [rbx+3Ch], r10d
0x18000f170  mov     ecx, esi; int
0x18000f172  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f177  imul    ecx, [rbx+48h], 64h ; 'd'
0x18000f17b  mov     r8d, 80808081h
0x18000f181  mov     eax, r8d
0x18000f184  mov     dword ptr [rsp+8B0h+var_890], r14d
0x18000f189  mul     ecx
0x18000f18b  imul    ecx, dword ptr [rsp+8B0h+var_870], 64h ; 'd'
0x18000f190  mov     eax, r8d
0x18000f193  mov     r9d, edx
0x18000f196  shr     r9d, 7
0x18000f19a  mul     ecx
0x18000f19c  mov     ecx, esi; int
0x18000f19e  shr     edx, 7
0x18000f1a1  mov     r8d, edx
0x18000f1a4  lea     rdx, aCpuIdleCurrent; "   CPU Idle:    Current [%4ld], Avg    "...
0x18000f1ab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f1b0  xor     edx, edx
0x18000f1b2  mov     eax, r12d
0x18000f1b5  div     dword ptr [rbx+3Ch]
0x18000f1b8  xor     edx, edx
0x18000f1ba  mov     ecx, eax
0x18000f1bc  mov     [rdi+30h], eax
0x18000f1bf  mov     eax, [rbp+7B0h+var_7C8]
0x18000f1c2  div     dword ptr [rbx+34h]
0x18000f1c5  cmp     eax, ecx
0x18000f1c7  mov     [rdi+34h], eax
0x18000f1ca  mov     r8d, eax
0x18000f1cd  sbb     r12d, r12d
0x18000f1d0  neg     r12d
0x18000f1d3  add     r12d, 3
0x18000f1d7  cmp     eax, ecx
0x18000f1d9  mov     eax, [rbp+7B0h+var_7B0]
0x18000f1dc  cmovnb  r8d, ecx
0x18000f1e0  xor     edx, edx
0x18000f1e2  div     dword ptr [rbx+38h]
0x18000f1e5  cmp     eax, r8d
0x18000f1e8  mov     [rdi+28h], eax
0x18000f1eb  mov     ecx, eax
0x18000f1ed  cmovnb  ecx, r8d
0x18000f1f1  cmovb   r12d, esi
0x18000f1f5  mov     [rbx+40h], ecx
0x18000f1f8  cmp     r14d, ecx
0x18000f1fb  jnb     loc_18000F361
0x18000f201  mov     r12d, 5
0x18000f207  mov     ecx, [rbp+7B0h+var_820]
0x18000f20a  mov     [rdi+38h], eax
0x18000f20d  mov     [rbx+44h], r14d
0x18000f211  cmp     r12d, 3
0x18000f215  jnz     loc_18000F3C1
0x18000f21b  lea     rax, aAvailableMemor; "Available Memory"
0x18000f222  mov     r8d, [rbx+40h]
  ... truncated ...
```
