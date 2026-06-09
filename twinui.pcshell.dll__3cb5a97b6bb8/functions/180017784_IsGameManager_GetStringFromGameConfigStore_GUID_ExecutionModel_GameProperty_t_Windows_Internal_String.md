# IsGameManager::GetStringFromGameConfigStore(_GUID,ExecutionModel::GameProperty_t,Windows::Internal::String *)

- ea: `0x180017784`
- end: `0x180017a44`
- name: `?GetStringFromGameConfigStore@IsGameManager@@AEAAJU_GUID@@W4GameProperty_t@ExecutionModel@@PEAVString@Internal@Windows@@@Z`
- size: `704`
- prototype: `int __high(struct _GUID, enum ExecutionModel::GameProperty_t, struct Windows::Internal::String *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180017410`
- `0x180017b50`
- `0x18039b0f0`

## callees

- `0x180017784`
- `0x180017fa0`
- `0x180018484`
- `0x1800237c8`
- `0x180031c70`
- `0x180142cc0`
- `0x18015d210`
- `0x180356360`
- `0x180356760`
- `0x180356edc`
- `0x18039aab8`
- `0x18039ab24`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001785a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001785a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001792a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017938`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001795d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001796b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800179ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001792a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017938`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001795d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001796b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800179ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x180017a09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x180017a09`

## string_xrefs

- `0x18001781d`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsGameManager::GetStringFromGameConfigStore(
        __int64 a1,
        _OWORD *a2,
        unsigned int a3,
        Windows::Internal::String *a4)
{
  unsigned __int16 *v8; // rdi
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // r8d
  HRESULT v12; // eax
  unsigned int v13; // ebx
  int v15; // eax
  wil::details::in1diag3 *v16; // rcx
  __int64 v17; // rdx
  __int64 unique; // rax
  HSTRING v19; // rcx
  HSTRING v20; // rbx
  HRESULT v21; // eax
  int v22; // eax
  unsigned int v23; // esi
  __int64 v24; // rcx
  int *v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v28[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v29[128]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  memset_0(v29, 0, sizeof(v29));
  v26 = 256;
  v8 = 0;
  string = 0;
  Windows::Internal::String::Release(a4);
  v9 = *(_QWORD *)(a1 + 16);
  *(_OWORD *)v28 = *a2;
  v25 = &v26;
  v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, _QWORD, unsigned __int16 *))(*(_QWORD *)v9 + 64LL))(
          v9,
          v28,
          a3,
          v29);
  v11 = (unsigned int)v26 >> 1;
  v26 = 2 * ((unsigned int)v26 >> 1);
  if ( v10 == -2147024774 )
  {
    unique = wil::make_unique_nothrow<unsigned short [0]>(v28, v11);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(&string, unique);
    v19 = v28[0];
    v28[0] = 0;
    if ( v19 )
      operator delete(v19);
    v8 = (unsigned __int16 *)string;
    if ( !string )
    {
      v13 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x573,
        (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
        (const char *)0x8007000ELL,
        (int)&v26);
      return v13;
    }
    v24 = *(_QWORD *)(a1 + 16);
    *(_OWORD *)v28 = *a2;
    v25 = &v26;
    if ( (*(int (__fastcall **)(__int64, HSTRING *, _QWORD, HSTRING))(*(_QWORD *)v24 + 64LL))(v24, v28, a3, string) >= 0 )
    {
      v15 = Windows::Internal::String::Initialize(a4, v8, (unsigned int)v26 >> 1);
      v16 = retaddr;
      if ( v15 < 0 )
      {
        v17 = 1400;
LABEL_9:
        wil::details::in1diag3::_Log_Hr(
          v16,
          (void *)v17,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
          (const char *)(unsigned int)v15,
          (int)&v26);
      }
    }
  }
  else if ( v10 >= 0 )
  {
    v15 = Windows::Internal::String::Initialize(a4, v29, v11);
    v16 = retaddr;
    if ( v15 < 0 )
    {
      v17 = 1405;
      goto LABEL_9;
    }
  }
  v28[0] = 0;
  string = 0;
  v12 = WindowsCreateString(&word_180769B28, 1u, &string);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x586,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)v12,
      (int)v25);
    if ( v8 )
      operator delete(v8);
    return v13;
  }
  v20 = string;
  WindowsDeleteString(0);
  string = 0;
  v21 = WindowsTrimStringEnd(*(HSTRING *)a4, v20, &string);
  if ( (int)Windows::Internal::String::FreeAndAssignOnSuccess(v21, string, v28) < 0
    || (v22 = Windows::Internal::String::Initialize(a4, v28), v23 = v22, v22 >= 0) )
  {
    if ( v28[0] )
      WindowsDeleteString(v28[0]);
    if ( v20 )
      WindowsDeleteString(v20);
    if ( v8 )
      operator delete(v8);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58A,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)v22,
      (int)v25);
    if ( v28[0] )
      WindowsDeleteString(v28[0]);
    if ( v20 )
      WindowsDeleteString(v20);
    if ( v8 )
      operator delete(v8);
    return v23;
  }
}

```

## disassembly

```asm
0x180017784  push    rbp
0x180017786  push    rbx
0x180017787  push    rsi
0x180017788  push    rdi
0x180017789  push    r13
0x18001778b  push    r14
0x18001778d  push    r15
0x18001778f  lea     rbp, [rsp-60h]
0x180017794  sub     rsp, 160h
0x18001779b  mov     rax, cs:__security_cookie
0x1800177a2  xor     rax, rsp
0x1800177a5  mov     [rbp+90h+var_40], rax
0x1800177a9  mov     rsi, r9
0x1800177ac  mov     r15d, r8d
0x1800177af  mov     r14, rdx
0x1800177b2  mov     rbx, rcx
0x1800177b5  mov     edi, 100h
0x1800177ba  mov     r8d, edi; Size
0x1800177bd  xor     edx, edx; Val
0x1800177bf  lea     rcx, [rsp+190h+var_140]; void *
0x1800177c4  call    memset_0
0x1800177c9  mov     [rsp+190h+var_160], edi
0x1800177cd  xor     edi, edi
0x1800177cf  mov     [rsp+190h+string], rdi
0x1800177d4  mov     rcx, rsi; this
0x1800177d7  call    ?Release@String@Internal@Windows@@QEAAXXZ; Windows::Internal::String::Release(void)
0x1800177dc  mov     rcx, [rbx+10h]
0x1800177e0  movaps  xmm0, xmmword ptr [r14]
0x1800177e4  movdqa  xmmword ptr [rsp+190h+var_150], xmm0
0x1800177ea  mov     rax, [rcx]
0x1800177ed  lea     rdx, [rsp+190h+var_160]
0x1800177f2  mov     qword ptr [rsp+190h+var_170], rdx; int
0x1800177f7  lea     r9, [rsp+190h+var_140]
0x1800177fc  mov     r8d, r15d
0x1800177ff  lea     rdx, [rsp+190h+var_150]
0x180017804  mov     rax, [rax+40h]
0x180017808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001780d  mov     r8d, [rsp+190h+var_160]
0x180017812  shr     r8d, 1; unsigned int
0x180017815  lea     ecx, [r8+r8]
0x180017819  mov     [rsp+190h+var_160], ecx
0x18001781d  lea     r13, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180017824  cmp     eax, 8007007Ah
0x180017829  jz      loc_180017986
0x18001782f  test    eax, eax
0x180017831  jns     loc_1800178E6
0x180017837  mov     [rsp+190h+var_150], 0
0x180017840  mov     [rsp+190h+string], 0
0x180017849  lea     r8, [rsp+190h+string]; string
0x18001784e  mov     edx, 1; length
0x180017853  lea     rcx, word_180769B28; sourceString
0x18001785a  call    cs:__imp_WindowsCreateString
0x180017860  mov     ebx, eax
0x180017862  test    eax, eax
0x180017864  jns     loc_1800179E8
0x18001786a  mov     rcx, [rbp+98h]; this
0x180017871  mov     r9d, eax; char *
0x180017874  mov     r8, r13; unsigned int
0x180017877  mov     edx, 586h; void *
0x18001787c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017881  nop
0x180017882  test    rdi, rdi
0x180017885  jz      short loc_18001788F
0x180017887  mov     rcx, rdi; Block
0x18001788a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001788f  mov     eax, ebx
0x180017891  mov     rcx, [rbp+90h+var_40]
0x180017895  xor     rcx, rsp; StackCookie
0x180017898  call    __security_check_cookie
0x18001789d  add     rsp, 160h
0x1800178a4  pop     r15
0x1800178a6  pop     r14
0x1800178a8  pop     r13
0x1800178aa  pop     rdi
0x1800178ab  pop     rsi
0x1800178ac  pop     rbx
0x1800178ad  pop     rbp
0x1800178ae  retn
0x1800178af  mov     r8d, [rsp+190h+var_160]
0x1800178b4  shr     r8d, 1; unsigned int
0x1800178b7  mov     rdx, rdi; unsigned __int16 *
0x1800178ba  mov     rcx, rsi; this
0x1800178bd  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x1800178c2  mov     rcx, [rbp+98h]; this
0x1800178c9  test    eax, eax
0x1800178cb  jns     loc_180017837
0x1800178d1  mov     edx, 578h; void *
0x1800178d6  mov     r9d, eax; char *
0x1800178d9  mov     r8, r13; unsigned int
0x1800178dc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800178e1  jmp     loc_180017837
0x1800178e6  lea     rdx, [rsp+190h+var_140]; unsigned __int16 *
0x1800178eb  mov     rcx, rsi; this
0x1800178ee  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x1800178f3  mov     rcx, [rbp+98h]
0x1800178fa  test    eax, eax
0x1800178fc  jns     loc_180017837
0x180017902  mov     edx, 57Dh
0x180017907  jmp     short loc_1800178D6
0x180017909  mov     rcx, [rbp+98h]; this
0x180017910  mov     r9d, esi; char *
0x180017913  mov     r8, r13; unsigned int
0x180017916  mov     edx, 58Ah; void *
0x18001791b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017920  mov     rcx, [rsp+190h+var_150]; string
0x180017925  test    rcx, rcx
0x180017928  jz      short loc_180017930
0x18001792a  call    cs:__imp_WindowsDeleteString
0x180017930  test    rbx, rbx
0x180017933  jz      short loc_18001793F
0x180017935  mov     rcx, rbx; string
0x180017938  call    cs:__imp_WindowsDeleteString
0x18001793e  nop
0x18001793f  test    rdi, rdi
0x180017942  jz      short loc_18001794C
0x180017944  mov     rcx, rdi; Block
0x180017947  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001794c  mov     eax, esi
0x18001794e  jmp     loc_180017891
0x180017953  mov     rcx, [rsp+190h+var_150]; string
0x180017958  test    rcx, rcx
0x18001795b  jz      short loc_180017963
0x18001795d  call    cs:__imp_WindowsDeleteString
0x180017963  test    rbx, rbx
0x180017966  jz      short loc_180017972
0x180017968  mov     rcx, rbx; string
0x18001796b  call    cs:__imp_WindowsDeleteString
0x180017971  nop
0x180017972  test    rdi, rdi
0x180017975  jz      short loc_18001797F
0x180017977  mov     rcx, rdi; Block
0x18001797a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001797f  xor     eax, eax
0x180017981  jmp     loc_180017891
0x180017986  mov     edx, r8d
0x180017989  lea     rcx, [rsp+190h+var_150]
0x18001798e  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180017993  mov     rdx, rax
0x180017996  lea     rcx, [rsp+190h+string]
0x18001799b  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x1800179a0  mov     rcx, [rsp+190h+var_150]; Block
0x1800179a5  mov     [rsp+190h+var_150], 0
0x1800179ae  test    rcx, rcx
0x1800179b1  jz      short loc_1800179B8
0x1800179b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800179b8  mov     rdi, [rsp+190h+string]
0x1800179bd  test    rdi, rdi
0x1800179c0  jnz     loc_1806EC41C
0x1800179c6  mov     rcx, [rbp+98h]; this
0x1800179cd  mov     ebx, 8007000Eh
0x1800179d2  mov     r9d, ebx; char *
0x1800179d5  mov     r8, r13; unsigned int
0x1800179d8  mov     edx, 573h; void *
0x1800179dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800179e2  nop
0x1800179e3  jmp     loc_18001788F
0x1800179e8  mov     rbx, [rsp+190h+string]
0x1800179ed  xor     ecx, ecx; string
0x1800179ef  call    cs:__imp_WindowsDeleteString
0x1800179f5  mov     [rsp+190h+string], 0
0x1800179fe  lea     r8, [rsp+190h+string]; newString
0x180017a03  mov     rdx, rbx; trimString
0x180017a06  mov     rcx, [rsi]; string
0x180017a09  call    cs:__imp_WindowsTrimStringEnd
0x180017a0f  lea     r8, [rsp+190h+var_150]; HSTRING *
0x180017a14  mov     rdx, [rsp+190h+string]; HSTRING
0x180017a19  mov     ecx, eax; int
0x180017a1b  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x180017a20  test    eax, eax
0x180017a22  js      loc_180017953
0x180017a28  lea     rdx, [rsp+190h+var_150]; HSTRING *
0x180017a2d  mov     rcx, rsi; this
0x180017a30  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180017a35  mov     esi, eax
0x180017a37  test    eax, eax
0x180017a39  jns     loc_180017953
0x180017a3f  jmp     loc_180017909
0x1806ec41c  mov     rcx, [rbx+10h]
0x1806ec420  movaps  xmm0, xmmword ptr [r14]
0x1806ec424  movdqa  xmmword ptr [rsp+190h+var_150], xmm0
0x1806ec42a  mov     rax, [rcx]
0x1806ec42d  lea     rdx, [rsp+190h+var_160]
0x1806ec432  mov     qword ptr [rsp+190h+var_170], rdx; int
0x1806ec437  mov     r9, rdi
0x1806ec43a  mov     r8d, r15d
0x1806ec43d  lea     rdx, [rsp+190h+var_150]
0x1806ec442  mov     rax, [rax+40h]
0x1806ec446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806ec44b  test    eax, eax
0x1806ec44d  js      loc_180017837
0x1806ec453  jmp     loc_1800178AF
```
