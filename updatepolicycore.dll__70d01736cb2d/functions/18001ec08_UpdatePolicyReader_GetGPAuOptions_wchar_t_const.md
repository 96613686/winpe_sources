# UpdatePolicyReader::GetGPAuOptions(wchar_t const *)

- ea: `0x18001ec08`
- end: `0x18001ecda`
- name: `?GetGPAuOptions@UpdatePolicyReader@@CAKPEB_W@Z`
- size: `210`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18001bf44`

## callees

- `0x18001e480`
- `0x18001e680`
- `0x18001ec08`

## string_xrefs

- `0x18001ec29`: `NoAutoUpdate`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::GetGPAuOptions(const wchar_t *a1)
{
  unsigned int v1; // ebx
  unsigned int v3; // edi
  __int128 v5; // [rsp+30h] [rbp-30h] BYREF
  __int128 v6; // [rsp+40h] [rbp-20h]
  __int64 v7; // [rsp+50h] [rbp-10h]
  int v8; // [rsp+88h] [rbp+28h] BYREF
  int v9; // [rsp+90h] [rbp+30h] BYREF

  v1 = 0;
  v8 = 0;
  v9 = 0;
  v5 = 0;
  v7 = 0;
  v6 = 0;
  if ( (int)UpdatePolicyReader::ReadGPPolicyStateHelper(a1, L"NoAutoUpdate", (enum tagUpdatePolicyStatus *)&v8, &v9) >= 0
    && v8 == 1
    && v9 )
  {
    return 1;
  }
  else if ( (int)UpdatePolicyReader::ReadGPDWordPolicyValueWithoutPolicyState(
                   a1,
                   L"AUOptions",
                   4u,
                   0,
                   7u,
                   (struct tagUpdatePolicyValue_V1 *)&v5) >= 0 )
  {
    v3 = DWORD2(v6);
    if ( DWORD2(v6) == 4
      && (int)UpdatePolicyReader::ReadGPPolicyStateHelper(
                a1,
                L"AutomaticMaintenanceEnabled",
                (enum tagUpdatePolicyStatus *)&v8,
                &v9) >= 0
      && v8 == 1
      && v9 )
    {
      v3 = 5;
    }
    if ( ((DWORD1(v5) - 1) & 0xFFFFFFFD) == 0 )
      return v3;
  }
  return v1;
}

```

## disassembly

```asm
0x18001ec08  mov     [rsp-18h+arg_0], rbx
0x18001ec0d  push    rbp
0x18001ec0e  push    rsi
0x18001ec0f  push    rdi
0x18001ec10  mov     rbp, rsp
0x18001ec13  sub     rsp, 60h
0x18001ec17  xorps   xmm0, xmm0
0x18001ec1a  lea     r9, [rbp+arg_10]; int *
0x18001ec1e  xor     ebx, ebx
0x18001ec20  lea     r8, [rbp+arg_8]; enum tagUpdatePolicyStatus *
0x18001ec24  xor     eax, eax
0x18001ec26  mov     [rbp+arg_8], ebx
0x18001ec29  lea     rdx, aNoautoupdate; "NoAutoUpdate"
0x18001ec30  mov     [rbp+arg_10], ebx
0x18001ec33  movups  [rbp+var_30], xmm0
0x18001ec37  mov     [rbp+var_10], rax
0x18001ec3b  mov     rsi, rcx
0x18001ec3e  movups  [rbp+var_20], xmm0
0x18001ec42  call    ?ReadGPPolicyStateHelper@UpdatePolicyReader@@CAJPEB_W0PEAW4tagUpdatePolicyStatus@@PEAH@Z; UpdatePolicyReader::ReadGPPolicyStateHelper(wchar_t const *,wchar_t const *,tagUpdatePolicyStatus *,int *)
0x18001ec47  test    eax, eax
0x18001ec49  js      short loc_18001EC5D
0x18001ec4b  cmp     [rbp+arg_8], 1
0x18001ec4f  jnz     short loc_18001EC5D
0x18001ec51  cmp     [rbp+arg_10], ebx
0x18001ec54  jz      short loc_18001EC5D
0x18001ec56  mov     ebx, 1
0x18001ec5b  jmp     short loc_18001ECC8
0x18001ec5d  xor     r9d, r9d; unsigned int
0x18001ec60  lea     rax, [rbp+var_30]
0x18001ec64  mov     [rsp+60h+var_38], rax; struct tagUpdatePolicyValue_V1 *
0x18001ec69  lea     rdx, aAuoptions; "AUOptions"
0x18001ec70  mov     rcx, rsi; wchar_t *
0x18001ec73  mov     [rsp+60h+var_40], 7; unsigned int
0x18001ec7b  lea     r8d, [r9+4]; unsigned int
0x18001ec7f  call    ?ReadGPDWordPolicyValueWithoutPolicyState@UpdatePolicyReader@@CAJPEB_W0KKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPDWordPolicyValueWithoutPolicyState(wchar_t const *,wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001ec84  test    eax, eax
0x18001ec86  js      short loc_18001ECC8
0x18001ec88  mov     edi, dword ptr [rbp+var_20+8]
0x18001ec8b  cmp     edi, 4
0x18001ec8e  jnz     short loc_18001ECBA
0x18001ec90  lea     r9, [rbp+arg_10]; int *
0x18001ec94  mov     rcx, rsi; lpSubKey
0x18001ec97  lea     r8, [rbp+arg_8]; enum tagUpdatePolicyStatus *
0x18001ec9b  lea     rdx, aAutomaticmaint; "AutomaticMaintenanceEnabled"
0x18001eca2  call    ?ReadGPPolicyStateHelper@UpdatePolicyReader@@CAJPEB_W0PEAW4tagUpdatePolicyStatus@@PEAH@Z; UpdatePolicyReader::ReadGPPolicyStateHelper(wchar_t const *,wchar_t const *,tagUpdatePolicyStatus *,int *)
0x18001eca7  test    eax, eax
0x18001eca9  js      short loc_18001ECBA
0x18001ecab  cmp     [rbp+arg_8], 1
0x18001ecaf  jnz     short loc_18001ECBA
0x18001ecb1  cmp     [rbp+arg_10], ebx
0x18001ecb4  lea     eax, [rdi+1]
0x18001ecb7  cmovnz  edi, eax
0x18001ecba  mov     ecx, dword ptr [rbp+var_30+4]
0x18001ecbd  dec     ecx
0x18001ecbf  test    ecx, 0FFFFFFFDh
0x18001ecc5  cmovz   ebx, edi
0x18001ecc8  mov     eax, ebx
0x18001ecca  mov     rbx, [rsp+60h+arg_0]
0x18001ecd2  add     rsp, 60h
0x18001ecd6  pop     rdi
0x18001ecd7  pop     rsi
0x18001ecd8  pop     rbp
0x18001ecd9  retn
```
