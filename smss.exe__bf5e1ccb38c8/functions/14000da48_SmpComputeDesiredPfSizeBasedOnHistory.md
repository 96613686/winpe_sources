# SmpComputeDesiredPfSizeBasedOnHistory

- ea: `0x14000da48`
- end: `0x14000dd16`
- name: `SmpComputeDesiredPfSizeBasedOnHistory`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000d92c`

## callees

- `0x14000d4c0`
- `0x14000da48`
- `0x14001cc11`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x14000dc14`
- `ntdll!NtClose` at `0x14000dc14`
- `ntdll!NtOpenKey` at `0x14000dbdd`
- `ntdll!NtOpenKey` at `0x14000dbdd`
- `ntdll!NtQueryValueKey` at `0x14000daf1`
- `ntdll!NtQueryValueKey` at `0x14000dc07`
- `ntdll!NtQueryValueKey` at `0x14000daf1`
- `ntdll!NtQueryValueKey` at `0x14000dc07`
- `ntdll!RtlSecondsSince1970ToTime` at `0x14000dc34`
- `ntdll!RtlSecondsSince1970ToTime` at `0x14000dc34`
- `ntdll!qsort` at `0x14000dccd`
- `ntdll!qsort` at `0x14000dccd`

## string_xrefs

- `0x14000da86`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion`
- `0x14000da96`: `InstallDate`
- `0x14000dc58`: `SmpComputeDesiredPfSizeBasedOnHistory`

## pseudocode

```c
__int64 SmpComputeDesiredPfSizeBasedOnHistory()
{
  __int64 v0; // rdx
  size_t *v1; // rcx
  ULONG *p_ElapsedSeconds; // rax
  __int128 v3; // xmm1
  __int128 v4; // xmm0
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  ULONG v13; // eax
  unsigned int v14; // edi
  NTSTATUS v15; // eax
  NTSTATUS v16; // ebx
  __int64 v17; // rbx
  unsigned int v18; // eax
  unsigned int v20; // ebx
  unsigned int v21; // edi
  size_t v22; // rsi
  unsigned __int64 v23; // rcx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  union _LARGE_INTEGER Time; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v27[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  _DWORD KeyValueInformation[2]; // [rsp+A0h] [rbp-60h] BYREF
  ULONG ElapsedSeconds; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD Base[240]; // [rsp+470h] [rbp+370h] BYREF

  v27[0] = 8257660;
  *(_QWORD *)&ValueName.Length = 1572886;
  v27[1] = L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion";
  ResultLength = 0;
  ValueName.Buffer = L"InstallDate";
  Time.QuadPart = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  memset_0(KeyValueInformation, 0, 0x3CCu);
  if ( NtQueryValueKey(
         SmpMmKey,
         (PUNICODE_STRING)&SmpPagefileUsageValue,
         KeyValuePartialInformationAlign64,
         KeyValueInformation,
         0x3CCu,
         &ResultLength) >= 0
    && KeyValueInformation[0] == 3
    && KeyValueInformation[1] == 964
    && ElapsedSeconds )
  {
    v0 = 7;
    v1 = &NumOfElements;
    p_ElapsedSeconds = &ElapsedSeconds;
    do
    {
      v3 = *((_OWORD *)p_ElapsedSeconds + 1);
      *(_OWORD *)v1 = *(_OWORD *)p_ElapsedSeconds;
      v4 = *((_OWORD *)p_ElapsedSeconds + 2);
      *((_OWORD *)v1 + 1) = v3;
      v5 = *((_OWORD *)p_ElapsedSeconds + 3);
      *((_OWORD *)v1 + 2) = v4;
      v6 = *((_OWORD *)p_ElapsedSeconds + 4);
      *((_OWORD *)v1 + 3) = v5;
      v7 = *((_OWORD *)p_ElapsedSeconds + 5);
      *((_OWORD *)v1 + 4) = v6;
      v8 = *((_OWORD *)p_ElapsedSeconds + 6);
      *((_OWORD *)v1 + 5) = v7;
      v9 = *((_OWORD *)p_ElapsedSeconds + 7);
      p_ElapsedSeconds += 32;
      *((_OWORD *)v1 + 6) = v8;
      *((_OWORD *)v1 + 7) = v9;
      v1 += 16;
      --v0;
    }
    while ( v0 );
    v10 = *((_OWORD *)p_ElapsedSeconds + 1);
    *(_OWORD *)v1 = *(_OWORD *)p_ElapsedSeconds;
    v11 = *((_OWORD *)p_ElapsedSeconds + 2);
    *((_OWORD *)v1 + 1) = v10;
    v12 = *((_OWORD *)p_ElapsedSeconds + 3);
    v13 = p_ElapsedSeconds[16];
    *((_OWORD *)v1 + 2) = v11;
    *((_OWORD *)v1 + 3) = v12;
    *((_DWORD *)v1 + 16) = v13;
  }
  else
  {
    LODWORD(NumOfElements) = 0;
  }
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v27;
  v14 = 48;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v15 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v15 < 0 )
  {
    SmpLogFailure("SmpComputeDesiredPfSizeBasedOnHistory", 3522, (unsigned int)v15);
  }
  else
  {
    v16 = NtQueryValueKey(
            KeyHandle,
            &ValueName,
            KeyValuePartialInformationAlign64,
            KeyValueInformation,
            0x3CCu,
            &ResultLength);
    NtClose(KeyHandle);
    if ( v16 >= 0 && KeyValueInformation[0] == 4 )
    {
      v17 = MEMORY[0x7FFE0014];
      RtlSecondsSince1970ToTime(ElapsedSeconds, &Time);
      if ( (unsigned __int64)(v17 - Time.QuadPart) >= 0x649534E0000LL )
        v14 = 8;
    }
  }
  v18 = NumOfElements;
  if ( (unsigned int)NumOfElements < v14 )
    return SmpDesiredPfSizeBasedOnRAM;
  v20 = 240;
  v21 = 0;
  if ( (unsigned int)NumOfElements >= 0xF0 )
  {
    v18 = 240;
LABEL_21:
    v22 = v18;
    memcpy_0(Base, &dword_140030CD4, 4LL * v18);
    do
      ++v21;
    while ( v21 < v20 );
    goto LABEL_23;
  }
  v20 = NumOfElements;
  if ( (_DWORD)NumOfElements )
    goto LABEL_21;
  v22 = 0;
LABEL_23:
  qsort(Base, v22, 4u, SmpPagefileUsageSampleCompare);
  v23 = (unsigned int)dword_140030B68 * (unsigned __int64)(unsigned int)Base[9 * v20 / 0xA];
  return v23 + (v23 >> 4);
}

```

## disassembly

```asm
0x14000da48  push    rbp
0x14000da4a  push    rbx
0x14000da4b  push    rsi
0x14000da4c  push    rdi
0x14000da4d  lea     rbp, [rsp-748h]
0x14000da55  sub     rsp, 848h
0x14000da5c  mov     rax, cs:__security_cookie
0x14000da63  xor     rax, rsp
0x14000da66  mov     [rbp+760h+var_30], rax
0x14000da6d  xorps   xmm0, xmm0
0x14000da70  mov     [rsp+860h+var_818], 7E007Ch
0x14000da79  xor     eax, eax
0x14000da7b  mov     qword ptr [rsp+860h+ValueName.Length], 180016h
0x14000da84  xor     esi, esi
0x14000da86  lea     rax, aRegistryMachin_80; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x14000da8d  mov     [rsp+860h+var_810], rax
0x14000da92  lea     rcx, [rbp+760h+KeyValueInformation]; void *
0x14000da96  lea     rax, aInstalldate; "InstallDate"
0x14000da9d  mov     [rsp+860h+var_830], esi
0x14000daa1  movups  xmmword ptr [rsp+860h+ObjectAttributes.ObjectName], xmm0
0x14000daa6  mov     ebx, 3CCh
0x14000daab  mov     [rsp+860h+ValueName.Buffer], rax
0x14000dab0  mov     r8d, ebx; Size
0x14000dab3  mov     qword ptr [rsp+860h+Time], rsi
0x14000dab8  xor     edx, edx; Val
0x14000daba  mov     [rsp+860h+KeyHandle], rsi
0x14000dabf  movups  xmmword ptr [rsp+860h+ObjectAttributes.Length], xmm0
0x14000dac4  movups  xmmword ptr [rbp+760h+ObjectAttributes+1Ch], xmm0
0x14000dac8  call    memset_0
0x14000dacd  mov     rcx, cs:SmpMmKey; KeyHandle
0x14000dad4  lea     rax, [rsp+860h+var_830]
0x14000dad9  mov     [rsp+860h+ResultLength], rax; ResultLength
0x14000dade  lea     r9, [rbp+760h+KeyValueInformation]; KeyValueInformation
0x14000dae2  lea     r8d, [rsi+4]; KeyValueInformationClass
0x14000dae6  mov     [rsp+860h+Length], ebx; Length
0x14000daea  lea     rdx, SmpPagefileUsageValue; ValueName
0x14000daf1  call    cs:__imp_NtQueryValueKey
0x14000daf7  test    eax, eax
0x14000daf9  js      loc_14000DBA1
0x14000daff  cmp     [rbp+760h+KeyValueInformation], 3
0x14000db03  jnz     loc_14000DBA1
0x14000db09  cmp     [rbp+760h+var_7BC], 3C4h
0x14000db10  jnz     loc_14000DBA1
0x14000db16  cmp     [rbp+760h+ElapsedSeconds], esi
0x14000db19  jz      loc_14000DBA1
0x14000db1f  lea     edx, [rsi+7]
0x14000db22  lea     r8d, [rdx+79h]
0x14000db26  lea     rcx, NumOfElements
0x14000db2d  lea     rax, [rbp+760h+ElapsedSeconds]
0x14000db31  movups  xmm0, xmmword ptr [rax]
0x14000db34  movups  xmm1, xmmword ptr [rax+10h]
0x14000db38  movups  xmmword ptr [rcx], xmm0
0x14000db3b  movups  xmm0, xmmword ptr [rax+20h]
0x14000db3f  movups  xmmword ptr [rcx+10h], xmm1
0x14000db43  movups  xmm1, xmmword ptr [rax+30h]
0x14000db47  movups  xmmword ptr [rcx+20h], xmm0
0x14000db4b  movups  xmm0, xmmword ptr [rax+40h]
0x14000db4f  movups  xmmword ptr [rcx+30h], xmm1
0x14000db53  movups  xmm1, xmmword ptr [rax+50h]
0x14000db57  movups  xmmword ptr [rcx+40h], xmm0
0x14000db5b  movups  xmm0, xmmword ptr [rax+60h]
0x14000db5f  movups  xmmword ptr [rcx+50h], xmm1
0x14000db63  movups  xmm1, xmmword ptr [rax+70h]
0x14000db67  add     rax, r8
0x14000db6a  movups  xmmword ptr [rcx+60h], xmm0
0x14000db6e  movups  xmmword ptr [rcx+70h], xmm1
0x14000db72  add     rcx, r8
0x14000db75  sub     rdx, 1
0x14000db79  jnz     short loc_14000DB31
0x14000db7b  movups  xmm0, xmmword ptr [rax]
0x14000db7e  movups  xmm1, xmmword ptr [rax+10h]
0x14000db82  movups  xmmword ptr [rcx], xmm0
0x14000db85  movups  xmm0, xmmword ptr [rax+20h]
0x14000db89  movups  xmmword ptr [rcx+10h], xmm1
0x14000db8d  movups  xmm1, xmmword ptr [rax+30h]
0x14000db91  mov     eax, [rax+40h]
0x14000db94  movups  xmmword ptr [rcx+20h], xmm0
0x14000db98  movups  xmmword ptr [rcx+30h], xmm1
0x14000db9c  mov     [rcx+40h], eax
0x14000db9f  jmp     short loc_14000DBA7
0x14000dba1  mov     cs:NumOfElements, esi
0x14000dba7  lea     rax, [rsp+860h+var_818]
0x14000dbac  mov     [rsp+860h+ObjectAttributes.RootDirectory], rsi
0x14000dbb1  xorps   xmm0, xmm0
0x14000dbb4  mov     [rsp+860h+ObjectAttributes.ObjectName], rax
0x14000dbb9  mov     edi, 30h ; '0'
0x14000dbbe  mov     [rbp+760h+ObjectAttributes.Attributes], 40h ; '@'
0x14000dbc5  lea     r8, [rsp+860h+ObjectAttributes]; ObjectAttributes
0x14000dbca  mov     [rsp+860h+ObjectAttributes.Length], edi
0x14000dbce  mov     edx, 20019h; DesiredAccess
0x14000dbd3  lea     rcx, [rsp+860h+KeyHandle]; KeyHandle
0x14000dbd8  movdqu  xmmword ptr [rbp+760h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000dbdd  call    cs:__imp_NtOpenKey
0x14000dbe3  test    eax, eax
0x14000dbe5  js      short loc_14000DC55
0x14000dbe7  mov     rcx, [rsp+860h+KeyHandle]; KeyHandle
0x14000dbec  lea     rax, [rsp+860h+var_830]
0x14000dbf1  mov     [rsp+860h+ResultLength], rax; ResultLength
0x14000dbf6  lea     r9, [rbp+760h+KeyValueInformation]; KeyValueInformation
0x14000dbfa  lea     r8d, [rdi-2Ch]; KeyValueInformationClass
0x14000dbfe  mov     [rsp+860h+Length], ebx; Length
0x14000dc02  lea     rdx, [rsp+860h+ValueName]; ValueName
0x14000dc07  call    cs:__imp_NtQueryValueKey
0x14000dc0d  mov     rcx, [rsp+860h+KeyHandle]; Handle
0x14000dc12  mov     ebx, eax
0x14000dc14  call    cs:__imp_NtClose
0x14000dc1a  test    ebx, ebx
0x14000dc1c  js      short loc_14000DC69
0x14000dc1e  cmp     [rbp+760h+KeyValueInformation], 4
0x14000dc22  jnz     short loc_14000DC69
0x14000dc24  mov     ebx, 7FFE0014h
0x14000dc29  lea     rdx, [rsp+860h+Time]; Time
0x14000dc2e  mov     rbx, [rbx]
0x14000dc31  mov     ecx, [rbp+760h+ElapsedSeconds]; ElapsedSeconds
0x14000dc34  call    cs:__imp_RtlSecondsSince1970ToTime
0x14000dc3a  sub     rbx, qword ptr [rsp+860h+Time]
0x14000dc3f  mov     rax, 649534E0000h
0x14000dc49  cmp     rbx, rax
0x14000dc4c  jb      short loc_14000DC69
0x14000dc4e  mov     edi, 8
0x14000dc53  jmp     short loc_14000DC69
0x14000dc55  mov     r8d, eax
0x14000dc58  lea     rcx, aSmpcomputedesi; "SmpComputeDesiredPfSizeBasedOnHistory"
0x14000dc5f  mov     edx, 0DC2h
0x14000dc64  call    SmpLogFailure
0x14000dc69  mov     eax, cs:NumOfElements
0x14000dc6f  cmp     eax, edi
0x14000dc71  jnb     short loc_14000DC7C
0x14000dc73  mov     rax, cs:SmpDesiredPfSizeBasedOnRAM
0x14000dc7a  jmp     short loc_14000DCFB
0x14000dc7c  mov     ebx, 0F0h
0x14000dc81  mov     edi, esi
0x14000dc83  cmp     eax, ebx
0x14000dc85  jnb     short loc_14000DC92
0x14000dc87  mov     ebx, eax
0x14000dc89  test    eax, eax
0x14000dc8b  jnz     short loc_14000DC94
0x14000dc8d  mov     rsi, rax
0x14000dc90  jmp     short loc_14000DCB6
0x14000dc92  mov     eax, ebx
0x14000dc94  mov     r8d, eax
0x14000dc97  lea     rdx, dword_140030CD4; Src
0x14000dc9e  shl     r8, 2; MaxCount
0x14000dca2  lea     rcx, [rbp+760h+Base]; void *
0x14000dca9  mov     esi, eax
0x14000dcab  call    memcpy_0
0x14000dcb0  inc     edi
0x14000dcb2  cmp     edi, ebx
0x14000dcb4  jb      short loc_14000DCB0
0x14000dcb6  lea     r9, SmpPagefileUsageSampleCompare; PtFuncCompare
0x14000dcbd  mov     r8d, 4; SizeOfElements
0x14000dcc3  mov     rdx, rsi; NumOfElements
0x14000dcc6  lea     rcx, [rbp+760h+Base]; Base
0x14000dccd  call    cs:__imp_qsort
0x14000dcd3  lea     ecx, [rbx+rbx*8]
0x14000dcd6  mov     eax, 0CCCCCCCDh
0x14000dcdb  mul     ecx
0x14000dcdd  mov     eax, cs:dword_140030B68
0x14000dce3  shr     edx, 3
0x14000dce6  mov     ecx, [rbp+rdx*4+760h+Base]
0x14000dced  imul    rcx, rax
0x14000dcf1  mov     rax, rcx
0x14000dcf4  shr     rax, 4
0x14000dcf8  add     rax, rcx
0x14000dcfb  mov     rcx, [rbp+760h+var_30]
0x14000dd02  xor     rcx, rsp; StackCookie
0x14000dd05  call    __security_check_cookie
0x14000dd0a  add     rsp, 848h
0x14000dd11  pop     rdi
0x14000dd12  pop     rsi
0x14000dd13  pop     rbx
0x14000dd14  pop     rbp
0x14000dd15  retn
```
