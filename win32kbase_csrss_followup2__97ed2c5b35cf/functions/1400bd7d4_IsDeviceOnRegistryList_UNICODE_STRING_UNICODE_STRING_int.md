# IsDeviceOnRegistryList(_UNICODE_STRING,_UNICODE_STRING,int)

- ea: `0x1400bd7d4`
- end: `0x1400bdbb5`
- name: `?IsDeviceOnRegistryList@@YAHU_UNICODE_STRING@@0H@Z`
- size: `993`
- prototype: `int(struct _UNICODE_STRING *__struct_ptr, struct _UNICODE_STRING *__struct_ptr, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400bc230`
- `0x1400bd6e0`

## callees

- `0x14004a0d0`
- `0x14004d770`
- `0x140096d00`
- `0x1400b1d40`
- `0x1400bd7d4`
- `0x1400bdbbc`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400bd831`
- `ntoskrnl!ZwOpenKey` at `0x1400bd831`
- `ntoskrnl!ZwQueryValueKey` at `0x1400bd865`
- `ntoskrnl!ZwQueryValueKey` at `0x1400bda3f`
- `ntoskrnl!ZwQueryValueKey` at `0x1400bd865`
- `ntoskrnl!ZwQueryValueKey` at `0x1400bda3f`
- `ntoskrnl!ZwClose` at `0x1400bd9d2`
- `ntoskrnl!ZwClose` at `0x1400bd9d2`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400bd8d4`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400bd929`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400bd8d4`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400bd929`
- `ntoskrnl!RtlCompareMemory` at `0x1400bd978`
- `ntoskrnl!RtlCompareMemory` at `0x1400bd978`
- `WIN32K!W32GetUserSessionState` at `0x1400bdac5`
- `WIN32K!W32GetUserSessionState` at `0x1400bdb67`
- `WIN32K!W32GetUserSessionState` at `0x1400bdac5`
- `WIN32K!W32GetUserSessionState` at `0x1400bdb67`

## pseudocode

```c
_BOOL8 __fastcall IsDeviceOnRegistryList(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2, int a3)
{
  BOOL v5; // r14d
  ULONG v6; // ebx
  NTSTATUS v7; // r15d
  struct _KEY_VALUE_FULL_INFORMATION *v8; // rsi
  unsigned int v9; // r12d
  _BYTE *v11; // rbx
  bool v12; // r12
  ULONG NameLength; // ebx
  __int64 v14; // rax
  int v15; // edx
  int v16; // r8d
  char v17; // bl
  bool v18; // si
  __int64 UserSessionState; // rax
  int v20; // r8d
  int v21; // edx
  ULONG Length; // [rsp+50h] [rbp-39h] BYREF
  ULONG v23; // [rsp+54h] [rbp-35h]
  unsigned int v24; // [rsp+58h] [rbp-31h]
  void *KeyHandle; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING v26; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  bool v28; // [rsp+F0h] [rbp+67h]
  ULONG ResultLength; // [rsp+108h] [rbp+7Fh] BYREF

  ObjectAttributes.ObjectName = a1;
  KeyHandle = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v5 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    if ( ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, 0, 0, &ResultLength) == -1073741772 || !ResultLength )
    {
      if ( a3 && a2->Length >= 0x2Au )
      {
        v6 = 0;
        Length = 0;
        v7 = 0;
        while ( 1 )
        {
          v23 = v6;
          if ( v7 == -2147483622 || v5 )
            break;
          v7 = ZwEnumerateValueKey(KeyHandle, v6, KeyValueFullInformation, 0, 0, &Length);
          if ( v7 != -1073741789 )
          {
            if ( v7 != -2147483622 )
            {
              if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
                || (v17 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
              {
                v17 = 0;
              }
              v18 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              if ( v17 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control);
                LOBYTE(v20) = v18;
                LOBYTE(v21) = v17;
                WPP_RECORDER_AND_TRACE_SF_D(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  v21,
                  v20,
                  *(_QWORD *)(UserSessionState + 19408),
                  3,
                  1,
                  17,
                  (__int64)WPP_b554531fceee36eb2b750301196162e5_Traceguids,
                  v7);
              }
            }
            break;
          }
          v8 = (struct _KEY_VALUE_FULL_INFORMATION *)Win32AllocPoolZInitImpl(0x100u, Length, 0x78657355u);
          if ( v8 )
          {
            v7 = ZwEnumerateValueKey(KeyHandle, v6, KeyValueFullInformation, v8, Length, &Length);
            if ( v7 >= 0 )
            {
              v9 = *((unsigned __int8 *)&v8->TitleIndex + v8->DataOffset);
              v24 = v9;
              if ( v9 - 1 <= 1 && v8->Type == 4 && v8->NameLength >= 0x2A && RtlCompareMemory(v8->Name, L"HID", 6u) == 6 )
              {
                v26 = *a2;
                v5 = CompareDeviceVIDPID(&v26, v8, v9) != 0;
              }
              else
              {
                v12 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
                v28 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  NameLength = v8->NameLength;
                  v14 = W32GetUserSessionState(WPP_GLOBAL_Control);
                  LOBYTE(v15) = v12;
                  LOBYTE(v16) = v28;
                  WPP_RECORDER_AND_TRACE_SF_DD(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    v15,
                    v16,
                    *(_QWORD *)(v14 + 19408),
                    4,
                    1,
                    16,
                    (__int64)WPP_b554531fceee36eb2b750301196162e5_Traceguids,
                    v24,
                    NameLength);
                  v6 = v23;
                }
              }
            }
            GreDeleteFastMutex(v8);
          }
          ++v6;
        }
      }
    }
    else
    {
      v11 = Win32AllocPoolZInitImpl(0x100u, ResultLength, 0x78657355u);
      if ( v11 )
      {
        if ( ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, v11, ResultLength, &ResultLength) >= 0
          && *((_DWORD *)v11 + 1) == 4 )
        {
          v5 = (unsigned __int8)(v11[12] - 1) <= 2u;
        }
        GreDeleteFastMutex(v11);
      }
    }
    ZwClose(KeyHandle);
  }
  return v5;
}

```

## disassembly

```asm
0x1400bd7d4  mov     [rsp-8+arg_8], rbx
0x1400bd7d9  push    rbp
0x1400bd7da  push    rsi
0x1400bd7db  push    rdi
0x1400bd7dc  push    r12
0x1400bd7de  push    r13
0x1400bd7e0  push    r14
0x1400bd7e2  push    r15
0x1400bd7e4  lea     rbp, [rsp-27h]
0x1400bd7e9  sub     rsp, 0B0h
0x1400bd7f0  xor     r12d, r12d
0x1400bd7f3  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x1400bd7f7  mov     ebx, r8d
0x1400bd7fa  mov     [rbp+57h+KeyHandle], r12
0x1400bd7fe  mov     r13, rdx
0x1400bd801  mov     [rbp+57h+arg_18], r12d
0x1400bd805  xorps   xmm0, xmm0
0x1400bd808  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1400bd80c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400bd810  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400bd818  mov     edx, 20019h; DesiredAccess
0x1400bd81d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400bd825  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400bd829  mov     r14d, r12d
0x1400bd82c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400bd831  call    cs:__imp_ZwOpenKey
0x1400bd838  nop     dword ptr [rax+rax+00h]
0x1400bd83d  test    eax, eax
0x1400bd83f  js      loc_1400BD9DE
0x1400bd845  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400bd849  lea     rax, [rbp+57h+arg_18]
0x1400bd84d  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400bd852  lea     esi, [r12+2]
0x1400bd857  mov     r8d, esi; KeyValueInformationClass
0x1400bd85a  mov     [rsp+0E0h+Length], r12d; Length
0x1400bd85f  xor     r9d, r9d; KeyValueInformation
0x1400bd862  mov     rdx, r13; ValueName
0x1400bd865  call    cs:__imp_ZwQueryValueKey
0x1400bd86c  nop     dword ptr [rax+rax+00h]
0x1400bd871  cmp     eax, 0C0000034h
0x1400bd876  jnz     loc_1400BD9FD
0x1400bd87c  test    ebx, ebx
0x1400bd87e  jz      loc_1400BD9CE
0x1400bd884  mov     eax, 2Ah ; '*'
0x1400bd889  cmp     [r13+0], ax
0x1400bd88e  jb      loc_1400BD9CE
0x1400bd894  mov     ebx, r12d
0x1400bd897  mov     [rbp+57h+var_90], r12d
0x1400bd89b  mov     r15d, r12d
0x1400bd89e  lea     edi, [rax-29h]
0x1400bd8a1  mov     [rbp+57h+var_8C], ebx
0x1400bd8a4  cmp     r15d, 8000001Ah
0x1400bd8ab  jz      loc_1400BD9CE
0x1400bd8b1  test    r14d, r14d
0x1400bd8b4  jnz     loc_1400BD9CE
0x1400bd8ba  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400bd8be  lea     rax, [rbp+57h+var_90]
0x1400bd8c2  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400bd8c7  xor     r9d, r9d; KeyValueInformation
0x1400bd8ca  mov     r8d, edi; KeyValueInformationClass
0x1400bd8cd  mov     [rsp+0E0h+Length], r12d; Length
0x1400bd8d2  mov     edx, ebx; Index
0x1400bd8d4  call    cs:__imp_ZwEnumerateValueKey
0x1400bd8db  nop     dword ptr [rax+rax+00h]
0x1400bd8e0  mov     r15d, eax
0x1400bd8e3  cmp     eax, 0C0000023h
0x1400bd8e8  jnz     loc_1400BD9C1
0x1400bd8ee  mov     edx, [rbp+57h+var_90]; unsigned __int64
0x1400bd8f1  mov     ecx, 100h; unsigned __int64
0x1400bd8f6  mov     r8d, 78657355h; unsigned int
0x1400bd8fc  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400bd901  mov     rsi, rax
0x1400bd904  test    rax, rax
0x1400bd907  jz      loc_1400BD9BA
0x1400bd90d  mov     ecx, [rbp+57h+var_90]
0x1400bd910  lea     rax, [rbp+57h+var_90]
0x1400bd914  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400bd919  mov     r9, rsi; KeyValueInformation
0x1400bd91c  mov     [rsp+0E0h+Length], ecx; Length
0x1400bd920  mov     r8d, edi; KeyValueInformationClass
0x1400bd923  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400bd927  mov     edx, ebx; Index
0x1400bd929  call    cs:__imp_ZwEnumerateValueKey
0x1400bd930  nop     dword ptr [rax+rax+00h]
0x1400bd935  mov     r15d, eax
0x1400bd938  test    eax, eax
0x1400bd93a  js      short loc_1400BD9B2
0x1400bd93c  mov     eax, [rsi+8]
0x1400bd93f  movzx   r12d, byte ptr [rax+rsi]
0x1400bd944  mov     [rbp+57h+var_88], r12d
0x1400bd948  lea     eax, [r12-1]
0x1400bd94d  cmp     eax, edi
0x1400bd94f  ja      loc_1400BDA7C
0x1400bd955  cmp     dword ptr [rsi+4], 4
0x1400bd959  jnz     loc_1400BDA7C
0x1400bd95f  cmp     dword ptr [rsi+10h], 2Ah ; '*'
0x1400bd963  jb      loc_1400BDA7C
0x1400bd969  lea     rcx, [rsi+14h]; Source1
0x1400bd96d  lea     r8d, [r14+6]; Length
0x1400bd971  lea     rdx, aHid_0; "HID"
0x1400bd978  call    cs:__imp_RtlCompareMemory
0x1400bd97f  nop     dword ptr [rax+rax+00h]
0x1400bd984  cmp     rax, 6
0x1400bd988  jnz     loc_1400BDA7C
0x1400bd98e  movaps  xmm0, xmmword ptr [r13+0]
0x1400bd993  lea     rcx, [rbp+57h+var_70]; struct _UNICODE_STRING
0x1400bd997  mov     r8d, r12d; unsigned int
0x1400bd99a  movdqa  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x1400bd99f  mov     rdx, rsi; struct _KEY_VALUE_FULL_INFORMATION *
0x1400bd9a2  call    ?CompareDeviceVIDPID@@YAHU_UNICODE_STRING@@PEAU_KEY_VALUE_FULL_INFORMATION@@K@Z; CompareDeviceVIDPID(_UNICODE_STRING,_KEY_VALUE_FULL_INFORMATION *,ulong)
0x1400bd9a7  xor     r12d, r12d
0x1400bd9aa  test    eax, eax
0x1400bd9ac  jnz     loc_1400BDA74
0x1400bd9b2  mov     rcx, rsi; Buffer
0x1400bd9b5  call    GreDeleteFastMutex
0x1400bd9ba  add     ebx, edi
0x1400bd9bc  jmp     loc_1400BD8A1
0x1400bd9c1  cmp     r15d, 8000001Ah
0x1400bd9c8  jnz     loc_1400BDB21
0x1400bd9ce  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400bd9d2  call    cs:__imp_ZwClose
0x1400bd9d9  nop     dword ptr [rax+rax+00h]
0x1400bd9de  mov     rbx, [rsp+0E0h+arg_8]
0x1400bd9e6  mov     eax, r14d
0x1400bd9e9  add     rsp, 0B0h
0x1400bd9f0  pop     r15
0x1400bd9f2  pop     r14
0x1400bd9f4  pop     r13
0x1400bd9f6  pop     r12
0x1400bd9f8  pop     rdi
0x1400bd9f9  pop     rsi
0x1400bd9fa  pop     rbp
0x1400bd9fb  retn
0x1400bd9fd  mov     eax, [rbp+57h+arg_18]
0x1400bda00  test    eax, eax
0x1400bda02  jz      loc_1400BD87C
0x1400bda08  mov     edx, eax; unsigned __int64
0x1400bda0a  mov     ecx, 100h; unsigned __int64
0x1400bda0f  mov     r8d, 78657355h; unsigned int
0x1400bda15  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400bda1a  mov     rbx, rax
0x1400bda1d  test    rax, rax
0x1400bda20  jz      short loc_1400BD9CE
0x1400bda22  mov     ecx, [rbp+57h+arg_18]
0x1400bda25  lea     rax, [rbp+57h+arg_18]
0x1400bda29  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400bda2e  mov     r9, rbx; KeyValueInformation
0x1400bda31  mov     [rsp+0E0h+Length], ecx; Length
0x1400bda35  mov     r8d, esi; KeyValueInformationClass
0x1400bda38  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400bda3c  mov     rdx, r13; ValueName
0x1400bda3f  call    cs:__imp_ZwQueryValueKey
0x1400bda46  nop     dword ptr [rax+rax+00h]
0x1400bda4b  test    eax, eax
0x1400bda4d  js      short loc_1400BDA67
0x1400bda4f  cmp     dword ptr [rbx+4], 4
0x1400bda53  jnz     short loc_1400BDA67
0x1400bda55  mov     al, [rbx+0Ch]
0x1400bda58  mov     edi, 1
0x1400bda5d  sub     al, dil
0x1400bda60  cmp     al, sil
0x1400bda63  cmovbe  r14d, edi
0x1400bda67  mov     rcx, rbx; Buffer
0x1400bda6a  call    GreDeleteFastMutex
0x1400bda6f  jmp     loc_1400BD9CE
0x1400bda74  mov     r14d, edi
0x1400bda77  jmp     loc_1400BD9B2
0x1400bda7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bda83  lea     rax, WPP_GLOBAL_Control
0x1400bda8a  cmp     rcx, rax
0x1400bda8d  jz      short loc_1400BDAA2
0x1400bda8f  mov     eax, [rcx+2Ch]
0x1400bda92  test    dil, al
0x1400bda95  jz      short loc_1400BDAA2
0x1400bda97  cmp     byte ptr [rcx+29h], 4
0x1400bda9b  jb      short loc_1400BDAA2
0x1400bda9d  mov     r12b, dil
0x1400bdaa0  jmp     short loc_1400BDAA5
0x1400bdaa2  xor     r12b, r12b
0x1400bdaa5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400bdaac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400bdab3  setnz   al
0x1400bdab6  mov     [rbp+57h+arg_0], al
0x1400bdab9  test    r12b, r12b
0x1400bdabc  jnz     short loc_1400BDAC2
0x1400bdabe  test    al, al
0x1400bdac0  jz      short loc_1400BDB19
0x1400bdac2  mov     ebx, [rsi+10h]
0x1400bdac5  call    cs:__imp_W32GetUserSessionState
0x1400bdacc  nop     dword ptr [rax+rax+00h]
0x1400bdad1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bdad8  mov     dl, r12b
0x1400bdadb  mov     r8b, [rbp+57h+arg_0]
0x1400bdadf  mov     [rsp+0E0h+var_98], ebx
0x1400bdae3  mov     r9, [rax+4BD0h]
0x1400bdaea  mov     eax, [rbp+57h+var_88]
0x1400bdaed  mov     rcx, [rcx+18h]
0x1400bdaf1  mov     [rsp+0E0h+var_A0], eax
0x1400bdaf5  lea     rax, WPP_b554531fceee36eb2b750301196162e5_Traceguids
0x1400bdafc  mov     [rsp+0E0h+var_A8], rax
0x1400bdb01  mov     [rsp+0E0h+var_B0], 10h
0x1400bdb08  mov     dword ptr [rsp+0E0h+ResultLength], edi
0x1400bdb0c  mov     byte ptr [rsp+0E0h+Length], 4
0x1400bdb11  call    WPP_RECORDER_AND_TRACE_SF_DD
0x1400bdb16  mov     ebx, [rbp+57h+var_8C]
0x1400bdb19  xor     r12d, r12d
0x1400bdb1c  jmp     loc_1400BD9B2
0x1400bdb21  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bdb28  lea     rax, WPP_GLOBAL_Control
0x1400bdb2f  cmp     rcx, rax
0x1400bdb32  jz      short loc_1400BDB45
0x1400bdb34  mov     eax, [rcx+2Ch]
0x1400bdb37  test    dil, al
0x1400bdb3a  jz      short loc_1400BDB45
0x1400bdb3c  cmp     byte ptr [rcx+29h], 3
0x1400bdb40  mov     bl, dil
0x1400bdb43  jnb     short loc_1400BDB48
0x1400bdb45  mov     bl, r12b
0x1400bdb48  lea     rax, WPP_RECORDER_INITIALIZED
0x1400bdb4f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400bdb56  setnz   sil
0x1400bdb5a  test    bl, bl
0x1400bdb5c  jnz     short loc_1400BDB67
0x1400bdb5e  test    sil, sil
0x1400bdb61  jz      loc_1400BD9CE
0x1400bdb67  call    cs:__imp_W32GetUserSessionState
0x1400bdb6e  nop     dword ptr [rax+rax+00h]
0x1400bdb73  mov     [rsp+0E0h+var_A0], r15d
0x1400bdb78  lea     rcx, WPP_b554531fceee36eb2b750301196162e5_Traceguids
0x1400bdb7f  mov     [rsp+0E0h+var_A8], rcx
0x1400bdb84  mov     r8b, sil
0x1400bdb87  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bdb8e  mov     dl, bl
0x1400bdb90  mov     r9, [rax+4BD0h]
0x1400bdb97  mov     [rsp+0E0h+var_B0], 11h
0x1400bdb9e  mov     dword ptr [rsp+0E0h+ResultLength], edi
0x1400bdba2  mov     rcx, [rcx+18h]
0x1400bdba6  mov     byte ptr [rsp+0E0h+Length], 3
0x1400bdbab  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400bdbb0  jmp     loc_1400BD9CE
```
