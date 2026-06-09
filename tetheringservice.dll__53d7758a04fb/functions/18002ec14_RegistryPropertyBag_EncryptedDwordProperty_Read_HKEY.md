# RegistryPropertyBag::EncryptedDwordProperty::Read(HKEY__ *)

- ea: `0x18002ec14`
- end: `0x18002ee3b`
- name: `?Read@EncryptedDwordProperty@RegistryPropertyBag@@MEAAJPEAUHKEY__@@@Z`
- size: `551`
- prototype: `__int64 __fastcall(RegistryPropertyBag::EncryptedDwordProperty *this, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002e0c0`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18002ec14`
- `0x18002eff8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ecec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ecec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ede0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ede0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ecad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ed33`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ecad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ed33`
- `ntdll!NtQueryKey` at `0x18002ed8f`
- `ntdll!NtQueryKey` at `0x18002ed8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryPropertyBag::EncryptedDwordProperty::Read(
        RegistryPropertyBag::EncryptedDwordProperty *this,
        HKEY a2)
{
  const WCHAR *v4; // r8
  int ValueW; // eax
  HLOCAL pvData; // rdi
  int v7; // eax
  int v8; // eax
  RegistryPropertyBag::EncryptedDwordProperty *v9; // rcx
  int v10; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength[3]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int KeyInformation; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v15[540]; // [rsp+54h] [rbp-ACh] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
  }
  v4 = (const WCHAR *)*((_QWORD *)this + 3);
  pcbData = 0;
  *((_BYTE *)this + 8) = 0;
  ValueW = RegGetValueW(a2, 0, v4, 8u, 0, 0, &pcbData);
  if ( ValueW > 0 )
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  *((_DWORD *)this + 4) = ValueW;
  if ( ValueW >= 0 )
  {
    if ( pcbData - 1 <= 0xFFF )
    {
      pvData = LocalAlloc(0x40u, pcbData);
      if ( !pvData )
        *((_DWORD *)this + 4) = -2147024882;
      if ( *((int *)this + 4) >= 0 )
      {
        v7 = RegGetValueW(a2, 0, *((LPCWSTR *)this + 3), 0x20000008u, 0, pvData, &pcbData);
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        *((_DWORD *)this + 4) = v7;
        if ( v7 >= 0 )
        {
          ResultLength[0] = 0;
          KeyInformation = 0;
          memset_0(v15, 0, 0x210u);
          v8 = NtQueryKey(a2, KeyNameInformation, &KeyInformation, 0x214u, ResultLength) | 0x10000000;
          *((_DWORD *)this + 4) = v8;
          if ( v8 >= 0 && KeyInformation <= 0x20A )
          {
            v10 = RegistryPropertyBag::EncryptedDwordProperty::_Decrypt(
                    v9,
                    pcbData,
                    (unsigned __int8 *)pvData,
                    KeyInformation,
                    v15,
                    (unsigned int *)this + 3);
            *((_DWORD *)this + 4) = v10;
            *((_BYTE *)this + 8) = v10 >= 0;
          }
        }
      }
      if ( pvData )
        LocalFree(pvData);
    }
    else
    {
      *((_DWORD *)this + 4) = -2147024883;
    }
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids,
      *((unsigned int *)this + 4));
  }
  return *((unsigned int *)this + 4);
}

```

## disassembly

```asm
0x18002ec14  mov     [rsp-8+arg_10], rbx
0x18002ec19  mov     [rsp-8+arg_18], rsi
0x18002ec1e  push    rbp
0x18002ec1f  push    rdi
0x18002ec20  push    r12
0x18002ec22  lea     rbp, [rsp-180h]
0x18002ec2a  sub     rsp, 280h
0x18002ec31  mov     rax, cs:__security_cookie
0x18002ec38  xor     rax, rsp
0x18002ec3b  mov     [rbp+190h+var_20], rax
0x18002ec42  mov     rsi, rdx
0x18002ec45  mov     rbx, rcx
0x18002ec48  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec4f  lea     r12, WPP_GLOBAL_Control
0x18002ec56  cmp     rcx, r12
0x18002ec59  jz      short loc_18002EC76
0x18002ec5b  test    byte ptr [rcx+1Ch], 10h
0x18002ec5f  jz      short loc_18002EC76
0x18002ec61  mov     rcx, [rcx+10h]
0x18002ec65  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x18002ec6c  mov     edx, 2Bh ; '+'
0x18002ec71  call    WPP_SF_
0x18002ec76  mov     r8, [rbx+18h]; lpValue
0x18002ec7a  lea     rax, [rsp+290h+var_250]
0x18002ec7f  mov     [rsp+290h+pcbData], rax; pcbData
0x18002ec84  mov     r9d, 8; dwFlags
0x18002ec8a  mov     [rsp+290h+pvData], 0; pvData
0x18002ec93  xor     edx, edx; lpSubKey
0x18002ec95  mov     rcx, rsi; hkey
0x18002ec98  mov     [rsp+290h+pdwType], 0; pdwType
0x18002eca1  mov     [rsp+290h+var_250], 0
0x18002eca9  mov     byte ptr [rbx+8], 0
0x18002ecad  call    cs:__imp_RegGetValueW
0x18002ecb3  test    eax, eax
0x18002ecb5  jle     short loc_18002ECBF
0x18002ecb7  movzx   eax, ax
0x18002ecba  or      eax, 80070000h
0x18002ecbf  mov     [rbx+10h], eax
0x18002ecc2  test    eax, eax
0x18002ecc4  js      loc_18002EDE6
0x18002ecca  mov     ecx, [rsp+290h+var_250]
0x18002ecce  lea     eax, [rcx-1]
0x18002ecd1  cmp     eax, 0FFFh
0x18002ecd6  jbe     short loc_18002ECE4
0x18002ecd8  mov     dword ptr [rbx+10h], 8007000Dh
0x18002ecdf  jmp     loc_18002EDE6
0x18002ece4  mov     rdx, rcx; uBytes
0x18002ece7  mov     ecx, 40h ; '@'; uFlags
0x18002ecec  call    cs:__imp_LocalAlloc
0x18002ecf2  mov     rdi, rax
0x18002ecf5  test    rax, rax
0x18002ecf8  jnz     short loc_18002ED01
0x18002ecfa  mov     dword ptr [rbx+10h], 8007000Eh
0x18002ed01  mov     eax, [rbx+10h]
0x18002ed04  test    eax, eax
0x18002ed06  js      loc_18002EDD8
0x18002ed0c  mov     r8, [rbx+18h]; lpValue
0x18002ed10  lea     rax, [rsp+290h+var_250]
0x18002ed15  mov     [rsp+290h+pcbData], rax; pcbData
0x18002ed1a  mov     r9d, 20000008h; dwFlags
0x18002ed20  mov     [rsp+290h+pvData], rdi; pvData
0x18002ed25  xor     edx, edx; lpSubKey
0x18002ed27  mov     rcx, rsi; hkey
0x18002ed2a  mov     [rsp+290h+pdwType], 0; pdwType
0x18002ed33  call    cs:__imp_RegGetValueW
0x18002ed39  test    eax, eax
0x18002ed3b  jle     short loc_18002ED45
0x18002ed3d  movzx   eax, ax
0x18002ed40  or      eax, 80070000h
0x18002ed45  mov     [rbx+10h], eax
0x18002ed48  test    eax, eax
0x18002ed4a  js      loc_18002EDD8
0x18002ed50  xor     edx, edx; Val
0x18002ed52  mov     [rsp+290h+ResultLength], 0
0x18002ed5a  mov     r8d, 210h; Size
0x18002ed60  mov     [rsp+290h+KeyInformation], 0
0x18002ed68  lea     rcx, [rsp+290h+var_23C]; void *
0x18002ed6d  call    memset_0
0x18002ed72  lea     rax, [rsp+290h+ResultLength]
0x18002ed77  mov     r9d, 214h; Length
0x18002ed7d  lea     r8, [rsp+290h+KeyInformation]; KeyInformation
0x18002ed82  mov     [rsp+290h+pdwType], rax; ResultLength
0x18002ed87  mov     edx, 3; KeyInformationClass
0x18002ed8c  mov     rcx, rsi; KeyHandle
0x18002ed8f  call    cs:__imp_NtQueryKey
0x18002ed95  or      eax, 10000000h
0x18002ed9a  mov     [rbx+10h], eax
0x18002ed9d  jl      short loc_18002EDD8
0x18002ed9f  cmp     [rsp+290h+KeyInformation], 20Ah
0x18002eda7  ja      short loc_18002EDD8
0x18002eda9  mov     r9d, [rsp+290h+KeyInformation]; unsigned __int64
0x18002edae  lea     rax, [rbx+0Ch]
0x18002edb2  mov     edx, [rsp+290h+var_250]; unsigned __int64
0x18002edb6  mov     r8, rdi; unsigned __int8 *
0x18002edb9  mov     [rsp+290h+pvData], rax; unsigned int *
0x18002edbe  lea     rax, [rsp+290h+var_23C]
0x18002edc3  mov     [rsp+290h+pdwType], rax; unsigned __int8 *
0x18002edc8  call    ?_Decrypt@EncryptedDwordProperty@RegistryPropertyBag@@AEAAJ_KPEAE01PEAK@Z; RegistryPropertyBag::EncryptedDwordProperty::_Decrypt(unsigned __int64,uchar *,unsigned __int64,uchar *,ulong *)
0x18002edcd  mov     [rbx+10h], eax
0x18002edd0  shr     eax, 1Fh
0x18002edd3  xor     al, 1
0x18002edd5  mov     [rbx+8], al
0x18002edd8  test    rdi, rdi
0x18002eddb  jz      short loc_18002EDE6
0x18002eddd  mov     rcx, rdi; hMem
0x18002ede0  call    cs:__imp_LocalFree
0x18002ede6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eded  cmp     rcx, r12
0x18002edf0  jz      short loc_18002EE11
0x18002edf2  test    byte ptr [rcx+1Ch], 10h
0x18002edf6  jz      short loc_18002EE11
0x18002edf8  mov     r9d, [rbx+10h]
0x18002edfc  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x18002ee03  mov     rcx, [rcx+10h]
0x18002ee07  mov     edx, 2Ch ; ','
0x18002ee0c  call    WPP_SF_d
0x18002ee11  mov     eax, [rbx+10h]
0x18002ee14  mov     rcx, [rbp+190h+var_20]
0x18002ee1b  xor     rcx, rsp; StackCookie
0x18002ee1e  call    __security_check_cookie
0x18002ee23  lea     r11, [rsp+290h+var_10]
0x18002ee2b  mov     rbx, [r11+30h]
0x18002ee2f  mov     rsi, [r11+38h]
0x18002ee33  mov     rsp, r11
0x18002ee36  pop     r12
0x18002ee38  pop     rdi
0x18002ee39  pop     rbp
0x18002ee3a  retn
```
