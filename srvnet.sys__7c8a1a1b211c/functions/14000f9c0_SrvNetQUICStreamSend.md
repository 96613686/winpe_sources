# SrvNetQUICStreamSend

- ea: `0x14000f9c0`
- end: `0x14000fc11`
- name: `SrvNetQUICStreamSend`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001cb80`

## callees

- `0x1400022d0`
- `0x14000f9c0`
- `0x14001bc5c`
- `0x14001e3c4`
- `0x14001e428`
- `0x14002a4c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000fa76`
- `ntoskrnl!ExAllocatePool2` at `0x14000fa76`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000fae2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000fae2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fbce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fbce`

## pseudocode

```c
__int64 __fastcall SrvNetQUICStreamSend(__int64 a1, unsigned int *a2, __int64 a3)
{
  unsigned int v4; // r15d
  unsigned __int64 v5; // rbx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 **v9; // rsi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  __int64 v12; // rdx
  _QWORD *Pool2; // rsi
  __int64 v14; // r8
  int v15; // ebx
  _QWORD *v16; // r14
  __int64 v17; // r12
  struct _MDL *v18; // rbx
  unsigned __int64 v19; // rbp
  PVOID MappedSystemVa; // rax
  unsigned __int64 ByteCount; // rcx
  __int64 result; // rax

  v4 = 0;
  v5 = *a2 + 4LL;
  *(_QWORD *)(*((_QWORD *)a2 + 1) + 24LL) -= 4LL;
  *(_DWORD *)(*((_QWORD *)a2 + 1) + 44LL) -= 4;
  *(_DWORD *)(*((_QWORD *)a2 + 1) + 40LL) += 4;
  v7 = *((_QWORD *)a2 + 1);
  v8 = _byteswap_ulong(*a2);
  **(_DWORD **)(v7 + 24) = v8;
  v9 = (__int64 **)*((_QWORD *)a2 + 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Pq(WPP_GLOBAL_Control->AttachedDevice, v8, a3, v5, a1);
  }
  while ( v9 && v5 )
  {
    v10 = *((unsigned int *)v9 + 10);
    ++v4;
    v9 = (__int64 **)*v9;
    v11 = v5;
    if ( v5 >= v10 )
      v11 = v10;
    v5 -= v11;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(66, 16LL * v4 + 8, 1717719884);
  if ( Pool2 )
  {
    v16 = Pool2 + 1;
    *Pool2 = *((_QWORD *)a2 + 3);
    v17 = 0;
    v18 = (struct _MDL *)*((_QWORD *)a2 + 1);
    v19 = *a2 + 4LL;
    *((_QWORD *)a2 + 3) = Pool2;
    while ( v18 && v19 )
    {
      if ( (v18->MdlFlags & 5) != 0 )
        MappedSystemVa = v18->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v18, 0, MmCached, 0, 0, 0x40000010u);
      if ( !MappedSystemVa )
      {
        v15 = -1073741670;
LABEL_32:
        *((_QWORD *)a2 + 3) = *Pool2;
        ExFreePoolWithTag(Pool2, 0x6662534Cu);
        goto LABEL_33;
      }
      v16[1] = MappedSystemVa;
      ByteCount = v19;
      if ( v19 >= v18->ByteCount )
        ByteCount = v18->ByteCount;
      *(_DWORD *)v16 = ByteCount;
      v19 -= ByteCount;
      v18 = v18->Next;
      v17 += ByteCount;
      v16 += 2;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_PPq(WPP_GLOBAL_Control->AttachedDevice, v12, v14, v4, v17, a1);
    }
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD, _QWORD, unsigned int *))(MsQuic + 200))(
               *(_QWORD *)(a1 + 400),
               Pool2 + 1,
               v4,
               0,
               a2);
    v15 = result;
    if ( (int)result < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          29,
          WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids,
          (unsigned int)result,
          a1);
      }
      goto LABEL_32;
    }
  }
  else
  {
    v15 = -1073741670;
LABEL_33:
    *(_QWORD *)(*((_QWORD *)a2 + 1) + 24LL) += 4LL;
    *(_DWORD *)(*((_QWORD *)a2 + 1) + 44LL) += 4;
    *(_DWORD *)(*((_QWORD *)a2 + 1) + 40LL) -= 4;
    return SrvNetCompleteSendData(v15, 0, (__int64)a2);
  }
  return result;
}

```

## disassembly

```asm
0x14000f9c0  push    rbx
0x14000f9c2  push    rbp
0x14000f9c3  push    rsi
0x14000f9c4  push    rdi
0x14000f9c5  push    r12
0x14000f9c7  push    r13
0x14000f9c9  push    r14
0x14000f9cb  push    r15
0x14000f9cd  sub     rsp, 38h
0x14000f9d1  mov     rax, [rdx+8]
0x14000f9d5  mov     rdi, rdx
0x14000f9d8  mov     ebx, [rdx]
0x14000f9da  xor     r15d, r15d
0x14000f9dd  add     rbx, 4
0x14000f9e1  mov     r13, rcx
0x14000f9e4  add     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFCh
0x14000f9e9  mov     rax, [rdx+8]
0x14000f9ed  add     dword ptr [rax+2Ch], 0FFFFFFFCh
0x14000f9f1  mov     rax, [rdx+8]
0x14000f9f5  add     dword ptr [rax+28h], 4
0x14000f9f9  mov     rax, [rdi+8]
0x14000f9fd  mov     edx, [rdx]
0x14000f9ff  bswap   edx
0x14000fa01  mov     rcx, [rax+18h]
0x14000fa05  mov     [rcx], edx
0x14000fa07  mov     rsi, [rdi+8]
0x14000fa0b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000fa12  lea     rax, WPP_GLOBAL_Control
0x14000fa19  cmp     rcx, rax
0x14000fa1c  jz      short loc_14000FA5B
0x14000fa1e  test    dword ptr [rcx+2Ch], 200000h
0x14000fa25  jz      short loc_14000FA5B
0x14000fa27  cmp     byte ptr [rcx+29h], 2
0x14000fa2b  jb      short loc_14000FA5B
0x14000fa2d  mov     rcx, [rcx+18h]
0x14000fa31  mov     r9, rbx
0x14000fa34  mov     qword ptr [rsp+78h+BugCheckOnFailure], r13
0x14000fa39  call    WPP_SF_Pq
0x14000fa3e  jmp     short loc_14000FA5B
0x14000fa40  test    rbx, rbx
0x14000fa43  jz      short loc_14000FA60
0x14000fa45  mov     ecx, [rsi+28h]
0x14000fa48  inc     r15d
0x14000fa4b  mov     rsi, [rsi]
0x14000fa4e  cmp     rbx, rcx
0x14000fa51  mov     rax, rbx
0x14000fa54  cmovnb  rax, rcx
0x14000fa58  sub     rbx, rax
0x14000fa5b  test    rsi, rsi
0x14000fa5e  jnz     short loc_14000FA40
0x14000fa60  mov     edx, r15d
0x14000fa63  mov     ecx, 42h ; 'B'
0x14000fa68  shl     rdx, 4
0x14000fa6c  mov     r8d, 6662534Ch
0x14000fa72  add     rdx, 8
0x14000fa76  call    cs:__imp_ExAllocatePool2
0x14000fa7d  nop     dword ptr [rax+rax+00h]
0x14000fa82  mov     rsi, rax
0x14000fa85  test    rax, rax
0x14000fa88  jnz     short loc_14000FA94
0x14000fa8a  mov     ebx, 0C000009Ah
0x14000fa8f  jmp     loc_14000FBDA
0x14000fa94  mov     rax, [rdi+18h]
0x14000fa98  lea     r14, [rsi+8]
0x14000fa9c  mov     [rsi], rax
0x14000fa9f  xor     r12d, r12d
0x14000faa2  mov     ebp, [rdi]
0x14000faa4  mov     rbx, [rdi+8]
0x14000faa8  add     rbp, 4
0x14000faac  mov     [rdi+18h], rsi
0x14000fab0  test    rbx, rbx
0x14000fab3  jz      short loc_14000FB20
0x14000fab5  test    rbp, rbp
0x14000fab8  jz      short loc_14000FB20
0x14000faba  test    byte ptr [rbx+0Ah], 5
0x14000fabe  jz      short loc_14000FAC6
0x14000fac0  mov     rax, [rbx+18h]
0x14000fac4  jmp     short loc_14000FAEE
0x14000fac6  xor     r9d, r9d; RequestedAddress
0x14000fac9  mov     [rsp+78h+Priority], 40000010h; Priority
0x14000fad1  xor     edx, edx; AccessMode
0x14000fad3  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000fadb  mov     rcx, rbx; MemoryDescriptorList
0x14000fade  lea     r8d, [r9+1]; CacheType
0x14000fae2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000fae9  nop     dword ptr [rax+rax+00h]
0x14000faee  test    rax, rax
0x14000faf1  jz      short loc_14000FB16
0x14000faf3  mov     [r14+8], rax
0x14000faf7  mov     rcx, rbp
0x14000fafa  mov     eax, [rbx+28h]
0x14000fafd  cmp     rbp, rax
0x14000fb00  cmovnb  rcx, rax
0x14000fb04  mov     [r14], ecx
0x14000fb07  sub     rbp, rcx
0x14000fb0a  mov     rbx, [rbx]
0x14000fb0d  add     r12, rcx
0x14000fb10  add     r14, 10h
0x14000fb14  jmp     short loc_14000FAB0
0x14000fb16  mov     ebx, 0C000009Ah
0x14000fb1b  jmp     loc_14000FBBF
0x14000fb20  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000fb27  lea     rbp, WPP_GLOBAL_Control
0x14000fb2e  cmp     rcx, rbp
0x14000fb31  jz      short loc_14000FB58
0x14000fb33  test    dword ptr [rcx+2Ch], 200000h
0x14000fb3a  jz      short loc_14000FB58
0x14000fb3c  cmp     byte ptr [rcx+29h], 2
0x14000fb40  jb      short loc_14000FB58
0x14000fb42  mov     rcx, [rcx+18h]
0x14000fb46  mov     qword ptr [rsp+78h+Priority], r13
0x14000fb4b  mov     r9d, r15d
0x14000fb4e  mov     qword ptr [rsp+78h+BugCheckOnFailure], r12
0x14000fb53  call    WPP_SF_PPq
0x14000fb58  mov     rax, cs:MsQuic
0x14000fb5f  lea     rdx, [rsi+8]
0x14000fb63  mov     rcx, [r13+190h]
0x14000fb6a  xor     r9d, r9d
0x14000fb6d  mov     r8d, r15d
0x14000fb70  mov     qword ptr [rsp+78h+BugCheckOnFailure], rdi
0x14000fb75  mov     rax, [rax+0C8h]
0x14000fb7c  call    _guard_dispatch_icall
0x14000fb81  mov     ebx, eax
0x14000fb83  test    eax, eax
0x14000fb85  jns     short loc_14000FBFF
0x14000fb87  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000fb8e  cmp     rcx, rbp
0x14000fb91  jz      short loc_14000FBBF
0x14000fb93  test    dword ptr [rcx+2Ch], 200000h
0x14000fb9a  jz      short loc_14000FBBF
0x14000fb9c  cmp     byte ptr [rcx+29h], 1
0x14000fba0  jb      short loc_14000FBBF
0x14000fba2  mov     rcx, [rcx+18h]
0x14000fba6  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x14000fbad  mov     edx, 1Dh
0x14000fbb2  mov     qword ptr [rsp+78h+BugCheckOnFailure], r13
0x14000fbb7  mov     r9d, eax
0x14000fbba  call    WPP_SF_dq
0x14000fbbf  mov     rax, [rsi]
0x14000fbc2  mov     edx, 6662534Ch; Tag
0x14000fbc7  mov     rcx, rsi; P
0x14000fbca  mov     [rdi+18h], rax
0x14000fbce  call    cs:__imp_ExFreePoolWithTag
0x14000fbd5  nop     dword ptr [rax+rax+00h]
0x14000fbda  mov     rax, [rdi+8]
0x14000fbde  mov     r8, rdi
0x14000fbe1  xor     edx, edx
0x14000fbe3  mov     ecx, ebx
0x14000fbe5  add     qword ptr [rax+18h], 4
0x14000fbea  mov     rax, [rdi+8]
0x14000fbee  add     dword ptr [rax+2Ch], 4
0x14000fbf2  mov     rax, [rdi+8]
0x14000fbf6  add     dword ptr [rax+28h], 0FFFFFFFCh
0x14000fbfa  call    SrvNetCompleteSendData
0x14000fbff  add     rsp, 38h
0x14000fc03  pop     r15
0x14000fc05  pop     r14
0x14000fc07  pop     r13
0x14000fc09  pop     r12
0x14000fc0b  pop     rdi
0x14000fc0c  pop     rsi
0x14000fc0d  pop     rbp
0x14000fc0e  pop     rbx
0x14000fc0f  retn
```
