# ComputeService::JobUtilities::ConvertJobObjectToContainer(void *,Schema::Containers::Definition::Container const &,bool)

- ea: `0x1400dbe7c`
- end: `0x1400dbf9a`
- name: `?ConvertJobObjectToContainer@JobUtilities@ComputeService@@YAXPEAXAEBUContainer@Definition@Containers@Schema@@_N@Z`
- size: `286`
- prototype: `void __fastcall(ComputeService::JobUtilities *__hidden this, void *, const struct Schema::Containers::Definition::Container *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400d3e5c`

## callees

- `0x140005360`
- `0x140008760`
- `0x14000ea60`
- `0x1400cd404`
- `0x1400dbe7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400dbf18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400dbf18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400dbf05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400dbf05`
- `container!WcCreateContainer` at `0x1400dbf2b`
- `container!WcCreateContainer` at `0x1400dbf2b`
- `container!WcDestroyDescription` at `0x1400dbf10`
- `container!WcDestroyDescription` at `0x1400dbf42`
- `container!WcDestroyDescription` at `0x1400dbf10`
- `container!WcDestroyDescription` at `0x1400dbf42`
- `container!WcCreateDescriptionFromXml` at `0x1400dbedd`
- `container!WcCreateDescriptionFromXml` at `0x1400dbedd`

## string_xrefs

- `0x1400dbf73`: `onecore\vm\compute\management\shared\container\jobutilities.cpp`
- `0x1400dbf88`: `onecore\vm\compute\management\shared\container\jobutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ComputeService::JobUtilities::ConvertJobObjectToContainer(
        ComputeService::JobUtilities *this,
        void *a2,
        const struct Schema::Containers::Definition::Container *a3)
{
  char v3; // r12
  _QWORD *v5; // rcx
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // r14
  __int64 v9; // rsi
  DWORD LastError; // ebx
  int Container; // eax
  int v12; // [rsp+20h] [rbp-60h]
  __int64 v13; // [rsp+38h] [rbp-48h] BYREF
  char v14; // [rsp+40h] [rbp-40h]
  __int64 v15; // [rsp+48h] [rbp-38h]
  _QWORD v16[4]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v3 = (char)a3;
  Marshal::ToXmlString<Schema::Containers::Definition::Container const &,>(v16, (int)a2);
  v15 = 0;
  v13 = 0;
  v14 = 1;
  v5 = v16;
  if ( v16[3] > 7u )
    v5 = (_QWORD *)v16[0];
  v6 = WcCreateDescriptionFromXml(v5, &v13);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\jobutilities.cpp",
      (const char *)(unsigned int)v6,
      v12);
  if ( v14 )
  {
    v8 = v13;
    v9 = v15;
    if ( v15 )
    {
      LastError = GetLastError();
      WcDestroyDescription(v9);
      SetLastError(LastError);
    }
    v15 = v8;
  }
  LOBYTE(v7) = v3;
  Container = WcCreateContainer(this, v15, v7);
  if ( Container < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\jobutilities.cpp",
      (const char *)(unsigned int)Container,
      v12);
  if ( v15 )
    WcDestroyDescription(v15);
  std::wstring::~wstring(v16);
}

```

## disassembly

```asm
0x1400dbe7c  push    rbp
0x1400dbe7e  push    rbx
0x1400dbe7f  push    rsi
0x1400dbe80  push    rdi
0x1400dbe81  push    r12
0x1400dbe83  push    r14
0x1400dbe85  push    r15
0x1400dbe87  mov     rbp, rsp
0x1400dbe8a  sub     rsp, 80h
0x1400dbe91  mov     rax, cs:__security_cookie
0x1400dbe98  xor     rax, rsp
0x1400dbe9b  mov     [rbp+var_10], rax
0x1400dbe9f  mov     r12b, r8b
0x1400dbea2  mov     r15, rcx
0x1400dbea5  lea     rcx, [rbp+var_30]
0x1400dbea9  call    ??$ToXmlString@AEBUContainer@Definition@Containers@Schema@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUContainer@Definition@Containers@Schema@@PEBG_NW4MarshalFlags@0@@Z; Marshal::ToXmlString<Schema::Containers::Definition::Container const &,>(Schema::Containers::Definition::Container const &,ushort const *,bool,Marshal::MarshalFlags)
0x1400dbeae  nop
0x1400dbeaf  mov     [rbp+var_38], 0
0x1400dbeb7  lea     rax, [rbp+var_38]
0x1400dbebb  mov     [rbp+var_50], rax
0x1400dbebf  mov     [rbp+var_48], 0
0x1400dbec7  mov     [rbp+var_40], 1
0x1400dbecb  lea     rcx, [rbp+var_30]
0x1400dbecf  cmp     [rbp+var_18], 7
0x1400dbed4  cmova   rcx, [rbp+var_30]
0x1400dbed9  lea     rdx, [rbp+var_48]
0x1400dbedd  call    cs:__imp_WcCreateDescriptionFromXml
0x1400dbee3  mov     rcx, [rbp+38h]; this
0x1400dbee7  test    eax, eax
0x1400dbee9  js      loc_1400DBF85
0x1400dbeef  cmp     [rbp+var_40], 0
0x1400dbef3  jz      short loc_1400DBF21
0x1400dbef5  mov     r14, [rbp+var_48]
0x1400dbef9  mov     rdi, [rbp+var_50]
0x1400dbefd  mov     rsi, [rdi]
0x1400dbf00  test    rsi, rsi
0x1400dbf03  jz      short loc_1400DBF1E
0x1400dbf05  call    cs:__imp_GetLastError
0x1400dbf0b  mov     ebx, eax
0x1400dbf0d  mov     rcx, rsi
0x1400dbf10  call    cs:__imp_WcDestroyDescription
0x1400dbf16  mov     ecx, ebx; dwErrCode
0x1400dbf18  call    cs:__imp_SetLastError
0x1400dbf1e  mov     [rdi], r14
0x1400dbf21  mov     r8b, r12b
0x1400dbf24  mov     rdx, [rbp+var_38]
0x1400dbf28  mov     rcx, r15
0x1400dbf2b  call    cs:__imp_WcCreateContainer
0x1400dbf31  mov     rcx, [rbp+38h]; this
0x1400dbf35  test    eax, eax
0x1400dbf37  js      short loc_1400DBF70
0x1400dbf39  mov     rcx, [rbp+var_38]
0x1400dbf3d  test    rcx, rcx
0x1400dbf40  jz      short loc_1400DBF49
0x1400dbf42  call    cs:__imp_WcDestroyDescription
0x1400dbf48  nop
0x1400dbf49  lea     rcx, [rbp+var_30]; void *
0x1400dbf4d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400dbf52  mov     rcx, [rbp+var_10]
0x1400dbf56  xor     rcx, rsp; StackCookie
0x1400dbf59  call    __security_check_cookie
0x1400dbf5e  add     rsp, 80h
0x1400dbf65  pop     r15
0x1400dbf67  pop     r14
0x1400dbf69  pop     r12
0x1400dbf6b  pop     rdi
0x1400dbf6c  pop     rsi
0x1400dbf6d  pop     rbx
0x1400dbf6e  pop     rbp
0x1400dbf6f  retn
0x1400dbf70  mov     r9d, eax; char *
0x1400dbf73  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\management\\share"...
0x1400dbf7a  mov     edx, 39h ; '9'; void *
0x1400dbf7f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400dbf85  mov     r9d, eax; char *
0x1400dbf88  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\management\\share"...
0x1400dbf8f  mov     edx, 37h ; '7'; void *
0x1400dbf94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
