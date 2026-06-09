# CTSVIPPublicBinding::Open(ushort const *)

- ea: `0x18001fad0`
- end: `0x18001fca9`
- name: `?Open@CTSVIPPublicBinding@@UEAAJPEBG@Z`
- size: `473`
- prototype: `__int64 __fastcall(CTSVIPPublicBinding *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002d8d0`

## callees

- `0x180007890`
- `0x18000c15c`
- `0x18001fad0`
- `0x18002e254`
- `0x18002e6a4`
- `0x18002fe40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb71`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001fb67`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001fb67`

## string_xrefs

- `0x18001fc30`: `\pipe\TSVIP_service`
- `0x18001fc37`: `Security=Impersonation Dynamic False`
- `0x18001fb8a`: `GetComputerName failed: 0x%x in %s`
- `0x18001fc6c`: `CTSVIPPublicBinding::Open`
- `0x18001fbb5`: `QueryTSVIPConfig failed: 0x%x in %s`
- `0x18001fbd2`: `FALSE == Config.EnableVip failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSVIPPublicBinding::Open(CTSVIPPublicBinding *this, WCHAR *a2)
{
  void **v4; // rsi
  unsigned int v5; // ebx
  int v6; // ecx
  signed int LastError; // eax
  int TSVIPConfig; // eax
  const unsigned __int16 *v9; // rcx
  int v10; // eax
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  struct _RPC_SECURITY_QOS v13; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v14[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+64h] [rbp-9Ch]
  __int16 v16; // [rsp+8B0h] [rbp+7B0h] BYREF
  WCHAR Buffer[8]; // [rsp+9E0h] [rbp+8E0h] BYREF
  __int128 v18; // [rsp+9F0h] [rbp+8F0h]
  __int16 v19; // [rsp+A00h] [rbp+900h]

  nSize = 16;
  v13 = 0;
  __TSVirtualIPConfig::__TSVirtualIPConfig((__TSVirtualIPConfig *)v14);
  v4 = (void **)((char *)this + 8);
  if ( *v4 )
  {
    return 0;
  }
  else
  {
    if ( !a2 || (v6 = 0, !*a2) )
    {
      v19 = 0;
      *(_OWORD *)Buffer = 0;
      v18 = 0;
      if ( !GetComputerNameW(Buffer, &nSize) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( (v5 & 0x80000000) != 0 )
        {
          _DbgPrintMessage(8, "GetComputerName failed: 0x%x in %s", v5, "CTSVIPPublicBinding::Open");
          return v5;
        }
      }
      TSVIPConfig = LoadTSVIPConfig(v14);
      v5 = TSVIPConfig;
      if ( TSVIPConfig )
      {
        if ( TSVIPConfig > 0 )
          v5 = (unsigned __int16)TSVIPConfig | 0x80070000;
        if ( (v5 & 0x80000000) != 0 )
        {
          _DbgPrintMessage(8, "QueryTSVIPConfig failed: 0x%x in %s", v5, "CTSVIPPublicBinding::Open");
          return v5;
        }
      }
      v6 = 1;
      if ( !v15 )
      {
        v5 = -2147023174;
        _DbgPrintMessage(8, "FALSE == Config.EnableVip failed: 0x%x in %s", 2147944122LL, "CTSVIPPublicBinding::Open");
        return v5;
      }
    }
    v13.Capabilities = 1;
    v13.IdentityTracking = 1;
    v13.ImpersonationType = 3;
    v13.Version = 1;
    if ( !v6 || (a2 = Buffer, v9 = (const unsigned __int16 *)&v16, !v16) )
      v9 = L"53b46b02-c73b-4a3e-8dee-b16b80672fc0";
    v10 = CRpcUtils::BindSecureEx(
            v9,
            L"ncacn_np",
            a2,
            L"\\pipe\\TSVIP_service",
            L"Security=Impersonation Dynamic False",
            &v13,
            v4);
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
      _DbgPrintMessage(8, "TSVIPBindSecure failed: 0x%x in %s", v5, "CTSVIPPublicBinding::Open");
  }
  return v5;
}

```

## disassembly

```asm
0x18001fad0  mov     [rsp-8+arg_10], rbx
0x18001fad5  mov     [rsp-8+arg_18], rsi
0x18001fada  push    rbp
0x18001fadb  push    rdi
0x18001fadc  push    r14
0x18001fade  lea     rbp, [rsp-910h]
0x18001fae6  sub     rsp, 0A10h
0x18001faed  mov     rax, cs:__security_cookie
0x18001faf4  xor     rax, rsp
0x18001faf7  mov     [rbp+920h+var_18], rax
0x18001fafe  mov     rsi, rcx
0x18001fb01  mov     [rsp+0A20h+nSize], 10h
0x18001fb09  xorps   xmm0, xmm0
0x18001fb0c  lea     rcx, [rsp+0A20h+var_9C0]; this
0x18001fb11  movups  xmmword ptr [rsp+0A20h+var_9D8.Version], xmm0
0x18001fb16  mov     rdi, rdx
0x18001fb19  call    ??0__TSVirtualIPConfig@@QEAA@XZ; __TSVirtualIPConfig::__TSVirtualIPConfig(void)
0x18001fb1e  add     rsi, 8
0x18001fb22  xor     r14d, r14d
0x18001fb25  cmp     [rsi], r14
0x18001fb28  jz      short loc_18001FB32
0x18001fb2a  mov     ebx, r14d
0x18001fb2d  jmp     loc_18001FC80
0x18001fb32  test    rdi, rdi
0x18001fb35  jz      short loc_18001FB44
0x18001fb37  mov     ecx, r14d
0x18001fb3a  cmp     r14w, [rdi]
0x18001fb3e  jnz     loc_18001FBDE
0x18001fb44  xor     eax, eax
0x18001fb46  lea     rdx, [rsp+0A20h+nSize]; nSize
0x18001fb4b  lea     rcx, [rbp+920h+Buffer]; lpBuffer
0x18001fb52  mov     [rbp+920h+var_20], ax
0x18001fb59  movups  xmmword ptr [rbp+920h+Buffer], xmm0
0x18001fb60  movups  [rbp+920h+var_30], xmm0
0x18001fb67  call    cs:__imp_GetComputerNameW
0x18001fb6d  test    eax, eax
0x18001fb6f  jnz     short loc_18001FB96
0x18001fb71  call    cs:__imp_GetLastError
0x18001fb77  mov     ebx, eax
0x18001fb79  test    eax, eax
0x18001fb7b  jle     short loc_18001FB86
0x18001fb7d  movzx   ebx, ax
0x18001fb80  or      ebx, 80070000h
0x18001fb86  test    ebx, ebx
0x18001fb88  jns     short loc_18001FB96
0x18001fb8a  lea     rdx, aGetcomputernam; "GetComputerName failed: 0x%x in %s"
0x18001fb91  jmp     loc_18001FC6C
0x18001fb96  lea     rcx, [rsp+0A20h+var_9C0]
0x18001fb9b  call    LoadTSVIPConfig
0x18001fba0  mov     ebx, eax
0x18001fba2  test    eax, eax
0x18001fba4  jz      short loc_18001FBC1
0x18001fba6  jle     short loc_18001FBB1
0x18001fba8  movzx   ebx, ax
0x18001fbab  or      ebx, 80070000h
0x18001fbb1  test    ebx, ebx
0x18001fbb3  jns     short loc_18001FBC1
0x18001fbb5  lea     rdx, aQuerytsvipconf; "QueryTSVIPConfig failed: 0x%x in %s"
0x18001fbbc  jmp     loc_18001FC6C
0x18001fbc1  mov     ecx, 1
0x18001fbc6  cmp     [rsp+0A20h+var_9BC], r14d
0x18001fbcb  jnz     short loc_18001FBDE
0x18001fbcd  mov     ebx, 800706BAh
0x18001fbd2  lea     rdx, aFalseConfigEna; "FALSE == Config.EnableVip failed: 0x%x "...
0x18001fbd9  jmp     loc_18001FC6C
0x18001fbde  mov     [rsp+0A20h+var_9D8.Capabilities], 1
0x18001fbe6  mov     [rsp+0A20h+var_9D8.IdentityTracking], 1
0x18001fbee  mov     [rsp+0A20h+var_9D8.ImpersonationType], 3
0x18001fbf6  mov     [rsp+0A20h+var_9D8.Version], 1
0x18001fbfe  test    ecx, ecx
0x18001fc00  jz      short loc_18001FC1A
0x18001fc02  lea     rdi, [rbp+920h+Buffer]
0x18001fc09  lea     rcx, [rbp+920h+var_170]
0x18001fc10  cmp     [rbp+920h+var_170], r14w
0x18001fc18  jnz     short loc_18001FC21
0x18001fc1a  lea     rcx, a53b46b02C73b4a; "53b46b02-c73b-4a3e-8dee-b16b80672fc0"
0x18001fc21  lea     rax, [rsp+0A20h+var_9D8]
0x18001fc26  mov     [rsp+0A20h+var_9F0], rsi; void **
0x18001fc2b  mov     [rsp+0A20h+var_9F8], rax; struct _RPC_SECURITY_QOS *
0x18001fc30  lea     r9, aPipeTsvipServi; "\\pipe\\TSVIP_service"
0x18001fc37  lea     rax, aSecurityImpers_0; "Security=Impersonation Dynamic False"
0x18001fc3e  mov     r8, rdi; unsigned __int16 *
0x18001fc41  lea     rdx, aNcacnNp_0; "ncacn_np"
0x18001fc48  mov     [rsp+0A20h+var_A00], rax; unsigned __int16 *
0x18001fc4d  call    ?BindSecureEx@CRpcUtils@@SAJPEBG0000PEAU_RPC_SECURITY_QOS@@PEAPEAX@Z; CRpcUtils::BindSecureEx(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_RPC_SECURITY_QOS *,void * *)
0x18001fc52  mov     ebx, eax
0x18001fc54  test    eax, eax
0x18001fc56  jle     short loc_18001FC61
0x18001fc58  movzx   ebx, ax
0x18001fc5b  or      ebx, 80070000h
0x18001fc61  test    ebx, ebx
0x18001fc63  jns     short loc_18001FC80
0x18001fc65  lea     rdx, aTsvipbindsecur; "TSVIPBindSecure failed: 0x%x in %s"
0x18001fc6c  lea     r9, aCtsvippublicbi; "CTSVIPPublicBinding::Open"
0x18001fc73  mov     r8d, ebx
0x18001fc76  mov     ecx, 8; int
0x18001fc7b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001fc80  mov     eax, ebx
0x18001fc82  mov     rcx, [rbp+920h+var_18]
0x18001fc89  xor     rcx, rsp; StackCookie
0x18001fc8c  call    __security_check_cookie
0x18001fc91  lea     r11, [rsp+0A20h+var_10]
0x18001fc99  mov     rbx, [r11+30h]
0x18001fc9d  mov     rsi, [r11+38h]
0x18001fca1  mov     rsp, r11
0x18001fca4  pop     r14
0x18001fca6  pop     rdi
0x18001fca7  pop     rbp
0x18001fca8  retn
```
