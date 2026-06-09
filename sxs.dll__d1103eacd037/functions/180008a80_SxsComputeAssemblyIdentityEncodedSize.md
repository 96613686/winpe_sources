# SxsComputeAssemblyIdentityEncodedSize

- ea: `0x180008a80`
- end: `0x18000915b`
- name: `SxsComputeAssemblyIdentityEncodedSize`
- size: `1755`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800077b0`
- `0x180007b10`
- `0x180007e10`
- `0x180062568`

## callees

- `0x180008a80`
- `0x18000dffc`
- `0x18001c2c8`
- `0x18004dce0`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180008bbc`
- `ntdll!RtlPopFrame` at `0x180008ca9`
- `ntdll!RtlPopFrame` at `0x180008da4`
- `ntdll!RtlPopFrame` at `0x180008e78`
- `ntdll!RtlPopFrame` at `0x18000906d`
- `ntdll!RtlPopFrame` at `0x180009097`
- `ntdll!RtlPopFrame` at `0x180008bbc`
- `ntdll!RtlPopFrame` at `0x180008ca9`
- `ntdll!RtlPopFrame` at `0x180008da4`
- `ntdll!RtlPopFrame` at `0x180008e78`
- `ntdll!RtlPopFrame` at `0x18000906d`
- `ntdll!RtlPopFrame` at `0x180009097`
- `ntdll!RtlPushFrame` at `0x180008ae9`
- `ntdll!RtlPushFrame` at `0x180008b5f`
- `ntdll!RtlPushFrame` at `0x180008c59`
- `ntdll!RtlPushFrame` at `0x180008cf8`
- `ntdll!RtlPushFrame` at `0x180008ae9`
- `ntdll!RtlPushFrame` at `0x180008b5f`
- `ntdll!RtlPushFrame` at `0x180008c59`
- `ntdll!RtlPushFrame` at `0x180008cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000907e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000907e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009141`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008cb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fe8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000901a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009043`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008cb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fe8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000901a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009043`

## pseudocode

```c
__int64 __fastcall SxsComputeAssemblyIdentityEncodedSize(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  _QWORD *v5; // rsi
  const char *v7; // rcx
  const char *v8; // rcx
  int v9; // edi
  __int64 v10; // rcx
  unsigned int v11; // edi
  __int64 v12; // r14
  unsigned int v13; // r15d
  __int64 v14; // rbx
  BOOL v15; // r12d
  __int64 v16; // rdx
  char v17; // r13
  unsigned __int64 v18; // r11
  __int64 v19; // r10
  __int64 v20; // r9
  unsigned __int16 *v21; // r8
  __int64 v22; // r13
  __int64 v23; // rbx
  unsigned int v24; // ebx
  unsigned __int64 v26; // rdx
  __int64 v27; // r8
  unsigned __int16 *v28; // r9
  __int64 v29; // r13
  int v30; // ecx
  DWORD LastError; // eax
  DWORD v32; // eax
  DWORD v33; // eax
  unsigned int v34; // [rsp+28h] [rbp-61h]
  __int64 v35; // [rsp+38h] [rbp-51h]
  int v36; // [rsp+40h] [rbp-49h] BYREF
  int v37; // [rsp+44h] [rbp-45h] BYREF
  struct _TEB_ACTIVE_FRAME v38; // [rsp+48h] [rbp-41h] BYREF
  __int64 v39; // [rsp+60h] [rbp-29h]
  int v40; // [rsp+68h] [rbp-21h]
  int *v41; // [rsp+70h] [rbp-19h]
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+78h] [rbp-11h] BYREF
  __int64 v43; // [rsp+90h] [rbp+7h]
  int v44; // [rsp+98h] [rbp+Fh]
  int *v45; // [rsp+A0h] [rbp+17h]

  v5 = a5;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006C5A0;
  v45 = &v37;
  v37 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v43 = 544438355;
  v44 = 259;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( a5 )
    *a5 = 0;
  if ( !a2 )
  {
    v44 = 270;
LABEL_79:
    FusionpTraceParameterCheck(v7);
    SetLastError(0x57u);
    *v45 = 0;
    goto LABEL_48;
  }
  if ( !a5 )
  {
    v44 = 271;
    goto LABEL_79;
  }
  SetLastError(0);
  v36 = 0;
  v38.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CE60;
  v38.Flags = 1;
  v41 = &v36;
  v38.Previous = 0;
  v39 = 544438355;
  v40 = 73;
  RtlPushFrame(&v38);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( (unsigned int)(*(_DWORD *)(a2 + 8) - 1) > 2 )
  {
    v40 = 84;
    FusionpTraceParameterCheck(v8);
    SetLastError(0x57u);
    v9 = 0;
    *v41 = 0;
  }
  else
  {
    SetLastError(0);
    v9 = 1;
    *v41 = 1;
  }
  if ( !g_FusionEnterExitTracingEnabled )
  {
    RtlPopFrame(&v38);
    if ( v9 )
      goto LABEL_13;
LABEL_84:
    *v45 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007D2C0);
    goto LABEL_48;
  }
  if ( !v9 )
  {
    LastError = GetLastError();
    FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    RtlPopFrame(&v38);
    goto LABEL_84;
  }
  FusionpTraceCallSuccessfulExit(0);
  RtlPopFrame(&v38);
LABEL_13:
  v10 = *(_QWORD *)(a2 + 40);
  v11 = 0;
  v12 = 0;
  v13 = *(_DWORD *)(a2 + 16);
  v34 = v13;
  v35 = v10;
  while ( 1 )
  {
    if ( v11 >= v13 )
    {
      *v5 = v12;
      v37 = 1;
      goto LABEL_48;
    }
    v14 = *(_QWORD *)(v10 + 8LL * v11);
    if ( !v14 )
      break;
    SetLastError(0);
    v36 = 0;
    v41 = &v36;
    v38.Flags = 1;
    v38.Previous = 0;
    v38.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_1800716D0;
    v39 = 544438355;
    v40 = 2403;
    RtlPushFrame(&v38);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallEntry();
    v15 = 0;
    if ( !*(_QWORD *)(v14 + 8) && *(_QWORD *)(v14 + 16) == 4 )
      v15 = **(_QWORD **)(v14 + 40) == 0x65006D0061006ELL;
    SetLastError(0);
    *v41 = 1;
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallSuccessfulExit(0);
    RtlPopFrame(&v38);
    SetLastError(0);
    v36 = 0;
    v38.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071650;
    v38.Flags = 1;
    v41 = &v36;
    v38.Previous = 0;
    v39 = 544438355;
    v40 = 710;
    RtlPushFrame(&v38);
    v17 = g_FusionEnterExitTracingEnabled;
    if ( g_FusionEnterExitTracingEnabled )
    {
      FusionpTraceCallEntry();
      v17 = g_FusionEnterExitTracingEnabled;
    }
    v18 = 0;
    if ( v15 )
      goto LABEL_24;
    v26 = *(_QWORD *)(v14 + 8);
    if ( v26 )
      v18 = SxspComputeQuotedStringSize(*(const unsigned __int16 **)(v14 + 32), v26) + 2;
    v27 = *(_QWORD *)(v14 + 16);
    v16 = 0;
    v28 = *(unsigned __int16 **)(v14 + 40);
    if ( v27 )
    {
      v29 = 0x43FFFFFF01FFBLL;
      while ( 1 )
      {
        v30 = *v28++;
        if ( (unsigned __int16)(v30 - 45) <= 0x32u && _bittest64(&v29, (unsigned int)(v30 - 45))
          || (unsigned __int16)(v30 - 97) <= 0x19u )
        {
          v16 += 2;
        }
        else
        {
          if ( (_WORD)v30 != 38 )
          {
            if ( (_WORD)v30 == 34 || (_WORD)v30 == 39 )
              goto LABEL_85;
            if ( (_WORD)v30 == 60 || (_WORD)v30 == 62 )
            {
              v16 += 8;
              goto LABEL_57;
            }
            if ( (unsigned __int16)v30 >= 0x10u )
            {
              if ( (unsigned __int16)v30 >= 0x100u )
              {
                if ( (unsigned __int16)v30 >= 0x1000u )
                  v16 += 16;
                else
                  v16 += 14;
                goto LABEL_57;
              }
LABEL_85:
              v16 += 12;
              goto LABEL_57;
            }
          }
          v16 += 10;
        }
LABEL_57:
        if ( !--v27 )
        {
          v5 = a5;
          v13 = v34;
          v17 = g_FusionEnterExitTracingEnabled;
          break;
        }
      }
    }
    v18 += v16 + 2;
LABEL_24:
    v19 = *(_QWORD *)(v14 + 24);
    v20 = 0;
    v21 = *(unsigned __int16 **)(v14 + 48);
    if ( !v19 )
      goto LABEL_31;
    v22 = 0x43FFFFFF01FFBLL;
    do
    {
      v16 = *v21++;
      if ( (unsigned __int16)(v16 - 45) <= 0x32u && _bittest64(&v22, (unsigned int)(v16 - 45))
        || (unsigned __int16)(v16 - 97) <= 0x19u )
      {
        v20 += 2;
        goto LABEL_29;
      }
      switch ( (_WORD)v16 )
      {
        case '&':
LABEL_72:
          v20 += 10;
          break;
        case '"':
        case '\'':
LABEL_87:
          v20 += 12;
          break;
        case '<':
        case '>':
          v20 += 8;
          break;
        default:
          if ( (unsigned __int16)v16 < 0x10u )
            goto LABEL_72;
          if ( (unsigned __int16)v16 < 0x100u )
            goto LABEL_87;
          if ( (unsigned __int16)v16 >= 0x1000u )
            v20 += 16;
          else
            v20 += 14;
          break;
      }
LABEL_29:
      --v19;
    }
    while ( v19 );
    v5 = a5;
    v13 = v34;
    v17 = g_FusionEnterExitTracingEnabled;
LABEL_31:
    v36 = 1;
    v23 = v20 + v18 + 4;
    if ( v15 )
      v23 = v20 + v18;
    if ( v17 )
    {
      if ( *v41 )
      {
        FusionpTraceCallSuccessfulExit(0, v16, v21);
      }
      else
      {
        v32 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v32, 0);
      }
    }
    RtlPopFrame(&v38);
    if ( v11 )
      v12 += 2;
    v10 = v35;
    v12 += v23;
    ++v11;
  }
  SetLastError(0x54Fu);
  *v45 = 0;
LABEL_48:
  v24 = v37;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v45 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v33 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v33, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v24;
}

```

## disassembly

```asm
0x180008a80  mov     r11, rsp
0x180008a83  push    rbp
0x180008a84  push    rbx
0x180008a85  lea     rbp, [r11-57h]
0x180008a89  sub     rsp, 0C8h
0x180008a90  mov     rax, cs:__security_cookie
0x180008a97  xor     rax, rsp
0x180008a9a  mov     [rbp+4Fh+var_30], rax
0x180008a9e  mov     [r11+8], rsi
0x180008aa2  lea     rax, qword_18006C5A0
0x180008aa9  mov     rsi, [rbp+4Fh+arg_20]
0x180008aad  lea     rcx, [rbp+4Fh+Frame]; Frame
0x180008ab1  mov     [rbp+4Fh+Frame.Context], rax
0x180008ab5  mov     rbx, rdx
0x180008ab8  mov     [r11-18h], r13
0x180008abc  lea     rax, [rbp+4Fh+var_94]
0x180008ac0  xor     r13d, r13d
0x180008ac3  mov     [rbp+4Fh+var_38], rax
0x180008ac7  mov     [rbp+4Fh+var_A8], rsi
0x180008acb  mov     [rbp+4Fh+var_94], r13d
0x180008acf  mov     [rbp+4Fh+Frame.Flags], 1
0x180008ad6  mov     [rbp+4Fh+Frame.Previous], r13
0x180008ada  mov     [rbp+4Fh+var_48], 20737853h
0x180008ae2  mov     [rbp+4Fh+var_40], 103h
0x180008ae9  call    cs:__imp_RtlPushFrame
0x180008af0  nop     dword ptr [rax+rax+00h]
0x180008af5  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x180008afc  jnz     loc_180008FCF
0x180008b02  test    rsi, rsi
0x180008b05  jz      short loc_180008B0A
0x180008b07  mov     [rsi], r13
0x180008b0a  test    rbx, rbx
0x180008b0d  jz      loc_180009000
0x180008b13  test    rsi, rsi
0x180008b16  jz      loc_180009009
0x180008b1c  xor     ecx, ecx; dwErrCode
0x180008b1e  call    cs:__imp_SetLastError
0x180008b25  nop     dword ptr [rax+rax+00h]
0x180008b2a  lea     rax, qword_18006CE60
0x180008b31  mov     [rbp+4Fh+var_98], r13d
0x180008b35  mov     [rbp+4Fh+var_90.Context], rax
0x180008b39  lea     rcx, [rbp+4Fh+var_90]; Frame
0x180008b3d  lea     rax, [rbp+4Fh+var_98]
0x180008b41  mov     [rbp+4Fh+var_90.Flags], 1
0x180008b48  mov     [rbp+4Fh+var_68], rax
0x180008b4c  mov     [rbp+4Fh+var_90.Previous], r13
0x180008b50  mov     [rbp+4Fh+var_78], 20737853h
0x180008b58  mov     [rbp+4Fh+var_70], 49h ; 'I'
0x180008b5f  call    cs:__imp_RtlPushFrame
0x180008b66  nop     dword ptr [rax+rax+00h]
0x180008b6b  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x180008b72  jnz     loc_180008FD9
0x180008b78  mov     eax, [rbx+8]
0x180008b7b  dec     eax
0x180008b7d  mov     [rsp+0D0h+arg_10], rdi
0x180008b85  cmp     eax, 2
0x180008b88  ja      loc_180009032
0x180008b8e  xor     ecx, ecx; dwErrCode
0x180008b90  call    cs:__imp_SetLastError
0x180008b97  nop     dword ptr [rax+rax+00h]
0x180008b9c  mov     rax, [rbp+4Fh+var_68]
0x180008ba0  mov     edi, 1
0x180008ba5  mov     dword ptr [rax], 1
0x180008bab  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x180008bb2  jnz     loc_18000905E
0x180008bb8  lea     rcx, [rbp+4Fh+var_90]; Frame
0x180008bbc  call    cs:__imp_RtlPopFrame
0x180008bc3  nop     dword ptr [rax+rax+00h]
0x180008bc8  test    edi, edi
0x180008bca  jz      loc_1800090A3
0x180008bd0  mov     rcx, [rbx+28h]
0x180008bd4  mov     edi, r13d
0x180008bd7  mov     [rsp+0D0h+arg_18], r12
0x180008bdf  mov     [rsp+0D0h+var_18], r14
0x180008be7  mov     r14, r13
0x180008bea  mov     [rsp+0D0h+var_20], r15
0x180008bf2  mov     r15d, [rbx+10h]
0x180008bf6  mov     [rbp+4Fh+var_B0], r15d
0x180008bfa  mov     [rbp+4Fh+var_A0], rcx
0x180008bfe  lea     r12, qword_1800716D0
0x180008c05  cmp     edi, r15d
0x180008c08  jnb     loc_180008E2A
0x180008c0e  mov     eax, edi
0x180008c10  mov     rbx, [rcx+rax*8]
0x180008c14  test    rbx, rbx
0x180008c17  jz      loc_180008FE3
0x180008c1d  xor     ecx, ecx; dwErrCode
0x180008c1f  call    cs:__imp_SetLastError
0x180008c26  nop     dword ptr [rax+rax+00h]
0x180008c2b  lea     rax, [rbp+4Fh+var_98]
0x180008c2f  mov     [rbp+4Fh+var_98], r13d
0x180008c33  lea     rcx, [rbp+4Fh+var_90]; Frame
0x180008c37  mov     [rbp+4Fh+var_68], rax
0x180008c3b  mov     [rbp+4Fh+var_90.Flags], 1
0x180008c42  mov     [rbp+4Fh+var_90.Previous], r13
0x180008c46  mov     [rbp+4Fh+var_90.Context], r12
0x180008c4a  mov     [rbp+4Fh+var_78], 20737853h
0x180008c52  mov     [rbp+4Fh+var_70], 963h
0x180008c59  call    cs:__imp_RtlPushFrame
0x180008c60  nop     dword ptr [rax+rax+00h]
0x180008c65  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180008c6c  jnz     loc_180008FAA
0x180008c72  cmp     qword ptr [rbx+8], 0
0x180008c77  mov     r12d, r13d
0x180008c7a  jz      loc_180008F5F
0x180008c80  xor     ecx, ecx; dwErrCode
0x180008c82  call    cs:__imp_SetLastError
0x180008c89  nop     dword ptr [rax+rax+00h]
0x180008c8e  mov     rax, [rbp+4Fh+var_68]
0x180008c92  mov     dword ptr [rax], 1
0x180008c98  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180008c9f  jnz     loc_1800090BB
0x180008ca5  lea     rcx, [rbp+4Fh+var_90]; Frame
0x180008ca9  call    cs:__imp_RtlPopFrame
0x180008cb0  nop     dword ptr [rax+rax+00h]
0x180008cb5  xor     ecx, ecx; dwErrCode
0x180008cb7  call    cs:__imp_SetLastError
0x180008cbe  nop     dword ptr [rax+rax+00h]
0x180008cc3  lea     rax, qword_180071650
0x180008cca  mov     [rbp+4Fh+var_98], r13d
0x180008cce  mov     [rbp+4Fh+var_90.Context], rax
0x180008cd2  lea     rcx, [rbp+4Fh+var_90]; Frame
0x180008cd6  lea     rax, [rbp+4Fh+var_98]
0x180008cda  mov     [rbp+4Fh+var_90.Flags], 1
0x180008ce1  mov     [rbp+4Fh+var_68], rax
0x180008ce5  mov     [rbp+4Fh+var_90.Previous], r13
0x180008ce9  mov     [rbp+4Fh+var_78], 20737853h
0x180008cf1  mov     [rbp+4Fh+var_70], 2C6h
0x180008cf8  call    cs:__imp_RtlPushFrame
0x180008cff  nop     dword ptr [rax+rax+00h]
0x180008d04  movzx   r13d, cs:g_FusionEnterExitTracingEnabled
0x180008d0c  test    r13b, r13b
0x180008d0f  jnz     loc_180008FB4
0x180008d15  xor     r11d, r11d
0x180008d18  test    r12d, r12d
0x180008d1b  jz      loc_180008E9D
0x180008d21  mov     r10, [rbx+18h]
0x180008d25  xor     r9d, r9d
0x180008d28  mov     r8, [rbx+30h]
0x180008d2c  test    r10, r10
0x180008d2f  jz      short loc_180008D81
0x180008d31  mov     esi, 100h
0x180008d36  mov     r13, 43FFFFFF01FFBh
0x180008d40  mov     r15d, 1000h
0x180008d46  nop     word ptr [rax+rax+00000000h]
0x180008d50  movzx   edx, word ptr [r8]
0x180008d54  lea     r8, [r8+2]
0x180008d58  lea     eax, [rdx-2Dh]
0x180008d5b  cmp     ax, 32h ; '2'
0x180008d5f  ja      short loc_180008DC9
0x180008d61  bt      r13, rax
0x180008d65  jnb     short loc_180008DC9
0x180008d67  add     r9, 2
0x180008d6b  sub     r10, 1
0x180008d6f  jnz     short loc_180008D50
0x180008d71  mov     rsi, [rbp+4Fh+var_A8]
0x180008d75  mov     r15d, [rbp+4Fh+var_B0]
0x180008d79  movzx   r13d, cs:g_FusionEnterExitTracingEnabled
0x180008d81  lea     rax, [r9+r11]
0x180008d85  mov     [rbp+4Fh+var_98], 1
0x180008d8c  test    r12d, r12d
0x180008d8f  lea     rbx, [rax+4]
0x180008d93  cmovnz  rbx, rax
0x180008d97  test    r13b, r13b
0x180008d9a  jnz     loc_1800090FD
0x180008da0  lea     rcx, [rbp+4Fh+var_90]; Frame
0x180008da4  call    cs:__imp_RtlPopFrame
0x180008dab  nop     dword ptr [rax+rax+00h]
0x180008db0  test    edi, edi
0x180008db2  jz      short loc_180008DB8
0x180008db4  add     r14, 2
0x180008db8  mov     rcx, [rbp+4Fh+var_A0]
0x180008dbc  add     r14, rbx
0x180008dbf  inc     edi
0x180008dc1  xor     r13d, r13d
0x180008dc4  jmp     loc_180008BFE
0x180008dc9  lea     eax, [rdx-61h]
0x180008dcc  cmp     ax, 19h
0x180008dd0  jbe     short loc_180008D67
0x180008dd2  cmp     dx, 26h ; '&'
0x180008dd6  jz      loc_180008F8F
0x180008ddc  cmp     dx, 22h ; '"'
0x180008de0  jz      loc_1800090EB
0x180008de6  cmp     dx, 27h ; '''
0x180008dea  jz      loc_1800090EB
0x180008df0  cmp     dx, 3Ch ; '<'
0x180008df4  jz      loc_1800090F4
0x180008dfa  cmp     dx, 3Eh ; '>'
0x180008dfe  jz      loc_1800090F4
0x180008e04  cmp     dx, 10h
0x180008e08  jb      loc_180008F8F
0x180008e0e  cmp     dx, si
0x180008e11  jb      loc_1800090EB
0x180008e17  cmp     dx, r15w
0x180008e1b  jnb     loc_180008FA1
0x180008e21  add     r9, 0Eh
0x180008e25  jmp     loc_180008D6B
0x180008e2a  mov     [rsi], r14
0x180008e2d  mov     [rbp+4Fh+var_94], 1
0x180008e34  mov     r14, [rsp+0D0h+var_18]
0x180008e3c  mov     r12, [rsp+0D0h+arg_18]
0x180008e44  mov     r15, [rsp+0D0h+var_20]
0x180008e4c  mov     rdi, [rsp+0D0h+arg_10]
0x180008e54  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180008e5b  mov     ebx, [rbp+4Fh+var_94]
0x180008e5e  mov     r13, [rsp+0C0h]
0x180008e66  mov     rsi, [rsp+0D0h+arg_0]
0x180008e6e  jnz     loc_18000912C
0x180008e74  lea     rcx, [rbp+4Fh+Frame]; Frame
0x180008e78  call    cs:__imp_RtlPopFrame
0x180008e7f  nop     dword ptr [rax+rax+00h]
0x180008e84  mov     eax, ebx
0x180008e86  mov     rcx, [rbp+4Fh+var_30]
0x180008e8a  xor     rcx, rsp; StackCookie
0x180008e8d  call    __security_check_cookie
0x180008e92  add     rsp, 0C8h
0x180008e99  pop     rbx
0x180008e9a  pop     rbp
0x180008e9b  retn
0x180008e9d  mov     rdx, [rbx+8]; unsigned __int64
0x180008ea1  test    rdx, rdx
0x180008ea4  jnz     loc_1800090C7
0x180008eaa  mov     r8, [rbx+10h]
0x180008eae  xor     edx, edx
0x180008eb0  mov     r9, [rbx+28h]
0x180008eb4  test    r8, r8
0x180008eb7  jz      short loc_180008F01
0x180008eb9  mov     esi, 100h
0x180008ebe  mov     r13, 43FFFFFF01FFBh
0x180008ec8  mov     r15d, 1000h
0x180008ece  xchg    ax, ax
0x180008ed0  movzx   ecx, word ptr [r9]
0x180008ed4  lea     r9, [r9+2]
0x180008ed8  lea     eax, [rcx-2Dh]
0x180008edb  cmp     ax, 32h ; '2'
0x180008edf  ja      short loc_180008F0D
0x180008ee1  bt      r13, rax
0x180008ee5  jnb     short loc_180008F0D
0x180008ee7  add     rdx, 2
0x180008eeb  sub     r8, 1
0x180008eef  jnz     short loc_180008ED0
0x180008ef1  mov     rsi, [rbp+4Fh+var_A8]
0x180008ef5  mov     r15d, [rbp+4Fh+var_B0]
0x180008ef9  movzx   r13d, cs:g_FusionEnterExitTracingEnabled
0x180008f01  add     r11, 2
0x180008f05  add     r11, rdx
0x180008f08  jmp     loc_180008D21
0x180008f0d  lea     eax, [rcx-61h]
0x180008f10  cmp     ax, 19h
0x180008f14  jbe     short loc_180008EE7
0x180008f16  cmp     cx, 26h ; '&'
0x180008f1a  jz      short loc_180008F98
0x180008f1c  cmp     cx, 22h ; '"'
0x180008f20  jz      loc_1800090D9
0x180008f26  cmp     cx, 27h ; '''
0x180008f2a  jz      loc_1800090D9
0x180008f30  cmp     cx, 3Ch ; '<'
0x180008f34  jz      loc_1800090E2
0x180008f3a  cmp     cx, 3Eh ; '>'
0x180008f3e  jz      loc_1800090E2
0x180008f44  cmp     cx, 10h
0x180008f48  jb      short loc_180008F98
0x180008f4a  cmp     cx, si
0x180008f4d  jb      loc_1800090D9
0x180008f53  cmp     cx, r15w
0x180008f57  jnb     short loc_180008FC6
0x180008f59  add     rdx, 0Eh
0x180008f5d  jmp     short loc_180008EEB
0x180008f5f  cmp     qword ptr [rbx+10h], 4
0x180008f64  jnz     loc_180008C80
0x180008f6a  mov     rax, [rbx+28h]
0x180008f6e  mov     rcx, [rax]
0x180008f71  mov     rax, 65006D0061006Eh
0x180008f7b  cmp     rcx, rax
0x180008f7e  jnz     loc_180008C80
0x180008f84  mov     r12d, 1
0x180008f8a  jmp     loc_180008C80
0x180008f8f  add     r9, 0Ah
0x180008f93  jmp     loc_180008D6B
0x180008f98  add     rdx, 0Ah
0x180008f9c  jmp     loc_180008EEB
0x180008fa1  add     r9, 10h
0x180008fa5  jmp     loc_180008D6B
0x180008faa  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180008faf  jmp     loc_180008C72
0x180008fb4  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180008fb9  movzx   r13d, cs:g_FusionEnterExitTracingEnabled
0x180008fc1  jmp     loc_180008D15
0x180008fc6  add     rdx, 10h
0x180008fca  jmp     loc_180008EEB
0x180008fcf  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180008fd4  jmp     loc_180008B02
0x180008fd9  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180008fde  jmp     loc_180008B78
0x180008fe3  mov     ecx, 54Fh; dwErrCode
0x180008fe8  call    cs:__imp_SetLastError
0x180008fef  nop     dword ptr [rax+rax+00h]
0x180008ff4  mov     rax, [rbp+4Fh+var_38]
0x180008ff8  mov     [rax], r13d
0x180008ffb  jmp     loc_180008E34
  ... truncated ...
```
