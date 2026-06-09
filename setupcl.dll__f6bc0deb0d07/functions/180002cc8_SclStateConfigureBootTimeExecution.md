# SclStateConfigureBootTimeExecution

- ea: `0x180002cc8`
- end: `0x18000336d`
- name: `SclStateConfigureBootTimeExecution`
- size: `1701`
- prototype: `__int64 __fastcall(__int64, char, char)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180001de0`
- `0x180003374`

## callees

- `0x1800014e8`
- `0x180001d48`
- `0x180002cc8`
- `0x180009438`
- `0x180009668`
- `0x18000a334`
- `0x18000a524`
- `0x18000a7f0`
- `0x18000a9b0`
- `0x1800179ad`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800030d3`
- `ntdll!RtlAllocateHeap` at `0x1800030d3`
- `ntdll!RtlInitUnicodeString` at `0x18000322e`
- `ntdll!RtlInitUnicodeString` at `0x18000322e`
- `ntdll!NtClose` at `0x18000319c`
- `ntdll!NtClose` at `0x1800031ac`
- `ntdll!NtClose` at `0x18000319c`
- `ntdll!NtClose` at `0x1800031ac`
- `ntdll!RtlFreeHeap` at `0x180002e8b`
- `ntdll!RtlFreeHeap` at `0x18000318c`
- `ntdll!RtlFreeHeap` at `0x18000328b`
- `ntdll!RtlFreeHeap` at `0x180002e8b`
- `ntdll!RtlFreeHeap` at `0x18000318c`
- `ntdll!RtlFreeHeap` at `0x18000328b`
- `ntdll!NtFlushKey` at `0x1800032af`
- `ntdll!NtFlushKey` at `0x1800032af`
- `ntdll!NtDeleteValueKey` at `0x18000323e`
- `ntdll!NtDeleteValueKey` at `0x18000323e`
- `ntdll!_wcsnicmp` at `0x180003026`
- `ntdll!_wcsnicmp` at `0x180003026`

## string_xrefs

- `0x180002d37`: `\REGISTRY\MACHINE\SYSTEM\SETUP\SETUPCL\SESSION MANAGER`
- `0x180002d94`: `SclStateConfigureBootTimeExecution`
- `0x180002f55`: `SclStateConfigureBootTimeExecution`
- `0x18000313b`: `SclStateConfigureBootTimeExecution`
- `0x180003296`: `SclStateConfigureBootTimeExecution`
- `0x180003327`: `SclStateConfigureBootTimeExecution`
- `0x180002dc5`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\CONTROL\SESSION MANAGER`
- `0x180002f44`: `%ws value not found; nothing to delete.`
- `0x180003337`: `%ws value not found; nothing to delete.`
- `0x180003305`: `Successfully configured SetupCl %s at next boot; a registry change %s`
- `0x180003147`: `(%lx): Failed to update %ws value.`

## pseudocode

```c
__int64 __fastcall SclStateConfigureBootTimeExecution(__int64 a1, char a2, char a3)
{
  unsigned int v3; // esi
  const wchar_t *v4; // r15
  bool v7; // r14
  _DWORD *v8; // r13
  const wchar_t *v9; // rdx
  __int64 v10; // rcx
  int Dword; // eax
  int Key; // edi
  char v13; // al
  const WCHAR *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int Value; // eax
  __int64 v18; // rdx
  int v19; // eax
  PVOID v20; // rbx
  unsigned __int64 v21; // r15
  _WORD *v22; // rsi
  int NextString; // eax
  int v24; // eax
  __int64 v25; // rbx
  unsigned __int64 v26; // r12
  _WORD *Heap; // rax
  size_t v28; // rbx
  void *v29; // rbx
  struct _UNICODE_STRING *p_DestinationString; // rcx
  __int64 *v31; // r8
  int v32; // r9d
  int v33; // edx
  NTSTATUS v35; // eax
  ULONG v36; // [rsp+20h] [rbp-E0h]
  char v38; // [rsp+41h] [rbp-BFh]
  char v39; // [rsp+42h] [rbp-BEh]
  const WCHAR *SourceString; // [rsp+48h] [rbp-B8h]
  PVOID P; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v42; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-A0h] BYREF
  size_t MaxCount; // [rsp+68h] [rbp-98h] BYREF
  HANDLE KeyHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  wchar_t String1[12]; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v48[3]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v49[2]; // [rsp+D0h] [rbp-30h]

  v3 = 0;
  KeyHandle = 0;
  Handle = 0;
  v4 = L"SETUPEXECUTENOPNPSYNC";
  v42 = 0;
  if ( !a2 )
    v4 = L"SETUPEXECUTE";
  SourceString = v4;
  v7 = 0;
  v8 = 0;
  if ( a2 )
  {
    LODWORD(P) = 0;
    v9 = L"SETUP\\SETUPCL\\SESSION MANAGER";
    if ( a1 )
    {
      v10 = *(_QWORD *)(a1 + 56);
    }
    else
    {
      v9 = L"\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SETUPCL\\SESSION MANAGER";
      v10 = 0;
    }
    Dword = SclRegGetDword(v10, v9, L"SUPPORTEDONETIMEEXECUTE", &P);
    Key = Dword;
    if ( Dword == -1073741772 )
    {
      v13 = 0;
    }
    else
    {
      if ( Dword < 0 )
        goto LABEL_79;
      v13 = (char)P;
    }
    if ( (v13 & 1) == 0 )
    {
      SclLogGenericMessage(
        0,
        2,
        (unsigned int)SclEvent_Generic_Warning,
        410,
        (__int64)"SclStateConfigureBootTimeExecution");
      Key = -1073741637;
      goto LABEL_57;
    }
  }
  if ( a1 )
  {
    v16 = *(_QWORD *)(a1 + 56);
    v48[0] = *(_OWORD *)L"CONTROLSET001\\CONTROL\\SESSION MANAGER";
    v48[2] = *(_OWORD *)L"NTROL\\SESSION MANAGER";
    P = 0;
    v48[1] = *(_OWORD *)L"ET001\\CONTROL\\SESSION MANAGER";
    v49[0] = *(_OWORD *)L"SSION MANAGER";
    *(_OWORD *)((char *)v49 + 12) = *(_OWORD *)L"MANAGER";
    Key = SclCreateKey(v16, L"SELECT", 0x20019u, (__int64)&KeyHandle);
    if ( Key < 0 )
      goto LABEL_84;
    Key = SclRegGetValue(KeyHandle, v36);
    if ( Key < 0 )
      goto LABEL_84;
    if ( *((_DWORD *)P + 1) == 4 )
    {
      if ( *((_DWORD *)P + 2) == 4 )
        v3 = *((_DWORD *)P + 3);
      else
        Key = -1073741820;
    }
    else
    {
      Key = -1073741788;
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    if ( Key < 0 )
      goto LABEL_84;
    Key = RtlStringCchPrintfW(v48, 38, L"CONTROLSET%03u\\CONTROL\\SESSION MANAGER", v3);
    if ( Key < 0 )
      goto LABEL_84;
    v15 = *(_QWORD *)(a1 + 56);
    v14 = (const WCHAR *)v48;
  }
  else
  {
    v14 = L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\CONTROL\\SESSION MANAGER";
    v15 = 0;
  }
  Key = SclCreateKey(v15, v14, 0xF003Fu, (__int64)&Handle);
  if ( Key >= 0 )
  {
    Value = SclRegGetValue(Handle, v36);
    Key = Value;
    if ( Value == -1073741772 )
    {
      if ( a3 )
      {
        v19 = SclRegSetValue(Handle, v18, v4, L"setupcl.exe", 26, 7);
        v8 = (_DWORD *)v42;
        Key = v19;
        v7 = v19 >= 0;
      }
      else
      {
        Key = 0;
        SclLogGenericMessage(
          0,
          1,
          (unsigned int)SclEvent_Generic_Info,
          523,
          (__int64)"SclStateConfigureBootTimeExecution");
        v8 = (_DWORD *)v42;
      }
      goto LABEL_79;
    }
    v8 = (_DWORD *)v42;
    if ( Value < 0 )
      goto LABEL_57;
    v39 = 0;
    LODWORD(v20) = 0;
    wcscpy(String1, L"setupclexe");
    v21 = (unsigned __int64)*(unsigned int *)(v42 + 8) >> 1;
    *(_QWORD *)&DestinationString.Length = 0;
    MaxCount = 0;
    v22 = (_WORD *)(v42 + 12);
    v42 = v21;
LABEL_34:
    P = 0;
    while ( 1 )
    {
      NextString = SclMultiSzFindNextString((int)v8 + 12, v21, (_DWORD)v20, (unsigned int)&P, (__int64)&MaxCount);
      Key = NextString;
      if ( NextString == -2147483622 )
        break;
      if ( NextString < 0 )
        goto LABEL_57;
      v20 = P;
      if ( MaxCount == 11 && !_wcsnicmp(String1, (const wchar_t *)P, 0xBu) )
      {
        v39 = 1;
        if ( !a3 )
        {
          v7 = 1;
          v24 = SclMultiSzRemoveString(v8 + 3, v21, v20, &v42);
          v21 = v42;
          if ( v24 >= 0 )
          {
            LODWORD(v20) = 0;
            v8[2] = 2 * v42;
            goto LABEL_34;
          }
        }
      }
    }
    v38 = 0;
    if ( !a3 || v39 )
    {
      p_DestinationString = (struct _UNICODE_STRING *)&v42;
      Key = 0;
      v29 = 0;
      if ( !v7 )
      {
LABEL_77:
        if ( v29 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
LABEL_79:
        if ( Key < 0 )
          goto LABEL_57;
        if ( v7 )
        {
          Key = NtFlushKey(Handle);
          if ( Key < 0 )
            goto LABEL_57;
        }
        goto LABEL_82;
      }
    }
    else
    {
      MaxCount = (size_t)(v8 + 3);
      if ( v8 == (_DWORD *)-12LL || !String1[0] )
      {
        Key = -1073741811;
LABEL_57:
        v31 = SclEvent_Generic_Error;
        v32 = 702;
        v33 = 3;
        goto LABEL_58;
      }
      v25 = -1;
      do
        ++v25;
      while ( String1[v25] );
      if ( v21 <= 1 || *v22 )
        ++v25;
      v26 = v25 + v21;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * (v25 + v21));
      v22 = Heap;
      if ( Heap )
      {
        Key = 0;
        v28 = v25;
        memcpy_0(Heap, String1, v28 * 2);
        memcpy_0(&v22[v28], (const void *)MaxCount, 2 * v21);
        *(_QWORD *)&DestinationString.Length = v26;
      }
      else
      {
        v22 = 0;
        Key = -1073741801;
      }
      v29 = v22;
      if ( Key < 0 )
        goto LABEL_77;
      v7 = 1;
      p_DestinationString = &DestinationString;
    }
    if ( v22 )
    {
      if ( !*(_QWORD *)&p_DestinationString->Length || (v38 = 0, !*v22) )
        v38 = 1;
      Key = 0;
    }
    else
    {
      Key = -1073741811;
    }
    if ( Key >= 0 )
    {
      if ( v38 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, SourceString);
        v35 = NtDeleteValueKey(Handle, &DestinationString);
      }
      else
      {
        v35 = SclRegSetValue(Handle, 0, SourceString, v22, 2 * *(_DWORD *)&p_DestinationString->Length, 7);
      }
      Key = v35;
    }
    goto LABEL_77;
  }
LABEL_84:
  if ( Key != -1073741772 )
    goto LABEL_79;
  if ( a3 )
    goto LABEL_57;
  Key = 0;
  SclLogGenericMessage(0, 1, (unsigned int)SclEvent_Generic_Info, 676, (__int64)"SclStateConfigureBootTimeExecution");
LABEL_82:
  v33 = 1;
  v31 = SclEvent_Generic_Info;
  v32 = 695;
LABEL_58:
  SclLogGenericMessage(0, v33, (_DWORD)v31, v32, (__int64)"SclStateConfigureBootTimeExecution");
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( Handle )
    NtClose(Handle);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180002cc8  push    rbp
0x180002cca  push    rbx
0x180002ccb  push    rsi
0x180002ccc  push    rdi
0x180002ccd  push    r12
0x180002ccf  push    r13
0x180002cd1  push    r14
0x180002cd3  push    r15
0x180002cd5  lea     rbp, [rsp-8]
0x180002cda  sub     rsp, 108h
0x180002ce1  mov     rax, cs:__security_cookie
0x180002ce8  xor     rax, rsp
0x180002ceb  mov     [rbp+40h+var_50], rax
0x180002cef  xor     esi, esi
0x180002cf1  mov     [rsp+140h+var_100], r8b
0x180002cf6  test    dl, dl
0x180002cf8  mov     [rsp+140h+KeyHandle], rsi
0x180002cfd  lea     rax, aSetupexecute; "SETUPEXECUTE"
0x180002d04  mov     [rsp+140h+Handle], rsi
0x180002d09  lea     r15, aSetupexecuteno; "SETUPEXECUTENOPNPSYNC"
0x180002d10  mov     [rsp+140h+var_E8], rsi
0x180002d15  cmovz   r15, rax
0x180002d19  mov     r12b, r8b
0x180002d1c  mov     [rsp+140h+SourceString], r15
0x180002d21  mov     rbx, rcx
0x180002d24  mov     r14b, sil
0x180002d27  mov     r13d, esi
0x180002d2a  jz      loc_180002DC0
0x180002d30  test    rcx, rcx
0x180002d33  mov     dword ptr [rsp+140h+P], esi
0x180002d37  lea     rax, aRegistryMachin_12; "\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SET"...
0x180002d3e  lea     rdx, aSetupSetupclSe; "SETUP\\SETUPCL\\SESSION MANAGER"
0x180002d45  cmovz   rdx, rax
0x180002d49  jz      short loc_180002D51
0x180002d4b  mov     rcx, [rcx+38h]
0x180002d4f  jmp     short loc_180002D54
0x180002d51  mov     rcx, rsi
0x180002d54  lea     r9, [rsp+140h+P]
0x180002d59  lea     r8, aSupportedoneti; "SUPPORTEDONETIMEEXECUTE"
0x180002d60  call    SclRegGetDword
0x180002d65  mov     edi, eax
0x180002d67  cmp     eax, 0C0000034h
0x180002d6c  jnz     short loc_180002D72
0x180002d6e  mov     eax, esi
0x180002d70  jmp     short loc_180002D7E
0x180002d72  test    eax, eax
0x180002d74  js      loc_180002F3C
0x180002d7a  mov     eax, dword ptr [rsp+140h+P]
0x180002d7e  test    al, 1
0x180002d80  jnz     short loc_180002DC0
0x180002d82  lea     rax, aOsDoesNotSuppo; "OS does not support boot-time execution"...
0x180002d89  mov     r9d, 19Ah
0x180002d8f  mov     [rsp+140h+var_118], rax
0x180002d94  lea     rbx, aSclstateconfig; "SclStateConfigureBootTimeExecution"
0x180002d9b  lea     r8, SclEvent_Generic_Warning
0x180002da2  mov     [rsp+140h+var_120], rbx
0x180002da7  mov     edx, 2
0x180002dac  xor     ecx, ecx
0x180002dae  call    SclLogGenericMessage
0x180002db3  mov     edi, 0C00000BBh
0x180002db8  mov     rsi, r15
0x180002dbb  jmp     loc_180003142
0x180002dc0  test    rbx, rbx
0x180002dc3  jnz     short loc_180002DD3
0x180002dc5  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x180002dcc  xor     ecx, ecx
0x180002dce  jmp     loc_180002EC5
0x180002dd3  movaps  xmm0, xmmword ptr cs:aControlset001C; "CONTROLSET001\\CONTROL\\SESSION MANAGER"
0x180002dda  lea     r9, [rsp+140h+KeyHandle]
0x180002ddf  movaps  xmm1, xmmword ptr cs:aControlset001C+10h; "ET001\\CONTROL\\SESSION MANAGER"
0x180002de6  lea     rdx, aSelect; "SELECT"
0x180002ded  mov     rcx, [rbx+38h]
0x180002df1  mov     r8d, 20019h
0x180002df7  movaps  [rbp+40h+var_A0], xmm0
0x180002dfb  movaps  xmm0, xmmword ptr cs:aControlset001C+20h; "NTROL\\SESSION MANAGER"
0x180002e02  movaps  [rbp+40h+var_80], xmm0
0x180002e06  movups  xmm0, xmmword ptr cs:aControlset001C+3Ch; "MANAGER"
0x180002e0d  mov     [rsp+140h+P], rsi
0x180002e12  movaps  [rbp+40h+var_90], xmm1
0x180002e16  movaps  xmm1, xmmword ptr cs:aControlset001C+30h; "SSION MANAGER"
0x180002e1d  movaps  xmmword ptr [rbp+40h+var_70], xmm1
0x180002e21  movups  xmmword ptr [rbp+40h+var_70+0Ch], xmm0
0x180002e25  call    SclCreateKey
0x180002e2a  mov     edi, eax
0x180002e2c  test    eax, eax
0x180002e2e  js      loc_18000331B
0x180002e34  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x180002e39  lea     r9, [rsp+140h+P]
0x180002e3e  xor     r8d, r8d
0x180002e41  lea     rdx, aCurrent; "CURRENT"
0x180002e48  call    SclRegGetValue
0x180002e4d  mov     edi, eax
0x180002e4f  test    eax, eax
0x180002e51  js      loc_18000331B
0x180002e57  mov     r8, [rsp+140h+P]; P
0x180002e5c  cmp     dword ptr [r8+4], 4
0x180002e61  jz      short loc_180002E6A
0x180002e63  mov     edi, 0C0000024h
0x180002e68  jmp     short loc_180002E7C
0x180002e6a  cmp     dword ptr [r8+8], 4
0x180002e6f  jz      short loc_180002E78
0x180002e71  mov     edi, 0C0000004h
0x180002e76  jmp     short loc_180002E7C
0x180002e78  mov     esi, [r8+0Ch]
0x180002e7c  mov     rcx, gs:60h
0x180002e85  xor     edx, edx; Flags
0x180002e87  mov     rcx, [rcx+30h]; HeapHandle
0x180002e8b  call    cs:__imp_RtlFreeHeap
0x180002e91  test    edi, edi
0x180002e93  js      loc_180003319
0x180002e99  mov     r9d, esi
0x180002e9c  lea     r8, aControlset03uC; "CONTROLSET%03u\\CONTROL\\SESSION MANAGE"...
0x180002ea3  mov     edx, 26h ; '&'
0x180002ea8  lea     rcx, [rbp+40h+var_A0]
0x180002eac  call    RtlStringCchPrintfW
0x180002eb1  xor     esi, esi
0x180002eb3  mov     edi, eax
0x180002eb5  test    eax, eax
0x180002eb7  js      loc_18000331B
0x180002ebd  mov     rcx, [rbx+38h]
0x180002ec1  lea     rdx, [rbp+40h+var_A0]
0x180002ec5  lea     r9, [rsp+140h+Handle]
0x180002eca  mov     r8d, 0F003Fh
0x180002ed0  call    SclCreateKey
0x180002ed5  mov     edi, eax
0x180002ed7  test    eax, eax
0x180002ed9  js      loc_18000331B
0x180002edf  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x180002ee4  lea     r9, [rsp+140h+var_E8]
0x180002ee9  xor     r8d, r8d
0x180002eec  mov     rdx, r15
0x180002eef  call    SclRegGetValue
0x180002ef4  mov     edi, eax
0x180002ef6  cmp     eax, 0C0000034h
0x180002efb  jnz     loc_180002F89
0x180002f01  test    r12b, r12b
0x180002f04  jz      short loc_180002F44
0x180002f06  mov     rcx, [rsp+140h+Handle]
0x180002f0b  lea     r9, aSetupclExe_0; "setupcl.exe"
0x180002f12  mov     dword ptr [rsp+140h+var_118], 7
0x180002f1a  mov     r8, r15
0x180002f1d  mov     dword ptr [rsp+140h+var_120], 1Ah
0x180002f25  call    SclRegSetValue
0x180002f2a  mov     r13, [rsp+140h+var_E8]
0x180002f2f  mov     r14d, eax
0x180002f32  shr     r14d, 1Fh
0x180002f36  mov     edi, eax
0x180002f38  xor     r14b, 1
0x180002f3c  mov     rsi, r15
0x180002f3f  jmp     loc_180003296
0x180002f44  lea     rax, aWsValueNotFoun; "%ws value not found; nothing to delete."
0x180002f4b  mov     [rsp+140h+var_110], r15
0x180002f50  mov     [rsp+140h+var_118], rax
0x180002f55  lea     rbx, aSclstateconfig; "SclStateConfigureBootTimeExecution"
0x180002f5c  mov     r9d, 20Bh
0x180002f62  mov     [rsp+140h+var_120], rbx
0x180002f67  lea     r8, SclEvent_Generic_Info
0x180002f6e  mov     edx, 1
0x180002f73  xor     ecx, ecx
0x180002f75  mov     edi, esi
0x180002f77  call    SclLogGenericMessage
0x180002f7c  mov     r13, [rsp+140h+var_E8]
0x180002f81  mov     rsi, r15
0x180002f84  jmp     loc_18000329D
0x180002f89  mov     r13, [rsp+140h+var_E8]
0x180002f8e  test    eax, eax
0x180002f90  js      loc_180003311
0x180002f96  movups  xmm0, xmmword ptr cs:aSetupclExe+2; "etupcl.exe"
0x180002f9d  mov     eax, 73h ; 's'
0x180002fa2  mov     [rsp+140h+var_FE], sil
0x180002fa7  movsd   xmm1, qword ptr cs:aSetupclExe+10h; "exe"
0x180002faf  mov     rbx, rsi
0x180002fb2  movups  [rbp+40h+var_B6], xmm0
0x180002fb6  mov     [rbp+40h+String1], ax
0x180002fba  movsd   qword ptr [rbp+40h+var_B6+0Eh], xmm1
0x180002fbf  mov     r15d, [r13+8]
0x180002fc3  shr     r15, 1
0x180002fc6  mov     qword ptr [rsp+140h+DestinationString.Length], rsi
0x180002fcb  mov     [rsp+140h+MaxCount], rsi
0x180002fd0  lea     rsi, [r13+0Ch]
0x180002fd4  mov     [rsp+140h+var_E8], r15
0x180002fd9  mov     [rsp+140h+P], rbx
0x180002fde  lea     rax, [rsp+140h+MaxCount]
0x180002fe3  mov     r8, rbx
0x180002fe6  lea     r9, [rsp+140h+P]
0x180002feb  mov     [rsp+140h+var_120], rax
0x180002ff0  mov     rdx, r15
0x180002ff3  mov     rcx, rsi
0x180002ff6  call    SclMultiSzFindNextString
0x180002ffb  mov     edi, eax
0x180002ffd  cmp     eax, 8000001Ah
0x180003002  jz      short loc_18000306B
0x180003004  xor     r12d, r12d
0x180003007  test    eax, eax
0x180003009  js      loc_180003136
0x18000300f  mov     r8, [rsp+140h+MaxCount]; MaxCount
0x180003014  mov     rbx, [rsp+140h+P]
0x180003019  cmp     r8, 0Bh
0x18000301d  jnz     short loc_180002FDE
0x18000301f  mov     rdx, rbx; String2
0x180003022  lea     rcx, [rbp+40h+String1]; String1
0x180003026  call    cs:__imp__wcsnicmp
0x18000302c  test    eax, eax
0x18000302e  jnz     short loc_180002FDE
0x180003030  mov     [rsp+140h+var_FE], 1
0x180003035  cmp     [rsp+140h+var_100], r12b
0x18000303a  jnz     short loc_180002FDE
0x18000303c  lea     r9, [rsp+140h+var_E8]
0x180003041  mov     r8, rbx
0x180003044  mov     rdx, r15
0x180003047  mov     rcx, rsi
0x18000304a  mov     r14b, 1
0x18000304d  call    SclMultiSzRemoveString
0x180003052  mov     r15, [rsp+140h+var_E8]
0x180003057  test    eax, eax
0x180003059  js      short loc_180002FDE
0x18000305b  lea     eax, [r15+r15]
0x18000305f  mov     ebx, r12d
0x180003062  mov     [r13+8], eax
0x180003066  jmp     loc_180002FD9
0x18000306b  xor     edx, edx; Flags
0x18000306d  mov     al, dl
0x18000306f  mov     [rsp+140h+var_FF], dl
0x180003073  cmp     [rsp+140h+var_100], dl
0x180003077  jz      loc_1800031D4
0x18000307d  cmp     [rsp+140h+var_FE], al
0x180003081  jnz     loc_1800031D4
0x180003087  mov     [rsp+140h+MaxCount], rsi
0x18000308c  test    rsi, rsi
0x18000308f  jz      loc_180003131
0x180003095  cmp     dx, [rbp+40h+String1]
0x180003099  jz      loc_180003131
0x18000309f  lea     rax, [rbp+40h+String1]
0x1800030a3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800030a7  inc     rbx
0x1800030aa  cmp     [rax+rbx*2], dx
0x1800030ae  jnz     short loc_1800030A7
0x1800030b0  cmp     r15, 1
0x1800030b4  jbe     short loc_1800030BB
0x1800030b6  cmp     dx, [rsi]
0x1800030b9  jz      short loc_1800030BE
0x1800030bb  inc     rbx
0x1800030be  mov     rcx, gs:60h
0x1800030c7  lea     r12, [rbx+r15]
0x1800030cb  lea     r8, [r12+r12]; Size
0x1800030cf  mov     rcx, [rcx+30h]; HeapHandle
0x1800030d3  call    cs:__imp_RtlAllocateHeap
0x1800030d9  xor     edx, edx
0x1800030db  mov     rsi, rax
0x1800030de  test    rax, rax
0x1800030e1  jnz     short loc_1800030EC
0x1800030e3  mov     esi, edx
0x1800030e5  mov     edi, 0C0000017h
0x1800030ea  jmp     short loc_180003119
0x1800030ec  mov     edi, edx
0x1800030ee  add     rbx, rbx
0x1800030f1  mov     r8, rbx; Size
0x1800030f4  lea     rdx, [rbp+40h+String1]; Src
0x1800030f8  mov     rcx, rsi; void *
0x1800030fb  call    memcpy_0
0x180003100  mov     rdx, [rsp+140h+MaxCount]; Src
0x180003105  lea     r8, [r15+r15]; Size
0x180003109  lea     rcx, [rbx+rsi]; void *
0x18000310d  call    memcpy_0
0x180003112  xor     edx, edx
0x180003114  mov     qword ptr [rsp+140h+DestinationString.Length], r12
0x180003119  mov     rbx, rsi
0x18000311c  test    edi, edi
0x18000311e  js      loc_18000326F
0x180003124  mov     r14b, 1
0x180003127  lea     rcx, [rsp+140h+DestinationString]
0x18000312c  jmp     loc_1800031E7
0x180003131  mov     edi, 0C000000Dh
0x180003136  mov     rsi, [rsp+140h+SourceString]
0x18000313b  lea     rbx, aSclstateconfig; "SclStateConfigureBootTimeExecution"
0x180003142  mov     [rsp+140h+var_108], rsi
0x180003147  lea     rax, aLxFailedToUpda; "(%lx): Failed to update %ws value."
0x18000314e  mov     dword ptr [rsp+140h+var_110], edi
0x180003152  lea     r8, SclEvent_Generic_Error
0x180003159  mov     r9d, 2BEh
0x18000315f  mov     edx, 3
0x180003164  mov     [rsp+140h+var_118], rax
0x180003169  xor     ecx, ecx
0x18000316b  mov     [rsp+140h+var_120], rbx
0x180003170  call    SclLogGenericMessage
0x180003175  test    r13, r13
0x180003178  jz      short loc_180003192
0x18000317a  mov     rcx, gs:60h
0x180003183  mov     r8, r13; P
0x180003186  xor     edx, edx; Flags
0x180003188  mov     rcx, [rcx+30h]; HeapHandle
0x18000318c  call    cs:__imp_RtlFreeHeap
0x180003192  mov     rcx, [rsp+140h+Handle]; Handle
0x180003197  test    rcx, rcx
0x18000319a  jz      short loc_1800031A2
0x18000319c  call    cs:__imp_NtClose
0x1800031a2  mov     rcx, [rsp+140h+KeyHandle]; Handle
0x1800031a7  test    rcx, rcx
0x1800031aa  jz      short loc_1800031B2
0x1800031ac  call    cs:__imp_NtClose
  ... truncated ...
```
