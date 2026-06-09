# IsDeviceOnRegistryList(_UNICODE_STRING,_UNICODE_STRING,int)

- ea: `0x1400d6ee4`
- end: `0x1400d72c5`
- name: `?IsDeviceOnRegistryList@@YAHU_UNICODE_STRING@@0H@Z`
- size: `993`
- prototype: `int(struct _UNICODE_STRING *__struct_ptr, struct _UNICODE_STRING *__struct_ptr, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400d5940`
- `0x1400d6df0`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x14009ff00`
- `0x1400cb450`
- `0x1400d6ee4`
- `0x1400d72cc`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400d6f41`
- `ntoskrnl!ZwOpenKey` at `0x1400d6f41`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d6f75`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d714f`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d6f75`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d714f`
- `ntoskrnl!ZwClose` at `0x1400d70e2`
- `ntoskrnl!ZwClose` at `0x1400d70e2`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400d6fe4`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400d7039`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400d6fe4`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400d7039`
- `ntoskrnl!RtlCompareMemory` at `0x1400d7088`
- `ntoskrnl!RtlCompareMemory` at `0x1400d7088`
- `WIN32K!W32GetUserSessionState` at `0x1400d71d5`
- `WIN32K!W32GetUserSessionState` at `0x1400d7277`
- `WIN32K!W32GetUserSessionState` at `0x1400d71d5`
- `WIN32K!W32GetUserSessionState` at `0x1400d7277`

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
0x1400d6ee4  mov     [rsp-8+arg_8], rbx
0x1400d6ee9  push    rbp
0x1400d6eea  push    rsi
0x1400d6eeb  push    rdi
0x1400d6eec  push    r12
0x1400d6eee  push    r13
0x1400d6ef0  push    r14
0x1400d6ef2  push    r15
0x1400d6ef4  lea     rbp, [rsp-27h]
0x1400d6ef9  sub     rsp, 0B0h
0x1400d6f00  xor     r12d, r12d
0x1400d6f03  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x1400d6f07  mov     ebx, r8d
0x1400d6f0a  mov     [rbp+57h+KeyHandle], r12
0x1400d6f0e  mov     r13, rdx
0x1400d6f11  mov     [rbp+57h+arg_18], r12d
0x1400d6f15  xorps   xmm0, xmm0
0x1400d6f18  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1400d6f1c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400d6f20  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400d6f28  mov     edx, 20019h; DesiredAccess
0x1400d6f2d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400d6f35  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400d6f39  mov     r14d, r12d
0x1400d6f3c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d6f41  call    cs:__imp_ZwOpenKey
0x1400d6f48  nop     dword ptr [rax+rax+00h]
0x1400d6f4d  test    eax, eax
0x1400d6f4f  js      loc_1400D70EE
0x1400d6f55  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400d6f59  lea     rax, [rbp+57h+arg_18]
0x1400d6f5d  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400d6f62  lea     esi, [r12+2]
0x1400d6f67  mov     r8d, esi; KeyValueInformationClass
0x1400d6f6a  mov     [rsp+0E0h+Length], r12d; Length
0x1400d6f6f  xor     r9d, r9d; KeyValueInformation
0x1400d6f72  mov     rdx, r13; ValueName
0x1400d6f75  call    cs:__imp_ZwQueryValueKey
0x1400d6f7c  nop     dword ptr [rax+rax+00h]
0x1400d6f81  cmp     eax, 0C0000034h
0x1400d6f86  jnz     loc_1400D710D
0x1400d6f8c  test    ebx, ebx
0x1400d6f8e  jz      loc_1400D70DE
0x1400d6f94  mov     eax, 2Ah ; '*'
0x1400d6f99  cmp     [r13+0], ax
0x1400d6f9e  jb      loc_1400D70DE
0x1400d6fa4  mov     ebx, r12d
0x1400d6fa7  mov     [rbp+57h+var_90], r12d
0x1400d6fab  mov     r15d, r12d
0x1400d6fae  lea     edi, [rax-29h]
0x1400d6fb1  mov     [rbp+57h+var_8C], ebx
0x1400d6fb4  cmp     r15d, 8000001Ah
0x1400d6fbb  jz      loc_1400D70DE
0x1400d6fc1  test    r14d, r14d
0x1400d6fc4  jnz     loc_1400D70DE
0x1400d6fca  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400d6fce  lea     rax, [rbp+57h+var_90]
0x1400d6fd2  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400d6fd7  xor     r9d, r9d; KeyValueInformation
0x1400d6fda  mov     r8d, edi; KeyValueInformationClass
0x1400d6fdd  mov     [rsp+0E0h+Length], r12d; Length
0x1400d6fe2  mov     edx, ebx; Index
0x1400d6fe4  call    cs:__imp_ZwEnumerateValueKey
0x1400d6feb  nop     dword ptr [rax+rax+00h]
0x1400d6ff0  mov     r15d, eax
0x1400d6ff3  cmp     eax, 0C0000023h
0x1400d6ff8  jnz     loc_1400D70D1
0x1400d6ffe  mov     edx, [rbp+57h+var_90]; unsigned __int64
0x1400d7001  mov     ecx, 100h; unsigned __int64
0x1400d7006  mov     r8d, 78657355h; unsigned int
0x1400d700c  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400d7011  mov     rsi, rax
0x1400d7014  test    rax, rax
0x1400d7017  jz      loc_1400D70CA
0x1400d701d  mov     ecx, [rbp+57h+var_90]
0x1400d7020  lea     rax, [rbp+57h+var_90]
0x1400d7024  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400d7029  mov     r9, rsi; KeyValueInformation
0x1400d702c  mov     [rsp+0E0h+Length], ecx; Length
0x1400d7030  mov     r8d, edi; KeyValueInformationClass
0x1400d7033  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400d7037  mov     edx, ebx; Index
0x1400d7039  call    cs:__imp_ZwEnumerateValueKey
0x1400d7040  nop     dword ptr [rax+rax+00h]
0x1400d7045  mov     r15d, eax
0x1400d7048  test    eax, eax
0x1400d704a  js      short loc_1400D70C2
0x1400d704c  mov     eax, [rsi+8]
0x1400d704f  movzx   r12d, byte ptr [rax+rsi]
0x1400d7054  mov     [rbp+57h+var_88], r12d
0x1400d7058  lea     eax, [r12-1]
0x1400d705d  cmp     eax, edi
0x1400d705f  ja      loc_1400D718C
0x1400d7065  cmp     dword ptr [rsi+4], 4
0x1400d7069  jnz     loc_1400D718C
0x1400d706f  cmp     dword ptr [rsi+10h], 2Ah ; '*'
0x1400d7073  jb      loc_1400D718C
0x1400d7079  lea     rcx, [rsi+14h]; Source1
0x1400d707d  lea     r8d, [r14+6]; Length
0x1400d7081  lea     rdx, aHid_0; "HID"
0x1400d7088  call    cs:__imp_RtlCompareMemory
0x1400d708f  nop     dword ptr [rax+rax+00h]
0x1400d7094  cmp     rax, 6
0x1400d7098  jnz     loc_1400D718C
0x1400d709e  movaps  xmm0, xmmword ptr [r13+0]
0x1400d70a3  lea     rcx, [rbp+57h+var_70]; struct _UNICODE_STRING
0x1400d70a7  mov     r8d, r12d; unsigned int
0x1400d70aa  movdqa  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x1400d70af  mov     rdx, rsi; struct _KEY_VALUE_FULL_INFORMATION *
0x1400d70b2  call    ?CompareDeviceVIDPID@@YAHU_UNICODE_STRING@@PEAU_KEY_VALUE_FULL_INFORMATION@@K@Z; CompareDeviceVIDPID(_UNICODE_STRING,_KEY_VALUE_FULL_INFORMATION *,ulong)
0x1400d70b7  xor     r12d, r12d
0x1400d70ba  test    eax, eax
0x1400d70bc  jnz     loc_1400D7184
0x1400d70c2  mov     rcx, rsi; Buffer
0x1400d70c5  call    GreDeleteFastMutex
0x1400d70ca  add     ebx, edi
0x1400d70cc  jmp     loc_1400D6FB1
0x1400d70d1  cmp     r15d, 8000001Ah
0x1400d70d8  jnz     loc_1400D7231
0x1400d70de  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400d70e2  call    cs:__imp_ZwClose
0x1400d70e9  nop     dword ptr [rax+rax+00h]
0x1400d70ee  mov     rbx, [rsp+0E0h+arg_8]
0x1400d70f6  mov     eax, r14d
0x1400d70f9  add     rsp, 0B0h
0x1400d7100  pop     r15
0x1400d7102  pop     r14
0x1400d7104  pop     r13
0x1400d7106  pop     r12
0x1400d7108  pop     rdi
0x1400d7109  pop     rsi
0x1400d710a  pop     rbp
0x1400d710b  retn
0x1400d710d  mov     eax, [rbp+57h+arg_18]
0x1400d7110  test    eax, eax
0x1400d7112  jz      loc_1400D6F8C
0x1400d7118  mov     edx, eax; unsigned __int64
0x1400d711a  mov     ecx, 100h; unsigned __int64
0x1400d711f  mov     r8d, 78657355h; unsigned int
0x1400d7125  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400d712a  mov     rbx, rax
0x1400d712d  test    rax, rax
0x1400d7130  jz      short loc_1400D70DE
0x1400d7132  mov     ecx, [rbp+57h+arg_18]
0x1400d7135  lea     rax, [rbp+57h+arg_18]
0x1400d7139  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400d713e  mov     r9, rbx; KeyValueInformation
0x1400d7141  mov     [rsp+0E0h+Length], ecx; Length
0x1400d7145  mov     r8d, esi; KeyValueInformationClass
0x1400d7148  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400d714c  mov     rdx, r13; ValueName
0x1400d714f  call    cs:__imp_ZwQueryValueKey
0x1400d7156  nop     dword ptr [rax+rax+00h]
0x1400d715b  test    eax, eax
0x1400d715d  js      short loc_1400D7177
0x1400d715f  cmp     dword ptr [rbx+4], 4
0x1400d7163  jnz     short loc_1400D7177
0x1400d7165  mov     al, [rbx+0Ch]
0x1400d7168  mov     edi, 1
0x1400d716d  sub     al, dil
0x1400d7170  cmp     al, sil
0x1400d7173  cmovbe  r14d, edi
0x1400d7177  mov     rcx, rbx; Buffer
0x1400d717a  call    GreDeleteFastMutex
0x1400d717f  jmp     loc_1400D70DE
0x1400d7184  mov     r14d, edi
0x1400d7187  jmp     loc_1400D70C2
0x1400d718c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7193  lea     rax, WPP_GLOBAL_Control
0x1400d719a  cmp     rcx, rax
0x1400d719d  jz      short loc_1400D71B2
0x1400d719f  mov     eax, [rcx+2Ch]
0x1400d71a2  test    dil, al
0x1400d71a5  jz      short loc_1400D71B2
0x1400d71a7  cmp     byte ptr [rcx+29h], 4
0x1400d71ab  jb      short loc_1400D71B2
0x1400d71ad  mov     r12b, dil
0x1400d71b0  jmp     short loc_1400D71B5
0x1400d71b2  xor     r12b, r12b
0x1400d71b5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d71bc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d71c3  setnz   al
0x1400d71c6  mov     [rbp+57h+arg_0], al
0x1400d71c9  test    r12b, r12b
0x1400d71cc  jnz     short loc_1400D71D2
0x1400d71ce  test    al, al
0x1400d71d0  jz      short loc_1400D7229
0x1400d71d2  mov     ebx, [rsi+10h]
0x1400d71d5  call    cs:__imp_W32GetUserSessionState
0x1400d71dc  nop     dword ptr [rax+rax+00h]
0x1400d71e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d71e8  mov     dl, r12b
0x1400d71eb  mov     r8b, [rbp+57h+arg_0]
0x1400d71ef  mov     [rsp+0E0h+var_98], ebx
0x1400d71f3  mov     r9, [rax+4BD0h]
0x1400d71fa  mov     eax, [rbp+57h+var_88]
0x1400d71fd  mov     rcx, [rcx+18h]
0x1400d7201  mov     [rsp+0E0h+var_A0], eax
0x1400d7205  lea     rax, WPP_b554531fceee36eb2b750301196162e5_Traceguids
0x1400d720c  mov     [rsp+0E0h+var_A8], rax
0x1400d7211  mov     [rsp+0E0h+var_B0], 10h
0x1400d7218  mov     dword ptr [rsp+0E0h+ResultLength], edi
0x1400d721c  mov     byte ptr [rsp+0E0h+Length], 4
0x1400d7221  call    WPP_RECORDER_AND_TRACE_SF_DD
0x1400d7226  mov     ebx, [rbp+57h+var_8C]
0x1400d7229  xor     r12d, r12d
0x1400d722c  jmp     loc_1400D70C2
0x1400d7231  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7238  lea     rax, WPP_GLOBAL_Control
0x1400d723f  cmp     rcx, rax
0x1400d7242  jz      short loc_1400D7255
0x1400d7244  mov     eax, [rcx+2Ch]
0x1400d7247  test    dil, al
0x1400d724a  jz      short loc_1400D7255
0x1400d724c  cmp     byte ptr [rcx+29h], 3
0x1400d7250  mov     bl, dil
0x1400d7253  jnb     short loc_1400D7258
0x1400d7255  mov     bl, r12b
0x1400d7258  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d725f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d7266  setnz   sil
0x1400d726a  test    bl, bl
0x1400d726c  jnz     short loc_1400D7277
0x1400d726e  test    sil, sil
0x1400d7271  jz      loc_1400D70DE
0x1400d7277  call    cs:__imp_W32GetUserSessionState
0x1400d727e  nop     dword ptr [rax+rax+00h]
0x1400d7283  mov     [rsp+0E0h+var_A0], r15d
0x1400d7288  lea     rcx, WPP_b554531fceee36eb2b750301196162e5_Traceguids
0x1400d728f  mov     [rsp+0E0h+var_A8], rcx
0x1400d7294  mov     r8b, sil
0x1400d7297  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d729e  mov     dl, bl
0x1400d72a0  mov     r9, [rax+4BD0h]
0x1400d72a7  mov     [rsp+0E0h+var_B0], 11h
0x1400d72ae  mov     dword ptr [rsp+0E0h+ResultLength], edi
0x1400d72b2  mov     rcx, [rcx+18h]
0x1400d72b6  mov     byte ptr [rsp+0E0h+Length], 3
0x1400d72bb  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400d72c0  jmp     loc_1400D70DE
```
