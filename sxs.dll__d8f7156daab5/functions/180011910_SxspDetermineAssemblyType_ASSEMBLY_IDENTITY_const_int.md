# SxspDetermineAssemblyType(_ASSEMBLY_IDENTITY const *,int &)

- ea: `0x180011910`
- end: `0x180011dd5`
- name: `?SxspDetermineAssemblyType@@YAHPEBU_ASSEMBLY_IDENTITY@@AEAH@Z`
- size: `1221`
- prototype: `__int64 __fastcall(const struct _ASSEMBLY_IDENTITY *, int *)`
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f170`
- `0x18002a2b4`
- `0x18002b7e0`
- `0x1800419e4`
- `0x18005a884`
- `0x18005c88c`

## callees

- `0x18000df40`
- `0x180011910`
- `0x18001c2c8`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180011c08`
- `ntdll!RtlCompareUnicodeString` at `0x180011ce9`
- `ntdll!RtlCompareUnicodeString` at `0x180011c08`
- `ntdll!RtlCompareUnicodeString` at `0x180011ce9`
- `ntdll!RtlPopFrame` at `0x180011b77`
- `ntdll!RtlPopFrame` at `0x180011c3f`
- `ntdll!RtlPopFrame` at `0x180011c88`
- `ntdll!RtlPopFrame` at `0x180011b77`
- `ntdll!RtlPopFrame` at `0x180011c3f`
- `ntdll!RtlPopFrame` at `0x180011c88`
- `ntdll!RtlPushFrame` at `0x180011979`
- `ntdll!RtlPushFrame` at `0x1800119ed`
- `ntdll!RtlPushFrame` at `0x180011979`
- `ntdll!RtlPushFrame` at `0x1800119ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800119b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800119b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c4d`

## pseudocode

```c
__int64 __fastcall SxspDetermineAssemblyType(const struct _ASSEMBLY_IDENTITY *a1, int *a2)
{
  unsigned int v2; // ebx
  const char *v5; // rcx
  char v6; // r12
  __int64 v7; // r13
  unsigned int v8; // edx
  unsigned int v9; // r8d
  __int64 v10; // rax
  unsigned int v11; // ecx
  unsigned int v12; // r10d
  _QWORD *v13; // r15
  unsigned __int64 v14; // rdi
  const wchar_t *v15; // r9
  unsigned __int16 *v16; // r14
  __int64 v17; // rax
  wchar_t *v18; // r11
  int v19; // ecx
  int v20; // eax
  int v21; // ecx
  __int64 v22; // rdi
  _QWORD *v23; // r8
  unsigned __int64 v24; // r10
  const wchar_t *v25; // rdx
  unsigned __int16 *v26; // r9
  __int64 v27; // rax
  wchar_t *v28; // r11
  int v29; // eax
  int v30; // ecx
  WCHAR *v31; // r14
  unsigned __int64 v32; // rdi
  DWORD LastError; // eax
  DWORD v35; // eax
  UNICODE_STRING String2; // [rsp+28h] [rbp-69h] BYREF
  UNICODE_STRING String1; // [rsp+38h] [rbp-59h] BYREF
  int v38; // [rsp+48h] [rbp-49h] BYREF
  int v39; // [rsp+4Ch] [rbp-45h] BYREF
  struct _TEB_ACTIVE_FRAME v40; // [rsp+50h] [rbp-41h] BYREF
  __int64 v41; // [rsp+68h] [rbp-29h]
  int v42; // [rsp+70h] [rbp-21h]
  int *v43; // [rsp+78h] [rbp-19h]
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+80h] [rbp-11h] BYREF
  __int64 v45; // [rsp+98h] [rbp+7h]
  int v46; // [rsp+A0h] [rbp+Fh]
  int *v47; // [rsp+A8h] [rbp+17h]

  v2 = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D060;
  Frame.Flags = 1;
  v39 = 0;
  Frame.Previous = 0;
  v47 = &v39;
  v45 = 544438355;
  v46 = 2472;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  *a2 = 0;
  if ( !a1 )
  {
    v46 = 2478;
    FusionpTraceParameterCheck(v5);
    SetLastError(0x57u);
    v2 = 0;
    *v47 = 0;
    goto LABEL_41;
  }
  SetLastError(0);
  v38 = 0;
  v40.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CDC0;
  v40.Flags = 1;
  v43 = &v38;
  v40.Previous = 0;
  v41 = 544438355;
  v42 = 153;
  RtlPushFrame(&v40);
  v6 = g_FusionEnterExitTracingEnabled;
  if ( g_FusionEnterExitTracingEnabled )
  {
    FusionpTraceCallEntry();
    v6 = g_FusionEnterExitTracingEnabled;
  }
  v7 = *((_QWORD *)a1 + 5);
  v8 = 0;
  v9 = *((_DWORD *)a1 + 4);
  while ( v8 < v9 )
  {
    v10 = v8;
    v11 = (v9 + v8) >> 1;
    if ( v11 != v9 )
      v10 = v11;
    v12 = v10;
    v13 = *(_QWORD **)(v7 + 8 * v10);
    if ( !v13[1] )
    {
      v14 = v13[2];
      v15 = L"type";
      v16 = (unsigned __int16 *)v13[5];
      v17 = v14;
      if ( v14 >= 4 )
        v17 = 4;
      v18 = &aType[v17];
      while ( v15 < v18 )
      {
        v19 = *v15++;
        v20 = *v16++;
        v21 = v19 - v20;
        if ( v21 )
          goto LABEL_29;
      }
      if ( v14 > 4 )
      {
        v21 = 1;
      }
      else
      {
        if ( v14 == 4 )
        {
          if ( v13 )
          {
            if ( !v12 )
              goto LABEL_48;
            do
            {
              v22 = v12 - 1;
              v23 = *(_QWORD **)(v7 + 8 * v22);
              if ( v23[1] )
                break;
              v24 = v23[2];
              v25 = L"type";
              v26 = (unsigned __int16 *)v23[5];
              v27 = v24;
              if ( v24 >= 4 )
                v27 = 4;
              v28 = &aType[v27];
              while ( v25 < v28 )
              {
                v29 = *v26++;
                v30 = *v25++;
                if ( v30 != v29 )
                  goto LABEL_47;
              }
              if ( v24 != 4 )
                break;
              v12 = v22;
              v13 = *(_QWORD **)(v7 + 8 * v22);
            }
            while ( (_DWORD)v22 );
LABEL_47:
            if ( v13 )
            {
LABEL_48:
              v31 = (WCHAR *)v13[6];
              v32 = v13[3];
              goto LABEL_34;
            }
          }
          break;
        }
        v21 = -1;
      }
LABEL_29:
      if ( v21 >= 0 )
        goto LABEL_30;
      if ( v9 != v12 )
      {
        v9 = v12;
        continue;
      }
      break;
    }
LABEL_30:
    if ( v8 == v12 )
      break;
    v8 = v12;
  }
  v31 = 0;
  v32 = 0;
LABEL_34:
  v38 = 1;
  if ( v6 )
  {
    if ( *v43 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&v40);
  SetLastError(0);
  v38 = 0;
  v40.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D640;
  v40.Flags = 1;
  v43 = &v38;
  v40.Previous = 0;
  v41 = 544438355;
  v42 = 2438;
  CFrame::BaseEnter((CFrame *)&v40);
  *a2 = 0;
  if ( v32 != 6 )
  {
    if ( v32 <= 7 )
      goto LABEL_38;
    *(_QWORD *)&String2.Length = 917518;
    *(_QWORD *)&String1.Length = 917518;
    String2.Buffer = &v31[v32 - 7];
    String1.Buffer = L"-policy";
    if ( RtlCompareUnicodeString(&String2, &String1, 0) )
      goto LABEL_38;
    goto LABEL_37;
  }
  *(_QWORD *)&String1.Length = 786444;
  String2.Buffer = L"policy";
  *(_QWORD *)&String2.Length = 786444;
  String1.Buffer = v31;
  if ( !RtlCompareUnicodeString(&String1, &String2, 0) )
LABEL_37:
    *a2 = 1;
LABEL_38:
  SetLastError(0);
  *v43 = 1;
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallSuccessfulExit(0);
  RtlPopFrame(&v40);
  SetLastError(0);
  *v47 = 1;
LABEL_41:
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v2 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v35 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v35, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v2;
}

```

## disassembly

```asm
0x180011910  mov     r11, rsp
0x180011913  push    rbp
0x180011914  push    rbx
0x180011915  lea     rbp, [r11-5Fh]
0x180011919  sub     rsp, 0D8h
0x180011920  mov     rax, cs:__security_cookie
0x180011927  xor     rax, rsp
0x18001192a  mov     [rbp+57h+var_38], rax
0x18001192e  mov     [r11+18h], rsi
0x180011932  lea     rax, qword_18006D060
0x180011939  mov     [r11-18h], rdi
0x18001193d  mov     ebx, 1
0x180011942  mov     [r11-30h], r14
0x180011946  mov     rdi, rcx
0x180011949  mov     [rbp+57h+Frame.Context], rax
0x18001194d  lea     rcx, [rbp+57h+Frame]; Frame
0x180011951  xor     r14d, r14d
0x180011954  mov     [rbp+57h+Frame.Flags], ebx
0x180011957  lea     rax, [rbp+57h+var_9C]
0x18001195b  mov     [rbp+57h+var_9C], r14d
0x18001195f  mov     [rbp+57h+Frame.Previous], r14
0x180011963  mov     rsi, rdx
0x180011966  mov     [rbp+57h+var_40], rax
0x18001196a  mov     [rbp+57h+var_50], 20737853h
0x180011972  mov     [rbp+57h+var_48], 9A8h
0x180011979  call    cs:__imp_RtlPushFrame
0x180011980  nop     dword ptr [rax+rax+00h]
0x180011985  cmp     cs:g_FusionEnterExitTracingEnabled, r14b
0x18001198c  jnz     loc_180011D28
0x180011992  mov     [rsi], r14d
0x180011995  test    rdi, rdi
0x180011998  jz      loc_180011B1E
0x18001199e  mov     [rsp+0E0h+var_18], r12
0x1800119a6  xor     ecx, ecx; dwErrCode
0x1800119a8  mov     [rsp+0E0h+var_20], r13
0x1800119b0  call    cs:__imp_SetLastError
0x1800119b7  nop     dword ptr [rax+rax+00h]
0x1800119bc  lea     rax, qword_18006CDC0
0x1800119c3  mov     [rbp+57h+var_A0], r14d
0x1800119c7  mov     [rbp+57h+var_98.Context], rax
0x1800119cb  lea     rcx, [rbp+57h+var_98]; Frame
0x1800119cf  lea     rax, [rbp+57h+var_A0]
0x1800119d3  mov     [rbp+57h+var_98.Flags], ebx
0x1800119d6  mov     [rbp+57h+var_70], rax
0x1800119da  mov     [rbp+57h+var_98.Previous], r14
0x1800119de  mov     [rbp+57h+var_80], 20737853h
0x1800119e6  mov     [rbp+57h+var_78], 99h
0x1800119ed  call    cs:__imp_RtlPushFrame
0x1800119f4  nop     dword ptr [rax+rax+00h]
0x1800119f9  movzx   r12d, cs:g_FusionEnterExitTracingEnabled
0x180011a01  test    r12b, r12b
0x180011a04  jnz     loc_180011D32
0x180011a0a  mov     r13, [rdi+28h]
0x180011a0e  mov     edx, r14d
0x180011a11  mov     r8d, [rdi+10h]
0x180011a15  mov     [rsp+0E0h+var_30], r15
0x180011a1d  mov     r11d, 4
0x180011a23  cmp     edx, r8d
0x180011a26  jnb     loc_180011B4A
0x180011a2c  mov     eax, edx
0x180011a2e  lea     ecx, [r8+rdx]
0x180011a32  shr     ecx, 1
0x180011a34  cmp     ecx, r8d
0x180011a37  cmovnz  eax, ecx
0x180011a3a  mov     r10d, eax
0x180011a3d  mov     r15, [r13+rax*8+0]
0x180011a42  cmp     qword ptr [r15+8], 0
0x180011a47  ja      loc_180011B11
0x180011a4d  mov     rdi, [r15+10h]
0x180011a51  mov     r9, cs:off_18006D130; "type"
0x180011a58  cmp     rdi, 4
0x180011a5c  mov     r14, [r15+28h]
0x180011a60  mov     rax, rdi
0x180011a63  cmovnb  rax, r11
0x180011a67  lea     r11, [r9+rax*2]
0x180011a6b  cmp     r9, r11
0x180011a6e  jnb     short loc_180011A86
0x180011a70  movzx   ecx, word ptr [r9]
0x180011a74  add     r9, 2
0x180011a78  movzx   eax, word ptr [r14]
0x180011a7c  add     r14, 2
0x180011a80  sub     ecx, eax
0x180011a82  jz      short loc_180011A6B
0x180011a84  jmp     short loc_180011B01
0x180011a86  cmp     rdi, 4
0x180011a8a  ja      loc_180011D55
0x180011a90  jnz     short loc_180011AFC
0x180011a92  test    r15, r15
0x180011a95  jz      loc_180011B4A
0x180011a9b  test    r10d, r10d
0x180011a9e  jz      loc_180011D1B
0x180011aa4  mov     r14d, 4
0x180011aaa  lea     edi, [r10-1]
0x180011aae  mov     r8, [r13+rdi*8+0]
0x180011ab3  cmp     qword ptr [r8+8], 0
0x180011ab8  ja      loc_180011D12
0x180011abe  mov     r10, [r8+10h]
0x180011ac2  mov     rdx, cs:off_18006D130; "type"
0x180011ac9  cmp     r10, r14
0x180011acc  mov     r9, [r8+28h]
0x180011ad0  mov     rax, r10
0x180011ad3  cmovnb  rax, r14
0x180011ad7  lea     r11, [rdx+rax*2]
0x180011adb  cmp     rdx, r11
0x180011ade  jnb     loc_180011D02
0x180011ae4  movzx   eax, word ptr [r9]
0x180011ae8  add     r9, 2
0x180011aec  movzx   ecx, word ptr [rdx]
0x180011aef  add     rdx, 2
0x180011af3  sub     ecx, eax
0x180011af5  jz      short loc_180011ADB
0x180011af7  jmp     loc_180011D0E
0x180011afc  mov     ecx, 0FFFFFFFFh
0x180011b01  test    ecx, ecx
0x180011b03  js      loc_180011D44
0x180011b09  jz      short loc_180011A92
0x180011b0b  mov     r11d, 4
0x180011b11  cmp     edx, r10d
0x180011b14  jz      short loc_180011B4A
0x180011b16  mov     edx, r10d
0x180011b19  jmp     loc_180011A23
0x180011b1e  mov     [rbp+57h+var_48], 9AEh
0x180011b25  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180011b2a  mov     ecx, 57h ; 'W'; dwErrCode
0x180011b2f  call    cs:__imp_SetLastError
0x180011b36  nop     dword ptr [rax+rax+00h]
0x180011b3b  mov     rax, [rbp+57h+var_40]
0x180011b3f  mov     ebx, r14d
0x180011b42  mov     [rax], r14d
0x180011b45  jmp     loc_180011C5F
0x180011b4a  xor     r14d, r14d
0x180011b4d  xor     edi, edi
0x180011b4f  mov     r15, [rsp+0E0h+var_30]
0x180011b57  mov     r13, [rsp+0E0h+var_20]
0x180011b5f  mov     [rbp+57h+var_A0], ebx
0x180011b62  test    r12b, r12b
0x180011b65  mov     r12, [rsp+0E0h+var_18]
0x180011b6d  jnz     loc_180011D70
0x180011b73  lea     rcx, [rbp+57h+var_98]; Frame
0x180011b77  call    cs:__imp_RtlPopFrame
0x180011b7e  nop     dword ptr [rax+rax+00h]
0x180011b83  xor     ecx, ecx; dwErrCode
0x180011b85  call    cs:__imp_SetLastError
0x180011b8c  nop     dword ptr [rax+rax+00h]
0x180011b91  lea     rax, qword_18006D640
0x180011b98  mov     [rbp+57h+var_A0], 0
0x180011b9f  mov     [rbp+57h+var_98.Context], rax
0x180011ba3  lea     rcx, [rbp+57h+var_98]; this
0x180011ba7  lea     rax, [rbp+57h+var_A0]
0x180011bab  mov     [rbp+57h+var_98.Flags], ebx
0x180011bae  mov     [rbp+57h+var_70], rax
0x180011bb2  mov     [rbp+57h+var_98.Previous], 0
0x180011bba  mov     [rbp+57h+var_80], 20737853h
0x180011bc2  mov     [rbp+57h+var_78], 986h
0x180011bc9  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180011bce  mov     dword ptr [rsi], 0
0x180011bd4  cmp     rdi, 6
0x180011bd8  jnz     loc_180011CAD
0x180011bde  lea     rax, aPolicy_1; "policy"
0x180011be5  mov     qword ptr [rbp+57h+String1.Length], 0C000Ch
0x180011bed  xor     r8d, r8d; CaseInsensitive
0x180011bf0  mov     [rbp+57h+String2.Buffer], rax
0x180011bf4  lea     rdx, [rbp+57h+String2]; String2
0x180011bf8  mov     qword ptr [rbp+57h+String2.Length], 0C000Ch
0x180011c00  lea     rcx, [rbp+57h+String1]; String1
0x180011c04  mov     [rbp+57h+String1.Buffer], r14
0x180011c08  call    cs:__imp_RtlCompareUnicodeString
0x180011c0f  nop     dword ptr [rax+rax+00h]
0x180011c14  test    eax, eax
0x180011c16  jnz     short loc_180011C1A
0x180011c18  mov     [rsi], ebx
0x180011c1a  xor     ecx, ecx; dwErrCode
0x180011c1c  call    cs:__imp_SetLastError
0x180011c23  nop     dword ptr [rax+rax+00h]
0x180011c28  mov     rax, [rbp+57h+var_70]
0x180011c2c  mov     [rax], ebx
0x180011c2e  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180011c35  jnz     loc_180011D9F
0x180011c3b  lea     rcx, [rbp+57h+var_98]; Frame
0x180011c3f  call    cs:__imp_RtlPopFrame
0x180011c46  nop     dword ptr [rax+rax+00h]
0x180011c4b  xor     ecx, ecx; dwErrCode
0x180011c4d  call    cs:__imp_SetLastError
0x180011c54  nop     dword ptr [rax+rax+00h]
0x180011c59  mov     rax, [rbp+57h+var_40]
0x180011c5d  mov     [rax], ebx
0x180011c5f  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180011c66  mov     r14, [rsp+0E0h+var_28]
0x180011c6e  mov     rdi, [rsp+0D0h]
0x180011c76  mov     rsi, [rsp+0E0h+arg_10]
0x180011c7e  jnz     loc_180011DAB
0x180011c84  lea     rcx, [rbp+57h+Frame]; Frame
0x180011c88  call    cs:__imp_RtlPopFrame
0x180011c8f  nop     dword ptr [rax+rax+00h]
0x180011c94  mov     eax, ebx
0x180011c96  mov     rcx, [rbp+57h+var_38]
0x180011c9a  xor     rcx, rsp; StackCookie
0x180011c9d  call    __security_check_cookie
0x180011ca2  add     rsp, 0D8h
0x180011ca9  pop     rbx
0x180011caa  pop     rbp
0x180011cab  retn
0x180011cad  cmp     rdi, 7
0x180011cb1  jbe     loc_180011C1A
0x180011cb7  lea     rax, [rdi-7]
0x180011cbb  mov     qword ptr [rbp+57h+String2.Length], 0E000Eh
0x180011cc3  lea     rax, [r14+rax*2]
0x180011cc7  mov     qword ptr [rbp+57h+String1.Length], 0E000Eh
0x180011ccf  mov     [rbp+57h+String2.Buffer], rax
0x180011cd3  lea     rdx, [rbp+57h+String1]; String2
0x180011cd7  lea     rax, aPolicy_0; "-policy"
0x180011cde  xor     r8d, r8d; CaseInsensitive
0x180011ce1  lea     rcx, [rbp+57h+String2]; String1
0x180011ce5  mov     [rbp+57h+String1.Buffer], rax
0x180011ce9  call    cs:__imp_RtlCompareUnicodeString
0x180011cf0  nop     dword ptr [rax+rax+00h]
0x180011cf5  test    eax, eax
0x180011cf7  jz      loc_180011C18
0x180011cfd  jmp     loc_180011C1A
0x180011d02  cmp     r10, r14
0x180011d05  jz      short loc_180011D60
0x180011d07  ja      short loc_180011D5C
0x180011d09  mov     ecx, 0FFFFFFFFh
0x180011d0e  test    ecx, ecx
0x180011d10  jz      short loc_180011D60
0x180011d12  test    r15, r15
0x180011d15  jz      loc_180011B4A
0x180011d1b  mov     r14, [r15+30h]
0x180011d1f  mov     rdi, [r15+18h]
0x180011d23  jmp     loc_180011B4F
0x180011d28  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180011d2d  jmp     loc_180011992
0x180011d32  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180011d37  movzx   r12d, cs:g_FusionEnterExitTracingEnabled
0x180011d3f  jmp     loc_180011A0A
0x180011d44  cmp     r8d, r10d
0x180011d47  jz      loc_180011B4A
0x180011d4d  mov     r8d, r10d
0x180011d50  jmp     loc_180011A1D
0x180011d55  mov     ecx, ebx
0x180011d57  jmp     loc_180011B01
0x180011d5c  mov     ecx, ebx
0x180011d5e  jmp     short loc_180011D0E
0x180011d60  mov     r10d, edi
0x180011d63  mov     r15, r8
0x180011d66  test    edi, edi
0x180011d68  jnz     loc_180011AAA
0x180011d6e  jmp     short loc_180011D12
0x180011d70  mov     rax, [rbp+57h+var_70]
0x180011d74  cmp     dword ptr [rax], 0
0x180011d77  jz      short loc_180011D85
0x180011d79  xor     ecx, ecx; char *
0x180011d7b  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180011d80  jmp     loc_180011B73
0x180011d85  call    cs:__imp_GetLastError
0x180011d8c  nop     dword ptr [rax+rax+00h]
0x180011d91  mov     ecx, eax; unsigned int
0x180011d93  xor     edx, edx; Format
0x180011d95  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180011d9a  jmp     loc_180011B73
0x180011d9f  xor     ecx, ecx; char *
0x180011da1  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180011da6  jmp     loc_180011C3B
0x180011dab  test    ebx, ebx
0x180011dad  jz      short loc_180011DBB
0x180011daf  xor     ecx, ecx; char *
0x180011db1  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180011db6  jmp     loc_180011C84
0x180011dbb  call    cs:__imp_GetLastError
0x180011dc2  nop     dword ptr [rax+rax+00h]
0x180011dc7  mov     ecx, eax; unsigned int
0x180011dc9  xor     edx, edx; Format
0x180011dcb  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180011dd0  jmp     loc_180011C84
```
