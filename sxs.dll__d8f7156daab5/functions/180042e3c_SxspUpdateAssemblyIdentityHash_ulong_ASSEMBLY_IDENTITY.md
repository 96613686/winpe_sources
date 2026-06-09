# SxspUpdateAssemblyIdentityHash(ulong,_ASSEMBLY_IDENTITY *)

- ea: `0x180042e3c`
- end: `0x1800430ad`
- name: `?SxspUpdateAssemblyIdentityHash@@YAHKPEAU_ASSEMBLY_IDENTITY@@@Z`
- size: `625`
- prototype: `__int64 __fastcall(unsigned int, struct _ASSEMBLY_IDENTITY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180042ce0`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180042e3c`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180042f97`
- `ntdll!RtlPopFrame` at `0x180042fc7`
- `ntdll!RtlPopFrame` at `0x180042f97`
- `ntdll!RtlPopFrame` at `0x180042fc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004304c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004304c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043093`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042ebe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042f47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042f70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043024`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042ebe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042f47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042f70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043024`

## pseudocode

```c
__int64 __fastcall SxspUpdateAssemblyIdentityHash(__int64 a1, struct _ASSEMBLY_IDENTITY *a2)
{
  const char *v3; // rcx
  __int64 v4; // r14
  unsigned int v5; // esi
  int *v6; // rbx
  const char *v7; // rcx
  int v8; // edx
  unsigned int i; // r8d
  __int64 v10; // rax
  int v11; // ebx
  unsigned int v12; // ebx
  DWORD LastError; // eax
  DWORD v15; // eax
  int v16; // [rsp+20h] [rbp-39h] BYREF
  int v17; // [rsp+24h] [rbp-35h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+28h] [rbp-31h] BYREF
  __int64 v19; // [rsp+40h] [rbp-19h]
  int v20; // [rsp+48h] [rbp-11h]
  int *v21; // [rsp+50h] [rbp-9h]
  struct _TEB_ACTIVE_FRAME v22; // [rsp+58h] [rbp-1h] BYREF
  __int64 v23; // [rsp+70h] [rbp+17h]
  int v24; // [rsp+78h] [rbp+1Fh]
  int *v25; // [rsp+80h] [rbp+27h]

  v23 = 544438355;
  v16 = 0;
  v22.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071070;
  v22.Previous = 0;
  v24 = 235;
  v22.Flags = 1;
  v25 = &v16;
  CFrame::BaseEnter((CFrame *)&v22);
  if ( !a2 )
  {
    v24 = 238;
    FusionpTraceParameterCheck(v3);
    SetLastError(0x57u);
    *v25 = 0;
    goto LABEL_16;
  }
  if ( !*((_DWORD *)a2 + 8) )
  {
LABEL_15:
    v16 = 1;
    goto LABEL_16;
  }
  SetLastError(0);
  v4 = *((_QWORD *)a2 + 5);
  v5 = *((_DWORD *)a2 + 4);
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071E50;
  v6 = (int *)((char *)a2 + 12);
  v17 = 0;
  v21 = &v17;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v19 = 544438355;
  v20 = 1084;
  CFrame::BaseEnter((CFrame *)&Frame);
  if ( a2 != (struct _ASSEMBLY_IDENTITY *)-12LL )
    *v6 = 0;
  if ( !v5 || v4 )
  {
    if ( a2 != (struct _ASSEMBLY_IDENTITY *)-12LL )
    {
      v8 = 0;
      for ( i = 0; i < v5; v8 = *(_DWORD *)(*(_QWORD *)(v4 + 8 * v10) + 68LL) + 65599 * v8 )
        v10 = i++;
      *v6 = v8;
      SetLastError(0);
      v11 = 1;
      *v21 = 1;
      goto LABEL_12;
    }
    v20 = 1093;
  }
  else
  {
    v20 = 1092;
  }
  FusionpTraceParameterCheck(v7);
  SetLastError(0x57u);
  v11 = 0;
  *v21 = 0;
LABEL_12:
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v11 )
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
  if ( v11 )
  {
    *((_DWORD *)a2 + 8) = 0;
    goto LABEL_15;
  }
  *v25 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007D120);
LABEL_16:
  v12 = v16;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v25 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v15 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v15, 0);
    }
  }
  RtlPopFrame(&v22);
  return v12;
}

```

## disassembly

```asm
0x180042e3c  mov     [rsp-8+arg_0], rbx
0x180042e41  mov     [rsp-8+arg_10], rsi
0x180042e46  push    rbp
0x180042e47  push    rdi
0x180042e48  push    r12
0x180042e4a  push    r14
0x180042e4c  push    r15
0x180042e4e  lea     rbp, [rsp-37h]
0x180042e53  sub     rsp, 90h
0x180042e5a  mov     rax, cs:__security_cookie
0x180042e61  xor     rax, rsp
0x180042e64  mov     [rbp+57h+var_28], rax
0x180042e68  xor     r15d, r15d
0x180042e6b  mov     [rbp+57h+var_40], 20737853h
0x180042e73  lea     rax, qword_180071070
0x180042e7a  mov     [rbp+57h+var_90], r15d
0x180042e7e  mov     [rbp+57h+var_58.Context], rax
0x180042e82  lea     rcx, [rbp+57h+var_58]; this
0x180042e86  lea     rax, [rbp+57h+var_90]
0x180042e8a  mov     [rbp+57h+var_58.Previous], r15
0x180042e8e  lea     r12d, [r15+1]
0x180042e92  mov     [rbp+57h+var_38], 0EBh
0x180042e99  mov     [rbp+57h+var_58.Flags], r12d
0x180042e9d  mov     rdi, rdx
0x180042ea0  mov     [rbp+57h+var_30], rax
0x180042ea4  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180042ea9  test    rdi, rdi
0x180042eac  jz      loc_180043013
0x180042eb2  cmp     [rdi+20h], r15d
0x180042eb6  jz      loc_180042FAF
0x180042ebc  xor     ecx, ecx; dwErrCode
0x180042ebe  call    cs:__imp_SetLastError
0x180042ec5  nop     dword ptr [rax+rax+00h]
0x180042eca  mov     r14, [rdi+28h]
0x180042ece  lea     rax, qword_180071E50
0x180042ed5  mov     esi, [rdi+10h]
0x180042ed8  lea     rcx, [rbp+57h+Frame]; this
0x180042edc  mov     [rbp+57h+Frame.Context], rax
0x180042ee0  lea     rbx, [rdi+0Ch]
0x180042ee4  lea     rax, [rbp+57h+var_8C]
0x180042ee8  mov     [rbp+57h+var_8C], r15d
0x180042eec  mov     [rbp+57h+var_60], rax
0x180042ef0  mov     [rbp+57h+Frame.Flags], r12d
0x180042ef4  mov     [rbp+57h+Frame.Previous], r15
0x180042ef8  mov     [rbp+57h+var_70], 20737853h
0x180042f00  mov     [rbp+57h+var_68], 43Ch
0x180042f07  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180042f0c  test    rbx, rbx
0x180042f0f  jz      short loc_180042F14
0x180042f11  mov     [rbx], r15d
0x180042f14  test    esi, esi
0x180042f16  jnz     loc_180042FFE
0x180042f1c  test    rbx, rbx
0x180042f1f  jz      short loc_180042F5F
0x180042f21  mov     edx, r15d
0x180042f24  mov     r8d, r15d
0x180042f27  test    esi, esi
0x180042f29  jz      short loc_180042F43
0x180042f2b  mov     eax, r8d
0x180042f2e  add     r8d, r12d
0x180042f31  imul    edx, 1003Fh
0x180042f37  mov     rcx, [r14+rax*8]
0x180042f3b  add     edx, [rcx+44h]
0x180042f3e  cmp     r8d, esi
0x180042f41  jb      short loc_180042F2B
0x180042f43  xor     ecx, ecx; dwErrCode
0x180042f45  mov     [rbx], edx
0x180042f47  call    cs:__imp_SetLastError
0x180042f4e  nop     dword ptr [rax+rax+00h]
0x180042f53  mov     rax, [rbp+57h+var_60]
0x180042f57  mov     ebx, r12d
0x180042f5a  mov     [rax], r12d
0x180042f5d  jmp     short loc_180042F86
0x180042f5f  mov     [rbp+57h+var_68], 445h
0x180042f66  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180042f6b  mov     ecx, 57h ; 'W'; dwErrCode
0x180042f70  call    cs:__imp_SetLastError
0x180042f77  nop     dword ptr [rax+rax+00h]
0x180042f7c  mov     rax, [rbp+57h+var_60]
0x180042f80  mov     ebx, r15d
0x180042f83  mov     [rax], r15d
0x180042f86  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180042f8d  jnz     loc_18004303C
0x180042f93  lea     rcx, [rbp+57h+Frame]; Frame
0x180042f97  call    cs:__imp_RtlPopFrame
0x180042f9e  nop     dword ptr [rax+rax+00h]
0x180042fa3  test    ebx, ebx
0x180042fa5  jz      loc_180043066
0x180042fab  mov     [rdi+20h], r15d
0x180042faf  mov     [rbp+57h+var_90], r12d
0x180042fb3  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180042fba  mov     ebx, [rbp+57h+var_90]
0x180042fbd  jnz     loc_18004307E
0x180042fc3  lea     rcx, [rbp+57h+var_58]; Frame
0x180042fc7  call    cs:__imp_RtlPopFrame
0x180042fce  nop     dword ptr [rax+rax+00h]
0x180042fd3  mov     eax, ebx
0x180042fd5  mov     rcx, [rbp+57h+var_28]
0x180042fd9  xor     rcx, rsp; StackCookie
0x180042fdc  call    __security_check_cookie
0x180042fe1  lea     r11, [rsp+0B0h+var_20]
0x180042fe9  mov     rbx, [r11+30h]
0x180042fed  mov     rsi, [r11+40h]
0x180042ff1  mov     rsp, r11
0x180042ff4  pop     r15
0x180042ff6  pop     r14
0x180042ff8  pop     r12
0x180042ffa  pop     rdi
0x180042ffb  pop     rbp
0x180042ffc  retn
0x180042ffe  test    r14, r14
0x180043001  jnz     loc_180042F1C
0x180043007  mov     [rbp+57h+var_68], 444h
0x18004300e  jmp     loc_180042F66
0x180043013  mov     [rbp+57h+var_38], 0EEh
0x18004301a  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18004301f  mov     ecx, 57h ; 'W'; dwErrCode
0x180043024  call    cs:__imp_SetLastError
0x18004302b  nop     dword ptr [rax+rax+00h]
0x180043030  mov     rax, [rbp+57h+var_30]
0x180043034  mov     [rax], r15d
0x180043037  jmp     loc_180042FB3
0x18004303c  test    ebx, ebx
0x18004303e  jz      short loc_18004304C
0x180043040  xor     ecx, ecx; char *
0x180043042  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180043047  jmp     loc_180042F93
0x18004304c  call    cs:__imp_GetLastError
0x180043053  nop     dword ptr [rax+rax+00h]
0x180043058  mov     ecx, eax; unsigned int
0x18004305a  xor     edx, edx; Format
0x18004305c  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180043061  jmp     loc_180042F93
0x180043066  mov     rax, [rbp+57h+var_30]
0x18004306a  lea     rcx, off_18007D120; struct _CALL_SITE_INFO *
0x180043071  mov     [rax], r15d
0x180043074  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180043079  jmp     loc_180042FB3
0x18004307e  mov     rax, [rbp+57h+var_30]
0x180043082  cmp     [rax], r15d
0x180043085  jz      short loc_180043093
0x180043087  xor     ecx, ecx; char *
0x180043089  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18004308e  jmp     loc_180042FC3
0x180043093  call    cs:__imp_GetLastError
0x18004309a  nop     dword ptr [rax+rax+00h]
0x18004309f  mov     ecx, eax; unsigned int
0x1800430a1  xor     edx, edx; Format
0x1800430a3  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x1800430a8  jmp     loc_180042FC3
```
