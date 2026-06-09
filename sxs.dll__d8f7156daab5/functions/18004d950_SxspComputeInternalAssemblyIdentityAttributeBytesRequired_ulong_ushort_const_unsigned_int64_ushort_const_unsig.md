# SxspComputeInternalAssemblyIdentityAttributeBytesRequired(ulong,ushort const *,unsigned __int64,ushort const *,unsigned __int64,unsigned __int64 *)

- ea: `0x18004d950`
- end: `0x18004dafb`
- name: `?SxspComputeInternalAssemblyIdentityAttributeBytesRequired@@YAHKPEBG_K01PEA_K@Z`
- size: `427`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, unsigned __int64, const unsigned __int16 *, char *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011580`

## callees

- `0x18001c2c8`
- `0x18004d950`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18004da44`
- `ntdll!RtlPopFrame` at `0x18004da44`
- `ntdll!RtlPushFrame` at `0x18004d9ba`
- `ntdll!RtlPushFrame` at `0x18004d9ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dae1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004da1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004daa1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004da1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004daa1`

## pseudocode

```c
__int64 __fastcall SxspComputeInternalAssemblyIdentityAttributeBytesRequired(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        char *a5,
        unsigned __int64 *a6)
{
  unsigned int v6; // esi
  const char *v10; // rcx
  __int64 v11; // rax
  DWORD LastError; // eax
  int v14; // [rsp+20h] [rbp-78h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+28h] [rbp-70h] BYREF
  __int64 v16; // [rsp+40h] [rbp-58h]
  int v17; // [rsp+48h] [rbp-50h]
  int *v18; // [rsp+50h] [rbp-48h]

  v6 = 1;
  v14 = 0;
  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CE80;
  Frame.Previous = 0;
  v16 = 544438355;
  v17 = 338;
  v18 = &v14;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( !a6 )
  {
    v17 = 345;
    goto LABEL_19;
  }
  *a6 = 0;
  if ( a3 && !a2 )
  {
    v17 = 346;
LABEL_19:
    FusionpTraceParameterCheck(v10);
    SetLastError(0x57u);
    v6 = 0;
    *v18 = 0;
    goto LABEL_12;
  }
  v10 = a5;
  if ( a5 && !a4 )
  {
    v17 = 347;
    goto LABEL_19;
  }
  v11 = 80;
  if ( a2 && a3 )
    v11 = 2 * a3 + 82;
  if ( a4 && a5 )
    v11 += 2LL * (_QWORD)a5 + 2;
  *a6 = v11;
  SetLastError(0);
  *v18 = 1;
LABEL_12:
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v6 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v6;
}

```

## disassembly

```asm
0x18004d950  mov     r11, rsp
0x18004d953  push    rbx
0x18004d954  push    rbp
0x18004d955  push    rsi
0x18004d956  push    rdi
0x18004d957  push    r14
0x18004d959  push    r15
0x18004d95b  sub     rsp, 68h
0x18004d95f  mov     rax, cs:__security_cookie
0x18004d966  xor     rax, rsp
0x18004d969  mov     [rsp+98h+var_40], rax
0x18004d96e  mov     rdi, [rsp+98h+arg_28]
0x18004d976  lea     rax, qword_18006CE80
0x18004d97d  xor     r15d, r15d
0x18004d980  lea     rcx, [r11-70h]; Frame
0x18004d984  mov     esi, 1
0x18004d989  mov     [r11-78h], r15d
0x18004d98d  mov     [rsp+98h+Frame.Flags], esi
0x18004d991  mov     r14, r9
0x18004d994  mov     [r11-60h], rax
0x18004d998  mov     rbx, r8
0x18004d99b  lea     rax, [r11-78h]
0x18004d99f  mov     [r11-68h], r15
0x18004d9a3  mov     qword ptr [r11-58h], 20737853h
0x18004d9ab  mov     rbp, rdx
0x18004d9ae  mov     [rsp+98h+var_50], 152h
0x18004d9b6  mov     [r11-48h], rax
0x18004d9ba  call    cs:__imp_RtlPushFrame
0x18004d9c1  nop     dword ptr [rax+rax+00h]
0x18004d9c6  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x18004d9cd  jnz     loc_18004DABD
0x18004d9d3  test    rdi, rdi
0x18004d9d6  jz      loc_18004DAC7
0x18004d9dc  mov     [rdi], r15
0x18004d9df  test    rbx, rbx
0x18004d9e2  jnz     loc_18004DA7C
0x18004d9e8  mov     rcx, [rsp+98h+arg_20]; char *
0x18004d9f0  test    rcx, rcx
0x18004d9f3  jz      short loc_18004D9FE
0x18004d9f5  test    r14, r14
0x18004d9f8  jz      loc_18004DA8F
0x18004d9fe  mov     eax, 50h ; 'P'
0x18004da03  test    rbp, rbp
0x18004da06  jz      short loc_18004DA15
0x18004da08  test    rbx, rbx
0x18004da0b  jz      short loc_18004DA15
0x18004da0d  lea     rax, ds:52h[rbx*2]
0x18004da15  test    r14, r14
0x18004da18  jnz     short loc_18004DA6D
0x18004da1a  xor     ecx, ecx; dwErrCode
0x18004da1c  mov     [rdi], rax
0x18004da1f  call    cs:__imp_SetLastError
0x18004da26  nop     dword ptr [rax+rax+00h]
0x18004da2b  mov     rax, [rsp+98h+var_48]
0x18004da30  mov     [rax], esi
0x18004da32  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x18004da39  jnz     loc_18004DAD1
0x18004da3f  lea     rcx, [rsp+98h+Frame]; Frame
0x18004da44  call    cs:__imp_RtlPopFrame
0x18004da4b  nop     dword ptr [rax+rax+00h]
0x18004da50  mov     eax, esi
0x18004da52  mov     rcx, [rsp+98h+var_40]
0x18004da57  xor     rcx, rsp; StackCookie
0x18004da5a  call    __security_check_cookie
0x18004da5f  add     rsp, 68h
0x18004da63  pop     r15
0x18004da65  pop     r14
0x18004da67  pop     rdi
0x18004da68  pop     rsi
0x18004da69  pop     rbp
0x18004da6a  pop     rbx
0x18004da6b  retn
0x18004da6d  test    rcx, rcx
0x18004da70  jz      short loc_18004DA1A
0x18004da72  lea     rax, [rax+rcx*2]
0x18004da76  add     rax, 2
0x18004da7a  jmp     short loc_18004DA1A
0x18004da7c  test    rbp, rbp
0x18004da7f  jnz     loc_18004D9E8
0x18004da85  mov     [rsp+98h+var_50], 15Ah
0x18004da8d  jmp     short loc_18004DA97
0x18004da8f  mov     [rsp+98h+var_50], 15Bh
0x18004da97  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18004da9c  mov     ecx, 57h ; 'W'; dwErrCode
0x18004daa1  call    cs:__imp_SetLastError
0x18004daa8  nop     dword ptr [rax+rax+00h]
0x18004daad  mov     rax, [rsp+98h+var_48]
0x18004dab2  mov     esi, r15d
0x18004dab5  mov     [rax], r15d
0x18004dab8  jmp     loc_18004DA32
0x18004dabd  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18004dac2  jmp     loc_18004D9D3
0x18004dac7  mov     [rsp+98h+var_50], 159h
0x18004dacf  jmp     short loc_18004DA97
0x18004dad1  test    esi, esi
0x18004dad3  jz      short loc_18004DAE1
0x18004dad5  xor     ecx, ecx; char *
0x18004dad7  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18004dadc  jmp     loc_18004DA3F
0x18004dae1  call    cs:__imp_GetLastError
0x18004dae8  nop     dword ptr [rax+rax+00h]
0x18004daed  mov     ecx, eax; unsigned int
0x18004daef  xor     edx, edx; Format
0x18004daf1  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18004daf6  jmp     loc_18004DA3F
```
