# SxsQueryManifestInformation

- ea: `0x180062db0`
- end: `0x180062f31`
- name: `SxsQueryManifestInformation`
- size: `385`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, unsigned __int16 *@<rdx>, unsigned __int64, void *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002b7e0`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18005d2b0`
- `0x180062568`
- `0x180062db0`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062e4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062ea9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062eee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062e4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062ea9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062eee`

## pseudocode

```c
__int64 __fastcall SxsQueryManifestInformation(
        int a1,
        unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned __int64 a5,
        _QWORD *a6,
        unsigned __int64 *a7)
{
  const char *v11; // rcx
  unsigned int v12; // ebx
  int v14; // [rsp+30h] [rbp-40h] BYREF
  int v15; // [rsp+38h] [rbp-38h] BYREF
  __int64 v16; // [rsp+40h] [rbp-30h]
  __int64 *v17; // [rsp+48h] [rbp-28h]
  __int64 v18; // [rsp+50h] [rbp-20h]
  int v19; // [rsp+58h] [rbp-18h]
  unsigned int *v20; // [rsp+60h] [rbp-10h]

  v17 = &qword_180076C00;
  v14 = 0;
  v20 = (unsigned int *)&v14;
  v15 = 1;
  v16 = 0;
  v18 = 544438355;
  v19 = 46;
  CFrame::BaseEnter((CFrame *)&v15);
  if ( a7 )
    *a7 = 0;
  if ( (a1 & 0xFFFFFFFE) != 0 )
  {
    v19 = 51;
LABEL_5:
    FusionpTraceParameterCheck(v11);
    SetLastError(0x57u);
    *v20 = 0;
    goto LABEL_18;
  }
  if ( !a2 )
  {
    v19 = 52;
    goto LABEL_5;
  }
  if ( a3 != 1 )
  {
    v19 = 53;
    goto LABEL_5;
  }
  if ( a5 )
  {
    if ( !a6 )
    {
      v19 = 55;
      goto LABEL_5;
    }
  }
  else if ( !a7 )
  {
    v19 = 56;
    goto LABEL_5;
  }
  SetLastError(0);
  if ( (unsigned int)SxspQueryManifestInformationBasic(a1, a2, a4, a5, a6, a7) )
  {
    SetLastError(0);
    *v20 = 1;
  }
  else
  {
    *v20 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180076BE0);
  }
LABEL_18:
  v12 = *v20;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v15);
  return v12;
}

```

## disassembly

```asm
0x180062db0  push    rbp
0x180062db2  push    rbx
0x180062db3  push    rsi
0x180062db4  push    rdi
0x180062db5  push    r12
0x180062db7  push    r14
0x180062db9  push    r15
0x180062dbb  mov     rbp, rsp
0x180062dbe  sub     rsp, 70h
0x180062dc2  mov     rax, cs:__security_cookie
0x180062dc9  xor     rax, rsp
0x180062dcc  mov     [rbp+var_8], rax
0x180062dd0  mov     r14, [rbp+arg_28]
0x180062dd4  lea     rax, qword_180076C00
0x180062ddb  mov     rbx, [rbp+arg_30]
0x180062ddf  mov     r15d, ecx
0x180062de2  mov     [rbp+var_28], rax
0x180062de6  lea     rcx, [rbp+var_38]; this
0x180062dea  lea     rax, [rbp+var_40]
0x180062dee  mov     [rbp+var_40], 0
0x180062df5  mov     [rbp+var_10], rax
0x180062df9  mov     r12d, r9d
0x180062dfc  mov     edi, r8d
0x180062dff  mov     [rbp+var_38], 1
0x180062e06  mov     rsi, rdx
0x180062e09  mov     [rbp+var_30], 0
0x180062e11  mov     [rbp+var_20], 20737853h
0x180062e19  mov     [rbp+var_18], 2Eh ; '.'
0x180062e20  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180062e25  test    rbx, rbx
0x180062e28  jz      short loc_180062E31
0x180062e2a  mov     qword ptr [rbx], 0
0x180062e31  test    r15d, 0FFFFFFFEh
0x180062e38  jz      short loc_180062E66
0x180062e3a  mov     [rbp+var_18], 33h ; '3'
0x180062e41  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180062e46  mov     ecx, 57h ; 'W'; dwErrCode
0x180062e4b  call    cs:__imp_SetLastError
0x180062e52  nop     dword ptr [rax+rax+00h]
0x180062e57  mov     rax, [rbp+var_10]
0x180062e5b  mov     dword ptr [rax], 0
0x180062e61  jmp     loc_180062F04
0x180062e66  test    rsi, rsi
0x180062e69  jnz     short loc_180062E74
0x180062e6b  mov     [rbp+var_18], 34h ; '4'
0x180062e72  jmp     short loc_180062E41
0x180062e74  cmp     edi, 1
0x180062e77  jz      short loc_180062E82
0x180062e79  mov     [rbp+var_18], 35h ; '5'
0x180062e80  jmp     short loc_180062E41
0x180062e82  mov     rdi, [rbp+arg_20]
0x180062e86  test    rdi, rdi
0x180062e89  jz      short loc_180062E99
0x180062e8b  test    r14, r14
0x180062e8e  jnz     short loc_180062EA7
0x180062e90  mov     [rbp+var_18], 37h ; '7'
0x180062e97  jmp     short loc_180062E41
0x180062e99  test    rbx, rbx
0x180062e9c  jnz     short loc_180062EA7
0x180062e9e  mov     [rbp+var_18], 38h ; '8'
0x180062ea5  jmp     short loc_180062E41
0x180062ea7  xor     ecx, ecx; dwErrCode
0x180062ea9  call    cs:__imp_SetLastError
0x180062eb0  nop     dword ptr [rax+rax+00h]
0x180062eb5  mov     r9, rdi; unsigned __int64
0x180062eb8  mov     [rsp+70h+var_48], rbx; unsigned __int64 *
0x180062ebd  mov     r8d, r12d; unsigned int
0x180062ec0  mov     [rsp+70h+var_50], r14; void *
0x180062ec5  mov     rdx, rsi; unsigned __int16 *
0x180062ec8  mov     ecx, r15d; unsigned int
0x180062ecb  call    ?SxspQueryManifestInformationBasic@@YAHKPEBGK_KPEAXPEA_K@Z; SxspQueryManifestInformationBasic(ulong,ushort const *,ulong,unsigned __int64,void *,unsigned __int64 *)
0x180062ed0  test    eax, eax
0x180062ed2  jnz     short loc_180062EEC
0x180062ed4  mov     rax, [rbp+var_10]
0x180062ed8  lea     rcx, off_180076BE0; struct _CALL_SITE_INFO *
0x180062edf  mov     dword ptr [rax], 0
0x180062ee5  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180062eea  jmp     short loc_180062F04
0x180062eec  xor     ecx, ecx; dwErrCode
0x180062eee  call    cs:__imp_SetLastError
0x180062ef5  nop     dword ptr [rax+rax+00h]
0x180062efa  mov     rax, [rbp+var_10]
0x180062efe  mov     dword ptr [rax], 1
0x180062f04  mov     rax, [rbp+var_10]
0x180062f08  lea     rcx, [rbp+var_38]; this
0x180062f0c  mov     ebx, [rax]
0x180062f0e  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180062f13  mov     eax, ebx
0x180062f15  mov     rcx, [rbp+var_8]
0x180062f19  xor     rcx, rsp; StackCookie
0x180062f1c  call    __security_check_cookie
0x180062f21  add     rsp, 70h
0x180062f25  pop     r15
0x180062f27  pop     r14
0x180062f29  pop     r12
0x180062f2b  pop     rdi
0x180062f2c  pop     rsi
0x180062f2d  pop     rbx
0x180062f2e  pop     rbp
0x180062f2f  retn
```
