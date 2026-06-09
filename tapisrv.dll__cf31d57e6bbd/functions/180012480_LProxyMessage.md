# LProxyMessage

- ea: `0x180012480`
- end: `0x180012a80`
- name: `LProxyMessage`
- size: `1536`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x180028100`

## callees

- `0x180001f50`
- `0x1800064f8`
- `0x180006dec`
- `0x180012480`
- `0x180017b74`
- `0x180019fcc`
- `0x18001aecc`
- `0x18002c8d4`
- `0x18002f778`
- `0x1800342d4`
- `0x18003dc84`
- `0x18003e15c`

## string_xrefs

- `0x1800126d9`: `ERROR: lineProxyMessage (AGENTSTATUS): dwParam1 bad addr ID (=x%x, num addrs=x%x)`
- `0x180012748`: `ERROR: lineProxyMessage (AGENTSTATUS): dwParam2 (=x%x) bad LINEAGENTSTATUS_ flags`
- `0x18001272f`: `ERROR: lineProxyMessage (AGENTSTATUS): dwParam3 (=x%x) bad LINEAGENTSTATE_ flags`
- `0x1800126bd`: `ERROR: lineProxyMessage (AGENTSESSIONSTATUS): dwParam2 (=x%x) bad LINEAGENTSESSIONSTATUS_ flags`
- `0x1800126b1`: `ERROR: lineProxyMessage (AGENTSESSIONSTATUS): dwParam3 (=x%x) bad LINEAGENTSESSIONSTATE_ flags`
- `0x180012641`: `ERROR: lineProxyMessage (AGENTSTATUSEX): dwParam2 (=x%x) bad LINEAGENTSTATUSEX_ flags`
- `0x180012635`: `ERROR: lineProxyMessage (AGENTSTATUSEX): dwParam3 (=x%x) bad LINEAGENTSTATEEX_ flags`

## pseudocode

```c
__int64 __fastcall LProxyMessage(__int64 a1, _DWORD *a2)
{
  int v4; // eax
  unsigned int v5; // r15d
  char *v6; // r13
  __int64 v7; // r10
  __int64 v8; // r8
  __int64 v9; // r8
  unsigned int v10; // edx
  __int64 v11; // r8
  bool v12; // zf
  __int64 v13; // r8
  unsigned int v14; // r9d
  unsigned int v15; // r8d
  __int64 v16; // r8
  unsigned int *v17; // r12
  __int64 v18; // rax
  __int64 v19; // rcx
  unsigned __int64 v20; // rbx
  int v21; // eax
  unsigned int v22; // r14d
  unsigned int *v23; // rbx
  __int64 v24; // r15
  unsigned int v25; // ecx
  __int64 v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int LineClientListFromLine; // eax
  unsigned int v30; // r14d
  __int64 v31; // r15
  unsigned int v32; // ecx
  unsigned int v34; // [rsp+74h] [rbp-104h]
  LPVOID lpMem; // [rsp+78h] [rbp-100h] BYREF
  unsigned int v36; // [rsp+80h] [rbp-F8h] BYREF
  unsigned int v37; // [rsp+84h] [rbp-F4h] BYREF
  char *v38; // [rsp+88h] [rbp-F0h] BYREF
  _DWORD *v39; // [rsp+90h] [rbp-E8h]
  __int64 lpTargetHandle; // [rsp+98h] [rbp-E0h] BYREF
  unsigned int v41; // [rsp+A0h] [rbp-D8h] BYREF
  int v42; // [rsp+A4h] [rbp-D4h]
  int v43; // [rsp+A8h] [rbp-D0h]
  int v44; // [rsp+ACh] [rbp-CCh]
  int v45; // [rsp+B0h] [rbp-C8h]
  int v46; // [rsp+B4h] [rbp-C4h]
  int v47; // [rsp+B8h] [rbp-C0h]
  int v48; // [rsp+BCh] [rbp-BCh]
  int v49; // [rsp+C0h] [rbp-B8h]
  int v50; // [rsp+C4h] [rbp-B4h]
  int v51; // [rsp+C8h] [rbp-B0h]
  _DWORD *v52; // [rsp+F0h] [rbp-88h]
  __int64 v53; // [rsp+F8h] [rbp-80h]
  _BYTE v54[4]; // [rsp+100h] [rbp-78h] BYREF
  int v55; // [rsp+104h] [rbp-74h]

  v37 = 0;
  lpTargetHandle = 0;
  lpMem = 0;
  v36 = 0;
  v38 = 0;
  v4 = LineProlog(
         a1,
         2,
         a2[2],
         (unsigned int *)&lpMem,
         0,
         (LPHANDLE)&lpTargetHandle,
         &v37,
         0xFFFFFFFF,
         0,
         0,
         0,
         &v36,
         &v38);
  *a2 = v4;
  if ( v4 )
    return LineEpilogSync(a2, lpTargetHandle, v37, v36);
  v5 = a2[4];
  v34 = v5;
  v55 = 0;
  memset_0(v54, 0, 0x44u);
  lpMem = v54;
  v6 = v38;
  v7 = *((_QWORD *)v38 + 4);
  v53 = v7;
  if ( (*((_DWORD *)v38 + 16) & 0x40000000) == 0 )
  {
    *a2 = -2147483577;
    return LineEpilogSync(a2, lpTargetHandle, v37, v36);
  }
  if ( v5 != 21 )
  {
    switch ( v5 )
    {
      case 0x16u:
        v14 = *(_DWORD *)(v7 + 228);
        v15 = a2[5];
        if ( v15 >= v14 )
        {
          TRACELogPrint(
            65538,
            "ERROR: lineProxyMessage (AGENTSTATUS): dwParam1 bad addr ID (=x%x, num addrs=x%x)",
            v15,
            v14);
          goto LABEL_36;
        }
        v16 = (unsigned int)a2[6];
        if ( !(_DWORD)v16 || (v16 & 0xFFFFFE00) != 0 )
        {
          TRACELogPrint(65538, "ERROR: lineProxyMessage (AGENTSTATUS): dwParam2 (=x%x) bad LINEAGENTSTATUS_ flags", v16);
          goto LABEL_36;
        }
        v10 = a2[7];
        if ( (v16 & 2) != 0 )
        {
          if ( !v10 || ((a2[7] - 1) & a2[7]) != 0 || (a2[7] & 0xFC00) != 0 )
          {
            TRACELogPrint(
              65538,
              "ERROR: lineProxyMessage (AGENTSTATUS): dwParam3 (=x%x) bad LINEAGENTSTATE_ flags",
              v10);
            goto LABEL_36;
          }
          goto LABEL_63;
        }
        break;
      case 0x1Bu:
        v13 = (unsigned int)a2[6];
        if ( !(_DWORD)v13 || (v13 & 0xFFFFFFF8) != 0 )
        {
          TRACELogPrint(
            65538,
            "ERROR: lineProxyMessage (AGENTSESSIONSTATUS): dwParam2 (=x%x) bad LINEAGENTSESSIONSTATUS_ flags",
            v13);
          goto LABEL_36;
        }
        v10 = a2[7];
        if ( (v13 & 2) != 0 )
        {
          if ( !v10 || ((v10 - 1) & v10) != 0 || (v10 & 0xFFFFFFC0) != 0 )
          {
            TRACELogPrint(
              65538,
              "ERROR: lineProxyMessage (AGENTSESSIONSTATUS): dwParam3 (=x%x) bad LINEAGENTSESSIONSTATE_ flags",
              v10);
            goto LABEL_36;
          }
          goto LABEL_63;
        }
        break;
      case 0x1Cu:
        v11 = (unsigned int)a2[6];
        if ( !(_DWORD)v11 || (v11 & 0xFFFFFFF8) != 0 )
        {
          TRACELogPrint(65538, "ERROR: lineProxyMessage (QUEUESTATUS): dwParam2 (=x%x) bad LINEQUEUESTATUS_ flags", v11);
          goto LABEL_36;
        }
LABEL_25:
        v12 = a2[7] == 0;
        goto LABEL_44;
      case 0x1Du:
        v9 = (unsigned int)a2[6];
        if ( !(_DWORD)v9 || (v9 & 0xFFFFFFF8) != 0 )
        {
          TRACELogPrint(
            65538,
            "ERROR: lineProxyMessage (AGENTSTATUSEX): dwParam2 (=x%x) bad LINEAGENTSTATUSEX_ flags",
            v9);
          goto LABEL_36;
        }
        v10 = a2[7];
        if ( (v9 & 2) != 0 )
        {
          if ( !v10 || ((v10 - 1) & v10) != 0 || (v10 & 0xFFFFFF80) != 0 )
          {
            TRACELogPrint(
              65538,
              "ERROR: lineProxyMessage (AGENTSTATUSEX): dwParam3 (=x%x) bad LINEAGENTSTATEEX_ flags",
              v10);
            goto LABEL_36;
          }
          goto LABEL_63;
        }
        break;
      case 0x1Eu:
        v8 = (unsigned int)a2[5];
        if ( !(_DWORD)v8 || (v8 & 0xFFFFFFFC) != 0 )
        {
          TRACELogPrint(65538, "ERROR: lineProxyMessage (GROUPSTATUS): dwParam1 (=x%x) bad LINEQUEUESTATUS_ flags", v8);
          goto LABEL_36;
        }
        if ( a2[6] )
        {
          a2[6] = 0;
          goto LABEL_63;
        }
        goto LABEL_25;
      default:
        TRACELogPrint(65538, "ERROR : lineProxyMessage: inval dwMsg (=x%x)", v5);
LABEL_36:
        *a2 = -2147483598;
        return LineEpilogSync(a2, lpTargetHandle, v37, v36);
    }
    v12 = v10 == 0;
LABEL_44:
    if ( !v12 )
      a2[7] = 0;
    goto LABEL_63;
  }
  v17 = a2 + 3;
  if ( a2[3] )
  {
    v18 = ReferenceCall(*v17, a1);
    if ( !v18 )
    {
      *a2 = -2147483624;
      return LineEpilogSync(a2, lpTargetHandle, v37, v36);
    }
    v39 = a2 + 3;
    v20 = *(_QWORD *)(v18 + 24);
    DereferenceObject(v19, *v17, 1);
    v21 = GetCallClientListFromCall(v20, (_DWORD **)&lpMem);
    *a2 = v21;
    if ( v21 )
      return LineEpilogSync(a2, lpTargetHandle, v37, v36);
    v41 = 44;
    v43 = 0;
    v45 = 21;
    v52 = a2 + 5;
    v47 = a2[5];
    v48 = a2[6];
    v49 = a2[7];
    v22 = 0;
    v23 = (unsigned int *)lpMem;
    while ( v22 < *v23 )
    {
      v24 = *(_QWORD *)&v23[2 * v22 + 2];
      if ( *(_DWORD *)(v24 + 88) != *v17 )
      {
        v38 = *(char **)(*(_QWORD *)(v24 + 16) + 16LL);
        v25 = *((_DWORD *)v38 + 12);
        if ( v25 >= 0x20000 && !(unsigned int)FMsgDisabled(v25, v24 + 92, v34) )
        {
          v42 = *((_DWORD *)v38 + 7);
          v44 = *(_DWORD *)(v24 + 88);
          v26 = *(_QWORD *)(v24 + 16);
          v46 = *(_DWORD *)(v26 + 72);
          v50 = *(_DWORD *)(v26 + 56);
          v27 = *(_QWORD *)(v24 + 80);
          v28 = v27 ? *(_DWORD *)(v27 + 28) : 0;
          v51 = v28;
          if ( *(_DWORD *)v24 == 1229734723 )
            WriteEventBuffer(*(_QWORD *)(v24 + 8), &v41);
        }
      }
      ++v22;
    }
    goto LABEL_72;
  }
LABEL_63:
  LineClientListFromLine = GetLineClientListFromLine((_QWORD *)v7, (_DWORD **)&lpMem);
  *a2 = LineClientListFromLine;
  if ( LineClientListFromLine )
    return LineEpilogSync(a2, lpTargetHandle, v37, v36);
  v41 = 40;
  v43 = 0;
  v45 = v5;
  v39 = a2 + 5;
  v47 = a2[5];
  v48 = a2[6];
  v49 = a2[7];
  v50 = 0;
  v30 = 0;
  v23 = (unsigned int *)lpMem;
  while ( v30 < *v23 )
  {
    v31 = *(_QWORD *)&v23[2 * v30 + 2];
    if ( (char *)v31 != v6 )
    {
      v32 = *(_DWORD *)(*(_QWORD *)(v31 + 16) + 48LL);
      if ( v32 >= 0x20000 && !(unsigned int)FMsgDisabled(v32, v31 + 168, v34) )
      {
        v42 = *(_DWORD *)(*(_QWORD *)(v31 + 16) + 28LL);
        v44 = *(_DWORD *)(v31 + 56);
        v46 = *(_DWORD *)(v31 + 72);
        if ( *(_DWORD *)v31 == 1229734732 )
          WriteEventBuffer(*(_QWORD *)(v31 + 8), &v41);
      }
    }
    ++v30;
  }
LABEL_72:
  if ( v23 != (unsigned int *)v54 )
    ServerFree(v23);
  return LineEpilogSync(a2, lpTargetHandle, v37, v36);
}

```

## disassembly

```asm
0x180012480  mov     r11, rsp
0x180012483  mov     [r11+8], rbx
0x180012487  mov     [r11+18h], rsi
0x18001248b  mov     [r11+10h], rdx
0x18001248f  push    rdi
0x180012490  push    r12
0x180012492  push    r13
0x180012494  push    r14
0x180012496  push    r15
0x180012498  sub     rsp, 150h
0x18001249f  mov     rdi, rdx
0x1800124a2  mov     rbx, rcx
0x1800124a5  xor     esi, esi
0x1800124a7  mov     [rsp+178h+var_F4], esi
0x1800124ae  mov     [r11-0E0h], rsi
0x1800124b5  mov     [rsp+178h+lpMem], rsi
0x1800124ba  mov     [rsp+178h+var_F8], esi
0x1800124c1  mov     [r11-0F0h], rsi
0x1800124c8  lea     rax, [r11-0F0h]
0x1800124cf  mov     [rsp+178h+var_118], rax; __int64
0x1800124d4  lea     rax, [r11-0F8h]
0x1800124db  mov     [rsp+178h+var_120], rax; __int64
0x1800124e0  mov     [rsp+178h+var_128], esi; int
0x1800124e4  mov     [rsp+178h+var_130], rsi; __int64
0x1800124e9  mov     [rsp+178h+var_138], rsi; __int64
0x1800124ee  mov     [rsp+178h+var_140], 0FFFFFFFFh; int
0x1800124f6  lea     rax, [r11-0F4h]
0x1800124fd  mov     [rsp+178h+var_148], rax; __int64
0x180012502  lea     rax, [r11-0E0h]
0x180012509  mov     [rsp+178h+lpTargetHandle], rax; lpTargetHandle
0x18001250e  mov     [rsp+178h+var_158], esi; int
0x180012512  lea     r9, [rsp+178h+lpMem]; int
0x180012517  mov     r8d, [rdx+8]; int
0x18001251b  lea     r14d, [rsi+2]
0x18001251f  mov     edx, r14d; int
0x180012522  call    LineProlog
0x180012527  mov     [rdi], eax
0x180012529  test    eax, eax
0x18001252b  jnz     loc_180012A43
0x180012531  mov     r15d, [rdi+10h]
0x180012535  mov     [rsp+178h+var_104], r15d
0x18001253a  xor     eax, eax
0x18001253c  mov     [rsp+178h+var_74], eax
0x180012543  xor     edx, edx; Val
0x180012545  lea     r8d, [rsi+44h]; Size
0x180012549  lea     rcx, [rsp+178h+var_78]; void *
0x180012551  call    memset_0
0x180012556  lea     rax, [rsp+178h+var_78]
0x18001255e  mov     [rsp+178h+lpMem], rax
0x180012563  mov     r13, [rsp+178h+var_F0]
0x18001256b  mov     r10, [r13+20h]
0x18001256f  mov     [rsp+178h+var_80], r10
0x180012577  test    dword ptr [r13+40h], 40000000h
0x18001257f  jnz     short loc_18001258C
0x180012581  mov     dword ptr [rdi], 80000047h
0x180012587  jmp     loc_180012A43
0x18001258c  mov     eax, r15d
0x18001258f  sub     eax, 15h
0x180012592  jz      loc_18001275B
0x180012598  sub     eax, 1
0x18001259b  jz      loc_1800126C9
0x1800125a1  sub     eax, 5
0x1800125a4  jz      loc_180012673
0x1800125aa  sub     eax, 1
0x1800125ad  jz      loc_18001264D
0x1800125b3  sub     eax, 1
0x1800125b6  jz      short loc_1800125F7
0x1800125b8  cmp     eax, 1
0x1800125bb  jz      short loc_1800125CC
0x1800125bd  mov     r8d, r15d
0x1800125c0  lea     rdx, aErrorLineproxy_1; "ERROR : lineProxyMessage: inval dwMsg ("...
0x1800125c7  jmp     loc_18001274F
0x1800125cc  mov     r8d, [rdi+14h]
0x1800125d0  test    r8d, r8d
0x1800125d3  jz      short loc_1800125EB
0x1800125d5  test    r8d, 0FFFFFFFCh
0x1800125dc  jnz     short loc_1800125EB
0x1800125de  cmp     [rdi+18h], esi
0x1800125e1  jz      short loc_18001265F
0x1800125e3  mov     [rdi+18h], esi
0x1800125e6  jmp     loc_1800128FC
0x1800125eb  lea     rdx, aErrorLineproxy_4; "ERROR: lineProxyMessage (GROUPSTATUS): "...
0x1800125f2  jmp     loc_18001274F
0x1800125f7  mov     r8d, [rdi+18h]
0x1800125fb  test    r8d, r8d
0x1800125fe  jz      short loc_180012641
0x180012600  test    r8d, 0FFFFFFF8h
0x180012607  jnz     short loc_180012641
0x180012609  mov     edx, [rdi+1Ch]
0x18001260c  test    r14b, r8b
0x18001260f  jz      loc_180012738
0x180012615  test    edx, edx
0x180012617  jz      short loc_180012632
0x180012619  lea     eax, [rdx-1]
0x18001261c  test    edx, eax
0x18001261e  setz    cl
0x180012621  test    edx, 0FFFFFF80h
0x180012627  setz    al
0x18001262a  test    al, cl
0x18001262c  jnz     loc_1800128FC
0x180012632  mov     r8d, edx
0x180012635  lea     rdx, aErrorLineproxy_3; "ERROR: lineProxyMessage (AGENTSTATUSEX)"...
0x18001263c  jmp     loc_18001274F
0x180012641  lea     rdx, aErrorLineproxy_6; "ERROR: lineProxyMessage (AGENTSTATUSEX)"...
0x180012648  jmp     loc_18001274F
0x18001264d  mov     r8d, [rdi+18h]
0x180012651  test    r8d, r8d
0x180012654  jz      short loc_180012667
0x180012656  test    r8d, 0FFFFFFF8h
0x18001265d  jnz     short loc_180012667
0x18001265f  cmp     [rdi+1Ch], esi
0x180012662  jmp     loc_18001273A
0x180012667  lea     rdx, aErrorLineproxy_0; "ERROR: lineProxyMessage (QUEUESTATUS): "...
0x18001266e  jmp     loc_18001274F
0x180012673  mov     r8d, [rdi+18h]
0x180012677  test    r8d, r8d
0x18001267a  jz      short loc_1800126BD
0x18001267c  test    r8d, 0FFFFFFF8h
0x180012683  jnz     short loc_1800126BD
0x180012685  mov     edx, [rdi+1Ch]
0x180012688  test    r14b, r8b
0x18001268b  jz      loc_180012738
0x180012691  test    edx, edx
0x180012693  jz      short loc_1800126AE
0x180012695  lea     eax, [rdx-1]
0x180012698  test    edx, eax
0x18001269a  setz    cl
0x18001269d  test    edx, 0FFFFFFC0h
0x1800126a3  setz    al
0x1800126a6  test    al, cl
0x1800126a8  jnz     loc_1800128FC
0x1800126ae  mov     r8d, edx
0x1800126b1  lea     rdx, aErrorLineproxy_8; "ERROR: lineProxyMessage (AGENTSESSIONST"...
0x1800126b8  jmp     loc_18001274F
0x1800126bd  lea     rdx, aErrorLineproxy_5; "ERROR: lineProxyMessage (AGENTSESSIONST"...
0x1800126c4  jmp     loc_18001274F
0x1800126c9  mov     r9d, [r10+0E4h]
0x1800126d0  mov     r8d, [rdi+14h]
0x1800126d4  cmp     r8d, r9d
0x1800126d7  jb      short loc_1800126F5
0x1800126d9  lea     rdx, aErrorLineproxy_7; "ERROR: lineProxyMessage (AGENTSTATUS): "...
0x1800126e0  mov     ecx, 10002h
0x1800126e5  call    TRACELogPrint
0x1800126ea  mov     dword ptr [rdi], 80000032h
0x1800126f0  jmp     loc_180012A43
0x1800126f5  mov     r8d, [rdi+18h]
0x1800126f9  test    r8d, r8d
0x1800126fc  jz      short loc_180012748
0x1800126fe  test    r8d, 0FFFFFE00h
0x180012705  jnz     short loc_180012748
0x180012707  mov     edx, [rdi+1Ch]
0x18001270a  test    r14b, r8b
0x18001270d  jz      short loc_180012738
0x18001270f  test    edx, edx
0x180012711  jz      short loc_18001272C
0x180012713  lea     eax, [rdx-1]
0x180012716  test    edx, eax
0x180012718  setz    cl
0x18001271b  test    edx, 0FC00h
0x180012721  setz    al
0x180012724  test    al, cl
0x180012726  jnz     loc_1800128FC
0x18001272c  mov     r8d, edx
0x18001272f  lea     rdx, aErrorLineproxy; "ERROR: lineProxyMessage (AGENTSTATUS): "...
0x180012736  jmp     short loc_18001274F
0x180012738  test    edx, edx
0x18001273a  jz      loc_1800128FC
0x180012740  mov     [rdi+1Ch], esi
0x180012743  jmp     loc_1800128FC
0x180012748  lea     rdx, aErrorLineproxy_2; "ERROR: lineProxyMessage (AGENTSTATUS): "...
0x18001274f  mov     ecx, 10002h
0x180012754  call    TRACELogPrint
0x180012759  jmp     short loc_1800126EA
0x18001275b  lea     r12, [rdi+0Ch]
0x18001275f  cmp     [r12], esi
0x180012763  jz      loc_1800128FC
0x180012769  mov     rdx, rbx
0x18001276c  mov     ecx, [r12]
0x180012770  call    ReferenceCall
0x180012775  test    rax, rax
0x180012778  jnz     short loc_180012785
0x18001277a  mov     dword ptr [rdi], 80000018h
0x180012780  jmp     loc_180012A43
0x180012785  mov     [rsp+178h+var_E8], r12
0x18001278d  mov     rbx, [rax+18h]
0x180012791  mov     r8d, 1
0x180012797  mov     edx, [r12]
0x18001279b  call    DereferenceObject
0x1800127a0  lea     rdx, [rsp+178h+lpMem]
0x1800127a5  mov     rcx, rbx
0x1800127a8  call    GetCallClientListFromCall
0x1800127ad  mov     [rdi], eax
0x1800127af  test    eax, eax
0x1800127b1  jnz     loc_180012A43
0x1800127b7  mov     [rsp+178h+var_D8], 2Ch ; ','
0x1800127c2  mov     [rsp+178h+var_D0], esi
0x1800127c9  mov     [rsp+178h+var_C8], 15h
0x1800127d4  lea     r13, [rdi+14h]
0x1800127d8  mov     [rsp+178h+var_88], r13
0x1800127e0  mov     eax, [r13+0]
0x1800127e4  mov     [rsp+178h+var_C0], eax
0x1800127eb  mov     eax, [rdi+18h]
0x1800127ee  mov     [rsp+178h+var_BC], eax
0x1800127f5  mov     eax, [rdi+1Ch]
0x1800127f8  mov     [rsp+178h+var_B8], eax
0x1800127ff  mov     r14d, esi
0x180012802  mov     [rsp+178h+var_108], esi
0x180012806  mov     rbx, [rsp+178h+lpMem]
0x18001280b  cmp     r14d, [rbx]
0x18001280e  jnb     loc_180012A1E
0x180012814  mov     eax, r14d
0x180012817  mov     r15, [rbx+rax*8+8]
0x18001281c  mov     eax, [r12]
0x180012820  cmp     [r15+58h], eax
0x180012824  jz      loc_1800128C9
0x18001282a  mov     rax, [r15+10h]
0x18001282e  mov     rax, [rax+10h]
0x180012832  mov     [rsp+178h+var_F0], rax
0x18001283a  mov     ecx, [rax+30h]
0x18001283d  cmp     ecx, 20000h
0x180012843  jb      loc_1800128C9
0x180012849  lea     rdx, [r15+5Ch]
0x18001284d  mov     r9d, [r13+0]
0x180012851  mov     r8d, [rsp+178h+var_104]
0x180012856  call    FMsgDisabled
0x18001285b  test    eax, eax
0x18001285d  jnz     loc_1800128EF
0x180012863  mov     rax, [rsp+178h+var_F0]
0x18001286b  mov     eax, [rax+1Ch]
0x18001286e  mov     [rsp+178h+var_D4], eax
0x180012875  mov     eax, [r15+58h]
0x180012879  mov     [rsp+178h+var_CC], eax
0x180012880  mov     rcx, [r15+10h]
0x180012884  mov     eax, [rcx+48h]
0x180012887  mov     [rsp+178h+var_C4], eax
0x18001288e  mov     eax, [rcx+38h]
0x180012891  mov     [rsp+178h+var_B4], eax
0x180012898  mov     rax, [r15+50h]
0x18001289c  test    rax, rax
0x18001289f  jz      short loc_1800128A6
0x1800128a1  mov     eax, [rax+1Ch]
0x1800128a4  jmp     short loc_1800128A8
0x1800128a6  mov     eax, esi
0x1800128a8  mov     [rsp+178h+var_B0], eax
0x1800128af  cmp     dword ptr [r15], 494C4343h
0x1800128b6  jnz     short loc_1800128C9
0x1800128b8  lea     rdx, [rsp+178h+var_D8]
0x1800128c0  mov     rcx, [r15+8]
0x1800128c4  call    WriteEventBuffer
0x1800128c9  jmp     short loc_1800128EF
0x1800128cb  xor     esi, esi
0x1800128cd  mov     rdi, [rsp+178h+arg_8]
0x1800128d5  mov     r14d, [rsp+178h+var_108]
0x1800128da  mov     rbx, [rsp+178h+lpMem]
0x1800128df  mov     r13, [rsp+178h+var_88]
0x1800128e7  mov     r12, [rsp+178h+var_E8]
0x1800128ef  inc     r14d
0x1800128f2  mov     [rsp+178h+var_108], r14d
0x1800128f7  jmp     loc_18001280B
0x1800128fc  lea     rdx, [rsp+178h+lpMem]
0x180012901  mov     rcx, r10
0x180012904  call    GetLineClientListFromLine
0x180012909  mov     [rdi], eax
0x18001290b  test    eax, eax
0x18001290d  jnz     loc_180012A43
0x180012913  mov     [rsp+178h+var_D8], 28h ; '('
0x18001291e  mov     [rsp+178h+var_D0], esi
0x180012925  mov     [rsp+178h+var_C8], r15d
0x18001292d  lea     r12, [rdi+14h]
0x180012931  mov     [rsp+178h+var_E8], r12
0x180012939  mov     eax, [r12]
0x18001293d  mov     [rsp+178h+var_C0], eax
0x180012944  mov     eax, [rdi+18h]
0x180012947  mov     [rsp+178h+var_BC], eax
0x18001294e  mov     eax, [rdi+1Ch]
0x180012951  mov     [rsp+178h+var_B8], eax
0x180012958  mov     [rsp+178h+var_B4], esi
0x18001295f  mov     r14d, esi
0x180012962  mov     [rsp+178h+var_108], esi
0x180012966  mov     rbx, [rsp+178h+lpMem]
0x18001296b  cmp     r14d, [rbx]
0x18001296e  jnb     loc_180012A1E
0x180012974  mov     eax, r14d
0x180012977  mov     r15, [rbx+rax*8+8]
0x18001297c  cmp     r15, r13
0x18001297f  jz      loc_180012A11
0x180012985  mov     rax, [r15+10h]
0x180012989  mov     ecx, [rax+30h]
0x18001298c  cmp     ecx, 20000h
0x180012992  jb      short loc_1800129EB
0x180012994  lea     rdx, [r15+0A8h]
0x18001299b  mov     r9d, [r12]
0x18001299f  mov     r8d, [rsp+178h+var_104]
0x1800129a4  call    FMsgDisabled
0x1800129a9  test    eax, eax
0x1800129ab  jnz     short loc_180012A11
0x1800129ad  mov     rax, [r15+10h]
0x1800129b1  mov     edx, [rax+1Ch]
0x1800129b4  mov     [rsp+178h+var_D4], edx
0x1800129bb  mov     eax, [r15+38h]
  ... truncated ...
```
