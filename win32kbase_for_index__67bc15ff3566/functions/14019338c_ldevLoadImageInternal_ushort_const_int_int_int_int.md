# ldevLoadImageInternal(ushort const *,int,int *,int,int)

- ea: `0x14019338c`
- end: `0x1401938bc`
- name: `?ldevLoadImageInternal@@YAPEAU_LDEV@@PEBGHPEAHHH@Z`
- size: `1328`
- prototype: `struct _LDEV *__usercall@<rax>(PCWSTR Source@<rcx>, int@<edx>, int *@<r8>, int@<r9d>, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x14019d1c0`

## callees

- `0x14000d76c`
- `0x14000f420`
- `0x14007ab04`
- `0x14007b930`
- `0x14017abbc`
- `0x14019338c`
- `0x140196660`
- `0x1401b32d4`
- `0x1401b7634`
- `0x1401c5428`
- `0x1401c5548`
- `0x1402388e0`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!ZwSetSystemInformation` at `0x140193541`
- `ntoskrnl!ZwSetSystemInformation` at `0x140193541`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140193651`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1401936a6`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140193651`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1401936a6`
- `ntoskrnl!RtlImageNtHeader` at `0x140193770`
- `ntoskrnl!RtlImageNtHeader` at `0x140193770`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140193623`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140193623`
- `ntoskrnl!RtlFreeAnsiString` at `0x1401937a4`
- `ntoskrnl!RtlFreeAnsiString` at `0x1401937a4`
- `ntoskrnl!RtlImageDirectoryEntryToData` at `0x140193715`
- `ntoskrnl!RtlImageDirectoryEntryToData` at `0x140193715`
- `ntoskrnl!RtlInitUnicodeString` at `0x14019360a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14019360a`
- `watchdog!WdLogSingleEntry3` at `0x1401933ea`
- `watchdog!WdLogSingleEntry3` at `0x1401933ea`
- `watchdog!WdLogSingleEntry1` at `0x140193820`
- `watchdog!WdLogSingleEntry1` at `0x14019387f`
- `watchdog!WdLogSingleEntry1` at `0x140193820`
- `watchdog!WdLogSingleEntry1` at `0x14019387f`
- `WIN32K!W32GetSessionState` at `0x14019342c`
- `WIN32K!W32GetSessionState` at `0x14019342c`

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
0x14019338c  push    rbp
0x14019338e  push    rbx
0x14019338f  push    rsi
0x140193390  push    rdi
0x140193391  push    r12
0x140193393  push    r13
0x140193395  push    r14
0x140193397  push    r15
0x140193399  lea     rbp, [rsp-0B8h]
0x1401933a1  sub     rsp, 1B8h
0x1401933a8  mov     rax, cs:__security_cookie
0x1401933af  xor     rax, rsp
0x1401933b2  mov     [rbp+0F0h+var_50], rax
0x1401933b9  mov     eax, [rbp+0F0h+arg_20]
0x1401933bf  xorps   xmm0, xmm0
0x1401933c2  movsxd  r13, r9d
0x1401933c5  mov     r15, r8
0x1401933c8  mov     [rsp+1F0h+Size], r13d
0x1401933cd  mov     r14, rcx
0x1401933d0  movups  xmmword ptr [rsp+1F0h+String2.Length], xmm0
0x1401933d5  movsxd  r12, edx
0x1401933d8  xor     ebx, ebx
0x1401933da  mov     [rsp+1F0h+var_1C8], eax
0x1401933de  mov     rdx, rcx
0x1401933e1  mov     r9, r13
0x1401933e4  lea     ecx, [rbx+4]
0x1401933e7  mov     r8, r12
0x1401933ea  call    cs:__imp_WdLogSingleEntry3
0x1401933f1  nop     dword ptr [rax+rax+00h]
0x1401933f6  xor     eax, eax
0x1401933f8  mov     cs:WdLogGlobalForLineNumber, 3E7h
0x140193402  test    r12d, r12d
0x140193405  mov     [r15], ebx
0x140193408  lea     rdx, [rsp+1F0h+String2]; Destination
0x14019340d  mov     rcx, r14; Source
0x140193410  setz    al
0x140193413  mov     r8d, eax
0x140193416  mov     [rsp+1F0h+ReturnLength], eax
0x14019341a  call    MakeSystemRelativePath
0x14019341f  test    eax, eax
0x140193421  jz      loc_140193877
0x140193427  xor     edi, edi
0x140193429  lea     esi, [rbx+1]
0x14019342c  call    cs:__imp_W32GetSessionState
0x140193433  nop     dword ptr [rax+rax+00h]
0x140193438  mov     r8d, [rsp+1F0h+var_1C8]
0x14019343d  lea     rcx, [rsp+1F0h+String2]; String2
0x140193442  mov     edx, r12d
0x140193445  mov     rax, [rax+58h]
0x140193449  mov     [rsp+1F0h+var_1B0], rax
0x14019344e  call    ldevTryReferenceLoadedDisplayDriver
0x140193453  mov     rbx, rax
0x140193456  test    rax, rax
0x140193459  jnz     loc_140193866
0x14019345f  test    r13d, r13d
0x140193462  jnz     short loc_1401934BB
0x140193464  test    esi, esi
0x140193466  jz      short loc_14019348F
0x140193468  lea     rcx, [rsp+1F0h+String2]
0x14019346d  call    FreeSystemRelativePath
0x140193472  mov     r8d, [rsp+1F0h+ReturnLength]
0x140193477  lea     rdx, [rsp+1F0h+String2]; Destination
0x14019347c  mov     rcx, r14; Source
0x14019347f  call    MakeSystemDriversRelativePath
0x140193484  test    eax, eax
0x140193486  jz      short loc_1401934BB
0x140193488  xor     esi, esi
0x14019348a  lea     edi, [rbx+1]
0x14019348d  jmp     short loc_14019342C
0x14019348f  test    edi, edi
0x140193491  jz      short loc_1401934BB
0x140193493  lea     rcx, [rsp+1F0h+String2]
0x140193498  call    FreeSystemRelativePath
0x14019349d  mov     r12d, [rsp+1F0h+ReturnLength]
0x1401934a2  lea     rdx, [rsp+1F0h+String2]; Destination
0x1401934a7  mov     r8d, r12d
0x1401934aa  mov     rcx, r14; Source
0x1401934ad  call    MakeSystemRelativePath
0x1401934b2  test    eax, eax
0x1401934b4  jnz     short loc_1401934C0
0x1401934b6  jmp     loc_14019386D
0x1401934bb  mov     r12d, [rsp+1F0h+ReturnLength]
0x1401934c0  mov     ebx, 76646C47h
0x1401934c5  mov     ecx, 30h ; '0'
0x1401934ca  mov     edx, ebx
0x1401934cc  call    PALLOCMEM
0x1401934d1  mov     edx, ebx
0x1401934d3  mov     ecx, 390h
0x1401934d8  mov     r13, rax
0x1401934db  call    PALLOCMEM
0x1401934e0  mov     rdi, rax
0x1401934e3  test    r13, r13
0x1401934e6  jz      loc_140193855
0x1401934ec  test    rax, rax
0x1401934ef  jz      loc_14019384D
0x1401934f5  mov     r15d, [rsp+1F0h+Size]
0x1401934fa  lea     rcx, [rax+48h]
0x1401934fe  mov     [rax+388h], rcx
0x140193505  mov     ebx, 1
0x14019350a  mov     dword ptr [rax+44h], 0
0x140193511  mov     rax, [rsp+1F0h+var_1B0]
0x140193516  mov     r8d, 30h ; '0'; SystemInformationLength
0x14019351c  mov     rdx, r13; SystemInformation
0x14019351f  movups  xmm0, xmmword ptr [rsp+1F0h+String2.Length]
0x140193524  lea     ecx, [r8-16h]
0x140193528  movdqu  xmmword ptr [r13+0], xmm0
0x14019352e  mov     dword ptr [rax+478h], 0
0x140193538  test    r15d, r15d
0x14019353b  jnz     short loc_140193541
0x14019353d  lea     ecx, [r8+6]; SystemInformationClass
0x140193541  call    cs:__imp_ZwSetSystemInformation
0x140193548  nop     dword ptr [rax+rax+00h]
0x14019354d  mov     esi, eax
0x14019354f  test    eax, eax
0x140193551  jns     loc_1401937BD
0x140193557  cmp     eax, 0C000010Eh
0x14019355c  jz      short loc_14019356D
0x14019355e  mov     rax, [rsp+1F0h+var_1B0]
0x140193563  mov     dword ptr [rax+478h], 3
0x14019356d  test    r15d, r15d
0x140193570  jnz     loc_14019383B
0x140193576  cmp     esi, 0C0000034h
0x14019357c  jnz     short loc_1401935AF
0x14019357e  test    ebx, ebx
0x140193580  jz      loc_14019384D
0x140193586  lea     rcx, [rsp+1F0h+String2]
0x14019358b  call    FreeSystemRelativePath
0x140193590  mov     r8d, r12d
0x140193593  lea     rdx, [rsp+1F0h+String2]; Destination
0x140193598  mov     rcx, r14; Source
0x14019359b  call    MakeSystemDriversRelativePath
0x1401935a0  test    eax, eax
0x1401935a2  jz      loc_14019384D
0x1401935a8  xor     ebx, ebx
0x1401935aa  jmp     loc_140193511
0x1401935af  cmp     esi, 0C000010Eh
0x1401935b5  jnz     loc_14019383B
0x1401935bb  mov     ebx, 130h
0x1401935c0  lea     rcx, [rsp+1F0h+SystemInformation]; void *
0x1401935c5  mov     r8d, ebx; Size
0x1401935c8  xor     edx, edx; Val
0x1401935ca  call    memset
0x1401935cf  xorps   xmm0, xmm0
0x1401935d2  mov     [rsp+1F0h+ReturnLength], 0
0x1401935da  xorps   xmm1, xmm1
0x1401935dd  mov     edx, 5Ch ; '\'; Ch
0x1401935e2  mov     rcx, r14; Str
0x1401935e5  movups  xmmword ptr [rsp+1F0h+AnsiString.Length], xmm0
0x1401935ea  movups  xmmword ptr [rsp+1F0h+DestinationString.Length], xmm1
0x1401935ef  call    wcsrchr
0x1401935f4  test    rax, rax
0x1401935f7  jz      short loc_1401935FF
0x1401935f9  add     rax, 2
0x1401935fd  jmp     short loc_140193602
0x1401935ff  mov     rax, r14
0x140193602  mov     rdx, rax; SourceString
0x140193605  lea     rcx, [rsp+1F0h+DestinationString]; DestinationString
0x14019360a  call    cs:__imp_RtlInitUnicodeString
0x140193611  nop     dword ptr [rax+rax+00h]
0x140193616  mov     r8b, 1; AllocateDestinationString
0x140193619  lea     rdx, [rsp+1F0h+DestinationString]; SourceString
0x14019361e  lea     rcx, [rsp+1F0h+AnsiString]; DestinationString
0x140193623  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14019362a  nop     dword ptr [rax+rax+00h]
0x14019362f  mov     esi, eax
0x140193631  test    eax, eax
0x140193633  js      loc_14019383B
0x140193639  xor     r12d, r12d
0x14019363c  lea     r9, [rsp+1F0h+ReturnLength]; ReturnLength
0x140193641  mov     r8d, ebx; SystemInformationLength
0x140193644  lea     rdx, [rsp+1F0h+SystemInformation]; SystemInformation
0x140193649  lea     r15d, [r12+0Bh]
0x14019364e  mov     ecx, r15d; SystemInformationClass
0x140193651  call    cs:__imp_ZwQuerySystemInformation
0x140193658  nop     dword ptr [rax+rax+00h]
0x14019365d  mov     ecx, 80000000h
0x140193662  mov     esi, eax
0x140193664  add     eax, ecx
0x140193666  test    ecx, eax
0x140193668  jnz     short loc_140193676
0x14019366a  cmp     esi, 0C0000004h
0x140193670  jnz     loc_14019379F
0x140193676  imul    ebx, [rsp+1F0h+SystemInformation], 128h
0x14019367e  mov     edx, 706D7447h
0x140193683  lea     ecx, [rbx+8]
0x140193686  call    PALLOCNOZ
0x14019368b  mov     r14, rax
0x14019368e  test    rax, rax
0x140193691  jz      loc_140193792
0x140193697  lea     r9, [rsp+1F0h+ReturnLength]; ReturnLength
0x14019369c  mov     rdx, rax; SystemInformation
0x14019369f  lea     r8d, [rbx+8]; SystemInformationLength
0x1401936a3  mov     ecx, r15d; SystemInformationClass
0x1401936a6  call    cs:__imp_ZwQuerySystemInformation
0x1401936ad  nop     dword ptr [rax+rax+00h]
0x1401936b2  mov     esi, eax
0x1401936b4  test    eax, eax
0x1401936b6  js      loc_140193797
0x1401936bc  xor     r15d, r15d
0x1401936bf  cmp     r15d, [r14]
0x1401936c2  jnb     loc_140193797
0x1401936c8  movzx   r8d, [rsp+1F0h+AnsiString.Length]; MaxCount
0x1401936ce  mov     rdx, [rsp+1F0h+AnsiString.Buffer]; Str2
0x1401936d3  mov     eax, r15d
0x1401936d6  imul    rcx, rax, 128h
0x1401936dd  movzx   eax, word ptr [rcx+r14+2Eh]
0x1401936e3  add     rax, 30h ; '0'
0x1401936e7  add     rcx, rax
0x1401936ea  add     rcx, r14; Str1
0x1401936ed  call    _strnicmp
0x1401936f2  test    eax, eax
0x1401936f4  jz      short loc_1401936FB
0x1401936f6  inc     r15d
0x1401936f9  jmp     short loc_1401936BF
0x1401936fb  mov     rcx, cs:?gpvWin32kImageBase@@3PEAXEA; BaseAddress
0x140193702  lea     r9, [rsp+1F0h+Size]; Size
0x140193707  mov     r8d, 1; Directory
0x14019370d  mov     [rsp+1F0h+Size], r12d
0x140193712  mov     dl, r8b; MappedAsImage
0x140193715  call    cs:__imp_RtlImageDirectoryEntryToData
0x14019371c  nop     dword ptr [rax+rax+00h]
0x140193721  mov     rbx, rax
0x140193724  test    rbx, rbx
0x140193727  jz      short loc_140193792
0x140193729  mov     eax, [rbx+0Ch]
0x14019372c  test    eax, eax
0x14019372e  jz      short loc_140193792
0x140193730  cmp     [rbx], r12d
0x140193733  jz      short loc_140193792
0x140193735  movzx   r8d, [rsp+1F0h+AnsiString.Length]; MaxCount
0x14019373b  mov     ecx, eax
0x14019373d  add     rcx, cs:?gpvWin32kImageBase@@3PEAXEA; Str1
0x140193744  mov     rdx, [rsp+1F0h+AnsiString.Buffer]; Str2
0x140193749  call    _strnicmp
0x14019374e  test    eax, eax
0x140193750  jz      short loc_140193758
0x140193752  add     rbx, 14h
0x140193756  jmp     short loc_140193724
0x140193758  mov     eax, r15d
0x14019375b  mov     r12d, 1
0x140193761  imul    rcx, rax, 128h
0x140193768  mov     rbx, [rcx+r14+18h]
0x14019376d  mov     rcx, rbx; BaseAddress
0x140193770  call    cs:__imp_RtlImageNtHeader
0x140193777  nop     dword ptr [rax+rax+00h]
0x14019377c  mov     eax, [rax+28h]
0x14019377f  add     rax, rbx
0x140193782  mov     [r13+10h], rbx
0x140193786  mov     [r13+20h], rax
0x14019378a  mov     qword ptr [r13+18h], 0
0x140193792  test    r14, r14
0x140193795  jz      short loc_14019379F
0x140193797  mov     rcx, r14; Buffer
0x14019379a  call    GreDeleteFastMutex
0x14019379f  lea     rcx, [rsp+1F0h+AnsiString]; AnsiString
0x1401937a4  call    cs:__imp_RtlFreeAnsiString
0x1401937ab  nop     dword ptr [rax+rax+00h]
0x1401937b0  test    r12d, r12d
0x1401937b3  jz      loc_14019383B
0x1401937b9  or      dword ptr [rdi+28h], 2
0x1401937bd  mov     eax, [rsp+1F0h+var_1C8]
0x1401937c1  shl     eax, 2
0x1401937c4  mov     ecx, eax
0x1401937c6  mov     [rdi+10h], r13
0x1401937ca  xor     ecx, [rdi+28h]
0x1401937cd  and     ecx, 0FFFFFFFBh
0x1401937d0  mov     dword ptr [rdi+24h], 1
0x1401937d7  xor     ecx, eax
0x1401937d9  mov     dword ptr [rdi+20h], 5
0x1401937e0  mov     [rdi+28h], ecx
0x1401937e3  mov     rcx, [rsp+1F0h+var_1B0]
0x1401937e8  mov     dword ptr [rdi+40h], 0FFFFFFFFh
0x1401937ef  mov     rax, [rcx+718h]
0x1401937f6  test    rax, rax
0x1401937f9  jz      short loc_1401937FF
0x1401937fb  mov     [rax+8], rdi
0x1401937ff  mov     rdx, [rcx+718h]
0x140193806  mov     [rdi], rdx
0x140193809  mov     qword ptr [rdi+8], 0
0x140193811  mov     [rcx+718h], rdi
0x140193818  mov     rdx, rdi
0x14019381b  mov     ecx, 5
0x140193820  call    cs:__imp_WdLogSingleEntry1
0x140193827  nop     dword ptr [rax+rax+00h]
0x14019382c  mov     rax, rdi
0x14019382f  mov     cs:WdLogGlobalForLineNumber, 48Fh
0x140193839  jmp     short loc_140193898
0x14019383b  cmp     esi, 0C000007Ah
0x140193841  jnz     short loc_14019384D
0x140193843  mov     ecx, 3
0x140193848  call    ?DrvLogDisplayDriverEvent@@YAXW4_DISP_DRIVER_LOG@@@Z; DrvLogDisplayDriverEvent(_DISP_DRIVER_LOG)
0x14019384d  mov     rcx, r13; Buffer
0x140193850  call    GreDeleteFastMutex
0x140193855  test    rdi, rdi
0x140193858  jz      short loc_140193862
0x14019385a  mov     rcx, rdi; Buffer
0x14019385d  call    GreDeleteFastMutex
0x140193862  xor     ebx, ebx
0x140193864  jmp     short loc_14019386D
0x140193866  mov     dword ptr [r15], 1
  ... truncated ...
```
