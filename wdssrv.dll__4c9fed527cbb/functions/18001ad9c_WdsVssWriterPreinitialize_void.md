# WdsVssWriterPreinitialize(void)

- ea: `0x18001ad9c`
- end: `0x18001ae50`
- name: `?WdsVssWriterPreinitialize@@YAKXZ`
- size: `180`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009da4`

## callees

- `0x18001a594`
- `0x18001a63c`
- `0x18001ad9c`
- `0x18001ae58`
- `0x18001af54`

## import_xrefs

- `ole32!CoInitializeEx` at `0x18001adab`
- `ole32!CoInitializeEx` at `0x18001adab`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001ae12`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001ae3b`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001ae12`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001ae3b`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18001adcc`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18001adcc`

## string_xrefs

- `0x18001ae0b`: `Deployment Server enabled.  Pre-initializing VSS Writer.`
- `0x18001ae34`: `Deployment Server disabled. Not pre-initializing VSS Writer.`

## pseudocode

```c
__int64 WdsVssWriterPreinitialize(void)
{
  unsigned int v0; // ebx
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  int v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = 0;
  v0 = CoInitializeEx(0, 0);
  if ( (int)ElValidateHr(v0, v1, v2, 540) >= 0 )
  {
    v3 = (unsigned int)CheckDeploymentServerRole(&v9);
    if ( !(unsigned int)ElValidateWin32_11(v3, v4, v5, 543) )
    {
      if ( v9 )
      {
        CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"Deployment Server enabled.  Pre-initializing VSS Writer.");
        LODWORD(v3) = IntializeComSecurityForVssCompat();
        ElValidateWin32_11((unsigned int)v3, v6, v7, 550);
      }
      else
      {
        CTrace::Trace(
          (CTrace *)qword_180039310,
          0x20000u,
          L"Deployment Server disabled. Not pre-initializing VSS Writer.");
      }
    }
  }
  else
  {
    LODWORD(v3) = WIN32_FROM_HRESULT(v0);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001ad9c  push    rbx
0x18001ad9e  sub     rsp, 20h
0x18001ada2  and     [rsp+28h+arg_0], 0
0x18001ada7  xor     edx, edx; dwCoInit
0x18001ada9  xor     ecx, ecx; pvReserved
0x18001adab  call    cs:__imp_CoInitializeEx
0x18001adb2  nop     dword ptr [rax+rax+00h]
0x18001adb7  mov     ecx, eax
0x18001adb9  mov     r9d, 21Ch
0x18001adbf  mov     ebx, eax
0x18001adc1  call    ElValidateHr
0x18001adc6  test    eax, eax
0x18001adc8  jns     short loc_18001ADDC
0x18001adca  mov     ecx, ebx
0x18001adcc  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001add3  nop     dword ptr [rax+rax+00h]
0x18001add8  mov     ebx, eax
0x18001adda  jmp     short loc_18001AE47
0x18001addc  lea     rcx, [rsp+28h+arg_0]; int *
0x18001ade1  call    ?CheckDeploymentServerRole@@YAKPEAH@Z; CheckDeploymentServerRole(int *)
0x18001ade6  mov     r9d, 21Fh
0x18001adec  mov     ecx, eax
0x18001adee  mov     ebx, eax
0x18001adf0  call    ElValidateWin32_11
0x18001adf5  test    eax, eax
0x18001adf7  jnz     short loc_18001AE47
0x18001adf9  lea     rcx, qword_180039310
0x18001ae00  mov     edx, 20000h
0x18001ae05  cmp     [rsp+28h+arg_0], eax
0x18001ae09  jz      short loc_18001AE34
0x18001ae0b  lea     r8, aDeploymentServ_2; "Deployment Server enabled.  Pre-initial"...
0x18001ae12  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001ae19  nop     dword ptr [rax+rax+00h]
0x18001ae1e  call    ?IntializeComSecurityForVssCompat@@YAKXZ; IntializeComSecurityForVssCompat(void)
0x18001ae23  mov     r9d, 226h
0x18001ae29  mov     ecx, eax
0x18001ae2b  mov     ebx, eax
0x18001ae2d  call    ElValidateWin32_11
0x18001ae32  jmp     short loc_18001AE47
0x18001ae34  lea     r8, aDeploymentServ_1; "Deployment Server disabled. Not pre-ini"...
0x18001ae3b  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001ae42  nop     dword ptr [rax+rax+00h]
0x18001ae47  mov     eax, ebx
0x18001ae49  add     rsp, 20h
0x18001ae4d  pop     rbx
0x18001ae4e  retn
```
