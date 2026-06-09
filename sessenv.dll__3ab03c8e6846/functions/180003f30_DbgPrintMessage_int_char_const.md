# _DbgPrintMessage(int,char const *,...)

- ea: `0x180003f30`
- end: `0x180004618`
- name: `?_DbgPrintMessage@@YAXHPEBDZZ`
- size: `1768`
- prototype: `void(int, const char *, ...)`
- caller_count: `236`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002730`
- `0x180002bb0`
- `0x180002da0`
- `0x180003040`
- `0x1800033e0`
- `0x180003860`
- `0x180003c70`
- `0x180003e30`
- `0x180004620`
- `0x180004c70`
- `0x180004eb0`
- `0x180005010`
- `0x180005120`
- `0x1800051f0`
- `0x18001200c`
- `0x1800122d0`
- `0x180012498`
- `0x180012680`
- `0x1800129b0`
- `0x180012a90`
- `0x180012f90`
- `0x180013160`
- `0x180013368`
- `0x18001346c`
- `0x1800135a0`
- `0x1800136ac`
- `0x180013970`
- `0x1800141f4`
- `0x1800142c0`
- `0x180014440`
- `0x1800145d4`
- `0x180014764`
- `0x180014b78`
- `0x180014f24`
- `0x180015240`
- `0x180015488`
- `0x1800155b8`
- `0x180015924`
- `0x180015bf8`
- `0x180015cac`
- `0x180015dd8`
- `0x180016140`
- `0x1800162cc`
- `0x18001642c`
- `0x180016580`
- `0x180016674`
- `0x18001716c`
- `0x180017350`
- `0x1800173f0`
- `0x180017564`

## callees

- `0x180003f30`
- `0x180012920`
- `0x18001a280`
- `0x18001b540`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180003f7d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003f7d`
- `ntdll!RtlReleaseResource` at `0x180004016`
- `ntdll!RtlReleaseResource` at `0x180004016`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004591`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004024`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003fd8`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003fd8`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003ff9`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003ff9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800044aa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800044aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004588`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004588`

## pseudocode

```c
void _DbgPrintMessage(int a1, const char *a2, ...)
{
  DWORD LastError; // r15d
  const char *v4; // rbx
  __int64 v5; // rax
  char *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  CHAR *v13; // rax
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // rax
  CHAR *v17; // rcx
  const char *v18; // rdx
  __int64 v19; // rdi
  CHAR *v20; // rax
  CHAR *v21; // rcx
  __int64 v22; // r8
  char (near **v23)[80]; // rdx
  char (near **v24)[80]; // rax
  bool v25; // zf
  GUID ProviderId; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-B8h] BYREF
  char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  CHAR *v31; // [rsp+68h] [rbp-98h]
  int v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+74h] [rbp-8Ch]
  CHAR OutputString[256]; // [rsp+80h] [rbp-80h] BYREF
  char Buffer[256]; // [rsp+180h] [rbp+80h] BYREF
  va_list ArgList; // [rsp+2E0h] [rbp+1E0h] BYREF

  va_start(ArgList, a2);
  if ( dword_1800877C0 )
    RtlAcquireResourceExclusive(&g_ProviderLock, 1u);
  if ( !RegisteredProvider )
  {
    ProviderId = *(GUID *)&(*off_180084178)[-16];
    if ( RegHandle )
      __fastfail(5u);
    xmmword_180084198 = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_180084170, &RegHandle) )
      EventSetInformation(RegHandle, 2, (char *)off_180084178, *(unsigned __int16 *)off_180084178);
    RegisteredProvider = 1;
  }
  if ( dword_1800877C0 )
    RtlReleaseResource(&g_ProviderLock);
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
        v4 = (const char *)&byte_18006386D;
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
  if ( (unsigned int)vsnprintf(Buffer, 0xFFu, a2, ArgList) > 0xFE )
    Buffer[255] = 0;
  StringCchPrintfA(OutputString, 0x100u, "%s:%s", v4, Buffer);
  OutputString[255] = 0;
  switch ( a1 )
  {
    case 1:
      if ( (unsigned int)dword_180084170 > 4 )
      {
        v11 = -1;
        do
          ++v11;
        while ( OutputString[v11] );
        v33 = 0;
        v32 = v11 + 1;
        *(_DWORD *)&ProviderId.Data2 = 4;
        UserData.Ptr = (ULONGLONG)off_180084178;
        v31 = OutputString;
        ProviderId.Data1 = 184549376;
        *(_QWORD *)ProviderId.Data4 = 0;
        UserData.Size = *(unsigned __int16 *)off_180084178;
        v6 = byte_180078D6B;
        goto LABEL_69;
      }
      break;
    case 4:
      if ( (unsigned int)dword_180084170 > 3 )
      {
        v10 = -1;
        do
          ++v10;
        while ( OutputString[v10] );
        v33 = 0;
        v32 = v10 + 1;
        *(_DWORD *)&ProviderId.Data2 = 3;
        UserData.Ptr = (ULONGLONG)off_180084178;
        v31 = OutputString;
        ProviderId.Data1 = 184549376;
        *(_QWORD *)ProviderId.Data4 = 0;
        UserData.Size = *(unsigned __int16 *)off_180084178;
        v6 = &byte_180078DB7;
        goto LABEL_69;
      }
      break;
    case 8:
      if ( (unsigned int)dword_180084170 > 2 )
      {
        v9 = -1;
        do
          ++v9;
        while ( OutputString[v9] );
        v33 = 0;
        v32 = v9 + 1;
        *(_DWORD *)&ProviderId.Data2 = 2;
        UserData.Ptr = (ULONGLONG)off_180084178;
        v31 = OutputString;
        ProviderId.Data1 = 184549376;
        *(_QWORD *)ProviderId.Data4 = 0;
        UserData.Size = *(unsigned __int16 *)off_180084178;
        v6 = byte_180078CF9;
        goto LABEL_69;
      }
      break;
    case 0x80:
      if ( (unsigned int)dword_180084170 > 1 )
      {
        v8 = -1;
        do
          ++v8;
        while ( OutputString[v8] );
        v33 = 0;
        v32 = v8 + 1;
        *(_DWORD *)&ProviderId.Data2 = 1;
        UserData.Ptr = (ULONGLONG)off_180084178;
        v31 = OutputString;
        ProviderId.Data1 = 184549376;
        *(_QWORD *)ProviderId.Data4 = 0;
        UserData.Size = *(unsigned __int16 *)off_180084178;
        v6 = byte_180078D45;
        goto LABEL_69;
      }
      break;
    case 0x4000:
      if ( (unsigned int)dword_180084170 > 5 )
      {
        v7 = -1;
        do
          ++v7;
        while ( OutputString[v7] );
        v33 = 0;
        v32 = v7 + 1;
        *(_DWORD *)&ProviderId.Data2 = 5;
        UserData.Ptr = (ULONGLONG)off_180084178;
        v31 = OutputString;
        ProviderId.Data1 = 184549376;
        *(_QWORD *)ProviderId.Data4 = 0;
        UserData.Size = *(unsigned __int16 *)off_180084178;
        v6 = byte_180078D91;
        goto LABEL_69;
      }
      break;
    default:
      if ( (unsigned int)dword_180084170 > 5 )
      {
        v5 = -1;
        do
          ++v5;
        while ( OutputString[v5] );
        v33 = 0;
        v32 = v5 + 1;
        *(_DWORD *)&ProviderId.Data2 = 5;
        UserData.Ptr = (ULONGLONG)off_180084178;
        v31 = OutputString;
        ProviderId.Data1 = 184549376;
        *(_QWORD *)ProviderId.Data4 = 0;
        UserData.Size = *(unsigned __int16 *)off_180084178;
        v6 = &byte_180078D1F;
LABEL_69:
        v28 = v6;
        UserData.Reserved = 2;
        v29 = 26;
        v30 = 1;
        EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&ProviderId, 0, 0, 3u, &UserData);
      }
      break;
  }
  v12 = 256;
  v13 = OutputString;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  v14 = 2147483646;
  v15 = 256 - v12;
  if ( v12 )
  {
    v16 = 2147483646;
    v17 = &OutputString[v15];
    v18 = "\n";
    v19 = 256 - v15;
    if ( 256 != v15 )
    {
      do
      {
        if ( !v16 )
          break;
        if ( !*v18 )
          break;
        *v17++ = *v18++;
        --v16;
        --v19;
      }
      while ( v19 );
    }
    v20 = v17 - 1;
    if ( v19 )
      v20 = v17;
    *v20 = 0;
  }
  v21 = OutputString;
  v22 = 80;
  v23 = &(&g_DbgTrace)[10 * (_InterlockedExchangeAdd((volatile signed __int32 *)&g_DbgTracePos, 1u) & 0x7F)];
  do
  {
    if ( !v14 )
      break;
    if ( !*v21 )
      break;
    *(_BYTE *)v23 = *v21++;
    v23 = (char (near **)[80])((char *)v23 + 1);
    --v14;
    --v22;
  }
  while ( v22 );
  v24 = (char (near **)[80])((char *)v23 - 1);
  if ( v22 )
    v24 = v23;
  v25 = g_bDebugSpew == 0;
  *(_BYTE *)v24 = 0;
  if ( !v25 || a1 == 128 )
    OutputDebugStringA(OutputString);
  SetLastError(LastError);
}

```

## disassembly

```asm
0x180003f30  mov     [rsp-8+Format], rdx
0x180003f35  mov     qword ptr [rsp-8+ArgList], r8
0x180003f3a  mov     [rsp-8+arg_18], r9
0x180003f3f  push    rbp
0x180003f40  push    rbx
0x180003f41  push    rsi
0x180003f42  push    rdi
0x180003f43  push    r12
0x180003f45  push    r14
0x180003f47  push    r15
0x180003f49  lea     rbp, [rsp-190h]
0x180003f51  sub     rsp, 290h
0x180003f58  mov     rax, cs:__security_cookie
0x180003f5f  xor     rax, rsp
0x180003f62  mov     [rbp+1C0h+var_40], rax
0x180003f69  cmp     cs:dword_1800877C0, 0
0x180003f70  mov     esi, ecx
0x180003f72  jz      short loc_180003F83
0x180003f74  mov     dl, 1; Wait
0x180003f76  lea     rcx, ?g_ProviderLock@@3VCResource@@A; Resource
0x180003f7d  call    cs:__imp_RtlAcquireResourceExclusive
0x180003f83  cmp     cs:?RegisteredProvider@@3HA, 0; int RegisteredProvider
0x180003f8a  mov     r14d, 1
0x180003f90  jnz     short loc_180004006
0x180003f92  cmp     cs:RegHandle, 0
0x180003f9a  mov     rax, cs:off_180084178
0x180003fa1  movups  xmm0, xmmword ptr [rax-10h]
0x180003fa5  movups  xmmword ptr [rsp+2C0h+ProviderId.Data1], xmm0
0x180003faa  jz      short loc_180003FB3
0x180003fac  mov     ecx, 5
0x180003fb1  int     29h; Win8: RtlFailFast(ecx)
0x180003fb3  xorps   xmm0, xmm0
0x180003fb6  lea     r9, RegHandle; RegHandle
0x180003fbd  lea     r8, dword_180084170; CallbackContext
0x180003fc4  lea     rdx, _tlgEnableCallback; EnableCallback
0x180003fcb  lea     rcx, [rsp+2C0h+ProviderId]; ProviderId
0x180003fd0  movdqu  cs:xmmword_180084198, xmm0
0x180003fd8  call    cs:__imp_EventRegister
0x180003fde  test    eax, eax
0x180003fe0  jnz     short loc_180003FFF
0x180003fe2  mov     r8, cs:off_180084178
0x180003fe9  mov     edx, 2
0x180003fee  mov     rcx, cs:RegHandle
0x180003ff5  movzx   r9d, word ptr [r8]
0x180003ff9  call    cs:__imp_EventSetInformation
0x180003fff  mov     cs:?RegisteredProvider@@3HA, r14d; int RegisteredProvider
0x180004006  cmp     cs:dword_1800877C0, 0
0x18000400d  jz      short loc_18000401C
0x18000400f  lea     rcx, ?g_ProviderLock@@3VCResource@@A; Resource
0x180004016  call    cs:__imp_RtlReleaseResource
0x18000401c  xor     r12d, r12d
0x18000401f  mov     [rsp+2C0h+var_290], r12
0x180004024  call    cs:__imp_GetLastError
0x18000402a  mov     edi, 100h
0x18000402f  mov     r15d, eax
0x180004032  cmp     esi, 80h
0x180004038  jg      loc_1800040C6
0x18000403e  jz      short loc_1800040BD
0x180004040  lea     eax, [rsi-1]; switch 64 cases
0x180004043  cmp     eax, 3Fh
0x180004046  ja      def_180004067; jumptable 0000000180004067 default case, cases 3,5-7,9-15,17-31,33-63
0x18000404c  lea     rdx, __ImageBase
0x180004053  cdqe
0x180004055  movzx   eax, ds:(byte_1800045D8 - 180000000h)[rdx+rax]
0x18000405d  mov     ecx, ds:(jpt_180004067 - 180000000h)[rdx+rax*4]
0x180004064  add     rcx, rdx
0x180004067  jmp     rcx; switch jump
0x180004069  lea     rbx, byte_18006386D; jumptable 0000000180004067 case 2
0x180004070  jmp     loc_180004142
0x180004075  lea     rbx, aInf; jumptable 0000000180004067 case 1
0x18000407c  jmp     loc_180004142
0x180004081  lea     rbx, aWrn; jumptable 0000000180004067 case 4
0x180004088  jmp     loc_180004142
0x18000408d  lea     rbx, aErr; jumptable 0000000180004067 case 8
0x180004094  jmp     loc_180004142
0x180004099  lea     rbx, aDump; jumptable 0000000180004067 case 64
0x1800040a0  jmp     loc_180004142
0x1800040a5  lea     rbx, aBvt; jumptable 0000000180004067 case 16
0x1800040ac  jmp     loc_180004142
0x1800040b1  lea     rbx, aPerf; jumptable 0000000180004067 case 32
0x1800040b8  jmp     loc_180004142
0x1800040bd  lea     rbx, aFatal; "!FATAL!:"
0x1800040c4  jmp     short loc_180004142
0x1800040c6  cmp     esi, 800h
0x1800040cc  jg      short loc_180004108
0x1800040ce  jz      short loc_1800040FF
0x1800040d0  cmp     esi, edi
0x1800040d2  jz      short loc_1800040F6
0x1800040d4  cmp     esi, 200h
0x1800040da  jz      short loc_1800040ED
0x1800040dc  cmp     esi, 400h
0x1800040e2  jnz     short def_180004067; jumptable 0000000180004067 default case, cases 3,5-7,9-15,17-31,33-63
0x1800040e4  lea     rbx, aTsrpc; "TSRPC>>>:"
0x1800040eb  jmp     short loc_180004142
0x1800040ed  lea     rbx, aTsapi; "TSAPI<<<:"
0x1800040f4  jmp     short loc_180004142
0x1800040f6  lea     rbx, aTsapi_0; "TSAPI>>>:"
0x1800040fd  jmp     short loc_180004142
0x1800040ff  lea     rbx, aTsrpc_0; "TSRPC<<<:"
0x180004106  jmp     short loc_180004142
0x180004108  cmp     esi, 1000h
0x18000410e  jz      short loc_18000413B
0x180004110  cmp     esi, 2000h
0x180004116  jz      short loc_180004132
0x180004118  cmp     esi, 4000h
0x18000411e  jz      short loc_180004129
0x180004120  lea     rbx, aUnk; jumptable 0000000180004067 default case, cases 3,5-7,9-15,17-31,33-63
0x180004127  jmp     short loc_180004142
0x180004129  lea     rbx, aVer; "VER:"
0x180004130  jmp     short loc_180004142
0x180004132  lea     rbx, asc_180064068; "<<<:"
0x180004139  jmp     short loc_180004142
0x18000413b  lea     rbx, asc_180064060; ">>>:"
0x180004142  mov     r8, [rbp+1C0h+Format]; Format
0x180004149  lea     r9, [rbp+1C0h+ArgList]; ArgList
0x180004150  mov     edx, 0FFh; BufferCount
0x180004155  lea     rcx, [rbp+1C0h+Buffer]; Buffer
0x18000415c  call    _vsnprintf
0x180004161  test    eax, eax
0x180004163  js      short loc_18000416C
0x180004165  cmp     eax, 0FFh
0x18000416a  jb      short loc_180004173
0x18000416c  mov     [rbp+1C0h+var_41], r12b
0x180004173  lea     rax, [rbp+1C0h+Buffer]
0x18000417a  mov     r9, rbx
0x18000417d  lea     r8, aSS; "%s:%s"
0x180004184  mov     qword ptr [rsp+2C0h+UserDataCount], rax
0x180004189  mov     rdx, rdi; unsigned __int64
0x18000418c  lea     rcx, [rbp+1C0h+OutputString]; char *
0x180004190  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180004195  mov     eax, cs:dword_180084170
0x18000419b  mov     ecx, esi
0x18000419d  mov     [rbp+1C0h+var_141], r12b
0x1800041a1  sub     ecx, r14d
0x1800041a4  jz      loc_1800043F1
0x1800041aa  sub     ecx, 3
0x1800041ad  jz      loc_180004384
0x1800041b3  sub     ecx, 4
0x1800041b6  jz      loc_180004314
0x1800041bc  sub     ecx, 78h ; 'x'
0x1800041bf  jz      loc_1800042A4
0x1800041c5  cmp     ecx, 3F80h
0x1800041cb  jz      short loc_180004235
0x1800041cd  cmp     eax, 5
0x1800041d0  jbe     loc_1800044B0
0x1800041d6  lea     rcx, [rbp+1C0h+OutputString]
0x1800041da  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800041e1  inc     rax
0x1800041e4  cmp     [rcx+rax], r12b
0x1800041e8  jnz     short loc_1800041E1
0x1800041ea  inc     eax
0x1800041ec  mov     [rsp+2C0h+var_24C], r12d
0x1800041f1  mov     [rsp+2C0h+var_250], eax
0x1800041f5  lea     rcx, [rbp+1C0h+OutputString]
0x1800041f9  movzx   eax, cs:word_180078D15
0x180004200  mov     dword ptr [rsp+2C0h+ProviderId.Data2], eax
0x180004204  mov     rax, cs:off_180084178
0x18000420b  mov     [rsp+2C0h+var_278.Ptr], rax
0x180004210  mov     [rsp+2C0h+var_258], rcx
0x180004215  mov     [rsp+2C0h+ProviderId.Data1], 0B000000h
0x18000421d  mov     qword ptr [rsp+2C0h+ProviderId.Data4], r12
0x180004222  movzx   eax, word ptr [rax]
0x180004225  mov     [rsp+2C0h+var_278.Size], eax
0x180004229  lea     rax, byte_180078D1F
0x180004230  jmp     loc_180004454
0x180004235  cmp     eax, 5
0x180004238  jbe     loc_1800044B0
0x18000423e  lea     rcx, [rbp+1C0h+OutputString]
0x180004242  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004249  nop     dword ptr [rax+00000000h]
0x180004250  inc     rax
0x180004253  cmp     [rcx+rax], r12b
0x180004257  jnz     short loc_180004250
0x180004259  inc     eax
0x18000425b  mov     [rsp+2C0h+var_24C], r12d
0x180004260  mov     [rsp+2C0h+var_250], eax
0x180004264  lea     rcx, [rbp+1C0h+OutputString]
0x180004268  movzx   eax, cs:word_180078D87
0x18000426f  mov     dword ptr [rsp+2C0h+ProviderId.Data2], eax
0x180004273  mov     rax, cs:off_180084178
0x18000427a  mov     [rsp+2C0h+var_278.Ptr], rax
0x18000427f  mov     [rsp+2C0h+var_258], rcx
0x180004284  mov     [rsp+2C0h+ProviderId.Data1], 0B000000h
0x18000428c  mov     qword ptr [rsp+2C0h+ProviderId.Data4], r12
0x180004291  movzx   eax, word ptr [rax]
0x180004294  mov     [rsp+2C0h+var_278.Size], eax
0x180004298  lea     rax, byte_180078D91
0x18000429f  jmp     loc_180004454
0x1800042a4  cmp     eax, r14d
0x1800042a7  jbe     loc_1800044B0
0x1800042ad  lea     rcx, [rbp+1C0h+OutputString]
0x1800042b1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800042b8  nop     dword ptr [rax+rax+00000000h]
0x1800042c0  inc     rax
0x1800042c3  cmp     [rcx+rax], r12b
0x1800042c7  jnz     short loc_1800042C0
0x1800042c9  inc     eax
0x1800042cb  mov     [rsp+2C0h+var_24C], r12d
0x1800042d0  mov     [rsp+2C0h+var_250], eax
0x1800042d4  lea     rcx, [rbp+1C0h+OutputString]
0x1800042d8  movzx   eax, cs:word_180078D3B
0x1800042df  mov     dword ptr [rsp+2C0h+ProviderId.Data2], eax
0x1800042e3  mov     rax, cs:off_180084178
0x1800042ea  mov     [rsp+2C0h+var_278.Ptr], rax
0x1800042ef  mov     [rsp+2C0h+var_258], rcx
0x1800042f4  mov     [rsp+2C0h+ProviderId.Data1], 0B000000h
0x1800042fc  mov     qword ptr [rsp+2C0h+ProviderId.Data4], r12
0x180004301  movzx   eax, word ptr [rax]
0x180004304  mov     [rsp+2C0h+var_278.Size], eax
0x180004308  lea     rax, byte_180078D45
0x18000430f  jmp     loc_180004454
0x180004314  cmp     eax, 2
0x180004317  jbe     loc_1800044B0
0x18000431d  lea     rcx, [rbp+1C0h+OutputString]
0x180004321  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004328  nop     dword ptr [rax+rax+00000000h]
0x180004330  inc     rax
0x180004333  cmp     [rcx+rax], r12b
0x180004337  jnz     short loc_180004330
0x180004339  inc     eax
0x18000433b  mov     [rsp+2C0h+var_24C], r12d
0x180004340  mov     [rsp+2C0h+var_250], eax
0x180004344  lea     rcx, [rbp+1C0h+OutputString]
0x180004348  movzx   eax, cs:word_180078CEF
0x18000434f  mov     dword ptr [rsp+2C0h+ProviderId.Data2], eax
0x180004353  mov     rax, cs:off_180084178
0x18000435a  mov     [rsp+2C0h+var_278.Ptr], rax
0x18000435f  mov     [rsp+2C0h+var_258], rcx
0x180004364  mov     [rsp+2C0h+ProviderId.Data1], 0B000000h
0x18000436c  mov     qword ptr [rsp+2C0h+ProviderId.Data4], r12
0x180004371  movzx   eax, word ptr [rax]
0x180004374  mov     [rsp+2C0h+var_278.Size], eax
0x180004378  lea     rax, byte_180078CF9
0x18000437f  jmp     loc_180004454
0x180004384  cmp     eax, 3
0x180004387  jbe     loc_1800044B0
0x18000438d  lea     rcx, [rbp+1C0h+OutputString]
0x180004391  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004398  nop     dword ptr [rax+rax+00000000h]
0x1800043a0  inc     rax
0x1800043a3  cmp     [rcx+rax], r12b
0x1800043a7  jnz     short loc_1800043A0
0x1800043a9  inc     eax
0x1800043ab  mov     [rsp+2C0h+var_24C], r12d
0x1800043b0  mov     [rsp+2C0h+var_250], eax
0x1800043b4  lea     rcx, [rbp+1C0h+OutputString]
0x1800043b8  movzx   eax, cs:word_180078DAD
0x1800043bf  mov     dword ptr [rsp+2C0h+ProviderId.Data2], eax
0x1800043c3  mov     rax, cs:off_180084178
0x1800043ca  mov     [rsp+2C0h+var_278.Ptr], rax
0x1800043cf  mov     [rsp+2C0h+var_258], rcx
0x1800043d4  mov     [rsp+2C0h+ProviderId.Data1], 0B000000h
0x1800043dc  mov     qword ptr [rsp+2C0h+ProviderId.Data4], r12
0x1800043e1  movzx   eax, word ptr [rax]
0x1800043e4  mov     [rsp+2C0h+var_278.Size], eax
0x1800043e8  lea     rax, byte_180078DB7
0x1800043ef  jmp     short loc_180004454
0x1800043f1  cmp     eax, 4
0x1800043f4  jbe     loc_1800044B0
0x1800043fa  lea     rcx, [rbp+1C0h+OutputString]
0x1800043fe  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004405  inc     rax
0x180004408  cmp     [rcx+rax], r12b
0x18000440c  jnz     short loc_180004405
0x18000440e  inc     eax
0x180004410  mov     [rsp+2C0h+var_24C], r12d
0x180004415  mov     [rsp+2C0h+var_250], eax
0x180004419  lea     rcx, [rbp+1C0h+OutputString]
0x18000441d  movzx   eax, cs:word_180078D61
0x180004424  mov     dword ptr [rsp+2C0h+ProviderId.Data2], eax
0x180004428  mov     rax, cs:off_180084178
0x18000442f  mov     [rsp+2C0h+var_278.Ptr], rax
0x180004434  mov     [rsp+2C0h+var_258], rcx
0x180004439  mov     [rsp+2C0h+ProviderId.Data1], 0B000000h
0x180004441  mov     qword ptr [rsp+2C0h+ProviderId.Data4], r12
0x180004446  movzx   eax, word ptr [rax]
0x180004449  mov     [rsp+2C0h+var_278.Size], eax
0x18000444d  lea     rax, byte_180078D6B
0x180004454  mov     [rsp+2C0h+var_268], rax
0x180004459  lea     rcx, _TraceLoggingMetadata
0x180004460  lea     rax, _TraceLoggingMetadataEnd
0x180004467  mov     dword ptr [rsp+2C0h+var_278.0Ch], 2
0x18000446f  sub     eax, ecx
0x180004471  mov     [rsp+2C0h+var_260], 1Ah
0x180004479  mov     [rsp+2C0h+var_25C], r14d
0x18000447e  lea     rdx, [rsp+2C0h+ProviderId]; EventDescriptor
0x180004483  mov     dword ptr [rsp+2C0h+var_290], eax
0x180004487  xor     r9d, r9d; RelatedActivityId
0x18000448a  mov     eax, dword ptr [rsp+2C0h+var_290]
0x18000448e  xor     r8d, r8d; ActivityId
0x180004491  mov     rcx, cs:RegHandle; RegHandle
0x180004498  lea     rax, [rsp+2C0h+var_278]
0x18000449d  mov     [rsp+2C0h+UserData], rax; UserData
0x1800044a2  mov     [rsp+2C0h+UserDataCount], 3; UserDataCount
0x1800044aa  call    cs:__imp_EventWriteTransfer
0x1800044b0  mov     rcx, rdi
0x1800044b3  lea     rax, [rbp+1C0h+OutputString]
0x1800044b7  cmp     [rax], r12b
0x1800044ba  jz      short loc_1800044C4
0x1800044bc  inc     rax
  ... truncated ...
```
