# OSF_CCALL::Receive(_RPC_MESSAGE *,uint)

- ea: `0x1800ae380`
- end: `0x1800ae4e4`
- name: `?Receive@OSF_CCALL@@UEAAJPEAU_RPC_MESSAGE@@I@Z`
- size: `356`
- prototype: `__int64 __fastcall(OSF_CCALL *__hidden this, struct _RPC_MESSAGE *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800191d0`
- `0x180025280`
- `0x180061948`
- `0x1800635d0`
- `0x1800637cc`
- `0x1800960fc`
- `0x1800a3fd4`
- `0x1800ae380`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800ae3d3`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800ae3d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ae3cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ae3cb`

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
0x1800ae380  push    rbx
0x1800ae382  push    rbp
0x1800ae383  push    rsi
0x1800ae384  push    rdi
0x1800ae385  push    r14
0x1800ae387  sub     rsp, 30h
0x1800ae38b  mov     rax, [rcx+110h]
0x1800ae392  mov     ebp, r8d
0x1800ae395  mov     rdi, rdx
0x1800ae398  mov     rsi, rcx
0x1800ae39b  mov     r9, [rax+198h]
0x1800ae3a2  cmp     qword ptr [r9+100h], 0
0x1800ae3aa  jz      short loc_1800AE406
0x1800ae3ac  mov     ecx, 2; unsigned int
0x1800ae3b1  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x1800ae3b6  test    eax, eax
0x1800ae3b8  jnz     short loc_1800AE3FC
0x1800ae3ba  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 1
0x1800ae3c1  jz      short loc_1800AE3FC
0x1800ae3c3  mov     rbx, [rdi+28h]
0x1800ae3c7  add     rbx, 4
0x1800ae3cb  call    cs:__imp_GetCurrentProcessId
0x1800ae3d1  mov     edi, eax
0x1800ae3d3  call    cs:__imp_GetCommandLineW
0x1800ae3d9  lea     rcx, aNcacnHttp; "ncacn_http"
0x1800ae3e0  mov     [rsp+58h+var_30], rbx
0x1800ae3e5  mov     r8, rax
0x1800ae3e8  mov     [rsp+58h+var_38], rcx
0x1800ae3ed  mov     r9d, edi
0x1800ae3f0  lea     rdx, RPC_EVENTLOG_SYNC_PIPE_USE_ERR
0x1800ae3f7  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x1800ae3fc  mov     ebx, 6E4h
0x1800ae401  jmp     loc_1800AE4C4
0x1800ae406  mov     r14d, [rdx+48h]
0x1800ae40a  bt      r14d, 0Eh
0x1800ae40f  jb      short loc_1800AE42B
0x1800ae411  mov     rcx, [rdx+10h]
0x1800ae415  test    rcx, rcx
0x1800ae418  jz      short loc_1800AE42B
0x1800ae41a  add     rcx, 0FFFFFFFFFFFFFFE8h; void *
0x1800ae41e  call    I_RpcBCacheFree
0x1800ae423  mov     qword ptr [rdi+10h], 0
0x1800ae42b  mov     ecx, [rsi+108h]
0x1800ae431  sub     ecx, 0Ah
0x1800ae434  jz      short loc_1800AE491
0x1800ae436  sub     ecx, 1
0x1800ae439  jz      short loc_1800AE48C
0x1800ae43b  cmp     ecx, 1
0x1800ae43e  jz      short loc_1800AE491
0x1800ae440  mov     rax, [rsi+110h]
0x1800ae447  movzx   ecx, word ptr [rax+30h]
0x1800ae44b  cmp     [rsi+150h], ecx
0x1800ae451  jb      short loc_1800AE47B
0x1800ae453  mov     rdx, rdi; struct _RPC_MESSAGE *
0x1800ae456  mov     rcx, rsi; this
0x1800ae459  call    ?GetCoalescedBuffer@OSF_CCALL@@AEAAJPEAU_RPC_MESSAGE@@@Z; OSF_CCALL::GetCoalescedBuffer(_RPC_MESSAGE *)
0x1800ae45e  mov     ebx, eax
0x1800ae460  test    eax, eax
0x1800ae462  jnz     short loc_1800AE49E
0x1800ae464  mov     eax, [rdi+48h]
0x1800ae467  bt      eax, 0Dh
0x1800ae46b  jnb     short loc_1800AE472
0x1800ae46d  cmp     [rdi+18h], ebp
0x1800ae470  jnb     short loc_1800AE49E
0x1800ae472  bts     eax, 0Eh
0x1800ae476  mov     [rdi+48h], eax
0x1800ae479  jmp     short loc_1800AE42B
0x1800ae47b  lea     rcx, [rsi+1A8h]; this
0x1800ae482  or      edx, 0FFFFFFFFh; int
0x1800ae485  call    ?Wait@EVENT@@QEAAHJ@Z; EVENT::Wait(long)
0x1800ae48a  jmp     short loc_1800AE42B
0x1800ae48c  mov     ebx, [rsi+20h]
0x1800ae48f  jmp     short loc_1800AE49E
0x1800ae491  mov     rdx, rdi; struct _RPC_MESSAGE *
0x1800ae494  mov     rcx, rsi; this
0x1800ae497  call    ?GetCoalescedBuffer@OSF_CCALL@@AEAAJPEAU_RPC_MESSAGE@@@Z; OSF_CCALL::GetCoalescedBuffer(_RPC_MESSAGE *)
0x1800ae49c  mov     ebx, eax
0x1800ae49e  mov     rax, [rsi+110h]
0x1800ae4a5  mov     rcx, [rax+18h]
0x1800ae4a9  mov     eax, [rcx+0FCh]
0x1800ae4af  mov     [rdi+8], eax
0x1800ae4b2  mov     eax, [rdi+48h]
0x1800ae4b5  xor     eax, r14d
0x1800ae4b8  and     eax, 4000h
0x1800ae4bd  xor     [rdi+48h], eax
0x1800ae4c0  test    ebx, ebx
0x1800ae4c2  jz      short loc_1800AE4D7
0x1800ae4c4  mov     rcx, rsi; this
0x1800ae4c7  call    ?UnregisterCallForCancels@OSF_CCALL@@AEAAXXZ; OSF_CCALL::UnregisterCallForCancels(void)
0x1800ae4cc  mov     rcx, rsi; this
0x1800ae4cf  mov     [rsi+20h], ebx
0x1800ae4d2  call    ?RemoveReference@REFERENCED_OBJECT@@UEAAXXZ; REFERENCED_OBJECT::RemoveReference(void)
0x1800ae4d7  mov     eax, ebx
0x1800ae4d9  add     rsp, 30h
0x1800ae4dd  pop     r14
0x1800ae4df  pop     rdi
0x1800ae4e0  pop     rsi
0x1800ae4e1  pop     rbp
0x1800ae4e2  pop     rbx
0x1800ae4e3  retn
```
