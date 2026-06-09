# PnPServices::RegisterForDeviceEvents(ushort const *,PnPServices::IPnPDeviceEventCB *)

- ea: `0x1800255c0`
- end: `0x180025681`
- name: `?RegisterForDeviceEvents@PnPServices@@YAJPEBGPEAVIPnPDeviceEventCB@1@@Z`
- size: `193`
- prototype: `int(PnPServices *__hidden this, const unsigned __int16 *, struct PnPServices::IPnPDeviceEventCB *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002880c`

## callees

- `0x180003570`
- `0x180007b04`
- `0x180007b20`
- `0x1800247c4`
- `0x1800255c0`
- `0x180030de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800255ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800255ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025666`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025666`

## pseudocode

```c
__int64 __fastcall PnPServices::RegisterForDeviceEvents(
        PnPServices *this,
        unsigned __int16 *a2,
        struct PnPServices::IPnPDeviceEventCB *a3)
{
  __int64 v5; // rcx
  int v6; // esi
  __int64 v7; // r14
  int inserted; // ebx
  int v10; // [rsp+60h] [rbp+18h] BYREF
  __int64 v11; // [rsp+68h] [rbp+20h] BYREF

  v10 = 0;
  v11 = 0;
  EnterCriticalSection(&stru_18003E470);
  v6 = CNamedElemList<PnPServices::CHandleNotif>::GetOrAdd<int,unsigned short const *>(
         v5,
         (const unsigned __int16 *)this,
         &v11,
         &v10);
  if ( v6 >= 0 )
  {
    v7 = v11;
    _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
    CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(v7 + 40);
    v6 = 0;
    inserted = DPA_InsertPtr(*(HDPA *)(v7 + 32), 0x7FFFFFFF, a2);
    if ( inserted == -1 )
      v6 = -2147467259;
    CCritSectWithResource<CDummyResource>::Leave(v7 + 40);
    if ( inserted == -1 )
      CRefCounted::Release((CRefCounted *)a2);
    CRefCounted::Release((CRefCounted *)(v7 + 16));
  }
  LeaveCriticalSection(&stru_18003E470);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800255c0  mov     rax, rsp
0x1800255c3  mov     [rax+8], rbx
0x1800255c7  mov     [rax+10h], rbp
0x1800255cb  push    rsi
0x1800255cc  push    rdi
0x1800255cd  push    r14
0x1800255cf  sub     rsp, 30h
0x1800255d3  mov     rbx, rcx
0x1800255d6  mov     dword ptr [rax+18h], 0
0x1800255dd  lea     rcx, stru_18003E470; lpCriticalSection
0x1800255e4  mov     qword ptr [rax+20h], 0
0x1800255ec  mov     rbp, rdx
0x1800255ef  call    cs:__imp_EnterCriticalSection
0x1800255f5  lea     r9, [rsp+48h+arg_10]
0x1800255fa  mov     rdx, rbx
0x1800255fd  lea     r8, [rsp+48h+arg_18]
0x180025602  call    ??$GetOrAdd@HPEBG@?$CNamedElemList@VCHandleNotif@PnPServices@@@@QEAAJQEBGPEAPEAVCHandleNotif@PnPServices@@PEAHH@Z; CNamedElemList<PnPServices::CHandleNotif>::GetOrAdd<int,ushort const *>(ushort const * const,PnPServices::CHandleNotif * *,int *,int)
0x180025607  mov     esi, eax
0x180025609  test    eax, eax
0x18002560b  js      short loc_18002565F
0x18002560d  mov     r14, [rsp+48h+arg_18]
0x180025612  lock inc dword ptr [rbp+8]
0x180025616  lea     rcx, [r14+28h]
0x18002561a  call    ?Enter@?$CCritSectWithResource@V?$CNamedElemList@VCHandleNotif@PnPServices@@@@@@QEAAXXZ; CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(void)
0x18002561f  mov     rcx, [r14+20h]; hdpa
0x180025623  mov     r8, rbp; p
0x180025626  mov     edx, 7FFFFFFFh; i
0x18002562b  call    cs:__imp_DPA_InsertPtr
0x180025631  xor     esi, esi
0x180025633  lea     rcx, [r14+28h]
0x180025637  mov     ebx, eax
0x180025639  mov     eax, 80004005h
0x18002563e  cmp     ebx, 0FFFFFFFFh
0x180025641  cmovz   esi, eax
0x180025644  call    ?Leave@?$CCritSectWithResource@VCDummyResource@@@@QEAAXXZ; CCritSectWithResource<CDummyResource>::Leave(void)
0x180025649  cmp     ebx, 0FFFFFFFFh
0x18002564c  jnz     short loc_180025656
0x18002564e  mov     rcx, rbp; this
0x180025651  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180025656  lea     rcx, [r14+10h]; this
0x18002565a  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x18002565f  lea     rcx, stru_18003E470; lpCriticalSection
0x180025666  call    cs:__imp_LeaveCriticalSection
0x18002566c  mov     rbx, [rsp+48h+arg_0]
0x180025671  mov     eax, esi
0x180025673  mov     rbp, [rsp+48h+arg_8]
0x180025678  add     rsp, 30h
0x18002567c  pop     r14
0x18002567e  pop     rdi
0x18002567f  pop     rsi
0x180025680  retn
```
