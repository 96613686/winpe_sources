# CClientLibrary::DumpRpcErrors(void)

- ea: `0x180005064`
- end: `0x18000532f`
- name: `?DumpRpcErrors@CClientLibrary@@AEAAXXZ`
- size: `715`
- prototype: `void __fastcall(CClientLibrary *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005558`
- `0x18000726c`

## callees

- `0x180005064`
- `0x18000bd5c`
- `0x18000d6d2`
- `0x18000d700`
- `0x18000e010`

## import_xrefs

- `RPCRT4!RpcErrorGetNextRecord` at `0x1800052e5`
- `RPCRT4!RpcErrorGetNextRecord` at `0x1800052e5`
- `RPCRT4!RpcErrorStartEnumeration` at `0x18000509a`
- `RPCRT4!RpcErrorStartEnumeration` at `0x18000509a`

## string_xrefs

- `0x18000512f`: `Computer Name=%s\n`
- `0x180005173`: `GeneratingComponent=%u\n`

## pseudocode

```c
void __fastcall CClientLibrary::DumpRpcErrors(CClientLibrary *this)
{
  unsigned int started; // eax
  __int64 v2; // rdx
  unsigned int v3; // eax
  __int64 v4; // rdx
  void (*v5)(const unsigned __int16 *, ...); // r9
  unsigned int v6; // ebx
  union tagRPC_EE_INFO_PARAM::$A3FD93C0502A9420CA2CBD32041223FD *p_u; // rdi
  const wchar_t *v8; // rcx
  const wchar_t *v9; // rcx
  __int64 LVal; // r8
  const wchar_t *v11; // rcx
  unsigned int NextRecord; // eax
  __int64 v13; // rdx
  RPC_ERROR_ENUM_HANDLE EnumHandle; // [rsp+20h] [rbp-79h] BYREF
  RPC_EXTENDED_ERROR_INFO ErrorInfo; // [rsp+40h] [rbp-59h] BYREF

  memset(&EnumHandle, 0, sizeof(EnumHandle));
  started = RpcErrorStartEnumeration(&EnumHandle);
  v3 = ElValidateWin32(started, v2, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1803);
  if ( !(unsigned int)ElValidateWin32(v3, v4, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1804) )
  {
    memset_0(&ErrorInfo, 0, sizeof(ErrorInfo));
    ErrorInfo.Version = 1;
    ErrorInfo.NumberOfParameters = 4;
    if ( g_ErrLibTraceFunction )
      g_ErrLibTraceFunction(L"RPC Extended Error Info\n-----------------------\n");
    while ( 1 )
    {
LABEL_41:
      NextRecord = RpcErrorGetNextRecord(&EnumHandle, 0, &ErrorInfo);
      if ( (unsigned int)ElValidateWin32(NextRecord, v13, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1814) )
        return;
      if ( !ErrorInfo.ComputerName )
        goto LABEL_7;
      v5 = g_ErrLibTraceFunction;
      if ( g_ErrLibTraceFunction )
        break;
LABEL_14:
      v6 = 0;
      if ( ErrorInfo.NumberOfParameters > 0 )
      {
        p_u = &ErrorInfo.Parameters[0].u;
        while ( 1 )
        {
          switch ( *(_DWORD *)&p_u[-1].BVal.Size )
          {
            case 1:
              if ( v5 )
              {
                v9 = L"Param[%d][Ansi]: %S\n";
LABEL_38:
                v5(v9, v6, p_u->PVal);
LABEL_39:
                v5 = g_ErrLibTraceFunction;
              }
              break;
            case 2:
              if ( v5 )
              {
                v9 = L"Param[%d][Unicode]: %s\n";
                goto LABEL_38;
              }
              break;
            case 3:
              if ( v5 )
              {
                LVal = (unsigned int)p_u->LVal;
                v11 = L"Param[%d][Long]: %d\n";
                goto LABEL_31;
              }
              break;
            case 4:
              if ( v5 )
              {
                LVal = (unsigned int)p_u->SVal;
                v11 = L"Param[%d][Short]: %d\n";
LABEL_31:
                v5(v11, v6, LVal);
                goto LABEL_39;
              }
              break;
            case 5:
              if ( v5 )
              {
                v9 = L"Param[%d][Pointer]: %I64u\n";
                goto LABEL_38;
              }
              break;
            case 6:
              if ( v5 )
              {
                v8 = L"Param[%d][Truncated]\n";
                goto LABEL_24;
              }
              break;
            default:
              if ( v5 )
              {
                v8 = L"Invalid type: %d\n";
LABEL_24:
                v5(v8);
                goto LABEL_39;
              }
              break;
          }
          ++v6;
          p_u = (union tagRPC_EE_INFO_PARAM::$A3FD93C0502A9420CA2CBD32041223FD *)((char *)p_u + 24);
          if ( (int)v6 >= ErrorInfo.NumberOfParameters )
            goto LABEL_41;
        }
      }
    }
    g_ErrLibTraceFunction(L"Computer Name=%s\n");
LABEL_7:
    v5 = g_ErrLibTraceFunction;
    if ( g_ErrLibTraceFunction )
    {
      g_ErrLibTraceFunction(L"Proces ID=%u\n", ErrorInfo.ProcessID);
      v5 = g_ErrLibTraceFunction;
      if ( g_ErrLibTraceFunction )
      {
        g_ErrLibTraceFunction(L"GeneratingComponent=%u\n", ErrorInfo.GeneratingComponent);
        v5 = g_ErrLibTraceFunction;
        if ( g_ErrLibTraceFunction )
        {
          g_ErrLibTraceFunction(L"Status=%u\n", ErrorInfo.Status);
          v5 = g_ErrLibTraceFunction;
          if ( g_ErrLibTraceFunction )
          {
            g_ErrLibTraceFunction(L"Flags=0x%x\n", ErrorInfo.Flags);
            v5 = g_ErrLibTraceFunction;
            if ( g_ErrLibTraceFunction )
            {
              g_ErrLibTraceFunction(L"Detection Location=%u\n", ErrorInfo.DetectionLocation);
              v5 = g_ErrLibTraceFunction;
              if ( g_ErrLibTraceFunction )
              {
                g_ErrLibTraceFunction(L"Parameters Count=%u\n", (unsigned int)ErrorInfo.NumberOfParameters);
                v5 = g_ErrLibTraceFunction;
              }
            }
          }
        }
      }
    }
    goto LABEL_14;
  }
}

```

## disassembly

```asm
0x180005064  mov     [rsp-8+arg_0], rbx
0x180005069  mov     [rsp-8+arg_8], rdi
0x18000506e  push    rbp
0x18000506f  lea     rbp, [rsp-57h]
0x180005074  sub     rsp, 0F0h
0x18000507b  mov     rax, cs:__security_cookie
0x180005082  xor     rax, rsp
0x180005085  mov     [rbp+57h+var_10], rax
0x180005089  xorps   xmm0, xmm0
0x18000508c  lea     rcx, [rbp+57h+EnumHandle]; EnumHandle
0x180005090  xor     eax, eax
0x180005092  movups  xmmword ptr [rbp+57h+EnumHandle.Signature], xmm0
0x180005096  mov     [rbp+57h+EnumHandle.Head], rax
0x18000509a  call    cs:__imp_RpcErrorStartEnumeration
0x1800050a1  nop     dword ptr [rax+rax+00h]
0x1800050a6  mov     r9d, 70Bh
0x1800050ac  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x1800050b3  mov     ecx, eax
0x1800050b5  call    ElValidateWin32
0x1800050ba  mov     r9d, 70Ch
0x1800050c0  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x1800050c7  mov     ecx, eax
0x1800050c9  call    ElValidateWin32
0x1800050ce  test    eax, eax
0x1800050d0  jnz     loc_18000530D
0x1800050d6  xor     edx, edx; Val
0x1800050d8  lea     rcx, [rbp+57h+ErrorInfo]; void *
0x1800050dc  mov     r8d, 98h; Size
0x1800050e2  call    memset_0
0x1800050e7  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800050ee  mov     [rbp+57h+ErrorInfo.Version], 1
0x1800050f5  mov     [rbp+57h+ErrorInfo.NumberOfParameters], 4
0x1800050fc  test    rax, rax
0x1800050ff  jz      loc_1800052DB
0x180005105  lea     rcx, aRpcExtendedErr; "RPC Extended Error Info\n--------------"...
0x18000510c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005111  jmp     loc_1800052DB
0x180005116  mov     rdx, [rbp+57h+ErrorInfo.ComputerName]
0x18000511a  test    rdx, rdx
0x18000511d  jz      short loc_18000513E
0x18000511f  mov     r9, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180005126  test    r9, r9
0x180005129  jz      loc_180005203
0x18000512f  lea     rcx, aComputerNameS; "Computer Name=%s\n"
0x180005136  mov     rax, r9
0x180005139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000513e  mov     r9, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180005145  test    r9, r9
0x180005148  jz      loc_180005203
0x18000514e  mov     edx, [rbp+57h+ErrorInfo.ProcessID]
0x180005151  lea     rcx, aProcesIdU; "Proces ID=%u\n"
0x180005158  mov     rax, r9
0x18000515b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005160  mov     r9, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180005167  test    r9, r9
0x18000516a  jz      loc_180005203
0x180005170  mov     edx, [rbp+57h+ErrorInfo.GeneratingComponent]
0x180005173  lea     rcx, aGeneratingcomp; "GeneratingComponent=%u\n"
0x18000517a  mov     rax, r9
0x18000517d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005182  mov     r9, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180005189  test    r9, r9
0x18000518c  jz      short loc_180005203
0x18000518e  mov     edx, [rbp+57h+ErrorInfo.Status]
0x180005191  lea     rcx, aStatusU; "Status=%u\n"
0x180005198  mov     rax, r9
0x18000519b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051a0  mov     r9, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800051a7  test    r9, r9
0x1800051aa  jz      short loc_180005203
0x1800051ac  movzx   edx, [rbp+57h+ErrorInfo.Flags]
0x1800051b0  lea     rcx, aFlags0xX; "Flags=0x%x\n"
0x1800051b7  mov     rax, r9
0x1800051ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051bf  mov     r9, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800051c6  test    r9, r9
0x1800051c9  jz      short loc_180005203
0x1800051cb  movzx   edx, [rbp+57h+ErrorInfo.DetectionLocation]
0x1800051cf  lea     rcx, aDetectionLocat; "Detection Location=%u\n"
0x1800051d6  mov     rax, r9
0x1800051d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051de  mov     r9, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800051e5  test    r9, r9
0x1800051e8  jz      short loc_180005203
0x1800051ea  mov     edx, [rbp+57h+ErrorInfo.NumberOfParameters]
0x1800051ed  lea     rcx, aParametersCoun; "Parameters Count=%u\n"
0x1800051f4  mov     rax, r9
0x1800051f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051fc  mov     r9, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180005203  xor     ebx, ebx
0x180005205  cmp     [rbp+57h+ErrorInfo.NumberOfParameters], ebx
0x180005208  jle     loc_1800052DB
0x18000520e  lea     rdi, [rbp+57h+ErrorInfo.Parameters.u]
0x180005212  mov     edx, [rdi-8]
0x180005215  mov     ecx, edx
0x180005217  sub     ecx, 1
0x18000521a  jz      loc_1800052AC
0x180005220  sub     ecx, 1
0x180005223  jz      short loc_18000529E
0x180005225  sub     ecx, 1
0x180005228  jz      short loc_18000528D
0x18000522a  sub     ecx, 1
0x18000522d  jz      short loc_180005271
0x18000522f  sub     ecx, 1
0x180005232  jz      short loc_180005263
0x180005234  cmp     ecx, 1
0x180005237  jz      short loc_180005253
0x180005239  test    r9, r9
0x18000523c  jz      loc_1800052CC
0x180005242  lea     rcx, aInvalidTypeD; "Invalid type: %d\n"
0x180005249  mov     rax, r9
0x18000524c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005251  jmp     short loc_1800052C5
0x180005253  test    r9, r9
0x180005256  jz      short loc_1800052CC
0x180005258  mov     edx, ebx
0x18000525a  lea     rcx, aParamDTruncate; "Param[%d][Truncated]\n"
0x180005261  jmp     short loc_180005249
0x180005263  test    r9, r9
0x180005266  jz      short loc_1800052CC
0x180005268  lea     rcx, aParamDPointerI; "Param[%d][Pointer]: %I64u\n"
0x18000526f  jmp     short loc_1800052B8
0x180005271  test    r9, r9
0x180005274  jz      short loc_1800052CC
0x180005276  movsx   r8d, word ptr [rdi]
0x18000527a  lea     rcx, aParamDShortD; "Param[%d][Short]: %d\n"
0x180005281  mov     edx, ebx
0x180005283  mov     rax, r9
0x180005286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528b  jmp     short loc_1800052C5
0x18000528d  test    r9, r9
0x180005290  jz      short loc_1800052CC
0x180005292  mov     r8d, [rdi]
0x180005295  lea     rcx, aParamDLongD; "Param[%d][Long]: %d\n"
0x18000529c  jmp     short loc_180005281
0x18000529e  test    r9, r9
0x1800052a1  jz      short loc_1800052CC
0x1800052a3  lea     rcx, aParamDUnicodeS; "Param[%d][Unicode]: %s\n"
0x1800052aa  jmp     short loc_1800052B8
0x1800052ac  test    r9, r9
0x1800052af  jz      short loc_1800052CC
0x1800052b1  lea     rcx, aParamDAnsiS; "Param[%d][Ansi]: %S\n"
0x1800052b8  mov     r8, [rdi]
0x1800052bb  mov     edx, ebx
0x1800052bd  mov     rax, r9
0x1800052c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052c5  mov     r9, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800052cc  inc     ebx
0x1800052ce  add     rdi, 18h
0x1800052d2  cmp     ebx, [rbp+57h+ErrorInfo.NumberOfParameters]
0x1800052d5  jl      loc_180005212
0x1800052db  lea     r8, [rbp+57h+ErrorInfo]; ErrorInfo
0x1800052df  xor     edx, edx; CopyStrings
0x1800052e1  lea     rcx, [rbp+57h+EnumHandle]; EnumHandle
0x1800052e5  call    cs:__imp_RpcErrorGetNextRecord
0x1800052ec  nop     dword ptr [rax+rax+00h]
0x1800052f1  mov     r9d, 716h
0x1800052f7  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x1800052fe  mov     ecx, eax
0x180005300  call    ElValidateWin32
0x180005305  test    eax, eax
0x180005307  jz      loc_180005116
0x18000530d  mov     rcx, [rbp+57h+var_10]
0x180005311  xor     rcx, rsp; StackCookie
0x180005314  call    __security_check_cookie
0x180005319  lea     r11, [rsp+0F0h+var_s0]
0x180005321  mov     rbx, [r11+10h]
0x180005325  mov     rdi, [r11+18h]
0x180005329  mov     rsp, r11
0x18000532c  pop     rbp
0x18000532d  retn
```
