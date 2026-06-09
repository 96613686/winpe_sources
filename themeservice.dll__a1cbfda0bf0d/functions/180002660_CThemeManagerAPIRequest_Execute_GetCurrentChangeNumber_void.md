# CThemeManagerAPIRequest::Execute_GetCurrentChangeNumber(void)

- ea: `0x180002660`
- end: `0x18000292d`
- name: `?Execute_GetCurrentChangeNumber@CThemeManagerAPIRequest@@AEAAJXZ`
- size: `717`
- prototype: `__int64 __fastcall(CThemeManagerAPIRequest *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002270`

## callees

- `0x180002660`
- `0x180002940`
- `0x180002ae0`
- `0x180006a08`
- `0x18000f300`
- `0x18000fa00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000285c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000285c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002834`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000289c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000289c`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000288a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000288a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800027b9`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800027b9`
- `ntdll!NtOpenSection` at `0x18000278a`
- `ntdll!NtOpenSection` at `0x18000278a`
- `ntdll!RtlInitUnicodeString` at `0x18000274a`
- `ntdll!RtlInitUnicodeString` at `0x18000274a`

## pseudocode

```c
__int64 __fastcall CThemeManagerAPIRequest::Execute_GetCurrentChangeNumber(CThemeManagerAPIRequest *this)
{
  int v2; // r14d
  __int64 v3; // rdx
  int v4; // r9d
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  int v6; // r15d
  NTSTATUS v7; // eax
  int v8; // eax
  struct _RTL_CRITICAL_SECTION *v9; // rsi
  int v10; // ebx
  signed int LastError; // eax
  bool v13; // sf
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  void **v16; // [rsp+70h] [rbp-90h]
  WCHAR SourceString[260]; // [rsp+78h] [rbp-88h] BYREF
  void *SectionHandle[2]; // [rsp+280h] [rbp+180h] BYREF
  ACCESS_MASK DesiredAccess; // [rsp+294h] [rbp+194h]
  DWORD dwDesiredAccess; // [rsp+298h] [rbp+198h]

  v2 = CThemeManagerAPIRequest::ImpersonateClientIfRequired(this);
  if ( v2 < 0 )
    goto LABEL_24;
  v3 = *((_QWORD *)this + 19);
  v4 = *(_DWORD *)(v3 + 16);
  v5 = *(struct _RTL_CRITICAL_SECTION **)(v3 + 24);
  v6 = 0;
  *(_OWORD *)SectionHandle = 0;
  DesiredAccess = 4;
  dwDesiredAccess = 4;
  SourceString[0] = 0;
  v16 = &CDataSection::`vftable';
  if ( v4 )
    StringCchPrintfW(SourceString, 0x104u, L"\\Sessions\\%d\\Windows\\ThemeSection");
  else
    StringCchPrintfW(SourceString, 0x104u, L"\\Windows\\ThemeSection");
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( SectionHandle[0]
    || (RtlInitUnicodeString(&DestinationString, SourceString),
        ObjectAttributes.ObjectName = &DestinationString,
        ObjectAttributes.Length = 48,
        ObjectAttributes.RootDirectory = 0,
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
        ObjectAttributes.Attributes = 64,
        v7 = NtOpenSection(SectionHandle, DesiredAccess, &ObjectAttributes),
        v7 >= 0) )
  {
    if ( SectionHandle[1] )
      goto LABEL_33;
    SectionHandle[1] = MapViewOfFile(SectionHandle[0], dwDesiredAccess, 0, 0, 0);
    if ( SectionHandle[1] )
      goto LABEL_33;
    LastError = GetLastError();
    v13 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = LastError < 0;
    }
    if ( !v13 )
    {
LABEL_33:
      if ( SourceString[0] || (v8 = StringCchCopyW(SourceString, 0x104u, SourceString), v8 >= 0) )
      {
        if ( SectionHandle[1] )
          v6 = *((_DWORD *)SectionHandle[1] + 260);
      }
      else
      {
        RecordError(v8, 0x49u);
      }
    }
    else
    {
      RecordError(LastError, 0x41u);
    }
  }
  else
  {
    RecordError(v7 | 0x10000000, 0x35u);
  }
  v9 = v5 + 1;
  if ( v5 != (struct _RTL_CRITICAL_SECTION *)-40LL && v9->DebugInfo )
  {
    EnterCriticalSection(v5 + 1);
    v10 = v6 | (v5->LockCount << 16);
    goto LABEL_17;
  }
  v10 = v6 | (v5->LockCount << 16);
  if ( v9 )
  {
LABEL_17:
    if ( v9->DebugInfo )
      LeaveCriticalSection(v9);
  }
  v16 = &CSection::`vftable';
  if ( SectionHandle[1] )
    UnmapViewOfFile(SectionHandle[1]);
  if ( SectionHandle[0] )
    CloseHandle(SectionHandle[0]);
  *((_DWORD *)this + 18) = v10;
LABEL_24:
  *((_DWORD *)this + 6) = 7340104;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180002660  push    rbp
0x180002662  push    rdi
0x180002663  push    r14
0x180002665  lea     rbp, [rsp-1C0h]
0x18000266d  sub     rsp, 2C0h
0x180002674  mov     rax, cs:__security_cookie
0x18000267b  xor     rax, rsp
0x18000267e  mov     [rbp+1D0h+var_30], rax
0x180002685  mov     rdi, rcx
0x180002688  call    ?ImpersonateClientIfRequired@CThemeManagerAPIRequest@@AEAAJXZ; CThemeManagerAPIRequest::ImpersonateClientIfRequired(void)
0x18000268d  mov     r14d, eax
0x180002690  test    eax, eax
0x180002692  js      loc_1800028AD
0x180002698  mov     rdx, [rdi+98h]
0x18000269f  lea     rax, ??_7CDataSection@@6B@; const CDataSection::`vftable'
0x1800026a6  mov     [rsp+2D0h+arg_8], rbx
0x1800026ae  lea     rcx, [rsp+2D0h+SourceString]; unsigned __int16 *
0x1800026b3  mov     [rsp+2D0h+arg_10], rsi
0x1800026bb  xorps   xmm0, xmm0
0x1800026be  mov     [rsp+2D0h+var_18], r12
0x1800026c6  xor     r12d, r12d
0x1800026c9  mov     r9d, [rdx+10h]
0x1800026cd  mov     rbx, [rdx+18h]
0x1800026d1  mov     edx, 104h; unsigned __int64
0x1800026d6  mov     [rsp+2D0h+var_20], r15
0x1800026de  mov     r15d, r12d
0x1800026e1  movdqa  xmmword ptr [rbp+1D0h+SectionHandle], xmm0
0x1800026e9  mov     [rbp+1D0h+DesiredAccess], 4
0x1800026f3  mov     [rbp+1D0h+dwDesiredAccess], 4
0x1800026fd  mov     [rsp+2D0h+SourceString], r12w
0x180002703  mov     [rsp+2D0h+var_260], rax
0x180002708  test    r9d, r9d
0x18000270b  jz      loc_1800028D2
0x180002711  lea     r8, aSessionsDWindo; "\\Sessions\\%d\\Windows\\ThemeSection"
0x180002718  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000271d  xorps   xmm0, xmm0
0x180002720  mov     esi, r12d
0x180002723  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.Length], xmm0
0x180002728  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.ObjectName], xmm0
0x18000272d  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002732  movups  xmmword ptr [rsp+2D0h+DestinationString.Length], xmm0
0x180002737  cmp     [rbp+1D0h+SectionHandle], rsi
0x18000273e  jnz     short loc_180002798
0x180002740  lea     rdx, [rsp+2D0h+SourceString]; SourceString
0x180002745  lea     rcx, [rsp+2D0h+DestinationString]; DestinationString
0x18000274a  call    cs:__imp_RtlInitUnicodeString
0x180002750  mov     edx, [rbp+1D0h+DesiredAccess]; DesiredAccess
0x180002756  lea     rax, [rsp+2D0h+DestinationString]
0x18000275b  xorps   xmm0, xmm0
0x18000275e  mov     [rsp+2D0h+ObjectAttributes.ObjectName], rax
0x180002763  lea     r8, [rsp+2D0h+ObjectAttributes]; ObjectAttributes
0x180002768  mov     [rsp+2D0h+ObjectAttributes.Length], 30h ; '0'
0x180002770  lea     rcx, [rbp+1D0h+SectionHandle]; SectionHandle
0x180002777  mov     [rsp+2D0h+ObjectAttributes.RootDirectory], r12
0x18000277c  movdqu  xmmword ptr [rsp+2D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002782  mov     [rsp+2D0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000278a  call    cs:__imp_NtOpenSection
0x180002790  test    eax, eax
0x180002792  js      loc_18000290E
0x180002798  cmp     [rbp+1D0h+SectionHandle+8], r12
0x18000279f  jnz     short loc_1800027CF
0x1800027a1  mov     edx, [rbp+1D0h+dwDesiredAccess]; dwDesiredAccess
0x1800027a7  xor     r9d, r9d; dwFileOffsetLow
0x1800027aa  mov     rcx, [rbp+1D0h+SectionHandle]; hFileMappingObject
0x1800027b1  xor     r8d, r8d; dwFileOffsetHigh
0x1800027b4  mov     [rsp+2D0h+dwNumberOfBytesToMap], r12; dwNumberOfBytesToMap
0x1800027b9  call    cs:__imp_MapViewOfFile
0x1800027bf  mov     [rbp+1D0h+SectionHandle+8], rax
0x1800027c6  test    rax, rax
0x1800027c9  jz      loc_1800028E3
0x1800027cf  test    esi, esi
0x1800027d1  js      short loc_18000281A
0x1800027d3  cmp     r12w, [rsp+2D0h+SourceString]
0x1800027d9  jnz     short loc_180002807
0x1800027db  lea     r8, [rsp+2D0h+SourceString]; unsigned __int16 *
0x1800027e0  mov     edx, 104h; unsigned __int64
0x1800027e5  lea     rcx, [rsp+2D0h+SourceString]; unsigned __int16 *
0x1800027ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800027ef  mov     esi, eax
0x1800027f1  test    eax, eax
0x1800027f3  jns     short loc_180002803
0x1800027f5  mov     edx, 49h ; 'I'; unsigned int
0x1800027fa  mov     ecx, eax; int
0x1800027fc  call    ?RecordError@@YAXJI@Z; RecordError(long,uint)
0x180002801  jmp     short loc_18000281A
0x180002803  test    esi, esi
0x180002805  js      short loc_18000281A
0x180002807  mov     rax, [rbp+1D0h+SectionHandle+8]
0x18000280e  test    rax, rax
0x180002811  jz      short loc_18000281A
0x180002813  mov     r15d, [rax+410h]
0x18000281a  mov     r12, [rsp+2D0h+var_18]
0x180002822  lea     rsi, [rbx+28h]
0x180002826  test    rsi, rsi
0x180002829  jz      short loc_180002845
0x18000282b  cmp     qword ptr [rsi], 0
0x18000282f  jz      short loc_180002845
0x180002831  mov     rcx, rsi; lpCriticalSection
0x180002834  call    cs:__imp_EnterCriticalSection
0x18000283a  mov     ebx, [rbx+8]
0x18000283d  shl     ebx, 10h
0x180002840  or      ebx, r15d
0x180002843  jmp     short loc_180002853
0x180002845  mov     ebx, [rbx+8]
0x180002848  shl     ebx, 10h
0x18000284b  or      ebx, r15d
0x18000284e  test    rsi, rsi
0x180002851  jz      short loc_180002862
0x180002853  cmp     qword ptr [rsi], 0
0x180002857  jz      short loc_180002862
0x180002859  mov     rcx, rsi; lpCriticalSection
0x18000285c  call    cs:__imp_LeaveCriticalSection
0x180002862  mov     rcx, [rbp+1D0h+SectionHandle+8]; lpBaseAddress
0x180002869  lea     rax, ??_7CSection@@6B@; const CSection::`vftable'
0x180002870  mov     r15, [rsp+2D0h+var_20]
0x180002878  mov     rsi, [rsp+2D0h+arg_10]
0x180002880  mov     [rsp+2D0h+var_260], rax
0x180002885  test    rcx, rcx
0x180002888  jz      short loc_180002890
0x18000288a  call    cs:__imp_UnmapViewOfFile
0x180002890  mov     rcx, [rbp+1D0h+SectionHandle]; hObject
0x180002897  test    rcx, rcx
0x18000289a  jz      short loc_1800028A2
0x18000289c  call    cs:__imp_CloseHandle
0x1800028a2  mov     [rdi+48h], ebx
0x1800028a5  mov     rbx, [rsp+2D0h+arg_8]
0x1800028ad  mov     dword ptr [rdi+18h], 700048h
0x1800028b4  mov     eax, r14d
0x1800028b7  mov     rcx, [rbp+1D0h+var_30]
0x1800028be  xor     rcx, rsp; StackCookie
0x1800028c1  call    __security_check_cookie
0x1800028c6  add     rsp, 2C0h
0x1800028cd  pop     r14
0x1800028cf  pop     rdi
0x1800028d0  pop     rbp
0x1800028d1  retn
0x1800028d2  lea     r8, aWindowsThemese; "\\Windows\\ThemeSection"
0x1800028d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800028de  jmp     loc_18000271D
0x1800028e3  call    cs:__imp_GetLastError
0x1800028e9  test    eax, eax
0x1800028eb  jle     short loc_1800028F7
0x1800028ed  movzx   eax, ax
0x1800028f0  or      eax, 80070000h
0x1800028f5  test    eax, eax
0x1800028f7  jns     loc_1800027D3
0x1800028fd  mov     edx, 41h ; 'A'; unsigned int
0x180002902  mov     ecx, eax; int
0x180002904  call    ?RecordError@@YAXJI@Z; RecordError(long,uint)
0x180002909  jmp     loc_18000281A
0x18000290e  mov     esi, eax
0x180002910  or      esi, 10000000h
0x180002916  jge     loc_180002798
0x18000291c  mov     edx, 35h ; '5'; unsigned int
0x180002921  mov     ecx, esi; int
0x180002923  call    ?RecordError@@YAXJI@Z; RecordError(long,uint)
0x180002928  jmp     loc_18000281A
```
