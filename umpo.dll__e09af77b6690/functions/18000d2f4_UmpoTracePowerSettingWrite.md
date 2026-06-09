# UmpoTracePowerSettingWrite

- ea: `0x18000d2f4`
- end: `0x18000d648`
- name: `UmpoTracePowerSettingWrite`
- size: `852`
- prototype: `RPC_STATUS __fastcall(RPC_BINDING_HANDLE Binding, GUID *, GUID *, GUID *, unsigned int, char, __int64, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000c780`
- `0x180015150`

## callees

- `0x18000b6f4`
- `0x18000bdd4`
- `0x18000bfcc`
- `0x18000c04c`
- `0x18000d2f4`
- `0x18000d6cc`
- `0x18000f3dc`
- `0x180010070`
- `0x1800100b0`
- `0x180010946`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000d3dd`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000d3dd`
- `ntdll!EtwEventWrite` at `0x18000d602`
- `ntdll!EtwEventWrite` at `0x18000d602`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000d3c7`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000d3c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d612`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d612`
- `RPCRT4!I_RpcOpenClientProcess` at `0x18000d35e`
- `RPCRT4!I_RpcOpenClientProcess` at `0x18000d35e`

## pseudocode

```c
RPC_STATUS __fastcall UmpoTracePowerSettingWrite(
        RPC_BINDING_HANDLE Binding,
        GUID *a2,
        GUID *a3,
        GUID *a4,
        unsigned int a5,
        char a6,
        __int64 a7,
        int a8)
{
  RPC_STATUS result; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int64 v14; // rcx
  wchar_t *v15; // rax
  int v16; // r9d
  __int64 v17; // rdi
  __int64 v18; // rcx
  __int64 *v19; // r15
  GUID *v20; // rsi
  GUID *v21; // r12
  int v22; // r10d
  __int64 v23; // r10
  __int64 v24; // r8
  __int64 v25; // r9
  char v26; // al
  char v27; // [rsp+30h] [rbp-D0h] BYREF
  char v28; // [rsp+31h] [rbp-CFh] BYREF
  unsigned int v29; // [rsp+34h] [rbp-CCh] BYREF
  int ProcessId; // [rsp+38h] [rbp-C8h] BYREF
  void *ClientProcess; // [rsp+40h] [rbp-C0h] BYREF
  GUID *v32; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v34[7]; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+98h] [rbp-68h]
  int v36; // [rsp+9Ch] [rbp-64h]
  int *v37; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  int v40; // [rsp+B8h] [rbp-48h]
  int v41; // [rsp+BCh] [rbp-44h]
  GUID *v42; // [rsp+C0h] [rbp-40h]
  __int64 v43; // [rsp+C8h] [rbp-38h]
  GUID *v44; // [rsp+D0h] [rbp-30h]
  __int64 v45; // [rsp+D8h] [rbp-28h]
  GUID *v46; // [rsp+E0h] [rbp-20h]
  __int64 v47; // [rsp+E8h] [rbp-18h]
  struct _EVENT_DATA_DESCRIPTOR v48; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v49; // [rsp+110h] [rbp+10h]
  __int64 v50; // [rsp+118h] [rbp+18h]
  char v51[16]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int *v52; // [rsp+130h] [rbp+30h]
  __int64 v53; // [rsp+138h] [rbp+38h]
  GUID *v54; // [rsp+140h] [rbp+40h]
  __int64 v55; // [rsp+148h] [rbp+48h]
  GUID *v56; // [rsp+150h] [rbp+50h]
  __int64 v57; // [rsp+158h] [rbp+58h]
  GUID *v58; // [rsp+160h] [rbp+60h]
  __int64 v59; // [rsp+168h] [rbp+68h]
  GUID **v60; // [rsp+170h] [rbp+70h]
  __int64 v61; // [rsp+178h] [rbp+78h]
  char *v62; // [rsp+180h] [rbp+80h]
  __int64 v63; // [rsp+188h] [rbp+88h]
  wchar_t Str[264]; // [rsp+190h] [rbp+90h] BYREF

  v32 = a3;
  v27 = 0;
  ProcessId = 0;
  memset_0(v34, 0, 0x90u);
  ClientProcess = 0;
  result = I_RpcOpenClientProcess(Binding, 0x1000u, &ClientProcess);
  if ( !result )
  {
    v29 = 260;
    result = UmpoQueryProcessImageName(ClientProcess, Str);
    if ( result )
    {
      v14 = 2LL * v29;
      if ( v14 >= 0x20A )
        _report_rangecheckfailure(v14, v12, v13, 0);
      Str[v29] = 0;
      ProcessId = GetProcessId(ClientProcess);
      v15 = wcsrchr(Str, 0x5Cu);
      v16 = 0;
      if ( !v15 )
        goto LABEL_31;
      v17 = -1;
      v18 = -1;
      do
        ++v18;
      while ( v15[v18] );
      if ( v18 )
      {
        v19 = (__int64 *)(v15 + 1);
        v20 = &GUID_NULL;
        if ( !a2 || !(unsigned __int8)UmpoIsInBuiltPowerScheme(a2) )
          a2 = &GUID_NULL;
        v21 = &GUID_NULL;
        v22 = 4;
        if ( v32 )
          v21 = v32;
        if ( a4 )
          v20 = a4;
        if ( (unsigned int)dword_180024190 > 5 && tlgKeywordOn() )
        {
          v33 = 0x2000000;
          v49 = &v33;
          v50 = 8;
          tlgCreate1Sz_wchar_t((__int64)v51, v19);
          v52 = &v29;
          v29 = ProcessId;
          v60 = &v32;
          v28 = a6;
          v62 = &v28;
          v53 = v23;
          v54 = a2;
          v55 = 16;
          v56 = v21;
          v57 = 16;
          v58 = v20;
          v59 = 16;
          LODWORD(v32) = a5;
          v61 = v23;
          v63 = 1;
          tlgWriteTransfer_EventWriteTransfer(
            (unsigned int)ProcessId,
            (unsigned __int8 *)&word_18001FA32,
            v24,
            v25,
            0xAu,
            &v48);
          v16 = 0;
          v22 = 4;
        }
        result = a5 - 7;
        if ( (a5 - 7 <= 1 || a5 <= 1) && (a8 == 1 || a8 == v22) )
        {
          if ( a5 == 7 || (v26 = v16, !a5) )
            v26 = 1;
          v27 = v26;
          v34[0] = &a6;
          v34[2] = &v27;
          v34[4] = &ProcessId;
          v34[1] = 1;
          v34[3] = 1;
          v34[5] = 4;
          do
            ++v17;
          while ( *((_WORD *)v19 + v17) != (_WORD)v16 );
          v36 = v16;
          v35 = 2 * v17 + 2;
          v40 = a8;
          v37 = &a8;
          v41 = v16;
          v39 = a7;
          v34[6] = v19;
          v38 = 4;
          v42 = a2;
          v43 = 16;
          v44 = v21;
          v45 = 16;
          v46 = v20;
          v47 = 16;
          result = EtwEventWrite(UmpoProviderHandle, UMPO_EVT_POWER_SETTING_UPDATE, 9, v34);
        }
      }
      else
      {
LABEL_31:
        result = MicrosoftTelemetryAssertTriggeredNoArgs();
      }
    }
    if ( ClientProcess )
      return CloseHandle(ClientProcess);
  }
  return result;
}

```

## disassembly

```asm
0x18000d2f4  push    rbp
0x18000d2f6  push    rbx
0x18000d2f7  push    rsi
0x18000d2f8  push    rdi
0x18000d2f9  push    r12
0x18000d2fb  push    r13
0x18000d2fd  push    r14
0x18000d2ff  push    r15
0x18000d301  lea     rbp, [rsp-2B8h]
0x18000d309  sub     rsp, 3B8h
0x18000d310  mov     rax, cs:__security_cookie
0x18000d317  xor     rax, rsp
0x18000d31a  mov     [rbp+2F0h+var_50], rax
0x18000d321  mov     [rsp+3F0h+var_3A8], r8
0x18000d326  mov     r14, rdx
0x18000d329  mov     rbx, rcx
0x18000d32c  xor     edi, edi
0x18000d32e  xor     edx, edx; Val
0x18000d330  mov     [rsp+3F0h+var_3C0], dil
0x18000d335  mov     r8d, 90h; Size
0x18000d33b  mov     [rsp+3F0h+var_3B8], edi
0x18000d33f  lea     rcx, [rsp+3F0h+var_390]; void *
0x18000d344  mov     r13, r9
0x18000d347  call    memset_0
0x18000d34c  lea     r8, [rsp+3F0h+ClientProcess]; ClientProcess
0x18000d351  mov     [rsp+3F0h+ClientProcess], rdi
0x18000d356  mov     edx, 1000h; DesiredAccess
0x18000d35b  mov     rcx, rbx; Binding
0x18000d35e  call    cs:__imp_I_RpcOpenClientProcess
0x18000d364  test    eax, eax
0x18000d366  jnz     loc_18000D618
0x18000d36c  mov     rcx, [rsp+3F0h+ClientProcess]; ProcessHandle
0x18000d371  lea     r8, [rsp+3F0h+var_3BC]
0x18000d376  mov     ebx, 104h
0x18000d37b  lea     rdx, [rbp+2F0h+Str]; void *
0x18000d382  mov     [rsp+3F0h+var_3BC], ebx
0x18000d386  call    UmpoQueryProcessImageName
0x18000d38b  xor     r9d, r9d
0x18000d38e  test    eax, eax
0x18000d390  jz      loc_18000D608
0x18000d396  cmp     [rsp+3F0h+var_3BC], ebx
0x18000d39a  jbe     short loc_18000D3A4
0x18000d39c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d3a1  xor     r9d, r9d
0x18000d3a4  mov     eax, [rsp+3F0h+var_3BC]
0x18000d3a8  lea     rcx, [rax+rax]
0x18000d3ac  cmp     rcx, 20Ah
0x18000d3b3  jnb     loc_18000D642
0x18000d3b9  mov     [rbp+rcx+2F0h+Str], r9w
0x18000d3c2  mov     rcx, [rsp+3F0h+ClientProcess]; Process
0x18000d3c7  call    cs:__imp_GetProcessId
0x18000d3cd  mov     edx, 5Ch ; '\'; Ch
0x18000d3d2  lea     rcx, [rbp+2F0h+Str]; Str
0x18000d3d9  mov     [rsp+3F0h+var_3B8], eax
0x18000d3dd  call    cs:__imp_wcsrchr
0x18000d3e3  xor     r9d, r9d
0x18000d3e6  test    rax, rax
0x18000d3e9  jz      loc_18000D63B
0x18000d3ef  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000d3f3  mov     rcx, rdi
0x18000d3f6  inc     rcx
0x18000d3f9  cmp     [rax+rcx*2], r9w
0x18000d3fe  jnz     short loc_18000D3F6
0x18000d400  test    rcx, rcx
0x18000d403  jz      loc_18000D63B
0x18000d409  lea     r15, [rax+2]
0x18000d40d  lea     rsi, GUID_NULL
0x18000d414  test    r14, r14
0x18000d417  jz      short loc_18000D425
0x18000d419  mov     rcx, r14
0x18000d41c  call    UmpoIsInBuiltPowerScheme
0x18000d421  test    al, al
0x18000d423  jnz     short loc_18000D428
0x18000d425  mov     r14, rsi
0x18000d428  mov     rax, [rsp+3F0h+var_3A8]
0x18000d42d  mov     r12, rsi
0x18000d430  mov     ebx, [rbp+2F0h+arg_20]
0x18000d436  test    rax, rax
0x18000d439  mov     r10d, 4
0x18000d43f  cmovnz  r12, rax
0x18000d443  mov     eax, cs:dword_180024190
0x18000d449  test    r13, r13
0x18000d44c  cmovnz  rsi, r13
0x18000d450  lea     r13d, [r10-3]
0x18000d454  cmp     eax, 5
0x18000d457  jbe     loc_18000D51B
0x18000d45d  call    _tlgKeywordOn
0x18000d462  test    al, al
0x18000d464  jz      loc_18000D51B
0x18000d46a  lea     rax, [rsp+3F0h+var_3A0]
0x18000d46f  mov     [rsp+3F0h+var_3A0], 2000000h
0x18000d478  mov     rdx, r15
0x18000d47b  mov     [rbp+2F0h+var_2E0], rax
0x18000d47f  lea     rcx, [rbp+2F0h+var_2D0]
0x18000d483  mov     [rbp+2F0h+var_2D8], 8
0x18000d48b  call    _tlgCreate1Sz_wchar_t
0x18000d490  mov     ecx, [rsp+3F0h+var_3B8]; int
0x18000d494  lea     rax, [rsp+3F0h+var_3BC]
0x18000d499  mov     [rbp+2F0h+var_2C0], rax
0x18000d49d  lea     rdx, word_18001FA32; int
0x18000d4a4  lea     rax, [rsp+3F0h+var_3A8]
0x18000d4a9  mov     [rsp+3F0h+var_3BC], ecx
0x18000d4ad  mov     [rbp+2F0h+var_280], rax
0x18000d4b1  mov     al, [rbp+2F0h+arg_28]
0x18000d4b7  mov     [rsp+3F0h+var_3BF], al
0x18000d4bb  lea     rax, [rsp+3F0h+var_3BF]
0x18000d4c0  mov     [rbp+2F0h+var_270], rax
0x18000d4c7  lea     rax, [rbp+2F0h+var_300]
0x18000d4cb  mov     [rsp+3F0h+var_3C8], rax; __int64
0x18000d4d0  mov     [rsp+3F0h+var_3D0], 0Ah; ULONG
0x18000d4d8  mov     [rbp+2F0h+var_2B8], r10
0x18000d4dc  mov     [rbp+2F0h+var_2B0], r14
0x18000d4e0  mov     [rbp+2F0h+var_2A8], 10h
0x18000d4e8  mov     [rbp+2F0h+var_2A0], r12
0x18000d4ec  mov     [rbp+2F0h+var_298], 10h
0x18000d4f4  mov     [rbp+2F0h+var_290], rsi
0x18000d4f8  mov     [rbp+2F0h+var_288], 10h
0x18000d500  mov     dword ptr [rsp+3F0h+var_3A8], ebx
0x18000d504  mov     [rbp+2F0h+var_278], r10
0x18000d508  mov     [rbp+2F0h+var_268], r13
0x18000d50f  call    _tlgWriteTransfer_EventWriteTransfer
0x18000d514  xor     r9d, r9d
0x18000d517  lea     r10d, [r13+3]
0x18000d51b  lea     eax, [rbx-7]
0x18000d51e  cmp     eax, r13d
0x18000d521  jbe     short loc_18000D52C
0x18000d523  cmp     ebx, r13d
0x18000d526  ja      loc_18000D608
0x18000d52c  mov     ecx, [rbp+2F0h+arg_38]
0x18000d532  cmp     ecx, r13d
0x18000d535  jz      short loc_18000D540
0x18000d537  cmp     ecx, r10d
0x18000d53a  jnz     loc_18000D608
0x18000d540  cmp     ebx, 7
0x18000d543  jz      short loc_18000D54C
0x18000d545  mov     al, r9b
0x18000d548  test    ebx, ebx
0x18000d54a  jnz     short loc_18000D54F
0x18000d54c  mov     al, r13b
0x18000d54f  mov     [rsp+3F0h+var_3C0], al
0x18000d553  lea     rax, [rbp+2F0h+arg_28]
0x18000d55a  mov     [rsp+3F0h+var_390], rax
0x18000d55f  lea     rax, [rsp+3F0h+var_3C0]
0x18000d564  mov     [rsp+3F0h+var_380], rax
0x18000d569  lea     rax, [rsp+3F0h+var_3B8]
0x18000d56e  mov     [rbp+2F0h+var_370], rax
0x18000d572  mov     [rsp+3F0h+var_388], r13
0x18000d577  mov     [rsp+3F0h+var_378], r13
0x18000d57c  mov     [rbp+2F0h+var_368], 4
0x18000d584  inc     rdi
0x18000d587  cmp     [r15+rdi*2], r9w
0x18000d58c  jnz     short loc_18000D584
0x18000d58e  lea     eax, ds:2[rdi*2]
0x18000d595  mov     [rbp+2F0h+var_354], r9d
0x18000d599  mov     [rbp+2F0h+var_358], eax
0x18000d59c  lea     rdx, UMPO_EVT_POWER_SETTING_UPDATE
0x18000d5a3  lea     rax, [rbp+2F0h+arg_38]
0x18000d5aa  mov     [rbp+2F0h+var_338], ecx
0x18000d5ad  mov     rcx, cs:UmpoProviderHandle
0x18000d5b4  mov     r8d, 9
0x18000d5ba  mov     [rbp+2F0h+var_350], rax
0x18000d5be  mov     rax, [rbp+2F0h+arg_30]
0x18000d5c5  mov     [rbp+2F0h+var_334], r9d
0x18000d5c9  lea     r9, [rsp+3F0h+var_390]
0x18000d5ce  mov     [rbp+2F0h+var_340], rax
0x18000d5d2  mov     [rbp+2F0h+var_360], r15
0x18000d5d6  mov     [rbp+2F0h+var_348], 4
0x18000d5de  mov     [rbp+2F0h+var_330], r14
0x18000d5e2  mov     [rbp+2F0h+var_328], 10h
0x18000d5ea  mov     [rbp+2F0h+var_320], r12
0x18000d5ee  mov     [rbp+2F0h+var_318], 10h
0x18000d5f6  mov     [rbp+2F0h+var_310], rsi
0x18000d5fa  mov     [rbp+2F0h+var_308], 10h
0x18000d602  call    cs:__imp_EtwEventWrite
0x18000d608  mov     rcx, [rsp+3F0h+ClientProcess]; hObject
0x18000d60d  test    rcx, rcx
0x18000d610  jz      short loc_18000D618
0x18000d612  call    cs:__imp_CloseHandle
0x18000d618  mov     rcx, [rbp+2F0h+var_50]
0x18000d61f  xor     rcx, rsp; StackCookie
0x18000d622  call    __security_check_cookie
0x18000d627  add     rsp, 3B8h
0x18000d62e  pop     r15
0x18000d630  pop     r14
0x18000d632  pop     r13
0x18000d634  pop     r12
0x18000d636  pop     rdi
0x18000d637  pop     rsi
0x18000d638  pop     rbx
0x18000d639  pop     rbp
0x18000d63a  retn
0x18000d63b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d640  jmp     short loc_18000D608
0x18000d642  call    __report_rangecheckfailure
```
