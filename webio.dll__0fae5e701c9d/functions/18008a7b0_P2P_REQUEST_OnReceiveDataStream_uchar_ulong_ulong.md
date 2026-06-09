# P2P_REQUEST::OnReceiveDataStream(uchar *,ulong,ulong)

- ea: `0x18008a7b0`
- end: `0x18008a97e`
- name: `?OnReceiveDataStream@P2P_REQUEST@@QEAAKPEAEKK@Z`
- size: `462`
- prototype: `unsigned int __fastcall(P2P_REQUEST *__hidden this, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18008a30c`

## callees

- `0x1800730dc`
- `0x18007310c`
- `0x18008a408`
- `0x18008a7b0`
- `0x18008bc6c`
- `0x180091678`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a7fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a7fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008a7e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008a7e7`

## pseudocode

```c
__int64 __fastcall P2P_REQUEST::OnReceiveDataStream(P2P_REQUEST *this, unsigned __int8 *a2, unsigned int a3, int a4)
{
  HANDLE EventW; // rax
  DWORD LastError; // edi
  unsigned __int8 *v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned int v13; // eax
  void *v15; // rax
  int v16; // ebp
  __int64 v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // r14d
  unsigned int v20; // r8d

  if ( *((_DWORD *)this + 34) )
    return 0;
  if ( !*((_QWORD *)this + 13) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 13) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      *((_DWORD *)this + 34) = LastError;
      return LastError;
    }
  }
  if ( a4 )
  {
    *((_DWORD *)this + 34) = a4;
    if ( a4 == 38 )
    {
      v10 = (unsigned __int8 *)*((_QWORD *)this + 27);
      if ( v10 )
      {
        v11 = *((_DWORD *)this + 52);
        if ( v11 )
        {
          v12 = P2P_REQUEST::AddDataStream(this, v10, v11);
          operator delete(*((void **)this + 27));
          *((_QWORD *)this + 27) = 0;
          if ( v12 )
          {
            *((_DWORD *)this + 34) = v12;
            return 0;
          }
          *((_DWORD *)this + 52) = 0;
        }
      }
      P2P_HASH_REQUEST::ProcessHashRequest(*((struct P2P_HASH_REQUEST **)this + 23));
      *((_QWORD *)this + 23) = 0;
    }
    return 0;
  }
  LastError = 0;
  if ( a2 && a3 )
  {
    if ( !*((_DWORD *)this + 52) && a3 >= 0x80000 )
    {
      v13 = P2P_REQUEST::AddDataStream(this, a2, a3);
      LastError = v13;
      if ( !v13 )
        return LastError;
LABEL_18:
      *((_DWORD *)this + 34) = v13;
      return 0;
    }
    if ( *((_QWORD *)this + 27)
      || (*((_DWORD *)this + 52) = 0,
          *((_DWORD *)this + 53) = 0x80000,
          v15 = operator new[](0x80000u, (const struct std::nothrow_t *)&std::nothrow),
          (*((_QWORD *)this + 27) = v15) != 0) )
    {
      v16 = 0;
      while ( a3 )
      {
        v17 = *((unsigned int *)this + 52);
        v18 = *((_DWORD *)this + 53) - v17;
        if ( v18 >= a3 )
          v18 = a3;
        v19 = v18;
        memcpy_0((void *)(*((_QWORD *)this + 27) + v17), &a2[v16], v18);
        *((_DWORD *)this + 52) += v19;
        v20 = *((_DWORD *)this + 52);
        if ( v20 == *((_DWORD *)this + 53) )
        {
          v13 = P2P_REQUEST::AddDataStream(this, *((unsigned __int8 **)this + 27), v20);
          LastError = v13;
          if ( v13 )
            goto LABEL_18;
          *((_DWORD *)this + 52) = 0;
        }
        v16 += v19;
        a3 -= v19;
      }
    }
    else
    {
      LastError = 8;
      *((_DWORD *)this + 34) = 8;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18008a7b0  push    rbx
0x18008a7b2  push    rbp
0x18008a7b3  push    rsi
0x18008a7b4  push    rdi
0x18008a7b5  push    r14
0x18008a7b7  push    r15
0x18008a7b9  sub     rsp, 28h
0x18008a7bd  cmp     dword ptr [rcx+88h], 0
0x18008a7c4  mov     edi, r9d
0x18008a7c7  mov     esi, r8d
0x18008a7ca  mov     r15, rdx
0x18008a7cd  mov     rbx, rcx
0x18008a7d0  jnz     loc_18008A8C6
0x18008a7d6  cmp     qword ptr [rcx+68h], 0
0x18008a7db  jnz     short loc_18008A815
0x18008a7dd  xor     r9d, r9d; lpName
0x18008a7e0  xor     r8d, r8d; bInitialState
0x18008a7e3  xor     edx, edx; bManualReset
0x18008a7e5  xor     ecx, ecx; lpEventAttributes
0x18008a7e7  call    cs:__imp_CreateEventW
0x18008a7ee  nop     dword ptr [rax+rax+00h]
0x18008a7f3  mov     [rbx+68h], rax
0x18008a7f7  test    rax, rax
0x18008a7fa  jnz     short loc_18008A815
0x18008a7fc  call    cs:__imp_GetLastError
0x18008a803  nop     dword ptr [rax+rax+00h]
0x18008a808  mov     edi, eax
0x18008a80a  mov     [rbx+88h], eax
0x18008a810  jmp     loc_18008A8C8
0x18008a815  test    edi, edi
0x18008a817  jz      short loc_18008A890
0x18008a819  mov     [rbx+88h], edi
0x18008a81f  cmp     edi, 26h ; '&'
0x18008a822  jnz     loc_18008A8C6
0x18008a828  mov     rdx, [rbx+0D8h]; unsigned __int8 *
0x18008a82f  test    rdx, rdx
0x18008a832  jz      short loc_18008A877
0x18008a834  mov     r8d, [rbx+0D0h]; unsigned int
0x18008a83b  test    r8d, r8d
0x18008a83e  jz      short loc_18008A877
0x18008a840  mov     rcx, rbx; this
0x18008a843  call    ?AddDataStream@P2P_REQUEST@@AEAAKPEAEK@Z; P2P_REQUEST::AddDataStream(uchar *,ulong)
0x18008a848  mov     rcx, [rbx+0D8h]; Block
0x18008a84f  mov     edi, eax
0x18008a851  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008a856  mov     qword ptr [rbx+0D8h], 0
0x18008a861  test    edi, edi
0x18008a863  jz      short loc_18008A86D
0x18008a865  mov     [rbx+88h], edi
0x18008a86b  jmp     short loc_18008A8C6
0x18008a86d  mov     dword ptr [rbx+0D0h], 0
0x18008a877  mov     rcx, [rbx+0B8h]; struct P2P_HASH_REQUEST *
0x18008a87e  call    ?ProcessHashRequest@P2P_HASH_REQUEST@@SAXPEAV1@@Z; P2P_HASH_REQUEST::ProcessHashRequest(P2P_HASH_REQUEST *)
0x18008a883  mov     qword ptr [rbx+0B8h], 0
0x18008a88e  jmp     short loc_18008A8C6
0x18008a890  xor     edi, edi
0x18008a892  test    r15, r15
0x18008a895  jz      short loc_18008A8C8
0x18008a897  test    esi, esi
0x18008a899  jz      short loc_18008A8C8
0x18008a89b  mov     ecx, 80000h; unsigned __int64
0x18008a8a0  cmp     [rbx+0D0h], edi
0x18008a8a6  jnz     short loc_18008A8D8
0x18008a8a8  cmp     esi, ecx
0x18008a8aa  jb      short loc_18008A8D8
0x18008a8ac  mov     r8d, esi; unsigned int
0x18008a8af  mov     rdx, r15; unsigned __int8 *
0x18008a8b2  mov     rcx, rbx; this
0x18008a8b5  call    ?AddDataStream@P2P_REQUEST@@AEAAKPEAEK@Z; P2P_REQUEST::AddDataStream(uchar *,ulong)
0x18008a8ba  mov     edi, eax
0x18008a8bc  test    eax, eax
0x18008a8be  jz      short loc_18008A8C8
0x18008a8c0  mov     [rbx+88h], eax
0x18008a8c6  xor     edi, edi
0x18008a8c8  mov     eax, edi
0x18008a8ca  add     rsp, 28h
0x18008a8ce  pop     r15
0x18008a8d0  pop     r14
0x18008a8d2  pop     rdi
0x18008a8d3  pop     rsi
0x18008a8d4  pop     rbp
0x18008a8d5  pop     rbx
0x18008a8d6  retn
0x18008a8d8  cmp     [rbx+0D8h], rdi
0x18008a8df  jnz     short loc_18008A910
0x18008a8e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008a8e8  mov     [rbx+0D0h], edi
0x18008a8ee  mov     [rbx+0D4h], ecx
0x18008a8f4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008a8f9  mov     [rbx+0D8h], rax
0x18008a900  test    rax, rax
0x18008a903  jnz     short loc_18008A910
0x18008a905  lea     edi, [rax+8]
0x18008a908  mov     [rbx+88h], edi
0x18008a90e  jmp     short loc_18008A8C8
0x18008a910  xor     ebp, ebp
0x18008a912  test    esi, esi
0x18008a914  jz      short loc_18008A8C8
0x18008a916  mov     ecx, [rbx+0D0h]
0x18008a91c  mov     eax, [rbx+0D4h]
0x18008a922  sub     eax, ecx
0x18008a924  mov     edx, ebp
0x18008a926  cmp     eax, esi
0x18008a928  cmovnb  eax, esi
0x18008a92b  add     rcx, [rbx+0D8h]; void *
0x18008a932  mov     r8d, eax; Size
0x18008a935  add     rdx, r15; Src
0x18008a938  mov     r14d, eax
0x18008a93b  call    memcpy_0
0x18008a940  add     [rbx+0D0h], r14d
0x18008a947  mov     r8d, [rbx+0D0h]; unsigned int
0x18008a94e  cmp     r8d, [rbx+0D4h]
0x18008a955  jnz     short loc_18008A976
0x18008a957  mov     rdx, [rbx+0D8h]; unsigned __int8 *
0x18008a95e  mov     rcx, rbx; this
0x18008a961  call    ?AddDataStream@P2P_REQUEST@@AEAAKPEAEK@Z; P2P_REQUEST::AddDataStream(uchar *,ulong)
0x18008a966  mov     edi, eax
0x18008a968  test    eax, eax
0x18008a96a  jnz     loc_18008A8C0
0x18008a970  mov     [rbx+0D0h], eax
0x18008a976  add     ebp, r14d
0x18008a979  sub     esi, r14d
0x18008a97c  jmp     short loc_18008A912
```
