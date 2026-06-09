# ScGetNotifyList(_GUID *,_SCC_NOTIFY_BLOCK *,int,_SCC_SERVER_NOTIFY_LIST * *,int *)

- ea: `0x18003ba74`
- end: `0x18003bcc3`
- name: `?ScGetNotifyList@@YAKPEAU_GUID@@PEAU_SCC_NOTIFY_BLOCK@@HPEAPEAU_SCC_SERVER_NOTIFY_LIST@@PEAH@Z`
- size: `591`
- prototype: `unsigned int __usercall@<eax>(UUID *Uuid@<rcx>, struct _SCC_NOTIFY_BLOCK *@<rdx>, int@<r8d>, struct _SCC_SERVER_NOTIFY_LIST **@<r9>, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013f34`

## callees

- `0x18003ba74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bc5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bca6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bc5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bca6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003bc46`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003bc46`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003bba8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003bba8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bb4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bb4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bc6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bc6c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003bb0c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003bb0c`
- `RPCRT4!UuidEqual` at `0x18003bae1`
- `RPCRT4!UuidEqual` at `0x18003bae1`
- `RPCRT4!UuidIsNil` at `0x18003bb8a`
- `RPCRT4!UuidIsNil` at `0x18003bbe7`
- `RPCRT4!UuidIsNil` at `0x18003bb8a`
- `RPCRT4!UuidIsNil` at `0x18003bbe7`

## pseudocode

```c
__int64 __fastcall ScGetNotifyList(
        UUID *Uuid,
        struct _SCC_NOTIFY_BLOCK *a2,
        int a3,
        struct _SCC_SERVER_NOTIFY_LIST **a4,
        int *a5)
{
  int *v5; // r12
  DWORD LastError; // esi
  char *Data4; // rbx
  UUID *i; // rdi
  int v12; // ebp
  _QWORD *v13; // rax
  void **v14; // rcx
  HANDLE EventW; // rbp
  _QWORD *v16; // rdi
  _QWORD *v17; // rax
  HANDLE Thread; // rcx
  _QWORD *v19; // rax
  RPC_STATUS Status; // [rsp+88h] [rbp+20h] BYREF

  v5 = a5;
  LastError = 0;
  Data4 = 0;
  Status = 0;
  *a5 = 0;
  *a4 = 0;
  for ( i = (UUID *)off_180079798; ; i = *(UUID **)&i->Data1 )
  {
    if ( i == (UUID *)&off_180079798 )
    {
      if ( a3 || UuidIsNil(Uuid, &Status) )
      {
LABEL_12:
        Data4 = (char *)LocalAlloc(0x40u, 0x50u);
        if ( Data4 && (EventW = CreateEventW(0, 0, 0, 0)) != 0 )
        {
          *(_DWORD *)Data4 = 1953721454;
          v16 = Data4 + 24;
          *(UUID *)(Data4 + 40) = *Uuid;
          *((_QWORD *)Data4 + 2) = Data4 + 8;
          *((_QWORD *)Data4 + 1) = Data4 + 8;
          *((_QWORD *)Data4 + 4) = Data4 + 24;
          *((_QWORD *)Data4 + 3) = Data4 + 24;
          if ( UuidIsNil(Uuid, &Status) )
          {
            *((_DWORD *)Data4 + 15) |= 1u;
            v17 = off_1800797A0;
            if ( *off_1800797A0 != (_UNKNOWN *)&off_180079798 )
              goto LABEL_29;
            *v16 = &off_180079798;
            *((_QWORD *)Data4 + 4) = v17;
            *v17 = v16;
            off_1800797A0 = (_UNKNOWN **)(Data4 + 24);
            *a4 = (struct _SCC_SERVER_NOTIFY_LIST *)Data4;
            *((_QWORD *)Data4 + 8) = EventW;
            return LastError;
          }
          Thread = CreateThread(0, 0, ScGetNotifyThread, a2, 0, (LPDWORD)Data4 + 14);
          if ( Thread )
          {
            v19 = off_1800797A0;
            if ( *off_1800797A0 != (_UNKNOWN *)&off_180079798 )
              goto LABEL_29;
            *v16 = &off_180079798;
            *((_QWORD *)Data4 + 4) = v19;
            *v19 = v16;
            off_1800797A0 = (_UNKNOWN **)(Data4 + 24);
            *a4 = (struct _SCC_SERVER_NOTIFY_LIST *)Data4;
            *((_QWORD *)Data4 + 8) = EventW;
            CloseHandle(Thread);
            return LastError;
          }
          LastError = GetLastError();
          CloseHandle(EventW);
        }
        else
        {
          LastError = GetLastError();
        }
        if ( !LastError )
          return LastError;
      }
      else
      {
        LastError = 1235;
      }
      LocalFree(Data4);
      return LastError;
    }
    Data4 = (char *)i[-2].Data4;
    v12 = *(_DWORD *)&i[2].Data2 & 1;
    if ( UuidEqual(i + 1, Uuid, &Status) )
      break;
  }
  if ( a3 == 1 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)Data4 + 18, 1, 0) == 1 )
    {
      do
        Sleep(0xFAu);
      while ( _InterlockedCompareExchange((volatile signed __int32 *)Data4 + 18, 1, 0) == 1 );
      LastError = 0;
    }
    v13 = *(_QWORD **)&i->Data1;
    if ( *(UUID **)(*(_QWORD *)&i->Data1 + 8LL) == i )
    {
      v14 = *(void ***)i->Data4;
      if ( *v14 == i )
      {
        *v14 = v13;
        v13[1] = v14;
        *(_QWORD *)i->Data4 = i;
        *(_QWORD *)&i->Data1 = i;
        goto LABEL_12;
      }
    }
LABEL_29:
    __fastfail(3u);
  }
  if ( !v12 )
    *v5 = 1;
  *a4 = (struct _SCC_SERVER_NOTIFY_LIST *)Data4;
  return LastError;
}

```

## disassembly

```asm
0x18003ba74  mov     rax, rsp
0x18003ba77  mov     [rax+8], rbx
0x18003ba7b  mov     [rax+10h], rdx
0x18003ba7f  push    rbp
0x18003ba80  push    rsi
0x18003ba81  push    rdi
0x18003ba82  push    r12
0x18003ba84  push    r13
0x18003ba86  push    r14
0x18003ba88  push    r15
0x18003ba8a  sub     rsp, 30h
0x18003ba8e  mov     r12, [rsp+68h+arg_20]
0x18003ba96  xor     esi, esi
0x18003ba98  xor     ebx, ebx
0x18003ba9a  mov     r14, r9
0x18003ba9d  mov     r15d, r8d
0x18003baa0  mov     [rax+20h], ebx
0x18003baa3  mov     r13, rcx
0x18003baa6  mov     [r12], ebx
0x18003baaa  mov     [r9], rbx
0x18003baad  mov     rdi, cs:off_180079798
0x18003bab4  lea     rcx, off_180079798
0x18003babb  mov     eax, 1
0x18003bac0  cmp     rdi, rcx
0x18003bac3  jz      loc_18003BB7A
0x18003bac9  lea     rbx, [rdi-18h]
0x18003bacd  mov     rdx, r13; Uuid2
0x18003bad0  mov     ebp, [rbx+3Ch]
0x18003bad3  lea     rcx, [rbx+28h]; Uuid1
0x18003bad7  lea     r8, [rsp+68h+Status]; Status
0x18003badf  and     ebp, eax
0x18003bae1  call    cs:__imp_UuidEqual
0x18003bae7  test    eax, eax
0x18003bae9  jnz     short loc_18003BAF0
0x18003baeb  mov     rdi, [rdi]
0x18003baee  jmp     short loc_18003BAB4
0x18003baf0  mov     ecx, 1
0x18003baf5  cmp     r15d, ecx
0x18003baf8  jnz     short loc_18003BB6A
0x18003bafa  xor     eax, eax
0x18003bafc  lock cmpxchg [rbx+48h], ecx
0x18003bb01  cmp     eax, ecx
0x18003bb03  jnz     short loc_18003BB1F
0x18003bb05  mov     esi, ecx
0x18003bb07  mov     ecx, 0FAh; dwMilliseconds
0x18003bb0c  call    cs:__imp_Sleep
0x18003bb12  xor     eax, eax
0x18003bb14  lock cmpxchg [rbx+48h], esi
0x18003bb19  cmp     eax, esi
0x18003bb1b  jz      short loc_18003BB07
0x18003bb1d  xor     esi, esi
0x18003bb1f  mov     rax, [rdi]
0x18003bb22  cmp     [rax+8], rdi
0x18003bb26  jnz     loc_18003BC87
0x18003bb2c  mov     rcx, [rdi+8]
0x18003bb30  cmp     [rcx], rdi
0x18003bb33  jnz     loc_18003BC87
0x18003bb39  mov     [rcx], rax
0x18003bb3c  mov     [rax+8], rcx
0x18003bb40  mov     [rdi+8], rdi
0x18003bb44  mov     [rdi], rdi
0x18003bb47  mov     edx, 50h ; 'P'; uBytes
0x18003bb4c  lea     ecx, [rdx-10h]; uFlags
0x18003bb4f  call    cs:__imp_LocalAlloc
0x18003bb55  mov     rbx, rax
0x18003bb58  test    rax, rax
0x18003bb5b  jnz     short loc_18003BB9E
0x18003bb5d  call    cs:__imp_GetLastError
0x18003bb63  mov     esi, eax
0x18003bb65  jmp     loc_18003BC65
0x18003bb6a  test    ebp, ebp
0x18003bb6c  jnz     short loc_18003BB72
0x18003bb6e  mov     [r12], ecx
0x18003bb72  mov     [r14], rbx
0x18003bb75  jmp     loc_18003BCAC
0x18003bb7a  test    r15d, r15d
0x18003bb7d  jnz     short loc_18003BB47
0x18003bb7f  lea     rdx, [rsp+68h+Status]; Status
0x18003bb87  mov     rcx, r13; Uuid
0x18003bb8a  call    cs:__imp_UuidIsNil
0x18003bb90  test    eax, eax
0x18003bb92  jnz     short loc_18003BB47
0x18003bb94  mov     esi, 4D3h
0x18003bb99  jmp     loc_18003BC69
0x18003bb9e  xor     r9d, r9d; lpName
0x18003bba1  xor     r8d, r8d; bInitialState
0x18003bba4  xor     edx, edx; bManualReset
0x18003bba6  xor     ecx, ecx; lpEventAttributes
0x18003bba8  call    cs:__imp_CreateEventW
0x18003bbae  mov     rbp, rax
0x18003bbb1  test    rax, rax
0x18003bbb4  jz      short loc_18003BB5D
0x18003bbb6  mov     dword ptr [rbx], 74736C6Eh
0x18003bbbc  lea     rax, [rbx+8]
0x18003bbc0  movups  xmm0, xmmword ptr [r13+0]
0x18003bbc5  lea     rdi, [rbx+18h]
0x18003bbc9  mov     rcx, r13; Uuid
0x18003bbcc  lea     rdx, [rsp+68h+Status]; Status
0x18003bbd4  movdqu  xmmword ptr [rbx+28h], xmm0
0x18003bbd9  mov     [rax+8], rax
0x18003bbdd  mov     [rax], rax
0x18003bbe0  mov     [rdi+8], rdi
0x18003bbe4  mov     [rdi], rdi
0x18003bbe7  call    cs:__imp_UuidIsNil
0x18003bbed  test    eax, eax
0x18003bbef  jz      short loc_18003BC25
0x18003bbf1  or      dword ptr [rbx+3Ch], 1
0x18003bbf5  lea     rdx, off_180079798
0x18003bbfc  mov     rax, cs:off_1800797A0
0x18003bc03  cmp     [rax], rdx
0x18003bc06  jnz     short loc_18003BC87
0x18003bc08  mov     [rdi], rdx
0x18003bc0b  mov     [rdi+8], rax
0x18003bc0f  mov     [rax], rdi
0x18003bc12  mov     cs:off_1800797A0, rdi
0x18003bc19  mov     [r14], rbx
0x18003bc1c  mov     [rbx+40h], rbp
0x18003bc20  jmp     loc_18003BCAC
0x18003bc25  mov     r9, [rsp+68h+lpParameter]; lpParameter
0x18003bc2a  lea     rax, [rbx+38h]
0x18003bc2e  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18003bc33  lea     r8, ?ScGetNotifyThread@@YAKPEAX@Z; lpStartAddress
0x18003bc3a  xor     edx, edx; dwStackSize
0x18003bc3c  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18003bc44  xor     ecx, ecx; lpThreadAttributes
0x18003bc46  call    cs:__imp_CreateThread
0x18003bc4c  mov     rcx, rax; hObject
0x18003bc4f  test    rax, rax
0x18003bc52  jnz     short loc_18003BC74
0x18003bc54  call    cs:__imp_GetLastError
0x18003bc5a  mov     rcx, rbp; hObject
0x18003bc5d  mov     esi, eax
0x18003bc5f  call    cs:__imp_CloseHandle
0x18003bc65  test    esi, esi
0x18003bc67  jz      short loc_18003BCAC
0x18003bc69  mov     rcx, rbx; hMem
0x18003bc6c  call    cs:__imp_LocalFree
0x18003bc72  jmp     short loc_18003BCAC
0x18003bc74  mov     rax, cs:off_1800797A0
0x18003bc7b  lea     rdx, off_180079798
0x18003bc82  cmp     [rax], rdx
0x18003bc85  jz      short loc_18003BC8E
0x18003bc87  mov     ecx, 3
0x18003bc8c  int     29h; Win8: RtlFailFast(ecx)
0x18003bc8e  mov     [rdi], rdx
0x18003bc91  mov     [rdi+8], rax
0x18003bc95  mov     [rax], rdi
0x18003bc98  mov     cs:off_1800797A0, rdi
0x18003bc9f  mov     [r14], rbx
0x18003bca2  mov     [rbx+40h], rbp
0x18003bca6  call    cs:__imp_CloseHandle
0x18003bcac  mov     rbx, [rsp+68h+arg_0]
0x18003bcb1  mov     eax, esi
0x18003bcb3  add     rsp, 30h
0x18003bcb7  pop     r15
0x18003bcb9  pop     r14
0x18003bcbb  pop     r13
0x18003bcbd  pop     r12
0x18003bcbf  pop     rdi
0x18003bcc0  pop     rsi
0x18003bcc1  pop     rbp
0x18003bcc2  retn
```
