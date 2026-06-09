# WFDSConMgr::CEventWrapper::CEventWrapper(bool,bool)

- ea: `0x18005dc28`
- end: `0x18005dc9a`
- name: `??0CEventWrapper@WFDSConMgr@@QEAA@_N0@Z`
- size: `114`
- prototype: `WFDSConMgr::CEventWrapper *__fastcall(WFDSConMgr::CEventWrapper *this, unsigned __int8, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004cdc`
- `0x180030404`

## callees

- `0x18005c888`
- `0x18005dc28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dc52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dc52`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005dc44`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005dc44`

## string_xrefs

- `0x18005dc64`: `CreateEvent failed`

## pseudocode

```c
WFDSConMgr::CEventWrapper *__fastcall WFDSConMgr::CEventWrapper::CEventWrapper(
        WFDSConMgr::CEventWrapper *this,
        unsigned __int8 a2,
        unsigned __int8 a3)
{
  HANDLE EventW; // rax
  char LastError; // al

  *(_QWORD *)this = 0;
  EventW = CreateEventW(0, a2, a3, 0);
  *(_QWORD *)this = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    WFDSConMgr::CException::Throw(
      LastError,
      "WFDSConMgr::CEventWrapper::CEventWrapper",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\util\\src\\event.cpp",
      38,
      L"CreateEvent failed",
      this);
  }
  return this;
}

```

## disassembly

```asm
0x18005dc28  push    rbx
0x18005dc2a  sub     rsp, 30h
0x18005dc2e  mov     rbx, rcx
0x18005dc31  mov     qword ptr [rcx], 0
0x18005dc38  xor     ecx, ecx; lpEventAttributes
0x18005dc3a  movzx   r8d, r8b; bInitialState
0x18005dc3e  movzx   edx, dl; bManualReset
0x18005dc41  xor     r9d, r9d; lpName
0x18005dc44  call    cs:__imp_CreateEventW
0x18005dc4a  mov     [rbx], rax
0x18005dc4d  test    rax, rax
0x18005dc50  jnz     short loc_18005DC91
0x18005dc52  call    cs:__imp_GetLastError
0x18005dc58  test    eax, eax
0x18005dc5a  jle     short loc_18005DC64
0x18005dc5c  movzx   eax, ax
0x18005dc5f  or      eax, 80070000h
0x18005dc64  lea     rcx, aCreateeventFai; "CreateEvent failed"
0x18005dc6b  mov     [rsp+38h+var_10], rbx; void *
0x18005dc70  mov     [rsp+38h+var_18], rcx; unsigned __int16 *
0x18005dc75  lea     r8, aOnecoreuapNetW_7; "onecoreuap\\net\\wlan\\wfdsconmgr\\util"...
0x18005dc7c  mov     ecx, eax; char
0x18005dc7e  lea     rdx, aWfdsconmgrCeve_2; "WFDSConMgr::CEventWrapper::CEventWrappe"...
0x18005dc85  mov     r9d, 26h ; '&'; char
0x18005dc8b  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18005dc91  mov     rax, rbx
0x18005dc94  add     rsp, 30h
0x18005dc98  pop     rbx
0x18005dc99  retn
```
