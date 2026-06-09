# SxsOleAut32MapIIDToProxyStubCLSID

- ea: `0x1800470a0`
- end: `0x1800473be`
- name: `SxsOleAut32MapIIDToProxyStubCLSID`
- size: `798`
- prototype: `__int64 __fastcall(GUID *lpGuidToFind)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001c2c8`
- `0x18002e98c`
- `0x1800470a0`
- `0x18005d2b0`
- `0x180067170`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180047257`
- `ntdll!RtlPopFrame` at `0x180047257`
- `ntdll!_snprintf_s` at `0x1800471e8`
- `ntdll!_snprintf_s` at `0x1800471e8`
- `ntdll!RtlGetFrame` at `0x180047190`
- `ntdll!RtlGetFrame` at `0x180047190`
- `ntdll!RtlPushFrame` at `0x18004710d`
- `ntdll!RtlPushFrame` at `0x18004710d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800471ff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800471ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800471b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800471b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047385`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004720d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800473ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004720d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800473ad`
- `KERNEL32!FindActCtxSectionGuid` at `0x180047309`
- `KERNEL32!FindActCtxSectionGuid` at `0x180047309`

## pseudocode

```c
__int64 __fastcall SxsOleAut32MapIIDToProxyStubCLSID(GUID *lpGuidToFind, GUID *a2)
{
  const char *v4; // rcx
  int Previous; // edi
  const char *v6; // rsi
  const char *FrameName; // r14
  PTEB_ACTIVE_FRAME v8; // rax
  PTEB_ACTIVE_FRAME v9; // rcx
  DWORD LastError; // ebx
  unsigned int v11; // ebx
  PCTEB_ACTIVE_FRAME_CONTEXT Context; // rdx
  signed int v14; // eax
  GUID v15; // xmm0
  DWORD v16; // edi
  DWORD v17; // ecx
  struct tagACTCTX_SECTION_KEYED_DATA ReturnedData; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+B0h] [rbp-50h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v21; // [rsp+D0h] [rbp-30h]
  int v22; // [rsp+D8h] [rbp-28h]
  int *v23; // [rsp+E0h] [rbp-20h]
  char Buffer[512]; // [rsp+F0h] [rbp-10h] BYREF

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071630;
  v19 = -2147418113;
  v23 = &v19;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v21 = 544438355;
  v22 = 549;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  memset(&ReturnedData, 0, sizeof(ReturnedData));
  if ( a2 )
    *a2 = GUID_NULL;
  if ( !lpGuidToFind )
  {
    Previous = 0;
    v6 = byte_18008517D;
    v22 = 556;
    FrameName = byte_18008517D;
    v8 = RtlGetFrame();
    if ( v8 && (v8->Flags & 1) != 0 )
    {
      v9 = v8;
    }
    else
    {
      v9 = 0;
      if ( !v8 )
      {
LABEL_8:
        LastError = GetLastError();
        _snprintf_s(
          Buffer,
          0x200u,
          0x1FFu,
          "%s(%d): Input parameter validation failed in function %s\n   Validation expression: %s\n",
          v6,
          Previous,
          FrameName,
          byte_18008517D);
        Buffer[511] = 0;
        OutputDebugStringA(Buffer);
        SetLastError(LastError);
        *v23 = -2147024809;
        goto LABEL_9;
      }
    }
    Context = v8->Context;
    if ( Context )
    {
      if ( Context->FrameName )
        FrameName = Context->FrameName;
      if ( (Context->Flags & 1) != 0 && *(_QWORD *)&Context[1].Flags )
        v6 = *(const char **)&Context[1].Flags;
    }
    if ( v9 && *(_QWORD *)&v9[1].Flags == 544438355 && LODWORD(v9[1].Previous) )
      Previous = (int)v9[1].Previous;
    goto LABEL_8;
  }
  if ( a2 )
  {
    ReturnedData.cbSize = 112;
    if ( FindActCtxSectionGuid(0, 0, 5u, lpGuidToFind, &ReturnedData) )
    {
      v15 = *(GUID *)((char *)ReturnedData.lpData + 8);
      v19 = 0;
      *a2 = v15;
    }
    else
    {
      v14 = GetLastError();
      if ( v14 == 14007 || v14 == 14000 )
      {
        v19 = 1;
      }
      else
      {
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        v19 = v14;
      }
    }
  }
  else
  {
    v22 = 557;
    FusionpTraceParameterCheck(v4);
    *v23 = -2147024809;
  }
LABEL_9:
  v11 = v19;
  if ( g_FusionEnterExitTracingEnabled )
  {
    v16 = GetLastError();
    v17 = *v23;
    if ( *v23 < 0 )
      FusionpTraceCOMFailure(v17, 0);
    else
      FusionpTraceCallCOMSuccessfulExit(v17, 0);
    SetLastError(v16);
  }
  RtlPopFrame(&Frame);
  return v11;
}

```

## disassembly

```asm
0x1800470a0  push    rbp
0x1800470a2  push    rbx
0x1800470a3  push    rdi
0x1800470a4  lea     rbp, [rsp-210h]
0x1800470ac  sub     rsp, 310h
0x1800470b3  mov     rax, cs:__security_cookie
0x1800470ba  xor     rax, rsp
0x1800470bd  mov     [rbp+220h+var_30], rax
0x1800470c4  lea     rax, qword_180071630
0x1800470cb  mov     [rsp+320h+arg_18], r12
0x1800470d3  mov     [rbp+220h+Frame.Context], rax
0x1800470d7  mov     rdi, rcx
0x1800470da  lea     rax, [rbp+220h+var_270]
0x1800470de  mov     [rbp+220h+var_270], 8000FFFFh
0x1800470e5  xor     r12d, r12d
0x1800470e8  mov     [rbp+220h+var_240], rax
0x1800470ec  lea     rcx, [rbp+220h+Frame]; Frame
0x1800470f0  mov     [rbp+220h+Frame.Flags], 1
0x1800470f7  mov     rbx, rdx
0x1800470fa  mov     [rbp+220h+Frame.Previous], r12
0x1800470fe  mov     [rbp+220h+var_250], 20737853h
0x180047106  mov     [rbp+220h+var_248], 225h
0x18004710d  call    cs:__imp_RtlPushFrame
0x180047114  nop     dword ptr [rax+rax+00h]
0x180047119  cmp     cs:g_FusionEnterExitTracingEnabled, r12b
0x180047120  jnz     loc_1800472DB
0x180047126  xorps   xmm0, xmm0
0x180047129  movups  xmmword ptr [rsp+320h+var_2E0.cbSize], xmm0
0x18004712e  movups  xmmword ptr [rsp+320h+var_2E0.ulLength], xmm0
0x180047133  movups  xmmword ptr [rsp+320h+var_2E0.ulSectionGlobalDataLength], xmm0
0x180047138  movups  xmmword ptr [rsp+320h+var_2E0.ulSectionTotalLength], xmm0
0x18004713d  movups  xmmword ptr [rbp+220h+var_2E0.ulAssemblyRosterIndex], xmm0
0x180047141  movups  xmmword ptr [rbp+220h+var_2E0.AssemblyMetadata.lpSectionBase], xmm0
0x180047145  movups  xmmword ptr [rbp+220h+var_2E0.AssemblyMetadata.lpSectionGlobalDataBase], xmm0
0x180047149  test    rbx, rbx
0x18004714c  jz      short loc_180047158
0x18004714e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180047155  movups  xmmword ptr [rbx], xmm0
0x180047158  test    rdi, rdi
0x18004715b  jnz     loc_1800472E5
0x180047161  mov     [rsp+320h+arg_10], rsi
0x180047169  mov     edi, r12d
0x18004716c  mov     [rsp+320h+var_18], r14
0x180047174  mov     [rsp+320h+var_20], r15
0x18004717c  lea     r15, byte_18008517D
0x180047183  mov     rsi, r15
0x180047186  mov     [rbp+220h+var_248], 22Ch
0x18004718d  mov     r14, r15
0x180047190  call    cs:__imp_RtlGetFrame
0x180047197  nop     dword ptr [rax+rax+00h]
0x18004719c  test    rax, rax
0x18004719f  jnz     loc_180047280
0x1800471a5  mov     rcx, r12
0x1800471a8  test    rax, rax
0x1800471ab  jnz     loc_18004728C
0x1800471b1  call    cs:__imp_GetLastError
0x1800471b8  nop     dword ptr [rax+rax+00h]
0x1800471bd  mov     [rsp+320h+var_2E8], r15
0x1800471c2  lea     r9, aSDInputParamet; "%s(%d): Input parameter validation fail"...
0x1800471c9  mov     [rsp+320h+var_2F0], r14
0x1800471ce  lea     rcx, [rbp+220h+Buffer]; Buffer
0x1800471d2  mov     [rsp+320h+var_2F8], edi
0x1800471d6  mov     edx, 200h; BufferCount
0x1800471db  mov     r8d, 1FFh; MaxCount
0x1800471e1  mov     [rsp+320h+ReturnedData], rsi
0x1800471e6  mov     ebx, eax
0x1800471e8  call    cs:__imp__snprintf_s
0x1800471ef  nop     dword ptr [rax+rax+00h]
0x1800471f4  lea     rcx, [rbp+220h+Buffer]; lpOutputString
0x1800471f8  mov     [rbp+220h+var_31], r12b
0x1800471ff  call    cs:__imp_OutputDebugStringA
0x180047206  nop     dword ptr [rax+rax+00h]
0x18004720b  mov     ecx, ebx; dwErrCode
0x18004720d  call    cs:__imp_SetLastError
0x180047214  nop     dword ptr [rax+rax+00h]
0x180047219  mov     rax, [rbp+220h+var_240]
0x18004721d  mov     r15, [rsp+320h+var_20]
0x180047225  mov     r14, [rsp+320h+var_18]
0x18004722d  mov     rsi, [rsp+320h+arg_10]
0x180047235  mov     dword ptr [rax], 80070057h
0x18004723b  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180047242  mov     ebx, [rbp+220h+var_270]
0x180047245  mov     r12, [rsp+320h+arg_18]
0x18004724d  jnz     loc_180047385
0x180047253  lea     rcx, [rbp+220h+Frame]; Frame
0x180047257  call    cs:__imp_RtlPopFrame
0x18004725e  nop     dword ptr [rax+rax+00h]
0x180047263  mov     eax, ebx
0x180047265  mov     rcx, [rbp+220h+var_30]
0x18004726c  xor     rcx, rsp; StackCookie
0x18004726f  call    __security_check_cookie
0x180047274  add     rsp, 310h
0x18004727b  pop     rdi
0x18004727c  pop     rbx
0x18004727d  pop     rbp
0x18004727e  retn
0x180047280  test    byte ptr [rax], 1
0x180047283  jz      loc_1800471A5
0x180047289  mov     rcx, rax
0x18004728c  mov     rdx, [rax+10h]
0x180047290  test    rdx, rdx
0x180047293  jz      short loc_1800472B2
0x180047295  mov     rax, [rdx+8]
0x180047299  test    rax, rax
0x18004729c  jz      short loc_1800472A1
0x18004729e  mov     r14, rax
0x1800472a1  test    byte ptr [rdx], 1
0x1800472a4  jz      short loc_1800472B2
0x1800472a6  mov     rax, [rdx+10h]
0x1800472aa  test    rax, rax
0x1800472ad  jz      short loc_1800472B2
0x1800472af  mov     rsi, rax
0x1800472b2  test    rcx, rcx
0x1800472b5  jz      loc_1800471B1
0x1800472bb  cmp     qword ptr [rcx+18h], 20737853h
0x1800472c3  jnz     loc_1800471B1
0x1800472c9  mov     eax, [rcx+20h]
0x1800472cc  test    eax, eax
0x1800472ce  jz      loc_1800471B1
0x1800472d4  mov     edi, eax
0x1800472d6  jmp     loc_1800471B1
0x1800472db  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x1800472e0  jmp     loc_180047126
0x1800472e5  test    rbx, rbx
0x1800472e8  jz      short loc_180047361
0x1800472ea  lea     rax, [rsp+320h+var_2E0]
0x1800472ef  mov     [rsp+320h+var_2E0.cbSize], 70h ; 'p'
0x1800472f7  mov     r9, rdi; lpGuidToFind
0x1800472fa  mov     [rsp+320h+ReturnedData], rax; ReturnedData
0x1800472ff  xor     edx, edx; lpExtensionGuid
0x180047301  mov     r8d, 5; ulSectionId
0x180047307  xor     ecx, ecx; dwFlags
0x180047309  call    cs:__imp_FindActCtxSectionGuid
0x180047310  nop     dword ptr [rax+rax+00h]
0x180047315  test    eax, eax
0x180047317  jnz     short loc_180047338
0x180047319  call    cs:__imp_GetLastError
0x180047320  nop     dword ptr [rax+rax+00h]
0x180047325  cmp     eax, 36B7h
0x18004732a  jnz     short loc_18004737C
0x18004732c  mov     [rbp+220h+var_270], 1
0x180047333  jmp     loc_18004723B
0x180047338  mov     rax, [rsp+320h+var_2E0.lpData]
0x18004733d  movups  xmm0, xmmword ptr [rax+8]
0x180047341  mov     [rbp+220h+var_270], r12d
0x180047345  movups  xmmword ptr [rbx], xmm0
0x180047348  jmp     loc_18004723B
0x18004734d  test    eax, eax
0x18004734f  jle     short loc_180047359
0x180047351  movzx   eax, ax
0x180047354  or      eax, 80070000h
0x180047359  mov     [rbp+220h+var_270], eax
0x18004735c  jmp     loc_18004723B
0x180047361  mov     [rbp+220h+var_248], 22Dh
0x180047368  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18004736d  mov     rax, [rbp+220h+var_240]
0x180047371  mov     dword ptr [rax], 80070057h
0x180047377  jmp     loc_18004723B
0x18004737c  cmp     eax, 36B0h
0x180047381  jz      short loc_18004732C
0x180047383  jmp     short loc_18004734D
0x180047385  call    cs:__imp_GetLastError
0x18004738c  nop     dword ptr [rax+rax+00h]
0x180047391  mov     rcx, [rbp+220h+var_240]
0x180047395  xor     edx, edx; char *
0x180047397  mov     edi, eax
0x180047399  mov     ecx, [rcx]; int
0x18004739b  test    ecx, ecx
0x18004739d  js      short loc_1800473A6
0x18004739f  call    ?FusionpTraceCallCOMSuccessfulExit@@YAXJPEBDZZ; FusionpTraceCallCOMSuccessfulExit(long,char const *,...)
0x1800473a4  jmp     short loc_1800473AB
0x1800473a6  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x1800473ab  mov     ecx, edi; dwErrCode
0x1800473ad  call    cs:__imp_SetLastError
0x1800473b4  nop     dword ptr [rax+rax+00h]
0x1800473b9  jmp     loc_180047253
```
