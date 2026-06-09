# ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::RemoveAll(void)

- ea: `0x180014aec`
- end: `0x180014b9d`
- name: `?RemoveAll@?$CAtlMap@KPEAVSqmSessionContext@CSqmSessionMgr@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmSessionContext@CSqmSessionMgr@@@4@@ATL@@QEAAXXZ`
- size: `177`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x1800144c4`
- `0x1800153ac`
- `0x180015dd8`

## callees

- `0x180001954`
- `0x1800146e8`
- `0x180014978`
- `0x180014aec`
- `0x180015024`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014b78`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014b78`

## pseudocode

```c
void __fastcall ATL::CAtlMap<unsigned long,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::RemoveAll(
        __int64 a1)
{
  __int64 i; // rbx
  __int64 v3; // rsi
  __int64 v4; // rdx
  bool v5; // zf
  _QWORD *v6; // rcx
  _QWORD *v7; // rbx

  ++*(_DWORD *)(a1 + 48);
  if ( *(_QWORD *)a1 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 16); i = (unsigned int)(i + 1) )
    {
      v3 = *(_QWORD *)(*(_QWORD *)a1 + 8 * i);
      while ( v3 )
      {
        v4 = v3;
        v3 = *(_QWORD *)(v3 + 16);
        ATL::CAtlMap<unsigned long,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::FreeNode(
          a1,
          v4);
      }
    }
  }
  operator delete(*(void **)a1);
  v5 = *(_DWORD *)(a1 + 48) == 0;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( v5 )
  {
    *(_DWORD *)(a1 + 16) = ATL::CAtlMap<unsigned long,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::PickSize(
                             a1,
                             0);
    ATL::CAtlMap<unsigned long,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::UpdateRehashThresholds(a1);
  }
  v6 = *(_QWORD **)(a1 + 56);
  *(_QWORD *)(a1 + 64) = 0;
  if ( v6 )
  {
    do
    {
      v7 = (_QWORD *)*v6;
      free(v6);
      v6 = v7;
    }
    while ( v7 );
    *(_QWORD *)(a1 + 56) = 0;
  }
  --*(_DWORD *)(a1 + 48);
}

```

## disassembly

```asm
0x180014aec  mov     [rsp+arg_0], rbx
0x180014af1  mov     [rsp+arg_8], rsi
0x180014af6  push    rdi
0x180014af7  sub     rsp, 20h
0x180014afb  inc     dword ptr [rcx+30h]
0x180014afe  mov     rdi, rcx
0x180014b01  cmp     qword ptr [rcx], 0
0x180014b05  jz      short loc_180014B32
0x180014b07  xor     ebx, ebx
0x180014b09  cmp     [rcx+10h], ebx
0x180014b0c  jbe     short loc_180014B32
0x180014b0e  mov     rax, [rdi]
0x180014b11  mov     rsi, [rax+rbx*8]
0x180014b15  jmp     short loc_180014B26
0x180014b17  mov     rdx, rsi
0x180014b1a  mov     rcx, rdi
0x180014b1d  mov     rsi, [rsi+10h]
0x180014b21  call    ?FreeNode@?$CAtlMap@KPEAVSqmSessionContext@CSqmSessionMgr@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmSessionContext@CSqmSessionMgr@@@4@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::FreeNode(ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::CNode *)
0x180014b26  test    rsi, rsi
0x180014b29  jnz     short loc_180014B17
0x180014b2b  inc     ebx
0x180014b2d  cmp     ebx, [rdi+10h]
0x180014b30  jb      short loc_180014B0E
0x180014b32  mov     rcx, [rdi]; Block
0x180014b35  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014b3a  cmp     dword ptr [rdi+30h], 0
0x180014b3e  mov     qword ptr [rdi], 0
0x180014b45  mov     qword ptr [rdi+8], 0
0x180014b4d  jnz     short loc_180014B64
0x180014b4f  xor     edx, edx
0x180014b51  mov     rcx, rdi
0x180014b54  call    ?PickSize@?$CAtlMap@KPEAVSqmSessionContext@CSqmSessionMgr@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmSessionContext@CSqmSessionMgr@@@4@@ATL@@AEBAI_K@Z; ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::PickSize(unsigned __int64)
0x180014b59  mov     rcx, rdi
0x180014b5c  mov     [rdi+10h], eax
0x180014b5f  call    ?UpdateRehashThresholds@?$CAtlMap@KPEAVSqmSessionContext@CSqmSessionMgr@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmSessionContext@CSqmSessionMgr@@@4@@ATL@@AEAAXXZ; ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::UpdateRehashThresholds(void)
0x180014b64  mov     rcx, [rdi+38h]; Block
0x180014b68  mov     qword ptr [rdi+40h], 0
0x180014b70  test    rcx, rcx
0x180014b73  jz      short loc_180014B8A
0x180014b75  mov     rbx, [rcx]
0x180014b78  call    cs:__imp_free
0x180014b7e  mov     rcx, rbx
0x180014b81  test    rbx, rbx
0x180014b84  jnz     short loc_180014B75
0x180014b86  mov     [rdi+38h], rbx
0x180014b8a  dec     dword ptr [rdi+30h]
0x180014b8d  mov     rbx, [rsp+28h+arg_0]
0x180014b92  mov     rsi, [rsp+28h+arg_8]
0x180014b97  add     rsp, 20h
0x180014b9b  pop     rdi
0x180014b9c  retn
```
