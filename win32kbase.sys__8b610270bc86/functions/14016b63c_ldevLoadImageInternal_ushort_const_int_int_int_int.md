# ldevLoadImageInternal(ushort const *,int,int *,int,int)

- ea: `0x14016b63c`
- end: `0x14016bb6c`
- name: `?ldevLoadImageInternal@@YAPEAU_LDEV@@PEBGHPEAHHH@Z`
- size: `1328`
- prototype: `struct _LDEV *__usercall@<rax>(PCWSTR Source@<rcx>, int@<edx>, int *@<r8>, int@<r9d>, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x14019bd60`

## callees

- `0x140040394`
- `0x1400411c0`
- `0x14009202c`
- `0x14016b63c`
- `0x14016bb80`
- `0x14017806c`
- `0x140193a10`
- `0x1401b2624`
- `0x1401b6a14`
- `0x1401c4858`
- `0x1401c4978`
- `0x140238b10`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!ZwSetSystemInformation` at `0x14016b7f1`
- `ntoskrnl!ZwSetSystemInformation` at `0x14016b7f1`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14016b901`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14016b956`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14016b901`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14016b956`
- `ntoskrnl!RtlImageNtHeader` at `0x14016ba20`
- `ntoskrnl!RtlImageNtHeader` at `0x14016ba20`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14016b8d3`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14016b8d3`
- `ntoskrnl!RtlFreeAnsiString` at `0x14016ba54`
- `ntoskrnl!RtlFreeAnsiString` at `0x14016ba54`
- `ntoskrnl!RtlImageDirectoryEntryToData` at `0x14016b9c5`
- `ntoskrnl!RtlImageDirectoryEntryToData` at `0x14016b9c5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14016b8ba`
- `ntoskrnl!RtlInitUnicodeString` at `0x14016b8ba`
- `watchdog!WdLogSingleEntry3` at `0x14016b69a`
- `watchdog!WdLogSingleEntry3` at `0x14016b69a`
- `watchdog!WdLogSingleEntry1` at `0x14016bad0`
- `watchdog!WdLogSingleEntry1` at `0x14016bb2f`
- `watchdog!WdLogSingleEntry1` at `0x14016bad0`
- `watchdog!WdLogSingleEntry1` at `0x14016bb2f`
- `WIN32K!W32GetSessionState` at `0x14016b6dc`
- `WIN32K!W32GetSessionState` at `0x14016b6dc`

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
0x14016b63c  push    rbp
0x14016b63e  push    rbx
0x14016b63f  push    rsi
0x14016b640  push    rdi
0x14016b641  push    r12
0x14016b643  push    r13
0x14016b645  push    r14
0x14016b647  push    r15
0x14016b649  lea     rbp, [rsp-0B8h]
0x14016b651  sub     rsp, 1B8h
0x14016b658  mov     rax, cs:__security_cookie
0x14016b65f  xor     rax, rsp
0x14016b662  mov     [rbp+0F0h+var_50], rax
0x14016b669  mov     eax, [rbp+0F0h+arg_20]
0x14016b66f  xorps   xmm0, xmm0
0x14016b672  movsxd  r13, r9d
0x14016b675  mov     r15, r8
0x14016b678  mov     [rsp+1F0h+Size], r13d
0x14016b67d  mov     r14, rcx
0x14016b680  movups  xmmword ptr [rsp+1F0h+String2.Length], xmm0
0x14016b685  movsxd  r12, edx
0x14016b688  xor     ebx, ebx
0x14016b68a  mov     [rsp+1F0h+var_1C8], eax
0x14016b68e  mov     rdx, rcx
0x14016b691  mov     r9, r13
0x14016b694  lea     ecx, [rbx+4]
0x14016b697  mov     r8, r12
0x14016b69a  call    cs:__imp_WdLogSingleEntry3
0x14016b6a1  nop     dword ptr [rax+rax+00h]
0x14016b6a6  xor     eax, eax
0x14016b6a8  mov     cs:WdLogGlobalForLineNumber, 3E7h
0x14016b6b2  test    r12d, r12d
0x14016b6b5  mov     [r15], ebx
0x14016b6b8  lea     rdx, [rsp+1F0h+String2]; Destination
0x14016b6bd  mov     rcx, r14; Source
0x14016b6c0  setz    al
0x14016b6c3  mov     r8d, eax
0x14016b6c6  mov     [rsp+1F0h+ReturnLength], eax
0x14016b6ca  call    MakeSystemRelativePath
0x14016b6cf  test    eax, eax
0x14016b6d1  jz      loc_14016BB27
0x14016b6d7  xor     edi, edi
0x14016b6d9  lea     esi, [rbx+1]
0x14016b6dc  call    cs:__imp_W32GetSessionState
0x14016b6e3  nop     dword ptr [rax+rax+00h]
0x14016b6e8  mov     r8d, [rsp+1F0h+var_1C8]
0x14016b6ed  lea     rcx, [rsp+1F0h+String2]; String2
0x14016b6f2  mov     edx, r12d
0x14016b6f5  mov     rax, [rax+58h]
0x14016b6f9  mov     [rsp+1F0h+var_1B0], rax
0x14016b6fe  call    ldevTryReferenceLoadedDisplayDriver
0x14016b703  mov     rbx, rax
0x14016b706  test    rax, rax
0x14016b709  jnz     loc_14016BB16
0x14016b70f  test    r13d, r13d
0x14016b712  jnz     short loc_14016B76B
0x14016b714  test    esi, esi
0x14016b716  jz      short loc_14016B73F
0x14016b718  lea     rcx, [rsp+1F0h+String2]
0x14016b71d  call    FreeSystemRelativePath
0x14016b722  mov     r8d, [rsp+1F0h+ReturnLength]
0x14016b727  lea     rdx, [rsp+1F0h+String2]; Destination
0x14016b72c  mov     rcx, r14; Source
0x14016b72f  call    MakeSystemDriversRelativePath
0x14016b734  test    eax, eax
0x14016b736  jz      short loc_14016B76B
0x14016b738  xor     esi, esi
0x14016b73a  lea     edi, [rbx+1]
0x14016b73d  jmp     short loc_14016B6DC
0x14016b73f  test    edi, edi
0x14016b741  jz      short loc_14016B76B
0x14016b743  lea     rcx, [rsp+1F0h+String2]
0x14016b748  call    FreeSystemRelativePath
0x14016b74d  mov     r12d, [rsp+1F0h+ReturnLength]
0x14016b752  lea     rdx, [rsp+1F0h+String2]; Destination
0x14016b757  mov     r8d, r12d
0x14016b75a  mov     rcx, r14; Source
0x14016b75d  call    MakeSystemRelativePath
0x14016b762  test    eax, eax
0x14016b764  jnz     short loc_14016B770
0x14016b766  jmp     loc_14016BB1D
0x14016b76b  mov     r12d, [rsp+1F0h+ReturnLength]
0x14016b770  mov     ebx, 76646C47h
0x14016b775  mov     ecx, 30h ; '0'
0x14016b77a  mov     edx, ebx
0x14016b77c  call    PALLOCMEM
0x14016b781  mov     edx, ebx
0x14016b783  mov     ecx, 390h
0x14016b788  mov     r13, rax
0x14016b78b  call    PALLOCMEM
0x14016b790  mov     rdi, rax
0x14016b793  test    r13, r13
0x14016b796  jz      loc_14016BB05
0x14016b79c  test    rax, rax
0x14016b79f  jz      loc_14016BAFD
0x14016b7a5  mov     r15d, [rsp+1F0h+Size]
0x14016b7aa  lea     rcx, [rax+48h]
0x14016b7ae  mov     [rax+388h], rcx
0x14016b7b5  mov     ebx, 1
0x14016b7ba  mov     dword ptr [rax+44h], 0
0x14016b7c1  mov     rax, [rsp+1F0h+var_1B0]
0x14016b7c6  mov     r8d, 30h ; '0'; SystemInformationLength
0x14016b7cc  mov     rdx, r13; SystemInformation
0x14016b7cf  movups  xmm0, xmmword ptr [rsp+1F0h+String2.Length]
0x14016b7d4  lea     ecx, [r8-16h]
0x14016b7d8  movdqu  xmmword ptr [r13+0], xmm0
0x14016b7de  mov     dword ptr [rax+478h], 0
0x14016b7e8  test    r15d, r15d
0x14016b7eb  jnz     short loc_14016B7F1
0x14016b7ed  lea     ecx, [r8+6]; SystemInformationClass
0x14016b7f1  call    cs:__imp_ZwSetSystemInformation
0x14016b7f8  nop     dword ptr [rax+rax+00h]
0x14016b7fd  mov     esi, eax
0x14016b7ff  test    eax, eax
0x14016b801  jns     loc_14016BA6D
0x14016b807  cmp     eax, 0C000010Eh
0x14016b80c  jz      short loc_14016B81D
0x14016b80e  mov     rax, [rsp+1F0h+var_1B0]
0x14016b813  mov     dword ptr [rax+478h], 3
0x14016b81d  test    r15d, r15d
0x14016b820  jnz     loc_14016BAEB
0x14016b826  cmp     esi, 0C0000034h
0x14016b82c  jnz     short loc_14016B85F
0x14016b82e  test    ebx, ebx
0x14016b830  jz      loc_14016BAFD
0x14016b836  lea     rcx, [rsp+1F0h+String2]
0x14016b83b  call    FreeSystemRelativePath
0x14016b840  mov     r8d, r12d
0x14016b843  lea     rdx, [rsp+1F0h+String2]; Destination
0x14016b848  mov     rcx, r14; Source
0x14016b84b  call    MakeSystemDriversRelativePath
0x14016b850  test    eax, eax
0x14016b852  jz      loc_14016BAFD
0x14016b858  xor     ebx, ebx
0x14016b85a  jmp     loc_14016B7C1
0x14016b85f  cmp     esi, 0C000010Eh
0x14016b865  jnz     loc_14016BAEB
0x14016b86b  mov     ebx, 130h
0x14016b870  lea     rcx, [rsp+1F0h+SystemInformation]; void *
0x14016b875  mov     r8d, ebx; Size
0x14016b878  xor     edx, edx; Val
0x14016b87a  call    memset
0x14016b87f  xorps   xmm0, xmm0
0x14016b882  mov     [rsp+1F0h+ReturnLength], 0
0x14016b88a  xorps   xmm1, xmm1
0x14016b88d  mov     edx, 5Ch ; '\'; Ch
0x14016b892  mov     rcx, r14; Str
0x14016b895  movups  xmmword ptr [rsp+1F0h+AnsiString.Length], xmm0
0x14016b89a  movups  xmmword ptr [rsp+1F0h+DestinationString.Length], xmm1
0x14016b89f  call    wcsrchr
0x14016b8a4  test    rax, rax
0x14016b8a7  jz      short loc_14016B8AF
0x14016b8a9  add     rax, 2
0x14016b8ad  jmp     short loc_14016B8B2
0x14016b8af  mov     rax, r14
0x14016b8b2  mov     rdx, rax; SourceString
0x14016b8b5  lea     rcx, [rsp+1F0h+DestinationString]; DestinationString
0x14016b8ba  call    cs:__imp_RtlInitUnicodeString
0x14016b8c1  nop     dword ptr [rax+rax+00h]
0x14016b8c6  mov     r8b, 1; AllocateDestinationString
0x14016b8c9  lea     rdx, [rsp+1F0h+DestinationString]; SourceString
0x14016b8ce  lea     rcx, [rsp+1F0h+AnsiString]; DestinationString
0x14016b8d3  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14016b8da  nop     dword ptr [rax+rax+00h]
0x14016b8df  mov     esi, eax
0x14016b8e1  test    eax, eax
0x14016b8e3  js      loc_14016BAEB
0x14016b8e9  xor     r12d, r12d
0x14016b8ec  lea     r9, [rsp+1F0h+ReturnLength]; ReturnLength
0x14016b8f1  mov     r8d, ebx; SystemInformationLength
0x14016b8f4  lea     rdx, [rsp+1F0h+SystemInformation]; SystemInformation
0x14016b8f9  lea     r15d, [r12+0Bh]
0x14016b8fe  mov     ecx, r15d; SystemInformationClass
0x14016b901  call    cs:__imp_ZwQuerySystemInformation
0x14016b908  nop     dword ptr [rax+rax+00h]
0x14016b90d  mov     ecx, 80000000h
0x14016b912  mov     esi, eax
0x14016b914  add     eax, ecx
0x14016b916  test    ecx, eax
0x14016b918  jnz     short loc_14016B926
0x14016b91a  cmp     esi, 0C0000004h
0x14016b920  jnz     loc_14016BA4F
0x14016b926  imul    ebx, [rsp+1F0h+SystemInformation], 128h
0x14016b92e  mov     edx, 706D7447h
0x14016b933  lea     ecx, [rbx+8]
0x14016b936  call    PALLOCNOZ
0x14016b93b  mov     r14, rax
0x14016b93e  test    rax, rax
0x14016b941  jz      loc_14016BA42
0x14016b947  lea     r9, [rsp+1F0h+ReturnLength]; ReturnLength
0x14016b94c  mov     rdx, rax; SystemInformation
0x14016b94f  lea     r8d, [rbx+8]; SystemInformationLength
0x14016b953  mov     ecx, r15d; SystemInformationClass
0x14016b956  call    cs:__imp_ZwQuerySystemInformation
0x14016b95d  nop     dword ptr [rax+rax+00h]
0x14016b962  mov     esi, eax
0x14016b964  test    eax, eax
0x14016b966  js      loc_14016BA47
0x14016b96c  xor     r15d, r15d
0x14016b96f  cmp     r15d, [r14]
0x14016b972  jnb     loc_14016BA47
0x14016b978  movzx   r8d, [rsp+1F0h+AnsiString.Length]; MaxCount
0x14016b97e  mov     rdx, [rsp+1F0h+AnsiString.Buffer]; Str2
0x14016b983  mov     eax, r15d
0x14016b986  imul    rcx, rax, 128h
0x14016b98d  movzx   eax, word ptr [rcx+r14+2Eh]
0x14016b993  add     rax, 30h ; '0'
0x14016b997  add     rcx, rax
0x14016b99a  add     rcx, r14; Str1
0x14016b99d  call    _strnicmp
0x14016b9a2  test    eax, eax
0x14016b9a4  jz      short loc_14016B9AB
0x14016b9a6  inc     r15d
0x14016b9a9  jmp     short loc_14016B96F
0x14016b9ab  mov     rcx, cs:?gpvWin32kImageBase@@3PEAXEA; BaseAddress
0x14016b9b2  lea     r9, [rsp+1F0h+Size]; Size
0x14016b9b7  mov     r8d, 1; Directory
0x14016b9bd  mov     [rsp+1F0h+Size], r12d
0x14016b9c2  mov     dl, r8b; MappedAsImage
0x14016b9c5  call    cs:__imp_RtlImageDirectoryEntryToData
0x14016b9cc  nop     dword ptr [rax+rax+00h]
0x14016b9d1  mov     rbx, rax
0x14016b9d4  test    rbx, rbx
0x14016b9d7  jz      short loc_14016BA42
0x14016b9d9  mov     eax, [rbx+0Ch]
0x14016b9dc  test    eax, eax
0x14016b9de  jz      short loc_14016BA42
0x14016b9e0  cmp     [rbx], r12d
0x14016b9e3  jz      short loc_14016BA42
0x14016b9e5  movzx   r8d, [rsp+1F0h+AnsiString.Length]; MaxCount
0x14016b9eb  mov     ecx, eax
0x14016b9ed  add     rcx, cs:?gpvWin32kImageBase@@3PEAXEA; Str1
0x14016b9f4  mov     rdx, [rsp+1F0h+AnsiString.Buffer]; Str2
0x14016b9f9  call    _strnicmp
0x14016b9fe  test    eax, eax
0x14016ba00  jz      short loc_14016BA08
0x14016ba02  add     rbx, 14h
0x14016ba06  jmp     short loc_14016B9D4
0x14016ba08  mov     eax, r15d
0x14016ba0b  mov     r12d, 1
0x14016ba11  imul    rcx, rax, 128h
0x14016ba18  mov     rbx, [rcx+r14+18h]
0x14016ba1d  mov     rcx, rbx; BaseAddress
0x14016ba20  call    cs:__imp_RtlImageNtHeader
0x14016ba27  nop     dword ptr [rax+rax+00h]
0x14016ba2c  mov     eax, [rax+28h]
0x14016ba2f  add     rax, rbx
0x14016ba32  mov     [r13+10h], rbx
0x14016ba36  mov     [r13+20h], rax
0x14016ba3a  mov     qword ptr [r13+18h], 0
0x14016ba42  test    r14, r14
0x14016ba45  jz      short loc_14016BA4F
0x14016ba47  mov     rcx, r14; Buffer
0x14016ba4a  call    GreDeleteFastMutex
0x14016ba4f  lea     rcx, [rsp+1F0h+AnsiString]; AnsiString
0x14016ba54  call    cs:__imp_RtlFreeAnsiString
0x14016ba5b  nop     dword ptr [rax+rax+00h]
0x14016ba60  test    r12d, r12d
0x14016ba63  jz      loc_14016BAEB
0x14016ba69  or      dword ptr [rdi+28h], 2
0x14016ba6d  mov     eax, [rsp+1F0h+var_1C8]
0x14016ba71  shl     eax, 2
0x14016ba74  mov     ecx, eax
0x14016ba76  mov     [rdi+10h], r13
0x14016ba7a  xor     ecx, [rdi+28h]
0x14016ba7d  and     ecx, 0FFFFFFFBh
0x14016ba80  mov     dword ptr [rdi+24h], 1
0x14016ba87  xor     ecx, eax
0x14016ba89  mov     dword ptr [rdi+20h], 5
0x14016ba90  mov     [rdi+28h], ecx
0x14016ba93  mov     rcx, [rsp+1F0h+var_1B0]
0x14016ba98  mov     dword ptr [rdi+40h], 0FFFFFFFFh
0x14016ba9f  mov     rax, [rcx+718h]
0x14016baa6  test    rax, rax
0x14016baa9  jz      short loc_14016BAAF
0x14016baab  mov     [rax+8], rdi
0x14016baaf  mov     rdx, [rcx+718h]
0x14016bab6  mov     [rdi], rdx
0x14016bab9  mov     qword ptr [rdi+8], 0
0x14016bac1  mov     [rcx+718h], rdi
0x14016bac8  mov     rdx, rdi
0x14016bacb  mov     ecx, 5
0x14016bad0  call    cs:__imp_WdLogSingleEntry1
0x14016bad7  nop     dword ptr [rax+rax+00h]
0x14016badc  mov     rax, rdi
0x14016badf  mov     cs:WdLogGlobalForLineNumber, 48Fh
0x14016bae9  jmp     short loc_14016BB48
0x14016baeb  cmp     esi, 0C000007Ah
0x14016baf1  jnz     short loc_14016BAFD
0x14016baf3  mov     ecx, 3
0x14016baf8  call    ?DrvLogDisplayDriverEvent@@YAXW4_DISP_DRIVER_LOG@@@Z; DrvLogDisplayDriverEvent(_DISP_DRIVER_LOG)
0x14016bafd  mov     rcx, r13; Buffer
0x14016bb00  call    GreDeleteFastMutex
0x14016bb05  test    rdi, rdi
0x14016bb08  jz      short loc_14016BB12
0x14016bb0a  mov     rcx, rdi; Buffer
0x14016bb0d  call    GreDeleteFastMutex
0x14016bb12  xor     ebx, ebx
0x14016bb14  jmp     short loc_14016BB1D
0x14016bb16  mov     dword ptr [r15], 1
  ... truncated ...
```
