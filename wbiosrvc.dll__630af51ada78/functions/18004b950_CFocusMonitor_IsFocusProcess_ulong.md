# CFocusMonitor::IsFocusProcess(ulong)

- ea: `0x18004b950`
- end: `0x18004badf`
- name: `?IsFocusProcess@CFocusMonitor@@SA_NK@Z`
- size: `399`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b7c0`
- `0x18004bc50`

## callees

- `0x180011008`
- `0x1800110f0`
- `0x180028af0`
- `0x18002b7c0`
- `0x18002d3b4`
- `0x1800332c0`
- `0x18004b950`
- `0x180068f60`
- `0x180091cc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004ba03`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004ba03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ba76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ba76`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004ba51`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004ba51`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CFocusMonitor::IsFocusProcess(int a1)
{
  struct CFocusMonitor *v2; // rax
  bool v3; // zf
  char v4; // bl
  __int64 **v5; // rax
  __int64 *i; // rbx
  struct CFocusMonitor *v7; // rax
  struct CFocusMonitor *v8; // rax
  unsigned int v9; // edx
  struct CFocusMonitor *v10; // rax
  BOOL v11; // ebx
  struct CFocusMonitor *v12; // rax
  __int64 v13; // r9
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-40h] BYREF
  __int64 *v16; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v17[8]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h] BYREF
  int Buffer; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+54h] [rbp-1Ch]
  int v21; // [rsp+5Ch] [rbp-14h]

  v2 = CFocusMonitor::Instance();
  winbio::lockable_object::lock_exclusive(v2, v17);
  if ( *((_DWORD *)CFocusMonitor::Instance() + 15) )
  {
    v3 = *((_DWORD *)CFocusMonitor::Instance() + 15) == a1;
  }
  else
  {
    if ( *((_BYTE *)CFocusMonitor::Instance() + 16) )
    {
      v5 = (__int64 **)*((_QWORD *)CFocusMonitor::Instance() + 3);
      for ( i = *v5; ; i = (__int64 *)*i )
      {
        if ( i == (__int64 *)v5 )
          goto LABEL_13;
        if ( *((_DWORD *)i + 4) == a1 )
          break;
      }
      Buffer = 0;
      v20 = 0;
      v21 = 0;
      NumberOfBytesRead = 0;
      v18 = *((_QWORD *)CFocusMonitor::Instance() + 6);
      SetEvent(*(HANDLE *)(i[3] + 8));
      v16 = &v18;
      v7 = CFocusMonitor::Instance();
      winbio::watchdog::SetTimeoutAction__lambda_00373b684e3b6e4cd33eeec1107ce061___((char *)v7 + 64, &v16);
      v8 = CFocusMonitor::Instance();
      winbio::watchdog::Start((struct CFocusMonitor *)((char *)v8 + 64), v9);
      v10 = CFocusMonitor::Instance();
      v11 = ReadFile(*((HANDLE *)v10 + 6), &Buffer, 0x10u, &NumberOfBytesRead, 0);
      v12 = CFocusMonitor::Instance();
      winbio::watchdog::Stop((PTP_TIMER *)v12 + 8);
      if ( v11 )
      {
        if ( NumberOfBytesRead >= 0x10 && HIDWORD(v20) == a1 && v21 )
        {
          v4 = 1;
          goto LABEL_14;
        }
      }
      else if ( (unsigned int)dword_18010F170 > 2 )
      {
        LODWORD(v16) = GetLastError();
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18010F170,
          (unsigned __int8 *)&unk_1800EF900,
          0,
          v13,
          (__int64)&v16);
      }
LABEL_13:
      v4 = 0;
      goto LABEL_14;
    }
    v3 = *(_DWORD *)(**((_QWORD **)CFocusMonitor::Instance() + 3) + 16LL) == a1;
  }
  v4 = v3;
LABEL_14:
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v17);
  return v4;
}

```

## disassembly

```asm
0x18004b950  mov     [rsp-8+arg_0], rbx
0x18004b955  mov     [rsp-8+arg_8], rdi
0x18004b95a  push    rbp
0x18004b95b  mov     rbp, rsp
0x18004b95e  sub     rsp, 70h
0x18004b962  mov     rax, cs:__security_cookie
0x18004b969  xor     rax, rsp
0x18004b96c  mov     [rbp+var_10], rax
0x18004b970  mov     edi, ecx
0x18004b972  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18004b977  lea     rdx, [rbp+var_30]
0x18004b97b  mov     rcx, rax
0x18004b97e  call    ?lock_exclusive@lockable_object@winbio@@QEBA?AVSyncLockExclusive@Details@Wrappers@WRL@Microsoft@@XZ; winbio::lockable_object::lock_exclusive(void)
0x18004b983  nop
0x18004b984  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18004b989  cmp     dword ptr [rax+3Ch], 0
0x18004b98d  jz      short loc_18004B9A0
0x18004b98f  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18004b994  nop
0x18004b995  cmp     [rax+3Ch], edi
0x18004b998  setz    bl
0x18004b99b  jmp     loc_18004BAA0
0x18004b9a0  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18004b9a5  cmp     byte ptr [rax+10h], 0
0x18004b9a9  jnz     short loc_18004B9BC
0x18004b9ab  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18004b9b0  mov     rcx, [rax+18h]
0x18004b9b4  mov     rax, [rcx]
0x18004b9b7  cmp     [rax+10h], edi
0x18004b9ba  jmp     short loc_18004B998
0x18004b9bc  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18004b9c1  mov     rax, [rax+18h]
0x18004b9c5  mov     rbx, [rax]
0x18004b9c8  cmp     rbx, rax
0x18004b9cb  jz      loc_18004BA9E
0x18004b9d1  cmp     [rbx+10h], edi
0x18004b9d4  jz      short loc_18004B9DB
0x18004b9d6  mov     rbx, [rbx]
0x18004b9d9  jmp     short loc_18004B9C8
0x18004b9db  mov     [rbp+Buffer], 0
0x18004b9e2  xor     eax, eax
0x18004b9e4  mov     [rbp+var_1C], rax
0x18004b9e8  mov     [rbp+var_14], eax
0x18004b9eb  mov     [rbp+NumberOfBytesRead], eax
0x18004b9ee  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18004b9f3  mov     rcx, [rax+30h]
0x18004b9f7  mov     [rbp+var_28], rcx
0x18004b9fb  mov     rcx, [rbx+18h]
0x18004b9ff  mov     rcx, [rcx+8]; hEvent
0x18004ba03  call    cs:__imp_SetEvent
0x18004ba09  lea     rax, [rbp+var_28]
0x18004ba0d  mov     [rbp+var_38], rax
0x18004ba11  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18004ba16  lea     rcx, [rax+40h]
0x18004ba1a  lea     rdx, [rbp+var_38]
0x18004ba1e  call    winbio__watchdog__SetTimeoutAction__lambda_00373b684e3b6e4cd33eeec1107ce061___
0x18004ba23  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18004ba28  lea     rcx, [rax+40h]; this
0x18004ba2c  call    ?Start@watchdog@winbio@@QEAAXK@Z; winbio::watchdog::Start(ulong)
0x18004ba31  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18004ba36  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x18004ba3f  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004ba43  mov     r8d, 10h; nNumberOfBytesToRead
0x18004ba49  lea     rdx, [rbp+Buffer]; lpBuffer
0x18004ba4d  mov     rcx, [rax+30h]; hFile
0x18004ba51  call    cs:__imp_ReadFile
0x18004ba57  mov     ebx, eax
0x18004ba59  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18004ba5e  lea     rcx, [rax+40h]; this
0x18004ba62  call    ?Stop@watchdog@winbio@@QEAAXXZ; winbio::watchdog::Stop(void)
0x18004ba67  test    ebx, ebx
0x18004ba69  jnz     short loc_18004BAC9
0x18004ba6b  mov     eax, cs:dword_18010F170
0x18004ba71  cmp     eax, 2
0x18004ba74  jbe     short loc_18004BA9E
0x18004ba76  call    cs:__imp_GetLastError
0x18004ba7c  mov     dword ptr [rbp+var_38], eax
0x18004ba7f  lea     rax, [rbp+var_38]
0x18004ba83  mov     [rsp+70h+lpOverlapped], rax
0x18004ba88  xor     r8d, r8d
0x18004ba8b  lea     rdx, unk_1800EF900
0x18004ba92  lea     rcx, dword_18010F170
0x18004ba99  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004ba9e  xor     bl, bl
0x18004baa0  lea     rcx, [rbp+var_30]; this
0x18004baa4  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18004baa9  mov     al, bl
0x18004baab  mov     rcx, [rbp+var_10]
0x18004baaf  xor     rcx, rsp; StackCookie
0x18004bab2  call    __security_check_cookie
0x18004bab7  lea     r11, [rsp+70h+var_s0]
0x18004babc  mov     rbx, [r11+10h]
0x18004bac0  mov     rdi, [r11+18h]
0x18004bac4  mov     rsp, r11
0x18004bac7  pop     rbp
0x18004bac8  retn
0x18004bac9  cmp     [rbp+NumberOfBytesRead], 10h
0x18004bacd  jb      short loc_18004BA9E
0x18004bacf  cmp     dword ptr [rbp+var_1C+4], edi
0x18004bad2  jnz     short loc_18004BA9E
0x18004bad4  cmp     [rbp+var_14], 0
0x18004bad8  jz      short loc_18004BA9E
0x18004bada  mov     bl, 1
0x18004badc  jmp     short loc_18004BAA0
```
