# CFDRShim::StartFDR(void)

- ea: `0x180005488`
- end: `0x180005676`
- name: `?StartFDR@CFDRShim@@QEAAJXZ`
- size: `494`
- prototype: `__int64 __fastcall(CFDRShim *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180004420`

## callees

- `0x180001cc6`
- `0x180001cd4`
- `0x1800040b4`
- `0x180004a70`
- `0x180004e1c`
- `0x180005158`
- `0x180005488`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x180005574`
- `ntdll!DbgPrintEx` at `0x18000560b`
- `ntdll!DbgPrintEx` at `0x180005574`
- `ntdll!DbgPrintEx` at `0x18000560b`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800055f0`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800055f0`

## string_xrefs

- `0x180005563`: `WERDIAG: Failed reading the session settings of updating the process ID. HRESULT: %08X\n`

## pseudocode

```c
__int64 __fastcall CFDRShim::StartFDR(CFDRShim *this)
{
  ULONG64 *RegistrationHandle; // r14
  __int64 v3; // rdx
  _OWORD *v4; // rcx
  CFDRShim *v5; // rax
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm1
  int updated; // eax
  unsigned int v15; // ebx
  const CHAR *v16; // r8
  int v17; // eax
  ULONG v18; // eax
  const wchar_t *v19; // rdx
  CFDRShim *v20; // rcx
  unsigned int v21; // r8d
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[304]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v25; // [rsp+190h] [rbp+90h] BYREF
  void *v26; // [rsp+198h] [rbp+98h] BYREF

  RegistrationHandle = (ULONG64 *)((char *)this + 296);
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  v26 = 0;
  v25 = 0;
  memset_0(v24, 0, 0x120u);
  v3 = 2;
  v4 = v24;
  v5 = this;
  do
  {
    v6 = v4[1];
    *(_OWORD *)v5 = *v4;
    v7 = v4[2];
    *((_OWORD *)v5 + 1) = v6;
    v8 = v4[3];
    *((_OWORD *)v5 + 2) = v7;
    v9 = v4[4];
    *((_OWORD *)v5 + 3) = v8;
    v10 = v4[5];
    *((_OWORD *)v5 + 4) = v9;
    v11 = v4[6];
    *((_OWORD *)v5 + 5) = v10;
    v12 = v4[7];
    v4 += 8;
    *((_OWORD *)v5 + 6) = v11;
    *((_OWORD *)v5 + 7) = v12;
    v5 = (CFDRShim *)((char *)v5 + 128);
    --v3;
  }
  while ( v3 );
  v13 = v4[1];
  *(_OWORD *)v5 = *v4;
  *((_OWORD *)v5 + 1) = v13;
  updated = CFDRShim::ReadAndUpdateSessionSettings((__int64)v4, (__int64)&v26, (__int64)&v25);
  v15 = updated;
  if ( updated >= 0 )
  {
    v17 = CFDRShim::ParseSettings(this, &v26);
    v15 = v17;
    if ( v17 < 0 )
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: Failed parsing settings string. HRESULT: %08X\n", (unsigned int)v17);
      goto LABEL_14;
    }
    TraceGuidReg.Guid = (LPCGUID)&xmmword_18000AE90;
    TraceGuidReg.RegHandle = 0;
    *RegistrationHandle = 0;
    v18 = RegisterTraceGuidsW(ControlCallback, 0, &ControlGuid, 1u, &TraceGuidReg, 0, 0, RegistrationHandle);
    if ( v18 )
      DbgPrintEx(0x96u, 0, "WERDIAG: Provider not registered. RegisterTraceGuids failed with %d\n", v18);
    updated = CFDRShim::EnableFDR(this, v25);
    v15 = updated;
    if ( updated >= 0 )
    {
      CFDRShim::LogMessage(v20, v19, v21);
      v15 = 0;
      goto LABEL_14;
    }
    v16 = "WERDIAG: Failed to enable logging. HRESULT: %08X\n";
  }
  else
  {
    v16 = "WERDIAG: Failed reading the session settings of updating the process ID. HRESULT: %08X\n";
  }
  DbgPrintEx(0x96u, 0, v16, (unsigned int)updated);
LABEL_14:
  if ( v25 )
    operator delete[](v25);
  if ( v26 )
    operator delete[](v26);
  return v15;
}

```

## disassembly

```asm
0x180005488  mov     [rsp-8+arg_10], rbx
0x18000548d  push    rbp
0x18000548e  push    rdi
0x18000548f  push    r14
0x180005491  lea     rbp, [rsp-70h]
0x180005496  sub     rsp, 170h
0x18000549d  lea     r14, [rcx+128h]
0x1800054a4  mov     qword ptr [rcx+120h], 0
0x1800054af  mov     rdi, rcx
0x1800054b2  mov     qword ptr [r14], 0
0x1800054b9  lea     rcx, [rsp+180h+var_130]; void *
0x1800054be  mov     [rbp+80h+arg_8], 0
0x1800054c9  xor     edx, edx; Val
0x1800054cb  mov     [rbp+80h+arg_0], 0
0x1800054d6  mov     r8d, 120h; Size
0x1800054dc  call    memset_0
0x1800054e1  mov     edx, 2
0x1800054e6  lea     rcx, [rsp+180h+var_130]
0x1800054eb  mov     rax, rdi
0x1800054ee  lea     r8d, [rdx+7Eh]
0x1800054f2  movups  xmm0, xmmword ptr [rcx]
0x1800054f5  movups  xmm1, xmmword ptr [rcx+10h]
0x1800054f9  movups  xmmword ptr [rax], xmm0
0x1800054fc  movups  xmm0, xmmword ptr [rcx+20h]
0x180005500  movups  xmmword ptr [rax+10h], xmm1
0x180005504  movups  xmm1, xmmword ptr [rcx+30h]
0x180005508  movups  xmmword ptr [rax+20h], xmm0
0x18000550c  movups  xmm0, xmmword ptr [rcx+40h]
0x180005510  movups  xmmword ptr [rax+30h], xmm1
0x180005514  movups  xmm1, xmmword ptr [rcx+50h]
0x180005518  movups  xmmword ptr [rax+40h], xmm0
0x18000551c  movups  xmm0, xmmword ptr [rcx+60h]
0x180005520  movups  xmmword ptr [rax+50h], xmm1
0x180005524  movups  xmm1, xmmword ptr [rcx+70h]
0x180005528  add     rcx, r8
0x18000552b  movups  xmmword ptr [rax+60h], xmm0
0x18000552f  movups  xmmword ptr [rax+70h], xmm1
0x180005533  add     rax, r8
0x180005536  sub     rdx, 1
0x18000553a  jnz     short loc_1800054F2
0x18000553c  movups  xmm0, xmmword ptr [rcx]
0x18000553f  lea     r8, [rbp+80h+arg_0]
0x180005546  movups  xmm1, xmmword ptr [rcx+10h]
0x18000554a  lea     rdx, [rbp+80h+arg_8]
0x180005551  movups  xmmword ptr [rax], xmm0
0x180005554  movups  xmmword ptr [rax+10h], xmm1
0x180005558  call    ?ReadAndUpdateSessionSettings@CFDRShim@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@0@Z; CFDRShim::ReadAndUpdateSessionSettings(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x18000555d  mov     ebx, eax
0x18000555f  test    eax, eax
0x180005561  jns     short loc_18000557F
0x180005563  lea     r8, aWerdiagFailedR_2; "WERDIAG: Failed reading the session set"...
0x18000556a  xor     edx, edx; Level
0x18000556c  mov     r9d, eax
0x18000556f  mov     ecx, 96h; ComponentId
0x180005574  call    cs:__imp_DbgPrintEx
0x18000557a  jmp     loc_180005639
0x18000557f  lea     rdx, [rbp+80h+arg_8]
0x180005586  mov     rcx, rdi
0x180005589  call    ?ParseSettings@CFDRShim@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z; CFDRShim::ParseSettings(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x18000558e  xor     edx, edx; RequestContext
0x180005590  mov     ebx, eax
0x180005592  test    eax, eax
0x180005594  jns     short loc_18000559F
0x180005596  lea     r8, aWerdiagFailedP; "WERDIAG: Failed parsing settings string"...
0x18000559d  jmp     short loc_18000556C
0x18000559f  mov     [rsp+180h+RegistrationHandle], r14; RegistrationHandle
0x1800055a4  lea     rax, xmmword_18000AE90
0x1800055ab  mov     [rsp+180h+var_140.Guid], rax
0x1800055b0  lea     r8, ControlGuid; ControlGuid
0x1800055b7  lea     rax, [rsp+180h+var_140]
0x1800055bc  mov     [rsp+180h+MofResourceName], 0; MofResourceName
0x1800055c5  mov     [rsp+180h+MofImagePath], 0; MofImagePath
0x1800055ce  lea     rcx, ?ControlCallback@@YAKW4WMIDPREQUESTCODE@@PEAXPEAK1@Z; RequestAddress
0x1800055d5  mov     r9d, 1; GuidCount
0x1800055db  mov     [rsp+180h+TraceGuidReg], rax; TraceGuidReg
0x1800055e0  mov     [rsp+180h+var_140.RegHandle], 0
0x1800055e9  mov     qword ptr [r14], 0
0x1800055f0  call    cs:__imp_RegisterTraceGuidsW
0x1800055f6  test    eax, eax
0x1800055f8  jz      short loc_180005611
0x1800055fa  mov     r9d, eax
0x1800055fd  lea     r8, aWerdiagProvide; "WERDIAG: Provider not registered. Regis"...
0x180005604  xor     edx, edx; Level
0x180005606  mov     ecx, 96h; ComponentId
0x18000560b  call    cs:__imp_DbgPrintEx
0x180005611  mov     rdx, [rbp+80h+arg_0]; wchar_t *
0x180005618  mov     rcx, rdi; this
0x18000561b  call    ?EnableFDR@CFDRShim@@AEAAJPEB_W@Z; CFDRShim::EnableFDR(wchar_t const *)
0x180005620  mov     ebx, eax
0x180005622  test    eax, eax
0x180005624  jns     short loc_180005632
0x180005626  lea     r8, aWerdiagFailedT; "WERDIAG: Failed to enable logging. HRES"...
0x18000562d  jmp     loc_18000556A
0x180005632  call    ?LogMessage@CFDRShim@@AEAAJPEB_WK@Z; CFDRShim::LogMessage(wchar_t const *,ulong)
0x180005637  xor     ebx, ebx
0x180005639  cmp     [rbp+80h+arg_0], 0
0x180005641  jz      short loc_18000564F
0x180005643  mov     rcx, [rbp+80h+arg_0]; void *
0x18000564a  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000564f  mov     rcx, [rbp+80h+arg_8]; void *
0x180005656  test    rcx, rcx
0x180005659  jz      short loc_180005660
0x18000565b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005660  mov     eax, ebx
0x180005662  mov     rbx, [rsp+180h+arg_10]
0x18000566a  add     rsp, 170h
0x180005671  pop     r14
0x180005673  pop     rdi
0x180005674  pop     rbp
0x180005675  retn
```
