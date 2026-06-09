# Smb2CompleteRead

- ea: `0x1400778b0`
- end: `0x140077b9b`
- name: `Smb2CompleteRead`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400760e0`

## callees

- `0x140005070`
- `0x1400384d0`
- `0x1400778b0`
- `0x140080364`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140077b85`
- `ntoskrnl!IofCallDriver` at `0x140077b85`
- `srvnet!SrvNetIsRdmaConnection` at `0x14007795f`
- `srvnet!SrvNetIsRdmaConnection` at `0x14007795f`

## string_xrefs

- `0x140077a8a`: `Smb2CompleteRead`
- `0x140077abe`: `Smb2CompleteRead`
- `0x140077b69`: `Smb2CompleteRead`

## pseudocode

```c
__int64 __fastcall Smb2CompleteRead(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rdx
  unsigned __int64 v4; // rdi
  __int64 *v5; // rax
  unsigned int v6; // ecx
  __int64 v7; // rdi
  char v8; // al
  __int64 v9; // rcx
  __int64 v11; // rdx
  int v12; // [rsp+20h] [rbp-78h]
  char v13; // [rsp+20h] [rbp-78h]
  int v14; // [rsp+20h] [rbp-78h]
  int v15; // [rsp+20h] [rbp-78h]
  char v16; // [rsp+28h] [rbp-70h]
  char v17; // [rsp+60h] [rbp-38h]
  char v18; // [rsp+68h] [rbp-30h]

  v1 = *(_QWORD *)(a1 + 560);
  v3 = *(unsigned int *)(v1 + 248);
  *(_BYTE *)(v1 + 4) = 1;
  if ( (_DWORD)v3 && byte_140058150 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v1 + 56) + 104LL) + 400LL));
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v1 + 40) + 240LL));
    v4 = (unsigned int)v3;
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v1 + 56) + 104LL) + 416LL), (unsigned int)v3);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v1 + 40) + 256LL), (unsigned int)v3);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v1 + 56) + 104LL) + 576LL), (unsigned int)v3);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v1 + 40) + 376LL), (unsigned int)v3);
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v1 + 56) + 104LL) + 568LL));
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v1 + 40) + 368LL));
    if ( (unsigned __int8)SrvNetIsRdmaConnection(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 24) + 96LL) + 480LL)) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v1 + 56) + 104LL) + 404LL));
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v1 + 56) + 104LL) + 424LL), v4);
    }
    if ( *(_BYTE *)(*(_QWORD *)(v1 + 72) + 245LL) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v1 + 56) + 104LL) + 540LL));
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v1 + 56) + 104LL) + 552LL), v4);
    }
    if ( *(_QWORD *)(v1 + 216) )
    {
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v1 + 56) + 104LL) + 328LL), v4);
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v1 + 40) + 176LL), v4);
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v1 + 56) + 104LL) + 320LL), v4);
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v1 + 40) + 168LL), v4);
    }
  }
  if ( !*(_QWORD *)(v1 + 88) )
    return 0;
  if ( (*(_BYTE *)(v1 + 264) & 1) == 0 )
    return 0;
  v5 = *(__int64 **)(v1 + 200);
  if ( !v5 )
    return 0;
  v6 = 0;
  do
  {
    v6 += *((_DWORD *)v5 + 10);
    if ( v6 >= *(_DWORD *)(v1 + 236) )
      *v5 = 0;
    v5 = (__int64 *)*v5;
  }
  while ( v5 && *v5 );
  LOBYTE(v3) = 2;
  if ( (*(_BYTE *)(v1 + 264) & 2) == 0 )
  {
    v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 96) + 8LL) + 80LL);
    if ( v7 )
    {
      if ( *(_DWORD *)v7 > 0x88u && *(_QWORD *)(v7 + 136) )
      {
        v13 = 1;
        SRV2_PERF_ENTER_EX(a1 + 584, v3, 1370, "Smb2CompleteRead", v13);
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v7 + 136))(
               *(_QWORD *)(v1 + 88),
               *(_QWORD *)(v1 + 200),
               *(_QWORD *)(v1 + 96));
        LOBYTE(v14) = 1;
        v9 = a1 + 584;
        if ( v8 )
        {
          SRV2_PERF_ENTER_EX(v9, 0, 1376, "Smb2CompleteRead", v14);
          return 0;
        }
        SRV2_PERF_ENTER_EX(v9, 0, 1380, "Smb2CompleteRead", v14);
      }
    }
  }
  v18 = 0;
  v17 = 0;
  v16 = 6;
  LOBYTE(v12) = 3;
  Smb2BuildReadOrWriteRequest(
    a1,
    0,
    *(_QWORD *)(v1 + 88),
    *(_QWORD *)(v1 + 96),
    v12,
    v16,
    0,
    *(_DWORD *)(v1 + 236),
    *(_QWORD *)(v1 + 200),
    *(_QWORD *)(v1 + 192),
    *(_DWORD *)(v1 + 252),
    0,
    v17,
    v18);
  LOBYTE(v15) = 1;
  *(_QWORD *)(a1 + 48) = Smb2MdlReadCompleteComplete;
  LOBYTE(v11) = 3;
  SRV2_PERF_ENTER_EX(a1 + 584, v11, 1403, "Smb2CompleteRead", v15);
  IofCallDriver(*(PDEVICE_OBJECT *)(v1 + 96), *(PIRP *)(a1 + 120));
  return 259;
}

```

## disassembly

```asm
0x1400778b0  push    rbx
0x1400778b2  push    rbp
0x1400778b3  push    rsi
0x1400778b4  push    rdi
0x1400778b5  sub     rsp, 78h
0x1400778b9  mov     rbx, [rcx+230h]
0x1400778c0  mov     rsi, rcx
0x1400778c3  mov     edx, [rbx+0F8h]
0x1400778c9  mov     byte ptr [rbx+4], 1
0x1400778cd  test    edx, edx
0x1400778cf  jz      loc_1400779FC
0x1400778d5  cmp     cs:byte_140058150, 0
0x1400778dc  jz      loc_1400779FC
0x1400778e2  mov     rax, [rbx+38h]
0x1400778e6  mov     rcx, [rax+68h]
0x1400778ea  lock inc dword ptr [rcx+190h]
0x1400778f1  mov     rax, [rbx+28h]
0x1400778f5  lock inc dword ptr [rax+0F0h]
0x1400778fc  mov     rax, [rbx+38h]
0x140077900  mov     edi, edx
0x140077902  mov     rcx, [rax+68h]
0x140077906  lock add [rcx+1A0h], rdi
0x14007790e  mov     rax, [rbx+28h]
0x140077912  lock add [rax+100h], rdi
0x14007791a  mov     rax, [rbx+38h]
0x14007791e  mov     rcx, [rax+68h]
0x140077922  lock add [rcx+240h], rdi
0x14007792a  mov     rax, [rbx+28h]
0x14007792e  lock add [rax+178h], rdi
0x140077936  mov     rax, [rbx+38h]
0x14007793a  mov     rcx, [rax+68h]
0x14007793e  lock inc dword ptr [rcx+238h]
0x140077945  mov     rax, [rbx+28h]
0x140077949  lock inc dword ptr [rax+170h]
0x140077950  mov     rax, [rbx+18h]
0x140077954  mov     rcx, [rax+60h]
0x140077958  mov     rcx, [rcx+1E0h]
0x14007795f  call    cs:__imp_SrvNetIsRdmaConnection
0x140077966  nop     dword ptr [rax+rax+00h]
0x14007796b  test    al, al
0x14007796d  jz      short loc_14007798E
0x14007796f  mov     rax, [rbx+38h]
0x140077973  mov     rcx, [rax+68h]
0x140077977  lock inc dword ptr [rcx+194h]
0x14007797e  mov     rax, [rbx+38h]
0x140077982  mov     rcx, [rax+68h]
0x140077986  lock add [rcx+1A8h], rdi
0x14007798e  mov     rax, [rbx+48h]
0x140077992  cmp     byte ptr [rax+0F5h], 0
0x140077999  jz      short loc_1400779BA
0x14007799b  mov     rax, [rbx+38h]
0x14007799f  mov     rcx, [rax+68h]
0x1400779a3  lock inc dword ptr [rcx+21Ch]
0x1400779aa  mov     rax, [rbx+38h]
0x1400779ae  mov     rcx, [rax+68h]
0x1400779b2  lock add [rcx+228h], rdi
0x1400779ba  cmp     qword ptr [rbx+0D8h], 0
0x1400779c2  jz      short loc_1400779FC
0x1400779c4  mov     rax, [rbx+38h]
0x1400779c8  mov     rcx, [rax+68h]
0x1400779cc  lock add [rcx+148h], rdi
0x1400779d4  mov     rax, [rbx+28h]
0x1400779d8  lock add [rax+0B0h], rdi
0x1400779e0  mov     rax, [rbx+38h]
0x1400779e4  mov     rcx, [rax+68h]
0x1400779e8  lock add [rcx+140h], rdi
0x1400779f0  mov     rax, [rbx+28h]
0x1400779f4  lock add [rax+0A8h], rdi
0x1400779fc  cmp     qword ptr [rbx+58h], 0
0x140077a01  jz      loc_140077AD7
0x140077a07  test    byte ptr [rbx+108h], 1
0x140077a0e  jz      loc_140077AD7
0x140077a14  mov     rax, [rbx+0C8h]
0x140077a1b  test    rax, rax
0x140077a1e  jz      loc_140077AD7
0x140077a24  xor     ecx, ecx
0x140077a26  add     ecx, [rax+28h]
0x140077a29  cmp     ecx, [rbx+0ECh]
0x140077a2f  jb      short loc_140077A38
0x140077a31  mov     qword ptr [rax], 0
0x140077a38  mov     rax, [rax]
0x140077a3b  test    rax, rax
0x140077a3e  jz      short loc_140077A46
0x140077a40  cmp     qword ptr [rax], 0
0x140077a44  jnz     short loc_140077A26
0x140077a46  mov     dl, 2
0x140077a48  test    [rbx+108h], dl
0x140077a4e  jnz     loc_140077AEE
0x140077a54  mov     rax, [rbx+60h]
0x140077a58  mov     rcx, [rax+8]
0x140077a5c  mov     rdi, [rcx+50h]
0x140077a60  test    rdi, rdi
0x140077a63  jz      loc_140077AEE
0x140077a69  cmp     dword ptr [rdi], 88h
0x140077a6f  jbe     short loc_140077AEE
0x140077a71  cmp     qword ptr [rdi+88h], 0
0x140077a79  jz      short loc_140077AEE
0x140077a7b  lea     rbp, [rsi+248h]
0x140077a82  mov     [rsp+98h+var_78], 1
0x140077a87  mov     rcx, rbp
0x140077a8a  lea     r9, aSmb2completere; "Smb2CompleteRead"
0x140077a91  mov     r8d, 55Ah
0x140077a97  call    SRV2_PERF_ENTER_EX
0x140077a9c  mov     rax, [rdi+88h]
0x140077aa3  mov     r8, [rbx+60h]
0x140077aa7  mov     rdx, [rbx+0C8h]
0x140077aae  mov     rcx, [rbx+58h]
0x140077ab2  call    _guard_dispatch_icall
0x140077ab7  xor     edx, edx
0x140077ab9  mov     [rsp+98h+var_78], 1
0x140077abe  lea     r9, aSmb2completere; "Smb2CompleteRead"
0x140077ac5  mov     rcx, rbp
0x140077ac8  test    al, al
0x140077aca  jz      short loc_140077AE3
0x140077acc  mov     r8d, 560h
0x140077ad2  call    SRV2_PERF_ENTER_EX
0x140077ad7  xor     eax, eax
0x140077ad9  add     rsp, 78h
0x140077add  pop     rdi
0x140077ade  pop     rsi
0x140077adf  pop     rbp
0x140077ae0  pop     rbx
0x140077ae1  retn
0x140077ae3  mov     r8d, 564h
0x140077ae9  call    SRV2_PERF_ENTER_EX
0x140077aee  mov     rax, [rbx+0C0h]
0x140077af5  xor     edx, edx
0x140077af7  mov     ecx, [rbx+0FCh]
0x140077afd  mov     r9, [rbx+60h]
0x140077b01  mov     r8, [rbx+58h]
0x140077b05  mov     [rsp+98h+var_30], 0
0x140077b0a  mov     [rsp+98h+var_38], 0
0x140077b0f  mov     [rsp+98h+var_40], 0
0x140077b18  mov     [rsp+98h+var_48], ecx
0x140077b1c  mov     rcx, rsi
0x140077b1f  mov     [rsp+98h+var_50], rax
0x140077b24  mov     rax, [rbx+0C8h]
0x140077b2b  mov     [rsp+98h+var_58], rax
0x140077b30  mov     eax, [rbx+0ECh]
0x140077b36  mov     [rsp+98h+var_60], eax
0x140077b3a  mov     [rsp+98h+var_68], 0
0x140077b43  mov     [rsp+98h+var_70], 6
0x140077b48  mov     [rsp+98h+var_78], 3
0x140077b4d  call    Smb2BuildReadOrWriteRequest
0x140077b52  lea     rax, Smb2MdlReadCompleteComplete
0x140077b59  mov     [rsp+98h+var_78], 1
0x140077b5e  lea     rcx, [rsi+248h]
0x140077b65  mov     [rsi+30h], rax
0x140077b69  lea     r9, aSmb2completere; "Smb2CompleteRead"
0x140077b70  mov     r8d, 57Bh
0x140077b76  mov     dl, 3
0x140077b78  call    SRV2_PERF_ENTER_EX
0x140077b7d  mov     rdx, [rsi+78h]; Irp
0x140077b81  mov     rcx, [rbx+60h]; DeviceObject
0x140077b85  call    cs:__imp_IofCallDriver
0x140077b8c  nop     dword ptr [rax+rax+00h]
0x140077b91  mov     eax, 103h
0x140077b96  jmp     loc_140077AD9
```
