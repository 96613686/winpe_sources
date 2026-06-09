# WdsVssWriterInitialize(void)

- ea: `0x18001ac90`
- end: `0x18001ad94`
- name: `?WdsVssWriterInitialize@@YAKXZ`
- size: `260`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009da4`

## callees

- `0x18001a594`
- `0x18001ac90`
- `0x18001ae58`
- `0x18001af54`

## import_xrefs

- `VSSAPI!?Initialize@CVssJetWriter@@QEAAJU_GUID@@PEBG_N211K@Z` at `0x18001ad27`
- `VSSAPI!?Initialize@CVssJetWriter@@QEAAJU_GUID@@PEBG_N211K@Z` at `0x18001ad27`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001acdd`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001ad7a`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001acdd`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001ad7a`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18001ad63`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18001ad63`

## string_xrefs

- `0x18001ad01`: `WDS VSS Writer`
- `0x18001acd6`: `Deployment Server enabled.  Initializing VSS Writer.`
- `0x18001ad73`: `Deployment Server disabled. Not initializing VSS Writer.`

## pseudocode

```c
__int64 WdsVssWriterInitialize(void)
{
  __int64 v0; // rbx
  __int64 v1; // rdx
  __int64 v2; // r8
  unsigned int v3; // edi
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  struct _GUID v9; // [rsp+40h] [rbp-18h] BYREF
  int v10; // [rsp+60h] [rbp+8h] BYREF

  v10 = 0;
  v0 = CheckDeploymentServerRole(&v10);
  if ( !(unsigned int)ElValidateWin32_11(v0, v1, v2, 586) )
  {
    if ( v10 )
    {
      CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"Deployment Server enabled.  Initializing VSS Writer.");
      v9 = (struct _GUID)xmmword_180023208;
      v3 = CVssJetWriter::Initialize(
             (CVssJetWriter *)&off_180028160,
             &v9,
             L"WDS VSS Writer",
             1,
             0,
             (const unsigned __int16 *)&dword_180021EC4,
             (const unsigned __int16 *)&dword_180021EC4,
             0);
      if ( (int)ElValidateHr(v3, v4, v5, 191) >= 0 )
        dword_180028178 = 1;
      if ( (int)ElValidateHr(v3, v6, v7, 593) < 0 )
        LODWORD(v0) = WIN32_FROM_HRESULT(v3);
    }
    else
    {
      CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"Deployment Server disabled. Not initializing VSS Writer.");
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18001ac90  mov     [rsp+arg_8], rbx
0x18001ac95  push    rdi
0x18001ac96  sub     rsp, 50h
0x18001ac9a  and     [rsp+58h+arg_0], 0
0x18001ac9f  lea     rcx, [rsp+58h+arg_0]; int *
0x18001aca4  call    ?CheckDeploymentServerRole@@YAKPEAH@Z; CheckDeploymentServerRole(int *)
0x18001aca9  mov     r9d, 24Ah
0x18001acaf  mov     ecx, eax
0x18001acb1  mov     ebx, eax
0x18001acb3  call    ElValidateWin32_11
0x18001acb8  test    eax, eax
0x18001acba  jnz     loc_18001AD86
0x18001acc0  lea     rcx, qword_180039310
0x18001acc7  mov     edx, 20000h
0x18001accc  cmp     [rsp+58h+arg_0], eax
0x18001acd0  jz      loc_18001AD73
0x18001acd6  lea     r8, aDeploymentServ; "Deployment Server enabled.  Initializin"...
0x18001acdd  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001ace4  nop     dword ptr [rax+rax+00h]
0x18001ace9  and     [rsp+58h+var_20], 0
0x18001acee  lea     rax, dword_180021EC4
0x18001acf5  movups  xmm0, cs:xmmword_180023208
0x18001acfc  mov     [rsp+58h+var_28], rax
0x18001ad01  lea     r8, aWdsVssWriter; "WDS VSS Writer"
0x18001ad08  mov     [rsp+58h+var_30], rax
0x18001ad0d  lea     rdx, [rsp+58h+var_18]
0x18001ad12  mov     r9b, 1
0x18001ad15  mov     [rsp+58h+var_38], 0
0x18001ad1a  lea     rcx, off_180028160
0x18001ad21  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x18001ad27  call    cs:__imp_?Initialize@CVssJetWriter@@QEAAJU_GUID@@PEBG_N211K@Z; CVssJetWriter::Initialize(_GUID,ushort const *,bool,bool,ushort const *,ushort const *,ulong)
0x18001ad2e  nop     dword ptr [rax+rax+00h]
0x18001ad33  mov     ecx, eax
0x18001ad35  mov     r9d, 0BFh
0x18001ad3b  mov     edi, eax
0x18001ad3d  call    ElValidateHr
0x18001ad42  test    eax, eax
0x18001ad44  js      short loc_18001AD50
0x18001ad46  mov     cs:dword_180028178, 1
0x18001ad50  mov     r9d, 251h
0x18001ad56  mov     ecx, edi
0x18001ad58  call    ElValidateHr
0x18001ad5d  test    eax, eax
0x18001ad5f  jns     short loc_18001AD86
0x18001ad61  mov     ecx, edi
0x18001ad63  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001ad6a  nop     dword ptr [rax+rax+00h]
0x18001ad6f  mov     ebx, eax
0x18001ad71  jmp     short loc_18001AD86
0x18001ad73  lea     r8, aDeploymentServ_0; "Deployment Server disabled. Not initial"...
0x18001ad7a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001ad81  nop     dword ptr [rax+rax+00h]
0x18001ad86  mov     eax, ebx
0x18001ad88  mov     rbx, [rsp+58h+arg_8]
0x18001ad8d  add     rsp, 50h
0x18001ad91  pop     rdi
0x18001ad92  retn
```
