# OSDeploymentInformationFactory::StartJITCOMServer(void)

- ea: `0x1400197cc`
- end: `0x14001999a`
- name: `?StartJITCOMServer@OSDeploymentInformationFactory@@QEAAJXZ`
- size: `462`
- prototype: `__int64 __fastcall(OSDeploymentInformationFactory *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140011f2c`

## callees

- `0x140002ac0`
- `0x14000bf4c`
- `0x14000fd28`
- `0x14001095c`
- `0x1400197cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14001984a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400198c2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14001984a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400198c2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14001980b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x140019883`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14001980b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x140019883`

## string_xrefs

- `0x1400198d8`: `Registering OSDeploymentInformationFactory COM server as CLSID %ws and APPID %ws`
- `0x140019953`: `Successfully registered OSDeploymentInformationFactory COM server`

## pseudocode

```c
__int64 __fastcall OSDeploymentInformationFactory::StartJITCOMServer(OSDeploymentInformationFactory *this)
{
  const GUID *v1; // rdi
  HRESULT Guid; // eax
  unsigned int v4; // esi
  __int64 result; // rax
  __int64 v6; // rdx
  HRESULT v7; // edi
  __int64 v8; // rdx
  int v9; // edx
  int v10; // ecx
  int v11; // r9d
  __int64 v12; // rax
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = (const GUID *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) == *(_QWORD *)&GUID_NULL.Data1 && *((_QWORD *)this + 2) == *(_QWORD *)GUID_NULL.Data4 )
  {
    Guid = CoCreateGuid((GUID *)((char *)this + 8));
    v4 = Guid;
    if ( Guid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x130,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentInfo"
                      "rmationFactory.cpp",
        (const char *)(unsigned int)Guid,
        v13);
      return v4;
    }
  }
  if ( !StringFromGUID2(v1, (LPOLESTR)this + 149, 39) )
  {
    v6 = 308;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentInform"
                    "ationFactory.cpp",
      (const char *)0x8007007ALL,
      v13);
    return 2147942522LL;
  }
  v7 = CoCreateGuid((GUID *)((char *)this + 376));
  if ( v7 < 0 )
  {
    v8 = 311;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentInform"
                    "ationFactory.cpp",
      (const char *)(unsigned int)v7,
      v13);
    return (unsigned int)v7;
  }
  if ( !StringFromGUID2((const GUID *const)((char *)this + 376), (LPOLESTR)this + 196, 39) )
  {
    v6 = 313;
    goto LABEL_7;
  }
  WUTrace(0, 0, 4096, 4);
  v12 = -1;
  do
    ++v12;
  while ( *((_WORD *)this + v12 + 196) );
  v7 = RegSetValue_Helper(v10, v9, (int)this + 298, v11, 0, (BYTE *)this + 392, 2 * (int)v12 + 2);
  if ( v7 < 0 )
  {
    v8 = 326;
    goto LABEL_10;
  }
  v7 = CWuaClassFactoryBase::RegisterClassFactory(this);
  if ( v7 < 0 )
  {
    v8 = 328;
    goto LABEL_10;
  }
  WUTrace(0, 0, 4096, 4);
  result = 0;
  *((_BYTE *)this + 296) = 1;
  return result;
}

```

## disassembly

```asm
0x1400197cc  mov     rax, rsp
0x1400197cf  mov     [rax+8], rbx
0x1400197d3  mov     [rax+10h], rbp
0x1400197d7  mov     [rax+18h], rsi
0x1400197db  mov     [rax+20h], rdi
0x1400197df  push    r14
0x1400197e1  sub     rsp, 40h
0x1400197e5  lea     rdi, [rcx+8]
0x1400197e9  xor     r14d, r14d
0x1400197ec  mov     rax, [rdi]
0x1400197ef  mov     rbx, rcx
0x1400197f2  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1400197f9  jnz     short loc_140019837
0x1400197fb  mov     rax, [rdi+8]
0x1400197ff  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x140019806  jnz     short loc_140019837
0x140019808  mov     rcx, rdi; pguid
0x14001980b  call    cs:__imp_CoCreateGuid
0x140019811  mov     esi, eax
0x140019813  test    eax, eax
0x140019815  jns     short loc_140019837
0x140019817  mov     rcx, [rsp+48h]; this
0x14001981c  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140019823  mov     r9d, eax; char *
0x140019826  mov     edx, 130h; void *
0x14001982b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019830  mov     eax, esi
0x140019832  jmp     loc_14001997F
0x140019837  lea     rbp, [rbx+12Ah]
0x14001983e  mov     r8d, 27h ; '''; cchMax
0x140019844  mov     rdx, rbp; lpsz
0x140019847  mov     rcx, rdi; rguid
0x14001984a  call    cs:__imp_StringFromGUID2
0x140019850  test    eax, eax
0x140019852  jnz     short loc_140019879
0x140019854  mov     edx, 134h; void *
0x140019859  mov     rcx, [rsp+48h]; this
0x14001985e  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140019865  mov     ebx, 8007007Ah
0x14001986a  mov     r9d, ebx; char *
0x14001986d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019872  mov     eax, ebx
0x140019874  jmp     loc_14001997F
0x140019879  lea     rsi, [rbx+178h]
0x140019880  mov     rcx, rsi; pguid
0x140019883  call    cs:__imp_CoCreateGuid
0x140019889  mov     edi, eax
0x14001988b  test    eax, eax
0x14001988d  jns     short loc_1400198AF
0x14001988f  mov     edx, 137h; void *
0x140019894  mov     rcx, [rsp+48h]; this
0x140019899  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1400198a0  mov     r9d, edi; char *
0x1400198a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400198a8  mov     eax, edi
0x1400198aa  jmp     loc_14001997F
0x1400198af  lea     rdi, [rbx+188h]
0x1400198b6  mov     r8d, 27h ; '''; cchMax
0x1400198bc  mov     rdx, rdi; lpsz
0x1400198bf  mov     rcx, rsi; rguid
0x1400198c2  call    cs:__imp_StringFromGUID2
0x1400198c8  test    eax, eax
0x1400198ca  jnz     short loc_1400198D3
0x1400198cc  mov     edx, 139h
0x1400198d1  jmp     short loc_140019859
0x1400198d3  mov     [rsp+48h+var_10], rdi
0x1400198d8  lea     rax, aRegisteringOsd; "Registering OSDeploymentInformationFact"...
0x1400198df  mov     qword ptr [rsp+48h+var_18], rbp
0x1400198e4  mov     esi, 4
0x1400198e9  mov     [rsp+48h+var_20], rax
0x1400198ee  mov     r9d, esi
0x1400198f1  xor     edx, edx
0x1400198f3  mov     qword ptr [rsp+48h+var_28], r14; int
0x1400198f8  xor     ecx, ecx
0x1400198fa  mov     r8d, 1000h
0x140019900  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140019905  or      rax, 0FFFFFFFFFFFFFFFFh
0x140019909  inc     rax
0x14001990c  cmp     [rdi+rax*2], r14w
0x140019911  jnz     short loc_140019909
0x140019913  lea     eax, ds:2[rax*2]
0x14001991a  mov     r8, rbp; int
0x14001991d  mov     [rsp+48h+var_18], eax; DWORD
0x140019921  mov     [rsp+48h+var_20], rdi; BYTE *
0x140019926  call    RegSetValue_Helper
0x14001992b  mov     edi, eax
0x14001992d  test    eax, eax
0x14001992f  jns     short loc_14001993B
0x140019931  mov     edx, 146h
0x140019936  jmp     loc_140019894
0x14001993b  mov     rcx, rbx; this
0x14001993e  call    ?RegisterClassFactory@CWuaClassFactoryBase@@QEAAJXZ; CWuaClassFactoryBase::RegisterClassFactory(void)
0x140019943  mov     edi, eax
0x140019945  test    eax, eax
0x140019947  jns     short loc_140019953
0x140019949  mov     edx, 148h
0x14001994e  jmp     loc_140019894
0x140019953  lea     rax, aSuccessfullyRe; "Successfully registered OSDeploymentInf"...
0x14001995a  mov     r9d, esi
0x14001995d  mov     [rsp+48h+var_20], rax
0x140019962  xor     edx, edx
0x140019964  xor     ecx, ecx
0x140019966  mov     qword ptr [rsp+48h+var_28], r14
0x14001996b  mov     r8d, 1000h
0x140019971  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140019976  xor     eax, eax
0x140019978  mov     byte ptr [rbx+128h], 1
0x14001997f  mov     rbx, [rsp+48h+arg_0]
0x140019984  mov     rbp, [rsp+48h+arg_8]
0x140019989  mov     rsi, [rsp+48h+arg_10]
0x14001998e  mov     rdi, [rsp+48h+arg_18]
0x140019993  add     rsp, 40h
0x140019997  pop     r14
0x140019999  retn
```
