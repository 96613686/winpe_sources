# SxspParseGUID(ushort const *,unsigned __int64,_GUID &)

- ea: `0x180002540`
- end: `0x180002a64`
- name: `?SxspParseGUID@@YAHPEBG_KAEAU_GUID@@@Z`
- size: `1316`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, struct _GUID *)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800017b8`
- `0x180001fe0`
- `0x1800023e0`
- `0x180002a70`
- `0x1800358d0`
- `0x18003731c`
- `0x180045cb0`

## callees

- `0x180002540`
- `0x18000c000`
- `0x18001c2c8`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x1800027e7`
- `ntdll!RtlPopFrame` at `0x1800027e7`
- `ntdll!RtlPushFrame` at `0x18000259f`
- `ntdll!RtlPushFrame` at `0x18000259f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800029ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800029ab`

## string_xrefs

- `0x180002995`: `SXS.DLL: SxspParseGUID() passed in GUID where character %d is not a dash.\n`
- `0x1800029bf`: `SXS.DLL: SxspParseGUID() passed in GUID where character %d is not a dash.\n`
- `0x1800029f4`: `SXS.DLL: SxspParseGUID() passed in GUID where character %d is not a dash.\n`
- `0x180002830`: `SXS.DLL: SxspParseGUID() passed in GUID where character %d is not hexidecimal\n`
- `0x18000285a`: `SXS.DLL: SxspParseGUID() passed in GUID where character %d is not hexidecimal\n`
- `0x1800029cb`: `SXS.DLL: SxspParseGUID() caller passed in GUID that is %d characters long; GUIDs must be exactly 38 characters long.\n`
- `0x1800029d4`: `SXS.DLL: SxspParseGUID() caller pass in GUID that does not begin with a left brace ('{')\n`
- `0x180002885`: `SXS.DLL: SxspParseGUID() given GUID where character %d is not hexidecimal\n`
- `0x180002a1f`: `SXS.DLL: SxspParseGUID() passed in GUID which does not terminate with a closing brace ('}')\n`

## pseudocode

```c
__int64 __fastcall SxspParseGUID(const unsigned __int16 *a1, __int64 a2, struct _GUID *a3)
{
  const unsigned __int16 *v6; // rbx
  __int64 v7; // r10
  unsigned int v8; // r9d
  unsigned int v9; // ecx
  _WORD *v10; // rdx
  unsigned int v11; // r8d
  int v12; // r9d
  int v13; // eax
  int v14; // r11d
  unsigned int v15; // r8d
  _WORD *v16; // rcx
  unsigned int v17; // r9d
  int v18; // r11d
  int v19; // eax
  int v20; // r11d
  unsigned int v21; // edx
  unsigned __int16 *v22; // r8
  unsigned int v23; // r9d
  int v24; // r11d
  int v25; // eax
  unsigned int i; // r9d
  unsigned __int16 v27; // ax
  unsigned __int16 v28; // dx
  char v29; // dl
  unsigned int v30; // ebx
  DWORD LastError; // eax
  int v33; // [rsp+20h] [rbp-58h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+28h] [rbp-50h] BYREF
  __int64 v35; // [rsp+40h] [rbp-38h]
  int v36; // [rsp+48h] [rbp-30h]
  int *v37; // [rsp+50h] [rbp-28h]

  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006C180;
  Frame.Previous = 0;
  v35 = 544438355;
  v36 = 2146;
  v37 = &v33;
  v33 = 0;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( a2 != 38 )
  {
    FusionpDbgPrintEx(
      0xC0000000,
      "SXS.DLL: SxspParseGUID() caller passed in GUID that is %d characters long; GUIDs must be exactly 38 characters long.\n",
      a2);
    goto LABEL_83;
  }
  if ( *a1 != 123 )
  {
    FusionpDbgPrintEx(
      0xC0000000,
      "SXS.DLL: SxspParseGUID() caller pass in GUID that does not begin with a left brace ('{')\n");
    goto LABEL_83;
  }
  v6 = a1 + 1;
  v7 = 2;
  v8 = 0;
  v9 = 0;
  while ( 1 )
  {
    v10 = v6 + 1;
    if ( v9 >= 8 )
      break;
    v11 = *v6;
    if ( (unsigned __int16)(v11 - 48) > 9u && (unsigned __int16)(v11 - 97) > 5u && (unsigned __int16)(v11 - 65) > 5u )
    {
LABEL_58:
      FusionpDbgPrintEx(0xC0000000, "SXS.DLL: SxspParseGUID() given GUID where character %d is not hexidecimal\n", v7);
      goto LABEL_83;
    }
    ++v7;
    v12 = 16 * v8;
    ++v6;
    if ( v11 >= 0x61 )
    {
      if ( v11 > 0x66 )
      {
LABEL_10:
        if ( (unsigned __int16)(v11 - 48) > 9u )
          v13 = -1;
        else
          v13 = v11 - 48;
        v8 = v13 + v12;
        ++v9;
      }
      else
      {
        v8 = v11 - 87 + v12;
        ++v9;
      }
    }
    else
    {
      if ( (unsigned __int16)(v11 - 65) > 5u )
        goto LABEL_10;
      v8 = v11 - 55 + v12;
      ++v9;
    }
  }
  a3->Data1 = v8;
  if ( *v6 != 45 )
    goto LABEL_82;
  ++v7;
  v14 = 0;
  v15 = 0;
  while ( 1 )
  {
    v16 = v10 + 1;
    if ( v15 >= 4 )
      break;
    v17 = (unsigned __int16)*v10;
    if ( (unsigned __int16)(v17 - 48) > 9u && (unsigned __int16)(v17 - 97) > 5u && (unsigned __int16)(v17 - 65) > 5u )
      goto LABEL_58;
    ++v7;
    v18 = 16 * v14;
    ++v10;
    if ( v17 >= 0x61 )
    {
      if ( v17 > 0x66 )
      {
LABEL_19:
        if ( (unsigned __int16)(v17 - 48) > 9u )
          v19 = -1;
        else
          v19 = v17 - 48;
        v14 = v19 + v18;
        ++v15;
      }
      else
      {
        v14 = v17 - 87 + v18;
        ++v15;
      }
    }
    else
    {
      if ( (unsigned __int16)(v17 - 65) > 5u )
        goto LABEL_19;
      v14 = v17 - 55 + v18;
      ++v15;
    }
  }
  a3->Data2 = v14;
  if ( *v10 != 45 )
    goto LABEL_82;
  ++v7;
  v20 = 0;
  v21 = 0;
  while ( 1 )
  {
    v22 = v16 + 1;
    if ( v21 >= 4 )
      break;
    v23 = (unsigned __int16)*v16;
    if ( (unsigned __int16)(v23 - 48) > 9u && (unsigned __int16)(v23 - 97) > 5u && (unsigned __int16)(v23 - 65) > 5u )
      goto LABEL_58;
    ++v7;
    v24 = 16 * v20;
    ++v16;
    if ( v23 >= 0x61 )
    {
      if ( v23 > 0x66 )
      {
LABEL_28:
        if ( (unsigned __int16)(v23 - 48) > 9u )
          v25 = -1;
        else
          v25 = v23 - 48;
        v20 = v25 + v24;
        ++v21;
      }
      else
      {
        v20 = v23 - 87 + v24;
        ++v21;
      }
    }
    else
    {
      if ( (unsigned __int16)(v23 - 65) > 5u )
        goto LABEL_28;
      v20 = v23 - 55 + v24;
      ++v21;
    }
  }
  a3->Data3 = v20;
  if ( *v16 != 45 )
  {
LABEL_82:
    FusionpDbgPrintEx(0xC0000000, "SXS.DLL: SxspParseGUID() passed in GUID where character %d is not a dash.\n", v7);
    goto LABEL_83;
  }
  ++v7;
  for ( i = 0; ; ++i )
  {
    v27 = *v22;
    if ( i >= 8 )
      break;
    if ( (unsigned __int16)(v27 - 48) > 9u && (unsigned __int16)(v27 - 97) > 5u && (unsigned __int16)(v27 - 65) > 5u )
    {
      FusionpDbgPrintEx(
        0xC0000000,
        "SXS.DLL: SxspParseGUID() passed in GUID where character %d is not hexidecimal\n",
        v7);
      goto LABEL_83;
    }
    v28 = v22[1];
    if ( (unsigned __int16)(v28 - 48) > 9u && (unsigned __int16)(v28 - 97) > 5u && (unsigned __int16)(v28 - 65) > 5u )
    {
      FusionpDbgPrintEx(
        0xC0000000,
        "SXS.DLL: SxspParseGUID() passed in GUID where character %d is not hexidecimal\n",
        v7 + 1);
      goto LABEL_83;
    }
    v22 += 2;
    v7 += 2;
    if ( v27 >= 0x61u )
    {
      if ( v27 <= 0x66u )
      {
        LOBYTE(v27) = v27 - 87;
        goto LABEL_40;
      }
    }
    else if ( (unsigned __int16)(v27 - 65) <= 5u )
    {
      LOBYTE(v27) = v27 - 55;
      goto LABEL_40;
    }
    if ( (unsigned __int16)(v27 - 48) > 9u )
      LOBYTE(v27) = -1;
LABEL_40:
    if ( v28 >= 0x61u )
    {
      if ( v28 <= 0x66u )
      {
        v29 = v28 - 87;
        goto LABEL_44;
      }
    }
    else if ( (unsigned __int16)(v28 - 65) <= 5u )
    {
      v29 = v28 - 55;
      goto LABEL_44;
    }
    if ( (unsigned __int16)(v28 - 48) > 9u )
      v29 = -1;
    else
      v29 = v28 - 48;
LABEL_44:
    a3->Data4[i] = v29 | (16 * v27);
    if ( i == 1 )
    {
      if ( *v22 != 45 )
        goto LABEL_82;
      ++v22;
      ++v7;
    }
  }
  if ( v27 == 125 )
  {
    v33 = 1;
    goto LABEL_48;
  }
  FusionpDbgPrintEx(
    0xC0000000,
    "SXS.DLL: SxspParseGUID() passed in GUID which does not terminate with a closing brace ('}')\n");
LABEL_83:
  SetLastError(0x36B5u);
LABEL_48:
  v30 = v33;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v37 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v30;
}

```

## disassembly

```asm
0x180002540  mov     r11, rsp
0x180002543  mov     [r11+8], rbx
0x180002547  push    rbp
0x180002548  push    rsi
0x180002549  push    rdi
0x18000254a  sub     rsp, 60h
0x18000254e  mov     rax, cs:__security_cookie
0x180002555  xor     rax, rsp
0x180002558  mov     [rsp+78h+var_20], rax
0x18000255d  mov     [rsp+78h+Frame.Flags], 1
0x180002565  lea     rax, qword_18006C180
0x18000256c  mov     [r11-40h], rax
0x180002570  xor     ebp, ebp
0x180002572  lea     rax, [r11-58h]
0x180002576  mov     [r11-48h], rbp
0x18000257a  mov     rbx, rcx
0x18000257d  mov     qword ptr [r11-38h], 20737853h
0x180002585  mov     [rsp+78h+var_30], 862h
0x18000258d  lea     rcx, [r11-50h]; Frame
0x180002591  mov     [r11-28h], rax
0x180002595  mov     rsi, r8
0x180002598  mov     rdi, rdx
0x18000259b  mov     [rsp+78h+var_58], ebp
0x18000259f  call    cs:__imp_RtlPushFrame
0x1800025a6  nop     dword ptr [rax+rax+00h]
0x1800025ab  cmp     cs:g_FusionEnterExitTracingEnabled, bpl
0x1800025b2  jnz     loc_180002988
0x1800025b8  cmp     rdi, 26h ; '&'
0x1800025bc  jnz     loc_1800029C8
0x1800025c2  cmp     word ptr [rbx], 7Bh ; '{'
0x1800025c6  jnz     loc_1800029D4
0x1800025cc  add     rbx, 2
0x1800025d0  mov     r10d, 2
0x1800025d6  mov     r9d, ebp
0x1800025d9  mov     ecx, ebp
0x1800025db  lea     rdx, [rbx+2]
0x1800025df  cmp     ecx, 8
0x1800025e2  jnb     short loc_180002631
0x1800025e4  movzx   r8d, word ptr [rbx]
0x1800025e8  lea     eax, [r8-30h]
0x1800025ec  cmp     ax, 9
0x1800025f0  ja      loc_180002866
0x1800025f6  inc     r10
0x1800025f9  shl     r9d, 4
0x1800025fd  mov     rbx, rdx
0x180002600  cmp     r8d, 61h ; 'a'
0x180002604  jnb     loc_180002928
0x18000260a  lea     eax, [r8-41h]
0x18000260e  cmp     ax, 5
0x180002612  jbe     loc_1800028A0
0x180002618  lea     eax, [r8-30h]
0x18000261c  cmp     ax, 9
0x180002620  ja      loc_1800029E7
0x180002626  lea     eax, [r8-30h]
0x18000262a  add     r9d, eax
0x18000262d  inc     ecx
0x18000262f  jmp     short loc_1800025DB
0x180002631  mov     [rsi], r9d
0x180002634  cmp     word ptr [rbx], 2Dh ; '-'
0x180002638  jnz     loc_1800029F1
0x18000263e  inc     r10
0x180002641  mov     r11d, ebp
0x180002644  mov     r8d, ebp
0x180002647  lea     rcx, [rdx+2]
0x18000264b  cmp     r8d, 4
0x18000264f  jnb     short loc_18000269F
0x180002651  movzx   r9d, word ptr [rdx]
0x180002655  lea     eax, [r9-30h]
0x180002659  cmp     ax, 9
0x18000265d  ja      loc_1800028CB
0x180002663  inc     r10
0x180002666  shl     r11d, 4
0x18000266a  mov     rdx, rcx
0x18000266d  cmp     r9d, 61h ; 'a'
0x180002671  jnb     loc_18000296F
0x180002677  lea     eax, [r9-41h]
0x18000267b  cmp     ax, 5
0x18000267f  jbe     loc_1800028F6
0x180002685  lea     eax, [r9-30h]
0x180002689  cmp     ax, 9
0x18000268d  ja      loc_1800029FD
0x180002693  lea     eax, [r9-30h]
0x180002697  add     r11d, eax
0x18000269a  inc     r8d
0x18000269d  jmp     short loc_180002647
0x18000269f  mov     [rsi+4], r11w
0x1800026a4  cmp     word ptr [rdx], 2Dh ; '-'
0x1800026a8  jnz     loc_180002992
0x1800026ae  inc     r10
0x1800026b1  mov     r11d, ebp
0x1800026b4  mov     edx, ebp
0x1800026b6  lea     r8, [rcx+2]
0x1800026ba  cmp     edx, 4
0x1800026bd  jnb     short loc_18000270C
0x1800026bf  movzx   r9d, word ptr [rcx]
0x1800026c3  lea     eax, [r9-30h]
0x1800026c7  cmp     ax, 9
0x1800026cb  ja      loc_1800028AE
0x1800026d1  inc     r10
0x1800026d4  shl     r11d, 4
0x1800026d8  mov     rcx, r8
0x1800026db  cmp     r9d, 61h ; 'a'
0x1800026df  jnb     loc_180002957
0x1800026e5  lea     eax, [r9-41h]
0x1800026e9  cmp     ax, 5
0x1800026ed  jbe     loc_1800028E8
0x1800026f3  lea     eax, [r9-30h]
0x1800026f7  cmp     ax, 9
0x1800026fb  ja      loc_180002A07
0x180002701  lea     eax, [r9-30h]
0x180002705  add     r11d, eax
0x180002708  inc     edx
0x18000270a  jmp     short loc_1800026B6
0x18000270c  mov     [rsi+6], r11w
0x180002711  cmp     word ptr [rcx], 2Dh ; '-'
0x180002715  jnz     loc_1800029BC
0x18000271b  inc     r10
0x18000271e  mov     r9d, ebp
0x180002721  movzx   eax, word ptr [r8]
0x180002725  cmp     r9d, 8
0x180002729  jnb     loc_1800027BF
0x18000272f  lea     ecx, [rax-30h]
0x180002732  cmp     cx, 9
0x180002736  ja      loc_180002813
0x18000273c  movzx   edx, word ptr [r8+2]
0x180002741  lea     ecx, [rdx-30h]
0x180002744  cmp     cx, 9
0x180002748  ja      loc_18000283C
0x18000274e  add     r8, 4
0x180002752  add     r10, 2
0x180002756  cmp     ax, 61h ; 'a'
0x18000275a  jnb     loc_180002905
0x180002760  lea     ecx, [rax-41h]
0x180002763  cmp     cx, 5
0x180002767  jbe     loc_180002891
0x18000276d  lea     ecx, [rax-30h]
0x180002770  cmp     cx, 9
0x180002774  ja      loc_180002A11
0x18000277a  cmp     dx, 61h ; 'a'
0x18000277e  jnb     loc_180002916
0x180002784  lea     ecx, [rdx-41h]
0x180002787  cmp     cx, 5
0x18000278b  jbe     loc_180002898
0x180002791  lea     ecx, [rdx-30h]
0x180002794  cmp     cx, 9
0x180002798  ja      loc_180002A18
0x18000279e  sub     dl, 30h ; '0'
0x1800027a1  shl     al, 4
0x1800027a4  or      al, dl
0x1800027a6  mov     ecx, r9d
0x1800027a9  mov     [rcx+rsi+8], al
0x1800027ad  cmp     r9d, 1
0x1800027b1  jz      loc_180002940
0x1800027b7  inc     r9d
0x1800027ba  jmp     loc_180002721
0x1800027bf  cmp     ax, 7Dh ; '}'
0x1800027c3  jnz     loc_180002A1F
0x1800027c9  mov     [rsp+78h+var_58], 1
0x1800027d1  cmp     cs:g_FusionEnterExitTracingEnabled, bpl
0x1800027d8  mov     ebx, [rsp+78h+var_58]
0x1800027dc  jnz     loc_180002A35
0x1800027e2  lea     rcx, [rsp+78h+Frame]; Frame
0x1800027e7  call    cs:__imp_RtlPopFrame
0x1800027ee  nop     dword ptr [rax+rax+00h]
0x1800027f3  mov     eax, ebx
0x1800027f5  mov     rcx, [rsp+78h+var_20]
0x1800027fa  xor     rcx, rsp; StackCookie
0x1800027fd  call    __security_check_cookie
0x180002802  mov     rbx, [rsp+78h+arg_0]
0x18000280a  add     rsp, 60h
0x18000280e  pop     rdi
0x18000280f  pop     rsi
0x180002810  pop     rbp
0x180002811  retn
0x180002813  lea     ecx, [rax-61h]
0x180002816  cmp     cx, 5
0x18000281a  jbe     loc_18000273C
0x180002820  lea     ecx, [rax-41h]
0x180002823  cmp     cx, 5
0x180002827  jbe     loc_18000273C
0x18000282d  mov     r8, r10
0x180002830  lea     rdx, aSxsDllSxsppars; "SXS.DLL: SxspParseGUID() passed in GUID"...
0x180002837  jmp     loc_18000299C
0x18000283c  lea     ecx, [rdx-61h]
0x18000283f  cmp     cx, 5
0x180002843  jbe     loc_18000274E
0x180002849  lea     ecx, [rdx-41h]
0x18000284c  cmp     cx, 5
0x180002850  jbe     loc_18000274E
0x180002856  lea     r8, [r10+1]
0x18000285a  lea     rdx, aSxsDllSxsppars; "SXS.DLL: SxspParseGUID() passed in GUID"...
0x180002861  jmp     loc_18000299C
0x180002866  lea     eax, [r8-61h]
0x18000286a  cmp     ax, 5
0x18000286e  jbe     loc_1800025F6
0x180002874  lea     eax, [r8-41h]
0x180002878  cmp     ax, 5
0x18000287c  jbe     loc_1800025F6
0x180002882  mov     r8, r10
0x180002885  lea     rdx, aSxsDllSxsppars_3; "SXS.DLL: SxspParseGUID() given GUID whe"...
0x18000288c  jmp     loc_18000299C
0x180002891  sub     al, 37h ; '7'
0x180002893  jmp     loc_18000277A
0x180002898  sub     dl, 37h ; '7'
0x18000289b  jmp     loc_1800027A1
0x1800028a0  lea     eax, [r8-37h]
0x1800028a4  add     r9d, eax
0x1800028a7  inc     ecx
0x1800028a9  jmp     loc_1800025DB
0x1800028ae  lea     eax, [r9-61h]
0x1800028b2  cmp     ax, 5
0x1800028b6  jbe     loc_1800026D1
0x1800028bc  lea     eax, [r9-41h]
0x1800028c0  cmp     ax, 5
0x1800028c4  ja      short loc_180002882
0x1800028c6  jmp     loc_1800026D1
0x1800028cb  lea     eax, [r9-61h]
0x1800028cf  cmp     ax, 5
0x1800028d3  jbe     loc_180002663
0x1800028d9  lea     eax, [r9-41h]
0x1800028dd  cmp     ax, 5
0x1800028e1  ja      short loc_180002882
0x1800028e3  jmp     loc_180002663
0x1800028e8  lea     eax, [r9-37h]
0x1800028ec  add     r11d, eax
0x1800028ef  inc     edx
0x1800028f1  jmp     loc_1800026B6
0x1800028f6  lea     eax, [r9-37h]
0x1800028fa  add     r11d, eax
0x1800028fd  inc     r8d
0x180002900  jmp     loc_180002647
0x180002905  cmp     ax, 66h ; 'f'
0x180002909  ja      loc_18000276D
0x18000290f  sub     al, 57h ; 'W'
0x180002911  jmp     loc_18000277A
0x180002916  cmp     dx, 66h ; 'f'
0x18000291a  ja      loc_180002791
0x180002920  sub     dl, 57h ; 'W'
0x180002923  jmp     loc_1800027A1
0x180002928  cmp     r8d, 66h ; 'f'
0x18000292c  ja      loc_180002618
0x180002932  lea     eax, [r8-57h]
0x180002936  add     r9d, eax
0x180002939  inc     ecx
0x18000293b  jmp     loc_1800025DB
0x180002940  cmp     word ptr [r8], 2Dh ; '-'
0x180002945  jnz     loc_1800029F1
0x18000294b  add     r8, 2
0x18000294f  inc     r10
0x180002952  jmp     loc_1800027B7
0x180002957  cmp     r9d, 66h ; 'f'
0x18000295b  ja      loc_1800026F3
0x180002961  lea     eax, [r9-57h]
0x180002965  add     r11d, eax
0x180002968  inc     edx
0x18000296a  jmp     loc_1800026B6
0x18000296f  cmp     r9d, 66h ; 'f'
0x180002973  ja      loc_180002685
0x180002979  lea     eax, [r9-57h]
0x18000297d  add     r11d, eax
0x180002980  inc     r8d
0x180002983  jmp     loc_180002647
0x180002988  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18000298d  jmp     loc_1800025B8
0x180002992  mov     r8, r10
0x180002995  lea     rdx, aSxsDllSxsppars_2; "SXS.DLL: SxspParseGUID() passed in GUID"...
0x18000299c  mov     ecx, 0C0000000h; unsigned int
0x1800029a1  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x1800029a6  mov     ecx, 36B5h; dwErrCode
0x1800029ab  call    cs:__imp_SetLastError
0x1800029b2  nop     dword ptr [rax+rax+00h]
0x1800029b7  jmp     loc_1800027D1
0x1800029bc  mov     r8, r10
0x1800029bf  lea     rdx, aSxsDllSxsppars_2; "SXS.DLL: SxspParseGUID() passed in GUID"...
0x1800029c6  jmp     short loc_18000299C
0x1800029c8  mov     r8, rdi
0x1800029cb  lea     rdx, aSxsDllSxsppars_0; "SXS.DLL: SxspParseGUID() caller passed "...
0x1800029d2  jmp     short loc_18000299C
0x1800029d4  lea     rdx, aSxsDllSxsppars_4; "SXS.DLL: SxspParseGUID() caller pass in"...
0x1800029db  mov     ecx, 0C0000000h; unsigned int
0x1800029e0  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x1800029e5  jmp     short loc_1800029A6
0x1800029e7  mov     eax, 0FFFFFFFFh
0x1800029ec  jmp     loc_18000262A
0x1800029f1  mov     r8, r10
0x1800029f4  lea     rdx, aSxsDllSxsppars_2; "SXS.DLL: SxspParseGUID() passed in GUID"...
0x1800029fb  jmp     short loc_18000299C
0x1800029fd  mov     eax, 0FFFFFFFFh
0x180002a02  jmp     loc_180002697
0x180002a07  mov     eax, 0FFFFFFFFh
0x180002a0c  jmp     loc_180002705
0x180002a11  mov     al, 0FFh
0x180002a13  jmp     loc_18000277A
0x180002a18  mov     dl, 0FFh
0x180002a1a  jmp     loc_1800027A1
0x180002a1f  lea     rdx, aSxsDllSxsppars_1; "SXS.DLL: SxspParseGUID() passed in GUID"...
0x180002a26  mov     ecx, 0C0000000h; unsigned int
0x180002a2b  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180002a30  jmp     loc_1800029A6
0x180002a35  mov     rax, [rsp+78h+var_28]
  ... truncated ...
```
