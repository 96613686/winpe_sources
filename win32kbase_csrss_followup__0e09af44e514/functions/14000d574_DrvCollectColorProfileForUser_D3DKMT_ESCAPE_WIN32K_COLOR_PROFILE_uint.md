# DrvCollectColorProfileForUser(_D3DKMT_ESCAPE_WIN32K_COLOR_PROFILE *,uint)

- ea: `0x14000d574`
- end: `0x14000da1d`
- name: `?DrvCollectColorProfileForUser@@YAJPEAU_D3DKMT_ESCAPE_WIN32K_COLOR_PROFILE@@I@Z`
- size: `1193`
- prototype: `__int64 __fastcall(PSID Sid, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140162188`

## callees

- `0x14000d574`
- `0x14000da24`
- `0x14000dc4c`
- `0x14004a0d0`
- `0x140238800`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d6dc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d945`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d95d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d975`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d9e6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d9fe`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d6dc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d945`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d95d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d975`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d9e6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d9fe`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000d6cb`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000d6cb`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000d68b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000d6a1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000d6b6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000d68b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000d6a1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000d6b6`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d767`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d826`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d8a6`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d767`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d826`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d8a6`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000d5f5`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000d5f5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d61d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d63b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d61d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d63b`

## string_xrefs

- `0x14000d60c`: `\REGISTRY\USER\`

## pseudocode

```c
NTSTATUS __fastcall DrvCollectColorProfileForUser(char *Sid, int a2)
{
  _WORD *i; // rcx
  NTSTATUS result; // eax
  NTSTATUS v6; // edi
  int v7; // eax
  NTSTATUS v8; // esi
  int v9; // ecx
  char *v10; // rdi
  int v11; // ecx
  int v12; // eax
  int v13; // eax
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-D0h] BYREF
  void *Src[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v16; // [rsp+50h] [rbp-B0h] BYREF
  _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  UNICODE_STRING Source; // [rsp+80h] [rbp-80h] BYREF
  _RTL_QUERY_REGISTRY_TABLE QueryTable; // [rsp+90h] [rbp-70h] BYREF
  __int64 v21; // [rsp+C8h] [rbp-38h]
  int v22; // [rsp+D0h] [rbp-30h]
  __int64 v23; // [rsp+D8h] [rbp-28h]
  __int128 v24; // [rsp+E0h] [rbp-20h]
  __int128 v25; // [rsp+F0h] [rbp-10h]
  struct _RTL_QUERY_REGISTRY_TABLE v26; // [rsp+100h] [rbp+0h] BYREF
  __int64 v27; // [rsp+138h] [rbp+38h]
  int v28; // [rsp+140h] [rbp+40h]
  __int64 v29; // [rsp+148h] [rbp+48h]
  __int128 v30; // [rsp+150h] [rbp+50h]
  __int128 v31; // [rsp+160h] [rbp+60h]
  struct _RTL_QUERY_REGISTRY_TABLE v32; // [rsp+170h] [rbp+70h] BYREF
  __int64 v33; // [rsp+1A8h] [rbp+A8h]
  int v34; // [rsp+1B0h] [rbp+B0h]
  __int64 v35; // [rsp+1B8h] [rbp+B8h]
  __int128 v36; // [rsp+1C0h] [rbp+C0h]
  __int128 v37; // [rsp+1D0h] [rbp+D0h]
  int v38; // [rsp+210h] [rbp+110h] BYREF
  int v39; // [rsp+218h] [rbp+118h] BYREF

  if ( !(unsigned int)DxgkEngIsDwmProcess() && !gbOSTestSigningEnabled )
    return -1073741790;
  if ( *((_DWORD *)Sid + 23) + *((_DWORD *)Sid + 22) > (unsigned int)(a2 - 96) || *((_WORD *)Sid + 41) )
    return -1073741811;
  for ( i = Sid + 68; *i; ++i )
  {
    if ( (unsigned __int16)(*i - 48) > 9u )
      return -1073741811;
  }
  UnicodeString = 0;
  result = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
  if ( result >= 0 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"\\REGISTRY\\USER\\");
    Source = 0;
    RtlInitUnicodeString(
      &Source,
      L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\ICM\\ProfileAssociations\\Display\\{4d36e96e-e325-11ce-bfc1-08002be10318}\\");
    *(_QWORD *)&Destination.Length = 0;
    *(_DWORD *)&Destination.MaximumLength = (unsigned __int16)(DestinationString.Length
                                                             + Source.Length
                                                             + UnicodeString.Length
                                                             + 16);
    Destination.Buffer = (PWSTR)PALLOCNOZ(
                                  (unsigned __int16)(DestinationString.Length + Source.Length
                                                                              + UnicodeString.Length
                                                                              + 16),
                                  1936876615);
    if ( !Destination.Buffer )
    {
      RtlFreeUnicodeString(&UnicodeString);
      return -1073741801;
    }
    RtlAppendUnicodeStringToString(&Destination, &DestinationString);
    RtlAppendUnicodeStringToString(&Destination, &UnicodeString);
    RtlAppendUnicodeStringToString(&Destination, &Source);
    RtlAppendUnicodeToString(&Destination, (PCWSTR)Sid + 34);
    RtlFreeUnicodeString(&UnicodeString);
    QueryTable.Name = L"UsePerUserProfiles";
    v38 = 0;
    QueryTable.EntryContext = &v38;
    v39 = 0;
    QueryTable.DefaultData = &v39;
    QueryTable.QueryRoutine = 0;
    QueryTable.Flags = 288;
    *(_OWORD *)Src = 0;
    QueryTable.DefaultType = 67108868;
    v16 = 0;
    QueryTable.DefaultLength = 4;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v6 = RtlQueryRegistryValues(0, Destination.Buffer, &QueryTable, 0, 0);
    if ( v6 < 0 )
    {
      GreDeleteFastMutex(Destination.Buffer);
      return v6;
    }
    v7 = v38;
    *((_DWORD *)Sid + 21) = v38;
    if ( !v7 )
    {
      GreDeleteFastMutex(Destination.Buffer);
      if ( !*((_DWORD *)Sid + 22) )
        return *((_DWORD *)Sid + 23) != 0 ? 0xC000000D : 0;
      return -1073741811;
    }
    v26.Name = L"ICMProfile";
    v26.QueryRoutine = 0;
    v26.EntryContext = Src;
    v26.Flags = 304;
    v26.DefaultType = 117440519;
    v26.DefaultData = 0;
    v26.DefaultLength = 0;
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v6 = RtlQueryRegistryValues(0, Destination.Buffer, &v26, 0, 0);
    v32.QueryRoutine = 0;
    v32.Flags = 304;
    v32.DefaultType = 117440519;
    v32.Name = L"ICMProfileAC";
    v32.DefaultData = 0;
    v32.EntryContext = &v16;
    v32.DefaultLength = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v8 = RtlQueryRegistryValues(0, Destination.Buffer, &v32, 0, 0);
    GreDeleteFastMutex(Destination.Buffer);
    if ( v6 < 0 && v8 < 0 )
    {
      *((_DWORD *)Sid + 21) = 0;
      return v6;
    }
    v9 = *((_DWORD *)Sid + 22);
    v10 = Sid + 96;
    if ( v9 )
    {
      if ( v9 != (LOWORD(Src[0]) >> 1) + 1 )
        goto LABEL_41;
      memmove(Sid + 96, Src[1], LOWORD(Src[0]));
      v10 += 2 * *((unsigned int *)Sid + 22);
      *((_WORD *)v10 - 1) = 0;
    }
    else
    {
      if ( LOWORD(Src[0]) )
        v13 = (LOWORD(Src[0]) >> 1) + 1;
      else
        v13 = 0;
      *((_DWORD *)Sid + 22) = v13;
    }
    v11 = *((_DWORD *)Sid + 23);
    if ( !v11 )
    {
      if ( v16.Length )
        v12 = (v16.Length >> 1) + 1;
      else
        v12 = 0;
      *((_DWORD *)Sid + 23) = v12;
      goto LABEL_24;
    }
    if ( v11 == (v16.Length >> 1) + 1 )
    {
      memmove(v10, v16.Buffer, v16.Length);
      *(_WORD *)&v10[2 * *((unsigned int *)Sid + 23) - 2] = 0;
LABEL_24:
      if ( Src[1] )
        RtlFreeUnicodeString((PUNICODE_STRING)Src);
      if ( v16.Buffer )
        RtlFreeUnicodeString(&v16);
      return 0;
    }
LABEL_41:
    if ( Src[1] )
      RtlFreeUnicodeString((PUNICODE_STRING)Src);
    if ( v16.Buffer )
      RtlFreeUnicodeString(&v16);
    return -1073741811;
  }
  return result;
}

```

## disassembly

```asm
0x14000d574  mov     [rsp-8+arg_0], rbx
0x14000d579  mov     [rsp-8+arg_8], rsi
0x14000d57e  push    rbp
0x14000d57f  push    rdi
0x14000d580  push    r15
0x14000d582  lea     rbp, [rsp-0E0h]
0x14000d58a  sub     rsp, 1E0h
0x14000d591  mov     edi, edx
0x14000d593  mov     rbx, rcx
0x14000d596  call    DxgkEngIsDwmProcess
0x14000d59b  xor     r15d, r15d
0x14000d59e  test    eax, eax
0x14000d5a0  jz      loc_14000D9B2
0x14000d5a6  mov     ecx, [rbx+58h]
0x14000d5a9  lea     eax, [rdi-60h]
0x14000d5ac  add     ecx, [rbx+5Ch]
0x14000d5af  cmp     ecx, eax
0x14000d5b1  ja      loc_14000DA0A
0x14000d5b7  cmp     [rbx+52h], r15w
0x14000d5bc  jnz     loc_14000DA0A
0x14000d5c2  lea     rcx, [rbx+44h]
0x14000d5c6  movzx   eax, word ptr [rcx]
0x14000d5c9  test    ax, ax
0x14000d5cc  jz      short loc_14000D5E2
0x14000d5ce  sub     ax, 30h ; '0'
0x14000d5d2  cmp     ax, 9
0x14000d5d6  ja      loc_14000DA0A
0x14000d5dc  add     rcx, 2
0x14000d5e0  jmp     short loc_14000D5C6
0x14000d5e2  xorps   xmm0, xmm0
0x14000d5e5  lea     rcx, [rsp+1F0h+UnicodeString]; UnicodeString
0x14000d5ea  mov     r8b, 1; AllocateDestinationString
0x14000d5ed  mov     rdx, rbx; Sid
0x14000d5f0  movups  xmmword ptr [rsp+1F0h+UnicodeString.Length], xmm0
0x14000d5f5  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000d5fc  nop     dword ptr [rax+rax+00h]
0x14000d601  test    eax, eax
0x14000d603  js      loc_14000D7A6
0x14000d609  xorps   xmm0, xmm0
0x14000d60c  lea     rdx, SourceString; "\\REGISTRY\\USER\\"
0x14000d613  lea     rcx, [rsp+1F0h+DestinationString]; DestinationString
0x14000d618  movups  xmmword ptr [rsp+1F0h+DestinationString.Length], xmm0
0x14000d61d  call    cs:__imp_RtlInitUnicodeString
0x14000d624  nop     dword ptr [rax+rax+00h]
0x14000d629  xorps   xmm0, xmm0
0x14000d62c  lea     rdx, aSoftwareMicros_2; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x14000d633  lea     rcx, [rbp+0F0h+Source]; DestinationString
0x14000d637  movups  xmmword ptr [rbp+0F0h+Source.Length], xmm0
0x14000d63b  call    cs:__imp_RtlInitUnicodeString
0x14000d642  nop     dword ptr [rax+rax+00h]
0x14000d647  movzx   eax, [rsp+1F0h+UnicodeString.Length]
0x14000d64c  xorps   xmm0, xmm0
0x14000d64f  add     ax, 10h
0x14000d653  mov     edx, 73726447h
0x14000d658  add     ax, [rbp+0F0h+Source.Length]
0x14000d65c  add     ax, [rsp+1F0h+DestinationString.Length]
0x14000d661  movzx   ecx, ax
0x14000d664  movups  xmmword ptr [rsp+1F0h+Destination.Length], xmm0
0x14000d669  mov     [rsp+1F0h+Destination.MaximumLength], cx
0x14000d66e  call    PALLOCNOZ
0x14000d673  mov     [rsp+1F0h+Destination.Buffer], rax
0x14000d678  test    rax, rax
0x14000d67b  jz      loc_14000D970
0x14000d681  lea     rdx, [rsp+1F0h+DestinationString]; Source
0x14000d686  lea     rcx, [rsp+1F0h+Destination]; Destination
0x14000d68b  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000d692  nop     dword ptr [rax+rax+00h]
0x14000d697  lea     rdx, [rsp+1F0h+UnicodeString]; Source
0x14000d69c  lea     rcx, [rsp+1F0h+Destination]; Destination
0x14000d6a1  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000d6a8  nop     dword ptr [rax+rax+00h]
0x14000d6ad  lea     rdx, [rbp+0F0h+Source]; Source
0x14000d6b1  lea     rcx, [rsp+1F0h+Destination]; Destination
0x14000d6b6  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000d6bd  nop     dword ptr [rax+rax+00h]
0x14000d6c2  lea     rdx, [rbx+44h]; Source
0x14000d6c6  lea     rcx, [rsp+1F0h+Destination]; Destination
0x14000d6cb  call    cs:__imp_RtlAppendUnicodeToString
0x14000d6d2  nop     dword ptr [rax+rax+00h]
0x14000d6d7  lea     rcx, [rsp+1F0h+UnicodeString]; UnicodeString
0x14000d6dc  call    cs:__imp_RtlFreeUnicodeString
0x14000d6e3  nop     dword ptr [rax+rax+00h]
0x14000d6e8  mov     rdx, [rsp+1F0h+Destination.Buffer]; Path
0x14000d6ed  lea     rax, aUseperuserprof; "UsePerUserProfiles"
0x14000d6f4  xorps   xmm0, xmm0
0x14000d6f7  mov     [rbp+0F0h+QueryTable.Name], rax
0x14000d6fb  lea     rax, [rbp+0F0h+arg_10]
0x14000d702  mov     [rbp+0F0h+arg_10], r15d
0x14000d709  mov     [rbp+0F0h+QueryTable.EntryContext], rax
0x14000d70d  lea     r8, [rbp+0F0h+QueryTable]; QueryTable
0x14000d711  lea     rax, [rbp+0F0h+arg_18]
0x14000d718  mov     [rbp+0F0h+arg_18], r15d
0x14000d71f  xorps   xmm1, xmm1
0x14000d722  mov     [rbp+0F0h+QueryTable.DefaultData], rax
0x14000d726  xor     r9d, r9d; Context
0x14000d729  mov     [rbp+0F0h+QueryTable.QueryRoutine], r15
0x14000d72d  xor     ecx, ecx; RelativeTo
0x14000d72f  mov     [rbp+0F0h+QueryTable.Flags], 120h
0x14000d736  movups  xmmword ptr [rsp+1F0h+Src], xmm0
0x14000d73b  mov     [rbp+0F0h+QueryTable.DefaultType], 4000004h
0x14000d742  movups  xmmword ptr [rsp+1F0h+var_1A0.Length], xmm1
0x14000d747  mov     [rbp+0F0h+QueryTable.DefaultLength], 4
0x14000d74e  mov     [rbp+0F0h+var_128], r15
0x14000d752  mov     [rbp+0F0h+var_120], r15d
0x14000d756  mov     [rbp+0F0h+var_118], r15
0x14000d75a  movups  [rbp+0F0h+var_110], xmm0
0x14000d75e  mov     [rsp+1F0h+Environment], r15; Environment
0x14000d763  movups  [rbp+0F0h+var_100], xmm0
0x14000d767  call    cs:__imp_RtlQueryRegistryValues
0x14000d76e  nop     dword ptr [rax+rax+00h]
0x14000d773  mov     edi, eax
0x14000d775  test    eax, eax
0x14000d777  js      short loc_14000D7BF
0x14000d779  mov     eax, [rbp+0F0h+arg_10]
0x14000d77f  mov     [rbx+54h], eax
0x14000d782  test    eax, eax
0x14000d784  jnz     short loc_14000D7CD
0x14000d786  mov     rcx, [rsp+1F0h+Destination.Buffer]; Buffer
0x14000d78b  call    GreDeleteFastMutex
0x14000d790  cmp     [rbx+58h], r15d
0x14000d794  jnz     loc_14000DA0A
0x14000d79a  mov     eax, [rbx+5Ch]
0x14000d79d  neg     eax
0x14000d79f  sbb     eax, eax
0x14000d7a1  and     eax, 0C000000Dh
0x14000d7a6  lea     r11, [rsp+1F0h+var_10]
0x14000d7ae  mov     rbx, [r11+20h]
0x14000d7b2  mov     rsi, [r11+28h]
0x14000d7b6  mov     rsp, r11
0x14000d7b9  pop     r15
0x14000d7bb  pop     rdi
0x14000d7bc  pop     rbp
0x14000d7bd  retn
0x14000d7bf  mov     rcx, [rsp+1F0h+Destination.Buffer]; Buffer
0x14000d7c4  call    GreDeleteFastMutex
0x14000d7c9  mov     eax, edi
0x14000d7cb  jmp     short loc_14000D7A6
0x14000d7cd  mov     rdx, [rsp+1F0h+Destination.Buffer]; Path
0x14000d7d2  lea     rax, aIcmprofile; "ICMProfile"
0x14000d7d9  xorps   xmm0, xmm0
0x14000d7dc  mov     [rbp+0F0h+var_F0.Name], rax
0x14000d7e0  lea     rax, [rsp+1F0h+Src]
0x14000d7e5  mov     [rbp+0F0h+var_F0.QueryRoutine], r15
0x14000d7e9  mov     esi, 7000007h
0x14000d7ee  mov     [rbp+0F0h+var_F0.EntryContext], rax
0x14000d7f2  xor     r9d, r9d; Context
0x14000d7f5  mov     [rbp+0F0h+var_F0.Flags], 130h
0x14000d7fc  lea     r8, [rbp+0F0h+var_F0]; QueryTable
0x14000d800  mov     [rbp+0F0h+var_F0.DefaultType], esi
0x14000d803  xor     ecx, ecx; RelativeTo
0x14000d805  mov     [rbp+0F0h+var_F0.DefaultData], r15
0x14000d809  mov     [rbp+0F0h+var_F0.DefaultLength], r15d
0x14000d80d  mov     [rbp+0F0h+var_B8], r15
0x14000d811  mov     [rbp+0F0h+var_B0], r15d
0x14000d815  mov     [rbp+0F0h+var_A8], r15
0x14000d819  movups  [rbp+0F0h+var_A0], xmm0
0x14000d81d  mov     [rsp+1F0h+Environment], r15; Environment
0x14000d822  movups  [rbp+0F0h+var_90], xmm0
0x14000d826  call    cs:__imp_RtlQueryRegistryValues
0x14000d82d  nop     dword ptr [rax+rax+00h]
0x14000d832  mov     rdx, [rsp+1F0h+Destination.Buffer]; Path
0x14000d837  lea     r8, [rbp+0F0h+var_80]; QueryTable
0x14000d83b  mov     edi, eax
0x14000d83d  mov     [rbp+0F0h+var_80.QueryRoutine], r15
0x14000d841  xorps   xmm0, xmm0
0x14000d844  mov     [rbp+0F0h+var_80.Flags], 130h
0x14000d84b  lea     rax, aIcmprofileac; "ICMProfileAC"
0x14000d852  mov     [rbp+0F0h+var_80.DefaultType], esi
0x14000d858  mov     [rbp+0F0h+var_80.Name], rax
0x14000d85f  xor     r9d, r9d; Context
0x14000d862  lea     rax, [rsp+1F0h+var_1A0]
0x14000d867  mov     [rbp+0F0h+var_80.DefaultData], r15
0x14000d86e  xor     ecx, ecx; RelativeTo
0x14000d870  mov     [rbp+0F0h+var_80.EntryContext], rax
0x14000d877  mov     [rbp+0F0h+var_80.DefaultLength], r15d
0x14000d87e  mov     [rbp+0F0h+var_48], r15
0x14000d885  mov     [rbp+0F0h+var_40], r15d
0x14000d88c  mov     [rbp+0F0h+var_38], r15
0x14000d893  movups  [rbp+0F0h+var_30], xmm0
0x14000d89a  mov     [rsp+1F0h+Environment], r15; Environment
0x14000d89f  movups  [rbp+0F0h+var_20], xmm0
0x14000d8a6  call    cs:__imp_RtlQueryRegistryValues
0x14000d8ad  nop     dword ptr [rax+rax+00h]
0x14000d8b2  mov     rcx, [rsp+1F0h+Destination.Buffer]; Buffer
0x14000d8b7  mov     esi, eax
0x14000d8b9  call    GreDeleteFastMutex
0x14000d8be  test    edi, edi
0x14000d8c0  js      loc_14000D9C9
0x14000d8c6  mov     ecx, [rbx+58h]
0x14000d8c9  lea     rdi, [rbx+60h]
0x14000d8cd  movzx   eax, word ptr [rsp+1F0h+Src]
0x14000d8d2  test    ecx, ecx
0x14000d8d4  jz      loc_14000D99C
0x14000d8da  shr     eax, 1
0x14000d8dc  inc     eax
0x14000d8de  cmp     ecx, eax
0x14000d8e0  jnz     loc_14000D9DA
0x14000d8e6  movzx   r8d, word ptr [rsp+1F0h+Src]; Size
0x14000d8ec  mov     rcx, rdi; void *
0x14000d8ef  mov     rdx, [rsp+1F0h+Src+8]; Src
0x14000d8f4  call    memmove
0x14000d8f9  mov     eax, [rbx+58h]
0x14000d8fc  lea     rdi, [rdi+rax*2]
0x14000d900  mov     [rdi-2], r15w
0x14000d905  mov     ecx, [rbx+5Ch]
0x14000d908  movzx   eax, [rsp+1F0h+var_1A0.Length]
0x14000d90d  test    ecx, ecx
0x14000d90f  jz      short loc_14000D98B
0x14000d911  shr     eax, 1
0x14000d913  inc     eax
0x14000d915  cmp     ecx, eax
0x14000d917  jnz     loc_14000D9DA
0x14000d91d  movzx   r8d, [rsp+1F0h+var_1A0.Length]; Size
0x14000d923  mov     rcx, rdi; void *
0x14000d926  mov     rdx, [rsp+1F0h+var_1A0.Buffer]; Src
0x14000d92b  call    memmove
0x14000d930  mov     ecx, [rbx+5Ch]
0x14000d933  mov     [rdi+rcx*2-2], r15w
0x14000d939  cmp     [rsp+1F0h+Src+8], r15
0x14000d93e  jz      short loc_14000D951
0x14000d940  lea     rcx, [rsp+1F0h+Src]; UnicodeString
0x14000d945  call    cs:__imp_RtlFreeUnicodeString
0x14000d94c  nop     dword ptr [rax+rax+00h]
0x14000d951  cmp     [rsp+1F0h+var_1A0.Buffer], r15
0x14000d956  jz      short loc_14000D969
0x14000d958  lea     rcx, [rsp+1F0h+var_1A0]; UnicodeString
0x14000d95d  call    cs:__imp_RtlFreeUnicodeString
0x14000d964  nop     dword ptr [rax+rax+00h]
0x14000d969  xor     eax, eax
0x14000d96b  jmp     loc_14000D7A6
0x14000d970  lea     rcx, [rsp+1F0h+UnicodeString]; UnicodeString
0x14000d975  call    cs:__imp_RtlFreeUnicodeString
0x14000d97c  nop     dword ptr [rax+rax+00h]
0x14000d981  mov     eax, 0C0000017h
0x14000d986  jmp     loc_14000D7A6
0x14000d98b  test    ax, ax
0x14000d98e  jnz     loc_14000DA14
0x14000d994  mov     eax, r15d
0x14000d997  mov     [rbx+5Ch], eax
0x14000d99a  jmp     short loc_14000D939
0x14000d99c  test    ax, ax
0x14000d99f  jz      short loc_14000D9AD
0x14000d9a1  shr     eax, 1
0x14000d9a3  inc     eax
0x14000d9a5  mov     [rbx+58h], eax
0x14000d9a8  jmp     loc_14000D905
0x14000d9ad  mov     eax, r15d
0x14000d9b0  jmp     short loc_14000D9A5
0x14000d9b2  cmp     cs:gbOSTestSigningEnabled, r15b
0x14000d9b9  jnz     loc_14000D5A6
0x14000d9bf  mov     eax, 0C0000022h
0x14000d9c4  jmp     loc_14000D7A6
0x14000d9c9  test    esi, esi
0x14000d9cb  jns     loc_14000D8C6
0x14000d9d1  mov     [rbx+54h], r15d
0x14000d9d5  jmp     loc_14000D7C9
0x14000d9da  cmp     [rsp+1F0h+Src+8], r15
0x14000d9df  jz      short loc_14000D9F2
0x14000d9e1  lea     rcx, [rsp+1F0h+Src]; UnicodeString
0x14000d9e6  call    cs:__imp_RtlFreeUnicodeString
0x14000d9ed  nop     dword ptr [rax+rax+00h]
0x14000d9f2  cmp     [rsp+1F0h+var_1A0.Buffer], r15
0x14000d9f7  jz      short loc_14000DA0A
0x14000d9f9  lea     rcx, [rsp+1F0h+var_1A0]; UnicodeString
0x14000d9fe  call    cs:__imp_RtlFreeUnicodeString
0x14000da05  nop     dword ptr [rax+rax+00h]
0x14000da0a  mov     eax, 0C000000Dh
0x14000da0f  jmp     loc_14000D7A6
0x14000da14  shr     eax, 1
0x14000da16  inc     eax
0x14000da18  jmp     loc_14000D997
```
