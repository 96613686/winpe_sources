# VPNIKEConnection::IdleTimerStart(void)

- ea: `0x18000eb54`
- end: `0x18000ee59`
- name: `?IdleTimerStart@VPNIKEConnection@@IEAAKXZ`
- size: `773`
- prototype: `__int64 __fastcall(VPNIKEConnection *this)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001a5f0`
- `0x1800246a0`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18000eb54`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec98`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000ec8a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000ec8a`

## string_xrefs

- `0x18000ecdc`: `CreateTimerQueueTimer failed: %d`
- `0x18000ed8b`: `CreateTimerQueueTimer is set for idle time out: %u`

## pseudocode

```c
__int64 __fastcall VPNIKEConnection::IdleTimerStart(VPNIKEConnection *this)
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
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
      L"VPNIKEConnection::IdleTimerStart",
      &LastError,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 14));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 24) )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 51);
    if ( CreateTimerQueueTimer(
           (PHANDLE)this + 31,
           0,
           VPNIKEConnection::IdleTimerCallback,
           this,
           1000 * *((_DWORD *)this + 24),
           1000 * *((_DWORD *)this + 24),
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
          L"CreateTimerQueueTimer is set for idle time out: %u",
          (unsigned int)(1000 * *((_DWORD *)this + 24)));
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
    WPP_SF_d(v2[2], 116, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, LastError);
  v10 = LastError;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v13);
  return v10;
}

```

## disassembly

```asm
0x18000eb54  mov     [rsp-8+arg_8], rbx
0x18000eb59  mov     [rsp-8+arg_10], rsi
0x18000eb5e  push    rbp
0x18000eb5f  push    rdi
0x18000eb60  push    r12
0x18000eb62  lea     rbp, [rsp-7D0h]
0x18000eb6a  sub     rsp, 8D0h
0x18000eb71  mov     rax, cs:__security_cookie
0x18000eb78  xor     rax, rsp
0x18000eb7b  mov     [rbp+7E0h+var_20], rax
0x18000eb82  mov     rdi, rcx
0x18000eb85  lea     r12, WPP_GLOBAL_Control
0x18000eb8c  mov     rbx, cs:WPP_GLOBAL_Control
0x18000eb93  cmp     rbx, r12
0x18000eb96  jz      short loc_18000EBC0
0x18000eb98  test    byte ptr [rbx+1Ch], 1
0x18000eb9c  jz      short loc_18000EBC0
0x18000eb9e  cmp     byte ptr [rbx+19h], 6
0x18000eba2  jb      short loc_18000EBC0
0x18000eba4  mov     edx, 73h ; 's'
0x18000eba9  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000ebb0  mov     rcx, [rbx+10h]
0x18000ebb4  call    WPP_SF_
0x18000ebb9  mov     rbx, cs:WPP_GLOBAL_Control
0x18000ebc0  mov     [rsp+8E0h+var_8A0], 0
0x18000ebc8  xor     eax, eax
0x18000ebca  mov     [rbp+7E0h+var_820], eax
0x18000ebcd  xor     edx, edx; Val
0x18000ebcf  mov     r8d, 7FCh; Size
0x18000ebd5  lea     rcx, [rbp+7E0h+var_81C]; void *
0x18000ebd9  call    memset_0
0x18000ebde  xor     eax, eax
0x18000ebe0  mov     [rbp+7E0h+var_850], eax
0x18000ebe3  xorps   xmm0, xmm0
0x18000ebe6  movups  [rbp+7E0h+var_84C], xmm0
0x18000ebea  movups  [rbp+7E0h+var_83C], xmm0
0x18000ebee  mov     [rbp+7E0h+var_82C], eax
0x18000ebf1  movups  [rbp+7E0h+var_860], xmm0
0x18000ebf5  xorps   xmm1, xmm1
0x18000ebf8  movdqu  [rsp+8E0h+var_890], xmm1
0x18000ebfe  mov     [rsp+8E0h+var_898], rax
0x18000ec03  movdqu  [rsp+8E0h+var_880], xmm0
0x18000ec09  mov     [rsp+8E0h+var_870], rax
0x18000ec0e  or      esi, 0FFFFFFFFh
0x18000ec11  mov     [rsp+8E0h+var_868], esi
0x18000ec15  mov     [rsp+8E0h+var_864], eax
0x18000ec19  test    cs:byte_1800AA941, 8
0x18000ec20  jz      short loc_18000EC4F
0x18000ec22  mov     rax, [rdi+70h]
0x18000ec26  mov     qword ptr [rsp+8E0h+DueTime], rax; void *
0x18000ec2b  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18000ec32  lea     r8, [rsp+8E0h+var_8A0]; unsigned int *
0x18000ec37  lea     rdx, aVpnikeconnecti_16; "VPNIKEConnection::IdleTimerStart"
0x18000ec3e  lea     rcx, [rsp+8E0h+var_898]; this
0x18000ec43  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18000ec48  mov     rbx, cs:WPP_GLOBAL_Control
0x18000ec4f  cmp     dword ptr [rdi+60h], 0
0x18000ec53  jz      loc_18000EDF7
0x18000ec59  lock inc dword ptr [rdi+0CCh]
0x18000ec60  imul    eax, [rdi+60h], 3E8h
0x18000ec67  lea     rcx, [rdi+0F8h]; phNewTimer
0x18000ec6e  mov     [rsp+8E0h+Flags], 20h ; ' '; Flags
0x18000ec76  mov     [rsp+8E0h+Period], eax; Period
0x18000ec7a  mov     [rsp+8E0h+DueTime], eax; DueTime
0x18000ec7e  mov     r9, rdi; Parameter
0x18000ec81  lea     r8, ?IdleTimerCallback@VPNIKEConnection@@KAXPEAXE@Z; Callback
0x18000ec88  xor     edx, edx; TimerQueue
0x18000ec8a  call    cs:__imp_CreateTimerQueueTimer
0x18000ec90  test    eax, eax
0x18000ec92  jnz     loc_18000ED4E
0x18000ec98  call    cs:__imp_GetLastError
0x18000ec9e  mov     [rsp+8E0h+var_8A0], eax
0x18000eca2  test    cs:byte_1800AA941, 4
0x18000eca9  jz      loc_18000ED41
0x18000ecaf  xor     eax, eax
0x18000ecb1  mov     word ptr [rbp+7E0h+var_820], ax
0x18000ecb5  mov     word ptr [rbp+7E0h+var_850], ax
0x18000ecb9  mov     rax, [rdi+70h]
0x18000ecbd  test    rax, rax
0x18000ecc0  jz      short loc_18000ECCC
0x18000ecc2  cmp     qword ptr [rax+10h], 0
0x18000ecc7  jz      short loc_18000ECCC
0x18000ecc9  mov     esi, [rax+10h]
0x18000eccc  mov     edx, esi
0x18000ecce  lea     rcx, [rbp+7E0h+var_850]
0x18000ecd2  call    ConvertPortNoToString
0x18000ecd7  mov     r8d, [rsp+8E0h+var_8A0]
0x18000ecdc  lea     rdx, aCreatetimerque_0; "CreateTimerQueueTimer failed: %d"
0x18000ece3  lea     rcx, [rbp+7E0h+var_820]
0x18000ece7  call    FormatRRASErrorString
0x18000ecec  test    cs:byte_1800AA941, 4
0x18000ecf3  jz      short loc_18000ED41
0x18000ecf5  mov     rdx, [rdi+70h]
0x18000ecf9  mov     rax, rdx
0x18000ecfc  lea     rcx, [rdx+0A7Eh]
0x18000ed03  neg     rax
0x18000ed06  sbb     r8, r8
0x18000ed09  and     r8, rcx
0x18000ed0c  test    rdx, rdx
0x18000ed0f  lea     r9, [rdx+848h]
0x18000ed16  jnz     short loc_18000ED1C
0x18000ed18  lea     r9, [rbp+7E0h+var_860]
0x18000ed1c  lea     rax, [rbp+7E0h+var_850]
0x18000ed20  mov     qword ptr [rsp+8E0h+Period], rax
0x18000ed25  mov     qword ptr [rsp+8E0h+DueTime], r8
0x18000ed2a  lea     r8, [rbp+7E0h+var_820]
0x18000ed2e  lea     rdx, RasVpnIkeParamTraceError
0x18000ed35  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ed3c  call    McTemplateU0zjzz_EventWriteTransfer
0x18000ed41  mov     rcx, rdi; this
0x18000ed44  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x18000ed49  jmp     loc_18000EDF0
0x18000ed4e  test    cs:byte_1800AA941, 8
0x18000ed55  jz      loc_18000EDF0
0x18000ed5b  xor     eax, eax
0x18000ed5d  mov     word ptr [rbp+7E0h+var_820], ax
0x18000ed61  mov     word ptr [rbp+7E0h+var_850], ax
0x18000ed65  mov     rax, [rdi+70h]
0x18000ed69  test    rax, rax
0x18000ed6c  jz      short loc_18000ED78
0x18000ed6e  cmp     qword ptr [rax+10h], 0
0x18000ed73  jz      short loc_18000ED78
0x18000ed75  mov     esi, [rax+10h]
0x18000ed78  mov     edx, esi
0x18000ed7a  lea     rcx, [rbp+7E0h+var_850]
0x18000ed7e  call    ConvertPortNoToString
0x18000ed83  imul    r8d, [rdi+60h], 3E8h
0x18000ed8b  lea     rdx, aCreatetimerque; "CreateTimerQueueTimer is set for idle t"...
0x18000ed92  lea     rcx, [rbp+7E0h+var_820]
0x18000ed96  call    FormatRRASErrorString
0x18000ed9b  test    cs:byte_1800AA941, 8
0x18000eda2  jz      short loc_18000EDF0
0x18000eda4  mov     rdx, [rdi+70h]
0x18000eda8  mov     rax, rdx
0x18000edab  lea     rcx, [rdx+0A7Eh]
0x18000edb2  neg     rax
0x18000edb5  sbb     r8, r8
0x18000edb8  and     r8, rcx
0x18000edbb  test    rdx, rdx
0x18000edbe  lea     r9, [rdx+848h]
0x18000edc5  jnz     short loc_18000EDCB
0x18000edc7  lea     r9, [rbp+7E0h+var_860]
0x18000edcb  lea     rax, [rbp+7E0h+var_850]
0x18000edcf  mov     qword ptr [rsp+8E0h+Period], rax
0x18000edd4  mov     qword ptr [rsp+8E0h+DueTime], r8
0x18000edd9  lea     r8, [rbp+7E0h+var_820]
0x18000eddd  lea     rdx, RasVpnIkeParamTraceInfo
0x18000ede4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000edeb  call    McTemplateU0zjzz_EventWriteTransfer
0x18000edf0  mov     rbx, cs:WPP_GLOBAL_Control
0x18000edf7  cmp     rbx, r12
0x18000edfa  jz      short loc_18000EE22
0x18000edfc  test    byte ptr [rbx+1Ch], 1
0x18000ee00  jz      short loc_18000EE22
0x18000ee02  cmp     byte ptr [rbx+19h], 6
0x18000ee06  jb      short loc_18000EE22
0x18000ee08  mov     edx, 74h ; 't'
0x18000ee0d  mov     r9d, [rsp+8E0h+var_8A0]
0x18000ee12  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000ee19  mov     rcx, [rbx+10h]
0x18000ee1d  call    WPP_SF_d
0x18000ee22  mov     ebx, [rsp+8E0h+var_8A0]
0x18000ee26  lea     rcx, [rsp+8E0h+var_898]; this
0x18000ee2b  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18000ee30  mov     eax, ebx
0x18000ee32  mov     rcx, [rbp+7E0h+var_20]
0x18000ee39  xor     rcx, rsp; StackCookie
0x18000ee3c  call    __security_check_cookie
0x18000ee41  lea     r11, [rsp+8E0h+var_10]
0x18000ee49  mov     rbx, [r11+28h]
0x18000ee4d  mov     rsi, [r11+30h]
0x18000ee51  mov     rsp, r11
0x18000ee54  pop     r12
0x18000ee56  pop     rdi
0x18000ee57  pop     rbp
0x18000ee58  retn
```
