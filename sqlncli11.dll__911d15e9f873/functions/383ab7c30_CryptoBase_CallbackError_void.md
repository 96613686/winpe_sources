# CryptoBase::CallbackError(void)

- ea: `0x383ab7c30`
- end: `0x383ab7e1d`
- name: `?CallbackError@CryptoBase@@IEAAXXZ`
- size: `493`
- prototype: `void __fastcall(CryptoBase *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x3838802e0`
- `0x383880460`
- `0x383abbf20`
- `0x383abf5c0`
- `0x383abf730`

## callees

- `0x383842d70`
- `0x383882650`
- `0x38391ac00`
- `0x38391ac40`
- `0x38391af20`
- `0x383ab7c30`
- `0x383ac4be0`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x383ab7cf0`
- `KERNEL32!PostQueuedCompletionStatus` at `0x383ab7d8f`
- `KERNEL32!PostQueuedCompletionStatus` at `0x383ab7cf0`
- `KERNEL32!PostQueuedCompletionStatus` at `0x383ab7d8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CryptoBase::CallbackError(struct SNI_Packet **this)
{
  _BYTE *v2; // rax
  int v3; // ecx
  struct SNI_Packet *v4; // rcx
  struct _OVERLAPPED *v5; // rax
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF

  v6 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48A60[0] )
    bidScopeEnterA(&v6, off_383B48A60[0], *((unsigned int *)this + 11));
  CryptoBase::FreeReadWriteBuffers((CryptoBase *)this);
  while ( this[35] )
  {
    v2 = DynamicQueue::DeQueue((DynamicQueue *)(this + 35));
    v2[144] = *((_BYTE *)this + 24);
    *((_DWORD *)v2 + 26) -= *((_DWORD *)this + 17);
    v3 = *((_DWORD *)this + 18) + *((_DWORD *)this + 20) + *((_DWORD *)this + 19);
    *((_DWORD *)v2 + 39) = v3;
    *((_WORD *)v2 + 86) = 257;
    *((_DWORD *)v2 + 24) += v3 + *((_DWORD *)this + 17);
    if ( !PostQueuedCompletionStatus(ghIoCompletionPort, 0, 0, (LPOVERLAPPED)v2)
      && (bidGblFlags & 2) != 0
      && off_383B47780[0]
      && bidID != -1 )
    {
      off_383B15038();
    }
  }
  v4 = this[7];
  if ( v4 )
  {
    SNIPacketRelease(v4);
    this[7] = 0;
  }
  if ( this[32] )
  {
    v5 = (struct _OVERLAPPED *)DynamicQueue::DeQueue((DynamicQueue *)(this + 32));
    LOBYTE(v5[4].Offset) = *((_BYTE *)this + 24);
    *((_BYTE *)this + 249) = 1;
    if ( !PostQueuedCompletionStatus(ghIoCompletionPort, 0, 0, v5)
      && (bidGblFlags & 2) != 0
      && off_383B47778[0]
      && bidID != -1 )
    {
      off_383B15038();
    }
  }
  if ( v6 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
}

```

## disassembly

```asm
0x383ab7c30  push    rdi
0x383ab7c32  sub     rsp, 40h
0x383ab7c36  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x383ab7c3f  mov     [rsp+48h+arg_8], rbx
0x383ab7c44  mov     [rsp+48h+arg_10], rsi
0x383ab7c49  mov     rbx, rcx
0x383ab7c4c  mov     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383ab7c55  mov     eax, cs:_bidGblFlags
0x383ab7c5b  and     eax, 20004h
0x383ab7c60  cmp     eax, 20004h
0x383ab7c65  jnz     short loc_383AB7C88
0x383ab7c67  mov     rax, cs:off_383B48A60; "<CryptoBase::CallbackError|API|SNI> %u#"...
0x383ab7c6e  test    rax, rax
0x383ab7c71  jz      short loc_383AB7C88
0x383ab7c73  mov     r8d, [rcx+2Ch]
0x383ab7c77  mov     rdx, cs:off_383B48A60; "<CryptoBase::CallbackError|API|SNI> %u#"...
0x383ab7c7e  lea     rcx, [rsp+48h+arg_0]
0x383ab7c83  call    _bidScopeEnterA
0x383ab7c88  mov     rcx, rbx; this
0x383ab7c8b  call    ?FreeReadWriteBuffers@CryptoBase@@IEAAXXZ; CryptoBase::FreeReadWriteBuffers(void)
0x383ab7c90  xor     esi, esi
0x383ab7c92  cmp     [rbx+118h], rsi
0x383ab7c99  jz      loc_383AB7D4C
0x383ab7c9f  nop
0x383ab7ca0  lea     rcx, [rbx+118h]; this
0x383ab7ca7  call    ?DeQueue@DynamicQueue@@QEAAPEAXXZ; DynamicQueue::DeQueue(void)
0x383ab7cac  mov     r9, rax; lpOverlapped
0x383ab7caf  movzx   ecx, byte ptr [rbx+18h]
0x383ab7cb3  mov     [rax+90h], cl
0x383ab7cb9  mov     ecx, [rbx+44h]
0x383ab7cbc  sub     [rax+68h], ecx
0x383ab7cbf  mov     ecx, [rbx+4Ch]
0x383ab7cc2  add     ecx, [rbx+50h]
0x383ab7cc5  add     ecx, [rbx+48h]
0x383ab7cc8  mov     [rax+9Ch], ecx
0x383ab7cce  mov     word ptr [rax+0ACh], 101h
0x383ab7cd7  mov     eax, [rbx+44h]
0x383ab7cda  add     eax, ecx
0x383ab7cdc  add     eax, [r9+60h]
0x383ab7ce0  mov     [r9+60h], eax
0x383ab7ce4  xor     r8d, r8d; dwCompletionKey
0x383ab7ce7  xor     edx, edx; dwNumberOfBytesTransferred
0x383ab7ce9  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; CompletionPort
0x383ab7cf0  call    cs:__imp_PostQueuedCompletionStatus
0x383ab7cf6  test    eax, eax
0x383ab7cf8  jnz     short loc_383AB7D3F
0x383ab7cfa  test    byte ptr cs:_bidGblFlags, 2
0x383ab7d01  jz      short loc_383AB7D3F
0x383ab7d03  mov     rax, cs:off_383B47780; "<CryptoBase::CallbackError|ERR|SNI> SNI"...
0x383ab7d0a  test    rax, rax
0x383ab7d0d  jz      short loc_383AB7D3F
0x383ab7d0f  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ab7d17  jz      short loc_383AB7D3F
0x383ab7d19  mov     [rsp+48h+var_28], rsi
0x383ab7d1e  mov     r9, cs:off_383B47780; "<CryptoBase::CallbackError|ERR|SNI> SNI"...
0x383ab7d25  mov     r8d, 61000h
0x383ab7d2b  mov     rdx, cs:off_383B45100; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab7d32  mov     rcx, cs:_bidID
0x383ab7d39  call    cs:off_383B15038
0x383ab7d3f  cmp     [rbx+118h], rsi
0x383ab7d46  jnz     loc_383AB7CA0
0x383ab7d4c  mov     rcx, [rbx+38h]; struct SNI_Packet *
0x383ab7d50  test    rcx, rcx
0x383ab7d53  jz      short loc_383AB7D5E
0x383ab7d55  call    SNIPacketRelease
0x383ab7d5a  mov     [rbx+38h], rsi
0x383ab7d5e  lea     rcx, [rbx+100h]; this
0x383ab7d65  cmp     [rcx], rsi
0x383ab7d68  jz      short loc_383AB7DDF
0x383ab7d6a  call    ?DeQueue@DynamicQueue@@QEAAPEAXXZ; DynamicQueue::DeQueue(void)
0x383ab7d6f  movzx   ecx, byte ptr [rbx+18h]
0x383ab7d73  mov     [rax+90h], cl
0x383ab7d79  mov     byte ptr [rbx+0F9h], 1
0x383ab7d80  mov     r9, rax; lpOverlapped
0x383ab7d83  xor     r8d, r8d; dwCompletionKey
0x383ab7d86  xor     edx, edx; dwNumberOfBytesTransferred
0x383ab7d88  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; CompletionPort
0x383ab7d8f  call    cs:__imp_PostQueuedCompletionStatus
0x383ab7d95  test    eax, eax
0x383ab7d97  jnz     short loc_383AB7DDF
0x383ab7d99  test    byte ptr cs:_bidGblFlags, 2
0x383ab7da0  jz      short loc_383AB7DDF
0x383ab7da2  mov     rax, cs:off_383B47778; "<CryptoBase::CallbackError|ERR|SNI> SNI"...
0x383ab7da9  test    rax, rax
0x383ab7dac  jz      short loc_383AB7DDF
0x383ab7dae  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ab7db6  jz      short loc_383AB7DDF
0x383ab7db8  mov     [rsp+48h+var_28], rsi
0x383ab7dbd  mov     r9, cs:off_383B47778; "<CryptoBase::CallbackError|ERR|SNI> SNI"...
0x383ab7dc4  mov     r8d, 67800h
0x383ab7dca  mov     rdx, cs:off_383B450F8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab7dd1  mov     rcx, cs:_bidID
0x383ab7dd8  call    cs:off_383B15038
0x383ab7dde  nop
0x383ab7ddf  cmp     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383ab7de5  jz      short loc_383AB7E0D
0x383ab7de7  test    byte ptr cs:_bidGblFlags, 4
0x383ab7dee  jz      short loc_383AB7E0D
0x383ab7df0  mov     rcx, cs:_bidID
0x383ab7df7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ab7dfb  jz      short loc_383AB7E0D
0x383ab7dfd  lea     r9, [rsp+48h+arg_0]
0x383ab7e02  xor     r8d, r8d
0x383ab7e05  xor     edx, edx
0x383ab7e07  call    cs:off_383B15058
0x383ab7e0d  mov     rbx, [rsp+48h+arg_8]
0x383ab7e12  mov     rsi, [rsp+48h+arg_10]
0x383ab7e17  add     rsp, 40h
0x383ab7e1b  pop     rdi
0x383ab7e1c  retn
```
