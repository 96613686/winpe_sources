# SxspCompareAssemblyIdentityAttributeLists(ulong,ulong,_INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE const * *,_INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE const * *,ulong *)

- ea: `0x1800430b4`
- end: `0x18004348e`
- name: `?SxspCompareAssemblyIdentityAttributeLists@@YAHKKPEAPEBU_INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE@@0PEAK@Z`
- size: `986`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, const struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE **, const struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180042a94`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x1800430b4`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180043210`
- `ntdll!RtlCompareUnicodeString` at `0x18004335f`
- `ntdll!RtlCompareUnicodeString` at `0x1800433ba`
- `ntdll!RtlCompareUnicodeString` at `0x180043210`
- `ntdll!RtlCompareUnicodeString` at `0x18004335f`
- `ntdll!RtlCompareUnicodeString` at `0x1800433ba`
- `ntdll!RtlPopFrame` at `0x18004325d`
- `ntdll!RtlPopFrame` at `0x1800432b4`
- `ntdll!RtlPopFrame` at `0x18004325d`
- `ntdll!RtlPopFrame` at `0x1800432b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043474`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043161`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043231`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043287`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800432fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043449`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043161`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043231`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043287`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800432fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043449`

## pseudocode

```c
__int64 __fastcall SxspCompareAssemblyIdentityAttributeLists(
        __int64 a1,
        unsigned int a2,
        const struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE **a3,
        const struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE **a4,
        unsigned int *a5)
{
  unsigned int v7; // edi
  const char *v8; // rcx
  unsigned int v9; // ebx
  __int64 i; // r14
  const struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE *v11; // rdi
  const struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE *v12; // rsi
  const char *v13; // rcx
  WCHAR *v14; // rax
  WCHAR *v15; // rax
  LONG v16; // eax
  bool v17; // sf
  int v18; // edi
  unsigned int v19; // ebx
  WCHAR *v21; // rax
  WCHAR *v22; // rax
  LONG v23; // eax
  WCHAR *v24; // rax
  WCHAR *v25; // rax
  LONG v26; // eax
  DWORD LastError; // eax
  DWORD v28; // eax
  UNICODE_STRING String2; // [rsp+28h] [rbp-79h] BYREF
  UNICODE_STRING String1; // [rsp+38h] [rbp-69h] BYREF
  int v32; // [rsp+48h] [rbp-59h] BYREF
  int v33; // [rsp+4Ch] [rbp-55h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+50h] [rbp-51h] BYREF
  __int64 v35; // [rsp+68h] [rbp-39h]
  int v36; // [rsp+70h] [rbp-31h]
  int *v37; // [rsp+78h] [rbp-29h]
  struct _TEB_ACTIVE_FRAME v38; // [rsp+80h] [rbp-21h] BYREF
  __int64 v39; // [rsp+98h] [rbp-9h]
  int v40; // [rsp+A0h] [rbp-1h]
  unsigned int *v41; // [rsp+A8h] [rbp+7h]

  v38.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_1800710F0;
  v41 = (unsigned int *)&v32;
  v32 = 0;
  v7 = a2;
  v38.Flags = 1;
  v38.Previous = 0;
  v39 = 544438355;
  v40 = 1051;
  CFrame::BaseEnter((CFrame *)&v38);
  if ( (!v7 || a3 && a4) && a5 )
  {
    v9 = 2;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= v7 )
      {
LABEL_17:
        *a5 = v9;
        SetLastError(0);
        *v41 = 1;
        goto LABEL_18;
      }
      SetLastError(0);
      v11 = a4[i];
      v12 = a3[i];
      Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_1800710D0;
      v37 = &v33;
      v33 = 0;
      Frame.Flags = 1;
      Frame.Previous = 0;
      v35 = 544438355;
      v36 = 952;
      CFrame::BaseEnter((CFrame *)&Frame);
      if ( !v12 )
        break;
      if ( !v11 )
      {
        v36 = 964;
LABEL_21:
        FusionpTraceParameterCheck(v13);
        SetLastError(0x57u);
        v18 = 0;
        *v37 = 0;
        goto LABEL_13;
      }
      v14 = (WCHAR *)*((_QWORD *)v12 + 4);
      *(_QWORD *)&String1.Length = 0;
      String1.Buffer = v14;
      String1.Length = 2 * *((_WORD *)v12 + 4);
      String1.MaximumLength = String1.Length;
      v15 = (WCHAR *)*((_QWORD *)v11 + 4);
      *(_QWORD *)&String2.Length = 0;
      String2.Buffer = v15;
      String2.Length = 2 * *((_WORD *)v11 + 4);
      String2.MaximumLength = String2.Length;
      v16 = RtlCompareUnicodeString(&String1, &String2, 0);
      v17 = v16 < 0;
      if ( v16 )
        goto LABEL_10;
      v21 = (WCHAR *)*((_QWORD *)v12 + 5);
      *(_QWORD *)&String2.Length = 0;
      String2.Buffer = v21;
      String2.Length = 2 * *((_WORD *)v12 + 8);
      String2.MaximumLength = String2.Length;
      v22 = (WCHAR *)*((_QWORD *)v11 + 5);
      *(_QWORD *)&String1.Length = 0;
      String1.Buffer = v22;
      String1.Length = 2 * *((_WORD *)v11 + 8);
      String1.MaximumLength = String1.Length;
      v23 = RtlCompareUnicodeString(&String2, &String1, 0);
      v17 = v23 < 0;
      if ( v23 )
        goto LABEL_10;
      v24 = (WCHAR *)*((_QWORD *)v12 + 6);
      *(_QWORD *)&String2.Length = 0;
      String2.Buffer = v24;
      String2.Length = 2 * *((_WORD *)v12 + 12);
      String2.MaximumLength = String2.Length;
      v25 = (WCHAR *)*((_QWORD *)v11 + 6);
      *(_QWORD *)&String1.Length = 0;
      String1.Buffer = v25;
      String1.Length = 2 * *((_WORD *)v11 + 12);
      String1.MaximumLength = String1.Length;
      v26 = RtlCompareUnicodeString(&String2, &String1, 1u);
      v17 = v26 < 0;
      if ( v26 )
      {
LABEL_10:
        if ( v17 )
          v9 = 1;
        else
          v9 = 3;
      }
      else
      {
        v9 = 2;
      }
      SetLastError(0);
      v18 = 1;
      *v37 = 1;
LABEL_13:
      if ( g_FusionEnterExitTracingEnabled )
      {
        if ( v18 )
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
      if ( !v18 )
      {
        *v41 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007CF20);
        goto LABEL_18;
      }
      if ( v9 != 2 )
        goto LABEL_17;
      v7 = a2;
    }
    v36 = 963;
    goto LABEL_21;
  }
  v40 = 1060;
  FusionpTraceParameterCheck(v8);
  SetLastError(0x57u);
  *v41 = 0;
LABEL_18:
  v19 = *v41;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v19 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v28 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v28, 0);
    }
  }
  RtlPopFrame(&v38);
  return v19;
}

```

## disassembly

```asm
0x1800430b4  mov     [rsp-8+arg_0], rbx
0x1800430b9  push    rbp
0x1800430ba  push    rsi
0x1800430bb  push    rdi
0x1800430bc  push    r12
0x1800430be  push    r13
0x1800430c0  push    r14
0x1800430c2  push    r15
0x1800430c4  lea     rbp, [rsp-1Fh]
0x1800430c9  sub     rsp, 0C0h
0x1800430d0  mov     rax, cs:__security_cookie
0x1800430d7  xor     rax, rsp
0x1800430da  mov     [rbp+4Fh+var_40], rax
0x1800430de  mov     r15, [rbp+4Fh+arg_20]
0x1800430e2  lea     rax, qword_1800710F0
0x1800430e9  mov     [rbp+4Fh+var_70.Context], rax
0x1800430ed  lea     rcx, [rbp+4Fh+var_70]; this
0x1800430f1  lea     rax, [rbp+4Fh+var_A8]
0x1800430f5  mov     [rsp+0F0h+var_D0], edx
0x1800430f9  mov     [rbp+4Fh+var_48], rax
0x1800430fd  mov     r13, r9
0x180043100  mov     r12, r8
0x180043103  mov     [rbp+4Fh+var_A8], 0
0x18004310a  mov     edi, edx
0x18004310c  mov     [rbp+4Fh+var_70.Flags], 1
0x180043113  mov     [rbp+4Fh+var_70.Previous], 0
0x18004311b  mov     [rbp+4Fh+var_58], 20737853h
0x180043123  mov     [rbp+4Fh+var_50], 41Bh
0x18004312a  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18004312f  test    edi, edi
0x180043131  jz      short loc_180043145
0x180043133  test    r12, r12
0x180043136  jz      loc_180043438
0x18004313c  test    r13, r13
0x18004313f  jz      loc_180043438
0x180043145  test    r15, r15
0x180043148  jz      loc_180043438
0x18004314e  mov     ebx, 2
0x180043153  xor     r14d, r14d
0x180043156  cmp     r14d, edi
0x180043159  jnb     loc_180043282
0x18004315f  xor     ecx, ecx; dwErrCode
0x180043161  call    cs:__imp_SetLastError
0x180043168  nop     dword ptr [rax+rax+00h]
0x18004316d  mov     rdi, [r13+r14*8+0]
0x180043172  lea     rax, qword_1800710D0
0x180043179  mov     rsi, [r12+r14*8]
0x18004317d  lea     rcx, [rbp+4Fh+Frame]; this
0x180043181  mov     [rbp+4Fh+Frame.Context], rax
0x180043185  lea     rax, [rbp+4Fh+var_A4]
0x180043189  mov     [rbp+4Fh+var_78], rax
0x18004318d  mov     [rbp+4Fh+var_A4], 0
0x180043194  mov     [rbp+4Fh+Frame.Flags], 1
0x18004319b  mov     [rbp+4Fh+Frame.Previous], 0
0x1800431a3  mov     [rbp+4Fh+var_88], 20737853h
0x1800431ab  mov     [rbp+4Fh+var_80], 3B8h
0x1800431b2  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800431b7  test    rsi, rsi
0x1800431ba  jz      loc_1800433E7
0x1800431c0  test    rdi, rdi
0x1800431c3  jz      loc_1800432EA
0x1800431c9  mov     rax, [rsi+20h]
0x1800431cd  lea     rdx, [rbp+4Fh+String2]; String2
0x1800431d1  xorps   xmm0, xmm0
0x1800431d4  lea     rcx, [rbp+4Fh+String1]; String1
0x1800431d8  movups  xmmword ptr [rbp+4Fh+String1.Length], xmm0
0x1800431dc  mov     [rbp+4Fh+String1.Buffer], rax
0x1800431e0  xor     r8d, r8d; CaseInsensitive
0x1800431e3  movzx   eax, word ptr [rsi+8]
0x1800431e7  xorps   xmm1, xmm1
0x1800431ea  add     ax, ax
0x1800431ed  mov     [rbp+4Fh+String1.Length], ax
0x1800431f1  mov     [rbp+4Fh+String1.MaximumLength], ax
0x1800431f5  mov     rax, [rdi+20h]
0x1800431f9  movups  xmmword ptr [rbp+4Fh+String2.Length], xmm1
0x1800431fd  mov     [rbp+4Fh+String2.Buffer], rax
0x180043201  movzx   eax, word ptr [rdi+8]
0x180043205  add     ax, ax
0x180043208  mov     [rbp+4Fh+String2.Length], ax
0x18004320c  mov     [rbp+4Fh+String2.MaximumLength], ax
0x180043210  call    cs:__imp_RtlCompareUnicodeString
0x180043217  nop     dword ptr [rax+rax+00h]
0x18004321c  test    eax, eax
0x18004321e  jz      loc_180043318
0x180043224  jns     loc_1800433D0
0x18004322a  mov     ebx, 1
0x18004322f  xor     ecx, ecx; dwErrCode
0x180043231  call    cs:__imp_SetLastError
0x180043238  nop     dword ptr [rax+rax+00h]
0x18004323d  mov     rax, [rbp+4Fh+var_78]
0x180043241  mov     edi, 1
0x180043246  mov     dword ptr [rax], 1
0x18004324c  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180043253  jnz     loc_1800433F3
0x180043259  lea     rcx, [rbp+4Fh+Frame]; Frame
0x18004325d  call    cs:__imp_RtlPopFrame
0x180043264  nop     dword ptr [rax+rax+00h]
0x180043269  test    edi, edi
0x18004326b  jz      loc_18004341D
0x180043271  cmp     ebx, 2
0x180043274  jnz     short loc_180043282
0x180043276  mov     edi, [rsp+0F0h+var_D0]
0x18004327a  inc     r14d
0x18004327d  jmp     loc_180043156
0x180043282  xor     ecx, ecx; dwErrCode
0x180043284  mov     [r15], ebx
0x180043287  call    cs:__imp_SetLastError
0x18004328e  nop     dword ptr [rax+rax+00h]
0x180043293  mov     rax, [rbp+4Fh+var_48]
0x180043297  mov     dword ptr [rax], 1
0x18004329d  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x1800432a4  mov     rax, [rbp+4Fh+var_48]
0x1800432a8  mov     ebx, [rax]
0x1800432aa  jnz     loc_180043464
0x1800432b0  lea     rcx, [rbp+4Fh+var_70]; Frame
0x1800432b4  call    cs:__imp_RtlPopFrame
0x1800432bb  nop     dword ptr [rax+rax+00h]
0x1800432c0  mov     eax, ebx
0x1800432c2  mov     rcx, [rbp+4Fh+var_40]
0x1800432c6  xor     rcx, rsp; StackCookie
0x1800432c9  call    __security_check_cookie
0x1800432ce  mov     rbx, [rsp+0F0h+arg_0]
0x1800432d6  add     rsp, 0C0h
0x1800432dd  pop     r15
0x1800432df  pop     r14
0x1800432e1  pop     r13
0x1800432e3  pop     r12
0x1800432e5  pop     rdi
0x1800432e6  pop     rsi
0x1800432e7  pop     rbp
0x1800432e8  retn
0x1800432ea  mov     [rbp+4Fh+var_80], 3C4h
0x1800432f1  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x1800432f6  mov     ecx, 57h ; 'W'; dwErrCode
0x1800432fb  call    cs:__imp_SetLastError
0x180043302  nop     dword ptr [rax+rax+00h]
0x180043307  mov     rax, [rbp+4Fh+var_78]
0x18004330b  xor     edi, edi
0x18004330d  mov     dword ptr [rax], 0
0x180043313  jmp     loc_18004324C
0x180043318  mov     rax, [rsi+28h]
0x18004331c  lea     rdx, [rbp+4Fh+String1]; String2
0x180043320  xorps   xmm0, xmm0
0x180043323  lea     rcx, [rbp+4Fh+String2]; String1
0x180043327  movups  xmmword ptr [rbp+4Fh+String2.Length], xmm0
0x18004332b  mov     [rbp+4Fh+String2.Buffer], rax
0x18004332f  xor     r8d, r8d; CaseInsensitive
0x180043332  movzx   eax, word ptr [rsi+10h]
0x180043336  xorps   xmm1, xmm1
0x180043339  add     ax, ax
0x18004333c  mov     [rbp+4Fh+String2.Length], ax
0x180043340  mov     [rbp+4Fh+String2.MaximumLength], ax
0x180043344  mov     rax, [rdi+28h]
0x180043348  movups  xmmword ptr [rbp+4Fh+String1.Length], xmm1
0x18004334c  mov     [rbp+4Fh+String1.Buffer], rax
0x180043350  movzx   eax, word ptr [rdi+10h]
0x180043354  add     ax, ax
0x180043357  mov     [rbp+4Fh+String1.Length], ax
0x18004335b  mov     [rbp+4Fh+String1.MaximumLength], ax
0x18004335f  call    cs:__imp_RtlCompareUnicodeString
0x180043366  nop     dword ptr [rax+rax+00h]
0x18004336b  test    eax, eax
0x18004336d  jnz     loc_180043224
0x180043373  mov     rax, [rsi+30h]
0x180043377  lea     rdx, [rbp+4Fh+String1]; String2
0x18004337b  xorps   xmm0, xmm0
0x18004337e  lea     rcx, [rbp+4Fh+String2]; String1
0x180043382  movups  xmmword ptr [rbp+4Fh+String2.Length], xmm0
0x180043386  mov     [rbp+4Fh+String2.Buffer], rax
0x18004338a  mov     r8b, 1; CaseInsensitive
0x18004338d  movzx   eax, word ptr [rsi+18h]
0x180043391  xorps   xmm1, xmm1
0x180043394  add     ax, ax
0x180043397  mov     [rbp+4Fh+String2.Length], ax
0x18004339b  mov     [rbp+4Fh+String2.MaximumLength], ax
0x18004339f  mov     rax, [rdi+30h]
0x1800433a3  movups  xmmword ptr [rbp+4Fh+String1.Length], xmm1
0x1800433a7  mov     [rbp+4Fh+String1.Buffer], rax
0x1800433ab  movzx   eax, word ptr [rdi+18h]
0x1800433af  add     ax, ax
0x1800433b2  mov     [rbp+4Fh+String1.Length], ax
0x1800433b6  mov     [rbp+4Fh+String1.MaximumLength], ax
0x1800433ba  call    cs:__imp_RtlCompareUnicodeString
0x1800433c1  nop     dword ptr [rax+rax+00h]
0x1800433c6  test    eax, eax
0x1800433c8  jnz     loc_180043224
0x1800433ce  jmp     short loc_1800433DD
0x1800433d0  mov     ebx, 3
0x1800433d5  test    eax, eax
0x1800433d7  jnz     loc_18004322F
0x1800433dd  mov     ebx, 2
0x1800433e2  jmp     loc_18004322F
0x1800433e7  mov     [rbp+4Fh+var_80], 3C3h
0x1800433ee  jmp     loc_1800432F1
0x1800433f3  test    edi, edi
0x1800433f5  jz      short loc_180043403
0x1800433f7  xor     ecx, ecx; char *
0x1800433f9  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x1800433fe  jmp     loc_180043259
0x180043403  call    cs:__imp_GetLastError
0x18004340a  nop     dword ptr [rax+rax+00h]
0x18004340f  mov     ecx, eax; unsigned int
0x180043411  xor     edx, edx; Format
0x180043413  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180043418  jmp     loc_180043259
0x18004341d  mov     rax, [rbp+4Fh+var_48]
0x180043421  lea     rcx, off_18007CF20; struct _CALL_SITE_INFO *
0x180043428  mov     dword ptr [rax], 0
0x18004342e  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180043433  jmp     loc_18004329D
0x180043438  mov     [rbp+4Fh+var_50], 424h
0x18004343f  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180043444  mov     ecx, 57h ; 'W'; dwErrCode
0x180043449  call    cs:__imp_SetLastError
0x180043450  nop     dword ptr [rax+rax+00h]
0x180043455  mov     rax, [rbp+4Fh+var_48]
0x180043459  mov     dword ptr [rax], 0
0x18004345f  jmp     loc_18004329D
0x180043464  test    ebx, ebx
0x180043466  jz      short loc_180043474
0x180043468  xor     ecx, ecx; char *
0x18004346a  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18004346f  jmp     loc_1800432B0
0x180043474  call    cs:__imp_GetLastError
0x18004347b  nop     dword ptr [rax+rax+00h]
0x180043480  mov     ecx, eax; unsigned int
0x180043482  xor     edx, edx; Format
0x180043484  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180043489  jmp     loc_1800432B0
```
