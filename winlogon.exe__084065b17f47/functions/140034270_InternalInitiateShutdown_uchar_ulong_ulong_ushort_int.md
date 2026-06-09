# InternalInitiateShutdown(uchar,ulong,ulong,ushort *,int)

- ea: `0x140034270`
- end: `0x14003466b`
- name: `?InternalInitiateShutdown@@YAKEKKPEAGH@Z`
- size: `1019`
- prototype: `unsigned int(unsigned __int8, unsigned int, unsigned int, unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140052c20`
- `0x140065644`
- `0x1400858e0`
- `0x1400877f0`
- `0x14008a85c`

## callees

- `0x1400057f4`
- `0x140031970`
- `0x140034270`
- `0x140041c34`
- `0x140053720`
- `0x140055588`

## import_xrefs

- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x140034431`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x140034431`
- `ntdll!NtShutdownSystem` at `0x1400344e6`
- `ntdll!NtShutdownSystem` at `0x1400344e6`
- `ntdll!NtAdjustPrivilegesToken` at `0x140034395`
- `ntdll!NtAdjustPrivilegesToken` at `0x1400345d5`
- `ntdll!NtAdjustPrivilegesToken` at `0x140034395`
- `ntdll!NtAdjustPrivilegesToken` at `0x1400345d5`
- `ntdll!NtOpenThreadToken` at `0x14003445c`
- `ntdll!NtOpenThreadToken` at `0x140034652`
- `ntdll!NtOpenThreadToken` at `0x14003445c`
- `ntdll!NtOpenThreadToken` at `0x140034652`
- `ntdll!EtwEventEnabled` at `0x1400342d5`
- `ntdll!EtwEventEnabled` at `0x140034509`
- `ntdll!EtwEventEnabled` at `0x1400342d5`
- `ntdll!EtwEventEnabled` at `0x140034509`
- `ntdll!EtwEventWrite` at `0x140034311`
- `ntdll!EtwEventWrite` at `0x14003453f`
- `ntdll!EtwEventWrite` at `0x140034311`
- `ntdll!EtwEventWrite` at `0x14003453f`
- `ntdll!NtOpenProcessToken` at `0x14003433c`
- `ntdll!NtOpenProcessToken` at `0x14003458e`
- `ntdll!NtOpenProcessToken` at `0x14003433c`
- `ntdll!NtOpenProcessToken` at `0x14003458e`
- `ntdll!RtlNtStatusToDosError` at `0x1400343f1`
- `ntdll!RtlNtStatusToDosError` at `0x1400343f1`
- `ntdll!NtClose` at `0x1400343a2`
- `ntdll!NtClose` at `0x1400345e2`
- `ntdll!NtClose` at `0x1400343a2`
- `ntdll!NtClose` at `0x1400345e2`

## pseudocode

```c
__int64 __fastcall InternalInitiateShutdown(char a1, ULONG a2, DWORD a3, unsigned __int16 *a4, int a5)
{
  bool v9; // r15
  NTSTATUS v10; // eax
  int v11; // edi
  ULONG v12; // edi
  DWORD v13; // eax
  __int64 v14; // r9
  CUser *v15; // rcx
  NTSTATUS v17; // eax
  NTSTATUS v18; // esi
  ULONG ReturnLength; // [rsp+40h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-80h] BYREF
  DWORD v21; // [rsp+50h] [rbp-78h]
  struct _TOKEN_PRIVILEGES NewState; // [rsp+58h] [rbp-70h] BYREF
  _QWORD v23[2]; // [rsp+68h] [rbp-60h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+78h] [rbp-50h] BYREF

  v9 = 0;
  if ( !(unsigned __int8)IsInitiateShutdownWPresent() )
    return 50;
  ReturnLength = a2;
  if ( g_TraceRegHandle && (unsigned __int8)EtwEventEnabled(g_TraceRegHandle, WLEvt_InitiateShutdown_Start) )
  {
    v23[0] = &ReturnLength;
    v23[1] = 4;
    EtwEventWrite(g_TraceRegHandle, WLEvt_InitiateShutdown_Start, 1, v23);
  }
  TokenHandle = 0;
  ReturnLength = 0;
  if ( a1 == 1 )
    v10 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 1u, &TokenHandle);
  else
    v10 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x28u, &TokenHandle);
  v11 = v10;
  if ( v10 < 0 )
    goto LABEL_10;
  v23[0] = 19;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = (LUID)19LL;
  NewState.Privileges[0].Attributes = 2;
  v11 = NtAdjustPrivilegesToken(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
  NtClose(TokenHandle);
  if ( v11 == 262 )
  {
    v11 = -1073741727;
  }
  else
  {
    if ( v11 < 0 )
      goto LABEL_10;
    if ( PreviousState.PrivilegeCount )
      v9 = (PreviousState.Privileges[0].Attributes & 2) != 0;
    else
      v9 = 1;
  }
  if ( v11 >= 0 )
  {
    v13 = InitiateShutdownW(0, a4, 0, a2, a3);
    v12 = v13;
    v21 = v13;
    if ( v13 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v13);
        v15 = WPP_GLOBAL_Control;
      }
      if ( a5 )
      {
        if ( v15 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) )
          WPP_SF_(*((_QWORD *)v15 + 2), 26, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v14);
        NtShutdownSystem(ShutdownReboot);
      }
    }
    goto LABEL_33;
  }
LABEL_10:
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids,
      (unsigned int)v11);
  }
  v12 = RtlNtStatusToDosError(v11);
  v21 = v12;
LABEL_33:
  if ( !v9 )
  {
    TokenHandle = 0;
    ReturnLength = 0;
    v17 = a1 == 1
        ? NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 1u, &TokenHandle)
        : NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x28u, &TokenHandle);
    v18 = v17;
    if ( v17 < 0 )
      goto LABEL_46;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = (LUID)19LL;
    NewState.Privileges[0].Attributes = 0;
    v18 = NtAdjustPrivilegesToken(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
    NtClose(TokenHandle);
    if ( v18 == 262 )
      v18 = -1073741727;
    if ( v18 < 0 )
    {
LABEL_46:
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids,
          (unsigned int)v18);
      }
    }
  }
  ReturnLength = v12;
  if ( g_TraceRegHandle )
  {
    if ( (unsigned __int8)EtwEventEnabled(g_TraceRegHandle, WLEvt_InitiateShutdown_Stop) )
    {
      *(_QWORD *)&NewState.PrivilegeCount = &ReturnLength;
      *(_QWORD *)&NewState.Privileges[0].Luid.HighPart = 4;
      EtwEventWrite(g_TraceRegHandle, WLEvt_InitiateShutdown_Stop, 1, &NewState);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140034270  push    rbx
0x140034272  push    rsi
0x140034273  push    rdi
0x140034274  push    r12
0x140034276  push    r13
0x140034278  push    r14
0x14003427a  push    r15
0x14003427c  sub     rsp, 90h
0x140034283  mov     rax, cs:__security_cookie
0x14003428a  xor     rax, rsp
0x14003428d  mov     [rsp+0C8h+var_40], rax
0x140034295  mov     r13, r9
0x140034298  mov     r12d, r8d
0x14003429b  mov     esi, edx
0x14003429d  movzx   r14d, cl
0x1400342a1  mov     [rsp+0C8h+var_90], cl
0x1400342a5  xor     r15b, r15b
0x1400342a8  mov     [rsp+0C8h+var_98], r15b
0x1400342ad  call    IsInitiateShutdownWPresent
0x1400342b2  test    al, al
0x1400342b4  jz      loc_140034639
0x1400342ba  mov     [rsp+0C8h+var_88], esi
0x1400342be  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x1400342c5  test    rcx, rcx
0x1400342c8  jz      loc_14003465D
0x1400342ce  lea     rdx, WLEvt_InitiateShutdown_Start
0x1400342d5  call    cs:__imp_EtwEventEnabled
0x1400342db  test    al, al
0x1400342dd  jz      loc_14003465D
0x1400342e3  lea     rax, [rsp+0C8h+var_88]
0x1400342e8  mov     [rsp+0C8h+var_60], rax
0x1400342ed  mov     [rsp+0C8h+var_58], 4
0x1400342f6  xor     ebx, ebx
0x1400342f8  lea     r9, [rsp+0C8h+var_60]
0x1400342fd  mov     r8d, 1
0x140034303  lea     rdx, WLEvt_InitiateShutdown_Start
0x14003430a  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x140034311  call    cs:__imp_EtwEventWrite
0x140034317  nop
0x140034318  mov     [rsp+0C8h+TokenHandle], rbx
0x14003431d  mov     [rsp+0C8h+var_88], ebx
0x140034321  mov     edx, 28h ; '('; DesiredAccess
0x140034326  cmp     r14b, 1
0x14003432a  jz      loc_14003444D
0x140034330  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x140034335  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14003433c  call    cs:__imp_NtOpenProcessToken
0x140034342  mov     edi, eax
0x140034344  test    eax, eax
0x140034346  js      short loc_1400343B8
0x140034348  mov     [rsp+0C8h+var_60], rbx
0x14003434d  mov     [rsp+0C8h+var_60], 13h
0x140034356  mov     [rsp+0C8h+NewState.PrivilegeCount], 1
0x14003435e  mov     qword ptr [rsp+0C8h+NewState.Privileges.Luid.LowPart], 13h
0x140034367  mov     [rsp+0C8h+NewState.Privileges.Attributes], 2
0x14003436f  lea     rax, [rsp+0C8h+var_88]
0x140034374  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x140034379  lea     rax, [rsp+0C8h+var_50]
0x14003437e  mov     [rsp+0C8h+PreviousState], rax; PreviousState
0x140034383  mov     r9d, 10h; BufferLength
0x140034389  lea     r8, [rsp+0C8h+NewState]; NewState
0x14003438e  xor     edx, edx; DisableAllPrivileges
0x140034390  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x140034395  call    cs:__imp_NtAdjustPrivilegesToken
0x14003439b  mov     edi, eax
0x14003439d  mov     rcx, [rsp+0C8h+TokenHandle]; Handle
0x1400343a2  call    cs:__imp_NtClose
0x1400343a8  cmp     edi, 106h
0x1400343ae  jz      loc_140034467
0x1400343b4  test    edi, edi
0x1400343b6  jns     short loc_140034402
0x1400343b8  lea     r12, WPP_GLOBAL_Control
0x1400343bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400343c6  cmp     rcx, r12
0x1400343c9  jz      short loc_1400343EF
0x1400343cb  test    byte ptr [rcx+1Ch], 1
0x1400343cf  jz      short loc_1400343EF
0x1400343d1  cmp     byte ptr [rcx+19h], 2
0x1400343d5  jb      short loc_1400343EF
0x1400343d7  mov     edx, 18h
0x1400343dc  mov     r9d, edi
0x1400343df  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x1400343e6  mov     rcx, [rcx+10h]
0x1400343ea  call    WPP_SF_d
0x1400343ef  mov     ecx, edi; Status
0x1400343f1  call    cs:__imp_RtlNtStatusToDosError
0x1400343f7  mov     edi, eax
0x1400343f9  mov     [rsp+0C8h+var_78], eax
0x1400343fd  jmp     loc_1400344ED
0x140034402  cmp     [rsp+0C8h+var_50.PrivilegeCount], 0
0x140034407  jz      short loc_14003446E
0x140034409  mov     r15d, [rsp+0C8h+var_50.Privileges.Attributes]
0x140034411  shr     r15d, 1
0x140034414  and     r15b, 1
0x140034418  mov     [rsp+0C8h+var_98], r15b
0x14003441d  test    edi, edi
0x14003441f  js      short loc_1400343B8
0x140034421  mov     dword ptr [rsp+0C8h+PreviousState], r12d; dwReason
0x140034426  mov     r9d, esi; dwShutdownFlags
0x140034429  xor     r8d, r8d; dwGracePeriod
0x14003442c  mov     rdx, r13; lpMessage
0x14003442f  xor     ecx, ecx; lpMachineName
0x140034431  call    cs:__imp_InitiateShutdownW
0x140034437  mov     edi, eax
0x140034439  mov     [rsp+0C8h+var_78], eax
0x14003443d  test    eax, eax
0x14003443f  jnz     short loc_140034473
0x140034441  lea     r12, WPP_GLOBAL_Control
0x140034448  jmp     loc_1400344ED
0x14003444d  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x140034452  mov     r8b, 1; OpenAsSelf
0x140034455  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14003445c  call    cs:__imp_NtOpenThreadToken
0x140034462  jmp     loc_140034342
0x140034467  mov     edi, 0C0000061h
0x14003446c  jmp     short loc_14003441D
0x14003446e  mov     r15b, 1
0x140034471  jmp     short loc_140034418
0x140034473  lea     r12, WPP_GLOBAL_Control
0x14003447a  mov     rcx, cs:WPP_GLOBAL_Control
0x140034481  cmp     rcx, r12
0x140034484  jz      short loc_1400344B1
0x140034486  test    byte ptr [rcx+1Ch], 1
0x14003448a  jz      short loc_1400344B1
0x14003448c  cmp     byte ptr [rcx+19h], 2
0x140034490  jb      short loc_1400344B1
0x140034492  mov     edx, 19h
0x140034497  mov     r9d, eax
0x14003449a  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x1400344a1  mov     rcx, [rcx+10h]
0x1400344a5  call    WPP_SF_d
0x1400344aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400344b1  cmp     [rsp+0C8h+arg_20], 0
0x1400344b9  jz      short loc_1400344ED
0x1400344bb  cmp     rcx, r12
0x1400344be  jz      short loc_1400344E1
0x1400344c0  test    byte ptr [rcx+1Ch], 1
0x1400344c4  jz      short loc_1400344E1
0x1400344c6  cmp     byte ptr [rcx+19h], 1
0x1400344ca  jb      short loc_1400344E1
0x1400344cc  mov     edx, 1Ah
0x1400344d1  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x1400344d8  mov     rcx, [rcx+10h]
0x1400344dc  call    WPP_SF_
0x1400344e1  mov     ecx, 1; Action
0x1400344e6  call    cs:__imp_NtShutdownSystem
0x1400344ec  nop
0x1400344ed  test    r15b, r15b
0x1400344f0  jz      short loc_14003456A
0x1400344f2  mov     [rsp+0C8h+var_88], edi
0x1400344f6  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x1400344fd  test    rcx, rcx
0x140034500  jz      short loc_140034545
0x140034502  lea     rdx, WLEvt_InitiateShutdown_Stop
0x140034509  call    cs:__imp_EtwEventEnabled
0x14003450f  test    al, al
0x140034511  jz      short loc_140034545
0x140034513  lea     rax, [rsp+0C8h+var_88]
0x140034518  mov     qword ptr [rsp+0C8h+NewState.PrivilegeCount], rax
0x14003451d  mov     qword ptr [rsp+60h], 4
0x140034526  lea     r9, [rsp+0C8h+NewState]
0x14003452b  mov     r8d, 1
0x140034531  lea     rdx, WLEvt_InitiateShutdown_Stop
0x140034538  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x14003453f  call    cs:__imp_EtwEventWrite
0x140034545  mov     eax, edi
0x140034547  mov     rcx, [rsp+0C8h+var_40]
0x14003454f  xor     rcx, rsp; StackCookie
0x140034552  call    __security_check_cookie
0x140034557  add     rsp, 90h
0x14003455e  pop     r15
0x140034560  pop     r14
0x140034562  pop     r13
0x140034564  pop     r12
0x140034566  pop     rdi
0x140034567  pop     rsi
0x140034568  pop     rbx
0x140034569  retn
0x14003456a  mov     [rsp+0C8h+TokenHandle], rbx
0x14003456f  mov     [rsp+0C8h+var_88], ebx
0x140034573  mov     edx, 28h ; '('; DesiredAccess
0x140034578  cmp     r14b, 1
0x14003457c  jz      loc_140034643
0x140034582  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x140034587  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14003458e  call    cs:__imp_NtOpenProcessToken
0x140034594  mov     esi, eax
0x140034596  test    eax, eax
0x140034598  js      short loc_1400345F8
0x14003459a  mov     [rsp+0C8h+NewState.PrivilegeCount], 1
0x1400345a2  mov     qword ptr [rsp+0C8h+NewState.Privileges.Luid.LowPart], 13h
0x1400345ab  mov     [rsp+0C8h+NewState.Privileges.Attributes], ebx
0x1400345af  lea     rax, [rsp+0C8h+var_88]
0x1400345b4  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x1400345b9  lea     rax, [rsp+0C8h+var_50]
0x1400345be  mov     [rsp+0C8h+PreviousState], rax; PreviousState
0x1400345c3  mov     r9d, 10h; BufferLength
0x1400345c9  lea     r8, [rsp+0C8h+NewState]; NewState
0x1400345ce  xor     edx, edx; DisableAllPrivileges
0x1400345d0  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x1400345d5  call    cs:__imp_NtAdjustPrivilegesToken
0x1400345db  mov     esi, eax
0x1400345dd  mov     rcx, [rsp+0C8h+TokenHandle]; Handle
0x1400345e2  call    cs:__imp_NtClose
0x1400345e8  cmp     esi, 106h
0x1400345ee  jz      short loc_140034664
0x1400345f0  test    esi, esi
0x1400345f2  jns     loc_1400344F2
0x1400345f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400345ff  cmp     rcx, r12
0x140034602  jz      loc_1400344F2
0x140034608  test    byte ptr [rcx+1Ch], 1
0x14003460c  jz      loc_1400344F2
0x140034612  cmp     byte ptr [rcx+19h], 2
0x140034616  jb      loc_1400344F2
0x14003461c  mov     edx, 1Bh
0x140034621  mov     r9d, esi
0x140034624  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14003462b  mov     rcx, [rcx+10h]
0x14003462f  call    WPP_SF_d
0x140034634  jmp     loc_1400344F2
0x140034639  mov     eax, 32h ; '2'
0x14003463e  jmp     loc_140034547
0x140034643  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x140034648  mov     r8b, 1; OpenAsSelf
0x14003464b  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140034652  call    cs:__imp_NtOpenThreadToken
0x140034658  jmp     loc_140034594
0x14003465d  xor     ebx, ebx
0x14003465f  jmp     loc_140034318
0x140034664  mov     esi, 0C0000061h
0x140034669  jmp     short loc_1400345F0
0x14009e330  push    rbp
0x14009e332  sub     rsp, 30h
0x14009e336  mov     rbp, rdx
0x14009e339  cmp     byte ptr [rbp+30h], 0
0x14009e33d  jnz     short loc_14009E390
0x14009e33f  lea     r9, [rbp+30h]
0x14009e343  movzx   r8d, byte ptr [rbp+38h]
0x14009e348  xor     edx, edx
0x14009e34a  mov     ecx, 13h
0x14009e34f  call    MyRtlAdjustPrivilege
0x14009e354  test    eax, eax
0x14009e356  jns     short loc_14009E390
0x14009e358  lea     rdx, WPP_GLOBAL_Control
0x14009e35f  mov     rcx, cs:WPP_GLOBAL_Control
0x14009e366  cmp     rcx, rdx
0x14009e369  jz      short loc_14009E390
0x14009e36b  test    byte ptr [rcx+1Ch], 1
0x14009e36f  jz      short loc_14009E390
0x14009e371  cmp     byte ptr [rcx+19h], 2
0x14009e375  jb      short loc_14009E390
0x14009e377  mov     edx, 1Bh
0x14009e37c  mov     r9d, eax
0x14009e37f  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14009e386  mov     rcx, [rcx+10h]
0x14009e38a  call    WPP_SF_d
0x14009e38f  nop
0x14009e390  add     rsp, 30h
0x14009e394  pop     rbp
0x14009e395  retn
```
