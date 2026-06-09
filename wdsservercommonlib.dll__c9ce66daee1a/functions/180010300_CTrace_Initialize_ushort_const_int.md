# CTrace::Initialize(ushort const *,int)

- ea: `0x180010300`
- end: `0x180010499`
- name: `?Initialize@CTrace@@QEAAKPEBGH@Z`
- size: `409`
- prototype: `unsigned int(CTrace *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x180005830`
- `0x180010300`
- `0x180011088`
- `0x180011184`
- `0x180011374`
- `0x180016520`
- `0x18002f3ba`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800103e0`
- `KERNEL32!GetLastError` at `0x18001040b`
- `KERNEL32!GetLastError` at `0x18001042f`
- `KERNEL32!GetLastError` at `0x1800103e0`
- `KERNEL32!GetLastError` at `0x18001040b`
- `KERNEL32!GetLastError` at `0x18001042f`
- `KERNEL32!GetCurrentProcessId` at `0x180010364`
- `KERNEL32!GetCurrentProcessId` at `0x180010364`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800103d0`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800103d0`
- `KERNEL32!SetEnvironmentVariableW` at `0x1800103fb`
- `KERNEL32!SetEnvironmentVariableW` at `0x1800103fb`

## pseudocode

```c
__int64 __fastcall CTrace::Initialize(CTrace *this, WCHAR *p_Buffer)
{
  unsigned int v4; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned __int16 *v13; // rax
  WCHAR Name[264]; // [rsp+20h] [rbp-448h] BYREF
  WCHAR Buffer; // [rsp+230h] [rbp-238h] BYREF
  _BYTE v17[526]; // [rsp+232h] [rbp-236h] BYREF

  Name[0] = 0;
  v4 = 0;
  memset_0(&Name[1], 0, 0x206u);
  Buffer = 0;
  memset_0(v17, 0, 0x206u);
  CurrentProcessId = GetCurrentProcessId();
  v6 = (unsigned int)StringCchPrintfW(Name, 0x104u, L"WDS_TRACING_%u", CurrentProcessId);
  if ( (int)ElValidateHr_2(v6, v7, v8, 222, *(_DWORD *)Name) < 0 )
  {
    if ( (int)v6 < 0 && (v6 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v6;
    else
      return (unsigned int)v6;
  }
  if ( GetEnvironmentVariableW(Name, &Buffer, 0x104u) )
  {
    p_Buffer = &Buffer;
  }
  else
  {
    if ( GetLastError() != 203 )
    {
      LastError = GetLastError();
      v12 = 242;
LABEL_10:
      v4 = ElValidateWin32_3(LastError, v10, v11, v12);
      if ( !v4 )
        return 31;
      return v4;
    }
    if ( !SetEnvironmentVariableW(Name, p_Buffer) )
    {
      LastError = GetLastError();
      v12 = 237;
      goto LABEL_10;
    }
  }
  v13 = WcsDup(p_Buffer);
  *(_QWORD *)this = v13;
  if ( v13 )
  {
    if ( qword_180049D60 )
      McGenEventRegister_s_pfnEventRegister();
  }
  else
  {
    return 8;
  }
  return v4;
}

```

## disassembly

```asm
0x180010300  mov     [rsp+arg_10], rbx
0x180010305  mov     [rsp+arg_18], rbp
0x18001030a  push    rsi
0x18001030b  push    rdi
0x18001030c  push    r14
0x18001030e  sub     rsp, 450h
0x180010315  mov     rax, cs:__security_cookie
0x18001031c  xor     rax, rsp
0x18001031f  mov     [rsp+468h+var_28], rax
0x180010327  mov     rsi, rdx
0x18001032a  mov     r14, rcx
0x18001032d  xor     ebp, ebp
0x18001032f  lea     rcx, [rsp+468h+var_446]; void *
0x180010334  mov     edi, 206h
0x180010339  mov     [rsp+468h+Name], bp
0x18001033e  mov     r8d, edi; Size
0x180010341  xor     edx, edx; Val
0x180010343  mov     ebx, ebp
0x180010345  call    memset_0
0x18001034a  mov     r8d, edi; Size
0x18001034d  mov     [rsp+468h+Buffer], bp
0x180010355  xor     edx, edx; Val
0x180010357  lea     rcx, [rsp+468h+var_236]; void *
0x18001035f  call    memset_0
0x180010364  call    cs:__imp_GetCurrentProcessId
0x18001036b  nop     dword ptr [rax+rax+00h]
0x180010370  lea     r8, aWdsTracingU; "WDS_TRACING_%u"
0x180010377  mov     edx, 104h; unsigned __int64
0x18001037c  mov     r9d, eax
0x18001037f  lea     rcx, [rsp+468h+Name]; unsigned __int16 *
0x180010384  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010389  mov     r9d, 0DEh
0x18001038f  mov     ecx, eax
0x180010391  mov     edi, eax
0x180010393  call    ElValidateHr_2
0x180010398  test    eax, eax
0x18001039a  jns     short loc_1800103BD
0x18001039c  test    edi, edi
0x18001039e  jns     short loc_1800103B6
0x1800103a0  mov     eax, edi
0x1800103a2  and     eax, 1FFF0000h
0x1800103a7  cmp     eax, 70000h
0x1800103ac  jnz     short loc_1800103B6
0x1800103ae  movzx   ebx, di
0x1800103b1  jmp     loc_18001046E
0x1800103b6  mov     ebx, edi
0x1800103b8  jmp     loc_18001046E
0x1800103bd  mov     r8d, 104h; nSize
0x1800103c3  lea     rdx, [rsp+468h+Buffer]; lpBuffer
0x1800103cb  lea     rcx, [rsp+468h+Name]; lpName
0x1800103d0  call    cs:__imp_GetEnvironmentVariableW
0x1800103d7  nop     dword ptr [rax+rax+00h]
0x1800103dc  test    eax, eax
0x1800103de  jnz     short loc_180010443
0x1800103e0  call    cs:__imp_GetLastError
0x1800103e7  nop     dword ptr [rax+rax+00h]
0x1800103ec  cmp     eax, 0CBh
0x1800103f1  jnz     short loc_18001042F
0x1800103f3  mov     rdx, rsi; lpValue
0x1800103f6  lea     rcx, [rsp+468h+Name]; lpName
0x1800103fb  call    cs:__imp_SetEnvironmentVariableW
0x180010402  nop     dword ptr [rax+rax+00h]
0x180010407  test    eax, eax
0x180010409  jnz     short loc_18001044B
0x18001040b  call    cs:__imp_GetLastError
0x180010412  nop     dword ptr [rax+rax+00h]
0x180010417  mov     r9d, 0EDh
0x18001041d  mov     ecx, eax
0x18001041f  call    ElValidateWin32_3
0x180010424  mov     ebx, eax
0x180010426  test    eax, eax
0x180010428  jnz     short loc_18001046E
0x18001042a  lea     ebx, [rax+1Fh]
0x18001042d  jmp     short loc_18001046E
0x18001042f  call    cs:__imp_GetLastError
0x180010436  nop     dword ptr [rax+rax+00h]
0x18001043b  mov     r9d, 0F2h
0x180010441  jmp     short loc_18001041D
0x180010443  lea     rsi, [rsp+468h+Buffer]
0x18001044b  mov     rcx, rsi; Src
0x18001044e  call    ?WcsDup@@YAPEAGPEBG@Z; WcsDup(ushort const *)
0x180010453  mov     [r14], rax
0x180010456  test    rax, rax
0x180010459  jnz     short loc_180010460
0x18001045b  lea     ebx, [rax+8]
0x18001045e  jmp     short loc_18001046E
0x180010460  cmp     cs:qword_180049D60, rbp
0x180010467  jz      short loc_18001046E
0x180010469  call    McGenEventRegister_s_pfnEventRegister
0x18001046e  mov     eax, ebx
0x180010470  mov     rcx, [rsp+468h+var_28]
0x180010478  xor     rcx, rsp; StackCookie
0x18001047b  call    __security_check_cookie
0x180010480  lea     r11, [rsp+468h+var_18]
0x180010488  mov     rbx, [r11+30h]
0x18001048c  mov     rbp, [r11+38h]
0x180010490  mov     rsp, r11
0x180010493  pop     r14
0x180010495  pop     rdi
0x180010496  pop     rsi
0x180010497  retn
```
