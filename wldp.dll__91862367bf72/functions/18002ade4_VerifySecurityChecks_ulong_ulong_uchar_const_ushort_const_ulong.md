# VerifySecurityChecks(ulong,ulong,uchar const *,ushort const *,ulong *)

- ea: `0x18002ade4`
- end: `0x18002af4e`
- name: `?VerifySecurityChecks@@YAJKKPEBEPEBGPEAK@Z`
- size: `362`
- prototype: `int(unsigned int, unsigned int, const unsigned __int8 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d220`

## callees

- `0x18001fdb4`
- `0x180021ec0`
- `0x180023ff0`
- `0x18002a480`
- `0x18002ab90`
- `0x18002ade4`
- `0x18002b670`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18002aee4`
- `ntdll!NtQuerySystemInformation` at `0x18002aee4`

## pseudocode

```c
int __fastcall VerifySecurityChecks(
        char a1,
        DWORD a2,
        const unsigned __int8 *a3,
        const unsigned __int16 *a4,
        unsigned int *a5)
{
  int result; // eax
  NTSTATUS v10; // eax
  int v11; // [rsp+20h] [rbp-40h] BYREF
  int v12; // [rsp+24h] [rbp-3Ch] BYREF
  int v13; // [rsp+28h] [rbp-38h] BYREF
  _OWORD SystemInformation[2]; // [rsp+30h] [rbp-30h] BYREF

  v11 = 0;
  v13 = 0;
  v12 = 0;
  if ( (a1 & 4) != 0 )
  {
    result = WldpCheckRetailConfiguration2(1, &v12, &v11, &v13);
    if ( result < 0 )
      return result;
    if ( !v12 )
    {
      *a5 |= 4u;
      DeleteWatermarkState(a4, 0);
    }
  }
  if ( (a1 & 8) != 0 )
  {
    result = WldpCheckRetailConfiguration2(2, &v12, &v11, &v13);
    if ( result < 0 )
      return result;
    if ( !v12 )
    {
      *a5 |= 8u;
      DeleteWatermarkState(a4, 0);
    }
  }
  if ( (a1 & 0x10) != 0 )
  {
    v11 = 1;
    result = CheckFveBinding(&v11);
    if ( result < 0 )
      return result;
    if ( !v11 )
    {
      *a5 |= 0x10u;
      DeleteWatermarkState(a4, 0);
    }
  }
  if ( (a1 & 0x20) != 0 )
  {
    memset(SystemInformation, 0, sizeof(SystemInformation));
    v10 = NtQuerySystemInformation(SystemContextSwitchInformation|0x80, SystemInformation, 0x20u, 0);
    if ( v10 < 0 )
      return v10 | 0x10000000;
    if ( (SystemInformation[0] & 0x4000000) == 0 )
    {
      *a5 |= 0x20u;
      LogFormatOut("TEST FAIL: Required policy is not enforced.\n");
      DeleteWatermarkState(a4, 0);
    }
  }
  if ( (*(_BYTE *)a5 & 0x3C) == 0 )
    UpdateWatermarkState(a2, a3, a4, 0);
  return 0;
}

```

## disassembly

```asm
0x18002ade4  mov     [rsp-28h+arg_0], rbx
0x18002ade9  push    rbp
0x18002adea  push    rsi
0x18002adeb  push    rdi
0x18002adec  push    r14
0x18002adee  push    r15
0x18002adf0  mov     rbp, rsp
0x18002adf3  sub     rsp, 60h
0x18002adf7  mov     rax, cs:__security_cookie
0x18002adfe  xor     rax, rsp
0x18002ae01  mov     [rbp+var_10], rax
0x18002ae05  mov     rbx, [rbp+arg_20]
0x18002ae09  mov     rdi, r9
0x18002ae0c  mov     [rbp+var_40], 0
0x18002ae13  mov     r15, r8
0x18002ae16  mov     [rbp+var_38], 0
0x18002ae1d  mov     r14d, edx
0x18002ae20  mov     [rbp+var_3C], 0
0x18002ae27  mov     esi, ecx
0x18002ae29  test    cl, 4
0x18002ae2c  jz      short loc_18002AE5F
0x18002ae2e  lea     r9, [rbp+var_38]
0x18002ae32  mov     ecx, 1
0x18002ae37  lea     r8, [rbp+var_40]
0x18002ae3b  lea     rdx, [rbp+var_3C]
0x18002ae3f  call    WldpCheckRetailConfiguration2
0x18002ae44  test    eax, eax
0x18002ae46  js      loc_18002AF2E
0x18002ae4c  cmp     [rbp+var_3C], 0
0x18002ae50  jnz     short loc_18002AE5F
0x18002ae52  or      dword ptr [rbx], 4
0x18002ae55  xor     edx, edx; unsigned __int16 *
0x18002ae57  mov     rcx, rdi; unsigned __int16 *
0x18002ae5a  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002ae5f  test    sil, 8
0x18002ae63  jz      short loc_18002AE96
0x18002ae65  lea     r9, [rbp+var_38]
0x18002ae69  mov     ecx, 2
0x18002ae6e  lea     r8, [rbp+var_40]
0x18002ae72  lea     rdx, [rbp+var_3C]
0x18002ae76  call    WldpCheckRetailConfiguration2
0x18002ae7b  test    eax, eax
0x18002ae7d  js      loc_18002AF2E
0x18002ae83  cmp     [rbp+var_3C], 0
0x18002ae87  jnz     short loc_18002AE96
0x18002ae89  or      dword ptr [rbx], 8
0x18002ae8c  xor     edx, edx; unsigned __int16 *
0x18002ae8e  mov     rcx, rdi; unsigned __int16 *
0x18002ae91  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002ae96  test    sil, 10h
0x18002ae9a  jz      short loc_18002AEC3
0x18002ae9c  lea     rcx, [rbp+var_40]; int *
0x18002aea0  mov     [rbp+var_40], 1
0x18002aea7  call    ?CheckFveBinding@@YAJPEAH@Z; CheckFveBinding(int *)
0x18002aeac  test    eax, eax
0x18002aeae  js      short loc_18002AF2E
0x18002aeb0  cmp     [rbp+var_40], 0
0x18002aeb4  jnz     short loc_18002AEC3
0x18002aeb6  or      dword ptr [rbx], 10h
0x18002aeb9  xor     edx, edx; unsigned __int16 *
0x18002aebb  mov     rcx, rdi; unsigned __int16 *
0x18002aebe  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002aec3  test    sil, 20h
0x18002aec7  jz      short loc_18002AF16
0x18002aec9  xorps   xmm0, xmm0
0x18002aecc  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18002aed0  xor     r9d, r9d; ReturnLength
0x18002aed3  mov     ecx, 0A4h; SystemInformationClass
0x18002aed8  movups  [rbp+SystemInformation], xmm0
0x18002aedc  movups  [rbp+var_20], xmm0
0x18002aee0  lea     r8d, [r9+20h]; SystemInformationLength
0x18002aee4  call    cs:__imp_NtQuerySystemInformation
0x18002aeea  test    eax, eax
0x18002aeec  jns     short loc_18002AEF4
0x18002aeee  bts     eax, 1Ch
0x18002aef2  jmp     short loc_18002AF2E
0x18002aef4  test    dword ptr [rbp+SystemInformation], 4000000h
0x18002aefb  jnz     short loc_18002AF16
0x18002aefd  or      dword ptr [rbx], 20h
0x18002af00  lea     rcx, aTestFailRequir; "TEST FAIL: Required policy is not enfor"...
0x18002af07  call    LogFormatOut
0x18002af0c  xor     edx, edx; unsigned __int16 *
0x18002af0e  mov     rcx, rdi; unsigned __int16 *
0x18002af11  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002af16  test    byte ptr [rbx], 3Ch
0x18002af19  jnz     short loc_18002AF2C
0x18002af1b  xor     r9d, r9d; unsigned __int16 *
0x18002af1e  mov     r8, rdi; unsigned __int16 *
0x18002af21  mov     rdx, r15; lpBuffer
0x18002af24  mov     ecx, r14d; nNumberOfBytesToWrite
0x18002af27  call    ?UpdateWatermarkState@@YAJKPEBEPEBG1@Z; UpdateWatermarkState(ulong,uchar const *,ushort const *,ushort const *)
0x18002af2c  xor     eax, eax
0x18002af2e  mov     rcx, [rbp+var_10]
0x18002af32  xor     rcx, rsp; StackCookie
0x18002af35  call    __security_check_cookie
0x18002af3a  mov     rbx, [rsp+60h+arg_0]
0x18002af42  add     rsp, 60h
0x18002af46  pop     r15
0x18002af48  pop     r14
0x18002af4a  pop     rdi
0x18002af4b  pop     rsi
0x18002af4c  pop     rbp
0x18002af4d  retn
```
