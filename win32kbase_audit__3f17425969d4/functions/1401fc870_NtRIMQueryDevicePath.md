# NtRIMQueryDevicePath

- ea: `0x1401fc870`
- end: `0x1401fcb03`
- name: `NtRIMQueryDevicePath`
- size: `659`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14000c420`
- `0x14000c460`
- `0x14007b930`
- `0x14007efd0`
- `0x1401aab9c`
- `0x1401fc870`
- `0x1402bb164`
- `0x1402bb1a0`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401fc8ef`
- `ntoskrnl!ProbeForRead` at `0x1401fc8ef`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fc990`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fc990`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401fca9b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401fca9b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fc94c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fc94c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1401fca56`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1401fca56`
- `ntoskrnl!ExRawInputManagerObjectType` at `0x1401fca7d`
- `WIN32K!W32GetUserSessionState` at `0x1401fc9e9`
- `WIN32K!W32GetUserSessionState` at `0x1401fca03`
- `WIN32K!W32GetUserSessionState` at `0x1401fcaa9`
- `WIN32K!W32GetUserSessionState` at `0x1401fc9e9`
- `WIN32K!W32GetUserSessionState` at `0x1401fca03`
- `WIN32K!W32GetUserSessionState` at `0x1401fcaa9`

## pseudocode

```c
__int64 __fastcall NtRIMQueryDevicePath(__int64 a1, __int64 a2)
{
  NTSTATUS v4; // esi
  __int64 v5; // rdx
  PWSTR Buffer; // rcx
  __int64 UserSessionState; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 **v12; // r12
  __int64 *i; // r15
  int v14; // eax
  __int64 v15; // rax
  UNICODE_STRING SourceString; // [rsp+48h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-50h] BYREF
  int ULongFromUser; // [rsp+68h] [rbp-40h]
  int v20; // [rsp+6Ch] [rbp-3Ch]
  WCHAR *ULong64FromUser; // [rsp+70h] [rbp-38h]
  void *Handle; // [rsp+C8h] [rbp+20h] BYREF

  v4 = 0;
  Handle = 0;
  DestinationString = 0;
  v20 = 0;
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
      UserSessionState = W32GetUserSessionState(Buffer, v5);
      RIMLockShared(UserSessionState + 48);
      v4 = -1073741275;
      v12 = (__int64 **)(W32GetUserSessionState(v9, v8) + 128);
      for ( i = *v12; i != (__int64 *)v12; i = (__int64 *)*i )
      {
        if ( !*((_BYTE *)i - 5) )
        {
          v14 = *((_DWORD *)i + 54);
          if ( (v14 & 0x200) == 0 && ((v14 & 0x1000) == 0 || (i[29] & 4) == 0) )
          {
            if ( RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)i + 15, 0) )
            {
              v4 = ObOpenObjectByPointer(i - 2, 0, 0, 1u, ExRawInputManagerObjectType, 0, &Handle);
              break;
            }
          }
        }
      }
      v15 = W32GetUserSessionState(v11, v10);
      W32ReleasePushLockShared((struct W32_PUSH_LOCK *)(v15 + 48));
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
0x1401fc870  mov     rax, rsp
0x1401fc873  mov     [rax+8], rbx
0x1401fc877  mov     [rax+10h], rdx
0x1401fc87b  push    rsi
0x1401fc87c  push    rdi
0x1401fc87d  push    r12
0x1401fc87f  push    r14
0x1401fc881  push    r15
0x1401fc883  sub     rsp, 80h
0x1401fc88a  mov     rbx, rdx
0x1401fc88d  mov     r15, rcx
0x1401fc890  xor     r14d, r14d
0x1401fc893  mov     esi, r14d
0x1401fc896  mov     [rax+20h], r14
0x1401fc89a  xorps   xmm0, xmm0
0x1401fc89d  movups  xmmword ptr [rax-50h], xmm0
0x1401fc8a1  movups  xmmword ptr [rax-60h], xmm0
0x1401fc8a5  xorps   xmm1, xmm1
0x1401fc8a8  movups  xmmword ptr [rax-40h], xmm1
0x1401fc8ac  call    RtlReadULongFromUser
0x1401fc8b1  mov     edi, eax
0x1401fc8b3  mov     [rsp+0A8h+var_40], edi
0x1401fc8b7  lea     rcx, [r15+8]
0x1401fc8bb  call    RtlReadULong64FromUser
0x1401fc8c0  mov     rcx, rax; Address
0x1401fc8c3  mov     [rsp+0A8h+var_38], rax
0x1401fc8c8  movzx   edx, di
0x1401fc8cb  mov     [rsp+0A8h+SourceString.Length], dx
0x1401fc8d0  shr     edi, 10h
0x1401fc8d3  mov     [rsp+0A8h+SourceString.MaximumLength], di
0x1401fc8d8  mov     eax, [rsp+0A8h+var_3C]
0x1401fc8dc  mov     dword ptr [rsp+0A8h+SourceString+4], eax
0x1401fc8e0  mov     [rsp+0A8h+SourceString.Buffer], rcx
0x1401fc8e5  lea     edi, [r14+2]
0x1401fc8e9  add     rdx, rdi; Length
0x1401fc8ec  mov     r8d, edi; Alignment
0x1401fc8ef  call    cs:__imp_ProbeForRead
0x1401fc8f6  nop     dword ptr [rax+rax+00h]
0x1401fc8fb  movzx   eax, [rsp+0A8h+SourceString.Length]
0x1401fc900  cmp     ax, [rsp+0A8h+SourceString.MaximumLength]
0x1401fc905  ja      short loc_1401FC965
0x1401fc907  mov     byte ptr [rsp+0A8h+SourceString.Length], al
0x1401fc90b  test    al, 1
0x1401fc90d  jnz     short loc_1401FC965
0x1401fc90f  cmp     eax, 6
0x1401fc912  jnb     short loc_1401FC91B
0x1401fc914  mov     esi, 0C000000Dh
0x1401fc919  jmp     short loc_1401FC95F
0x1401fc91b  mov     [rsp+0A8h+DestinationString.MaximumLength], ax
0x1401fc920  mov     [rsp+0A8h+DestinationString.Length], ax
0x1401fc925  mov     rdx, rax; unsigned __int64
0x1401fc928  mov     ecx, 100h; unsigned __int64
0x1401fc92d  mov     r8d, 706D7452h; unsigned int
0x1401fc933  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401fc938  mov     [rsp+0A8h+DestinationString.Buffer], rax
0x1401fc93d  test    rax, rax
0x1401fc940  jz      short loc_1401FC95A
0x1401fc942  lea     rdx, [rsp+0A8h+SourceString]; SourceString
0x1401fc947  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x1401fc94c  call    cs:__imp_RtlCopyUnicodeString
0x1401fc953  nop     dword ptr [rax+rax+00h]
0x1401fc958  jmp     short loc_1401FC963
0x1401fc95a  mov     esi, 0C000009Ah
0x1401fc95f  mov     [rsp+0A8h+var_68], esi
0x1401fc963  jmp     short loc_1401FC9B1
0x1401fc965  test    byte ptr [rsp+0A8h+SourceString.Length], 1
0x1401fc96a  jz      short loc_1401FC990
0x1401fc96c  mov     [rsp+0A8h+arg_10], 20000h
0x1401fc977  mov     r8d, 1639h
0x1401fc97d  mov     edx, [rsp+0A8h+arg_10]
0x1401fc984  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401fc98b  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401fc990  call    cs:__imp_ExRaiseAccessViolation
0x1401fc997  nop     dword ptr [rax+rax+00h]
0x1401fc99c  nop
0x1401fc99d  mov     esi, 0C000000Dh
0x1401fc9a2  mov     [rsp+0A8h+var_68], esi
0x1401fc9a6  xor     r14d, r14d
0x1401fc9a9  mov     rbx, [rsp+0A8h+arg_8]
0x1401fc9b1  test    esi, esi
0x1401fc9b3  js      loc_1401FCAD9
0x1401fc9b9  mov     rcx, [rsp+0A8h+DestinationString.Buffer]
0x1401fc9be  cmp     word ptr [rcx], 5Ch ; '\'
0x1401fc9c2  jnz     short loc_1401FC9DC
0x1401fc9c4  cmp     word ptr [rcx+2], 5Ch ; '\'
0x1401fc9c9  jnz     short loc_1401FC9DC
0x1401fc9cb  mov     eax, 3Fh ; '?'
0x1401fc9d0  cmp     [rcx+4], ax
0x1401fc9d4  jnz     short loc_1401FC9DC
0x1401fc9d6  mov     [rcx+2], ax
0x1401fc9da  jmp     short loc_1401FC9E1
0x1401fc9dc  mov     esi, 0C000000Dh
0x1401fc9e1  test    esi, esi
0x1401fc9e3  js      loc_1401FCAD9
0x1401fc9e9  call    cs:__imp_W32GetUserSessionState
0x1401fc9f0  nop     dword ptr [rax+rax+00h]
0x1401fc9f5  lea     rcx, [rax+30h]
0x1401fc9f9  call    RIMLockShared
0x1401fc9fe  mov     esi, 0C0000225h
0x1401fca03  call    cs:__imp_W32GetUserSessionState
0x1401fca0a  nop     dword ptr [rax+rax+00h]
0x1401fca0f  lea     r12, [rax+80h]
0x1401fca16  mov     r15, [r12]
0x1401fca1a  cmp     r15, r12
0x1401fca1d  jz      loc_1401FCAA9
0x1401fca23  cmp     [r15-5], r14b
0x1401fca27  jnz     short loc_1401FCA66
0x1401fca29  mov     eax, [r15+0D8h]
0x1401fca30  bt      eax, 9
0x1401fca34  jb      short loc_1401FCA66
0x1401fca36  bt      eax, 0Ch
0x1401fca3a  jnb     short loc_1401FCA47
0x1401fca3c  mov     eax, [r15+0E8h]
0x1401fca43  test    al, 4
0x1401fca45  jnz     short loc_1401FCA66
0x1401fca47  lea     rdx, [r15+0F0h]; String2
0x1401fca4e  xor     r8d, r8d; CaseInSensitive
0x1401fca51  lea     rcx, [rsp+0A8h+DestinationString]; String1
0x1401fca56  call    cs:__imp_RtlEqualUnicodeString
0x1401fca5d  nop     dword ptr [rax+rax+00h]
0x1401fca62  test    al, al
0x1401fca64  jnz     short loc_1401FCA6B
0x1401fca66  mov     r15, [r15]
0x1401fca69  jmp     short loc_1401FCA1A
0x1401fca6b  lea     rax, [rsp+0A8h+arg_18]
0x1401fca73  mov     [rsp+0A8h+Handle], rax; Handle
0x1401fca78  mov     [rsp+0A8h+AccessMode], r14b; AccessMode
0x1401fca7d  mov     rax, cs:__imp_ExRawInputManagerObjectType
0x1401fca84  mov     rdx, [rax]
0x1401fca87  mov     [rsp+0A8h+ObjectType], rdx; ObjectType
0x1401fca8c  mov     r9d, 1; DesiredAccess
0x1401fca92  xor     r8d, r8d; PassedAccessState
0x1401fca95  xor     edx, edx; HandleAttributes
0x1401fca97  lea     rcx, [r15-10h]; Object
0x1401fca9b  call    cs:__imp_ObOpenObjectByPointer
0x1401fcaa2  nop     dword ptr [rax+rax+00h]
0x1401fcaa7  mov     esi, eax
0x1401fcaa9  call    cs:__imp_W32GetUserSessionState
0x1401fcab0  nop     dword ptr [rax+rax+00h]
0x1401fcab5  lea     rcx, [rax+30h]; struct W32_PUSH_LOCK *
0x1401fcab9  call    ?W32ReleasePushLockShared@@YAXPEAVW32_PUSH_LOCK@@@Z; W32ReleasePushLockShared(W32_PUSH_LOCK *)
0x1401fcabe  test    esi, esi
0x1401fcac0  js      short loc_1401FCAD9
0x1401fcac2  mov     rdx, [rsp+0A8h+arg_18]
0x1401fcaca  mov     rcx, rbx
0x1401fcacd  call    RtlWriteULong64ToUser
0x1401fcad2  jmp     short loc_1401FCAD9
0x1401fcad4  mov     esi, 0C000000Dh
0x1401fcad9  mov     rcx, [rsp+0A8h+DestinationString.Buffer]; Buffer
0x1401fcade  test    rcx, rcx
0x1401fcae1  jz      short loc_1401FCAE8
0x1401fcae3  call    GreDeleteFastMutex
0x1401fcae8  mov     eax, esi
0x1401fcaea  mov     rbx, [rsp+0A8h+arg_0]
0x1401fcaf2  add     rsp, 80h
0x1401fcaf9  pop     r15
0x1401fcafb  pop     r14
0x1401fcafd  pop     r12
0x1401fcaff  pop     rdi
0x1401fcb00  pop     rsi
0x1401fcb01  retn
```
