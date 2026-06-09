# CRegZone::UpdateZoneMapFlags(void)

- ea: `0x180032e6c`
- end: `0x1800330b3`
- name: `?UpdateZoneMapFlags@CRegZone@@QEAAHXZ`
- size: `583`
- prototype: `__int64 __fastcall(CRegZone *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180107b5c`

## callees

- `0x180032e6c`
- `0x1800342d0`
- `0x180034300`

## import_xrefs

- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x180033051`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x18003306f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x180033051`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x18003306f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180032f50`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180032f8d`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180032fcf`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180033000`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180032f50`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180032f8d`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180032fcf`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180033000`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180032f07`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800330a0`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180032f07`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800330a0`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180033025`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180033025`

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
0x180032e6c  push    rbp
0x180032e6e  push    rbx
0x180032e6f  push    r12
0x180032e71  push    r14
0x180032e73  mov     rbp, rsp
0x180032e76  sub     rsp, 58h
0x180032e7a  cmp     dword ptr [rcx], 1
0x180032e7d  mov     rbx, rcx
0x180032e80  jnz     loc_18003302B
0x180032e86  mov     r14d, 4
0x180032e8c  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x180032e93  mov     edx, r14d; unsigned int
0x180032e96  call    ?IncrementCounter@CSharedMem@@QEAAHK@Z; CSharedMem::IncrementCounter(ulong)
0x180032e9b  mov     eax, cs:?g_bUseHKLMOnly@@3HA; int g_bUseHKLMOnly
0x180032ea1  lea     r12, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180032ea8  mov     [rbp+var_28], r12
0x180032eac  mov     [rbp+var_18], eax
0x180032eaf  mov     [rbp+hUSKey], 0
0x180032eb7  mov     [rbp+var_14], 0
0x180032ebf  mov     rax, gs:60h
0x180032ec8  test    byte ptr [rax+3], 20h
0x180032ecc  jnz     loc_18003302B
0x180032ed2  lea     rcx, [rbp+var_28]; this
0x180032ed6  mov     [rbp+phNewUSKey], 0
0x180032ede  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x180032ee3  cmp     dword ptr [rbp+var_14], 0
0x180032ee7  jnz     loc_18003307A
0x180032eed  mov     eax, [rbp+var_18]
0x180032ef0  lea     r9, [rbp+phNewUSKey]; phNewUSKey
0x180032ef4  mov     [rsp+58h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180032ef8  xor     r8d, r8d; hRelativeUSKey
0x180032efb  lea     rcx, pwzPath; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180032f02  mov     edx, 2001Fh; samDesired
0x180032f07  call    cs:__imp_SHRegOpenUSKeyW
0x180032f0d  test    eax, eax
0x180032f0f  jnz     loc_180033018
0x180032f15  test    byte ptr [rbx+4], 8
0x180032f19  mov     rcx, [rbp+phNewUSKey]; hUSKey
0x180032f1d  mov     [rbp+hUSKey], rcx
0x180032f21  jz      loc_18003303B
0x180032f27  mov     eax, [rbx]
0x180032f29  lea     r9, [rbp+phNewUSKey]; pvData
0x180032f2d  mov     dword ptr [rbp+phNewUSKey], eax
0x180032f30  mov     r8d, r14d; dwType
0x180032f33  mov     eax, [rbp+var_18]
0x180032f36  neg     eax
0x180032f38  sbb     edx, edx
0x180032f3a  and     edx, 6
0x180032f3d  add     edx, 2
0x180032f40  mov     [rsp+58h+dwFlags], edx; dwFlags
0x180032f44  lea     rdx, pwzValue; "ProxyBypass"
0x180032f4b  mov     [rsp+58h+fIgnoreHKCU], r14d; cbData
0x180032f50  call    cs:__imp_SHRegWriteUSValueW
0x180032f56  test    byte ptr [rbx+4], 10h
0x180032f5a  lea     rdx, aIntranetname; "IntranetName"
0x180032f61  jz      loc_18003305C
0x180032f67  mov     eax, [rbx]
0x180032f69  lea     r9, [rbp+phNewUSKey]; pvData
0x180032f6d  mov     dword ptr [rbp+phNewUSKey], eax
0x180032f70  mov     r8d, r14d; dwType
0x180032f73  mov     eax, [rbp+var_18]
0x180032f76  neg     eax
0x180032f78  sbb     ecx, ecx
0x180032f7a  and     ecx, 6
0x180032f7d  add     ecx, 2
0x180032f80  mov     [rsp+58h+dwFlags], ecx; dwFlags
0x180032f84  mov     rcx, [rbp+hUSKey]; hUSKey
0x180032f88  mov     [rsp+58h+fIgnoreHKCU], r14d; cbData
0x180032f8d  call    cs:__imp_SHRegWriteUSValueW
0x180032f93  mov     eax, [rbx+4]
0x180032f96  lea     r9, [rbp+phNewUSKey]; pvData
0x180032f9a  mov     ebx, eax
0x180032f9c  lea     rdx, aUncasintranet; "UNCAsIntranet"
0x180032fa3  shr     eax, 7
0x180032fa6  mov     r8d, r14d; dwType
0x180032fa9  and     eax, 1
0x180032fac  shr     ebx, 8
0x180032faf  mov     dword ptr [rbp+phNewUSKey], eax
0x180032fb2  and     ebx, 1
0x180032fb5  mov     eax, [rbp+var_18]
0x180032fb8  neg     eax
0x180032fba  sbb     ecx, ecx
0x180032fbc  and     ecx, 6
0x180032fbf  add     ecx, 2
0x180032fc2  mov     [rsp+58h+dwFlags], ecx; dwFlags
0x180032fc6  mov     rcx, [rbp+hUSKey]; hUSKey
0x180032fca  mov     [rsp+58h+fIgnoreHKCU], r14d; cbData
0x180032fcf  call    cs:__imp_SHRegWriteUSValueW
0x180032fd5  mov     eax, [rbp+var_18]
0x180032fd8  lea     r9, [rbp+phNewUSKey]; pvData
0x180032fdc  neg     eax
0x180032fde  mov     dword ptr [rbp+phNewUSKey], ebx
0x180032fe1  mov     r8d, r14d; dwType
0x180032fe4  lea     rdx, aAutodetect_0; "AutoDetect"
0x180032feb  sbb     ecx, ecx
0x180032fed  and     ecx, 6
0x180032ff0  add     ecx, 2
0x180032ff3  mov     [rsp+58h+dwFlags], ecx; dwFlags
0x180032ff7  mov     rcx, [rbp+hUSKey]; hUSKey
0x180032ffb  mov     [rsp+58h+fIgnoreHKCU], r14d; cbData
0x180033000  call    cs:__imp_SHRegWriteUSValueW
0x180033006  cmp     ebx, cs:?g_dwAutoDetectFlag@@3KA; ulong g_dwAutoDetectFlag
0x18003300c  jz      short loc_180033018
0x18003300e  mov     cs:?g_dwAutoDetectFlag@@3KA, 0FFFFFFFFh; ulong g_dwAutoDetectFlag
0x180033018  mov     rcx, [rbp+hUSKey]; hUSKey
0x18003301c  mov     [rbp+var_28], r12
0x180033020  test    rcx, rcx
0x180033023  jz      short loc_18003302B
0x180033025  call    cs:__imp_SHRegCloseUSKey
0x18003302b  mov     eax, 1
0x180033030  add     rsp, 58h
0x180033034  pop     r14
0x180033036  pop     r12
0x180033038  pop     rbx
0x180033039  pop     rbp
0x18003303a  retn
0x18003303b  mov     eax, [rbp+var_18]
0x18003303e  lea     rdx, pwzValue; "ProxyBypass"
0x180033045  neg     eax
0x180033047  sbb     r8d, r8d
0x18003304a  and     r8d, 0Fh
0x18003304e  inc     r8d; delRegFlags
0x180033051  call    cs:__imp_SHRegDeleteUSValueW
0x180033057  jmp     loc_180032F56
0x18003305c  mov     eax, [rbp+var_18]
0x18003305f  mov     rcx, [rbp+hUSKey]; hUSKey
0x180033063  neg     eax
0x180033065  sbb     r8d, r8d
0x180033068  and     r8d, 0Fh
0x18003306c  inc     r8d; delRegFlags
0x18003306f  call    cs:__imp_SHRegDeleteUSValueW
0x180033075  jmp     loc_180032F93
0x18003307a  mov     eax, [rbp+var_18]
0x18003307d  test    eax, eax
0x18003307f  jnz     loc_180032EF0
0x180033085  lea     r9, [rbp+phNewUSKey]; phNewUSKey
0x180033089  mov     [rsp+58h+fIgnoreHKCU], 1; fIgnoreHKCU
0x180033091  xor     r8d, r8d; hRelativeUSKey
0x180033094  lea     rcx, pwzPath; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003309b  mov     edx, 2001Fh; samDesired
0x1800330a0  call    cs:__imp_SHRegOpenUSKeyW
0x1800330a6  test    eax, eax
0x1800330a8  jnz     loc_180032EED
0x1800330ae  jmp     loc_180032F15
```
