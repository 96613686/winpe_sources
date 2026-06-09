# PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *,int)

- ea: `0x180009630`
- end: `0x180009797`
- name: `?GetProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@H@Z`
- size: `359`
- prototype: `__int64 __fastcall(PROTOCOL_MANAGER_LIST ***this, const unsigned __int16 *, const unsigned __int16 *, struct PROTOCOL_MANAGER_ENTRY **, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005c10`
- `0x180006144`
- `0x1800066c4`
- `0x18000a22c`
- `0x18000bf58`

## callees

- `0x1800019e0`
- `0x180001f68`
- `0x180009428`
- `0x180009520`
- `0x1800095a8`
- `0x180009630`
- `0x1800097a0`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000968b`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009756`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009782`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000968b`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009756`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009782`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009652`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009652`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000972c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000973c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009747`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000972c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000973c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009747`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009694`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009694`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800096db`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800096f1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800096db`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800096f1`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(
        PROTOCOL_MANAGER_LIST ***this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct PROTOCOL_MANAGER_ENTRY **a4,
        int a5)
{
  int ProtocolManagerEntry; // eax
  int v10; // edi
  PROTOCOL_MANAGER_ENTRY *v11; // rax
  PROTOCOL_MANAGER_ENTRY *v12; // rax
  struct PROTOCOL_MANAGER_ENTRY *v13; // rbx
  unsigned int v14; // edx
  PROTOCOL_MANAGER_LIST **v15; // rcx
  PROTOCOL_MANAGER_ENTRY *v16; // rcx
  struct PROTOCOL_MANAGER_ENTRY *v18; // [rsp+60h] [rbp+8h] BYREF

  v18 = 0;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)this);
  ProtocolManagerEntry = PROTOCOL_MANAGER_LIST::FindProtocolManagerEntry((PROTOCOL_MANAGER_LIST *)this, a2, a3, &v18);
  v10 = ProtocolManagerEntry;
  if ( ProtocolManagerEntry != -2147023728 )
  {
    if ( ProtocolManagerEntry >= 0 )
    {
      CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)this);
      goto LABEL_17;
    }
LABEL_21:
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)this);
    return (unsigned int)v10;
  }
  if ( !a5 )
    goto LABEL_21;
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)this);
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)this);
  if ( PROTOCOL_MANAGER_LIST::FindProtocolManagerEntry((PROTOCOL_MANAGER_LIST *)this, a2, a3, &v18) != -2147023728 )
  {
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)this);
LABEL_17:
    v13 = v18;
    goto LABEL_18;
  }
  v11 = (PROTOCOL_MANAGER_ENTRY *)operator new(0x148u);
  if ( !v11 || (v12 = PROTOCOL_MANAGER_ENTRY::PROTOCOL_MANAGER_ENTRY(v11), (v13 = v12) == 0) )
  {
    v10 = -2147024882;
    goto LABEL_13;
  }
  v10 = STRU::Copy((PROTOCOL_MANAGER_ENTRY *)((char *)v12 + 16), a2);
  if ( v10 < 0 || (v10 = STRU::Copy((struct PROTOCOL_MANAGER_ENTRY *)((char *)v13 + 136), a3), v10 < 0) )
  {
    PROTOCOL_MANAGER_ENTRY::`scalar deleting destructor'(v13, v14);
LABEL_13:
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)this);
    return (unsigned int)v10;
  }
  v15 = this[2];
  if ( *v15 != (PROTOCOL_MANAGER_LIST *)(this + 1) )
    __fastfail(3u);
  *((_QWORD *)v13 + 1) = v15;
  *(_QWORD *)v13 = this + 1;
  *v15 = v13;
  this[2] = (PROTOCOL_MANAGER_LIST **)v13;
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)this);
LABEL_18:
  if ( (unsigned int)PROTOCOL_MANAGER_ENTRY::IsFullyInitialized(v13)
    || (v10 = PROTOCOL_MANAGER_ENTRY::InitializeInstanceStep2(v16), v10 >= 0) )
  {
    *a4 = v13;
    return 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180009630  push    rbx
0x180009632  push    rbp
0x180009633  push    rsi
0x180009634  push    rdi
0x180009635  push    r14
0x180009637  push    r15
0x180009639  sub     rsp, 28h
0x18000963d  mov     r15, r9
0x180009640  mov     [rsp+58h+arg_0], 0
0x180009649  mov     rbp, r8
0x18000964c  mov     r14, rdx
0x18000964f  mov     rsi, rcx
0x180009652  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180009658  lea     r9, [rsp+58h+arg_0]; struct PROTOCOL_MANAGER_ENTRY **
0x18000965d  mov     r8, rbp; unsigned __int16 *
0x180009660  mov     rdx, r14; unsigned __int16 *
0x180009663  mov     rcx, rsi; this
0x180009666  call    ?FindProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@AEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@@Z; PROTOCOL_MANAGER_LIST::FindProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *)
0x18000966b  mov     ebx, 80070490h
0x180009670  mov     edi, eax
0x180009672  cmp     eax, ebx
0x180009674  jnz     loc_18000974F
0x18000967a  cmp     [rsp+58h+arg_20], 0
0x180009682  jz      loc_18000977F
0x180009688  mov     rcx, rsi
0x18000968b  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180009691  mov     rcx, rsi
0x180009694  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000969a  lea     r9, [rsp+58h+arg_0]; struct PROTOCOL_MANAGER_ENTRY **
0x18000969f  mov     r8, rbp; unsigned __int16 *
0x1800096a2  mov     rdx, r14; unsigned __int16 *
0x1800096a5  mov     rcx, rsi; this
0x1800096a8  call    ?FindProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@AEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@@Z; PROTOCOL_MANAGER_LIST::FindProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *)
0x1800096ad  cmp     eax, ebx
0x1800096af  jnz     loc_180009744
0x1800096b5  mov     ecx, 148h; Size
0x1800096ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800096bf  test    rax, rax
0x1800096c2  jz      short loc_180009734
0x1800096c4  mov     rcx, rax; this
0x1800096c7  call    ??0PROTOCOL_MANAGER_ENTRY@@QEAA@XZ; PROTOCOL_MANAGER_ENTRY::PROTOCOL_MANAGER_ENTRY(void)
0x1800096cc  mov     rbx, rax
0x1800096cf  test    rax, rax
0x1800096d2  jz      short loc_180009734
0x1800096d4  lea     rcx, [rax+10h]
0x1800096d8  mov     rdx, r14
0x1800096db  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800096e1  mov     edi, eax
0x1800096e3  test    eax, eax
0x1800096e5  js      short loc_1800096FD
0x1800096e7  lea     rcx, [rbx+88h]
0x1800096ee  mov     rdx, rbp
0x1800096f1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800096f7  mov     edi, eax
0x1800096f9  test    eax, eax
0x1800096fb  jns     short loc_180009707
0x1800096fd  mov     rcx, rbx; this
0x180009700  call    ??_GPROTOCOL_MANAGER_ENTRY@@QEAAPEAXI@Z; PROTOCOL_MANAGER_ENTRY::`scalar deleting destructor'(uint)
0x180009705  jmp     short loc_180009739
0x180009707  lea     rax, [rsi+8]
0x18000970b  mov     rcx, [rax+8]
0x18000970f  cmp     [rcx], rax
0x180009712  jz      short loc_18000971B
0x180009714  mov     ecx, 3
0x180009719  int     29h; Win8: RtlFailFast(ecx)
0x18000971b  mov     [rbx+8], rcx
0x18000971f  mov     [rbx], rax
0x180009722  mov     [rcx], rbx
0x180009725  mov     rcx, rsi
0x180009728  mov     [rax+8], rbx
0x18000972c  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180009732  jmp     short loc_180009761
0x180009734  mov     edi, 8007000Eh
0x180009739  mov     rcx, rsi
0x18000973c  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180009742  jmp     short loc_180009788
0x180009744  mov     rcx, rsi
0x180009747  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000974d  jmp     short loc_18000975C
0x18000974f  test    eax, eax
0x180009751  js      short loc_18000977F
0x180009753  mov     rcx, rsi
0x180009756  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000975c  mov     rbx, [rsp+58h+arg_0]
0x180009761  mov     rcx, rbx; this
0x180009764  call    ?IsFullyInitialized@PROTOCOL_MANAGER_ENTRY@@QEAAHXZ; PROTOCOL_MANAGER_ENTRY::IsFullyInitialized(void)
0x180009769  test    eax, eax
0x18000976b  jnz     short loc_180009778
0x18000976d  call    ?InitializeInstanceStep2@PROTOCOL_MANAGER_ENTRY@@QEAAJXZ; PROTOCOL_MANAGER_ENTRY::InitializeInstanceStep2(void)
0x180009772  mov     edi, eax
0x180009774  test    eax, eax
0x180009776  js      short loc_180009788
0x180009778  mov     [r15], rbx
0x18000977b  xor     edi, edi
0x18000977d  jmp     short loc_180009788
0x18000977f  mov     rcx, rsi
0x180009782  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180009788  mov     eax, edi
0x18000978a  add     rsp, 28h
0x18000978e  pop     r15
0x180009790  pop     r14
0x180009792  pop     rdi
0x180009793  pop     rsi
0x180009794  pop     rbp
0x180009795  pop     rbx
0x180009796  retn
```
