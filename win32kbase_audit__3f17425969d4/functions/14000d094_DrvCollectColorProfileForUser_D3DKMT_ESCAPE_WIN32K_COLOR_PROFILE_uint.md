# DrvCollectColorProfileForUser(_D3DKMT_ESCAPE_WIN32K_COLOR_PROFILE *,uint)

- ea: `0x14000d094`
- end: `0x14000d53d`
- name: `?DrvCollectColorProfileForUser@@YAJPEAU_D3DKMT_ESCAPE_WIN32K_COLOR_PROFILE@@I@Z`
- size: `1193`
- prototype: `NTSTATUS __fastcall(char *Sid, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140164758`

## callees

- `0x14000d094`
- `0x14000d544`
- `0x14000d76c`
- `0x14007b930`
- `0x140238f80`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d1fc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d465`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d47d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d495`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d506`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d51e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d1fc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d465`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d47d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d495`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d506`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d51e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000d1eb`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000d1eb`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000d1ab`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000d1c1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000d1d6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000d1ab`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000d1c1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000d1d6`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d287`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d346`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d3c6`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d287`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d346`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d3c6`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000d115`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000d115`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d13d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d15b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d13d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d15b`

## string_xrefs

- `0x14000d12c`: `\REGISTRY\USER\`

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
0x14000d094  mov     [rsp-8+arg_0], rbx
0x14000d099  mov     [rsp-8+arg_8], rsi
0x14000d09e  push    rbp
0x14000d09f  push    rdi
0x14000d0a0  push    r15
0x14000d0a2  lea     rbp, [rsp-0E0h]
0x14000d0aa  sub     rsp, 1E0h
0x14000d0b1  mov     edi, edx
0x14000d0b3  mov     rbx, rcx
0x14000d0b6  call    DxgkEngIsDwmProcess
0x14000d0bb  xor     r15d, r15d
0x14000d0be  test    eax, eax
0x14000d0c0  jz      loc_14000D4D2
0x14000d0c6  mov     ecx, [rbx+58h]
0x14000d0c9  lea     eax, [rdi-60h]
0x14000d0cc  add     ecx, [rbx+5Ch]
0x14000d0cf  cmp     ecx, eax
0x14000d0d1  ja      loc_14000D52A
0x14000d0d7  cmp     [rbx+52h], r15w
0x14000d0dc  jnz     loc_14000D52A
0x14000d0e2  lea     rcx, [rbx+44h]
0x14000d0e6  movzx   eax, word ptr [rcx]
0x14000d0e9  test    ax, ax
0x14000d0ec  jz      short loc_14000D102
0x14000d0ee  sub     ax, 30h ; '0'
0x14000d0f2  cmp     ax, 9
0x14000d0f6  ja      loc_14000D52A
0x14000d0fc  add     rcx, 2
0x14000d100  jmp     short loc_14000D0E6
0x14000d102  xorps   xmm0, xmm0
0x14000d105  lea     rcx, [rsp+1F0h+UnicodeString]; UnicodeString
0x14000d10a  mov     r8b, 1; AllocateDestinationString
0x14000d10d  mov     rdx, rbx; Sid
0x14000d110  movups  xmmword ptr [rsp+1F0h+UnicodeString.Length], xmm0
0x14000d115  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000d11c  nop     dword ptr [rax+rax+00h]
0x14000d121  test    eax, eax
0x14000d123  js      loc_14000D2C6
0x14000d129  xorps   xmm0, xmm0
0x14000d12c  lea     rdx, SourceString; "\\REGISTRY\\USER\\"
0x14000d133  lea     rcx, [rsp+1F0h+DestinationString]; DestinationString
0x14000d138  movups  xmmword ptr [rsp+1F0h+DestinationString.Length], xmm0
0x14000d13d  call    cs:__imp_RtlInitUnicodeString
0x14000d144  nop     dword ptr [rax+rax+00h]
0x14000d149  xorps   xmm0, xmm0
0x14000d14c  lea     rdx, aSoftwareMicros_2; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x14000d153  lea     rcx, [rbp+0F0h+Source]; DestinationString
0x14000d157  movups  xmmword ptr [rbp+0F0h+Source.Length], xmm0
0x14000d15b  call    cs:__imp_RtlInitUnicodeString
0x14000d162  nop     dword ptr [rax+rax+00h]
0x14000d167  movzx   eax, [rsp+1F0h+UnicodeString.Length]
0x14000d16c  xorps   xmm0, xmm0
0x14000d16f  add     ax, 10h
0x14000d173  mov     edx, 73726447h
0x14000d178  add     ax, [rbp+0F0h+Source.Length]
0x14000d17c  add     ax, [rsp+1F0h+DestinationString.Length]
0x14000d181  movzx   ecx, ax
0x14000d184  movups  xmmword ptr [rsp+1F0h+Destination.Length], xmm0
0x14000d189  mov     [rsp+1F0h+Destination.MaximumLength], cx
0x14000d18e  call    PALLOCNOZ
0x14000d193  mov     [rsp+1F0h+Destination.Buffer], rax
0x14000d198  test    rax, rax
0x14000d19b  jz      loc_14000D490
0x14000d1a1  lea     rdx, [rsp+1F0h+DestinationString]; Source
0x14000d1a6  lea     rcx, [rsp+1F0h+Destination]; Destination
0x14000d1ab  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000d1b2  nop     dword ptr [rax+rax+00h]
0x14000d1b7  lea     rdx, [rsp+1F0h+UnicodeString]; Source
0x14000d1bc  lea     rcx, [rsp+1F0h+Destination]; Destination
0x14000d1c1  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000d1c8  nop     dword ptr [rax+rax+00h]
0x14000d1cd  lea     rdx, [rbp+0F0h+Source]; Source
0x14000d1d1  lea     rcx, [rsp+1F0h+Destination]; Destination
0x14000d1d6  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000d1dd  nop     dword ptr [rax+rax+00h]
0x14000d1e2  lea     rdx, [rbx+44h]; Source
0x14000d1e6  lea     rcx, [rsp+1F0h+Destination]; Destination
0x14000d1eb  call    cs:__imp_RtlAppendUnicodeToString
0x14000d1f2  nop     dword ptr [rax+rax+00h]
0x14000d1f7  lea     rcx, [rsp+1F0h+UnicodeString]; UnicodeString
0x14000d1fc  call    cs:__imp_RtlFreeUnicodeString
0x14000d203  nop     dword ptr [rax+rax+00h]
0x14000d208  mov     rdx, [rsp+1F0h+Destination.Buffer]; Path
0x14000d20d  lea     rax, aUseperuserprof; "UsePerUserProfiles"
0x14000d214  xorps   xmm0, xmm0
0x14000d217  mov     [rbp+0F0h+QueryTable.Name], rax
0x14000d21b  lea     rax, [rbp+0F0h+arg_10]
0x14000d222  mov     [rbp+0F0h+arg_10], r15d
0x14000d229  mov     [rbp+0F0h+QueryTable.EntryContext], rax
0x14000d22d  lea     r8, [rbp+0F0h+QueryTable]; QueryTable
0x14000d231  lea     rax, [rbp+0F0h+arg_18]
0x14000d238  mov     [rbp+0F0h+arg_18], r15d
0x14000d23f  xorps   xmm1, xmm1
0x14000d242  mov     [rbp+0F0h+QueryTable.DefaultData], rax
0x14000d246  xor     r9d, r9d; Context
0x14000d249  mov     [rbp+0F0h+QueryTable.QueryRoutine], r15
0x14000d24d  xor     ecx, ecx; RelativeTo
0x14000d24f  mov     [rbp+0F0h+QueryTable.Flags], 120h
0x14000d256  movups  xmmword ptr [rsp+1F0h+Src], xmm0
0x14000d25b  mov     [rbp+0F0h+QueryTable.DefaultType], 4000004h
0x14000d262  movups  xmmword ptr [rsp+1F0h+var_1A0.Length], xmm1
0x14000d267  mov     [rbp+0F0h+QueryTable.DefaultLength], 4
0x14000d26e  mov     [rbp+0F0h+var_128], r15
0x14000d272  mov     [rbp+0F0h+var_120], r15d
0x14000d276  mov     [rbp+0F0h+var_118], r15
0x14000d27a  movups  [rbp+0F0h+var_110], xmm0
0x14000d27e  mov     [rsp+1F0h+Environment], r15; Environment
0x14000d283  movups  [rbp+0F0h+var_100], xmm0
0x14000d287  call    cs:__imp_RtlQueryRegistryValues
0x14000d28e  nop     dword ptr [rax+rax+00h]
0x14000d293  mov     edi, eax
0x14000d295  test    eax, eax
0x14000d297  js      short loc_14000D2DF
0x14000d299  mov     eax, [rbp+0F0h+arg_10]
0x14000d29f  mov     [rbx+54h], eax
0x14000d2a2  test    eax, eax
0x14000d2a4  jnz     short loc_14000D2ED
0x14000d2a6  mov     rcx, [rsp+1F0h+Destination.Buffer]; Buffer
0x14000d2ab  call    GreDeleteFastMutex
0x14000d2b0  cmp     [rbx+58h], r15d
0x14000d2b4  jnz     loc_14000D52A
0x14000d2ba  mov     eax, [rbx+5Ch]
0x14000d2bd  neg     eax
0x14000d2bf  sbb     eax, eax
0x14000d2c1  and     eax, 0C000000Dh
0x14000d2c6  lea     r11, [rsp+1F0h+var_10]
0x14000d2ce  mov     rbx, [r11+20h]
0x14000d2d2  mov     rsi, [r11+28h]
0x14000d2d6  mov     rsp, r11
0x14000d2d9  pop     r15
0x14000d2db  pop     rdi
0x14000d2dc  pop     rbp
0x14000d2dd  retn
0x14000d2df  mov     rcx, [rsp+1F0h+Destination.Buffer]; Buffer
0x14000d2e4  call    GreDeleteFastMutex
0x14000d2e9  mov     eax, edi
0x14000d2eb  jmp     short loc_14000D2C6
0x14000d2ed  mov     rdx, [rsp+1F0h+Destination.Buffer]; Path
0x14000d2f2  lea     rax, aIcmprofile; "ICMProfile"
0x14000d2f9  xorps   xmm0, xmm0
0x14000d2fc  mov     [rbp+0F0h+var_F0.Name], rax
0x14000d300  lea     rax, [rsp+1F0h+Src]
0x14000d305  mov     [rbp+0F0h+var_F0.QueryRoutine], r15
0x14000d309  mov     esi, 7000007h
0x14000d30e  mov     [rbp+0F0h+var_F0.EntryContext], rax
0x14000d312  xor     r9d, r9d; Context
0x14000d315  mov     [rbp+0F0h+var_F0.Flags], 130h
0x14000d31c  lea     r8, [rbp+0F0h+var_F0]; QueryTable
0x14000d320  mov     [rbp+0F0h+var_F0.DefaultType], esi
0x14000d323  xor     ecx, ecx; RelativeTo
0x14000d325  mov     [rbp+0F0h+var_F0.DefaultData], r15
0x14000d329  mov     [rbp+0F0h+var_F0.DefaultLength], r15d
0x14000d32d  mov     [rbp+0F0h+var_B8], r15
0x14000d331  mov     [rbp+0F0h+var_B0], r15d
0x14000d335  mov     [rbp+0F0h+var_A8], r15
0x14000d339  movups  [rbp+0F0h+var_A0], xmm0
0x14000d33d  mov     [rsp+1F0h+Environment], r15; Environment
0x14000d342  movups  [rbp+0F0h+var_90], xmm0
0x14000d346  call    cs:__imp_RtlQueryRegistryValues
0x14000d34d  nop     dword ptr [rax+rax+00h]
0x14000d352  mov     rdx, [rsp+1F0h+Destination.Buffer]; Path
0x14000d357  lea     r8, [rbp+0F0h+var_80]; QueryTable
0x14000d35b  mov     edi, eax
0x14000d35d  mov     [rbp+0F0h+var_80.QueryRoutine], r15
0x14000d361  xorps   xmm0, xmm0
0x14000d364  mov     [rbp+0F0h+var_80.Flags], 130h
0x14000d36b  lea     rax, aIcmprofileac; "ICMProfileAC"
0x14000d372  mov     [rbp+0F0h+var_80.DefaultType], esi
0x14000d378  mov     [rbp+0F0h+var_80.Name], rax
0x14000d37f  xor     r9d, r9d; Context
0x14000d382  lea     rax, [rsp+1F0h+var_1A0]
0x14000d387  mov     [rbp+0F0h+var_80.DefaultData], r15
0x14000d38e  xor     ecx, ecx; RelativeTo
0x14000d390  mov     [rbp+0F0h+var_80.EntryContext], rax
0x14000d397  mov     [rbp+0F0h+var_80.DefaultLength], r15d
0x14000d39e  mov     [rbp+0F0h+var_48], r15
0x14000d3a5  mov     [rbp+0F0h+var_40], r15d
0x14000d3ac  mov     [rbp+0F0h+var_38], r15
0x14000d3b3  movups  [rbp+0F0h+var_30], xmm0
0x14000d3ba  mov     [rsp+1F0h+Environment], r15; Environment
0x14000d3bf  movups  [rbp+0F0h+var_20], xmm0
0x14000d3c6  call    cs:__imp_RtlQueryRegistryValues
0x14000d3cd  nop     dword ptr [rax+rax+00h]
0x14000d3d2  mov     rcx, [rsp+1F0h+Destination.Buffer]; Buffer
0x14000d3d7  mov     esi, eax
0x14000d3d9  call    GreDeleteFastMutex
0x14000d3de  test    edi, edi
0x14000d3e0  js      loc_14000D4E9
0x14000d3e6  mov     ecx, [rbx+58h]
0x14000d3e9  lea     rdi, [rbx+60h]
0x14000d3ed  movzx   eax, word ptr [rsp+1F0h+Src]
0x14000d3f2  test    ecx, ecx
0x14000d3f4  jz      loc_14000D4BC
0x14000d3fa  shr     eax, 1
0x14000d3fc  inc     eax
0x14000d3fe  cmp     ecx, eax
0x14000d400  jnz     loc_14000D4FA
0x14000d406  movzx   r8d, word ptr [rsp+1F0h+Src]; Size
0x14000d40c  mov     rcx, rdi; void *
0x14000d40f  mov     rdx, [rsp+1F0h+Src+8]; Src
0x14000d414  call    memmove
0x14000d419  mov     eax, [rbx+58h]
0x14000d41c  lea     rdi, [rdi+rax*2]
0x14000d420  mov     [rdi-2], r15w
0x14000d425  mov     ecx, [rbx+5Ch]
0x14000d428  movzx   eax, [rsp+1F0h+var_1A0.Length]
0x14000d42d  test    ecx, ecx
0x14000d42f  jz      short loc_14000D4AB
0x14000d431  shr     eax, 1
0x14000d433  inc     eax
0x14000d435  cmp     ecx, eax
0x14000d437  jnz     loc_14000D4FA
0x14000d43d  movzx   r8d, [rsp+1F0h+var_1A0.Length]; Size
0x14000d443  mov     rcx, rdi; void *
0x14000d446  mov     rdx, [rsp+1F0h+var_1A0.Buffer]; Src
0x14000d44b  call    memmove
0x14000d450  mov     ecx, [rbx+5Ch]
0x14000d453  mov     [rdi+rcx*2-2], r15w
0x14000d459  cmp     [rsp+1F0h+Src+8], r15
0x14000d45e  jz      short loc_14000D471
0x14000d460  lea     rcx, [rsp+1F0h+Src]; UnicodeString
0x14000d465  call    cs:__imp_RtlFreeUnicodeString
0x14000d46c  nop     dword ptr [rax+rax+00h]
0x14000d471  cmp     [rsp+1F0h+var_1A0.Buffer], r15
0x14000d476  jz      short loc_14000D489
0x14000d478  lea     rcx, [rsp+1F0h+var_1A0]; UnicodeString
0x14000d47d  call    cs:__imp_RtlFreeUnicodeString
0x14000d484  nop     dword ptr [rax+rax+00h]
0x14000d489  xor     eax, eax
0x14000d48b  jmp     loc_14000D2C6
0x14000d490  lea     rcx, [rsp+1F0h+UnicodeString]; UnicodeString
0x14000d495  call    cs:__imp_RtlFreeUnicodeString
0x14000d49c  nop     dword ptr [rax+rax+00h]
0x14000d4a1  mov     eax, 0C0000017h
0x14000d4a6  jmp     loc_14000D2C6
0x14000d4ab  test    ax, ax
0x14000d4ae  jnz     loc_14000D534
0x14000d4b4  mov     eax, r15d
0x14000d4b7  mov     [rbx+5Ch], eax
0x14000d4ba  jmp     short loc_14000D459
0x14000d4bc  test    ax, ax
0x14000d4bf  jz      short loc_14000D4CD
0x14000d4c1  shr     eax, 1
0x14000d4c3  inc     eax
0x14000d4c5  mov     [rbx+58h], eax
0x14000d4c8  jmp     loc_14000D425
0x14000d4cd  mov     eax, r15d
0x14000d4d0  jmp     short loc_14000D4C5
0x14000d4d2  cmp     cs:gbOSTestSigningEnabled, r15b
0x14000d4d9  jnz     loc_14000D0C6
0x14000d4df  mov     eax, 0C0000022h
0x14000d4e4  jmp     loc_14000D2C6
0x14000d4e9  test    esi, esi
0x14000d4eb  jns     loc_14000D3E6
0x14000d4f1  mov     [rbx+54h], r15d
0x14000d4f5  jmp     loc_14000D2E9
0x14000d4fa  cmp     [rsp+1F0h+Src+8], r15
0x14000d4ff  jz      short loc_14000D512
0x14000d501  lea     rcx, [rsp+1F0h+Src]; UnicodeString
0x14000d506  call    cs:__imp_RtlFreeUnicodeString
0x14000d50d  nop     dword ptr [rax+rax+00h]
0x14000d512  cmp     [rsp+1F0h+var_1A0.Buffer], r15
0x14000d517  jz      short loc_14000D52A
0x14000d519  lea     rcx, [rsp+1F0h+var_1A0]; UnicodeString
0x14000d51e  call    cs:__imp_RtlFreeUnicodeString
0x14000d525  nop     dword ptr [rax+rax+00h]
0x14000d52a  mov     eax, 0C000000Dh
0x14000d52f  jmp     loc_14000D2C6
0x14000d534  shr     eax, 1
0x14000d536  inc     eax
0x14000d538  jmp     loc_14000D4B7
```
