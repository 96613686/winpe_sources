# LoadTSVIPConfig

- ea: `0x180031130`
- end: `0x180031543`
- name: `LoadTSVIPConfig`
- size: `1043`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800211d0`

## callees

- `0x18000d870`
- `0x180030904`
- `0x1800309ec`
- `0x180030c64`
- `0x180030dc0`
- `0x180031130`
- `0x180032c20`
- `0x180032ce0`

## string_xrefs

- `0x1800311e5`: `Software\Policies\Microsoft\Windows NT\Terminal Services\TSAppSrv\VirtualIP`

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
0x180031130  push    rbp
0x180031132  push    rbx
0x180031133  push    rsi
0x180031134  push    rdi
0x180031135  push    r14
0x180031137  push    r15
0x180031139  lea     rbp, [rsp-1298h]
0x180031141  mov     eax, 1398h
0x180031146  call    _alloca_probe
0x18003114b  sub     rsp, rax
0x18003114e  mov     rax, cs:__security_cookie
0x180031155  xor     rax, rsp
0x180031158  mov     [rbp+12C0h+var_40], rax
0x18003115f  xor     esi, esi
0x180031161  or      eax, 0FFFFFFFFh
0x180031164  mov     rbx, rcx
0x180031167  mov     [rsp+13C0h+var_1360], rsi
0x18003116c  lea     rcx, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180031173  mov     [rsp+13C0h+var_1358], esi
0x180031177  mov     [rsp+13C0h+var_1368], rcx
0x18003117c  mov     [rsp+13C0h+var_1390], rcx
0x180031181  lea     rcx, [rbp+12C0h+var_9C0]; this
0x180031188  mov     [rsp+13C0h+var_1350], rsi
0x18003118d  mov     [rsp+13C0h+var_1348], eax
0x180031191  mov     [rsp+13C0h+var_1344], eax
0x180031195  mov     [rsp+13C0h+var_1388], rsi
0x18003119a  mov     [rsp+13C0h+var_1380], esi
0x18003119e  mov     [rsp+13C0h+var_1378], rsi
0x1800311a3  mov     [rsp+13C0h+var_1370], eax
0x1800311a7  mov     [rsp+13C0h+var_136C], eax
0x1800311ab  call    ??0__TSVirtualIPConfig@@QEAA@XZ; __TSVirtualIPConfig::__TSVirtualIPConfig(void)
0x1800311b0  lea     rcx, [rbp+12C0h+var_1340]; this
0x1800311b4  call    ??0__TSVirtualIPConfig@@QEAA@XZ; __TSVirtualIPConfig::__TSVirtualIPConfig(void)
0x1800311b9  test    rbx, rbx
0x1800311bc  jnz     short loc_1800311C6
0x1800311be  lea     edi, [rsi+57h]
0x1800311c1  jmp     loc_18003150D
0x1800311c6  mov     edi, 974h
0x1800311cb  lea     rax, [rbp+12C0h+var_9C0]
0x1800311d2  mov     ecx, edi
0x1800311d4  mov     r15d, 1
0x1800311da  mov     [rax], sil
0x1800311dd  add     rax, r15
0x1800311e0  sub     rcx, r15
0x1800311e3  jnz     short loc_1800311DA
0x1800311e5  lea     r8, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x1800311ec  lea     rcx, [rsp+13C0h+var_1368]; this
0x1800311f1  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x1800311f6  test    eax, eax
0x1800311f8  jnz     short loc_18003120E
0x1800311fa  lea     r8, [rbp+12C0h+var_9C0]
0x180031201  mov     edx, r15d
0x180031204  lea     rcx, [rsp+13C0h+var_1368]; this
0x180031209  call    RegReadConfigSettings
0x18003120e  lea     rax, [rbp+12C0h+var_1340]
0x180031212  mov     [rax], sil
0x180031215  add     rax, r15
0x180031218  sub     rdi, r15
0x18003121b  jnz     short loc_180031212
0x18003121d  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x180031224  lea     rcx, [rsp+13C0h+var_1390]; this
0x180031229  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18003122e  lea     r14d, [rdi+2]
0x180031232  test    eax, eax
0x180031234  jnz     short loc_180031247
0x180031236  lea     r8, [rbp+12C0h+var_1340]
0x18003123a  mov     edx, r14d
0x18003123d  lea     rcx, [rsp+13C0h+var_1390]; this
0x180031242  call    RegReadConfigSettings
0x180031247  mov     edi, esi
0x180031249  cmp     [rbp+12C0h+var_9C0], r15d
0x180031250  jnz     short loc_18003125D
0x180031252  mov     eax, [rbp+12C0h+var_9BC]
0x180031258  mov     [rbx], r15d
0x18003125b  jmp     short loc_180031269
0x18003125d  cmp     [rbp+12C0h+var_1340], r14d
0x180031261  jnz     short loc_18003126E
0x180031263  mov     eax, [rbp+12C0h+var_133C]
0x180031266  mov     [rbx], r14d
0x180031269  mov     [rbx+4], eax
0x18003126c  jmp     short loc_180031271
0x18003126e  mov     [rbx], rsi
0x180031271  cmp     [rbp+12C0h+var_9B8], r15d
0x180031278  jnz     short loc_180031286
0x18003127a  mov     eax, [rbp+12C0h+var_9B4]
0x180031280  mov     [rbx+8], r15d
0x180031284  jmp     short loc_180031293
0x180031286  cmp     [rbp+12C0h+var_1338], r14d
0x18003128a  jnz     short loc_180031298
0x18003128c  mov     eax, [rbp+12C0h+var_1334]
0x18003128f  mov     [rbx+8], r14d
0x180031293  mov     [rbx+0Ch], eax
0x180031296  jmp     short loc_18003129F
0x180031298  mov     [rbx+8], esi
0x18003129b  mov     [rbx+0Ch], r15d
0x18003129f  cmp     [rbp+12C0h+var_9B8], r15d
0x1800312a6  jnz     short loc_1800312B4
0x1800312a8  mov     eax, [rbp+12C0h+var_9AC]
0x1800312ae  mov     [rbx+10h], r15d
0x1800312b2  jmp     short loc_1800312C1
0x1800312b4  cmp     [rbp+12C0h+var_1338], r14d
0x1800312b8  jnz     short loc_1800312C6
0x1800312ba  mov     eax, [rbp+12C0h+var_132C]
0x1800312bd  mov     [rbx+10h], r14d
0x1800312c1  mov     [rbx+14h], eax
0x1800312c4  jmp     short loc_1800312CA
0x1800312c6  mov     [rbx+10h], rsi
0x1800312ca  cmp     [rbp+12C0h+var_9A8], r15d
0x1800312d1  jnz     short loc_1800312DF
0x1800312d3  mov     eax, [rbp+12C0h+var_9A4]
0x1800312d9  mov     [rbx+18h], r15d
0x1800312dd  jmp     short loc_1800312EC
0x1800312df  cmp     [rbp+12C0h+var_1328], r14d
0x1800312e3  jnz     short loc_1800312F1
0x1800312e5  mov     eax, [rbp+12C0h+var_1324]
0x1800312e8  mov     [rbx+18h], r14d
0x1800312ec  mov     [rbx+1Ch], eax
0x1800312ef  jmp     short loc_1800312F8
0x1800312f1  mov     [rbx+18h], esi
0x1800312f4  mov     [rbx+1Ch], r14d
0x1800312f8  cmp     [rbp+12C0h+var_9A0], r15d
0x1800312ff  jnz     short loc_180031314
0x180031301  mov     r10d, [rbp+12C0h+var_798]
0x180031308  lea     r8, [rbp+12C0h+var_99C]
0x18003130f  mov     ecx, r15d
0x180031312  jmp     short loc_180031328
0x180031314  cmp     [rbp+12C0h+var_1320], r14d
0x180031318  jnz     short loc_18003134A
0x18003131a  mov     r10d, [rbp+12C0h+var_1118]
0x180031321  lea     r8, [rbp+12C0h+var_131C]; unsigned __int16 *
0x180031325  mov     ecx, r14d
0x180031328  mov     [rbx+20h], ecx
0x18003132b  test    r10d, r10d
0x18003132e  jz      short loc_18003134D
0x180031330  lea     rcx, [rbx+24h]; unsigned __int16 *
0x180031334  mov     edx, 101h; unsigned __int64
0x180031339  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003133e  movzx   edi, ax
0x180031341  mov     [rbx+228h], r10d
0x180031348  jmp     short loc_18003134D
0x18003134a  mov     [rbx+20h], esi
0x18003134d  lea     rax, [rbx+22Ch]
0x180031354  cmp     [rbp+12C0h+var_794], r15d
0x18003135b  jnz     short loc_180031370
0x18003135d  mov     r10d, [rbp+12C0h+var_38C]
0x180031364  lea     r8, [rbp+12C0h+var_790]
0x18003136b  mov     ecx, r15d
0x18003136e  jmp     short loc_18003138A
0x180031370  cmp     [rbp+12C0h+var_1114], r14d
0x180031377  jnz     short loc_1800313AE
0x180031379  mov     r10d, [rbp+12C0h+var_D0C]
0x180031380  lea     r8, [rbp+12C0h+var_1110]; unsigned __int16 *
0x180031387  mov     ecx, r14d
0x18003138a  mov     [rax], ecx
0x18003138c  test    r10d, r10d
0x18003138f  jz      short loc_1800313B0
0x180031391  lea     rcx, [rbx+230h]; unsigned __int16 *
0x180031398  mov     edx, 201h; unsigned __int64
0x18003139d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800313a2  movzx   edi, ax
0x1800313a5  mov     [rbx+634h], r10d
0x1800313ac  jmp     short loc_1800313B0
0x1800313ae  mov     [rax], esi
0x1800313b0  cmp     [rbp+12C0h+var_388], r15d
0x1800313b7  jnz     short loc_1800313C9
0x1800313b9  mov     [rbx+638h], r15d
0x1800313c0  lea     r8, [rbp+12C0h+var_384]
0x1800313c7  jmp     short loc_1800313E0
0x1800313c9  cmp     [rbp+12C0h+var_D08], r14d
0x1800313d0  jnz     short loc_1800313F3
0x1800313d2  mov     [rbx+638h], r14d
0x1800313d9  lea     r8, [rbp+12C0h+var_D04]; unsigned __int16 *
0x1800313e0  lea     rcx, [rbx+63Ch]; unsigned __int16 *
0x1800313e7  mov     edx, 105h; unsigned __int64
0x1800313ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800313f1  jmp     short loc_1800313F9
0x1800313f3  mov     [rbx+638h], esi
0x1800313f9  cmp     [rbp+12C0h+var_178], r15d
0x180031400  jnz     short loc_180031411
0x180031402  mov     eax, [rbp+12C0h+var_174]
0x180031408  mov     [rbx+848h], r15d
0x18003140f  jmp     short loc_180031427
0x180031411  cmp     [rbp+12C0h+var_AF8], r14d
0x180031418  jnz     short loc_18003142F
0x18003141a  mov     eax, [rbp+12C0h+var_AF4]
0x180031420  mov     [rbx+848h], r14d
0x180031427  mov     [rbx+84Ch], eax
0x18003142d  jmp     short loc_180031436
0x18003142f  mov     [rbx+848h], rsi
0x180031436  lea     rcx, [rbx+850h]; unsigned __int16 *
0x18003143d  mov     edx, 81h; unsigned __int64
0x180031442  lea     r8, [rbp+12C0h+var_AF0]; unsigned __int16 *
0x180031449  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003144e  cmp     [rbp+12C0h+var_6C], r15d
0x180031455  jnz     short loc_180031466
0x180031457  mov     eax, [rbp+12C0h+var_68]
0x18003145d  mov     [rbx+954h], r15d
0x180031464  jmp     short loc_18003147C
0x180031466  cmp     [rbp+12C0h+var_9EC], r14d
0x18003146d  jnz     short loc_180031484
0x18003146f  mov     eax, [rbp+12C0h+var_9E8]
0x180031475  mov     [rbx+954h], r14d
0x18003147c  mov     [rbx+958h], eax
0x180031482  jmp     short loc_18003148B
0x180031484  mov     [rbx+954h], rsi
0x18003148b  cmp     [rbp+12C0h+var_9E4], r14d
0x180031492  jnz     short loc_1800314A5
0x180031494  mov     eax, [rbp+12C0h+var_9E0]
0x18003149a  mov     [rbx+960h], eax
0x1800314a0  mov     eax, r14d
0x1800314a3  jmp     short loc_1800314AD
0x1800314a5  mov     [rbx+960h], esi
0x1800314ab  mov     eax, esi
0x1800314ad  mov     [rbx+95Ch], eax
0x1800314b3  cmp     [rbp+12C0h+var_9DC], r14d
0x1800314ba  jnz     short loc_1800314CD
0x1800314bc  mov     eax, [rbp+12C0h+var_9D8]
0x1800314c2  mov     [rbx+968h], eax
0x1800314c8  mov     eax, r14d
0x1800314cb  jmp     short loc_1800314D9
0x1800314cd  mov     dword ptr [rbx+968h], 0Ah
0x1800314d7  mov     eax, esi
0x1800314d9  mov     [rbx+964h], eax
0x1800314df  cmp     [rbp+12C0h+var_9D4], r14d
0x1800314e6  jnz     short loc_1800314FD
0x1800314e8  mov     eax, [rbp+12C0h+var_9D0]
0x1800314ee  mov     [rbx+970h], eax
0x1800314f4  mov     [rbx+96Ch], r14d
0x1800314fb  jmp     short loc_18003150D
0x1800314fd  mov     [rbx+96Ch], esi
0x180031503  mov     dword ptr [rbx+970h], 3E8h
0x18003150d  lea     rcx, [rsp+13C0h+var_1390]; this
0x180031512  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180031517  lea     rcx, [rsp+13C0h+var_1368]; this
0x18003151c  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180031521  mov     eax, edi
0x180031523  mov     rcx, [rbp+12C0h+var_40]
0x18003152a  xor     rcx, rsp; StackCookie
0x18003152d  call    __security_check_cookie
0x180031532  add     rsp, 1398h
0x180031539  pop     r15
0x18003153b  pop     r14
0x18003153d  pop     rdi
0x18003153e  pop     rsi
0x18003153f  pop     rbx
0x180031540  pop     rbp
0x180031541  retn
```
