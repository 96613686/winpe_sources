# CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(ushort * *,unsigned __int64 *,unsigned __int64 *,void *,ulong *,ulong *)

- ea: `0x18004a810`
- end: `0x18004aab9`
- name: `?Win32CopyIntoBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAPEAGPEA_K1PEAXPEAK3@Z`
- size: `681`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180049590`
- `0x180049970`
- `0x180049df0`
- `0x18004a060`
- `0x18004fa50`
- `0x180050010`
- `0x180066b5c`

## callees

- `0x18001c2c8`
- `0x18004a810`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a0dd`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18004a9ab`
- `ntdll!RtlPopFrame` at `0x18004a9ab`
- `ntdll!RtlPushFrame` at `0x18004a8a0`
- `ntdll!RtlPushFrame` at `0x18004a8a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aa18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aa43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aa70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aa18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aa43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aa70`

## pseudocode

```c
__int64 __fastcall CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(
        __int64 a1,
        void **a2,
        size_t *a3,
        _QWORD *a4,
        __int64 a5,
        _DWORD *a6,
        _DWORD *a7)
{
  const char *v11; // rcx
  char *v12; // r15
  __int64 v13; // r12
  size_t v14; // rbx
  unsigned int v15; // ebx
  DWORD LastError; // eax
  int v19; // [rsp+28h] [rbp-90h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+30h] [rbp-88h] BYREF
  __int64 v21; // [rsp+48h] [rbp-70h]
  int v22; // [rsp+50h] [rbp-68h]
  int *v23; // [rsp+58h] [rbp-60h]

  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer'::`2'::__stc;
  Frame.Previous = 0;
  v21 = 544438355;
  v22 = 1422;
  v23 = &v19;
  v19 = 0;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( !a3 )
  {
    v22 = 1435;
LABEL_28:
    FusionpTraceParameterCheck(v11);
    SetLastError(0x57u);
    *v23 = 0;
    goto LABEL_16;
  }
  if ( !a2 )
  {
    v22 = 1436;
    goto LABEL_28;
  }
  v12 = (char *)*a2;
  v13 = (__int64)*a2 - a5;
  if ( a6 && v13 > 0xFFFFFFFFLL )
  {
    v22 = 1443;
    FusionpTraceParameterCheck(v11);
    SetLastError(0x57u);
    *v23 = 0;
  }
  else
  {
    v14 = *(_QWORD *)(a1 + 32);
    if ( v14 && ((v14 = 2 * v14 + 2, v14 > 0xFFFFFFFF) || *a3 < v14) )
    {
      SetLastError(0x7Au);
    }
    else
    {
      memcpy_0(v12, *(const void **)(a1 + 16), v14);
      if ( a6 && v14 )
        *a6 = v13;
      if ( a7 )
      {
        if ( v14 )
          *a7 = v14 - 2;
        else
          *a7 = 0;
      }
      *a4 += v14;
      *a3 -= v14;
      *a2 = &v12[v14];
      v19 = 1;
    }
  }
LABEL_16:
  v15 = v19;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v23 )
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
  return v15;
}

```

## disassembly

```asm
0x18004a810  mov     r11, rsp
0x18004a813  push    rbx
0x18004a814  sub     rsp, 0B0h
0x18004a81b  mov     rax, cs:__security_cookie
0x18004a822  xor     rax, rsp
0x18004a825  mov     [rsp+0B8h+var_58], rax
0x18004a82a  mov     [r11-10h], rbp
0x18004a82e  lea     rax, ?__stc@?1??Win32CopyIntoBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAPEAGPEA_K1PEAXPEAK3@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(ushort * *,unsigned __int64 *,unsigned __int64 *,void *,ulong *,ulong *)'::`2'::__stc
0x18004a835  mov     [r11-18h], rsi
0x18004a839  mov     rbx, rcx
0x18004a83c  mov     rsi, [rsp+0B8h+arg_28]
0x18004a844  mov     rbp, rdx
0x18004a847  mov     [r11-20h], rdi
0x18004a84b  mov     rdi, r8
0x18004a84e  mov     [rsp+0B8h+Frame.Flags], 1
0x18004a856  mov     [r11-30h], r13
0x18004a85a  mov     r13, r9
0x18004a85d  mov     [r11-38h], r14
0x18004a861  mov     r14, [rsp+0B8h+arg_30]
0x18004a869  mov     [r11-78h], rax
0x18004a86d  lea     rax, [rsp+0B8h+var_90]
0x18004a872  mov     [r11-40h], r15
0x18004a876  xor     r15d, r15d
0x18004a879  mov     [r11-80h], r15
0x18004a87d  mov     [rsp+0B8h+var_98], rcx
0x18004a882  lea     rcx, [rsp+0B8h+Frame]; Frame
0x18004a887  mov     qword ptr [r11-70h], 20737853h
0x18004a88f  mov     [rsp+0B8h+var_68], 58Eh
0x18004a897  mov     [r11-60h], rax
0x18004a89b  mov     [rsp+0B8h+var_90], r15d
0x18004a8a0  call    cs:__imp_RtlPushFrame
0x18004a8a7  nop     dword ptr [rax+rax+00h]
0x18004a8ac  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x18004a8b3  jnz     loc_18004AA34
0x18004a8b9  test    rsi, rsi
0x18004a8bc  jz      short loc_18004A8C1
0x18004a8be  mov     [rsi], r15d
0x18004a8c1  test    r14, r14
0x18004a8c4  jz      short loc_18004A8C9
0x18004a8c6  mov     [r14], r15d
0x18004a8c9  test    rdi, rdi
0x18004a8cc  jz      loc_18004AA54
0x18004a8d2  test    rbp, rbp
0x18004a8d5  jz      loc_18004AA5E
0x18004a8db  mov     r15, [rbp+0]
0x18004a8df  mov     eax, 0FFFFFFFFh
0x18004a8e4  mov     [rsp+0B8h+var_28], r12
0x18004a8ec  mov     r12, r15
0x18004a8ef  sub     r12, [rsp+0B8h+arg_20]
0x18004a8f7  test    rsi, rsi
0x18004a8fa  jnz     loc_18004A9FD
0x18004a900  mov     rbx, [rbx+20h]
0x18004a904  test    rbx, rbx
0x18004a907  jz      short loc_18004A923
0x18004a909  lea     rbx, ds:2[rbx*2]
0x18004a911  cmp     rbx, rax
0x18004a914  ja      loc_18004AA3E
0x18004a91a  cmp     [rdi], rbx
0x18004a91d  jb      loc_18004AA3E
0x18004a923  mov     rdx, [rsp+0B8h+var_98]
0x18004a928  mov     r8, rbx; Size
0x18004a92b  mov     rcx, r15; void *
0x18004a92e  mov     rdx, [rdx+10h]; Src
0x18004a932  call    memcpy_0
0x18004a937  test    rsi, rsi
0x18004a93a  jnz     loc_18004A9EC
0x18004a940  test    r14, r14
0x18004a943  jnz     loc_18004A9D0
0x18004a949  add     [r13+0], rbx
0x18004a94d  lea     rax, [r15+rbx]
0x18004a951  sub     [rdi], rbx
0x18004a954  mov     [rbp+0], rax
0x18004a958  mov     [rsp+0B8h+var_90], 1
0x18004a960  mov     r12, [rsp+0B8h+var_28]
0x18004a968  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18004a96f  mov     ebx, [rsp+0B8h+var_90]
0x18004a973  mov     r15, [rsp+0B8h+var_40]
0x18004a978  mov     r14, [rsp+0B8h+var_38]
0x18004a980  mov     r13, [rsp+0B8h+var_30]
0x18004a988  mov     rdi, [rsp+0B8h+var_20]
0x18004a990  mov     rsi, [rsp+0B8h+var_18]
0x18004a998  mov     rbp, [rsp+0B8h+var_10]
0x18004a9a0  jnz     loc_18004AA89
0x18004a9a6  lea     rcx, [rsp+0B8h+Frame]; Frame
0x18004a9ab  call    cs:__imp_RtlPopFrame
0x18004a9b2  nop     dword ptr [rax+rax+00h]
0x18004a9b7  mov     eax, ebx
0x18004a9b9  mov     rcx, [rsp+0B8h+var_58]
0x18004a9be  xor     rcx, rsp; StackCookie
0x18004a9c1  call    __security_check_cookie
0x18004a9c6  add     rsp, 0B0h
0x18004a9cd  pop     rbx
0x18004a9ce  retn
0x18004a9d0  test    rbx, rbx
0x18004a9d3  jz      short loc_18004A9E0
0x18004a9d5  lea     eax, [rbx-2]
0x18004a9d8  mov     [r14], eax
0x18004a9db  jmp     loc_18004A949
0x18004a9e0  mov     dword ptr [r14], 0
0x18004a9e7  jmp     loc_18004A949
0x18004a9ec  test    rbx, rbx
0x18004a9ef  jz      loc_18004A940
0x18004a9f5  mov     [rsi], r12d
0x18004a9f8  jmp     loc_18004A940
0x18004a9fd  cmp     r12, rax
0x18004aa00  jle     loc_18004A900
0x18004aa06  mov     [rsp+0B8h+var_68], 5A3h
0x18004aa0e  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18004aa13  mov     ecx, 57h ; 'W'; dwErrCode
0x18004aa18  call    cs:__imp_SetLastError
0x18004aa1f  nop     dword ptr [rax+rax+00h]
0x18004aa24  mov     rax, [rsp+0B8h+var_60]
0x18004aa29  mov     dword ptr [rax], 0
0x18004aa2f  jmp     loc_18004A960
0x18004aa34  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18004aa39  jmp     loc_18004A8B9
0x18004aa3e  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18004aa43  call    cs:__imp_SetLastError
0x18004aa4a  nop     dword ptr [rax+rax+00h]
0x18004aa4f  jmp     loc_18004A960
0x18004aa54  mov     [rsp+0B8h+var_68], 59Bh
0x18004aa5c  jmp     short loc_18004AA66
0x18004aa5e  mov     [rsp+0B8h+var_68], 59Ch
0x18004aa66  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18004aa6b  mov     ecx, 57h ; 'W'; dwErrCode
0x18004aa70  call    cs:__imp_SetLastError
0x18004aa77  nop     dword ptr [rax+rax+00h]
0x18004aa7c  mov     rax, [rsp+0B8h+var_60]
0x18004aa81  mov     [rax], r15d
0x18004aa84  jmp     loc_18004A968
0x18004aa89  mov     rax, [rsp+0B8h+var_60]
0x18004aa8e  cmp     dword ptr [rax], 0
0x18004aa91  jz      short loc_18004AA9F
0x18004aa93  xor     ecx, ecx; char *
0x18004aa95  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18004aa9a  jmp     loc_18004A9A6
0x18004aa9f  call    cs:__imp_GetLastError
0x18004aaa6  nop     dword ptr [rax+rax+00h]
0x18004aaab  mov     ecx, eax; unsigned int
0x18004aaad  xor     edx, edx; Format
0x18004aaaf  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18004aab4  jmp     loc_18004A9A6
```
