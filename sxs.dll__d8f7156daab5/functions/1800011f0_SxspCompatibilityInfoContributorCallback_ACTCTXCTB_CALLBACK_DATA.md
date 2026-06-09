# SxspCompatibilityInfoContributorCallback(_ACTCTXCTB_CALLBACK_DATA *)

- ea: `0x1800011f0`
- end: `0x1800017b0`
- name: `?SxspCompatibilityInfoContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z`
- size: `1472`
- prototype: `void __fastcall(union _ACTCTXCTB_CALLBACK_DATA *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800011f0`
- `0x1800017b8`
- `0x180001b54`
- `0x180001c70`
- `0x18000df40`
- `0x18000dffc`
- `0x180013150`
- `0x18001c2c8`
- `0x180022f60`
- `0x18005cf40`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a0dd`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x1800013a9`
- `ntdll!RtlPopFrame` at `0x1800015cc`
- `ntdll!RtlPopFrame` at `0x180001618`
- `ntdll!RtlPopFrame` at `0x1800013a9`
- `ntdll!RtlPopFrame` at `0x1800015cc`
- `ntdll!RtlPopFrame` at `0x180001618`
- `ntdll!_snprintf_s` at `0x180001326`
- `ntdll!_snprintf_s` at `0x180001326`
- `ntdll!RtlGetFrame` at `0x1800012ce`
- `ntdll!RtlGetFrame` at `0x1800012ce`
- `ntdll!RtlPushFrame` at `0x18000124a`
- `ntdll!RtlPushFrame` at `0x18000140e`
- `ntdll!RtlPushFrame` at `0x18000124a`
- `ntdll!RtlPushFrame` at `0x18000140e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000133d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000133d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800012ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000171f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800012ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000171f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000134b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000135c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001438`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800016e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000134b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000135c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001438`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800016e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800012a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800012a9`

## pseudocode

```c
void __fastcall SxspCompatibilityInfoContributorCallback(union _ACTCTXCTB_CALLBACK_DATA *a1)
{
  __int64 v1; // r14
  bool v3; // zf
  _QWORD *v4; // rax
  int Previous; // edi
  const char *v6; // rsi
  const char *FrameName; // r14
  PTEB_ACTIVE_FRAME v8; // rax
  PTEB_ACTIVE_FRAME v9; // rcx
  DWORD LastError; // ebx
  unsigned int *v11; // r13
  __int64 v12; // rbx
  const char *v13; // rcx
  WCHAR *v14; // rax
  int v15; // r15d
  __int64 v16; // r12
  unsigned __int64 v17; // rbx
  __int64 v18; // rdi
  unsigned int v19; // edi
  char v20; // r14
  PCTEB_ACTIVE_FRAME_CONTEXT Context; // rdx
  __int64 v22; // rax
  int v23; // ebx
  struct _ACTIVATION_CONTEXT_COMPATIBILITY_INFORMATION *v24; // rbx
  DWORD v25; // eax
  WCHAR *v26; // [rsp+50h] [rbp-B8h]
  int v27; // [rsp+58h] [rbp-B0h] BYREF
  struct _TEB_ACTIVE_FRAME v28; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+78h] [rbp-90h]
  int v30; // [rsp+80h] [rbp-88h]
  int *v31; // [rsp+88h] [rbp-80h]
  struct _TEB_ACTIVE_FRAME v32; // [rsp+90h] [rbp-78h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-60h]
  int v34; // [rsp+B0h] [rbp-58h]
  _TEB_ACTIVE_FRAME Frame; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v36; // [rsp+D0h] [rbp-38h]
  int v37; // [rsp+D8h] [rbp-30h]
  char Buffer[512]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v39; // [rsp+300h] [rbp+1F8h]

  Frame.Flags = 1;
  Frame.Previous = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006C000;
  v36 = 544438355;
  v37 = 63;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v3 = *(_DWORD *)a1 == 2;
  v39 = v1;
  if ( v3 )
  {
    *((_DWORD *)a1 + 28) = 0;
    if ( !*((_QWORD *)a1 + 5) )
    {
      v4 = HeapAlloc(g_hHeap, 0, 0x10u);
      if ( !v4 )
      {
        Previous = 0;
        v6 = byte_18008517D;
        FrameName = byte_18008517D;
        v8 = RtlGetFrame();
        if ( v8 && (v8->Flags & 1) != 0 )
        {
          v9 = v8;
        }
        else
        {
          v9 = 0;
          if ( !v8 )
          {
LABEL_8:
            LastError = GetLastError();
            _snprintf_s(
              Buffer,
              0x200u,
              0x1FFu,
              "%s(%d): Memory allocation failed in function %s\n   Expression: %s\n",
              v6,
              Previous,
              FrameName,
              byte_18008517D);
            Buffer[511] = 0;
            OutputDebugStringA(Buffer);
            SetLastError(LastError);
            SetLastError(0xEu);
            goto LABEL_9;
          }
        }
        Context = v8->Context;
        if ( Context )
        {
          if ( Context->FrameName )
            FrameName = Context->FrameName;
          if ( (Context->Flags & 1) != 0 && *(_QWORD *)&Context[1].Flags )
            v6 = *(const char **)&Context[1].Flags;
        }
        if ( v9 && *(_QWORD *)&v9[1].Flags == 544438355 && LODWORD(v9[1].Previous) )
          Previous = (int)v9[1].Previous;
        goto LABEL_8;
      }
      *(_DWORD *)v4 = 0;
      v4[1] = 0;
      *((_QWORD *)a1 + 5) = v4;
    }
  }
  v11 = (unsigned int *)*((_QWORD *)a1 + 5);
  v32.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006C020;
  v32.Flags = 1;
  v32.Previous = 0;
  v33 = 544438355;
  v34 = 331;
  RtlPushFrame(&v32);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( *(_DWORD *)a1 == 7 )
  {
    *((_DWORD *)a1 + 28) = 0;
    SetLastError(0);
    v12 = *((_QWORD *)a1 + 11);
    v28.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D2C0;
    v27 = 0;
    v31 = &v27;
    v28.Flags = 1;
    v28.Previous = 0;
    v29 = 544438355;
    v30 = 2540;
    CFrame::BaseEnter((CFrame *)&v28);
    if ( v12 )
    {
      v14 = *(WCHAR **)v12;
      v15 = *(_DWORD *)(v12 + 36);
      v16 = *(_QWORD *)(v12 + 8);
      v17 = 0;
      v26 = v14;
      while ( v17 < 3 )
      {
        v18 = 4 * v17;
        if ( LODWORD(qword_18007AA28[4 * v17 + 1]) == v15 && qword_18007AA40[v18] == v16 )
        {
          if ( !FusionpCompareStrings(v14, v16, (&off_18007AA38)[v18], v16, 0) )
          {
            v19 = qword_18007AA40[v18 + 1];
            v20 = 1;
            goto LABEL_39;
          }
          v14 = v26;
        }
        ++v17;
      }
      v19 = 0;
      v20 = 0;
LABEL_39:
      v23 = 1;
      v27 = 1;
    }
    else
    {
      v19 = 0;
      v30 = 2546;
      v20 = 0;
      FusionpTraceParameterCheck(v13);
      SetLastError(0x57u);
      *v31 = 0;
      v23 = v27;
    }
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( *v31 )
      {
        FusionpTraceCallSuccessfulExit(0);
      }
      else
      {
        v25 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v25, 0);
      }
    }
    RtlPopFrame(&v28);
    if ( v23 )
    {
      if ( !v20 || (v19 == 2 || v19 <= 1) && (unsigned int)CCompatibilityInfo::ParseElement(v11, a1, v19) )
LABEL_45:
        *((_DWORD *)a1 + 28) = 1;
    }
    else
    {
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007AA10);
    }
  }
  else
  {
    switch ( *(_DWORD *)a1 )
    {
      case 2:
        goto LABEL_45;
      case 0xA:
        *((_DWORD *)a1 + 22) = 1;
        break;
      case 0xC:
      case 0xF:
        *((_DWORD *)a1 + 20) = 1;
        break;
      case 0xD:
        v22 = 32LL * *v11;
        *((_DWORD *)a1 + 22) = 1;
        *((_QWORD *)a1 + 10) = v22 + 8;
        break;
      case 0xE:
        v24 = (struct _ACTIVATION_CONTEXT_COMPATIBILITY_INFORMATION *)*((_QWORD *)a1 + 11);
        v24->ElementCount = *v11;
        memcpy_0(&v24->Elements[0].Id.Data2, *((const void **)v11 + 1), 32LL * *v11);
        FillSupportedOsInfo(v24, (struct _SUPPORTED_OS_INFO *)(*((_QWORD *)a1 + 9) + 4306LL));
        FillMaxVersionTestedInfo(v24, (struct _MAXVERSIONTESTED_INFO *)(*((_QWORD *)a1 + 9) + 4312LL));
        *((_DWORD *)a1 + 24) = 1;
        break;
      default:
        break;
    }
  }
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallExit();
  RtlPopFrame(&v32);
  if ( *(_DWORD *)a1 == 16 && v11 )
  {
    operator delete(*((void **)v11 + 1));
    *((_QWORD *)v11 + 1) = 0;
    operator delete(v11);
  }
LABEL_9:
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallExit();
  RtlPopFrame(&Frame);
}

```

## disassembly

```asm
0x1800011f0  mov     r11, rsp
0x1800011f3  push    rbp
0x1800011f4  lea     rbp, [r11-218h]
0x1800011fb  sub     rsp, 310h
0x180001202  mov     rax, cs:__security_cookie
0x180001209  xor     rax, rsp
0x18000120c  mov     [rbp+210h+var_30], rax
0x180001213  mov     [r11+18h], rsi
0x180001217  lea     rax, qword_18006C000
0x18000121e  mov     [r11-28h], r15
0x180001222  mov     rsi, rcx
0x180001225  xor     r15d, r15d
0x180001228  mov     [rbp+210h+Frame.Flags], 1
0x18000122f  lea     rcx, [rbp+210h+Frame]; Frame
0x180001233  mov     [rbp+210h+Frame.Previous], r15
0x180001237  mov     [rbp+210h+Frame.Context], rax
0x18000123b  mov     [rbp+210h+var_248], 20737853h
0x180001243  mov     [rbp+210h+var_240], 3Fh ; '?'
0x18000124a  call    cs:__imp_RtlPushFrame
0x180001251  nop     dword ptr [rax+rax+00h]
0x180001256  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x18000125d  jnz     loc_18000165B
0x180001263  cmp     dword ptr [rsi], 2
0x180001266  mov     [rsp+310h+arg_8], rbx
0x18000126e  mov     [rsp+310h+arg_18], rdi
0x180001276  mov     [rsp+308h], r12
0x18000127e  mov     [rsp+310h+var_18], r14
0x180001286  jnz     loc_1800013D9
0x18000128c  mov     [rsi+70h], r15d
0x180001290  cmp     [rsi+28h], r15
0x180001294  jnz     loc_1800013D9
0x18000129a  mov     rcx, cs:g_hHeap; hHeap
0x1800012a1  xor     edx, edx; dwFlags
0x1800012a3  mov     r8d, 10h; dwBytes
0x1800012a9  call    cs:__imp_HeapAlloc
0x1800012b0  nop     dword ptr [rax+rax+00h]
0x1800012b5  test    rax, rax
0x1800012b8  jnz     loc_1800013CE
0x1800012be  lea     r12, byte_18008517D
0x1800012c5  mov     edi, r15d
0x1800012c8  mov     rsi, r12
0x1800012cb  mov     r14, r12
0x1800012ce  call    cs:__imp_RtlGetFrame
0x1800012d5  nop     dword ptr [rax+rax+00h]
0x1800012da  test    rax, rax
0x1800012dd  jnz     loc_18000150F
0x1800012e3  mov     rcx, r15
0x1800012e6  test    rax, rax
0x1800012e9  jnz     loc_18000151B
0x1800012ef  call    cs:__imp_GetLastError
0x1800012f6  nop     dword ptr [rax+rax+00h]
0x1800012fb  mov     qword ptr [rsp+310h+var_2D8], r12
0x180001300  lea     r9, Format; "%s(%d): Memory allocation failed in fun"...
0x180001307  mov     [rsp+310h+var_2E0], r14
0x18000130c  lea     rcx, [rbp+210h+Buffer]; Buffer
0x180001310  mov     dword ptr [rsp+310h+var_2E8], edi
0x180001314  mov     edx, 200h; BufferCount
0x180001319  mov     r8d, 1FFh; MaxCount
0x18000131f  mov     qword ptr [rsp+310h+var_2F0], rsi
0x180001324  mov     ebx, eax
0x180001326  call    cs:__imp__snprintf_s
0x18000132d  nop     dword ptr [rax+rax+00h]
0x180001332  lea     rcx, [rbp+210h+Buffer]; lpOutputString
0x180001336  mov     [rbp+210h+var_31], r15b
0x18000133d  call    cs:__imp_OutputDebugStringA
0x180001344  nop     dword ptr [rax+rax+00h]
0x180001349  mov     ecx, ebx; dwErrCode
0x18000134b  call    cs:__imp_SetLastError
0x180001352  nop     dword ptr [rax+rax+00h]
0x180001357  mov     ecx, 0Eh; dwErrCode
0x18000135c  call    cs:__imp_SetLastError
0x180001363  nop     dword ptr [rax+rax+00h]
0x180001368  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18000136f  mov     r15, [rsp+310h+var_20]
0x180001377  mov     r14, [rsp+310h+var_18]
0x18000137f  mov     r12, [rsp+308h]
0x180001387  mov     rdi, [rsp+310h+arg_18]
0x18000138f  mov     rsi, [rsp+310h+arg_10]
0x180001397  mov     rbx, [rsp+310h+arg_8]
0x18000139f  jnz     loc_18000176C
0x1800013a5  lea     rcx, [rbp+210h+Frame]; Frame
0x1800013a9  call    cs:__imp_RtlPopFrame
0x1800013b0  nop     dword ptr [rax+rax+00h]
0x1800013b5  mov     rcx, [rbp+210h+var_30]
0x1800013bc  xor     rcx, rsp; StackCookie
0x1800013bf  call    __security_check_cookie
0x1800013c4  add     rsp, 310h
0x1800013cb  pop     rbp
0x1800013cc  retn
0x1800013ce  mov     [rax], r15d
0x1800013d1  mov     [rax+8], r15
0x1800013d5  mov     [rsi+28h], rax
0x1800013d9  lea     rax, qword_18006C020
0x1800013e0  mov     [rsp+310h+var_10], r13
0x1800013e8  mov     r13, [rsi+28h]
0x1800013ec  lea     rcx, [rbp+210h+var_288]; Frame
0x1800013f0  mov     [rbp+210h+var_288.Context], rax
0x1800013f4  mov     [rbp+210h+var_288.Flags], 1
0x1800013fb  mov     [rbp+210h+var_288.Previous], r15
0x1800013ff  mov     [rbp+210h+var_270], 20737853h
0x180001407  mov     [rbp+210h+var_268], 14Bh
0x18000140e  call    cs:__imp_RtlPushFrame
0x180001415  nop     dword ptr [rax+rax+00h]
0x18000141a  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180001421  jnz     loc_180001665
0x180001427  mov     eax, [rsi]
0x180001429  cmp     eax, 7
0x18000142c  jnz     loc_18000156A
0x180001432  xor     ecx, ecx; dwErrCode
0x180001434  mov     [rsi+70h], r15d
0x180001438  call    cs:__imp_SetLastError
0x18000143f  nop     dword ptr [rax+rax+00h]
0x180001444  mov     rbx, [rsi+58h]
0x180001448  lea     rax, qword_18006D2C0
0x18000144f  mov     [rsp+310h+var_2B8.Context], rax
0x180001454  lea     rcx, [rsp+310h+var_2B8]; this
0x180001459  lea     rax, [rsp+310h+var_2C0]
0x18000145e  mov     [rsp+310h+var_2C0], r15d
0x180001463  mov     [rbp+210h+var_290], rax
0x180001467  mov     [rsp+310h+var_2B8.Flags], 1
0x18000146f  mov     [rsp+310h+var_2B8.Previous], r15
0x180001474  mov     [rsp+310h+var_2A0], 20737853h
0x18000147d  mov     [rsp+310h+var_298], 9ECh
0x180001485  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18000148a  test    rbx, rbx
0x18000148d  jz      loc_1800016CC
0x180001493  mov     rax, [rbx]
0x180001496  lea     r14, __ImageBase
0x18000149d  mov     r15d, [rbx+24h]
0x1800014a1  xor     edi, edi
0x1800014a3  mov     r12, [rbx+8]
0x1800014a7  xor     ebx, ebx
0x1800014a9  mov     [rsp+310h+var_2C8], rax
0x1800014ae  mov     dword ptr [rsp+310h+var_2D0], edi
0x1800014b2  cmp     rbx, 3
0x1800014b6  jnb     loc_1800015A7
0x1800014bc  mov     rdi, rbx
0x1800014bf  shl     rdi, 5
0x1800014c3  cmp     [rdi+r14+7AA30h], r15d
0x1800014cb  jz      short loc_1800014D2
0x1800014cd  inc     rbx
0x1800014d0  jmp     short loc_1800014B2
0x1800014d2  cmp     [rdi+r14+7AA40h], r12
0x1800014da  jnz     short loc_1800014CD
0x1800014dc  mov     r8, [rdi+r14+7AA38h]; unsigned __int16 *
0x1800014e4  mov     r9, r12; unsigned __int64
0x1800014e7  mov     rdx, r12; unsigned __int64
0x1800014ea  mov     [rsp+310h+var_2F0], 0; bool
0x1800014ef  mov     rcx, rax; unsigned __int16 *
0x1800014f2  call    ?FusionpCompareStrings@@YAHPEBG_K01_N@Z; FusionpCompareStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x1800014f7  test    eax, eax
0x1800014f9  jnz     loc_180001700
0x1800014ff  mov     edi, [rdi+r14+7AA48h]
0x180001507  mov     r14b, 1
0x18000150a  jmp     loc_1800015AE
0x18000150f  test    byte ptr [rax], 1
0x180001512  jz      loc_1800012E3
0x180001518  mov     rcx, rax
0x18000151b  mov     rdx, [rax+10h]
0x18000151f  test    rdx, rdx
0x180001522  jz      short loc_180001541
0x180001524  mov     rax, [rdx+8]
0x180001528  test    rax, rax
0x18000152b  jz      short loc_180001530
0x18000152d  mov     r14, rax
0x180001530  test    byte ptr [rdx], 1
0x180001533  jz      short loc_180001541
0x180001535  mov     rax, [rdx+10h]
0x180001539  test    rax, rax
0x18000153c  jz      short loc_180001541
0x18000153e  mov     rsi, rax
0x180001541  test    rcx, rcx
0x180001544  jz      loc_1800012EF
0x18000154a  cmp     qword ptr [rcx+18h], 20737853h
0x180001552  jnz     loc_1800012EF
0x180001558  mov     eax, [rcx+20h]
0x18000155b  test    eax, eax
0x18000155d  jz      loc_1800012EF
0x180001563  mov     edi, eax
0x180001565  jmp     loc_1800012EF
0x18000156a  add     eax, 0FFFFFFFEh; switch 14 cases
0x18000156d  cmp     eax, 0Dh
0x180001570  ja      def_180001588; jumptable 0000000180001588 default case, cases 3-9,11
0x180001576  lea     r14, __ImageBase
0x18000157d  mov     eax, ds:(jpt_180001588 - 180000000h)[r14+rax*4]
0x180001585  add     rax, r14
0x180001588  jmp     rax; switch jump
0x18000158e  mov     eax, [r13+0]; jumptable 0000000180001588 case 13
0x180001592  shl     rax, 5
0x180001596  add     rax, 8
0x18000159a  mov     dword ptr [rsi+58h], 1
0x1800015a1  mov     [rsi+50h], rax
0x1800015a5  jmp     short def_180001588; jumptable 0000000180001588 default case, cases 3-9,11
0x1800015a7  mov     edi, dword ptr [rsp+310h+var_2D0]
0x1800015ab  xor     r14b, r14b
0x1800015ae  mov     ebx, 1
0x1800015b3  xor     r15d, r15d
0x1800015b6  mov     [rsp+310h+var_2C0], ebx
0x1800015ba  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x1800015c1  jnz     loc_18000170A
0x1800015c7  lea     rcx, [rsp+310h+var_2B8]; Frame
0x1800015cc  call    cs:__imp_RtlPopFrame
0x1800015d3  nop     dword ptr [rax+rax+00h]
0x1800015d8  test    ebx, ebx
0x1800015da  jz      loc_180001739
0x1800015e0  test    r14b, r14b
0x1800015e3  jz      short loc_180001600; jumptable 0000000180001588 case 2
0x1800015e5  cmp     edi, 2
0x1800015e8  jnz     loc_18000174A
0x1800015ee  mov     r8d, edi
0x1800015f1  mov     rdx, rsi
0x1800015f4  mov     rcx, r13
0x1800015f7  call    ?ParseElement@CCompatibilityInfo@@AEAAHPEAU_ACTCTXCTB_CBELEMENTPARSED@@W4AppCompatSupportType@@@Z; CCompatibilityInfo::ParseElement(_ACTCTXCTB_CBELEMENTPARSED *,AppCompatSupportType)
0x1800015fc  test    eax, eax
0x1800015fe  jz      short def_180001588; jumptable 0000000180001588 default case, cases 3-9,11
0x180001600  mov     dword ptr [rsi+70h], 1; jumptable 0000000180001588 case 2
0x180001607  cmp     cs:g_FusionEnterExitTracingEnabled, 0; jumptable 0000000180001588 default case, cases 3-9,11
0x18000160e  jnz     loc_180001762
0x180001614  lea     rcx, [rbp+210h+var_288]; Frame
0x180001618  call    cs:__imp_RtlPopFrame
0x18000161f  nop     dword ptr [rax+rax+00h]
0x180001624  cmp     dword ptr [rsi], 10h
0x180001627  jz      short loc_180001636
0x180001629  mov     r13, [rsp+310h+var_10]
0x180001631  jmp     loc_180001368
0x180001636  test    r13, r13
0x180001639  jz      short loc_180001629
0x18000163b  mov     rcx, [r13+8]; void *
0x18000163f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001644  mov     rcx, r13; void *
0x180001647  mov     [r13+8], r15
0x18000164b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001650  jmp     short loc_180001629
0x180001652  mov     dword ptr [rsi+50h], 1; jumptable 0000000180001588 cases 12,15
0x180001659  jmp     short def_180001588; jumptable 0000000180001588 default case, cases 3-9,11
0x18000165b  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180001660  jmp     loc_180001263
0x180001665  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18000166a  jmp     loc_180001427
0x18000166f  mov     rbx, [rsi+58h]; jumptable 0000000180001588 case 14
0x180001673  mov     eax, [r13+0]
0x180001677  mov     [rbx], eax
0x180001679  lea     rcx, [rbx+8]; void *
0x18000167d  mov     r8d, [r13+0]
0x180001681  mov     rdx, [r13+8]; Src
0x180001685  shl     r8, 5; Size
0x180001689  call    memcpy_0
0x18000168e  mov     rdx, [rsi+48h]
0x180001692  mov     rcx, rbx; struct _ACTIVATION_CONTEXT_COMPATIBILITY_INFORMATION *
0x180001695  add     rdx, 10D2h; struct _SUPPORTED_OS_INFO *
0x18000169c  call    ?FillSupportedOsInfo@@YAXPEAU_ACTIVATION_CONTEXT_COMPATIBILITY_INFORMATION@@PEAU_SUPPORTED_OS_INFO@@@Z; FillSupportedOsInfo(_ACTIVATION_CONTEXT_COMPATIBILITY_INFORMATION *,_SUPPORTED_OS_INFO *)
0x1800016a1  mov     rdx, [rsi+48h]
0x1800016a5  mov     rcx, rbx; struct _ACTIVATION_CONTEXT_COMPATIBILITY_INFORMATION *
0x1800016a8  add     rdx, 10D8h; struct _MAXVERSIONTESTED_INFO *
0x1800016af  call    ?FillMaxVersionTestedInfo@@YAXPEAU_ACTIVATION_CONTEXT_COMPATIBILITY_INFORMATION@@PEAU_MAXVERSIONTESTED_INFO@@@Z; FillMaxVersionTestedInfo(_ACTIVATION_CONTEXT_COMPATIBILITY_INFORMATION *,_MAXVERSIONTESTED_INFO *)
0x1800016b4  mov     dword ptr [rsi+60h], 1
0x1800016bb  jmp     def_180001588; jumptable 0000000180001588 default case, cases 3-9,11
0x1800016c0  mov     dword ptr [rsi+58h], 1; jumptable 0000000180001588 case 10
0x1800016c7  jmp     def_180001588; jumptable 0000000180001588 default case, cases 3-9,11
0x1800016cc  mov     edi, r15d
0x1800016cf  mov     [rsp+310h+var_298], 9F2h
0x1800016d7  xor     r14b, r14b
0x1800016da  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x1800016df  mov     ecx, 57h ; 'W'; dwErrCode
0x1800016e4  call    cs:__imp_SetLastError
0x1800016eb  nop     dword ptr [rax+rax+00h]
0x1800016f0  mov     rax, [rbp+210h+var_290]
0x1800016f4  mov     [rax], r15d
0x1800016f7  mov     ebx, [rsp+310h+var_2C0]
0x1800016fb  jmp     loc_1800015BA
0x180001700  mov     rax, [rsp+310h+var_2C8]
0x180001705  jmp     loc_1800014CD
0x18000170a  mov     rax, [rbp+210h+var_290]
0x18000170e  cmp     dword ptr [rax], 0
0x180001711  jz      short loc_18000171F
0x180001713  xor     ecx, ecx; char *
0x180001715  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18000171a  jmp     loc_1800015C7
0x18000171f  call    cs:__imp_GetLastError
0x180001726  nop     dword ptr [rax+rax+00h]
0x18000172b  mov     ecx, eax; unsigned int
0x18000172d  xor     edx, edx; Format
0x18000172f  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180001734  jmp     loc_1800015C7
0x180001739  lea     rcx, off_18007AA10; struct _CALL_SITE_INFO *
0x180001740  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180001745  jmp     def_180001588; jumptable 0000000180001588 default case, cases 3-9,11
0x18000174a  mov     eax, edi
0x18000174c  test    edi, edi
0x18000174e  jz      loc_1800015EE
0x180001754  cmp     eax, 1
0x180001757  jnz     def_180001588; jumptable 0000000180001588 default case, cases 3-9,11
0x18000175d  jmp     loc_1800015EE
0x180001762  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x180001767  jmp     loc_180001614
0x18000176c  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x180001771  jmp     loc_1800013A5
```
