# CSdController::QueryLastStatus(_SD_SCHEDULED_BACKUP_STATUS *)

- ea: `0x18000fae0`
- end: `0x18000fc40`
- name: `?QueryLastStatus@CSdController@@UEAAJPEAU_SD_SCHEDULED_BACKUP_STATUS@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(CSdController *__hidden this, struct _SD_SCHEDULED_BACKUP_STATUS *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fae0`
- `0x180013434`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fbfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fbfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbe9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbe9`

## pseudocode

```c
__int64 __fastcall CSdController::QueryLastStatus(CSdController *this, struct _SD_SCHEDULED_BACKUP_STATUS *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  struct _SD_SCHEDULED_BACKUP_STATUS *v6; // rax
  __int16 v7; // ax
  __int128 v8; // xmm0
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  BOOL v10; // edx
  int v11; // eax
  void *v12; // rcx
  unsigned int v13; // ebx
  int PersistentStatus; // [rsp+20h] [rbp-48h] BYREF
  __int16 v16; // [rsp+24h] [rbp-44h]
  __int16 v17; // [rsp+26h] [rbp-42h]
  __int64 v18; // [rsp+98h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&PersistentStatus,
    "CSdController::QueryLastStatus",
    0xAA6u,
    1u);
  v4 = 0;
  v18 = 0;
  if ( a2 )
  {
    v5 = 104;
    v6 = a2;
    do
    {
      *(_BYTE *)v6 = 0;
      v6 = (struct _SD_SCHEDULED_BACKUP_STATUS *)((char *)v6 + 1);
      --v5;
    }
    while ( v5 );
    PersistentStatus = 0;
    v16 = 2733;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    PersistentStatus = CSdController::_ReadPersistentStatus(this, a2);
    v7 = 2745;
    if ( PersistentStatus < 0 )
      goto LABEL_5;
    v8 = *((_OWORD *)this + 7);
    v16 = 2745;
    *(_OWORD *)a2 = v8;
    if ( !*((_DWORD *)this + 27) )
      goto LABEL_14;
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 17);
    v10 = 0;
    if ( v9 )
    {
      PersistentStatus = (**v9)(v9, &IID_ISdAsyncPriv, &v18);
      v7 = 2763;
      if ( PersistentStatus < 0 )
      {
LABEL_5:
        v17 = v7;
LABEL_14:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
        v4 = v18;
        v13 = PersistentStatus;
        goto LABEL_16;
      }
      v16 = 2763;
      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 112LL))(v18) == 0;
    }
    if ( *((_DWORD *)this + 32) || (v11 = 2, v10) )
      v11 = 3;
    *((_DWORD *)a2 + 4) = v11;
    v12 = (void *)*((_QWORD *)a2 + 4);
    *((_DWORD *)a2 + 5) = 0;
    CoTaskMemFree(v12);
    *((_QWORD *)a2 + 4) = 0;
    goto LABEL_14;
  }
  v13 = -2147024809;
  PersistentStatus = -2147024809;
  v17 = 2733;
LABEL_16:
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&PersistentStatus);
  return v13;
}

```

## disassembly

```asm
0x18000fae0  push    rbp
0x18000fae2  push    rbx
0x18000fae3  push    rsi
0x18000fae4  push    rdi
0x18000fae5  mov     rbp, rsp
0x18000fae8  sub     rsp, 68h
0x18000faec  mov     rbx, rdx
0x18000faef  mov     rdi, rcx
0x18000faf2  lea     rdx, aCsdcontrollerQ; "CSdController::QueryLastStatus"
0x18000faf9  mov     r9d, 1; unsigned __int16
0x18000faff  lea     rcx, [rbp+var_48]; this
0x18000fb03  mov     r8d, 0AA6h; unsigned __int16
0x18000fb09  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000fb0e  xor     ecx, ecx
0x18000fb10  mov     [rbp+arg_8], rcx
0x18000fb14  test    rbx, rbx
0x18000fb17  jz      loc_18000FC0A
0x18000fb1d  mov     ecx, 68h ; 'h'
0x18000fb22  mov     rax, rbx
0x18000fb25  mov     byte ptr [rax], 0
0x18000fb28  inc     rax
0x18000fb2b  sub     rcx, 1
0x18000fb2f  jnz     short loc_18000FB25
0x18000fb31  mov     [rbp+var_48], ecx
0x18000fb34  mov     eax, 0AADh
0x18000fb39  lea     rcx, [rdi+40h]; lpCriticalSection
0x18000fb3d  mov     [rbp+var_44], ax
0x18000fb41  call    cs:__imp_EnterCriticalSection
0x18000fb47  mov     rdx, rbx; struct _SD_SCHEDULED_BACKUP_STATUS *
0x18000fb4a  mov     rcx, rdi; this
0x18000fb4d  call    ?_ReadPersistentStatus@CSdController@@AEAAJPEAU_SD_SCHEDULED_BACKUP_STATUS@@@Z; CSdController::_ReadPersistentStatus(_SD_SCHEDULED_BACKUP_STATUS *)
0x18000fb52  mov     [rbp+var_48], eax
0x18000fb55  test    eax, eax
0x18000fb57  mov     eax, 0AB9h
0x18000fb5c  jns     short loc_18000FB67
0x18000fb5e  mov     [rbp+var_42], ax
0x18000fb62  jmp     loc_18000FBF7
0x18000fb67  movups  xmm0, xmmword ptr [rdi+70h]
0x18000fb6b  mov     [rbp+var_44], ax
0x18000fb6f  movdqu  xmmword ptr [rbx], xmm0
0x18000fb73  cmp     dword ptr [rdi+6Ch], 0
0x18000fb77  jz      short loc_18000FBF7
0x18000fb79  mov     rcx, [rdi+88h]
0x18000fb80  xor     edx, edx
0x18000fb82  test    rcx, rcx
0x18000fb85  jz      short loc_18000FBC4
0x18000fb87  mov     rax, [rcx]
0x18000fb8a  lea     r8, [rbp+arg_8]
0x18000fb8e  lea     rdx, IID_ISdAsyncPriv
0x18000fb95  mov     rax, [rax]
0x18000fb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb9d  mov     [rbp+var_48], eax
0x18000fba0  test    eax, eax
0x18000fba2  mov     eax, 0ACBh
0x18000fba7  js      short loc_18000FB5E
0x18000fba9  mov     rcx, [rbp+arg_8]
0x18000fbad  mov     [rbp+var_44], ax
0x18000fbb1  mov     rax, [rcx]
0x18000fbb4  mov     rax, [rax+70h]
0x18000fbb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbbd  xor     edx, edx
0x18000fbbf  test    eax, eax
0x18000fbc1  setz    dl
0x18000fbc4  cmp     dword ptr [rdi+80h], 0
0x18000fbcb  jnz     short loc_18000FBD6
0x18000fbcd  mov     eax, 2
0x18000fbd2  test    edx, edx
0x18000fbd4  jz      short loc_18000FBDB
0x18000fbd6  mov     eax, 3
0x18000fbdb  mov     [rbx+10h], eax
0x18000fbde  mov     rcx, [rbx+20h]; pv
0x18000fbe2  mov     dword ptr [rbx+14h], 0
0x18000fbe9  call    cs:__imp_CoTaskMemFree
0x18000fbef  mov     qword ptr [rbx+20h], 0
0x18000fbf7  lea     rcx, [rdi+40h]; lpCriticalSection
0x18000fbfb  call    cs:__imp_LeaveCriticalSection
0x18000fc01  mov     rcx, [rbp+arg_8]
0x18000fc05  mov     ebx, [rbp+var_48]
0x18000fc08  jmp     short loc_18000FC1B
0x18000fc0a  mov     ebx, 80070057h
0x18000fc0f  mov     eax, 0AADh
0x18000fc14  mov     [rbp+var_48], ebx
0x18000fc17  mov     [rbp+var_42], ax
0x18000fc1b  test    rcx, rcx
0x18000fc1e  jz      short loc_18000FC2C
0x18000fc20  mov     rdx, [rcx]
0x18000fc23  mov     rax, [rdx+10h]
0x18000fc27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc2c  lea     rcx, [rbp+var_48]; this
0x18000fc30  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000fc35  mov     eax, ebx
0x18000fc37  add     rsp, 68h
0x18000fc3b  pop     rdi
0x18000fc3c  pop     rsi
0x18000fc3d  pop     rbx
0x18000fc3e  pop     rbp
0x18000fc3f  retn
```
