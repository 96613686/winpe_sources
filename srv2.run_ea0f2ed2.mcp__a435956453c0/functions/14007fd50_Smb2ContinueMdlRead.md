# Smb2ContinueMdlRead

- ea: `0x14007fd50`
- end: `0x14008010d`
- name: `Smb2ContinueMdlRead`
- size: `957`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14007f510`

## callees

- `0x140004560`
- `0x140007400`
- `0x140007900`
- `0x140008190`
- `0x14000a034`
- `0x1400222ec`
- `0x140038980`
- `0x14007fd50`
- `0x140080114`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x14007fe6f`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007fe6f`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400800ac`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400800ac`
- `srvnet!SrvNetIsRdmaConnection` at `0x14007ff8f`
- `srvnet!SrvNetIsRdmaConnection` at `0x14007ff8f`

## string_xrefs

- `0x14008001c`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`

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
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1);
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
0x14007fd50  push    rbx
0x14007fd52  push    rbp
0x14007fd53  push    rsi
0x14007fd54  push    rdi
0x14007fd55  push    r14
0x14007fd57  sub     rsp, 30h
0x14007fd5b  mov     rax, [rcx+138h]
0x14007fd62  mov     rbx, rcx
0x14007fd65  mov     rdi, [rcx+230h]
0x14007fd6c  xor     ebp, ebp
0x14007fd6e  mov     rsi, [rax+18h]
0x14007fd72  mov     rax, [rcx+78h]
0x14007fd76  mov     rcx, [rax+8]
0x14007fd7a  or      byte ptr [rdi+108h], 1
0x14007fd81  movzx   edx, byte ptr [rdi+108h]
0x14007fd88  mov     [rdi+0C8h], rcx
0x14007fd8f  mov     rax, [rbx+78h]
0x14007fd93  mov     r14d, [rax+30h]
0x14007fd97  test    r14d, r14d
0x14007fd9a  js      loc_14007FEE7
0x14007fda0  test    rcx, rcx
0x14007fda3  jz      short loc_14007FDB0
0x14007fda5  add     ebp, [rcx+28h]
0x14007fda8  mov     rcx, [rcx]
0x14007fdab  test    rcx, rcx
0x14007fdae  jnz     short loc_14007FDA5
0x14007fdb0  mov     [rdi+0ECh], ebp
0x14007fdb6  mov     rcx, rbx
0x14007fdb9  call    Smb2SequentialReadComplete
0x14007fdbe  cmp     ebp, [rdi+0F0h]
0x14007fdc4  jb      loc_14007FFFF
0x14007fdca  test    ebp, ebp
0x14007fdcc  jz      loc_14008004F
0x14007fdd2  mov     rdx, [rdi+0D8h]
0x14007fdd9  xor     eax, eax
0x14007fddb  mov     [rsp+58h+arg_0], r12
0x14007fde0  test    rdx, rdx
0x14007fde3  mov     [rsp+58h+arg_8], r13
0x14007fde8  mov     ecx, ebp
0x14007fdea  cmovnz  ecx, eax
0x14007fded  mov     [rsp+58h+arg_10], r15
0x14007fdf2  cmovnz  eax, ebp
0x14007fdf5  mov     [rsi+44h], ecx
0x14007fdf8  mov     [rsi+48h], eax
0x14007fdfb  cmp     cs:byte_140058150, 0
0x14007fe02  jnz     loc_14007FF11
0x14007fe08  movzx   eax, byte ptr [rdi+109h]
0x14007fe0f  mov     ecx, 50h ; 'P'
0x14007fe14  cmp     al, cl
0x14007fe16  mov     byte ptr [rsi+43h], 0
0x14007fe1a  mov     dword ptr [rsi+4Ch], 0
0x14007fe21  cmova   ecx, eax
0x14007fe24  mov     word ptr [rsi+40h], 11h
0x14007fe2a  movzx   r8d, cl
0x14007fe2e  xor     edx, edx; Val
0x14007fe30  mov     [rsi+42h], cl
0x14007fe33  sub     r8, 50h ; 'P'; Size
0x14007fe37  lea     rcx, [rsi+50h]; void *
0x14007fe3b  call    memset
0x14007fe40  mov     rax, [rbx+138h]
0x14007fe47  movzx   r15d, byte ptr [rsi+42h]
0x14007fe4c  mov     r14, [rax+50h]
0x14007fe50  mov     r12, [rax+18h]
0x14007fe54  mov     r13, [rax+38h]
0x14007fe58  test    byte ptr [r14+0Ah], 20h
0x14007fe5d  jnz     loc_1400800A5
0x14007fe63  mov     r9d, r15d; Length
0x14007fe66  mov     r8, r12; VirtualAddress
0x14007fe69  mov     rdx, r14; TargetMdl
0x14007fe6c  mov     rcx, r13; SourceMdl
0x14007fe6f  call    cs:__imp_IoBuildPartialMdl
0x14007fe76  nop     dword ptr [rax+rax+00h]
0x14007fe7b  mov     rax, [rbx+138h]
0x14007fe82  xor     edx, edx
0x14007fe84  mov     rcx, [rax+50h]
0x14007fe88  mov     rax, [rdi+0C8h]
0x14007fe8f  mov     [rcx], rax
0x14007fe92  mov     rcx, rbx
0x14007fe95  or      dword ptr [rbx+1E4h], 4
0x14007fe9c  call    Smb2SetSuccess
0x14007fea1  movzx   ecx, byte ptr [rsi+42h]
0x14007fea5  add     ecx, [rsi+44h]
0x14007fea8  mov     rax, [rbx+138h]
0x14007feaf  mov     r15, [rsp+58h+arg_10]
0x14007feb4  mov     r13, [rsp+58h+arg_8]
0x14007feb9  mov     r12, [rsp+58h+arg_0]
0x14007febe  mov     [rax+24h], ecx
0x14007fec1  mov     rcx, rbx
0x14007fec4  mov     rdx, [rdi+0D8h]
0x14007fecb  test    rdx, rdx
0x14007fece  jnz     loc_1400800BD
0x14007fed4  xor     edx, edx
0x14007fed6  call    Srv2CompleteWorkItem
0x14007fedb  add     rsp, 30h
0x14007fedf  pop     r14
0x14007fee1  pop     rdi
0x14007fee2  pop     rsi
0x14007fee3  pop     rbp
0x14007fee4  pop     rbx
0x14007fee5  retn
0x14007fee7  cmp     r14d, 0C0000011h
0x14007feee  jz      loc_140080038
0x14007fef4  and     dl, 0FEh
0x14007fef7  mov     rcx, rbx
0x14007fefa  mov     [rdi+108h], dl
0x14007ff00  call    Smb2RestartNonMdlRead
0x14007ff05  add     rsp, 30h
0x14007ff09  pop     r14
0x14007ff0b  pop     rdi
0x14007ff0c  pop     rsi
0x14007ff0d  pop     rbp
0x14007ff0e  pop     rbx
0x14007ff0f  retn
0x14007ff11  mov     rax, [rdi+38h]
0x14007ff15  mov     rcx, [rax+68h]
0x14007ff19  lock inc dword ptr [rcx+190h]
0x14007ff20  mov     rax, [rdi+28h]
0x14007ff24  lock inc dword ptr [rax+0F0h]
0x14007ff2b  mov     rax, [rdi+38h]
0x14007ff2f  mov     r14d, ebp
0x14007ff32  mov     rcx, [rax+68h]
0x14007ff36  lock add [rcx+1A0h], r14
0x14007ff3e  mov     rax, [rdi+28h]
0x14007ff42  lock add [rax+100h], r14
0x14007ff4a  mov     rax, [rdi+38h]
0x14007ff4e  mov     rcx, [rax+68h]
0x14007ff52  lock add [rcx+240h], r14
0x14007ff5a  mov     rax, [rdi+28h]
0x14007ff5e  lock add [rax+178h], r14
0x14007ff66  mov     rax, [rdi+38h]
0x14007ff6a  mov     rcx, [rax+68h]
0x14007ff6e  lock inc dword ptr [rcx+238h]
0x14007ff75  mov     rax, [rdi+28h]
0x14007ff79  lock inc dword ptr [rax+170h]
0x14007ff80  mov     rax, [rdi+18h]
0x14007ff84  mov     rcx, [rax+60h]
0x14007ff88  mov     rcx, [rcx+1E0h]
0x14007ff8f  call    cs:__imp_SrvNetIsRdmaConnection
0x14007ff96  nop     dword ptr [rax+rax+00h]
0x14007ff9b  test    al, al
0x14007ff9d  jnz     loc_14008005D
0x14007ffa3  mov     rax, [rdi+48h]
0x14007ffa7  cmp     byte ptr [rax+0F5h], 0
0x14007ffae  jnz     loc_140080081
0x14007ffb4  cmp     qword ptr [rdi+0D8h], 0
0x14007ffbc  jz      loc_14007FE08
0x14007ffc2  mov     rax, [rdi+38h]
0x14007ffc6  mov     rcx, [rax+68h]
0x14007ffca  lock add [rcx+148h], r14
0x14007ffd2  mov     rax, [rdi+28h]
0x14007ffd6  lock add [rax+0B0h], r14
0x14007ffde  mov     rax, [rdi+38h]
0x14007ffe2  mov     rcx, [rax+68h]
0x14007ffe6  lock add [rcx+140h], r14
0x14007ffee  mov     rax, [rdi+28h]
0x14007fff2  lock add [rax+0A8h], r14
0x14007fffa  jmp     loc_14007FE08
0x14007ffff  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140080006  lea     rax, WPP_GLOBAL_Control
0x14008000d  cmp     rcx, rax
0x140080010  jnz     loc_1400800D9
0x140080016  mov     r9d, 73Dh
0x14008001c  lea     r8, aOnecoreBaseFsR_9; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140080023  mov     edx, 0C0000011h
0x140080028  mov     rcx, rbx
0x14008002b  call    _Smb2SetError
0x140080030  mov     rcx, rbx
0x140080033  jmp     loc_14007FED4
0x140080038  test    rcx, rcx
0x14008003b  jnz     loc_14007FDB6
0x140080041  and     dl, 0FEh
0x140080044  mov     [rdi+108h], dl
0x14008004a  jmp     loc_14007FDB6
0x14008004f  cmp     r14d, 0C0000011h
0x140080056  jz      short loc_14007FFFF
0x140080058  jmp     loc_14007FDD2
0x14008005d  mov     rax, [rdi+38h]
0x140080061  mov     rcx, [rax+68h]
0x140080065  lock inc dword ptr [rcx+194h]
0x14008006c  mov     rax, [rdi+38h]
0x140080070  mov     rcx, [rax+68h]
0x140080074  lock add [rcx+1A8h], r14
0x14008007c  jmp     loc_14007FFA3
0x140080081  mov     rax, [rdi+38h]
0x140080085  mov     rcx, [rax+68h]
0x140080089  lock inc dword ptr [rcx+21Ch]
0x140080090  mov     rax, [rdi+38h]
0x140080094  mov     rcx, [rax+68h]
0x140080098  lock add [rcx+228h], r14
0x1400800a0  jmp     loc_14007FFB4
0x1400800a5  mov     rcx, [r14+18h]; BaseAddress
0x1400800a9  mov     rdx, r14; MemoryDescriptorList
0x1400800ac  call    cs:__imp_MmUnmapLockedPages
0x1400800b3  nop     dword ptr [rax+rax+00h]
0x1400800b8  jmp     loc_14007FE63
0x1400800bd  mov     r9, [rdi+0C8h]
0x1400800c4  mov     r8d, [rdi+0E8h]
0x1400800cb  mov     [rsp+58h+var_38], ebp
0x1400800cf  call    Srv2WriteDirectDataAndCompleteWorkItem
0x1400800d4  jmp     loc_14007FEDB
0x1400800d9  test    dword ptr [rcx+2Ch], 800000h
0x1400800e0  jz      loc_140080016
0x1400800e6  cmp     byte ptr [rcx+29h], 1
0x1400800ea  jb      loc_140080016
0x1400800f0  mov     rcx, [rcx+18h]
0x1400800f4  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x1400800fb  mov     edx, 20h ; ' '
0x140080100  mov     r9, rbx
0x140080103  call    WPP_SF_q
0x140080108  jmp     loc_140080016
```
