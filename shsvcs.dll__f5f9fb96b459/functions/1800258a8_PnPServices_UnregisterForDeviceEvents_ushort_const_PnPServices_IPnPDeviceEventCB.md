# PnPServices::UnregisterForDeviceEvents(ushort const *,PnPServices::IPnPDeviceEventCB *)

- ea: `0x1800258a8`
- end: `0x180025977`
- name: `?UnregisterForDeviceEvents@PnPServices@@YAJPEBGPEAVIPnPDeviceEventCB@1@@Z`
- size: `207`
- prototype: `int(PnPServices *__hidden this, const unsigned __int16 *, struct PnPServices::IPnPDeviceEventCB *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x18002880c`
- `0x1800288d4`

## callees

- `0x180003570`
- `0x180007b04`
- `0x180007b20`
- `0x180018b14`
- `0x180024958`
- `0x180025750`
- `0x1800258a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800258c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800258c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002595c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002595c`

## pseudocode

```c
__int64 __fastcall PnPServices::UnregisterForDeviceEvents(
        PnPServices *this,
        struct PnPServices::IPnPDeviceEventCB *a2,
        struct PnPServices::IPnPDeviceEventCB *a3)
{
  CRefCounted *v5; // rsi
  __int64 v6; // rdi
  int Elem; // ebx
  CRefCounted *v8; // rcx
  CRefCounted *v9; // rcx
  CRefCounted *v11; // [rsp+50h] [rbp+18h] BYREF

  EnterCriticalSection(&stru_18003E470);
  v5 = PnPServices::g_pnelHandleNotif;
  v6 = 0;
  v11 = 0;
  CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(*((_QWORD *)PnPServices::g_pnelHandleNotif + 3));
  Elem = CNamedElemList<PnPServices::CHandleNotif>::_GetElemSlot<unsigned short const *>(
           (__int64)v5,
           (const unsigned __int16 *)this,
           (__int64 *)&v11);
  if ( Elem >= 0 )
  {
    v8 = v11;
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v11 + 2) + 24LL));
    v6 = *((_QWORD *)v8 + 2);
    Elem = 0;
    CRefCounted::Release(v8);
  }
  CCritSectWithResource<CDummyResource>::Leave(*((_QWORD *)v5 + 3));
  if ( Elem >= 0 )
  {
    LODWORD(v11) = 0;
    Elem = PnPServices::CHandleNotif::RemoveCallback((PnPServices::CHandleNotif *)v6, a2, (int *)&v11);
    if ( (_DWORD)v11 )
      CNamedElemList<PnPServices::CHandleNotif>::Remove<unsigned short const *>(v9, (const unsigned __int16 *)this);
    CRefCounted::Release((CRefCounted *)(v6 + 16));
  }
  LeaveCriticalSection(&stru_18003E470);
  return (unsigned int)Elem;
}

```

## disassembly

```asm
0x1800258a8  mov     [rsp+arg_0], rbx
0x1800258ad  mov     [rsp+arg_8], rbp
0x1800258b2  push    rsi
0x1800258b3  push    rdi
0x1800258b4  push    r14
0x1800258b6  sub     rsp, 20h
0x1800258ba  mov     rbp, rcx
0x1800258bd  mov     r14, rdx
0x1800258c0  lea     rcx, stru_18003E470; lpCriticalSection
0x1800258c7  call    cs:__imp_EnterCriticalSection
0x1800258cd  mov     rsi, cs:?g_pnelHandleNotif@PnPServices@@3PEAV?$CNamedElemList@VCHandleNotif@PnPServices@@@@EA; CNamedElemList<PnPServices::CHandleNotif> * PnPServices::g_pnelHandleNotif
0x1800258d4  xor     edi, edi
0x1800258d6  mov     [rsp+38h+arg_10], 0
0x1800258df  mov     rcx, [rsi+18h]
0x1800258e3  call    ?Enter@?$CCritSectWithResource@V?$CNamedElemList@VCHandleNotif@PnPServices@@@@@@QEAAXXZ; CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(void)
0x1800258e8  lea     r8, [rsp+38h+arg_10]
0x1800258ed  mov     rdx, rbp
0x1800258f0  mov     rcx, rsi
0x1800258f3  call    ??$_GetElemSlot@PEBG@?$CNamedElemList@VCHandleNotif@PnPServices@@@@AEAAJQEBGPEAPEAV?$CElemSlot@VCHandleNotif@PnPServices@@@@@Z; CNamedElemList<PnPServices::CHandleNotif>::_GetElemSlot<ushort const *>(ushort const * const,CElemSlot<PnPServices::CHandleNotif> * *)
0x1800258f8  mov     ebx, eax
0x1800258fa  test    eax, eax
0x1800258fc  js      short loc_180025916
0x1800258fe  mov     rcx, [rsp+38h+arg_10]; this
0x180025903  mov     rax, [rcx+10h]
0x180025907  lock inc dword ptr [rax+18h]
0x18002590b  mov     rdi, [rcx+10h]
0x18002590f  xor     ebx, ebx
0x180025911  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180025916  mov     rcx, [rsi+18h]
0x18002591a  call    ?Leave@?$CCritSectWithResource@VCDummyResource@@@@QEAAXXZ; CCritSectWithResource<CDummyResource>::Leave(void)
0x18002591f  test    ebx, ebx
0x180025921  js      short loc_180025955
0x180025923  lea     r8, [rsp+38h+arg_10]; int *
0x180025928  mov     dword ptr [rsp+38h+arg_10], 0
0x180025930  mov     rdx, r14; struct PnPServices::IPnPDeviceEventCB *
0x180025933  mov     rcx, rdi; this
0x180025936  call    ?RemoveCallback@CHandleNotif@PnPServices@@QEAAJPEAVIPnPDeviceEventCB@2@PEAH@Z; PnPServices::CHandleNotif::RemoveCallback(PnPServices::IPnPDeviceEventCB *,int *)
0x18002593b  cmp     dword ptr [rsp+38h+arg_10], 0
0x180025940  mov     ebx, eax
0x180025942  jz      short loc_18002594C
0x180025944  mov     rdx, rbp
0x180025947  call    ??$Remove@PEBG@?$CNamedElemList@VCHandleNotif@PnPServices@@@@QEAAJQEBG@Z; CNamedElemList<PnPServices::CHandleNotif>::Remove<ushort const *>(ushort const * const)
0x18002594c  lea     rcx, [rdi+10h]; this
0x180025950  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180025955  lea     rcx, stru_18003E470; lpCriticalSection
0x18002595c  call    cs:__imp_LeaveCriticalSection
0x180025962  mov     rbp, [rsp+38h+arg_8]
0x180025967  mov     eax, ebx
0x180025969  mov     rbx, [rsp+38h+arg_0]
0x18002596e  add     rsp, 20h
0x180025972  pop     r14
0x180025974  pop     rdi
0x180025975  pop     rsi
0x180025976  retn
```
