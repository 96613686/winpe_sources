# SxspValidateBoolAttribute(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &)

- ea: `0x18004ed50`
- end: `0x18004f0ef`
- name: `?SxspValidateBoolAttribute@@YAHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEA_N_KPEAXAEA_K@Z`
- size: `927`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18004ed50`
- `0x18004f0f8`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18004ee9a`
- `ntdll!RtlCompareUnicodeString` at `0x18004ee9a`
- `ntdll!RtlPopFrame` at `0x18004ef04`
- `ntdll!RtlPopFrame` at `0x18004ef04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f0d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f0d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ee09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ee52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004eeb3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ef3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ef87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004efd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f023`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f07e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ee09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ee52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004eeb3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ef3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ef87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004efd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f023`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f07e`

## pseudocode

```c
__int64 __fastcall SxspValidateBoolAttribute(int a1, __int64 a2, _BYTE *a3, unsigned __int64 a4, bool *a5, _QWORD *a6)
{
  const char *v10; // rcx
  int v11; // ebx
  __int64 v12; // rax
  WCHAR *v13; // rax
  UNICODE_STRING *p_String1; // rdx
  UNICODE_STRING *p_String2; // rcx
  LONG v16; // eax
  bool v17; // al
  bool v18; // cl
  unsigned int v19; // ebx
  WCHAR *v21; // rax
  char **v22; // rcx
  DWORD LastError; // eax
  UNICODE_STRING String1; // [rsp+30h] [rbp-79h] BYREF
  UNICODE_STRING String2; // [rsp+40h] [rbp-69h] BYREF
  int v26; // [rsp+50h] [rbp-59h] BYREF
  int v27; // [rsp+54h] [rbp-55h] BYREF
  int v28; // [rsp+58h] [rbp-51h] BYREF
  __int64 v29; // [rsp+60h] [rbp-49h]
  __int64 *v30; // [rsp+68h] [rbp-41h]
  __int64 v31; // [rsp+70h] [rbp-39h]
  int v32; // [rsp+78h] [rbp-31h]
  int *v33; // [rsp+80h] [rbp-29h]
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+88h] [rbp-21h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-9h]
  int v36; // [rsp+A8h] [rbp-1h]
  int *v37; // [rsp+B0h] [rbp+7h]

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071FC0;
  Frame.Flags = 1;
  v37 = &v27;
  v27 = 0;
  Frame.Previous = 0;
  v35 = 544438355;
  v36 = 3150;
  CFrame::BaseEnter((CFrame *)&Frame);
  v26 = 0;
  *a3 = 0;
  if ( a1 )
  {
    v36 = 3158;
LABEL_26:
    FusionpTraceParameterCheck(v10);
    SetLastError(0x57u);
    *v37 = 0;
    goto LABEL_15;
  }
  v11 = 2;
  if ( a4 >= 2 )
  {
    v36 = 3159;
    goto LABEL_26;
  }
  v12 = *(_QWORD *)(a2 + 32);
  switch ( v12 )
  {
    case 2LL:
      SetLastError(0);
      if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Compare(a2, L"no", 2, &v26) )
      {
        v17 = 0;
        v18 = v26 == 1;
        goto LABEL_10;
      }
      v22 = off_180075330;
      break;
    case 3LL:
      SetLastError(0);
      v26 = 0;
      v30 = &`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Compare'::`2'::__stc;
      v29 = 0;
      v33 = &v26;
      v28 = 1;
      v31 = 544438355;
      v32 = 644;
      CFrame::BaseEnter((CFrame *)&v28);
      SetLastError(0);
      v21 = *(WCHAR **)(a2 + 16);
      p_String1 = &String1;
      *(_QWORD *)&String1.Length = 393222;
      *(_QWORD *)&String2.Length = 0;
      String2.Buffer = v21;
      p_String2 = &String2;
      LOWORD(v21) = *(_WORD *)(a2 + 32);
      *(_QWORD *)&String2.Length = (unsigned __int16)(2 * (_WORD)v21);
      String2.MaximumLength = 2 * (_WORD)v21;
      String1.Buffer = L"yes";
      goto LABEL_7;
    case 4LL:
      SetLastError(0);
      v26 = 0;
      v30 = &`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Compare'::`2'::__stc;
      v28 = 1;
      v33 = &v26;
      v29 = 0;
      v31 = 544438355;
      v32 = 644;
      CFrame::BaseEnter((CFrame *)&v28);
      SetLastError(0);
      v13 = *(WCHAR **)(a2 + 16);
      p_String1 = &String2;
      *(_QWORD *)&String2.Length = 524296;
      *(_QWORD *)&String1.Length = 0;
      String1.Buffer = v13;
      p_String2 = &String1;
      LOWORD(v13) = *(_WORD *)(a2 + 32);
      *(_QWORD *)&String1.Length = (unsigned __int16)(2 * (_WORD)v13);
      String1.MaximumLength = 2 * (_WORD)v13;
      String2.Buffer = L"true";
LABEL_7:
      v16 = RtlCompareUnicodeString(p_String2, p_String1, 1u);
      if ( v16 )
      {
        if ( v16 < 0 )
          v11 = 0;
      }
      else
      {
        v11 = 1;
      }
      SetLastError(0);
      *v33 = 1;
      CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v28);
      v17 = v11 == 1;
      v18 = v11 == 1;
LABEL_10:
      if ( v18 )
      {
LABEL_11:
        if ( a5 )
          *a5 = v17;
        *a6 = 1;
        *a3 = 1;
        goto LABEL_14;
      }
      goto LABEL_14;
    case 5LL:
      SetLastError(0);
      if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Compare(a2, L"false", 5, &v26) )
      {
        if ( v26 == 1 )
        {
          v17 = 0;
          goto LABEL_11;
        }
LABEL_14:
        v27 = 1;
        goto LABEL_15;
      }
      v22 = off_180075310;
      break;
    default:
      goto LABEL_14;
  }
  *v37 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v22);
LABEL_15:
  v19 = v27;
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
  return v19;
}

```

## disassembly

```asm
0x18004ed50  mov     [rsp-8+arg_0], rbx
0x18004ed55  push    rbp
0x18004ed56  push    rsi
0x18004ed57  push    rdi
0x18004ed58  push    r12
0x18004ed5a  push    r13
0x18004ed5c  push    r14
0x18004ed5e  push    r15
0x18004ed60  lea     rbp, [rsp-17h]
0x18004ed65  sub     rsp, 0C0h
0x18004ed6c  mov     rax, cs:__security_cookie
0x18004ed73  xor     rax, rsp
0x18004ed76  mov     [rbp+47h+var_38], rax
0x18004ed7a  mov     rsi, [rbp+47h+arg_20]
0x18004ed7e  lea     rax, qword_180071FC0
0x18004ed85  mov     r12, [rbp+47h+arg_28]
0x18004ed89  mov     ebx, ecx
0x18004ed8b  mov     [rbp+47h+Frame.Context], rax
0x18004ed8f  lea     rcx, [rbp+47h+Frame]; this
0x18004ed93  lea     rax, [rbp+47h+var_9C]
0x18004ed97  mov     [rbp+47h+Frame.Flags], 1
0x18004ed9e  xor     r13d, r13d
0x18004eda1  mov     [rbp+47h+var_40], rax
0x18004eda5  mov     r14, r9
0x18004eda8  mov     [rbp+47h+var_9C], r13d
0x18004edac  mov     r15, r8
0x18004edaf  mov     [rbp+47h+Frame.Previous], r13
0x18004edb3  mov     rdi, rdx
0x18004edb6  mov     [rbp+47h+var_50], 20737853h
0x18004edbe  mov     [rbp+47h+var_48], 0C4Eh
0x18004edc5  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18004edca  mov     [rbp+47h+var_A0], r13d
0x18004edce  mov     [r15], r13b
0x18004edd1  test    ebx, ebx
0x18004edd3  jnz     loc_18004F064
0x18004edd9  lea     ebx, [r13+2]
0x18004eddd  cmp     r14, rbx
0x18004ede0  jnb     loc_18004F06D
0x18004ede6  mov     rax, [rdi+20h]
0x18004edea  cmp     rax, rbx
0x18004eded  jz      loc_18004EFD1
0x18004edf3  cmp     rax, 3
0x18004edf7  jz      loc_18004EF3A
0x18004edfd  cmp     rax, 4
0x18004ee01  jnz     loc_18004F017
0x18004ee07  xor     ecx, ecx; dwErrCode
0x18004ee09  call    cs:__imp_SetLastError
0x18004ee10  nop     dword ptr [rax+rax+00h]
0x18004ee15  lea     rax, ?__stc@?1??Win32Compare@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEBG_KAEAW4StringComparisonResult@@_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Compare(ushort const *,unsigned __int64,StringComparisonResult &,bool)'::`2'::__stc
0x18004ee1c  mov     [rbp+47h+var_A0], r13d
0x18004ee20  mov     [rbp+47h+var_88], rax
0x18004ee24  lea     r14d, [r13+1]
0x18004ee28  lea     rax, [rbp+47h+var_A0]
0x18004ee2c  mov     [rbp+47h+var_98], r14d
0x18004ee30  lea     rcx, [rbp+47h+var_98]; this
0x18004ee34  mov     [rbp+47h+var_70], rax
0x18004ee38  mov     [rbp+47h+var_90], r13
0x18004ee3c  mov     [rbp+47h+var_80], 20737853h
0x18004ee44  mov     [rbp+47h+var_78], 284h
0x18004ee4b  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18004ee50  xor     ecx, ecx; dwErrCode
0x18004ee52  call    cs:__imp_SetLastError
0x18004ee59  nop     dword ptr [rax+rax+00h]
0x18004ee5e  mov     rax, [rdi+10h]
0x18004ee62  lea     rdx, [rbp+47h+String2]; String2
0x18004ee66  xorps   xmm0, xmm0
0x18004ee69  mov     qword ptr [rbp+47h+String2.Length], 80008h
0x18004ee71  movups  xmmword ptr [rbp+47h+String1.Length], xmm0
0x18004ee75  mov     [rbp+47h+String1.Buffer], rax
0x18004ee79  lea     rcx, [rbp+47h+String1]; String1
0x18004ee7d  movzx   eax, word ptr [rdi+20h]
0x18004ee81  add     ax, ax
0x18004ee84  mov     [rbp+47h+String1.Length], ax
0x18004ee88  mov     [rbp+47h+String1.MaximumLength], ax
0x18004ee8c  lea     rax, aTrue; "true"
0x18004ee93  mov     [rbp+47h+String2.Buffer], rax
0x18004ee97  mov     r8b, r14b; CaseInsensitive
0x18004ee9a  call    cs:__imp_RtlCompareUnicodeString
0x18004eea1  nop     dword ptr [rax+rax+00h]
0x18004eea6  test    eax, eax
0x18004eea8  jnz     loc_18004F0B7
0x18004eeae  mov     ebx, r14d
0x18004eeb1  xor     ecx, ecx; dwErrCode
0x18004eeb3  call    cs:__imp_SetLastError
0x18004eeba  nop     dword ptr [rax+rax+00h]
0x18004eebf  mov     rax, [rbp+47h+var_70]
0x18004eec3  mov     [rax], r14d
0x18004eec6  lea     rcx, [rbp+47h+var_98]; this
0x18004eeca  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18004eecf  cmp     ebx, r14d
0x18004eed2  setz    al
0x18004eed5  mov     cl, al
0x18004eed7  test    cl, cl
0x18004eed9  jz      short loc_18004EEE9
0x18004eedb  test    rsi, rsi
0x18004eede  jz      short loc_18004EEE2
0x18004eee0  mov     [rsi], al
0x18004eee2  mov     [r12], r14
0x18004eee6  mov     [r15], r14b
0x18004eee9  mov     [rbp+47h+var_9C], 1
0x18004eef0  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x18004eef7  mov     ebx, [rbp+47h+var_9C]
0x18004eefa  jnz     loc_18004F0C0
0x18004ef00  lea     rcx, [rbp+47h+Frame]; Frame
0x18004ef04  call    cs:__imp_RtlPopFrame
0x18004ef0b  nop     dword ptr [rax+rax+00h]
0x18004ef10  mov     eax, ebx
0x18004ef12  mov     rcx, [rbp+47h+var_38]
0x18004ef16  xor     rcx, rsp; StackCookie
0x18004ef19  call    __security_check_cookie
0x18004ef1e  mov     rbx, [rsp+0F0h+arg_0]
0x18004ef26  add     rsp, 0C0h
0x18004ef2d  pop     r15
0x18004ef2f  pop     r14
0x18004ef31  pop     r13
0x18004ef33  pop     r12
0x18004ef35  pop     rdi
0x18004ef36  pop     rsi
0x18004ef37  pop     rbp
0x18004ef38  retn
0x18004ef3a  xor     ecx, ecx; dwErrCode
0x18004ef3c  call    cs:__imp_SetLastError
0x18004ef43  nop     dword ptr [rax+rax+00h]
0x18004ef48  lea     rax, ?__stc@?1??Win32Compare@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEBG_KAEAW4StringComparisonResult@@_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Compare(ushort const *,unsigned __int64,StringComparisonResult &,bool)'::`2'::__stc
0x18004ef4f  mov     [rbp+47h+var_A0], r13d
0x18004ef53  mov     [rbp+47h+var_88], rax
0x18004ef57  lea     rcx, [rbp+47h+var_98]; this
0x18004ef5b  lea     rax, [rbp+47h+var_A0]
0x18004ef5f  mov     [rbp+47h+var_90], r13
0x18004ef63  mov     r14d, 1
0x18004ef69  mov     [rbp+47h+var_70], rax
0x18004ef6d  mov     [rbp+47h+var_98], r14d
0x18004ef71  mov     [rbp+47h+var_80], 20737853h
0x18004ef79  mov     [rbp+47h+var_78], 284h
0x18004ef80  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18004ef85  xor     ecx, ecx; dwErrCode
0x18004ef87  call    cs:__imp_SetLastError
0x18004ef8e  nop     dword ptr [rax+rax+00h]
0x18004ef93  mov     rax, [rdi+10h]
0x18004ef97  lea     rdx, [rbp+47h+String1]
0x18004ef9b  xorps   xmm0, xmm0
0x18004ef9e  mov     qword ptr [rbp+47h+String1.Length], 60006h
0x18004efa6  movups  xmmword ptr [rbp+47h+String2.Length], xmm0
0x18004efaa  mov     [rbp+47h+String2.Buffer], rax
0x18004efae  lea     rcx, [rbp+47h+String2]
0x18004efb2  movzx   eax, word ptr [rdi+20h]
0x18004efb6  add     ax, ax
0x18004efb9  mov     [rbp+47h+String2.Length], ax
0x18004efbd  mov     [rbp+47h+String2.MaximumLength], ax
0x18004efc1  lea     rax, aYes; "yes"
0x18004efc8  mov     [rbp+47h+String1.Buffer], rax
0x18004efcc  jmp     loc_18004EE97
0x18004efd1  xor     ecx, ecx; dwErrCode
0x18004efd3  call    cs:__imp_SetLastError
0x18004efda  nop     dword ptr [rax+rax+00h]
0x18004efdf  lea     r9, [rbp+47h+var_A0]
0x18004efe3  mov     r8, rbx
0x18004efe6  lea     rdx, aNo; "no"
0x18004efed  mov     rcx, rdi
0x18004eff0  call    ?Win32Compare@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEBG_KAEAW4StringComparisonResult@@_N@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Compare(ushort const *,unsigned __int64,StringComparisonResult &,bool)
0x18004eff5  test    eax, eax
0x18004eff7  jz      loc_18004F096
0x18004effd  mov     r14d, 1
0x18004f003  movzx   ecx, r13b
0x18004f007  cmp     [rbp+47h+var_A0], r14d
0x18004f00b  mov     al, r13b
0x18004f00e  cmovz   ecx, r14d
0x18004f012  jmp     loc_18004EED7
0x18004f017  cmp     rax, 5
0x18004f01b  jnz     loc_18004EEE9
0x18004f021  xor     ecx, ecx; dwErrCode
0x18004f023  call    cs:__imp_SetLastError
0x18004f02a  nop     dword ptr [rax+rax+00h]
0x18004f02f  lea     r9, [rbp+47h+var_A0]
0x18004f033  mov     r8d, 5
0x18004f039  lea     rdx, aFalse; "false"
0x18004f040  mov     rcx, rdi
0x18004f043  call    ?Win32Compare@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEBG_KAEAW4StringComparisonResult@@_N@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Compare(ushort const *,unsigned __int64,StringComparisonResult &,bool)
0x18004f048  test    eax, eax
0x18004f04a  jz      short loc_18004F09F
0x18004f04c  mov     r14d, 1
0x18004f052  cmp     [rbp+47h+var_A0], r14d
0x18004f056  jnz     loc_18004EEE9
0x18004f05c  mov     al, r13b
0x18004f05f  jmp     loc_18004EEDB
0x18004f064  mov     [rbp+47h+var_48], 0C56h
0x18004f06b  jmp     short loc_18004F074
0x18004f06d  mov     [rbp+47h+var_48], 0C57h
0x18004f074  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18004f079  mov     ecx, 57h ; 'W'; dwErrCode
0x18004f07e  call    cs:__imp_SetLastError
0x18004f085  nop     dword ptr [rax+rax+00h]
0x18004f08a  mov     rax, [rbp+47h+var_40]
0x18004f08e  mov     [rax], r13d
0x18004f091  jmp     loc_18004EEF0
0x18004f096  lea     rcx, off_180075330; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18004f09d  jmp     short loc_18004F0A6
0x18004f09f  lea     rcx, off_180075310; struct _CALL_SITE_INFO *
0x18004f0a6  mov     rax, [rbp+47h+var_40]
0x18004f0aa  mov     [rax], r13d
0x18004f0ad  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004f0b2  jmp     loc_18004EEF0
0x18004f0b7  cmovs   ebx, r13d
0x18004f0bb  jmp     loc_18004EEB1
0x18004f0c0  mov     rax, [rbp+47h+var_40]
0x18004f0c4  cmp     [rax], r13d
0x18004f0c7  jz      short loc_18004F0D5
0x18004f0c9  xor     ecx, ecx; char *
0x18004f0cb  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18004f0d0  jmp     loc_18004EF00
0x18004f0d5  call    cs:__imp_GetLastError
0x18004f0dc  nop     dword ptr [rax+rax+00h]
0x18004f0e1  mov     ecx, eax; unsigned int
0x18004f0e3  xor     edx, edx; Format
0x18004f0e5  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18004f0ea  jmp     loc_18004EF00
```
