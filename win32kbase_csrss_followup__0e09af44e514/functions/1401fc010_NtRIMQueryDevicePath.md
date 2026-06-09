# NtRIMQueryDevicePath

- ea: `0x1401fc010`
- end: `0x1401fc2a3`
- name: `NtRIMQueryDevicePath`
- size: `659`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14000c900`
- `0x14000c940`
- `0x14004a0d0`
- `0x14004d770`
- `0x1401a9f9c`
- `0x1401fc010`
- `0x1402bb164`
- `0x1402bb1a0`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401fc08f`
- `ntoskrnl!ProbeForRead` at `0x1401fc08f`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fc130`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fc130`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401fc23b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401fc23b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fc0ec`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fc0ec`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1401fc1f6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1401fc1f6`
- `ntoskrnl!ExRawInputManagerObjectType` at `0x1401fc21d`
- `WIN32K!W32GetUserSessionState` at `0x1401fc189`
- `WIN32K!W32GetUserSessionState` at `0x1401fc1a3`
- `WIN32K!W32GetUserSessionState` at `0x1401fc249`
- `WIN32K!W32GetUserSessionState` at `0x1401fc189`
- `WIN32K!W32GetUserSessionState` at `0x1401fc1a3`
- `WIN32K!W32GetUserSessionState` at `0x1401fc249`

## pseudocode

```c
__int64 __fastcall NtRIMQueryDevicePath(__int64 a1, __int64 a2)
{
  NTSTATUS v4; // esi
  PWSTR Buffer; // rcx
  __int64 UserSessionState; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 **v9; // r12
  __int64 *i; // r15
  int v11; // eax
  __int64 v12; // rax
  UNICODE_STRING SourceString; // [rsp+48h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-50h] BYREF
  int ULongFromUser; // [rsp+68h] [rbp-40h]
  int v17; // [rsp+6Ch] [rbp-3Ch]
  WCHAR *ULong64FromUser; // [rsp+70h] [rbp-38h]
  void *Handle; // [rsp+C8h] [rbp+20h] BYREF

  v4 = 0;
  Handle = 0;
  DestinationString = 0;
  v17 = 0;
  ULongFromUser = RtlReadULongFromUser(a1);
  ULong64FromUser = (WCHAR *)RtlReadULong64FromUser(a1 + 8);
  *(_DWORD *)&SourceString.Length = ULongFromUser;
  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  SourceString.Buffer = ULong64FromUser;
  ProbeForRead(ULong64FromUser, (unsigned __int16)ULongFromUser + 2LL, 2u);
  if ( (unsigned __int16)ULongFromUser > HIWORD(ULongFromUser)
    || (LOBYTE(SourceString.Length) = ULongFromUser, (ULongFromUser & 1) != 0) )
  {
    if ( (SourceString.Length & 1) != 0 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 5689);
    ExRaiseAccessViolation();
  }
  if ( (unsigned __int16)ULongFromUser >= 6u )
  {
    DestinationString.MaximumLength = ULongFromUser;
    DestinationString.Length = ULongFromUser;
    DestinationString.Buffer = (PWSTR)Win32AllocPoolZInitImpl(0x100u, (unsigned __int16)ULongFromUser, 0x706D7452u);
    if ( DestinationString.Buffer )
      RtlCopyUnicodeString(&DestinationString, &SourceString);
    else
      v4 = -1073741670;
  }
  else
  {
    v4 = -1073741811;
  }
  if ( v4 >= 0 )
  {
    Buffer = DestinationString.Buffer;
    if ( *DestinationString.Buffer == 92 && DestinationString.Buffer[1] == 92 && DestinationString.Buffer[2] == 63 )
      DestinationString.Buffer[1] = 63;
    else
      v4 = -1073741811;
    if ( v4 >= 0 )
    {
      UserSessionState = W32GetUserSessionState(Buffer);
      RIMLockShared(UserSessionState + 48);
      v4 = -1073741275;
      v9 = (__int64 **)(W32GetUserSessionState(v7) + 128);
      for ( i = *v9; i != (__int64 *)v9; i = (__int64 *)*i )
      {
        if ( !*((_BYTE *)i - 5) )
        {
          v11 = *((_DWORD *)i + 54);
          if ( (v11 & 0x200) == 0 && ((v11 & 0x1000) == 0 || (i[29] & 4) == 0) )
          {
            if ( RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)i + 15, 0) )
            {
              v4 = ObOpenObjectByPointer(i - 2, 0, 0, 1u, ExRawInputManagerObjectType, 0, &Handle);
              break;
            }
          }
        }
      }
      v12 = W32GetUserSessionState(v8);
      W32ReleasePushLockShared((struct W32_PUSH_LOCK *)(v12 + 48));
      if ( v4 >= 0 )
        RtlWriteULong64ToUser(a2, Handle);
    }
  }
  if ( DestinationString.Buffer )
    GreDeleteFastMutex(DestinationString.Buffer);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1401fc010  mov     rax, rsp
0x1401fc013  mov     [rax+8], rbx
0x1401fc017  mov     [rax+10h], rdx
0x1401fc01b  push    rsi
0x1401fc01c  push    rdi
0x1401fc01d  push    r12
0x1401fc01f  push    r14
0x1401fc021  push    r15
0x1401fc023  sub     rsp, 80h
0x1401fc02a  mov     rbx, rdx
0x1401fc02d  mov     r15, rcx
0x1401fc030  xor     r14d, r14d
0x1401fc033  mov     esi, r14d
0x1401fc036  mov     [rax+20h], r14
0x1401fc03a  xorps   xmm0, xmm0
0x1401fc03d  movups  xmmword ptr [rax-50h], xmm0
0x1401fc041  movups  xmmword ptr [rax-60h], xmm0
0x1401fc045  xorps   xmm1, xmm1
0x1401fc048  movups  xmmword ptr [rax-40h], xmm1
0x1401fc04c  call    RtlReadULongFromUser
0x1401fc051  mov     edi, eax
0x1401fc053  mov     [rsp+0A8h+var_40], edi
0x1401fc057  lea     rcx, [r15+8]
0x1401fc05b  call    RtlReadULong64FromUser
0x1401fc060  mov     rcx, rax; Address
0x1401fc063  mov     [rsp+0A8h+var_38], rax
0x1401fc068  movzx   edx, di
0x1401fc06b  mov     [rsp+0A8h+SourceString.Length], dx
0x1401fc070  shr     edi, 10h
0x1401fc073  mov     [rsp+0A8h+SourceString.MaximumLength], di
0x1401fc078  mov     eax, [rsp+0A8h+var_3C]
0x1401fc07c  mov     dword ptr [rsp+0A8h+SourceString+4], eax
0x1401fc080  mov     [rsp+0A8h+SourceString.Buffer], rcx
0x1401fc085  lea     edi, [r14+2]
0x1401fc089  add     rdx, rdi; Length
0x1401fc08c  mov     r8d, edi; Alignment
0x1401fc08f  call    cs:__imp_ProbeForRead
0x1401fc096  nop     dword ptr [rax+rax+00h]
0x1401fc09b  movzx   eax, [rsp+0A8h+SourceString.Length]
0x1401fc0a0  cmp     ax, [rsp+0A8h+SourceString.MaximumLength]
0x1401fc0a5  ja      short loc_1401FC105
0x1401fc0a7  mov     byte ptr [rsp+0A8h+SourceString.Length], al
0x1401fc0ab  test    al, 1
0x1401fc0ad  jnz     short loc_1401FC105
0x1401fc0af  cmp     eax, 6
0x1401fc0b2  jnb     short loc_1401FC0BB
0x1401fc0b4  mov     esi, 0C000000Dh
0x1401fc0b9  jmp     short loc_1401FC0FF
0x1401fc0bb  mov     [rsp+0A8h+DestinationString.MaximumLength], ax
0x1401fc0c0  mov     [rsp+0A8h+DestinationString.Length], ax
0x1401fc0c5  mov     rdx, rax; unsigned __int64
0x1401fc0c8  mov     ecx, 100h; unsigned __int64
0x1401fc0cd  mov     r8d, 706D7452h; unsigned int
0x1401fc0d3  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401fc0d8  mov     [rsp+0A8h+DestinationString.Buffer], rax
0x1401fc0dd  test    rax, rax
0x1401fc0e0  jz      short loc_1401FC0FA
0x1401fc0e2  lea     rdx, [rsp+0A8h+SourceString]; SourceString
0x1401fc0e7  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x1401fc0ec  call    cs:__imp_RtlCopyUnicodeString
0x1401fc0f3  nop     dword ptr [rax+rax+00h]
0x1401fc0f8  jmp     short loc_1401FC103
0x1401fc0fa  mov     esi, 0C000009Ah
0x1401fc0ff  mov     [rsp+0A8h+var_68], esi
0x1401fc103  jmp     short loc_1401FC151
0x1401fc105  test    byte ptr [rsp+0A8h+SourceString.Length], 1
0x1401fc10a  jz      short loc_1401FC130
0x1401fc10c  mov     [rsp+0A8h+arg_10], 20000h
0x1401fc117  mov     r8d, 1639h
0x1401fc11d  mov     edx, [rsp+0A8h+arg_10]
0x1401fc124  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401fc12b  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401fc130  call    cs:__imp_ExRaiseAccessViolation
0x1401fc137  nop     dword ptr [rax+rax+00h]
0x1401fc13c  nop
0x1401fc13d  mov     esi, 0C000000Dh
0x1401fc142  mov     [rsp+0A8h+var_68], esi
0x1401fc146  xor     r14d, r14d
0x1401fc149  mov     rbx, [rsp+0A8h+arg_8]
0x1401fc151  test    esi, esi
0x1401fc153  js      loc_1401FC279
0x1401fc159  mov     rcx, [rsp+0A8h+DestinationString.Buffer]
0x1401fc15e  cmp     word ptr [rcx], 5Ch ; '\'
0x1401fc162  jnz     short loc_1401FC17C
0x1401fc164  cmp     word ptr [rcx+2], 5Ch ; '\'
0x1401fc169  jnz     short loc_1401FC17C
0x1401fc16b  mov     eax, 3Fh ; '?'
0x1401fc170  cmp     [rcx+4], ax
0x1401fc174  jnz     short loc_1401FC17C
0x1401fc176  mov     [rcx+2], ax
0x1401fc17a  jmp     short loc_1401FC181
0x1401fc17c  mov     esi, 0C000000Dh
0x1401fc181  test    esi, esi
0x1401fc183  js      loc_1401FC279
0x1401fc189  call    cs:__imp_W32GetUserSessionState
0x1401fc190  nop     dword ptr [rax+rax+00h]
0x1401fc195  lea     rcx, [rax+30h]
0x1401fc199  call    RIMLockShared
0x1401fc19e  mov     esi, 0C0000225h
0x1401fc1a3  call    cs:__imp_W32GetUserSessionState
0x1401fc1aa  nop     dword ptr [rax+rax+00h]
0x1401fc1af  lea     r12, [rax+80h]
0x1401fc1b6  mov     r15, [r12]
0x1401fc1ba  cmp     r15, r12
0x1401fc1bd  jz      loc_1401FC249
0x1401fc1c3  cmp     [r15-5], r14b
0x1401fc1c7  jnz     short loc_1401FC206
0x1401fc1c9  mov     eax, [r15+0D8h]
0x1401fc1d0  bt      eax, 9
0x1401fc1d4  jb      short loc_1401FC206
0x1401fc1d6  bt      eax, 0Ch
0x1401fc1da  jnb     short loc_1401FC1E7
0x1401fc1dc  mov     eax, [r15+0E8h]
0x1401fc1e3  test    al, 4
0x1401fc1e5  jnz     short loc_1401FC206
0x1401fc1e7  lea     rdx, [r15+0F0h]; String2
0x1401fc1ee  xor     r8d, r8d; CaseInSensitive
0x1401fc1f1  lea     rcx, [rsp+0A8h+DestinationString]; String1
0x1401fc1f6  call    cs:__imp_RtlEqualUnicodeString
0x1401fc1fd  nop     dword ptr [rax+rax+00h]
0x1401fc202  test    al, al
0x1401fc204  jnz     short loc_1401FC20B
0x1401fc206  mov     r15, [r15]
0x1401fc209  jmp     short loc_1401FC1BA
0x1401fc20b  lea     rax, [rsp+0A8h+arg_18]
0x1401fc213  mov     [rsp+0A8h+Handle], rax; Handle
0x1401fc218  mov     [rsp+0A8h+AccessMode], r14b; AccessMode
0x1401fc21d  mov     rax, cs:__imp_ExRawInputManagerObjectType
0x1401fc224  mov     rdx, [rax]
0x1401fc227  mov     [rsp+0A8h+ObjectType], rdx; ObjectType
0x1401fc22c  mov     r9d, 1; DesiredAccess
0x1401fc232  xor     r8d, r8d; PassedAccessState
0x1401fc235  xor     edx, edx; HandleAttributes
0x1401fc237  lea     rcx, [r15-10h]; Object
0x1401fc23b  call    cs:__imp_ObOpenObjectByPointer
0x1401fc242  nop     dword ptr [rax+rax+00h]
0x1401fc247  mov     esi, eax
0x1401fc249  call    cs:__imp_W32GetUserSessionState
0x1401fc250  nop     dword ptr [rax+rax+00h]
0x1401fc255  lea     rcx, [rax+30h]; struct W32_PUSH_LOCK *
0x1401fc259  call    ?W32ReleasePushLockShared@@YAXPEAVW32_PUSH_LOCK@@@Z; W32ReleasePushLockShared(W32_PUSH_LOCK *)
0x1401fc25e  test    esi, esi
0x1401fc260  js      short loc_1401FC279
0x1401fc262  mov     rdx, [rsp+0A8h+arg_18]
0x1401fc26a  mov     rcx, rbx
0x1401fc26d  call    RtlWriteULong64ToUser
0x1401fc272  jmp     short loc_1401FC279
0x1401fc274  mov     esi, 0C000000Dh
0x1401fc279  mov     rcx, [rsp+0A8h+DestinationString.Buffer]; Buffer
0x1401fc27e  test    rcx, rcx
0x1401fc281  jz      short loc_1401FC288
0x1401fc283  call    GreDeleteFastMutex
0x1401fc288  mov     eax, esi
0x1401fc28a  mov     rbx, [rsp+0A8h+arg_0]
0x1401fc292  add     rsp, 80h
0x1401fc299  pop     r15
0x1401fc29b  pop     r14
0x1401fc29d  pop     r12
0x1401fc29f  pop     rdi
0x1401fc2a0  pop     rsi
0x1401fc2a1  retn
```
