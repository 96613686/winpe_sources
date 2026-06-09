# register_unknown

- ea: `0x18000ebac`
- end: `0x18000ece6`
- name: `register_unknown`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e8b8`

## callees

- `0x18000e474`
- `0x18000e4a8`
- `0x18000e52c`
- `0x18000e748`
- `0x18000e79c`
- `0x18000ebac`
- `0x18000edd0`
- `0x180010250`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x18000ec68`
- `KERNEL32!GetModuleFileNameA` at `0x18000ec68`

## string_xrefs

- `0x18000ebfe`: `CLSID\%s`
- `0x18000ec93`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall register_unknown(char *a1, __int64 a2)
{
  int v4; // ebx
  char v6; // r8
  RegHelper *v7; // rcx
  RegHelper *v8; // rcx
  RegHelper *v9; // rcx
  HKEY phkResult[2]; // [rsp+20h] [rbp-E0h] BYREF
  CHAR Filename[260]; // [rsp+30h] [rbp-D0h] BYREF
  char v12; // [rsp+134h] [rbp+34h]

  *(_OWORD *)phkResult = 0;
  v4 = unregister_0(a1);
  if ( v4 >= 0 )
  {
    StringCchPrintfA(Filename, 0x105u, "CLSID\\%s", a1);
    if ( RegHelper::Create(phkResult, Filename, v6)
      && RegHelper::Set(v7, phkResult[0], *(const BYTE **)(a2 + 24), 0)
      && RegHelper::CreateSub((RegHelper *)phkResult, "InProcServer32")
      && (v12 = 0, GetModuleFileNameA(Global::g_hInstance, Filename, 0x105u))
      && !v12
      && RegHelper::Set(v8, phkResult[1], (const BYTE *)Filename, 0)
      && RegHelper::Set(v9, phkResult[1], (const BYTE *)"Apartment", "ThreadingModel") )
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
0x18000ebac  mov     [rsp-8+arg_10], rbx
0x18000ebb1  push    rbp
0x18000ebb2  push    rsi
0x18000ebb3  push    rdi
0x18000ebb4  lea     rbp, [rsp-50h]
0x18000ebb9  sub     rsp, 150h
0x18000ebc0  mov     rax, cs:__security_cookie
0x18000ebc7  xor     rax, rsp
0x18000ebca  mov     [rbp+60h+var_20], rax
0x18000ebce  xorps   xmm0, xmm0
0x18000ebd1  mov     rsi, rdx
0x18000ebd4  movdqu  xmmword ptr [rsp+160h+phkResult], xmm0
0x18000ebda  mov     rdi, rcx
0x18000ebdd  call    unregister_0
0x18000ebe2  mov     ebx, eax
0x18000ebe4  test    eax, eax
0x18000ebe6  jns     short loc_18000EBF9
0x18000ebe8  lea     rcx, [rsp+160h+phkResult]; this
0x18000ebed  call    ??1RegHelper@@QEAA@XZ; RegHelper::~RegHelper(void)
0x18000ebf2  mov     eax, ebx
0x18000ebf4  jmp     loc_18000ECC7
0x18000ebf9  mov     ebx, 105h
0x18000ebfe  lea     r8, aClsidS; "CLSID\\%s"
0x18000ec05  mov     edx, ebx; unsigned __int64
0x18000ec07  lea     rcx, [rsp+160h+Filename]; char *
0x18000ec0c  mov     r9, rdi
0x18000ec0f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000ec14  lea     rdx, [rsp+160h+Filename]; lpSubKey
0x18000ec19  lea     rcx, [rsp+160h+phkResult]; phkResult
0x18000ec1e  call    ?Create@RegHelper@@QEAA_NPEBD_N@Z; RegHelper::Create(char const *,bool)
0x18000ec23  test    al, al
0x18000ec25  jz      loc_18000ECB8
0x18000ec2b  mov     r8, [rsi+18h]; char *
0x18000ec2f  xor     r9d, r9d; char *
0x18000ec32  mov     rdx, [rsp+160h+phkResult]; HKEY
0x18000ec37  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000ec3c  test    al, al
0x18000ec3e  jz      short loc_18000ECB8
0x18000ec40  lea     rdx, aInprocserver32; "InProcServer32"
0x18000ec47  lea     rcx, [rsp+160h+phkResult]; this
0x18000ec4c  call    ?CreateSub@RegHelper@@QEAA_NPEBD@Z; RegHelper::CreateSub(char const *)
0x18000ec51  test    al, al
0x18000ec53  jz      short loc_18000ECB8
0x18000ec55  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hModule
0x18000ec5c  lea     rdx, [rsp+160h+Filename]; lpFilename
0x18000ec61  mov     r8d, ebx; nSize
0x18000ec64  mov     [rbp+60h+var_2C], 0
0x18000ec68  call    cs:__imp_GetModuleFileNameA
0x18000ec6e  test    eax, eax
0x18000ec70  jz      short loc_18000ECB8
0x18000ec72  cmp     [rbp+60h+var_2C], 0
0x18000ec76  jnz     short loc_18000ECB8
0x18000ec78  mov     rdx, [rsp+160h+phkResult+8]; HKEY
0x18000ec7d  lea     r8, [rsp+160h+Filename]; char *
0x18000ec82  xor     r9d, r9d; char *
0x18000ec85  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000ec8a  test    al, al
0x18000ec8c  jz      short loc_18000ECB8
0x18000ec8e  mov     rdx, [rsp+160h+phkResult+8]; HKEY
0x18000ec93  lea     r9, aThreadingmodel; "ThreadingModel"
0x18000ec9a  lea     r8, aApartment; "Apartment"
0x18000eca1  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000eca6  test    al, al
0x18000eca8  jz      short loc_18000ECB8
0x18000ecaa  lea     rcx, [rsp+160h+phkResult]; this
0x18000ecaf  call    ??1RegHelper@@QEAA@XZ; RegHelper::~RegHelper(void)
0x18000ecb4  xor     eax, eax
0x18000ecb6  jmp     short loc_18000ECC7
0x18000ecb8  lea     rcx, [rsp+160h+phkResult]; this
0x18000ecbd  call    ??1RegHelper@@QEAA@XZ; RegHelper::~RegHelper(void)
0x18000ecc2  mov     eax, 8000FFFFh
0x18000ecc7  mov     rcx, [rbp+60h+var_20]
0x18000eccb  xor     rcx, rsp; StackCookie
0x18000ecce  call    __security_check_cookie
0x18000ecd3  mov     rbx, [rsp+160h+arg_10]
0x18000ecdb  add     rsp, 150h
0x18000ece2  pop     rdi
0x18000ece3  pop     rsi
0x18000ece4  pop     rbp
0x18000ece5  retn
```
