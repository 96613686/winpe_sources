# CMediaUiRequestSubscriber::DoSubscribe(long (*)(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong),void *)

- ea: `0x18005dde8`
- end: `0x18005df97`
- name: `?DoSubscribe@CMediaUiRequestSubscriber@@AEAAJP6AJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z2@Z`
- size: `431`
- prototype: `__int64 __fastcall(CMediaUiRequestSubscriber *__hidden this, int (*)(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180032a68`

## callees

- `0x180019a20`
- `0x18001a5bc`
- `0x18005dde8`
- `0x18005dfa0`
- `0x1800600d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005de27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005de27`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18005de33`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18005de33`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18005df34`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18005df34`
- `ntdll!NtQueryWnfStateData` at `0x18005dec8`
- `ntdll!NtQueryWnfStateData` at `0x18005dec8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005de67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005de67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005de7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005df47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005df5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005de7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005df47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005df5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005de3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005de3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMediaUiRequestSubscriber::DoSubscribe(
        CMediaUiRequestSubscriber *this,
        int (*a2)(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int),
        void *a3)
{
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  struct _WNF_STATE_NAME v8; // rdx
  int v9; // ebx
  unsigned int v10; // r8d
  struct _WNF_TYPE_ID *v11; // r9
  unsigned int v13; // [rsp+44h] [rbp-1044h] BYREF
  char *v14; // [rsp+48h] [rbp-1040h]
  _BYTE v15[4096]; // [rsp+50h] [rbp-1038h] BYREF

  if ( *((_BYTE *)this + 16) || *((_DWORD *)this + 5) )
  {
    v7 = -2147019873;
    goto LABEL_16;
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, (DWORD *)this + 6) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_12;
  }
  v14 = (char *)this + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *((_BYTE *)this + 16) )
  {
    v7 = -2147019873;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
LABEL_16:
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
    return v7;
  }
  v13 = 0;
  memset_0(v15, 0, sizeof(v15));
  v9 = NtQueryWnfStateData(this, 0, 0, &v13);
  if ( v9 >= 0 )
  {
    *((_QWORD *)this + 9) = CWlanSSODialogSink::WnfMediaUiRequestCallback;
    *((_QWORD *)this + 10) = a3;
    v9 = CMediaUiRequestSubscriber::InterfaceMappingCallback(this, v8, v10, v11, v15, v15, 0x1000u);
    if ( v9 >= 0 )
    {
      v9 = RtlSubscribeWnfStateChangeNotification(
             (char *)this + 8,
             *(_QWORD *)this,
             v13,
             CMediaUiRequestSubscriber::InterfaceMappingCallbackThunk,
             this,
             0,
             0,
             4);
      if ( v9 >= 0 )
      {
        v7 = 0;
        *((_BYTE *)this + 16) = 1;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
        return v7;
      }
    }
  }
  v7 = v9 | 0x10000000;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
LABEL_12:
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_16;
  return v7;
}

```

## disassembly

```asm
0x18005dde8  push    rbx
0x18005ddea  push    rbp
0x18005ddeb  push    rsi
0x18005ddec  push    rdi
0x18005dded  mov     eax, 1068h
0x18005ddf2  call    _alloca_probe
0x18005ddf7  sub     rsp, rax
0x18005ddfa  mov     rax, cs:__security_cookie
0x18005de01  xor     rax, rsp
0x18005de04  mov     [rsp+1088h+var_38], rax
0x18005de0c  mov     rbp, r8
0x18005de0f  mov     rdi, rcx
0x18005de12  cmp     byte ptr [rcx+10h], 0
0x18005de16  jnz     loc_18005DF64
0x18005de1c  mov     eax, [rcx+14h]
0x18005de1f  test    eax, eax
0x18005de21  jnz     loc_18005DF64
0x18005de27  call    cs:__imp_GetCurrentProcessId
0x18005de2d  lea     rdx, [rdi+18h]; pSessionId
0x18005de31  mov     ecx, eax; dwProcessId
0x18005de33  call    cs:__imp_ProcessIdToSessionId
0x18005de39  test    eax, eax
0x18005de3b  jnz     short loc_18005DE5B
0x18005de3d  call    cs:__imp_GetLastError
0x18005de43  mov     ebx, eax
0x18005de45  test    eax, eax
0x18005de47  jle     loc_18005DF4D
0x18005de4d  movzx   ebx, ax
0x18005de50  or      ebx, 80070000h
0x18005de56  jmp     loc_18005DF4D
0x18005de5b  lea     rsi, [rdi+20h]
0x18005de5f  mov     [rsp+1088h+var_1040], rsi
0x18005de64  mov     rcx, rsi; lpCriticalSection
0x18005de67  call    cs:__imp_EnterCriticalSection
0x18005de6d  nop
0x18005de6e  cmp     byte ptr [rdi+10h], 0
0x18005de72  jz      short loc_18005DE87
0x18005de74  mov     ebx, 8007139Fh
0x18005de79  mov     rcx, rsi; lpCriticalSection
0x18005de7c  call    cs:__imp_LeaveCriticalSection
0x18005de82  jmp     loc_18005DF69
0x18005de87  mov     [rsp+1088h+var_1044], 0
0x18005de8f  mov     ebx, 1000h
0x18005de94  mov     r8d, ebx; Size
0x18005de97  xor     edx, edx; Val
0x18005de99  lea     rcx, [rsp+1088h+var_1038]; void *
0x18005de9e  call    memset_0
0x18005dea3  mov     [rsp+1088h+var_1048], ebx
0x18005dea7  lea     rax, [rsp+1088h+var_1048]
0x18005deac  mov     [rsp+1088h+var_1060], rax
0x18005deb1  lea     rax, [rsp+1088h+var_1038]
0x18005deb6  mov     [rsp+1088h+var_1068], rax; void *
0x18005debb  lea     r9, [rsp+1088h+var_1044]
0x18005dec0  xor     r8d, r8d
0x18005dec3  xor     edx, edx
0x18005dec5  mov     rcx, rdi
0x18005dec8  call    cs:__imp_NtQueryWnfStateData
0x18005dece  mov     ebx, eax
0x18005ded0  test    eax, eax
0x18005ded2  js      short loc_18005DF40
0x18005ded4  lea     rax, ?WnfMediaUiRequestCallback@CWlanSSODialogSink@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CWlanSSODialogSink::WnfMediaUiRequestCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18005dedb  mov     [rdi+48h], rax
0x18005dedf  mov     [rdi+50h], rbp
0x18005dee3  mov     eax, [rsp+1088h+var_1048]
0x18005dee7  mov     [rsp+1088h+var_1058], eax; unsigned int
0x18005deeb  lea     rax, [rsp+1088h+var_1038]
0x18005def0  mov     [rsp+1088h+var_1060], rax; void *
0x18005def5  mov     rcx, rdi; this
0x18005def8  call    ?InterfaceMappingCallback@CMediaUiRequestSubscriber@@AEAAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CMediaUiRequestSubscriber::InterfaceMappingCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18005defd  mov     ebx, eax
0x18005deff  test    eax, eax
0x18005df01  js      short loc_18005DF40
0x18005df03  lea     rcx, [rdi+8]
0x18005df07  mov     [rsp+1088h+var_1050], 4
0x18005df0f  mov     [rsp+1088h+var_1058], 0
0x18005df17  mov     [rsp+1088h+var_1060], 0
0x18005df20  mov     [rsp+1088h+var_1068], rdi
0x18005df25  lea     r9, ?InterfaceMappingCallbackThunk@CMediaUiRequestSubscriber@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CMediaUiRequestSubscriber::InterfaceMappingCallbackThunk(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18005df2c  mov     r8d, [rsp+1088h+var_1044]
0x18005df31  mov     rdx, [rdi]
0x18005df34  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18005df3a  mov     ebx, eax
0x18005df3c  test    eax, eax
0x18005df3e  jns     short loc_18005DF53
0x18005df40  bts     ebx, 1Ch
0x18005df44  mov     rcx, rsi; lpCriticalSection
0x18005df47  call    cs:__imp_LeaveCriticalSection
0x18005df4d  test    ebx, ebx
0x18005df4f  jns     short loc_18005DF79
0x18005df51  jmp     short loc_18005DF69
0x18005df53  xor     ebx, ebx
0x18005df55  mov     byte ptr [rdi+10h], 1
0x18005df59  mov     rcx, rsi; lpCriticalSection
0x18005df5c  call    cs:__imp_LeaveCriticalSection
0x18005df62  jmp     short loc_18005DF79
0x18005df64  mov     ebx, 8007139Fh
0x18005df69  mov     qword ptr [rdi+48h], 0
0x18005df71  mov     qword ptr [rdi+50h], 0
0x18005df79  mov     eax, ebx
0x18005df7b  mov     rcx, [rsp+1088h+var_38]
0x18005df83  xor     rcx, rsp; StackCookie
0x18005df86  call    __security_check_cookie
0x18005df8b  add     rsp, 1068h
0x18005df92  pop     rdi
0x18005df93  pop     rsi
0x18005df94  pop     rbp
0x18005df95  pop     rbx
0x18005df96  retn
```
