# BoundSubscription::EnterSubscribingState(void)

- ea: `0x18000c724`
- end: `0x18000cd4a`
- name: `?EnterSubscribingState@BoundSubscription@@AEAAXXZ`
- size: `1574`
- prototype: `void __fastcall(BoundSubscription *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180008828`
- `0x18000ea28`

## callees

- `0x18000195c`
- `0x1800024b0`
- `0x180002510`
- `0x1800032dc`
- `0x1800034f0`
- `0x180006334`
- `0x18000c2d8`
- `0x18000c724`
- `0x18000d0f0`
- `0x18000db1c`
- `0x18000f1f8`
- `0x18000f7b0`
- `0x180011a10`
- `0x18001351c`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccd6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c8b9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c8b9`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000c7e0`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000c7e0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000c98c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000cb7f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000c98c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000cb7f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000c9b9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000c9b9`
- `WsmSvc!WSManCreatePushSubscription` at `0x18000cb22`
- `WsmSvc!WSManCreatePushSubscription` at `0x18000cb22`
- `WsmSvc!WSManCreatePullSubscription` at `0x18000cb6e`
- `WsmSvc!WSManCreatePullSubscription` at `0x18000cb6e`
- `WsmSvc!WSManCloseObjectHandle` at `0x18000c88c`
- `WsmSvc!WSManEncodeObject` at `0x18000c87e`
- `WsmSvc!WSManEncodeObject` at `0x18000c87e`

## string_xrefs

- `0x18000cc44`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x18000ccb1`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x18000cd25`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall BoundSubscription::EnterSubscribingState(BoundSubscription *this)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rax
  const unsigned __int16 *v4; // rsi
  _QWORD *v5; // rdx
  _QWORD *v6; // rcx
  unsigned __int16 *v7; // rdi
  __int64 v8; // rax
  char v9; // cl
  char **v10; // rdi
  char *v11; // r8
  _QWORD *v12; // rdx
  char *v13; // rax
  void *v14; // r15
  HANDLE *v15; // r14
  void *v16; // rcx
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  int v19; // eax
  DWORD LastError; // ebx
  DWORD v21; // ebx
  _BYTE v22[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+70h] [rbp-90h]
  int v26; // [rsp+74h] [rbp-8Ch]
  _OWORD *v27; // [rsp+78h] [rbp-88h]
  void (__fastcall *v28)(const struct _WSMAN_EVENTS_RESULT *, const struct WSMAN_SENDER_DETAILS_INTERNAL *, struct WSMAN_DELIVERY *, struct SubscriptionCallbackContext *); // [rsp+80h] [rbp-80h]
  __int64 v29; // [rsp+88h] [rbp-78h]
  char *v30; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v31[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v32; // [rsp+A8h] [rbp-58h]
  void *v33[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-40h]
  char v35[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 (__fastcall *v36)(_QWORD); // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  _QWORD v38[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v39; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+100h] [rbp+0h]
  __int64 v41; // [rsp+108h] [rbp+8h]
  int v42; // [rsp+110h] [rbp+10h]
  int v43; // [rsp+114h] [rbp+14h]
  void *v44; // [rsp+118h] [rbp+18h]
  __int64 v45; // [rsp+120h] [rbp+20h]
  _OWORD v46[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v47; // [rsp+150h] [rbp+50h]
  __int128 v48; // [rsp+158h] [rbp+58h] BYREF
  __int128 v49; // [rsp+168h] [rbp+68h]
  _BYTE v50[24]; // [rsp+178h] [rbp+78h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+190h] [rbp+90h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v2 = (_QWORD *)((char *)this + 72);
    if ( v2[3] >= 8u )
      v2 = (_QWORD *)*v2;
    v3 = (_QWORD *)(*((_QWORD *)this + 8) + 56LL);
    if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
      v3 = (_QWORD *)*v3;
    WPP_SF_dSSq(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v3, (__int64)v2, (char)this);
  }
  BoundSubscription::RecordLastError(this, 0, 0);
  SystemTime = 0;
  FileTimeToSystemTime((const FILETIME *)((char *)this + 500), &SystemTime);
  *(_OWORD *)v31 = 0;
  v32 = 0;
  v23 = 0;
  v22[0] = 0;
  if ( *((_QWORD *)this + 60) )
  {
    v4 = (const unsigned __int16 *)((char *)this + 464);
    if ( *((_QWORD *)this + 61) >= 8u )
      v4 = *(const unsigned __int16 **)v4;
  }
  else
  {
    v4 = 0;
  }
  v5 = (_QWORD *)((char *)this + 72);
  if ( *((_QWORD *)this + 12) >= 8u )
    v5 = (_QWORD *)*v5;
  v6 = (_QWORD *)(*((_QWORD *)this + 8) + 56LL);
  if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
    v6 = (_QWORD *)*v6;
  if ( (unsigned __int8)ReadBookmark((_DWORD)v6, (_DWORD)v5, 0, (unsigned int)v31, (__int64)v22) )
  {
    v7 = v31[0];
    if ( IsBookMarkMatchToQueryFilter(v4, v31[0])
      && !(unsigned int)WSManEncodeObject(v7, (unsigned int)(LODWORD(v31[1]) - (_DWORD)v7), 0x4000, &v23) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, LastError);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        LastError,
        "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp",
        1540);
      throw (wmi::GenericException *)pExceptionObject;
    }
  }
  v8 = v23;
  if ( v23 )
  {
    v35[0] = 0;
  }
  else
  {
    v8 = 0;
    v35[0] = 1;
  }
  v36 = WSManCloseObjectHandle;
  v37 = v8;
  ResetEvent(*((HANDLE *)this + 29));
  *(_OWORD *)v33 = 0;
  v34 = 0;
  v9 = 0;
  if ( !v22[0] )
    v9 = *((_BYTE *)this + 176);
  v10 = (char **)((char *)this + 136);
  if ( *((_QWORD *)this + 20) < 8u )
    LODWORD(v11) = (_DWORD)this + 136;
  else
    v11 = *v10;
  v12 = (_QWORD *)(*((_QWORD *)this + 8) + 56LL);
  if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
    v12 = (_QWORD *)*v12;
  GetWSManSubscribeOptions((int)v33, (int)v12, (int)v11, *((_DWORD *)this + 96), *((_DWORD *)this + 43), v9);
  v38[0] = 72;
  if ( *((_QWORD *)this + 20) < 8u )
    v13 = (char *)this + 136;
  else
    v13 = *v10;
  v38[1] = v13;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v14 = v33[0];
  v42 = -1431655765 * (((char *)v33[1] - (char *)v33[0]) >> 3);
  v43 = 0;
  v44 = v33[0];
  v45 = 0;
  v15 = (HANDLE *)((char *)this + 224);
  v16 = (void *)*((_QWORD *)this + 28);
  if ( v16 )
  {
    UnregisterWaitEx(v16, 0);
    *v15 = 0;
  }
  if ( !RegisterWaitForSingleObject(
          (PHANDLE)this + 28,
          *((HANDLE *)this + 29),
          BoundSubscription::SubscribeCompleteCallback,
          this,
          0xFFFFFFFF,
          8u) )
  {
    v21 = GetLastError();
    if ( !v21 )
      v21 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v21);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      v21,
      "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp",
      1577);
    throw (wmi::GenericException *)pExceptionObject;
  }
  v48 = 0;
  v49 = 0;
  memset(v50, 0, sizeof(v50));
  *((_QWORD *)&v49 + 1) = *(_QWORD *)((char *)this + 388);
  *(_DWORD *)v50 = *((_DWORD *)this + 99);
  *(_QWORD *)&v48 = GetDialect((char *)this + 432, (char *)this + 136);
  *((_QWORD *)&v48 + 1) = v4;
  *(struct _SYSTEMTIME *)&v50[4] = SystemTime;
  *(_DWORD *)&v50[20] = *((_DWORD *)this + 124);
  *(_QWORD *)&v49 = v23;
  if ( *((_DWORD *)this + 42) == 2 )
  {
    pExceptionObject[0] = 0;
    pExceptionObject[1] = 0;
    v29 = 0;
    if ( *((_QWORD *)this + 52) )
    {
      v17 = (_QWORD *)((char *)this + 400);
      if ( *((_QWORD *)this + 53) >= 8u )
        v17 = (_QWORD *)*v17;
      pExceptionObject[0] = v17;
    }
    v25 = 60;
    v26 = 5;
    v28 = Subscription::EventsCallback;
    *((_DWORD *)this + 128) = 1;
    *((_QWORD *)this + 65) = *((_QWORD *)this + 8);
    v18 = (_QWORD *)((char *)this + 104);
    if ( *((_QWORD *)this + 16) >= 8u )
      v18 = (_QWORD *)*v18;
    *((_QWORD *)this + 66) = v18;
    v30 = (char *)this + 512;
    memset(v46, 0, sizeof(v46));
    v47 = 0;
    LODWORD(v46[0]) = 1;
    v27 = v46;
    v19 = WSManCreatePushSubscription(
            *((_QWORD *)this + 36),
            *((unsigned int *)this + 96),
            60000,
            v38,
            &v48,
            pExceptionObject,
            (char *)this + 304,
            (char *)this + 296,
            *((_QWORD *)this + 29));
  }
  else
  {
    v19 = WSManCreatePullSubscription(
            *((_QWORD *)this + 36),
            *((unsigned int *)this + 96),
            60000,
            v38,
            &v48,
            (char *)this + 304,
            (char *)this + 296,
            *((_QWORD *)this + 29));
  }
  if ( v19 )
  {
    *((_DWORD *)this + 14) = 1;
  }
  else
  {
    UnregisterWaitEx(*v15, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *v15 = 0;
    BoundSubscription::RecordLastError(this, *((_DWORD *)this + 78), *((struct WSMAN_OBJECT **)this + 40));
    if ( *((_DWORD *)this + 78) == -2144108374 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids,
          2150858922LL);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0x803380AA,
        "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp",
        1650);
      throw (wmi::GenericException *)pExceptionObject;
    }
    BoundSubscription::EnterRetryingState(this);
  }
  if ( v14 )
    operator delete(v14);
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v35);
  std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(v31);
}

```

## disassembly

```asm
0x18000c724  mov     [rsp-8+arg_8], rbx
0x18000c729  mov     [rsp-8+arg_10], rsi
0x18000c72e  push    rbp
0x18000c72f  push    rdi
0x18000c730  push    r12
0x18000c732  push    r14
0x18000c734  push    r15
0x18000c736  lea     rbp, [rsp-0B0h]
0x18000c73e  sub     rsp, 1B0h
0x18000c745  mov     rax, cs:__security_cookie
0x18000c74c  xor     rax, rsp
0x18000c74f  mov     [rbp+0D0h+var_30], rax
0x18000c756  mov     rbx, rcx
0x18000c759  lea     r14, WPP_GLOBAL_Control
0x18000c760  mov     r8, cs:WPP_GLOBAL_Control
0x18000c767  cmp     r8, r14
0x18000c76a  jz      short loc_18000C7BB
0x18000c76c  test    byte ptr [r8+1Ch], 10h
0x18000c771  jz      short loc_18000C7BB
0x18000c773  cmp     byte ptr [r8+19h], 5
0x18000c778  jb      short loc_18000C7BB
0x18000c77a  add     rcx, 48h ; 'H'
0x18000c77e  cmp     qword ptr [rcx+18h], 8
0x18000c783  jb      short loc_18000C788
0x18000c785  mov     rcx, [rcx]
0x18000c788  mov     rax, [rbx+40h]
0x18000c78c  add     rax, 38h ; '8'
0x18000c790  cmp     qword ptr [rax+18h], 8
0x18000c795  jb      short loc_18000C79A
0x18000c797  mov     rax, [rax]
0x18000c79a  mov     edx, 28h ; '('
0x18000c79f  mov     qword ptr [rsp+1D0h+var_1A0], rbx; char
0x18000c7a4  mov     qword ptr [rsp+1D0h+dwFlags], rcx; __int64
0x18000c7a9  mov     qword ptr [rsp+1D0h+dwMilliseconds], rax; __int64
0x18000c7ae  mov     r9d, [rbx+38h]
0x18000c7b2  mov     rcx, [r8+10h]; LoggerHandle
0x18000c7b6  call    WPP_SF_dSSq
0x18000c7bb  xor     r8d, r8d; struct WSMAN_OBJECT *
0x18000c7be  xor     edx, edx; unsigned int
0x18000c7c0  mov     rcx, rbx; this
0x18000c7c3  call    ?RecordLastError@BoundSubscription@@AEAAXKPEAUWSMAN_OBJECT@@@Z; BoundSubscription::RecordLastError(ulong,WSMAN_OBJECT *)
0x18000c7c8  xorps   xmm0, xmm0
0x18000c7cb  movups  xmmword ptr [rbp+0D0h+SystemTime.wYear], xmm0
0x18000c7d2  lea     rcx, [rbx+1F4h]; lpFileTime
0x18000c7d9  lea     rdx, [rbp+0D0h+SystemTime]; lpSystemTime
0x18000c7e0  call    cs:__imp_FileTimeToSystemTime
0x18000c7e6  xorps   xmm0, xmm0
0x18000c7e9  movdqu  xmmword ptr [rbp+0D0h+var_138], xmm0
0x18000c7ee  xor     r12d, r12d
0x18000c7f1  mov     [rbp+0D0h+var_128], r12
0x18000c7f5  mov     [rsp+1D0h+var_178], r12
0x18000c7fa  mov     [rsp+1D0h+var_180], r12b
0x18000c7ff  cmp     [rbx+1E0h], r12
0x18000c806  jz      short loc_18000C81B
0x18000c808  lea     rsi, [rbx+1D0h]
0x18000c80f  cmp     qword ptr [rsi+18h], 8
0x18000c814  jb      short loc_18000C81E
0x18000c816  mov     rsi, [rsi]
0x18000c819  jmp     short loc_18000C81E
0x18000c81b  mov     rsi, r12
0x18000c81e  lea     rdx, [rbx+48h]
0x18000c822  cmp     qword ptr [rdx+18h], 8
0x18000c827  jb      short loc_18000C82C
0x18000c829  mov     rdx, [rdx]
0x18000c82c  mov     rcx, [rbx+40h]
0x18000c830  add     rcx, 38h ; '8'
0x18000c834  cmp     qword ptr [rcx+18h], 8
0x18000c839  jb      short loc_18000C83E
0x18000c83b  mov     rcx, [rcx]
0x18000c83e  lea     rax, [rsp+1D0h+var_180]
0x18000c843  mov     qword ptr [rsp+1D0h+dwMilliseconds], rax
0x18000c848  lea     r9, [rbp+0D0h+var_138]
0x18000c84c  xor     r8d, r8d
0x18000c84f  call    ?ReadBookmark@@YA_NPEBG0_NAEAV?$vector@EV?$allocator@E@std@@@std@@AEA_N@Z; ReadBookmark(ushort const *,ushort const *,bool,std::vector<uchar> &,bool &)
0x18000c854  test    al, al
0x18000c856  jz      short loc_18000C88C
0x18000c858  mov     rdi, [rbp+0D0h+var_138]
0x18000c85c  mov     rdx, rdi; unsigned __int16 *
0x18000c85f  mov     rcx, rsi; unsigned __int16 *
0x18000c862  call    ?IsBookMarkMatchToQueryFilter@@YA_NPEBG0@Z; IsBookMarkMatchToQueryFilter(ushort const *,ushort const *)
0x18000c867  test    al, al
0x18000c869  jz      short loc_18000C88C
0x18000c86b  mov     edx, dword ptr [rbp+0D0h+var_138+8]
0x18000c86e  sub     edx, edi
0x18000c870  lea     r9, [rsp+1D0h+var_178]
0x18000c875  mov     r8d, 4000h
0x18000c87b  mov     rcx, rdi
0x18000c87e  call    cs:__imp_WSManEncodeObject
0x18000c884  test    eax, eax
0x18000c886  jz      loc_18000CC69
0x18000c88c  mov     rcx, cs:__imp_WSManCloseObjectHandle
0x18000c893  mov     rax, [rsp+1D0h+var_178]
0x18000c898  test    rax, rax
0x18000c89b  jz      short loc_18000C8A3
0x18000c89d  mov     [rbp+0D0h+var_108], r12b
0x18000c8a1  jmp     short loc_18000C8AA
0x18000c8a3  mov     rax, r12
0x18000c8a6  mov     [rbp+0D0h+var_108], 1
0x18000c8aa  mov     [rbp+0D0h+var_100], rcx
0x18000c8ae  mov     [rbp+0D0h+var_F8], rax
0x18000c8b2  mov     rcx, [rbx+0E8h]; hEvent
0x18000c8b9  call    cs:__imp_ResetEvent
0x18000c8bf  xorps   xmm0, xmm0
0x18000c8c2  movdqu  xmmword ptr [rbp+0D0h+var_120], xmm0
0x18000c8c7  mov     [rbp+0D0h+var_110], r12
0x18000c8cb  cmp     [rsp+1D0h+var_180], r12b
0x18000c8d0  mov     cl, r12b
0x18000c8d3  jnz     short loc_18000C8DB
0x18000c8d5  mov     cl, [rbx+0B0h]
0x18000c8db  mov     r9d, [rbx+0ACh]
0x18000c8e2  lea     rdi, [rbx+88h]
0x18000c8e9  cmp     qword ptr [rdi+18h], 8
0x18000c8ee  jb      short loc_18000C8F5
0x18000c8f0  mov     r8, [rdi]
0x18000c8f3  jmp     short loc_18000C8F8
0x18000c8f5  mov     r8, rdi
0x18000c8f8  mov     rdx, [rbx+40h]
0x18000c8fc  add     rdx, 38h ; '8'
0x18000c900  cmp     qword ptr [rdx+18h], 8
0x18000c905  jb      short loc_18000C90A
0x18000c907  mov     rdx, [rdx]
0x18000c90a  mov     byte ptr [rsp+1D0h+dwFlags], cl
0x18000c90e  mov     [rsp+1D0h+dwMilliseconds], r9d
0x18000c913  mov     r9d, [rbx+180h]
0x18000c91a  lea     rcx, [rbp+0D0h+var_120]
0x18000c91e  call    ?GetWSManSubscribeOptions@@YAXAEAV?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@PEBG1KW4_EC_SUBSCRIPTION_CONTENT_FORMAT@@_N@Z; GetWSManSubscribeOptions(std::vector<_WSMAN_OPTION> &,ushort const *,ushort const *,ulong,_EC_SUBSCRIPTION_CONTENT_FORMAT,bool)
0x18000c923  mov     [rbp+0D0h+var_F0], 48h ; 'H'
0x18000c92b  cmp     qword ptr [rdi+18h], 8
0x18000c930  jb      short loc_18000C937
0x18000c932  mov     rax, [rdi]
0x18000c935  jmp     short loc_18000C93A
0x18000c937  mov     rax, rdi
0x18000c93a  mov     [rbp+0D0h+var_E8], rax
0x18000c93e  xorps   xmm0, xmm0
0x18000c941  movdqa  [rbp+0D0h+var_E0], xmm0
0x18000c946  mov     [rbp+0D0h+var_D0], r12
0x18000c94a  mov     [rbp+0D0h+var_C8], r12
0x18000c94e  mov     rax, [rbp+0D0h+var_120+8]
0x18000c952  mov     r15, [rbp+0D0h+var_120]
0x18000c956  sub     rax, r15
0x18000c959  sar     rax, 3
0x18000c95d  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18000c967  imul    rax, rcx
0x18000c96b  mov     [rbp+0D0h+var_C0], eax
0x18000c96e  xor     eax, eax
0x18000c970  mov     [rbp+0D0h+var_BC], eax
0x18000c973  mov     [rbp+0D0h+var_B8], r15
0x18000c977  mov     [rbp+0D0h+var_B0], r12
0x18000c97b  lea     r14, [rbx+0E0h]
0x18000c982  mov     rcx, [r14]; WaitHandle
0x18000c985  test    rcx, rcx
0x18000c988  jz      short loc_18000C995
0x18000c98a  xor     edx, edx; CompletionEvent
0x18000c98c  call    cs:__imp_UnregisterWaitEx
0x18000c992  mov     [r14], r12
0x18000c995  mov     [rsp+1D0h+dwFlags], 8; dwFlags
0x18000c99d  mov     [rsp+1D0h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18000c9a5  mov     r9, rbx; Context
0x18000c9a8  lea     r8, ?SubscribeCompleteCallback@BoundSubscription@@CAXPEAXE@Z; Callback
0x18000c9af  mov     rdx, [rbx+0E8h]; hObject
0x18000c9b6  mov     rcx, r14; phNewWaitObject
0x18000c9b9  call    cs:__imp_RegisterWaitForSingleObject
0x18000c9bf  test    eax, eax
0x18000c9c1  jz      loc_18000CCD6
0x18000c9c7  xorps   xmm0, xmm0
0x18000c9ca  xor     eax, eax
0x18000c9cc  movups  [rbp+0D0h+var_78], xmm0
0x18000c9d0  movups  [rbp+0D0h+var_68], xmm0
0x18000c9d4  movups  [rbp+0D0h+var_58], xmm0
0x18000c9d8  mov     [rbp+0D0h+var_48], rax
0x18000c9df  movsd   xmm0, qword ptr [rbx+184h]
0x18000c9e7  movsd   qword ptr [rbp+0D0h+var_68+8], xmm0
0x18000c9ec  mov     eax, [rbx+18Ch]
0x18000c9f2  mov     dword ptr [rbp+0D0h+var_58], eax
0x18000c9f5  lea     rcx, [rbx+1B0h]
0x18000c9fc  mov     rdx, rdi
0x18000c9ff  call    ?GetDialect@@YAPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; GetDialect(std::wstring const &,std::wstring const &)
0x18000ca04  mov     qword ptr [rbp+0D0h+var_78], rax
0x18000ca08  mov     qword ptr [rbp+0D0h+var_78+8], rsi
0x18000ca0c  movups  xmm0, xmmword ptr [rbp+0D0h+SystemTime.wYear]
0x18000ca13  movdqu  [rbp+0D0h+var_58+4], xmm0
0x18000ca18  mov     eax, [rbx+1F0h]
0x18000ca1e  mov     dword ptr [rbp+0D0h+var_48+4], eax
0x18000ca24  mov     rax, [rsp+1D0h+var_178]
0x18000ca29  mov     qword ptr [rbp+0D0h+var_68], rax
0x18000ca2d  cmp     dword ptr [rbx+0A8h], 2
0x18000ca34  jnz     loc_18000CB2A
0x18000ca3a  mov     [rsp+1D0h+pExceptionObject], r12
0x18000ca3f  mov     [rsp+1D0h+var_168], r12
0x18000ca44  mov     [rbp+0D0h+var_148], r12
0x18000ca48  cmp     [rbx+1A0h], r12
0x18000ca4f  jz      short loc_18000CA67
0x18000ca51  lea     rax, [rbx+190h]
0x18000ca58  cmp     qword ptr [rax+18h], 8
0x18000ca5d  jb      short loc_18000CA62
0x18000ca5f  mov     rax, [rax]
0x18000ca62  mov     [rsp+1D0h+pExceptionObject], rax
0x18000ca67  mov     [rsp+1D0h+var_160], 3Ch ; '<'
0x18000ca6f  mov     [rsp+1D0h+var_15C], 5
0x18000ca77  lea     rax, ?EventsCallback@Subscription@@SAXPEBU_WSMAN_EVENTS_RESULT@@PEBVWSMAN_SENDER_DETAILS_INTERNAL@@PEAUWSMAN_DELIVERY@@PEAX@Z; Subscription::EventsCallback(_WSMAN_EVENTS_RESULT const *,WSMAN_SENDER_DETAILS_INTERNAL const *,WSMAN_DELIVERY *,void *)
0x18000ca7e  mov     [rbp+0D0h+var_150], rax
0x18000ca82  lea     rcx, [rbx+200h]
0x18000ca89  mov     dword ptr [rcx], 1
0x18000ca8f  mov     rax, [rbx+40h]
0x18000ca93  mov     [rbx+208h], rax
0x18000ca9a  lea     rax, [rbx+68h]
0x18000ca9e  cmp     qword ptr [rax+18h], 8
0x18000caa3  jb      short loc_18000CAA8
0x18000caa5  mov     rax, [rax]
0x18000caa8  mov     [rbx+210h], rax
0x18000caaf  mov     [rbp+0D0h+var_140], rcx
0x18000cab3  xorps   xmm0, xmm0
0x18000cab6  xor     eax, eax
0x18000cab8  movups  [rbp+0D0h+var_A0], xmm0
0x18000cabc  movups  [rbp+0D0h+var_90], xmm0
0x18000cac0  mov     [rbp+0D0h+var_80], rax
0x18000cac4  mov     dword ptr [rbp+0D0h+var_A0], 1
0x18000cacb  lea     rax, [rbp+0D0h+var_A0]
0x18000cacf  mov     [rsp+1D0h+var_158], rax
0x18000cad4  lea     rcx, [rbx+128h]
0x18000cadb  lea     rdx, [rbx+130h]
0x18000cae2  mov     rax, [rbx+0E8h]
0x18000cae9  mov     [rsp+1D0h+var_190], rax
0x18000caee  mov     [rsp+1D0h+var_198], rcx
0x18000caf3  mov     qword ptr [rsp+1D0h+var_1A0], rdx
0x18000caf8  lea     rax, [rsp+1D0h+pExceptionObject]
0x18000cafd  mov     qword ptr [rsp+1D0h+dwFlags], rax
0x18000cb02  lea     rax, [rbp+0D0h+var_78]
0x18000cb06  mov     qword ptr [rsp+1D0h+dwMilliseconds], rax
0x18000cb0b  lea     r9, [rbp+0D0h+var_F0]
0x18000cb0f  mov     r8d, 0EA60h
0x18000cb15  mov     edx, [rbx+180h]
0x18000cb1b  mov     rcx, [rbx+120h]
0x18000cb22  call    cs:__imp_WSManCreatePushSubscription
0x18000cb28  jmp     short loc_18000CB74
0x18000cb2a  lea     rcx, [rbx+128h]
0x18000cb31  lea     rdx, [rbx+130h]
0x18000cb38  mov     rax, [rbx+0E8h]
0x18000cb3f  mov     [rsp+1D0h+var_198], rax
0x18000cb44  mov     qword ptr [rsp+1D0h+var_1A0], rcx
0x18000cb49  mov     qword ptr [rsp+1D0h+dwFlags], rdx
0x18000cb4e  lea     rax, [rbp+0D0h+var_78]
0x18000cb52  mov     qword ptr [rsp+1D0h+dwMilliseconds], rax
0x18000cb57  lea     r9, [rbp+0D0h+var_F0]
0x18000cb5b  mov     r8d, 0EA60h
0x18000cb61  mov     edx, [rbx+180h]
0x18000cb67  mov     rcx, [rbx+120h]
0x18000cb6e  call    cs:__imp_WSManCreatePullSubscription
0x18000cb74  test    eax, eax
0x18000cb76  jnz     short loc_18000CBB4
0x18000cb78  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000cb7c  mov     rcx, [r14]; WaitHandle
0x18000cb7f  call    cs:__imp_UnregisterWaitEx
0x18000cb85  mov     [r14], r12
0x18000cb88  mov     r8, [rbx+140h]; struct WSMAN_OBJECT *
0x18000cb8f  mov     edx, [rbx+138h]; unsigned int
0x18000cb95  mov     rcx, rbx; this
0x18000cb98  call    ?RecordLastError@BoundSubscription@@AEAAXKPEAUWSMAN_OBJECT@@@Z; BoundSubscription::RecordLastError(ulong,WSMAN_OBJECT *)
0x18000cb9d  mov     edi, 803380AAh
0x18000cba2  cmp     [rbx+138h], edi
0x18000cba8  jz      short loc_18000CC07
0x18000cbaa  mov     rcx, rbx; this
0x18000cbad  call    ?EnterRetryingState@BoundSubscription@@AEAAXXZ; BoundSubscription::EnterRetryingState(void)
0x18000cbb2  jmp     short loc_18000CBBB
0x18000cbb4  mov     dword ptr [rbx+38h], 1
0x18000cbbb  test    r15, r15
0x18000cbbe  jz      short loc_18000CBC9
0x18000cbc0  mov     rcx, r15; void *
0x18000cbc3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cbc8  nop
0x18000cbc9  lea     rcx, [rbp+0D0h+var_108]
0x18000cbcd  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18000cbd2  nop
0x18000cbd3  lea     rcx, [rbp+0D0h+var_138]
0x18000cbd7  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x18000cbdc  mov     rcx, [rbp+0D0h+var_30]
0x18000cbe3  xor     rcx, rsp; StackCookie
0x18000cbe6  call    __security_check_cookie
0x18000cbeb  lea     r11, [rsp+1D0h+var_20]
0x18000cbf3  mov     rbx, [r11+38h]
0x18000cbf7  mov     rsi, [r11+40h]
0x18000cbfb  mov     rsp, r11
0x18000cbfe  pop     r15
0x18000cc00  pop     r14
0x18000cc02  pop     r12
0x18000cc04  pop     rdi
0x18000cc05  pop     rbp
0x18000cc06  retn
0x18000cc07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc0e  lea     rax, WPP_GLOBAL_Control
0x18000cc15  cmp     rcx, rax
0x18000cc18  jz      short loc_18000CC3E
0x18000cc1a  test    byte ptr [rcx+1Ch], 10h
0x18000cc1e  jz      short loc_18000CC3E
0x18000cc20  cmp     byte ptr [rcx+19h], 2
0x18000cc24  jb      short loc_18000CC3E
0x18000cc26  mov     edx, 2Bh ; '+'
0x18000cc2b  mov     r9d, edi
0x18000cc2e  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000cc35  mov     rcx, [rcx+10h]
  ... truncated ...
```
