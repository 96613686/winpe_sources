# WldpSanitizeFileName(ushort const *,ushort const * *,uchar *)

- ea: `0x180017340`
- end: `0x1800174d8`
- name: `?WldpSanitizeFileName@@YAJPEBGPEAPEBGPEAE@Z`
- size: `408`
- prototype: `__int64 __fastcall(PCWSTR SourceString, const unsigned __int16 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800177e4`
- `0x18001cd18`
- `0x18001d9b4`
- `0x18002a0e0`
- `0x18002a318`

## callees

- `0x180017340`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800174cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800174cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001746d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001746d`
- `ntdll!RtlInitUnicodeString` at `0x1800173b6`
- `ntdll!RtlInitUnicodeString` at `0x1800173b6`
- `ntdll!RtlFindUnicodeSubstring` at `0x1800173c7`
- `ntdll!RtlFindUnicodeSubstring` at `0x180017430`
- `ntdll!RtlFindUnicodeSubstring` at `0x1800173c7`
- `ntdll!RtlFindUnicodeSubstring` at `0x180017430`
- `ntdll!RtlCopyUnicodeString` at `0x18001748e`
- `ntdll!RtlCopyUnicodeString` at `0x18001748e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001749c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001749c`

## pseudocode

```c
__int64 __fastcall WldpSanitizeFileName(PCWSTR SourceString, const unsigned __int16 **a2, unsigned __int8 *a3)
{
  NTSTATUS appended; // ebx
  __int64 v7; // r8
  __int64 UnicodeSubstring; // rax
  __int64 v9; // r8
  WCHAR *v11; // rax
  USHORT v12; // bx
  const unsigned __int16 *Buffer; // rcx
  UNICODE_STRING Source; // [rsp+20h] [rbp-39h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-9h] BYREF
  UNICODE_STRING SourceStringa; // [rsp+60h] [rbp+7h] BYREF
  _QWORD v19[8]; // [rsp+70h] [rbp+17h] BYREF

  v17[0] = 1048590;
  v19[0] = 262146;
  v17[1] = L"\\Users\\";
  *(_QWORD *)&SourceStringa.Length = 1835034;
  v19[1] = L"\\";
  SourceStringa.Buffer = L"%USERPROFILE%";
  appended = 0;
  DestinationString = 0;
  Destination = 0;
  Source = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  LOBYTE(v7) = 1;
  UnicodeSubstring = RtlFindUnicodeSubstring(&DestinationString, v17, v7);
  if ( UnicodeSubstring
    && (LOBYTE(v9) = 1,
        Source.Buffer = (PWSTR)(UnicodeSubstring + 2 * ((unsigned __int64)LOWORD(v17[0]) >> 1)),
        Source.Length = DestinationString.Length - 2 * (Source.Buffer - DestinationString.Buffer),
        Source.MaximumLength = Source.Length,
        (v11 = (WCHAR *)RtlFindUnicodeSubstring(&Source, v19, v9)) != 0) )
  {
    Source.Buffer = v11;
    Source.Length = DestinationString.Length - 2 * (v11 - DestinationString.Buffer);
    Source.MaximumLength = Source.Length;
    v12 = SourceStringa.Length + Source.Length + 2;
    Destination.Buffer = (PWSTR)LocalAlloc(0x40u, v12);
    if ( Destination.Buffer )
    {
      Destination.MaximumLength = v12;
      Destination.Length = 0;
      RtlCopyUnicodeString(&Destination, &SourceStringa);
      appended = RtlAppendUnicodeStringToString(&Destination, &Source);
      if ( appended >= 0 )
      {
        Buffer = Destination.Buffer;
        *a3 = 1;
        *a2 = Buffer;
        Destination.Buffer = 0;
      }
    }
    else
    {
      appended = -1073741801;
    }
  }
  else
  {
    *a2 = SourceString;
    *a3 = 0;
  }
  if ( Destination.Buffer )
    LocalFree(Destination.Buffer);
  return appended | 0x10000000u;
}

```

## disassembly

```asm
0x180017340  push    rbp
0x180017342  push    rbx
0x180017343  push    rsi
0x180017344  push    rdi
0x180017345  push    r12
0x180017347  push    r14
0x180017349  lea     rbp, [rsp-2Fh]
0x18001734e  sub     rsp, 88h
0x180017355  xorps   xmm0, xmm0
0x180017358  mov     [rbp+57h+var_60], 10000Eh
0x180017360  lea     rax, aUsers; "\\Users\\"
0x180017367  mov     [rbp+57h+var_40], 40002h
0x18001736f  mov     [rbp+57h+var_58], rax
0x180017373  mov     rsi, rdx
0x180017376  lea     rax, asc_180047B68; "\\"
0x18001737d  mov     qword ptr [rbp+57h+SourceString.Length], 1C001Ah
0x180017385  mov     [rbp+57h+var_38], rax
0x180017389  mov     r14, rcx
0x18001738c  lea     rax, aUserprofile; "%USERPROFILE%"
0x180017393  xorps   xmm1, xmm1
0x180017396  mov     rdx, rcx; SourceString
0x180017399  mov     [rbp+57h+SourceString.Buffer], rax
0x18001739d  xor     ebx, ebx
0x18001739f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800173a3  mov     rdi, r8
0x1800173a6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800173aa  movups  xmmword ptr [rbp+57h+Destination.Length], xmm1
0x1800173ae  lea     r12d, [rbx+2]
0x1800173b2  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x1800173b6  call    cs:__imp_RtlInitUnicodeString
0x1800173bc  mov     r8b, 1
0x1800173bf  lea     rdx, [rbp+57h+var_60]
0x1800173c3  lea     rcx, [rbp+57h+DestinationString]
0x1800173c7  call    cs:__imp_RtlFindUnicodeSubstring
0x1800173cd  mov     rcx, rax
0x1800173d0  test    rax, rax
0x1800173d3  jnz     short loc_1800173FD
0x1800173d5  mov     [rsi], r14
0x1800173d8  mov     [rdi], bl
0x1800173da  mov     rcx, [rbp+57h+Destination.Buffer]; hMem
0x1800173de  test    rcx, rcx
0x1800173e1  jnz     loc_1800174CD
0x1800173e7  bts     ebx, 1Ch
0x1800173eb  mov     eax, ebx
0x1800173ed  add     rsp, 88h
0x1800173f4  pop     r14
0x1800173f6  pop     r12
0x1800173f8  pop     rdi
0x1800173f9  pop     rsi
0x1800173fa  pop     rbx
0x1800173fb  pop     rbp
0x1800173fc  retn
0x1800173fd  movzx   eax, word ptr [rbp+57h+var_60]
0x180017401  lea     rdx, [rbp+57h+var_40]
0x180017405  shr     rax, 1
0x180017408  mov     r8b, 1
0x18001740b  lea     rcx, [rcx+rax*2]
0x18001740f  movzx   eax, [rbp+57h+DestinationString.Length]
0x180017413  mov     [rbp+57h+Source.Buffer], rcx
0x180017417  sub     rcx, [rbp+57h+DestinationString.Buffer]
0x18001741b  sar     rcx, 1
0x18001741e  add     cx, cx
0x180017421  sub     ax, cx
0x180017424  lea     rcx, [rbp+57h+Source]
0x180017428  mov     [rbp+57h+Source.Length], ax
0x18001742c  mov     [rbp+57h+Source.MaximumLength], ax
0x180017430  call    cs:__imp_RtlFindUnicodeSubstring
0x180017436  mov     rcx, rax
0x180017439  test    rax, rax
0x18001743c  jz      short loc_1800173D5
0x18001743e  sub     rcx, [rbp+57h+DestinationString.Buffer]
0x180017442  mov     [rbp+57h+Source.Buffer], rax
0x180017446  movzx   eax, [rbp+57h+DestinationString.Length]
0x18001744a  sar     rcx, 1
0x18001744d  add     cx, cx
0x180017450  sub     ax, cx
0x180017453  mov     ecx, 40h ; '@'; uFlags
0x180017458  mov     [rbp+57h+Source.Length], ax
0x18001745c  mov     [rbp+57h+Source.MaximumLength], ax
0x180017460  add     ax, [rbp+57h+SourceString.Length]
0x180017464  add     ax, r12w
0x180017468  movzx   ebx, ax
0x18001746b  mov     edx, ebx; uBytes
0x18001746d  call    cs:__imp_LocalAlloc
0x180017473  mov     [rbp+57h+Destination.Buffer], rax
0x180017477  test    rax, rax
0x18001747a  jz      short loc_1800174C3
0x18001747c  xor     eax, eax
0x18001747e  mov     [rbp+57h+Destination.MaximumLength], bx
0x180017482  lea     rdx, [rbp+57h+SourceString]; SourceString
0x180017486  mov     [rbp+57h+Destination.Length], ax
0x18001748a  lea     rcx, [rbp+57h+Destination]; DestinationString
0x18001748e  call    cs:__imp_RtlCopyUnicodeString
0x180017494  lea     rdx, [rbp+57h+Source]; Source
0x180017498  lea     rcx, [rbp+57h+Destination]; Destination
0x18001749c  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800174a2  mov     ebx, eax
0x1800174a4  test    eax, eax
0x1800174a6  js      loc_1800173DA
0x1800174ac  mov     rcx, [rbp+57h+Destination.Buffer]
0x1800174b0  mov     byte ptr [rdi], 1
0x1800174b3  mov     [rsi], rcx
0x1800174b6  mov     [rbp+57h+Destination.Buffer], 0
0x1800174be  jmp     loc_1800173DA
0x1800174c3  mov     ebx, 0C0000017h
0x1800174c8  jmp     loc_1800173DA
0x1800174cd  call    cs:__imp_LocalFree
0x1800174d3  jmp     loc_1800173E7
```
