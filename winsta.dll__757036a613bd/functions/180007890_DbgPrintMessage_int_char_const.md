# _DbgPrintMessage(int,char const *,...)

- ea: `0x180007890`
- end: `0x180007d00`
- name: `?_DbgPrintMessage@@YAXHPEBDZZ`
- size: `1136`
- prototype: `void(int, const char *, ...)`
- caller_count: `265`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800011c0`
- `0x180001640`
- `0x18000171c`
- `0x180001908`
- `0x180001a10`
- `0x180001b68`
- `0x180001eb0`
- `0x180002080`
- `0x1800023a0`
- `0x1800026e0`
- `0x1800027d4`
- `0x180002990`
- `0x180002d94`
- `0x180002ed8`
- `0x180003034`
- `0x1800031d8`
- `0x18000332c`
- `0x180003398`
- `0x180003560`
- `0x1800035d0`
- `0x1800036e0`
- `0x18000375c`
- `0x1800039e8`
- `0x180003ad4`
- `0x180003b48`
- `0x180003ba8`
- `0x180003e30`
- `0x180003f10`
- `0x180004114`
- `0x180004200`
- `0x180004450`
- `0x180004570`
- `0x1800046ec`
- `0x180004a30`
- `0x180004bb0`
- `0x180005194`
- `0x180005374`
- `0x1800053f0`
- `0x180005834`
- `0x180005974`
- `0x180005a70`
- `0x180005c30`
- `0x180005db0`
- `0x180006040`
- `0x1800063e0`
- `0x1800067b0`
- `0x180006e30`
- `0x180006f3c`
- `0x180007030`
- `0x180007540`

## callees

- `0x180007890`
- `0x18000bbe0`
- `0x18000bd70`
- `0x18002fe40`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180007ab8`
- `msvcrt!_vsnprintf` at `0x180007ab8`
- `ntdll!RtlReleaseResource` at `0x180007974`
- `ntdll!RtlReleaseResource` at `0x180007974`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800078db`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800078db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007983`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007c71`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007c71`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180007957`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180007957`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180007936`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180007936`

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
  if ( dword_1800575B0 )
    RtlAcquireResourceExclusive(&g_ProviderLock, 1u);
  if ( !RegisteredProvider )
  {
    ProviderId = *(GUID *)&(*off_180054198)[-16];
    if ( RegHandle )
      __fastfail(5u);
    xmmword_1800541B8 = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_180054190, &RegHandle) )
      EventSetInformation(RegHandle, 2, (char *)off_180054198, *(unsigned __int16 *)off_180054198);
    RegisteredProvider = 1;
  }
  if ( dword_1800575B0 )
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
        v4 = (const char *)&byte_18003E6E1;
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
    if ( (unsigned int)dword_180054190 > 4 )
    {
      v8 = byte_18004C89B;
      goto LABEL_57;
    }
  }
  else
  {
    v7 = (unsigned int)(a1 - 4);
    if ( a1 == 4 )
    {
      if ( (unsigned int)dword_180054190 > 3 )
      {
        v8 = &byte_18004C8E7;
        goto LABEL_57;
      }
    }
    else
    {
      v7 = (unsigned int)(a1 - 8);
      if ( a1 == 8 )
      {
        if ( (unsigned int)dword_180054190 > 2 )
        {
          v8 = byte_18004C829;
          goto LABEL_57;
        }
      }
      else
      {
        v7 = (unsigned int)(a1 - 128);
        if ( a1 == 128 )
        {
          if ( (unsigned int)dword_180054190 > 1 )
          {
            v8 = byte_18004C875;
            goto LABEL_57;
          }
        }
        else if ( a1 == 0x4000 )
        {
          if ( (unsigned int)dword_180054190 > 5 )
          {
            v8 = byte_18004C8C1;
            goto LABEL_57;
          }
        }
        else if ( (unsigned int)dword_180054190 > 5 )
        {
          v8 = &byte_18004C84F;
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
0x180007890  mov     [rsp-8+Format], rdx
0x180007895  mov     [rsp-8+ArgList], r8
0x18000789a  mov     [rsp-8+arg_18], r9
0x18000789f  push    rbp
0x1800078a0  push    rbx
0x1800078a1  push    rsi
0x1800078a2  push    rdi
0x1800078a3  push    r14
0x1800078a5  push    r15
0x1800078a7  lea     rbp, [rsp-158h]
0x1800078af  sub     rsp, 258h
0x1800078b6  mov     rax, cs:__security_cookie
0x1800078bd  xor     rax, rsp
0x1800078c0  mov     [rbp+180h+var_40], rax
0x1800078c7  cmp     cs:dword_1800575B0, 0
0x1800078ce  mov     esi, ecx
0x1800078d0  jz      short loc_1800078E1
0x1800078d2  mov     dl, 1; Wait
0x1800078d4  lea     rcx, ?g_ProviderLock@@3VCResource@@A; Resource
0x1800078db  call    cs:__imp_RtlAcquireResourceExclusive
0x1800078e1  cmp     cs:?RegisteredProvider@@3HA, 0; int RegisteredProvider
0x1800078e8  mov     r14d, 1
0x1800078ee  jnz     short loc_180007964
0x1800078f0  cmp     cs:RegHandle, 0
0x1800078f8  mov     rax, cs:off_180054198
0x1800078ff  movups  xmm0, xmmword ptr [rax-10h]
0x180007903  movups  xmmword ptr [rsp+280h+ProviderId.Data1], xmm0
0x180007908  jz      short loc_180007911
0x18000790a  mov     ecx, 5
0x18000790f  int     29h; Win8: RtlFailFast(ecx)
0x180007911  xorps   xmm0, xmm0
0x180007914  lea     r9, RegHandle; RegHandle
0x18000791b  lea     r8, dword_180054190; CallbackContext
0x180007922  lea     rdx, _tlgEnableCallback; EnableCallback
0x180007929  lea     rcx, [rsp+280h+ProviderId]; ProviderId
0x18000792e  movdqu  cs:xmmword_1800541B8, xmm0
0x180007936  call    cs:__imp_EventRegister
0x18000793c  test    eax, eax
0x18000793e  jnz     short loc_18000795D
0x180007940  mov     r8, cs:off_180054198
0x180007947  mov     edx, 2
0x18000794c  mov     rcx, cs:RegHandle
0x180007953  movzx   r9d, word ptr [r8]
0x180007957  call    cs:__imp_EventSetInformation
0x18000795d  mov     cs:?RegisteredProvider@@3HA, r14d; int RegisteredProvider
0x180007964  cmp     cs:dword_1800575B0, 0
0x18000796b  jz      short loc_18000797A
0x18000796d  lea     rcx, ?g_ProviderLock@@3VCResource@@A; Resource
0x180007974  call    cs:__imp_RtlReleaseResource
0x18000797a  mov     qword ptr [rsp+280h+ProviderId.Data1], 0
0x180007983  call    cs:__imp_GetLastError
0x180007989  mov     edi, 100h
0x18000798e  mov     r15d, eax
0x180007991  cmp     esi, 80h
0x180007997  jg      loc_180007A25
0x18000799d  jz      short loc_180007A1C
0x18000799f  lea     eax, [rsi-1]; switch 64 cases
0x1800079a2  cmp     eax, 3Fh
0x1800079a5  ja      def_1800079C6; jumptable 00000001800079C6 default case, cases 3,5-7,9-15,17-31,33-63
0x1800079ab  lea     rdx, __ImageBase
0x1800079b2  cdqe
0x1800079b4  movzx   eax, ds:(byte_180007CC0 - 180000000h)[rdx+rax]
0x1800079bc  mov     ecx, ds:(jpt_1800079C6 - 180000000h)[rdx+rax*4]
0x1800079c3  add     rcx, rdx
0x1800079c6  jmp     rcx; switch jump
0x1800079c8  lea     rbx, byte_18003E6E1; jumptable 00000001800079C6 case 2
0x1800079cf  jmp     loc_180007AA1
0x1800079d4  lea     rbx, aInf; jumptable 00000001800079C6 case 1
0x1800079db  jmp     loc_180007AA1
0x1800079e0  lea     rbx, aWrn; jumptable 00000001800079C6 case 4
0x1800079e7  jmp     loc_180007AA1
0x1800079ec  lea     rbx, aErr; jumptable 00000001800079C6 case 8
0x1800079f3  jmp     loc_180007AA1
0x1800079f8  lea     rbx, aDump; jumptable 00000001800079C6 case 64
0x1800079ff  jmp     loc_180007AA1
0x180007a04  lea     rbx, aBvt; jumptable 00000001800079C6 case 16
0x180007a0b  jmp     loc_180007AA1
0x180007a10  lea     rbx, aPerf; jumptable 00000001800079C6 case 32
0x180007a17  jmp     loc_180007AA1
0x180007a1c  lea     rbx, aFatal; "!FATAL!:"
0x180007a23  jmp     short loc_180007AA1
0x180007a25  cmp     esi, 800h
0x180007a2b  jg      short loc_180007A67
0x180007a2d  jz      short loc_180007A5E
0x180007a2f  cmp     esi, edi
0x180007a31  jz      short loc_180007A55
0x180007a33  cmp     esi, 200h
0x180007a39  jz      short loc_180007A4C
0x180007a3b  cmp     esi, 400h
0x180007a41  jnz     short def_1800079C6; jumptable 00000001800079C6 default case, cases 3,5-7,9-15,17-31,33-63
0x180007a43  lea     rbx, aTsrpc; "TSRPC>>>:"
0x180007a4a  jmp     short loc_180007AA1
0x180007a4c  lea     rbx, aTsapi; "TSAPI<<<:"
0x180007a53  jmp     short loc_180007AA1
0x180007a55  lea     rbx, aTsapi_0; "TSAPI>>>:"
0x180007a5c  jmp     short loc_180007AA1
0x180007a5e  lea     rbx, aTsrpc_0; "TSRPC<<<:"
0x180007a65  jmp     short loc_180007AA1
0x180007a67  cmp     esi, 1000h
0x180007a6d  jz      short loc_180007A9A
0x180007a6f  cmp     esi, 2000h
0x180007a75  jz      short loc_180007A91
0x180007a77  cmp     esi, 4000h
0x180007a7d  jz      short loc_180007A88
0x180007a7f  lea     rbx, aUnk; jumptable 00000001800079C6 default case, cases 3,5-7,9-15,17-31,33-63
0x180007a86  jmp     short loc_180007AA1
0x180007a88  lea     rbx, aVer; "VER:"
0x180007a8f  jmp     short loc_180007AA1
0x180007a91  lea     rbx, asc_18004A060; "<<<:"
0x180007a98  jmp     short loc_180007AA1
0x180007a9a  lea     rbx, asc_18004A058; ">>>:"
0x180007aa1  mov     r8, [rbp+180h+Format]; Format
0x180007aa8  lea     r9, [rbp+180h+ArgList]; ArgList
0x180007aaf  mov     edx, 0FFh; BufferCount
0x180007ab4  lea     rcx, [rbp+180h+Buffer]; Buffer
0x180007ab8  call    cs:__imp__vsnprintf
0x180007abe  test    eax, eax
0x180007ac0  js      short loc_180007AC9
0x180007ac2  cmp     eax, 0FFh
0x180007ac7  jb      short loc_180007AD0
0x180007ac9  mov     [rbp+180h+var_41], 0
0x180007ad0  lea     rax, [rbp+180h+Buffer]
0x180007ad4  mov     r9, rbx
0x180007ad7  lea     r8, aSS; "%s:%s"
0x180007ade  mov     [rsp+280h+var_260], rax
0x180007ae3  mov     rdx, rdi; unsigned __int64
0x180007ae6  lea     rcx, [rsp+280h+OutputString]; char *
0x180007aeb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180007af0  mov     eax, cs:dword_180054190
0x180007af6  mov     ecx, esi
0x180007af8  mov     [rbp+180h+var_141], 0
0x180007afc  sub     ecx, r14d
0x180007aff  jz      short loc_180007B5E
0x180007b01  sub     ecx, 3
0x180007b04  jz      short loc_180007B50
0x180007b06  sub     ecx, 4
0x180007b09  jz      short loc_180007B42
0x180007b0b  sub     ecx, 78h ; 'x'
0x180007b0e  jz      short loc_180007B34
0x180007b10  cmp     ecx, 3F80h
0x180007b16  jz      short loc_180007B26
0x180007b18  cmp     eax, 5
0x180007b1b  jbe     short loc_180007B83
0x180007b1d  lea     rdx, byte_18004C84F
0x180007b24  jmp     short loc_180007B6A
0x180007b26  cmp     eax, 5
0x180007b29  jbe     short loc_180007B83
0x180007b2b  lea     rdx, byte_18004C8C1
0x180007b32  jmp     short loc_180007B6A
0x180007b34  cmp     eax, r14d
0x180007b37  jbe     short loc_180007B83
0x180007b39  lea     rdx, byte_18004C875
0x180007b40  jmp     short loc_180007B6A
0x180007b42  cmp     eax, 2
0x180007b45  jbe     short loc_180007B83
0x180007b47  lea     rdx, byte_18004C829
0x180007b4e  jmp     short loc_180007B6A
0x180007b50  cmp     eax, 3
0x180007b53  jbe     short loc_180007B83
0x180007b55  lea     rdx, byte_18004C8E7
0x180007b5c  jmp     short loc_180007B6A
0x180007b5e  cmp     eax, 4
0x180007b61  jbe     short loc_180007B83
0x180007b63  lea     rdx, byte_18004C89B
0x180007b6a  lea     rax, [rsp+280h+OutputString]
0x180007b6f  mov     qword ptr [rsp+280h+ProviderId.Data1], rax
0x180007b74  lea     rax, [rsp+280h+ProviderId]
0x180007b79  mov     [rsp+280h+var_260], rax
0x180007b7e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180007b83  mov     rcx, rdi
0x180007b86  lea     rax, [rsp+280h+OutputString]
0x180007b8b  nop     dword ptr [rax+rax+00h]
0x180007b90  cmp     byte ptr [rax], 0
0x180007b93  jz      short loc_180007B9D
0x180007b95  inc     rax
0x180007b98  sub     rcx, r14
0x180007b9b  jnz     short loc_180007B90
0x180007b9d  xor     eax, eax
0x180007b9f  mov     r8, rdi
0x180007ba2  sub     r8, rcx
0x180007ba5  mov     r9d, 7FFFFFFEh
0x180007bab  test    rcx, rcx
0x180007bae  cmovz   r8, rax
0x180007bb2  jz      short loc_180007BFD
0x180007bb4  lea     rcx, [rsp+280h+OutputString]
0x180007bb9  mov     eax, r9d
0x180007bbc  lea     rcx, [rcx+r8]
0x180007bc0  lea     rdx, asc_18003E304; "\n"
0x180007bc7  sub     rdi, r8
0x180007bca  jz      short loc_180007BEF
0x180007bcc  nop     dword ptr [rax+00h]
0x180007bd0  test    rax, rax
0x180007bd3  jz      short loc_180007BEF
0x180007bd5  movzx   r8d, byte ptr [rdx]
0x180007bd9  test    r8b, r8b
0x180007bdc  jz      short loc_180007BEF
0x180007bde  mov     [rcx], r8b
0x180007be1  inc     rdx
0x180007be4  inc     rcx
0x180007be7  dec     rax
0x180007bea  sub     rdi, r14
0x180007bed  jnz     short loc_180007BD0
0x180007bef  test    rdi, rdi
0x180007bf2  lea     rax, [rcx-1]
0x180007bf6  cmovnz  rax, rcx
0x180007bfa  mov     byte ptr [rax], 0
0x180007bfd  lock xadd cs:?g_DbgTracePos@@3KA, r14d; ulong g_DbgTracePos
0x180007c06  mov     eax, r14d
0x180007c09  lea     rcx, [rsp+280h+OutputString]
0x180007c0e  and     eax, 7Fh
0x180007c11  mov     r8d, 50h ; 'P'
0x180007c17  lea     rdx, [rax+rax*4]
0x180007c1b  shl     rdx, 4
0x180007c1f  lea     rax, ?g_DbgTrace@@3PAY0FA@DA; char (near * g_DbgTrace)[80]
0x180007c26  add     rdx, rax
0x180007c29  nop     dword ptr [rax+00000000h]
0x180007c30  test    r9, r9
0x180007c33  jz      short loc_180007C4D
0x180007c35  movzx   eax, byte ptr [rcx]
0x180007c38  test    al, al
0x180007c3a  jz      short loc_180007C4D
0x180007c3c  mov     [rdx], al
0x180007c3e  inc     rcx
0x180007c41  inc     rdx
0x180007c44  dec     r9
0x180007c47  sub     r8, 1
0x180007c4b  jnz     short loc_180007C30
0x180007c4d  test    r8, r8
0x180007c50  lea     rax, [rdx-1]
0x180007c54  cmovnz  rax, rdx
0x180007c58  cmp     cs:?g_bDebugSpew@@3HA, 0; int g_bDebugSpew
0x180007c5f  mov     byte ptr [rax], 0
0x180007c62  jnz     short loc_180007C6C
0x180007c64  cmp     esi, 80h
0x180007c6a  jnz     short loc_180007C77
0x180007c6c  lea     rcx, [rsp+280h+OutputString]; lpOutputString
0x180007c71  call    cs:__imp_OutputDebugStringA
0x180007c77  mov     ecx, r15d; dwErrCode
0x180007c7a  call    cs:__imp_SetLastError
0x180007c80  mov     rcx, [rbp+180h+var_40]
0x180007c87  xor     rcx, rsp; StackCookie
0x180007c8a  call    __security_check_cookie
0x180007c8f  add     rsp, 258h
0x180007c96  pop     r15
0x180007c98  pop     r14
0x180007c9a  pop     rdi
0x180007c9b  pop     rsi
0x180007c9c  pop     rbx
0x180007c9d  pop     rbp
0x180007c9e  retn
```
