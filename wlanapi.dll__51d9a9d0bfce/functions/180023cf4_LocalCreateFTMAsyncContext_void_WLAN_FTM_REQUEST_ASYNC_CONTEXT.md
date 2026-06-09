# LocalCreateFTMAsyncContext(void *,_WLAN_FTM_REQUEST_ASYNC_CONTEXT * *)

- ea: `0x180023cf4`
- end: `0x180023f35`
- name: `?LocalCreateFTMAsyncContext@@YAKPEAXPEAPEAU_WLAN_FTM_REQUEST_ASYNC_CONTEXT@@@Z`
- size: `577`
- prototype: `unsigned int __fastcall(void *, struct _WLAN_FTM_REQUEST_ASYNC_CONTEXT **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180029e70`

## callees

- `0x1800053c0`
- `0x1800063a0`
- `0x180006934`
- `0x18001a5bc`
- `0x180023cf4`
- `0x180024140`
- `0x1800281e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023d88`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d9a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180023de8`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180023de8`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180023e55`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180023e55`
- `MobileNetworking!HtNewHandle` at `0x180023eb7`
- `MobileNetworking!HtNewHandle` at `0x180023eb7`

## pseudocode

```c
__int64 __fastcall LocalCreateFTMAsyncContext(void *a1, struct _WLAN_FTM_REQUEST_ASYNC_CONTEXT **a2)
{
  char *v4; // rax
  char *v5; // rsi
  DWORD v6; // eax
  DWORD v7; // ebx
  union DOT11_OUI_HEADER *v8; // rcx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  union DOT11_OUI_HEADER *v11; // rcx
  __int64 v12; // rdx
  DWORD v13; // eax

  v4 = (char *)AllocWLMem(0xA8u);
  v5 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0xA8u);
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v5 + 16) = EventW;
    if ( EventW )
    {
      LastError = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(v5 + 16), 0x70u);
      v7 = LastError;
      if ( !LastError )
      {
        *((_QWORD *)v5 + 8) = *((_QWORD *)v5 + 16);
        *((_DWORD *)v5 + 15) = 1;
        v13 = HtReferenceHandleWithTag(g_hHandleTable, a1, 1129074260, 0, 1, v5 + 8);
        v7 = v13;
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105)
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
          {
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              151,
              WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids,
              a1,
              v13);
          }
        }
        else
        {
          v7 = HtNewHandle(g_hHandleTable, v5, 1129074260, LocalFtmAsyncContextDestroy, 1, v5);
          if ( !v7 )
          {
            *a2 = (struct _WLAN_FTM_REQUEST_ASYNC_CONTEXT *)v5;
            goto LABEL_29;
          }
          if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105)
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 152, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
          }
        }
        goto LABEL_27;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
LABEL_27:
        LocalFtmAsyncContextDestroy((struct _WLAN_FTM_REQUEST_ASYNC_CONTEXT *)v5);
        goto LABEL_29;
      }
      v12 = 150;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        goto LABEL_27;
      }
      v12 = 149;
    }
    WPP_SF_d(*((_QWORD *)v11 + 12), v12, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, LastError);
    goto LABEL_27;
  }
  v6 = GetLastError();
  v7 = v6;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
    return v7;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 148, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, v6);
LABEL_29:
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v8 + 105) >= 4u
    && (*((_BYTE *)v8 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v8 + 12), 153, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x180023cf4  push    rbx
0x180023cf6  push    rbp
0x180023cf7  push    rsi
0x180023cf8  push    r12
0x180023cfa  push    r13
0x180023cfc  push    r14
0x180023cfe  sub     rsp, 38h
0x180023d02  mov     rbp, rcx
0x180023d05  mov     ebx, 0A8h
0x180023d0a  mov     ecx, ebx; dwBytes
0x180023d0c  mov     r14, rdx
0x180023d0f  call    AllocWLMem
0x180023d14  lea     r13, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180023d1b  mov     rsi, rax
0x180023d1e  lea     r12, WPP_GLOBAL_Control
0x180023d25  test    rax, rax
0x180023d28  jnz     short loc_180023D6F
0x180023d2a  call    cs:__imp_GetLastError
0x180023d30  mov     ebx, eax
0x180023d32  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d39  cmp     rcx, r12
0x180023d3c  jz      loc_180023F25
0x180023d42  cmp     byte ptr [rcx+69h], 1
0x180023d46  jb      loc_180023F00
0x180023d4c  test    byte ptr [rcx+6Ch], 2
0x180023d50  jz      loc_180023F00
0x180023d56  mov     rcx, [rcx+60h]
0x180023d5a  mov     edx, 94h
0x180023d5f  mov     r9d, eax
0x180023d62  mov     r8, r13
0x180023d65  call    WPP_SF_d
0x180023d6a  jmp     loc_180023EF9
0x180023d6f  mov     r8, rbx; Size
0x180023d72  xor     edx, edx; Val
0x180023d74  mov     rcx, rsi; void *
0x180023d77  call    memset_0
0x180023d7c  xor     r9d, r9d; lpName
0x180023d7f  xor     r8d, r8d; bInitialState
0x180023d82  xor     ecx, ecx; lpEventAttributes
0x180023d84  lea     edx, [r9+1]; bManualReset
0x180023d88  call    cs:__imp_CreateEventW
0x180023d8e  mov     [rsi+80h], rax
0x180023d95  test    rax, rax
0x180023d98  jnz     short loc_180023DDF
0x180023d9a  call    cs:__imp_GetLastError
0x180023da0  mov     ebx, eax
0x180023da2  mov     rcx, cs:WPP_GLOBAL_Control
0x180023da9  cmp     rcx, r12
0x180023dac  jz      loc_180023EEC
0x180023db2  cmp     byte ptr [rcx+69h], 1
0x180023db6  jb      loc_180023EEC
0x180023dbc  test    byte ptr [rcx+6Ch], 2
0x180023dc0  jz      loc_180023EEC
0x180023dc6  mov     edx, 95h
0x180023dcb  mov     rcx, [rcx+60h]
0x180023dcf  mov     r9d, eax
0x180023dd2  mov     r8, r13
0x180023dd5  call    WPP_SF_d
0x180023dda  jmp     loc_180023EEC
0x180023ddf  lea     rcx, [rsi+10h]; pAsync
0x180023de3  mov     edx, 70h ; 'p'; Size
0x180023de8  call    cs:__imp_RpcAsyncInitializeHandle
0x180023dee  mov     ebx, eax
0x180023df0  test    eax, eax
0x180023df2  jz      short loc_180023E1F
0x180023df4  mov     rcx, cs:WPP_GLOBAL_Control
0x180023dfb  cmp     rcx, r12
0x180023dfe  jz      loc_180023EEC
0x180023e04  cmp     byte ptr [rcx+69h], 1
0x180023e08  jb      loc_180023EEC
0x180023e0e  test    byte ptr [rcx+6Ch], 2
0x180023e12  jz      loc_180023EEC
0x180023e18  mov     edx, 96h
0x180023e1d  jmp     short loc_180023DCB
0x180023e1f  mov     rax, [rsi+80h]
0x180023e26  xor     r9d, r9d
0x180023e29  mov     [rsi+40h], rax
0x180023e2d  mov     r8d, 434C4E54h
0x180023e33  lea     rax, [rsi+8]
0x180023e37  mov     dword ptr [rsi+3Ch], 1
0x180023e3e  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180023e45  mov     rdx, rbp
0x180023e48  mov     [rsp+68h+var_40], rax
0x180023e4d  mov     [rsp+68h+var_48], 1
0x180023e55  call    cs:__imp_HtReferenceHandleWithTag
0x180023e5b  mov     ebx, eax
0x180023e5d  test    eax, eax
0x180023e5f  jz      short loc_180023E93
0x180023e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e68  cmp     rcx, r12
0x180023e6b  jz      short loc_180023EEC
0x180023e6d  cmp     byte ptr [rcx+69h], 1
0x180023e71  jb      short loc_180023EEC
0x180023e73  test    byte ptr [rcx+6Ch], 2
0x180023e77  jz      short loc_180023EEC
0x180023e79  mov     rcx, [rcx+60h]
0x180023e7d  mov     edx, 97h
0x180023e82  mov     r9, rbp
0x180023e85  mov     [rsp+68h+var_48], eax
0x180023e89  mov     r8, r13
0x180023e8c  call    WPP_SF_qD
0x180023e91  jmp     short loc_180023EEC
0x180023e93  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180023e9a  lea     r9, ?LocalFtmAsyncContextDestroy@@YAKPEAU_WLAN_FTM_REQUEST_ASYNC_CONTEXT@@@Z; LocalFtmAsyncContextDestroy(_WLAN_FTM_REQUEST_ASYNC_CONTEXT *)
0x180023ea1  mov     [rsp+68h+var_40], rsi
0x180023ea6  mov     r8d, 434C4E54h
0x180023eac  mov     rdx, rsi
0x180023eaf  mov     [rsp+68h+var_48], 1
0x180023eb7  call    cs:__imp_HtNewHandle
0x180023ebd  mov     ebx, eax
0x180023ebf  test    eax, eax
0x180023ec1  jz      short loc_180023EF6
0x180023ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x180023eca  cmp     rcx, r12
0x180023ecd  jz      short loc_180023EEC
0x180023ecf  cmp     byte ptr [rcx+69h], 1
0x180023ed3  jb      short loc_180023EEC
0x180023ed5  test    byte ptr [rcx+6Ch], 2
0x180023ed9  jz      short loc_180023EEC
0x180023edb  mov     rcx, [rcx+60h]
0x180023edf  mov     edx, 98h
0x180023ee4  mov     r8, r13
0x180023ee7  call    WPP_SF_
0x180023eec  mov     rcx, rsi; struct _WLAN_FTM_REQUEST_ASYNC_CONTEXT *
0x180023eef  call    ?LocalFtmAsyncContextDestroy@@YAKPEAU_WLAN_FTM_REQUEST_ASYNC_CONTEXT@@@Z; LocalFtmAsyncContextDestroy(_WLAN_FTM_REQUEST_ASYNC_CONTEXT *)
0x180023ef4  jmp     short loc_180023EF9
0x180023ef6  mov     [r14], rsi
0x180023ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f00  cmp     rcx, r12
0x180023f03  jz      short loc_180023F25
0x180023f05  cmp     byte ptr [rcx+69h], 4
0x180023f09  jb      short loc_180023F25
0x180023f0b  test    byte ptr [rcx+6Ch], 2
0x180023f0f  jz      short loc_180023F25
0x180023f11  mov     rcx, [rcx+60h]
0x180023f15  mov     edx, 99h
0x180023f1a  mov     r9d, ebx
0x180023f1d  mov     r8, r13
0x180023f20  call    WPP_SF_d
0x180023f25  mov     eax, ebx
0x180023f27  add     rsp, 38h
0x180023f2b  pop     r14
0x180023f2d  pop     r13
0x180023f2f  pop     r12
0x180023f31  pop     rsi
0x180023f32  pop     rbp
0x180023f33  pop     rbx
0x180023f34  retn
```
