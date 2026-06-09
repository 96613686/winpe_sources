# CUSClient_NotificationsManager::Advise(__MIDL___MIDL_itf_unistore_0000_0000_0010 const *,IUSAdviseSink *,ulong *)

- ea: `0x180023c30`
- end: `0x180023e62`
- name: `?Advise@CUSClient_NotificationsManager@@UEAAJPEBU__MIDL___MIDL_itf_unistore_0000_0000_0010@@PEAUIUSAdviseSink@@PEAK@Z`
- size: `562`
- prototype: `int(CUSClient_NotificationsManager *__hidden this, const struct __MIDL___MIDL_itf_unistore_0000_0000_0010 *, struct IUSAdviseSink *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800068f0`
- `0x1800230ac`
- `0x1800231ac`
- `0x180023510`
- `0x180023c30`
- `0x180023f9c`
- `0x180024154`
- `0x18002995c`
- `0x18006c984`
- `0x1800701e0`
- `0x180078a4c`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180023d7d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180023d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023da4`

## string_xrefs

- `0x180023e06`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\clientobjects.cpp`
- `0x180023e2e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\clientobjects.cpp`

## pseudocode

```c
__int64 __fastcall CUSClient_NotificationsManager::Advise(
        CUSClient_NotificationsManager *this,
        const struct __MIDL___MIDL_itf_unistore_0000_0000_0010 *a2,
        struct IUSAdviseSink *a3,
        unsigned int *a4)
{
  _QWORD *v8; // rax
  unsigned __int64 v9; // rbx
  struct __MIDL_UnistoreService_0002 *v10; // rcx
  __int128 v11; // xmm0
  __int64 v12; // rcx
  int Rpc; // eax
  unsigned int v14; // edi
  __int64 v15; // r9
  HANDLE *v16; // rsi
  HANDLE v17; // rdi
  signed int LastError; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  const struct __MIDL___MIDL_itf_unistore_0000_0000_0010 *v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v26[24]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[104]; // [rsp+70h] [rbp-90h] BYREF

  v23 = a2;
  v8 = operator new(0xB0u);
  v9 = (unsigned __int64)v8;
  if ( v8 )
  {
    v8[1] = 0;
    v8[4] = 0;
    v8[5] = 0;
    v8[8] = 0;
    *((_DWORD *)v8 + 18) = 0;
    v8[19] = 0;
    v8[20] = 0;
    v8[7] = v8 + 6;
    v8[6] = v8 + 6;
    *((_OWORD *)v8 + 1) = 0;
    *v8 = &CUSClient_NotifyHandler::`vftable';
    v8[21] = 0;
    ATL::CComPtr<IDBFilter>::operator=(v8 + 1, a3);
    v10 = *(struct __MIDL_UnistoreService_0002 **)(v9 + 168);
    if ( v10 )
      _AdviseCloserAsync(v10);
    *(_QWORD *)(v9 + 168) = 0;
    *(_QWORD *)v22 = v9 + 168;
    v11 = *(_OWORD *)GetClientThreadInfo(v26);
    v24 = *((_QWORD *)this + 3);
    v25 = v11;
    Rpc = RpcHelper::MakeRpcCall<__MIDL_UnistoreService_0001 *,_CLIENT_THREAD_INFO,__MIDL___MIDL_itf_unistore_0000_0000_0010 const *,__MIDL_UnistoreService_0002 * *,unsigned short *,__MIDL_UnistoreService_0001 *,_CLIENT_THREAD_INFO,__MIDL___MIDL_itf_unistore_0000_0000_0010 const * &,__MIDL_UnistoreService_0002 * *,unsigned short (&)[100]>(
            v12,
            &v24,
            &v25,
            &v23,
            (__int64 *)v22,
            (__int64)Name);
    v14 = Rpc;
    if ( Rpc < 0 )
    {
      v15 = 1728;
LABEL_17:
      v20 = (unsigned int)Rpc;
      v19 = 1;
LABEL_18:
      Log_UnistoreHREvent_0(
        v20,
        v19,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\clientobjects.cpp",
        v15);
      tlx::_delete<DPBuffer>((__int64 (__fastcall ***)(_QWORD, __int64))v9);
      return v14;
    }
    *(_OWORD *)(v9 + 16) = *(_OWORD *)GetClientThreadInfo(v26);
    v16 = (HANDLE *)(v9 + 40);
    v17 = OpenEventW(0x100002u, 0, Name);
    if ( v17 == *(HANDLE *)(v9 + 40) )
    {
      v17 = *v16;
    }
    else
    {
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(v9 + 40);
      *v16 = v17;
    }
    if ( !v17 )
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      v15 = 1732;
      v19 = 0;
      v20 = v14;
      goto LABEL_18;
    }
    Rpc = BaseClientNotifyHandler::InitializeNewHandler((char *)v9, a2);
    v14 = Rpc;
    if ( Rpc < 0 )
    {
      v15 = 1734;
      goto LABEL_17;
    }
    v22[0] = 0;
    Rpc = AddAdvisorToMap(v9, v22);
    v14 = Rpc;
    if ( Rpc < 0 )
    {
      v15 = 1738;
      goto LABEL_17;
    }
    *a4 = v22[0];
    return 0;
  }
  else
  {
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\clientobjects.cpp",
      1715);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180023c30  push    rbp
0x180023c32  push    rbx
0x180023c33  push    rsi
0x180023c34  push    rdi
0x180023c35  push    r14
0x180023c37  push    r15
0x180023c39  lea     rbp, [rsp-58h]
0x180023c3e  sub     rsp, 158h
0x180023c45  mov     rax, cs:__security_cookie
0x180023c4c  xor     rax, rsp
0x180023c4f  mov     [rbp+80h+var_40], rax
0x180023c53  mov     rsi, rcx
0x180023c56  mov     [rsp+180h+var_148], rdx
0x180023c5b  mov     ecx, 0B0h; Size
0x180023c60  mov     r15, r9
0x180023c63  mov     rdi, r8
0x180023c66  mov     r14, rdx
0x180023c69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023c6e  mov     rbx, rax
0x180023c71  test    rax, rax
0x180023c74  jz      loc_180023E29
0x180023c7a  mov     qword ptr [rax+8], 0
0x180023c82  lea     rcx, [rax+30h]
0x180023c86  mov     qword ptr [rax+20h], 0
0x180023c8e  xorps   xmm0, xmm0
0x180023c91  mov     qword ptr [rax+28h], 0
0x180023c99  mov     rdx, rdi
0x180023c9c  mov     qword ptr [rax+40h], 0
0x180023ca4  mov     dword ptr [rax+48h], 0
0x180023cab  mov     qword ptr [rax+98h], 0
0x180023cb6  mov     qword ptr [rax+0A0h], 0
0x180023cc1  mov     [rcx+8], rcx
0x180023cc5  mov     [rcx], rcx
0x180023cc8  lea     rcx, [rbx+8]
0x180023ccc  movups  xmmword ptr [rax+10h], xmm0
0x180023cd0  lea     rax, ??_7CUSClient_NotifyHandler@@6B@; const CUSClient_NotifyHandler::`vftable'
0x180023cd7  mov     [rbx], rax
0x180023cda  mov     qword ptr [rbx+0A8h], 0
0x180023ce5  call    ??4?$CComPtr@UIDBFilter@@@ATL@@QEAAPEAUIDBFilter@@PEAU2@@Z; ATL::CComPtr<IDBFilter>::operator=(IDBFilter *)
0x180023cea  lea     rdi, [rbx+0A8h]
0x180023cf1  mov     rcx, [rdi]; struct __MIDL_UnistoreService_0002 *
0x180023cf4  test    rcx, rcx
0x180023cf7  jz      short loc_180023CFE
0x180023cf9  call    ?_AdviseCloserAsync@@YAJPEAU__MIDL_UnistoreService_0002@@@Z; _AdviseCloserAsync(__MIDL_UnistoreService_0002 *)
0x180023cfe  lea     rcx, [rsp+180h+var_128]
0x180023d03  mov     qword ptr [rdi], 0
0x180023d0a  mov     qword ptr [rsp+180h+var_150], rdi
0x180023d0f  call    ?GetClientThreadInfo@@YA?AU_CLIENT_THREAD_INFO@@XZ; GetClientThreadInfo(void)
0x180023d14  lea     r9, [rsp+180h+var_148]
0x180023d19  lea     r8, [rsp+180h+var_138]
0x180023d1e  lea     rdx, [rsp+180h+var_140]
0x180023d23  movups  xmm0, xmmword ptr [rax]
0x180023d26  mov     rax, [rsi+18h]
0x180023d2a  mov     [rsp+180h+var_140], rax
0x180023d2f  lea     rax, [rsp+180h+Name]
0x180023d34  mov     [rsp+180h+var_158], rax
0x180023d39  lea     rax, [rsp+180h+var_150]
0x180023d3e  mov     [rsp+180h+var_160], rax
0x180023d43  movdqu  [rsp+180h+var_138], xmm0
0x180023d49  call    ??$MakeRpcCall@PEAU__MIDL_UnistoreService_0001@@U_CLIENT_THREAD_INFO@@PEBU__MIDL___MIDL_itf_unistore_0000_0000_0010@@PEAPEAU__MIDL_UnistoreService_0002@@PEAGPEAU1@U2@AEAPEBU3@PEAPEAU4@AEAY0GE@G@RpcHelper@@YAJP6AJPEAU__MIDL_UnistoreService_0001@@U_CLIENT_THREAD_INFO@@PEBU__MIDL___MIDL_itf_unistore_0000_0000_0010@@PEAPEAU__MIDL_UnistoreService_0002@@PEAG@Z$$QEAPEAU1@$$QEAU2@AEAPEBU3@$$QEAPEAPEAU4@AEAY0GE@G@Z; RpcHelper::MakeRpcCall<__MIDL_UnistoreService_0001 *,_CLIENT_THREAD_INFO,__MIDL___MIDL_itf_unistore_0000_0000_0010 const *,__MIDL_UnistoreService_0002 * *,ushort *,__MIDL_UnistoreService_0001 *,_CLIENT_THREAD_INFO,__MIDL___MIDL_itf_unistore_0000_0000_0010 const * &,__MIDL_UnistoreService_0002 * *,ushort (&)[100]>(long (*)(__MIDL_UnistoreService_0001 *,_CLIENT_THREAD_INFO,__MIDL___MIDL_itf_unistore_0000_0000_0010 const *,__MIDL_UnistoreService_0002 * *,ushort *),__MIDL_UnistoreService_0001 * &&,_CLIENT_THREAD_INFO &&,__MIDL___MIDL_itf_unistore_0000_0000_0010 const * &,__MIDL_UnistoreService_0002 * * &&,ushort (&)[100])
0x180023d4e  mov     edi, eax
0x180023d50  test    eax, eax
0x180023d52  jns     short loc_180023D5F
0x180023d54  mov     r9d, 6C0h
0x180023d5a  jmp     loc_180023DFF
0x180023d5f  lea     rcx, [rsp+180h+var_128]
0x180023d64  call    ?GetClientThreadInfo@@YA?AU_CLIENT_THREAD_INFO@@XZ; GetClientThreadInfo(void)
0x180023d69  lea     r8, [rsp+180h+Name]; lpName
0x180023d6e  xor     edx, edx; bInheritHandle
0x180023d70  mov     ecx, 100002h; dwDesiredAccess
0x180023d75  movups  xmm0, xmmword ptr [rax]
0x180023d78  movdqu  xmmword ptr [rbx+10h], xmm0
0x180023d7d  call    cs:__imp_OpenEventW
0x180023d83  lea     rsi, [rbx+28h]
0x180023d87  mov     rdi, rax
0x180023d8a  cmp     rax, [rsi]
0x180023d8d  jz      short loc_180023D9C
0x180023d8f  mov     rcx, rsi
0x180023d92  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180023d97  mov     [rsi], rdi
0x180023d9a  jmp     short loc_180023D9F
0x180023d9c  mov     rdi, [rsi]
0x180023d9f  test    rdi, rdi
0x180023da2  jnz     short loc_180023DC5
0x180023da4  call    cs:__imp_GetLastError
0x180023daa  mov     edi, eax
0x180023dac  test    eax, eax
0x180023dae  jle     short loc_180023DB9
0x180023db0  movzx   edi, ax
0x180023db3  or      edi, 80070000h
0x180023db9  mov     r9d, 6C4h
0x180023dbf  xor     edx, edx
0x180023dc1  mov     ecx, edi
0x180023dc3  jmp     short loc_180023E06
0x180023dc5  mov     rdx, r14; struct __MIDL___MIDL_itf_unistore_0000_0000_0010 *
0x180023dc8  mov     rcx, rbx; pv
0x180023dcb  call    ?InitializeNewHandler@BaseClientNotifyHandler@@QEAAJPEBU__MIDL___MIDL_itf_unistore_0000_0000_0010@@@Z; BaseClientNotifyHandler::InitializeNewHandler(__MIDL___MIDL_itf_unistore_0000_0000_0010 const *)
0x180023dd0  mov     edi, eax
0x180023dd2  test    eax, eax
0x180023dd4  jns     short loc_180023DDE
0x180023dd6  mov     r9d, 6C6h
0x180023ddc  jmp     short loc_180023DFF
0x180023dde  lea     rdx, [rsp+180h+var_150]; unsigned int *
0x180023de3  mov     [rsp+180h+var_150], 0
0x180023deb  mov     rcx, rbx; unsigned __int64
0x180023dee  call    ?AddAdvisorToMap@@YAJ_KPEAK@Z; AddAdvisorToMap(unsigned __int64,ulong *)
0x180023df3  mov     edi, eax
0x180023df5  test    eax, eax
0x180023df7  jns     short loc_180023E1E
0x180023df9  mov     r9d, 6CAh
0x180023dff  mov     ecx, eax
0x180023e01  mov     edx, 1
0x180023e06  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180023e0d  call    Log_UnistoreHREvent_0
0x180023e12  mov     rcx, rbx
0x180023e15  call    ??$_delete@VDPBuffer@@@tlx@@YAXPEAVDPBuffer@@@Z; tlx::_delete<DPBuffer>(DPBuffer *)
0x180023e1a  mov     eax, edi
0x180023e1c  jmp     short loc_180023E46
0x180023e1e  mov     eax, [rsp+180h+var_150]
0x180023e22  mov     [r15], eax
0x180023e25  xor     eax, eax
0x180023e27  jmp     short loc_180023E46
0x180023e29  mov     ebx, 8007000Eh
0x180023e2e  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180023e35  mov     ecx, ebx
0x180023e37  mov     r9d, 6B3h
0x180023e3d  xor     edx, edx
0x180023e3f  call    Log_UnistoreHREvent_0
0x180023e44  mov     eax, ebx
0x180023e46  mov     rcx, [rbp+80h+var_40]
0x180023e4a  xor     rcx, rsp; StackCookie
0x180023e4d  call    __security_check_cookie
0x180023e52  add     rsp, 158h
0x180023e59  pop     r15
0x180023e5b  pop     r14
0x180023e5d  pop     rdi
0x180023e5e  pop     rsi
0x180023e5f  pop     rbx
0x180023e60  pop     rbp
0x180023e61  retn
```
