# CCredProvVault::CCredProvVault(void)

- ea: `0x1800bd7d8`
- end: `0x1800bd967`
- name: `??0CCredProvVault@@QEAA@XZ`
- size: `399`
- prototype: `CCredProvVault *__fastcall(CCredProvVault *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800bc1d0`
- `0x1800bc4a0`
- `0x1800bc7e0`
- `0x1800bc920`
- `0x1800bca60`
- `0x1800bcd80`

## callees

- `0x180039380`
- `0x180060dc8`
- `0x180068f60`
- `0x1800bd7d8`

## import_xrefs

- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItemType` at `0x1800bd85f`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItemType` at `0x1800bd85f`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x1800bd83f`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x1800bd83f`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCreateItemType` at `0x1800bd931`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCreateItemType` at `0x1800bd931`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x1800bd93d`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x1800bd93d`

## pseudocode

```c
CCredProvVault *__fastcall CCredProvVault::CCredProvVault(CCredProvVault *this)
{
  _QWORD v3[4]; // [rsp+20h] [rbp-89h] BYREF
  __int128 v4; // [rsp+40h] [rbp-69h]
  __int128 v5; // [rsp+50h] [rbp-59h]
  __int128 v6; // [rsp+60h] [rbp-49h]
  _OWORD v7[4]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v8[12]; // [rsp+B0h] [rbp+7h] BYREF
  int v9; // [rsp+BCh] [rbp+13h]
  int v10; // [rsp+C0h] [rbp+17h] BYREF
  __int64 v11; // [rsp+C4h] [rbp+1Bh]
  int v12; // [rsp+CCh] [rbp+23h]
  int v13; // [rsp+D0h] [rbp+27h] BYREF
  __int64 v14; // [rsp+D4h] [rbp+2Bh]
  int v15; // [rsp+DCh] [rbp+33h]
  int v16; // [rsp+E0h] [rbp+37h] BYREF
  __int64 v17; // [rsp+E4h] [rbp+3Bh]
  int v18; // [rsp+ECh] [rbp+43h]

  *(_QWORD *)this = 0;
  *(_OWORD *)((char *)this + 8) = Vault_DefaultVault_ID;
  v3[0] = 0;
  *(_QWORD *)v8 = v3;
  if ( !IsVaultApiPresent() )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !(unsigned int)VaultOpenVault((char *)this + 8, 0x10000000, this)
    && (unsigned int)VaultGetItemType(*(_QWORD *)this, &CCredProvVault::_guidSchema, 0, v3) == 1168 )
  {
    *(_QWORD *)&v6 = 1;
    *(_DWORD *)v8 = 1;
    *(_QWORD *)&v8[4] = 7;
    v9 = 0;
    v10 = 2;
    v11 = 8;
    v12 = 0;
    v13 = 3;
    v14 = 8;
    v15 = 0;
    v16 = 100;
    v17 = 8;
    v18 = 0;
    *(_QWORD *)&v4 = L"WinBio Credential Manager Credential Schema";
    *((_QWORD *)&v4 + 1) = v8;
    *(_QWORD *)&v5 = &v10;
    *((_QWORD *)&v5 + 1) = &v13;
    *((_QWORD *)&v6 + 1) = &v16;
    v7[0] = CCredProvVault::_guidSchema;
    v7[1] = v4;
    v7[2] = v5;
    v7[3] = v6;
    VaultCreateItemType(*(_QWORD *)this, v7, 0);
  }
  VaultFree(v3[0]);
  return this;
}

```

## disassembly

```asm
0x1800bd7d8  mov     [rsp-8+arg_8], rbx
0x1800bd7dd  mov     [rsp-8+arg_10], rdi
0x1800bd7e2  push    rbp
0x1800bd7e3  lea     rbp, [rsp-57h]
0x1800bd7e8  sub     rsp, 100h
0x1800bd7ef  mov     rax, cs:__security_cookie
0x1800bd7f6  xor     rax, rsp
0x1800bd7f9  mov     [rbp+57h+var_10], rax
0x1800bd7fd  mov     rbx, rcx
0x1800bd800  mov     qword ptr [rcx], 0
0x1800bd807  movups  xmm0, cs:Vault_DefaultVault_ID
0x1800bd80e  movdqu  xmmword ptr [rcx+8], xmm0
0x1800bd813  mov     [rsp+100h+var_E0], 0
0x1800bd81c  lea     rax, [rsp+100h+var_E0]
0x1800bd821  mov     qword ptr [rbp+57h+var_50], rax
0x1800bd825  call    ?IsVaultApiPresent@@YA_NXZ; IsVaultApiPresent(void)
0x1800bd82a  test    al, al
0x1800bd82c  jnz     short loc_1800BD833
0x1800bd82e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800bd833  mov     r8, rbx
0x1800bd836  mov     edx, 10000000h
0x1800bd83b  lea     rcx, [rbx+8]
0x1800bd83f  call    cs:__imp_VaultOpenVault
0x1800bd845  test    eax, eax
0x1800bd847  jnz     loc_1800BD938
0x1800bd84d  lea     r9, [rsp+100h+var_E0]
0x1800bd852  xor     r8d, r8d
0x1800bd855  lea     rdx, ?_guidSchema@CCredProvVault@@0U_GUID@@A; _GUID CCredProvVault::_guidSchema
0x1800bd85c  mov     rcx, [rbx]
0x1800bd85f  call    cs:__imp_VaultGetItemType
0x1800bd865  test    eax, eax
0x1800bd867  jz      loc_1800BD938
0x1800bd86d  cmp     eax, 490h
0x1800bd872  jnz     loc_1800BD938
0x1800bd878  mov     qword ptr [rbp+57h+var_A0], 1
0x1800bd880  mov     ecx, 1
0x1800bd885  mov     dword ptr [rbp+57h+var_50], ecx
0x1800bd888  mov     qword ptr [rbp+57h+var_50+4], 7
0x1800bd890  mov     [rbp+57h+var_44], 0
0x1800bd897  mov     [rbp+57h+var_40], 2
0x1800bd89e  mov     [rbp+57h+var_3C], 8
0x1800bd8a6  mov     [rbp+57h+var_34], 0
0x1800bd8ad  mov     [rbp+57h+var_30], 3
0x1800bd8b4  mov     [rbp+57h+var_2C], 8
0x1800bd8bc  mov     [rbp+57h+var_24], 0
0x1800bd8c3  mov     [rbp+57h+var_20], 64h ; 'd'
0x1800bd8ca  mov     [rbp+57h+var_1C], 8
0x1800bd8d2  mov     [rbp+57h+var_14], 0
0x1800bd8d9  movups  xmm0, xmmword ptr cs:?_guidSchema@CCredProvVault@@0U_GUID@@A.Data1; _GUID CCredProvVault::_guidSchema ...
0x1800bd8e0  lea     rax, aWinbioCredenti; "WinBio Credential Manager Credential Sc"...
0x1800bd8e7  mov     qword ptr [rbp+57h+var_C0], rax
0x1800bd8eb  lea     rax, [rbp+57h+var_50]
0x1800bd8ef  mov     qword ptr [rbp+57h+var_C0+8], rax
0x1800bd8f3  lea     rax, [rbp+57h+var_40]
0x1800bd8f7  mov     qword ptr [rbp+57h+var_B0], rax
0x1800bd8fb  lea     rax, [rbp+57h+var_30]
0x1800bd8ff  mov     qword ptr [rbp+57h+var_B0+8], rax
0x1800bd903  lea     rax, [rbp+57h+var_20]
0x1800bd907  mov     qword ptr [rbp+57h+var_A0+8], rax
0x1800bd90b  movaps  [rbp+57h+var_90], xmm0
0x1800bd90f  movaps  xmm0, [rbp+57h+var_C0]
0x1800bd913  movaps  [rbp+57h+var_80], xmm0
0x1800bd917  movaps  xmm1, [rbp+57h+var_B0]
0x1800bd91b  movaps  [rbp+57h+var_70], xmm1
0x1800bd91f  movaps  xmm0, [rbp+57h+var_A0]
0x1800bd923  movaps  [rbp+57h+var_60], xmm0
0x1800bd927  xor     r8d, r8d
0x1800bd92a  lea     rdx, [rbp+57h+var_90]
0x1800bd92e  mov     rcx, [rbx]
0x1800bd931  call    cs:__imp_VaultCreateItemType
0x1800bd937  nop
0x1800bd938  mov     rcx, [rsp+100h+var_E0]
0x1800bd93d  call    cs:__imp_VaultFree
0x1800bd943  mov     rax, rbx
0x1800bd946  mov     rcx, [rbp+57h+var_10]
0x1800bd94a  xor     rcx, rsp; StackCookie
0x1800bd94d  call    __security_check_cookie
0x1800bd952  lea     r11, [rsp+100h+var_s0]
0x1800bd95a  mov     rbx, [r11+18h]
0x1800bd95e  mov     rdi, [r11+20h]
0x1800bd962  mov     rsp, r11
0x1800bd965  pop     rbp
0x1800bd966  retn
```
