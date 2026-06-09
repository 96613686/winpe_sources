# VPNIKEConnection::IdleTimerStop(uchar)

- ea: `0x18000ee60`
- end: `0x18000f098`
- name: `?IdleTimerStop@VPNIKEConnection@@QEAAKE@Z`
- size: `568`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180002e70`
- `0x18000c830`
- `0x1800246a0`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18000ee60`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef78`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000ef6a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000ef6a`

## string_xrefs

- `0x18000efba`: `DeleteTimerQueueTimer failed with %d`

## pseudocode

```c
__int64 __fastcall VPNIKEConnection::IdleTimerStop(void **this)
{
  PVOID *v2; // rbx
  unsigned int v3; // esi
  void *v4; // rdx
  DWORD LastError; // ebx
  _DWORD *v6; // rcx
  void *v7; // rdx
  __int128 *v8; // r9
  __int64 v10; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v11; // [rsp+38h] [rbp-C8h]
  __int128 v12; // [rsp+48h] [rbp-B8h]
  __int64 v13; // [rsp+58h] [rbp-A8h]
  int v14; // [rsp+60h] [rbp-A0h]
  int v15; // [rsp+64h] [rbp-9Ch]
  __int128 v16; // [rsp+68h] [rbp-98h] BYREF
  int v17; // [rsp+78h] [rbp-88h] BYREF
  __int128 v18; // [rsp+7Ch] [rbp-84h]
  __int128 v19; // [rsp+8Ch] [rbp-74h]
  int v20; // [rsp+9Ch] [rbp-64h]
  int v21; // [rsp+A0h] [rbp-60h] BYREF
  char v22[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v16 = 0;
  v11 = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  v3 = -1;
  v14 = -1;
  v15 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v10,
      L"VPNIKEConnection::IdleTimerStop",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      this[14]);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = this[31];
  if ( v4 )
  {
    if ( !DeleteTimerQueueTimer(0, v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v21) = 0;
        LOWORD(v17) = 0;
        v6 = this[14];
        if ( v6 && *((_QWORD *)v6 + 2) )
          v3 = v6[4];
        ConvertPortNoToString(&v17, v3);
        FormatRRASErrorString(&v21, L"DeleteTimerQueueTimer failed with %d", LastError);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v7 = this[14];
          LODWORD(v8) = (_DWORD)v7 + 2120;
          if ( !v7 )
            v8 = &v16;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v21,
            (_DWORD)v8,
            ((unsigned __int64)v7 + 2686) & -(__int64)(v7 != 0),
            (__int64)&v17);
        }
      }
    }
    this[31] = 0;
    BaseConnection::DeleteRef((BaseConnection *)this);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 121, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v10);
  return 0;
}

```

## disassembly

```asm
0x18000ee60  mov     [rsp-8+arg_8], rbx
0x18000ee65  mov     [rsp-8+arg_10], rsi
0x18000ee6a  push    rbp
0x18000ee6b  push    rdi
0x18000ee6c  push    r15
0x18000ee6e  lea     rbp, [rsp-7B0h]
0x18000ee76  sub     rsp, 8B0h
0x18000ee7d  mov     rax, cs:__security_cookie
0x18000ee84  xor     rax, rsp
0x18000ee87  mov     [rbp+7C0h+var_20], rax
0x18000ee8e  mov     rdi, rcx
0x18000ee91  lea     r15, WPP_GLOBAL_Control
0x18000ee98  mov     rbx, cs:WPP_GLOBAL_Control
0x18000ee9f  cmp     rbx, r15
0x18000eea2  jz      short loc_18000EECC
0x18000eea4  test    byte ptr [rbx+1Ch], 1
0x18000eea8  jz      short loc_18000EECC
0x18000eeaa  cmp     byte ptr [rbx+19h], 6
0x18000eeae  jb      short loc_18000EECC
0x18000eeb0  mov     edx, 78h ; 'x'
0x18000eeb5  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000eebc  mov     rcx, [rbx+10h]
0x18000eec0  call    WPP_SF_
0x18000eec5  mov     rbx, cs:WPP_GLOBAL_Control
0x18000eecc  xor     eax, eax
0x18000eece  mov     [rbp+7C0h+var_820], eax
0x18000eed1  xor     edx, edx; Val
0x18000eed3  mov     r8d, 7FCh; Size
0x18000eed9  lea     rcx, [rbp+7C0h+var_81C]; void *
0x18000eedd  call    memset_0
0x18000eee2  xor     eax, eax
0x18000eee4  mov     [rsp+8C0h+var_848], eax
0x18000eee8  xorps   xmm0, xmm0
0x18000eeeb  movups  [rsp+8C0h+var_844], xmm0
0x18000eef0  movups  [rbp+7C0h+var_834], xmm0
0x18000eef4  mov     [rbp+7C0h+var_824], eax
0x18000eef7  movups  [rsp+8C0h+var_858], xmm0
0x18000eefc  xorps   xmm1, xmm1
0x18000eeff  movdqu  [rsp+8C0h+var_888], xmm1
0x18000ef05  mov     [rsp+8C0h+var_890], rax
0x18000ef0a  movdqu  [rsp+8C0h+var_878], xmm0
0x18000ef10  mov     [rsp+8C0h+var_868], rax
0x18000ef15  or      esi, 0FFFFFFFFh
0x18000ef18  mov     [rsp+8C0h+var_860], esi
0x18000ef1c  mov     [rsp+8C0h+var_85C], eax
0x18000ef20  test    cs:byte_1800AA941, 8
0x18000ef27  jz      short loc_18000EF54
0x18000ef29  mov     rax, [rdi+70h]
0x18000ef2d  mov     [rsp+8C0h+var_8A0], rax; void *
0x18000ef32  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18000ef39  xor     r8d, r8d; unsigned int *
0x18000ef3c  lea     rdx, aVpnikeconnecti_3; "VPNIKEConnection::IdleTimerStop"
0x18000ef43  lea     rcx, [rsp+8C0h+var_890]; this
0x18000ef48  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18000ef4d  mov     rbx, cs:WPP_GLOBAL_Control
0x18000ef54  mov     rdx, [rdi+0F8h]; Timer
0x18000ef5b  test    rdx, rdx
0x18000ef5e  jz      loc_18000F03B
0x18000ef64  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000ef68  xor     ecx, ecx; TimerQueue
0x18000ef6a  call    cs:__imp_DeleteTimerQueueTimer
0x18000ef70  test    eax, eax
0x18000ef72  jnz     loc_18000F021
0x18000ef78  call    cs:__imp_GetLastError
0x18000ef7e  mov     ebx, eax
0x18000ef80  test    cs:byte_1800AA941, 4
0x18000ef87  jz      loc_18000F021
0x18000ef8d  xor     ecx, ecx
0x18000ef8f  mov     word ptr [rbp+7C0h+var_820], cx
0x18000ef93  mov     word ptr [rsp+8C0h+var_848], cx
0x18000ef98  mov     rcx, [rdi+70h]
0x18000ef9c  test    rcx, rcx
0x18000ef9f  jz      short loc_18000EFAB
0x18000efa1  cmp     qword ptr [rcx+10h], 0
0x18000efa6  jz      short loc_18000EFAB
0x18000efa8  mov     esi, [rcx+10h]
0x18000efab  mov     edx, esi
0x18000efad  lea     rcx, [rsp+8C0h+var_848]
0x18000efb2  call    ConvertPortNoToString
0x18000efb7  mov     r8d, ebx
0x18000efba  lea     rdx, aDeletetimerque; "DeleteTimerQueueTimer failed with %d"
0x18000efc1  lea     rcx, [rbp+7C0h+var_820]
0x18000efc5  call    FormatRRASErrorString
0x18000efca  test    cs:byte_1800AA941, 4
0x18000efd1  jz      short loc_18000F021
0x18000efd3  mov     rdx, [rdi+70h]
0x18000efd7  mov     rax, rdx
0x18000efda  lea     rcx, [rdx+0A7Eh]
0x18000efe1  neg     rax
0x18000efe4  sbb     r8, r8
0x18000efe7  and     r8, rcx
0x18000efea  test    rdx, rdx
0x18000efed  lea     r9, [rdx+848h]
0x18000eff4  jnz     short loc_18000EFFB
0x18000eff6  lea     r9, [rsp+8C0h+var_858]
0x18000effb  lea     rax, [rsp+8C0h+var_848]
0x18000f000  mov     [rsp+8C0h+var_898], rax
0x18000f005  mov     [rsp+8C0h+var_8A0], r8
0x18000f00a  lea     r8, [rbp+7C0h+var_820]
0x18000f00e  lea     rdx, RasVpnIkeParamTraceError
0x18000f015  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f01c  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f021  mov     qword ptr [rdi+0F8h], 0
0x18000f02c  mov     rcx, rdi; this
0x18000f02f  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x18000f034  mov     rbx, cs:WPP_GLOBAL_Control
0x18000f03b  cmp     rbx, r15
0x18000f03e  jz      short loc_18000F065
0x18000f040  test    byte ptr [rbx+1Ch], 1
0x18000f044  jz      short loc_18000F065
0x18000f046  cmp     byte ptr [rbx+19h], 6
0x18000f04a  jb      short loc_18000F065
0x18000f04c  mov     edx, 79h ; 'y'
0x18000f051  xor     r9d, r9d
0x18000f054  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000f05b  mov     rcx, [rbx+10h]
0x18000f05f  call    WPP_SF_d
0x18000f064  nop
0x18000f065  lea     rcx, [rsp+8C0h+var_890]; this
0x18000f06a  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18000f06f  xor     eax, eax
0x18000f071  mov     rcx, [rbp+7C0h+var_20]
0x18000f078  xor     rcx, rsp; StackCookie
0x18000f07b  call    __security_check_cookie
0x18000f080  lea     r11, [rsp+8C0h+var_10]
0x18000f088  mov     rbx, [r11+28h]
0x18000f08c  mov     rsi, [r11+30h]
0x18000f090  mov     rsp, r11
0x18000f093  pop     r15
0x18000f095  pop     rdi
0x18000f096  pop     rbp
0x18000f097  retn
```
