# RemoteMessageThread

- ea: `0x1800120c0`
- end: `0x1800122d5`
- name: `RemoteMessageThread`
- size: `533`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000dda0`
- `0x1800120c0`
- `0x1800138c5`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180012278`
- `ntdll!NtWaitForSingleObject` at `0x180012278`
- `ntdll!RtlExitUserThread` at `0x1800122c8`
- `ntdll!RtlExitUserThread` at `0x1800122c8`
- `ntdll!NtResetEvent` at `0x18001228f`
- `ntdll!NtResetEvent` at `0x18001228f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800121b9`
- `ntdll!RtlLeaveCriticalSection` at `0x180012256`
- `ntdll!RtlLeaveCriticalSection` at `0x1800121b9`
- `ntdll!RtlLeaveCriticalSection` at `0x180012256`
- `ntdll!RtlInitUnicodeString` at `0x1800121cd`
- `ntdll!RtlInitUnicodeString` at `0x1800121e1`
- `ntdll!RtlInitUnicodeString` at `0x1800121cd`
- `ntdll!RtlInitUnicodeString` at `0x1800121e1`
- `ntdll!NtCreateEvent` at `0x180012126`
- `ntdll!NtCreateEvent` at `0x180012126`
- `ntdll!RtlEnterCriticalSection` at `0x180012148`
- `ntdll!RtlEnterCriticalSection` at `0x180012148`
- `ntdll!NtClose` at `0x1800122af`
- `ntdll!NtClose` at `0x1800122af`

## pseudocode

```c
void RemoteMessageThread()
{
  int v0; // edi
  __int64 v1; // rax
  __int64 *v2; // rbx
  __int64 v3; // rcx
  __int64 *v4; // rdx
  __int64 v5; // rbx
  __int64 *v6; // rcx
  __int32 v7; // eax
  __int128 v8; // xmm0
  struct _UNICODE_STRING v9; // [rsp+30h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-49h] BYREF
  __m256i v12; // [rsp+80h] [rbp-19h] BYREF
  __int64 v13; // [rsp+A0h] [rbp+7h]
  int v14; // [rsp+A8h] [rbp+Fh]
  int v15; // [rsp+B8h] [rbp+1Fh]
  int v16; // [rsp+C0h] [rbp+27h]
  int v17; // [rsp+C4h] [rbp+2Bh]
  struct _UNICODE_STRING *v18; // [rsp+C8h] [rbp+2Fh]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+D0h] [rbp+37h]
  __int64 v20; // [rsp+D8h] [rbp+3Fh]

  memset_0(&v12, 0, 0x70u);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v9 = 0;
  DestinationString = 0;
  v0 = NtCreateEvent(&g_hDoMessageEvent, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( v0 >= 0 )
  {
    while ( !gbExitInProgress )
    {
      RtlEnterCriticalSection(&gcsUserSrv);
      v1 = gpchiList;
      if ( !gpchiList )
        goto LABEL_15;
      v2 = &gpchiList;
      v3 = gpchiList;
      while ( 1 )
      {
        v4 = (__int64 *)(v3 + 88);
        v3 = *(_QWORD *)(v3 + 88);
        if ( !v3 )
          break;
        v2 = v4;
      }
      v5 = *v2;
      if ( v5 )
      {
        v6 = &gpchiList;
        while ( v1 && v1 != v5 )
        {
          v6 = (__int64 *)(v1 + 88);
          v1 = *(_QWORD *)(v1 + 88);
        }
        if ( *v6 )
          *v6 = *(_QWORD *)(v5 + 88);
        RtlLeaveCriticalSection(&gcsUserSrv);
        RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v5 + 24));
        RtlInitUnicodeString(&v9, *(PCWSTR *)(v5 + 32));
        v14 = 1073741848;
        v13 = 0;
        v7 = *(_DWORD *)(v5 + 16);
        *(_OWORD *)&v12.m256i_u64[2] = 0;
        v12.m256i_i32[6] = v7;
        *(_OWORD *)v12.m256i_i8 = 0;
        v8 = *(_OWORD *)v5;
        v18 = &v9;
        p_DestinationString = &DestinationString;
        v20 = *(unsigned int *)(v5 + 40);
        *(_OWORD *)&v12.m256i_u64[1] = v8;
        v16 = 3;
        v17 = 3;
        v15 = 1;
        UserHardErrorEx(0, (__int64)&v12, v5);
      }
      else
      {
LABEL_15:
        RtlLeaveCriticalSection(&gcsUserSrv);
      }
      if ( !gpchiList )
      {
        v0 = NtWaitForSingleObject(g_hDoMessageEvent, 0, 0);
        NtResetEvent(g_hDoMessageEvent, 0);
      }
    }
    NtClose(g_hDoMessageEvent);
    g_hDoMessageEvent = 0;
  }
  RtlExitUserThread(v0);
  __debugbreak();
  JUMPOUT(0x1800122D5LL);
}

```

## disassembly

```asm
0x1800120c0  mov     [rsp-8+arg_0], rbx
0x1800120c5  mov     [rsp-8+arg_8], rdi
0x1800120ca  push    rbp
0x1800120cb  lea     rbp, [rsp-57h]
0x1800120d0  sub     rsp, 0F0h
0x1800120d7  xor     edx, edx; Val
0x1800120d9  lea     rcx, [rbp+57h+var_70]; void *
0x1800120dd  lea     r8d, [rdx+70h]; Size
0x1800120e1  call    memset_0
0x1800120e6  xor     eax, eax
0x1800120e8  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800120f0  xorps   xmm0, xmm0
0x1800120f3  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], rax
0x1800120f7  xorps   xmm1, xmm1
0x1800120fa  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800120fe  xor     r9d, r9d; EventType
0x180012101  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180012105  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180012109  mov     [rsp+0F0h+InitialState], al; InitialState
0x18001210d  mov     edx, 1F0003h; DesiredAccess
0x180012112  lea     rcx, g_hDoMessageEvent; EventHandle
0x180012119  movups  xmmword ptr [rbp+57h+var_C0.Length], xmm0
0x18001211d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180012121  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180012126  call    cs:__imp_NtCreateEvent
0x18001212d  nop     dword ptr [rax+rax+00h]
0x180012132  mov     edi, eax
0x180012134  test    eax, eax
0x180012136  js      loc_1800122C6
0x18001213c  jmp     loc_18001229B
0x180012141  lea     rcx, gcsUserSrv; CriticalSection
0x180012148  call    cs:__imp_RtlEnterCriticalSection
0x18001214f  nop     dword ptr [rax+rax+00h]
0x180012154  mov     rax, cs:gpchiList
0x18001215b  test    rax, rax
0x18001215e  jz      loc_18001224F
0x180012164  lea     rbx, gpchiList
0x18001216b  mov     rcx, rax
0x18001216e  lea     rdx, [rcx+58h]
0x180012172  mov     rcx, [rdx]
0x180012175  test    rcx, rcx
0x180012178  jz      short loc_18001217F
0x18001217a  mov     rbx, rdx
0x18001217d  jmp     short loc_18001216E
0x18001217f  mov     rbx, [rbx]
0x180012182  test    rbx, rbx
0x180012185  jz      loc_18001224F
0x18001218b  lea     rcx, gpchiList
0x180012192  jmp     short loc_1800121A0
0x180012194  cmp     rax, rbx
0x180012197  jz      short loc_1800121A5
0x180012199  lea     rcx, [rax+58h]
0x18001219d  mov     rax, [rcx]
0x1800121a0  test    rax, rax
0x1800121a3  jnz     short loc_180012194
0x1800121a5  cmp     qword ptr [rcx], 0
0x1800121a9  jz      short loc_1800121B2
0x1800121ab  mov     rax, [rbx+58h]
0x1800121af  mov     [rcx], rax
0x1800121b2  lea     rcx, gcsUserSrv; CriticalSection
0x1800121b9  call    cs:__imp_RtlLeaveCriticalSection
0x1800121c0  nop     dword ptr [rax+rax+00h]
0x1800121c5  mov     rdx, [rbx+18h]; SourceString
0x1800121c9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800121cd  call    cs:__imp_RtlInitUnicodeString
0x1800121d4  nop     dword ptr [rax+rax+00h]
0x1800121d9  mov     rdx, [rbx+20h]; SourceString
0x1800121dd  lea     rcx, [rbp+57h+var_C0]; DestinationString
0x1800121e1  call    cs:__imp_RtlInitUnicodeString
0x1800121e8  nop     dword ptr [rax+rax+00h]
0x1800121ed  xor     eax, eax
0x1800121ef  mov     [rbp+57h+var_48], 40000018h
0x1800121f6  mov     [rbp+57h+var_50], rax
0x1800121fa  lea     rdx, [rbp+57h+var_70]
0x1800121fe  mov     eax, [rbx+10h]
0x180012201  xorps   xmm0, xmm0
0x180012204  movups  [rbp+57h+var_60], xmm0
0x180012208  mov     dword ptr [rbp+57h+var_60+8], eax
0x18001220b  mov     r8, rbx
0x18001220e  movups  [rbp+57h+var_70], xmm0
0x180012212  lea     rax, [rbp+57h+var_C0]
0x180012216  xor     ecx, ecx
0x180012218  movups  xmm0, xmmword ptr [rbx]
0x18001221b  mov     [rbp+57h+var_28], rax
0x18001221f  lea     rax, [rbp+57h+DestinationString]
0x180012223  mov     [rbp+57h+var_20], rax
0x180012227  mov     eax, [rbx+28h]
0x18001222a  mov     [rbp+57h+var_18], rax
0x18001222e  movdqu  [rbp+57h+var_70+8], xmm0
0x180012233  mov     [rbp+57h+var_30], 3
0x18001223a  mov     [rbp+57h+var_2C], 3
0x180012241  mov     [rbp+57h+var_38], 1
0x180012248  call    UserHardErrorEx
0x18001224d  jmp     short loc_180012262
0x18001224f  lea     rcx, gcsUserSrv; CriticalSection
0x180012256  call    cs:__imp_RtlLeaveCriticalSection
0x18001225d  nop     dword ptr [rax+rax+00h]
0x180012262  cmp     cs:gpchiList, 0
0x18001226a  jnz     short loc_18001229B
0x18001226c  mov     rcx, cs:g_hDoMessageEvent; Handle
0x180012273  xor     r8d, r8d; Timeout
0x180012276  xor     edx, edx; Alertable
0x180012278  call    cs:__imp_NtWaitForSingleObject
0x18001227f  nop     dword ptr [rax+rax+00h]
0x180012284  mov     rcx, cs:g_hDoMessageEvent; EventHandle
0x18001228b  xor     edx, edx; NumberOfWaitingThreads
0x18001228d  mov     edi, eax
0x18001228f  call    cs:__imp_NtResetEvent
0x180012296  nop     dword ptr [rax+rax+00h]
0x18001229b  cmp     cs:gbExitInProgress, 0
0x1800122a2  jz      loc_180012141
0x1800122a8  mov     rcx, cs:g_hDoMessageEvent; Handle
0x1800122af  call    cs:__imp_NtClose
0x1800122b6  nop     dword ptr [rax+rax+00h]
0x1800122bb  mov     cs:g_hDoMessageEvent, 0
0x1800122c6  mov     ecx, edi; Status
0x1800122c8  call    cs:__imp_RtlExitUserThread
0x1800122cf  nop     dword ptr [rax+rax+00h]
0x1800122d4  int     3; Trap to Debugger
```
