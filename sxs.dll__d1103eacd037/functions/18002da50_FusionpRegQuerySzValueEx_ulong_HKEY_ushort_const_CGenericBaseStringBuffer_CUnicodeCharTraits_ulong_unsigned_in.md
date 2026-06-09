# FusionpRegQuerySzValueEx(ulong,HKEY__ *,ushort const *,CGenericBaseStringBuffer<CUnicodeCharTraits> &,ulong &,unsigned __int64,...)

- ea: `0x18002da50`
- end: `0x18002de07`
- name: `?FusionpRegQuerySzValueEx@@YAHKPEAUHKEY__@@PEBGAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEAK_KZZ`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180026a60`

## callees

- `0x18000a804`
- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x180023260`
- `0x18002d630`
- `0x18002da50`
- `0x18002de10`
- `0x18002de34`
- `0x180030480`
- `0x18005cf40`
- `0x18005d2b0`
- `0x18005d38c`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18002db4e`
- `ntdll!RtlPopFrame` at `0x18002dc0d`
- `ntdll!RtlPopFrame` at `0x18002db4e`
- `ntdll!RtlPopFrame` at `0x18002dc0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dded`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dbc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dcbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dbc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dcbb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002db8e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002dd38`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002db8e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002dd38`

## string_xrefs

- `0x18002dd9d`: `SXS.DLL: %s(%d) Err 0x%08lx not acceptable`

## pseudocode

```c
__int64 __fastcall FusionpRegQuerySzValueEx(
        int a1,
        HKEY a2,
        const WCHAR *a3,
        LPBYTE a4,
        unsigned int *a5,
        unsigned __int64 a6,
        char a7)
{
  const char *v11; // rcx
  BYTE *lpData; // rsi
  __int64 v13; // rdi
  DWORD v14; // r14d
  DWORD v15; // eax
  LSTATUS v16; // eax
  unsigned int v17; // edi
  int *v18; // rax
  unsigned int v19; // edi
  LSTATUS v21; // eax
  char *v22; // rdx
  unsigned __int64 i; // rax
  char **v24; // rcx
  DWORD LastError; // eax
  LPBYTE v26[2]; // [rsp+30h] [rbp-99h] BYREF
  __int64 v27; // [rsp+40h] [rbp-89h]
  unsigned int *v28; // [rsp+48h] [rbp-81h]
  DWORD cbData; // [rsp+58h] [rbp-71h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-6Dh] BYREF
  int v31; // [rsp+60h] [rbp-69h] BYREF
  struct _TEB_ACTIVE_FRAME v32; // [rsp+68h] [rbp-61h] BYREF
  __int64 v33; // [rsp+80h] [rbp-49h]
  int v34; // [rsp+88h] [rbp-41h]
  int *v35; // [rsp+90h] [rbp-39h]
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+98h] [rbp-31h] BYREF
  __int64 v37; // [rsp+B0h] [rbp-19h]
  int v38; // [rsp+B8h] [rbp-11h]

  v32.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006E048;
  v28 = a5;
  v35 = &v31;
  v31 = 0;
  v32.Flags = 1;
  v32.Previous = 0;
  v33 = 544438355;
  v34 = 37;
  CFrame::BaseEnter((CFrame *)&v32);
  v27 = 0;
  cbData = 0;
  *(_OWORD *)v26 = 0;
  Type = 0;
  *a5 = 0;
  CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(a4);
  if ( (a1 & 0xFFFFFFFE) != 0 )
  {
    v34 = 46;
    FusionpTraceParameterCheck(v11);
    SetLastError(0x57u);
    *v35 = 0;
    goto LABEL_18;
  }
  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach'::`2'::__stc;
  Frame.Previous = 0;
  v37 = 544438355;
  v38 = 1580;
  CFrame::BaseEnter((CFrame *)&Frame);
  _InterlockedIncrement((volatile signed __int32 *)a4 + 2);
  lpData = (BYTE *)*((_QWORD *)a4 + 2);
  v13 = *((_QWORD *)a4 + 3);
  v26[1] = lpData;
  v27 = v13;
  v26[0] = a4;
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallExit();
  RtlPopFrame(&Frame);
  v14 = -1;
  if ( (unsigned __int64)(2 * v13) <= 0xFFFFFFFF )
    v15 = 2 * v13 - 2;
  else
    v15 = -1;
  cbData = v15;
  v16 = RegQueryValueExW(a2, a3, 0, &Type, lpData, &cbData);
  v17 = v16;
  if ( v16 == 2 )
  {
    if ( (a1 & 1) != 0 )
    {
      SetLastError(0);
      SetLastError(0);
      goto LABEL_11;
    }
    goto LABEL_26;
  }
  if ( v16 == 234 )
  {
    CGenericStringBufferAccessor<CUnicodeCharTraits>::Detach(v26);
    SetLastError(0);
    if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(
                         a4,
                         ((unsigned __int64)cbData >> 1) + 1) )
    {
      CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(v26, a4);
      if ( (unsigned __int64)(2 * v27) <= 0xFFFFFFFF )
        v14 = 2 * v27;
      lpData = v26[1];
      cbData = v14;
      v21 = RegQueryValueExW(a2, a3, 0, &Type, v26[1], &cbData);
      a4 = v26[0];
      v17 = v21;
      goto LABEL_8;
    }
    *v35 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007C9C0);
LABEL_18:
    lpData = v26[1];
    a4 = v26[0];
    goto LABEL_12;
  }
LABEL_8:
  if ( !v17 )
  {
    if ( Type == 1 )
    {
LABEL_10:
      SetLastError(0);
LABEL_11:
      *v35 = 1;
      goto LABEL_12;
    }
    CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v32, 0xDu);
    v24 = off_18007CA80;
    goto LABEL_32;
  }
LABEL_26:
  v22 = &a7;
  *v28 = v17;
  for ( i = 0; i < a6; ++i )
  {
    v22 += 8;
    if ( v17 == *((_DWORD *)v22 - 2) )
      break;
  }
  if ( i != a6 )
    goto LABEL_10;
  FusionpDbgPrintEx(0xC0000000, "SXS.DLL: %s(%d) Err 0x%08lx not acceptable", "FusionpRegQuerySzValueEx", 98, v17);
  CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v32, v17);
  v24 = off_18007CA40;
LABEL_32:
  FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)v24);
LABEL_12:
  v18 = v35;
  v19 = *v35;
  if ( a4 )
  {
    *((_QWORD *)a4 + 4) = CUnicodeCharTraits::Cch((const unsigned __int16 *)lpData);
    _InterlockedDecrement((volatile signed __int32 *)a4 + 2);
    v18 = v35;
  }
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v18 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&v32);
  return v19;
}

```

## disassembly

```asm
0x18002da50  push    rbp
0x18002da52  push    rbx
0x18002da53  push    rsi
0x18002da54  push    rdi
0x18002da55  push    r12
0x18002da57  push    r13
0x18002da59  push    r14
0x18002da5b  push    r15
0x18002da5d  lea     rbp, [rsp-0Fh]
0x18002da62  sub     rsp, 0D8h
0x18002da69  mov     rax, cs:__security_cookie
0x18002da70  xor     rax, rsp
0x18002da73  mov     [rbp+47h+var_50], rax
0x18002da77  mov     rdi, [rbp+47h+arg_20]
0x18002da7b  lea     rax, qword_18006E048
0x18002da82  mov     [rbp+47h+var_A8.Context], rax
0x18002da86  mov     r15d, ecx
0x18002da89  lea     rax, [rbp+47h+var_B0]
0x18002da8d  mov     [rsp+110h+var_C8], rdi
0x18002da92  xor     r14d, r14d
0x18002da95  mov     [rbp+47h+var_80], rax
0x18002da99  mov     esi, 20737853h
0x18002da9e  mov     [rbp+47h+var_B0], r14d
0x18002daa2  lea     rcx, [rbp+47h+var_A8]; this
0x18002daa6  mov     [rbp+47h+var_A8.Flags], 1
0x18002daad  mov     rbx, r9
0x18002dab0  mov     [rbp+47h+var_A8.Previous], r14
0x18002dab4  mov     r13, r8
0x18002dab7  mov     [rbp+47h+var_90], rsi
0x18002dabb  mov     r12, rdx
0x18002dabe  mov     [rbp+47h+var_88], 25h ; '%'
0x18002dac5  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002daca  xorps   xmm0, xmm0
0x18002dacd  mov     [rsp+110h+var_D0], r14
0x18002dad2  mov     rcx, rbx
0x18002dad5  mov     [rbp+47h+cbData], r14d
0x18002dad9  movdqu  xmmword ptr [rsp+110h+var_E0], xmm0
0x18002dadf  mov     [rbp+47h+Type], r14d
0x18002dae3  mov     [rdi], r14d
0x18002dae6  call    ?Clear@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAX_N@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(bool)
0x18002daeb  test    r15d, 0FFFFFFFEh
0x18002daf2  jnz     loc_18002DC44
0x18002daf8  lea     rax, ?__stc@?1??Attach@?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAAXPEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(CGenericBaseStringBuffer<CUnicodeCharTraits> *)'::`2'::__stc
0x18002daff  mov     [rbp+47h+Frame.Flags], 1
0x18002db06  lea     rcx, [rbp+47h+Frame]; this
0x18002db0a  mov     [rbp+47h+Frame.Context], rax
0x18002db0e  mov     [rbp+47h+Frame.Previous], r14
0x18002db12  mov     [rbp+47h+var_60], rsi
0x18002db16  mov     [rbp+47h+var_58], 62Ch
0x18002db1d  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002db22  lock inc dword ptr [rbx+8]
0x18002db26  cmp     cs:g_FusionEnterExitTracingEnabled, r14b
0x18002db2d  mov     rsi, [rbx+10h]
0x18002db31  mov     rdi, [rbx+18h]
0x18002db35  mov     [rsp+110h+var_E0+8], rsi
0x18002db3a  mov     [rsp+110h+var_D0], rdi
0x18002db3f  mov     [rsp+110h+var_E0], rbx
0x18002db44  jnz     loc_18002DC77
0x18002db4a  lea     rcx, [rbp+47h+Frame]; Frame
0x18002db4e  call    cs:__imp_RtlPopFrame
0x18002db55  nop     dword ptr [rax+rax+00h]
0x18002db5a  lea     rax, [rdi+rdi]
0x18002db5e  mov     r14d, 0FFFFFFFFh
0x18002db64  cmp     rax, r14
0x18002db67  jbe     loc_18002DC3C
0x18002db6d  mov     eax, r14d
0x18002db70  mov     [rbp+47h+cbData], eax
0x18002db73  lea     r9, [rbp+47h+Type]; lpType
0x18002db77  lea     rax, [rbp+47h+cbData]
0x18002db7b  xor     r8d, r8d; lpReserved
0x18002db7e  mov     [rsp+110h+lpcbData], rax; lpcbData
0x18002db83  mov     rdx, r13; lpValueName
0x18002db86  mov     rcx, r12; hKey
0x18002db89  mov     [rsp+110h+lpData], rsi; lpData
0x18002db8e  call    cs:__imp_RegQueryValueExW
0x18002db95  nop     dword ptr [rax+rax+00h]
0x18002db9a  mov     edi, eax
0x18002db9c  cmp     eax, 2
0x18002db9f  jz      loc_18002DC81
0x18002dba5  cmp     eax, 0EAh
0x18002dbaa  jz      loc_18002DCAF
0x18002dbb0  xor     r14d, r14d
0x18002dbb3  test    edi, edi
0x18002dbb5  jnz     loc_18002DD53
0x18002dbbb  cmp     [rbp+47h+Type], 1
0x18002dbbf  jnz     loc_18002DDBD
0x18002dbc5  xor     ecx, ecx; dwErrCode
0x18002dbc7  call    cs:__imp_SetLastError
0x18002dbce  nop     dword ptr [rax+rax+00h]
0x18002dbd3  mov     rax, [rbp+47h+var_80]
0x18002dbd7  mov     dword ptr [rax], 1
0x18002dbdd  mov     rax, [rbp+47h+var_80]
0x18002dbe1  mov     edi, [rax]
0x18002dbe3  test    rbx, rbx
0x18002dbe6  jz      short loc_18002DBFC
0x18002dbe8  mov     rcx, rsi; unsigned __int16 *
0x18002dbeb  call    ?Cch@CUnicodeCharTraits@@SA_KPEBG@Z; CUnicodeCharTraits::Cch(ushort const *)
0x18002dbf0  mov     [rbx+20h], rax
0x18002dbf4  lock dec dword ptr [rbx+8]
0x18002dbf8  mov     rax, [rbp+47h+var_80]
0x18002dbfc  cmp     cs:g_FusionEnterExitTracingEnabled, r14b
0x18002dc03  jnz     loc_18002DDDC
0x18002dc09  lea     rcx, [rbp+47h+var_A8]; Frame
0x18002dc0d  call    cs:__imp_RtlPopFrame
0x18002dc14  nop     dword ptr [rax+rax+00h]
0x18002dc19  mov     eax, edi
0x18002dc1b  mov     rcx, [rbp+47h+var_50]
0x18002dc1f  xor     rcx, rsp; StackCookie
0x18002dc22  call    __security_check_cookie
0x18002dc27  add     rsp, 0D8h
0x18002dc2e  pop     r15
0x18002dc30  pop     r14
0x18002dc32  pop     r13
0x18002dc34  pop     r12
0x18002dc36  pop     rdi
0x18002dc37  pop     rsi
0x18002dc38  pop     rbx
0x18002dc39  pop     rbp
0x18002dc3a  retn
0x18002dc3c  add     eax, 0FFFFFFFEh
0x18002dc3f  jmp     loc_18002DB70
0x18002dc44  mov     [rbp+47h+var_88], 2Eh ; '.'
0x18002dc4b  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18002dc50  mov     ecx, 57h ; 'W'; dwErrCode
0x18002dc55  call    cs:__imp_SetLastError
0x18002dc5c  nop     dword ptr [rax+rax+00h]
0x18002dc61  mov     rax, [rbp+47h+var_80]
0x18002dc65  mov     [rax], r14d
0x18002dc68  mov     rsi, [rsp+110h+var_E0+8]
0x18002dc6d  mov     rbx, [rsp+110h+var_E0]
0x18002dc72  jmp     loc_18002DBDD
0x18002dc77  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x18002dc7c  jmp     loc_18002DB4A
0x18002dc81  test    r15b, 1
0x18002dc85  jz      loc_18002DD50
0x18002dc8b  xor     ecx, ecx; dwErrCode
0x18002dc8d  call    cs:__imp_SetLastError
0x18002dc94  nop     dword ptr [rax+rax+00h]
0x18002dc99  xor     ecx, ecx; dwErrCode
0x18002dc9b  call    cs:__imp_SetLastError
0x18002dca2  nop     dword ptr [rax+rax+00h]
0x18002dca7  xor     r14d, r14d
0x18002dcaa  jmp     loc_18002DBD3
0x18002dcaf  lea     rcx, [rsp+110h+var_E0]
0x18002dcb4  call    ?Detach@?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAAXXZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::Detach(void)
0x18002dcb9  xor     ecx, ecx; dwErrCode
0x18002dcbb  call    cs:__imp_SetLastError
0x18002dcc2  nop     dword ptr [rax+rax+00h]
0x18002dcc7  mov     edx, [rbp+47h+cbData]
0x18002dcca  mov     rcx, rbx
0x18002dccd  shr     rdx, 1
0x18002dcd0  inc     rdx
0x18002dcd3  call    ?Win32ResizeBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAH_KW4EPreserveContents@@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(unsigned __int64,EPreserveContents)
0x18002dcd8  test    eax, eax
0x18002dcda  jnz     short loc_18002DCF7
0x18002dcdc  mov     rax, [rbp+47h+var_80]
0x18002dce0  lea     rcx, off_18007C9C0; struct _CALL_SITE_INFO *
0x18002dce7  xor     r14d, r14d
0x18002dcea  mov     [rax], r14d
0x18002dced  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002dcf2  jmp     loc_18002DC68
0x18002dcf7  mov     rdx, rbx
0x18002dcfa  lea     rcx, [rsp+110h+var_E0]
0x18002dcff  call    ?Attach@?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAAXPEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(CGenericBaseStringBuffer<CUnicodeCharTraits> *)
0x18002dd04  mov     rax, [rsp+110h+var_D0]
0x18002dd09  add     rax, rax
0x18002dd0c  cmp     rax, r14
0x18002dd0f  ja      short loc_18002DD14
0x18002dd11  mov     r14d, eax
0x18002dd14  mov     rsi, [rsp+110h+var_E0+8]
0x18002dd19  lea     rax, [rbp+47h+cbData]
0x18002dd1d  mov     [rsp+110h+lpcbData], rax; lpcbData
0x18002dd22  lea     r9, [rbp+47h+Type]; lpType
0x18002dd26  xor     r8d, r8d; lpReserved
0x18002dd29  mov     [rsp+110h+lpData], rsi; lpData
0x18002dd2e  mov     rdx, r13; lpValueName
0x18002dd31  mov     [rbp+47h+cbData], r14d
0x18002dd35  mov     rcx, r12; hKey
0x18002dd38  call    cs:__imp_RegQueryValueExW
0x18002dd3f  nop     dword ptr [rax+rax+00h]
0x18002dd44  mov     rbx, [rsp+110h+var_E0]
0x18002dd49  mov     edi, eax
0x18002dd4b  jmp     loc_18002DBB0
0x18002dd50  xor     r14d, r14d
0x18002dd53  mov     rax, [rsp+110h+var_C8]
0x18002dd58  lea     rdx, [rbp+47h+arg_30]
0x18002dd5f  mov     rcx, [rbp+47h+arg_28]
0x18002dd63  mov     [rax], edi
0x18002dd65  mov     rax, r14
0x18002dd68  test    rcx, rcx
0x18002dd6b  jz      short loc_18002DD7E
0x18002dd6d  lea     rdx, [rdx+8]
0x18002dd71  cmp     edi, [rdx-8]
0x18002dd74  jz      short loc_18002DD7E
0x18002dd76  inc     rax
0x18002dd79  cmp     rax, rcx
0x18002dd7c  jb      short loc_18002DD6D
0x18002dd7e  cmp     rax, rcx
0x18002dd81  jnz     loc_18002DBC5
0x18002dd87  mov     r9d, 62h ; 'b'
0x18002dd8d  mov     dword ptr [rsp+110h+lpData], edi
0x18002dd91  lea     r8, aFusionpregquer; "FusionpRegQuerySzValueEx"
0x18002dd98  mov     ecx, 0C0000000h; unsigned int
0x18002dd9d  lea     rdx, aSxsDllSDErr0x0; "SXS.DLL: %s(%d) Err 0x%08lx not accepta"...
0x18002dda4  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18002dda9  mov     edx, edi; unsigned int
0x18002ddab  lea     rcx, [rbp+47h+var_A8]; this
0x18002ddaf  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x18002ddb4  lea     rcx, off_18007CA40; "clientcore\\base\\win32\\fusion\\utils"...
0x18002ddbb  jmp     short loc_18002DDD2
0x18002ddbd  mov     edx, 0Dh; unsigned int
0x18002ddc2  lea     rcx, [rbp+47h+var_A8]; this
0x18002ddc6  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x18002ddcb  lea     rcx, off_18007CA80; struct _CALL_SITE_INFO *
0x18002ddd2  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18002ddd7  jmp     loc_18002DBDD
0x18002dddc  cmp     [rax], r14d
0x18002dddf  jz      short loc_18002DDED
0x18002dde1  xor     ecx, ecx; char *
0x18002dde3  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18002dde8  jmp     loc_18002DC09
0x18002dded  call    cs:__imp_GetLastError
0x18002ddf4  nop     dword ptr [rax+rax+00h]
0x18002ddf9  mov     ecx, eax; unsigned int
0x18002ddfb  xor     edx, edx; Format
0x18002ddfd  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18002de02  jmp     loc_18002DC09
```
