# NotificationServiceImpl::OnAuthSuccess(char *,char *,_NotificationUser)

- ea: `0x18006f460`
- end: `0x18006f842`
- name: `?OnAuthSuccess@NotificationServiceImpl@@AEAAJPEAD0U_NotificationUser@@@Z`
- size: `994`
- prototype: `__int64 __fastcall(__int64, const char *, const char *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006c280`

## callees

- `0x180007440`
- `0x18000af1c`
- `0x18000ba54`
- `0x18000fddc`
- `0x18000fe54`
- `0x18001bde4`
- `0x18001c4bc`
- `0x180067a30`
- `0x18006d890`
- `0x18006f460`
- `0x180075a98`
- `0x18007669c`
- `0x180076b64`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f50f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f761`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f7cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f50f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f761`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f7cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f4fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f74e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f7bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f4fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f74e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f7bc`

## string_xrefs

- `0x18006f5e1`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006f710`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::OnAuthSuccess(__int64 a1, const char *a2, const char *a3, __int64 a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  void *v12; // rdx
  int v13; // edx
  int v14; // ecx
  __int64 v15; // r8
  __int64 v16; // rcx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  PVOID *v22; // rcx
  void *v23; // rcx
  int v25; // [rsp+20h] [rbp-59h]
  int v26; // [rsp+28h] [rbp-51h]
  unsigned int v27; // [rsp+50h] [rbp-29h] BYREF
  void *v28; // [rsp+58h] [rbp-21h] BYREF
  struct IConnectionProviderEvents *v29[2]; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int8 *v30[2]; // [rsp+70h] [rbp-9h] BYREF
  char v31; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_ssId(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (_DWORD)a3,
      (_DWORD)a2,
      (__int64)a3,
      *(_QWORD *)a4,
      *(_DWORD *)(a4 + 8));
  }
  v29[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29, a2, a3, a4);
  NotificationServiceImpl::GetConnectionProviderEvents((NotificationServiceImpl *)a1, v29);
  v28 = 0;
  v27 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  *(_DWORD *)(a1 + 216) = 8;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v8 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v29[0] + 24LL))(
         v29[0],
         *(unsigned int *)(a1 + 216),
         0,
         0);
  if ( v8 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      243,
      &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
      (unsigned int)v8);
  }
  v30[0] = (unsigned __int8 *)&v28;
  v30[1] = 0;
  v31 = 1;
  v9 = WNPMessageGenerator::GenerateAuthPayload(*(WNPMessageGenerator **)(a1 + 128), a2, a3, &v30[1], &v27);
  wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(v30);
  if ( (v9 & 0x80000000) == 0 )
  {
    v12 = v28;
    v28 = 0;
    wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::reset(
      a1 + 240,
      v12,
      v27);
    if ( (byte_1800AFD82 & 0x10) != 0 )
      McTemplateU0xqssqbr4qbr6_EventWriteTransfer(
        v14,
        v13,
        *(_QWORD *)a4,
        *(_DWORD *)(a4 + 8),
        v25,
        v26,
        v27,
        *(_QWORD *)(a1 + 240));
    if ( (byte_1800AFD84 & 0x20) != 0 )
      McGenEventWrite_EventWriteTransfer(&WPNCORE_PROVIDER_GUID_Context, WPNPRV_PERFTRACK_CONNECT, v15, 1, v30);
    v16 = *(_QWORD *)(a1 + 112);
    *(_OWORD *)v30 = *(_OWORD *)a4;
    v17 = (*(__int64 (__fastcall **)(__int64, const char *, __int64, const char *))(*(_QWORD *)v16 + 24LL))(
            v16,
            "WNS",
            72,
            "\r\n<wns><ver>1</ver><client><name>WPN</name><ver>1.0</ver></client></wns>");
    v9 = v17;
    if ( v17 >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      *(_DWORD *)(a1 + 144) = 1;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      goto LABEL_37;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        246,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v17);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA22,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v9,
      0);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v11 = 247;
      goto LABEL_30;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 244, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v9);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA09,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v9,
      v25);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v11 = 245;
LABEL_30:
      WPP_SF_d(v10[2], v11, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v9);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  *(_DWORD *)(a1 + 216) = 3;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v18 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v29[0] + 24LL))(
          v29[0],
          *(unsigned int *)(a1 + 216),
          0,
          v9);
  if ( v18 >= 0 )
  {
LABEL_37:
    v22 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_38;
  }
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_42;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      248,
      &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
      (unsigned int)v18);
    goto LABEL_37;
  }
LABEL_38:
  if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 2) != 0 && *((_BYTE *)v22 + 25) >= 6u )
    WPP_SF_d(v22[2], 249, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v9);
LABEL_42:
  v23 = v28;
  v28 = 0;
  if ( v23 )
    MemoryFree(v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29, v19, v20, v21);
  return v9;
}

```

## disassembly

```asm
0x18006f460  push    rbp
0x18006f462  push    rbx
0x18006f463  push    rsi
0x18006f464  push    rdi
0x18006f465  push    r13
0x18006f467  push    r14
0x18006f469  push    r15
0x18006f46b  lea     rbp, [rsp-27h]
0x18006f470  sub     rsp, 0A0h
0x18006f477  mov     rax, cs:__security_cookie
0x18006f47e  xor     rax, rsp
0x18006f481  mov     [rbp+57h+var_40], rax
0x18006f485  mov     rsi, r9
0x18006f488  mov     r15, r8
0x18006f48b  mov     rbx, rdx
0x18006f48e  mov     rdi, rcx
0x18006f491  lea     r13, WPP_GLOBAL_Control
0x18006f498  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f49f  cmp     rcx, r13
0x18006f4a2  jz      short loc_18006F4D1
0x18006f4a4  test    byte ptr [rcx+1Ch], 2
0x18006f4a8  jz      short loc_18006F4D1
0x18006f4aa  cmp     byte ptr [rcx+19h], 6
0x18006f4ae  jb      short loc_18006F4D1
0x18006f4b0  mov     eax, [r9+8]
0x18006f4b4  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18006f4b8  mov     rax, [r9]
0x18006f4bb  mov     [rsp+0D0h+var_A8], rax
0x18006f4c0  mov     [rsp+0D0h+var_B0], r8
0x18006f4c5  mov     r9, rdx
0x18006f4c8  mov     rcx, [rcx+10h]
0x18006f4cc  call    WPP_SF_ssId
0x18006f4d1  xor     r14d, r14d
0x18006f4d4  mov     [rbp+57h+var_70], r14
0x18006f4d8  lea     rcx, [rbp+57h+var_70]
0x18006f4dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f4e1  lea     rdx, [rbp+57h+var_70]; struct IConnectionProviderEvents **
0x18006f4e5  mov     rcx, rdi; this
0x18006f4e8  call    ?GetConnectionProviderEvents@NotificationServiceImpl@@AEAAXPEAPEAUIConnectionProviderEvents@@@Z; NotificationServiceImpl::GetConnectionProviderEvents(IConnectionProviderEvents * *)
0x18006f4ed  mov     [rbp+57h+var_78], r14
0x18006f4f1  mov     [rbp+57h+var_80], r14d
0x18006f4f5  lea     r14, [rdi+10h]
0x18006f4f9  mov     rcx, r14; lpCriticalSection
0x18006f4fc  call    cs:__imp_EnterCriticalSection
0x18006f502  mov     dword ptr [rdi+0D8h], 8
0x18006f50c  mov     rcx, r14; lpCriticalSection
0x18006f50f  call    cs:__imp_LeaveCriticalSection
0x18006f515  mov     rcx, [rbp+57h+var_70]
0x18006f519  mov     rax, [rcx]
0x18006f51c  xor     r9d, r9d
0x18006f51f  xor     r8d, r8d
0x18006f522  mov     edx, [rdi+0D8h]
0x18006f528  mov     rax, [rax+18h]
0x18006f52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f531  test    eax, eax
0x18006f533  jns     short loc_18006F565
0x18006f535  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f53c  cmp     rcx, r13
0x18006f53f  jz      short loc_18006F565
0x18006f541  test    byte ptr [rcx+1Ch], 2
0x18006f545  jz      short loc_18006F565
0x18006f547  cmp     byte ptr [rcx+19h], 2
0x18006f54b  jb      short loc_18006F565
0x18006f54d  mov     edx, 0F3h
0x18006f552  mov     r9d, eax
0x18006f555  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f55c  mov     rcx, [rcx+10h]
0x18006f560  call    WPP_SF_d
0x18006f565  lea     rax, [rbp+57h+var_78]
0x18006f569  mov     [rbp+57h+var_60], rax
0x18006f56d  mov     [rbp+57h+var_60+8], 0
0x18006f575  mov     [rbp+57h+var_50], 1
0x18006f579  lea     rax, [rbp+57h+var_80]
0x18006f57d  mov     [rsp+0D0h+var_B0], rax; int
0x18006f582  lea     r9, [rbp+57h+var_60+8]; unsigned __int8 **
0x18006f586  mov     r8, r15; char *
0x18006f589  mov     rdx, rbx; char *
0x18006f58c  mov     rcx, [rdi+80h]; this
0x18006f593  call    ?GenerateAuthPayload@WNPMessageGenerator@@QEAAJPEBD0PEAPEAEPEAK@Z; WNPMessageGenerator::GenerateAuthPayload(char const *,char const *,uchar * *,ulong *)
0x18006f598  mov     ebx, eax
0x18006f59a  lea     rcx, [rbp+57h+var_60]
0x18006f59e  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x18006f5a3  xor     r15d, r15d
0x18006f5a6  test    ebx, ebx
0x18006f5a8  jns     short loc_18006F616
0x18006f5aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f5b1  cmp     rcx, r13
0x18006f5b4  jz      short loc_18006F5DA
0x18006f5b6  test    byte ptr [rcx+1Ch], 2
0x18006f5ba  jz      short loc_18006F5DA
0x18006f5bc  cmp     byte ptr [rcx+19h], 2
0x18006f5c0  jb      short loc_18006F5DA
0x18006f5c2  mov     edx, 0F4h
0x18006f5c7  mov     r9d, ebx
0x18006f5ca  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f5d1  mov     rcx, [rcx+10h]
0x18006f5d5  call    WPP_SF_d
0x18006f5da  mov     rcx, [rbp+5Fh]; this
0x18006f5de  mov     r9d, ebx; char *
0x18006f5e1  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006f5e8  mov     edx, 0A09h; void *
0x18006f5ed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f5f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f5f9  cmp     rcx, r13
0x18006f5fc  jz      loc_18006F74B
0x18006f602  test    byte ptr [rcx+1Ch], 80h
0x18006f606  jz      loc_18006F74B
0x18006f60c  mov     edx, 0F5h
0x18006f611  jmp     loc_18006F738
0x18006f616  mov     rdx, [rbp+57h+var_78]
0x18006f61a  mov     [rbp+57h+var_78], r15
0x18006f61e  lea     rbx, [rdi+0F0h]
0x18006f625  mov     r8d, [rbp+57h+var_80]
0x18006f629  mov     rcx, rbx
0x18006f62c  call    ?reset@?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEAAXPEAE_K@Z; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::reset(uchar *,unsigned __int64)
0x18006f631  test    cs:byte_1800AFD82, 10h
0x18006f638  jz      short loc_18006F655
0x18006f63a  mov     rax, [rbx]
0x18006f63d  mov     [rsp+0D0h+var_98], rax
0x18006f642  mov     eax, [rbp+57h+var_80]
0x18006f645  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18006f649  mov     r9d, [rsi+8]
0x18006f64d  mov     r8, [rsi]
0x18006f650  call    McTemplateU0xqssqbr4qbr6_EventWriteTransfer
0x18006f655  test    cs:byte_1800AFD84, 20h
0x18006f65c  jz      short loc_18006F680
0x18006f65e  lea     rax, [rbp+57h+var_60]
0x18006f662  mov     [rsp+0D0h+var_B0], rax
0x18006f667  mov     r9d, 1
0x18006f66d  lea     rdx, WPNPRV_PERFTRACK_CONNECT
0x18006f674  lea     rcx, WPNCORE_PROVIDER_GUID_Context
0x18006f67b  call    McGenEventWrite_EventWriteTransfer
0x18006f680  mov     rcx, [rdi+70h]
0x18006f684  movaps  xmm0, xmmword ptr [rsi]
0x18006f687  movdqa  xmmword ptr [rbp+57h+var_60], xmm0
0x18006f68c  mov     r8, [rcx]
0x18006f68f  mov     rax, rdi
0x18006f692  lea     rdx, [rdi+8]
0x18006f696  neg     rax
0x18006f699  sbb     r9, r9
0x18006f69c  and     r9, rdx
0x18006f69f  mov     rax, [r8+18h]
0x18006f6a3  lea     rdx, [rbp+57h+var_60]
0x18006f6a7  mov     [rsp+0D0h+var_A0], rdx
0x18006f6ac  mov     [rsp+0D0h+var_A8], r9
0x18006f6b1  mov     dword ptr [rsp+0D0h+var_B0], r15d; int
0x18006f6b6  lea     r9, ?s_BindPayload@WNPMessageGenerator@@2QBDB; "\r\n<wns><ver>1</ver><client><name>WPN<"...
0x18006f6bd  mov     r8d, 48h ; 'H'
0x18006f6c3  lea     rdx, aWns_1; "WNS"
0x18006f6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f6cf  mov     ebx, eax
0x18006f6d1  test    eax, eax
0x18006f6d3  jns     loc_18006F7B9
0x18006f6d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f6e0  cmp     rcx, r13
0x18006f6e3  jz      short loc_18006F709
0x18006f6e5  test    byte ptr [rcx+1Ch], 2
0x18006f6e9  jz      short loc_18006F709
0x18006f6eb  cmp     byte ptr [rcx+19h], 2
0x18006f6ef  jb      short loc_18006F709
0x18006f6f1  mov     edx, 0F6h
0x18006f6f6  mov     r9d, eax
0x18006f6f9  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f700  mov     rcx, [rcx+10h]
0x18006f704  call    WPP_SF_d
0x18006f709  mov     rcx, [rbp+5Fh]; this
0x18006f70d  mov     r9d, ebx; char *
0x18006f710  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006f717  mov     edx, 0A22h; void *
0x18006f71c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f721  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f728  cmp     rcx, r13
0x18006f72b  jz      short loc_18006F74B
0x18006f72d  test    byte ptr [rcx+1Ch], 80h
0x18006f731  jz      short loc_18006F74B
0x18006f733  mov     edx, 0F7h
0x18006f738  mov     r9d, ebx
0x18006f73b  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f742  mov     rcx, [rcx+10h]
0x18006f746  call    WPP_SF_d
0x18006f74b  mov     rcx, r14; lpCriticalSection
0x18006f74e  call    cs:__imp_EnterCriticalSection
0x18006f754  mov     dword ptr [rdi+0D8h], 3
0x18006f75e  mov     rcx, r14; lpCriticalSection
0x18006f761  call    cs:__imp_LeaveCriticalSection
0x18006f767  mov     rcx, [rbp+57h+var_70]
0x18006f76b  mov     rax, [rcx]
0x18006f76e  mov     r9d, ebx
0x18006f771  xor     r8d, r8d
0x18006f774  mov     edx, [rdi+0D8h]
0x18006f77a  mov     rax, [rax+18h]
0x18006f77e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f783  test    eax, eax
0x18006f785  jns     short loc_18006F7D5
0x18006f787  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f78e  cmp     rcx, r13
0x18006f791  jz      short loc_18006F806
0x18006f793  test    byte ptr [rcx+1Ch], 2
0x18006f797  jz      short loc_18006F7DC
0x18006f799  cmp     byte ptr [rcx+19h], 2
0x18006f79d  jb      short loc_18006F7DC
0x18006f79f  mov     edx, 0F8h
0x18006f7a4  mov     r9d, eax
0x18006f7a7  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f7ae  mov     rcx, [rcx+10h]
0x18006f7b2  call    WPP_SF_d
0x18006f7b7  jmp     short loc_18006F7D5
0x18006f7b9  mov     rcx, r14; lpCriticalSection
0x18006f7bc  call    cs:__imp_EnterCriticalSection
0x18006f7c2  mov     dword ptr [rdi+90h], 1
0x18006f7cc  mov     rcx, r14; lpCriticalSection
0x18006f7cf  call    cs:__imp_LeaveCriticalSection
0x18006f7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f7dc  cmp     rcx, r13
0x18006f7df  jz      short loc_18006F806
0x18006f7e1  test    byte ptr [rcx+1Ch], 2
0x18006f7e5  jz      short loc_18006F806
0x18006f7e7  cmp     byte ptr [rcx+19h], 6
0x18006f7eb  jb      short loc_18006F806
0x18006f7ed  mov     edx, 0F9h
0x18006f7f2  mov     r9d, ebx
0x18006f7f5  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f7fc  mov     rcx, [rcx+10h]
0x18006f800  call    WPP_SF_d
0x18006f805  nop
0x18006f806  mov     rcx, [rbp+57h+var_78]; void *
0x18006f80a  mov     [rbp+57h+var_78], r15
0x18006f80e  test    rcx, rcx
0x18006f811  jz      short loc_18006F819
0x18006f813  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18006f818  nop
0x18006f819  lea     rcx, [rbp+57h+var_70]
0x18006f81d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f822  mov     eax, ebx
0x18006f824  mov     rcx, [rbp+57h+var_40]
0x18006f828  xor     rcx, rsp; StackCookie
0x18006f82b  call    __security_check_cookie
0x18006f830  add     rsp, 0A0h
0x18006f837  pop     r15
0x18006f839  pop     r14
0x18006f83b  pop     r13
0x18006f83d  pop     rdi
0x18006f83e  pop     rsi
0x18006f83f  pop     rbx
0x18006f840  pop     rbp
0x18006f841  retn
```
