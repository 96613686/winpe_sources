# BoundSubscription::EnterReceivingState(void)

- ea: `0x18000c0e8`
- end: `0x18000c2cf`
- name: `?EnterReceivingState@BoundSubscription@@AEAAXXZ`
- size: `487`
- prototype: `void __fastcall(BoundSubscription *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b724`
- `0x18000eaf0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18000c0e8`
- `0x18000c2d8`
- `0x18000f7b0`
- `0x180011a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1b2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c166`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c166`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000c284`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000c284`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000c1a4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000c1a4`
- `WsmSvc!WSManPullEvents` at `0x18000c260`
- `WsmSvc!WSManPullEvents` at `0x18000c260`
- `WsmSvc!WSManCloseSubscriptionHandle` at `0x18000c298`
- `WsmSvc!WSManCloseSubscriptionHandle` at `0x18000c298`

## string_xrefs

- `0x18000c1f4`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
void __fastcall BoundSubscription::EnterReceivingState(BoundSubscription *this)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rax
  HANDLE *v4; // rdi
  DWORD LastError; // ebx
  __int64 v6; // rcx
  void **pExceptionObject; // [rsp+40h] [rbp-48h] BYREF
  char v8; // [rsp+48h] [rbp-40h]
  const char *v9; // [rsp+50h] [rbp-38h]
  __int64 v10; // [rsp+58h] [rbp-30h]
  __int64 v11; // [rsp+60h] [rbp-28h]
  DWORD v12; // [rsp+68h] [rbp-20h]
  int v13; // [rsp+6Ch] [rbp-1Ch]
  int v14; // [rsp+70h] [rbp-18h]

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
  ResetEvent(*((HANDLE *)this + 29));
  if ( *((_DWORD *)this + 42) != 1 )
    goto LABEL_20;
  v4 = (HANDLE *)((char *)this + 224);
  if ( !RegisterWaitForSingleObject(
          (PHANDLE)this + 28,
          *((HANDLE *)this + 29),
          BoundSubscription::ReceiveCompleteCallback,
          this,
          0xFFFFFFFF,
          8u) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, LastError);
    }
    v8 = 0;
    v9 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
    v10 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v11 = 0;
    v12 = LastError;
    v13 = -1;
    v14 = 1816;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( (unsigned int)WSManPullEvents(*((_QWORD *)this + 37), 0, (char *)this + 328, *((_QWORD *)this + 29)) )
  {
LABEL_20:
    *((_DWORD *)this + 14) = 2;
  }
  else
  {
    BoundSubscription::RecordLastError(this, *((_DWORD *)this + 84), *((struct WSMAN_OBJECT **)this + 43));
    UnregisterWaitEx(*v4, 0);
    v6 = *((_QWORD *)this + 37);
    *v4 = 0;
    WSManCloseSubscriptionHandle(v6);
    *((_QWORD *)this + 37) = 0;
    BoundSubscription::EnterRetryingState(this);
  }
}

```

## disassembly

```asm
0x18000c0e8  mov     [rsp+arg_0], rbx
0x18000c0ed  mov     [rsp+arg_8], rbp
0x18000c0f2  push    rdi
0x18000c0f3  sub     rsp, 80h
0x18000c0fa  mov     rbx, rcx
0x18000c0fd  mov     r8, cs:WPP_GLOBAL_Control
0x18000c104  lea     rbp, WPP_GLOBAL_Control
0x18000c10b  cmp     r8, rbp
0x18000c10e  jz      short loc_18000C15F
0x18000c110  test    byte ptr [r8+1Ch], 10h
0x18000c115  jz      short loc_18000C15F
0x18000c117  cmp     byte ptr [r8+19h], 5
0x18000c11c  jb      short loc_18000C15F
0x18000c11e  add     rcx, 48h ; 'H'
0x18000c122  cmp     qword ptr [rcx+18h], 8
0x18000c127  jb      short loc_18000C12C
0x18000c129  mov     rcx, [rcx]
0x18000c12c  mov     rax, [rbx+40h]
0x18000c130  add     rax, 38h ; '8'
0x18000c134  cmp     qword ptr [rax+18h], 8
0x18000c139  jb      short loc_18000C13E
0x18000c13b  mov     rax, [rax]
0x18000c13e  mov     r9d, [rbx+38h]
0x18000c142  mov     edx, 30h ; '0'
0x18000c147  mov     qword ptr [rsp+88h+var_58], rbx; char
0x18000c14c  mov     qword ptr [rsp+88h+dwFlags], rcx; __int64
0x18000c151  mov     rcx, [r8+10h]; LoggerHandle
0x18000c155  mov     qword ptr [rsp+88h+dwMilliseconds], rax; __int64
0x18000c15a  call    WPP_SF_dSSq
0x18000c15f  mov     rcx, [rbx+0E8h]; hEvent
0x18000c166  call    cs:__imp_ResetEvent
0x18000c16c  cmp     dword ptr [rbx+0A8h], 1
0x18000c173  jnz     loc_18000C2B3
0x18000c179  mov     rdx, [rbx+0E8h]; hObject
0x18000c180  lea     rdi, [rbx+0E0h]
0x18000c187  mov     rcx, rdi; phNewWaitObject
0x18000c18a  mov     [rsp+88h+dwFlags], 8; dwFlags
0x18000c192  mov     r9, rbx; Context
0x18000c195  mov     [rsp+88h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18000c19d  lea     r8, ?ReceiveCompleteCallback@BoundSubscription@@CAXPEAXE@Z; Callback
0x18000c1a4  call    cs:__imp_RegisterWaitForSingleObject
0x18000c1aa  test    eax, eax
0x18000c1ac  jnz     loc_18000C249
0x18000c1b2  call    cs:__imp_GetLastError
0x18000c1b8  mov     ebx, eax
0x18000c1ba  mov     eax, 507h
0x18000c1bf  test    ebx, ebx
0x18000c1c1  cmovz   ebx, eax
0x18000c1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1cb  cmp     rcx, rbp
0x18000c1ce  jz      short loc_18000C1F4
0x18000c1d0  test    byte ptr [rcx+1Ch], 10h
0x18000c1d4  jz      short loc_18000C1F4
0x18000c1d6  cmp     byte ptr [rcx+19h], 2
0x18000c1da  jb      short loc_18000C1F4
0x18000c1dc  mov     rcx, [rcx+10h]
0x18000c1e0  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000c1e7  mov     edx, 31h ; '1'
0x18000c1ec  mov     r9d, ebx
0x18000c1ef  call    WPP_SF_D
0x18000c1f4  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000c1fb  mov     [rsp+88h+var_40], 0
0x18000c200  mov     [rsp+88h+var_38], rax
0x18000c205  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000c20c  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000c213  mov     [rsp+88h+var_30], 0
0x18000c21c  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000c221  mov     [rsp+88h+pExceptionObject], rax
0x18000c226  mov     [rsp+88h+var_28], 0
0x18000c22f  mov     [rsp+88h+var_20], ebx
0x18000c233  mov     [rsp+88h+var_1C], 0FFFFFFFFh
0x18000c23b  mov     [rsp+88h+var_18], 718h
0x18000c243  call    _CxxThrowException_0
0x18000c249  mov     r9, [rbx+0E8h]
0x18000c250  lea     r8, [rbx+148h]
0x18000c257  mov     rcx, [rbx+128h]
0x18000c25e  xor     edx, edx
0x18000c260  call    cs:__imp_WSManPullEvents
0x18000c266  test    eax, eax
0x18000c268  jnz     short loc_18000C2B3
0x18000c26a  mov     r8, [rbx+158h]; struct WSMAN_OBJECT *
0x18000c271  mov     rcx, rbx; this
0x18000c274  mov     edx, [rbx+150h]; unsigned int
0x18000c27a  call    ?RecordLastError@BoundSubscription@@AEAAXKPEAUWSMAN_OBJECT@@@Z; BoundSubscription::RecordLastError(ulong,WSMAN_OBJECT *)
0x18000c27f  mov     rcx, [rdi]; WaitHandle
0x18000c282  xor     edx, edx; CompletionEvent
0x18000c284  call    cs:__imp_UnregisterWaitEx
0x18000c28a  mov     rcx, [rbx+128h]
0x18000c291  mov     qword ptr [rdi], 0
0x18000c298  call    cs:__imp_WSManCloseSubscriptionHandle
0x18000c29e  mov     rcx, rbx; this
0x18000c2a1  mov     qword ptr [rbx+128h], 0
0x18000c2ac  call    ?EnterRetryingState@BoundSubscription@@AEAAXXZ; BoundSubscription::EnterRetryingState(void)
0x18000c2b1  jmp     short loc_18000C2BA
0x18000c2b3  mov     dword ptr [rbx+38h], 2
0x18000c2ba  lea     r11, [rsp+88h+var_8]
0x18000c2c2  mov     rbx, [r11+10h]
0x18000c2c6  mov     rbp, [r11+18h]
0x18000c2ca  mov     rsp, r11
0x18000c2cd  pop     rdi
0x18000c2ce  retn
```
