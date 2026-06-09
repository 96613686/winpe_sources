# ldevLoadImageInternal(ushort const *,int,int *,int,int)

- ea: `0x14016be3c`
- end: `0x14016c36c`
- name: `?ldevLoadImageInternal@@YAPEAU_LDEV@@PEBGHPEAHHH@Z`
- size: `1328`
- prototype: `struct _LDEV *__usercall@<rax>(PCWSTR Source@<rcx>, int@<edx>, int *@<r8>, int@<r9d>, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x14019b800`

## callees

- `0x14000dc4c`
- `0x1400492a4`
- `0x14004a0d0`
- `0x14016be3c`
- `0x14016c380`
- `0x140178bdc`
- `0x140193b40`
- `0x1401b20c4`
- `0x1401b64b4`
- `0x1401c42f8`
- `0x1401c4418`
- `0x140238160`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!ZwSetSystemInformation` at `0x14016bff1`
- `ntoskrnl!ZwSetSystemInformation` at `0x14016bff1`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14016c101`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14016c156`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14016c101`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14016c156`
- `ntoskrnl!RtlImageNtHeader` at `0x14016c220`
- `ntoskrnl!RtlImageNtHeader` at `0x14016c220`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14016c0d3`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14016c0d3`
- `ntoskrnl!RtlFreeAnsiString` at `0x14016c254`
- `ntoskrnl!RtlFreeAnsiString` at `0x14016c254`
- `ntoskrnl!RtlImageDirectoryEntryToData` at `0x14016c1c5`
- `ntoskrnl!RtlImageDirectoryEntryToData` at `0x14016c1c5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14016c0ba`
- `ntoskrnl!RtlInitUnicodeString` at `0x14016c0ba`
- `watchdog!WdLogSingleEntry3` at `0x14016be9a`
- `watchdog!WdLogSingleEntry3` at `0x14016be9a`
- `watchdog!WdLogSingleEntry1` at `0x14016c2d0`
- `watchdog!WdLogSingleEntry1` at `0x14016c32f`
- `watchdog!WdLogSingleEntry1` at `0x14016c2d0`
- `watchdog!WdLogSingleEntry1` at `0x14016c32f`
- `WIN32K!W32GetSessionState` at `0x14016bedc`
- `WIN32K!W32GetSessionState` at `0x14016bedc`

## pseudocode

```c
struct _LDEV *__fastcall ldevLoadImageInternal(PCWSTR Source, int a2, int *a3, signed int a4, int a5)
{
  struct _LDEV *v9; // rbx
  __int64 v10; // rcx
  int v11; // edi
  int i; // esi
  UNICODE_STRING *v13; // r13
  __int64 v14; // rax
  __int64 v15; // rdi
  ULONG v16; // r15d
  int v17; // ebx
  __int64 v18; // rax
  SYSTEM_INFORMATION_CLASS v19; // ecx
  NTSTATUS v20; // eax
  NTSTATUS v21; // esi
  wchar_t *v22; // rax
  const WCHAR *v23; // rax
  int v24; // r12d
  int v25; // ebx
  unsigned int *v26; // rax
  unsigned int *v27; // r14
  unsigned int j; // r15d
  _DWORD *k; // rbx
  unsigned int v30; // eax
  char *v31; // rbx
  __int64 AddressOfEntryPoint; // rax
  int v33; // eax
  int v34; // ecx
  unsigned int v35; // ecx
  __int64 v36; // rcx
  __int64 v37; // rax
  struct _LDEV *result; // rax
  ULONG ReturnLength; // [rsp+20h] [rbp-E0h] BYREF
  ULONG Size; // [rsp+24h] [rbp-DCh] BYREF
  int v41; // [rsp+28h] [rbp-D8h]
  UNICODE_STRING String2; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v43; // [rsp+40h] [rbp-C0h]
  struct _STRING AnsiString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD SystemInformation[76]; // [rsp+70h] [rbp-90h] BYREF

  Size = a4;
  String2 = 0;
  v9 = 0;
  v41 = a5;
  WdLogSingleEntry3(4, Source, a2, a4);
  WdLogGlobalForLineNumber = 999;
  *a3 = 0;
  ReturnLength = a2 == 0;
  if ( !(unsigned int)MakeSystemRelativePath(Source, &String2) )
    goto LABEL_58;
  v11 = 0;
  for ( i = 1; ; i = 0 )
  {
    v43 = *(_QWORD *)(W32GetSessionState(v10) + 88);
    v9 = (struct _LDEV *)ldevTryReferenceLoadedDisplayDriver(&String2);
    if ( v9 )
    {
      *a3 = 1;
      goto LABEL_57;
    }
    if ( a4 )
      break;
    if ( !i )
    {
      if ( v11 )
      {
        FreeSystemRelativePath(&String2);
        if ( !(unsigned int)MakeSystemRelativePath(Source, &String2) )
          goto LABEL_57;
      }
      break;
    }
    FreeSystemRelativePath(&String2);
    if ( !(unsigned int)MakeSystemDriversRelativePath(Source, &String2) )
      break;
    v11 = 1;
  }
  v13 = (UNICODE_STRING *)PALLOCMEM(48, 1986292807);
  v14 = PALLOCMEM(912, 1986292807);
  v15 = v14;
  if ( v13 )
  {
    if ( !v14 )
    {
LABEL_52:
      GreDeleteFastMutex(v13);
      goto LABEL_53;
    }
    v16 = Size;
    *(_QWORD *)(v14 + 904) = v14 + 72;
    v17 = 1;
    *(_DWORD *)(v14 + 68) = 0;
    while ( 1 )
    {
      v18 = v43;
      v19 = SystemLoadGdiDriverInformation;
      *v13 = String2;
      *(_DWORD *)(v18 + 1144) = 0;
      if ( !v16 )
        v19 = SystemLoadGdiDriverInSystemSpaceInformation;
      v20 = ZwSetSystemInformation(v19, v13, 0x30u);
      v21 = v20;
      if ( v20 >= 0 )
        goto LABEL_47;
      if ( v20 != -1073741554 )
        *(_DWORD *)(v43 + 1144) = 3;
      if ( v16 )
        goto LABEL_50;
      if ( v20 != -1073741772 )
        break;
      if ( !v17 )
        goto LABEL_52;
      FreeSystemRelativePath(&String2);
      if ( !(unsigned int)MakeSystemDriversRelativePath(Source, &String2) )
        goto LABEL_52;
      v17 = 0;
    }
    if ( v20 != -1073741554 )
      goto LABEL_50;
    memset(SystemInformation, 0, sizeof(SystemInformation));
    ReturnLength = 0;
    AnsiString = 0;
    DestinationString = 0;
    v22 = wcsrchr(Source, 0x5Cu);
    v23 = v22 ? v22 + 1 : Source;
    RtlInitUnicodeString(&DestinationString, v23);
    v21 = RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u);
    if ( v21 < 0 )
    {
LABEL_50:
      if ( v21 == -1073741702 )
        DrvLogDisplayDriverEvent(3);
      goto LABEL_52;
    }
    v24 = 0;
    v21 = ZwQuerySystemInformation(SystemModuleInformation, SystemInformation, 0x130u, &ReturnLength);
    if ( (int)(v21 + 0x80000000) < 0 || v21 == -1073741820 )
    {
      v25 = 296 * SystemInformation[0];
      v26 = (unsigned int *)PALLOCNOZ((unsigned int)(296 * SystemInformation[0] + 8), 1886221383);
      v27 = v26;
      if ( v26 )
      {
        v21 = ZwQuerySystemInformation(SystemModuleInformation, v26, v25 + 8, &ReturnLength);
        if ( v21 >= 0 )
        {
          for ( j = 0; j < *v27; ++j )
          {
            if ( !strnicmp(
                    (const char *)&v27[74 * j + 12] + HIWORD(v27[74 * j + 11]),
                    AnsiString.Buffer,
                    AnsiString.Length) )
            {
              Size = 0;
              for ( k = RtlImageDirectoryEntryToData(gpvWin32kImageBase, 1u, 1u, &Size); k; k += 5 )
              {
                v30 = k[3];
                if ( !v30 || !*k )
                  break;
                if ( !strnicmp((const char *)gpvWin32kImageBase + v30, AnsiString.Buffer, AnsiString.Length) )
                {
                  v24 = 1;
                  v31 = *(char **)&v27[74 * j + 6];
                  AddressOfEntryPoint = RtlImageNtHeader(v31)->OptionalHeader.AddressOfEntryPoint;
                  *(_QWORD *)&v13[1].Length = v31;
                  *(_QWORD *)&v13[2].Length = &v31[AddressOfEntryPoint];
                  v13[1].Buffer = 0;
                  goto LABEL_43;
                }
              }
              goto LABEL_43;
            }
          }
        }
      }
      else
      {
LABEL_43:
        if ( !v27 )
          goto LABEL_45;
      }
      GreDeleteFastMutex(v27);
    }
LABEL_45:
    RtlFreeAnsiString(&AnsiString);
    if ( v24 )
    {
      *(_DWORD *)(v15 + 40) |= 2u;
LABEL_47:
      v33 = 4 * v41;
      v34 = 4 * v41;
      *(_QWORD *)(v15 + 16) = v13;
      v35 = (*(_DWORD *)(v15 + 40) ^ v34) & 0xFFFFFFFB;
      *(_DWORD *)(v15 + 36) = 1;
      *(_DWORD *)(v15 + 32) = 5;
      *(_DWORD *)(v15 + 40) = v33 ^ v35;
      v36 = v43;
      *(_DWORD *)(v15 + 64) = -1;
      v37 = *(_QWORD *)(v36 + 1816);
      if ( v37 )
        *(_QWORD *)(v37 + 8) = v15;
      *(_QWORD *)v15 = *(_QWORD *)(v36 + 1816);
      *(_QWORD *)(v15 + 8) = 0;
      *(_QWORD *)(v36 + 1816) = v15;
      WdLogSingleEntry1(5, v15);
      result = (struct _LDEV *)v15;
      WdLogGlobalForLineNumber = 1167;
      return result;
    }
    goto LABEL_50;
  }
LABEL_53:
  if ( v15 )
    GreDeleteFastMutex((PVOID)v15);
  v9 = 0;
LABEL_57:
  FreeSystemRelativePath(&String2);
LABEL_58:
  WdLogSingleEntry1(5, v9);
  result = v9;
  WdLogGlobalForLineNumber = 1369;
  return result;
}

```

## disassembly

```asm
0x14016be3c  push    rbp
0x14016be3e  push    rbx
0x14016be3f  push    rsi
0x14016be40  push    rdi
0x14016be41  push    r12
0x14016be43  push    r13
0x14016be45  push    r14
0x14016be47  push    r15
0x14016be49  lea     rbp, [rsp-0B8h]
0x14016be51  sub     rsp, 1B8h
0x14016be58  mov     rax, cs:__security_cookie
0x14016be5f  xor     rax, rsp
0x14016be62  mov     [rbp+0F0h+var_50], rax
0x14016be69  mov     eax, [rbp+0F0h+arg_20]
0x14016be6f  xorps   xmm0, xmm0
0x14016be72  movsxd  r13, r9d
0x14016be75  mov     r15, r8
0x14016be78  mov     [rsp+1F0h+Size], r13d
0x14016be7d  mov     r14, rcx
0x14016be80  movups  xmmword ptr [rsp+1F0h+String2.Length], xmm0
0x14016be85  movsxd  r12, edx
0x14016be88  xor     ebx, ebx
0x14016be8a  mov     [rsp+1F0h+var_1C8], eax
0x14016be8e  mov     rdx, rcx
0x14016be91  mov     r9, r13
0x14016be94  lea     ecx, [rbx+4]
0x14016be97  mov     r8, r12
0x14016be9a  call    cs:__imp_WdLogSingleEntry3
0x14016bea1  nop     dword ptr [rax+rax+00h]
0x14016bea6  xor     eax, eax
0x14016bea8  mov     cs:WdLogGlobalForLineNumber, 3E7h
0x14016beb2  test    r12d, r12d
0x14016beb5  mov     [r15], ebx
0x14016beb8  lea     rdx, [rsp+1F0h+String2]; Destination
0x14016bebd  mov     rcx, r14; Source
0x14016bec0  setz    al
0x14016bec3  mov     r8d, eax
0x14016bec6  mov     [rsp+1F0h+ReturnLength], eax
0x14016beca  call    MakeSystemRelativePath
0x14016becf  test    eax, eax
0x14016bed1  jz      loc_14016C327
0x14016bed7  xor     edi, edi
0x14016bed9  lea     esi, [rbx+1]
0x14016bedc  call    cs:__imp_W32GetSessionState
0x14016bee3  nop     dword ptr [rax+rax+00h]
0x14016bee8  mov     r8d, [rsp+1F0h+var_1C8]
0x14016beed  lea     rcx, [rsp+1F0h+String2]; String2
0x14016bef2  mov     edx, r12d
0x14016bef5  mov     rax, [rax+58h]
0x14016bef9  mov     [rsp+1F0h+var_1B0], rax
0x14016befe  call    ldevTryReferenceLoadedDisplayDriver
0x14016bf03  mov     rbx, rax
0x14016bf06  test    rax, rax
0x14016bf09  jnz     loc_14016C316
0x14016bf0f  test    r13d, r13d
0x14016bf12  jnz     short loc_14016BF6B
0x14016bf14  test    esi, esi
0x14016bf16  jz      short loc_14016BF3F
0x14016bf18  lea     rcx, [rsp+1F0h+String2]
0x14016bf1d  call    FreeSystemRelativePath
0x14016bf22  mov     r8d, [rsp+1F0h+ReturnLength]
0x14016bf27  lea     rdx, [rsp+1F0h+String2]; Destination
0x14016bf2c  mov     rcx, r14; Source
0x14016bf2f  call    MakeSystemDriversRelativePath
0x14016bf34  test    eax, eax
0x14016bf36  jz      short loc_14016BF6B
0x14016bf38  xor     esi, esi
0x14016bf3a  lea     edi, [rbx+1]
0x14016bf3d  jmp     short loc_14016BEDC
0x14016bf3f  test    edi, edi
0x14016bf41  jz      short loc_14016BF6B
0x14016bf43  lea     rcx, [rsp+1F0h+String2]
0x14016bf48  call    FreeSystemRelativePath
0x14016bf4d  mov     r12d, [rsp+1F0h+ReturnLength]
0x14016bf52  lea     rdx, [rsp+1F0h+String2]; Destination
0x14016bf57  mov     r8d, r12d
0x14016bf5a  mov     rcx, r14; Source
0x14016bf5d  call    MakeSystemRelativePath
0x14016bf62  test    eax, eax
0x14016bf64  jnz     short loc_14016BF70
0x14016bf66  jmp     loc_14016C31D
0x14016bf6b  mov     r12d, [rsp+1F0h+ReturnLength]
0x14016bf70  mov     ebx, 76646C47h
0x14016bf75  mov     ecx, 30h ; '0'
0x14016bf7a  mov     edx, ebx
0x14016bf7c  call    PALLOCMEM
0x14016bf81  mov     edx, ebx
0x14016bf83  mov     ecx, 390h
0x14016bf88  mov     r13, rax
0x14016bf8b  call    PALLOCMEM
0x14016bf90  mov     rdi, rax
0x14016bf93  test    r13, r13
0x14016bf96  jz      loc_14016C305
0x14016bf9c  test    rax, rax
0x14016bf9f  jz      loc_14016C2FD
0x14016bfa5  mov     r15d, [rsp+1F0h+Size]
0x14016bfaa  lea     rcx, [rax+48h]
0x14016bfae  mov     [rax+388h], rcx
0x14016bfb5  mov     ebx, 1
0x14016bfba  mov     dword ptr [rax+44h], 0
0x14016bfc1  mov     rax, [rsp+1F0h+var_1B0]
0x14016bfc6  mov     r8d, 30h ; '0'; SystemInformationLength
0x14016bfcc  mov     rdx, r13; SystemInformation
0x14016bfcf  movups  xmm0, xmmword ptr [rsp+1F0h+String2.Length]
0x14016bfd4  lea     ecx, [r8-16h]
0x14016bfd8  movdqu  xmmword ptr [r13+0], xmm0
0x14016bfde  mov     dword ptr [rax+478h], 0
0x14016bfe8  test    r15d, r15d
0x14016bfeb  jnz     short loc_14016BFF1
0x14016bfed  lea     ecx, [r8+6]; SystemInformationClass
0x14016bff1  call    cs:__imp_ZwSetSystemInformation
0x14016bff8  nop     dword ptr [rax+rax+00h]
0x14016bffd  mov     esi, eax
0x14016bfff  test    eax, eax
0x14016c001  jns     loc_14016C26D
0x14016c007  cmp     eax, 0C000010Eh
0x14016c00c  jz      short loc_14016C01D
0x14016c00e  mov     rax, [rsp+1F0h+var_1B0]
0x14016c013  mov     dword ptr [rax+478h], 3
0x14016c01d  test    r15d, r15d
0x14016c020  jnz     loc_14016C2EB
0x14016c026  cmp     esi, 0C0000034h
0x14016c02c  jnz     short loc_14016C05F
0x14016c02e  test    ebx, ebx
0x14016c030  jz      loc_14016C2FD
0x14016c036  lea     rcx, [rsp+1F0h+String2]
0x14016c03b  call    FreeSystemRelativePath
0x14016c040  mov     r8d, r12d
0x14016c043  lea     rdx, [rsp+1F0h+String2]; Destination
0x14016c048  mov     rcx, r14; Source
0x14016c04b  call    MakeSystemDriversRelativePath
0x14016c050  test    eax, eax
0x14016c052  jz      loc_14016C2FD
0x14016c058  xor     ebx, ebx
0x14016c05a  jmp     loc_14016BFC1
0x14016c05f  cmp     esi, 0C000010Eh
0x14016c065  jnz     loc_14016C2EB
0x14016c06b  mov     ebx, 130h
0x14016c070  lea     rcx, [rsp+1F0h+SystemInformation]; void *
0x14016c075  mov     r8d, ebx; Size
0x14016c078  xor     edx, edx; Val
0x14016c07a  call    memset
0x14016c07f  xorps   xmm0, xmm0
0x14016c082  mov     [rsp+1F0h+ReturnLength], 0
0x14016c08a  xorps   xmm1, xmm1
0x14016c08d  mov     edx, 5Ch ; '\'; Ch
0x14016c092  mov     rcx, r14; Str
0x14016c095  movups  xmmword ptr [rsp+1F0h+AnsiString.Length], xmm0
0x14016c09a  movups  xmmword ptr [rsp+1F0h+DestinationString.Length], xmm1
0x14016c09f  call    wcsrchr
0x14016c0a4  test    rax, rax
0x14016c0a7  jz      short loc_14016C0AF
0x14016c0a9  add     rax, 2
0x14016c0ad  jmp     short loc_14016C0B2
0x14016c0af  mov     rax, r14
0x14016c0b2  mov     rdx, rax; SourceString
0x14016c0b5  lea     rcx, [rsp+1F0h+DestinationString]; DestinationString
0x14016c0ba  call    cs:__imp_RtlInitUnicodeString
0x14016c0c1  nop     dword ptr [rax+rax+00h]
0x14016c0c6  mov     r8b, 1; AllocateDestinationString
0x14016c0c9  lea     rdx, [rsp+1F0h+DestinationString]; SourceString
0x14016c0ce  lea     rcx, [rsp+1F0h+AnsiString]; DestinationString
0x14016c0d3  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14016c0da  nop     dword ptr [rax+rax+00h]
0x14016c0df  mov     esi, eax
0x14016c0e1  test    eax, eax
0x14016c0e3  js      loc_14016C2EB
0x14016c0e9  xor     r12d, r12d
0x14016c0ec  lea     r9, [rsp+1F0h+ReturnLength]; ReturnLength
0x14016c0f1  mov     r8d, ebx; SystemInformationLength
0x14016c0f4  lea     rdx, [rsp+1F0h+SystemInformation]; SystemInformation
0x14016c0f9  lea     r15d, [r12+0Bh]
0x14016c0fe  mov     ecx, r15d; SystemInformationClass
0x14016c101  call    cs:__imp_ZwQuerySystemInformation
0x14016c108  nop     dword ptr [rax+rax+00h]
0x14016c10d  mov     ecx, 80000000h
0x14016c112  mov     esi, eax
0x14016c114  add     eax, ecx
0x14016c116  test    ecx, eax
0x14016c118  jnz     short loc_14016C126
0x14016c11a  cmp     esi, 0C0000004h
0x14016c120  jnz     loc_14016C24F
0x14016c126  imul    ebx, [rsp+1F0h+SystemInformation], 128h
0x14016c12e  mov     edx, 706D7447h
0x14016c133  lea     ecx, [rbx+8]
0x14016c136  call    PALLOCNOZ
0x14016c13b  mov     r14, rax
0x14016c13e  test    rax, rax
0x14016c141  jz      loc_14016C242
0x14016c147  lea     r9, [rsp+1F0h+ReturnLength]; ReturnLength
0x14016c14c  mov     rdx, rax; SystemInformation
0x14016c14f  lea     r8d, [rbx+8]; SystemInformationLength
0x14016c153  mov     ecx, r15d; SystemInformationClass
0x14016c156  call    cs:__imp_ZwQuerySystemInformation
0x14016c15d  nop     dword ptr [rax+rax+00h]
0x14016c162  mov     esi, eax
0x14016c164  test    eax, eax
0x14016c166  js      loc_14016C247
0x14016c16c  xor     r15d, r15d
0x14016c16f  cmp     r15d, [r14]
0x14016c172  jnb     loc_14016C247
0x14016c178  movzx   r8d, [rsp+1F0h+AnsiString.Length]; MaxCount
0x14016c17e  mov     rdx, [rsp+1F0h+AnsiString.Buffer]; Str2
0x14016c183  mov     eax, r15d
0x14016c186  imul    rcx, rax, 128h
0x14016c18d  movzx   eax, word ptr [rcx+r14+2Eh]
0x14016c193  add     rax, 30h ; '0'
0x14016c197  add     rcx, rax
0x14016c19a  add     rcx, r14; Str1
0x14016c19d  call    _strnicmp
0x14016c1a2  test    eax, eax
0x14016c1a4  jz      short loc_14016C1AB
0x14016c1a6  inc     r15d
0x14016c1a9  jmp     short loc_14016C16F
0x14016c1ab  mov     rcx, cs:?gpvWin32kImageBase@@3PEAXEA; BaseAddress
0x14016c1b2  lea     r9, [rsp+1F0h+Size]; Size
0x14016c1b7  mov     r8d, 1; Directory
0x14016c1bd  mov     [rsp+1F0h+Size], r12d
0x14016c1c2  mov     dl, r8b; MappedAsImage
0x14016c1c5  call    cs:__imp_RtlImageDirectoryEntryToData
0x14016c1cc  nop     dword ptr [rax+rax+00h]
0x14016c1d1  mov     rbx, rax
0x14016c1d4  test    rbx, rbx
0x14016c1d7  jz      short loc_14016C242
0x14016c1d9  mov     eax, [rbx+0Ch]
0x14016c1dc  test    eax, eax
0x14016c1de  jz      short loc_14016C242
0x14016c1e0  cmp     [rbx], r12d
0x14016c1e3  jz      short loc_14016C242
0x14016c1e5  movzx   r8d, [rsp+1F0h+AnsiString.Length]; MaxCount
0x14016c1eb  mov     ecx, eax
0x14016c1ed  add     rcx, cs:?gpvWin32kImageBase@@3PEAXEA; Str1
0x14016c1f4  mov     rdx, [rsp+1F0h+AnsiString.Buffer]; Str2
0x14016c1f9  call    _strnicmp
0x14016c1fe  test    eax, eax
0x14016c200  jz      short loc_14016C208
0x14016c202  add     rbx, 14h
0x14016c206  jmp     short loc_14016C1D4
0x14016c208  mov     eax, r15d
0x14016c20b  mov     r12d, 1
0x14016c211  imul    rcx, rax, 128h
0x14016c218  mov     rbx, [rcx+r14+18h]
0x14016c21d  mov     rcx, rbx; BaseAddress
0x14016c220  call    cs:__imp_RtlImageNtHeader
0x14016c227  nop     dword ptr [rax+rax+00h]
0x14016c22c  mov     eax, [rax+28h]
0x14016c22f  add     rax, rbx
0x14016c232  mov     [r13+10h], rbx
0x14016c236  mov     [r13+20h], rax
0x14016c23a  mov     qword ptr [r13+18h], 0
0x14016c242  test    r14, r14
0x14016c245  jz      short loc_14016C24F
0x14016c247  mov     rcx, r14; Buffer
0x14016c24a  call    GreDeleteFastMutex
0x14016c24f  lea     rcx, [rsp+1F0h+AnsiString]; AnsiString
0x14016c254  call    cs:__imp_RtlFreeAnsiString
0x14016c25b  nop     dword ptr [rax+rax+00h]
0x14016c260  test    r12d, r12d
0x14016c263  jz      loc_14016C2EB
0x14016c269  or      dword ptr [rdi+28h], 2
0x14016c26d  mov     eax, [rsp+1F0h+var_1C8]
0x14016c271  shl     eax, 2
0x14016c274  mov     ecx, eax
0x14016c276  mov     [rdi+10h], r13
0x14016c27a  xor     ecx, [rdi+28h]
0x14016c27d  and     ecx, 0FFFFFFFBh
0x14016c280  mov     dword ptr [rdi+24h], 1
0x14016c287  xor     ecx, eax
0x14016c289  mov     dword ptr [rdi+20h], 5
0x14016c290  mov     [rdi+28h], ecx
0x14016c293  mov     rcx, [rsp+1F0h+var_1B0]
0x14016c298  mov     dword ptr [rdi+40h], 0FFFFFFFFh
0x14016c29f  mov     rax, [rcx+718h]
0x14016c2a6  test    rax, rax
0x14016c2a9  jz      short loc_14016C2AF
0x14016c2ab  mov     [rax+8], rdi
0x14016c2af  mov     rdx, [rcx+718h]
0x14016c2b6  mov     [rdi], rdx
0x14016c2b9  mov     qword ptr [rdi+8], 0
0x14016c2c1  mov     [rcx+718h], rdi
0x14016c2c8  mov     rdx, rdi
0x14016c2cb  mov     ecx, 5
0x14016c2d0  call    cs:__imp_WdLogSingleEntry1
0x14016c2d7  nop     dword ptr [rax+rax+00h]
0x14016c2dc  mov     rax, rdi
0x14016c2df  mov     cs:WdLogGlobalForLineNumber, 48Fh
0x14016c2e9  jmp     short loc_14016C348
0x14016c2eb  cmp     esi, 0C000007Ah
0x14016c2f1  jnz     short loc_14016C2FD
0x14016c2f3  mov     ecx, 3
0x14016c2f8  call    ?DrvLogDisplayDriverEvent@@YAXW4_DISP_DRIVER_LOG@@@Z; DrvLogDisplayDriverEvent(_DISP_DRIVER_LOG)
0x14016c2fd  mov     rcx, r13; Buffer
0x14016c300  call    GreDeleteFastMutex
0x14016c305  test    rdi, rdi
0x14016c308  jz      short loc_14016C312
0x14016c30a  mov     rcx, rdi; Buffer
0x14016c30d  call    GreDeleteFastMutex
0x14016c312  xor     ebx, ebx
0x14016c314  jmp     short loc_14016C31D
0x14016c316  mov     dword ptr [r15], 1
  ... truncated ...
```
