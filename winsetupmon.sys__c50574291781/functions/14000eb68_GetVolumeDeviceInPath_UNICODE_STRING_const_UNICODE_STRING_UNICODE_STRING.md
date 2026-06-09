# GetVolumeDeviceInPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x14000eb68`
- end: `0x14000f343`
- name: `?GetVolumeDeviceInPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z`
- size: `2011`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001a94`
- `0x14000e1d0`
- `0x14000f34c`

## callees

- `0x140008138`
- `0x14000eb68`
- `0x14000f900`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ec52`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ee2b`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ee80`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000eed5`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ef2a`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f003`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f095`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f18d`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f305`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ec52`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ee2b`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ee80`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000eed5`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ef2a`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f003`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f095`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f18d`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f305`
- `ntoskrnl!RtlGUIDFromString` at `0x14000f143`
- `ntoskrnl!RtlGUIDFromString` at `0x14000f143`

## string_xrefs

- `0x14000ebba`: `\Device\HarddiskVolumeShadowCopy`

## pseudocode

```c
__int64 __fastcall GetVolumeDeviceInPath(
        PCUNICODE_STRING String2,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3)
{
  unsigned __int16 i; // bx
  unsigned __int64 v7; // r8
  wchar_t *v8; // r9
  unsigned __int16 v9; // cx
  unsigned __int16 v10; // dx
  unsigned __int64 v11; // r10
  wchar_t v12; // cx
  unsigned __int16 v13; // dx
  wchar_t v14; // cx
  wchar_t v15; // cx
  unsigned __int16 v16; // dx
  unsigned __int16 Length; // dx
  wchar_t *Buffer; // r8
  wchar_t v19; // cx
  __int64 v20; // r10
  int v21; // ecx
  wchar_t *v22; // rax
  GUID v23; // xmm0
  wchar_t *v24; // rcx
  unsigned __int16 v25; // ax
  unsigned __int16 v26; // dx
  wchar_t *v27; // r8
  __int64 v28; // r10
  int v29; // r9d
  unsigned __int64 v30; // r9
  wchar_t *v31; // r8
  unsigned __int64 v32; // rcx
  wchar_t v33; // r10
  unsigned __int16 v34; // dx
  unsigned __int16 v35; // dx
  unsigned __int64 v36; // rcx
  unsigned __int16 v37; // ax
  UNICODE_STRING GuidString; // [rsp+20h] [rbp-89h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-79h] BYREF
  UNICODE_STRING v41; // [rsp+40h] [rbp-69h] BYREF
  UNICODE_STRING v42; // [rsp+50h] [rbp-59h] BYREF
  UNICODE_STRING v43; // [rsp+60h] [rbp-49h] BYREF
  UNICODE_STRING v44; // [rsp+70h] [rbp-39h] BYREF
  UNICODE_STRING v45; // [rsp+80h] [rbp-29h] BYREF
  UNICODE_STRING v46; // [rsp+90h] [rbp-19h] BYREF
  UNICODE_STRING v47; // [rsp+A0h] [rbp-9h] BYREF
  UNICODE_STRING v48; // [rsp+B0h] [rbp+7h] BYREF
  GUID Guid; // [rsp+C0h] [rbp+17h] BYREF

  *(_QWORD *)&v48.Length = 1179664;
  v48.Buffer = L"\\Device\\";
  *(_QWORD *)&String1.Length = 1572886;
  String1.Buffer = L"\\Device\\Mup";
  *(_QWORD *)&v41.Length = 4325440;
  v41.Buffer = L"\\Device\\HarddiskVolumeShadowCopy";
  *(_QWORD *)&v42.Length = 3014700;
  v42.Buffer = L"\\Device\\HarddiskVolume";
  *(_QWORD *)&v43.Length = 1835034;
  v43.Buffer = L"\\Device\\CdRom";
  *(_QWORD *)&v44.Length = 2228256;
  v44.Buffer = L"\\Device\\Harddisk";
  *(_QWORD *)&v45.Length = 1966108;
  v45.Buffer = L"\\Device\\Volume";
  *(_QWORD *)&v46.Length = 2097182;
  v46.Buffer = L"\\Device\\Ramdisk";
  v47.Buffer = L"\\Device\\RdpDr";
  *(_QWORD *)&v47.Length = 1835034;
  if ( !RtlPrefixUnicodeString(&String1, String2, 1u) )
  {
    if ( RtlPrefixUnicodeString(&v41, String2, 1u) )
    {
      for ( i = v41.Length; i < String2->Length; i += 2 )
      {
        if ( (unsigned __int16)(String2->Buffer[(unsigned __int64)i >> 1] - 48) > 9u )
          break;
      }
      goto LABEL_115;
    }
    if ( RtlPrefixUnicodeString(&v42, String2, 1u) )
    {
      for ( i = v42.Length; i < String2->Length; i += 2 )
      {
        if ( (unsigned __int16)(String2->Buffer[(unsigned __int64)i >> 1] - 48) > 9u )
          break;
      }
      goto LABEL_115;
    }
    if ( RtlPrefixUnicodeString(&v43, String2, 1u) )
    {
      for ( i = v43.Length; i < String2->Length; i += 2 )
      {
        if ( (unsigned __int16)(String2->Buffer[(unsigned __int64)i >> 1] - 48) > 9u )
          break;
      }
      goto LABEL_115;
    }
    if ( RtlPrefixUnicodeString(&v44, String2, 1u) )
    {
      i = v44.Length;
      Length = String2->Length;
      if ( v44.Length >= String2->Length )
        return 3221225659LL;
      Buffer = String2->Buffer;
      while ( (unsigned __int16)(Buffer[(unsigned __int64)i >> 1] - 48) <= 9u )
      {
        i += 2;
        if ( i >= Length )
          return 3221225659LL;
      }
      if ( Buffer[(unsigned __int64)i >> 1] != 92 )
        return 3221225659LL;
      do
      {
        i += 2;
        if ( i >= Length )
          break;
        v19 = Buffer[(unsigned __int64)i >> 1];
      }
      while ( (unsigned __int16)(v19 - 97) <= 0x19u || (unsigned __int16)(v19 - 65) <= 0x19u );
      if ( i >= Length || (unsigned __int16)(Buffer[(unsigned __int64)i >> 1] - 48) > 9u )
        return 3221225659LL;
      do
      {
        if ( (unsigned __int16)(Buffer[(unsigned __int64)i >> 1] - 48) > 9u )
          break;
        i += 2;
      }
      while ( i < Length );
      goto LABEL_115;
    }
    if ( RtlPrefixUnicodeString(&v45, String2, 1u) )
    {
      i = v45.Length;
      if ( v45.Length < String2->Length )
      {
        v20 = 0x3FFFFFF01FF9LL;
        do
        {
          v21 = String2->Buffer[(unsigned __int64)i >> 1];
          if ( (unsigned __int16)(v21 - 97) > 0x1Au
            && ((unsigned __int16)(v21 - 45) > 0x2Du || !_bittest64(&v20, (unsigned int)(v21 - 45)))
            && (_WORD)v21 != 125 )
          {
            break;
          }
          i += 2;
        }
        while ( i < String2->Length );
      }
      v22 = String2->Buffer;
      v23 = 0;
      *(_QWORD *)&GuidString.Length = 0;
      v24 = &v22[(unsigned __int64)v45.Length >> 1];
      v25 = i - v45.Length;
      GuidString.Buffer = v24;
    }
    else
    {
      if ( !RtlPrefixUnicodeString(&v46, String2, 1u) )
      {
        if ( RtlPrefixUnicodeString(&v47, String2, 1u) )
        {
          v30 = String2->Length;
          if ( (unsigned __int64)v47.Length + 8 < v30 )
          {
            v31 = String2->Buffer;
            v32 = (unsigned __int64)v47.Length >> 1;
            if ( v31[v32] == 92 && v31[v32 + 1] == 59 )
            {
              v33 = v31[v32 + 2];
              if ( ((unsigned __int16)(v33 - 97) <= 0x19u || (unsigned __int16)(v33 - 65) <= 0x19u)
                && v31[v32 + 3] == 58 )
              {
                v34 = v47.Length + 8;
                if ( (unsigned __int16)(v47.Length + 8) < (unsigned __int16)v30
                  && (unsigned __int16)(v31[(unsigned __int64)v34 >> 1] - 48) <= 9u )
                {
                  while ( 1 )
                  {
                    v34 += 2;
                    if ( v34 >= (unsigned __int16)v30 )
                      break;
                    if ( (unsigned __int16)(v31[(unsigned __int64)v34 >> 1] - 48) > 9u )
                    {
                      if ( v31[(unsigned __int64)v34 >> 1] != 92 )
                        return 3221225659LL;
                      v35 = v34 + 2;
                      if ( v35 >= (unsigned __int16)v30 )
                        return 3221225659LL;
                      while ( 1 )
                      {
                        i = v35 + 2;
                        if ( v31[(unsigned __int64)v35 >> 1] == 92 )
                          break;
                        v35 += 2;
                        if ( i >= (unsigned __int16)v30 )
                          return 3221225659LL;
                      }
                      while ( i < (unsigned __int16)v30 && v31[(unsigned __int64)i >> 1] != 92 )
                        i += 2;
                      goto LABEL_115;
                    }
                  }
                }
              }
            }
          }
        }
        else if ( RtlPrefixUnicodeString(&v48, String2, 1u) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        return 3221225659LL;
      }
      v26 = String2->Length;
      i = v46.Length;
      if ( v46.Length >= String2->Length )
        goto LABEL_115;
      v27 = String2->Buffer;
      if ( v27[(unsigned __int64)v46.Length >> 1] != 123 )
      {
        do
        {
          if ( (unsigned __int16)(v27[(unsigned __int64)i >> 1] - 48) > 9u )
            break;
          i += 2;
        }
        while ( i < v26 );
        goto LABEL_115;
      }
      v28 = 0x3FFFFFF01FF9LL;
      do
      {
        v29 = v27[(unsigned __int64)i >> 1];
        if ( (unsigned __int16)(v29 - 97) > 0x1Au
          && ((unsigned __int16)(v29 - 45) > 0x2Du || !_bittest64(&v28, (unsigned int)(v29 - 45)))
          && (_WORD)v29 != 125 )
        {
          break;
        }
        i += 2;
      }
      while ( i < v26 );
      v23 = 0;
      *(_QWORD *)&GuidString.Length = 0;
      GuidString.Buffer = &v27[(unsigned __int64)v46.Length >> 1];
      v25 = i - v46.Length;
    }
    GuidString.MaximumLength = v25;
    GuidString.Length = v25;
    Guid = v23;
    if ( RtlGUIDFromString(&GuidString, &Guid) >= 0 )
      goto LABEL_115;
    return 3221225659LL;
  }
  i = String1.Length;
  v7 = String2->Length;
  if ( String1.Length >= (unsigned __int16)v7 )
  {
    if ( String1.Length == (_WORD)v7 )
      goto LABEL_115;
    return 3221225659LL;
  }
  v8 = String2->Buffer;
  if ( v8[(unsigned __int64)String1.Length >> 1] != 92 )
    return 3221225659LL;
  v9 = String1.Length + 2;
  if ( (unsigned __int16)(String1.Length + 2) < (unsigned __int16)v7 )
  {
    if ( v8[(unsigned __int64)v9 >> 1] == 59 )
    {
      do
        v9 += 2;
      while ( v9 < (unsigned __int16)v7 && v8[(unsigned __int64)v9 >> 1] != 92 );
      i = v9;
    }
    else if ( v9 < (unsigned __int16)v7 )
    {
      while ( 1 )
      {
        v10 = v9 + 2;
        if ( v8[(unsigned __int64)v9 >> 1] == 92 )
          break;
        v9 += 2;
        if ( v10 >= (unsigned __int16)v7 )
          goto LABEL_115;
      }
      if ( (unsigned __int64)v10 + 6 < v7 )
      {
        v11 = (unsigned __int64)v10 >> 1;
        if ( v8[v11] == 59 )
        {
          v12 = v8[v11 + 1];
          if ( ((unsigned __int16)(v12 - 97) <= 0x19u || (unsigned __int16)(v12 - 65) <= 0x19u) && v8[v11 + 2] == 58 )
          {
            v13 = v10 + 6;
            if ( v13 >= (unsigned __int16)v7 )
              return 3221225659LL;
            v14 = v8[(unsigned __int64)v13 >> 1];
            if ( (unsigned __int16)(v14 - 48) > 9u
              && (unsigned __int16)(v14 - 97) > 5u
              && (unsigned __int16)(v14 - 65) > 5u )
            {
              return 3221225659LL;
            }
            do
            {
              v13 += 2;
              if ( v13 >= (unsigned __int16)v7 )
                break;
              v15 = v8[(unsigned __int64)v13 >> 1];
            }
            while ( (unsigned __int16)(v15 - 48) <= 9u
                 || (unsigned __int16)(v15 - 97) <= 5u
                 || (unsigned __int16)(v15 - 65) <= 5u );
            if ( v13 >= (unsigned __int16)v7 )
              return 3221225659LL;
            if ( v8[(unsigned __int64)v13 >> 1] != 92 )
              return 3221225659LL;
            v16 = v13 + 2;
            if ( v16 >= (unsigned __int16)v7 )
              return 3221225659LL;
            while ( 1 )
            {
              i = v16 + 2;
              if ( v8[(unsigned __int64)v16 >> 1] == 92 )
                break;
              v16 += 2;
              if ( i >= (unsigned __int16)v7 )
                return 3221225659LL;
            }
            while ( i < (unsigned __int16)v7 && v8[(unsigned __int64)i >> 1] != 92 )
              i += 2;
          }
        }
      }
    }
  }
LABEL_115:
  v36 = (unsigned __int64)i >> 1;
  if ( i < String2->Length && String2->Buffer[v36] != 92 )
    return 3221225659LL;
  a2->Buffer = String2->Buffer;
  a2->MaximumLength = i;
  a2->Length = i;
  if ( i >= String2->Length )
  {
    *a3 = 0;
  }
  else
  {
    a3->Buffer = &String2->Buffer[v36];
    v37 = String2->Length - a2->Length;
    a3->MaximumLength = v37;
    a3->Length = v37;
  }
  return 0;
}

```

## disassembly

```asm
0x14000eb68  mov     [rsp-8+arg_18], rbx
0x14000eb6d  push    rbp
0x14000eb6e  push    rsi
0x14000eb6f  push    rdi
0x14000eb70  push    r12
0x14000eb72  push    r14
0x14000eb74  lea     rbp, [rsp-37h]
0x14000eb79  sub     rsp, 0E0h
0x14000eb80  mov     rax, cs:__security_cookie
0x14000eb87  xor     rax, rsp
0x14000eb8a  mov     [rbp+57h+var_30], rax
0x14000eb8e  lea     rax, aDevice; "\\Device\\"
0x14000eb95  mov     qword ptr [rbp+57h+var_50.Length], 120010h
0x14000eb9d  mov     [rbp+57h+var_50.Buffer], rax
0x14000eba1  mov     r14, rdx
0x14000eba4  lea     rax, aDeviceMup; "\\Device\\Mup"
0x14000ebab  mov     qword ptr [rbp+57h+String1.Length], 180016h
0x14000ebb3  mov     [rbp+57h+String1.Buffer], rax
0x14000ebb7  mov     rsi, r8
0x14000ebba  lea     rax, aDeviceHarddisk_0; "\\Device\\HarddiskVolumeShadowCopy"
0x14000ebc1  mov     qword ptr [rbp+57h+var_C0.Length], 420040h
0x14000ebc9  mov     [rbp+57h+var_C0.Buffer], rax
0x14000ebcd  mov     rdi, rcx
0x14000ebd0  lea     rax, aDeviceHarddisk_1; "\\Device\\HarddiskVolume"
0x14000ebd7  mov     qword ptr [rbp+57h+var_B0.Length], 2E002Ch
0x14000ebdf  mov     [rbp+57h+var_B0.Buffer], rax
0x14000ebe3  mov     rdx, rcx; String2
0x14000ebe6  lea     rax, aDeviceCdrom; "\\Device\\CdRom"
0x14000ebed  mov     qword ptr [rbp+57h+var_A0.Length], 1C001Ah
0x14000ebf5  mov     [rbp+57h+var_A0.Buffer], rax
0x14000ebf9  lea     rcx, [rbp+57h+String1]; String1
0x14000ebfd  lea     rax, aDeviceHarddisk; "\\Device\\Harddisk"
0x14000ec04  mov     qword ptr [rbp+57h+var_90.Length], 220020h
0x14000ec0c  mov     [rbp+57h+var_90.Buffer], rax
0x14000ec10  mov     r8b, 1; CaseInSensitive
0x14000ec13  lea     rax, aDeviceVolume; "\\Device\\Volume"
0x14000ec1a  mov     qword ptr [rbp+57h+var_80.Length], 1E001Ch
0x14000ec22  mov     [rbp+57h+var_80.Buffer], rax
0x14000ec26  mov     r12d, 1Ah
0x14000ec2c  lea     rax, aDeviceRamdisk; "\\Device\\Ramdisk"
0x14000ec33  mov     qword ptr [rbp+57h+var_70.Length], 20001Eh
0x14000ec3b  mov     [rbp+57h+var_70.Buffer], rax
0x14000ec3f  lea     rax, aDeviceRdpdr; "\\Device\\RdpDr"
0x14000ec46  mov     [rbp+57h+var_60.Buffer], rax
0x14000ec4a  mov     qword ptr [rbp+57h+var_60.Length], 1C001Ah
0x14000ec52  call    cs:__imp_RtlPrefixUnicodeString
0x14000ec59  nop     dword ptr [rax+rax+00h]
0x14000ec5e  test    al, al
0x14000ec60  jz      loc_14000EE21
0x14000ec66  movzx   ebx, [rbp+57h+String1.Length]
0x14000ec6a  movzx   r8d, word ptr [rdi]
0x14000ec6e  cmp     bx, r8w
0x14000ec72  jnb     loc_14000EE16
0x14000ec78  mov     r9, [rdi+8]
0x14000ec7c  mov     eax, ebx
0x14000ec7e  shr     rax, 1
0x14000ec81  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x14000ec87  jnz     loc_14000F31A
0x14000ec8d  lea     ecx, [rbx+2]
0x14000ec90  cmp     cx, r8w
0x14000ec94  jnb     loc_14000F2A9
0x14000ec9a  movzx   eax, cx
0x14000ec9d  shr     rax, 1
0x14000eca0  cmp     word ptr [r9+rax*2], 3Bh ; ';'
0x14000eca6  jz      short loc_14000ECDF
0x14000eca8  cmp     cx, r8w
0x14000ecac  jnb     loc_14000F2A9
0x14000ecb2  movzx   eax, cx
0x14000ecb5  lea     edx, [rcx+2]
0x14000ecb8  shr     rax, 1
0x14000ecbb  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x14000ecc1  jz      short loc_14000ECF1
0x14000ecc3  movzx   ecx, dx
0x14000ecc6  cmp     dx, r8w
0x14000ecca  jb      short loc_14000ECB2
0x14000eccc  jmp     loc_14000F2A9
0x14000ecd1  movzx   eax, cx
0x14000ecd4  shr     rax, 1
0x14000ecd7  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x14000ecdd  jz      short loc_14000ECE9
0x14000ecdf  add     cx, 2
0x14000ece3  cmp     cx, r8w
0x14000ece7  jb      short loc_14000ECD1
0x14000ece9  movzx   ebx, cx
0x14000ecec  jmp     loc_14000F2A9
0x14000ecf1  movzx   r10d, dx
0x14000ecf5  lea     rcx, [r10+6]
0x14000ecf9  cmp     rcx, r8
0x14000ecfc  jnb     loc_14000F2A9
0x14000ed02  shr     r10, 1
0x14000ed05  cmp     word ptr [r9+r10*2], 3Bh ; ';'
0x14000ed0b  jnz     loc_14000F2A9
0x14000ed11  movzx   ecx, word ptr [r9+r10*2+2]
0x14000ed17  lea     eax, [rcx-61h]
0x14000ed1a  cmp     ax, 19h
0x14000ed1e  jbe     short loc_14000ED2E
0x14000ed20  sub     cx, 41h ; 'A'
0x14000ed24  cmp     cx, 19h
0x14000ed28  ja      loc_14000F2A9
0x14000ed2e  cmp     word ptr [r9+r10*2+4], 3Ah ; ':'
0x14000ed35  jnz     loc_14000F2A9
0x14000ed3b  add     dx, 6
0x14000ed3f  cmp     dx, r8w
0x14000ed43  jnb     loc_14000F31A
0x14000ed49  movzx   eax, dx
0x14000ed4c  mov     r10w, 5
0x14000ed51  shr     rax, 1
0x14000ed54  movzx   ecx, word ptr [r9+rax*2]
0x14000ed59  lea     eax, [rcx-30h]
0x14000ed5c  cmp     ax, 9
0x14000ed60  jbe     short loc_14000EDA2
0x14000ed62  lea     eax, [rcx-61h]
0x14000ed65  cmp     ax, r10w
0x14000ed69  jbe     short loc_14000EDA2
0x14000ed6b  sub     cx, 41h ; 'A'
0x14000ed6f  cmp     cx, r10w
0x14000ed73  ja      loc_14000F31A
0x14000ed79  jmp     short loc_14000EDA2
0x14000ed7b  movzx   eax, dx
0x14000ed7e  shr     rax, 1
0x14000ed81  movzx   ecx, word ptr [r9+rax*2]
0x14000ed86  lea     eax, [rcx-30h]
0x14000ed89  cmp     ax, 9
0x14000ed8d  jbe     short loc_14000EDA2
0x14000ed8f  lea     eax, [rcx-61h]
0x14000ed92  cmp     ax, r10w
0x14000ed96  jbe     short loc_14000EDA2
0x14000ed98  sub     cx, 41h ; 'A'
0x14000ed9c  cmp     cx, r10w
0x14000eda0  ja      short loc_14000EDAC
0x14000eda2  add     dx, 2
0x14000eda6  cmp     dx, r8w
0x14000edaa  jb      short loc_14000ED7B
0x14000edac  cmp     dx, r8w
0x14000edb0  jnb     loc_14000F31A
0x14000edb6  movzx   eax, dx
0x14000edb9  shr     rax, 1
0x14000edbc  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x14000edc2  jnz     loc_14000F31A
0x14000edc8  add     dx, 2
0x14000edcc  cmp     dx, r8w
0x14000edd0  jnb     loc_14000F31A
0x14000edd6  movzx   eax, dx
0x14000edd9  lea     ebx, [rdx+2]
0x14000eddc  shr     rax, 1
0x14000eddf  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x14000ede5  jz      short loc_14000EE0B
0x14000ede7  movzx   edx, bx
0x14000edea  cmp     bx, r8w
0x14000edee  jb      short loc_14000EDD6
0x14000edf0  jmp     loc_14000F31A
0x14000edf5  movzx   eax, bx
0x14000edf8  shr     rax, 1
0x14000edfb  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x14000ee01  jz      loc_14000F2A9
0x14000ee07  add     bx, 2
0x14000ee0b  cmp     bx, r8w
0x14000ee0f  jb      short loc_14000EDF5
0x14000ee11  jmp     loc_14000F2A9
0x14000ee16  jnz     loc_14000F31A
0x14000ee1c  jmp     loc_14000F2A9
0x14000ee21  mov     r8b, 1; CaseInSensitive
0x14000ee24  lea     rcx, [rbp+57h+var_C0]; String1
0x14000ee28  mov     rdx, rdi; String2
0x14000ee2b  call    cs:__imp_RtlPrefixUnicodeString
0x14000ee32  nop     dword ptr [rax+rax+00h]
0x14000ee37  test    al, al
0x14000ee39  jz      short loc_14000EE76
0x14000ee3b  movzx   ebx, [rbp+57h+var_C0.Length]
0x14000ee3f  movzx   edx, word ptr [rdi]
0x14000ee42  cmp     bx, dx
0x14000ee45  jnb     loc_14000F2A9
0x14000ee4b  mov     r8, [rdi+8]
0x14000ee4f  movzx   eax, bx
0x14000ee52  shr     rax, 1
0x14000ee55  movzx   ecx, word ptr [r8+rax*2]
0x14000ee5a  sub     cx, 30h ; '0'
0x14000ee5e  cmp     cx, 9
0x14000ee62  ja      loc_14000F2A9
0x14000ee68  add     bx, 2
0x14000ee6c  cmp     bx, dx
0x14000ee6f  jb      short loc_14000EE4F
0x14000ee71  jmp     loc_14000F2A9
0x14000ee76  mov     r8b, 1; CaseInSensitive
0x14000ee79  lea     rcx, [rbp+57h+var_B0]; String1
0x14000ee7d  mov     rdx, rdi; String2
0x14000ee80  call    cs:__imp_RtlPrefixUnicodeString
0x14000ee87  nop     dword ptr [rax+rax+00h]
0x14000ee8c  test    al, al
0x14000ee8e  jz      short loc_14000EECB
0x14000ee90  movzx   ebx, [rbp+57h+var_B0.Length]
0x14000ee94  movzx   edx, word ptr [rdi]
0x14000ee97  cmp     bx, dx
0x14000ee9a  jnb     loc_14000F2A9
0x14000eea0  mov     r8, [rdi+8]
0x14000eea4  movzx   eax, bx
0x14000eea7  shr     rax, 1
0x14000eeaa  movzx   ecx, word ptr [r8+rax*2]
0x14000eeaf  sub     cx, 30h ; '0'
0x14000eeb3  cmp     cx, 9
0x14000eeb7  ja      loc_14000F2A9
0x14000eebd  add     bx, 2
0x14000eec1  cmp     bx, dx
0x14000eec4  jb      short loc_14000EEA4
0x14000eec6  jmp     loc_14000F2A9
0x14000eecb  mov     r8b, 1; CaseInSensitive
0x14000eece  lea     rcx, [rbp+57h+var_A0]; String1
0x14000eed2  mov     rdx, rdi; String2
0x14000eed5  call    cs:__imp_RtlPrefixUnicodeString
0x14000eedc  nop     dword ptr [rax+rax+00h]
0x14000eee1  test    al, al
0x14000eee3  jz      short loc_14000EF20
0x14000eee5  movzx   ebx, [rbp+57h+var_A0.Length]
0x14000eee9  movzx   edx, word ptr [rdi]
0x14000eeec  cmp     bx, dx
0x14000eeef  jnb     loc_14000F2A9
0x14000eef5  mov     r8, [rdi+8]
0x14000eef9  movzx   eax, bx
0x14000eefc  shr     rax, 1
0x14000eeff  movzx   ecx, word ptr [r8+rax*2]
0x14000ef04  sub     cx, 30h ; '0'
0x14000ef08  cmp     cx, 9
0x14000ef0c  ja      loc_14000F2A9
0x14000ef12  add     bx, 2
0x14000ef16  cmp     bx, dx
0x14000ef19  jb      short loc_14000EEF9
0x14000ef1b  jmp     loc_14000F2A9
0x14000ef20  mov     r8b, 1; CaseInSensitive
0x14000ef23  lea     rcx, [rbp+57h+var_90]; String1
0x14000ef27  mov     rdx, rdi; String2
0x14000ef2a  call    cs:__imp_RtlPrefixUnicodeString
0x14000ef31  nop     dword ptr [rax+rax+00h]
0x14000ef36  test    al, al
0x14000ef38  jz      loc_14000EFF9
0x14000ef3e  movzx   ebx, [rbp+57h+var_90.Length]
0x14000ef42  movzx   edx, word ptr [rdi]
0x14000ef45  cmp     bx, dx
0x14000ef48  jnb     loc_14000F31A
0x14000ef4e  mov     r8, [rdi+8]
0x14000ef52  movzx   eax, bx
0x14000ef55  shr     rax, 1
0x14000ef58  movzx   ecx, word ptr [r8+rax*2]
0x14000ef5d  sub     cx, 30h ; '0'
0x14000ef61  cmp     cx, 9
0x14000ef65  ja      short loc_14000EF75
0x14000ef67  add     bx, 2
0x14000ef6b  cmp     bx, dx
0x14000ef6e  jb      short loc_14000EF52
0x14000ef70  jmp     loc_14000F31A
0x14000ef75  movzx   eax, bx
0x14000ef78  shr     rax, 1
0x14000ef7b  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x14000ef81  jnz     loc_14000F31A
0x14000ef87  jmp     short loc_14000EFA7
0x14000ef89  movzx   eax, bx
0x14000ef8c  shr     rax, 1
0x14000ef8f  movzx   ecx, word ptr [r8+rax*2]
0x14000ef94  lea     eax, [rcx-61h]
0x14000ef97  cmp     ax, 19h
0x14000ef9b  jbe     short loc_14000EFA7
0x14000ef9d  sub     cx, 41h ; 'A'
0x14000efa1  cmp     cx, 19h
0x14000efa5  ja      short loc_14000EFB0
0x14000efa7  add     bx, 2
0x14000efab  cmp     bx, dx
0x14000efae  jb      short loc_14000EF89
0x14000efb0  cmp     bx, dx
0x14000efb3  jnb     loc_14000F31A
0x14000efb9  movzx   eax, bx
0x14000efbc  shr     rax, 1
0x14000efbf  movzx   ecx, word ptr [r8+rax*2]
0x14000efc4  sub     cx, 30h ; '0'
0x14000efc8  cmp     cx, 9
0x14000efcc  ja      loc_14000F31A
0x14000efd2  movzx   eax, bx
0x14000efd5  shr     rax, 1
0x14000efd8  movzx   ecx, word ptr [r8+rax*2]
0x14000efdd  sub     cx, 30h ; '0'
0x14000efe1  cmp     cx, 9
0x14000efe5  ja      loc_14000F2A9
0x14000efeb  add     bx, 2
0x14000efef  cmp     bx, dx
0x14000eff2  jb      short loc_14000EFD2
0x14000eff4  jmp     loc_14000F2A9
0x14000eff9  mov     r8b, 1; CaseInSensitive
0x14000effc  lea     rcx, [rbp+57h+var_80]; String1
0x14000f000  mov     rdx, rdi; String2
0x14000f003  call    cs:__imp_RtlPrefixUnicodeString
0x14000f00a  nop     dword ptr [rax+rax+00h]
0x14000f00f  test    al, al
0x14000f011  jz      short loc_14000F08B
0x14000f013  movzx   edx, [rbp+57h+var_80.Length]
0x14000f017  movzx   r8d, word ptr [rdi]
0x14000f01b  movzx   ebx, dx
0x14000f01e  cmp     dx, r8w
0x14000f022  jnb     short loc_14000F065
0x14000f024  mov     r9, [rdi+8]
0x14000f028  mov     r10, 3FFFFFF01FF9h
0x14000f032  movzx   eax, bx
0x14000f035  shr     rax, 1
  ... truncated ...
```
