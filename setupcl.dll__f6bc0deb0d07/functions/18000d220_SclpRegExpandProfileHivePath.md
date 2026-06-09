# SclpRegExpandProfileHivePath

- ea: `0x18000d220`
- end: `0x18000d61a`
- name: `SclpRegExpandProfileHivePath`
- size: `1018`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const wchar_t *, __int64, __int64, PWSTR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000bc68`

## callees

- `0x180007944`
- `0x180007ac4`
- `0x18000a524`
- `0x18000d220`
- `0x1800126d8`
- `0x1800151f0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000d2f5`
- `ntdll!RtlAllocateHeap` at `0x18000d2f5`
- `ntdll!RtlInitUnicodeString` at `0x18000d266`
- `ntdll!RtlInitUnicodeString` at `0x18000d57b`
- `ntdll!RtlInitUnicodeString` at `0x18000d266`
- `ntdll!RtlInitUnicodeString` at `0x18000d57b`
- `ntdll!RtlFreeHeap` at `0x18000d526`
- `ntdll!RtlFreeHeap` at `0x18000d56d`
- `ntdll!RtlFreeHeap` at `0x18000d5e5`
- `ntdll!RtlFreeHeap` at `0x18000d526`
- `ntdll!RtlFreeHeap` at `0x18000d56d`
- `ntdll!RtlFreeHeap` at `0x18000d5e5`
- `ntdll!_wcsnicmp` at `0x18000d39c`
- `ntdll!_wcsnicmp` at `0x18000d39c`
- `ntdll!RtlDestroyEnvironment` at `0x18000d5f7`
- `ntdll!RtlDestroyEnvironment` at `0x18000d5f7`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x18000d31c`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x18000d31c`

## string_xrefs

- `0x18000d284`: `SclpRegExpandProfileHivePath`
- `0x18000d34a`: `SclpRegExpandProfileHivePath`
- `0x18000d5ac`: `SclpRegExpandProfileHivePath`
- `0x18000d5a0`: `Expanded profile hive path: NT path = [%ws]`

## pseudocode

```c
__int64 __fastcall SclpRegExpandProfileHivePath(
        __int64 a1,
        const WCHAR *a2,
        const wchar_t *a3,
        __int64 a4,
        __int64 a5,
        PWSTR *a6)
{
  WCHAR *v7; // rsi
  __int64 v11; // r15
  int v12; // eax
  signed int v13; // ebx
  NTSTATUS v14; // eax
  char v15; // al
  __int64 v16; // r14
  unsigned __int64 v17; // r13
  __int64 v18; // r15
  WCHAR *v19; // rbx
  wchar_t *v20; // r12
  signed int LastErrorValue; // edx
  struct _TEB *v22; // rcx
  char v23; // di
  unsigned __int64 v24; // rcx
  PWSTR Buffer; // rax
  unsigned __int64 v27; // [rsp+50h] [rbp-30h] BYREF
  __int64 v28; // [rsp+58h] [rbp-28h]
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-10h] BYREF
  PCWSTR SourceString; // [rsp+C0h] [rbp+40h] BYREF
  PWSTR Environment; // [rsp+D0h] [rbp+50h] BYREF
  WCHAR *v33; // [rsp+D8h] [rbp+58h]

  LOBYTE(SourceString) = 0;
  Environment = 0;
  v7 = 0;
  DestinationString = 0;
  Destination = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  v11 = a1 + 1152;
  if ( !a1 )
    v11 = 0;
  v28 = v11;
  SclLogGenericMessage(
    v11,
    1,
    (int)SclEvent_Generic_Info,
    1909,
    (__int64)"SclpRegExpandProfileHivePath",
    "Locating user profile hive: %ws",
    a2);
  if ( !a3 || (v12 = SclCreateFakeNtPathEnvironment(a3, a4, &Environment), v7 = Environment, v13 = v12, v12 >= 0) )
  {
    *(_DWORD *)&Destination.Length = 102236160;
    Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x61Au);
    if ( !Destination.Buffer )
    {
      v13 = -1073741801;
      goto LABEL_52;
    }
    v14 = RtlExpandEnvironmentStrings_U(v7, &DestinationString, &Destination, 0);
    v13 = v14;
    if ( v14 < 0 )
    {
      SclLogGenericMessage(
        v11,
        3,
        (int)SclEvent_Generic_Error,
        1959,
        (__int64)"SclpRegExpandProfileHivePath",
        "(%lx): Failed to expand environment string!",
        v14);
      goto LABEL_52;
    }
    if ( !*Destination.Buffer )
    {
      v13 = -1073741811;
      goto LABEL_52;
    }
    Destination.Buffer[(unsigned __int64)Destination.Length >> 1] = 0;
    if ( DestinationString.Length != Destination.Length
      || _wcsnicmp(DestinationString.Buffer, Destination.Buffer, DestinationString.Length) )
    {
      v15 = 1;
      if ( v7 )
        goto LABEL_51;
    }
    else
    {
      v15 = 0;
    }
    if ( !v15 && a3 )
    {
      v16 = a5;
      v17 = -1;
      if ( a5 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)(a5 + 2 * v18) );
LABEL_24:
        v19 = (WCHAR *)((unsigned __int64)Destination.Length >> 1);
        v33 = v19;
        Environment = v19;
        v27 = (unsigned __int64)Destination.MaximumLength >> 1;
        v20 = BuildPath(a3, &pszSrc);
        if ( !v20 )
        {
          LastErrorValue = NtCurrentTeb()->LastErrorValue;
          v22 = NtCurrentTeb();
          if ( !LastErrorValue )
            LastErrorValue = 31;
          v13 = v22->LastErrorValue;
          if ( LastErrorValue > 0 )
          {
            if ( !v13 )
              LOWORD(v13) = 31;
            v13 = (unsigned __int16)v13 | 0xC0070000;
          }
          else if ( !v13 )
          {
            v13 = 31;
          }
          v23 = 0;
          if ( v13 < 0 )
          {
LABEL_47:
            if ( v13 < 0 )
              goto LABEL_52;
            if ( !v23 )
              goto LABEL_49;
LABEL_51:
            SclLogGenericMessage(
              v28,
              1,
              (int)SclEvent_Generic_Info,
              2116,
              (__int64)"SclpRegExpandProfileHivePath",
              "Expanded profile hive path: NT path = [%ws]",
              Destination.Buffer);
            Buffer = Destination.Buffer;
            Destination.Buffer = 0;
            *a6 = Buffer;
            goto LABEL_52;
          }
          v19 = v33;
        }
        do
          ++v17;
        while ( v20[v17] );
        v13 = SclFindAndReplaceChars(
                (char *)Destination.Buffer,
                (unsigned __int64)v19,
                (unsigned __int64 *)&Environment,
                &v27,
                v16,
                v18,
                v20,
                v17,
                (bool *)&SourceString);
        v23 = 0;
        if ( v13 >= 0 )
        {
          v24 = 2LL * (_QWORD)Environment;
          if ( is_mul_ok((unsigned __int64)Environment, 2u) )
          {
            Destination.Length = 2 * (_WORD)Environment;
            if ( (unsigned __int64)(2LL * (_QWORD)Environment) > 0xFFFF )
              Destination.Length = -1;
            v23 = 0;
            v13 = v24 > 0xFFFF ? 0xC0000095 : 0;
            if ( v24 <= 0xFFFF )
              v23 = (char)SourceString;
          }
          else
          {
            v13 = -1073741675;
          }
        }
        if ( v20 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
        goto LABEL_47;
      }
      if ( (*(_DWORD *)(a1 + 8) & 2) != 0 )
      {
        v16 = a1 + 552;
        if ( a1 != -552 )
        {
          v18 = *(unsigned int *)(a1 + 2388);
          goto LABEL_24;
        }
      }
    }
LABEL_49:
    SourceString = 0;
    v13 = SclDosPathToNtPath((__int64)Destination.Buffer, &SourceString);
    if ( v13 < 0 )
      goto LABEL_52;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
    RtlInitUnicodeString(&Destination, SourceString);
    goto LABEL_51;
  }
LABEL_52:
  if ( Destination.Buffer )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
    Destination.Buffer = 0;
  }
  if ( v7 )
    RtlDestroyEnvironment(v7);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000d220  mov     [rsp-38h+arg_8], rbx
0x18000d225  push    rbp
0x18000d226  push    rsi
0x18000d227  push    rdi
0x18000d228  push    r12
0x18000d22a  push    r13
0x18000d22c  push    r14
0x18000d22e  push    r15
0x18000d230  mov     rbp, rsp
0x18000d233  sub     rsp, 80h
0x18000d23a  xor     r13d, r13d
0x18000d23d  mov     rdi, rcx
0x18000d240  xorps   xmm0, xmm0
0x18000d243  mov     byte ptr [rbp+SourceString], r13b
0x18000d247  xorps   xmm1, xmm1
0x18000d24a  mov     [rbp+Environment], r13
0x18000d24e  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000d252  mov     esi, r13d
0x18000d255  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000d259  mov     r14, r9
0x18000d25c  mov     r12, r8
0x18000d25f  movups  xmmword ptr [rbp+Destination.Length], xmm1
0x18000d263  mov     rbx, rdx
0x18000d266  call    cs:__imp_RtlInitUnicodeString
0x18000d26c  lea     rax, aLocatingUserPr; "Locating user profile hive: %ws"
0x18000d273  mov     [rsp+80h+var_50], rbx
0x18000d278  mov     [rsp+80h+var_58], rax
0x18000d27d  lea     r15, [rdi+480h]
0x18000d284  lea     rax, aSclpregexpandp; "SclpRegExpandProfileHivePath"
0x18000d28b  test    rdi, rdi
0x18000d28e  mov     r9d, 775h
0x18000d294  mov     [rsp+80h+var_60], rax
0x18000d299  cmovz   r15, r13
0x18000d29d  lea     r8, SclEvent_Generic_Info
0x18000d2a4  mov     rcx, r15
0x18000d2a7  mov     [rbp+var_28], r15
0x18000d2ab  lea     edx, [r13+1]
0x18000d2af  call    SclLogGenericMessage
0x18000d2b4  test    r12, r12
0x18000d2b7  jz      short loc_18000D2D6
0x18000d2b9  lea     r8, [rbp+Environment]
0x18000d2bd  mov     rdx, r14
0x18000d2c0  mov     rcx, r12
0x18000d2c3  call    SclCreateFakeNtPathEnvironment
0x18000d2c8  mov     rsi, [rbp+Environment]
0x18000d2cc  mov     ebx, eax
0x18000d2ce  test    eax, eax
0x18000d2d0  js      loc_18000D5CC
0x18000d2d6  mov     dword ptr [rbp+Destination.Length], 6180000h
0x18000d2dd  mov     edx, 8; Flags
0x18000d2e2  mov     rcx, gs:60h
0x18000d2eb  mov     r8d, 61Ah; Size
0x18000d2f1  mov     rcx, [rcx+30h]; HeapHandle
0x18000d2f5  call    cs:__imp_RtlAllocateHeap
0x18000d2fb  mov     [rbp+Destination.Buffer], rax
0x18000d2ff  test    rax, rax
0x18000d302  jnz     short loc_18000D30E
0x18000d304  mov     ebx, 0C0000017h
0x18000d309  jmp     loc_18000D5CC
0x18000d30e  xor     r9d, r9d; Length
0x18000d311  lea     r8, [rbp+Destination]; Destination
0x18000d315  lea     rdx, [rbp+DestinationString]; Source
0x18000d319  mov     rcx, rsi; Environment
0x18000d31c  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x18000d322  mov     ebx, eax
0x18000d324  test    eax, eax
0x18000d326  jns     short loc_18000D363
0x18000d328  mov     dword ptr [rsp+80h+var_50], eax
0x18000d32c  lea     r8, SclEvent_Generic_Error
0x18000d333  lea     rax, aLxFailedToExpa; "(%lx): Failed to expand environment str"...
0x18000d33a  mov     r9d, 7A7h
0x18000d340  mov     [rsp+80h+var_58], rax
0x18000d345  mov     edx, 3
0x18000d34a  lea     rax, aSclpregexpandp; "SclpRegExpandProfileHivePath"
0x18000d351  mov     rcx, r15
0x18000d354  mov     [rsp+80h+var_60], rax
0x18000d359  call    SclLogGenericMessage
0x18000d35e  jmp     loc_18000D5CC
0x18000d363  mov     rax, [rbp+Destination.Buffer]
0x18000d367  cmp     r13w, [rax]
0x18000d36b  jnz     short loc_18000D377
0x18000d36d  mov     ebx, 0C000000Dh
0x18000d372  jmp     loc_18000D5CC
0x18000d377  movzx   edx, [rbp+Destination.Length]
0x18000d37b  mov     rax, [rbp+Destination.Buffer]
0x18000d37f  shr     rdx, 1
0x18000d382  mov     [rax+rdx*2], r13w
0x18000d387  movzx   eax, [rbp+DestinationString.Length]
0x18000d38b  cmp     ax, [rbp+Destination.Length]
0x18000d38f  jnz     short loc_18000D3AB
0x18000d391  mov     rdx, [rbp+Destination.Buffer]; String2
0x18000d395  mov     r8d, eax; MaxCount
0x18000d398  mov     rcx, [rbp+DestinationString.Buffer]; String1
0x18000d39c  call    cs:__imp__wcsnicmp
0x18000d3a2  test    eax, eax
0x18000d3a4  jnz     short loc_18000D3AB
0x18000d3a6  mov     al, r13b
0x18000d3a9  jmp     short loc_18000D3B6
0x18000d3ab  mov     al, 1
0x18000d3ad  test    rsi, rsi
0x18000d3b0  jnz     loc_18000D581
0x18000d3b6  test    al, al
0x18000d3b8  jnz     loc_18000D543
0x18000d3be  test    r12, r12
0x18000d3c1  jz      loc_18000D543
0x18000d3c7  mov     r14, [rbp+arg_20]
0x18000d3cb  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000d3cf  xor     ecx, ecx
0x18000d3d1  test    r14, r14
0x18000d3d4  jz      short loc_18000D3E5
0x18000d3d6  mov     r15, r13
0x18000d3d9  inc     r15
0x18000d3dc  cmp     [r14+r15*2], cx
0x18000d3e1  jnz     short loc_18000D3D9
0x18000d3e3  jmp     short loc_18000D407
0x18000d3e5  mov     eax, [rdi+8]
0x18000d3e8  test    al, 2
0x18000d3ea  jz      loc_18000D540
0x18000d3f0  lea     r14, [rdi+228h]
0x18000d3f7  test    r14, r14
0x18000d3fa  jz      loc_18000D540
0x18000d400  mov     r15d, [rdi+954h]
0x18000d407  movzx   ebx, [rbp+Destination.Length]
0x18000d40b  lea     rdx, pszSrc; STRSAFE_PCNZWCH
0x18000d412  movzx   eax, [rbp+Destination.MaximumLength]
0x18000d416  mov     rcx, r12; pszSrc
0x18000d419  shr     rbx, 1
0x18000d41c  shr     rax, 1
0x18000d41f  mov     [rbp+arg_18], rbx
0x18000d423  mov     [rbp+Environment], rbx
0x18000d427  mov     [rbp+var_30], rax
0x18000d42b  call    BuildPath
0x18000d430  mov     r12, rax
0x18000d433  xor     eax, eax
0x18000d435  test    r12, r12
0x18000d438  jnz     short loc_18000D486
0x18000d43a  mov     rcx, gs:30h
0x18000d443  lea     r8d, [rax+1Fh]
0x18000d447  mov     edx, [rcx+68h]
0x18000d44a  test    edx, edx
0x18000d44c  mov     rcx, gs:30h
0x18000d455  cmovz   edx, r8d
0x18000d459  mov     ebx, [rcx+68h]
0x18000d45c  test    edx, edx
0x18000d45e  jg      short loc_18000D468
0x18000d460  test    ebx, ebx
0x18000d462  cmovz   ebx, r8d
0x18000d466  jmp     short loc_18000D477
0x18000d468  test    ebx, ebx
0x18000d46a  cmovz   ebx, r8d
0x18000d46e  movzx   ebx, bx
0x18000d471  or      ebx, 0C0070000h
0x18000d477  mov     dil, al
0x18000d47a  test    ebx, ebx
0x18000d47c  js      loc_18000D52E
0x18000d482  mov     rbx, [rbp+arg_18]
0x18000d486  inc     r13
0x18000d489  cmp     [r12+r13*2], ax
0x18000d48e  jnz     short loc_18000D486
0x18000d490  mov     rcx, [rbp+Destination.Buffer]; Src
0x18000d494  lea     rax, [rbp+SourceString]
0x18000d498  mov     [rsp+80h+var_40], rax; __int64
0x18000d49d  lea     r9, [rbp+var_30]
0x18000d4a1  mov     [rsp+80h+var_48], r13; __int64
0x18000d4a6  lea     r8, [rbp+Environment]
0x18000d4aa  mov     [rsp+80h+var_50], r12; __int64
0x18000d4af  mov     rdx, rbx
0x18000d4b2  mov     [rsp+80h+var_58], r15; __int64
0x18000d4b7  mov     [rsp+80h+var_60], r14; __int64
0x18000d4bc  call    SclFindAndReplaceChars
0x18000d4c1  xor     r13d, r13d
0x18000d4c4  mov     ebx, eax
0x18000d4c6  mov     dil, r13b
0x18000d4c9  test    eax, eax
0x18000d4cb  js      short loc_18000D50F
0x18000d4cd  lea     eax, [r13+2]
0x18000d4d1  mul     [rbp+Environment]
0x18000d4d5  mov     rcx, rax
0x18000d4d8  test    rdx, rdx
0x18000d4db  jnz     short loc_18000D50A
0x18000d4dd  mov     edx, 0FFFFh
0x18000d4e2  mov     [rbp+Destination.Length], cx
0x18000d4e6  cmp     rax, rdx
0x18000d4e9  jbe     short loc_18000D4EF
0x18000d4eb  mov     [rbp+Destination.Length], dx
0x18000d4ef  movzx   eax, byte ptr [rbp+SourceString]
0x18000d4f3  cmp     rdx, rcx
0x18000d4f6  movzx   edi, r13b
0x18000d4fa  sbb     ebx, ebx
0x18000d4fc  and     ebx, 0C0000095h
0x18000d502  cmp     rcx, rdx
0x18000d505  cmovbe  edi, eax
0x18000d508  jmp     short loc_18000D50F
0x18000d50a  mov     ebx, 0C0000095h
0x18000d50f  test    r12, r12
0x18000d512  jz      short loc_18000D531
0x18000d514  mov     rcx, gs:60h
0x18000d51d  mov     r8, r12; P
0x18000d520  xor     edx, edx; Flags
0x18000d522  mov     rcx, [rcx+30h]; HeapHandle
0x18000d526  call    cs:__imp_RtlFreeHeap
0x18000d52c  jmp     short loc_18000D531
0x18000d52e  xor     r13d, r13d
0x18000d531  test    ebx, ebx
0x18000d533  js      loc_18000D5CC
0x18000d539  test    dil, dil
0x18000d53c  jnz     short loc_18000D581
0x18000d53e  jmp     short loc_18000D543
0x18000d540  xor     r13d, r13d
0x18000d543  mov     rcx, [rbp+Destination.Buffer]
0x18000d547  lea     rdx, [rbp+SourceString]
0x18000d54b  mov     [rbp+SourceString], r13
0x18000d54f  call    SclDosPathToNtPath
0x18000d554  mov     ebx, eax
0x18000d556  test    eax, eax
0x18000d558  js      short loc_18000D5CC
0x18000d55a  mov     rcx, gs:60h
0x18000d563  xor     edx, edx; Flags
0x18000d565  mov     r8, [rbp+Destination.Buffer]; P
0x18000d569  mov     rcx, [rcx+30h]; HeapHandle
0x18000d56d  call    cs:__imp_RtlFreeHeap
0x18000d573  mov     rdx, [rbp+SourceString]; SourceString
0x18000d577  lea     rcx, [rbp+Destination]; DestinationString
0x18000d57b  call    cs:__imp_RtlInitUnicodeString
0x18000d581  mov     rax, [rbp+Destination.Buffer]
0x18000d585  lea     r8, SclEvent_Generic_Info
0x18000d58c  mov     rcx, [rbp+var_28]
0x18000d590  mov     r9d, 844h
0x18000d596  mov     [rsp+80h+var_50], rax
0x18000d59b  mov     edx, 1
0x18000d5a0  lea     rax, aExpandedProfil; "Expanded profile hive path: NT path = ["...
0x18000d5a7  mov     [rsp+80h+var_58], rax
0x18000d5ac  lea     rax, aSclpregexpandp; "SclpRegExpandProfileHivePath"
0x18000d5b3  mov     [rsp+80h+var_60], rax
0x18000d5b8  call    SclLogGenericMessage
0x18000d5bd  mov     rax, [rbp+Destination.Buffer]
0x18000d5c1  mov     rcx, [rbp+arg_28]
0x18000d5c5  mov     [rbp+Destination.Buffer], r13
0x18000d5c9  mov     [rcx], rax
0x18000d5cc  cmp     [rbp+Destination.Buffer], r13
0x18000d5d0  jz      short loc_18000D5EF
0x18000d5d2  mov     rcx, gs:60h
0x18000d5db  xor     edx, edx; Flags
0x18000d5dd  mov     r8, [rbp+Destination.Buffer]; P
0x18000d5e1  mov     rcx, [rcx+30h]; HeapHandle
0x18000d5e5  call    cs:__imp_RtlFreeHeap
0x18000d5eb  mov     [rbp+Destination.Buffer], r13
0x18000d5ef  test    rsi, rsi
0x18000d5f2  jz      short loc_18000D5FD
0x18000d5f4  mov     rcx, rsi; Environment
0x18000d5f7  call    cs:__imp_RtlDestroyEnvironment
0x18000d5fd  mov     eax, ebx
0x18000d5ff  mov     rbx, [rsp+80h+arg_8]
0x18000d607  add     rsp, 80h
0x18000d60e  pop     r15
0x18000d610  pop     r14
0x18000d612  pop     r13
0x18000d614  pop     r12
0x18000d616  pop     rdi
0x18000d617  pop     rsi
0x18000d618  pop     rbp
0x18000d619  retn
```
