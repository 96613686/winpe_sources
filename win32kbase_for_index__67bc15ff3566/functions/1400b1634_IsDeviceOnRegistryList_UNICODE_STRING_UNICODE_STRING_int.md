# IsDeviceOnRegistryList(_UNICODE_STRING,_UNICODE_STRING,int)

- ea: `0x1400b1634`
- end: `0x1400b1a15`
- name: `?IsDeviceOnRegistryList@@YAHU_UNICODE_STRING@@0H@Z`
- size: `993`
- prototype: `int(struct _UNICODE_STRING *__struct_ptr, struct _UNICODE_STRING *__struct_ptr, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400b0090`
- `0x1400b1540`

## callees

- `0x140069e00`
- `0x14007b930`
- `0x14007efd0`
- `0x1400a5ba0`
- `0x1400b1634`
- `0x1400b1a1c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400b1691`
- `ntoskrnl!ZwOpenKey` at `0x1400b1691`
- `ntoskrnl!ZwQueryValueKey` at `0x1400b16c5`
- `ntoskrnl!ZwQueryValueKey` at `0x1400b189f`
- `ntoskrnl!ZwQueryValueKey` at `0x1400b16c5`
- `ntoskrnl!ZwQueryValueKey` at `0x1400b189f`
- `ntoskrnl!ZwClose` at `0x1400b1832`
- `ntoskrnl!ZwClose` at `0x1400b1832`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400b1734`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400b1789`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400b1734`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400b1789`
- `ntoskrnl!RtlCompareMemory` at `0x1400b17d8`
- `ntoskrnl!RtlCompareMemory` at `0x1400b17d8`
- `WIN32K!W32GetUserSessionState` at `0x1400b1925`
- `WIN32K!W32GetUserSessionState` at `0x1400b19c7`
- `WIN32K!W32GetUserSessionState` at `0x1400b1925`
- `WIN32K!W32GetUserSessionState` at `0x1400b19c7`

## pseudocode

```c
_BOOL8 __fastcall IsDeviceOnRegistryList(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2, int a3)
{
  BOOL v5; // r14d
  ULONG v6; // ebx
  NTSTATUS v7; // r15d
  __int64 v8; // rdx
  __int64 v9; // r8
  struct _KEY_VALUE_FULL_INFORMATION *v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // r12d
  _BYTE *v15; // rbx
  bool v16; // r12
  ULONG NameLength; // ebx
  __int64 v18; // rax
  int v19; // edx
  int v20; // r8d
  char v21; // bl
  bool v22; // si
  __int64 UserSessionState; // rax
  int v24; // r8d
  int v25; // edx
  ULONG Length; // [rsp+50h] [rbp-39h] BYREF
  ULONG v27; // [rsp+54h] [rbp-35h]
  unsigned int v28; // [rsp+58h] [rbp-31h]
  void *KeyHandle; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING v30; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  bool v32; // [rsp+F0h] [rbp+67h]
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
          v27 = v6;
          if ( v7 == -2147483622 || v5 )
            break;
          v7 = ZwEnumerateValueKey(KeyHandle, v6, KeyValueFullInformation, 0, 0, &Length);
          if ( v7 != -1073741789 )
          {
            if ( v7 != -2147483622 )
            {
              if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
                || (v21 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
              {
                v21 = 0;
              }
              v22 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              if ( v21 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control, v8, v9);
                LOBYTE(v24) = v22;
                LOBYTE(v25) = v21;
                WPP_RECORDER_AND_TRACE_SF_D(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  v25,
                  v24,
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
          v10 = (struct _KEY_VALUE_FULL_INFORMATION *)Win32AllocPoolZInitImpl(0x100u, Length, 0x78657355u);
          if ( v10 )
          {
            v7 = ZwEnumerateValueKey(KeyHandle, v6, KeyValueFullInformation, v10, Length, &Length);
            if ( v7 >= 0 )
            {
              v13 = *((unsigned __int8 *)&v10->TitleIndex + v10->DataOffset);
              v28 = v13;
              if ( v13 - 1 <= 1
                && v10->Type == 4
                && v10->NameLength >= 0x2A
                && RtlCompareMemory(v10->Name, L"HID", 6u) == 6 )
              {
                v30 = *a2;
                v5 = CompareDeviceVIDPID(&v30, v10, v13) != 0;
              }
              else
              {
                v16 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
                v32 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  NameLength = v10->NameLength;
                  v18 = W32GetUserSessionState(WPP_GLOBAL_Control, v11, v12);
                  LOBYTE(v19) = v16;
                  LOBYTE(v20) = v32;
                  WPP_RECORDER_AND_TRACE_SF_DD(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    v19,
                    v20,
                    *(_QWORD *)(v18 + 19408),
                    4,
                    1,
                    16,
                    (__int64)WPP_b554531fceee36eb2b750301196162e5_Traceguids,
                    v28,
                    NameLength);
                  v6 = v27;
                }
              }
            }
            GreDeleteFastMutex(v10);
          }
          ++v6;
        }
      }
    }
    else
    {
      v15 = Win32AllocPoolZInitImpl(0x100u, ResultLength, 0x78657355u);
      if ( v15 )
      {
        if ( ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, v15, ResultLength, &ResultLength) >= 0
          && *((_DWORD *)v15 + 1) == 4 )
        {
          v5 = (unsigned __int8)(v15[12] - 1) <= 2u;
        }
        GreDeleteFastMutex(v15);
      }
    }
    ZwClose(KeyHandle);
  }
  return v5;
}

```

## disassembly

```asm
0x1400b1634  mov     [rsp-8+arg_8], rbx
0x1400b1639  push    rbp
0x1400b163a  push    rsi
0x1400b163b  push    rdi
0x1400b163c  push    r12
0x1400b163e  push    r13
0x1400b1640  push    r14
0x1400b1642  push    r15
0x1400b1644  lea     rbp, [rsp-27h]
0x1400b1649  sub     rsp, 0B0h
0x1400b1650  xor     r12d, r12d
0x1400b1653  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x1400b1657  mov     ebx, r8d
0x1400b165a  mov     [rbp+57h+KeyHandle], r12
0x1400b165e  mov     r13, rdx
0x1400b1661  mov     [rbp+57h+arg_18], r12d
0x1400b1665  xorps   xmm0, xmm0
0x1400b1668  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1400b166c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400b1670  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400b1678  mov     edx, 20019h; DesiredAccess
0x1400b167d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400b1685  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400b1689  mov     r14d, r12d
0x1400b168c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400b1691  call    cs:__imp_ZwOpenKey
0x1400b1698  nop     dword ptr [rax+rax+00h]
0x1400b169d  test    eax, eax
0x1400b169f  js      loc_1400B183E
0x1400b16a5  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400b16a9  lea     rax, [rbp+57h+arg_18]
0x1400b16ad  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400b16b2  lea     esi, [r12+2]
0x1400b16b7  mov     r8d, esi; KeyValueInformationClass
0x1400b16ba  mov     [rsp+0E0h+Length], r12d; Length
0x1400b16bf  xor     r9d, r9d; KeyValueInformation
0x1400b16c2  mov     rdx, r13; ValueName
0x1400b16c5  call    cs:__imp_ZwQueryValueKey
0x1400b16cc  nop     dword ptr [rax+rax+00h]
0x1400b16d1  cmp     eax, 0C0000034h
0x1400b16d6  jnz     loc_1400B185D
0x1400b16dc  test    ebx, ebx
0x1400b16de  jz      loc_1400B182E
0x1400b16e4  mov     eax, 2Ah ; '*'
0x1400b16e9  cmp     [r13+0], ax
0x1400b16ee  jb      loc_1400B182E
0x1400b16f4  mov     ebx, r12d
0x1400b16f7  mov     [rbp+57h+var_90], r12d
0x1400b16fb  mov     r15d, r12d
0x1400b16fe  lea     edi, [rax-29h]
0x1400b1701  mov     [rbp+57h+var_8C], ebx
0x1400b1704  cmp     r15d, 8000001Ah
0x1400b170b  jz      loc_1400B182E
0x1400b1711  test    r14d, r14d
0x1400b1714  jnz     loc_1400B182E
0x1400b171a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400b171e  lea     rax, [rbp+57h+var_90]
0x1400b1722  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400b1727  xor     r9d, r9d; KeyValueInformation
0x1400b172a  mov     r8d, edi; KeyValueInformationClass
0x1400b172d  mov     [rsp+0E0h+Length], r12d; Length
0x1400b1732  mov     edx, ebx; Index
0x1400b1734  call    cs:__imp_ZwEnumerateValueKey
0x1400b173b  nop     dword ptr [rax+rax+00h]
0x1400b1740  mov     r15d, eax
0x1400b1743  cmp     eax, 0C0000023h
0x1400b1748  jnz     loc_1400B1821
0x1400b174e  mov     edx, [rbp+57h+var_90]; unsigned __int64
0x1400b1751  mov     ecx, 100h; unsigned __int64
0x1400b1756  mov     r8d, 78657355h; unsigned int
0x1400b175c  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400b1761  mov     rsi, rax
0x1400b1764  test    rax, rax
0x1400b1767  jz      loc_1400B181A
0x1400b176d  mov     ecx, [rbp+57h+var_90]
0x1400b1770  lea     rax, [rbp+57h+var_90]
0x1400b1774  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400b1779  mov     r9, rsi; KeyValueInformation
0x1400b177c  mov     [rsp+0E0h+Length], ecx; Length
0x1400b1780  mov     r8d, edi; KeyValueInformationClass
0x1400b1783  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400b1787  mov     edx, ebx; Index
0x1400b1789  call    cs:__imp_ZwEnumerateValueKey
0x1400b1790  nop     dword ptr [rax+rax+00h]
0x1400b1795  mov     r15d, eax
0x1400b1798  test    eax, eax
0x1400b179a  js      short loc_1400B1812
0x1400b179c  mov     eax, [rsi+8]
0x1400b179f  movzx   r12d, byte ptr [rax+rsi]
0x1400b17a4  mov     [rbp+57h+var_88], r12d
0x1400b17a8  lea     eax, [r12-1]
0x1400b17ad  cmp     eax, edi
0x1400b17af  ja      loc_1400B18DC
0x1400b17b5  cmp     dword ptr [rsi+4], 4
0x1400b17b9  jnz     loc_1400B18DC
0x1400b17bf  cmp     dword ptr [rsi+10h], 2Ah ; '*'
0x1400b17c3  jb      loc_1400B18DC
0x1400b17c9  lea     rcx, [rsi+14h]; Source1
0x1400b17cd  lea     r8d, [r14+6]; Length
0x1400b17d1  lea     rdx, aHid_0; "HID"
0x1400b17d8  call    cs:__imp_RtlCompareMemory
0x1400b17df  nop     dword ptr [rax+rax+00h]
0x1400b17e4  cmp     rax, 6
0x1400b17e8  jnz     loc_1400B18DC
0x1400b17ee  movaps  xmm0, xmmword ptr [r13+0]
0x1400b17f3  lea     rcx, [rbp+57h+var_70]; struct _UNICODE_STRING
0x1400b17f7  mov     r8d, r12d; unsigned int
0x1400b17fa  movdqa  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x1400b17ff  mov     rdx, rsi; struct _KEY_VALUE_FULL_INFORMATION *
0x1400b1802  call    ?CompareDeviceVIDPID@@YAHU_UNICODE_STRING@@PEAU_KEY_VALUE_FULL_INFORMATION@@K@Z; CompareDeviceVIDPID(_UNICODE_STRING,_KEY_VALUE_FULL_INFORMATION *,ulong)
0x1400b1807  xor     r12d, r12d
0x1400b180a  test    eax, eax
0x1400b180c  jnz     loc_1400B18D4
0x1400b1812  mov     rcx, rsi; Buffer
0x1400b1815  call    GreDeleteFastMutex
0x1400b181a  add     ebx, edi
0x1400b181c  jmp     loc_1400B1701
0x1400b1821  cmp     r15d, 8000001Ah
0x1400b1828  jnz     loc_1400B1981
0x1400b182e  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400b1832  call    cs:__imp_ZwClose
0x1400b1839  nop     dword ptr [rax+rax+00h]
0x1400b183e  mov     rbx, [rsp+0E0h+arg_8]
0x1400b1846  mov     eax, r14d
0x1400b1849  add     rsp, 0B0h
0x1400b1850  pop     r15
0x1400b1852  pop     r14
0x1400b1854  pop     r13
0x1400b1856  pop     r12
0x1400b1858  pop     rdi
0x1400b1859  pop     rsi
0x1400b185a  pop     rbp
0x1400b185b  retn
0x1400b185d  mov     eax, [rbp+57h+arg_18]
0x1400b1860  test    eax, eax
0x1400b1862  jz      loc_1400B16DC
0x1400b1868  mov     edx, eax; unsigned __int64
0x1400b186a  mov     ecx, 100h; unsigned __int64
0x1400b186f  mov     r8d, 78657355h; unsigned int
0x1400b1875  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400b187a  mov     rbx, rax
0x1400b187d  test    rax, rax
0x1400b1880  jz      short loc_1400B182E
0x1400b1882  mov     ecx, [rbp+57h+arg_18]
0x1400b1885  lea     rax, [rbp+57h+arg_18]
0x1400b1889  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400b188e  mov     r9, rbx; KeyValueInformation
0x1400b1891  mov     [rsp+0E0h+Length], ecx; Length
0x1400b1895  mov     r8d, esi; KeyValueInformationClass
0x1400b1898  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400b189c  mov     rdx, r13; ValueName
0x1400b189f  call    cs:__imp_ZwQueryValueKey
0x1400b18a6  nop     dword ptr [rax+rax+00h]
0x1400b18ab  test    eax, eax
0x1400b18ad  js      short loc_1400B18C7
0x1400b18af  cmp     dword ptr [rbx+4], 4
0x1400b18b3  jnz     short loc_1400B18C7
0x1400b18b5  mov     al, [rbx+0Ch]
0x1400b18b8  mov     edi, 1
0x1400b18bd  sub     al, dil
0x1400b18c0  cmp     al, sil
0x1400b18c3  cmovbe  r14d, edi
0x1400b18c7  mov     rcx, rbx; Buffer
0x1400b18ca  call    GreDeleteFastMutex
0x1400b18cf  jmp     loc_1400B182E
0x1400b18d4  mov     r14d, edi
0x1400b18d7  jmp     loc_1400B1812
0x1400b18dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b18e3  lea     rax, WPP_GLOBAL_Control
0x1400b18ea  cmp     rcx, rax
0x1400b18ed  jz      short loc_1400B1902
0x1400b18ef  mov     eax, [rcx+2Ch]
0x1400b18f2  test    dil, al
0x1400b18f5  jz      short loc_1400B1902
0x1400b18f7  cmp     byte ptr [rcx+29h], 4
0x1400b18fb  jb      short loc_1400B1902
0x1400b18fd  mov     r12b, dil
0x1400b1900  jmp     short loc_1400B1905
0x1400b1902  xor     r12b, r12b
0x1400b1905  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b190c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b1913  setnz   al
0x1400b1916  mov     [rbp+57h+arg_0], al
0x1400b1919  test    r12b, r12b
0x1400b191c  jnz     short loc_1400B1922
0x1400b191e  test    al, al
0x1400b1920  jz      short loc_1400B1979
0x1400b1922  mov     ebx, [rsi+10h]
0x1400b1925  call    cs:__imp_W32GetUserSessionState
0x1400b192c  nop     dword ptr [rax+rax+00h]
0x1400b1931  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1938  mov     dl, r12b
0x1400b193b  mov     r8b, [rbp+57h+arg_0]
0x1400b193f  mov     [rsp+0E0h+var_98], ebx
0x1400b1943  mov     r9, [rax+4BD0h]
0x1400b194a  mov     eax, [rbp+57h+var_88]
0x1400b194d  mov     rcx, [rcx+18h]
0x1400b1951  mov     [rsp+0E0h+var_A0], eax
0x1400b1955  lea     rax, WPP_b554531fceee36eb2b750301196162e5_Traceguids
0x1400b195c  mov     [rsp+0E0h+var_A8], rax
0x1400b1961  mov     [rsp+0E0h+var_B0], 10h
0x1400b1968  mov     dword ptr [rsp+0E0h+ResultLength], edi
0x1400b196c  mov     byte ptr [rsp+0E0h+Length], 4
0x1400b1971  call    WPP_RECORDER_AND_TRACE_SF_DD
0x1400b1976  mov     ebx, [rbp+57h+var_8C]
0x1400b1979  xor     r12d, r12d
0x1400b197c  jmp     loc_1400B1812
0x1400b1981  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1988  lea     rax, WPP_GLOBAL_Control
0x1400b198f  cmp     rcx, rax
0x1400b1992  jz      short loc_1400B19A5
0x1400b1994  mov     eax, [rcx+2Ch]
0x1400b1997  test    dil, al
0x1400b199a  jz      short loc_1400B19A5
0x1400b199c  cmp     byte ptr [rcx+29h], 3
0x1400b19a0  mov     bl, dil
0x1400b19a3  jnb     short loc_1400B19A8
0x1400b19a5  mov     bl, r12b
0x1400b19a8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b19af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b19b6  setnz   sil
0x1400b19ba  test    bl, bl
0x1400b19bc  jnz     short loc_1400B19C7
0x1400b19be  test    sil, sil
0x1400b19c1  jz      loc_1400B182E
0x1400b19c7  call    cs:__imp_W32GetUserSessionState
0x1400b19ce  nop     dword ptr [rax+rax+00h]
0x1400b19d3  mov     [rsp+0E0h+var_A0], r15d
0x1400b19d8  lea     rcx, WPP_b554531fceee36eb2b750301196162e5_Traceguids
0x1400b19df  mov     [rsp+0E0h+var_A8], rcx
0x1400b19e4  mov     r8b, sil
0x1400b19e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b19ee  mov     dl, bl
0x1400b19f0  mov     r9, [rax+4BD0h]
0x1400b19f7  mov     [rsp+0E0h+var_B0], 11h
0x1400b19fe  mov     dword ptr [rsp+0E0h+ResultLength], edi
0x1400b1a02  mov     rcx, [rcx+18h]
0x1400b1a06  mov     byte ptr [rsp+0E0h+Length], 3
0x1400b1a0b  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400b1a10  jmp     loc_1400B182E
```
