# CVssSafeCriticalSection::Init(void)

- ea: `0x14002ad34`
- end: `0x14002b024`
- name: `?Init@CVssSafeCriticalSection@@QEAAXXZ`
- size: `752`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `14`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140028d60`
- `0x1400532a4`
- `0x140063078`
- `0x14007b9b0`
- `0x14007cf8c`
- `0x140080400`
- `0x1400afa84`
- `0x1400b3120`
- `0x1400b5908`
- `0x1400b6a54`
- `0x1400b736c`
- `0x1400c1e70`
- `0x1400c4c5c`
- `0x1400c7c80`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x140013cb0`
- `0x140015e38`
- `0x14002ad34`
- `0x140049ec4`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14002af01`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14002af01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002af16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002af16`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002aee3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002aee3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002addc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002addc`
- `VssTrace!__imp_VssTraceMessage` at `0x14002aeb4`
- `VssTrace!__imp_VssTraceMessage` at `0x14002aeb4`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002ae2d`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002ae2d`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002ae1f`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002ae1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssSafeCriticalSection::Init(LPCRITICAL_SECTION lpCriticalSection)
{
  int v2; // eax
  __int64 v3; // rcx
  int v4; // edi
  int DebugInfo; // ecx
  int v6; // ecx
  int v7; // ecx
  DWORD LastError; // ebx
  const unsigned __int16 *v9; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v10; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v11; // [rsp+60h] [rbp-A0h]
  int v12; // [rsp+68h] [rbp-98h]
  int v13; // [rsp+6Ch] [rbp-94h]
  int v14; // [rsp+70h] [rbp-90h]
  _BYTE v15[120]; // [rsp+78h] [rbp-88h] BYREF
  int v16; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v17; // [rsp+100h] [rbp+0h] BYREF
  int v18; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v19; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v20; // [rsp+118h] [rbp+18h]
  unsigned int v21; // [rsp+120h] [rbp+20h]
  int v22; // [rsp+124h] [rbp+24h]
  const wchar_t *v23; // [rsp+128h] [rbp+28h]
  unsigned int v24; // [rsp+130h] [rbp+30h]
  DWORD TickCount; // [rsp+134h] [rbp+34h]
  int v26; // [rsp+138h] [rbp+38h]
  __int128 v27; // [rsp+140h] [rbp+40h]
  __int128 v28; // [rsp+150h] [rbp+50h]
  __int64 v29; // [rsp+160h] [rbp+60h]
  __int64 v30; // [rsp+1A0h] [rbp+A0h] BYREF

  v9 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v10 = L"CVssSafeCriticalSection::Init";
  v11 = L"INCTYPEH";
  v12 = 320;
  v13 = 11;
  v14 = 255;
  v16 = 0x1000000;
  memset_0(v15, 0, sizeof(v15));
  v18 = 0;
  v23 = L"CVssSafeCriticalSection::Init";
  v19 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v20 = L"INCTYPEH";
  v21 = 320;
  v22 = 11;
  TickCount = GetTickCount();
  v26 = 255;
  v17 = 0xFFFFFFFF00000000uLL;
  v29 = 0;
  v27 = 0;
  v28 = 0;
  v30 = 0;
  if ( (int)VssGetTracingContextPerThread(&v30) < 0 )
  {
    v3 = v29;
  }
  else
  {
    v2 = VssSetTracingContextPerThread(&v17);
    v3 = v29;
    if ( v2 >= 0 )
      v3 = v30;
    v29 = v3;
  }
  if ( v3 )
    v24 = *(_DWORD *)(v3 + 48) + 1;
  else
    v24 = 0;
  v4 = 160;
  if ( v26 != 255 )
    v4 = v26;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v17) )
    VssTraceMessage(v19, v20, v21, v24, v22, v23, L"ENTER", v4, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v9);
  do
  {
    while ( 1 )
    {
      DebugInfo = (int)lpCriticalSection[1].DebugInfo;
      if ( !DebugInfo )
        break;
      v6 = DebugInfo - 1;
      if ( !v6 )
        goto LABEL_25;
      v7 = v6 - 1;
      if ( v7 )
      {
        v9 = L"base\\stor\\vss\\inc\\vs_types.hxx";
        v10 = L"CVssSafeCriticalSection::Init";
        v11 = L"INCTYPEH";
        v13 = 11;
        v14 = 255;
        v16 = 0x1000000;
        if ( v7 != 1 )
        {
          v12 = 363;
          memset_0(v15, 0, sizeof(v15));
          CVssFunctionTracer::Throw(&v17, &v9, 2147549183LL, L"Unexpected error");
        }
        v12 = 359;
        memset_0(v15, 0, sizeof(v15));
        CVssFunctionTracer::Throw(&v17, &v9, 2147942414LL, L"Initialization failed");
      }
      Sleep(0x1F4u);
    }
  }
  while ( _InterlockedCompareExchange((volatile signed __int32 *)&lpCriticalSection[1], 2, 0) );
  if ( !InitializeCriticalSectionAndSpinCount(lpCriticalSection, 0x80000400) )
  {
    LODWORD(lpCriticalSection[1].DebugInfo) = 3;
    LastError = GetLastError();
    v9 = L"base\\stor\\vss\\inc\\vs_types.hxx";
    v10 = L"CVssSafeCriticalSection::Init";
    v11 = L"INCTYPEH";
    v12 = 338;
    v13 = 11;
    v14 = 255;
    v16 = 0x1000000;
    memset_0(v15, 0, sizeof(v15));
    CVssFunctionTracer::TranslateGenericError(
      &v17,
      &v9,
      LastError,
      L"InitializeCriticalSectionAndSpinCount(&m_cs, 0x80000400)");
  }
  LODWORD(lpCriticalSection[1].DebugInfo) = 1;
LABEL_25:
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v17);
}

```

## disassembly

```asm
0x14002ad34  mov     [rsp-8+arg_8], rbx
0x14002ad39  mov     [rsp-8+arg_10], rdi
0x14002ad3e  push    rbp
0x14002ad3f  push    r12
0x14002ad41  push    r13
0x14002ad43  push    r14
0x14002ad45  push    r15
0x14002ad47  lea     rbp, [rsp-70h]
0x14002ad4c  sub     rsp, 170h
0x14002ad53  mov     rbx, rcx
0x14002ad56  lea     r15, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x14002ad5d  mov     [rsp+190h+var_140], r15
0x14002ad62  lea     r12, aCvsssafecritic; "CVssSafeCriticalSection::Init"
0x14002ad69  mov     [rsp+190h+var_138], r12
0x14002ad6e  lea     r13, aInctypeh; "INCTYPEH"
0x14002ad75  mov     [rsp+190h+var_130], r13
0x14002ad7a  mov     [rsp+190h+var_128], 140h
0x14002ad82  mov     [rsp+190h+var_124], 0Bh
0x14002ad8a  mov     r14d, 0FFh
0x14002ad90  mov     [rsp+190h+var_120], r14d
0x14002ad95  mov     [rbp+90h+var_A0], 1000000h
0x14002ad9c  xor     edx, edx; Val
0x14002ad9e  lea     r8d, [rdx+78h]; Size
0x14002ada2  lea     rcx, [rsp+190h+var_118]; void *
0x14002ada7  call    memset_0
0x14002adac  mov     [rbp+90h+var_88], 0
0x14002adb3  mov     rax, [rsp+190h+var_138]
0x14002adb8  mov     [rbp+90h+var_68], rax
0x14002adbc  mov     rax, [rsp+190h+var_140]
0x14002adc1  mov     [rbp+90h+var_80], rax
0x14002adc5  mov     rax, [rsp+190h+var_130]
0x14002adca  mov     [rbp+90h+var_78], rax
0x14002adce  mov     eax, [rsp+190h+var_128]
0x14002add2  mov     [rbp+90h+var_70], eax
0x14002add5  mov     eax, [rsp+190h+var_124]
0x14002add9  mov     [rbp+90h+var_6C], eax
0x14002addc  call    cs:__imp_GetTickCount
0x14002ade2  mov     [rbp+90h+var_5C], eax
0x14002ade5  mov     [rbp+90h+var_8C], 0FFFFFFFFh
0x14002adec  mov     eax, [rsp+190h+var_120]
0x14002adf0  mov     [rbp+90h+var_58], eax
0x14002adf3  mov     [rbp+90h+var_90], 0
0x14002adfa  mov     [rbp+90h+var_30], 0
0x14002ae02  xorps   xmm0, xmm0
0x14002ae05  movups  [rbp+90h+var_50], xmm0
0x14002ae09  movups  [rbp+90h+var_40], xmm0
0x14002ae0d  mov     [rbp+90h+arg_0], 0
0x14002ae18  lea     rcx, [rbp+90h+arg_0]
0x14002ae1f  call    cs:__imp_VssGetTracingContextPerThread
0x14002ae25  test    eax, eax
0x14002ae27  js      short loc_14002AE47
0x14002ae29  lea     rcx, [rbp+90h+var_90]
0x14002ae2d  call    cs:__imp_VssSetTracingContextPerThread
0x14002ae33  mov     rcx, [rbp+90h+var_30]
0x14002ae37  test    eax, eax
0x14002ae39  cmovns  rcx, [rbp+90h+arg_0]
0x14002ae41  mov     [rbp+90h+var_30], rcx
0x14002ae45  jmp     short loc_14002AE4B
0x14002ae47  mov     rcx, [rbp+90h+var_30]
0x14002ae4b  test    rcx, rcx
0x14002ae4e  jz      short loc_14002AE5A
0x14002ae50  mov     eax, [rcx+30h]
0x14002ae53  inc     eax
0x14002ae55  mov     [rbp+90h+var_60], eax
0x14002ae58  jmp     short loc_14002AE61
0x14002ae5a  mov     [rbp+90h+var_60], 0
0x14002ae61  mov     edi, 0A0h
0x14002ae66  cmp     [rbp+90h+var_58], r14d
0x14002ae6a  cmovnz  edi, [rbp+90h+var_58]
0x14002ae6e  lea     rcx, [rbp+90h+var_90]; this
0x14002ae72  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14002ae77  test    eax, eax
0x14002ae79  jz      short loc_14002AEBA
0x14002ae7b  mov     [rsp+190h+var_150], 0
0x14002ae84  mov     [rsp+190h+var_158], edi
0x14002ae88  lea     rax, aEnter; "ENTER"
0x14002ae8f  mov     [rsp+190h+var_160], rax
0x14002ae94  mov     rax, [rbp+90h+var_68]
0x14002ae98  mov     [rsp+190h+var_168], rax
0x14002ae9d  mov     eax, [rbp+90h+var_6C]
0x14002aea0  mov     [rsp+190h+var_170], eax
0x14002aea4  mov     r9d, [rbp+90h+var_60]
0x14002aea8  mov     r8d, [rbp+90h+var_70]
0x14002aeac  mov     rdx, [rbp+90h+var_78]
0x14002aeb0  mov     rcx, [rbp+90h+var_80]
0x14002aeb4  call    cs:__imp_VssTraceMessage
0x14002aeba  lea     rcx, [rsp+190h+var_140]; this
0x14002aebf  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14002aec4  nop
0x14002aec5  mov     ecx, [rbx+28h]
0x14002aec8  test    ecx, ecx
0x14002aeca  jz      short loc_14002AEEB
0x14002aecc  sub     ecx, 1
0x14002aecf  jz      loc_14002AFFE
0x14002aed5  sub     ecx, 1
0x14002aed8  jnz     loc_14002AF72
0x14002aede  mov     ecx, 1F4h; dwMilliseconds
0x14002aee3  call    cs:__imp_Sleep
0x14002aee9  jmp     short loc_14002AEC5
0x14002aeeb  mov     ecx, 2
0x14002aef0  xor     eax, eax
0x14002aef2  lock cmpxchg [rbx+28h], ecx
0x14002aef7  jnz     short loc_14002AEC5
0x14002aef9  mov     edx, 80000400h; dwSpinCount
0x14002aefe  mov     rcx, rbx; lpCriticalSection
0x14002af01  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14002af07  test    eax, eax
0x14002af09  jnz     loc_14002AFF7
0x14002af0f  mov     dword ptr [rbx+28h], 3
0x14002af16  call    cs:__imp_GetLastError
0x14002af1c  mov     ebx, eax
0x14002af1e  mov     [rsp+190h+var_140], r15
0x14002af23  mov     [rsp+190h+var_138], r12
0x14002af28  mov     [rsp+190h+var_130], r13
0x14002af2d  mov     [rsp+190h+var_128], 152h
0x14002af35  mov     [rsp+190h+var_124], 0Bh
0x14002af3d  mov     [rsp+190h+var_120], r14d
0x14002af42  mov     [rbp+90h+var_A0], 1000000h
0x14002af49  xor     edx, edx; Val
0x14002af4b  lea     r8d, [rdx+78h]; Size
0x14002af4f  lea     rcx, [rsp+190h+var_118]; void *
0x14002af54  call    memset_0
0x14002af59  lea     r9, aInitializecrit; "InitializeCriticalSectionAndSpinCount(&"...
0x14002af60  mov     r8d, ebx
0x14002af63  lea     rdx, [rsp+190h+var_140]
0x14002af68  lea     rcx, [rbp+90h+var_90]
0x14002af6c  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14002af72  mov     [rsp+190h+var_140], r15
0x14002af77  mov     [rsp+190h+var_138], r12
0x14002af7c  mov     [rsp+190h+var_130], r13
0x14002af81  mov     [rsp+190h+var_124], 0Bh
0x14002af89  mov     [rsp+190h+var_120], r14d
0x14002af8e  mov     [rbp+90h+var_A0], 1000000h
0x14002af95  xor     edx, edx; Val
0x14002af97  lea     r8d, [rdx+78h]; Size
0x14002af9b  cmp     ecx, 1
0x14002af9e  lea     rcx, [rsp+190h+var_118]; void *
0x14002afa3  jz      short loc_14002AFCE
0x14002afa5  mov     [rsp+190h+var_128], 16Bh
0x14002afad  call    memset_0
0x14002afb2  lea     r9, aUnexpectedErro_1; "Unexpected error"
0x14002afb9  mov     r8d, 8000FFFFh
0x14002afbf  lea     rdx, [rsp+190h+var_140]
0x14002afc4  lea     rcx, [rbp+90h+var_90]
0x14002afc8  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14002afce  mov     [rsp+190h+var_128], 167h
0x14002afd6  call    memset_0
0x14002afdb  lea     r9, aInitialization_0; "Initialization failed"
0x14002afe2  mov     r8d, 8007000Eh
0x14002afe8  lea     rdx, [rsp+190h+var_140]
0x14002afed  lea     rcx, [rbp+90h+var_90]
0x14002aff1  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14002aff7  mov     dword ptr [rbx+28h], 1
0x14002affe  lea     rcx, [rbp+90h+var_90]; this
0x14002b002  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14002b007  lea     r11, [rsp+190h+var_20]
0x14002b00f  mov     rbx, [r11+38h]
0x14002b013  mov     rdi, [r11+40h]
0x14002b017  mov     rsp, r11
0x14002b01a  pop     r15
0x14002b01c  pop     r14
0x14002b01e  pop     r13
0x14002b020  pop     r12
0x14002b022  pop     rbp
0x14002b023  retn
```
