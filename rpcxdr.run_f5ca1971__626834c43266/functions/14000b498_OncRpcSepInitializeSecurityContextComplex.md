# OncRpcSepInitializeSecurityContextComplex

- ea: `0x14000b498`
- end: `0x14000b61b`
- name: `OncRpcSepInitializeSecurityContextComplex`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140008988`

## callees

- `0x1400020c0`
- `0x14000a1ec`
- `0x14000b498`

## import_xrefs

- `ksecdd!InitializeSecurityContextW` at `0x14000b558`
- `ksecdd!InitializeSecurityContextW` at `0x14000b558`
- `ksecdd!MapSecurityError` at `0x14000b57d`
- `ksecdd!MapSecurityError` at `0x14000b57d`

## pseudocode

```c
__int64 __fastcall OncRpcSepInitializeSecurityContextComplex(
        struct _SecHandle *a1,
        __int64 a2,
        struct _SecHandle *a3,
        UNICODE_STRING *a4,
        int a5,
        unsigned int *a6,
        _DWORD *a7,
        __int64 a8,
        __int64 a9,
        unsigned int a10,
        _QWORD *a11,
        _DWORD *a12,
        PTimeStamp a13)
{
  unsigned int v13; // eax
  SECURITY_STATUS v14; // r8d
  NTSTATUS v15; // eax
  unsigned int v16; // ebx
  _DWORD v18[2]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v19; // [rsp+70h] [rbp-29h]
  _DWORD v20[2]; // [rsp+78h] [rbp-21h] BYREF
  __int64 v21; // [rsp+80h] [rbp-19h]
  struct _SecBufferDesc v22; // [rsp+88h] [rbp-11h] BYREF
  struct _SecBufferDesc v23; // [rsp+98h] [rbp-1h] BYREF

  a10 = 0;
  v23.pBuffers = (PSecBuffer)v20;
  v20[1] = 2;
  v22.pBuffers = (PSecBuffer)v18;
  v18[1] = 2;
  v23.ulVersion = 0;
  v23.cBuffers = 1;
  v21 = 0;
  v20[0] = 0;
  v22.ulVersion = 0;
  v22.cBuffers = 1;
  v19 = 0;
  v18[0] = 0;
  v13 = InitializeSecurityContextW(a1, 0, a4, a5 | 0x100, 0, 0x10u, &v23, 0, a3, &v22, &a10, a13);
  *a6 = v13;
  *a7 = OncRpcSeSecStatusToGssMajor(v13);
  v15 = MapSecurityError(v14);
  v16 = v15;
  if ( v15 >= 0 )
  {
    *a11 = v19;
    *a12 = v18[0];
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v15);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, v16);
  return v16;
}

```

## disassembly

```asm
0x14000b498  mov     r11, rsp
0x14000b49b  mov     [r11+8], rbx
0x14000b49f  mov     [r11+10h], rsi
0x14000b4a3  push    rbp
0x14000b4a4  lea     rbp, [r11-17h]
0x14000b4a8  sub     rsp, 0A0h
0x14000b4af  mov     r10, r9
0x14000b4b2  mov     [rbp+0Fh+arg_48], 0
0x14000b4b9  mov     r9d, [rbp+0Fh+arg_20]
0x14000b4bd  lea     rax, [rbp+0Fh+var_30]
0x14000b4c1  mov     [rbp+0Fh+var_8], rax
0x14000b4c5  mov     edx, 2
0x14000b4ca  lea     rax, [rbp+0Fh+var_40]
0x14000b4ce  mov     [rbp+0Fh+var_2C], edx
0x14000b4d1  mov     [rbp+0Fh+var_18], rax
0x14000b4d5  bts     r9d, 8; fContextReq
0x14000b4da  mov     rax, [rbp+0Fh+arg_60]
0x14000b4de  mov     [r11-50h], rax
0x14000b4e2  lea     rax, [rbp+0Fh+arg_48]
0x14000b4e6  mov     [r11-58h], rax
0x14000b4ea  lea     rax, [rbp+0Fh+var_20]
0x14000b4ee  mov     [r11-60h], rax
0x14000b4f2  lea     rax, [rbp+0Fh+var_10]
0x14000b4f6  mov     [r11-68h], r8
0x14000b4fa  mov     r8, r10; pTargetName
0x14000b4fd  mov     [rsp+0A0h+Reserved2], 0; Reserved2
0x14000b505  mov     [r11-78h], rax
0x14000b509  mov     [rbp+0Fh+var_3C], edx
0x14000b50c  xor     edx, edx; phContext
0x14000b50e  mov     [rsp+0A0h+TargetDataRep], 10h; TargetDataRep
0x14000b516  mov     [rsp+0A0h+Reserved1], 0; Reserved1
0x14000b51e  mov     [rbp+0Fh+var_10], 0
0x14000b525  mov     [rbp+0Fh+var_C], 1
0x14000b52c  mov     [rbp+0Fh+var_28], 0
0x14000b534  mov     [rbp+0Fh+var_30], 0
0x14000b53b  mov     [rbp+0Fh+var_20], 0
0x14000b542  mov     [rbp+0Fh+var_1C], 1
0x14000b549  mov     [rbp+0Fh+var_38], 0
0x14000b551  mov     [rbp+0Fh+var_40], 0
0x14000b558  call    cs:__imp_InitializeSecurityContextW
0x14000b55f  nop     dword ptr [rax+rax+00h]
0x14000b564  mov     rcx, [rbp+0Fh+arg_28]
0x14000b568  mov     r8d, eax
0x14000b56b  mov     [rcx], eax
0x14000b56d  mov     ecx, eax
0x14000b56f  call    OncRpcSeSecStatusToGssMajor
0x14000b574  mov     rcx, [rbp+0Fh+arg_30]
0x14000b578  mov     [rcx], eax
0x14000b57a  mov     ecx, r8d; SecStatus
0x14000b57d  call    cs:__imp_MapSecurityError
0x14000b584  nop     dword ptr [rax+rax+00h]
0x14000b589  lea     rsi, WPP_GLOBAL_Control
0x14000b590  mov     ebx, eax
0x14000b592  test    eax, eax
0x14000b594  jns     short loc_14000B5C4
0x14000b596  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b59d  cmp     rcx, rsi
0x14000b5a0  jz      short loc_14000B5D8
0x14000b5a2  mov     edx, [rcx+2Ch]
0x14000b5a5  test    dl, 40h
0x14000b5a8  jz      short loc_14000B5D8
0x14000b5aa  mov     rcx, [rcx+18h]
0x14000b5ae  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000b5b5  mov     edx, 14h
0x14000b5ba  mov     r9d, eax
0x14000b5bd  call    WPP_SF_d
0x14000b5c2  jmp     short loc_14000B5D8
0x14000b5c4  mov     rcx, [rbp+0Fh+arg_50]
0x14000b5c8  mov     rax, [rbp+0Fh+var_38]
0x14000b5cc  mov     [rcx], rax
0x14000b5cf  mov     rcx, [rbp+0Fh+arg_58]
0x14000b5d3  mov     eax, [rbp+0Fh+var_40]
0x14000b5d6  mov     [rcx], eax
0x14000b5d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b5df  cmp     rcx, rsi
0x14000b5e2  jz      short loc_14000B603
0x14000b5e4  mov     eax, [rcx+2Ch]
0x14000b5e7  test    al, 1
0x14000b5e9  jz      short loc_14000B603
0x14000b5eb  mov     rcx, [rcx+18h]
0x14000b5ef  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000b5f6  mov     edx, 15h
0x14000b5fb  mov     r9d, ebx
0x14000b5fe  call    WPP_SF_d
0x14000b603  lea     r11, [rsp+0A0h+var_s0]
0x14000b60b  mov     eax, ebx
0x14000b60d  mov     rbx, [r11+10h]
0x14000b611  mov     rsi, [r11+18h]
0x14000b615  mov     rsp, r11
0x14000b618  pop     rbp
0x14000b619  retn
```
