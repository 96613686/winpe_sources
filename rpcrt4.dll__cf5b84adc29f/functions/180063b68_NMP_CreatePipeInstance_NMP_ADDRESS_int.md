# NMP_CreatePipeInstance(NMP_ADDRESS *,int)

- ea: `0x180063b68`
- end: `0x180063d82`
- name: `?NMP_CreatePipeInstance@@YAJPEAUNMP_ADDRESS@@H@Z`
- size: `538`
- prototype: `__int64 __fastcall(struct NMP_ADDRESS *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180064f20`
- `0x180086690`

## callees

- `0x180016600`
- `0x180023020`
- `0x180023a40`
- `0x180063b68`
- `0x180064e3c`
- `0x18006e110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063cf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063cf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063d13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063d13`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180063c99`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180063c99`

## pseudocode

```c
__int64 __fastcall NMP_CreatePipeInstance(struct NMP_ADDRESS *a1)
{
  __int64 i; // rdx
  __int64 v3; // r8
  __int64 result; // rax
  _QWORD *v5; // rax
  __int64 v6; // rax
  void *v7; // rcx
  DWORD LastError; // ebx
  void *v9; // rcx
  DWORD v10; // ebx
  DWORD v11; // ebx
  DWORD v12; // ebx
  DWORD v13; // ebx
  DWORD v14; // ebx
  DWORD v15; // ebx
  DWORD v16; // ebx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-28h] BYREF

  SecurityAttributes.lpSecurityDescriptor = (LPVOID)*((_QWORD *)a1 + 34);
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  CSpinLock::Lock((struct NMP_ADDRESS *)((char *)a1 + 208));
  for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 56); i = (unsigned int)(i + 1) )
  {
    v3 = *(_QWORD *)(*((_QWORD *)a1 + 27) + 8 * i);
    if ( v3 )
      goto LABEL_6;
  }
  LODWORD(i) = 0;
  v3 = 0;
LABEL_6:
  *((_QWORD *)a1 + 25) = v3;
  if ( v3 )
  {
    SIMPLE_DICT::Delete((struct NMP_ADDRESS *)((char *)a1 + 216), i);
    result = 3221360672LL;
    _InterlockedExchange(
      (volatile __int32 *)a1 + 52,
      ((*((_DWORD *)a1 + 52) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)a1 + 52) - 0x10000000 : 0);
    return result;
  }
  _InterlockedExchange(
    (volatile __int32 *)a1 + 52,
    ((*((_DWORD *)a1 + 52) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)a1 + 52) - 0x10000000 : 0);
  v5 = AllocWrapper(0x40u);
  *((_QWORD *)a1 + 25) = v5;
  if ( !v5 )
    return 14;
  *v5 = a1;
  *(_QWORD *)(*((_QWORD *)a1 + 25) + 48LL) = 0;
  *(_QWORD *)(*((_QWORD *)a1 + 25) + 56LL) = CreateNamedPipeW(
                                               *((LPCWSTR *)a1 + 35),
                                               0x40000003u,
                                               *((_DWORD *)a1 + 72) != 0 ? 14 : 6,
                                               0xFFu,
                                               0x800u,
                                               0x800u,
                                               0,
                                               &SecurityAttributes);
  v6 = *((_QWORD *)a1 + 25);
  v7 = *(void **)(v6 + 56);
  if ( v7 == (void *)-1LL )
  {
    LastError = GetLastError();
LABEL_14:
    v9 = *(void **)(*((_QWORD *)a1 + 25) + 56LL);
    if ( v9 != (void *)-1LL )
      CloseHandle(v9);
    FreeWrapper(*((void **)a1 + 25));
    *((_QWORD *)a1 + 25) = 0;
    v10 = LastError - 2;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 2;
        if ( !v12 )
          return 1740;
        v13 = v12 - 3;
        if ( !v13 )
          return 14;
        v14 = v13 - 6;
        if ( !v14 )
          return 14;
        v15 = v14 - 109;
        if ( v15 )
        {
          v16 = v15 - 1327;
          if ( v16 && v16 != 366 )
            return 1766;
          return 14;
        }
      }
    }
    return 1706;
  }
  result = RPC_THREAD_POOL::CreateIoEx(
             v7,
             (PTP_WIN32_IO_CALLBACK)CO_NmpThreadPoolCallback,
             0,
             1,
             (struct RPC_THREAD_POOL_IO **)(v6 + 48));
  LastError = result;
  if ( (_DWORD)result )
    goto LABEL_14;
  return result;
}

```

## disassembly

```asm
0x180063b68  mov     r11, rsp
0x180063b6b  mov     [r11+8], rbx
0x180063b6f  push    rdi
0x180063b70  sub     rsp, 60h
0x180063b74  mov     rax, [rcx+110h]
0x180063b7b  mov     rdi, rcx
0x180063b7e  add     rcx, 0D0h; this
0x180063b85  mov     [r11-20h], rax
0x180063b89  mov     qword ptr [r11-28h], 18h
0x180063b91  mov     qword ptr [r11-18h], 0
0x180063b99  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x180063b9e  xor     edx, edx
0x180063ba0  lea     r9, [rdi+0D8h]
0x180063ba7  cmp     edx, [r9+8]
0x180063bab  jnb     short loc_180063BBD
0x180063bad  mov     rax, [r9]
0x180063bb0  mov     r8, [rax+rdx*8]
0x180063bb4  test    r8, r8
0x180063bb7  jnz     short loc_180063BC2
0x180063bb9  inc     edx
0x180063bbb  jmp     short loc_180063BA7
0x180063bbd  xor     edx, edx; unsigned int
0x180063bbf  xor     r8d, r8d
0x180063bc2  mov     [rdi+0C8h], r8
0x180063bc9  test    r8, r8
0x180063bcc  jz      short loc_180063C0A
0x180063bce  mov     rcx, r9; this
0x180063bd1  call    ?Delete@SIMPLE_DICT@@QEAAPEAXI@Z; SIMPLE_DICT::Delete(uint)
0x180063bd6  mov     r9d, [rdi+0D0h]
0x180063bdd  add     r9d, 0F0000000h
0x180063be4  mov     eax, r9d
0x180063be7  and     eax, 0F0000000h
0x180063bec  neg     eax
0x180063bee  mov     eax, 0C0021020h
0x180063bf3  sbb     ecx, ecx
0x180063bf5  and     ecx, r9d
0x180063bf8  xchg    ecx, [rdi+0D0h]
0x180063bfe  mov     rbx, [rsp+68h+arg_0]
0x180063c03  add     rsp, 60h
0x180063c07  pop     rdi
0x180063c08  retn
0x180063c0a  mov     edx, [rdi+0D0h]
0x180063c10  add     edx, 0F0000000h
0x180063c16  mov     eax, edx
0x180063c18  and     eax, 0F0000000h
0x180063c1d  neg     eax
0x180063c1f  sbb     ecx, ecx
0x180063c21  and     ecx, edx
0x180063c23  xchg    ecx, [rdi+0D0h]
0x180063c29  mov     ecx, 40h ; '@'; dwBytes
0x180063c2e  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180063c33  mov     [rdi+0C8h], rax
0x180063c3a  test    rax, rax
0x180063c3d  jz      loc_180063CEA
0x180063c43  mov     [rax], rdi
0x180063c46  mov     edx, 40000003h; dwOpenMode
0x180063c4b  mov     rax, [rdi+0C8h]
0x180063c52  mov     r9d, 0FFh; nMaxInstances
0x180063c58  mov     qword ptr [rax+30h], 0
0x180063c60  mov     eax, [rdi+120h]
0x180063c66  mov     rcx, [rdi+118h]; lpName
0x180063c6d  neg     eax
0x180063c6f  lea     rax, [rsp+68h+SecurityAttributes]
0x180063c74  mov     [rsp+68h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180063c79  sbb     r8d, r8d
0x180063c7c  mov     eax, 800h
0x180063c81  mov     [rsp+68h+nDefaultTimeOut], 0; nDefaultTimeOut
0x180063c89  and     r8d, 8
0x180063c8d  mov     [rsp+68h+nInBufferSize], eax; nInBufferSize
0x180063c91  add     r8d, 6; dwPipeMode
0x180063c95  mov     [rsp+68h+nOutBufferSize], eax; nOutBufferSize
0x180063c99  call    cs:__imp_CreateNamedPipeW
0x180063ca0  nop     dword ptr [rax+rax+00h]
0x180063ca5  mov     rcx, [rdi+0C8h]
0x180063cac  mov     [rcx+38h], rax
0x180063cb0  mov     rax, [rdi+0C8h]
0x180063cb7  mov     rcx, [rax+38h]; fl
0x180063cbb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180063cbf  jz      short loc_180063CF4
0x180063cc1  add     rax, 30h ; '0'
0x180063cc5  lea     rdx, ?CO_NmpThreadPoolCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x180063ccc  mov     r9d, 1; int
0x180063cd2  mov     qword ptr [rsp+68h+nOutBufferSize], rax; struct RPC_THREAD_POOL_IO **
0x180063cd7  xor     r8d, r8d; pv
0x180063cda  call    ?CreateIoEx@RPC_THREAD_POOL@@SAJPEAXP6AXPEAU_TP_CALLBACK_INSTANCE@@00K_KPEAU_TP_IO@@@Z0HPEAPEAVRPC_THREAD_POOL_IO@@@Z; RPC_THREAD_POOL::CreateIoEx(void *,void (*)(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *),void *,int,RPC_THREAD_POOL_IO * *)
0x180063cdf  mov     ebx, eax
0x180063ce1  test    eax, eax
0x180063ce3  jnz     short loc_180063D02
0x180063ce5  jmp     loc_180063BFE
0x180063cea  mov     eax, 0Eh
0x180063cef  jmp     loc_180063BFE
0x180063cf4  call    cs:__imp_GetLastError
0x180063cfb  nop     dword ptr [rax+rax+00h]
0x180063d00  mov     ebx, eax
0x180063d02  mov     rax, [rdi+0C8h]
0x180063d09  mov     rcx, [rax+38h]; hObject
0x180063d0d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180063d11  jz      short loc_180063D1F
0x180063d13  call    cs:__imp_CloseHandle
0x180063d1a  nop     dword ptr [rax+rax+00h]
0x180063d1f  mov     rcx, [rdi+0C8h]; lpMem
0x180063d26  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180063d2b  mov     qword ptr [rdi+0C8h], 0
0x180063d36  sub     ebx, 2
0x180063d39  jz      short loc_180063D78
0x180063d3b  sub     ebx, 1
0x180063d3e  jz      short loc_180063D78
0x180063d40  sub     ebx, 2
0x180063d43  jz      short loc_180063D6E
0x180063d45  sub     ebx, 3
0x180063d48  jz      short loc_180063CEA
0x180063d4a  sub     ebx, 6
0x180063d4d  jz      short loc_180063CEA
0x180063d4f  sub     ebx, 6Dh ; 'm'
0x180063d52  jz      short loc_180063D78
0x180063d54  sub     ebx, 52Fh
0x180063d5a  jz      short loc_180063CEA
0x180063d5c  cmp     ebx, 16Eh
0x180063d62  jz      short loc_180063CEA
0x180063d64  mov     eax, 6E6h
0x180063d69  jmp     loc_180063BFE
0x180063d6e  mov     eax, 6CCh
0x180063d73  jmp     loc_180063BFE
0x180063d78  mov     eax, 6AAh
0x180063d7d  jmp     loc_180063BFE
```
