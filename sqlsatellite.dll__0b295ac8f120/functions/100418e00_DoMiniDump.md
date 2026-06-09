# DoMiniDump

- ea: `0x100418e00`
- end: `0x10041917c`
- name: `DoMiniDump`
- size: `892`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, unsigned __int64@<rdx>, struct _CONTEXT *@<r8>, __int64, wchar_t *, __int64, int, int, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1004191d0`
- `0x100419360`

## callees

- `0x100418e00`
- `0x10045d480`
- `0x1004646c0`
- `0x100467ea0`
- `0x100486af0`
- `0x100487cd6`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x100419126`
- `KERNEL32!FormatMessageW` at `0x100419126`
- `KERNEL32!CloseHandle` at `0x1004190ef`
- `KERNEL32!CloseHandle` at `0x1004190ef`
- `KERNEL32!GetLastError` at `0x1004190d2`
- `KERNEL32!GetLastError` at `0x1004190d2`
- `sqldk!?GetCurrentNtToken@SOS_OS@@SA?AW4SOS_RESULT@@PEAPEAX@Z` at `0x100418fe3`
- `sqldk!?GetCurrentNtToken@SOS_OS@@SA?AW4SOS_RESULT@@PEAPEAX@Z` at `0x100418fe3`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100418ed1`
- `sqldk!?ResetStackOverflow@SOS_OS@@SA?AW4SOS_RESULT@@XZ` at `0x100418f0a`
- `sqldk!?ResetStackOverflow@SOS_OS@@SA?AW4SOS_RESULT@@XZ` at `0x100418f0a`
- `ADVAPI32!RevertToSelf` at `0x100418ff8`
- `ADVAPI32!RevertToSelf` at `0x100418ff8`
- `ADVAPI32!SetThreadToken` at `0x1004190c8`
- `ADVAPI32!SetThreadToken` at `0x1004190c8`

## string_xrefs

- `0x100418f56`: `Unable to create dump because SQLDUMPER library is not available.\n`

## pseudocode

```c
__int64 __fastcall DoMiniDump(
        unsigned int a1,
        unsigned __int64 a2,
        struct _CONTEXT *a3,
        struct _EXCEPTION_RECORD *a4,
        wchar_t *a5,
        wchar_t *a6,
        wchar_t *a7,
        int a8,
        unsigned int a9,
        struct _GUID *a10)
{
  signed int v14; // ebx
  unsigned int *v15; // r9
  unsigned int v16; // ebx
  signed int LastError; // eax
  DWORD v18; // eax
  unsigned int *nSize; // [rsp+28h] [rbp-B60h]
  unsigned int v20; // [rsp+A0h] [rbp-AE8h] BYREF
  unsigned int v21; // [rsp+A8h] [rbp-AE0h] BYREF
  HANDLE Token; // [rsp+B0h] [rbp-AD8h] BYREF
  _DWORD v23[2]; // [rsp+B8h] [rbp-AD0h] BYREF
  struct _GUID *v24; // [rsp+C0h] [rbp-AC8h]
  wchar_t *v25; // [rsp+D0h] [rbp-AB8h]
  wchar_t *v26; // [rsp+D8h] [rbp-AB0h]
  struct _EXCEPTION_RECORD *v27; // [rsp+E0h] [rbp-AA8h]
  struct IDmpDump *v28; // [rsp+E8h] [rbp-AA0h] BYREF
  unsigned int v29; // [rsp+F8h] [rbp-A90h] BYREF
  unsigned __int64 v30; // [rsp+100h] [rbp-A88h]
  struct _CONTEXT *v31; // [rsp+108h] [rbp-A80h]
  struct _EXCEPTION_RECORD *v32; // [rsp+110h] [rbp-A78h]
  wchar_t *v33; // [rsp+120h] [rbp-A68h]
  wchar_t v34[264]; // [rsp+130h] [rbp-A58h] BYREF
  WCHAR Buffer[1024]; // [rsp+340h] [rbp-848h] BYREF

  v27 = a4;
  v23[1] = a9;
  v20 = a1;
  v30 = a2;
  v31 = a3;
  v32 = a4;
  v26 = a5;
  v33 = a6;
  v25 = a7;
  v24 = a10;
  v21 = 0;
  memset_0(v34, 0, 0x208u);
  v23[0] = 520;
  (*(void (__fastcall **)(struct IServerConfiguration *, wchar_t *, _DWORD *))(*(_QWORD *)s_pServerConf + 104LL))(
    s_pServerConf,
    v34,
    v23);
  StackDumpScErrLog(L"Stack Signature for the dump is 0x%p\n", a2);
  if ( qword_100556E18 )
  {
    v28 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, struct IDmpDump **))(*(_QWORD *)qword_100556E18 + 40LL))(
            qword_100556E18,
            &v28);
    if ( v14 >= 0 )
    {
      v20 = a9;
      AdjustDumpFlags(a8, a6, &v20, v15, &v21, nSize);
      v16 = v20 | 0x400000;
      Token = 0;
      if ( !(unsigned int)SOS_OS::GetCurrentNtToken(&Token) && Token && !RevertToSelf() )
        StackDumpScErrLog(L"Failed in RevertToSelf.\r\n");
      v14 = SQLDumperLibraryInvoke(
              v28,
              a1,
              a2,
              a3,
              v27,
              v26,
              a6,
              v25,
              v34,
              0,
              v16,
              0,
              v21,
              0,
              v24,
              &v29,
              Buffer,
              0x400u,
              1);
      if ( Token )
      {
        if ( !SetThreadToken(0, Token) )
        {
          LastError = GetLastError();
          v14 = LastError;
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
        }
        CloseHandle(Token);
      }
      if ( v14 < 0 )
      {
        _mm_lfence();
        v18 = FormatMessageW(0x1000u, 0, v14, 0x400u, Buffer, 0x400u, 0);
        _mm_lfence();
        if ( v18 )
          StackDumpScErrLog(L"DoMiniDump () encountered error (0x%X) - %ls\n", (unsigned int)v14, Buffer);
        else
          StackDumpScErrLog(L"DoMiniDump () encountered error (0x%X)\n", (unsigned int)v14);
      }
    }
    else
    {
      _mm_lfence();
      StackDumpScErrLog(L"Unable to obtain SQLDUMPER dump object.\r\n");
    }
    return (unsigned int)v14;
  }
  else
  {
    StackDumpScErrLog(L"Unable to create dump because SQLDUMPER library is not available.\n");
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x100418e00  push    rbx
0x100418e02  push    rsi
0x100418e03  push    rdi
0x100418e04  push    r12
0x100418e06  push    r13
0x100418e08  push    r14
0x100418e0a  push    r15
0x100418e0c  sub     rsp, 0B50h
0x100418e13  mov     rax, cs:__security_cookie
0x100418e1a  xor     rax, rsp
0x100418e1d  mov     [rsp+0B88h+var_48], rax
0x100418e25  mov     rbx, r9
0x100418e28  mov     [rsp+0B88h+var_AA8], rbx
0x100418e30  mov     r13, r8
0x100418e33  mov     rsi, rdx
0x100418e36  mov     r12d, ecx
0x100418e39  mov     r15d, [rsp+0B88h+arg_40]
0x100418e41  mov     [rsp+0B88h+var_ACC], r15d
0x100418e49  mov     [rsp+0B88h+var_AE8], ecx
0x100418e50  mov     [rsp+0B88h+var_A88], rdx
0x100418e58  mov     [rsp+0B88h+var_A80], r8
0x100418e60  mov     [rsp+0B88h+var_A78], rbx
0x100418e68  mov     rbx, [rsp+0B88h+arg_20]
0x100418e70  mov     [rsp+0B88h+var_AB0], rbx
0x100418e78  mov     r14, [rsp+0B88h+arg_28]
0x100418e80  mov     [rsp+0B88h+var_A68], r14
0x100418e88  mov     rbx, [rsp+0B88h+arg_30]
0x100418e90  mov     [rsp+0B88h+var_AB8], rbx
0x100418e98  mov     rbx, [rsp+0B88h+arg_48]
0x100418ea0  mov     [rsp+0B88h+var_AC8], rbx
0x100418ea8  xor     edi, edi
0x100418eaa  mov     [rsp+0B88h+var_AE0], edi
0x100418eb1  xor     edx, edx; Val
0x100418eb3  mov     r8d, 208h; Size
0x100418eb9  lea     rcx, [rsp+0B88h+var_A58]; void *
0x100418ec1  call    memset_0
0x100418ec6  mov     [rsp+0B88h+var_AD0], 208h
0x100418ed1  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100418ed8  mov     rcx, [rax]
0x100418edb  mov     rax, [rcx]
0x100418ede  lea     r8, [rsp+0B88h+var_AD0]
0x100418ee6  lea     rdx, [rsp+0B88h+var_A58]
0x100418eee  call    qword ptr [rax+68h]
0x100418ef1  nop
0x100418ef2  mov     rdx, rsi
0x100418ef5  lea     rcx, aStackSignature; "Stack Signature for the dump is 0x%p\n"
0x100418efc  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x100418f01  jmp     short loc_100418F4A
0x100418f03  cmp     eax, 0C00000FDh
0x100418f08  jnz     short loc_100418F10
0x100418f0a  call    cs:__imp_?ResetStackOverflow@SOS_OS@@SA?AW4SOS_RESULT@@XZ; SOS_OS::ResetStackOverflow(void)
0x100418f10  xor     edi, edi
0x100418f12  mov     r12d, [rsp+0B88h+var_AE8]
0x100418f1a  mov     rsi, [rsp+0B88h+var_A88]
0x100418f22  mov     r13, [rsp+0B88h+var_A80]
0x100418f2a  mov     rax, [rsp+0B88h+var_A78]
0x100418f32  mov     [rsp+0B88h+var_AA8], rax
0x100418f3a  mov     r14, [rsp+0B88h+var_A68]
0x100418f42  mov     r15d, [rsp+0B88h+var_ACC]
0x100418f4a  mov     rcx, cs:qword_100556E18
0x100418f51  test    rcx, rcx
0x100418f54  jnz     short loc_100418F6C
0x100418f56  lea     rcx, aUnableToCreate; "Unable to create dump because SQLDUMPER"...
0x100418f5d  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x100418f62  mov     eax, 80004005h
0x100418f67  jmp     loc_100419159
0x100418f6c  mov     [rsp+0B88h+var_AA0], rdi
0x100418f74  mov     rax, [rcx]
0x100418f77  lea     rdx, [rsp+0B88h+var_AA0]
0x100418f7f  call    qword ptr [rax+28h]
0x100418f82  mov     ebx, eax
0x100418f84  test    eax, eax
0x100418f86  jns     short loc_100418F9C
0x100418f88  lfence
0x100418f8b  lea     rcx, aUnableToObtain; "Unable to obtain SQLDUMPER dump object."...
0x100418f92  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x100418f97  jmp     loc_100419157
0x100418f9c  mov     [rsp+0B88h+var_AE8], r15d
0x100418fa4  lea     rax, [rsp+0B88h+var_AE0]
0x100418fac  mov     [rsp+0B88h+lpBuffer], rax; unsigned int *
0x100418fb1  lea     r8, [rsp+0B88h+var_AE8]; unsigned int *
0x100418fb9  mov     rdx, r14; wchar_t *
0x100418fbc  mov     ecx, [rsp+0B88h+arg_38]; int
0x100418fc3  call    ?AdjustDumpFlags@@YAXHPEB_WPEAK111@Z; AdjustDumpFlags(int,wchar_t const *,ulong *,ulong *,ulong *,ulong *)
0x100418fc8  mov     ebx, [rsp+0B88h+var_AE8]
0x100418fcf  bts     ebx, 16h
0x100418fd3  mov     [rsp+0B88h+Token], rdi
0x100418fdb  lea     rcx, [rsp+0B88h+Token]
0x100418fe3  call    cs:__imp_?GetCurrentNtToken@SOS_OS@@SA?AW4SOS_RESULT@@PEAPEAX@Z; SOS_OS::GetCurrentNtToken(void * *)
0x100418fe9  test    eax, eax
0x100418feb  jnz     short loc_10041900E
0x100418fed  cmp     [rsp+0B88h+Token], 0
0x100418ff6  jz      short loc_10041900E
0x100418ff8  call    cs:__imp_RevertToSelf
0x100418ffe  test    eax, eax
0x100419000  jnz     short loc_10041900E
0x100419002  lea     rcx, aFailedInRevert; "Failed in RevertToSelf.\r\n"
0x100419009  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x10041900e  mov     [rsp+0B88h+var_AF8], 1; bool
0x100419016  mov     [rsp+0B88h+var_B00], 400h; unsigned __int64
0x100419022  lea     rax, [rsp+0B88h+Buffer]
0x10041902a  mov     [rsp+0B88h+var_B08], rax; wchar_t *
0x100419032  lea     rax, [rsp+0B88h+var_A90]
0x10041903a  mov     [rsp+0B88h+var_B10], rax; unsigned int *
0x10041903f  mov     rax, [rsp+0B88h+var_AC8]
0x100419047  mov     [rsp+0B88h+var_B18], rax; struct _GUID *
0x10041904c  mov     [rsp+0B88h+var_B20], edi; unsigned int
0x100419050  mov     eax, [rsp+0B88h+var_AE0]
0x100419057  mov     [rsp+0B88h+var_B28], eax; unsigned int
0x10041905b  mov     [rsp+0B88h+var_B30], edi; unsigned int
0x10041905f  mov     [rsp+0B88h+var_B38], ebx; unsigned int
0x100419063  mov     [rsp+0B88h+var_B40], rdi; wchar_t *
0x100419068  lea     rax, [rsp+0B88h+var_A58]
0x100419070  mov     [rsp+0B88h+var_B48], rax; wchar_t *
0x100419075  mov     rax, [rsp+0B88h+var_AB8]
0x10041907d  mov     [rsp+0B88h+var_B50], rax; wchar_t *
0x100419082  mov     [rsp+0B88h+Arguments], r14; wchar_t *
0x100419087  mov     rax, [rsp+0B88h+var_AB0]
0x10041908f  mov     qword ptr [rsp+0B88h+nSize], rax; wchar_t *
0x100419094  mov     rax, [rsp+0B88h+var_AA8]
0x10041909c  mov     [rsp+0B88h+lpBuffer], rax; struct _EXCEPTION_RECORD *
0x1004190a1  mov     r9, r13; struct _CONTEXT *
0x1004190a4  mov     r8, rsi; unsigned __int64
0x1004190a7  mov     edx, r12d; unsigned int
0x1004190aa  mov     rcx, [rsp+0B88h+var_AA0]; struct IDmpDump *
0x1004190b2  call    ?SQLDumperLibraryInvoke@@YAJPEAUIDmpDump@@K_KQEAU_CONTEXT@@QEAU_EXCEPTION_RECORD@@QEB_W4444KKKKPEBU_GUID@@PEAKPEA_W_K_N@Z; SQLDumperLibraryInvoke(IDmpDump *,ulong,unsigned __int64,_CONTEXT * const,_EXCEPTION_RECORD * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,ulong,ulong,ulong,ulong,_GUID const *,ulong *,wchar_t *,unsigned __int64,bool)
0x1004190b7  mov     ebx, eax
0x1004190b9  mov     rdx, [rsp+0B88h+Token]; Token
0x1004190c1  test    rdx, rdx
0x1004190c4  jz      short loc_1004190F5
0x1004190c6  xor     ecx, ecx; Thread
0x1004190c8  call    cs:__imp_SetThreadToken
0x1004190ce  test    eax, eax
0x1004190d0  jnz     short loc_1004190E7
0x1004190d2  call    cs:__imp_GetLastError
0x1004190d8  mov     ebx, eax
0x1004190da  test    eax, eax
0x1004190dc  jle     short loc_1004190E7
0x1004190de  movzx   ebx, ax
0x1004190e1  or      ebx, 80070000h
0x1004190e7  mov     rcx, [rsp+0B88h+Token]; hObject
0x1004190ef  call    cs:__imp_CloseHandle
0x1004190f5  test    ebx, ebx
0x1004190f7  jns     short loc_100419157
0x1004190f9  lfence
0x1004190fc  mov     [rsp+0B88h+Arguments], rdi; Arguments
0x100419101  mov     [rsp+0B88h+nSize], 400h; nSize
0x100419109  lea     rax, [rsp+0B88h+Buffer]
0x100419111  mov     [rsp+0B88h+lpBuffer], rax; lpBuffer
0x100419116  mov     r9d, 400h; dwLanguageId
0x10041911c  mov     r8d, ebx; dwMessageId
0x10041911f  xor     edx, edx; lpSource
0x100419121  mov     ecx, 1000h; dwFlags
0x100419126  call    cs:__imp_FormatMessageW
0x10041912c  lfence
0x10041912f  mov     edx, ebx
0x100419131  test    eax, eax
0x100419133  jz      short loc_10041914B
0x100419135  lea     r8, [rsp+0B88h+Buffer]
0x10041913d  lea     rcx, aDominidumpEnco; "DoMiniDump () encountered error (0x%X) "...
0x100419144  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x100419149  jmp     short loc_100419157
0x10041914b  lea     rcx, aDominidumpEnco_0; "DoMiniDump () encountered error (0x%X)"...
0x100419152  call    ?StackDumpScErrLog@@YAXPEB_WZZ; StackDumpScErrLog(wchar_t const *,...)
0x100419157  mov     eax, ebx
0x100419159  mov     rcx, [rsp+0B88h+var_48]
0x100419161  xor     rcx, rsp; StackCookie
0x100419164  call    __security_check_cookie
0x100419169  add     rsp, 0B50h
0x100419170  pop     r15
0x100419172  pop     r14
0x100419174  pop     r13
0x100419176  pop     r12
0x100419178  pop     rdi
0x100419179  pop     rsi
0x10041917a  pop     rbx
0x10041917b  retn
```
