# CTSVIPPublicBinding::Open(ushort const *)

- ea: `0x1800211d0`
- end: `0x1800213b6`
- name: `?Open@CTSVIPPublicBinding@@UEAAJPEBG@Z`
- size: `486`
- prototype: `__int64 __fastcall(CTSVIPPublicBinding *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fd70`

## callees

- `0x180005b40`
- `0x18000dcec`
- `0x1800211d0`
- `0x180030c64`
- `0x180031130`
- `0x180032c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021277`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180021267`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180021267`

## string_xrefs

- `0x18002133c`: `\pipe\TSVIP_service`
- `0x180021343`: `Security=Impersonation Dynamic False`
- `0x180021296`: `GetComputerName failed: 0x%x in %s`
- `0x180021378`: `CTSVIPPublicBinding::Open`
- `0x1800212c1`: `QueryTSVIPConfig failed: 0x%x in %s`
- `0x1800212de`: `FALSE == Config.EnableVip failed: 0x%x in %s`

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
0x1800211d0  mov     [rsp-8+arg_10], rbx
0x1800211d5  mov     [rsp-8+arg_18], rsi
0x1800211da  push    rbp
0x1800211db  push    rdi
0x1800211dc  push    r14
0x1800211de  lea     rbp, [rsp-910h]
0x1800211e6  sub     rsp, 0A10h
0x1800211ed  mov     rax, cs:__security_cookie
0x1800211f4  xor     rax, rsp
0x1800211f7  mov     [rbp+920h+var_18], rax
0x1800211fe  mov     rsi, rcx
0x180021201  mov     [rsp+0A20h+nSize], 10h
0x180021209  xorps   xmm0, xmm0
0x18002120c  lea     rcx, [rsp+0A20h+var_9C0]; this
0x180021211  movups  xmmword ptr [rsp+0A20h+var_9D8.Version], xmm0
0x180021216  mov     rdi, rdx
0x180021219  call    ??0__TSVirtualIPConfig@@QEAA@XZ; __TSVirtualIPConfig::__TSVirtualIPConfig(void)
0x18002121e  add     rsi, 8
0x180021222  xor     r14d, r14d
0x180021225  cmp     [rsi], r14
0x180021228  jz      short loc_180021232
0x18002122a  mov     ebx, r14d
0x18002122d  jmp     loc_18002138C
0x180021232  test    rdi, rdi
0x180021235  jz      short loc_180021244
0x180021237  mov     ecx, r14d
0x18002123a  cmp     r14w, [rdi]
0x18002123e  jnz     loc_1800212EA
0x180021244  xor     eax, eax
0x180021246  lea     rdx, [rsp+0A20h+nSize]; nSize
0x18002124b  lea     rcx, [rbp+920h+Buffer]; lpBuffer
0x180021252  mov     [rbp+920h+var_20], ax
0x180021259  movups  xmmword ptr [rbp+920h+Buffer], xmm0
0x180021260  movups  [rbp+920h+var_30], xmm0
0x180021267  call    cs:__imp_GetComputerNameW
0x18002126e  nop     dword ptr [rax+rax+00h]
0x180021273  test    eax, eax
0x180021275  jnz     short loc_1800212A2
0x180021277  call    cs:__imp_GetLastError
0x18002127e  nop     dword ptr [rax+rax+00h]
0x180021283  mov     ebx, eax
0x180021285  test    eax, eax
0x180021287  jle     short loc_180021292
0x180021289  movzx   ebx, ax
0x18002128c  or      ebx, 80070000h
0x180021292  test    ebx, ebx
0x180021294  jns     short loc_1800212A2
0x180021296  lea     rdx, aGetcomputernam; "GetComputerName failed: 0x%x in %s"
0x18002129d  jmp     loc_180021378
0x1800212a2  lea     rcx, [rsp+0A20h+var_9C0]
0x1800212a7  call    LoadTSVIPConfig
0x1800212ac  mov     ebx, eax
0x1800212ae  test    eax, eax
0x1800212b0  jz      short loc_1800212CD
0x1800212b2  jle     short loc_1800212BD
0x1800212b4  movzx   ebx, ax
0x1800212b7  or      ebx, 80070000h
0x1800212bd  test    ebx, ebx
0x1800212bf  jns     short loc_1800212CD
0x1800212c1  lea     rdx, aQuerytsvipconf; "QueryTSVIPConfig failed: 0x%x in %s"
0x1800212c8  jmp     loc_180021378
0x1800212cd  mov     ecx, 1
0x1800212d2  cmp     [rsp+0A20h+var_9BC], r14d
0x1800212d7  jnz     short loc_1800212EA
0x1800212d9  mov     ebx, 800706BAh
0x1800212de  lea     rdx, aFalseConfigEna; "FALSE == Config.EnableVip failed: 0x%x "...
0x1800212e5  jmp     loc_180021378
0x1800212ea  mov     [rsp+0A20h+var_9D8.Capabilities], 1
0x1800212f2  mov     [rsp+0A20h+var_9D8.IdentityTracking], 1
0x1800212fa  mov     [rsp+0A20h+var_9D8.ImpersonationType], 3
0x180021302  mov     [rsp+0A20h+var_9D8.Version], 1
0x18002130a  test    ecx, ecx
0x18002130c  jz      short loc_180021326
0x18002130e  lea     rdi, [rbp+920h+Buffer]
0x180021315  lea     rcx, [rbp+920h+var_170]
0x18002131c  cmp     [rbp+920h+var_170], r14w
0x180021324  jnz     short loc_18002132D
0x180021326  lea     rcx, a53b46b02C73b4a; "53b46b02-c73b-4a3e-8dee-b16b80672fc0"
0x18002132d  lea     rax, [rsp+0A20h+var_9D8]
0x180021332  mov     [rsp+0A20h+var_9F0], rsi; void **
0x180021337  mov     [rsp+0A20h+var_9F8], rax; struct _RPC_SECURITY_QOS *
0x18002133c  lea     r9, aPipeTsvipServi; "\\pipe\\TSVIP_service"
0x180021343  lea     rax, aSecurityImpers_0; "Security=Impersonation Dynamic False"
0x18002134a  mov     r8, rdi; unsigned __int16 *
0x18002134d  lea     rdx, aNcacnNp_0; "ncacn_np"
0x180021354  mov     [rsp+0A20h+var_A00], rax; unsigned __int16 *
0x180021359  call    ?BindSecureEx@CRpcUtils@@SAJPEBG0000PEAU_RPC_SECURITY_QOS@@PEAPEAX@Z; CRpcUtils::BindSecureEx(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_RPC_SECURITY_QOS *,void * *)
0x18002135e  mov     ebx, eax
0x180021360  test    eax, eax
0x180021362  jle     short loc_18002136D
0x180021364  movzx   ebx, ax
0x180021367  or      ebx, 80070000h
0x18002136d  test    ebx, ebx
0x18002136f  jns     short loc_18002138C
0x180021371  lea     rdx, aTsvipbindsecur; "TSVIPBindSecure failed: 0x%x in %s"
0x180021378  lea     r9, aCtsvippublicbi; "CTSVIPPublicBinding::Open"
0x18002137f  mov     r8d, ebx
0x180021382  mov     ecx, 8; int
0x180021387  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002138c  mov     eax, ebx
0x18002138e  mov     rcx, [rbp+920h+var_18]
0x180021395  xor     rcx, rsp; StackCookie
0x180021398  call    __security_check_cookie
0x18002139d  lea     r11, [rsp+0A20h+var_10]
0x1800213a5  mov     rbx, [r11+30h]
0x1800213a9  mov     rsi, [r11+38h]
0x1800213ad  mov     rsp, r11
0x1800213b0  pop     r14
0x1800213b2  pop     rdi
0x1800213b3  pop     rbp
0x1800213b4  retn
```
