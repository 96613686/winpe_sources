# SxspClrInteropContributorCallback(_ACTCTXCTB_CALLBACK_DATA *)

- ea: `0x180036dc0`
- end: `0x180037316`
- name: `?SxspClrInteropContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z`
- size: `1366`
- prototype: `void __fastcall(union _ACTCTXCTB_CALLBACK_DATA *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800054d0`
- `0x1800054f8`
- `0x1800055c0`
- `0x180005f60`
- `0x180007044`
- `0x18000dffc`
- `0x18001c2c8`
- `0x180022f60`
- `0x180036914`
- `0x180036dc0`
- `0x18003731c`
- `0x18005cf40`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180036f60`
- `ntdll!RtlCompareUnicodeString` at `0x180036f60`
- `ntdll!RtlPopFrame` at `0x180036fe6`
- `ntdll!RtlPopFrame` at `0x180037030`
- `ntdll!RtlPopFrame` at `0x180036fe6`
- `ntdll!RtlPopFrame` at `0x180037030`
- `ntdll!RtlPushFrame` at `0x180036e1b`
- `ntdll!RtlPushFrame` at `0x180036eb5`
- `ntdll!RtlPushFrame` at `0x180036e1b`
- `ntdll!RtlPushFrame` at `0x180036eb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036e71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036f99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037084`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800370f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037150`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800371d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037200`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037271`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036e71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036f99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037084`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800370f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037150`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800371d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037200`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037271`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003716b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003716b`

## pseudocode

```c
void __fastcall SxspClrInteropContributorCallback(union _ACTCTXCTB_CALLBACK_DATA *a1)
{
  char v2; // di
  __int64 v3; // r14
  CDequeBase *v4; // r12
  int v5; // eax
  __int64 v6; // rbx
  const char *v7; // rcx
  WCHAR *v8; // rax
  int v9; // r15d
  __int64 v10; // r13
  __int64 v11; // rbx
  DWORD v12; // ecx
  int v13; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned __int64 *v17; // r9
  bool v18; // zf
  _QWORD *v19; // rax
  void *v20; // rdi
  unsigned int v21; // edx
  DWORD v22; // eax
  DWORD LastError; // ebx
  struct _GUID_SECTION_GENERATION_CONTEXT *v24; // [rsp+28h] [rbp-69h] BYREF
  WCHAR *v25; // [rsp+30h] [rbp-61h]
  UNICODE_STRING String2; // [rsp+38h] [rbp-59h] BYREF
  UNICODE_STRING String1; // [rsp+48h] [rbp-49h] BYREF
  int v28; // [rsp+58h] [rbp-39h] BYREF
  struct _TEB_ACTIVE_FRAME v29; // [rsp+60h] [rbp-31h] BYREF
  __int64 v30; // [rsp+78h] [rbp-19h]
  int v31; // [rsp+80h] [rbp-11h]
  int *v32; // [rsp+88h] [rbp-9h]
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+90h] [rbp-1h] BYREF
  __int64 v34; // [rsp+A8h] [rbp+17h]
  int v35; // [rsp+B0h] [rbp+1Fh]

  v2 = 0;
  Frame.Previous = 0;
  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006FB70;
  v34 = 544438355;
  v35 = 87;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v3 = *((_QWORD *)a1 + 5);
  v4 = 0;
  v24 = (struct _GUID_SECTION_GENERATION_CONTEXT *)v3;
  if ( v3 )
    v4 = *(CDequeBase **)(v3 + 8);
  v5 = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 == 2 )
  {
    *((_DWORD *)a1 + 28) = 0;
    if ( !v4 && !v3 )
    {
      SetLastError(0);
      v19 = HeapAlloc(g_hHeap, 0, 0x28u);
      v20 = v19;
      if ( !v19 )
      {
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006FBB0);
        goto LABEL_20;
      }
      *((_DWORD *)v19 + 6) = 0;
      v19[4] = 0;
      *v19 = v19;
      v19[1] = v19;
      v19[2] = v19;
      SetLastError(0);
      if ( (unsigned int)CGSGenCtx::Create(
                           &v24,
                           v21,
                           (int (*)(void *, unsigned int, void *))SxspClrInteropGuidSectionGenerationCallback,
                           v20) )
      {
        *((_QWORD *)a1 + 5) = v24;
        *((_DWORD *)a1 + 28) = 1;
        goto LABEL_20;
      }
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007BE60);
      LastError = GetLastError();
      CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::~CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>(v20);
      operator delete(v20);
      v12 = LastError;
LABEL_19:
      SetLastError(v12);
      goto LABEL_20;
    }
LABEL_18:
    v12 = 1359;
    goto LABEL_19;
  }
  if ( v5 != 7 )
  {
    v14 = v5 - 12;
    if ( !v14 )
    {
      *((_DWORD *)a1 + 20) = 0;
      if ( v3 )
        SetLastError(0);
      *((_DWORD *)a1 + 20) = 1;
      goto LABEL_20;
    }
    v15 = v14 - 1;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        if ( v16 == 2 )
        {
          SxsDestroyGuidSectionGenerationContext((void *)v3);
          if ( v4 )
          {
            CDeque<_CLR_SURROGATE_ENTRY,0>::ClearAndDeleteAll(v4);
            CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::~CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>(v4);
            operator delete(v4);
          }
        }
        goto LABEL_20;
      }
      *((_DWORD *)a1 + 24) = 0;
      if ( v3 && *((_DWORD *)a1 + 1) == 1 )
      {
        SetLastError(0);
        if ( (unsigned int)CGSGenCtx::GetSectionData((CGSGenCtx *)v3, *((_QWORD *)a1 + 10), *((void **)a1 + 11), v17) )
          *((_DWORD *)a1 + 24) = 1;
        else
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007BE80);
        goto LABEL_20;
      }
    }
    else
    {
      v18 = *((_DWORD *)a1 + 1) == 1;
      *((_DWORD *)a1 + 22) = 0;
      if ( v18 && v3 )
      {
        SetLastError(0);
        if ( (unsigned int)CGSGenCtx::GetSectionSize((CGSGenCtx *)v3, (unsigned __int64 *)a1 + 10) )
          *((_DWORD *)a1 + 22) = 1;
        else
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007BE40);
        goto LABEL_20;
      }
    }
    goto LABEL_18;
  }
  *((_DWORD *)a1 + 28) = 0;
  SetLastError(0);
  v6 = *((_QWORD *)a1 + 11);
  v29.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D2C0;
  v28 = 0;
  v32 = &v28;
  v29.Flags = 1;
  v29.Previous = 0;
  v30 = 544438355;
  v31 = 2540;
  RtlPushFrame(&v29);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( v6 )
  {
    v8 = *(WCHAR **)v6;
    v9 = *(_DWORD *)(v6 + 36);
    v10 = *(_QWORD *)(v6 + 8);
    v11 = 0;
    v25 = v8;
    LODWORD(v24) = 0;
    while ( !v11 )
    {
      if ( v9 == 2 && v10 == 87 )
      {
        String1.Buffer = v8;
        *(&String2.MaximumLength + 2) = 0;
        *(_QWORD *)&String1.Length = 11403438;
        String2.Length = 174;
        *(_DWORD *)&String2.MaximumLength = 174;
        String2.Buffer = L"urn:schemas-microsoft-com:asm.v1^assembly!urn:schemas-microsoft-com:asm.v1^clrSurrogate";
        if ( !RtlCompareUnicodeString(&String1, &String2, 0) )
        {
          v2 = 1;
          goto LABEL_24;
        }
        v8 = v25;
      }
      v11 = 1;
    }
    v2 = 0;
LABEL_24:
    v13 = 1;
    v28 = 1;
  }
  else
  {
    v31 = 2546;
    FusionpTraceParameterCheck(v7);
    SetLastError(0x57u);
    *v32 = 0;
    v13 = v28;
  }
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v32 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v22 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v22, 0);
    }
  }
  RtlPopFrame(&v29);
  if ( v13 )
  {
    if ( v2 )
    {
      if ( SxspClrSurrogateAddSurrogate(a1, v4, (struct _GUID_SECTION_GENERATION_CONTEXT *)v3) )
        *((_DWORD *)a1 + 28) = 1;
    }
    else
    {
      *((_DWORD *)a1 + 28) = 1;
    }
  }
  else
  {
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007BE20);
  }
LABEL_20:
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallExit();
  RtlPopFrame(&Frame);
}

```

## disassembly

```asm
0x180036dc0  mov     r11, rsp
0x180036dc3  push    rbp
0x180036dc4  lea     rbp, [r11-5Fh]
0x180036dc8  sub     rsp, 0E0h
0x180036dcf  mov     rax, cs:__security_cookie
0x180036dd6  xor     rax, rsp
0x180036dd9  mov     [rbp+57h+var_30], rax
0x180036ddd  mov     [r11+18h], rsi
0x180036de1  lea     rax, qword_18006FB70
0x180036de8  mov     [r11+20h], rdi
0x180036dec  mov     rsi, rcx
0x180036def  mov     [r11-10h], r12
0x180036df3  lea     rcx, [rbp+57h+Frame]; Frame
0x180036df7  xor     edi, edi
0x180036df9  mov     [r11-20h], r14
0x180036dfd  mov     [rbp+57h+Frame.Previous], rdi
0x180036e01  mov     [rbp+57h+Frame.Flags], 1
0x180036e08  mov     [rbp+57h+Frame.Context], rax
0x180036e0c  mov     [rbp+57h+var_40], 20737853h
0x180036e14  mov     [rbp+57h+var_38], 57h ; 'W'
0x180036e1b  call    cs:__imp_RtlPushFrame
0x180036e22  nop     dword ptr [rax+rax+00h]
0x180036e27  cmp     cs:g_FusionEnterExitTracingEnabled, dil
0x180036e2e  jnz     loc_18003713B
0x180036e34  mov     r14, [rsi+28h]
0x180036e38  mov     r12, rdi
0x180036e3b  mov     [rbp+57h+var_C0], r14
0x180036e3f  test    r14, r14
0x180036e42  jz      short loc_180036E48
0x180036e44  mov     r12, [r14+8]
0x180036e48  mov     eax, [rsi]
0x180036e4a  mov     [rsp+0E0h+arg_8], rbx
0x180036e52  mov     [rsp+0E0h+var_20], r15
0x180036e5a  cmp     eax, 2
0x180036e5d  jz      loc_180036F88
0x180036e63  cmp     eax, 7
0x180036e66  jnz     loc_180037055
0x180036e6c  xor     ecx, ecx; dwErrCode
0x180036e6e  mov     [rsi+70h], edi
0x180036e71  call    cs:__imp_SetLastError
0x180036e78  nop     dword ptr [rax+rax+00h]
0x180036e7d  mov     rbx, [rsi+58h]
0x180036e81  lea     rax, qword_18006D2C0
0x180036e88  mov     [rbp+57h+var_88.Context], rax
0x180036e8c  lea     rcx, [rbp+57h+var_88]; Frame
0x180036e90  lea     rax, [rbp+57h+var_90]
0x180036e94  mov     [rbp+57h+var_90], edi
0x180036e97  mov     [rbp+57h+var_60], rax
0x180036e9b  mov     [rbp+57h+var_88.Flags], 1
0x180036ea2  mov     [rbp+57h+var_88.Previous], rdi
0x180036ea6  mov     [rbp+57h+var_70], 20737853h
0x180036eae  mov     [rbp+57h+var_68], 9ECh
0x180036eb5  call    cs:__imp_RtlPushFrame
0x180036ebc  nop     dword ptr [rax+rax+00h]
0x180036ec1  cmp     cs:g_FusionEnterExitTracingEnabled, dil
0x180036ec8  jnz     loc_180037190
0x180036ece  test    rbx, rbx
0x180036ed1  jz      loc_18003725D
0x180036ed7  mov     rax, [rbx]
0x180036eda  lea     rdx, qword_18006FB90
0x180036ee1  mov     r15d, [rbx+24h]
0x180036ee5  mov     [rsp+0E0h+var_10], r13
0x180036eed  mov     r13, [rbx+8]
0x180036ef1  xor     ebx, ebx
0x180036ef3  mov     [rbp+57h+var_B8], rax
0x180036ef7  mov     dword ptr [rbp+57h+var_C0], edi
0x180036efa  nop     word ptr [rax+rax+00h]
0x180036f00  cmp     rbx, 1
0x180036f04  jnb     loc_180037008
0x180036f0a  mov     rdi, rbx
0x180036f0d  shl     rdi, 5
0x180036f11  cmp     [rdi+rdx], r15d
0x180036f15  jz      short loc_180036F1C
0x180036f17  inc     rbx
0x180036f1a  jmp     short loc_180036F00
0x180036f1c  cmp     [rdi+rdx+10h], r13
0x180036f21  jnz     short loc_180036F17
0x180036f23  xorps   xmm0, xmm0
0x180036f26  movzx   ecx, r13w
0x180036f2a  add     cx, cx
0x180036f2d  xorps   xmm1, xmm1
0x180036f30  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x180036f34  mov     [rbp+57h+String1.Buffer], rax
0x180036f38  xor     r8d, r8d; CaseInsensitive
0x180036f3b  mov     rax, [rdi+rdx+8]
0x180036f40  lea     rdx, [rbp+57h+String2]; String2
0x180036f44  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x180036f48  mov     [rbp+57h+String1.Length], cx
0x180036f4c  mov     [rbp+57h+String1.MaximumLength], cx
0x180036f50  mov     [rbp+57h+String2.Length], cx
0x180036f54  mov     [rbp+57h+String2.MaximumLength], cx
0x180036f58  lea     rcx, [rbp+57h+String1]; String1
0x180036f5c  mov     [rbp+57h+String2.Buffer], rax
0x180036f60  call    cs:__imp_RtlCompareUnicodeString
0x180036f67  nop     dword ptr [rax+rax+00h]
0x180036f6c  test    eax, eax
0x180036f6e  jnz     loc_18003728B
0x180036f74  lea     r15, qword_18006FB90
0x180036f7b  mov     r15d, [rdi+r15+18h]
0x180036f80  mov     dil, 1
0x180036f83  jmp     loc_18003700F
0x180036f88  mov     [rsi+70h], edi
0x180036f8b  test    r12, r12
0x180036f8e  jz      loc_180037145
0x180036f94  mov     ecx, 54Fh; dwErrCode
0x180036f99  call    cs:__imp_SetLastError
0x180036fa0  nop     dword ptr [rax+rax+00h]
0x180036fa5  mov     r15, [rsp+0E0h+var_20]
0x180036fad  mov     r14, [rsp+0E0h+var_18]
0x180036fb5  mov     r12, [rsp+0D8h]
0x180036fbd  mov     rdi, [rsp+0E0h+arg_18]
0x180036fc5  mov     rsi, [rsp+0E0h+arg_10]
0x180036fcd  mov     rbx, [rsp+0E0h+arg_8]
0x180036fd5  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180036fdc  jnz     loc_18003730C
0x180036fe2  lea     rcx, [rbp+57h+Frame]; Frame
0x180036fe6  call    cs:__imp_RtlPopFrame
0x180036fed  nop     dword ptr [rax+rax+00h]
0x180036ff2  mov     rcx, [rbp+57h+var_30]
0x180036ff6  xor     rcx, rsp; StackCookie
0x180036ff9  call    __security_check_cookie
0x180036ffe  add     rsp, 0E0h
0x180037005  pop     rbp
0x180037006  retn
0x180037008  mov     r15d, dword ptr [rbp+57h+var_C0]
0x18003700c  xor     dil, dil
0x18003700f  mov     r13, [rsp+0E0h+var_10]
0x180037017  mov     ebx, 1
0x18003701c  mov     [rbp+57h+var_90], ebx
0x18003701f  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180037026  jnz     loc_18003729B
0x18003702c  lea     rcx, [rbp+57h+var_88]; Frame
0x180037030  call    cs:__imp_RtlPopFrame
0x180037037  nop     dword ptr [rax+rax+00h]
0x18003703c  test    ebx, ebx
0x18003703e  jz      loc_1800372CA
0x180037044  test    dil, dil
0x180037047  jnz     short loc_1800370B4
0x180037049  mov     dword ptr [rsi+70h], 1
0x180037050  jmp     loc_180036FA5
0x180037055  sub     eax, 0Ch
0x180037058  jz      loc_180037123
0x18003705e  sub     eax, 1
0x180037061  jz      short loc_1800370DF
0x180037063  sub     eax, 1
0x180037066  jnz     loc_18003719A
0x18003706c  mov     [rsi+60h], edi
0x18003706f  test    r14, r14
0x180037072  jz      loc_180036F94
0x180037078  cmp     dword ptr [rsi+4], 1
0x18003707c  jnz     loc_180036F94
0x180037082  xor     ecx, ecx; dwErrCode
0x180037084  call    cs:__imp_SetLastError
0x18003708b  nop     dword ptr [rax+rax+00h]
0x180037090  mov     r8, [rsi+58h]; void *
0x180037094  mov     rcx, r14; this
0x180037097  mov     rdx, [rsi+50h]; unsigned __int64
0x18003709b  call    ?GetSectionData@CGSGenCtx@@QEAAH_KPEAXPEA_K@Z; CGSGenCtx::GetSectionData(unsigned __int64,void *,unsigned __int64 *)
0x1800370a0  test    eax, eax
0x1800370a2  jz      loc_18003723B
0x1800370a8  mov     dword ptr [rsi+60h], 1
0x1800370af  jmp     loc_180036FA5
0x1800370b4  test    r15d, r15d
0x1800370b7  jnz     loc_180036FA5
0x1800370bd  mov     r8, r14; struct _GUID_SECTION_GENERATION_CONTEXT *
0x1800370c0  mov     rdx, r12; struct _CLR_GLOBAL_CONTEXT *
0x1800370c3  mov     rcx, rsi; struct _ACTCTXCTB_CBELEMENTPARSED *
0x1800370c6  call    ?SxspClrSurrogateAddSurrogate@@YAHPEAU_ACTCTXCTB_CBELEMENTPARSED@@PEAU_CLR_GLOBAL_CONTEXT@@PEAU_GUID_SECTION_GENERATION_CONTEXT@@@Z; SxspClrSurrogateAddSurrogate(_ACTCTXCTB_CBELEMENTPARSED *,_CLR_GLOBAL_CONTEXT *,_GUID_SECTION_GENERATION_CONTEXT *)
0x1800370cb  test    eax, eax
0x1800370cd  jz      loc_180036FA5
0x1800370d3  mov     dword ptr [rsi+70h], 1
0x1800370da  jmp     loc_180036FA5
0x1800370df  cmp     dword ptr [rsi+4], 1
0x1800370e3  mov     [rsi+58h], edi
0x1800370e6  jnz     loc_180036F94
0x1800370ec  test    r14, r14
0x1800370ef  jz      loc_180036F94
0x1800370f5  xor     ecx, ecx; dwErrCode
0x1800370f7  call    cs:__imp_SetLastError
0x1800370fe  nop     dword ptr [rax+rax+00h]
0x180037103  lea     rdx, [rsi+50h]; unsigned __int64 *
0x180037107  mov     rcx, r14; this
0x18003710a  call    ?GetSectionSize@CGSGenCtx@@QEAAHPEA_K@Z; CGSGenCtx::GetSectionSize(unsigned __int64 *)
0x18003710f  test    eax, eax
0x180037111  jz      loc_18003724C
0x180037117  mov     dword ptr [rsi+58h], 1
0x18003711e  jmp     loc_180036FA5
0x180037123  mov     [rsi+50h], edi
0x180037126  test    r14, r14
0x180037129  jnz     loc_1800371D1
0x18003712f  mov     dword ptr [rsi+50h], 1
0x180037136  jmp     loc_180036FA5
0x18003713b  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180037140  jmp     loc_180036E34
0x180037145  test    r14, r14
0x180037148  jnz     loc_180036F94
0x18003714e  xor     ecx, ecx; dwErrCode
0x180037150  call    cs:__imp_SetLastError
0x180037157  nop     dword ptr [rax+rax+00h]
0x18003715c  mov     rcx, cs:g_hHeap; hHeap
0x180037163  xor     edx, edx; dwFlags
0x180037165  mov     r8d, 28h ; '('; dwBytes
0x18003716b  call    cs:__imp_HeapAlloc
0x180037172  nop     dword ptr [rax+rax+00h]
0x180037177  mov     rdi, rax
0x18003717a  test    rax, rax
0x18003717d  jnz     short loc_1800371E4
0x18003717f  lea     rcx, off_18006FBB0; struct _CALL_SITE_INFO *
0x180037186  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18003718b  jmp     loc_180036FA5
0x180037190  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180037195  jmp     loc_180036ECE
0x18003719a  cmp     eax, 2
0x18003719d  jnz     loc_180036FA5
0x1800371a3  mov     rcx, r14; void *
0x1800371a6  call    SxsDestroyGuidSectionGenerationContext
0x1800371ab  test    r12, r12
0x1800371ae  jz      loc_180036FA5
0x1800371b4  mov     rcx, r12; this
0x1800371b7  call    ?ClearAndDeleteAll@?$CDeque@U_CLR_SURROGATE_ENTRY@@$0A@@@QEAAXXZ; CDeque<_CLR_SURROGATE_ENTRY,0>::ClearAndDeleteAll(void)
0x1800371bc  mov     rcx, r12
0x1800371bf  call    ??1?$CDeque@VCBucket@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@$0CEA@@@QEAA@XZ; CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::~CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>(void)
0x1800371c4  mov     rcx, r12; void *
0x1800371c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800371cc  jmp     loc_180036FA5
0x1800371d1  xor     ecx, ecx; dwErrCode
0x1800371d3  call    cs:__imp_SetLastError
0x1800371da  nop     dword ptr [rax+rax+00h]
0x1800371df  jmp     loc_18003712F
0x1800371e4  mov     dword ptr [rax+18h], 0
0x1800371eb  xor     ecx, ecx; dwErrCode
0x1800371ed  mov     qword ptr [rax+20h], 0
0x1800371f5  mov     [rax], rdi
0x1800371f8  mov     [rax+8], rdi
0x1800371fc  mov     [rax+10h], rdi
0x180037200  call    cs:__imp_SetLastError
0x180037207  nop     dword ptr [rax+rax+00h]
0x18003720c  mov     r9, rdi; void *
0x18003720f  lea     r8, ?SxspClrInteropGuidSectionGenerationCallback@@YAHPEAXK0@Z; int (*)(void *, unsigned int, void *)
0x180037216  lea     rcx, [rbp+57h+var_C0]; struct _GUID_SECTION_GENERATION_CONTEXT **
0x18003721a  call    ?Create@CGSGenCtx@@SAHPEAPEAU_GUID_SECTION_GENERATION_CONTEXT@@KP6AHPEAXK1@Z1@Z; CGSGenCtx::Create(_GUID_SECTION_GENERATION_CONTEXT * *,ulong,int (*)(void *,ulong,void *),void *)
0x18003721f  test    eax, eax
0x180037221  jz      loc_1800372DB
0x180037227  mov     rax, [rbp+57h+var_C0]
0x18003722b  mov     [rsi+28h], rax
0x18003722f  mov     dword ptr [rsi+70h], 1
0x180037236  jmp     loc_180036FA5
0x18003723b  lea     rcx, off_18007BE80; struct _CALL_SITE_INFO *
0x180037242  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180037247  jmp     loc_180036FA5
0x18003724c  lea     rcx, off_18007BE40; struct _CALL_SITE_INFO *
0x180037253  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180037258  jmp     loc_180036FA5
0x18003725d  mov     r15d, edi
0x180037260  mov     [rbp+57h+var_68], 9F2h
0x180037267  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18003726c  mov     ecx, 57h ; 'W'; dwErrCode
0x180037271  call    cs:__imp_SetLastError
0x180037278  nop     dword ptr [rax+rax+00h]
0x18003727d  mov     rax, [rbp+57h+var_60]
0x180037281  mov     [rax], edi
0x180037283  mov     ebx, [rbp+57h+var_90]
0x180037286  jmp     loc_18003701F
0x18003728b  mov     rax, [rbp+57h+var_B8]
0x18003728f  lea     rdx, qword_18006FB90
0x180037296  jmp     loc_180036F17
0x18003729b  mov     rax, [rbp+57h+var_60]
0x18003729f  cmp     dword ptr [rax], 0
0x1800372a2  jz      short loc_1800372B0
0x1800372a4  xor     ecx, ecx; char *
0x1800372a6  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x1800372ab  jmp     loc_18003702C
0x1800372b0  call    cs:__imp_GetLastError
0x1800372b7  nop     dword ptr [rax+rax+00h]
0x1800372bc  mov     ecx, eax; unsigned int
0x1800372be  xor     edx, edx; Format
0x1800372c0  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x1800372c5  jmp     loc_18003702C
0x1800372ca  lea     rcx, off_18007BE20; struct _CALL_SITE_INFO *
0x1800372d1  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800372d6  jmp     loc_180036FA5
0x1800372db  lea     rcx, off_18007BE60; struct _CALL_SITE_INFO *
0x1800372e2  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800372e7  call    cs:__imp_GetLastError
0x1800372ee  nop     dword ptr [rax+rax+00h]
0x1800372f3  mov     rcx, rdi
0x1800372f6  mov     ebx, eax
0x1800372f8  call    ??1?$CDeque@VCBucket@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@$0CEA@@@QEAA@XZ; CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::~CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>(void)
0x1800372fd  mov     rcx, rdi; void *
0x180037300  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037305  mov     ecx, ebx
0x180037307  jmp     loc_180036F99
0x18003730c  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x180037311  jmp     loc_180036FE2
```
