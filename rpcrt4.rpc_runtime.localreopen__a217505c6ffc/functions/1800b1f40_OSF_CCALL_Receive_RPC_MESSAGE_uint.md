# OSF_CCALL::Receive(_RPC_MESSAGE *,uint)

- ea: `0x1800b1f40`
- end: `0x1800b20b1`
- name: `?Receive@OSF_CCALL@@UEAAJPEAU_RPC_MESSAGE@@I@Z`
- size: `369`
- prototype: `__int64 __fastcall(OSF_CCALL *__hidden this, struct _RPC_MESSAGE *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800162e0`
- `0x180026500`
- `0x180034eb4`
- `0x180066718`
- `0x1800692a4`
- `0x180099b7c`
- `0x1800a72e0`
- `0x1800b1f40`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800b1f99`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800b1f99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b1f8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b1f8b`

## pseudocode

```c
__int64 __fastcall OSF_CCALL::Receive(OSF_CCALL *this, struct _RPC_MESSAGE *a2, unsigned int a3)
{
  char *v6; // rbx
  DWORD CurrentProcessId; // edi
  unsigned int CommandLineW; // eax
  unsigned int CoalescedBuffer; // ebx
  unsigned int RpcFlags; // r14d
  char *Buffer; // rcx
  unsigned int v12; // eax

  if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 34) + 408LL) + 256LL) )
  {
    if ( !(unsigned int)ShouldSkipLogging(2u) && (Microsoft_Windows_RPC_EventsEnableBits & 1) != 0 )
    {
      v6 = (char *)a2->RpcInterfaceInformation + 4;
      CurrentProcessId = GetCurrentProcessId();
      CommandLineW = (unsigned int)GetCommandLineW();
      McTemplateU0zdzj_EtwEventWriteTransfer(
        (unsigned int)L"ncacn_http",
        (unsigned int)RPC_EVENTLOG_SYNC_PIPE_USE_ERR,
        CommandLineW,
        CurrentProcessId,
        (__int64)L"ncacn_http",
        (__int64)v6);
    }
    CoalescedBuffer = 1764;
LABEL_21:
    OSF_CCALL::UnregisterCallForCancels(this);
    *((_DWORD *)this + 8) = CoalescedBuffer;
    REFERENCED_OBJECT::RemoveReference(this);
    return CoalescedBuffer;
  }
  RpcFlags = a2->RpcFlags;
  if ( (RpcFlags & 0x4000) == 0 )
  {
    Buffer = (char *)a2->Buffer;
    if ( Buffer )
    {
      I_RpcBCacheFree(Buffer - 24);
      a2->Buffer = 0;
    }
  }
  while ( *((_DWORD *)this + 66) != 10 )
  {
    if ( *((_DWORD *)this + 66) == 11 )
    {
      CoalescedBuffer = *((_DWORD *)this + 8);
      goto LABEL_20;
    }
    if ( *((_DWORD *)this + 66) == 12 )
      break;
    if ( *((_DWORD *)this + 84) < (unsigned int)*(unsigned __int16 *)(*((_QWORD *)this + 34) + 48LL) )
    {
      EVENT::Wait((OSF_CCALL *)((char *)this + 424), -1);
    }
    else
    {
      CoalescedBuffer = OSF_CCALL::GetCoalescedBuffer(this, a2);
      if ( CoalescedBuffer )
        goto LABEL_20;
      v12 = a2->RpcFlags;
      if ( (v12 & 0x2000) != 0 && a2->BufferLength >= a3 )
        goto LABEL_20;
      a2->RpcFlags = v12 | 0x4000;
    }
  }
  CoalescedBuffer = OSF_CCALL::GetCoalescedBuffer(this, a2);
LABEL_20:
  a2->DataRepresentation = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 34) + 24LL) + 252LL);
  a2->RpcFlags ^= ((unsigned __int16)RpcFlags ^ (unsigned __int16)a2->RpcFlags) & 0x4000;
  if ( CoalescedBuffer )
    goto LABEL_21;
  return CoalescedBuffer;
}

```

## disassembly

```asm
0x1800b1f40  push    rbx
0x1800b1f42  push    rbp
0x1800b1f43  push    rsi
0x1800b1f44  push    rdi
0x1800b1f45  push    r14
0x1800b1f47  sub     rsp, 30h
0x1800b1f4b  mov     rax, [rcx+110h]
0x1800b1f52  mov     ebp, r8d
0x1800b1f55  mov     rdi, rdx
0x1800b1f58  mov     rsi, rcx
0x1800b1f5b  mov     r9, [rax+198h]
0x1800b1f62  cmp     qword ptr [r9+100h], 0
0x1800b1f6a  jz      short loc_1800B1FD2
0x1800b1f6c  mov     ecx, 2; unsigned int
0x1800b1f71  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x1800b1f76  test    eax, eax
0x1800b1f78  jnz     short loc_1800B1FC8
0x1800b1f7a  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 1
0x1800b1f81  jz      short loc_1800B1FC8
0x1800b1f83  mov     rbx, [rdi+28h]
0x1800b1f87  add     rbx, 4
0x1800b1f8b  call    cs:__imp_GetCurrentProcessId
0x1800b1f92  nop     dword ptr [rax+rax+00h]
0x1800b1f97  mov     edi, eax
0x1800b1f99  call    cs:__imp_GetCommandLineW
0x1800b1fa0  nop     dword ptr [rax+rax+00h]
0x1800b1fa5  lea     rcx, aNcacnHttp; "ncacn_http"
0x1800b1fac  mov     [rsp+58h+var_30], rbx
0x1800b1fb1  mov     r8, rax
0x1800b1fb4  mov     [rsp+58h+var_38], rcx
0x1800b1fb9  mov     r9d, edi
0x1800b1fbc  lea     rdx, RPC_EVENTLOG_SYNC_PIPE_USE_ERR
0x1800b1fc3  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x1800b1fc8  mov     ebx, 6E4h
0x1800b1fcd  jmp     loc_1800B2090
0x1800b1fd2  mov     r14d, [rdx+48h]
0x1800b1fd6  bt      r14d, 0Eh
0x1800b1fdb  jb      short loc_1800B1FF7
0x1800b1fdd  mov     rcx, [rdx+10h]
0x1800b1fe1  test    rcx, rcx
0x1800b1fe4  jz      short loc_1800B1FF7
0x1800b1fe6  add     rcx, 0FFFFFFFFFFFFFFE8h; void *
0x1800b1fea  call    I_RpcBCacheFree
0x1800b1fef  mov     qword ptr [rdi+10h], 0
0x1800b1ff7  mov     ecx, [rsi+108h]
0x1800b1ffd  sub     ecx, 0Ah
0x1800b2000  jz      short loc_1800B205D
0x1800b2002  sub     ecx, 1
0x1800b2005  jz      short loc_1800B2058
0x1800b2007  cmp     ecx, 1
0x1800b200a  jz      short loc_1800B205D
0x1800b200c  mov     rax, [rsi+110h]
0x1800b2013  movzx   ecx, word ptr [rax+30h]
0x1800b2017  cmp     [rsi+150h], ecx
0x1800b201d  jb      short loc_1800B2047
0x1800b201f  mov     rdx, rdi; struct _RPC_MESSAGE *
0x1800b2022  mov     rcx, rsi; this
0x1800b2025  call    ?GetCoalescedBuffer@OSF_CCALL@@AEAAJPEAU_RPC_MESSAGE@@@Z; OSF_CCALL::GetCoalescedBuffer(_RPC_MESSAGE *)
0x1800b202a  mov     ebx, eax
0x1800b202c  test    eax, eax
0x1800b202e  jnz     short loc_1800B206A
0x1800b2030  mov     eax, [rdi+48h]
0x1800b2033  bt      eax, 0Dh
0x1800b2037  jnb     short loc_1800B203E
0x1800b2039  cmp     [rdi+18h], ebp
0x1800b203c  jnb     short loc_1800B206A
0x1800b203e  bts     eax, 0Eh
0x1800b2042  mov     [rdi+48h], eax
0x1800b2045  jmp     short loc_1800B1FF7
0x1800b2047  lea     rcx, [rsi+1A8h]; this
0x1800b204e  or      edx, 0FFFFFFFFh; int
0x1800b2051  call    ?Wait@EVENT@@QEAAHJ@Z; EVENT::Wait(long)
0x1800b2056  jmp     short loc_1800B1FF7
0x1800b2058  mov     ebx, [rsi+20h]
0x1800b205b  jmp     short loc_1800B206A
0x1800b205d  mov     rdx, rdi; struct _RPC_MESSAGE *
0x1800b2060  mov     rcx, rsi; this
0x1800b2063  call    ?GetCoalescedBuffer@OSF_CCALL@@AEAAJPEAU_RPC_MESSAGE@@@Z; OSF_CCALL::GetCoalescedBuffer(_RPC_MESSAGE *)
0x1800b2068  mov     ebx, eax
0x1800b206a  mov     rax, [rsi+110h]
0x1800b2071  mov     rcx, [rax+18h]
0x1800b2075  mov     eax, [rcx+0FCh]
0x1800b207b  mov     [rdi+8], eax
0x1800b207e  mov     eax, [rdi+48h]
0x1800b2081  xor     eax, r14d
0x1800b2084  and     eax, 4000h
0x1800b2089  xor     [rdi+48h], eax
0x1800b208c  test    ebx, ebx
0x1800b208e  jz      short loc_1800B20A3
0x1800b2090  mov     rcx, rsi; this
0x1800b2093  call    ?UnregisterCallForCancels@OSF_CCALL@@AEAAXXZ; OSF_CCALL::UnregisterCallForCancels(void)
0x1800b2098  mov     rcx, rsi; this
0x1800b209b  mov     [rsi+20h], ebx
0x1800b209e  call    ?RemoveReference@REFERENCED_OBJECT@@UEAAXXZ; REFERENCED_OBJECT::RemoveReference(void)
0x1800b20a3  mov     eax, ebx
0x1800b20a5  add     rsp, 30h
0x1800b20a9  pop     r14
0x1800b20ab  pop     rdi
0x1800b20ac  pop     rsi
0x1800b20ad  pop     rbp
0x1800b20ae  pop     rbx
0x1800b20af  retn
```
