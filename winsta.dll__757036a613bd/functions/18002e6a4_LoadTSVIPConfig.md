# LoadTSVIPConfig

- ea: `0x18002e6a4`
- end: `0x18002eab6`
- name: `LoadTSVIPConfig`
- size: `1042`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001fad0`

## callees

- `0x18000bcf0`
- `0x18002df28`
- `0x18002e004`
- `0x18002e254`
- `0x18002e314`
- `0x18002e6a4`
- `0x18002fe40`
- `0x18002ff00`

## string_xrefs

- `0x18002e759`: `Software\Policies\Microsoft\Windows NT\Terminal Services\TSAppSrv\VirtualIP`

## pseudocode

```c
__int64 __fastcall LoadTSVIPConfig(__int64 a1)
{
  HKEY v2; // rdx
  unsigned int v3; // edi
  __int64 v4; // rdi
  _BYTE *v5; // rax
  __int64 v6; // rcx
  HKEY v7; // rdx
  _BYTE *v8; // rax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // r10d
  unsigned __int16 *v14; // r8
  int v15; // ecx
  int v16; // r10d
  int *v17; // rax
  int v18; // r10d
  unsigned __int16 *v19; // r8
  int v20; // ecx
  int v21; // r10d
  unsigned __int16 *v22; // r8
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  _QWORD v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+48h] [rbp-B8h]
  int v31; // [rsp+50h] [rbp-B0h]
  int v32; // [rsp+54h] [rbp-ACh]
  _QWORD v33[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  int v36; // [rsp+78h] [rbp-88h]
  int v37; // [rsp+7Ch] [rbp-84h]
  _DWORD v38[2]; // [rsp+80h] [rbp-80h] BYREF
  int v39; // [rsp+88h] [rbp-78h]
  int v40; // [rsp+8Ch] [rbp-74h]
  int v41; // [rsp+94h] [rbp-6Ch]
  int v42; // [rsp+98h] [rbp-68h]
  int v43; // [rsp+9Ch] [rbp-64h]
  int v44; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v45; // [rsp+A4h] [rbp-5Ch] BYREF
  int v46; // [rsp+2A8h] [rbp+1A8h]
  int v47; // [rsp+2ACh] [rbp+1ACh]
  unsigned __int16 v48; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v49; // [rsp+6B4h] [rbp+5B4h]
  int v50; // [rsp+6B8h] [rbp+5B8h]
  unsigned __int16 v51; // [rsp+6BCh] [rbp+5BCh] BYREF
  int v52; // [rsp+8C8h] [rbp+7C8h]
  int v53; // [rsp+8CCh] [rbp+7CCh]
  unsigned __int16 v54[130]; // [rsp+8D0h] [rbp+7D0h] BYREF
  int v55; // [rsp+9D4h] [rbp+8D4h]
  int v56; // [rsp+9D8h] [rbp+8D8h]
  int v57; // [rsp+9DCh] [rbp+8DCh]
  int v58; // [rsp+9E0h] [rbp+8E0h]
  int v59; // [rsp+9E4h] [rbp+8E4h]
  int v60; // [rsp+9E8h] [rbp+8E8h]
  int v61; // [rsp+9ECh] [rbp+8ECh]
  int v62; // [rsp+9F0h] [rbp+8F0h]
  _DWORD v63[2]; // [rsp+A00h] [rbp+900h] BYREF
  int v64; // [rsp+A08h] [rbp+908h]
  int v65; // [rsp+A0Ch] [rbp+90Ch]
  int v66; // [rsp+A14h] [rbp+914h]
  int v67; // [rsp+A18h] [rbp+918h]
  int v68; // [rsp+A1Ch] [rbp+91Ch]
  int v69; // [rsp+A20h] [rbp+920h]
  char v70; // [rsp+A24h] [rbp+924h] BYREF
  int v71; // [rsp+C28h] [rbp+B28h]
  int v72; // [rsp+C2Ch] [rbp+B2Ch]
  char v73; // [rsp+C30h] [rbp+B30h] BYREF
  int v74; // [rsp+1034h] [rbp+F34h]
  int v75; // [rsp+1038h] [rbp+F38h]
  char v76; // [rsp+103Ch] [rbp+F3Ch] BYREF
  int v77; // [rsp+1248h] [rbp+1148h]
  int v78; // [rsp+124Ch] [rbp+114Ch]
  int v79; // [rsp+1354h] [rbp+1254h]
  int v80; // [rsp+1358h] [rbp+1258h]

  v33[1] = 0;
  v34 = 0;
  v33[0] = &CRegistry::`vftable';
  v28[0] = &CRegistry::`vftable';
  v35 = 0;
  v36 = -1;
  v37 = -1;
  v28[1] = 0;
  v29 = 0;
  v30 = 0;
  v31 = -1;
  v32 = -1;
  __TSVirtualIPConfig::__TSVirtualIPConfig((__TSVirtualIPConfig *)v63);
  __TSVirtualIPConfig::__TSVirtualIPConfig((__TSVirtualIPConfig *)v38);
  if ( !a1 )
  {
    v3 = 87;
    goto LABEL_76;
  }
  v4 = 2420;
  v5 = v63;
  v6 = 2420;
  do
  {
    *v5++ = 0;
    --v6;
  }
  while ( v6 );
  if ( !CRegistry::OpenKey(
          (CRegistry *)v33,
          v2,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\TSAppSrv\\VirtualIP") )
    RegReadConfigSettings((CRegistry *)v33, 1, (__int64)v63);
  v8 = v38;
  do
  {
    *v8++ = 0;
    --v4;
  }
  while ( v4 );
  if ( !CRegistry::OpenKey(
          (CRegistry *)v28,
          v7,
          L"System\\CurrentControlSet\\Control\\Terminal Server\\TSAppSrv\\VirtualIP") )
    RegReadConfigSettings((CRegistry *)v28, 2, (__int64)v38);
  v3 = 0;
  if ( v63[0] == 1 )
  {
    v9 = v63[1];
    *(_DWORD *)a1 = 1;
LABEL_15:
    *(_DWORD *)(a1 + 4) = v9;
    goto LABEL_17;
  }
  if ( v38[0] == 2 )
  {
    v9 = v38[1];
    *(_DWORD *)a1 = 2;
    goto LABEL_15;
  }
  *(_QWORD *)a1 = 0;
LABEL_17:
  if ( v64 == 1 )
  {
    v10 = v65;
    *(_DWORD *)(a1 + 8) = 1;
LABEL_21:
    *(_DWORD *)(a1 + 12) = v10;
    goto LABEL_23;
  }
  if ( v39 == 2 )
  {
    v10 = v40;
    *(_DWORD *)(a1 + 8) = 2;
    goto LABEL_21;
  }
  *(_DWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 12) = 1;
LABEL_23:
  if ( v64 == 1 )
  {
    v11 = v66;
    *(_DWORD *)(a1 + 16) = 1;
LABEL_27:
    *(_DWORD *)(a1 + 20) = v11;
    goto LABEL_29;
  }
  if ( v39 == 2 )
  {
    v11 = v41;
    *(_DWORD *)(a1 + 16) = 2;
    goto LABEL_27;
  }
  *(_QWORD *)(a1 + 16) = 0;
LABEL_29:
  if ( v67 == 1 )
  {
    v12 = v68;
    *(_DWORD *)(a1 + 24) = 1;
LABEL_33:
    *(_DWORD *)(a1 + 28) = v12;
    goto LABEL_35;
  }
  if ( v42 == 2 )
  {
    v12 = v43;
    *(_DWORD *)(a1 + 24) = 2;
    goto LABEL_33;
  }
  *(_DWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 28) = 2;
LABEL_35:
  if ( v69 == 1 )
  {
    v13 = v71;
    v14 = (unsigned __int16 *)&v70;
    v15 = 1;
  }
  else
  {
    if ( v44 != 2 )
    {
      *(_DWORD *)(a1 + 32) = 0;
      goto LABEL_42;
    }
    v13 = v46;
    v14 = &v45;
    v15 = 2;
  }
  *(_DWORD *)(a1 + 32) = v15;
  if ( v13 )
  {
    v3 = (unsigned __int16)StringCchCopyW((unsigned __int16 *)(a1 + 36), 0x101u, v14);
    *(_DWORD *)(a1 + 552) = v16;
  }
LABEL_42:
  v17 = (int *)(a1 + 556);
  if ( v72 == 1 )
  {
    v18 = v74;
    v19 = (unsigned __int16 *)&v73;
    v20 = 1;
  }
  else
  {
    if ( v47 != 2 )
    {
      *v17 = 0;
      goto LABEL_49;
    }
    v18 = v49;
    v19 = &v48;
    v20 = 2;
  }
  *v17 = v20;
  if ( v18 )
  {
    v3 = (unsigned __int16)StringCchCopyW((unsigned __int16 *)(a1 + 560), 0x201u, v19);
    *(_DWORD *)(a1 + 1588) = v21;
  }
LABEL_49:
  if ( v75 == 1 )
  {
    *(_DWORD *)(a1 + 1592) = 1;
    v22 = (unsigned __int16 *)&v76;
LABEL_53:
    StringCchCopyW((unsigned __int16 *)(a1 + 1596), 0x105u, v22);
    goto LABEL_55;
  }
  if ( v50 == 2 )
  {
    *(_DWORD *)(a1 + 1592) = 2;
    v22 = &v51;
    goto LABEL_53;
  }
  *(_DWORD *)(a1 + 1592) = 0;
LABEL_55:
  if ( v77 == 1 )
  {
    v23 = v78;
    *(_DWORD *)(a1 + 2120) = 1;
LABEL_59:
    *(_DWORD *)(a1 + 2124) = v23;
    goto LABEL_61;
  }
  if ( v52 == 2 )
  {
    v23 = v53;
    *(_DWORD *)(a1 + 2120) = 2;
    goto LABEL_59;
  }
  *(_QWORD *)(a1 + 2120) = 0;
LABEL_61:
  StringCchCopyW((unsigned __int16 *)(a1 + 2128), 0x81u, v54);
  if ( v79 == 1 )
  {
    v24 = v80;
    *(_DWORD *)(a1 + 2388) = 1;
  }
  else
  {
    if ( v55 != 2 )
    {
      *(_QWORD *)(a1 + 2388) = 0;
      goto LABEL_67;
    }
    v24 = v56;
    *(_DWORD *)(a1 + 2388) = 2;
  }
  *(_DWORD *)(a1 + 2392) = v24;
LABEL_67:
  if ( v57 == 2 )
  {
    *(_DWORD *)(a1 + 2400) = v58;
    v25 = 2;
  }
  else
  {
    *(_DWORD *)(a1 + 2400) = 0;
    v25 = 0;
  }
  *(_DWORD *)(a1 + 2396) = v25;
  if ( v59 == 2 )
  {
    *(_DWORD *)(a1 + 2408) = v60;
    v26 = 2;
  }
  else
  {
    *(_DWORD *)(a1 + 2408) = 10;
    v26 = 0;
  }
  *(_DWORD *)(a1 + 2404) = v26;
  if ( v61 == 2 )
  {
    *(_DWORD *)(a1 + 2416) = v62;
    *(_DWORD *)(a1 + 2412) = 2;
  }
  else
  {
    *(_DWORD *)(a1 + 2412) = 0;
    *(_DWORD *)(a1 + 2416) = 1000;
  }
LABEL_76:
  CRegistry::~CRegistry((CRegistry *)v28);
  CRegistry::~CRegistry((CRegistry *)v33);
  return v3;
}

```

## disassembly

```asm
0x18002e6a4  push    rbp
0x18002e6a6  push    rbx
0x18002e6a7  push    rsi
0x18002e6a8  push    rdi
0x18002e6a9  push    r14
0x18002e6ab  push    r15
0x18002e6ad  lea     rbp, [rsp-1298h]
0x18002e6b5  mov     eax, 1398h
0x18002e6ba  call    _alloca_probe
0x18002e6bf  sub     rsp, rax
0x18002e6c2  mov     rax, cs:__security_cookie
0x18002e6c9  xor     rax, rsp
0x18002e6cc  mov     [rbp+12C0h+var_40], rax
0x18002e6d3  xor     esi, esi
0x18002e6d5  or      eax, 0FFFFFFFFh
0x18002e6d8  mov     rbx, rcx
0x18002e6db  mov     [rsp+13C0h+var_1360], rsi
0x18002e6e0  lea     rcx, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18002e6e7  mov     [rsp+13C0h+var_1358], esi
0x18002e6eb  mov     [rsp+13C0h+var_1368], rcx
0x18002e6f0  mov     [rsp+13C0h+var_1390], rcx
0x18002e6f5  lea     rcx, [rbp+12C0h+var_9C0]; this
0x18002e6fc  mov     [rsp+13C0h+var_1350], rsi
0x18002e701  mov     [rsp+13C0h+var_1348], eax
0x18002e705  mov     [rsp+13C0h+var_1344], eax
0x18002e709  mov     [rsp+13C0h+var_1388], rsi
0x18002e70e  mov     [rsp+13C0h+var_1380], esi
0x18002e712  mov     [rsp+13C0h+var_1378], rsi
0x18002e717  mov     [rsp+13C0h+var_1370], eax
0x18002e71b  mov     [rsp+13C0h+var_136C], eax
0x18002e71f  call    ??0__TSVirtualIPConfig@@QEAA@XZ; __TSVirtualIPConfig::__TSVirtualIPConfig(void)
0x18002e724  lea     rcx, [rbp+12C0h+var_1340]; this
0x18002e728  call    ??0__TSVirtualIPConfig@@QEAA@XZ; __TSVirtualIPConfig::__TSVirtualIPConfig(void)
0x18002e72d  test    rbx, rbx
0x18002e730  jnz     short loc_18002E73A
0x18002e732  lea     edi, [rsi+57h]
0x18002e735  jmp     loc_18002EA81
0x18002e73a  mov     edi, 974h
0x18002e73f  lea     rax, [rbp+12C0h+var_9C0]
0x18002e746  mov     ecx, edi
0x18002e748  mov     r15d, 1
0x18002e74e  mov     [rax], sil
0x18002e751  add     rax, r15
0x18002e754  sub     rcx, r15
0x18002e757  jnz     short loc_18002E74E
0x18002e759  lea     r8, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18002e760  lea     rcx, [rsp+13C0h+var_1368]; this
0x18002e765  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18002e76a  test    eax, eax
0x18002e76c  jnz     short loc_18002E782
0x18002e76e  lea     r8, [rbp+12C0h+var_9C0]
0x18002e775  mov     edx, r15d
0x18002e778  lea     rcx, [rsp+13C0h+var_1368]; this
0x18002e77d  call    RegReadConfigSettings
0x18002e782  lea     rax, [rbp+12C0h+var_1340]
0x18002e786  mov     [rax], sil
0x18002e789  add     rax, r15
0x18002e78c  sub     rdi, r15
0x18002e78f  jnz     short loc_18002E786
0x18002e791  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18002e798  lea     rcx, [rsp+13C0h+var_1390]; this
0x18002e79d  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18002e7a2  lea     r14d, [rdi+2]
0x18002e7a6  test    eax, eax
0x18002e7a8  jnz     short loc_18002E7BB
0x18002e7aa  lea     r8, [rbp+12C0h+var_1340]
0x18002e7ae  mov     edx, r14d
0x18002e7b1  lea     rcx, [rsp+13C0h+var_1390]; this
0x18002e7b6  call    RegReadConfigSettings
0x18002e7bb  mov     edi, esi
0x18002e7bd  cmp     [rbp+12C0h+var_9C0], r15d
0x18002e7c4  jnz     short loc_18002E7D1
0x18002e7c6  mov     eax, [rbp+12C0h+var_9BC]
0x18002e7cc  mov     [rbx], r15d
0x18002e7cf  jmp     short loc_18002E7DD
0x18002e7d1  cmp     [rbp+12C0h+var_1340], r14d
0x18002e7d5  jnz     short loc_18002E7E2
0x18002e7d7  mov     eax, [rbp+12C0h+var_133C]
0x18002e7da  mov     [rbx], r14d
0x18002e7dd  mov     [rbx+4], eax
0x18002e7e0  jmp     short loc_18002E7E5
0x18002e7e2  mov     [rbx], rsi
0x18002e7e5  cmp     [rbp+12C0h+var_9B8], r15d
0x18002e7ec  jnz     short loc_18002E7FA
0x18002e7ee  mov     eax, [rbp+12C0h+var_9B4]
0x18002e7f4  mov     [rbx+8], r15d
0x18002e7f8  jmp     short loc_18002E807
0x18002e7fa  cmp     [rbp+12C0h+var_1338], r14d
0x18002e7fe  jnz     short loc_18002E80C
0x18002e800  mov     eax, [rbp+12C0h+var_1334]
0x18002e803  mov     [rbx+8], r14d
0x18002e807  mov     [rbx+0Ch], eax
0x18002e80a  jmp     short loc_18002E813
0x18002e80c  mov     [rbx+8], esi
0x18002e80f  mov     [rbx+0Ch], r15d
0x18002e813  cmp     [rbp+12C0h+var_9B8], r15d
0x18002e81a  jnz     short loc_18002E828
0x18002e81c  mov     eax, [rbp+12C0h+var_9AC]
0x18002e822  mov     [rbx+10h], r15d
0x18002e826  jmp     short loc_18002E835
0x18002e828  cmp     [rbp+12C0h+var_1338], r14d
0x18002e82c  jnz     short loc_18002E83A
0x18002e82e  mov     eax, [rbp+12C0h+var_132C]
0x18002e831  mov     [rbx+10h], r14d
0x18002e835  mov     [rbx+14h], eax
0x18002e838  jmp     short loc_18002E83E
0x18002e83a  mov     [rbx+10h], rsi
0x18002e83e  cmp     [rbp+12C0h+var_9A8], r15d
0x18002e845  jnz     short loc_18002E853
0x18002e847  mov     eax, [rbp+12C0h+var_9A4]
0x18002e84d  mov     [rbx+18h], r15d
0x18002e851  jmp     short loc_18002E860
0x18002e853  cmp     [rbp+12C0h+var_1328], r14d
0x18002e857  jnz     short loc_18002E865
0x18002e859  mov     eax, [rbp+12C0h+var_1324]
0x18002e85c  mov     [rbx+18h], r14d
0x18002e860  mov     [rbx+1Ch], eax
0x18002e863  jmp     short loc_18002E86C
0x18002e865  mov     [rbx+18h], esi
0x18002e868  mov     [rbx+1Ch], r14d
0x18002e86c  cmp     [rbp+12C0h+var_9A0], r15d
0x18002e873  jnz     short loc_18002E888
0x18002e875  mov     r10d, [rbp+12C0h+var_798]
0x18002e87c  lea     r8, [rbp+12C0h+var_99C]
0x18002e883  mov     ecx, r15d
0x18002e886  jmp     short loc_18002E89C
0x18002e888  cmp     [rbp+12C0h+var_1320], r14d
0x18002e88c  jnz     short loc_18002E8BE
0x18002e88e  mov     r10d, [rbp+12C0h+var_1118]
0x18002e895  lea     r8, [rbp+12C0h+var_131C]; unsigned __int16 *
0x18002e899  mov     ecx, r14d
0x18002e89c  mov     [rbx+20h], ecx
0x18002e89f  test    r10d, r10d
0x18002e8a2  jz      short loc_18002E8C1
0x18002e8a4  lea     rcx, [rbx+24h]; unsigned __int16 *
0x18002e8a8  mov     edx, 101h; unsigned __int64
0x18002e8ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e8b2  movzx   edi, ax
0x18002e8b5  mov     [rbx+228h], r10d
0x18002e8bc  jmp     short loc_18002E8C1
0x18002e8be  mov     [rbx+20h], esi
0x18002e8c1  lea     rax, [rbx+22Ch]
0x18002e8c8  cmp     [rbp+12C0h+var_794], r15d
0x18002e8cf  jnz     short loc_18002E8E4
0x18002e8d1  mov     r10d, [rbp+12C0h+var_38C]
0x18002e8d8  lea     r8, [rbp+12C0h+var_790]
0x18002e8df  mov     ecx, r15d
0x18002e8e2  jmp     short loc_18002E8FE
0x18002e8e4  cmp     [rbp+12C0h+var_1114], r14d
0x18002e8eb  jnz     short loc_18002E922
0x18002e8ed  mov     r10d, [rbp+12C0h+var_D0C]
0x18002e8f4  lea     r8, [rbp+12C0h+var_1110]; unsigned __int16 *
0x18002e8fb  mov     ecx, r14d
0x18002e8fe  mov     [rax], ecx
0x18002e900  test    r10d, r10d
0x18002e903  jz      short loc_18002E924
0x18002e905  lea     rcx, [rbx+230h]; unsigned __int16 *
0x18002e90c  mov     edx, 201h; unsigned __int64
0x18002e911  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e916  movzx   edi, ax
0x18002e919  mov     [rbx+634h], r10d
0x18002e920  jmp     short loc_18002E924
0x18002e922  mov     [rax], esi
0x18002e924  cmp     [rbp+12C0h+var_388], r15d
0x18002e92b  jnz     short loc_18002E93D
0x18002e92d  mov     [rbx+638h], r15d
0x18002e934  lea     r8, [rbp+12C0h+var_384]
0x18002e93b  jmp     short loc_18002E954
0x18002e93d  cmp     [rbp+12C0h+var_D08], r14d
0x18002e944  jnz     short loc_18002E967
0x18002e946  mov     [rbx+638h], r14d
0x18002e94d  lea     r8, [rbp+12C0h+var_D04]; unsigned __int16 *
0x18002e954  lea     rcx, [rbx+63Ch]; unsigned __int16 *
0x18002e95b  mov     edx, 105h; unsigned __int64
0x18002e960  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e965  jmp     short loc_18002E96D
0x18002e967  mov     [rbx+638h], esi
0x18002e96d  cmp     [rbp+12C0h+var_178], r15d
0x18002e974  jnz     short loc_18002E985
0x18002e976  mov     eax, [rbp+12C0h+var_174]
0x18002e97c  mov     [rbx+848h], r15d
0x18002e983  jmp     short loc_18002E99B
0x18002e985  cmp     [rbp+12C0h+var_AF8], r14d
0x18002e98c  jnz     short loc_18002E9A3
0x18002e98e  mov     eax, [rbp+12C0h+var_AF4]
0x18002e994  mov     [rbx+848h], r14d
0x18002e99b  mov     [rbx+84Ch], eax
0x18002e9a1  jmp     short loc_18002E9AA
0x18002e9a3  mov     [rbx+848h], rsi
0x18002e9aa  lea     rcx, [rbx+850h]; unsigned __int16 *
0x18002e9b1  mov     edx, 81h; unsigned __int64
0x18002e9b6  lea     r8, [rbp+12C0h+var_AF0]; unsigned __int16 *
0x18002e9bd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e9c2  cmp     [rbp+12C0h+var_6C], r15d
0x18002e9c9  jnz     short loc_18002E9DA
0x18002e9cb  mov     eax, [rbp+12C0h+var_68]
0x18002e9d1  mov     [rbx+954h], r15d
0x18002e9d8  jmp     short loc_18002E9F0
0x18002e9da  cmp     [rbp+12C0h+var_9EC], r14d
0x18002e9e1  jnz     short loc_18002E9F8
0x18002e9e3  mov     eax, [rbp+12C0h+var_9E8]
0x18002e9e9  mov     [rbx+954h], r14d
0x18002e9f0  mov     [rbx+958h], eax
0x18002e9f6  jmp     short loc_18002E9FF
0x18002e9f8  mov     [rbx+954h], rsi
0x18002e9ff  cmp     [rbp+12C0h+var_9E4], r14d
0x18002ea06  jnz     short loc_18002EA19
0x18002ea08  mov     eax, [rbp+12C0h+var_9E0]
0x18002ea0e  mov     [rbx+960h], eax
0x18002ea14  mov     eax, r14d
0x18002ea17  jmp     short loc_18002EA21
0x18002ea19  mov     [rbx+960h], esi
0x18002ea1f  mov     eax, esi
0x18002ea21  mov     [rbx+95Ch], eax
0x18002ea27  cmp     [rbp+12C0h+var_9DC], r14d
0x18002ea2e  jnz     short loc_18002EA41
0x18002ea30  mov     eax, [rbp+12C0h+var_9D8]
0x18002ea36  mov     [rbx+968h], eax
0x18002ea3c  mov     eax, r14d
0x18002ea3f  jmp     short loc_18002EA4D
0x18002ea41  mov     dword ptr [rbx+968h], 0Ah
0x18002ea4b  mov     eax, esi
0x18002ea4d  mov     [rbx+964h], eax
0x18002ea53  cmp     [rbp+12C0h+var_9D4], r14d
0x18002ea5a  jnz     short loc_18002EA71
0x18002ea5c  mov     eax, [rbp+12C0h+var_9D0]
0x18002ea62  mov     [rbx+970h], eax
0x18002ea68  mov     [rbx+96Ch], r14d
0x18002ea6f  jmp     short loc_18002EA81
0x18002ea71  mov     [rbx+96Ch], esi
0x18002ea77  mov     dword ptr [rbx+970h], 3E8h
0x18002ea81  lea     rcx, [rsp+13C0h+var_1390]; this
0x18002ea86  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18002ea8b  lea     rcx, [rsp+13C0h+var_1368]; this
0x18002ea90  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18002ea95  mov     eax, edi
0x18002ea97  mov     rcx, [rbp+12C0h+var_40]
0x18002ea9e  xor     rcx, rsp; StackCookie
0x18002eaa1  call    __security_check_cookie
0x18002eaa6  add     rsp, 1398h
0x18002eaad  pop     r15
0x18002eaaf  pop     r14
0x18002eab1  pop     rdi
0x18002eab2  pop     rsi
0x18002eab3  pop     rbx
0x18002eab4  pop     rbp
0x18002eab5  retn
```
