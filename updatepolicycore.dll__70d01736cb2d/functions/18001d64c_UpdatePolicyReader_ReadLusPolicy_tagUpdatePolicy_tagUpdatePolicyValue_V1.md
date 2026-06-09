# UpdatePolicyReader::ReadLusPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 *)

- ea: `0x18001d64c`
- end: `0x18001d87b`
- name: `?ReadLusPolicy@UpdatePolicyReader@@CAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001a320`

## callees

- `0x18001d64c`
- `0x18001d884`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001d69a`
- `OLEAUT32!__imp_VariantInit` at `0x18001d69a`
- `OLEAUT32!__imp_VariantClear` at `0x18001d84d`
- `OLEAUT32!__imp_VariantClear` at `0x18001d84d`

## string_xrefs

- `0x18001d7e2`: `AllowResumeUpdateAfterDevicePoweredOn`
- `0x18001d7b0`: `AllowAutoUpdate`
- `0x18001d81e`: `AllowAutoUpdate`
- `0x18001d808`: `ScheduledInstallDay`
- `0x18001d7f6`: `ScheduledInstallTime`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadLusPolicy(int a1, __int64 a2)
{
  int LusPolicy; // esi
  int v5; // ebx
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  unsigned int v12; // r9d
  unsigned int v13; // r8d
  int v14; // edx
  const wchar_t *v15; // rcx
  _BYTE v17[40]; // [rsp+30h] [rbp-30h] BYREF

  LusPolicy = 0;
  memset(v17, 0, sizeof(v17));
  VariantInit((VARIANTARG *)&v17[16]);
  *(_QWORD *)&v17[4] = 0;
  *(_DWORD *)v17 = 0;
  if ( !a2 )
  {
    LusPolicy = -2147467261;
    goto LABEL_28;
  }
  *(_DWORD *)a2 = a1;
  v5 = a1 - 4;
  if ( !v5 )
  {
    v14 = 22;
    v15 = L"DetectionFrequency";
    v13 = 1;
    goto LABEL_26;
  }
  v6 = v5 - 3;
  if ( !v6 )
  {
    v14 = 6;
    v15 = L"AllowAutoUpdate";
    v13 = 0;
LABEL_26:
    v12 = v14;
    goto LABEL_27;
  }
  v7 = v6 - 3;
  if ( !v7 )
  {
    v13 = 0;
    v15 = L"ScheduledInstallDay";
    v14 = 0;
    v12 = 7;
    goto LABEL_27;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v12 = 24;
    v15 = L"ScheduledInstallTime";
    v13 = 0;
    v14 = 3;
    goto LABEL_27;
  }
  v9 = v8 - 2;
  if ( v9 )
  {
    v10 = v9 - 9;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( v11 != 1 )
          goto LABEL_28;
        v12 = 23;
        v13 = 0;
        v14 = 17;
        v15 = L"ActiveHoursEnd";
      }
      else
      {
        v12 = 23;
        v15 = L"ActiveHoursStart";
        v13 = 0;
        v14 = 8;
      }
LABEL_27:
      LusPolicy = UpdatePolicyReader::ReadLusPolicy(v15, v14, v13, v12, (struct tagUpdatePolicyValue_V1 *)a2);
      goto LABEL_28;
    }
    LusPolicy = UpdatePolicyReader::ReadLusPolicy(
                  L"ActiveHoursStart",
                  8,
                  0,
                  0x17u,
                  (struct tagUpdatePolicyValue_V1 *)v17);
    if ( LusPolicy >= 0 && *(_DWORD *)&v17[4] == 1 )
    {
      LusPolicy = UpdatePolicyReader::ReadLusPolicy(
                    L"ActiveHoursEnd",
                    17,
                    0,
                    0x17u,
                    (struct tagUpdatePolicyValue_V1 *)a2);
      if ( LusPolicy >= 0 && *(_DWORD *)(a2 + 4) == 1 )
      {
        *(_WORD *)(a2 + 16) = 3;
        *(_DWORD *)(a2 + 24) = 1;
      }
    }
  }
  else
  {
    LusPolicy = UpdatePolicyReader::ReadLusPolicy(L"AllowAutoUpdate", 6, 0, 4u, (struct tagUpdatePolicyValue_V1 *)v17);
    if ( LusPolicy >= 0 && *(_DWORD *)&v17[4] == 1 && (unsigned int)(*(_DWORD *)&v17[24] - 3) <= 1 )
    {
      v12 = 1;
      v15 = L"AllowResumeUpdateAfterDevicePoweredOn";
      v13 = 0;
      v14 = 1;
      goto LABEL_27;
    }
  }
LABEL_28:
  VariantClear((VARIANTARG *)&v17[16]);
  return (unsigned int)LusPolicy;
}

```

## disassembly

```asm
0x18001d64c  mov     [rsp-18h+arg_0], rbx
0x18001d651  mov     [rsp-18h+arg_10], rsi
0x18001d656  mov     [rsp-18h+arg_18], rdi
0x18001d65b  push    rbp
0x18001d65c  push    r14
0x18001d65e  push    r15
0x18001d660  mov     rbp, rsp
0x18001d663  sub     rsp, 60h
0x18001d667  mov     rax, cs:__security_cookie
0x18001d66e  xor     rax, rsp
0x18001d671  mov     [rbp+var_8], rax
0x18001d675  mov     ebx, ecx
0x18001d677  lea     rdi, [rbp+var_30]
0x18001d67b  xorps   xmm0, xmm0
0x18001d67e  xor     eax, eax
0x18001d680  movups  [rbp+var_30], xmm0
0x18001d684  mov     qword ptr [rbp+pvarg+10h], rax
0x18001d688  xor     esi, esi
0x18001d68a  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001d68e  mov     r14, rdx
0x18001d691  lea     ecx, [rsi+28h]
0x18001d694  rep stosb
0x18001d696  lea     rcx, [rbp+pvarg]; pvarg
0x18001d69a  call    cs:__imp_VariantInit
0x18001d6a0  mov     qword ptr [rbp+var_30+4], rsi
0x18001d6a4  mov     dword ptr [rbp+var_30], esi
0x18001d6a7  test    r14, r14
0x18001d6aa  jnz     short loc_18001D6B6
0x18001d6ac  mov     esi, 80004003h
0x18001d6b1  jmp     loc_18001D849
0x18001d6b6  mov     r9d, 4; unsigned int
0x18001d6bc  mov     [r14], ebx
0x18001d6bf  sub     ebx, r9d
0x18001d6c2  jz      loc_18001D82A
0x18001d6c8  lea     r15d, [r9-1]
0x18001d6cc  sub     ebx, r15d
0x18001d6cf  jz      loc_18001D819
0x18001d6d5  sub     ebx, r15d
0x18001d6d8  jz      loc_18001D805
0x18001d6de  sub     ebx, 1
0x18001d6e1  jz      loc_18001D7F0
0x18001d6e7  sub     ebx, 2
0x18001d6ea  jz      loc_18001D7A9
0x18001d6f0  sub     ebx, 9
0x18001d6f3  jz      short loc_18001D732
0x18001d6f5  sub     ebx, 1
0x18001d6f8  jz      short loc_18001D719
0x18001d6fa  cmp     ebx, 1
0x18001d6fd  jnz     loc_18001D849
0x18001d703  lea     r9d, [r15+14h]
0x18001d707  xor     r8d, r8d
0x18001d70a  lea     edx, [rbx+10h]
0x18001d70d  lea     rcx, aActivehoursend; "ActiveHoursEnd"
0x18001d714  jmp     loc_18001D83D
0x18001d719  mov     r9d, 17h
0x18001d71f  lea     rcx, aActivehourssta; "ActiveHoursStart"
0x18001d726  xor     r8d, r8d
0x18001d729  lea     edx, [r9-0Fh]
0x18001d72d  jmp     loc_18001D83D
0x18001d732  mov     r9d, 17h; unsigned int
0x18001d738  lea     rax, [rbp+var_30]
0x18001d73c  xor     r8d, r8d; unsigned int
0x18001d73f  mov     [rsp+60h+var_40], rax; struct tagUpdatePolicyValue_V1 *
0x18001d744  lea     rcx, aActivehourssta; "ActiveHoursStart"
0x18001d74b  lea     edx, [r9-0Fh]; unsigned int
0x18001d74f  call    ?ReadLusPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadLusPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001d754  mov     esi, eax
0x18001d756  test    eax, eax
0x18001d758  js      loc_18001D849
0x18001d75e  mov     edi, 1
0x18001d763  cmp     dword ptr [rbp+var_30+4], edi
0x18001d766  jnz     loc_18001D849
0x18001d76c  lea     r9d, [rdi+16h]; unsigned int
0x18001d770  mov     [rsp+60h+var_40], r14; struct tagUpdatePolicyValue_V1 *
0x18001d775  xor     r8d, r8d; unsigned int
0x18001d778  lea     edx, [rdi+10h]; unsigned int
0x18001d77b  lea     rcx, aActivehoursend; "ActiveHoursEnd"
0x18001d782  call    ?ReadLusPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadLusPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001d787  mov     esi, eax
0x18001d789  test    eax, eax
0x18001d78b  js      loc_18001D849
0x18001d791  cmp     [r14+4], edi
0x18001d795  jnz     loc_18001D849
0x18001d79b  mov     [r14+10h], r15w
0x18001d7a0  mov     [r14+18h], edi
0x18001d7a4  jmp     loc_18001D849
0x18001d7a9  xor     r8d, r8d; unsigned int
0x18001d7ac  lea     rax, [rbp+var_30]
0x18001d7b0  lea     rcx, aAllowautoupdat; "AllowAutoUpdate"
0x18001d7b7  mov     [rsp+60h+var_40], rax; struct tagUpdatePolicyValue_V1 *
0x18001d7bc  lea     edx, [r8+6]; unsigned int
0x18001d7c0  call    ?ReadLusPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadLusPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001d7c5  mov     esi, eax
0x18001d7c7  test    eax, eax
0x18001d7c9  js      short loc_18001D849
0x18001d7cb  mov     edi, 1
0x18001d7d0  cmp     dword ptr [rbp+var_30+4], edi
0x18001d7d3  jnz     short loc_18001D849
0x18001d7d5  mov     eax, dword ptr [rbp+pvarg+8]
0x18001d7d8  add     eax, 0FFFFFFFDh
0x18001d7db  cmp     eax, edi
0x18001d7dd  ja      short loc_18001D849
0x18001d7df  mov     r9d, edi
0x18001d7e2  lea     rcx, aAllowresumeupd; "AllowResumeUpdateAfterDevicePoweredOn"
0x18001d7e9  xor     r8d, r8d
0x18001d7ec  mov     edx, edi
0x18001d7ee  jmp     short loc_18001D83D
0x18001d7f0  mov     r9d, 18h
0x18001d7f6  lea     rcx, aScheduledinsta_2; "ScheduledInstallTime"
0x18001d7fd  xor     r8d, r8d
0x18001d800  mov     edx, r15d
0x18001d803  jmp     short loc_18001D83D
0x18001d805  xor     r8d, r8d
0x18001d808  lea     rcx, aScheduledinsta_5; "ScheduledInstallDay"
0x18001d80f  xor     edx, edx
0x18001d811  mov     r9d, 7
0x18001d817  jmp     short loc_18001D83D
0x18001d819  mov     edx, 6
0x18001d81e  lea     rcx, aAllowautoupdat; "AllowAutoUpdate"
0x18001d825  xor     r8d, r8d
0x18001d828  jmp     short loc_18001D83A
0x18001d82a  mov     edx, 16h; unsigned int
0x18001d82f  lea     rcx, aDetectionfrequ_0; "DetectionFrequency"
0x18001d836  lea     r8d, [rdx-15h]; unsigned int
0x18001d83a  mov     r9d, edx; unsigned int
0x18001d83d  mov     [rsp+60h+var_40], r14; struct tagUpdatePolicyValue_V1 *
0x18001d842  call    ?ReadLusPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadLusPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001d847  mov     esi, eax
0x18001d849  lea     rcx, [rbp+pvarg]; pvarg
0x18001d84d  call    cs:__imp_VariantClear
0x18001d853  mov     eax, esi
0x18001d855  mov     rcx, [rbp+var_8]
0x18001d859  xor     rcx, rsp; StackCookie
0x18001d85c  call    __security_check_cookie
0x18001d861  lea     r11, [rsp+60h+var_s0]
0x18001d866  mov     rbx, [r11+20h]
0x18001d86a  mov     rsi, [r11+30h]
0x18001d86e  mov     rdi, [r11+38h]
0x18001d872  mov     rsp, r11
0x18001d875  pop     r15
0x18001d877  pop     r14
0x18001d879  pop     rbp
0x18001d87a  retn
```
