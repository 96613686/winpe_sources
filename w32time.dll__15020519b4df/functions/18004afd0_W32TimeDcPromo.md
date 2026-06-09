# W32TimeDcPromo

- ea: `0x18004afd0`
- end: `0x18004b2de`
- name: `W32TimeDcPromo`
- size: `782`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18004ade0`

## callees

- `0x18003d270`
- `0x1800498b8`
- `0x18004a3cc`
- `0x18004aae4`
- `0x18004ac98`
- `0x18004afd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b085`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b085`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b2ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b2ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b0d1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b0d1`

## string_xrefs

- `0x18004b066`: `System\CurrentControlSet\Services\W32Time\Parameters`

## pseudocode

```c
LSTATUS __fastcall W32TimeDcPromo(char a1)
{
  LSTATUS result; // eax
  int v2; // ebx
  unsigned __int16 *v3; // rdi
  int v4; // r15d
  int v5; // esi
  int v6; // r14d
  int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // ecx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v12; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+60h] [rbp-A0h]
  __int64 v15; // [rsp+64h] [rbp-9Ch]
  int v16; // [rsp+6Ch] [rbp-94h]
  _DWORD v17[6]; // [rsp+70h] [rbp-90h]
  __int64 v18; // [rsp+88h] [rbp-78h]
  int v19; // [rsp+90h] [rbp-70h]
  int v20; // [rsp+94h] [rbp-6Ch]
  int v21; // [rsp+98h] [rbp-68h]
  int v22; // [rsp+9Ch] [rbp-64h]
  int v23; // [rsp+A0h] [rbp-60h]
  int v24; // [rsp+A4h] [rbp-5Ch]
  int v25; // [rsp+A8h] [rbp-58h]
  int v26; // [rsp+ACh] [rbp-54h]
  int v27; // [rsp+B0h] [rbp-50h]
  int v28; // [rsp+B4h] [rbp-4Ch]
  int v29; // [rsp+B8h] [rbp-48h]
  int v30; // [rsp+BCh] [rbp-44h]
  int v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C4h] [rbp-3Ch]
  int v33; // [rsp+CCh] [rbp-34h]
  int v34; // [rsp+D0h] [rbp-30h]
  int v35; // [rsp+D4h] [rbp-2Ch]
  int v36; // [rsp+D8h] [rbp-28h]
  __int64 v37; // [rsp+DCh] [rbp-24h]
  int v38; // [rsp+E4h] [rbp-1Ch]
  int v39; // [rsp+E8h] [rbp-18h]
  int v40; // [rsp+ECh] [rbp-14h]
  int v41; // [rsp+F0h] [rbp-10h]
  int v42; // [rsp+F4h] [rbp-Ch]
  int v43; // [rsp+F8h] [rbp-8h]
  int v44; // [rsp+FCh] [rbp-4h]
  __int64 v45; // [rsp+100h] [rbp+0h]
  int v46; // [rsp+108h] [rbp+8h]
  int v47; // [rsp+10Ch] [rbp+Ch]
  int v48; // [rsp+110h] [rbp+10h]
  int v49; // [rsp+114h] [rbp+14h]
  int v50; // [rsp+118h] [rbp+18h]
  int v51; // [rsp+11Ch] [rbp+1Ch]
  int v52; // [rsp+120h] [rbp+20h]
  int v53; // [rsp+124h] [rbp+24h]
  int v54; // [rsp+128h] [rbp+28h]
  int v55; // [rsp+12Ch] [rbp+2Ch]
  int v56; // [rsp+130h] [rbp+30h]
  int v57; // [rsp+134h] [rbp+34h]
  int v58; // [rsp+138h] [rbp+38h]
  __int64 v59; // [rsp+13Ch] [rbp+3Ch]
  int v60; // [rsp+144h] [rbp+44h]
  int v61; // [rsp+148h] [rbp+48h]
  int v62; // [rsp+14Ch] [rbp+4Ch]
  int v63; // [rsp+150h] [rbp+50h]
  __int64 v64; // [rsp+154h] [rbp+54h]
  int v65; // [rsp+15Ch] [rbp+5Ch]
  int v66; // [rsp+160h] [rbp+60h]
  int v67; // [rsp+164h] [rbp+64h]
  int v68; // [rsp+168h] [rbp+68h]
  int v69; // [rsp+16Ch] [rbp+6Ch]
  int v70; // [rsp+170h] [rbp+70h]
  int v71; // [rsp+174h] [rbp+74h]
  int v72; // [rsp+178h] [rbp+78h]
  int v73; // [rsp+17Ch] [rbp+7Ch]
  int v74; // [rsp+180h] [rbp+80h]
  int v75; // [rsp+184h] [rbp+84h]
  int v76; // [rsp+188h] [rbp+88h]
  int v77; // [rsp+18Ch] [rbp+8Ch]
  int v78; // [rsp+190h] [rbp+90h]
  int v79; // [rsp+194h] [rbp+94h]
  int v80; // [rsp+198h] [rbp+98h]
  int v81; // [rsp+19Ch] [rbp+9Ch]
  _BYTE pvData[518]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int16 v83; // [rsp+3A6h] [rbp+2A6h]

  pcbData = 0;
  pdwType = 0;
  result = a1 & 1;
  hkey = 0;
  v12 = 0;
  if ( (a1 & 1) != 0 || (a1 & 4) != 0 )
  {
    v2 = 1;
  }
  else if ( (a1 & 8) != 0 )
  {
    v2 = 8;
  }
  else
  {
    if ( (a1 & 2) == 0 )
      return result;
    v2 = 2;
  }
  v3 = 0;
  v4 = HasNewPeerlist() != 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time\\Parameters", 0, 3u, &hkey) )
    goto LABEL_12;
  pcbData = 520;
  result = RegGetValueW(hkey, 0, L"Type", 0xFFFFu, &pdwType, pvData, &pcbData);
  if ( result )
    goto LABEL_12;
  if ( pdwType == 1 )
  {
    v83 = 0;
    v3 = (unsigned __int16 *)pvData;
LABEL_12:
    v5 = 0;
    v6 = 0;
    v7 = ToDwordSyncFromFlags(v3, &v12);
    v8 = 0;
    if ( v7 >= 0 )
      v9 = v12;
    else
      v9 = (v2 != 8) + 1;
    v14 = 1;
    v17[4] = 3;
    v29 = 3;
    v30 = 3;
    v33 = 3;
    v56 = 3;
    v57 = 3;
    v60 = 3;
    v66 = 3;
    v71 = 3;
    v76 = 3;
    v79 = 3;
    v81 = 3;
    v15 = 2;
    v16 = 0;
    v17[0] = 1;
    v17[1] = 1;
    v17[2] = 1;
    v17[3] = 1;
    v17[5] = 1;
    v18 = 1;
    v19 = 1;
    v20 = 2;
    v21 = 1;
    v22 = 1;
    v23 = 2;
    v24 = 2;
    v25 = 2;
    v26 = 1;
    v27 = 1;
    v28 = 1;
    v31 = 1;
    v32 = 1;
    v34 = 2;
    v35 = 1;
    v36 = 2;
    v37 = 2;
    v38 = 0;
    v39 = 2;
    v40 = 2;
    v41 = 1;
    v42 = 1;
    v43 = 1;
    v44 = 2;
    v45 = 2;
    v46 = 1;
    v47 = 2;
    v48 = 2;
    v49 = 2;
    v50 = 2;
    v51 = 2;
    v52 = 2;
    v53 = 2;
    v54 = 2;
    v55 = 1;
    v58 = 2;
    v59 = 2;
    v61 = 2;
    v62 = 2;
    v63 = 8;
    v64 = 2;
    v65 = 0;
    v67 = 8;
    v68 = 2;
    v69 = 1;
    v70 = 1;
    v72 = 8;
    v73 = 2;
    v74 = 2;
    v75 = 1;
    v77 = 8;
    v78 = 2;
    v80 = 1;
    do
    {
      if ( v2 == *(&v14 + 5 * v8)
        && v9 == *((_DWORD *)&v15 + 5 * v8 + 1)
        && (*((_DWORD *)&v15 + 5 * v8) == 2 || v4 == *((_DWORD *)&v15 + 5 * v8)) )
      {
        v5 = v17[5 * v8 - 1];
        v6 = v17[5 * v8];
      }
      ++v8;
    }
    while ( v8 != 16 );
    CreateRoleSpecificRegValues(v6, 0, 1);
    result = WriteSyncFromFlagsSpecial(v5);
  }
  if ( hkey )
    return RegCloseKey(hkey);
  return result;
}

```

## disassembly

```asm
0x18004afd0  push    rbp
0x18004afd2  push    rbx
0x18004afd3  push    rsi
0x18004afd4  push    rdi
0x18004afd5  push    r12
0x18004afd7  push    r13
0x18004afd9  push    r14
0x18004afdb  push    r15
0x18004afdd  lea     rbp, [rsp-2C8h]
0x18004afe5  sub     rsp, 3C8h
0x18004afec  mov     rax, cs:__security_cookie
0x18004aff3  xor     rax, rsp
0x18004aff6  mov     [rbp+300h+var_50], rax
0x18004affd  mov     r12d, 1
0x18004b003  mov     [rsp+400h+var_3C0], 0
0x18004b00b  mov     eax, ecx
0x18004b00d  mov     [rsp+400h+pdwType], 0
0x18004b015  and     eax, r12d
0x18004b018  mov     [rsp+400h+hkey], 0
0x18004b021  mov     [rsp+400h+var_3B8], 0
0x18004b029  lea     r13d, [r12+1]
0x18004b02e  test    al, al
0x18004b030  jnz     short loc_18004B037
0x18004b032  test    cl, 4
0x18004b035  jz      short loc_18004B03C
0x18004b037  mov     ebx, r12d
0x18004b03a  jmp     short loc_18004B056
0x18004b03c  test    cl, 8
0x18004b03f  jz      short loc_18004B048
0x18004b041  mov     ebx, 8
0x18004b046  jmp     short loc_18004B056
0x18004b048  and     ecx, r13d
0x18004b04b  test    cl, cl
0x18004b04d  jz      loc_18004B2BA
0x18004b053  mov     ebx, r13d
0x18004b056  xor     edi, edi
0x18004b058  call    ?HasNewPeerlist@@YAHXZ; HasNewPeerlist(void)
0x18004b05d  xor     r15d, r15d
0x18004b060  lea     r9d, [rdi+3]; samDesired
0x18004b064  test    eax, eax
0x18004b066  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\W3"...
0x18004b06d  lea     rax, [rsp+400h+hkey]
0x18004b072  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004b079  setnz   r15b
0x18004b07d  mov     [rsp+400h+phkResult], rax; phkResult
0x18004b082  xor     r8d, r8d; ulOptions
0x18004b085  call    cs:__imp_RegOpenKeyExW
0x18004b08c  nop     dword ptr [rax+rax+00h]
0x18004b091  test    eax, eax
0x18004b093  jnz     short loc_18004B0FA
0x18004b095  mov     rcx, [rsp+400h+hkey]; hkey
0x18004b09a  lea     rax, [rsp+400h+var_3C0]
0x18004b09f  mov     [rsp+400h+pcbData], rax; pcbData
0x18004b0a4  lea     r8, aType; "Type"
0x18004b0ab  lea     rax, [rbp+300h+var_260]
0x18004b0b2  mov     [rsp+400h+var_3C0], 208h
0x18004b0ba  mov     [rsp+400h+pvData], rax; pvData
0x18004b0bf  mov     r9d, 0FFFFh; dwFlags
0x18004b0c5  lea     rax, [rsp+400h+pdwType]
0x18004b0ca  xor     edx, edx; lpSubKey
0x18004b0cc  mov     [rsp+400h+phkResult], rax; pdwType
0x18004b0d1  call    cs:__imp_RegGetValueW
0x18004b0d8  nop     dword ptr [rax+rax+00h]
0x18004b0dd  test    eax, eax
0x18004b0df  jnz     short loc_18004B0FA
0x18004b0e1  cmp     [rsp+400h+pdwType], r12d
0x18004b0e6  jnz     loc_18004B2A4
0x18004b0ec  mov     [rbp+300h+var_5A], ax
0x18004b0f3  lea     rdi, [rbp+300h+var_260]
0x18004b0fa  lea     rdx, [rsp+400h+var_3B8]; unsigned int *
0x18004b0ff  mov     rcx, rdi; unsigned __int16 *
0x18004b102  xor     esi, esi
0x18004b104  xor     r14d, r14d
0x18004b107  call    ?ToDwordSyncFromFlags@@YAJPEAGPEAK@Z; ToDwordSyncFromFlags(ushort *,ulong *)
0x18004b10c  xor     edx, edx
0x18004b10e  lea     r8d, [rsi+8]
0x18004b112  test    eax, eax
0x18004b114  jns     short loc_18004B123
0x18004b116  cmp     ebx, r8d
0x18004b119  mov     ecx, edx
0x18004b11b  setnz   cl
0x18004b11e  add     ecx, r12d
0x18004b121  jmp     short loc_18004B127
0x18004b123  mov     ecx, [rsp+400h+var_3B8]
0x18004b127  mov     eax, 3
0x18004b12c  mov     [rsp+400h+var_3A0], r12d
0x18004b131  mov     [rbp+300h+var_380], eax
0x18004b134  mov     [rbp+300h+var_348], eax
0x18004b137  mov     [rbp+300h+var_344], eax
0x18004b13a  mov     [rbp+300h+var_334], eax
0x18004b13d  mov     [rbp+300h+var_2D0], eax
0x18004b140  mov     [rbp+300h+var_2CC], eax
0x18004b143  mov     [rbp+300h+var_2BC], eax
0x18004b146  mov     [rbp+300h+var_2A0], eax
0x18004b149  mov     [rbp+300h+var_28C], eax
0x18004b14c  mov     [rbp+300h+var_278], eax
0x18004b152  mov     [rbp+300h+var_26C], eax
0x18004b158  mov     [rbp+300h+var_264], eax
0x18004b15e  mov     [rsp+400h+var_39C], r13
0x18004b163  mov     [rsp+400h+var_394], edx
0x18004b167  mov     [rsp+400h+var_390], r12d
0x18004b16c  mov     [rsp+400h+var_38C], r12d
0x18004b171  mov     [rsp+400h+var_388], r12d
0x18004b176  mov     [rsp+400h+var_384], r12d
0x18004b17b  mov     [rbp+300h+var_37C], r12d
0x18004b17f  mov     [rbp+300h+var_378], r12
0x18004b183  mov     [rbp+300h+var_370], r12d
0x18004b187  mov     [rbp+300h+var_36C], r13d
0x18004b18b  mov     [rbp+300h+var_368], r12d
0x18004b18f  mov     [rbp+300h+var_364], r12d
0x18004b193  mov     [rbp+300h+var_360], r13d
0x18004b197  mov     [rbp+300h+var_35C], r13d
0x18004b19b  mov     [rbp+300h+var_358], r13d
0x18004b19f  mov     [rbp+300h+var_354], r12d
0x18004b1a3  mov     [rbp+300h+var_350], r12d
0x18004b1a7  mov     [rbp+300h+var_34C], r12d
0x18004b1ab  mov     [rbp+300h+var_340], r12d
0x18004b1af  mov     [rbp+300h+var_33C], r12
0x18004b1b3  mov     [rbp+300h+var_330], r13d
0x18004b1b7  mov     [rbp+300h+var_32C], r12d
0x18004b1bb  mov     [rbp+300h+var_328], r13d
0x18004b1bf  mov     [rbp+300h+var_324], r13
0x18004b1c3  mov     [rbp+300h+var_31C], edx
0x18004b1c6  mov     [rbp+300h+var_318], r13d
0x18004b1ca  mov     [rbp+300h+var_314], r13d
0x18004b1ce  mov     [rbp+300h+var_310], r12d
0x18004b1d2  mov     [rbp+300h+var_30C], r12d
0x18004b1d6  mov     [rbp+300h+var_308], r12d
0x18004b1da  mov     [rbp+300h+var_304], r13d
0x18004b1de  mov     [rbp+300h+var_300], r13
0x18004b1e2  mov     [rbp+300h+var_2F8], r12d
0x18004b1e6  mov     [rbp+300h+var_2F4], r13d
0x18004b1ea  mov     [rbp+300h+var_2F0], r13d
0x18004b1ee  mov     [rbp+300h+var_2EC], r13d
0x18004b1f2  mov     [rbp+300h+var_2E8], r13d
0x18004b1f6  mov     [rbp+300h+var_2E4], r13d
0x18004b1fa  mov     [rbp+300h+var_2E0], r13d
0x18004b1fe  mov     [rbp+300h+var_2DC], r13d
0x18004b202  mov     [rbp+300h+var_2D8], r13d
0x18004b206  mov     [rbp+300h+var_2D4], r12d
0x18004b20a  mov     [rbp+300h+var_2C8], r13d
0x18004b20e  mov     [rbp+300h+var_2C4], r13
0x18004b212  mov     [rbp+300h+var_2B8], r13d
0x18004b216  mov     [rbp+300h+var_2B4], r13d
0x18004b21a  mov     [rbp+300h+var_2B0], r8d
0x18004b21e  mov     [rbp+300h+var_2AC], r13
0x18004b222  mov     [rbp+300h+var_2A4], edx
0x18004b225  mov     [rbp+300h+var_29C], r8d
0x18004b229  mov     [rbp+300h+var_298], r13d
0x18004b22d  mov     [rbp+300h+var_294], r12d
0x18004b231  mov     [rbp+300h+var_290], r12d
0x18004b235  mov     [rbp+300h+var_288], r8d
0x18004b239  mov     [rbp+300h+var_284], r13d
0x18004b23d  mov     [rbp+300h+var_280], r13d
0x18004b244  mov     [rbp+300h+var_27C], r12d
0x18004b24b  mov     [rbp+300h+var_274], r8d
0x18004b252  mov     [rbp+300h+var_270], r13d
0x18004b259  mov     [rbp+300h+var_268], r12d
0x18004b260  lea     rax, [rdx+rdx*4]
0x18004b264  cmp     ebx, [rsp+rax*4+400h+var_3A0]
0x18004b268  jnz     short loc_18004B287
0x18004b26a  cmp     ecx, dword ptr [rsp+rax*4+400h+var_39C+4]
0x18004b26e  jnz     short loc_18004B287
0x18004b270  cmp     dword ptr [rsp+rax*4+400h+var_39C], r13d
0x18004b275  jz      short loc_18004B27E
0x18004b277  cmp     r15d, dword ptr [rsp+rax*4+400h+var_39C]
0x18004b27c  jnz     short loc_18004B287
0x18004b27e  mov     esi, [rsp+rax*4+400h+var_394]
0x18004b282  mov     r14d, [rsp+rax*4+400h+var_390]
0x18004b287  add     rdx, r12
0x18004b28a  cmp     rdx, 10h
0x18004b28e  jnz     short loc_18004B260
0x18004b290  mov     r8d, r12d
0x18004b293  xor     edx, edx
0x18004b295  mov     ecx, r14d
0x18004b298  call    ?CreateRoleSpecificRegValues@@YAJW4RoleType@@HH@Z; CreateRoleSpecificRegValues(RoleType,int,int)
0x18004b29d  mov     ecx, esi; unsigned int
0x18004b29f  call    ?WriteSyncFromFlagsSpecial@@YAJK@Z; WriteSyncFromFlagsSpecial(ulong)
0x18004b2a4  mov     rcx, [rsp+400h+hkey]; hKey
0x18004b2a9  test    rcx, rcx
0x18004b2ac  jz      short loc_18004B2BA
0x18004b2ae  call    cs:__imp_RegCloseKey
0x18004b2b5  nop     dword ptr [rax+rax+00h]
0x18004b2ba  mov     rcx, [rbp+300h+var_50]
0x18004b2c1  xor     rcx, rsp; StackCookie
0x18004b2c4  call    __security_check_cookie
0x18004b2c9  add     rsp, 3C8h
0x18004b2d0  pop     r15
0x18004b2d2  pop     r14
0x18004b2d4  pop     r13
0x18004b2d6  pop     r12
0x18004b2d8  pop     rdi
0x18004b2d9  pop     rsi
0x18004b2da  pop     rbx
0x18004b2db  pop     rbp
0x18004b2dc  retn
```
