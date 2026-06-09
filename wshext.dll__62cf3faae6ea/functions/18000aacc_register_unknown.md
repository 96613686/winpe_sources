# register_unknown

- ea: `0x18000aacc`
- end: `0x18000abff`
- name: `register_unknown`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a270`

## callees

- `0x180005900`
- `0x18000a70c`
- `0x18000a740`
- `0x18000a7c4`
- `0x18000a9dc`
- `0x18000aacc`
- `0x18000ac08`
- `0x18000d1c0`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x18000ab81`
- `KERNEL32!GetModuleFileNameA` at `0x18000ab81`

## string_xrefs

- `0x18000abac`: `ThreadingModel`
- `0x18000ab1e`: `CLSID\%s`

## pseudocode

```c
__int64 __fastcall register_unknown(char *a1, __int64 a2)
{
  int v4; // ebx
  char v6; // r8
  RegHelper *v7; // rcx
  const char *v8; // rdx
  RegHelper *v9; // rcx
  RegHelper *v10; // rcx
  HKEY phkResult[2]; // [rsp+20h] [rbp-E0h] BYREF
  CHAR Filename[260]; // [rsp+30h] [rbp-D0h] BYREF
  char v13; // [rsp+134h] [rbp+34h]

  *(_OWORD *)phkResult = 0;
  v4 = unregister(a1);
  if ( v4 >= 0 )
  {
    StringCchPrintfA(Filename, 0x105u, "CLSID\\%s", a1);
    if ( RegHelper::Create(phkResult, Filename, v6)
      && RegHelper::Set(v7, phkResult[0], *(const BYTE **)(a2 + 24), 0)
      && RegHelper::CreateSub((RegHelper *)phkResult, v8)
      && (v13 = 0, GetModuleFileNameA(Global::g_hInstance, Filename, 0x105u))
      && !v13
      && RegHelper::Set(v9, phkResult[1], (const BYTE *)Filename, 0)
      && RegHelper::Set(v10, phkResult[1], "Apartment", "ThreadingModel") )
    {
      RegHelper::~RegHelper((RegHelper *)phkResult);
      return 0;
    }
    else
    {
      RegHelper::~RegHelper((RegHelper *)phkResult);
      return 2147549183LL;
    }
  }
  else
  {
    RegHelper::~RegHelper((RegHelper *)phkResult);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x18000aacc  mov     [rsp-8+arg_10], rbx
0x18000aad1  push    rbp
0x18000aad2  push    rsi
0x18000aad3  push    rdi
0x18000aad4  lea     rbp, [rsp-50h]
0x18000aad9  sub     rsp, 150h
0x18000aae0  mov     rax, cs:__security_cookie
0x18000aae7  xor     rax, rsp
0x18000aaea  mov     [rbp+60h+var_20], rax
0x18000aaee  xorps   xmm0, xmm0
0x18000aaf1  mov     rsi, rdx
0x18000aaf4  movdqu  xmmword ptr [rsp+160h+phkResult], xmm0
0x18000aafa  mov     rdi, rcx
0x18000aafd  call    unregister
0x18000ab02  mov     ebx, eax
0x18000ab04  test    eax, eax
0x18000ab06  jns     short loc_18000AB19
0x18000ab08  lea     rcx, [rsp+160h+phkResult]; this
0x18000ab0d  call    ??1RegHelper@@QEAA@XZ; RegHelper::~RegHelper(void)
0x18000ab12  mov     eax, ebx
0x18000ab14  jmp     loc_18000ABE0
0x18000ab19  mov     ebx, 105h
0x18000ab1e  lea     r8, aClsidS; "CLSID\\%s"
0x18000ab25  mov     edx, ebx; unsigned __int64
0x18000ab27  lea     rcx, [rsp+160h+Filename]; char *
0x18000ab2c  mov     r9, rdi
0x18000ab2f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000ab34  lea     rdx, [rsp+160h+Filename]; lpSubKey
0x18000ab39  lea     rcx, [rsp+160h+phkResult]; phkResult
0x18000ab3e  call    ?Create@RegHelper@@QEAA_NPEBD_N@Z; RegHelper::Create(char const *,bool)
0x18000ab43  test    al, al
0x18000ab45  jz      loc_18000ABD1
0x18000ab4b  mov     r8, [rsi+18h]; char *
0x18000ab4f  xor     r9d, r9d; char *
0x18000ab52  mov     rdx, [rsp+160h+phkResult]; HKEY
0x18000ab57  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000ab5c  test    al, al
0x18000ab5e  jz      short loc_18000ABD1
0x18000ab60  lea     rcx, [rsp+160h+phkResult]; this
0x18000ab65  call    ?CreateSub@RegHelper@@QEAA_NPEBD@Z; RegHelper::CreateSub(char const *)
0x18000ab6a  test    al, al
0x18000ab6c  jz      short loc_18000ABD1
0x18000ab6e  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hModule
0x18000ab75  lea     rdx, [rsp+160h+Filename]; lpFilename
0x18000ab7a  mov     r8d, ebx; nSize
0x18000ab7d  mov     [rbp+60h+var_2C], 0
0x18000ab81  call    cs:__imp_GetModuleFileNameA
0x18000ab87  test    eax, eax
0x18000ab89  jz      short loc_18000ABD1
0x18000ab8b  cmp     [rbp+60h+var_2C], 0
0x18000ab8f  jnz     short loc_18000ABD1
0x18000ab91  mov     rdx, [rsp+160h+phkResult+8]; HKEY
0x18000ab96  lea     r8, [rsp+160h+Filename]; char *
0x18000ab9b  xor     r9d, r9d; char *
0x18000ab9e  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000aba3  test    al, al
0x18000aba5  jz      short loc_18000ABD1
0x18000aba7  mov     rdx, [rsp+160h+phkResult+8]; HKEY
0x18000abac  lea     r9, aThreadingmodel; "ThreadingModel"
0x18000abb3  lea     r8, Data; "Apartment"
0x18000abba  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000abbf  test    al, al
0x18000abc1  jz      short loc_18000ABD1
0x18000abc3  lea     rcx, [rsp+160h+phkResult]; this
0x18000abc8  call    ??1RegHelper@@QEAA@XZ; RegHelper::~RegHelper(void)
0x18000abcd  xor     eax, eax
0x18000abcf  jmp     short loc_18000ABE0
0x18000abd1  lea     rcx, [rsp+160h+phkResult]; this
0x18000abd6  call    ??1RegHelper@@QEAA@XZ; RegHelper::~RegHelper(void)
0x18000abdb  mov     eax, 8000FFFFh
0x18000abe0  mov     rcx, [rbp+60h+var_20]
0x18000abe4  xor     rcx, rsp; StackCookie
0x18000abe7  call    __security_check_cookie
0x18000abec  mov     rbx, [rsp+160h+arg_10]
0x18000abf4  add     rsp, 150h
0x18000abfb  pop     rdi
0x18000abfc  pop     rsi
0x18000abfd  pop     rbp
0x18000abfe  retn
```
