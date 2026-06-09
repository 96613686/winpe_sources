# Smb2CompleteRead

- ea: `0x140077900`
- end: `0x140077beb`
- name: `Smb2CompleteRead`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140076130`

## callees

- `0x140005070`
- `0x1400384d0`
- `0x140077900`
- `0x1400803b4`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140077bd5`
- `ntoskrnl!IofCallDriver` at `0x140077bd5`
- `srvnet!SrvNetIsRdmaConnection` at `0x1400779af`
- `srvnet!SrvNetIsRdmaConnection` at `0x1400779af`

## string_xrefs

- `0x140077ada`: `Smb2CompleteRead`
- `0x140077b0e`: `Smb2CompleteRead`
- `0x140077bb9`: `Smb2CompleteRead`

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
0x140077900  push    rbx
0x140077902  push    rbp
0x140077903  push    rsi
0x140077904  push    rdi
0x140077905  sub     rsp, 78h
0x140077909  mov     rbx, [rcx+230h]
0x140077910  mov     rsi, rcx
0x140077913  mov     edx, [rbx+0F8h]
0x140077919  mov     byte ptr [rbx+4], 1
0x14007791d  test    edx, edx
0x14007791f  jz      loc_140077A4C
0x140077925  cmp     cs:byte_140058150, 0
0x14007792c  jz      loc_140077A4C
0x140077932  mov     rax, [rbx+38h]
0x140077936  mov     rcx, [rax+68h]
0x14007793a  lock inc dword ptr [rcx+190h]
0x140077941  mov     rax, [rbx+28h]
0x140077945  lock inc dword ptr [rax+0F0h]
0x14007794c  mov     rax, [rbx+38h]
0x140077950  mov     edi, edx
0x140077952  mov     rcx, [rax+68h]
0x140077956  lock add [rcx+1A0h], rdi
0x14007795e  mov     rax, [rbx+28h]
0x140077962  lock add [rax+100h], rdi
0x14007796a  mov     rax, [rbx+38h]
0x14007796e  mov     rcx, [rax+68h]
0x140077972  lock add [rcx+240h], rdi
0x14007797a  mov     rax, [rbx+28h]
0x14007797e  lock add [rax+178h], rdi
0x140077986  mov     rax, [rbx+38h]
0x14007798a  mov     rcx, [rax+68h]
0x14007798e  lock inc dword ptr [rcx+238h]
0x140077995  mov     rax, [rbx+28h]
0x140077999  lock inc dword ptr [rax+170h]
0x1400779a0  mov     rax, [rbx+18h]
0x1400779a4  mov     rcx, [rax+60h]
0x1400779a8  mov     rcx, [rcx+1E0h]
0x1400779af  call    cs:__imp_SrvNetIsRdmaConnection
0x1400779b6  nop     dword ptr [rax+rax+00h]
0x1400779bb  test    al, al
0x1400779bd  jz      short loc_1400779DE
0x1400779bf  mov     rax, [rbx+38h]
0x1400779c3  mov     rcx, [rax+68h]
0x1400779c7  lock inc dword ptr [rcx+194h]
0x1400779ce  mov     rax, [rbx+38h]
0x1400779d2  mov     rcx, [rax+68h]
0x1400779d6  lock add [rcx+1A8h], rdi
0x1400779de  mov     rax, [rbx+48h]
0x1400779e2  cmp     byte ptr [rax+0F5h], 0
0x1400779e9  jz      short loc_140077A0A
0x1400779eb  mov     rax, [rbx+38h]
0x1400779ef  mov     rcx, [rax+68h]
0x1400779f3  lock inc dword ptr [rcx+21Ch]
0x1400779fa  mov     rax, [rbx+38h]
0x1400779fe  mov     rcx, [rax+68h]
0x140077a02  lock add [rcx+228h], rdi
0x140077a0a  cmp     qword ptr [rbx+0D8h], 0
0x140077a12  jz      short loc_140077A4C
0x140077a14  mov     rax, [rbx+38h]
0x140077a18  mov     rcx, [rax+68h]
0x140077a1c  lock add [rcx+148h], rdi
0x140077a24  mov     rax, [rbx+28h]
0x140077a28  lock add [rax+0B0h], rdi
0x140077a30  mov     rax, [rbx+38h]
0x140077a34  mov     rcx, [rax+68h]
0x140077a38  lock add [rcx+140h], rdi
0x140077a40  mov     rax, [rbx+28h]
0x140077a44  lock add [rax+0A8h], rdi
0x140077a4c  cmp     qword ptr [rbx+58h], 0
0x140077a51  jz      loc_140077B27
0x140077a57  test    byte ptr [rbx+108h], 1
0x140077a5e  jz      loc_140077B27
0x140077a64  mov     rax, [rbx+0C8h]
0x140077a6b  test    rax, rax
0x140077a6e  jz      loc_140077B27
0x140077a74  xor     ecx, ecx
0x140077a76  add     ecx, [rax+28h]
0x140077a79  cmp     ecx, [rbx+0ECh]
0x140077a7f  jb      short loc_140077A88
0x140077a81  mov     qword ptr [rax], 0
0x140077a88  mov     rax, [rax]
0x140077a8b  test    rax, rax
0x140077a8e  jz      short loc_140077A96
0x140077a90  cmp     qword ptr [rax], 0
0x140077a94  jnz     short loc_140077A76
0x140077a96  mov     dl, 2
0x140077a98  test    [rbx+108h], dl
0x140077a9e  jnz     loc_140077B3E
0x140077aa4  mov     rax, [rbx+60h]
0x140077aa8  mov     rcx, [rax+8]
0x140077aac  mov     rdi, [rcx+50h]
0x140077ab0  test    rdi, rdi
0x140077ab3  jz      loc_140077B3E
0x140077ab9  cmp     dword ptr [rdi], 88h
0x140077abf  jbe     short loc_140077B3E
0x140077ac1  cmp     qword ptr [rdi+88h], 0
0x140077ac9  jz      short loc_140077B3E
0x140077acb  lea     rbp, [rsi+248h]
0x140077ad2  mov     [rsp+98h+var_78], 1
0x140077ad7  mov     rcx, rbp
0x140077ada  lea     r9, aSmb2completere; "Smb2CompleteRead"
0x140077ae1  mov     r8d, 55Ah
0x140077ae7  call    SRV2_PERF_ENTER_EX
0x140077aec  mov     rax, [rdi+88h]
0x140077af3  mov     r8, [rbx+60h]
0x140077af7  mov     rdx, [rbx+0C8h]
0x140077afe  mov     rcx, [rbx+58h]
0x140077b02  call    _guard_dispatch_icall
0x140077b07  xor     edx, edx
0x140077b09  mov     [rsp+98h+var_78], 1
0x140077b0e  lea     r9, aSmb2completere; "Smb2CompleteRead"
0x140077b15  mov     rcx, rbp
0x140077b18  test    al, al
0x140077b1a  jz      short loc_140077B33
0x140077b1c  mov     r8d, 560h
0x140077b22  call    SRV2_PERF_ENTER_EX
0x140077b27  xor     eax, eax
0x140077b29  add     rsp, 78h
0x140077b2d  pop     rdi
0x140077b2e  pop     rsi
0x140077b2f  pop     rbp
0x140077b30  pop     rbx
0x140077b31  retn
0x140077b33  mov     r8d, 564h
0x140077b39  call    SRV2_PERF_ENTER_EX
0x140077b3e  mov     rax, [rbx+0C0h]
0x140077b45  xor     edx, edx
0x140077b47  mov     ecx, [rbx+0FCh]
0x140077b4d  mov     r9, [rbx+60h]
0x140077b51  mov     r8, [rbx+58h]
0x140077b55  mov     [rsp+98h+var_30], 0
0x140077b5a  mov     [rsp+98h+var_38], 0
0x140077b5f  mov     [rsp+98h+var_40], 0
0x140077b68  mov     [rsp+98h+var_48], ecx
0x140077b6c  mov     rcx, rsi
0x140077b6f  mov     [rsp+98h+var_50], rax
0x140077b74  mov     rax, [rbx+0C8h]
0x140077b7b  mov     [rsp+98h+var_58], rax
0x140077b80  mov     eax, [rbx+0ECh]
0x140077b86  mov     [rsp+98h+var_60], eax
0x140077b8a  mov     [rsp+98h+var_68], 0
0x140077b93  mov     [rsp+98h+var_70], 6
0x140077b98  mov     [rsp+98h+var_78], 3
0x140077b9d  call    Smb2BuildReadOrWriteRequest
0x140077ba2  lea     rax, Smb2MdlReadCompleteComplete
0x140077ba9  mov     [rsp+98h+var_78], 1
0x140077bae  lea     rcx, [rsi+248h]
0x140077bb5  mov     [rsi+30h], rax
0x140077bb9  lea     r9, aSmb2completere; "Smb2CompleteRead"
0x140077bc0  mov     r8d, 57Bh
0x140077bc6  mov     dl, 3
0x140077bc8  call    SRV2_PERF_ENTER_EX
0x140077bcd  mov     rdx, [rsi+78h]; Irp
0x140077bd1  mov     rcx, [rbx+60h]; DeviceObject
0x140077bd5  call    cs:__imp_IofCallDriver
0x140077bdc  nop     dword ptr [rax+rax+00h]
0x140077be1  mov     eax, 103h
0x140077be6  jmp     loc_140077B29
```
