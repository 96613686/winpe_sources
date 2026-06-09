# SxspRemoveAssemblyIdentityAttribute(ulong,_ASSEMBLY_IDENTITY *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *)

- ea: `0x18004c2c0`
- end: `0x18004c6f2`
- name: `?SxspRemoveAssemblyIdentityAttribute@@YAHKPEAU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@@Z`
- size: `1074`
- prototype: `int(unsigned int, struct _ASSEMBLY_IDENTITY *, const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18000f170`
- `0x18004c178`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001bcd0`
- `0x18004c2c0`
- `0x18004c700`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x180069b04`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18004c533`
- `ntdll!RtlPopFrame` at `0x18004c572`
- `ntdll!RtlPopFrame` at `0x18004c675`
- `ntdll!RtlPopFrame` at `0x18004c69f`
- `ntdll!RtlPopFrame` at `0x18004c533`
- `ntdll!RtlPopFrame` at `0x18004c572`
- `ntdll!RtlPopFrame` at `0x18004c675`
- `ntdll!RtlPopFrame` at `0x18004c69f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c6d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c6d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c374`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c3d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c424`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c4e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c5d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c605`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c374`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c3d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c424`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c4e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c5d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c605`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c4b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c4b1`

## pseudocode

```c
__int64 __fastcall SxspRemoveAssemblyIdentityAttribute(
        __int64 a1,
        struct _ASSEMBLY_IDENTITY *a2,
        const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *a3)
{
  const struct _ASSEMBLY_IDENTITY_NAMESPACE *v3; // r13
  const char *v6; // rcx
  unsigned int v7; // ebx
  unsigned int v8; // ecx
  __int64 v9; // rcx
  __int64 v10; // rsi
  unsigned int v11; // r14d
  __int64 v12; // r15
  __int64 v13; // r12
  __int64 v14; // rax
  __int64 v15; // r8
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  __int64 v19; // rax
  _QWORD *v20; // rdx
  int v21; // ecx
  DWORD v22; // ecx
  DWORD LastError; // eax
  DWORD v24; // eax
  unsigned int v25; // [rsp+38h] [rbp-59h] BYREF
  unsigned int v26; // [rsp+3Ch] [rbp-55h] BYREF
  int v27; // [rsp+40h] [rbp-51h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+48h] [rbp-49h] BYREF
  __int64 v29; // [rsp+60h] [rbp-31h]
  __int64 v30; // [rsp+68h] [rbp-29h]
  unsigned int *v31; // [rsp+70h] [rbp-21h]
  __int64 v32; // [rsp+78h] [rbp-19h]
  struct _TEB_ACTIVE_FRAME v33; // [rsp+80h] [rbp-11h] BYREF
  __int64 v34; // [rsp+98h] [rbp+7h]
  int v35; // [rsp+A0h] [rbp+Fh]
  int *v36; // [rsp+A8h] [rbp+17h]

  v33.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071C50;
  v3 = 0;
  v36 = &v27;
  v27 = 0;
  v33.Flags = 1;
  v33.Previous = 0;
  v34 = 544438355;
  v35 = 93;
  CFrame::BaseEnter((CFrame *)&v33);
  *(&Frame.Flags + 1) = 0;
  v29 = 0;
  v32 = 0;
  v25 = 0;
  v26 = 0;
  if ( !a2 )
  {
    v35 = 100;
    goto LABEL_28;
  }
  if ( !a3 )
  {
    v35 = 101;
LABEL_28:
    FusionpTraceParameterCheck(v6);
    v22 = 87;
LABEL_29:
    SetLastError(v22);
    *v36 = 0;
    goto LABEL_23;
  }
  v30 = *(_QWORD *)a3;
  Frame.Previous = (struct _TEB_ACTIVE_FRAME *)*((_QWORD *)a3 + 1);
  v31 = (unsigned int *)*((_QWORD *)a3 + 2);
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)*((_QWORD *)a3 + 3);
  Frame.Flags = 0;
  SetLastError(0);
  if ( !(unsigned int)SxsFindAssemblyIdentityAttribute(11, a2, &Frame, &v25, &v26) )
  {
    *v36 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007D0C0);
    goto LABEL_23;
  }
  v7 = v26;
  if ( v26 > 1 )
  {
    v22 = 1359;
    goto LABEL_29;
  }
  if ( !v26 )
  {
LABEL_22:
    v27 = 1;
    goto LABEL_23;
  }
  SetLastError(0);
  v26 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071C90;
  Frame.Flags = 1;
  v31 = &v26;
  Frame.Previous = 0;
  v29 = 544438355;
  LODWORD(v30) = 1905;
  CFrame::BaseEnter((CFrame *)&Frame);
  SetLastError(0);
  if ( (unsigned int)SxspValidateAssemblyIdentity(v8, a2) )
  {
    LODWORD(v10) = v25;
    v11 = *((_DWORD *)a2 + 4);
    if ( v25 >= v11 || v7 > v11 || (v12 = v7 + v25, (unsigned int)v12 > v11) )
    {
      SetLastError(0x57u);
    }
    else
    {
      v13 = *((_QWORD *)a2 + 5);
      if ( v25 < (unsigned int)v12 )
      {
        do
        {
          v14 = (unsigned int)v10;
          v10 = (unsigned int)(v10 + 1);
          v15 = *(_QWORD *)(v13 + 8 * v14);
          if ( (unsigned int)v10 < v11 )
          {
            v9 = *(_QWORD *)(v13 + 8 * v10);
            if ( *(_QWORD *)(v9 + 56) != *(_QWORD *)(v15 + 56) )
              v3 = *(const struct _ASSEMBLY_IDENTITY_NAMESPACE **)(v15 + 56);
          }
          *(_QWORD *)(v13 + 8 * v14) = 0;
          if ( v15 && _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 72), 0xFFFFFFFF) == 1 )
            HeapFree(g_hHeap, 0, (LPVOID)v15);
          if ( v3 )
            SxspCleanUpAssemblyIdentityNamespaceIfNotReferenced(v9, a2, v3);
          v3 = 0;
        }
        while ( (unsigned int)v10 < (unsigned int)v12 );
      }
      for ( ; (unsigned int)v12 < v11; *v20 = 0 )
      {
        v19 = *(_QWORD *)(v13 + 8 * v12);
        v20 = (_QWORD *)(v13 + 8 * v12);
        v21 = v12;
        v12 = (unsigned int)(v12 + 1);
        *(_QWORD *)(v13 + 8LL * (v21 - v7)) = v19;
      }
      *((_DWORD *)a2 + 4) -= v7;
      *((_DWORD *)a2 + 8) = 1;
      SetLastError(0);
      *v31 = 1;
    }
  }
  else
  {
    *v31 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007CE60);
  }
  v16 = *v31;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v16 )
    {
      FusionpTraceCallSuccessfulExit(0);
      RtlPopFrame(&Frame);
      goto LABEL_22;
    }
    LastError = GetLastError();
    FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    RtlPopFrame(&Frame);
  }
  else
  {
    RtlPopFrame(&Frame);
    if ( v16 )
      goto LABEL_22;
  }
  *v36 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007D080);
LABEL_23:
  v17 = v27;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v36 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v24 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v24, 0);
    }
  }
  RtlPopFrame(&v33);
  return v17;
}

```

## disassembly

```asm
0x18004c2c0  mov     r11, rsp
0x18004c2c3  push    rbp
0x18004c2c4  push    rbx
0x18004c2c5  lea     rbp, [r11-5Fh]
0x18004c2c9  sub     rsp, 0D8h
0x18004c2d0  mov     rax, cs:__security_cookie
0x18004c2d7  xor     rax, rsp
0x18004c2da  mov     [rbp+57h+var_38], rax
0x18004c2de  mov     [r11-18h], rdi
0x18004c2e2  lea     rax, qword_180071C50
0x18004c2e9  mov     [rbp+57h+var_68.Context], rax
0x18004c2ed  lea     rcx, [rbp+57h+var_68]; this
0x18004c2f1  mov     [r11-28h], r13
0x18004c2f5  lea     rax, [rbp+57h+var_A8]
0x18004c2f9  xor     r13d, r13d
0x18004c2fc  mov     [rbp+57h+var_40], rax
0x18004c300  mov     rbx, r8
0x18004c303  mov     [rbp+57h+var_A8], r13d
0x18004c307  mov     rdi, rdx
0x18004c30a  mov     [rbp+57h+var_68.Flags], 1
0x18004c311  mov     [rbp+57h+var_68.Previous], r13
0x18004c315  mov     [rbp+57h+var_50], 20737853h
0x18004c31d  mov     [rbp+57h+var_48], 5Dh ; ']'
0x18004c324  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18004c329  mov     dword ptr [rbp+57h+Frame+4], r13d
0x18004c32d  mov     [rbp+57h+var_88], r13
0x18004c331  mov     [rbp+57h+var_70], r13
0x18004c335  mov     [rbp+57h+var_B0], r13d
0x18004c339  mov     [rbp+57h+var_AC], r13d
0x18004c33d  test    rdi, rdi
0x18004c340  jz      loc_18004C616
0x18004c346  test    rbx, rbx
0x18004c349  jz      loc_18004C5C2
0x18004c34f  mov     rax, [rbx]
0x18004c352  xor     ecx, ecx; dwErrCode
0x18004c354  mov     [rbp+57h+var_80], rax
0x18004c358  mov     rax, [rbx+8]
0x18004c35c  mov     [rbp+57h+Frame.Previous], rax
0x18004c360  mov     rax, [rbx+10h]
0x18004c364  mov     [rbp+57h+var_78], rax
0x18004c368  mov     rax, [rbx+18h]
0x18004c36c  mov     [rbp+57h+Frame.Context], rax
0x18004c370  mov     [rbp+57h+Frame.Flags], r13d
0x18004c374  call    cs:__imp_SetLastError
0x18004c37b  nop     dword ptr [rax+rax+00h]
0x18004c380  lea     rax, [rbp+57h+var_AC]
0x18004c384  mov     rdx, rdi
0x18004c387  lea     r9, [rbp+57h+var_B0]
0x18004c38b  mov     [rsp+20h], rax
0x18004c390  lea     r8, [rbp+57h+Frame]
0x18004c394  mov     ecx, 0Bh
0x18004c399  call    SxsFindAssemblyIdentityAttribute
0x18004c39e  test    eax, eax
0x18004c3a0  jz      loc_18004C61F
0x18004c3a6  mov     ebx, [rbp+57h+var_AC]
0x18004c3a9  cmp     ebx, 1
0x18004c3ac  ja      loc_18004C637
0x18004c3b2  test    ebx, ebx
0x18004c3b4  jz      loc_18004C547
0x18004c3ba  mov     [rsp+0E0h+arg_0], rsi
0x18004c3c2  xor     ecx, ecx; dwErrCode
0x18004c3c4  mov     [rsp+0E0h+var_28], r14
0x18004c3cc  mov     [rsp+0E0h+var_30], r15
0x18004c3d4  call    cs:__imp_SetLastError
0x18004c3db  nop     dword ptr [rax+rax+00h]
0x18004c3e0  lea     rax, qword_180071C90
0x18004c3e7  mov     [rbp+57h+var_AC], r13d
0x18004c3eb  mov     [rbp+57h+Frame.Context], rax
0x18004c3ef  lea     rcx, [rbp+57h+Frame]; this
0x18004c3f3  lea     rax, [rbp+57h+var_AC]
0x18004c3f7  mov     [rbp+57h+Frame.Flags], 1
0x18004c3fe  mov     [rbp+57h+var_78], rax
0x18004c402  mov     [rbp+57h+Frame.Previous], r13
0x18004c406  mov     [rbp+57h+var_88], 20737853h
0x18004c40e  mov     dword ptr [rbp+57h+var_80], 771h
0x18004c415  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18004c41a  test    ebx, ebx
0x18004c41c  jz      loc_18004C600
0x18004c422  xor     ecx, ecx; dwErrCode
0x18004c424  call    cs:__imp_SetLastError
0x18004c42b  nop     dword ptr [rax+rax+00h]
0x18004c430  mov     rdx, rdi; struct _ASSEMBLY_IDENTITY *
0x18004c433  call    ?SxspValidateAssemblyIdentity@@YAHKPEBU_ASSEMBLY_IDENTITY@@@Z; SxspValidateAssemblyIdentity(ulong,_ASSEMBLY_IDENTITY const *)
0x18004c438  test    eax, eax
0x18004c43a  jz      loc_18004C63E
0x18004c440  mov     esi, [rbp+57h+var_B0]
0x18004c443  mov     r14d, [rdi+10h]
0x18004c447  cmp     esi, r14d
0x18004c44a  jnb     loc_18004C600
0x18004c450  cmp     ebx, r14d
0x18004c453  ja      loc_18004C600
0x18004c459  lea     r15d, [rbx+rsi]
0x18004c45d  cmp     r15d, r14d
0x18004c460  ja      loc_18004C600
0x18004c466  mov     [rsp+0E0h+var_18], r12
0x18004c46e  mov     r12, [rdi+28h]
0x18004c472  cmp     esi, r15d
0x18004c475  jnb     short loc_18004C4D1
0x18004c477  mov     eax, esi
0x18004c479  inc     esi
0x18004c47b  mov     r8, [r12+rax*8]; lpMem
0x18004c47f  lea     r9, [r12+rax*8]
0x18004c483  cmp     esi, r14d
0x18004c486  jb      loc_18004C5EB
0x18004c48c  mov     qword ptr [r9], 0
0x18004c493  test    r8, r8
0x18004c496  jz      short loc_18004C4BD
0x18004c498  mov     eax, 0FFFFFFFFh
0x18004c49d  lock xadd [r8+48h], eax
0x18004c4a3  cmp     eax, 1
0x18004c4a6  jnz     short loc_18004C4BD
0x18004c4a8  mov     rcx, cs:g_hHeap; hHeap
0x18004c4af  xor     edx, edx; dwFlags
0x18004c4b1  call    cs:__imp_HeapFree
0x18004c4b8  nop     dword ptr [rax+rax+00h]
0x18004c4bd  test    r13, r13
0x18004c4c0  jnz     loc_18004C656
0x18004c4c6  mov     r13d, 0
0x18004c4cc  cmp     esi, r15d
0x18004c4cf  jb      short loc_18004C477
0x18004c4d1  cmp     r15d, r14d
0x18004c4d4  jb      loc_18004C5A0
0x18004c4da  sub     [rdi+10h], ebx
0x18004c4dd  xor     ecx, ecx; dwErrCode
0x18004c4df  mov     dword ptr [rdi+20h], 1
0x18004c4e6  call    cs:__imp_SetLastError
0x18004c4ed  nop     dword ptr [rax+rax+00h]
0x18004c4f2  mov     rax, [rbp+57h+var_78]
0x18004c4f6  mov     r12, [rsp+0E0h+var_18]
0x18004c4fe  mov     dword ptr [rax], 1
0x18004c504  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18004c50b  mov     rax, [rbp+57h+var_78]
0x18004c50f  mov     r15, [rsp+0E0h+var_30]
0x18004c517  mov     r14, [rsp+0E0h+var_28]
0x18004c51f  mov     rsi, [rsp+0E0h+arg_0]
0x18004c527  mov     ebx, [rax]
0x18004c529  jnz     loc_18004C666
0x18004c52f  lea     rcx, [rbp+57h+Frame]; Frame
0x18004c533  call    cs:__imp_RtlPopFrame
0x18004c53a  nop     dword ptr [rax+rax+00h]
0x18004c53f  test    ebx, ebx
0x18004c541  jz      loc_18004C6AB
0x18004c547  mov     [rbp+57h+var_A8], 1
0x18004c54e  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18004c555  mov     ebx, [rbp+57h+var_A8]
0x18004c558  mov     r13, [rsp+0E0h+var_20]
0x18004c560  mov     rdi, [rsp+0D0h]
0x18004c568  jnz     loc_18004C6C3
0x18004c56e  lea     rcx, [rbp+57h+var_68]; Frame
0x18004c572  call    cs:__imp_RtlPopFrame
0x18004c579  nop     dword ptr [rax+rax+00h]
0x18004c57e  mov     eax, ebx
0x18004c580  mov     rcx, [rbp+57h+var_38]
0x18004c584  xor     rcx, rsp; StackCookie
0x18004c587  call    __security_check_cookie
0x18004c58c  add     rsp, 0D8h
0x18004c593  pop     rbx
0x18004c594  pop     rbp
0x18004c595  retn
0x18004c5a0  mov     rax, [r12+r15*8]
0x18004c5a4  lea     rdx, [r12+r15*8]
0x18004c5a8  mov     ecx, r15d
0x18004c5ab  inc     r15d
0x18004c5ae  sub     ecx, ebx
0x18004c5b0  mov     [r12+rcx*8], rax
0x18004c5b4  mov     [rdx], r13
0x18004c5b7  cmp     r15d, r14d
0x18004c5ba  jnb     loc_18004C4DA
0x18004c5c0  jmp     short loc_18004C5A0
0x18004c5c2  mov     [rbp+57h+var_48], 65h ; 'e'
0x18004c5c9  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18004c5ce  mov     ecx, 57h ; 'W'; dwErrCode
0x18004c5d3  call    cs:__imp_SetLastError
0x18004c5da  nop     dword ptr [rax+rax+00h]
0x18004c5df  mov     rax, [rbp+57h+var_40]
0x18004c5e3  mov     [rax], r13d
0x18004c5e6  jmp     loc_18004C54E
0x18004c5eb  mov     rdx, [r8+38h]
0x18004c5ef  mov     rcx, [r12+rsi*8]
0x18004c5f3  cmp     [rcx+38h], rdx
0x18004c5f7  cmovnz  r13, rdx
0x18004c5fb  jmp     loc_18004C48C
0x18004c600  mov     ecx, 57h ; 'W'; dwErrCode
0x18004c605  call    cs:__imp_SetLastError
0x18004c60c  nop     dword ptr [rax+rax+00h]
0x18004c611  jmp     loc_18004C504
0x18004c616  mov     [rbp+57h+var_48], 64h ; 'd'
0x18004c61d  jmp     short loc_18004C5C9
0x18004c61f  mov     rax, [rbp+57h+var_40]
0x18004c623  lea     rcx, off_18007D0C0; struct _CALL_SITE_INFO *
0x18004c62a  mov     [rax], r13d
0x18004c62d  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004c632  jmp     loc_18004C54E
0x18004c637  mov     ecx, 54Fh
0x18004c63c  jmp     short loc_18004C5D3
0x18004c63e  mov     rax, [rbp+57h+var_78]
0x18004c642  lea     rcx, off_18007CE60; struct _CALL_SITE_INFO *
0x18004c649  mov     [rax], r13d
0x18004c64c  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004c651  jmp     loc_18004C504
0x18004c656  mov     r8, r13; struct _ASSEMBLY_IDENTITY_NAMESPACE *
0x18004c659  mov     rdx, rdi; struct _ASSEMBLY_IDENTITY *
0x18004c65c  call    ?SxspCleanUpAssemblyIdentityNamespaceIfNotReferenced@@YAXKPEAU_ASSEMBLY_IDENTITY@@PEBU_ASSEMBLY_IDENTITY_NAMESPACE@@@Z; SxspCleanUpAssemblyIdentityNamespaceIfNotReferenced(ulong,_ASSEMBLY_IDENTITY *,_ASSEMBLY_IDENTITY_NAMESPACE const *)
0x18004c661  jmp     loc_18004C4C6
0x18004c666  test    ebx, ebx
0x18004c668  jz      short loc_18004C686
0x18004c66a  xor     ecx, ecx; char *
0x18004c66c  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18004c671  lea     rcx, [rbp+57h+Frame]; Frame
0x18004c675  call    cs:__imp_RtlPopFrame
0x18004c67c  nop     dword ptr [rax+rax+00h]
0x18004c681  jmp     loc_18004C547
0x18004c686  call    cs:__imp_GetLastError
0x18004c68d  nop     dword ptr [rax+rax+00h]
0x18004c692  mov     ecx, eax; unsigned int
0x18004c694  xor     edx, edx; Format
0x18004c696  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18004c69b  lea     rcx, [rbp+57h+Frame]; Frame
0x18004c69f  call    cs:__imp_RtlPopFrame
0x18004c6a6  nop     dword ptr [rax+rax+00h]
0x18004c6ab  mov     rax, [rbp+57h+var_40]
0x18004c6af  lea     rcx, off_18007D080; struct _CALL_SITE_INFO *
0x18004c6b6  mov     [rax], r13d
0x18004c6b9  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004c6be  jmp     loc_18004C54E
0x18004c6c3  mov     rax, [rbp+57h+var_40]
0x18004c6c7  cmp     dword ptr [rax], 0
0x18004c6ca  jz      short loc_18004C6D8
0x18004c6cc  xor     ecx, ecx; char *
0x18004c6ce  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18004c6d3  jmp     loc_18004C56E
0x18004c6d8  call    cs:__imp_GetLastError
0x18004c6df  nop     dword ptr [rax+rax+00h]
0x18004c6e4  mov     ecx, eax; unsigned int
0x18004c6e6  xor     edx, edx; Format
0x18004c6e8  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18004c6ed  jmp     loc_18004C56E
```
