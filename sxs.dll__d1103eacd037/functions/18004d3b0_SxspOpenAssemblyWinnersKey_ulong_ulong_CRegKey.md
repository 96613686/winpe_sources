# SxspOpenAssemblyWinnersKey(ulong,ulong,CRegKey &)

- ea: `0x18004d3b0`
- end: `0x18004d53d`
- name: `?SxspOpenAssemblyWinnersKey@@YAHKKAEAVCRegKey@@@Z`
- size: `397`
- prototype: `int(unsigned int, unsigned int, struct CRegKey *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026a60`

## callees

- `0x18000a804`
- `0x18001c2c8`
- `0x18004d3b0`
- `0x18004d550`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18004d499`
- `ntdll!RtlPopFrame` at `0x18004d499`
- `ntdll!RtlPushFrame` at `0x18004d40a`
- `ntdll!RtlPushFrame` at `0x18004d40a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d523`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d46d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d4f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d46d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d4f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d45b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d45b`

## string_xrefs

- `0x18004d448`: `Software\Microsoft\Windows\CurrentVersion\SideBySide\Winners`

## pseudocode

```c
__int64 __fastcall SxspOpenAssemblyWinnersKey(__int64 a1, __int64 a2, HKEY *a3)
{
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  int v7; // edx
  DWORD LastError; // eax
  _DWORD v9[2]; // [rsp+30h] [rbp-58h]
  int v10; // [rsp+38h] [rbp-50h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+40h] [rbp-48h] BYREF
  __int64 v12; // [rsp+58h] [rbp-30h]
  int v13; // [rsp+60h] [rbp-28h]
  unsigned int *v14; // [rsp+68h] [rbp-20h]

  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D360;
  v12 = 544438355;
  Frame.Previous = 0;
  v13 = 975;
  v14 = (unsigned int *)&v10;
  v10 = 0;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( *a3 )
  {
    *a3 = 0;
    COperatorFRegCloseKey::operator()();
  }
  v9[0] = 2;
  v9[1] = 3;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\SideBySide\\Winners",
         0,
         0x20119u,
         a3);
  if ( v4 )
  {
    v7 = 0;
    while ( v9[v7] != v4 )
    {
      if ( (unsigned int)++v7 >= 2 )
      {
        if ( v7 != 2 )
          break;
        SetLastError(v4);
        FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180075D70);
        goto LABEL_7;
      }
    }
  }
  SetLastError(0);
  *v14 = 1;
LABEL_7:
  v5 = *v14;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v5 )
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
  return v5;
}

```

## disassembly

```asm
0x18004d3b0  mov     r11, rsp
0x18004d3b3  mov     [r11+8], rbx
0x18004d3b7  push    rdi
0x18004d3b8  sub     rsp, 80h
0x18004d3bf  mov     rax, cs:__security_cookie
0x18004d3c6  xor     rax, rsp
0x18004d3c9  mov     [rsp+88h+var_18], rax
0x18004d3ce  mov     [rsp+88h+Frame.Flags], 1
0x18004d3d6  lea     rax, qword_18006D360
0x18004d3dd  mov     [r11-38h], rax
0x18004d3e1  lea     rcx, [r11-48h]; Frame
0x18004d3e5  xor     edi, edi
0x18004d3e7  mov     qword ptr [r11-30h], 20737853h
0x18004d3ef  lea     rax, [r11-50h]
0x18004d3f3  mov     [r11-40h], rdi
0x18004d3f7  mov     [rsp+88h+var_28], 3CFh
0x18004d3ff  mov     rbx, r8
0x18004d402  mov     [r11-20h], rax
0x18004d406  mov     [rsp+88h+var_50], edi
0x18004d40a  call    cs:__imp_RtlPushFrame
0x18004d411  nop     dword ptr [rax+rax+00h]
0x18004d416  cmp     cs:g_FusionEnterExitTracingEnabled, dil
0x18004d41d  jnz     loc_18004D4D3
0x18004d423  mov     rdx, [rbx]
0x18004d426  test    rdx, rdx
0x18004d429  jnz     loc_18004D4C6
0x18004d42f  mov     r9d, 20119h; samDesired
0x18004d435  mov     [rsp+88h+var_58], 2
0x18004d43d  xor     r8d, r8d; ulOptions
0x18004d440  mov     [rsp+88h+var_54], 3
0x18004d448  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004d44f  mov     [rsp+88h+phkResult], rbx; phkResult
0x18004d454  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004d45b  call    cs:__imp_RegOpenKeyExW
0x18004d462  nop     dword ptr [rax+rax+00h]
0x18004d467  test    eax, eax
0x18004d469  jnz     short loc_18004D4DD
0x18004d46b  xor     ecx, ecx; dwErrCode
0x18004d46d  call    cs:__imp_SetLastError
0x18004d474  nop     dword ptr [rax+rax+00h]
0x18004d479  mov     rax, [rsp+88h+var_20]
0x18004d47e  mov     dword ptr [rax], 1
0x18004d484  cmp     cs:g_FusionEnterExitTracingEnabled, dil
0x18004d48b  mov     rbx, [rsp+88h+var_20]
0x18004d490  mov     ebx, [rbx]
0x18004d492  jnz     short loc_18004D513
0x18004d494  lea     rcx, [rsp+88h+Frame]; Frame
0x18004d499  call    cs:__imp_RtlPopFrame
0x18004d4a0  nop     dword ptr [rax+rax+00h]
0x18004d4a5  mov     eax, ebx
0x18004d4a7  mov     rcx, [rsp+88h+var_18]
0x18004d4ac  xor     rcx, rsp; StackCookie
0x18004d4af  call    __security_check_cookie
0x18004d4b4  mov     rbx, [rsp+88h+arg_0]
0x18004d4bc  add     rsp, 80h
0x18004d4c3  pop     rdi
0x18004d4c4  retn
0x18004d4c6  mov     [rbx], rdi
0x18004d4c9  call    ??RCOperatorFRegCloseKey@@QEBAHPEAX@Z; COperatorFRegCloseKey::operator()(void *)
0x18004d4ce  jmp     loc_18004D42F
0x18004d4d3  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18004d4d8  jmp     loc_18004D423
0x18004d4dd  mov     edx, edi
0x18004d4df  mov     ecx, edx
0x18004d4e1  cmp     [rsp+rcx*4+88h+var_58], eax
0x18004d4e5  jz      short loc_18004D46B
0x18004d4e7  inc     edx
0x18004d4e9  cmp     edx, 2
0x18004d4ec  jb      short loc_18004D4DF
0x18004d4ee  jnz     loc_18004D46B
0x18004d4f4  mov     ecx, eax; dwErrCode
0x18004d4f6  call    cs:__imp_SetLastError
0x18004d4fd  nop     dword ptr [rax+rax+00h]
0x18004d502  lea     rcx, off_180075D70; struct _CALL_SITE_INFO *
0x18004d509  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18004d50e  jmp     loc_18004D484
0x18004d513  test    ebx, ebx
0x18004d515  jz      short loc_18004D523
0x18004d517  xor     ecx, ecx; char *
0x18004d519  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18004d51e  jmp     loc_18004D494
0x18004d523  call    cs:__imp_GetLastError
0x18004d52a  nop     dword ptr [rax+rax+00h]
0x18004d52f  mov     ecx, eax; unsigned int
0x18004d531  xor     edx, edx; Format
0x18004d533  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18004d538  jmp     loc_18004D494
```
