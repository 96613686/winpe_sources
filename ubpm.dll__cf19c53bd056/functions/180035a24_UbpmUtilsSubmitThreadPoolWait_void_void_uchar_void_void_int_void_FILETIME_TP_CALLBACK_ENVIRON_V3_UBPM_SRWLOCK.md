# UbpmUtilsSubmitThreadPoolWait(void (*)(void *,uchar,void *),void *,int,void *,_FILETIME *,_TP_CALLBACK_ENVIRON_V3 *,_UBPM_SRWLOCK *)

- ea: `0x180035a24`
- end: `0x180035bae`
- name: `?UbpmUtilsSubmitThreadPoolWait@@YAKP6AXPEAXE0@Z0H0PEAU_FILETIME@@PEAU_TP_CALLBACK_ENVIRON_V3@@PEAU_UBPM_SRWLOCK@@@Z`
- size: `394`
- prototype: `unsigned int(void (*)(void *, unsigned __int8, void *), void *, int, void *, struct _FILETIME *, struct _TP_CALLBACK_ENVIRON_V3 *, struct _UBPM_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800343b0`

## callees

- `0x18000f9a0`
- `0x180019d90`
- `0x180026fac`
- `0x180032e38`
- `0x180035a24`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180035b95`
- `ntdll!RtlReleaseSRWLockShared` at `0x180035b95`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180035b31`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180035b31`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180035b88`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180035b88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b3c`

## pseudocode

```c
__int64 __fastcall UbpmUtilsSubmitThreadPoolWait(
        void (*a1)(void *, unsigned __int8, void *),
        void *a2,
        __int64 a3,
        void *a4)
{
  _DWORD *v6; // rdi
  DWORD LastError; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  struct _TP_WAIT *ThreadpoolWait; // rax
  unsigned int v14; // [rsp+60h] [rbp+18h] BYREF

  v14 = 0;
  v6 = UbpmAlloc(0x30u);
  if ( !v6 )
  {
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 32;
LABEL_5:
      WPP_SF_d(v8[2], v9, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
      goto LABEL_21;
    }
    goto LABEL_21;
  }
  UBPM_TRY_ACQUIRE_SRWLOCK_SHARED((struct _UBPM_SRWLOCK *)&g_TpSubmitLock, &v14);
  LastError = v14;
  if ( !v14 )
  {
    if ( g_pThreadpool )
    {
      ThreadpoolWait = CreateThreadpoolWait(UbpmUtilsWaitCallback, v6, &g_CallbackEnv);
      if ( ThreadpoolWait )
      {
        *((_BYTE *)v6 + 24) |= 1u;
        *((_QWORD *)v6 + 2) = UbpmpRegistryChangeCallback;
        *v6 = 1886667349;
        *((_QWORD *)v6 + 1) = a2;
        v6 = 0;
        SetThreadpoolWait(ThreadpoolWait, a4, 0);
        goto LABEL_20;
      }
      LastError = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v11 = 35;
    }
    else
    {
      LastError = 1115;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v11 = 34;
    }
    WPP_SF_d(v10[2], v11, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
LABEL_20:
    RtlReleaseSRWLockShared(&g_TpSubmitLock);
    goto LABEL_21;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 33;
    goto LABEL_5;
  }
LABEL_21:
  UBPM_MIDL_user_free(v6);
  return LastError;
}

```

## disassembly

```asm
0x180035a24  mov     [rsp+arg_10], r8d
0x180035a29  push    rbx
0x180035a2a  push    rbp
0x180035a2b  push    rsi
0x180035a2c  push    rdi
0x180035a2d  sub     rsp, 28h
0x180035a31  mov     ecx, 30h ; '0'; Size
0x180035a36  mov     [rsp+48h+arg_10], 0
0x180035a3e  mov     rsi, r9
0x180035a41  mov     rbp, rdx
0x180035a44  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180035a49  mov     rdi, rax
0x180035a4c  test    rax, rax
0x180035a4f  jnz     short loc_180035A95
0x180035a51  call    cs:__imp_GetLastError
0x180035a57  mov     ebx, eax
0x180035a59  mov     rcx, cs:WPP_GLOBAL_Control
0x180035a60  lea     rax, WPP_GLOBAL_Control
0x180035a67  cmp     rcx, rax
0x180035a6a  jz      loc_180035B9B
0x180035a70  test    byte ptr [rcx+1Ch], 1
0x180035a74  jz      loc_180035B9B
0x180035a7a  lea     edx, [rdi+20h]
0x180035a7d  mov     rcx, [rcx+10h]
0x180035a81  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180035a88  mov     r9d, ebx
0x180035a8b  call    WPP_SF_d
0x180035a90  jmp     loc_180035B9B
0x180035a95  lea     rdx, [rsp+48h+arg_10]; unsigned int *
0x180035a9a  lea     rcx, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; struct _UBPM_SRWLOCK *
0x180035aa1  call    ?UBPM_TRY_ACQUIRE_SRWLOCK_SHARED@@YAXAEAU_UBPM_SRWLOCK@@PEAK@Z; UBPM_TRY_ACQUIRE_SRWLOCK_SHARED(_UBPM_SRWLOCK &,ulong *)
0x180035aa6  mov     ebx, [rsp+48h+arg_10]
0x180035aaa  test    ebx, ebx
0x180035aac  jz      short loc_180035AD6
0x180035aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ab5  lea     rax, WPP_GLOBAL_Control
0x180035abc  cmp     rcx, rax
0x180035abf  jz      loc_180035B9B
0x180035ac5  test    byte ptr [rcx+1Ch], 1
0x180035ac9  jz      loc_180035B9B
0x180035acf  mov     edx, 21h ; '!'
0x180035ad4  jmp     short loc_180035A7D
0x180035ad6  cmp     cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA, 0; _TP_POOL * g_pThreadpool
0x180035ade  jnz     short loc_180035B20
0x180035ae0  mov     ebx, 45Bh
0x180035ae5  mov     rcx, cs:WPP_GLOBAL_Control
0x180035aec  lea     rax, WPP_GLOBAL_Control
0x180035af3  cmp     rcx, rax
0x180035af6  jz      loc_180035B8E
0x180035afc  test    byte ptr [rcx+1Ch], 1
0x180035b00  jz      loc_180035B8E
0x180035b06  mov     edx, 22h ; '"'
0x180035b0b  mov     rcx, [rcx+10h]
0x180035b0f  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180035b16  mov     r9d, ebx
0x180035b19  call    WPP_SF_d
0x180035b1e  jmp     short loc_180035B8E
0x180035b20  lea     r8, ?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180035b27  mov     rdx, rdi; pv
0x180035b2a  lea     rcx, ?UbpmUtilsWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180035b31  call    cs:__imp_CreateThreadpoolWait
0x180035b37  test    rax, rax
0x180035b3a  jnz     short loc_180035B64
0x180035b3c  call    cs:__imp_GetLastError
0x180035b42  mov     ebx, eax
0x180035b44  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b4b  lea     rax, WPP_GLOBAL_Control
0x180035b52  cmp     rcx, rax
0x180035b55  jz      short loc_180035B8E
0x180035b57  test    byte ptr [rcx+1Ch], 1
0x180035b5b  jz      short loc_180035B8E
0x180035b5d  mov     edx, 23h ; '#'
0x180035b62  jmp     short loc_180035B0B
0x180035b64  or      byte ptr [rdi+18h], 1
0x180035b68  lea     rdx, ?UbpmpRegistryChangeCallback@@YAXPEAXE0@Z; UbpmpRegistryChangeCallback(void *,uchar,void *)
0x180035b6f  mov     [rdi+10h], rdx
0x180035b73  xor     r8d, r8d; pftTimeout
0x180035b76  mov     dword ptr [rdi], 70744255h
0x180035b7c  mov     rdx, rsi; h
0x180035b7f  mov     [rdi+8], rbp
0x180035b83  mov     rcx, rax; pwa
0x180035b86  xor     edi, edi
0x180035b88  call    cs:__imp_SetThreadpoolWait
0x180035b8e  lea     rcx, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TpSubmitLock
0x180035b95  call    cs:__imp_RtlReleaseSRWLockShared
0x180035b9b  mov     rcx, rdi
0x180035b9e  call    UBPM_MIDL_user_free
0x180035ba3  mov     eax, ebx
0x180035ba5  add     rsp, 28h
0x180035ba9  pop     rdi
0x180035baa  pop     rsi
0x180035bab  pop     rbp
0x180035bac  pop     rbx
0x180035bad  retn
```
