# PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *,int)

- ea: `0x18000a0f4`
- end: `0x18000a29c`
- name: `?GetProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@H@Z`
- size: `424`
- prototype: `__int64 __usercall@<rax>(PROTOCOL_MANAGER_LIST *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, struct PROTOCOL_MANAGER_ENTRY **@<r9>, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006180`
- `0x180006754`
- `0x180006d24`
- `0x18000ae4c`
- `0x18000ce28`

## callees

- `0x180001a70`
- `0x180002090`
- `0x180009eac`
- `0x180009fc8`
- `0x18000a058`
- `0x18000a0f4`
- `0x18000a2a4`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a155`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a24e`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a280`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a155`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a24e`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a280`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a116`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a116`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a212`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a228`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a239`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a212`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a228`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a239`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a164`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a164`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a1b5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a1d1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a1b5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a1d1`

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
0x18000a0f4  push    rbx
0x18000a0f6  push    rbp
0x18000a0f7  push    rsi
0x18000a0f8  push    rdi
0x18000a0f9  push    r14
0x18000a0fb  push    r15
0x18000a0fd  sub     rsp, 28h
0x18000a101  mov     r15, r9
0x18000a104  mov     [rsp+58h+arg_0], 0
0x18000a10d  mov     rbp, r8
0x18000a110  mov     r14, rdx
0x18000a113  mov     rsi, rcx
0x18000a116  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000a11d  nop     dword ptr [rax+rax+00h]
0x18000a122  lea     r9, [rsp+58h+arg_0]; struct PROTOCOL_MANAGER_ENTRY **
0x18000a127  mov     r8, rbp; unsigned __int16 *
0x18000a12a  mov     rdx, r14; unsigned __int16 *
0x18000a12d  mov     rcx, rsi; this
0x18000a130  call    ?FindProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@AEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@@Z; PROTOCOL_MANAGER_LIST::FindProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *)
0x18000a135  mov     ebx, 80070490h
0x18000a13a  mov     edi, eax
0x18000a13c  cmp     eax, ebx
0x18000a13e  jnz     loc_18000A247
0x18000a144  cmp     [rsp+58h+arg_20], 0
0x18000a14c  jz      loc_18000A27D
0x18000a152  mov     rcx, rsi
0x18000a155  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000a15c  nop     dword ptr [rax+rax+00h]
0x18000a161  mov     rcx, rsi
0x18000a164  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000a16b  nop     dword ptr [rax+rax+00h]
0x18000a170  lea     r9, [rsp+58h+arg_0]; struct PROTOCOL_MANAGER_ENTRY **
0x18000a175  mov     r8, rbp; unsigned __int16 *
0x18000a178  mov     rdx, r14; unsigned __int16 *
0x18000a17b  mov     rcx, rsi; this
0x18000a17e  call    ?FindProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@AEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@@Z; PROTOCOL_MANAGER_LIST::FindProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *)
0x18000a183  cmp     eax, ebx
0x18000a185  jnz     loc_18000A236
0x18000a18b  mov     ecx, 148h; Size
0x18000a190  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a195  test    rax, rax
0x18000a198  jz      loc_18000A220
0x18000a19e  mov     rcx, rax; this
0x18000a1a1  call    ??0PROTOCOL_MANAGER_ENTRY@@QEAA@XZ; PROTOCOL_MANAGER_ENTRY::PROTOCOL_MANAGER_ENTRY(void)
0x18000a1a6  mov     rbx, rax
0x18000a1a9  test    rax, rax
0x18000a1ac  jz      short loc_18000A220
0x18000a1ae  lea     rcx, [rax+10h]
0x18000a1b2  mov     rdx, r14
0x18000a1b5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a1bc  nop     dword ptr [rax+rax+00h]
0x18000a1c1  mov     edi, eax
0x18000a1c3  test    eax, eax
0x18000a1c5  js      short loc_18000A1E3
0x18000a1c7  lea     rcx, [rbx+88h]
0x18000a1ce  mov     rdx, rbp
0x18000a1d1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a1d8  nop     dword ptr [rax+rax+00h]
0x18000a1dd  mov     edi, eax
0x18000a1df  test    eax, eax
0x18000a1e1  jns     short loc_18000A1ED
0x18000a1e3  mov     rcx, rbx; this
0x18000a1e6  call    ??_GPROTOCOL_MANAGER_ENTRY@@QEAAPEAXI@Z; PROTOCOL_MANAGER_ENTRY::`scalar deleting destructor'(uint)
0x18000a1eb  jmp     short loc_18000A225
0x18000a1ed  lea     rax, [rsi+8]
0x18000a1f1  mov     rcx, [rax+8]
0x18000a1f5  cmp     [rcx], rax
0x18000a1f8  jz      short loc_18000A201
0x18000a1fa  mov     ecx, 3
0x18000a1ff  int     29h; Win8: RtlFailFast(ecx)
0x18000a201  mov     [rbx+8], rcx
0x18000a205  mov     [rbx], rax
0x18000a208  mov     [rcx], rbx
0x18000a20b  mov     rcx, rsi
0x18000a20e  mov     [rax+8], rbx
0x18000a212  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000a219  nop     dword ptr [rax+rax+00h]
0x18000a21e  jmp     short loc_18000A25F
0x18000a220  mov     edi, 8007000Eh
0x18000a225  mov     rcx, rsi
0x18000a228  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000a22f  nop     dword ptr [rax+rax+00h]
0x18000a234  jmp     short loc_18000A28C
0x18000a236  mov     rcx, rsi
0x18000a239  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000a240  nop     dword ptr [rax+rax+00h]
0x18000a245  jmp     short loc_18000A25A
0x18000a247  test    eax, eax
0x18000a249  js      short loc_18000A27D
0x18000a24b  mov     rcx, rsi
0x18000a24e  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000a255  nop     dword ptr [rax+rax+00h]
0x18000a25a  mov     rbx, [rsp+58h+arg_0]
0x18000a25f  mov     rcx, rbx; this
0x18000a262  call    ?IsFullyInitialized@PROTOCOL_MANAGER_ENTRY@@QEAAHXZ; PROTOCOL_MANAGER_ENTRY::IsFullyInitialized(void)
0x18000a267  test    eax, eax
0x18000a269  jnz     short loc_18000A276
0x18000a26b  call    ?InitializeInstanceStep2@PROTOCOL_MANAGER_ENTRY@@QEAAJXZ; PROTOCOL_MANAGER_ENTRY::InitializeInstanceStep2(void)
0x18000a270  mov     edi, eax
0x18000a272  test    eax, eax
0x18000a274  js      short loc_18000A28C
0x18000a276  mov     [r15], rbx
0x18000a279  xor     edi, edi
0x18000a27b  jmp     short loc_18000A28C
0x18000a27d  mov     rcx, rsi
0x18000a280  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000a287  nop     dword ptr [rax+rax+00h]
0x18000a28c  mov     eax, edi
0x18000a28e  add     rsp, 28h
0x18000a292  pop     r15
0x18000a294  pop     r14
0x18000a296  pop     rdi
0x18000a297  pop     rsi
0x18000a298  pop     rbp
0x18000a299  pop     rbx
0x18000a29a  retn
```
