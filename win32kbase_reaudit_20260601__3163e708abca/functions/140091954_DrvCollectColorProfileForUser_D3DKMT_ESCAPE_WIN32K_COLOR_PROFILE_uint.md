# DrvCollectColorProfileForUser(_D3DKMT_ESCAPE_WIN32K_COLOR_PROFILE *,uint)

- ea: `0x140091954`
- end: `0x140091dfd`
- name: `?DrvCollectColorProfileForUser@@YAJPEAU_D3DKMT_ESCAPE_WIN32K_COLOR_PROFILE@@I@Z`
- size: `1193`
- prototype: `__int64 __fastcall(PSID Sid, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1401618e8`

## callees

- `0x1400411c0`
- `0x140091954`
- `0x140091e04`
- `0x14009202c`
- `0x140239180`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140091abc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140091d25`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140091d3d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140091d55`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140091dc6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140091dde`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140091abc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140091d25`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140091d3d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140091d55`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140091dc6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140091dde`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140091aab`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140091aab`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140091a6b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140091a81`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140091a96`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140091a6b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140091a81`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140091a96`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140091b47`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140091c06`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140091c86`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140091b47`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140091c06`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140091c86`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400919d5`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400919d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400919fd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091a1b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400919fd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091a1b`

## string_xrefs

- `0x1400919ec`: `\REGISTRY\USER\`

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
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-A0h] BYREF
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
0x140091954  mov     [rsp-8+arg_0], rbx
0x140091959  mov     [rsp-8+arg_8], rsi
0x14009195e  push    rbp
0x14009195f  push    rdi
0x140091960  push    r15
0x140091962  lea     rbp, [rsp-0E0h]
0x14009196a  sub     rsp, 1E0h
0x140091971  mov     edi, edx
0x140091973  mov     rbx, rcx
0x140091976  call    DxgkEngIsDwmProcess
0x14009197b  xor     r15d, r15d
0x14009197e  test    eax, eax
0x140091980  jz      loc_140091D92
0x140091986  mov     ecx, [rbx+58h]
0x140091989  lea     eax, [rdi-60h]
0x14009198c  add     ecx, [rbx+5Ch]
0x14009198f  cmp     ecx, eax
0x140091991  ja      loc_140091DEA
0x140091997  cmp     [rbx+52h], r15w
0x14009199c  jnz     loc_140091DEA
0x1400919a2  lea     rcx, [rbx+44h]
0x1400919a6  movzx   eax, word ptr [rcx]
0x1400919a9  test    ax, ax
0x1400919ac  jz      short loc_1400919C2
0x1400919ae  sub     ax, 30h ; '0'
0x1400919b2  cmp     ax, 9
0x1400919b6  ja      loc_140091DEA
0x1400919bc  add     rcx, 2
0x1400919c0  jmp     short loc_1400919A6
0x1400919c2  xorps   xmm0, xmm0
0x1400919c5  lea     rcx, [rsp+1F0h+UnicodeString]; UnicodeString
0x1400919ca  mov     r8b, 1; AllocateDestinationString
0x1400919cd  mov     rdx, rbx; Sid
0x1400919d0  movups  xmmword ptr [rsp+1F0h+UnicodeString.Length], xmm0
0x1400919d5  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400919dc  nop     dword ptr [rax+rax+00h]
0x1400919e1  test    eax, eax
0x1400919e3  js      loc_140091B86
0x1400919e9  xorps   xmm0, xmm0
0x1400919ec  lea     rdx, SourceString; "\\REGISTRY\\USER\\"
0x1400919f3  lea     rcx, [rsp+1F0h+DestinationString]; DestinationString
0x1400919f8  movups  xmmword ptr [rsp+1F0h+DestinationString.Length], xmm0
0x1400919fd  call    cs:__imp_RtlInitUnicodeString
0x140091a04  nop     dword ptr [rax+rax+00h]
0x140091a09  xorps   xmm0, xmm0
0x140091a0c  lea     rdx, aSoftwareMicros_2; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x140091a13  lea     rcx, [rbp+0F0h+Source]; DestinationString
0x140091a17  movups  xmmword ptr [rbp+0F0h+Source.Length], xmm0
0x140091a1b  call    cs:__imp_RtlInitUnicodeString
0x140091a22  nop     dword ptr [rax+rax+00h]
0x140091a27  movzx   eax, [rsp+1F0h+UnicodeString.Length]
0x140091a2c  xorps   xmm0, xmm0
0x140091a2f  add     ax, 10h
0x140091a33  mov     edx, 73726447h
0x140091a38  add     ax, [rbp+0F0h+Source.Length]
0x140091a3c  add     ax, [rsp+1F0h+DestinationString.Length]
0x140091a41  movzx   ecx, ax
0x140091a44  movups  xmmword ptr [rsp+1F0h+Destination.Length], xmm0
0x140091a49  mov     [rsp+1F0h+Destination.MaximumLength], cx
0x140091a4e  call    PALLOCNOZ
0x140091a53  mov     [rsp+1F0h+Destination.Buffer], rax
0x140091a58  test    rax, rax
0x140091a5b  jz      loc_140091D50
0x140091a61  lea     rdx, [rsp+1F0h+DestinationString]; Source
0x140091a66  lea     rcx, [rsp+1F0h+Destination]; Destination
0x140091a6b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140091a72  nop     dword ptr [rax+rax+00h]
0x140091a77  lea     rdx, [rsp+1F0h+UnicodeString]; Source
0x140091a7c  lea     rcx, [rsp+1F0h+Destination]; Destination
0x140091a81  call    cs:__imp_RtlAppendUnicodeStringToString
0x140091a88  nop     dword ptr [rax+rax+00h]
0x140091a8d  lea     rdx, [rbp+0F0h+Source]; Source
0x140091a91  lea     rcx, [rsp+1F0h+Destination]; Destination
0x140091a96  call    cs:__imp_RtlAppendUnicodeStringToString
0x140091a9d  nop     dword ptr [rax+rax+00h]
0x140091aa2  lea     rdx, [rbx+44h]; Source
0x140091aa6  lea     rcx, [rsp+1F0h+Destination]; Destination
0x140091aab  call    cs:__imp_RtlAppendUnicodeToString
0x140091ab2  nop     dword ptr [rax+rax+00h]
0x140091ab7  lea     rcx, [rsp+1F0h+UnicodeString]; UnicodeString
0x140091abc  call    cs:__imp_RtlFreeUnicodeString
0x140091ac3  nop     dword ptr [rax+rax+00h]
0x140091ac8  mov     rdx, [rsp+1F0h+Destination.Buffer]; Path
0x140091acd  lea     rax, aUseperuserprof; "UsePerUserProfiles"
0x140091ad4  xorps   xmm0, xmm0
0x140091ad7  mov     [rbp+0F0h+QueryTable.Name], rax
0x140091adb  lea     rax, [rbp+0F0h+arg_10]
0x140091ae2  mov     [rbp+0F0h+arg_10], r15d
0x140091ae9  mov     [rbp+0F0h+QueryTable.EntryContext], rax
0x140091aed  lea     r8, [rbp+0F0h+QueryTable]; QueryTable
0x140091af1  lea     rax, [rbp+0F0h+arg_18]
0x140091af8  mov     [rbp+0F0h+arg_18], r15d
0x140091aff  xorps   xmm1, xmm1
0x140091b02  mov     [rbp+0F0h+QueryTable.DefaultData], rax
0x140091b06  xor     r9d, r9d; Context
0x140091b09  mov     [rbp+0F0h+QueryTable.QueryRoutine], r15
0x140091b0d  xor     ecx, ecx; RelativeTo
0x140091b0f  mov     [rbp+0F0h+QueryTable.Flags], 120h
0x140091b16  movups  xmmword ptr [rsp+1F0h+Src], xmm0
0x140091b1b  mov     [rbp+0F0h+QueryTable.DefaultType], 4000004h
0x140091b22  movups  xmmword ptr [rsp+1F0h+var_1A0.Length], xmm1
0x140091b27  mov     [rbp+0F0h+QueryTable.DefaultLength], 4
0x140091b2e  mov     [rbp+0F0h+var_128], r15
0x140091b32  mov     [rbp+0F0h+var_120], r15d
0x140091b36  mov     [rbp+0F0h+var_118], r15
0x140091b3a  movups  [rbp+0F0h+var_110], xmm0
0x140091b3e  mov     [rsp+1F0h+Environment], r15; Environment
0x140091b43  movups  [rbp+0F0h+var_100], xmm0
0x140091b47  call    cs:__imp_RtlQueryRegistryValues
0x140091b4e  nop     dword ptr [rax+rax+00h]
0x140091b53  mov     edi, eax
0x140091b55  test    eax, eax
0x140091b57  js      short loc_140091B9F
0x140091b59  mov     eax, [rbp+0F0h+arg_10]
0x140091b5f  mov     [rbx+54h], eax
0x140091b62  test    eax, eax
0x140091b64  jnz     short loc_140091BAD
0x140091b66  mov     rcx, [rsp+1F0h+Destination.Buffer]; Buffer
0x140091b6b  call    GreDeleteFastMutex
0x140091b70  cmp     [rbx+58h], r15d
0x140091b74  jnz     loc_140091DEA
0x140091b7a  mov     eax, [rbx+5Ch]
0x140091b7d  neg     eax
0x140091b7f  sbb     eax, eax
0x140091b81  and     eax, 0C000000Dh
0x140091b86  lea     r11, [rsp+1F0h+var_10]
0x140091b8e  mov     rbx, [r11+20h]
0x140091b92  mov     rsi, [r11+28h]
0x140091b96  mov     rsp, r11
0x140091b99  pop     r15
0x140091b9b  pop     rdi
0x140091b9c  pop     rbp
0x140091b9d  retn
0x140091b9f  mov     rcx, [rsp+1F0h+Destination.Buffer]; Buffer
0x140091ba4  call    GreDeleteFastMutex
0x140091ba9  mov     eax, edi
0x140091bab  jmp     short loc_140091B86
0x140091bad  mov     rdx, [rsp+1F0h+Destination.Buffer]; Path
0x140091bb2  lea     rax, aIcmprofile; "ICMProfile"
0x140091bb9  xorps   xmm0, xmm0
0x140091bbc  mov     [rbp+0F0h+var_F0.Name], rax
0x140091bc0  lea     rax, [rsp+1F0h+Src]
0x140091bc5  mov     [rbp+0F0h+var_F0.QueryRoutine], r15
0x140091bc9  mov     esi, 7000007h
0x140091bce  mov     [rbp+0F0h+var_F0.EntryContext], rax
0x140091bd2  xor     r9d, r9d; Context
0x140091bd5  mov     [rbp+0F0h+var_F0.Flags], 130h
0x140091bdc  lea     r8, [rbp+0F0h+var_F0]; QueryTable
0x140091be0  mov     [rbp+0F0h+var_F0.DefaultType], esi
0x140091be3  xor     ecx, ecx; RelativeTo
0x140091be5  mov     [rbp+0F0h+var_F0.DefaultData], r15
0x140091be9  mov     [rbp+0F0h+var_F0.DefaultLength], r15d
0x140091bed  mov     [rbp+0F0h+var_B8], r15
0x140091bf1  mov     [rbp+0F0h+var_B0], r15d
0x140091bf5  mov     [rbp+0F0h+var_A8], r15
0x140091bf9  movups  [rbp+0F0h+var_A0], xmm0
0x140091bfd  mov     [rsp+1F0h+Environment], r15; Environment
0x140091c02  movups  [rbp+0F0h+var_90], xmm0
0x140091c06  call    cs:__imp_RtlQueryRegistryValues
0x140091c0d  nop     dword ptr [rax+rax+00h]
0x140091c12  mov     rdx, [rsp+1F0h+Destination.Buffer]; Path
0x140091c17  lea     r8, [rbp+0F0h+var_80]; QueryTable
0x140091c1b  mov     edi, eax
0x140091c1d  mov     [rbp+0F0h+var_80.QueryRoutine], r15
0x140091c21  xorps   xmm0, xmm0
0x140091c24  mov     [rbp+0F0h+var_80.Flags], 130h
0x140091c2b  lea     rax, aIcmprofileac; "ICMProfileAC"
0x140091c32  mov     [rbp+0F0h+var_80.DefaultType], esi
0x140091c38  mov     [rbp+0F0h+var_80.Name], rax
0x140091c3f  xor     r9d, r9d; Context
0x140091c42  lea     rax, [rsp+1F0h+var_1A0]
0x140091c47  mov     [rbp+0F0h+var_80.DefaultData], r15
0x140091c4e  xor     ecx, ecx; RelativeTo
0x140091c50  mov     [rbp+0F0h+var_80.EntryContext], rax
0x140091c57  mov     [rbp+0F0h+var_80.DefaultLength], r15d
0x140091c5e  mov     [rbp+0F0h+var_48], r15
0x140091c65  mov     [rbp+0F0h+var_40], r15d
0x140091c6c  mov     [rbp+0F0h+var_38], r15
0x140091c73  movups  [rbp+0F0h+var_30], xmm0
0x140091c7a  mov     [rsp+1F0h+Environment], r15; Environment
0x140091c7f  movups  [rbp+0F0h+var_20], xmm0
0x140091c86  call    cs:__imp_RtlQueryRegistryValues
0x140091c8d  nop     dword ptr [rax+rax+00h]
0x140091c92  mov     rcx, [rsp+1F0h+Destination.Buffer]; Buffer
0x140091c97  mov     esi, eax
0x140091c99  call    GreDeleteFastMutex
0x140091c9e  test    edi, edi
0x140091ca0  js      loc_140091DA9
0x140091ca6  mov     ecx, [rbx+58h]
0x140091ca9  lea     rdi, [rbx+60h]
0x140091cad  movzx   eax, word ptr [rsp+1F0h+Src]
0x140091cb2  test    ecx, ecx
0x140091cb4  jz      loc_140091D7C
0x140091cba  shr     eax, 1
0x140091cbc  inc     eax
0x140091cbe  cmp     ecx, eax
0x140091cc0  jnz     loc_140091DBA
0x140091cc6  movzx   r8d, word ptr [rsp+1F0h+Src]; Size
0x140091ccc  mov     rcx, rdi; void *
0x140091ccf  mov     rdx, [rsp+1F0h+Src+8]; Src
0x140091cd4  call    memmove
0x140091cd9  mov     eax, [rbx+58h]
0x140091cdc  lea     rdi, [rdi+rax*2]
0x140091ce0  mov     [rdi-2], r15w
0x140091ce5  mov     ecx, [rbx+5Ch]
0x140091ce8  movzx   eax, [rsp+1F0h+var_1A0.Length]
0x140091ced  test    ecx, ecx
0x140091cef  jz      short loc_140091D6B
0x140091cf1  shr     eax, 1
0x140091cf3  inc     eax
0x140091cf5  cmp     ecx, eax
0x140091cf7  jnz     loc_140091DBA
0x140091cfd  movzx   r8d, [rsp+1F0h+var_1A0.Length]; Size
0x140091d03  mov     rcx, rdi; void *
0x140091d06  mov     rdx, [rsp+1F0h+var_1A0.Buffer]; Src
0x140091d0b  call    memmove
0x140091d10  mov     ecx, [rbx+5Ch]
0x140091d13  mov     [rdi+rcx*2-2], r15w
0x140091d19  cmp     [rsp+1F0h+Src+8], r15
0x140091d1e  jz      short loc_140091D31
0x140091d20  lea     rcx, [rsp+1F0h+Src]; UnicodeString
0x140091d25  call    cs:__imp_RtlFreeUnicodeString
0x140091d2c  nop     dword ptr [rax+rax+00h]
0x140091d31  cmp     [rsp+1F0h+var_1A0.Buffer], r15
0x140091d36  jz      short loc_140091D49
0x140091d38  lea     rcx, [rsp+1F0h+var_1A0]; UnicodeString
0x140091d3d  call    cs:__imp_RtlFreeUnicodeString
0x140091d44  nop     dword ptr [rax+rax+00h]
0x140091d49  xor     eax, eax
0x140091d4b  jmp     loc_140091B86
0x140091d50  lea     rcx, [rsp+1F0h+UnicodeString]; UnicodeString
0x140091d55  call    cs:__imp_RtlFreeUnicodeString
0x140091d5c  nop     dword ptr [rax+rax+00h]
0x140091d61  mov     eax, 0C0000017h
0x140091d66  jmp     loc_140091B86
0x140091d6b  test    ax, ax
0x140091d6e  jnz     loc_140091DF4
0x140091d74  mov     eax, r15d
0x140091d77  mov     [rbx+5Ch], eax
0x140091d7a  jmp     short loc_140091D19
0x140091d7c  test    ax, ax
0x140091d7f  jz      short loc_140091D8D
0x140091d81  shr     eax, 1
0x140091d83  inc     eax
0x140091d85  mov     [rbx+58h], eax
0x140091d88  jmp     loc_140091CE5
0x140091d8d  mov     eax, r15d
0x140091d90  jmp     short loc_140091D85
0x140091d92  cmp     cs:gbOSTestSigningEnabled, r15b
0x140091d99  jnz     loc_140091986
0x140091d9f  mov     eax, 0C0000022h
0x140091da4  jmp     loc_140091B86
0x140091da9  test    esi, esi
0x140091dab  jns     loc_140091CA6
0x140091db1  mov     [rbx+54h], r15d
0x140091db5  jmp     loc_140091BA9
0x140091dba  cmp     [rsp+1F0h+Src+8], r15
0x140091dbf  jz      short loc_140091DD2
0x140091dc1  lea     rcx, [rsp+1F0h+Src]; UnicodeString
0x140091dc6  call    cs:__imp_RtlFreeUnicodeString
0x140091dcd  nop     dword ptr [rax+rax+00h]
0x140091dd2  cmp     [rsp+1F0h+var_1A0.Buffer], r15
0x140091dd7  jz      short loc_140091DEA
0x140091dd9  lea     rcx, [rsp+1F0h+var_1A0]; UnicodeString
0x140091dde  call    cs:__imp_RtlFreeUnicodeString
0x140091de5  nop     dword ptr [rax+rax+00h]
0x140091dea  mov     eax, 0C000000Dh
0x140091def  jmp     loc_140091B86
0x140091df4  shr     eax, 1
0x140091df6  inc     eax
0x140091df8  jmp     loc_140091D77
```
