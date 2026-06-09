# CReplicaMetadata::Initialize(CDbOperationManager *,uchar const *,_ID_PARAMETERS *,CReplicaTable *)

- ea: `0x1800db974`
- end: `0x1800dba54`
- name: `?Initialize@CReplicaMetadata@@AEAAJPEAVCDbOperationManager@@PEBEPEAU_ID_PARAMETERS@@PEAVCReplicaTable@@@Z`
- size: `224`
- prototype: `int(CReplicaMetadata *__hidden this, struct CDbOperationManager *, const unsigned __int8 *, struct _ID_PARAMETERS *, struct CReplicaTable *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800d93ec`

## callees

- `0x1800d72e8`
- `0x1800d7788`
- `0x1800d7b74`
- `0x1800d7c88`
- `0x1800db974`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800db9bd`
- `KERNEL32!GetLastError` at `0x1800db9bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800db9ae`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800db9ae`
- `WinSync!__imp_CreateSyncServiceInstance` at `0x1800dba2b`
- `WinSync!__imp_CreateSyncServiceInstance` at `0x1800dba2b`

## pseudocode

```c
int __fastcall CReplicaMetadata::Initialize(
        CReplicaMetadata *this,
        struct CDbOperationManager *a2,
        unsigned __int8 *a3,
        struct _ID_PARAMETERS *a4,
        struct CReplicaTable *a5)
{
  __int128 v8; // xmm1
  HANDLE MutexW; // rax
  int result; // eax
  bool v11; // sf
  unsigned __int16 ReplicaIdSize; // ax

  *((_QWORD *)this + 9) = a2;
  *(_OWORD *)((char *)this + 92) = *(_OWORD *)&a4->dwSize;
  v8 = *(_OWORD *)&a4->itemId.fIsVariable;
  *((_QWORD *)this + 20) = a5;
  *(_OWORD *)((char *)this + 104) = v8;
  MutexW = CreateMutexW(0, 0, 0);
  *((_QWORD *)this + 7) = MutexW;
  if ( MutexW )
    goto LABEL_5;
  result = GetLastError();
  v11 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v11 = result < 0;
  }
  if ( !v11 )
  {
LABEL_5:
    result = CMetaStoreUtils::CopyReplicaId(a3, a4, (unsigned __int16 *)this + 44, (unsigned __int8 **)this + 10);
    if ( result >= 0 )
    {
      ReplicaIdSize = CMetaStoreUtils::GetReplicaIdSize(a3, a4);
      result = CSha1Hash::HashBytes((CReplicaMetadata *)((char *)this + 120), a3, ReplicaIdSize);
      if ( result >= 0 )
      {
        result = CSha1Hash::GetAsString((CReplicaMetadata *)((char *)this + 120), (unsigned __int16 **)this + 18);
        if ( result >= 0 )
        {
          result = CreateSyncServiceInstance(&GUID_8ed97ec6_e77c_452e_9866_3747bc305db5, (char *)this + 152);
          if ( result >= 0 )
            return (*(__int64 (__fastcall **)(_QWORD, struct _ID_PARAMETERS *))(**((_QWORD **)this + 19) + 24LL))(
                     *((_QWORD *)this + 19),
                     a4);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800db974  push    rbx
0x1800db976  push    rbp
0x1800db977  push    rsi
0x1800db978  push    rdi
0x1800db979  sub     rsp, 28h
0x1800db97d  mov     rax, [rsp+48h+arg_20]
0x1800db982  mov     rbp, r8
0x1800db985  mov     [rcx+48h], rdx
0x1800db989  mov     rbx, rcx
0x1800db98c  movups  xmm0, xmmword ptr [r9]
0x1800db990  xor     r8d, r8d; lpName
0x1800db993  xor     edx, edx; bInitialOwner
0x1800db995  mov     rdi, r9
0x1800db998  movups  xmmword ptr [rcx+5Ch], xmm0
0x1800db99c  movups  xmm1, xmmword ptr [r9+0Ch]
0x1800db9a1  mov     [rcx+0A0h], rax
0x1800db9a8  movups  xmmword ptr [rcx+68h], xmm1
0x1800db9ac  xor     ecx, ecx; lpMutexAttributes
0x1800db9ae  call    cs:__imp_CreateMutexW
0x1800db9b4  mov     [rbx+38h], rax
0x1800db9b8  test    rax, rax
0x1800db9bb  jnz     short loc_1800DB9D3
0x1800db9bd  call    cs:__imp_GetLastError
0x1800db9c3  test    eax, eax
0x1800db9c5  jle     short loc_1800DB9D1
0x1800db9c7  movzx   eax, ax
0x1800db9ca  or      eax, 80070000h
0x1800db9cf  test    eax, eax
0x1800db9d1  js      short loc_1800DBA4B
0x1800db9d3  lea     r9, [rbx+50h]; unsigned __int8 **
0x1800db9d7  mov     rdx, rdi; struct _ID_PARAMETERS *
0x1800db9da  lea     r8, [rbx+58h]; unsigned __int16 *
0x1800db9de  mov     rcx, rbp; Source
0x1800db9e1  call    ?CopyReplicaId@CMetaStoreUtils@@SAJPEBEPEAU_ID_PARAMETERS@@PEAGPEAPEAE@Z; CMetaStoreUtils::CopyReplicaId(uchar const *,_ID_PARAMETERS *,ushort *,uchar * *)
0x1800db9e6  test    eax, eax
0x1800db9e8  js      short loc_1800DBA4B
0x1800db9ea  mov     rdx, rdi; struct _ID_PARAMETERS *
0x1800db9ed  mov     rcx, rbp; unsigned __int8 *
0x1800db9f0  call    ?GetReplicaIdSize@CMetaStoreUtils@@SAGPEBEPEBU_ID_PARAMETERS@@@Z; CMetaStoreUtils::GetReplicaIdSize(uchar const *,_ID_PARAMETERS const *)
0x1800db9f5  movzx   r8d, ax; dwDataLen
0x1800db9f9  lea     rcx, [rbx+78h]; this
0x1800db9fd  mov     rdx, rbp; pbData
0x1800dba00  call    ?HashBytes@CSha1Hash@@QEAAJPEBE_K@Z; CSha1Hash::HashBytes(uchar const *,unsigned __int64)
0x1800dba05  test    eax, eax
0x1800dba07  js      short loc_1800DBA4B
0x1800dba09  lea     rdx, [rbx+90h]; unsigned __int16 **
0x1800dba10  lea     rcx, [rbx+78h]; this
0x1800dba14  call    ?GetAsString@CSha1Hash@@QEBAJPEAPEAG@Z; CSha1Hash::GetAsString(ushort * *)
0x1800dba19  test    eax, eax
0x1800dba1b  js      short loc_1800DBA4B
0x1800dba1d  lea     rdx, [rbx+98h]
0x1800dba24  lea     rcx, _GUID_8ed97ec6_e77c_452e_9866_3747bc305db5
0x1800dba2b  call    cs:__imp_CreateSyncServiceInstance
0x1800dba31  test    eax, eax
0x1800dba33  js      short loc_1800DBA4B
0x1800dba35  mov     rcx, [rbx+98h]
0x1800dba3c  mov     rdx, rdi
0x1800dba3f  mov     rax, [rcx]
0x1800dba42  mov     rax, [rax+18h]
0x1800dba46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dba4b  add     rsp, 28h
0x1800dba4f  pop     rdi
0x1800dba50  pop     rsi
0x1800dba51  pop     rbp
0x1800dba52  pop     rbx
0x1800dba53  retn
```
