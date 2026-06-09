# SynchronizationEventHandle::SynchronizationEventHandle(void)

- ea: `0x1800587f4`
- end: `0x18005896f`
- name: `??0SynchronizationEventHandle@@QEAA@XZ`
- size: `379`
- prototype: `SynchronizationEventHandle *__fastcall(SynchronizationEventHandle *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180058f70`

## callees

- `0x180001f78`
- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x1800587f4`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005888b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005888b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180058878`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180058878`

## string_xrefs

- `0x18005889e`: `SynchronizationEventHandle:: failed to create event handle. Error = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SynchronizationEventHandle *__fastcall SynchronizationEventHandle::SynchronizationEventHandle(
        SynchronizationEventHandle *this)
{
  HANDLE EventA; // rax
  DWORD LastError; // ebx
  ulong pExceptionObject; // [rsp+20h] [rbp-828h] BYREF
  int v6; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v7[2044]; // [rsp+34h] [rbp-814h] BYREF

  *(_QWORD *)this = &SynchronizationEventHandle::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids);
  }
  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  EventA = CreateEventA(0, 1, 0, 0);
  *((_QWORD *)this + 1) = EventA;
  if ( !EventA )
  {
    LastError = GetLastError();
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v6) = 0;
      FormatRRASErrorString(&v6, L"SynchronizationEventHandle:: failed to create event handle. Error = %d", LastError);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v6);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids, LastError);
    }
    pExceptionObject = LastError;
    throw &pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids);
  }
  return this;
}

```

## disassembly

```asm
0x1800587f4  mov     [rsp+arg_8], rbx
0x1800587f9  push    rbp
0x1800587fa  sub     rsp, 840h
0x180058801  mov     rax, cs:__security_cookie
0x180058808  xor     rax, rsp
0x18005880b  mov     [rsp+848h+var_18], rax
0x180058813  lea     rax, ??_7SynchronizationEventHandle@@6B@; const SynchronizationEventHandle::`vftable'
0x18005881a  mov     rbx, rcx
0x18005881d  mov     [rcx], rax
0x180058820  mov     rcx, cs:WPP_GLOBAL_Control
0x180058827  lea     rbp, WPP_GLOBAL_Control
0x18005882e  cmp     rcx, rbp
0x180058831  jz      short loc_180058854
0x180058833  test    byte ptr [rcx+1Ch], 1
0x180058837  jz      short loc_180058854
0x180058839  cmp     byte ptr [rcx+19h], 6
0x18005883d  jb      short loc_180058854
0x18005883f  mov     rcx, [rcx+10h]
0x180058843  lea     r8, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids
0x18005884a  mov     edx, 0Ah
0x18005884f  call    WPP_SF_
0x180058854  xor     eax, eax
0x180058856  lea     rcx, [rsp+848h+var_814]; void *
0x18005885b  xor     edx, edx; Val
0x18005885d  mov     [rsp+848h+var_818], eax
0x180058861  mov     r8d, 7FCh; Size
0x180058867  call    memset_0
0x18005886c  xor     r9d, r9d; lpName
0x18005886f  xor     r8d, r8d; bInitialState
0x180058872  xor     ecx, ecx; lpEventAttributes
0x180058874  lea     edx, [r9+1]; bManualReset
0x180058878  call    cs:__imp_CreateEventA
0x18005887e  mov     [rbx+8], rax
0x180058882  test    rax, rax
0x180058885  jnz     loc_18005891E
0x18005888b  call    cs:__imp_GetLastError
0x180058891  test    cs:byte_1800AA941, 4
0x180058898  mov     ebx, eax
0x18005889a  jz      short loc_1800588D8
0x18005889c  xor     eax, eax
0x18005889e  lea     rdx, aSynchronizatio_9; "SynchronizationEventHandle:: failed to "...
0x1800588a5  mov     r8d, ebx
0x1800588a8  mov     word ptr [rsp+848h+var_818], ax
0x1800588ad  lea     rcx, [rsp+848h+var_818]
0x1800588b2  call    FormatRRASErrorString
0x1800588b7  test    cs:byte_1800AA941, 4
0x1800588be  jz      short loc_1800588D8
0x1800588c0  lea     r8, [rsp+848h+var_818]
0x1800588c5  lea     rdx, RasVpnIkeTraceError
0x1800588cc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800588d3  call    McTemplateU0z_EventWriteTransfer
0x1800588d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800588df  cmp     rcx, rbp
0x1800588e2  jz      short loc_180058908
0x1800588e4  test    byte ptr [rcx+1Ch], 1
0x1800588e8  jz      short loc_180058908
0x1800588ea  cmp     byte ptr [rcx+19h], 6
0x1800588ee  jb      short loc_180058908
0x1800588f0  mov     rcx, [rcx+10h]
0x1800588f4  lea     r8, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids
0x1800588fb  mov     edx, 0Bh
0x180058900  mov     r9d, ebx
0x180058903  call    WPP_SF_d
0x180058908  lea     rdx, _TI1K; pThrowInfo
0x18005890f  mov     [rsp+848h+pExceptionObject], ebx
0x180058913  lea     rcx, [rsp+848h+pExceptionObject]; pExceptionObject
0x180058918  call    _CxxThrowException_0
0x18005891e  mov     rcx, cs:WPP_GLOBAL_Control
0x180058925  cmp     rcx, rbp
0x180058928  jz      short loc_18005894B
0x18005892a  test    byte ptr [rcx+1Ch], 1
0x18005892e  jz      short loc_18005894B
0x180058930  cmp     byte ptr [rcx+19h], 6
0x180058934  jb      short loc_18005894B
0x180058936  mov     rcx, [rcx+10h]
0x18005893a  lea     r8, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids
0x180058941  mov     edx, 0Ch
0x180058946  call    WPP_SF_
0x18005894b  mov     rax, rbx
0x18005894e  mov     rcx, [rsp+848h+var_18]
0x180058956  xor     rcx, rsp; StackCookie
0x180058959  call    __security_check_cookie
0x18005895e  mov     rbx, [rsp+848h+arg_8]
0x180058966  add     rsp, 840h
0x18005896d  pop     rbp
0x18005896e  retn
```
