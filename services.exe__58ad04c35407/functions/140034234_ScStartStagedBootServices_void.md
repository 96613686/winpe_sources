# ScStartStagedBootServices(void)

- ea: `0x140034234`
- end: `0x14003460e`
- name: `?ScStartStagedBootServices@@YAKXZ`
- size: `986`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140039bd4`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140007130`
- `0x14000bcc4`
- `0x14000c310`
- `0x140011ba0`
- `0x14001761c`
- `0x1400188fc`
- `0x14001c1e0`
- `0x14002193c`
- `0x14002b4a4`
- `0x140034234`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003457e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003457e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400343d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400343d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400343e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400343e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400345d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400345d4`
- `ntdll!NtClose` at `0x1400345be`
- `ntdll!NtClose` at `0x1400345be`
- `ntdll!RtlNtStatusToDosError` at `0x1400345c6`
- `ntdll!RtlNtStatusToDosError` at `0x1400345c6`
- `ntdll!RtlFreeHeap` at `0x1400345ec`
- `ntdll!RtlFreeHeap` at `0x1400345ec`

## string_xrefs

- `0x1400342e7`: `ServicesForStagedBoot`

## pseudocode

```c
__int64 __fastcall ScStartStagedBootServices(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned __int16 *v3; // rsi
  HANDLE EventW; // r12
  unsigned int NamedServiceRecord; // eax
  unsigned int v6; // ebx
  PRPC_ASYNC_STATE v7; // rcx
  int v8; // edx
  const wchar_t *v9; // r9
  unsigned int v10; // eax
  DWORD LastError; // eax
  PRPC_ASYNC_STATE v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int v15; // r13d
  PRPC_ASYNC_STATE v16; // r10
  unsigned int v17; // r14d
  wchar_t *v18; // r15
  int started; // eax
  NTSTATUS v20; // eax
  wchar_t *String2; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *v23; // [rsp+90h] [rbp+48h] BYREF
  unsigned __int16 *v24; // [rsp+98h] [rbp+50h] BYREF
  struct CServiceRecord *v25; // [rsp+A0h] [rbp+58h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp+60h] BYREF

  Handle = 0;
  v25 = 0;
  v24 = 0;
  v3 = 0;
  String2 = 0;
  EventW = 0;
  LODWORD(v23) = 0;
  NamedServiceRecord = ScRegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\\\Setup", a3, 0x20019u, (HKEY *)&Handle);
  v6 = NamedServiceRecord;
  if ( !NamedServiceRecord )
  {
    v10 = ScAllocateAndReadConfigValue((HKEY)Handle, L"ServicesForStagedBoot", &v24, (unsigned int *)&v23);
    v6 = v10;
    if ( v10 )
    {
      if ( v10 == 2 )
      {
        v6 = 0;
      }
      else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
             && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 105, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, v10);
      }
      v3 = v24;
      goto LABEL_56;
    }
    v3 = v24;
    LastError = ScValidateMultiSZ(v24, (unsigned int)v23);
    v6 = LastError;
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_56;
      v13 = 106;
LABEL_18:
      v14 = LastError;
      goto LABEL_19;
    }
    v15 = ScWStrArrayStrCount();
    if ( !v15 )
    {
      v6 = 13;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_56;
      v13 = 107;
      v14 = 13;
LABEL_19:
      WPP_SF_d(v12->StubInfo, v13, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, v14);
      goto LABEL_56;
    }
    EventW = CreateEventW(0, 1, 0, L"Global\\SC_STAGED_BOOT_DONE");
    if ( !EventW )
    {
      LastError = GetLastError();
      v6 = LastError;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_56;
      v13 = 108;
      goto LABEL_18;
    }
    v16 = WPP_GLOBAL_Control;
    v17 = 0;
    v23 = v3;
    while ( 1 )
    {
      do
      {
        if ( !*v23 )
        {
          if ( v16 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v16->UserInfo) & 4) != 0 )
            WPP_SF_S(
              v16->StubInfo,
              113,
              WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids,
              L"Global\\SC_STAGED_BOOT_DONE");
          WaitForSingleObject(EventW, 0xFFFFFFFF);
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            WPP_SF_S(
              WPP_GLOBAL_Control->StubInfo,
              114,
              WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids,
              L"Global\\SC_STAGED_BOOT_DONE");
          }
          goto LABEL_55;
        }
      }
      while ( !(unsigned int)ScGetToken(&v23, &String2) );
      if ( v17 >= v15 )
      {
        if ( v16 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v16->UserInfo) & 1) != 0 )
          WPP_SF_d(v16->StubInfo, 109, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, v17);
        v6 = 13;
        goto LABEL_56;
      }
      v18 = String2;
      if ( v16 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v16->UserInfo) & 4) != 0 )
        WPP_SF_S(v16->StubInfo, 110, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, String2);
      Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v25);
      NamedServiceRecord = ScGetNamedServiceRecord(v18, &v25);
      v6 = NamedServiceRecord;
      if ( NamedServiceRecord )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v8 = 111;
          LODWORD(v9) = (_DWORD)v18;
          goto LABEL_6;
        }
        goto LABEL_56;
      }
      started = ScStartServiceAndDependencies(v25, 0, 0, 0, 1u, 0);
      if ( !started )
        goto LABEL_40;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
        break;
LABEL_41:
      ++v17;
    }
    WPP_SF_Sd(
      WPP_GLOBAL_Control->StubInfo,
      112,
      (unsigned int)WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids,
      (_DWORD)v18,
      started);
LABEL_40:
    v16 = WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  if ( NamedServiceRecord == 2 )
  {
LABEL_55:
    v6 = 0;
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v8 = 104;
      v9 = L"System\\Setup";
LABEL_6:
      WPP_SF_Sd(
        v7->StubInfo,
        v8,
        (unsigned int)WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids,
        (_DWORD)v9,
        NamedServiceRecord);
    }
  }
LABEL_56:
  if ( Handle )
  {
    v20 = NtClose(Handle);
    RtlNtStatusToDosError(v20);
  }
  if ( EventW )
    CloseHandle(EventW);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v25);
  return v6;
}

```

## disassembly

```asm
0x140034234  push    rbp
0x140034236  push    rbx
0x140034237  push    rsi
0x140034238  push    rdi
0x140034239  push    r12
0x14003423b  push    r13
0x14003423d  push    r14
0x14003423f  push    r15
0x140034241  mov     rbp, rsp
0x140034244  sub     rsp, 48h
0x140034248  xor     r15d, r15d
0x14003424b  lea     rax, [rbp+Handle]
0x14003424f  mov     r9d, 20019h; unsigned int
0x140034255  mov     [rbp+Handle], r15
0x140034259  lea     rdx, aSystemSetup_0; "System\\\\Setup"
0x140034260  mov     [rbp+arg_10], r15
0x140034264  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x14003426b  mov     [rbp+arg_8], r15
0x14003426f  mov     esi, r15d
0x140034272  mov     [rbp+String2], r15
0x140034276  mov     r12d, r15d
0x140034279  mov     dword ptr [rbp+arg_0], r15d
0x14003427d  mov     [rsp+48h+var_28], rax; HKEY *
0x140034282  call    ?ScRegOpenKeyExW@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; ScRegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x140034287  mov     ebx, eax
0x140034289  test    eax, eax
0x14003428b  jz      short loc_1400342DB
0x14003428d  cmp     eax, 2
0x140034290  jz      loc_1400345B2
0x140034296  mov     rcx, cs:WPP_GLOBAL_Control
0x14003429d  lea     rdi, WPP_GLOBAL_Control
0x1400342a4  cmp     rcx, rdi
0x1400342a7  jz      loc_1400345B5
0x1400342ad  test    byte ptr [rcx+1Ch], 1
0x1400342b1  jz      loc_1400345B5
0x1400342b7  lea     edx, [r15+68h]
0x1400342bb  lea     r9, aSystemSetup; "System\\Setup"
0x1400342c2  mov     rcx, [rcx+10h]
0x1400342c6  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x1400342cd  mov     dword ptr [rsp+48h+var_28], eax
0x1400342d1  call    WPP_SF_Sd
0x1400342d6  jmp     loc_1400345B5
0x1400342db  mov     rcx, [rbp+Handle]; KeyHandle
0x1400342df  lea     r9, [rbp+arg_0]; unsigned int *
0x1400342e3  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x1400342e7  lea     rdx, aServicesforsta; "ServicesForStagedBoot"
0x1400342ee  call    ?ScAllocateAndReadConfigValue@@YAKPEAUHKEY__@@PEBGPEAPEAGPEAK@Z; ScAllocateAndReadConfigValue(HKEY__ *,ushort const *,ushort * *,ulong *)
0x1400342f3  mov     ebx, eax
0x1400342f5  test    eax, eax
0x1400342f7  jz      short loc_14003433D
0x1400342f9  cmp     eax, 2
0x1400342fc  jnz     short loc_140034303
0x1400342fe  mov     ebx, r15d
0x140034301  jmp     short loc_140034334
0x140034303  mov     rcx, cs:WPP_GLOBAL_Control
0x14003430a  lea     rdi, WPP_GLOBAL_Control
0x140034311  cmp     rcx, rdi
0x140034314  jz      short loc_140034334
0x140034316  test    byte ptr [rcx+1Ch], 1
0x14003431a  jz      short loc_140034334
0x14003431c  mov     rcx, [rcx+10h]
0x140034320  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140034327  mov     edx, 69h ; 'i'
0x14003432c  mov     r9d, eax
0x14003432f  call    WPP_SF_d
0x140034334  mov     rsi, [rbp+arg_8]
0x140034338  jmp     loc_1400345B5
0x14003433d  mov     rsi, [rbp+arg_8]
0x140034341  mov     edx, dword ptr [rbp+arg_0]
0x140034344  mov     rcx, rsi
0x140034347  call    ScValidateMultiSZ
0x14003434c  mov     ebx, eax
0x14003434e  test    eax, eax
0x140034350  jz      short loc_140034390
0x140034352  mov     rcx, cs:WPP_GLOBAL_Control
0x140034359  lea     rdi, WPP_GLOBAL_Control
0x140034360  cmp     rcx, rdi
0x140034363  jz      loc_1400345B5
0x140034369  test    byte ptr [rcx+1Ch], 1
0x14003436d  jz      loc_1400345B5
0x140034373  mov     edx, 6Ah ; 'j'
0x140034378  mov     r9d, eax
0x14003437b  mov     rcx, [rcx+10h]
0x14003437f  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140034386  call    WPP_SF_d
0x14003438b  jmp     loc_1400345B5
0x140034390  call    ScWStrArrayStrCount
0x140034395  mov     r13d, eax
0x140034398  test    eax, eax
0x14003439a  jnz     short loc_1400343C8
0x14003439c  lea     ebx, [rax+0Dh]
0x14003439f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400343a6  lea     rdi, WPP_GLOBAL_Control
0x1400343ad  cmp     rcx, rdi
0x1400343b0  jz      loc_1400345B5
0x1400343b6  test    byte ptr [rcx+1Ch], 1
0x1400343ba  jz      loc_1400345B5
0x1400343c0  lea     edx, [rax+6Bh]
0x1400343c3  mov     r9d, ebx
0x1400343c6  jmp     short loc_14003437B
0x1400343c8  xor     r8d, r8d; bInitialState
0x1400343cb  lea     r9, aGlobalScStaged; "Global\\SC_STAGED_BOOT_DONE"
0x1400343d2  xor     ecx, ecx; lpEventAttributes
0x1400343d4  lea     edx, [r8+1]; bManualReset
0x1400343d8  call    cs:__imp_CreateEventW
0x1400343de  mov     r12, rax
0x1400343e1  test    rax, rax
0x1400343e4  jnz     short loc_140034419
0x1400343e6  call    cs:__imp_GetLastError
0x1400343ec  mov     ebx, eax
0x1400343ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400343f5  lea     rdi, WPP_GLOBAL_Control
0x1400343fc  cmp     rcx, rdi
0x1400343ff  jz      loc_1400345B5
0x140034405  test    byte ptr [rcx+1Ch], 1
0x140034409  jz      loc_1400345B5
0x14003440f  lea     edx, [r12+6Ch]
0x140034414  jmp     loc_140034378
0x140034419  mov     r10, cs:WPP_GLOBAL_Control
0x140034420  lea     rdi, WPP_GLOBAL_Control
0x140034427  mov     r14d, r15d
0x14003442a  mov     [rbp+arg_0], rsi
0x14003442e  mov     rax, [rbp+arg_0]
0x140034432  cmp     [rax], r15w
0x140034436  jz      loc_140034550
0x14003443c  lea     rdx, [rbp+String2]; unsigned __int16 **
0x140034440  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x140034444  call    ?ScGetToken@@YAHPEAPEAG0@Z; ScGetToken(ushort * *,ushort * *)
0x140034449  test    eax, eax
0x14003444b  jz      short loc_14003442E
0x14003444d  cmp     r14d, r13d
0x140034450  jnb     loc_140034525
0x140034456  mov     r15, [rbp+String2]
0x14003445a  cmp     r10, rdi
0x14003445d  jz      short loc_14003447E
0x14003445f  test    byte ptr [r10+1Ch], 4
0x140034464  jz      short loc_14003447E
0x140034466  mov     rcx, [r10+10h]
0x14003446a  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140034471  mov     edx, 6Eh ; 'n'
0x140034476  mov     r9, r15
0x140034479  call    WPP_SF_S
0x14003447e  lea     rcx, [rbp+arg_10]
0x140034482  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140034487  lea     rdx, [rbp+arg_10]; struct CServiceRecord **
0x14003448b  mov     rcx, r15; String2
0x14003448e  call    ?ScGetNamedServiceRecord@@YAKPEBGPEAPEAVCServiceRecord@@@Z; ScGetNamedServiceRecord(ushort const *,CServiceRecord * *)
0x140034493  mov     ebx, eax
0x140034495  test    eax, eax
0x140034497  jnz     short loc_1400344FE
0x140034499  mov     rcx, [rbp+arg_10]; this
0x14003449d  xor     r9d, r9d; unsigned int
0x1400344a0  mov     [rsp+48h+var_20], 0; struct CServiceRecord *
0x1400344a9  xor     r8d, r8d; struct _STRING_PTRSW *
0x1400344ac  xor     edx, edx; unsigned int
0x1400344ae  mov     dword ptr [rsp+48h+var_28], 1; unsigned int
0x1400344b6  call    ?ScStartServiceAndDependencies@@YAKPEAVCServiceRecord@@KPEAU_STRING_PTRSW@@KK0@Z; ScStartServiceAndDependencies(CServiceRecord *,ulong,_STRING_PTRSW *,ulong,ulong,CServiceRecord *)
0x1400344bb  test    eax, eax
0x1400344bd  jz      short loc_1400344EC
0x1400344bf  mov     r10, cs:WPP_GLOBAL_Control
0x1400344c6  cmp     r10, rdi
0x1400344c9  jz      short loc_1400344F3
0x1400344cb  test    byte ptr [r10+1Ch], 2
0x1400344d0  jz      short loc_1400344F3
0x1400344d2  mov     rcx, [r10+10h]
0x1400344d6  lea     edx, [rbx+70h]
0x1400344d9  mov     r9, r15
0x1400344dc  mov     dword ptr [rsp+48h+var_28], eax
0x1400344e0  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x1400344e7  call    WPP_SF_Sd
0x1400344ec  mov     r10, cs:WPP_GLOBAL_Control
0x1400344f3  inc     r14d
0x1400344f6  xor     r15d, r15d
0x1400344f9  jmp     loc_14003442E
0x1400344fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140034505  cmp     rcx, rdi
0x140034508  jz      loc_1400345B5
0x14003450e  test    byte ptr [rcx+1Ch], 1
0x140034512  jz      loc_1400345B5
0x140034518  mov     edx, 6Fh ; 'o'
0x14003451d  mov     r9, r15
0x140034520  jmp     loc_1400342C2
0x140034525  cmp     r10, rdi
0x140034528  jz      short loc_140034549
0x14003452a  test    byte ptr [r10+1Ch], 1
0x14003452f  jz      short loc_140034549
0x140034531  mov     rcx, [r10+10h]
0x140034535  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x14003453c  mov     edx, 6Dh ; 'm'
0x140034541  mov     r9d, r14d
0x140034544  call    WPP_SF_d
0x140034549  mov     ebx, 0Dh
0x14003454e  jmp     short loc_1400345B5
0x140034550  cmp     r10, rdi
0x140034553  jz      short loc_140034578
0x140034555  test    byte ptr [r10+1Ch], 4
0x14003455a  jz      short loc_140034578
0x14003455c  mov     rcx, [r10+10h]
0x140034560  lea     r9, aGlobalScStaged; "Global\\SC_STAGED_BOOT_DONE"
0x140034567  mov     edx, 71h ; 'q'
0x14003456c  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140034573  call    WPP_SF_S
0x140034578  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14003457b  mov     rcx, r12; hHandle
0x14003457e  call    cs:__imp_WaitForSingleObject
0x140034584  mov     rcx, cs:WPP_GLOBAL_Control
0x14003458b  cmp     rcx, rdi
0x14003458e  jz      short loc_1400345B2
0x140034590  test    byte ptr [rcx+1Ch], 4
0x140034594  jz      short loc_1400345B2
0x140034596  mov     rcx, [rcx+10h]
0x14003459a  lea     r9, aGlobalScStaged; "Global\\SC_STAGED_BOOT_DONE"
0x1400345a1  mov     edx, 72h ; 'r'
0x1400345a6  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x1400345ad  call    WPP_SF_S
0x1400345b2  mov     ebx, r15d
0x1400345b5  mov     rcx, [rbp+Handle]; Handle
0x1400345b9  test    rcx, rcx
0x1400345bc  jz      short loc_1400345CC
0x1400345be  call    cs:__imp_NtClose
0x1400345c4  mov     ecx, eax; Status
0x1400345c6  call    cs:__imp_RtlNtStatusToDosError
0x1400345cc  test    r12, r12
0x1400345cf  jz      short loc_1400345DA
0x1400345d1  mov     rcx, r12; hObject
0x1400345d4  call    cs:__imp_CloseHandle
0x1400345da  mov     rcx, gs:60h
0x1400345e3  mov     r8, rsi; P
0x1400345e6  xor     edx, edx; Flags
0x1400345e8  mov     rcx, [rcx+30h]; HeapHandle
0x1400345ec  call    cs:__imp_RtlFreeHeap
0x1400345f2  lea     rcx, [rbp+arg_10]
0x1400345f6  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x1400345fb  mov     eax, ebx
0x1400345fd  add     rsp, 48h
0x140034601  pop     r15
0x140034603  pop     r14
0x140034605  pop     r13
0x140034607  pop     r12
0x140034609  pop     rdi
0x14003460a  pop     rsi
0x14003460b  pop     rbx
0x14003460c  pop     rbp
0x14003460d  retn
```
