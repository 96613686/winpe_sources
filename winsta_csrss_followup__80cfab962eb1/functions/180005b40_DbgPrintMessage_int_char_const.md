# _DbgPrintMessage(int,char const *,...)

- ea: `0x180005b40`
- end: `0x180005fec`
- name: `?_DbgPrintMessage@@YAXHPEBDZZ`
- size: `1196`
- prototype: `void(int, const char *, ...)`
- caller_count: `264`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800011c0`
- `0x18000129c`
- `0x1800013a0`
- `0x180001460`
- `0x180001524`
- `0x1800016c8`
- `0x180001a10`
- `0x180001d80`
- `0x180002014`
- `0x180002114`
- `0x180002464`
- `0x180002600`
- `0x180002c00`
- `0x180002df0`
- `0x1800032b4`
- `0x180003338`
- `0x180003480`
- `0x1800038c0`
- `0x180003d24`
- `0x180003e78`
- `0x180003f90`
- `0x1800041a0`
- `0x180004330`
- `0x1800045d0`
- `0x1800049a0`
- `0x180005060`
- `0x180005180`
- `0x180005280`
- `0x1800057c0`
- `0x180006000`
- `0x180006480`
- `0x1800066d0`
- `0x180006740`
- `0x180006b20`
- `0x180006ed0`
- `0x1800075a0`
- `0x180007690`
- `0x180007b10`
- `0x180007d20`
- `0x180007fe0`
- `0x180008380`
- `0x1800083fc`
- `0x180008494`
- `0x180008508`
- `0x180008590`
- `0x180008640`
- `0x1800090a0`
- `0x180009350`
- `0x1800095b0`
- `0x1800096c0`

## callees

- `0x180005b40`
- `0x18000d760`
- `0x18000d8f0`
- `0x180032c20`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180005d92`
- `msvcrt!_vsnprintf` at `0x180005d92`
- `ntdll!RtlReleaseResource` at `0x180005c3a`
- `ntdll!RtlReleaseResource` at `0x180005c3a`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005b8b`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005b8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c4f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005f51`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005f51`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005c17`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005c17`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005bf0`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005bf0`

## pseudocode

```c
void _DbgPrintMessage(int a1, const char *a2, ...)
{
  DWORD LastError; // r15d
  const char *v4; // rbx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  char *v8; // rdx
  __int64 v9; // rcx
  CHAR *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rax
  CHAR *v14; // rcx
  const char *v15; // rdx
  __int64 v16; // rdi
  CHAR *v17; // rax
  CHAR *v18; // rcx
  __int64 v19; // r8
  char (near **v20)[80]; // rdx
  char (near **v21)[80]; // rax
  bool v22; // zf
  GUID ProviderId; // [rsp+30h] [rbp-D0h] BYREF
  CHAR OutputString[256]; // [rsp+40h] [rbp-C0h] BYREF
  char Buffer[256]; // [rsp+140h] [rbp+40h] BYREF
  __int64 ArgList; // [rsp+2A0h] [rbp+1A0h] BYREF
  va_list ArgLista; // [rsp+2A0h] [rbp+1A0h]
  __int64 v29; // [rsp+2A8h] [rbp+1A8h]
  va_list va1; // [rsp+2B0h] [rbp+1B0h] BYREF

  va_start(va1, a2);
  va_start(ArgLista, a2);
  ArgList = va_arg(va1, _QWORD);
  v29 = va_arg(va1, _QWORD);
  if ( dword_18005A5B0 )
    RtlAcquireResourceExclusive(&g_ProviderLock, 1u);
  if ( !RegisteredProvider )
  {
    ProviderId = *(GUID *)&(*off_180057198)[-16];
    if ( RegHandle )
      __fastfail(5u);
    xmmword_1800571B8 = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_180057190, &RegHandle) )
      EventSetInformation(RegHandle, 2, (char *)off_180057198, *(unsigned __int16 *)off_180057198);
    RegisteredProvider = 1;
  }
  if ( dword_18005A5B0 )
    RtlReleaseResource(&g_ProviderLock);
  *(_QWORD *)&ProviderId.Data1 = 0;
  LastError = GetLastError();
  if ( a1 > 128 )
  {
    if ( a1 > 2048 )
    {
      switch ( a1 )
      {
        case 0x1000:
          v4 = ">>>:";
          goto LABEL_38;
        case 0x2000:
          v4 = "<<<:";
          goto LABEL_38;
        case 0x4000:
          v4 = "VER:";
          goto LABEL_38;
      }
    }
    else
    {
      switch ( a1 )
      {
        case 2048:
          v4 = "TSRPC<<<:";
          goto LABEL_38;
        case 256:
          v4 = "TSAPI>>>:";
          goto LABEL_38;
        case 512:
          v4 = "TSAPI<<<:";
          goto LABEL_38;
        case 1024:
          v4 = "TSRPC>>>:";
          goto LABEL_38;
      }
    }
LABEL_34:
    v4 = "UNK:";
    goto LABEL_38;
  }
  if ( a1 == 128 )
  {
    v4 = "!FATAL!:";
  }
  else
  {
    switch ( a1 )
    {
      case 1:
        v4 = "INF:";
        break;
      case 2:
        v4 = (const char *)&byte_1800416E1;
        break;
      case 4:
        v4 = "WRN:";
        break;
      case 8:
        v4 = "ERR:";
        break;
      case 16:
        v4 = "BVT:";
        break;
      case 32:
        v4 = "PERF:";
        break;
      case 64:
        v4 = "DUMP:";
        break;
      default:
        goto LABEL_34;
    }
  }
LABEL_38:
  if ( (unsigned int)_vsnprintf(Buffer, 0xFFu, a2, ArgLista) > 0xFE )
    Buffer[255] = 0;
  StringCchPrintfA(OutputString, 0x100u, "%s:%s", v4, Buffer);
  OutputString[255] = 0;
  v7 = (unsigned int)(a1 - 1);
  if ( a1 == 1 )
  {
    if ( (unsigned int)dword_180057190 > 4 )
    {
      v8 = byte_18004F8EB;
      goto LABEL_57;
    }
  }
  else
  {
    v7 = (unsigned int)(a1 - 4);
    if ( a1 == 4 )
    {
      if ( (unsigned int)dword_180057190 > 3 )
      {
        v8 = &byte_18004F937;
        goto LABEL_57;
      }
    }
    else
    {
      v7 = (unsigned int)(a1 - 8);
      if ( a1 == 8 )
      {
        if ( (unsigned int)dword_180057190 > 2 )
        {
          v8 = byte_18004F879;
          goto LABEL_57;
        }
      }
      else
      {
        v7 = (unsigned int)(a1 - 128);
        if ( a1 == 128 )
        {
          if ( (unsigned int)dword_180057190 > 1 )
          {
            v8 = byte_18004F8C5;
            goto LABEL_57;
          }
        }
        else if ( a1 == 0x4000 )
        {
          if ( (unsigned int)dword_180057190 > 5 )
          {
            v8 = byte_18004F911;
            goto LABEL_57;
          }
        }
        else if ( (unsigned int)dword_180057190 > 5 )
        {
          v8 = &byte_18004F89F;
LABEL_57:
          *(_QWORD *)&ProviderId.Data1 = OutputString;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v7,
            (unsigned __int8 *)v8,
            v5,
            v6,
            (const unsigned __int16 **)&ProviderId);
        }
      }
    }
  }
  v9 = 256;
  v10 = OutputString;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = 256 - v9;
  v12 = 2147483646;
  if ( v9 )
  {
    v13 = 2147483646;
    v14 = &OutputString[v11];
    v15 = "\n";
    v16 = 256 - v11;
    if ( 256 != v11 )
    {
      do
      {
        if ( !v13 )
          break;
        if ( !*v15 )
          break;
        *v14++ = *v15++;
        --v13;
        --v16;
      }
      while ( v16 );
    }
    v17 = v14 - 1;
    if ( v16 )
      v17 = v14;
    *v17 = 0;
  }
  v18 = OutputString;
  v19 = 80;
  v20 = &(&g_DbgTrace)[10 * (_InterlockedExchangeAdd((volatile signed __int32 *)&g_DbgTracePos, 1u) & 0x7F)];
  do
  {
    if ( !v12 )
      break;
    if ( !*v18 )
      break;
    *(_BYTE *)v20 = *v18++;
    v20 = (char (near **)[80])((char *)v20 + 1);
    --v12;
    --v19;
  }
  while ( v19 );
  v21 = (char (near **)[80])((char *)v20 - 1);
  if ( v19 )
    v21 = v20;
  v22 = g_bDebugSpew == 0;
  *(_BYTE *)v21 = 0;
  if ( !v22 || a1 == 128 )
    OutputDebugStringA(OutputString);
  SetLastError(LastError);
}

```

## disassembly

```asm
0x180005b40  mov     [rsp-8+Format], rdx
0x180005b45  mov     [rsp-8+ArgList], r8
0x180005b4a  mov     [rsp-8+arg_18], r9
0x180005b4f  push    rbp
0x180005b50  push    rbx
0x180005b51  push    rsi
0x180005b52  push    rdi
0x180005b53  push    r14
0x180005b55  push    r15
0x180005b57  lea     rbp, [rsp-158h]
0x180005b5f  sub     rsp, 258h
0x180005b66  mov     rax, cs:__security_cookie
0x180005b6d  xor     rax, rsp
0x180005b70  mov     [rbp+180h+var_40], rax
0x180005b77  cmp     cs:dword_18005A5B0, 0
0x180005b7e  mov     esi, ecx
0x180005b80  jz      short loc_180005B97
0x180005b82  mov     dl, 1; Wait
0x180005b84  lea     rcx, ?g_ProviderLock@@3VCResource@@A; Resource
0x180005b8b  call    cs:__imp_RtlAcquireResourceExclusive
0x180005b92  nop     dword ptr [rax+rax+00h]
0x180005b97  cmp     cs:?RegisteredProvider@@3HA, 0; int RegisteredProvider
0x180005b9e  mov     r14d, 1
0x180005ba4  jnz     loc_180005C2A
0x180005baa  cmp     cs:RegHandle, 0
0x180005bb2  mov     rax, cs:off_180057198
0x180005bb9  movups  xmm0, xmmword ptr [rax-10h]
0x180005bbd  movups  xmmword ptr [rsp+280h+ProviderId.Data1], xmm0
0x180005bc2  jz      short loc_180005BCB
0x180005bc4  mov     ecx, 5
0x180005bc9  int     29h; Win8: RtlFailFast(ecx)
0x180005bcb  xorps   xmm0, xmm0
0x180005bce  lea     r9, RegHandle; RegHandle
0x180005bd5  lea     r8, dword_180057190; CallbackContext
0x180005bdc  lea     rdx, _tlgEnableCallback; EnableCallback
0x180005be3  lea     rcx, [rsp+280h+ProviderId]; ProviderId
0x180005be8  movdqu  cs:xmmword_1800571B8, xmm0
0x180005bf0  call    cs:__imp_EventRegister
0x180005bf7  nop     dword ptr [rax+rax+00h]
0x180005bfc  test    eax, eax
0x180005bfe  jnz     short loc_180005C23
0x180005c00  mov     r8, cs:off_180057198
0x180005c07  mov     edx, 2
0x180005c0c  mov     rcx, cs:RegHandle
0x180005c13  movzx   r9d, word ptr [r8]
0x180005c17  call    cs:__imp_EventSetInformation
0x180005c1e  nop     dword ptr [rax+rax+00h]
0x180005c23  mov     cs:?RegisteredProvider@@3HA, r14d; int RegisteredProvider
0x180005c2a  cmp     cs:dword_18005A5B0, 0
0x180005c31  jz      short loc_180005C46
0x180005c33  lea     rcx, ?g_ProviderLock@@3VCResource@@A; Resource
0x180005c3a  call    cs:__imp_RtlReleaseResource
0x180005c41  nop     dword ptr [rax+rax+00h]
0x180005c46  mov     qword ptr [rsp+280h+ProviderId.Data1], 0
0x180005c4f  call    cs:__imp_GetLastError
0x180005c56  nop     dword ptr [rax+rax+00h]
0x180005c5b  mov     edi, 100h
0x180005c60  mov     r15d, eax
0x180005c63  cmp     esi, 80h
0x180005c69  jg      loc_180005CFF
0x180005c6f  jz      loc_180005CF6
0x180005c75  lea     eax, [rsi-1]; switch 64 cases
0x180005c78  cmp     eax, 3Fh
0x180005c7b  ja      def_180005C9C; jumptable 0000000180005C9C default case, cases 3,5-7,9-15,17-31,33-63
0x180005c81  lea     rdx, __ImageBase
0x180005c88  cdqe
0x180005c8a  movzx   eax, ds:(byte_180005FAC - 180000000h)[rdx+rax]
0x180005c92  mov     ecx, ds:(jpt_180005C9C - 180000000h)[rdx+rax*4]
0x180005c99  add     rcx, rdx
0x180005c9c  jmp     rcx; switch jump
0x180005ca2  lea     rbx, byte_1800416E1; jumptable 0000000180005C9C case 2
0x180005ca9  jmp     loc_180005D7B
0x180005cae  lea     rbx, aInf; jumptable 0000000180005C9C case 1
0x180005cb5  jmp     loc_180005D7B
0x180005cba  lea     rbx, aWrn; jumptable 0000000180005C9C case 4
0x180005cc1  jmp     loc_180005D7B
0x180005cc6  lea     rbx, aErr; jumptable 0000000180005C9C case 8
0x180005ccd  jmp     loc_180005D7B
0x180005cd2  lea     rbx, aDump; jumptable 0000000180005C9C case 64
0x180005cd9  jmp     loc_180005D7B
0x180005cde  lea     rbx, aBvt; jumptable 0000000180005C9C case 16
0x180005ce5  jmp     loc_180005D7B
0x180005cea  lea     rbx, aPerf; jumptable 0000000180005C9C case 32
0x180005cf1  jmp     loc_180005D7B
0x180005cf6  lea     rbx, aFatal; "!FATAL!:"
0x180005cfd  jmp     short loc_180005D7B
0x180005cff  cmp     esi, 800h
0x180005d05  jg      short loc_180005D41
0x180005d07  jz      short loc_180005D38
0x180005d09  cmp     esi, edi
0x180005d0b  jz      short loc_180005D2F
0x180005d0d  cmp     esi, 200h
0x180005d13  jz      short loc_180005D26
0x180005d15  cmp     esi, 400h
0x180005d1b  jnz     short def_180005C9C; jumptable 0000000180005C9C default case, cases 3,5-7,9-15,17-31,33-63
0x180005d1d  lea     rbx, aTsrpc; "TSRPC>>>:"
0x180005d24  jmp     short loc_180005D7B
0x180005d26  lea     rbx, aTsapi; "TSAPI<<<:"
0x180005d2d  jmp     short loc_180005D7B
0x180005d2f  lea     rbx, aTsapi_0; "TSAPI>>>:"
0x180005d36  jmp     short loc_180005D7B
0x180005d38  lea     rbx, aTsrpc_0; "TSRPC<<<:"
0x180005d3f  jmp     short loc_180005D7B
0x180005d41  cmp     esi, 1000h
0x180005d47  jz      short loc_180005D74
0x180005d49  cmp     esi, 2000h
0x180005d4f  jz      short loc_180005D6B
0x180005d51  cmp     esi, 4000h
0x180005d57  jz      short loc_180005D62
0x180005d59  lea     rbx, aUnk; jumptable 0000000180005C9C default case, cases 3,5-7,9-15,17-31,33-63
0x180005d60  jmp     short loc_180005D7B
0x180005d62  lea     rbx, aVer; "VER:"
0x180005d69  jmp     short loc_180005D7B
0x180005d6b  lea     rbx, asc_18004D060; "<<<:"
0x180005d72  jmp     short loc_180005D7B
0x180005d74  lea     rbx, asc_18004D058; ">>>:"
0x180005d7b  mov     r8, [rbp+180h+Format]; Format
0x180005d82  lea     r9, [rbp+180h+ArgList]; ArgList
0x180005d89  mov     edx, 0FFh; BufferCount
0x180005d8e  lea     rcx, [rbp+180h+Buffer]; Buffer
0x180005d92  call    cs:__imp__vsnprintf
0x180005d99  nop     dword ptr [rax+rax+00h]
0x180005d9e  test    eax, eax
0x180005da0  js      short loc_180005DA9
0x180005da2  cmp     eax, 0FFh
0x180005da7  jb      short loc_180005DB0
0x180005da9  mov     [rbp+180h+var_41], 0
0x180005db0  lea     rax, [rbp+180h+Buffer]
0x180005db4  mov     r9, rbx
0x180005db7  lea     r8, aSS; "%s:%s"
0x180005dbe  mov     [rsp+280h+var_260], rax
0x180005dc3  mov     rdx, rdi; unsigned __int64
0x180005dc6  lea     rcx, [rsp+280h+OutputString]; char *
0x180005dcb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180005dd0  mov     eax, cs:dword_180057190
0x180005dd6  mov     ecx, esi
0x180005dd8  mov     [rbp+180h+var_141], 0
0x180005ddc  sub     ecx, r14d
0x180005ddf  jz      short loc_180005E3E
0x180005de1  sub     ecx, 3
0x180005de4  jz      short loc_180005E30
0x180005de6  sub     ecx, 4
0x180005de9  jz      short loc_180005E22
0x180005deb  sub     ecx, 78h ; 'x'
0x180005dee  jz      short loc_180005E14
0x180005df0  cmp     ecx, 3F80h
0x180005df6  jz      short loc_180005E06
0x180005df8  cmp     eax, 5
0x180005dfb  jbe     short loc_180005E63
0x180005dfd  lea     rdx, byte_18004F89F
0x180005e04  jmp     short loc_180005E4A
0x180005e06  cmp     eax, 5
0x180005e09  jbe     short loc_180005E63
0x180005e0b  lea     rdx, byte_18004F911
0x180005e12  jmp     short loc_180005E4A
0x180005e14  cmp     eax, r14d
0x180005e17  jbe     short loc_180005E63
0x180005e19  lea     rdx, byte_18004F8C5
0x180005e20  jmp     short loc_180005E4A
0x180005e22  cmp     eax, 2
0x180005e25  jbe     short loc_180005E63
0x180005e27  lea     rdx, byte_18004F879
0x180005e2e  jmp     short loc_180005E4A
0x180005e30  cmp     eax, 3
0x180005e33  jbe     short loc_180005E63
0x180005e35  lea     rdx, byte_18004F937
0x180005e3c  jmp     short loc_180005E4A
0x180005e3e  cmp     eax, 4
0x180005e41  jbe     short loc_180005E63
0x180005e43  lea     rdx, byte_18004F8EB
0x180005e4a  lea     rax, [rsp+280h+OutputString]
0x180005e4f  mov     qword ptr [rsp+280h+ProviderId.Data1], rax
0x180005e54  lea     rax, [rsp+280h+ProviderId]
0x180005e59  mov     [rsp+280h+var_260], rax
0x180005e5e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180005e63  mov     rcx, rdi
0x180005e66  lea     rax, [rsp+280h+OutputString]
0x180005e6b  nop     dword ptr [rax+rax+00h]
0x180005e70  cmp     byte ptr [rax], 0
0x180005e73  jz      short loc_180005E7D
0x180005e75  inc     rax
0x180005e78  sub     rcx, r14
0x180005e7b  jnz     short loc_180005E70
0x180005e7d  xor     eax, eax
0x180005e7f  mov     r8, rdi
0x180005e82  sub     r8, rcx
0x180005e85  mov     r9d, 7FFFFFFEh
0x180005e8b  test    rcx, rcx
0x180005e8e  cmovz   r8, rax
0x180005e92  jz      short loc_180005EDD
0x180005e94  lea     rcx, [rsp+280h+OutputString]
0x180005e99  mov     eax, r9d
0x180005e9c  lea     rcx, [rcx+r8]
0x180005ea0  lea     rdx, asc_1800413EC; "\n"
0x180005ea7  sub     rdi, r8
0x180005eaa  jz      short loc_180005ECF
0x180005eac  nop     dword ptr [rax+00h]
0x180005eb0  test    rax, rax
0x180005eb3  jz      short loc_180005ECF
0x180005eb5  movzx   r8d, byte ptr [rdx]
0x180005eb9  test    r8b, r8b
0x180005ebc  jz      short loc_180005ECF
0x180005ebe  mov     [rcx], r8b
0x180005ec1  inc     rdx
0x180005ec4  inc     rcx
0x180005ec7  dec     rax
0x180005eca  sub     rdi, r14
0x180005ecd  jnz     short loc_180005EB0
0x180005ecf  test    rdi, rdi
0x180005ed2  lea     rax, [rcx-1]
0x180005ed6  cmovnz  rax, rcx
0x180005eda  mov     byte ptr [rax], 0
0x180005edd  lock xadd cs:?g_DbgTracePos@@3KA, r14d; ulong g_DbgTracePos
0x180005ee6  mov     eax, r14d
0x180005ee9  lea     rcx, [rsp+280h+OutputString]
0x180005eee  and     eax, 7Fh
0x180005ef1  mov     r8d, 50h ; 'P'
0x180005ef7  lea     rdx, [rax+rax*4]
0x180005efb  shl     rdx, 4
0x180005eff  lea     rax, ?g_DbgTrace@@3PAY0FA@DA; char (near * g_DbgTrace)[80]
0x180005f06  add     rdx, rax
0x180005f09  nop     dword ptr [rax+00000000h]
0x180005f10  test    r9, r9
0x180005f13  jz      short loc_180005F2D
0x180005f15  movzx   eax, byte ptr [rcx]
0x180005f18  test    al, al
0x180005f1a  jz      short loc_180005F2D
0x180005f1c  mov     [rdx], al
0x180005f1e  inc     rcx
0x180005f21  inc     rdx
0x180005f24  dec     r9
0x180005f27  sub     r8, 1
0x180005f2b  jnz     short loc_180005F10
0x180005f2d  test    r8, r8
0x180005f30  lea     rax, [rdx-1]
0x180005f34  cmovnz  rax, rdx
0x180005f38  cmp     cs:?g_bDebugSpew@@3HA, 0; int g_bDebugSpew
0x180005f3f  mov     byte ptr [rax], 0
0x180005f42  jnz     short loc_180005F4C
0x180005f44  cmp     esi, 80h
0x180005f4a  jnz     short loc_180005F5D
0x180005f4c  lea     rcx, [rsp+280h+OutputString]; lpOutputString
0x180005f51  call    cs:__imp_OutputDebugStringA
0x180005f58  nop     dword ptr [rax+rax+00h]
0x180005f5d  mov     ecx, r15d; dwErrCode
0x180005f60  call    cs:__imp_SetLastError
0x180005f67  nop     dword ptr [rax+rax+00h]
0x180005f6c  mov     rcx, [rbp+180h+var_40]
0x180005f73  xor     rcx, rsp; StackCookie
0x180005f76  call    __security_check_cookie
0x180005f7b  add     rsp, 258h
0x180005f82  pop     r15
0x180005f84  pop     r14
0x180005f86  pop     rdi
0x180005f87  pop     rsi
0x180005f88  pop     rbx
0x180005f89  pop     rbp
0x180005f8a  retn
```
