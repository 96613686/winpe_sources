# CRegZone::UpdateZoneMapFlags(void)

- ea: `0x18003a958`
- end: `0x18003abd6`
- name: `?UpdateZoneMapFlags@CRegZone@@QEAAHXZ`
- size: `638`
- prototype: `__int64 __fastcall(CRegZone *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180113104`

## callees

- `0x18003a958`
- `0x18003bef0`
- `0x18003bf28`

## import_xrefs

- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x18003ab62`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x18003ab86`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x18003ab62`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x18003ab86`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003aa42`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003aa85`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003aacd`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003ab04`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003aa42`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003aa85`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003aacd`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003ab04`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003a9f3`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003abbd`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003a9f3`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003abbd`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003ab2f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003ab2f`

## pseudocode

```c
__int64 __fastcall CRegZone::UpdateZoneMapFlags(CRegZone *this)
{
  BOOL fIgnoreHKCU; // eax
  bool v3; // zf
  HUSKEY v4; // rcx
  unsigned int v5; // ebx
  int v6; // ebx
  const unsigned int *v8; // [rsp+30h] [rbp-28h] BYREF
  HUSKEY hUSKey; // [rsp+38h] [rbp-20h]
  BOOL v10; // [rsp+40h] [rbp-18h]
  __int64 v11; // [rsp+44h] [rbp-14h]
  HUSKEY phNewUSKey; // [rsp+80h] [rbp+28h] BYREF

  if ( *(_DWORD *)this != 1 )
    return 1;
  CSharedMem::IncrementCounter((CSharedMem *)&g_SharedMem, 4u);
  v8 = &CRegKey::`vftable';
  v10 = g_bUseHKLMOnly;
  hUSKey = 0;
  v11 = 0;
  if ( (NtCurrentPeb()->BitField & 0x20) != 0 )
    return 1;
  phNewUSKey = 0;
  CRegKey::Close((CRegKey *)&v8);
  if ( !(_DWORD)v11 )
  {
LABEL_4:
    fIgnoreHKCU = v10;
    goto LABEL_5;
  }
  fIgnoreHKCU = v10;
  if ( !v10 )
  {
    if ( !SHRegOpenUSKeyW(
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap\\",
            0x2001Fu,
            0,
            &phNewUSKey,
            1) )
    {
LABEL_6:
      v3 = (*((_BYTE *)this + 4) & 8) == 0;
      v4 = phNewUSKey;
      hUSKey = phNewUSKey;
      if ( v3 )
      {
        SHRegDeleteUSValueW(phNewUSKey, L"ProxyBypass", (SHREGDEL_FLAGS)(v10 ? SHREGDEL_HKLM : SHREGDEL_HKCU));
      }
      else
      {
        LODWORD(phNewUSKey) = *(_DWORD *)this;
        SHRegWriteUSValueW(v4, L"ProxyBypass", 4u, &phNewUSKey, 4u, v10 ? 8 : 2);
      }
      if ( (*((_BYTE *)this + 4) & 0x10) != 0 )
      {
        LODWORD(phNewUSKey) = *(_DWORD *)this;
        SHRegWriteUSValueW(hUSKey, L"IntranetName", 4u, &phNewUSKey, 4u, v10 ? 8 : 2);
      }
      else
      {
        SHRegDeleteUSValueW(hUSKey, L"IntranetName", (SHREGDEL_FLAGS)(v10 ? SHREGDEL_HKLM : SHREGDEL_HKCU));
      }
      v5 = *((_DWORD *)this + 1);
      LODWORD(phNewUSKey) = (v5 >> 7) & 1;
      v6 = (v5 >> 8) & 1;
      SHRegWriteUSValueW(hUSKey, L"UNCAsIntranet", 4u, &phNewUSKey, 4u, v10 ? 8 : 2);
      LODWORD(phNewUSKey) = v6;
      SHRegWriteUSValueW(hUSKey, L"AutoDetect", 4u, &phNewUSKey, 4u, v10 ? 8 : 2);
      if ( v6 != g_dwAutoDetectFlag )
        g_dwAutoDetectFlag = -1;
      goto LABEL_12;
    }
    goto LABEL_4;
  }
LABEL_5:
  if ( !SHRegOpenUSKeyW(
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap\\",
          0x2001Fu,
          0,
          &phNewUSKey,
          fIgnoreHKCU) )
    goto LABEL_6;
LABEL_12:
  v8 = &CRegKey::`vftable';
  if ( hUSKey )
    SHRegCloseUSKey(hUSKey);
  return 1;
}

```

## disassembly

```asm
0x18003a958  push    rbp
0x18003a95a  push    rbx
0x18003a95b  push    r12
0x18003a95d  push    r14
0x18003a95f  mov     rbp, rsp
0x18003a962  sub     rsp, 58h
0x18003a966  cmp     dword ptr [rcx], 1
0x18003a969  mov     rbx, rcx
0x18003a96c  jnz     loc_18003AB3B
0x18003a972  mov     r14d, 4
0x18003a978  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x18003a97f  mov     edx, r14d; unsigned int
0x18003a982  call    ?IncrementCounter@CSharedMem@@QEAAHK@Z; CSharedMem::IncrementCounter(ulong)
0x18003a987  mov     eax, cs:?g_bUseHKLMOnly@@3HA; int g_bUseHKLMOnly
0x18003a98d  lea     r12, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x18003a994  mov     [rbp+var_28], r12
0x18003a998  mov     [rbp+var_18], eax
0x18003a99b  mov     [rbp+hUSKey], 0
0x18003a9a3  mov     [rbp+var_14], 0
0x18003a9ab  mov     rax, gs:60h
0x18003a9b4  test    byte ptr [rax+3], 20h
0x18003a9b8  jnz     loc_18003AB3B
0x18003a9be  lea     rcx, [rbp+var_28]; this
0x18003a9c2  mov     [rbp+phNewUSKey], 0
0x18003a9ca  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003a9cf  cmp     dword ptr [rbp+var_14], 0
0x18003a9d3  jnz     loc_18003AB97
0x18003a9d9  mov     eax, [rbp+var_18]
0x18003a9dc  lea     r9, [rbp+phNewUSKey]; phNewUSKey
0x18003a9e0  mov     [rsp+58h+fIgnoreHKCU], eax; fIgnoreHKCU
0x18003a9e4  xor     r8d, r8d; hRelativeUSKey
0x18003a9e7  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003a9ee  mov     edx, 2001Fh; samDesired
0x18003a9f3  call    cs:__imp_SHRegOpenUSKeyW
0x18003a9fa  nop     dword ptr [rax+rax+00h]
0x18003a9ff  test    eax, eax
0x18003aa01  jnz     loc_18003AB22
0x18003aa07  test    byte ptr [rbx+4], 8
0x18003aa0b  mov     rcx, [rbp+phNewUSKey]; hUSKey
0x18003aa0f  mov     [rbp+hUSKey], rcx
0x18003aa13  jz      loc_18003AB4C
0x18003aa19  mov     eax, [rbx]
0x18003aa1b  lea     r9, [rbp+phNewUSKey]; pvData
0x18003aa1f  mov     dword ptr [rbp+phNewUSKey], eax
0x18003aa22  mov     r8d, r14d; dwType
0x18003aa25  mov     eax, [rbp+var_18]
0x18003aa28  neg     eax
0x18003aa2a  sbb     edx, edx
0x18003aa2c  and     edx, 6
0x18003aa2f  add     edx, 2
0x18003aa32  mov     [rsp+58h+dwFlags], edx; dwFlags
0x18003aa36  lea     rdx, pwzValue; "ProxyBypass"
0x18003aa3d  mov     [rsp+58h+fIgnoreHKCU], r14d; cbData
0x18003aa42  call    cs:__imp_SHRegWriteUSValueW
0x18003aa49  nop     dword ptr [rax+rax+00h]
0x18003aa4e  test    byte ptr [rbx+4], 10h
0x18003aa52  lea     rdx, aIntranetname; "IntranetName"
0x18003aa59  jz      loc_18003AB73
0x18003aa5f  mov     eax, [rbx]
0x18003aa61  lea     r9, [rbp+phNewUSKey]; pvData
0x18003aa65  mov     dword ptr [rbp+phNewUSKey], eax
0x18003aa68  mov     r8d, r14d; dwType
0x18003aa6b  mov     eax, [rbp+var_18]
0x18003aa6e  neg     eax
0x18003aa70  sbb     ecx, ecx
0x18003aa72  and     ecx, 6
0x18003aa75  add     ecx, 2
0x18003aa78  mov     [rsp+58h+dwFlags], ecx; dwFlags
0x18003aa7c  mov     rcx, [rbp+hUSKey]; hUSKey
0x18003aa80  mov     [rsp+58h+fIgnoreHKCU], r14d; cbData
0x18003aa85  call    cs:__imp_SHRegWriteUSValueW
0x18003aa8c  nop     dword ptr [rax+rax+00h]
0x18003aa91  mov     eax, [rbx+4]
0x18003aa94  lea     r9, [rbp+phNewUSKey]; pvData
0x18003aa98  mov     ebx, eax
0x18003aa9a  lea     rdx, aUncasintranet; "UNCAsIntranet"
0x18003aaa1  shr     eax, 7
0x18003aaa4  mov     r8d, r14d; dwType
0x18003aaa7  and     eax, 1
0x18003aaaa  shr     ebx, 8
0x18003aaad  mov     dword ptr [rbp+phNewUSKey], eax
0x18003aab0  and     ebx, 1
0x18003aab3  mov     eax, [rbp+var_18]
0x18003aab6  neg     eax
0x18003aab8  sbb     ecx, ecx
0x18003aaba  and     ecx, 6
0x18003aabd  add     ecx, 2
0x18003aac0  mov     [rsp+58h+dwFlags], ecx; dwFlags
0x18003aac4  mov     rcx, [rbp+hUSKey]; hUSKey
0x18003aac8  mov     [rsp+58h+fIgnoreHKCU], r14d; cbData
0x18003aacd  call    cs:__imp_SHRegWriteUSValueW
0x18003aad4  nop     dword ptr [rax+rax+00h]
0x18003aad9  mov     eax, [rbp+var_18]
0x18003aadc  lea     r9, [rbp+phNewUSKey]; pvData
0x18003aae0  neg     eax
0x18003aae2  mov     dword ptr [rbp+phNewUSKey], ebx
0x18003aae5  mov     r8d, r14d; dwType
0x18003aae8  lea     rdx, aAutodetect_0; "AutoDetect"
0x18003aaef  sbb     ecx, ecx
0x18003aaf1  and     ecx, 6
0x18003aaf4  add     ecx, 2
0x18003aaf7  mov     [rsp+58h+dwFlags], ecx; dwFlags
0x18003aafb  mov     rcx, [rbp+hUSKey]; hUSKey
0x18003aaff  mov     [rsp+58h+fIgnoreHKCU], r14d; cbData
0x18003ab04  call    cs:__imp_SHRegWriteUSValueW
0x18003ab0b  nop     dword ptr [rax+rax+00h]
0x18003ab10  cmp     ebx, cs:?g_dwAutoDetectFlag@@3KA; ulong g_dwAutoDetectFlag
0x18003ab16  jz      short loc_18003AB22
0x18003ab18  mov     cs:?g_dwAutoDetectFlag@@3KA, 0FFFFFFFFh; ulong g_dwAutoDetectFlag
0x18003ab22  mov     rcx, [rbp+hUSKey]; hUSKey
0x18003ab26  mov     [rbp+var_28], r12
0x18003ab2a  test    rcx, rcx
0x18003ab2d  jz      short loc_18003AB3B
0x18003ab2f  call    cs:__imp_SHRegCloseUSKey
0x18003ab36  nop     dword ptr [rax+rax+00h]
0x18003ab3b  mov     eax, 1
0x18003ab40  add     rsp, 58h
0x18003ab44  pop     r14
0x18003ab46  pop     r12
0x18003ab48  pop     rbx
0x18003ab49  pop     rbp
0x18003ab4a  retn
0x18003ab4c  mov     eax, [rbp+var_18]
0x18003ab4f  lea     rdx, pwzValue; "ProxyBypass"
0x18003ab56  neg     eax
0x18003ab58  sbb     r8d, r8d
0x18003ab5b  and     r8d, 0Fh
0x18003ab5f  inc     r8d; delRegFlags
0x18003ab62  call    cs:__imp_SHRegDeleteUSValueW
0x18003ab69  nop     dword ptr [rax+rax+00h]
0x18003ab6e  jmp     loc_18003AA4E
0x18003ab73  mov     eax, [rbp+var_18]
0x18003ab76  mov     rcx, [rbp+hUSKey]; hUSKey
0x18003ab7a  neg     eax
0x18003ab7c  sbb     r8d, r8d
0x18003ab7f  and     r8d, 0Fh
0x18003ab83  inc     r8d; delRegFlags
0x18003ab86  call    cs:__imp_SHRegDeleteUSValueW
0x18003ab8d  nop     dword ptr [rax+rax+00h]
0x18003ab92  jmp     loc_18003AA91
0x18003ab97  mov     eax, [rbp+var_18]
0x18003ab9a  test    eax, eax
0x18003ab9c  jnz     loc_18003A9DC
0x18003aba2  lea     r9, [rbp+phNewUSKey]; phNewUSKey
0x18003aba6  mov     [rsp+58h+fIgnoreHKCU], 1; fIgnoreHKCU
0x18003abae  xor     r8d, r8d; hRelativeUSKey
0x18003abb1  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003abb8  mov     edx, 2001Fh; samDesired
0x18003abbd  call    cs:__imp_SHRegOpenUSKeyW
0x18003abc4  nop     dword ptr [rax+rax+00h]
0x18003abc9  test    eax, eax
0x18003abcb  jnz     loc_18003A9D9
0x18003abd1  jmp     loc_18003AA07
```
