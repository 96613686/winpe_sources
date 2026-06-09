# NtRIMQueryDevicePath

- ea: `0x1401fc830`
- end: `0x1401fcac3`
- name: `NtRIMQueryDevicePath`
- size: `659`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x140090d20`
- `0x140090d60`
- `0x1401aa4fc`
- `0x1401fc830`
- `0x1402bd208`
- `0x1402bd244`
- `0x1402bd3b4`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401fc8af`
- `ntoskrnl!ProbeForRead` at `0x1401fc8af`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fc950`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fc950`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401fca5b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401fca5b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fc90c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fc90c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1401fca16`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1401fca16`
- `ntoskrnl!ExRawInputManagerObjectType` at `0x1401fca3d`
- `WIN32K!W32GetUserSessionState` at `0x1401fc9a9`
- `WIN32K!W32GetUserSessionState` at `0x1401fc9c3`
- `WIN32K!W32GetUserSessionState` at `0x1401fca69`
- `WIN32K!W32GetUserSessionState` at `0x1401fc9a9`
- `WIN32K!W32GetUserSessionState` at `0x1401fc9c3`
- `WIN32K!W32GetUserSessionState` at `0x1401fca69`

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
0x1401fc830  mov     rax, rsp
0x1401fc833  mov     [rax+8], rbx
0x1401fc837  mov     [rax+10h], rdx
0x1401fc83b  push    rsi
0x1401fc83c  push    rdi
0x1401fc83d  push    r12
0x1401fc83f  push    r14
0x1401fc841  push    r15
0x1401fc843  sub     rsp, 80h
0x1401fc84a  mov     rbx, rdx
0x1401fc84d  mov     r15, rcx
0x1401fc850  xor     r14d, r14d
0x1401fc853  mov     esi, r14d
0x1401fc856  mov     [rax+20h], r14
0x1401fc85a  xorps   xmm0, xmm0
0x1401fc85d  movups  xmmword ptr [rax-50h], xmm0
0x1401fc861  movups  xmmword ptr [rax-60h], xmm0
0x1401fc865  xorps   xmm1, xmm1
0x1401fc868  movups  xmmword ptr [rax-40h], xmm1
0x1401fc86c  call    RtlReadULongFromUser
0x1401fc871  mov     edi, eax
0x1401fc873  mov     [rsp+0A8h+var_40], edi
0x1401fc877  lea     rcx, [r15+8]
0x1401fc87b  call    RtlReadULong64FromUser
0x1401fc880  mov     rcx, rax; Address
0x1401fc883  mov     [rsp+0A8h+var_38], rax
0x1401fc888  movzx   edx, di
0x1401fc88b  mov     [rsp+0A8h+SourceString.Length], dx
0x1401fc890  shr     edi, 10h
0x1401fc893  mov     [rsp+0A8h+SourceString.MaximumLength], di
0x1401fc898  mov     eax, [rsp+0A8h+var_3C]
0x1401fc89c  mov     dword ptr [rsp+0A8h+SourceString+4], eax
0x1401fc8a0  mov     [rsp+0A8h+SourceString.Buffer], rcx
0x1401fc8a5  lea     edi, [r14+2]
0x1401fc8a9  add     rdx, rdi; Length
0x1401fc8ac  mov     r8d, edi; Alignment
0x1401fc8af  call    cs:__imp_ProbeForRead
0x1401fc8b6  nop     dword ptr [rax+rax+00h]
0x1401fc8bb  movzx   eax, [rsp+0A8h+SourceString.Length]
0x1401fc8c0  cmp     ax, [rsp+0A8h+SourceString.MaximumLength]
0x1401fc8c5  ja      short loc_1401FC925
0x1401fc8c7  mov     byte ptr [rsp+0A8h+SourceString.Length], al
0x1401fc8cb  test    al, 1
0x1401fc8cd  jnz     short loc_1401FC925
0x1401fc8cf  cmp     eax, 6
0x1401fc8d2  jnb     short loc_1401FC8DB
0x1401fc8d4  mov     esi, 0C000000Dh
0x1401fc8d9  jmp     short loc_1401FC91F
0x1401fc8db  mov     [rsp+0A8h+DestinationString.MaximumLength], ax
0x1401fc8e0  mov     [rsp+0A8h+DestinationString.Length], ax
0x1401fc8e5  mov     rdx, rax; unsigned __int64
0x1401fc8e8  mov     ecx, 100h; unsigned __int64
0x1401fc8ed  mov     r8d, 706D7452h; unsigned int
0x1401fc8f3  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401fc8f8  mov     [rsp+0A8h+DestinationString.Buffer], rax
0x1401fc8fd  test    rax, rax
0x1401fc900  jz      short loc_1401FC91A
0x1401fc902  lea     rdx, [rsp+0A8h+SourceString]; SourceString
0x1401fc907  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x1401fc90c  call    cs:__imp_RtlCopyUnicodeString
0x1401fc913  nop     dword ptr [rax+rax+00h]
0x1401fc918  jmp     short loc_1401FC923
0x1401fc91a  mov     esi, 0C000009Ah
0x1401fc91f  mov     [rsp+0A8h+var_68], esi
0x1401fc923  jmp     short loc_1401FC971
0x1401fc925  test    byte ptr [rsp+0A8h+SourceString.Length], 1
0x1401fc92a  jz      short loc_1401FC950
0x1401fc92c  mov     [rsp+0A8h+arg_10], 20000h
0x1401fc937  mov     r8d, 1639h
0x1401fc93d  mov     edx, [rsp+0A8h+arg_10]
0x1401fc944  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401fc94b  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401fc950  call    cs:__imp_ExRaiseAccessViolation
0x1401fc957  nop     dword ptr [rax+rax+00h]
0x1401fc95c  nop
0x1401fc95d  mov     esi, 0C000000Dh
0x1401fc962  mov     [rsp+0A8h+var_68], esi
0x1401fc966  xor     r14d, r14d
0x1401fc969  mov     rbx, [rsp+0A8h+arg_8]
0x1401fc971  test    esi, esi
0x1401fc973  js      loc_1401FCA99
0x1401fc979  mov     rcx, [rsp+0A8h+DestinationString.Buffer]
0x1401fc97e  cmp     word ptr [rcx], 5Ch ; '\'
0x1401fc982  jnz     short loc_1401FC99C
0x1401fc984  cmp     word ptr [rcx+2], 5Ch ; '\'
0x1401fc989  jnz     short loc_1401FC99C
0x1401fc98b  mov     eax, 3Fh ; '?'
0x1401fc990  cmp     [rcx+4], ax
0x1401fc994  jnz     short loc_1401FC99C
0x1401fc996  mov     [rcx+2], ax
0x1401fc99a  jmp     short loc_1401FC9A1
0x1401fc99c  mov     esi, 0C000000Dh
0x1401fc9a1  test    esi, esi
0x1401fc9a3  js      loc_1401FCA99
0x1401fc9a9  call    cs:__imp_W32GetUserSessionState
0x1401fc9b0  nop     dword ptr [rax+rax+00h]
0x1401fc9b5  lea     rcx, [rax+30h]
0x1401fc9b9  call    RIMLockShared
0x1401fc9be  mov     esi, 0C0000225h
0x1401fc9c3  call    cs:__imp_W32GetUserSessionState
0x1401fc9ca  nop     dword ptr [rax+rax+00h]
0x1401fc9cf  lea     r12, [rax+80h]
0x1401fc9d6  mov     r15, [r12]
0x1401fc9da  cmp     r15, r12
0x1401fc9dd  jz      loc_1401FCA69
0x1401fc9e3  cmp     [r15-5], r14b
0x1401fc9e7  jnz     short loc_1401FCA26
0x1401fc9e9  mov     eax, [r15+0D8h]
0x1401fc9f0  bt      eax, 9
0x1401fc9f4  jb      short loc_1401FCA26
0x1401fc9f6  bt      eax, 0Ch
0x1401fc9fa  jnb     short loc_1401FCA07
0x1401fc9fc  mov     eax, [r15+0E8h]
0x1401fca03  test    al, 4
0x1401fca05  jnz     short loc_1401FCA26
0x1401fca07  lea     rdx, [r15+0F0h]; String2
0x1401fca0e  xor     r8d, r8d; CaseInSensitive
0x1401fca11  lea     rcx, [rsp+0A8h+DestinationString]; String1
0x1401fca16  call    cs:__imp_RtlEqualUnicodeString
0x1401fca1d  nop     dword ptr [rax+rax+00h]
0x1401fca22  test    al, al
0x1401fca24  jnz     short loc_1401FCA2B
0x1401fca26  mov     r15, [r15]
0x1401fca29  jmp     short loc_1401FC9DA
0x1401fca2b  lea     rax, [rsp+0A8h+arg_18]
0x1401fca33  mov     [rsp+0A8h+Handle], rax; Handle
0x1401fca38  mov     [rsp+0A8h+AccessMode], r14b; AccessMode
0x1401fca3d  mov     rax, cs:__imp_ExRawInputManagerObjectType
0x1401fca44  mov     rdx, [rax]
0x1401fca47  mov     [rsp+0A8h+ObjectType], rdx; ObjectType
0x1401fca4c  mov     r9d, 1; DesiredAccess
0x1401fca52  xor     r8d, r8d; PassedAccessState
0x1401fca55  xor     edx, edx; HandleAttributes
0x1401fca57  lea     rcx, [r15-10h]; Object
0x1401fca5b  call    cs:__imp_ObOpenObjectByPointer
0x1401fca62  nop     dword ptr [rax+rax+00h]
0x1401fca67  mov     esi, eax
0x1401fca69  call    cs:__imp_W32GetUserSessionState
0x1401fca70  nop     dword ptr [rax+rax+00h]
0x1401fca75  lea     rcx, [rax+30h]; struct W32_PUSH_LOCK *
0x1401fca79  call    ?W32ReleasePushLockShared@@YAXPEAVW32_PUSH_LOCK@@@Z; W32ReleasePushLockShared(W32_PUSH_LOCK *)
0x1401fca7e  test    esi, esi
0x1401fca80  js      short loc_1401FCA99
0x1401fca82  mov     rdx, [rsp+0A8h+arg_18]
0x1401fca8a  mov     rcx, rbx
0x1401fca8d  call    RtlWriteULong64ToUser
0x1401fca92  jmp     short loc_1401FCA99
0x1401fca94  mov     esi, 0C000000Dh
0x1401fca99  mov     rcx, [rsp+0A8h+DestinationString.Buffer]; Buffer
0x1401fca9e  test    rcx, rcx
0x1401fcaa1  jz      short loc_1401FCAA8
0x1401fcaa3  call    GreDeleteFastMutex
0x1401fcaa8  mov     eax, esi
0x1401fcaaa  mov     rbx, [rsp+0A8h+arg_0]
0x1401fcab2  add     rsp, 80h
0x1401fcab9  pop     r15
0x1401fcabb  pop     r14
0x1401fcabd  pop     r12
0x1401fcabf  pop     rdi
0x1401fcac0  pop     rsi
0x1401fcac1  retn
```
