# BoundSubscription::ContinueReceiveEvents(void)

- ea: `0x18000b724`
- end: `0x18000b887`
- name: `?ContinueReceiveEvents@BoundSubscription@@AEAAXXZ`
- size: `355`
- prototype: `void __fastcall(BoundSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000f670`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180006334`
- `0x18000b724`
- `0x18000c0e8`
- `0x18000f110`
- `0x18000fc80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7f1`
- `WsmSvc!WSManCloseEnumeratorHandle` at `0x18000b7bf`
- `WsmSvc!WSManCloseEnumeratorHandle` at `0x18000b7bf`
- `WsmSvc!WSManCloseObjectHandle` at `0x18000b792`
- `WsmSvc!WSManCloseObjectHandle` at `0x18000b792`
- `WsmSvc!WSManEnumeratorNextObject` at `0x18000b75c`
- `WsmSvc!WSManEnumeratorNextObject` at `0x18000b75c`

## string_xrefs

- `0x18000b83f`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
void __fastcall BoundSubscription::ContinueReceiveEvents(BoundSubscription *this)
{
  unsigned int v2; // esi
  struct WSMAN_OBJECT **i; // rdi
  const unsigned __int16 *v4; // r8
  DWORD LastError; // ebx
  __int128 v6; // [rsp+20h] [rbp-58h] BYREF
  __int64 v7; // [rsp+30h] [rbp-48h]
  void **pExceptionObject; // [rsp+38h] [rbp-40h] BYREF
  char v9; // [rsp+40h] [rbp-38h]
  const char *v10; // [rsp+48h] [rbp-30h]
  __int64 v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  DWORD v13; // [rsp+60h] [rbp-18h]
  int v14; // [rsp+64h] [rbp-14h]
  int v15; // [rsp+68h] [rbp-10h]

  v6 = 0;
  v7 = 0;
  v2 = 0;
  for ( i = (struct WSMAN_OBJECT **)((char *)this + 376);
        *i || (unsigned int)WSManEnumeratorNextObject(*((_QWORD *)this + 44), i);
        *i = 0 )
  {
    v4 = (const unsigned __int16 *)((char *)this + 104);
    if ( *((_QWORD *)this + 16) >= 8u )
      v4 = *(const unsigned __int16 **)v4;
    Subscription::ProcessEvent(*((Subscription **)this + 8), *i, v4);
    ++v2;
    *((_DWORD *)this + 62) = 0;
    WSManCloseObjectHandle(*i);
  }
  if ( GetLastError() != 259 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, LastError);
    }
    v9 = 0;
    v10 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
    v11 = 0;
    v12 = 0;
    v13 = LastError;
    v14 = -1;
    v15 = 1906;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  BoundSubscription::SaveBookmark(this, v2);
  WSManCloseEnumeratorHandle(*((_QWORD *)this + 44));
  *(_OWORD *)((char *)this + 328) = 0;
  *(_OWORD *)((char *)this + 344) = 0;
  BoundSubscription::EnterReceivingState(this);
  std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(&v6);
}

```

## disassembly

```asm
0x18000b724  push    rbp
0x18000b726  push    rbx
0x18000b727  push    rsi
0x18000b728  push    rdi
0x18000b729  mov     rbp, rsp
0x18000b72c  sub     rsp, 78h
0x18000b730  mov     rbx, rcx
0x18000b733  xorps   xmm0, xmm0
0x18000b736  movdqu  [rbp+var_58], xmm0
0x18000b73b  mov     [rbp+var_48], 0
0x18000b743  xor     esi, esi
0x18000b745  lea     rdi, [rcx+178h]
0x18000b74c  cmp     qword ptr [rdi], 0
0x18000b750  jnz     short loc_18000B766
0x18000b752  mov     rdx, rdi
0x18000b755  mov     rcx, [rbx+160h]
0x18000b75c  call    cs:__imp_WSManEnumeratorNextObject
0x18000b762  test    eax, eax
0x18000b764  jz      short loc_18000B7A1
0x18000b766  lea     r8, [rbx+68h]
0x18000b76a  cmp     qword ptr [rbx+80h], 8
0x18000b772  jb      short loc_18000B777
0x18000b774  mov     r8, [r8]; unsigned __int16 *
0x18000b777  mov     rdx, [rdi]; struct WSMAN_OBJECT *
0x18000b77a  mov     rcx, [rbx+40h]; this
0x18000b77e  call    ?ProcessEvent@Subscription@@QEAAXPEAUWSMAN_OBJECT@@PEBG@Z; Subscription::ProcessEvent(WSMAN_OBJECT *,ushort const *)
0x18000b783  inc     esi
0x18000b785  mov     dword ptr [rbx+0F8h], 0
0x18000b78f  mov     rcx, [rdi]
0x18000b792  call    cs:__imp_WSManCloseObjectHandle
0x18000b798  mov     qword ptr [rdi], 0
0x18000b79f  jmp     short loc_18000B74C
0x18000b7a1  call    cs:__imp_GetLastError
0x18000b7a7  cmp     eax, 103h
0x18000b7ac  jnz     short loc_18000B7F1
0x18000b7ae  mov     edx, esi; unsigned int
0x18000b7b0  mov     rcx, rbx; this
0x18000b7b3  call    ?SaveBookmark@BoundSubscription@@AEAAXK@Z; BoundSubscription::SaveBookmark(ulong)
0x18000b7b8  mov     rcx, [rbx+160h]
0x18000b7bf  call    cs:__imp_WSManCloseEnumeratorHandle
0x18000b7c5  xorps   xmm0, xmm0
0x18000b7c8  movups  xmmword ptr [rbx+148h], xmm0
0x18000b7cf  movups  xmmword ptr [rbx+158h], xmm0
0x18000b7d6  mov     rcx, rbx; this
0x18000b7d9  call    ?EnterReceivingState@BoundSubscription@@AEAAXXZ; BoundSubscription::EnterReceivingState(void)
0x18000b7de  nop
0x18000b7df  lea     rcx, [rbp+var_58]
0x18000b7e3  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x18000b7e8  add     rsp, 78h
0x18000b7ec  pop     rdi
0x18000b7ed  pop     rsi
0x18000b7ee  pop     rbx
0x18000b7ef  pop     rbp
0x18000b7f0  retn
0x18000b7f1  call    cs:__imp_GetLastError
0x18000b7f7  nop
0x18000b7f8  mov     ebx, eax
0x18000b7fa  mov     eax, 507h
0x18000b7ff  test    ebx, ebx
0x18000b801  cmovz   ebx, eax
0x18000b804  lea     rax, WPP_GLOBAL_Control
0x18000b80b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b812  cmp     rcx, rax
0x18000b815  jz      short loc_18000B83B
0x18000b817  test    byte ptr [rcx+1Ch], 10h
0x18000b81b  jz      short loc_18000B83B
0x18000b81d  cmp     byte ptr [rcx+19h], 2
0x18000b821  jb      short loc_18000B83B
0x18000b823  mov     edx, 32h ; '2'
0x18000b828  mov     r9d, ebx
0x18000b82b  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000b832  mov     rcx, [rcx+10h]
0x18000b836  call    WPP_SF_D
0x18000b83b  mov     [rbp+var_38], 0
0x18000b83f  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000b846  mov     [rbp+var_30], rax
0x18000b84a  mov     [rbp+var_28], 0
0x18000b852  mov     [rbp+var_20], 0
0x18000b85a  mov     [rbp+var_18], ebx
0x18000b85d  mov     [rbp+var_14], 0FFFFFFFFh
0x18000b864  mov     [rbp+var_10], 772h
0x18000b86b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000b872  mov     [rbp+pExceptionObject], rax
0x18000b876  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000b87d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b881  call    _CxxThrowException_0
```
