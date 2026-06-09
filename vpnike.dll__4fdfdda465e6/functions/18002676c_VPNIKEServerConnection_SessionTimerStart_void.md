# VPNIKEServerConnection::SessionTimerStart(void)

- ea: `0x18002676c`
- end: `0x180026a75`
- name: `?SessionTimerStart@VPNIKEServerConnection@@IEAAKXZ`
- size: `777`
- prototype: `__int64 __fastcall(VPNIKEServerConnection *this)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800246a0`
- `0x1800256c4`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18002676c`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268b4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800268a6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800268a6`

## string_xrefs

- `0x1800268f8`: `CreateTimerQueueTimer failed: %d`
- `0x1800269a7`: `CreateTimerQueueTimer is set for session time out: %u`

## pseudocode

```c
__int64 __fastcall VPNIKEServerConnection::SessionTimerStart(VPNIKEServerConnection *this)
{
  PVOID *v2; // rbx
  unsigned int v3; // esi
  __int64 v4; // rax
  __int64 v5; // rdx
  __int128 *v6; // r9
  __int64 v7; // rax
  __int64 v8; // rdx
  __int128 *v9; // r9
  unsigned int v10; // ebx
  unsigned int LastError; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v14; // [rsp+50h] [rbp-B0h]
  __int128 v15; // [rsp+60h] [rbp-A0h]
  __int64 v16; // [rsp+70h] [rbp-90h]
  int v17; // [rsp+78h] [rbp-88h]
  int v18; // [rsp+7Ch] [rbp-84h]
  __int128 v19; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+90h] [rbp-70h] BYREF
  __int128 v21; // [rsp+94h] [rbp-6Ch]
  __int128 v22; // [rsp+A4h] [rbp-5Ch]
  int v23; // [rsp+B4h] [rbp-4Ch]
  int v24; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v25[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  LastError = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v19 = 0;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v3 = -1;
  v17 = -1;
  v18 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v13,
      L"VPNIKEServerConnection::SessionTimerStart",
      &LastError,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 14));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 25) )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 51);
    if ( CreateTimerQueueTimer(
           (PHANDLE)this + 46,
           0,
           VPNIKEServerConnection::SessionTimerCallback,
           this,
           1000 * *((_DWORD *)this + 25),
           0,
           0x20u) )
    {
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v24) = 0;
        LOWORD(v20) = 0;
        v7 = *((_QWORD *)this + 14);
        if ( v7 && *(_QWORD *)(v7 + 16) )
          v3 = *(_DWORD *)(v7 + 16);
        ConvertPortNoToString(&v20, v3);
        FormatRRASErrorString(
          &v24,
          L"CreateTimerQueueTimer is set for session time out: %u",
          (unsigned int)(1000 * *((_DWORD *)this + 25)));
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v8 = *((_QWORD *)this + 14);
          LODWORD(v9) = v8 + 2120;
          if ( !v8 )
            v9 = &v19;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)&v24,
            (_DWORD)v9,
            (v8 + 2686) & -(__int64)(v8 != 0),
            (__int64)&v20);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v24) = 0;
        LOWORD(v20) = 0;
        v4 = *((_QWORD *)this + 14);
        if ( v4 && *(_QWORD *)(v4 + 16) )
          v3 = *(_DWORD *)(v4 + 16);
        ConvertPortNoToString(&v20, v3);
        FormatRRASErrorString(&v24, L"CreateTimerQueueTimer failed: %d", LastError);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v5 = *((_QWORD *)this + 14);
          LODWORD(v6) = v5 + 2120;
          if ( !v5 )
            v6 = &v19;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v24,
            (_DWORD)v6,
            (v5 + 2686) & -(__int64)(v5 != 0),
            (__int64)&v20);
        }
      }
      BaseConnection::DeleteRef(this);
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 68, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids, LastError);
  v10 = LastError;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v13);
  return v10;
}

```

## disassembly

```asm
0x18002676c  mov     [rsp-8+arg_8], rbx
0x180026771  mov     [rsp-8+arg_10], rsi
0x180026776  push    rbp
0x180026777  push    rdi
0x180026778  push    r12
0x18002677a  lea     rbp, [rsp-7D0h]
0x180026782  sub     rsp, 8D0h
0x180026789  mov     rax, cs:__security_cookie
0x180026790  xor     rax, rsp
0x180026793  mov     [rbp+7E0h+var_20], rax
0x18002679a  mov     rdi, rcx
0x18002679d  lea     r12, WPP_GLOBAL_Control
0x1800267a4  mov     rbx, cs:WPP_GLOBAL_Control
0x1800267ab  cmp     rbx, r12
0x1800267ae  jz      short loc_1800267D8
0x1800267b0  test    byte ptr [rbx+1Ch], 1
0x1800267b4  jz      short loc_1800267D8
0x1800267b6  cmp     byte ptr [rbx+19h], 6
0x1800267ba  jb      short loc_1800267D8
0x1800267bc  mov     edx, 43h ; 'C'
0x1800267c1  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x1800267c8  mov     rcx, [rbx+10h]
0x1800267cc  call    WPP_SF_
0x1800267d1  mov     rbx, cs:WPP_GLOBAL_Control
0x1800267d8  mov     [rsp+8E0h+var_8A0], 0
0x1800267e0  xor     eax, eax
0x1800267e2  mov     [rbp+7E0h+var_820], eax
0x1800267e5  xor     edx, edx; Val
0x1800267e7  mov     r8d, 7FCh; Size
0x1800267ed  lea     rcx, [rbp+7E0h+var_81C]; void *
0x1800267f1  call    memset_0
0x1800267f6  xor     eax, eax
0x1800267f8  mov     [rbp+7E0h+var_850], eax
0x1800267fb  xorps   xmm0, xmm0
0x1800267fe  movups  [rbp+7E0h+var_84C], xmm0
0x180026802  movups  [rbp+7E0h+var_83C], xmm0
0x180026806  mov     [rbp+7E0h+var_82C], eax
0x180026809  movups  [rbp+7E0h+var_860], xmm0
0x18002680d  xorps   xmm1, xmm1
0x180026810  movdqu  [rsp+8E0h+var_890], xmm1
0x180026816  mov     [rsp+8E0h+var_898], rax
0x18002681b  movdqu  [rsp+8E0h+var_880], xmm0
0x180026821  mov     [rsp+8E0h+var_870], rax
0x180026826  or      esi, 0FFFFFFFFh
0x180026829  mov     [rsp+8E0h+var_868], esi
0x18002682d  mov     [rsp+8E0h+var_864], eax
0x180026831  test    cs:byte_1800AA941, 8
0x180026838  jz      short loc_180026867
0x18002683a  mov     rax, [rdi+70h]
0x18002683e  mov     qword ptr [rsp+8E0h+DueTime], rax; void *
0x180026843  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18002684a  lea     r8, [rsp+8E0h+var_8A0]; unsigned int *
0x18002684f  lea     rdx, aVpnikeserverco_9; "VPNIKEServerConnection::SessionTimerSta"...
0x180026856  lea     rcx, [rsp+8E0h+var_898]; this
0x18002685b  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180026860  mov     rbx, cs:WPP_GLOBAL_Control
0x180026867  cmp     dword ptr [rdi+64h], 0
0x18002686b  jz      loc_180026A13
0x180026871  lock inc dword ptr [rdi+0CCh]
0x180026878  imul    eax, [rdi+64h], 3E8h
0x18002687f  lea     rcx, [rdi+170h]; phNewTimer
0x180026886  mov     [rsp+8E0h+Flags], 20h ; ' '; Flags
0x18002688e  mov     [rsp+8E0h+Period], 0; Period
0x180026896  mov     [rsp+8E0h+DueTime], eax; DueTime
0x18002689a  mov     r9, rdi; Parameter
0x18002689d  lea     r8, ?SessionTimerCallback@VPNIKEServerConnection@@KAXPEAXE@Z; Callback
0x1800268a4  xor     edx, edx; TimerQueue
0x1800268a6  call    cs:__imp_CreateTimerQueueTimer
0x1800268ac  test    eax, eax
0x1800268ae  jnz     loc_18002696A
0x1800268b4  call    cs:__imp_GetLastError
0x1800268ba  mov     [rsp+8E0h+var_8A0], eax
0x1800268be  test    cs:byte_1800AA941, 4
0x1800268c5  jz      loc_18002695D
0x1800268cb  xor     eax, eax
0x1800268cd  mov     word ptr [rbp+7E0h+var_820], ax
0x1800268d1  mov     word ptr [rbp+7E0h+var_850], ax
0x1800268d5  mov     rax, [rdi+70h]
0x1800268d9  test    rax, rax
0x1800268dc  jz      short loc_1800268E8
0x1800268de  cmp     qword ptr [rax+10h], 0
0x1800268e3  jz      short loc_1800268E8
0x1800268e5  mov     esi, [rax+10h]
0x1800268e8  mov     edx, esi
0x1800268ea  lea     rcx, [rbp+7E0h+var_850]
0x1800268ee  call    ConvertPortNoToString
0x1800268f3  mov     r8d, [rsp+8E0h+var_8A0]
0x1800268f8  lea     rdx, aCreatetimerque_0; "CreateTimerQueueTimer failed: %d"
0x1800268ff  lea     rcx, [rbp+7E0h+var_820]
0x180026903  call    FormatRRASErrorString
0x180026908  test    cs:byte_1800AA941, 4
0x18002690f  jz      short loc_18002695D
0x180026911  mov     rdx, [rdi+70h]
0x180026915  mov     rax, rdx
0x180026918  lea     rcx, [rdx+0A7Eh]
0x18002691f  neg     rax
0x180026922  sbb     r8, r8
0x180026925  and     r8, rcx
0x180026928  test    rdx, rdx
0x18002692b  lea     r9, [rdx+848h]
0x180026932  jnz     short loc_180026938
0x180026934  lea     r9, [rbp+7E0h+var_860]
0x180026938  lea     rax, [rbp+7E0h+var_850]
0x18002693c  mov     qword ptr [rsp+8E0h+Period], rax
0x180026941  mov     qword ptr [rsp+8E0h+DueTime], r8
0x180026946  lea     r8, [rbp+7E0h+var_820]
0x18002694a  lea     rdx, RasVpnIkeParamTraceError
0x180026951  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026958  call    McTemplateU0zjzz_EventWriteTransfer
0x18002695d  mov     rcx, rdi; this
0x180026960  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x180026965  jmp     loc_180026A0C
0x18002696a  test    cs:byte_1800AA941, 8
0x180026971  jz      loc_180026A0C
0x180026977  xor     eax, eax
0x180026979  mov     word ptr [rbp+7E0h+var_820], ax
0x18002697d  mov     word ptr [rbp+7E0h+var_850], ax
0x180026981  mov     rax, [rdi+70h]
0x180026985  test    rax, rax
0x180026988  jz      short loc_180026994
0x18002698a  cmp     qword ptr [rax+10h], 0
0x18002698f  jz      short loc_180026994
0x180026991  mov     esi, [rax+10h]
0x180026994  mov     edx, esi
0x180026996  lea     rcx, [rbp+7E0h+var_850]
0x18002699a  call    ConvertPortNoToString
0x18002699f  imul    r8d, [rdi+64h], 3E8h
0x1800269a7  lea     rdx, aCreatetimerque_2; "CreateTimerQueueTimer is set for sessio"...
0x1800269ae  lea     rcx, [rbp+7E0h+var_820]
0x1800269b2  call    FormatRRASErrorString
0x1800269b7  test    cs:byte_1800AA941, 8
0x1800269be  jz      short loc_180026A0C
0x1800269c0  mov     rdx, [rdi+70h]
0x1800269c4  mov     rax, rdx
0x1800269c7  lea     rcx, [rdx+0A7Eh]
0x1800269ce  neg     rax
0x1800269d1  sbb     r8, r8
0x1800269d4  and     r8, rcx
0x1800269d7  test    rdx, rdx
0x1800269da  lea     r9, [rdx+848h]
0x1800269e1  jnz     short loc_1800269E7
0x1800269e3  lea     r9, [rbp+7E0h+var_860]
0x1800269e7  lea     rax, [rbp+7E0h+var_850]
0x1800269eb  mov     qword ptr [rsp+8E0h+Period], rax
0x1800269f0  mov     qword ptr [rsp+8E0h+DueTime], r8
0x1800269f5  lea     r8, [rbp+7E0h+var_820]
0x1800269f9  lea     rdx, RasVpnIkeParamTraceInfo
0x180026a00  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026a07  call    McTemplateU0zjzz_EventWriteTransfer
0x180026a0c  mov     rbx, cs:WPP_GLOBAL_Control
0x180026a13  cmp     rbx, r12
0x180026a16  jz      short loc_180026A3E
0x180026a18  test    byte ptr [rbx+1Ch], 1
0x180026a1c  jz      short loc_180026A3E
0x180026a1e  cmp     byte ptr [rbx+19h], 6
0x180026a22  jb      short loc_180026A3E
0x180026a24  mov     edx, 44h ; 'D'
0x180026a29  mov     r9d, [rsp+8E0h+var_8A0]
0x180026a2e  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x180026a35  mov     rcx, [rbx+10h]
0x180026a39  call    WPP_SF_d
0x180026a3e  mov     ebx, [rsp+8E0h+var_8A0]
0x180026a42  lea     rcx, [rsp+8E0h+var_898]; this
0x180026a47  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180026a4c  mov     eax, ebx
0x180026a4e  mov     rcx, [rbp+7E0h+var_20]
0x180026a55  xor     rcx, rsp; StackCookie
0x180026a58  call    __security_check_cookie
0x180026a5d  lea     r11, [rsp+8E0h+var_10]
0x180026a65  mov     rbx, [r11+28h]
0x180026a69  mov     rsi, [r11+30h]
0x180026a6d  mov     rsp, r11
0x180026a70  pop     r12
0x180026a72  pop     rdi
0x180026a73  pop     rbp
0x180026a74  retn
```
