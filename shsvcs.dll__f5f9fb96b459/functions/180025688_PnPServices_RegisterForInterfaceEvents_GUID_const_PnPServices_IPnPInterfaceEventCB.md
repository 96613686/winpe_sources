# PnPServices::RegisterForInterfaceEvents(_GUID const *,PnPServices::IPnPInterfaceEventCB *)

- ea: `0x180025688`
- end: `0x180025748`
- name: `?RegisterForInterfaceEvents@PnPServices@@YAJPEBU_GUID@@PEAVIPnPInterfaceEventCB@1@@Z`
- size: `192`
- prototype: `int(PnPServices *__hidden this, const struct _GUID *, struct PnPServices::IPnPInterfaceEventCB *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002874c`

## callees

- `0x180003570`
- `0x180007b04`
- `0x180007b20`
- `0x180024880`
- `0x180025688`
- `0x180030de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800256b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800256b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002572d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002572d`

## pseudocode

```c
__int64 __fastcall PnPServices::RegisterForInterfaceEvents(
        PnPServices *this,
        struct _GUID *a2,
        struct PnPServices::IPnPInterfaceEventCB *a3)
{
  __int64 v5; // rcx
  int v6; // esi
  HDPA *v7; // r14
  int inserted; // ebx
  int v10; // [rsp+60h] [rbp+18h] BYREF
  CRefCounted *v11; // [rsp+68h] [rbp+20h] BYREF

  v10 = 0;
  v11 = 0;
  EnterCriticalSection(&stru_18003E470);
  v6 = CNamedElemList<PnPServices::CInterfaceNotif>::GetOrAdd<int,_GUID const *>(v5, this, &v11, &v10);
  if ( v6 >= 0 )
  {
    v7 = (HDPA *)v11;
    _InterlockedIncrement((volatile signed __int32 *)a2->Data4);
    CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter((__int64)(v7 + 3));
    v6 = 0;
    inserted = DPA_InsertPtr(v7[2], 0x7FFFFFFF, a2);
    if ( inserted == -1 )
      v6 = -2147467259;
    CCritSectWithResource<CDummyResource>::Leave(v7 + 3);
    if ( inserted == -1 )
      CRefCounted::Release((CRefCounted *)a2);
    CRefCounted::Release((CRefCounted *)v7);
  }
  LeaveCriticalSection(&stru_18003E470);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180025688  mov     rax, rsp
0x18002568b  mov     [rax+8], rbx
0x18002568f  mov     [rax+10h], rbp
0x180025693  push    rsi
0x180025694  push    rdi
0x180025695  push    r14
0x180025697  sub     rsp, 30h
0x18002569b  mov     rbx, rcx
0x18002569e  mov     dword ptr [rax+18h], 0
0x1800256a5  lea     rcx, stru_18003E470; lpCriticalSection
0x1800256ac  mov     qword ptr [rax+20h], 0
0x1800256b4  mov     rbp, rdx
0x1800256b7  call    cs:__imp_EnterCriticalSection
0x1800256bd  lea     r9, [rsp+48h+arg_10]
0x1800256c2  mov     rdx, rbx
0x1800256c5  lea     r8, [rsp+48h+arg_18]
0x1800256ca  call    ??$GetOrAdd@HPEBU_GUID@@@?$CNamedElemList@VCInterfaceNotif@PnPServices@@@@QEAAJQEBU_GUID@@PEAPEAVCInterfaceNotif@PnPServices@@PEAHH@Z; CNamedElemList<PnPServices::CInterfaceNotif>::GetOrAdd<int,_GUID const *>(_GUID const * const,PnPServices::CInterfaceNotif * *,int *,int)
0x1800256cf  mov     esi, eax
0x1800256d1  test    eax, eax
0x1800256d3  js      short loc_180025726
0x1800256d5  mov     r14, [rsp+48h+arg_18]
0x1800256da  lock inc dword ptr [rbp+8]
0x1800256de  lea     rcx, [r14+18h]
0x1800256e2  call    ?Enter@?$CCritSectWithResource@V?$CNamedElemList@VCHandleNotif@PnPServices@@@@@@QEAAXXZ; CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(void)
0x1800256e7  mov     rcx, [r14+10h]; hdpa
0x1800256eb  mov     r8, rbp; p
0x1800256ee  mov     edx, 7FFFFFFFh; i
0x1800256f3  call    cs:__imp_DPA_InsertPtr
0x1800256f9  xor     esi, esi
0x1800256fb  lea     rcx, [r14+18h]
0x1800256ff  mov     ebx, eax
0x180025701  mov     eax, 80004005h
0x180025706  cmp     ebx, 0FFFFFFFFh
0x180025709  cmovz   esi, eax
0x18002570c  call    ?Leave@?$CCritSectWithResource@VCDummyResource@@@@QEAAXXZ; CCritSectWithResource<CDummyResource>::Leave(void)
0x180025711  cmp     ebx, 0FFFFFFFFh
0x180025714  jnz     short loc_18002571E
0x180025716  mov     rcx, rbp; this
0x180025719  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x18002571e  mov     rcx, r14; this
0x180025721  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180025726  lea     rcx, stru_18003E470; lpCriticalSection
0x18002572d  call    cs:__imp_LeaveCriticalSection
0x180025733  mov     rbx, [rsp+48h+arg_0]
0x180025738  mov     eax, esi
0x18002573a  mov     rbp, [rsp+48h+arg_8]
0x18002573f  add     rsp, 30h
0x180025743  pop     r14
0x180025745  pop     rdi
0x180025746  pop     rsi
0x180025747  retn
```
