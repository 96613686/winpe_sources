# SxspDllRedirectionContributorCallback(_ACTCTXCTB_CALLBACK_DATA *)

- ea: `0x180020550`
- end: `0x180020818`
- name: `?SxspDllRedirectionContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z`
- size: `712`
- prototype: `void __fastcall(union _ACTCTXCTB_CALLBACK_DATA *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callees

- `0x18001c2c8`
- `0x18001ef5c`
- `0x180020550`
- `0x180020820`
- `0x18002089c`
- `0x180022f60`
- `0x1800278b0`
- `0x18005cf40`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180020621`
- `ntdll!RtlPopFrame` at `0x180020621`
- `ntdll!_snprintf_s` at `0x18002075a`
- `ntdll!_snprintf_s` at `0x18002075a`
- `ntdll!RtlGetFrame` at `0x180020701`
- `ntdll!RtlGetFrame` at `0x180020701`
- `ntdll!RtlPushFrame` at `0x1800205a9`
- `ntdll!RtlPushFrame` at `0x1800205a9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180020773`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180020773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020722`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020781`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020792`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020781`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020792`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002065f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002065f`

## pseudocode

```c
void __fastcall SxspDllRedirectionContributorCallback(union _ACTCTXCTB_CALLBACK_DATA *a1)
{
  struct _STRING_SECTION_GENERATION_CONTEXT **v2; // rdi
  _QWORD *v3; // rax
  _QWORD *v4; // rsi
  int Previous; // edi
  const char *v6; // rsi
  const char *FrameName; // rbp
  PTEB_ACTIVE_FRAME v8; // rax
  PTEB_ACTIVE_FRAME v9; // rcx
  DWORD LastError; // ebx
  PCTEB_ACTIVE_FRAME_CONTEXT Context; // rdx
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+40h] [rbp-258h] BYREF
  __int64 v13; // [rsp+58h] [rbp-240h]
  int v14; // [rsp+60h] [rbp-238h]
  char Buffer[512]; // [rsp+70h] [rbp-228h] BYREF

  Frame.Flags = 1;
  Frame.Previous = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D1A0;
  v13 = 544438355;
  v14 = 68;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( *(_DWORD *)a1 != 2 )
    goto LABEL_4;
  *((_DWORD *)a1 + 28) = 0;
  if ( *((_QWORD *)a1 + 5) )
    goto LABEL_4;
  v3 = HeapAlloc(g_hHeap, 0, 0x450u);
  v4 = v3;
  if ( !v3 )
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
LABEL_15:
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
        goto LABEL_5;
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
    goto LABEL_15;
  }
  *v3 = 0;
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v3 + 1);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v4 + 22);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v4 + 43);
  CGenericStringBuffer<128,CUnicodeCharTraits>::CGenericStringBuffer<128,CUnicodeCharTraits>(v4 + 64);
  CGenericStringBuffer<128,CUnicodeCharTraits>::CGenericStringBuffer<128,CUnicodeCharTraits>(v4 + 101);
  *((_QWORD *)a1 + 5) = v4;
LABEL_4:
  v2 = (struct _STRING_SECTION_GENERATION_CONTEXT **)*((_QWORD *)a1 + 5);
  CDllRedir::ContributorCallback(v2, a1);
  if ( *(_DWORD *)a1 == 16 && v2 )
  {
    CDllRedir::_ContributorCallbackLocalsStruct::~_ContributorCallbackLocalsStruct((CDllRedir::_ContributorCallbackLocalsStruct *)(v2 + 1));
    operator delete(v2);
  }
LABEL_5:
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallExit();
  RtlPopFrame(&Frame);
}

```

## disassembly

```asm
0x180020550  mov     r11, rsp
0x180020553  sub     rsp, 298h
0x18002055a  mov     rax, cs:__security_cookie
0x180020561  xor     rax, rsp
0x180020564  mov     [rsp+298h+var_28], rax
0x18002056c  mov     [r11+10h], rbx
0x180020570  lea     rax, qword_18006D1A0
0x180020577  mov     [r11-10h], r14
0x18002057b  mov     rbx, rcx
0x18002057e  xor     r14d, r14d
0x180020581  mov     [rsp+298h+Frame.Flags], 1
0x180020589  lea     rcx, [rsp+298h+Frame]; Frame
0x18002058e  mov     [rsp+298h+Frame.Previous], r14
0x180020593  mov     [rsp+298h+Frame.Context], rax
0x180020598  mov     [rsp+298h+var_240], 20737853h
0x1800205a1  mov     [rsp+298h+var_238], 44h ; 'D'
0x1800205a9  call    cs:__imp_RtlPushFrame
0x1800205b0  nop     dword ptr [rax+rax+00h]
0x1800205b5  cmp     cs:g_FusionEnterExitTracingEnabled, r14b
0x1800205bc  jnz     loc_1800206B8
0x1800205c2  cmp     dword ptr [rbx], 2
0x1800205c5  mov     [rsp+298h+arg_18], rsi
0x1800205cd  mov     [rsp+298h+var_8], rdi
0x1800205d5  jz      short loc_180020646
0x1800205d7  mov     rdi, [rbx+28h]
0x1800205db  mov     rdx, rbx; union _ACTCTXCTB_CALLBACK_DATA *
0x1800205de  mov     rcx, rdi; this
0x1800205e1  call    ?ContributorCallback@CDllRedir@@QEAAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z; CDllRedir::ContributorCallback(_ACTCTXCTB_CALLBACK_DATA *)
0x1800205e6  cmp     dword ptr [rbx], 10h
0x1800205e9  jz      loc_1800206C2
0x1800205ef  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x1800205f6  mov     r14, [rsp+298h+var_10]
0x1800205fe  mov     rdi, [rsp+298h+var_8]
0x180020606  mov     rsi, [rsp+298h+arg_18]
0x18002060e  mov     rbx, [rsp+298h+arg_8]
0x180020616  jnz     loc_18002080E
0x18002061c  lea     rcx, [rsp+298h+Frame]; Frame
0x180020621  call    cs:__imp_RtlPopFrame
0x180020628  nop     dword ptr [rax+rax+00h]
0x18002062d  mov     rcx, [rsp+298h+var_28]
0x180020635  xor     rcx, rsp; StackCookie
0x180020638  call    __security_check_cookie
0x18002063d  add     rsp, 298h
0x180020644  retn
0x180020646  mov     [rbx+70h], r14d
0x18002064a  cmp     [rbx+28h], r14
0x18002064e  jnz     short loc_1800205D7
0x180020650  mov     rcx, cs:g_hHeap; hHeap
0x180020657  xor     edx, edx; dwFlags
0x180020659  mov     r8d, 450h; dwBytes
0x18002065f  call    cs:__imp_HeapAlloc
0x180020666  nop     dword ptr [rax+rax+00h]
0x18002066b  mov     rsi, rax
0x18002066e  test    rax, rax
0x180020671  jz      short loc_1800206E1
0x180020673  lea     rcx, [rax+8]
0x180020677  mov     [rax], r14
0x18002067a  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18002067f  lea     rcx, [rsi+0B0h]
0x180020686  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18002068b  lea     rcx, [rsi+158h]
0x180020692  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x180020697  lea     rcx, [rsi+200h]
0x18002069e  call    ??0?$CGenericStringBuffer@$0IA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<128,CUnicodeCharTraits>::CGenericStringBuffer<128,CUnicodeCharTraits>(void)
0x1800206a3  lea     rcx, [rsi+328h]
0x1800206aa  call    ??0?$CGenericStringBuffer@$0IA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<128,CUnicodeCharTraits>::CGenericStringBuffer<128,CUnicodeCharTraits>(void)
0x1800206af  mov     [rbx+28h], rsi
0x1800206b3  jmp     loc_1800205D7
0x1800206b8  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x1800206bd  jmp     loc_1800205C2
0x1800206c2  test    rdi, rdi
0x1800206c5  jz      loc_1800205EF
0x1800206cb  lea     rcx, [rdi+8]; this
0x1800206cf  call    ??1_ContributorCallbackLocalsStruct@CDllRedir@@QEAA@XZ; CDllRedir::_ContributorCallbackLocalsStruct::~_ContributorCallbackLocalsStruct(void)
0x1800206d4  mov     rcx, rdi; void *
0x1800206d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800206dc  jmp     loc_1800205EF
0x1800206e1  mov     [rsp+298h+arg_10], rbp
0x1800206e9  mov     edi, r14d
0x1800206ec  mov     [rsp+298h+var_18], r15
0x1800206f4  lea     r15, byte_18008517D
0x1800206fb  mov     rsi, r15
0x1800206fe  mov     rbp, r15
0x180020701  call    cs:__imp_RtlGetFrame
0x180020708  nop     dword ptr [rax+rax+00h]
0x18002070d  test    rax, rax
0x180020710  jnz     loc_1800207B3
0x180020716  mov     rcx, r14
0x180020719  test    rax, rax
0x18002071c  jnz     loc_1800207BF
0x180020722  call    cs:__imp_GetLastError
0x180020729  nop     dword ptr [rax+rax+00h]
0x18002072e  mov     [rsp+298h+var_260], r15
0x180020733  lea     r9, Format; "%s(%d): Memory allocation failed in fun"...
0x18002073a  mov     [rsp+298h+var_268], rbp
0x18002073f  lea     rcx, [rsp+298h+Buffer]; Buffer
0x180020744  mov     [rsp+298h+var_270], edi
0x180020748  mov     edx, 200h; BufferCount
0x18002074d  mov     r8d, 1FFh; MaxCount
0x180020753  mov     [rsp+298h+var_278], rsi
0x180020758  mov     ebx, eax
0x18002075a  call    cs:__imp__snprintf_s
0x180020761  nop     dword ptr [rax+rax+00h]
0x180020766  lea     rcx, [rsp+298h+Buffer]; lpOutputString
0x18002076b  mov     [rsp+298h+var_29], r14b
0x180020773  call    cs:__imp_OutputDebugStringA
0x18002077a  nop     dword ptr [rax+rax+00h]
0x18002077f  mov     ecx, ebx; dwErrCode
0x180020781  call    cs:__imp_SetLastError
0x180020788  nop     dword ptr [rax+rax+00h]
0x18002078d  mov     ecx, 0Eh; dwErrCode
0x180020792  call    cs:__imp_SetLastError
0x180020799  nop     dword ptr [rax+rax+00h]
0x18002079e  mov     r15, [rsp+298h+var_18]
0x1800207a6  mov     rbp, [rsp+298h+arg_10]
0x1800207ae  jmp     loc_1800205EF
0x1800207b3  test    byte ptr [rax], 1
0x1800207b6  jz      loc_180020716
0x1800207bc  mov     rcx, rax
0x1800207bf  mov     rdx, [rax+10h]
0x1800207c3  test    rdx, rdx
0x1800207c6  jz      short loc_1800207E5
0x1800207c8  mov     rax, [rdx+8]
0x1800207cc  test    rax, rax
0x1800207cf  jz      short loc_1800207D4
0x1800207d1  mov     rbp, rax
0x1800207d4  test    byte ptr [rdx], 1
0x1800207d7  jz      short loc_1800207E5
0x1800207d9  mov     rax, [rdx+10h]
0x1800207dd  test    rax, rax
0x1800207e0  jz      short loc_1800207E5
0x1800207e2  mov     rsi, rax
0x1800207e5  test    rcx, rcx
0x1800207e8  jz      loc_180020722
0x1800207ee  cmp     qword ptr [rcx+18h], 20737853h
0x1800207f6  jnz     loc_180020722
0x1800207fc  mov     eax, [rcx+20h]
0x1800207ff  test    eax, eax
0x180020801  jz      loc_180020722
0x180020807  mov     edi, eax
0x180020809  jmp     loc_180020722
0x18002080e  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x180020813  jmp     loc_18002061C
```
