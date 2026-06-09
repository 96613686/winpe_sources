# SmpFinishPFROLogging

- ea: `0x140014100`
- end: `0x140014264`
- name: `SmpFinishPFROLogging`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x140015ae8`

## callees

- `0x14000ad0c`
- `0x14000d4c0`
- `0x14000eaec`
- `0x140014100`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x140014233`
- `ntdll!NtClose` at `0x140014233`
- `ntdll!NtWriteFile` at `0x14001420e`
- `ntdll!NtWriteFile` at `0x14001420e`

## pseudocode

```c
void __fastcall SmpFinishPFROLogging(int a1, char a2)
{
  NTSTATUS v3; // eax
  __int64 v4; // rdx
  ULONG Length; // [rsp+30h] [rbp-D0h]
  int ByteOffset; // [rsp+38h] [rbp-C8h]
  int Key; // [rsp+40h] [rbp-C0h]
  int Hour; // [rsp+48h] [rbp-B8h]
  int Minute; // [rsp+50h] [rbp-B0h]
  int Second; // [rsp+58h] [rbp-A8h]
  int v11; // [rsp+60h] [rbp-A0h]
  size_t pcbRemaining; // [rsp+70h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  _TIME_FIELDS TimeFields; // [rsp+88h] [rbp-78h] BYREF
  wchar_t pszDest[256]; // [rsp+A0h] [rbp-60h] BYREF

  pcbRemaining = 0;
  IoStatusBlock = 0;
  TimeFields = 0;
  if ( SmpLogFileHandle )
  {
    if ( a2 )
    {
      SmpGetTime(&TimeFields);
      v11 = a1;
      Second = TimeFields.Second;
      Minute = TimeFields.Minute;
      Hour = TimeFields.Hour;
      Key = TimeFields.Year;
      ByteOffset = TimeFields.Day;
      Length = TimeFields.Month;
      v3 = RtlStringCbPrintfExW(
             pszDest,
             0x200u,
             0,
             &pcbRemaining,
             0,
             L"%d/%d/%d %d:%d:%d - %d Successful PFRO operations\r\n\r\n",
             Length,
             ByteOffset,
             Key,
             Hour,
             Minute,
             Second,
             v11);
      if ( v3 < 0 )
      {
        v4 = 12280;
LABEL_7:
        SmpLogFailure("SmpFinishPFROLogging", v4, (unsigned int)v3);
        goto LABEL_8;
      }
      v3 = NtWriteFile(SmpLogFileHandle, 0, 0, 0, &IoStatusBlock, pszDest, 512 - pcbRemaining, 0, 0);
      if ( v3 < 0 )
      {
        v4 = 12301;
        goto LABEL_7;
      }
    }
LABEL_8:
    NtClose(SmpLogFileHandle);
    SmpLogFileHandle = 0;
  }
}

```

## disassembly

```asm
0x140014100  mov     [rsp-8+arg_8], rbx
0x140014105  push    rbp
0x140014106  lea     rbp, [rsp-1B0h]
0x14001410e  sub     rsp, 2B0h
0x140014115  mov     rax, cs:__security_cookie
0x14001411c  xor     rax, rsp
0x14001411f  mov     [rbp+1B0h+var_10], rax
0x140014126  cmp     cs:SmpLogFileHandle, 0
0x14001412e  xorps   xmm0, xmm0
0x140014131  xorps   xmm1, xmm1
0x140014134  mov     [rsp+2B0h+pcbRemaining], 0
0x14001413d  movups  xmmword ptr [rsp+2B0h+IoStatusBlock], xmm0
0x140014142  mov     ebx, ecx
0x140014144  movups  xmmword ptr [rbp+1B0h+TimeFields.Year], xmm1
0x140014148  jz      loc_140014244
0x14001414e  test    dl, dl
0x140014150  jz      loc_14001422C
0x140014156  lea     rcx, [rbp+1B0h+TimeFields]; TimeFields
0x14001415a  call    SmpGetTime
0x14001415f  movsx   eax, [rbp+1B0h+TimeFields.Second]
0x140014163  movsx   ecx, [rbp+1B0h+TimeFields.Minute]
0x140014167  movsx   edx, [rbp+1B0h+TimeFields.Hour]
0x14001416b  movsx   r8d, [rbp+1B0h+TimeFields.Year]
0x140014170  movsx   r9d, [rbp+1B0h+TimeFields.Day]
0x140014175  movsx   r10d, [rbp+1B0h+TimeFields.Month]
0x14001417a  mov     [rsp+2B0h+var_250], ebx
0x14001417e  mov     ebx, 200h
0x140014183  mov     [rsp+2B0h+var_258], eax
0x140014187  lea     rax, aDDDDDDDSuccess; "%d/%d/%d %d:%d:%d - %d Successful PFRO "...
0x14001418e  mov     [rsp+2B0h+var_260], ecx
0x140014192  lea     rcx, [rbp+1B0h+pszDest]; pszDest
0x140014196  mov     [rsp+2B0h+var_268], edx
0x14001419a  mov     edx, ebx; cbDest
0x14001419c  mov     dword ptr [rsp+2B0h+Key], r8d
0x1400141a1  xor     r8d, r8d; ppszDestEnd
0x1400141a4  mov     dword ptr [rsp+2B0h+ByteOffset], r9d
0x1400141a9  lea     r9, [rsp+2B0h+pcbRemaining]; pcbRemaining
0x1400141ae  mov     [rsp+2B0h+Length], r10d
0x1400141b3  mov     [rsp+2B0h+pszFormat], rax; pszFormat
0x1400141b8  mov     qword ptr [rsp+2B0h+dwFlags], 0; dwFlags
0x1400141c1  call    RtlStringCbPrintfExW
0x1400141c6  test    eax, eax
0x1400141c8  jns     short loc_1400141D1
0x1400141ca  mov     edx, 2FF8h
0x1400141cf  jmp     short loc_14001421D
0x1400141d1  sub     rbx, [rsp+2B0h+pcbRemaining]
0x1400141d6  lea     rax, [rbp+1B0h+pszDest]
0x1400141da  mov     rcx, cs:SmpLogFileHandle; FileHandle
0x1400141e1  xor     r9d, r9d; ApcContext
0x1400141e4  mov     [rsp+2B0h+Key], 0; Key
0x1400141ed  xor     r8d, r8d; ApcRoutine
0x1400141f0  mov     [rsp+2B0h+ByteOffset], 0; ByteOffset
0x1400141f9  xor     edx, edx; Event
0x1400141fb  mov     [rsp+2B0h+Length], ebx; Length
0x1400141ff  mov     [rsp+2B0h+pszFormat], rax; Buffer
0x140014204  lea     rax, [rsp+2B0h+IoStatusBlock]
0x140014209  mov     qword ptr [rsp+2B0h+dwFlags], rax; IoStatusBlock
0x14001420e  call    cs:__imp_NtWriteFile
0x140014214  test    eax, eax
0x140014216  jns     short loc_14001422C
0x140014218  mov     edx, 300Dh
0x14001421d  mov     r8d, eax
0x140014220  lea     rcx, aSmpfinishpfrol; "SmpFinishPFROLogging"
0x140014227  call    SmpLogFailure
0x14001422c  mov     rcx, cs:SmpLogFileHandle; Handle
0x140014233  call    cs:__imp_NtClose
0x140014239  mov     cs:SmpLogFileHandle, 0
0x140014244  mov     rcx, [rbp+1B0h+var_10]
0x14001424b  xor     rcx, rsp; StackCookie
0x14001424e  call    __security_check_cookie
0x140014253  mov     rbx, [rsp+2B0h+arg_8]
0x14001425b  add     rsp, 2B0h
0x140014262  pop     rbp
0x140014263  retn
```
