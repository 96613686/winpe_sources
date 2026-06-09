# Smb2ContinueMdlRead

- ea: `0x14007fd00`
- end: `0x1400800bd`
- name: `Smb2ContinueMdlRead`
- size: `957`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14007f4c0`

## callees

- `0x140004560`
- `0x140007400`
- `0x140007900`
- `0x140008190`
- `0x14000a034`
- `0x1400222ec`
- `0x140038980`
- `0x14007fd00`
- `0x1400800c4`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x14007fe1f`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007fe1f`
- `ntoskrnl!MmUnmapLockedPages` at `0x14008005c`
- `ntoskrnl!MmUnmapLockedPages` at `0x14008005c`
- `srvnet!SrvNetIsRdmaConnection` at `0x14007ff3f`
- `srvnet!SrvNetIsRdmaConnection` at `0x14007ff3f`

## string_xrefs

- `0x14007ffcc`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`

## pseudocode

```c
NTSTATUS __fastcall Smb2ContinueMdlRead(__int64 a1)
{
  __int64 v2; // rdi
  unsigned int v3; // ebp
  __int64 v4; // rsi
  __int64 *v5; // rcx
  char v6; // dl
  int v7; // r14d
  unsigned int v8; // eax
  unsigned int v9; // ecx
  unsigned __int8 v10; // al
  unsigned __int8 v11; // cl
  __int64 v12; // rax
  ULONG v13; // r15d
  __int64 v14; // r14
  void *v15; // r12
  struct _MDL *v16; // r13
  __int64 v17; // rcx
  __int64 v18; // rdx

  v2 = *(_QWORD *)(a1 + 560);
  v3 = 0;
  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 312) + 24LL);
  v5 = *(__int64 **)(*(_QWORD *)(a1 + 120) + 8LL);
  *(_BYTE *)(v2 + 264) |= 1u;
  v6 = *(_BYTE *)(v2 + 264);
  *(_QWORD *)(v2 + 200) = v5;
  v7 = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL);
  if ( v7 < 0 )
  {
    if ( v7 != -1073741807 )
    {
      *(_BYTE *)(v2 + 264) = v6 & 0xFE;
      return Smb2RestartNonMdlRead(a1);
    }
    if ( !v5 )
      *(_BYTE *)(v2 + 264) = v6 & 0xFE;
  }
  else
  {
    for ( ; v5; v5 = (__int64 *)*v5 )
      v3 += *((_DWORD *)v5 + 10);
    *(_DWORD *)(v2 + 236) = v3;
  }
  Smb2SequentialReadComplete(a1);
  if ( v3 < *(_DWORD *)(v2 + 240) || !v3 && v7 == -1073741807 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1);
    }
    Smb2SetError(a1, 3221225489LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c", 1853);
    v17 = a1;
    return Srv2CompleteWorkItem(v17, 0);
  }
  v8 = 0;
  v9 = v3;
  if ( *(_QWORD *)(v2 + 216) )
  {
    v9 = 0;
    v8 = v3;
  }
  *(_DWORD *)(v4 + 68) = v9;
  *(_DWORD *)(v4 + 72) = v8;
  if ( byte_140058150 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 104LL) + 400LL));
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v2 + 40) + 240LL));
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 104LL) + 416LL), v3);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v2 + 40) + 256LL), v3);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 104LL) + 576LL), v3);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v2 + 40) + 376LL), v3);
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 104LL) + 568LL));
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v2 + 40) + 368LL));
    if ( (unsigned __int8)SrvNetIsRdmaConnection(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 24) + 96LL) + 480LL)) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 104LL) + 404LL));
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 104LL) + 424LL), v3);
    }
    if ( *(_BYTE *)(*(_QWORD *)(v2 + 72) + 245LL) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 104LL) + 540LL));
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 104LL) + 552LL), v3);
    }
    if ( *(_QWORD *)(v2 + 216) )
    {
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 104LL) + 328LL), v3);
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v2 + 40) + 176LL), v3);
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 104LL) + 320LL), v3);
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v2 + 40) + 168LL), v3);
    }
  }
  v10 = *(_BYTE *)(v2 + 265);
  v11 = 80;
  *(_BYTE *)(v4 + 67) = 0;
  *(_DWORD *)(v4 + 76) = 0;
  if ( v10 > 0x50u )
    v11 = v10;
  *(_WORD *)(v4 + 64) = 17;
  *(_BYTE *)(v4 + 66) = v11;
  memset((void *)(v4 + 80), 0, v11 - 80LL);
  v12 = *(_QWORD *)(a1 + 312);
  v13 = *(unsigned __int8 *)(v4 + 66);
  v14 = *(_QWORD *)(v12 + 80);
  v15 = *(void **)(v12 + 24);
  v16 = *(struct _MDL **)(v12 + 56);
  if ( (*(_BYTE *)(v14 + 10) & 0x20) != 0 )
    MmUnmapLockedPages(*(PVOID *)(v14 + 24), *(PMDL *)(v12 + 80));
  IoBuildPartialMdl(v16, (PMDL)v14, v15, v13);
  **(_QWORD **)(*(_QWORD *)(a1 + 312) + 80LL) = *(_QWORD *)(v2 + 200);
  *(_DWORD *)(a1 + 484) |= 4u;
  Smb2SetSuccess(a1, 0);
  *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL) = *(_DWORD *)(v4 + 68) + *(unsigned __int8 *)(v4 + 66);
  v17 = a1;
  v18 = *(_QWORD *)(v2 + 216);
  if ( !v18 )
    return Srv2CompleteWorkItem(v17, 0);
  return Srv2WriteDirectDataAndCompleteWorkItem(
           (_QWORD *)a1,
           v18,
           *(unsigned int *)(v2 + 232),
           *(_QWORD *)(v2 + 200),
           v3);
}

```

## disassembly

```asm
0x14007fd00  push    rbx
0x14007fd02  push    rbp
0x14007fd03  push    rsi
0x14007fd04  push    rdi
0x14007fd05  push    r14
0x14007fd07  sub     rsp, 30h
0x14007fd0b  mov     rax, [rcx+138h]
0x14007fd12  mov     rbx, rcx
0x14007fd15  mov     rdi, [rcx+230h]
0x14007fd1c  xor     ebp, ebp
0x14007fd1e  mov     rsi, [rax+18h]
0x14007fd22  mov     rax, [rcx+78h]
0x14007fd26  mov     rcx, [rax+8]
0x14007fd2a  or      byte ptr [rdi+108h], 1
0x14007fd31  movzx   edx, byte ptr [rdi+108h]
0x14007fd38  mov     [rdi+0C8h], rcx
0x14007fd3f  mov     rax, [rbx+78h]
0x14007fd43  mov     r14d, [rax+30h]
0x14007fd47  test    r14d, r14d
0x14007fd4a  js      loc_14007FE97
0x14007fd50  test    rcx, rcx
0x14007fd53  jz      short loc_14007FD60
0x14007fd55  add     ebp, [rcx+28h]
0x14007fd58  mov     rcx, [rcx]
0x14007fd5b  test    rcx, rcx
0x14007fd5e  jnz     short loc_14007FD55
0x14007fd60  mov     [rdi+0ECh], ebp
0x14007fd66  mov     rcx, rbx
0x14007fd69  call    Smb2SequentialReadComplete
0x14007fd6e  cmp     ebp, [rdi+0F0h]
0x14007fd74  jb      loc_14007FFAF
0x14007fd7a  test    ebp, ebp
0x14007fd7c  jz      loc_14007FFFF
0x14007fd82  mov     rdx, [rdi+0D8h]
0x14007fd89  xor     eax, eax
0x14007fd8b  mov     [rsp+58h+arg_0], r12
0x14007fd90  test    rdx, rdx
0x14007fd93  mov     [rsp+58h+arg_8], r13
0x14007fd98  mov     ecx, ebp
0x14007fd9a  cmovnz  ecx, eax
0x14007fd9d  mov     [rsp+58h+arg_10], r15
0x14007fda2  cmovnz  eax, ebp
0x14007fda5  mov     [rsi+44h], ecx
0x14007fda8  mov     [rsi+48h], eax
0x14007fdab  cmp     cs:byte_140058150, 0
0x14007fdb2  jnz     loc_14007FEC1
0x14007fdb8  movzx   eax, byte ptr [rdi+109h]
0x14007fdbf  mov     ecx, 50h ; 'P'
0x14007fdc4  cmp     al, cl
0x14007fdc6  mov     byte ptr [rsi+43h], 0
0x14007fdca  mov     dword ptr [rsi+4Ch], 0
0x14007fdd1  cmova   ecx, eax
0x14007fdd4  mov     word ptr [rsi+40h], 11h
0x14007fdda  movzx   r8d, cl
0x14007fdde  xor     edx, edx; Val
0x14007fde0  mov     [rsi+42h], cl
0x14007fde3  sub     r8, 50h ; 'P'; Size
0x14007fde7  lea     rcx, [rsi+50h]; void *
0x14007fdeb  call    memset
0x14007fdf0  mov     rax, [rbx+138h]
0x14007fdf7  movzx   r15d, byte ptr [rsi+42h]
0x14007fdfc  mov     r14, [rax+50h]
0x14007fe00  mov     r12, [rax+18h]
0x14007fe04  mov     r13, [rax+38h]
0x14007fe08  test    byte ptr [r14+0Ah], 20h
0x14007fe0d  jnz     loc_140080055
0x14007fe13  mov     r9d, r15d; Length
0x14007fe16  mov     r8, r12; VirtualAddress
0x14007fe19  mov     rdx, r14; TargetMdl
0x14007fe1c  mov     rcx, r13; SourceMdl
0x14007fe1f  call    cs:__imp_IoBuildPartialMdl
0x14007fe26  nop     dword ptr [rax+rax+00h]
0x14007fe2b  mov     rax, [rbx+138h]
0x14007fe32  xor     edx, edx
0x14007fe34  mov     rcx, [rax+50h]
0x14007fe38  mov     rax, [rdi+0C8h]
0x14007fe3f  mov     [rcx], rax
0x14007fe42  mov     rcx, rbx
0x14007fe45  or      dword ptr [rbx+1E4h], 4
0x14007fe4c  call    Smb2SetSuccess
0x14007fe51  movzx   ecx, byte ptr [rsi+42h]
0x14007fe55  add     ecx, [rsi+44h]
0x14007fe58  mov     rax, [rbx+138h]
0x14007fe5f  mov     r15, [rsp+58h+arg_10]
0x14007fe64  mov     r13, [rsp+58h+arg_8]
0x14007fe69  mov     r12, [rsp+58h+arg_0]
0x14007fe6e  mov     [rax+24h], ecx
0x14007fe71  mov     rcx, rbx
0x14007fe74  mov     rdx, [rdi+0D8h]
0x14007fe7b  test    rdx, rdx
0x14007fe7e  jnz     loc_14008006D
0x14007fe84  xor     edx, edx
0x14007fe86  call    Srv2CompleteWorkItem
0x14007fe8b  add     rsp, 30h
0x14007fe8f  pop     r14
0x14007fe91  pop     rdi
0x14007fe92  pop     rsi
0x14007fe93  pop     rbp
0x14007fe94  pop     rbx
0x14007fe95  retn
0x14007fe97  cmp     r14d, 0C0000011h
0x14007fe9e  jz      loc_14007FFE8
0x14007fea4  and     dl, 0FEh
0x14007fea7  mov     rcx, rbx
0x14007feaa  mov     [rdi+108h], dl
0x14007feb0  call    Smb2RestartNonMdlRead
0x14007feb5  add     rsp, 30h
0x14007feb9  pop     r14
0x14007febb  pop     rdi
0x14007febc  pop     rsi
0x14007febd  pop     rbp
0x14007febe  pop     rbx
0x14007febf  retn
0x14007fec1  mov     rax, [rdi+38h]
0x14007fec5  mov     rcx, [rax+68h]
0x14007fec9  lock inc dword ptr [rcx+190h]
0x14007fed0  mov     rax, [rdi+28h]
0x14007fed4  lock inc dword ptr [rax+0F0h]
0x14007fedb  mov     rax, [rdi+38h]
0x14007fedf  mov     r14d, ebp
0x14007fee2  mov     rcx, [rax+68h]
0x14007fee6  lock add [rcx+1A0h], r14
0x14007feee  mov     rax, [rdi+28h]
0x14007fef2  lock add [rax+100h], r14
0x14007fefa  mov     rax, [rdi+38h]
0x14007fefe  mov     rcx, [rax+68h]
0x14007ff02  lock add [rcx+240h], r14
0x14007ff0a  mov     rax, [rdi+28h]
0x14007ff0e  lock add [rax+178h], r14
0x14007ff16  mov     rax, [rdi+38h]
0x14007ff1a  mov     rcx, [rax+68h]
0x14007ff1e  lock inc dword ptr [rcx+238h]
0x14007ff25  mov     rax, [rdi+28h]
0x14007ff29  lock inc dword ptr [rax+170h]
0x14007ff30  mov     rax, [rdi+18h]
0x14007ff34  mov     rcx, [rax+60h]
0x14007ff38  mov     rcx, [rcx+1E0h]
0x14007ff3f  call    cs:__imp_SrvNetIsRdmaConnection
0x14007ff46  nop     dword ptr [rax+rax+00h]
0x14007ff4b  test    al, al
0x14007ff4d  jnz     loc_14008000D
0x14007ff53  mov     rax, [rdi+48h]
0x14007ff57  cmp     byte ptr [rax+0F5h], 0
0x14007ff5e  jnz     loc_140080031
0x14007ff64  cmp     qword ptr [rdi+0D8h], 0
0x14007ff6c  jz      loc_14007FDB8
0x14007ff72  mov     rax, [rdi+38h]
0x14007ff76  mov     rcx, [rax+68h]
0x14007ff7a  lock add [rcx+148h], r14
0x14007ff82  mov     rax, [rdi+28h]
0x14007ff86  lock add [rax+0B0h], r14
0x14007ff8e  mov     rax, [rdi+38h]
0x14007ff92  mov     rcx, [rax+68h]
0x14007ff96  lock add [rcx+140h], r14
0x14007ff9e  mov     rax, [rdi+28h]
0x14007ffa2  lock add [rax+0A8h], r14
0x14007ffaa  jmp     loc_14007FDB8
0x14007ffaf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007ffb6  lea     rax, WPP_GLOBAL_Control
0x14007ffbd  cmp     rcx, rax
0x14007ffc0  jnz     loc_140080089
0x14007ffc6  mov     r9d, 73Dh
0x14007ffcc  lea     r8, aOnecoreBaseFsR_9; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14007ffd3  mov     edx, 0C0000011h
0x14007ffd8  mov     rcx, rbx
0x14007ffdb  call    _Smb2SetError
0x14007ffe0  mov     rcx, rbx
0x14007ffe3  jmp     loc_14007FE84
0x14007ffe8  test    rcx, rcx
0x14007ffeb  jnz     loc_14007FD66
0x14007fff1  and     dl, 0FEh
0x14007fff4  mov     [rdi+108h], dl
0x14007fffa  jmp     loc_14007FD66
0x14007ffff  cmp     r14d, 0C0000011h
0x140080006  jz      short loc_14007FFAF
0x140080008  jmp     loc_14007FD82
0x14008000d  mov     rax, [rdi+38h]
0x140080011  mov     rcx, [rax+68h]
0x140080015  lock inc dword ptr [rcx+194h]
0x14008001c  mov     rax, [rdi+38h]
0x140080020  mov     rcx, [rax+68h]
0x140080024  lock add [rcx+1A8h], r14
0x14008002c  jmp     loc_14007FF53
0x140080031  mov     rax, [rdi+38h]
0x140080035  mov     rcx, [rax+68h]
0x140080039  lock inc dword ptr [rcx+21Ch]
0x140080040  mov     rax, [rdi+38h]
0x140080044  mov     rcx, [rax+68h]
0x140080048  lock add [rcx+228h], r14
0x140080050  jmp     loc_14007FF64
0x140080055  mov     rcx, [r14+18h]; BaseAddress
0x140080059  mov     rdx, r14; MemoryDescriptorList
0x14008005c  call    cs:__imp_MmUnmapLockedPages
0x140080063  nop     dword ptr [rax+rax+00h]
0x140080068  jmp     loc_14007FE13
0x14008006d  mov     r9, [rdi+0C8h]
0x140080074  mov     r8d, [rdi+0E8h]
0x14008007b  mov     [rsp+58h+var_38], ebp
0x14008007f  call    Srv2WriteDirectDataAndCompleteWorkItem
0x140080084  jmp     loc_14007FE8B
0x140080089  test    dword ptr [rcx+2Ch], 800000h
0x140080090  jz      loc_14007FFC6
0x140080096  cmp     byte ptr [rcx+29h], 1
0x14008009a  jb      loc_14007FFC6
0x1400800a0  mov     rcx, [rcx+18h]
0x1400800a4  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x1400800ab  mov     edx, 20h ; ' '
0x1400800b0  mov     r9, rbx
0x1400800b3  call    WPP_SF_q
0x1400800b8  jmp     loc_14007FFC6
```
