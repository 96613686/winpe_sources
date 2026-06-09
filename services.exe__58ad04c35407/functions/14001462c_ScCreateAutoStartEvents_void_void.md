# ScCreateAutoStartEvents(void * *,void * *)

- ea: `0x14001462c`
- end: `0x14001481d`
- name: `?ScCreateAutoStartEvents@@YAKPEAPEAX0@Z`
- size: `497`
- prototype: `__int64 __fastcall(void **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400848e0`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14001462c`
- `0x140016318`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001473d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400147a2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001473d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400147a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001474b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001474b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014800`
- `ntdll!RtlNtStatusToDosError` at `0x140014708`
- `ntdll!RtlNtStatusToDosError` at `0x140014708`
- `ntdll!RtlDeleteSecurityObject` at `0x1400147f2`
- `ntdll!RtlDeleteSecurityObject` at `0x1400147f2`

## string_xrefs

- `0x140014719`: `Global\SC_AutoStartComplete`
- `0x140014773`: `Global\SC_AutoStartComplete`

## pseudocode

```c
__int64 __fastcall ScCreateAutoStartEvents(void **a1, void **a2)
{
  int v2; // eax
  NTSTATUS v3; // ebx
  HANDLE v4; // rdi
  ULONG v5; // ebx
  DWORD LastError; // eax
  PRPC_ASYNC_STATE v7; // rcx
  int v8; // edx
  const WCHAR *v9; // r9
  HANDLE v10; // rax
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+30h] [rbp-50h] BYREF
  __int16 v13; // [rsp+48h] [rbp-38h] BYREF
  char v14; // [rsp+4Ah] [rbp-36h]
  int v15; // [rsp+4Ch] [rbp-34h]
  PSID *v16; // [rsp+50h] [rbp-30h]
  __int16 v17; // [rsp+58h] [rbp-28h]
  char v18; // [rsp+5Ah] [rbp-26h]
  int v19; // [rsp+5Ch] [rbp-24h]
  __int64 *v20; // [rsp+60h] [rbp-20h]
  __int16 v21; // [rsp+68h] [rbp-18h]
  char v22; // [rsp+6Ah] [rbp-16h]
  int v23; // [rsp+6Ch] [rbp-14h]
  __int64 *v24; // [rsp+70h] [rbp-10h]
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+98h] [rbp+18h] BYREF

  v16 = &LocalSystemSid;
  ObjectDescriptor = 0;
  v20 = &AliasAdminsSid;
  v13 = 0;
  v24 = &AuthenticatedUserSid;
  v14 = 0;
  v15 = 0x10000000;
  v17 = 0;
  v18 = 0;
  v19 = -1610612736;
  v21 = 0;
  v22 = 0;
  v23 = 0x100000;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v2 = ScCreateAndSetSD(
         (unsigned int)&v13,
         3,
         (_DWORD)LocalSystemSid,
         (_DWORD)LocalSystemSid,
         (__int64)&ObjectDescriptor);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 0;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 94, WPP_73e763182c4133cee281a4c48659d989_Traceguids, (unsigned int)v2);
    v5 = RtlNtStatusToDosError(v3);
    goto LABEL_16;
  }
  EventAttributes.nLength = 24;
  EventAttributes.bInheritHandle = 0;
  EventAttributes.lpSecurityDescriptor = ObjectDescriptor;
  v4 = CreateEventW(&EventAttributes, 1, 0, L"Global\\SC_AutoStartComplete");
  if ( !v4 )
  {
    LastError = GetLastError();
    v5 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_16;
    v8 = 95;
    v9 = L"Global\\SC_AutoStartComplete";
LABEL_10:
    WPP_SF_Sd(v7->StubInfo, v8, (unsigned int)WPP_73e763182c4133cee281a4c48659d989_Traceguids, (_DWORD)v9, LastError);
    goto LABEL_16;
  }
  v10 = CreateEventW(&EventAttributes, 1, 0, L"Global\\SC_AutoStartPhase1Done");
  if ( v10 )
  {
    v5 = 0;
    g_hAutoStartEvent = v4;
    v4 = 0;
    g_hAutoStartPhase1Event = v10;
    goto LABEL_16;
  }
  LastError = GetLastError();
  v5 = LastError;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    v8 = 96;
    v9 = L"Global\\SC_AutoStartPhase1Done";
    goto LABEL_10;
  }
LABEL_16:
  RtlDeleteSecurityObject(&ObjectDescriptor);
  if ( v4 )
    CloseHandle(v4);
  return v5;
}

```

## disassembly

```asm
0x14001462c  mov     r11, rsp
0x14001462f  mov     [r11+8], rbx
0x140014633  mov     [r11+18h], rdi
0x140014637  mov     [r11+10h], rdx
0x14001463b  push    rbp
0x14001463c  mov     rbp, rsp
0x14001463f  sub     rsp, 80h
0x140014646  mov     r8, cs:LocalSystemSid
0x14001464d  lea     rax, LocalSystemSid
0x140014654  mov     [rbp+var_30], rax
0x140014658  lea     rcx, [rbp+var_38]
0x14001465c  lea     rax, AliasAdminsSid
0x140014663  mov     [rbp+ObjectDescriptor], 0
0x14001466b  mov     [rbp+var_20], rax
0x14001466f  xorps   xmm0, xmm0
0x140014672  lea     rax, AuthenticatedUserSid
0x140014679  mov     [rbp+var_38], 0
0x14001467f  mov     [rbp+var_10], rax
0x140014683  mov     r9, r8
0x140014686  xor     eax, eax
0x140014688  mov     [rbp+var_36], 0
0x14001468c  mov     qword ptr [rbp+EventAttributes.bInheritHandle], rax
0x140014690  mov     edx, 3
0x140014695  lea     rax, [rbp+ObjectDescriptor]
0x140014699  mov     [rbp+var_34], 10000000h
0x1400146a0  mov     [r11-68h], rax
0x1400146a4  mov     [rbp+var_28], 0
0x1400146aa  mov     [rbp+var_26], 0
0x1400146ae  mov     [rbp+var_24], 0A0000000h
0x1400146b5  mov     [rbp+var_18], 0
0x1400146bb  mov     [rbp+var_16], 0
0x1400146bf  mov     [rbp+var_14], 100000h
0x1400146c6  movups  xmmword ptr [rbp+EventAttributes.nLength], xmm0
0x1400146ca  call    ScCreateAndSetSD
0x1400146cf  mov     ebx, eax
0x1400146d1  test    eax, eax
0x1400146d3  jns     short loc_140014715
0x1400146d5  xor     edi, edi
0x1400146d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400146de  lea     rdx, WPP_GLOBAL_Control
0x1400146e5  cmp     rcx, rdx
0x1400146e8  jz      short loc_140014706
0x1400146ea  test    byte ptr [rcx+1Ch], 1
0x1400146ee  jz      short loc_140014706
0x1400146f0  mov     rcx, [rcx+10h]
0x1400146f4  lea     edx, [rdi+5Eh]
0x1400146f7  mov     r9d, eax
0x1400146fa  lea     r8, WPP_73e763182c4133cee281a4c48659d989_Traceguids
0x140014701  call    WPP_SF_d
0x140014706  mov     ecx, ebx; Status
0x140014708  call    cs:__imp_RtlNtStatusToDosError
0x14001470e  mov     ebx, eax
0x140014710  jmp     loc_1400147EE
0x140014715  mov     rax, [rbp+ObjectDescriptor]
0x140014719  lea     r9, Name; "Global\\SC_AutoStartComplete"
0x140014720  xor     r8d, r8d; bInitialState
0x140014723  mov     [rbp+EventAttributes.nLength], 18h
0x14001472a  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x14001472e  mov     [rbp+EventAttributes.bInheritHandle], 0
0x140014735  mov     [rbp+EventAttributes.lpSecurityDescriptor], rax
0x140014739  lea     edx, [r8+1]; bManualReset
0x14001473d  call    cs:__imp_CreateEventW
0x140014743  mov     rdi, rax
0x140014746  test    rax, rax
0x140014749  jnz     short loc_140014790
0x14001474b  call    cs:__imp_GetLastError
0x140014751  mov     ebx, eax
0x140014753  mov     rcx, cs:WPP_GLOBAL_Control
0x14001475a  lea     rdx, WPP_GLOBAL_Control
0x140014761  cmp     rcx, rdx
0x140014764  jz      loc_1400147EE
0x14001476a  test    byte ptr [rcx+1Ch], 1
0x14001476e  jz      short loc_1400147EE
0x140014770  lea     edx, [rdi+5Fh]
0x140014773  lea     r9, Name; "Global\\SC_AutoStartComplete"
0x14001477a  mov     rcx, [rcx+10h]
0x14001477e  lea     r8, WPP_73e763182c4133cee281a4c48659d989_Traceguids
0x140014785  mov     [rsp+80h+var_60], eax
0x140014789  call    WPP_SF_Sd
0x14001478e  jmp     short loc_1400147EE
0x140014790  xor     r8d, r8d; bInitialState
0x140014793  lea     r9, aGlobalScAutost; "Global\\SC_AutoStartPhase1Done"
0x14001479a  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x14001479e  lea     edx, [r8+1]; bManualReset
0x1400147a2  call    cs:__imp_CreateEventW
0x1400147a8  test    rax, rax
0x1400147ab  jnz     short loc_1400147DC
0x1400147ad  call    cs:__imp_GetLastError
0x1400147b3  mov     ebx, eax
0x1400147b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400147bc  lea     rdx, WPP_GLOBAL_Control
0x1400147c3  cmp     rcx, rdx
0x1400147c6  jz      short loc_1400147EE
0x1400147c8  test    byte ptr [rcx+1Ch], 1
0x1400147cc  jz      short loc_1400147EE
0x1400147ce  mov     edx, 60h ; '`'
0x1400147d3  lea     r9, aGlobalScAutost; "Global\\SC_AutoStartPhase1Done"
0x1400147da  jmp     short loc_14001477A
0x1400147dc  xor     ebx, ebx
0x1400147de  mov     cs:?g_hAutoStartEvent@@3PEAXEA, rdi; void * g_hAutoStartEvent
0x1400147e5  xor     edi, edi
0x1400147e7  mov     cs:?g_hAutoStartPhase1Event@@3PEAXEA, rax; void * g_hAutoStartPhase1Event
0x1400147ee  lea     rcx, [rbp+ObjectDescriptor]; ObjectDescriptor
0x1400147f2  call    cs:__imp_RtlDeleteSecurityObject
0x1400147f8  test    rdi, rdi
0x1400147fb  jz      short loc_140014806
0x1400147fd  mov     rcx, rdi; hObject
0x140014800  call    cs:__imp_CloseHandle
0x140014806  lea     r11, [rsp+80h+var_s0]
0x14001480e  mov     eax, ebx
0x140014810  mov     rbx, [r11+10h]
0x140014814  mov     rdi, [r11+20h]
0x140014818  mov     rsp, r11
0x14001481b  pop     rbp
0x14001481c  retn
```
