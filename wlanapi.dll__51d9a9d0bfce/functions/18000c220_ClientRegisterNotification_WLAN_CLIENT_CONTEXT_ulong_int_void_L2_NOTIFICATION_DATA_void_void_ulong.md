# ClientRegisterNotification(_WLAN_CLIENT_CONTEXT *,ulong,int,void (*)(_L2_NOTIFICATION_DATA *,void *),void *,ulong *)

- ea: `0x18000c220`
- end: `0x18000c5aa`
- name: `?ClientRegisterNotification@@YAKPEAU_WLAN_CLIENT_CONTEXT@@KHP6AXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z2PEAK@Z`
- size: `906`
- prototype: `unsigned int __usercall@<eax>(struct _WLAN_CLIENT_CONTEXT *@<rcx>, unsigned int@<edx>, int@<r8d>, void (*)(struct _L2_NOTIFICATION_DATA *, void *)@<r9>, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015580`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x18000c220`
- `0x18000c5b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c2b7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c2b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c274`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c46f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c274`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c46f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c490`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c490`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c3be`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c3be`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c292`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c292`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c3da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c3da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3e3`
- `RPCRT4!NdrClientCall3` at `0x18000c30a`
- `RPCRT4!NdrClientCall3` at `0x18000c30a`
- `RPCRT4!RpcExceptionFilter` at `0x18006064e`
- `RPCRT4!RpcExceptionFilter` at `0x18006064e`

## pseudocode

```c
__int64 __fastcall ClientRegisterNotification(
        struct _WLAN_CLIENT_CONTEXT *a1,
        unsigned int a2,
        __int64 a3,
        void (*a4)(struct _L2_NOTIFICATION_DATA *, void *),
        void *a5,
        unsigned int *Simple)
{
  DWORD LastError; // ebx
  union DOT11_OUI_HEADER *v9; // rcx
  struct _RTL_CRITICAL_SECTION *v10; // r14
  void **v11; // r15
  HANDLE Thread; // rax
  CLIENT_CALL_RETURN v13; // rax
  union DOT11_OUI_HEADER *v14; // rcx
  void *v15; // r13
  __int64 dwCreationFlags; // [rsp+20h] [rbp-68h]
  unsigned int v18; // [rsp+A0h] [rbp+18h] BYREF
  void (*v19)(struct _L2_NOTIFICATION_DATA *, void *); // [rsp+A8h] [rbp+20h]

  v19 = a4;
  LastError = 0;
  v18 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v9 + 105) >= 4u
      && (*((_BYTE *)v9 + 108) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v9 + 12), 26, WPP_797f1b088bb039a5f91226960c081484_Traceguids, a2);
    }
  }
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 168);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 168));
  v11 = (void **)((char *)a1 + 216);
  if ( !*((_QWORD *)a1 + 27) )
  {
    ResetEvent(*((HANDLE *)a1 + 26));
    *((_DWORD *)a1 + 39) = 0;
    Thread = CreateThread(0, 0, NotificationApcThreadProc, a1, 0, 0);
    *v11 = Thread;
    if ( Thread )
      *((_QWORD *)a1 + 12) = Thread;
    else
      LastError = GetLastError();
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 168));
  if ( LastError )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_797f1b088bb039a5f91226960c081484_Traceguids, LastError);
      v14 = WPP_GLOBAL_Control;
    }
LABEL_8:
    if ( !LastError )
      goto LABEL_14;
    goto LABEL_9;
  }
  Simple = 0;
  LODWORD(dwCreationFlags) = a2;
  v13.Pointer = NdrClientCall3(
                  (MIDL_STUBLESS_PROXY_INFO *)&winwlan_ProxyInfo,
                  0x16u,
                  0,
                  *(_QWORD *)a1,
                  dwCreationFlags,
                  &v18).Pointer;
  LastError = (DWORD)v13.Pointer;
  Simple = (unsigned int *)v13.Simple;
  v14 = WPP_GLOBAL_Control;
  if ( LODWORD(v13.Pointer) == 1717
    || LODWORD(v13.Pointer) == 1702
    || LODWORD(v13.Pointer) == 1726
    || LODWORD(v13.Pointer) == 1753 )
  {
    LastError = 1062;
    goto LABEL_8;
  }
  if ( !LODWORD(v13.Pointer) )
  {
    EnterCriticalSection(v10);
    *((_QWORD *)a1 + 3) = v19;
    *((_QWORD *)a1 + 4) = a5;
    LeaveCriticalSection(v10);
    LastError = ClientGetNotification(a1);
    v14 = WPP_GLOBAL_Control;
    goto LABEL_8;
  }
LABEL_9:
  v15 = 0;
  EnterCriticalSection(v10);
  if ( *v11 )
  {
    v15 = *v11;
    *v11 = 0;
    SetEvent(*((HANDLE *)a1 + 26));
  }
  LeaveCriticalSection(v10);
  if ( v15 )
  {
    WaitForSingleObject(v15, 0xFFFFFFFF);
    CloseHandle(v15);
  }
  v14 = WPP_GLOBAL_Control;
LABEL_14:
  if ( v14 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)v14 + 105) >= 4u && (*((_BYTE *)v14 + 108) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v14 + 12), 29, WPP_797f1b088bb039a5f91226960c081484_Traceguids, v18);
      v14 = WPP_GLOBAL_Control;
    }
    if ( v14 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v14 + 105) >= 4u
      && (*((_BYTE *)v14 + 108) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v14 + 12), 30, WPP_797f1b088bb039a5f91226960c081484_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18000c220  mov     rax, rsp
0x18000c223  mov     [rax+20h], r9
0x18000c227  mov     [rax+18h], r8d
0x18000c22b  mov     [rax+8], rcx
0x18000c22f  push    rbx
0x18000c230  push    rsi
0x18000c231  push    rdi
0x18000c232  push    r12
0x18000c234  push    r13
0x18000c236  push    r14
0x18000c238  push    r15
0x18000c23a  sub     rsp, 50h
0x18000c23e  mov     r13d, edx
0x18000c241  mov     rsi, rcx
0x18000c244  xor     r12d, r12d
0x18000c247  mov     ebx, r12d
0x18000c24a  mov     [rax+18h], r12d
0x18000c24e  lea     rdi, WPP_GLOBAL_Control
0x18000c255  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c25c  cmp     rcx, rdi
0x18000c25f  jnz     loc_18000C420
0x18000c265  lea     r14, [rsi+0A8h]
0x18000c26c  mov     [rsp+88h+var_50], r14
0x18000c271  mov     rcx, r14; lpCriticalSection
0x18000c274  call    cs:__imp_EnterCriticalSection
0x18000c27a  lea     r15, [rsi+0D8h]
0x18000c281  mov     [rsp+88h+var_48], r15
0x18000c286  cmp     [r15], rbx
0x18000c289  jnz     short loc_18000C2CD
0x18000c28b  mov     rcx, [rsi+0D0h]; hEvent
0x18000c292  call    cs:__imp_ResetEvent
0x18000c298  mov     [rsi+9Ch], r12d
0x18000c29f  mov     [rsp+88h+lpThreadId], r12; lpThreadId
0x18000c2a4  mov     dword ptr [rsp+88h+dwCreationFlags], r12d; dwCreationFlags
0x18000c2a9  mov     r9, rsi; lpParameter
0x18000c2ac  lea     r8, ?NotificationApcThreadProc@@YAKPEAX@Z; lpStartAddress
0x18000c2b3  xor     edx, edx; dwStackSize
0x18000c2b5  xor     ecx, ecx; lpThreadAttributes
0x18000c2b7  call    cs:__imp_CreateThread
0x18000c2bd  mov     [r15], rax
0x18000c2c0  test    rax, rax
0x18000c2c3  jz      loc_18000C4D7
0x18000c2c9  mov     [rsi+60h], rax
0x18000c2cd  mov     rcx, r14; lpCriticalSection
0x18000c2d0  call    cs:__imp_LeaveCriticalSection
0x18000c2d6  test    ebx, ebx
0x18000c2d8  jnz     loc_18000C4E4
0x18000c2de  mov     [rsp+88h+arg_28], r12
0x18000c2e6  lea     rax, [rsp+88h+arg_10]
0x18000c2ee  mov     [rsp+88h+lpThreadId], rax
0x18000c2f3  mov     dword ptr [rsp+88h+dwCreationFlags], r13d
0x18000c2f8  mov     r9, [rsi]
0x18000c2fb  xor     r8d, r8d; pReturnValue
0x18000c2fe  mov     edx, 16h; nProcNum
0x18000c303  lea     rcx, ?winwlan_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000c30a  call    cs:__imp_NdrClientCall3
0x18000c310  mov     rbx, rax
0x18000c313  mov     [rsp+88h+arg_28], rax
0x18000c31b  mov     [rsp+88h+var_58], eax
0x18000c31f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c326  jmp     short loc_18000C388
0x18000c328  mov     ebx, eax
0x18000c32a  mov     [rsp+88h+var_58], eax
0x18000c32e  lea     rdx, WPP_GLOBAL_Control
0x18000c335  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c33c  cmp     rcx, rdx
0x18000c33f  jz      short loc_18000C36C
0x18000c341  cmp     byte ptr [rcx+69h], 1
0x18000c345  jb      short loc_18000C36C
0x18000c347  test    byte ptr [rcx+6Ch], 2
0x18000c34b  jz      short loc_18000C36C
0x18000c34d  mov     edx, 1Ch
0x18000c352  mov     r9d, eax
0x18000c355  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000c35c  mov     rcx, [rcx+60h]
0x18000c360  call    WPP_SF_d
0x18000c365  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c36c  xor     r12d, r12d
0x18000c36f  lea     rdi, WPP_GLOBAL_Control
0x18000c376  mov     rsi, [rsp+88h+arg_0]
0x18000c37e  mov     r14, [rsp+88h+var_50]
0x18000c383  mov     r15, [rsp+88h+var_48]
0x18000c388  cmp     ebx, 6B5h
0x18000c38e  jnz     loc_18000C52C
0x18000c394  mov     ebx, 426h
0x18000c399  test    ebx, ebx
0x18000c39b  jz      short loc_18000C3F0
0x18000c39d  mov     r13, r12
0x18000c3a0  mov     rcx, r14; lpCriticalSection
0x18000c3a3  call    cs:__imp_EnterCriticalSection
0x18000c3a9  mov     rax, [r15]
0x18000c3ac  test    rax, rax
0x18000c3af  jz      short loc_18000C3C4
0x18000c3b1  mov     r13, rax
0x18000c3b4  mov     [r15], r12
0x18000c3b7  mov     rcx, [rsi+0D0h]; hEvent
0x18000c3be  call    cs:__imp_SetEvent
0x18000c3c4  mov     rcx, r14; lpCriticalSection
0x18000c3c7  call    cs:__imp_LeaveCriticalSection
0x18000c3cd  test    r13, r13
0x18000c3d0  jz      short loc_18000C3E9
0x18000c3d2  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000c3d7  mov     rcx, r13; hHandle
0x18000c3da  call    cs:__imp_WaitForSingleObject
0x18000c3e0  mov     rcx, r13; hObject
0x18000c3e3  call    cs:__imp_CloseHandle
0x18000c3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3f0  cmp     rcx, rdi
0x18000c3f3  jz      short loc_18000C40E
0x18000c3f5  cmp     byte ptr [rcx+69h], 4
0x18000c3f9  jnb     loc_18000C550
0x18000c3ff  cmp     rcx, rdi
0x18000c402  jz      short loc_18000C40E
0x18000c404  cmp     byte ptr [rcx+69h], 4
0x18000c408  jnb     loc_18000C583
0x18000c40e  mov     eax, ebx
0x18000c410  add     rsp, 50h
0x18000c414  pop     r15
0x18000c416  pop     r14
0x18000c418  pop     r13
0x18000c41a  pop     r12
0x18000c41c  pop     rdi
0x18000c41d  pop     rsi
0x18000c41e  pop     rbx
0x18000c41f  retn
0x18000c420  cmp     byte ptr [rcx+69h], 4
0x18000c424  jnb     loc_18000C4AC
0x18000c42a  cmp     rcx, rdi
0x18000c42d  jz      loc_18000C265
0x18000c433  cmp     byte ptr [rcx+69h], 4
0x18000c437  jb      loc_18000C265
0x18000c43d  test    byte ptr [rcx+6Ch], 2
0x18000c441  jz      loc_18000C265
0x18000c447  mov     edx, 1Ah
0x18000c44c  mov     r9d, r13d
0x18000c44f  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000c456  mov     rcx, [rcx+60h]
0x18000c45a  call    WPP_SF_d
0x18000c45f  jmp     loc_18000C265
0x18000c464  test    ebx, ebx
0x18000c466  jnz     loc_18000C39D
0x18000c46c  mov     rcx, r14; lpCriticalSection
0x18000c46f  call    cs:__imp_EnterCriticalSection
0x18000c475  mov     rax, [rsp+88h+arg_18]
0x18000c47d  mov     [rsi+18h], rax
0x18000c481  mov     rax, [rsp+88h+arg_20]
0x18000c489  mov     [rsi+20h], rax
0x18000c48d  mov     rcx, r14; lpCriticalSection
0x18000c490  call    cs:__imp_LeaveCriticalSection
0x18000c496  mov     rcx, rsi; struct _WLAN_CLIENT_CONTEXT *
0x18000c499  call    ?ClientGetNotification@@YAKPEAU_WLAN_CLIENT_CONTEXT@@@Z; ClientGetNotification(_WLAN_CLIENT_CONTEXT *)
0x18000c49e  mov     ebx, eax
0x18000c4a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4a7  jmp     loc_18000C399
0x18000c4ac  test    byte ptr [rcx+6Ch], 2
0x18000c4b0  jz      loc_18000C42A
0x18000c4b6  mov     edx, 19h
0x18000c4bb  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000c4c2  mov     rcx, [rcx+60h]
0x18000c4c6  call    WPP_SF_
0x18000c4cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4d2  jmp     loc_18000C42A
0x18000c4d7  call    cs:__imp_GetLastError
0x18000c4dd  mov     ebx, eax
0x18000c4df  jmp     loc_18000C2CD
0x18000c4e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4eb  cmp     rcx, rdi
0x18000c4ee  jz      loc_18000C399
0x18000c4f4  cmp     byte ptr [rcx+69h], 4
0x18000c4f8  jb      loc_18000C399
0x18000c4fe  test    byte ptr [rcx+6Ch], 2
0x18000c502  jz      loc_18000C399
0x18000c508  mov     edx, 1Bh
0x18000c50d  mov     r9d, ebx
0x18000c510  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000c517  mov     rcx, [rcx+60h]
0x18000c51b  call    WPP_SF_d
0x18000c520  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c527  jmp     loc_18000C399
0x18000c52c  mov     eax, ebx
0x18000c52e  sub     eax, 6A6h
0x18000c533  jz      loc_18000C394
0x18000c539  sub     eax, 18h
0x18000c53c  jz      loc_18000C394
0x18000c542  cmp     eax, 1Bh
0x18000c545  jz      loc_18000C394
0x18000c54b  jmp     loc_18000C464
0x18000c550  test    byte ptr [rcx+6Ch], 2
0x18000c554  jz      loc_18000C3FF
0x18000c55a  mov     edx, 1Dh
0x18000c55f  mov     r9d, [rsp+88h+arg_10]
0x18000c567  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000c56e  mov     rcx, [rcx+60h]
0x18000c572  call    WPP_SF_d
0x18000c577  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c57e  jmp     loc_18000C3FF
0x18000c583  test    byte ptr [rcx+6Ch], 2
0x18000c587  jz      loc_18000C40E
0x18000c58d  mov     edx, 1Eh
0x18000c592  mov     r9d, ebx
0x18000c595  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000c59c  mov     rcx, [rcx+60h]
0x18000c5a0  call    WPP_SF_d
0x18000c5a5  jmp     loc_18000C40E
0x180060640  push    rbp
0x180060642  sub     rsp, 30h
0x180060646  mov     rbp, rdx
0x180060649  mov     rcx, [rcx]
0x18006064c  mov     ecx, [rcx]; ExceptionCode
0x18006064e  call    cs:__imp_RpcExceptionFilter
0x180060654  nop
0x180060655  add     rsp, 30h
0x180060659  pop     rbp
0x18006065a  retn
```
