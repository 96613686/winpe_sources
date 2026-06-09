# VPNIKEServerConnection::SessionTimerStop(uchar)

- ea: `0x180026a7c`
- end: `0x180026cbd`
- name: `?SessionTimerStop@VPNIKEServerConnection@@IEAAKE@Z`
- size: `577`
- prototype: `__int64 __fastcall(void **this, char, __int64, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800227f0`
- `0x1800246a0`
- `0x1800256c4`

## callees

- `0x180007610`
- `0x1800077bc`
- `0x180007894`
- `0x180026a7c`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b9c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180026b8e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180026b8e`

## string_xrefs

- `0x180026be0`: `DeleteTimerQueueTimer failed: %d`

## pseudocode

```c
__int64 __fastcall VPNIKEServerConnection::SessionTimerStop(void **this, char a2, __int64 a3, __int64 a4)
{
  PVOID *v6; // rbx
  unsigned int v7; // r14d
  void *v8; // rdx
  DWORD LastError; // ebx
  _DWORD *v10; // rcx
  void *v11; // rdx
  __int128 *v12; // r9
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v15; // [rsp+38h] [rbp-C8h]
  __int128 v16; // [rsp+48h] [rbp-B8h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+60h] [rbp-A0h]
  int v19; // [rsp+64h] [rbp-9Ch]
  __int128 v20; // [rsp+68h] [rbp-98h] BYREF
  int v21; // [rsp+78h] [rbp-88h] BYREF
  __int128 v22; // [rsp+7Ch] [rbp-84h]
  __int128 v23; // [rsp+8Ch] [rbp-74h]
  int v24; // [rsp+9Ch] [rbp-64h]
  int v25; // [rsp+A0h] [rbp-60h] BYREF
  char v26[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a2;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids, a4);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v20 = 0;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v7 = -1;
  v18 = -1;
  v19 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v14,
      L"VPNIKEServerConnection::SessionTimerStop",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      this[14]);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = this[46];
  if ( v8 )
  {
    if ( !DeleteTimerQueueTimer(0, v8, (HANDLE)-(__int64)(a2 != 0)) )
    {
      LastError = GetLastError();
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v25) = 0;
        LOWORD(v21) = 0;
        v10 = this[14];
        if ( v10 && *((_QWORD *)v10 + 2) )
          v7 = v10[4];
        ConvertPortNoToString(&v21, v7);
        FormatRRASErrorString(&v25, L"DeleteTimerQueueTimer failed: %d", LastError);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v11 = this[14];
          LODWORD(v12) = (_DWORD)v11 + 2120;
          if ( !v11 )
            v12 = &v20;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v25,
            (_DWORD)v12,
            ((unsigned __int64)v11 + 2686) & -(__int64)(v11 != 0),
            (__int64)&v21);
        }
      }
    }
    this[46] = 0;
    BaseConnection::DeleteRef((BaseConnection *)this);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 72, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
  return 0;
}

```

## disassembly

```asm
0x180026a7c  mov     [rsp-8+arg_10], rbx
0x180026a81  push    rbp
0x180026a82  push    rsi
0x180026a83  push    rdi
0x180026a84  push    r12
0x180026a86  push    r14
0x180026a88  lea     rbp, [rsp-7B0h]
0x180026a90  sub     rsp, 8B0h
0x180026a97  mov     rax, cs:__security_cookie
0x180026a9e  xor     rax, rsp
0x180026aa1  mov     [rbp+7D0h+var_30], rax
0x180026aa8  mov     sil, dl
0x180026aab  mov     rdi, rcx
0x180026aae  lea     r12, WPP_GLOBAL_Control
0x180026ab5  mov     rbx, cs:WPP_GLOBAL_Control
0x180026abc  cmp     rbx, r12
0x180026abf  jz      short loc_180026AEC
0x180026ac1  test    byte ptr [rbx+1Ch], 1
0x180026ac5  jz      short loc_180026AEC
0x180026ac7  cmp     byte ptr [rbx+19h], 6
0x180026acb  jb      short loc_180026AEC
0x180026acd  mov     edx, 47h ; 'G'
0x180026ad2  mov     r9b, sil
0x180026ad5  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x180026adc  mov     rcx, [rbx+10h]
0x180026ae0  call    WPP_SF_c
0x180026ae5  mov     rbx, cs:WPP_GLOBAL_Control
0x180026aec  xor     eax, eax
0x180026aee  mov     [rbp+7D0h+var_830], eax
0x180026af1  xor     edx, edx; Val
0x180026af3  mov     r8d, 7FCh; Size
0x180026af9  lea     rcx, [rbp+7D0h+var_82C]; void *
0x180026afd  call    memset_0
0x180026b02  xor     eax, eax
0x180026b04  mov     [rsp+8D0h+var_858], eax
0x180026b08  xorps   xmm0, xmm0
0x180026b0b  movups  [rsp+8D0h+var_854], xmm0
0x180026b10  movups  [rbp+7D0h+var_844], xmm0
0x180026b14  mov     [rbp+7D0h+var_834], eax
0x180026b17  movups  [rsp+8D0h+var_868], xmm0
0x180026b1c  xorps   xmm1, xmm1
0x180026b1f  movdqu  [rsp+8D0h+var_898], xmm1
0x180026b25  mov     [rsp+8D0h+var_8A0], rax
0x180026b2a  movdqu  [rsp+8D0h+var_888], xmm0
0x180026b30  mov     [rsp+8D0h+var_878], rax
0x180026b35  or      r14d, 0FFFFFFFFh
0x180026b39  mov     [rsp+8D0h+var_870], r14d
0x180026b3e  mov     [rsp+8D0h+var_86C], eax
0x180026b42  test    cs:byte_1800AA941, 8
0x180026b49  jz      short loc_180026B76
0x180026b4b  mov     rax, [rdi+70h]
0x180026b4f  mov     [rsp+8D0h+var_8B0], rax; void *
0x180026b54  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180026b5b  xor     r8d, r8d; unsigned int *
0x180026b5e  lea     rdx, aVpnikeserverco_14; "VPNIKEServerConnection::SessionTimerSto"...
0x180026b65  lea     rcx, [rsp+8D0h+var_8A0]; this
0x180026b6a  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180026b6f  mov     rbx, cs:WPP_GLOBAL_Control
0x180026b76  mov     rdx, [rdi+170h]; Timer
0x180026b7d  test    rdx, rdx
0x180026b80  jz      loc_180026C61
0x180026b86  neg     sil
0x180026b89  sbb     r8, r8; CompletionEvent
0x180026b8c  xor     ecx, ecx; TimerQueue
0x180026b8e  call    cs:__imp_DeleteTimerQueueTimer
0x180026b94  test    eax, eax
0x180026b96  jnz     loc_180026C47
0x180026b9c  call    cs:__imp_GetLastError
0x180026ba2  mov     ebx, eax
0x180026ba4  test    cs:byte_1800AA941, 4
0x180026bab  jz      loc_180026C47
0x180026bb1  xor     ecx, ecx
0x180026bb3  mov     word ptr [rbp+7D0h+var_830], cx
0x180026bb7  mov     word ptr [rsp+8D0h+var_858], cx
0x180026bbc  mov     rcx, [rdi+70h]
0x180026bc0  test    rcx, rcx
0x180026bc3  jz      short loc_180026BD0
0x180026bc5  cmp     qword ptr [rcx+10h], 0
0x180026bca  jz      short loc_180026BD0
0x180026bcc  mov     r14d, [rcx+10h]
0x180026bd0  mov     edx, r14d
0x180026bd3  lea     rcx, [rsp+8D0h+var_858]
0x180026bd8  call    ConvertPortNoToString
0x180026bdd  mov     r8d, ebx
0x180026be0  lea     rdx, aDeletetimerque_0; "DeleteTimerQueueTimer failed: %d"
0x180026be7  lea     rcx, [rbp+7D0h+var_830]
0x180026beb  call    FormatRRASErrorString
0x180026bf0  test    cs:byte_1800AA941, 4
0x180026bf7  jz      short loc_180026C47
0x180026bf9  mov     rdx, [rdi+70h]
0x180026bfd  mov     rax, rdx
0x180026c00  lea     rcx, [rdx+0A7Eh]
0x180026c07  neg     rax
0x180026c0a  sbb     r8, r8
0x180026c0d  and     r8, rcx
0x180026c10  test    rdx, rdx
0x180026c13  lea     r9, [rdx+848h]
0x180026c1a  jnz     short loc_180026C21
0x180026c1c  lea     r9, [rsp+8D0h+var_868]
0x180026c21  lea     rax, [rsp+8D0h+var_858]
0x180026c26  mov     [rsp+8D0h+var_8A8], rax
0x180026c2b  mov     [rsp+8D0h+var_8B0], r8
0x180026c30  lea     r8, [rbp+7D0h+var_830]
0x180026c34  lea     rdx, RasVpnIkeParamTraceError
0x180026c3b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026c42  call    McTemplateU0zjzz_EventWriteTransfer
0x180026c47  mov     qword ptr [rdi+170h], 0
0x180026c52  mov     rcx, rdi; this
0x180026c55  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x180026c5a  mov     rbx, cs:WPP_GLOBAL_Control
0x180026c61  cmp     rbx, r12
0x180026c64  jz      short loc_180026C8B
0x180026c66  test    byte ptr [rbx+1Ch], 1
0x180026c6a  jz      short loc_180026C8B
0x180026c6c  cmp     byte ptr [rbx+19h], 6
0x180026c70  jb      short loc_180026C8B
0x180026c72  mov     edx, 48h ; 'H'
0x180026c77  xor     r9d, r9d
0x180026c7a  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x180026c81  mov     rcx, [rbx+10h]
0x180026c85  call    WPP_SF_d
0x180026c8a  nop
0x180026c8b  lea     rcx, [rsp+8D0h+var_8A0]; this
0x180026c90  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180026c95  xor     eax, eax
0x180026c97  mov     rcx, [rbp+7D0h+var_30]
0x180026c9e  xor     rcx, rsp; StackCookie
0x180026ca1  call    __security_check_cookie
0x180026ca6  mov     rbx, [rsp+8D0h+arg_10]
0x180026cae  add     rsp, 8B0h
0x180026cb5  pop     r14
0x180026cb7  pop     r12
0x180026cb9  pop     rdi
0x180026cba  pop     rsi
0x180026cbb  pop     rbp
0x180026cbc  retn
```
