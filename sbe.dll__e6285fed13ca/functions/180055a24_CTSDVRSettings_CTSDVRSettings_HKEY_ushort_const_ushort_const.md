# CTSDVRSettings::CTSDVRSettings(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180055a24`
- end: `0x180055baa`
- name: `??0CTSDVRSettings@@QEAA@PEAUHKEY__@@PEBG1@Z`
- size: `390`
- prototype: `CTSDVRSettings *__fastcall(CTSDVRSettings *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055980`

## callees

- `0x180001c00`
- `0x180002974`
- `0x180055a24`
- `0x1800565e0`
- `0x1800569e8`
- `0x18005f818`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180055a7e`
- `KERNEL32!InitializeCriticalSection` at `0x180055a7e`
- `ADVAPI32!RegCloseKey` at `0x180055ae0`
- `ADVAPI32!RegCloseKey` at `0x180055ae0`
- `ADVAPI32!RegCreateKeyExW` at `0x180055ac1`
- `ADVAPI32!RegCreateKeyExW` at `0x180055b1a`
- `ADVAPI32!RegCreateKeyExW` at `0x180055ac1`
- `ADVAPI32!RegCreateKeyExW` at `0x180055b1a`

## pseudocode

```c
CTSDVRSettings *__fastcall CTSDVRSettings::CTSDVRSettings(
        CTSDVRSettings *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  _DWORD *v6; // rdi
  __int64 v7; // rdx
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  `vector constructor iterator'(
    (char *)this + 584,
    8u,
    0x58u,
    CTSDVRSettings::CTRegVal<unsigned long>::CTRegVal<unsigned long>);
  v6 = (_DWORD *)((char *)this + 1288);
  *((_DWORD *)this + 322) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_WORD *)this + 32) = 0;
  hKey = 0;
  if ( !RegCreateKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft", 0, 0, 0, 0x2001Fu, 0, &hKey, 0) )
  {
    CTSDVRSettings::SetDVRRegKey(this, hKey, a4);
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( RegCreateKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\DVR", 0, 0, 0, 0x2001Fu, 0, (PHKEY)this, 0) )
  {
    *(_QWORD *)this = 0;
  }
  else
  {
    v7 = *(_QWORD *)this;
    *v6 = 0;
    CTSDVRSettings::GetValLocked_(this, v7, L"Stats", 0, 0, (char *)this + 1288);
    *v6 = 1;
  }
  g_fRegGenericStreams_Video = 0;
  GetRegDWORDValIfExist(*((HKEY *)this + 1), L"Video_UseGenericStreams", &g_fRegGenericStreams_Video);
  g_fRegGenericStreams_Audio = 1;
  GetRegDWORDValIfExist(*((HKEY *)this + 1), L"Audio_UseGenericStreams", &g_fRegGenericStreams_Audio);
  return this;
}

```

## disassembly

```asm
0x180055a24  mov     [rsp+arg_8], rbx
0x180055a29  push    rbp
0x180055a2a  push    rsi
0x180055a2b  push    rdi
0x180055a2c  sub     rsp, 60h
0x180055a30  mov     rax, cs:__security_cookie
0x180055a37  xor     rax, rsp
0x180055a3a  mov     [rsp+78h+var_20], rax
0x180055a3f  xor     ebp, ebp
0x180055a41  mov     rsi, r9
0x180055a44  mov     rbx, rcx
0x180055a47  mov     [rcx], rbp
0x180055a4a  mov     [rcx+8], rbp
0x180055a4e  lea     r9, ??0?$CTRegVal@K@CTSDVRSettings@@QEAA@XZ; void *(*)(void *)
0x180055a55  mov     [rcx+10h], rbp
0x180055a59  add     rcx, 248h; void *
0x180055a60  lea     edx, [rbp+8]; unsigned __int64
0x180055a63  lea     r8d, [rbp+58h]; unsigned __int64
0x180055a67  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180055a6c  lea     rdi, [rbx+508h]
0x180055a73  mov     [rsp+78h+hKey], rbp
0x180055a78  lea     rcx, [rbx+18h]; lpCriticalSection
0x180055a7c  mov     [rdi], ebp
0x180055a7e  call    cs:__imp_InitializeCriticalSection
0x180055a84  mov     [rsp+78h+lpdwDisposition], rbp; lpdwDisposition
0x180055a89  lea     rax, [rsp+78h+hKey]
0x180055a8e  mov     [rsp+78h+phkResult], rax; phkResult
0x180055a93  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft"
0x180055a9a  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x180055a9f  xor     r9d, r9d; lpClass
0x180055aa2  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180055aaa  xor     r8d, r8d; Reserved
0x180055aad  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180055ab4  mov     [rsp+78h+dwOptions], ebp; dwOptions
0x180055ab8  mov     [rbx+40h], bp
0x180055abc  mov     [rsp+78h+hKey], rbp
0x180055ac1  call    cs:__imp_RegCreateKeyExW
0x180055ac7  test    eax, eax
0x180055ac9  jnz     short loc_180055AEB
0x180055acb  mov     rdx, [rsp+78h+hKey]; hKey
0x180055ad0  mov     r8, rsi; lpSubKey
0x180055ad3  mov     rcx, rbx; this
0x180055ad6  call    ?SetDVRRegKey@CTSDVRSettings@@QEAAJPEAUHKEY__@@PEBG@Z; CTSDVRSettings::SetDVRRegKey(HKEY__ *,ushort const *)
0x180055adb  mov     rcx, [rsp+78h+hKey]; hKey
0x180055ae0  call    cs:__imp_RegCloseKey
0x180055ae6  mov     [rsp+78h+hKey], rbp
0x180055aeb  mov     [rsp+78h+lpdwDisposition], rbp; lpdwDisposition
0x180055af0  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\DVR"
0x180055af7  mov     [rsp+78h+phkResult], rbx; phkResult
0x180055afc  xor     r9d, r9d; lpClass
0x180055aff  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x180055b04  xor     r8d, r8d; Reserved
0x180055b07  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180055b0f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180055b16  mov     [rsp+78h+dwOptions], ebp; dwOptions
0x180055b1a  call    cs:__imp_RegCreateKeyExW
0x180055b20  mov     esi, 1
0x180055b25  test    eax, eax
0x180055b27  jnz     short loc_180055B4D
0x180055b29  mov     rdx, [rbx]
0x180055b2c  lea     r8, aStats; "Stats"
0x180055b33  mov     qword ptr [rsp+78h+samDesired], rdi
0x180055b38  xor     r9d, r9d
0x180055b3b  mov     rcx, rbx
0x180055b3e  mov     [rsp+78h+dwOptions], ebp
0x180055b42  mov     [rdi], ebp
0x180055b44  call    ?GetValLocked_@CTSDVRSettings@@AEAAKPEAUHKEY__@@PEBGHKPEAU?$CTRegVal@K@1@@Z; CTSDVRSettings::GetValLocked_(HKEY__ *,ushort const *,int,ulong,CTSDVRSettings::CTRegVal<ulong> *)
0x180055b49  mov     [rdi], esi
0x180055b4b  jmp     short loc_180055B50
0x180055b4d  mov     [rbx], rbp
0x180055b50  mov     cs:?g_fRegGenericStreams_Video@@3HA, ebp; int g_fRegGenericStreams_Video
0x180055b56  lea     r8, ?g_fRegGenericStreams_Video@@3HA; unsigned int *
0x180055b5d  mov     rcx, [rbx+8]; HKEY
0x180055b61  lea     rdx, aVideoUsegeneri; "Video_UseGenericStreams"
0x180055b68  call    ?GetRegDWORDValIfExist@@YAHPEAUHKEY__@@PEBGPEAK@Z; GetRegDWORDValIfExist(HKEY__ *,ushort const *,ulong *)
0x180055b6d  mov     cs:?g_fRegGenericStreams_Audio@@3HA, esi; int g_fRegGenericStreams_Audio
0x180055b73  lea     r8, ?g_fRegGenericStreams_Audio@@3HA; unsigned int *
0x180055b7a  mov     rcx, [rbx+8]; HKEY
0x180055b7e  lea     rdx, aAudioUsegeneri; "Audio_UseGenericStreams"
0x180055b85  call    ?GetRegDWORDValIfExist@@YAHPEAUHKEY__@@PEBGPEAK@Z; GetRegDWORDValIfExist(HKEY__ *,ushort const *,ulong *)
0x180055b8a  mov     rax, rbx
0x180055b8d  mov     rcx, [rsp+78h+var_20]
0x180055b92  xor     rcx, rsp; StackCookie
0x180055b95  call    __security_check_cookie
0x180055b9a  mov     rbx, [rsp+78h+arg_8]
0x180055ba2  add     rsp, 60h
0x180055ba6  pop     rdi
0x180055ba7  pop     rsi
0x180055ba8  pop     rbp
0x180055ba9  retn
```
